---
title: HoloLens 1 の再起動、リセット、または回復
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Windows デバイス回復ツールを使用して HoloLens 第 1 世代にイメージをフラッシュする方法。
keywords: 方法, 再起動, リセット, 回復, ハード リセット, ソフト リセット, 電源サイクル, HoloLens, シャットダウン, wdrt, Windows デバイス回復ツール
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
ms.openlocfilehash: f855aa84a347edc85e5b9f02458721778eb2515a
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397693"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="e40d3-104">HoloLens の再起動、リセット、または復旧 (第 1 世代)</span><span class="sxs-lookup"><span data-stu-id="e40d3-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="e40d3-105">HoloLens で問題が発生している場合は、再起動またはリセットを試したり、デバイスの回復を使用してデバイスを再フラッシュしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e40d3-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="e40d3-106">この記事では、推奨される復旧手順を順番に説明します。</span><span class="sxs-lookup"><span data-stu-id="e40d3-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="e40d3-107">アプリケーションの復旧を行う場合HoloLens 2プロセスが異なHoloLens 2の復旧[](https://docs.microsoft.com/hololens/hololens-recovery)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e40d3-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="e40d3-108">この記事では、HoloLens デバイスとソフトウェアについて重点的に取り上にします。</span><span class="sxs-lookup"><span data-stu-id="e40d3-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="e40d3-109">ホログラムが正しそうに見えない場合は、ホログラムの品質を向上させる要因の詳細については **[、「HoloLens](hololens-environment-considerations.md)** 環境に関する考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e40d3-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="e40d3-110">やり直し</span><span class="sxs-lookup"><span data-stu-id="e40d3-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="e40d3-111">Cortana を使用して安全な再起動を行う</span><span class="sxs-lookup"><span data-stu-id="e40d3-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="e40d3-112">HoloLens を再起動する最も安全な方法は Cortana を使用する方法です。これは、通常、HoloLens で問題が発生した場合に最初に試す方法です。</span><span class="sxs-lookup"><span data-stu-id="e40d3-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="e40d3-113">Cortana は、すべてのデバイスで使用できるとは言えす。</span><span class="sxs-lookup"><span data-stu-id="e40d3-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="e40d3-114">Cortana は、すべての HoloLens (第 1 世代) デバイスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e40d3-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="e40d3-115">Cortana は、Windows Holograpic バージョン 2004 更新プログラムより前のビルドHoloLens 2デバイスで利用できます。</span><span class="sxs-lookup"><span data-stu-id="e40d3-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="e40d3-116">HoloLens を有効にする。</span><span class="sxs-lookup"><span data-stu-id="e40d3-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="e40d3-117">ユーザーがログインし、デバイスがパスワードのロック解除を待機していない状態にしてください。</span><span class="sxs-lookup"><span data-stu-id="e40d3-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="e40d3-118">"Hey Cortana, reboot" または "Hey Cortana, restart" と言います。</span><span class="sxs-lookup"><span data-stu-id="e40d3-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="e40d3-119">Cortana が応答し、確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e40d3-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="e40d3-120">質問の後にサウンドが再生されるのを待ち、"はい" と言います。</span><span class="sxs-lookup"><span data-stu-id="e40d3-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="e40d3-121">デバイスが再起動します。</span><span class="sxs-lookup"><span data-stu-id="e40d3-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="e40d3-122">[電源] ボタンを使用して安全に再起動する</span><span class="sxs-lookup"><span data-stu-id="e40d3-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="e40d3-123">それでもデバイスを再起動できない場合は、 **電源** ボタンを使用してデバイスを再起動してみてください。</span><span class="sxs-lookup"><span data-stu-id="e40d3-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="e40d3-124">5秒間、 **電源** ボタンを押したままにします。</span><span class="sxs-lookup"><span data-stu-id="e40d3-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="e40d3-125">1秒後に、5つのすべての Led が点灯し、右から左に1ずつ徐々にオフになります。</span><span class="sxs-lookup"><span data-stu-id="e40d3-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="e40d3-126">5秒後、すべての Led はオフになり、正常にシャットダウンされたことを示します。</span><span class="sxs-lookup"><span data-stu-id="e40d3-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="e40d3-127">すべての Led がオフになった直後にボタンを押すのを止めます。</span><span class="sxs-lookup"><span data-stu-id="e40d3-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="e40d3-128">シャットダウンが完了するまで1分待ちます。</span><span class="sxs-lookup"><span data-stu-id="e40d3-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="e40d3-129">ディスプレイがオフになった後も、シャットダウンが進行中である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e40d3-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="e40d3-130">1秒間、電源ボタンを押したままデバイスの **電源** を再度オンにします。</span><span class="sxs-lookup"><span data-stu-id="e40d3-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="e40d3-131">Windows デバイスポータルを使用して安全に再起動する</span><span class="sxs-lookup"><span data-stu-id="e40d3-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="e40d3-132">このプロセスでは、HoloLens を開発者デバイスとして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e40d3-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="e40d3-133">詳細については、「 [Windows デバイスポータル](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e40d3-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="e40d3-134">前の手順が機能しなかった場合は、 [Windows デバイスポータル](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)を使用してデバイスを再起動してみてください。</span><span class="sxs-lookup"><span data-stu-id="e40d3-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="e40d3-135">右上隅で、デバイスを再起動またはシャットダウンするオプションを見つけます。</span><span class="sxs-lookup"><span data-stu-id="e40d3-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="e40d3-136">安全でない強制再起動の実行</span><span class="sxs-lookup"><span data-stu-id="e40d3-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="e40d3-137">前の方法で HoloLens を再起動しなかった場合は、強制的に再起動します。</span><span class="sxs-lookup"><span data-stu-id="e40d3-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="e40d3-138">この方法は、バッテリを取り外して再インストールすることと同じです。</span><span class="sxs-lookup"><span data-stu-id="e40d3-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="e40d3-139">デバイスが破損した状態のままになる可能性があるため、危険です。</span><span class="sxs-lookup"><span data-stu-id="e40d3-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="e40d3-140">そのような場合は、HoloLens をフラッシュする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e40d3-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="e40d3-141">これは有害な可能性があるメソッドであり、前述のメソッドが機能しなかった場合にのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="e40d3-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="e40d3-142">電源ボタンを **少なくとも** 10 秒間長押しします。</span><span class="sxs-lookup"><span data-stu-id="e40d3-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="e40d3-143">ボタンを 10 秒以上保持しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="e40d3-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="e40d3-144">LED アクティビティは無視しても安全です。</span><span class="sxs-lookup"><span data-stu-id="e40d3-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="e40d3-145">ボタンを離し、2 ~ 3 秒待ちます。</span><span class="sxs-lookup"><span data-stu-id="e40d3-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="e40d3-146">電源ボタンを **1** 秒間長押しします。</span><span class="sxs-lookup"><span data-stu-id="e40d3-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="e40d3-147">それでも問題が解決しない場合は、電源ボタンを 4 秒間押します。すべてのバッテリ インジケーターがフェードアウトし、画面にホログラムが表示されなくなってきます。</span><span class="sxs-lookup"><span data-stu-id="e40d3-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="e40d3-148">1 分待った後、もう一度電源ボタン **を** 押してデバイスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e40d3-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="e40d3-149">出荷時の設定にリセットする</span><span class="sxs-lookup"><span data-stu-id="e40d3-149">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="e40d3-150">バッテリをリセットするには、少なくとも 40% の充電が必要です。</span><span class="sxs-lookup"><span data-stu-id="e40d3-150">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="e40d3-151">HoloLens に問題がある場合は、出荷時の状態にリセットしてみてください。</span><span class="sxs-lookup"><span data-stu-id="e40d3-151">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="e40d3-152">この手順では、インストールされている Windows Holographic ソフトウェアのバージョンを保持し、それ以外のすべてを出荷時の設定に返します。</span><span class="sxs-lookup"><span data-stu-id="e40d3-152">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="e40d3-153">デバイスをリセットすると、TPM リセット情報を含むすべての個人データ、アプリ、および設定が消去されます。</span><span class="sxs-lookup"><span data-stu-id="e40d3-153">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="e40d3-154">リセットでは、インストールされている最新バージョンの Windows Holographic だけがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e40d3-154">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="e40d3-155">すべての初期化手順をやり直す必要があります (調整、Wi-Fi への接続、ユーザー アカウントの作成、アプリのダウンロードなど)。</span><span class="sxs-lookup"><span data-stu-id="e40d3-155">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="e40d3-156">[設定] アプリを開き、[回復の更新]**を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e40d3-156">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="e40d3-157">[デバイスの **リセット] オプションを** 選択し、確認メッセージを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="e40d3-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="e40d3-158">リセットを確認します。</span><span class="sxs-lookup"><span data-stu-id="e40d3-158">Confirm the reset.</span></span> <span data-ttu-id="e40d3-159">デバイスが再起動し、一連の回転する歯車と進行状況バーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e40d3-159">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="e40d3-160">このプロセスが完了するまで約 30 分待ちます。</span><span class="sxs-lookup"><span data-stu-id="e40d3-160">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="e40d3-161">完了すると、デバイスは "Out-of-the-box" エクスペリエンスに再起動されます。</span><span class="sxs-lookup"><span data-stu-id="e40d3-161">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="e40d3-162">オペレーティングシステムを再インストールする</span><span class="sxs-lookup"><span data-stu-id="e40d3-162">Reinstall the operating system</span></span>

<span data-ttu-id="e40d3-163">再起動およびリセット後もデバイスに問題が発生する場合は、コンピューターで回復ツールを使用して、HoloLens オペレーティングシステムとファームウェアを再インストールできます。</span><span class="sxs-lookup"><span data-stu-id="e40d3-163">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="e40d3-164">HoloLens がリセットに必要とするデータは完全な Flash 更新プログラム (FFU) にパッケージ化されています。これは、.iso、.wim、.vhd ファイルに似ています。</span><span class="sxs-lookup"><span data-stu-id="e40d3-164">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="e40d3-165">FFU イメージファイル形式について説明します。</span><span class="sxs-lookup"><span data-stu-id="e40d3-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="e40d3-166">Windows デバイスの回復ツールを使用して、HoloLens (第1世代) に新しいオペレーティングシステムをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="e40d3-166">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="e40d3-167">このツールを使用する前に、「HoloLens を再起動またはリセットすると問題が修正される」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e40d3-167">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="e40d3-168">回復プロセスには時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="e40d3-168">The recovery process may take a while.</span></span> <span data-ttu-id="e40d3-169">完了すると、最新バージョンの Windows Holographic ソフトウェアがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e40d3-169">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="e40d3-170">このツールを使用するには、少なくとも 4 GB の空き領域がある Windows 10 以降を実行しているコンピューターが必要です。</span><span class="sxs-lookup"><span data-stu-id="e40d3-170">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="e40d3-171">仮想マシンでこのツールを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="e40d3-171">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="e40d3-172">HoloLens を回復する</span><span class="sxs-lookup"><span data-stu-id="e40d3-172">Recover your HoloLens</span></span>

1. <span data-ttu-id="e40d3-173">[Windows デバイス回復ツール](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)をコンピューターにダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="e40d3-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="e40d3-174">Hololens に付属しているマイクロ USB ケーブルを使用して、HoloLens をコンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="e40d3-174">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="e40d3-175">Windows デバイスの回復ツールを開き、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="e40d3-175">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="e40d3-176">HoloLens (第1世代) が自動的に検出されなかった場合は、[ **デバイスが検出されませんでした**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e40d3-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="e40d3-177">次に、指示に従って、デバイスを回復モードにします。</span><span class="sxs-lookup"><span data-stu-id="e40d3-177">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="e40d3-178">手動フラッシュモード</span><span class="sxs-lookup"><span data-stu-id="e40d3-178">Manual flashing mode</span></span>

<span data-ttu-id="e40d3-179">デバイスが検出されない場合は、次の手順に従って、フラッシュモードにします。</span><span class="sxs-lookup"><span data-stu-id="e40d3-179">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="e40d3-180">任意の電源からデバイスを取り外します。</span><span class="sxs-lookup"><span data-stu-id="e40d3-180">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="e40d3-181">デバイスがオンになっている場合は、 **電源** ボタンを押したままにすると、完全にオフになります。</span><span class="sxs-lookup"><span data-stu-id="e40d3-181">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="e40d3-182">音量を **上げボタン** を押したまま、電源ボタンを簡単 **にタップ** します。</span><span class="sxs-lookup"><span data-stu-id="e40d3-182">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="e40d3-183">デバイスが起動し、中央の LED のみを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e40d3-183">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="e40d3-184">デバイスを PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="e40d3-184">Plug the device into your PC.</span></span>
4. <span data-ttu-id="e40d3-185">Windows デバイス回復ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="e40d3-185">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="e40d3-186">[**デバイスが検出されない] を選択し\*\*\*\*、[HoloLens] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e40d3-186">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="e40d3-187">指示に従ってデバイスを回復します。</span><span class="sxs-lookup"><span data-stu-id="e40d3-187">Follow the instructions to recover your device.</span></span>
