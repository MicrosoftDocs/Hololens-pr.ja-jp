---
title: HoloLens 1 を再起動、リセット、または回復する
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Windows Device Recovery Tool を使用して HoloLens 第 1 世代に画像をフラッシュする方法。
keywords: ハウツー、再起動、リセット、回復、ハード リセット、ソフト リセット、電源サイクル、HoloLens、シャットダウン、wdrt、windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f0aa400be56d09a843a1b7c9bae78346551ad8af
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283918"
---
# <span data-ttu-id="a9daa-104">HoloLens 第 1 世代を再起動、リセット、または回復する</span><span class="sxs-lookup"><span data-stu-id="a9daa-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="a9daa-105">HoloLens で問題が発生している場合は、再起動、リセット、またはデバイスの回復を使用してデバイスを再フラッシュしてみてください。</span><span class="sxs-lookup"><span data-stu-id="a9daa-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="a9daa-106">この記事では、推奨される回復手順を順に説明します。</span><span class="sxs-lookup"><span data-stu-id="a9daa-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="a9daa-107">HoloLens 2 を復元したい場合は、プロセスが異なるので [RHoloLens 2 を回復させる方法](https://docs.microsoft.com/hololens/hololens-recovery) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9daa-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="a9daa-108">この記事では、HoloLens デバイスとソフトウェアに焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="a9daa-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="a9daa-109">ホログラムが正しく表示されない場合、ホログラムの品質を改善する要因の詳細については、「**[HoloLens 環境の考慮事項](hololens-environment-considerations.md)**」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9daa-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <span data-ttu-id="a9daa-110">再起動</span><span class="sxs-lookup"><span data-stu-id="a9daa-110">Restart</span></span>

### <span data-ttu-id="a9daa-111">Cortana を使用して安全に再起動する</span><span class="sxs-lookup"><span data-stu-id="a9daa-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="a9daa-112">HoloLens を再起動する最も安全な方法は、Cortana を使用することであり、通常、HoloLens に問題が発生した場合に最初に試みることになります。</span><span class="sxs-lookup"><span data-stu-id="a9daa-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="a9daa-113">Cortana はすべてのデバイスで利用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="a9daa-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="a9daa-114">Cortana は、すべての HoloLens (第 1 世代) デバイスで利用できます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="a9daa-115">Cortana は、Windows Holograpic バージョン 2004 更新プログラムより前のビルドの HoloLens 2 デバイスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="a9daa-116">HoloLens の電源を入れます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="a9daa-117">ユーザーがログインしていること、およびデバイスがパスワードのロックを解除するのを待っていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a9daa-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="a9daa-118">「コルタナさん、再起動して」または「コルタナさん、再起動して」と言います。</span><span class="sxs-lookup"><span data-stu-id="a9daa-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="a9daa-119">Cortana が反応し、確認を求めます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="a9daa-120">質問の後に音が鳴るのを待ってから、"はい" と音声で指示します。</span><span class="sxs-lookup"><span data-stu-id="a9daa-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="a9daa-121">デバイスが再起動します。</span><span class="sxs-lookup"><span data-stu-id="a9daa-121">The device will restart.</span></span>

### <span data-ttu-id="a9daa-122">電源ボタンを使って安全に再起動する</span><span class="sxs-lookup"><span data-stu-id="a9daa-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="a9daa-123">それでもデバイスを再起動できない場合は、**電源** ボタンを使用して再起動してみてください。</span><span class="sxs-lookup"><span data-stu-id="a9daa-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="a9daa-124">**電源ボタン**を 5 秒間押し続けます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="a9daa-125">1 秒後に 5 個の Led がすべて点灯してから、1 つずつ右から左にゆっくりと消灯していきます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="a9daa-126">5 秒後にすべての Led が消灯し、正常にシャットダウンされたことが示されます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="a9daa-127">すべての LED が消灯した直後にすぐボタンを押すのはやめてください。</span><span class="sxs-lookup"><span data-stu-id="a9daa-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="a9daa-128">完全にシャットダウンされるまで 1 分待ちます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="a9daa-129">ディスプレイが消灯した後もシャットダウンが進行中の場合があります。</span><span class="sxs-lookup"><span data-stu-id="a9daa-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="a9daa-130">**電源** ボタンを 1 秒間押し続けて、デバイスの電源を再度オンにします。</span><span class="sxs-lookup"><span data-stu-id="a9daa-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <span data-ttu-id="a9daa-131">Windows デバイス ポータルを使用して安全な再起動を行う</span><span class="sxs-lookup"><span data-stu-id="a9daa-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="a9daa-132">これを行うには、HoloLens を開発者デバイスとして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9daa-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="a9daa-133">詳細については、[Windows デバイス ポータル](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="a9daa-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="a9daa-134">前の手順が機能しない場合は、[Windows デバイス ポータル](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) を使用してデバイスを再起動してみてください。</span><span class="sxs-lookup"><span data-stu-id="a9daa-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="a9daa-135">右上隅に、デバイスを再起動またはシャットダウンするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="a9daa-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <span data-ttu-id="a9daa-136">安全でない強制再起動を行う</span><span class="sxs-lookup"><span data-stu-id="a9daa-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="a9daa-137">前の方法でも HoloLens が再起動しない場合は、強制的に再起動させます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="a9daa-138">この方法は、バッテリーを取り出して再インストールするのと同じです。</span><span class="sxs-lookup"><span data-stu-id="a9daa-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="a9daa-139">デバイスが破損する可能性があるため、危険です。</span><span class="sxs-lookup"><span data-stu-id="a9daa-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="a9daa-140">その場合は、HoloLens をフラッシュする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9daa-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="a9daa-141">これは害を及ぼす可能性のある方法であり、これまでに紹介した方法がどれも機能しない場合にのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="a9daa-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="a9daa-142">**電源** ボタンを 10 秒以上押し続けます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="a9daa-143">ボタンを 10 秒以上押しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="a9daa-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="a9daa-144">LED アクティビティを無視しても安全です。</span><span class="sxs-lookup"><span data-stu-id="a9daa-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="a9daa-145">ボタンを離し、2 ~ 3 秒待ちます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="a9daa-146">**電源** ボタンを 1 秒間押し続けます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="a9daa-147">それでも問題が解決しない場合は、すべてのバッテリー インジケーターが消え、画面にホログラムが表示されなくなるまで、**電源** ボタンを 4 秒間押します。</span><span class="sxs-lookup"><span data-stu-id="a9daa-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="a9daa-148">1 分間待ってから、もう一度 **電源** ボタンを押してデバイスの電源を入れます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <span data-ttu-id="a9daa-149">工場出荷時の設定にリセット</span><span class="sxs-lookup"><span data-stu-id="a9daa-149">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="a9daa-150">リセットするには、バッテリーを最低 40% 充電する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9daa-150">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="a9daa-151">HoloLens にまだ問題がある場合は、それを工場出荷時の状態に再設定してみてください。</span><span class="sxs-lookup"><span data-stu-id="a9daa-151">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="a9daa-152">この手順により、HoloLens にインストールされている Windows Holographic ソフトウェアのバージョンが保持され、それ以外はすべて工場出荷時の設定に戻ります。</span><span class="sxs-lookup"><span data-stu-id="a9daa-152">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="a9daa-153">デバイスをリセットすると、TPM リセットを含むすべての個人データ、アプリ、設定が消去されます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-153">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="a9daa-154">リセットすると、最後にインストールされたバージョンの Windows Holographic のみがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-154">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="a9daa-155">すべての初期設定 （調整、Wi-Fi への接続、ユーザー アカウントの作成、アプリのダウンロードなど） をやり直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9daa-155">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="a9daa-156">設定アプリを起動し、[**更新**] > [**回復**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a9daa-156">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="a9daa-157">[**デバイスのリセット**] オプションを選択し、確認メッセージを読みます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="a9daa-158">リセットを確認します。</span><span class="sxs-lookup"><span data-stu-id="a9daa-158">Confirm the reset.</span></span> <span data-ttu-id="a9daa-159">デバイスが再起動し、回転する歯車とプログレス バーのセットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-159">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="a9daa-160">このプロセスが完了するまで約 30 分待ちます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-160">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="a9daa-161">リセットが完了し、デバイスは 「すぐに使用可能」 な状態で再起動します。</span><span class="sxs-lookup"><span data-stu-id="a9daa-161">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <span data-ttu-id="a9daa-162">オペレーティング システムを再インストールする</span><span class="sxs-lookup"><span data-stu-id="a9daa-162">Reinstall the operating system</span></span>

<span data-ttu-id="a9daa-163">再起動してリセットした後もデバイスに問題がある場合は、コンピューターの回復ツールを使用して、HoloLens のオペレーティング システムとファームウェアを再インストールできます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-163">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="a9daa-164">HoloLens がリセットに必要とするデータは、.iso、.wim、または .vhd ファイルに似たフル フラッシュ アップデート （FFU） にパッケージ化されています。</span><span class="sxs-lookup"><span data-stu-id="a9daa-164">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="a9daa-165">FFU 画像ファイル形式について学習します。</span><span class="sxs-lookup"><span data-stu-id="a9daa-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="a9daa-166">Windows Device Recovery Tool を使用して、HoloLens (第 1 世代) に新しいオペレーティング システムをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-166">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="a9daa-167">このツールを使用する前に、HoloLens を再起動またはリセットすると問題が解決するかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a9daa-167">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="a9daa-168">回復プロセスには時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a9daa-168">The recovery process may take a while.</span></span> <span data-ttu-id="a9daa-169">完了すると、Windows Holographic ソフトウェアの最新バージョンがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-169">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="a9daa-170">このツールを使用するには、Windows 10 以降を実行し、4 GB 以上の空き容量があるコンピューターが必要です。</span><span class="sxs-lookup"><span data-stu-id="a9daa-170">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="a9daa-171">このツールを仮想マシンで実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="a9daa-171">You can't run this tool on a virtual machine.</span></span>

### <span data-ttu-id="a9daa-172">HoloLens を回復する</span><span class="sxs-lookup"><span data-stu-id="a9daa-172">Recover your HoloLens</span></span>

1. <span data-ttu-id="a9daa-173">コンピューターに [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="a9daa-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="a9daa-174">HoloLens に付属の Micro USB ケーブルを使用して、HoloLens (第 1 世代) をコンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="a9daa-174">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="a9daa-175">Windows Device Recovery Tool を開き、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="a9daa-175">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="a9daa-176">HoloLens (1 番目の世代) が自動的に検出されない場合は、[**デバイスが検出されませんでした**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="a9daa-177">次に、指示に従ってデバイスを回復モードにします。</span><span class="sxs-lookup"><span data-stu-id="a9daa-177">Then follow the instructions to put the device into recovery mode.</span></span>

### <span data-ttu-id="a9daa-178">手動フラッシュ モード</span><span class="sxs-lookup"><span data-stu-id="a9daa-178">Manual flashing mode</span></span>

<span data-ttu-id="a9daa-179">デバイスが検出されない場合は、次の手順に従って、フラッシュ モードにします。</span><span class="sxs-lookup"><span data-stu-id="a9daa-179">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="a9daa-180">すべての電源からデバイスを取り外します。</span><span class="sxs-lookup"><span data-stu-id="a9daa-180">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="a9daa-181">デバイスがオンになっている場合は、完全にオフになるまで **電源** ボタンを押し続けてください。</span><span class="sxs-lookup"><span data-stu-id="a9daa-181">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="a9daa-182">[**音量を上げる**] ボタンを押したまま、**電源** ボタンを軽くタップします。</span><span class="sxs-lookup"><span data-stu-id="a9daa-182">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="a9daa-183">デバイスが起動し、中央の LED ライトのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-183">The device should start and display only the middle LED light.</span></span>
3. <span data-ttu-id="a9daa-184">デバイスを PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="a9daa-184">Plug the device into your PC.</span></span>
4. <span data-ttu-id="a9daa-185">Windows Device Recovery Tool を開きます。</span><span class="sxs-lookup"><span data-stu-id="a9daa-185">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="a9daa-186">[**デバイスが検出されませんでした**]、**HoloLens** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a9daa-186">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="a9daa-187">指示に従ってデバイスを回復します。</span><span class="sxs-lookup"><span data-stu-id="a9daa-187">Follow the instructions to recover your device.</span></span>
