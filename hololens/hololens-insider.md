---
title: Microsoft HoloLens の Insider Preview
description: Insider ビルドの使用を開始し、次の主要なオペレーティング システム更新プログラムに関する貴重なフィードバックを提供する方法についてHoloLens。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 08/16/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 80346fd74c9b38ed557d815ed138b1da5702609e
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859019"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens の Insider Preview

最新の Insider Preview ビルドへようこそ HoloLens。 使用を開始し、[次の](hololens-insider.md#start-receiving-insider-builds)主要なオペレーティング システム更新プログラムに関する貴重なフィードバックを提供HoloLens。

## <a name="windows-insider-release-notes"></a>WindowsInsider リリース ノート

Insiders に対する新機能のフライトを開始Windowsしています。 新しいビルドは、最新の更新プログラムのために Dev および Beta チャネルにフライトします。 このページは引き続き更新されます。Insider ビルドの機能と更新プログラムWindows追加します。 これらの更新プログラムを実際に組み合わせ、準備を整えます。

これは、改善されたトラブルシューティングとデバイス レポート、キオスク モードの修正されたバグ、証明書ビューアー、拡張された管理可能性サーフェス、および更新の信頼性の向上に関する情報です。 この機能更新プログラムの新しい主要機能は、HoloLensプラットフォーム モードです。 お使いのための新しい機能を確認HoloLens 2。

| 機能                 | 説明                | ユーザーまたはシナリオ | 導入されたビルド |
|-------------------------|----------------------------|--------------|------------------|
| [プラットフォーム モードの移動](#moving-platform-mode) | 移動プラットフォーム モード ベータ版を導入します。このベータ版では、構成時に、動きの少ない動きが発生しているHoloLens 2大型の船でシステムを使用できます。 | すべて | 20348.1411 |
| [証明書マネージャーの PFX ファイルのサポート](#pfx-file-support-for-certificate-manager) | UI を使用して PFX 証明書設定する | エンド ユーザー | 20348.1405 |
| [詳細な診断レポートは、設定で表示HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | デバイスで MDM 診断ログを表示する | トラブルシューティング | 20348.1405 |
| [オフライン診断通知](#offline-diagnostics-notifications) | ログ収集に関する視聴覚フィードバック | トラブルシューティング | 20348.1405 |
| [低ストレージ ログ収集の機能強化](#low-storage-log-collection-improvements) | ストレージが少ない状況でのログ収集シナリオの改善。 | トラブルシューティング | 20348.1412 |
| [レポートの詳細に関する CSP HoloLens変更](#csp-changes-for-reporting-hololens-details) | データに対してクエリを実行するの新しい CSP | IT 管理者    | 20348.1403                 |
| [CSP によって制御される自動ログイン ポリシー](#auto-login-policy-controlled-by-csp) | アカウントを自動的にログインするために使用されます | IT 管理者 | 20348.1405 |
| [更新プログラムの再起動の検出と通知の改善](#improved-update-restart-detection-and-notifications) | 新しく有効にされたポリシーと更新プログラムの UX。 | IT 管理者 | 20348.1405 |
| [アプリ更新プログラムのスマート再試行](#smart-retry-for-app-updates) | IT 管理者がアプリを更新するためにスケジュールされた再試行を許可します。 | IT 管理者 | 20348.1405 |
| [プライベート ストア アプリのみをプライベート ストア アプリにMicrosoft Store](#use-only-private-store-apps-for-microsoft-store) | 組織のアプリのみを表示するストア アプリを構成する | IT 管理者 | 20348.1408 |
| [WDAC アプリと LOB アプリを使用する](#use-wdac-and-lob-apps) | IT 管理者が独自のアプリを使用し、WDAC を使用して他のアプリをブロックできます。 | IT 管理者 | 20348.1405 |
| [修正と機能強化](#fixes-and-improvements) | 更新プログラムの修正とHoloLens。 | すべて | 20348.1411 |

### <a name="it-admin-insider-feature-checklist"></a>IT 管理者のインサイダー機能のチェックリスト

✔️アカウントを 1 つ設定して自動的にログインAzure AD場合は、この新しい [CSP を構成します。](#auto-login-policy-controlled-by-csp) <br>
✔️更新に失敗した後に自動的に更新を試行するアプリを構成する場合は、この新しい CSP をスマート 再試行 [用に設定します。](#smart-retry-for-app-updates) <br>
✔️ OS の更新を詳細に制御する場合は、これらの新しく有効にされた更新 [ポリシーを確認してください。](#improved-update-restart-detection-and-notifications) <br>
✔️ Microsoft Store 経由で組織のアプリを会社のストアで使用できる必要があるが、完全なストアではなく組織のアプリへのアクセスのみを許可する場合は、このポリシーを設定します。 [](#use-only-private-store-apps-for-microsoft-store) <br>
✔️ デバイスの空き記憶域スペース、SSID、または BSSID を知りたい場合はHoloLensこれらのレポートの SSID を[確認してください。](#csp-changes-for-reporting-hololens-details) <br>
✔️ WDAC を使用してアプリまたはプロセスの起動をブロックするが、独自の行の機能アプリを使用する必要がある場合は [、WDAC](#use-wdac-and-lob-apps)ポリシー で LOB を許可できます。

### <a name="moving-platform-mode"></a>プラットフォーム モードの移動

Insider ビルド **20348.1411** の段階で、HoloLens 2 の低動的モーション移動プラットフォームの追跡に対するベータ サポートが追加されました。 ビルドをインストールしてプラットフォーム モードの移動を有効にすると、以前はアクセスできない環境 (大型船や大型の船船など) で HoloLens 2 を使用できます。 現在、この機能は、これらの特定の移動プラットフォームを有効にすることのみを目的としています。 この機能を他の環境で使用してはいけないことはありませんが、この機能はそもそもこういった環境にサポートを追加することに重点を置いています。

サポートされている機能と、この新機能を有効にする方法の詳細については、プラットフォームの移動に関する [ページを参照してください。](hololens2-moving-platform.md)

### <a name="pfx-file-support-for-certificate-manager"></a>証明書マネージャーの PFX ファイルのサポート

Insider ビルド 20348.1405 Windowsで導入されました。 証明書マネージャーに .pfx [証明書を](certificate-manager.md) 使用するサポートが追加されました。 ユーザーが [Update 設定 &セキュリティ証明書] に移動し、[証明書のインストール] を選択すると、UI で .pfx 証明書ファイル  >    >  がサポートされます。 
ユーザーは、ユーザー ストアまたはコンピューター ストアに、プライベート キーを使用して .pfx 証明書をインポートできます。

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>詳細な診断レポートは、設定で表示HoloLens

動作のトラブルシューティング時にマネージド デバイスに対して、想定されるポリシー構成が適用されるのを確認することが重要な手順です。 以前は、この新機能では、この情報を MDM 経由で、または **設定** アカウント アクセスの仕事または学校を介して収集された MDM 診断ログをエクスポートした後、デバイスの近くでこの情報を表示し、管理ログをエクスポートし、近くの  ->    >  PCで表示するを選択する必要がありました。

これで、Edge ブラウザーを使用してデバイスで MDM 診断を表示できます。 MDM 診断レポートを簡単に表示するには、[Access work or school]/(学校または学校へのアクセス)ページに移動し、[高度な診断レポートの表示 **] を選択します**。 これにより、新しい Edge ウィンドウでレポートが生成され、開きます。

![アプリで高度な診断レポート設定表示します。](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>オフライン診断通知

これは、オフライン診断 と呼ばれる既存の機能 [の更新プログラムです](hololens-diagnostic-logs.md#offline-diagnostics)。 以前は、診断収集をトリガーした、または完了したユーザーに対する明確なインジケーターは見ていました。
Insider ビルドWindowsに追加されました。オフライン診断には、2 つの形式の視聴覚フィードバックがあります。 1 つ目は、コレクションの開始と完了の両方に対して表示されるトースト通知です。 これらは、ユーザーがログインし、ビジュアルを持つ場合に表示されます。

![ログを収集するトースト。](./images/logcollection1.jpg)

![ログ収集が完了したらトーストします。](./images/logcollection2.jpg)

ユーザーは、ディスプレイにアクセスできない場合、ログインできない、または OOBE にまだ存在する場合のフォールバック ログ収集メカニズムとしてオフライン診断を使用する場合が多いので、ログを収集するときにオーディオ キューも再生されます。 このサウンドは、トースト通知に加えて再生されます。

この新機能は、デバイスの更新時に有効になり、有効にしたり管理したりする必要はありません。 この新しいフィードバックを表示したり聞いたりできない場合でも、オフライン診断は引き続き生成されます。

この新しいオーディオビジュアルフィードバックの追加により、診断データを簡単に収集し、問題のトラブルシューティングをより簡単に行うことができます。

### <a name="low-storage-log-collection-improvements"></a>低ストレージログ収集の機能強化

診断ログを収集するときにデバイスのディスク領域が不足していると思われる場合は、 **StorageDiagnostics.zip** という名前の追加のレポートが作成されます。 低ストレージのしきい値は、Windows ストレージの[意味](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)で自動的に決定されます。

### <a name="csp-changes-for-reporting-hololens-details"></a>レポート HoloLens の詳細の CSP の変更

- Windows Insider build、20348.1403 で導入されました

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

### <a name="smart-retry-for-app-updates"></a>アプリの更新のためのスマートな再試行

現在、HoloLens が有効になっています。これにより、IT 管理者は、更新プログラムの適用を許可するアプリが使用中であるために更新が失敗したアプリを再起動するように、定期的または1回の日付を設定できます。 これらは、スケジュールされた時刻やサインインなど、いくつかの異なるトリガーに基づいて設定できます。 このポリシーを使用する方法の詳細については、「 [Applicationmanagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)」を参照してください。

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Microsoft Store の専用ストアアプリのみを使用する

RequirePrivateStoreOnly ポリシーは HoloLens に対して有効になっています。 このポリシーを使用すると、組織用に構成されたプライベートストアのみを表示するように Microsoft Store アプリを構成できます。 使用できるようにしたアプリのみにアクセスを制限する。

[Applicationmanagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)の詳細情報

### <a name="use-wdac-and-lob-apps"></a>WDAC アプリと LOB アプリを使用する

WDAC を使用して、アプリやプロセスの起動をブロックし、独自の bushiness アプリを引き続き使用できるようになりました。 これで、WDAC ポリシーで許可できるようになりました。 このポリシーを使用するには、WDAC ポリシーを作成するときに、PowerShell で余分なコード行を実行する必要があります。 [こちらの手順を確認してください。](/mem/intune/configuration/custom-profile-hololens)

### <a name="fixes-and-improvements"></a>修正プログラムと機能強化

- [ロックされたファイルをダウンロードするプロンプトがないデバイスポータルの既知の問題を修正しました。](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- [ファイルのアップロードとダウンロードのタイムアウトを含むデバイスポータルの既知の問題](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)を修正した。
- HoloLens デバイスからのコンプライアンスプロパティのレポートに関する問題に対処します。Insider ビルドで適切なレポートをトリガーするには、再起動が必要になることがあります。  
- [割り当てられたアクセス API](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348)を有効にし、アプリが HoloLens にログインしているユーザーに対してキオスクモードで実行されている HoloLens かどうかを確認できるようになりました。
- 新しい点滅にインストールされているリモートアシスタンスのインボックスバージョンが更新されました。

## <a name="start-receiving-insider-builds"></a>Insider ビルドの受信を開始します

> [!NOTE]
> 最近更新したことがない場合は、デバイスを再起動して状態を更新し、最新のビルドを取得してください。
>
> - "デバイスの再起動" 音声コマンドは正常に機能します。
> - 設定/Windows Insider プログラムで [再起動] ボタンを選択することもできます。
>
> バックエンドには、発生した可能性があるバグがあり、これによって追跡が再開されます。

HoloLens 2 デバイスで、[   >  **セキュリティ**  >  **Windows Insider program** & 設定更新] をクリックし、[**開始**] を選択します。 Windows Insider として登録するために使用したアカウントをリンクします。

Windows insider がチャネルに移行しています。 **高速** リングが **開発チャネル** になり、**低速** リングが **ベータチャネル** になり、 **release preview** リングが **release preview チャネル** になります。 マッピングは次のようになります。

![Windows内部のチャネルの説明](images/WindowsInsiderChannels.png)

詳細については、Windows ブログの「 [Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) channel の概要」を参照してください。
次に、[ **Windows のアクティブな開発**] を選択し、**開発チャネル** または **ベータチャネル** のビルドを受信するかどうかを選択して、プログラムの条件を確認します。
[ **Confirm > Restart Now** ] を選択して終了します。 デバイスが再起動されたら、> 設定に移動して & セキュリティ > 更新し、最新のビルドを取得するために **更新プログラムを確認** ます。

### <a name="update-error-0x80070490-work-around"></a>Update エラー0x80070490 の回避策

Dev または Beta チャネルで更新するときに update エラー0x80070490 が発生した場合は、次の短期的な回避策を試してください。 これには、insider チャネルを移動し、更新を選択して、Insider channel を戻す必要があります。

#### <a name="stage-one---release-preview"></a>ステージワンリリースプレビュー

1. 設定]、[Update & Security]、[Windows Insider program] を選択し、[ **Release Preview Channel**] を選択します。

2. 設定、更新プログラム & セキュリティ、Windows Update、**更新プログラムを確認** します。 更新後、段階2に進みます。

#### <a name="stage-two---dev-channel"></a>ステージ2開発チャネル

1. 設定、Update & Security、Windows Insider program で、[ **Dev Channel**] を選択します。

2. 設定、更新プログラム & セキュリティ、Windows Update、**更新プログラムを確認** します。

## <a name="ffu-download-and-flash-directions"></a>FFU のダウンロードとフラッシュの方向

フライト署名済み ffu を使用してテストするには、フライト署名済み ffu を点滅させる前にデバイスのロックを解除する必要があります。

1. PC の場合:
    1. から PC に ffu をダウンロード [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) します。

    1. Microsoft Store から ARC (Advanced Recovery コンパニオン) をインストール [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) します。

1. HoloLens フライトのロック解除:   >  **& セキュリティ**  >  **Windows Insider プログラム** を開き設定更新し、サインアップして、デバイスを再起動します。

1. Flash FFU-atc を使用して、デジタル署名された FFU をフラッシュできるようになりました。

### <a name="provide-feedback-and-report-issues"></a>フィードバックの提供と問題の報告

フィードバックを提供し、問題を報告するに[は、HoloLens でフィードバックハブアプリ](hololens-feedback.md)を使用してください。 フィードバックハブを使用すると、エンジニアが迅速に問題をデバッグして解決できるように、必要な診断情報がすべて含まれるようになります。  HoloLens の中国語と日本語バージョンに関する問題は、同じように報告する必要があります。

> [!NOTE]
> フィードバックハブがドキュメントフォルダーにアクセスするかどうかを確認するメッセージが表示されることを確認します (メッセージが表示されたら [ **はい]** を選択します)。

## <a name="note-for-developers"></a>開発者向けのメモ

HoloLens の Insider ビルドを使用してアプリケーションを開発することをお勧めします。  作業を開始するには、 [HoloLens 開発者向けドキュメント](https://developer.microsoft.com/windows/mixed-reality/development)を参照してください。 これらの同じ手順は、HoloLens の内部のビルドでも機能します。  Unity の同じビルドと、HoloLens 開発に既に使用している Visual Studio を使用できます。

## <a name="stop-receiving-insider-builds"></a>Insider ビルドの受信を停止します

Windows Holographic の insider ビルドを受信する必要がなくなった場合は、HoloLens が実稼働ビルドを実行しているタイミングをオプトアウトできます。または、Advanced Recovery コンパニオンを使用してデバイスを[回復](hololens-recovery.md)し、デバイスを Insider バージョン以外の Windows Holographic に回復することもできます。

> [!CAUTION]
> 新しいプレビュービルドを手動で再インストールした後に、Insider Preview ビルドから登録を解除したユーザーがブルースクリーンを使用するという既知の問題があります。 その後、デバイスを手動で回復する必要があります。 影響を受けるかどうかに関する詳細については、この既知の [問題](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)を参照してください。

HoloLens が運用ビルドを実行していることを確認するには、次のようにします。

1. 設定にアクセスし **て > システム > のバージョン情報** を確認し、ビルド番号を見つけます。

1. [実稼働ビルド番号については、リリースノートを参照してください](hololens-release-notes.md)。

Insider ビルドをオプトアウトするには、次のようにします。

1. 実稼働ビルドを実行している HoloLens で、設定にアクセスして **& セキュリティ > Windows insider program > 更新** し、[ **insider ビルドの停止**] を選択します。

1. 指示に従ってデバイスをオプトアウトします。
