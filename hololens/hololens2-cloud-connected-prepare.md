---
title: デプロイ ガイド – クラウド接続HoloLens 2大規模なデプロイ - Remote Assist - 準備
description: Azure Active Directory と ID 管理を使用してHoloLensネットワークを使用してデバイスを登録する準備をする方法について説明します。
keywords: HoloLens、管理、クラウド接続、Remote Assist、AAD、Azure AD、MDM、Mobile デバイス管理
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 21fffdc24f8682bc44779e1cebe8cd6eacb59619
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639660"
---
# <a name="prepare---cloud-connected-guide"></a><span data-ttu-id="3f548-104">準備 - クラウド接続ガイド</span><span class="sxs-lookup"><span data-stu-id="3f548-104">Prepare - Cloud connected Guide</span></span>

<span data-ttu-id="3f548-105">この記事の最後までに、AZURE AD アカウントとネットワーク要件の使用に関するAzure ADを設定します。</span><span class="sxs-lookup"><span data-stu-id="3f548-105">By the end of this article you will have set up Azure AD, MDM, and understand more about using Azure AD accounts and network requirements.</span></span> <span data-ttu-id="3f548-106">このガイドのこのセクションは、ユーザーと組織がクラウドにデプロイし、HoloLens 2を使用するための準備をDynamics 365 Remote Assist。</span><span class="sxs-lookup"><span data-stu-id="3f548-106">This section of the guide will help you and your organization get prepared to deploy HoloLens 2 to the cloud and use Dynamics 365 Remote Assist.</span></span> <span data-ttu-id="3f548-107">インフラストラクチャの各部分の重要性に加え、必要に応じてこれらの部分を設定するのに役立つガイドへのリンクが提供されます。</span><span class="sxs-lookup"><span data-stu-id="3f548-107">It will go over the importance of each piece of your infrastructure as well as providing links to guides to help you set up those pieces as needed.</span></span>

## <a name="infrastructure-essentials"></a><span data-ttu-id="3f548-108">Infrastructure Essentials</span><span class="sxs-lookup"><span data-stu-id="3f548-108">Infrastructure Essentials</span></span>

<span data-ttu-id="3f548-109">個人と企業の両方の展開シナリオでは、MDM システムは、デバイスを展開および管理するために必要Windows 10 Holographicです。</span><span class="sxs-lookup"><span data-stu-id="3f548-109">For both personal and corporate deployment scenarios, an MDM system is the essential infrastructure required to deploy and manage Windows 10 Holographic devices.</span></span> <span data-ttu-id="3f548-110">Azure AD Premium サブスクリプションは、ID プロバイダーとして推奨され、特定の機能をサポートするために必要です。</span><span class="sxs-lookup"><span data-stu-id="3f548-110">An Azure AD premium subscription is recommended as an identity provider and required to support certain capabilities.</span></span>

### <a name="azure-active-directory"></a><span data-ttu-id="3f548-111">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3f548-111">Azure Active Directory</span></span>

<span data-ttu-id="3f548-112">Azure AD は、ID とアクセス管理を提供する、クラウド ベースのディレクトリ サービスです。</span><span class="sxs-lookup"><span data-stu-id="3f548-112">Azure AD is a cloud-based directory service that provides identity and access management.</span></span> <span data-ttu-id="3f548-113">Microsoft Office 365 または Intune を使用する組織では、3 つのエディション (Free、プレミアム P1、プレミアム P2) を持つ Azure AD を既に使用しています (「Azure Active Directory [editions](https://azure.microsoft.com/documentation/articles/active-directory-editions)」を参照)。すべてのエディションでデバイスAzure ADサポートされますが、このガイドプレミアム使用する MDM 自動登録を有効にするには、P1 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f548-113">Organizations that use Microsoft Office 365 or Intune are already using Azure AD, which has three editions: Free, Premium P1, and Premium P2 (see [Azure Active Directory editions](https://azure.microsoft.com/documentation/articles/active-directory-editions).) All editions support Azure AD device registration, but Premium P1 is required to enable MDM auto-enrollment which we will be using in this guide later.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f548-114">オンプレミスの AD 参加をAzure Active DirectoryデバイスHoloLens、この機能を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f548-114">It is essential to have an Azure Active Directory as HoloLens devices do not support on-premises AD join.</span></span> <span data-ttu-id="3f548-115">新しいテナント&#39;まだ設定していない場合Azure Active Directoryに新しいテナントを作成する[」にAzure Active Directory。](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)</span><span class="sxs-lookup"><span data-stu-id="3f548-115">If you don&#39;t already have an Azure Active Directory set up, go to [Create a new tenant in Azure Active Directory](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).</span></span>

## <a name="identity-management"></a><span data-ttu-id="3f548-116">ID 管理</span><span class="sxs-lookup"><span data-stu-id="3f548-116">Identity Management</span></span>

<span data-ttu-id="3f548-117">従業員は、デバイスを初期化するために 1 つのアカウントのみを使用&#39;、組織が最初に有効にするアカウントを制御する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f548-117">Employees can use only one account to initialize a device so it&#39;s imperative that your organization controls which account is enabled first.</span></span> <span data-ttu-id="3f548-118">選択したアカウントによって、デバイスを制御するユーザーが決まり、管理機能に影響があります。</span><span class="sxs-lookup"><span data-stu-id="3f548-118">The account chosen will determine who controls the device and influence your management capabilities.</span></span>

<span data-ttu-id="3f548-119">このガイドでは、使用する ID[](/hololens/hololens-identity)に対して、アカウントまたはアカウントAzure AD使用Azure Active Directoryしました。</span><span class="sxs-lookup"><span data-stu-id="3f548-119">In this guide we have chosen that for the [Identity](/hololens/hololens-identity) used we will use Azure AD accounts, or Azure Active Directory accounts.</span></span> <span data-ttu-id="3f548-120">使用するアカウントAzure ADにはいくつかの利点があります。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3f548-120">There are several benefits to Azure AD accounts we would like to use, such as:</span></span>

- <span data-ttu-id="3f548-121">従業員は、Azure AD アカウントを使用してデバイスを Azure AD に登録し、組織&#39;の MDM ソリューションに自動的に登録します (Azure AD + MDM – Azure AD Premium が必要)。</span><span class="sxs-lookup"><span data-stu-id="3f548-121">Employees use their Azure AD account to register the device in Azure AD and automatically enroll it with the organization&#39;s MDM solution (Azure AD+MDM – requires Azure AD Premium).</span></span>
- <span data-ttu-id="3f548-122">Azure ADアカウントでは、シングル [サインオン がサポートされます](/azure/active-directory/manage-apps/what-is-single-sign-on)。</span><span class="sxs-lookup"><span data-stu-id="3f548-122">Azure AD accounts support [Single Sign On](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span> <span data-ttu-id="3f548-123">ユーザーが Remote Assist にサインインすると、サインインした Azure AD ユーザーの ID が認識され、ユーザーはアプリにサインインして、エクスペリエンスを効率化します。</span><span class="sxs-lookup"><span data-stu-id="3f548-123">When a user signs into Remote Assist, their Identity from the signed in Azure AD user will be recognized and the user will be signed into the app for a streamlined experience.</span></span>
- <span data-ttu-id="3f548-124">Azure ADアカウントには、Business 用[の Windows Hello](/hololens/hololens-identity)を[使用して追加の認証オプションがあります](/windows/security/identity-protection/hello-for-business/hello-identity-verification)。</span><span class="sxs-lookup"><span data-stu-id="3f548-124">Azure AD accounts have additional [authentication options](/hololens/hololens-identity) via [Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification).</span></span> <span data-ttu-id="3f548-125">Iris ログイン ユーザーに加えて、別のデバイスからサインインしたり、FIDO セキュリティ キーを使用したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3f548-125">In addition to Iris log-in users can sign in from another device or use FIDO security keys.</span></span>

### <a name="mobile-device-management"></a><span data-ttu-id="3f548-126">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="3f548-126">Mobile Device Management</span></span>

<span data-ttu-id="3f548-127">Microsoft [Intune](/mem/intune/fundamentals/what-is-intune)は、テナントに接続Enterprise Mobility + Securityデバイスを管理するクラウドベースの MDM システムです。</span><span class="sxs-lookup"><span data-stu-id="3f548-127">Microsoft [Intune](/mem/intune/fundamentals/what-is-intune), part of the Enterprise Mobility + Security, is a cloud-based MDM system that manages devices connected to your tenant.</span></span> <span data-ttu-id="3f548-128">たとえばOffice 365 Intune では ID 管理に Azure AD が使用されます。そのため、従業員は同じ資格情報を使用して、サインインに使用するデバイスを Intune に登録Office 365。</span><span class="sxs-lookup"><span data-stu-id="3f548-128">Like Office 365, Intune uses Azure AD for identity management, so employees use the same credentials to enroll devices in Intune that they use to sign into Office 365.</span></span> <span data-ttu-id="3f548-129">Intune では、完全な MDM ソリューションを提供するために、iOS や Android などの他のオペレーティング システムを実行するデバイスもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3f548-129">Intune also supports devices that run other operating systems, such as iOS and Android, to provide a complete MDM solution.</span></span> <span data-ttu-id="3f548-130">このガイドでは、&#39;を使用して大規模なクラウドデプロイを有効にするための Intune の使用に焦点を当HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="3f548-130">For the purposes of this guide, we&#39;ll be focusing on using Intune for enabling a cloud deployment at scale with HoloLens 2.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f548-131">Mobile デバイス管理。</span><span class="sxs-lookup"><span data-stu-id="3f548-131">It is essential to have Mobile Device Management.</span></span> <span data-ttu-id="3f548-132">まだ設定&#39;場合は、このガイドに従い [、Intune 概要を使用してください](/mem/intune/fundamentals/free-trial-sign-up)。</span><span class="sxs-lookup"><span data-stu-id="3f548-132">If you don&#39;t already have it set up follow this guide and [Get started with Intune](/mem/intune/fundamentals/free-trial-sign-up).</span></span>

> [!NOTE]
> <span data-ttu-id="3f548-133">複数の MDM システムが Windows 10 をサポートしており、ほとんどは、個人のデバイスおよび企業のデバイスの展開のシナリオをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3f548-133">Multiple MDM systems support Windows 10 and most support personal and corporate device deployment scenarios.</span></span> <span data-ttu-id="3f548-134">現在、この機能をWindows 10 Holographic MDM プロバイダーには、AirWatch、MobileIron などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3f548-134">MDM providers that support Windows 10 Holographic currently include: AirWatch, MobileIron, and others.</span></span> <span data-ttu-id="3f548-135">業界をリードする MDM ベンダーのほとんどは既に Azure AD との統合をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3f548-135">Most industry-leading MDM vendors already support integration with Azure AD.</span></span> <span data-ttu-id="3f548-136">Azure AD をサポートする MDM ベンダーは [Azure Marketplace](https://azure.microsoft.com/marketplace/)で検索できます。</span><span class="sxs-lookup"><span data-stu-id="3f548-136">You can find the MDM vendors that support Azure AD in [Azure Marketplace](https://azure.microsoft.com/marketplace/).</span></span>

## <a name="network"></a><span data-ttu-id="3f548-137">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="3f548-137">Network</span></span>

<span data-ttu-id="3f548-138">このセットアップでは、使用可能なHoloLens 2ネットワークからインターネットに接続するデバイスがWi-Fiされます。</span><span class="sxs-lookup"><span data-stu-id="3f548-138">In this setup, we anticipate HoloLens 2 devices connecting to the Internet from any available open Wi-Fi network.</span></span> <span data-ttu-id="3f548-139">ユーザーは場所に基づいてネットワーク接続を変更する必要がある可能性があるから、ユーザーはデバイスを[Wi-Fi にHoloLensする方法を学習する必要があります。](/hololens/hololens-network)</span><span class="sxs-lookup"><span data-stu-id="3f548-139">Since a user could need to change the network connection based on location, they should learn how to [connect HoloLens devices to Wi-Fi.](/hololens/hololens-network)</span></span>

<span data-ttu-id="3f548-140">たとえばDynamics 365 Remote Assist、帯域幅、待機時間、ジッター、パケット損失など、ビデオ通話エクスペリエンスに影響を与える可能性があるさまざまなネットワーク条件があります。</span><span class="sxs-lookup"><span data-stu-id="3f548-140">For Dynamics 365 Remote Assist there are a variety of network conditions, including bandwidth, latency, jitter, and packet loss, that can impact your video calling experience.</span></span> <span data-ttu-id="3f548-141">帯域幅が少ない環境ではオーディオとビデオの呼び出しが可能な場合でも、機能が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3f548-141">Although audio and video calls might be possible in environments with reduced bandwidth, you might experience feature degradation.</span></span> <span data-ttu-id="3f548-142">デバイスで Dynamics 365 Remote AssistをHoloLens、次のネットワーク要件に注意してください。</span><span class="sxs-lookup"><span data-stu-id="3f548-142">When using Dynamics 365 Remote Assist on HoloLens here are the network requirements to keep in mind:</span></span>

<span data-ttu-id="3f548-143">**最小** : HD 1080p の解像度が 30 fps のピア ツー ピア HD 品質ビデオ通話には、1.5 Mbps のアップ/ダウンが必要です。</span><span class="sxs-lookup"><span data-stu-id="3f548-143">**Minimum** : 1.5 Mbps up/down is required for peer-to-peer HD quality video calling with resolution of HD 1080p at 30 fps.</span></span>

<span data-ttu-id="3f548-144">**最適:** HD 1080p の解像度でピア ツー ピア HD 品質のビデオ通話を行う場合は、4 ~ 5 Mbps のアップ/ダウンが必要です。</span><span class="sxs-lookup"><span data-stu-id="3f548-144">**Optimal:** For peer-to-peer HD quality video calling with resolution of HD 1080p, 4-5 Mbps up/down should be expected.</span></span>

<span data-ttu-id="3f548-145">詳細情報:</span><span class="sxs-lookup"><span data-stu-id="3f548-145">More information:</span></span>

- [<span data-ttu-id="3f548-146">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="3f548-146">Network requirements</span></span>](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [<span data-ttu-id="3f548-147">ネットワークの最適化に関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="3f548-147">Network optimization recommendations</span></span>](/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a><span data-ttu-id="3f548-148">省略可能: Connect VPN HoloLens接続する</span><span class="sxs-lookup"><span data-stu-id="3f548-148">Optional: Connect your HoloLens to VPN</span></span>

<span data-ttu-id="3f548-149">このガイドに接続されているデバイスは、外部クラウド ネットワークを介してネットワークに接続します。</span><span class="sxs-lookup"><span data-stu-id="3f548-149">The devices being connected into this guide are going to connect to the network via and external cloud network.</span></span> <span data-ttu-id="3f548-150">VPN 経由でデバイスを接続する必要&#39;会社のリソースにアクセスする場合があります。</span><span class="sxs-lookup"><span data-stu-id="3f548-150">It may be that to access company resources you&#39;ll need to connect your devices via VPN.</span></span> <span data-ttu-id="3f548-151">エンド ユーザーがデバイス UI を使用して接続できる VPN にデバイスを接続する方法と、デバイスを管理して PPKG または MDM から VPN プロファイルを受信する方法の両方があります。</span><span class="sxs-lookup"><span data-stu-id="3f548-151">There are several different ways to connect your devices to VPN, both where the end user can connect via using the device UI, or the devices can be managed and receive the VPN profile from either a PPKG or MDM.</span></span> <span data-ttu-id="3f548-152">VPN を設定する方法については、この記事では説明&#39;説明しないので、さまざまな HoloLens VPN プロトコルや VPN の管理方法の詳細については、&#39;と[VPN](/hololens/hololens-network#vpn)の詳細については、これらのガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f548-152">How to set up VPN won&#39;t be covered in this article, so if you&#39;d like to learn more about the different VPN protocols or ways to manage VPN visit [these guides for information on HoloLens and VPN.](/hololens/hololens-network#vpn)</span></span>

## <a name="next-step"></a><span data-ttu-id="3f548-153">次のステップ</span><span class="sxs-lookup"><span data-stu-id="3f548-153">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3f548-154">クラウドに接続されたデプロイ - 構成</span><span class="sxs-lookup"><span data-stu-id="3f548-154">Cloud connected deployment - Configure</span></span>](hololens2-cloud-connected-configure.md)
