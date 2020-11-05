---
title: HoloLens を Kiosk としてセットアップする
description: HoloLens でアプリをロックダウンするには、キオスクの構成を使用します。
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: c4c4b533538ab7998f8438d7cc0c2f3d88143ec6
ms.sourcegitcommit: 4e168380c23e8463438aa8a1388baf8d5ac1a1ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2020
ms.locfileid: "11154187"
---
# HoloLens を Kiosk としてセットアップする

HoloLens デバイスを、キオスクモードで実行するように構成することによって、 *キオスク*デバイス (キオスクとも呼ばれます) として機能させることができます。 キオスクモードでは、デバイスで利用可能なアプリケーション (またはユーザー) を制限します。 キオスクモードは、HoloLens デバイスをビジネスアプリ専用にするために使うことができる便利な機能です。または、アプリデモで HoloLens デバイスを使うことができます。

この記事では、HoloLens デバイスに固有のキオスク構成の要素について説明します。 Windows ベースのキオスクのさまざまな種類とその構成方法については、「 [windows デスクトップエディションでのキオスクとデジタル署名の構成](https://docs.microsoft.com/windows/configuration/kiosk-methods)」を参照してください。  

> [!IMPORTANT]  
> キオスクモードは、ユーザーがデバイスにサインインしたときに利用できるアプリを決定します。 ただし、キオスクモードはセキュリティの方法ではありません。 これにより、許可されていない別のアプリを開くことができなくなることはありません。 アプリやプロセスが開かれないようにするには、 [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) を使って適切なポリシーを作成します。
>
> Microsoft サービスの詳細については、「HoloLens 2 で使用する高度なセキュリティレベルをユーザーに提供する」を参照してください。 [状態の分離と分離防御の保護](security-state-separation-isolation.md#defender-protections)について詳しくはこちらをご覧ください。 または、 [WDAC と Windows PowerShell を使用して、Microsoft Intune との HoloLens 2 デバイスでアプリを許可またはブロックする](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)方法について説明します。

キオスクモードは1つのアプリまたは複数のアプリの構成で使うことができます。また、3つのプロセスのいずれかを使って、キオスク構成を設定して展開することもできます。

> [!IMPORTANT]  
> マルチアプリ構成を削除すると、割り当てられたアクセス機能で作成されたユーザーロックダウンプロファイルが削除されます。 ただし、すべてのポリシーの変更は元に戻すわけではありません。 これらのポリシーを元に戻すには、デバイスを出荷時の設定にリセットする必要があります。

## キオスク展開を計画する

キオスクを計画する際には、次の質問に答えることができる必要があります。 ここでは、このページを閲覧する際に考慮すべき事項と、それらの質問に関するいくつかの考慮事項について説明します。
1. **自分のキオスクを使用するユーザーと、そのユーザーが使用する [アカウントの種類](hololens-identity.md) を教えてください。** これは、既に作成されている可能性があり、キオスクのように調整する必要はありませんが、キオスクを後で割り当てる方法に影響します。
1. **ユーザー/グループごとに異なるキオスクを持っているか、一部のキオスクが有効になっていないかどうかを確認する必要がありますか?** その場合は、XML を使ってキオスクを作成します。 
1. **キオスクには何人のアプリがありますか?** アプリが1つ以上ある場合は、マルチアプリキオスクが必要です。 
1. **どのアプリがキオスクに表示されますか?** 以下のリストに記載されている Aumid を使用して、独自の In-Box アプリも追加してください。
1. **キオスクの展開を計画するにはどうすればよいですか?** MDM にデバイスを登録している場合は、MDM を使用してキオスクを展開することをお勧めします。 MDM を使っていない場合は、プロビジョニングパッケージと共に展開することができます。  

### キオスクモードの要件

すべての HoloLens 2 デバイスでキオスクモードを使用するように構成することができます。

HoloLens (第1世代) デバイスでキオスクモードを使用するように構成するには、デバイスが Windows 10、バージョン1803、またはそれ以降のバージョンを実行していることを確認する必要があります。 HoloLens (第1世代) デバイスを既定のビルドに復元するために Windows デバイス回復ツールを使っている場合、または最新の更新プログラムがインストールされている場合は、デバイスを構成することができます。

> [!IMPORTANT]  
> キオスクモードで実行されているデバイスを保護するには、USB 接続などの機能をオフにするデバイス管理ポリシーを追加することを検討してください。 さらに、更新プログラムのリング設定を確認して、営業時間中に自動更新が行われないようにします。

### 単一アプリのキオスクと複数アプリのキオスクのどちらを選択するかを決定する

1つのアプリのキオスクは、ユーザーがデバイスにサインインしたときに、指定されたアプリを起動します。 [スタート] メニューは、Cortana のように無効になっています。 HoloLens 2 デバイスは、 [開始](hololens2-basic-usage.md#start-gesture) ジェスチャには応答しません。 HoloLens (第1世代) デバイスは、 [ブルーム](hololens1-basic-usage.md) ジェスチャに対応していません。 1つのアプリのみを実行できるため、ユーザーは他のアプリを配置することはできません。

マルチアプリキオスクは、ユーザーがデバイスにサインインしたときに [スタート] メニューを表示します。 キオスクの構成では、[スタート] メニューで使用できるアプリを決定します。 複数アプリのキオスクを使って、ユーザーが使用する必要があるものだけを表示したり、使用する必要がないものを削除したりすることで、ユーザーにとってわかりやすいエクスペリエンスを提供することができます。

次の表に、さまざまなキオスクモードの機能の一覧を示します。

| &nbsp; |スタート メニュー |クイック操作メニュー |カメラとビデオ |Miracast |Cortana |組み込みの音声コマンド |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|単一アプリのキオスク |無効 |無効   |無効 |無効   |無効 |Enabled <sup> 1</sup> |
|複数アプリ キオスク |有効 |Enabled <sup> 2</sup> |利用可能な <sup> 2</sup> |利用可能な <sup> 2</sup> |利用可能な <sup> 2、3</sup>  |Enabled <sup> 1</sup> |

> <sup>1 </sup> 無効な機能に関連する音声コマンドが機能しません。  
> <sup>2 </sup> これらの機能を構成する方法の詳細については、「 [キオスクアプリを選択](#plan-kiosk-apps)する」を参照してください。  
> <sup>3 </sup> Cortana が無効になっている場合でも、組み込みの音声コマンドは有効になります。

次の表は、さまざまなキオスクモードのユーザーサポート機能をまとめたものです。

| &nbsp; |サポートされているユーザーの種類 | 自動サインイン | 複数のアクセスレベル |
| --- | --- | --- | --- |
|単一アプリのキオスク |Azure Active Directory (AAD) またはローカルアカウントの管理されたサービスアカウント (MSA) |あり |なし |
|複数アプリ キオスク |AAD アカウント |なし |あり |

これらの機能の使用方法の例については、次の表を参照してください。

|単一アプリのキオスクの用途: |複数のアプリでのキオスクの用途: |
| --- | --- |
|新しい従業員向けの Dynamics 365 ガイドのみを実行するデバイス。 |さまざまな従業員のガイドとリモートアシスタンスの両方を実行するデバイス。 |
|カスタムアプリのみを実行するデバイス。 |ほとんどのユーザーのためにキオスクとして機能する (カスタムアプリのみを実行します)、特定のユーザーグループの標準デバイスとして機能するデバイス。 |

### キオスクアプリを計画する

キオスクアプリの選択方法に関する一般的な情報については、「 [割り当てられたアクセスのアプリを選ぶためのガイドライン (キオスクモード)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)」を参照してください。

Windows Device Portal を使って単一アプリのキオスクを構成する場合は、セットアッププロセス中にアプリを選択します。  

モバイルデバイス管理 (MDM) システムまたはプロビジョニングパッケージを使ってキオスクモードを構成する場合は、 [AssignedAccess 構成サービスプロバイダー (CSP)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) を使ってアプリケーションを指定します。 CSP は、 [アプリケーションユーザーモデル id (aumid)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) を使ってアプリケーションを特定します。 次の表に、マルチアプリキオスクで使用できる Aumid アプリケーションの一覧を示します。

> [!IMPORTANT]
> キオスクモードは、ユーザーがデバイスにサインインしたときに利用できるアプリを決定します。 ただし、キオスクモードはセキュリティの方法ではありません。 これにより、許可されていない別のアプリを開くことができなくなることはありません。 この動作は制限されていないため、アプリは Edge、エクスプローラー、Microsoft ストアアプリから起動することができます。 キオスクで起動したくない特定のアプリがある場合は、 [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) を使って適切なポリシーを作成します。 
> 
> さらに、Mixed Reality ホームをキオスクアプリとして設定することはできません。

<a id="aumids"></a>

|アプリ名 |AUMID |
| --- | --- |
|3D ビューアー |Microsoft3DViewer \ _8wekyb3d8bbwe \!Microsoft3DViewer |
|カレンダー |windowscommunicationsapps \ _8wekyb3d8bbwe \! windowslive の予定表 |
|カメラ <sup> 1、2</sup> |HoloCamera \ _cw5n1h2txyewy \!HoloCamera |
|Cortana <sup> 3</sup> |Microsoft 2015 9981C3F5F10 \ _8wekyb3d8bbwe \!アプリケーション |
|HoloLens のデバイスピッカー (第1世代) |HoloDevicesFlow \ _cw5n1h2txyewy \!HoloDevicesFlow |
|HoloLens 2 のデバイスピッカー |DevicesFlowHost \ _cw5n1h2txyewy \!DevicesFlowHost |
|Dynamics 365 Guides |Dynamics365 () _8wekyb3d8bbwe \!Microsoft のガイド |
|Dynamics 365 Remote Assist |Microsoft office サポートの \ _8wekyb3d8bbwe \!Microsoft RemoteAssist |
|フィードバック &nbsp; Hub |Microsoft Windowsフィードバックハブ \ _8wekyb3d8bbwe \!アプリケーション |
|エクスプローラー |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|メール |microsoft.windowscommunicationsapps_8wekyb3d8bbwe! windowslive |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast <sup> 4</sup> |&nbsp; |
|映画 & テレビ |Microsoft ZuneVideo \ _8wekyb3d8bbweMicrosoft ZuneVideo |
|OneDrive |microsoft office skydrive \ _8wekyb3d8bbweアプリケーション |
|フォト |Microsoft. 写真 \ _8wekyb3d8bbwe \!アプリケーション |
|設定 |HolographicSystemSettings \ _cw5n1h2txyewy \!アプリケーション |
|ヒント |HoloLensTips \ _8wekyb3d8bbwe \!HoloLensTips |

> <sup>1 </sup> 写真またはビデオのキャプチャを有効にするには、カメラアプリをキオスクアプリとして有効にする必要があります。  
> <sup>2 </sup> カメラアプリを有効にする場合は、次の条件に注意してください。
> - [クイック操作] メニューには、写真とビデオのボタンが含まれています。  
> - 画像を操作したり、写真を取得したりできるアプリ (写真、メール、OneDrive など) も有効にする必要があります。  
>  
> <sup>3 </sup> キオスクアプリとして Cortana を有効にしていない場合でも、組み込みの音声コマンドは有効になります。 ただし、無効な機能に関連するコマンドには影響はありません。  
> <sup>4 </sup> Miracast を直接有効にすることはできません。 キオスクのアプリとして Miracast を有効にするには、カメラアプリとデバイスピッカーアプリを有効にします。

### ユーザーまたはグループのキオスクプロファイルを計画する

Xml ファイルを作成するとき、または Intune の UI を使用してキオスクを設定するときは、ユーザーがキオスクを行うユーザーを考慮する必要があります。 キオスク構成は、個々のアカウントまたは Azure AD グループに制限することができます。 

通常、キオスクはユーザーまたはユーザーグループに対して有効になっています。 ただし、独自の XML キオスクの作成を計画している場合は、Id に関係なく、キオスクがデバイスレベルで適用される、グローバルに割り当てられたアクセスを検討することをお勧めします。 この appeals では、 [グローバルに割り当てられているアクセスキオスクについての詳細をご覧ください。](hololens-global-assigned-access-kiosk.md)

#### XML ファイルを作成する場合は、次の操作を行います。
-   複数のキオスクプロファイルを作成し、それぞれを別々のユーザー/グループに割り当てることができます。 多数のアプリを持つ AAD グループのキオスク、単数形のアプリで複数のアプリのキオスクを使用しているビジタなど。
-   キオスクの構成は、 **プロファイル Id** として表示され、GUID が含まれます。
-   このプロファイルは、[設定] セクションで、ユーザーの種類を指定し、 **Defaultprofile Id**と同じ GUID を使うことによって割り当てられます。
- XML ファイルは作成できますが、カスタム OMA URI デバイス構成プロファイルを作成して、URI 値を使って HoloLens デバイスグループに適用することによって、MDM 経由でデバイスに適用することができます。/Device/Vendor/MSFT/AssignedAccess/Configuration

#### Intune でキオスクを作成している場合。
-   各デバイスは、1つのキオスクプロファイルのみを受け取ることができます。それ以外の場合は、競合が発生し、キオスクの構成をまったく受け取りません。 
    -   キオスク構成プロファイルに関連付けられていないデバイスの制限など、他の種類のプロファイルとポリシーは、キオスク構成プロファイルと競合しません。
-   [キオスク] は、ユーザーログオンの種類の一部であるすべてのユーザーに対して有効になります。これは、ユーザーまたは AAD グループで設定されます。 
-   キオスクの構成を設定し、 **ユーザーのログオンの種類** (キオスクにログインできるユーザー) とアプリを選択した後、デバイスの構成をグループに割り当てる必要があります。 割り当てられたグループは、キオスクデバイスの構成を受け取るデバイスを決定します。ただし、キオスクが有効になっているかどうかは操作できません。 
    - Intune で構成プロファイルを割り当てる場合の影響の詳細については、「 [Microsoft intune でユーザーとデバイスのプロファイルを割り当てる](https://docs.microsoft.com/intune/configuration/device-profile-assign)」を参照してください。

### 展開方法を選択する

キオスクの構成を展開するには、次のいずれかの方法を選択できます。

- [Microsoft Intune またはその他のモバイルデバイス管理 (MDM) サービス](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [プロビジョニング パッケージ](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Device Portal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > このメソッドでは、デバイスで開発者モードが有効になっている必要があるため、デモ用にのみ使用することをお勧めします。

次の表に、各展開方法の機能と利点を示します。

| &nbsp; |Windows Device Portal を使用して展開する |プロビジョニングパッケージを使用して展開する |MDM を使用して展開する |
| --------------------------- | ------------- | -------------------- | ---- |
|単一アプリのキオスクの展開   | あり           | あり                  | あり  |
|複数アプリのキオスクの展開    | なし            | あり                  | あり  |
|ローカルデバイスのみに展開する | あり           | あり                  | なし   |
|開発者モードを使用して展開する |必須かどうか       | 任意            | 任意   |
|Azure Active Directory (AAD) を使用して展開する  | 任意            | 任意                   | 必須かどうか  |
|自動的に展開する      | なし            | なし                   | あり  |
|展開の速度            | Fast (高速)       | Fast (高速)                 | スロー (低速) |
|Scale で展開する | 推奨されない    | 推奨        | 推奨 |

## Microsoft Intune またはその他の MDM を使用して、1つのアプリまたは複数のアプリのキオスクを設定する

Microsoft Intune または別の MDM システムを使用してキオスクモードを設定するには、次の手順を実行します。

1. [デバイスの登録を準備](#mdmenroll)します。
1. [キオスク構成プロファイルを作成](#mdmprofile)します。
1. キオスクを構成します。
   - [単一アプリのキオスクの設定を構成](#mdmconfigsingle)します。
   - [マルチアプリキオスクの設定を構成](#mdmconfigmulti)します。
1. [キオスクの構成プロファイルをグループに割り当て](#mdmassign)ます。
1. デバイスを展開します。
   - [単一アプリのキオスクを展開](#mdmsingledeploy)します。
   - [複数アプリのキオスクを展開](#mdmmultideploy)します。

### <a id="mdmenroll"></a>MDM、ステップ 1 &ndash; デバイスの登録を準備する

ユーザーが最初にサインインしたとき、またはユーザーがデバイスを手動で登録したときに HoloLens デバイスを自動的に登録するように MDM システムを構成することができます。 また、デバイスは、Azure AD ドメインに参加し、適切なグループに割り当てる必要があります。

デバイスの登録方法の詳細については、「MDM および[Windows デバイスの Intune 登録方法](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)[に HoloLens を登録](hololens-enroll-mdm.md)する」を参照してください。

### <a id="mdmprofile"></a>MDM、手順 2: &ndash; キオスク構成プロファイルを作成する

1. [Azure](https://portal.azure.com/) portal を開いて、Intune 管理者アカウントにサインインします。
1. [ **Microsoft Intune**  >  **デバイス構成-プロファイルの**  >  **作成プロファイル**] を選択します。
1. プロファイル名を入力します。
1. [ **Platform**  >  **Windows 10**以降] を選択し、[**プロファイルの種類**のデバイスの制限] を選択し  > **Device restrictions**ます。
1. [キオスクの**構成**] を選択し、  >  **Kiosk**次のいずれかを選択します。
   - 単一アプリのキオスクを作成するには、[**キオスクモード**  >  **単一アプリキオスク**] を選びます。
   - マルチアプリキオスクを作成するには、[**キオスクモード**  >  **マルチアプリキオスク**] を選択します。
1. キオスクの構成を開始するには、[ **追加**] を選択します。

次の手順は、必要なキオスクの種類によって異なります。 詳細については、次のいずれかのオプションを選択します。  

- [単一アプリのキオスク](#mdmconfigsingle)
- [複数アプリ キオスク](#mdmconfigmulti)

キオスク構成プロファイルの作成方法の詳細については、「 [windows 10 と Windows ホログラフィック For Business デバイスの設定」を参照して、Intune を使って専用のキオスクとして実行](https://docs.microsoft.com/intune/configuration/kiosk-settings)してください。

### <a id="mdmconfigsingle"></a>MDM、ステップ 3 (単一アプリ) &ndash;  1 つのアプリのキオスクの設定を構成する

このセクションでは、単一アプリのキオスクで必要な設定の概要を示します。 詳細については、次の記事を参照してください。

- Intune でキオスク構成プロファイルを構成する方法については、「 [Microsoft Intune を使用してキオスクモードを構成する方法](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)」を参照してください。
- Intune での単一アプリのキオスクで利用可能な設定について詳しくは、「[全画面表示アプリのキオスク](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)」をご覧ください。
- その他の MDM サービスについては、使用しているプロバイダーのドキュメントで手順を参照してください。 MDM サービスでユーザー設定の XML 構成を使用してキオスクを設定する必要がある場合は、 [キオスクの構成を定義する xml ファイルを作成](#ppkioskconfig)します。

1. [**ユーザーログオンの種類**の  >  **ローカルユーザーアカウント**] を選択し、キオスクにサインインできるローカル (デバイス) アカウントまたは Microsoft アカウント (MSA) のユーザー名を入力します。
   > [!NOTE]  
   > **自動ログオン** ユーザーアカウントの種類は、Windows ホログラフィック for Business ではサポートされていません。
1. [ **Application type**  >  **Store アプリ**] を選び、一覧からアプリを選びます。

次の手順では、プロファイルをグループに [割り当て](#mdmassign) ます。

### <a id="mdmconfigmulti"></a>MDM、手順 3 (マルチアプリ) &ndash; マルチアプリキオスクの設定を構成する

このセクションでは、マルチアプリのキオスクで必要な設定の概要を示します。 詳細については、次の記事を参照してください。

- Intune でキオスク構成プロファイルを構成する方法については、「 [Microsoft Intune を使用してキオスクモードを構成する方法](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)」を参照してください。
- Intune でのマルチアプリキオスクで利用可能な設定の詳細については、「[マルチアプリキオスク](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)」を参照してください。
- その他の MDM サービスについては、使用しているプロバイダーのドキュメントで手順を参照してください。 カスタム XML 構成を使用して、MDM サービスでキオスクを設定する必要がある場合は、 [キオスクの構成を定義する xml ファイルを作成](#ppkioskconfig)します。 XML ファイルを使用する場合は、[ [開始] レイアウト](#start-layout-for-hololens)を含めるようにします。  
- 必要に応じて、Intune またはその他の MDM サービスでカスタム開始レイアウトを使用することができます。 詳細については、「 [MDM のレイアウトファイルを開始する (Intune など)](#start-layout-file-for-mdm-intune-and-others)」を参照してください。

1. **S モードデバイスのターゲット Windows 10**を選択し  >  **No**ます。  
   >[!NOTE]  
   > S モードは、Windows ホログラフィック for Business ではサポートされていません。
1. [**ユーザーログオンの種類**] を選択し、[  >  **Azure AD ユーザー] また**は [グループ] または [**ユーザーログオンの種類**] を選び  >  ます。次に、1つ**以上の**ユーザーグループまたはアカウントを追加します。  

   **ユーザーのログオンの種類**で指定したグループまたはアカウントに属しているユーザーのみが、キオスクのエクスペリエンスを使用できます。

1. 次のオプションを使用して、1つまたは複数のアプリを選択します。
   - アップロードした基幹業務アプリを追加するには、[ **ストアアプリの追加** ] を選択し、目的のアプリを選択します。
   - AUMID を指定してアプリを追加するには、[ **AUMID によって追加** ] を選択し、アプリの AUMID を入力します。 [利用可能な Aumid のリストを表示する](#aumids)

次の手順では、プロファイルをグループに [割り当て](#mdmassign) ます。

### <a id="mdmassign"></a>MDM、手順 4 &ndash; グループにキオスク構成プロファイルを割り当てる

キオスク構成プロファイルの [ **課題** ] ページを使用して、キオスクの構成を展開する場所を設定します。 最も単純なケースでは、MDM にデバイスを登録するときに、HoloLens デバイスを含むグループにキオスク構成プロファイルを割り当てることになります。

### <a id="mdmsingledeploy"></a>MDM、ステップ 5 (単一アプリ) &ndash; 1 つのアプリでのキオスクの展開

MDM システムを使用する場合は、OOBE 中に MDM にデバイスを登録することができます。 OOBE が終了したら、デバイスへのサインインは簡単です。

OOBE 中に、次の手順を実行します。

1. キオスク構成プロファイルで指定したアカウントを使用してサインインします。
1. デバイスを登録します。 キオスク構成プロファイルが割り当てられているグループに、デバイスが追加されていることを確認します。
1. OOBE が完了するのを待って、ストアアプリがダウンロードとインストールを行い、ポリシーが適用されるようにします。 次に、デバイスを再起動します。

次にデバイスにサインインしたときに、キオスクアプリが自動的に起動します。

この時点でキオスクの設定が表示されない場合は、 [課題の状態を確認](https://docs.microsoft.com/intune/configuration/device-profile-monitor)してください。

### <a id="mdmmultideploy"></a>MDM、ステップ 5 (マルチアプリ) に &ndash; よるマルチアプリキオスクの展開

MDM システムを使用する場合は、デバイスを Azure AD テナントに参加させることができます。また、OOBE 中に MDM にデバイスを登録することもできます。 必要に応じて、ユーザーに登録情報を提供します。これにより、そのユーザーは、OOBE プロセスで利用できるようになります。

> [!NOTE]  
> ユーザーを含むグループに [キオスク構成] プロファイルが割り当てられている場合は、これらのいずれかのユーザーアカウントが、デバイスにサインインする最初のアカウントであることを確認してください。

OOBE 中に、次の手順を実行します。

1. [ **ユーザーログオンの種類** ] グループに属しているアカウントを使用してサインインします。
1. デバイスを登録します。
1. キオスク構成プロファイルに含まれているすべてのアプリについて、ダウンロードしてインストールします。 また、ポリシーが適用されるのを待ちます。  
1. OOBE が完了したら、Microsoft ストアまたはサイドローディングから追加のアプリをインストールできます。 デバイスが属しているグループに[必要なアプリ](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)が自動的にインストールされます。
1. インストールが完了したら、デバイスを再起動します。

次に、 **ユーザーのログオンの種類**に属するアカウントを使用してデバイスにサインインすると、キオスクアプリが自動的に起動します。

この時点でキオスクの設定が表示されない場合は、 [課題の状態を確認](https://docs.microsoft.com/intune/configuration/device-profile-monitor)してください。

## プロビジョニングパッケージを使用して1つのアプリまたは複数のアプリのキオスクを設定する

プロビジョニングパッケージを使用してキオスクモードを設定するには、次の手順を実行します。

1. [キオスクの構成を定義する XML ファイルを作成します。](#ppkioskconfig)これには、 [開始レイアウト](#start-layout-for-hololens)も含まれます。
2. [プロビジョニングパッケージに XML ファイルを追加します。](#ppconfigadd)
3. [HoloLens にプロビジョニングパッケージを適用します。](#ppapply)

### <a id="ppkioskconfig"></a>プロビジョニングパッケージ、手順 1 &ndash; キオスク構成の XML ファイルを作成する

次の点を除き、 [一般的な手順に従って、Windows デスクトップ用のキオスク構成の XML ファイルを作成](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)します。

- クラシック Windows アプリケーション (Win32) は含まれません。 HoloLens はこれらのアプリケーションをサポートしていません。
- HoloLens 用の [プレースホルダーの開始レイアウト XML](#start-layout-for-hololens) を使用します。
- オプション: キオスクの構成へのゲストアクセスの追加

#### <a id="ppkioskguest"></a>オプション: キオスクの構成へのゲストアクセスの追加

[XML ファイルの **[構成**] セクション](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)で、[ゲスト] という名前の特別なグループを構成して、ゲストがキオスクを使用できるよう**にすること**ができます。 **ユーザー**設定の特殊グループをサポートするようにキオスクを構成すると、サインインページに "**ゲスト**" オプションが追加されます。 **Guest**アカウントではパスワードは必要ありません。また、アカウントに関連付けられているすべてのデータは、アカウントのサインアウト時に削除されます。

**ゲスト**アカウントを有効にするには、次のスニペットをキオスク構成 XML に追加します。

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a>HoloLens のプレースホルダーの開始のレイアウト

[プロビジョニングパッケージ](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)を使ってマルチアプリのキオスクを構成する場合は、この手順で開始レイアウトが必要になります。 スタート画面のレイアウトのカスタマイズは、Windows ホログラフィック for Business ではサポートされていません。 そのため、プレースホルダーの開始レイアウトを使用する必要があります。

> [!NOTE]  
> 1つのアプリのキオスクでは、ユーザーがサインインしたときにキオスクアプリが起動されるため、スタートメニューを使っていないため、開始レイアウトを設定する必要はありません。

> [!NOTE]  
> [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)を使ってマルチアプリのキオスクを設定する場合は、必要に応じて開始レイアウトを使うことができます。 詳細については、「 [MDM (Intune およびその他) のプレースホルダーの開始レイアウトファイル](#start-layout-file-for-mdm-intune-and-others)」を参照してください。

開始レイアウトの場合は、次の **startlayout** セクションを KIOSK provisioning XML ファイルに追加します。

```xml
<!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
            <StartLayout>
                <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
                      <LayoutOptions StartTileGroupCellWidth="6" />
                      <DefaultLayoutOverride>
                        <StartLayoutCollection>
                          <defaultlayout:StartLayout GroupCellWidth="6">
                            <start:Group Name="">
                              <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
                            </start:Group>
                          </defaultlayout:StartLayout>
                        </StartLayoutCollection>
                      </DefaultLayoutOverride>
                    </LayoutModificationTemplate>
                ]]>
            </StartLayout>
            <!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
```

#### <a id="start-layout-file-for-mdm-intune-and-others"></a>MDM (Intune およびその他) のプレースホルダーの開始レイアウトファイル

次のサンプルを XML ファイルとして保存します。 このファイルは、Microsoft Intune (またはキオスクプロファイルを提供する別の MDM サービス) でマルチアプリキオスクを構成するときに使用できます。

> [!NOTE]
> カスタム設定と完全な XML 構成を使って MDM サービスでキオスクを設定する必要がある場合は、 [プロビジョニングパッケージの開始レイアウトの手順](#start-layout-for-hololens)を使用します。

```xml
<LayoutModificationTemplate
    xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"
    xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout"
    xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout"
    Version="1">
  <RequiredStartGroupsCollection>
    <RequiredStartGroups>
      <AppendGroup Name="">
        <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
      </AppendGroup>
    </RequiredStartGroups>
  </RequiredStartGroupsCollection>
 </LayoutModificationTemplate>
```

### <a id="ppconfigadd"></a>Prov.xml. パッケージ、手順2「 &ndash; キオスク構成 XML ファイルをプロビジョニングパッケージに追加する」

1. [Windows 構成デザイナー](https://www.microsoft.com/store/apps/9nblggh4tx22)を開きます。
1. [ **Advanced provisioning**] を選んで、プロジェクトの名前を入力し、[ **次へ**] を選択します。
1. [ **Windows 10 ホログラフィック**] を選び、[ **次へ**] を選びます。
1. [ **完了**] を選びます。 パッケージのワークスペースが開きます。
1. [ **Runtime settings**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**] を選びます。
1. 中央のウィンドウで、[ **参照** ] を選択して、作成したキオスク構成の XML ファイルを見つけて選択します。

   ![Windows 構成デザイナーにおける MultiAppAssignedAccessSettings フィールドのスクリーンショット](./images/multiappassignedaccesssettings.png)

1. **省略可能**。 (デバイスの最初のセットアップ後にプロビジョニングパッケージを適用する場合、キオスクデバイスで既に管理者ユーザーが利用可能である場合は、この手順をスキップします)。[**ランタイム設定**アカウントユーザー] を選択し、 &gt; **Accounts** &gt; **Users**ユーザーアカウントを作成します。 ユーザー名とパスワードを入力して、[ **UserGroup**  >  **管理者**] を選択します。  
  
     このアカウントを使用すると、プロビジョニングの状態とログを表示できます。  
1. **省略可能**。 (キオスクデバイスで管理者以外のアカウントを既に持っている場合は、この手順をスキップします)。[**ランタイム設定**アカウントユーザー] を選択し &gt; **Accounts** &gt; **Users**、ローカルユーザーアカウントを作成します。 ユーザー名が、構成 XML で指定したアカウントと同じであることを確認します。 [ **UserGroup**  >  **Standard ユーザー**] を選択します。
1. [**ファイル**  >  の**保存**] を選びます。
1. [ **Export**  >  **プロビジョニングパッケージ**のエクスポート] を選択し、[**所有者**の  >  **IT 管理**者] を選択します。これにより、このプロビジョニングパッケージの優先順位が、他のソースからこのデバイスに適用されるプロビジョニングパッケージよりも高くなります。
1. **[次へ]** を選択します。
1. [ **プロビジョニングパッケージのセキュリティ** ] ページで、セキュリティオプションを選びます。
   > [!IMPORTANT]  
   > [ **パッケージ署名を有効**にする] を選択した場合は、パッケージの署名に使用する有効な証明書を選択する必要もあります。 これを行うには、[ **参照** ] を選択し、パッケージの署名に使用する証明書を選択します。
   
   > [!CAUTION]  
   > [パッケージの **暗号化を有効にする**] を選択しないでください。 HoloLens デバイスでは、この設定によってプロビジョニングが失敗します。
1. **[次へ]** を選択します。
1. プロビジョニングパッケージをビルドするときの出力場所を指定します。 既定では、Windows 構成デザイナーはプロジェクト フォルダーを出力先として使います。 出力場所を変更する場合は、[ **参照**] を選択します。 完了したら、[ **次へ**] を選びます。
1. [ **ビルド** ] を選択して、パッケージの作成を開始します。 プロビジョニング パッケージのビルドにはそれほど時間はかかりません。 ビルドページにプロジェクト情報が表示され、進行状況バーにはビルドの状態が示されます。

### <a id="ppapply"></a>プロビジョニングパッケージ、手順 3 &ndash; プロビジョニングパッケージを HoloLens に適用する

「プロビジョニングパッケージを使って HoloLens を構成する」の記事では、次のような状況でプロビジョニングパッケージを適用するための詳しい手順について説明します。

- [セットアップ時に、最初にプロビジョニングパッケージを HoloLens に適用](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)することができます。

- [セットアップ後に、プロビジョニングパッケージを HoloLens に適用](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)することもできます。

## Windows Device Portal を使用して単一アプリのキオスクを設定する

Windows Device Portal を使用してキオスクモードを設定するには、次の手順を実行します。

> [!IMPORTANT]
> キオスクモードは、デバイスに [Windows ホログラフィック For Business](hololens1-upgrade-enterprise.md) がインストールされている場合にのみ使用できます。

1. [Windows Device Portal を使用するように HoloLens デバイス](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)をセットアップします。 デバイス ポータルは、お使いの PC に Web ブラウザーから接続することができる HoloLens 上の Web サーバーです。

    > [!CAUTION]
    > HoloLens で Device Portal を使うように設定する場合は、デバイスで開発者モードを有効にする必要があります。 Windows ホログラフィック for Business がインストールされているデバイスの開発者モードでは、アプリをサイドロードすることができます。 ただし、この設定では、Microsoft Store によって認定されていないアプリをユーザーがインストールできるというリスクが生じます。 管理者は、[ポリシー CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)の**Applicationmanagement/allowdeveloper Unlock**設定を使用して、開発者モードを有効にする機能をブロックすることができます。 [開発者モードの詳細をご覧ください。](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. コンピューターで、 [wi-fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) または [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)を使って HoloLens に接続します。

1. 次のいずれかの操作を行います。
   - Windows Device Portal に初めて接続している場合は、[ユーザー名とパスワードを作成](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)する
   - 以前に設定したユーザー名とパスワードを入力します。

    > [!TIP]
    > ブラウザーに証明書エラーが表示された場合は、[こちらのトラブルシューティング手順](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)に従います。

1. Windows Device Portal で、[ **キオスクモード**] を選びます。

1. [ **キオスクモードを有効**にする] を選択し、デバイスの起動時に実行するアプリを選択して、[ **保存**] を選択します。

    ![Kiosk Mode (キオスク モード)](images/kiosk.png)
1. HoloLens を再起動します。 まだデバイスポータルページを開いている場合は、ページの上部にある [ **再起動** ] を選択できます。

> [!NOTE]
> キオスクモードは、Device Portal の REST API を使って設定することができます。/api/holographic/kioskmode/settings には、1つの必要なクエリ文字列パラメーター ("true" または "false" の値を持つ "kioskModeEnabled") と1つのオプションパラメーター (パッケージ名の値を持つ "startupApp") を指定します。 Device Portal は開発者のみを対象としており、開発者以外のデバイスでは有効にしないように注意してください。 REST API は、将来の更新/リリースで変更される可能性があります。

## 詳細情報

プロビジョニングパッケージを使用して、キオスクを構成する方法をご覧ください。  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

## HoloLens 用 XML Kiosk コードサンプル

### AAD グループをターゲットとする複数のアプリのキオスクモード。 
この kiosk は、AAD グループ内のユーザーに対してキオスクを展開します。これには、設定、リモートアシスタンス、フィードバック Hub の3つのアプリを含むキオスクが有効になります。 すぐに使用されるようにこのサンプルを変更するには、自分の AAD グループと一致するように、以下で強調表示されている GUID を変更してください。 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### AAD アカウントを対象とする複数のアプリのキオスクモード。
この kiosk は、1人のユーザーに対してキオスクを展開し、3つのアプリ (設定、リモートアシスト、フィードバック Hub) を含むキオスクを有効にします。 直ちに使用されるようにこのサンプルを変更するには、自分の AAD アカウントに合わせて、以下で強調表示されているアカウントを変更してください。 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

