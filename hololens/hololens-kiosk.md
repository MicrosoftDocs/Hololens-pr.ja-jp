---
title: HoloLens を Kiosk としてセットアップする
description: キオスク構成を使って HoloLens 上のアプリをロックダウンします。
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
ms.openlocfilehash: 777c90c4be397e176281ee72cb684a561ba78cfa
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253034"
---
# HoloLens を Kiosk としてセットアップする

キオスク モードで実行するデバイスを構成することで、HoloLens デバイスを固定目的のデバイス**(キオスクとも呼ばれる) として機能するために構成できます。 キオスク モードでは、デバイスで利用可能なアプリケーション (またはユーザー) が制限されます。 キオスク モードは、HoloLens デバイスをビジネス アプリ専用にしたり、アプリ のデモで HoloLens デバイスを使用したりするために使用できる便利な機能です。

この記事では、HoloLens デバイスに固有のキオスク構成の側面について説明します。 さまざまな種類の Windows ベースのキオスクと、それらを構成する方法に関する一般的な情報については、「Windows デスクトップ エディションでキオスクとデジタル サイネージを構成する」を [参照してください](https://docs.microsoft.com/windows/configuration/kiosk-methods)。  

> [!IMPORTANT]  
> キオスク モードは、ユーザーがデバイスにサインインするときに利用できるアプリを決定します。 ただし、キオスク モードはセキュリティ方法ではありません。 "許可" アプリが、許可されていない別のアプリを開くのを停止するのではありません。 アプリまたはプロセスを開くのをブロックするには、Windows Defender [Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) を使用して適切なポリシーを作成します。
>
> HoloLens 2 で使用される高度なレベルのセキュリティをユーザーに提供する Microsoft サービスの詳細については、「状態の分離と分離 [- Defender](security-state-separation-isolation.md#defender-protections)保護」を参照してください。 または、Microsoft Intune で WDAC と Windows PowerShell を使って [HoloLens 2](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)デバイス上のアプリを許可またはブロックする方法について説明します。

キオスク モードは、単一アプリ構成または複数アプリ構成で使用できます。キオスク構成のセットアップと展開には、3 つのプロセスのいずれかを使用できます。

> [!IMPORTANT]  
> 複数アプリ構成を削除すると、割り当てられたアクセス機能によって作成されたユーザー ロックダウン プロファイルが削除されます。 ただし、すべてのポリシー変更が元に戻されるわけではありません。 これらのポリシーを元に戻すには、デバイスを工場出荷時の設定にリセットする必要があります。

## キオスクの展開を計画する

キオスクを計画する場合は、次の質問に回答できる必要があります。 このページを読む際に考慮する必要があるいくつかの決定事項と、これらの質問に関する考慮事項を次に示します。
1. **キオスクを使用するユーザーと、ユーザーが使用する[アカウントの種類](hololens-identity.md)** これは、キオスクのために既に行われた可能性が高く、調整すべきではないが、キオスクが後で割り当てられる方法に影響を与える可能性がある決定です。
1. **ユーザー/グループごとに異なるキオスクを使用するか、一部のキオスクを有効にしない必要がありますか?** その場合は、XML を使用してキオスクを作成します。 
1. **キオスクに含めるアプリの数** 1 つ以上のアプリがある場合は、複数アプリキオスクが必要です。 
1. **キオスクに含めになるアプリは何ですか?** 以下の AUMID の一覧を使用して、独自のアプリIn-Boxアプリを追加してください。
1. **キオスクの展開を計画する方法** MDM にデバイスを登録している場合は、MDM を使ってキオスクを展開します。 MDM を使用していない場合は、プロビジョニング パッケージを使った展開を利用できます。  

### キオスク モードの要件

キオスク モードを使う HoloLens 2 デバイスを構成できます。

> [!IMPORTANT]
> キオスク モードは、デバイスに Windows Holographic for Business がある場合にのみ使用できます。 すべての HoloLens 2 デバイスには Windows Holographic for Business が組み込まれているので、他のエディションはありません。 すべての HoloLens 2 デバイスは、オンボックスからキオスク モードを実行できます。
>
> HoloLens (第 1 世代) デバイスは、OS ビルドと OS エディションの両方でアップグレードする必要があります。 HoloLens (第 1 世代) を Windows Holographic for Business エディションに更新する方法について詳 [しくは、以下をご覧](hololens1-upgrade-enterprise.md) ください。 キオスク モードを使う HoloLens (第 1 世代) デバイスを更新するには、まず、デバイスが Windows 10 バージョン 1803 以降のバージョンを実行している必要があります。 Windows デバイス回復ツールを使って HoloLens (第 1 世代) デバイスを既定のビルドに回復した場合、または最新の更新プログラムをインストールしている場合は、デバイスを構成する準備が整っています。

> [!IMPORTANT]  
> キオスク モードで実行されるデバイスを保護するには、USB 接続などの機能をオフにするデバイス管理ポリシーを追加する方法を検討してください。 さらに、更新リングの設定を確認して、営業時間内に自動更新が行われるのを確認します。

### 単一アプリキオスクと複数アプリキオスクの 2 つを決定する

シングル アプリ キオスクは、ユーザーがデバイスにサインインすると、指定したアプリを起動します。 スタート メニューは、Cortana と同様に無効になっています。 HoloLens 2 デバイスがスタート ジェスチャに [応答](hololens2-basic-usage.md#start-gesture) しない。 HoloLens (第 1 世代) デバイスは、ブルーム ジェスチャに [応答](hololens1-basic-usage.md) しない。 1 つのアプリしか実行できないので、ユーザーは他のアプリを配置できません。

複数アプリのキオスクは、ユーザーがデバイスにサインインするとスタート メニューを表示します。 キオスクの構成によって、スタート メニューで利用できるアプリが決まる。 複数アプリのキオスクを使って、使う必要があるものだけをユーザーに提示し、使う必要のなかったものを削除することで、ユーザーにわかりやすいエクスペリエンスを提供できます。

次の表に、さまざまなキオスク モードの機能を示します。

| &nbsp; |スタート メニュー |[クイック 操作] メニュー |カメラとビデオ |Miracast |Cortana |組み込みの音声コマンド |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|シングル アプリ キオスク |無効 |無効   |無効 |無効   |無効 |有効 <sup> 1</sup> |
|複数アプリ キオスク |有効 |有効 <sup> 2</sup> |Available <sup> 2</sup> |Available <sup> 2</sup> |Available <sup> 2, 3</sup>  |有効 <sup> 1</sup> |

> <sup>無効に </sup> された機能に関連する 1 つの音声コマンドが機能しません。  
> <sup>2 </sup> これらの機能を構成する方法の詳細については、「キオスク アプリの選択」を [参照してください](#plan-kiosk-apps)。  
> <sup>3 </sup> Cortana が無効になっている場合でも、組み込みの音声コマンドが有効になります。

次の表に、さまざまなキオスク モードのユーザー サポート機能を示します。

| &nbsp; |サポートされるユーザーの種類 | 自動サインイン | 複数のアクセス レベル |
| --- | --- | --- | --- |
|シングル アプリ キオスク |Azure Active Directory (Azure AD) またはローカル アカウントの管理サービス アカウント (MSA) |○ |なし |
|複数アプリ キオスク |Azure AD アカウント |なし |○ |

これらの機能の使用例については、次の表を参照してください。

|次の場合は、単一アプリキオスクを使用します。 |次の場合に複数アプリキオスクを使用します。 |
| --- | --- |
|新入社員向け Dynamics 365 ガイドのみを実行するデバイス。 |一部の従業員に対してガイドとリモート アシスタンスの両方を実行するデバイス。 |
|カスタム アプリのみを実行するデバイス。 |ほとんどのユーザーのキオスクとして機能するデバイス (カスタム アプリのみを実行) が、特定のユーザー グループの標準デバイスとして機能するデバイス。 |

### キオスク アプリを計画する

キオスク アプリの選択方法に関する一般的な情報については、「割り当てられたアクセス用のアプリを選択するためのガイドライン (キオスク モード)」 [を参照してください](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)。

Windows Device Portal を使ってシングル アプリ キオスクを構成する場合は、セットアップ プロセス中にアプリを選択します。  

モバイル デバイス管理 (MDM) システムまたはプロビジョニング パッケージを使ってキオスク モードを構成する場合は [、AssignedAccess 構成](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) サービス プロバイダー (CSP) を使用してアプリケーションを指定します。 CSP は [アプリケーション ユーザー モデル ID (AUMID)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) を使用してアプリケーションを識別します。 次の表に、複数アプリキオスクで使用できる一部のインボックス アプリケーションの AUMID を示します。

> [!IMPORTANT]
> キオスク モードは、ユーザーがデバイスにサインインするときに利用できるアプリを決定します。 ただし、キオスク モードはセキュリティ方法ではありません。 "許可" アプリが、許可されていない別のアプリを開くのを停止するのではありません。 この動作は制限されていないので、Edge、エクスプローラー、Microsoft Store アプリからアプリを起動できます。 キオスクから起動したくない特定のアプリがある場合は [、Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) を使って適切なポリシーを作成します。 
> 
> さらに、Mixed Reality ホームをキオスク アプリとして設定できない。

<a id="aumids"></a>

|アプリ名 |AUMID |
| --- | --- |
|3D ビューアー |Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\!Microsoft.Microsoft3DViewer |
|カレンダー |microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\!microsoft.windowslive.calendar |
|カメラ <sup> 1、2</sup> |HoloCamera\_cw5n1h2txyewy\!HoloCamera |
|Cortana <sup> 3</sup> |Microsoft.549981C3F5F10\_8wekyb3d8bbwe\!App |
|HoloLens (第 1 世代) のデバイス ピッカー |HoloDevicesFlow\_cw5n1h2txyewy\!HoloDevicesFlow |
|HoloLens 2 のデバイス ピッカー |Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\!Microsoft.Windows.DevicesFlowHost |
|Dynamics 365 Guides |Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\!MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\!Microsoft.RemoteAssist |
|フィードバック &nbsp; Hub |Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\!App |
|エクスプローラー |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|メール |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast <sup> 4</sup> |&nbsp; |
|映画 & テレビ |Microsoft.ZuneVideo\_8wekyb3d8bbwe\!Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive\_8wekyb3d8bbwe\!App |
|フォト |Microsoft.Windows.Photos\_8wekyb3d8bbwe\!App |
|設定 |HolographicSystemSettings\_cw5n1h2txyewy\!App |
|ヒント |Microsoft.HoloLensTips\_8wekyb3d8bbwe\!HoloLensTips |

> <sup>1 </sup> 写真やビデオのキャプチャを有効にするには、キオスク アプリとしてカメラ アプリを有効にする必要があります。  
> <sup>2 </sup> カメラ アプリを有効にする場合は、次の条件に注意してください。
> - クイック アクション メニューには、[写真] ボタンと [ビデオ] ボタンがあります。  
> - 写真を操作または取得できるアプリ (フォト、メール、OneDrive など) も有効にする必要があります。  
>  
> <sup>3 キオスク アプリとして Cortana を有効にしていない場合でも、組み込みの </sup> 音声コマンドが有効になります。 ただし、無効にされた機能に関連するコマンドは無効になります。  
> <sup>4 </sup> Miracast を直接有効にすることはできません。 キオスク アプリとして Miracast を有効にするには、カメラ アプリとデバイス ピッカー アプリを有効にします。

### ユーザーまたはグループのキオスク プロファイルを計画する

xml ファイルを作成する場合、または Intune の UI を使用してキオスクをセットアップする場合は、キオスクのユーザーになるユーザーを検討する必要があります。 キオスクの構成は、個々のアカウントまたは Azure のグループADできます。 

通常、キオスクは、ユーザーまたはユーザー グループに対して有効になります。 ただし、独自の XML キオスクの作成を計画している場合は、ID に関係なくデバイス レベルでキオスクが適用されるグローバル割り当てアクセスを検討できます。 グローバルな割り当てられたアクセス キオスク [について詳しくは、この記事をご覧ください。](hololens-global-assigned-access-kiosk.md)

#### XML ファイルを作成する場合:
-   多くの場合、複数のキオスク プロファイルを作成し、それぞれを異なるユーザー/グループに割り当てる必要があります。 多くのアプリを持つ Azure AD グループのキオスクや、1 つのアプリを持つ複数のアプリ キオスクを持つ訪問者などです。
-   キオスク構成はプロファイル ID と呼ばされ **、GUID** が設定されます。
-   ユーザーの種類を指定し、DefaultProfile ID に同じ GUID を使用して、configs セクションでプロファイル **を割り当てる必要があります**。
- カスタム OMA URI デバイス構成プロファイルを作成し、URI 値を使用して HoloLens デバイス グループに適用することで、XML ファイルを作成できますが、MDM を介してデバイスに適用できます。./Device/Vendor/MSFT/AssignedAccess/Configuration

#### Intune でキオスクを作成する場合。
-   各デバイスは 1 つのキオスク プロファイルのみを受け取る場合があります。それ以外の場合、競合が発生し、キオスク構成を受け取る必要はありません。 
    -   キオスク構成プロファイルに関連しないデバイスの制限など、他の種類のプロファイルとポリシーは、キオスク構成プロファイルと競合しない。
-   キオスクは、ユーザー ログオンの種類に含まれるすべてのユーザーに対して有効になります。これは、ユーザーまたは Azure AD グループに設定されます。 
-   キオスクの構成を設定し、ユーザー ログオンの種類 **(キオスク** にログインできるユーザー) と [アプリ] を選択した後も、デバイスの構成をグループに割り当てる必要があります。 割り当てられたグループは、キオスク デバイスの構成を受け取るデバイスを決定しますが、キオスクが有効になっているか、有効になっていない場合は対話しません。 
    - Intune での構成プロファイルの割り当てによる影響の詳細については [、「Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign)でのユーザープロファイルとデバイス プロファイルの割り当て」を参照してください。

### 展開方法の選択

キオスク構成を展開するには、次のいずれかの方法を選択できます。

- [Microsoft Intune または他のモバイル デバイス管理 (MDM) サービス](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [プロビジョニング パッケージ](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Device Portal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > この方法ではデバイスで開発者モードを有効にする必要があります。このため、デモにのみ使用することをお勧めします。

次の表に、各展開方法の機能と利点を示します。

| &nbsp; |Windows Device Portal を使用した展開 |プロビジョニング パッケージを使用して展開する |MDM を使用して展開する |
| --------------------------- | ------------- | -------------------- | ---- |
|単一アプリ キオスクを展開する   | ○           | ○                  | ○  |
|複数アプリキオスクを展開する    | なし            | ○                  | ○  |
|ローカル デバイスにのみ展開する | ○           | ○                  | なし   |
|開発者モードを使用して展開する |必須かどうか       | 任意            | 任意   |
|Azure Active Directory を使用して展開する (Azure AD)  | 任意            | 任意                   | 必須かどうか  |
|自動的に展開する      | なし            | なし                   | ○  |
|展開速度            | Fast (高速)       | Fast (高速)                 | スロー (低速) |
|規模に合った展開 | 推奨されません    | 推奨        | 推奨 |

## Microsoft Intune または他の MDM を使用して、単一アプリまたは複数アプリのキオスクをセットアップする

Microsoft Intune または別の MDM システムを使用してキオスク モードを設定するには、次の手順を実行します。

1. [デバイスを登録する準備をします](#mdmenroll)。
1. [キオスク構成プロファイルを作成します](#mdmprofile)。
1. キオスクを構成します。
   - [単一アプリキオスクの設定を構成します](#mdmconfigsingle)。
   - [複数アプリキオスクの設定を構成します](#mdmconfigmulti)。
1. [キオスク構成プロファイルをグループに割り当てる](#mdmassign)。
1. デバイスを展開します。
   - [単一アプリキオスクを展開します](#mdmsingledeploy)。
   - [複数アプリキオスクを展開します](#mdmmultideploy)。

### <a id="mdmenroll"></a>MDM、手順 1 &ndash; デバイスの登録を準備する

ユーザーが初めてサインインするときに HoloLens デバイスを自動的に登録するか、ユーザーにデバイスを手動で登録する MDM システムを構成できます。 また、デバイスを Azure AD ドメインに参加し、適切なグループに割り当てる必要があります。

デバイスを登録する方法について詳しくは [、「Mdm への HoloLens](hololens-enroll-mdm.md) の登録」と Windows デバイスの Intune 登録方法に関するページ [をご覧ください](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)。

### <a id="mdmprofile"></a>MDM、手順 2 &ndash; キオスク構成プロファイルを作成する

1. Azure Portal [を開](https://portal.azure.com/) き、Intune 管理者アカウントにサインインします。
1. **Select Microsoft Intune**Device configuration -  >  **Profiles**Create  >  **profile**.
1. プロファイル名を入力します。
1. [**プラットフォーム**Windows 10 以降] を選択し、[プロファイルの種類] の  >  ********  > **[デバイスの制限] を選択します**。
1. [**キオスクの**  >  **構成]** を選択し、次のいずれかを選択します。
   - 単一アプリのキオスクを作成するには、[**キオスク**モード] の [シングル アプリ  >  **キオスク] を選択します**。
   - 複数アプリのキオスクを作成するには、キオスク モードの複数アプリ**キオスク**  >  **を選択します**。
1. キオスクの構成を開始するには、[追加] を **選択します**。

次の手順は、必要なキオスクの種類によって異なります。 詳細については、次のいずれかのオプションを選択します。  

- [シングル アプリ キオスク](#mdmconfigsingle)
- [複数アプリ キオスク](#mdmconfigmulti)

キオスク構成プロファイルを作成する方法について詳しくは、Intune を使用して専用のキオスクとして実行する [Windows 10 と Windows Holographic for Business](https://docs.microsoft.com/intune/configuration/kiosk-settings)のデバイス設定をご覧ください。

### <a id="mdmconfigsingle"></a>MDM、手順 3 (単一アプリ) 単一アプリ キオスク &ndash;  の設定を構成する

このセクションでは、単一アプリのキオスクで必要な設定の概要を示します。 詳細については、次の記事を参照してください。

- Intune でキオスク構成プロファイルを構成する方法については [、「Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)を使用してキオスク モードを構成する方法」を参照してください。
- Intune の単一アプリ キオスクで使用可能な設定の詳細については、「シングル 全画面アプリ キオスク」 [を参照してください。](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- その他の MDM サービスについては、使用しているプロバイダーのドキュメントで手順を参照してください。 MDM サービスでキオスクをセットアップするためにカスタム XML 構成を使用する必要がある場合は、キオスク構成を定義する [XML ファイルを作成します](#ppkioskconfig)。

1. [**ユーザー ログオン] の [** ローカル ユーザー アカウント] を選択し、キオスクにサインインできるローカル (デバイス) アカウントまたは Microsoft アカウント (MSA) のユーザー名を  >  **** 入力します。
   > [!NOTE]  
   > **Windows** Holographic for Business では、自動ログのユーザー アカウントの種類はサポートされていません。
1. [**アプリケーションの種類**  >  **のストア アプリ**] を選択し、一覧からアプリを選択します。

次の手順では、 [プロファイルを](#mdmassign) グループに割り当てる必要があります。

### <a id="mdmconfigmulti"></a>MDM、手順 3 (複数アプリ) 複数アプリキオスク &ndash; の設定を構成する

このセクションでは、複数アプリのキオスクで必要な設定の概要を示します。 詳細については、次の記事を参照してください。

- Intune でキオスク構成プロファイルを構成する方法については [、「Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)を使用してキオスク モードを構成する方法」を参照してください。
- Intune の複数アプリ キオスクで利用可能な設定の詳細については、「複数アプリキオスク」 [を参照してください。](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- その他の MDM サービスについては、使用しているプロバイダーのドキュメントで手順を参照してください。 カスタム XML 構成を使用して MDM サービスでキオスクをセットアップする必要がある場合は、キオスク構成を定義する [XML ファイルを作成します](#ppkioskconfig)。 XML ファイルを使用する場合は、スタート画面のレイアウトを含 [める必要があります](#start-layout-for-hololens)。  
- 必要に応じて、Intune または他の MDM サービスでカスタムスタート画面のレイアウトを使用できます。 詳しくは [、MDM のスタート画面のレイアウト ファイル (Intune など) をご覧ください](#start-layout-file-for-mdm-intune-and-others)。

1. **Select Target Windows 10 in S mode devices**  >  **No**.  
   >[!NOTE]  
   > S モードは、Windows Holographic for Business ではサポートされていません。
1. [**ユーザー ログオンの種類**: Azure ADグループまたはユーザー ログオンタイプ  >  ********  >  **HoloLens 訪問者**] を選択し、1 つ以上のユーザー グループまたはアカウントを追加します。  

   ユーザー ログオンの種類で指定したグループまたはアカウントに属**** するユーザーだけが、キオスク エクスペリエンスを使用できます。

1. 次のオプションを使用して、1 つ以上のアプリを選択します。
   - アップロードした業務アプリを追加するには、[ストア アプリの**** 追加] を選択し、目的のアプリを選択します。
   - AUMID を指定してアプリを追加するには **、[AUMID** で追加] を選択し、アプリの AUMID を入力します。 [使用可能な AUMID の一覧を表示する](#aumids)

次の手順では、 [プロファイルを](#mdmassign) グループに割り当てる必要があります。

### <a id="mdmassign"></a>MDM、手順 4 &ndash; キオスク構成プロファイルをグループに割り当てる

キオスク構成 **プロファイルの** [割り当て] ページを使って、キオスク構成を展開する場所を設定します。 最も簡単なケースでは、デバイスが MDM に登録されているときに HoloLens デバイスを含むグループにキオスク構成プロファイルを割り当てる必要があります。

### <a id="mdmsingledeploy"></a>MDM、手順 5 (単一アプリ) &ndash; 単一アプリ キオスクの展開

MDM システムを使う場合は、OOBE 中に MDM にデバイスを登録できます。 OOBE が完了したら、デバイスへのサインインは簡単です。

OOBE 中に、次の手順を実行します。

1. キオスク構成プロファイルで指定したアカウントを使用してサインインします。
1. デバイスを登録します。 キオスク構成プロファイルが割り当てられているグループにデバイスが追加されている必要があります。
1. OOBE が完了し、ストア アプリがダウンロードおよびインストールされ、ポリシーが適用されるのを待ちます。 その後、デバイスを再起動します。

次回デバイスにサインインすると、キオスク アプリが自動的に起動します。

この時点でキオスクの構成が表示されていない場合は、割り当ての [状態を確認します](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。

### <a id="mdmmultideploy"></a>MDM、手順 5 (複数アプリ) &ndash; 複数アプリ キオスクの展開

MDM システムを使う場合は、デバイスを Azure AD テナントに参加し、OOBE 中に MDM にデバイスを登録できます。 必要に応じて、OOBE プロセス中にユーザーが利用できる登録情報をユーザーに提供します。

> [!NOTE]  
> ユーザーを含むグループにキオスク構成プロファイルを割り当てた場合は、それらのユーザー アカウントの 1 つがデバイスにサインインする最初のアカウントである必要があります。

OOBE 中に、次の手順を実行します。

1. ユーザー ログオンタイプ グループに属するアカウントを使用 **してサインイン** します。
1. デバイスを登録します。
1. キオスク構成プロファイルの一部であるアプリがダウンロードおよびインストールされるのを待ちます。 また、ポリシーが適用されるのを待ちます。  
1. OOBE が完了したら、Microsoft ストアから追加のアプリをインストールするか、サイドロードします。 [デバイスが](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) 自動的にインストールされるグループに必要なアプリ。
1. インストールが完了したら、デバイスを再起動します。

次回、ユーザー ログオンの種類に属するアカウントを使用してデバイスにサインインすると****、キオスク アプリが自動的に起動します。

この時点でキオスクの構成が表示されていない場合は、割り当ての [状態を確認します](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。

## プロビジョニング パッケージを使って単一アプリまたは複数アプリのキオスクをセットアップする

プロビジョニング パッケージを使ってキオスク モードを設定するには、次の手順を実行します。

1. [スタート画面のレイアウトを含む、キオスク](#ppkioskconfig)の構成を定義する XML ファイル [を作成します](#start-layout-for-hololens)。
2. [XML ファイルをプロビジョニング パッケージに追加します。](#ppconfigadd)
3. [HoloLens にプロビジョニング パッケージを適用します。](#ppapply)

### <a id="ppkioskconfig"></a>プロビジョニング パッケージ、手順 1 &ndash; キオスク構成 XML ファイルを作成する

一 [般的な手順に従って、Windows デスクトップ用のキオスク構成 XML ファイル](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)を作成します。ただし、次の手順は除きます。

- 従来の Windows アプリケーション (Win32) を含めない。 HoloLens では、これらのアプリケーションはサポートされていません。
- HoloLens [用のプレースホルダースタート画面](#start-layout-for-hololens) のレイアウト XML を使用します。
- オプション: キオスク構成にゲスト アクセスを追加する

#### <a id="ppkioskguest"></a>オプション: キオスク構成にゲスト アクセスを追加する

XML ファイル[**の Configs**](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)セクションでは、ゲストがキオスクを使用できるよう **、Visitor**という名前の特別なグループを構成できます。 キオスクが訪問者の特別なグループを**** サポートするように構成されている場合、サインイン ページに **"ゲスト**" オプションが追加されます。 ゲスト **アカウント** にはパスワードは必要ではなく、アカウントのサインアウト時にアカウントに関連付けられているデータは削除されます。

ゲスト アカウントを **有効にするには** 、キオスク構成 XML に次のスニペットを追加します。

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a>HoloLens のプレースホルダースタート画面のレイアウト

プロビジョニング パッケージを使 [って複数アプリ](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) キオスクを構成する場合は、スタート画面のレイアウトが必要です。 スタート画面のレイアウトのカスタマイズは、Windows Holographic for Business ではサポートされていません。 そのため、プレースホルダーのスタート画面のレイアウトを使用する必要があります。

> [!NOTE]  
> 1 つのアプリキオスクはユーザーがサインインするときにキオスク アプリを起動しますが、スタート メニューを使うのではなく、スタート画面のレイアウトを設定する必要はないので、

> [!NOTE]  
> MDM を [使って](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 複数アプリのキオスクをセットアップする場合は、必要に応じてスタート画面のレイアウトを使います。 詳しくは [、MDM 用のプレースホルダースタート画面のレイアウト ファイル (Intune など) をご覧ください](#start-layout-file-for-mdm-intune-and-others)。

スタート画面のレイアウトでは、次の **StartLayout** セクションをキオスク プロビジョニング XML ファイルに追加します。

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

#### <a id="start-layout-file-for-mdm-intune-and-others"></a>MDM 用のプレースホルダースタート画面のレイアウト ファイル (Intune など)

次のサンプルを XML ファイルとして保存します。 このファイルは、Microsoft Intune (またはキオスク プロファイルを提供する別の MDM サービス) で複数アプリキオスクを構成するときに使用できます。

> [!NOTE]
> カスタム設定と完全な XML 構成を使って MDM サービスでキオスクをセットアップする必要がある場合は、プロビジョニング パッケージのスタート画面のレイアウトの手順 [を使います](#start-layout-for-hololens)。

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

### <a id="ppconfigadd"></a>Prov. パッケージ、手順 2 &ndash; プロビジョニング パッケージにキオスク構成 XML ファイルを追加する

1. [Windows 構成デザイナーを開きます](https://www.microsoft.com/store/apps/9nblggh4tx22)。
1. [ **プロビジョニングの詳細設定] を**選択し、プロジェクトの名前を入力して、[次へ] を選択 **します**。
1. **[Windows 10 Holographic] を選択し**、[次へ] を**選択します**。
1. [完了] **を選択します**。 パッケージのワークスペースが開きます。
1. Select **Runtime settings**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**.
1. 中央のウィンドウで、[参照] **を選択** して、作成したキオスク構成 XML ファイルを見つけて選択します。

   ![Windows 構成デザイナーにおける MultiAppAssignedAccessSettings フィールドのスクリーンショット](./images/multiappassignedaccesssettings.png)

1. **省略可能**です。 (デバイスの初期セットアップ後にプロビジョニング パッケージを適用する場合、キオスク デバイスで既に利用可能な管理者ユーザーが存在する場合は、この手順を省略します)。[ **実行時の設定]** &gt; **の** &gt; **[アカウント ユーザー]** を選択し、ユーザー アカウントを作成します。 ユーザー名とパスワードを入力し **、[UserGroup**  >  **Administrators] を選択します**。  
  
     このアカウントを使用すると、プロビジョニングの状態とログを表示できます。  
1. **省略可能**です。 (キオスク デバイスに管理者以外のアカウントが既にある場合は、この手順をスキップします)。[ **実行時の設定** &gt; **] の** &gt; **[アカウント ユーザー]** を選択し、ローカル ユーザー アカウントを作成します。 構成 XML で指定するアカウントのユーザー名と同じ名前にしてください。 **[UserGroup Standard**  >  **Users] を選択します**。
1. [ファイル**の保存]**  >  **を選択します**。
1. [**プロビジョニング パッケージ**  >  **のエクスポート] を選択し**、[所有者 IT 管理者]****  >  **を選択します**。これにより、このプロビジョニング パッケージの優先順位が、他のソースからこのデバイスに適用されるプロビジョニング パッケージよりも高く設定されます。
1. **[次へ]** を選択します。
1. [プロビジョニング **パッケージのセキュリティ] ページで** 、セキュリティ オプションを選択します。
   > [!IMPORTANT]  
   > [パッケージの署名 **を有効**にする] を選択した場合は、パッケージの署名に使用する有効な証明書も選択する必要があります。 これを行うには、[参照 **]** を選択し、パッケージの署名に使用する証明書を選択します。
   
   > [!CAUTION]  
   > [パッケージの暗号化を **有効にする] は選択しません**。 HoloLens デバイスでは、この設定によってプロビジョニングが失敗します。
1. **[次へ]** を選択します。
1. プロビジョニング パッケージのビルド時の出力場所を指定します。 既定では、Windows 構成デザイナーはプロジェクト フォルダーを出力先として使います。 出力場所を変更する場合は、[参照] を選択 **します**。 完了したら、[次へ] を選択 **します**。
1. [ **ビルド] を** 選択してパッケージのビルドを開始します。 プロビジョニング パッケージのビルドにはそれほど時間はかかりません。 ビルド ページにはプロジェクト情報が表示され、進行状況バーはビルドの状態を示します。

### <a id="ppapply"></a>プロビジョニング パッケージ、手順 3 &ndash; プロビジョニング パッケージを HoloLens に適用する

「プロビジョニング パッケージを使用して HoloLens を構成する」の記事では、次の状況でプロビジョニング パッケージを適用する詳細な手順を示します。

- セットアップ中に [、最初にプロビジョニング パッケージを HoloLens に適用できます](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。

- セットアップ後 [に HoloLens にプロビジョニング パッケージを適用できます](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)。

## Windows Device Portal を使ってシングル アプリ キオスクをセットアップする

Windows Device Portal を使ってキオスク モードを設定するには、次の手順を実行します。

1. [Windows Device Portal を使う HoloLens デバイスをセットアップします](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)。 デバイス ポータルは、お使いの PC に Web ブラウザーから接続することができる HoloLens 上の Web サーバーです。

    > [!CAUTION]
    > Device Portal を使う HoloLens をセットアップする場合は、デバイスで開発者モードを有効にする必要があります。 Windows Holographic for Business を備えるデバイスの開発者モードでは、アプリをサイドロードできます。 ただし、この設定により、Microsoft Store で認定されていないアプリをユーザーがインストールできるリスクが生じ、 管理者は、ポリシー CSP の **ApplicationManagement/AllowDeveloper Unlock** 設定を使用して、開発者モードを有効にする機能を [ブロックできます](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)。 [開発者モードの詳細をご覧ください。](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. コンピューターで [、Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) または USB を使って HoloLens に接続 [します](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)。

1. 次のいずれかの操作を行います。
   - Windows Device Portal に初めて接続する場合は、ユーザー [名とパスワードを作成します。](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - 以前に設定したユーザー名とパスワードを入力します。

    > [!TIP]
    > ブラウザーに証明書エラーが表示された場合は、[こちらのトラブルシューティング手順](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)に従います。

1. Windows Device Portal で、[キオスク モード] **を選択します**。

1. [ **キオスク モードを有効**にする] を選択し、デバイスの起動時に実行するアプリを選択して、[保存] を **選択します**。

    ![Kiosk Mode (キオスク モード)](images/kiosk.png)
1. HoloLens を再起動します。 引き続き Device Portal ページを開いている場合は、ページの **上部にある** [再起動] を選択できます。

> [!NOTE]
> キオスク モードは、1 つの必須クエリ文字列パラメーター (値が "true" または "false" の "kioskModeEnabled") と 1 つのオプション パラメーター (パッケージ名の値を持つ "startupApp") を使用して、/api/holographic/kioskmode/settings への POST を実行することで、Device Portal の REST API を介して設定できます。 Device Portal は開発者のみを対象とし、開発者以外のデバイスでは有効にしない必要があります。 REST API は、今後の更新/リリースで変更される可能性があります。

## 詳細情報

### プロビジョニング パッケージを使ってキオスクを構成する方法をご確認ください。  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### グローバル割り当てアクセス – キオスク モード
- システム レベルでキオスク モードを適用する新しいキオスク方式を有効にすることで、キオスクの ID 管理が削減されます。

この新機能により、IT 管理者は HoloLens 2 デバイスを複数のアプリ キオスク モード用に構成できます。これはシステム レベルで適用可能で、システム上の ID とのアフィニティは持たず、デバイスにサインインするユーザー全員に適用されます。 この新機能の詳細については、こちらを参照 [してください](hololens-global-assigned-access-kiosk.md)。

### 複数アプリキオスク モードでのアプリケーションの自動起動 
- アプリの自動起動に重点を置いてエクスペリエンスを提供し、キオスク モードエクスペリエンス用に選択された UI とアプリの選択をさらに増やします。

複数アプリのキオスク モードにのみ適用され、割り当てられたアクセスの構成で以下の強調表示された属性を使って自動起動を指定できるアプリは 1 つのみです。 

ユーザーがサインインすると、アプリケーションが自動的に起動します。 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### 失敗の処理に関するキオスク モードの動作の変更
- キオスク モードのエラーで利用可能なアプリを排除することで、より安全なキオスク モード。 

以前は、キオスク モードの適用でエラーが発生した場合、HoloLens はスタート メニューにすべてのアプリケーションを表示するために使用しました。 Windows Holographic Version 20H2 では、エラーが発生した場合、スタート メニューに以下のようにアプリは表示されません。 

![失敗したときのキオスク モードの画像。](images/hololens-kiosk-failure-behavior.png )

### オフライン キオスクAD Azure およびグループ メンバーシップをキャッシュする
- 最大 60 日間、Azure ADでオフライン キオスクを使用できます。

このポリシーは、Azure AD グループ メンバーシップ キャッシュを、サインインしているユーザーの Azure AD グループをターゲットとする割り当てられたアクセス構成に使用できる日数を制御します。 このポリシー値を 0 より大きい値に設定すると、それ以外の場合はキャッシュが使用されません。  

名前: AADGroupMembershipCacheValidityInDays URI 値: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最小 - 0 日  
最大 - 60 日 

このポリシーを正しく使用する手順は次のとおりです。 
1. Azure AD グループをターゲットとするキオスクのデバイス構成プロファイルを作成し、HoloLens デバイスに割り当てる。 
1. このポリシー値を希望する日数 (> 0) に設定し、HoloLens デバイスに割り当てるカスタム OMA URI ベースのデバイス構成を作成します。 
    1. URI 値は、OMA-URI テキスト ボックスに ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays として入力する必要があります。
    1. 値は、最小/最大許容値の間で指定できます。
1. HoloLens デバイスを登録し、両方の構成がデバイスに適用されるのを確認します。 
1. インターネットが利用可能AD Azure ユーザー 1 のサインインを許可し、ユーザーのサインインと Azure AD グループ メンバーシップが正常に確認されると、キャッシュが作成されます。 
1. Azure ADユーザー 1 は HoloLens をオフラインにし、ポリシー値で X 日数が許可されている限りキオスク モードで使用できます。 
1. 他の Azure AD ユーザー N に対して手順 4 と 5 を繰り返し実行できます。ここでの重要なポイントは、すべての Azure AD ユーザーがインターネットを使用してデバイスにサインインする必要がある点です。少なくとも 1 回は、キオスク構成の対象となる Azure AD グループのメンバーと判断できます。 
 
> [!NOTE]
> Azure アプリケーションに対して手順 4 が実行されるまでAD"切断された" 環境で説明されているエラー動作が発生します。 


## HoloLens の XML キオスク コード サンプル

### Azure ユーザー グループをターゲットとする複数ADキオスク モード。 
このキオスクは、Azure AD グループのユーザーに対して、設定、リモート アシスト、フィードバック Hub の 3 つのアプリを含むキオスクを有効にしたキオスクを展開します。 このサンプルをすぐに使用するように変更するには、自分の Azure AD グループに一致するように、以下で強調表示されている GUID を変更してください。 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### Azure ADアカウントをターゲットとする複数のアプリ キオスク モード。
このキオスクは 1 人のユーザーにキオスクを展開し、設定、リモート アシスト、フィードバック Hub の 3 つのアプリを含むキオスクを有効にします。 このサンプルをすぐに使用するように変更するには、以下で強調表示されているアカウントを、Azure AD アカウントに一致するように変更してください。 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

