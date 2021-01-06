---
title: HoloLens を再起動、リセット、または回復する
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
description: 高度な回復コンパニオンを使用してイメージを HoloLens 2 にフラッシュする方法。
keywords: ハウツー、再起動、リセット、回復、ハード リセット、ソフト リセット、電源サイクル、HoloLens、シャットダウン、アーク、高度な回復コンパニオン
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
ms.openlocfilehash: ad162d1f415430e22e683280089cacf2e1cef02a
ms.sourcegitcommit: 3827d244426ffecb517f6cfa714eeef9363c062d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "11253583"
---
# <span data-ttu-id="744de-104">HoloLens 2 を再起動、リセット、または回復する</span><span class="sxs-lookup"><span data-stu-id="744de-104">Restart, reset, or recover HoloLens 2</span></span>

## <span data-ttu-id="744de-105">デバイスを充電する</span><span class="sxs-lookup"><span data-stu-id="744de-105">Charge the device</span></span>

<span data-ttu-id="744de-106">トラブルシューティングの手順を開始する前に、可能であれば、デバイスがバッテリ容量の 20 - 40% に充電されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="744de-106">Before you start any troubleshooting procedure, make sure that your device is charged to 20 to 40 percent of battery capacity if possible.</span></span> <span data-ttu-id="744de-107">HoloLens 2 デバイスに付属の充電器と USB Type-C ケーブルを使用します。</span><span class="sxs-lookup"><span data-stu-id="744de-107">Use the charger and the USB Type-C cables that come with the HoloLens 2 device.</span></span> <span data-ttu-id="744de-108">デバイスに付属している電源アダプターと USB-C-C ケーブルは、HoloLens 2 を充電する最適な方法です。</span><span class="sxs-lookup"><span data-stu-id="744de-108">The power supply and USB-C-to-C cable that come with the device are the best way to charge your HoloLens 2.</span></span> <span data-ttu-id="744de-109">充電器は、18W の電力 (2A で 9V) を供給します。</span><span class="sxs-lookup"><span data-stu-id="744de-109">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="744de-110">付属のプラグを使用すると、HoloLens 2 デバイスは、デバイスがスタンバイ状態のときに 65 分未満でバッテリーを完全に充電できます。</span><span class="sxs-lookup"><span data-stu-id="744de-110">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="744de-111">これらのアクセサリが使用できない場合は、使用可能な充電器が少なくとも 15W の電力に対応していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="744de-111">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="744de-112">可能であれば、PC を使用してデバイスを USB 経由で充電することは避けてください。これは遅いです。</span><span class="sxs-lookup"><span data-stu-id="744de-112">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="744de-113">デバイスが正常に起動し、動作している場合は、次の 3 つの方法でバッテリの充電レベルを確認できます。</span><span class="sxs-lookup"><span data-stu-id="744de-113">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="744de-114">HoloLens デバイス UI のメイン メニューから。</span><span class="sxs-lookup"><span data-stu-id="744de-114">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="744de-115">電源ボタンの近くにある LED を確認します (40% が充電されている場合、少なくとも 2 つの点灯した LED が見えるはずです)。</span><span class="sxs-lookup"><span data-stu-id="744de-115">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDS).</span></span>
    - <span data-ttu-id="744de-116">デバイスの充電中は、バッテリー インジケーターが点灯し、現在の充電レベルを示します。</span><span class="sxs-lookup"><span data-stu-id="744de-116">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="744de-117">最後のライトはゆっくりと点滅し、充電中であることを示します。</span><span class="sxs-lookup"><span data-stu-id="744de-117">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="744de-118">HoloLens の電源が入っているときは、バッテリー インジケーターにバッテリー レベルが 5 段階的で表示されます。</span><span class="sxs-lookup"><span data-stu-id="744de-118">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="744de-119">5 個のライトのうち 1 個しか点灯していない場合は、バッテリー レベルが 20 パーセントを下回っています。</span><span class="sxs-lookup"><span data-stu-id="744de-119">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="744de-120">バッテリー レベルが極端に低い場合にデバイスの電源を入れようとすると、1 個のライトが短く点滅してから消えます。</span><span class="sxs-lookup"><span data-stu-id="744de-120">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="744de-121">ホスト PC で**エクスプローラー**を開き、左側の [**この PC**] の下にある HoloLens 2 デバイスを探します。</span><span class="sxs-lookup"><span data-stu-id="744de-121">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="744de-122">そのデバイスを右クリックし、**[プロパティ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="744de-122">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="744de-123">ダイアログ ボックスにバッテリの充電レベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="744de-123">A dialog box will show the battery charge level.</span></span>

   ![HoloLens 2 のプロパティ画面にバッテリの残量レベルが表示されます。](images/ResetRecovery2.png)

<span data-ttu-id="744de-125">デバイスが起動メニューから起動できない場合は、ホスト PC の LED の外観とデバイスの一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="744de-125">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="744de-126">次に、[トラブルシューティング ガイド](https://docs.microsoft.com/hololens/hololens-troubleshooting)に従います。</span><span class="sxs-lookup"><span data-stu-id="744de-126">Then follow the [troubleshooting guide](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="744de-127">デバイスの状態がトラブルシューティング ガイドに記載されている状態と一致しない場合は、ホスト PC ではなく、電源に接続されたデバイスで[ハード リセット手順](hololens-recovery.md#hard-reset-procedure)を実行してください。</span><span class="sxs-lookup"><span data-stu-id="744de-127">If the state of the device doesn't match any of the states listed in the troubleshooting guide, preform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="744de-128">デバイスが充電されるまで少なくとも 1 時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="744de-128">Wait at least one hour for the device to charge.</span></span>

## <span data-ttu-id="744de-129">デバイスをリセットする</span><span class="sxs-lookup"><span data-stu-id="744de-129">Reset the device</span></span>

<span data-ttu-id="744de-130">状況によっては、ソフトウェアの UI を使用せずにデバイスを手動でリセットする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="744de-130">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <span data-ttu-id="744de-131">標準手順</span><span class="sxs-lookup"><span data-stu-id="744de-131">Standard procedure</span></span>
1. <span data-ttu-id="744de-132">Type-C ケーブルを抜いて、デバイスを電源またはホスト PC から切断します。</span><span class="sxs-lookup"><span data-stu-id="744de-132">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="744de-133">**電源**ボタンを 15 秒間押し続けます。</span><span class="sxs-lookup"><span data-stu-id="744de-133">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="744de-134">すべての LED がオフになるはずです。</span><span class="sxs-lookup"><span data-stu-id="744de-134">All LEDs should be off.</span></span>

3. <span data-ttu-id="744de-135">2 - 3 秒待ってから、**電源**ボタンを短く押します。</span><span class="sxs-lookup"><span data-stu-id="744de-135">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="744de-136">電源ボタンの近くの LED が点灯し、デバイスが起動します。</span><span class="sxs-lookup"><span data-stu-id="744de-136">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="744de-137">デバイスをホスト PC に接続し、デバイス マネージャーを開きます。</span><span class="sxs-lookup"><span data-stu-id="744de-137">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="744de-138">(Windows 10 の場合は、**Windows キー**を押し、次に**X キー**を押して、**デバイス マネージャー**を選択します)。次の図に示すように、デバイスが *Microsoft HoloLens* として正しく列挙されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="744de-138">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery デバイス マネージャー](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="744de-140">ハード リセット手順</span><span class="sxs-lookup"><span data-stu-id="744de-140">Hard-reset procedure</span></span>

<span data-ttu-id="744de-141">標準のリセット手順が機能しない場合は、ハード リセット手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="744de-141">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="744de-142">Type-C ケーブルを抜いて、デバイスを電源またはホスト PC から切断します。</span><span class="sxs-lookup"><span data-stu-id="744de-142">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="744de-143">**音量減** + **電源**ボタンを 15 秒間押し続けます。</span><span class="sxs-lookup"><span data-stu-id="744de-143">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="744de-144">デバイスが自動的に再起動します。</span><span class="sxs-lookup"><span data-stu-id="744de-144">The device will automatically restart.</span></span>

4. <span data-ttu-id="744de-145">デバイスをホスト PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="744de-145">Connect the device to the host PC.</span></span>
5. <span data-ttu-id="744de-146">デバイス マネージャーを開きます (Windows 10 の場合は、**Windows キー**を押し、次に**X キー**を押して、**デバイス マネージャー**を選択します)。</span><span class="sxs-lookup"><span data-stu-id="744de-146">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="744de-147">次の図に示すように、デバイスが *Microsoft HoloLens* として正しく列挙されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="744de-147">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery デバイス マネージャー 2](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="744de-149">デバイスをきれいに再フラッシュする</span><span class="sxs-lookup"><span data-stu-id="744de-149">Clean-reflash the device</span></span>

<span data-ttu-id="744de-150">異常な状況では、HoloLens 2 のクリーン フラッシュが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="744de-150">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="744de-151">なお、以下の問題については、クリーン再フラッシュの実行によって解決することは期待できません。</span><span class="sxs-lookup"><span data-stu-id="744de-151">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="744de-152">画面の色の均一性</span><span class="sxs-lookup"><span data-stu-id="744de-152">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="744de-153">起動時に音がするが、ディスプレイ出力がない</span><span class="sxs-lookup"><span data-stu-id="744de-153">Booting with sound but no display output</span></span>
- [<span data-ttu-id="744de-154">1-3-5 の LED パターン</span><span class="sxs-lookup"><span data-stu-id="744de-154">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="744de-155">オーバーヒート</span><span class="sxs-lookup"><span data-stu-id="744de-155">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="744de-156">OS のクラッシュ (アプリケーションのクラッシュとは異なります)</span><span class="sxs-lookup"><span data-stu-id="744de-156">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="744de-157">デバイスを再フラッシュするには 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="744de-157">There are two ways to reflash the device.</span></span> <span data-ttu-id="744de-158">どちらの場合も、最初に [Windows ストアから Advanced Recovery Companion をインストール](https://www.microsoft.com/store/productId/9P74Z35SFRS8)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="744de-158">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="744de-159">デバイスを再フラッシュすると、TPM リセットを含むすべての個人データ、アプリ、設定が消去されます。</span><span class="sxs-lookup"><span data-stu-id="744de-159">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="744de-160">既定では、Advanced Recovery Companion は最新の機能リリース ビルドをダウンロードするように設定されています。最新の機能リリースについては、[リリース ノート](hololens-release-notes.md#)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="744de-160">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="744de-161">最新の HoloLens 2 フル フラッシュ更新プログラム (FFU) パッケージを取得して Advanced Recovery Companion を介してデバイスを更新するには、[こちらをクリックして最新の月次 HoloLens 2 イメージをダウンロード](https://aka.ms/hololens2download)してください。</span><span class="sxs-lookup"><span data-stu-id="744de-161">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="744de-162">このバージョンは、一般的に利用可能な最新のビルドです。</span><span class="sxs-lookup"><span data-stu-id="744de-162">This version is the latest generally available build.</span></span>

<span data-ttu-id="744de-163">再フラッシュ手順を開始する前に、アプリが Windows 10 PC にインストールされて実行されており、デバイスを検出する準備ができていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="744de-163">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![HoloLens 2 クリーン再フラッシュ スクリーンショット](images/ARC1.png)

### <span data-ttu-id="744de-165">通常の手順</span><span class="sxs-lookup"><span data-stu-id="744de-165">Normal procedure</span></span>

1. <span data-ttu-id="744de-166">HoloLens デバイスの実行中に、以前に高度な回復コンパニオン アプリを開いた Windows 10 PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="744de-166">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="744de-167">デバイスが自動的に検出され、高度な回復コンパニオン アプリの UI が更新プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="744de-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 クリーン 再フラッシュの初期画面](images/ARC2.png)

3. <span data-ttu-id="744de-169">高度な回復コンパニオン アプリの UI で HoloLens 2 デバイスを選択し、指示に従って再フラッシュを完了します。</span><span class="sxs-lookup"><span data-stu-id="744de-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <span data-ttu-id="744de-170">手動の手順</span><span class="sxs-lookup"><span data-stu-id="744de-170">Manual procedure</span></span>

<span data-ttu-id="744de-171">HoloLens 2 が正常に起動しない場合は、デバイスを回復モードにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="744de-171">If the HoloLens 2 doesn't start correctly, you may need to put the device into Recovery mode:</span></span>

1. <span data-ttu-id="744de-172">Type-C ケーブルを抜いて、デバイスを電源またはホスト PC から切断します。</span><span class="sxs-lookup"><span data-stu-id="744de-172">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="744de-173">**電源**ボタンを 15 秒間押し続けます。</span><span class="sxs-lookup"><span data-stu-id="744de-173">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="744de-174">すべての LED がオフになります。</span><span class="sxs-lookup"><span data-stu-id="744de-174">All LEDs should turn off.</span></span>

3. <span data-ttu-id="744de-175">**[音量を上げる] ボタン**を押しながら、**電源ボタン**を押して離し、デバイスを起動します。</span><span class="sxs-lookup"><span data-stu-id="744de-175">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="744de-176">15 秒待ってから、**[音量を上げる]** ボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="744de-176">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="744de-177">5 つの LED のうち中央の LED だけが点灯します。</span><span class="sxs-lookup"><span data-stu-id="744de-177">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="744de-178">デバイスをホスト PC に接続し、デバイス マネージャーを開きます。</span><span class="sxs-lookup"><span data-stu-id="744de-178">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="744de-179">(Windows 10 の場合は、**Windows キー**を押し、次に**X キー**を押して、**デバイス マネージャー**を選択します)。次の図に示すように、デバイスが Microsoft HoloLens として正しく列挙されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="744de-179">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="744de-181">デバイスが自動的に検出され、高度な回復コンパニオン アプリの UI が更新プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="744de-181">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 クリーン再フラッシュの画面](images/ARC2.png)

6. <span data-ttu-id="744de-183">高度な回復コンパニオン アプリの UI で HoloLens 2 デバイスを選択し、指示に従って再フラッシュを完了します。</span><span class="sxs-lookup"><span data-stu-id="744de-183">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <span data-ttu-id="744de-184">アプリ ストアを使用せずに ARC をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="744de-184">Download ARC without using the app store</span></span>

<span data-ttu-id="744de-185">IT 環境が Windows Store アプリの使用を妨げたり、小売店へのアクセスを制限したりする場合、IT 管理者は「オフライン」展開パスを通じてこのアプリを利用可能にすることができます。</span><span class="sxs-lookup"><span data-stu-id="744de-185">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE] 
 > - <span data-ttu-id="744de-186">IT 管​​理者は、System Center Configuration Manager (SCCM) または Intune を介してこのアプリを配布することもできます。</span><span class="sxs-lookup"><span data-stu-id="744de-186">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="744de-187">このガイドでは高度な回復コンパニオンに焦点を当てますが、プロセスは、他の「オフライン」アプリにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="744de-187">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="744de-188">展開パスを有効にする手順は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="744de-188">Follow these steps to enable the deployment path:</span></span>
1. <span data-ttu-id="744de-189">[ビジネス向け Microsoft Store](https://businessstore.microsoft.com) に移動し、Azure Active Directory ID を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="744de-189">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="744de-190">**[管理]、[設定]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="744de-190">Go to **Manage – Settings**.</span></span> <span data-ttu-id="744de-191">**[買い物エクスペリエンス]** で **[オフライン アプリの表示]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="744de-191">Turn on **Show offline apps** under **Shopping experience**.</span></span> 
1. <span data-ttu-id="744de-192">**[グループで買い物]** に移動して、[\**_Advanced Recovery Companion_*_](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8) を検索します。</span><span class="sxs-lookup"><span data-stu-id="744de-192">Go to **shop for my group**, and search for [\**_Advanced Recovery Companion_*_](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>
1. <span data-ttu-id="744de-193">_*[ライセンスの種類]*\* を \*\*_オフライン_\*_ に変更し、_*[管理]*\* を選択します。</span><span class="sxs-lookup"><span data-stu-id="744de-193">Change the _*License Type*\* to \**_offline_*_, and select _\*Manage\*\*.</span></span>
1. <span data-ttu-id="744de-194">**[オフラインで使用するためのパッケージをダウンロードする]** で、2 番目の青い **[ダウンロード]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="744de-194">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="744de-195">ファイル拡張子が *.appxbundle* であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="744de-195">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="744de-196">この段階で、デスクトップ PC がインターネットにアクセスできる場合は、パッケージをダブルクリックしてアプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="744de-196">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>


    - <span data-ttu-id="744de-197">接続先 PC にインターネット接続がない場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="744de-197">If the destination PC has no internet connectivity, follow these steps:</span></span> 
       1. <span data-ttu-id="744de-198">エンコードされていないライセンスを選択して、**[ライセンスを生成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="744de-198">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="744de-199">**[必要なフレームワーク]** で **[ダウンロード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="744de-199">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="744de-200">DISM を使用して、依存関係とライセンスを持つパッケージを適用します。</span><span class="sxs-lookup"><span data-stu-id="744de-200">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="744de-201">管理者のコマンド プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="744de-201">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > <span data-ttu-id="744de-202">このコード例のバージョン番号は、現在利用可能なバージョンと一致しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="744de-202">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="744de-203">例とは異なるダウンロード場所を選択した可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="744de-203">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="744de-204">必要に応じてコマンドを変更します。</span><span class="sxs-lookup"><span data-stu-id="744de-204">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="744de-205">高度な回復コンパニオンを使用して FFU をオフラインでインストールする場合は、フラッシュ イメージをダウンロードすると便利です。</span><span class="sxs-lookup"><span data-stu-id="744de-205">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="744de-206">[**HoloLens 2**](https://aka.ms/hololens2download) の現在の画像をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="744de-206">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="744de-207">その他のリソース:</span><span class="sxs-lookup"><span data-stu-id="744de-207">Other resources:</span></span>
- [<span data-ttu-id="744de-208">オフライン アプリの配布</span><span class="sxs-lookup"><span data-stu-id="744de-208">Distribute offline apps</span></span>](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="744de-209">DISM アプリ パッケージ (.appx または .appxbundle) によるコマンドライン オプションのサービス</span><span class="sxs-lookup"><span data-stu-id="744de-209">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
