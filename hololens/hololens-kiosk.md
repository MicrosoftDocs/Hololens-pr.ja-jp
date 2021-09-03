---
title: HoloLens をキオスクとしてセットアップする
description: キオスク構成を設定して使用して、デバイス上のアプリをロックダウンする方法HoloLensします。
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
ms.openlocfilehash: e856ac74e959743e8d05ea6acf583700a6450373
ms.sourcegitcommit: 37611ac0a4efaf69816a734e16b763c810655f1a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2021
ms.locfileid: "123411346"
---
# <a name="set-up-hololens-as-a-kiosk"></a>HoloLens をキオスクとしてセットアップする

## <a name="what-is-kiosk-mode"></a>キオスク モードとは

キオスク モードは、ユーザーがアプリにサインインするときに[スタート] メニューに表示されるアプリケーションを制御HoloLens。 次の 2 つのシナリオがサポートされています。

1. **シングル アプリ キオスク モード** – [スタート] メニューは表示されません。ユーザーがサインインすると、1 つのアプリが自動的に起動されます。 <br> *使用例*: アプリで実行されるデバイスDynamics 365 Guidesします。
2. **複数のアプリ** キオスク モード – スタート メニューユーザーがサインインするときにキオスク構成で指定されたアプリケーションのみを表示します。 必要に応じて、アプリを選択して自動的に起動できます。 <br> *使用例*: [スタート] メニューに [ストア] アプリ、フィードバック Hub、設定を表示するデバイス。

    <img alt="Multi app kiosk example" src=".\images\multi-app-kiosk.jpg" width="411" height="500" />

## <a name="description-of-kiosk-mode-experience-when-a-user-signs-in"></a>ユーザーがサインインした場合のキオスク モード エクスペリエンスの説明

次の表に、さまざまなキオスク モードの機能を示します。

| &nbsp; |[スタート] メニュー |[クイック アクション] メニュー |カメラとビデオ |Miracast |Cortana |組み込みの音声コマンド |
| --- | --- | --- | --- | --- | --- | --- |
|シングル アプリ キオスク |無効 |無効 |無効 |無効   |無効 |有効* |
|マルチ アプリ キオスク |Enabled |有効*  |利用可能*  |利用可能* |利用可能*   |有効*  |

\*無効な機能を有効にする方法、または音声コマンドが無効な機能と対話する方法の詳細については、「Cortana [AUMID](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)のHoloLensを参照してください。

## <a name="key-general-considerations-before-configuring-kiosk-mode"></a>キオスク モードを構成する前の主な一般的な考慮事項

1. 環境内の HoloLens にサインインするユーザー アカウントの種類を決定する - HoloLens では、Azure Active Directory (AAD) アカウント、Microsoft アカウント (MSA)、ローカル アカウントがサポートされます。 さらに、ゲスト/ビジターと呼ばれる一時的に作成されたアカウントもサポートされています (AAD 参加デバイスの場合のみ)。 詳細については、「ユーザー ID[とサインインの管理 」を参照HoloLens。](hololens-identity.md)
2. キオスク モード エクスペリエンスのターゲットを決定する – すべてのユーザー、1 人のユーザー、特定のユーザー、または AAD グループのメンバーであるユーザーなどです。
3. 複数のアプリ キオスク モードの場合は、スタート メニューに表示するアプリケーションを決定します。 アプリケーションごとに、その [アプリケーション ユーザー モデル ID (AUMID) が](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) 必要です。
4. ランタイム プロビジョニング パッケージまたは Mobile HoloLens (MDM) サーバーを使用して、キオスク モードがデバイス管理適用されるかどうかを決定します。

## <a name="security-considerations"></a>セキュリティに関する考慮事項

キオスク モードはセキュリティ方法と見なすのではなく、ユーザーのサインイン時の起動エクスペリエンスを制御する手段として考慮する必要があります。 特定のセキュリティ関連のニーズがある場合は、キオスク モードエクスペリエンスと以下に示すオプションを組み合わせて使用できます。

- アプリ設定キオスク モードで表示するように構成され、設定 アプリに表示されるページを制御する場合は、「ページの表示設定[参照してください](settings-uri-list.md)。
- 特定のアプリの特定のハードウェア機能 (カメラ、Bluetooth など) へのアクセスを制御する場合は[、「HoloLens 2 - Windows Client Management](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2)でサポートされるポリシー CSP のポリシー」を参照してください。 アイデアについては、デバイス [に関する一般的な](hololens-common-device-restrictions.md) 制限を確認できます。
- キオスク モードでは、(キオスク エクスペリエンスの一部として構成されている) アプリが他のアプリを起動できません。 HoloLens での特定のアプリまたはプロセスの起動を完全にブロックする場合は、「HoloLens 内の HoloLens 2 Microsoft Intune デバイスで Windows Defender アプリケーション制御を使用する[- Azure」を](/mem/intune/configuration/custom-profile-hololens)参照してください。

## <a name="key-technical-considerations-for-kiosk-mode-for-hololens"></a>デバイスのキオスク モードに関する主な技術的HoloLens

ランタイム プロビジョニング パッケージを使用するか、キオスク構成を手動で作成する予定の場合にのみ適用されます。 キオスク モードの構成では、XML に基づく階層構造が使用されます。

- 割り当てられたアクセス プロファイルでは、キオスク モードの [スタート] メニューに表示されるアプリケーションを定義します。 同じ XML 構造で複数のプロファイルを定義できます。これは後で参照できます。
- 割り当てられたアクセス構成は、特定のユーザーや AAD グループや訪問者など、そのプロファイルのプロファイルとターゲット ユーザーを参照します。使用シナリオの複雑さによっては、同じ XML 構造で複数の構成を定義できます (後の「サポートされるシナリオ」セクションを参照してください)。
- 詳細については [、AssignedAccess CSP に関するページを参照してください](/windows/client-management/mdm/assignedaccess-csp)。

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>ID の種類に基づくキオスク モードでサポートされるシナリオ

コピー [貼り付](hololens-kiosk-reference.md#kiosk-xml-code-samples) け前に、シナリオに基づく例と必要に応じて更新する例については、参照リンクを参照してください。

> [!NOTE]
> Intune の UI を使用してキオスク構成を作成しない場合にのみ、XML を使用します。

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>ローカル アカウントまたは MSA としてサインインするユーザーの場合

| **必要なキオスク エクスペリエンス** | **推奨されるキオスク構成** | **構成方法**  | **解説** |
| --- | --- | --- | --- |
| サインインするユーザーは、キオスク エクスペリエンスを取得します。 | [複数のアプリのグローバル割り当てアクセス プロファイルを構成する](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune テンプレート](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [ランタイム プロビジョニング - マルチ アプリ](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | グローバル割り当てアクセスには [、20H2 以降のビルドが必要です](hololens-release-notes.md#windows-holographic-version-20h2) |
| サインインした特定のユーザーがキオスク エクスペリエンスを取得します。  | [特定のユーザーの名前を指定して、(必要に応じて) 1 つ以上のアプリ割り当てアクセス プロファイルを構成します。](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [以下のサポートされているオプションを参照してください。](#steps-in-configuring-kiosk-mode-for-hololens) | シングル アプリ キオスク モードの場合、ローカル ユーザー アカウントまたは MSA アカウントだけが、HoloLens。 <br> 複数のアプリ キオスク モードの場合、MSA アカウントまたは AAD アカウントだけが、HoloLens。 |

### <a name="for-users-who-sign-in-as-aad-account"></a>AAD アカウントとしてサインインするユーザーの場合

| **必要なキオスク エクスペリエンス** | **推奨されるキオスク構成** | **構成方法** | **解説** |
| --- | --- | --- | --- |
| サインインするユーザーは、キオスク エクスペリエンスを取得します。 | [複数のアプリのグローバル割り当てアクセス プロファイルを構成する](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune テンプレート](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [ランタイム プロビジョニング - マルチ アプリ](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | グローバル割り当てアクセスには [、20H2 以降のビルドが必要です](hololens-release-notes.md#windows-holographic-version-20h2) |
| サインインしたユーザーは、特定のユーザーを除くすべてのユーザーがキオスク エクスペリエンスを取得します。 | [特定のユーザー (デバイス所有者である必要があります](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners)) を除外して、複数のアプリのグローバル割り当てアクセス プロファイルを構成します。 | • [Microsoft Intune テンプレート](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [ランタイム プロビジョニング - マルチ アプリ](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | グローバル割り当てアクセスには [、20H2 以降のビルドが必要です](hololens-release-notes.md#windows-holographic-version-20h2) |
| すべての AAD ユーザーは、そのユーザーに固有の個別のキオスク エクスペリエンスを取得します。 | [AAD アカウント名を指定して、各ユーザーに割り当てられたアクセス構成を構成します。](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [Microsoft Intune テンプレート](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [ランタイム プロビジョニング - マルチ アプリ](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| 別の AAD グループのユーザーには、グループ専用のキオスク モードが表示されます。 | [必要な AAD グループごとに割り当てられたアクセス構成を構成します。](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [Microsoft Intune テンプレート](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [ランタイム プロビジョニング - マルチ アプリ](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | • ユーザーがサインインし、HoloLens がインターネットに接続されている場合、そのユーザーがキオスク構成が存在する AAD グループのメンバーである場合、ユーザーは、その AAD グループのキオスクを体験します。 <br> • ユーザーのサインイン時にインターネットを使用できない場合、ユーザーはHoloLens[動作を受け取ります。](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) <br> • ユーザーがサインインし、AAD グループ ベースのキオスクを使用する必要があるときにインターネットの可用性が保証されない場合は [、AADGroupMembershipCacheValidityInDayspolicy](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)の使用を検討してください。 <br> • サインイン中に AAD グループを最適に使用するには[、AADGroupMembershipCacheValidityInDayspolicy](/hololens/hololens-release-notes#cache-azure-ad-group-membership-for-offline-kiosk)を使用する方法が推奨されます |
| 一時的な目的でHoloLensする必要があるユーザーは、キオスク エクスペリエンスを利用できます。 | [訪問者の割り当て済みアクセス構成を構成する](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | • [Microsoft Intune テンプレート](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [ランタイム プロビジョニング - 単一アプリ](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | • 一時ユーザー アカウントは、サインイン時HoloLensによって自動的に作成され、一時ユーザーがサインアウトすると削除されます。 <br> • ビジターの自動ログイン [ポリシー を有効にしてください](#how-can-visitor-accounts-automatically-logon-to-kiosk-experience)。 |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>デバイスのキオスク モードを構成するHoloLens

キオスク構成は、次の方法で作成および適用できます。

1. MDM サーバーの UI (Intune のキオスク テンプレートやカスタム OMA-URI 構成など) を使用すると、リモートで HoloLens に適用されます。
2. ランタイム プロビジョニング パッケージを使用すると、パッケージに直接適用HoloLens。

次の構成方法を示します。使用するプロセスに一致するタブを選択します。

1. [Microsoft Intune シングル アプリ キオスク テンプレートを作成する](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [Microsoft Intune マルチ アプリ キオスク テンプレート](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Microsoft Intune テンプレートの作成](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [ランタイム プロビジョニング - マルチ アプリ](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [ランタイム プロビジョニング - 単一アプリ](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

[!INCLUDE[](includes/kiosk-configure-steps.md)]

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="how-can-visitor-accounts-automatically-logon-to-kiosk-experience"></a>訪問者アカウントをキオスク エクスペリエンスに自動的にログオンする方法

[Holographic Windowsバージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1)以降のビルドの場合:

- AAD 構成と非追加構成はどちらも、キオスク モードで自動ログオンが有効になっているビジター アカウントをサポートします。

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>キオスク エクスペリエンスは、HoloLens (第 1 世代) でサポートされていますか?

キオスク モードは、デバイスにデバイスがインストールされているWindows Holographic for Business。 すべてのHoloLens 2デバイスは Windows Holographic for Businessに出荷され、他のエディションはありません。 すべてのデバイスHoloLens 2、キオスク モードを一から実行できます。

HoloLens (第 1 世代) デバイスは、OS ビルドと OS エディションの両方でアップグレードする必要があります。 次に示すのは、HoloLens (第 1 世代) を新しいエディション[に更新Windows Holographic for Business](hololens1-upgrade-enterprise.md)です。 キオスク モードを使用HoloLens (第 1 世代) デバイスを更新するには、まず、デバイスが Windows 10 バージョン 1803 以降のバージョンを実行している必要があります。 Windows Device Recovery Tool を使用して HoloLens (第 1 世代) デバイスを既定のビルドに回復した場合、または最新の更新プログラムをインストールした場合は、デバイスを構成する準備ができています。

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>デバイス ポータルを使用して非実稼働環境でキオスクを構成する方法

次のコマンドを[HoloLensデバイスを設定Windows デバイス ポータル。](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) デバイス ポータルは、お使いの PC に Web ブラウザーから接続することができる HoloLens 上の Web サーバーです。

 > [!CAUTION]
 > アプリケーションを使用HoloLens設定デバイス ポータル、デバイスで開発者モードを有効にする必要があります。 アプリがインストールされているデバイスの開発者モードWindows Holographic for Businessアプリをサイドロードできます。 ただし、この設定により、ユーザーがアプリの認定を受けしていないアプリをインストールMicrosoft Store。 管理者は、ポリシー CSP の **ApplicationManagement/AllowDeveloper Unlock** 設定を使用して、開発者モードを有効にする機能を [ブロックできます](/windows/client-management/mdm/policy-configuration-service-provider)。 [開発者モードの詳細をご覧ください。](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

キオスク モードは、必要なクエリ文字列パラメーター ("kioskModeEnabled" の値が "true" または "false") とオプションのパラメーター (パッケージ名の値が "startupApp" ) を 1 つ指定して、/api/holographic/kioskmode/settings に POST を実行することで、デバイス ポータル の REST API を介して設定できます。 この機能はデバイス ポータル開発者のみを対象とし、開発者以外のデバイスでは有効にしなける必要があるという念頭に置いておきます。 このREST API、今後の更新プログラム/リリースで変更される可能性があります。

## <a name="troubleshooting"></a>トラブルシューティング

### <a name="issue---no-apps-are-shown-in-start-menu-in-kiosk-mode"></a>問題 - キオスク モードの [スタート] メニューにアプリが表示されません

**現象**

キオスク モードの適用でエラーが発生すると、次の動作が表示されます。

- Holographic Windowsより前のバージョン 20H2 - HoloLens では、すべてのアプリケーションが スタート メニュー。
- WindowsHolographic バージョン 20H2 - デバイスにキオスク構成 (グローバル割り当てアクセスと AAD グループ メンバー割り当てアクセスの両方の組み合わせ) がある場合、AAD グループ メンバーシップの決定に失敗した場合、ユーザーには "何も表示されません" メニューが表示されます。

    ![失敗したときのキオスク モードの画像。](images/hololens-kiosk-failure-behavior.png )

- [Holographic バージョン 21H1 Windows、](hololens-release-notes.md#windows-holographic-version-21h1)キオスク モードでは、空のスタート メニューを表示する前にグローバル割り当てアクセスが検索されます。 AAD グループ キオスク モード中にエラーが発生した場合、キオスク エクスペリエンスはグローバル キオスク構成 (存在する場合) に戻ります。

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

1. ランタイム プロビジョニング パッケージ用のWindowsデザイナー プロジェクトが存在するフォルダーを参照します。
1. ICD.log を開き、プロビジョニング パッケージの構築中にログにエラーが発生していないか確認します。 一部のエラーはビルド中に表示されませんが、ICD.log に記録されます

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>問題 – AAD グループへの複数のアプリ割り当てアクセスが機能しない

**現象**

AAD ユーザーのサインイン時に、デバイスがキオスク モードに入らない

**トラブルシューティングの手順**

- [割り当て済みアクセス構成 XML] で、サインインしているユーザーが のメンバーである AAD グループの GUID が使用され、AAD ユーザーの GUID が使用されていないか確認します。
- Intune ポータルで、AAD ユーザーが実際に対象の AAD グループのメンバーとして表示されます。
