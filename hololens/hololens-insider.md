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
ms.openlocfilehash: b7e5a7cbaa746f58fe0344dd8bf5b027e2e8cea7
ms.sourcegitcommit: dc5d6f3802c997749775be04de522af8cb6d0850
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2021
ms.locfileid: "114693716"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens の Insider Preview

最新の Insider Preview ビルドへようこそ HoloLens! 使用を開始し、[次の](hololens-insider.md#start-receiving-insider-builds)主要なオペレーティング システム更新プログラムに関する貴重なフィードバックを提供HoloLens。

## <a name="windows-insider-release-notes"></a>WindowsInsider リリース ノート

新しい機能のフライトを開始して、Insiders Windows開始します。 新しいビルドは、最新の更新プログラムのために Dev および Beta チャネルにフライトします。 このページは引き続き更新されます。Insider ビルドの機能と更新プログラムWindows追加します。 これらの更新プログラムを実際に組み合わせ、準備を整えます。

| 特徴量                 | 説明                | ユーザーまたはシナリオ | 導入されたビルド |
|-------------------------|----------------------------|--------------|------------------|
| [レポートと詳細に関する CSP HoloLens変更](#csp-changes-for-reporting-hololens-details) | データに対してクエリを実行するの新しい CSP | IT 管理者    | 20348.1403                 |
| [CSP によって制御される自動ログイン ポリシー](#auto-login-policy-controlled-by-csp) | アカウントを自動的にログインするために使用されます | IT 管理者 | 20348.1405 |
| [証明書マネージャーの PFX ファイルのサポート](#pfx-file-support-for-certificate-manager) | UI を使用して PFX 証明書設定する | エンド ユーザー | 20348.1405 |
| [詳細な診断レポートは、設定で表示HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | デバイスで MDM 診断ログを表示する | トラブルシューティング | 20348.1405 |
| [オフライン診断通知](#offline-diagnostics-notifications) | ログ収集に関する視聴覚フィードバック | トラブルシューティング | 20348.1405 |
| [プライベート ストア アプリのみをプライベート ストア アプリにMicrosoft Store](#use-only-private-store-apps-for-microsoft-store) | 組織のアプリのみを表示するストア アプリを構成する | IT 管理者 | 20348.1408 |
| [修正と機能強化](hololens-insider.md#fixes-and-improvements) | 更新プログラムの修正とHoloLens。 | All | 20348.1408 |

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

RequirePrivateStoreOnly ポリシーが有効になっているHoloLens。 このポリシーにより、組織Microsoft Storeプライベート ストアのみを表示するようにアプリを構成できます。 使用できるようにしたアプリのみにアクセスを制限する。

[Applicationmanagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)の詳細情報

### <a name="fixes-and-improvements"></a>修正と改善:

- [ロックされたファイルをダウンロードするプロンプトがないデバイスポータルの既知の問題を修正しました。](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- [ファイルのアップロードとダウンロードのタイムアウトを含むデバイスポータルの既知の問題](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)を修正した。
- HoloLens デバイスからのコンプライアンスプロパティのレポートに関する問題に対処します。Insider ビルドで適切なレポートをトリガーするには、再起動が必要になることがあります。  
- 新しい点滅にインストールされているリモートアシスタンスのインボックスバージョンが更新されました。


## <a name="start-receiving-insider-builds"></a>Insider ビルドの受信を開始します

> [!NOTE]
> 最近更新したことがない場合は、デバイスを再起動して状態を更新し、最新のビルドを取得してください。
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

Dev または Beta チャネルで更新するときに更新エラー0x80070490 が発生した場合は、次の短期的な対処を試してください。 これには、insider チャネルを移動し、更新を選択して、Insider channel を戻す必要があります。

#### <a name="stage-one---release-preview"></a>ステージワンリリースプレビュー

1.  設定]、[Update & Security]、[Windows Insider program] を選択し、[ **Release Preview Channel**] を選択します。

2.  設定、更新プログラム & セキュリティ、Windows Update、**更新プログラムを確認** します。 更新後、段階2に進みます。

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
