---
title: HoloLens をキオスクとしてセットアップする
description: キオスク構成を設定して使用して、デバイス上のアプリをロックダウンするHoloLensします。
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
ms.openlocfilehash: e7f1efa99cc16b1003bd7063817451013ed2ec2661dbdf02edcd89c7984d0980
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664007"
---
# <a name="set-up-hololens-as-a-kiosk"></a>HoloLens をキオスクとしてセットアップする

キオスク モードで実行HoloLensデバイスを構成することで、固定目的のデバイス (キオスク とも呼ばれる) として機能するデバイスを構成できます。 キオスク モードでは、デバイスで使用できるアプリケーション (またはユーザー) が制限されます。 キオスク モードは、HoloLens デバイスをビジネス アプリに割り当て、アプリデモで HoloLens デバイスを使用するために使用できる便利な機能です。

この記事では、デバイス固有のキオスク構成の側面についてHoloLensします。 さまざまな種類の Windows ベースのキオスクとそれらを構成する方法に関する一般的な情報については、「Windows デスクトップ エディションでのキオスクとデジタル[サインの構成」を参照してください](/windows/configuration/kiosk-methods)。  

> [!IMPORTANT]  
> キオスク モードは、ユーザーがデバイスにサインインするときに使用できるアプリを決定します。 ただし、キオスク モードはセキュリティ方法ではありません。 "許可された" アプリが、許可されていない別のアプリを開くのを停止しない。 アプリまたはプロセスの開きをブロックするには、Windows Defender [Application Control (WDAC) CSP](/windows/client-management/mdm/applicationcontrol-csp)を使用して適切なポリシーを作成します。
>
> ユーザーが使用する高度Microsoft サービスレベルのセキュリティをユーザーに提供HoloLens 2の詳細については、「状態の分離と分離 - Defender 保護」を[参照してください](security-state-separation-isolation.md#defender-protections)。 または、WDAC と Windows PowerShell を使用して、 を使用してデバイス上のアプリを許可またはHoloLens 2[する方法Microsoft Intune。](/mem/intune/configuration/custom-profile-hololens)

キオスク モードは、単一アプリまたはマルチアプリ構成で使用できます。また、3 つのプロセスのいずれかを使用してキオスク構成を設定および展開できます。

> [!IMPORTANT]  
> マルチアプリ構成を削除すると、割り当てられたアクセス機能によって作成されたユーザー ロックダウン プロファイルが削除されます。 ただし、すべてのポリシー変更が元に戻されるわけではありません。 これらのポリシーを元に戻すには、デバイスを出荷時の設定にリセットする必要があります。

## <a name="plan-the-kiosk-deployment"></a>キオスクの展開を計画する

キオスクを計画する場合は、次の質問に回答できる必要があります。 このページを読む際に考慮すべきいくつかの決定事項と、これらの質問に関する考慮事項を次に示します。
1. **Whoキオスクを使用する場合、どのような種類のアカウント [を](hololens-identity.md)使用しますか?** これは既に行っている可能性が高い決定であり、キオスクのために調整すべきではなく、後でキオスクが割り当てられる方法に影響します。
1. **ユーザー/グループごとに異なるキオスクを使用するか、一部のキオスクが有効になっていない必要がありますか?** その場合は、XML を使用してキオスクを作成します。 
1. **キオスクに含むアプリの数はどれくらいですか?** アプリが 1 つ以上の場合は、マルチアプリ キオスクが必要です。 
1. **キオスクに表示されるアプリは何ですか?** 以下の AUMID の一覧を使用して、独自のアプリIn-Boxアプリを追加してください。
1. **キオスクを展開する方法** MDM にデバイスを登録する場合は、MDM を使用してキオスクを展開してください。 MDM を使用していない場合は、プロビジョニング パッケージを使用した展開を使用できます。  

### <a name="kiosk-mode-requirements"></a>キオスク モードの要件

キオスク モードを使用HoloLens 2デバイスを構成できます。

> [!IMPORTANT]
> キオスク モードは、デバイスにデバイスがインストールされているWindows Holographic for Business。 すべてのHoloLens 2デバイスは Windows Holographic for Businessに出荷され、他のエディションはありません。 すべてのHoloLens 2デバイスは、キオスク モードを一から実行できます。
>
> HoloLens (第 1 世代) デバイスは、OS ビルドと OS エディションの両方でアップグレードする必要があります。 次に、新しいエディション (第 1 世代) HoloLens[更新する方法](hololens1-upgrade-enterprise.md)の詳細Windows Holographic for Businessします。 HoloLens (第 1 世代) デバイスを更新してキオスク モードを使用するには、まず、デバイスが Windows 10 バージョン 1803 以降のバージョンを実行している必要があります。 Windows Device Recovery Tool を使用して HoloLens (第 1 世代) デバイスを既定のビルドに回復した場合、または最新の更新プログラムをインストールした場合は、デバイスを構成する準備ができています。

> [!IMPORTANT]  
> キオスク モードで実行されるデバイスを保護するには、USB 接続などの機能をオフにするデバイス管理ポリシーを追加する方法を検討してください。 さらに、更新リングの設定を確認して、営業時間中に自動更新が行われるのを確認します。

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>シングル アプリ キオスクとマルチアプリ キオスクの間で決定する

シングル アプリ キオスクは、ユーザーがデバイスにサインインすると、指定されたアプリを起動します。 このスタート メニューと同様に、無効Cortana。 デバイスHoloLens 2開始ジェスチャに[応答](hololens2-basic-usage.md#start-gesture)しない。 1 HoloLens (第 1 世代) デバイスは、花のジェスチャに[応答](hololens1-basic-usage.md)しない。 実行できるアプリは 1 つだけなので、ユーザーは他のアプリを配置できません。

マルチアプリ キオスクでは、ユーザースタート メニューデバイスにサインインすると、そのデバイスが表示されます。 キオスク構成によって、デバイスで使用できるアプリがスタート メニュー。 マルチアプリ キオスクを使用すると、ユーザーが使用する必要があるものだけをユーザーに提示し、使用する必要のなかったものを削除することで、ユーザーにわかりやすいエクスペリエンスを提供できます。

次の表に、さまざまなキオスク モードの機能を示します。

| &nbsp; |[スタート] メニュー |[クイック アクション] メニュー |カメラとビデオ |Miracast |Cortana |組み込みの音声コマンド |
| --- | --- | --- | --- | --- | --- | --- | 
|シングル アプリ キオスク |無効 |無効 |無効 |無効   |無効 |有効<sup>1</sup> |
|マルチ アプリ キオスク |Enabled |有効<sup>2</sup> |利用可能<sup>2</sup> |利用可能<sup>2</sup> |使用可能<sup>2、3</sup>  |有効<sup>1</sup> |

> <sup>1 無効</sup> な機能に関連する音声コマンドは機能しません。  
> <sup>2 これらの</sup> 機能を構成する方法の詳細については、「キオスク アプリの選択 [」を参照してください](#plan-kiosk-apps)。  
> <sup>3</sup>無効Cortana場合でも、組み込みの音声コマンドが有効になります。

次の表に、さまざまなキオスク モードのユーザー サポート機能を示します。

| &nbsp; |サポートされているユーザーの種類 | 自動サインイン | 複数のアクセス レベル |
| --- | --- | --- | --- |
|シングル アプリ キオスク | Azure Active Directory (Azure AD) またはローカル アカウントの Microsoft アカウント (MSA) |はい |いいえ |
|マルチ アプリ キオスク |Azure AD アカウント |いいえ |はい |

これらの機能の使用例については、次の表を参照してください。

|次の場合は、シングル アプリ キオスクを使用します。 |次の場合は、マルチアプリ キオスクを使用します。 |
| --- | --- |
|新しい従業員向け Dynamics 365 ガイドのみを実行するデバイス。 |さまざまな従業員のガイドとリモート アシスタンスの両方を実行するデバイス。 |
|カスタム アプリのみを実行するデバイス。 |ほとんどのユーザーのキオスクとして機能するデバイス (カスタム アプリのみを実行) が、特定のユーザー グループの標準デバイスとして機能します。 |

### <a name="plan-kiosk-apps"></a>キオスク アプリを計画する

キオスク アプリの選択方法に関する一般的な情報については、「割り当て済みアクセスのアプリを選択するためのガイドライン (キオスク モード [)」を参照してください](/windows/configuration/guidelines-for-assigned-access-app)。

シングル アプリ キオスクを構成Windows デバイス ポータルを使用する場合は、セットアップ プロセス中にアプリを選択します。  

Mobile デバイス管理 (MDM) システムまたはプロビジョニング パッケージを使用してキオスク モードを構成する場合は [、AssignedAccess 構成](/windows/client-management/mdm/assignedaccess-csp) サービス プロバイダー (CSP) を使用してアプリケーションを指定します。 CSP は、 [アプリケーション を識別するためにアプリケーション ユーザー モデル ID (AUMID)](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) を使用します。 次の表に、マルチアプリ キオスクで使用できる一部のインボックス アプリケーションの AUMID を示します。

> [!IMPORTANT]
> キオスク モードは、ユーザーがデバイスにサインインするときに使用できるアプリを決定します。 ただし、キオスク モードはセキュリティ方法ではありません。 "許可された" アプリが、許可されていない別のアプリを開くのを停止しない。 この動作は制限されていないので、Edge、エクスプローラー、およびアプリからアプリを起動Microsoft Storeできます。 キオスクから起動したくない特定のアプリがある場合は[、Windows Defender Application Control (WDAC) CSP](/windows/client-management/mdm/applicationcontrol-csp)を使用して適切なポリシーを作成します。 
> 
> さらに、Mixed Reality Home をキオスク アプリとして設定できない。

<a id="aumids"></a>

|アプリ名 |AUMID |
| --- | --- |
|3D ビューアー |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Calendar |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|カメラ<sup>1、2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! アプリ |
|HoloLens デバイス ピッカー (第 1 世代) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|デバイス ピッカー (HoloLens 2 |マイクロソフト。Windows。DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows。DevicesFlowHost |
|Dynamics 365 Guides |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft.RemoteAssist |
|フィードバック &nbsp; ハブ |Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe \! アプリ |
|エクスプローラー |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|メール |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|古いMicrosoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge |
|新しいMicrosoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast<sup>4</sup> |&nbsp; |
|映画 & テレビ |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! アプリ |
|写真 |マイクロソフト。Windows。写真 \_ 8wekyb3d8bbwe \! アプリ |
|古い設定 |HolographicSystemSettings_cw5n1h2txyewy!アプリ |
|新しい設定 |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!アプリ |
|ヒント |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> 写真またはビデオのキャプチャを有効にするには、キオスク アプリとしてカメラ アプリを有効にする必要があります。  
> <sup>2</sup> カメラ アプリを有効にする場合は、次の条件に注意してください。
> - [クイック アクション] メニューには、[写真] ボタンと [ビデオ] ボタンが表示されます。  
> - また、画像を操作または取得できるアプリ (写真、メール、OneDrive など) を有効にする必要があります。  
>  
> <sup>3</sup>キオスク アプリとしてCortana有効にしていない場合でも、組み込みの音声コマンドが有効になります。 ただし、無効な機能に関連するコマンドは効果がありません。  
> <sup>4</sup>直接有効にMiracastすることはできません。 キオスク アプリMiracast有効にするには、カメラ アプリとデバイス ピッカー アプリを有効にします。

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>ユーザーまたはグループのキオスク プロファイルを計画する

xml ファイルを作成する場合、または Intune の UI を使用してキオスクを設定する場合は、キオスクのユーザーを検討する必要があります。 キオスクの構成は、個々のアカウントまたはグループにAzure ADできます。 

通常、キオスクはユーザーまたはユーザー グループに対して有効になります。 ただし、独自の XML キオスクの作成を計画している場合は、ID に関係なくデバイス レベルでキオスクが適用されるグローバル割り当てアクセスを検討できます。 これがお気に入りである場合は、グローバル [割り当てアクセス キオスクに関するページを参照してください。](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>XML ファイルを作成する場合:
-   多くの場合、複数のキオスク プロファイルを作成し、それぞれを異なるユーザー/グループに割り当てる必要があります。 多数のアプリを持つ Azure AD グループのキオスクや、1 つのアプリを持つ複数のアプリ キオスクを持つビジターなどです。
-   キオスクの構成はプロファイル ID と呼ば **され、GUID** が設定されます。
-   ユーザーの種類を指定し、DefaultProfile ID に同じ GUID を使用して、configs セクションでこのプロファイル **を割り当てる必要があります**。
- カスタム OMA URI デバイス構成プロファイルを作成し、URI 値 ./Device/Vendor/MSFT/AssignedAccess/Configuration を使用して HoloLens デバイス グループに適用することで、MDM を介してデバイスに XML ファイルを作成できますが、引き続き適用できます。

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Intune でキオスクを作成する場合。
-   各デバイスは 1 つのキオスク プロファイルのみを受け取る場合があります。それ以外の場合、競合が発生し、キオスク構成は一切受信されない。 
    -   キオスク構成プロファイルに関連しないデバイスの制限など、他の種類のプロファイルとポリシーは、キオスク構成プロファイルと競合しない。
-   キオスクは、ユーザー ログオンの種類の一部であるすべてのユーザーに対して有効になります。これは、ユーザーまたはユーザー グループAzure ADされます。 
-   キオスクの構成が設定され、ユーザー ログオンの種類 **(キオスク** にログインできるユーザー) と [アプリ] が選択された後も、デバイス構成をグループに割り当てる必要があります。 [割り当て済み] グループは、キオスク デバイス構成を受け取るデバイスを決定しますが、キオスクが有効になっている場合は、対話しません。 
    - Intune で構成プロファイルを割り当てる効果の詳細については、「Intune でのユーザープロファイルとデバイス プロファイルの割り当て」を[Microsoft Intune。](/intune/configuration/device-profile-assign)

### <a name="select-a-deployment-method"></a>デプロイ方法を選択する

キオスク構成を展開するには、次のいずれかの方法を選択できます。

- [Microsoft Intuneその他のモバイル デバイス管理 (MDM) サービス](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [プロビジョニング パッケージ](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windowsデバイス ポータル](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > この方法では、デバイスで開発者モードを有効にする必要があります。このため、デモンストレーションにのみ使用することをお勧めします。

次の表に、各デプロイ方法の機能と利点を示します。

| &nbsp; |を使用してデプロイWindows デバイス ポータル |プロビジョニング パッケージを使用してデプロイする |MDM を使用したデプロイ |
| --------------------------- | ------------- | -------------------- | ---- |
|シングル アプリ キオスクを展開する   | Yes           | Yes                  | Yes  |
|マルチアプリ キオスクを展開する    | いいえ            | はい                  | Yes  |
|ローカル デバイスにのみ展開する | Yes           | はい                  | いいえ   |
|開発者モードを使用したデプロイ |必須       | 必要なし            | 必要なし   |
|Azure Active Directory を使用したデプロイ (Azure AD)  | 必要なし            | 必要なし                   | 必須  |
|自動的に配置する      | いいえ            | いいえ                   | はい  |
|展開の速度            | 速い       | 高速                 | 低速 |
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

ユーザーが初めてサインインしたとき、またはユーザーが手動でデバイスを登録するときに、HoloLens デバイスを自動的に登録するように MDM システムを構成できます。 また、デバイスは Azure AD ドメインに参加し、適切なグループに割り当てられている必要があります。

デバイスを登録する方法の詳細については、「 [Windows デバイスの MDM と Intune の登録方法](/mem/intune/enrollment/windows-enrollment-methods)[に HoloLens を登録](hololens-enroll-mdm.md)する」を参照してください。

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM、手順 2 &ndash; キオスク構成プロファイルの作成

1. [Azure](https://portal.azure.com/) portal を開き、Intune 管理者アカウントにサインインします。
1. **Microsoft Intune**  >  **デバイスの構成-プロファイルの**  >  **作成プロファイル**] を選択します。
1. プロファイル名を入力してください。
1. [ **Platform**  >  **Windows 10 以降**] を選択し、[**プロファイルの種類**] [デバイスの制限] を選択し  > ます。
1. [ **Configure**  >  **キオスク**] を選択し、次のいずれかを選択します。
   - シングルアプリキオスクを作成するには、[**キオスクモード**  >  **シングルアプリキオスク**] を選択します。
   - マルチアプリキオスクを作成するには、[**キオスクモード**  >  **マルチアプリキオスク**] を選択します。
1. キオスクの構成を開始するには、[ **追加**] を選択します。

次の手順は、必要なキオスクの種類によって異なります。 詳細については、次のいずれかのオプションを選択してください。  

- [シングルアプリキオスク](#mdmconfigsingle)
- [マルチ アプリ キオスク](#mdmconfigmulti)

キオスク構成プロファイルを作成する方法の詳細については、「 [Intune を使用して専用キオスクとして実行するデバイス設定の Windows 10 と Windows Holographic for Business](/intune/configuration/kiosk-settings)」を参照してください。

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM、ステップ 3 (単一アプリ) &ndash;  シングルアプリキオスクの設定を構成する

このセクションでは、シングルアプリキオスクで必要な設定の概要を示します。 詳細については、次の記事を参照してください。

- Intune でキオスク構成プロファイルを構成する方法の詳細については、「 [Microsoft Intune を使用してキオスクモードを構成する方法](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)」を参照してください。
- Intune でのシングルアプリキオスクに使用できる設定の詳細については、「[シングルスクリーンアプリキオスク](/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)」を参照してください。
- その他の MDM サービスについては、使用しているプロバイダーのドキュメントで手順を参照してください。 カスタム XML 構成を使用して、MDM サービスでキオスクを設定する必要がある場合は、 [キオスク構成を定義する xml ファイルを作成](#ppkioskconfig)します。

1. [**ユーザーログオンの種類**] [  >  **ローカルユーザーアカウント**] を選択し、キオスクにサインインできるローカル (デバイス) アカウントまたは Microsoft アカウント (MSA) のユーザー名を入力します。
   > [!NOTE]  
   > **[自動ログオン]** というユーザー アカウントの種類は、Windows Holographic for Business ではサポートされていません。
1. [**アプリケーションの種類** ストアアプリ] を選択し、  >  一覧からアプリを選択します。

次の手順では、プロファイルをグループに [割り当て](#mdmassign) ます。

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM、ステップ 3 (マルチアプリ) &ndash; マルチアプリキオスクの設定を構成する

このセクションでは、マルチアプリキオスクで必要な設定の概要を示します。 詳細については、次の各記事を参照してください。

- Intune でキオスク構成プロファイルを構成する方法の詳細については、「 [Microsoft Intune を使用してキオスクモードを構成する方法](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)」を参照してください。
- Intune のマルチアプリキオスクで使用可能な設定の詳細については、「[マルチアプリキオスク](/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)」を参照してください。
- その他の MDM サービスについては、使用しているプロバイダーのドキュメントで手順を参照してください。 カスタム XML 構成を使用して、MDM サービスでキオスクを設定する必要がある場合は、 [キオスク構成を定義する xml ファイルを作成](#ppkioskconfig)します。 XML ファイルを使用する場合は、必ず [開始レイアウト](#start-layout-for-hololens)を含めてください。  
- 必要に応じて、Intune またはその他の MDM サービスでカスタムのスタートレイアウトを使用することもできます。 詳細については、「 [MDM のレイアウトファイルの開始 (Intune など)](#start-layout-file-for-mdm-intune-and-others)」を参照してください。

1. **S モードデバイスで [ターゲット Windows 10**] を選択し  >  ます。  
>[!NOTE]  
> S モードは、Windows Holographic for Business ではサポートされていません。

1. ユーザー   >  **またはグループ** または **ユーザーのログオン** の種類 HoloLens ビジターに Azure AD ユーザーログオンの種類を選択し、  >  1 つまたは複数のユーザーグループまたはアカウントを追加します。  

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

この時点でキオスクの構成が表示されない場合は、 [割り当ての状態を確認](/intune/configuration/device-profile-monitor)してください。

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM、手順 5 (マルチアプリ) に &ndash; よるマルチアプリキオスクのデプロイ

MDM システムを使用する場合、デバイスを Azure AD テナントに参加させ、OOBE 中にデバイスを MDM に登録できます。 必要に応じて、OOBE プロセス中に使用できるように、登録情報をユーザーに提供します。

> [!NOTE]  
> キオスク構成プロファイルをユーザーが含まれているグループに割り当てた場合は、これらのユーザーアカウントのいずれかが、デバイスにサインインするための最初のアカウントであることを確認してください。

OOBE 中に、次の手順を実行します。

1. **ユーザーログオンの種類** のグループに属するアカウントを使用してサインインします。
1. デバイスを登録します。
1. キオスク構成プロファイルに含まれるすべてのアプリがダウンロードされ、インストールされるまで待ちます。 また、ポリシーが適用されるまで待機します。  
1. OOBE が終了したら、Microsoft ストアまたはサイドローディングから追加のアプリをインストールできます。 デバイスが属しているグループに[必要なアプリ](/mem/intune/apps/apps-deploy#assign-an-app)が自動的にインストールされます。
1. インストールが完了したら、デバイスを再起動します。

次に **ユーザーログオンの種類** に属するアカウントを使用してデバイスにサインインすると、キオスクアプリが自動的に起動します。

この時点でキオスクの構成が表示されない場合は、 [割り当ての状態を確認](/intune/configuration/device-profile-monitor)してください。

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>プロビジョニングパッケージを使用してシングルアプリまたはマルチアプリキオスクを設定する

プロビジョニングパッケージを使用してキオスクモードを設定するには、次の手順に従います。

1. [キオスク構成を定義する XML ファイルを作成します。](#ppkioskconfig)これには、 [スタートレイアウト](#start-layout-for-hololens)も含まれます。
2. [プロビジョニングパッケージに XML ファイルを追加します。](#ppconfigadd)
3. [プロビジョニングパッケージを HoloLens に適用します。](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>プロビジョニングパッケージ、手順 1 &ndash; キオスク構成 XML ファイルを作成する

次の場合を除き、[一般的な手順に従って Windows desktop のキオスク構成 XML ファイルを作成](/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)します。

- クラシック Windows アプリケーション (Win32) を含めないでください。 HoloLens は、これらのアプリケーションをサポートしていません。
- プレースホルダーの [ [Start LAYOUT XML](#start-layout-for-hololens) for HoloLens を使用します。
- オプション: キオスク構成にゲストアクセスを追加する

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>オプション: キオスク構成にゲストアクセスを追加する

[  XML ファイルの構成セクション](/windows/configuration/lock-down-windows-10-to-specific-apps#configs)では、ゲストがキオスクを使用できるように、**ビジター** という名前の特別なグループを構成できます。 **訪問** 者の特別なグループをサポートするようにキオスクが構成されている場合、サインインページに "**ゲスト**" オプションが追加されます。 **Guest** アカウントにはパスワードは必要ありません。アカウントに関連付けられているデータは、アカウントのサインアウト時に削除されます。

**ゲスト** アカウントを有効にするには、次のスニペットをキオスク構成 XML に追加します。

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```
#### <a name="enable-visitor-autologon"></a>ビジター自動ログオンを有効にする

ビルド時[Windows Holographic、バージョン 21h1](hololens-release-notes.md#windows-holographic-version-21h1)以降:
- AAD と追加以外の構成では、キオスクモードに対して自動ログオンが有効になっているビジターアカウントがサポートされています。

##### <a name="non-aad-configuration"></a>AAD 以外の構成

1. 次のようなプロビジョニングパッケージを作成します。
    1. ユーザーアカウントを許可するようにランタイム設定/AssignedAccess を構成します。
    1. 必要に応じて、後で管理できるように MDM (ランタイム設定/ワークプレース/登録) にデバイスを登録します。
    1. ローカルアカウントを作成しない
2. [プロビジョニングパッケージを適用](hololens-provisioning.md)します。

##### <a name="aad-configuration"></a>AAD の構成

キオスクモード用に構成された AAD 参加済みデバイスは、サインイン画面からボタンを1回タップするだけで、ビジターアカウントにサインインできます。 ビジターアカウントにサインインすると、ユーザーが [スタート] メニューから明示的にサインアウトするか、デバイスが再起動されるまで、もう一度サインインするように求められることはありません。

ビジター自動ログオンは、 [カスタム oma-uri ポリシー](/mem/intune/configuration/custom-settings-windows-10)を使用して管理できます。

- URI 値:./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon


| ポリシー |[説明] |構成 
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | 訪問者がキオスクに自動ログオンすることを許可します。 | 1 (はい)、0 (いいえ、既定値) |

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>HoloLens のプレースホルダーの開始レイアウト

[プロビジョニングパッケージ](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)を使用してマルチアプリキオスクを構成する場合、この手順にはスタートレイアウトが必要です。 Windows Holographic for Business では、レイアウトのカスタマイズはサポートされていません。 そのため、プレースホルダーのスタートレイアウトを使用する必要があります。

> [!NOTE]  
> シングルアプリキオスクは、ユーザーがサインインしたときにキオスクアプリを開始するため、スタートメニューを使用せず、スタートレイアウトを設定する必要はありません。

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
1. [ **Windows 10 Holographic**] を選択し、[**次へ**] を選択します。
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

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>プロビジョニングパッケージ、ステップ 3 &ndash; プロビジョニングパッケージを HoloLens に適用します

「プロビジョニングパッケージを使用した HoloLens の構成」の記事では、次の状況でプロビジョニングパッケージを適用するための詳細な手順について説明しています。

- 初期[設定では、セットアップ中に HoloLens にプロビジョニングパッケージを適用](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)できます。

- [セットアップ後に HoloLens にプロビジョニングパッケージを適用](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)することもできます。

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>Windows デバイスポータルを使用してシングルアプリキオスクをセットアップする

Windows デバイスポータルを使用してキオスクモードを設定するには、次の手順に従います。

1. [Windows デバイスポータルを使用するように HoloLens デバイスを設定](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)します。 デバイス ポータルは、お使いの PC に Web ブラウザーから接続することができる HoloLens 上の Web サーバーです。

    > [!CAUTION]
    > デバイスポータルを使用するように HoloLens を設定する場合は、デバイスで開発者モードを有効にする必要があります。 Windows Holographic for Business があるデバイスの開発者モードでは、アプリをサイドロードすることができます。 ただし、この設定により、Microsoft Store によって認定されていないアプリをユーザーがインストールできる危険性が生じます。 管理者は、[ポリシー CSP](/windows/client-management/mdm/policy-configuration-service-provider)の **Applicationmanagement/allowdeveloper Unlock** 設定を使用して、開発者モードを有効にする機能をブロックできます。 [開発者モードの詳細をご覧ください。](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. コンピューターで[、Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi)または USB HoloLensデバイスに接続[します](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)。

1. 次のいずれかの操作を行います。
   - デバイスに初めて接続するWindows デバイス ポータル、ユーザー[名とパスワードを作成します](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - 前に設定したユーザー名とパスワードを入力します。

    > [!TIP]
    > ブラウザーに証明書エラーが表示された場合は、[こちらのトラブルシューティング手順](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)に従います。

1. [キオスク モード] Windows デバイス ポータル[キオスク モード]**を選択します**。

1. [ **キオスク モードを有効にする**] を選択し、デバイスの起動時に実行するアプリを選択してから、[保存] を **選択します**。

    ![キオスク モード](images/kiosk.png)
1. 再起動HoloLens。 このページを開いたデバイス ポータル、ページの上部にある **[再起動** ] を選択できます。

> [!NOTE]
> キオスク モードは、必要なクエリ文字列パラメーター ("kioskModeEnabled&quot; の値が &quot;true&quot; または &quot;false") とオプションのパラメーター (パッケージ名の値が "startupApp" ) を 1 つ指定して、/api/holographic/kioskmode/settings に POST を実行することで、デバイス ポータル の REST API を介して設定できます。 この機能は開発者デバイス ポータルのみを対象とし、開発者以外のデバイスでは有効にしなける必要があるという注意が必要です。 このREST API、今後の更新/リリースで変更される可能性があります。

## <a name="more-information"></a>詳細情報

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>プロビジョニング パッケージを使用してキオスクを構成する方法を見る。  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>グローバル割り当てアクセス – キオスク モード
- システム レベルでキオスク モードを適用する新しいキオスク 方法を有効にすることで、キオスクの ID 管理を減らしました。

この新機能により、IT 管理者は、システム レベルで適用可能な複数のアプリ キオスク モード用に HoloLens 2 デバイスを構成できます。システム上の ID とのアフィニティは持たず、デバイスにサインインするすべてのユーザーに適用されます。 この新しい[HoloLensの詳細については、](hololens-global-assigned-access-kiosk.md)グローバル割り当てアクセス キオスクのドキュメントを参照してください。

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>複数アプリキオスク モードでのアプリケーションの自動起動 
- アプリの自動起動に重点を置いてエクスペリエンスを向上し、キオスク モード エクスペリエンス用に選択された UI とアプリの選択をさらに増やします。

複数アプリキオスク モードにのみ適用され、割り当て済みアクセス構成で以下の強調表示された属性を使用して、1 つのアプリのみを自動起動に指定できます。 

ユーザーがサインインすると、アプリケーションが自動的に起動されます。 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>エラー処理のためのキオスク モードの動作の変更
キオスク モードの適用でエラーが発生すると、次の動作が表示されます。

- Holographic Windowsより前のバージョン 20H2 - HoloLens では、すべてのアプリケーションが スタート メニュー。
- WindowsHolographic バージョン 20H2 - デバイスに、グローバル割り当てアクセスと AAD グループ メンバー割り当てアクセスの両方の組み合わせであるキオスク構成がある場合、AAD グループ メンバーシップの決定に失敗した場合、ユーザーには [スタート画面に何も表示されません] メニューが表示されます。

![失敗したときのキオスク モードの画像。](images/hololens-kiosk-failure-behavior.png )


- [Holographic バージョン 21H1 Windows、](hololens-release-notes.md#windows-holographic-version-21h1)キオスク モードでは、空のスタート メニューが表示される前にグローバル割り当てアクセスが検索されます。 キオスク エクスペリエンスは、AAD グループ キオスク モード中に障害が発生した場合に、グローバル キオスク構成 (存在する場合) にフォールバックします。

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>オフライン キオスクAzure ADグループ メンバーシップをキャッシュする

- キオスク モードのエラーで使用可能なアプリを排除することで、より安全なキオスク モード。
- 最大 60 日間、オフライン キオスクAzure ADグループで使用できます。

このポリシーでは、サインインしたユーザーの Azure AD グループを対象とする割り当てアクセス構成に対して、Azure AD グループ メンバーシップ キャッシュを使用できる日数を制御します。 このポリシー値が 0 より大きい値にのみ設定されている場合は、キャッシュが使用されます。それ以外の場合は使用されません。  

名前: AADGroupMembershipCacheValidityInDays URI 値: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最小 - 0 日  
最大 - 60 日 

このポリシーを正しく使用する手順: 
1. デバイス グループを対象とするキオスク用のデバイス構成プロファイルAzure ADし、デバイスに割HoloLens割り当てる。 
1. このポリシー値を必要な日数 (> 0) に設定し、それを HoloLens デバイスに割り当てるカスタム OMA URI ベースのデバイス構成を作成します。 
    1. URI の値は、./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays として OMA-URI テキスト ボックスに入力する必要があります。
    1. 値は、min または max allowed の間で指定できます。
1. デバイスHoloLens登録し、両方の構成がデバイスに適用されるのを確認します。 
1. インターネットAzure ADユーザー 1 のサインインを許可し、ユーザーがサインインし、Azure AD グループ メンバーシップが正常に確認されると、キャッシュが作成されます。 
1. これでAzure ADユーザー 1 は、ポリシー値で X HoloLensできる限り、オフラインにし、キオスク モードで使用できます。 
1. 手順 4 と 5 は、他の Azure AD ユーザー N に対して繰り返し実行できます。ここで重要な点は、すべての Azure AD ユーザーがインターネットを使用してデバイスにサインインする必要がある点です。少なくとも 1 回は、キオスク構成の対象となる Azure AD グループのメンバーと判断できます。 
 
> [!NOTE]
> 手順 4. が実行されるまで、ユーザー Azure AD"切断" 環境で説明されているエラー動作が発生します。 


## <a name="xml-kiosk-code-samples-for-hololens"></a>XML キオスク コード サンプル (HoloLens

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>1 つのグループを対象とする複数Azure AD モード。 
このキオスクは、Azure AD グループ内のユーザーに対して、設定、Remote Assist、フィードバック Hub の 3 つのアプリを含むキオスクを有効にするキオスクを展開します。 このサンプルをすぐに使用するために変更するには、以下で強調表示されている GUID を独自のグループのAzure AD変更してください。 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>アカウントを対象とする複数Azure AD キオスク モード。
このキオスクは、1 人のユーザーにキオスクを展開します。キオスクは、設定、Remote Assist、フィードバック Hub の 3 つのアプリを含むキオスクを有効にします。 このサンプルをすぐに使用するために変更するには、以下で強調表示されているアカウントを自分のアカウントのAzure AD変更してください。 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

