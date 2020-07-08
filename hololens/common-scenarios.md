---
title: インフラストラクチャの一般的な展開シナリオ
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 6/30/2020
keywords: HoloLens
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: v-evmill
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: f8d69fc988afabad5f4ae1cce9003381ceb8e68c
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857921"
---
# <span data-ttu-id="c8c97-103">インフラストラクチャの一般的な展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="c8c97-103">Common Infrastructure Deployment Scenarios</span></span>
<span data-ttu-id="c8c97-104">以下の情報は、企業内で Microsoft HoloLens 2 デバイスを展開して管理する場合の3つの一般的なシナリオについて、大まかなアーキテクチャの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="c8c97-104">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span>

## <span data-ttu-id="c8c97-105">シナリオ</span><span class="sxs-lookup"><span data-stu-id="c8c97-105">Scenarios</span></span>

<span data-ttu-id="c8c97-106">次の図は、HoloLens 2 展開の3つの一般的なシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="c8c97-106">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span> 
![用途](images/scenarios.jpg)

### <span data-ttu-id="c8c97-108">シナリオ A</span><span class="sxs-lookup"><span data-stu-id="c8c97-108">Scenario A</span></span>

<span data-ttu-id="c8c97-109">HoloLens 2 は、企業ネットワークの外部にある環境で主に使用するために展開されます。</span><span class="sxs-lookup"><span data-stu-id="c8c97-109">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="c8c97-110">企業リソースはアクセスされないか、VPN によって制限されることがあります。</span><span class="sxs-lookup"><span data-stu-id="c8c97-110">Corporate resources are not accessed or may be limited through VPN.</span></span> <span data-ttu-id="c8c97-111">これは、社内の管理されたモバイルデバイスと非常に似ています。</span><span class="sxs-lookup"><span data-stu-id="c8c97-111">This is a deployment very similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="c8c97-112">基本的な一般的な構成</span><span class="sxs-lookup"><span data-stu-id="c8c97-112">Basic Common Configurations</span></span>
   * <span data-ttu-id="c8c97-113">Wi-fi ネットワークは通常、インターネットとクラウドサービスに対して完全に開かれます。</span><span class="sxs-lookup"><span data-stu-id="c8c97-113">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="c8c97-114">MDM の自動登録による Azure AD の参加--MDM (Intune) 管理</span><span class="sxs-lookup"><span data-stu-id="c8c97-114">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
   * <span data-ttu-id="c8c97-115">ユーザーは独自の企業アカウント (AAD) でサインインする</span><span class="sxs-lookup"><span data-stu-id="c8c97-115">Users sign in with their own corporate account (AAD)</span></span> 
     * <span data-ttu-id="c8c97-116">デバイスごとに1つまたは複数のユーザーがサポートされる</span><span class="sxs-lookup"><span data-stu-id="c8c97-116">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="c8c97-117">さまざまなレベルのデバイスロックダウン構成は、1つのアプリキオスクでの特定のユースケースに基づいて適用されます。</span><span class="sxs-lookup"><span data-stu-id="c8c97-117">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="c8c97-118">MDM を使用して展開された1つ以上のアプリケーション</span><span class="sxs-lookup"><span data-stu-id="c8c97-118">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="c8c97-119">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="c8c97-119">Common Challenges</span></span>
   * <span data-ttu-id="c8c97-120">シナリオ要件に基づいて、HoloLens 2 に適用する MDM 構成を決定します。</span><span class="sxs-lookup"><span data-stu-id="c8c97-120">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

### <span data-ttu-id="c8c97-121">シナリオ B</span><span class="sxs-lookup"><span data-stu-id="c8c97-121">Scenario B</span></span>

<span data-ttu-id="c8c97-122">HoloLens 2 は、内部の企業リソースにアクセスできる企業ネットワークで主に使用するために展開されます。</span><span class="sxs-lookup"><span data-stu-id="c8c97-122">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="c8c97-123">インターネットとクラウドサービスが制限されることがあります。</span><span class="sxs-lookup"><span data-stu-id="c8c97-123">Internet and cloud services may be limited.</span></span> <span data-ttu-id="c8c97-124">これは、ほとんどの Windows 10 Pc 向けの一般的な展開です。</span><span class="sxs-lookup"><span data-stu-id="c8c97-124">This is a typical deployment for most Windows 10 PCs.</span></span>
 * <span data-ttu-id="c8c97-125">基本的な一般的な構成</span><span class="sxs-lookup"><span data-stu-id="c8c97-125">Basic Common Configurations</span></span>
   * <span data-ttu-id="c8c97-126">Wi-fi ネットワークは内部の企業ネットワークであり、内部リソースにアクセスでき、インターネットまたはクラウドサービスへのアクセスが制限されています。</span><span class="sxs-lookup"><span data-stu-id="c8c97-126">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="c8c97-127">MDM の自動登録による Azure AD の参加</span><span class="sxs-lookup"><span data-stu-id="c8c97-127">Azure AD Join with MDM Auto Enrollment</span></span> 
   * <span data-ttu-id="c8c97-128">MDM (Intune) 管理</span><span class="sxs-lookup"><span data-stu-id="c8c97-128">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="c8c97-129">ユーザーは独自の企業アカウント (AAD) でサインインする</span><span class="sxs-lookup"><span data-stu-id="c8c97-129">Users sign in with their own corporate account (AAD)</span></span>
     * <span data-ttu-id="c8c97-130">デバイスごとに1つまたは複数のユーザーがサポートされる</span><span class="sxs-lookup"><span data-stu-id="c8c97-130">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="c8c97-131">さまざまなレベルのデバイスロックダウン構成は、1つのアプリキオスクでの特定のユースケースに基づいて適用されます。</span><span class="sxs-lookup"><span data-stu-id="c8c97-131">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="c8c97-132">MDM を使用して展開された1つ以上のアプリケーション</span><span class="sxs-lookup"><span data-stu-id="c8c97-132">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="c8c97-133">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="c8c97-133">Common Challenges</span></span>
   * <span data-ttu-id="c8c97-134">HoloLens 2 は、オンプレミス広告の参加または SCCM をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c8c97-134">HoloLens 2 does not support on premises AD join or SCCM.</span></span> <span data-ttu-id="c8c97-135">MDM での Azure AD 参加のみ。</span><span class="sxs-lookup"><span data-stu-id="c8c97-135">Only Azure AD join with MDM.</span></span> <span data-ttu-id="c8c97-136">今日、多くの会社は、システムセンター構成マネージャー (SCCM) で管理され、内部の Windows 10 デバイスをクラウドベースの MDM ソリューションで管理するために展開または構成されている、社内の AD 参加デバイスと同様に、Windows 10 Pc を展開しています。</span><span class="sxs-lookup"><span data-stu-id="c8c97-136">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud based MDM solutions.</span></span>
   * <span data-ttu-id="c8c97-137">HoloLens 2 はクラウドの第1のデバイスであるため、ユーザー認証、OS の更新、MDM 管理などのために、インターネットとクラウドに接続されたサービスに大きく依存します。企業ネットワークに接続する場合、HoloLens 2 とそれに対応するアプリケーションのアクセスを有効にするために、プロキシ/ファイアウォールルールを調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8c97-137">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, etc. When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span> 
   * <span data-ttu-id="c8c97-138">一般に、企業の Wi-fi 接続では、デバイスまたはユーザーをネットワークに認証するために証明書が必要になります。</span><span class="sxs-lookup"><span data-stu-id="c8c97-138">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="c8c97-139">MDM を介して Windows 10 デバイスに証明書を展開するために必要なインフラストラクチャまたは設定は、構成が難しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="c8c97-139">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

### <span data-ttu-id="c8c97-140">シナリオ C</span><span class="sxs-lookup"><span data-stu-id="c8c97-140">Scenario C</span></span>

<span data-ttu-id="c8c97-141">HoloLens 2 は、ネットワークやインターネットアクセスなしで主にオフラインで使用するために展開されます。</span><span class="sxs-lookup"><span data-stu-id="c8c97-141">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="c8c97-142">これは、高度なセキュリティで保護された場所または機密情報を使用するための一般的な展開です。</span><span class="sxs-lookup"><span data-stu-id="c8c97-142">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="c8c97-143">基本的な一般的な構成</span><span class="sxs-lookup"><span data-stu-id="c8c97-143">Basic Common Configurations</span></span>
   * <span data-ttu-id="c8c97-144">Wi-fi 接続が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="c8c97-144">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="c8c97-145">必要に応じて、USB 経由のイーサネット接続が有効になっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c8c97-145">Ethernet via USB may be enabled for LAN connectivity if required.</span></span>
   * <span data-ttu-id="c8c97-146">管理されません。</span><span class="sxs-lookup"><span data-stu-id="c8c97-146">Not Managed.</span></span>
   * <span data-ttu-id="c8c97-147">デバイスのサインインのローカルユーザーアカウント。</span><span class="sxs-lookup"><span data-stu-id="c8c97-147">Local user account for device sign in.</span></span>
     * <span data-ttu-id="c8c97-148">HoloLens 2 でサポートされるローカルアカウントは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="c8c97-148">HoloLens 2 supports only 1 local account.</span></span>
   * <span data-ttu-id="c8c97-149">さまざまなレベルのデバイスロックダウン構成は、特定のユースケースに基づくプロビジョニングパッケージによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="c8c97-149">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="c8c97-150">これらの構成は、通常、安全な環境要件によって制限されています。</span><span class="sxs-lookup"><span data-stu-id="c8c97-150">These configurations are typically very restricted due to secure environment requirements.</span></span>
   * <span data-ttu-id="c8c97-151">プロビジョニングパッケージによって展開される1つ以上のアプリケーション</span><span class="sxs-lookup"><span data-stu-id="c8c97-151">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="c8c97-152">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="c8c97-152">Common Challenges</span></span>
   * <span data-ttu-id="c8c97-153">プロビジョニングパッケージで利用できる構成は限られています。</span><span class="sxs-lookup"><span data-stu-id="c8c97-153">There are a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="c8c97-154">クラウドサービスは利用できないため、HoloLens 2 の機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="c8c97-154">Cloud services are not able to be leveraged, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="c8c97-155">これらのデバイスは、手動で設定、構成、更新する必要があるため、管理上のオーバーヘッドが高くなります。</span><span class="sxs-lookup"><span data-stu-id="c8c97-155">Higher administrative overhead since these devices have to be setup, configured, and updated manually.</span></span>
