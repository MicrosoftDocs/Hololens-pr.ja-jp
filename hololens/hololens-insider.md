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
ms.date: 10/19/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 382c979138068ab1d9682ee4e84831accc9e4553
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351657"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens の Insider Preview

HoloLens のための最新の Insider Preview ビルドへようこそ。 この機能は簡単に[開始](hololens-insider.md#start-receiving-insider-builds)でき、次の主要なオペレーティングシステムの更新プログラムについての重要なフィードバックを提供します HoloLens。

## <a name="windows-insider-release-notes"></a>WindowsInsider のリリースノート

新機能と HoloLens の期間 これらの新しい更新プログラムについては HoloLens をご覧ください。

### <a name="colorblind-mode"></a>Colorblind モード

Insider build 20348.1463 に追加されました

colorblind モードは、HoloLens アクセスしやすくする優れた機能です。 新しい色覚モードは、設定アプリの [   ->  **アクセスの容易さ** 設定  ->  **色フィルター**] の下にあります。 いくつかの新しいフィルターを使用できます。 いくつかの使用可能なフィルターの視覚的な例を次に示します。

| オフ | グレースケール | Tritanopia |
|-----|-----------|------------|
| ![色フィルターをオフにする](images/colorblind-off.png)   | ![カラーフィルターグレースケール](images/colorblind-greyscale.png)         | ![カラーフィルター tritanopia](images/colorblind-tritanopia.png)          |

### <a name="fixes-and-improvements"></a>修正プログラムと機能強化

- [電力が18% になるたびに、デバイスが突然自動的に](hololens-troubleshooting.md#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)シャットダウンされるという既知の問題を修正しています。
- ダウン方向を検出するときのプラットフォームモードの移動の機能強化。
- 更新ダイアログに関する問題を修正しています。
- 受信トレイ Microsoft Edge ブラウザーのバージョンが更新されました。
- 再起動後にオプションの診断データを切り替えると、テレメトリ設定ページで選択した設定が保持されない問題を修正しました。
- デバイスに対して45度の角度で回転したときに、QR コードが認識されない問題を修正しました。

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
