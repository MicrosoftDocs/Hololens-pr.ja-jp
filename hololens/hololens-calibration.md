---
title: 視覚効果と快適性の向上
description: 'IPD (interpupillary distance: 瞳孔間距離) を調整すると、視覚効果の品質を向上させることができます。 HoloLens と Windows Mixed Reality イマーシブ ヘッドセットでは、IPD をカスタマイズする手段が用意されています。'
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
keywords: 調整, 快適性, 視覚, 品質, IPD
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f2c8afffdc24eedf9cb6b462448f5ed6ffc8d5d
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828772"
---
# <span data-ttu-id="7475f-105">視覚効果と快適性の向上</span><span class="sxs-lookup"><span data-stu-id="7475f-105">Improve visual quality and comfort</span></span>

<span data-ttu-id="7475f-106">HoloLens 2 と HoloLens (第 1 世代) では、ユーザーの目に合わせて調整すると性能が向上します。</span><span class="sxs-lookup"><span data-stu-id="7475f-106">HoloLens 2 and HoloLens (1st gen) both work better when they're calibrated to your unique eyes.</span></span>

<span data-ttu-id="7475f-107">どちらのデバイスでも、最適なホログラム表示エクスペリエンスを目的として調整する必要がある点では同じですが、使用する調整テクノロジと手法が異なります。</span><span class="sxs-lookup"><span data-stu-id="7475f-107">While both devices need to calibrate for the best hologram viewing experience, they use different calibration technologies and techniques.</span></span>  <span data-ttu-id="7475f-108">必要に応じて、[HoloLens 2 の調整](#calibrating-your-hololens-2)または[HoloLens (第 1 世代) の調整](#calibrating-your-hololens-1st-gen)に関する説明をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7475f-108">Jump to [HoloLens 2 calibration](#calibrating-your-hololens-2) or [HoloLens (1st gen) calibration](#calibrating-your-hololens-1st-gen).</span></span>

## <span data-ttu-id="7475f-109">HoloLens 2 の調整</span><span class="sxs-lookup"><span data-stu-id="7475f-109">Calibrating your HoloLens 2</span></span>

<span data-ttu-id="7475f-110">HoloLens 2 では、仮想環境の表示と操作のエクスペリエンスを向上させるために視線追跡テクノロジが使用されています。</span><span class="sxs-lookup"><span data-stu-id="7475f-110">HoloLens 2 uses eye-tracking technology to improve your experience seeing and interacting with the virtual environment.</span></span> <span data-ttu-id="7475f-111">HoloLens 2 を調整すると、ユーザーの視線 (およびデバイスを使用している他のユーザーの視線) を正確に追跡できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7475f-111">Calibrating the HoloLens 2 ensures that it can accurately track your eyes (and the eyes of anyone else who uses the device).</span></span> <span data-ttu-id="7475f-112">ユーザーの安心、ホログラムの整列、ハンド トラッキングにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7475f-112">It also helps with user comfort, hologram alignment, and hand tracking.</span></span> <span data-ttu-id="7475f-113">調整後は、頭部に装着したバイザーの位置がずれても、ホログラムが正しく表示されます。</span><span class="sxs-lookup"><span data-stu-id="7475f-113">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

<span data-ttu-id="7475f-114">HoloLens 2 では、次のようなときに、デバイスの調整がユーザーに求められます。</span><span class="sxs-lookup"><span data-stu-id="7475f-114">HoloLens 2 prompts a user to calibrate the device under the following circumstances:</span></span>

- <span data-ttu-id="7475f-115">ユーザーが初めてデバイスを使用する</span><span class="sxs-lookup"><span data-stu-id="7475f-115">The user is using the device for the first time</span></span>
- <span data-ttu-id="7475f-116">ユーザーが前回の調整プロセスを実施しなかった</span><span class="sxs-lookup"><span data-stu-id="7475f-116">The user previously opted out of the calibration process</span></span>
- <span data-ttu-id="7475f-117">ユーザーが前回デバイスを使用したときに、調整プロセスに失敗した</span><span class="sxs-lookup"><span data-stu-id="7475f-117">The calibration process did not succeed the last time the user used the device</span></span>
- <span data-ttu-id="7475f-118">ユーザーが調整プロファイルを削除した</span><span class="sxs-lookup"><span data-stu-id="7475f-118">The user has deleted their calibration profiles</span></span>
- <span data-ttu-id="7475f-119">デバイスはオフになり、上記のいずれかの状況が発生します。</span><span class="sxs-lookup"><span data-stu-id="7475f-119">The device is taken off and put back on and any of the above circumstances apply</span></span> 


![調整プロンプト](./images/07-et-adjust-for-your-eyes.png)

<span data-ttu-id="7475f-121">このプロセスでは、一連のターゲット (ジェム) を目視します。</span><span class="sxs-lookup"><span data-stu-id="7475f-121">During this process, you'll look at a set of targets (gems).</span></span> <span data-ttu-id="7475f-122">調整中にまばたきしても問題はありませんが、室内の他のオブジェクトではなく宝石に集中するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="7475f-122">It's fine if you blink during calibration, but try to stay focused on the gems instead of other objects in the room.</span></span>  <span data-ttu-id="7475f-123">HoloLens はこのプロセスにより、ホログラフィックの世界をレンダリングできるように、ユーザーの眼球位置を学習します。</span><span class="sxs-lookup"><span data-stu-id="7475f-123">This allows HoloLens to learn about your eye position to render your holographic world.</span></span>

![調整プロンプト](./images/07-et-hold-head-still.png)

![調整プロンプト](./images/08-et-gems.png)

![調整プロンプト](./images/09-et-adjusting.png)

<span data-ttu-id="7475f-127">調整に成功すると、成功を示す画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7475f-127">If calibration was successful, you'll see a success screen.</span></span>  <span data-ttu-id="7475f-128">調整に成功しなかった場合は、調整の失敗に関する診断について、[こちら](#troubleshooting-hololens-2-calibration)の説明をお読みください。</span><span class="sxs-lookup"><span data-stu-id="7475f-128">If not, read more about diagnosing calibration failures [here](#troubleshooting-hololens-2-calibration).</span></span>

![調整プロンプト](./images/10-et-success.png)

### <span data-ttu-id="7475f-130">デバイスまたはセッションを共有する場合の調整</span><span class="sxs-lookup"><span data-stu-id="7475f-130">Calibration when sharing a device or session</span></span>

<span data-ttu-id="7475f-131">HoloLens 2 デバイスは、複数のユーザーが共有できます。各ユーザーがデバイスのセットアップを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7475f-131">Multiple users can share a HoloLens 2 device, without a need for each person to go through device setup.</span></span> <span data-ttu-id="7475f-132">新しいユーザーがデバイスを初めて頭に装着する際には、HoloLens 2 によって、視覚調整をユーザーに求めるメッセージが自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7475f-132">When a new user puts the device on their head for the first time, HoloLens 2 automatically prompts the user to calibrate visuals.</span></span> <span data-ttu-id="7475f-133">視覚調整を実施済みのユーザーがデバイスを頭に装着すると、質の高い視覚効果と快適な表示エクスペリエンスを得られるように、ディスプレイの調整がシームレスに行われます。</span><span class="sxs-lookup"><span data-stu-id="7475f-133">When a user that has previously calibrated visuals puts the device on their head, the display seamlessly adjusts for quality and a comfortable viewing experience.</span></span>  

### <span data-ttu-id="7475f-134">調整プロセスを手動で開始する</span><span class="sxs-lookup"><span data-stu-id="7475f-134">Manually starting the calibration process</span></span>

1. <span data-ttu-id="7475f-135">スタート ジェスチャを使用して、[**スタート** メニュー](hololens2-basic-usage.md#start-gesture)を開きます。</span><span class="sxs-lookup"><span data-stu-id="7475f-135">Use the start gesture to open the [**Start** menu](hololens2-basic-usage.md#start-gesture).</span></span>
1. <span data-ttu-id="7475f-136">設定アプリが **[スタート]** にピン留めされていない場合は、**[すべてのアプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7475f-136">If the Settings app isn't pinned to **Start**, select **All Apps**.</span></span>
1. <span data-ttu-id="7475f-137">**[設定]** を選択し、**[システム]** > **[調整]** > **[目に合わせた調整]** > **[Run eye calibration]** (目に合わせた調整の実行) の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7475f-137">Select **Settings**, and then select **System** > **Calibration** > **Eye Calibration** > **Run eye calibration**.</span></span>

   ![目に合わせた調整の実行オプションが表示されている設定アプリ](./images/C-Settings.Calibration.png)

### <span data-ttu-id="7475f-139">HoloLens 2 の調整のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7475f-139">Troubleshooting HoloLens 2 calibration</span></span>

<span data-ttu-id="7475f-140">調整はほとんどのユーザーに適合しますが、調整が失敗となるケースもあります。</span><span class="sxs-lookup"><span data-stu-id="7475f-140">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="7475f-141">調整が失敗となる原因として、次のようなことが考えられます。</span><span class="sxs-lookup"><span data-stu-id="7475f-141">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="7475f-142">注意散漫になり、調整ターゲットを追っていない</span><span class="sxs-lookup"><span data-stu-id="7475f-142">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="7475f-143">デバイスのバイザーに汚れや傷があるか、デバイスのバイザーの位置が正しくない</span><span class="sxs-lookup"><span data-stu-id="7475f-143">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="7475f-144">眼鏡に汚れや傷がある</span><span class="sxs-lookup"><span data-stu-id="7475f-144">Dirty or scratched glasses</span></span>
- <span data-ttu-id="7475f-145">特殊なコンタクト レンズや眼鏡 (色付きのコンタクト レンズ、一部の乱視用コンタクト レンズ、赤外線カット眼鏡、一部の高処方眼鏡、サングラス、またはこれらに類似したもの) を使用している</span><span class="sxs-lookup"><span data-stu-id="7475f-145">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="7475f-146">極端な化粧や、まつげエクステンション</span><span class="sxs-lookup"><span data-stu-id="7475f-146">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="7475f-147">髪や太い眼鏡フレームにより、デバイスが見えにくくなっている</span><span class="sxs-lookup"><span data-stu-id="7475f-147">Hair or thick eyeglass frames if they are blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="7475f-148">目に関する一部の症状、状態、手術 (視野狭窄、長いまつげ、弱視、眼振、レーシックその他の眼科手術 (一部のケース) など)</span><span class="sxs-lookup"><span data-stu-id="7475f-148">Certain eye physiology, eye conditions or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="7475f-149">調整に失敗した場合は、次のことをお試しください。</span><span class="sxs-lookup"><span data-stu-id="7475f-149">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="7475f-150">デバイス バイザーのクリーニング</span><span class="sxs-lookup"><span data-stu-id="7475f-150">Cleaning your device visor</span></span>
- <span data-ttu-id="7475f-151">眼鏡のクリーニング</span><span class="sxs-lookup"><span data-stu-id="7475f-151">Cleaning your glasses</span></span>
- <span data-ttu-id="7475f-152">可能な限り目に近くなるようにデバイス バイザーを押す</span><span class="sxs-lookup"><span data-stu-id="7475f-152">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="7475f-153">バイザー内で視野を遮っているもの (髪など) を取り除く</span><span class="sxs-lookup"><span data-stu-id="7475f-153">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="7475f-154">部屋の照明を点灯するか、直接日光が当たらない場所に移動する</span><span class="sxs-lookup"><span data-stu-id="7475f-154">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="7475f-155">すべてのガイドラインに従っても調整に失敗する場合は、[設定] で調整プロンプトを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="7475f-155">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="7475f-156">[フィードバック Hub](hololens-feedback.md) からフィードバックお送りください。</span><span class="sxs-lookup"><span data-stu-id="7475f-156">Please also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="7475f-157">目の位置はシステムによって計算されるため、IPD 設定は Hololens 2 には当てはまらないことにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="7475f-157">Note that setting IPD is not applicable for Hololens 2, since eye positions are computed by the system.</span></span> 

### <span data-ttu-id="7475f-158">調整データとセキュリティ</span><span class="sxs-lookup"><span data-stu-id="7475f-158">Calibration data and security</span></span>

<span data-ttu-id="7475f-159">調整情報は、デバイスにローカル保存され、アカウント情報には関連付けられません。</span><span class="sxs-lookup"><span data-stu-id="7475f-159">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="7475f-160">調整なしでデバイスを使用したユーザーについては、記録が保存されません。</span><span class="sxs-lookup"><span data-stu-id="7475f-160">There is no record of who has used the device without calibration.</span></span> <span data-ttu-id="7475f-161">このため、デバイスを初めて使用する新しいユーザー、それまで調整を実施していないユーザー、前回の調整が失敗したユーザーは、視覚調整を行うように求められます。</span><span class="sxs-lookup"><span data-stu-id="7475f-161">This mean new users will get prompted to calibrate visuals when they use the device for the first time, as well as users who opted out of calibration previously or if calibration was unsuccessful.</span></span>

<span data-ttu-id="7475f-162">デバイスは、最大 50 個の調整プロファイルをローカルに保存できます。</span><span class="sxs-lookup"><span data-stu-id="7475f-162">The device can locally store up to 50 calibration profiles.</span></span> <span data-ttu-id="7475f-163">この数値に達すると、デバイスが最も古い使用されていないプロファイルを自動的に削除します。</span><span class="sxs-lookup"><span data-stu-id="7475f-163">After this number is reached, the device automatically deletes the oldest unused profile.</span></span>

<span data-ttu-id="7475f-164">調整情報は、**[設定]** > **[プライバシー]** > **[アイ トラッカー]** で、いつでもデバイスから削除できます。</span><span class="sxs-lookup"><span data-stu-id="7475f-164">Calibration information can always be deleted from the device in **Settings** > **Privacy** > **Eye tracker**.</span></span>  

### <span data-ttu-id="7475f-165">調整を無効にする</span><span class="sxs-lookup"><span data-stu-id="7475f-165">Disable calibration</span></span>

<span data-ttu-id="7475f-166">調整プロンプトは、以下の手順に従って無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7475f-166">You can also disable the calibration prompt by following these steps:</span></span>

1. <span data-ttu-id="7475f-167">**[設定]** > **[システム]** > **[調整]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7475f-167">Select **Settings** > **System** > **Calibration**.</span></span>
1. <span data-ttu-id="7475f-168">**[When a new person uses this HoloLens, automatically ask to run eye calibration]** (HoloLens を使用する新しいユーザーには、目に合わせた調整の実行を自動的に求める) をオフにします。</span><span class="sxs-lookup"><span data-stu-id="7475f-168">Turn off **When a new person uses this HoloLens, automatically ask to run eye calibration**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7475f-169">この設定では、ホログラムのレンダリング品質と快適さが低下することがあります。</span><span class="sxs-lookup"><span data-stu-id="7475f-169">This setting may adversely affect hologram rendering quality and comfort.</span></span>  <span data-ttu-id="7475f-170">この設定をオフにすると、視線追跡に依存する機能 (テキストのスクロールなど) がイマーシブ アプリケーションで動作しなくなります。</span><span class="sxs-lookup"><span data-stu-id="7475f-170">When you turn off this setting, features that depend on eye tracking (such as text scrolling) no longer work in immersive applications.</span></span>

### <span data-ttu-id="7475f-171">HoloLens 2 の視線追跡テクノロジ</span><span class="sxs-lookup"><span data-stu-id="7475f-171">HoloLens 2 eye-tracking technology</span></span>

<span data-ttu-id="7475f-172">このデバイスでは、表示品質を向上し、すべてのホログラムを正確に配置して、快適な 3D ビューを表示できるように、独自の視線追跡テクノロジが使用されています。</span><span class="sxs-lookup"><span data-stu-id="7475f-172">The device uses its eye-tracking technology to improve display quality, and to ensure that all holograms are positioned accurately and comfortable to view in 3D.</span></span> <span data-ttu-id="7475f-173">ランドマークとして目が使用されるため、個々のユーザーに対してデバイスを調整できます。使用中にヘッドセットが多少ずれても視覚効果が調整されます。</span><span class="sxs-lookup"><span data-stu-id="7475f-173">Because it uses the eyes as landmarks, the device can adjust itself for every user and tune its visuals as the headset shifts slightly throughout use.</span></span>  <span data-ttu-id="7475f-174">調整はすべて、手動での調整を必要とせず、使用中に行われます。</span><span class="sxs-lookup"><span data-stu-id="7475f-174">All adjustments happen on the fly without a need for manual tuning.</span></span>
> [!NOTE]
> <span data-ttu-id="7475f-175">目の位置はシステムによって計算されるため、IPD 設定は Hololens 2 には当てはまりません。</span><span class="sxs-lookup"><span data-stu-id="7475f-175">Setting the IPD is not applicable for Hololens 2, since eye positions are computed by the system.</span></span>

<span data-ttu-id="7475f-176">HoloLens アプリケーションでは、ユーザーが見ている場所をリアルタイムで追跡するために、視線追跡が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7475f-176">HoloLens applications use eye tracking to track where you are looking in real time.</span></span> <span data-ttu-id="7475f-177">開発者は、この主要機能を利用して、ホログラフィック エクスペリエンス内でまったく新しいレベルのコンテキスト、人間の認識、対話を実現できます。</span><span class="sxs-lookup"><span data-stu-id="7475f-177">This is the main capability developers can leverage to enable a whole new level of context, human understanding and interactions within the Holographic experience.</span></span> <span data-ttu-id="7475f-178">開発者は、特別な作業を何もすることなく、この機能を活用できます。</span><span class="sxs-lookup"><span data-stu-id="7475f-178">Developers don’t need to do anything to leverage this capability.</span></span>

## <span data-ttu-id="7475f-179">HoloLens (第 1 世代) を調整する</span><span class="sxs-lookup"><span data-stu-id="7475f-179">Calibrating your HoloLens (1st gen)</span></span>

<span data-ttu-id="7475f-180">HoloLens (第 1 世代) では、[瞳孔間距離](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD) に従ってホログラムの表示が調整されます。</span><span class="sxs-lookup"><span data-stu-id="7475f-180">HoloLens (1st gen) adjusts hologram display according to the your [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD).</span></span> <span data-ttu-id="7475f-181">IPD が正確でない場合は、ホログラムが不安定になったり、正しくない距離感で表示されます。</span><span class="sxs-lookup"><span data-stu-id="7475f-181">If the IPD is not accurate, holograms may appear unstable or at an incorrect distance.</span></span> <span data-ttu-id="7475f-182">瞳孔間距離 (IPD: interpupillary distance) に合わせてデバイスを調整することで、視覚効果の品質を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="7475f-182">You can improve the quality of your visuals by calibrating the device to your interpupillary distance (IPD).</span></span>

<span data-ttu-id="7475f-183">Hololens (第 1 世代) デバイスをセットアップする際には、Cortana の紹介後、視覚調整を行うように求められます。</span><span class="sxs-lookup"><span data-stu-id="7475f-183">When you set up your Hololens (1st gen) device, it prompts to calibrate your visuals after Cortana introduces herself.</span></span> <span data-ttu-id="7475f-184">調整手順は、このセットアップ フェーズで完了することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7475f-184">It's recommended that you complete the calibration step during this setup phase.</span></span> <span data-ttu-id="7475f-185">ただし、Cortana からのプロンプトを待って「Skip」 (スキップ) と言うことで、スキップすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7475f-185">However you can skip it by waiting until Cortana prompts you and then saying "Skip."</span></span>

<span data-ttu-id="7475f-186">HoloLens の調整プロセスでは、片目ごとに 6 つのターゲットに指を合わせるように求められます。</span><span class="sxs-lookup"><span data-stu-id="7475f-186">During the calibration process, HoloLens asks you to align your finger with a series of six targets per eye.</span></span> <span data-ttu-id="7475f-187">HoloLens はこのプロセスを使用し、ユーザーの目に合わせて正しく IPD を設定します。</span><span class="sxs-lookup"><span data-stu-id="7475f-187">HoloLens uses this process to set the IPD correctly for your eyes.</span></span>

![IPD の指合わせ画面 (2 番目の手順)](./images/ipd-finger-alignment-300px.jpg)

### <span data-ttu-id="7475f-189">調整プロセスを手動で開始する</span><span class="sxs-lookup"><span data-stu-id="7475f-189">Manually start the calibration process</span></span>

<span data-ttu-id="7475f-190">調整を更新する必要がある場合や、新しいユーザーの調整を行う必要がある場合は、いつでも手動で調整アプリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7475f-190">If you need to update the calibration or if a new user needs to adjust it, you can manually run the Calibration app at any time.</span></span> <span data-ttu-id="7475f-191">調整アプリは、既定でインストールされています。</span><span class="sxs-lookup"><span data-stu-id="7475f-191">The Calibration app is installed by default.</span></span> <span data-ttu-id="7475f-192">このアプリには、**スタート** メニューまたは設定アプリを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7475f-192">You can access it by using eihter the **Start** menu or the Settings app.</span></span>

<span data-ttu-id="7475f-193">**スタート** メニューを使用して調整アプリを実行するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7475f-193">To use the **Start** menu to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="7475f-194">[ブルーム](hololens1-basic-usage.md) ジェスチャを使用して、**スタート** メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="7475f-194">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="7475f-195">すべてのアプリを表示するには、**[+]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7475f-195">To view all apps, select **+**.</span></span>
1. <span data-ttu-id="7475f-196">**[調整]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7475f-196">Select **Calibration**.</span></span>

![シェルから調整アプリへのアクセス](./images/calibration-shell.png)

![起動後にライブ キューブとして表示された調整アプリ](./images/calibration-livecube-200px.png)

<span data-ttu-id="7475f-199">設定アプリを使用して調整アプリを実行するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7475f-199">To use the Settings app to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="7475f-200">[ブルーム](hololens1-basic-usage.md) ジェスチャを使用して、**スタート** メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="7475f-200">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="7475f-201">**[設定]** が **[スタート]** にピン留めされていない場合は、**[+]** を選択してすべてのアプリを表示します。</span><span class="sxs-lookup"><span data-stu-id="7475f-201">If **Settings** isn't pinned to **Start**, select **+** to view all apps.</span></span>
1. <span data-ttu-id="7475f-202">**[設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7475f-202">Select **Settings**.</span></span>
1. <span data-ttu-id="7475f-203">**[システム]** > **[ユーティリティ]** > **[調整を開く]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7475f-203">Select **System** > **Utilities** > **Open Calibration**.</span></span>

![設定アプリからの調整アプリの起動](./images/calibration-settings-500px.jpg)

## <span data-ttu-id="7475f-205">イマーシブ ヘッドセット</span><span class="sxs-lookup"><span data-stu-id="7475f-205">Immersive headsets</span></span>

<span data-ttu-id="7475f-206">一部のイマーシブ ヘッドセットには、IPD 設定をカスタマイズする機能が装備されています。</span><span class="sxs-lookup"><span data-stu-id="7475f-206">Some immersive headsets provide the ability to customize the IPD setting.</span></span> <span data-ttu-id="7475f-207">ヘッドセットの IPD を変更するには、設定アプリを開き、**[Mixed Reality]** > **[ヘッドセット ディスプレイ]** の順に選択して、スライダー コントロールを動かします。</span><span class="sxs-lookup"><span data-stu-id="7475f-207">To change the IPD for your headset, open the Settings app and select **Mixed reality** > **Headset display**, and then move the slider control.</span></span> <span data-ttu-id="7475f-208">変更は、ヘッドセットにリアルタイムで反映されます。</span><span class="sxs-lookup"><span data-stu-id="7475f-208">You’ll see the changes in real time in your headset.</span></span> <span data-ttu-id="7475f-209">眼科検査などで IPD がわかっている場合は、直接入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="7475f-209">If you know your IPD, maybe from a visit to the optometrist, you can enter it directly as well.</span></span>

<span data-ttu-id="7475f-210">この設定は、PC で調整することもできます。これには、**[設定]** > **[Mixed Reality]** > **[ヘッドセット ディスプレイ]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7475f-210">You can also adjust this setting on your PC by selecting **Settings** > **Mixed reality** > **Headset display**.</span></span>

<span data-ttu-id="7475f-211">お使いのヘッドセットで IPD のカスタマイズがサポートされていない場合、この設定は無効になります。</span><span class="sxs-lookup"><span data-stu-id="7475f-211">If your headset does not support IPD customization, this setting will be disabled.</span></span>
