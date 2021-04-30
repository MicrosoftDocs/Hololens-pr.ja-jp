---
title: トラブルシューティング
description: HoloLens デバイスの問題とトラブルシューティング手法に関する最も一般的な解決策については、最新情報を入手してください。
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: 懸案事項, バグ, トラブルシューティング, 修正, ヘルプ, サポート, HoloLens
ms.openlocfilehash: f57aea52337f7ca7e15bda1363f73a3a7265a025
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309516"
---
# <a name="troubleshooting"></a><span data-ttu-id="f83dc-104">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f83dc-104">Troubleshooting</span></span>

<span data-ttu-id="f83dc-105">この記事では、いくつかの一般的な HoloLens の問題を解決する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-105">This article describes how to resolve several common HoloLens issues.</span></span>

## <a name="my-hololens-is-unresponsive-or-wont-start"></a><span data-ttu-id="f83dc-106">HoloLens が応答していないか、起動しない</span><span class="sxs-lookup"><span data-stu-id="f83dc-106">My HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="f83dc-107">HoloLens が開始されない場合:</span><span class="sxs-lookup"><span data-stu-id="f83dc-107">If your HoloLens won't start:</span></span>

- <span data-ttu-id="f83dc-108">電源ボタンの横にある Led が点灯していない場合、または1つの LED だけが少し点滅している場合は、 [HoloLens の料金を支払う](hololens-recovery.md#charge-the-device)必要があります。</span><span class="sxs-lookup"><span data-stu-id="f83dc-108">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens-recovery.md#charge-the-device)</span></span>
- <span data-ttu-id="f83dc-109">電源ボタンを押したときに Led が点灯しても、ディスプレイに何も表示されない場合は、 [検査によってデバイスのハードリセットが](hololens-recovery.md#hard-reset-procedure)発生します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-109">If the LEDs light up when you press the power button but you can't see anything on the displays, [preform a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="f83dc-110">HoloLens がフリーズまたは応答しなくなった場合:</span><span class="sxs-lookup"><span data-stu-id="f83dc-110">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="f83dc-111">5つの Led がすべてオフになるまで電源ボタンを押すか、Led が応答していない場合は15秒間、HoloLens をオフにします。</span><span class="sxs-lookup"><span data-stu-id="f83dc-111">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="f83dc-112">HoloLens を開始するには、もう一度 [電源] ボタンを押します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-112">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="f83dc-113">これらの手順がうまくいかない場合は、 [hololens 2 デバイス](hololens-recovery.md)または[hololens (第1世代) デバイス](hololens1-recovery.md)の復旧を試すことができます。</span><span class="sxs-lookup"><span data-stu-id="f83dc-113">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

## <a name="holograms-dont-look-good"></a><span data-ttu-id="f83dc-114">ホログラムが正しく表示されない</span><span class="sxs-lookup"><span data-stu-id="f83dc-114">Holograms don't look good</span></span>

<span data-ttu-id="f83dc-115">ホログラムが不安定な場合、過敏ていない場合、または正しく表示されない場合は、次を試してください。</span><span class="sxs-lookup"><span data-stu-id="f83dc-115">If your holograms are unstable, jumpy, or don't look right, try:</span></span>

- <span data-ttu-id="f83dc-116">HoloLens の前面にあるデバイスのバイザーとセンサーバーをクリーニングします。</span><span class="sxs-lookup"><span data-stu-id="f83dc-116">Cleaning your device visor and sensor bar on the front of your HoloLens.</span></span>
- <span data-ttu-id="f83dc-117">部屋の光を増やします。</span><span class="sxs-lookup"><span data-stu-id="f83dc-117">Increasing the light in your room.</span></span>
- <span data-ttu-id="f83dc-118">お客様の環境を調べて、HoloLens がより完全にスキャンできるようにします。</span><span class="sxs-lookup"><span data-stu-id="f83dc-118">Walking around and looking at your surroundings so that HoloLens can scan them more completely.</span></span>
- <span data-ttu-id="f83dc-119">お客様の HoloLens を調整します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-119">Calibrating your HoloLens for your eyes.</span></span> <span data-ttu-id="f83dc-120">[**設定**] [システムユーティリティ] にアクセス  >    >  します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-120">Go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="f83dc-121">[ **調整**] で [ **調整を開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-121">Under **Calibration**, select **Open Calibration**.</span></span>
 
### <a name="reporting-issues-where-holograms-are-unstable-or-dont-look-right"></a><span data-ttu-id="f83dc-122">ホログラムが不安定であるか、または正しくない問題を報告しています</span><span class="sxs-lookup"><span data-stu-id="f83dc-122">Reporting issues where Holograms are unstable or don't look right</span></span>
 
1. <span data-ttu-id="f83dc-123">問題のビデオを記録し、 [Mixed Reality をキャプチャ](holographic-photos-and-videos.md#capture-a-mixed-reality-video) してください。</span><span class="sxs-lookup"><span data-stu-id="f83dc-123">Please record and a [Mixed Reality Capture video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) of the issue.</span></span> <span data-ttu-id="f83dc-124">このビデオは、後でフィードバックハブを使用して添付ファイルとしてアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="f83dc-124">This video can be later uploaded through Feedback Hub as an attached file.</span></span>  
1. <span data-ttu-id="f83dc-125">**設定** アプリを使用して完全なテレメトリを有効にする->**プライバシー**  ->  **診断 & のフィードバック** と、**オプションの診断データ** で、トグルが **On** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-125">Enable full telemetry via the **Settings** app -> **Privacy** -> **Diagnostics & feedback** and under **Optional diagnostics data** ensure the toggle is set to **On**</span></span>
1. <span data-ttu-id="f83dc-126">最新の [Windows HOLOGRAPHIC OS (20H2 以降)](hololens-release-notes.md#windows-holographic-version-20h2)に更新して、最新のホログラムスケールと安定性の修正を取得します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-126">Get the latest hologram scale and stability fixes by updating to the latest [Windows Holographic OS, (20H2 or higher)](hololens-release-notes.md#windows-holographic-version-20h2).</span></span> <span data-ttu-id="f83dc-127">更新後、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-127">After updating perform the following:</span></span>
    1. <span data-ttu-id="f83dc-128">**設定** アプリを使用してすべてのホログラムを削除する->**システム**  ->  **ホログラム**-> [**すべてのホログラムを削除** し、新しいマップで開始する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-128">Remove all Holograms via **Settings** app -> **System** -> **Holograms** -> then select **Remove all holograms** and start with a fresh map.</span></span>
    1. <span data-ttu-id="f83dc-129">HoloLens を装着して部屋に移動し、空間内のすべての領域とサーフェイスを確認することで、スペースの新しいマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-129">Create a new map of your space by wearing the HoloLens and walking around your room and looking at all areas and surfaces in the space.</span></span> <span data-ttu-id="f83dc-130">これは、2-3 分間実行します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-130">Do this for 2-3 minutes.</span></span>
    1. <span data-ttu-id="f83dc-131">IPD の調整を実行します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-131">Perform IPD calibration.</span></span> <span data-ttu-id="f83dc-132">[**設定**] [システムユーティリティ] にアクセス  >    >  します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-132">Go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="f83dc-133">[ **調整**] で [ **調整を開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-133">Under **Calibration**, select **Open Calibration**.</span></span>
    1. <span data-ttu-id="f83dc-134">シナリオを再テストし、まだ永続化されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-134">Re-test the scenario and see if it still persists.</span></span>
1. <span data-ttu-id="f83dc-135">更新によって問題が解決されない場合は、 [フィードバックハブの問題](hololens-feedback.md)を報告してください。</span><span class="sxs-lookup"><span data-stu-id="f83dc-135">If updating does not fix the issue, please file a [Feedback Hub issue](hololens-feedback.md).</span></span> <span data-ttu-id="f83dc-136">フィードバックを入力したら、[ **共有** ] ボタンを使用して、サポートに連絡するときに送信できる、共有の簡単なリンクを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f83dc-136">After you've filled feedback you can use the **Share** button, to create an easy to share link that can be sent when contacting support.</span></span>

## <a name="hololens-doesnt-respond-to-hand-input"></a><span data-ttu-id="f83dc-137">HoloLens が手入力に応答しない</span><span class="sxs-lookup"><span data-stu-id="f83dc-137">HoloLens doesn't respond to hand input</span></span>

<span data-ttu-id="f83dc-138">HoloLens が自分の手を見えるようにするには、それらをジェスチャフレームに保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f83dc-138">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="f83dc-139">Mixed Reality ホームでは、自分がどのように追跡されるかを知ることができるフィードバックが提供されます。</span><span class="sxs-lookup"><span data-stu-id="f83dc-139">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="f83dc-140">このフィードバックは、HoloLens のバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f83dc-140">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="f83dc-141">HoloLens (第1世代) では、宝石カーソルがドットからリングに変わります。</span><span class="sxs-lookup"><span data-stu-id="f83dc-141">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="f83dc-142">HoloLens 2 では、指先カーソルは、手がスレートの近くにあるときに表示され、スレートがさらに離れたときにハンドレイが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f83dc-142">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="f83dc-143">多くのイマーシブアプリは、Mixed Reality ホームに似た入力パターンに従います。</span><span class="sxs-lookup"><span data-stu-id="f83dc-143">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="f83dc-144">[Hololens (第1世代)](hololens1-basic-usage.md#use-hololens-with-your-hands)と[hololens 2](hololens2-basic-usage.md#the-hand-tracking-frame)で手書き入力を使用する方法の詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f83dc-144">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="f83dc-145">手袋を装着している場合は、一部の種類の手袋がハンドトラッキングで動作しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f83dc-145">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="f83dc-146">一般的な例としては、赤外線信号を吸収する傾向があり、深度カメラでは選択されていない黒色のゴムグローブがあります。</span><span class="sxs-lookup"><span data-stu-id="f83dc-146">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="f83dc-147">ゴムグローブが使用されている場合は、青や灰色などの明るい色を試すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f83dc-147">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="f83dc-148">もう1つの例として、大きな baggy グローブがあります。これは、手の形が見えにくくなる傾向があります。</span><span class="sxs-lookup"><span data-stu-id="f83dc-148">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="f83dc-149">最良の結果を得るには、できるだけフォーム継ぎ手として手袋を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f83dc-149">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="f83dc-150">バイザーに指紋または汚れがある場合は、HoloLens に付属している microfiber 掃除布を使用して、バイザーをゆっくりとクリーニングします。</span><span class="sxs-lookup"><span data-stu-id="f83dc-150">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

## <a name="hololens-doesnt-respond-to-my-voice-commands"></a><span data-ttu-id="f83dc-151">HoloLens が音声コマンドに応答しない</span><span class="sxs-lookup"><span data-stu-id="f83dc-151">HoloLens doesn't respond to my voice commands</span></span>

<span data-ttu-id="f83dc-152">Cortana が音声コマンドに応答しない場合は、Cortana が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-152">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="f83dc-153">[すべてのアプリ] の一覧で、[ **Cortana** メニューノートブックの設定] を選択して  >    >    >  変更を行います。</span><span class="sxs-lookup"><span data-stu-id="f83dc-153">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="f83dc-154">説明できることの詳細については、「 [HoloLens での音声の使用](hololens-cortana.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f83dc-154">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

## <a name="i-cant-place-holograms-or-see-holograms-that-i-previously-placed"></a><span data-ttu-id="f83dc-155">ホログラムを配置できない、または以前に配置したホログラムを表示できない</span><span class="sxs-lookup"><span data-stu-id="f83dc-155">I can't place holograms or see holograms that I previously placed</span></span>

<span data-ttu-id="f83dc-156">HoloLens がスペースをマップまたは読み込むことができない場合、制限モードになり、ホログラムを配置したり、配置したホログラムを表示したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f83dc-156">If HoloLens can't map or load your space, it enters Limited mode and you won't be able to place holograms or see holograms that you've placed.</span></span> <span data-ttu-id="f83dc-157">以下のことを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="f83dc-157">Here are some things to try:</span></span>

- <span data-ttu-id="f83dc-158">HoloLens が領域を参照してマップできるように、環境内に十分な光があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-158">Make sure that there's enough light in your environment so HoloLens can see and map the space.</span></span>
- <span data-ttu-id="f83dc-159">Wi-Fi ネットワークに接続していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-159">Make sure that you're connected to a Wi-Fi network.</span></span> <span data-ttu-id="f83dc-160">Wi-fi に接続していない場合、HoloLens は既知の領域を特定して読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="f83dc-160">If you're not connected to Wi-Fi, HoloLens can't identify and load a known space.</span></span>
- <span data-ttu-id="f83dc-161">新しいスペースを作成する必要がある場合は、Wi-fi に接続してから、HoloLens を再起動します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-161">If you need to create a new space, connect to Wi-Fi, then restart your HoloLens.</span></span>
- <span data-ttu-id="f83dc-162">正しい領域がアクティブかどうかを確認したり、手動で領域を読み込んだりするには、[**設定**] [システム領域] にアクセスし  >    >  ます。</span><span class="sxs-lookup"><span data-stu-id="f83dc-162">To see if the correct space is active, or to manually load a space, go to **Settings** > **System** > **Spaces**.</span></span>
- <span data-ttu-id="f83dc-163">適切な領域が読み込まれても問題が解決しない場合は、領域が破損している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f83dc-163">If the correct space is loaded and you're still having problems, the space may be corrupt.</span></span> <span data-ttu-id="f83dc-164">この問題を解決するには、スペースを選択し、[ **削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-164">To fix this issue, select the space, then select **Remove**.</span></span> <span data-ttu-id="f83dc-165">この領域を削除すると、HoloLens は環境のマップを開始し、新しい領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-165">After you remove the space, HoloLens starts to map your surroundings and create a new space.</span></span>

## <a name="my-hololens-cant-tell-what-space-im-in"></a><span data-ttu-id="f83dc-166">HoloLens がどの領域に参加しているかを判別できない</span><span class="sxs-lookup"><span data-stu-id="f83dc-166">My HoloLens can't tell what space I'm in</span></span>

<span data-ttu-id="f83dc-167">HoloLens が自動的に使用している領域を特定して読み込むことができない場合は、次の要素を確認します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-167">If your HoloLens can't identify and load the space you're in automatically, check the following factors:</span></span>

- <span data-ttu-id="f83dc-168">に接続されていることを確認し Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="f83dc-168">Make sure that you're connected to Wi-Fi</span></span>
- <span data-ttu-id="f83dc-169">部屋に十分な光があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-169">Make sure that there's plenty of light in the room</span></span>
- <span data-ttu-id="f83dc-170">周囲に大きな変更がないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-170">Make sure that there haven't been any major changes to the surroundings.</span></span>

<span data-ttu-id="f83dc-171">また、領域を手動で読み込むか、または **設定** システム領域に移動して、スペースを管理することもでき  >    >  ます。</span><span class="sxs-lookup"><span data-stu-id="f83dc-171">You can also load a space manually or manage your spaces by going to **Settings** > **System** > **Spaces**.</span></span>

## <a name="im-getting-a-low-disk-space-error"></a><span data-ttu-id="f83dc-172">"ディスク領域が不足しています" というエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="f83dc-172">I'm getting a "low disk space" error</span></span>

<span data-ttu-id="f83dc-173">次の1つまたは複数の操作を行って、記憶域スペースを解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f83dc-173">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="f83dc-174">未使用の領域をいくつか削除します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-174">Delete some unused spaces.</span></span> <span data-ttu-id="f83dc-175">[**設定**] [システム領域]  >    >  の順に選択し、不要になった領域を選択して、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-175">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="f83dc-176">配置したホログラムの一部を削除します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-176">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="f83dc-177">写真アプリから一部の画像とビデオを削除します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-177">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="f83dc-178">HoloLens から一部のアプリをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="f83dc-178">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="f83dc-179">[ **すべてのアプリ** ] 一覧で、アンインストールするアプリをタップして保持し、[ **アンインストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f83dc-179">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

## <a name="my-hololens-cant-create-a-new-space"></a><span data-ttu-id="f83dc-180">HoloLens で新しいスペースを作成できない</span><span class="sxs-lookup"><span data-stu-id="f83dc-180">My HoloLens can't create a new space</span></span>

<span data-ttu-id="f83dc-181">最も可能性の高い問題は、記憶域スペースが不足していることです。</span><span class="sxs-lookup"><span data-stu-id="f83dc-181">The most likely problem is that you're running low on storage space.</span></span> <span data-ttu-id="f83dc-182">前のいずれかの [ヒント](#im-getting-a-low-disk-space-error) を試して、ディスク領域を解放してください。</span><span class="sxs-lookup"><span data-stu-id="f83dc-182">Try one of the [previous tips](#im-getting-a-low-disk-space-error) to free up some disk space.</span></span>

## <a name="the-hololens-emulator-isnt-working"></a><span data-ttu-id="f83dc-183">HoloLens エミュレーターが動作していません</span><span class="sxs-lookup"><span data-stu-id="f83dc-183">The HoloLens emulator isn't working</span></span>

<span data-ttu-id="f83dc-184">HoloLens エミュレーターに関する情報は、開発者向けドキュメントに記載されています。</span><span class="sxs-lookup"><span data-stu-id="f83dc-184">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="f83dc-185">[HoloLens エミュレーターのトラブルシューティングの](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f83dc-185">Read more about [troubleshooting the HoloLens emulator](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).</span></span>
