---
title: HoloLens 2 を再起動、リセット、または回復する
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Advanced Recovery Companion を使用してイメージを HoloLens 2 にフラッシュする方法。
keywords: ハウツー, 再起動, リセット, 回復, ハード リセット, ソフト リセット, 電源サイクル, HoloLens, シャットダウン, アーク, Advanced Recovery Companion
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
appliesto:
- HoloLens 2
ms.openlocfilehash: be33eb5d06ee7d63f1f598792ff75605b0eb4424
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923637"
---
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="f3a9a-104">HoloLens 2 を再起動、リセット、または回復する</span><span class="sxs-lookup"><span data-stu-id="f3a9a-104">Restart, reset, or recover HoloLens 2</span></span>

>[!IMPORTANT]
> <span data-ttu-id="f3a9a-105">トラブルシューティングの手順を開始する前に、可能であれば、デバイスのバッテリ容量が **20 - 40%** 残っていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-105">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="f3a9a-106">電源 ボタンの下 にある[バッテリ インジケーター ライト](hololens2-setup.md#lights-that-indicate-the-battery-level)により、デバイスにログインせずにバッテリ容量を簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-106">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<span data-ttu-id="f3a9a-107">HoloLens 2 に付属している[充電器と USB タイプ C ケーブル](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1)を使用します。これは、デバイスの充電に最適な方法です。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-107">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="f3a9a-108">充電器は、18W の電力 (2A で 9V) を供給します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-108">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="f3a9a-109">付属のプラグを使用すると、HoloLens 2 デバイスは、デバイスがスタンバイ状態のときに 65 分未満でバッテリーを完全に充電できます。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-109">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="f3a9a-110">これらのアクセサリが使用できない場合は、使用可能な充電器が少なくとも 15W の電力に対応していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-110">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="f3a9a-111">可能であれば、PC を使用してデバイスを USB 経由で充電することは避けてください。遅いです。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-111">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="f3a9a-112">デバイスが正常に起動し、動作している場合は、次の 3 つの方法でバッテリの充電レベルを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="f3a9a-113">HoloLens デバイス UI のメイン メニューから。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="f3a9a-114">電源ボタンの近くにある LED を確認します (40% が充電されている場合、少なくとも 2 つの点灯した LED が見えるはずです)。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="f3a9a-115">デバイスの充電中は、バッテリー インジケーターが点灯し、現在の充電レベルを示します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="f3a9a-116">最後のライトはゆっくりと点滅し、充電中であることを示します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="f3a9a-117">HoloLens の電源が入っているときは、バッテリー インジケーターにバッテリー レベルが 5 段階で表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="f3a9a-118">5 個のライトのうち 1 個しか点灯していない場合は、バッテリー レベルが 20 パーセントを下回っています。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="f3a9a-119">バッテリー レベルが極端に低い場合にデバイスの電源を入れようとすると、1 個のライトが短く点滅してから消えます。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="f3a9a-120">ホスト PC で、**エクスプローラー** を開き、 **[この PC]** の下にある HoloLens 2 デバイスを探します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="f3a9a-121">そのデバイスを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="f3a9a-122">ダイアログ ボックスにバッテリの充電レベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-122">A dialog box will show the battery charge level.</span></span>

   ![HoloLens 2 のプロパティ画面にバッテリの残量レベルが表示されます](images/ResetRecovery2.png)

<span data-ttu-id="f3a9a-124">デバイスが起動メニューから起動できない場合は、ホスト PC の LED の外観とデバイスの一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-124">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="f3a9a-125">次に、[トラブルシューティング ガイド](hololens-troubleshooting.md)に従います。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-125">Then follow the [troubleshooting guide](hololens-troubleshooting.md).</span></span> <span data-ttu-id="f3a9a-126">デバイスの状態がトラブルシューティング ガイドに記載されている状態と一致しない場合は、ホスト PC ではなく、電源に接続されたデバイスで[ハード的なリセット手順](hololens-recovery.md#hard-reset-procedure)を実行してください。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-126">If the state of the device doesn't match any of the states listed in the troubleshooting guide, perform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="f3a9a-127">デバイスが充電されるまで少なくとも 1 時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-127">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="f3a9a-128">デバイスをリセットする</span><span class="sxs-lookup"><span data-stu-id="f3a9a-128">Reset the device</span></span>

<span data-ttu-id="f3a9a-129">状況によっては、ソフトウェアの UI を使用せずにデバイスを手動でリセットする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-129">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="f3a9a-130">標準手順</span><span class="sxs-lookup"><span data-stu-id="f3a9a-130">Standard procedure</span></span>

1. <span data-ttu-id="f3a9a-131">Type-C ケーブルを抜いて、デバイスを電源またはホスト PC から切断します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-131">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="f3a9a-132">**[電源]** ボタンを 15 秒間押し続けます。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-132">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="f3a9a-133">すべての LED がオフになるはずです。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-133">All LEDs should be off.</span></span>

3. <span data-ttu-id="f3a9a-134">2 - 3 秒待ってから、 **[電源]** ボタンを短く押します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-134">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="f3a9a-135">電源ボタンの近くの LED が点灯し、デバイスが起動します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-135">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="f3a9a-136">デバイスをホスト PC に接続し、デバイス マネージャーを開きます。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-136">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="f3a9a-137">(Windows 10 の場合は、**Windows** キーを押し、次に **X** キーを押して、**デバイス マネージャー** を選択します)。次の図に示すように、デバイスが *Microsoft HoloLens* として正しく列挙されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-137">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery デバイス マネージャー](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="f3a9a-139">ハード リセット手順</span><span class="sxs-lookup"><span data-stu-id="f3a9a-139">Hard-reset procedure</span></span>

<span data-ttu-id="f3a9a-140">標準のリセット手順が機能しない場合は、ハード リセット手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-140">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="f3a9a-141">Type-C ケーブルを抜いて、デバイスを電源またはホスト PC から切断します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-141">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="f3a9a-142">**[ボリューム ダウン]** ボタン +  **[電源]** ボタンを 15 秒間押したままにします。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-142">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="f3a9a-143">デバイスが自動的に再起動します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-143">The device will automatically restart.</span></span>

4. <span data-ttu-id="f3a9a-144">デバイスをホスト PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-144">Connect the device to the host PC.</span></span>

5. <span data-ttu-id="f3a9a-145">デバイス マネージャーを開きます (Windows 10 の場合は **Windows** キー、次に **X** キーを押して、**デバイス マネージャー** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-145">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="f3a9a-146">次の図に示すように、デバイスが *Microsoft HoloLens* として正しく列挙されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-146">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery デバイス マネージャー 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="f3a9a-148">デバイスをきれいに再フラッシュする</span><span class="sxs-lookup"><span data-stu-id="f3a9a-148">Clean-reflash the device</span></span>

<span data-ttu-id="f3a9a-149">異常な状況では、HoloLens 2 のクリーン フラッシュが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-149">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="f3a9a-150">なお、以下の問題については、クリーン再フラッシュの実行によって解決することは期待できません。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-150">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="f3a9a-151">ディスプレイの色の均一性</span><span class="sxs-lookup"><span data-stu-id="f3a9a-151">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="f3a9a-152">起動時に音がするが、ディスプレイ出力がない</span><span class="sxs-lookup"><span data-stu-id="f3a9a-152">Booting with sound but no display output</span></span>
- [<span data-ttu-id="f3a9a-153">1-3-5 の LED パターン</span><span class="sxs-lookup"><span data-stu-id="f3a9a-153">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="f3a9a-154">過熱</span><span class="sxs-lookup"><span data-stu-id="f3a9a-154">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="f3a9a-155">OS のクラッシュ (アプリケーションのクラッシュとは異なります)</span><span class="sxs-lookup"><span data-stu-id="f3a9a-155">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="f3a9a-156">デバイスを再フラッシュするには 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-156">There are two ways to reflash the device.</span></span> <span data-ttu-id="f3a9a-157">どちらの場合も、最初に、[Windows Store から Advanced Recovery Companion をインストールする必要があります](https://www.microsoft.com/store/productId/9P74Z35SFRS8)。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-157">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="f3a9a-158">デバイスを再フラッシュすると、TPM リセットを含むすべての個人データ、アプリ、設定が消去されます。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-158">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="f3a9a-159">既定では、Advanced Recovery Companion は最新の機能リリース ビルドをダウンロードするように設定されています。最新の機能リリースについては、 [リリース ノート](hololens-release-notes.md#)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-159">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="f3a9a-160">最新の HoloLens 2 Full Flash Update (FFU) パッケージを取得し、Advanced Recovery Companion を使用してデバイスを再フラッシュするには、[ここをクリックして最新のマンスリー HoloLens 2 イメージをダウンロードしてください](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-160">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="f3a9a-161">このバージョンは、一般的に利用可能な最新のビルドです。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-161">This version is the latest generally available build.</span></span>

<span data-ttu-id="f3a9a-162">再フラッシュ手順を開始する前に、アプリが Windows 10 PC にインストールされて実行されており、デバイスを検出する準備ができていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-162">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="f3a9a-163">また、HoloLens の充電が少なくとも 40% 以上になっていることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-163">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![HoloLens 2 クリーン再フラッシュのスクリーンショット](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="f3a9a-165">通常の手順</span><span class="sxs-lookup"><span data-stu-id="f3a9a-165">Normal procedure</span></span>

1. <span data-ttu-id="f3a9a-166">HoloLens デバイスの実行中に、以前に Advanced Recovery Companion アプリを開いた Windows 10 PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-166">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="f3a9a-167">デバイスが自動的に検出され、Advanced Recovery Companion アプリの UI が更新プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 クリーン 再フラッシュの初期画面](images/ARC2.png)

3. <span data-ttu-id="f3a9a-169">Advanced Recovery Companion アプリの UI で HoloLens 2 デバイスを選択し、指示に従って再フラッシュを完了します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="f3a9a-170">手動の手順</span><span class="sxs-lookup"><span data-stu-id="f3a9a-170">Manual procedure</span></span>

<span data-ttu-id="f3a9a-171">HoloLens 2 が正常に起動しない場合、または Advanced Recovery Companion がデバイスを検出できない場合は、デバイスを回復モードにする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-171">If the HoloLens 2 doesn't start correctly or if Advanced Recovery Companion cannot detect the device, you may need to put the device into recovery mode:</span></span>

1. <span data-ttu-id="f3a9a-172">Type-C ケーブルを抜いて、デバイスを電源またはホスト PC から切断します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-172">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="f3a9a-173">**[電源]** ボタンを 15 秒間押し続けます。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-173">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="f3a9a-174">すべての LED がオフになります。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-174">All LEDs should turn off.</span></span>

3. <span data-ttu-id="f3a9a-175">**[ボリューム アップ]** ボタンを押 しながら **[電源]** ボタンを 押して離 し、デバイスを起動します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-175">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="f3a9a-176">15 秒待って、 **[ボリューム アップ]** ボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-176">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="f3a9a-177">5 つの LED のうち中央の LED だけが点灯します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-177">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="f3a9a-178">デバイスをホスト PC に接続し、デバイス マネージャーを開きます。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-178">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="f3a9a-179">(Windows 10 の場合は、**Windows** キーを押し、次に **X** キーを押して、**デバイス マネージャー** を選択します)。次の図に示すように、デバイスが Microsoft HoloLens として正しく列挙されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-179">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="f3a9a-181">デバイスが自動的に検出され、Advanced Recovery Companion アプリの UI が更新プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-181">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 クリーン再フラッシュの画面](images/ARC2.png)

6. <span data-ttu-id="f3a9a-183">Advanced Recovery Companion アプリの UI で HoloLens 2 デバイスを選択し、指示に従って再フラッシュを完了します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-183">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="troubleshoot-advanced-recovery-companion"></a><span data-ttu-id="f3a9a-184">Advanced Recovery Companion のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f3a9a-184">Troubleshoot Advanced Recovery Companion</span></span>

1. <span data-ttu-id="f3a9a-185">フラッシュを試みる前に、デバイスが 40% 以上に充電されるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-185">Ensure your device is charged to 40% or more before attempting to flash.</span></span>

2. <span data-ttu-id="f3a9a-186">デバイスのロックが解除されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-186">Check that your device is unlocked.</span></span>

3. <span data-ttu-id="f3a9a-187">ARC によってデバイスが検出されない場合は、PC 上のデバイスからデバイスへエクスプローラーから接続できます。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-187">If ARC does not detect your device, ensure that you can connect to your device via File Explorer on your PC.</span></span> <span data-ttu-id="f3a9a-188">それができない場合、</span><span class="sxs-lookup"><span data-stu-id="f3a9a-188">If you cannot;</span></span>

    1.  <span data-ttu-id="f3a9a-189">デバイスに、その接続を無効にする USB ポリシーがある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-189">It is possible that your device may have USB policies that disable that connection.</span></span> <span data-ttu-id="f3a9a-190">その場合は、[手動フラッシュ モード](hololens-recovery.md#manual-procedure)を試してください。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-190">If so, try [Manual Flashing mode](hololens-recovery.md#manual-procedure).</span></span>
    2.  <span data-ttu-id="f3a9a-191">ポリシーがない場合は、別の USB ケーブルを試してください。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-191">If there are no policies, try a different USB cable.</span></span>

1. <span data-ttu-id="f3a9a-192">デバイスに [1-3-5-LED パターン](hololens2-setup.md#lights-to-indicate-problems)が表示されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-192">Check that your device doesn't display a [1-3-5-LED pattern](hololens2-setup.md#lights-to-indicate-problems).</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="f3a9a-193">アプリ ストアを使用せずに ARC をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="f3a9a-193">Download ARC without using the app store</span></span>

<span data-ttu-id="f3a9a-194">IT 環境が Windows Store アプリの使用を妨げたり、小売店へのアクセスを制限したりする場合、IT 管理者は「オフライン」展開パスを通じてこのアプリを利用可能にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-194">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="f3a9a-195">IT 管​​理者は、System Center Configuration Manager (SCCM) または Intune を介してこのアプリを配布することもできます。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-195">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="f3a9a-196">このガイドでは高度な回復コンパニオンに焦点を当てますが、プロセスは、他の「オフライン」アプリにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-196">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="f3a9a-197">展開パスを有効にする手順は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-197">Follow these steps to enable the deployment path:</span></span>

1. <span data-ttu-id="f3a9a-198">[Microsoft Store for Business](https://businessstore.microsoft.com) に進み、Azure Active Directory ID を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-198">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="f3a9a-199">**[管理][設定]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-199">Go to **Manage – Settings**.</span></span> <span data-ttu-id="f3a9a-200">**[ショッピング エクスペリエンス]** で **[オフライン アプリを表示]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-200">Turn on **Show offline apps** under **Shopping experience**.</span></span>

1. <span data-ttu-id="f3a9a-201">**[グループのショッピング**] にアクセスし、 [**_[Advanced Recovery Companion]_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8) を検索します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-201">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>

1. <span data-ttu-id="f3a9a-202">**ライセンスの種類** を **_[オフライン_ *] _ に変更し、* [_ 管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-202">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>

1. <span data-ttu-id="f3a9a-203">**[オフラインで使用するパッケージをダウンロード]** で、2番目の青い **[ダウンロード]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-203">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="f3a9a-204">ファイル拡張子が *.appxbundle* であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-204">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="f3a9a-205">この段階で、デスクトップ PC がインターネットにアクセスできる場合は、パッケージをダブルクリックしてアプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-205">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="f3a9a-206">接続先 PC にインターネット接続がない場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-206">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="f3a9a-207">エンコードされていないライセンスを選択し、 **[ライセンスの生成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-207">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="f3a9a-208">**[必須のフレームワーク]** で、 **[ダウンロード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-208">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="f3a9a-209">DISM を使用して、依存関係とライセンスを持つパッケージを適用します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-209">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="f3a9a-210">管理者のコマンド プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-210">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > <span data-ttu-id="f3a9a-211">このコード例のバージョン番号は、現在利用可能なバージョンと一致しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-211">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="f3a9a-212">例とは異なるダウンロード場所を選択した可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-212">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="f3a9a-213">必要に応じてコマンドを変更します。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-213">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="f3a9a-214">Advanced Recovery Companion を使用して FFU をオフラインでインストールする場合は、フラッシュ イメージをダウンロードすると便利です。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-214">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="f3a9a-215">[**HoloLens 2 の現在のイメージをダウンロードします**](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="f3a9a-215">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>


<span data-ttu-id="f3a9a-216">その他のリソース:</span><span class="sxs-lookup"><span data-stu-id="f3a9a-216">Other resources:</span></span>
- [<span data-ttu-id="f3a9a-217">オフライン アプリの配布</span><span class="sxs-lookup"><span data-stu-id="f3a9a-217">Distribute offline apps</span></span>](/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="f3a9a-218">DISM アプリ パッケージ (.appx または .appxbundle) によるコマンドライン オプションのサービス</span><span class="sxs-lookup"><span data-stu-id="f3a9a-218">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
