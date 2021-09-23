---
title: Microsoft HoloLens の Insider Preview
description: Insider ビルドの使用を開始し、次の主要なオペレーティング システム更新プログラムに関する貴重なフィードバックを提供する方法についてHoloLens。
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
ms.date: 09/14/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 22d635fd3fc32b8aedc36bcb19d900128cdcb718
ms.sourcegitcommit: ab86b31357004726d8a28ebae76123728adc8e59
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2021
ms.locfileid: "128306167"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens の Insider Preview

最新の Insider Preview ビルドへようこそ HoloLens。 使用を開始し、[次の](hololens-insider.md#start-receiving-insider-builds)主要なオペレーティング システムの更新プログラムに関する貴重なフィードバックを提供HoloLens。

## <a name="windows-insider-release-notes"></a>WindowsInsider リリース ノート

新しい機能のフライトを開始して、Insiders Windows開始します。 新しいビルドは、最新の更新プログラムのために Dev および Beta チャネルにフライトします。 このページは引き続き更新されます。Insider ビルドの機能と更新プログラムWindows追加します。 これらの更新プログラムを実際に組み合わせ、準備を整えます。

これは、改善されたトラブルシューティングとデバイス レポート、キオスク モードの修正されたバグ、証明書ビューアー、拡張された管理可能性サーフェス、および更新の信頼性の向上に関する情報です。 この機能更新プログラムの新しい主要な機能は、HoloLensプラットフォーム モードです。 この機能に関する新しい機能HoloLens 2。

| 機能                 | 説明                | ユーザーまたはシナリオ | 導入されたビルド |
|-------------------------|----------------------------|--------------|------------------|
| [プラットフォーム モードの移動](#moving-platform-mode) | プラットフォーム モードの移動ベータ版を導入します。このベータ版では、構成時に、動きの少ないHoloLens 2発生している大規模な船に対して移動プラットフォーム モードを使用できます。 | すべて | 20348.1411 |
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
✔️ OS の更新を詳細に制御する場合は、これらの新しく有効にされた更新ポリシー [を確認してください](#improved-update-restart-detection-and-notifications)。 <br>
✔️ Microsoft Store 経由で会社のストアで組織のアプリを使用できる必要があるが、完全なストアではなく組織のアプリへのアクセスのみを許可する場合は、このポリシー を[設定します](#use-only-private-store-apps-for-microsoft-store)。 <br>
✔️ デバイスの空き記憶域スペース、SSID、または BSSID を知りたい場合は、HoloLensの「」を[参照してください](#csp-changes-for-reporting-hololens-details)。 <br>
✔️ WDAC を使用してアプリまたはプロセスの起動をブロックするが、独自の行の機能アプリを使用する必要がある場合は [、WDAC](#use-wdac-and-lob-apps)ポリシー で LOB を許可できます。

### <a name="moving-platform-mode"></a>プラットフォーム モードの移動

Insider ビルド **20348.1411** の段階で、HoloLens 2 の低動的モーション移動プラットフォームの追跡に対するベータ サポートが追加されました。 ビルドをインストールしてプラットフォーム モードの移動を有効にすると、以前はアクセスできない環境 (大型船や大型の船船など) で HoloLens 2 を使用できます。 現在、この機能は、これらの特定の移動プラットフォームを有効にすることのみを目的としています。 この機能を他の環境で使用してはいけないことはありませんが、この機能はそもそもこういった環境にサポートを追加することに重点を置いています。

サポートされている機能と、この新機能を有効にする方法の詳細については、プラットフォームの移動に関する [ページを参照してください](hololens2-moving-platform.md)。

#### <a name="overview-to-try-out-moving-platform-mode"></a>プラットフォーム モードの移動を試す方法の概要

1. [開発者モードとデバイス ポータルを有効にします](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。
1. [デバイス ポータル を使用してプラットフォーム モードの移動を有効にします](hololens2-moving-platform.md#enabling-moving-platform-mode)。
1. デバイスを大きな移動プラットフォームに移動し、ホログラムの安定性を確認します。

### <a name="pfx-file-support-for-certificate-manager"></a>証明書マネージャーの PFX ファイルのサポート

Insider ビルド 20348.1405 Windowsで導入されました。 証明書マネージャーに .pfx [証明書を](certificate-manager.md) 使用するサポートが追加されました。 ユーザーが [Update 設定 &セキュリティ証明書] に移動し、[証明書のインストール] を選択すると、UI で .pfx 証明書ファイル  >    >  がサポートされます。 
ユーザーは、ユーザー ストアまたはコンピューター ストアに、プライベート キーを使用して .pfx 証明書をインポートできます。

#### <a name="overview-to-try-out-pfx-files-in-certificate-manager"></a>証明書マネージャーで PFX ファイルを試す方法の概要

1. PFX ファイルを準備します。
1. USB-C ケーブルを使用してデバイスにファイルをコピーします。
1. アプリを設定し、証明書マネージャーに移動[して](certificate-manager.md)証明書を適用します。

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>詳細な診断レポートは、設定で表示HoloLens

動作のトラブルシューティング時にマネージド デバイスに対して、想定されるポリシー構成が適用されるのを確認することが重要な手順です。 以前は、この新機能では、この情報を MDM 経由で、または **設定** アカウント アクセスの仕事または学校を介して収集された MDM 診断ログをエクスポートした後、デバイスの近くでデバイスからこの情報を表示し、管理ログをエクスポートし、近くの  ->    >  PCで表示するを選択する必要がありました。

これで、Edge ブラウザーを使用してデバイスで MDM 診断を表示できます。 MDM 診断レポートを簡単に表示するには、[Access work or school]/(学校または学校へのアクセス)ページに移動し、[高度な診断レポートの表示 **] を選択します**。 これにより、新しい Edge ウィンドウでレポートが生成され、開きます。

![アプリで高度な診断レポート設定表示します。](./images/view-advanced-diagnostic-report.jpg)

#### <a name="overview-to-try-out-the-advanced-diagnostic-report"></a>高度な診断レポートを試す概要

1. [設定] アプリを開きます。
1. [アカウント] ページに移動し、新しいリンク [ **管理ログのエクスポート] をクリックします**。
1. デバイスの構成に関する詳細な情報を表示します。

### <a name="offline-diagnostics-notifications"></a>オフライン診断通知

これは、オフライン診断 と呼ばれる既存の機能 [の更新プログラムです](hololens-diagnostic-logs.md#offline-diagnostics)。 以前は、診断収集をトリガーした、または完了したユーザーに対する明確なインジケーターは見ていました。
Insider ビルドWindowsに追加されました。オフライン診断には、2 つの形式の視聴覚フィードバックがあります。 1 つ目は、コレクションの開始と完了の両方に対して表示されるトースト通知です。 これらは、ユーザーがログインし、ビジュアルを持つ場合に表示されます。

![ログを収集するトースト。](./images/logcollection1.jpg)

![ログ収集が完了したらトーストします。](./images/logcollection2.jpg)

ユーザーは、ディスプレイにアクセスできない場合、ログインできない、または OOBE にまだ存在する場合のフォールバック ログ収集メカニズムとしてオフライン診断を使用する場合が多いので、ログを収集するときにオーディオ キューも再生されます。 このサウンドは、トースト通知に加えて再生されます。

この新機能は、デバイスが更新された場合に有効になります。有効または管理する必要はない。 この新しいフィードバックを表示または確認できない場合でも、オフライン診断は生成されます。

この新しいオーディオビジュアル フィードバックの追加により、診断データの収集が容易になり、問題をより迅速にトラブルシューティングできると期待しています。

#### <a name="overview-to-try-out-the-diagnostics-notifications"></a>診断通知を試す概要

1. デバイスのロックを解除し、それを装着します。
1. [電源]**ボタンと [****ボリューム] ボタンの組み合わせを** 押して、[オフライン診断を収集します](hololens-diagnostic-logs.md#offline-diagnostics)。
1. トースト通知を表示し、デバイスが起動してログの収集が完了した場合のオーディオ キューを聞きます。

### <a name="low-storage-log-collection-improvements"></a>低ストレージ ログ収集の機能強化

診断ログの収集時にデバイスのディスク領域が少なそうなシナリオでは、StorageDiagnostics.zipという **名前の追加レポート** が作成されます。 記憶域が少ない場合のしきい値は、記憶域のWindows[によって自動的に決定されます](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)。

#### <a name="overview-to-try-out-the-low-storage-improvements"></a>記憶域の低レベルの機能強化を試す方法の概要

1. デバイスの記憶域スペースを埋める。
1. [電源]**ボタンと [****ボリューム] ボタンの組み合わせを** 押して、[オフライン診断を収集します](hololens-diagnostic-logs.md#offline-diagnostics)。
1. ファイルの Documents フォルダーに格納されているログのコレクションに新しいファイルHoloLens。

### <a name="csp-changes-for-reporting-hololens-details"></a>レポートの詳細に関する CSP HoloLens変更

- Insider ビルドWindowsで導入、20348.1403

次の PS は、デバイスから情報を報告する新しい方法でHoloLensされました。

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP - 無料Storage

DevDetail CSP では、デバイス上の空きストレージ領域HoloLensされます。 これは、アプリの [アプリ] ページに表示設定値とStorage一致する必要があります。 この情報を含む特定のノードを次に示します。

- ./DevDetail/Ext/Microsoft/FreeStorage (GET 操作のみ)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP - SSID と BSSID

DeviceStatus CSP では、アクティブに接続されているネットワークWi-Fi SSID と BSSID HoloLens報告する機能も追加されています。 この情報を含む特定のノードを次に示します。

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/ mac アドレス *(Wi-Fi*/SSID)
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

この新しい AutoLogonUser ポリシーは、ユーザーが自動的にログオンするかどうかを制御します。 一部のお客様は、ID に関連付けられてもサインイン エクスペリエンスを望んでいないデバイスを設定したいと考えています。 Imagineを選択し、すぐにリモート 支援を使用する必要があります。 または、デバイスを迅速に配布し、エンド HoloLensを迅速にログインできるという利点があります。

ポリシーが空でない値に設定されている場合は、自動ログオン ユーザーの電子メール アドレスを指定します。 自動ログオンを有効にするには、指定したユーザーがデバイスに少なくとも 1 回ログオンする必要があります。

新しいポリシー文字列値の OMA-URI `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`

- 同じ電子メール アドレスを持つユーザーは、自動ログオンを有効にします。

このポリシーが構成されているデバイスでは、ポリシーで指定されたユーザーが少なくとも 1 回ログオンする必要があります。 最初のログオン後にデバイスを再起動すると、指定したユーザーが自動的にログオンします。 1 人の自動ログオン ユーザーだけがサポートされます。 有効にすると、自動的にログオンしたユーザーは手動でログアウトできません。 別のユーザーとしてログオンするには、まずポリシーを無効にする必要があります。

> [!NOTE]
>
> - OS のメジャー更新などの一部のイベントでは、自動ログオンの動作を再開するために、指定されたユーザーがデバイスに再度ログオンする必要がある場合があります。
> - 自動ログオンは、MSA ユーザーと AAD ユーザーに対してのみサポートされます。

#### <a name="overview-to-try-auto-logon-csp"></a>CSP の自動ログオンを試す方法の概要

1. カスタム ポリシーを使用して、目的のユーザーに新しい CSP [を構成します](/mem/intune/configuration/custom-settings-windows-10) 。 `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`
1. プロビジョニング パッケージまたは MDM を使用して、CSP[をデバイスに](hololens-provisioning.md)[適用します](hololens-mdm-configure.md)。
1. 指定したアカウントにサインインします。
1. デバイスを再起動し、ユーザーが自動的にログインしているのを確認します。

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

#### <a name="overview-to-try-new-update-notifications"></a>新しい更新通知を試す概要

1. プロビジョニング パッケージまたは MDM を使用して[](hololens-provisioning.md)、新しい更新[CSP](hololens-mdm-configure.md)のいずれかを構成します (上記のリンクリストを参照して選択してください)。
1. スケジュールされた時間にデバイスを使用します。
1. 更新プログラムについてユーザーに通知され、デバイスを再起動する必要がある場合を確認します \* 。

\* 結果は、使用される更新ポリシーによって異なる場合があります。

### <a name="smart-retry-for-app-updates"></a>アプリ更新プログラムのスマート再試行

HoloLens に対して有効になるのは、IT 管理者が定期的または 1 回の日付を設定して、アプリの使用が原因で更新が失敗したアプリを再起動し、更新プログラムの適用を許可する新しいポリシーです。 これらは、スケジュールされた時刻やサインインなど、いくつかの異なるトリガーに基づいて設定できます。 このポリシーの使用方法の詳細については [、「ApplicationManagement/ScheduleForceRestartForUpdateFailures 」を参照してください](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)。

#### <a name="overview-to-try-smart-retry-for-app-updates"></a>アプリの更新プログラムのスマート再試行を試す方法の概要

1. 新しいスマート再試行機能を構成します。
1. アプリをまだ受信していないデバイスで、正しく構成されている場合は、オンライン環境でログインします。
1. デバイスをオフにしたり切断したりして、デバイスがアプリをダウンロードできない。
1. トリガーされた時間中にデバイスの電源をオンにし、インターネットに接続してダウンロードを再試行します。

### <a name="use-only-private-store-apps-for-microsoft-store"></a>プライベート ストア アプリのみを使用してMicrosoft Store

RequirePrivateStoreOnly ポリシーが有効になっているHoloLens。 このポリシーを使用するとMicrosoft Storeを使用して、組織用に構成されたプライベート ストアのみを表示するようにアプリを構成[ビジネス向け Microsoft Store。](/microsoft-store/microsoft-store-for-business-overview) 使用可能にしたアプリにのみアクセスを制限する。

[ApplicationManagement/RequirePrivateStoreOnly の詳細を確認してください](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)。

#### <a name="overview-to-try-only-private-store-apps"></a>プライベート ストア アプリのみを試す方法の概要

1. MDM を使用してデバイスの新しいポリシーを [構成します](hololens-mdm-configure.md)。
1. ポリシーを持つデバイスにログインします。
1. アプリをMicrosoft Store開き、組織のアプリしか表示されていないことを確認します。

### <a name="use-wdac-and-lob-apps"></a>WDAC アプリと LOB アプリを使用する

WDAC を使用して、アプリやプロセスの起動をブロックし、独自の bushiness アプリを引き続き使用できるようになりました。 これで、WDAC ポリシーで許可できるようになりました。 このポリシーを使用するには、WDAC ポリシーを作成するときに、PowerShell で余分なコード行を実行する必要があります。 [こちらの手順を確認して](/mem/intune/configuration/custom-profile-hololens)ください。

#### <a name="overview-to-try-your-own-apps-while-using-wdac-to-block-others"></a>他のユーザーをブロックするために、WDAC を使用して独自のアプリを試すための概要

1. LOB アプリとブロックするアプリの AUMIDs を収集します。
1. 新しい手順に従って、[新しい WDAC ポリシーを作成](/mem/intune/configuration/custom-profile-hololens)します。
1. [MDM を使用して](hololens-mdm-configure.md) デバイスにポリシーを展開します。
1. デバイスにサインインし、アプリを起動して他のユーザーをブロックできることを確認します。

### <a name="fixes-and-improvements"></a>修正プログラムと機能強化

- [ロックされたファイルをダウンロードするプロンプトがないデバイスポータルの既知の問題](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)を修正しました。
- [ファイルのアップロードとダウンロードのタイムアウトを含むデバイスポータルの既知の問題](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)を修正した。
- HoloLens デバイスからのコンプライアンスプロパティのレポートに関する問題に対処します。Insider ビルドで適切なレポートをトリガーするには、再起動が必要になることがあります。  
- [割り当てられたアクセス API](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true)を有効にし、アプリが HoloLens にログインしているユーザーに対してキオスクモードで実行されている HoloLens かどうかを確認できるようになりました。
- 新しい点滅にインストールされているリモートアシスタンスのインボックスバージョンが更新されました。
- 内部版のビルドでは、2D アプリのゲームパッド処理が無効になりました。 これを削除することで、アプリはゲームパッド Api を直接使用できるようになり、コントロールのセット全体にアクセスし、必要な操作を実行できるようになりました。 開発者がゲームパッドの入力を使用するには、ゲームパッド Api を使用する必要があります。 ゲームパッドクラスのサンプル (Windows を次に示し[ます。ゲームの入力)-UWP アプリケーションを Windows](/uwp/api/windows.gaming.input.gamepad?view=winrt-20348&preserve-view=true)します。
- 最初のユーザーのサインイン後に、AAD グループベースのキオスク構成が使用されていたシナリオで OOBE が終了された問題を修正しました。
- デバイスを再起動するための更新通知とダイアログプロンプトの表示に関する問題を修正しました。

## <a name="start-receiving-insider-builds"></a>Insider ビルドの受信を開始します

> [!NOTE]
> 最近更新したことがない場合は、デバイスを再起動して状態を更新し、最新のビルドを取得してください。
>
> - "デバイスの再起動" 音声コマンドは正常に機能します。
> - 設定/Windows Insider プログラムで [再起動] ボタンを選択することもできます。
>
> バックエンドには、発生した可能性があるバグがあり、これによって追跡が再開されます。

HoloLens 2 デバイスで、[   >  **セキュリティ**  >  **Windows Insider program** & 設定更新] をクリックし、[**開始**] を選択します。 Windows Insider として登録するために使用したアカウントをリンクします。

> [!NOTE]
> Insider ビルドにデバイスを登録するには、オプションのテレメトリを有効にする必要があります。 まだ行っていない場合は、設定アプリを開き、[**プライバシー**  ->  **診断 & フィードバック**] を選択し、[**オプションの診断データ**] を選択します。

Windows insider がチャネルに移行しています。 **高速** リングが **開発チャネル** になり、**低速** リングが **ベータチャネル** になり、 **release preview** リングが **release preview チャネル** になります。 マッピングは次のようになります。

![Windows内部のチャネルの説明。](images/WindowsInsiderChannels.png)

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
