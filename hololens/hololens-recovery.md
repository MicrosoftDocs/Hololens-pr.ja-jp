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
ms.openlocfilehash: 9c9dd12b596d8fafdfe575797193f18e7b96919c
ms.sourcegitcommit: 2122490074adb7f63edfc3576441980caa22695f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "10915971"
---
# <span data-ttu-id="0f00e-104">HoloLens 2 を再起動、リセット、または回復する</span><span class="sxs-lookup"><span data-stu-id="0f00e-104">Restart, reset, or recover HoloLens 2</span></span>

## <span data-ttu-id="0f00e-105">デバイスを充電する</span><span class="sxs-lookup"><span data-stu-id="0f00e-105">Charge the device</span></span>

<span data-ttu-id="0f00e-106">トラブルシューティングの手順を開始する前に、可能であれば、デバイスがバッテリ容量の 20 - 40% に充電されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0f00e-106">Before you start any troubleshooting procedure, make sure that your device is charged to 20 to 40 percent of battery capacity if possible.</span></span> <span data-ttu-id="0f00e-107">HoloLens 2 デバイスに付属の充電器と USB Type-C ケーブルを使用します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-107">Use the charger and the USB Type-C cables that come with the HoloLens2 device.</span></span> <span data-ttu-id="0f00e-108">これらのアクセサリが使用できない場合は、使用可能な充電器が少なくとも 15W の電力に対応していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0f00e-108">If those accessories aren't available, make sure the charger that's available can support at least 15 W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="0f00e-109">可能であれば、PC を使用してデバイスを USB 経由で充電することは避けてください。これは遅いです。</span><span class="sxs-lookup"><span data-stu-id="0f00e-109">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="0f00e-110">デバイスが正常に起動し、動作している場合は、次の 3 つの方法でバッテリの充電レベルを確認できます。</span><span class="sxs-lookup"><span data-stu-id="0f00e-110">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="0f00e-111">HoloLens デバイス UI のメイン メニューから。</span><span class="sxs-lookup"><span data-stu-id="0f00e-111">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="0f00e-112">電源ボタンの近くにある LED を確認します (40% が充電されている場合、少なくとも 2 つの点灯した LED が見えるはずです)。</span><span class="sxs-lookup"><span data-stu-id="0f00e-112">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDS).</span></span>
- <span data-ttu-id="0f00e-113">ホスト PC でエクスプローラーを開き、左側の **[この PC]** の下にある HoloLens 2 デバイスを探します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-113">On your host PC, open File Explorer and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="0f00e-114">そのデバイスを右クリックし、**[プロパティ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="0f00e-114">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="0f00e-115">ダイアログ ボックスにバッテリの充電レベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f00e-115">A dialog box will show the battery charge level.</span></span>

   ![HoloLens 2 のプロパティ画面にバッテリの残量レベルが表示されます。](images/ResetRecovery2.png)

<span data-ttu-id="0f00e-117">デバイスが起動メニューから起動できない場合は、ホスト PC の LED の外観とデバイスの一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-117">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="0f00e-118">次に、[トラブルシューティング ガイド](https://docs.microsoft.com/hololens/hololens-troubleshooting)に従います。</span><span class="sxs-lookup"><span data-stu-id="0f00e-118">Then follow the [troubleshooting guide](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="0f00e-119">デバイスの状態がトラブルシューティング ガイドに記載されている状態と一致しない場合は、ホスト PC ではなく、電源に接続されたデバイスで*ハード リセット手順*を実行してください。</span><span class="sxs-lookup"><span data-stu-id="0f00e-119">If the state of the device doesn't match any of the states listed in the troubleshooting guide, do the *hard reset procedure* with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="0f00e-120">デバイスが充電されるまで少なくとも 1 時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="0f00e-120">Wait at least one hour for the device to charge.</span></span>

## <span data-ttu-id="0f00e-121">デバイスをリセットする</span><span class="sxs-lookup"><span data-stu-id="0f00e-121">Reset the device</span></span>

<span data-ttu-id="0f00e-122">状況によっては、SW UI を使用せずにデバイスを手動でリセットしなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="0f00e-122">Under certain circumstances, you may have to manually reset the device without using the SW UI.</span></span>

### <span data-ttu-id="0f00e-123">標準手順</span><span class="sxs-lookup"><span data-stu-id="0f00e-123">Standard procedure</span></span>
1. <span data-ttu-id="0f00e-124">Type-C ケーブルを抜いて、デバイスを電源またはホスト PC から切断します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-124">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="0f00e-125">**電源**ボタンを 15 秒間押し続けます。</span><span class="sxs-lookup"><span data-stu-id="0f00e-125">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="0f00e-126">すべての LED がオフになるはずです。</span><span class="sxs-lookup"><span data-stu-id="0f00e-126">All LEDs should be off.</span></span>

3. <span data-ttu-id="0f00e-127">2 - 3 秒待ってから、**電源**ボタンを短く押します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-127">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="0f00e-128">電源ボタンの近くの LED が点灯し、デバイスが起動します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-128">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="0f00e-129">デバイスをホスト PC に接続し、デバイス マネージャーを開きます。</span><span class="sxs-lookup"><span data-stu-id="0f00e-129">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="0f00e-130">(Windows 10 の場合は、**Windows キー**を押し、次に**X キー**を押して、**デバイス マネージャー**を選択します)。次の図に示すように、デバイスが *Microsoft HoloLens* として正しく列挙されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-130">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="0f00e-132">ハード リセット手順</span><span class="sxs-lookup"><span data-stu-id="0f00e-132">Hard-reset procedure</span></span>

<span data-ttu-id="0f00e-133">標準のリセット手順が機能しない場合は、ハード リセット手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-133">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="0f00e-134">Type-C ケーブルを抜いて、デバイスを電源またはホスト PC から切断します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-134">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="0f00e-135">**音量減** + **電源**ボタンを 15 秒間押し続けます。</span><span class="sxs-lookup"><span data-stu-id="0f00e-135">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="0f00e-136">デバイスが自動的に再起動します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-136">The device will automatically restart.</span></span>

4. <span data-ttu-id="0f00e-137">デバイスをホスト PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-137">Connect the device to the host PC.</span></span>
5. <span data-ttu-id="0f00e-138">デバイス マネージャーを開きます (Windows 10 の場合は、**Windows キー**を押し、次に**X キー**を押して、**デバイス マネージャー**を選択します)。</span><span class="sxs-lookup"><span data-stu-id="0f00e-138">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="0f00e-139">次の図に示すように、デバイスが *Microsoft HoloLens* として正しく列挙されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-139">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="0f00e-141">デバイスをきれいに再フラッシュする</span><span class="sxs-lookup"><span data-stu-id="0f00e-141">Clean-reflash the device</span></span>

<span data-ttu-id="0f00e-142">異常な状況では、HoloLens 2 のクリーン フラッシュが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="0f00e-142">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="0f00e-143">デバイスを再フラッシュするには 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="0f00e-143">There are two ways to reflash the device.</span></span> <span data-ttu-id="0f00e-144">両方の場合、まず、[Windows ストアから高度な回復コンパニオン](https://www.microsoft.com/store/productId/9P74Z35SFRS8)をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f00e-144">For both, you must first install [Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="0f00e-145">デバイスを再フラッシュすると、TPM リセットを含むすべての個人データ、アプリ、設定が消去されます。</span><span class="sxs-lookup"><span data-stu-id="0f00e-145">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="0f00e-146">基本的に高度な回復コンパニオンは、現在 [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004) の機能リリース ビルドをダウンロードするように設定されています。</span><span class="sxs-lookup"><span data-stu-id="0f00e-146">By default, Advanced Recovery Companion is currently set to download the feature release build for [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004).</span></span> <span data-ttu-id="0f00e-147">高度な回復コンパニオンを介してデバイスを再フラッシュするための最新の HoloLens 2 Full Flash Update (FFU) パッケージを取得するには、[ここからダウンロード](https://aka.ms/hololens2download)してください。</span><span class="sxs-lookup"><span data-stu-id="0f00e-147">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [download it here](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="0f00e-148">このバージョンは、一般的に利用可能な最新のビルドです。</span><span class="sxs-lookup"><span data-stu-id="0f00e-148">This version is the latest generally available build.</span></span>

<span data-ttu-id="0f00e-149">再フラッシュ手順を開始する前に、アプリが Windows 10 PC にインストールされて実行されており、デバイスを検出する準備ができていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0f00e-149">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![HoloLens 2 クリーン再フラッシュ スクリーンショット](images/ARC1.png)

### <span data-ttu-id="0f00e-151">通常の手順</span><span class="sxs-lookup"><span data-stu-id="0f00e-151">Normal procedure</span></span>

1. <span data-ttu-id="0f00e-152">HoloLens デバイスの実行中に、以前に高度な回復コンパニオン アプリを開いた Windows 10 PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-152">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="0f00e-153">デバイスが自動的に検出され、高度な回復コンパニオン アプリの UI が更新プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-153">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 クリーン 再フラッシュの初期画面](images/ARC2.png)

3. <span data-ttu-id="0f00e-155">高度な回復コンパニオン アプリの UI で HoloLens 2 デバイスを選択し、指示に従って再フラッシュを完了します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-155">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <span data-ttu-id="0f00e-156">手動の手順</span><span class="sxs-lookup"><span data-stu-id="0f00e-156">Manual procedure</span></span>

<span data-ttu-id="0f00e-157">HoloLens 2 が正常に起動しない場合は、デバイスを回復モードにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f00e-157">If the HoloLens 2 doesn't start correctly, you may need to put the device into Recovery mode:</span></span>

1. <span data-ttu-id="0f00e-158">Type-C ケーブルを抜いて、デバイスを電源またはホスト PC から切断します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-158">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="0f00e-159">**電源**ボタンを 15 秒間押し続けます。</span><span class="sxs-lookup"><span data-stu-id="0f00e-159">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="0f00e-160">すべての LED がオフになります。</span><span class="sxs-lookup"><span data-stu-id="0f00e-160">All LEDs should turn off.</span></span>

3. <span data-ttu-id="0f00e-161">**[音量を上げる] ボタン**を押しながら、**電源ボタン**を押して離し、デバイスを起動します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-161">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="0f00e-162">15 秒待ってから、**[音量を上げる]** ボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-162">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="0f00e-163">5 つの LED のうち中央の LED だけが点灯します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-163">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="0f00e-164">デバイスをホスト PC に接続し、デバイス マネージャーを開きます。</span><span class="sxs-lookup"><span data-stu-id="0f00e-164">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="0f00e-165">(Windows 10 の場合は、**Windows キー**を押し、次に**X キー**を押して、**デバイス マネージャー**を選択します)。次の図に示すように、デバイスが Microsoft HoloLens として正しく列挙されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-165">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="0f00e-167">デバイスが自動的に検出され、高度な回復コンパニオン アプリの UI が更新プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 クリーン再フラッシュの画面](images/ARC2.png)

6. <span data-ttu-id="0f00e-169">高度な回復コンパニオン アプリの UI で HoloLens 2 デバイスを選択し、指示に従って再フラッシュを完了します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <span data-ttu-id="0f00e-170">アプリ ストアを使用せずに ARC をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="0f00e-170">Download ARC without using the app store</span></span>

<span data-ttu-id="0f00e-171">IT 環境が Windows Store アプリの使用を妨げたり、小売店へのアクセスを制限したりする場合、IT 管理者は「オフライン」展開パスを通じてこのアプリを利用可能にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0f00e-171">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE] 
 > - <span data-ttu-id="0f00e-172">IT 管​​理者は、System Center Configuration Manager (SCCM) または Intune を介してこのアプリを配布することもできます。</span><span class="sxs-lookup"><span data-stu-id="0f00e-172">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="0f00e-173">このガイドでは高度な回復コンパニオンに焦点を当てますが、プロセスは、他の「オフライン」アプリにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="0f00e-173">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="0f00e-174">展開パスを有効にする手順は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0f00e-174">Follow these steps to enable the deployment path:</span></span>
1. <span data-ttu-id="0f00e-175">[ビジネス向け Microsoft Store](https://businessstore.microsoft.com) に移動し、Azure Active Directory ID を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="0f00e-175">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="0f00e-176">**[管理]、[設定]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-176">Go to **Manage – Settings**.</span></span> <span data-ttu-id="0f00e-177">**[買い物エクスペリエンス]** で **[オフライン アプリの表示]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="0f00e-177">Turn on **Show offline apps** under **Shopping experience**.</span></span> 
1. <span data-ttu-id="0f00e-178">[**グループで買い物**] に移動し、[***高度な回復コンパニオン***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8) アプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-178">Go to **shop for my group**, and search for [***Advanced Recovery Companion***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>
1. <span data-ttu-id="0f00e-179">[**ライセンスの種類**] を***オフライン***に変更し、**[管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-179">Change the **License Type** to ***offline***, and select **Manage**.</span></span>
1. <span data-ttu-id="0f00e-180">**[オフラインで使用するためのパッケージをダウンロードする]** で、2 番目の青い **[ダウンロード]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-180">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="0f00e-181">ファイル拡張子が *.appxbundle* であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-181">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="0f00e-182">この段階で、デスクトップ PC がインターネットにアクセスできる場合は、パッケージをダブルクリックしてアプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="0f00e-182">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>


    - <span data-ttu-id="0f00e-183">接続先 PC にインターネット接続がない場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-183">If the desination PC has no internet connectivity, follow these steps:</span></span> 
       1. <span data-ttu-id="0f00e-184">エンコードされていないライセンスを選択して、**[ライセンスを生成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-184">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="0f00e-185">**[必要なフレームワーク]** で **[ダウンロード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-185">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="0f00e-186">DISM を使用して、依存関係とライセンスを持つパッケージを適用します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-186">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="0f00e-187">管理者のコマンド プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-187">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > <span data-ttu-id="0f00e-188">このコード例のバージョン番号は、現在利用可能なバージョンと一致しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="0f00e-188">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="0f00e-189">例とは異なるダウンロード場所を選択した可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="0f00e-189">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="0f00e-190">必要に応じてコマンドを変更します。</span><span class="sxs-lookup"><span data-stu-id="0f00e-190">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="0f00e-191">高度な回復コンパニオンを使用して FFU をオフラインでインストールする場合は、フラッシュ イメージをダウンロードすると便利です。</span><span class="sxs-lookup"><span data-stu-id="0f00e-191">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="0f00e-192">[**HoloLens 2**](https://aka.ms/hololens2download) の現在の画像をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="0f00e-192">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="0f00e-193">その他のリソース:</span><span class="sxs-lookup"><span data-stu-id="0f00e-193">Other resources:</span></span>
- [<span data-ttu-id="0f00e-194">オフライン アプリの配布</span><span class="sxs-lookup"><span data-stu-id="0f00e-194">Distribute offline apps</span></span>](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="0f00e-195">DISM アプリ パッケージ (.appx または .appxbundle) によるコマンドライン オプションのサービス</span><span class="sxs-lookup"><span data-stu-id="0f00e-195">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
