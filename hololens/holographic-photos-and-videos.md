---
title: Mixed Reality の写真とビデオのキャプチャと管理
description: HoloLens Mixed Reality デバイスを使って Mixed Reality の写真やビデオをキャプチャ、表示、共有する方法について学習します。
keywords: hololens, 写真, ビデオ, キャプチャ, mrc, Mixed Reality キャプチャ, 写真, カメラ, ストリーム, ライブストリーム, デモ
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
ms.openlocfilehash: 6b7bb29ab76a16aa518ca38ee04f434dfd0cf0c7
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283508"
---
# <span data-ttu-id="99afa-104">Mixed Reality の写真とビデオを作成する</span><span class="sxs-lookup"><span data-stu-id="99afa-104">Create mixed reality photos and videos</span></span>

<span data-ttu-id="99afa-105">HoloLens は、現実世界とデジタル世界を混在するエクスペリエンスをユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="99afa-105">HoloLens gives users the experience of mixing the real world with the digital world.</span></span>  <span data-ttu-id="99afa-106">Mixed Reality キャプチャ (MRC) を使うと、そのエクスペリエンスを写真やビデオとしてキャプチャしたり、見た情報をリアルタイムで他のユーザーと共有することができます。</span><span class="sxs-lookup"><span data-stu-id="99afa-106">Mixed reality capture (MRC) lets you capture that experience as a photo or video, or share what you see with others in real-time.</span></span>

<span data-ttu-id="99afa-107">Mixed Reality キャプチャでは、一人一人の視点を使用して、他のユーザーがホログラムを見て見る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="99afa-107">Mixed reality capture uses a first-person point of view so other people can see holograms as you see them.</span></span> <span data-ttu-id="99afa-108">第三者視点の場合は、視点 [ビューを使用します](https://docs.microsoft.com/windows/mixed-reality/spectator-view)。</span><span class="sxs-lookup"><span data-stu-id="99afa-108">For a third-person point of view, use [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view).</span></span> <span data-ttu-id="99afa-109">Spectator ビューは、デモに特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="99afa-109">Spectator view is especially useful for demos.</span></span>

<span data-ttu-id="99afa-110">友人や同僚の間でビデオを共有するのも楽しい一方で、ビデオは他のユーザーにアプリの使用やアプリやエクスペリエンスの問題の伝達を教えるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="99afa-110">While it's fun to share videos amongst friends and colleagues, videos can also help teach other people to use an app or to communicate problems with apps and experiences.</span></span>

> [!NOTE]
> <span data-ttu-id="99afa-111">Mixed Reality キャプチャ エクスペリエンスを起動できない場合、HoloLens が作業デバイスである場合は、システム管理者に確認してください。</span><span class="sxs-lookup"><span data-stu-id="99afa-111">If you can't launch mixed reality capture experiences and your HoloLens is a work device, check with your system administrator.</span></span> <span data-ttu-id="99afa-112">会社のポリシーを通じてカメラへのアクセスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="99afa-112">Access to the camera can be restricted through company policy.</span></span>

## <span data-ttu-id="99afa-113">Mixed Reality の写真をキャプチャする</span><span class="sxs-lookup"><span data-stu-id="99afa-113">Capture a mixed reality photo</span></span>

<span data-ttu-id="99afa-114">HoloLens で Mixed Reality の写真を撮影する方法は複数あります。ハードウェア ボタン、音声、またはスタート メニューを使用できます。</span><span class="sxs-lookup"><span data-stu-id="99afa-114">There are several ways to take a photo of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <span data-ttu-id="99afa-115">写真を撮影するハードウェア ボタン</span><span class="sxs-lookup"><span data-stu-id="99afa-115">Hardware buttons to take photos</span></span>

<span data-ttu-id="99afa-116">現在のビューの簡単な写真を撮影するには、音量を上げ、音量を下げボタンを同時に押します。</span><span class="sxs-lookup"><span data-stu-id="99afa-116">To take a quick photo of your current view, press the volume up and volume down buttons at the same time.</span></span>  <span data-ttu-id="99afa-117">これは、スクリーンショットや印刷画面の HoloLens バージョンと少し似たものになります。</span><span class="sxs-lookup"><span data-stu-id="99afa-117">This is a bit like the HoloLens version of a screenshot or print screen.</span></span>

- [<span data-ttu-id="99afa-118">HoloLens 2 のボタンの場所</span><span class="sxs-lookup"><span data-stu-id="99afa-118">Button locations on HoloLens 2</span></span>](hololens2-hardware.md)
- [<span data-ttu-id="99afa-119">HoloLens (第 1 世代) 上のボタンの場所</span><span class="sxs-lookup"><span data-stu-id="99afa-119">Button locations on HoloLens (1st gen)</span></span>](hololens1-hardware.md#hololens-components)

> [!NOTE]
> <span data-ttu-id="99afa-120">音量を**上げ、\*\*\*\*音量を下**げボタンを 3 秒間押すと、写真を撮影するのではなく、ビデオの録画が開始されます。</span><span class="sxs-lookup"><span data-stu-id="99afa-120">Holding the **volume up** and **volume down** buttons for three seconds will start recording a video rather than taking a photo.</span></span> <span data-ttu-id="99afa-121">録音を停止するには、音量を**上げ下げ\*\*\*\*ボタンと音量を下げボタンの両方を**同時にタップします。</span><span class="sxs-lookup"><span data-stu-id="99afa-121">To stop recording, tap both **volume up** and **volume down** buttons simultaneously.</span></span>

### <span data-ttu-id="99afa-122">写真を撮影する音声コマンド</span><span class="sxs-lookup"><span data-stu-id="99afa-122">Voice commands to take photos</span></span>

<span data-ttu-id="99afa-123">HoloLens 2 バージョン 2004 (以降) では、「写真を撮る」と言います。</span><span class="sxs-lookup"><span data-stu-id="99afa-123">On HoloLens 2, version 2004 (and later), say: "Take a picture."</span></span>

<span data-ttu-id="99afa-124">HoloLens (第 1 世代) または HoloLens 2 バージョン 1903 では、「コルタナさん、写真を撮って」と言います。</span><span class="sxs-lookup"><span data-stu-id="99afa-124">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, take a picture."</span></span>

### <span data-ttu-id="99afa-125">写真を撮影するスタート メニュー</span><span class="sxs-lookup"><span data-stu-id="99afa-125">Start menu to take photos</span></span>

<span data-ttu-id="99afa-126">スタート ジェスチャを使ってスタート画面に移動 **し、** カメラ アイコンを **選択** します。</span><span class="sxs-lookup"><span data-stu-id="99afa-126">Use the Start gesture to go to **Start**, then select the **camera** icon.</span></span>

<span data-ttu-id="99afa-127">キャプチャする画像の方向に頭を向け、エアタップで [写真を](hololens2-basic-usage.md#touch-holograms-near-you) 撮影します。</span><span class="sxs-lookup"><span data-stu-id="99afa-127">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to take a photo.</span></span> <span data-ttu-id="99afa-128">引き続きエアタップして、追加の写真をキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="99afa-128">You can continue to air tap and capture additional photos.</span></span> <span data-ttu-id="99afa-129">キャプチャした写真は、デバイスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="99afa-129">Any photos you capture will be saved to your device.</span></span>

<span data-ttu-id="99afa-130">写真のキャプチャを終了するには、もう一度スタート ジェスチャを使います。</span><span class="sxs-lookup"><span data-stu-id="99afa-130">Use the Start gesture again to end photo capture.</span></span>  

## <span data-ttu-id="99afa-131">Mixed Reality ビデオをキャプチャする</span><span class="sxs-lookup"><span data-stu-id="99afa-131">Capture a mixed reality video</span></span>

<span data-ttu-id="99afa-132">HoloLens で Mixed Reality のビデオを録画する方法は複数あります。ハードウェア ボタン、音声、またはスタート メニューを使用できます。</span><span class="sxs-lookup"><span data-stu-id="99afa-132">There are several ways to record a video of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <span data-ttu-id="99afa-133">ビデオを記録するハードウェア ボタン</span><span class="sxs-lookup"><span data-stu-id="99afa-133">Hardware buttons to record videos</span></span>

<span data-ttu-id="99afa-134">ビデオを記録する最も簡単な方法は、音量を上\*\*\*\* げ、音量\*\*\*\* を下げ、3 秒のカウントダウンが始まるまでボタンを同時に長押しする方法です。</span><span class="sxs-lookup"><span data-stu-id="99afa-134">The quickest way to record a video is to press and hold the **volume up** and **volume down** buttons simultaneously until a three-second countdown begins.</span></span> <span data-ttu-id="99afa-135">レコーディングを停止するには、両方のボタンを同時にタップします。</span><span class="sxs-lookup"><span data-stu-id="99afa-135">To stop recording, tap both buttons simultaneously.</span></span>

> [!NOTE]
> <span data-ttu-id="99afa-136">音量を上**げ、\*\*\*\*音量を下**げボタンを同時にすばやく押すと、ビデオを録画するのではなく、写真を撮影できます。</span><span class="sxs-lookup"><span data-stu-id="99afa-136">Quickly pressing the **volume up** and **volume down** buttons at the same time will take a photo rather than recording a video.</span></span>

### <span data-ttu-id="99afa-137">音声によるビデオの録音</span><span class="sxs-lookup"><span data-stu-id="99afa-137">Voice to record videos</span></span>

<span data-ttu-id="99afa-138">HoloLens 2 バージョン 2004 (以降) で、「記録を開始する」と言います。</span><span class="sxs-lookup"><span data-stu-id="99afa-138">On HoloLens 2, version 2004 (and later), say: "Start recording."</span></span> <span data-ttu-id="99afa-139">レコーディングを停止するには、「記録を停止する」と言います。</span><span class="sxs-lookup"><span data-stu-id="99afa-139">To stop recording, say "Stop recording."</span></span>

<span data-ttu-id="99afa-140">HoloLens (第 1 世代) または HoloLens 2 バージョン 1903 では、「コルタナさん、レコーディングを開始してください」と言います。</span><span class="sxs-lookup"><span data-stu-id="99afa-140">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, start recording."</span></span> <span data-ttu-id="99afa-141">レコーディングを停止するには、「Hey Cortana, stop recording」と言います。</span><span class="sxs-lookup"><span data-stu-id="99afa-141">To stop recording, say "Hey Cortana, stop recording."</span></span>

### <span data-ttu-id="99afa-142">ビデオを録画するスタート メニュー</span><span class="sxs-lookup"><span data-stu-id="99afa-142">Start menu to record videos</span></span>

<span data-ttu-id="99afa-143">スタート ジェスチャを使ってスタート画面に移動 **し、** ビデオ アイコンを **選択** します。</span><span class="sxs-lookup"><span data-stu-id="99afa-143">Use the Start gesture to go to **Start**, then select the **video** icon.</span></span> <span data-ttu-id="99afa-144">キャプチャする情報の方向に頭を向け、エア [タップ](hololens2-basic-usage.md#touch-holograms-near-you) でレコーディングを開始します。</span><span class="sxs-lookup"><span data-stu-id="99afa-144">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to start recording.</span></span> <span data-ttu-id="99afa-145">3 秒のカウントダウンが行い、レコーディングが開始されます。</span><span class="sxs-lookup"><span data-stu-id="99afa-145">There will be a three second countdown and your recording will begin.</span></span>

<span data-ttu-id="99afa-146">記録を停止するには、スタート ジェスチャを使って、強調表示されているビデオ アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="99afa-146">To stop recording, use the Start gesture and select the highlighted **video** icon.</span></span> <span data-ttu-id="99afa-147">ビデオはデバイスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="99afa-147">The video will be saved to your device.</span></span>

> [!NOTE]
> **<span data-ttu-id="99afa-148">HoloLens (第 1 世代) にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="99afa-148">Applies to HoloLens (1st gen) only</span></span>**  
> <span data-ttu-id="99afa-149">[Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)は、HoloLens (第 1 世代) でのスタート ジェスチャと Windows ボタンの動作を変更します。</span><span class="sxs-lookup"><span data-stu-id="99afa-149">The [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) changes how the Start gesture and Windows button behave on HoloLens (1st gen).</span></span> <span data-ttu-id="99afa-150">更新の前に、スタート ジェスチャまたは Windows ボタンはビデオ録画を停止します。</span><span class="sxs-lookup"><span data-stu-id="99afa-150">Before the update, the Start gesture or Windows button would stop a video recording.</span></span> <span data-ttu-id="99afa-151">ただし、更新後、スタート ジェスチャまたは Windows ボタンによってスタート メニュー (\*\*\*\* イマーシブ アプリの場合はクイック アクション メニュー) が開き、\*\*\*\* 強調表示されたビデオ アイコンを選択して録画を停止できます。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="99afa-151">After the update, however, the Start gesture or Windows button opens the **Start** menu (or the **quick actions menu** if you are in an immersive app), from which you can select the highlighted **video** icon to stop recording.</span></span>

## <span data-ttu-id="99afa-152">表示される情報をリアルタイムで共有する</span><span class="sxs-lookup"><span data-stu-id="99afa-152">Share what you see in real-time</span></span>

<span data-ttu-id="99afa-153">HoloLens で表示される情報を、友人や同僚とリアルタイムで共有できます。</span><span class="sxs-lookup"><span data-stu-id="99afa-153">You can share what you see in HoloLens with friends and colleagues in real-time.</span></span> <span data-ttu-id="99afa-154">いくつかの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="99afa-154">There are a few methods available:</span></span>

1. <span data-ttu-id="99afa-155">Miracast 対応デバイスまたはアダプターに接続してテレビで視聴する。</span><span class="sxs-lookup"><span data-stu-id="99afa-155">Connecting to a Miracast-enabled device or adapter to watch on a TV.</span></span>
1. <span data-ttu-id="99afa-156">[Windows Device Portal を使用](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)して PC で視聴する</span><span class="sxs-lookup"><span data-stu-id="99afa-156">Using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to watch on a PC</span></span>
1. <span data-ttu-id="99afa-157">Microsoft [HoloLens コンパニオン アプリを使って](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) PC で視聴する。</span><span class="sxs-lookup"><span data-stu-id="99afa-157">Using the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) to watch on a PC.</span></span>
1. <span data-ttu-id="99afa-158">[Microsoft Dynamics 365 リモート](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist)アシスト アプリを展開すると、フロント ライン ワーカーはリモートの専門家に表示される情報をストリーミングできます。</span><span class="sxs-lookup"><span data-stu-id="99afa-158">Deploying the [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) app, which enables front-line workers to stream what they see to a remote expert.</span></span> <span data-ttu-id="99afa-159">リモートの専門家は、フロント ライン ワーカーを言葉で、または自分の世界で注釈を付ける方法で案内できます。</span><span class="sxs-lookup"><span data-stu-id="99afa-159">The remote expert can then guide the front-line worker verbally or by annotating in their world.</span></span>

> [!NOTE]
> <span data-ttu-id="99afa-160">Windows Device Portal または Microsoft HoloLens コンパニオン アプリで表示される情報を共有するには、HoloLens が開発者モードである [必要があります](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="99afa-160">Sharing what you see via Windows Device Portal or Microsoft HoloLens companion app requires your HoloLens to be in [Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal).</span></span>

### <span data-ttu-id="99afa-161">Miracast を使ったストリーム ビデオ</span><span class="sxs-lookup"><span data-stu-id="99afa-161">Stream video with Miracast</span></span>

<span data-ttu-id="99afa-162">スタート ジェスチャを使ってスタート画面に移動 **し、** 接続アイコンを **選択** します。</span><span class="sxs-lookup"><span data-stu-id="99afa-162">Use the Start gesture to go to **Start**, then select the **connect** icon.</span></span> <span data-ttu-id="99afa-163">表示されるピッカーから、接続する Miracast 対応デバイスまたはアダプターを選択します。</span><span class="sxs-lookup"><span data-stu-id="99afa-163">From the picker that appears, select the Miracast-enabled device or adapter to which you want to connect.</span></span>

<span data-ttu-id="99afa-164">共有を停止するには、スタート ジェスチャを使って、強調表示されている接続アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="99afa-164">To stop sharing, use the Start gesture and select the highlighted **connect** icon.</span></span> <span data-ttu-id="99afa-165">ストリーミングしていたため、デバイスには何も保存されません。</span><span class="sxs-lookup"><span data-stu-id="99afa-165">Because you were streaming, nothing will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="99afa-166">Miracast のサポートは [、Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)から HoloLens (第 1 世代) で有効にされました。</span><span class="sxs-lookup"><span data-stu-id="99afa-166">Miracast support was enabled on HoloLens (1st gen) beginning with the [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018).</span></span>

### <span data-ttu-id="99afa-167">Windows Device Portal を使ったリアルタイム ビデオ</span><span class="sxs-lookup"><span data-stu-id="99afa-167">Real time video with Windows Device Portal</span></span>

<span data-ttu-id="99afa-168">Windows Device Portal を使用して共有するには、HoloLens で開発者モードを有効にする必要があります。開発者向けドキュメントの指示に従って、開発者モードをセットアップし [、Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)に移動します。</span><span class="sxs-lookup"><span data-stu-id="99afa-168">Because sharing via Windows Device Portal requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode and navigate Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

### <span data-ttu-id="99afa-169">Microsoft HoloLens コンパニオン アプリ</span><span class="sxs-lookup"><span data-stu-id="99afa-169">Microsoft HoloLens companion app</span></span>

<span data-ttu-id="99afa-170">Microsoft HoloLens コンパニオン アプリを使って共有するには、HoloLens で開発者モードを有効にする必要があります。開発者向けドキュメントの指示に従って、開発者モードを [設定します](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="99afa-170">Because sharing via the Microsoft HoloLens companion app requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="99afa-171">次に [、Microsoft HoloLens コンパニオン](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) アプリをダウンロードし、アプリ内の指示に従って HoloLens に接続します。</span><span class="sxs-lookup"><span data-stu-id="99afa-171">Then, download the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) and follow the instructions within the app to connect to your HoloLens.</span></span>

<span data-ttu-id="99afa-172">アプリを HoloLens でセットアップしたら、アプリのメイン メニューから **Live ストリーム** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="99afa-172">Once the app is set up with your HoloLens, select the **Live stream** option from the app's main menu.</span></span>

## <span data-ttu-id="99afa-173">Mixed Reality の写真とビデオを表示する</span><span class="sxs-lookup"><span data-stu-id="99afa-173">View your mixed reality photos and videos</span></span>

<span data-ttu-id="99afa-174">Mixed Reality の写真とビデオは、デバイスの "カメラ ロール" に保存されます。</span><span class="sxs-lookup"><span data-stu-id="99afa-174">Mixed reality photos and videos are saved to the device's "Camera Roll".</span></span> <span data-ttu-id="99afa-175">エクスプローラー アプリを使って、HoloLens でこのフォルダーの内容を参照できます ([ピクチャ] > [カメラ ロール] に移動します)。</span><span class="sxs-lookup"><span data-stu-id="99afa-175">You can browse the contents of this folder on your HoloLens with the File Explorer app (navigate to Pictures > Camera Roll).</span></span>

<span data-ttu-id="99afa-176">HoloLens にプレインストールされているフォト アプリで、Mixed Reality の写真やビデオを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="99afa-176">You can also view your mixed reality photos and videos in the Photos app, which is pre-installed on HoloLens.</span></span> <span data-ttu-id="99afa-177">自分の世界で写真をピン留めするには、フォト アプリで写真を選択し、[混在世界で **配置] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="99afa-177">To pin a photo in your world, select it in the Photos app and choose **Place in mixed world**.</span></span> <span data-ttu-id="99afa-178">写真を配置した後で、世界中に写真を移動できます。</span><span class="sxs-lookup"><span data-stu-id="99afa-178">You can move the photo around your world after it's been placed.</span></span>

<span data-ttu-id="99afa-179">HoloLens に接続された PC で Mixed Reality の写真やビデオを表示または保存するには [、MTP](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) を使って Windows Device Portal または PC の [エクスプローラーを使います](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="99afa-179">To view and/or save your mixed reality photos and videos on a PC connected to HoloLens, you can use [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) or your [PC's File Explorer via MTP](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens).</span></span>

### <span data-ttu-id="99afa-180">エクスプローラーを使って画像、ビデオ、ファイルを取得する</span><span class="sxs-lookup"><span data-stu-id="99afa-180">Use File Explorer to get your pictures, videos and files</span></span>

<span data-ttu-id="99afa-181">他のモバイル デバイスと同様に、HoloLens を PC に接続してエクスプローラーを表示し、HoloLens ライブラリ (写真、ビデオ、ドキュメント) にアクセスして簡単に転送できます。</span><span class="sxs-lookup"><span data-stu-id="99afa-181">Similar to other mobile devices, connect your HoloLens to your PC to bring up File Explorer to access your HoloLens libraries (photos, videos, documents) for easy transfer.</span></span> <span data-ttu-id="99afa-182">この方法は使いやすく、デバイス ポータルや Wi-Fi の使用は必要とされません。</span><span class="sxs-lookup"><span data-stu-id="99afa-182">This method is easy to use and does not require the use of device portal or Wi-Fi.</span></span>

1. <span data-ttu-id="99afa-183">デバイスのロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="99afa-183">Unlock the device.</span></span>
1. <span data-ttu-id="99afa-184">USB 経由でデバイスを PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="99afa-184">Connect the device to a PC via USB.</span></span>
1. <span data-ttu-id="99afa-185">エクスプローラーが PC で開きます。</span><span class="sxs-lookup"><span data-stu-id="99afa-185">File Explorer should open on your PC.</span></span>
1. <span data-ttu-id="99afa-186">[Navigate to]: This PC\\*yourhololensname*\Internal Storage\Pictures\Camera Roll</span><span class="sxs-lookup"><span data-stu-id="99afa-186">Navigate to: This PC\\*yourhololensname*\Internal Storage\Pictures\Camera Roll</span></span>
1. <span data-ttu-id="99afa-187">必要なファイルを PC にコピーします。</span><span class="sxs-lookup"><span data-stu-id="99afa-187">Copy whatever files you need to your PC.</span></span>

<span data-ttu-id="99afa-188">ヒント: </span><span class="sxs-lookup"><span data-stu-id="99afa-188">Tips:</span></span>
- <span data-ttu-id="99afa-189">ファイルが表示されていない場合は、HoloLens にサインインしてデータへのアクセスを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="99afa-189">If you don't see any files, please ensure you sign in to your HoloLens to enable access to your data.</span></span>
- <span data-ttu-id="99afa-190">[ドキュメント] フォルダーから診断ファイルなど、他のフォルダー内の [他](hololens-diagnostic-logs.md#offline-diagnostics) のファイルを取得できます。</span><span class="sxs-lookup"><span data-stu-id="99afa-190">You can get other files in other folders, such as [diagnostics files](hololens-diagnostic-logs.md#offline-diagnostics) from the Documents folder.</span></span>
- <span data-ttu-id="99afa-191">PC のエクスプローラーで[デバイスのプロパティ] を選択すると、Windows Holographic OS のバージョン番号 (ファームウェアバージョン)、デバイスのシリアル番号、バッテリの割合を確認できます。</span><span class="sxs-lookup"><span data-stu-id="99afa-191">From File Explorer on your PC, you can select Device properties to see Windows Holographic OS version number (firmware version), device serial number, and battery percentage.</span></span>
- <span data-ttu-id="99afa-192">組織が MDM を使用して [Connectivity/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) を無効にしている場合、デバイスに接続できません。</span><span class="sxs-lookup"><span data-stu-id="99afa-192">If your Organization has used MDM to disable [Connectivity/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) then you will be unable to connect to your device.</span></span>

## <span data-ttu-id="99afa-193">Mixed Reality の写真とビデオを共有する</span><span class="sxs-lookup"><span data-stu-id="99afa-193">Share your mixed reality photos and videos</span></span>

<span data-ttu-id="99afa-194">Mixed Reality の写真やビデオをキャプチャすると、プレビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="99afa-194">After capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="99afa-195">プレビューの **上にある** 共有アイコンを選択して、共有アシスタントを表示します。</span><span class="sxs-lookup"><span data-stu-id="99afa-195">Select the **share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="99afa-196">そこから、その写真またはビデオを共有するエンド ポイントを選択できます。</span><span class="sxs-lookup"><span data-stu-id="99afa-196">From there, you can select the end point to which you'd like to share that photo or video.</span></span>

<span data-ttu-id="99afa-197">Mixed Reality の写真やビデオを自動的にアップロードすることで、OneDrive から Mixed Reality の写真やビデオを共有することもできます。</span><span class="sxs-lookup"><span data-stu-id="99afa-197">You can also share mixed reality photos and videos from OneDrive, by automatically uploading your mixed reality photos and videos.</span></span> <span data-ttu-id="99afa-198">HoloLens で OneDrive アプリを開き、まだサインインしていない場合は、個人用 [の Microsoft](https://account.microsoft.com) アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="99afa-198">Open the OneDrive app on HoloLens and sign in with a personal [Microsoft account](https://account.microsoft.com) if you haven't already.</span></span> <span data-ttu-id="99afa-199">設定アイコンを **選択し** 、[カメラのアップロード **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="99afa-199">Select the **settings** icon and choose **Camera upload**.</span></span> <span data-ttu-id="99afa-200">カメラのアップロードを有効にする。</span><span class="sxs-lookup"><span data-stu-id="99afa-200">Turn Camera upload on.</span></span> <span data-ttu-id="99afa-201">HoloLens でアプリを起動するごとに、Mixed Reality の写真とビデオが OneDrive にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="99afa-201">Your mixed reality photos and videos will now be uploaded to OneDrive each time you launch the app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="99afa-202">OneDrive でカメラのアップロードを有効にできるのは、個人用の Microsoft アカウントで OneDrive にサインインしている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="99afa-202">You can only enable camera upload in OneDrive if you’re signed into OneDrive with a personal Microsoft account.</span></span> <span data-ttu-id="99afa-203">HoloLens を仕事または学校のアカウントでセットアップする場合は、OneDrive アプリで個人用の Microsoft アカウントを追加して、この機能を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="99afa-203">If you set up HoloLens with a work or school account, you can add a personal Microsoft account in the OneDrive app to enable this feature.</span></span>

## <span data-ttu-id="99afa-204">Mixed Reality キャプチャの制限事項</span><span class="sxs-lookup"><span data-stu-id="99afa-204">Limitations of mixed reality capture</span></span>

- <span data-ttu-id="99afa-205">Mixed Reality キャプチャを使用している間、HoloLens のフレームレートは 30 Hz に半分になります。</span><span class="sxs-lookup"><span data-stu-id="99afa-205">While using mixed reality capture, the framerate of HoloLens will be halved to 30 Hz.</span></span>
- <span data-ttu-id="99afa-206">写真/ビデオ カメラが別のアプリケーションで既に使用されている場合、ライブ ストリーミング中、またはシステム リソースが低い場合は、写真やビデオの解像度が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="99afa-206">The resolution of photos and videos may be reduced if the photo/video camera is already in use by another application, while live streaming, or when system resources are low.</span></span>

### <span data-ttu-id="99afa-207">最大録音長</span><span class="sxs-lookup"><span data-stu-id="99afa-207">Maximum recording length</span></span>

<span data-ttu-id="99afa-208">Windows Holographic より前の HoloLens 2 デバイスでは、デバイスに記録されたバージョン 20H2 のビデオは、最大で 5 分の長さに制限されました。</span><span class="sxs-lookup"><span data-stu-id="99afa-208">On HoloLens 2 devices before the Windows Holographic, version 20H2 videos recorded on the device were limited to maximum length of five minutes.</span></span>

<span data-ttu-id="99afa-209">お客様からのフィードバックにより、Mixed Reality キャプチャの記録 [の長さが長くなっています](holographic-photos-and-videos.md)。</span><span class="sxs-lookup"><span data-stu-id="99afa-209">Due to customer feedback we’ve increased the recording length of [mixed reality captures](holographic-photos-and-videos.md).</span></span> <span data-ttu-id="99afa-210">Mixed Reality キャプチャは既定で 5 分に制限されず、使用可能なディスク領域に基づいて最大記録長が計算されます。</span><span class="sxs-lookup"><span data-stu-id="99afa-210">Mixed reality captures will no longer be limited to 5 minutes by default but instead will calculate the maximum recording length based on available disk space.</span></span> <span data-ttu-id="99afa-211">デバイスは、利用可能なディスク領域に基づいてビデオ録画の最大再生時間を、合計ディスク領域の 80% まで推定します。</span><span class="sxs-lookup"><span data-stu-id="99afa-211">The device will estimate the max video recording duration based on available disk space up to 80% of the total disk space.</span></span>

> [!NOTE]
> <span data-ttu-id="99afa-212">次のいずれかの場合、HoloLens は既定のビデオ録画の長さ (5 分) を使用します。</span><span class="sxs-lookup"><span data-stu-id="99afa-212">The HoloLens will use default video recording length (5 minutes) if one of the following occurs:</span></span>
> - <span data-ttu-id="99afa-213">推定最大記録時間は、既定の 5 分よりも小さくてす。</span><span class="sxs-lookup"><span data-stu-id="99afa-213">The estimated max recording duration is smaller than the default 5 mins.</span></span>
> - <span data-ttu-id="99afa-214">使用可能なディスク領域は、ディスク領域全体の 20% 未満です。</span><span class="sxs-lookup"><span data-stu-id="99afa-214">The available disk space is less than 20% of the total disk space.</span></span>

## <span data-ttu-id="99afa-215">既定のファイル形式と解像度</span><span class="sxs-lookup"><span data-stu-id="99afa-215">Default file format and resolution</span></span>

### <span data-ttu-id="99afa-216">既定の写真の形式と解像度</span><span class="sxs-lookup"><span data-stu-id="99afa-216">Default photo format and resolution</span></span>

|  <span data-ttu-id="99afa-217">デバイス</span><span class="sxs-lookup"><span data-stu-id="99afa-217">Device</span></span>  |  <span data-ttu-id="99afa-218">形式</span><span class="sxs-lookup"><span data-stu-id="99afa-218">Format</span></span>  |  <span data-ttu-id="99afa-219">拡張機能</span><span class="sxs-lookup"><span data-stu-id="99afa-219">Extension</span></span>  |  <span data-ttu-id="99afa-220">解決方法</span><span class="sxs-lookup"><span data-stu-id="99afa-220">Resolution</span></span>  |
|----------|----------|----------|----------|
| <span data-ttu-id="99afa-221">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="99afa-221">HoloLens 2</span></span> | [<span data-ttu-id="99afa-222">JPEG</span><span class="sxs-lookup"><span data-stu-id="99afa-222">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="99afa-223">.jpg</span><span class="sxs-lookup"><span data-stu-id="99afa-223">.jpg</span></span> | <span data-ttu-id="99afa-224">3904x2196px</span><span class="sxs-lookup"><span data-stu-id="99afa-224">3904x2196px</span></span> |
| <span data-ttu-id="99afa-225">HoloLens (第 1 世代)</span><span class="sxs-lookup"><span data-stu-id="99afa-225">HoloLens (1st gen)</span></span> | [<span data-ttu-id="99afa-226">JPEG</span><span class="sxs-lookup"><span data-stu-id="99afa-226">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="99afa-227">.jpg</span><span class="sxs-lookup"><span data-stu-id="99afa-227">.jpg</span></span> | <span data-ttu-id="99afa-228">1408x792px</span><span class="sxs-lookup"><span data-stu-id="99afa-228">1408x792px</span></span> |

### <span data-ttu-id="99afa-229">録画されたビデオの形式と解像度</span><span class="sxs-lookup"><span data-stu-id="99afa-229">Recorded video format and resolution</span></span>

| <span data-ttu-id="99afa-230">デバイス</span><span class="sxs-lookup"><span data-stu-id="99afa-230">Device</span></span> | <span data-ttu-id="99afa-231">形式</span><span class="sxs-lookup"><span data-stu-id="99afa-231">Format</span></span> | <span data-ttu-id="99afa-232">拡張機能</span><span class="sxs-lookup"><span data-stu-id="99afa-232">Extension</span></span> | <span data-ttu-id="99afa-233">解決方法</span><span class="sxs-lookup"><span data-stu-id="99afa-233">Resolution</span></span> | <span data-ttu-id="99afa-234">速度</span><span class="sxs-lookup"><span data-stu-id="99afa-234">Speed</span></span> | <span data-ttu-id="99afa-235">オーディオ</span><span class="sxs-lookup"><span data-stu-id="99afa-235">Audio</span></span> |
|----------|----------|----------|----------|----------|----------|
| <span data-ttu-id="99afa-236">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="99afa-236">HoloLens 2</span></span> | [<span data-ttu-id="99afa-237">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="99afa-237">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="99afa-238">.mp4</span><span class="sxs-lookup"><span data-stu-id="99afa-238">.mp4</span></span> | <span data-ttu-id="99afa-239">1920x1080px</span><span class="sxs-lookup"><span data-stu-id="99afa-239">1920x1080px</span></span> | <span data-ttu-id="99afa-240">30fps</span><span class="sxs-lookup"><span data-stu-id="99afa-240">30fps</span></span> | <span data-ttu-id="99afa-241">48kHz ステレオ</span><span class="sxs-lookup"><span data-stu-id="99afa-241">48kHz Stereo</span></span> |
| <span data-ttu-id="99afa-242">HoloLens (第 1 世代)</span><span class="sxs-lookup"><span data-stu-id="99afa-242">HoloLens (1st gen)</span></span> |  [<span data-ttu-id="99afa-243">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="99afa-243">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="99afa-244">.mp4</span><span class="sxs-lookup"><span data-stu-id="99afa-244">.mp4</span></span> | <span data-ttu-id="99afa-245">1216x684px</span><span class="sxs-lookup"><span data-stu-id="99afa-245">1216x684px</span></span> | <span data-ttu-id="99afa-246">24fps</span><span class="sxs-lookup"><span data-stu-id="99afa-246">24fps</span></span> | <span data-ttu-id="99afa-247">48kHz ステレオ</span><span class="sxs-lookup"><span data-stu-id="99afa-247">48kHz Stereo</span></span> |
