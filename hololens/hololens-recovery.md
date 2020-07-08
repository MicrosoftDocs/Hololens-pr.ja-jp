---
title: HoloLens を再起動、リセット、または回復する
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
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
ms.openlocfilehash: 2c7fa9b8c86900c89bbced1a10f3e9e2bc69bcd0
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857765"
---
# <span data-ttu-id="42715-104">HoloLens を再起動、リセット、または回復する</span><span class="sxs-lookup"><span data-stu-id="42715-104">Restart, reset, or recover HoloLens</span></span>

## <span data-ttu-id="42715-105">デバイスの充電</span><span class="sxs-lookup"><span data-stu-id="42715-105">Charging the device</span></span>

<span data-ttu-id="42715-106">トラブルシューティング手順を開始する前に、可能であれば、デバイスが少なくとも 20 ~ 40% 充電されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="42715-106">Before starting any troubleshooting procedure, if possible, ensure that your device is charged at least between 20% and 40%.</span></span>

<span data-ttu-id="42715-107">HoloLens 2 デバイスに付属の充電器と USB Type-C ケーブルを使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="42715-107">Please ensure you are using the charger and the USB Type-C cables that come with the HoloLens2 device.</span></span> <span data-ttu-id="42715-108">それらが利用できない場合は、利用可能な充電器が少なくとも 15W の電力をサポートできることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="42715-108">In case they are not available ensure the charger available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="42715-109">可能であれば、PC を使用して USB 経由でデバイスを充電しないでください。充電が非常に遅くなるためです。</span><span class="sxs-lookup"><span data-stu-id="42715-109">If possible, do not use a PC to charge the device over USB as this will provide a very slow charge.</span></span>

<span data-ttu-id="42715-110">デバイスが正しく起動して実行されている場合、バッテリーの充電をチェックするには 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="42715-110">If the device is correctly booted and running there are three different ways of checking the charge of your battery.</span></span>

1. <span data-ttu-id="42715-111">HoloLens デバイス UI のメイン メニューから。</span><span class="sxs-lookup"><span data-stu-id="42715-111">From the main menu of the HoloLens Device UI.</span></span>
2. <span data-ttu-id="42715-112">電源ボタンの近くにある LED を使用する (40% の場合、少なくとも 2 つの点灯した LED が見えるはずです)。</span><span class="sxs-lookup"><span data-stu-id="42715-112">Using the LED close to the power button (for 40% you should see at least two solid LEDS).</span></span>
3. <span data-ttu-id="42715-113">ホスト PC でエクスプローラー ウィンドウを開き、左側の [この PC] の下にある HoloLens 2 デバイスを探します。</span><span class="sxs-lookup"><span data-stu-id="42715-113">On your Host PC open File Explorer window and look for your HoloLens 2 device on left side under “This PC”.</span></span>
    
      <span data-ttu-id="42715-114">a. </span><span class="sxs-lookup"><span data-stu-id="42715-114">a.</span></span> <span data-ttu-id="42715-115">デバイス名を右クリックして、プロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="42715-115">Right click on the name of the device and select properties.</span></span> <span data-ttu-id="42715-116">デバイスのバッテリー レベルを示すダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="42715-116">A dialog will appear showing the battery level for your device.</span></span>

![HoloLens 2 ResetRecovery](images/ResetRecovery2.png)

<span data-ttu-id="42715-118">デバイスをスタートアップ メニューから起動できない場合は、ホスト PC の LED と列挙値を記録し、トラブルシューティング ガイド (https://docs.microsoft.com/hololens/hololens-troubleshooting)) に従います。</span><span class="sxs-lookup"><span data-stu-id="42715-118">If the device cannot be booted to the Startup Menu, please take note of the LEDs and enumeration on the host PC and follow the troubleshooting guide (https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="42715-119">デバイスの状態がトラブルシューティング ガイドに記載されている状態のいずれにも該当しない場合は、デバイスをホスト PC に再接続せずに、**ハード リセット手順**を実行しますが、代わりに電源に接続します。</span><span class="sxs-lookup"><span data-stu-id="42715-119">In case the state of the device does not fall in any of the states listed in the troubleshooting guide, execute the **hard reset procedure** without reconnecting the device to your host PC, but connect it instead to the power supply.</span></span> <span data-ttu-id="42715-120">デバイスが充電されるまで少なくとも 1 時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="42715-120">Wait for at least one hour for the device to charge.</span></span>

## <span data-ttu-id="42715-121">デバイスをリセットする</span><span class="sxs-lookup"><span data-stu-id="42715-121">Reset the device</span></span>

<span data-ttu-id="42715-122">特定の状況下では、SW UI を使用せずにデバイスを手動でリセットする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="42715-122">Under certain circumstances the customer may be required to manually reset the device without using the SW UI.</span></span> 

### <span data-ttu-id="42715-123">標準手順</span><span class="sxs-lookup"><span data-stu-id="42715-123">Standard procedure</span></span>
1. <span data-ttu-id="42715-124">Type-C ケーブルを抜いて、デバイスを電源またはホスト PC から切断します。</span><span class="sxs-lookup"><span data-stu-id="42715-124">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span>

2. <span data-ttu-id="42715-125">**電源ボタン**を 15 秒間押し続けます。</span><span class="sxs-lookup"><span data-stu-id="42715-125">Press and hold the **power button** for 15 seconds.</span></span> <span data-ttu-id="42715-126">すべての LED がオフになるはずです。</span><span class="sxs-lookup"><span data-stu-id="42715-126">All LEDs should be off.</span></span>

3. <span data-ttu-id="42715-127">2 ~ 3 秒待ってから**電源ボタン**を短く押します。電源ボタンの近くの LED が点灯し、デバイスの起動が始まります。</span><span class="sxs-lookup"><span data-stu-id="42715-127">Wait 2-3 seconds and Short press the **power button**, the LEDs close to the power button will light up and the device will start to boot.</span></span> 

4. <span data-ttu-id="42715-128">デバイスをホスト PC に接続し、デバイス マネージャーを開きます (Windows 10 の場合は、**「Windows」キー**を押し、次に **「x」キー**を押して、「デバイス マネージャー」をクリックします)。下の図に示すように、デバイスが Microsoft HoloLens として正しく列挙されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="42715-128">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the pictures below:</span></span>

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="42715-130">ハード リセット手順</span><span class="sxs-lookup"><span data-stu-id="42715-130">Hard-reset procedure</span></span>

<span data-ttu-id="42715-131">標準のリセット手順が機能しない場合は、ハード リセット手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="42715-131">If the standard reset procedure does not work, you can use the hard-reset procedure.</span></span>

1. <span data-ttu-id="42715-132">Type-C ケーブルを抜いて、デバイスを電源またはホスト PC から切断します。</span><span class="sxs-lookup"><span data-stu-id="42715-132">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span>

2. <span data-ttu-id="42715-133">**[音量を下げる] + 電源ボタン**を 15 秒間押し続けます。</span><span class="sxs-lookup"><span data-stu-id="42715-133">Hold **volume down + power button** for 15 seconds.</span></span>

3. <span data-ttu-id="42715-134">デバイスは自動的に再起動します。</span><span class="sxs-lookup"><span data-stu-id="42715-134">The device will automatically reboot.</span></span> 

4. <span data-ttu-id="42715-135">デバイスをホスト PC に接続し、デバイス マネージャーを開きます (Windows 10 の場合は、**「Windows」キー**を押し、次に **「x」キー**を押して、「デバイス マネージャー」をクリックします)。下の図に示すように、デバイスが Microsoft HoloLens として正しく列挙されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="42715-135">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the pictures below.</span></span>

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="42715-137">デバイスをきれいに再フラッシュする</span><span class="sxs-lookup"><span data-stu-id="42715-137">Clean reflash the device</span></span>

<span data-ttu-id="42715-138">異常な状況では、デバイスのクリーン フラッシュが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="42715-138">In extraordinary situations you may be required to clean flash the device.</span></span> <span data-ttu-id="42715-139">HoloLens 2 デバイスを再フラッシュするには 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="42715-139">There are two ways to reflash a HoloLens2 device.</span></span> <span data-ttu-id="42715-140">すべての再フラッシュ手順では、[Windows Store から高度な回復コンパニオン アプリをインストールする](https://www.microsoft.com/store/productId/9P74Z35SFRS8)必要があります。</span><span class="sxs-lookup"><span data-stu-id="42715-140">For all reflashing procedures you will be required to [install the Advanced Recovery Companion app from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span> <span data-ttu-id="42715-141">デバイスをリセットすると、TPM リセットを含むすべての個人データ、アプリ、設定が消去されます。</span><span class="sxs-lookup"><span data-stu-id="42715-141">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset.</span></span>

<span data-ttu-id="42715-142">高度な回復コンパニオンは現在、[Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004) の機能リリース ビルドをダウンロードするように設定されています。最新の HoloLens 2 FFU をダウンロードして高度な回復コンパニオン経由でデバイスをフラッシュする場合は、[こちら](https://aka.ms/hololens2download)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="42715-142">Advanced Recovery Companion is currently set to download the feature release build for [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004), if you would like to download the latest HoloLens 2 FFU to flash your device via Advanced Recovery Companion then you may download it from [here](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="42715-143">これは最新の状態に保たれ、最新の一般に入手可能なビルドと一致します。</span><span class="sxs-lookup"><span data-stu-id="42715-143">This is kept up-to-date and will match the latest generally available build.</span></span> 

<span data-ttu-id="42715-144">フラッシュ手順を開始する前に、アプリが Windows 10 PC にインストールされて実行されており、デバイスを検出する準備ができていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="42715-144">Before starting the flashing procedure make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![HoloLens 2 クリーン再フラッシュ](images/ARC1.png)

### <span data-ttu-id="42715-146">通常の手順</span><span class="sxs-lookup"><span data-stu-id="42715-146">Normal procedure</span></span>

1. <span data-ttu-id="42715-147">HoloLens デバイスの実行中に、以前に高度な回復コンパニオン アプリを起動した Windows 10 PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="42715-147">While the HoloLens device is running, connect it to your Windows 10 PC where you previously launched the Advanced Recovery Companion App.</span></span>

2. <span data-ttu-id="42715-148">デバイスが自動的に検出され、高度な回復コンパニオン アプリの UI が次のように更新されます。</span><span class="sxs-lookup"><span data-stu-id="42715-148">The device will automatically be detected and the Advanced Recovery Companion App UI will update as follows:</span></span>

![HoloLens 2 クリーン再フラッシュ](images/ARC2.png)

3. <span data-ttu-id="42715-150">高度な回復コンパニオン アプリの UI で HoloLens 2 デバイスを選択し、指示に従ってフラッシュを完了します。</span><span class="sxs-lookup"><span data-stu-id="42715-150">Select the HoloLens2 device in the Advanced Recovery Companion App UI and follow the instructions to complete the flashing.</span></span>

### <span data-ttu-id="42715-151">手動の手順</span><span class="sxs-lookup"><span data-stu-id="42715-151">Manual procedure</span></span>

<span data-ttu-id="42715-152">デバイスが正しく起動しない場合は、HoloLens 2 デバイスを回復モードにする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="42715-152">If the device does not boot correctly you may need to put the HoloLens 2 device in Recovery mode.</span></span>

1. <span data-ttu-id="42715-153">Type-C ケーブルを抜いて、デバイスを電源またはホスト PC から切断します。</span><span class="sxs-lookup"><span data-stu-id="42715-153">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span> 

2. <span data-ttu-id="42715-154">**電源ボタン**を 15 秒間押し続けます。</span><span class="sxs-lookup"><span data-stu-id="42715-154">Press and hold the **power button** for 15 seconds.</span></span> <span data-ttu-id="42715-155">すべての LED がオフになります。</span><span class="sxs-lookup"><span data-stu-id="42715-155">All LEDs should turn off.</span></span> 

3. <span data-ttu-id="42715-156">**[音量を上げる] ボタン**を押しながら、**電源ボタン**を押して離し、デバイスを起動します。</span><span class="sxs-lookup"><span data-stu-id="42715-156">While pressing the **volume up button**, press and release the **power button** to boot the device.</span></span> <span data-ttu-id="42715-157">15 秒待ってから、[音量を上げる] ボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="42715-157">Wait 15 seconds before releasing the volume up button.</span></span> <span data-ttu-id="42715-158">デバイスの 5 つの LED のうち、真ん中の LED のみが点灯します。</span><span class="sxs-lookup"><span data-stu-id="42715-158">Out of the 5 LEDs on the device, only the middle LED will light up.</span></span>

4. <span data-ttu-id="42715-159">デバイスをホスト PC に接続し、デバイス マネージャーを開きます (Windows 10 の場合は、**「Windows」キー**を押し、次に **「x」キー**を押して、「デバイス マネージャー」をクリックします)。下の図に示すように、デバイスが Microsoft HoloLens として正しく列挙されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="42715-159">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the image below.</span></span>

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

5. <span data-ttu-id="42715-161">デバイスが自動的に検出され、高度な回復コンパニオン アプリの UI が次のように更新されます。</span><span class="sxs-lookup"><span data-stu-id="42715-161">The device will be automatically detected, and the Advanced Recovery Companion app UI will update as follows:</span></span>

![HoloLens 2 クリーン再フラッシュ](images/ARC2.png)

6. <span data-ttu-id="42715-163">高度な回復コンパニオン アプリの UI で HoloLens 2 デバイスを選択し、指示に従ってフラッシュを完了します。</span><span class="sxs-lookup"><span data-stu-id="42715-163">Select the HoloLens 2 device in the Advanced Recovery Companion app UI and follow the instructions to complete the flashing.</span></span>

## <span data-ttu-id="42715-164">アプリ ストアを使用せずに ARC をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="42715-164">Downloading ARC without using the app store</span></span>

<span data-ttu-id="42715-165">IT 環境が Windows Store アプリの使用を妨げたり、小売店へのアクセスを制限したりする場合、IT 管理者は他の「オフライン」展開パスを通じてこのアプリを利用可能にすることができます。</span><span class="sxs-lookup"><span data-stu-id="42715-165">If an IT environment prevents the use of the Windows Store app or limits access to the retail store, IT administrators can make this app available through other ‘offline’ deployment paths.</span></span> 

- <span data-ttu-id="42715-166">このプロセスは、手順 2 に示すように、他のアプリにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="42715-166">This process may also be used for other apps, as seen in step 2.</span></span> <span data-ttu-id="42715-167">このガイドでは高度な回復コンパニオンに焦点を当てますが、他のオフライン アプリ用に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="42715-167">This guide will focus on Advanced Recovery Companion, but my be modified for other offline apps.</span></span>  

<span data-ttu-id="42715-168">この展開パスは、次の手順で有効にできます。</span><span class="sxs-lookup"><span data-stu-id="42715-168">This deployment path can be enabled with the following steps:</span></span>
1.  <span data-ttu-id="42715-169">[ビジネス向けストアの Web サイト](https://businessstore.microsoft.com)に移動し、Azure AD ID でサインインします。</span><span class="sxs-lookup"><span data-stu-id="42715-169">Go to the [Store For Business website](https://businessstore.microsoft.com) and sign-in with an Azure AD identity.</span></span>
1.  <span data-ttu-id="42715-170">**[管理]、[設定]** の順に移動し、https://businessstore.microsoft.com/manage/settings/shop で説明されているように、[**ショッピング エクスペリエンス**] の下で [**オフライン アプリを表示する**] をオンにします</span><span class="sxs-lookup"><span data-stu-id="42715-170">Go to **Manage – Settings**, and turn on **Show offline apps** under **Shopping experience** as described at https://businessstore.microsoft.com/manage/settings/shop</span></span> 
1.  <span data-ttu-id="42715-171">[**グループで買い物**] に移動し、[高度な回復コンパニオン](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8) アプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="42715-171">Go to **shop for my group** and search for the [Advanced Recovery Companion](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8) app.</span></span>
1.  <span data-ttu-id="42715-172">[**ライセンスの種類**] ボックスをオフラインに変更し、[**管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="42715-172">Change the **License Type** box to offline and click **Manage**.</span></span>
1.  <span data-ttu-id="42715-173">[オフラインで使用するためのパッケージをダウンロードする] で、2 番目の青い [**ダウンロード**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="42715-173">Under Download the package for offline use click the second blue **“Download”** button .</span></span> <span data-ttu-id="42715-174">ファイル拡張子が .appxbundle であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="42715-174">Ensure the file extension is .appxbundle.</span></span>
1.  <span data-ttu-id="42715-175">この段階で、デスクトップ PC がインターネットにアクセスできる場合は、ダブル クリックしてインストールするだけです。</span><span class="sxs-lookup"><span data-stu-id="42715-175">At this stage, if the Desktop PC has Internet access, simply double click and install.</span></span> 
1.  <span data-ttu-id="42715-176">IT 管​​理者は、System Center Configuration Manager (SCCM) または Intune を介してこのアプリを配布することもできます。</span><span class="sxs-lookup"><span data-stu-id="42715-176">The IT administrator can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
1.  <span data-ttu-id="42715-177">対象の PC にインターネット接続がない場合は、いくつかの追加手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="42715-177">If the target PC has no Internet connectivity, some additional steps are needed:</span></span> 
    1.  <span data-ttu-id="42715-178">エンコードされていないライセンスを選択し、[**ライセンスを生成**] をクリックし、[**必要なフレームワーク**] の下で、[**ダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="42715-178">Select the unencoded license and click **“Generate license”** and under **“Required Frameworks”** click **“Download.”**</span></span> 
    1.  <span data-ttu-id="42715-179">インターネットにアクセスできない PC は、依存関係とライセンスを含むパッケージを適用するために DISM を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42715-179">PCs without internet access will need to use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="42715-180">管理者のコマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="42715-180">In an administrator command prompt, type:</span></span>

      ```console
      C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
      ```
> [!NOTE]
> <span data-ttu-id="42715-181">このコード例のバージョン番号は、現在利用可能なバージョンと一致しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="42715-181">The version number in this code example may not match the currently avalible version.</span></span> <span data-ttu-id="42715-182">指定された例とは異なるダウンロード場所を選択した可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="42715-182">You may have also choosen a different download location than in the example given.</span></span> <span data-ttu-id="42715-183">必要に応じて変更してください。</span><span class="sxs-lookup"><span data-stu-id="42715-183">Please make sure to make any changes as needed.</span></span>

> [!TIP]
> <span data-ttu-id="42715-184">高度な回復コンパニオンを使用して ffu をオフラインでインストールすることを計画している場合、フラッシュ画像をダウンロードして使用できるようにすると便利な場合があります。「[HoloLens 2 の現在の画像](https://aka.ms/hololens2download)」です。</span><span class="sxs-lookup"><span data-stu-id="42715-184">When planning to use Advanced Recovery Companion to install an ffu offline it may be useful to download your flashing image to be availible, here is the [current image for HoloLens 2](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="42715-185">その他のリソース:</span><span class="sxs-lookup"><span data-stu-id="42715-185">Other resources:</span></span>
- https://docs.microsoft.com/microsoft-store/distribute-offline-apps 
- https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options


