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
ms.openlocfilehash: 7932ba493f8434c0fa5fc7a0efdd4d43eedd51bd
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163039"
---
# <span data-ttu-id="0a160-104">HoloLens をネットワークに接続する</span><span class="sxs-lookup"><span data-stu-id="0a160-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="0a160-105">HoloLens で何らかの操作を実行するには、ほとんどの場合、ネットワークに接続している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a160-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="0a160-106">このガイドは次の作業に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0a160-106">This guide will help you:</span></span>

- <span data-ttu-id="0a160-107">Wi-Fi または (HoloLens 2 の場合のみ) Ethernet over USB-C を使用してネットワークに接続する</span><span class="sxs-lookup"><span data-stu-id="0a160-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="0a160-108">Wi-Fi を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="0a160-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="0a160-109">[HoloLens のオフライン使用](hololens-offline.md)に関する詳細情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a160-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="0a160-110">初めての接続</span><span class="sxs-lookup"><span data-stu-id="0a160-110">Connecting for the first time</span></span>

<span data-ttu-id="0a160-111">HoloLens を初めて使うときは、Wi-Fi ネットワークに接続するためのガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a160-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="0a160-112">セットアップ中に Wi-Fi に接続できない場合は、接続先がオープン ネットワーク、パスワードで保護されたネットワーク、またはキャプティブ ポータル ネットワークであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0a160-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="0a160-113">また、そのネットワークへの接続時に証明書の使用が求められないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0a160-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="0a160-114">セットアップの完了後は、他の種類の Wi-Fi ネットワークにも接続できます。</span><span class="sxs-lookup"><span data-stu-id="0a160-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="0a160-115">HoloLens 2 デバイスでは、[USB-C to Ethernet アダプターを使用](hololens-connect-devices.md#hololens-2-connect-usb-c-devices)して、直接 Wi-Fi に接続してデバイスのセットアップを支援する こともできます。</span><span class="sxs-lookup"><span data-stu-id="0a160-115">On HoloLens 2 devices a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="0a160-116">デバイスを設定した後は、アダプターを使い続けることもできますが、アダプターから切断して、[セットアップ後にデバイスを Wi-Fi に接続する](hololens-network.md#connecting-to-wi-fi-after-setup)こともできます。</span><span class="sxs-lookup"><span data-stu-id="0a160-116">Once the device has been set up a user may continue to user the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <span data-ttu-id="0a160-117">セットアップ後の Wi-Fi 接続</span><span class="sxs-lookup"><span data-stu-id="0a160-117">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="0a160-118">**スタート ジェスチャ** を事前に準備し、**設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a160-118">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="0a160-119">設定アプリは、ユーザーの正面に自動配置されます。</span><span class="sxs-lookup"><span data-stu-id="0a160-119">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="0a160-120">**[ネットワークとインターネット]** > **[Wi-Fi]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="0a160-120">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="0a160-121">Wi-Fi がオンになっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0a160-121">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="0a160-122">目的のネットワークが表示されない場合は、一覧を下方向へスクロールします。</span><span class="sxs-lookup"><span data-stu-id="0a160-122">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="0a160-123">ネットワークを選択し、**[接続]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a160-123">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="0a160-124">ネットワーク パスワードを求めるメッセージが表示されたら、入力して **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a160-124">If you are prompted for a network password type it and then select **Next**.</span></span>

<span data-ttu-id="0a160-125">HoloLens には、802.11ac 対応の 2x2 Wi-Fi 無線が装備されています。</span><span class="sxs-lookup"><span data-stu-id="0a160-125">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="0a160-126">HoloLens から Wi-Fi ネットワークへの接続は、Windows 10 デスクトップまたはモバイル デバイスから Wi-Fi ネットワークへの接続と似ています。</span><span class="sxs-lookup"><span data-stu-id="0a160-126">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![HoloLens の Wi-Fi 設定](./images/wifi-hololens-600px.jpg)

<span data-ttu-id="0a160-128">**スタート** メニューで Wi-Fi の状態を確認することにより、Wi-Fi ネットワークへの接続を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="0a160-128">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="0a160-129">**スタート** メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="0a160-129">Open the **Start** menu.</span></span>
1. <span data-ttu-id="0a160-130">**スタート** メニューの左上で Wi-Fi の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="0a160-130">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="0a160-131">Wi-Fi の状態と、接続されているネットワークの SSID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a160-131">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="0a160-132">Wi-Fi への接続のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0a160-132">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="0a160-133">Wi-Fi への接続で問題が発生した場合は、「[Wi-Fi に接続できない](./hololens-faq.md#i-cant-connect-to-wi-fi)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0a160-133">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="0a160-134">デバイスのエンタープライズ アカウントまたは組織アカウントにサインインするときに、ポリシーが IT 管理者によって構成されている場合、モバイル デバイス管理 (MDM) ポリシーも適用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="0a160-134">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="0a160-135">HoloLens をエンタープライズ Wi-Fi ネットワークに接続する</span><span class="sxs-lookup"><span data-stu-id="0a160-135">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="0a160-136">エンタープライズ Wi-Fi プロファイルは、拡張認証プロトコル (EAP) を使って Wi-Fi 接続を認証します。</span><span class="sxs-lookup"><span data-stu-id="0a160-136">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="0a160-137">HoloLens エンタープライズ Wi-Fi プロファイルは、[Windows 構成デザイナー](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)によって作成された MDM またはプロビジョニング パッケージを介して構成できます。</span><span class="sxs-lookup"><span data-stu-id="0a160-137">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="0a160-138">Microsoft Intune 管理対象デバイスの場合、構成手順については [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a160-138">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="0a160-139">WCD で Wi-Fi プロビジョニング パッケージを作成するには、事前に構成された Wi-Fi プロファイルの .xml ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="0a160-139">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="0a160-140">以下は、EAP-TLS 認証を使用した WPA2-Enterprise の Wi-Fi プロファイルの例です。</span><span class="sxs-lookup"><span data-stu-id="0a160-140">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

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


<span data-ttu-id="0a160-141">サーバー ルート CA 証明書とクライアント証明書は、EAP の種類に応じて、デバイスにプロビジョニングされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a160-141">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="0a160-142">その他のリソース:</span><span class="sxs-lookup"><span data-stu-id="0a160-142">Additional resources:</span></span>

- <span data-ttu-id="0a160-143">WLANv1プロファイル スキーマ: [[MS-GPWL]: ワイヤレス LAN プロファイル V1 スキーマ | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="0a160-143">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="0a160-144">EAP-TLS スキーマ: [[MS-GPWL]: Microsoft EAP TLS スキーマ | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="0a160-144">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

### <span data-ttu-id="0a160-145">EAP のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0a160-145">EAP Troubleshooting</span></span>

1. <span data-ttu-id="0a160-146">Wi-Fi プロファイルが正しく設定されているかどうかを再確認します。</span><span class="sxs-lookup"><span data-stu-id="0a160-146">Double check Wi-Fi profile has right settings:</span></span>
   1. <span data-ttu-id="0a160-147">EAP の種類が正しく構成されているか。一般的な EAP の種類は、EAP-TLS (13)、EAP-TTLS (21)、および PEAP (25) です。</span><span class="sxs-lookup"><span data-stu-id="0a160-147">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
   1. <span data-ttu-id="0a160-148">Wi-Fi SSID 名は正しく、HEX 文字列と一致しているか。</span><span class="sxs-lookup"><span data-stu-id="0a160-148">Wi-Fi SSID name is right and matches with HEX string.</span></span>
   1. <span data-ttu-id="0a160-149">EAP-TLS の場合、TrustedRootCA に、サーバーの信頼されたルート CA 証明書の SHA-1 ハッシュが含まれるかどうか。</span><span class="sxs-lookup"><span data-stu-id="0a160-149">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server&#39;s trusted root CA certificate.</span></span> <span data-ttu-id="0a160-150">Windows PC で &quot;certutil.exe -dump cert\_file\_name&quot; コマンドを実行すると、証明書の SHA-1 ハッシュ文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a160-150">On Windows PC &quot;certutil.exe -dump cert\_file\_name&quot; command will show a certificate&#39;s SHA-1 hash string.</span></span>
1. <span data-ttu-id="0a160-151">アクセス ポイントまたはコントローラーまたは AAA サーバー ログでネットワーク パケット キャプチャを収集して、EAP セッションが失敗した場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="0a160-151">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
   1. <span data-ttu-id="0a160-152">HoloLens によって提供される EAP ID が想定されていない場合は、Wi-Fi プロファイルまたはクライアント証明書を通じて、ID が正しくプロビジョニングされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0a160-152">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
   1. <span data-ttu-id="0a160-153">サーバーが HoloLens クライアント証明書を拒否した場合は、必要なクライアント証明書がデバイスでプロビジョニングされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0a160-153">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
   1. <span data-ttu-id="0a160-154">HoloLens がサーバー証明書を拒否した場合は、サーバー ルート CA 証明書が HoloLens でプロビジョニングされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0a160-154">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
1. <span data-ttu-id="0a160-155">エンタープライズ プロファイルが Wi-Fi プロビジョニング パッケージによってプロビジョニングされている場合は、Windows 10 PC にプロビジョニング パッケージを適用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="0a160-155">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="0a160-156">Windows 10 PC でもエラーが発生する場合は、「[Windows クライアント 802.1X 認証に関するトラブルシューティング ガイド](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication)」に従ってください。</span><span class="sxs-lookup"><span data-stu-id="0a160-156">If it also fails on Windows 10 PC, follow the [Windows client 802.1X authentication troubleshooting guide](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span></span>
1. <span data-ttu-id="0a160-157">[フィードバック Hub](https://docs.microsoft.com/hololens/hololens-feedback)からフィードバックを送信してください。</span><span class="sxs-lookup"><span data-stu-id="0a160-157">Send us feedback through [Feedback Hub](https://docs.microsoft.com/hololens/hololens-feedback).</span></span>

### <span data-ttu-id="0a160-158">その他のリソース:</span><span class="sxs-lookup"><span data-stu-id="0a160-158">Additional resources:</span></span>
- [<span data-ttu-id="0a160-159">Windows デバイスから Wi-Fi 設定をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="0a160-159">Export Wi-Fi settings from a Windows device</span></span>](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <span data-ttu-id="0a160-160">VPN</span><span class="sxs-lookup"><span data-stu-id="0a160-160">VPN</span></span>
<span data-ttu-id="0a160-161">VPN 接続を使用すると、より安全な接続と会社のネットワークやインターネットへのアクセスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="0a160-161">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="0a160-162">HoloLens 2 は、組み込み VPN クライアントおよびユニバーサル Windows プラットフォーム (UWP) VPN プラグインをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0a160-162">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="0a160-163">サポートされている組み込み VPN プロトコル:</span><span class="sxs-lookup"><span data-stu-id="0a160-163">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="0a160-164">IKEv2</span><span class="sxs-lookup"><span data-stu-id="0a160-164">IKEv2</span></span>
- <span data-ttu-id="0a160-165">L2TP</span><span class="sxs-lookup"><span data-stu-id="0a160-165">L2TP</span></span>
- <span data-ttu-id="0a160-166">PPTP</span><span class="sxs-lookup"><span data-stu-id="0a160-166">PPTP</span></span>

<span data-ttu-id="0a160-167">組み込みのVPN クライアントの認証に証明書を使用している場合は、必要なクライアント証明書をユーザー証明書ストアに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a160-167">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="0a160-168">サードパーティの VPN プラグインが HoloLens 2 をサポートしているかどうかを確認するには、[VPN アプリ] がある [ストア] に移動し、 ARM または ARM64 アーキテクチャ をサポートしているアプリの [システム要件ページ] に [HoloLens] が表示されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0a160-168">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="0a160-169">HoloLens は、サード パーティ VPN 用のユニバーサル Windows プラットフォーム アプリケーションのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0a160-169">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="0a160-170">VPN は、[Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 経由で MDM によって管理され、[Vpnv2-csp ポリシー](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)を使用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="0a160-170">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="0a160-171">[これらのガイド](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)を使用して [VPN を構成する方法](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn)の詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0a160-171">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <span data-ttu-id="0a160-172">UI 経由の VPN</span><span class="sxs-lookup"><span data-stu-id="0a160-172">VPN via UI</span></span>

<span data-ttu-id="0a160-173">VPN は既定で有効になっていませんが、**設定** アプリを開き、**[ネットワークとインターネット]、[VPN]** の順に移動して、手動で有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0a160-173">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="0a160-174">VPN プロバイダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="0a160-174">Select a VPN provider.</span></span>
1. <span data-ttu-id="0a160-175">接続名を作成します。</span><span class="sxs-lookup"><span data-stu-id="0a160-175">Create a connection name.</span></span> 
1. <span data-ttu-id="0a160-176">サーバー名またはアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="0a160-176">Enter your server name or address.</span></span>
1. <span data-ttu-id="0a160-177">VPN の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a160-177">Select the VPN type.</span></span>
1. <span data-ttu-id="0a160-178">サインイン情報の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a160-178">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="0a160-179">必要に応じて、ユーザー名とパスワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="0a160-179">Optionally add user name and password.</span></span>
1. <span data-ttu-id="0a160-180">VPN 設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="0a160-180">Apply the VPN settings.</span></span> 

![HoloLens VPN の設定](./images/vpn-settings-ui.jpg)

### <span data-ttu-id="0a160-182">プロビジョニング パッケージによる VPN の設定</span><span class="sxs-lookup"><span data-stu-id="0a160-182">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="0a160-183">Windows Holographic バージョン 20H2 では、VPN 接続のプロキシ構成の問題が修正されました。</span><span class="sxs-lookup"><span data-stu-id="0a160-183">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="0a160-184">このフローを使う場合は、このビルドにデバイスをアップグレードすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="0a160-184">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="0a160-185">Windows 構成デザイナーを起動します。</span><span class="sxs-lookup"><span data-stu-id="0a160-185">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="0a160-186">**[HoloLens デバイスのプロビジョニング]** をクリックして対象のデバイスを選択してから **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a160-186">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="0a160-187">パッケージ名とパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="0a160-187">Enter package name and path.</span></span>
1. <span data-ttu-id="0a160-188">**[詳細エディターに切り替える]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0a160-188">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="0a160-189">**[ランタイム設定]** -> **[ConnectivityProfiles]** -> **[VPN]** -> **[VPNSettings]** の順に開きます。</span><span class="sxs-lookup"><span data-stu-id="0a160-189">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="0a160-190">VPNProfileName を構成する</span><span class="sxs-lookup"><span data-stu-id="0a160-190">Configure VPNProfileName</span></span>
1. <span data-ttu-id="0a160-191">ProfileType を **[ネイティブ]** または **[サードパーティ]** から選択します。</span><span class="sxs-lookup"><span data-stu-id="0a160-191">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="0a160-192">ネイティブ プロファイルの場合、**[NativeProtocolType]** を選択し、サーバー、ルーティング ポリシー、認証の種類、その他の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="0a160-192">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="0a160-193">「サードパーティ」プロファイルの場合、サーバー URL、VPN プラグイン アプリ パッケージ ファミリ名 (事前に定義されている 3 つのみ) およびカスタム構成を構成します。</span><span class="sxs-lookup"><span data-stu-id="0a160-193">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="0a160-194">パッケージをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="0a160-194">Export your package.</span></span>
1. <span data-ttu-id="0a160-195">HoloLens を接続して、.ppkg ファイルをデバイスにコピーします。</span><span class="sxs-lookup"><span data-stu-id="0a160-195">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="0a160-196">HoloLens では、[スタート] メニューを開き、**[設定]** -> **[アカウント]** -> **[職場または学校にアクセスする]** -> **[プロビジョニング パッケージを追加または削除する]** の順に選択して、VPN パッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="0a160-196">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <span data-ttu-id="0a160-197">Intune を使用した VPN のセットアップ</span><span class="sxs-lookup"><span data-stu-id="0a160-197">Setting up VPN via Intune</span></span>
<span data-ttu-id="0a160-198">Intune のドキュメントに従って、作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="0a160-198">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="0a160-199">これらの手順を実行するときは、HoloLens デバイスがサポートする組み込みの VPN プロトコルに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0a160-199">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="0a160-200">[Intune で VPN サーバーに接続するための VPN プロファイルを作成します](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="0a160-200">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="0a160-201">[Intune を使用して VPN 接続を追加するための Windows 10 および Windows Holographic デバイスを設定します](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="0a160-201">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="0a160-202">完了したら、[プロファイルを割り当てる](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)ことを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="0a160-202">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <span data-ttu-id="0a160-203">サード パーティ MDM ソリューションを使用した VPN</span><span class="sxs-lookup"><span data-stu-id="0a160-203">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="0a160-204">サード パーティ VPN 接続の例:</span><span class="sxs-lookup"><span data-stu-id="0a160-204">3rd party VPN connection example:</span></span>
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

<span data-ttu-id="0a160-205">ネイティブ IKEv2 VPN の例:</span><span class="sxs-lookup"><span data-stu-id="0a160-205">Native IKEv2 VPN example:</span></span>
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
## <span data-ttu-id="0a160-206">HoloLens (第 1 世代) での Wi-Fi の無効化</span><span class="sxs-lookup"><span data-stu-id="0a160-206">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="0a160-207">HoloLens での設定アプリの使用</span><span class="sxs-lookup"><span data-stu-id="0a160-207">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="0a160-208">**スタート** メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="0a160-208">Open the **Start** menu.</span></span>
1. <span data-ttu-id="0a160-209">**[スタート]** か、**スタート** メニューの右側にある **[すべてのアプリ]** の一覧から、**設定**アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="0a160-209">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="0a160-210">**設定**アプリは、ユーザーの正面に自動配置されます。</span><span class="sxs-lookup"><span data-stu-id="0a160-210">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="0a160-211">**[ネットワークとインターネット]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a160-211">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="0a160-212">[Wi-Fi] のスライダー スイッチを選択して、**[オフ]** の位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="0a160-212">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="0a160-213">これにより、Wi-Fi 無線の RF コンポーネントがオフになり、HoloLens 上の Wi-Fi 機能がすべて無効になります。</span><span class="sxs-lookup"><span data-stu-id="0a160-213">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="0a160-214">Wi-Fi 無線が無効になっている場合、HoloLens は[空間](hololens-spaces.md)を自動的に読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="0a160-214">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="0a160-215">スライダー スイッチを **[オン]** の位置に移動して Wi-Fi 無線を有効にし、Microsoft HoloLens に Wi-Fi 機能を復元します。</span><span class="sxs-lookup"><span data-stu-id="0a160-215">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="0a160-216">選択した Wi-Fi 無線の状態 (**[オン]** または **[オフ]**) は、再起動しても維持されます。</span><span class="sxs-lookup"><span data-stu-id="0a160-216">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="0a160-217">Wi-Fi ネットワーク上での HoloLens の IP アドレスの識別</span><span class="sxs-lookup"><span data-stu-id="0a160-217">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="0a160-218">設定アプリを使用する</span><span class="sxs-lookup"><span data-stu-id="0a160-218">By using the Settings app</span></span>

1. <span data-ttu-id="0a160-219">**スタート** メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="0a160-219">Open the **Start** menu.</span></span>
1. <span data-ttu-id="0a160-220">**[スタート]** か、**スタート** メニューの右側にある **[すべてのアプリ]** の一覧から、**設定**アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="0a160-220">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="0a160-221">**設定**アプリは、ユーザーの正面に自動配置されます。</span><span class="sxs-lookup"><span data-stu-id="0a160-221">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="0a160-222">**[ネットワークとインターネット]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a160-222">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="0a160-223">使用可能な Wi-Fi ネットワークの下までスクロールし、**[ハードウェアのプロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a160-223">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Wi-Fi 設定の [ハードウェア プロパティ]](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="0a160-225">IP アドレスは **[IPv4 アドレス]** の横に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a160-225">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="0a160-226">音声コマンドを使用する</span><span class="sxs-lookup"><span data-stu-id="0a160-226">By using voice commands</span></span>

<span data-ttu-id="0a160-227">使用しているデバイスに応じて、組み込み音声コマンドや Cortana を使用して IP アドレスを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="0a160-227">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="0a160-228">ビルドで[19041.1103](hololens-release-notes.md#windows-holographic-version-2004)の後に、"IP アドレスを教えて" と話します。</span><span class="sxs-lookup"><span data-stu-id="0a160-228">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="0a160-229">すると、それが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a160-229">and it will be displayed.</span></span> <span data-ttu-id="0a160-230">以前のビルドまたは HoloLens (第１世代) では、「コルタナさん、IP アドレスを教えて」 と言います。</span><span class="sxs-lookup"><span data-stu-id="0a160-230">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="0a160-231">Cortana によって IP アドレスの表示と読み上げが行われます。</span><span class="sxs-lookup"><span data-stu-id="0a160-231">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="0a160-232">Windows デバイス ポータルを使用する</span><span class="sxs-lookup"><span data-stu-id="0a160-232">By using Windows Device Portal</span></span>

1. <span data-ttu-id="0a160-233">PC の Web ブラウザーで[デバイス ポータル](/windows/mixed-reality/using-the-windows-device-portal.md#networking)を開きます。</span><span class="sxs-lookup"><span data-stu-id="0a160-233">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="0a160-234">**[ネットワーク]** セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="0a160-234">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="0a160-235">このセクションには、IP アドレスとその他のネットワーク情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a160-235">This section displays your IP address and other network information.</span></span> <span data-ttu-id="0a160-236">この方法を使用すると、開発用 PC の IP アドレスをコピーして貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="0a160-236">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
