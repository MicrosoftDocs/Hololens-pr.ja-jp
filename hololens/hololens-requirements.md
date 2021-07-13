---
title: 一般的な配置シナリオ
description: インフラストラクチャ、デバイス管理、モバイル デバイス管理HoloLens、エンタープライズ環境でのAzure Active Directoryの展開と管理について説明します。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bgener
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: ccccdcc7d3188919d02eb5855131137415c12d16
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639830"
---
# <a name="common-deployment-scenarios"></a><span data-ttu-id="9eca8-103">一般的な配置シナリオ</span><span class="sxs-lookup"><span data-stu-id="9eca8-103">Common Deployment Scenarios</span></span>

## <a name="overview"></a><span data-ttu-id="9eca8-104">概要</span><span class="sxs-lookup"><span data-stu-id="9eca8-104">Overview</span></span>

<span data-ttu-id="9eca8-105">このページでは、エンタープライズ内の 2 つのデバイスを展開および管理する場合の 3 つの一般的Microsoft HoloLens概要を示します。</span><span class="sxs-lookup"><span data-stu-id="9eca8-105">This page provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span>

<span data-ttu-id="9eca8-106">多くの場合、デバイスを管理し、組織のリソースにアクセスする方法は、主に既に設定されている要因によって決まります。</span><span class="sxs-lookup"><span data-stu-id="9eca8-106">Often, how you manage your devices and access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="9eca8-107">既存のインフラストラクチャに基づいて、次のシナリオで一般的なデバイス管理スタイル (MDM) を確認してから、「商用環境での[HoloLens 2](hololens-core-components.md)展開の計画」を参照して、ニーズに一致するシナリオを判断してください。</span><span class="sxs-lookup"><span data-stu-id="9eca8-107">Based on your existing infrastructure, we invite you to review the common device management style (MDM) in the following scenarios and then read [Planning HoloLens 2 deployments in a commercial environment](hololens-core-components.md) to determine which scenario matches your needs.</span></span> <span data-ttu-id="9eca8-108">デプロイ中に使用できる対応するガイドも 3 つ用意されています。</span><span class="sxs-lookup"><span data-stu-id="9eca8-108">There are also three corresponding guides available for use during your deployment.</span></span>


 1. [<span data-ttu-id="9eca8-109">クラウド接続された環境のデプロイ ガイド</span><span class="sxs-lookup"><span data-stu-id="9eca8-109">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)
     1. [<span data-ttu-id="9eca8-110">クラウド接続された環境 (外部クライアント) のデプロイ ガイド</span><span class="sxs-lookup"><span data-stu-id="9eca8-110">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)
 1. [<span data-ttu-id="9eca8-111">企業ネットワークの展開ガイド</span><span class="sxs-lookup"><span data-stu-id="9eca8-111">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)
 1. [<span data-ttu-id="9eca8-112">オフラインでの安全な環境展開ガイド</span><span class="sxs-lookup"><span data-stu-id="9eca8-112">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a><span data-ttu-id="9eca8-113">シナリオ A: クラウドに接続されたデバイスにデプロイする</span><span class="sxs-lookup"><span data-stu-id="9eca8-113">Scenario A: Deploy to cloud connected devices</span></span>

<span data-ttu-id="9eca8-114">このシナリオは、会社内にマネージド モバイル デバイスを展開する場合と同等です。</span><span class="sxs-lookup"><span data-stu-id="9eca8-114">This scenario is comparable to deploying managed mobile devices within a company.</span></span> <span data-ttu-id="9eca8-115">HoloLens 2は、主に企業ネットワークの外部環境で使用するためにデプロイされます。</span><span class="sxs-lookup"><span data-stu-id="9eca8-115">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="9eca8-116">企業リソースにはアクセスされないか、VPN 経由で制限される場合があります。</span><span class="sxs-lookup"><span data-stu-id="9eca8-116">Corporate resources aren't accessed or may be limited through VPN.</span></span> 
 * <span data-ttu-id="9eca8-117">基本的な一般的な構成</span><span class="sxs-lookup"><span data-stu-id="9eca8-117">Basic Common Configurations</span></span>
   * <span data-ttu-id="9eca8-118">Wi-Fiネットワークは、通常、インターネットおよびクラウド サービスに対して完全に開きます。</span><span class="sxs-lookup"><span data-stu-id="9eca8-118">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="9eca8-119">Azure AD Mobile デバイス管理 (MDM) 自動登録に参加する - MDM (Intune) マネージド</span><span class="sxs-lookup"><span data-stu-id="9eca8-119">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="9eca8-120">ユーザーが自分の企業アカウントでサインインする (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="9eca8-120">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="9eca8-121">サポートされているデバイスごとに 1 人または複数のユーザー</span><span class="sxs-lookup"><span data-stu-id="9eca8-121">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="9eca8-122">デバイス ロックダウン構成のレベルは、フル オープンからシングル アプリ キオスクまで、特定の使用事例に基づいて適用されます。</span><span class="sxs-lookup"><span data-stu-id="9eca8-122">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="9eca8-123">1 つ以上のアプリケーションが MDM 経由でデプロイされる</span><span class="sxs-lookup"><span data-stu-id="9eca8-123">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="9eca8-124">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="9eca8-124">Common Challenges</span></span>
   * <span data-ttu-id="9eca8-125">シナリオの要件に基づいて、アプリケーションに適用HoloLens 2 MDM 構成を決定します。</span><span class="sxs-lookup"><span data-stu-id="9eca8-125">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="9eca8-126">[![シナリオ A 図 ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="9eca8-126">[ ![Scenario A diagram](images/deployment-guides-revised-scenario-a.png) ](images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>

<span data-ttu-id="9eca8-127">対応するクラウド接続ガイドでは、HoloLens 2 をデバイス管理に登録し、必要に応じてライセンスを適用し、エンド ユーザーがデバイスのセットアップ時に Remote Assist をすぐに使用できると検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9eca8-127">The corresponding Cloud connected guide covers how to enroll HoloLens 2 into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="9eca8-128">短期的または長期的な外部使用のためにリモート サイトにデバイスを展開するには、外部クライアント ガイドを使用します。</span><span class="sxs-lookup"><span data-stu-id="9eca8-128">Use the External Clients guide to deploy devices to a remote site for short-term or long-term external use.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9eca8-129">クラウド接続された環境のデプロイ ガイド</span><span class="sxs-lookup"><span data-stu-id="9eca8-129">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [<span data-ttu-id="9eca8-130">クラウド接続された環境 (外部クライアント) のデプロイ ガイド</span><span class="sxs-lookup"><span data-stu-id="9eca8-130">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="9eca8-131">シナリオ B: 組織のネットワーク内にデプロイする</span><span class="sxs-lookup"><span data-stu-id="9eca8-131">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="9eca8-132">このシナリオは、ほとんどの PC のクラシック デプロイとWindows 10です。</span><span class="sxs-lookup"><span data-stu-id="9eca8-132">This scenario is identical to a classic deployment for most Windows 10 PCs.</span></span> <span data-ttu-id="9eca8-133">HoloLens 2は、主に社内リソースにアクセスできる企業ネットワークで使用するためにデプロイされます。</span><span class="sxs-lookup"><span data-stu-id="9eca8-133">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="9eca8-134">インターネットサービスとクラウド サービスは制限される場合があります。</span><span class="sxs-lookup"><span data-stu-id="9eca8-134">Internet and cloud services may be limited.</span></span> 

 * <span data-ttu-id="9eca8-135">基本的な一般的な構成</span><span class="sxs-lookup"><span data-stu-id="9eca8-135">Basic Common Configurations</span></span>
   * <span data-ttu-id="9eca8-136">Wi-Fiネットワークは、内部リソースにアクセスできる内部企業ネットワークであり、インターネットまたはクラウド サービスへのアクセスが制限されています。</span><span class="sxs-lookup"><span data-stu-id="9eca8-136">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="9eca8-137">Azure AD MDM 自動登録との結合</span><span class="sxs-lookup"><span data-stu-id="9eca8-137">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="9eca8-138">MDM (Intune) マネージド</span><span class="sxs-lookup"><span data-stu-id="9eca8-138">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="9eca8-139">ユーザーが自分の企業アカウントでサインインする (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="9eca8-139">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="9eca8-140">サポートされているデバイスごとに 1 人または複数のユーザー</span><span class="sxs-lookup"><span data-stu-id="9eca8-140">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="9eca8-141">デバイス ロックダウン構成のレベルは、フル オープンからシングル アプリ キオスクまで、特定の使用事例に基づいて適用されます。</span><span class="sxs-lookup"><span data-stu-id="9eca8-141">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="9eca8-142">1 つ以上のアプリケーションが MDM 経由でデプロイされる</span><span class="sxs-lookup"><span data-stu-id="9eca8-142">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="9eca8-143">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="9eca8-143">Common Challenges</span></span>
   * <span data-ttu-id="9eca8-144">HoloLens 2 AD 参加または SCCM はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9eca8-144">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="9eca8-145">MDM Azure AD参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9eca8-145">Only Azure AD join with MDM.</span></span> <span data-ttu-id="9eca8-146">現在、多くの企業では、このシナリオでは、System Center Configuration Manager (SCCM) によって管理されるオンプレミスの AD 参加済みデバイスとして Windows 10 PC をデプロイし、クラウドベースの MDM ソリューションを介して内部 Windows 10 デバイスを管理するためのインフラストラクチャがデプロイまたは構成されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9eca8-146">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="9eca8-147">クラウドHoloLens 2デバイスなので、ユーザー認証、OS の更新、MDM 管理などのために、インターネットとクラウドに接続されたサービスに大きく依存しています。</span><span class="sxs-lookup"><span data-stu-id="9eca8-147">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="9eca8-148">企業ネットワークに接続する場合は、HoloLens 2 と、そのネットワーク上で実行されるアプリケーションに対してアクセスを有効にするために、プロキシ/ファイアウォール規則を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9eca8-148">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="9eca8-149">企業Wi-Fi接続には、通常、ネットワークに対してデバイスまたはユーザーを認証するための証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="9eca8-149">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="9eca8-150">MDM を介してデバイスに証明書を展開するためにWindows 10必要なインフラストラクチャまたは設定は、構成が困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9eca8-150">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

<span data-ttu-id="9eca8-151">[![シナリオ B1 図 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="9eca8-151">[ ![Scenario B1 diagram](images/deployment-guides-revised-scenario-b-01-1.png) ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="9eca8-152">[![シナリオ B2 図 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="9eca8-152">[ ![Scenario B2 diagram](images/deployment-guides-revised-scenario-b-02-1.png) ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

<span data-ttu-id="9eca8-153">対応する企業ネットワーク ガイドでは、既存のデバイス管理に HoloLens 2 を登録し、必要に応じてライセンスを適用し、デバイスの設定後にエンド ユーザーが Dynamics 365 ガイドを操作できるだけでなく、カスタムのビジネス アプリを使用できるのを検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9eca8-153">The corresponding Corporate network guide instructs on how to enroll HoloLens 2 into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9eca8-154">企業ネットワークの展開ガイド</span><span class="sxs-lookup"><span data-stu-id="9eca8-154">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="9eca8-155">シナリオ C: 安全なオフライン環境にデプロイする</span><span class="sxs-lookup"><span data-stu-id="9eca8-155">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="9eca8-156">これは、安全性の高い場所または機密性の高い場所に対する一般的なデプロイです。</span><span class="sxs-lookup"><span data-stu-id="9eca8-156">This is a typical deployment for highly secure or confidential locations.</span></span> <span data-ttu-id="9eca8-157">HoloLens 2は、主にネットワークやインターネットにアクセスする必要がないオフラインで使用するためにデプロイされます。</span><span class="sxs-lookup"><span data-stu-id="9eca8-157">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> 
 * <span data-ttu-id="9eca8-158">基本的な一般的な構成</span><span class="sxs-lookup"><span data-stu-id="9eca8-158">Basic Common Configurations</span></span>
   * <span data-ttu-id="9eca8-159">Wi-Fi接続が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="9eca8-159">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="9eca8-160">必要に応じて、USB 経由のイーサネットで LAN 接続を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="9eca8-160">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="9eca8-161">管理されていない。</span><span class="sxs-lookup"><span data-stu-id="9eca8-161">Not Managed.</span></span>
   * <span data-ttu-id="9eca8-162">デバイス サインイン用のローカル ユーザー アカウント。</span><span class="sxs-lookup"><span data-stu-id="9eca8-162">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="9eca8-163">HoloLens 2は、1 つのローカル アカウントのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="9eca8-163">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="9eca8-164">デバイス ロックダウン構成のさまざまなレベルは、特定の使用例に基づいてプロビジョニング パッケージを介して適用されます。</span><span class="sxs-lookup"><span data-stu-id="9eca8-164">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="9eca8-165">これらの構成は、通常、セキュリティで保護された環境の要件のために制限されます。</span><span class="sxs-lookup"><span data-stu-id="9eca8-165">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="9eca8-166">プロビジョニング パッケージを使用して 1 つ以上のアプリケーションをデプロイする</span><span class="sxs-lookup"><span data-stu-id="9eca8-166">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="9eca8-167">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="9eca8-167">Common Challenges</span></span>
   * <span data-ttu-id="9eca8-168">プロビジョニング パッケージを通じて使用できる構成のセットは限られています</span><span class="sxs-lookup"><span data-stu-id="9eca8-168">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="9eca8-169">クラウド サービスを使用できないので、クラウド サービスのHoloLens 2制限されます。</span><span class="sxs-lookup"><span data-stu-id="9eca8-169">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="9eca8-170">これらのデバイスは手動で設定、構成、更新する必要があります。管理オーバーヘッドが高くなります。</span><span class="sxs-lookup"><span data-stu-id="9eca8-170">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="9eca8-171">[![オフライン セキュリティで保護された図 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="9eca8-171">[ ![Offline Secure diagram 1](images/deployment-guides-revised-scenario-c-01.png) ](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

<span data-ttu-id="9eca8-172">対応するオフライン セキュリティ ガイドでは、セキュリティで保護された環境で使用するためにアプリケーションをロックダウンHoloLens 2プロビジョニング パッケージのサンプルを適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9eca8-172">The corresponding Offline secure guide provides instruction for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9eca8-173">オフラインでの安全な環境展開ガイド</span><span class="sxs-lookup"><span data-stu-id="9eca8-173">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)


