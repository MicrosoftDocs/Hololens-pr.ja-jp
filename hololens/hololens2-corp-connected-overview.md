---
title: 展開ガイド– Dynamics 365 Guides による企業接続 HoloLens 2-概要
description: 企業に接続されたネットワーク経由で Dynamics 365 Guides を使用して HoloLens 2 デバイスを登録する方法について説明します。
keywords: HoloLens、管理、企業接続、Dynamics 365 Guides、AAD、Azure AD、MDM、モバイルデバイス管理
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f2f7e1425a208e1f466d995f66118b7e68984242
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637015"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="42c67-104">展開ガイド-Dynamics 365 Guides による企業接続 HoloLens 2-概要</span><span class="sxs-lookup"><span data-stu-id="42c67-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="42c67-105">このガイドは、IT プロフェッショナルが Dynamics 365 Guides (ガイド) を使用して Microsoft HoloLens 2 つのデバイスを組織に計画して展開するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="42c67-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="42c67-106">このガイドは、パイロットと運用環境の展開に適しており、 [シナリオ B: 組織のネットワークガイド内での展開](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) に似ています。</span><span class="sxs-lookup"><span data-stu-id="42c67-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="42c67-107">概念実証をテストした後は、このガイドを使用して、HoloLens を組織に統合することによって先に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="42c67-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="42c67-108">このガイドでは、既存のデバイス管理にデバイスを登録する方法、必要に応じてライセンスを適用する方法、およびエンドユーザーが Dynamics 365 ガイドを操作できること、およびデバイスのセットアップ後にカスタムの基幹業務アプリを使用できることを検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="42c67-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="42c67-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="42c67-109">Prerequisites</span></span>

<span data-ttu-id="42c67-110">次のインフラストラクチャが既に配置されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="42c67-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="42c67-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="42c67-111">Wi-Fi</span></span>
    - <span data-ttu-id="42c67-112">内部リソースにアクセスし、インターネットまたはクラウドサービスへのアクセスが制限されている社内ネットワーク</span><span class="sxs-lookup"><span data-stu-id="42c67-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="42c67-113">デバイスベースの証明書認証。</span><span class="sxs-lookup"><span data-stu-id="42c67-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="42c67-114">Azure Active Directory (Azure AD) MDM 自動登録を使用した参加 ([Azure AD P1 サブスクリプション](/azure/active-directory/fundamentals/active-directory-whatis)が必要)</span><span class="sxs-lookup"><span data-stu-id="42c67-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="42c67-115">MDM (Intune) で管理</span><span class="sxs-lookup"><span data-stu-id="42c67-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="42c67-116">MDM を使用して1つ以上のアプリケーションがデプロイされています。</span><span class="sxs-lookup"><span data-stu-id="42c67-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="42c67-117">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="42c67-117">Network</span></span> 
    - <span data-ttu-id="42c67-118">証明書 (SCEP または PKCS)</span><span class="sxs-lookup"><span data-stu-id="42c67-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="42c67-119">[プロキシ構成]</span><span class="sxs-lookup"><span data-stu-id="42c67-119">Proxy configuration</span></span>
- <span data-ttu-id="42c67-120">ユーザーが自分の会社のアカウントでサインインする (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="42c67-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="42c67-121">デバイスごとに1つまたは複数のユーザーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="42c67-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="42c67-122">完全にオープンからシングルアプリキオスクまで、特定のユースケースに基づいて適用されるさまざまなレベルのデバイスロックダウン構成。</span><span class="sxs-lookup"><span data-stu-id="42c67-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## <a name="guides-licensing-and-requirements"></a>[<span data-ttu-id="42c67-123">ライセンスと要件のガイド</span><span class="sxs-lookup"><span data-stu-id="42c67-123">Guides Licensing and Requirements</span></span>](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- <span data-ttu-id="42c67-124">Azure AD アカウント</span><span class="sxs-lookup"><span data-stu-id="42c67-124">Azure AD account</span></span>
- <span data-ttu-id="42c67-125">Dynamics 365 Guides アプリケーション PC と HoloLens</span><span class="sxs-lookup"><span data-stu-id="42c67-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="42c67-126">Dynamics 365 Guides サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="42c67-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="42c67-127">Microsoft Dataverse 定型文 (含まれています)</span><span class="sxs-lookup"><span data-stu-id="42c67-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="42c67-128">Power Apps (含まれています)</span><span class="sxs-lookup"><span data-stu-id="42c67-128">Power Apps (included)</span></span>
- <span data-ttu-id="42c67-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="42c67-129">Power BI Desktop</span></span>
- <span data-ttu-id="42c67-130">ネットワーク接続</span><span class="sxs-lookup"><span data-stu-id="42c67-130">Network Connectivity</span></span>

<span data-ttu-id="42c67-131">[![Corp 接続ネットワーク図、ステージ 1 ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="42c67-131">[ ![Corp connected network diagram, stage 1](./images/deployment-guides-revised-scenario-b-01-1.png) ](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="42c67-132">[![Corp 接続ネットワーク図、ステージ 2 ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="42c67-132">[ ![Corp connected network diagram, stage 2](./images/deployment-guides-revised-scenario-b-02-1.png) ](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="42c67-133">このガイドで行うこと:</span><span class="sxs-lookup"><span data-stu-id="42c67-133">In this guide you will:</span></span>
### <a name="prepare"></a><span data-ttu-id="42c67-134">準備</span><span class="sxs-lookup"><span data-stu-id="42c67-134">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="42c67-135">HoloLens 2 デバイスのインフラストラクチャに関する基本事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="42c67-135">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="42c67-136">Azure AD の詳細については、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42c67-136">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="42c67-137">Id 管理と Azure AD アカウントを最適に設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="42c67-137">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="42c67-138">まだ準備ができていない場合は、MDM の詳細を確認し、Intune をセットアップしてください。</span><span class="sxs-lookup"><span data-stu-id="42c67-138">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="42c67-139">証明書ベースの Wi-fi について理解を深めます。</span><span class="sxs-lookup"><span data-stu-id="42c67-139">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="42c67-140">プロキシについて理解を深めます。</span><span class="sxs-lookup"><span data-stu-id="42c67-140">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="42c67-141">基幹業務アプリを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="42c67-141">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="42c67-142">組織にガイドを使用する方法の詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="42c67-142">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="42c67-143">構成</span><span class="sxs-lookup"><span data-stu-id="42c67-143">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="42c67-144">ユーザーとグループを作成する方法。</span><span class="sxs-lookup"><span data-stu-id="42c67-144">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="42c67-145">自動登録をセットアップする方法。</span><span class="sxs-lookup"><span data-stu-id="42c67-145">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="42c67-146">企業 Wi-Fi 接続用の Wi-Fi 証明書とプロファイルを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="42c67-146">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="42c67-147">基幹業務 (LOB) アプリパッケージをアップロードして割り当てます。</span><span class="sxs-lookup"><span data-stu-id="42c67-147">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="42c67-148">Dynamics 365 Guides セットアップします。</span><span class="sxs-lookup"><span data-stu-id="42c67-148">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="42c67-149">キオスクモードを構成する方法 (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="42c67-149">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="42c67-150">WDAC を構成する方法 (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="42c67-150">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="42c67-151">配置</span><span class="sxs-lookup"><span data-stu-id="42c67-151">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="42c67-152">デバイスと MDM を使用して登録を検証します。</span><span class="sxs-lookup"><span data-stu-id="42c67-152">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="42c67-153">Wi-Fi 証明書を検証します。</span><span class="sxs-lookup"><span data-stu-id="42c67-153">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="42c67-154">LOB アプリのインストールを検証します。</span><span class="sxs-lookup"><span data-stu-id="42c67-154">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="42c67-155">作成と運用を通じてガイドを検証します。</span><span class="sxs-lookup"><span data-stu-id="42c67-155">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="42c67-156">管理</span><span class="sxs-lookup"><span data-stu-id="42c67-156">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="42c67-157">HoloLens 2 を更新します。</span><span class="sxs-lookup"><span data-stu-id="42c67-157">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="42c67-158">ガイドを更新する方法 (ストアアプリ)</span><span class="sxs-lookup"><span data-stu-id="42c67-158">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="42c67-159">LOB アプリを更新する方法。</span><span class="sxs-lookup"><span data-stu-id="42c67-159">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="42c67-160">開発計画。</span><span class="sxs-lookup"><span data-stu-id="42c67-160">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="42c67-161">サポートプランを作成しています。</span><span class="sxs-lookup"><span data-stu-id="42c67-161">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="42c67-162">デバイス管理オプション。</span><span class="sxs-lookup"><span data-stu-id="42c67-162">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="42c67-163">次のステップ</span><span class="sxs-lookup"><span data-stu-id="42c67-163">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="42c67-164">企業に接続された展開-準備</span><span class="sxs-lookup"><span data-stu-id="42c67-164">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
