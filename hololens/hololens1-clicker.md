---
title: HoloLens クリッカーの使用
description: この記事では、クリッカーのペアリング、充電、回復など、HoloLens クリッカーの使用方法について説明します。
ms.assetid: 7d4a30fd-cf1d-4c9a-8eb1-1968ccecbe59
ms.date: 09/16/2019
manager: jarrettr
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4b17fc134846a66046a819c56755d87206c5643e
ms.sourcegitcommit: 01c0b0a789e156a9d29aaf6f61e36dfd09b8c01a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439053"
---
# <a name="use-the-hololens-1st-gen-clicker"></a><span data-ttu-id="e845a-104">HoloLens (第1世代) クリッカーの使用</span><span class="sxs-lookup"><span data-stu-id="e845a-104">Use the HoloLens (1st gen) clicker</span></span>

<span data-ttu-id="e845a-105">クリッカーは HoloLens (第1世代) 用に特別に設計されており、ホログラムを操作する別の方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="e845a-105">The clicker was designed specifically for HoloLens (1st gen) and gives you another way to interact with holograms.</span></span> <span data-ttu-id="e845a-106">HoloLens (第1世代) が別のボックスに入っています。</span><span class="sxs-lookup"><span data-stu-id="e845a-106">It comes with HoloLens (1st gen), in a separate box.</span></span>

<span data-ttu-id="e845a-107">手のジェスチャの代わりに使用して、アプリを選択、スクロール、移動、サイズ変更します。</span><span class="sxs-lookup"><span data-stu-id="e845a-107">Use it in place of hand gestures to select, scroll, move, and resize apps.</span></span>

## <a name="clicker-hardware-and-pairing"></a><span data-ttu-id="e845a-108">クリッカー ハードウェアとペアリング</span><span class="sxs-lookup"><span data-stu-id="e845a-108">Clicker hardware and pairing</span></span>

<span data-ttu-id="e845a-109">HoloLens (第1世代) クリッカーには、持ちやすくするための指のループとインジケーター ライトがあります。</span><span class="sxs-lookup"><span data-stu-id="e845a-109">The HoloLens (1st gen) clicker has a finger loop to make it easier to hold, and an indicator light.</span></span>

![HoloLens クリッカー](images/use-hololens-clicker-1.png)

### <a name="clicker-indicator-lights"></a><span data-ttu-id="e845a-111">クリッカー インジケーター ライト</span><span class="sxs-lookup"><span data-stu-id="e845a-111">Clicker indicator lights</span></span>

<span data-ttu-id="e845a-112">クリッカーのライトの意味は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e845a-112">Here's what the lights on the clicker mean.</span></span>

- <span data-ttu-id="e845a-113">**白の点滅**。</span><span class="sxs-lookup"><span data-stu-id="e845a-113">**Blinking white**.</span></span> <span data-ttu-id="e845a-114">クリッカーはペアリング モードです。</span><span class="sxs-lookup"><span data-stu-id="e845a-114">The clicker is in pairing mode.</span></span>
- <span data-ttu-id="e845a-115">**白の速い点滅**。</span><span class="sxs-lookup"><span data-stu-id="e845a-115">**Fast-blinking white**.</span></span> <span data-ttu-id="e845a-116">ペアリングが正常に終了しました。</span><span class="sxs-lookup"><span data-stu-id="e845a-116">Pairing was successful.</span></span>
- <span data-ttu-id="e845a-117">**白の点灯**。</span><span class="sxs-lookup"><span data-stu-id="e845a-117">**Solid white**.</span></span> <span data-ttu-id="e845a-118">クリッカーは充電中です。</span><span class="sxs-lookup"><span data-stu-id="e845a-118">The clicker is charging.</span></span>
- <span data-ttu-id="e845a-119">**オレンジで点滅**。</span><span class="sxs-lookup"><span data-stu-id="e845a-119">**Blinking amber**.</span></span> <span data-ttu-id="e845a-120">バッテリーが少なくなっています。</span><span class="sxs-lookup"><span data-stu-id="e845a-120">The battery is low.</span></span>
- <span data-ttu-id="e845a-121">**オレンジの点灯**。</span><span class="sxs-lookup"><span data-stu-id="e845a-121">**Solid amber**.</span></span> <span data-ttu-id="e845a-122">クリッカーにエラーが発生し、再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e845a-122">The clicker ran into an error and you'll need to restart it.</span></span> <span data-ttu-id="e845a-123">ペアリング ボタンを押しながら、クリックして 15 秒間押し続けます。</span><span class="sxs-lookup"><span data-stu-id="e845a-123">While pressing the pairing button, click and hold for 15 seconds.</span></span>

### <a name="pair-the-clicker-with-your-hololens-1st-gen"></a><span data-ttu-id="e845a-124">クリッカーを HoloLens (第1世代) とペアリングします</span><span class="sxs-lookup"><span data-stu-id="e845a-124">Pair the clicker with your HoloLens (1st gen)</span></span>

1. <span data-ttu-id="e845a-125">ブルーム ジェスチャを使用して、[**スタート**] に移動し、[**設定**] > [**デバイス**] の順に選択して、Bluetooth がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e845a-125">Use the bloom gesture to go to **Start**, then select **Settings** > **Devices** and verify that Bluetooth is on.</span></span>
1. <span data-ttu-id="e845a-126">クリッカーで、状態ライトが白く点滅するまでペアリング ボタンを押し続けます。</span><span class="sxs-lookup"><span data-stu-id="e845a-126">On the clicker, press and hold the pairing button until the status light blinks white.</span></span>
1. <span data-ttu-id="e845a-127">ペアリング画面で、**[クリッカー]** > **[ペアリング]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e845a-127">On the pairing screen, select **Clicker** > **Pair**.</span></span>

### <a name="charge-the-clicker"></a><span data-ttu-id="e845a-128">クリッカーを充電する</span><span class="sxs-lookup"><span data-stu-id="e845a-128">Charge the clicker</span></span>

<span data-ttu-id="e845a-129">クリッカー バッテリーが少なくなると、バッテリーのインジケーターがオレンジ色に点滅します。</span><span class="sxs-lookup"><span data-stu-id="e845a-129">When the clicker battery is low, the battery indicator will blink amber.</span></span> <span data-ttu-id="e845a-130">Micro USB ケーブルを USB 電源に接続して、デバイスを充電します。</span><span class="sxs-lookup"><span data-stu-id="e845a-130">Plug the Micro USB cable into a USB power supply to charge the device.</span></span>

## <a name="use-the-clicker-with-hololens-1st-gen"></a><span data-ttu-id="e845a-131">HoloLens (第1世代) でクリッカーを使用する</span><span class="sxs-lookup"><span data-stu-id="e845a-131">Use the clicker with HoloLens (1st gen)</span></span>

### <a name="hold-the-clicker"></a><span data-ttu-id="e845a-132">クリッカーを押し続ける</span><span class="sxs-lookup"><span data-stu-id="e845a-132">Hold the clicker</span></span>

<span data-ttu-id="e845a-133">クリッカーを装着するには、Micro USB ポートが手首を向くように、ループを薬指または中指にスライドさせます。</span><span class="sxs-lookup"><span data-stu-id="e845a-133">To put on the clicker, slide the loop over your ring or middle finger so that the Micro USB port faces toward your wrist.</span></span> <span data-ttu-id="e845a-134">くぼみに親指を置きます。</span><span class="sxs-lookup"><span data-stu-id="e845a-134">Rest your thumb in the indentation.</span></span>

![クリッカーの持ち方](images/use-hololens-clicker-2.png)

### <a name="clicker-gestures"></a><span data-ttu-id="e845a-136">クリッカーのジェスチャ</span><span class="sxs-lookup"><span data-stu-id="e845a-136">Clicker gestures</span></span>

<span data-ttu-id="e845a-137">クリッカーのジェスチャは手首の小さな回転であり、HoloLens ハンド ジェスチャで使用される大きな動きではありません。</span><span class="sxs-lookup"><span data-stu-id="e845a-137">Clicker gestures are small wrist rotations, not the larger movements used for HoloLens hand gestures.</span></span> <span data-ttu-id="e845a-138">HoloLens は、クリッカーが[ジェスチャ フレーム](hololens1-basic-usage.md)の外側にある場合でもジェスチャとクリックを認識します。そのため、クリッカーを最も快適な位置に保持できます。</span><span class="sxs-lookup"><span data-stu-id="e845a-138">And HoloLens recognizes your gestures and clicks even if the clicker is outside the [gesture frame](hololens1-basic-usage.md), so you can hold the clicker in the position that's most comfortable for you.</span></span>

- <span data-ttu-id="e845a-139">**選択します**。</span><span class="sxs-lookup"><span data-stu-id="e845a-139">**Select**.</span></span> <span data-ttu-id="e845a-140">ホログラム、ボタン、またはその他の要素を選択するには、それを見つめて、クリックします。</span><span class="sxs-lookup"><span data-stu-id="e845a-140">To select a hologram, button, or other element, gaze at it, then click.</span></span>

- <span data-ttu-id="e845a-141">**クリックしたままにします**。</span><span class="sxs-lookup"><span data-stu-id="e845a-141">**Click and hold**.</span></span> <span data-ttu-id="e845a-142">ボタンを親指で長押しすると、ホログラムの移動やサイズ変更など、長押しした場合と同じ操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="e845a-142">Click and hold your thumb down on the button to do some of the same things you would with tap and hold, such as move or resize a hologram.</span></span>

- <span data-ttu-id="e845a-143">**スクロール**。</span><span class="sxs-lookup"><span data-stu-id="e845a-143">**Scroll**.</span></span> <span data-ttu-id="e845a-144">アプリ バーで、[**スクロール モード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e845a-144">On the app bar, select **Scroll Tool**.</span></span> <span data-ttu-id="e845a-145">クリックしたままにして、クリッカーを上下左右に回転させます。</span><span class="sxs-lookup"><span data-stu-id="e845a-145">Click and hold, then rotate the clicker up, down, left, or right.</span></span> <span data-ttu-id="e845a-146">高速でスクロールするには、スクロール ツールの中心から手を速く動かします。</span><span class="sxs-lookup"><span data-stu-id="e845a-146">To scroll faster, move your hand farther from the center of the scroll tool.</span></span>

- <span data-ttu-id="e845a-147">**ズーム**。</span><span class="sxs-lookup"><span data-stu-id="e845a-147">**Zoom**.</span></span> <span data-ttu-id="e845a-148">アプリ バーで、[**ズーム モード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e845a-148">On the app bar, select **Zoom Tool**.</span></span> <span data-ttu-id="e845a-149">クリックしたまま、クリッカーを上に回転するとズーム イン、下に回転するとズーム アウトします。</span><span class="sxs-lookup"><span data-stu-id="e845a-149">Click and hold, then rotate the clicker up to zoom in, or down to zoom out.</span></span>

> [!TIP]
> <span data-ttu-id="e845a-150">Microsoft Edge を使用しているときにズーム インまたはズーム アウトするには、ページを注視してダブル クリックします。</span><span class="sxs-lookup"><span data-stu-id="e845a-150">To zoom in or out when using Microsoft Edge, gaze at a page and double-click.</span></span>

## <a name="restart-or-recover-the-clicker"></a><span data-ttu-id="e845a-151">クリッカーを再起動または回復する</span><span class="sxs-lookup"><span data-stu-id="e845a-151">Restart or recover the clicker</span></span>

<span data-ttu-id="e845a-152">HoloLens クリッカーが応答しない、またはうまく機能しない場合に試してみることがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="e845a-152">Here are some things to try if the HoloLens clicker is unresponsive or isn’t working well.</span></span>

### <a name="restart-the-clicker"></a><span data-ttu-id="e845a-153">クリッカーを再起動する</span><span class="sxs-lookup"><span data-stu-id="e845a-153">Restart the clicker</span></span>

<span data-ttu-id="e845a-154">ペンの先を使って、ペアリング ボタンを押し続けます。</span><span class="sxs-lookup"><span data-stu-id="e845a-154">Use the tip of a pen to press and hold the pairing button.</span></span> <span data-ttu-id="e845a-155">同時に、クリッカーをクリックして 15 秒間押し続けます。</span><span class="sxs-lookup"><span data-stu-id="e845a-155">At the same time, click and hold the clicker for 15 seconds.</span></span> <span data-ttu-id="e845a-156">クリッカーがすでに HoloLens とペアリングされている場合、クリッカーは再起動後もペアリングされたままになります。</span><span class="sxs-lookup"><span data-stu-id="e845a-156">If the clicker was already paired with your HoloLens, it will stay paired after it restarts.</span></span>

<span data-ttu-id="e845a-157">クリッカーがオンにならないか、再起動しない場合は、HoloLens 充電器を使用してクリッカーを充電してみてください。</span><span class="sxs-lookup"><span data-stu-id="e845a-157">If the clicker won't turn on or restart, try charging it by using the HoloLens charger.</span></span> <span data-ttu-id="e845a-158">バッテリー残量が非常に少ない場合、白いインジケーター ライトがオンになるまで数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="e845a-158">If the battery is very low, it might take a few minutes for the white indicator light to turn on.</span></span>

### <a name="re-pair-the-clicker"></a><span data-ttu-id="e845a-159">クリッカーを再ペアリングする</span><span class="sxs-lookup"><span data-stu-id="e845a-159">Re-pair the clicker</span></span>

<span data-ttu-id="e845a-160">[**設定**] > [**デバイス**] を選択して、クリッカーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e845a-160">Select **Settings** > **Devices** and select the clicker.</span></span> <span data-ttu-id="e845a-161">[**削除**] を選択し、数秒待ってから、クリッカーを再度ペアリングします。</span><span class="sxs-lookup"><span data-stu-id="e845a-161">Select **Remove**, wait a few seconds, then pair the clicker again.</span></span>

### <a name="recover-the-clicker"></a><span data-ttu-id="e845a-162">クリッカーを回復する</span><span class="sxs-lookup"><span data-stu-id="e845a-162">Recover the clicker</span></span>

<span data-ttu-id="e845a-163">クリッカーを再起動してペアリングしても問題が解決しない場合は、Windows Device Recovery Tool を使用して問題を回復できます。</span><span class="sxs-lookup"><span data-stu-id="e845a-163">If restarting and re-pairing the clicker don’t fix the problem, the Windows Device Recovery Tool can help you recover it.</span></span> <span data-ttu-id="e845a-164">回復プロセスには時間がかかる場合があり、最新バージョンのクリッカー ソフトウェアがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e845a-164">The recovery process may take some time, and it will install the latest version of the clicker software.</span></span> <span data-ttu-id="e845a-165">このツールを使用するには、Windows 10 以降を実行し、4 GB 以上の空き容量があるコンピューターが必要です。</span><span class="sxs-lookup"><span data-stu-id="e845a-165">To use the tool, you’ll need a computer running Windows 10 or later that has at least 4 GB of free storage space.</span></span>

<span data-ttu-id="e845a-166">クリッカーを回復するには:</span><span class="sxs-lookup"><span data-stu-id="e845a-166">To recover the clicker:</span></span>

1. <span data-ttu-id="e845a-167">コンピューターに [Windows Device Recovery Tool](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="e845a-167">Download and install the [Windows Device Recovery Tool](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) on your computer.</span></span>
1. <span data-ttu-id="e845a-168">HoloLens に付属の Micro USB ケーブルを使用して、クリッカーをコンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="e845a-168">Connect the clicker to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="e845a-169">Windows Device Recovery Tool を実行し、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="e845a-169">Run the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="e845a-170">クリッカーが自動的に検出されない場合は、[**デバイスが検出されませんでした**] を選択し、指示に従ってデバイスを回復モードにします。</span><span class="sxs-lookup"><span data-stu-id="e845a-170">If the clicker isn’t automatically detected, select **My device was not detected** and follow the instructions to put your device into recovery mode.</span></span>
