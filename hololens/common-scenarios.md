---
title: 一般的なインフラストラクチャの展開シナリオ
description: さまざまな一般的なインフラストラクチャに基づく一般的な展開シナリオ
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
ms.openlocfilehash: a7d847e2d2d335f2e2388535a5cf9d5246bb330b
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253074"
---
# <span data-ttu-id="8fb1e-104">一般的なインフラストラクチャ展開シナリオの概要</span><span class="sxs-lookup"><span data-stu-id="8fb1e-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="8fb1e-105">次の情報は、企業内で Microsoft HoloLens 2 デバイスを展開および管理する際の 3 つの一般的なシナリオのアーキテクチャの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="8fb1e-106">多くの場合、デバイスの管理方法と組織のリソースへのアクセス方法は、既に設定されている要因によって大きく決まります。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="8fb1e-107">既存のインフラストラクチャに基づいて、次のシナリオで一般的なデバイス管理のスタイルを確認し、ニーズに合ったシナリオで展開するガイドをお試しください。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <span data-ttu-id="8fb1e-108">シナリオ</span><span class="sxs-lookup"><span data-stu-id="8fb1e-108">Scenarios</span></span>

<span data-ttu-id="8fb1e-109">次の図は、HoloLens 2 展開の 3 つの一般的なシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
![シナリオ図](images/scenarios.jpg)

### <span data-ttu-id="8fb1e-111">シナリオ A: クラウド接続デバイスへの展開</span><span class="sxs-lookup"><span data-stu-id="8fb1e-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="8fb1e-112">HoloLens 2 は、主に企業ネットワークの外部の環境で使用するために展開されます。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="8fb1e-113">企業リソースにはアクセスされないか、VPN を介して制限される場合があります。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-113">Corporate resources are not accessed or may be limited through VPN.</span></span> <span data-ttu-id="8fb1e-114">この展開は、企業内の管理対象モバイル デバイスに似ています。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="8fb1e-115">基本的な一般的な構成</span><span class="sxs-lookup"><span data-stu-id="8fb1e-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="8fb1e-116">Wi-Fiネットワークは、通常、インターネットサービスとクラウド サービスに完全に開きます。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="8fb1e-117">Azure AD MDM 自動登録での参加 - MDM (Intune) 管理</span><span class="sxs-lookup"><span data-stu-id="8fb1e-117">Azure AD Join with MDM Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="8fb1e-118">ユーザーが自分の会社のアカウントでサインインする (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="8fb1e-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="8fb1e-119">サポートされているデバイスごとに 1 人または複数のユーザー</span><span class="sxs-lookup"><span data-stu-id="8fb1e-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="8fb1e-120">さまざまなレベルのデバイス ロックダウン構成が、完全に開いているアプリから単一のアプリ キオスクまで、特定の使用例に基づいて適用されます。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="8fb1e-121">1 つ以上のアプリケーションが MDM 経由で展開される</span><span class="sxs-lookup"><span data-stu-id="8fb1e-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="8fb1e-122">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="8fb1e-122">Common Challenges</span></span>
   * <span data-ttu-id="8fb1e-123">シナリオの要件に基づいて HoloLens 2 に適用する MDM 構成を決定します。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="8fb1e-124">シナリオに似た展開ガイドについては、リモート アシスト付きのクラウド接続 [HoloLens 2 のガイドを確認してください](hololens2-cloud-connected-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-124">For a deployment guide that is similar to scenario A review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8fb1e-125">展開ガイド - リモート アシスト付きのクラウド接続 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="8fb1e-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <span data-ttu-id="8fb1e-126">シナリオ B: 組織のネットワーク内に展開する</span><span class="sxs-lookup"><span data-stu-id="8fb1e-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="8fb1e-127">HoloLens 2 は、主に内部の企業リソースにアクセスできる企業ネットワークで使用するために展開されます。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="8fb1e-128">インターネットサービスとクラウド サービスが制限される場合があります。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="8fb1e-129">この展開は、ほとんどの Windows 10 PC で一般的な展開です。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-129">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="8fb1e-130">基本的な一般的な構成</span><span class="sxs-lookup"><span data-stu-id="8fb1e-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="8fb1e-131">Wi-Fiネットワークは、内部リソースにアクセスできる内部企業ネットワークであり、インターネットまたはクラウド サービスへのアクセスが制限されています。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="8fb1e-132">AZURE AD MDM 自動登録への参加</span><span class="sxs-lookup"><span data-stu-id="8fb1e-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="8fb1e-133">MDM (Intune) の管理</span><span class="sxs-lookup"><span data-stu-id="8fb1e-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="8fb1e-134">ユーザーが自分の会社のアカウントでサインインする (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="8fb1e-134">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="8fb1e-135">サポートされているデバイスごとに 1 人または複数のユーザー</span><span class="sxs-lookup"><span data-stu-id="8fb1e-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="8fb1e-136">さまざまなレベルのデバイス ロックダウン構成が、完全に開いているアプリから単一のアプリ キオスクまで、特定の使用例に基づいて適用されます。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="8fb1e-137">1 つ以上のアプリケーションが MDM 経由で展開される</span><span class="sxs-lookup"><span data-stu-id="8fb1e-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="8fb1e-138">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="8fb1e-138">Common Challenges</span></span>
   * <span data-ttu-id="8fb1e-139">HoloLens 2 では、オンプレミスの会議参加AD SCCM はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-139">HoloLens 2 does not support on premises AD join or SCCM.</span></span> <span data-ttu-id="8fb1e-140">AZURE のみAD MDM に参加できます。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="8fb1e-141">現在でも多くの企業は、オンプレミスの AD に参加しているデバイスとして Windows 10 PC を展開しています。これは System Center Configuration Manager (SCCM) によって管理され、クラウドベースの MDM ソリューションを介して内部 Windows 10 デバイスを管理するためのインフラストラクチャが展開/構成されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="8fb1e-142">HoloLens 2 はクラウド ファースト デバイスであり、ユーザー認証、OS 更新プログラム、MDM 管理などのためにインターネットとクラウドに接続されたサービスに大きく依存しています。企業ネットワークに接続する場合、HoloLens 2 および HoloLens 2 で実行されるアプリケーションへのアクセスを有効にするには、プロキシ/ファイアウォールの規則を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, etc. When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="8fb1e-143">企業Wi-Fi接続には、通常、デバイスまたはユーザーをネットワークに対して認証するための証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-143">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="8fb1e-144">MDM を介して Windows 10 デバイスに証明書を展開するために必要なインフラストラクチャまたは設定は、構成が困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-144">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

### <span data-ttu-id="8fb1e-145">シナリオ C: 安全なオフライン環境での展開</span><span class="sxs-lookup"><span data-stu-id="8fb1e-145">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="8fb1e-146">HoloLens 2 は、主にオフラインで使用するために展開され、ネットワークやインターネットにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-146">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="8fb1e-147">これは、セキュリティが高い場所または機密性の高い場所に対する一般的な展開です。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-147">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="8fb1e-148">基本的な一般的な構成</span><span class="sxs-lookup"><span data-stu-id="8fb1e-148">Basic Common Configurations</span></span>
   * <span data-ttu-id="8fb1e-149">Wi-Fiは無効です。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-149">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="8fb1e-150">必要に応じて、USB 経由のイーサネットで LAN 接続が有効になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-150">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="8fb1e-151">管理されていない。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-151">Not Managed.</span></span>
   * <span data-ttu-id="8fb1e-152">デバイス サインイン用のローカル ユーザー アカウント。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-152">Local user account for device sign in.</span></span>
     * <span data-ttu-id="8fb1e-153">HoloLens 2 では、ローカル アカウントが 1 つしかサポートされません。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-153">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="8fb1e-154">デバイスのロックダウン構成のレベルは、特定の使用例に基づいてプロビジョニング パッケージによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-154">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="8fb1e-155">これらの構成は、通常、セキュリティで保護された環境の要件のために非常に制限されています。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-155">These configurations are typically very restricted due to secure environment requirements.</span></span>
   * <span data-ttu-id="8fb1e-156">1 つ以上のアプリケーションがプロビジョニング パッケージ経由で展開される</span><span class="sxs-lookup"><span data-stu-id="8fb1e-156">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="8fb1e-157">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="8fb1e-157">Common Challenges</span></span>
   * <span data-ttu-id="8fb1e-158">プロビジョニング パッケージで使用できる構成のセットは限られています</span><span class="sxs-lookup"><span data-stu-id="8fb1e-158">There is a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="8fb1e-159">クラウド サービスを利用できないので、HoloLens 2 の機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-159">Cloud services are not able to be leveraged, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="8fb1e-160">これらのデバイスを手動でセットアップ、構成、および更新する必要が生じ、管理上のオーバーヘッドが高くなります。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-160">Higher administrative overhead since these devices have to be setup, configured, and updated manually.</span></span>

<span data-ttu-id="8fb1e-161">このシナリオに似た展開ガイドについては、「オフライン セキュア展開ガイド [」を参照してください](hololens-common-scenarios-offline-secure.md)。</span><span class="sxs-lookup"><span data-stu-id="8fb1e-161">For a deployment guide that is similar to this scenario review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8fb1e-162">展開ガイド - オフラインセキュア HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="8fb1e-162">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
