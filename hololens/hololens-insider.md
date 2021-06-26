---
title: Microsoft HoloLens の Insider Preview
description: 次の主要なオペレーティングシステム更新プログラム (HoloLens) について、Insider ビルドの使用を開始し、貴重なフィードバックを提供する方法について説明します。
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
ms.openlocfilehash: a4949ab68121cb772fdb8a62411ed70868a6ccb6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924368"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens の Insider Preview

HoloLens 用の最新の Insider Preview ビルドへようこそ。 この機能は簡単に [開始](hololens-insider.md#start-receiving-insider-builds) でき、HoloLens の次の主なオペレーティングシステムの更新に関する貴重なフィードバックを提供します。

## <a name="windows-insider-release-notes"></a>Windows Insider リリースノート

Windows Insider の新機能を再び開始します。 新しいビルドは、最新の更新プログラムの開発およびベータチャネルに対して実行されます。 Windows Insider ビルドに機能と更新プログラムを追加すると、このページは引き続き更新されます。 これらの更新プログラムを実際のものに混在させることができます。 

### <a name="csp-changes-on-hololens"></a>HoloLens での CSP の変更
 
- Windows Insider build 20348.1403 で導入されました

#### <a name="devdetail-csp"></a>DevDetail CSP

DevDetail CSP は、HoloLens デバイスの空き記憶領域も報告するようになりました。 これは、[設定] [アプリのストレージ] ページに表示される値とほぼ一致している必要があります。 この情報を含む特定のノードを次に示します。

- ./DevDetail/Ext/Microsoft/FreeStorage (GET 操作のみ)

#### <a name="devicestatus-csp"></a>DeviceStatus CSP

DeviceStatus CSP は、HoloLens がアクティブに接続されている、Wifi ネットワークの SSID と BSSID も報告するようになりました。 この情報を含む特定のノードを次に示します。

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

### <a name="fixes-and-improvements"></a>修正と改善:

- [ロックされたファイルをダウンロードするプロンプトがないデバイスポータルの既知の問題を修正しました。](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- [ファイルのアップロードとダウンロードのタイムアウトを含むデバイスポータルの既知の問題](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)を修正した。

## <a name="start-receiving-insider-builds"></a>Insider ビルドの受信を開始します
> [!NOTE]
> 最近更新したことがない場合は、デバイスを再起動して状態を更新し、最新のビルドを取得してください。
> - "デバイスの再起動" 音声コマンドは正常に機能します。 
> - [設定]/[Windows Insider Program] で [再起動] ボタンを選択することもできます。
>
> バックエンドには、発生した可能性があるバグがあり、これによって追跡が再開されます。

HoloLens 2 デバイスで、[**設定**  >  ] [**更新 & セキュリティ**] [  >  **Windows Insider program** ] に移動し、[**開始**] を選択します。 Windows Insider として登録するために使用したアカウントをリンクします。
Windows insider がチャネルに移動するようになりました。 **高速** リングが **開発チャネル** になり、**低速** リングが **ベータチャネル** になり、 **release preview** リングが **release preview チャネル** になります。 マッピングは次のようになります。 ![ Windows insider channel の説明 ](images/WindowsInsiderChannels.png) 詳細については、windows ブログの「windows insider Channel の [概要](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 」を参照してください。
次に、[ **Windows のアクティブな開発**] を選択し、 **開発チャネル** または **ベータチャネル** のビルドを受信するかどうかを選択して、プログラムの条件を確認します。
[ **Confirm > Restart Now** ] を選択して終了します。 デバイスが再起動したら、[設定] [& のセキュリティ > 更新プログラムをチェックし、最新のビルドを取得するため **の更新プログラムを確認 >** ます。
### <a name="update-error-0x80070490-work-around"></a>Update エラー0x80070490 の回避策
Dev または Beta チャネルで更新するときに更新エラー0x80070490 が発生した場合は、次の短期的な対処を試してください。 これには、insider チャネルを移動し、更新を選択して、Insider channel を戻す必要があります。
#### <a name="stage-one---release-preview"></a>ステージワンリリースプレビュー
1.  [設定]、[更新プログラム & セキュリティ]、[Windows Insider Program] を選択し、[ **Release Preview Channel**] を選択します。
2.  設定、更新 & セキュリティ、Windows Update、 **更新を確認** します。 更新後、段階2に進みます。
#### <a name="stage-two---dev-channel"></a>ステージ2開発チャネル
1. [設定]、[更新プログラム & セキュリティ]、[Windows Insider Program] の [ **開発チャネル**] を選択します。
2. 設定、更新 & セキュリティ、Windows Update、 **更新を確認** します。
## <a name="ffu-download-and-flash-directions"></a>FFU のダウンロードとフラッシュの方向
フライト署名済み ffu を使用してテストするには、フライト署名済み ffu を点滅させる前にデバイスのロックを解除する必要があります。
1. PC の場合:
    1. から PC に ffu をダウンロード [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) します。
    
    1. Microsoft Store から ARC (Advanced Recovery コンパニオン) をインストール [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) します。
    
1. HoloLens-フライトのロック解除: [**設定** の  >  **更新] & セキュリティ**]  >  [**Windows Insider program** ] の順に選択し、サインアップして、デバイスを再起動します。
1. Flash FFU-atc を使用して、デジタル署名された FFU をフラッシュできるようになりました。
### <a name="provide-feedback-and-report-issues"></a>フィードバックの提供と問題の報告
HoloLens で [フィードバックハブアプリ](hololens-feedback.md) を使用して、フィードバックを提供し、問題を報告してください。 フィードバックハブを使用すると、エンジニアが迅速に問題をデバッグして解決できるように、必要な診断情報がすべて含まれるようになります。  HoloLens の中国語と日本語バージョンの問題は、同じように報告する必要があります。
> [!NOTE]
> フィードバックハブがドキュメントフォルダーにアクセスするかどうかを確認するメッセージが表示されることを確認します (メッセージが表示されたら [ **はい]** を選択します)。
## <a name="note-for-developers"></a>開発者向けのメモ
HoloLens の Insider ビルドを使用してアプリケーションを開発することをお勧めします。  ご利用を開始するには、 [HoloLens 開発者ドキュメント](https://developer.microsoft.com/windows/mixed-reality/development) を参照してください。 これらの命令は、HoloLens の Insider ビルドでも機能します。  既に HoloLens 開発に使用している Unity と Visual Studio の同じビルドを使用できます。
## <a name="stop-receiving-insider-builds"></a>Insider ビルドの受信を停止します
Windows Holographic の Insider ビルドを受信する必要がなくなった場合は、HoloLens が運用ビルドを実行しているときにオプトアウトできます。または、Advanced Recovery コンパニオンを使用してデバイスを [回復](hololens-recovery.md) し、デバイスを Insider バージョン以外の windows Holographic に回復することもできます。
> [!CAUTION]
> 新しいプレビュービルドを手動で再インストールした後に、Insider Preview ビルドから登録を解除したユーザーがブルースクリーンを使用するという既知の問題があります。 その後、デバイスを手動で回復する必要があります。 影響を受けるかどうかに関する詳細については、この既知の [問題](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)を参照してください。
HoloLens で運用ビルドが実行されていることを確認するには、次のようにします。
1. [設定] にアクセスし、[ **バージョン情報] を > >**、ビルド番号を見つけます。
1. [実稼働ビルド番号については、リリースノートを参照してください](hololens-release-notes.md)。
Insider ビルドをオプトアウトするには、次のようにします。
1. 実稼働ビルドを実行する HoloLens で、[ **設定] [& セキュリティ > Windows Insider program に更新 >**、[ **Insider ビルドの停止**] を選択します。
1. 指示に従ってデバイスをオプトアウトします。
