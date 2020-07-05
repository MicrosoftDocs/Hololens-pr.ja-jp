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
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 13b86c049ba8bb6ed67be202609d27c8d47ffc53
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829473"
---
# <span data-ttu-id="d0de3-104">HoloLens (第1世代) クリッカーの使用</span><span class="sxs-lookup"><span data-stu-id="d0de3-104">Use the HoloLens (1st gen) clicker</span></span>

<span data-ttu-id="d0de3-105">クリッカーは HoloLens (第1世代) 用に特別に設計されており、ホログラムを操作する別の方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="d0de3-105">The clicker was designed specifically for HoloLens (1st gen) and gives you another way to interact with holograms.</span></span> <span data-ttu-id="d0de3-106">HoloLens (第1世代) が別のボックスに入っています。</span><span class="sxs-lookup"><span data-stu-id="d0de3-106">It comes with HoloLens (1st gen), in a separate box.</span></span>

<span data-ttu-id="d0de3-107">手のジェスチャの代わりに使用して、アプリを選択、スクロール、移動、サイズ変更します。</span><span class="sxs-lookup"><span data-stu-id="d0de3-107">Use it in place of hand gestures to select, scroll, move, and resize apps.</span></span>

## <span data-ttu-id="d0de3-108">クリッカー ハードウェアとペアリング</span><span class="sxs-lookup"><span data-stu-id="d0de3-108">Clicker hardware and pairing</span></span>

<span data-ttu-id="d0de3-109">HoloLens (第1世代) クリッカーには、持ちやすくするための指のループとインジケーター ライトがあります。</span><span class="sxs-lookup"><span data-stu-id="d0de3-109">The HoloLens (1st gen) clicker has a finger loop to make it easier to hold, and an indicator light.</span></span>

![HoloLens クリッカー](images/use-hololens-clicker-1.png)

### <span data-ttu-id="d0de3-111">クリッカー インジケーター ライト</span><span class="sxs-lookup"><span data-stu-id="d0de3-111">Clicker indicator lights</span></span>

<span data-ttu-id="d0de3-112">クリッカーのライトの意味は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d0de3-112">Here's what the lights on the clicker mean.</span></span>

- <span data-ttu-id="d0de3-113">**白の点滅**。</span><span class="sxs-lookup"><span data-stu-id="d0de3-113">**Blinking white**.</span></span> <span data-ttu-id="d0de3-114">クリッカーはペアリング モードです。</span><span class="sxs-lookup"><span data-stu-id="d0de3-114">The clicker is in pairing mode.</span></span>
- <span data-ttu-id="d0de3-115">**白の速い点滅**。</span><span class="sxs-lookup"><span data-stu-id="d0de3-115">**Fast-blinking white**.</span></span> <span data-ttu-id="d0de3-116">ペアリングが正常に終了しました。</span><span class="sxs-lookup"><span data-stu-id="d0de3-116">Pairing was successful.</span></span>
- <span data-ttu-id="d0de3-117">**白の点灯**。</span><span class="sxs-lookup"><span data-stu-id="d0de3-117">**Solid white**.</span></span> <span data-ttu-id="d0de3-118">クリッカーは充電中です。</span><span class="sxs-lookup"><span data-stu-id="d0de3-118">The clicker is charging.</span></span>
- <span data-ttu-id="d0de3-119">**オレンジで点滅**。</span><span class="sxs-lookup"><span data-stu-id="d0de3-119">**Blinking amber**.</span></span> <span data-ttu-id="d0de3-120">バッテリーが少なくなっています。</span><span class="sxs-lookup"><span data-stu-id="d0de3-120">The battery is low.</span></span>
- <span data-ttu-id="d0de3-121">**オレンジの点灯**。</span><span class="sxs-lookup"><span data-stu-id="d0de3-121">**Solid amber**.</span></span> <span data-ttu-id="d0de3-122">クリッカーにエラーが発生し、再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0de3-122">The clicker ran into an error and you'll need to restart it.</span></span> <span data-ttu-id="d0de3-123">ペアリング ボタンを押しながら、クリックして 15 秒間押し続けます。</span><span class="sxs-lookup"><span data-stu-id="d0de3-123">While pressing the pairing button, click and hold for 15 seconds.</span></span>

### <span data-ttu-id="d0de3-124">クリッカーを HoloLens (第1世代) とペアリングします</span><span class="sxs-lookup"><span data-stu-id="d0de3-124">Pair the clicker with your HoloLens (1st gen)</span></span>

1. <span data-ttu-id="d0de3-125">ブルーム ジェスチャを使用して、[**スタート**] に移動し、[**設定**] > [**デバイス**] の順に選択して、Bluetooth がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0de3-125">Use the bloom gesture to go to **Start**, then select **Settings** > **Devices** and verify that Bluetooth is on.</span></span>
1. <span data-ttu-id="d0de3-126">クリッカーで、状態ライトが白く点滅するまでペアリング ボタンを押し続けます。</span><span class="sxs-lookup"><span data-stu-id="d0de3-126">On the clicker, press and hold the pairing button until the status light blinks white.</span></span>
1. <span data-ttu-id="d0de3-127">ペアリング画面で、**[クリッカー]** > **[ペアリング]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0de3-127">On the pairing screen, select **Clicker** > **Pair**.</span></span>

### <span data-ttu-id="d0de3-128">クリッカーを充電する</span><span class="sxs-lookup"><span data-stu-id="d0de3-128">Charge the clicker</span></span>

<span data-ttu-id="d0de3-129">クリッカー バッテリーが少なくなると、バッテリーのインジケーターがオレンジ色に点滅します。</span><span class="sxs-lookup"><span data-stu-id="d0de3-129">When the clicker battery is low, the battery indicator will blink amber.</span></span> <span data-ttu-id="d0de3-130">Micro USB ケーブルを USB 電源に接続して、デバイスを充電します。</span><span class="sxs-lookup"><span data-stu-id="d0de3-130">Plug the Micro USB cable into a USB power supply to charge the device.</span></span>

## <span data-ttu-id="d0de3-131">HoloLens (第1世代) でクリッカーを使用する</span><span class="sxs-lookup"><span data-stu-id="d0de3-131">Use the clicker with HoloLens (1st gen)</span></span>

### <span data-ttu-id="d0de3-132">クリッカーを押し続ける</span><span class="sxs-lookup"><span data-stu-id="d0de3-132">Hold the clicker</span></span>

<span data-ttu-id="d0de3-133">クリッカーを装着するには、Micro USB ポートが手首を向くように、ループを薬指または中指にスライドさせます。</span><span class="sxs-lookup"><span data-stu-id="d0de3-133">To put on the clicker, slide the loop over your ring or middle finger so that the Micro USB port faces toward your wrist.</span></span> <span data-ttu-id="d0de3-134">くぼみに親指を置きます。</span><span class="sxs-lookup"><span data-stu-id="d0de3-134">Rest your thumb in the indentation.</span></span>

![クリッカーの持ち方](images/use-hololens-clicker-2.png)

### <span data-ttu-id="d0de3-136">クリッカーのジェスチャ</span><span class="sxs-lookup"><span data-stu-id="d0de3-136">Clicker gestures</span></span>

<span data-ttu-id="d0de3-137">クリッカーのジェスチャは手首の小さな回転であり、HoloLens ハンド ジェスチャで使用される大きな動きではありません。</span><span class="sxs-lookup"><span data-stu-id="d0de3-137">Clicker gestures are small wrist rotations, not the larger movements used for HoloLens hand gestures.</span></span> <span data-ttu-id="d0de3-138">HoloLens は、クリッカーが[ジェスチャ フレーム](hololens1-basic-usage.md)の外側にある場合でもジェスチャとクリックを認識します。そのため、クリッカーを最も快適な位置に保持できます。</span><span class="sxs-lookup"><span data-stu-id="d0de3-138">And HoloLens recognizes your gestures and clicks even if the clicker is outside the [gesture frame](hololens1-basic-usage.md), so you can hold the clicker in the position that's most comfortable for you.</span></span>

- <span data-ttu-id="d0de3-139">**選択します**。</span><span class="sxs-lookup"><span data-stu-id="d0de3-139">**Select**.</span></span> <span data-ttu-id="d0de3-140">ホログラム、ボタン、またはその他の要素を選択するには、それを見つめて、クリックします。</span><span class="sxs-lookup"><span data-stu-id="d0de3-140">To select a hologram, button, or other element, gaze at it, then click.</span></span>

- <span data-ttu-id="d0de3-141">**クリックしたままにします**。</span><span class="sxs-lookup"><span data-stu-id="d0de3-141">**Click and hold**.</span></span> <span data-ttu-id="d0de3-142">ボタンを親指で長押しすると、ホログラムの移動やサイズ変更など、長押しした場合と同じ操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="d0de3-142">Click and hold your thumb down on the button to do some of the same things you would with tap and hold, such as move or resize a hologram.</span></span>

- <span data-ttu-id="d0de3-143">**スクロール**。</span><span class="sxs-lookup"><span data-stu-id="d0de3-143">**Scroll**.</span></span> <span data-ttu-id="d0de3-144">アプリ バーで、[**スクロール モード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0de3-144">On the app bar, select **Scroll Tool**.</span></span> <span data-ttu-id="d0de3-145">クリックしたままにして、クリッカーを上下左右に回転させます。</span><span class="sxs-lookup"><span data-stu-id="d0de3-145">Click and hold, then rotate the clicker up, down, left, or right.</span></span> <span data-ttu-id="d0de3-146">高速でスクロールするには、スクロール ツールの中心から手を速く動かします。</span><span class="sxs-lookup"><span data-stu-id="d0de3-146">To scroll faster, move your hand farther from the center of the scroll tool.</span></span>

- <span data-ttu-id="d0de3-147">**ズーム**。</span><span class="sxs-lookup"><span data-stu-id="d0de3-147">**Zoom**.</span></span> <span data-ttu-id="d0de3-148">アプリ バーで、[**ズーム モード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0de3-148">On the app bar, select **Zoom Tool**.</span></span> <span data-ttu-id="d0de3-149">クリックしたまま、クリッカーを上に回転するとズーム イン、下に回転するとズーム アウトします。</span><span class="sxs-lookup"><span data-stu-id="d0de3-149">Click and hold, then rotate the clicker up to zoom in, or down to zoom out.</span></span>

> [!TIP]
> <span data-ttu-id="d0de3-150">Microsoft Edge を使用しているときにズーム インまたはズーム アウトするには、ページを注視してダブル クリックします。</span><span class="sxs-lookup"><span data-stu-id="d0de3-150">To zoom in or out when using Microsoft Edge, gaze at a page and double-click.</span></span>

## <span data-ttu-id="d0de3-151">クリッカーを再起動または回復する</span><span class="sxs-lookup"><span data-stu-id="d0de3-151">Restart or recover the clicker</span></span>

<span data-ttu-id="d0de3-152">HoloLens クリッカーが応答しない、またはうまく機能しない場合に試してみることがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="d0de3-152">Here are some things to try if the HoloLens clicker is unresponsive or isn’t working well.</span></span>

### <span data-ttu-id="d0de3-153">クリッカーを再起動する</span><span class="sxs-lookup"><span data-stu-id="d0de3-153">Restart the clicker</span></span>

<span data-ttu-id="d0de3-154">ペンの先を使って、ペアリング ボタンを押し続けます。</span><span class="sxs-lookup"><span data-stu-id="d0de3-154">Use the tip of a pen to press and hold the pairing button.</span></span> <span data-ttu-id="d0de3-155">同時に、クリッカーをクリックして 15 秒間押し続けます。</span><span class="sxs-lookup"><span data-stu-id="d0de3-155">At the same time, click and hold the clicker for 15 seconds.</span></span> <span data-ttu-id="d0de3-156">クリッカーがすでに HoloLens とペアリングされている場合、クリッカーは再起動後もペアリングされたままになります。</span><span class="sxs-lookup"><span data-stu-id="d0de3-156">If the clicker was already paired with your HoloLens, it will stay paired after it restarts.</span></span>

<span data-ttu-id="d0de3-157">クリッカーがオンにならないか、再起動しない場合は、HoloLens 充電器を使用してクリッカーを充電してみてください。</span><span class="sxs-lookup"><span data-stu-id="d0de3-157">If the clicker won't turn on or restart, try charging it by using the HoloLens charger.</span></span> <span data-ttu-id="d0de3-158">バッテリー残量が非常に少ない場合、白いインジケーター ライトがオンになるまで数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="d0de3-158">If the battery is very low, it might take a few minutes for the white indicator light to turn on.</span></span>

### <span data-ttu-id="d0de3-159">クリッカーを再ペアリングする</span><span class="sxs-lookup"><span data-stu-id="d0de3-159">Re-pair the clicker</span></span>

<span data-ttu-id="d0de3-160">[**設定**] > [**デバイス**] を選択して、クリッカーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d0de3-160">Select **Settings** > **Devices** and select the clicker.</span></span> <span data-ttu-id="d0de3-161">[**削除**] を選択し、数秒待ってから、クリッカーを再度ペアリングします。</span><span class="sxs-lookup"><span data-stu-id="d0de3-161">Select **Remove**, wait a few seconds, then pair the clicker again.</span></span>

### <span data-ttu-id="d0de3-162">クリッカーを回復する</span><span class="sxs-lookup"><span data-stu-id="d0de3-162">Recover the clicker</span></span>

<span data-ttu-id="d0de3-163">クリッカーを再起動してペアリングしても問題が解決しない場合は、Windows Device Recovery Tool を使用して問題を回復できます。</span><span class="sxs-lookup"><span data-stu-id="d0de3-163">If restarting and re-pairing the clicker don’t fix the problem, the Windows Device Recovery Tool can help you recover it.</span></span> <span data-ttu-id="d0de3-164">回復プロセスには時間がかかる場合があり、最新バージョンのクリッカー ソフトウェアがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d0de3-164">The recovery process may take some time, and it will install the latest version of the clicker software.</span></span> <span data-ttu-id="d0de3-165">このツールを使用するには、Windows 10 以降を実行し、4 GB 以上の空き容量があるコンピューターが必要です。</span><span class="sxs-lookup"><span data-stu-id="d0de3-165">To use the tool, you’ll need a computer running Windows 10 or later that has at least 4 GB of free storage space.</span></span>

<span data-ttu-id="d0de3-166">クリッカーを回復するには:</span><span class="sxs-lookup"><span data-stu-id="d0de3-166">To recover the clicker:</span></span>

1. <span data-ttu-id="d0de3-167">コンピューターに [Windows Device Recovery Tool](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="d0de3-167">Download and install the [Windows Device Recovery Tool](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) on your computer.</span></span>
1. <span data-ttu-id="d0de3-168">HoloLens に付属の Micro USB ケーブルを使用して、クリッカーをコンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="d0de3-168">Connect the clicker to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="d0de3-169">Windows Device Recovery Tool を実行し、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="d0de3-169">Run the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="d0de3-170">クリッカーが自動的に検出されない場合は、[**デバイスが検出されませんでした**] を選択し、指示に従ってデバイスを回復モードにします。</span><span class="sxs-lookup"><span data-stu-id="d0de3-170">If the clicker isn’t automatically detected, select **My device was not detected** and follow the instructions to put your device into recovery mode.</span></span>
