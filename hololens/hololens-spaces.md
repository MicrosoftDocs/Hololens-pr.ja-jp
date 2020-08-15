---
title: HoloLens を使用して物理的スペースをマッピングする
description: HoloLens は、時間の経過とともに空間がどのように見えるかを学習します。 ユーザーは、HoloLens を空間内で特定の方法で移動することにより、このプロセスを容易にすることができます。
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: HoloLens、Windows Mixed Reality、デザイン、空間マッピング、HoloLens、表面再構築、メッシュ、ヘッド トラッキング、マッピング
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: 7cedf2af90744477c33736087c85a43168167707
ms.sourcegitcommit: 6f2ec9ced776166f96eddcd601bef5de715703a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2020
ms.locfileid: "10931839"
---
# <span data-ttu-id="27f85-105">HoloLens を使用して物理的スペースをマッピングする</span><span class="sxs-lookup"><span data-stu-id="27f85-105">Map physical spaces with HoloLens</span></span>

<span data-ttu-id="27f85-106">HoloLens は、ホログラムを物理世界と融合させます。</span><span class="sxs-lookup"><span data-stu-id="27f85-106">HoloLens blends holograms with your physical world.</span></span> <span data-ttu-id="27f85-107">そのためには、HoloLens は周りの物理世界について学び、ホログラムをその空間内のどこに配置するかを覚えておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="27f85-107">To do that, HoloLens has to learn about the physical world around you and remember where you place holograms within that space.</span></span>

<span data-ttu-id="27f85-108">時間の経過とともに、HoloLens は、それが見た環境の*空間マップ*を構築します。</span><span class="sxs-lookup"><span data-stu-id="27f85-108">Over time, the HoloLens builds up a *spatial map* of the environment that it has seen.</span></span>  <span data-ttu-id="27f85-109">HoloLens は、環境の変化に応じてマップを更新します。</span><span class="sxs-lookup"><span data-stu-id="27f85-109">HoloLens updates the map as the environment changes.</span></span> <span data-ttu-id="27f85-110">ログインしてデバイスがオンになっている限り、HoloLens は空間マップを作成および更新します。</span><span class="sxs-lookup"><span data-stu-id="27f85-110">As long as you are logged in and the device is turned on, HoloLens creates and updates your spatial maps.</span></span> <span data-ttu-id="27f85-111">カメラを空間に向けた状態でデバイスを保持または装着すると、HoloLens はエリアをマップしようとします。</span><span class="sxs-lookup"><span data-stu-id="27f85-111">If you hold or wear the device with the cameras pointed at a space, the HoloLens tries to map the area.</span></span> <span data-ttu-id="27f85-112">HoloLens は時間の経過とともに自然に空間を学習しますが、HoloLens が空間をより迅速かつ効率的にマッピングするのに役立つ方法があります。</span><span class="sxs-lookup"><span data-stu-id="27f85-112">While the HoloLens learns a space naturally over time, there are ways in which you can help HoloLens map your space more quickly and efficiently.</span></span>  

> [!NOTE]
> <span data-ttu-id="27f85-113">HoloLens が空間をマッピングできない場合、またはキャリブレーションの範囲外の場合、HoloLens は制限モードに入る場合があります。</span><span class="sxs-lookup"><span data-stu-id="27f85-113">If your HoloLens can't map your space or is out of calibration, HoloLens may enter Limited mode.</span></span> <span data-ttu-id="27f85-114">制限モードでは、周囲にホログラムを配置することはできません。</span><span class="sxs-lookup"><span data-stu-id="27f85-114">In Limited mode, you won't be able to place holograms in your surroundings.</span></span>

<span data-ttu-id="27f85-115">この記事では、HoloLens が空間をマッピングする方法、空間マッピングを改善する方法、および HoloLens が収集する空間データを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="27f85-115">This article explains how HoloLens maps spaces, how to improve spatial mapping, and how to manage the spatial data that HoloLens collects.</span></span>

## <span data-ttu-id="27f85-116">空間の選択とセットアップ</span><span class="sxs-lookup"><span data-stu-id="27f85-116">Choosing and setting up and your space</span></span>

<span data-ttu-id="27f85-117">環境内の機能により、HoloLens が空間を解釈するのが困難になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="27f85-117">Features in your environment can make it difficult for the HoloLens to interpret a space.</span></span> <span data-ttu-id="27f85-118">ライト レベル、空間内のマテリアル、オブジェクトのレイアウトなどはすべて、HoloLens がエリアをマップする方法に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="27f85-118">Light levels, materials in the space, the layout of objects, and more can all affect how HoloLens maps an area.</span></span>

<span data-ttu-id="27f85-119">HoloLens は特定の種類の環境で最適に動作します。</span><span class="sxs-lookup"><span data-stu-id="27f85-119">HoloLens works best in certain kinds of environments.</span></span> <span data-ttu-id="27f85-120">最適な空間マップを作成するには、十分な光と十分な空間がある部屋を選択してください。</span><span class="sxs-lookup"><span data-stu-id="27f85-120">To produce the best spatial map, choose a room that has adequate light and plenty of space.</span></span> <span data-ttu-id="27f85-121">暗い空間や、暗い、輝く、または半透明の表面がたくさんある部屋 (鏡やガーゼのカーテンなど) は避けてください。</span><span class="sxs-lookup"><span data-stu-id="27f85-121">Avoid dark spaces and rooms that have a lot of dark, shiny, or translucent surfaces (for instance, mirrors or gauzy curtains).</span></span>

<span data-ttu-id="27f85-122">HoloLens は屋内での使用に最適化されています。</span><span class="sxs-lookup"><span data-stu-id="27f85-122">HoloLens is optimized for indoor use.</span></span> <span data-ttu-id="27f85-123">空間マッピングは、Wi-Fi がオンになっている場合にも最適に機能しますが、ネットワークに接続する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="27f85-123">Spatial mapping also works best when Wi-Fi is turned on, although it doesn't have to be connected to a network.</span></span> <span data-ttu-id="27f85-124">HoloLens は、接続または認証されていなくても、Wi-Fi アクセス　ポイントを取得できます。</span><span class="sxs-lookup"><span data-stu-id="27f85-124">HoloLens can obtain Wi-Fi access points even if it is not connected or authenticated.</span></span> <span data-ttu-id="27f85-125">HoloLens 機能は、アクセス ポイントがインターネットに接続されているか、イントラネット/ローカルのみであるかを変更しません。</span><span class="sxs-lookup"><span data-stu-id="27f85-125">HoloLens functionality does not change whether the access points are internet-connected or intranet/local only.</span></span>

<span data-ttu-id="27f85-126">HoloLens は、つまずく危険がない安全な場所でのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="27f85-126">Only use HoloLens in safe places with no tripping hazards.</span></span> <span data-ttu-id="27f85-127">[安全性に関する詳細](https://support.microsoft.com/help/4023454/safety-information)。</span><span class="sxs-lookup"><span data-stu-id="27f85-127">[More on safety](https://support.microsoft.com/help/4023454/safety-information).</span></span>

## <span data-ttu-id="27f85-128">空間マッピング</span><span class="sxs-lookup"><span data-stu-id="27f85-128">Mapping your space</span></span>

<span data-ttu-id="27f85-129">これで、空間マッピングを開始する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="27f85-129">Now you're ready to start mapping your spare.</span></span>  <span data-ttu-id="27f85-130">HoloLens が周囲のマッピングを開始すると、空間全体に広がるメッシュ グラフィックが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27f85-130">When HoloLens starts mapping your surroundings, you'll see a mesh graphic spreading over the space.</span></span>  <span data-ttu-id="27f85-131">Mixed Reality ホームでは、マップされた表面を選択することで、マップをトリガーして表示できます。</span><span class="sxs-lookup"><span data-stu-id="27f85-131">In mixed reality home, you can trigger the map to show by selecting on a mapped surface.</span></span>

<span data-ttu-id="27f85-132">優れた空間マップを作成するためのガイドラインを次に示します。</span><span class="sxs-lookup"><span data-stu-id="27f85-132">Here are guidelines for building a great spatial map.</span></span>

### <span data-ttu-id="27f85-133">エリアのシナリオを理解する</span><span class="sxs-lookup"><span data-stu-id="27f85-133">Understand the scenarios for the area</span></span>

<span data-ttu-id="27f85-134">マップが適切で完全になるように、HoloLens を使用する場所で最も多くの時間を費やすことが重要です。</span><span class="sxs-lookup"><span data-stu-id="27f85-134">It is important to spend the most time where you will be using the HoloLens, so that the map is relevant and complete.</span></span> <span data-ttu-id="27f85-135">たとえば、HoloLens のユーザー シナリオにポイント A からポイント B への移動が含まれている場合は、移動しながらすべての方向を見て、そのパスを 2 ~ 3 回歩きます。</span><span class="sxs-lookup"><span data-stu-id="27f85-135">For example, if a user scenario for HoloLens involves moving from Point A to Point B, walk that path two to three times, looking in all directions as you move.</span></span>  

### <span data-ttu-id="27f85-136">空間をゆっくり歩く</span><span class="sxs-lookup"><span data-stu-id="27f85-136">Walk slowly around the space</span></span>

<span data-ttu-id="27f85-137">エリアの周りをあまりにも速く歩くと、HoloLens がマッピング エリアを見落とす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="27f85-137">If you walk too quickly around the area, it's likely that the HoloLens will miss mapping areas.</span></span> <span data-ttu-id="27f85-138">周囲をゆっくりと歩き、5 ~ 8 フィートごとに立ち止まって周囲を見回します。</span><span class="sxs-lookup"><span data-stu-id="27f85-138">Walk slowly around the space, stopping every 5-8 feet to look around at your surroundings.</span></span>  

<span data-ttu-id="27f85-139">スムーズな動きは、HoloLens マップをより効率的にするのにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="27f85-139">Smooth movements also help the HoloLens map more efficiently.</span></span>

### <span data-ttu-id="27f85-140">全方位を見る</span><span class="sxs-lookup"><span data-stu-id="27f85-140">Look in all directions</span></span>

<span data-ttu-id="27f85-141">空間をマッピングしながら見回すと、HoloLens にポイントが相対的位置に関するデータが多くなります。</span><span class="sxs-lookup"><span data-stu-id="27f85-141">Looking around as you map the space gives the HoloLens more data on where points are relative to each other.</span></span>  

<span data-ttu-id="27f85-142">たとえば、見上げないと、HoloLens は部屋の天井がどこにあるのかわからない場合があります。</span><span class="sxs-lookup"><span data-stu-id="27f85-142">If you don't look up, for example, the HoloLens may not know where the ceiling in a room is.</span></span>  

<span data-ttu-id="27f85-143">空間をマッピングするときは、床を見下ろすことを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="27f85-143">Don't forget to look down at the floor as you map the space.</span></span>

### <span data-ttu-id="27f85-144">重要なエリアを複数回カバーする</span><span class="sxs-lookup"><span data-stu-id="27f85-144">Cover key areas multiple times</span></span>

<span data-ttu-id="27f85-145">エリアを複数回移動すると、最初のウォークスルーで見逃した可能性がある機能を選択するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="27f85-145">Moving through an area multiple times will help pick up features you may have missed on the first walkthrough.</span></span> <span data-ttu-id="27f85-146">理想的なマップを作成するには、エリアを 2 ~ 3 回通過します。</span><span class="sxs-lookup"><span data-stu-id="27f85-146">To build an ideal map, try traversing an area two to three times.</span></span>

<span data-ttu-id="27f85-147">可能であれば、これらの動きを繰り返しながら、一方向に歩いて、それから振り返って来た道を歩いてみましょう。</span><span class="sxs-lookup"><span data-stu-id="27f85-147">If possible, while repeating these movements, spend time walking through an area in one direction, then turn around and walk back the way you came.</span></span>

### <span data-ttu-id="27f85-148">時間をかけてエリアをマッピングする</span><span class="sxs-lookup"><span data-stu-id="27f85-148">Take your time mapping the area</span></span>

<span data-ttu-id="27f85-149">HoloLens が完全にマッピングして周囲に適応するまでには、15 ~ 20 分かかります。</span><span class="sxs-lookup"><span data-stu-id="27f85-149">It can take between 15 and 20 minutes for the HoloLens to fully map and adjust itself to its surroundings.</span></span> <span data-ttu-id="27f85-150">HoloLens を頻繁に使用する予定の空間がある場合、前もって時間を取って空間をマップすると、後で問題が発生することを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="27f85-150">If you have a space in which you plan to use a HoloLens frequently, taking that time up front to map the space can prevent issues later on.</span></span>  

## <span data-ttu-id="27f85-151">空間マップで起こりうるエラー</span><span class="sxs-lookup"><span data-stu-id="27f85-151">Possible errors in the spatial map</span></span>

<span data-ttu-id="27f85-152">空間マッピング データのエラーは、いくつかのカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="27f85-152">Errors in spatial mapping data fall into a few categories:</span></span>

- <span data-ttu-id="27f85-153">*穴*: 空間マッピング データに実際の表面がありません。</span><span class="sxs-lookup"><span data-stu-id="27f85-153">*Holes*: Real-world surfaces are missing from the spatial mapping data.</span></span>
- <span data-ttu-id="27f85-154">*幻覚*: 現実世界には存在しない表面が空間マッピング データに存在します。</span><span class="sxs-lookup"><span data-stu-id="27f85-154">*Hallucinations*: Surfaces exist in the spatial mapping data that do not exist in the real world.</span></span>
- <span data-ttu-id="27f85-155">*ワームホール*: HoloLens は、実際のマップとは別の部分にあると考えて、空間マップの一部を「失います」。</span><span class="sxs-lookup"><span data-stu-id="27f85-155">*Wormholes*: HoloLens 'loses' part of the spatial map by thinking it is in a different part of the map than it actually is.</span></span>
- <span data-ttu-id="27f85-156">*バイアス*: 空間マッピング データの表面は、押し込まれたり引き出されたりして実際の表面と不完全に整列しています。</span><span class="sxs-lookup"><span data-stu-id="27f85-156">*Bias*: Surfaces in the spatial mapping data are imperfectly aligned with real-world surfaces, either pushed in or pulled out.</span></span>

<span data-ttu-id="27f85-157">これらのエラーが表示された場合は、[FeedbackHub](hololens-feedback.md) を使用してフィードバックを送信してください。</span><span class="sxs-lookup"><span data-stu-id="27f85-157">If you see any of these errors please use the [FeedbackHub](hololens-feedback.md) to send feedback.</span></span>

## <span data-ttu-id="27f85-158">空間データのセキュリティとストレージ</span><span class="sxs-lookup"><span data-stu-id="27f85-158">Security and storage for spatial data</span></span>

<span data-ttu-id="27f85-159">Microsoft HoloLens 以降用の Windows 10 バージョン 1803 更新プログラムでは、マッピング データをローカル (デバイス上の) データベースに保存します。</span><span class="sxs-lookup"><span data-stu-id="27f85-159">Windows 10 version 1803 update for Microsoft HoloLens and later stores mapping data in a local (on-device) database.</span></span>

<span data-ttu-id="27f85-160">HoloLens ユーザーは、デバイスが PC に接続されている場合やファイル エクスプローラー アプリを使用している場合でも、マップ データベースに直接アクセスできません。</span><span class="sxs-lookup"><span data-stu-id="27f85-160">HoloLens users cannot directly access the map database, even when the device is plugged into a PC or when using the File Explorer app.</span></span> <span data-ttu-id="27f85-161">HoloLens で BitLocker を有効にすると、保存されたマップ データもボリューム全体とともに暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="27f85-161">When BitLocker is enabled on HoloLens, the stored map data is also encrypted along with the entire volume.</span></span>

### <span data-ttu-id="27f85-162">HoloLens からマップ データと既知の空間を削除する</span><span class="sxs-lookup"><span data-stu-id="27f85-162">Remove map data and known spaces from HoloLens</span></span>

<span data-ttu-id="27f85-163">**[設定]、[システム]、[ホログラム]** でマップ データを削除するには、次の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="27f85-163">There are two options for deleting map data in **Settings > System > Holograms**:</span></span>

- <span data-ttu-id="27f85-164">近くのホログラムを削除するには、[**近くのホログラムを削除する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="27f85-164">To delete nearby holograms, select **Remove nearby holograms**.</span></span> <span data-ttu-id="27f85-165">このコマンドは、現在の空間のマップ データと固定ホログラムをクリアします。</span><span class="sxs-lookup"><span data-stu-id="27f85-165">This command clears the map data and anchored holograms for the current space.</span></span> <span data-ttu-id="27f85-166">同じ空間でデバイスを使い続けると、削除された情報を置き換える新しいマップ セクションが作成および保存されます。</span><span class="sxs-lookup"><span data-stu-id="27f85-166">If you continue to use the device in the same space, it creates and stores a brand new map section to replace the deleted information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="27f85-167">「近くの」ホログラムは、現在の空間の同じマップ セクション内に固定されているホログラムです。</span><span class="sxs-lookup"><span data-stu-id="27f85-167">"Nearby" holograms are holograms that are anchored within the same map section in the current space.</span></span>

   <span data-ttu-id="27f85-168">たとえば、このオプションを使用して、自宅関連のマップ データに影響を与えることなく、仕事関連のマップ データをクリアできます。</span><span class="sxs-lookup"><span data-stu-id="27f85-168">For example, you can use this option to clear work-related map data without affecting any home-related map data.</span></span>

- <span data-ttu-id="27f85-169">すべてのホログラムを削除するには、[**すべてのホログラムを削除する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="27f85-169">To delete all holograms, select **Remove all holograms**.</span></span> <span data-ttu-id="27f85-170">このコマンドは、デバイスに格納されているすべてのマップ データとすべての固定ホログラムをクリアします。</span><span class="sxs-lookup"><span data-stu-id="27f85-170">This command clears all map data that is stored on the device as well as all anchored holograms.</span></span> <span data-ttu-id="27f85-171">ホログラムを明示的に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27f85-171">You will need to explicitly place any holograms.</span></span> <span data-ttu-id="27f85-172">以前に配置したホログラムを再検出することはできません。</span><span class="sxs-lookup"><span data-stu-id="27f85-172">You will not be able to rediscover the previously-placed holograms.</span></span>

> [!NOTE]
> <span data-ttu-id="27f85-173">近くまたはすべてのホログラムを削除すると、HoloLens はすぐに現在の空間のスキャンとマッピングを開始します。</span><span class="sxs-lookup"><span data-stu-id="27f85-173">After you remove nearby or all holograms, HoloLens immediately starts scanning and mapping the current space.</span></span>

### <span data-ttu-id="27f85-174">空間マップの Wi-Fi データ</span><span class="sxs-lookup"><span data-stu-id="27f85-174">Wi-Fi data in spatial maps</span></span>

<span data-ttu-id="27f85-175">HoloLens は Wi-Fi 特性を格納して、既知の空間の HoloLens データベース内に格納されているホログラムの場所とマップ セクションを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="27f85-175">HoloLens stores Wi-Fi characteristics to help correlate hologram locations and map sections that are stored within the HoloLens database of known spaces.</span></span> <span data-ttu-id="27f85-176">Wi-Fi 特性に関する情報にはユーザーはアクセスできず、クラウドまたはテレメトリを使用して Microsoft に送信されません。</span><span class="sxs-lookup"><span data-stu-id="27f85-176">Information about Wi-Fi characteristics is not accessible to users, and not sent to Microsoft using the cloud or using telemetry.</span></span>

<span data-ttu-id="27f85-177">Wi-Fi が有効になっている限り、HoloLens はマップ データを近くの Wi-Fi アクセス ポイントと関連付けます。</span><span class="sxs-lookup"><span data-stu-id="27f85-177">As long as Wi-Fi is enabled, HoloLens correlates map data with nearby Wi-Fi access points.</span></span> <span data-ttu-id="27f85-178">ネットワークが接続されていても、近くで検出されても、動作に違いはありません。</span><span class="sxs-lookup"><span data-stu-id="27f85-178">There is no difference in behavior whether a network is connected or just detected nearby.</span></span> <span data-ttu-id="27f85-179">Wi-Fi が無効になっている場合でも、HoloLens は空間を検索します。</span><span class="sxs-lookup"><span data-stu-id="27f85-179">If Wi-Fi is disabled, HoloLens still searches the space.</span></span> <span data-ttu-id="27f85-180">ただし、HoloLens は空間データベース内のより多くのマップ データを検索する必要があり、ホログラムを見つけるためにより多くの時間が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="27f85-180">However, HoloLens has to search more of the map data within the spaces database, and may need more time to find holograms.</span></span> <span data-ttu-id="27f85-181">Wi-Fi 情報がない場合、HoloLens は、有効なスキャンを、デバイスに保存されているすべてのホログラム アンカーおよびマップ セクションと比較して、マップの正しい分割を見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="27f85-181">Without the Wi-Fi info, the HoloLens has to compare active scans to all hologram anchors and map sections that are stored on the device in order to locate the correct portion of the map.</span></span>

## <span data-ttu-id="27f85-182">関連トピック</span><span class="sxs-lookup"><span data-stu-id="27f85-182">Related topics</span></span>

- [<span data-ttu-id="27f85-183">空間マッピング設計</span><span class="sxs-lookup"><span data-stu-id="27f85-183">Spatial mapping design</span></span>](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping)
