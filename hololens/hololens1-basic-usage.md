---
title: HoloLens (第 1 世代) の操作方法
description: HoloLens (第 1 世代) インターフェイス、ハンド トラッキング機能、およびホログラフィック アプリケーションの使用について簡単に説明します。
ms.assetid: 064f7eb0-190e-4643-abeb-ed3b09312042
ms.date: 9/16/2019
ms.reviewer: jarrettr
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
ms.openlocfilehash: 5beb3e333634dfbe5080c9d36a7df3f38b0a5f37
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284068"
---
# <span data-ttu-id="eaf0d-104">HoloLens (第 1 世代) の操作方法</span><span class="sxs-lookup"><span data-stu-id="eaf0d-104">Getting around HoloLens (1st gen)</span></span>

<span data-ttu-id="eaf0d-105">ホログラムの世界に入る準備はできていますか? </span><span class="sxs-lookup"><span data-stu-id="eaf0d-105">Ready to step into the world of holograms?</span></span> <span data-ttu-id="eaf0d-106">ここでは、開始にあたって必要な情報をお伝えします。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-106">Here's some information to get started.</span></span>

<span data-ttu-id="eaf0d-107">このガイドでは、Mixed Reality の概要とホログラムを操作するためのジェスチャについて説明し、Windows Holographic を紹介します。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-107">This guide provides an intro to mixed reality, gestures for interacting with holograms, and an intro to Windows Holographic.</span></span>

## <span data-ttu-id="eaf0d-108">Mixed Reality について</span><span class="sxs-lookup"><span data-stu-id="eaf0d-108">Discover mixed reality</span></span>

<span data-ttu-id="eaf0d-109">HoloLens では、ホログラムが物理環境と一体化して、現実世界の一部であるかのような見た目やサウンドを生み出します。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-109">On HoloLens, holograms blend with your physical environment to look and sound like they're part of your world.</span></span> <span data-ttu-id="eaf0d-110">ホログラムが自分の周囲にあっても、自分の周りに実在するものを見て、自由に動き、他の人々や物体とやり取りすることができます。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-110">Even when holograms are all around you, you can still see your surroundings, move freely, and interact with other people and objects.</span></span> <span data-ttu-id="eaf0d-111">このエクスペリエンスを "Mixed Reality" と呼びます。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-111">We call this experience "mixed reality."</span></span>

<span data-ttu-id="eaf0d-112">ホログラフィック フレームによって、ユーザーの目が細部に最も敏感になる位置にホログラムが配置されます。レンズが透明であるため、ユーザーの周辺視野が妨害されません。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-112">The holographic frame positions your holograms where your eyes are most sensitive to detail, and the see-through lenses leave your peripheral vision unobscured.</span></span> <span data-ttu-id="eaf0d-113">立体音響により、ホログラムが自分の背後にある場合でもホログラムを特定できます。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-113">With spatial sound, you can pinpoint a hologram even if it’s behind you.</span></span> <span data-ttu-id="eaf0d-114">HoloLens はユーザーの環境を認識して理解するため、実際の物体の上および周囲にホログラムを配置できます。アプリやゲームでも同様のことができます。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-114">And because HoloLens learns and understands your environment, you can place holograms on and around real objects—and so can your apps and games.</span></span> <span data-ttu-id="eaf0d-115">そのため、ゲームのキャラクターがソファに座ったり、[宇宙ロボットが突然壁から出てきたりすることもあり得ます](https://www.microsoft.com/store/apps/9nblggh5fv3j)。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-115">So a character in a game might sit down on your sofa, or [space robots could bust out of your walls](https://www.microsoft.com/store/apps/9nblggh5fv3j).</span></span>

## <span data-ttu-id="eaf0d-116">手を使って HoloLens を操作する</span><span class="sxs-lookup"><span data-stu-id="eaf0d-116">Use HoloLens with your hands</span></span>

<span data-ttu-id="eaf0d-117">HoloLens の操作は、スマートフォンの使用によく似ています。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-117">Getting around HoloLens is a lot like using your smart phone.</span></span> <span data-ttu-id="eaf0d-118">Holographic のウィンドウ、メニュー、およびボタンは、手を使って操作できます。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-118">You can use your hands to manipulate holographic windows, menus, and buttons.</span></span>  <span data-ttu-id="eaf0d-119">ポイント、クリック、タップの代わりに、視線入力、[声](hololens-cortana.md)、手の動きを使用してアプリやホログラムを選択し、HoloLens を操作できます。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-119">Instead of pointing, clicking, or tapping, you'll use your gaze, your [voice](hololens-cortana.md), and gestures to select apps and holograms and to get around HoloLens.</span></span>

<span data-ttu-id="eaf0d-120">このような基本操作を知っていれば、HoloLens の操作は簡単です。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-120">When you know these basic interactions, getting around on HoloLens will be a snap.</span></span>

<span data-ttu-id="eaf0d-121">ここでは、初めて HoloLens を使用する場合の基本事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-121">We'll walk you through the basics the first time you use your HoloLens.</span></span> <span data-ttu-id="eaf0d-122">**スタート** メニューにもジェスチャのチュートリアルがあります。ジェスチャの詳細アプリを探してください。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-122">You'll also find a gesture tutorial on your **Start** menu—look for the Learn Gestures app.</span></span>

### <span data-ttu-id="eaf0d-123">ハンド トラッキング フレーム</span><span class="sxs-lookup"><span data-stu-id="eaf0d-123">The hand-tracking frame</span></span>

<span data-ttu-id="eaf0d-124">HoloLens には、ユーザーの左右を数フィートずつ見ることのできるセンサーが搭載されています。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-124">HoloLens has sensors that can see a few feet to either side of you.</span></span> <span data-ttu-id="eaf0d-125">手を使用する場合は、手の位置をこのフレーム内に収める必要があります。そうしないと、HoloLens では認識できません。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-125">When you use your hands, you'll need to keep them inside that frame, or HoloLens won't see them.</span></span> <span data-ttu-id="eaf0d-126">ユーザーが動くと、フレームも一緒に動きます。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-126">As you move around, the frame moves with you.</span></span>  

![HoloLens のハンド トラッキング フレームを示す画像](./images/hololens-2-gesture-frame.png)

### <span data-ttu-id="eaf0d-128">ブルームでスタート メニューを開く</span><span class="sxs-lookup"><span data-stu-id="eaf0d-128">Open the Start menu with bloom</span></span>

<span data-ttu-id="eaf0d-129">**スタート** メニューを開くには:</span><span class="sxs-lookup"><span data-stu-id="eaf0d-129">To open the **Start** menu:</span></span>

1. <span data-ttu-id="eaf0d-130">ジェスチャ フレームに収まるように、手を自分の正面に出します。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-130">Hold your hand in front of you so it's in the gesture frame.</span></span>
1. <span data-ttu-id="eaf0d-131">ブルーム: すべての指をすぼめてから、手を開きます。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-131">Bloom: bring all of your fingers together then open your hand.</span></span>
  ![ブルーム ジェスチャを示すアニメーション](./images/hololens-bloom.gif)

### <span data-ttu-id="eaf0d-133">視線入力とエアタップでホログラムを選択する</span><span class="sxs-lookup"><span data-stu-id="eaf0d-133">Select holograms with gaze and air tap</span></span>

<span data-ttu-id="eaf0d-134">アプリまたはその他のホログラムを選択するには、選択するホログラムを直接見ながらエアタップします。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-134">To select an app or other hologram, air tap it while looking directly at the hologram you're selecting.</span></span> <span data-ttu-id="eaf0d-135">これを行うには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-135">To do this, follow these steps:</span></span>

1. <span data-ttu-id="eaf0d-136">選択するホログラムを見つめます。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-136">Gaze at the hologram you want to select.</span></span>
1. <span data-ttu-id="eaf0d-137">人差し指をまっすぐ上に伸ばして、天井を指します。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-137">Point your index finger straight up toward the ceiling.</span></span>
1. <span data-ttu-id="eaf0d-138">エアタップ: 指先を下げてから、またすばやく上げます。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-138">Air tap: lower your finger, then quickly raise it.</span></span>
   ![エアタップ ジェスチャのアニメーション](./images/hololens-air-tap.gif)

### <span data-ttu-id="eaf0d-140">声を使用してホログラムを選択する</span><span class="sxs-lookup"><span data-stu-id="eaf0d-140">Select a hologram by using your voice</span></span>

1. <span data-ttu-id="eaf0d-141">視線カーソルは、頭を動かすことで移動するドットです。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-141">The gaze cursor is a dot that you move around by moving your head.</span></span> <span data-ttu-id="eaf0d-142">これを使用すると、音声コマンドの対象を高い精度で指定できます。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-142">You can use it to target voice commands with precision.</span></span>
1. <span data-ttu-id="eaf0d-143">選択対象のホログラムを見つめます。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-143">Gaze at the hologram that you want to select.</span></span>
1. <span data-ttu-id="eaf0d-144">ホログラムを選択するには、「選択」と言います。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-144">To select the hologram, say "Select."</span></span>

## <span data-ttu-id="eaf0d-145">ホログラムとアプリ</span><span class="sxs-lookup"><span data-stu-id="eaf0d-145">Holograms and apps</span></span>

<span data-ttu-id="eaf0d-146">それではジェスチャを試してみましょう。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-146">Now it's time to put gestures to the test!</span></span>

<span data-ttu-id="eaf0d-147">インストールされているアプリは[スタート メニュー](holographic-home.md)にありますが、Microsoft Store にはさらに多くの HoloLens (第 1 世代) 用アプリがあります。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-147">You'll find your installed apps in the [Start menu](holographic-home.md) and there are more apps for HoloLens (1st gen) in the Microsoft Store.</span></span>

<span data-ttu-id="eaf0d-148">**スタート** メニューを開き、アプリを選択しましょう。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-148">Open the **Start** menu and select an app!</span></span>

<span data-ttu-id="eaf0d-149">HoloLens でのアプリの使用は、PC での場合と少し異なります。一部のアプリでは、2D ビューが使用され、他の Windows アプリケーションと同様の外観です。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-149">Using apps on HoloLens is a little different from on a PC: Some apps use a 2D view and look like other Windows applications.</span></span> <span data-ttu-id="eaf0d-150">他のアプリ (イマーシブ アプリ) では 3D ビューが使用されます。起動した場合、見えるのはそのアプリだけになります。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-150">Other apps (immersive apps) use a 3D view and when you launch them, they become the only app you see.</span></span>

<span data-ttu-id="eaf0d-151">アプリ ウィンドウまたはアプリ起動ツールを配置すると、削除するまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-151">When you place an app window or app launcher, it will stay put until you remove it.</span></span> <span data-ttu-id="eaf0d-152">Mixed Reality ホームにあるホログラムは、いつでも移動またはサイズ変更できます。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-152">You can move or resize these holograms in your mixed reality home at any time.</span></span>

## <span data-ttu-id="eaf0d-153">アプリの移動、サイズ変更、回転</span><span class="sxs-lookup"><span data-stu-id="eaf0d-153">Move, resize, and rotate apps</span></span>

<span data-ttu-id="eaf0d-154">HoloLens でのアプリの移動とサイズ変更は、PC の場合と少し異なります。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-154">Moving and resizing apps on HoloLens works a bit differently than it does on a PC.</span></span> <span data-ttu-id="eaf0d-155">アプリをドラッグする代わりに、見つめる動作と共に[ジェスチャ](https://support.microsoft.com/help/12644/hololens-use-gestures)または[クリッカー](hololens1-clicker.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-155">Instead of dragging the app, you'll use your gaze, along with a [gesture](https://support.microsoft.com/help/12644/hololens-use-gestures) or the [clicker](hololens1-clicker.md).</span></span> <span data-ttu-id="eaf0d-156">アプリ ウィンドウを 3D 空間内で回転させることもできます。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-156">You can also rotate an app window in 3D space.</span></span>

> [!TIP]
> <span data-ttu-id="eaf0d-157">音声を使ってアプリの位置やサイズを調節することもできます。アプリを見つめて、「正面から見る」、「もっと大きく」、「もっと小さく」と言います。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-157">Rearrange apps using your voice - gaze at an app and say "Face me," "Bigger," or "Smaller."</span></span> <span data-ttu-id="eaf0d-158">または、Cortana を使ってアプリを動かすには、「Hey Cortana, move \**app name\** here」 (コルタナさん、"アプリ名" をここに移動して) と言います。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-158">Or have Cortana move an app for you: say "Hey Cortana, move \**app name\** here."</span></span>

### <span data-ttu-id="eaf0d-159">アプリを移動する</span><span class="sxs-lookup"><span data-stu-id="eaf0d-159">Move an app</span></span>

<span data-ttu-id="eaf0d-160">アプリ (アプリ ウィンドウのタイトル バーの部分) を見つめ、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-160">Gaze at the app (at the title bar of an app window), and then do one of the following.</span></span>

- <span data-ttu-id="eaf0d-161">アプリを長押しして選択します。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-161">Tap and hold to select the app.</span></span> <span data-ttu-id="eaf0d-162">アプリの移動先まで手を動かし、指を上げてアプリを配置します。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-162">Move your hand to position the app, and raise your finger to place it.</span></span>
- <span data-ttu-id="eaf0d-163">**[調整]** を選択し、長押しして、アプリの移動先まで手を動かします。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-163">Select **Adjust**, tap and hold, and move your hand to position the app.</span></span> <span data-ttu-id="eaf0d-164">指を上げてアプリを配置し、**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-164">Raise your finger to place it, then select **Done**.</span></span>
- <span data-ttu-id="eaf0d-165">**[調整]** を選択し、クリッカーを長押しして、アプリの移動先まで手を動かします。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-165">Select **Adjust**, click and hold the clicker, and move your hand to position the app.</span></span> <span data-ttu-id="eaf0d-166">クリッカーを離し、**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-166">Release the clicker, then select **Done**.</span></span>

> [!TIP]
> <span data-ttu-id="eaf0d-167">アプリを移動するときにドロップする場合は、自分の手を視線で追い、手がジェスチャ フレームから出ないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-167">If you drop apps when you move them, make sure to keep your hand in the gesture frame by following it with your gaze.</span></span>

### <span data-ttu-id="eaf0d-168">アプリのサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="eaf0d-168">Resize an app</span></span>

<span data-ttu-id="eaf0d-169">アプリを見つめて、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-169">Gaze at the app, and then do one of the following.</span></span>

- <span data-ttu-id="eaf0d-170">アプリ ウィンドウの隅または縁を見つめて、長押しします。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-170">Gaze at a corner or edge of an app window, and tap and hold.</span></span> <span data-ttu-id="eaf0d-171">手を動かしてアプリのサイズを変更し、終わったら指を上げます。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-171">Move your hand to change the app's size, and raise your finger when you're done.</span></span>
- <span data-ttu-id="eaf0d-172">**[調整]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-172">Select **Adjust**.</span></span> <span data-ttu-id="eaf0d-173">アプリの隅にある青色の正方形の 1 つを見つめて、長押しし、手を動かしてアプリのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-173">Gaze at one of the blue squares at the corners of the app, tap and hold, then move your hand to resize the app.</span></span> <span data-ttu-id="eaf0d-174">指を上げてアプリを離し、**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-174">Raise your finger to release it, then select **Done**.</span></span>
- <span data-ttu-id="eaf0d-175">**[調整]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-175">Select **Adjust**.</span></span> <span data-ttu-id="eaf0d-176">アプリの隅にある青色の正方形の 1 つを見つめて、クリッカーを長押しし、手を動かしてアプリのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-176">Gaze at one of the blue squares at the corners of the app, click and hold the clicker, then move your hand to resize the app.</span></span> <span data-ttu-id="eaf0d-177">クリッカーを離し、**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-177">Release the clicker, then select **Done**.</span></span>

> [!TIP]
> <span data-ttu-id="eaf0d-178">調節モードでは、任意のホログラムを移動またはサイズ変更できます。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-178">In Adjust mode, you can move or resize any hologram.</span></span>

### <span data-ttu-id="eaf0d-179">アプリを回転させる</span><span class="sxs-lookup"><span data-stu-id="eaf0d-179">Rotate an app</span></span>

<span data-ttu-id="eaf0d-180">アプリを見つめ、両手で長押しして選択します。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-180">Gaze at the app, and tap and hold with both hands to select it.</span></span> <span data-ttu-id="eaf0d-181">アプリを回転させるには、一方の手を固定し、それを中心にもう一方の手で円弧を描きます。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-181">Rotate the app by keeping one hand steady and moving your other hand around it.</span></span> <span data-ttu-id="eaf0d-182">操作を終えたら、両手の人差し指を上げます。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-182">When you're done, raise both index fingers.</span></span>

### <span data-ttu-id="eaf0d-183">アプリ ウィンドウのコンテンツをスクロールする</span><span class="sxs-lookup"><span data-stu-id="eaf0d-183">Scroll content in an app window</span></span>

<span data-ttu-id="eaf0d-184">アプリ ウィンドウのコンテンツを見つめます。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-184">Gaze at the content of the app window.</span></span> <span data-ttu-id="eaf0d-185">タップして長押しし、手を少し上方向または下方向へ動かして、コンテンツをスクロールします。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-185">Tap and hold and then move your hand slightly upwards or downwards to scroll the content.</span></span>

## <span data-ttu-id="eaf0d-186">HoloLens (第 1 世代) クリッカーについて</span><span class="sxs-lookup"><span data-stu-id="eaf0d-186">Meet the HoloLens (1st gen) Clicker</span></span>

<span data-ttu-id="eaf0d-187">[HoloLens (第 1 世代) クリッカー](hololens1-clicker.md)は、ホログラムを操作するもう 1 つの方法です。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-187">The [HoloLens (1st Gen) clicker](hololens1-clicker.md) gives you another way to interact with holograms.</span></span> <span data-ttu-id="eaf0d-188">HoloLens と[ペアリング](hololens-connect-devices.md)し、見つめる動作と共に使用して、選択、スクロールなどを行います。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-188">[Pair it](hololens-connect-devices.md) with your HoloLens and then use it along with your gaze to select, scroll, and more.</span></span>

## <span data-ttu-id="eaf0d-189">次のステップ</span><span class="sxs-lookup"><span data-stu-id="eaf0d-189">Next steps</span></span>

<span data-ttu-id="eaf0d-190">お疲れさまでした。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-190">Congratulations!</span></span> <span data-ttu-id="eaf0d-191">HoloLens (第 1 世代) を使用する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-191">you're ready to use HoloLens (1st gen).</span></span>

<span data-ttu-id="eaf0d-192">これで、特定のニーズに合わせて HoloLens (第 1 世代) を構成できます。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-192">Now you can configure your HoloLens (1st gen) to meet your specific needs.</span></span>

[<span data-ttu-id="eaf0d-193">マウスやキーボードなどの bluetooth デバイスを接続する</span><span class="sxs-lookup"><span data-stu-id="eaf0d-193">Connect bluetooth devices like mouse and keyboard</span></span>](hololens-connect-devices.md)

[<span data-ttu-id="eaf0d-194">音声と Cortana について</span><span class="sxs-lookup"><span data-stu-id="eaf0d-194">Learn more about Voice and Cortana</span></span>](hololens-cortana.md)

### <span data-ttu-id="eaf0d-195">トラブルシューティング: </span><span class="sxs-lookup"><span data-stu-id="eaf0d-195">Help!</span></span> <span data-ttu-id="eaf0d-196">ホログラムが見つからない</span><span class="sxs-lookup"><span data-stu-id="eaf0d-196">I don't see my holograms</span></span>

<span data-ttu-id="eaf0d-197">HoloLens の使用中に配置したホログラムが見つからない場合には、次の方法を試すことができます。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-197">If you don’t see holograms that you’ve placed while using HoloLens, here are some things to try:</span></span>

- <span data-ttu-id="eaf0d-198">適切な領域を見ているか確認します。ホログラムがある場所は、配置した場所です。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-198">Make sure that you’re looking in the right area&mdash;remember, holograms stay where you left them!</span></span>
- <span data-ttu-id="eaf0d-199">今いる場所が、直射日光が当たりすぎない明るい部屋であるか確認します。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-199">Make sure that you're in a well-lit room without a lot of direct sunlight.</span></span>
- <span data-ttu-id="eaf0d-200">しばらくお待ちください。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-200">Wait.</span></span> <span data-ttu-id="eaf0d-201">HoloLens が空間を認識できない場合、以前に配置されたホログラムが再表示されるまでに最大で 1 分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-201">When HoloLens has trouble recognizing your space, previously placed holograms can take up to a minute to reappear.</span></span>
- <span data-ttu-id="eaf0d-202">問題が解決しない場合は、**[設定]** > **[システム]** > **[ホログラム]** でホログラムのストレージ データを消去して、Mixed Reality ホームにホログラムをもう一度配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="eaf0d-202">If issue persists, you may want to clear out your Holograms storage data in **Settings** > **System** > **Holograms**, then place holograms in mixed reality home again.</span></span>
