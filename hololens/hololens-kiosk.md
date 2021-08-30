---
title: HoloLens をキオスクとしてセットアップする
description: キオスク構成を設定して使用し、HoloLens デバイス上のアプリをロックダウンする方法について説明します。
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f717a0323d1b141423fab52e49a38407ba617d02
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189343"
---
# <a name="set-up-hololens-as-a-kiosk"></a>HoloLens をキオスクとしてセットアップする

## <a name="what-is-kiosk-mode"></a>キオスクモードとは

キオスクモードは、ユーザーが HoloLens にサインインしたときに、[スタート] メニューに表示されるアプリケーションを制御できるようにする機能です。 2つのシナリオがサポートされています。

1. **シングルアプリキオスクモード** – [スタート] メニューは表示されず、ユーザーがサインインすると、1つのアプリが自動的に起動します。 <br> *使用例*: Dynamics 365 Guides アプリのみを実行するデバイス。
2. **複数のアプリキオスクモード**–スタートメニューは、ユーザーがサインインしたときにキオスク構成で指定されたアプリケーションのみを表示します。 必要に応じて、アプリを自動的に起動するように選択できます。 <br> *使用例*: [スタート] メニューには、ストアアプリ、フィードバックハブ、および設定アプリのみを表示するデバイスです。

    <img alt="Multi app kiosk example" src=".\images\multi-app-kiosk.jpg" width="411" height="500" />

## <a name="description-of-kiosk-mode-experience-when-a-user-signs-in"></a>ユーザーがサインインしたときのキオスクモードエクスペリエンスの説明

次の表に、各種キオスクモードの機能の一覧を示します。

| &nbsp; |[スタート] メニュー |クイックアクションメニュー |カメラとビデオ |Miracast |Cortana |組み込みの音声コマンド |
| --- | --- | --- | --- | --- | --- | --- |
|シングルアプリキオスク |無効 |無効 |無効 |無効   |無効 |Enabled |
|マルチ アプリ キオスク |Enabled |Enabled  |ご  |ご |ご   |Enabled  |

\*無効な機能を有効にする方法、または音声コマンドが無効な機能と対話する方法の詳細については Cortana 「 [HoloLens AUMIDs for apps](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)」を参照してください。

## <a name="key-general-considerations-before-configuring-kiosk-mode"></a>キオスクモードを構成する前の主な注意事項

1. 環境内の HoloLens にサインインするユーザーアカウントの種類を決定する-HoloLens Azure Active Directory (AAD) アカウント、Microsoft アカウント (MSA)、およびローカルアカウントをサポートします。 さらに、ゲスト/訪問者と呼ばれるアカウントも一時的に作成されています (AAD 参加デバイスの場合のみ)。 詳細について[は、「HoloLens のユーザー id とサインインの管理」](hololens-identity.md)を参照してください。
2. キオスクモードのエクスペリエンスの対象を決定します。これは、すべてのユーザー、1人のユーザー、特定のユーザー、または AAD グループのメンバーであるユーザーです。
3. 複数のアプリキオスクモードの場合は、[スタート] メニューに表示するアプリケーションを決定します。 アプリケーションごとに、 [アプリケーションユーザーモデル ID (AUMID)](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) が必要になります。
4. キオスクモードをランタイムプロビジョニングパッケージまたはモバイルデバイス管理 (MDM) サーバーを使用して HoloLens に適用するかどうかを決定します。

## <a name="security-considerations"></a>セキュリティに関する考慮事項

キオスクモードは、ユーザーのサインイン時に起動エクスペリエンスを制御する手段として、セキュリティメソッドとは見なさないでください。 特定のセキュリティ関連のニーズがある場合は、キオスクモードのエクスペリエンスを以下で説明するオプションと組み合わせることができます。

- 設定アプリがキオスクモードで表示するように構成されていて、設定アプリに表示されるページを制御する場合は、[ページ設定表示](settings-uri-list.md)を参照してください
- 特定のアプリの特定のハードウェア機能 (カメラ、Bluetooth など) へのアクセスを制御する必要がある場合は、 [HoloLens 2 Windows のクライアント管理でサポートされているポリシー CSP のポリシー](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2)を参照してください。 [一般的なデバイスの制限事項](hololens-common-device-restrictions.md)については、「」を参照してください。
- キオスクモードでは、他のアプリの起動から、(キオスクエクスペリエンスの一部として構成されている) アプリをブロックすることはできません。 HoloLens 上の特定のアプリ/プロセスの起動を完全にブロックする場合は、「 [Microsoft Intune の HoloLens 2 デバイスで Windows Defender アプリケーション制御を使用する」](/mem/intune/configuration/custom-profile-hololens)を参照してください。

## <a name="key-technical-considerations-for-kiosk-mode-for-hololens"></a>HoloLens のキオスクモードに関する主要な技術的考慮事項

ランタイムプロビジョニングパッケージを使用する予定がある場合、または手動でキオスク構成を作成する場合にのみ適用されます。 キオスクモードの構成では、XML に基づく階層構造を使用します。

- 割り当てられたアクセスプロファイルは、キオスクモードの [スタート] メニューに表示されるアプリケーションを定義します。 同じ XML 構造で複数のプロファイルを定義して、後で参照することができます。
- 割り当てられたアクセス構成は、特定のユーザー、AAD グループ、訪問者などのプロファイルと対象ユーザーを参照します。使用シナリオの複雑さに応じて、同じ XML 構造で複数の構成を定義できます (以下の「サポートされるシナリオ」セクションを参照してください)。
- 詳細については、「 [ASSIGNEDACCESS CSP](/windows/client-management/mdm/assignedaccess-csp)」を参照してください。

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>Id の種類に基づくキオスクモードのサポートされているシナリオ

コピー/貼り付けを行う前に、シナリオに基づいてサンプルの [参照リンク](hololens-kiosk-reference.md#kiosk-xml-code-samples) を参照し、必要に応じて更新してください。

> [!NOTE]
> Intune の UI を使用してキオスク構成を作成しない場合にのみ、XML を使用します。

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>ローカルアカウントまたは MSA としてサインインしているユーザーの場合

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Prov. パッケージ、手順 2. &ndash; キオスク構成 XML ファイルをプロビジョニングパッケージに追加する

1. [Windows 構成デザイナー](https://www.microsoft.com/store/apps/9nblggh4tx22)を開きます。
1. [ **高度なプロビジョニング**] を選択し、プロジェクトの名前を入力して、[ **次へ**] を選択します。
1. [ **Windows 10 Holographic**] を選択し、[**次へ**] を選択します。
1. **[完了]** を選択します。 パッケージのワークスペースが開きます。
1. [**ランタイム設定**  >  **AssignedAccess** MultiAppAssignedAccessSettings] を選択し  >  ます。
1. 中央のウィンドウで、[ **参照** ] を選択して、作成したキオスク構成 XML ファイルを見つけて選択します。

   ![Windows 構成デザイナーの MultiAppAssignedAccessSettings フィールドのスクリーンショット。](./images/multiappassignedaccesssettings.png)
| **必要なキオスクエクスペリエンス** | **推奨されるキオスク構成** | **構成方法**  | **解説** |
| --- | --- | --- | --- |
| サインインするすべてのユーザーがキオスクエクスペリエンスを取得します。 | [複数のアプリのグローバルに割り当てられたアクセスプロファイルの構成](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | •[カスタムテンプレートの Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [ランタイムプロビジョニング-マルチアプリ](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | グローバルに割り当てられたアクセスには[、20H2 以降のビルド](hololens-release-notes.md#windows-holographic-version-20h2)が必要です |
| サインインする特定のユーザーがキオスクエクスペリエンスを取得します。  | [特定のユーザーの名前を指定して、1つまたは複数のアプリ割り当てアクセスプロファイルを (必要に応じて) 構成します。](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [以下のサポートされているオプションを参照してください。](#steps-in-configuring-kiosk-mode-for-hololens) | シングルアプリキオスクモードの場合、HoloLens ではローカルユーザーアカウントまたは MSA アカウントのみがサポートされます。 <br> 複数のアプリキオスクモードでは、HoloLens では MSA アカウントまたは AAD アカウントのみがサポートされています。 |

### <a name="for-users-who-sign-in-as-aad-account"></a>AAD アカウントとしてサインインしているユーザーの場合

| **必要なキオスクエクスペリエンス** | **推奨されるキオスク構成** | **構成方法** | **解説** |
| --- | --- | --- | --- |
| サインインするすべてのユーザーがキオスクエクスペリエンスを取得します。 | [複数のアプリのグローバルに割り当てられたアクセスプロファイルの構成](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | •[カスタムテンプレートの Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [ランタイムプロビジョニング-マルチアプリ](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | グローバルに割り当てられたアクセスには[、20H2 以降のビルド](hololens-release-notes.md#windows-holographic-version-20h2)が必要です |
| サインインするすべてのユーザーは、特定のユーザーを除き、キオスクエクスペリエンスを利用できます。 | [特定のユーザー (デバイスの所有者である必要があります) を除外することで、複数のアプリのグローバルに割り当てられたアクセスプロファイルを構成](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners)します。 | •[カスタムテンプレートの Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [ランタイムプロビジョニング-マルチアプリ](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | グローバルに割り当てられたアクセスには[、20H2 以降のビルド](hololens-release-notes.md#windows-holographic-version-20h2)が必要です |
| すべての AAD ユーザーは、そのユーザーに固有の個別のキオスク エクスペリエンスを取得します。 | [AAD アカウント名を指定して、各ユーザーに割り当てられたアクセス構成を構成します。](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [Microsoft Intune テンプレート](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [ランタイム プロビジョニング - マルチ アプリ](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| 別の AAD グループのユーザーには、グループ専用のキオスク モードが表示されます。 | [必要な AAD グループごとに割り当てられたアクセス構成を構成します。](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [Microsoft Intune テンプレート](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [ランタイム プロビジョニング - マルチ アプリ](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | • ユーザーがサインインし、HoloLens がインターネットに接続されている場合、そのユーザーがキオスク構成が存在する AAD グループのメンバーである場合、ユーザーは、その AAD グループのキオスクを体験します。 <br> •[ユーザーのサインイン時にインターネット](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode)を使用できない場合、ユーザーはHoloLens動作を発生します。 <br> • ユーザーがサインインし、AAD グループ ベースのキオスクを使用する必要があるときにインターネットの可用性が保証されない場合は [、AADGroupMembershipCacheValidityInDayspolicy](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)の使用を検討してください。 |
| 一時的な目的でHoloLensを使用する必要があるユーザーは、キオスク エクスペリエンスを利用できます。 | [訪問者の割り当て済みアクセス構成を構成する](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | • [Microsoft Intune テンプレート](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [ランタイム プロビジョニング - 単一アプリ](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | • 一時ユーザー アカウントは、サインイン時HoloLensによって自動的に作成され、一時ユーザーがサインアウトすると削除されます。 <br> • ビジターの自動ログイン [ポリシー を有効にしてください](#how-can-visitor-accounts-automatically-logon-to-kiosk-experience)。 |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>デバイスのキオスク モードを構成するHoloLens

キオスク構成は、次の方法で作成および適用できます。

1. MDM サーバーの UI (Intune のキオスク テンプレートやカスタム OMA-URI 構成など) を使用すると、リモートで HoloLens に適用されます。
2. ランタイム プロビジョニング パッケージを使用すると、パッケージに直接適用HoloLens。

次の構成方法を示します。使用するプロセスに一致するタブを選択します。

1. [Microsoft Intune シングル アプリ キオスク テンプレートの作成](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [Microsoft Intune マルチ アプリ キオスク テンプレート](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Microsoft Intune テンプレートを作成する](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [ランタイム プロビジョニング - マルチ アプリ](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [ランタイム プロビジョニング - 単一アプリ](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

[!INCLUDE[](includes/kiosk-configure-steps.md)]

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="how-can-visitor-accounts-automatically-logon-to-kiosk-experience"></a>訪問者アカウントをキオスク エクスペリエンスに自動的にログオンする方法

[Holographic Windowsバージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1)以降のビルドの場合:

- AAD 構成と非追加構成はどちらも、キオスク モードで自動ログオンが有効になっているビジター アカウントをサポートします。

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>キオスク エクスペリエンスは、HoloLens (第 1 世代) でサポートされていますか?

キオスク モードは、デバイスにデバイスがインストールされているWindows Holographic for Business。 すべてのHoloLens 2デバイスは Windows Holographic for Businessに出荷され、他のエディションはありません。 すべてのHoloLens 2デバイスは、キオスク モードを一から実行できます。

HoloLens (第 1 世代) デバイスは、OS ビルドと OS エディションの両方でアップグレードする必要があります。 次に示すのは、HoloLens (第 1 世代) を新しいエディション[に更新Windows Holographic for Business](hololens1-upgrade-enterprise.md)です。 HoloLens (第 1 世代) デバイスを更新してキオスク モードを使用するには、まず、デバイスが Windows 10 バージョン 1803 以降のバージョンを実行している必要があります。 Windows Device Recovery Tool を使用して HoloLens (第 1 世代) デバイスを既定のビルドに回復した場合、または最新の更新プログラムをインストールした場合は、デバイスを構成する準備ができています。

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>デバイス ポータルを使用して非実稼働環境でキオスクを構成する方法

を使用[HoloLensデバイスを設定Windows デバイス ポータル。](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) デバイス ポータルは、お使いの PC に Web ブラウザーから接続することができる HoloLens 上の Web サーバーです。

 > [!CAUTION]
 > アプリケーションを使用HoloLens設定デバイス ポータルデバイスで開発者モードを有効にする必要があります。 アプリがインストールされているデバイスの開発者モードWindows Holographic for Businessアプリをサイドロードできます。 ただし、この設定により、ユーザーがアプリの認定を受けしていないアプリをインストールMicrosoft Store。 管理者は、ポリシー CSP の **ApplicationManagement/AllowDeveloper Unlock** 設定を使用して、開発者モードを有効にする機能を [ブロックできます](/windows/client-management/mdm/policy-configuration-service-provider)。 [開発者モードの詳細をご覧ください。](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

キオスク モードは、必要なクエリ文字列パラメーター ("kioskModeEnabled" の値が "true" または "false" の場合) とオプションのパラメーター (パッケージ名の値が "startupApp" ) を 1 つ指定して、/api/holographic/kioskmode/settings に POST を実行することで、デバイス ポータル の REST API を介して設定できます。 この機能はデバイス ポータル開発者のみを対象とし、開発者以外のデバイスでは有効にしなける必要があるという念頭に置いておきます。 このREST API、今後の更新/リリースで変更される可能性があります。

## <a name="troubleshooting"></a>トラブルシューティング

### <a name="issue---no-apps-are-shown-in-start-menu-in-kiosk-mode"></a>問題 - キオスク モードの [スタート] メニューにアプリが表示されません

**現象**

キオスク モードの適用でエラーが発生すると、次の動作が表示されます。

- Holographic Windowsより前のバージョン 20H2 - HoloLens では、すべてのアプリケーションが スタート メニュー。
- WindowsHolographic バージョン 20H2 - デバイスにキオスク構成 (グローバル割り当てアクセスと AAD グループ メンバー割り当てアクセスの両方の組み合わせ) がある場合、AAD グループ メンバーシップの決定に失敗した場合、ユーザーには "何も表示されません" メニューが表示されます。

    ![失敗したときのキオスク モードの画像。](images/hololens-kiosk-failure-behavior.png )

- [Holographic バージョン 21H1 Windows、](hololens-release-notes.md#windows-holographic-version-21h1)キオスク モードでは、空のスタート メニューが表示される前にグローバル割り当てアクセスが検索されます。 AAD グループ キオスク モード中にエラーが発生した場合、キオスク エクスペリエンスはグローバル キオスク構成 (存在する場合) に戻ります。

**トラブルシューティングの手順**

- アプリの AUMID が正しく指定され、バージョンが含まれているのを確認します。 例についてはHoloLens受信トレイ アプリの[AUMID](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)に関するページを参照してください。
- そのユーザーのデバイスにアプリケーションがインストールされていることを確認します。
- キオスクの構成が AAD グループに基づく場合は、AAD ユーザーがサインインするときにインターネット接続が存在する必要があります。 必要に応じて [MixedReality/AADGroupMembershipCacheValidityInDays](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-aadgroupmembershipcachevalidityindays) ポリシーを構成し、インターネットなしでも機能します。

### <a name="issue---building-a-package-with-kiosk-mode-failed"></a>問題 - キオスク モードでパッケージを構築できなかった

**現象**

次のようなダイアログが表示されます。

<kbd>
    <img alt="Kiosk failure to build" src="./images/kiosk-steps/kiosk-ppkg-failure.png"/>
</kbd>

**トラブルシューティングの手順**

1. 上のダイアログに示されているハイパーリンクをクリックします。
1. テキスト エディターで ICD.log を開きます。その内容はエラーを示すはずです。

> [!NOTE]
> いくつかの試行を行った場合は、ログのタイム スタンプを確認します。 これは、現在の問題のみを確認するのに役立ちます。

### <a name="issue--provisioning-package-built-successfully-but-failed-to-apply"></a>問題 – プロビジョニング パッケージは正常にビルドされましたが、適用に失敗しました。

**現象**

Hololens にプロビジョニング パッケージを適用するとエラーが表示される

**トラブルシューティングの手順**

1. ランタイム プロビジョニング パッケージの構成Windowsプロジェクトが存在するフォルダーを参照します。
1. ICD.log を開き、プロビジョニング パッケージの構築中にログにエラーが発生していないか確認します。 一部のエラーはビルド中に表示されませんが、ICD.log に記録されます

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>問題 – AAD グループへの複数のアプリ割り当てアクセスが機能しない

**現象**

AAD ユーザーのサインイン時に、デバイスがキオスク モードに入らない

**トラブルシューティングの手順**

- [割り当て済みアクセス構成 XML] で、サインインしているユーザーが のメンバーである AAD グループの GUID が使用され、AAD ユーザーの GUID が使用されていないか確認します。
- Intune ポータルで、AAD ユーザーが実際に対象の AAD グループのメンバーとして表示されます。
