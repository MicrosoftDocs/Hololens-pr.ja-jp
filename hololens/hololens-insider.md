---
title: Microsoft HoloLens の Insider Preview
description: Insider ビルドの使用を開始し、HoloLens の次の主要なオペレーティング システム更新プログラムに関する貴重なフィードバックを提供する方法について説明します。
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
ms.openlocfilehash: 8b8c3c26ff743a4df0010110d0fe6e2930646c86
ms.sourcegitcommit: add53aa73588986a3430cdc0310af7665a038cfc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2021
ms.locfileid: "112977238"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens の Insider Preview

HoloLens の最新の Insider Preview ビルドへようこそ。 HoloLens [の次](hololens-insider.md#start-receiving-insider-builds) の主要なオペレーティング システム更新プログラムの開始と貴重なフィードバックの提供は簡単です。

## <a name="windows-insider-release-notes"></a>Windows Insider リリース ノート

Windows Insider に新しい機能を再び提供し始め、楽しみに思います。 新しいビルドは、最新の更新プログラムのために Dev および Beta チャネルにフライトします。 このページは引き続き更新されます。このページでは、新しいビルドの機能と更新プログラムWindows Insiderします。 これらの更新プログラムを実際に組み合わせ、準備を整えます。

| 機能                 | 説明                | 対象ユーザー | 導入されたビルド |
|-------------------------|----------------------------|--------------|------------------|
| HoloLens での CSP の変更 | データに対してクエリを実行するの新しい CSP | IT 管理者    | 20348.1403                 |

### <a name="csp-changes-on-hololens"></a>HoloLens での CSP の変更

- このビルドでWindows Insider、20348.1403

#### <a name="devdetail-csp"></a>DevDetail CSP

DevDetail CSP では、HoloLens デバイス上の空き記憶域スペースも報告されます。 これは、設定アプリの [ストレージ] ページに表示される値とほぼ一致する必要があります。 この情報を含む特定のノードを次に示します。

- ./DevDetail/Ext/Microsoft/FreeStorage (GET 操作のみ)

#### <a name="devicestatus-csp"></a>DeviceStatus CSP

DeviceStatus CSP では、HoloLens がアクティブに接続されている Wifi ネットワークの SSID と BSSID も報告されます。 この情報を含む特定のノードを次に示します。

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

### <a name="fixes-and-improvements"></a>修正と機能強化:

- ロックされた [ファイルをダウンロードするプロンプトデバイス ポータルが表示される場合の既知の問題を修正しました。](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- ファイルの [アップロードとダウンロードのデバイス ポータルに関する既知の問題を修正しました。](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)

## <a name="start-receiving-insider-builds"></a>Insider ビルドの受信を開始する
> [!NOTE]
> 最近更新していない場合は、デバイスを再起動して状態を更新し、最新のビルドを取得してください。
> - "デバイスの再起動" 音声コマンドは正常に機能します。 
> - [設定]/[再起動] で再起動ボタンを選択Windows Insider Program。
>
> 発生した可能性があるバック エンドにバグがありました。これにより、追跡が戻されます。

デバイス上HoloLens 2 [設定の **更新]** に移動し&セキュリティ  >  **Windows Insider Program]** を選択  >  **概要。** アカウントとして登録するために使用したアカウントをリンクWindows Insider。
Windows Insider は現在、チャネルに移行しています。 高速 **リング** は開発チャネルになり、低速リングはベータ チャネル になり、リリース プレビュー リングはリリースプレビュー チャネル **になります**。 マッピングは次のように表示されます。Windows Insider チャネルの説明 については、「Windows ブログでの Windows Insider チャネルの紹介」 ![ ](images/WindowsInsiderChannels.png) を参照してください。 [](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)
次に、 **[Windows のアクティブ** な開発] を選択し、開発チャネルを受け取るのとビルドをベータ チャネル、プログラムの用語を確認します。
[Confirm **> Restart Now]を選択して** 完了します。 デバイスが再起動したら、[設定] > [更新&セキュリティ] > **更新** プログラムを確認して最新のビルドを取得します。
### <a name="update-error-0x80070490-work-around"></a>更新エラー 0x80070490回避
Dev または Beta チャネルで更新0x80070490更新エラーが発生した場合は、次の短期的な回避を試してください。 インサイダー チャネルを移動し、更新プログラムを選択してから、Insider チャネルを戻す必要があります。
#### <a name="stage-one---release-preview"></a>ステージ 1 - リリース プレビュー
1.  [設定] 、 [セキュリティ&更新] 、 [Windows Insider Program、 [リリース プレビュー チャネル **] を選択します**。
2.  設定、更新プログラム&セキュリティ、Windows Update、 **更新プログラムの確認**。 更新後、ステージ 2 に進む。
#### <a name="stage-two---dev-channel"></a>ステージ 2 - 開発チャネル
1. [設定] 、 [セキュリティ&更新Windows Insider Program、 [開発チャネル] **を選択します**。
2. 設定、更新プログラム&セキュリティ、Windows Update、 **更新プログラムの確認**。
## <a name="ffu-download-and-flash-directions"></a>FFU のダウンロードとフラッシュの方向
フライト署名済み ffu でテストするには、フライト署名済み ffu をフラッシュする前に、まずデバイスのロックを解除する必要があります。
1. PC の場合:
    1. から ffu を PC にダウンロードします [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. 次のコマンドから ARC (Advanced Recovery Companion) をMicrosoft Storeします [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 。
    
1. HoloLens - Flight Unlock: Open **Settings**  >  **Update & Security Windows Insider Program** サインアップ  >  し、デバイスを再起動します。
1. Flash FFU - ARC を使用してフライト署名済み FFU をフラッシュできます。
### <a name="provide-feedback-and-report-issues"></a>フィードバックを提供し、問題を報告する
HoloLens [フィードバック Hub](hololens-feedback.md) アプリを使用して、フィードバックを提供し、問題を報告してください。 このフィードバック Hubを使用すると、エンジニアが問題をすばやくデバッグして解決するのに役立つ、必要なすべての診断情報が確実に含まれます。  HoloLens の中国語と日本語のバージョンに関する問題は、同じ方法で報告する必要があります。
> [!NOTE]
> [ドキュメント] フォルダーにアクセスするかどうかを確認するプロンプトフィードバック Hub受け入れる必要があります (メッセージが表示されたら、[は **い]** を選択します)。
## <a name="note-for-developers"></a>開発者向けの注意
HoloLens の Insider ビルドを使用してアプリケーションを開発してみてください。  使用を開始 [するには、HoloLens 開発者向けドキュメント](https://developer.microsoft.com/windows/mixed-reality/development) を参照してください。 これらの同じ手順は、HoloLens の Insider ビルドで動作します。  HoloLens 開発に既に使用Visual Studio Unity と同じビルドを使用できます。
## <a name="stop-receiving-insider-builds"></a>Insider ビルドの受信を停止する
Windows Holographic の Insider ビルドを受け取りたくない場合は、HoloLens が実稼働ビルドを実行している場合はオプトアウト[](hololens-recovery.md)できます。または、Advanced Recovery Companion を使用してデバイスを回復して、Insider 以外のバージョンの Windows Holographic にデバイスを回復することもできます。
> [!CAUTION]
> 新しいプレビュー ビルドを手動で再インストールした後に Insider Preview から登録を解除したユーザーがブルー スクリーンを表示する既知の問題があります。 その後、デバイスを手動で回復する必要があります。 影響を受け取る可能性がある場合の詳細については、この既知の問題に関するページを [参照してください](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)。
HoloLens で実稼働ビルドが実行されていないことを確認するには:
1. [システムの **設定] > [>について**] に移動し、ビルド番号を見つける。
1. [実稼働ビルド番号については、リリース ノートを参照してください](hololens-release-notes.md)。
Insider ビルドをオプトアウトするには:
1. 実稼働ビルドを実行している HoloLens で、[設定] > **[Update & Security**> Windows Insider Program] に移動し、[Stop Insider builds]/(Insider ビルドの停止)を選択 **します**。
1. 指示に従ってデバイスをオプトアウトします。
