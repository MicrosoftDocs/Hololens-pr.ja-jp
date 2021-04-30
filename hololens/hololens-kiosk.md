---
title: HoloLens をキオスクとしてセットアップする
description: アプリを HoloLens デバイスでロックダウンするためにキオスク構成を設定して使用する方法について説明します。
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
ms.openlocfilehash: a043b2f96bec6127d52622b4662279c777df6f8f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309571"
---
# <a name="set-up-hololens-as-a-kiosk"></a>HoloLens をキオスクとしてセットアップする

デバイスをキオスクモードで実行するように構成することで、HoloLens デバイスを固定用途のデバイス ( *キオスク* ともいいます) として機能するように構成できます。 キオスクモードでは、デバイスで使用できるアプリケーション (またはユーザー) が制限されます。 キオスクモードは、HoloLens デバイスをビジネスアプリに専用にする場合や、アプリのデモで HoloLens デバイスを使用する場合に使用できる便利な機能です。

この記事では、HoloLens デバイスに固有のキオスク構成の側面について説明します。 さまざまな種類の Windows ベースキオスクとその構成方法に関する一般的な情報については、「 [windows デスクトップエディションでキオスクとデジタルサインを構成](https://docs.microsoft.com/windows/configuration/kiosk-methods)する」を参照してください。  

> [!IMPORTANT]  
> キオスクモードでは、ユーザーがデバイスにサインインしたときに利用できるアプリを決定します。 ただし、キオスクモードはセキュリティメソッドではありません。 許可されていない別のアプリを開くことが許可されていないアプリを停止することはありません。 アプリまたはプロセスを開けないようにするには、 [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) を使用して適切なポリシーを作成します。
>
> HoloLens 2 が使用する高度なレベルのセキュリティをユーザーに提供する Microsoft サービスの詳細については、「 [状態の分離と分離-Defender の保護](security-state-separation-isolation.md#defender-protections)」を参照してください。 または、 [WDAC および Windows PowerShell を使用して、Microsoft Intune で HoloLens 2 デバイス上のアプリを許可またはブロック](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)する方法についても説明します。

キオスクモードは、シングルアプリ構成またはマルチアプリ構成のいずれかで使用できます。また、3つのプロセスのいずれかを使用して、キオスク構成を設定し、展開することができます。

> [!IMPORTANT]  
> マルチアプリ構成を削除すると、割り当てられたアクセス機能によって作成されたユーザーロックダウンプロファイルが削除されます。 ただし、ポリシーの変更はすべて元に戻されるわけではありません。 これらのポリシーを元に戻すには、デバイスを工場出荷時の設定にリセットする必要があります。

## <a name="plan-the-kiosk-deployment"></a>キオスク展開を計画する

キオスクを計画するときは、次の質問に答えることができる必要があります。 ここでは、このページの説明と、これらの質問に関する考慮事項について説明します。
1. **誰がキオスクを使用するか、どのような [種類のアカウント](hololens-identity.md) を使用しますか?** これは、既に作成されている可能性があり、キオスクのために調整することはできませんが、後でキオスクを割り当てる方法に影響します。
1. **ユーザー/グループごとに異なるキオスクを使用する必要がありますか、それともキオスクが有効になっていないかどうかを確認してください。** その場合は、XML を使用してキオスクを作成します。 
1. **キオスクに含まれるアプリの数を確認できます。** アプリが1つ以上ある場合は、マルチアプリキオスクが必要になります。 
1. **どのアプリがキオスクに配置されますか?** 以下の AUMIDs の一覧を使用して、独自のアプリに加えて In-Box アプリを追加してください。
1. **キオスクの展開を計画するにはどうすればよいですか。** MDM にデバイスを登録する場合は、MDM を使用してキオスクをデプロイすることをお勧めします。 MDM を使用していない場合は、プロビジョニングパッケージを使用したデプロイが可能です。  

### <a name="kiosk-mode-requirements"></a>キオスクモードの要件

任意の HoloLens 2 デバイスでキオスクモードを使用するように構成できます。

> [!IMPORTANT]
> キオスクモードは、デバイスに Windows Holographic for Business がある場合にのみ使用できます。 すべての HoloLens 2 デバイスは Windows Holographic for Business に付属しており、他のエディションはありません。 すべての HoloLens 2 デバイスは、そのままでキオスクモードを実行できます。
>
> HoloLens (第1世代) デバイスは、OS ビルドと OS エディションの両方でアップグレードする必要があります。 HoloLens (第1世代) を [Windows Holographic For Business](hololens1-upgrade-enterprise.md) edition に更新する方法については、こちらを参照してください。 HoloLens (第1世代) デバイスでキオスクモードを使用するように更新するには、まず、デバイスで Windows 10 バージョン1803以降のバージョンが実行されていることを確認する必要があります。 Windows デバイス回復ツールを使用して HoloLens (第1世代) デバイスを既定のビルドに回復した場合、または最新の更新プログラムをインストールした場合は、デバイスを構成する準備ができています。

> [!IMPORTANT]  
> キオスクモードで実行されているデバイスを保護するには、USB 接続などの機能を無効にするデバイス管理ポリシーを追加することを検討してください。 また、更新プログラムのリングの設定を確認して、営業時間中に自動更新が実行されないことを確認してください。

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>シングルアプリキオスクとマルチアプリキオスクのどちらかを決定する

シングルアプリキオスクは、ユーザーがデバイスにサインインすると、指定されたアプリを開始します。 Cortana と同様に、[スタート] メニューは無効になっています。 HoloLens 2 デバイスは、 [開始](hololens2-basic-usage.md#start-gesture) ジェスチャに応答しません。 HoloLens (第1世代) デバイスは、 [ブルーム](hololens1-basic-usage.md) ジェスチャに応答しません。 実行できるアプリは1つだけなので、ユーザーは他のアプリを配置することはできません。

マルチアプリキオスクでは、ユーザーがデバイスにサインインすると [スタート] メニューが表示されます。 キオスクの構成によって、[スタート] メニューで使用できるアプリが決まります。 マルチアプリキオスクを使用すると、ユーザーが使用する必要があるものだけを提示し、使用する必要がないものを削除することで、ユーザーにわかりやすいエクスペリエンスを提供できます。

次の表に、各種キオスクモードの機能の一覧を示します。

| &nbsp; |[スタート] メニュー |クイックアクションメニュー |カメラとビデオ |Miracast |Cortana |組み込みの音声コマンド |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|シングルアプリキオスク |無効 |無効   |無効 |無効   |無効 |有効化<sup>1</sup> |
|マルチ アプリ キオスク |Enabled |有効<sup>2</sup> |利用可能<sup>2</sup> |利用可能<sup>2</sup> |使用可能<sup>2、3</sup>  |有効化<sup>1</sup> |

> <sup>1</sup> 無効になっている機能に関連する音声コマンドは機能しません。  
> <sup>2</sup> これらの機能を構成する方法の詳細については、「 [キオスクアプリを選択](#plan-kiosk-apps)する」を参照してください。  
> <sup>3</sup> Cortana が無効になっている場合でも、組み込みの音声コマンドが有効になります。

次の表は、さまざまなキオスクモードのユーザーサポート機能を示しています。

| &nbsp; |サポートされているユーザーの種類 | 自動サインイン | 複数のアクセスレベル |
| --- | --- | --- | --- |
|シングルアプリキオスク |Azure Active Directory (Azure AD) またはローカルアカウントの管理されたサービスアカウント (MSA) |はい |いいえ |
|マルチ アプリ キオスク |Azure AD アカウント |いいえ |はい |

これらの機能を使用する方法の例については、次の表を参照してください。

|次の場合にシングルアプリキオスクを使用します。 |次の場合にマルチアプリキオスクを使用します。 |
| --- | --- |
|新しい従業員向けの Dynamics 365 ガイドのみを実行するデバイス。 |さまざまな従業員について、ガイドとリモートアシスタンスの両方を実行するデバイス。 |
|カスタムアプリのみを実行するデバイス。 |(カスタムアプリのみを実行する) ほとんどのユーザーのキオスクとして機能するが、特定のユーザーグループの標準デバイスとして機能するデバイス。 |

### <a name="plan-kiosk-apps"></a>キオスクアプリを計画する

キオスクアプリを選択する方法に関する一般的な情報については、「 [割り当てられたアクセス用のアプリを選択するためのガイドライン (キオスクモード)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)」を参照してください。

Windows デバイスポータルを使用してシングルアプリキオスクを構成する場合は、セットアッププロセス中にアプリを選択します。  

モバイルデバイス管理 (MDM) システムまたはプロビジョニングパッケージを使用してキオスクモードを構成する場合は、 [AssignedAccess 構成サービスプロバイダー (CSP)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) を使用してアプリケーションを指定します。 CSP は、 [アプリケーションユーザーモデル id (AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) を使用してアプリケーションを識別します。 次の表に、マルチアプリキオスクで使用できるいくつかのインボックスアプリケーションの AUMIDs を示します。

> [!IMPORTANT]
> キオスクモードでは、ユーザーがデバイスにサインインしたときに利用できるアプリを決定します。 ただし、キオスクモードはセキュリティメソッドではありません。 許可されていない別のアプリを開くことが許可されていないアプリを停止することはありません。 この動作を制限しないため、アプリは Edge、ファイルエクスプローラー、および Microsoft Store アプリから起動できます。 キオスクから起動したくない特定のアプリがある場合は、 [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) を使用して適切なポリシーを作成します。 
> 
> また、Mixed Reality ホームをキオスクアプリとして設定することはできません。

<a id="aumids"></a>

|アプリ名 |AUMID |
| --- | --- |
|3D ビューアー |Microsoft3DViewer \_ 8Wekyb3d8bbwe \! Microsoft3DViewer |
|Calendar |windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft. live |
|カメラ<sup>1、2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft 549981C3F5F10 \_ 8wekyb3d8bbwe \! アプリ |
|HoloLens のデバイスピッカー (第1世代) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|HoloLens 2 のデバイスピッカー |DevicesFlowHost \_ cw5n1h2txyewy \! . DevicesFlowHost. |
|Dynamics 365 Guides |Dynamics365 \_ 8wekyb3d8bbwe の \! ガイド |
|Dynamics 365 Remote Assist |Microsoft office Remoteassist \_ 8wekyb3d8bbwe \! Microsoft. remoteassist |
|フィードバック &nbsp; ハブ |Microsoft Windowsフィード Backhub \_ 8wekyb3d8bbwe \! アプリ |
|エクスプローラー |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe! live |
|Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast<sup>4</sup> |&nbsp; |
|映画 & テレビ |Microsoft ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft ZuneVideo |
|OneDrive |microsoft office skydrive \_ 8wekyb3d8bbwe \! アプリ |
|Photos |\_8wekyb3d8bbwe アプリ (Microsoft) \! |
|設定 |HolographicSystemSettings \_ cw5n1h2txyewy \! アプリ |
|ヒント |HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> 写真またはビデオのキャプチャを有効にするには、キオスクアプリとしてカメラアプリを有効にする必要があります。  
> <sup>2</sup> カメラアプリを有効にするときは、次の条件に注意してください。
> - [クイックアクション] メニューには、[写真] ボタンと [ビデオ] ボタンがあります。  
> - また、画像を操作したり、画像を取得したりできるアプリ (写真、メール、OneDrive など) を有効にする必要もあります。  
>  
> <sup>3</sup> キオスクアプリとして Cortana を有効にしない場合でも、組み込みの音声コマンドが有効になります。 ただし、無効になっている機能に関連するコマンドには影響しません。  
> <sup>4</sup> Miracast を直接有効にすることはできません。 キオスクアプリとして Miracast を有効にするには、カメラアプリとデバイスピッカーアプリを有効にします。

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>ユーザーまたはグループのキオスクプロファイルを計画する

Xml ファイルを作成する場合、または Intune の UI を使用してキオスクを設定する場合は、どのユーザーがキオスクを使用するかを検討する必要があります。 キオスク構成は、個々のアカウントまたは Azure AD グループに制限することができます。 

通常、キオスクはユーザーまたはユーザーグループに対して有効になっています。 ただし、独自の XML キオスクの作成を計画している場合は、グローバルに割り当てられたアクセスを考慮することをお勧めします。この場合、キオスクは Id に関係なくデバイスレベルで適用されます。 この appeals に [ついては、「グローバルに割り当てられたアクセスキオスク」を参照してください。](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>XML ファイルを作成する場合は、次の手順を実行します。
-   複数のキオスクプロファイルを作成し、それぞれを異なるユーザー/グループに割り当てることができます。 たとえば、多くのアプリを持つ Azure AD グループのキオスクや、単一のアプリを持つ複数のアプリキオスクを持つビジターなどです。
-   キオスク構成は **プロファイル Id** と呼ばれ、GUID があります。
-   このプロファイルは、ユーザーの種類を指定し、 **Defaultprofile Id** に同じ GUID を使用して、構成セクションに割り当てます。
- XML ファイルは作成できますが、カスタム OMA-URI デバイス構成プロファイルを作成し、URI 値を使用して HoloLens デバイスグループに適用することで、MDM 経由でデバイスに適用できます。/Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Intune でキオスクを作成する場合。
-   各デバイスは、1つのキオスクプロファイルのみを受け取ることができます。それ以外の場合は、競合を作成し、キオスク構成を受信しません。 
    -   キオスク構成プロファイルに関連付けられていないデバイス制限など、その他の種類のプロファイルやポリシーは、キオスク構成プロファイルと競合しません。
-   キオスクは、ユーザーログオンの種類の一部であるすべてのユーザーに対して有効になります。これは、ユーザーまたは Azure AD グループで設定されます。 
-   キオスク構成を設定し、ユーザーの **ログオンの種類** (キオスクにログインできるユーザー) とアプリを選択した後、デバイスの構成をグループに割り当てる必要があります。 割り当てられたグループによって、どのデバイスがキオスクデバイスの構成を受け取るかが決定されますが、キオスクが有効になっているかどうかはと対話しません。 
    - Intune での構成プロファイルの割り当ての影響の詳細については、「 [Microsoft Intune でユーザーとデバイスのプロファイルを割り当てる](https://docs.microsoft.com/intune/configuration/device-profile-assign)」を参照してください。

### <a name="select-a-deployment-method"></a>展開方法の選択

キオスク構成を展開するには、次のいずれかの方法を選択します。

- [Microsoft Intune またはその他のモバイルデバイス管理 (MDM) サービス](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [プロビジョニング パッケージ](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows デバイス ポータル](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > この方法では、デバイスで開発者モードを有効にする必要があるため、デモにのみ使用することをお勧めします。

次の表に、各展開方法の機能と利点を示します。

| &nbsp; |Windows デバイスポータルを使用して展開する |プロビジョニングパッケージを使用して展開する |MDM を使用したデプロイ |
| --------------------------- | ------------- | -------------------- | ---- |
|シングルアプリキオスクのデプロイ   | はい           | はい                  | はい  |
|複数アプリキオスクのデプロイ    | いいえ            | はい                  | はい  |
|ローカルデバイスのみに展開する | はい           | はい                  | いいえ   |
|開発者モードを使用した配置 |必須       | 必要なし            | 必要なし   |
|Azure Active Directory を使用したデプロイ (Azure AD)  | 必要なし            | 必要なし                   | 必須  |
|自動的に配置する      | いいえ            | いいえ                   | はい  |
|展開の速度            | Fast       | 高速                 | 低速 |
|大規模にデプロイする | 推奨されません    | 推奨        | 推奨 |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Microsoft Intune またはその他の MDM を使用して、シングルアプリまたはマルチアプリのキオスクを設定する

Microsoft Intune または別の MDM システムを使用してキオスクモードを設定するには、次の手順に従います。

1. [デバイスを登録する準備を](#mdmenroll)します。
1. [キオスク構成プロファイルを作成](#mdmprofile)します。
1. キオスクを構成します。
   - [シングルアプリキオスクの設定を構成し](#mdmconfigsingle)ます。
   - [マルチアプリキオスクの設定を構成し](#mdmconfigmulti)ます。
1. [キオスク構成プロファイルをグループに割り当て](#mdmassign)ます。
1. デバイスを展開します。
   - [シングルアプリキオスクをデプロイ](#mdmsingledeploy)します。
   - [マルチアプリキオスクをデプロイ](#mdmmultideploy)します。

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM、手順 1 &ndash; デバイスの登録の準備

ユーザーが初めてサインインするとき、またはユーザーが手動でデバイスを登録するときに、HoloLens デバイスを自動的に登録するように MDM システムを構成できます。 また、デバイスは Azure AD ドメインに参加し、適切なグループに割り当てられている必要があります。

デバイスを登録する方法の詳細については、「 [Windows デバイスの MDM および Intune の登録方法](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)[に HoloLens を登録](hololens-enroll-mdm.md)する」を参照してください。

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM、手順 2 &ndash; キオスク構成プロファイルの作成

1. [Azure](https://portal.azure.com/) portal を開き、Intune 管理者アカウントにサインインします。
1. **Microsoft Intune**  >  **デバイスの構成-プロファイルの**  >  **作成プロファイル**] を選択します。
1. プロファイル名を入力してください。
1. [**プラットフォーム**] [  >  **Windows 10 以降**] の順に選択し、[**プロファイルの種類**] [デバイスの制限] を選択し  > ます。
1. [ **Configure**  >  **キオスク**] を選択し、次のいずれかを選択します。
   - シングルアプリキオスクを作成するには、[**キオスクモード**  >  **シングルアプリキオスク**] を選択します。
   - マルチアプリキオスクを作成するには、[**キオスクモード**  >  **マルチアプリキオスク**] を選択します。
1. キオスクの構成を開始するには、[ **追加**] を選択します。

次の手順は、必要なキオスクの種類によって異なります。 詳細については、次のいずれかのオプションを選択してください。  

- [シングルアプリキオスク](#mdmconfigsingle)
- [マルチ アプリ キオスク](#mdmconfigmulti)

キオスク構成プロファイルを作成する方法の詳細については、「 [windows 10 および Windows Holographic For Business デバイス設定を Intune を使用して専用キオスクとして実行する](https://docs.microsoft.com/intune/configuration/kiosk-settings)」を参照してください。

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM、ステップ 3 (単一アプリ) &ndash;  シングルアプリキオスクの設定を構成する

このセクションでは、シングルアプリキオスクで必要な設定の概要を示します。 詳細については、次の記事を参照してください。

- Intune でキオスク構成プロファイルを構成する方法の詳細については、「 [Microsoft Intune を使用してキオスクモードを構成する方法](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)」を参照してください。
- Intune でのシングルアプリキオスクに使用できる設定の詳細については、「[シングルスクリーンアプリキオスク](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)」を参照してください。
- その他の MDM サービスについては、プロバイダーのドキュメントで手順を確認してください。 カスタム XML 構成を使用して、MDM サービスでキオスクを設定する必要がある場合は、 [キオスク構成を定義する xml ファイルを作成](#ppkioskconfig)します。

1. [**ユーザーログオンの種類**] [  >  **ローカルユーザーアカウント**] を選択し、キオスクにサインインできるローカル (デバイス) アカウントまたは Microsoft アカウント (MSA) のユーザー名を入力します。
   > [!NOTE]  
   > **[自動ログオン]** というユーザー アカウントの種類は、Windows Holographic for Business ではサポートされていません。
1. [**アプリケーションの種類** ストアアプリ] を選択し、  >  一覧からアプリを選択します。

次の手順では、プロファイルをグループに [割り当て](#mdmassign) ます。

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM、ステップ 3 (マルチアプリ) &ndash; マルチアプリキオスクの設定を構成する

このセクションでは、マルチアプリキオスクで必要な設定の概要を示します。 詳細については、次の各記事を参照してください。

- Intune でキオスク構成プロファイルを構成する方法の詳細については、「 [Microsoft Intune を使用してキオスクモードを構成する方法](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)」を参照してください。
- Intune のマルチアプリキオスクで使用可能な設定の詳細については、「[マルチアプリキオスク](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)」を参照してください。
- その他の MDM サービスについては、プロバイダーのドキュメントで手順を確認してください。 カスタム XML 構成を使用して、MDM サービスでキオスクを設定する必要がある場合は、 [キオスク構成を定義する xml ファイルを作成](#ppkioskconfig)します。 XML ファイルを使用する場合は、必ず [開始レイアウト](#start-layout-for-hololens)を含めてください。  
- 必要に応じて、Intune またはその他の MDM サービスでカスタムのスタートレイアウトを使用することもできます。 詳細については、「 [MDM のレイアウトファイルの開始 (Intune など)](#start-layout-file-for-mdm-intune-and-others)」を参照してください。

1. [ **S モードデバイス] の [ターゲット Windows 10**] を選択し  >  ます。  
   >[!NOTE]  
   > S モードは、Windows Holographic for Business ではサポートされていません。
1. [ユーザー **ログオンの種類**] を選択し、[ユーザー] または [グループ] または [  >  **ユーザーログオンの種類**]**Azure AD** [  >  **HoloLens ビジター**] を選択し、1つ以上のユーザーグループまたはアカウントを追加します。  

   **ユーザーのログオンの種類** で指定したグループまたはアカウントに属しているユーザーのみがキオスクエクスペリエンスを使用できます。

1. 次のオプションを使用して、1つまたは複数のアプリを選択します。
   - アップロードした基幹業務アプリを追加するには、[ **ストアアプリの追加** ] を選択し、目的のアプリを選択します。
   - AUMID を指定してアプリを追加するには、[ **AUMID で追加** ] を選択し、アプリの AUMID を入力します。 [使用可能な AUMIDs の一覧を参照してください。](#aumids)

次の手順では、プロファイルをグループに [割り当て](#mdmassign) ます。

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM、手順 4. &ndash; キオスク構成プロファイルをグループに割り当てる

キオスク構成プロファイルの [ **割り当て** ] ページを使用して、キオスク構成を展開する場所を設定します。 最も単純なケースでは、デバイスが MDM に登録されるときに、HoloLens デバイスを含むグループにキオスク構成プロファイルを割り当てます。

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM、手順 5 (シングルアプリ) に &ndash; よるシングルアプリキオスクのデプロイ

MDM システムを使用する場合は、OOBE 中にデバイスを MDM に登録できます。 OOBE の完了後、デバイスへのサインインは簡単です。

OOBE 中に、次の手順を実行します。

1. キオスク構成プロファイルで指定したアカウントを使用してサインインします。
1. デバイスを登録します。 キオスク構成プロファイルが割り当てられているグループにデバイスが追加されていることを確認します。
1. OOBE が終了するまで待ってから、ストアアプリをダウンロードしてインストールし、ポリシーを適用します。 その後、デバイスを再起動します。

次回デバイスにサインインすると、キオスクアプリが自動的に起動します。

この時点でキオスクの構成が表示されない場合は、 [割り当ての状態を確認](https://docs.microsoft.com/intune/configuration/device-profile-monitor)してください。

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM、手順 5 (マルチアプリ) に &ndash; よるマルチアプリキオスクのデプロイ

MDM システムを使用する場合、デバイスを Azure AD テナントに参加させ、OOBE 中にデバイスを MDM に登録できます。 必要に応じて、OOBE プロセス中に使用できるように、登録情報をユーザーに提供します。

> [!NOTE]  
> キオスク構成プロファイルをユーザーが含まれているグループに割り当てた場合は、これらのユーザーアカウントのいずれかが、デバイスにサインインするための最初のアカウントであることを確認してください。

OOBE 中に、次の手順を実行します。

1. **ユーザーログオンの種類** のグループに属するアカウントを使用してサインインします。
1. デバイスを登録します。
1. キオスク構成プロファイルに含まれるすべてのアプリがダウンロードされ、インストールされるまで待ちます。 また、ポリシーが適用されるまで待機します。  
1. OOBE が終了したら、Microsoft ストアまたはサイドローディングから追加のアプリをインストールできます。 デバイスが属しているグループに[必要なアプリ](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)が自動的にインストールされます。
1. インストールが完了したら、デバイスを再起動します。

次に **ユーザーログオンの種類** に属するアカウントを使用してデバイスにサインインすると、キオスクアプリが自動的に起動します。

この時点でキオスクの構成が表示されない場合は、 [割り当ての状態を確認](https://docs.microsoft.com/intune/configuration/device-profile-monitor)してください。

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>プロビジョニングパッケージを使用してシングルアプリまたはマルチアプリキオスクを設定する

プロビジョニングパッケージを使用してキオスクモードを設定するには、次の手順に従います。

1. [キオスク構成を定義する XML ファイルを作成します。](#ppkioskconfig)これには、 [スタートレイアウト](#start-layout-for-hololens)も含まれます。
2. [プロビジョニングパッケージに XML ファイルを追加します。](#ppconfigadd)
3. [HoloLens にプロビジョニングパッケージを適用します。](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>プロビジョニングパッケージ、手順 1 &ndash; キオスク構成 XML ファイルを作成する

次の場合を除き、一般的な手順に従って、 [Windows デスクトップ用のキオスク構成 XML ファイルを作成](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)します。

- 従来の Windows アプリケーション (Win32) を含めないでください。 HoloLens は、これらのアプリケーションをサポートしていません。
- 「HoloLens の [スタートレイアウト XML](#start-layout-for-hololens) 」を使用します。
- オプション: キオスク構成にゲストアクセスを追加する

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>オプション: キオスク構成にゲストアクセスを追加する

[  XML ファイルの構成セクション](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)では、ゲストがキオスクを使用できるように、**ビジター** という名前の特別なグループを構成できます。 **訪問** 者の特別なグループをサポートするようにキオスクが構成されている場合、サインインページに "**ゲスト**" オプションが追加されます。 **Guest** アカウントにはパスワードは必要ありません。アカウントに関連付けられているデータは、アカウントのサインアウト時に削除されます。

**ゲスト** アカウントを有効にするには、次のスニペットをキオスク構成 XML に追加します。

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>HoloLens のプレースホルダー開始レイアウト

[プロビジョニングパッケージ](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)を使用してマルチアプリキオスクを構成する場合、この手順にはスタートレイアウトが必要です。 Windows Holographic for Business では、レイアウトのカスタマイズはサポートされていません。 そのため、プレースホルダーのスタートレイアウトを使用する必要があります。

> [!NOTE]  
> シングルアプリキオスクは、ユーザーがサインインしたときにキオスクアプリを開始するため、スタートメニューを使用せず、スタートレイアウトを設定する必要もありません。

> [!NOTE]  
> [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)を使用してマルチアプリキオスクを設定する場合は、必要に応じて、スタートレイアウトを使用することもできます。 詳細については、「 [MDM のプレースホルダー開始レイアウトファイル (Intune など)](#start-layout-file-for-mdm-intune-and-others)」を参照してください。

スタート画面のレイアウトでは、次の **startlayout** セクションをキオスクプロビジョニング XML ファイルに追加します。

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

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>MDM (Intune など) のプレースホルダー開始レイアウトファイル

次のサンプルを XML ファイルとして保存します。 このファイルは、Microsoft Intune (またはキオスクプロファイルを提供する別の MDM サービス) でマルチアプリキオスクを構成するときに使用できます。

> [!NOTE]
> カスタム設定と完全な XML 構成を使用して、MDM サービスでキオスクを設定する必要がある場合は、 [プロビジョニングパッケージの [レイアウトの開始] 手順](#start-layout-for-hololens)を使用します。

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

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Prov. パッケージ、手順 2. &ndash; キオスク構成 XML ファイルをプロビジョニングパッケージに追加する

1. [Windows 構成デザイナー](https://www.microsoft.com/store/apps/9nblggh4tx22)を開きます。
1. [ **高度なプロビジョニング**] を選択し、プロジェクトの名前を入力して、[ **次へ**] を選択します。
1. [ **Windows 10 Holographic**] を選択し、[ **次へ**] を選択します。
1. **[完了]** を選択します。 パッケージのワークスペースが開きます。
1. [**ランタイム設定**  >  **AssignedAccess** MultiAppAssignedAccessSettings] を選択し  >  ます。
1. 中央のウィンドウで、[ **参照** ] を選択して、作成したキオスク構成 XML ファイルを見つけて選択します。

   ![Windows 構成デザイナーにおける MultiAppAssignedAccessSettings フィールドのスクリーンショット](./images/multiappassignedaccesssettings.png)

1. **オプション**。 (デバイスの初期セットアップ後にプロビジョニングパッケージを適用する場合、キオスクデバイスで既に利用可能な管理者ユーザーが存在する場合は、この手順をスキップしてください)。[**ランタイム設定**] [アカウント] [ &gt;  &gt; **ユーザー**] の順に選択し、ユーザーアカウントを作成します。 ユーザー名とパスワードを入力し、[ **UserGroup** Administrators] を選択し  >  ます。  
  
     このアカウントを使用して、プロビジョニングの状態とログを表示できます。  
1. **オプション**。 (キオスクデバイスで管理者以外のアカウントを既に持っている場合は、この手順をスキップしてください)。[**ランタイム設定**] [アカウント] [ &gt;  &gt; **ユーザー**] の順に選択し、ローカルユーザーアカウントを作成します。 ユーザー名が、構成 XML で指定したアカウントと同じであることを確認します。 [ **UserGroup**  >  **Standard Users**] を選択します。
1. **[ファイル]**  >  **[保存]** を選びます。
1. [   >  **プロビジョニングパッケージ** のエクスポート] を選択し、[  >  **IT 管理** 者] を選択します。これにより、このプロビジョニングパッケージの優先順位は、他のソースからこのデバイスに適用されるパッケージのプロビジョニングよりも高くなります。
1. **[次へ]** を選択します。
1. [ **プロビジョニングパッケージのセキュリティ** ] ページで、セキュリティオプションを選択します。
   > [!IMPORTANT]  
   > [ **パッケージ署名を有効** にする] を選択した場合は、パッケージの署名に使用する有効な証明書も選択する必要があります。 これを行うには、[ **参照** ] を選択し、パッケージの署名に使用する証明書を選択します。
   
   > [!CAUTION]  
   > [パッケージの **暗号化を有効にする**] を選択しないでください。 HoloLens デバイスでは、この設定によってプロビジョニングが失敗します。
1. **[次へ]** を選択します。
1. プロビジョニングパッケージを構築するときに使用する出力場所を指定します。 既定では、Windows 構成デザイナーはプロジェクト フォルダーを出力先として使います。 出力場所を変更する場合は、[ **参照**] を選択します。 操作が完了したら、**[次へ]** をクリックします。
1. [ **ビルド** ] を選択して、パッケージのビルドを開始します。 プロビジョニング パッケージのビルドにはそれほど時間はかかりません。 [ビルド] ページにプロジェクト情報が表示され、進行状況バーにビルドの状態が示されます。

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>プロビジョニングパッケージ、ステップ 3 &ndash; プロビジョニングパッケージを HoloLens に適用する

「プロビジョニングパッケージを使用して HoloLens を構成する」の記事では、次の状況でプロビジョニングパッケージを適用するための詳細な手順について説明しています。

- 最初 [に、セットアップ中に HoloLens にプロビジョニングパッケージを適用](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)できます。

- [セットアップ後に、HoloLens にプロビジョニングパッケージを適用](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)することもできます。

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>Windows デバイスポータルを使用してシングルアプリキオスクをセットアップする

Windows デバイスポータルを使用してキオスクモードを設定するには、次の手順に従います。

1. [Windows デバイスポータルを使用するように HoloLens デバイスを設定](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)します。 デバイス ポータルは、お使いの PC に Web ブラウザーから接続することができる HoloLens 上の Web サーバーです。

    > [!CAUTION]
    > デバイスポータルを使用するように HoloLens を設定する場合は、デバイスで開発者モードを有効にする必要があります。 Windows Holographic for Business があるデバイスの開発者モードでは、アプリをサイドロードすることができます。 ただし、この設定により、Microsoft Store によって認定されていないアプリをユーザーがインストールできる危険性が生じます。 管理者は、[ポリシー CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)の **Applicationmanagement/allowdeveloper Unlock** 設定を使用して、開発者モードを有効にする機能をブロックできます。 [開発者モードの詳細をご覧ください。](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. コンピューターで、 [wi-fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) または [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)を使用して HoloLens に接続します。

1. 次のいずれかの操作を行います。
   - Windows デバイスポータルに初めて接続する場合は、[ユーザー名とパスワードを作成](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)します。
   - 以前に設定したユーザー名とパスワードを入力します。

    > [!TIP]
    > ブラウザーに証明書エラーが表示された場合は、[こちらのトラブルシューティング手順](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)に従います。

1. Windows デバイスポータルで、[ **キオスクモード**] を選択します。

1. [ **キオスクモードを有効** にする] を選択し、デバイスの起動時に実行するアプリを選択して、[ **保存**] を選択します。

    ![キオスク モード](images/kiosk.png)
1. HoloLens を再起動します。 デバイスポータルページを開いたままにしている場合は、ページの上部にある [ **再起動** ] を選択できます。

> [!NOTE]
> キオスクモードは、デバイスポータルの REST API を使用して設定できます。これを行うには、1つの必須クエリ文字列パラメーター ("kioskModeEnabled&quot;、値 &quot;true&quot; または &quot;false") と1つの省略可能なパラメーター (パッケージ名の値を持つ/api/holographic/kioskmode/settings) を指定します。 デバイスポータルは開発者向けのものであり、開発者以外のデバイスでは有効にしないでください。 REST API は、今後の更新プログラム/リリースで変更される可能性があります。

## <a name="more-information"></a>詳細情報

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>プロビジョニングパッケージを使用してキオスクを構成する方法をご覧ください。  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>グローバルに割り当てられたアクセス: キオスクモード
- キオスクモードをシステムレベルで適用する新しいキオスク方法を有効にすることにより、キオスクの Id 管理を減らしました。

この新機能により、IT 管理者は、システムレベルで適用可能な複数のアプリキオスクモード用に HoloLens 2 デバイスを構成することができます。また、システム上の id との関係がなく、デバイスにサインインするすべてのユーザーに適用されます。 この新機能の詳細については、 [HoloLens グローバルに割り当てられたアクセスキオスク](hololens-global-assigned-access-kiosk.md) のドキュメントを参照してください。

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>マルチアプリキオスクモードでのアプリケーションの自動起動 
- アプリの自動起動に焦点を合わせ、キオスクモードエクスペリエンス用に選択された UI とアプリの選択範囲をさらに増やしています。

マルチアプリキオスクモードにのみ適用され、[割り当てられたアクセス構成] の下の強調表示された属性を使用して、1つのアプリのみを自動起動するように指定できます。 

ユーザーがサインインすると、アプリケーションが自動的に起動されます。 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>キオスクモードでのエラー処理の動作変更
- キオスクモードのエラーで利用可能なアプリを排除することで、より安全なキオスクモード。 

以前は、キオスクモードの適用中にエラーが発生した場合、[スタート] メニューのすべてのアプリケーションを表示するために HoloLens が使用されていました。 Windows Holographic バージョン20H2 でエラーが発生した場合は、次のように [スタート] メニューにアプリが表示されません。 

![キオスクモードが失敗したときにどのように表示されるかを示した画像。](images/hololens-kiosk-failure-behavior.png )

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>オフラインキオスクのキャッシュ Azure AD グループメンバーシップ
- オフラインキオスクが有効になり、Azure AD グループで最大60日間使用できるようになりました。

このポリシーでは、サインインしているユーザーのグループ Azure AD グループを対象とする割り当てられたアクセス構成で、Azure AD グループメンバーシップキャッシュを使用できる日数を制御します。 このポリシー値が0より大きい値に設定されている場合は、キャッシュが使用されます。  

名前: AADGroupMembershipCacheValidityInDays URI 値:./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最小-0 日  
最大-60 日 

このポリシーを正しく使用するための手順: 
1. Azure AD グループを対象とするキオスク用のデバイス構成プロファイルを作成し、HoloLens デバイスに割り当てます。 
1. カスタム OMA-URI ベースのデバイス構成を作成します。この構成では、このポリシー値を目的の日数 (> 0) に設定し、HoloLens デバイスに割り当てます。 
    1. URI 値は、/Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays のように OMA-URI テキストボックスに入力する必要があります。
    1. 許容される最小値と最大値の間の値を指定できます。
1. HoloLens デバイスを登録し、両方の構成がデバイスに適用されていることを確認します。 
1. インターネットが利用可能なときにユーザー1のサインインを Azure AD し、ユーザーのサインインと Azure AD グループのメンバーシップが正常に確認されると、キャッシュが作成されます。 
1. これで Azure AD ユーザー1が HoloLens をオフラインにして、ポリシー値で X 日の日数が許容される限り、キオスクモードで使用できるようになりました。 
1. 手順 4. と 5. は、他の Azure AD ユーザー N に対して繰り返すことができます。ここで重要なのは、Azure AD ユーザーは、少なくとも1回、キオスク構成の対象となる Azure AD グループのメンバーであることを確認できるように、インターネットを使用してデバイスにサインインする必要があるという点です。 
 
> [!NOTE]
> 手順 4. を実行すると Azure AD ユーザーに対して、"切断" 環境に記載されているエラー動作が発生します。 


## <a name="xml-kiosk-code-samples-for-hololens"></a>HoloLens 用の XML キオスクコードサンプル

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Azure AD グループを対象とする複数のアプリキオスクモード。 
このキオスクでは、Azure AD グループのユーザーに対してキオスクを展開し、[設定]、[リモートアシスタンス]、[フィードバックハブ] の3つのアプリを含むキオスクを有効にします。 このサンプルをすぐに使用するように変更するには、以下の強調表示されている GUID を、自分の Azure AD グループに一致するように変更してください。 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Azure AD アカウントを対象とする複数のアプリキオスクモード。
このキオスクでは、1人のユーザーに対してキオスクをデプロイし、[設定]、[リモートアシスタンス]、[フィードバックハブ] の3つのアプリを含むキオスクが有効になります。 このサンプルをすぐに使用するように変更するには、以下の強調表示されているアカウントを、自分の Azure AD アカウントと一致するように変更してください。 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

