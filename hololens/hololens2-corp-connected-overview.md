---
title: 展開ガイド – Dynamics 365 ガイドを使用した企業接続 HoloLens 2 - 概要
description: 企業の接続ネットワーク上で Dynamics 365 ガイドを使用して HoloLens 2 デバイスを登録する方法について学習します。
keywords: HoloLens、管理、企業接続、Dynamics 365 ガイド、AAD、Azure AD、MDM、モバイル デバイス管理
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
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448585"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="8ebcd-104">展開ガイド - Dynamics 365 ガイドを使用した企業接続 HoloLens 2 - 概要</span><span class="sxs-lookup"><span data-stu-id="8ebcd-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="8ebcd-105">このガイドは、IT 担当者が組織に Dynamics 365 ガイド (ガイド) を使用して Microsoft HoloLens 2 デバイスを計画および展開するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="8ebcd-106">このガイドは、パイロットおよび実稼働環境に最適で、シナリオ [B: 組織](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) のネットワーク ガイド内での展開に似ています。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="8ebcd-107">概念実証をテストした後、このガイドを使用して、HoloLens を組織に統合します。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="8ebcd-108">このガイドでは、デバイスを既存のデバイス管理に登録し、必要に応じてライセンスを適用し、デバイスのセットアップ後にエンドユーザーが Dynamics 365 Guide を操作できるだけでなく、カスタム ラインのビジネス アプリを使用できるのか検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="8ebcd-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="8ebcd-109">Prerequisites</span></span>

<span data-ttu-id="8ebcd-110">次のインフラストラクチャが既に配置されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="8ebcd-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="8ebcd-111">Wi-Fi</span></span>
    - <span data-ttu-id="8ebcd-112">内部リソースにアクセスし、インターネットまたはクラウド サービスへのアクセスが制限された内部企業ネットワーク</span><span class="sxs-lookup"><span data-stu-id="8ebcd-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="8ebcd-113">デバイス ベースの証明書認証。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="8ebcd-114">Azure Active Directory (Azure AD) MDM 自動登録に参加する[(Azure AD P1 サブスクリプションが](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) 必要)</span><span class="sxs-lookup"><span data-stu-id="8ebcd-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="8ebcd-115">MDM (Intune) マネージ</span><span class="sxs-lookup"><span data-stu-id="8ebcd-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="8ebcd-116">1 つ以上のアプリケーションが MDM 経由で展開されます。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="8ebcd-117">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="8ebcd-117">Network</span></span> 
    - <span data-ttu-id="8ebcd-118">証明書 (SCEP または PKCS)</span><span class="sxs-lookup"><span data-stu-id="8ebcd-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="8ebcd-119">プロキシの構成</span><span class="sxs-lookup"><span data-stu-id="8ebcd-119">Proxy configuration</span></span>
- <span data-ttu-id="8ebcd-120">ユーザーが自分の企業アカウントでサインインする (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="8ebcd-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="8ebcd-121">デバイスごとに 1 人または複数のユーザーがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="8ebcd-122">特定の使用例に基づいて適用されるデバイス ロックダウン構成のレベルは、完全に開いたアプリキオスクから単一アプリ キオスクまでさまざまです。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## [<a name="guides-licensing-and-requirements"></a><span data-ttu-id="8ebcd-123">ガイド ライセンスと要件</span><span class="sxs-lookup"><span data-stu-id="8ebcd-123">Guides Licensing and Requirements</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- <span data-ttu-id="8ebcd-124">Azure AD アカウント</span><span class="sxs-lookup"><span data-stu-id="8ebcd-124">Azure AD account</span></span>
- <span data-ttu-id="8ebcd-125">Dynamics 365 アプリケーション PC と HoloLens のガイド</span><span class="sxs-lookup"><span data-stu-id="8ebcd-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="8ebcd-126">Dynamics 365 Guides サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="8ebcd-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="8ebcd-127">Microsoft Dataverse (付属)</span><span class="sxs-lookup"><span data-stu-id="8ebcd-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="8ebcd-128">Power Apps (含まれる)</span><span class="sxs-lookup"><span data-stu-id="8ebcd-128">Power Apps (included)</span></span>
- <span data-ttu-id="8ebcd-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="8ebcd-129">Power BI Desktop</span></span>
- <span data-ttu-id="8ebcd-130">ネットワーク接続</span><span class="sxs-lookup"><span data-stu-id="8ebcd-130">Network Connectivity</span></span>

![Corp 接続ネットワーク図](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a><span data-ttu-id="8ebcd-132">展開のステージ</span><span class="sxs-lookup"><span data-stu-id="8ebcd-132">Stages of Deployment</span></span>
### <a name="prepare"></a><span data-ttu-id="8ebcd-133">準備</span><span class="sxs-lookup"><span data-stu-id="8ebcd-133">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="8ebcd-134">HoloLens 2 デバイスのインフラストラクチャの必需品について学ぶ。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-134">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="8ebcd-135">Azure ADの詳細とセットアップについて説明します。必要な場合は、その設定を行います。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-135">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="8ebcd-136">Id 管理と、Azure アカウントを最適にセットアップする方法ADします。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-136">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="8ebcd-137">MDM について詳しく知り、Intune でセットアップする準備ができていない場合は、このページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-137">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="8ebcd-138">証明書ベースの Wi-Fi について理解する。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-138">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="8ebcd-139">プロキシに慣れ親しむ。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-139">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="8ebcd-140">Line of Business Apps の使い方を理解します。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-140">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="8ebcd-141">組織でガイドを使用する方法について詳しくは、ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-141">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="8ebcd-142">構成</span><span class="sxs-lookup"><span data-stu-id="8ebcd-142">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="8ebcd-143">ユーザーとグループを作成する方法。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-143">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="8ebcd-144">自動登録を設定する方法。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-144">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="8ebcd-145">企業の接続Wi-Fiの証明書とプロファイルをWi-Fiする方法。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-145">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="8ebcd-146">ビジネス行 (LOB) アプリ パッケージのアップロードと割り当て。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-146">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="8ebcd-147">Dynamics 365 ガイドのセットアップ。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-147">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="8ebcd-148">キオスク モードを構成する方法 (オプション)。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-148">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="8ebcd-149">WDAC を構成する方法 (オプション)。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-149">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="8ebcd-150">展開</span><span class="sxs-lookup"><span data-stu-id="8ebcd-150">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="8ebcd-151">デバイスと MDM を使用して登録を検証します。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-151">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="8ebcd-152">証明書Wi-Fi検証します。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-152">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="8ebcd-153">LOB アプリのインストールを検証します。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-153">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="8ebcd-154">作成と操作を通じてガイドを検証します。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-154">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="8ebcd-155">保守</span><span class="sxs-lookup"><span data-stu-id="8ebcd-155">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="8ebcd-156">HoloLens 2 を更新します。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-156">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="8ebcd-157">ガイド (ストア アプリ) を更新する方法。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-157">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="8ebcd-158">LOB アプリを更新する方法。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-158">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="8ebcd-159">開発計画。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-159">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="8ebcd-160">サポート プランを作成する。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-160">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="8ebcd-161">デバイス管理オプション。</span><span class="sxs-lookup"><span data-stu-id="8ebcd-161">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="8ebcd-162">次の手順</span><span class="sxs-lookup"><span data-stu-id="8ebcd-162">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="8ebcd-163">企業接続展開 - 準備</span><span class="sxs-lookup"><span data-stu-id="8ebcd-163">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
