---
title: 一般的なインフラストラクチャのデプロイ シナリオ
description: Mixed Reality 用のさまざまなインフラストラクチャデプロイに基づく、最も一般的なデプロイ シナリオについて説明します。
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
ms.openlocfilehash: 30a35fb0fe5d5b669249df25ebff0228b552596c
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397425"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a><span data-ttu-id="5bd74-104">一般的なインフラストラクチャのデプロイ シナリオの概要</span><span class="sxs-lookup"><span data-stu-id="5bd74-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="5bd74-105">次の情報では、エンタープライズ内の 2 つのデバイスを展開および管理する場合の 3 つの一般的Microsoft HoloLens概要を示します。</span><span class="sxs-lookup"><span data-stu-id="5bd74-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="5bd74-106">多くの場合、デバイスの管理方法と組織のリソースへのアクセス方法は、主に既に設定されている要因によって決まります。</span><span class="sxs-lookup"><span data-stu-id="5bd74-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="5bd74-107">既存のインフラストラクチャに基づいて、次のシナリオで一般的なデバイス管理スタイルを確認し、ニーズに合ったシナリオでのデプロイに関するガイドをお試しください。</span><span class="sxs-lookup"><span data-stu-id="5bd74-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <a name="scenarios"></a><span data-ttu-id="5bd74-108">シナリオ</span><span class="sxs-lookup"><span data-stu-id="5bd74-108">Scenarios</span></span>

<span data-ttu-id="5bd74-109">次の図は、次の 2 つの一般的なマネージド シナリオをHoloLens 2しています。</span><span class="sxs-lookup"><span data-stu-id="5bd74-109">The diagram below represents two typical managed scenarios for HoloLens 2 deployments.</span></span>
 

<span data-ttu-id="5bd74-110">オフラインでセキュリティで保護されたデプロイを可能にする 3 番目のシナリオも用意されています。</span><span class="sxs-lookup"><span data-stu-id="5bd74-110">There is also third scenario that allows for offline secure deployments.</span></span>

### <a name="scenario-a-deploy-to-cloud-connected-devices"></a><span data-ttu-id="5bd74-111">シナリオ A: クラウドに接続されたデバイスにデプロイする</span><span class="sxs-lookup"><span data-stu-id="5bd74-111">Scenario A: Deploy to cloud connected devices</span></span>

<span data-ttu-id="5bd74-112">HoloLens 2は、主に企業ネットワークの外部環境で使用するためにデプロイされます。</span><span class="sxs-lookup"><span data-stu-id="5bd74-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="5bd74-113">企業リソースにはアクセスされないか、VPN 経由で制限される場合があります。</span><span class="sxs-lookup"><span data-stu-id="5bd74-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="5bd74-114">この展開は、会社内のマネージド モバイル デバイスに似ています。</span><span class="sxs-lookup"><span data-stu-id="5bd74-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="5bd74-115">基本的な一般的な構成</span><span class="sxs-lookup"><span data-stu-id="5bd74-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="5bd74-116">Wi-Fiネットワークは、通常、インターネットおよびクラウド サービスに対して完全に開きます。</span><span class="sxs-lookup"><span data-stu-id="5bd74-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="5bd74-117">Azure AD Mobile デバイス管理 (MDM) 自動登録に参加する - MDM (Intune) マネージド</span><span class="sxs-lookup"><span data-stu-id="5bd74-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="5bd74-118">ユーザーが自分の企業アカウントでサインインする (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="5bd74-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="5bd74-119">サポートされているデバイスごとに 1 人または複数のユーザー</span><span class="sxs-lookup"><span data-stu-id="5bd74-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="5bd74-120">デバイス ロックダウン構成のレベルは、フル オープンからシングル アプリ キオスクまで、特定の使用事例に基づいて適用されます。</span><span class="sxs-lookup"><span data-stu-id="5bd74-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="5bd74-121">1 つ以上のアプリケーションが MDM 経由でデプロイされる</span><span class="sxs-lookup"><span data-stu-id="5bd74-121">One or more applications are deployed via MDM</span></span>



* <span data-ttu-id="5bd74-122">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="5bd74-122">Common Challenges</span></span>
   * <span data-ttu-id="5bd74-123">シナリオの要件に基づいて、HoloLens 2 に適用する MDM 構成を決定します。</span><span class="sxs-lookup"><span data-stu-id="5bd74-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="5bd74-124">[![シナリオ図 ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5bd74-124">[ ![Scenario A diagram](images/deployment-guides-revised-scenario-a.png) ](images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>

<span data-ttu-id="5bd74-125">このシナリオに似たデプロイガイドについては、「 [クラウド接続環境の展開ガイド](hololens2-cloud-connected-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bd74-125">For a deployment guide that is similar to this scenario review our guide for [Cloud connected environment deployment guide](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5bd74-126">クラウドに接続された環境のデプロイガイド</span><span class="sxs-lookup"><span data-stu-id="5bd74-126">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="5bd74-127">クラウド接続環境 (外部クライアント) 配置ガイド</span><span class="sxs-lookup"><span data-stu-id="5bd74-127">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="5bd74-128">シナリオ B: 組織のネットワーク内に展開する</span><span class="sxs-lookup"><span data-stu-id="5bd74-128">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="5bd74-129">HoloLens 2 は、主に企業ネットワーク上で企業内部リソースにアクセスするために展開されます。</span><span class="sxs-lookup"><span data-stu-id="5bd74-129">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="5bd74-130">インターネットおよびクラウドサービスは制限される場合があります。</span><span class="sxs-lookup"><span data-stu-id="5bd74-130">Internet and cloud services may be limited.</span></span> <span data-ttu-id="5bd74-131">この展開は、ほとんどの Windows 10 Pc における一般的な展開です。</span><span class="sxs-lookup"><span data-stu-id="5bd74-131">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="5bd74-132">基本的な共通構成</span><span class="sxs-lookup"><span data-stu-id="5bd74-132">Basic Common Configurations</span></span>
   * <span data-ttu-id="5bd74-133">Wi-Fi ネットワークは、内部リソースにアクセスし、インターネットまたはクラウドサービスへのアクセスが制限されている社内ネットワークです。</span><span class="sxs-lookup"><span data-stu-id="5bd74-133">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="5bd74-134">MDM の自動登録を使用した Azure AD 参加</span><span class="sxs-lookup"><span data-stu-id="5bd74-134">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="5bd74-135">MDM (Intune) で管理</span><span class="sxs-lookup"><span data-stu-id="5bd74-135">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="5bd74-136">ユーザーが自分の会社のアカウントでサインインする (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="5bd74-136">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="5bd74-137">デバイスごとに1つまたは複数のユーザーがサポートされています</span><span class="sxs-lookup"><span data-stu-id="5bd74-137">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="5bd74-138">さまざまなレベルのデバイスロックダウン構成は、完全にオープンからシングルアプリキオスクまで、特定のユースケースに基づいて適用されます。</span><span class="sxs-lookup"><span data-stu-id="5bd74-138">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="5bd74-139">MDM を使用して1つ以上のアプリケーションが展開されている</span><span class="sxs-lookup"><span data-stu-id="5bd74-139">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="5bd74-140">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="5bd74-140">Common Challenges</span></span>
   * <span data-ttu-id="5bd74-141">HoloLens 2 では、オンプレミスの AD join または SCCM はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5bd74-141">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="5bd74-142">MDM Azure AD参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bd74-142">Only Azure AD join with MDM.</span></span> <span data-ttu-id="5bd74-143">現在も多くの企業では、このシナリオで Windows 10 PC をオンプレミスの AD 参加済みデバイスとして展開し、System Center 構成マネージャー (SCCM) によって管理され、クラウドベースの MDM ソリューションを介して内部 Windows 10 デバイスを管理するためのインフラストラクチャがデプロイまたは構成されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5bd74-143">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="5bd74-144">クラウドHoloLens 2デバイスなので、ユーザー認証、OS の更新、MDM 管理などのために、インターネットとクラウドに接続されたサービスに大きく依存しています。</span><span class="sxs-lookup"><span data-stu-id="5bd74-144">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="5bd74-145">企業ネットワークに接続する場合は、HoloLens 2 と、そのネットワーク上で実行されるアプリケーションへのアクセスを有効にするためのプロキシ/ファイアウォール規則を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bd74-145">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="5bd74-146">企業Wi-Fi接続には、通常、ネットワークに対してデバイスまたはユーザーを認証するための証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="5bd74-146">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="5bd74-147">MDM を介してデバイスに証明書を展開するためにWindows 10必要なインフラストラクチャまたは設定は、構成が困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="5bd74-147">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

<span data-ttu-id="5bd74-148">[![シナリオ B1 図 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5bd74-148">[ ![Scenario B1 diagram](images/deployment-guides-revised-scenario-b-01-1.png) ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="5bd74-149">[![シナリオ B2 図 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5bd74-149">[ ![Scenario B2 diagram](images/deployment-guides-revised-scenario-b-02-1.png) ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

<span data-ttu-id="5bd74-150">このシナリオに似たデプロイ ガイドについては、企業ネットワーク展開ガイドの [ガイドを参照してください](hololens2-corp-connected-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5bd74-150">For a deployment guide that is similar to this scenario review our guide for [Corporate network deployment guide](hololens2-corp-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5bd74-151">企業ネットワーク展開ガイド</span><span class="sxs-lookup"><span data-stu-id="5bd74-151">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="5bd74-152">シナリオ C: 安全なオフライン環境にデプロイする</span><span class="sxs-lookup"><span data-stu-id="5bd74-152">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="5bd74-153">HoloLens 2は、主にネットワークやインターネットにアクセスする必要がないオフラインで使用するためにデプロイされます。</span><span class="sxs-lookup"><span data-stu-id="5bd74-153">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="5bd74-154">これは、安全性の高い場所または機密性の高い場所に対する一般的なデプロイです。</span><span class="sxs-lookup"><span data-stu-id="5bd74-154">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="5bd74-155">基本的な一般的な構成</span><span class="sxs-lookup"><span data-stu-id="5bd74-155">Basic Common Configurations</span></span>
   * <span data-ttu-id="5bd74-156">Wi-Fi接続が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="5bd74-156">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="5bd74-157">必要に応じて、USB 経由のイーサネットで LAN 接続を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="5bd74-157">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="5bd74-158">管理されていない。</span><span class="sxs-lookup"><span data-stu-id="5bd74-158">Not Managed.</span></span>
   * <span data-ttu-id="5bd74-159">デバイス サインイン用のローカル ユーザー アカウント。</span><span class="sxs-lookup"><span data-stu-id="5bd74-159">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="5bd74-160">HoloLens 2は、1 つのローカル アカウントのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5bd74-160">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="5bd74-161">デバイス ロックダウン構成のさまざまなレベルは、特定の使用例に基づいてプロビジョニング パッケージを介して適用されます。</span><span class="sxs-lookup"><span data-stu-id="5bd74-161">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="5bd74-162">これらの構成は、通常、セキュリティで保護された環境要件によって制限されます。</span><span class="sxs-lookup"><span data-stu-id="5bd74-162">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="5bd74-163">1つ以上のアプリケーションがプロビジョニングパッケージを使用して展開されています</span><span class="sxs-lookup"><span data-stu-id="5bd74-163">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="5bd74-164">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="5bd74-164">Common Challenges</span></span>
   * <span data-ttu-id="5bd74-165">プロビジョニングパッケージで使用できる構成は限られています。</span><span class="sxs-lookup"><span data-stu-id="5bd74-165">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="5bd74-166">Cloud services は使用できないため、HoloLens 2 の機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="5bd74-166">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="5bd74-167">これらのデバイスは手動でセットアップ、構成、および更新する必要があるため、管理オーバーヘッドが高くなります。</span><span class="sxs-lookup"><span data-stu-id="5bd74-167">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="5bd74-168">[![オフラインのセキュリティで保護された図 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5bd74-168">[ ![Offline Secure diagram 1](images/deployment-guides-revised-scenario-c-01.png) ](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

<span data-ttu-id="5bd74-169">このシナリオに似た展開ガイドについては、「 [オフラインの安全な環境の展開ガイド」](hololens-common-scenarios-offline-secure.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bd74-169">For a deployment guide that is similar to this scenario review our [Offline secure environment deployment guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5bd74-170">オフライン安全環境の展開ガイド</span><span class="sxs-lookup"><span data-stu-id="5bd74-170">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)
