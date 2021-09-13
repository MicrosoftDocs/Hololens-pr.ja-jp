---
title: Mixed reality の写真とビデオをキャプチャ、記録、共有する
description: HoloLens mixed reality デバイスを使用して、現実の写真やビデオをキャプチャ、記録、表示する方法について説明します。 Miracast または収集したファイルを介して共有する方法を説明します。
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
ms.openlocfilehash: daced6fab65f779b7bd670bf1275f99ae5311d3f
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033283"
---
# <a name="create-mixed-reality-photos-and-videos"></a>Mixed Reality の写真とビデオを作成する

HoloLens を使用すると、ユーザーは、実際の世界とデジタルの世界を混在させることができます。  Mixed reality キャプチャ (MRC) を使用すると、そのエクスペリエンスを写真やビデオとしてキャプチャしたり、他のユーザーとリアルタイムで表示したりすることができます。

Mixed reality capture では、最初の人の視点を使用して、他のユーザーが表示されているホログラムを見ることができます。 3人の観点では、 [spectator view](/windows/mixed-reality/spectator-view)を使用します。 Spectator view は、デモに特に役立ちます。

友人や同僚とビデオを共有することは楽しいですが、ビデオも、他の人がアプリを使用したり、アプリやエクスペリエンスに関する問題を伝えたりするのにも役立ちます。

> [!NOTE]
> mixed reality のキャプチャエクスペリエンスを起動できず、HoloLens が仕事用デバイスの場合は、システム管理者に確認してください。 カメラへのアクセスは、会社のポリシーによって制限できます。

## <a name="capture-a-mixed-reality-photo"></a>Mixed reality の写真をキャプチャする

HoloLens で mixed reality の写真を撮るには、いくつかの方法があります。ハードウェアボタン、音声、またはスタートメニューを使用できます。

### <a name="hardware-buttons-to-take-photos"></a>写真を撮影するためのハードウェアボタン

現在のビューの簡単な写真を撮るには、[音量] ボタンと [音量] ボタンを同時に押します。  これは、スクリーンショットや印刷画面の HoloLens バージョンに似ています。

- [HoloLens 2 上のボタンの場所](hololens2-hardware.md)
- [HoloLens 上のボタンの場所 (第1世代)](hololens1-hardware.md#hololens-components)

> [!NOTE]
> [ **音量アップ** ] ボタンと [ **音量** ] ボタンを3秒押し続けると、写真を撮影するのではなく、ビデオの録画が開始されます。 記録を停止するには、[ **音量アップ** ] ボタンと [ **音量ダウン** ] ボタンの両方を同時にタップします。

### <a name="voice-commands-to-take-photos"></a>写真を撮影するための音声コマンド

HoloLens 2 のバージョン 2004 (以降) では、「写真を撮る」と言います。

HoloLens (第1世代) または HoloLens 2 バージョン1903では、次のようになります。「Cortana、写真を撮る」と言います。

### <a name="start-menu-to-take-photos"></a>写真を撮影するためのスタートメニュー

開始ジェスチャを使用して **スタート** 画面に戻り、 **カメラ** アイコンを選択します。

キャプチャする内容の方向をポイントし、 [エアタップ](hololens2-basic-usage.md#touch-holograms-near-you) を使用して写真を撮影します。 引き続きエアタップして、追加の写真を取り込むことができます。 キャプチャした写真はすべてデバイスに保存されます。

フォトキャプチャを終了するには、もう一度開始ジェスチャを使用します。  

## <a name="capture-a-mixed-reality-video"></a>Mixed reality ビデオをキャプチャする

HoloLens で mixed reality のビデオを記録するには、いくつかの方法があります。ハードウェアボタン、音声、またはスタートメニューを使用できます。

### <a name="hardware-buttons-to-record-videos"></a>ビデオを録画するためのハードウェアボタン

ビデオを録画する最も簡単な方法は、3秒のカウントダウンが開始されるまで、[ **音量** ] ボタンと [ **音量** ] ボタンを同時に押すことです。 記録を停止するには、両方のボタンを同時にタップします。

> [!NOTE]
> [ **音量** ] ボタンと [ **音量** ] ボタンを同時に押すと、ビデオを録画するのではなく、写真が撮影されます。

### <a name="voice-to-record-videos"></a>動画を録画するための音声

HoloLens 2 バージョン 2004 (以降) では、"記録の開始" と言うことができます。 記録を停止するには、「録画を停止する」と言います。

HoloLens (第1世代) または HoloLens 2 バージョン1903では、「Cortana、記録を開始する」と言います。 記録を停止するには、「Cortana、録画を停止する」と言います。

### <a name="start-menu-to-record-videos"></a>ビデオを録画するためのスタートメニュー

開始ジェスチャを使用して **スタート** 画面にアクセスし、 **ビデオ** アイコンを選択します。 キャプチャする対象の方向をポイントし、次に [エアタップ](hololens2-basic-usage.md#touch-holograms-near-you) で録音を開始します。 3秒間のカウントダウンが発生し、記録が開始されます。

記録を停止するには、開始ジェスチャを使用して、強調表示された **ビデオ** アイコンを選択します。 ビデオはデバイスに保存されます。

> [!NOTE]
> **HoloLens (第1世代) のみに適用されます**  
> [Windows 10 October 2018 Update](/windows/mixed-reality/release-notes-october-2018)は HoloLens (第1世代) で開始ジェスチャと Windows ボタンがどのように動作するかを変更します。 更新前は、開始ジェスチャまたは Windows ボタンによってビデオ記録が停止されます。 ただし、更新後、[開始ジェスチャ] または [Windows] ボタンをクリックすると [**スタート**] メニュー (または、イマーシブアプリの場合は [**クイックアクション] メニュー** ) が開きます。このメニューから、強調表示された **ビデオ** アイコンを選択して録画を停止できます。

## <a name="share-what-you-see-in-real-time"></a>リアルタイムで表示されるものを共有する

HoloLens に表示されているものは、リアルタイムで友人や同僚と共有できます。 使用できるメソッドはいくつかあります。

1. Miracast 対応のデバイスまたはアダプターに接続して、テレビを視聴する。
1. [Windows デバイスポータル](/windows/mixed-reality/using-the-windows-device-portal)を使用して PC を監視する
1. [Microsoft HoloLens コンパニオンアプリ](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)を使用して PC を監視する。
1. [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist)アプリをデプロイします。これにより、フロントラインワーカーは、リモートのエキスパートに表示される情報をストリームできます。 その後、リモートの専門家は、フロントラインワーカーの口頭で他者をガイドしたり、世界中に注釈を付けたりすることができます。

> [!NOTE]
> Windows デバイスポータルまたは Microsoft HoloLens コンパニオンアプリを使用して表示されるものを共有するには、HoloLens が[開発者モード](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)である必要があります。

### <a name="stream-video-with-miracast"></a>Miracast によるビデオのストリーミング

開始ジェスチャを使用して [**スタート**] ボタンをクリックし、[ **Connect** ] アイコンを選択します。 表示されるピッカーから、接続する Miracast 対応のデバイスまたはアダプターを選択します。

共有を停止するには、開始ジェスチャを使用して、強調表示されている **Connect** アイコンを選択します。 ストリーミングを行っているため、デバイスには何も保存されません。

> [!NOTE]
> [Windows 10 October 2018 Update](/windows/mixed-reality/release-notes-october-2018)で始まる HoloLens (第1世代) で Miracast のサポートが有効になりました。

### <a name="real-time-video-with-windows-device-portal"></a>Windows デバイスポータルを使用したリアルタイムビデオ

Windows デバイスポータルを使用して共有するには HoloLens で開発者モードを有効にする必要があるため、開発者向けドキュメントの手順に従って[開発者モードを設定し、Windows デバイスポータルに移動](/windows/mixed-reality/using-the-windows-device-portal)してください。

### <a name="microsoft-hololens-companion-app"></a>Microsoft HoloLens コンパニオンアプリ

Microsoft HoloLens コンパニオンアプリを使用して共有するには HoloLens で開発者モードを有効にする必要があるため、開発者向けドキュメントの手順に従って[開発者モードを設定](/windows/mixed-reality/using-the-windows-device-portal)します。 次に、 [Microsoft HoloLens コンパニオンアプリ](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)をダウンロードし、アプリ内の指示に従って HoloLens に接続します。

アプリが HoloLens に設定されたら、アプリのメインメニューから [**ライブストリーム**] オプションを選択します。

## <a name="view-your-mixed-reality-photos-and-videos"></a>Mixed reality の写真とビデオを表示する

Mixed reality の写真とビデオは、デバイスの "カメラロール" に保存されます。 ファイルエクスプローラーアプリを使用して、HoloLens 上のこのフォルダーの内容を参照できます ([**画像] > [カメラロール**] の順に移動します)。

HoloLens にプレインストールされている Photos アプリで、mixed reality の写真とビデオを表示することもできます。 世界中の写真をピン留めするには、[写真] アプリで写真を選択し、[ **混合世界に配置** する] を選択します。 写真は、配置された後、世界中に移動できます。

HoloLens に接続されている pc で mixed reality の写真とビデオを表示したり保存したりするには、 [Windows デバイスポータル](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)または MTP を使用して[pc のエクスプローラー](/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)を使用します。

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>ファイルエクスプローラーを使用して画像、ビデオ、ファイルを取得する

他のモバイルデバイスと同様に、HoloLens を PC に接続して、簡単に転送できるように、HoloLens ライブラリ (写真、ビデオ、ドキュメント) にアクセスできるようにします。 この方法は使いやすく、デバイスポータルや Wi-fi を使用する必要はありません。

1. デバイスのロックを解除します。
1. USB を使用してデバイスを PC に Connect します。
1. PC でファイルエクスプローラーが開きます。
1. 移動: This PC \\ *yourhololensname*\ 内部 Storage \Pictures\Camera Roll
1. 必要なすべてのファイルを PC にコピーします。

ヒント:
- ファイルが表示されない場合は、HoloLens にサインインして、データにアクセスできることを確認してください。
- 他のフォルダーにある他のファイル ( [診断ファイル](hololens-diagnostic-logs.md#offline-diagnostics) など) は、[ドキュメント] フォルダーから取得できます。
- PC のエクスプローラーから、[デバイスのプロパティ] を選択して、Windows Holographic OS のバージョン番号 (ファームウェアのバージョン)、デバイスのシリアル番号、およびバッテリの割合を確認できます。
- 組織で MDM を使用して [接続/AllowUSBConnection](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) を無効にした場合、デバイスに接続できなくなります。

## <a name="share-your-mixed-reality-photos-and-videos"></a>Mixed reality の写真とビデオを共有する

[Holographic バージョン21h1 を Windows](hololens-release-notes.md#windows-holographic-version-21h1)前に、mixed reality の写真またはビデオをキャプチャした後、プレビューが表示されます。 プレビューの上にある [ **共有** ] アイコンを選択して、共有アシスタントを表示します。 そこから、写真またはビデオを共有するエンドポイントを選択できます。

Windows Holographic バージョン21h1 では、mixed reality の写真またはビデオをキャプチャした後にプレビューが表示されます。 プレビューの上にある [ **共有** ] アイコンを選択して、共有アシスタントを表示します。 そこから、その写真またはビデオを共有するエンドポイント (メール、OneDrive など) を選択できます。 また、**設定-> システム-> 共有エクスペリエンス** に移動して、HoloLens を近くのデバイスと共有することもできます。 詳細については、「 [Windows 10 で近くのデバイスとの共有](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)」を参照してください。

> [!TIP] 
> また、混在している現実の写真やビデオを自動的にアップロードすることで、OneDrive から mixed reality の写真やビデオを共有することもできます。 HoloLens で OneDrive アプリを開き、**個人用 [Microsoft アカウント](https://account.microsoft.com)** でサインインします (まだインストールしていない場合)。 **設定** アイコンを選択し、[**カメラのアップロード**] を選択します。 カメラのアップロードを有効にします。 これで、HoloLens でアプリを起動するたびに、mixed reality の写真とビデオが OneDrive にアップロードされるようになります。

> [!NOTE]
> 個人用 Microsoft アカウントで OneDrive にサインインしている場合にのみ、OneDrive でカメラのアップロードを有効にすることができます。 職場または学校のアカウントを使用して HoloLens を設定した場合は、OneDrive アプリに個人用 Microsoft アカウントを追加して、この機能を有効にすることができます。

## <a name="limitations-of-mixed-reality-capture"></a>Mixed reality キャプチャの制限事項

- 混合 reality キャプチャを使用している間、HoloLens のフレームレートは半分から 30 Hz になります。
- 写真/ビデオカメラが既に別のアプリケーションによって使用されている場合、ライブストリーミング中、またはシステムリソースが少ない場合は、写真やビデオの解像度が低下する可能性があります。

### <a name="maximum-recording-length"></a>最大記録長

Windows Holographic、バージョン20h2 より前のデバイス HoloLens 2 では、デバイスに記録されたビデオは、最大長の5分に制限されていました。

お客様からのフィードバックにより、 [混合現実のキャプチャ](holographic-photos-and-videos.md)の記録長さが増加しています。 混合の現実のキャプチャは、既定では5分に制限されなくなりましたが、代わりに使用可能なディスク領域に基づいて最大記録長が計算されます。 デバイスは、ディスクの空き領域の最大80% まで、使用可能なディスク領域に基づいて、最大ビデオ記録期間を見積もります。

> [!NOTE]
> 次のいずれかが発生した場合、HoloLens は既定のビデオ記録の長さ (5 分) を使用します。
> - 推定最大記録期間は、既定の5分よりも小さくなっています。
> - 使用可能なディスク領域が、合計ディスク領域の20% 未満です。

## <a name="default-file-format-and-resolution"></a>既定のファイル形式と解決方法

### <a name="default-photo-format-and-resolution"></a>既定の写真の形式と解像度

|  デバイス  |  Format  |  拡張機能  |  解決方法  |
|----------|----------|----------|----------|
| HoloLens 2 | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens (第 1 世代) | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408x792px |

### <a name="recorded-video-format-and-resolution"></a>記録されたビデオ形式と解像度

| デバイス | Format | 拡張機能 | 解決方法 | 速度 | オーディオ |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30 fps | 48 Khz ステレオ |
| HoloLens (第 1 世代) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | 48 Khz ステレオ |
