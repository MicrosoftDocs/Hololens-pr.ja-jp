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
ms.openlocfilehash: e8f269a3793a5e61eb3eb4b88084a5e4af375ffa
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351721"
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

1. 環境内の HoloLens にサインインするユーザーアカウントの種類を決定する-HoloLens Azure Active Directory (AAD) アカウント、Microsoft アカウント (MSA)、およびローカルアカウントをサポートします。 さらに、ゲスト/訪問者と呼ばれるアカウントも一時的に作成されています (AAD 参加デバイスのみ)。 詳細について[は、「HoloLens のユーザー id とサインインの管理」](hololens-identity.md)を参照してください。
2. キオスクモードのエクスペリエンスの対象を決定します。これには、すべてのユーザー、1人のユーザー、特定のユーザー、または AAD グループのメンバーであるユーザーなどがあります。
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
- 割り当てられたアクセス構成は、特定のユーザー、AAD グループや訪問者などのプロファイルと対象ユーザーを参照します。使用シナリオの複雑さに応じて、同じ XML 構造で複数の構成を定義できます (以下の「サポートされるシナリオ」セクションを参照してください)。
- 詳細については、「 [ASSIGNEDACCESS CSP](/windows/client-management/mdm/assignedaccess-csp)」を参照してください。

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>Id の種類に基づくキオスクモードのサポートされているシナリオ

コピー/貼り付けを行う前に、シナリオに基づいてサンプルの [参照リンク](hololens-kiosk-reference.md#kiosk-xml-code-samples) を参照し、必要に応じて更新してください。

> [!NOTE]
> Intune の UI を使用してキオスク構成を作成しない場合にのみ、XML を使用します。

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>ローカルアカウントまたは MSA としてサインインしているユーザーの場合

| **必要なキオスクエクスペリエンス** | **推奨されるキオスク構成** | **構成方法**  | **解説** |
| --- | --- | --- | --- |
| サインインするすべてのユーザーがキオスクエクスペリエンスを取得します。 | [複数のアプリのグローバルに割り当てられたアクセスプロファイルの構成](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | •[カスタムテンプレートの Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [ランタイムプロビジョニング-マルチアプリ](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | グローバルに割り当てられたアクセスには[、20H2 以降のビルド](hololens-release-notes.md#windows-holographic-version-20h2)が必要です |
| サインインする特定のユーザーがキオスクエクスペリエンスを取得します。  | [特定のユーザーの名前を指定して、1つまたは複数のアプリ割り当てアクセスプロファイルを (必要に応じて) 構成します。](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [以下のサポートされているオプションを参照してください。](#steps-in-configuring-kiosk-mode-for-hololens) | シングルアプリキオスクモードの場合、HoloLens ではローカルユーザーアカウントまたは MSA アカウントのみがサポートされます。 <br> 複数のアプリキオスクモードでは、HoloLens では、MSA アカウントまたは AAD アカウントのみがサポートされます。 |

### <a name="for-users-who-sign-in-as-aad-account"></a>AAD アカウントとしてサインインしているユーザーの場合

| **必要なキオスクエクスペリエンス** | **推奨されるキオスク構成** | **構成方法** | **解説** |
| --- | --- | --- | --- |
| サインインするすべてのユーザーがキオスクエクスペリエンスを取得します。 | [複数のアプリのグローバルに割り当てられたアクセスプロファイルの構成](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | •[カスタムテンプレートの Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [ランタイムプロビジョニング-マルチアプリ](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | グローバルに割り当てられたアクセスには[、20H2 以降のビルド](hololens-release-notes.md#windows-holographic-version-20h2)が必要です |
| サインインするすべてのユーザーは、特定のユーザーを除き、キオスクエクスペリエンスを利用できます。 | [特定のユーザー (デバイスの所有者である必要があります) を除外することで、複数のアプリのグローバルに割り当てられたアクセスプロファイルを構成](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners)します。 | •[カスタムテンプレートの Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [ランタイムプロビジョニング-マルチアプリ](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | グローバルに割り当てられたアクセスには[、20H2 以降のビルド](hololens-release-notes.md#windows-holographic-version-20h2)が必要です |
| すべての AAD ユーザーは、そのユーザーに固有のキオスクエクスペリエンスを利用できます。 | [AAD アカウント名を指定して、各ユーザーの割り当てられたアクセス構成を構成します。](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | •[カスタムテンプレートの Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [ランタイムプロビジョニング-マルチアプリ](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| 異なる AAD グループのユーザーには、そのグループ専用のキオスクモードがあります。 | [目的の AAD グループごとに割り当てられたアクセス構成を構成します。](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | •[カスタムテンプレートの Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [ランタイムプロビジョニング-マルチアプリ](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | •ユーザーがサインインして HoloLens がインターネットに接続されている場合、そのユーザーがキオスク構成が存在する AAD グループのメンバーであることが判明すると、ユーザーはその AAD グループのキオスクを体験することができます。 <br> •[ユーザーのサインイン時にインターネットに接続できない場合、ユーザーは HoloLens エラーモードの動作を経験します。](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) <br> •ユーザーのサインインと AAD グループベースのキオスクを使用する必要がある場合、インターネットの可用性が保証されない場合は、 [AADGroupMembershipCacheValidityInDayspolicy の使用を検討](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)してください。 <br> •サインイン時に AAD グループで最適なエクスペリエンスを実現するには、 [AADGroupMembershipCacheValidityInDayspolicy](/hololens/hololens-release-notes#cache-azure-ad-group-membership-for-offline-kiosk)を使用することをお勧めします。 |
| 一時的な目的で HoloLens を使用する必要があるユーザーは、キオスクエクスペリエンスを利用できます。 | [訪問者の割り当て済みアクセス構成を構成する](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | •[カスタムテンプレートの Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [ランタイムプロビジョニング-単一アプリ](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | •一時ユーザーアカウントは、サインイン時に HoloLens によって自動的に作成され、一時ユーザーがサインアウトすると削除されます。 <br> •訪問者 [の自動ログインポリシー](#how-can-visitor-accounts-automatically-logon-to-kiosk-experience)を有効にすることを検討してください。 |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>HoloLens のキオスクモードを構成する手順

キオスクの構成は、次の方法で作成および適用できます。

1. MDM サーバーの UI を使用します。たとえば、Intune のキオスクテンプレートや、カスタム OMA-URI 構成を HoloLens にリモートで適用します。
2. ランタイムプロビジョニングパッケージを使用します。このパッケージは、HoloLens に直接適用されます。

次の方法でを構成し、使用するプロセスに一致するタブを選択します。

1. [Microsoft Intune シングル アプリ キオスク テンプレート](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [Microsoft Intune マルチ アプリ キオスク テンプレート](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Microsoft Intune カスタム テンプレート](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [ランタイム プロビジョニング - 複数アプリ](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [ランタイムプロビジョニング - 単一アプリ](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

[!INCLUDE[](includes/kiosk-configure-steps.md)]

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="how-can-visitor-accounts-automatically-logon-to-kiosk-experience"></a>訪問者アカウントがキオスクエクスペリエンスに自動的にログオンするにはどうすればよいですか。

ビルド時[Windows Holographic、バージョン 21h1](hololens-release-notes.md#windows-holographic-version-21h1)以降:

- AAD と追加以外の構成では、キオスクモードで自動ログオンが有効になっているビジターアカウントがサポートされています。

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>キオスクエクスペリエンスは HoloLens (第1世代) でサポートされていますか?

キオスクモードは、デバイスに Windows Holographic for Business がある場合にのみ使用できます。 すべての HoloLens 2 デバイスは Windows Holographic for Business に付属しており、他のエディションはありません。 すべての HoloLens 2 デバイスは、すぐに使えるキオスクモードを実行できます。

HoloLens (第1世代) デバイスは、os ビルドと os エディションの両方でアップグレードする必要があります。 HoloLens (第1世代) を[Windows Holographic for Business](hololens1-upgrade-enterprise.md)エディションに更新する方法については、こちらを参照してください。 キオスクモードを使用するように HoloLens (第1世代) デバイスを更新するには、まず、デバイスで Windows 10 バージョン1803以降のバージョンが実行されていることを確認する必要があります。 Windows デバイス回復ツールを使用して HoloLens (第1世代) デバイスを既定のビルドに回復した場合、または最新の更新プログラムをインストールした場合は、デバイスを構成する準備ができています。

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>デバイスポータルを使用して非運用環境でキオスクを構成する方法

[Windows デバイスポータルを使用するように HoloLens デバイス](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)を設定します。 デバイス ポータルは、お使いの PC に Web ブラウザーから接続することができる HoloLens 上の Web サーバーです。

 > [!CAUTION]
 > デバイスポータルを使用するように HoloLens を設定する場合は、デバイスで開発者モードを有効にする必要があります。 Windows Holographic for Business があるデバイスの開発者モードでは、アプリをサイドロードすることができます。 ただし、この設定により、Microsoft Store によって認定されていないアプリをユーザーがインストールできる危険性が生じます。 管理者は、[ポリシー CSP](/windows/client-management/mdm/policy-configuration-service-provider)の **Applicationmanagement/allowdeveloper Unlock** 設定を使用して、開発者モードを有効にする機能をブロックできます。 [開発者モードの詳細をご覧ください。](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

キオスクモードは、デバイスポータルの REST API を使用して設定できます。これを行うには、1つの必須クエリ文字列パラメーター ("kioskModeEnabled"、値 "true" または "false") と1つの省略可能なパラメーター (パッケージ名の値を持つ/api/holographic/kioskmode/settings) を指定します。 デバイスポータルは開発者向けのものであり、開発者以外のデバイスでは有効にしないでください。 REST API は、今後の更新プログラム/リリースで変更される可能性があります。

## <a name="troubleshooting"></a>トラブルシューティング

### <a name="issue---no-apps-are-shown-in-start-menu-in-kiosk-mode"></a>問題-キオスクモードのスタートメニューにアプリが表示されない

**現象**

キオスクモードの適用中にエラーが発生すると、次の動作が表示されます。

- Windows Holographic より前では、バージョン 20h2-HoloLens はスタートメニュー内のすべてのアプリケーションを表示します。
- WindowsHolographic、バージョン 20h2-デバイスにキオスク構成があり、グローバルに割り当てられたアクセスと AAD グループメンバーが割り当てられたアクセスの両方を組み合わせている場合、AAD グループのメンバーシップが失敗した場合、ユーザーには [スタート] メニューに表示されないものが表示されます。

    ![キオスクモードが失敗したときにどのように表示されるかを示した画像。](images/hololens-kiosk-failure-behavior.png )

- [Windows Holographic バージョン 21h1](hololens-release-notes.md#windows-holographic-version-21h1)以降では、キオスクモードでは、空の [スタート] メニューが表示される前に、グローバルに割り当てられたアクセスが検索されます。 AAD グループキオスクモード中にエラーが発生した場合、キオスクのエクスペリエンスはグローバルキオスク構成 (存在する場合) にフォールバックします。

**トラブルシューティングの手順**

- アプリの AUMID が正しく指定されており、バージョンが含まれていないことを確認します。 例については、「 [HoloLens AUMIDs](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) for inbox apps」を参照してください。
- そのユーザーのデバイスにアプリケーションがインストールされていることを確認します。
- キオスク構成が AAD グループに基づいている場合は、AAD ユーザーがサインインしたときにインターネット接続が存在することを確認してください。 必要に応じて、 [MixedReality/AADGroupMembershipCacheValidityInDays](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-aadgroupmembershipcachevalidityindays) ポリシーを構成して、インターネットがなくても機能できるようにします。

(ランタイムプロビジョニングまたは Intune カスタム OMA-URI URI を使用して) 割り当てられたアクセス構成を作成するために XML が使用されている場合は、XML が適切な形式であることを確認してください。そのためには、任意の web ブラウザーまたは XML エディターで xml を開きます。 整形式および有効なテンプレートについては、「 [キオスク XML コードサンプル](hololens-kiosk-reference.md#kiosk-xml-code-samples) 」を参照してください。

### <a name="issue---building-a-package-with-kiosk-mode-failed"></a>問題-キオスクモードでのパッケージのビルドに失敗しました

**現象**

次のようなダイアログが表示されます。

<kbd>
    <img alt="Kiosk failure to build" src="./images/kiosk-steps/kiosk-ppkg-failure.png"/>
</kbd>

**トラブルシューティングの手順**

1. 上のダイアログボックスに表示されているハイパーリンクをクリックします。
1. テキストエディターで ICD を開き、その内容がエラーを示す必要があります。

> [!NOTE]
> 複数回試行した場合は、ログのタイムスタンプを確認します。 これは、現在の問題のみを確認するのに役立ちます。

### <a name="issue--provisioning-package-built-successfully-but-failed-to-apply"></a>問題-プロビジョニングパッケージは正常にビルドされましたが、適用できませんでした。

**現象**

Hololens でプロビジョニングパッケージを適用するときにエラーが表示される

**トラブルシューティングの手順**

1. ランタイムプロビジョニングパッケージの Windows 構成デザイナープロジェクトが存在するフォルダーを参照します。
1. ICD .log を開き、プロビジョニングパッケージの作成中にログにエラーがないことを確認します。 一部のエラーはビルド中に表示されませんが、まだ ICD .log に記録されています

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>問題-AAD グループに対する複数のアプリ割り当てアクセスが機能しない

**現象**

AAD のユーザーサインインでは、デバイスは、期待されるキオスクモードに移行しません。

**トラブルシューティングの手順**

- [割り当てられたアクセス構成 XML] で、サインインしているユーザーがメンバーである AAD グループの guid が使用され、AAD ユーザーの guid ではないことを確認します。
- Intune ポータルで、AAD ユーザーが対象の AAD グループのメンバーとして実際に表示されていることを確認します。
- Intune の場合のみ、デバイスが準拠していると表示されていることを確認します。 詳細については、「 [デバイスのコンプライアンスリファレンス](/mem/intune/protect/device-compliance-get-started) 」を参照してください。
