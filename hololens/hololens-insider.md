---
title: Microsoft HoloLens の Insider Preview
description: Insider ビルドの使用を開始する方法について説明します。また、次の主要なオペレーティングシステムの更新プログラムに関して、HoloLens の貴重なフィードバックを提供します。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 09/10/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 84ec45a4bb05eb28106e4bfdc915a18ae6330767
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033268"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens の Insider Preview

HoloLens のための最新の Insider Preview ビルドへようこそ。 この機能は簡単に[開始](hololens-insider.md#start-receiving-insider-builds)でき、次の主要なオペレーティングシステムの更新プログラムについての重要なフィードバックを提供します HoloLens。

## <a name="windows-insider-release-notes"></a>WindowsInsider のリリースノート

ここでは、新しい機能を開始して、insider を Windows します。 新しいビルドは、最新の更新プログラムの開発およびベータチャネルに対して実行されます。 Windows Insider ビルドに機能と更新プログラムを追加すると、このページは引き続き更新されます。 これらの更新プログラムを実際のものに混在させることができます。

これは、トラブルシューティングとデバイスレポートの改善、キオスクモードおよび証明書ビューアーの一部の修正されたバグ、拡張された管理面の強化、および更新の信頼性の向上に関するものです。 この機能更新プログラムの新機能として、プラットフォームの移行モードが HoloLens になっています。 HoloLens 2 の新しい優れた機能をすべてご確認ください。

| 特徴量                 | 説明                | ユーザーまたはシナリオ | 導入されたビルド |
|-------------------------|----------------------------|--------------|------------------|
| [プラットフォームモードの移動](#moving-platform-mode) | プラットフォームモードベータの移行について説明します。これにより、構成されている場合、船舶を使用して、動的な動きが発生している大海の大規模な海での HoloLens 2 | すべて | 20348.1411 |
| [証明書マネージャーの PFX ファイルのサポート](#pfx-file-support-for-certificate-manager) | 設定 UI を使用した PFX 証明書の追加 | エンド ユーザー | 20348.1405 |
| [HoloLens の設定で詳細な診断レポートを表示する](#view-advanced-diagnostic-report-in-settings-on-hololens) | デバイスで MDM 診断ログを表示する | トラブルシューティング | 20348.1405 |
| [オフライン診断の通知](#offline-diagnostics-notifications) | ログ収集に関する audiovisual フィードバック | トラブルシューティング | 20348.1405 |
| [低ストレージログ収集の機能強化](#low-storage-log-collection-improvements) | ストレージが不足している場合のログ収集シナリオの改善。 | トラブルシューティング | 20348.1412 |
| [レポート HoloLens の詳細の CSP の変更](#csp-changes-for-reporting-hololens-details) | データを照会するための新しい Csp | IT 管理者    | 20348.1403                 |
| [CSP によって制御される自動ログインポリシー](#auto-login-policy-controlled-by-csp) | アカウントを自動的にログインするために使用されます | IT 管理者 | 20348.1405 |
| [更新の再起動の検出と通知の向上](#improved-update-restart-detection-and-notifications) | 更新プログラム用の新しい有効なポリシーと UX。 | IT 管理者 | 20348.1405 |
| [アプリの更新のためのスマートな再試行](#smart-retry-for-app-updates) | IT 管理者がアプリを更新するためのスケジュールされた再試行を許可します。 | IT 管理者 | 20348.1405 |
| [Microsoft Store にのみプライベートストアアプリを使用する](#use-only-private-store-apps-for-microsoft-store) | 組織のアプリのみを表示するようにストアアプリを構成する | IT 管理者 | 20348.1408 |
| [WDAC アプリと LOB アプリを使用する](#use-wdac-and-lob-apps) | IT 管理者が独自のアプリを使用し、引き続き WDAC を使用して他のアプリをブロックできるようにします。 | IT 管理者 | 20348.1405 |
| [修正プログラムと機能強化](#fixes-and-improvements) | HoloLens の修正と改善。 | すべて | 20348.1411 |

### <a name="it-admin-insider-feature-checklist"></a>IT 管理者の Insider 機能のチェックリスト

✔️、1つの Azure AD アカウントを自動的にログインするように設定する場合は、 [この新しい CSP を構成します。](#auto-login-policy-controlled-by-csp) <br>
✔️更新に失敗した後に自動的に更新を試みるようにアプリを構成する場合は、 [この新しい CSP をスマート再試行用に設定します。](#smart-retry-for-app-updates) <br>
✔️ OS の更新をより細かく制御する場合は、 [新しく有効にした更新ポリシーを確認してください。](#improved-update-restart-detection-and-notifications) <br>
✔️組織のアプリを Microsoft Store を通じて会社のストアで使用できるようにする必要がありますが、完全なストアではなく、組織のアプリへのアクセスのみを許可する場合は、[このポリシーを設定します。](#use-only-private-store-apps-for-microsoft-store) <br>
✔️ HoloLens デバイスの空き記憶域スペース、SSID、または BSSID を知りたい場合は、これらの[レポート csp を確認してください。](#csp-changes-for-reporting-hololens-details) <br>
✔️、WDAC を使用してアプリやプロセスの起動をブロックしたいが、独自の bushiness アプリを使用する必要がある場合は、 [wdac ポリシーで LOB を許可](#use-wdac-and-lob-apps)できるようになりました。

### <a name="moving-platform-mode"></a>プラットフォームモードの移動

**Insider build 20348.1411** の段階では、HoloLens 2 での動的な動き移動プラットフォームを追跡するためのベータサポートを追加しました。 ビルドをインストールし、プラットフォームの移動モードを有効にすると、大規模な船舶や大海船舶など、以前にアクセスできなかった環境で HoloLens 2 を使用できるようになります。 現在、この機能は、これらの特定の移動プラットフォームを有効にすることのみを目的としています。 この機能を他の環境で使用してはいけないことはありませんが、この機能はそもそもこういった環境にサポートを追加することに重点を置いています。

サポートされている機能と、この新機能を有効にする方法の詳細については、「[プラットフォームの移行」ページを参照](hololens2-moving-platform.md)してください。

### <a name="pfx-file-support-for-certificate-manager"></a>証明書マネージャーの PFX ファイルのサポート

Windows Insider build 20348.1405 で導入されました。 .Pfx 証明書を使用するように、 [証明書マネージャー](certificate-manager.md) にサポートを追加しました。 ユーザーが  >  **& セキュリティ**  >  **証明書** を更新設定に移動し、[**証明書のインストール**] を選択すると、UI で .pfx 証明書ファイルがサポートされるようになりました。
ユーザーは、秘密キーを持つ .pfx 証明書をユーザーストアまたはコンピューターストアにインポートできます。

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>HoloLens の設定で詳細な診断レポートを表示する

管理対象デバイスでの動作のトラブルシューティングでは、必要なポリシー構成が適用されていることを確認することが重要な手順です。 以前は、この新機能では、この情報を表示する必要がありました。これは、**設定** アカウントを使用して収集された mdm 診断ログをエクスポートした後、mdm またはデバイスの近くでデバイスからのアクセスを行う必要があり  ->    >  ます。 

これで、Edge ブラウザーを使用してデバイスで MDM 診断を表示できるようになりました。 MDM 診断レポートをより簡単に表示するには、[職場または学校へのアクセス] ページに移動し、[ **詳細な診断レポートの表示**] を選択します。 これにより、レポートが生成され、新しいエッジウィンドウで開きます。

![設定アプリで詳細な診断レポートを表示します。](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>オフライン診断の通知

これは、 [オフライン診断](hololens-diagnostic-logs.md#offline-diagnostics)と呼ばれる既存の機能の更新プログラムです。 以前は、診断コレクションがトリガーされたか、または完了したことをユーザーに明確に示すインジケーターがありませんでした。
Windows Insider ビルドに追加された、オフライン診断に対するオーディオビジュアルフィードバックには、2つの形式があります。 コレクションの開始時と完了時の両方について、最初に表示されるトースト通知が表示されます。 これらは、ユーザーがログインし、視覚エフェクトを持っているときに表示されます。

![ログを収集するためのトースト。](./images/logcollection1.jpg)

![ログの収集が完了したときのトースト。](./images/logcollection2.jpg)

多くの場合、ユーザーがディスプレイにアクセスできない場合にはフォールバックログ収集メカニズムとしてオフライン診断を使用しますが、ログインができない場合や、まだ OOBE にある場合は、ログが収集されるときにオーディオキューも再生されます。 このサウンドは、トースト通知に加えて再生されます。

この新機能は、デバイスが更新された場合に有効になります。有効または管理する必要はない。 この新しいフィードバックを表示または確認できない場合でも、オフライン診断は生成されます。

この新しいオーディオビジュアル フィードバックの追加により、診断データの収集が容易になり、問題をより迅速にトラブルシューティングできると期待しています。

### <a name="low-storage-log-collection-improvements"></a>低ストレージ ログ収集の機能強化

診断ログの収集時にデバイスのディスク領域が少なそうなシナリオでは、StorageDiagnostics.zipという名前 **の追加レポート** が作成されます。 記憶域が少ない場合のしきい値は、ストレージ のWindows[によって決まります](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)。

### <a name="csp-changes-for-reporting-hololens-details"></a>レポートの詳細に関する CSP HoloLens変更

- Insider ビルドWindows 20348.1403 で導入

次の CSP は、デバイスから情報を報告する新しい方法でHoloLensされました。

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP - 無料Storage

DevDetail CSP では、デバイス上の空き記憶域HoloLensも報告されます。 これは、アプリの [アプリ] ページに表示設定値とStorageされます。 この情報を含む特定のノードを次に示します。

- ./DevDetail/Ext/Microsoft/FreeStorage (GET 操作のみ)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP - SSID と BSSID

DeviceStatus CSP では、デバイスがアクティブに接続されているWi-Fiの SSID と BSSID HoloLensも報告されます。 この情報を含む特定のノードを次に示します。

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

この新しい AutoLogonUser ポリシーは、ユーザーが自動的にログオンするかどうかを制御します。 一部のお客様は、ID に関連付けられてもサインイン エクスペリエンスを望んでいないデバイスを設定したいと考えています。 Imagineを選択し、すぐにリモート 支援を使用する必要があります。 または、デバイスを迅速に配布しHoloLensエンド ユーザーがログインを迅速に行えるという利点があります。

ポリシーが空でない値に設定されている場合は、自動ログオン ユーザーの電子メール アドレスを指定します。 自動ログオンを有効にするには、指定したユーザーがデバイスに少なくとも 1 回ログオンする必要があります。

新しいポリシー文字列値の OMA-URI `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`

- 同じ電子メール アドレスを持つユーザーは、自動ログオンを有効にします。

このポリシーが構成されているデバイスでは、ポリシーで指定されたユーザーが少なくとも 1 回ログオンする必要があります。 最初のログオン後にデバイスを再起動すると、指定したユーザーが自動的にログオンします。 1 人の自動ログオン ユーザーだけがサポートされます。 有効にすると、自動的にログオンしたユーザーは手動でログアウトできません。 別のユーザーとしてログオンするには、まずポリシーを無効にする必要があります。

> [!NOTE]
>
> - OS のメジャー更新などの一部のイベントでは、自動ログオン動作を再開するために、指定されたユーザーがデバイスに再度ログオンする必要がある場合があります。
> - 自動ログオンは、MSA ユーザーと AAD ユーザーに対してのみサポートされます。

### <a name="improved-update-restart-detection-and-notifications"></a>更新プログラムの再起動の検出と通知の改善

アクティブな時間とインストール時間のポリシーの間に、デバイスが使用されているHoloLens再起動を回避できます。 ただし、必要な更新プログラムのインストールを完了するために再起動が発生しない場合は、更新プログラムの導入も遅れる可能性があります。 IT が期限と必要な再起動を適用し、更新プログラムのインストールが適切な時間内に完了するためのポリシーを追加しました。 再起動が開始される前にユーザーに通知を受け取り、IT ポリシーに従って再起動を遅らせる可能性があります。

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

### <a name="smart-retry-for-app-updates"></a>アプリ更新プログラムのスマート再試行

HoloLens に対して有効になるのは、IT 管理者が定期的または 1 回の日付を設定して、アプリの使用が原因で更新が失敗したアプリを再起動し、更新プログラムの適用を許可する新しいポリシーです。 これらは、スケジュールされた時刻やサインインなど、いくつかの異なるトリガーに基づいて設定できます。 このポリシーの使用方法の詳細については [、「ApplicationManagement/ScheduleForceRestartForUpdateFailures 」を参照してください](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)。

### <a name="use-only-private-store-apps-for-microsoft-store"></a>プライベート ストア アプリのみを使用してMicrosoft Store

RequirePrivateStoreOnly ポリシーが有効になっているHoloLens。 このポリシーにより、組織Microsoft Storeプライベート ストアのみを表示するようにアプリを構成できます。 使用可能にしたアプリにのみアクセスを制限する。

[ApplicationManagement/RequirePrivateStoreOnly の詳細を確認する](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="use-wdac-and-lob-apps"></a>WDAC アプリと LOB アプリを使用する

WDAC を使用して、アプリまたはプロセスの起動をブロックし、独自の行の機能アプリを引き続き使用できます。 これで、WDAC ポリシーで許可できます。 このポリシーを使用するには、WDAC ポリシーを作成するときに、PowerShell で追加のコード行を実行する必要があります。 [手順については、こちらを参照してください。](/mem/intune/configuration/custom-profile-hololens)

### <a name="fixes-and-improvements"></a>修正と機能強化

- ロックされた [ファイルをダウンロードするプロンプトデバイス ポータルが表示されるという既知の問題を修正しました。](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- ファイルの [アップロードとダウンロードのデバイス ポータルに関する既知の問題を修正しました。](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- デバイスからのコンプライアンス プロパティの報告に関する問題HoloLens対応します。Insider ビルドで正しいレポートをトリガーするには、再起動が必要になる場合があります。  
- 割り[当て](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true)済みアクセス API を有効にし、アプリがデバイスにログインしたユーザー HoloLensキオスク モードで実行されているかどうかをアプリが判断HoloLens。
- 新しいフラッシュにインストールRemote Assistのインボックス バージョンを更新しました。
- Insider ビルドでは、2D アプリのゲームパッド処理が無効になりました。 これを削除することで、アプリは Gamepad API を直接自由に使用し、コントロールのセット全体にアクセスし、必要な操作を実行できます。 開発者は、Gamepad API を使用して Gamepad 入力を使用する必要があります。 Gamepad クラス[(Windows) のサンプルを次に示します。Gaming.Input) - Windows UWP アプリケーション](/uwp/api/windows.gaming.input.gamepad?view=winrt-20348&preserve-view=true)
- 最初のユーザーサインイン後に、AAD グループ ベースのキオスク構成が使用されているシナリオで OOBE が終了する問題を修正しました。
- デバイスの再起動に関する更新通知とダイアログ プロンプトの表示に関する問題を修正しました。

## <a name="start-receiving-insider-builds"></a>Insider ビルドの受信を開始する

> [!NOTE]
> 最近更新していない場合は、デバイスを再起動して状態を更新し、最新のビルドを取得してください。
>
> - "デバイスの再起動" 音声コマンドは正常に機能します。
> - [再起動] ボタンは、設定/Windows Insider Program。
>
> 発生した可能性があるバック エンドにバグがありました。これにより、追跡が戻されます。

デバイスで HoloLens 2 Update 設定Security & に移動Windows Insider Program  >    >  を選択 **概要。** インサイダーとして登録するために使用したアカウントをWindowsします。

Windowsインサイダーはチャネルに移行しています。 高速 **リング** は開発チャネルになり、低速リングはベータ チャネル になり、リリース プレビュー リングはリリースプレビュー チャネル **になります**。 マッピングは次のように表示されます。

![WindowsInsider Channels の説明。](images/WindowsInsiderChannels.png)

詳細については、ブログの[「Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)のWindows参照してください。
次 **に、[** Windows のアクティブな開発 ] を選択し、開発チャネルを受け取るのとビルドをベータ チャネル **を選択し**、プログラムの用語を確認します。
[Confirm **> Restart Now]を選択して** 完了します。 デバイスが再起動したら、[Update 設定 > **Security]** &に移動>更新プログラムを確認して最新のビルドを取得します。

### <a name="update-error-0x80070490-work-around"></a>更新エラー 0x80070490回避

Dev または Beta チャネルで更新0x80070490更新エラーが発生した場合は、次の短期的な回避を試してください。 インサイダー チャネルを移動し、更新プログラムを選択してから、Insider チャネルを戻す必要があります。

#### <a name="stage-one---release-preview"></a>ステージ 1 - リリース プレビュー

1. 設定セキュリティの更新&、Windows Insider Programリリース プレビュー チャネル **] を選択します**。

2. 設定セキュリティの更新&更新プログラムWindows更新プログラムの **確認」を参照してください**。 更新後、ステージ 2 に進む。

#### <a name="stage-two---dev-channel"></a>ステージ 2 - 開発チャネル

1. 設定セキュリティの更新&、Windows Insider Program Dev Channel ]**を選択します**。

2. 設定セキュリティの更新&更新プログラムWindows更新プログラムの **確認」を参照してください**。

## <a name="ffu-download-and-flash-directions"></a>FFU のダウンロードとフラッシュの方向

フライト署名済み ffu でテストするには、フライト署名済み ffu をフラッシュする前に、まずデバイスのロックを解除する必要があります。

1. PC の場合:
    1. から ffu を PC にダウンロードします [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。

    1. 次のコマンドから ARC (Advanced Recovery Companion) をMicrosoft Storeします [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 。

1. [HoloLens - Flight Unlock: Open  >  **設定 Update & Security Windows Insider Program** サインアップし、  >  デバイスを再起動します。

1. Flash FFU - ARC を使用してフライト署名済み FFU をフラッシュできます。

### <a name="provide-feedback-and-report-issues"></a>フィードバックを提供し、問題を報告する

フィードバックを[提供しフィードバック Hub問題](hololens-feedback.md)を報告するには、HoloLensアプリを使用してください。 このフィードバック Hubを使用すると、エンジニアが問題を迅速にデバッグして解決するのに役立つ、必要なすべての診断情報が確実に含まれます。  中国語と日本語のバージョンに関する問題HoloLens同じように報告する必要があります。

> [!NOTE]
> [ドキュメント] フォルダーにアクセスするかどうかを確認するプロンプトフィードバック Hub受け入れる必要があります (メッセージが表示されたら、[はい **]** を選択します)。

## <a name="note-for-developers"></a>開発者向けの注意

お客様は、アプリケーションの Insider ビルドを使用してアプリケーションの開発を試みHoloLens。  使用を開始[するにはHoloLens開発者向けドキュメント](https://developer.microsoft.com/windows/mixed-reality/development)を参照してください。 これらの同じ手順は、アプリケーションの Insider ビルドHoloLens。  Unity と同じビルドを使用して、Visual Studio開発に既に使用HoloLensできます。

## <a name="stop-receiving-insider-builds"></a>Insider ビルドの受信を停止する

Windows Holographic の Insider ビルドを受け取らなくなった場合は、HoloLens が実稼働ビルドを実行している場合はオプトアウトできます。または、Advanced [](hololens-recovery.md) Recovery Companion を使用してデバイスを回復して、Insider 以外のバージョンの Windows Holographic にデバイスを回復することもできます。

> [!CAUTION]
> 新しいプレビュー ビルドを手動で再インストールした後に Insider Preview から登録を解除したユーザーがブルー スクリーンを表示する既知の問題があります。 その後、デバイスを手動で回復する必要があります。 影響を受け取る可能性がある場合の詳細については、この既知の問題に関するページを [参照してください](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)。

お使HoloLensが実稼働ビルドを実行している場合は、次の手順を実行します。

1. [System 設定 > **About] >に移動** し、ビルド番号を見つける。

1. [実稼働ビルド番号については、リリース ノートを参照してください](hololens-release-notes.md)。

Insider ビルドをオプトアウトするには:

1. 実稼働HoloLensを実行している場合は、設定 > Update **& Security**> Windows Insider Program に移動し、[Stop Insider builds]/(Insider ビルドの停止)を **選択します**。

1. 指示に従ってデバイスをオプトアウトします。
