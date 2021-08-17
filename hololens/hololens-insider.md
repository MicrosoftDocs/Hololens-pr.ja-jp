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
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 86a763adb233b45242182d069a56692aeddc2e59
ms.sourcegitcommit: 5cb3230e02e703584e50358cb0f0b5f33a51b169
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "121858583"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens の Insider Preview

最新の Insider Preview ビルドへようこそ HoloLens。 新しいオペレーティング システム[の次](hololens-insider.md#start-receiving-insider-builds)の主要な更新プログラムについては、簡単に開始して貴重なフィードバックを提供HoloLens。

## <a name="windows-insider-release-notes"></a>WindowsInsider リリース ノート

新しい機能のフライトを開始して、Insiders Windows開始します。 新しいビルドは、最新の更新プログラムのために Dev および Beta チャネルにフライトします。 このページは引き続き更新されます。Insider ビルドの機能と更新プログラムWindows追加します。 これらの更新プログラムを実際に組み合わせ、準備を整えます。

| 機能                 | 説明                | ユーザーまたはシナリオ | 導入されたビルド |
|-------------------------|----------------------------|--------------|------------------|
| [レポートの詳細に関する CSP HoloLens変更](#csp-changes-for-reporting-hololens-details) | データに対してクエリを実行するの新しい CSP | IT 管理者    | 20348.1403                 |
| [CSP によって制御される自動ログイン ポリシー](#auto-login-policy-controlled-by-csp) | アカウントを自動的にログインするために使用されます | IT 管理者 | 20348.1405 |
| [更新プログラムの再起動の検出と通知の改善](#improved-update-restart-detection-and-notifications) | 更新プログラムに対して有効な新しいセキュリティ と UX。 | IT 管理者 | 20348.1405 |
| [証明書マネージャーの PFX ファイルのサポート](#pfx-file-support-for-certificate-manager) | UI を使用して PFX 証明書設定する | エンド ユーザー | 20348.1405 |
| [アプリ更新プログラムのスマート再試行](#smart-retry-for-app-updates) | IT 管理者がアプリを更新するためにスケジュールされた再試行を許可します。 | IT 管理者 | 20348.1405 |
| [詳細な診断レポートは、設定で表示HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | デバイスで MDM 診断ログを表示する | トラブルシューティング | 20348.1405 |
| [オフライン診断通知](#offline-diagnostics-notifications) | ログ収集に関する視聴覚フィードバック | トラブルシューティング | 20348.1405 |
| [プライベート ストア アプリのみをプライベート ストア アプリにMicrosoft Store](#use-only-private-store-apps-for-microsoft-store) | 組織のアプリのみを表示するストア アプリを構成する | IT 管理者 | 20348.1408 |
| [低ストレージ ログ収集の機能強化](#low-storage-log-collection-improvements) | ストレージが少ない状況でのログ収集シナリオの改善。 | IT 管理者 | 20348.1412 |
| [プラットフォーム モードの移動](#moving-platform-mode) | 移動プラットフォーム モード ベータ版を導入します。このベータ版では、構成すると、動きの少ない動きをHoloLens 2大きな船に対して、移動プラットフォーム モードベータ版を使用できます。 | すべて | 20348.1411 |
| [修正と機能強化](#fixes-and-improvements) | 更新プログラムの修正とHoloLens。 | すべて | 20348.1411 |

### <a name="csp-changes-for-reporting-hololens-details"></a>レポートの詳細に関する CSP HoloLens変更

- Insider ビルドでWindows、20348.1403 で導入されました

次の PS は、デバイスから情報を報告する新しい方法でHoloLensされました。

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP - 無料Storage

DevDetail CSP では、デバイス上の空き記憶域HoloLensも報告されます。 これは、アプリの [アプリ] ページに表示設定値とStorage一致する必要があります。 この情報を含む特定のノードを次に示します。

- ./DevDetail/Ext/Microsoft/FreeStorage (GET 操作のみ)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP - SSID と BSSID

DeviceStatus CSP では、アクティブに接続されているネットワークWi-Fi SSID と BSSID HoloLens報告する機能も追加されています。 この情報を含む特定のノードを次に示します。

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac* アドレス (Wi-Fi /SSID)
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac* Wi-Fi /BSSID

NetworkIdentifiers のクエリを実行する syncml BLOB の例 (MDM ベンダー向け)

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

### <a name="auto-login-policy-controlled-by-csp"></a>CSP によって制御される自動ログイン ポリシー

この新しい AutoLogonUser ポリシーは、ユーザーが自動的にログオンするかどうかを制御します。 一部のお客様は、ID に関連付けられてもサインイン エクスペリエンスを望んでいないデバイスを設定したいと考えています。 Imagineを選択し、すぐにリモート 支援を使用する必要があります。 または、デバイスを迅速に配布し、エンド ユーザーがHoloLensを迅速に行えるという利点があります。

ポリシーが空でない値に設定されている場合は、自動ログオン ユーザーの電子メール アドレスを指定します。 自動ログオンを有効にするには、指定したユーザーがデバイスに少なくとも 1 回ログオンする必要があります。

新しいポリシー文字列値の OMA-URI `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`

- 同じ電子メール アドレスを持つユーザーは、自動ログオンを有効にします。

このポリシーが構成されているデバイスでは、ポリシーで指定されたユーザーが少なくとも 1 回ログオンする必要があります。 最初のログオン後にデバイスを再起動すると、指定したユーザーが自動的にログオンします。 1 人の自動ログオン ユーザーだけがサポートされます。 有効にすると、自動的にログオンしたユーザーは手動でログアウトできません。 別のユーザーとしてログオンするには、まずポリシーを無効にする必要があります。

> [!NOTE]
>
> - OS のメジャー更新などの一部のイベントでは、自動ログオン動作を再開するために、指定されたユーザーがデバイスに再度ログオンする必要がある場合があります。
> - 自動ログオンは、MSA ユーザーと AAD ユーザーに対してのみサポートされます。

### <a name="improved-update-restart-detection-and-notifications"></a>更新プログラムの再起動の検出と通知の改善

アクティブな時間とインストール時間ポリシーの間に、デバイスが使用されているHoloLens再起動を回避できます。 ただし、必要な更新プログラムのインストールを完了するために再起動が発生しない場合は、更新プログラムの導入も遅れる可能性があります。 IT が期限と必要な再起動を適用し、更新プログラムのインストールが適切な時間内に完了するためのポリシーを追加しました。 再起動が開始される前にユーザーに通知を受け取り、IT ポリシーに従って再起動を遅らせる可能性があります。

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

診断ログの収集時にデバイスのディスク領域が少なそうなシナリオでは、StorageDiagnostics.zipという名前 **の追加レポート** が作成されます。 記憶域が少ない場合のしきい値は、記憶域のWindows[によって自動的に決定されます](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)。

### <a name="moving-platform-mode"></a>プラットフォーム モードの移動

Insider ビルド **20348.1411** の段階で、HoloLens 2 の低動的モーション移動プラットフォームを追跡するためのベータ サポートが追加されました。 ビルドをインストールしてプラットフォーム モードの移動を有効にすると、大規模な船や大型の船など、以前はアクセスできない環境で HoloLens 2 を使用できます。 現在、この機能は、これらの特定の移動プラットフォームのみを有効にするための機能です。 他の環境でこの機能を使用しようとするのを妨げるものは何もありませんが、この機能では、最初にこれらの環境のサポートを追加する方法に重点が置かされています。

サポートされている機能と、この新機能を有効にする方法の詳細については、プラットフォームの移動に関する [ページを参照してください。](hololens2-moving-platform.md)

### <a name="fixes-and-improvements"></a>修正と機能強化

- ロックされた [ファイルをダウンロードするプロンプトデバイス ポータルが表示される問題の既知の問題を修正しました。](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- ファイルの [アップロードとダウンロードのデバイス ポータルに関する既知の問題を修正しました。](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- デバイスからのコンプライアンス プロパティの報告に関する問題HoloLens修正します。Insider ビルドで正しいレポートをトリガーするには、再起動が必要になる場合があります。  
- 割り[当て](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348)済みアクセス API が有効になっているので、アプリは、HoloLens にログインしたユーザーに対してキオスク モードで実行HoloLens。
- 新しいフラッシュにインストールされている Remote Assistのインボックス バージョンを更新しました。

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
次 **に、[** Windows のアクティブな開発 ] を選択し、開発チャネルまたはビルドを受け取 **ベータ チャネル** 選択し、プログラムの用語を確認します。
[Confirm **> Restart Now]を選択** して完了します。 デバイスが再起動したら、[Update 設定 > **Security** &]>[更新プログラムの確認] に移動して最新のビルドを取得します。

### <a name="update-error-0x80070490-work-around"></a>更新エラー 0x80070490回避

Dev または Beta チャネルで更新0x80070490更新エラーが発生した場合は、次の短期的な回避を試してください。 インサイダー チャネルを移動し、更新プログラムを選択してから、Insider チャネルを戻す必要があります。

#### <a name="stage-one---release-preview"></a>ステージ 1 - リリース プレビュー

1. 設定セキュリティの更新&、Windows Insider Program リリース プレビュー チャネル **] を選択します**。

2. 設定セキュリティの更新&更新プログラムWindows更新プログラムの **確認」を参照してください**。 更新後、ステージ 2 に進む。

#### <a name="stage-two---dev-channel"></a>ステージ 2 - 開発チャネル

1. 設定セキュリティの更新&、Windows Insider Program Dev Channel ]**を選択します**。

2. 設定セキュリティの更新&更新プログラムWindows更新プログラムの **確認」を参照してください**。

## <a name="ffu-download-and-flash-directions"></a>FFU のダウンロードとフラッシュの方向

フライト署名済み ffu でテストするには、フライト署名済み ffu をフラッシュする前に、まずデバイスのロックを解除する必要があります。

1. PC の場合:
    1. から ffu を PC にダウンロードします [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。

    1. 次のコマンドから ARC (Advanced Recovery Companion) をMicrosoft Storeします [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 。

1. [HoloLens - Flight Unlock: Open **設定**  >  **Update & Security Windows Insider Program** サインアップし、  >  デバイスを再起動します。

1. Flash FFU - ARC を使用してフライト署名済み FFU をフラッシュできます。

### <a name="provide-feedback-and-report-issues"></a>フィードバックを提供し、問題を報告する

フィードバックを[提供しフィードバック Hub問題](hololens-feedback.md)を報告するには、HoloLensアプリを使用してください。 このフィードバック Hubを使用すると、エンジニアが問題を迅速にデバッグして解決するのに役立つ、必要なすべての診断情報が確実に含まれます。  中国語と日本語のバージョンに関する問題HoloLens同じように報告する必要があります。

> [!NOTE]
> [ドキュメント] フォルダーにアクセスするかどうかを確認するプロンプトフィードバック Hub受け入れる必要があります (メッセージが表示されたら、[は **い]** を選択します)。

## <a name="note-for-developers"></a>開発者向けの注意

アプリケーションの Insider ビルドを使用してアプリケーションの開発を試みHoloLens。  使用を開始[するにはHoloLens開発者向けドキュメント](https://developer.microsoft.com/windows/mixed-reality/development)を参照してください。 これらの同じ手順は、アプリケーションの Insider ビルドHoloLens。  Unity と同じビルドを使用して、Visual Studio開発に既に使用しているHoloLensできます。

## <a name="stop-receiving-insider-builds"></a>Insider ビルドの受信を停止する

Windows Holographic の Insider ビルドを受け取らなくなった場合は、HoloLens が実稼働ビルドを実行している場合はオプトアウトできます。または、Advanced [](hololens-recovery.md) Recovery Companion を使用してデバイスを回復して、Insider 以外のバージョンの Windows Holographic にデバイスを回復することもできます。

> [!CAUTION]
> 新しいプレビュー ビルドを手動で再インストールした後に Insider Preview から登録を解除したユーザーがブルー スクリーンを表示する既知の問題があります。 その後、デバイスを手動で回復する必要があります。 影響を受け取る可能性がある場合の詳細については、この既知の問題に関するページを [参照してください](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)。

アプリケーションで実稼働ビルドHoloLensを確認するには、次の手順を実行します。

1. [System **設定 > About] >に移動** し、ビルド番号を見つける。

1. [実稼働ビルド番号については、リリース ノートを参照してください](hololens-release-notes.md)。

Insider ビルドをオプトアウトするには:

1. 実稼働HoloLensを実行している場合は、設定 > **Update & Security**> Windows Insider Program に移動し、[Stop Insider builds]/(Insider ビルドの停止)を **選択します**。

1. 指示に従ってデバイスをオプトアウトします。
