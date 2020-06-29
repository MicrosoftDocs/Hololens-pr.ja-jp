---
title: ネットワークに接続する
description: HoloLens でインターネットに接続する方法と、デバイスの IP アドレスを識別する方法について説明します。
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, Wi-Fi, ワイヤレス, インターネット, IP, IP アドレス
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 0bc5a5f7f3eaf3d811da055a7bda664fd3f0daff
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829285"
---
# <span data-ttu-id="7cc3c-104">ネットワークに接続する</span><span class="sxs-lookup"><span data-stu-id="7cc3c-104">Connect to a network</span></span>

<span data-ttu-id="7cc3c-105">HoloLens で何らかの操作を実行するには、ほとんどの場合、ネットワークに接続している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="7cc3c-106">このガイドは次の作業に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-106">This guide will help you:</span></span>

- <span data-ttu-id="7cc3c-107">Wi-Fi または (HoloLens 2 の場合のみ) Ethernet over USB-C を使用してネットワークに接続する</span><span class="sxs-lookup"><span data-stu-id="7cc3c-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="7cc3c-108">Wi-Fi を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="7cc3c-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="7cc3c-109">[HoloLens のオフライン使用](hololens-offline.md)に関する詳細情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="7cc3c-110">初めての接続</span><span class="sxs-lookup"><span data-stu-id="7cc3c-110">Connecting for the first time</span></span>

<span data-ttu-id="7cc3c-111">HoloLens を初めて使うときは、Wi-Fi ネットワークに接続するためのガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="7cc3c-112">セットアップ中に Wi-Fi に接続できない場合は、接続先がオープン ネットワーク、パスワードで保護されたネットワーク、またはキャプティブ ポータル ネットワークであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="7cc3c-113">また、そのネットワークへの接続時に証明書の使用が求められないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="7cc3c-114">セットアップの完了後は、他の種類の Wi-Fi ネットワークにも接続できます。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

## <span data-ttu-id="7cc3c-115">セットアップ後の Wi-Fi 接続</span><span class="sxs-lookup"><span data-stu-id="7cc3c-115">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="7cc3c-116">**[スタート]** > **[設定]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-116">Select **Start** > **Settings**.</span></span>
   - <span data-ttu-id="7cc3c-117">*HoloLens (第 1 世代) のみ*: 視線入力を使って設定アプリを移動し、エアタップして配置するか、「置く」と言います。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-117">*HoloLens (1st gen) only*: Use your gaze to position the Settings app, then air tap to place it, or say "Place."</span></span>
1. <span data-ttu-id="7cc3c-118">**[ネットワークとインターネット]** > **[Wi-Fi]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-118">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="7cc3c-119">目的のネットワークが表示されない場合は、一覧を下方向へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-119">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="7cc3c-120">ネットワークを選択し、**[接続]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-120">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="7cc3c-121">ネットワーク パスワードを求めるメッセージが表示されたら、入力して **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-121">If you are prompted for a network password type it and then select **Next**.</span></span>

## <span data-ttu-id="7cc3c-122">HoloLens (第 1 世代) での Wi-Fi 接続</span><span class="sxs-lookup"><span data-stu-id="7cc3c-122">Connecting to Wi-Fi on HoloLens (1st gen)</span></span>

<span data-ttu-id="7cc3c-123">HoloLens には、802.11ac 対応の 2x2 Wi-Fi 無線が装備されています。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-123">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="7cc3c-124">HoloLens から Wi-Fi ネットワークへの接続は、Windows 10 デスクトップまたはモバイル デバイスから Wi-Fi ネットワークへの接続と似ています。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-124">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![HoloLens の Wi-Fi 設定](./images/wifi-hololens-600px.jpg)

1. <span data-ttu-id="7cc3c-126">**スタート** メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-126">Open the **Start** menu.</span></span>
1. <span data-ttu-id="7cc3c-127">**[スタート]** か、**スタート** メニューの右側にある **[すべてのアプリ]** の一覧から、設定アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-127">Select the Settings app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="7cc3c-128">設定アプリは、ユーザーの正面に自動配置されます。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-128">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="7cc3c-129">**[ネットワークとインターネット]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-129">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="7cc3c-130">Wi-Fi がオンになっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-130">Make sure Wi-Fi is turned on.</span></span>
1. <span data-ttu-id="7cc3c-131">一覧から Wi-Fi ネットワークを選択します。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-131">Select a Wi-Fi network from the list.</span></span>
1. <span data-ttu-id="7cc3c-132">必要に応じて、Wi-Fi ネットワーク パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-132">If needed, type in the Wi-Fi network password.</span></span>

<span data-ttu-id="7cc3c-133">**スタート** メニューで Wi-Fi の状態を確認することにより、Wi-Fi ネットワークへの接続を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-133">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="7cc3c-134">**スタート** メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-134">Open the **Start** menu.</span></span>
1. <span data-ttu-id="7cc3c-135">**スタート** メニューの左上で Wi-Fi の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-135">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="7cc3c-136">Wi-Fi の状態と、接続されているネットワークの SSID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-136">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="7cc3c-137">Wi-Fi への接続のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7cc3c-137">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="7cc3c-138">Wi-Fi への接続で問題が発生した場合は、「[Wi-Fi に接続できない](./hololens-faq.md#i-cant-connect-to-wi-fi)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-138">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="7cc3c-139">デバイスのエンタープライズ アカウントまたは組織アカウントにサインインするときに、ポリシーが IT 管理者によって構成されている場合、モバイル デバイス管理 (MDM) ポリシーも適用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="7cc3c-140">HoloLens (第 1 世代) での Wi-Fi の無効化</span><span class="sxs-lookup"><span data-stu-id="7cc3c-140">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="7cc3c-141">HoloLens での設定アプリの使用</span><span class="sxs-lookup"><span data-stu-id="7cc3c-141">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="7cc3c-142">**スタート** メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-142">Open the **Start** menu.</span></span>
1. <span data-ttu-id="7cc3c-143">**[スタート]** か、**スタート** メニューの右側にある **[すべてのアプリ]** の一覧から、**設定**アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-143">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="7cc3c-144">**設定**アプリは、ユーザーの正面に自動配置されます。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-144">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="7cc3c-145">**[ネットワークとインターネット]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-145">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="7cc3c-146">[Wi-Fi] のスライダー スイッチを選択して、**[オフ]** の位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-146">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="7cc3c-147">これにより、Wi-Fi 無線の RF コンポーネントがオフになり、HoloLens 上の Wi-Fi 機能がすべて無効になります。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-147">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="7cc3c-148">Wi-Fi 無線が無効になっている場合、HoloLens は[空間](hololens-spaces.md)を自動的に読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-148">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="7cc3c-149">スライダー スイッチを **[オン]** の位置に移動して Wi-Fi 無線を有効にし、Microsoft HoloLens に Wi-Fi 機能を復元します。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-149">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="7cc3c-150">選択した Wi-Fi 無線の状態 (**[オン]** または **[オフ]**) は、再起動しても維持されます。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-150">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="7cc3c-151">Wi-Fi ネットワーク上での HoloLens の IP アドレスの識別</span><span class="sxs-lookup"><span data-stu-id="7cc3c-151">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="7cc3c-152">設定アプリを使用する</span><span class="sxs-lookup"><span data-stu-id="7cc3c-152">By using the Settings app</span></span>

1. <span data-ttu-id="7cc3c-153">**スタート** メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-153">Open the **Start** menu.</span></span>
1. <span data-ttu-id="7cc3c-154">**[スタート]** か、**スタート** メニューの右側にある **[すべてのアプリ]** の一覧から、**設定**アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-154">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="7cc3c-155">**設定**アプリは、ユーザーの正面に自動配置されます。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-155">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="7cc3c-156">**[ネットワークとインターネット]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-156">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="7cc3c-157">使用可能な Wi-Fi ネットワークの下までスクロールし、**[ハードウェアのプロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-157">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Wi-Fi 設定の [ハードウェア プロパティ]](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="7cc3c-159">IP アドレスは **[IPv4 アドレス]** の横に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-159">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="7cc3c-160">Cortana を使用する</span><span class="sxs-lookup"><span data-stu-id="7cc3c-160">By using Cortana</span></span>

<span data-ttu-id="7cc3c-161">「Hey Cortana, What's my IP address?」 (コルタナさん、IP アドレスを教えて) と言うと、</span><span class="sxs-lookup"><span data-stu-id="7cc3c-161">Say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="7cc3c-162">Cortana によって IP アドレスの表示と読み上げが行われます。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-162">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="7cc3c-163">Windows デバイス ポータルを使用する</span><span class="sxs-lookup"><span data-stu-id="7cc3c-163">By using Windows Device Portal</span></span>

1. <span data-ttu-id="7cc3c-164">PC の Web ブラウザーで[デバイス ポータル](/windows/mixed-reality/using-the-windows-device-portal.md#networking)を開きます。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-164">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="7cc3c-165">**[ネットワーク]** セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-165">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="7cc3c-166">このセクションには、IP アドレスとその他のネットワーク情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-166">This section displays your IP address and other network information.</span></span> <span data-ttu-id="7cc3c-167">この方法を使用すると、開発用 PC の IP アドレスをコピーして貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="7cc3c-167">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
