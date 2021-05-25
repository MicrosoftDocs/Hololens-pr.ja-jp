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
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397653"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="8d13b-104">展開ガイド–リモートアシスタンスを使用したクラウド接続型 HoloLens 2 –概要</span><span class="sxs-lookup"><span data-stu-id="8d13b-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="8d13b-105">このガイドは、IT プロフェッショナルが Microsoft HoloLens 2 デバイスを組織に接続する際の全体的な目標を計画し、組織に展開するのに役立ちます。これらのデバイスは、Dynamics 365 リモートアシスタンスを使用する準備が整っている組織に接続されています。</span><span class="sxs-lookup"><span data-stu-id="8d13b-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="8d13b-106">これは、さまざまな HoloLens 2 ユースケースで組織に対する概念実証展開のモデルとして機能することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8d13b-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="8d13b-107">このガイドでは、デバイスをデバイス管理に登録する方法、必要に応じてライセンスを適用する方法、およびエンドユーザーがデバイスのセットアップ時にリモートアシスタンスをすぐに使用できることを検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d13b-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="8d13b-108">これを行うには、設定と実行に必要なインフラストラクチャの重要な部分について説明します。これは、HoloLens 2 を使用した大規模なデプロイを実現するために必要です。</span><span class="sxs-lookup"><span data-stu-id="8d13b-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

<span data-ttu-id="8d13b-109">[![クラウド接続シナリオ ](./images/deployment-guides-revised-scenario-a.png)](./images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="8d13b-109">[ ![Cloud connected scenario](./images/deployment-guides-revised-scenario-a.png) ](./images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>
## <a name="in-this-guide"></a><span data-ttu-id="8d13b-110">このガイドの内容</span><span class="sxs-lookup"><span data-stu-id="8d13b-110">In this Guide</span></span>

<span data-ttu-id="8d13b-111">このガイドには、お客様の HoloLens デバイスで組織内にリモートアシスタンスを設定するための特定の目標があります。</span><span class="sxs-lookup"><span data-stu-id="8d13b-111">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="8d13b-112">この目標を達成するために必要な virtual-machines-windows-classic-ps-sql-alwayson-availability-groups について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d13b-112">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="8d13b-113">この目標に焦点を当てるために、この展開を最適化するため、または構成する必要がある項目を減らすために、特定の準備と構成があらかじめ選択されています。</span><span class="sxs-lookup"><span data-stu-id="8d13b-113">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="8d13b-114">これらの選択が通知され、ビジネスニーズに基づいてデプロイをカスタマイズできるようになります。</span><span class="sxs-lookup"><span data-stu-id="8d13b-114">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="8d13b-115">これは、 [シナリオ a: クラウド接続デバイスへのデプロイ](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)に似ています。これは、多くの概念実証展開に適しています。これには、次のようなものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8d13b-115">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="8d13b-116">Wi-Fi ネットワークは、通常、インターネットおよびクラウドサービスに対して完全に開いています。</span><span class="sxs-lookup"><span data-stu-id="8d13b-116">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="8d13b-117">MDM の自動登録による Azure AD 参加--MDM (Intune) で管理</span><span class="sxs-lookup"><span data-stu-id="8d13b-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="8d13b-118">ユーザーが自分の会社のアカウントでサインインする (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="8d13b-118">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="8d13b-119">デバイスごとに1つまたは複数のユーザーがサポートされています</span><span class="sxs-lookup"><span data-stu-id="8d13b-119">Single or multiple users per device supported</span></span>
- <span data-ttu-id="8d13b-120">デバイス ロックダウン構成のさまざまなレベルが、フル オープンからシングル アプリ キオスクまで、特定の使用事例に基づいて適用されます</span><span class="sxs-lookup"><span data-stu-id="8d13b-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>



<span data-ttu-id="8d13b-121">このガイドでは、他のデバイスの制限や構成は適用されませんが、完了した後でこれらのオプションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8d13b-121">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <a name="learn-about-remote-assist"></a><span data-ttu-id="8d13b-122">詳細については、Remote Assist</span><span class="sxs-lookup"><span data-stu-id="8d13b-122">Learn about Remote Assist</span></span>

<span data-ttu-id="8d13b-123">Remote Assist、共同作業によるメンテナンスと修復、リモート検査、ナレッジの共有とトレーニングが可能になります。</span><span class="sxs-lookup"><span data-stu-id="8d13b-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="8d13b-124">さまざまな役割と場所のユーザーを接続することで、Remote Assistを使用して、Microsoft Teams のリモート コラボレーターと接続できます。</span><span class="sxs-lookup"><span data-stu-id="8d13b-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="8d13b-125">ビデオ、スクリーンショット、注釈を組み合わせて、問題が同じ場所になくても&#39;をリアルタイムで解決できます。</span><span class="sxs-lookup"><span data-stu-id="8d13b-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="8d13b-126">リモート コラボレーターは、HoloLens でヘッドアップとハンズフリーの作業を行っている間に、技術者&#39;の物理空間に参照画像、概略図、その他の役に立つ情報を挿入できます。</span><span class="sxs-lookup"><span data-stu-id="8d13b-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="8d13b-127">このガイドで行うこと:</span><span class="sxs-lookup"><span data-stu-id="8d13b-127">In this guide you will:</span></span>

<span data-ttu-id="8d13b-128">準備:</span><span class="sxs-lookup"><span data-stu-id="8d13b-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="8d13b-129">デバイスのインフラストラクチャの基本についてHoloLens 2します。</span><span class="sxs-lookup"><span data-stu-id="8d13b-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="8d13b-130">詳細については、Azure AD設定する必要がある場合は、&#39;してください。</span><span class="sxs-lookup"><span data-stu-id="8d13b-130">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="8d13b-131">ID 管理と、アカウントを最適に設定する方法Azure AD説明します。</span><span class="sxs-lookup"><span data-stu-id="8d13b-131">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="8d13b-132">MDM の詳細を確認し、まだ準備ができていない場合&#39;Intune で設定します。</span><span class="sxs-lookup"><span data-stu-id="8d13b-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="8d13b-133">アプリケーションのネットワーク要件についてRemote Assist。</span><span class="sxs-lookup"><span data-stu-id="8d13b-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="8d13b-134">必要に応じて、組織のリソースに接続するための VPN</span><span class="sxs-lookup"><span data-stu-id="8d13b-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="8d13b-135">以下を構成します。</span><span class="sxs-lookup"><span data-stu-id="8d13b-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="8d13b-136">ユーザーとグループを作成する方法。</span><span class="sxs-lookup"><span data-stu-id="8d13b-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="8d13b-137">データ 内で自動登録を設定するAzure AD。</span><span class="sxs-lookup"><span data-stu-id="8d13b-137">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="8d13b-138">アプリケーション ライセンスを割り当てる方法。</span><span class="sxs-lookup"><span data-stu-id="8d13b-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="8d13b-139">展開: </span><span class="sxs-lookup"><span data-stu-id="8d13b-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="8d13b-140">登録を設定しHoloLens 2を検証します。</span><span class="sxs-lookup"><span data-stu-id="8d13b-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="8d13b-141">呼び出しを行Remote Assist検証します。</span><span class="sxs-lookup"><span data-stu-id="8d13b-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="8d13b-142">保守:</span><span class="sxs-lookup"><span data-stu-id="8d13b-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="8d13b-143">アプリを使用してRemote Assistを更新Microsoft Store方法。</span><span class="sxs-lookup"><span data-stu-id="8d13b-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="8d13b-144">サポート プランを作成する。</span><span class="sxs-lookup"><span data-stu-id="8d13b-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="8d13b-145">開発計画。</span><span class="sxs-lookup"><span data-stu-id="8d13b-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="8d13b-146">次のステップ</span><span class="sxs-lookup"><span data-stu-id="8d13b-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8d13b-147">クラウドに接続されたデプロイ-準備</span><span class="sxs-lookup"><span data-stu-id="8d13b-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

