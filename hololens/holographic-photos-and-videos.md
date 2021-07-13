---
title: Mixed Reality の写真とビデオをキャプチャ、記録、共有する
description: 複合現実デバイスを使用して、Mixed Reality の写真とビデオをキャプチャ、記録、表示、およびHoloLensする方法について学習します。 データ ファイルまたは収集されたファイルをMiracastする方法について説明します。
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
ms.openlocfilehash: daced6fab65f779b7bd670bf1275f99ae5311d3f
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635961"
---
# <a name="create-mixed-reality-photos-and-videos"></a>Mixed Reality の写真とビデオを作成する

HoloLens、現実世界とデジタル世界を混在するエクスペリエンスをユーザーに提供します。  Mixed Reality Capture (MRC) を使用すると、そのエクスペリエンスを写真やビデオとしてキャプチャしたり、表示した情報を他のユーザーとリアルタイムで共有することができます。

Mixed Reality キャプチャでは、一人一人の視点を使用して、他のユーザーがホログラムを見るのを見るのを見る。 3 人目の視点の場合は [、spectator ビュー を使用します](/windows/mixed-reality/spectator-view)。 Spectator ビューは、デモに特に役立ちます。

友人や同僚の間でビデオを共有するのも楽しいのですが、ビデオは他のユーザーにアプリの使用やアプリやエクスペリエンスとの問題の伝達を教えるのに役立ちます。

> [!NOTE]
> Mixed Reality キャプチャ エクスペリエンスを起動できない場合に、HoloLensデバイスである場合は、システム管理者に確認してください。 カメラへのアクセスは、会社のポリシーを使用して制限できます。

## <a name="capture-a-mixed-reality-photo"></a>Mixed Reality 写真をキャプチャする

複合現実の写真を撮影するには、いくつかの方法HoloLens。ハードウェア ボタン、音声、またはデバイスを使用スタート メニュー。

### <a name="hardware-buttons-to-take-photos"></a>写真を撮影するハードウェア ボタン

現在のビューの簡単な写真を撮影するには、ボリュームの上下ボタンを同時に押します。  これは、スクリーンショットまたは印刷画面HoloLensバージョンに少し似たものになります。

- [HoloLens 2 上のボタンの場所](hololens2-hardware.md)
- [HoloLens (第 1 世代) のボタンの場所](hololens1-hardware.md#hololens-components)

> [!NOTE]
> 音量を **上げ、****音量を** 下げボタンを 3 秒間押すと、写真を撮影するのではなく、ビデオの記録が開始されます。 記録を停止するには、ボリュームアップボタン **と音量ダウン ボタン****の両方を** 同時にタップします。

### <a name="voice-commands-to-take-photos"></a>写真を撮影する音声コマンド

バージョン HoloLens 2 2004 (以降) では、"写真を撮る" と言います。

HoloLens (第 1 世代) または HoloLens 2 バージョン 1903 では、"Hey Cortana, take a picture" (写真を撮って) とします。

### <a name="start-menu-to-take-photos"></a>スタート メニュー写真を撮影する方法

[開始] ジェスチャを使用して [開始] **に移動し**、[カメラ] アイコン **を選択** します。

キャプチャする方向に頭を向け、エア タップ [で写真を](hololens2-basic-usage.md#touch-holograms-near-you) 撮影します。 引き続きエア タップを行い、追加の写真をキャプチャできます。 キャプチャした写真は、デバイスに保存されます。

写真のキャプチャを終了するには、もう一度開始ジェスチャを使用します。  

## <a name="capture-a-mixed-reality-video"></a>Mixed Reality ビデオをキャプチャする

複合現実のビデオをビデオ に記録するには、いくつかの方法HoloLens。ハードウェア ボタン、音声、またはデバイスを使用スタート メニュー。

### <a name="hardware-buttons-to-record-videos"></a>ビデオを記録するハードウェア ボタン

ビデオを記録する最も簡単な方法は、3秒のカウントダウンが始まるまで、音量を上げ、音量を下げボタンを同時に押し続けます。 記録を停止するには、両方のボタンを同時にタップします。

> [!NOTE]
> 音量を上 **げ、** 音量 **を下** げボタンを同時に押すと、ビデオを録画するのではなく、写真が撮影されます。

### <a name="voice-to-record-videos"></a>ビデオを記録する音声

バージョン HoloLens 2 2004 (以降) では、"記録の開始" と表示されます。 記録を停止するには、"記録を停止する" とします。

バージョン HoloLens (第 1 世代) または HoloLens 2 バージョン 1903 では、"Hey Cortana,start recording" と表示されます。 記録を停止するには、"Hey Cortana、記録を停止します。

### <a name="start-menu-to-record-videos"></a>スタート メニュービデオを記録する

[開始] ジェスチャを使用して [開始] **に移動し**、[ビデオ] アイコン **を選択** します。 キャプチャする方向に頭を向け、エア タップ [して記録を](hololens2-basic-usage.md#touch-holograms-near-you) 開始します。 3 秒のカウントダウンが行き、記録が開始されます。

記録を停止するには、[開始] ジェスチャを使用し、強調表示されている [ビデオ] アイコン **を選択** します。 ビデオがデバイスに保存されます。

> [!NOTE]
> **HoloLens (第 1 世代) にのみ適用されます**  
> この[Windows 10 October 2018 Update、(](/windows/mixed-reality/release-notes-october-2018)第 1 世代) の [開始] ジェスチャWindowsボタンの動作HoloLens変更されます。 更新の前に、[開始] ジェスチャまたは [Windows] ボタンをクリックすると、ビデオの記録が停止します。 ただし、更新後、[開始] ジェスチャまたは [Windows] ボタンをクリックすると、[スタート] メニュー (イマーシブ アプリの場合はクイック アクション メニュー)が開き、強調表示されているビデオ アイコンを選択して記録を停止できます。 

## <a name="share-what-you-see-in-real-time"></a>表示される情報をリアルタイムで共有する

友人や同僚とリアルタイムでHoloLens表示される情報を共有できます。 いくつかの方法を使用できます。

1. テレビで視聴Miracastデバイスまたはアダプターに接続する。
1. PC [Windows デバイス ポータル](/windows/mixed-reality/using-the-windows-device-portal)監視するアプリの使用
1. PC で[Microsoft HoloLensアプリを使用](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)して監視します。
1. このアプリ[Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist)展開すると、フロントエンド ワーカーは、見た目をリモートの専門家にストリーミングできます。 その後、リモートエキスパートは、フロント ライン ワーカーを逐語的に、または自分の世界で注釈を付け、ガイドすることができます。

> [!NOTE]
> アプリまたはコンパニオン アプリを使用Windows デバイス ポータルMicrosoft HoloLensを共有するには、開発者HoloLensモードである[必要があります](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。

### <a name="stream-video-with-miracast"></a>ビデオをストリーム配信Miracast

[開始] ジェスチャを使用して [開始]**に移動** し、次 **のConnectします**。 表示されたピッカーから、接続Miracast有効なデバイスまたはアダプターを選択します。

共有を停止するには、[開始] ジェスチャを使用し、強調表示されている [Connect **選択します**。 ストリーミングしていたため、デバイスには何も保存されません。

> [!NOTE]
> Miracast (第 1 世代) HoloLensで、サポートが有効[Windows 10 October 2018 Update。](/windows/mixed-reality/release-notes-october-2018)

### <a name="real-time-video-with-windows-device-portal"></a>リアルタイム ビデオとWindows デバイス ポータル

Windows デバイス ポータル を使用して共有するには、HoloLens で開発者モードを有効にする必要があるため、開発者向けドキュメントの手順に従って開発者モードを設定し、 に移動[Windows デバイス ポータル。](/windows/mixed-reality/using-the-windows-device-portal)

### <a name="microsoft-hololens-companion-app"></a>Microsoft HoloLensコンパニオン アプリ

Microsoft HoloLens コンパニオン アプリを使用して共有するには、HoloLens で開発者モードを有効にする必要があります。ため、開発者向けドキュメントの手順に従って開発者モード を[設定します](/windows/mixed-reality/using-the-windows-device-portal)。 次に、Microsoft HoloLens[アプリをダウンロードし](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)、アプリ内の指示に従ってアプリに接続HoloLens。

アプリが自分のアプリで設定HoloLens、アプリのメイン メニューから[ライブ ストリーム] オプションを選択します。

## <a name="view-your-mixed-reality-photos-and-videos"></a>Mixed Reality の写真とビデオを表示する

Mixed Reality の写真とビデオは、デバイスの "カメラ ロール" に保存されます。 このフォルダーの内容は、HoloLens アプリを使用してエクスプローラーできます ([カメラ ロール] の [ピクチャ] **>移動します**)。

また、Mixed Reality の写真やビデオは、アプリにプレインストールされているフォト アプリでHoloLens。 自分の世界で写真をピン留めするには、[フォト] アプリで写真を選択し、[Mixed World に **配置] を選択します**。 写真は、配置後に世界中に移動できます。

HoloLens に接続されている PC で Mixed Reality の写真やビデオを表示または保存するには、mtP を使用して[Windows デバイス ポータル](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)または PC の エクスプローラー[を使用できます](/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)。

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>画像エクスプローラーファイルを取得するには、次のコマンドを使用します。

他のモバイル デバイスと同様に、HoloLens を PC に接続して エクスプローラー を表示し、HoloLens ライブラリ (写真、ビデオ、ドキュメント) にアクセスして転送を容易にします。 この方法は簡単に使用できます。デバイス ポータルや Wi-Fi を使用する必要は一方ではありません。

1. デバイスのロックを解除します。
1. Connect USB 経由で PC にデバイスを接続します。
1. エクスプローラー PC で開きます。
1. 移動: この PC \\ *yourolensname*\Internal Storage\Pictures\Camera Roll
1. 必要なファイルを PC にコピーします。

ヒント:
- ファイルが表示されていない場合は、データへのアクセスを有効HoloLensにサインインしてください。
- 診断ファイルなど、他のフォルダー内の他の [ファイルは Documents](hololens-diagnostic-logs.md#offline-diagnostics) フォルダーから取得できます。
- PC エクスプローラーから[デバイスのプロパティ] を選択すると、Windows Holographic OS のバージョン番号 (ファームウェアのバージョン)、デバイスのシリアル番号、バッテリの割合が表示されます。
- 組織が MDM を使用して [接続/AllowUSBConnection](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) を無効にしている場合、デバイスに接続できません。

## <a name="share-your-mixed-reality-photos-and-videos"></a>Mixed Reality の写真とビデオを共有する

[Holographic Windowsバージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1)より前のバージョンでは、Mixed Reality の写真またはビデオをキャプチャした後、プレビューが表示されます。 プレビューの **上にある** [共有] アイコンを選択して、共有アシスタントを表示します。 そこから、その写真やビデオを共有するエンド ポイントを選択できます。

Holographic Windowsバージョン 21H1 では、Mixed Reality の写真またはビデオをキャプチャした後、プレビューが表示されます。 プレビューの **上にある** [共有] アイコンを選択して、共有アシスタントを表示します。 そこから、その写真やビデオを共有するエンド ポイント (メール、OneDrive など) を選択できます。 また、**設定-> システム-> 共有エクスペリエンス** に移動して、HoloLens を近くのデバイスと共有することもできます。 詳細については、「 [Windows 10 で近くのデバイスとの共有](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)」を参照してください。

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

|  デバイス  |  Format  |  拡張機能  |  解決策  |
|----------|----------|----------|----------|
| HoloLens 2 | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens (第 1 世代) | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408x792px |

### <a name="recorded-video-format-and-resolution"></a>記録されたビデオ形式と解像度

| デバイス | Format | 拡張機能 | 解決策 | 速度 | オーディオ |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30 fps | 48 Khz ステレオ |
| HoloLens (第 1 世代) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | 48 Khz ステレオ |
