---
title: トラブルシューティング
description: HoloLens の一般的な問題に対する解決策です。
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
keywords: 問題、バグ、トラブルシューティング、修正プログラム、ヘルプ、サポート、HoloLens
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: e00226852f92cf5b3137d8d41cfde0f01394f5bc
ms.sourcegitcommit: 7c16570839893f4a4432286b13ae6d84c665d376
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "10902292"
---
# <span data-ttu-id="e99e8-104">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e99e8-104">Troubleshooting</span></span>

<span data-ttu-id="e99e8-105">この記事では、いくつかの一般的な HoloLens の問題を解決する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e99e8-105">This article describes how to resolve several common HoloLens issues.</span></span>

## <span data-ttu-id="e99e8-106">HoloLens が応答しない、または起動しない</span><span class="sxs-lookup"><span data-stu-id="e99e8-106">My HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="e99e8-107">HoloLens が起動しない場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e99e8-107">If your HoloLens won't start:</span></span>

- <span data-ttu-id="e99e8-108">電源ボタンの横にある Led が点灯しない場合、または1つの LED がわずかに点滅する場合は、HoloLens の充電が必要になることがあり[ます。](hololens-recovery.md#charging-the-device)</span><span class="sxs-lookup"><span data-stu-id="e99e8-108">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens-recovery.md#charging-the-device)</span></span>
- <span data-ttu-id="e99e8-109">電源ボタンを押したときに Led が点灯したが、ディスプレイに何も表示されない場合は、[デバイスのハードリセットを preform](hololens-recovery.md#hard-reset-procedure)します。</span><span class="sxs-lookup"><span data-stu-id="e99e8-109">If the LEDs light up when you press the power button but you can't see anything on the displays, [preform a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="e99e8-110">HoloLens がフリーズまたは応答しなくなった場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e99e8-110">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="e99e8-111">すべての Led がオフになるまで、または15秒間、Led が反応しない場合は、電源ボタンを押して HoloLens をオフにします。</span><span class="sxs-lookup"><span data-stu-id="e99e8-111">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="e99e8-112">HoloLens を起動するには、もう一度 power ボタンを押します。</span><span class="sxs-lookup"><span data-stu-id="e99e8-112">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="e99e8-113">以上の手順で問題が解決しない場合は、 [hololens 2 デバイス](hololens-recovery.md)または[hololens (第1世代) デバイス](hololens1-recovery.md)を回復してみてください。</span><span class="sxs-lookup"><span data-stu-id="e99e8-113">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

## <span data-ttu-id="e99e8-114">ホログラムが適切に表示されない</span><span class="sxs-lookup"><span data-stu-id="e99e8-114">Holograms don't look good</span></span>

<span data-ttu-id="e99e8-115">ホログラムが不安定な場合、jumpy されている場合、または適切に表示されない場合は、次の操作を試してください。</span><span class="sxs-lookup"><span data-stu-id="e99e8-115">If your holograms are unstable, jumpy, or don't look right, try:</span></span>

- <span data-ttu-id="e99e8-116">HoloLens の前面にあるデバイスのバイザーとセンサーバーをクリーニングします。</span><span class="sxs-lookup"><span data-stu-id="e99e8-116">Cleaning your device visor and sensor bar on the front of your HoloLens.</span></span>
- <span data-ttu-id="e99e8-117">室内での光の増加。</span><span class="sxs-lookup"><span data-stu-id="e99e8-117">Increasing the light in your room.</span></span>
- <span data-ttu-id="e99e8-118">HoloLens でより完全にスキャンされるように、お客様の環境を調査して見ていきましょう。</span><span class="sxs-lookup"><span data-stu-id="e99e8-118">Walking around and looking at your surroundings so that HoloLens can scan them more completely.</span></span>
- <span data-ttu-id="e99e8-119">お客様のニーズに応じた HoloLens の調整。</span><span class="sxs-lookup"><span data-stu-id="e99e8-119">Calibrating your HoloLens for your eyes.</span></span> <span data-ttu-id="e99e8-120">[**設定**  >  **システム**  >  **ユーティリティ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e99e8-120">Go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="e99e8-121">**[調整]** で、**[調整を開く]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e99e8-121">Under **Calibration**, select **Open Calibration**.</span></span>

## <span data-ttu-id="e99e8-122">HoloLens が手書き入力に応答しない</span><span class="sxs-lookup"><span data-stu-id="e99e8-122">HoloLens doesn't respond to hand input</span></span>

<span data-ttu-id="e99e8-123">HoloLens が自分の手を見ることができるようにするには、ジェスチャのフレームにそのまま保存しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e99e8-123">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="e99e8-124">Mixed Reality ホームでは、自分の針が追跡されたことを通知するフィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="e99e8-124">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="e99e8-125">フィードバックは、HoloLens のバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e99e8-125">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="e99e8-126">HoloLens (第1世代) では、宝石カーソルがドットからリングに変わります</span><span class="sxs-lookup"><span data-stu-id="e99e8-126">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="e99e8-127">HoloLens 2 では、手がスレートに近いときに指先のカーソルが表示され、slates が離れると手動で表示されます。</span><span class="sxs-lookup"><span data-stu-id="e99e8-127">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="e99e8-128">多くのイマーシブアプリは、Mixed Reality ホームに似た入力パターンに従います。</span><span class="sxs-lookup"><span data-stu-id="e99e8-128">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="e99e8-129">詳細については、「 [hololens (第1世代)](hololens1-basic-usage.md#use-hololens-with-your-hands)と[hololens 2](hololens2-basic-usage.md#the-hand-tracking-frame)での手書き入力の使い方」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e99e8-129">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="e99e8-130">手袋を装着している場合、一部の種類の手袋は、ハンドトラッキングで動作しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e99e8-130">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="e99e8-131">一般的な例としては、赤外線の光量を吸収し、深度カメラによって認識されないことが多い黒のゴムがあります。</span><span class="sxs-lookup"><span data-stu-id="e99e8-131">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="e99e8-132">ラバーグローブが含まれている場合は、青や灰色などの明るい色を試すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e99e8-132">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="e99e8-133">別の例としては、大きな baggy グローブがあります。これは、手の形が不明瞭になる傾向があります。</span><span class="sxs-lookup"><span data-stu-id="e99e8-133">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="e99e8-134">最善の結果を得るために、できるだけフォーム継ぎ手として手袋を使うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e99e8-134">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="e99e8-135">お使いのバイザーに指紋や汚れがある場合は、HoloLens に付属のマイクロファイバーのクリーニング布を使って、お使いのバイザーを軽く拭きます。</span><span class="sxs-lookup"><span data-stu-id="e99e8-135">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

## <span data-ttu-id="e99e8-136">HoloLens が音声コマンドに応答しない</span><span class="sxs-lookup"><span data-stu-id="e99e8-136">HoloLens doesn't respond to my voice commands</span></span>

<span data-ttu-id="e99e8-137">Cortana が音声コマンドに応答しない場合は、[Cortana] がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e99e8-137">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="e99e8-138">[すべてのアプリ] の一覧で、[ **Cortana**メニューノートブックの設定] を選択して  >  **Menu**  >  **Notebook**  >  **Settings**変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="e99e8-138">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="e99e8-139">発声できる内容の詳細については、「[HoloLens で音声を使う](hololens-cortana.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e99e8-139">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

## <span data-ttu-id="e99e8-140">ホログラムを配置できない、または以前に配置したホログラムが表示されない</span><span class="sxs-lookup"><span data-stu-id="e99e8-140">I can't place holograms or see holograms that I previously placed</span></span>

<span data-ttu-id="e99e8-141">HoloLens でスペースをマップまたは読み込むことができない場合は、制限モードになり、ホログラムを配置したり、配置したホログラムを表示したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e99e8-141">If HoloLens can't map or load your space, it enters Limited mode and you won't be able to place holograms or see holograms that you've placed.</span></span> <span data-ttu-id="e99e8-142">以下をお試しください。</span><span class="sxs-lookup"><span data-stu-id="e99e8-142">Here are some things to try:</span></span>

- <span data-ttu-id="e99e8-143">お使いの環境に、HoloLens がスペースを表示してマップできる十分なライトがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e99e8-143">Make sure that there's enough light in your environment so HoloLens can see and map the space.</span></span>
- <span data-ttu-id="e99e8-144">Wi-fi ネットワークに接続していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e99e8-144">Make sure that you're connected to a Wi-Fi network.</span></span> <span data-ttu-id="e99e8-145">Wi-fi に接続していない場合は、HoloLens で既知のスペースを特定して読み込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="e99e8-145">If you're not connected to Wi-Fi, HoloLens can't identify and load a known space.</span></span>
- <span data-ttu-id="e99e8-146">新しいスペースを作成する必要がある場合は、Wi-fi に接続して、HoloLens を再起動します。</span><span class="sxs-lookup"><span data-stu-id="e99e8-146">If you need to create a new space, connect to Wi-Fi, then restart your HoloLens.</span></span>
- <span data-ttu-id="e99e8-147">適切な領域がアクティブであるか、または手動でスペースを読み込むかを確認するには、[**設定**  >  **システム**スペース] に移動し  >  **Spaces**ます。</span><span class="sxs-lookup"><span data-stu-id="e99e8-147">To see if the correct space is active, or to manually load a space, go to **Settings** > **System** > **Spaces**.</span></span>
- <span data-ttu-id="e99e8-148">適切な領域が読み込まれても問題が解決しない場合は、領域が破損している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e99e8-148">If the correct space is loaded and you're still having problems, the space may be corrupt.</span></span> <span data-ttu-id="e99e8-149">この問題を解決するには、領域を選択し、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e99e8-149">To fix this issue, select the space, then select **Remove**.</span></span> <span data-ttu-id="e99e8-150">この領域を削除すると、HoloLens で環境のマッピングが開始され、新しいスペースが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e99e8-150">After you remove the space, HoloLens starts to map your surroundings and create a new space.</span></span>

## <span data-ttu-id="e99e8-151">HoloLens で現在のスペースがわからない</span><span class="sxs-lookup"><span data-stu-id="e99e8-151">My HoloLens can't tell what space I'm in</span></span>

<span data-ttu-id="e99e8-152">HoloLens で自動的に使用されている領域を特定して読み込むことができない場合は、次の点を確認してください。</span><span class="sxs-lookup"><span data-stu-id="e99e8-152">If your HoloLens can't identify and load the space you're in automatically, check the following factors:</span></span>

- <span data-ttu-id="e99e8-153">Wi-fi に接続していることを確認する</span><span class="sxs-lookup"><span data-stu-id="e99e8-153">Make sure that you're connected to Wi-Fi</span></span>
- <span data-ttu-id="e99e8-154">会議室に光が十分あることを確認する</span><span class="sxs-lookup"><span data-stu-id="e99e8-154">Make sure that there's plenty of light in the room</span></span>
- <span data-ttu-id="e99e8-155">環境に大きな変更が加えられていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e99e8-155">Make sure that there haven't been any major changes to the surroundings.</span></span>

<span data-ttu-id="e99e8-156">また、**設定**システムの領域に移動して、スペースを手動で読み込むか、スペースを管理することもでき  >  **System**  >  **Spaces**ます。</span><span class="sxs-lookup"><span data-stu-id="e99e8-156">You can also load a space manually or manage your spaces by going to **Settings** > **System** > **Spaces**.</span></span>

## <span data-ttu-id="e99e8-157">"ディスク領域が不足しています" というエラーが表示になる</span><span class="sxs-lookup"><span data-stu-id="e99e8-157">I'm getting a "low disk space" error</span></span>

<span data-ttu-id="e99e8-158">次の操作のいずれか、または複数の操作を行って、記憶域を解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e99e8-158">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="e99e8-159">未使用のスペースを削除します。</span><span class="sxs-lookup"><span data-stu-id="e99e8-159">Delete some unused spaces.</span></span> <span data-ttu-id="e99e8-160">[**設定**システムスペース] に移動して、不要になったスペースを選択し、[  >  **System**  >  **Spaces\*\*\*\*削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e99e8-160">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="e99e8-161">配置したホログラムの一部を削除します。</span><span class="sxs-lookup"><span data-stu-id="e99e8-161">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="e99e8-162">写真アプリから一部の画像とビデオを削除します。</span><span class="sxs-lookup"><span data-stu-id="e99e8-162">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="e99e8-163">HoloLens からいくつかのアプリをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="e99e8-163">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="e99e8-164">[**すべてのアプリ**] の一覧で、アンインストールするアプリをタップして押し続け、[**アンインストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e99e8-164">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

## <span data-ttu-id="e99e8-165">HoloLens で新しいスペースを作成できない</span><span class="sxs-lookup"><span data-stu-id="e99e8-165">My HoloLens can't create a new space</span></span>

<span data-ttu-id="e99e8-166">最も可能性が高いのは、記憶領域が少なくなっていることです。</span><span class="sxs-lookup"><span data-stu-id="e99e8-166">The most likely problem is that you're running low on storage space.</span></span> <span data-ttu-id="e99e8-167">ディスク領域を解放するには、[上記のヒント](#im-getting-a-low-disk-space-error)のいずれかを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="e99e8-167">Try one of the [previous tips](#im-getting-a-low-disk-space-error) to free up some disk space.</span></span>

## <span data-ttu-id="e99e8-168">HoloLens エミュレーターが動作していない</span><span class="sxs-lookup"><span data-stu-id="e99e8-168">The HoloLens emulator isn't working</span></span>

<span data-ttu-id="e99e8-169">HoloLens エミュレーターに関する情報は、開発者向けドキュメントに記載されています。</span><span class="sxs-lookup"><span data-stu-id="e99e8-169">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="e99e8-170">「 [HoloLens エミュレーターのトラブルシューティング](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e99e8-170">Read more about [troubleshooting the HoloLens emulator](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).</span></span>
