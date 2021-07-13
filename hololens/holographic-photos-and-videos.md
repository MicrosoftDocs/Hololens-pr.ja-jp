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
# <a name="create-mixed-reality-photos-and-videos"></a><span data-ttu-id="d8742-105">Mixed Reality の写真とビデオを作成する</span><span class="sxs-lookup"><span data-stu-id="d8742-105">Create mixed reality photos and videos</span></span>

<span data-ttu-id="d8742-106">HoloLens、現実世界とデジタル世界を混在するエクスペリエンスをユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="d8742-106">HoloLens gives users the experience of mixing the real world with the digital world.</span></span>  <span data-ttu-id="d8742-107">Mixed Reality Capture (MRC) を使用すると、そのエクスペリエンスを写真やビデオとしてキャプチャしたり、表示した情報を他のユーザーとリアルタイムで共有することができます。</span><span class="sxs-lookup"><span data-stu-id="d8742-107">Mixed reality capture (MRC) lets you capture that experience as a photo or video, or share what you see with others in real-time.</span></span>

<span data-ttu-id="d8742-108">Mixed Reality キャプチャでは、一人一人の視点を使用して、他のユーザーがホログラムを見るのを見るのを見る。</span><span class="sxs-lookup"><span data-stu-id="d8742-108">Mixed reality capture uses a first-person point of view so other people can see holograms as you see them.</span></span> <span data-ttu-id="d8742-109">3 人目の視点の場合は [、spectator ビュー を使用します](/windows/mixed-reality/spectator-view)。</span><span class="sxs-lookup"><span data-stu-id="d8742-109">For a third-person point of view, use [spectator view](/windows/mixed-reality/spectator-view).</span></span> <span data-ttu-id="d8742-110">Spectator ビューは、デモに特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d8742-110">Spectator view is especially useful for demos.</span></span>

<span data-ttu-id="d8742-111">友人や同僚の間でビデオを共有するのも楽しいのですが、ビデオは他のユーザーにアプリの使用やアプリやエクスペリエンスとの問題の伝達を教えるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d8742-111">While it's fun to share videos amongst friends and colleagues, videos can also help teach other people to use an app or to communicate problems with apps and experiences.</span></span>

> [!NOTE]
> <span data-ttu-id="d8742-112">Mixed Reality キャプチャ エクスペリエンスを起動できない場合に、HoloLensデバイスである場合は、システム管理者に確認してください。</span><span class="sxs-lookup"><span data-stu-id="d8742-112">If you can't launch mixed reality capture experiences and your HoloLens is a work device, check with your system administrator.</span></span> <span data-ttu-id="d8742-113">カメラへのアクセスは、会社のポリシーを使用して制限できます。</span><span class="sxs-lookup"><span data-stu-id="d8742-113">Access to the camera can be restricted through company policy.</span></span>

## <a name="capture-a-mixed-reality-photo"></a><span data-ttu-id="d8742-114">Mixed Reality 写真をキャプチャする</span><span class="sxs-lookup"><span data-stu-id="d8742-114">Capture a mixed reality photo</span></span>

<span data-ttu-id="d8742-115">複合現実の写真を撮影するには、いくつかの方法HoloLens。ハードウェア ボタン、音声、またはデバイスを使用スタート メニュー。</span><span class="sxs-lookup"><span data-stu-id="d8742-115">There are several ways to take a photo of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <a name="hardware-buttons-to-take-photos"></a><span data-ttu-id="d8742-116">写真を撮影するハードウェア ボタン</span><span class="sxs-lookup"><span data-stu-id="d8742-116">Hardware buttons to take photos</span></span>

<span data-ttu-id="d8742-117">現在のビューの簡単な写真を撮影するには、ボリュームの上下ボタンを同時に押します。</span><span class="sxs-lookup"><span data-stu-id="d8742-117">To take a quick photo of your current view, press the volume up and volume down buttons at the same time.</span></span>  <span data-ttu-id="d8742-118">これは、スクリーンショットまたは印刷画面HoloLensバージョンに少し似たものになります。</span><span class="sxs-lookup"><span data-stu-id="d8742-118">This is a bit like the HoloLens version of a screenshot or print screen.</span></span>

- [<span data-ttu-id="d8742-119">HoloLens 2 上のボタンの場所</span><span class="sxs-lookup"><span data-stu-id="d8742-119">Button locations on HoloLens 2</span></span>](hololens2-hardware.md)
- [<span data-ttu-id="d8742-120">HoloLens (第 1 世代) のボタンの場所</span><span class="sxs-lookup"><span data-stu-id="d8742-120">Button locations on HoloLens (1st gen)</span></span>](hololens1-hardware.md#hololens-components)

> [!NOTE]
> <span data-ttu-id="d8742-121">音量を **上げ、\*\*\*\*音量を** 下げボタンを 3 秒間押すと、写真を撮影するのではなく、ビデオの記録が開始されます。</span><span class="sxs-lookup"><span data-stu-id="d8742-121">Holding the **volume up** and **volume down** buttons for three seconds will start recording a video rather than taking a photo.</span></span> <span data-ttu-id="d8742-122">記録を停止するには、ボリュームアップボタン **と音量ダウン ボタン\*\*\*\*の両方を** 同時にタップします。</span><span class="sxs-lookup"><span data-stu-id="d8742-122">To stop recording, tap both **volume up** and **volume down** buttons simultaneously.</span></span>

### <a name="voice-commands-to-take-photos"></a><span data-ttu-id="d8742-123">写真を撮影する音声コマンド</span><span class="sxs-lookup"><span data-stu-id="d8742-123">Voice commands to take photos</span></span>

<span data-ttu-id="d8742-124">バージョン HoloLens 2 2004 (以降) では、"写真を撮る" と言います。</span><span class="sxs-lookup"><span data-stu-id="d8742-124">On HoloLens 2, version 2004 (and later), say: "Take a picture."</span></span>

<span data-ttu-id="d8742-125">HoloLens (第 1 世代) または HoloLens 2 バージョン 1903 では、"Hey Cortana, take a picture" (写真を撮って) とします。</span><span class="sxs-lookup"><span data-stu-id="d8742-125">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, take a picture."</span></span>

### <a name="start-menu-to-take-photos"></a><span data-ttu-id="d8742-126">スタート メニュー写真を撮影する方法</span><span class="sxs-lookup"><span data-stu-id="d8742-126">Start menu to take photos</span></span>

<span data-ttu-id="d8742-127">[開始] ジェスチャを使用して [開始] **に移動し**、[カメラ] アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="d8742-127">Use the Start gesture to go to **Start**, then select the **Camera** icon.</span></span>

<span data-ttu-id="d8742-128">キャプチャする方向に頭を向け、エア タップ [で写真を](hololens2-basic-usage.md#touch-holograms-near-you) 撮影します。</span><span class="sxs-lookup"><span data-stu-id="d8742-128">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to take a photo.</span></span> <span data-ttu-id="d8742-129">引き続きエア タップを行い、追加の写真をキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="d8742-129">You can continue to air tap and capture additional photos.</span></span> <span data-ttu-id="d8742-130">キャプチャした写真は、デバイスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="d8742-130">Any photos you capture will be saved to your device.</span></span>

<span data-ttu-id="d8742-131">写真のキャプチャを終了するには、もう一度開始ジェスチャを使用します。</span><span class="sxs-lookup"><span data-stu-id="d8742-131">Use the Start gesture again to end photo capture.</span></span>  

## <a name="capture-a-mixed-reality-video"></a><span data-ttu-id="d8742-132">Mixed Reality ビデオをキャプチャする</span><span class="sxs-lookup"><span data-stu-id="d8742-132">Capture a mixed reality video</span></span>

<span data-ttu-id="d8742-133">複合現実のビデオをビデオ に記録するには、いくつかの方法HoloLens。ハードウェア ボタン、音声、またはデバイスを使用スタート メニュー。</span><span class="sxs-lookup"><span data-stu-id="d8742-133">There are several ways to record a video of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <a name="hardware-buttons-to-record-videos"></a><span data-ttu-id="d8742-134">ビデオを記録するハードウェア ボタン</span><span class="sxs-lookup"><span data-stu-id="d8742-134">Hardware buttons to record videos</span></span>

<span data-ttu-id="d8742-135">ビデオを記録する最も簡単な方法は、3秒のカウントダウンが始まるまで、音量を上げ、音量を下げボタンを同時に押し続けます。</span><span class="sxs-lookup"><span data-stu-id="d8742-135">The quickest way to record a video is to press and hold the **volume up** and **volume down** buttons simultaneously until a three-second countdown begins.</span></span> <span data-ttu-id="d8742-136">記録を停止するには、両方のボタンを同時にタップします。</span><span class="sxs-lookup"><span data-stu-id="d8742-136">To stop recording, tap both buttons simultaneously.</span></span>

> [!NOTE]
> <span data-ttu-id="d8742-137">音量を上 **げ、** 音量 **を下** げボタンを同時に押すと、ビデオを録画するのではなく、写真が撮影されます。</span><span class="sxs-lookup"><span data-stu-id="d8742-137">Quickly pressing the **volume up** and **volume down** buttons at the same time will take a photo rather than recording a video.</span></span>

### <a name="voice-to-record-videos"></a><span data-ttu-id="d8742-138">ビデオを記録する音声</span><span class="sxs-lookup"><span data-stu-id="d8742-138">Voice to record videos</span></span>

<span data-ttu-id="d8742-139">バージョン HoloLens 2 2004 (以降) では、"記録の開始" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8742-139">On HoloLens 2, version 2004 (and later), say: "Start recording."</span></span> <span data-ttu-id="d8742-140">記録を停止するには、"記録を停止する" とします。</span><span class="sxs-lookup"><span data-stu-id="d8742-140">To stop recording, say "Stop recording."</span></span>

<span data-ttu-id="d8742-141">バージョン HoloLens (第 1 世代) または HoloLens 2 バージョン 1903 では、"Hey Cortana,start recording" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8742-141">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, start recording."</span></span> <span data-ttu-id="d8742-142">記録を停止するには、"Hey Cortana、記録を停止します。</span><span class="sxs-lookup"><span data-stu-id="d8742-142">To stop recording, say "Hey Cortana, stop recording."</span></span>

### <a name="start-menu-to-record-videos"></a><span data-ttu-id="d8742-143">スタート メニュービデオを記録する</span><span class="sxs-lookup"><span data-stu-id="d8742-143">Start menu to record videos</span></span>

<span data-ttu-id="d8742-144">[開始] ジェスチャを使用して [開始] **に移動し**、[ビデオ] アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="d8742-144">Use the Start gesture to go to **Start**, then select the **Video** icon.</span></span> <span data-ttu-id="d8742-145">キャプチャする方向に頭を向け、エア タップ [して記録を](hololens2-basic-usage.md#touch-holograms-near-you) 開始します。</span><span class="sxs-lookup"><span data-stu-id="d8742-145">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to start recording.</span></span> <span data-ttu-id="d8742-146">3 秒のカウントダウンが行き、記録が開始されます。</span><span class="sxs-lookup"><span data-stu-id="d8742-146">There will be a three second countdown and your recording will begin.</span></span>

<span data-ttu-id="d8742-147">記録を停止するには、[開始] ジェスチャを使用し、強調表示されている [ビデオ] アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="d8742-147">To stop recording, use the Start gesture and select the highlighted **Video** icon.</span></span> <span data-ttu-id="d8742-148">ビデオがデバイスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="d8742-148">The video will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="d8742-149">**HoloLens (第 1 世代) にのみ適用されます**</span><span class="sxs-lookup"><span data-stu-id="d8742-149">**Applies to HoloLens (1st gen) only**</span></span>  
> <span data-ttu-id="d8742-150">この[Windows 10 October 2018 Update、(](/windows/mixed-reality/release-notes-october-2018)第 1 世代) の [開始] ジェスチャWindowsボタンの動作HoloLens変更されます。</span><span class="sxs-lookup"><span data-stu-id="d8742-150">The [Windows 10 October 2018 Update](/windows/mixed-reality/release-notes-october-2018) changes how the Start gesture and Windows button behave on HoloLens (1st gen).</span></span> <span data-ttu-id="d8742-151">更新の前に、[開始] ジェスチャまたは [Windows] ボタンをクリックすると、ビデオの記録が停止します。</span><span class="sxs-lookup"><span data-stu-id="d8742-151">Before the update, the Start gesture or Windows button would stop a video recording.</span></span> <span data-ttu-id="d8742-152">ただし、更新後、[開始] ジェスチャまたは [Windows] ボタンをクリックすると、[スタート] メニュー (イマーシブ アプリの場合はクイック アクション メニュー)が開き、強調表示されているビデオ アイコンを選択して記録を停止できます。 </span><span class="sxs-lookup"><span data-stu-id="d8742-152">After the update, however, the Start gesture or Windows button opens the **Start** menu (or the **quick actions menu** if you are in an immersive app), from which you can select the highlighted **video** icon to stop recording.</span></span>

## <a name="share-what-you-see-in-real-time"></a><span data-ttu-id="d8742-153">表示される情報をリアルタイムで共有する</span><span class="sxs-lookup"><span data-stu-id="d8742-153">Share what you see in real-time</span></span>

<span data-ttu-id="d8742-154">友人や同僚とリアルタイムでHoloLens表示される情報を共有できます。</span><span class="sxs-lookup"><span data-stu-id="d8742-154">You can share what you see in HoloLens with friends and colleagues in real-time.</span></span> <span data-ttu-id="d8742-155">いくつかの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d8742-155">There are a few methods available:</span></span>

1. <span data-ttu-id="d8742-156">テレビで視聴Miracastデバイスまたはアダプターに接続する。</span><span class="sxs-lookup"><span data-stu-id="d8742-156">Connecting to a Miracast-enabled device or adapter to watch on a TV.</span></span>
1. <span data-ttu-id="d8742-157">PC [Windows デバイス ポータル](/windows/mixed-reality/using-the-windows-device-portal)監視するアプリの使用</span><span class="sxs-lookup"><span data-stu-id="d8742-157">Using [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal) to watch on a PC</span></span>
1. <span data-ttu-id="d8742-158">PC で[Microsoft HoloLensアプリを使用](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)して監視します。</span><span class="sxs-lookup"><span data-stu-id="d8742-158">Using the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) to watch on a PC.</span></span>
1. <span data-ttu-id="d8742-159">このアプリ[Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist)展開すると、フロントエンド ワーカーは、見た目をリモートの専門家にストリーミングできます。</span><span class="sxs-lookup"><span data-stu-id="d8742-159">Deploying the [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) app, which enables front-line workers to stream what they see to a remote expert.</span></span> <span data-ttu-id="d8742-160">その後、リモートエキスパートは、フロント ライン ワーカーを逐語的に、または自分の世界で注釈を付け、ガイドすることができます。</span><span class="sxs-lookup"><span data-stu-id="d8742-160">The remote expert can then guide the front-line worker verbally or by annotating in their world.</span></span>

> [!NOTE]
> <span data-ttu-id="d8742-161">アプリまたはコンパニオン アプリを使用Windows デバイス ポータルMicrosoft HoloLensを共有するには、開発者HoloLensモードである[必要があります](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="d8742-161">Sharing what you see via Windows Device Portal or Microsoft HoloLens companion app requires your HoloLens to be in [Developer mode](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal).</span></span>

### <a name="stream-video-with-miracast"></a><span data-ttu-id="d8742-162">ビデオをストリーム配信Miracast</span><span class="sxs-lookup"><span data-stu-id="d8742-162">Stream video with Miracast</span></span>

<span data-ttu-id="d8742-163">[開始] ジェスチャを使用して [開始]**に移動** し、次 **のConnectします**。</span><span class="sxs-lookup"><span data-stu-id="d8742-163">Use the Start gesture to go to **Start**, then select the **Connect** icon.</span></span> <span data-ttu-id="d8742-164">表示されたピッカーから、接続Miracast有効なデバイスまたはアダプターを選択します。</span><span class="sxs-lookup"><span data-stu-id="d8742-164">From the picker that appears, select the Miracast-enabled device or adapter to which you want to connect.</span></span>

<span data-ttu-id="d8742-165">共有を停止するには、[開始] ジェスチャを使用し、強調表示されている [Connect **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d8742-165">To stop sharing, use the Start gesture and select the highlighted **Connect** icon.</span></span> <span data-ttu-id="d8742-166">ストリーミングしていたため、デバイスには何も保存されません。</span><span class="sxs-lookup"><span data-stu-id="d8742-166">Because you were streaming, nothing will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="d8742-167">Miracast (第 1 世代) HoloLensで、サポートが有効[Windows 10 October 2018 Update。](/windows/mixed-reality/release-notes-october-2018)</span><span class="sxs-lookup"><span data-stu-id="d8742-167">Miracast support was enabled on HoloLens (1st gen) beginning with the [Windows 10 October 2018 Update](/windows/mixed-reality/release-notes-october-2018).</span></span>

### <a name="real-time-video-with-windows-device-portal"></a><span data-ttu-id="d8742-168">リアルタイム ビデオとWindows デバイス ポータル</span><span class="sxs-lookup"><span data-stu-id="d8742-168">Real time video with Windows Device Portal</span></span>

<span data-ttu-id="d8742-169">Windows デバイス ポータル を使用して共有するには、HoloLens で開発者モードを有効にする必要があるため、開発者向けドキュメントの手順に従って開発者モードを設定し、 に移動[Windows デバイス ポータル。](/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="d8742-169">Because sharing via Windows Device Portal requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode and navigate Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span>

### <a name="microsoft-hololens-companion-app"></a><span data-ttu-id="d8742-170">Microsoft HoloLensコンパニオン アプリ</span><span class="sxs-lookup"><span data-stu-id="d8742-170">Microsoft HoloLens companion app</span></span>

<span data-ttu-id="d8742-171">Microsoft HoloLens コンパニオン アプリを使用して共有するには、HoloLens で開発者モードを有効にする必要があります。ため、開発者向けドキュメントの手順に従って開発者モード を[設定します](/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="d8742-171">Because sharing via the Microsoft HoloLens companion app requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode](/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="d8742-172">次に、Microsoft HoloLens[アプリをダウンロードし](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)、アプリ内の指示に従ってアプリに接続HoloLens。</span><span class="sxs-lookup"><span data-stu-id="d8742-172">Then, download the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) and follow the instructions within the app to connect to your HoloLens.</span></span>

<span data-ttu-id="d8742-173">アプリが自分のアプリで設定HoloLens、アプリのメイン メニューから[ライブ ストリーム] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d8742-173">Once the app is set up with your HoloLens, select the **Live stream** option from the app's main menu.</span></span>

## <a name="view-your-mixed-reality-photos-and-videos"></a><span data-ttu-id="d8742-174">Mixed Reality の写真とビデオを表示する</span><span class="sxs-lookup"><span data-stu-id="d8742-174">View your mixed reality photos and videos</span></span>

<span data-ttu-id="d8742-175">Mixed Reality の写真とビデオは、デバイスの "カメラ ロール" に保存されます。</span><span class="sxs-lookup"><span data-stu-id="d8742-175">Mixed reality photos and videos are saved to the device's "Camera Roll".</span></span> <span data-ttu-id="d8742-176">このフォルダーの内容は、HoloLens アプリを使用してエクスプローラーできます ([カメラ ロール] の [ピクチャ] **>移動します**)。</span><span class="sxs-lookup"><span data-stu-id="d8742-176">You can browse the contents of this folder on your HoloLens with the File Explorer app (navigate to **Pictures > Camera Roll**).</span></span>

<span data-ttu-id="d8742-177">また、Mixed Reality の写真やビデオは、アプリにプレインストールされているフォト アプリでHoloLens。</span><span class="sxs-lookup"><span data-stu-id="d8742-177">You can also view your mixed reality photos and videos in the Photos app, which is pre-installed on HoloLens.</span></span> <span data-ttu-id="d8742-178">自分の世界で写真をピン留めするには、[フォト] アプリで写真を選択し、[Mixed World に **配置] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d8742-178">To pin a photo in your world, select it in the Photos app and choose **Place in mixed world**.</span></span> <span data-ttu-id="d8742-179">写真は、配置後に世界中に移動できます。</span><span class="sxs-lookup"><span data-stu-id="d8742-179">You can move the photo around your world after it's been placed.</span></span>

<span data-ttu-id="d8742-180">HoloLens に接続されている PC で Mixed Reality の写真やビデオを表示または保存するには、mtP を使用して[Windows デバイス ポータル](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)または PC の エクスプローラー[を使用できます](/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="d8742-180">To view and/or save your mixed reality photos and videos on a PC connected to HoloLens, you can use [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) or your [PC's File Explorer via MTP](/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens).</span></span>

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a><span data-ttu-id="d8742-181">画像エクスプローラーファイルを取得するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d8742-181">Use File Explorer to get your pictures, videos and files</span></span>

<span data-ttu-id="d8742-182">他のモバイル デバイスと同様に、HoloLens を PC に接続して エクスプローラー を表示し、HoloLens ライブラリ (写真、ビデオ、ドキュメント) にアクセスして転送を容易にします。</span><span class="sxs-lookup"><span data-stu-id="d8742-182">Similar to other mobile devices, connect your HoloLens to your PC to bring up File Explorer to access your HoloLens libraries (photos, videos, documents) for easy transfer.</span></span> <span data-ttu-id="d8742-183">この方法は簡単に使用できます。デバイス ポータルや Wi-Fi を使用する必要は一方ではありません。</span><span class="sxs-lookup"><span data-stu-id="d8742-183">This method is easy to use and does not require the use of device portal or Wi-Fi.</span></span>

1. <span data-ttu-id="d8742-184">デバイスのロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="d8742-184">Unlock the device.</span></span>
1. <span data-ttu-id="d8742-185">Connect USB 経由で PC にデバイスを接続します。</span><span class="sxs-lookup"><span data-stu-id="d8742-185">Connect the device to a PC via USB.</span></span>
1. <span data-ttu-id="d8742-186">エクスプローラー PC で開きます。</span><span class="sxs-lookup"><span data-stu-id="d8742-186">File Explorer should open on your PC.</span></span>
1. <span data-ttu-id="d8742-187">移動: この PC \\ *yourolensname*\Internal Storage\Pictures\Camera Roll</span><span class="sxs-lookup"><span data-stu-id="d8742-187">Navigate to: This PC\\*yourhololensname*\Internal Storage\Pictures\Camera Roll</span></span>
1. <span data-ttu-id="d8742-188">必要なファイルを PC にコピーします。</span><span class="sxs-lookup"><span data-stu-id="d8742-188">Copy whatever files you need to your PC.</span></span>

<span data-ttu-id="d8742-189">ヒント:</span><span class="sxs-lookup"><span data-stu-id="d8742-189">Tips:</span></span>
- <span data-ttu-id="d8742-190">ファイルが表示されていない場合は、データへのアクセスを有効HoloLensにサインインしてください。</span><span class="sxs-lookup"><span data-stu-id="d8742-190">If you don't see any files, please ensure you sign in to your HoloLens to enable access to your data.</span></span>
- <span data-ttu-id="d8742-191">診断ファイルなど、他のフォルダー内の他の [ファイルは Documents](hololens-diagnostic-logs.md#offline-diagnostics) フォルダーから取得できます。</span><span class="sxs-lookup"><span data-stu-id="d8742-191">You can get other files in other folders, such as [diagnostics files](hololens-diagnostic-logs.md#offline-diagnostics) from the Documents folder.</span></span>
- <span data-ttu-id="d8742-192">PC エクスプローラーから[デバイスのプロパティ] を選択すると、Windows Holographic OS のバージョン番号 (ファームウェアのバージョン)、デバイスのシリアル番号、バッテリの割合が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8742-192">From File Explorer on your PC, you can select Device properties to see Windows Holographic OS version number (firmware version), device serial number, and battery percentage.</span></span>
- <span data-ttu-id="d8742-193">組織が MDM を使用して [接続/AllowUSBConnection](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) を無効にしている場合、デバイスに接続できません。</span><span class="sxs-lookup"><span data-stu-id="d8742-193">If your Organization has used MDM to disable [Connectivity/AllowUSBConnection](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) then you will be unable to connect to your device.</span></span>

## <a name="share-your-mixed-reality-photos-and-videos"></a><span data-ttu-id="d8742-194">Mixed Reality の写真とビデオを共有する</span><span class="sxs-lookup"><span data-stu-id="d8742-194">Share your mixed reality photos and videos</span></span>

<span data-ttu-id="d8742-195">[Holographic Windowsバージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1)より前のバージョンでは、Mixed Reality の写真またはビデオをキャプチャした後、プレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8742-195">Prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), after capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="d8742-196">プレビューの **上にある** [共有] アイコンを選択して、共有アシスタントを表示します。</span><span class="sxs-lookup"><span data-stu-id="d8742-196">Select the **Share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="d8742-197">そこから、その写真やビデオを共有するエンド ポイントを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d8742-197">From there, you can select the end point to which you'd like to share that photo or video.</span></span>

<span data-ttu-id="d8742-198">Holographic Windowsバージョン 21H1 では、Mixed Reality の写真またはビデオをキャプチャした後、プレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8742-198">With Windows Holographic, version 21H1, after capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="d8742-199">プレビューの **上にある** [共有] アイコンを選択して、共有アシスタントを表示します。</span><span class="sxs-lookup"><span data-stu-id="d8742-199">Select the **Share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="d8742-200">そこから、その写真やビデオを共有するエンド ポイント (メール、OneDrive など) を選択できます。</span><span class="sxs-lookup"><span data-stu-id="d8742-200">From there, you can select the end point (Mail, OneDrive, etc.) to which you'd like to share that photo or video.</span></span> <span data-ttu-id="d8742-201">また、**設定-> システム-> 共有エクスペリエンス** に移動して、HoloLens を近くのデバイスと共有することもできます。</span><span class="sxs-lookup"><span data-stu-id="d8742-201">You can also enable your HoloLens to share with nearby devices by going to **Settings -> System -> Shared Experiences**.</span></span> <span data-ttu-id="d8742-202">詳細については、「 [Windows 10 で近くのデバイスとの共有](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8742-202">For more details, read [Share things with nearby devices in Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).</span></span>

> [!TIP] 
> <span data-ttu-id="d8742-203">また、混在している現実の写真やビデオを自動的にアップロードすることで、OneDrive から mixed reality の写真やビデオを共有することもできます。</span><span class="sxs-lookup"><span data-stu-id="d8742-203">You can also share mixed reality photos and videos from OneDrive by automatically uploading your mixed reality photos and videos.</span></span> <span data-ttu-id="d8742-204">HoloLens で OneDrive アプリを開き、**個人用 [Microsoft アカウント](https://account.microsoft.com)** でサインインします (まだインストールしていない場合)。</span><span class="sxs-lookup"><span data-stu-id="d8742-204">Open the OneDrive app on HoloLens and sign in with a **personal [Microsoft account](https://account.microsoft.com)**, if you haven't already.</span></span> <span data-ttu-id="d8742-205">**設定** アイコンを選択し、[**カメラのアップロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8742-205">Select the **Settings** icon and choose **Camera upload**.</span></span> <span data-ttu-id="d8742-206">カメラのアップロードを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d8742-206">Turn Camera upload on.</span></span> <span data-ttu-id="d8742-207">これで、HoloLens でアプリを起動するたびに、mixed reality の写真とビデオが OneDrive にアップロードされるようになります。</span><span class="sxs-lookup"><span data-stu-id="d8742-207">Your mixed reality photos and videos will now be uploaded to OneDrive each time you launch the app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="d8742-208">個人用 Microsoft アカウントで OneDrive にサインインしている場合にのみ、OneDrive でカメラのアップロードを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d8742-208">You can only enable camera upload in OneDrive if you’re signed into OneDrive with a personal Microsoft account.</span></span> <span data-ttu-id="d8742-209">職場または学校のアカウントを使用して HoloLens を設定した場合は、OneDrive アプリに個人用 Microsoft アカウントを追加して、この機能を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d8742-209">If you set up HoloLens with a work or school account, you can add a personal Microsoft account in the OneDrive app to enable this feature.</span></span>

## <a name="limitations-of-mixed-reality-capture"></a><span data-ttu-id="d8742-210">Mixed reality キャプチャの制限事項</span><span class="sxs-lookup"><span data-stu-id="d8742-210">Limitations of mixed reality capture</span></span>

- <span data-ttu-id="d8742-211">混合 reality キャプチャを使用している間、HoloLens のフレームレートは半分から 30 Hz になります。</span><span class="sxs-lookup"><span data-stu-id="d8742-211">While using mixed reality capture, the frame rate of HoloLens will be halved to 30 Hz.</span></span>
- <span data-ttu-id="d8742-212">写真/ビデオカメラが既に別のアプリケーションによって使用されている場合、ライブストリーミング中、またはシステムリソースが少ない場合は、写真やビデオの解像度が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d8742-212">The resolution of photos and videos may be reduced if the photo/video camera is already in use by another application, while live streaming, or when system resources are low.</span></span>

### <a name="maximum-recording-length"></a><span data-ttu-id="d8742-213">最大記録長</span><span class="sxs-lookup"><span data-stu-id="d8742-213">Maximum recording length</span></span>

<span data-ttu-id="d8742-214">Windows Holographic、バージョン20h2 より前のデバイス HoloLens 2 では、デバイスに記録されたビデオは、最大長の5分に制限されていました。</span><span class="sxs-lookup"><span data-stu-id="d8742-214">On HoloLens 2 devices before the Windows Holographic, version 20H2, videos recorded on the device were limited to maximum length of five minutes.</span></span>

<span data-ttu-id="d8742-215">お客様からのフィードバックにより、 [混合現実のキャプチャ](holographic-photos-and-videos.md)の記録長さが増加しています。</span><span class="sxs-lookup"><span data-stu-id="d8742-215">Due to customer feedback, we’ve increased the recording length of [mixed reality captures](holographic-photos-and-videos.md).</span></span> <span data-ttu-id="d8742-216">混合の現実のキャプチャは、既定では5分に制限されなくなりましたが、代わりに使用可能なディスク領域に基づいて最大記録長が計算されます。</span><span class="sxs-lookup"><span data-stu-id="d8742-216">Mixed reality captures will no longer be limited to 5 minutes by default, but instead will calculate the maximum recording length based on available disk space.</span></span> <span data-ttu-id="d8742-217">デバイスは、ディスクの空き領域の最大80% まで、使用可能なディスク領域に基づいて、最大ビデオ記録期間を見積もります。</span><span class="sxs-lookup"><span data-stu-id="d8742-217">The device will estimate the max video recording duration based on available disk space up to 80% of the total disk space.</span></span>

> [!NOTE]
> <span data-ttu-id="d8742-218">次のいずれかが発生した場合、HoloLens は既定のビデオ記録の長さ (5 分) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d8742-218">The HoloLens will use default video recording length (5 minutes) if one of the following occurs:</span></span>
> - <span data-ttu-id="d8742-219">推定最大記録期間は、既定の5分よりも小さくなっています。</span><span class="sxs-lookup"><span data-stu-id="d8742-219">The estimated max recording duration is smaller than the default 5 mins.</span></span>
> - <span data-ttu-id="d8742-220">使用可能なディスク領域が、合計ディスク領域の20% 未満です。</span><span class="sxs-lookup"><span data-stu-id="d8742-220">The available disk space is less than 20% of the total disk space.</span></span>

## <a name="default-file-format-and-resolution"></a><span data-ttu-id="d8742-221">既定のファイル形式と解決方法</span><span class="sxs-lookup"><span data-stu-id="d8742-221">Default file format and resolution</span></span>

### <a name="default-photo-format-and-resolution"></a><span data-ttu-id="d8742-222">既定の写真の形式と解像度</span><span class="sxs-lookup"><span data-stu-id="d8742-222">Default photo format and resolution</span></span>

|  <span data-ttu-id="d8742-223">デバイス</span><span class="sxs-lookup"><span data-stu-id="d8742-223">Device</span></span>  |  <span data-ttu-id="d8742-224">Format</span><span class="sxs-lookup"><span data-stu-id="d8742-224">Format</span></span>  |  <span data-ttu-id="d8742-225">拡張機能</span><span class="sxs-lookup"><span data-stu-id="d8742-225">Extension</span></span>  |  <span data-ttu-id="d8742-226">解決策</span><span class="sxs-lookup"><span data-stu-id="d8742-226">Resolution</span></span>  |
|----------|----------|----------|----------|
| <span data-ttu-id="d8742-227">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="d8742-227">HoloLens 2</span></span> | [<span data-ttu-id="d8742-228">JPEG</span><span class="sxs-lookup"><span data-stu-id="d8742-228">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="d8742-229">.jpg</span><span class="sxs-lookup"><span data-stu-id="d8742-229">.jpg</span></span> | <span data-ttu-id="d8742-230">3904x2196px</span><span class="sxs-lookup"><span data-stu-id="d8742-230">3904x2196px</span></span> |
| <span data-ttu-id="d8742-231">HoloLens (第 1 世代)</span><span class="sxs-lookup"><span data-stu-id="d8742-231">HoloLens (1st gen)</span></span> | [<span data-ttu-id="d8742-232">JPEG</span><span class="sxs-lookup"><span data-stu-id="d8742-232">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="d8742-233">.jpg</span><span class="sxs-lookup"><span data-stu-id="d8742-233">.jpg</span></span> | <span data-ttu-id="d8742-234">1408x792px</span><span class="sxs-lookup"><span data-stu-id="d8742-234">1408x792px</span></span> |

### <a name="recorded-video-format-and-resolution"></a><span data-ttu-id="d8742-235">記録されたビデオ形式と解像度</span><span class="sxs-lookup"><span data-stu-id="d8742-235">Recorded video format and resolution</span></span>

| <span data-ttu-id="d8742-236">デバイス</span><span class="sxs-lookup"><span data-stu-id="d8742-236">Device</span></span> | <span data-ttu-id="d8742-237">Format</span><span class="sxs-lookup"><span data-stu-id="d8742-237">Format</span></span> | <span data-ttu-id="d8742-238">拡張機能</span><span class="sxs-lookup"><span data-stu-id="d8742-238">Extension</span></span> | <span data-ttu-id="d8742-239">解決策</span><span class="sxs-lookup"><span data-stu-id="d8742-239">Resolution</span></span> | <span data-ttu-id="d8742-240">速度</span><span class="sxs-lookup"><span data-stu-id="d8742-240">Speed</span></span> | <span data-ttu-id="d8742-241">オーディオ</span><span class="sxs-lookup"><span data-stu-id="d8742-241">Audio</span></span> |
|----------|----------|----------|----------|----------|----------|
| <span data-ttu-id="d8742-242">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="d8742-242">HoloLens 2</span></span> | [<span data-ttu-id="d8742-243">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="d8742-243">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="d8742-244">.mp4</span><span class="sxs-lookup"><span data-stu-id="d8742-244">.mp4</span></span> | <span data-ttu-id="d8742-245">1920x1080px</span><span class="sxs-lookup"><span data-stu-id="d8742-245">1920x1080px</span></span> | <span data-ttu-id="d8742-246">30 fps</span><span class="sxs-lookup"><span data-stu-id="d8742-246">30fps</span></span> | <span data-ttu-id="d8742-247">48 Khz ステレオ</span><span class="sxs-lookup"><span data-stu-id="d8742-247">48kHz Stereo</span></span> |
| <span data-ttu-id="d8742-248">HoloLens (第 1 世代)</span><span class="sxs-lookup"><span data-stu-id="d8742-248">HoloLens (1st gen)</span></span> |  [<span data-ttu-id="d8742-249">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="d8742-249">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="d8742-250">.mp4</span><span class="sxs-lookup"><span data-stu-id="d8742-250">.mp4</span></span> | <span data-ttu-id="d8742-251">1216x684px</span><span class="sxs-lookup"><span data-stu-id="d8742-251">1216x684px</span></span> | <span data-ttu-id="d8742-252">24fps</span><span class="sxs-lookup"><span data-stu-id="d8742-252">24fps</span></span> | <span data-ttu-id="d8742-253">48 Khz ステレオ</span><span class="sxs-lookup"><span data-stu-id="d8742-253">48kHz Stereo</span></span> |
