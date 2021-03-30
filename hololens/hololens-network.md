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
ms.openlocfilehash: f1968afe7d450425776bac24532f2d84c4dc3c62
ms.sourcegitcommit: 9f79ed9f76b930b8ceb97844d5f9eace9316b8a3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2021
ms.locfileid: "11442595"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="f6796-104">HoloLens をネットワークに接続する</span><span class="sxs-lookup"><span data-stu-id="f6796-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="f6796-105">HoloLens で何らかの操作を実行するには、ほとんどの場合、ネットワークに接続している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6796-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="f6796-106">HoloLens には、802.11ac 対応の 2x2 Wi-Fi 無線が含まれているので、ネットワークに接続する方法は、Windows 10 デスクトップまたはモバイル デバイスを Wi-Fi ネットワークに接続するのと似ています。</span><span class="sxs-lookup"><span data-stu-id="f6796-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="f6796-107">このガイドは次の作業に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f6796-107">This guide will help you:</span></span>

- <span data-ttu-id="f6796-108">Wi-Fi または (HoloLens 2 の場合のみ) Ethernet over USB-C を使用してネットワークに接続する</span><span class="sxs-lookup"><span data-stu-id="f6796-108">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="f6796-109">Wi-Fi を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="f6796-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="f6796-110">[HoloLens のオフライン使用](hololens-offline.md)に関する詳細情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6796-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="f6796-111">初めての接続</span><span class="sxs-lookup"><span data-stu-id="f6796-111">Connecting for the first time</span></span>

<span data-ttu-id="f6796-112">HoloLens を初めて使うときは、Wi-Fi ネットワークに接続するためのガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6796-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="f6796-113">セットアップ中に Wi-Fi に接続できない場合は、接続先がオープン ネットワーク、パスワードで保護されたネットワーク、またはキャプティブ ポータル ネットワークであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f6796-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="f6796-114">また、接続に証明書を使用する必要がネットワークに存在しない場合も確認します。</span><span class="sxs-lookup"><span data-stu-id="f6796-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="f6796-115">セットアップの完了後は、他の種類の Wi-Fi ネットワークにも接続できます。</span><span class="sxs-lookup"><span data-stu-id="f6796-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="f6796-116">HoloLens 2 デバイスでは、ユーザーは [USB-C](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to Ethernet アダプターを使用してデバイスのセットアップを支援するために Wi-Fi に直接接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="f6796-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="f6796-117">デバイスがセットアップされた後、ユーザーはアダプターを引き続き使用するか、デバイスをアダプターから切断し、セットアップ後に [Wi-Fi に接続する可能性があります](hololens-network.md#connecting-to-wi-fi-after-setup)。</span><span class="sxs-lookup"><span data-stu-id="f6796-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="f6796-118">セットアップ後の Wi-Fi 接続</span><span class="sxs-lookup"><span data-stu-id="f6796-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="f6796-119">**スタート ジェスチャ** を事前に準備し、**設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6796-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="f6796-120">設定アプリは、ユーザーの正面に自動配置されます。</span><span class="sxs-lookup"><span data-stu-id="f6796-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="f6796-121">**[ネットワークとインターネット]** > **[Wi-Fi]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="f6796-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="f6796-122">Wi-Fi がオンになっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f6796-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="f6796-123">目的のネットワークが表示されない場合は、一覧を下方向へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="f6796-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="f6796-124">ネットワークを選択し、**[接続]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6796-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="f6796-125">ネットワーク パスワードを求めるメッセージが表示されたら、入力して **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6796-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![HoloLens の Wi-Fi 設定](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="f6796-127">ネットワークに接続されていることを確認Wi-Fi、[スタート] メニューWi-Fiの状態を **確認** します。</span><span class="sxs-lookup"><span data-stu-id="f6796-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="f6796-128">**スタート** メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="f6796-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="f6796-129">**スタート** メニューの左上で Wi-Fi の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="f6796-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="f6796-130">Wi-Fi の状態と、接続されているネットワークの SSID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6796-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="f6796-131">このWi-Fi使用できない場合は、Cellular ネットワークと [5G ネットワークに接続できます](https://docs.microsoft.com/hololens/hololens-cellular)。</span><span class="sxs-lookup"><span data-stu-id="f6796-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](https://docs.microsoft.com/hololens/hololens-cellular).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6796-132">設計上、ユーザーは HoloLens 2 の Wi-Fi ローミング動作を微調整できません **。Wi-Fi**リストを更新する唯一の方法は、Wi-Fi Off と On を切り替える方法です。</span><span class="sxs-lookup"><span data-stu-id="f6796-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="f6796-133">これにより、デバイスが範囲を外れ、AP に "スタック" 状態を維持できるなど、多くの問題が回避されます。</span><span class="sxs-lookup"><span data-stu-id="f6796-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="troubleshooting-your-connection-to-wi-fi"></a><span data-ttu-id="f6796-134">Wi-Fi への接続のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f6796-134">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="f6796-135">Wi-Fi への接続で問題が発生した場合は、「[Wi-Fi に接続できない](./hololens-faq.md#i-cant-connect-to-wi-fi)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f6796-135">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="f6796-136">デバイスのエンタープライズ アカウントまたは組織アカウントにサインインするときに、ポリシーが IT 管理者によって構成されている場合、モバイル デバイス管理 (MDM) ポリシーも適用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="f6796-136">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="f6796-137">HoloLens をエンタープライズ Wi-Fi ネットワークに接続する</span><span class="sxs-lookup"><span data-stu-id="f6796-137">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="f6796-138">エンタープライズ Wi-Fi プロファイルは、拡張認証プロトコル (EAP) を使って Wi-Fi 接続を認証します。</span><span class="sxs-lookup"><span data-stu-id="f6796-138">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="f6796-139">HoloLens エンタープライズ Wi-Fi プロファイルは、[Windows 構成デザイナー](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)によって作成された MDM またはプロビジョニング パッケージを介して構成できます。</span><span class="sxs-lookup"><span data-stu-id="f6796-139">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="f6796-140">Microsoft Intune 管理対象デバイスの場合、構成手順については [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6796-140">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="f6796-141">WCD で Wi-Fi プロビジョニング パッケージを作成するには、事前に構成された Wi-Fi プロファイルの .xml ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="f6796-141">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="f6796-142">以下は、EAP-TLS 認証を使用した WPA2-Enterprise の Wi-Fi プロファイルの例です。</span><span class="sxs-lookup"><span data-stu-id="f6796-142">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

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


<span data-ttu-id="f6796-143">サーバー ルート CA 証明書とクライアント証明書は、EAP の種類に応じて、デバイスにプロビジョニングされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6796-143">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="f6796-144">その他のリソース:</span><span class="sxs-lookup"><span data-stu-id="f6796-144">Additional resources:</span></span>

- <span data-ttu-id="f6796-145">WLANv1プロファイル スキーマ: [[MS-GPWL]: ワイヤレス LAN プロファイル V1 スキーマ | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="f6796-145">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="f6796-146">EAP-TLS スキーマ: [[MS-GPWL]: Microsoft EAP TLS スキーマ | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="f6796-146">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

### <a name="eap-troubleshooting"></a><span data-ttu-id="f6796-147">EAP のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f6796-147">EAP Troubleshooting</span></span>

1. <span data-ttu-id="f6796-148">Wi-Fi プロファイルが正しく設定されているかどうかを再確認します。</span><span class="sxs-lookup"><span data-stu-id="f6796-148">Double check Wi-Fi profile has right settings:</span></span>
   1. <span data-ttu-id="f6796-149">EAP の種類が正しく構成されているか。一般的な EAP の種類は、EAP-TLS (13)、EAP-TTLS (21)、および PEAP (25) です。</span><span class="sxs-lookup"><span data-stu-id="f6796-149">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
   1. <span data-ttu-id="f6796-150">Wi-Fi SSID 名は正しく、HEX 文字列と一致しているか。</span><span class="sxs-lookup"><span data-stu-id="f6796-150">Wi-Fi SSID name is right and matches with HEX string.</span></span>
   1. <span data-ttu-id="f6796-151">EAP-TLS の場合、TrustedRootCA に、サーバーの信頼されたルート CA 証明書の SHA-1 ハッシュが含まれるかどうか。</span><span class="sxs-lookup"><span data-stu-id="f6796-151">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server&#39;s trusted root CA certificate.</span></span> <span data-ttu-id="f6796-152">Windows PC で &quot;certutil.exe -dump cert\_file\_name&quot; コマンドを実行すると、証明書の SHA-1 ハッシュ文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6796-152">On Windows PC &quot;certutil.exe -dump cert\_file\_name&quot; command will show a certificate&#39;s SHA-1 hash string.</span></span>
1. <span data-ttu-id="f6796-153">アクセス ポイントまたはコントローラーまたは AAA サーバー ログでネットワーク パケット キャプチャを収集して、EAP セッションが失敗した場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="f6796-153">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
   1. <span data-ttu-id="f6796-154">HoloLens によって提供される EAP ID が想定されていない場合は、Wi-Fi プロファイルまたはクライアント証明書を通じて、ID が正しくプロビジョニングされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f6796-154">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
   1. <span data-ttu-id="f6796-155">サーバーが HoloLens クライアント証明書を拒否した場合は、必要なクライアント証明書がデバイスでプロビジョニングされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f6796-155">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
   1. <span data-ttu-id="f6796-156">HoloLens がサーバー証明書を拒否した場合は、サーバー ルート CA 証明書が HoloLens でプロビジョニングされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f6796-156">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
1. <span data-ttu-id="f6796-157">エンタープライズ プロファイルが Wi-Fi プロビジョニング パッケージによってプロビジョニングされている場合は、Windows 10 PC にプロビジョニング パッケージを適用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="f6796-157">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="f6796-158">Windows 10 PC でもエラーが発生する場合は、「[Windows クライアント 802.1X 認証に関するトラブルシューティング ガイド](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication)」に従ってください。</span><span class="sxs-lookup"><span data-stu-id="f6796-158">If it also fails on Windows 10 PC, follow the [Windows client 802.1X authentication troubleshooting guide](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span></span>
1. <span data-ttu-id="f6796-159">[フィードバック Hub](https://docs.microsoft.com/hololens/hololens-feedback)からフィードバックを送信してください。</span><span class="sxs-lookup"><span data-stu-id="f6796-159">Send us feedback through [Feedback Hub](https://docs.microsoft.com/hololens/hololens-feedback).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="f6796-160">その他のリソース:</span><span class="sxs-lookup"><span data-stu-id="f6796-160">Additional resources:</span></span>
- [<span data-ttu-id="f6796-161">Windows デバイスから Wi-Fi 設定をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="f6796-161">Export Wi-Fi settings from a Windows device</span></span>](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <a name="vpn"></a><span data-ttu-id="f6796-162">VPN</span><span class="sxs-lookup"><span data-stu-id="f6796-162">VPN</span></span>
<span data-ttu-id="f6796-163">VPN 接続を使用すると、より安全な接続と会社のネットワークやインターネットへのアクセスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="f6796-163">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="f6796-164">HoloLens 2 は、組み込み VPN クライアントおよびユニバーサル Windows プラットフォーム (UWP) VPN プラグインをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f6796-164">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="f6796-165">サポートされている組み込み VPN プロトコル:</span><span class="sxs-lookup"><span data-stu-id="f6796-165">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="f6796-166">IKEv2</span><span class="sxs-lookup"><span data-stu-id="f6796-166">IKEv2</span></span>
- <span data-ttu-id="f6796-167">L2TP</span><span class="sxs-lookup"><span data-stu-id="f6796-167">L2TP</span></span>
- <span data-ttu-id="f6796-168">PPTP</span><span class="sxs-lookup"><span data-stu-id="f6796-168">PPTP</span></span>

<span data-ttu-id="f6796-169">組み込みのVPN クライアントの認証に証明書を使用している場合は、必要なクライアント証明書をユーザー証明書ストアに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6796-169">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="f6796-170">サードパーティの VPN プラグインが HoloLens 2 をサポートしているかどうかを確認するには、[VPN アプリ] がある [ストア] に移動し、 ARM または ARM64 アーキテクチャ をサポートしているアプリの [システム要件ページ] に [HoloLens] が表示されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f6796-170">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="f6796-171">HoloLens は、サード パーティ VPN 用のユニバーサル Windows プラットフォーム アプリケーションのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f6796-171">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="f6796-172">VPN は、[Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 経由で MDM によって管理され、[Vpnv2-csp ポリシー](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)を使用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="f6796-172">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="f6796-173">[これらのガイド](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)を使用して [VPN を構成する方法](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn)の詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f6796-173">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="f6796-174">UI 経由の VPN</span><span class="sxs-lookup"><span data-stu-id="f6796-174">VPN via UI</span></span>

<span data-ttu-id="f6796-175">VPN は既定で有効になっていませんが、**設定** アプリを開き、**[ネットワークとインターネット]、[VPN]** の順に移動して、手動で有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f6796-175">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="f6796-176">VPN プロバイダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f6796-176">Select a VPN provider.</span></span>
1. <span data-ttu-id="f6796-177">接続名を作成します。</span><span class="sxs-lookup"><span data-stu-id="f6796-177">Create a connection name.</span></span> 
1. <span data-ttu-id="f6796-178">サーバー名またはアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="f6796-178">Enter your server name or address.</span></span>
1. <span data-ttu-id="f6796-179">VPN の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6796-179">Select the VPN type.</span></span>
1. <span data-ttu-id="f6796-180">サインイン情報の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6796-180">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="f6796-181">必要に応じて、ユーザー名とパスワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="f6796-181">Optionally add user name and password.</span></span>
1. <span data-ttu-id="f6796-182">VPN 設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="f6796-182">Apply the VPN settings.</span></span> 

![HoloLens VPN の設定](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="f6796-184">プロビジョニング パッケージによる VPN の設定</span><span class="sxs-lookup"><span data-stu-id="f6796-184">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="f6796-185">Windows Holographic バージョン 20H2 では、VPN 接続のプロキシ構成の問題が修正されました。</span><span class="sxs-lookup"><span data-stu-id="f6796-185">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="f6796-186">このフローを使う場合は、このビルドにデバイスをアップグレードすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="f6796-186">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="f6796-187">Windows 構成デザイナーを起動します。</span><span class="sxs-lookup"><span data-stu-id="f6796-187">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="f6796-188">**[HoloLens デバイスのプロビジョニング]** をクリックして対象のデバイスを選択してから **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6796-188">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="f6796-189">パッケージ名とパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="f6796-189">Enter package name and path.</span></span>
1. <span data-ttu-id="f6796-190">**[詳細エディターに切り替える]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6796-190">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="f6796-191">**[ランタイム設定]** -> **[ConnectivityProfiles]** -> **[VPN]** -> **[VPNSettings]** の順に開きます。</span><span class="sxs-lookup"><span data-stu-id="f6796-191">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="f6796-192">VPNProfileName を構成する</span><span class="sxs-lookup"><span data-stu-id="f6796-192">Configure VPNProfileName</span></span>
1. <span data-ttu-id="f6796-193">ProfileType を **[ネイティブ]** または **[サードパーティ]** から選択します。</span><span class="sxs-lookup"><span data-stu-id="f6796-193">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="f6796-194">ネイティブ プロファイルの場合、**[NativeProtocolType]** を選択し、サーバー、ルーティング ポリシー、認証の種類、その他の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f6796-194">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="f6796-195">「サードパーティ」プロファイルの場合、サーバー URL、VPN プラグイン アプリ パッケージ ファミリ名 (事前に定義されている 3 つのみ) およびカスタム構成を構成します。</span><span class="sxs-lookup"><span data-stu-id="f6796-195">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="f6796-196">パッケージをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="f6796-196">Export your package.</span></span>
1. <span data-ttu-id="f6796-197">HoloLens を接続して、.ppkg ファイルをデバイスにコピーします。</span><span class="sxs-lookup"><span data-stu-id="f6796-197">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="f6796-198">HoloLens では、[スタート] メニューを開き、**[設定]** -> **[アカウント]** -> **[職場または学校にアクセスする]** -> **[プロビジョニング パッケージを追加または削除する]** の順に選択して、VPN パッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="f6796-198">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="f6796-199">Intune を使用した VPN のセットアップ</span><span class="sxs-lookup"><span data-stu-id="f6796-199">Setting up VPN via Intune</span></span>
<span data-ttu-id="f6796-200">Intune のドキュメントに従って、作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="f6796-200">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="f6796-201">これらの手順を実行するときは、HoloLens デバイスがサポートする組み込みの VPN プロトコルに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f6796-201">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="f6796-202">[Intune で VPN サーバーに接続するための VPN プロファイルを作成します](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="f6796-202">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="f6796-203">[Intune を使用して VPN 接続を追加するための Windows 10 および Windows Holographic デバイスを設定します](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="f6796-203">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="f6796-204">完了したら、[プロファイルを割り当てる](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)ことを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="f6796-204">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="f6796-205">サード パーティ MDM ソリューションを使用した VPN</span><span class="sxs-lookup"><span data-stu-id="f6796-205">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="f6796-206">サード パーティ VPN 接続の例:</span><span class="sxs-lookup"><span data-stu-id="f6796-206">3rd party VPN connection example:</span></span>
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

<span data-ttu-id="f6796-207">ネイティブ IKEv2 VPN の例:</span><span class="sxs-lookup"><span data-stu-id="f6796-207">Native IKEv2 VPN example:</span></span>
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="f6796-208">HoloLens (第 1 世代) での Wi-Fi の無効化</span><span class="sxs-lookup"><span data-stu-id="f6796-208">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="f6796-209">HoloLens での設定アプリの使用</span><span class="sxs-lookup"><span data-stu-id="f6796-209">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="f6796-210">**スタート** メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="f6796-210">Open the **Start** menu.</span></span>
1. <span data-ttu-id="f6796-211">**[スタート]** か、**スタート** メニューの右側にある **[すべてのアプリ]** の一覧から、**設定**アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="f6796-211">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="f6796-212">**設定**アプリは、ユーザーの正面に自動配置されます。</span><span class="sxs-lookup"><span data-stu-id="f6796-212">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="f6796-213">**[ネットワークとインターネット]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6796-213">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="f6796-214">[Wi-Fi] のスライダー スイッチを選択して、**[オフ]** の位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="f6796-214">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="f6796-215">これにより、Wi-Fi 無線の RF コンポーネントがオフになり、HoloLens 上の Wi-Fi 機能がすべて無効になります。</span><span class="sxs-lookup"><span data-stu-id="f6796-215">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="f6796-216">Wi-Fi 無線が無効になっている場合、HoloLens は[空間](hololens-spaces.md)を自動的に読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="f6796-216">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="f6796-217">スライダー スイッチを **[オン]** の位置に移動して Wi-Fi 無線を有効にし、Microsoft HoloLens に Wi-Fi 機能を復元します。</span><span class="sxs-lookup"><span data-stu-id="f6796-217">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="f6796-218">選択した Wi-Fi 無線の状態 (**[オン]** または **[オフ]**) は、再起動しても維持されます。</span><span class="sxs-lookup"><span data-stu-id="f6796-218">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="f6796-219">Wi-Fi ネットワーク上での HoloLens の IP アドレスの識別</span><span class="sxs-lookup"><span data-stu-id="f6796-219">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="f6796-220">設定アプリを使用する</span><span class="sxs-lookup"><span data-stu-id="f6796-220">By using the Settings app</span></span>

1. <span data-ttu-id="f6796-221">**スタート** メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="f6796-221">Open the **Start** menu.</span></span>
1. <span data-ttu-id="f6796-222">**[スタート]** か、**スタート** メニューの右側にある **[すべてのアプリ]** の一覧から、**設定**アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="f6796-222">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="f6796-223">**設定**アプリは、ユーザーの正面に自動配置されます。</span><span class="sxs-lookup"><span data-stu-id="f6796-223">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="f6796-224">**[ネットワークとインターネット]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6796-224">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="f6796-225">使用可能な Wi-Fi ネットワークの下までスクロールし、**[ハードウェアのプロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6796-225">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Wi-Fi 設定の [ハードウェア プロパティ]](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="f6796-227">IP アドレスは **[IPv4 アドレス]** の横に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6796-227">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="f6796-228">音声コマンドを使用する</span><span class="sxs-lookup"><span data-stu-id="f6796-228">By using voice commands</span></span>

<span data-ttu-id="f6796-229">使用しているデバイスに応じて、組み込み音声コマンドや Cortana を使用して IP アドレスを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="f6796-229">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="f6796-230">ビルドで[19041.1103](hololens-release-notes.md#windows-holographic-version-2004)の後に、"IP アドレスを教えて" と話します。</span><span class="sxs-lookup"><span data-stu-id="f6796-230">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="f6796-231">すると、それが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6796-231">and it will be displayed.</span></span> <span data-ttu-id="f6796-232">以前のビルドまたは HoloLens (第１世代) では、「コルタナさん、IP アドレスを教えて」 と言います。</span><span class="sxs-lookup"><span data-stu-id="f6796-232">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="f6796-233">Cortana によって IP アドレスの表示と読み上げが行われます。</span><span class="sxs-lookup"><span data-stu-id="f6796-233">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="f6796-234">Windows デバイス ポータルを使用する</span><span class="sxs-lookup"><span data-stu-id="f6796-234">By using Windows Device Portal</span></span>

1. <span data-ttu-id="f6796-235">PC の Web ブラウザーで[デバイス ポータル](/windows/mixed-reality/using-the-windows-device-portal.md#networking)を開きます。</span><span class="sxs-lookup"><span data-stu-id="f6796-235">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="f6796-236">**[ネットワーク]** セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="f6796-236">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="f6796-237">このセクションには、IP アドレスとその他のネットワーク情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6796-237">This section displays your IP address and other network information.</span></span> <span data-ttu-id="f6796-238">この方法を使用すると、開発用 PC の IP アドレスをコピーして貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="f6796-238">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
