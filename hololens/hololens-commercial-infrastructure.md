---
title: HoloLens のインフラストラクチャ ガイドライン
description: ''
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
ms.openlocfilehash: 1031eaeaf2767f8aa982d74bb282bc1fb086051b
ms.sourcegitcommit: 77eb85608066d9a4ed01b3862afe356f7e54d583
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "10940217"
---
# <span data-ttu-id="f5f33-102">HoloLens 向けにネットワークを構成する</span><span class="sxs-lookup"><span data-stu-id="f5f33-102">Configure Your Network for HoloLens</span></span>

<span data-ttu-id="f5f33-103">ドキュメントのこの部分には、次のユーザーが必要です。</span><span class="sxs-lookup"><span data-stu-id="f5f33-103">This portion of the document will require the following people:</span></span>

1. <span data-ttu-id="f5f33-104">プロキシ/ファイアウォールを変更するためのアクセス許可を持つネットワーク管理者</span><span class="sxs-lookup"><span data-stu-id="f5f33-104">Network Admin with permissions to make changes to the proxy/firewall</span></span>
2. <span data-ttu-id="f5f33-105">Azure Active Directory 管理者</span><span class="sxs-lookup"><span data-stu-id="f5f33-105">Azure Active Directory Admin</span></span>
3. <span data-ttu-id="f5f33-106">モバイル デバイス マネージャー管理者</span><span class="sxs-lookup"><span data-stu-id="f5f33-106">Mobile Device Manager Admin</span></span>

## <span data-ttu-id="f5f33-107">インフラストラクチャの要件</span><span class="sxs-lookup"><span data-stu-id="f5f33-107">Infrastructure Requirements</span></span>

<span data-ttu-id="f5f33-108">HoloLens は、本質的には、Azure と統合された Windows モバイル デバイスです。</span><span class="sxs-lookup"><span data-stu-id="f5f33-108">HoloLens is, at its core, a Windows mobile device integrated with Azure.</span></span>  <span data-ttu-id="f5f33-109">利用可能なワイヤレス ネットワーク (Wi-Fi) があり Microsoft サービスへアクセスできる商用環境で最もよく動作します。</span><span class="sxs-lookup"><span data-stu-id="f5f33-109">It works best in commercial environments with wireless network availability (wi-fi) and access to Microsoft services.</span></span>

<span data-ttu-id="f5f33-110">必須のクラウド サービス:</span><span class="sxs-lookup"><span data-stu-id="f5f33-110">Critical cloud services include:</span></span>

- <span data-ttu-id="f5f33-111">Azure Active Directory (AAD)</span><span class="sxs-lookup"><span data-stu-id="f5f33-111">Azure active directory (AAD)</span></span>
- <span data-ttu-id="f5f33-112">Windows Update (WU)</span><span class="sxs-lookup"><span data-stu-id="f5f33-112">Windows Update (WU)</span></span>

<span data-ttu-id="f5f33-113">商業利用のお客様は、HoloLens デバイスの大規模な管理を行うには Enterprise Mobility Management (EMM) またはモバイル デバイス管理 (MDM) インフラストラクチャが必要になります。  </span><span class="sxs-lookup"><span data-stu-id="f5f33-113">Commercial customers will need enterprise mobility management (EMM) or mobile device management (MDM) infrastructure to manage HoloLens devices at scale.</span></span>  <span data-ttu-id="f5f33-114">このガイドでは例として [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) を使用しますが、Microsoft ポリシーをフル サポートしているプロバイダーは、いずれも HoloLens をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="f5f33-114">This guide uses [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) as an example, though any provider with full support for Microsoft Policy can support HoloLens.</span></span>  <span data-ttu-id="f5f33-115">使用しているモバイル デバイス管理プロバイダーに問い合わせて、HoloLens 2 をサポートしているかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f5f33-115">Ask your mobile device management provider if they support HoloLens 2.</span></span>

<span data-ttu-id="f5f33-116">HoloLens は、一部の、クラウドに接続されていないエクスペリエンスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f5f33-116">HoloLens does support a limited set of cloud disconnected experiences.</span></span>

### <span data-ttu-id="f5f33-117">ワイヤレス ネットワーク EAP のサポート</span><span class="sxs-lookup"><span data-stu-id="f5f33-117">Wireless network EAP support</span></span>

- <span data-ttu-id="f5f33-118">PEAP-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="f5f33-118">PEAP-MS-CHAPv2</span></span>
- <span data-ttu-id="f5f33-119">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="f5f33-119">PEAP-TLS</span></span>
- <span data-ttu-id="f5f33-120">TLS</span><span class="sxs-lookup"><span data-stu-id="f5f33-120">TLS</span></span>
- <span data-ttu-id="f5f33-121">TTLS-CHAP</span><span class="sxs-lookup"><span data-stu-id="f5f33-121">TTLS-CHAP</span></span>
- <span data-ttu-id="f5f33-122">TTLS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="f5f33-122">TTLS-CHAPv2</span></span>
- <span data-ttu-id="f5f33-123">TTLS-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="f5f33-123">TTLS-MS-CHAPv2</span></span>
- <span data-ttu-id="f5f33-124">TTLS-PAP</span><span class="sxs-lookup"><span data-stu-id="f5f33-124">TTLS-PAP</span></span>
- <span data-ttu-id="f5f33-125">TTLS-TLS</span><span class="sxs-lookup"><span data-stu-id="f5f33-125">TTLS-TLS</span></span>

### <span data-ttu-id="f5f33-126">HoloLens 固有のネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="f5f33-126">HoloLens Specific Network Requirements</span></span>

<span data-ttu-id="f5f33-127">エンドポイントの[このリスト](hololens-offline.md)がネットワーク ファイアウォールで許可されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f5f33-127">Make sure that [this list](hololens-offline.md) of endpoints are allowed on your network firewall.</span></span> <span data-ttu-id="f5f33-128">これにより、HoloLens が正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="f5f33-128">This will enable HoloLens to function properly.</span></span>

### <span data-ttu-id="f5f33-129">リモート アシスト固有のネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="f5f33-129">Remote Assist Specific Network Requirements</span></span>

1. <span data-ttu-id="f5f33-130">リモート アシストの最適なパフォーマンスのために推奨される帯域幅は 1.5 Mbps です。</span><span class="sxs-lookup"><span data-stu-id="f5f33-130">The recommended bandwidth for optimal performance of Remote Assist is 1.5Mbps.</span></span> <span data-ttu-id="f5f33-131">[こちら](https://docs.microsoft.com/MicrosoftTeams/prepare-network)で詳細なネットワーク要件と追加情報を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="f5f33-131">Detailed network requirements and additional information can be found [here](https://docs.microsoft.com/MicrosoftTeams/prepare-network).</span></span>
**<span data-ttu-id="f5f33-132">(ネットワーク速度が 1.5 Mbps 以上でないネットワークの場合でも、リモート アシストは機能します。</span><span class="sxs-lookup"><span data-stu-id="f5f33-132">(Please note, if you don't network have network speeds of at least 1.5Mbps, Remote Assist will still work.</span></span> <span data-ttu-id="f5f33-133">ただし、品質が低下する場合があります。)</span><span class="sxs-lookup"><span data-stu-id="f5f33-133">However, quality may suffer).</span></span>**
1. <span data-ttu-id="f5f33-134">これらのポートと URL がネットワーク ファイアウォールで許可されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f5f33-134">Make sure that these ports and URLs are allowed on your network firewall.</span></span> <span data-ttu-id="f5f33-135">これにより、Microsoft Teams が機能します。</span><span class="sxs-lookup"><span data-stu-id="f5f33-135">This will enable Microsoft Teams to function.</span></span> <span data-ttu-id="f5f33-136">最新のリストについては、[こちら](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5f33-136">The latest list can be found [here](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

- <span data-ttu-id="f5f33-137">特定の「[リモート アシストのネットワーク要件](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)」の詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5f33-137">Learn more about the specific [Network Requirements for Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span></span> 
- <span data-ttu-id="f5f33-138">[Microsoft Teams のために組織のネットワークを準備する](https://docs.microsoft.com/MicrosoftTeams/prepare-network)方法の詳細</span><span class="sxs-lookup"><span data-stu-id="f5f33-138">Learn more about how to [prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</span></span>

### <span data-ttu-id="f5f33-139">固有のネットワーク要件のガイド</span><span class="sxs-lookup"><span data-stu-id="f5f33-139">Guides Specific Network Requirements</span></span>

<span data-ttu-id="f5f33-140">ガイドには、アプリをダウンロードして使用するためのネットワーク アクセスのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="f5f33-140">Guides only require network access to download and use the app.</span></span>

## <span data-ttu-id="f5f33-141">Azure Active Directory ガイダンス</span><span class="sxs-lookup"><span data-stu-id="f5f33-141">Azure Active Directory Guidance</span></span>

> [!NOTE]
> <span data-ttu-id="f5f33-142">この手順は、会社が HoloLens を管理する予定にしている場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="f5f33-142">This step is only necessary if your company plans on managing the HoloLens.</span></span>

1. <span data-ttu-id="f5f33-143">Azure AD ライセンスがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f5f33-143">Ensure that you have an Azure AD License.</span></span>
<span data-ttu-id="f5f33-144">追加情報については、「[HoloLens Licenses Requirements (HoloLens のライセンス要件)](hololens-licenses-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5f33-144">Please [HoloLens Licenses Requirements](hololens-licenses-requirements.md) for additional information.</span></span>

1. <span data-ttu-id="f5f33-145">自動登録を使用することを予定している場合は、[Azure AD の登録を構成する](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5f33-145">If you plan on using Auto Enrollment, you will have to [Configure Azure AD enrollment.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span></span>

1. <span data-ttu-id="f5f33-146">会社のユーザーが Azure Active Directory (Azure AD) に含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f5f33-146">Ensure that your company's users are in Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="f5f33-147">ユーザーを追加する手順については、[こちら](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5f33-147">Instructions for adding users can be found [here](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory).</span></span>

1. <span data-ttu-id="f5f33-148">同様のライセンスが必要なユーザーは、同じグループに追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f5f33-148">We suggest that users who need similar licenses are added to the same group.</span></span>
    1. [<span data-ttu-id="f5f33-149">グループの作成</span><span class="sxs-lookup"><span data-stu-id="f5f33-149">Create a Group</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [<span data-ttu-id="f5f33-150">ユーザーをグループに追加する</span><span class="sxs-lookup"><span data-stu-id="f5f33-150">Add users to groups</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. <span data-ttu-id="f5f33-151">会社のユーザー (またはユーザー グループ) に必要なライセンスが割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f5f33-151">Ensure that your company's users (or group of users) are assigned the necessary licenses.</span></span>
<span data-ttu-id="f5f33-152">ライセンスを割り当てる方法は、[こちら](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="f5f33-152">Directions for assigning licenses can be found [here](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).</span></span>

1. <span data-ttu-id="f5f33-153">この手順は、ユーザーが各自の HoloLens またはモバイル デバイスを会社のネットワークに登録することを想定している場合にのみ実行してください (3 つのオプションがあります)。これらの手順により、会社のユーザー (またはユーザー グループ) がデバイスを追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f5f33-153">Only do this step if users are expected to enroll their HoloLens/Mobile device into you (There are three options) These steps ensure that your company's users (or a group of users) can add devices.</span></span>
    1. <span data-ttu-id="f5f33-154">**オプション 1:** デバイスを Azure AD に参加させる許可をすべてのユーザーに与えます。</span><span class="sxs-lookup"><span data-stu-id="f5f33-154">**Option 1:** Give all users permission to join devices to Azure AD.</span></span>
<span data-ttu-id="f5f33-155">**管理者として Azure ポータルにサインインする** > **Azure Active Directory** > **デバイス** > **デバイス設定** >
 **[ユーザーはデバイスを Azure AD に参加させることができます] を [*All (すべてのユーザー)*] に設定する**</span><span class="sxs-lookup"><span data-stu-id="f5f33-155">**Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
**Set Users may join devices to Azure AD to *All***</span></span>

    1. <span data-ttu-id="f5f33-156">**オプション 2:** デバイスを Azure AD に参加させる権限を、選択されたユーザーおよびグループに付与します。**Azure ポータルに管理者としてサインイン** > [**Azure Active Directory**] > [**デバイス**] > [**デバイス設定**] >
[**ユーザーはデバイスを Azure AD に参加させることができます] を [*Selected*] (選択されたユーザー) に設定**
![Azure AD に参加したデバイスの構成を示す画像</span><span class="sxs-lookup"><span data-stu-id="f5f33-156">**Option 2:** Give selected users/groups permission to join devices to Azure AD **Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
\*\*Set Users may join devices to Azure AD to \*Selected\*\*\*
![Image that shows Configuration of Azure AD Joined Devices</span></span>](images/azure-ad-image.png)

    1. <span data-ttu-id="f5f33-157">**オプション 3:** デバイスをドメインに参加させることをすべてのユーザーに対してブロックできます。</span><span class="sxs-lookup"><span data-stu-id="f5f33-157">**Option 3:** You can block all users from joining their devices to the domain.</span></span> <span data-ttu-id="f5f33-158">この場合、すべてのデバイスを手動で登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5f33-158">This means that all devices will need to be manually enrolled.</span></span>

## <span data-ttu-id="f5f33-159">モバイル デバイス マネージャーのガイダンス</span><span class="sxs-lookup"><span data-stu-id="f5f33-159">Mobile Device Manager Guidance</span></span>

### <span data-ttu-id="f5f33-160">継続的なデバイス管理</span><span class="sxs-lookup"><span data-stu-id="f5f33-160">Ongoing device management</span></span>

> [!NOTE]
> <span data-ttu-id="f5f33-161">この手順は、会社が HoloLens を管理する予定にしている場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="f5f33-161">This step is only necessary if your company plans to manage the HoloLens.</span></span>

<span data-ttu-id="f5f33-162">継続的なデバイス管理は、モバイル デバイスの管理インフラストラクチャに依存します。</span><span class="sxs-lookup"><span data-stu-id="f5f33-162">Ongoing device management will depend on your mobile device management infrastructure.</span></span>  <span data-ttu-id="f5f33-163">ほとんどのインフラストラクチャでは同様の機能が備わっていますが、ユーザー インターフェイスが大きく異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f5f33-163">Most have the same general functionality but the user interface may vary widely.</span></span>

1. <span data-ttu-id="f5f33-164">[CSP (構成サービス プロバイダー)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) を使用すると、ネットワーク上のデバイスの管理設定を作成および展開できます。</span><span class="sxs-lookup"><span data-stu-id="f5f33-164">[CSPs (Configuration Service Providers)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) allows you to create and deploy management settings for the devices on your network.</span></span> <span data-ttu-id="f5f33-165">HoloLens の CSP の一覧については、[ここ](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5f33-165">A list of CSPs for HoloLens can be found [here](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).</span></span>

1. <span data-ttu-id="f5f33-166">[コンプライアンス ポリシー](https://docs.microsoft.com/intune/device-compliance-get-started)は、会社のインフラストラクチャに準拠するためにデバイスが満たす必要があるルールおよび設定 です。</span><span class="sxs-lookup"><span data-stu-id="f5f33-166">[Compliance policies](https://docs.microsoft.com/intune/device-compliance-get-started) are rules and settings that devices must meet to be compliant in your corporate infrastructure.</span></span> <span data-ttu-id="f5f33-167">非準拠デバイスについては、これらのポリシーを条件付きアクセスとともに使用して、会社のリソースへのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="f5f33-167">Use these policies with Conditional Access to block access to company resources for devices that are non-compliant.</span></span> <span data-ttu-id="f5f33-168">たとえば、Bitlocker が有効になっていることを要求するポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="f5f33-168">For example, you can create a policy that requires Bitlocker be enabled.</span></span>

1. <span data-ttu-id="f5f33-169">[コンプライアンス ポリシーの作成](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows)。</span><span class="sxs-lookup"><span data-stu-id="f5f33-169">[Create Compliance Policy](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).</span></span>

1. <span data-ttu-id="f5f33-170">条件付きアクセスは、モバイル デバイスおよびモバイル アプリケーションが会社のリソースにアクセスすることを許可または拒否します。</span><span class="sxs-lookup"><span data-stu-id="f5f33-170">Conditional Access allows/denies mobile devices and mobile applications from accessing company resources.</span></span> <span data-ttu-id="f5f33-171">役に立つと思われる 2 つのドキュメントとして、「[Plan your CA Deployment (CA 展開を計画する)](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)」と「[ベスト プラクティス](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices)」があります。</span><span class="sxs-lookup"><span data-stu-id="f5f33-171">Two documents you may find helpful are [Plan your CA Deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) and [Best Practices](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).</span></span>

1. <span data-ttu-id="f5f33-172">[こちらの記事](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business)では、 Intune の HoloLens 向けの管理ツールについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="f5f33-172">[This article](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) talks about Intune's management tools for HoloLens.</span></span>

1. [<span data-ttu-id="f5f33-173">デバイス プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="f5f33-173">Create a device profile</span></span>](https://docs.microsoft.com/intune/configuration/device-profile-create)

### <span data-ttu-id="f5f33-174">更新プログラムの管理</span><span class="sxs-lookup"><span data-stu-id="f5f33-174">Manage updates</span></span>

<span data-ttu-id="f5f33-175">Intune には、HoloLens 2 や HoloLens v1 (Holographic for Business を含む) などの Windows 10 デバイス向けに、更新リングと呼ばれる機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f5f33-175">Intune includes a feature called Update rings for Windows 10 devices, including HoloLens 2 and HoloLens v1 (with Holographic for Business).</span></span> <span data-ttu-id="f5f33-176">更新リングには、更新プログラムのインストール方法とタイミングを決めるための設定群が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f5f33-176">Update rings include a group of settings that determine how and when updates are installed.</span></span>

<span data-ttu-id="f5f33-177">たとえば、更新プログラムをインストールするためのメンテナンス期間を作成することも、更新プログラムのインストール後に再起動することもできます。</span><span class="sxs-lookup"><span data-stu-id="f5f33-177">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span>  <span data-ttu-id="f5f33-178">更新の準備ができるまで、更新プログラムを無期限に一時停止することもできます。</span><span class="sxs-lookup"><span data-stu-id="f5f33-178">You can also choose to pause updates indefinitely until you're ready to update.</span></span>

<span data-ttu-id="f5f33-179">詳細については、「[Intune を使用して更新リングを構成する](https://docs.microsoft.com/intune/windows-update-for-business-configure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5f33-179">Read more about [configuring update rings with Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span></span>

### <span data-ttu-id="f5f33-180">アプリケーション管理</span><span class="sxs-lookup"><span data-stu-id="f5f33-180">Application management</span></span>

<span data-ttu-id="f5f33-181">HoloLens アプリケーションの管理には、次を使用します。</span><span class="sxs-lookup"><span data-stu-id="f5f33-181">Manage HoloLens applications through:</span></span>

1. <span data-ttu-id="f5f33-182">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="f5f33-182">Microsoft Store</span></span>  
  <span data-ttu-id="f5f33-183">Microsoft Store は、HoloLens でアプリケーションを配布および使用するための最善の方法です。</span><span class="sxs-lookup"><span data-stu-id="f5f33-183">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span></span>  <span data-ttu-id="f5f33-184">Store では、HoloLens の優れた基本的なアプリ群が既に提供されています。[独自のアプリを公開](https://docs.microsoft.com/windows/uwp/publish/)することもできます。</span><span class="sxs-lookup"><span data-stu-id="f5f33-184">There is a great set of core HoloLens applications already available in the store or you can [publish your own](https://docs.microsoft.com/windows/uwp/publish/).</span></span>  
  <span data-ttu-id="f5f33-185">Store 内のすべてのアプリケーションはすべてのユーザーに一般提供されていますが、お客様の要求を満たすアプリが見当たらない場合は、ビジネス向け Microsoft Store をご覧になってください。</span><span class="sxs-lookup"><span data-stu-id="f5f33-185">All applications in the store are available publicly to everyone, but if it isn't acceptable, checkout the Microsoft Store for Business.</span></span>  

1. [<span data-ttu-id="f5f33-186">ビジネス向け Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="f5f33-186">Microsoft Store for Business</span></span>](https://docs.microsoft.com/microsoft-store/)  
  <span data-ttu-id="f5f33-187">ビジネスおよび教育機関向け Microsoft Storeは、企業環境に合わせてカスタマイズされたストアです。</span><span class="sxs-lookup"><span data-stu-id="f5f33-187">Microsoft Store for Business and Education is a custom store for your corporate environment.</span></span>  <span data-ttu-id="f5f33-188">ビジネスおよび教育機関向け Microsoft Store を使用することで、Windows 10 および HoloLens に組み込まれている Microsoft Store を使用して、組織用にアプリの検索、取得、配布、管理を行えます。</span><span class="sxs-lookup"><span data-stu-id="f5f33-188">It lets you use the Microsoft Store built into Windows 10 and HoloLens to find, acquire, distribute, and manage apps for your organization.</span></span>  <span data-ttu-id="f5f33-189">一般的な環境ではなくお客様の商用環境に特化したアプリを展開することも可能になります。</span><span class="sxs-lookup"><span data-stu-id="f5f33-189">It also lets you deploy apps that are specific to your commercial environment but not to the world.</span></span>

1. <span data-ttu-id="f5f33-190">Intune またはその他のモバイル デバイス管理ソリューションを使用したアプリケーションの展開と管理</span><span class="sxs-lookup"><span data-stu-id="f5f33-190">Application deployment and management via Intune or another mobile device management solution</span></span>  
  <span data-ttu-id="f5f33-191">Intune を含むほとんどのモバイル デバイス管理ソリューションでは、基幹アプリケーションを登録済みのデバイス群に直接展開する方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="f5f33-191">Most mobile device management solutions, including Intune, provide a way to deploy line of business applications directly to a set of enrolled devices.</span></span>  <span data-ttu-id="f5f33-192">詳細については、[Intune アプリのインストール](https://docs.microsoft.com/intune/apps-deploy)についての記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5f33-192">See this article for [Intune app install](https://docs.microsoft.com/intune/apps-deploy).</span></span>

1. <span data-ttu-id="f5f33-193">_非推奨_ Device Portal</span><span class="sxs-lookup"><span data-stu-id="f5f33-193">_not recommended_ Device Portal</span></span>  
  <span data-ttu-id="f5f33-194">アプリケーションは、Windows デバイス ポータルを使用して HoloLens に直接インストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f5f33-194">Applications can also be installed on HoloLens directly using the Windows Device Portal.</span></span>  <span data-ttu-id="f5f33-195">デバイス ポータルを使用するには開発者モードを有効にする必要があるため、この方法はお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="f5f33-195">This isn't recommended since Developer Mode has to be enabled to use the device portal.</span></span>

<span data-ttu-id="f5f33-196">[HoloLens にアプリをインストールする方法](https://docs.microsoft.com/hololens/hololens-install-apps)の詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f5f33-196">Read more about [installing apps on HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).</span></span>

### <span data-ttu-id="f5f33-197">証明書</span><span class="sxs-lookup"><span data-stu-id="f5f33-197">Certificates</span></span>

<span data-ttu-id="f5f33-198">証明書は、MDM プロバイダー経由で配布できます。</span><span class="sxs-lookup"><span data-stu-id="f5f33-198">You can distribute certificates through your MDM provider.</span></span> <span data-ttu-id="f5f33-199">会社で証明書が要求される場合、Intune では PKCS、PFX、および SCEP がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f5f33-199">If your company requires certificates, Intune supports PKCS, PFX, and SCEP.</span></span> <span data-ttu-id="f5f33-200">どの証明書が会社に適しているかについて理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="f5f33-200">It is important to understand which certificate is right for your company.</span></span> <span data-ttu-id="f5f33-201">最適な証明書を決定するには、[こちら](https://docs.microsoft.com/intune/protect/certificates-configure)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f5f33-201">Please visit [here](https://docs.microsoft.com/intune/protect/certificates-configure) to determine which cert is best for you.</span></span> <span data-ttu-id="f5f33-202">HoloLens 認証に証明書を使用する予定がある場合には、PFX または SCEP が最適です。</span><span class="sxs-lookup"><span data-stu-id="f5f33-202">If you plan to use certificates for HoloLens Authentication, PFX or SCEP may be right for you.</span></span>

<span data-ttu-id="f5f33-203">SCEP の手順については、[こちら](https://docs.microsoft.com/intune/protect/certificates-profile-scep)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f5f33-203">Steps for SCEP can be found [here](https://docs.microsoft.com/intune/protect/certificates-profile-scep).</span></span>

### <span data-ttu-id="f5f33-204">Holographics for Business Commercial Suite へのアップグレード方法</span><span class="sxs-lookup"><span data-stu-id="f5f33-204">How to Upgrade to Holographics for Business Commercial Suite</span></span>

> [!NOTE]
> <span data-ttu-id="f5f33-205">Windows Holographics for Business (Commercial Suite) は、HoloLens の第 1 世代デバイスのみを対象としています。</span><span class="sxs-lookup"><span data-stu-id="f5f33-205">Windows Holographics for Business (commercial suite) is only intended for HoloLens 1st gen devices.</span></span> <span data-ttu-id="f5f33-206">プロファイルは HoloLens 2 デバイスには適用されません。</span><span class="sxs-lookup"><span data-stu-id="f5f33-206">The profile will not be applied to HoloLens 2 devices.</span></span>

<span data-ttu-id="f5f33-207">Commercial Suite へアップグレードする方法は、[こちらで](https://docs.microsoft.com/intune/configuration/holographic-upgrade)確認できます。</span><span class="sxs-lookup"><span data-stu-id="f5f33-207">Directions for upgrading to the commercial suite can be found [here](https://docs.microsoft.com/intune/configuration/holographic-upgrade).</span></span>

### <span data-ttu-id="f5f33-208">Microsoft Intune を使用してキオスク モードを構成する方法 </span><span class="sxs-lookup"><span data-stu-id="f5f33-208">How to Configure Kiosk Mode Using Microsoft Intune</span></span>

1. <span data-ttu-id="f5f33-209">Microsoft Store を Intune に同期します ([やり方](https://docs.microsoft.com/intune/apps/windows-store-for-business))。</span><span class="sxs-lookup"><span data-stu-id="f5f33-209">Sync Microsoft Store to Intune ([Here](https://docs.microsoft.com/intune/apps/windows-store-for-business)).</span></span>

1. <span data-ttu-id="f5f33-210">アプリの設定を確認します</span><span class="sxs-lookup"><span data-stu-id="f5f33-210">Check your app settings</span></span>
    1. <span data-ttu-id="f5f33-211">ビジネス向け Microsoft Store のアカウントにログインします。</span><span class="sxs-lookup"><span data-stu-id="f5f33-211">Log into your Microsoft Store Business account</span></span>
    1. **<span data-ttu-id="f5f33-212">[管理]、[製品とサービス]、[アプリとソフトウェア]、[同期するアプリを選択する]、[プライベート ストアの利用許可] の順に選択し、[すべてのユーザー] または [特定のグループ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5f33-212">Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"</span></span>**
        >[!NOTE]
        ><span data-ttu-id="f5f33-213">目的のアプリが表示されない場合は、ストアを検索してアプリを「取得」する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5f33-213">If you don't see the app you want, you will have to "get" the app by searching the store for your app.</span></span> <span data-ttu-id="f5f33-214">**右上隅の「検索」バーをクリックし、アプリの名前を入力し、アプリをクリックして、「取得」を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f5f33-214">**Click the "Search" bar in the upper right-hand corner > type in the name of the app > click on the app > select "Get"**.</span></span>
    1. <span data-ttu-id="f5f33-215">目的のアプリが **[Intune]、[クライアント アプリ]、[アプリ]** の順に移動して表示されない場合は、再度[アプリを同期する](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps)必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5f33-215">If you do not see your apps in **Intune > Client Apps > Apps** , you may have to [sync your apps](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) again.</span></span>

1. [<span data-ttu-id="f5f33-216">キオスク モード用のデバイス プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="f5f33-216">Create a device profile for Kiosk mode</span></span>](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> <span data-ttu-id="f5f33-217">[Azure AD] を [User logon type] (ユーザー ログオン型) として使用することで、ユーザーごとにキオスク モードのエクスペリエンスが異なるように構成できます。</span><span class="sxs-lookup"><span data-stu-id="f5f33-217">You can configure different users to have different Kiosk Mode experiences by using "Azure AD" as the "User logon type".</span></span> <span data-ttu-id="f5f33-218">ただし、このオプションは複数アプリ キオスク モードでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5f33-218">However, this option is only available in Multi-App kiosk mode.</span></span> <span data-ttu-id="f5f33-219">複数アプリ キオスク モードは、1 つのアプリだけでなく複数のアプリでも機能します。</span><span class="sxs-lookup"><span data-stu-id="f5f33-219">Multi-App kiosk mode will work with only one app as well as multiple apps.</span></span>

![Intune のキオスク モードの構成画面を示す画像](images/aad-kioskmode.png)

<span data-ttu-id="f5f33-221">その他の MDM サービスについては、使用しているプロバイダーのドキュメントで手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5f33-221">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="f5f33-222">使用している MDM サービスでキオスクを設定するためにカスタム設定とフル XML 構成を使用する必要がある場合は、追加の手順を[こちら](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="f5f33-222">If you need to use a custom setting and full XML configuration to set up a kiosk in your MDM service, additional directions can be found [here](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)</span></span>

## <span data-ttu-id="f5f33-223">証明書と認証</span><span class="sxs-lookup"><span data-stu-id="f5f33-223">Certificates and Authentication</span></span>

<span data-ttu-id="f5f33-224">証明書は、MDM 経由で展開できます ([MDM セクション](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)の「証明書」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="f5f33-224">Certificates can be deployed via you MDM (see "certificates" in the [MDM Section](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span></span> <span data-ttu-id="f5f33-225">証明書は、パッケージ プロビジョニングを使用しても HoloLens にできます。</span><span class="sxs-lookup"><span data-stu-id="f5f33-225">Certificates can also be deployed to the HoloLens through package provisioning.</span></span> <span data-ttu-id="f5f33-226">詳細については、「[HoloLens Provisioning (HoloLens のプロビジョニング)](hololens-provisioning.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5f33-226">Please see [HoloLens Provisioning](hololens-provisioning.md) for additional information.</span></span>

### <span data-ttu-id="f5f33-227">その他の Intune クイック リンク</span><span class="sxs-lookup"><span data-stu-id="f5f33-227">Additional Intune Quick Links</span></span>

1. <span data-ttu-id="f5f33-228">[プロファイルを作成する:](https://docs.microsoft.com/intune/configuration/device-profile-create) プロファイルを使用すると、組織内のデバイスにプッシュされる設定を追加および構成できます。</span><span class="sxs-lookup"><span data-stu-id="f5f33-228">[Create Profiles:](https://docs.microsoft.com/intune/configuration/device-profile-create) Profiles allow you to add and configure settings that will be pushed to the devices in your organization.</span></span>

