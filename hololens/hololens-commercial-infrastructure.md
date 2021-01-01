---
title: HoloLens のインフラストラクチャ ガイドライン
description: HoloLens デバイスのインフラストラクチャ ガイドライン
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: a67aaa5df4c74531b5bed88abaa266b00de5c406
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253164"
---
# <span data-ttu-id="8fe63-103">HoloLens 向けにネットワークを構成する</span><span class="sxs-lookup"><span data-stu-id="8fe63-103">Configure Your Network for HoloLens</span></span>

<span data-ttu-id="8fe63-104">ドキュメントのこの部分には、次のユーザーが必要です。</span><span class="sxs-lookup"><span data-stu-id="8fe63-104">This portion of the document will require the following people:</span></span>

1. <span data-ttu-id="8fe63-105">プロキシ/ファイアウォールを変更するためのアクセス許可を持つネットワーク管理者</span><span class="sxs-lookup"><span data-stu-id="8fe63-105">Network Admin with permissions to make changes to the proxy/firewall</span></span>
2. <span data-ttu-id="8fe63-106">Azure Active Directory 管理者</span><span class="sxs-lookup"><span data-stu-id="8fe63-106">Azure Active Directory Admin</span></span>
3. <span data-ttu-id="8fe63-107">モバイル デバイス マネージャー管理者</span><span class="sxs-lookup"><span data-stu-id="8fe63-107">Mobile Device Manager Admin</span></span>

## <span data-ttu-id="8fe63-108">インフラストラクチャの要件</span><span class="sxs-lookup"><span data-stu-id="8fe63-108">Infrastructure Requirements</span></span>

<span data-ttu-id="8fe63-109">HoloLens は、本質的には、Azure と統合された Windows モバイル デバイスです。</span><span class="sxs-lookup"><span data-stu-id="8fe63-109">HoloLens is, at its core, a Windows mobile device integrated with Azure.</span></span>  <span data-ttu-id="8fe63-110">利用可能なワイヤレス ネットワーク (Wi-Fi) があり Microsoft サービスへアクセスできる商用環境で最もよく動作します。</span><span class="sxs-lookup"><span data-stu-id="8fe63-110">It works best in commercial environments with wireless network availability (wi-fi) and access to Microsoft services.</span></span>

<span data-ttu-id="8fe63-111">必須のクラウド サービス:</span><span class="sxs-lookup"><span data-stu-id="8fe63-111">Critical cloud services include:</span></span>

- <span data-ttu-id="8fe63-112">Azure active directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="8fe63-112">Azure active directory (Azure AD)</span></span>
- <span data-ttu-id="8fe63-113">Windows Update (WU)</span><span class="sxs-lookup"><span data-stu-id="8fe63-113">Windows Update (WU)</span></span>

<span data-ttu-id="8fe63-114">商業利用のお客様は、HoloLens デバイスの大規模な管理を行うには Enterprise Mobility Management (EMM) またはモバイル デバイス管理 (MDM) インフラストラクチャが必要になります。  </span><span class="sxs-lookup"><span data-stu-id="8fe63-114">Commercial customers will need enterprise mobility management (EMM) or mobile device management (MDM) infrastructure to manage HoloLens devices at scale.</span></span>  <span data-ttu-id="8fe63-115">このガイドでは例として [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) を使用しますが、Microsoft ポリシーをフル サポートしているプロバイダーは、いずれも HoloLens をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="8fe63-115">This guide uses [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) as an example, though any provider with full support for Microsoft Policy can support HoloLens.</span></span>  <span data-ttu-id="8fe63-116">使用しているモバイル デバイス管理プロバイダーに問い合わせて、HoloLens 2 をサポートしているかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8fe63-116">Ask your mobile device management provider if they support HoloLens 2.</span></span>

<span data-ttu-id="8fe63-117">HoloLens は、一部の、クラウドに接続されていないエクスペリエンスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8fe63-117">HoloLens does support a limited set of cloud disconnected experiences.</span></span>

### <span data-ttu-id="8fe63-118">ワイヤレス ネットワーク EAP のサポート</span><span class="sxs-lookup"><span data-stu-id="8fe63-118">Wireless network EAP support</span></span>

- <span data-ttu-id="8fe63-119">PEAP-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="8fe63-119">PEAP-MS-CHAPv2</span></span>
- <span data-ttu-id="8fe63-120">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="8fe63-120">PEAP-TLS</span></span>
- <span data-ttu-id="8fe63-121">TLS</span><span class="sxs-lookup"><span data-stu-id="8fe63-121">TLS</span></span>
- <span data-ttu-id="8fe63-122">TTLS-CHAP</span><span class="sxs-lookup"><span data-stu-id="8fe63-122">TTLS-CHAP</span></span>
- <span data-ttu-id="8fe63-123">TTLS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="8fe63-123">TTLS-CHAPv2</span></span>
- <span data-ttu-id="8fe63-124">TTLS-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="8fe63-124">TTLS-MS-CHAPv2</span></span>
- <span data-ttu-id="8fe63-125">TTLS-PAP</span><span class="sxs-lookup"><span data-stu-id="8fe63-125">TTLS-PAP</span></span>
- <span data-ttu-id="8fe63-126">TTLS-TLS</span><span class="sxs-lookup"><span data-stu-id="8fe63-126">TTLS-TLS</span></span>

### <span data-ttu-id="8fe63-127">HoloLens 固有のネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="8fe63-127">HoloLens Specific Network Requirements</span></span>

<span data-ttu-id="8fe63-128">エンドポイントの[このリスト](hololens-offline.md)がネットワーク ファイアウォールで許可されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8fe63-128">Make sure that [this list](hololens-offline.md) of endpoints are allowed on your network firewall.</span></span> <span data-ttu-id="8fe63-129">これにより、HoloLens が正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="8fe63-129">This will enable HoloLens to function properly.</span></span>

### <span data-ttu-id="8fe63-130">リモート アシスト固有のネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="8fe63-130">Remote Assist Specific Network Requirements</span></span>

1. <span data-ttu-id="8fe63-131">リモート アシストの最適なパフォーマンスのために推奨される帯域幅は 1.5 Mbps です。</span><span class="sxs-lookup"><span data-stu-id="8fe63-131">The recommended bandwidth for optimal performance of Remote Assist is 1.5Mbps.</span></span> <span data-ttu-id="8fe63-132">[こちら](https://docs.microsoft.com/MicrosoftTeams/prepare-network)で詳細なネットワーク要件と追加情報を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="8fe63-132">Detailed network requirements and additional information can be found [here](https://docs.microsoft.com/MicrosoftTeams/prepare-network).</span></span>
**<span data-ttu-id="8fe63-133">(ネットワーク速度が 1.5 Mbps 以上でないネットワークの場合でも、リモート アシストは機能します。</span><span class="sxs-lookup"><span data-stu-id="8fe63-133">(Please note, if you don't network have network speeds of at least 1.5Mbps, Remote Assist will still work.</span></span> <span data-ttu-id="8fe63-134">ただし、品質が低下する場合があります。)</span><span class="sxs-lookup"><span data-stu-id="8fe63-134">However, quality may suffer).</span></span>**
1. <span data-ttu-id="8fe63-135">これらのポートと URL がネットワーク ファイアウォールで許可されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8fe63-135">Make sure that these ports and URLs are allowed on your network firewall.</span></span> <span data-ttu-id="8fe63-136">これにより、Microsoft Teams が機能します。</span><span class="sxs-lookup"><span data-stu-id="8fe63-136">This will enable Microsoft Teams to function.</span></span> <span data-ttu-id="8fe63-137">最新のリストについては、[こちら](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe63-137">The latest list can be found [here](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

- <span data-ttu-id="8fe63-138">特定の「[リモート アシストのネットワーク要件](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)」の詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe63-138">Learn more about the specific [Network Requirements for Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span></span> 
- <span data-ttu-id="8fe63-139">[Microsoft Teams のために組織のネットワークを準備する](https://docs.microsoft.com/MicrosoftTeams/prepare-network)方法の詳細</span><span class="sxs-lookup"><span data-stu-id="8fe63-139">Learn more about how to [prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</span></span>

### <span data-ttu-id="8fe63-140">固有のネットワーク要件のガイド</span><span class="sxs-lookup"><span data-stu-id="8fe63-140">Guides Specific Network Requirements</span></span>

<span data-ttu-id="8fe63-141">ガイドには、アプリをダウンロードして使用するためのネットワーク アクセスのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="8fe63-141">Guides only require network access to download and use the app.</span></span>

## <span data-ttu-id="8fe63-142">Azure Active Directory ガイダンス</span><span class="sxs-lookup"><span data-stu-id="8fe63-142">Azure Active Directory Guidance</span></span>

> [!NOTE]
> <span data-ttu-id="8fe63-143">この手順は、会社が HoloLens を管理する予定にしている場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="8fe63-143">This step is only necessary if your company plans on managing the HoloLens.</span></span>

1. <span data-ttu-id="8fe63-144">Azure AD ライセンスがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8fe63-144">Ensure that you have an Azure AD License.</span></span>
<span data-ttu-id="8fe63-145">追加情報については、「[HoloLens Licenses Requirements (HoloLens のライセンス要件)](hololens-licenses-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe63-145">Please [HoloLens Licenses Requirements](hololens-licenses-requirements.md) for additional information.</span></span>

1. <span data-ttu-id="8fe63-146">自動登録を使用することを予定している場合は、[Azure AD の登録を構成する](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fe63-146">If you plan on using Auto Enrollment, you will have to [Configure Azure AD enrollment.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span></span>

1. <span data-ttu-id="8fe63-147">会社のユーザーが Azure Active Directory (Azure AD) に含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8fe63-147">Ensure that your company's users are in Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="8fe63-148">ユーザーを追加する手順については、[こちら](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe63-148">Instructions for adding users can be found [here](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory).</span></span>

1. <span data-ttu-id="8fe63-149">同様のライセンスが必要なユーザーは、同じグループに追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8fe63-149">We suggest that users who need similar licenses are added to the same group.</span></span>
    1. [<span data-ttu-id="8fe63-150">グループの作成</span><span class="sxs-lookup"><span data-stu-id="8fe63-150">Create a Group</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [<span data-ttu-id="8fe63-151">ユーザーをグループに追加する</span><span class="sxs-lookup"><span data-stu-id="8fe63-151">Add users to groups</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. <span data-ttu-id="8fe63-152">会社のユーザー (またはユーザー グループ) に必要なライセンスが割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8fe63-152">Ensure that your company's users (or group of users) are assigned the necessary licenses.</span></span>
<span data-ttu-id="8fe63-153">ライセンスを割り当てる方法は、[こちら](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="8fe63-153">Directions for assigning licenses can be found [here](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).</span></span>

1. <span data-ttu-id="8fe63-154">この手順は、ユーザーが各自の HoloLens またはモバイル デバイスを会社のネットワークに登録することを想定している場合にのみ実行してください (3 つのオプションがあります)。これらの手順により、会社のユーザー (またはユーザー グループ) がデバイスを追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8fe63-154">Only do this step if users are expected to enroll their HoloLens/Mobile device into you (There are three options) These steps ensure that your company's users (or a group of users) can add devices.</span></span>
    1. <span data-ttu-id="8fe63-155">**オプション 1:** デバイスを Azure AD に参加させる許可をすべてのユーザーに与えます。</span><span class="sxs-lookup"><span data-stu-id="8fe63-155">**Option 1:** Give all users permission to join devices to Azure AD.</span></span>
<span data-ttu-id="8fe63-156">**管理者として Azure ポータルにサインインする** > **Azure Active Directory** > **デバイス** > **デバイス設定** >
 **[ユーザーはデバイスを Azure AD に参加させることができます] を [*All (すべてのユーザー)*] に設定する**</span><span class="sxs-lookup"><span data-stu-id="8fe63-156">**Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
**Set Users may join devices to Azure AD to *All***</span></span>

    1. <span data-ttu-id="8fe63-157">**オプション 2:** デバイスを Azure AD に参加させる権限を、選択されたユーザーおよびグループに付与します。**Azure ポータルに管理者としてサインイン** > [**Azure Active Directory**] > [**デバイス**] > [**デバイス設定**] >
[**ユーザーはデバイスを Azure AD に参加させることができます] を [*Selected*] (選択されたユーザー) に設定**
![Azure AD に参加したデバイスの構成を示す画像</span><span class="sxs-lookup"><span data-stu-id="8fe63-157">**Option 2:** Give selected users/groups permission to join devices to Azure AD **Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
\*\*Set Users may join devices to Azure AD to \*Selected\*\*\*
![Image that shows Configuration of Azure AD Joined Devices</span></span>](images/azure-ad-image.png)

    1. <span data-ttu-id="8fe63-158">**オプション 3:** デバイスをドメインに参加させることをすべてのユーザーに対してブロックできます。</span><span class="sxs-lookup"><span data-stu-id="8fe63-158">**Option 3:** You can block all users from joining their devices to the domain.</span></span> <span data-ttu-id="8fe63-159">この場合、すべてのデバイスを手動で登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fe63-159">This means that all devices will need to be manually enrolled.</span></span>

## <span data-ttu-id="8fe63-160">モバイル デバイス マネージャーのガイダンス</span><span class="sxs-lookup"><span data-stu-id="8fe63-160">Mobile Device Manager Guidance</span></span>

### <span data-ttu-id="8fe63-161">継続的なデバイス管理</span><span class="sxs-lookup"><span data-stu-id="8fe63-161">Ongoing device management</span></span>

> [!NOTE]
> <span data-ttu-id="8fe63-162">この手順は、会社が HoloLens を管理する予定にしている場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="8fe63-162">This step is only necessary if your company plans to manage the HoloLens.</span></span>

<span data-ttu-id="8fe63-163">継続的なデバイス管理は、モバイル デバイスの管理インフラストラクチャに依存します。</span><span class="sxs-lookup"><span data-stu-id="8fe63-163">Ongoing device management will depend on your mobile device management infrastructure.</span></span>  <span data-ttu-id="8fe63-164">ほとんどのインフラストラクチャでは同様の機能が備わっていますが、ユーザー インターフェイスが大きく異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8fe63-164">Most have the same general functionality but the user interface may vary widely.</span></span>

1. <span data-ttu-id="8fe63-165">[CSP (構成サービス プロバイダー)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) を使用すると、ネットワーク上のデバイスの管理設定を作成および展開できます。</span><span class="sxs-lookup"><span data-stu-id="8fe63-165">[CSPs (Configuration Service Providers)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) allows you to create and deploy management settings for the devices on your network.</span></span> <span data-ttu-id="8fe63-166">HoloLens の CSP の一覧については、[ここ](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe63-166">A list of CSPs for HoloLens can be found [here](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).</span></span>

1. <span data-ttu-id="8fe63-167">[コンプライアンス ポリシー](https://docs.microsoft.com/intune/device-compliance-get-started)は、会社のインフラストラクチャに準拠するためにデバイスが満たす必要があるルールおよび設定 です。</span><span class="sxs-lookup"><span data-stu-id="8fe63-167">[Compliance policies](https://docs.microsoft.com/intune/device-compliance-get-started) are rules and settings that devices must meet to be compliant in your corporate infrastructure.</span></span> <span data-ttu-id="8fe63-168">非準拠デバイスについては、これらのポリシーを条件付きアクセスとともに使用して、会社のリソースへのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="8fe63-168">Use these policies with Conditional Access to block access to company resources for devices that are non-compliant.</span></span> <span data-ttu-id="8fe63-169">たとえば、Bitlocker が有効になっていることを要求するポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="8fe63-169">For example, you can create a policy that requires Bitlocker be enabled.</span></span>

1. <span data-ttu-id="8fe63-170">[コンプライアンス ポリシーの作成](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows)。</span><span class="sxs-lookup"><span data-stu-id="8fe63-170">[Create Compliance Policy](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).</span></span>

1. <span data-ttu-id="8fe63-171">条件付きアクセスは、モバイル デバイスおよびモバイル アプリケーションが会社のリソースにアクセスすることを許可または拒否します。</span><span class="sxs-lookup"><span data-stu-id="8fe63-171">Conditional Access allows/denies mobile devices and mobile applications from accessing company resources.</span></span> <span data-ttu-id="8fe63-172">役に立つと思われる 2 つのドキュメントとして、「[Plan your CA Deployment (CA 展開を計画する)](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)」と「[ベスト プラクティス](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices)」があります。</span><span class="sxs-lookup"><span data-stu-id="8fe63-172">Two documents you may find helpful are [Plan your CA Deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) and [Best Practices](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).</span></span>

1. <span data-ttu-id="8fe63-173">[こちらの記事](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business)では、 Intune の HoloLens 向けの管理ツールについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="8fe63-173">[This article](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) talks about Intune's management tools for HoloLens.</span></span>

1. [<span data-ttu-id="8fe63-174">デバイス プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="8fe63-174">Create a device profile</span></span>](https://docs.microsoft.com/intune/configuration/device-profile-create)

### <span data-ttu-id="8fe63-175">更新プログラムの管理</span><span class="sxs-lookup"><span data-stu-id="8fe63-175">Manage updates</span></span>

<span data-ttu-id="8fe63-176">Intune には、HoloLens 2 や HoloLens v1 (Holographic for Business を含む) などの Windows 10 デバイス向けに、更新リングと呼ばれる機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8fe63-176">Intune includes a feature called Update rings for Windows 10 devices, including HoloLens 2 and HoloLens v1 (with Holographic for Business).</span></span> <span data-ttu-id="8fe63-177">更新リングには、更新プログラムのインストール方法とタイミングを決めるための設定群が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8fe63-177">Update rings include a group of settings that determine how and when updates are installed.</span></span>

<span data-ttu-id="8fe63-178">たとえば、更新プログラムをインストールするためのメンテナンス期間を作成することも、更新プログラムのインストール後に再起動することもできます。</span><span class="sxs-lookup"><span data-stu-id="8fe63-178">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span>  <span data-ttu-id="8fe63-179">更新の準備ができるまで、更新プログラムを無期限に一時停止することもできます。</span><span class="sxs-lookup"><span data-stu-id="8fe63-179">You can also choose to pause updates indefinitely until you're ready to update.</span></span>

<span data-ttu-id="8fe63-180">詳細については、「[Intune を使用して更新リングを構成する](https://docs.microsoft.com/intune/windows-update-for-business-configure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe63-180">Read more about [configuring update rings with Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span></span>

### <span data-ttu-id="8fe63-181">アプリケーション管理</span><span class="sxs-lookup"><span data-stu-id="8fe63-181">Application management</span></span>

<span data-ttu-id="8fe63-182">HoloLens アプリケーションの管理には、次を使用します。</span><span class="sxs-lookup"><span data-stu-id="8fe63-182">Manage HoloLens applications through:</span></span>

1. <span data-ttu-id="8fe63-183">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="8fe63-183">Microsoft Store</span></span>  
  <span data-ttu-id="8fe63-184">Microsoft Store は、HoloLens でアプリケーションを配布および使用するための最善の方法です。</span><span class="sxs-lookup"><span data-stu-id="8fe63-184">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span></span>  <span data-ttu-id="8fe63-185">Store では、HoloLens の優れた基本的なアプリ群が既に提供されています。[独自のアプリを公開](https://docs.microsoft.com/windows/uwp/publish/)することもできます。</span><span class="sxs-lookup"><span data-stu-id="8fe63-185">There is a great set of core HoloLens applications already available in the store or you can [publish your own](https://docs.microsoft.com/windows/uwp/publish/).</span></span>  
  <span data-ttu-id="8fe63-186">Store 内のすべてのアプリケーションはすべてのユーザーに一般提供されていますが、お客様の要求を満たすアプリが見当たらない場合は、ビジネス向け Microsoft Store をご覧になってください。</span><span class="sxs-lookup"><span data-stu-id="8fe63-186">All applications in the store are available publicly to everyone, but if it isn't acceptable, checkout the Microsoft Store for Business.</span></span>  

1. [<span data-ttu-id="8fe63-187">ビジネス向け Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="8fe63-187">Microsoft Store for Business</span></span>](https://docs.microsoft.com/microsoft-store/)  
  <span data-ttu-id="8fe63-188">ビジネスおよび教育機関向け Microsoft Storeは、企業環境に合わせてカスタマイズされたストアです。</span><span class="sxs-lookup"><span data-stu-id="8fe63-188">Microsoft Store for Business and Education is a custom store for your corporate environment.</span></span>  <span data-ttu-id="8fe63-189">ビジネスおよび教育機関向け Microsoft Store を使用することで、Windows 10 および HoloLens に組み込まれている Microsoft Store を使用して、組織用にアプリの検索、取得、配布、管理を行えます。</span><span class="sxs-lookup"><span data-stu-id="8fe63-189">It lets you use the Microsoft Store built into Windows 10 and HoloLens to find, acquire, distribute, and manage apps for your organization.</span></span>  <span data-ttu-id="8fe63-190">一般的な環境ではなくお客様の商用環境に特化したアプリを展開することも可能になります。</span><span class="sxs-lookup"><span data-stu-id="8fe63-190">It also lets you deploy apps that are specific to your commercial environment but not to the world.</span></span>

1. <span data-ttu-id="8fe63-191">Intune またはその他のモバイル デバイス管理ソリューションを使用したアプリケーションの展開と管理</span><span class="sxs-lookup"><span data-stu-id="8fe63-191">Application deployment and management via Intune or another mobile device management solution</span></span>  
  <span data-ttu-id="8fe63-192">Intune を含むほとんどのモバイル デバイス管理ソリューションでは、基幹アプリケーションを登録済みのデバイス群に直接展開する方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="8fe63-192">Most mobile device management solutions, including Intune, provide a way to deploy line of business applications directly to a set of enrolled devices.</span></span>  <span data-ttu-id="8fe63-193">詳細については、[Intune アプリのインストール](https://docs.microsoft.com/intune/apps-deploy)についての記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe63-193">See this article for [Intune app install](https://docs.microsoft.com/intune/apps-deploy).</span></span>

1. <span data-ttu-id="8fe63-194">_非推奨_ Device Portal</span><span class="sxs-lookup"><span data-stu-id="8fe63-194">_not recommended_ Device Portal</span></span>  
  <span data-ttu-id="8fe63-195">アプリケーションは、Windows デバイス ポータルを使用して HoloLens に直接インストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8fe63-195">Applications can also be installed on HoloLens directly using the Windows Device Portal.</span></span>  <span data-ttu-id="8fe63-196">デバイス ポータルを使用するには開発者モードを有効にする必要があるため、この方法はお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="8fe63-196">This isn't recommended since Developer Mode has to be enabled to use the device portal.</span></span>

<span data-ttu-id="8fe63-197">[HoloLens にアプリをインストールする方法](https://docs.microsoft.com/hololens/hololens-install-apps)の詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8fe63-197">Read more about [installing apps on HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).</span></span>

### <span data-ttu-id="8fe63-198">証明書</span><span class="sxs-lookup"><span data-stu-id="8fe63-198">Certificates</span></span>

<span data-ttu-id="8fe63-199">証明書は、MDM プロバイダー経由で配布できます。</span><span class="sxs-lookup"><span data-stu-id="8fe63-199">You can distribute certificates through your MDM provider.</span></span> <span data-ttu-id="8fe63-200">会社で証明書が要求される場合、Intune では PKCS、PFX、および SCEP がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8fe63-200">If your company requires certificates, Intune supports PKCS, PFX, and SCEP.</span></span> <span data-ttu-id="8fe63-201">どの証明書が会社に適しているかについて理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="8fe63-201">It is important to understand which certificate is right for your company.</span></span> <span data-ttu-id="8fe63-202">最適な証明書を決定するには、[こちら](https://docs.microsoft.com/intune/protect/certificates-configure)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8fe63-202">Please visit [here](https://docs.microsoft.com/intune/protect/certificates-configure) to determine which cert is best for you.</span></span> <span data-ttu-id="8fe63-203">HoloLens 認証に証明書を使用する予定がある場合には、PFX または SCEP が最適です。</span><span class="sxs-lookup"><span data-stu-id="8fe63-203">If you plan to use certificates for HoloLens Authentication, PFX or SCEP may be right for you.</span></span>

<span data-ttu-id="8fe63-204">SCEP の手順については、[こちら](https://docs.microsoft.com/intune/protect/certificates-profile-scep)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8fe63-204">Steps for SCEP can be found [here](https://docs.microsoft.com/intune/protect/certificates-profile-scep).</span></span>

### <span data-ttu-id="8fe63-205">Holographics for Business Commercial Suite へのアップグレード方法</span><span class="sxs-lookup"><span data-stu-id="8fe63-205">How to Upgrade to Holographics for Business Commercial Suite</span></span>

> [!NOTE]
> <span data-ttu-id="8fe63-206">Windows Holographics for Business (Commercial Suite) は、HoloLens の第 1 世代デバイスのみを対象としています。</span><span class="sxs-lookup"><span data-stu-id="8fe63-206">Windows Holographics for Business (commercial suite) is only intended for HoloLens 1st gen devices.</span></span> <span data-ttu-id="8fe63-207">プロファイルは HoloLens 2 デバイスには適用されません。</span><span class="sxs-lookup"><span data-stu-id="8fe63-207">The profile will not be applied to HoloLens 2 devices.</span></span>

<span data-ttu-id="8fe63-208">Commercial Suite へアップグレードする方法は、[こちらで](https://docs.microsoft.com/intune/configuration/holographic-upgrade)確認できます。</span><span class="sxs-lookup"><span data-stu-id="8fe63-208">Directions for upgrading to the commercial suite can be found [here](https://docs.microsoft.com/intune/configuration/holographic-upgrade).</span></span>

### <span data-ttu-id="8fe63-209">Microsoft Intune を使用してキオスク モードを構成する方法 </span><span class="sxs-lookup"><span data-stu-id="8fe63-209">How to Configure Kiosk Mode Using Microsoft Intune</span></span>

1. <span data-ttu-id="8fe63-210">Microsoft Store を Intune に同期します ([やり方](https://docs.microsoft.com/intune/apps/windows-store-for-business))。</span><span class="sxs-lookup"><span data-stu-id="8fe63-210">Sync Microsoft Store to Intune ([Here](https://docs.microsoft.com/intune/apps/windows-store-for-business)).</span></span>

1. <span data-ttu-id="8fe63-211">アプリの設定を確認します</span><span class="sxs-lookup"><span data-stu-id="8fe63-211">Check your app settings</span></span>
    1. <span data-ttu-id="8fe63-212">ビジネス向け Microsoft Store のアカウントにログインします。</span><span class="sxs-lookup"><span data-stu-id="8fe63-212">Log into your Microsoft Store Business account</span></span>
    1. **<span data-ttu-id="8fe63-213">[管理]、[製品とサービス]、[アプリとソフトウェア]、[同期するアプリを選択する]、[プライベート ストアの利用許可] の順に選択し、[すべてのユーザー] または [特定のグループ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8fe63-213">Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"</span></span>**
        >[!NOTE]
        ><span data-ttu-id="8fe63-214">目的のアプリが表示されない場合は、ストアを検索してアプリを「取得」する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fe63-214">If you don't see the app you want, you will have to "get" the app by searching the store for your app.</span></span> <span data-ttu-id="8fe63-215">**右上隅の「検索」バーをクリックし、アプリの名前を入力し、アプリをクリックして、「取得」を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8fe63-215">**Click the "Search" bar in the upper right-hand corner > type in the name of the app > click on the app > select "Get"**.</span></span>
    1. <span data-ttu-id="8fe63-216">目的のアプリが **[Intune]、[クライアント アプリ]、[アプリ]** の順に移動して表示されない場合は、再度[アプリを同期する](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps)必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fe63-216">If you do not see your apps in **Intune > Client Apps > Apps** , you may have to [sync your apps](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) again.</span></span>

1. [<span data-ttu-id="8fe63-217">キオスク モード用のデバイス プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="8fe63-217">Create a device profile for Kiosk mode</span></span>](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> <span data-ttu-id="8fe63-218">[Azure AD] を [User logon type] (ユーザー ログオン型) として使用することで、ユーザーごとにキオスク モードのエクスペリエンスが異なるように構成できます。</span><span class="sxs-lookup"><span data-stu-id="8fe63-218">You can configure different users to have different Kiosk Mode experiences by using "Azure AD" as the "User logon type".</span></span> <span data-ttu-id="8fe63-219">ただし、このオプションは複数アプリ キオスク モードでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="8fe63-219">However, this option is only available in Multi-App kiosk mode.</span></span> <span data-ttu-id="8fe63-220">複数アプリ キオスク モードは、1 つのアプリだけでなく複数のアプリでも機能します。</span><span class="sxs-lookup"><span data-stu-id="8fe63-220">Multi-App kiosk mode will work with only one app as well as multiple apps.</span></span>

![Intune のキオスク モードの構成画面を示す画像](images/aad-kioskmode.png)

<span data-ttu-id="8fe63-222">その他の MDM サービスについては、使用しているプロバイダーのドキュメントで手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe63-222">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="8fe63-223">使用している MDM サービスでキオスクを設定するためにカスタム設定とフル XML 構成を使用する必要がある場合は、追加の手順を[こちら](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="8fe63-223">If you need to use a custom setting and full XML configuration to set up a kiosk in your MDM service, additional directions can be found [here](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)</span></span>

## <span data-ttu-id="8fe63-224">証明書と認証</span><span class="sxs-lookup"><span data-stu-id="8fe63-224">Certificates and Authentication</span></span>

<span data-ttu-id="8fe63-225">証明書は、MDM 経由で展開できます ([MDM セクション](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)の「証明書」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="8fe63-225">Certificates can be deployed via you MDM (see "certificates" in the [MDM Section](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span></span> <span data-ttu-id="8fe63-226">証明書は、パッケージ プロビジョニングを使用しても HoloLens にできます。</span><span class="sxs-lookup"><span data-stu-id="8fe63-226">Certificates can also be deployed to the HoloLens through package provisioning.</span></span> <span data-ttu-id="8fe63-227">詳細については、「[HoloLens Provisioning (HoloLens のプロビジョニング)](hololens-provisioning.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe63-227">Please see [HoloLens Provisioning](hololens-provisioning.md) for additional information.</span></span>

### <span data-ttu-id="8fe63-228">その他の Intune クイック リンク</span><span class="sxs-lookup"><span data-stu-id="8fe63-228">Additional Intune Quick Links</span></span>

1. <span data-ttu-id="8fe63-229">[プロファイルを作成する:](https://docs.microsoft.com/intune/configuration/device-profile-create) プロファイルを使用すると、組織内のデバイスにプッシュされる設定を追加および構成できます。</span><span class="sxs-lookup"><span data-stu-id="8fe63-229">[Create Profiles:](https://docs.microsoft.com/intune/configuration/device-profile-create) Profiles allow you to add and configure settings that will be pushed to the devices in your organization.</span></span>

