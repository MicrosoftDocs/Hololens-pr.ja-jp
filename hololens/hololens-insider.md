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
ms.openlocfilehash: 87b606e634d4035da02802ddd1a8e1a980f1f1d6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636095"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens の Insider Preview

HoloLens のための最新の Insider Preview ビルドへようこそ。 この機能は簡単に[開始](hololens-insider.md#start-receiving-insider-builds)でき、次の主要なオペレーティングシステムの更新プログラムについての重要なフィードバックを提供します HoloLens。

## <a name="windows-insider-release-notes"></a>WindowsInsider のリリースノート

ここでは、新しい機能を開始して、insider を Windows します。 新しいビルドは、最新の更新プログラムの開発およびベータチャネルに対して実行されます。 Windows Insider ビルドに機能と更新プログラムを追加すると、このページは引き続き更新されます。 これらの更新プログラムを実際のものに混在させることができます。

| 機能                 | 説明                | ユーザーまたはシナリオ | 導入されたビルド |
|-------------------------|----------------------------|--------------|------------------|
| [レポート HoloLens の詳細の CSP の変更](#csp-changes-for-reporting-hololens-details) | データを照会するための新しい Csp | IT 管理者    | 20348.1403                 |
| [CSP によって制御される自動ログインポリシー](#auto-login-policy-controlled-by-csp) | アカウントを自動的にログインするために使用されます | IT 管理者 | 20348.1405 |
| [証明書マネージャーの PFX ファイルのサポート](#pfx-file-support-for-certificate-manager) | 設定 UI を使用した PFX 証明書の追加 | エンド ユーザー | 20348.1405 |
| [HoloLens の設定で詳細な診断レポートを表示する](#view-advanced-diagnostic-report-in-settings-on-hololens) | デバイスで MDM 診断ログを表示する | トラブルシューティング | 20348.1405 |
| [オフライン診断の通知](#offline-diagnostics-notifications) | ログ収集に関する audiovisual フィードバック | トラブルシューティング | 20348.1405 |


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



### <a name="fixes-and-improvements"></a>修正と改善:

- [ロックされたファイルをダウンロードするプロンプトがないデバイスポータルの既知の問題を修正しました。](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- [ファイルのアップロードとダウンロードのタイムアウトを含むデバイスポータルの既知の問題](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)を修正した。


## <a name="start-receiving-insider-builds"></a>Insider ビルドの受信を開始します

> [!NOTE]
> 最近更新したことがない場合は、デバイスを再起動して状態を更新し、最新のビルドを取得してください。
> - "デバイスの再起動" 音声コマンドは正常に機能します。 
> - 設定/Windows Insider プログラムで [再起動] ボタンを選択することもできます。
>
> バックエンドには、発生した可能性があるバグがあり、これによって追跡が再開されます。

HoloLens 2 デバイスで、[   >  **セキュリティ**  >  **Windows Insider program** & 設定更新] をクリックし、[**開始**] を選択します。 Windows Insider として登録するために使用したアカウントをリンクします。

Windows insider がチャネルに移行しています。 高速 **リング** は開発チャネルになり、低速リングはベータ チャネル になり、リリース プレビュー リングはリリースプレビュー チャネル **になります**。 マッピングは次のように表示されます。

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
