---
title: HoloLens の問題のトラブルシューティング
description: HoloLens の一般的な問題に対する解決策です。
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: 問題、バグ、トラブルシューティング、修正プログラム、ヘルプ、サポート、HoloLens
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4897d02f4b789c77204d57c0a7750e3c3803d7bb
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829022"
---
# <span data-ttu-id="e0cee-104">HoloLens の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e0cee-104">Troubleshoot HoloLens issues</span></span>

<span data-ttu-id="e0cee-105">この記事では、いくつかの一般的な HoloLens の問題を解決する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0cee-105">This article describes how to resolve several common HoloLens issues.</span></span>

## <span data-ttu-id="e0cee-106">HoloLens が応答しない、または起動しない</span><span class="sxs-lookup"><span data-stu-id="e0cee-106">My HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="e0cee-107">HoloLens が起動しない場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e0cee-107">If your HoloLens won't start:</span></span>

- <span data-ttu-id="e0cee-108">電源ボタンの横にある Led が点灯しない場合、または1つの LED がわずかに点滅する場合は、HoloLens の充電が必要になることがあり[ます。](hololens-recovery.md#charging-the-device)</span><span class="sxs-lookup"><span data-stu-id="e0cee-108">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens-recovery.md#charging-the-device)</span></span>
- <span data-ttu-id="e0cee-109">電源ボタンを押したときに Led が点灯したが、ディスプレイに何も表示されない場合は、[デバイスのハードリセットを preform](hololens-recovery.md#hard-reset-procedure)します。</span><span class="sxs-lookup"><span data-stu-id="e0cee-109">If the LEDs light up when you press the power button but you can't see anything on the displays, [preform a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="e0cee-110">HoloLens がフリーズまたは応答しなくなった場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e0cee-110">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="e0cee-111">すべての Led がオフになるまで、または15秒間、Led が反応しない場合は、電源ボタンを押して HoloLens をオフにします。</span><span class="sxs-lookup"><span data-stu-id="e0cee-111">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="e0cee-112">HoloLens を起動するには、もう一度 power ボタンを押します。</span><span class="sxs-lookup"><span data-stu-id="e0cee-112">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="e0cee-113">以上の手順で問題が解決しない場合は、 [hololens 2 デバイス](hololens-recovery.md)または[hololens (第1世代) デバイス](hololens1-recovery.md)を回復してみてください。</span><span class="sxs-lookup"><span data-stu-id="e0cee-113">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

## <span data-ttu-id="e0cee-114">ホログラムが適切に表示されない</span><span class="sxs-lookup"><span data-stu-id="e0cee-114">Holograms don't look good</span></span>

<span data-ttu-id="e0cee-115">ホログラムが不安定な場合、jumpy されている場合、または適切に表示されない場合は、次の操作を試してください。</span><span class="sxs-lookup"><span data-stu-id="e0cee-115">If your holograms are unstable, jumpy, or don't look right, try:</span></span>

- <span data-ttu-id="e0cee-116">HoloLens の前面にあるデバイスのバイザーとセンサーバーをクリーニングします。</span><span class="sxs-lookup"><span data-stu-id="e0cee-116">Cleaning your device visor and sensor bar on the front of your HoloLens.</span></span>
- <span data-ttu-id="e0cee-117">室内での光の増加。</span><span class="sxs-lookup"><span data-stu-id="e0cee-117">Increasing the light in your room.</span></span>
- <span data-ttu-id="e0cee-118">HoloLens でより完全にスキャンされるように、お客様の環境を調査して見ていきましょう。</span><span class="sxs-lookup"><span data-stu-id="e0cee-118">Walking around and looking at your surroundings so that HoloLens can scan them more completely.</span></span>
- <span data-ttu-id="e0cee-119">お客様のニーズに応じた HoloLens の調整。</span><span class="sxs-lookup"><span data-stu-id="e0cee-119">Calibrating your HoloLens for your eyes.</span></span> <span data-ttu-id="e0cee-120">[**設定**  >  **システム**  >  **ユーティリティ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e0cee-120">Go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="e0cee-121">**[調整]** で、**[調整を開く]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0cee-121">Under **Calibration**, select **Open Calibration**.</span></span>

## <span data-ttu-id="e0cee-122">HoloLens がジェスチャに応答しない</span><span class="sxs-lookup"><span data-stu-id="e0cee-122">HoloLens doesn't respond to gestures</span></span>

<span data-ttu-id="e0cee-123">を選び、HoloLens がジェスチャを見られるようにします。</span><span class="sxs-lookup"><span data-stu-id="e0cee-123">To make sure that HoloLens can see your gestures.</span></span>  <span data-ttu-id="e0cee-124">ジェスチャのフレームに手を置く-HoloLens で手を見られるようになると、カーソルがドットからリングに変わります。</span><span class="sxs-lookup"><span data-stu-id="e0cee-124">Keep your hand in the gesture frame - when HoloLens can see your hand, the cursor changes from a dot to a ring.</span></span>

<span data-ttu-id="e0cee-125">[Hololens (第1世代)](hololens1-basic-usage.md#use-hololens-with-your-hands)または[hololens 2](hololens2-basic-usage.md#the-hand-tracking-frame)でのジェスチャの使い方については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0cee-125">Learn more about using gestures on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) or [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="e0cee-126">環境が暗すぎると、HoloLens で手が見えない場合があるため、十分なライトがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e0cee-126">If your environment is too dark, HoloLens might not see your hand, so make sure that there's enough light.</span></span>

<span data-ttu-id="e0cee-127">お使いのバイザーに指紋や汚れがある場合は、HoloLens に付属のマイクロファイバーのクリーニング布を使って、お使いのバイザーを軽く拭きます。</span><span class="sxs-lookup"><span data-stu-id="e0cee-127">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

## <span data-ttu-id="e0cee-128">HoloLens が音声コマンドに応答しない</span><span class="sxs-lookup"><span data-stu-id="e0cee-128">HoloLens doesn't respond to my voice commands</span></span>

<span data-ttu-id="e0cee-129">Cortana が音声コマンドに応答しない場合は、[Cortana] がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e0cee-129">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="e0cee-130">[すべてのアプリ] の一覧で、[ **Cortana**メニューノートブックの設定] を選択して  >  **Menu**  >  **Notebook**  >  **Settings**変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="e0cee-130">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="e0cee-131">発声できる内容の詳細については、「[HoloLens で音声を使う](hololens-cortana.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e0cee-131">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

## <span data-ttu-id="e0cee-132">ホログラムを配置できない、または以前に配置したホログラムが表示されない</span><span class="sxs-lookup"><span data-stu-id="e0cee-132">I can't place holograms or see holograms that I previously placed</span></span>

<span data-ttu-id="e0cee-133">HoloLens でスペースをマップまたは読み込むことができない場合は、制限モードになり、ホログラムを配置したり、配置したホログラムを表示したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e0cee-133">If HoloLens can't map or load your space, it enters Limited mode and you won't be able to place holograms or see holograms that you've placed.</span></span> <span data-ttu-id="e0cee-134">以下をお試しください。</span><span class="sxs-lookup"><span data-stu-id="e0cee-134">Here are some things to try:</span></span>

- <span data-ttu-id="e0cee-135">お使いの環境に、HoloLens がスペースを表示してマップできる十分なライトがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e0cee-135">Make sure that there's enough light in your environment so HoloLens can see and map the space.</span></span>
- <span data-ttu-id="e0cee-136">Wi-fi ネットワークに接続していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e0cee-136">Make sure that you're connected to a Wi-Fi network.</span></span> <span data-ttu-id="e0cee-137">Wi-fi に接続していない場合は、HoloLens で既知のスペースを特定して読み込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="e0cee-137">If you're not connected to Wi-Fi, HoloLens can't identify and load a known space.</span></span>
- <span data-ttu-id="e0cee-138">新しいスペースを作成する必要がある場合は、Wi-fi に接続して、HoloLens を再起動します。</span><span class="sxs-lookup"><span data-stu-id="e0cee-138">If you need to create a new space, connect to Wi-Fi, then restart your HoloLens.</span></span>
- <span data-ttu-id="e0cee-139">適切な領域がアクティブであるか、または手動でスペースを読み込むかを確認するには、[**設定**  >  **システム**スペース] に移動し  >  **Spaces**ます。</span><span class="sxs-lookup"><span data-stu-id="e0cee-139">To see if the correct space is active, or to manually load a space, go to **Settings** > **System** > **Spaces**.</span></span>
- <span data-ttu-id="e0cee-140">適切な領域が読み込まれても問題が解決しない場合は、領域が破損している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e0cee-140">If the correct space is loaded and you're still having problems, the space may be corrupt.</span></span> <span data-ttu-id="e0cee-141">この問題を解決するには、領域を選択し、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0cee-141">To fix this issue, select the space, then select **Remove**.</span></span> <span data-ttu-id="e0cee-142">この領域を削除すると、HoloLens で環境のマッピングが開始され、新しいスペースが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e0cee-142">After you remove the space, HoloLens starts to map your surroundings and create a new space.</span></span>

## <span data-ttu-id="e0cee-143">HoloLens で現在のスペースがわからない</span><span class="sxs-lookup"><span data-stu-id="e0cee-143">My HoloLens can't tell what space I'm in</span></span>

<span data-ttu-id="e0cee-144">HoloLens で自動的に使用されている領域を特定して読み込むことができない場合は、次の点を確認してください。</span><span class="sxs-lookup"><span data-stu-id="e0cee-144">If your HoloLens can't identify and load the space you're in automatically, check the following factors:</span></span>

- <span data-ttu-id="e0cee-145">Wi-fi に接続していることを確認する</span><span class="sxs-lookup"><span data-stu-id="e0cee-145">Make sure that you're connected to Wi-Fi</span></span>
- <span data-ttu-id="e0cee-146">会議室に光が十分あることを確認する</span><span class="sxs-lookup"><span data-stu-id="e0cee-146">Make sure that there's plenty of light in the room</span></span>
- <span data-ttu-id="e0cee-147">環境に大きな変更が加えられていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e0cee-147">Make sure that there haven't been any major changes to the surroundings.</span></span>

<span data-ttu-id="e0cee-148">また、**設定**システムの領域に移動して、スペースを手動で読み込むか、スペースを管理することもでき  >  **System**  >  **Spaces**ます。</span><span class="sxs-lookup"><span data-stu-id="e0cee-148">You can also load a space manually or manage your spaces by going to **Settings** > **System** > **Spaces**.</span></span>

## <span data-ttu-id="e0cee-149">"ディスク領域が不足しています" というエラーが表示になる</span><span class="sxs-lookup"><span data-stu-id="e0cee-149">I'm getting a "low disk space" error</span></span>

<span data-ttu-id="e0cee-150">次の操作のいずれか、または複数の操作を行って、記憶域を解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0cee-150">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="e0cee-151">未使用のスペースを削除します。</span><span class="sxs-lookup"><span data-stu-id="e0cee-151">Delete some unused spaces.</span></span> <span data-ttu-id="e0cee-152">[**設定**システムスペース] に移動して、不要になったスペースを選択し、[  >  **System**  >  **Spaces\*\*\*\*削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0cee-152">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="e0cee-153">配置したホログラムの一部を削除します。</span><span class="sxs-lookup"><span data-stu-id="e0cee-153">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="e0cee-154">写真アプリから一部の画像とビデオを削除します。</span><span class="sxs-lookup"><span data-stu-id="e0cee-154">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="e0cee-155">HoloLens からいくつかのアプリをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="e0cee-155">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="e0cee-156">[**すべてのアプリ**] の一覧で、アンインストールするアプリをタップして押し続け、[**アンインストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0cee-156">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

## <span data-ttu-id="e0cee-157">HoloLens で新しいスペースを作成できない</span><span class="sxs-lookup"><span data-stu-id="e0cee-157">My HoloLens can't create a new space</span></span>

<span data-ttu-id="e0cee-158">最も可能性が高いのは、記憶領域が少なくなっていることです。</span><span class="sxs-lookup"><span data-stu-id="e0cee-158">The most likely problem is that you're running low on storage space.</span></span> <span data-ttu-id="e0cee-159">ディスク領域を解放するには、[上記のヒント](#im-getting-a-low-disk-space-error)のいずれかを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="e0cee-159">Try one of the [previous tips](#im-getting-a-low-disk-space-error) to free up some disk space.</span></span>

## <span data-ttu-id="e0cee-160">HoloLens エミュレーターが動作していない</span><span class="sxs-lookup"><span data-stu-id="e0cee-160">The HoloLens emulator isn't working</span></span>

<span data-ttu-id="e0cee-161">HoloLens エミュレーターに関する情報は、開発者向けドキュメントに記載されています。</span><span class="sxs-lookup"><span data-stu-id="e0cee-161">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="e0cee-162">「 [HoloLens エミュレーターのトラブルシューティング](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0cee-162">Read more about [troubleshooting the HoloLens emulator](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).</span></span>
