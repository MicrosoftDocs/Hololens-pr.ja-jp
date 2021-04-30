---
title: HoloLens clicker を使用する
description: この記事では、clicker ペアリング、充電、回復など、HoloLens clicker の使用方法について説明します。
ms.assetid: 7d4a30fd-cf1d-4c9a-8eb1-1968ccecbe59
ms.date: 09/16/2019
manager: jarrettr
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4b17fc134846a66046a819c56755d87206c5643e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310001"
---
# <a name="use-the-hololens-1st-gen-clicker"></a><span data-ttu-id="974a9-104">HoloLens (第1世代) clicker を使用する</span><span class="sxs-lookup"><span data-stu-id="974a9-104">Use the HoloLens (1st gen) clicker</span></span>

<span data-ttu-id="974a9-105">Clicker は HoloLens (第1世代) 専用に設計されており、ホログラムを操作する別の方法を提供しています。</span><span class="sxs-lookup"><span data-stu-id="974a9-105">The clicker was designed specifically for HoloLens (1st gen) and gives you another way to interact with holograms.</span></span> <span data-ttu-id="974a9-106">HoloLens (第1世代) が別のボックスに付属しています。</span><span class="sxs-lookup"><span data-stu-id="974a9-106">It comes with HoloLens (1st gen), in a separate box.</span></span>

<span data-ttu-id="974a9-107">ハンドジェスチャの代わりに使用して、アプリの選択、スクロール、移動、およびサイズ変更を行います。</span><span class="sxs-lookup"><span data-stu-id="974a9-107">Use it in place of hand gestures to select, scroll, move, and resize apps.</span></span>

## <a name="clicker-hardware-and-pairing"></a><span data-ttu-id="974a9-108">ハードウェアとペアリングの Clicker</span><span class="sxs-lookup"><span data-stu-id="974a9-108">Clicker hardware and pairing</span></span>

<span data-ttu-id="974a9-109">HoloLens (第1世代) clicker には、より簡単にするための指ループと、インジケーターライトがあります。</span><span class="sxs-lookup"><span data-stu-id="974a9-109">The HoloLens (1st gen) clicker has a finger loop to make it easier to hold, and an indicator light.</span></span>

![HoloLens Clicker](images/use-hololens-clicker-1.png)

### <a name="clicker-indicator-lights"></a><span data-ttu-id="974a9-111">Clicker インジケーターライト</span><span class="sxs-lookup"><span data-stu-id="974a9-111">Clicker indicator lights</span></span>

<span data-ttu-id="974a9-112">Clicker のライトは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="974a9-112">Here's what the lights on the clicker mean.</span></span>

- <span data-ttu-id="974a9-113">**白を点滅** します。</span><span class="sxs-lookup"><span data-stu-id="974a9-113">**Blinking white**.</span></span> <span data-ttu-id="974a9-114">Clicker はペアリングモードです。</span><span class="sxs-lookup"><span data-stu-id="974a9-114">The clicker is in pairing mode.</span></span>
- <span data-ttu-id="974a9-115">**高速点滅白**。</span><span class="sxs-lookup"><span data-stu-id="974a9-115">**Fast-blinking white**.</span></span> <span data-ttu-id="974a9-116">ペアリングに成功しました。</span><span class="sxs-lookup"><span data-stu-id="974a9-116">Pairing was successful.</span></span>
- <span data-ttu-id="974a9-117">**無地の白**。</span><span class="sxs-lookup"><span data-stu-id="974a9-117">**Solid white**.</span></span> <span data-ttu-id="974a9-118">Clicker は充電中です。</span><span class="sxs-lookup"><span data-stu-id="974a9-118">The clicker is charging.</span></span>
- <span data-ttu-id="974a9-119">**黄色で点滅** します。</span><span class="sxs-lookup"><span data-stu-id="974a9-119">**Blinking amber**.</span></span> <span data-ttu-id="974a9-120">バッテリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="974a9-120">The battery is low.</span></span>
- <span data-ttu-id="974a9-121">緑色で **点灯** します。</span><span class="sxs-lookup"><span data-stu-id="974a9-121">**Solid amber**.</span></span> <span data-ttu-id="974a9-122">Clicker でエラーが発生したため、再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="974a9-122">The clicker ran into an error and you'll need to restart it.</span></span> <span data-ttu-id="974a9-123">ペアリングボタンを押しながら、15秒間はクリックしたままにします。</span><span class="sxs-lookup"><span data-stu-id="974a9-123">While pressing the pairing button, click and hold for 15 seconds.</span></span>

### <a name="pair-the-clicker-with-your-hololens-1st-gen"></a><span data-ttu-id="974a9-124">Clicker と HoloLens をペアリングする (第1世代)</span><span class="sxs-lookup"><span data-stu-id="974a9-124">Pair the clicker with your HoloLens (1st gen)</span></span>

1. <span data-ttu-id="974a9-125">ブルームジェスチャを使用して [**スタート**] にアクセスし、[**設定**] [デバイス] の順に選択して、  >   Bluetooth がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="974a9-125">Use the bloom gesture to go to **Start**, then select **Settings** > **Devices** and verify that Bluetooth is on.</span></span>
1. <span data-ttu-id="974a9-126">Clicker で、ペアリングボタンを押したままにして、ステータスライトが白になるまで続けます。</span><span class="sxs-lookup"><span data-stu-id="974a9-126">On the clicker, press and hold the pairing button until the status light blinks white.</span></span>
1. <span data-ttu-id="974a9-127">[ペアリング] 画面で、[ **Clicker** Pair] を選択し  >  ます。</span><span class="sxs-lookup"><span data-stu-id="974a9-127">On the pairing screen, select **Clicker** > **Pair**.</span></span>

### <a name="charge-the-clicker"></a><span data-ttu-id="974a9-128">Clicker を請求する</span><span class="sxs-lookup"><span data-stu-id="974a9-128">Charge the clicker</span></span>

<span data-ttu-id="974a9-129">Clicker バッテリが低い場合、バッテリインジケーターは黄色で点滅します。</span><span class="sxs-lookup"><span data-stu-id="974a9-129">When the clicker battery is low, the battery indicator will blink amber.</span></span> <span data-ttu-id="974a9-130">マイクロ USB ケーブルを USB 電源装置に接続して、デバイスを充電します。</span><span class="sxs-lookup"><span data-stu-id="974a9-130">Plug the Micro USB cable into a USB power supply to charge the device.</span></span>

## <a name="use-the-clicker-with-hololens-1st-gen"></a><span data-ttu-id="974a9-131">HoloLens で clicker を使用する (第1世代)</span><span class="sxs-lookup"><span data-stu-id="974a9-131">Use the clicker with HoloLens (1st gen)</span></span>

### <a name="hold-the-clicker"></a><span data-ttu-id="974a9-132">Clicker を保持する</span><span class="sxs-lookup"><span data-stu-id="974a9-132">Hold the clicker</span></span>

<span data-ttu-id="974a9-133">Clicker を使用するには、このループをリングまたは真ん中の指でスライドさせることで、マイクロ USB ポートが手首に向くようにします。</span><span class="sxs-lookup"><span data-stu-id="974a9-133">To put on the clicker, slide the loop over your ring or middle finger so that the Micro USB port faces toward your wrist.</span></span> <span data-ttu-id="974a9-134">インデントにつまみを置きます。</span><span class="sxs-lookup"><span data-stu-id="974a9-134">Rest your thumb in the indentation.</span></span>

![Clicker を保持する方法](images/use-hololens-clicker-2.png)

### <a name="clicker-gestures"></a><span data-ttu-id="974a9-136">Clicker ジェスチャ</span><span class="sxs-lookup"><span data-stu-id="974a9-136">Clicker gestures</span></span>

<span data-ttu-id="974a9-137">Clicker ジェスチャは、HoloLens ハンドジェスチャに使用される大きな動きではなく、小さな手首回転です。</span><span class="sxs-lookup"><span data-stu-id="974a9-137">Clicker gestures are small wrist rotations, not the larger movements used for HoloLens hand gestures.</span></span> <span data-ttu-id="974a9-138">Clicker が [ジェスチャフレーム](hololens1-basic-usage.md)の外側にある場合でも、HoloLens はジェスチャとクリックを認識するので、clicker を最も使いやすい位置に保持できます。</span><span class="sxs-lookup"><span data-stu-id="974a9-138">And HoloLens recognizes your gestures and clicks even if the clicker is outside the [gesture frame](hololens1-basic-usage.md), so you can hold the clicker in the position that's most comfortable for you.</span></span>

- <span data-ttu-id="974a9-139">**を選択** します。</span><span class="sxs-lookup"><span data-stu-id="974a9-139">**Select**.</span></span> <span data-ttu-id="974a9-140">ホログラム、ボタン、またはその他の要素を選択するには、その要素を見つめて、をクリックします。</span><span class="sxs-lookup"><span data-stu-id="974a9-140">To select a hologram, button, or other element, gaze at it, then click.</span></span>

- <span data-ttu-id="974a9-141">**クリック** したままにします。</span><span class="sxs-lookup"><span data-stu-id="974a9-141">**Click and hold**.</span></span> <span data-ttu-id="974a9-142">ボタンのつまみをクリックしたままにすると、ホログラムの移動やサイズ変更など、タップして保持するものと同じことが実行されます。</span><span class="sxs-lookup"><span data-stu-id="974a9-142">Click and hold your thumb down on the button to do some of the same things you would with tap and hold, such as move or resize a hologram.</span></span>

- <span data-ttu-id="974a9-143">**スクロール**。</span><span class="sxs-lookup"><span data-stu-id="974a9-143">**Scroll**.</span></span> <span data-ttu-id="974a9-144">アプリバーで、[ **スクロールツール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="974a9-144">On the app bar, select **Scroll Tool**.</span></span> <span data-ttu-id="974a9-145">クリックしたままにして、clicker up、down、left、または right を回転させます。</span><span class="sxs-lookup"><span data-stu-id="974a9-145">Click and hold, then rotate the clicker up, down, left, or right.</span></span> <span data-ttu-id="974a9-146">スクロールを速くするには、スクロールツールの中央から離れた位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="974a9-146">To scroll faster, move your hand farther from the center of the scroll tool.</span></span>

- <span data-ttu-id="974a9-147">**ズーム**。</span><span class="sxs-lookup"><span data-stu-id="974a9-147">**Zoom**.</span></span> <span data-ttu-id="974a9-148">アプリバーで、[ **ズームツール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="974a9-148">On the app bar, select **Zoom Tool**.</span></span> <span data-ttu-id="974a9-149">[拡大] をクリックし、clicker を回転して、ズームアウトします。</span><span class="sxs-lookup"><span data-stu-id="974a9-149">Click and hold, then rotate the clicker up to zoom in, or down to zoom out.</span></span>

> [!TIP]
> <span data-ttu-id="974a9-150">Microsoft Edge を使用しているときに拡大または縮小するには、ページを見つめ、をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="974a9-150">To zoom in or out when using Microsoft Edge, gaze at a page and double-click.</span></span>

## <a name="restart-or-recover-the-clicker"></a><span data-ttu-id="974a9-151">Clicker を再起動または回復する</span><span class="sxs-lookup"><span data-stu-id="974a9-151">Restart or recover the clicker</span></span>

<span data-ttu-id="974a9-152">HoloLens clicker が応答していないか、正しく機能していない場合は、次の点を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="974a9-152">Here are some things to try if the HoloLens clicker is unresponsive or isn’t working well.</span></span>

### <a name="restart-the-clicker"></a><span data-ttu-id="974a9-153">Clicker を再起動します。</span><span class="sxs-lookup"><span data-stu-id="974a9-153">Restart the clicker</span></span>

<span data-ttu-id="974a9-154">ペンの先端を使用して、ペアリングボタンを押したままにします。</span><span class="sxs-lookup"><span data-stu-id="974a9-154">Use the tip of a pen to press and hold the pairing button.</span></span> <span data-ttu-id="974a9-155">同時に、clicker を15秒間クリックして保持します。</span><span class="sxs-lookup"><span data-stu-id="974a9-155">At the same time, click and hold the clicker for 15 seconds.</span></span> <span data-ttu-id="974a9-156">Clicker が既に HoloLens とペアリングされている場合は、再起動後もペアリングされたままになります。</span><span class="sxs-lookup"><span data-stu-id="974a9-156">If the clicker was already paired with your HoloLens, it will stay paired after it restarts.</span></span>

<span data-ttu-id="974a9-157">Clicker が有効にならない場合、または再起動しない場合は、HoloLens チャージャーを使用して課金します。</span><span class="sxs-lookup"><span data-stu-id="974a9-157">If the clicker won't turn on or restart, try charging it by using the HoloLens charger.</span></span> <span data-ttu-id="974a9-158">バッテリの残量が非常に少ない場合は、白いインジケーターライトが点灯するまで数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="974a9-158">If the battery is very low, it might take a few minutes for the white indicator light to turn on.</span></span>

### <a name="re-pair-the-clicker"></a><span data-ttu-id="974a9-159">Clicker を再ペアします。</span><span class="sxs-lookup"><span data-stu-id="974a9-159">Re-pair the clicker</span></span>

<span data-ttu-id="974a9-160">[**設定**] [デバイス] を選択し  >   、[clicker] を選択します。</span><span class="sxs-lookup"><span data-stu-id="974a9-160">Select **Settings** > **Devices** and select the clicker.</span></span> <span data-ttu-id="974a9-161">[ **削除**] を選択し、数秒待ってから、もう一度 clicker をペアリングします。</span><span class="sxs-lookup"><span data-stu-id="974a9-161">Select **Remove**, wait a few seconds, then pair the clicker again.</span></span>

### <a name="recover-the-clicker"></a><span data-ttu-id="974a9-162">Clicker を回復する</span><span class="sxs-lookup"><span data-stu-id="974a9-162">Recover the clicker</span></span>

<span data-ttu-id="974a9-163">Clicker を再起動して再ペアリングしても問題が解決しない場合は、Windows デバイス回復ツールを使用して回復することができます。</span><span class="sxs-lookup"><span data-stu-id="974a9-163">If restarting and re-pairing the clicker don’t fix the problem, the Windows Device Recovery Tool can help you recover it.</span></span> <span data-ttu-id="974a9-164">回復プロセスには時間がかかる場合があり、最新バージョンの clicker ソフトウェアがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="974a9-164">The recovery process may take some time, and it will install the latest version of the clicker software.</span></span> <span data-ttu-id="974a9-165">このツールを使用するには、少なくとも 4 GB の空き領域がある Windows 10 以降を実行しているコンピューターが必要です。</span><span class="sxs-lookup"><span data-stu-id="974a9-165">To use the tool, you’ll need a computer running Windows 10 or later that has at least 4 GB of free storage space.</span></span>

<span data-ttu-id="974a9-166">Clicker を回復するには:</span><span class="sxs-lookup"><span data-stu-id="974a9-166">To recover the clicker:</span></span>

1. <span data-ttu-id="974a9-167">[Windows デバイス回復ツール](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/)をコンピューターにダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="974a9-167">Download and install the [Windows Device Recovery Tool](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) on your computer.</span></span>
1. <span data-ttu-id="974a9-168">HoloLens に付属しているマイクロ USB ケーブルを使用して、clicker をコンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="974a9-168">Connect the clicker to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="974a9-169">Windows デバイス回復ツールを実行し、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="974a9-169">Run the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="974a9-170">Clicker が自動的に検出されない場合は、[ **デバイスが検出されませんでした** ] を選択し、指示に従ってデバイスを回復モードにします。</span><span class="sxs-lookup"><span data-stu-id="974a9-170">If the clicker isn’t automatically detected, select **My device was not detected** and follow the instructions to put your device into recovery mode.</span></span>
