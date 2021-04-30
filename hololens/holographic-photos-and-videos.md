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
# <a name="create-mixed-reality-photos-and-videos"></a><span data-ttu-id="4c921-105">Mixed reality の写真とビデオを作成する</span><span class="sxs-lookup"><span data-stu-id="4c921-105">Create mixed reality photos and videos</span></span>

<span data-ttu-id="4c921-106">HoloLens を使用すると、ユーザーは世界とデジタルの世界を混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="4c921-106">HoloLens gives users the experience of mixing the real world with the digital world.</span></span>  <span data-ttu-id="4c921-107">Mixed reality キャプチャ (MRC) を使用すると、そのエクスペリエンスを写真やビデオとしてキャプチャしたり、他のユーザーとリアルタイムで表示したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="4c921-107">Mixed reality capture (MRC) lets you capture that experience as a photo or video, or share what you see with others in real-time.</span></span>

<span data-ttu-id="4c921-108">Mixed reality capture では、最初の人の視点を使用して、他のユーザーが表示されているホログラムを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="4c921-108">Mixed reality capture uses a first-person point of view so other people can see holograms as you see them.</span></span> <span data-ttu-id="4c921-109">3人の観点では、 [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view)を使用します。</span><span class="sxs-lookup"><span data-stu-id="4c921-109">For a third-person point of view, use [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view).</span></span> <span data-ttu-id="4c921-110">Spectator view は、デモに特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4c921-110">Spectator view is especially useful for demos.</span></span>

<span data-ttu-id="4c921-111">友人や同僚とビデオを共有することは楽しいですが、ビデオも、他の人がアプリを使用したり、アプリやエクスペリエンスに関する問題を伝えたりするのにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4c921-111">While it's fun to share videos amongst friends and colleagues, videos can also help teach other people to use an app or to communicate problems with apps and experiences.</span></span>

> [!NOTE]
> <span data-ttu-id="4c921-112">Mixed reality のキャプチャエクスペリエンスを起動できず、HoloLens が仕事用デバイスの場合は、システム管理者に確認してください。</span><span class="sxs-lookup"><span data-stu-id="4c921-112">If you can't launch mixed reality capture experiences and your HoloLens is a work device, check with your system administrator.</span></span> <span data-ttu-id="4c921-113">カメラへのアクセスは、会社のポリシーによって制限できます。</span><span class="sxs-lookup"><span data-stu-id="4c921-113">Access to the camera can be restricted through company policy.</span></span>

## <a name="capture-a-mixed-reality-photo"></a><span data-ttu-id="4c921-114">Mixed reality の写真をキャプチャする</span><span class="sxs-lookup"><span data-stu-id="4c921-114">Capture a mixed reality photo</span></span>

<span data-ttu-id="4c921-115">HoloLens で mixed reality の写真を撮るには、いくつかの方法があります。ハードウェアボタン、音声、または [スタート] メニューを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4c921-115">There are several ways to take a photo of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <a name="hardware-buttons-to-take-photos"></a><span data-ttu-id="4c921-116">写真を撮影するためのハードウェアボタン</span><span class="sxs-lookup"><span data-stu-id="4c921-116">Hardware buttons to take photos</span></span>

<span data-ttu-id="4c921-117">現在のビューの簡単な写真を撮るには、[音量] ボタンと [音量] ボタンを同時に押します。</span><span class="sxs-lookup"><span data-stu-id="4c921-117">To take a quick photo of your current view, press the volume up and volume down buttons at the same time.</span></span>  <span data-ttu-id="4c921-118">これは、HoloLens バージョンのスクリーンショットや印刷画面のようなものです。</span><span class="sxs-lookup"><span data-stu-id="4c921-118">This is a bit like the HoloLens version of a screenshot or print screen.</span></span>

- [<span data-ttu-id="4c921-119">HoloLens 2 のボタンの場所</span><span class="sxs-lookup"><span data-stu-id="4c921-119">Button locations on HoloLens 2</span></span>](hololens2-hardware.md)
- [<span data-ttu-id="4c921-120">HoloLens のボタンの場所 (第1世代)</span><span class="sxs-lookup"><span data-stu-id="4c921-120">Button locations on HoloLens (1st gen)</span></span>](hololens1-hardware.md#hololens-components)

> [!NOTE]
> <span data-ttu-id="4c921-121">[ **音量アップ** ] ボタンと [ **音量** ] ボタンを3秒押し続けると、写真を撮影するのではなく、ビデオの録画が開始されます。</span><span class="sxs-lookup"><span data-stu-id="4c921-121">Holding the **volume up** and **volume down** buttons for three seconds will start recording a video rather than taking a photo.</span></span> <span data-ttu-id="4c921-122">記録を停止するには、[ **音量アップ** ] ボタンと [ **音量ダウン** ] ボタンの両方を同時にタップします。</span><span class="sxs-lookup"><span data-stu-id="4c921-122">To stop recording, tap both **volume up** and **volume down** buttons simultaneously.</span></span>

### <a name="voice-commands-to-take-photos"></a><span data-ttu-id="4c921-123">写真を撮影するための音声コマンド</span><span class="sxs-lookup"><span data-stu-id="4c921-123">Voice commands to take photos</span></span>

<span data-ttu-id="4c921-124">HoloLens 2、バージョン 2004 (およびそれ以降) では、「写真を撮る」と言います。</span><span class="sxs-lookup"><span data-stu-id="4c921-124">On HoloLens 2, version 2004 (and later), say: "Take a picture."</span></span>

<span data-ttu-id="4c921-125">HoloLens (第1世代) または HoloLens 2、バージョン1903では、「Cortana さん、写真を撮る」と言います。</span><span class="sxs-lookup"><span data-stu-id="4c921-125">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, take a picture."</span></span>

### <a name="start-menu-to-take-photos"></a><span data-ttu-id="4c921-126">[スタート] メニューを使用して写真を撮影する</span><span class="sxs-lookup"><span data-stu-id="4c921-126">Start menu to take photos</span></span>

<span data-ttu-id="4c921-127">開始ジェスチャを使用して **スタート** 画面に戻り、 **カメラ** アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="4c921-127">Use the Start gesture to go to **Start**, then select the **camera** icon.</span></span>

<span data-ttu-id="4c921-128">キャプチャする内容の方向をポイントし、 [エアタップ](hololens2-basic-usage.md#touch-holograms-near-you) を使用して写真を撮影します。</span><span class="sxs-lookup"><span data-stu-id="4c921-128">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to take a photo.</span></span> <span data-ttu-id="4c921-129">引き続きエアタップして、追加の写真を取り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="4c921-129">You can continue to air tap and capture additional photos.</span></span> <span data-ttu-id="4c921-130">キャプチャした写真はすべてデバイスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="4c921-130">Any photos you capture will be saved to your device.</span></span>

<span data-ttu-id="4c921-131">フォトキャプチャを終了するには、もう一度開始ジェスチャを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c921-131">Use the Start gesture again to end photo capture.</span></span>  

## <a name="capture-a-mixed-reality-video"></a><span data-ttu-id="4c921-132">Mixed reality ビデオをキャプチャする</span><span class="sxs-lookup"><span data-stu-id="4c921-132">Capture a mixed reality video</span></span>

<span data-ttu-id="4c921-133">HoloLens で mixed reality のビデオを記録するには、いくつかの方法があります。ハードウェアボタン、音声、または [スタート] メニューを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4c921-133">There are several ways to record a video of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <a name="hardware-buttons-to-record-videos"></a><span data-ttu-id="4c921-134">ビデオを録画するためのハードウェアボタン</span><span class="sxs-lookup"><span data-stu-id="4c921-134">Hardware buttons to record videos</span></span>

<span data-ttu-id="4c921-135">ビデオを録画する最も簡単な方法は、3秒のカウントダウンが開始されるまで、[ **音量** ] ボタンと [ **音量** ] ボタンを同時に押すことです。</span><span class="sxs-lookup"><span data-stu-id="4c921-135">The quickest way to record a video is to press and hold the **volume up** and **volume down** buttons simultaneously until a three-second countdown begins.</span></span> <span data-ttu-id="4c921-136">記録を停止するには、両方のボタンを同時にタップします。</span><span class="sxs-lookup"><span data-stu-id="4c921-136">To stop recording, tap both buttons simultaneously.</span></span>

> [!NOTE]
> <span data-ttu-id="4c921-137">[ **音量** ] ボタンと [ **音量** ] ボタンを同時に押すと、ビデオを録画するのではなく、写真が撮影されます。</span><span class="sxs-lookup"><span data-stu-id="4c921-137">Quickly pressing the **volume up** and **volume down** buttons at the same time will take a photo rather than recording a video.</span></span>

### <a name="voice-to-record-videos"></a><span data-ttu-id="4c921-138">動画を録画するための音声</span><span class="sxs-lookup"><span data-stu-id="4c921-138">Voice to record videos</span></span>

<span data-ttu-id="4c921-139">HoloLens 2、バージョン 2004 (およびそれ以降) では、"記録の開始" と言います。</span><span class="sxs-lookup"><span data-stu-id="4c921-139">On HoloLens 2, version 2004 (and later), say: "Start recording."</span></span> <span data-ttu-id="4c921-140">記録を停止するには、「録画を停止する」と言います。</span><span class="sxs-lookup"><span data-stu-id="4c921-140">To stop recording, say "Stop recording."</span></span>

<span data-ttu-id="4c921-141">HoloLens (第1世代) または HoloLens 2、バージョン1903では、「Cortana について、記録を開始する」と言います。</span><span class="sxs-lookup"><span data-stu-id="4c921-141">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, start recording."</span></span> <span data-ttu-id="4c921-142">記録を停止するには、"Cortana さん、録画を停止する" と言います。</span><span class="sxs-lookup"><span data-stu-id="4c921-142">To stop recording, say "Hey Cortana, stop recording."</span></span>

### <a name="start-menu-to-record-videos"></a><span data-ttu-id="4c921-143">ビデオを録画するための [スタート] メニュー</span><span class="sxs-lookup"><span data-stu-id="4c921-143">Start menu to record videos</span></span>

<span data-ttu-id="4c921-144">開始ジェスチャを使用して **スタート** 画面にアクセスし、 **ビデオ** アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="4c921-144">Use the Start gesture to go to **Start**, then select the **video** icon.</span></span> <span data-ttu-id="4c921-145">キャプチャする対象の方向をポイントし、次に [エアタップ](hololens2-basic-usage.md#touch-holograms-near-you) で録音を開始します。</span><span class="sxs-lookup"><span data-stu-id="4c921-145">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to start recording.</span></span> <span data-ttu-id="4c921-146">3秒間のカウントダウンが発生し、記録が開始されます。</span><span class="sxs-lookup"><span data-stu-id="4c921-146">There will be a three second countdown and your recording will begin.</span></span>

<span data-ttu-id="4c921-147">記録を停止するには、開始ジェスチャを使用して、強調表示された **ビデオ** アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="4c921-147">To stop recording, use the Start gesture and select the highlighted **video** icon.</span></span> <span data-ttu-id="4c921-148">ビデオはデバイスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="4c921-148">The video will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="4c921-149">**HoloLens (第1世代) のみに適用されます**</span><span class="sxs-lookup"><span data-stu-id="4c921-149">**Applies to HoloLens (1st gen) only**</span></span>  
> <span data-ttu-id="4c921-150">[Windows 10 10 月2018更新プログラム](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)は、[開始] ジェスチャと [windows] ボタンが HoloLens (第1世代) でどのように動作するかを変更します。</span><span class="sxs-lookup"><span data-stu-id="4c921-150">The [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) changes how the Start gesture and Windows button behave on HoloLens (1st gen).</span></span> <span data-ttu-id="4c921-151">更新前は、開始ジェスチャまたは Windows ボタンによってビデオ記録が停止されます。</span><span class="sxs-lookup"><span data-stu-id="4c921-151">Before the update, the Start gesture or Windows button would stop a video recording.</span></span> <span data-ttu-id="4c921-152">ただし、更新後、[開始ジェスチャ] または [Windows] ボタンをクリックすると、[ **スタート** ] メニュー (または、イマーシブアプリの場合は [ **クイックアクション] メニュー** ) が開き、強調表示された **ビデオ** アイコンを選択して録画を停止できます。</span><span class="sxs-lookup"><span data-stu-id="4c921-152">After the update, however, the Start gesture or Windows button opens the **Start** menu (or the **quick actions menu** if you are in an immersive app), from which you can select the highlighted **video** icon to stop recording.</span></span>

## <a name="share-what-you-see-in-real-time"></a><span data-ttu-id="4c921-153">リアルタイムで表示されるものを共有する</span><span class="sxs-lookup"><span data-stu-id="4c921-153">Share what you see in real-time</span></span>

<span data-ttu-id="4c921-154">HoloLens で表示されているものは、リアルタイムで友人や同僚と共有できます。</span><span class="sxs-lookup"><span data-stu-id="4c921-154">You can share what you see in HoloLens with friends and colleagues in real-time.</span></span> <span data-ttu-id="4c921-155">使用できるメソッドはいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="4c921-155">There are a few methods available:</span></span>

1. <span data-ttu-id="4c921-156">Miracast が有効なデバイスまたはアダプターに接続して、テレビを視聴します。</span><span class="sxs-lookup"><span data-stu-id="4c921-156">Connecting to a Miracast-enabled device or adapter to watch on a TV.</span></span>
1. <span data-ttu-id="4c921-157">[Windows デバイスポータル](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)を使用して PC を監視する</span><span class="sxs-lookup"><span data-stu-id="4c921-157">Using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to watch on a PC</span></span>
1. <span data-ttu-id="4c921-158">[Microsoft HoloLens コンパニオンアプリ](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)を使用して PC を監視します。</span><span class="sxs-lookup"><span data-stu-id="4c921-158">Using the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) to watch on a PC.</span></span>
1. <span data-ttu-id="4c921-159">[Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist)アプリを展開します。これにより、フロントラインワーカーは、リモートのエキスパートに表示される情報をストリームできます。</span><span class="sxs-lookup"><span data-stu-id="4c921-159">Deploying the [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) app, which enables front-line workers to stream what they see to a remote expert.</span></span> <span data-ttu-id="4c921-160">その後、リモートの専門家は、フロントラインワーカーの口頭で他者をガイドしたり、世界中に注釈を付けたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="4c921-160">The remote expert can then guide the front-line worker verbally or by annotating in their world.</span></span>

> [!NOTE]
> <span data-ttu-id="4c921-161">Windows デバイスポータルまたは Microsoft HoloLens コンパニオンアプリを使用して表示される情報を共有するには、HoloLens が [開発者モード](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c921-161">Sharing what you see via Windows Device Portal or Microsoft HoloLens companion app requires your HoloLens to be in [Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal).</span></span>

### <a name="stream-video-with-miracast"></a><span data-ttu-id="4c921-162">Miracast によるビデオのストリーミング</span><span class="sxs-lookup"><span data-stu-id="4c921-162">Stream video with Miracast</span></span>

<span data-ttu-id="4c921-163">開始ジェスチャを使用して **スタート** 画面にアクセスし、[ **接続** ] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="4c921-163">Use the Start gesture to go to **Start**, then select the **connect** icon.</span></span> <span data-ttu-id="4c921-164">表示されるピッカーから、接続先の Miracast が有効なデバイスまたはアダプターを選択します。</span><span class="sxs-lookup"><span data-stu-id="4c921-164">From the picker that appears, select the Miracast-enabled device or adapter to which you want to connect.</span></span>

<span data-ttu-id="4c921-165">共有を停止するには、開始ジェスチャを使用して、強調表示された **接続** アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="4c921-165">To stop sharing, use the Start gesture and select the highlighted **connect** icon.</span></span> <span data-ttu-id="4c921-166">ストリーミングを行っているため、デバイスには何も保存されません。</span><span class="sxs-lookup"><span data-stu-id="4c921-166">Because you were streaming, nothing will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="4c921-167">Miracast サポートは、 [Windows 10 10 月2018更新プログラム](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)以降、HoloLens (第1世代) で有効になりました。</span><span class="sxs-lookup"><span data-stu-id="4c921-167">Miracast support was enabled on HoloLens (1st gen) beginning with the [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018).</span></span>

### <a name="real-time-video-with-windows-device-portal"></a><span data-ttu-id="4c921-168">Windows デバイスポータルを使用したリアルタイムビデオ</span><span class="sxs-lookup"><span data-stu-id="4c921-168">Real time video with Windows Device Portal</span></span>

<span data-ttu-id="4c921-169">Windows デバイスポータルを使用して共有するには、HoloLens で開発者モードを有効にする必要があるため、開発者向けドキュメントの手順に従って [開発者モードを設定し、Windows デバイスポータルに移動](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)します。</span><span class="sxs-lookup"><span data-stu-id="4c921-169">Because sharing via Windows Device Portal requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode and navigate Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

### <a name="microsoft-hololens-companion-app"></a><span data-ttu-id="4c921-170">Microsoft HoloLens コンパニオンアプリ</span><span class="sxs-lookup"><span data-stu-id="4c921-170">Microsoft HoloLens companion app</span></span>

<span data-ttu-id="4c921-171">Microsoft HoloLens コンパニオンアプリを使用して共有するには、HoloLens で開発者モードを有効にする必要があるため、開発者向けドキュメントの手順に従って [開発者モードを設定](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)します。</span><span class="sxs-lookup"><span data-stu-id="4c921-171">Because sharing via the Microsoft HoloLens companion app requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="4c921-172">次に、 [Microsoft hololens コンパニオンアプリ](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) をダウンロードし、アプリ内の指示に従って HoloLens に接続します。</span><span class="sxs-lookup"><span data-stu-id="4c921-172">Then, download the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) and follow the instructions within the app to connect to your HoloLens.</span></span>

<span data-ttu-id="4c921-173">アプリが HoloLens で設定されたら、アプリのメインメニューから [ **ライブストリーム** ] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="4c921-173">Once the app is set up with your HoloLens, select the **Live stream** option from the app's main menu.</span></span>

## <a name="view-your-mixed-reality-photos-and-videos"></a><span data-ttu-id="4c921-174">Mixed reality の写真とビデオを表示する</span><span class="sxs-lookup"><span data-stu-id="4c921-174">View your mixed reality photos and videos</span></span>

<span data-ttu-id="4c921-175">Mixed reality の写真とビデオは、デバイスの "カメラロール" に保存されます。</span><span class="sxs-lookup"><span data-stu-id="4c921-175">Mixed reality photos and videos are saved to the device's "Camera Roll".</span></span> <span data-ttu-id="4c921-176">ファイルエクスプローラーアプリを使用して、HoloLens のこのフォルダーの内容を参照することができます ([画像] > [カメラロール] に移動します)。</span><span class="sxs-lookup"><span data-stu-id="4c921-176">You can browse the contents of this folder on your HoloLens with the File Explorer app (navigate to Pictures > Camera Roll).</span></span>

<span data-ttu-id="4c921-177">また、HoloLens にプレインストールされている Photos アプリで、mixed reality の写真とビデオを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="4c921-177">You can also view your mixed reality photos and videos in the Photos app, which is pre-installed on HoloLens.</span></span> <span data-ttu-id="4c921-178">世界中の写真をピン留めするには、[写真] アプリで写真を選択し、[ **混合世界に配置** する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c921-178">To pin a photo in your world, select it in the Photos app and choose **Place in mixed world**.</span></span> <span data-ttu-id="4c921-179">写真は、配置された後、世界中に移動できます。</span><span class="sxs-lookup"><span data-stu-id="4c921-179">You can move the photo around your world after it's been placed.</span></span>

<span data-ttu-id="4c921-180">HoloLens に接続されている PC で mixed reality の写真とビデオを表示したり保存したりするには、 [Windows デバイスポータル](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) または MTP を使用して [pc のエクスプローラー](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)を使用します。</span><span class="sxs-lookup"><span data-stu-id="4c921-180">To view and/or save your mixed reality photos and videos on a PC connected to HoloLens, you can use [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) or your [PC's File Explorer via MTP](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens).</span></span>

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a><span data-ttu-id="4c921-181">ファイルエクスプローラーを使用して画像、ビデオ、ファイルを取得する</span><span class="sxs-lookup"><span data-stu-id="4c921-181">Use File Explorer to get your pictures, videos and files</span></span>

<span data-ttu-id="4c921-182">他のモバイルデバイスと同様に、HoloLens を PC に接続して、ファイルエクスプローラーから HoloLens ライブラリ (写真、ビデオ、ドキュメント) にアクセスして転送を容易にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4c921-182">Similar to other mobile devices, connect your HoloLens to your PC to bring up File Explorer to access your HoloLens libraries (photos, videos, documents) for easy transfer.</span></span> <span data-ttu-id="4c921-183">この方法は使いやすく、デバイスポータルや Wi-fi を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4c921-183">This method is easy to use and does not require the use of device portal or Wi-Fi.</span></span>

1. <span data-ttu-id="4c921-184">デバイスのロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="4c921-184">Unlock the device.</span></span>
1. <span data-ttu-id="4c921-185">USB を使用してデバイスを PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="4c921-185">Connect the device to a PC via USB.</span></span>
1. <span data-ttu-id="4c921-186">PC でファイルエクスプローラーが開きます。</span><span class="sxs-lookup"><span data-stu-id="4c921-186">File Explorer should open on your PC.</span></span>
1. <span data-ttu-id="4c921-187">移動: This PC \\ *yourhololensname*\ Internal Storage\Pictures\Camera Roll</span><span class="sxs-lookup"><span data-stu-id="4c921-187">Navigate to: This PC\\*yourhololensname*\Internal Storage\Pictures\Camera Roll</span></span>
1. <span data-ttu-id="4c921-188">必要なすべてのファイルを PC にコピーします。</span><span class="sxs-lookup"><span data-stu-id="4c921-188">Copy whatever files you need to your PC.</span></span>

<span data-ttu-id="4c921-189">ヒント:</span><span class="sxs-lookup"><span data-stu-id="4c921-189">Tips:</span></span>
- <span data-ttu-id="4c921-190">ファイルが表示されない場合は、HoloLens にサインインしてデータにアクセスできることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4c921-190">If you don't see any files, please ensure you sign in to your HoloLens to enable access to your data.</span></span>
- <span data-ttu-id="4c921-191">他のフォルダーにある他のファイル ( [診断ファイル](hololens-diagnostic-logs.md#offline-diagnostics) など) は、[ドキュメント] フォルダーから取得できます。</span><span class="sxs-lookup"><span data-stu-id="4c921-191">You can get other files in other folders, such as [diagnostics files](hololens-diagnostic-logs.md#offline-diagnostics) from the Documents folder.</span></span>
- <span data-ttu-id="4c921-192">PC のエクスプローラーから、[デバイスのプロパティ] を選択して、Windows Holographic OS のバージョン番号 (ファームウェアのバージョン)、デバイスのシリアル番号、およびバッテリの割合を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4c921-192">From File Explorer on your PC, you can select Device properties to see Windows Holographic OS version number (firmware version), device serial number, and battery percentage.</span></span>
- <span data-ttu-id="4c921-193">組織で MDM を使用して [接続/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) を無効にした場合、デバイスに接続できなくなります。</span><span class="sxs-lookup"><span data-stu-id="4c921-193">If your Organization has used MDM to disable [Connectivity/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) then you will be unable to connect to your device.</span></span>

## <a name="share-your-mixed-reality-photos-and-videos"></a><span data-ttu-id="4c921-194">Mixed reality の写真とビデオを共有する</span><span class="sxs-lookup"><span data-stu-id="4c921-194">Share your mixed reality photos and videos</span></span>

<span data-ttu-id="4c921-195">Mixed reality の写真またはビデオをキャプチャすると、プレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c921-195">After capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="4c921-196">プレビューの上にある [ **共有** ] アイコンを選択して、共有アシスタントを表示します。</span><span class="sxs-lookup"><span data-stu-id="4c921-196">Select the **share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="4c921-197">そこから、写真またはビデオを共有するエンドポイントを選択できます。</span><span class="sxs-lookup"><span data-stu-id="4c921-197">From there, you can select the end point to which you'd like to share that photo or video.</span></span>

<span data-ttu-id="4c921-198">また、mixed reality の写真とビデオを OneDrive から共有することもできます。これにより、mixed reality の写真とビデオが自動的にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="4c921-198">You can also share mixed reality photos and videos from OneDrive, by automatically uploading your mixed reality photos and videos.</span></span> <span data-ttu-id="4c921-199">HoloLens で OneDrive アプリを開き、personal [Microsoft アカウント](https://account.microsoft.com) でサインインします (まだインストールしていない場合)。</span><span class="sxs-lookup"><span data-stu-id="4c921-199">Open the OneDrive app on HoloLens and sign in with a personal [Microsoft account](https://account.microsoft.com) if you haven't already.</span></span> <span data-ttu-id="4c921-200">**設定** アイコンを選択し、[**カメラのアップロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c921-200">Select the **settings** icon and choose **Camera upload**.</span></span> <span data-ttu-id="4c921-201">カメラのアップロードを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4c921-201">Turn Camera upload on.</span></span> <span data-ttu-id="4c921-202">アプリを HoloLens で起動するたびに、mixed reality の写真とビデオが OneDrive にアップロードされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4c921-202">Your mixed reality photos and videos will now be uploaded to OneDrive each time you launch the app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="4c921-203">Onedrive で個人用 Microsoft アカウントを使用して OneDrive にサインインしている場合にのみ、OneDrive でのカメラのアップロードを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4c921-203">You can only enable camera upload in OneDrive if you’re signed into OneDrive with a personal Microsoft account.</span></span> <span data-ttu-id="4c921-204">職場または学校のアカウントを使用して HoloLens をセットアップした場合は、OneDrive アプリに個人の Microsoft アカウントを追加して、この機能を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4c921-204">If you set up HoloLens with a work or school account, you can add a personal Microsoft account in the OneDrive app to enable this feature.</span></span>

## <a name="limitations-of-mixed-reality-capture"></a><span data-ttu-id="4c921-205">Mixed reality キャプチャの制限事項</span><span class="sxs-lookup"><span data-stu-id="4c921-205">Limitations of mixed reality capture</span></span>

- <span data-ttu-id="4c921-206">Mixed reality キャプチャを使用している間、HoloLens のレートは 30 Hz に半減します。</span><span class="sxs-lookup"><span data-stu-id="4c921-206">While using mixed reality capture, the framerate of HoloLens will be halved to 30 Hz.</span></span>
- <span data-ttu-id="4c921-207">写真/ビデオカメラが既に別のアプリケーションによって使用されている場合、ライブストリーミング中、またはシステムリソースが少ない場合は、写真やビデオの解像度が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4c921-207">The resolution of photos and videos may be reduced if the photo/video camera is already in use by another application, while live streaming, or when system resources are low.</span></span>

### <a name="maximum-recording-length"></a><span data-ttu-id="4c921-208">最大記録長</span><span class="sxs-lookup"><span data-stu-id="4c921-208">Maximum recording length</span></span>

<span data-ttu-id="4c921-209">Windows Holographic より前の HoloLens 2 デバイスでは、デバイスに記録されているバージョン20H2 ビデオは、最大で5分の長さに制限されていました。</span><span class="sxs-lookup"><span data-stu-id="4c921-209">On HoloLens 2 devices before the Windows Holographic, version 20H2 videos recorded on the device were limited to maximum length of five minutes.</span></span>

<span data-ttu-id="4c921-210">お客様からのフィードバックにより、 [混合現実のキャプチャ](holographic-photos-and-videos.md)の記録長さが増加しています。</span><span class="sxs-lookup"><span data-stu-id="4c921-210">Due to customer feedback we’ve increased the recording length of [mixed reality captures](holographic-photos-and-videos.md).</span></span> <span data-ttu-id="4c921-211">混合の現実のキャプチャは、既定では5分に制限されなくなりましたが、代わりに使用可能なディスク領域に基づいて最大記録長が計算されます。</span><span class="sxs-lookup"><span data-stu-id="4c921-211">Mixed reality captures will no longer be limited to 5 minutes by default but instead will calculate the maximum recording length based on available disk space.</span></span> <span data-ttu-id="4c921-212">デバイスは、ディスクの空き領域の最大80% まで、使用可能なディスク領域に基づいて、最大ビデオ記録期間を見積もります。</span><span class="sxs-lookup"><span data-stu-id="4c921-212">The device will estimate the max video recording duration based on available disk space up to 80% of the total disk space.</span></span>

> [!NOTE]
> <span data-ttu-id="4c921-213">次のいずれかが発生した場合、HoloLens では既定のビデオ記録の長さ (5 分) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="4c921-213">The HoloLens will use default video recording length (5 minutes) if one of the following occurs:</span></span>
> - <span data-ttu-id="4c921-214">推定最大記録期間は、既定の5分よりも小さくなっています。</span><span class="sxs-lookup"><span data-stu-id="4c921-214">The estimated max recording duration is smaller than the default 5 mins.</span></span>
> - <span data-ttu-id="4c921-215">使用可能なディスク領域が、合計ディスク領域の20% 未満です。</span><span class="sxs-lookup"><span data-stu-id="4c921-215">The available disk space is less than 20% of the total disk space.</span></span>

## <a name="default-file-format-and-resolution"></a><span data-ttu-id="4c921-216">既定のファイル形式と解決方法</span><span class="sxs-lookup"><span data-stu-id="4c921-216">Default file format and resolution</span></span>

### <a name="default-photo-format-and-resolution"></a><span data-ttu-id="4c921-217">既定の写真の形式と解像度</span><span class="sxs-lookup"><span data-stu-id="4c921-217">Default photo format and resolution</span></span>

|  <span data-ttu-id="4c921-218">Device</span><span class="sxs-lookup"><span data-stu-id="4c921-218">Device</span></span>  |  <span data-ttu-id="4c921-219">Format</span><span class="sxs-lookup"><span data-stu-id="4c921-219">Format</span></span>  |  <span data-ttu-id="4c921-220">拡張機能</span><span class="sxs-lookup"><span data-stu-id="4c921-220">Extension</span></span>  |  <span data-ttu-id="4c921-221">解像度</span><span class="sxs-lookup"><span data-stu-id="4c921-221">Resolution</span></span>  |
|----------|----------|----------|----------|
| <span data-ttu-id="4c921-222">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="4c921-222">HoloLens 2</span></span> | [<span data-ttu-id="4c921-223">JPEG</span><span class="sxs-lookup"><span data-stu-id="4c921-223">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="4c921-224">.jpg</span><span class="sxs-lookup"><span data-stu-id="4c921-224">.jpg</span></span> | <span data-ttu-id="4c921-225">3904x2196px</span><span class="sxs-lookup"><span data-stu-id="4c921-225">3904x2196px</span></span> |
| <span data-ttu-id="4c921-226">HoloLens (第 1 世代)</span><span class="sxs-lookup"><span data-stu-id="4c921-226">HoloLens (1st gen)</span></span> | [<span data-ttu-id="4c921-227">JPEG</span><span class="sxs-lookup"><span data-stu-id="4c921-227">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="4c921-228">.jpg</span><span class="sxs-lookup"><span data-stu-id="4c921-228">.jpg</span></span> | <span data-ttu-id="4c921-229">1408x792px</span><span class="sxs-lookup"><span data-stu-id="4c921-229">1408x792px</span></span> |

### <a name="recorded-video-format-and-resolution"></a><span data-ttu-id="4c921-230">記録されたビデオ形式と解像度</span><span class="sxs-lookup"><span data-stu-id="4c921-230">Recorded video format and resolution</span></span>

| <span data-ttu-id="4c921-231">Device</span><span class="sxs-lookup"><span data-stu-id="4c921-231">Device</span></span> | <span data-ttu-id="4c921-232">Format</span><span class="sxs-lookup"><span data-stu-id="4c921-232">Format</span></span> | <span data-ttu-id="4c921-233">拡張機能</span><span class="sxs-lookup"><span data-stu-id="4c921-233">Extension</span></span> | <span data-ttu-id="4c921-234">解像度</span><span class="sxs-lookup"><span data-stu-id="4c921-234">Resolution</span></span> | <span data-ttu-id="4c921-235">速度</span><span class="sxs-lookup"><span data-stu-id="4c921-235">Speed</span></span> | <span data-ttu-id="4c921-236">オーディオ</span><span class="sxs-lookup"><span data-stu-id="4c921-236">Audio</span></span> |
|----------|----------|----------|----------|----------|----------|
| <span data-ttu-id="4c921-237">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="4c921-237">HoloLens 2</span></span> | [<span data-ttu-id="4c921-238">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="4c921-238">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="4c921-239">.mp4</span><span class="sxs-lookup"><span data-stu-id="4c921-239">.mp4</span></span> | <span data-ttu-id="4c921-240">1920x1080px</span><span class="sxs-lookup"><span data-stu-id="4c921-240">1920x1080px</span></span> | <span data-ttu-id="4c921-241">30 fps</span><span class="sxs-lookup"><span data-stu-id="4c921-241">30fps</span></span> | <span data-ttu-id="4c921-242">48 Khz ステレオ</span><span class="sxs-lookup"><span data-stu-id="4c921-242">48kHz Stereo</span></span> |
| <span data-ttu-id="4c921-243">HoloLens (第 1 世代)</span><span class="sxs-lookup"><span data-stu-id="4c921-243">HoloLens (1st gen)</span></span> |  [<span data-ttu-id="4c921-244">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="4c921-244">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="4c921-245">.mp4</span><span class="sxs-lookup"><span data-stu-id="4c921-245">.mp4</span></span> | <span data-ttu-id="4c921-246">1216x684px</span><span class="sxs-lookup"><span data-stu-id="4c921-246">1216x684px</span></span> | <span data-ttu-id="4c921-247">24fps</span><span class="sxs-lookup"><span data-stu-id="4c921-247">24fps</span></span> | <span data-ttu-id="4c921-248">48 Khz ステレオ</span><span class="sxs-lookup"><span data-stu-id="4c921-248">48kHz Stereo</span></span> |
