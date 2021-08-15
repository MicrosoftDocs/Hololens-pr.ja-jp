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
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: df0cb555c8445ef4d8f8165996a33e0f8c1a38653b45514594f893e3c761f65a
ms.sourcegitcommit: 9615ed824bdf3f1747ec346da6136704d8eed015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2021
ms.locfileid: "120364287"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens の Insider Preview

HoloLens のための最新の Insider Preview ビルドへようこそ。 この機能は簡単に[開始](hololens-insider.md#start-receiving-insider-builds)でき、次の主要なオペレーティングシステムの更新プログラムについての重要なフィードバックを提供します HoloLens。

## <a name="windows-insider-release-notes"></a>WindowsInsider のリリースノート

ここでは、新しい機能を開始して、insider を Windows します。 新しいビルドは、最新の更新プログラムの開発およびベータチャネルに対して実行されます。 Windows Insider ビルドに機能と更新プログラムを追加すると、このページは引き続き更新されます。 これらの更新プログラムを実際のものに混在させることができます。

| 特徴量                 | 説明                | ユーザーまたはシナリオ | 導入されたビルド |
|-------------------------|----------------------------|--------------|------------------|
| [レポート HoloLens の詳細の CSP の変更](#csp-changes-for-reporting-hololens-details) | データを照会するための新しい Csp | IT 管理者    | 20348.1403                 |
| [CSP によって制御される自動ログインポリシー](#auto-login-policy-controlled-by-csp) | アカウントを自動的にログインするために使用されます | IT 管理者 | 20348.1405 |
| [証明書マネージャーの PFX ファイルのサポート](#pfx-file-support-for-certificate-manager) | 設定 UI を使用した PFX 証明書の追加 | エンド ユーザー | 20348.1405 |
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
> - 主要な OS の更新などの一部のイベントでは、指定されたユーザーがデバイスにもう一度ログオンして、自動ログオンの動作を再開することが必要になる場合があります。 
> - 自動ログオンは、MSA および AAD ユーザーに対してのみサポートされています。

### <a name="pfx-file-support-for-certificate-manager"></a>証明書マネージャーの PFX ファイルのサポート

Windows Insider build 20348.1405 で導入されました。 .Pfx 証明書を使用するように、 [証明書マネージャー](certificate-manager.md) にサポートを追加しました。 ユーザーが  >  **& セキュリティ**  >  **証明書** を更新設定に移動し、[**証明書のインストール**] を選択すると、UI で .pfx 証明書ファイルがサポートされるようになりました。
ユーザーは、秘密キーを持つ .pfx 証明書をユーザーストアまたはコンピューターストアにインポートできます。

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>HoloLens の設定で詳細な診断レポートを表示する

管理対象デバイスでの動作のトラブルシューティングでは、必要なポリシー構成が適用されていることを確認することが重要な手順です。 これまでの新機能では、**設定** アカウントによって収集された mdm 診断ログをエクスポートした後、mdm またはデバイスの近くでデバイスを使用する必要がありました。これには、  ->    >  **職場または学校へのアクセス権** があります。また、**管理ログをエクスポート** し、近くの PC に表示します。

これで、Edge ブラウザーを使用してデバイスで MDM 診断を表示できるようになりました。 MDM 診断レポートをより簡単に表示するには、[職場または学校へのアクセス] ページに移動し、[ **詳細な診断レポートの表示**] を選択します。 これにより、レポートが生成され、新しいエッジウィンドウで開きます。

![設定アプリで詳細な診断レポートを表示します。](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>オフライン診断の通知

これは、 [オフライン診断](hololens-diagnostic-logs.md#offline-diagnostics)と呼ばれる既存の機能の更新プログラムです。 以前は、診断コレクションがトリガーされたか、または完了したことをユーザーに明確に示すインジケーターがありませんでした。
Windows Insider ビルドに追加された、オフライン診断に対するオーディオビジュアルフィードバックには、2つの形式があります。 コレクションの開始時と完了時の両方について、最初に表示されるトースト通知が表示されます。 これらは、ユーザーがログインし、視覚エフェクトを持っているときに表示されます。

![ログを収集するためのトースト。](./images/logcollection1.jpg)

![ログの収集が完了したときのトースト。](./images/logcollection2.jpg)
 
多くの場合、ユーザーがディスプレイにアクセスできない場合にはフォールバックログ収集メカニズムとしてオフライン診断を使用しますが、ログインができない場合や、まだ OOBE にある場合は、ログが収集されるときにオーディオキューも再生されます。 このサウンドは、トースト通知に加えて再生されます。

この新機能は、デバイスの更新時に有効になり、有効にしたり管理したりする必要はありません。 この新しいフィードバックを表示したり聞いたりできない場合でも、オフライン診断は引き続き生成されます。

この新しいオーディオビジュアルフィードバックの追加により、診断データを簡単に収集し、問題のトラブルシューティングをより簡単に行うことができます。

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Microsoft Store の専用ストアアプリのみを使用する

RequirePrivateStoreOnly ポリシーは HoloLens に対して有効になっています。 このポリシーを使用すると、組織用に構成されたプライベートストアのみを表示するように Microsoft Store アプリを構成できます。 使用できるようにしたアプリのみにアクセスを制限する。

[Applicationmanagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)の詳細情報

### <a name="low-storage-log-collection-improvements"></a>低ストレージログ収集の機能強化

診断ログを収集するときにデバイスのディスク領域が不足していると思われる場合は、 **StorageDiagnostics.zip** という名前の追加のレポートが作成されます。 低ストレージのしきい値は、Windows ストレージの[意味](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)で自動的に決定されます。

### <a name="moving-platform-mode"></a>プラットフォームモードの移動

**Insider build 20348.1411** の段階では、HoloLens 2 での動的な動き移動プラットフォームを追跡するためのベータサポートを追加しました。 ビルドをインストールし、プラットフォームの移動モードを有効にすると、大規模な船舶や大海船舶など、以前にアクセスできなかった環境で HoloLens 2 を使用できるようになります。 現時点では、この機能は、これらの特定の移動プラットフォームのみを有効にすることを目的としています。 他の環境でこの機能を使用することはできませんが、この機能は最初にこれらの環境のサポートを追加することに重点を置いています。

サポートされている機能と、この新機能を有効にする方法の詳細については、「[プラットフォームの移行」ページを参照](hololens2-moving-platform.md)してください。

### <a name="fixes-and-improvements"></a>修正プログラムと機能強化

- [ロックされたファイルをダウンロードするプロンプトがないデバイスポータルの既知の問題を修正しました。](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- [ファイルのアップロードとダウンロードのタイムアウトを含むデバイスポータルの既知の問題](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)を修正した。
- HoloLens デバイスからのコンプライアンスプロパティのレポートに関する問題に対処します。Insider ビルドで適切なレポートをトリガーするには、再起動が必要になることがあります。  
- [割り当てられたアクセス API](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348)を有効にし、アプリが HoloLens にログインしているユーザーに対してキオスクモードで実行されている HoloLens かどうかを確認できるようになりました。
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
