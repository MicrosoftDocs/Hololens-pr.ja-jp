---
title: 複合現実の写真とビデオをキャプチャ、記録、共有する
description: HoloLens 複合現実デバイスを使用して、キャプチャ、記録、表示、複合現実の写真とビデオを取得する方法について学習します。 Miracast または収集されたファイルを使用して共有する方法について説明します。
keywords: hololens, 写真, ビデオ, キャプチャ, mrc, mixed reality capture, 写真, カメラ, miracast, stream, livestream, demo, record
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
ms.sourcegitcommit: 047738224840013bede45dbb642a0ad2115a9c84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2021
ms.locfileid: "11406711"
---
# <a name="create-mixed-reality-photos-and-videos"></a>Mixed Reality の写真とビデオを作成する

HoloLens は、現実世界とデジタル世界を混在するエクスペリエンスをユーザーに提供します。  複合現実キャプチャ (MRC) を使用すると、そのエクスペリエンスを写真やビデオとしてキャプチャしたり、見た情報をリアルタイムで他のユーザーと共有することができます。

複合現実のキャプチャでは、一人一人の視点を使用して、他のユーザーがホログラムを表示できます。 第三者視点の場合は、スペクテーター [ビューを使用します](https://docs.microsoft.com/windows/mixed-reality/spectator-view)。 Spectator ビューは、デモに特に役立ちます。

友人や同僚の間でビデオを共有するのも楽しい一方で、ビデオは他のユーザーにアプリの使用を教えることや、アプリやエクスペリエンスと問題を伝えるのに役立ちます。

> [!NOTE]
> 複合現実キャプチャ エクスペリエンスを起動できない場合、HoloLens が作業デバイスである場合は、システム管理者に確認してください。 カメラへのアクセスは、会社のポリシーを通じて制限できます。

## <a name="capture-a-mixed-reality-photo"></a>複合現実の写真をキャプチャする

HoloLens で複合現実の写真を撮る方法は複数あります。ハードウェア ボタン、音声、または [スタート] メニューを使用できます。

### <a name="hardware-buttons-to-take-photos"></a>写真を撮るハードウェア ボタン

現在のビューの簡単な写真を撮る場合は、音量を上げ、音量を下げボタンを同時に押します。  これは、スクリーンショットまたは印刷画面の HoloLens バージョンと少し似たものになります。

- [HoloLens 2 のボタンの場所](hololens2-hardware.md)
- [HoloLens のボタンの場所 (第 1 世代)](hololens1-hardware.md#hololens-components)

> [!NOTE]
> 音量を**上げ、****音量を**下げボタンを 3 秒間押すと、写真を撮るのではなく、ビデオの記録が開始されます。 録音を停止するには、音量アップ**ボタンと音量ダウンボタン****の両方を**同時にタップします。

### <a name="voice-commands-to-take-photos"></a>写真を撮る音声コマンド

HoloLens 2 バージョン 2004 以降では、「写真を撮る」と言います。

HoloLens (第 1 世代) または HoloLens 2 バージョン 1903 では、「コルタナさん、写真を撮って」と言います。

### <a name="start-menu-to-take-photos"></a>写真を撮るスタート メニュー

Start ジェスチャを使用して [スタート] に **移動し**、カメラ アイコン **を選択** します。

キャプチャする画像の方向に頭を向け、エア [タップ](hololens2-basic-usage.md#touch-holograms-near-you) で写真を撮る。 引き続きエア タップして追加の写真をキャプチャできます。 キャプチャした写真は、デバイスに保存されます。

写真のキャプチャを終了するには、もう一度 Start ジェスチャを使用します。  

## <a name="capture-a-mixed-reality-video"></a>複合現実のビデオをキャプチャする

HoloLens で複合現実のビデオを記録するには、いくつかの方法があります。ハードウェア ボタン、音声、または [スタート] メニューを使用できます。

### <a name="hardware-buttons-to-record-videos"></a>ビデオを記録するハードウェア ボタン

ビデオを記録する最も簡単な方法は、3**** 秒のカウントダウン**** が始まるまで音量を上げ、音量を下げボタンを同時に押し続けます。 録音を停止するには、両方のボタンを同時にタップします。

> [!NOTE]
> 音量を上**げ、****音量を**下げボタンを同時にすばやく押すと、ビデオを録画するのではなく、写真が撮影されます。

### <a name="voice-to-record-videos"></a>ビデオを録音する音声

HoloLens 2 バージョン 2004 以降では、「録音を開始する」と言います。 録音を停止するには、「録音を停止する」と言います。

HoloLens (第 1 世代) または HoloLens 2 バージョン 1903 では、「コルタナさん、録音を開始してください」と言います。 録音を停止するには、「コルタナさん、録音を停止してください」と言います。

### <a name="start-menu-to-record-videos"></a>ビデオを記録するスタート メニュー

Start ジェスチャを使用して [スタート] に移動 **し**、ビデオ アイコン **を選択** します。 キャプチャする情報の方向に頭を向け、エア [タップで録音](hololens2-basic-usage.md#touch-holograms-near-you) を開始します。 3 秒のカウントダウンが行い、録音が開始されます。

録音を停止するには、スタート ジェスチャを使用して、強調表示されているビデオ アイコン **を選択** します。 ビデオはデバイスに保存されます。

> [!NOTE]
> **HoloLens (第 1 世代) にのみ適用されます。**  
> [Windows 10 10 月 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)は、HoloLens (第 1 世代) でのスタート ジェスチャと Windows ボタンの動作を変更します。 更新の前に、[スタート] ジェスチャまたは [Windows] ボタンがビデオ録画を停止します。 ただし、更新後、[スタート] ジェスチャまたは Windows ボタンをクリックすると、[スタート****] メニュー (またはイマーシブ アプリの場合はクイック アクション メニュー **** ) が開き、強調表示されたビデオ アイコンを選択して録画を停止できます。 ****

## <a name="share-what-you-see-in-real-time"></a>リアルタイムで表示される情報を共有する

HoloLens で見た情報を友人や同僚とリアルタイムで共有できます。 使用可能なメソッドは次のとおりです。

1. Miracast 対応のデバイスまたはアダプターに接続してテレビで視聴する。
1. [Windows デバイス ポータルを使用](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)して PC で視聴する
1. Microsoft [HoloLens コンパニオン アプリを使用して](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) PC で視聴する。
1. [Microsoft Dynamics 365 リモート](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist)アシスト アプリを展開すると、フロント ラインのワーカーは、見た情報をリモートエキスパートにストリーミングできます。 リモートエキスパートは、第一線の作業員を口頭で、または自分の世界で注釈を付ける方法で案内できます。

> [!NOTE]
> Windows デバイス ポータルまたは Microsoft HoloLens コンパニオン アプリを介して表示される情報を共有するには、HoloLens が開発者モードである [必要があります](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。

### <a name="stream-video-with-miracast"></a>Miracast を使用してビデオをストリーミングする

Start ジェスチャを使用して [スタート] に **移動し**、接続アイコン **を選択** します。 表示されるピッカーから、接続する Miracast 対応デバイスまたはアダプターを選択します。

共有を停止するには、スタート ジェスチャを使用して、強調表示されている接続アイコン **を選択** します。 ストリーミングしていたので、デバイスには何も保存されません。

> [!NOTE]
> Miracast のサポートは [、Windows 10 2018 年 10](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)月の更新プログラムで始まる HoloLens (第 1 世代) で有効になっています。

### <a name="real-time-video-with-windows-device-portal"></a>Windows デバイス ポータルを使用したリアルタイム ビデオ

Windows デバイス ポータルを使用して共有するには、HoloLens で開発者モードを有効にする必要があります。開発者向けドキュメントの指示に従って開発者モードをセットアップし [、Windows デバイス ポータルを移動します](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。

### <a name="microsoft-hololens-companion-app"></a>Microsoft HoloLens コンパニオン アプリ

Microsoft HoloLens コンパニオン アプリを使用して共有するには、HoloLens で開発者モードを有効にする必要があります。開発者向けドキュメントの指示に従って開発者モード [を設定します](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。 次に [、Microsoft HoloLens](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) コンパニオン アプリをダウンロードし、アプリ内の指示に従って HoloLens に接続します。

HoloLens でアプリをセットアップしたら、アプリのメイン メニューから [ **ライブ** ストリーム] オプションを選択します。

## <a name="view-your-mixed-reality-photos-and-videos"></a>複合現実の写真とビデオを表示する

複合現実の写真とビデオは、デバイスの "カメラ ロール" に保存されます。 HoloLens 上のこのフォルダーの内容は、エクスプローラー アプリで参照できます ([ピクチャ] >ロール)。

HoloLens にプレインストールされているフォト アプリで、複合現実の写真やビデオを表示することもできます。 世界で写真をピン留めするには、[写真] アプリで写真を選択し、[混在世界に配置] **を選択します**。 写真を配置した後で、世界中の写真を移動できます。

HoloLens に接続された PC で複合現実の写真やビデオを表示および/または保存するには [、WINDOWS デバイス](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) ポータルまたは MTP 経由で PC の [エクスプローラーを使用できます](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)。

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>エクスプローラーを使用して画像、ビデオ、ファイルを取得する

他のモバイル デバイスと同様に、HoloLens を PC に接続してエクスプローラーを起動し、HoloLens ライブラリ (写真、ビデオ、ドキュメント) にアクセスして簡単に転送できます。 このメソッドは使いやすく、デバイス ポータルや Wi-Fi の使用は必要とされません。

1. デバイスのロックを解除します。
1. USB 経由でデバイスを PC に接続します。
1. エクスプローラーが PC で開きます。
1. ナビゲート: この PC\\*yourhololensname*\Internal Storage\Pictures\Camera Roll
1. 必要なファイルを PC にコピーします。

ヒント: 
- ファイルが表示されていない場合は、HoloLens にサインインしてデータへのアクセスを有効にしてください。
- 他のフォルダー内の他のファイル (診断ファイルなど) は [、Documents](hololens-diagnostic-logs.md#offline-diagnostics) フォルダーから取得できます。
- PC のエクスプローラーから [デバイスのプロパティ] を選択すると、Windows Holographic OS のバージョン番号 (ファームウェア バージョン)、デバイスシリアル番号、およびバッテリーの割合が表示されます。
- 組織が MDM を使用して [Connectivity/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) を無効にしている場合、デバイスに接続できません。

## <a name="share-your-mixed-reality-photos-and-videos"></a>複合現実の写真とビデオを共有する

複合現実の写真またはビデオをキャプチャすると、プレビューが表示されます。 プレビューの **上にある** 共有アイコンを選択して、共有アシスタントを表示します。 そこから、その写真またはビデオを共有する終了点を選択できます。

また、複合現実の写真とビデオを自動的にアップロードすることで、OneDrive から複合現実の写真やビデオを共有することもできます。 HoloLens で OneDrive アプリを開き、まだない場合は、 [個人用 Microsoft](https://account.microsoft.com) アカウントでサインインします。 設定アイコンを **選択し** 、[カメラのアップロード **] を選択します**。 カメラのアップロードを有効にする。 HoloLens でアプリを起動する度に、複合現実の写真とビデオが OneDrive にアップロードされます。

> [!NOTE]
> OneDrive でカメラアップロードを有効にできるのは、個人用 Microsoft アカウントで OneDrive にサインインしている場合のみです。 仕事用または学校用のアカウントで HoloLens を設定する場合は、OneDrive アプリに個人用 Microsoft アカウントを追加して、この機能を有効にできます。

## <a name="limitations-of-mixed-reality-capture"></a>複合現実キャプチャの制限

- 複合現実キャプチャを使用している間、HoloLens のフレームレートは 30 Hz に半減されます。
- 写真/ビデオ カメラが別のアプリケーションで既に使用されている場合、ライブ ストリーミング中、またはシステム リソースが低い場合は、写真やビデオの解像度が低下する可能性があります。

### <a name="maximum-recording-length"></a>最大記録長

Windows Holographic より前の HoloLens 2 デバイスでは、デバイスに記録されたバージョン 20H2 ビデオは、最大 5 分の長さに制限されました。

お客様からのフィードバックにより、複合現実キャプチャの記録長 [が長くなっています](holographic-photos-and-videos.md)。 複合現実キャプチャは既定で 5 分に制限されなくなりましたが、代わりに使用可能なディスク領域に基づいて最大記録長が計算されます。 デバイスは、使用可能なディスク領域に基づいて最大ビデオ録画時間を推定し、ディスク容量全体の最大 80% を占める。

> [!NOTE]
> HoloLens は、次のいずれかの場合、既定のビデオ録画の長さ (5 分) を使用します。
> - 推定最大記録時間は、既定の 5 分よりも短い値です。
> - 使用可能なディスク領域は、ディスク領域全体の 20% 未満です。

## <a name="default-file-format-and-resolution"></a>既定のファイル形式と解像度

### <a name="default-photo-format-and-resolution"></a>既定の写真の形式と解像度

|  デバイス  |  形式  |  拡張機能  |  解決方法  |
|----------|----------|----------|----------|
| HoloLens 2 | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens (第 1 世代) | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408x792px |

### <a name="recorded-video-format-and-resolution"></a>録画されたビデオの形式と解像度

| デバイス | 形式 | 拡張機能 | 解決方法 | 速度 | オーディオ |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30fps | 48kHz ステレオ |
| HoloLens (第 1 世代) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | 48kHz ステレオ |
