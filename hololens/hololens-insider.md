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
ms.openlocfilehash: de5b8f052cfdd176f5b883661b2339764fd8ec24113e06b1286d9406acf3790f
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664061"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens の Insider Preview

最新の Insider Preview ビルドへようこそ HoloLens! 使用を開始し、[次の](hololens-insider.md#start-receiving-insider-builds)主要なオペレーティング システム更新プログラムに関する貴重なフィードバックを提供HoloLens。

## <a name="windows-insider-release-notes"></a>WindowsInsider リリース ノート

新しい機能のフライトを開始して、Insiders Windows開始します。 新しいビルドは、最新の更新プログラムのために Dev および Beta チャネルにフライトします。 このページは引き続き更新されます。Insider ビルドの機能と更新プログラムWindows追加します。 これらの更新プログラムを実際に組み合わせ、準備を整えます。

| 機能                 | Description                | ユーザーまたはシナリオ | 導入されたビルド |
|-------------------------|----------------------------|--------------|------------------|
| [レポートと詳細に関する CSP HoloLens変更](#csp-changes-for-reporting-hololens-details) | データに対してクエリを実行するの新しい CSP | IT 管理者    | 20348.1403                 |
| [CSP によって制御される自動ログイン ポリシー](#auto-login-policy-controlled-by-csp) | アカウントを自動的にログインするために使用されます | IT 管理者 | 20348.1405 |
| [証明書マネージャーの PFX ファイルのサポート](#pfx-file-support-for-certificate-manager) | UI を使用して PFX 証明書設定する | エンド ユーザー | 20348.1405 |
| [詳細な診断レポートは、設定で表示HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | デバイスで MDM 診断ログを表示する | トラブルシューティング | 20348.1405 |
| [オフライン診断通知](#offline-diagnostics-notifications) | ログ収集に関する視聴覚フィードバック | トラブルシューティング | 20348.1405 |
| [プライベート ストア アプリのみをプライベート ストア アプリにMicrosoft Store](#use-only-private-store-apps-for-microsoft-store) | 組織のアプリのみを表示するストア アプリを構成する | IT 管理者 | 20348.1408 |
| [低ストレージ ログ収集の機能強化](#low-storage-log-collection-improvements) | ストレージが少ない状況でのログ収集シナリオの改善。 | IT 管理者 | 20348.1412 |
| [修正と機能強化](hololens-insider.md#fixes-and-improvements) | 更新プログラムの修正とHoloLens。 | すべて | 20348.1411 |

### <a name="csp-changes-for-reporting-hololens-details"></a>レポートと詳細に関する CSP HoloLens変更

- Insider ビルドWindows 20348.1403 で導入

次の PS は、デバイスから情報を報告する新しい方法でHoloLensされました。

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP - 無料Storage

DevDetail CSP では、デバイス上の空きストレージ領域HoloLensされます。 これは、アプリの [アプリ] ページに表示設定値とStorage一致する必要があります。 この情報を含む特定のノードを次に示します。

- ./DevDetail/Ext/Microsoft/FreeStorage (GET 操作のみ)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP - SSID と BSSID

DeviceStatus CSP では、アクティブに接続されているネットワークWi-Fi SSID と BSSID HoloLens報告されます。 この情報を含む特定のノードを次に示します。

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

この新しい AutoLogonUser ポリシーは、ユーザーが自動的にログオンするかどうかを制御します。 一部のお客様は、ID に関連付けられてもサインイン エクスペリエンスを望んでいないデバイスを設定したいと考えています。 Imagineを選択し、すぐにリモート 支援を使用する必要があります。 または、デバイスを迅速に配布しHoloLensエンド ユーザーがログインを迅速に行えるという利点があります。

ポリシーが空でない値に設定されている場合は、自動ログオン ユーザーの電子メール アドレスを指定します。 自動ログオンを有効にするには、指定したユーザーがデバイスに少なくとも 1 回ログオンする必要があります。

新しいポリシー文字列値の OMA-URI `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`

- 同じ電子メール アドレスを持つユーザーは、自動ログオンを有効にします。

このポリシーが構成されているデバイスでは、ポリシーで指定されたユーザーが少なくとも 1 回ログオンする必要があります。 最初のログオン後にデバイスを再起動すると、指定したユーザーが自動的にログオンします。 1 人の自動ログオン ユーザーだけがサポートされます。 有効にすると、自動的にログオンしたユーザーは手動でログアウトできません。 別のユーザーとしてログオンするには、まずポリシーを無効にする必要があります。

> [!NOTE]
> - OS のメジャー更新などの一部のイベントでは、自動ログオンの動作を再開するために、指定されたユーザーがデバイスに再度ログオンする必要がある場合があります。 
> - 自動ログオンは、MSA ユーザーと AAD ユーザーに対してのみサポートされます。

### <a name="pfx-file-support-for-certificate-manager"></a>証明書マネージャーの PFX ファイルのサポート

Insider ビルド 20348.1405 Windowsで導入されました。 証明書マネージャーに .pfx [証明書を](certificate-manager.md) 使用するサポートが追加されました。 ユーザーが [Update 設定 &セキュリティ証明書] に移動し、[証明書のインストール] を選択すると、UI で .pfx 証明書ファイル  >    >  がサポートされます。 
ユーザーは、ユーザー ストアまたはコンピューター ストアに、プライベート キーを使用して .pfx 証明書をインポートできます。

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>詳細な診断レポートは、設定で表示HoloLens

動作のトラブルシューティング時にマネージド デバイスに対して、想定されるポリシー構成が適用されるのを確認することが重要な手順です。 以前は、この新機能では **、設定** アカウント アクセスの仕事または学校を介して収集された MDM 診断ログをエクスポートした後、MDM またはデバイスの近くでデバイスからこれを行い、管理ログをエクスポートし、近くの  ->    >  PCで表示するを選択する必要がありました。

これで、Edge ブラウザーを使用してデバイスで MDM 診断を表示できます。 MDM 診断レポートを簡単に表示するには、[Access work or school]/(学校または学校へのアクセス)ページに移動し、[高度な診断レポートの表示 **] を選択します**。 これにより、新しい Edge ウィンドウでレポートが生成され、開きます。

![アプリで高度な診断レポート設定表示します。](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>オフライン診断通知

これは、オフライン診断 と呼ばれる既存の機能 [の更新プログラムです](hololens-diagnostic-logs.md#offline-diagnostics)。 以前は、診断収集をトリガーした、または完了したという明確なインジケーターがユーザーに表示されません。
Insider ビルドWindowsに追加されました。オフライン診断には、2 つの形式の視聴覚フィードバックがあります。 1 つ目は、コレクションの開始時と完了時の両方に表示されるトースト通知です。 これらは、ユーザーがログインし、ビジュアルを持つ場合に表示されます。

![ログを収集するトースト。](./images/logcollection1.jpg)

![ログ収集が完了したらトーストします。](./images/logcollection2.jpg)
 
ユーザーは、ディスプレイにアクセスできない、ログインできない、または OOBE にまだ存在する場合のフォールバック ログ収集メカニズムとしてオフライン診断を使用する場合が多いので、ログを収集するときにオーディオ キューも再生されます。 このサウンドは、トースト通知に加えて再生されます。

この新機能は、デバイスが更新された場合に有効になります。有効または管理する必要はない。 この新しいフィードバックを表示または確認できない場合でも、オフライン診断は生成されます。

この新しいオーディオビジュアル フィードバックの追加により、診断データの収集が容易になり、問題をより迅速にトラブルシューティングできると期待しています。

### <a name="use-only-private-store-apps-for-microsoft-store"></a>プライベート ストア アプリのみを使用してMicrosoft Store

RequirePrivateStoreOnly ポリシーが有効になっているHoloLens。 このポリシーにより、組織Microsoft Storeプライベート ストアのみを表示するようにアプリを構成できます。 使用可能にしたアプリにのみアクセスを制限する。

[ApplicationManagement/RequirePrivateStoreOnly の詳細を確認する](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="low-storage-log-collection-improvements"></a>低ストレージ ログ収集の機能強化

診断ログの収集時にデバイスのディスク領域が少なそうなシナリオでは、StorageDiagnostics.zipという名前 **の追加レポート** が作成されます。 記憶域が少ない場合のしきい値は、ストレージ のWindows[によって決まります](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)。

### <a name="fixes-and-improvements"></a>修正と機能強化

- ロックされた [ファイルをダウンロードするプロンプトデバイス ポータルが表示される場合の既知の問題を修正しました。](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- ファイルの [アップロードとダウンロードのデバイス ポータルに関する既知の問題を修正しました。](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- デバイスからのコンプライアンス プロパティの報告に関する問題HoloLens対応します。Insider ビルドで正しいレポートをトリガーするには、再起動が必要になる場合があります。  
- 新しいフラッシュにインストールRemote Assistのインボックス バージョンを更新しました。

## <a name="start-receiving-insider-builds"></a>Insider ビルドの受信を開始する

> [!NOTE]
> 最近更新していない場合は、デバイスを再起動して状態を更新し、最新のビルドを取得してください。
> - "デバイスの再起動" 音声コマンドは正常に機能します。 
> - [再起動] ボタンは、設定/Windows Insider Program。
>
> 発生した可能性があるバック エンドにバグがありました。これにより、追跡が戻されます。

デバイスで HoloLens 2 Update 設定Security & に移動Windows Insider Program  >    >  を選択 **概要。** インサイダーとして登録するために使用したアカウントをWindowsします。

Windowsインサイダーはチャネルに移行しています。 高速 **リング** は開発チャネルになり、低速リングはベータ チャネル になり、リリース プレビュー リングはリリースプレビュー チャネル **になります**。 マッピングは次のように表示されます。

![WindowsInsider Channels の説明](images/WindowsInsiderChannels.png)

詳細については、「 [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs」を参照してください。
次 **に、[** Windows のアクティブな開発 ] を選択し、開発チャネルを受け取ベータ チャネルビルドを受け取 **る** かどうかを選択し、プログラムの用語を確認します。
[Confirm **> Restart Now]を選択して** 完了します。 デバイスが再起動したら、[Update 設定 > **Security]** &に移動>更新プログラムを確認して最新のビルドを取得します。

### <a name="update-error-0x80070490-work-around"></a>更新エラー 0x80070490回避

Dev または Beta チャネルで更新0x80070490更新エラーが発生した場合は、次の短期的な回避を試してください。 インサイダー チャネルを移動し、更新プログラムを選択してから、Insider チャネルを戻す必要があります。

#### <a name="stage-one---release-preview"></a>ステージ 1 - リリース プレビュー

1.  設定セキュリティの更新&、Windows Insider Programリリース プレビュー チャネル **] を選択します**。

2.  設定セキュリティの更新&更新プログラムWindows更新プログラムの **確認」を参照してください**。 更新後、ステージ 2 に進む。

#### <a name="stage-two---dev-channel"></a>ステージ 2 - 開発チャネル

1. 設定セキュリティの更新&、Windows Insider Program Dev Channel ]**を選択します**。

2. 設定セキュリティの更新&更新プログラムWindows更新プログラムの **確認」を参照してください**。

## <a name="ffu-download-and-flash-directions"></a>FFU のダウンロードとフラッシュの方向

フライト署名済み ffu でテストするには、フライト署名済み ffu をフラッシュする前に、まずデバイスのロックを解除する必要があります。

1. PC の場合:
    1. から ffu を PC にダウンロードします [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. ARC (Advanced Recovery Companion) を次のコマンドからMicrosoft Storeします [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 。
    
1. [HoloLens - Flight Unlock: Update 設定 Security &を開Windows Insider Program  >    >  サインアップし、デバイスを再起動します。

1. Flash FFU - ARC を使用してフライト署名済み FFU をフラッシュできます。

### <a name="provide-feedback-and-report-issues"></a>フィードバックを提供し、問題を報告する

フィードバックを[提供フィードバック Hub問題を報告](hololens-feedback.md)するには、HoloLensアプリを使用してください。 このフィードバック Hubを使用すると、エンジニアが問題をすばやくデバッグして解決するのに役立つ、必要なすべての診断情報が確実に含まれます。  中国語と日本語のバージョンに関する問題HoloLens同じように報告する必要があります。

> [!NOTE]
> [ドキュメント] フォルダーにアクセスするかどうかを確認するプロンプトフィードバック Hub受け入れる必要があります (メッセージが表示されたら、[は **い]** を選択します)。

## <a name="note-for-developers"></a>開発者向けの注意

アプリケーションの Insider ビルドを使用してアプリケーションの開発を試みHoloLens。  使用を開始[するにはHoloLens開発者向けドキュメント](https://developer.microsoft.com/windows/mixed-reality/development)を参照してください。 これらの同じ手順は、アプリケーションの Insider ビルドHoloLens。  Unity のビルドと同じビルドを使用してVisual Studio開発に既に使用している同じHoloLensできます。

## <a name="stop-receiving-insider-builds"></a>Insider ビルドの受信を停止する

Windows Holographic の Insider ビルドを受け取らなくなった場合は、HoloLens が実稼働ビルドを実行している場合はオプトアウトできます。または、Advanced [](hololens-recovery.md) Recovery Companion を使用してデバイスを回復して、Insider 以外のバージョンの Windows Holographic にデバイスを回復することもできます。

> [!CAUTION]
> 新しいプレビュー ビルドを手動で再インストールした後に Insider Preview から登録を解除したユーザーがブルー スクリーンを表示する既知の問題があります。 その後、デバイスを手動で回復する必要があります。 影響を受け取る可能性がある場合の詳細については、この既知の問題に関するページを [参照してください](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)。

お使HoloLensが実稼働ビルドを実行している場合は、次の手順を実行します。

1. [System **設定 > About] >に移動** し、ビルド番号を見つける。

1. [実稼働ビルド番号については、リリース ノートを参照してください](hololens-release-notes.md)。

Insider ビルドをオプトアウトするには:

1. 実稼働ビルドHoloLens実行中のアプリで、設定 > **Update & Security**> Windows Insider Program に移動し、[Stop Insider builds]/(Insider ビルドの停止)を **選択します**。

1. 指示に従ってデバイスをオプトアウトします。
