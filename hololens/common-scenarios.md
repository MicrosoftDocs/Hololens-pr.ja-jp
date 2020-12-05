---
title: 一般的なインフラストラクチャの展開シナリオ
description: 一般的なさまざまなインフラストラクチャに基づいたいくつかの一般的な展開シナリオ
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 11/04/2020
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
ms.openlocfilehash: e9e91535bb49b5076547e8b9934bdc86808d41fc
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2020
ms.locfileid: "11195570"
---
# <span data-ttu-id="f87bb-104">インフラストラクチャの一般的な展開シナリオの概要</span><span class="sxs-lookup"><span data-stu-id="f87bb-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="f87bb-105">以下の情報は、企業内で Microsoft HoloLens 2 デバイスを展開して管理する場合の3つの一般的なシナリオについて、大まかなアーキテクチャの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="f87bb-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="f87bb-106">多くの場合、デバイスの管理方法と組織のリソースへのアクセス方法は、既に実装されている要因によって決まります。</span><span class="sxs-lookup"><span data-stu-id="f87bb-106">Often how you manage your devices and how access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="f87bb-107">既存のインフラストラクチャに基づいて、次のシナリオで一般的なデバイス管理スタイルを確認するように依頼して、ニーズに合ったシナリオで展開するためのガイドをお試しください。</span><span class="sxs-lookup"><span data-stu-id="f87bb-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <span data-ttu-id="f87bb-108">シナリオ</span><span class="sxs-lookup"><span data-stu-id="f87bb-108">Scenarios</span></span>

<span data-ttu-id="f87bb-109">次の図は、HoloLens 2 展開の3つの一般的なシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="f87bb-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
![シナリオ図](images/scenarios.jpg)

### <span data-ttu-id="f87bb-111">シナリオ A: クラウド接続デバイスへの展開</span><span class="sxs-lookup"><span data-stu-id="f87bb-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="f87bb-112">HoloLens 2 は、企業ネットワークの外部にある環境で主に使用するために展開されます。</span><span class="sxs-lookup"><span data-stu-id="f87bb-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="f87bb-113">企業リソースはアクセスされないか、VPN によって制限されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f87bb-113">Corporate resources are not accessed or may be limited through VPN.</span></span> <span data-ttu-id="f87bb-114">これは、社内の管理されたモバイルデバイスと非常に似ています。</span><span class="sxs-lookup"><span data-stu-id="f87bb-114">This is a deployment very similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="f87bb-115">基本的な一般的な構成</span><span class="sxs-lookup"><span data-stu-id="f87bb-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="f87bb-116">通常、Wi-Fi ネットワークは、インターネットとクラウドサービスに対して完全に開かれます。</span><span class="sxs-lookup"><span data-stu-id="f87bb-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="f87bb-117">MDM の自動登録による Azure AD の参加--MDM (Intune) 管理</span><span class="sxs-lookup"><span data-stu-id="f87bb-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
   * <span data-ttu-id="f87bb-118">ユーザーは独自の企業アカウント (AAD) でサインインする</span><span class="sxs-lookup"><span data-stu-id="f87bb-118">Users sign in with their own corporate account (AAD)</span></span>
     * <span data-ttu-id="f87bb-119">デバイスごとに1つまたは複数のユーザーがサポートされる</span><span class="sxs-lookup"><span data-stu-id="f87bb-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="f87bb-120">さまざまなレベルのデバイスロックダウン構成は、1つのアプリキオスクでの特定のユースケースに基づいて適用されます。</span><span class="sxs-lookup"><span data-stu-id="f87bb-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="f87bb-121">MDM を使用して展開された1つ以上のアプリケーション</span><span class="sxs-lookup"><span data-stu-id="f87bb-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="f87bb-122">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="f87bb-122">Common Challenges</span></span>
   * <span data-ttu-id="f87bb-123">シナリオ要件に基づいて、HoloLens 2 に適用する MDM 構成を決定します。</span><span class="sxs-lookup"><span data-stu-id="f87bb-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="f87bb-124">このシナリオと同様の展開ガイドについては、「リモートアシスタンスを使用して [クラウドに接続された HoloLens 2](hololens2-cloud-connected-overview.md)」のガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f87bb-124">For a deployment guide that is similar to this scenario please review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f87bb-125">展開ガイド–リモートアシスタンスによるクラウド接続の HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="f87bb-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <span data-ttu-id="f87bb-126">シナリオ B: 組織のネットワーク内に展開する</span><span class="sxs-lookup"><span data-stu-id="f87bb-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="f87bb-127">HoloLens 2 は、内部の企業リソースにアクセスできる企業ネットワークで主に使用するために展開されます。</span><span class="sxs-lookup"><span data-stu-id="f87bb-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="f87bb-128">インターネットとクラウドサービスが制限されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f87bb-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="f87bb-129">これは、ほとんどの Windows 10 Pc 向けの一般的な展開です。</span><span class="sxs-lookup"><span data-stu-id="f87bb-129">This is a typical deployment for most Windows 10 PCs.</span></span>
 * <span data-ttu-id="f87bb-130">基本的な一般的な構成</span><span class="sxs-lookup"><span data-stu-id="f87bb-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="f87bb-131">Wi-Fi ネットワークは内部のリソースにアクセスできる社内ネットワークで、インターネットまたはクラウドサービスへのアクセスは制限されています。</span><span class="sxs-lookup"><span data-stu-id="f87bb-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="f87bb-132">MDM の自動登録による Azure AD の参加</span><span class="sxs-lookup"><span data-stu-id="f87bb-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="f87bb-133">MDM (Intune) 管理</span><span class="sxs-lookup"><span data-stu-id="f87bb-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="f87bb-134">ユーザーは独自の企業アカウント (AAD) でサインインする</span><span class="sxs-lookup"><span data-stu-id="f87bb-134">Users sign in with their own corporate account (AAD)</span></span>
     * <span data-ttu-id="f87bb-135">デバイスごとに1つまたは複数のユーザーがサポートされる</span><span class="sxs-lookup"><span data-stu-id="f87bb-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="f87bb-136">さまざまなレベルのデバイスロックダウン構成は、1つのアプリキオスクでの特定のユースケースに基づいて適用されます。</span><span class="sxs-lookup"><span data-stu-id="f87bb-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="f87bb-137">MDM を使用して展開された1つ以上のアプリケーション</span><span class="sxs-lookup"><span data-stu-id="f87bb-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="f87bb-138">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="f87bb-138">Common Challenges</span></span>
   * <span data-ttu-id="f87bb-139">HoloLens 2 は、オンプレミス広告の参加または SCCM をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f87bb-139">HoloLens 2 does not support on premises AD join or SCCM.</span></span> <span data-ttu-id="f87bb-140">MDM での Azure AD 参加のみ。</span><span class="sxs-lookup"><span data-stu-id="f87bb-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="f87bb-141">今日、多くの会社は、システムセンター構成マネージャー (SCCM) で管理され、内部の Windows 10 デバイスをクラウドベースの MDM ソリューションで管理するために展開または構成されている、社内の AD 参加デバイスと同様に、Windows 10 Pc を展開しています。</span><span class="sxs-lookup"><span data-stu-id="f87bb-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud based MDM solutions.</span></span>
   * <span data-ttu-id="f87bb-142">HoloLens 2 はクラウドの第1のデバイスであるため、ユーザー認証、OS の更新、MDM 管理などのために、インターネットとクラウドに接続されたサービスに大きく依存します。企業ネットワークに接続する場合、HoloLens 2 とそれに対応するアプリケーションのアクセスを有効にするために、プロキシ/ファイアウォールルールを調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f87bb-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, etc. When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="f87bb-143">企業 Wi-Fi の接続では、通常、デバイスまたはユーザーをネットワークに対して認証するために証明書が必要になります。</span><span class="sxs-lookup"><span data-stu-id="f87bb-143">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="f87bb-144">MDM を介して Windows 10 デバイスに証明書を展開するために必要なインフラストラクチャまたは設定は、構成が難しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="f87bb-144">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

### <span data-ttu-id="f87bb-145">シナリオ C: セキュリティで保護されたオフライン環境で展開する</span><span class="sxs-lookup"><span data-stu-id="f87bb-145">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="f87bb-146">HoloLens 2 は、ネットワークやインターネットアクセスなしで主にオフラインで使用するために展開されます。</span><span class="sxs-lookup"><span data-stu-id="f87bb-146">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="f87bb-147">これは、高度なセキュリティで保護された場所または機密情報を使用するための一般的な展開です。</span><span class="sxs-lookup"><span data-stu-id="f87bb-147">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="f87bb-148">基本的な一般的な構成</span><span class="sxs-lookup"><span data-stu-id="f87bb-148">Basic Common Configurations</span></span>
   * <span data-ttu-id="f87bb-149">Wi-Fi 接続が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="f87bb-149">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="f87bb-150">必要に応じて、USB 経由のイーサネット接続が有効になっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f87bb-150">Ethernet via USB may be enabled for LAN connectivity if required.</span></span>
   * <span data-ttu-id="f87bb-151">管理されません。</span><span class="sxs-lookup"><span data-stu-id="f87bb-151">Not Managed.</span></span>
   * <span data-ttu-id="f87bb-152">デバイスのサインインのローカルユーザーアカウント。</span><span class="sxs-lookup"><span data-stu-id="f87bb-152">Local user account for device sign in.</span></span>
     * <span data-ttu-id="f87bb-153">HoloLens 2 でサポートされるローカルアカウントは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="f87bb-153">HoloLens 2 supports only 1 local account.</span></span>
   * <span data-ttu-id="f87bb-154">さまざまなレベルのデバイスロックダウン構成は、特定のユースケースに基づくプロビジョニングパッケージによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="f87bb-154">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="f87bb-155">これらの構成は、通常、安全な環境要件によって制限されています。</span><span class="sxs-lookup"><span data-stu-id="f87bb-155">These configurations are typically very restricted due to secure environment requirements.</span></span>
   * <span data-ttu-id="f87bb-156">プロビジョニングパッケージによって展開される1つ以上のアプリケーション</span><span class="sxs-lookup"><span data-stu-id="f87bb-156">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="f87bb-157">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="f87bb-157">Common Challenges</span></span>
   * <span data-ttu-id="f87bb-158">プロビジョニングパッケージで利用できる構成は限られています。</span><span class="sxs-lookup"><span data-stu-id="f87bb-158">There are a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="f87bb-159">クラウドサービスは利用できないため、HoloLens 2 の機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="f87bb-159">Cloud services are not able to be leveraged, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="f87bb-160">これらのデバイスは、手動で設定、構成、更新する必要があるため、管理上のオーバーヘッドが高くなります。</span><span class="sxs-lookup"><span data-stu-id="f87bb-160">Higher administrative overhead since these devices have to be setup, configured, and updated manually.</span></span>

<span data-ttu-id="f87bb-161">このシナリオと同じような展開ガイドについては、「 [オフラインのセキュリティで保護された展開ガイド」](hololens-common-scenarios-offline-secure.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f87bb-161">For a deployment guide that is similar to this scenario please review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f87bb-162">展開ガイド–オフラインで安全な HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="f87bb-162">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
