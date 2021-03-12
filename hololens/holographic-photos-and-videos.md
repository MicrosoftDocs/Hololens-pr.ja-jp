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
# <a name="create-mixed-reality-photos-and-videos"></a><span data-ttu-id="6e4e5-105">Mixed Reality の写真とビデオを作成する</span><span class="sxs-lookup"><span data-stu-id="6e4e5-105">Create mixed reality photos and videos</span></span>

<span data-ttu-id="6e4e5-106">HoloLens は、現実世界とデジタル世界を混在するエクスペリエンスをユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-106">HoloLens gives users the experience of mixing the real world with the digital world.</span></span>  <span data-ttu-id="6e4e5-107">複合現実キャプチャ (MRC) を使用すると、そのエクスペリエンスを写真やビデオとしてキャプチャしたり、見た情報をリアルタイムで他のユーザーと共有することができます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-107">Mixed reality capture (MRC) lets you capture that experience as a photo or video, or share what you see with others in real-time.</span></span>

<span data-ttu-id="6e4e5-108">複合現実のキャプチャでは、一人一人の視点を使用して、他のユーザーがホログラムを表示できます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-108">Mixed reality capture uses a first-person point of view so other people can see holograms as you see them.</span></span> <span data-ttu-id="6e4e5-109">第三者視点の場合は、スペクテーター [ビューを使用します](https://docs.microsoft.com/windows/mixed-reality/spectator-view)。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-109">For a third-person point of view, use [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view).</span></span> <span data-ttu-id="6e4e5-110">Spectator ビューは、デモに特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-110">Spectator view is especially useful for demos.</span></span>

<span data-ttu-id="6e4e5-111">友人や同僚の間でビデオを共有するのも楽しい一方で、ビデオは他のユーザーにアプリの使用を教えることや、アプリやエクスペリエンスと問題を伝えるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-111">While it's fun to share videos amongst friends and colleagues, videos can also help teach other people to use an app or to communicate problems with apps and experiences.</span></span>

> [!NOTE]
> <span data-ttu-id="6e4e5-112">複合現実キャプチャ エクスペリエンスを起動できない場合、HoloLens が作業デバイスである場合は、システム管理者に確認してください。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-112">If you can't launch mixed reality capture experiences and your HoloLens is a work device, check with your system administrator.</span></span> <span data-ttu-id="6e4e5-113">カメラへのアクセスは、会社のポリシーを通じて制限できます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-113">Access to the camera can be restricted through company policy.</span></span>

## <a name="capture-a-mixed-reality-photo"></a><span data-ttu-id="6e4e5-114">複合現実の写真をキャプチャする</span><span class="sxs-lookup"><span data-stu-id="6e4e5-114">Capture a mixed reality photo</span></span>

<span data-ttu-id="6e4e5-115">HoloLens で複合現実の写真を撮る方法は複数あります。ハードウェア ボタン、音声、または [スタート] メニューを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-115">There are several ways to take a photo of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <a name="hardware-buttons-to-take-photos"></a><span data-ttu-id="6e4e5-116">写真を撮るハードウェア ボタン</span><span class="sxs-lookup"><span data-stu-id="6e4e5-116">Hardware buttons to take photos</span></span>

<span data-ttu-id="6e4e5-117">現在のビューの簡単な写真を撮る場合は、音量を上げ、音量を下げボタンを同時に押します。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-117">To take a quick photo of your current view, press the volume up and volume down buttons at the same time.</span></span>  <span data-ttu-id="6e4e5-118">これは、スクリーンショットまたは印刷画面の HoloLens バージョンと少し似たものになります。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-118">This is a bit like the HoloLens version of a screenshot or print screen.</span></span>

- [<span data-ttu-id="6e4e5-119">HoloLens 2 のボタンの場所</span><span class="sxs-lookup"><span data-stu-id="6e4e5-119">Button locations on HoloLens 2</span></span>](hololens2-hardware.md)
- [<span data-ttu-id="6e4e5-120">HoloLens のボタンの場所 (第 1 世代)</span><span class="sxs-lookup"><span data-stu-id="6e4e5-120">Button locations on HoloLens (1st gen)</span></span>](hololens1-hardware.md#hololens-components)

> [!NOTE]
> <span data-ttu-id="6e4e5-121">音量を**上げ、\*\*\*\*音量を**下げボタンを 3 秒間押すと、写真を撮るのではなく、ビデオの記録が開始されます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-121">Holding the **volume up** and **volume down** buttons for three seconds will start recording a video rather than taking a photo.</span></span> <span data-ttu-id="6e4e5-122">録音を停止するには、音量アップ**ボタンと音量ダウンボタン\*\*\*\*の両方を**同時にタップします。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-122">To stop recording, tap both **volume up** and **volume down** buttons simultaneously.</span></span>

### <a name="voice-commands-to-take-photos"></a><span data-ttu-id="6e4e5-123">写真を撮る音声コマンド</span><span class="sxs-lookup"><span data-stu-id="6e4e5-123">Voice commands to take photos</span></span>

<span data-ttu-id="6e4e5-124">HoloLens 2 バージョン 2004 以降では、「写真を撮る」と言います。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-124">On HoloLens 2, version 2004 (and later), say: "Take a picture."</span></span>

<span data-ttu-id="6e4e5-125">HoloLens (第 1 世代) または HoloLens 2 バージョン 1903 では、「コルタナさん、写真を撮って」と言います。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-125">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, take a picture."</span></span>

### <a name="start-menu-to-take-photos"></a><span data-ttu-id="6e4e5-126">写真を撮るスタート メニュー</span><span class="sxs-lookup"><span data-stu-id="6e4e5-126">Start menu to take photos</span></span>

<span data-ttu-id="6e4e5-127">Start ジェスチャを使用して [スタート] に **移動し**、カメラ アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-127">Use the Start gesture to go to **Start**, then select the **camera** icon.</span></span>

<span data-ttu-id="6e4e5-128">キャプチャする画像の方向に頭を向け、エア [タップ](hololens2-basic-usage.md#touch-holograms-near-you) で写真を撮る。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-128">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to take a photo.</span></span> <span data-ttu-id="6e4e5-129">引き続きエア タップして追加の写真をキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-129">You can continue to air tap and capture additional photos.</span></span> <span data-ttu-id="6e4e5-130">キャプチャした写真は、デバイスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-130">Any photos you capture will be saved to your device.</span></span>

<span data-ttu-id="6e4e5-131">写真のキャプチャを終了するには、もう一度 Start ジェスチャを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-131">Use the Start gesture again to end photo capture.</span></span>  

## <a name="capture-a-mixed-reality-video"></a><span data-ttu-id="6e4e5-132">複合現実のビデオをキャプチャする</span><span class="sxs-lookup"><span data-stu-id="6e4e5-132">Capture a mixed reality video</span></span>

<span data-ttu-id="6e4e5-133">HoloLens で複合現実のビデオを記録するには、いくつかの方法があります。ハードウェア ボタン、音声、または [スタート] メニューを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-133">There are several ways to record a video of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <a name="hardware-buttons-to-record-videos"></a><span data-ttu-id="6e4e5-134">ビデオを記録するハードウェア ボタン</span><span class="sxs-lookup"><span data-stu-id="6e4e5-134">Hardware buttons to record videos</span></span>

<span data-ttu-id="6e4e5-135">ビデオを記録する最も簡単な方法は、3\*\*\*\* 秒のカウントダウン\*\*\*\* が始まるまで音量を上げ、音量を下げボタンを同時に押し続けます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-135">The quickest way to record a video is to press and hold the **volume up** and **volume down** buttons simultaneously until a three-second countdown begins.</span></span> <span data-ttu-id="6e4e5-136">録音を停止するには、両方のボタンを同時にタップします。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-136">To stop recording, tap both buttons simultaneously.</span></span>

> [!NOTE]
> <span data-ttu-id="6e4e5-137">音量を上**げ、\*\*\*\*音量を**下げボタンを同時にすばやく押すと、ビデオを録画するのではなく、写真が撮影されます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-137">Quickly pressing the **volume up** and **volume down** buttons at the same time will take a photo rather than recording a video.</span></span>

### <a name="voice-to-record-videos"></a><span data-ttu-id="6e4e5-138">ビデオを録音する音声</span><span class="sxs-lookup"><span data-stu-id="6e4e5-138">Voice to record videos</span></span>

<span data-ttu-id="6e4e5-139">HoloLens 2 バージョン 2004 以降では、「録音を開始する」と言います。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-139">On HoloLens 2, version 2004 (and later), say: "Start recording."</span></span> <span data-ttu-id="6e4e5-140">録音を停止するには、「録音を停止する」と言います。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-140">To stop recording, say "Stop recording."</span></span>

<span data-ttu-id="6e4e5-141">HoloLens (第 1 世代) または HoloLens 2 バージョン 1903 では、「コルタナさん、録音を開始してください」と言います。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-141">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, start recording."</span></span> <span data-ttu-id="6e4e5-142">録音を停止するには、「コルタナさん、録音を停止してください」と言います。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-142">To stop recording, say "Hey Cortana, stop recording."</span></span>

### <a name="start-menu-to-record-videos"></a><span data-ttu-id="6e4e5-143">ビデオを記録するスタート メニュー</span><span class="sxs-lookup"><span data-stu-id="6e4e5-143">Start menu to record videos</span></span>

<span data-ttu-id="6e4e5-144">Start ジェスチャを使用して [スタート] に移動 **し**、ビデオ アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-144">Use the Start gesture to go to **Start**, then select the **video** icon.</span></span> <span data-ttu-id="6e4e5-145">キャプチャする情報の方向に頭を向け、エア [タップで録音](hololens2-basic-usage.md#touch-holograms-near-you) を開始します。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-145">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to start recording.</span></span> <span data-ttu-id="6e4e5-146">3 秒のカウントダウンが行い、録音が開始されます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-146">There will be a three second countdown and your recording will begin.</span></span>

<span data-ttu-id="6e4e5-147">録音を停止するには、スタート ジェスチャを使用して、強調表示されているビデオ アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-147">To stop recording, use the Start gesture and select the highlighted **video** icon.</span></span> <span data-ttu-id="6e4e5-148">ビデオはデバイスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-148">The video will be saved to your device.</span></span>

> [!NOTE]
> **<span data-ttu-id="6e4e5-149">HoloLens (第 1 世代) にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-149">Applies to HoloLens (1st gen) only</span></span>**  
> <span data-ttu-id="6e4e5-150">[Windows 10 10 月 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)は、HoloLens (第 1 世代) でのスタート ジェスチャと Windows ボタンの動作を変更します。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-150">The [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) changes how the Start gesture and Windows button behave on HoloLens (1st gen).</span></span> <span data-ttu-id="6e4e5-151">更新の前に、[スタート] ジェスチャまたは [Windows] ボタンがビデオ録画を停止します。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-151">Before the update, the Start gesture or Windows button would stop a video recording.</span></span> <span data-ttu-id="6e4e5-152">ただし、更新後、[スタート] ジェスチャまたは Windows ボタンをクリックすると、[スタート\*\*\*\*] メニュー (またはイマーシブ アプリの場合はクイック アクション メニュー \*\*\*\* ) が開き、強調表示されたビデオ アイコンを選択して録画を停止できます。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6e4e5-152">After the update, however, the Start gesture or Windows button opens the **Start** menu (or the **quick actions menu** if you are in an immersive app), from which you can select the highlighted **video** icon to stop recording.</span></span>

## <a name="share-what-you-see-in-real-time"></a><span data-ttu-id="6e4e5-153">リアルタイムで表示される情報を共有する</span><span class="sxs-lookup"><span data-stu-id="6e4e5-153">Share what you see in real-time</span></span>

<span data-ttu-id="6e4e5-154">HoloLens で見た情報を友人や同僚とリアルタイムで共有できます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-154">You can share what you see in HoloLens with friends and colleagues in real-time.</span></span> <span data-ttu-id="6e4e5-155">使用可能なメソッドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-155">There are a few methods available:</span></span>

1. <span data-ttu-id="6e4e5-156">Miracast 対応のデバイスまたはアダプターに接続してテレビで視聴する。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-156">Connecting to a Miracast-enabled device or adapter to watch on a TV.</span></span>
1. <span data-ttu-id="6e4e5-157">[Windows デバイス ポータルを使用](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)して PC で視聴する</span><span class="sxs-lookup"><span data-stu-id="6e4e5-157">Using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to watch on a PC</span></span>
1. <span data-ttu-id="6e4e5-158">Microsoft [HoloLens コンパニオン アプリを使用して](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) PC で視聴する。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-158">Using the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) to watch on a PC.</span></span>
1. <span data-ttu-id="6e4e5-159">[Microsoft Dynamics 365 リモート](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist)アシスト アプリを展開すると、フロント ラインのワーカーは、見た情報をリモートエキスパートにストリーミングできます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-159">Deploying the [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) app, which enables front-line workers to stream what they see to a remote expert.</span></span> <span data-ttu-id="6e4e5-160">リモートエキスパートは、第一線の作業員を口頭で、または自分の世界で注釈を付ける方法で案内できます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-160">The remote expert can then guide the front-line worker verbally or by annotating in their world.</span></span>

> [!NOTE]
> <span data-ttu-id="6e4e5-161">Windows デバイス ポータルまたは Microsoft HoloLens コンパニオン アプリを介して表示される情報を共有するには、HoloLens が開発者モードである [必要があります](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-161">Sharing what you see via Windows Device Portal or Microsoft HoloLens companion app requires your HoloLens to be in [Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal).</span></span>

### <a name="stream-video-with-miracast"></a><span data-ttu-id="6e4e5-162">Miracast を使用してビデオをストリーミングする</span><span class="sxs-lookup"><span data-stu-id="6e4e5-162">Stream video with Miracast</span></span>

<span data-ttu-id="6e4e5-163">Start ジェスチャを使用して [スタート] に **移動し**、接続アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-163">Use the Start gesture to go to **Start**, then select the **connect** icon.</span></span> <span data-ttu-id="6e4e5-164">表示されるピッカーから、接続する Miracast 対応デバイスまたはアダプターを選択します。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-164">From the picker that appears, select the Miracast-enabled device or adapter to which you want to connect.</span></span>

<span data-ttu-id="6e4e5-165">共有を停止するには、スタート ジェスチャを使用して、強調表示されている接続アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-165">To stop sharing, use the Start gesture and select the highlighted **connect** icon.</span></span> <span data-ttu-id="6e4e5-166">ストリーミングしていたので、デバイスには何も保存されません。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-166">Because you were streaming, nothing will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="6e4e5-167">Miracast のサポートは [、Windows 10 2018 年 10](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)月の更新プログラムで始まる HoloLens (第 1 世代) で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-167">Miracast support was enabled on HoloLens (1st gen) beginning with the [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018).</span></span>

### <a name="real-time-video-with-windows-device-portal"></a><span data-ttu-id="6e4e5-168">Windows デバイス ポータルを使用したリアルタイム ビデオ</span><span class="sxs-lookup"><span data-stu-id="6e4e5-168">Real time video with Windows Device Portal</span></span>

<span data-ttu-id="6e4e5-169">Windows デバイス ポータルを使用して共有するには、HoloLens で開発者モードを有効にする必要があります。開発者向けドキュメントの指示に従って開発者モードをセットアップし [、Windows デバイス ポータルを移動します](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-169">Because sharing via Windows Device Portal requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode and navigate Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

### <a name="microsoft-hololens-companion-app"></a><span data-ttu-id="6e4e5-170">Microsoft HoloLens コンパニオン アプリ</span><span class="sxs-lookup"><span data-stu-id="6e4e5-170">Microsoft HoloLens companion app</span></span>

<span data-ttu-id="6e4e5-171">Microsoft HoloLens コンパニオン アプリを使用して共有するには、HoloLens で開発者モードを有効にする必要があります。開発者向けドキュメントの指示に従って開発者モード [を設定します](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-171">Because sharing via the Microsoft HoloLens companion app requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="6e4e5-172">次に [、Microsoft HoloLens](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) コンパニオン アプリをダウンロードし、アプリ内の指示に従って HoloLens に接続します。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-172">Then, download the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) and follow the instructions within the app to connect to your HoloLens.</span></span>

<span data-ttu-id="6e4e5-173">HoloLens でアプリをセットアップしたら、アプリのメイン メニューから [ **ライブ** ストリーム] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-173">Once the app is set up with your HoloLens, select the **Live stream** option from the app's main menu.</span></span>

## <a name="view-your-mixed-reality-photos-and-videos"></a><span data-ttu-id="6e4e5-174">複合現実の写真とビデオを表示する</span><span class="sxs-lookup"><span data-stu-id="6e4e5-174">View your mixed reality photos and videos</span></span>

<span data-ttu-id="6e4e5-175">複合現実の写真とビデオは、デバイスの "カメラ ロール" に保存されます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-175">Mixed reality photos and videos are saved to the device's "Camera Roll".</span></span> <span data-ttu-id="6e4e5-176">HoloLens 上のこのフォルダーの内容は、エクスプローラー アプリで参照できます ([ピクチャ] >ロール)。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-176">You can browse the contents of this folder on your HoloLens with the File Explorer app (navigate to Pictures > Camera Roll).</span></span>

<span data-ttu-id="6e4e5-177">HoloLens にプレインストールされているフォト アプリで、複合現実の写真やビデオを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-177">You can also view your mixed reality photos and videos in the Photos app, which is pre-installed on HoloLens.</span></span> <span data-ttu-id="6e4e5-178">世界で写真をピン留めするには、[写真] アプリで写真を選択し、[混在世界に配置] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-178">To pin a photo in your world, select it in the Photos app and choose **Place in mixed world**.</span></span> <span data-ttu-id="6e4e5-179">写真を配置した後で、世界中の写真を移動できます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-179">You can move the photo around your world after it's been placed.</span></span>

<span data-ttu-id="6e4e5-180">HoloLens に接続された PC で複合現実の写真やビデオを表示および/または保存するには [、WINDOWS デバイス](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) ポータルまたは MTP 経由で PC の [エクスプローラーを使用できます](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-180">To view and/or save your mixed reality photos and videos on a PC connected to HoloLens, you can use [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) or your [PC's File Explorer via MTP](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens).</span></span>

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a><span data-ttu-id="6e4e5-181">エクスプローラーを使用して画像、ビデオ、ファイルを取得する</span><span class="sxs-lookup"><span data-stu-id="6e4e5-181">Use File Explorer to get your pictures, videos and files</span></span>

<span data-ttu-id="6e4e5-182">他のモバイル デバイスと同様に、HoloLens を PC に接続してエクスプローラーを起動し、HoloLens ライブラリ (写真、ビデオ、ドキュメント) にアクセスして簡単に転送できます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-182">Similar to other mobile devices, connect your HoloLens to your PC to bring up File Explorer to access your HoloLens libraries (photos, videos, documents) for easy transfer.</span></span> <span data-ttu-id="6e4e5-183">このメソッドは使いやすく、デバイス ポータルや Wi-Fi の使用は必要とされません。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-183">This method is easy to use and does not require the use of device portal or Wi-Fi.</span></span>

1. <span data-ttu-id="6e4e5-184">デバイスのロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-184">Unlock the device.</span></span>
1. <span data-ttu-id="6e4e5-185">USB 経由でデバイスを PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-185">Connect the device to a PC via USB.</span></span>
1. <span data-ttu-id="6e4e5-186">エクスプローラーが PC で開きます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-186">File Explorer should open on your PC.</span></span>
1. <span data-ttu-id="6e4e5-187">ナビゲート: この PC\\*yourhololensname*\Internal Storage\Pictures\Camera Roll</span><span class="sxs-lookup"><span data-stu-id="6e4e5-187">Navigate to: This PC\\*yourhololensname*\Internal Storage\Pictures\Camera Roll</span></span>
1. <span data-ttu-id="6e4e5-188">必要なファイルを PC にコピーします。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-188">Copy whatever files you need to your PC.</span></span>

<span data-ttu-id="6e4e5-189">ヒント: </span><span class="sxs-lookup"><span data-stu-id="6e4e5-189">Tips:</span></span>
- <span data-ttu-id="6e4e5-190">ファイルが表示されていない場合は、HoloLens にサインインしてデータへのアクセスを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-190">If you don't see any files, please ensure you sign in to your HoloLens to enable access to your data.</span></span>
- <span data-ttu-id="6e4e5-191">他のフォルダー内の他のファイル (診断ファイルなど) は [、Documents](hololens-diagnostic-logs.md#offline-diagnostics) フォルダーから取得できます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-191">You can get other files in other folders, such as [diagnostics files](hololens-diagnostic-logs.md#offline-diagnostics) from the Documents folder.</span></span>
- <span data-ttu-id="6e4e5-192">PC のエクスプローラーから [デバイスのプロパティ] を選択すると、Windows Holographic OS のバージョン番号 (ファームウェア バージョン)、デバイスシリアル番号、およびバッテリーの割合が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-192">From File Explorer on your PC, you can select Device properties to see Windows Holographic OS version number (firmware version), device serial number, and battery percentage.</span></span>
- <span data-ttu-id="6e4e5-193">組織が MDM を使用して [Connectivity/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) を無効にしている場合、デバイスに接続できません。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-193">If your Organization has used MDM to disable [Connectivity/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) then you will be unable to connect to your device.</span></span>

## <a name="share-your-mixed-reality-photos-and-videos"></a><span data-ttu-id="6e4e5-194">複合現実の写真とビデオを共有する</span><span class="sxs-lookup"><span data-stu-id="6e4e5-194">Share your mixed reality photos and videos</span></span>

<span data-ttu-id="6e4e5-195">複合現実の写真またはビデオをキャプチャすると、プレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-195">After capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="6e4e5-196">プレビューの **上にある** 共有アイコンを選択して、共有アシスタントを表示します。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-196">Select the **share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="6e4e5-197">そこから、その写真またはビデオを共有する終了点を選択できます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-197">From there, you can select the end point to which you'd like to share that photo or video.</span></span>

<span data-ttu-id="6e4e5-198">また、複合現実の写真とビデオを自動的にアップロードすることで、OneDrive から複合現実の写真やビデオを共有することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-198">You can also share mixed reality photos and videos from OneDrive, by automatically uploading your mixed reality photos and videos.</span></span> <span data-ttu-id="6e4e5-199">HoloLens で OneDrive アプリを開き、まだない場合は、 [個人用 Microsoft](https://account.microsoft.com) アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-199">Open the OneDrive app on HoloLens and sign in with a personal [Microsoft account](https://account.microsoft.com) if you haven't already.</span></span> <span data-ttu-id="6e4e5-200">設定アイコンを **選択し** 、[カメラのアップロード **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-200">Select the **settings** icon and choose **Camera upload**.</span></span> <span data-ttu-id="6e4e5-201">カメラのアップロードを有効にする。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-201">Turn Camera upload on.</span></span> <span data-ttu-id="6e4e5-202">HoloLens でアプリを起動する度に、複合現実の写真とビデオが OneDrive にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-202">Your mixed reality photos and videos will now be uploaded to OneDrive each time you launch the app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="6e4e5-203">OneDrive でカメラアップロードを有効にできるのは、個人用 Microsoft アカウントで OneDrive にサインインしている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-203">You can only enable camera upload in OneDrive if you’re signed into OneDrive with a personal Microsoft account.</span></span> <span data-ttu-id="6e4e5-204">仕事用または学校用のアカウントで HoloLens を設定する場合は、OneDrive アプリに個人用 Microsoft アカウントを追加して、この機能を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-204">If you set up HoloLens with a work or school account, you can add a personal Microsoft account in the OneDrive app to enable this feature.</span></span>

## <a name="limitations-of-mixed-reality-capture"></a><span data-ttu-id="6e4e5-205">複合現実キャプチャの制限</span><span class="sxs-lookup"><span data-stu-id="6e4e5-205">Limitations of mixed reality capture</span></span>

- <span data-ttu-id="6e4e5-206">複合現実キャプチャを使用している間、HoloLens のフレームレートは 30 Hz に半減されます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-206">While using mixed reality capture, the framerate of HoloLens will be halved to 30 Hz.</span></span>
- <span data-ttu-id="6e4e5-207">写真/ビデオ カメラが別のアプリケーションで既に使用されている場合、ライブ ストリーミング中、またはシステム リソースが低い場合は、写真やビデオの解像度が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-207">The resolution of photos and videos may be reduced if the photo/video camera is already in use by another application, while live streaming, or when system resources are low.</span></span>

### <a name="maximum-recording-length"></a><span data-ttu-id="6e4e5-208">最大記録長</span><span class="sxs-lookup"><span data-stu-id="6e4e5-208">Maximum recording length</span></span>

<span data-ttu-id="6e4e5-209">Windows Holographic より前の HoloLens 2 デバイスでは、デバイスに記録されたバージョン 20H2 ビデオは、最大 5 分の長さに制限されました。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-209">On HoloLens 2 devices before the Windows Holographic, version 20H2 videos recorded on the device were limited to maximum length of five minutes.</span></span>

<span data-ttu-id="6e4e5-210">お客様からのフィードバックにより、複合現実キャプチャの記録長 [が長くなっています](holographic-photos-and-videos.md)。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-210">Due to customer feedback we’ve increased the recording length of [mixed reality captures](holographic-photos-and-videos.md).</span></span> <span data-ttu-id="6e4e5-211">複合現実キャプチャは既定で 5 分に制限されなくなりましたが、代わりに使用可能なディスク領域に基づいて最大記録長が計算されます。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-211">Mixed reality captures will no longer be limited to 5 minutes by default but instead will calculate the maximum recording length based on available disk space.</span></span> <span data-ttu-id="6e4e5-212">デバイスは、使用可能なディスク領域に基づいて最大ビデオ録画時間を推定し、ディスク容量全体の最大 80% を占める。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-212">The device will estimate the max video recording duration based on available disk space up to 80% of the total disk space.</span></span>

> [!NOTE]
> <span data-ttu-id="6e4e5-213">HoloLens は、次のいずれかの場合、既定のビデオ録画の長さ (5 分) を使用します。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-213">The HoloLens will use default video recording length (5 minutes) if one of the following occurs:</span></span>
> - <span data-ttu-id="6e4e5-214">推定最大記録時間は、既定の 5 分よりも短い値です。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-214">The estimated max recording duration is smaller than the default 5 mins.</span></span>
> - <span data-ttu-id="6e4e5-215">使用可能なディスク領域は、ディスク領域全体の 20% 未満です。</span><span class="sxs-lookup"><span data-stu-id="6e4e5-215">The available disk space is less than 20% of the total disk space.</span></span>

## <a name="default-file-format-and-resolution"></a><span data-ttu-id="6e4e5-216">既定のファイル形式と解像度</span><span class="sxs-lookup"><span data-stu-id="6e4e5-216">Default file format and resolution</span></span>

### <a name="default-photo-format-and-resolution"></a><span data-ttu-id="6e4e5-217">既定の写真の形式と解像度</span><span class="sxs-lookup"><span data-stu-id="6e4e5-217">Default photo format and resolution</span></span>

|  <span data-ttu-id="6e4e5-218">デバイス</span><span class="sxs-lookup"><span data-stu-id="6e4e5-218">Device</span></span>  |  <span data-ttu-id="6e4e5-219">形式</span><span class="sxs-lookup"><span data-stu-id="6e4e5-219">Format</span></span>  |  <span data-ttu-id="6e4e5-220">拡張機能</span><span class="sxs-lookup"><span data-stu-id="6e4e5-220">Extension</span></span>  |  <span data-ttu-id="6e4e5-221">解決方法</span><span class="sxs-lookup"><span data-stu-id="6e4e5-221">Resolution</span></span>  |
|----------|----------|----------|----------|
| <span data-ttu-id="6e4e5-222">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="6e4e5-222">HoloLens 2</span></span> | [<span data-ttu-id="6e4e5-223">JPEG</span><span class="sxs-lookup"><span data-stu-id="6e4e5-223">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="6e4e5-224">.jpg</span><span class="sxs-lookup"><span data-stu-id="6e4e5-224">.jpg</span></span> | <span data-ttu-id="6e4e5-225">3904x2196px</span><span class="sxs-lookup"><span data-stu-id="6e4e5-225">3904x2196px</span></span> |
| <span data-ttu-id="6e4e5-226">HoloLens (第 1 世代)</span><span class="sxs-lookup"><span data-stu-id="6e4e5-226">HoloLens (1st gen)</span></span> | [<span data-ttu-id="6e4e5-227">JPEG</span><span class="sxs-lookup"><span data-stu-id="6e4e5-227">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="6e4e5-228">.jpg</span><span class="sxs-lookup"><span data-stu-id="6e4e5-228">.jpg</span></span> | <span data-ttu-id="6e4e5-229">1408x792px</span><span class="sxs-lookup"><span data-stu-id="6e4e5-229">1408x792px</span></span> |

### <a name="recorded-video-format-and-resolution"></a><span data-ttu-id="6e4e5-230">録画されたビデオの形式と解像度</span><span class="sxs-lookup"><span data-stu-id="6e4e5-230">Recorded video format and resolution</span></span>

| <span data-ttu-id="6e4e5-231">デバイス</span><span class="sxs-lookup"><span data-stu-id="6e4e5-231">Device</span></span> | <span data-ttu-id="6e4e5-232">形式</span><span class="sxs-lookup"><span data-stu-id="6e4e5-232">Format</span></span> | <span data-ttu-id="6e4e5-233">拡張機能</span><span class="sxs-lookup"><span data-stu-id="6e4e5-233">Extension</span></span> | <span data-ttu-id="6e4e5-234">解決方法</span><span class="sxs-lookup"><span data-stu-id="6e4e5-234">Resolution</span></span> | <span data-ttu-id="6e4e5-235">速度</span><span class="sxs-lookup"><span data-stu-id="6e4e5-235">Speed</span></span> | <span data-ttu-id="6e4e5-236">オーディオ</span><span class="sxs-lookup"><span data-stu-id="6e4e5-236">Audio</span></span> |
|----------|----------|----------|----------|----------|----------|
| <span data-ttu-id="6e4e5-237">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="6e4e5-237">HoloLens 2</span></span> | [<span data-ttu-id="6e4e5-238">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="6e4e5-238">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="6e4e5-239">.mp4</span><span class="sxs-lookup"><span data-stu-id="6e4e5-239">.mp4</span></span> | <span data-ttu-id="6e4e5-240">1920x1080px</span><span class="sxs-lookup"><span data-stu-id="6e4e5-240">1920x1080px</span></span> | <span data-ttu-id="6e4e5-241">30fps</span><span class="sxs-lookup"><span data-stu-id="6e4e5-241">30fps</span></span> | <span data-ttu-id="6e4e5-242">48kHz ステレオ</span><span class="sxs-lookup"><span data-stu-id="6e4e5-242">48kHz Stereo</span></span> |
| <span data-ttu-id="6e4e5-243">HoloLens (第 1 世代)</span><span class="sxs-lookup"><span data-stu-id="6e4e5-243">HoloLens (1st gen)</span></span> |  [<span data-ttu-id="6e4e5-244">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="6e4e5-244">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="6e4e5-245">.mp4</span><span class="sxs-lookup"><span data-stu-id="6e4e5-245">.mp4</span></span> | <span data-ttu-id="6e4e5-246">1216x684px</span><span class="sxs-lookup"><span data-stu-id="6e4e5-246">1216x684px</span></span> | <span data-ttu-id="6e4e5-247">24fps</span><span class="sxs-lookup"><span data-stu-id="6e4e5-247">24fps</span></span> | <span data-ttu-id="6e4e5-248">48kHz ステレオ</span><span class="sxs-lookup"><span data-stu-id="6e4e5-248">48kHz Stereo</span></span> |
