---
title: 一般的なインフラストラクチャの展開シナリオ
description: さまざまなインフラストラクチャの展開に基づいて、さまざまなシナリオについて説明します。
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
keywords: hololens
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
ms.openlocfilehash: 4b9bd4335e45180276d69af2ce5f33a38ecb800f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309481"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a><span data-ttu-id="d3e34-104">一般的なインフラストラクチャの展開シナリオの概要</span><span class="sxs-lookup"><span data-stu-id="d3e34-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="d3e34-105">ここでは、企業内で Microsoft HoloLens 2 デバイスを展開および管理する場合の3つの一般的なシナリオについて、大まかなアーキテクチャの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="d3e34-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="d3e34-106">多くの場合、デバイスの管理方法と組織のリソースへのアクセス方法は、既に導入されている要因によって決まります。</span><span class="sxs-lookup"><span data-stu-id="d3e34-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="d3e34-107">既存のインフラストラクチャに基づいて、次のシナリオで一般的なデバイス管理スタイルを確認し、ニーズに合ったシナリオでデプロイするためのガイドを試してみることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d3e34-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <a name="scenarios"></a><span data-ttu-id="d3e34-108">シナリオ</span><span class="sxs-lookup"><span data-stu-id="d3e34-108">Scenarios</span></span>

<span data-ttu-id="d3e34-109">次の図は、HoloLens 2 展開の一般的な3つのシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="d3e34-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
<span data-ttu-id="d3e34-110">![シナリオ図](images/scenarios.jpg)</span><span class="sxs-lookup"><span data-stu-id="d3e34-110">![Scenarios diagram](images/scenarios.jpg)</span></span>

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a><span data-ttu-id="d3e34-111">シナリオ A: クラウド接続デバイスにデプロイする</span><span class="sxs-lookup"><span data-stu-id="d3e34-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="d3e34-112">HoloLens 2 は、主に企業ネットワークの外部の環境で使用するために展開されます。</span><span class="sxs-lookup"><span data-stu-id="d3e34-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="d3e34-113">企業リソースにアクセスできないか、VPN 経由で制限されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d3e34-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="d3e34-114">この展開は、社内の管理対象モバイルデバイスに似ています。</span><span class="sxs-lookup"><span data-stu-id="d3e34-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="d3e34-115">基本的な共通構成</span><span class="sxs-lookup"><span data-stu-id="d3e34-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="d3e34-116">Wi-Fi ネットワークは、通常、インターネットおよびクラウドサービスに対して完全に開いています。</span><span class="sxs-lookup"><span data-stu-id="d3e34-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="d3e34-117">モバイルデバイス管理 (MDM) の自動登録を使用した Azure AD 参加--MDM (Intune) で管理</span><span class="sxs-lookup"><span data-stu-id="d3e34-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="d3e34-118">ユーザーが自分の会社のアカウントでサインインする (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="d3e34-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="d3e34-119">デバイスごとに1つまたは複数のユーザーがサポートされています</span><span class="sxs-lookup"><span data-stu-id="d3e34-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="d3e34-120">さまざまなレベルのデバイスロックダウン構成は、完全にオープンからシングルアプリキオスクまで、特定のユースケースに基づいて適用されます。</span><span class="sxs-lookup"><span data-stu-id="d3e34-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="d3e34-121">MDM を使用して1つ以上のアプリケーションが展開されている</span><span class="sxs-lookup"><span data-stu-id="d3e34-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="d3e34-122">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="d3e34-122">Common Challenges</span></span>
   * <span data-ttu-id="d3e34-123">シナリオの要件に基づいて、HoloLens 2 に適用する MDM 構成を決定します。</span><span class="sxs-lookup"><span data-stu-id="d3e34-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="d3e34-124">シナリオ A と同様のデプロイガイドについては、「 [Cloud Connected HoloLens 2 とリモート](hololens2-cloud-connected-overview.md)アシスタンスのガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3e34-124">For a deployment guide that is similar to scenario A review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d3e34-125">展開ガイド–リモートアシスタンスを使用したクラウド接続型 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="d3e34-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="d3e34-126">シナリオ B: 組織のネットワーク内に展開する</span><span class="sxs-lookup"><span data-stu-id="d3e34-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="d3e34-127">HoloLens 2 は、主に企業ネットワーク上で企業内部リソースにアクセスするために展開されます。</span><span class="sxs-lookup"><span data-stu-id="d3e34-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="d3e34-128">インターネットおよびクラウドサービスは制限される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d3e34-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="d3e34-129">この展開は、ほとんどの Windows 10 Pc における一般的な展開です。</span><span class="sxs-lookup"><span data-stu-id="d3e34-129">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="d3e34-130">基本的な共通構成</span><span class="sxs-lookup"><span data-stu-id="d3e34-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="d3e34-131">Wi-Fi ネットワークは、内部リソースにアクセスし、インターネットまたはクラウドサービスへのアクセスが制限されている社内ネットワークです。</span><span class="sxs-lookup"><span data-stu-id="d3e34-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="d3e34-132">MDM の自動登録を使用した Azure AD 参加</span><span class="sxs-lookup"><span data-stu-id="d3e34-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="d3e34-133">MDM (Intune) で管理</span><span class="sxs-lookup"><span data-stu-id="d3e34-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="d3e34-134">ユーザーが自分の会社のアカウントでサインインする (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="d3e34-134">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="d3e34-135">デバイスごとに1つまたは複数のユーザーがサポートされています</span><span class="sxs-lookup"><span data-stu-id="d3e34-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="d3e34-136">さまざまなレベルのデバイスロックダウン構成は、完全にオープンからシングルアプリキオスクまで、特定のユースケースに基づいて適用されます。</span><span class="sxs-lookup"><span data-stu-id="d3e34-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="d3e34-137">MDM を使用して1つ以上のアプリケーションが展開されている</span><span class="sxs-lookup"><span data-stu-id="d3e34-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="d3e34-138">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="d3e34-138">Common Challenges</span></span>
   * <span data-ttu-id="d3e34-139">HoloLens 2 では、オンプレミスの AD join または SCCM はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d3e34-139">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="d3e34-140">MDM との結合のみ Azure AD ます。</span><span class="sxs-lookup"><span data-stu-id="d3e34-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="d3e34-141">現在、多くの企業では、このシナリオでは、System Center Configuration Manager (SCCM) によって管理されているオンプレミス AD 参加済みデバイスとして Windows 10 Pc を展開します。また、クラウドベースの MDM ソリューションを使用して内部 Windows 10 デバイスを管理するためにインフラストラクチャをデプロイまたは構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="d3e34-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="d3e34-142">HoloLens 2 はクラウドの最初のデバイスであるため、ユーザー認証、OS の更新、MDM の管理などのために、インターネットおよびクラウドに接続されたサービスに大きく依存します。</span><span class="sxs-lookup"><span data-stu-id="d3e34-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="d3e34-143">企業ネットワークに接続する場合、プロキシ/ファイアウォールルールを調整して、HoloLens 2 およびそれで実行されるアプリケーションにアクセスできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3e34-143">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="d3e34-144">企業の Wi-Fi 接続では、通常、デバイスまたはユーザーをネットワークに認証するために証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="d3e34-144">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="d3e34-145">MDM を使用して Windows 10 デバイスに証明書を展開するために必要なインフラストラクチャまたは設定は、構成することが困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d3e34-145">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d3e34-146">展開ガイド-企業接続 HoloLens 2 と Dynamics 365 ガイド</span><span class="sxs-lookup"><span data-stu-id="d3e34-146">Deployment Guide – Corporate connected HoloLens 2 with Dynamics 365 Guides</span></span>](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="d3e34-147">シナリオ C: セキュリティで保護されたオフライン環境に配置する</span><span class="sxs-lookup"><span data-stu-id="d3e34-147">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="d3e34-148">HoloLens 2 は、主にネットワークやインターネットにアクセスすることなくオフラインで使用するように展開されています。</span><span class="sxs-lookup"><span data-stu-id="d3e34-148">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="d3e34-149">これは、セキュリティで保護された、または機密性の高い場所への一般的な展開です。</span><span class="sxs-lookup"><span data-stu-id="d3e34-149">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="d3e34-150">基本的な共通構成</span><span class="sxs-lookup"><span data-stu-id="d3e34-150">Basic Common Configurations</span></span>
   * <span data-ttu-id="d3e34-151">Wi-Fi 接続が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="d3e34-151">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="d3e34-152">必要に応じて、LAN 経由のイーサネットが LAN 接続に対して有効になっている場合があります。</span><span class="sxs-lookup"><span data-stu-id="d3e34-152">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="d3e34-153">管理されていません。</span><span class="sxs-lookup"><span data-stu-id="d3e34-153">Not Managed.</span></span>
   * <span data-ttu-id="d3e34-154">デバイスのサインイン用のローカルユーザーアカウント。</span><span class="sxs-lookup"><span data-stu-id="d3e34-154">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="d3e34-155">HoloLens 2 でサポートされるローカルアカウントは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="d3e34-155">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="d3e34-156">さまざまなレベルのデバイスロックダウン構成は、特定のユースケースに基づいてパッケージをプロビジョニングすることによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="d3e34-156">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="d3e34-157">これらの構成は、通常、セキュリティで保護された環境要件によって制限されます。</span><span class="sxs-lookup"><span data-stu-id="d3e34-157">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="d3e34-158">1つ以上のアプリケーションがプロビジョニングパッケージを使用して展開されています</span><span class="sxs-lookup"><span data-stu-id="d3e34-158">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="d3e34-159">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="d3e34-159">Common Challenges</span></span>
   * <span data-ttu-id="d3e34-160">プロビジョニングパッケージで使用できる構成は限られています。</span><span class="sxs-lookup"><span data-stu-id="d3e34-160">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="d3e34-161">Cloud services は使用できないため、HoloLens 2 の機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="d3e34-161">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="d3e34-162">これらのデバイスは手動でセットアップ、構成、および更新する必要があるため、管理オーバーヘッドが高くなります。</span><span class="sxs-lookup"><span data-stu-id="d3e34-162">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="d3e34-163">このシナリオに似た展開ガイドについては、「 [オフラインのセキュリティで保護された展開ガイド」](hololens-common-scenarios-offline-secure.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3e34-163">For a deployment guide that is similar to this scenario review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d3e34-164">展開ガイド– Offline Secure HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="d3e34-164">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
