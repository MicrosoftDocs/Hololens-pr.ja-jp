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
ms.openlocfilehash: 28c431397385c06fb94de410a0763e24e18e4509
ms.sourcegitcommit: 749d617f3f0ce3e6363ff6cd1a03f87b9280f418
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "122979374"
---
# <a name="set-up-hololens-as-a-kiosk"></a>HoloLens をキオスクとしてセットアップする

## <a name="what-is-kiosk-mode"></a>キオスク モードとは

キオスク モードは、ユーザーがアプリにサインインするときにスタート メニューに表示されるアプリケーションを制御できるHoloLens。 次の 2 つのシナリオがサポートされています。

1. **シングル アプリ キオスク モード** – [スタート] メニューは表示されません。ユーザーがサインインすると、1 つのアプリが自動的に起動されます。 <br> *使用例*: アプリ内でのみ実行Dynamics 365 Guides。
2. **複数のアプリ** キオスク モード – スタート メニューユーザーがサインインするときにキオスク構成で指定されたアプリケーションのみを表示します。 必要に応じて、アプリを選択して自動的に起動できます。 <br> *使用例*: [スタート] メニューに [ストア] アプリ、フィードバック Hub、設定のみを表示するデバイス。

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

## <a name="security-considerations"></a>セキュリティの考慮事項

キオスク モードはセキュリティ方法と見なすのではなく、ユーザーのサインイン時の起動エクスペリエンスを制御する手段として考慮する必要があります。 特定のセキュリティ関連のニーズがある場合は、キオスク モードエクスペリエンスと以下に示すオプションを組み合わせて使用できます。

- アプリ設定キオスク モードで表示するように構成され、設定 アプリに表示されるページを制御する場合は、「ページの表示設定[参照してください](settings-uri-list.md)。
- 特定のアプリの特定のハードウェア機能 (カメラ、Bluetooth など) へのアクセスを制御する場合は[、「HoloLens 2 - Windows Client Management](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2)でサポートされるポリシー CSP のポリシー」を参照してください。 アイデアについては、デバイス [に関する一般的な](hololens-common-device-restrictions.md) 制限を確認できます。
- キオスク モードでは、(キオスク エクスペリエンスの一部として構成されている) アプリが他のアプリを起動できません。 HoloLens での特定のアプリ/プロセスの起動を完全にブロックする場合は、「HoloLens 2 Microsoft Intune 内の HoloLens 2 デバイスで Windows Defender アプリケーション制御を使用する[- Azure」を参照](/mem/intune/configuration/custom-profile-hololens)してください。

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
| 別の AAD グループのユーザーには、グループ専用のキオスク モードが表示されます。 | [必要な AAD グループごとに割り当てられたアクセス構成を構成します。](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [Microsoft Intune テンプレート](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [ランタイム プロビジョニング - マルチ アプリ](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | • ユーザーがサインインし、HoloLens がインターネットに接続されている場合、そのユーザーがキオスク構成が存在する AAD グループのメンバーである場合、ユーザーは、その AAD グループのキオスクを体験します。 <br> •[ユーザーのサインイン時にインターネット](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode)を使用できない場合、ユーザーはHoloLens動作を発生します。 <br> •ユーザーのサインインと AAD グループベースのキオスクの使用が必要な場合にインターネットの可用性が保証されない場合は、 [AADGroupMembershipCacheValidityInDayspolicy の使用を検討](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)してください。 |
| 一時的な目的で HoloLens を使用する必要があるユーザーは、キオスクエクスペリエンスを利用できます。 | [訪問者の割り当て済みアクセス構成を構成する](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | •[カスタムテンプレートの Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [ランタイムプロビジョニング-単一アプリ](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | •一時ユーザーアカウントは、サインイン時に HoloLens によって自動的に作成され、一時ユーザーがサインアウトすると削除されます。 <br> •訪問者 [の自動ログインポリシー](#how-can-visitor-accounts-automatically-logon-to-kiosk-experience)を有効にすることを検討してください。 |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>HoloLens のキオスクモードを構成する手順

キオスクの構成は、次の方法で作成および適用できます。

1. MDM サーバーの UI を使用します。たとえば、Intune のキオスクテンプレートや、カスタム OMA-URI 構成を HoloLens にリモートで適用します。
2. ランタイムプロビジョニングパッケージを使用します。このパッケージは、HoloLens に直接適用されます。

次の方法でを構成し、使用するプロセスに一致するタブを選択します。

1. [シングルアプリキオスクテンプレートを Microsoft Intune](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [マルチアプリキオスクテンプレートの Microsoft Intune](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [カスタムテンプレートの Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [ランタイムのプロビジョニング-マルチアプリ](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [ランタイムプロビジョニング-単一アプリ](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

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
- WindowsHolographic、バージョン 20H2-デバイスにキオスク構成 (グローバルに割り当てられたアクセスと AAD グループメンバーの割り当て済みアクセスの両方の組み合わせ) がある場合、AAD グループのメンバーシップの確認に失敗すると、ユーザーには [スタート] メニューに表示されないものが表示されます。

    ![キオスクモードが失敗したときにどのように表示されるかを示した画像。](images/hololens-kiosk-failure-behavior.png )

- [Windows Holographic バージョン 21h1](hololens-release-notes.md#windows-holographic-version-21h1)以降では、キオスクモードでは、空の [スタート] メニューが表示される前に、グローバルに割り当てられたアクセスが検索されます。 AAD グループキオスクモードでエラーが発生した場合、キオスクのエクスペリエンスはグローバルキオスク構成 (存在する場合) にフォールバックします。

**トラブルシューティングの手順**

- アプリの AUMID が正しく指定されており、バージョンが含まれていないことを確認します。 例については、「 [HoloLens AUMIDs](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) for inbox apps」を参照してください。
- そのユーザーのデバイスにアプリケーションがインストールされていることを確認します。
- キオスク構成が AAD グループに基づいている場合は、AAD ユーザーがサインインしたときにインターネット接続が存在することを確認してください。 必要に応じて、 [MixedReality/AADGroupMembershipCacheValidityInDays](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-aadgroupmembershipcachevalidityindays) ポリシーを構成して、インターネットがなくても機能できるようにします。

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

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>問題-AAD グループへの複数のアプリ割り当てアクセスが機能しない

**現象**

AAD ユーザーサインインでは、デバイスがキオスクモードに移行しない

**トラブルシューティングの手順**

- [割り当てられたアクセス構成 XML] で、サインインしているユーザーがメンバーである AAD グループの GUID が使用され、AAD ユーザーの GUID ではないことを確認します。
- Intune ポータルで、AAD ユーザーがターゲット AAD グループのメンバーとして実際に表示されていることを確認します。
