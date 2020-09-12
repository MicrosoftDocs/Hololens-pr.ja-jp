---
title: HoloLens をネットワークに接続する
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
ms.openlocfilehash: 0db64ffb4113ff948651c708c28b91da535cb09b
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009525"
---
# <span data-ttu-id="0f4a3-104">HoloLens をネットワークに接続する</span><span class="sxs-lookup"><span data-stu-id="0f4a3-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="0f4a3-105">HoloLens で何らかの操作を実行するには、ほとんどの場合、ネットワークに接続している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="0f4a3-106">このガイドは次の作業に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-106">This guide will help you:</span></span>

- <span data-ttu-id="0f4a3-107">Wi-Fi または (HoloLens 2 の場合のみ) Ethernet over USB-C を使用してネットワークに接続する</span><span class="sxs-lookup"><span data-stu-id="0f4a3-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="0f4a3-108">Wi-Fi を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="0f4a3-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="0f4a3-109">[HoloLens のオフライン使用](hololens-offline.md)に関する詳細情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="0f4a3-110">初めての接続</span><span class="sxs-lookup"><span data-stu-id="0f4a3-110">Connecting for the first time</span></span>

<span data-ttu-id="0f4a3-111">HoloLens を初めて使うときは、Wi-Fi ネットワークに接続するためのガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="0f4a3-112">セットアップ中に Wi-Fi に接続できない場合は、接続先がオープン ネットワーク、パスワードで保護されたネットワーク、またはキャプティブ ポータル ネットワークであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="0f4a3-113">また、そのネットワークへの接続時に証明書の使用が求められないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="0f4a3-114">セットアップの完了後は、他の種類の Wi-Fi ネットワークにも接続できます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="0f4a3-115">HoloLens 2 デバイスでは、[USB-C to Ethernet アダプターを使用](hololens-connect-devices.md#hololens-2-connect-usb-c-devices)して、直接 Wi-Fi に接続してデバイスのセットアップを支援する こともできます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-115">On HoloLens 2 devices a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="0f4a3-116">デバイスを設定した後は、アダプターを使い続けることもできますが、アダプターから切断して、[セットアップ後にデバイスを Wi-Fi に接続する](hololens-network.md#connecting-to-wi-fi-after-setup)こともできます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-116">Once the device has been set up a user may continue to user the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <span data-ttu-id="0f4a3-117">セットアップ後の Wi-Fi 接続</span><span class="sxs-lookup"><span data-stu-id="0f4a3-117">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="0f4a3-118">**スタート ジェスチャ** を事前に準備し、**設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-118">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="0f4a3-119">設定アプリは、ユーザーの正面に自動配置されます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-119">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="0f4a3-120">**[ネットワークとインターネット]** > **[Wi-Fi]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-120">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="0f4a3-121">Wi-Fi がオンになっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-121">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="0f4a3-122">目的のネットワークが表示されない場合は、一覧を下方向へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-122">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="0f4a3-123">ネットワークを選択し、**[接続]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-123">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="0f4a3-124">ネットワーク パスワードを求めるメッセージが表示されたら、入力して **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-124">If you are prompted for a network password type it and then select **Next**.</span></span>

<span data-ttu-id="0f4a3-125">HoloLens には、802.11ac 対応の 2x2 Wi-Fi 無線が装備されています。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-125">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="0f4a3-126">HoloLens から Wi-Fi ネットワークへの接続は、Windows 10 デスクトップまたはモバイル デバイスから Wi-Fi ネットワークへの接続と似ています。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-126">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![HoloLens の Wi-Fi 設定](./images/wifi-hololens-600px.jpg)

<span data-ttu-id="0f4a3-128">**スタート** メニューで Wi-Fi の状態を確認することにより、Wi-Fi ネットワークへの接続を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-128">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="0f4a3-129">**スタート** メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-129">Open the **Start** menu.</span></span>
1. <span data-ttu-id="0f4a3-130">**スタート** メニューの左上で Wi-Fi の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-130">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="0f4a3-131">Wi-Fi の状態と、接続されているネットワークの SSID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-131">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="0f4a3-132">Wi-Fi への接続のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0f4a3-132">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="0f4a3-133">Wi-Fi への接続で問題が発生した場合は、「[Wi-Fi に接続できない](./hololens-faq.md#i-cant-connect-to-wi-fi)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-133">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="0f4a3-134">デバイスのエンタープライズ アカウントまたは組織アカウントにサインインするときに、ポリシーが IT 管理者によって構成されている場合、モバイル デバイス管理 (MDM) ポリシーも適用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-134">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="0f4a3-135">VPN</span><span class="sxs-lookup"><span data-stu-id="0f4a3-135">VPN</span></span>
<span data-ttu-id="0f4a3-136">VPN 接続を使用すると、より安全な接続と会社のネットワークやインターネットへのアクセスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-136">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="0f4a3-137">HoloLens 2 は、組み込み VPN クライアントおよびユニバーサル Windows プラットフォーム (UWP) VPN プラグインをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-137">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="0f4a3-138">サポートされている組み込み VPN プロトコル:</span><span class="sxs-lookup"><span data-stu-id="0f4a3-138">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="0f4a3-139">IKEv2</span><span class="sxs-lookup"><span data-stu-id="0f4a3-139">IKEv2</span></span>
- <span data-ttu-id="0f4a3-140">L2TP</span><span class="sxs-lookup"><span data-stu-id="0f4a3-140">L2TP</span></span>
- <span data-ttu-id="0f4a3-141">PPTP</span><span class="sxs-lookup"><span data-stu-id="0f4a3-141">PPTP</span></span>

<span data-ttu-id="0f4a3-142">組み込みのVPN クライアントの認証に証明書を使用している場合は、必要なクライアント証明書をユーザー証明書ストアに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-142">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="0f4a3-143">サードパーティの VPN プラグインが HoloLens 2 をサポートしているかどうかを確認するには、[VPN アプリ] がある [ストア] に移動し、 ARM または ARM64 アーキテクチャ をサポートしているアプリの [システム要件ページ] に [HoloLens] が表示されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-143">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="0f4a3-144">HoloLens は、サードパーティ VPN 用のユニバーサル Windows プラットフォームアプリケーションのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-144">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

<span data-ttu-id="0f4a3-145">VPN は既定で有効になっていませんが、 **設定** アプリを開き、 **ネットワーク & インターネット -> VPN** に移動して、手動で有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-145">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span> <span data-ttu-id="0f4a3-146">VPN は、[Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)経由で MDM によって管理され、  [Vpnv2-csp ポリシー](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)を使用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-146">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>
<span data-ttu-id="0f4a3-147">詳細については、[これらのガイド](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)を使用して[how to configure VPNを構成する方法](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-147">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

## <span data-ttu-id="0f4a3-148">HoloLens (第 1 世代) での Wi-Fi の無効化</span><span class="sxs-lookup"><span data-stu-id="0f4a3-148">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="0f4a3-149">HoloLens での設定アプリの使用</span><span class="sxs-lookup"><span data-stu-id="0f4a3-149">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="0f4a3-150">**スタート** メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-150">Open the **Start** menu.</span></span>
1. <span data-ttu-id="0f4a3-151">**[スタート]** か、**スタート** メニューの右側にある **[すべてのアプリ]** の一覧から、**設定**アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-151">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="0f4a3-152">**設定**アプリは、ユーザーの正面に自動配置されます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-152">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="0f4a3-153">**[ネットワークとインターネット]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-153">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="0f4a3-154">[Wi-Fi] のスライダー スイッチを選択して、**[オフ]** の位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-154">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="0f4a3-155">これにより、Wi-Fi 無線の RF コンポーネントがオフになり、HoloLens 上の Wi-Fi 機能がすべて無効になります。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-155">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="0f4a3-156">Wi-Fi 無線が無効になっている場合、HoloLens は[空間](hololens-spaces.md)を自動的に読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-156">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="0f4a3-157">スライダー スイッチを **[オン]** の位置に移動して Wi-Fi 無線を有効にし、Microsoft HoloLens に Wi-Fi 機能を復元します。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-157">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="0f4a3-158">選択した Wi-Fi 無線の状態 (**[オン]** または **[オフ]**) は、再起動しても維持されます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-158">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="0f4a3-159">Wi-Fi ネットワーク上での HoloLens の IP アドレスの識別</span><span class="sxs-lookup"><span data-stu-id="0f4a3-159">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="0f4a3-160">設定アプリを使用する</span><span class="sxs-lookup"><span data-stu-id="0f4a3-160">By using the Settings app</span></span>

1. <span data-ttu-id="0f4a3-161">**スタート** メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-161">Open the **Start** menu.</span></span>
1. <span data-ttu-id="0f4a3-162">**[スタート]** か、**スタート** メニューの右側にある **[すべてのアプリ]** の一覧から、**設定**アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-162">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="0f4a3-163">**設定**アプリは、ユーザーの正面に自動配置されます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-163">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="0f4a3-164">**[ネットワークとインターネット]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-164">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="0f4a3-165">使用可能な Wi-Fi ネットワークの下までスクロールし、**[ハードウェアのプロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-165">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Wi-Fi 設定の [ハードウェア プロパティ]](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="0f4a3-167">IP アドレスは **[IPv4 アドレス]** の横に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-167">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="0f4a3-168">音声コマンドを使用する</span><span class="sxs-lookup"><span data-stu-id="0f4a3-168">By using voice commands</span></span>

<span data-ttu-id="0f4a3-169">使用しているデバイスに応じて、組み込み音声コマンドや Cortana を使用して IP アドレスを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-169">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="0f4a3-170">ビルドで[19041.1103](hololens-release-notes.md#windows-holographic-version-2004)の後に、"IP アドレスを教えて" と話します。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-170">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="0f4a3-171">すると、それが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-171">and it will be displayed.</span></span> <span data-ttu-id="0f4a3-172">以前のビルドまたは HoloLens (第１世代) では、「コルタナさん、IP アドレスを教えて」 と言います。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-172">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="0f4a3-173">Cortana によって IP アドレスの表示と読み上げが行われます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-173">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="0f4a3-174">Windows デバイス ポータルを使用する</span><span class="sxs-lookup"><span data-stu-id="0f4a3-174">By using Windows Device Portal</span></span>

1. <span data-ttu-id="0f4a3-175">PC の Web ブラウザーで[デバイス ポータル](/windows/mixed-reality/using-the-windows-device-portal.md#networking)を開きます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-175">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="0f4a3-176">**[ネットワーク]** セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-176">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="0f4a3-177">このセクションには、IP アドレスとその他のネットワーク情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-177">This section displays your IP address and other network information.</span></span> <span data-ttu-id="0f4a3-178">この方法を使用すると、開発用 PC の IP アドレスをコピーして貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="0f4a3-178">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
