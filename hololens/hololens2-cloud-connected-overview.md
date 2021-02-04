---
title: リモート アシスト付きのクラウド接続 HoloLens 2 の概要
description: Dynamics 365 リモート アシストを使用して、クラウド接続ネットワーク上で HoloLens 2 デバイスを登録する方法について学習します。
keywords: HoloLens, 管理, クラウド接続, リモート アシスト, AAD, Azure AD, MDM, モバイル デバイス管理
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
ms.openlocfilehash: 69b31657a7efaebd5b25b742023dc8767f9c5038
ms.sourcegitcommit: 39424078a75feaf6a1e9b0547cb7d5de9847faf3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312638"
---
# <span data-ttu-id="c42b3-104">展開ガイド - HoloLens 2 (Remote Assist 付き) のクラウド接続 – 概要</span><span class="sxs-lookup"><span data-stu-id="c42b3-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="c42b3-105">このガイドは、Dynamics 365 リモート アシストを使用してこれらのデバイスを組織に接続する全体的な目標を達成し、IT 担当者が Microsoft HoloLens 2 デバイスを計画して組織に展開する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c42b3-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="c42b3-106">これは、さまざまな HoloLens 2 の使用事例にわたって組織に概念実証を展開するモデルとして機能します。</span><span class="sxs-lookup"><span data-stu-id="c42b3-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="c42b3-107">このガイドでは、デバイスをデバイス管理に登録し、必要に応じてライセンスを適用し、エンド ユーザーがデバイスのセットアップ時にリモート アシストをすぐに使用できるのを検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c42b3-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="c42b3-108">これを行うには、HoloLens 2 を使用して大規模な展開を実現するために、セットアップと実行に必要な重要なインフラストラクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c42b3-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

![クラウドに接続されたバナー](./images/cloud-connected-hololens-large.png)

## <span data-ttu-id="c42b3-110">このガイドのページ</span><span class="sxs-lookup"><span data-stu-id="c42b3-110">In this Guide</span></span>

<span data-ttu-id="c42b3-111">このガイドには、組織内で HoloLens デバイスにリモート アシストをセットアップする具体的な目標があります。</span><span class="sxs-lookup"><span data-stu-id="c42b3-111">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="c42b3-112">その目標を達成するために必要な情報を扱います。</span><span class="sxs-lookup"><span data-stu-id="c42b3-112">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="c42b3-113">この目標に集中するために、この展開を最適化したり、構成に必要な項目を減らしたりするために、特定の準備と構成を事前に選択します。</span><span class="sxs-lookup"><span data-stu-id="c42b3-113">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="c42b3-114">これらの選択肢が通知され、ビジネス ニーズに基づいて展開をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="c42b3-114">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="c42b3-115">これは、シナリオ [A:](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)クラウド接続デバイスへの展開に似た設定です。これは、概念実証の多くの展開に最適なオプションです。これには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c42b3-115">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="c42b3-116">Wi-Fiネットワークは、通常、インターネットサービスとクラウド サービスに完全に開いている</span><span class="sxs-lookup"><span data-stu-id="c42b3-116">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="c42b3-117">Azure AD MDM 自動登録を使用した参加 - MDM (Intune) 管理</span><span class="sxs-lookup"><span data-stu-id="c42b3-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="c42b3-118">ユーザーが自分の会社のアカウントでサインインする (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="c42b3-118">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="c42b3-119">サポートされるデバイスごとに 1 人または複数のユーザー</span><span class="sxs-lookup"><span data-stu-id="c42b3-119">Single or multiple users per device supported</span></span>
- <span data-ttu-id="c42b3-120">さまざまなレベルのデバイス ロックダウン構成が、完全に開いているアプリからシングル アプリ キオスクまで、特定の使用例に基づいて適用されます。</span><span class="sxs-lookup"><span data-stu-id="c42b3-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>

![クラウド接続シナリオ](./images/cloud-connected-guide-diagram.png)

<span data-ttu-id="c42b3-122">このガイドでは、他のデバイスの制限や構成は適用されませんが、終了後にこれらのオプションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c42b3-122">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <span data-ttu-id="c42b3-123">リモート アシストについて</span><span class="sxs-lookup"><span data-stu-id="c42b3-123">Learn about Remote Assist</span></span>

<span data-ttu-id="c42b3-124">リモート アシストを使用すると、共同作業による保守と修復、リモート検査、知識の共有とトレーニングが可能になります。</span><span class="sxs-lookup"><span data-stu-id="c42b3-124">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="c42b3-125">リモート アシストを使用して技術者と異なる役割や場所のユーザーを接続すると、Microsoft Teams のリモート共同作業者と接続できます。</span><span class="sxs-lookup"><span data-stu-id="c42b3-125">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="c42b3-126">ビデオ、スクリーンショット、注釈を組み合わせて、問題が同じ場所になくても&#39;をリアルタイムで解決できます。</span><span class="sxs-lookup"><span data-stu-id="c42b3-126">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="c42b3-127">リモート共同作業者は、HoloLens でヘッドアップとハンズフリーの作業を行っている間に、技術者&#39;の物理空間に参照イメージ、図版、その他の有用な情報を挿入できます。</span><span class="sxs-lookup"><span data-stu-id="c42b3-127">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <span data-ttu-id="c42b3-128">このガイドでは、次の方法を行います。</span><span class="sxs-lookup"><span data-stu-id="c42b3-128">In this guide you will:</span></span>

<span data-ttu-id="c42b3-129">準備:</span><span class="sxs-lookup"><span data-stu-id="c42b3-129">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="c42b3-130">HoloLens 2 デバイスのインフラストラクチャの基本について学習します。</span><span class="sxs-lookup"><span data-stu-id="c42b3-130">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="c42b3-131">Azure ADについてAD、必要ない場合はセットアップ&#39;確認してください。</span><span class="sxs-lookup"><span data-stu-id="c42b3-131">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="c42b3-132">ID 管理と、Azure アカウントを最適にセットアップする方法ADします。</span><span class="sxs-lookup"><span data-stu-id="c42b3-132">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="c42b3-133">MDM について詳しく知り、まだ準備ができていない場合は Intune&#39;セットアップしてください。</span><span class="sxs-lookup"><span data-stu-id="c42b3-133">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="c42b3-134">リモート アシストのネットワーク要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="c42b3-134">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="c42b3-135">オプション: 組織のリソースに接続するための VPN</span><span class="sxs-lookup"><span data-stu-id="c42b3-135">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="c42b3-136">次の構成を行います。</span><span class="sxs-lookup"><span data-stu-id="c42b3-136">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="c42b3-137">ユーザーとグループを作成する方法。</span><span class="sxs-lookup"><span data-stu-id="c42b3-137">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="c42b3-138">Azure AD 内で自動登録をセットアップする方法。</span><span class="sxs-lookup"><span data-stu-id="c42b3-138">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="c42b3-139">アプリケーション ライセンスを割り当てる方法。</span><span class="sxs-lookup"><span data-stu-id="c42b3-139">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="c42b3-140">展開:</span><span class="sxs-lookup"><span data-stu-id="c42b3-140">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="c42b3-141">HoloLens 2 をセットアップし、登録を検証します。</span><span class="sxs-lookup"><span data-stu-id="c42b3-141">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="c42b3-142">リモート アシスト呼び出しを行う可能性を検証します。</span><span class="sxs-lookup"><span data-stu-id="c42b3-142">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="c42b3-143">次の保守を行います。</span><span class="sxs-lookup"><span data-stu-id="c42b3-143">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="c42b3-144">Microsoft Store アプリを使ってリモート アシストを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c42b3-144">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="c42b3-145">サポート計画の作成。</span><span class="sxs-lookup"><span data-stu-id="c42b3-145">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="c42b3-146">開発計画。</span><span class="sxs-lookup"><span data-stu-id="c42b3-146">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <span data-ttu-id="c42b3-147">次の手順</span><span class="sxs-lookup"><span data-stu-id="c42b3-147">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c42b3-148">クラウド接続展開 - 準備</span><span class="sxs-lookup"><span data-stu-id="c42b3-148">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

