---
title: ライセンス要件
description: ''
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 18a583f407b19c5b86870a49b8182d45f46a45f5
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857805"
---
# <span data-ttu-id="b2401-102">ライセンス要件</span><span class="sxs-lookup"><span data-stu-id="b2401-102">License requirements</span></span>

## <span data-ttu-id="b2401-103">モバイル デバイス管理 (MDM) ライセンス ガイダンス</span><span class="sxs-lookup"><span data-stu-id="b2401-103">Mobile Device Management (MDM) Licenses Guidance</span></span>

<span data-ttu-id="b2401-104">HoloLens デバイスの管理を計画している場合は、Azure AD と MDM が必要です。</span><span class="sxs-lookup"><span data-stu-id="b2401-104">If you plan on managing your HoloLens devices, you will need Azure AD and an MDM.</span></span> <span data-ttu-id="b2401-105">Active Directory (AD) を使用して HoloLens デバイスを管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="b2401-105">Active Director (AD) cannot be used to manage HoloLens devices.</span></span>
<span data-ttu-id="b2401-106">Intune 以外の MDM の使用を計画している場合、[Azure Active Directory ライセンス](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)が必要です。</span><span class="sxs-lookup"><span data-stu-id="b2401-106">If you plan on using an MDM other than Intune, an [Azure Active Directory Licenses](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) is required.</span></span>
<span data-ttu-id="b2401-107">Intune を MDM として使用する場合は、Intune ライセンスを含むスイートのリストを[以下](https://docs.microsoft.com/intune/fundamentals/licenses)に示します。</span><span class="sxs-lookup"><span data-stu-id="b2401-107">If you plan on using Intune as your MDM,  [here](https://docs.microsoft.com/intune/fundamentals/licenses) are a list of suites that includes Intune licenses.</span></span> **<span data-ttu-id="b2401-108">Azure AD はこれらのスイートの大部分に含まれていることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="b2401-108">Please note that Azure AD is included in the majority of these suites.</span></span>**

## <span data-ttu-id="b2401-109">シナリオと製品に必要なライセンスを特定する</span><span class="sxs-lookup"><span data-stu-id="b2401-109">Identify the licenses needed for your scenario and products</span></span>

### <span data-ttu-id="b2401-110">HoloLens ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="b2401-110">HoloLens Licenses Requirements</span></span>

<span data-ttu-id="b2401-111">HoloLens 第 1 世代デバイスを Windows Holographic for Business にアップグレードする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="b2401-111">You may need to upgrade your HoloLens 1st Gen Device to Windows Holographic for Business.</span></span> <span data-ttu-id="b2401-112">(アップグレードが必要かどうかを判断するには、「[HoloLens commercial features (HoloLensの商用機能)](holoLens-commercial-features.md#feature-comparison-between-editions)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="b2401-112">(See [HoloLens commercial features](holoLens-commercial-features.md#feature-comparison-between-editions) to determine if you need to upgrade).</span></span>

 <span data-ttu-id="b2401-113">その場合、次の操作をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2401-113">If so, you will need to do the following:</span></span>

- <span data-ttu-id="b2401-114">HoloLens Enterprise ライセンスの XML ファイルを取得します</span><span class="sxs-lookup"><span data-stu-id="b2401-114">Acquire a HoloLens Enterprise license XML file</span></span>
- <span data-ttu-id="b2401-115">XML ファイルを HoloLens に適用します。</span><span class="sxs-lookup"><span data-stu-id="b2401-115">Apply the XML file to the HoloLens.</span></span> <span data-ttu-id="b2401-116">これは、[プロビジョニング パッケージ](hololens-provisioning.md)または[モバイル デバイス マネージャー](https://docs.microsoft.com/intune/configuration/holographic-upgrade)を使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="b2401-116">You can do this through a [Provisioning package](hololens-provisioning.md) or through your [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span></span>

### <span data-ttu-id="b2401-117">リモート アシスト ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="b2401-117">Remote Assist License Requirements</span></span>

<span data-ttu-id="b2401-118">必要なライセンスとデバイスがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b2401-118">Make sure you have the required licensing and device.</span></span> <span data-ttu-id="b2401-119">更新されたライセンスおよび製品の要件は、[こちら](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="b2401-119">Updated licensing and product requirements can be found [here](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).</span></span>

1. [<span data-ttu-id="b2401-120">リモート アシスト ライセンス</span><span class="sxs-lookup"><span data-stu-id="b2401-120">Remote Assist License</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
1. [<span data-ttu-id="b2401-121">Teams フリーミアム/Teams</span><span class="sxs-lookup"><span data-stu-id="b2401-121">Teams Freemium/Teams</span></span>](https://products.office.com/microsoft-teams/free)
1. [<span data-ttu-id="b2401-122">Azure Active Directory (Azure AD) ライセンス</span><span class="sxs-lookup"><span data-stu-id="b2401-122">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

<span data-ttu-id="b2401-123">**[このクロステナント シナリオ](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** の実装を計画している場合、情報バリア ライセンスが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b2401-123">If you plan on implementing **[this cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, you may need an Information Barriers license.</span></span> <span data-ttu-id="b2401-124">情報バリア ライセンスが必要かどうかを確認するには、[この記事](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2401-124">Please see [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <span data-ttu-id="b2401-125">ライセンス要件のガイド</span><span class="sxs-lookup"><span data-stu-id="b2401-125">Guides License Requirements</span></span>

<span data-ttu-id="b2401-126">更新されたライセンスおよびデバイスの要件は、[こちら](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="b2401-126">Updated licensing and device requirements can be found [here](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span></span>

1. [<span data-ttu-id="b2401-127">Azure Active Directory (Azure AD) ライセンス</span><span class="sxs-lookup"><span data-stu-id="b2401-127">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [<span data-ttu-id="b2401-128">Power BI</span><span class="sxs-lookup"><span data-stu-id="b2401-128">Power BI</span></span>](https://powerbi.microsoft.com/desktop/)
1. [<span data-ttu-id="b2401-129">ガイド</span><span class="sxs-lookup"><span data-stu-id="b2401-129">Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
