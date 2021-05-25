---
title: Mixed Reality の写真とビデオをキャプチャ、記録、共有する
description: HoloLens Mixed Reality デバイスを使用して、Mixed Reality の写真とビデオをキャプチャ、記録、表示する方法について学習します。 Miracast または収集されたファイルを使用して共有する方法について説明します。
keywords: hololens, 写真, ビデオ, キャプチャ, mrc, Mixed Reality Capture, 写真, カメラ, ミラーキャスト, ストリーム, ライブストリーム, デモ, レコード
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
ms.openlocfilehash: 178dff5d8a30fdd9c5012e2d14f5d4683d6cc23e
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397503"
---
# <a name="create-mixed-reality-photos-and-videos"></a>Mixed Reality の写真とビデオを作成する

HoloLens は、現実世界とデジタル世界を混在するエクスペリエンスをユーザーに提供します。  Mixed Reality Capture (MRC) を使用すると、そのエクスペリエンスを写真やビデオとしてキャプチャしたり、表示した情報を他のユーザーとリアルタイムで共有することができます。

Mixed Reality キャプチャでは、一人一人の視点を使用して、他のユーザーがホログラムを見るのを見るのを見る。 3 人目の視点の場合は [、spectator ビュー を使用します](https://docs.microsoft.com/windows/mixed-reality/spectator-view)。 Spectator ビューは、デモに特に役立ちます。

友人や同僚の間でビデオを共有するのも楽しいのですが、ビデオは他のユーザーにアプリの使用やアプリやエクスペリエンスとの問題の伝達を教えるのに役立ちます。

> [!NOTE]
> Mixed Reality キャプチャ エクスペリエンスを起動できない場合、HoloLens が作業デバイスである場合は、システム管理者に確認してください。 カメラへのアクセスは、会社のポリシーを使用して制限できます。

## <a name="capture-a-mixed-reality-photo"></a>Mixed Reality 写真をキャプチャする

HoloLens で Mixed Reality の写真を撮影するには、いくつかの方法があります。ハードウェア ボタン、音声、またはデバイスを使用スタート メニュー。

### <a name="hardware-buttons-to-take-photos"></a>写真を撮影するハードウェア ボタン

現在のビューの簡単な写真を撮影するには、ボリュームの上下ボタンを同時に押します。  これは、スクリーンショットまたは印刷画面の HoloLens バージョンに少し似たものになります。

- [HoloLens 2 上のボタンの場所](hololens2-hardware.md)
- [HoloLens のボタンの場所 (第 1 世代)](hololens1-hardware.md#hololens-components)

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

HoloLens (第 1 世代) または HoloLens 2 バージョン 1903 では、"Hey Cortana, start recording" (Cortana さん、録音を開始します。) と表示されます。 記録を停止するには、"Hey Cortana, stop recording" (Cortana さん、記録を停止してください) と言います。

### <a name="start-menu-to-record-videos"></a>スタート メニュービデオを記録する

[開始] ジェスチャを使用して [開始] **に移動し**、[ビデオ] アイコン **を選択** します。 キャプチャする方向に頭を向け、エア タップ [して記録を](hololens2-basic-usage.md#touch-holograms-near-you) 開始します。 3 秒のカウントダウンが行き、記録が開始されます。

記録を停止するには、[開始] ジェスチャを使用し、強調表示されている [ビデオ] アイコン **を選択** します。 ビデオがデバイスに保存されます。

> [!NOTE]
> **HoloLens (第 1 世代) にのみ適用されます**  
> この[](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)Windows 10 October 2018 Update、HoloLens (第 1 世代) での [開始] ジェスチャと [Windows] ボタンの動作を変更します。 更新の前に、[開始] ジェスチャまたは [Windows] ボタンをクリックすると、ビデオの記録が停止します。 ただし、更新後、[スタート ジェスチャ] または [Windows] ボタンをクリックすると、[スタート] メニュー (イマーシブ アプリの場合はクイック アクションメニュー) が開き、強調表示されているビデオ アイコンを選択して記録を停止できます。 

## <a name="share-what-you-see-in-real-time"></a>表示される情報をリアルタイムで共有する

HoloLens に表示される情報を、友人や同僚とリアルタイムで共有できます。 いくつかの方法を使用できます。

1. テレビで視聴するために Miracast 対応デバイスまたはアダプターに接続する。
1. PC [Windows デバイス ポータル](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 監視する方法
1. アプリを [Microsoft HoloLensアプリを使用](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) して PC で視聴します。
1. [Microsoft](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) Dynamics 365 Remote Assist アプリをデプロイします。これにより、フロントエンド ワーカーは、見たものをリモートの専門家にストリーミングできます。 その後、リモートエキスパートは、フロント ライン ワーカーを逐語的に、または自分の世界で注釈を付け、ガイドすることができます。

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

Mixed reality の写真とビデオは、デバイスの "カメラロール" に保存されます。 ファイルエクスプローラーアプリを使用して、HoloLens のこのフォルダーの内容を参照することができます ([ **画像] > [カメラロール**] に移動します)。

また、HoloLens にプレインストールされている Photos アプリで、mixed reality の写真とビデオを表示することもできます。 世界中の写真をピン留めするには、[写真] アプリで写真を選択し、[ **混合世界に配置** する] を選択します。 写真は、配置された後、世界中に移動できます。

HoloLens に接続されている PC で Mixed Reality の写真やビデオを表示または保存するには [、MTP](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) を使用して Windows デバイス ポータル または PC の エクスプローラー [を使用できます](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)。

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>画像エクスプローラーファイルを取得するには、次のコマンドを使用します。

他のモバイル デバイスと同様に、HoloLens を PC に接続して エクスプローラー を表示し、HoloLens ライブラリ (写真、ビデオ、ドキュメント) にアクセスして簡単に転送できます。 この方法は簡単に使用できます。デバイス ポータルや Wi-Fi を使用する必要は一方ではありません。

1. デバイスのロックを解除します。
1. USB 経由でデバイスを PC に接続します。
1. エクスプローラー PC で開きます。
1. 移動: この PC \\ *yourolensname*\Internal Storage\Pictures\Camera Roll
1. 必要なファイルを PC にコピーします。

ヒント:
- ファイルが表示されていない場合は、HoloLens にサインインしてデータへのアクセスを有効にしてください。
- 診断ファイルなど、他のフォルダー内の他の [ファイルは Documents](hololens-diagnostic-logs.md#offline-diagnostics) フォルダーから取得できます。
- PC エクスプローラーから[デバイスのプロパティ] を選択すると、Windows Holographic OS のバージョン番号 (ファームウェアのバージョン)、デバイスのシリアル番号、バッテリの割合が表示されます。
- 組織が MDM を使用して [接続/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) を無効にしている場合、デバイスに接続できません。

## <a name="share-your-mixed-reality-photos-and-videos"></a>Mixed Reality の写真とビデオを共有する

Windows [Holographic バージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1)より前では、Mixed Reality の写真またはビデオをキャプチャした後、プレビューが表示されます。 プレビューの **上にある** [共有] アイコンを選択して、共有アシスタントを表示します。 そこから、その写真やビデオを共有するエンド ポイントを選択できます。

Windows Holographic バージョン 21H1 では、Mixed Reality の写真またはビデオをキャプチャした後、プレビューが表示されます。 プレビューの **上にある** [共有] アイコンを選択して、共有アシスタントを表示します。 そこから、その写真やビデオを共有するエンド ポイント (メール、OneDrive など) を選択できます。 また、HoloLens が近くのデバイスと共有できるようにするには、「 **設定-> システム-> 共有エクスペリエンス**」に移動します。 詳細については、「 [Windows 10 で近くのデバイスとの共有](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)」を参照してください。

> [!TIP] 
> また、mixed reality の写真やビデオを自動的にアップロードすることで、OneDrive から mixed reality の写真やビデオを共有することもできます。 HoloLens で OneDrive アプリを開き、 **personal [Microsoft アカウント](https://account.microsoft.com)** でサインインします (まだインストールしていない場合)。 **設定** アイコンを選択し、[**カメラのアップロード**] を選択します。 カメラのアップロードを有効にします。 アプリを HoloLens で起動するたびに、mixed reality の写真とビデオが OneDrive にアップロードされるようになりました。

> [!NOTE]
> Onedrive で個人用 Microsoft アカウントを使用して OneDrive にサインインしている場合にのみ、OneDrive でのカメラのアップロードを有効にすることができます。 職場または学校のアカウントを使用して HoloLens をセットアップした場合は、OneDrive アプリに個人の Microsoft アカウントを追加して、この機能を有効にすることができます。

## <a name="limitations-of-mixed-reality-capture"></a>Mixed reality キャプチャの制限事項

- Mixed reality キャプチャを使用している間、HoloLens のフレームレートは半分から 30 Hz になります。
- 写真/ビデオカメラが既に別のアプリケーションによって使用されている場合、ライブストリーミング中、またはシステムリソースが少ない場合は、写真やビデオの解像度が低下する可能性があります。

### <a name="maximum-recording-length"></a>最大記録長

Windows Holographic バージョン20H2 より前の HoloLens 2 デバイスでは、デバイス上に記録されたビデオは、最大長の5分に制限されていました。

お客様からのフィードバックにより、 [混合現実のキャプチャ](holographic-photos-and-videos.md)の記録長さが増加しています。 混合の現実のキャプチャは、既定では5分に制限されなくなりましたが、代わりに使用可能なディスク領域に基づいて最大記録長が計算されます。 デバイスは、ディスクの空き領域の最大80% まで、使用可能なディスク領域に基づいて、最大ビデオ記録期間を見積もります。

> [!NOTE]
> 次のいずれかが発生した場合、HoloLens では既定のビデオ記録の長さ (5 分) が使用されます。
> - 推定最大記録期間は、既定の5分よりも小さくなっています。
> - 使用可能なディスク領域が、合計ディスク領域の20% 未満です。

## <a name="default-file-format-and-resolution"></a>既定のファイル形式と解像度

### <a name="default-photo-format-and-resolution"></a>既定の写真の形式と解像度

|  デバイス  |  Format  |  拡張機能  |  解決方法  |
|----------|----------|----------|----------|
| HoloLens 2 | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens (第 1 世代) | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408x792px |

### <a name="recorded-video-format-and-resolution"></a>記録されたビデオの形式と解像度

| デバイス | Format | 拡張機能 | 解決方法 | 速度 | オーディオ |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30fps | 48kHz ステレオ |
| HoloLens (第 1 世代) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | 48kHz ステレオ |
