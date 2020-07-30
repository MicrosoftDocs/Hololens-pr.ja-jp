---
title: HoloLens 1 を再起動、リセット、または回復する
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
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
ms.openlocfilehash: de53f8f2cccfe3ece8900c88c5379adf2fb55a7b
ms.sourcegitcommit: 5d38af8d17dfcc028e7e0b2bb888c6c9d1e40524
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "10899180"
---
# <span data-ttu-id="19d61-104">HoloLens 第 1 世代を再起動、リセット、または回復する</span><span class="sxs-lookup"><span data-stu-id="19d61-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="19d61-105">HoloLens で問題が発生している場合は、再起動、リセット、またはデバイスの回復を伴う更新を試してください。</span><span class="sxs-lookup"><span data-stu-id="19d61-105">If you're experiencing problems with your HoloLens you may want to try a restart, reset, or even re-flash with device recovery.</span></span>

<span data-ttu-id="19d61-106">HoloLens が正常に動作していない場合に試してみることがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="19d61-106">Here are some things to try if your HoloLens isn't running well.</span></span>  <span data-ttu-id="19d61-107">この記事では、推奨される回復手順を順に説明します。</span><span class="sxs-lookup"><span data-stu-id="19d61-107">This article will guide you through the recommended recovery steps in succession.</span></span>

<span data-ttu-id="19d61-108">HoloLens 2 の回復を検討している場合は、プロセスに違いがあるため、[HoloLens 2 の回復](https://docs.microsoft.com/hololens/hololens-recovery)ページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="19d61-108">If you are looking to recover a HoloLens 2, please view the page for [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as there are differences in the processes.</span></span>

<span data-ttu-id="19d61-109">この記事では HoloLens デバイスとソフトウェアに焦点を当てていますが、ホログラムが正しく表示されない場合は、[この記事](hololens-environment-considerations.md)で説明されているホログラムの品質を向上させる環境要因を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19d61-109">This article focuses on the HoloLens device and software, if your holograms don't look right, [this article](hololens-environment-considerations.md) talks about environmental factors that improve hologram quality.</span></span>

## <span data-ttu-id="19d61-110">再起動</span><span class="sxs-lookup"><span data-stu-id="19d61-110">Restart</span></span>

### <span data-ttu-id="19d61-111">Cortana を使用して安全な再起動を実行する</span><span class="sxs-lookup"><span data-stu-id="19d61-111">Perform a safe restart by using Cortana</span></span>

<span data-ttu-id="19d61-112">HoloLens を再起動する最も安全な方法は、Cortana を使用することです。</span><span class="sxs-lookup"><span data-stu-id="19d61-112">The safest way to restart the HoloLens is by using Cortana.</span></span> <span data-ttu-id="19d61-113">これは通常、HoloLens で問題が発生した場合の簡単な最初の手順です。</span><span class="sxs-lookup"><span data-stu-id="19d61-113">This is generally an easy first-step when experiencing an issue with HoloLens.</span></span> 

> [!NOTE]
> <span data-ttu-id="19d61-114">Cortana はすべてのデバイスで利用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="19d61-114">Cortana is not avalible on all devices.</span></span> <span data-ttu-id="19d61-115">Cortana は、すべての HoloLens (第 1 世代) デバイスで利用できます。</span><span class="sxs-lookup"><span data-stu-id="19d61-115">Cortana is avalible to all HoloLens (1st Gen) devices.</span></span>
> <span data-ttu-id="19d61-116">Cortana は、Windows Holograpic バージョン 2004 更新プログラムより前のビルドの HoloLens 2 デバイスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="19d61-116">Cortana is avalible on HoloLens 2 devices on a build prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="19d61-117">デバイスを装着する</span><span class="sxs-lookup"><span data-stu-id="19d61-117">Put on your device</span></span>
1. <span data-ttu-id="19d61-118">電源が入っていること、ユーザーがログインしていること、およびデバイスがパスワードのロックを解除するのを待っていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="19d61-118">Make sure it's powered on, a user is logged in, and the device is not waiting for a password to unlock it.</span></span>
1. <span data-ttu-id="19d61-119">「コルタナさん、再起動して」または「コルタナさん、再起動して」と言います。</span><span class="sxs-lookup"><span data-stu-id="19d61-119">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
1. <span data-ttu-id="19d61-120">Cortana が認識すると、確認を求めます。</span><span class="sxs-lookup"><span data-stu-id="19d61-120">When she acknowledges she will ask you for confirmation.</span></span> <span data-ttu-id="19d61-121">Cortana が質問を終えた後、Cortana が自分の言うことを聞いていることを示す音が鳴るのを少し待ってから、「はい」と言います。</span><span class="sxs-lookup"><span data-stu-id="19d61-121">Wait a second for a sound to play after she has finished her question, indicating she is listening to you and then say "Yes."</span></span>
1. <span data-ttu-id="19d61-122">デバイスが再起動します。</span><span class="sxs-lookup"><span data-stu-id="19d61-122">The device will now restart.</span></span>

### <span data-ttu-id="19d61-123">電源ボタンを使用して安全に再起動する</span><span class="sxs-lookup"><span data-stu-id="19d61-123">Perform a safe restart by using the power button</span></span>

<span data-ttu-id="19d61-124">それでもデバイスを再起動できない場合は、電源ボタンを使用して再起動してみてください。</span><span class="sxs-lookup"><span data-stu-id="19d61-124">If you still can't restart your device, you can try to restart it by using the power button:</span></span>

1. <span data-ttu-id="19d61-125">電源ボタンを 5 秒間押し続けます。</span><span class="sxs-lookup"><span data-stu-id="19d61-125">Press and hold the power button for five seconds.</span></span>
   1. <span data-ttu-id="19d61-126">1 秒後、5 つのすべての LED が点灯してから、右から左にゆっくりと消灯します。</span><span class="sxs-lookup"><span data-stu-id="19d61-126">After one second, you will see all five LEDs illuminate, then slowly turn off from right to left.</span></span>
   1. <span data-ttu-id="19d61-127">5 秒後、すべての LED がオフになり、シャットダウン コマンドが正常に発行されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="19d61-127">After five seconds, all LEDs will be off, indicating the shutdown command was issued successfully.</span></span>
   1. <span data-ttu-id="19d61-128">すべての LED がオフになった直後にボタンを押すのを停止することが重要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="19d61-128">Note that it's important to stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="19d61-129">シャットダウンが完全に成功するまで 1 分間待ちます。</span><span class="sxs-lookup"><span data-stu-id="19d61-129">Wait one minute for the shutdown to cleanly succeed.</span></span> <span data-ttu-id="19d61-130">ディスプレイがオフになっていても、シャットダウンが進行中の場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="19d61-130">Note that the shutdown may still be in progress even if the displays are turned off.</span></span>
1. <span data-ttu-id="19d61-131">電源ボタンを 1 秒間押し続けて、デバイスの電源を再度オンにします。</span><span class="sxs-lookup"><span data-stu-id="19d61-131">Power on the device again by pressing and holding the power button for one second.</span></span>

### <span data-ttu-id="19d61-132">Windows Device Portal を使用して安全な再起動を実行する</span><span class="sxs-lookup"><span data-stu-id="19d61-132">Perform a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="19d61-133">これを行うには、HoloLens を開発者デバイスとして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19d61-133">To do this, HoloLens has to be configured as a developer device.</span></span>  
> <span data-ttu-id="19d61-134">[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) の詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="19d61-134">Read more about [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="19d61-135">前の手順が機能しない場合は、[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) を使用してデバイスを再起動してみてください。</span><span class="sxs-lookup"><span data-stu-id="19d61-135">If the previous procedure doesn't work, you can try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="19d61-136">右上隅に、デバイスを再起動またはシャットダウンするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="19d61-136">In the upper right corner, there is an option to restart or shut down the device.</span></span>

### <span data-ttu-id="19d61-137">安全でない強制再起動を実行する</span><span class="sxs-lookup"><span data-stu-id="19d61-137">Perform an unsafe forced restart</span></span>

<span data-ttu-id="19d61-138">上記のいずれの方法でもデバイスを正常に再起動できない場合は、強制的に再起動できます。</span><span class="sxs-lookup"><span data-stu-id="19d61-138">If none of the previous methods are able to successfully restart your device, you can force a restart.</span></span> <span data-ttu-id="19d61-139">この方法は、HoloLens からバッテリーを取り出すのと同じです。</span><span class="sxs-lookup"><span data-stu-id="19d61-139">This method is equivalent to pulling the battery from the HoloLens.</span></span>  <span data-ttu-id="19d61-140">これは、デバイスを破損する可能性がある危険な操作です。</span><span class="sxs-lookup"><span data-stu-id="19d61-140">It is a dangerous operation which may leave your device in a corrupt state.</span></span>  <span data-ttu-id="19d61-141">その場合は、HoloLens をフラッシュする必要があります。</span><span class="sxs-lookup"><span data-stu-id="19d61-141">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="19d61-142">これは有害な可能性のある方法であり、上記の方法がどれも機能しない場合にのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="19d61-142">This is a potentially harmful method and should only be used in the event none of the above methods work.</span></span>

1. <span data-ttu-id="19d61-143">電源ボタンを 10 秒以上押し続けます。</span><span class="sxs-lookup"><span data-stu-id="19d61-143">Press and hold the power button for at least 10 seconds.</span></span>
   - <span data-ttu-id="19d61-144">ボタンを 10 秒以上押しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="19d61-144">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="19d61-145">LED アクティビティを無視しても安全です。</span><span class="sxs-lookup"><span data-stu-id="19d61-145">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="19d61-146">ボタンを離し、2 ~ 3 秒待ちます。</span><span class="sxs-lookup"><span data-stu-id="19d61-146">Release the button and wait for two or three seconds.</span></span>
1. <span data-ttu-id="19d61-147">電源ボタンを 1 秒間押し続けて、デバイスの電源を再度オンにします。</span><span class="sxs-lookup"><span data-stu-id="19d61-147">Power on the device again by pressing and holding the power button for one second.</span></span>
<span data-ttu-id="19d61-148">それでも問題が解決しない場合は、すべてのバッテリー インジケーターが消え、画面にホログラムが表示されなくなるまで、電源ボタンを 4 秒間押します。</span><span class="sxs-lookup"><span data-stu-id="19d61-148">If you're still having problems, press the power button for 4 seconds, until all of the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="19d61-149">1 分間待ってから、もう一度電源ボタンを押してデバイスの電源を入れます。</span><span class="sxs-lookup"><span data-stu-id="19d61-149">Wait 1 minute, then press the power button again to turn on the device.</span></span>

## <span data-ttu-id="19d61-150">工場出荷時の設定にリセット</span><span class="sxs-lookup"><span data-stu-id="19d61-150">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="19d61-151">リセットするには、バッテリーを最低 40% 充電する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19d61-151">The battery needs at least 40 percent charge to reset.</span></span>

<span data-ttu-id="19d61-152">再起動後も HoloLens に問題が発生する場合は、HoloLens を出荷時の状態にリセットしてみてください。</span><span class="sxs-lookup"><span data-stu-id="19d61-152">If your HoloLens is still experiencing issues after restarting, try resetting it to factory state.</span></span>  <span data-ttu-id="19d61-153">HoloLens をリセットすると、HoloLens にインストールされている Windows Holographic ソフトウェアのバージョンが保持され、それ以外はすべて工場出荷時の設定に戻ります。</span><span class="sxs-lookup"><span data-stu-id="19d61-153">Resetting your HoloLens keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

<span data-ttu-id="19d61-154">デバイスをリセットすると、TPM リセットを含むすべての個人データ、アプリ、設定が消去されます。</span><span class="sxs-lookup"><span data-stu-id="19d61-154">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset.</span></span> <span data-ttu-id="19d61-155">リセットすると、インストールされている最新バージョンの Windows Holographic のみがインストールされ、すべての初期化手順 (調整、Wi-Fi への接続、ユーザー アカウントの作成、アプリのダウンロードなど) をやり直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="19d61-155">Resetting will only install the latest installed version of Windows Holographic and you will have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so forth).</span></span>

1. <span data-ttu-id="19d61-156">設定アプリを起動し、**[更新]** > **[回復]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="19d61-156">Launch the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="19d61-157">[**デバイスのリセット**] オプションを選択し、確認メッセージを読みます。</span><span class="sxs-lookup"><span data-stu-id="19d61-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="19d61-158">デバイスをリセットすることに同意すると、デバイスが再起動し、プログレス バー付きの回転するギアのセットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19d61-158">If you agree to reset your device, the device will restart and display a set of spinning gears with a progress bar.</span></span>
1. <span data-ttu-id="19d61-159">このプロセスが完了するまで約 30 分待ちます。</span><span class="sxs-lookup"><span data-stu-id="19d61-159">Wait about 30 minutes for this process to complete.</span></span>
1. <span data-ttu-id="19d61-160">リセットが完了し、デバイスはすぐに使用可能な状態で再起動します。</span><span class="sxs-lookup"><span data-stu-id="19d61-160">The reset will complete and the device will restart into the out-of-the-box experience.</span></span>

## <span data-ttu-id="19d61-161">オペレーティング システムを再インストールする</span><span class="sxs-lookup"><span data-stu-id="19d61-161">Re-install the operating system</span></span>

<span data-ttu-id="19d61-162">再起動してリセットした後もデバイスに問題がある場合は、コンピューターの回復ツールを使用して、HoloLens のオペレーティング システムとファームウェアを再インストールできます。</span><span class="sxs-lookup"><span data-stu-id="19d61-162">If the device is still having a problem after rebooting and resetting, you can use a recovery tool on your computer to reinstall the HoloLens' operating system and firmware.</span></span>  

<span data-ttu-id="19d61-163">HoloLens がリセットする必要があるすべてのデータは、Full Flash Update (ffu) にパッケージ化されています。</span><span class="sxs-lookup"><span data-stu-id="19d61-163">All of the data HoloLens needs to reset is packaged in a Full Flash Update (ffu).</span></span>  <span data-ttu-id="19d61-164">これは、iso、wim、または vhd に似ています。</span><span class="sxs-lookup"><span data-stu-id="19d61-164">This is similar to an iso, wim, or vhd.</span></span>  [<span data-ttu-id="19d61-165">FFU 画像ファイル形式について学習します。</span><span class="sxs-lookup"><span data-stu-id="19d61-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="19d61-166">必要に応じて、Windows Device Recovery Tool を使用して、HoloLens (第 1 世代) に完全に新しいオペレーティング システムをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="19d61-166">If necessary, you can install a completely new operating system on your HoloLens (1st gen) with the Windows Device Recovery Tool.</span></span>

<span data-ttu-id="19d61-167">このツールを使用する前に、HoloLens を再起動またはリセットすると問題が解決するかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="19d61-167">Before you use this tool, determine if restarting or resetting your HoloLens fixes the problem.</span></span> <span data-ttu-id="19d61-168">回復プロセスには時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="19d61-168">The recovery process may take some time.</span></span>  <span data-ttu-id="19d61-169">完了すると、HoloLens に承認された Windows Holographic ソフトウェアの最新バージョンがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="19d61-169">When you're done, the latest version of the Windows Holographic software approved for your HoloLens will be installed.</span></span>

<span data-ttu-id="19d61-170">このツールを使用するには、Windows 10 以降を実行し、4 GB 以上の空き容量があるコンピューターが必要です。</span><span class="sxs-lookup"><span data-stu-id="19d61-170">To use the tool, you'll need a computer running Windows 10 or later, with at least 4 GB of free storage space.</span></span>  <span data-ttu-id="19d61-171">このツールは仮想マシンでは実行できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="19d61-171">Please note that you can't run this tool on a virtual machine.</span></span>

### <span data-ttu-id="19d61-172">HoloLens を回復する:</span><span class="sxs-lookup"><span data-stu-id="19d61-172">Recover your HoloLens:</span></span>

1. <span data-ttu-id="19d61-173">コンピューターに [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="19d61-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="19d61-174">HoloLens に付属の Micro USB ケーブルを使用して、HoloLens (第 1 世代) をコンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="19d61-174">Connect the HoloLens (1st gen) to your computer using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="19d61-175">Windows Device Recovery Tool を実行し、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="19d61-175">Run the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="19d61-176">HoloLens (第 1 世代) が自動的に検出されない場合は、[**デバイスが検出されませんでした**] を選択し、指示に従ってデバイスを回復モードにします。</span><span class="sxs-lookup"><span data-stu-id="19d61-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected** and follow the instructions to put your device into recovery mode.</span></span>

### <span data-ttu-id="19d61-177">手動フラッシュ モード:</span><span class="sxs-lookup"><span data-stu-id="19d61-177">Manual Flashing Mode:</span></span>

<span data-ttu-id="19d61-178">デバイスが検出されない場合は、次の方法を使用して手動でデバイスをフラッシュ モードにしてください。</span><span class="sxs-lookup"><span data-stu-id="19d61-178">In the event that your device is not being detected please use the following method to manually place it into flashing mode.</span></span>

1. <span data-ttu-id="19d61-179">すべての電源からデバイスを取り外します。</span><span class="sxs-lookup"><span data-stu-id="19d61-179">Unplug the device from all power sources.</span></span>
1. <span data-ttu-id="19d61-180">デバイスがオンになっている場合は、完全にオフになるまで電源ボタンを押し続けてください。</span><span class="sxs-lookup"><span data-stu-id="19d61-180">If the device is on please hold down the power button until it is completely off.</span></span>
1. <span data-ttu-id="19d61-181">[**音量を上げる**] ボタンを押したまま、**電源ボタン**を軽くタップします。</span><span class="sxs-lookup"><span data-stu-id="19d61-181">Hold the **Volume Up** button, and briefly tap the **Power button**.</span></span> 
1. <span data-ttu-id="19d61-182">デバイスが起動し、中央の LED ライトのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19d61-182">The device should boot and then display only the middle LED light.</span></span>
1. <span data-ttu-id="19d61-183">デバイスを PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="19d61-183">Plug the device into your PC.</span></span>
1. <span data-ttu-id="19d61-184">Windows Device Recovery Tool を起動します。</span><span class="sxs-lookup"><span data-stu-id="19d61-184">Launch Windows Device Recovery Tool.</span></span>
1. <span data-ttu-id="19d61-185">[*デバイスが検出されませんでした**] を選択し、**HoloLens*\* を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19d61-185">You will need to select \*My device was not detected\*\*, and then select **HoloLens**.</span></span> 
1. <span data-ttu-id="19d61-186">指示に従ってデバイスを回復します。</span><span class="sxs-lookup"><span data-stu-id="19d61-186">Follow the instructions to recover your device.</span></span>
