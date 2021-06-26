---
title: リモートアシスタンスを使用したクラウド接続型 HoloLens 2 の概要
description: Dynamics 365 Remote Assist を使用して、クラウドに接続されたネットワーク上に HoloLens 2 デバイスを登録する方法について説明します。
keywords: HoloLens、管理、クラウド接続、リモートアシスタンス、AAD、Azure AD、MDM、モバイルデバイス管理
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: a44247b4afea747e4b75c974fcae344380909989
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923535"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="597c7-104">展開ガイド–リモートアシスタンスを使用したクラウド接続型 HoloLens 2 –概要</span><span class="sxs-lookup"><span data-stu-id="597c7-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="597c7-105">このガイドは、IT プロフェッショナルが、リモートアシスタンスを使用する Microsoft HoloLens 2 デバイスを組織に計画し、展開するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="597c7-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="597c7-106">これは、さまざまな HoloLens 2 ユースケースにわたる組織への概念実証展開のモデルとして機能します。</span><span class="sxs-lookup"><span data-stu-id="597c7-106">This will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span> <span data-ttu-id="597c7-107">セットアップは、 [シナリオ A: クラウド接続デバイスへのデプロイ](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)に似ています。</span><span class="sxs-lookup"><span data-stu-id="597c7-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span></span> 

<span data-ttu-id="597c7-108">このガイドでは、デバイスをデバイス管理に登録する方法、必要に応じてライセンスを適用する方法、およびエンドユーザーがデバイスのセットアップ時にすぐにリモートアシスタンスを使用できることを検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="597c7-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="597c7-109">これを行うには、セットアップと実行に必要なインフラストラクチャの重要な部分について説明します。 HoloLens 2 を使用した大規模なデプロイを実現します。</span><span class="sxs-lookup"><span data-stu-id="597c7-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="597c7-110">このガイドでは、その他のデバイスの制限や構成は適用されませんが、これらのオプションについては、完了後に調査することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="597c7-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="597c7-111">[前提条件]</span><span class="sxs-lookup"><span data-stu-id="597c7-111">Prerequisites</span></span>

<span data-ttu-id="597c7-112">HoloLens 2 を展開するには、次のインフラストラクチャが適切に配置されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="597c7-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="597c7-113">Azure と Intune を設定していない場合は、次のガイドに記載されています。</span><span class="sxs-lookup"><span data-stu-id="597c7-113">If not, setting up Azure and Intune is included in this guide:</span></span>

- <span data-ttu-id="597c7-114">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="597c7-114">Wi-Fi</span></span>
    - <span data-ttu-id="597c7-115">ネットワークは通常、インターネットおよびクラウドサービスで開かれています。</span><span class="sxs-lookup"><span data-stu-id="597c7-115">Networks are typically open to the Internet and Cloud services</span></span>
- <span data-ttu-id="597c7-116">Azure Active Directory (Azure AD) MDM 自動登録を使用した参加 ([Azure AD P1 サブスクリプション](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) が必要)</span><span class="sxs-lookup"><span data-stu-id="597c7-116">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="597c7-117">MDM (Intune) で管理</span><span class="sxs-lookup"><span data-stu-id="597c7-117">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="597c7-118">MDM を使用して1つ以上のアプリケーションがデプロイされています。</span><span class="sxs-lookup"><span data-stu-id="597c7-118">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="597c7-119">ユーザーが自分の会社のアカウントでサインインする (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="597c7-119">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="597c7-120">デバイスごとに1つまたは複数のユーザーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="597c7-120">Single or multiple users per device is supported.</span></span>

:::image type="content" alt-text="クラウド接続シナリオ" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="597c7-122">リモートアシスタンスの詳細</span><span class="sxs-lookup"><span data-stu-id="597c7-122">Learn about Remote Assist</span></span>

<span data-ttu-id="597c7-123">リモートアシスタンスを使用すると、共同での保守と修復、リモート検査、知識の共有とトレーニングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="597c7-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="597c7-124">さまざまな役割と場所のメンバーを接続することで、リモートアシスタンスを使用する技術者は、Microsoft Teams のリモートコラボレーターに接続できます。</span><span class="sxs-lookup"><span data-stu-id="597c7-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="597c7-125">ビデオ、スクリーンショット、注釈を組み合わせることにより、同じ場所に t&#39;いなくても、リアルタイムで問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="597c7-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="597c7-126">リモートコラボレーターは参照イメージ、概略図、およびその他の役に立つ情報を挿入できます。技術者は、&#39;、HoloLens でのヘッドアップとハンドフリーの作業中に、概略図を参照できます。</span><span class="sxs-lookup"><span data-stu-id="597c7-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="597c7-127">リモートアシスタンスのライセンスと要件</span><span class="sxs-lookup"><span data-stu-id="597c7-127">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="597c7-128">Azure AD アカウント (サブスクリプションの購入とライセンスの割り当てに必要)</span><span class="sxs-lookup"><span data-stu-id="597c7-128">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="597c7-129">[リモートアシスタンスサブスクリプション](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (または [リモートアシスタンス試用版](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span><span class="sxs-lookup"><span data-stu-id="597c7-129">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="597c7-130">Dynamics 365 リモートアシスタンスユーザー</span><span class="sxs-lookup"><span data-stu-id="597c7-130">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="597c7-131">リモート支援ライセンス</span><span class="sxs-lookup"><span data-stu-id="597c7-131">Remote Assist license</span></span>
- <span data-ttu-id="597c7-132">ネットワーク接続</span><span class="sxs-lookup"><span data-stu-id="597c7-132">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="597c7-133">Microsoft Teams ユーザー</span><span class="sxs-lookup"><span data-stu-id="597c7-133">Microsoft Teams user</span></span>

- <span data-ttu-id="597c7-134">Microsoft Teams または [Teams フリーミアム](https://products.office.com/microsoft-teams/free)。</span><span class="sxs-lookup"><span data-stu-id="597c7-134">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="597c7-135">ネットワーク接続</span><span class="sxs-lookup"><span data-stu-id="597c7-135">Network connectivity</span></span>

<span data-ttu-id="597c7-136">この [クロステナントシナリオ](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)を実装する予定がある場合は、情報バリアライセンスが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="597c7-136">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="597c7-137">情報バリアライセンスが必要かどうかを判断するには、 [この記事](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="597c7-137">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="597c7-138">このガイドで行うこと:</span><span class="sxs-lookup"><span data-stu-id="597c7-138">In this guide you will:</span></span>

<span data-ttu-id="597c7-139">準備:</span><span class="sxs-lookup"><span data-stu-id="597c7-139">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="597c7-140">HoloLens 2 デバイスのインフラストラクチャの基本について説明します。</span><span class="sxs-lookup"><span data-stu-id="597c7-140">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="597c7-141">Azure AD とセットアップの詳細について&#39;は、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="597c7-141">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="597c7-142">Id 管理と Azure AD アカウントを最適に設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="597c7-142">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="597c7-143">MDM の詳細を確認し、まだ準備ができていない場合は、Intune を使用してセットアップします。&#39;。</span><span class="sxs-lookup"><span data-stu-id="597c7-143">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="597c7-144">リモートアシスタンスのネットワーク要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="597c7-144">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="597c7-145">必要に応じて、組織のリソースに接続するための VPN</span><span class="sxs-lookup"><span data-stu-id="597c7-145">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="597c7-146">以下を構成します。</span><span class="sxs-lookup"><span data-stu-id="597c7-146">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="597c7-147">ユーザーとグループを作成する方法。</span><span class="sxs-lookup"><span data-stu-id="597c7-147">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="597c7-148">Azure AD 内で自動登録を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="597c7-148">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="597c7-149">アプリケーションライセンスを割り当てる方法。</span><span class="sxs-lookup"><span data-stu-id="597c7-149">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="597c7-150">展開: </span><span class="sxs-lookup"><span data-stu-id="597c7-150">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="597c7-151">HoloLens 2 をセットアップし、登録を検証します。</span><span class="sxs-lookup"><span data-stu-id="597c7-151">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="597c7-152">検証リモートアシスタンス通話を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="597c7-152">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="597c7-153">保守:</span><span class="sxs-lookup"><span data-stu-id="597c7-153">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="597c7-154">Microsoft Store アプリを使用してリモートアシスタンスを更新する方法。</span><span class="sxs-lookup"><span data-stu-id="597c7-154">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="597c7-155">サポートプランを作成しています。</span><span class="sxs-lookup"><span data-stu-id="597c7-155">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="597c7-156">開発計画。</span><span class="sxs-lookup"><span data-stu-id="597c7-156">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="597c7-157">次のステップ</span><span class="sxs-lookup"><span data-stu-id="597c7-157">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="597c7-158">クラウドに接続されたデプロイ-準備</span><span class="sxs-lookup"><span data-stu-id="597c7-158">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

