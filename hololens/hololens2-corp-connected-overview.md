---
title: 展開ガイド-Dynamics 365 を使用した企業接続 HoloLens 2 ガイド-概要
description: Dynamics 365 ガイドを使用して、企業に接続されたネットワーク経由で HoloLens 2 デバイスを登録する方法について説明します。
keywords: HoloLens, 管理, 企業接続, Dynamics 365 ガイド, AAD, Azure AD, MDM, モバイルデバイス管理
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
ms.openlocfilehash: 3041a31e6a4f8b51385fa02dfddc21d56993721d
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309774"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="ddb96-104">展開ガイド-企業接続 HoloLens 2 と Dynamics 365 ガイド-概要</span><span class="sxs-lookup"><span data-stu-id="ddb96-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="ddb96-105">このガイドは、IT プロフェッショナルが Dynamics 365 ガイド (ガイド) を使用して Microsoft HoloLens 2 デバイスを組織に計画し、展開するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ddb96-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="ddb96-106">このガイドは、パイロットと運用環境の展開に適しており、 [シナリオ B: 組織のネットワークガイド内での展開](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) に似ています。</span><span class="sxs-lookup"><span data-stu-id="ddb96-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="ddb96-107">概念実証をテストした後、このガイドを使用して、HoloLens を組織に統合することに進みます。</span><span class="sxs-lookup"><span data-stu-id="ddb96-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="ddb96-108">このガイドでは、既存のデバイス管理にデバイスを登録する方法、必要に応じてライセンスを適用する方法、およびエンドユーザーが Dynamics 365 ガイドを操作できること、およびデバイスのセットアップ後にカスタムの基幹業務アプリを使用できることを検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ddb96-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="ddb96-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="ddb96-109">Prerequisites</span></span>

<span data-ttu-id="ddb96-110">次のインフラストラクチャが既に配置されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddb96-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="ddb96-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="ddb96-111">Wi-Fi</span></span>
    - <span data-ttu-id="ddb96-112">内部リソースにアクセスし、インターネットまたはクラウドサービスへのアクセスが制限されている社内ネットワーク</span><span class="sxs-lookup"><span data-stu-id="ddb96-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="ddb96-113">デバイスベースの証明書認証。</span><span class="sxs-lookup"><span data-stu-id="ddb96-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="ddb96-114">Azure Active Directory (Azure AD) MDM 自動登録を使用した参加 ([Azure AD P1 サブスクリプション](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) が必要)</span><span class="sxs-lookup"><span data-stu-id="ddb96-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="ddb96-115">MDM (Intune) で管理</span><span class="sxs-lookup"><span data-stu-id="ddb96-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="ddb96-116">MDM を使用して1つ以上のアプリケーションがデプロイされています。</span><span class="sxs-lookup"><span data-stu-id="ddb96-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="ddb96-117">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="ddb96-117">Network</span></span> 
    - <span data-ttu-id="ddb96-118">証明書 (SCEP または PKCS)</span><span class="sxs-lookup"><span data-stu-id="ddb96-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="ddb96-119">[プロキシ構成]</span><span class="sxs-lookup"><span data-stu-id="ddb96-119">Proxy configuration</span></span>
- <span data-ttu-id="ddb96-120">ユーザーが自分の会社のアカウントでサインインする (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="ddb96-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="ddb96-121">デバイスごとに1つまたは複数のユーザーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ddb96-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="ddb96-122">完全にオープンからシングルアプリキオスクまで、特定のユースケースに基づいて適用されるさまざまなレベルのデバイスロックダウン構成。</span><span class="sxs-lookup"><span data-stu-id="ddb96-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## <a name="guides-licensing-and-requirements"></a>[<span data-ttu-id="ddb96-123">ライセンスと要件のガイド</span><span class="sxs-lookup"><span data-stu-id="ddb96-123">Guides Licensing and Requirements</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- <span data-ttu-id="ddb96-124">Azure AD アカウント</span><span class="sxs-lookup"><span data-stu-id="ddb96-124">Azure AD account</span></span>
- <span data-ttu-id="ddb96-125">Dynamics 365 ガイドアプリケーション PC および HoloLens</span><span class="sxs-lookup"><span data-stu-id="ddb96-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="ddb96-126">Dynamics 365 ガイドサブスクリプション</span><span class="sxs-lookup"><span data-stu-id="ddb96-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="ddb96-127">Microsoft Dataverse 定型文 (含まれています)</span><span class="sxs-lookup"><span data-stu-id="ddb96-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="ddb96-128">Power Apps (付属)</span><span class="sxs-lookup"><span data-stu-id="ddb96-128">Power Apps (included)</span></span>
- <span data-ttu-id="ddb96-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="ddb96-129">Power BI Desktop</span></span>
- <span data-ttu-id="ddb96-130">ネットワーク接続</span><span class="sxs-lookup"><span data-stu-id="ddb96-130">Network Connectivity</span></span>

![Corp 接続ネットワーク図](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a><span data-ttu-id="ddb96-132">配置の段階</span><span class="sxs-lookup"><span data-stu-id="ddb96-132">Stages of Deployment</span></span>
### <a name="prepare"></a><span data-ttu-id="ddb96-133">準備</span><span class="sxs-lookup"><span data-stu-id="ddb96-133">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="ddb96-134">HoloLens 2 デバイスのインフラストラクチャの基本について説明します。</span><span class="sxs-lookup"><span data-stu-id="ddb96-134">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="ddb96-135">Azure AD の詳細については、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddb96-135">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="ddb96-136">Id 管理と Azure AD アカウントを最適に設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ddb96-136">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="ddb96-137">まだ準備ができていない場合は、MDM の詳細を確認し、Intune をセットアップしてください。</span><span class="sxs-lookup"><span data-stu-id="ddb96-137">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="ddb96-138">証明書ベースの Wi-fi について理解を深めます。</span><span class="sxs-lookup"><span data-stu-id="ddb96-138">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="ddb96-139">プロキシについて理解を深めます。</span><span class="sxs-lookup"><span data-stu-id="ddb96-139">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="ddb96-140">基幹業務アプリを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ddb96-140">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="ddb96-141">組織にガイドを使用する方法の詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddb96-141">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="ddb96-142">構成</span><span class="sxs-lookup"><span data-stu-id="ddb96-142">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="ddb96-143">ユーザーとグループを作成する方法。</span><span class="sxs-lookup"><span data-stu-id="ddb96-143">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="ddb96-144">自動登録をセットアップする方法。</span><span class="sxs-lookup"><span data-stu-id="ddb96-144">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="ddb96-145">企業 Wi-Fi 接続用の Wi-Fi 証明書とプロファイルを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ddb96-145">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="ddb96-146">基幹業務 (LOB) アプリパッケージをアップロードして割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ddb96-146">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="ddb96-147">Dynamics 365 ガイドをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="ddb96-147">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="ddb96-148">キオスクモードを構成する方法 (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="ddb96-148">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="ddb96-149">WDAC を構成する方法 (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="ddb96-149">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="ddb96-150">配置</span><span class="sxs-lookup"><span data-stu-id="ddb96-150">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="ddb96-151">デバイスと MDM を使用して登録を検証します。</span><span class="sxs-lookup"><span data-stu-id="ddb96-151">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="ddb96-152">Wi-Fi 証明書を検証します。</span><span class="sxs-lookup"><span data-stu-id="ddb96-152">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="ddb96-153">LOB アプリのインストールを検証します。</span><span class="sxs-lookup"><span data-stu-id="ddb96-153">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="ddb96-154">作成と運用を通じてガイドを検証します。</span><span class="sxs-lookup"><span data-stu-id="ddb96-154">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="ddb96-155">管理</span><span class="sxs-lookup"><span data-stu-id="ddb96-155">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="ddb96-156">HoloLens 2 を更新します。</span><span class="sxs-lookup"><span data-stu-id="ddb96-156">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="ddb96-157">ガイドを更新する方法 (ストアアプリ)</span><span class="sxs-lookup"><span data-stu-id="ddb96-157">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="ddb96-158">LOB アプリを更新する方法。</span><span class="sxs-lookup"><span data-stu-id="ddb96-158">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="ddb96-159">開発計画。</span><span class="sxs-lookup"><span data-stu-id="ddb96-159">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="ddb96-160">サポートプランを作成しています。</span><span class="sxs-lookup"><span data-stu-id="ddb96-160">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="ddb96-161">デバイス管理オプション。</span><span class="sxs-lookup"><span data-stu-id="ddb96-161">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="ddb96-162">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ddb96-162">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="ddb96-163">企業に接続された展開-準備</span><span class="sxs-lookup"><span data-stu-id="ddb96-163">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
