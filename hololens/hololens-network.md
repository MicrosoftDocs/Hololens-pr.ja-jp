---
title: HoloLens をネットワークに接続する
description: HoloLens を使用してインターネットを設定して接続する方法と、デバイスの IP アドレスを識別する方法について説明します。
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, Wi-Fi, ワイヤレス, インターネット, IP, IP アドレス
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: c2a2fe1a20a4e9baa194b1037ccb6649d324b990
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640221"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="58b2f-104">HoloLens をネットワークに接続する</span><span class="sxs-lookup"><span data-stu-id="58b2f-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="58b2f-105">HoloLens で何らかの操作を実行するには、ほとんどの場合、ネットワークに接続している必要があります。</span><span class="sxs-lookup"><span data-stu-id="58b2f-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="58b2f-106">HoloLens には、802.11ac 対応の 2x2 Wi-Fi 無線が含まれているので、ネットワークに接続する方法は、Windows 10 デスクトップまたはモバイル デバイスを Wi-Fi ネットワークに接続するのと似ています。</span><span class="sxs-lookup"><span data-stu-id="58b2f-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="58b2f-107">このガイドは次の作業に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-107">This guide will help you:</span></span>

- <span data-ttu-id="58b2f-108">Wi-Fi または HoloLens 2 のみの場合、Wi-Fi Direct または Ethernet over USB-C を使用してネットワークに接続する</span><span class="sxs-lookup"><span data-stu-id="58b2f-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="58b2f-109">Wi-Fi を無効にし、再度有効にする</span><span class="sxs-lookup"><span data-stu-id="58b2f-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="58b2f-110">[HoloLens オフラインでの使用](hololens-offline.md)について詳しくは、こちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="58b2f-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="58b2f-111">初めての接続</span><span class="sxs-lookup"><span data-stu-id="58b2f-111">Connecting for the first time</span></span>

<span data-ttu-id="58b2f-112">HoloLens を初めて使うときは、Wi-Fi ネットワークに接続するためのガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="58b2f-113">セットアップ中に Wi-Fi に接続できない場合は、接続先がオープン ネットワーク、パスワードで保護されたネットワーク、またはキャプティブ ポータル ネットワークであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="58b2f-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="58b2f-114">また、接続に証明書を使用する必要がネットワークに存在しない場合も確認します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="58b2f-115">セットアップの完了後は、他の種類の Wi-Fi ネットワークにも接続できます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="58b2f-116">HoloLens 2 デバイスでは、ユーザーは[USB-C からイーサネットアダプターを使用](hololens-connect-devices.md#hololens-2-connect-usb-c-devices)して Wi-Fi に直接接続し、デバイスのセットアップを支援することもできます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="58b2f-117">デバイスがセットアップされた後、ユーザーはアダプターを引き続き使用するか、デバイスをアダプターから切断し、[セットアップ後にWi-Fiに接続することもできます](hololens-network.md#connecting-to-wi-fi-after-setup)。</span><span class="sxs-lookup"><span data-stu-id="58b2f-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="58b2f-118">セットアップ後の Wi-Fi 接続</span><span class="sxs-lookup"><span data-stu-id="58b2f-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="58b2f-119">**スタート ジェスチャ** を実行し、 **[設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="58b2f-120">設定アプリは、ユーザーの正面に自動配置されます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="58b2f-121">**[ネットワークとインターネット]**  >  **[Wi-Fi]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="58b2f-122">Wi-Fi がオンになっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="58b2f-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="58b2f-123">目的のネットワークが表示されない場合は、一覧を下方向へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="58b2f-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="58b2f-124">ネットワークを選択し、 **[接続]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="58b2f-125">ネットワーク パスワードを求めるメッセージが表示されたら、入力して **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![HoloLens の Wi-Fi 設定](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="58b2f-127">Wi-Fi ネットワークに接続されていることを確認するには、 **[スタート]** メニューで Wi-Fiの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="58b2f-128">**スタート** メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="58b2f-129">**[スタート]** メニューの左上で Wi-Fi の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="58b2f-130">Wi-Fi の状態と、接続されているネットワークの SSID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="58b2f-131">Wi-Fi が使用できない場合は、 [携帯ネットワークや5G ネットワークに接続](hololens-cellular.md)することもできます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](hololens-cellular.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="58b2f-132">設計上、ユーザーは HoloLens 2 の Wi-Fi ローミング動作を微調整することはできません。 **Wi-Fi リストを更新する唯一の方法は、Wi-Fi をオフまたはオンに切り替えることです**。</span><span class="sxs-lookup"><span data-stu-id="58b2f-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="58b2f-133">これにより、デバイスが範囲を外れ、AP に "スタック" 状態を維持できるなど、多くの問題が回避されます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="58b2f-134">HoloLens をエンタープライズ Wi-Fi ネットワークに接続する</span><span class="sxs-lookup"><span data-stu-id="58b2f-134">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="58b2f-135">エンタープライズ Wi-Fi プロファイルは、拡張認証プロトコル (EAP) を使って Wi-Fi 接続を認証します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-135">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="58b2f-136">HoloLens エンタープライズ Wi-Fi プロファイルは、[Windows 構成デザイナー](/windows/configuration/provisioning-packages/provisioning-packages) によって作成された MDM またはプロビジョニング パッケージを介して構成できます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-136">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="58b2f-137">Microsoft Intune 管理対象デバイスの場合、構成手順については [Intune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58b2f-137">For Microsoft Intune managed device, refer to [Intune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="58b2f-138">WCD で Wi-Fi プロビジョニング パッケージを作成するには、事前に構成された Wi-Fi プロファイルの .xml ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="58b2f-138">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="58b2f-139">以下は、EAP-TLS 認証を使用した WPA2-Enterprise の Wi-Fi プロファイルの例です。</span><span class="sxs-lookup"><span data-stu-id="58b2f-139">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

``` xml
<?xml version="1.0"?> 
<WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1"> 
    <name>SampleEapTlsProfile</name> 
    <SSIDConfig> 
        <SSID> 
            <hex>53616d706c65</hex> 
            <name>Sample</name> 
        </SSID> 
        <nonBroadcast>true</nonBroadcast> 
    </SSIDConfig> 
    <connectionType>ESS</connectionType> 
    <connectionMode>auto</connectionMode> 
    <autoSwitch>false</autoSwitch> 
    <MSM> 
        <security> 
            <authEncryption> 
                <authentication>WPA2</authentication> 
                <encryption>AES</encryption> 
                <useOneX>true</useOneX> 
                <FIPSMode xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode> 
            </authEncryption> 
            <PMKCacheMode>disabled</PMKCacheMode> 
            <OneX xmlns="http://www.microsoft.com/networking/OneX/v1"> 
                <authMode>machine</authMode> 
                <EAPConfig> 
                    <EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                        <EapMethod> 
                            <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type> 
                            <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId> 
                            <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType> 
                            <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId> 
                        </EapMethod> 
                        <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                            <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"> 
                                <Type>13</Type> 
                                <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"> 
                                    <CredentialsSource><CertificateStore><SimpleCertSelection>true</SimpleCertSelection> 
                                        </CertificateStore> 
                                    </CredentialsSource> 
                                    <ServerValidation> 
                                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation> 
                                        <ServerNames></ServerNames> 
                                        <TrustedRootCA>00 01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f 10 11 12 13</TrustedRootCA> 
                                    </ServerValidation> 
                                    <DifferentUsername>false</DifferentUsername> 
                                    <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</PerformServerValidation> 
                                    <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName> 
                                </EapType> 
                            </Eap> 
                        </Config> 
                    </EapHostConfig> 
                </EAPConfig> 
            </OneX> 
        </security> 
    </MSM> 
</WLANProfile> 
```


<span data-ttu-id="58b2f-140">サーバー ルート CA 証明書とクライアント証明書は、EAP の種類に応じて、デバイスにプロビジョニングされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="58b2f-140">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="58b2f-141">その他のリソース:</span><span class="sxs-lookup"><span data-stu-id="58b2f-141">Additional resources:</span></span>

- <span data-ttu-id="58b2f-142">WLANv1 プロファイル スキーマ: [[MS-GPWL]: ワイヤレス LAN プロファイル v1 スキーマ | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="58b2f-142">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="58b2f-143">EAP-TLS スキーマ: [[MS-GPWL]: Microsoft EAP TLS スキーマ | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="58b2f-143">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

<span data-ttu-id="58b2f-144">Wi-fi への接続に問題がある場合は、 [トラブルシューティング](hololens2-enterprise-troubleshooting.md#) のページを確認してください。</span><span class="sxs-lookup"><span data-stu-id="58b2f-144">Check our [Troubleshooting](hololens2-enterprise-troubleshooting.md#) page if you are having problems connecting to your Wi-Fi.</span></span>

## <a name="configure-network-proxy"></a><span data-ttu-id="58b2f-145">ネットワーク ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="58b2f-145">Configure Network Proxy</span></span>

<span data-ttu-id="58b2f-146">このセクションでは Windows HTTP スタックを使用して HoloLens OS およびユニバーサル Windows プラットフォーム (UWP) アプリ用のネットワーク プロキシについて説明します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-146">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="58b2f-147">Windows 以外の HTTP スタックを使用するアプリケーションでは、独自のプロキシ構成と処理を使用できます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-147">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="58b2f-148">プロキシの構成</span><span class="sxs-lookup"><span data-stu-id="58b2f-148">Proxy Configurations</span></span> 

- <span data-ttu-id="58b2f-149">プロキシの自動構成 (PAC) スクリプト: [PAC ファイル](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (Microsoft 以外のサイトを開く) には、JavaScript 関数 FindProxyForURL (url, host) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="58b2f-149">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="58b2f-150">静的プロキシ: サーバー: ポートの形式。</span><span class="sxs-lookup"><span data-stu-id="58b2f-150">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="58b2f-151">Web プロキシ自動検出プロトコル (WPAD): DHCP または DNS を介してプロキシ構成ファイルの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-151">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="58b2f-152">プロキシのプロビジョニング方法</span><span class="sxs-lookup"><span data-stu-id="58b2f-152">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="58b2f-153">プロビジョニング プロキシを提供するには、3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="58b2f-153">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="58b2f-154">**設定UI:**</span><span class="sxs-lookup"><span data-stu-id="58b2f-154">**Settings UI:**</span></span> 
    1. <span data-ttu-id="58b2f-155">ユーザーごとのプロキシ (20H2 以前):</span><span class="sxs-lookup"><span data-stu-id="58b2f-155">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="58b2f-156">スタート メニューを開き、[設定] を選択します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-156">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="58b2f-157">[ネットワークとインターネット] を選択して左のメニューでプロキシを選択します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-157">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="58b2f-158">[手動プロキシの設定] まで下にスクロールし、[プロキシサーバーの使用] を [オン] に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-158">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="58b2f-159">プロキシ サーバーの IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-159">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="58b2f-160">ポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-160">Enter the port number.</span></span>
        6. <span data-ttu-id="58b2f-161">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58b2f-161">Click Save.</span></span>
      1. <span data-ttu-id="58b2f-162">WiFi プロキシ (21H1 以降):</span><span class="sxs-lookup"><span data-stu-id="58b2f-162">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="58b2f-163">スタートメニューを開き、Wi-Fi ネットワークのプロパティ ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="58b2f-163">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="58b2f-164">プロキシまで下方向へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="58b2f-164">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="58b2f-165">手動セットアップに変更</span><span class="sxs-lookup"><span data-stu-id="58b2f-165">Change to Manual Setup</span></span>
          1. <span data-ttu-id="58b2f-166">プロキシ サーバーの IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-166">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="58b2f-167">ポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-167">Enter the port number.</span></span>
          1. <span data-ttu-id="58b2f-168">[適用] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58b2f-168">Click Apply.</span></span>
        
 2. <span data-ttu-id="58b2f-169">**MDM**</span><span class="sxs-lookup"><span data-stu-id="58b2f-169">**MDM**</span></span> 
     1. <span data-ttu-id="58b2f-170">Intune - Intune でプロキシを構成するには、次の[手順](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)に従います。</span><span class="sxs-lookup"><span data-stu-id="58b2f-170">Intune - Use these [steps](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="58b2f-171">セクションの一番下までスクロールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="58b2f-171">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="58b2f-172">その他のサードパーティ製 MDM ソリューション- [WiFi CSP](/windows/client-management/mdm/wifi-csp)を使用します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-172">Other 3rd party MDM solutions - Use a [WiFi CSP](/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="58b2f-173">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="58b2f-173">**PPKG**</span></span> 
    1. <span data-ttu-id="58b2f-174">Windows 構成デザイナーを開く</span><span class="sxs-lookup"><span data-stu-id="58b2f-174">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="58b2f-175">[高度なプロビジョニング] をクリックし、新しいプロジェクトの名前を入力して、[次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58b2f-175">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="58b2f-176">[Windows Holographic (HoloLens 2)] を選択し、[次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58b2f-176">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="58b2f-177">PPKG をインポートし (オプション)、[完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58b2f-177">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="58b2f-178">[ランタイムの設定] -> [接続プロファイル] -> [WLAN] -> [WLAN プロキシ] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-178">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="58b2f-179">Wi-Fi ネットワークの SSID を入力し、[追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58b2f-179">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="58b2f-180">左側のウィンドウで Wi-Fi ネットワークを選択し、必要なカスタマイズを入力します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-180">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="58b2f-181">有効なカスタマイズは、左側のメニューに太字で表示されます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-181">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="58b2f-182">[保存して閉じる] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58b2f-182">Click Save and Exit.</span></span>
    1. <span data-ttu-id="58b2f-183">HoloLens へプロビジョニング パッケージを[適用](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)氏ます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-183">[Apply](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="58b2f-184">[CSP](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) は、Microsoft Intune や Microsoft 以外の MDM サービス プロバイダーで、Windows 10 の多くの管理タスクとポリシーを陰で支えています。</span><span class="sxs-lookup"><span data-stu-id="58b2f-184">[CSPs](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="58b2f-185">[Windows 構成デザイナー](/windows/configuration/provisioning-packages/provisioning-install-icd)を使用して、[プロビジョニングパッケージ](/windows/configuration/provisioning-packages/provisioning-packages)を作成し、HoloLens 2 に適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-185">You can also use [Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="58b2f-186">HoloLens 2 に適用される可能性が最も高い CSP は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="58b2f-186">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="58b2f-187">[WiFi CSP](/windows/client-management/mdm/wifi-csp): プロファイルごとの Wi-Fi プロキシ</span><span class="sxs-lookup"><span data-stu-id="58b2f-187">[WiFi CSP](/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="58b2f-188">HoloLens デバイスでサポートされているそのほかの CSP</span><span class="sxs-lookup"><span data-stu-id="58b2f-188">Other CSPs supported in HoloLens devices</span></span>](/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="58b2f-189">VPN</span><span class="sxs-lookup"><span data-stu-id="58b2f-189">VPN</span></span>
<span data-ttu-id="58b2f-190">VPN 接続を使用すると、より安全な接続と会社のネットワークやインターネットへのアクセスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-190">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="58b2f-191">HoloLens 2 は、組み込み VPN クライアントおよびユニバーサル Windows プラットフォーム (UWP) VPN プラグインをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="58b2f-191">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="58b2f-192">サポートされている組み込み VPN プロトコル:</span><span class="sxs-lookup"><span data-stu-id="58b2f-192">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="58b2f-193">IKEv2</span><span class="sxs-lookup"><span data-stu-id="58b2f-193">IKEv2</span></span>
- <span data-ttu-id="58b2f-194">L2TP</span><span class="sxs-lookup"><span data-stu-id="58b2f-194">L2TP</span></span>
- <span data-ttu-id="58b2f-195">PPTP</span><span class="sxs-lookup"><span data-stu-id="58b2f-195">PPTP</span></span>

<span data-ttu-id="58b2f-196">組み込みのVPN クライアントの認証に証明書を使用している場合は、必要なクライアント証明書をユーザー証明書ストアに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58b2f-196">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="58b2f-197">サードパーティの VPN プラグインが HoloLens 2 をサポートしているかどうかを確認するには、[VPN アプリ] がある [ストア] に移動し、 ARM または ARM64 アーキテクチャ をサポートしているアプリの [システム要件ページ] に [HoloLens] が表示されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-197">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="58b2f-198">HoloLens は、サード パーティ VPN 用のユニバーサル Windows プラットフォーム アプリケーションのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="58b2f-198">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="58b2f-199">VPN は[設定/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)を使用して MDM で管理し、 [Vpnv2-CSP ポリシー](/windows/client-management/mdm/vpnv2-csp)を使用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-199">VPN can be managed by MDM via [Settings/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="58b2f-200">[VPN を構成する方法](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn)の詳細については、こちらの[ガイド](/windows/security/identity-protection/vpn/vpn-guide)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58b2f-200">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="58b2f-201">UI 経由の VPN</span><span class="sxs-lookup"><span data-stu-id="58b2f-201">VPN via UI</span></span>

<span data-ttu-id="58b2f-202">VPN は既定で有効になっていませんが、 **[設定]** アプリを開き、 **[ネットワークとインターネット] -> [VPN]** の順に移動して、手動で有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-202">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="58b2f-203">VPN プロバイダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-203">Select a VPN provider.</span></span>
1. <span data-ttu-id="58b2f-204">接続名を作成します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-204">Create a connection name.</span></span> 
1. <span data-ttu-id="58b2f-205">サーバー名またはアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-205">Enter your server name or address.</span></span>
1. <span data-ttu-id="58b2f-206">VPN の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-206">Select the VPN type.</span></span>
1. <span data-ttu-id="58b2f-207">サインイン情報の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-207">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="58b2f-208">必要に応じて、ユーザー名とパスワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-208">Optionally add user name and password.</span></span>
1. <span data-ttu-id="58b2f-209">VPN 設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-209">Apply the VPN settings.</span></span> 

![HoloLens VPN の設定](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="58b2f-211">プロビジョニング パッケージによる VPN の設定</span><span class="sxs-lookup"><span data-stu-id="58b2f-211">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="58b2f-212">Windows Holographic バージョン 20H2 では、VPN 接続のプロキシ構成の問題が修正されました。</span><span class="sxs-lookup"><span data-stu-id="58b2f-212">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="58b2f-213">このフローを使う場合は、このビルドにデバイスをアップグレードすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="58b2f-213">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="58b2f-214">Windows 構成デザイナーを起動します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-214">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="58b2f-215">**[HoloLens デバイスをプロビジョニング]** をクリックし、ターゲット デバイス と **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-215">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="58b2f-216">パッケージ名とパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-216">Enter package name and path.</span></span>
1. <span data-ttu-id="58b2f-217">**[詳細エディターに切り替える]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58b2f-217">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="58b2f-218">**[ランタイム設定]**  ->  **[ConnectivityProfiles]**  ->  **[VPN]**  ->  **[VPNSettings]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-218">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="58b2f-219">VPNProfileName を構成する</span><span class="sxs-lookup"><span data-stu-id="58b2f-219">Configure VPNProfileName</span></span>
1. <span data-ttu-id="58b2f-220">ProfileType (**Native** または **サードパーティー**) を選択します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-220">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="58b2f-221">ネイティブ プロファイルの場合、**NativeProtocolType** を選択し、サーバー、ルーティング ポリシー、認証の種類、その他の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-221">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="58b2f-222">「サードパーティ」プロファイルの場合、サーバー URL、VPN プラグイン アプリ パッケージ ファミリ名 (事前に定義されている 3 つのみ) およびカスタム構成を構成します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-222">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="58b2f-223">パッケージをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="58b2f-223">Export your package.</span></span>
1. <span data-ttu-id="58b2f-224">HoloLens を接続して、.ppkg ファイルをデバイスにコピーします。</span><span class="sxs-lookup"><span data-stu-id="58b2f-224">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="58b2f-225">HoloLens で、スタート メニュー を開き、 **[設定]**  ->  **[アカウント]**  ->  **[ワークまたはスクールにアクセス]**  ->  **[プロビジョニング パッケージを追加または削除]** -> [VPN パッケージを選択] を選択して、VPN .ppkg を適用します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-225">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="58b2f-226">Intune を使用した VPN のセットアップ</span><span class="sxs-lookup"><span data-stu-id="58b2f-226">Setting up VPN via Intune</span></span>
<span data-ttu-id="58b2f-227">Intune のドキュメントに従って、作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-227">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="58b2f-228">これらの手順を実行するときは、HoloLens デバイスがサポートする組み込みの VPN プロトコルに注意してください。</span><span class="sxs-lookup"><span data-stu-id="58b2f-228">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="58b2f-229">[Intune で VPN サーバーに接続するための VPN プロファイルを作成します](/mem/intune/configuration/vpn-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="58b2f-229">[Create VPN profiles to connect to VPN servers in Intune](/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="58b2f-230">[Intune を使用して VPN 接続を追加するための Windows 10 デバイスと Windows Holographic デバイスの設定](/mem/intune/configuration/vpn-settings-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="58b2f-230">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="58b2f-231">完了したら、忘れずに[プロファイル を割り当ててください](/mem/intune/configuration/device-profile-assign)。</span><span class="sxs-lookup"><span data-stu-id="58b2f-231">When done please remember to [assign the profile](/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="58b2f-232">サード パーティ MDM ソリューションを使用した VPN</span><span class="sxs-lookup"><span data-stu-id="58b2f-232">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="58b2f-233">サード パーティ VPN 接続の例:</span><span class="sxs-lookup"><span data-stu-id="58b2f-233">3rd party VPN connection example:</span></span>
```xml
<!-- Configure VPN Server Name or Address (PhoneNumber=) [Comma Separated]-->
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/ServerUrlList</LocURI>
          </Target>
          <Data>selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <!-- Configure VPN Plugin AppX Package ID (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/PluginPackageFamilyName</LocURI>
          </Target>
          <Data>TestVpnPluginApp-SL_8wekyb3d8bbwe</Data>
        </Item>
      </Add>

      <!-- Configure Microsoft's Custom XML (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/CustomConfiguration</LocURI>
          </Target>          <Data><pluginschema><ipAddress>auto</ipAddress><port>443</port><networksettings><routes><includev4><route><address>172.10.10.0</address><prefix>24</prefix></route></includev4></routes><namespaces><namespace><space>.vpnbackend.com</space><dnsservers><server>172.10.10.11</server></dnsservers></namespace></namespaces></networksettings></pluginschema></Data>
        </Item>
      </Add>
```

<span data-ttu-id="58b2f-234">ネイティブ IKEv2 VPN の例:</span><span class="sxs-lookup"><span data-stu-id="58b2f-234">Native IKEv2 VPN example:</span></span>
```xml
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Servers</LocURI>
          </Target>
          <Data>Selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/RoutingPolicyType</LocURI>
          </Target>
          <Data>ForceTunnel</Data>
        </Item>
      </Add>

      <!-- Configure VPN Protocol Type (L2tp, Pptp, Ikev2) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/NativeProtocolType</LocURI>
          </Target>
          <Data>Ikev2</Data>
        </Item>
      </Add>

      <!-- Configure VPN User Method (Mschapv2, Eap) -->
      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/UserMethod</LocURI>
          </Target>
          <Data>Eap</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/Eap/Configuration</LocURI>
          </Target>
          <Data>EAP_configuration_xml_content</Data>
        </Item>
      </Add>
```
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="58b2f-235">HoloLens (第 1 世代) での Wi-Fi の無効化</span><span class="sxs-lookup"><span data-stu-id="58b2f-235">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="58b2f-236">HoloLens での設定アプリの使用</span><span class="sxs-lookup"><span data-stu-id="58b2f-236">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="58b2f-237">**スタート** メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-237">Open the **Start** menu.</span></span>
1. <span data-ttu-id="58b2f-238">**[スタート]** または **[スタート]** メニューの右側にある **[すべてのアプリ]** の一覧から **設定** アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-238">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="58b2f-239">**設定** アプリは、ユーザーの正面に自動配置されます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-239">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="58b2f-240">**[ネットワークとインターネット]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-240">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="58b2f-241">Wi-Fi のスライダー スイッチを選択して、**オフ** の位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-241">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="58b2f-242">これにより、Wi-Fi 無線の RF コンポーネントがオフになり、HoloLens 上の Wi-Fi 機能がすべて無効になります。</span><span class="sxs-lookup"><span data-stu-id="58b2f-242">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="58b2f-243">Wi-Fi 無線が無効になっている場合、HoloLens は[スペース](hololens-spaces.md)を自動的に読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="58b2f-243">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="58b2f-244">スライダー スイッチを **オン** の位置に移動して Wi-Fi 無線を有効にし、Microsoft HoloLens に Wi-Fi 機能を復元します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-244">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="58b2f-245">選択した Wi-Fi 無線の状態 (**オン** または **オフ**) は、再起動しても維持されます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-245">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="58b2f-246">Wi-Fi ネットワーク上での HoloLens の IP アドレスの識別</span><span class="sxs-lookup"><span data-stu-id="58b2f-246">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="58b2f-247">設定アプリを使用する</span><span class="sxs-lookup"><span data-stu-id="58b2f-247">By using the Settings app</span></span>

1. <span data-ttu-id="58b2f-248">**スタート** メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-248">Open the **Start** menu.</span></span>
1. <span data-ttu-id="58b2f-249">**[スタート]** または **[スタート]** メニューの右側にある **[すべてのアプリ]** の一覧から **設定** アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-249">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="58b2f-250">**設定** アプリは、ユーザーの正面に自動配置されます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-250">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="58b2f-251">**[ネットワークとインターネット]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-251">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="58b2f-252">使用可能な Wi-Fi ネットワークの下までスクロールし、 **[ハードウェアのプロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-252">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Wi-Fi 設定のハードウェア プロパティ](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="58b2f-254">IP アドレスは、**IPv4 アドレス** の横に表示されます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-254">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="58b2f-255">音声コマンドを使用する</span><span class="sxs-lookup"><span data-stu-id="58b2f-255">By using voice commands</span></span>

<span data-ttu-id="58b2f-256">使用しているデバイスに応じて、組み込み音声コマンドや Cortana を使用して IP アドレスを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-256">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="58b2f-257">ビルドで [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) の後に、"IP アドレスを教えて" と話します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-257">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="58b2f-258">すると、それが表示されます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-258">and it will be displayed.</span></span> <span data-ttu-id="58b2f-259">以前のビルドまたは HoloLens (第１世代) では、「コルタナさん、IP アドレスを教えて」 と言います。</span><span class="sxs-lookup"><span data-stu-id="58b2f-259">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="58b2f-260">Cortana によって IP アドレスの表示と読み上げが行われます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-260">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="58b2f-261">Windows デバイス ポータルを使用する</span><span class="sxs-lookup"><span data-stu-id="58b2f-261">By using Windows Device Portal</span></span>

1. <span data-ttu-id="58b2f-262">PC の Web ブラウザーで、[デバイス ポータル](/windows/mixed-reality/using-the-windows-device-portal.md#networking)を開きます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-262">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="58b2f-263">**[ネットワーク]** セクションに移動 します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-263">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="58b2f-264">このセクションには、IP アドレスとその他のネットワーク情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-264">This section displays your IP address and other network information.</span></span> <span data-ttu-id="58b2f-265">この方法を使用すると、開発用 PC の IP アドレスをコピーして貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-265">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="58b2f-266">IP アドレスを静的アドレスに変更</span><span class="sxs-lookup"><span data-stu-id="58b2f-266">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="58b2f-267">設定を使用する</span><span class="sxs-lookup"><span data-stu-id="58b2f-267">By using Settings</span></span>
 
1. <span data-ttu-id="58b2f-268">**スタート** メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-268">Open the **Start** menu.</span></span>
1. <span data-ttu-id="58b2f-269">**[スタート]** または **[スタート]** メニューの右側にある **[すべてのアプリ]** の一覧から **設定** アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-269">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="58b2f-270">**設定** アプリは、ユーザーの正面に自動配置されます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-270">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="58b2f-271">**[ネットワークとインターネット]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-271">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="58b2f-272">使用可能な Wi-Fi ネットワークの下までスクロールし、 **[ハードウェアのプロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-272">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="58b2f-273">**[IP 設定の編集]** ウィンドウ で、最初のフィールドを **[手動]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-273">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="58b2f-274">残りのフィールドに目的の IP 構成を入力し、 **[保存]** を クリックします。</span><span class="sxs-lookup"><span data-stu-id="58b2f-274">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="58b2f-275">Windows デバイス ポータルを使用する</span><span class="sxs-lookup"><span data-stu-id="58b2f-275">By using Windows Device Portal</span></span>

1. <span data-ttu-id="58b2f-276">PC の Web ブラウザーで、[デバイス ポータル](/windows/mixed-reality/using-the-windows-device-portal.md#networking)を開きます。</span><span class="sxs-lookup"><span data-stu-id="58b2f-276">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="58b2f-277">**[ネットワーク]** セクションに移動 します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-277">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="58b2f-278">**[IPv4 構成]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-278">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="58b2f-279">**[次 の IP アドレスを使用する]** を選択し、必要な TCP/IP 構成を入力します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-279">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="58b2f-280">**[次の DNS サーバー アドレスを使用する]** を選択し、必要に応じて優先 DNS サーバー アドレスと代替 DNS サーバー アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="58b2f-280">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="58b2f-281">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58b2f-281">Click **Save**.</span></span> 
