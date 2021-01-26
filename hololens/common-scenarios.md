---
title: 一般的なインフラストラクチャの展開シナリオ
description: Mixed Reality の異なるインフラストラクチャ展開に基づく、最も一般的な展開シナリオについて説明します。
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
ms.openlocfilehash: 6f398327ba82e15a15da21c2b3f90222178d257a
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283628"
---
# <span data-ttu-id="3e219-104">一般的なインフラストラクチャ展開シナリオの概要</span><span class="sxs-lookup"><span data-stu-id="3e219-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="3e219-105">次の情報は、企業内で Microsoft HoloLens 2 デバイスを展開および管理する際の 3 つの一般的なシナリオのアーキテクチャの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="3e219-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="3e219-106">多くの場合、デバイスの管理方法と組織のリソースへのアクセス方法は、既に設定されている要因によって大きく決まります。</span><span class="sxs-lookup"><span data-stu-id="3e219-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="3e219-107">既存のインフラストラクチャに基づいて、次のシナリオで一般的なデバイス管理のスタイルを確認し、ニーズに合ったシナリオで展開するガイドをお試しください。</span><span class="sxs-lookup"><span data-stu-id="3e219-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <span data-ttu-id="3e219-108">シナリオ</span><span class="sxs-lookup"><span data-stu-id="3e219-108">Scenarios</span></span>

<span data-ttu-id="3e219-109">次の図は、HoloLens 2 展開の 3 つの一般的なシナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="3e219-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
![シナリオ図](images/scenarios.jpg)

### <span data-ttu-id="3e219-111">シナリオ A: クラウド接続デバイスへの展開</span><span class="sxs-lookup"><span data-stu-id="3e219-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="3e219-112">HoloLens 2 は、主に企業ネットワークの外部の環境で使用するために展開されます。</span><span class="sxs-lookup"><span data-stu-id="3e219-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="3e219-113">企業リソースにはアクセスされないか、VPN を介して制限される場合があります。</span><span class="sxs-lookup"><span data-stu-id="3e219-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="3e219-114">この展開は、企業内の管理対象モバイル デバイスに似ています。</span><span class="sxs-lookup"><span data-stu-id="3e219-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="3e219-115">基本的な一般的な構成</span><span class="sxs-lookup"><span data-stu-id="3e219-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="3e219-116">Wi-Fiネットワークは、通常、インターネットサービスとクラウド サービスに完全に開きます。</span><span class="sxs-lookup"><span data-stu-id="3e219-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="3e219-117">Azure AD モバイル デバイス管理 (MDM) 自動登録を使用した参加 - MDM (Intune) 管理</span><span class="sxs-lookup"><span data-stu-id="3e219-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="3e219-118">ユーザーが自分の会社のアカウントでサインインする (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="3e219-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="3e219-119">サポートされるデバイスごとに 1 人または複数のユーザー</span><span class="sxs-lookup"><span data-stu-id="3e219-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="3e219-120">さまざまなレベルのデバイス ロックダウン構成が、完全に開いているアプリから単一のアプリ キオスクまで、特定の使用例に基づいて適用されます。</span><span class="sxs-lookup"><span data-stu-id="3e219-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="3e219-121">1 つ以上のアプリケーションが MDM 経由で展開される</span><span class="sxs-lookup"><span data-stu-id="3e219-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="3e219-122">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="3e219-122">Common Challenges</span></span>
   * <span data-ttu-id="3e219-123">シナリオの要件に基づいて HoloLens 2 に適用する MDM 構成を決定します。</span><span class="sxs-lookup"><span data-stu-id="3e219-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="3e219-124">シナリオに似た展開ガイドについては、リモート アシスト付きのクラウド接続 [HoloLens 2 のガイドを確認してください](hololens2-cloud-connected-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="3e219-124">For a deployment guide that is similar to scenario A review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3e219-125">展開ガイド - リモート アシスト付きのクラウド接続 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="3e219-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <span data-ttu-id="3e219-126">シナリオ B: 組織のネットワーク内に展開する</span><span class="sxs-lookup"><span data-stu-id="3e219-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="3e219-127">HoloLens 2 は、主に内部の企業リソースにアクセスできる企業ネットワークで使用するために展開されます。</span><span class="sxs-lookup"><span data-stu-id="3e219-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="3e219-128">インターネットサービスとクラウド サービスが制限される場合があります。</span><span class="sxs-lookup"><span data-stu-id="3e219-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="3e219-129">この展開は、ほとんどの Windows 10 PC で一般的な展開です。</span><span class="sxs-lookup"><span data-stu-id="3e219-129">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="3e219-130">基本的な一般的な構成</span><span class="sxs-lookup"><span data-stu-id="3e219-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="3e219-131">Wi-Fiネットワークは、内部リソースにアクセスできる内部企業ネットワークであり、インターネットまたはクラウド サービスへのアクセスが制限されています。</span><span class="sxs-lookup"><span data-stu-id="3e219-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="3e219-132">AZURE AD MDM 自動登録への参加</span><span class="sxs-lookup"><span data-stu-id="3e219-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="3e219-133">MDM (Intune) の管理</span><span class="sxs-lookup"><span data-stu-id="3e219-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="3e219-134">ユーザーが自分の会社のアカウントでサインインする (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="3e219-134">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="3e219-135">サポートされるデバイスごとに 1 人または複数のユーザー</span><span class="sxs-lookup"><span data-stu-id="3e219-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="3e219-136">さまざまなレベルのデバイス ロックダウン構成が、完全に開いているアプリから単一のアプリ キオスクまで、特定の使用例に基づいて適用されます。</span><span class="sxs-lookup"><span data-stu-id="3e219-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="3e219-137">1 つ以上のアプリケーションが MDM 経由で展開される</span><span class="sxs-lookup"><span data-stu-id="3e219-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="3e219-138">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="3e219-138">Common Challenges</span></span>
   * <span data-ttu-id="3e219-139">HoloLens 2 は、オンプレミスの会議参加や SCCM ADサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3e219-139">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="3e219-140">AZURE のみAD MDM に参加できます。</span><span class="sxs-lookup"><span data-stu-id="3e219-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="3e219-141">現在でも多くの企業は、オンプレミスの AD に参加しているデバイスとして Windows 10 PC を展開しています。これは System Center Configuration Manager (SCCM) によって管理され、クラウドベースの MDM ソリューションを介して内部 Windows 10 デバイスを管理するためのインフラストラクチャが展開/構成されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3e219-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="3e219-142">HoloLens 2 はクラウド ファースト デバイスなので、ユーザー認証、OS 更新プログラム、MDM 管理などのためにインターネットとクラウドに接続されたサービスに大きく依存しています。</span><span class="sxs-lookup"><span data-stu-id="3e219-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="3e219-143">企業ネットワークに接続する場合、HoloLens 2 および HoloLens 2 で実行されるアプリケーションへのアクセスを有効にするには、プロキシ/ファイアウォールの規則を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e219-143">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="3e219-144">企業Wi-Fi接続には、通常、デバイスまたはユーザーをネットワークに対して認証するための証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="3e219-144">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="3e219-145">MDM を介して Windows 10 デバイスに証明書を展開するために必要なインフラストラクチャまたは設定は、構成が困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3e219-145">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

### <span data-ttu-id="3e219-146">シナリオ C: 安全なオフライン環境での展開</span><span class="sxs-lookup"><span data-stu-id="3e219-146">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="3e219-147">HoloLens 2 は、主にオフラインで使用するために展開され、ネットワークやインターネットにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3e219-147">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="3e219-148">これは、セキュリティが高い場所または機密性の高い場所に対する一般的な展開です。</span><span class="sxs-lookup"><span data-stu-id="3e219-148">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="3e219-149">基本的な一般的な構成</span><span class="sxs-lookup"><span data-stu-id="3e219-149">Basic Common Configurations</span></span>
   * <span data-ttu-id="3e219-150">Wi-Fiは無効です。</span><span class="sxs-lookup"><span data-stu-id="3e219-150">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="3e219-151">必要に応じて、USB 経由のイーサネットで LAN 接続が有効になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3e219-151">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="3e219-152">管理されていない。</span><span class="sxs-lookup"><span data-stu-id="3e219-152">Not Managed.</span></span>
   * <span data-ttu-id="3e219-153">デバイス サインイン用のローカル ユーザー アカウント。</span><span class="sxs-lookup"><span data-stu-id="3e219-153">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="3e219-154">HoloLens 2 では、ローカル アカウントが 1 つしかサポートされません。</span><span class="sxs-lookup"><span data-stu-id="3e219-154">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="3e219-155">デバイスのロックダウン構成のレベルは、特定の使用例に基づいてプロビジョニング パッケージによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="3e219-155">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="3e219-156">これらの構成は、通常、セキュリティで保護された環境要件のために制限されます。</span><span class="sxs-lookup"><span data-stu-id="3e219-156">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="3e219-157">1 つ以上のアプリケーションがプロビジョニング パッケージ経由で展開されている</span><span class="sxs-lookup"><span data-stu-id="3e219-157">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="3e219-158">一般的な課題</span><span class="sxs-lookup"><span data-stu-id="3e219-158">Common Challenges</span></span>
   * <span data-ttu-id="3e219-159">プロビジョニング パッケージで利用できる構成のセットは限られています</span><span class="sxs-lookup"><span data-stu-id="3e219-159">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="3e219-160">クラウド サービスを使用できないので、HoloLens 2 の機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="3e219-160">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="3e219-161">これらのデバイスを手動でセットアップ、構成、および更新する必要が生じ、管理上のオーバーヘッドが高くなります。</span><span class="sxs-lookup"><span data-stu-id="3e219-161">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="3e219-162">このシナリオに似た展開ガイドについては、「オフライン セキュア展開ガイド [」を参照してください](hololens-common-scenarios-offline-secure.md)。</span><span class="sxs-lookup"><span data-stu-id="3e219-162">For a deployment guide that is similar to this scenario review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3e219-163">展開ガイド - オフラインセキュア HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="3e219-163">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
