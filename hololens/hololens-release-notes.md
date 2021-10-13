---
title: HoloLens 2 のリリース ノート
description: 新しい HoloLens 2 リリースごとに最新情報を入手できます。
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/12/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: c45a9a05cc7911bc9866df5e4313bc27a205d333
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924469"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 のリリース ノート

HoloLens デバイスの生産性を向上させるために、引き続き機能、バグ、およびセキュリティ更新プログラムをリリースします。 このページでは、毎月 HoloLens の新機能を確認できます。 最新の HoloLens 2 更新プログラムを入手するには、[更新プログラムを確認して手動で更新](hololens-update-hololens.md#check-for-updates-and-manually-update)するか、完全なフラッシュ更新プログラム (ffu) を取得して、 [Advanced Recovery コンパニオンを使用してデバイスをフラッシュ](hololens-recovery.md#clean-reflash-the-device)することができます。 [ダウンロード](https://aka.ms/hololens2download)は最新の状態に保たれ、一般公開されている最新のビルドを提供します。

> [!NOTE]
> 最近の Windows 11 の発表は、Windows の PC バージョンに重点を置いていました。 [2021 年10月に HoloLens 2 するために、OS の主要な更新](#windows-holographic-version-21h2)を最近開始しました。お客様からのフィードバックに基づいて今後リリースされる予定です。

## <a name="windows-holographic-version-21h2"></a>WindowsHolographic バージョン21H2

- ビルド20348.1432

WindowsHolographic、バージョン21h2 が利用可能になりました。また、ユーザーと IT プロフェッショナル HoloLens 2 に優れた新機能が用意されています。 これは、トラブルシューティングとデバイスレポートの改善、キオスクモードおよび証明書ビューアーの一部の修正されたバグ、拡張された管理面の強化、および更新の信頼性の向上に関するものです。 この機能更新プログラムの新機能として、プラットフォームの移行モードが HoloLens になっています。 HoloLens 2 の新しい優れた機能をすべてご確認ください。

この最新リリースは、バージョン21H1 の月間更新版ですが、今回は新機能を追加しています。 メジャービルド番号は変わりません。 Windows Update は、バージョン 21h1 (ビルド 20348) の月単位のリリースを示します。 設定 > [バージョン情報] 画面でビルド番号を確認すると、利用可能な最新のビルド 20348.1432 + が表示されていることを確認できます。 最新のリリースに更新するには、設定アプリを開き、[Update & Security] にアクセスして、[更新プログラムの確認] をタップします。 HoloLens 更新プログラムを管理する方法の詳細については、「 [HoloLens 更新プログラムの管理](hololens-updates.md)」を参照してください。

| 機能                 | 説明                | ユーザーまたはシナリオ |
|-------------------------|----------------------------|--------------|
| [移動プラットフォーム モード](#moving-platform-mode) | プラットフォームモードベータの移行について説明します。これにより、構成されている場合、船舶を使用して、動的な動きが発生している大海の大規模な海での HoloLens 2 | すべて |
| [証明書マネージャーの PFX ファイルのサポート](#pfx-file-support-for-certificate-manager) | 設定 UI を使用した PFX 証明書の追加 | エンド ユーザー |
| [HoloLens の設定で詳細な診断レポートを表示する](#view-advanced-diagnostic-report-in-settings-on-hololens) | デバイスで MDM 診断ログを表示する | トラブルシューティング |
| [オフライン診断の通知](#offline-diagnostics-notifications) | ログ収集に関する audiovisual フィードバック | トラブルシューティング |
| [低ストレージログ収集の機能強化](#low-storage-log-collection-improvements) | ストレージが不足している場合のログ収集シナリオの改善。 | トラブルシューティング |
| [レポート HoloLens の詳細の CSP の変更](#csp-changes-for-reporting-hololens-details) | データを照会するための新しい Csp | IT 管理者    |
| [CSP によって制御される自動ログインポリシー](#auto-login-policy-controlled-by-csp) | アカウントを自動的にログインするために使用されます | IT 管理者 |
| [更新の再起動の検出と通知の向上](#improved-update-restart-detection-and-notifications) | 更新プログラム用の新しい有効なポリシーと UX。 | IT 管理者 |
| [アプリの更新のためのスマートな再試行](#smart-retry-for-app-updates) | IT 管理者がアプリを更新するためのスケジュールされた再試行を許可します。 | IT 管理者 |
| [Microsoft Store にのみプライベートストアアプリを使用する](#use-only-private-store-apps-for-microsoft-store) | 組織のアプリのみを表示するようにストアアプリを構成する | IT 管理者 |
| [WDAC アプリと LOB アプリを使用する](#use-wdac-and-lob-apps) | IT 管理者が独自のアプリを使用し、引き続き WDAC を使用して他のアプリをブロックできるようにします。 | IT 管理者 |
| [修正プログラムと機能強化](#fixes-and-improvements) | HoloLens の修正と改善。 | すべて |

### <a name="it-admin-feature-checklist"></a>IT 管理機能のチェックリスト

✔️、1つの Azure AD アカウントを自動的にログインするように設定する場合は、[この新しい CSP を構成します。](#auto-login-policy-controlled-by-csp) <br>
✔️更新に失敗した後に自動的に更新を試みるようにアプリを構成する場合は、 [この新しい CSP をスマート再試行用に設定します。](#smart-retry-for-app-updates) <br>
✔️ OS の更新をより細かく制御する場合は、 [新しく有効にした更新ポリシーを確認してください。](#improved-update-restart-detection-and-notifications) <br>
✔️組織のアプリを Microsoft Store 経由で会社のストアで使用できるようにする必要があり、完全なストアではなく、組織のアプリへのアクセスのみを許可する場合は、[このポリシーを設定します。](#use-only-private-store-apps-for-microsoft-store) <br>
✔️ HoloLens デバイスの空き記憶域スペース、SSID、または BSSID を知りたい場合は、これらの[レポート csp を確認してください。](#csp-changes-for-reporting-hololens-details) <br>
✔️、WDAC を使用してアプリやプロセスの起動をブロックしたいが、独自の bushiness アプリを使用する必要がある場合は、 [wdac ポリシーで LOB を許可](#use-wdac-and-lob-apps)できるようになりました。

### <a name="moving-platform-mode"></a>移動プラットフォーム モード

[Windows Holographic の As バージョン 21h2](hololens-release-notes.md#windows-holographic-version-21h2)では、HoloLens 2 での動的な動き移動プラットフォームを追跡するためのベータサポートを追加しました。 ビルドをインストールし、プラットフォームの移動モードを有効にすると、大規模な船舶や大海船舶など、以前にアクセスできなかった環境で HoloLens 2 を使用できるようになります。 現在、この機能は、これらの特定の移動プラットフォームを有効にすることのみを目的としています。 この機能を他の環境で使用してはいけないことはありませんが、この機能はそもそもこういった環境にサポートを追加することに重点を置いています。

サポートされている機能と、この新機能を有効にする方法の詳細については、「 [プラットフォームの移行」ページを参照](hololens2-moving-platform.md)してください。

#### <a name="overview-to-try-out-moving-platform-mode"></a>プラットフォームモードの移行を試すための概要

1. [開発者モードとデバイスポータルを有効に](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)します。
1. [デバイスポータルを使用したプラットフォームモードの移動を有効に](hololens2-moving-platform.md#enabling-moving-platform-mode)します。
1. デバイスを大規模な移動プラットフォームに取り、安定したホログラムがどのように動作するかを観察します。

### <a name="pfx-file-support-for-certificate-manager"></a>証明書マネージャーの PFX ファイルのサポート

Windows Insider build 20348.1405 で導入されました。 .Pfx 証明書を使用するように、 [証明書マネージャー](certificate-manager.md) にサポートを追加しました。 ユーザーが  >  **& セキュリティ**  >  **証明書** を更新設定に移動し、[**証明書のインストール**] を選択すると、UI で .pfx 証明書ファイルがサポートされるようになりました。
ユーザーは、秘密キーを持つ .pfx 証明書をユーザーストアまたはコンピューターストアにインポートできます。

#### <a name="overview-to-try-out-pfx-files-in-certificate-manager"></a>証明書マネージャーで PFX ファイルを試すための概要

1. PFX ファイルを準備します。
1. USB C ケーブルを使用して、ファイルをデバイスにコピーします。
1. 設定アプリを開き、[証明書マネージャー](certificate-manager.md)に移動して、証明書を適用します。

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>HoloLens の設定で詳細な診断レポートを表示する

管理対象デバイスでの動作のトラブルシューティングでは、必要なポリシー構成が適用されていることを確認することが重要な手順です。 これまでの新機能では、**設定** アカウントによって収集された mdm 診断ログをエクスポートした後、mdm またはデバイスの近くでデバイスを使用する必要がありました。これには、  ->    >  **職場または学校へのアクセス権** があります。また、**管理ログをエクスポート** し、近くの PC に表示します。

これで、Edge ブラウザーを使用してデバイスで MDM 診断を表示できるようになりました。 MDM 診断レポートをより簡単に表示するには、[職場または学校へのアクセス] ページに移動し、[ **詳細な診断レポートの表示**] を選択します。 これにより、レポートが生成され、新しいエッジウィンドウで開きます。

![設定アプリで詳細な診断レポートを表示します。](./images/view-advanced-diagnostic-report.jpg)

#### <a name="overview-to-try-out-the-advanced-diagnostic-report"></a>詳細な診断レポートを試すための概要

1. [設定] アプリを開きます。
1. [アカウント] ページに移動し、[新規] リンクをクリックし **て管理ログをエクスポート** します。
1. デバイスの構成に関する詳細情報を表示します。

### <a name="offline-diagnostics-notifications"></a>オフライン診断の通知

これは、 [オフライン診断](hololens-diagnostic-logs.md#offline-diagnostics)と呼ばれる既存の機能の更新プログラムです。 以前は、診断コレクションがトリガーされたか、または完了したことをユーザーに明確に示すインジケーターがありませんでした。
[Windows Holographic version 21h2](hololens-release-notes.md#windows-holographic-version-21h2)に追加された、オフライン診断のためのオーディオビジュアルフィードバックには、2つの形式があります。 コレクションの開始時と完了時の両方について、最初に表示されるトースト通知が表示されます。 これらは、ユーザーがログインし、視覚エフェクトを持っているときに表示されます。

![ログを収集するためのトースト。](./images/logcollection1.jpg)

![ログの収集が完了したときのトースト。](./images/logcollection2.jpg)

多くの場合、ユーザーがディスプレイにアクセスできない場合にはフォールバックログ収集メカニズムとしてオフライン診断を使用しますが、ログインができない場合や、まだ OOBE にある場合は、ログが収集されるときにオーディオキューも再生されます。 このサウンドは、トースト通知に加えて再生されます。

この新機能は、デバイスの更新時に有効になり、有効にしたり管理したりする必要はありません。 この新しいフィードバックを表示したり聞いたりできない場合でも、オフライン診断は引き続き生成されます。

この新しいオーディオビジュアルフィードバックの追加により、診断データを簡単に収集し、問題のトラブルシューティングをより簡単に行うことができます。

この情報は、後で [ [診断ログ] ページ](hololens-diagnostic-logs.md#offline-diagnostics)で確認できます。

#### <a name="overview-to-try-out-the-diagnostics-notifications"></a>診断通知を試すための概要

1. デバイスのロックを解除して、磨耗します。
1. [ **電源** と **音量** ] ボタンの組み合わせを押して、 [オフライン診断](hololens-diagnostic-logs.md#offline-diagnostics)を収集します。
1. トースト通知を表示し、デバイスが起動してログ収集が完了したときのオーディオキューを聞きます。

### <a name="low-storage-log-collection-improvements"></a>低ストレージログ収集の機能強化

診断ログを収集するときにデバイスのディスク領域が不足していると思われる場合は、 **StorageDiagnostics.zip** という名前の追加のレポートが作成されます。 低ストレージのしきい値は、Windows ストレージの[意味](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)で自動的に決定されます。

この情報は、後で [ [診断ログ] ページ](hololens-diagnostic-logs.md#offline-diagnostics)で確認できます。

#### <a name="overview-to-try-out-the-low-storage-improvements"></a>低ストレージの機能強化を試すための概要

1. デバイスの記憶域スペースをいっぱいにします。
1. [ **電源** と **音量** ] ボタンの組み合わせを押して、 [オフライン診断](hololens-diagnostic-logs.md#offline-diagnostics)を収集します。
1. HoloLens の Documents フォルダーに格納されているログのコレクションに新しいファイルがあることを確認します。

### <a name="csp-changes-for-reporting-hololens-details"></a>レポート HoloLens の詳細の CSP の変更

次の csp は、HoloLens デバイスから情報をレポートする新しい方法で更新されました。

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP-Free Storage

devdetail CSP は HoloLens デバイスの空き記憶域も報告するようになりました。 これは、設定アプリの Storage ページに表示される値とほぼ一致している必要があります。 この情報を含む特定のノードを次に示します。

- ./DevDetail/Ext/Microsoft/FreeStorage (GET 操作のみ)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP-SSID および BSSID

devicestatus CSP は、HoloLens がアクティブに接続されている Wi-Fi ネットワークの SSID と BSSID も報告するようになりました。 この情報を含む特定のノードを次に示します。

- *Wi-Fi アダプタ/SSID の/Vendor/MSFT/DeviceStatus/NetworkIdentifiers/mac アドレス*
- *Wi-Fi アダプタ/BSSID の/Vendor/MSFT/DeviceStatus/NetworkIdentifiers/mac アドレス*

ネットワーク識別子を照会するための syncml blob の例 (MDM ベンダー向け)

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a>CSP によって制御される自動ログインポリシー

この新しい AutoLogonUser ポリシーは、ユーザーが自動的にログオンするかどうかを制御します。 一部のお客様は、id に関連付けられているものの、サインインエクスペリエンスが不要なデバイスを設定する必要があります。 デバイスを選択し、リモートアシスタンスをすぐに使用する Imagine ます。 または、HoloLens デバイスを迅速に配布し、エンドユーザーがログインを迅速に行えるようにするという利点があります。

ポリシーが空でない値に設定されている場合は、自動ログオンユーザーの電子メールアドレスを指定します。 自動ログオンを有効にするには、指定されたユーザーがデバイスに少なくとも1回ログオンする必要があります。

新しいポリシー `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` 文字列値の oma-uri

- 同じ電子メールアドレスを持つユーザーは、自動ログオンが有効になります。

このポリシーが構成されているデバイスでは、ポリシーで指定されたユーザーが少なくとも1回ログオンする必要があります。 最初のログオン後にデバイスを再起動すると、指定したユーザーが自動的にログオンします。 1つの自動ログオンユーザーのみがサポートされています。 有効にすると、自動的にログオンしたユーザーは手動でログアウトできなくなります。 別のユーザーとしてログオンするには、まずポリシーを無効にする必要があります。

> [!NOTE]
>
> - 主要な OS の更新などの一部のイベントでは、指定されたユーザーがデバイスにもう一度ログオンして、自動ログオンの動作を再開することが必要になる場合があります。
> - 自動ログオンは、MSA および AAD ユーザーに対してのみサポートされています。

#### <a name="overview-to-try-auto-logon-csp"></a>自動ログオン CSP を試すための概要

1. [カスタムポリシーを使用して](/mem/intune/configuration/custom-settings-windows-10)、目的のユーザーに新しい CSP を構成します。`./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`
1. [プロビジョニングパッケージ](hololens-provisioning.md)または[MDM](hololens-mdm-configure.md)を使用して、CSP をデバイスに適用します。
1. 指定されたアカウントにサインインします。
1. デバイスを再起動し、ユーザーが自動的にログインしていることを確認します。

### <a name="improved-update-restart-detection-and-notifications"></a>更新の再起動の検出と通知の向上

アクティブ時間とインストール時間のポリシーの間に、デバイスが使用されているときに HoloLens デバイスを再起動しないようにすることができます。 ただし、必要な更新プログラムのインストールを完了するために再起動が行われない場合は、更新プログラムの導入が遅れることもあります。 ポリシーを追加して、期限および必要な再起動を実施し、更新プログラムのインストールが適時に完了するようにしました。 ユーザーは再起動を開始する前に通知を受け、IT ポリシーに従って再起動を遅らせることができます。

次の更新ポリシーが追加されました。

- [Update/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Update/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [Update/ConfigureDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [Update/ConfigureDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [Update/ConfigureDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [Update/ConfigureDeadlineNoAutoReboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Update/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Update/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Update/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

#### <a name="overview-to-try-new-update-notifications"></a>新しい更新通知を試すための概要

1. [プロビジョニングパッケージ](hololens-provisioning.md)または[MDM](hololens-mdm-configure.md)を使用して、新しい更新プログラムの csp のいずれかを構成します (上記のリンクリストを参照し、1つを選択してください)。
1. スケジュールされた時刻にデバイスを使用します。
1. 更新についてユーザーに通知し、デバイスを再起動する必要があることを確認し \* ます。

\* 結果は、使用する更新ポリシーによって異なる場合があります。

### <a name="smart-retry-for-app-updates"></a>アプリの更新のためのスマートな再試行

現在、HoloLens が有効になっています。これにより、IT 管理者は、更新プログラムの適用を許可するアプリが使用中であるために更新が失敗したアプリを再起動するように、定期的または1回の日付を設定できます。 これらは、スケジュールされた時刻やサインインなど、いくつかの異なるトリガーに基づいて設定できます。 このポリシーの使用方法の詳細については、「 [Applicationmanagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)」を参照してください。

詳細については、後の「 [ビジネス向けアプリ展開ストア」ページ](app-deploy-store-business.md)を参照してください。

#### <a name="overview-to-try-smart-retry-for-app-updates"></a>アプリの更新のためにスマートな再試行を試すための概要

1. 新しいスマート再試行機能を構成します。
1. アプリをまだ受信しておらず、に適切に構成されているデバイスで、オンライン環境にログインします。
1. デバイスの電源をオフにするか、接続を切断することで、アプリをダウンロードできないようにします。
1. トリガーされた時間内にデバイスの電源をオンにし、インターネットに接続してから、ダウンロードを再試行します。

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Microsoft Store の専用ストアアプリのみを使用する

RequirePrivateStoreOnly ポリシーは HoloLens に対して有効になっています。 このポリシーを使用すると、[ビジネス向け Microsoft Store](/microsoft-store/microsoft-store-for-business-overview)によって組織用に構成されたプライベートストアのみを表示するように Microsoft Store アプリを構成できます。 使用できるようにしたアプリのみにアクセスを制限する。

[Applicationmanagement/RequirePrivateStoreOnly](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)の詳細情報

詳細については、後の「 [ビジネス向けアプリ展開ストア」ページ](app-deploy-store-business.md)を参照してください。

#### <a name="overview-to-try-only-private-store-apps"></a>プライベートストアアプリのみを試すための概要

1. [MDM](hololens-mdm-configure.md)を使用してデバイスの新しいポリシーを構成します。
1. ポリシーを持つデバイスにログインします。
1. Microsoft Store アプリを開き、組織のアプリのみが表示されることを確認します。

### <a name="use-wdac-and-lob-apps"></a>WDAC アプリと LOB アプリを使用する

WDAC を使用して、アプリやプロセスの起動をブロックし、独自の bushiness アプリを引き続き使用できるようになりました。 これで、WDAC ポリシーで許可できるようになりました。 このポリシーを使用するには、WDAC ポリシーを作成するときに、PowerShell で余分なコード行を実行する必要があります。 [こちらの手順を確認してください。](/mem/intune/configuration/custom-profile-hololens)

#### <a name="overview-to-try-your-own-apps-while-using-wdac-to-block-others"></a>他のユーザーをブロックするために、WDAC を使用して独自のアプリを試すための概要

1. LOB アプリとブロックするアプリの AUMIDs を収集します。
1. 新しい手順に従って、[新しい WDAC ポリシーを作成](/mem/intune/configuration/custom-profile-hololens)します。
1. [MDM を使用して](hololens-mdm-configure.md) デバイスにポリシーを展開します。
1. デバイスにサインインし、アプリを起動して他のユーザーをブロックできることを確認します。

### <a name="fixes-and-improvements"></a>修正プログラムと機能強化

#### <a name="for-developers"></a>開発者向け

- [ロックされたファイルをダウンロードするプロンプトがないデバイスポータルの既知の問題](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)を修正しました。
- [ファイルのアップロードとダウンロードのタイムアウトを含むデバイスポータルの既知の問題](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)を修正した。
- 内部版のビルドでは、2D アプリのゲームパッド処理が無効になりました。 これを削除することで、アプリはゲームパッド Api を直接使用できるようになり、コントロールのセット全体にアクセスできるようになり、さらに多くのことを行うことができます。 開発者がゲームパッドの入力を使用するには、ゲームパッド Api を使用する必要があります。 ゲームパッドクラスのサンプル (Windows を次に示し[ます。ゲームの入力)-UWP アプリケーションを Windows](/uwp/api/windows.gaming.input.gamepad?view=winrt-20348&preserve-view=true)します。
- [割り当てられたアクセス API](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true)を有効にし、アプリが HoloLens にログインしているユーザーに対してキオスクモードで実行されている HoloLens かどうかを確認できるようになりました。

#### <a name="for-enterprise"></a>Enterprise

- HoloLens デバイスからのコンプライアンスプロパティのレポートに関する問題に対処します。Insider ビルドで適切なレポートをトリガーするには、再起動が必要になることがあります。  
- 新しい点滅にインストールされているリモートアシスタンスのインボックスバージョンが更新されました。
- AAD グループベースのキオスク構成が使用されていた場合に、最初のユーザーのサインイン後に OOBE が終了される問題を修正しました。
- デバイスを再起動するための更新通知とダイアログプロンプトの表示に関する問題を修正しました。
- デバイスを再起動した後、Xbox コントローラーとその他の Bluetooth LE 周辺機器をペアリングしてから、接続するという問題を修正しています。
- リモートアシスタンス通話中に送信ビデオが少しフリーズする原因となるビデオエンコーダーの問題を修正しました。 Wi-Fi ドライバーとファームウェアの変更により、Wi-Fi 脆弱性を解決します。
- Wi-Fi ドライバーとファームウェアの変更により、Wi-Fi 脆弱性を解決します。
- 移動プラットフォームモード (MPM) を使用する場合、"Down" は短期間の平均重力によって推定されます。 この値は、プラットフォームモードを移動するときの真の重力に代わるものです。
- 3DoF の場合、または追跡が失われた場合に、ホログラムの周期的な wobble を修正します。
- 以前のリリースから 21H1/21H1 リリースの更新に影響する問題に対処します。

## <a name="windows-holographic-version-20h2---october-2021-update"></a>WindowsHolographic、バージョン 20H2-2021 年10月の更新プログラム

- ビルド19041.1168

更新プログラムの機能強化と修正:

- この月間品質更新プログラムには、重要な変更は含まれていません。最新のビルド (Windows Holographic、バージョン 21h2) を試すことをお勧めします。

## <a name="windows-holographic-version-21h1---september-2021-update"></a>WindowsHolographic、バージョン 21H1-2021 年9月更新

- ビルド20348.1018

更新プログラムの機能強化と修正:

- システム時刻が予期せずに移動する問題を解決するための修正。

## <a name="windows-holographic-version-20h2---september-2021-update"></a>WindowsHolographic、バージョン 20H2-2021 年9月更新

- ビルド19041.1165

更新プログラムの機能強化と修正:

- システム時刻が予期せずに移動する問題を解決するための修正。

## <a name="windows-holographic-version-21h1---august-2021-update"></a>WindowsHolographic、バージョン 21H1-2021 年8月更新

- ビルド20348.1014

更新プログラムの機能強化と修正:

- コントローラーがサポートされているイマーシブアプリケーションで Xbox コントローラーを使用できない問題を修正しています。
- デバイスの更新エラーの診断が改善されました。

## <a name="windows-holographic-version-20h2---august-2021-update"></a>WindowsHolographic、バージョン 20H2-2021 年8月更新

- ビルド19041.1161

更新プログラムの機能強化と修正:

- この月間品質更新プログラムには、重要な変更は含まれていません。最新のビルド (Windows Holographic、バージョン 21h1) を試すことをお勧めします。

## <a name="windows-holographic-version-21h1---july-2021-update"></a>WindowsHolographic、バージョン 21H1-2021 年7月の更新プログラム

- ビルド20348.1010

更新プログラムの機能強化と修正:

- デバイスポータルには、ファイルエクスプローラーでロックされたファイルを開くときに問題が発生した場合に、ユーザーに通知するための拡張された方法
- サポートされているすべてのブラウザーで https を使用すると、ファイルのアップロード、ダウンロード、名前の変更、および削除が修正されるようになりました。
- **設定 > ネットワーク & Internet > Status > properties** から Wi-Fi プロパティ UI を起動したときに Wi-Fi プロキシを保存できない問題を修正しました。
- OS 更新プログラム間での eSIM 証明書の削除に関する問題に対処します。 この修正により、21H1 リリースに更新するときに、eSIM 証明書と関連コンポーネントが削除されます。
- OS のリセットを通じてプレインストールされたアプリに影響する問題を修正しました。
- CPU 負荷の増加による課金時にランタイムを増加させるためにチューニングされたバッテリの充電パフォーマンス。 デバイスの HoloLens 2 充電中に、デバイスがホットで動作していることが検出された場合、内部バッテリの充電が遅くなり、熱が減少します。 正のトレードオフとして、デバイスが温度の問題によってシャットダウンされる可能性が低く、デバイスの実行時間が長くなることがあります。 デバイスでクールが実行されている場合、料金は影響を受けません。

> [!IMPORTANT]
> リモートアシスタンス Windows の[ユーザーに影響を与える21h1 ビルドの既知の問題が解決され](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)たため、一時的に Holographic version 21h1 更新プログラムの提供を一時停止しました。 また、既定の Advanced Recovery コンパニオン (ARC) ビルドも[Windows Holographic バージョン20h2 – June 2021 Update](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update)に変更されました。 これで、弧ビルドが21H1 ビルドのターゲットを再開します。

## <a name="windows-holographic-version-20h2--july-2021-update"></a>WindowsHolographic、バージョン20H2 –2021年7月の更新プログラム

- ビルド19041.1157

更新プログラムの機能強化と修正:

- デバイスポータルには、ファイルエクスプローラーでロックされたファイルを開くときに問題が発生した場合に、ユーザーに通知するための拡張された方法
- サポートされているすべてのブラウザーで https を使用すると、ファイルのアップロード、ダウンロード、名前の変更、および削除が修正されるようになりました。

## <a name="windows-holographic-version-21h1---june-2021-update"></a>WindowsHolographic、バージョン 21H1-2021 年6月更新

- ビルド20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>職場または学校のカメラロールのアップロード用の OneDrive

HoloLens 2 設定アプリに新しい機能が追加されました。これにより、デバイスの画像 > カメラロールフォルダーから、職場または学校のフォルダーの対応する OneDrive に、混合した現実の写真とビデオを自動的にアップロードできます。 この機能は、HoloLens 2 上の[OneDrive アプリ内の機能のギャップ](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos)に対処します。これは、お客様の個人の Microsoft アカウント (職場または学校のアカウントではなく) に対するカメラロールの自動アップロードのみをサポートしています。

**動作のしくみ**

- **設定 > System > Mixed Reality カメラ** にアクセスして、"カメラのアップロード" を有効にします。
- この機能を On の位置に設定することにより、デバイスにキャプチャされた mixed reality 写真またはビデオは、職場または学校アカウントの OneDrive の **[** 画像 > カメラロール] フォルダーにアップロードするために自動的にキューに登録されます。
    >[!NOTE]
    >この機能を有効にする前にキャプチャした写真やビデオは、アップロードのキューに登録され *ない* ため、手動でアップロードする必要があります。
- [設定] ページのステータスメッセージには、アップロードを保留中のファイルの数が表示されます (保留中のすべてのファイルがアップロードされた場合は、"OneDrive が最新の状態" になります)。
- 帯域幅に関する問題や、何らかの理由でアップロードを "一時停止" する場合は、この機能を **オフ** の位置に切り替えることができます。 この機能を一時的に無効にすると、新しいファイルをカメラのロールフォルダーに追加してもアップロードキューのサイズが増加し続けますが、この機能を再度有効にするまでファイルはアップロードされません。
- 最新のファイルが最初にアップロードされます (後入れ先出し)。
- OneDrive アカウントに問題がある場合 (パスワードの変更後など)、[**今すぐ修正**] ボタンが設定] ページに表示されます。
- ファイルの最大サイズはありませんが、大きなファイルはアップロードに時間がかかることに注意してください (アップロードの帯域幅が制限されている場合は特に)。 大きなファイルのアップロード中に [一時停止] または [アップロード] をオフにすると、部分的なアップロードが保持されます。 アップロードが "一時停止" から数時間以内に再び有効になった場合、またはオフになっている場合、アップロードは中断された箇所から続行されます。 ただし、数時間後にアップロードを再び有効にすると、大きなファイルのアップロードが最初から再開されます。

**既知の問題と注意事項**

- この設定には、現在の使用帯域幅に基づく制限が組み込まれていません。 別のシナリオの帯域幅を最大化する必要がある場合は、設定を手動でオフにします。 アップロードは一時停止されますが、この機能では、新たに追加されたファイルのカメラロールへの監視が継続されます。 続行する準備ができたら、アップロードを再度有効にしてください。
- この機能は、デバイス上のユーザーアカウントごとに有効にする必要があります。また、デバイスに現在サインインしているユーザーのファイルのみをアクティブにアップロードできます。
- 設定ページのアップロード数をリアルタイムで監視しているときに写真やビデオを撮影している場合は、現在のファイルのアップロードが完了するまで保留中のファイル数が変更されないことに注意してください。
- デバイスがスリープ状態になった場合、または電源がオフになっている場合、アップロードは一時停止します。 保留中のアップロードが完了したことを確認するには、設定ページが [OneDrive が最新の状態であることを確認するか、**電源 & スリープ** 設定を調整するまで、デバイスをアクティブに使用します。

### <a name="added-support-for-some-telemetry-policies"></a>一部のテレメトリポリシーのサポートを追加しました

HoloLens 2 では、次のテレメトリポリシーがサポートされるようになりました。

- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry と System\ConfigureTelemetryOptInSettingsUx の両方を一緒に使用して、設定アプリのテレメトリと動作を完全に制御する必要があります。

更新プログラムの機能強化と修正:

- カラー調整による主要なビデオの破損を修正します。
- Power menu でテキストが切り捨てられる可能性のある問題に対処します。
- RequirePrivateStoreOnly ポリシーのサポートを有効にします。

## <a name="windows-holographic-version-20h2--june-2021-update"></a>WindowsHolographic、バージョン20H2 –2021年6月更新

- ビルド19041.1154

### <a name="added-support-for-some-telemetry-policies"></a>一部のテレメトリポリシーのサポートを追加しました

HoloLens 2 では、次のテレメトリポリシーがサポートされるようになりました。

- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry と System\ConfigureTelemetryOptInSettingsUx の両方を一緒に使用して、設定アプリのテレメトリと動作を完全に制御する必要があります。

最新のビルド (Windows Holographic、バージョン 21h1) を試すことをお勧めします。

## <a name="windows-holographic-version-1903---june-2021-update"></a>WindowsHolographic、バージョン 1903-6 月2021更新プログラム

- ビルド18362.1116

更新プログラムの機能強化と修正:

- この月間品質更新プログラムには、重要な変更は含まれていません。最新のビルド (Windows Holographic、バージョン 21h1) を試すことをお勧めします。

>[!IMPORTANT]
> このビルドはサービスされなくなります。

## <a name="windows-holographic-version-21h1"></a>WindowsHolographic、バージョン21H1

- ビルド20346.1002

この更新プログラムには、2つの対象ユーザーのための機能が含まれています。エンドユーザーによってデバイス上のすべてのユーザーが使用できる機能と、IT 管理者が構成できる新しいデバイス管理オプション。 次の表は、各ユーザーに関連する機能を示しています。 IT 管理者の場合は、 [it 管理者の更新チェックリスト](#it-admin---update-checklist)を参照してください。
>[!IMPORTANT]
>このビルドに更新するには、HoloLens 2 デバイスが2021年2月の更新プログラム (ビルド 19041.1136) 以降を実行している必要があります。 この機能更新プログラムが利用可能になっていない場合は、まずデバイスを更新してから、もう一度お試しください。

>[!NOTE]
>現在、Microsoft HoloLens 2 では、次のリリースについて、月ごとのサービス更新 (バグおよびセキュリティの修正) がサポートされています。
>
>- WindowsHolographic、バージョン 20H2 (Build 19041.1128 +)
>- WindowsHolographic、バージョン 2004 (Build 19041.1103 +)
>- WindowsHolographic、バージョン 1903 (Build 18362 +)
>
> Windows Holographic バージョン21h1 の導入により、 **Windows Holographic バージョン1903の月単位のサービス更新プログラムを中止** します。 これにより、より新しいリリースに専念し、貴重な改善を続けることができます。

| 機能名                                              | 簡単な説明                                                                      | 対象読者 |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [新しい Microsoft Edge](#introducing-the-new-microsoft-edge)  | 新しい Chromium ベースの Microsoft Edge が HoloLens 2 で使用できるようになりました。 | エンド ユーザー |
[WebXR および 360 ビューアー](#webxr-and-360-viewer) | イマーシブ web エクスペリエンスと360ビデオ再生を試してみてください。 | エンド ユーザー |
[新しい設定アプリ](#new-settings-app) | レガシ設定アプリは、新しい機能と設定を使用して、更新されたバージョンに置き換えられています。 | エンド ユーザー |
[色の調整を表示する](#display-color-calibration) | HoloLens 2 表示の代替カラー プロファイルを選択します。 | エンド ユーザー |
[既定のアプリ ピッカー](#default-app-picker) | ファイルまたはリンクの種類ごとに起動するアプリを選択します。 | エンド ユーザー |
[アプリごとのボリューム制御](#per-app-volume-control) | システムボリュームとは独立してアプリレベルボリュームを制御します。 | エンド ユーザー |
[Web アプリのインストール](#install-web-apps) | 新しい Microsoft Edge ブラウザーを使用して、Microsoft Office などの HoloLens 2 に web アプリをインストールします。 | エンド ユーザー |
[スワイプして入力する](#swipe-to-type) | 指の先端を使用して、holographic キーボードで単語を "スワイプ" します。 | エンド ユーザー |
[[スタート] の [電源] メニュー](#power-menu-from-start) | [スタート] メニューで HoloLens デバイスを再起動してシャットダウンします。 | エンド ユーザー |
[サインイン画面に複数のユーザーが表示される](#multiple-users-listed-on-sign-in-screen) | サインイン画面に複数のユーザーアカウントを表示します。 | エンド ユーザー |
[USB-C 外部マイクのサポート](#usb-c-external-microphone-support) | アプリやリモートアシスタンスで USB C マイクを使用します。 | エンド ユーザー |
[キオスクのビジター自動ログオン](#visitor-auto-logon-for-kiosks) | ビジターアカウントの自動ログオンをキオスクモードで使用できるようにします。 | IT 管理者 |
[キオスクモードでの新しいアプリの新しい AUMIDs](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | AUMIDs は、新しい設定とエッジアプリを対象としています。 | IT 管理者 |
[キオスクモードのエラー処理の改善](#kiosk-mode-behavior-changes-for-handling-of-failures) | キオスクモードでは、空のスタートメニューの前に、グローバルに割り当てられたアクセスを検索します。 | IT 管理者 |
[新しい Settingはページ設定可視性を備えています](#new-settings-uris-for-page-settings-visibility) | 20 + 新しい Setting/PageVisibilityList は、設定ポリシーを対象としています。 | IT 管理者 |
[フォールバック診断の構成](#configuring-fallback-diagnostics-via-settings-app) | 設定アプリでフォールバック診断動作を設定しています。 | IT 管理者 |
[近くのデバイスとの共有](#share-things-with-nearby-devices) | ファイルまたは url を HoloLens から PC に共有します。 | すべて |
[新しい OS 診断トレース](#new-os-diagnostic-traces) | OS の更新のための設定の新しいトラブルシューティングです。 | IT 管理者 |
[配信の最適化のプレビュー](#delivery-optimization-preview) | 複数の HoloLens デバイスからのダウンロードの帯域幅の消費を削減します。 | IT 管理者 |

関連するリリースノートを確認する:

- [HoloLens Emulator アーカイブにアクセスする](/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>新しい Microsoft Edge について

![レガシ Microsoft Edge ロゴから新しい Microsoft Edge ロゴへのアニメーション。](images/new-edge.gif)

新しいMicrosoft Edge[ は、Chromiumオープンソース プロジェクト](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/)を採用して、顧客との互換性を向上し、Web 開発者向けの Web の断片化を減らします。

> [!IMPORTANT]
> この新しい Microsoft Edge は、新しいリリースでは[サポートされなくなった](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/)レガシの Microsoft Edge を自動的に置き換える機能です。

![新しい Microsoft Edge のスクリーンショット。](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>新しい Microsoft Edge を起動する

新しい Microsoft Edge ![新しい Microsoft Edge アイコン。](images/new_edge_logo.png) (青と緑のスワイル アイコンで表されます) は、スタート メニュー にピン留めされ、Web リンクをアクティブ化すると自動的に起動します。

> [!NOTE]
> HoloLens 2 で新しい Microsoft Edge を初めて起動するとき、設定とデータはレガシの Microsoft Edgeからインポートされます。 新しい Microsoft Edge を起動した後も従来の Microsoft Edge を使用し続ける場合、新しいデータは従来の Microsoft Edge から新しい Microsoft Edge には同期されません。

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>新しい Microsoft Edge のポリシー設定を構成する

この新しいMicrosoft Edgeでは、IT 管理者に、従来の Microsoft Edge で以前に使用していたよりも、HoloLens 2 に対するはるかに広範なブラウザー ポリシーのセットを提供します。

新しい Microsoft Edge のポリシー設定の管理の詳細については、次のリソースを参照してください。

- [Microsoft Intune で Microsoft Edge ポリシー設定を構成](/deployedge/configure-edge-with-intune)
- [Microsoft Edge ポリシーと Microsoft Edge ポリシーのマッピング](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome と Microsoft Edge ポリシーのマッピング](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- 完全な [Microsoft Edge Enterprise ドキュメント](/deployedge/)

> [!IMPORTANT]
> 新しい Microsoft Edge でサポートされているブラウザー ポリシーの量が多いので、チームは新しい各ポリシーが HoloLens 2 で動作することを保証できません。 ただし、以前に HoloLens 2 でサポートされている各レガシの Microsoft Edge ポリシーと同等の新しい Microsoft Edge をテストし期待どおりに機能することを確認しました。 HoloLens 2 で使用していた各レガシ Microsoft Edge ブラウザー ポリシーと同等の新しい Microsoft Edge を確認するには、「[Microsoft Edge レガシと Microsoft Edge ポリシーのマッピング](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)」を参照してください。
>
> 次の 2 つ以上の当社が把握している新しい Microsoft Edge ポリシーは、HoloLens 2 では機能 *しません*。
>
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>HoloLens 2 で新しい Microsoft Edge から期待するもの

新しい Microsoft Edge は、新しい UWP アダプター レイヤーを備え、HoloLens 2 のような UWP 専用デバイスで実行できるネイティブ Win32 アプリなので、一部の機能はすぐには使用できない場合があります。 今後数か月間に新しいシナリオと機能をサポートする予定なので、この領域で最新の情報を確認してください。

**機能することが想定されるシナリオと機能:**

- 初回実行エクスペリエンス、プロファイルへのサインイン、同期
- Web サイトがレンダリングされ、期待どおりに動作する必要がある
- ほとんどのブラウザー機能 (お気に入り、履歴など) は期待した通りに動作する必要があります
- ダーク モード
- デバイスへの Web アプリのインストール
- 拡張機能のインストール (HoloLens 2 上で正常に機能しない拡張機能がある場合は、お知らせください)
- PDF の表示と設定
- 1 つのブラウザー ウィンドウからの空間サウンド
- ブラウザーの自動更新と手動更新
- [印刷] メニューから PDF を保存する ([PDF に保存] オプションを使用)
- WebXR および 360 ビューアー拡張機能
- 環境内に配置された複数のウィンドウ間で参照する場合の、正しいウィンドウへのコンテンツの復元

**機能することが想定されないシナリオと機能:**

- 同時オーディオ ストリームを使用した複数のウィンドウからの空間サウンド
- 「見て発音する」
- 印刷

**ブラウザーに関する既知の問題:**

- ホログラフィック キーボードの拡大鏡プレビューは、新しい Microsoft Edge では無効になっています。 拡大が正しく機能したら、今後の更新プログラムでこの機能を再び有効にしてください。
- 別のブラウザー ウィンドウが開いておりアクティブな場合、間違ったブラウザー ウィンドウからオーディオが再生される可能性があります。 この問題を回避するには、オーディオを再生していてはいけない他のアクティブ ウィンドウを閉じます。
- "フォローする" [モード](hololens2-basic-usage.md#follow-me-stop-following)でブラウザーウィンドウからオーディオを再生するときに、"フォローする" モードを無効にすると、オーディオの再生が続行されます。 この問題を回避するには、"フォローする" モードを無効にする前にオーディオの再生を停止するか、[ **X** ] ボタンを使用してウィンドウを閉じます。
- アクティブな Microsoft Edge ウィンドウとやりとりすると、他の 2D アプリ ウィンドウが予期せず非アクティブになる可能性があります。 これらのウィンドウは、もう一度操作すれば再アクティブ化できます。

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider アイコン

このMicrosoft Edge チームは、Edge Insider コミュニティで 3 つのプレビュー チャネル (ベータ、開発、カナリア) を利用できます。 プレビュー チャネルをインストールしても、リリースされたバージョンの Microsoft Edge は HoloLens 2 でアンインストールされません。また、複数を同時にインストールできます。

Edge Insider コミュニティの詳細については、[Microsoft Edge Insider](https://www.microsoftedgeinsider.com) のホームページを参照してください。 さまざまな Edge Insider チャネルの詳細と使用を開始するには、[Edge Insider のダウンロード ページ](https://www.microsoftedgeinsider.com/download)を参照してください。

Microsoft Edge Insider チャネルを HoloLens 2 にインストールするには、複数の方法があります。

**デバイスへの直接インストール (現在はアンマネージド デバイスでのみ使用可能)**

  1. お使いの HoloLens 2 で、[Edge Insider ダウンロード ページ](https://www.microsoftedgeinsider.com/download)にアクセスします。
  1. インストールする Edge Insider チャネルの **[HoloLens 2 のためにダウンロード]** ボタンを選択します。
  1. ダウンロードした .msix ファイルを Edge ダウンロード キューから、またはデバイスの "ダウンロード" フォルダーから起動します (エクスプローラーを使用)。
  1. [アプリ インストーラー](app-deploy-app-installer.md)が起動します。
  1. **[インストール]** ボタンを選択します。
  1. インストールが成功すると、スタートメニューの **[すべてのアプリ]** の一覧に、Microsoft Edge Beta、Dev、または Canary が別のエントリとして表示されます。

**コンピューターを使用してWindows デバイス ポータル(HoloLens 2 で [開発者モード](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)を有効にする必要あり) をインストールします**

  1. お使いのコンピュータで、[Edge Insider ダウンロード ページ](https://www.microsoftedgeinsider.com/download)にアクセスします。
  1. インストールする Edge Insiderチャネルの [Windows 10 用にダウンロード] ボタンの横にある **ドロップダウン矢印ボタン** を選択します。
  1. ドロップダウンの **[HoloLens 2]** を選択します。
  1. .msix ファイルを PC の "ダウンロード" フォルダー (または簡単に見つけられている別のフォルダー) に保存します。
  1. PC 上の[Windows デバイス ポータル](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)を使用して、HoloLens 2 上のダウンロードした .msix ファイルをインストールします。
  1. インストールが成功すると、スタートメニューの **[すべてのアプリ]** の一覧に、Microsoft Edge Beta、Dev、または Canary が別のエントリとして表示されます。

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>WDAC を使用して新しい Microsoft Edge をブロック

[WDAC ポリシー](windows-defender-application-control-wdac.md)を更新して新しい Microsoft Edge アプリをブロックする IT 管理者の場合は、ポリシーに次を追加する必要があります。

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>新しい Microsoft Edge のエンドポイントを管理する

一部の環境には、考慮すべきネットワーク制限がある場合があります。 新しい Edge でスムーズなエクスペリエンスを実現するには、[これらの Microsoft エンドポイントを有効にして](/deployedge/microsoft-edge-security-endpoints)ください。

現在使用可能な[ HoloLens 用エンドポイントの詳細について](hololens-offline.md)参照してください。

### <a name="install-web-apps"></a>Web アプリのインストール

 > [!Note]
>[Holographic Windowsバージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1)では、Office Web アプリはプレインストールされなくなりました。

新しい Edge を使用して、Microsoft Store アプリと共に Web アプリをインストールします。 たとえば、Microsoft Office Web アプリをインストールして、SharePoint または OneDrive でホストされているファイルを表示および編集できます。 Office Web アプリをインストールするには、 https://www.office.com にアクセスし、アドレス バーの **[使用可能なアプリ]** または **[Office をインストール]**  ボタンをクリックします。 **[インストール]** を選択 して確定します。

> [!IMPORTANT]
> Office Web アプリの機能は、HoloLens 2 にアクティブなインターネットがある場合にのみ使用できます。

### <a name="webxr-and-360-viewer"></a>WebXR および 360 ビューアー

新しいMicrosoft Edge には WebXR のサポートが含まれています。これは、イマーシブ Web エクスペリエンスを作成するための新しい標準です (WebVR の後継)。 多くのイマーシブ Web エクスペリエンスは、VR を念頭に置いて設計されました (実際の視野を仮想環境に置き換えます)。ただし、これらのエクスペリエンスは、HoloLens 2 でもサポートされています。 WebXR 標準では、物理環境を使用する拡張および Mixed Reality のイマーシブ Web エクスペリエンスも可能になります。 開発者が WebXR により多くの時間を費やすと、HoloLens 2 のお客様が新しい拡張および Mixed Reality イマーシブ エクスペリエンスを試せるようになる予定です!

360 Viewer 拡張機能は WebXR 上に構築され、HoloLens 2 上で新しい Microsoft Edge と共に自動的にインストールされます。 この Web 拡張機能を使用すると、360 度のビデオに取り入れすることができます。 YouTube では最大 360 本の動画が提供されているため、そこから開始することをお勧めします。

#### <a name="how-to-use-webxr"></a>WebXR の使用方法

1. WebXR がサポートされている Web サイトに移動します。
1. Web サイトの **[VR の入力]** ボタンを選択します。 このボタンの場所と視覚的な表現は、Web サイトごとに異なる場合がありますが、次のような場合があります。

    ![ENTER VR ボタンの例。](images/75px-enter-vr.png)

1. 特定のドメインで初めて WebXR エクスペリエンスを起動しようとすると、ブラウザーでイマーシブ ビューに入る同意を求められます。 **[許可]** を選択 してください。
1. [HoloLens 2 ジェスチャ](hololens2-basic-usage.md#the-hand-tracking-frame) を使用して、エクスペリエンスを操作します。
1. エクスペリエンスに **[終了]** ボタンがない場合は、[スタート ジェスチャ](hololens2-basic-usage.md#start-gesture)を使用してホームに戻ります。

**推奨される WebXR サンプル**

- 360 ビューアー (次のセクションを参照)
- [XR Dinosaurs](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>360 ビューアーの使い方

1. YouTube で 360 度のビデオに移動します。
1. ビデオ フレームで、[Mixed Reality ヘッドセット] ボタンを選択します。

    ![360 ビューアーをアクティブ化するボタン。](images/enter-360-viewer.jpg)

1. 特定のドメインで初めて 360 ビューアーを起動しようとすると、ブラウザーでイマーシブ ビューに入る同意を求められます。 **[許可]** を選択します。
1. [エア タップ](hololens2-basic-usage.md#select-using-air-tap) で再生コントロールを表示します。 [ハンド レイとエア タップ](hololens2-basic-usage.md#select-using-air-tap) を使用して、再生/一時停止、前方/戻るスキップ、キャプションのオン/オフの切り替え、エクスペリエンスの停止 (イマーシブ ビューを終了) を行います。 再生コントロールは、数秒の非アクティブ状態の後に消えます。

#### <a name="top-webxr-and-360-viewer-known-issues"></a>WebXR と 360 ビューアーの既知の問題

- WebXR エクスペリエンスの複雑さによっては、フレームレートが低下したり、つまずく場合があります。
- WebXR での多関節手関節のサポートは、既定では有効になっていません。 開発者は、"WebXR ハンド入力" をオンにすることで、 を使用 `edge://flags` してサポートを有効にできます。
- YouTube 以外の Web サイト 360 本の動画は想定通り動作しない場合があります。

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>WebXR と 360 ビューアーに関するフィードバックの提供

新しい Microsoft Edge の **フィードバックを送る** 機能を通じて当社のチームにフィードバックやバグをお知らせください。

### <a name="new-settings-app"></a>新しい設定アプリ

このリリースでは、新しいバージョンの新しい 設定しています。 新しい設定アプリには、サウンド、電源とスリープ、ネットワークとインターネット、アプリ、アカウント、コンピューターの簡単操作などの領域における HoloLens 2 の新機能と拡張設定が含まれています。

> [!NOTE]
> 新しい設定アプリは従来の設定アプリとは別であるため、以前に環境に配置した設定の windows は、更新時に削除されます。

![新しい設定アプリのホームページ。](images/new-settings-app.png)

**新機能と設定**

- 設定の検索: キーワードまたは設定の名前を使用して、設定ホームページから設定を検索します。
- [システム] > [サウンド]:
  - 入出力オーディオ デバイス: 入力と出力のオーディオ デバイスを個別に選択します (たとえば、Bluetooth ヘッドホンを使用してオーディオをリッスンするか、オーディオ入力に USB C マイクを使用します)。
    > [!NOTE]
    > Bluetooth のマイクは、HoloLens 2 ではサポートされていません。
  - アプリのボリューム: 各アプリのボリュームを個別に調整します。 [「アプリごとのボリューム制御」](#per-app-volume-control)を参照してください。
- [システム] > [電源とスリープ]: 操作のない状態が一定期間続いた後にスリープに移行するときに選択します。
- [システム] > [バッテリ]: バッテリ節約モードを手動で有効にするか、バッテリ省モードが自動的にオンになるようにバッテリのしきい値を設定します。
- [デバイス] > [USB]: USB 接続を既定で無効にすることができます。
- ネットワークとインターネット:
  - USB-C イーサネット アダプタが、[ネットワークとインターネット] に表示されます。
  - USB-C イーサネットアダプターの設定が、IP アドレスを含めて使用できるようになりました。
  - HoloLens 2 で機内モードを有効にできるようになりました。
- アプリ: ファイルとリンクの種類に使用される既定のアプリをリセットできます。 詳細については、[「既定のアプリ ピッカー」](#default-app-picker)を参照してください。
- [アカウント] > [他のユーザー]: デバイス所有者は、ユーザーを追加し、標準ユーザーをデバイス所有者にアップグレードし、デバイス所有者を標準ユーザーにダウングレードして、ユーザーを削除することができます。
- 簡単操作: テキストのサイズと視覚効果を変更します。

**既知の問題**

- 以前に配置した設定ウィンドウは削除されます (上のメモを参照)。
- 設定アプリでは、デバイスの名前を変更できなくなります。 IT 管理者は、[Windows Autopilot for HoloLens 2](hololens2-autopilot.md) のデバイス名テンプレートまたは MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName ノードを使用してデバイスの名前を変更できます。
- イーサネットのページには、常に仮想イーサネットデバイス ("UsbNcm") が表示されます。
- 新しい Microsoft Edge のバッテリ使用量は、UWP アダプター レイヤーによってサポートされている Win32 デスクトップ アプリケーションの性質上、正確ではない可能性があります (近日対応予定の修正プログラムはありません)。

#### <a name="display-color-calibration"></a>色の調整を表示する

この新しい設定を使用すると、表示する別の色プロファイルをHoloLens 2できます。 これにより、特にディスプレイの明るさが低いレベルで、色が正確に表示される場合があります。 ディスプレイの色の調整は、設定の [System > の調整] ページで確認できます。

> [!NOTE]
> この設定により、ディスプレイ ファームウェアに新しいカラー プロファイルが保存されるため、デバイスごとの設定になります (各ユーザー アカウントに固有ではありません)。

##### <a name="how-to-use-display-color-calibration"></a>ディスプレイの色の調整を使用する方法

1. **設定** アプリを起動して、 **[システム] > [調整]** に移動します。
1. **[ディスプレイの色の調整]** で、 **[ディスプレイの色の調整を実行する]** ボタンを選択します。
1. ディスプレイのカラー調整エクスペリエンスが起動し、バイザーが正しい位置にあることを確認することをお勧めします。
1. 指示のダイアログボックスが表示された後、ディスプレイは自動的にグレーで30% の明るさになります。
    > [!TIP]
    > お使いの環境で単色表示されているシーンが表示されない場合は、デバイスの左側にある [明るさ] ボタンを使用して HoloLens 2 の明るさのレベルを手動で調整できます。
1. ボタン1-6 を選択すると、各カラープロファイルが瞬時に表示され、最もよく見られるものを見つけることができます (これは通常、シーンを最もニュートラルにするのに役立つプロファイルで、グレースケール パターンとスキントーンが予想どおりに見えることを意味します)。

    ![ディスプレイの色の調整シーン。](images/color-cal-ui.png)

1. 選択したプロフィールに満足している場合、 **[保存して終了]** ボタンを選択します
1. 変更しない場合は、 **[キャンセル して終了]** ボタンを選択すると、変更が元に戻されます

> [!TIP]
> ディスプレイの色の調整設定を使用する際に留意すべき便利なヒントを次に示します。
>
> - 必要に応じて、設定からディスプレイの色の調整を再実行することができます
> - デバイス上のすべてのユーザーが以前にカラー プロファイルを変更する設定を使用していた場合は、最新の変更の日付/時刻が [設定] ページに反映されます
> - ディスプレイの色の調整を再実行すると、以前に保存されたカラープロファイルが強調表示され、プロファイル 0 は表示されません (プロファイル 0 はディスプレイの元のカラープロファイルを表します)
> - ディスプレイの元のカラー プロファイルに戻す場合は、[設定] ページから変更できます ([「カラープロファイルをリセットする方法」](#how-to-reset-color-profile)を参照してください)

##### <a name="how-to-reset-color-profile"></a>カラープロファイルをリセットする方法

HoloLens 2 に保存されたカスタム カラー プロファイルに不満がある場合は、デバイスの元のカラー プロファイルを復元できます。

1. **設定** アプリを起動して、 **[システム] > [調整]** に移動します。
1. **[ディスプレイの色の調整]** で、 **[既定のカラー プロファイルにリセット]** ボタンを選択します。
1. ダイアログ ボックスが開いたら、HoloLens 2 を再起動して変更を適用する準備ができたら、 **[再起動]** を選択します。

#### <a name="top-display-color-calibration-known-issues"></a>最上位のディスプレイの色の調整に関する既知の問題

- [設定 ページで、カラー プロファイルが最後に変更された日時を示す状態文字列は、そのページのページを再度読み込むまで設定。
    - 回避策: 別の設定ページを選択し、[調整] ページを再選択します。

#### <a name="default-app-picker"></a>既定のアプリ ピッカー

ハイパーリンクをアクティブにするか、複数のインストール済みアプリを含むファイルの種類を開いた場合、新しいウィンドウが開き、ファイルまたはリンクの種類を処理するインストール済みアプリを選択するように求めるメッセージが表示されます。 このウィンドウでは、選択したアプリがファイルまたはリンクの種類を「一度のみ」または「常時」として処理するように選択することもできます。

[常時] を選択した後、特定のファイルまたはリンクの種類を処理するアプリを変更する場合は、 **[設定] > [アプリ]** で保存されている既定値をリセットできます。 ページの一番下までスクロールし、[ファイルの種類の既定のアプリ] または [リンクの種類の既定のアプリ] の下にある **[クリア]** ボタンを選択します。 デスクトップ PC の同様の設定とは異なり、個々のファイルの種類の既定値をリセットすることはできません。

#### <a name="per-app-volume-control"></a>アプリごとのボリューム制御

このビルドWindows、ユーザーは各アプリのボリューム レベルを手動で調整できます。 これにより、ユーザーは、必要なアプリに集中することができます。また、複数のアプリを使用する場合は、より適切に聞くことができます。 たとえば、あるアプリのボリュームを下げる必要があるものの、別のユーザーは別の場所でリモート アシスタンスが必要な場合などです。

個々のアプリのボリュームを設定するには **[設定]**  >  **[システム]**  >  **[サウンド]** に移動し、[高度なサウンドオプション] で **[アプリのボリュームとデバイスの設定]** を選択します。<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>スワイプして入力する

一部のお客様は、入力する予定の単語の形をスワイプすることで、仮想キーボードで "入力" する方が速く見つかり、ホログラフィック キーボード用にこの機能をプレビューしています。 ホログラフィック キーボードの平面に指のチップを渡し、単語の形をスワイプし、キーボードの平面から指の先を引き出して、一度に 1 つの単語をスワイプできます。 単語と単語の間ではキーボードから指を離せば、スペース バーを押さなくてもフォローアップ ワードをスワイプできます。 キーボード上で指の動きの後にスワイプ の跡が見えれば、機能が動作しているということです。

この機能は、(携帯電話のディスプレイとは異なり) 指に抵抗を感じないホログラフィック キーボードの性質上、使い方をマスターするのが難しい場合があります。 

### <a name="power-menu-from-start"></a>[スタート] の [電源] メニュー

ユーザーがデバイスをサインアウト、シャットダウン、再起動できる新しいメニュー。 システム更新プログラムが使用可能な場合に表示される HoloLens スタート画面のインジケーター。

#### <a name="how-to-use"></a>使用方法

1. [スタート ジェスチャ](hololens2-basic-usage.md#start-gesture)を使うか、「ホームに移動」と言って HoloLensの開始画面を開きます。

2. ユーザー プロファイルの画像の横にある省略記号アイコン (...) に注意してください。<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. 手または音声コマンド "Power" を使用して、ユーザー プロファイルの画像を選択します。

4. メニューが表示され、デバイスのサインアウト、再起動、シャットダウンのオプションが表示されます。<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. メニュー オプションを選択して、HoloLens をサインアウト、再起動、またはシャットダウンします。 デバイスが [1 つの Microsoft アカウント (MSA) またはローカル アカウント](hololens-identity.md)に設定されている場合は、[サインアウト ] オプションを使用できない場合があります。

6. メニューを閉じるには、他の場所にタッチするか、スタート ジェスチャでスタート メニューを閉じる必要があります。

#### <a name="update-indicator"></a>インジケーターの更新

更新プログラムが使用可能な場合は、更新プログラムが再起動によってインストールされるという省略記号アイコンが表示されます。更新プログラムの存在を反映するようにメニュー オプションも変更されます。<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>[サインイン] 画面に表示される複数のユーザー

以前は、[サインイン] 画面には、最近サインインしたユーザーと "その他のユーザー" エントリ ポイントだけが表示されました。 複数のユーザーがデバイスにサインインしている場合は、これでは十分ではないというお客様からのフィードバックを受け取っています。 それでも、ユーザー名などを再入力する必要があります。

この Windows ビルドで導入された[PIN エントリ]フィールドの右側にある [その他のユーザー] を選択すると、[サインイン] 画面に、以前にデバイスにサインインしたユーザーが複数表示されます。 これにより、ユーザーは自分のユーザー プロファイルを選択し、自分の資格情報を使用Windows Helloできます。 [アカウントの追加] ボタンを使用して、この [その他のユーザー] ページからデバイスに新しい **ユーザーを追加** することもできます。

[その他のユーザー] メニューの [その他のユーザー] ボタンには、デバイスにサインインした最後のユーザーが表示されます。 このボタンを選択すると、このユーザーのサインイン画面に戻ります。

![サインイン画面の既定値。](./images/multiusers1.jpg)

<br>

![他のユーザーのサインイン画面。](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C 外部マイクのサポート

> [!IMPORTANT]
> USB マイクを **接続すると、入力デバイス として自動的に設定されません**。 USB-C の一連のヘッドセットを接続すると、ユーザーは、ヘッドセットのオーディオが自動的にヘッドセットにリダイレクトされるのを確認しますが、HoloLens OS では、他の入力デバイスよりも内部マイク 配列の優先順位が優先されます。 **USB-C マイクを使用するには、次の手順に従います。**

ユーザーは、 **[サウンド]** 設定パネルを使用して USB-C 接続外部マイク を 選択できます。 USB-C マイクは、通話や録音などに使用できます。

**設定** アプリを開いて **[システム]**  >  **[サウンド]** を選択します。

![サウンド設定。](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> 外部マイクを **Remote Assist** で使用するには、[サウンド デバイスの管理] ハイパーリンクをクリックする必要があります。
>
> 次に、ドロップダウンを使用して、外部マイクを **[既定]** または **[通信の既定値]** に設定します。 **[既定]** を選択すると、外部マイクはどこででも使用されます。
>
> **[通信の既定値]** を選択すると、外部マイクは Remote Assist や他の通信アプリで使用されますが、HoloLens マイク 配列は他のタスクにも引き続き使用できます。

![サウンド デバイスを管理する。](images/usbc-mic-2.png)

<br>

![マイクの既定値を設定する。](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Bluetooth のマイクのサポートについてはどうですか?

残念Bluetoothマイクは、現在のところ現在サポートHoloLens 2。

#### <a name="troubleshooting-usb-c-microphones"></a>USB-C マイクのトラブルシューティング

一部の USB-C マイクでは、マイクとスピーカーの両方として誤って報告される *点に* 注意してください。 これはマイクの問題であり、マイクには問題HoloLens。 これらのマイクの 1 つをデバイスに接続HoloLens音が失われる可能性があります。 さいわい、簡単な修正があります。  

**[設定** サウンド] で、組み込みのスピーカー (アナログ機能オーディオ ドライバー) を既定のデバイス として明示的  >    >  **に設定します**。  HoloLensマイクが削除され、後で再接続された場合でも、この設定を覚えておく必要があります。

![USB-C マイクのトラブルシューティング。](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>キオスクのビジター自動ログオン

この新機能により、キオスク モードでビジター アカウントの自動ログオンを使用できます。

管理者以外の構成AAD、訪問者の自動ログオン用にデバイスを構成するには、次の手順を実行します。

1. 次のプロビジョニング パッケージを作成します。
    1. ビジター アカウント **を許可するランタイム設定/AssignedAccess** を構成します。
    1. 後で管理できるよう、必要に応じてデバイスを MDM **(ランタイム設定/ワークプレース/登録)** に登録します。
    1. ローカル アカウントを作成しない
1. [プロビジョニング パッケージ を適用します](hololens-provisioning.md)。

構成をAAD、ユーザーは、この変更を行わずに、今日のようなことを実現できます。 AADモード用に構成された参加済みデバイスは、サインイン画面から 1 つのボタン タップで Visitor アカウントにサインインできます。 ビジター アカウントにサインインすると、ビジターがスタート メニューから明示的にサインアウトするか、デバイスが再起動されるまで、デバイスは再度サインインを求めるメッセージを表示しません。

ビジター自動ログオンは、カスタム [OMA-URI ポリシーを使用して管理](/mem/intune/configuration/custom-settings-windows-10) できます。

- URI 値: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| ポリシー  | 説明   | 構成  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | キオスクへの訪問者の自動ログオンを許可する   | 1 (はい)、0 (いいえ、既定値)。  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>キオスク モードで新設定 Edge アプリを使用する

キオスクにアプリを [含めた](hololens-kiosk.md)場合、IT 管理者は多くの場合、キオスクにアプリを追加しますが、アプリ ユーザー モデル ID (AUMID) を使用します。 設定 アプリと Microsoft Edge アプリの両方が新しいアプリと見なされ、それらのアプリに AUMID を使用する古いアプリ キオスクとは異なるので、新しい AUMID を使用するには更新する必要があります。

キオスクを変更して新しいアプリを含める場合は、新しい AUMID に を追加し、古いアプリを残することをお勧めします。 これにより、ユーザーが OS を更新するときに簡単に切り替わるので、キオスクを意図した方法で使用し続ける新しいポリシーを受け取る必要がなされます。

| アプリ                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| 古設定アプリ       | HolographicSystemSettings_cw5n1h2txyewy!アプリ            |
| 新設定 アプリ       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!アプリ |
| 古いMicrosoft Edgeアプリ | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| 新Microsoft Edgeアプリ | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>エラー処理のためのキオスク モードの動作の変更

以前のビルドでは、デバイスにキオスク構成 (グローバル割り当てアクセスと AAD グループ メンバー割り当てアクセスの両方の組み合わせ) がある場合、AAD グループ メンバーシップが[](hololens-kiosk.md#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode)失敗したと判断すると、ユーザーには "何も表示されません" メニューが表示されます。

このリリースWindows、キオスク エクスペリエンスは、グループ キオスク モードで障害が発生した場合にグローバル キオスク構成 (存在する場合) AADフォールバックします。

### <a name="new-settings-uris-for-page-settings-visibility"></a>ページ設定可視性の新しい 設定 URI

[Holographic Windowsバージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2)では[、設定/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)ポリシーを追加して、設定 アプリ内に表示されるページを制限しました。 PageVisibilityList は、IT 管理者がシステム設定アプリの特定のページを表示またはアクセスできないようにしたり、または指定されたページ以外のすべてのページで同様に行うことを許可するポリシーです。

Page 設定[Visibility に](settings-uri-list.md)アクセスする場合は、この CSP を使用する手順と、以前のリリースで使用できる URI の一覧を確認できます。

IT 管理者が管理できる利用可能な 設定の一覧を拡張しています。 これらの URI の一部は、新しいアプリ内で新しく使用可能な領域設定されています。 設定/PageVisibilityList ポリシーを使用している場合は、次の一覧を確認し、必要に応じて許可またはブロックされたページを調整します。

> [!NOTE]
> **非推奨: ms-settings:network-proxy**
>
> これらの新しいビルドでは、1 つの設定ページが非推奨とされます。 古い **[ネットワーク & インターネット**  >  **プロキシ]** ページは、グローバル設定として使用できなくなりました。 新しい接続ごとのプロキシ設定は、[ネットワーク]の [インターネット Wi-Fi プロパティ] & [ネットワーク] [インターネット イーサネットのプロパティ] &  >    >  **で**  >  **確認**  >  **できます**。

<br>

| [設定] ページ                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Apps > Apps &機能                               | `ms-settings:appsfeatures`                         |
| アプリ > Apps &の機能>詳細オプション          | `ms-settings:appsfeatures-app`                     |
| オフライン >アプリ                                  | `ms-settings:maps`                                 |
| オフライン >アプリとダウンロード > マップ                  | `ms-settings:maps-downloadmaps`                    |
| マウス>デバイス                                      | `ms-settings:mouse`                                |
| USB > デバイス                                        | `ms-settings:usb`                                  |
| ネットワーク & インターネット > 機内モード                   | `ms-settings:network-airplanemode`                 |
| プライバシー > 全般                                    | `ms-settings:privacy-general`                      |
| プライバシー > インク & 個人設定の入力             | `ms-settings:privacy-speechtyping`                 |
| プライバシー > モーション                                     | `ms-settings:privacy-motion`                       |
| プライバシー > スクリーンショットの枠線                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| プライバシー > スクリーンショットとアプリ                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| システム > バッテリ                                     | `ms-settings:batterysaver`                         |
| システム > バッテリ                                     | `ms-settings:batterysaver-settings`                |
| システム > サウンド                                       | `ms-settings:sound`                                |
| システム > サウンド > アプリのボリュームとデバイスの基本設定 | `ms-settings:apps-volume`                          |
| システム > サウンド > サウンドデバイスの管理              | `ms-settings:sound-devices`                        |
| システム > Storage > Storage Sense の構成         | `ms-settings:storagepolicies`                      |
| 時刻 & 言語 > 日付 & 時刻                        | `ms-settings:dateandtime`                          |
| 時刻 & 言語 > キーボード                           | `ms-settings:keyboard`                             |
| 時刻 & 言語 > 言語                           | `ms-settings:language`                             |
| 時刻 & 言語 > 言語                           | `ms-settings:regionlanguage-languageoptions`       |
| 更新 & セキュリティ > リセット & 回復               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>更新された Uri

以前は、次の2つの Uri は、指定されたページに直接ユーザーを移動しませんが、メイン更新ページはブロックされています。 次の項目が更新され、ページに直接移動しました。

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>設定アプリを使用したフォールバック診断の構成

現在設定アプリでは、ユーザーは[フォールバック診断](hololens-diagnostic-logs.md)の動作を構成できます。 設定アプリで、プライバシーに  >  **関するトラブルシューティング** ページに移動し、この設定を構成します。

> [!NOTE]
> デバイスに MDM ポリシーが構成されている場合、ユーザーはその動作をオーバーライドすることはできません。  

### <a name="share-things-with-nearby-devices"></a>近くのデバイスとの共有

pc とその他の HoloLens 2 デバイスの両方を含めて、Windows 10 デバイスの近くで共有できます。   >    >  HoloLens から PC にファイルまたは url を共有するために設定システム **共有エクスペリエンス** で試してみることができます。 詳細については、 [Windows 10 で近くのデバイスと項目を共有](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)する方法を参照してください。

この機能は、 [接続/AllowConnectedDevices](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)を介して管理できます。

### <a name="new-os-diagnostic-traces"></a>新しい OS 診断トレース

設定アプリ内の前のトラブルシューティングツールに加えて、新しいトラブルシューティングツールが追加されました。 OS 更新プログラム用の新しい設定アプリが追加されました。 **設定**  >  **更新の &amp; セキュリティ**  >  **トラブルシューティング**  >  **Windows Update** に移動し、[**開始**] を選択します。 これにより、OS の更新に関する問題を再現しながら、IT またはサポートによるトラブルシューティングを容易にするために、トレースを収集することができます。

### <a name="delivery-optimization-preview"></a>配信の最適化のプレビュー

この HoloLens の更新により、Windows Holographic for Business は配信の最適化の設定を有効にして、複数の HoloLens デバイスからのダウンロードにかかる帯域幅の消費を削減します。 推奨されるネットワーク構成と共に、この機能の詳細な説明については、[「Windows 10 更新プログラムの配信の最適化」](/windows/deployment/update/waas-delivery-optimization)を参照してください。

次の設定は管理画面の一部として有効にされ、[Intune から構成できます](/mem/intune/configuration/delivery-optimization-settings)。

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

このプレビューの内容に関する注意点を次に示します。

- HoloLens のサポートは、このプレビューでは OS の更新プログラムにのみ制限されます。
- Windows Holographic for Business は、HTTP ダウンロード モードと [Microsoft 接続キャッシュ エンドポイント](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)からのダウンロードのみをサポートします。ピア ツー ピア のダウンロード モードとグループの割り当ては、現時点では HoloLens デバイスではサポートされていません。
- HoloLens では、Windows Server Update Services エンドポイントのデプロイまたは配信の最適化はサポートされていません。
- トラブルシューティングを行う場合は、接続キャッシュ サーバーでの診断、または **[設定]**  >  **[アップデートとセキュリティ]**  >   **[トラブルシューティング]**  >   **[Windows Update]** を介して HoloLens 上で HoloLens のトレースを収集する必要があります。

### <a name="it-admin---update-checklist"></a>IT 管理者-更新プログラムのチェックリスト

このチェックリストは、現在のデバイス管理構成に影響を与える可能性がある、この機能更新プログラムに追加される新しい項目、または使用を開始する新機能を理解するのに役立ちます。

#### <a name="updates-to-kiosk-mode"></a>キオスクモードの更新プログラム

[**キオスクモードで新しいアプリの新しい AUMIDs を**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)✔️します。

キオスクで設定アプリまたは Microsoft Edge アプリを以前に使用していた場合、これらのアプリは別のアプリ ID を使用する新しいアプリに置き換えられました。 以下 [のキオスクモードで新しいアプリの新しい AUMIDs](#use-the-new-settings-and-edge-apps-in-kiosk-modes) を読むことを強くお勧めします。 これにより、キオスクで設定アプリを引き続き使用するか、新しい Microsoft Edge アプリを含めることができます。 これらの変更は、今すぐ実行し、すべてのデバイスに展開して、更新をスムーズに移行できるようにすることができます。

[**キオスクの✔️ビジターの自動ログオン**](#visitor-auto-logon-for-kiosks):

訪問者がキオスクに自動的にログインできるようになりました。 この動作は既定で有効になっていますが、管理と無効化を行うことができます。

✔️ [**キオスクモードのエラー**](#kiosk-mode-behavior-changes-for-handling-of-failures)処理の改善:

サインインしている AAD ユーザーのグループメンバーシップが正常に決定されていない AAD 場合、[スタート] メニュー (存在する場合) にはグローバルキオスク構成が使用され、それ以外の場合は空の [スタート] メニューが表示されます。 空の [スタート] メニューは、直接設定できる構成ではありませんが、キオスクを使用している場合は、この新しい処理によってサポート部門に通知されることがあります。これは、構成に適用される可能性があります。また、割り当てられているアクセス構成に新しい調整を加える必要があります。

#### <a name="updates-to-page-settings-visibility"></a>ページ設定表示の更新

[**ページ設定可視性の新しい設定 uri** ✔️](#new-settings-uris-for-page-settings-visibility)

現在、[ページ設定可視性](settings-uri-list.md)を使用している場合は、許可またはブロックされている既存の uri に対して調整を行うことができます。

#### <a name="updates-for-your-wdac-policy"></a>WDAC ポリシーの更新

✔️、以前に wdac 経由で Microsoft Edge をブロックしていた場合は、wdac ポリシーを更新する必要があります。 次の内容を確認し、提供されているサンプルコードを使用してください。

#### <a name="enable-new-endpoints-for-edge"></a>エッジの新しいエンドポイントを有効にする

✔️プロキシやファイアウォールなどのネットワークエンドポイントを構成するインフラストラクチャがある場合は、新しい Microsoft Edge アプリに対してこれらの新しいエンドポイントを有効にしてください。

#### <a name="newly-configurable-items"></a>新しく構成可能な項目

[フォールバック診断の構成](#configuring-fallback-diagnostics-via-settings-app)✔️: フォールバック診断を収集するかどうかを構成できます。

[近くのデバイスで項目を共有](#share-things-with-nearby-devices)✔️: 新しい近くにある共有機能を無効にすることができます。

[新しい Microsoft Edge のポリシー設定を構成](#configuring-policy-settings-for-the-new-microsoft-edge)✔️には、Microsoft Edge で使用できるようになった新たな構成を確認します。

#### <a name="new-diagnostic-tool"></a>新しい診断ツール

[新しい os 診断トレース](#new-os-diagnostic-traces)の✔️: Os の更新に関連するログを収集します。

### <a name="improvements-and-fixes-in-the-update"></a>更新プログラムの機能強化と修正:

- [オフライン診断](hololens-diagnostic-logs.md#offline-diagnostics) には、シリアル番号と OS バージョン用の追加のデバイス情報も含まれます。
- ランタイムプロビジョニングパッケージを使用した基幹業務アプリケーションの展開に関する問題を修正します。
- 基幹業務アプリケーションのインストール状態レポートに関する問題を修正しました。
- デバイスのリセットを通じて新しいアプリパッケージの永続化に関する問題を修正します。
- 日本のお客様に対して、エッジに間違った記号が入力された場合に発生する可能性のある問題を修正します。
- エッジなど、プレインストールされているアプリに関連する OS 更新プログラムの回復性を向上させます。
- Microsoft Edge のインストールに影響を与える更新の信頼性に対処します。

## <a name="windows-holographic-version-20h2--may-2021-update"></a>WindowsHolographic、バージョン20H2 –2021年5月更新

- ビルド19041.1146

更新プログラムの機能強化と修正:

- この月間品質更新プログラムには、重要な変更は含まれていません。最新のビルド (Windows Holographic、バージョン 21h1) を試すことをお勧めします。

## <a name="windows-holographic-version-1903---may-2021-update"></a>WindowsHolographic、バージョン 1903-2021 更新プログラム

- ビルド18362.1110

更新プログラムの機能強化と修正:

- この月間品質更新プログラムには、注目すべき変更は含まれていません。 **このビルドは、月ごとのサービス更新を受信しなく** なります。 最新のビルド (Windows Holographic、バージョン 21h1) を試すことをお勧めします。

## <a name="windows-holographic-version-20h2---april-2021-update"></a>WindowsHolographic バージョン 20H2 - 2021 年 4 月更新

- ビルド 19041.1144

更新プログラムの機能強化と修正:

- 業務アプリケーションのインストール状態レポートに関する問題を修正します。

## <a name="windows-holographic-version-1903---april-2021-update"></a>WindowsHolographic バージョン 1903 - 2021 年 4 月の更新プログラム

- ビルド 18362.1108

更新プログラムの機能強化と修正:

- ローカル アカウントのパスワードを変更設定アプリがクラッシュする問題を修正します。


## <a name="windows-holographic-version-20h2---march-2021-update"></a>WindowsHolographic バージョン 20H2 - 2021 年 3 月更新

- ビルド 19041.1140

更新プログラムの機能強化と修正:

- AdvancedPhotoCapture または LowLagPhotoCapture を使用して HoloLens 2 で写真をキャプチャしているお客様は、写真がキャプチャされた後、最大 3 秒後にカメラの姿勢を取得できます。
- デバイス ポータル Service のメモリ リークを修正しました。この問題により、他のアプリケーションがメモリの割り当てに失敗する原因となるサービスによるメモリ使用量が増加しました。
- 段階的なロールアウトに登録されているユーザーがデバイスにサインインできない問題を修正しました。

## <a name="windows-holographic-version-1903---march-2021-update"></a>WindowsHolographic バージョン 1903 - 2021 年 3 月の更新プログラム

- ビルド 18362.1102

更新プログラムの機能強化と修正:

- デバイス ポータル Service のメモリ リークを修正しました。この問題により、他のアプリケーションがメモリの割り当てに失敗する原因となるサービスによるメモリ使用量が増加しました。

## <a name="windows-holographic-version-20h2---february-2021-update"></a>WindowsHolographic バージョン 20H2 - 2021 年 2 月の更新プログラム

- ビルド 19041.1136

更新プログラムの機能強化と修正:

- デバイスの初期セットアップとストア アプリの更新に関する問題を修正します。
- 以降のリリースのアップグレードとフライトに関する問題HoloLensします。
- eSIM ルート ストアから未使用のプレインストール済み証明書をデバイスからHoloLensしました。

## <a name="windows-holographic-version-1903---february-2021-update"></a>WindowsHolographic バージョン 1903 - 2021 年 2 月更新

- ビルド 18362.1098

この毎月の品質更新プログラムには、重要な変更が含まれているのではなく、Windows Holographic バージョン 2004 の最新ビルドをお試しください。

## <a name="windows-holographic-version-20h2---january-2021-update"></a>WindowsHolographic バージョン 20H2 - 2021 年 1 月更新

- ビルド 19041.1134

更新プログラムの機能強化と修正:

- デバイス上に多数のユーザーがいて、起動時、再開中、ユーザー切り替え中のパフォーマンスが向上しました。
- 研究モード の arm32 サポートを [追加しました](/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)。

## <a name="windows-holographic-version-1903---january-2021-update"></a>WindowsHolographic バージョン 1903 - 2021 年 1 月更新

- ビルド 18362.1091

この毎月の品質更新プログラムには、重要な変更が含まれているのではなく、Windows Holographic バージョン 2004 の最新ビルドをお試しください。

## <a name="windows-holographic-version-20h2--december-2020-update"></a>WindowsHolographic バージョン 20H2 – 2020 年 12 月の更新プログラム

- ビルド 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>アプリ インストーラー 経由でアプリを HoloLens 2 にインストールアプリ インストーラー

新しい **機能 (アプリ インストーラー)** を追加して、アプリケーションをデバイスにシームレスにインストールHoloLens 2しています。 この機能は、アン **マネージド デバイスでは既定でオンになります**。 企業の中断を防ぐために、現時点では、マネージド デバイスでアプリ インストーラー **を** 使用できません。  

次の条件に当てはまる場合、デバイスは "マネージド" と見なされます。

- MDM [登録済み](hololens-enroll-mdm.md)
- プロビジョニング パッケージ [を使用して構成する](hololens-provisioning.md)
- ユーザー [ID が](hololens-identity.md)Azure AD

開発者モードを有効にしたり、開発者モードを使用したりせずにアプリをインストールデバイス ポータル。  (USB 経由または Edge 経由で) Appx バンドルをデバイスにダウンロードし、エクスプローラー の Appx バンドルに移動するだけで、インストールを開始するように求めるメッセージが表示されます。  または、Web [ページ からインストールを開始します](/windows/msix/app-installer/installing-windows10-apps-web)。  MDM の LOB アプリ展開機能を使用して Microsoft Store またはサイドロードからインストールするアプリと同様に、アプリは署名ツールでデジタル[](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)署名する必要があります[](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)。また、アプリを展開する前に、署名に使用される証明書が HoloLens デバイスによって信頼されている必要があります。

**アプリケーションのインストール手順。**

1. デバイスが管理対象と見なされていないことを確認する
1. デバイスの電源HoloLens 2 PC に接続されていることを確認します
1. デバイスにサインインHoloLens 2する
1. PC でカスタム アプリに移動し、yourapp.appxbundle を yourdevicename\Internal Storage\Downloads にコピーします。   ファイルのコピーが完了したら、デバイスを切断できます
1. デバイスからHoloLens 2スタート メニューを開き、[すべてのアプリ] を選択し、アプリを起動エクスプローラーします。
1. [ダウンロード] フォルダーに移動します。 アプリの左側のパネルで、[このデバイス] を最初に選択し、[ダウンロード] に移動する必要があります。
1. yourapp.appxbundle ファイルを選択します。
1. このアプリ インストーラーが起動します。 [インストール] ボタンを選択して、アプリをインストールします。
インストールが完了すると、インストールされたアプリが自動的に起動します。

サンプル アプリは、このフローを[テストWindowsユニバーサル GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)で確認できます。

を使用してアプリをインストール[するプロセスの詳細については、HoloLens 2を参照アプリ インストーラー。](app-deploy-app-installer.md)  

![を使用した MRTK のインストールアプリ インストーラー。](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>更新プログラムの機能強化と修正:

- 手の追跡では、以前に手が失われた可能性がある多くの新しいケースで追跡が維持されます。  これらの新しいケースの一部では、手のひらの位置だけがユーザーの実際の手に基づいて更新され続け、もう一方の関節は前の姿勢に基づいて推論されます。  この変更は、スラップ、スロー、傾斜、アプリの適用などの動きの追跡の一貫性を向上させるのに役立ちます。  また、手が表面に近い場合やオブジェクトを保持している場合にも役立ちます。  手の関節が推論されている場合 [、関節ごとの](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) 精度の値は 、"高" ではなく "近似" に設定されます。
- アカウントの PIN のリセットでAzure ADが表示される問題を修正しました。
- ET、Iris を設定アプリ、新しいユーザー、または通知トーストから起動すると、起動後の OOBE クラッシュがはるかに少なく表示される必要があります。
- ユーザーは、OOBE から正しいタイム ゾーンが出てくる必要があります。

## <a name="windows-holographic-version-1903--december-2020-update"></a>WindowsHolographic バージョン 1903 – 2020 年 12 月の更新プログラム

- ビルド 18362.1088

この毎月の品質更新プログラムには重要な変更は含められないので、最新の Windows Holographic バージョン 20H2 – 2020 年 12 月の更新プログラムと、ビルドに追加された新しい アプリ インストーラー 機能を試してみることができます。

## <a name="windows-holographic-version-20h2"></a>WindowsHolographic バージョン 20H2

- ビルド 19041.1128

WindowsHolographic バージョン 20H2 が利用可能にされ、ユーザーや IT プロフェッショナルにHoloLens 2機能のセットが提供されます。 自動目のポジショニングから、設定 の証明書マネージャー、キオスク モード機能の向上、および新しい Autopilot セットアップ機能まで。 この新しい更新により、IT チームは、HoloLens デバイスの構成と管理をきめ細かく制御し、ユーザーにさらにシームレスなホログラフィック エクスペリエンスを提供できます。

この最新リリースは、バージョン 2004 の月次更新プログラムですが、今回は新機能が含まれる予定です。 メジャー ビルド番号は変わりません。Windows Update は、バージョン 2004 (ビルド 19041) への月次リリースを示します。 [バージョン情報] 画面の [ビルド番号] を設定 >して、利用可能な最新のビルド 19041.1128 以上を確認できます。 最新リリースに更新するには、アプリを開き設定[更新プログラムの更新] & [更新プログラムの確認] をタップします。 更新プログラムを管理する方法の詳細については、「更新プログラムHoloLens管理する[」をHoloLensしてください](hololens-updates.md)。

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Holographic バージョン 20H2 Windowsの新機能  

| 機能                                              | 説明                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [視線の自動調整サポート](hololens-release-notes.md#auto-eye-position-support) | ユーザーが目の追跡の調整を行わずに、目の位置を積極的に計算します。   |
| [Certificate Manager](hololens-release-notes.md#certificate-manager)   | 新しい簡単な方法で、新しいアプリから証明書をインストール設定できます。     |
| [USB からの自動起動プロビジョニング](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | USB ドライブにパッケージをプロビジョニングすると、OOBE のプロビジョニング ページが自動的に表示されます。                                                         |
| [OOBE でのプロビジョニング パッケージの自動確認](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | プロビジョニング パッケージは、プロビジョニング ページから OOBE 中に自動的に適用されます。                                                         |
| [UI を使用しない自動プロビジョニング](hololens-release-notes.md#automatic-provisioning-without-using-ui) | プロビジョニングの自動起動と自動確認を組み合わせる方法。 |
| [Autopilot と接続のWi-Fiする](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | イーサネット アダプターを必要とせずにWi-Fiデバイスからオートパイロットを使用します。 |
| [Tenantlockdown CSP と Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | テナントの登録とポリシーが適用された後は、デバイスがリセットまたは再フラッシュされた場合にのみ、そのテナントにデバイスを登録できます。 |
| [グローバル割り当てアクセス](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | システム レベルでキオスクを適用し、すべてのユーザーに適用できる、複数のアプリ キオスク モードの新しい構成方法。                  |
| [マルチアプリ キオスクでアプリを自動起動する](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | 複数アプリキオスク モードにサインインするときに自動的に起動するアプリケーションを設定します。                                                        |
| [エラー処理のためのキオスク モードの動作の変更](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | キオスク モードの失敗に制限付きフォールバックが追加された。                                                                                                |
| [HoloLensポリシー](hololens-release-notes.md#hololens-policies)                                    | 新しいポリシー HoloLens。     |
| [オフライン キオスクAzure ADグループ メンバーシップをキャッシュする](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | 新しいポリシーを使用すると、ユーザーはグループ メンバーシップ キャッシュを使用して、設定された日数のキオスク モードをオフラインで使用できます。                                        |
| [デバイスの新しい制限ポリシー HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | デバイス管理ポリシーが新しく有効になっていると、HoloLens 2。                                                                                |
| [新しい電源ポリシーのHoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | 電源タイムアウト設定で新しくサポートされたポリシー。  |
| [ポリシーの更新](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | 更新プログラムの制御を許可する新しく有効にされたポリシー。           |
| [ページ設定表示を有効HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | アプリに表示されるページを選択設定ポリシー。             |
| [調査モード](hololens-release-notes.md#research-mode) | 調査モードを使用HoloLens 2。 |
| [記録長の増加](hololens-release-notes.md#recording-length-increased) | MRC の記録は 5 分に制限されなくなりました。 |
| [更新プログラムの機能強化と修正](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | 更新プログラムの追加の修正。   |

### <a name="auto-eye-position-support"></a>視線の自動調整サポート

このHoloLens 2、目の位置により、正確なホログラムの配置、快適な表示エクスペリエンス、および表示品質の向上が可能になります。 視線は、視線追跡計算の一部として内部的に計算されます。 ただし、これには、エクスペリエンスで視線の入力が必要ない場合でも、各ユーザーが視線追跡の調整を実行する必要があります。

**視線の自動調整 (AEP)** は、ユーザーの目の位置を計算するための操作のない方法でこれらのシナリオを可能にします。 自動目の位置は、ユーザーがデバイスを置いた瞬間から自動的にバックグラウンドで作業を開始します。 ユーザーが前の目追跡の調整を行っていない場合、自動目の位置は、20 - 30 秒の処理時間の後に、表示システムにユーザーの目の位置を提供し始める。 ユーザー データはデバイスに保持されません。そのため、ユーザーが離れてデバイスを再度起動した場合、またはデバイスが再起動またはスリープからウェイクアップした場合は、このプロセスが繰り返されます。

調整されていないユーザーがデバイスを装着した場合、視線の自動調整機能によるシステム動作の変更がいくつかあります。 このコンテキストでは、未調整のユーザーは、以前にデバイスで目の追跡の調整プロセスを実行していないユーザーを指します。

| アクティブなアプリケーション | 以前の動作 | Windows Holographic、バージョン 20H2 アップデートからの動作 |
|:-------------------|:-----------------|:-----------------------------------|
| 非視線対応アプリまたはホログラフィック シェル |視線追跡の調整プロンプト ダイアログが表示されます。 | プロンプトは表示されません。 |
| 視線対応アプリ | 視線追跡の調整プロンプト ダイアログが表示されます。 | 視線追跡の調整プロンプトは、アプリケーションが視線ストリームにアクセスした場合にのみ表示されます。 |

ユーザーが非視線対応アプリケーションから視線データにアクセスするアプリケーションに移行すると、調整プロンプトが表示されます。

他のすべてのシステム動作は、現在のユーザーがアクティブな目追跡調整を行っていない場合と似ています。 たとえば、One-handed Start ジェスチャは有効になりません。 初期設定の既定のエクスペリエンスに変更はありません。

目の視線入力データまたは非常に正確なホログラムの配置を必要とするエクスペリエンスの場合は、未調整のユーザーに視線追跡の調整を実行することをお勧めします。 これは、目の追跡の調整プロンプトから、またはスタート メニューから 設定 アプリを起動し **、[System > Calibration > Eye Calibration > Run eye calibration ]** を選択することでアクセスできます。

この情報は、後で他の調整 [情報 と一緒に確認できます](hololens-calibration.md#auto-eye-position-support)。

### <a name="certificate-manager"></a>証明書マネージャー

- 新しい証明書マネージャーを使用して、デバイスのセキュリティとコンプライアンスのための監査、診断、検証ツールが改善されました。 この機能を使用すると、商用環境で大規模に証明書を展開、トラブルシューティング、検証できます。

Holographic Windows 20H2 では、アプリに証明書マネージャー HoloLens 2 設定しています。 [Update **設定 > Security & Certificates]>移動します**。 この機能を使用すると、デバイス上の証明書を表示、インストール、削除する簡単で使い分け的な方法が提供されます。 新しい証明書マネージャーにより、管理者とユーザーは、デバイスのセキュリティと準拠を維持するために、監査、診断、検証ツールが改善されました。

- **監査:** 証明書が正しく展開されていることを検証する機能、または証明書が適切に削除されていることを確認する機能。
- **診断:** 問題が発生した場合は、デバイスに適切な証明書が存在する場合は、時間を節約し、トラブルシューティングに役立ちます。
- **検証:** 証明書が目的の目的に対応し、機能することを確認すると、特に商用環境で大規模に証明書を展開する前に、かなりの時間を節約できます。

一覧内の特定の証明書をすばやく検索するには、名前、ストア、または有効期限で並べ替えるオプションがあります。 ユーザーは証明書を直接検索することもできます。 個々の証明書のプロパティを表示するには、証明書を選択し、[情報] を **クリックします**。

証明書のインストールでは現在、.cer ファイルと .crt ファイルがサポートされています。 デバイス所有者は、ローカル コンピューターと現在のユーザーに証明書をインストールできます。 他のすべてのユーザーは、現在のユーザーにのみインストールできます。 ユーザーは、UI から直接インストールされた証明書設定できます。 証明書が他の方法でインストールされている場合は、同じメカニズムでも削除する必要があります。

#### <a name="steps-to-install-a-certificate"></a>証明書をインストールする手順

1. Connect PC HoloLens 2に接続します。
1. インストールする証明書ファイルを、自分の証明書ファイルの場所にHoloLens 2。
1. [App 設定 **Update > & Security > 証明書**] に移動し、[証明書のインストール] を選択します。
1. [ **ファイルのインポート]** をクリックし、証明書を保存した場所に移動します。
1. [ストア **の場所] を選択します**。
1. [証明書 **ストア] を選択します**。
1. **[インストール]** をクリックします。

これで、証明書がデバイスにインストールされます。

#### <a name="steps-to-remove-a-certificate"></a>証明書を削除する手順

1. [App 設定 **Update > Security > Certificates] に移動します**。
1. 検索ボックスで名前で証明書を検索します。
1. 証明書を選択します。
1. [削除] **をクリックします。**
1. 確認を求められたら、 **[はい]** を選択します。

![アプリの証明書ビューアー設定します。](images/certificate-viewer-device.jpg)

![証明書 UI を使用して証明書をインストールする方法を示す図。](images/certificate-device-install.jpg)

この情報は、後で新 [しい [証明書マネージャー] ページで確認できます](certificate-manager.md)。

### <a name="auto-launch-provisioning-from-usb"></a>USB からの自動起動プロビジョニング

- OOBE 中にプロビジョニング パッケージを備えた USB ドライブが使用されている場合、ユーザーの操作を減らして自動化されたプロセス。

このリリースより前は、ユーザーは、ボタンの組み合わせを使用してプロビジョニングするために、OOBE 中にプロビジョニング画面を手動で起動する必要があります。 これで、ユーザーは USB ストレージ ドライブ上のプロビジョニング パッケージを使用して、ボタンの組み合わせをスキップできます。

1. OOBE の最初の対話可能な瞬間にプロビジョニング パッケージを使用して USB ドライブを接続する
1. デバイスをプロビジョニングする準備ができたら、プロビジョニング ページが表示されたプロンプトが自動的に開きます。

注: デバイスの起動中に USB ドライブが接続された状態の場合、OOBE は既存の USB ストレージ デバイスを列挙し、追加の USB ストレージ デバイスが接続されているのを監視します。

OOBE 中にプロビジョニング パッケージを適用する方法の詳細については、プロビジョニングに関するドキュメント[HoloLens参照](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)してください。

USB からの[自動起動プロビジョニングに関](hololens-provisioning.md#auto-launch-provisioning-from-usb)する追加情報については、プロビジョニングに関するドキュメントHoloLens参照してください。

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>OOBE でのプロビジョニング パッケージの自動確認

- [プロビジョニング パッケージ] ページが表示されている場合、ユーザーの操作を減らして自動プロセスを実行すると、一覧に表示されているすべてのパッケージが自動的に適用されます。

プロビジョニングのメイン画面が表示された場合、OOBE は、すべてのプロビジョニング パッケージの適用を自動的に開始する前に、10 秒をカウントダウンします。 ユーザーは、 [期待したパッケージを](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) 確認した後も、この 10 時間以内に確認または取り消しを行います。

### <a name="automatic-provisioning-without-using-ui"></a>UI を使用しない自動プロビジョニング

- プロビジョニングのためのデバイスの操作を減らした自動プロセスを組み合わせたもの。

ユーザーは、USB デバイスからのプロビジョニングの自動起動とプロビジョニング パッケージの自動確認を組み合わせることで、デバイスの UI を使用したり、デバイスを装着したりすることなく、HoloLens 2 デバイスを自動的にプロビジョニングできます。 複数のデバイスに対して同じ USB ドライブとプロビジョニング パッケージを引き続き使用できます。 これは、同じ領域に複数のデバイスを一度に展開する場合に便利です。

1. [構成デザイナー を使用してプロビジョニング](hololens-provisioning.md)[パッケージWindows作成します](https://www.microsoft.com/store/productId/9NBLGGH4TX22)。
1. パッケージを USB ストレージ ドライブにコピーします。
1. [19041.1361](https://aka.ms/hololens2previewdownload)[以降HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions)ビルド にフラッシュします。
1. Advanced [Recovery Companion で](https://www.microsoft.com/store/productId/9P74Z35SFRS8) デバイスのフラッシュが完了したら、USB-C ケーブルを取り外します。
1. USB ドライブをデバイスに接続します。
1. デバイスが HoloLens 2 OOBE に起動すると、USB ドライブ上のプロビジョニング パッケージが自動的に検出され、プロビジョニング ページが起動します。
1. 10 秒後、デバイスによってプロビジョニング パッケージが自動的に適用されます。

これでデバイスが構成され、[プロビジョニングに成功しました [] 画面が表示されます](hololens-provisioning.md#automatic-provisioning-without-using-ui)。

### <a name="using-autopilot-with-wi-fi-connection"></a>Autopilot と接続のWi-Fiする

- 接続されているデバイスで Autopilot が機能する機能を有効にすることで、ハードウェアのニーズを減らすイーサネットへの USB-C アダプターWi-Fi必要が取り除かれました。

OOBE 中に、Wi-Fi HoloLens 2接続すると、OOBE によってデバイスの Autopilot プロファイルが確認されます。 見つかった場合は、参加フローと登録フローの残りのAADに使用されます。 つまり、USB-C または Wi-Fi から USB-C アダプターへのイーサネットの使用は要件ではなくなりましたが、OOBE の開始時に提供されている場合は引き続き機能します。 デバイスの[Autopilot の詳細については、HoloLens 2してください](hololens2-autopilot.md)。

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP と Autopilot

- デバイスのリセットまたは再フラッシュを使用しても、デバイスをテナントにロックすることで、組織のテナント上のデバイスを保持します。 プロビジョニングを介した でのアカウントの作成を禁止することで、セキュリティを強化します。

HoloLens 2デバイスでは[、Holographic バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2)のWindows TenantLockdown CSP がサポートされます。

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP は、HoloLens 2 が Autopilot のみを使用して MDM 登録に関連付けられるようにします。 TenantLockdown CSP の RequireNetworkInOOBE ノードが HoloLens 2 で true または false (最初に設定された) 値に設定されると、その値は、再フラッシュ、OS 更新プログラムなどにもかかわらずデバイスに残ります。

HoloLens 2 で TenantLockdown CSP の RequireNetworkInOOBE ノードが true に設定されると、OOBE は、ネットワーク接続後、Autopilot プロファイルが正常にダウンロードおよび適用されるまで無期限に待機します。

HoloLens 2 で TenantLockdown CSP の RequireNetworkInOOBE ノードが true に設定されると、OOBE では次の操作が許可されなくなります。

- ランタイム プロビジョニングを使用したローカル ユーザーの作成
- ランタイム プロビジョニングによる Azure AD への参加操作の実行
- OOBE エクスペリエンスでデバイスの所有者を選択する

#### <a name="how-to-set-this-using-intune"></a>Intune を使用してこれを設定する方法

1. 以下に示すように、カスタム OMA URI デバイス構成プロファイルを作成し、RequireNetworkInOOBE ノードに true を指定します。
OMA-URI 値は ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE である必要があります

   > [!div class="mx-imgBorder"]
   > ![OMA-URI によるテナントのロックダウンの設定。](images/hololens-tenant-lockdown.png)

1. グループを作成し、デバイス構成プロファイルをそのデバイス グループに割り当てます。

1. 前の手順で作成したグループの HoloLens 2 デバイス メンバーを作成し、同期をトリガーします。  

Intune ポータルで、デバイス構成が正常に適用されていることを確認します。 このデバイスの構成が HoloLens 2 デバイスに正常に適用されると、TenantLockdown の効果がアクティブになります。

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Intune を使用して HoloLens 2 で TenantLockdown の RequireNetworkInOOBE の設定を解除する方法

1. 上で作成したデバイス構成が以前に割り当てられていたデバイス グループから HoloLens 2 を削除します。

1. 以下に示すように、カスタム OMA URI ベースのデバイス構成プロファイルを作成し、RequireNetworkInOOBE に false を指定します。
OMA-URI 値は ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE である必要があります

   > [!div class="mx-imgBorder"]
   > ![Intune の OMA URI を介して RequireNetworkInOOBE を false に設定するスクリーンショット。](images/hololens-tenant-lockdown-false.png)

1. グループを作成し、デバイス構成プロファイルをそのデバイス グループに割り当てます。

1. 前の手順で作成したグループの HoloLens 2 デバイス メンバーを作成し、同期をトリガーします。

Intune ポータルで、デバイス構成が正常に適用されていることを確認します。 このデバイスの構成が HoloLens 2 デバイスに正常に適用されると、TenantLockdown の効果が非アクティブになります。

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>TenantLockdown が true に設定された後、HoloLens で Autopilot プロファイルが割り当て解除された場合、OOBE 中にどうなりますか?

OOBE は、Autopilot プロファイルがダウンロードされるのを無期限に待機し、次のダイアログが表示されます。 TenantLockdown の影響を取り除くには、最初に Autopilot のみを使用してデバイスを元のテナントに登録し、TenantLockdown CSP によって導入された制限を取り除く前に、前の手順で説明したように RequireNetworkInOOBE の設定を解除する必要があります。

![ポリシーがデバイスに適用される時のデバイス内ビュー。](images/hololens-autopilot-lockdown.png)

この情報は [、Tenantlockdown CSP と Autopilot](hololens2-autopilot.md#tenant-lockdown-csp-and-autopilot)の下にある Autopilot の残りの部分と共に確認できます。

### <a name="global-assigned-access--kiosk-mode"></a>グローバル割り当てアクセス – キオスク モード

- システム レベルでキオスク モードを適用する新しいキオスク 方法を有効にすることで、キオスクの ID 管理を減らしました。

この新機能を使用すると、IT 管理者は、システム レベルで適用できる複数のアプリ キオスク モード用に HoloLens 2 デバイスを構成できます。システム上の ID とのアフィニティは持たず、デバイスにサインインするすべてのユーザーに適用されます。 この新機能の詳細については、キオスク モード[の](hololens-kiosk.md)HoloLensしてください。

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>複数アプリキオスク モードでのアプリケーションの自動起動

- アプリの自動起動に重点を置いてエクスペリエンスを向上し、キオスク モード エクスペリエンス用に選択された UI とアプリの選択をさらに増やします。

複数アプリキオスク モードにのみ適用され、割り当て済みアクセス構成で以下の強調表示された属性を使用して、1 つのアプリのみを自動起動に指定できます。

ユーザーがサインインすると、アプリケーションが自動的に起動されます。

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>エラー処理のためのキオスク モードの動作の変更

- キオスク モードのエラーで使用可能なアプリを排除することで、より安全なキオスク モード。

以前は、キオスク モードの適用でエラーが発生した場合、HoloLensすべてのアプリケーションを [スタート] メニューに表示するために使用されました。 これで、Windows Holographic バージョン 20H2 でエラーが発生した場合、次のようにスタート メニューにアプリが表示されません。

![失敗したときのキオスク モードの画像。](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLensポリシー

- デバイス管理オプションは、デバイスHoloLens専用に作成されます。

Holographic バージョン 20H2 の HoloLens 2デバイス用Windows Mixed Reality ポリシーが新しく作成されました。 新しい制御可能な設定には、明るさの設定、ボリュームの設定、Mixed Reality キャプチャでのオーディオ記録の無効化、診断を収集できる時間の設定、グループ メンバーシップ キャッシュAAD設定が含まれます。  

| 新HoloLensポリシー                                | 説明                                                                               | Notes                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 明るさボタンを無効にし、ボタンを押しても明るさが変わらないよう許可します。       | 1 はい、0 はい (既定値)                                                |
| MixedReality\VolumeButtonDisabled                  | ボリューム ボタンを無効にし、ボタンを押してもボリュームが変更されません。               | 1 はい、0 はい (既定値)                                                |
| MixedReality\MicrophoneDisabled                    | マイクを無効にして、オーディオ録音を行HoloLens 2。                      | 1 はい、0 はい (既定値)                                                |
| MixedReality\FallbackDiagnostics                   | 診断ログを収集できる場合の動作を制御します。                               | 0 無効、1 デバイス所有者に対して有効、2 すべて有効 (既定) |
| MixedReality\HeadTrackingMode                      | 将来利用するために予約されています。                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | キオスクがグループを対象Azure ADに使用されるグループ メンバーシップ キャッシュの日数Azure AD制御します。 | 以下を参照してください。                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>オフライン キオスクAzure ADグループ メンバーシップをキャッシュする

- 最大 60 日間、オフライン キオスクAADグループで使用できます。

このポリシーでは、サインインしたユーザーの Azure AD グループを対象とする割り当てアクセス構成に対して、Azure AD グループ メンバーシップ キャッシュを使用できる日数を制御します。 このポリシー値が 0 より大きい値にのみ設定されている場合は、キャッシュが使用されます。それ以外の場合は使用されません。  

名前: AADGroupMembershipCacheValidityInDays URI 値: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最小 - 0 日  
最大 - 60 日

このポリシーを正しく使用する手順:

1. デバイス グループを対象とするキオスク用のデバイス構成プロファイルAzure ADし、そのデバイスをデバイスHoloLens割り当てる。
1. カスタム oma-uri ベースのデバイス構成を作成します。この構成では、このポリシー値が必要な日数 (> 0) に設定され、HoloLens デバイスに割り当てられます。
    1. URI 値は、/Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays のように OMA-URI テキストボックスに入力する必要があります。
    1. 許容される最小値と最大値の間の値を指定できます。
1. HoloLens デバイスを登録し、両方の構成がデバイスに適用されていることを確認します。
1. インターネットが利用可能なときにユーザー1のサインインを Azure AD し、ユーザーのサインインと Azure AD グループのメンバーシップが正常に確認されると、キャッシュが作成されます。
1. これで Azure AD ユーザー1がオフライン HoloLens して、ポリシー値で X 日の日数が許可されている限り、キオスクモードで使用できるようになりました。
1. 手順 4. と 5. は、他の Azure AD ユーザー N に対して繰り返すことができます。ここで重要なのは、Azure AD ユーザーは、少なくとも1回、キオスク構成の対象となる Azure AD グループのメンバーであることを確認できるように、インターネットを使用してデバイスにサインインする必要があるという点です。

> [!NOTE]
> 手順 4. を実行すると Azure AD ユーザーに対して、"切断" 環境に記載されているエラー動作が発生します。

### <a name="new-device-restriction-policies-for-hololens-2"></a>HoloLens 2 の新しいデバイス制限ポリシー

- プロビジョニングパッケージの追加や削除をブロックするなど、特定のデバイス管理ポリシーをユーザーが管理できるようにします。

新しく有効になったポリシーにより、HoloLens 2 デバイスの管理オプションを追加できるようになりました。

- [AllowAddProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage)
- [ConfigureTimeZone](/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](/windows/client-management/mdm/remotelock-csp)

この2つの新しいポリシー Allowaddのパッケージと Allowremoveのパッケージは、 [一般的なデバイスの制限](hololens-common-device-restrictions.md)に追加されています。

> [!NOTE]
> [remotelock](/windows/client-management/mdm/remotelock-csp)に関しては、HoloLens は/Vendor/MSFT/RemoteLock/Lock 構成のみをサポートします。 リセットや回復などの PIN を処理する構成はサポートされていません。

### <a name="new-power-policies-for-hololens-2"></a>HoloLens 2 の新しい電源ポリシー

- 電源ポリシーを使用してスリープまたはロックを HoloLens する場合のその他のオプション。

これらの新しく追加されたポリシーにより、管理者はアイドルタイムアウトなどの電源状態を制御できるようになります。 個々のポリシーの詳細を確認するには、そのポリシーのリンクをクリックしてください。

|     ポリシードキュメントのリンク                |     Notes                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Windows 構成デザイナーで使用する値の例を次に示します。`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Windows 構成デザイナーで使用する値の例を次に示します。`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Windows 構成デザイナーで使用する値の例 (100)                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Windows 構成デザイナーで使用する値の例 (100)                                                                          |
|     [スタンドアロン](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows 構成デザイナーで使用する値の例を次に示します。`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows 構成デザイナーで使用する値の例を次に示します。`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

DisplayOffTimeoutOnBattery と DisplayOffTimeoutPluggedIn のこれら2つの新しいポリシーは、 [一般的なデバイスの制限](hololens-common-device-restrictions.md)に追加されています。

> [!NOTE]
> HoloLens 2 の一貫したエクスペリエンスを得るには、displayofftimeoutonbattery とスタンドアロンの両方の値が同じ値として設定されていることを確認してください。 DisplayOffTimeoutPluggedIn と StandbyTimeoutPluggedIn にも同じことが当てはまります。 最新のスタンバイの詳細については [、「表示、スリープ、休止状態のタイマー」](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) を参照してください。

### <a name="newly-enabled-update-policies-for-hololens"></a>HoloLens 用に新しく有効になった更新ポリシー

- 更新プログラムをインストールするとき、または [更新の一時停止] ボタンを無効にして更新を確認する方法の詳細。

これらの更新ポリシーは HoloLens 2 デバイスで有効になりました。

- [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
- [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
- [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
- [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

これらの更新ポリシーの詳細と HoloLens デバイスでの使用方法については、「 [HoloLens 更新プログラムの管理](hololens-updates.md)」を参照してください。

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>HoloLens 2 の設定ページ表示を有効にする

- 設定アプリの UI コントロールが向上しました。これは、限られたページの選択を示すために混同される可能性があります。

これで、IT 管理者がシステム設定アプリ内の特定のページを表示またはアクセスできないようにするか、指定されたページ以外のすべてのページに対して実行できるようにするポリシーが有効になりました。 この機能を完全にカスタマイズする方法については、下のリンクをクリックしてください。

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

HoloLens 2 でカスタマイズできるページ設定については、[設定の uri](settings-uri-list.md)に関するページを参照してください。

![設定アプリで変更されたアクティブ時間のスクリーンショット。](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>リサーチモード

研究モードでは、HoloLens 2 はコンピュータービジョン調査の potent ツールになります。 以前のエディションと比較して、HoloLens 2 のリサーチモードには次の利点があります。

- HoloLens (第1世代) リサーチモードで公開されるセンサーに加えて、加速度計、ジャイロスコープ、磁力計などの imu センサーアクセスを提供するようになりました。
- HoloLens 2 には、リサーチモードと共に使用できる新しい機能が用意されています。 具体的には、より充実した一連の実験を提供できる、明確な追跡 Api と視点追跡 Api へのアクセスを提供します。

研究者は、HoloLens デバイスでリサーチモードを有効にして、これらの外部に面しているすべての未加工のイメージセンサーストリームにアクセスできるようになりました。 HoloLens 2 のリサーチモードでは、加速度計、ジャイロスコープ、および磁力計の読み取りにもアクセスできます。 ユーザーのプライバシーを保護するために、未加工の視点を追跡するカメライメージは、リサーチモードでは使用できませんが、既存の Api を通じて目を見つめます。

詳細については、 [調査モードのドキュメント](/windows/mixed-reality/research-mode) をご覧ください。

### <a name="recording-length-increased"></a>記録の長さが増加しました

お客様からのフィードバックにより、 [混合現実のキャプチャ](holographic-photos-and-videos.md)の記録長さが増加しています。 混合の現実のキャプチャは、既定では5分に制限されなくなりましたが、代わりに使用可能なディスク領域に基づいて最大記録長が計算されます。 デバイスは、ディスクの空き領域の最大80% まで、使用可能なディスク領域に基づいて、最大ビデオ記録期間を見積もります。

> [!NOTE]
> 次のいずれかが発生した場合、HoloLens は既定のビデオ記録の長さ (5 分) を使用します。
>
> - 推定最大記録期間は、既定の5分よりも小さくなっています。
> - 使用可能なディスク領域が、合計ディスク領域の20% 未満です。

完全な要件については、 [holographic の写真とビデオ](holographic-photos-and-videos.md#maximum-recording-length) のドキュメントを参照してください。

### <a name="improvements-and-fixes-in-the-windows-holographic-version-20h2-update"></a>Windows Holographic、バージョン20h2 更新プログラムの機能強化と修正:

- OOBE の他の画面がダークモードになりました。
- 詳細については、オンラインで最新のプライバシーに関する声明を参照してください。
- ユーザーがプロビジョニングパッケージを使用して VPN プロファイルをプロビジョニングできない問題に対処しました。
- VPN 接続のプロキシ構成の問題を修正しています。
- NCM for AllowUsbConnection の MDM による USB 機能の列挙を無効にするポリシーが更新されました。
- デバイスが[シングルアプリキオスク](hololens-kiosk.md)として設定されている場合に、HoloLens デバイスが Media Transfer Protocol (MTP) 経由でファイルエクスプローラーに表示されない問題に対処します。 MTP (および一般的な USB 接続) は、 [Allowusbconnection](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) ポリシーを使用して無効にすることもできます。
- スタートメニューのアイコンがキオスクモードで正しく拡大縮小された問題を修正しました。
- Azure AD グループを対象としたキオスクモードでの HTTP キャッシュの妨害が原因で発生する問題を修正します。
- 開発者モードを無効にしてから再度有効にしない限り、ユーザーがプロビジョニングパッケージで開発者モードを有効にした後に [ペアリング] ボタンを使用できない問題を修正しました。

## <a name="windows-holographic-version-1903---november-2020-update"></a>WindowsHolographic、バージョン 1903-2020 の11月の更新プログラム

- ビルド18362.1085

この月間品質更新プログラムには、重要な変更は含まれていません。最新の機能リリースビルド Windows Holographic、バージョン20h2 を試すことをお勧めします。

## <a name="windows-holographic-version-2004---october-2020-update"></a>WindowsHolographic、バージョン 2004-2020 更新プログラム

- ビルド19041.1124

更新プログラムの機能強化と修正:

- ランタイムシステム障害の原因となった不要なチェックを削除しました。

## <a name="windows-holographic-version-1903---october-2020-update"></a>WindowsHolographic、バージョン 1903-2020 更新プログラム

- ビルド18362.1081

この月間品質更新プログラムには、重要な変更は含まれていません。 Windows Holographic バージョン2004の最新のビルドを試すことをお勧めします。

## <a name="windows-holographic-version-2004---september-2020-update"></a>WindowsHolographic、バージョン 2004-9 月2020更新プログラム

- ビルド19041.1117

更新プログラムの機能強化と修正:

- package.appxmanifest に supports複数インスタンス = "true" が存在する場合に、アプリケーションのデバッグを Visual Studio できない問題に対処します。
- このリリースには、ネットワークプロキシ経由のインターネット検出の失敗に対処するための NCSI プロキシ検出修正が含まれています。 NCSI は、コンピュータープロキシとプロファイルごとのプロキシを使用して、インターネット接続を検出できます。 ユーザーごとのプロキシは、今後のリリースで NCSI でサポートされる予定です。
- ほとんどのデバイスWindows Mixed Reality、ユーザーの頭が前方を見ている中立的な位置にある場合、前方方向ベクトルはグラウンドと平行になります。 ただし、以前のバージョンの HoloLens 2は、ベクターをディスプレイ パネルに平行に配置する必要がありました。これは、理想的な向きに対して数度下向きに傾きます。 新しいバージョンの HoloLens 2フォーム ファクター間のセマンティック整合性を確保するために、これを修正しました。
- 特定のシナリオでの追跡損失を減らすハンド トラッキングの堅牢性が向上しました。
- このリリースには、ビデオ キャプチャの問題の原因である可能性があるオーディオ タイムスタンプの品質を向上させる修正プログラムが含まれています。

## <a name="windows-holographic-version-1903---september-2020-update"></a>WindowsHolographic バージョン 1903 - 2020 年 9 月の更新プログラム

- ビルド 18362.1079

更新プログラムの機能強化と修正:

- ほとんどのデバイスWindows Mixed Reality、ユーザーの頭が前方を見ている中立的な位置にある場合、前方方向ベクトルはグラウンドと平行になります。 ただし、以前のバージョンの HoloLens 2は、ベクターをディスプレイ パネルに平行に配置する必要がありました。これは、理想的な向きに対して数度下向きに傾きます。 新しいバージョンの HoloLens 2フォーム ファクター間のセマンティック整合性を確保するために、これを修正しました。
- 特定のシナリオでの追跡損失を減らすハンド トラッキングの堅牢性が向上しました。

## <a name="windows-holographic-version-2004---august-2020-update"></a>WindowsHolographic バージョン 2004 - 2020 年 8 月更新

- ビルド 19041.1113

更新プログラムの機能強化と修正:

- 設定アプリは、Iris Enrollment または Eye Tracking の調整エクスペリエンスにユーザーをフォローしなくなりました。
- デバイスの名前を変更し、他のアクション (ネットワークへの接続など) を実行するプロビジョニング パッケージを OOBE 中に適用すると、名前の変更のためにデバイスの再起動後に他のアクションを実行できなかったバグを修正しました。
- 初期デバイス設定の変更された配色は、視覚的な品質を向上させるためにフローします。

## <a name="windows-holographic-version-1903---august-2020-update"></a>WindowsHolographic バージョン 1903 - 2020 年 8 月更新

- ビルド 18362.1074

この毎月の品質更新プログラムには、重要な変更が含まれているのではなく、Windows Holographic バージョン 2004 の最新ビルドをお試しください。

## <a name="windows-holographic-version-2004---july-2020-update"></a>WindowsHolographic バージョン 2004 - 2020 年 7 月更新

- ビルド 19041.1109

更新プログラムの機能強化と修正:

- 開発者は、セキュリティで保護された接続を必要とするデバイス ポータルを有効または無効にするか選択できます。
- OS の更新後にアプリケーションが起動する場合の信頼性が向上しました。
- 既定の受信トレイの明るさを 100% に変更しました。
- Windows デバイス ポータル の HTTPS 転送に関する問題に対処HoloLens 2。

## <a name="windows-holographic-version-1903---july-2020-update"></a>WindowsHolographic バージョン 1903 - 2020 年 7 月の更新プログラム

- ビルド 18362.1071

更新プログラムの機能強化と修正:

- 追跡を失った場合や回復するときに Unity アプリケーションでホログラムが消える可能性がある問題を修正しました。
- 特定のデバイスでハードウェア アクセラレーションを使用して HoloLensを使用している間に、アプリの排他HoloLens Emulatorがシェルにクラッシュする原因となる問題を修正しました。
- サーバー上のクライアントの HTTPS 転送に関するWindows デバイス ポータルに対処HoloLens 2。

## <a name="windows-holographic-version-2004---june-2020-update"></a>WindowsHolographic バージョン 2004 - 2020 年 6 月更新

- ビルド 19041.1106

更新プログラムの機能強化と修正:

- カスタム MRC レコーダーが指定されていない場合、特定のプロパティに新しい既定値が追加されました。
  - *MRC ビデオ効果の場合*:
    - PreferredOgramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (イマーシブ ヘッドセット))
  - *MRC オーディオ効果:*
    - LoopbackGain (現在の "App Audio Gain" の値は、Mixed Reality キャプチャ ページWindows デバイス ポータル)
    - MicrophoneGain (現在の [マイク オーディオ ゲイン] の値は、Mixed Reality キャプチャページWindows デバイス ポータル)
- Mixed Reality キャプチャ シナリオでオーディオ品質を向上させるバグを修正しました。 具体的には、この修正により、[スタート] メニューが表示されているときに、記録中のオーディオ **のグリグリコが** 排除されます。
- 記録されたビデオでのホログラムの安定性が向上しました。
- デバイスがスタンバイ状態を数日間残した後、Mixed Reality キャプチャでビデオを記録できない問題を解決しました。
- Unity アプリケーションでは、HolographicSpace.UserPresence API は一般に無効になっています。 この動作により、"バックグラウンドで実行" 設定が有効になっている場合でも、バイザーが反転した場合に一部のアプリが一時停止する問題が回避されます。 この API は、Unity バージョン 2018.4.18 以降および 2019.3.4 以降で有効になっています。
- 接続を使用してデバイス ポータルアクセスWi-Fi、無効な証明書が原因で Web ブラウザーが へのアクセスを妨げる可能性があります。 デバイス証明書が以前に信頼されている場合でも、ブラウザーから "ERR_SSL_PROTOCOL_ERROR" などのエラーが報告される場合があります。 この場合、セキュリティ警告を無視するオプションデバイス ポータル、更新プログラムの作成に進む必要はありません。 この更新プログラムによって問題が解決されました。 デバイス証明書が以前にダウンロードされ、ブラウザーのセキュリティ警告を削除するために PC で信頼されている場合、SSL エラーが発生した場合は、ブラウザーのセキュリティ警告に対処するために新しい証明書をダウンロードして信頼する必要があります。
- MSIX パッケージを使用してアプリをインストールできるランタイム プロビジョニング パッケージを作成する機能を有効にしました。
- 設定 Systemホログラム に設定を追加しました。この設定を使用すると、デバイスのシャットダウン時に、ユーザーは自宅からMixed Realityホログラムを  >    >  自動的に削除できます。
- ピクセル形式を変更し、HoloLensエミュレーターで黒にレンダリングするアプリのHoloLens修正しました。
- Iris ログイン中にクラッシュを引き起こしたバグを修正しました。
- 既に現在のアプリに対するストアのダウンロードの繰り返しに関する問題を修正しました。
- イマーシブ アプリがアプリを繰り返し開かMicrosoft Edge修正しました。
- 1903 リリースから更新した後の初期ブートでの Photos アプリの起動に関する問題を修正しました。
- パフォーマンスと信頼性の向上。

## <a name="windows-holographic-version-1903---june-2020-update"></a>WindowsHolographic バージョン 1903 - 2020 年 6 月更新

- ビルド 18362.1064

更新プログラムの機能強化と修正:

- カスタム MRC レコーダーは、指定されていない場合、特定のプロパティに対して新しい既定値を持っています。
  - *MRC ビデオ効果の場合*:
    - PreferredOgramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (イマーシブ ヘッドセット))
  - *MRC オーディオ効果:*
    - LoopbackGain (現在の "App Audio Gain" の値は、Mixed Reality キャプチャ ページWindows デバイス ポータル)
    - MicrophoneGain (現在の [マイク オーディオ ゲイン] の値は、Mixed Reality キャプチャページWindows デバイス ポータル)
- Unity アプリケーションでは、HolographicSpace.UserPresence API は一般に無効になっています。 この動作により、バックグラウンドで実行する設定が有効になっている場合でも、バイザーが反転した場合に一部のアプリが一時停止する問題が回避されます。 この API は、Unity バージョン 2018.4.18 以降および 2019.3.4 以降で有効になっています。
- ピクセル形式を変更するアプリHoloLensが黒くレンダリングされる問題を修正HoloLens Emulator。
- 1903 リリースから更新した後の初期ブートでの Photos アプリの起動に関する問題を修正しました。

## <a name="windows-holographic-version-2004"></a>WindowsHolographic バージョン 2004

- ビルド - 19041.1103

*HoloLens 2、Windows Holographic、バージョン 2004* の 2020 年 5 月のメジャー ソフトウェア更新プログラムには、Windows Autopilot のサポート、アプリダーク モード、5G/LTE ホットスポットの USB イーサネット サポートなど、多くの重要な新機能が含まれています。 最新リリースに更新するには、新しいアプリを開設定、Update & Security に移動して、[更新プログラムの確認]    **** **ボタンを選択**   します。 

|             機能                              |          説明                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          AutoPilot を使用して、実稼働用の新しいデバイスを事前Windowsセットアップする                 |
|       FIDO 2 のサポート                             |          共有デバイスの高速かつ安全な認証を有効にする FIDO2 セキュリティ キーのサポート            |
|       プロビジョニングの改善                      |          USB ドライブからデバイスにプロビジョニング パッケージをシームレスに適用HoloLens                              |
|       アプリケーションのインストール状態                 |          アプリのアプリが MDM 経由設定にプッシュされている場合は、アプリのインストールHoloLens 2を確認します               |
|       構成サービス プロバイダー (AP)   |          管理者制御機能を強化する新しい構成サービス プロバイダーを追加しました                 |
|       USB 5G/LTE のサポート                       |          USB イーサネット機能の拡張により、5G/LTE のサポートが可能                                    |
|       ダーク アプリ モード                              |          ダーク モードとライト モードの両方をサポートするアプリで使用できるダーク アプリ モード。表示エクスペリエンスが向上します        |
|       音声指示コマンド                             |          ハンドフリー HoloLens 制御する追加のシステム音声コマンドのサポート                           |
|       手動追跡の機能強化                 |          ハンドトラッキングの機能強化によって、ボタンと2D スレートの相互作用がより正確になりました                        |
|       品質の向上と修正                 |          プラットフォーム全体でのさまざまなシステムパフォーマンスと信頼性の向上                            |

### <a name="support-for-windows-autopilot"></a>Windows 自動操縦のサポート

WindowsHoloLens 2 の自動操縦機能により、デバイスの販売チャネルは Intune テナントに HoloLens 事前登録されます。 デバイスが到着すると、テナント内の共有デバイスとして自己展開できるようになります。 自己展開を利用するには、USB-C からイーサネットを使用したセットアップの最初の画面で、デバイスをネットワークに接続する必要があります。

ユーザーが自動操縦用自己展開プロセスを開始すると、プロセスは次の手順を完了します。

1. デバイスを Azure Active Directory (Azure AD) に参加させます。
1. Azure AD を使用して、Microsoft Intune (または別の MDM サービス) にデバイスを登録します。
1. デバイスを対象とするポリシー、証明書、およびネットワークプロファイルをダウンロードします。
1. デバイスをプロビジョニングします。
1. ユーザーにサインイン画面を提示します。

詳細については、「 [Windows 自動操縦の HoloLens 2 評価ガイド」](hololens2-autopilot.md)を参照してください。

*今すぐ自動操縦プレビューに参加するには、アカウントマネージャーにお問い合わせください。自動操縦準備ができたデバイスは、間もなく発送が開始されます。*

### <a name="fido2-security-key-support"></a>FIDO2 セキュリティキーのサポート

一部のユーザーは、職場または学校の環境で HoloLens デバイスを他のユーザーと共有します。 このため、ユーザーが長いユーザー名とパスワードを入力しなくても簡単に実行できるようにすることが重要です。 高速 id オンライン (FIDO) を使用すると、組織内のすべてのユーザー (Azure AD テナント) は、ユーザー名やパスワードを入力しなくても HoloLens にシームレスにサインインできます。

FIDO2 セキュリティキーは、"unphishable" 標準ベースのパスワードなし認証方法であり、任意のフォームファクターで使用できます。 FIDO は、パスワードなし認証用のオープンスタンダードです。 これにより、ユーザーと組織はユーザー名やパスワードを使用せずに自分のリソースにサインインできるようになります。 代わりに、デバイスに組み込まれている外部セキュリティキーまたはプラットフォームキーを使用します。

開始するには、「 [パスワードなしセキュリティキーのサインインを有効に](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)する」を参照してください。

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>プロビジョニングパッケージによる MDM 登録の向上

プロビジョニングパッケージを使用すると、HoloLens の既定の操作ではなく、構成ファイルを使用して HoloLens 構成を設定できます。 以前は、プロビジョニングパッケージを内部メモリ HoloLens にコピーする必要がありました。 USB ドライブを使用すると、複数の HoloLens デバイスでの再利用が容易になり、デバイスを並行してプロビジョニングすることができます。 プロビジョニングパッケージでは、デバイス管理に登録するためのフィールドもサポートされるようになりました。プロビジョニング後に手動で設定する必要はありません。

実行方法:

1. Windows 構成デザイナーの最新バージョンを Windows ストアから PC にダウンロードします。
1. [**プロビジョニング**] [デバイス  >  の **プロビジョニング HoloLens 2** デバイス] の HoloLens 選択します。
1. 構成プロファイルを作成します。 次に、作成されたすべてのファイルを USB C ストレージデバイスにコピーします。
1. USB C デバイスを、新しくフラッシュした HoloLens に接続します。 次に、**音量を下げ** た電源ボタンを押して、  +  プロビジョニングパッケージを適用します。

### <a name="line-of-business-application-install-status"></a>基幹業務アプリケーションのインストール状態

基幹業務アプリの MDM アプリの展開と管理は、HoloLens するうえで重要です。 管理者とユーザーは、監査と診断のためにアプリのインストール状態を表示する必要があります。 このリリースでは、   >    >  アカウント情報をクリックして設定アカウントに **アクセス職場または学校**  >    >  で詳細を追加しました。

### <a name="additional-csps-and-policies"></a>追加の Csp とポリシー

[構成サービスプロバイダー (CSP)](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN)は、デバイスの構成設定を読み取り、設定、変更、または削除するためのインターフェイスです。 このリリースでは、より多くのポリシーのサポートを追加して、管理者が展開した HoloLens デバイスよりも多くの制御を行うことができます。 HoloLens でサポートされる csp の一覧については、「 [NetworkQoSPolicy csp](/windows/client-management/mdm/networkqospolicy-csp)」を参照してください。

このリリースでの新しい内容

**Policy CSP** 

ポリシー構成サービスプロバイダーを使用すると、企業は Windows デバイスでポリシーを構成できます。 このリリースでは、HoloLens の新しいポリシーを追加しました。このポリシーは、ここに記載されています。 詳細については、 [HoloLens 2 によってサポートされるポリシー csp](/windows/client-management/mdm/policies-supported-by-hololens2)に関するページを参照してください。  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps
- LetAppsAccessGazeInput
- LetAppsAccessGazeInput_ForceAllowTheseApps
- LetAppsAccessGazeInput_ForceDenyTheseApps
- LetAppsAccessGazeInput_UserInControlOfTheseApps
- LetAppsAccessMicrophone_ForceAllowTheseApps
- LetAppsAccessMicrophone_ForceDenyTheseApps
- LetAppsAccessMicrophone_UserInControlOfTheseApps
- AllowWiFi

**NetworkQoSPolicy CSP**

NetworkQoSPolicy 構成サービスプロバイダーは、ネットワークのサービス品質 (QoS) ポリシーを作成します。 QoS ポリシーは、一連の照合条件に基づいて、ネットワーク トラフィックに一連のアクションを実行します。 詳細については、「 [NETWORKQOSPOLICY CSP](/windows/client-management/mdm/networkqospolicy-csp)」を参照してください。

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>5G/LTE テザリングさデバイス向けの拡張された USB イーサネットサポート

5G/LTE フォンや Wi-Fi ホットスポットなど、特定のモバイルブロードバンドデバイスを USB 経由で HoloLens 2 にテザリングさするときに、サポートが追加されました。 これらのデバイスは、別のイーサネット接続として [ **ネットワーク設定** ] に表示されるようになりました。 (外部ドライバーを必要とするモバイルブロードバンドデバイスはサポートされていません)。この機能により、Wi-Fi を利用できず Wi-Fi テザリングで十分なパフォーマンスが得られない場合に、高帯域幅の接続が可能になります。 サポートされている usb デバイスの詳細については、「 [Connect Bluetooth と usb C デバイス](hololens-connect-devices.md)」を参照してください。  

### <a name="hand-tracking-improvements"></a>手動追跡の機能強化

このリリースには、いくつかの手動追跡の機能強化が含まれています。

- **ポイントの安定性:** これで、システムは、palm によって occluded されたときにインデックスの指を resists 曲げます。 この変更により、ボタン、型、コンテンツのスクロールなどをプッシュするときの精度が向上します。 
- **偶発的なエアタップの削減:** エアタップジェスチャの検出を改善しました。 いくつかの一般的なシナリオでは、ユーザーを自分の側にドロップしたときなど、誤ったアクティベーションが減ります。
- **ユーザースイッチの信頼性:** デバイスを共有するときに、手動でサイズを更新すると、システムの速度と信頼性が向上しました。
- **手作業の盗難:** センサーの2つ以上のハンズオンビューがあるケースの処理を改善しました。 複数の人が近くに作業している場合、追跡されたハンドがシーン内の他のユーザーの手に "ジャンプ" する可能性は非常に低くなります。
- **システムの信頼性:** デバイスの負荷が高いときに、ハンドトラッキングが動作を停止する原因となった問題を修正しました。

### <a name="dark-mode"></a>ダーク モード

多くの Windows アプリで、ダークモードとライトモードの両方がサポートされるようになりました。 HoloLens 2 ユーザーは、両方をサポートするアプリの既定のモードを選択できます。 更新後、既定のアプリモードは "ダーク" になりますが、この設定を簡単に変更できます。 [**設定**  >  **システム** の色] に移動し  >    >  **て、既定のアプリモードを選択** します。

これらの "インボックス" アプリでは、ダークモードがサポートされるようになります。

- 設定
- Microsoft Store
- メール
- 予定表
- エクスプローラー
- フィードバック Hub
- OneDrive
- 写真
- 3D ビューアー
- 映画 & テレビ

![ダークモードのウィンドウが並べて表示します。](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>システム音声コマンド

デバイス上の任意のアプリで音声コマンドを使用できるようになりました。 詳細については、「音声を[使用して音声を操作する」をHoloLens。](hololens-cortana.md) 「サポート[されている言語」も参照HoloLens 2。](hololens2-language-support.md)  

### <a name="cortana-updates"></a>Cortana更新プログラム

更新されたアプリは、Microsoft 365と統合され、デバイス全体で (現在、US-Englishされます)。 このHoloLens 2、Cortanaの調整や再起動など、特定のデバイス固有のコマンドがサポートされなくなりました。 これらのオプションは、新しいシステム音声コマンドでサポートされています。 新しいアプリの詳細についてはCortanaブログを[参照してください](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)。

### <a name="quality-improvements-and-fixes"></a>品質の向上と修正

更新プログラムの機能強化と修正:  

- アクティブなディスプレイ調整システムを導入しました。 この機能により、ホログラムの安定性と配置が向上します。 これで、頭を横から横に移動すると、その場所に残ることになります。
- ストリーム配信が定期的Wi-Fi中断HoloLensバグを修正しました。 アプリケーションで低待機時間のストリーミングが必要と示されている場合は [、SetSocketMediaStreamingMode](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)関数 を呼び出して修正プログラムを実装します。
- 調査モードでのストリーミング中に発生したデバイスハングを修正しました。
- セッションを終了するときに、サインイン画面に適切なユーザーが表示されない場合があるバグを修正しました。
- ユーザーが を使用して MDM ログをエクスポートできない問題を **修正設定。**
- すぐに設定した後の目の追跡の精度が予想よりも低い可能性がある問題を修正しました。
- 特定の条件下で、目の追跡サブシステムが初期化または調整を実行できなかった問題を修正しました。
- 既に調整されたユーザーに対して目の調整を求める問題を修正しました。
- 目の調整中にドライバーがクラッシュする問題を修正しました。
- 電源ボタンを繰り返し押すと、60 秒のシステム タイムアウトとシェル クラッシュが発生する可能性がある問題を修正しました。
- 深度バッファーの安定性が向上しました。
- ユーザーがフィードバック **を** 簡単に共有フィードバック Hubに [共有] ボタンを追加しました。
- RoboRaid wan が正しくインストールされないバグを修正しました。

### <a name="known-issues"></a>既知の問題

- zh-CN システム言語に関する問題により、音声コマンドが Mixed Reality キャプチャを取得したり、デバイスの IP アドレスを表示したり妨げる可能性があります。
- 問題では、Cortana"Hey Cortana" 音声アクティブ化を使用するデバイスを起動した後、アプリを起動する必要があります。 18362 ビルドから更新した場合は、以前のバージョンの Cortana アプリの 2 つ目のアプリ タイルが表示され、 [開始] で機能しなくなった場合 **もあります**。

## <a name="windows-holographic-version-1903---may-2020-update"></a>WindowsHolographic バージョン 1903 - 2020 年 5 月更新

- ビルド 18362.1061

この毎月の品質更新プログラムには、前述のように、チームが Windows Holographic バージョン 2004 May Update に取り組っていたため、重要な変更は含められない。

## <a name="windows-holographic-version-1903---april-2020-update"></a>WindowsHolographic バージョン 1903 - 2020 年 4 月更新

- ビルド 18362.1059

**サポートされているアプリのダーク モード**

多くのWindowsアプリでは、ダーク モードとライト モードの両方がサポートされています。 HoloLens 2両方の配色をサポートするアプリの既定のモードを選択できます。 お客様からのフィードバックに基づいて、既定のアプリ モードを "ダーク" に設定していますが、この設定はいつでも簡単に変更できます **。設定 > System > Colors** に移動して、"既定のアプリ モードを選択する" を見つける。

これらの "インボックス" アプリでは、ダーク モードがサポートされます。

- 設定
- Microsoft Store
- メール
- 予定表
- エクスプローラー
- フィードバック Hub
- OneDrive
- 写真
- 3D ビューアー
- 映画 & テレビ

**更新プログラムの機能強化と修正:**

- シェル オーバーレイが Mixed Reality キャプチャに含まれる必要があります。
- Unreal 開発者は、アプリの 3D ビュー ページを使用デバイス ポータルアプリケーションをテストおよびデバッグできます。
- *HolographicDepthReprojectionMethod DepthReprojection* アルゴリズムを使用すると、Mixed Reality キャプチャのホログラムの安定性が向上しました。
- 32 ビット ARM アプリで "WinRT IStreamSocketListener API クラスが登録されていません" というエラーを修正しました。

## <a name="windows-holographic-version-1903---march-2020-update"></a>WindowsHolographic バージョン 1903 - 2020 年 3 月更新

- ビルド 18362.1056

更新プログラムの機能強化と修正:

- *HolographicDepthReprojectionMethod AutoPlanar* アルゴリズムを使用すると、Mixed Reality キャプチャのホログラムの安定性が向上しました。
- 深度 MF サンプルにアタッチされている座標系がパブリック ドキュメントと一致する必要があります。
- 顧客がデバイス ポータルを使用して大量のテキストを貼り付け可能にすることで、開発者の生産性が向上しました。

## <a name="windows-holographic-version-1903---february-2020-update"></a>WindowsHolographic バージョン 1903 - 2020 年 2 月更新

- ビルド 18362.1053

更新プログラムの機能強化と修正:

- Unity アプリケーション用の HolographicSpace.UserPresence API を一時的に無効にしました。 この変更により、"バックグラウンドで実行" 設定が有効になっている場合でも、バイザーが反転した場合に一部のアプリが一時停止する問題が回避されます。
- ユーザーが UI がフリーズし、数秒後にシェルに戻るのをユーザーが気付いた、手の追跡によって発生するランダムな HUP クラッシュを修正しました。
- 人差し指で突っ込むときに、その指の上部が予期せず丸くならずになじむので、手の追跡が改善されました。
- ヘッドトラッキング、空間マッピング、その他のランタイムの信頼性が向上しました。

## <a name="windows-holographic-version-1903---january-2020-update"></a>WindowsHolographic バージョン 1903 - 2020 年 1 月更新

- ビルド 18362.1043

更新プログラムの機能強化と修正:

- アプリケーション エミュレーターを使用する場合の排他アプリの安定性HoloLens 2しました。

## <a name="windows-holographic-version-1903---december-2019-update"></a>WindowsHolographic バージョン 1903 - 2019 年 12 月の更新プログラム

- ビルド 18362.1042

更新プログラムの機能強化と修正:

- 最終ステージの再現 (LSR) の修正が導入されました。 ホログラムの深度をより正確に説明することで、ホログラムの視覚的なレンダリングが向上し、より安定して鮮明に見える。 この現象は、アプリがホログラムの深さを正しく設定しない場合、この更新後に顕著になります。
- 排他的なアプリと排他的なアプリ間のナビゲーションの安定性を修正しました。
- デバイスが数日間スタンバイ状態の後に Mixed Reality キャプチャでビデオを記録できない問題を解決しました。
- ホログラムの安定性が向上しました。

## <a name="windows-holographic-version-1903---november-2019-update"></a>WindowsHolographic バージョン 1903 - 2019 年 11 月の更新プログラム

- ビルド 18362.1039

更新プログラムの機能強化と修正:

- en-CA **と** en-AU の初期セットアップ中に音声コマンドを選択する機能を修正しました。
- 最新の Unity および MRTK (MRTK) バージョンに配置されたオブジェクトMixed Reality Toolkit品質が向上しました。
- アプリケーションが開いてから閉じるまで、ホログラフィック アプリケーションが起動時に一時停止状態でスタックする問題スタート メニュー修正しました。
- OpenXR ランタイム準拠の修正と、HoloLens 2エミュレーターの機能強化。
