---
title: リモートアシスタンスを使用したクラウド接続 HoloLens 2 の概要
description: Dynamics 365 Remote Assist を使用して、クラウドに接続されたネットワーク経由で HoloLens 2 デバイスを登録する方法について説明します。
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
ms.openlocfilehash: 26fd2def8ce1fa8f960ab930e209c74fb37e2e0a
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639762"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="1d80c-104">展開ガイド–リモートアシスタンスを使用したクラウド接続 HoloLens 2-概要</span><span class="sxs-lookup"><span data-stu-id="1d80c-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="1d80c-105">このガイドは、IT プロフェッショナルが、リモートアシスタンスを使用する Microsoft HoloLens 2 つのデバイスを組織に計画して展開するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1d80c-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="1d80c-106">これは、さまざまな HoloLens 2 のユースケースにわたる組織への概念実証展開のモデルとして機能します。</span><span class="sxs-lookup"><span data-stu-id="1d80c-106">This will serve as a model for proof-of-concept deployments to your organization across various HoloLens 2 use cases.</span></span> <span data-ttu-id="1d80c-107">セットアップは、 [シナリオ A: クラウド接続デバイスへのデプロイ](common-scenarios.md#scenario-a)に似ています。</span><span class="sxs-lookup"><span data-stu-id="1d80c-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](common-scenarios.md#scenario-a).</span></span> 

<span data-ttu-id="1d80c-108">このガイドでは、デバイスをデバイス管理に登録する方法、必要に応じてライセンスを適用する方法、およびエンドユーザーがデバイスのセットアップ時にすぐにリモートアシスタンスを使用できることを検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d80c-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="1d80c-109">これを行うには、セットアップと実行に必要なインフラストラクチャの重要な部分について説明します。 HoloLens 2 による大規模なデプロイを実現します。</span><span class="sxs-lookup"><span data-stu-id="1d80c-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="1d80c-110">このガイドでは、その他のデバイスの制限や構成は適用されませんが、これらのオプションについては、完了後に調査することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1d80c-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1d80c-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="1d80c-111">Prerequisites</span></span>

<span data-ttu-id="1d80c-112">HoloLens 2 を展開するには、次のインフラストラクチャが配置されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d80c-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="1d80c-113">Azure と Intune を設定していない場合は、次のガイドに記載されています。</span><span class="sxs-lookup"><span data-stu-id="1d80c-113">If not, setting up Azure and Intune is included in this guide:</span></span>

<span data-ttu-id="1d80c-114">これは、「 [シナリオ a: クラウド接続デバイスへの展開](/hololens/common-scenarios#scenario-a)」と同様のセットアップです。これは、多くの概念実証展開に適しています。これには、次のようなものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1d80c-114">This is a setup similar to [Scenario A: Deploy to cloud connect devices](/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="1d80c-115">Wi-Fi ネットワークは、通常、インターネットおよびクラウドサービスに対して完全に開いています。</span><span class="sxs-lookup"><span data-stu-id="1d80c-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="1d80c-116">MDM の自動登録を使用した Azure AD 参加-MDM 管理 (Intune)</span><span class="sxs-lookup"><span data-stu-id="1d80c-116">Azure AD Join with MDM Auto Enrollment—MDM-managed (Intune)</span></span>
- <span data-ttu-id="1d80c-117">ユーザーが自分の会社のアカウントでサインインする (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="1d80c-117">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="1d80c-118">デバイスごとに1つまたは複数のユーザーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1d80c-118">Single or multiple users per device are supported.</span></span>

:::image type="content" alt-text="クラウド接続シナリオ" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="1d80c-120">リモートアシスタンスの詳細</span><span class="sxs-lookup"><span data-stu-id="1d80c-120">Learn about Remote Assist</span></span>

<span data-ttu-id="1d80c-121">リモートアシスタンスを使用すると、共同での保守と修復、リモート検査、知識の共有とトレーニングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1d80c-121">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="1d80c-122">さまざまな役割と場所にいるユーザーを接続することで、リモートアシスタンスを使用する技術者は Microsoft Teams のリモートコラボレーターに接続できます。</span><span class="sxs-lookup"><span data-stu-id="1d80c-122">By connecting people in different roles and locations, a technician who uses Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="1d80c-123">ビデオ、スクリーンショット、注釈を組み合わせて、同じ場所にいなくてもリアルタイムで問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="1d80c-123">They can combine video, screenshots, and annotations to solve problems in real time even when they aren't in the same location.</span></span> <span data-ttu-id="1d80c-124">リモートコラボレーターは、参照イメージ、概略図、その他の役に立つ情報を技術者の物理的な領域に挿入して、HoloLens でのヘッドアップとハンドフリーの作業中に、概略図を参照できます。</span><span class="sxs-lookup"><span data-stu-id="1d80c-124">Remote collaborators can insert reference images, schematics, and other helpful information the technician's physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="1d80c-125">リモートアシスタンスのライセンスと要件</span><span class="sxs-lookup"><span data-stu-id="1d80c-125">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="1d80c-126">Azure AD アカウント (サブスクリプションの購入とライセンスの割り当てに必要)</span><span class="sxs-lookup"><span data-stu-id="1d80c-126">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="1d80c-127">[リモートアシスタンスサブスクリプション](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (または [リモートアシスタンス試用版](/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span><span class="sxs-lookup"><span data-stu-id="1d80c-127">[Remote Assist subscription](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="1d80c-128">Dynamics 365 Remote Assist ユーザー</span><span class="sxs-lookup"><span data-stu-id="1d80c-128">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="1d80c-129">リモート支援ライセンス</span><span class="sxs-lookup"><span data-stu-id="1d80c-129">Remote Assist license</span></span>
- <span data-ttu-id="1d80c-130">ネットワーク接続</span><span class="sxs-lookup"><span data-stu-id="1d80c-130">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="1d80c-131">Microsoft Teams ユーザー</span><span class="sxs-lookup"><span data-stu-id="1d80c-131">Microsoft Teams user</span></span>

- <span data-ttu-id="1d80c-132">Microsoft Teams または[Teams フリーミアム](https://products.office.com/microsoft-teams/free)。</span><span class="sxs-lookup"><span data-stu-id="1d80c-132">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="1d80c-133">ネットワーク接続</span><span class="sxs-lookup"><span data-stu-id="1d80c-133">Network connectivity</span></span>

<span data-ttu-id="1d80c-134">この [クロステナントシナリオ](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)を実装する予定がある場合は、情報バリアライセンスが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="1d80c-134">If you plan on implementing this [cross-tenant scenario](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="1d80c-135">情報バリアライセンスが必要かどうかを判断するには、「[ベンダーと顧客がフル Dynamics 365 Remote Assist 機能を使用する](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d80c-135">To determine if an Information Barrier License is required, see [Vendors and customers use full Dynamics 365 Remote Assist capabilities](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation).</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="1d80c-136">このガイドで行うこと:</span><span class="sxs-lookup"><span data-stu-id="1d80c-136">In this guide you will:</span></span>

<span data-ttu-id="1d80c-137">準備:</span><span class="sxs-lookup"><span data-stu-id="1d80c-137">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="1d80c-138">HoloLens 2 デバイスのインフラストラクチャに関する基本事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d80c-138">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="1d80c-139">Azure AD とセットアップの詳細について&#39;は、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d80c-139">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="1d80c-140">Id 管理と Azure AD アカウントを最適に設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d80c-140">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="1d80c-141">MDM の詳細を確認し、まだ準備ができていない場合は、Intune を使用してセットアップします。&#39;。</span><span class="sxs-lookup"><span data-stu-id="1d80c-141">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="1d80c-142">リモートアシスタンスのネットワーク要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d80c-142">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="1d80c-143">必要に応じて、組織のリソースに接続するための VPN</span><span class="sxs-lookup"><span data-stu-id="1d80c-143">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="1d80c-144">以下を構成します。</span><span class="sxs-lookup"><span data-stu-id="1d80c-144">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="1d80c-145">ユーザーとグループを作成する方法。</span><span class="sxs-lookup"><span data-stu-id="1d80c-145">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="1d80c-146">Azure AD 内で自動登録を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d80c-146">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="1d80c-147">アプリケーションライセンスを割り当てる方法。</span><span class="sxs-lookup"><span data-stu-id="1d80c-147">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="1d80c-148">展開: </span><span class="sxs-lookup"><span data-stu-id="1d80c-148">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="1d80c-149">HoloLens 2 を設定し、登録を検証します。</span><span class="sxs-lookup"><span data-stu-id="1d80c-149">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="1d80c-150">検証リモートアシスタンス通話を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1d80c-150">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="1d80c-151">保守:</span><span class="sxs-lookup"><span data-stu-id="1d80c-151">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="1d80c-152">Microsoft Store アプリを使用してリモートアシスタンスを更新する方法。</span><span class="sxs-lookup"><span data-stu-id="1d80c-152">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="1d80c-153">サポートプランを作成しています。</span><span class="sxs-lookup"><span data-stu-id="1d80c-153">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="1d80c-154">開発計画。</span><span class="sxs-lookup"><span data-stu-id="1d80c-154">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="1d80c-155">次のステップ</span><span class="sxs-lookup"><span data-stu-id="1d80c-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1d80c-156">クラウドに接続されたデプロイ-準備</span><span class="sxs-lookup"><span data-stu-id="1d80c-156">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

