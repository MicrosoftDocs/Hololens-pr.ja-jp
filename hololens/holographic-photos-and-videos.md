---
title: Mixed reality の写真とビデオをキャプチャして管理する
description: HoloLens を使って、mixed reality 写真とビデオのキャプチャ、表示、共有を行う方法について説明します。
keywords: hololens、写真、ビデオ、キャプチャ、mrc、mixed reality キャプチャ、写真、カメラ、ストリーム、livestream、デモ
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
ms.openlocfilehash: 1be4e80c040d5b8e451c07fb931c7c7fb8d5ab48
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829109"
---
# <span data-ttu-id="1a958-104">Mixed Reality の写真とビデオを作成する</span><span class="sxs-lookup"><span data-stu-id="1a958-104">Create mixed reality photos and videos</span></span>

<span data-ttu-id="1a958-105">HoloLens は、現実世界とデジタル世界との混合のエクスペリエンスをユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="1a958-105">HoloLens gives users the experience of mixing the real world with the digital world.</span></span>  <span data-ttu-id="1a958-106">複合現実キャプチャ (MRC) を使用すると、そのエクスペリエンスを写真やビデオとしてキャプチャしたり、他のユーザーとリアルタイムで共有したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="1a958-106">Mixed reality capture (MRC) lets you capture that experience as a photo or video, or share what you see with others in real-time.</span></span>

<span data-ttu-id="1a958-107">Mixed reality キャプチャでは、他のユーザーが表示しているホログラムを他のユーザーが見ることができるように、最初のユーザーの視点を使います。</span><span class="sxs-lookup"><span data-stu-id="1a958-107">Mixed reality capture uses a first-person point of view so other people can see holograms as you see them.</span></span> <span data-ttu-id="1a958-108">視点が3人の場合は、 [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view)を使用します。</span><span class="sxs-lookup"><span data-stu-id="1a958-108">For a third-person point of view, use [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view).</span></span> <span data-ttu-id="1a958-109">Spectator view は、デモに特に便利です。</span><span class="sxs-lookup"><span data-stu-id="1a958-109">Spectator view is especially useful for demos.</span></span>

<span data-ttu-id="1a958-110">ビデオは、友達や同僚とビデオを共有するのに便利ですが、ビデオは、他のユーザーがアプリを使用したり、アプリやエクスペリエンスの問題を伝えたりするために役立つこともあります。</span><span class="sxs-lookup"><span data-stu-id="1a958-110">While it's fun to share videos amongst friends and colleagues, videos can also help teach other people to use an app or to communicate problems with apps and experiences.</span></span>

> [!NOTE]
> <span data-ttu-id="1a958-111">Mixed reality キャプチャエクスペリエンスを起動できず、HoloLens が作業デバイスである場合は、システム管理者に確認してください。</span><span class="sxs-lookup"><span data-stu-id="1a958-111">If you can't launch mixed reality capture experiences and your HoloLens is a work device, check with your system administrator.</span></span> <span data-ttu-id="1a958-112">カメラへのアクセスは、会社のポリシーを通じて制限することができます。</span><span class="sxs-lookup"><span data-stu-id="1a958-112">Access to the camera can be restricted through company policy.</span></span>

## <span data-ttu-id="1a958-113">Mixed reality 写真をキャプチャする</span><span class="sxs-lookup"><span data-stu-id="1a958-113">Capture a mixed reality photo</span></span>

<span data-ttu-id="1a958-114">HoloLens で mixed reality の写真を撮影するには、いくつかの方法があります。ハードウェアボタン、音声、または [スタート] メニューを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1a958-114">There are several ways to take a photo of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <span data-ttu-id="1a958-115">写真を撮るためのハードウェアボタン</span><span class="sxs-lookup"><span data-stu-id="1a958-115">Hardware buttons to take photos</span></span>

<span data-ttu-id="1a958-116">現在のビューの写真を撮影するには、[音量を上げる] ボタンと [音量を下げる] ボタンを同時に押します。</span><span class="sxs-lookup"><span data-stu-id="1a958-116">To take a quick photo of your current view, press the volume up and volume down buttons at the same time.</span></span>  <span data-ttu-id="1a958-117">これは、HoloLens バージョンのスクリーンショットまたは印刷画面に似ています。</span><span class="sxs-lookup"><span data-stu-id="1a958-117">This is a bit like the HoloLens version of a screenshot or print screen.</span></span>

- [<span data-ttu-id="1a958-118">HoloLens 2 のボタンの場所</span><span class="sxs-lookup"><span data-stu-id="1a958-118">Button locations on HoloLens 2</span></span>](hololens2-hardware.md)
- [<span data-ttu-id="1a958-119">HoloLens 上のボタンの場所 (第1世代)</span><span class="sxs-lookup"><span data-stu-id="1a958-119">Button locations on HoloLens (1st gen)</span></span>](hololens1-hardware.md#hololens-components)

> [!NOTE]
> <span data-ttu-id="1a958-120">[**音量を上げる**] ボタンと [**音量を下げる**] ボタンを3回押すと、写真を撮影するのではなく、ビデオの録画が開始されます。</span><span class="sxs-lookup"><span data-stu-id="1a958-120">Holding the **volume up** and **volume down** buttons for three seconds will start recording a video rather than taking a photo.</span></span> <span data-ttu-id="1a958-121">記録を停止するには、[**音量を上げる**] と [**音量を下げる**] の両方のボタンを同時にタップします。</span><span class="sxs-lookup"><span data-stu-id="1a958-121">To stop recording, tap both **volume up** and **volume down** buttons simultaneously.</span></span>

### <span data-ttu-id="1a958-122">写真を撮るための音声コマンド</span><span class="sxs-lookup"><span data-stu-id="1a958-122">Voice commands to take photos</span></span>

<span data-ttu-id="1a958-123">HoloLens 2、バージョン 2004 (以降) では、「写真を撮る」と言ってください。</span><span class="sxs-lookup"><span data-stu-id="1a958-123">On HoloLens 2, version 2004 (and later), say: "Take a picture."</span></span>

<span data-ttu-id="1a958-124">HoloLens (第1世代) または HoloLens 2、バージョン1903では、「コルタナさん、写真を撮影してください」と言っています。</span><span class="sxs-lookup"><span data-stu-id="1a958-124">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, take a picture."</span></span>

### <span data-ttu-id="1a958-125">[スタート] メニューで写真を撮る</span><span class="sxs-lookup"><span data-stu-id="1a958-125">Start menu to take photos</span></span>

<span data-ttu-id="1a958-126">開始ジェスチャを使用して [**スタート**] に移動し、[**カメラ**] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="1a958-126">Use the Start gesture to go to **Start**, then select the **camera** icon.</span></span>

<span data-ttu-id="1a958-127">キャプチャする内容の向きをポイントして、[エアタップ](hololens2-basic-usage.md#touch-holograms-near-you)して写真を撮ります。</span><span class="sxs-lookup"><span data-stu-id="1a958-127">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to take a photo.</span></span> <span data-ttu-id="1a958-128">引き続き、空中でタップして追加の写真をキャプチャすることができます。</span><span class="sxs-lookup"><span data-stu-id="1a958-128">You can continue to air tap and capture additional photos.</span></span> <span data-ttu-id="1a958-129">キャプチャした写真は、お使いのデバイスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="1a958-129">Any photos you capture will be saved to your device.</span></span>

<span data-ttu-id="1a958-130">もう一度開始ジェスチャを使って写真のキャプチャを終了します。</span><span class="sxs-lookup"><span data-stu-id="1a958-130">Use the Start gesture again to end photo capture.</span></span>  

## <span data-ttu-id="1a958-131">Mixed reality ビデオをキャプチャする</span><span class="sxs-lookup"><span data-stu-id="1a958-131">Capture a mixed reality video</span></span>

<span data-ttu-id="1a958-132">HoloLens で mixed reality のビデオを録画するには、いくつかの方法があります。ハードウェアボタン、音声、または [スタート] メニューを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1a958-132">There are several ways to record a video of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <span data-ttu-id="1a958-133">ビデオを録画するためのハードウェアボタン</span><span class="sxs-lookup"><span data-stu-id="1a958-133">Hardware buttons to record videos</span></span>

<span data-ttu-id="1a958-134">ビデオを録画する最も簡単な方法は、[**音量を上げる**] ボタンと [**音量を下げる**] ボタンを同時に押して、3秒のカウントダウンが開始されるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="1a958-134">The quickest way to record a video is to press and hold the **volume up** and **volume down** buttons simultaneously until a three-second countdown begins.</span></span> <span data-ttu-id="1a958-135">記録を停止するには、両方のボタンを同時にタップします。</span><span class="sxs-lookup"><span data-stu-id="1a958-135">To stop recording, tap both buttons simultaneously.</span></span>

> [!NOTE]
> <span data-ttu-id="1a958-136">[**音量を上げる**] ボタンと [**音量を下げる**] ボタンを同時に押すと、ビデオを録画するのではなく写真が撮影されます。</span><span class="sxs-lookup"><span data-stu-id="1a958-136">Quickly pressing the **volume up** and **volume down** buttons at the same time will take a photo rather than recording a video.</span></span>

### <span data-ttu-id="1a958-137">音声を録音してビデオを録画する</span><span class="sxs-lookup"><span data-stu-id="1a958-137">Voice to record videos</span></span>

<span data-ttu-id="1a958-138">HoloLens 2、バージョン 2004 (以降) では、「レコーディングの開始」と言ってください。</span><span class="sxs-lookup"><span data-stu-id="1a958-138">On HoloLens 2, version 2004 (and later), say: "Start recording."</span></span> <span data-ttu-id="1a958-139">記録を停止するには、「記録を停止」と発声します。</span><span class="sxs-lookup"><span data-stu-id="1a958-139">To stop recording, say "Stop recording."</span></span>

<span data-ttu-id="1a958-140">HoloLens (第1世代) または HoloLens 2、バージョン1903では、"コルタナさん、レコーディングを開始します" と言います。</span><span class="sxs-lookup"><span data-stu-id="1a958-140">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, start recording."</span></span> <span data-ttu-id="1a958-141">記録を停止するには、「コルタナさん、レコーディングを停止」と発声します。</span><span class="sxs-lookup"><span data-stu-id="1a958-141">To stop recording, say "Hey Cortana, stop recording."</span></span>

### <span data-ttu-id="1a958-142">ビデオを録画するためのスタートメニュー</span><span class="sxs-lookup"><span data-stu-id="1a958-142">Start menu to record videos</span></span>

<span data-ttu-id="1a958-143">開始ジェスチャを使用して [**スタート**] に移動し、[**ビデオ**] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="1a958-143">Use the Start gesture to go to **Start**, then select the **video** icon.</span></span> <span data-ttu-id="1a958-144">キャプチャするものの向きをポイントして、[[エアタップ](hololens2-basic-usage.md#touch-holograms-near-you)] をクリックして録音を開始します。</span><span class="sxs-lookup"><span data-stu-id="1a958-144">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to start recording.</span></span> <span data-ttu-id="1a958-145">3秒間のカウントダウンが表示され、レコーディングが開始されます。</span><span class="sxs-lookup"><span data-stu-id="1a958-145">There will be a three second countdown and your recording will begin.</span></span>

<span data-ttu-id="1a958-146">記録を停止するには、開始ジェスチャを使用して、強調表示された**ビデオ**アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="1a958-146">To stop recording, use the Start gesture and select the highlighted **video** icon.</span></span> <span data-ttu-id="1a958-147">ビデオがデバイスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="1a958-147">The video will be saved to your device.</span></span>

> [!NOTE]
> **<span data-ttu-id="1a958-148">HoloLens (第1世代) のみに適用されます</span><span class="sxs-lookup"><span data-stu-id="1a958-148">Applies to HoloLens (1st gen) only</span></span>**  
> <span data-ttu-id="1a958-149">[2018 年10月の更新プログラム](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)は、HoloLens (第1世代) で開始ジェスチャと Windows ボタンが動作する方法を変更します。</span><span class="sxs-lookup"><span data-stu-id="1a958-149">The [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) changes how the Start gesture and Windows button behave on HoloLens (1st gen).</span></span> <span data-ttu-id="1a958-150">更新する前に、開始ジェスチャまたは Windows ボタンをクリックすると、ビデオ録画が停止します。</span><span class="sxs-lookup"><span data-stu-id="1a958-150">Before the update, the Start gesture or Windows button would stop a video recording.</span></span> <span data-ttu-id="1a958-151">ただし、更新後、[スタート] または [Windows] ボタンをクリックすると、[**スタート**] メニュー (または [**クイック操作] メニュー** ) が開きます。これは、強調表示された**ビデオ**アイコンを選択して記録を停止することができます。</span><span class="sxs-lookup"><span data-stu-id="1a958-151">After the update, however, the Start gesture or Windows button opens the **Start** menu (or the **quick actions menu** if you are in an immersive app), from which you can select the highlighted **video** icon to stop recording.</span></span>

## <span data-ttu-id="1a958-152">表示される内容をリアルタイムで共有する</span><span class="sxs-lookup"><span data-stu-id="1a958-152">Share what you see in real-time</span></span>

<span data-ttu-id="1a958-153">HoloLens での表示内容は、お友達や同僚とリアルタイムで共有できます。</span><span class="sxs-lookup"><span data-stu-id="1a958-153">You can share what you see in HoloLens with friends and colleagues in real-time.</span></span> <span data-ttu-id="1a958-154">次のような方法があります。</span><span class="sxs-lookup"><span data-stu-id="1a958-154">There are a few methods available:</span></span>

1. <span data-ttu-id="1a958-155">Miracast を有効にしたデバイスまたはアダプターに接続して、テレビで見ることができます。</span><span class="sxs-lookup"><span data-stu-id="1a958-155">Connecting to a Miracast-enabled device or adapter to watch on a TV.</span></span>
1. <span data-ttu-id="1a958-156">[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)を使って PC を監視する</span><span class="sxs-lookup"><span data-stu-id="1a958-156">Using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to watch on a PC</span></span>
1. <span data-ttu-id="1a958-157">[Microsoft HoloLens コンパニオンアプリ](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)を使って PC を監視します。</span><span class="sxs-lookup"><span data-stu-id="1a958-157">Using the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) to watch on a PC.</span></span>
1. <span data-ttu-id="1a958-158">[Microsoft Dynamics 365 リモート](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist)アシスタンスアプリを展開して、フロントラインワーカーがリモートエキスパートに表示される内容をストリーミングできるようにします。</span><span class="sxs-lookup"><span data-stu-id="1a958-158">Deploying the [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) app, which enables front-line workers to stream what they see to a remote expert.</span></span> <span data-ttu-id="1a958-159">次に、リモートの専門家は、フロントラインワーカーのコミュニケーションとるを案内するか、または世界で注釈を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="1a958-159">The remote expert can then guide the front-line worker verbally or by annotating in their world.</span></span>

> [!NOTE]
> <span data-ttu-id="1a958-160">Windows Device Portal または Microsoft HoloLens コンパニオンアプリでの表示内容を共有するには、HoloLens が[開発者モード](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a958-160">Sharing what you see via Windows Device Portal or Microsoft HoloLens companion app requires your HoloLens to be in [Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal).</span></span>

### <span data-ttu-id="1a958-161">Miracast を使用したビデオのストリーミング</span><span class="sxs-lookup"><span data-stu-id="1a958-161">Stream video with Miracast</span></span>

<span data-ttu-id="1a958-162">開始ジェスチャを使用して [**スタート**] に移動し、[**接続**] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="1a958-162">Use the Start gesture to go to **Start**, then select the **connect** icon.</span></span> <span data-ttu-id="1a958-163">表示されるピッカーで、接続する Miracast 対応デバイスまたはアダプターを選択します。</span><span class="sxs-lookup"><span data-stu-id="1a958-163">From the picker that appears, select the Miracast-enabled device or adapter to which you want to connect.</span></span>

<span data-ttu-id="1a958-164">共有を停止するには、開始ジェスチャを使用し、強調表示されている**接続**アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="1a958-164">To stop sharing, use the Start gesture and select the highlighted **connect** icon.</span></span> <span data-ttu-id="1a958-165">ストリーミングを行っているため、デバイスに何も保存されません。</span><span class="sxs-lookup"><span data-stu-id="1a958-165">Because you were streaming, nothing will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="1a958-166">Miracast のサポートは、 [Windows 10 年 2018 10 月の更新プログラム](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)以降、HoloLens (第1世代) で有効にされています。</span><span class="sxs-lookup"><span data-stu-id="1a958-166">Miracast support was enabled on HoloLens (1st gen) beginning with the [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018).</span></span>

### <span data-ttu-id="1a958-167">Windows Device Portal を使ったリアルタイムビデオ</span><span class="sxs-lookup"><span data-stu-id="1a958-167">Real time video with Windows Device Portal</span></span>

<span data-ttu-id="1a958-168">Windows Device Portal で共有するには、HoloLens で開発者モードが有効になっている必要があるため、開発者向けドキュメントの指示に従って[開発者モードを設定し、Windows Device portal に移動](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)します。</span><span class="sxs-lookup"><span data-stu-id="1a958-168">Because sharing via Windows Device Portal requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode and navigate Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

### <span data-ttu-id="1a958-169">Microsoft HoloLens コンパニオンアプリ</span><span class="sxs-lookup"><span data-stu-id="1a958-169">Microsoft HoloLens companion app</span></span>

<span data-ttu-id="1a958-170">Microsoft HoloLens コンパニオンアプリで共有するには、HoloLens で開発者モードが有効になっている必要があるため、開発者向けドキュメントの指示に従って[開発者モードを設定](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)してください。</span><span class="sxs-lookup"><span data-stu-id="1a958-170">Because sharing via the Microsoft HoloLens companion app requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="1a958-171">次に、 [Microsoft HoloLens コンパニオンアプリ](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)をダウンロードして、アプリ内の指示に従って HoloLens に接続します。</span><span class="sxs-lookup"><span data-stu-id="1a958-171">Then, download the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) and follow the instructions within the app to connect to your HoloLens.</span></span>

<span data-ttu-id="1a958-172">アプリが HoloLens で設定されたら、アプリのメインメニューから [**ライブストリーム**] オプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="1a958-172">Once the app is set up with your HoloLens, select the **Live stream** option from the app's main menu.</span></span>

## <span data-ttu-id="1a958-173">Mixed reality の写真とビデオを表示する</span><span class="sxs-lookup"><span data-stu-id="1a958-173">View your mixed reality photos and videos</span></span>

<span data-ttu-id="1a958-174">Mixed reality の写真とビデオは、デバイスの "カメラロール" に保存されます。</span><span class="sxs-lookup"><span data-stu-id="1a958-174">Mixed reality photos and videos are saved to the device's "Camera Roll".</span></span> <span data-ttu-id="1a958-175">HoloLens でこのフォルダーの内容を参照するには、エクスプローラーアプリを使用します ([ピクチャ > カメラロール] に移動します)。</span><span class="sxs-lookup"><span data-stu-id="1a958-175">You can browse the contents of this folder on your HoloLens with the File Explorer app (navigate to Pictures > Camera Roll).</span></span>

<span data-ttu-id="1a958-176">また、mixed reality の写真やビデオを、HoloLens にプレインストールされている写真アプリで表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a958-176">You can also view your mixed reality photos and videos in the Photos app, which is pre-installed on HoloLens.</span></span> <span data-ttu-id="1a958-177">世界中の写真をピン留めするには、写真アプリで写真を選択し、[**混合世界で配置**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a958-177">To pin a photo in your world, select it in the Photos app and choose **Place in mixed world**.</span></span> <span data-ttu-id="1a958-178">世界中の写真は、配置後に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="1a958-178">You can move the photo around your world after it's been placed.</span></span>

<span data-ttu-id="1a958-179">HoloLens に接続された PC で mixed reality の写真やビデオを表示したり保存したりするには、 [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)または[pc のエクスプローラーを MTP 経由](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)で使うことができます。</span><span class="sxs-lookup"><span data-stu-id="1a958-179">To view and/or save your mixed reality photos and videos on a PC connected to HoloLens, you can use [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) or your [PC's File Explorer via MTP](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens).</span></span>

## <span data-ttu-id="1a958-180">Mixed reality の写真とビデオを共有する</span><span class="sxs-lookup"><span data-stu-id="1a958-180">Share your mixed reality photos and videos</span></span>

<span data-ttu-id="1a958-181">Mixed reality の写真やビデオをキャプチャすると、プレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a958-181">After capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="1a958-182">プレビューの上にある [**共有**] アイコンを選択して、共有アシスタントを表示します。</span><span class="sxs-lookup"><span data-stu-id="1a958-182">Select the **share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="1a958-183">そこから、写真やビデオを共有するエンドポイントを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1a958-183">From there, you can select the end point to which you'd like to share that photo or video.</span></span>

<span data-ttu-id="1a958-184">また、mixed reality 写真とビデオを自動的にアップロードすることで、OneDrive から mixed reality 写真とビデオを共有することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a958-184">You can also share mixed reality photos and videos from OneDrive, by automatically uploading your mixed reality photos and videos.</span></span> <span data-ttu-id="1a958-185">HoloLens で OneDrive アプリを開き、個人の[Microsoft アカウント](https://account.microsoft.com)でサインインします (まだインストールしていない場合)。</span><span class="sxs-lookup"><span data-stu-id="1a958-185">Open the OneDrive app on HoloLens and sign in with a personal [Microsoft account](https://account.microsoft.com) if you haven't already.</span></span> <span data-ttu-id="1a958-186">[**設定**] アイコンを選択し、[**カメラアップロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a958-186">Select the **settings** icon and choose **Camera upload**.</span></span> <span data-ttu-id="1a958-187">カメラのアップロードをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1a958-187">Turn Camera upload on.</span></span> <span data-ttu-id="1a958-188">Mixed reality の写真とビデオは、HoloLens でアプリを起動するたびに OneDrive にアップロードされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1a958-188">Your mixed reality photos and videos will now be uploaded to OneDrive each time you launch the app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="1a958-189">個人用の Microsoft アカウントで OneDrive にサインインしている場合のみ、OneDrive でカメラアップロードを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1a958-189">You can only enable camera upload in OneDrive if you’re signed into OneDrive with a personal Microsoft account.</span></span> <span data-ttu-id="1a958-190">HoloLens または学校のアカウントを使用して HoloLens をセットアップした場合は、OneDrive アプリで個人用の Microsoft アカウントを追加して、この機能を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1a958-190">If you set up HoloLens with a work or school account, you can add a personal Microsoft account in the OneDrive app to enable this feature.</span></span>

## <span data-ttu-id="1a958-191">Mixed reality キャプチャの制限事項</span><span class="sxs-lookup"><span data-stu-id="1a958-191">Limitations of mixed reality capture</span></span>

- <span data-ttu-id="1a958-192">Mixed reality キャプチャを使う場合、HoloLens のフレームレートは 30 Hz に半減します。</span><span class="sxs-lookup"><span data-stu-id="1a958-192">While using mixed reality capture, the framerate of HoloLens will be halved to 30 Hz.</span></span>
- <span data-ttu-id="1a958-193">ビデオの最大文字数は5分です。</span><span class="sxs-lookup"><span data-stu-id="1a958-193">Videos have a maximum length of five minutes.</span></span>
- <span data-ttu-id="1a958-194">写真/ビデオカメラが別のアプリケーションで既に使用されている場合、ライブストリーミング中、またはシステムリソースが少ない場合は、写真やビデオの解像度が低くなることがあります。</span><span class="sxs-lookup"><span data-stu-id="1a958-194">The resolution of photos and videos may be reduced if the photo/video camera is already in use by another application, while live streaming, or when system resources are low.</span></span>

## <span data-ttu-id="1a958-195">既定のファイル形式と解像度</span><span class="sxs-lookup"><span data-stu-id="1a958-195">Default file format and resolution</span></span>

### <span data-ttu-id="1a958-196">既定の写真の形式と解像度</span><span class="sxs-lookup"><span data-stu-id="1a958-196">Default photo format and resolution</span></span>

|  <span data-ttu-id="1a958-197">デバイス</span><span class="sxs-lookup"><span data-stu-id="1a958-197">Device</span></span>  |  <span data-ttu-id="1a958-198">形式</span><span class="sxs-lookup"><span data-stu-id="1a958-198">Format</span></span>  |  <span data-ttu-id="1a958-199">拡張機能</span><span class="sxs-lookup"><span data-stu-id="1a958-199">Extension</span></span>  |  <span data-ttu-id="1a958-200">解決方法</span><span class="sxs-lookup"><span data-stu-id="1a958-200">Resolution</span></span>  |
|----------|----------|----------|----------|
| <span data-ttu-id="1a958-201">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="1a958-201">HoloLens 2</span></span> | [<span data-ttu-id="1a958-202">JPEG</span><span class="sxs-lookup"><span data-stu-id="1a958-202">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="1a958-203">.jpg</span><span class="sxs-lookup"><span data-stu-id="1a958-203">.jpg</span></span> | <span data-ttu-id="1a958-204">3904x2196px</span><span class="sxs-lookup"><span data-stu-id="1a958-204">3904x2196px</span></span> |
| <span data-ttu-id="1a958-205">HoloLens (第1世代)</span><span class="sxs-lookup"><span data-stu-id="1a958-205">HoloLens (1st gen)</span></span> | [<span data-ttu-id="1a958-206">JPEG</span><span class="sxs-lookup"><span data-stu-id="1a958-206">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="1a958-207">.jpg</span><span class="sxs-lookup"><span data-stu-id="1a958-207">.jpg</span></span> | <span data-ttu-id="1a958-208">1408x79 2px</span><span class="sxs-lookup"><span data-stu-id="1a958-208">1408x792px</span></span> |

### <span data-ttu-id="1a958-209">記録されたビデオ形式と解像度</span><span class="sxs-lookup"><span data-stu-id="1a958-209">Recorded video format and resolution</span></span>

| <span data-ttu-id="1a958-210">デバイス</span><span class="sxs-lookup"><span data-stu-id="1a958-210">Device</span></span> | <span data-ttu-id="1a958-211">形式</span><span class="sxs-lookup"><span data-stu-id="1a958-211">Format</span></span> | <span data-ttu-id="1a958-212">拡張機能</span><span class="sxs-lookup"><span data-stu-id="1a958-212">Extension</span></span> | <span data-ttu-id="1a958-213">解決方法</span><span class="sxs-lookup"><span data-stu-id="1a958-213">Resolution</span></span> | <span data-ttu-id="1a958-214">速度</span><span class="sxs-lookup"><span data-stu-id="1a958-214">Speed</span></span> | <span data-ttu-id="1a958-215">オーディオ</span><span class="sxs-lookup"><span data-stu-id="1a958-215">Audio</span></span> |
|----------|----------|----------|----------|----------|----------|
| <span data-ttu-id="1a958-216">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="1a958-216">HoloLens 2</span></span> | [<span data-ttu-id="1a958-217">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="1a958-217">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="1a958-218">.mp4</span><span class="sxs-lookup"><span data-stu-id="1a958-218">.mp4</span></span> | <span data-ttu-id="1a958-219">1920x1080px</span><span class="sxs-lookup"><span data-stu-id="1a958-219">1920x1080px</span></span> | <span data-ttu-id="1a958-220">30fps</span><span class="sxs-lookup"><span data-stu-id="1a958-220">30fps</span></span> | <span data-ttu-id="1a958-221">48 Khz ステレオ</span><span class="sxs-lookup"><span data-stu-id="1a958-221">48kHz Stereo</span></span> |
| <span data-ttu-id="1a958-222">HoloLens (第1世代)</span><span class="sxs-lookup"><span data-stu-id="1a958-222">HoloLens (1st gen)</span></span> |  [<span data-ttu-id="1a958-223">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="1a958-223">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="1a958-224">.mp4</span><span class="sxs-lookup"><span data-stu-id="1a958-224">.mp4</span></span> | <span data-ttu-id="1a958-225">1216x684px</span><span class="sxs-lookup"><span data-stu-id="1a958-225">1216x684px</span></span> | <span data-ttu-id="1a958-226">24fps</span><span class="sxs-lookup"><span data-stu-id="1a958-226">24fps</span></span> | <span data-ttu-id="1a958-227">48 Khz ステレオ</span><span class="sxs-lookup"><span data-stu-id="1a958-227">48kHz Stereo</span></span> |
