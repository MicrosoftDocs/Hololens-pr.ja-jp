---
title: HoloLens 1 を再起動、リセット、または回復する
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Windows デバイス回復ツールを使用してイメージを HoloLens 最初の世代にフラッシュする方法。
keywords: 操作方法、再起動、リセット、回復、ハードリセット、ソフトリセット、電源サイクル、HoloLens、シャットダウン、wdrt、windows デバイス回復ツール
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4840535030cc81f222cb25357474f1c751426e91
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635230"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="6eb6c-104">HoloLens の再起動、リセット、または回復 (第1世代)</span><span class="sxs-lookup"><span data-stu-id="6eb6c-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="6eb6c-105">HoloLens で問題が発生している場合は、再起動またはリセットするか、デバイスの回復を使用してデバイスを更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="6eb6c-106">この記事では、推奨される回復手順について順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="6eb6c-107">HoloLens 2 の回復を検討している場合は、「 [HoloLens 2 の回復](hololens-recovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](hololens-recovery.md), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="6eb6c-108">この記事では、HoloLens デバイスとソフトウェアに焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="6eb6c-109">ホログラムが正しく表示されない場合は、「 **[HoloLens 環境に関する考慮事項](hololens-environment-considerations.md)**」で、ホログラムの品質を向上させる要因についての情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="6eb6c-110">やり直し</span><span class="sxs-lookup"><span data-stu-id="6eb6c-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="6eb6c-111">Cortana を使用して安全に再起動する</span><span class="sxs-lookup"><span data-stu-id="6eb6c-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="6eb6c-112">HoloLens を再起動する最も安全な方法は、Cortana を使用することです。これは通常、HoloLens に関する問題が発生したときに最初に試みることになります。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="6eb6c-113">Cortana は、すべてのデバイスで使用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="6eb6c-114">Cortana は、すべての HoloLens (第1世代) デバイスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="6eb6c-115">Cortana は、Windows Holograpic バージョン 2004 update より前のビルドの HoloLens 2 デバイスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="6eb6c-116">HoloLens をオンにします。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="6eb6c-117">ユーザーがログインしていて、デバイスがパスワードのロックを解除するのを待機していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="6eb6c-118">「Cortana、再起動」、Cortana 「再起動についてはこんにちは」と言います。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="6eb6c-119">Cortana が応答し、確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="6eb6c-120">質問の後にサウンドが再生されるのを待ってから、「はい」と言います。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="6eb6c-121">デバイスが再起動されます。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="6eb6c-122">[電源] ボタンを使用して安全に再起動する</span><span class="sxs-lookup"><span data-stu-id="6eb6c-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="6eb6c-123">それでもデバイスを再起動できない場合は、 **電源** ボタンを使用してデバイスを再起動してみてください。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="6eb6c-124">5秒間、 **電源** ボタンを押したままにします。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="6eb6c-125">1秒後に、5つのすべての Led が点灯し、右から左に1ずつ徐々にオフになります。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="6eb6c-126">5秒後、すべての Led はオフになり、正常にシャットダウンされたことを示します。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="6eb6c-127">すべての Led がオフになった直後にボタンを押すのを止めます。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="6eb6c-128">シャットダウンが完了するまで1分待ちます。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="6eb6c-129">ディスプレイがオフになった後も、シャットダウンが進行中である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="6eb6c-130">1秒間、電源ボタンを押したままデバイスの **電源** を再度オンにします。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="6eb6c-131">Windows デバイスポータルを使用して安全に再起動する</span><span class="sxs-lookup"><span data-stu-id="6eb6c-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="6eb6c-132">このプロセスでは、HoloLens を開発者デバイスとして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="6eb6c-133">詳細については、 [Windows デバイスポータル](/windows/mixed-reality/using-the-windows-device-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-133">Learn more at [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="6eb6c-134">前の手順が機能しなかった場合は、 [Windows デバイスポータル](/windows/mixed-reality/using-the-windows-device-portal)を使用してデバイスを再起動してみてください。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="6eb6c-135">右上隅で、デバイスを再起動またはシャットダウンするオプションを見つけます。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="6eb6c-136">安全でない強制再起動の実行</span><span class="sxs-lookup"><span data-stu-id="6eb6c-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="6eb6c-137">前の方法で HoloLens を再起動しなかった場合は、強制的に再起動します。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="6eb6c-138">この方法は、バッテリを取り外して再インストールすることと同じです。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="6eb6c-139">デバイスが破損した状態のままになる可能性があるため、危険です。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="6eb6c-140">そのような場合は、HoloLens をフラッシュする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="6eb6c-141">これは有害な可能性があるメソッドであり、前述のメソッドが機能しなかった場合にのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="6eb6c-142">少なくとも10秒間、 **電源** ボタンを押したままにします。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="6eb6c-143">ボタンは10秒より長く保持できます。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="6eb6c-144">LED の動作を無視しても安全です。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="6eb6c-145">ボタンを離し、2-3 秒間待機します。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="6eb6c-146">1秒間、 **電源** ボタンを押したままにします。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="6eb6c-147">それでも問題が発生する場合は、 **電源** ボタンを4秒押して、すべてのバッテリインジケーターがフェードアウトし、画面がホログラムの表示を停止します。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="6eb6c-148">1分待ってから、もう一度 **電源** ボタンを押してデバイスの電源を入れます。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="6eb6c-149">前のバージョン HoloLens に戻る (第1世代)</span><span class="sxs-lookup"><span data-stu-id="6eb6c-149">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="6eb6c-150">場合によっては、以前のバージョンの HoloLens ソフトウェアに戻る必要があります。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-150">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="6eb6c-151">これを行うには、Windows デバイスの回復ツールを使用して、HoloLens を以前のバージョンにリセットします。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-151">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="6eb6c-152">以前のバージョンに戻すと、個人用ファイルと設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-152">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="6eb6c-153">以前のバージョンの HoloLens 1 に戻るには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-153">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="6eb6c-154">PC に接続されている携帯電話や Windows デバイスがないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-154">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="6eb6c-155">PC で、 [Windows Device Recovery Tool (wdrt)](https://support.microsoft.com/help/12379)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-155">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="6eb6c-156">[HoloLens 記念日更新プログラムの回復パッケージ](https://aka.ms/hololensrecovery)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-156">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="6eb6c-157">ダウンロードが完了したら、**エクスプローラー** の [ダウンロード] を開き  >  ます。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-157">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="6eb6c-158">ダウンロードした zip 形式のフォルダーを右クリックし、[**すべて** 抽出] を選択し  >  て解凍します。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-158">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="6eb6c-159">付属のマイクロ USB ケーブルを使用して、HoloLens を PC に Connect します。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-159">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="6eb6c-160">(他のケーブルを使って HoloLens に接続していたとしても、この方法は最適です)。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-160">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="6eb6c-161">WDRT は、HoloLens を自動的に検出します。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-161">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="6eb6c-162">[ **Microsoft HoloLens** ] タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-162">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="6eb6c-163">次の画面で、[ **パッケージの手動選択** ] を選択し、手順 4. で解凍したフォルダーに格納されているインストールファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-163">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="6eb6c-164">(拡張子が ffu のファイルを探します。)</span><span class="sxs-lookup"><span data-stu-id="6eb6c-164">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="6eb6c-165">[ **ソフトウェアのインストール**] を選択し、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-165">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="6eb6c-166">wdrt によって HoloLens が検出されない場合は、PC を再起動してみてください。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-166">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="6eb6c-167">それでもうまくいかない場合は、[**デバイスが検出されませんでした**] を選択し、[ **Microsoft HoloLens**] を選択して、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-167">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="6eb6c-168">工場出荷時の設定にリセットする</span><span class="sxs-lookup"><span data-stu-id="6eb6c-168">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="6eb6c-169">バッテリのリセットには、少なくとも40% の料金が必要です。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-169">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="6eb6c-170">HoloLens に問題が解決しない場合は、工場出荷時の状態にリセットしてみてください。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-170">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="6eb6c-171">このステップでは、インストールされている Windows Holographic ソフトウェアのバージョンを保持し、他のすべてを出荷時の設定に戻します。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-171">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="6eb6c-172">デバイスをリセットすると、すべての個人データ、アプリ、および設定が削除されます (TPM リセット情報も含む)。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-172">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="6eb6c-173">リセットすると、Windows Holographic のインストールされている最新バージョンのみがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-173">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="6eb6c-174">すべての初期化手順 (調整、Wi-fi への接続、ユーザーアカウントの作成、アプリのダウンロードなど) を再実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-174">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="6eb6c-175">設定アプリを開き、[**更新**] [回復] の順に選択し  >  ます。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-175">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="6eb6c-176">[ **デバイスのリセット** ] オプションを選択し、確認メッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-176">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="6eb6c-177">リセットを確認します。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-177">Confirm the reset.</span></span> <span data-ttu-id="6eb6c-178">デバイスが再起動し、スピン歯車と進行状況バーのセットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-178">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="6eb6c-179">このプロセスが完了するまで約30分待ちます。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-179">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="6eb6c-180">この処理が完了すると、デバイスはすぐに使えるようになります。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-180">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="6eb6c-181">オペレーティングシステムを再インストールする</span><span class="sxs-lookup"><span data-stu-id="6eb6c-181">Reinstall the operating system</span></span>

<span data-ttu-id="6eb6c-182">再起動およびリセット後もデバイスに問題が発生する場合は、コンピューターで回復ツールを使用して、HoloLens オペレーティングシステムとファームウェアを再インストールできます。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-182">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="6eb6c-183">リセットに必要な HoloLens データは、.iso、.wim、.vhd ファイルに似た完全な Flash 更新プログラム (ffu) にパッケージ化されます。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-183">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="6eb6c-184">FFU イメージファイル形式について説明します。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-184">Learn about FFU image file formats.</span></span>](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="6eb6c-185">Windows デバイスの回復ツールを使用して、HoloLens (第1世代) に新しいオペレーティングシステムをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-185">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="6eb6c-186">このツールを使用する前に、HoloLens の再起動またはリセットによって問題が解決されるかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-186">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="6eb6c-187">回復プロセスには時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-187">The recovery process may take a while.</span></span> <span data-ttu-id="6eb6c-188">完了すると、Windows Holographic ソフトウェアの最新バージョンがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-188">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="6eb6c-189">このツールを使用するには、少なくとも 4 GB の空き記憶領域がある Windows 10 以降を実行するコンピューターが必要です。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-189">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="6eb6c-190">仮想マシンでこのツールを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-190">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="6eb6c-191">HoloLens の回復</span><span class="sxs-lookup"><span data-stu-id="6eb6c-191">Recover your HoloLens</span></span>

1. <span data-ttu-id="6eb6c-192">[Windows デバイス回復ツール](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)をコンピューターにダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-192">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="6eb6c-193">HoloLens に付属しているマイクロ USB ケーブルを使用して、HoloLens (第1世代) をコンピューターに Connect します。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-193">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="6eb6c-194">Windows デバイスの回復ツールを開き、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-194">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="6eb6c-195">HoloLens (第1世代) が自動的に検出されなかった場合は、[**デバイスが検出されませんでした**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-195">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="6eb6c-196">次に、指示に従って、デバイスを回復モードにします。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-196">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="6eb6c-197">手動フラッシュモード</span><span class="sxs-lookup"><span data-stu-id="6eb6c-197">Manual flashing mode</span></span>

<span data-ttu-id="6eb6c-198">デバイスが検出されない場合は、次の手順に従って、フラッシュモードにします。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-198">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="6eb6c-199">任意の電源からデバイスを取り外します。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-199">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="6eb6c-200">デバイスがオンになっている場合は、 **電源** ボタンを押したままにすると、完全にオフになります。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-200">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="6eb6c-201">[ **音量** ] ボタンを押したまま、[ **電源** ] ボタンを簡単にタップします。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-201">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="6eb6c-202">デバイスが起動し、中央の LED のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-202">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="6eb6c-203">デバイスを PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-203">Plug the device into your PC.</span></span>
4. <span data-ttu-id="6eb6c-204">Windows デバイスの回復ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-204">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="6eb6c-205">[**デバイスが検出されませんでした**] を選択し、 **HoloLens** します。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-205">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="6eb6c-206">指示に従って、デバイスを回復します。</span><span class="sxs-lookup"><span data-stu-id="6eb6c-206">Follow the instructions to recover your device.</span></span>
