---
title: Microsoft HoloLens の Insider Preview
description: Insider ビルドの使用を開始する方法について説明します。また、次の主要なオペレーティングシステムの更新プログラムに関して、HoloLens の貴重なフィードバックを提供します。
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
ms.date: 08/19/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 3ccb9d0f7175a358262c39c76d364aee464c5469
ms.sourcegitcommit: e2a3e85882b7c594d73d08fbd7ae85856d22f8c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2021
ms.locfileid: "122213912"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens の Insider Preview

HoloLens のための最新の Insider Preview ビルドへようこそ。 この機能は簡単に[開始](hololens-insider.md#start-receiving-insider-builds)でき、次の主要なオペレーティングシステムの更新プログラムについての重要なフィードバックを提供します HoloLens。

## <a name="windows-insider-release-notes"></a>WindowsInsider のリリースノート

ここでは、新しい機能を開始して、insider を Windows します。 新しいビルドは、最新の更新プログラムの開発およびベータチャネルに対して実行されます。 Windows Insider ビルドに機能と更新プログラムを追加すると、このページは引き続き更新されます。 これらの更新プログラムを実際のものに混在させることができます。

| 機能                 | 説明                | ユーザーまたはシナリオ | 導入されたビルド |
|-------------------------|----------------------------|--------------|------------------|
| [レポート HoloLens の詳細の CSP の変更](#csp-changes-for-reporting-hololens-details) | データを照会するための新しい Csp | IT 管理者    | 20348.1403                 |
| [CSP によって制御される自動ログインポリシー](#auto-login-policy-controlled-by-csp) | アカウントを自動的にログインするために使用されます | IT 管理者 | 20348.1405 |
| [更新の再起動の検出と通知の向上](#improved-update-restart-detection-and-notifications) | 更新プログラム用の新しい有効なポリシーと UX。 | IT 管理者 | 20348.1405 |
| [証明書マネージャーの PFX ファイルのサポート](#pfx-file-support-for-certificate-manager) | 設定 UI を使用した PFX 証明書の追加 | エンド ユーザー | 20348.1405 |
| [アプリの更新のためのスマートな再試行](#smart-retry-for-app-updates) | IT 管理者がアプリを更新するためのスケジュールされた再試行を許可します。 | IT 管理者 | 20348.1405 |
| [HoloLens の設定で詳細な診断レポートを表示する](#view-advanced-diagnostic-report-in-settings-on-hololens) | デバイスで MDM 診断ログを表示する | トラブルシューティング | 20348.1405 |
| [オフライン診断の通知](#offline-diagnostics-notifications) | ログ収集に関する audiovisual フィードバック | トラブルシューティング | 20348.1405 |
| [Microsoft Store にのみプライベートストアアプリを使用する](#use-only-private-store-apps-for-microsoft-store) | 組織のアプリのみを表示するようにストアアプリを構成する | IT 管理者 | 20348.1408 |
| [低ストレージログ収集の機能強化](#low-storage-log-collection-improvements) | ストレージが不足している場合のログ収集シナリオの改善。 | IT 管理者 | 20348.1412 |
| [プラットフォームモードの移動](#moving-platform-mode) | プラットフォームモードベータの移行について説明します。これにより、構成されている場合、船舶を使用して、動的な動きが発生している大海の大規模な海での HoloLens 2 | すべて | 20348.1411 |
| [修正プログラムと機能強化](#fixes-and-improvements) | HoloLens の修正と改善。 | すべて | 20348.1411 |

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

アクティブ時間とインストール時間のポリシーの間に、デバイスが使用されているときに HoloLens デバイスを再起動しないようにすることができます。 ただし、必要な更新プログラムのインストールを完了するために再起動が行われない場合は、更新プログラムの導入が遅れることもあります。 ポリシーを追加して、期限および必要な再起動を実施し、更新プログラムのインストールが適時に完了するようにしました。 再起動が開始される前にユーザーに通知し、IT ポリシーに従って再起動を遅らせることができます。

次の更新ポリシーが追加されました:

- [Update/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Update/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [Update/ConfigureDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [Update/ConfigureDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [Update/ConfigureDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [Update/ConfigureDeadlineNoAutoReboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Update/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Update/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Update/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

### <a name="pfx-file-support-for-certificate-manager"></a>証明書マネージャーの PFX ファイルのサポート

Insider ビルド 20348.1405 Windowsで導入されました。 証明書マネージャーに .pfx [証明書を](certificate-manager.md) 使用するサポートが追加されました。 ユーザーが [Update 設定 &セキュリティ証明書] に移動し、[証明書のインストール] を選択すると、UI で .pfx 証明書ファイル  >    >  がサポートされます。 
ユーザーは、ユーザー ストアまたはコンピューター ストアに、プライベート キーを使用して .pfx 証明書をインポートできます。

### <a name="smart-retry-for-app-updates"></a>アプリ更新プログラムのスマート再試行

HoloLens に対して有効になるのは、IT 管理者が定期的または 1 回の日付を設定してアプリの再起動を許可する新しいポリシーです。このポリシーでは、アプリの使用が失敗し、更新プログラムの適用が許可されています。 これらは、スケジュールされた時刻やサインインなど、いくつかの異なるトリガーに基づいて設定できます。 このポリシーの使用方法の詳細については [、「ApplicationManagement/ScheduleForceRestartForUpdateFailures 」を参照してください](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)。

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>詳細な診断レポートは、設定で表示HoloLens

動作のトラブルシューティング時にマネージド デバイスに対して、想定されるポリシー構成が適用されるのを確認することが重要な手順です。 以前は、この新機能では **、設定** アカウント アクセスの仕事または学校を介して収集された MDM 診断ログをエクスポートした後、MDM またはデバイスの近くでデバイスからこれを行い、管理ログをエクスポートし、近くの  ->    >  PCで表示するを選択する必要がありました。

これで、Edge ブラウザーを使用してデバイスで MDM 診断を表示できます。 MDM 診断レポートを簡単に表示するには、[Access work or school]/(学校または学校へのアクセス)ページに移動し、[高度な診断レポートの表示 **] を選択します**。 これにより、新しい Edge ウィンドウでレポートが生成され、開きます。

![アプリで高度な診断レポート設定表示します。](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>オフライン診断通知

これは、オフライン診断 と呼ばれる既存の機能 [の更新プログラムです](hololens-diagnostic-logs.md#offline-diagnostics)。 以前は、診断収集をトリガーした、または完了したユーザーに対する明確なインジケーターは見ていました。
Insider ビルドWindowsに追加されました。オフライン診断には、2 つの形式の視聴覚フィードバックがあります。 1 つ目は、コレクションの開始と完了の両方に対して表示されるトースト通知です。 これらは、ユーザーがログインし、ビジュアルを持つ場合に表示されます。

![ログを収集するトースト。](./images/logcollection1.jpg)

![ログ収集が完了したらトーストします。](./images/logcollection2.jpg)

ユーザーは、ディスプレイにアクセスできない場合、ログインできない、または OOBE にまだ存在する場合のフォールバック ログ収集メカニズムとしてオフライン診断を使用する場合が多いので、ログを収集するときにオーディオ キューも再生されます。 このサウンドは、トースト通知に加えて再生されます。

この新機能は、デバイスが更新された場合に有効になります。有効または管理する必要はない。 この新しいフィードバックを表示または確認できない場合でも、オフライン診断は生成されます。

この新しいオーディオビジュアル フィードバックの追加により、診断データの収集が容易になり、問題をより迅速にトラブルシューティングできると期待しています。

### <a name="use-only-private-store-apps-for-microsoft-store"></a>プライベート ストア アプリのみを使用してMicrosoft Store

RequirePrivateStoreOnly ポリシーが有効になっているHoloLens。 このポリシーにより、組織Microsoft Storeプライベート ストアのみを表示するようにアプリを構成できます。 使用可能にしたアプリにのみアクセスを制限する。

[ApplicationManagement/RequirePrivateStoreOnly の詳細を確認する](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="low-storage-log-collection-improvements"></a>低ストレージ ログ収集の機能強化

診断ログの収集時にデバイスのディスク領域が少なそうなシナリオでは、StorageDiagnostics.zipという名前 **の追加レポート** が作成されます。 記憶域が少ない場合のしきい値は、ストレージ のWindows[によって決まります](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)。

### <a name="moving-platform-mode"></a>プラットフォーム モードの移動

Insider ビルド **20348.1411** の現在、HoloLens 2 で低動的モーション移動プラットフォームの追跡に対するベータ サポートが追加されました。 ビルドをインストールしてプラットフォーム モードの移動を有効にすると、以前はアクセスできない環境 (大型船や大規模な船船など) で HoloLens 2 を使用できます。 現在、この機能は、これらの特定の移動プラットフォームのみを有効にするための機能です。 他の環境でこの機能を使用しようとするのを妨げるものは何もありませんが、この機能では、最初にこれらの環境のサポートを追加する方法に重点が置かされています。

サポートされている機能と、この新機能を有効にする方法の詳細については、プラットフォームの移動に関する [ページを参照してください。](hololens2-moving-platform.md)

### <a name="fixes-and-improvements"></a>修正と機能強化

- ロックされた [ファイルをダウンロードするプロンプトデバイス ポータルが表示される問題の既知の問題を修正しました。](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- ファイルの [アップロードとダウンロードのデバイス ポータルに関する既知の問題を修正しました。](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- デバイスからのコンプライアンス プロパティの報告に関する問題HoloLens対応します。Insider ビルドで正しいレポートをトリガーするには、再起動が必要になる場合があります。  
- 割り[当て](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348)済みアクセス API が有効になっているので、アプリは、HoloLens にログインしたユーザーに対してキオスク モードで実行HoloLens。
- 新しいフラッシュにインストールされているRemote Assistのインボックス バージョンを更新しました。

## <a name="start-receiving-insider-builds"></a>Insider ビルドの受信を開始する

> [!NOTE]
> 最近更新していない場合は、デバイスを再起動して状態を更新し、最新のビルドを取得してください。
>
> - "デバイスの再起動" 音声コマンドは正常に機能します。
> - [再起動] ボタンは、設定/Windows Insider Program。
>
> 発生した可能性があるバック エンドにバグがありました。これにより、追跡が戻されます。

デバイスで HoloLens 2 Update 設定Security & に移動しWindows Insider Program  >    >  を選択 **概要。** インサイダーとして登録するために使用したアカウントWindowsリンクします。

Windowsインサイダーはチャネルに移行しています。 高速 **リング** は開発チャネルになり、低速リングはベータ チャネル になり、リリース プレビュー リングはリリースプレビュー チャネル **になります**。 マッピングは次のように表示されます。

![WindowsInsider Channels の説明](images/WindowsInsiderChannels.png)

詳細については、「 [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs」を参照してください。
次 **に、**[Windows のアクティブな開発] を選択し、開発チャネルまたはベータ チャネル ビルドを受け取 **る** かどうかを選択し、プログラムの用語を確認します。
[Confirm **> Restart Now]を選択** して完了します。 デバイスが再起動したら、[Update 設定 > **Security** &]>[更新プログラムの確認] に移動して最新のビルドを取得します。

### <a name="update-error-0x80070490-work-around"></a>更新エラー 0x80070490回避

Dev または Beta チャネルで更新0x80070490更新エラーが発生した場合は、次の短期的な回避を試してください。 インサイダー チャネルを移動し、更新プログラムを選択してから、Insider チャネルを戻す必要があります。

#### <a name="stage-one---release-preview"></a>ステージ 1 - リリース プレビュー

1. 設定セキュリティの更新&、Windows Insider Program リリース プレビュー チャネル **] を選択します**。

2. 設定セキュリティの更新&更新プログラムWindows更新プログラム **の確認」を参照してください**。 更新後、ステージ 2 に進む。

#### <a name="stage-two---dev-channel"></a>ステージ 2 - 開発チャネル

1. 設定セキュリティの更新&、Windows Insider Program Dev Channel ]**を選択します**。

2. 設定セキュリティの更新&更新プログラムWindows更新プログラム **の確認」を参照してください**。

## <a name="ffu-download-and-flash-directions"></a>FFU のダウンロードとフラッシュの方向

フライト署名済み ffu でテストするには、フライト署名済み ffu をフラッシュする前に、まずデバイスのロックを解除する必要があります。

1. PC の場合:
    1. から ffu を PC にダウンロードします [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。

    1. 次のコマンドから ARC (Advanced Recovery Companion) をMicrosoft Storeします [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 。

1. [HoloLens - Flight Unlock: Open **設定**  >  **Update & Security Windows Insider Program** サインアップし、  >  デバイスを再起動します。

1. Flash FFU - ARC を使用してフライト署名済み FFU をフラッシュできます。

### <a name="provide-feedback-and-report-issues"></a>フィードバックを提供し、問題を報告する

フィードバックを[提供フィードバック Hub問題を報告](hololens-feedback.md)するには、HoloLensアプリを使用してください。 このフィードバック Hubを使用すると、エンジニアが問題を迅速にデバッグして解決するのに役立つ、必要なすべての診断情報が確実に含まれます。  中国語と日本語のバージョンに関する問題HoloLens同じように報告する必要があります。

> [!NOTE]
> [ドキュメント] フォルダーにアクセスするかどうかを確認するプロンプトフィードバック Hub受け入れる必要があります (メッセージが表示されたら、[はい **]** を選択します)。

## <a name="note-for-developers"></a>開発者向けの注意

アプリケーションの Insider ビルドを使用してアプリケーションの開発を試みHoloLens。  使用を開始[するにはHoloLens開発者向けドキュメント](https://developer.microsoft.com/windows/mixed-reality/development)を参照してください。 これらの同じ手順は、アプリケーションの Insider ビルドHoloLens。  Unity と同じビルドを使用して、Visual Studio開発に既に使用しているHoloLensできます。

## <a name="stop-receiving-insider-builds"></a>Insider ビルドの受信を停止する

Windows Holographic の Insider ビルドを受け取らなくなった場合は、HoloLens が実稼働ビルドを実行している場合はオプトアウトできます。または、Advanced [](hololens-recovery.md) Recovery Companion を使用してデバイスを回復して、Insider 以外のバージョンの Windows Holographic にデバイスを回復することもできます。

> [!CAUTION]
> 新しいプレビュー ビルドを手動で再インストールした後に Insider Preview から登録を解除したユーザーがブルー スクリーンを表示する既知の問題があります。 その後、デバイスを手動で回復する必要があります。 影響を受け取る可能性がある場合の詳細については、この既知の問題に関するページを [参照してください](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)。

アプリケーションで実稼働ビルドHoloLensを確認するには、次の手順を実行します。

1. 設定にアクセスし **て > システム > のバージョン情報** を確認し、ビルド番号を見つけます。

1. [実稼働ビルド番号については、リリースノートを参照してください](hololens-release-notes.md)。

Insider ビルドをオプトアウトするには、次のようにします。

1. 実稼働ビルドを実行している HoloLens で、設定にアクセスして **& セキュリティ > Windows insider program > 更新** し、[ **insider ビルドの停止**] を選択します。

1. 指示に従ってデバイスをオプトアウトします。
