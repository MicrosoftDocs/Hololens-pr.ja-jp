---
title: HoloLens を Kiosk としてセットアップする
description: キオスク構成をセットアップして使用して HoloLens デバイス上のアプリをロックダウンする方法について説明します。
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
ms.sourcegitcommit: e1dd3d79d763d02d4fe04c82d8f49e8f9d85ee4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "11445377"
---
# <a name="set-up-hololens-as-a-kiosk"></a>HoloLens を Kiosk としてセットアップする

キオスク モードで実行するデバイスを構成することで、HoloLens デバイスを固定目的のデバイス**(キオスクとも呼ばれる) として機能する構成できます。 キオスク モードでは、デバイスで使用できるアプリケーション (またはユーザー) が制限されます。 キオスク モードは、HoloLens デバイスをビジネス アプリに割り当て、またはアプリデモで HoloLens デバイスを使用するために使用できる便利な機能です。

この記事では、HoloLens デバイスに固有のキオスク構成の側面について説明します。 Windows ベースのキオスクの種類と構成方法の一般的な情報については、「Windows デスクトップ エディションでキオスクとデジタルサインを構成する」 [を参照してください](https://docs.microsoft.com/windows/configuration/kiosk-methods)。  

> [!IMPORTANT]  
> キオスク モードは、ユーザーがデバイスにサインインするときに使用できるアプリを決定します。 ただし、キオスク モードはセキュリティ方法ではありません。 許可されていない別のアプリを開く "許可" アプリは停止されません。 アプリやプロセスの開き方をブロックするには、Windows Defender アプリケーションコントロール [(WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) を使用して適切なポリシーを作成します。
>
> HoloLens 2 が使用する高度なレベルのセキュリティをユーザーに提供する Microsoft サービスの詳細については、「状態の分離と分離 - Defender の保護」を [参照してください](security-state-separation-isolation.md#defender-protections)。 または [、Microsoft Intune を使用して HoloLens 2](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)Windows PowerShellアプリを許可またはブロックするために WDAC とアプリを使用する方法について説明します。

キオスク モードは、単一アプリ構成または複数アプリ構成で使用できます。キオスク構成をセットアップおよび展開するには、3 つのプロセスのいずれかを使用できます。

> [!IMPORTANT]  
> マルチアプリ構成を削除すると、割り当てられたアクセス機能が作成したユーザー ロックダウン プロファイルが削除されます。 ただし、すべてのポリシー変更を元に戻すわけではありません。 これらのポリシーを元に戻すには、デバイスを工場出荷時の設定にリセットする必要があります。

## <a name="plan-the-kiosk-deployment"></a>キオスクの展開を計画する

キオスクを計画する場合は、次の質問に答える必要があります。 ここでは、このページを読んでいる間に考えるいくつかの決定事項と、これらの質問に関する考慮事項を示します。
1. **キオスクを使用するユーザーと、ユーザーが使用 [する](hololens-identity.md) アカウントの種類** これは、キオスクのために既に行っている可能性が高く、調整すべきではないが、キオスクが後で割り当てられる方法に影響を与える可能性がある決定です。
1. **ユーザー/グループごとに異なるキオスクを使用するか、キオスクが一部で有効になっていない必要がありますか?** その場合は、XML を使用してキオスクを作成します。 
1. **キオスクに含むアプリの数** アプリが 1 つ以上の場合は、マルチアプリ キオスクが必要です。 
1. **キオスクに含むアプリは何ですか?** 以下の AUMIDs のリストを使用して、独自のアプリに加In-Boxアプリを追加してください。
1. **キオスクを展開する方法** MDM にデバイスを登録する場合は、MDM を使用してキオスクを展開してください。 MDM を使用していない場合は、プロビジョニング パッケージを使用して展開できます。  

### <a name="kiosk-mode-requirements"></a>キオスク モードの要件

キオスク モードを使用する HoloLens 2 デバイスを構成できます。

> [!IMPORTANT]
> キオスク モードは、デバイスに Windows Holographic for Business がある場合にのみ使用できます。 HoloLens 2 デバイスはすべて Windows Holographic for Business に組み込まれているので、他のエディションはありません。 すべての HoloLens 2 デバイスは、キオスク モードを一度に実行できます。
>
> HoloLens (第 1 世代) デバイスは、OS ビルドと OS エディションの両方でアップグレードする必要があります。 HoloLens (第 1 世代) を Windows Holographic for Business エディションに更新する方法の [詳細を次に示](hololens1-upgrade-enterprise.md) します。 キオスク モードを使用する HoloLens (第 1 世代) デバイスを更新するには、まずデバイスが Windows 10 バージョン 1803 以降のバージョンを実行する必要があります。 Windows デバイス回復ツールを使用して HoloLens (第 1 世代) デバイスを既定のビルドに復元した場合、または最新の更新プログラムをインストールした場合は、デバイスを構成する準備が整いました。

> [!IMPORTANT]  
> キオスク モードで実行されるデバイスを保護するには、USB 接続などの機能をオフにするデバイス管理ポリシーの追加を検討してください。 さらに、更新リングの設定を確認して、営業時間内に自動更新が行われません。

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>単一アプリキオスクまたはマルチアプリ キオスクの間で決定する

ユーザーがデバイスにサインインすると、1 つのアプリ キオスクが指定したアプリを起動します。 スタート メニューは、Cortana と同様に無効になっています。 HoloLens 2 デバイスがスタート ジェスチャに [応答](hololens2-basic-usage.md#start-gesture) しない。 HoloLens (第 1 世代) デバイスはブルーム ジェスチャに [応答](hololens1-basic-usage.md) しない。 1 つのアプリしか実行できないので、ユーザーは他のアプリを配置できません。

マルチアプリ キオスクは、ユーザーがデバイスにサインインするときに [スタート] メニューを表示します。 キオスク構成によって、[スタート] メニューで使用できるアプリが決まる。 マルチアプリ キオスクを使用すると、ユーザーに使う必要があるものだけを提示し、使用する必要のなかったものを削除することで、ユーザーにわかりやすいエクスペリエンスを提供できます。

次の表に、さまざまなキオスク モードの機能を示します。

| &nbsp; |スタート メニュー |[クイック アクション] メニュー |カメラとビデオ |Miracast |Cortana |組み込みの音声コマンド |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|シングル アプリ キオスク |無効 |無効   |無効 |無効   |無効 |有効 <sup> 1</sup> |
|複数アプリ キオスク |有効 |有効 <sup> 2</sup> |使用可能 <sup> な 2</sup> |使用可能 <sup> な 2</sup> |使用可能 <sup> な 2、3</sup>  |有効 <sup> 1</sup> |

> <sup>1 </sup> 無効な機能に関連する音声コマンドは機能しません。  
> <sup>2 </sup> これらの機能を構成する方法の詳細については、「キオスク アプリの選択 [」を参照してください](#plan-kiosk-apps)。  
> <sup>3 </sup> Cortana が無効になっている場合でも、組み込みの音声コマンドが有効になります。

次の表に、さまざまなキオスク モードのユーザー サポート機能を示します。

| &nbsp; |サポートされているユーザーの種類 | 自動サインイン | 複数のアクセス レベル |
| --- | --- | --- | --- |
|シングル アプリ キオスク |Azure Active Directory (Azure Active Directory) (Azure AD) またはローカル アカウントのマネージ サービス アカウント (MSA) |はい |いいえ |
|複数アプリ キオスク |Azure AD アカウント |いいえ |はい |

これらの機能を使用する方法の例については、次の表を参照してください。

|次の場合は、単一アプリ キオスクを使用します。 |次の場合は、マルチアプリ キオスクを使用します。 |
| --- | --- |
|新入社員向け Dynamics 365 ガイドのみを実行するデバイス。 |さまざまな従業員に対してガイドとリモート アシスタンスの両方を実行するデバイス。 |
|カスタム アプリのみを実行するデバイス。 |ほとんどのユーザー (カスタム アプリのみを実行) のキオスクとして機能するが、特定のユーザー グループの標準デバイスとして機能するデバイス。 |

### <a name="plan-kiosk-apps"></a>キオスク アプリを計画する

キオスク アプリを選択する方法の一般的な情報については、「割り当てられたアクセス用アプリを選択するためのガイドライン (キオスク モード [)」を参照してください](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)。

Windows デバイス ポータルを使用して単一アプリ キオスクを構成する場合は、セットアップ プロセス中にアプリを選択します。  

モバイル デバイス管理 (MDM) システムまたはプロビジョニング パッケージを使用してキオスク モードを構成する場合は [、AssignedAccess 構成](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) サービス プロバイダー (CSP) を使用してアプリケーションを指定します。 CSP は [、アプリケーションを識別するためにアプリケーション ユーザー モデル ID (AUMID)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) を使用します。 次の表に、マルチアプリ キオスクで使用できる一部のインボックス アプリケーションの AUMID を示します。

> [!IMPORTANT]
> キオスク モードは、ユーザーがデバイスにサインインするときに使用できるアプリを決定します。 ただし、キオスク モードはセキュリティ方法ではありません。 許可されていない別のアプリを開く "許可" アプリは停止されません。 この動作は制限されないので、Edge アプリ、エクスプローラー アプリ、Microsoft Store アプリからアプリを起動できます。 キオスクから起動しない特定のアプリがある場合は、Windows Defender アプリケーション コントロール [(WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) を使用して適切なポリシーを作成します。 
> 
> さらに、Mixed Reality Home はキオスク アプリとして設定できない。

<a id="aumids"></a>

|アプリ名 |AUMID |
| --- | --- |
|3D ビューアー |Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\!Microsoft.Microsoft3DViewer |
|カレンダー |microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\!microsoft.windowslive.calendar |
|カメラ <sup> 1、2</sup> |HoloCamera\_cw5n1h2txyewy\!HoloCamera |
|Cortana <sup> 3</sup> |Microsoft.549981C3F5F10\_8wekyb3d8bbwe\!アプリ |
|HoloLens のデバイス ピッカー (第 1 世代) |HoloDevicesFlow\_cw5n1h2txyewy\!HoloDevicesFlow |
|HoloLens 2 のデバイス ピッカー |Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\!Microsoft.Windows.DevicesFlowHost |
|Dynamics 365 Guides |Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\!MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\!Microsoft.RemoteAssist |
|フィードバック &nbsp; ハブ |Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\!アプリ |
|エクスプローラー |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|メール |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast <sup> 4</sup> |&nbsp; |
|映画 & テレビ |Microsoft.ZuneVideo\_8wekyb3d8bbwe\!Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive\_8wekyb3d8bbwe\!アプリ |
|フォト |Microsoft.Windows.Photos\_8wekyb3d8bbwe\!アプリ |
|設定 |HolographicSystemSettings\_cw5n1h2txyewy\!アプリ |
|ヒント |Microsoft.HoloLensTips\_8wekyb3d8bbwe\!HoloLensTips |

> <sup>1 </sup> 写真またはビデオのキャプチャを有効にするには、キオスク アプリとしてカメラ アプリを有効にする必要があります。  
> <sup>2 </sup> カメラ アプリを有効にする場合は、次の条件に注意してください。
> - [クイック アクション] メニューには、[写真] ボタンと [ビデオ] ボタンが表示されます。  
> - また、写真を操作または取得できるアプリ (写真、メール、OneDrive など) を有効にする必要があります。  
>  
> <sup>3 キオスク アプリとして Cortana を有効にしない場合でも、組み込みの </sup> 音声コマンドが有効になります。 ただし、無効な機能に関連するコマンドは効果がありません。  
> <sup>4 </sup> Miracast を直接有効にすることはできません。 キオスク アプリとして Miracast を有効にするには、カメラ アプリとデバイス ピッカー アプリを有効にします。

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>ユーザーまたはグループのキオスク プロファイルを計画する

xml ファイルを作成する場合、または Intune の UI を使用してキオスクをセットアップする場合は、キオスクのユーザーになるユーザーを検討する必要があります。 キオスク構成は、個々のアカウントまたは Azure ユーザー グループADできます。 

通常、キオスクはユーザーまたはユーザー グループに対して有効です。 ただし、独自の XML キオスクの作成を計画している場合は、Id に関係なくデバイス レベルでキオスクが適用されるグローバル割り当てアクセスを検討する必要があります。 これがアピールされる場合は、「グローバル [割り当てアクセス キオスク」の詳細をご覧ください。](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>XML ファイルを作成する場合は、次の手順を実行します。
-   多くのユーザーは、複数のキオスク プロファイルを作成し、それぞれを異なるユーザー/グループに割り当てる必要があります。 多くのアプリを持つ Azure AD グループのキオスクや、1 つのアプリを持つ複数のアプリ キオスクを持つ訪問者など。
-   キオスク構成はプロファイル ID と呼ば **され、GUID** が設定されます。
-   ユーザーの種類を指定し、DefaultProfile Id に同じ GUID を使用して、configs セクションでプロファイル **を割り当てる必要があります**。
- カスタム OMA URI デバイス構成プロファイルを作成し、URI 値を使用して HoloLens デバイス グループに適用することで、XML ファイルを作成できますが、MDM を介してデバイスに適用できます。./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Intune でキオスクを作成する場合。
-   各デバイスは 1 つのキオスク プロファイルのみを受信できます。それ以外の場合は競合が発生し、キオスク構成は一切受け取らなされます。 
    -   キオスク構成プロファイルに関連しないデバイス制限など、他の種類のプロファイルやポリシーは、キオスク構成プロファイルと競合しない。
-   キオスクは、ユーザー ログオンの種類の一部であるすべてのユーザーに対して有効になります。これは、ユーザーまたは Azure ユーザー グループADされます。 
-   キオスク構成が設定され、 **ユーザー** ログオンの種類 (キオスクにログインできるユーザー) と [アプリ] が選択された後も、デバイス構成をグループに割り当てる必要があります。 割り当てられたグループは、キオスク デバイス構成を受け取るデバイスを決定しますが、キオスクが有効になっているかどうかを操作しません。 
    - Intune で構成プロファイルを割り当てる効果の詳細については、「Assign user and device [profiles in Microsoft Intune」を参照してください](https://docs.microsoft.com/intune/configuration/device-profile-assign)。

### <a name="select-a-deployment-method"></a>展開方法の選択

キオスク構成を展開するには、次のいずれかの方法を選択できます。

- [Microsoft Intune または他のモバイル デバイス管理 (MDM) サービス](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [プロビジョニング パッケージ](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Device Portal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > このメソッドでは、デバイスで開発者モードを有効にする必要があるため、デモンストレーションにのみ使用することをお勧めします。

次の表に、各展開方法の機能と利点を示します。

| &nbsp; |Windows デバイス ポータルを使用した展開 |プロビジョニング パッケージを使用して展開する |MDM を使用した展開 |
| --------------------------- | ------------- | -------------------- | ---- |
|単一アプリキオスクの展開   | はい           | はい                  | はい  |
|マルチアプリ キオスクの展開    | いいえ            | はい                  | はい  |
|ローカル デバイスにのみ展開する | はい           | はい                  | いいえ   |
|開発者モードを使用した展開 |必須かどうか       | 任意            | 任意   |
|Azure Active Directory を使用した展開 (Azure AD)  | 任意            | 任意                   | 必須かどうか  |
|自動的に展開する      | いいえ            | いいえ                   | はい  |
|展開速度            | Fast (高速)       | Fast (高速)                 | スロー (低速) |
|大規模な展開 | 推奨されません    | 推奨        | 推奨 |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Microsoft Intune または他の MDM を使用して、単一アプリまたは複数アプリのキオスクをセットアップする

Microsoft Intune または別の MDM システムを使用してキオスク モードを設定するには、次の手順を実行します。

1. [デバイスを登録する準備をします](#mdmenroll)。
1. [キオスク構成プロファイルを作成します](#mdmprofile)。
1. キオスクを構成します。
   - [単一アプリ キオスクの設定を構成します](#mdmconfigsingle)。
   - [マルチアプリ キオスクの設定を構成します](#mdmconfigmulti)。
1. [キオスク構成プロファイルをグループに割り当てる](#mdmassign)。
1. デバイスを展開します。
   - [単一アプリキオスクを展開します](#mdmsingledeploy)。
   - [マルチアプリ キオスクを展開します](#mdmmultideploy)。

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM、手順 1 &ndash; デバイスの登録の準備

ユーザーが最初にサインインするときに HoloLens デバイスを自動的に登録するか、ユーザーにデバイスを手動で登録する MDM システムを構成できます。 また、デバイスを Azure ADドメインに参加し、適切なグループに割り当てる必要があります。

デバイスを登録する方法の詳細については、「Windows デバイスの MDM および Intune 登録方法に [HoloLens](hololens-enroll-mdm.md) を登録する」 [を参照してください](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)。

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM、手順 2 &ndash; キオスク構成プロファイルの作成

1. Azure portal [を開](https://portal.azure.com/) き、Intune 管理者アカウントにサインインします。
1. [Microsoft **Intune**  >  **デバイス構成 - プロファイルプロファイルの**  >  **作成] を選択します**。
1. プロファイル名を入力します。
1. [**プラットフォーム**  >  **Windows 10 以降] を選択**し、[プロファイルの種類 **] [デバイス**の制限  > **] を選択します**。
1. [**キオスクの**  >  **構成]** を選択し、次のいずれかを選択します。
   - 単一アプリ キオスクを作成するには、[キオスク モード] **[シングル**アプリ  >  **キオスク] を選択します**。
   - マルチアプリ キオスクを作成するには、[キオスク**モード]**[マルチアプリ キオスク]  >  **を選択します**。
1. キオスクの構成を開始するには、[追加] を **選択します**。

次の手順は、必要なキオスクの種類によって異なります。 詳細については、次のいずれかのオプションを選択します。  

- [シングル アプリ キオスク](#mdmconfigsingle)
- [複数アプリ キオスク](#mdmconfigmulti)

キオスク構成プロファイルを作成する方法の詳細については、「Intune を使用して専用のキオスクとして実行する [Windows 10 および Windows Holographic for Business](https://docs.microsoft.com/intune/configuration/kiosk-settings)デバイス設定」を参照してください。

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM、手順 3 (単一アプリ) シングル アプリ キオスク &ndash;  の設定を構成する

このセクションでは、単一アプリキオスクで必要な設定の概要を示します。 詳細については、次の記事を参照してください。

- Intune でキオスク構成プロファイルを構成する方法については、「Microsoft Intune を使用してキオスク モードを構成する方法」 [を参照してください](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)。
- Intune の単一アプリ キオスクで使用可能な設定の詳細については、「シングル フルスクリーン アプリ キオスク」 [を参照してください。](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- その他の MDM サービスについては、使用しているプロバイダーのドキュメントで手順を参照してください。 MDM サービスでカスタム XML 構成を使用してキオスクをセットアップする必要がある場合は、キオスク構成を定義する [XML ファイルを作成します](#ppkioskconfig)。

1. [**ユーザー ログオンの種類]**[ローカル ユーザー アカウント] を選択し、キオスクにサインインできるローカル (デバイス) アカウントまたは  >  **** Microsoft アカウント (MSA) のユーザー名を入力します。
   > [!NOTE]  
   > **Autologon** ユーザー アカウントの種類は、Windows Holographic for Business ではサポートされていません。
1. [**アプリケーションの種類**  >  **] [ストア アプリ**] を選択し、一覧からアプリを選択します。

次の手順は、プロファイル [を](#mdmassign) グループに割り当てる方法です。

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM、手順 3 (マルチアプリ) マルチアプリ キオスクの &ndash; 設定を構成する

このセクションでは、マルチアプリ キオスクで必要な設定の概要を示します。 詳細については、次の記事を参照してください。

- Intune でキオスク構成プロファイルを構成する方法については、「Microsoft Intune を使用してキオスク モードを構成する方法」 [を参照してください](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)。
- Intune のマルチアプリ キオスクで使用可能な設定の詳細については、「マルチアプリ キオスク [」を参照してください。](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- その他の MDM サービスについては、使用しているプロバイダーのドキュメントで手順を参照してください。 MDM サービスでカスタム XML 構成を使用してキオスクをセットアップする必要がある場合は、キオスク構成を定義する [XML ファイルを作成します](#ppkioskconfig)。 XML ファイルを使用する場合は、必ずスタート 画面のレイアウトを [含める必要があります](#start-layout-for-hololens)。  
- 必要に応じて、Intune または他の MDM サービスでカスタムスタート レイアウトを使用できます。 詳細については、「スタート レイアウト [ファイル for MDM (Intune など)」を参照してください](#start-layout-file-for-mdm-intune-and-others)。

1. **S モード デバイスで [ターゲット Windows 10] を**  >  **選択します。**  
   >[!NOTE]  
   > S モードは、Windows Holographic for Business ではサポートされていません。
1. [**ユーザー ログオンの種類**  >  **] [Azure ADまたは**グループまたはユーザー ログオンの種類****  >  **HoloLens の**訪問者] を選択し、1 つ以上のユーザー グループまたはアカウントを追加します。  

   ユーザー ログオンの種類で指定したグループまたはアカウントに属**** するユーザーだけが、キオスク エクスペリエンスを使用できます。

1. 次のオプションを使用して、1 つ以上のアプリを選択します。
   - アップロードされた業務用アプリを追加するには、[ストア アプリの追加] **を** 選択し、目的のアプリを選択します。
   - AUMID を指定してアプリを追加するには **、[AUMID** で追加] を選択し、アプリの AUMID を入力します。 [使用可能な AUMID の一覧を参照してください。](#aumids)

次の手順は、プロファイル [を](#mdmassign) グループに割り当てる方法です。

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM、手順 4 &ndash; キオスク構成プロファイルをグループに割り当てる

キオスク構成 **プロファイルの [** 割り当て] ページを使用して、キオスク構成を展開する場所を設定します。 最も簡単なケースでは、デバイスが MDM に登録するときに HoloLens デバイスを含むグループにキオスク構成プロファイルを割り当てる必要があります。

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM、手順 5 (単一アプリ) &ndash; 単一アプリ キオスクの展開

MDM システムを使用すると、OOBE 中にデバイスを MDM に登録できます。 OOBE の完了後、デバイスへのサインインは簡単です。

OOBE の間に、次の手順を実行します。

1. キオスク構成プロファイルで指定したアカウントを使用してサインインします。
1. デバイスを登録します。 キオスク構成プロファイルが割り当てられているグループにデバイスが追加されている必要があります。
1. OOBE が終了し、ストア アプリがダウンロードおよびインストールされ、ポリシーが適用されるのを待ちます。 次に、デバイスを再起動します。

次回デバイスにサインインすると、キオスク アプリが自動的に起動します。

この時点でキオスク構成が表示されていない場合は、割り当 [ての状態を確認します](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM、手順 5 (マルチアプリ) &ndash; マルチアプリ キオスクの展開

MDM システムを使用する場合は、デバイスを Azure ADテナントに参加し、OOBE の間に MDM に登録できます。 必要に応じて、OOBE プロセス中にユーザーが利用できる登録情報をユーザーに提供します。

> [!NOTE]  
> ユーザーを含むグループにキオスク構成プロファイルを割り当てた場合は、そのユーザー アカウントの 1 つがデバイスにサインインする最初のアカウントである必要があります。

OOBE の間に、次の手順を実行します。

1. ユーザー ログオンの種類グループに属するアカウントを使用 **してサインイン** します。
1. デバイスを登録します。
1. キオスク構成プロファイルの一部であるアプリがダウンロードおよびインストールされるのを待ちます。 また、ポリシーが適用されるのを待ちます。  
1. OOBE が完了したら、Microsoft ストアから、またはサイドローディングによって追加のアプリをインストールできます。 [デバイスが](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) 属するグループに必要なアプリが自動的にインストールされます。
1. インストールが完了したら、デバイスを再起動します。

ユーザー ログオンの種類に属するアカウントを使用してデバイスに次回サインインすると、**** キオスク アプリが自動的に起動します。

この時点でキオスク構成が表示されていない場合は、割り当 [ての状態を確認します](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>プロビジョニング パッケージを使用して、単一アプリまたは複数アプリのキオスクをセットアップする

プロビジョニング パッケージを使用してキオスク モードを設定するには、次の手順を実行します。

1. [キオスク構成を定義する XML ファイルを作成します](#ppkioskconfig)。開始レイアウトを [含む](#start-layout-for-hololens)。
2. [プロビジョニング パッケージに XML ファイルを追加します。](#ppconfigadd)
3. [HoloLens にプロビジョニング パッケージを適用します。](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>プロビジョニング パッケージ、手順 1 &ndash; キオスク構成 XML ファイルの作成

Windows [デスクトップ用のキオスク構成 XML](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)ファイルを作成するには、以下を除く一般的な手順に従います。

- クラシック Windows アプリケーション (Win32) を含めない。 HoloLens では、これらのアプリケーションはサポートされていません。
- HoloLens [用のプレースホルダー](#start-layout-for-hololens) Start layout XML を使用します。
- オプション: キオスク構成へのゲスト アクセスの追加

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>オプション: キオスク構成へのゲスト アクセスの追加

XML ファイル[**の [Configs]**](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)セクションで、ゲストがキオスクを使用できるよう、**訪問者**という名前の特別なグループを構成できます。 キオスクが訪問者特別グループをサポートするように**** 構成されている場合は、サインイン ページに "**ゲスト**" オプションが追加されます。 ゲスト **アカウント** にはパスワードは必要ではなく、アカウントに関連付けられているデータは、アカウントがサインアウトするときに削除されます。

ゲスト アカウントを **有効にするには** 、キオスク構成 XML に次のスニペットを追加します。

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>HoloLens のプレースホルダースタートレイアウト

プロビジョニング パッケージを使用 [してマルチ](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) アプリ キオスクを構成する場合は、スタート 画面のレイアウトが必要です。 Windows Holographic for Business では、スタート レイアウトのカスタマイズはサポートされていません。 そのため、プレースホルダーのスタート 画面のレイアウトを使用する必要があります。

> [!NOTE]  
> ユーザーがサインインすると、1 つのアプリ キオスクがキオスク アプリを起動するので、[スタート] メニューは使用しないので、スタート画面のレイアウトを持つ必要はないのでです。

> [!NOTE]  
> MDM を使用 [して](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) マルチアプリ キオスクをセットアップする場合は、必要に応じてスタート 画面のレイアウトを使用できます。 詳細については、「プレースホルダースタート [レイアウト ファイル for MDM (Intune など)」を参照してください](#start-layout-file-for-mdm-intune-and-others)。

[スタート] レイアウトの場合は、次の **[StartLayout]** セクションをキオスク プロビジョニング XML ファイルに追加します。

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

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>MDM のプレースホルダースタート レイアウト ファイル (Intune など)

次のサンプルを XML ファイルとして保存します。 このファイルは、Microsoft Intune (またはキオスク プロファイルを提供する別の MDM サービス) でマルチアプリ キオスクを構成するときに使用できます。

> [!NOTE]
> MDM サービスでカスタム設定と完全な XML 構成を使用してキオスクをセットアップする必要がある場合は、プロビジョニング パッケージのレイアウトの開始手順 [を使用します](#start-layout-for-hololens)。

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

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Prov。 パッケージ、手順 2 &ndash; キオスク構成 XML ファイルをプロビジョニング パッケージに追加する

1. [Windows 構成デザイナーを開きます](https://www.microsoft.com/store/apps/9nblggh4tx22)。
1. [ **高度なプロビジョニング] を**選択し、プロジェクトの名前を入力し、[次へ] を **選択します**。
1. [Windows **10 Holographic] を**選択し、[次へ] を **選択します**。
1. [完了 **] を選択します**。 パッケージのワークスペースが開きます。
1. [**ランタイム設定**  >  **]**  >  **[AssignedAccess MultiAppAssignedAccessSettings] を選択します**。
1. 中央のウィンドウで、[参照] **を選択** して、作成したキオスク構成 XML ファイルを見つけて選択します。

   ![Windows 構成デザイナーにおける MultiAppAssignedAccessSettings フィールドのスクリーンショット](./images/multiappassignedaccesssettings.png)

1. **省略可能です**。 (デバイスの初期セットアップ後にプロビジョニング パッケージを適用する場合に、キオスク デバイスで既に利用可能な管理者ユーザーが存在する場合は、この手順を省略します)。[ **ランタイム設定]** &gt; **[アカウント** &gt; **ユーザー]** を選択し、ユーザー アカウントを作成します。 ユーザー名とパスワードを入力し **、[UserGroup**  >  **Administrators] を選択します**。  
  
     このアカウントを使用すると、プロビジョニングの状態とログを表示できます。  
1. **省略可能です**。 (キオスク デバイスに管理者以外のアカウントが既にある場合は、この手順を省略します)。[ **ランタイム設定]** &gt; **[** &gt; **アカウント ユーザー]** を選択し、ローカル ユーザー アカウントを作成します。 ユーザー名が構成 XML で指定したアカウントと同じことを確認します。 **[UserGroup Standard**  >  **Users] を選択します**。
1. [ファイル**の保存]**  >  **を選択します**。
1. [**プロビジョニング パッケージ**  >  **のエクスポート] を選択**し、[所有者 IT**管理者]**  >  **を選択します**。これにより、他のソースからこのデバイスに適用されるプロビジョニング パッケージよりも、このプロビジョニング パッケージの優先順位が高くなります。
1. **[次へ]** を選択します。
1. [プロビジョニング **パッケージのセキュリティ] ページで** 、セキュリティ オプションを選択します。
   > [!IMPORTANT]  
   > [パッケージ署名を **有効にする]** を選択した場合は、パッケージの署名に使用する有効な証明書も選択する必要があります。 これを行うには、[参照] **を** 選択し、パッケージの署名に使用する証明書を選択します。
   
   > [!CAUTION]  
   > [パッケージの暗号化を **有効にする] を選択しません**。 HoloLens デバイスでは、この設定によってプロビジョニングが失敗します。
1. **[次へ]** を選択します。
1. プロビジョニング パッケージのビルド時に移動する出力場所を指定します。 既定では、Windows 構成デザイナーはプロジェクト フォルダーを出力先として使います。 出力場所を変更する場合は、[参照] を **選択します**。 完了したら、[次へ] を **選択します**。
1. [ **ビルド] を** 選択して、パッケージのビルドを開始します。 プロビジョニング パッケージのビルドにはそれほど時間はかかりません。 ビルド ページにはプロジェクト情報が表示され、進行状況バーはビルドの状態を示します。

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>プロビジョニング パッケージ、手順 3 プロビジョニング パッケージを &ndash; HoloLens に適用する

「プロビジョニング パッケージを使用して HoloLens を構成する」の記事では、次の状況でプロビジョニング パッケージを適用する詳細な手順を説明します。

- セットアップ中に [、最初にプロビジョニング パッケージを HoloLens に適用できます](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。

- セットアップ後 [に HoloLens にプロビジョニング パッケージを適用できます](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)。

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>Windows デバイス ポータルを使用して単一アプリ キオスクをセットアップする

Windows デバイス ポータルを使用してキオスク モードを設定するには、次の手順を実行します。

1. [Windows デバイス ポータルを使用する HoloLens デバイスをセットアップします](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)。 デバイス ポータルは、お使いの PC に Web ブラウザーから接続することができる HoloLens 上の Web サーバーです。

    > [!CAUTION]
    > デバイス ポータルを使用する HoloLens を設定する場合は、デバイスで開発者モードを有効にする必要があります。 Windows Holographic for Business を持つデバイスの開発者モードを使用すると、アプリをサイド ロードできます。 ただし、この設定により、Microsoft Store によって認定されていないアプリをユーザーがインストールできるリスクが生じかねない。 管理者は、ポリシー CSP の **ApplicationManagement/AllowDeveloper Unlock** 設定を使用して、開発者モードを有効にする機能を [ブロックできます](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)。 [開発者モードの詳細をご覧ください。](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. コンピューターで [、Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) または USB を使用して HoloLens に接続 [します](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)。

1. 次のいずれかの操作を行います。
   - Windows デバイス ポータルに初めて接続する場合は、ユーザー [名とパスワードを作成します。](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - 以前に設定したユーザー名とパスワードを入力します。

    > [!TIP]
    > ブラウザーに証明書エラーが表示された場合は、[こちらのトラブルシューティング手順](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)に従います。

1. Windows デバイス ポータルで、[キオスク モード] **を選択します**。

1. [ **キオスク モードを有効にする**] を選択し、デバイスの起動時に実行するアプリを選択し、[保存] を **選択します**。

    ![Kiosk Mode (キオスク モード)](images/kiosk.png)
1. HoloLens を再起動します。 デバイス ポータル ページがまだ開いている場合は、ページの上部にある **[** 再起動] を選択できます。

> [!NOTE]
> キオスク モードは、デバイス ポータルの REST API を使用して、必要なクエリ文字列パラメーター ("kioskModeEnabled" の値が "true" または "false") とオプションのパラメーター (パッケージ名の値を持つ 1 つの "startupApp") を使用して、/api/holographic/kioskmode/settings に POST を実行することで設定できます。 Device Portal は開発者のみを対象としますが、開発者以外のデバイスでは有効にしない必要があります。 REST API は、今後の更新/リリースで変更される可能性があります。

## <a name="more-information"></a>詳細情報

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>プロビジョニング パッケージを使用してキオスクを構成する方法について説明します。  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>グローバル割り当てアクセス – キオスク モード
- システム レベルでキオスク モードを適用する新しい Kiosk メソッドを有効にすることで、キオスクの ID 管理を減らしました。

この新しい機能により、IT 管理者は HoloLens 2 デバイスを複数のアプリ キオスク モード用に構成できます。これはシステム レベルで適用可能で、システム上の ID と親和性を持たず、デバイスにサインインするすべてのユーザーに適用されます。 この新機能 [の詳細については、「HoloLens グローバル割り当てアクセス](hololens-global-assigned-access-kiosk.md) キオスク」のドキュメントを参照してください。

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>複数アプリキオスク モードでのアプリケーションの自動起動 
- アプリの自動起動に重点を置いてエクスペリエンスを向上し、キオスク モード エクスペリエンス用に選択された UI とアプリの選択をさらに増やします。

複数アプリキオスク モードにのみ適用され、割り当てられたアクセス構成で以下の強調表示された属性を使用して自動起動に指定できるアプリは 1 つのみです。 

ユーザーがサインインすると、アプリケーションが自動的に起動されます。 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>失敗の処理に関するキオスク モードの動作の変更
- キオスク モードのエラーで使用可能なアプリを排除することで、より安全なキオスク モードを提供します。 

以前、キオスク モードの適用でエラーが発生した場合、HoloLens はスタート メニューにすべてのアプリケーションを表示するために使用しました。 Windows Holographic Version 20H2 では、エラーが発生した場合、スタート メニューに以下のようにアプリが表示されません。 

![失敗した場合に表示されるキオスク モードのイメージ。](images/hololens-kiosk-failure-behavior.png )

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>オフライン キオスクの Azure ADグループ メンバーシップをキャッシュする
- 最大 60 日間、Azure ADグループで使用するオフライン キオスクを有効にしました。

このポリシーは、サインインしているユーザーの Azure AD グループを対象とする割り当てられたアクセス構成に、Azure AD グループ メンバーシップ キャッシュを使用できる日数を制御します。 このポリシー値を 0 より大きい値に設定すると、それ以外の場合はキャッシュが使用されません。  

名前: AADGroupMembershipCacheValidityInDays URI 値: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最小 - 0 日  
最大 - 60 日間 

このポリシーを正しく使用する手順は次のとおりです。 
1. Azure グループを対象とするキオスク用のデバイス構成プロファイルAD作成し、HoloLens デバイスに割り当てる。 
1. このポリシー値を希望の日数 (> > 0) に設定し、HoloLens デバイスに割り当てるカスタム OMA URI ベースのデバイス構成を作成します。 
    1. URI 値は 、./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays として OMA-URI テキスト ボックスに入力する必要があります。
    1. 値は最小/最大の間で指定できます。
1. HoloLens デバイスを登録し、両方の構成がデバイスに適用されるのを確認します。 
1. インターネットがAD、ユーザーがサインインし、Azure AD グループ メンバーシップが正常に確認されると、キャッシュが作成されます。 
1. これで、Azure ADユーザー 1 は HoloLens をオフラインにし、ポリシー値で日数を X に設定できる限り、キオスク モードで使用できます。 
1. 手順 4 と 5 は、他の Azure AD ユーザー N に対して繰り返し実行できます。ここで重要な点は、Azure AD ユーザーがインターネットを使用してデバイスにサインインする必要がある点です。少なくとも 1 回は、キオスク構成が対象となる Azure AD グループのメンバーと判断できます。 
 
> [!NOTE]
> Azure サーバーに対して手順 4 が実行されるまでAD「切断された」環境で説明されているエラー動作が発生します。 


## <a name="xml-kiosk-code-samples-for-hololens"></a>HoloLens の XML キオスク コード サンプル

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Azure ユーザーグループを対象とする複数ADキオスク モード。 
このキオスクは、Azure AD グループのユーザーに対して、設定、リモート アシスト、フィードバック ハブの 3 つのアプリを含むキオスクを有効にするキオスクを展開します。 このサンプルを直ちに使用するように変更するには、以下で強調表示されている GUID を、独自の Azure AD一致するように変更してください。 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Azure ADアカウントを対象とする複数のアプリ キオスク モード。
このキオスクは、1 人のユーザーにキオスクを展開し、設定、リモート アシスト、フィードバック ハブの 3 つのアプリを含むキオスクを有効にします。 このサンプルをすぐに使用するように変更するには、以下で強調表示されているアカウントを、自分の Azure ADアカウントと一致するように変更してください。 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

