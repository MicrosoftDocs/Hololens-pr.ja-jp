---
title: Mixed reality の写真とビデオをキャプチャ、記録、共有する
description: HoloLens mixed reality デバイスを使用して、現実の写真やビデオをキャプチャ、記録、表示する方法について説明します。 Miracast または収集されたファイルを使用して共有する方法について説明します。
keywords: hololens、写真、ビデオ、キャプチャ、mrc、mixed reality のキャプチャ、写真、カメラ、miracast、stream、ライブストリーム、demo、記録
ms.assetid: 1b636ec3-6186-4fbb-81b2-71155aef0593
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 10/28/2019
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 86ef4328869c15517732eedf3dfb9e2a8252e713
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309180"
---
# <a name="create-mixed-reality-photos-and-videos"></a>Mixed reality の写真とビデオを作成する

HoloLens を使用すると、ユーザーは世界とデジタルの世界を混在させることができます。  Mixed reality キャプチャ (MRC) を使用すると、そのエクスペリエンスを写真やビデオとしてキャプチャしたり、他のユーザーとリアルタイムで表示したりすることができます。

Mixed reality capture では、最初の人の視点を使用して、他のユーザーが表示されているホログラムを見ることができます。 3人の観点では、 [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view)を使用します。 Spectator view は、デモに特に役立ちます。

友人や同僚とビデオを共有することは楽しいですが、ビデオも、他の人がアプリを使用したり、アプリやエクスペリエンスに関する問題を伝えたりするのにも役立ちます。

> [!NOTE]
> Mixed reality のキャプチャエクスペリエンスを起動できず、HoloLens が仕事用デバイスの場合は、システム管理者に確認してください。 カメラへのアクセスは、会社のポリシーによって制限できます。

## <a name="capture-a-mixed-reality-photo"></a>Mixed reality の写真をキャプチャする

HoloLens で mixed reality の写真を撮るには、いくつかの方法があります。ハードウェアボタン、音声、または [スタート] メニューを使用できます。

### <a name="hardware-buttons-to-take-photos"></a>写真を撮影するためのハードウェアボタン

現在のビューの簡単な写真を撮るには、[音量] ボタンと [音量] ボタンを同時に押します。  これは、HoloLens バージョンのスクリーンショットや印刷画面のようなものです。

- [HoloLens 2 のボタンの場所](hololens2-hardware.md)
- [HoloLens のボタンの場所 (第1世代)](hololens1-hardware.md#hololens-components)

> [!NOTE]
> [ **音量アップ** ] ボタンと [ **音量** ] ボタンを3秒押し続けると、写真を撮影するのではなく、ビデオの録画が開始されます。 記録を停止するには、[ **音量アップ** ] ボタンと [ **音量ダウン** ] ボタンの両方を同時にタップします。

### <a name="voice-commands-to-take-photos"></a>写真を撮影するための音声コマンド

HoloLens 2、バージョン 2004 (およびそれ以降) では、「写真を撮る」と言います。

HoloLens (第1世代) または HoloLens 2、バージョン1903では、「Cortana さん、写真を撮る」と言います。

### <a name="start-menu-to-take-photos"></a>[スタート] メニューを使用して写真を撮影する

開始ジェスチャを使用して **スタート** 画面に戻り、 **カメラ** アイコンを選択します。

キャプチャする内容の方向をポイントし、 [エアタップ](hololens2-basic-usage.md#touch-holograms-near-you) を使用して写真を撮影します。 引き続きエアタップして、追加の写真を取り込むことができます。 キャプチャした写真はすべてデバイスに保存されます。

フォトキャプチャを終了するには、もう一度開始ジェスチャを使用します。  

## <a name="capture-a-mixed-reality-video"></a>Mixed reality ビデオをキャプチャする

HoloLens で mixed reality のビデオを記録するには、いくつかの方法があります。ハードウェアボタン、音声、または [スタート] メニューを使用できます。

### <a name="hardware-buttons-to-record-videos"></a>ビデオを録画するためのハードウェアボタン

ビデオを録画する最も簡単な方法は、3秒のカウントダウンが開始されるまで、[ **音量** ] ボタンと [ **音量** ] ボタンを同時に押すことです。 記録を停止するには、両方のボタンを同時にタップします。

> [!NOTE]
> [ **音量** ] ボタンと [ **音量** ] ボタンを同時に押すと、ビデオを録画するのではなく、写真が撮影されます。

### <a name="voice-to-record-videos"></a>動画を録画するための音声

HoloLens 2、バージョン 2004 (およびそれ以降) では、"記録の開始" と言います。 記録を停止するには、「録画を停止する」と言います。

HoloLens (第1世代) または HoloLens 2、バージョン1903では、「Cortana について、記録を開始する」と言います。 記録を停止するには、"Cortana さん、録画を停止する" と言います。

### <a name="start-menu-to-record-videos"></a>ビデオを録画するための [スタート] メニュー

開始ジェスチャを使用して **スタート** 画面にアクセスし、 **ビデオ** アイコンを選択します。 キャプチャする対象の方向をポイントし、次に [エアタップ](hololens2-basic-usage.md#touch-holograms-near-you) で録音を開始します。 3秒間のカウントダウンが発生し、記録が開始されます。

記録を停止するには、開始ジェスチャを使用して、強調表示された **ビデオ** アイコンを選択します。 ビデオはデバイスに保存されます。

> [!NOTE]
> **HoloLens (第1世代) のみに適用されます**  
> [Windows 10 10 月2018更新プログラム](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)は、[開始] ジェスチャと [windows] ボタンが HoloLens (第1世代) でどのように動作するかを変更します。 更新前は、開始ジェスチャまたは Windows ボタンによってビデオ記録が停止されます。 ただし、更新後、[開始ジェスチャ] または [Windows] ボタンをクリックすると、[ **スタート** ] メニュー (または、イマーシブアプリの場合は [ **クイックアクション] メニュー** ) が開き、強調表示された **ビデオ** アイコンを選択して録画を停止できます。

## <a name="share-what-you-see-in-real-time"></a>リアルタイムで表示されるものを共有する

HoloLens で表示されているものは、リアルタイムで友人や同僚と共有できます。 使用できるメソッドはいくつかあります。

1. Miracast が有効なデバイスまたはアダプターに接続して、テレビを視聴します。
1. [Windows デバイスポータル](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)を使用して PC を監視する
1. [Microsoft HoloLens コンパニオンアプリ](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)を使用して PC を監視します。
1. [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist)アプリを展開します。これにより、フロントラインワーカーは、リモートのエキスパートに表示される情報をストリームできます。 その後、リモートの専門家は、フロントラインワーカーの口頭で他者をガイドしたり、世界中に注釈を付けたりすることができます。

> [!NOTE]
> Windows デバイスポータルまたは Microsoft HoloLens コンパニオンアプリを使用して表示される情報を共有するには、HoloLens が [開発者モード](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)である必要があります。

### <a name="stream-video-with-miracast"></a>Miracast によるビデオのストリーミング

開始ジェスチャを使用して **スタート** 画面にアクセスし、[ **接続** ] アイコンを選択します。 表示されるピッカーから、接続先の Miracast が有効なデバイスまたはアダプターを選択します。

共有を停止するには、開始ジェスチャを使用して、強調表示された **接続** アイコンを選択します。 ストリーミングを行っているため、デバイスには何も保存されません。

> [!NOTE]
> Miracast サポートは、 [Windows 10 10 月2018更新プログラム](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)以降、HoloLens (第1世代) で有効になりました。

### <a name="real-time-video-with-windows-device-portal"></a>Windows デバイスポータルを使用したリアルタイムビデオ

Windows デバイスポータルを使用して共有するには、HoloLens で開発者モードを有効にする必要があるため、開発者向けドキュメントの手順に従って [開発者モードを設定し、Windows デバイスポータルに移動](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)します。

### <a name="microsoft-hololens-companion-app"></a>Microsoft HoloLens コンパニオンアプリ

Microsoft HoloLens コンパニオンアプリを使用して共有するには、HoloLens で開発者モードを有効にする必要があるため、開発者向けドキュメントの手順に従って [開発者モードを設定](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)します。 次に、 [Microsoft hololens コンパニオンアプリ](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) をダウンロードし、アプリ内の指示に従って HoloLens に接続します。

アプリが HoloLens で設定されたら、アプリのメインメニューから [ **ライブストリーム** ] オプションを選択します。

## <a name="view-your-mixed-reality-photos-and-videos"></a>Mixed reality の写真とビデオを表示する

Mixed reality の写真とビデオは、デバイスの "カメラロール" に保存されます。 ファイルエクスプローラーアプリを使用して、HoloLens のこのフォルダーの内容を参照することができます ([画像] > [カメラロール] に移動します)。

また、HoloLens にプレインストールされている Photos アプリで、mixed reality の写真とビデオを表示することもできます。 世界中の写真をピン留めするには、[写真] アプリで写真を選択し、[ **混合世界に配置** する] を選択します。 写真は、配置された後、世界中に移動できます。

HoloLens に接続されている PC で mixed reality の写真とビデオを表示したり保存したりするには、 [Windows デバイスポータル](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) または MTP を使用して [pc のエクスプローラー](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)を使用します。

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>ファイルエクスプローラーを使用して画像、ビデオ、ファイルを取得する

他のモバイルデバイスと同様に、HoloLens を PC に接続して、ファイルエクスプローラーから HoloLens ライブラリ (写真、ビデオ、ドキュメント) にアクセスして転送を容易にすることができます。 この方法は使いやすく、デバイスポータルや Wi-fi を使用する必要はありません。

1. デバイスのロックを解除します。
1. USB を使用してデバイスを PC に接続します。
1. PC でファイルエクスプローラーが開きます。
1. 移動: This PC \\ *yourhololensname*\ Internal Storage\Pictures\Camera Roll
1. 必要なすべてのファイルを PC にコピーします。

ヒント:
- ファイルが表示されない場合は、HoloLens にサインインしてデータにアクセスできることを確認してください。
- 他のフォルダーにある他のファイル ( [診断ファイル](hololens-diagnostic-logs.md#offline-diagnostics) など) は、[ドキュメント] フォルダーから取得できます。
- PC のエクスプローラーから、[デバイスのプロパティ] を選択して、Windows Holographic OS のバージョン番号 (ファームウェアのバージョン)、デバイスのシリアル番号、およびバッテリの割合を確認できます。
- 組織で MDM を使用して [接続/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) を無効にした場合、デバイスに接続できなくなります。

## <a name="share-your-mixed-reality-photos-and-videos"></a>Mixed reality の写真とビデオを共有する

Mixed reality の写真またはビデオをキャプチャすると、プレビューが表示されます。 プレビューの上にある [ **共有** ] アイコンを選択して、共有アシスタントを表示します。 そこから、写真またはビデオを共有するエンドポイントを選択できます。

また、mixed reality の写真とビデオを OneDrive から共有することもできます。これにより、mixed reality の写真とビデオが自動的にアップロードされます。 HoloLens で OneDrive アプリを開き、personal [Microsoft アカウント](https://account.microsoft.com) でサインインします (まだインストールしていない場合)。 **設定** アイコンを選択し、[**カメラのアップロード**] を選択します。 カメラのアップロードを有効にします。 アプリを HoloLens で起動するたびに、mixed reality の写真とビデオが OneDrive にアップロードされるようになりました。

> [!NOTE]
> Onedrive で個人用 Microsoft アカウントを使用して OneDrive にサインインしている場合にのみ、OneDrive でのカメラのアップロードを有効にすることができます。 職場または学校のアカウントを使用して HoloLens をセットアップした場合は、OneDrive アプリに個人の Microsoft アカウントを追加して、この機能を有効にすることができます。

## <a name="limitations-of-mixed-reality-capture"></a>Mixed reality キャプチャの制限事項

- Mixed reality キャプチャを使用している間、HoloLens のレートは 30 Hz に半減します。
- 写真/ビデオカメラが既に別のアプリケーションによって使用されている場合、ライブストリーミング中、またはシステムリソースが少ない場合は、写真やビデオの解像度が低下する可能性があります。

### <a name="maximum-recording-length"></a>最大記録長

Windows Holographic より前の HoloLens 2 デバイスでは、デバイスに記録されているバージョン20H2 ビデオは、最大で5分の長さに制限されていました。

お客様からのフィードバックにより、 [混合現実のキャプチャ](holographic-photos-and-videos.md)の記録長さが増加しています。 混合の現実のキャプチャは、既定では5分に制限されなくなりましたが、代わりに使用可能なディスク領域に基づいて最大記録長が計算されます。 デバイスは、ディスクの空き領域の最大80% まで、使用可能なディスク領域に基づいて、最大ビデオ記録期間を見積もります。

> [!NOTE]
> 次のいずれかが発生した場合、HoloLens では既定のビデオ記録の長さ (5 分) が使用されます。
> - 推定最大記録期間は、既定の5分よりも小さくなっています。
> - 使用可能なディスク領域が、合計ディスク領域の20% 未満です。

## <a name="default-file-format-and-resolution"></a>既定のファイル形式と解決方法

### <a name="default-photo-format-and-resolution"></a>既定の写真の形式と解像度

|  Device  |  Format  |  拡張機能  |  解像度  |
|----------|----------|----------|----------|
| HoloLens 2 | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens (第 1 世代) | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408x792px |

### <a name="recorded-video-format-and-resolution"></a>記録されたビデオ形式と解像度

| Device | Format | 拡張機能 | 解像度 | 速度 | オーディオ |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30 fps | 48 Khz ステレオ |
| HoloLens (第 1 世代) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | 48 Khz ステレオ |
