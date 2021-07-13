---
title: 視覚効果と快適性の向上
description: 瞳孔間距離 (IPD) を調整して、HoloLens デバイスの視覚効果の品質を向上させる方法について説明します。
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: 調整, 快適性, 視覚効果, 品質, ipd, HoloLens, Windows Mixed Reality, VR ヘッドセット
ms.openlocfilehash: 62d83aa5c6032d15b26fbc7938859bdaf74151f4
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924147"
---
# <a name="improve-visual-quality-and-comfort"></a><span data-ttu-id="90d2b-104">視覚効果と快適性の向上</span><span class="sxs-lookup"><span data-stu-id="90d2b-104">Improve visual quality and comfort</span></span>

<span data-ttu-id="90d2b-105">HoloLens 2 と HoloLens (第 1 世代) では、ユーザーの目に合わせて調整すると性能が向上します。</span><span class="sxs-lookup"><span data-stu-id="90d2b-105">HoloLens 2 and HoloLens (1st gen) both work better when they're calibrated to your unique eyes.</span></span>

<span data-ttu-id="90d2b-106">どちらのデバイスでも、最適なホログラム表示エクスペリエンスを目的として調整する必要がある点では同じですが、使用する調整テクノロジと手法が異なります。</span><span class="sxs-lookup"><span data-stu-id="90d2b-106">While both devices need to calibrate for the best hologram viewing experience, they use different calibration technologies and techniques.</span></span>  <span data-ttu-id="90d2b-107">[HoloLens 2 調整](#calibrating-your-hololens-2)または[HoloLens (第1世代) の調整](#calibrating-your-hololens-1st-gen)に移動します。</span><span class="sxs-lookup"><span data-stu-id="90d2b-107">Jump to [HoloLens 2 calibration](#calibrating-your-hololens-2) or [HoloLens (1st gen) calibration](#calibrating-your-hololens-1st-gen).</span></span>

## <a name="calibrating-your-hololens-2"></a><span data-ttu-id="90d2b-108">HoloLens 2 の調整</span><span class="sxs-lookup"><span data-stu-id="90d2b-108">Calibrating your HoloLens 2</span></span>

<span data-ttu-id="90d2b-109">HoloLens 2 では、仮想環境の表示と操作のエクスペリエンスを向上させるために視線追跡テクノロジが使用されています。</span><span class="sxs-lookup"><span data-stu-id="90d2b-109">HoloLens 2 uses eye-tracking technology to improve your experience seeing and interacting with the virtual environment.</span></span> <span data-ttu-id="90d2b-110">HoloLens 2 を調整すると、ユーザーの視線 (およびデバイスを使用している他のユーザーの視線) を正確に追跡できるようになります。</span><span class="sxs-lookup"><span data-stu-id="90d2b-110">Calibrating the HoloLens 2 ensures that it can accurately track your eyes (and the eyes of anyone else who uses the device).</span></span> <span data-ttu-id="90d2b-111">ユーザーの安心、ホログラムの整列、ハンド トラッキングにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-111">It also helps with user comfort, hologram alignment, and hand tracking.</span></span> <span data-ttu-id="90d2b-112">調整後は、頭部に装着したバイザーの位置がずれても、ホログラムが正しく表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-112">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

<span data-ttu-id="90d2b-113">HoloLens 2 では、次のようなときに、デバイスの調整がユーザーに求められます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-113">HoloLens 2 prompts a user to calibrate the device under the following circumstances:</span></span>

- <span data-ttu-id="90d2b-114">ユーザーが初めてデバイスを使用する</span><span class="sxs-lookup"><span data-stu-id="90d2b-114">The user is using the device for the first time</span></span>
- <span data-ttu-id="90d2b-115">ユーザーが前回の調整プロセスを実施しなかった</span><span class="sxs-lookup"><span data-stu-id="90d2b-115">The user previously opted out of the calibration process</span></span>
- <span data-ttu-id="90d2b-116">ユーザーが前回デバイスを使用したときに、調整プロセスに失敗した</span><span class="sxs-lookup"><span data-stu-id="90d2b-116">The calibration process didn't succeed the last time the user used the device</span></span>
- <span data-ttu-id="90d2b-117">ユーザーが調整プロファイルを削除した</span><span class="sxs-lookup"><span data-stu-id="90d2b-117">The user has deleted their calibration profiles</span></span>
- <span data-ttu-id="90d2b-118">デバイスが取り外されて再びオンになり、上記のいずれかの状況の状況が発生する</span><span class="sxs-lookup"><span data-stu-id="90d2b-118">The device is taken off and puts back on and any of the above circumstances apply</span></span> 


![目に合わせるための調整プロンプト。](./images/07-et-adjust-for-your-eyes.png)

<span data-ttu-id="90d2b-120">このプロセスでは、一連のターゲット (ジェム) を目視します。</span><span class="sxs-lookup"><span data-stu-id="90d2b-120">During this process, you'll look at a set of targets (gems).</span></span> <span data-ttu-id="90d2b-121">調整中にまばたきしても問題はありませんが、室内の他のオブジェクトではなく宝石に集中するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="90d2b-121">It's fine if you blink during calibration, but try to stay focused on the gems instead of other objects in the room.</span></span>  <span data-ttu-id="90d2b-122">宝石に焦点を当てると、HoloLens はホログラフィックの世界をレンダリングするための目の位置を学習できます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-122">Focusing on the gems allows HoloLens to learn about your eye position to render your holographic world.</span></span>

![頭を動かさずにドットを目で追うようにユーザーに指示する調整プロンプト。](./images/07-et-hold-head-still.png)

![宝石の例を含む調整のプロンプト。](./images/08-et-gems.png)

![調整プロンプトの調整。](./images/09-et-adjusting.png)

<span data-ttu-id="90d2b-126">調整に成功すると、成功を示す画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-126">If calibration was successful, you'll see a success screen.</span></span>  <span data-ttu-id="90d2b-127">それ以外の場合は、 [調整エラーの診断](hololens2-display.md#troubleshooting)に関する詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90d2b-127">If not, read more about [diagnosing calibration failures](hololens2-display.md#troubleshooting).</span></span>

![調整プロンプトの完了。](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a><span data-ttu-id="90d2b-129">デバイスまたはセッションを共有する場合の調整</span><span class="sxs-lookup"><span data-stu-id="90d2b-129">Calibration when sharing a device or session</span></span>

<span data-ttu-id="90d2b-130">HoloLens 2 デバイスは、複数のユーザーが共有できます。各ユーザーがデバイスのセットアップを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="90d2b-130">Multiple users can share a HoloLens 2 device, without a need for each person to go through device setup.</span></span> <span data-ttu-id="90d2b-131">新しいユーザーがデバイスを初めて頭に装着する際には、HoloLens 2 によって、視覚調整をユーザーに求めるメッセージが自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-131">When a new user puts the device on their head for the first time, HoloLens 2 automatically prompts the user to calibrate visuals.</span></span> <span data-ttu-id="90d2b-132">視覚調整を実施済みのユーザーがデバイスを頭に装着すると、質の高い視覚効果と快適な表示エクスペリエンスを得られるように、ディスプレイの調整がシームレスに行われます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-132">When a user that has previously calibrated visuals puts the device on their head, the display seamlessly adjusts for quality and a comfortable viewing experience.</span></span>  

### <a name="manually-starting-the-calibration-process"></a><span data-ttu-id="90d2b-133">調整プロセスを手動で開始する</span><span class="sxs-lookup"><span data-stu-id="90d2b-133">Manually starting the calibration process</span></span>

1. <span data-ttu-id="90d2b-134">スタート ジェスチャを使用して、[ **[スタート]** メニュー](hololens2-basic-usage.md#start-gesture)を開きます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-134">Use the start gesture to open the [**Start** menu](hololens2-basic-usage.md#start-gesture).</span></span>
1. <span data-ttu-id="90d2b-135">設定アプリが **スタート** にピン留めされていない場合は、 **[すべてのアプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="90d2b-135">If the Settings app isn't pinned to **Start**, select **All Apps**.</span></span>
1. <span data-ttu-id="90d2b-136">**[設定]** を選択し、 **[システム]**  >  **[調整]**  >  **[視線の調整]**  >  **[視点の調整を実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="90d2b-136">Select **Settings**, and then select **System** > **Calibration** > **Eye Calibration** > **Run eye calibration**.</span></span>

   ![[視線の調整を実行] オプションが表示されている設定アプリ](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a><span data-ttu-id="90d2b-138">視線の自動調整サポート</span><span class="sxs-lookup"><span data-stu-id="90d2b-138">Auto Eye Position Support</span></span>

<span data-ttu-id="90d2b-139">HoloLens 2 では、視線により、正確なホログラムの位置決め、快適な表示エクスペリエンス、および表示品質の向上が可能になります。</span><span class="sxs-lookup"><span data-stu-id="90d2b-139">In HoloLens 2, eye positions enable accurate hologram positioning, comfortable viewing experience, and improved display quality.</span></span> <span data-ttu-id="90d2b-140">視線は、視線追跡計算の一部として内部的に計算されます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-140">Eye positions are computed internally as part of the eye tracking computation.</span></span> <span data-ttu-id="90d2b-141">ただし、これには、エクスペリエンスで視線の入力が必要ない場合でも、各ユーザーが視線追跡の調整を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90d2b-141">However, this requires each user to go through eye tracking calibration, even when the experience might not require eye gaze input.</span></span>

<span data-ttu-id="90d2b-142">**視線の自動調整 (AEP)** は、ユーザーの目の位置を計算するための操作のない方法でこれらのシナリオを可能にします。</span><span class="sxs-lookup"><span data-stu-id="90d2b-142">**Auto Eye Position (AEP)** enables these scenarios with an interaction-free way to compute eye positions for the user.</span></span> <span data-ttu-id="90d2b-143">視線の自動調整は、ユーザーがデバイスを装着した瞬間から自動的にバックグラウンドで動作を開始します。</span><span class="sxs-lookup"><span data-stu-id="90d2b-143">Auto Eye Position starts working in the background automatically from the moment the user puts on the device.</span></span> <span data-ttu-id="90d2b-144">ユーザーが事前に視線追跡の調整を行っていない場合、視線の自動調整は、20 から 30 秒の処理時間の後にユーザーの視線を表示システムに提供し始めます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-144">If the user doesn't have a prior eye tracking calibration, Auto Eye Position will start providing the user's eye positions to the display system after a processing time of 20 - 30 seconds.</span></span> <span data-ttu-id="90d2b-145">ユーザー データはデバイスに保持されません。ユーザーが離陸してデバイスをオンに戻した場合、またはデバイスが再起動したりスリープから復帰したりすると、このプロセスが繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-145">The user data isn't persisted on the device and this process is repeated if the user takes off and puts the device back on or if the device reboots or wakes up from sleep.</span></span>

<span data-ttu-id="90d2b-146">調整されていないユーザーがデバイスを装着した場合、視線の自動調整機能によるシステム動作の変更がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="90d2b-146">There are a few system behavior changes with Auto Eye Position feature when an uncalibrated user puts on the device.</span></span> <span data-ttu-id="90d2b-147">このコンテキストでは、調整されていないユーザーとは、以前にデバイスで視線追跡の調整プロセスを実行したことがないユーザーを指します。</span><span class="sxs-lookup"><span data-stu-id="90d2b-147">In this context, an uncalibrated user refers to someone who hasn't gone through the eye tracking calibration process on the device previously.</span></span>

| <span data-ttu-id="90d2b-148">アクティブなアプリケーション</span><span class="sxs-lookup"><span data-stu-id="90d2b-148">Active Application</span></span> | <span data-ttu-id="90d2b-149">以前の動作</span><span class="sxs-lookup"><span data-stu-id="90d2b-149">Prior Behavior</span></span> | <span data-ttu-id="90d2b-150">Windows Holographic、バージョン 20H2 アップデートからの動作</span><span class="sxs-lookup"><span data-stu-id="90d2b-150">Behavior from Windows Holographic, version 20H2 Update</span></span> |
|:-------------------|:-----------------|:-----------------------------------|
| <span data-ttu-id="90d2b-151">非視線対応アプリまたはホログラフィック シェル</span><span class="sxs-lookup"><span data-stu-id="90d2b-151">Non-gaze enabled app or Holographic Shell</span></span> |<span data-ttu-id="90d2b-152">視線追跡の調整プロンプト ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-152">Eye tracking calibration prompt dialog is displayed.</span></span> | <span data-ttu-id="90d2b-153">プロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="90d2b-153">No prompt is displayed.</span></span> |
| <span data-ttu-id="90d2b-154">視線対応アプリ</span><span class="sxs-lookup"><span data-stu-id="90d2b-154">Gaze enabled app</span></span> | <span data-ttu-id="90d2b-155">視線追跡の調整プロンプト ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-155">Eye tracking calibration prompt dialog is displayed.</span></span> | <span data-ttu-id="90d2b-156">視線追跡の調整プロンプトは、アプリケーションが視線ストリームにアクセスした場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-156">Eye tracking calibration prompt is displayed only when the application accesses eye gaze stream.</span></span> |

<span data-ttu-id="90d2b-157">ユーザーが非視線対応アプリケーションから視線データにアクセスするアプリケーションに移行すると、調整プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-157">If the user transitions from a non-gaze enabled application to one that accesses the gaze data, the calibration prompt will be displayed.</span></span> 

<span data-ttu-id="90d2b-158">他のすべてのシステム動作は、現在のユーザーがアクティブな視線追跡の調整を持っていない場合と同様になります。</span><span class="sxs-lookup"><span data-stu-id="90d2b-158">All other system behavior will be similar to when the current user doesn't have an active eye tracking calibration.</span></span> <span data-ttu-id="90d2b-159">たとえば、片手のスタート ジェスチャは有効になりません。</span><span class="sxs-lookup"><span data-stu-id="90d2b-159">For example, the One-handed Start gesture won't be enabled.</span></span> <span data-ttu-id="90d2b-160">初期設定の既定のエクスペリエンスに変更はありません。</span><span class="sxs-lookup"><span data-stu-id="90d2b-160">There will be no change to the Out-Of-Box-Experience for initial setup.</span></span>

<span data-ttu-id="90d2b-161">視線データまたは正確なホログラムの位置合わせが必要なエクスペリエンスの場合は、調整されていないユーザーに視線追跡の調整を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="90d2b-161">For experiences that require eye gaze data or precise hologram positioning, we recommend uncalibrated users to run eye tracking calibration.</span></span> <span data-ttu-id="90d2b-162">視線追跡調整 プロンプトから、またはスタート メニューから設定アプリを起動し、 **[システム] > [調整] > [視線の調整] > [視線の調整を実行]** の順に選択してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-162">It's accessible from the eye tracking calibration prompt or by launching the Settings app from the start menu, and then selecting **System > Calibration > Eye Calibration > Run eye calibration**.</span></span>

#### <a name="deferred-calibration-prompt"></a><span data-ttu-id="90d2b-163">遅延調整プロンプト</span><span class="sxs-lookup"><span data-stu-id="90d2b-163">Deferred Calibration Prompt</span></span>

<span data-ttu-id="90d2b-164">視線の自動調整では、アプリケーションが視線データを要求するまで、視線追跡調整プロンプト ダイアログが遅延されます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-164">With Auto Eye Position, the Eye Tracking Calibration prompt dialog is deferred until an application requests Eye Gaze data.</span></span> <span data-ttu-id="90d2b-165">これにより、アクティブなアプリケーションが視線を必要としない場合に、ユーザーにプロンプトが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="90d2b-165">This ensures that there's no prompt to the user when the active application doesn't require gaze.</span></span> <span data-ttu-id="90d2b-166">アプリケーションが視線データを必要とし、現在のユーザーのために調整されていない場合、そのユーザーには調整プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-166">If the application does require gaze data and the current user isn't calibrated, the user is presented with a calibration prompt.</span></span> <span data-ttu-id="90d2b-167">この動作を使用して、エクスペリエンスに適した時間に視線追跡調整プロンプトを表示できます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-167">This behavior could be used to display eye tracking calibration prompt at a suitable time for the experience.</span></span> <span data-ttu-id="90d2b-168">この方法は、次の理由で推奨されます</span><span class="sxs-lookup"><span data-stu-id="90d2b-168">This method is recommended for the following reasons</span></span>

1.  <span data-ttu-id="90d2b-169">視線追跡調整プロンプトのダイアログには、視線の追跡が必要な理由についての詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-169">The Eye Tracking Calibration Prompt dialog provides the user with details on why eye tracking is needed.</span></span>
2.  <span data-ttu-id="90d2b-170">ユーザーに、視線の調整を拒否する方法を提示します。</span><span class="sxs-lookup"><span data-stu-id="90d2b-170">Presents the user a way to decline to have their eyes calibrated.</span></span>

<span data-ttu-id="90d2b-171">ユーザーが [視線追跡の調整] を選択すると、調整が完了した後で、フォーカスが元のアプリケーションに戻る必要があります。</span><span class="sxs-lookup"><span data-stu-id="90d2b-171">If the user chooses to launch the Eye Tracking Calibration, the focus should returning to the original application after calibration completes.</span></span> 

### <a name="calibration-data-and-security"></a><span data-ttu-id="90d2b-172">調整データとセキュリティ</span><span class="sxs-lookup"><span data-stu-id="90d2b-172">Calibration data and security</span></span>

<span data-ttu-id="90d2b-173">調整情報は、デバイスにローカル保存され、アカウント情報には関連付けられません。</span><span class="sxs-lookup"><span data-stu-id="90d2b-173">Calibration information is stored locally on the device and isn't associated with any account information.</span></span> <span data-ttu-id="90d2b-174">調整なしでデバイスを使用したユーザーについては、記録が保存されません。</span><span class="sxs-lookup"><span data-stu-id="90d2b-174">There's no record of who has used the device without calibration.</span></span> <span data-ttu-id="90d2b-175">このため、デバイスを初めて使用する新しいユーザー、それまで調整を実施していないユーザー、前回の調整が失敗したユーザーは、視覚調整を行うように求められます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-175">This mean new users will get prompted to calibrate visuals when they use the device for the first time, and users who opted out of calibration previously or if calibration was unsuccessful.</span></span>

<span data-ttu-id="90d2b-176">デバイスは、最大 50 個の調整プロファイルをローカルに保存できます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-176">The device can locally store up to 50 calibration profiles.</span></span> <span data-ttu-id="90d2b-177">この数値に達すると、最も古く使用されていないプロファイルが自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-177">After this number is reached, the device automatically deletes the oldest unused profile.</span></span>

<span data-ttu-id="90d2b-178">調整情報は、 **[設定]**  >  **[プライバシー]**  >  **[視線トラッカー]** でデバイスからいつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-178">Calibration information can always be deleted from the device in **Settings** > **Privacy** > **Eye tracker**.</span></span>  

### <a name="disable-calibration"></a><span data-ttu-id="90d2b-179">調整を無効にする</span><span class="sxs-lookup"><span data-stu-id="90d2b-179">Disable calibration</span></span>

<span data-ttu-id="90d2b-180">調整プロンプトは、以下の手順に従って無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-180">You can also disable the calibration prompt by following these steps:</span></span>

1. <span data-ttu-id="90d2b-181">**[設定]**  >  **[システム]**  >  **[調整]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="90d2b-181">Select **Settings** > **System** > **Calibration**.</span></span>
1. <span data-ttu-id="90d2b-182">**新しいユーザーがこの HoloLens を使用したときに、自動的に [視線の調整を実行]** をオフにします。</span><span class="sxs-lookup"><span data-stu-id="90d2b-182">Turn off **When a new person uses this HoloLens, automatically ask to run eye calibration**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90d2b-183">この設定では、ホログラムのレンダリング品質と快適さが低下することがあります。</span><span class="sxs-lookup"><span data-stu-id="90d2b-183">This setting may adversely affect hologram rendering quality and comfort.</span></span>  <span data-ttu-id="90d2b-184">この設定をオフにすると、視線追跡に依存する機能 (テキストのスクロールなど) がイマーシブ アプリケーションで動作しなくなります。</span><span class="sxs-lookup"><span data-stu-id="90d2b-184">When you turn off this setting, features that depend on eye tracking (such as text scrolling) no longer work in immersive applications.</span></span>

### <a name="hololens-2-eye-tracking-technology"></a><span data-ttu-id="90d2b-185">HoloLens 2 の視線追跡テクノロジ</span><span class="sxs-lookup"><span data-stu-id="90d2b-185">HoloLens 2 eye-tracking technology</span></span>

<span data-ttu-id="90d2b-186">このデバイスでは、表示品質を向上し、すべてのホログラムを正確に配置して、快適な 3D ビューを表示できるように、独自の視線追跡テクノロジが使用されています。</span><span class="sxs-lookup"><span data-stu-id="90d2b-186">The device uses its eye-tracking technology to improve display quality, and to ensure that all holograms are positioned accurately and comfortable to view in 3D.</span></span> <span data-ttu-id="90d2b-187">ランドマークとして目が使用されるため、個々のユーザーに対してデバイスを調整できます。使用中にヘッドセットが多少ずれても視覚効果が調整されます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-187">Because it uses the eyes as landmarks, the device can adjust itself for every user and tune its visuals as the headset shifts slightly throughout use.</span></span>  <span data-ttu-id="90d2b-188">調整はすべて、手動での調整を必要とせず、使用中に行われます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-188">All adjustments happen on the fly without a need for manual tuning.</span></span>
> [!NOTE]
> <span data-ttu-id="90d2b-189">目の位置はシステムによって計算されるため、IPD 設定は HoloLens 2 には当てはまりません。</span><span class="sxs-lookup"><span data-stu-id="90d2b-189">Setting the IPD is not applicable for Hololens 2, since eye positions are computed by the system.</span></span>

<span data-ttu-id="90d2b-190">HoloLens アプリケーションでは、ユーザーが見ている場所をリアルタイムで追跡するために、視線追跡が使用されます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-190">HoloLens applications use eye tracking to track where you're looking in real time.</span></span> <span data-ttu-id="90d2b-191">開発者は、この主要機能を使用して、ホログラフィック エクスペリエンス内でまったく新しいレベルのコンテキスト、人間の認識、対話を実現できます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-191">This is the main capability developers can use to enable a whole new level of context, human understanding, and interactions within the Holographic experience.</span></span> <span data-ttu-id="90d2b-192">開発者は、特別な作業を何もすることなく、この機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-192">Developers don’t need to do anything to use this capability.</span></span>

## <a name="calibrating-your-hololens-1st-gen"></a><span data-ttu-id="90d2b-193">HoloLens (第 1 世代) を調整する</span><span class="sxs-lookup"><span data-stu-id="90d2b-193">Calibrating your HoloLens (1st gen)</span></span>

<span data-ttu-id="90d2b-194">HoloLens (第1世代) は、 [i瞳孔間距離](https://en.wikipedia.org/wiki/Interpupillary_distance)(IPD) に従ってホログラムの表示を調整します。</span><span class="sxs-lookup"><span data-stu-id="90d2b-194">HoloLens (1st gen) adjusts hologram display according to your [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD).</span></span> <span data-ttu-id="90d2b-195">IPD が正確でない場合は、ホログラムが不安定になったり、正しくない距離感で表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-195">If the IPD isn't accurate, holograms may appear unstable or at an incorrect distance.</span></span> <span data-ttu-id="90d2b-196">瞳孔間距離 (IPD) に合わせてデバイスを調整することで、視覚効果の品質を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-196">You can improve the quality of your visuals by calibrating the device to your interpupillary distance (IPD).</span></span>

<span data-ttu-id="90d2b-197">HoloLens (第 1 世代) デバイスをセットアップする際には、Cortana の紹介後、視覚調整を行うように求められます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-197">When you set up your HoloLens (1st gen) device, it prompts to calibrate your visuals after Cortana introduces herself.</span></span> <span data-ttu-id="90d2b-198">調整手順は、このセットアップ フェーズで完了することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="90d2b-198">It's recommended that you complete the calibration step during this setup phase.</span></span> <span data-ttu-id="90d2b-199">ただし、Cortana からのプロンプトを待って「スキップ」 と言うことで、スキップすることもできます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-199">However you can skip it by waiting until Cortana prompts you and then saying "Skip."</span></span>

<span data-ttu-id="90d2b-200">HoloLens の調整プロセスでは、片目ごとに 6 つのターゲットに指を合わせるように求められます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-200">During the calibration process, HoloLens asks you to align your finger with a series of six targets per eye.</span></span> <span data-ttu-id="90d2b-201">HoloLens はこのプロセスを使用し、ユーザーの目に合わせて正しく IPD を設定します。</span><span class="sxs-lookup"><span data-stu-id="90d2b-201">HoloLens uses this process to set the IPD correctly for your eyes.</span></span>

![IPD の指合わせ画面 (2 番目の手順)](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a><span data-ttu-id="90d2b-203">調整プロセスを手動で開始する</span><span class="sxs-lookup"><span data-stu-id="90d2b-203">Manually start the calibration process</span></span>

<span data-ttu-id="90d2b-204">調整を更新する必要がある場合や、新しいユーザーの調整を行う必要がある場合は、いつでも手動で調整アプリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-204">If you need to update the calibration or if a new user needs to adjust it, you can manually run the Calibration app at any time.</span></span> <span data-ttu-id="90d2b-205">調整アプリは、既定でインストールされています。</span><span class="sxs-lookup"><span data-stu-id="90d2b-205">The Calibration app is installed by default.</span></span> <span data-ttu-id="90d2b-206">このアプリには、 **[スタート]** メニューまたは設定アプリを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-206">You can access it by using either the **Start** menu or the Settings app.</span></span>

<span data-ttu-id="90d2b-207">**[スタート]** メニューを使用して調整アプリを実行するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="90d2b-207">To use the **Start** menu to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="90d2b-208">[ブルーム](hololens1-basic-usage.md)ジェスチャを使用して、 **[スタート]** メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-208">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="90d2b-209">すべてのアプリを表示するには、 **+** を選択します。</span><span class="sxs-lookup"><span data-stu-id="90d2b-209">To view all apps, select **+**.</span></span>
1. <span data-ttu-id="90d2b-210">**[調整]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="90d2b-210">Select **Calibration**.</span></span>

![シェルから調整アプリへのアクセス](./images/calibration-shell.png)

![起動後にライブ キューブとして表示された調整アプリ](./images/calibration-livecube-200px.png)

<span data-ttu-id="90d2b-213">設定アプリを使用して調整アプリを実行するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="90d2b-213">To use the Settings app to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="90d2b-214">[ブルーム](hololens1-basic-usage.md)ジェスチャを使用して、 **[スタート]** メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-214">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="90d2b-215">**[設定]** が **[スタート]** にピン留めされていない場合、 **+** を選択 してすべてのアプリを表示します。</span><span class="sxs-lookup"><span data-stu-id="90d2b-215">If **Settings** isn't pinned to **Start**, select **+** to view all apps.</span></span>
1. <span data-ttu-id="90d2b-216">**[設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="90d2b-216">Select **Settings**.</span></span>
1. <span data-ttu-id="90d2b-217">**[システム]**  >  **[ユーティリティ]**  >  **[調整を開く]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="90d2b-217">Select **System** > **Utilities** > **Open Calibration**.</span></span>

![設定アプリからお調整アプリの起動](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a><span data-ttu-id="90d2b-219">イマーシブ ヘッドセット</span><span class="sxs-lookup"><span data-stu-id="90d2b-219">Immersive headsets</span></span>

<span data-ttu-id="90d2b-220">一部のイマーシブ ヘッドセットには、IPD 設定をカスタマイズする機能が装備されています。</span><span class="sxs-lookup"><span data-stu-id="90d2b-220">Some immersive headsets provide the ability to customize the IPD setting.</span></span> <span data-ttu-id="90d2b-221">ヘッドセットの IPD を変更するには、設定 アプリを開き、 **[Mixed Reality]**  >  **[ヘッドセットの表示]** を選択し、スライダー コントロール を移動します。</span><span class="sxs-lookup"><span data-stu-id="90d2b-221">To change the IPD for your headset, open the Settings app and select **Mixed reality** > **Headset display**, and then move the slider control.</span></span> <span data-ttu-id="90d2b-222">変更は、ヘッドセットにリアルタイムで反映されます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-222">You’ll see the changes in real time in your headset.</span></span> <span data-ttu-id="90d2b-223">眼科検査などで IPD がわかっている場合は、直接入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-223">If you know your IPD, maybe from a visit to the optometrist, you can enter it directly as well.</span></span>

<span data-ttu-id="90d2b-224">**[設定]**  >  **[Mixed Reality]**  >  **[ヘッドセットの表示]** を選択して、PC 設定を調整できます。</span><span class="sxs-lookup"><span data-stu-id="90d2b-224">You can also adjust this setting on your PC by selecting **Settings** > **Mixed reality** > **Headset display**.</span></span>

<span data-ttu-id="90d2b-225">お使いのヘッドセットで IPD のカスタマイズがサポートされていない場合、この設定は無効になります。</span><span class="sxs-lookup"><span data-stu-id="90d2b-225">If your headset doesn't support IPD customization, this setting will be disabled.</span></span>
