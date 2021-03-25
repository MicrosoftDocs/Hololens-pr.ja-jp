---
title: 一般的なインフラストラクチャの展開シナリオ
description: 複合現実向けさまざまなインフラストラクチャ展開に基づく最も一般的な展開シナリオについて説明します。
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
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
ms.openlocfilehash: 4b9bd4335e45180276d69af2ce5f33a38ecb800f
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448495"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a><span data-ttu-id="c3511-104">共通インフラストラクチャ展開シナリオの概要</span><span class="sxs-lookup"><span data-stu-id="c3511-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="c3511-105">次の情報は、エンタープライズ内で Microsoft HoloLens 2 デバイスを展開および管理する場合の 3 つの一般的なシナリオの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="c3511-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="c3511-106">多くの場合、デバイスの管理方法と組織のリソースへのアクセス方法は、主に既に設定されている要因によって決まります。</span><span class="sxs-lookup"><span data-stu-id="c3511-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="c3511-107">既存のインフラストラクチャに基づいて、次のシナリオで一般的なデバイス管理スタイルを確認し、ニーズに合ったシナリオで展開するガイドを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="c3511-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <a name="scenarios"></a><span data-ttu-id="c3511-108">シナリオ</span><span class="sxs-lookup"><span data-stu-id="c3511-108">Scenarios</span></span>

<span data-ttu-id="c3511-109">次の図は、HoloLens 2 展開の 3 つの一般的なシナリオを表しています。</span><span class="sxs-lookup"><span data-stu-id="c3511-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
![シナリオ図](images/scenarios.jpg)

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a><span data-ttu-id="c3511-111">シナリオ A: クラウド接続デバイスへの展開</span><span class="sxs-lookup"><span data-stu-id="c3511-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="c3511-112">HoloLens 2 は、主に企業ネットワーク外の環境で使用するために展開されます。</span><span class="sxs-lookup"><span data-stu-id="c3511-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="c3511-113">企業のリソースにアクセスできないか、VPN を介して制限される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c3511-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="c3511-114">この展開は、企業内の管理対象モバイル デバイスに似ています。</span><span class="sxs-lookup"><span data-stu-id="c3511-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="c3511-115">基本的な一般的な構成</span><span class="sxs-lookup"><span data-stu-id="c3511-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="c3511-116">Wi-Fiネットワークは、通常、インターネットおよびクラウド サービスに対して完全に開きます。</span><span class="sxs-lookup"><span data-stu-id="c3511-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="c3511-117">Azure AD モバイル デバイス管理 (MDM) 自動登録に参加する--MDM (Intune) マネージ</span><span class="sxs-lookup"><span data-stu-id="c3511-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="c3511-118">ユーザーが自分の企業アカウントでサインインする (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="c3511-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="c3511-119">サポートされるデバイスごとに 1 人または複数のユーザー</span><span class="sxs-lookup"><span data-stu-id="c3511-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="c3511-120">デバイス のロックダウン構成のレベルは、完全に開くから単一のアプリ キオスクまで、特定の使用例に基づいて適用されます。</span><span class="sxs-lookup"><span data-stu-id="c3511-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="c3511-121">1 つ以上のアプリケーションが MDM 経由で展開される</span><span class="sxs-lookup"><span data-stu-id="c3511-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="c3511-122">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="c3511-122">Common Challenges</span></span>
   * <span data-ttu-id="c3511-123">シナリオ要件に基づいて HoloLens 2 に適用する MDM 構成を決定します。</span><span class="sxs-lookup"><span data-stu-id="c3511-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="c3511-124">シナリオに似た展開ガイドについては、リモート アシストを使用した [クラウド接続 HoloLens 2 のガイドを参照してください](hololens2-cloud-connected-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c3511-124">For a deployment guide that is similar to scenario A review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c3511-125">展開ガイド – リモート アシストを使用したクラウド接続 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="c3511-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="c3511-126">シナリオ B: 組織のネットワーク内に展開する</span><span class="sxs-lookup"><span data-stu-id="c3511-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="c3511-127">HoloLens 2 は、主に内部の企業リソースにアクセスできる企業ネットワークで使用するために展開されます。</span><span class="sxs-lookup"><span data-stu-id="c3511-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="c3511-128">インターネットおよびクラウド サービスは制限される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c3511-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="c3511-129">この展開は、ほとんどの Windows 10 PC の一般的な展開です。</span><span class="sxs-lookup"><span data-stu-id="c3511-129">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="c3511-130">基本的な一般的な構成</span><span class="sxs-lookup"><span data-stu-id="c3511-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="c3511-131">Wi-Fiネットワークは、内部リソースにアクセスできる内部企業ネットワークであり、インターネットまたはクラウド サービスへのアクセスが制限されています。</span><span class="sxs-lookup"><span data-stu-id="c3511-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="c3511-132">Azure AD MDM 自動登録に参加する</span><span class="sxs-lookup"><span data-stu-id="c3511-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="c3511-133">MDM (Intune) マネージ</span><span class="sxs-lookup"><span data-stu-id="c3511-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="c3511-134">ユーザーが自分の企業アカウントでサインインする (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="c3511-134">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="c3511-135">サポートされるデバイスごとに 1 人または複数のユーザー</span><span class="sxs-lookup"><span data-stu-id="c3511-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="c3511-136">デバイス のロックダウン構成のレベルは、完全に開くから単一のアプリ キオスクまで、特定の使用例に基づいて適用されます。</span><span class="sxs-lookup"><span data-stu-id="c3511-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="c3511-137">1 つ以上のアプリケーションが MDM 経由で展開される</span><span class="sxs-lookup"><span data-stu-id="c3511-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="c3511-138">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="c3511-138">Common Challenges</span></span>
   * <span data-ttu-id="c3511-139">HoloLens 2 は、参加または SCCM のADサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c3511-139">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="c3511-140">MDM にADできるのは Azure のみです。</span><span class="sxs-lookup"><span data-stu-id="c3511-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="c3511-141">多くの企業は、現在もこのシナリオでは、オンプレミスの AD 参加デバイスとして Windows 10 PC を展開し、System Center Configuration Manager (SCCM) によって管理され、クラウドベースの MDM ソリューションを介して内部 Windows 10 デバイスを管理するためのインフラストラクチャが展開または構成されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c3511-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="c3511-142">HoloLens 2 はクラウド ファースト デバイスなので、ユーザー認証、OS 更新プログラム、MDM 管理などのインターネットおよびクラウド接続サービスに大きく依存しています。</span><span class="sxs-lookup"><span data-stu-id="c3511-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="c3511-143">企業ネットワークに接続する場合、HoloLens 2 と、その上で実行されるアプリケーションへのアクセスを有効にするには、プロキシ/ファイアウォールルールを調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3511-143">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="c3511-144">企業Wi-Fi接続には、通常、デバイスまたはユーザーをネットワークに対して認証するための証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="c3511-144">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="c3511-145">MDM を介して Windows 10 デバイスに証明書を展開するために必要なインフラストラクチャまたは設定は、構成が困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c3511-145">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c3511-146">展開ガイド – Dynamics 365 ガイドを使用した企業接続 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="c3511-146">Deployment Guide – Corporate connected HoloLens 2 with Dynamics 365 Guides</span></span>](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="c3511-147">シナリオ C: 安全なオフライン環境での展開</span><span class="sxs-lookup"><span data-stu-id="c3511-147">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="c3511-148">HoloLens 2 は、主にネットワークやインターネット アクセスがないオフラインで使用するために展開されます。</span><span class="sxs-lookup"><span data-stu-id="c3511-148">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="c3511-149">これは、高度にセキュリティで保護された場所または機密の場所に対する一般的な展開です。</span><span class="sxs-lookup"><span data-stu-id="c3511-149">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="c3511-150">基本的な一般的な構成</span><span class="sxs-lookup"><span data-stu-id="c3511-150">Basic Common Configurations</span></span>
   * <span data-ttu-id="c3511-151">Wi-Fiが無効になっている場合。</span><span class="sxs-lookup"><span data-stu-id="c3511-151">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="c3511-152">必要に応じて、USB 経由のイーサネットで LAN 接続を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="c3511-152">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="c3511-153">管理されていない。</span><span class="sxs-lookup"><span data-stu-id="c3511-153">Not Managed.</span></span>
   * <span data-ttu-id="c3511-154">デバイス サインインのローカル ユーザー アカウント。</span><span class="sxs-lookup"><span data-stu-id="c3511-154">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="c3511-155">HoloLens 2 では、ローカル アカウントが 1 つしかサポートされません。</span><span class="sxs-lookup"><span data-stu-id="c3511-155">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="c3511-156">デバイスロックダウン構成のレベルは、特定の使用例に基づいてプロビジョニング パッケージを介して適用されます。</span><span class="sxs-lookup"><span data-stu-id="c3511-156">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="c3511-157">これらの構成は、通常、セキュリティで保護された環境要件のために制限されます。</span><span class="sxs-lookup"><span data-stu-id="c3511-157">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="c3511-158">1 つ以上のアプリケーションがプロビジョニング パッケージ経由で展開される</span><span class="sxs-lookup"><span data-stu-id="c3511-158">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="c3511-159">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="c3511-159">Common Challenges</span></span>
   * <span data-ttu-id="c3511-160">プロビジョニング パッケージを使用して使用できる構成のセットは制限されています</span><span class="sxs-lookup"><span data-stu-id="c3511-160">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="c3511-161">クラウド サービスを使用できないので、HoloLens 2 の機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="c3511-161">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="c3511-162">これらのデバイスを手動で設定、構成、および更新する必要がある場合の管理オーバーヘッドが大きくなります。</span><span class="sxs-lookup"><span data-stu-id="c3511-162">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="c3511-163">このシナリオに似た展開ガイドについては、「オフライン セキュア展開ガイド [」を参照してください](hololens-common-scenarios-offline-secure.md)。</span><span class="sxs-lookup"><span data-stu-id="c3511-163">For a deployment guide that is similar to this scenario review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c3511-164">展開ガイド – オフライン セキュア HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="c3511-164">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
