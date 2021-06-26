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
ms.openlocfilehash: 5963be84a5fbb186c77965d9bbf112713fea8242
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923518"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="d07a4-104">HoloLens の再起動、リセット、または復旧 (第 1 世代)</span><span class="sxs-lookup"><span data-stu-id="d07a4-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="d07a4-105">HoloLens で問題が発生している場合は、再起動またはリセットを試したり、デバイスの回復を使用してデバイスを再フラッシュしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d07a4-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="d07a4-106">この記事では、推奨される復旧手順を順番に説明します。</span><span class="sxs-lookup"><span data-stu-id="d07a4-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="d07a4-107">アプリケーションの復旧を行う場合HoloLens 2プロセスが異なHoloLens 2の復旧[](hololens-recovery.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d07a4-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](hololens-recovery.md), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="d07a4-108">この記事では、HoloLens デバイスとソフトウェアについて重点的に取り上にします。</span><span class="sxs-lookup"><span data-stu-id="d07a4-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="d07a4-109">ホログラムが正しそうに見えない場合は、ホログラムの品質を向上させる要因の詳細については **[、「HoloLens](hololens-environment-considerations.md)** 環境に関する考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d07a4-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="d07a4-110">やり直し</span><span class="sxs-lookup"><span data-stu-id="d07a4-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="d07a4-111">Cortana を使用して安全な再起動を行う</span><span class="sxs-lookup"><span data-stu-id="d07a4-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="d07a4-112">HoloLens を再起動する最も安全な方法は Cortana を使用する方法です。これは、通常、HoloLens で問題が発生した場合に最初に試す方法です。</span><span class="sxs-lookup"><span data-stu-id="d07a4-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="d07a4-113">Cortana は、すべてのデバイスで使用できるとは言えす。</span><span class="sxs-lookup"><span data-stu-id="d07a4-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="d07a4-114">Cortana は、すべての HoloLens (第 1 世代) デバイスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d07a4-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="d07a4-115">Cortana は、Windows Holograpic バージョン 2004 更新プログラムより前のビルドHoloLens 2デバイスで利用できます。</span><span class="sxs-lookup"><span data-stu-id="d07a4-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="d07a4-116">HoloLens を有効にする。</span><span class="sxs-lookup"><span data-stu-id="d07a4-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="d07a4-117">ユーザーがログインし、デバイスがパスワードのロック解除を待機していない状態にしてください。</span><span class="sxs-lookup"><span data-stu-id="d07a4-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="d07a4-118">"Hey Cortana, reboot" または "Hey Cortana, restart" と言います。</span><span class="sxs-lookup"><span data-stu-id="d07a4-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="d07a4-119">Cortana が応答し、確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d07a4-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="d07a4-120">質問の後にサウンドが再生されるのを待ち、"はい" と言います。</span><span class="sxs-lookup"><span data-stu-id="d07a4-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="d07a4-121">デバイスが再起動します。</span><span class="sxs-lookup"><span data-stu-id="d07a4-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="d07a4-122">電源ボタンを使用して安全な再起動を行う</span><span class="sxs-lookup"><span data-stu-id="d07a4-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="d07a4-123">それでもデバイスを再起動できない場合は、電源ボタンを使用して **再起動してみてください。**</span><span class="sxs-lookup"><span data-stu-id="d07a4-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="d07a4-124">電源ボタンを5 秒間長押しします。</span><span class="sxs-lookup"><span data-stu-id="d07a4-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="d07a4-125">1 秒後、5 つの LED すべてが点灯し、右から左に 1 つ 1 つ徐々にオフになります。</span><span class="sxs-lookup"><span data-stu-id="d07a4-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="d07a4-126">5 秒後、すべての LED がオフになります。シャットダウンが成功したことを示します。</span><span class="sxs-lookup"><span data-stu-id="d07a4-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="d07a4-127">すべての LED がオフになった直後に、ボタンの押しを停止します。</span><span class="sxs-lookup"><span data-stu-id="d07a4-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="d07a4-128">シャットダウンが完了するまで 1 分待ちます。</span><span class="sxs-lookup"><span data-stu-id="d07a4-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="d07a4-129">表示をオフにした後でも、シャットダウンは進行中である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d07a4-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="d07a4-130">電源ボタンを 1 秒間長押し **して、デバイス** の電源を再びオンにします。</span><span class="sxs-lookup"><span data-stu-id="d07a4-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="d07a4-131">を使用して安全な再起動を行Windows デバイス ポータル</span><span class="sxs-lookup"><span data-stu-id="d07a4-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="d07a4-132">このプロセスでは、HoloLens を開発者デバイスとして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07a4-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="d07a4-133">詳細については、「 」を[参照Windows デバイス ポータル。](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="d07a4-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="d07a4-134">前の手順で問題が発生した場合は、 を使用してデバイスを[再起動Windows デバイス ポータル。](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="d07a4-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="d07a4-135">右上隅で、デバイスを再起動またはシャットダウンするオプションを探します。</span><span class="sxs-lookup"><span data-stu-id="d07a4-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="d07a4-136">安全でない強制再起動を実行する</span><span class="sxs-lookup"><span data-stu-id="d07a4-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="d07a4-137">前のメソッドで HoloLens が再起動しなかった場合は、強制的に再起動します。</span><span class="sxs-lookup"><span data-stu-id="d07a4-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="d07a4-138">この方法は、バッテリの取り外しと再インストールに相当します。</span><span class="sxs-lookup"><span data-stu-id="d07a4-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="d07a4-139">デバイスが破損した状態になる可能性があるため、危険です。</span><span class="sxs-lookup"><span data-stu-id="d07a4-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="d07a4-140">その場合は、HoloLens をフラッシュする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07a4-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="d07a4-141">これは害を及ぼす可能性のあるメソッドであり、以前に引用したメソッドが機能しなかった場合にのみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07a4-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="d07a4-142">電源ボタンを **少なくとも** 10 秒間長押しします。</span><span class="sxs-lookup"><span data-stu-id="d07a4-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="d07a4-143">ボタンを 10 秒以上保持しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="d07a4-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="d07a4-144">LED アクティビティは無視しても安全です。</span><span class="sxs-lookup"><span data-stu-id="d07a4-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="d07a4-145">ボタンを離し、2 ~ 3 秒待ちます。</span><span class="sxs-lookup"><span data-stu-id="d07a4-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="d07a4-146">電源ボタンを **1** 秒間長押しします。</span><span class="sxs-lookup"><span data-stu-id="d07a4-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="d07a4-147">それでも問題が解決しない場合は、電源ボタンを 4 秒間押します。すべてのバッテリ インジケーターがフェードアウトし、画面にホログラムが表示されなくなってきます。</span><span class="sxs-lookup"><span data-stu-id="d07a4-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="d07a4-148">1 分待った後、もう一度電源ボタン **を** 押してデバイスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d07a4-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="d07a4-149">以前のバージョンに戻る - HoloLens (第 1 世代)</span><span class="sxs-lookup"><span data-stu-id="d07a4-149">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="d07a4-150">場合によっては、以前のバージョンの HoloLens ソフトウェアに戻したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="d07a4-150">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="d07a4-151">これを行うには、Windows デバイス回復ツールを使用して HoloLens を以前のバージョンにリセットします。</span><span class="sxs-lookup"><span data-stu-id="d07a4-151">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="d07a4-152">以前のバージョンに戻って、個人用ファイルと設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="d07a4-152">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="d07a4-153">以前のバージョンの HoloLens 1 に戻る場合は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d07a4-153">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="d07a4-154">PC にスマートフォンや Windows デバイスが接続されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d07a4-154">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="d07a4-155">PC で [、Windows Device Recovery Tool (WDRT) をダウンロードします](https://support.microsoft.com/help/12379)。</span><span class="sxs-lookup"><span data-stu-id="d07a4-155">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="d07a4-156">[HoloLens Anniversary Update 回復パッケージ をダウンロードします](https://aka.ms/hololensrecovery)。</span><span class="sxs-lookup"><span data-stu-id="d07a4-156">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="d07a4-157">ダウンロードが完了したら、エクスプローラーの [**ダウンロード]**  >  **を開きます**。</span><span class="sxs-lookup"><span data-stu-id="d07a4-157">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="d07a4-158">ダウンロードした zip 形式のフォルダーを右クリックし、[すべての抽出] を **選択** して  >  解凍します。</span><span class="sxs-lookup"><span data-stu-id="d07a4-158">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="d07a4-159">付属のマイクロ USB ケーブルを使用して、HoloLens を PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="d07a4-159">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="d07a4-160">(他のケーブルを使用して HoloLens を接続している場合でも、これは最適です)。</span><span class="sxs-lookup"><span data-stu-id="d07a4-160">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="d07a4-161">WDRT によって HoloLens が自動的に検出されます。</span><span class="sxs-lookup"><span data-stu-id="d07a4-161">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="d07a4-162">[新 **しい** Microsoft HoloLens選択します。</span><span class="sxs-lookup"><span data-stu-id="d07a4-162">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="d07a4-163">次の画面で、[手動 **パッケージの** 選択] を選択し、手順 4. で展開したフォルダーに含まれているインストール ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d07a4-163">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="d07a4-164">(拡張子が .ffu のファイルを探します)。</span><span class="sxs-lookup"><span data-stu-id="d07a4-164">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="d07a4-165">[ **ソフトウェアのインストール] を** 選択し、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="d07a4-165">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="d07a4-166">WDRT で HoloLens が検出されない場合は、PC の再起動を試してください。</span><span class="sxs-lookup"><span data-stu-id="d07a4-166">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="d07a4-167">それでも問題が生じなかった場合は、[デバイスが検出されない] を選択し、[Microsoft HoloLens]**を** 選択して、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="d07a4-167">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="d07a4-168">出荷時の設定にリセットする</span><span class="sxs-lookup"><span data-stu-id="d07a4-168">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="d07a4-169">バッテリをリセットするには、少なくとも 40% の充電が必要です。</span><span class="sxs-lookup"><span data-stu-id="d07a4-169">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="d07a4-170">HoloLens に問題がある場合は、出荷時の状態にリセットしてみてください。</span><span class="sxs-lookup"><span data-stu-id="d07a4-170">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="d07a4-171">この手順では、インストールされている Windows Holographic ソフトウェアのバージョンを保持し、それ以外のすべてを出荷時の設定に返します。</span><span class="sxs-lookup"><span data-stu-id="d07a4-171">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="d07a4-172">デバイスをリセットすると、TPM リセット情報を含むすべての個人データ、アプリ、および設定が消去されます。</span><span class="sxs-lookup"><span data-stu-id="d07a4-172">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="d07a4-173">リセットでは、インストールされている最新バージョンの Windows Holographic だけがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d07a4-173">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="d07a4-174">すべての初期化手順をやり直す必要があります (調整、Wi-Fi への接続、ユーザー アカウントの作成、アプリのダウンロードなど)。</span><span class="sxs-lookup"><span data-stu-id="d07a4-174">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="d07a4-175">[設定] アプリを開き、[回復の更新]**を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d07a4-175">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="d07a4-176">[デバイスの **リセット] オプションを** 選択し、確認メッセージを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="d07a4-176">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="d07a4-177">リセットを確認します。</span><span class="sxs-lookup"><span data-stu-id="d07a4-177">Confirm the reset.</span></span> <span data-ttu-id="d07a4-178">デバイスが再起動し、一連の回転する歯車と進行状況バーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d07a4-178">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="d07a4-179">このプロセスが完了するまで約 30 分待ちます。</span><span class="sxs-lookup"><span data-stu-id="d07a4-179">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="d07a4-180">完了すると、デバイスは "Out-of-the-box" エクスペリエンスに再起動されます。</span><span class="sxs-lookup"><span data-stu-id="d07a4-180">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="d07a4-181">オペレーティング システムを再インストールする</span><span class="sxs-lookup"><span data-stu-id="d07a4-181">Reinstall the operating system</span></span>

<span data-ttu-id="d07a4-182">再起動とリセット後もデバイスで問題が解決しない場合は、コンピューターの回復ツールを使用して、HoloLens オペレーティング システムとファームウェアを再インストールできます。</span><span class="sxs-lookup"><span data-stu-id="d07a4-182">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="d07a4-183">HoloLens がリセットに必要なデータは、フル フラッシュ更新 (FFU) にパッケージ化されます。これは、.iso、.wim、または .vhd ファイルに似ています。</span><span class="sxs-lookup"><span data-stu-id="d07a4-183">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="d07a4-184">FFU イメージ ファイル形式について学習します。</span><span class="sxs-lookup"><span data-stu-id="d07a4-184">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="d07a4-185">Windows デバイス回復ツールを使用して、HoloLens (第 1 世代) に新しいオペレーティング システムをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="d07a4-185">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="d07a4-186">このツールを使用する前に、HoloLens の再起動またはリセットによって問題が解決される場合を確認してください。</span><span class="sxs-lookup"><span data-stu-id="d07a4-186">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="d07a4-187">復旧プロセスには時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d07a4-187">The recovery process may take a while.</span></span> <span data-ttu-id="d07a4-188">完了すると、最新バージョンの Windows Holographic ソフトウェアがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d07a4-188">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="d07a4-189">このツールを使用するには、少なくとも 4 GB の空きWindows 10空き領域があるコンピューターが必要です。</span><span class="sxs-lookup"><span data-stu-id="d07a4-189">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="d07a4-190">仮想マシンでこのツールを実行できない。</span><span class="sxs-lookup"><span data-stu-id="d07a4-190">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="d07a4-191">HoloLens を回復する</span><span class="sxs-lookup"><span data-stu-id="d07a4-191">Recover your HoloLens</span></span>

1. <span data-ttu-id="d07a4-192">コンピューターに [Windows Device Recovery ツールをダウンロードして](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) インストールします。</span><span class="sxs-lookup"><span data-stu-id="d07a4-192">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="d07a4-193">HoloLens に付属のマイクロ USB ケーブルを使用して、HoloLens (第 1 世代) をコンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="d07a4-193">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="d07a4-194">Windows デバイス回復ツールを開き、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="d07a4-194">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="d07a4-195">HoloLens (第 1 世代) が自動的に検出されない場合は、[デバイスが検出されません] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d07a4-195">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="d07a4-196">次に、指示に従ってデバイスを回復モードにします。</span><span class="sxs-lookup"><span data-stu-id="d07a4-196">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="d07a4-197">手動フラッシュ モード</span><span class="sxs-lookup"><span data-stu-id="d07a4-197">Manual flashing mode</span></span>

<span data-ttu-id="d07a4-198">デバイスが検出されない場合は、次の手順に従ってフラッシュ モードにします。</span><span class="sxs-lookup"><span data-stu-id="d07a4-198">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="d07a4-199">任意の電源からデバイスを取り外します。</span><span class="sxs-lookup"><span data-stu-id="d07a4-199">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="d07a4-200">デバイスがオンの場合は、電源ボタン **が完全** にオフになるまで押したままにします。</span><span class="sxs-lookup"><span data-stu-id="d07a4-200">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="d07a4-201">[ **音量** ] ボタンを押したまま、[ **電源** ] ボタンを簡単にタップします。</span><span class="sxs-lookup"><span data-stu-id="d07a4-201">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="d07a4-202">デバイスが起動し、中央の LED のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d07a4-202">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="d07a4-203">デバイスを PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="d07a4-203">Plug the device into your PC.</span></span>
4. <span data-ttu-id="d07a4-204">Windows デバイスの回復ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="d07a4-204">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="d07a4-205">[ **デバイスは検出されませんでした** ]、[ **HoloLens**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d07a4-205">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="d07a4-206">指示に従って、デバイスを回復します。</span><span class="sxs-lookup"><span data-stu-id="d07a4-206">Follow the instructions to recover your device.</span></span>
