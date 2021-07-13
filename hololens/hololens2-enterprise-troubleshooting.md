---
title: HoloLens 2 の実装とマネージド デバイスのトラブルシューティング
description: エンタープライズ環境における HoloLens 2 デバイスのトラブルシューティング
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: トラブルシューティング
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961501"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="aa77a-104">実装とマネージド デバイスのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="aa77a-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="aa77a-105">この記事では、HoloLens 2 の実装と管理について問題を解決する方法、または質問に回答する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aa77a-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="aa77a-106">トラブルシューティングの手順を開始する前に、可能であれば、デバイスのバッテリ容量が **20 - 40%** 残っていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="aa77a-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="aa77a-107">電源 ボタンの下 にある[バッテリ インジケーター ライト](hololens2-setup.md#lights-that-indicate-the-battery-level)により、デバイスにログインせずにバッテリ容量を簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="aa77a-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="aa77a-108">EAP のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="aa77a-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="aa77a-109">Wi-Fi のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="aa77a-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="aa77a-110">ネットワークのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="aa77a-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="aa77a-111">以前にセットアップした HoloLens デバイスにサインインできない</span><span class="sxs-lookup"><span data-stu-id="aa77a-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="aa77a-112">Windows Holographic 21H1 への更新後ログインできない</span><span class="sxs-lookup"><span data-stu-id="aa77a-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="aa77a-113">Autopilot のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="aa77a-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="aa77a-114">マネージド HoloLens デバイスに関する FAQ</span><span class="sxs-lookup"><span data-stu-id="aa77a-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="aa77a-115">EAP のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="aa77a-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="aa77a-116">Wi-Fi プロファイルが正しく設定されているかどうかを再確認します。</span><span class="sxs-lookup"><span data-stu-id="aa77a-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="aa77a-117">EAP の種類が正しく構成されているか。一般的な EAP の種類は、EAP-TLS (13)、EAP-TTLS (21)、および PEAP (25) です。</span><span class="sxs-lookup"><span data-stu-id="aa77a-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="aa77a-118">Wi-Fi SSID 名は正しく、HEX 文字列と一致しているか。</span><span class="sxs-lookup"><span data-stu-id="aa77a-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="aa77a-119">EAP-TLS の場合、TrustedRootCA に、サーバーの信頼されたルート CA 証明書の SHA-1 ハッシュが含まれるかどうか。</span><span class="sxs-lookup"><span data-stu-id="aa77a-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="aa77a-120">Windows PC 上では、"certutil.exe -dump cert_file_name" コマンドを実行すると、証明書の SHA-1 ハッシュ文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa77a-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="aa77a-121">アクセス ポイントまたはコントローラーまたは AAA サーバー ログでネットワーク パケット キャプチャを収集して、EAP セッションが失敗した場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="aa77a-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="aa77a-122">HoloLens によって提供される EAP ID が想定されていない場合は、Wi-Fi プロファイルまたはクライアント証明書を通じて、ID が正しくプロビジョニングされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="aa77a-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="aa77a-123">サーバーが HoloLens クライアント証明書を拒否した場合は、必要なクライアント証明書がデバイスでプロビジョニングされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="aa77a-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="aa77a-124">HoloLens がサーバー証明書を拒否した場合は、サーバー ルート CA 証明書が HoloLens でプロビジョニングされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="aa77a-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="aa77a-125">エンタープライズ プロファイルが Wi-Fi プロビジョニング パッケージによってプロビジョニングされている場合は、Windows 10 PC にプロビジョニング パッケージを適用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="aa77a-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="aa77a-126">Windows 10 PC でも失敗する場合は、Windows クライアントの 802.1X 認証ガイドに従ってください。</span><span class="sxs-lookup"><span data-stu-id="aa77a-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="aa77a-127">フィードバック Hub からフィードバックを送信してください。</span><span class="sxs-lookup"><span data-stu-id="aa77a-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="aa77a-128">一覧に戻る</span><span class="sxs-lookup"><span data-stu-id="aa77a-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="aa77a-129">Wi-Fi のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="aa77a-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="aa77a-130">HoloLens を Wi-Fi ネットワークに接続できない場合は、以下を試してください。</span><span class="sxs-lookup"><span data-stu-id="aa77a-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="aa77a-131">Wi-Fi がオンになっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="aa77a-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="aa77a-132">確認するには、スタート ジェスチャを使用して、[設定] > [ネットワークとインターネット] > [Wi-Fi] を選択します。</span><span class="sxs-lookup"><span data-stu-id="aa77a-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="aa77a-133">Wi-Fi がオンである場合は、オフにしてから、もう一度オンにしてみてください。</span><span class="sxs-lookup"><span data-stu-id="aa77a-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="aa77a-134">ルーターまたはアクセス ポイントに PC を近づけます。</span><span class="sxs-lookup"><span data-stu-id="aa77a-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="aa77a-135">Wi-Fi ルーターを再起動し、その後で、HoloLens を再起動します。</span><span class="sxs-lookup"><span data-stu-id="aa77a-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="aa77a-136">接続を再試行してください。</span><span class="sxs-lookup"><span data-stu-id="aa77a-136">Try connecting again.</span></span>
4. <span data-ttu-id="aa77a-137">これらのいずれも機能しない場合は、ルーターのファームウェアが最新であるか確認します。</span><span class="sxs-lookup"><span data-stu-id="aa77a-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="aa77a-138">この情報は、製造元の Web サイトで見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="aa77a-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="aa77a-139">デバイスのエンタープライズ アカウントまたは組織アカウントにサインインするときに、ポリシーが IT 管理者によって構成されている場合、モバイル デバイス管理 (MDM) ポリシーも適用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="aa77a-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="network-troubleshooting"></a><span data-ttu-id="aa77a-140">ネットワークのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="aa77a-140">Network Troubleshooting</span></span>
<span data-ttu-id="aa77a-141">ネットワークの問題が組織内で HoloLens 2 を正常にデプロイして使用するための障害である場合は、Fiddler と Wireshark という 2 つのよく知られたネットワーク診断ツールが、問題のスキャン、診断、および特定にどのように役立つのか確認してください。</span><span class="sxs-lookup"><span data-stu-id="aa77a-141">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, learn how two well-known network diagnostic tools, Fiddler and Wireshark can help you scan, diagnose, and identify problems.</span></span> <span data-ttu-id="aa77a-142">詳細については、 [このブログ](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa77a-142">Check out this [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) for more details.</span></span>

[<span data-ttu-id="aa77a-143">一覧に戻る</span><span class="sxs-lookup"><span data-stu-id="aa77a-143">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="aa77a-144">以前にセットアップした HoloLens デバイスにサインインできない</span><span class="sxs-lookup"><span data-stu-id="aa77a-144">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="aa77a-145">クライアントや元従業員用など、デバイスが誰か他の人に設定されていており、デバイスのロックを解除するためのパスワードを持ってない場合は、Intune を使用してデバイスをリモートで[ワイプ](https://docs.microsoft.com/intune/remote-actions/devices-wipe)できます。</span><span class="sxs-lookup"><span data-stu-id="aa77a-145">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](https://docs.microsoft.com/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="aa77a-146">その後、デバイス自体が再フラッシュされます。</span><span class="sxs-lookup"><span data-stu-id="aa77a-146">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="aa77a-147">デバイスをワイプする場合は、**登録状態を保持 し、ユーザー アカウント** をオフのままにします。</span><span class="sxs-lookup"><span data-stu-id="aa77a-147">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>
[<span data-ttu-id="aa77a-148">一覧に戻る</span><span class="sxs-lookup"><span data-stu-id="aa77a-148">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="aa77a-149">Windows Holographic 21H1 への更新後ログインできない</span><span class="sxs-lookup"><span data-stu-id="aa77a-149">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="aa77a-150">現象</span><span class="sxs-lookup"><span data-stu-id="aa77a-150">Symptoms</span></span>
- <span data-ttu-id="aa77a-151">正しい PIN を入力した後、ログオンに PIN を使用すると失敗します。</span><span class="sxs-lookup"><span data-stu-id="aa77a-151">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="aa77a-152">Web ページで正常にサインインした後、Web ログオン方法を使用すると失敗します。</span><span class="sxs-lookup"><span data-stu-id="aa77a-152">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="aa77a-153">デバイスは[[Azure portal]](https://portal.azure.com/) -> [Azure Active Directory] -> で [Azure AD joined] として一覧表示されていません。</span><span class="sxs-lookup"><span data-stu-id="aa77a-153">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="aa77a-154">原因</span><span class="sxs-lookup"><span data-stu-id="aa77a-154">Cause</span></span>
<span data-ttu-id="aa77a-155">影響を受けたデバイスが、Azure AD テナントから削除された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="aa77a-155">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="aa77a-156">たとえば、これは次の理由で発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="aa77a-156">For example, this may happen because:</span></span>

- <span data-ttu-id="aa77a-157">管理者またはユーザーが Azure portal で、または PowerShell を使用してデバイスを削除した。</span><span class="sxs-lookup"><span data-stu-id="aa77a-157">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="aa77a-158">非アクティブであるため、デバイスが Azure AD テナントから削除された。</span><span class="sxs-lookup"><span data-stu-id="aa77a-158">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="aa77a-159">効率的に管理される環境の場合、通常、IT 管理者は、[古い非アクティブなデバイスを Azure AD テナントから削除することをお勧めします](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices)。</span><span class="sxs-lookup"><span data-stu-id="aa77a-159">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="aa77a-160">影響を受けたデバイスが、削除された後に Azure AD テナントに再度接続しようとすると、Azure AD を使用した認証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="aa77a-160">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="aa77a-161">PIN によるキャッシュされたログオンでは引き続きユーザーのログオンが許可されるので、この効果は多くの場合、デバイスのユーザーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="aa77a-161">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="aa77a-162">対応策</span><span class="sxs-lookup"><span data-stu-id="aa77a-162">Mitigation</span></span>
<span data-ttu-id="aa77a-163">現在、削除された HoloLens デバイスを Azure AD に戻す方法はありません。</span><span class="sxs-lookup"><span data-stu-id="aa77a-163">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="aa77a-164">影響を受けるデバイスは、[デバイス の再フラッシュ](hololens-recovery.md#clean-reflash-the-device)に関する手順に従って 、クリーンな再フラッシュを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa77a-164">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="aa77a-165">Autopilot のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="aa77a-165">Autopilot Troubleshooting</span></span>

<span data-ttu-id="aa77a-166">以下の記事は、Autopilot に関する問題の詳細情報を参照してトラブルシューティングを行う場合に役立つリソースです。ただし、これらの記事は、Windows 10 のデスクトップ版を使用しており、HoloLens には適用されない情報もあることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="aa77a-166">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="aa77a-167">Windows Autopilot - 既知の問題</span><span class="sxs-lookup"><span data-stu-id="aa77a-167">Windows Autopilot - known issues</span></span>](https://docs.microsoft.com/mem/autopilot/known-issues)
- [<span data-ttu-id="aa77a-168">Microsoft Intune での Windows デバイスの登録に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="aa77a-168">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="aa77a-169">Windows Autopilot - ポリシーの競合</span><span class="sxs-lookup"><span data-stu-id="aa77a-169">Windows Autopilot - Policy Conflicts</span></span>](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="aa77a-170">マネージド HoloLens デバイスに関する FAQ</span><span class="sxs-lookup"><span data-stu-id="aa77a-170">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="aa77a-171">System Center Configuration Manager (SCCM) を使用して HoloLens デバイスを管理できますか?</span><span class="sxs-lookup"><span data-stu-id="aa77a-171">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="aa77a-172">いいえ。</span><span class="sxs-lookup"><span data-stu-id="aa77a-172">No.</span></span> <span data-ttu-id="aa77a-173">MDM システムを使用して、HoloLens デバイスを管理しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="aa77a-173">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="aa77a-174">HoloLens ユーザー アカウントの管理に Active Directory Domain Services (AD DS) を使用できますか?</span><span class="sxs-lookup"><span data-stu-id="aa77a-174">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="aa77a-175">いいえ。</span><span class="sxs-lookup"><span data-stu-id="aa77a-175">No.</span></span> <span data-ttu-id="aa77a-176">HoloLens デバイスのユーザー アカウントを管理するために Azure Active Directory (Azure AD) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa77a-176">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="aa77a-177">HoloLens は、Automated Data Capture Systems (ADCS) の自動登録は可能ですか?</span><span class="sxs-lookup"><span data-stu-id="aa77a-177">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="aa77a-178">いいえ。</span><span class="sxs-lookup"><span data-stu-id="aa77a-178">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="aa77a-179">HoloLens は統合 Windows 認証に参加できますか?</span><span class="sxs-lookup"><span data-stu-id="aa77a-179">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="aa77a-180">いいえ。</span><span class="sxs-lookup"><span data-stu-id="aa77a-180">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="aa77a-181">HoloLens はブランディングをサポートしていますか?</span><span class="sxs-lookup"><span data-stu-id="aa77a-181">Does HoloLens support branding?</span></span>

<span data-ttu-id="aa77a-182">いいえ。</span><span class="sxs-lookup"><span data-stu-id="aa77a-182">No.</span></span> <span data-ttu-id="aa77a-183">ただし、この件は、次のいずれかの方法を使用して回避できます。</span><span class="sxs-lookup"><span data-stu-id="aa77a-183">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="aa77a-184">カスタム アプリを作成し、キオスク [Kiosk モード を有効にします](hololens-kiosk.md)。</span><span class="sxs-lookup"><span data-stu-id="aa77a-184">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="aa77a-185">カスタム アプリにはブランドを設定し、他のアプリ (Remote Assist など) を起動できます。</span><span class="sxs-lookup"><span data-stu-id="aa77a-185">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="aa77a-186">Azure AD 内のユーザー プロファイルのすべての画像を会社のロゴに変更します。</span><span class="sxs-lookup"><span data-stu-id="aa77a-186">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="aa77a-187">ただし、これはすべてのシナリオで望ましいとは言えません。</span><span class="sxs-lookup"><span data-stu-id="aa77a-187">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="aa77a-188">HoloLens 2 にはどのようなログ機能がありますか?</span><span class="sxs-lookup"><span data-stu-id="aa77a-188">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="aa77a-189">ログ記録は、開発またはトラブルシューティングのシナリオでキャプチャできるトレース、またはデバイスが Microsoft サーバーに送信するテレメトリに限定されます。</span><span class="sxs-lookup"><span data-stu-id="aa77a-189">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="aa77a-190">HoloLens デバイスのセキュリティ保護に関する質問</span><span class="sxs-lookup"><span data-stu-id="aa77a-190">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="aa77a-191">[当社のHoloLens 2 セキュリティに関する情報](security-overview.md)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="aa77a-191">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="aa77a-192">HoloLens の第 1 世代については、[この FAQ ](hololens1-faq-security.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa77a-192">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.md).</span></span>

[<span data-ttu-id="aa77a-193">一覧に戻る</span><span class="sxs-lookup"><span data-stu-id="aa77a-193">Back to list</span></span>](#list)
