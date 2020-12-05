---
title: 展開ガイド–リモートアシストによるクラウド接続の HoloLens 2-概要
description: クラウドに接続されたネットワーク経由で HoloLens デバイスを登録する
keywords: HoloLens、管理、クラウド接続、リモートアシスト、AAD、Azure AD、MDM、モバイルデバイス管理
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
ms.openlocfilehash: ba3f826360f999a72e671166af7a19d19ce9c567
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196342"
---
# <span data-ttu-id="23f1e-104">展開ガイド–リモートアシスタンスによるクラウド接続の HoloLens 2 –概要</span><span class="sxs-lookup"><span data-stu-id="23f1e-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="23f1e-105">このガイドは、IT 担当者が組織に Microsoft HoloLens 2 デバイスを計画して展開する際の全体的な目標 (Dynamics 365 リモートアシスタンスを使用するために、それらのデバイスクラウドを組織に接続することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="23f1e-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="23f1e-106">これは、さまざまな HoloLens 2 のユースケースを通じて、組織の概念実証の展開のモデルとして機能するという点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="23f1e-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="23f1e-107">このガイドでは、デバイスをデバイス管理に登録する方法、必要に応じてライセンスを適用する方法、エンドユーザーがデバイスのセットアップ時にリモートアシスタンスを直ちに使用できることを検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="23f1e-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device set up.</span></span> <span data-ttu-id="23f1e-108">これを行うには、セットアップして実行するために必要なインフラストラクチャの重要な要素を把握します。これには、HoloLens 2 を使用して展開を実現します。</span><span class="sxs-lookup"><span data-stu-id="23f1e-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

## <span data-ttu-id="23f1e-109">このガイドの内容</span><span class="sxs-lookup"><span data-stu-id="23f1e-109">In this Guide</span></span>

<span data-ttu-id="23f1e-110">このガイドには、HoloLens デバイスで組織内のリモートアシスタンスを設定するための具体的な目標があります。</span><span class="sxs-lookup"><span data-stu-id="23f1e-110">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="23f1e-111">その目標を達成するために必要な necessities について説明します。</span><span class="sxs-lookup"><span data-stu-id="23f1e-111">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="23f1e-112">この目標にフォーカスを維持するために、この展開の最適化または構成が必要な項目の削減のために、特定の準備と構成が事前に選択されます。</span><span class="sxs-lookup"><span data-stu-id="23f1e-112">In order to maintain focus on this goal certain preparations and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="23f1e-113">これらの選択肢の情報が表示され、ビジネスニーズに合わせて展開をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="23f1e-113">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="23f1e-114">これは、 [シナリオ a: クラウド接続デバイスへの展開](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)に似ています。これは、次のようなさまざまな概念展開の検証に最適なオプションです。</span><span class="sxs-lookup"><span data-stu-id="23f1e-114">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments which will include:</span></span>

- <span data-ttu-id="23f1e-115">通常、インターネットとクラウドサービスへの Wi-Fi ネットワークは完全に開かれます。</span><span class="sxs-lookup"><span data-stu-id="23f1e-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="23f1e-116">MDM の自動登録による Azure AD の参加--MDM (Intune) 管理</span><span class="sxs-lookup"><span data-stu-id="23f1e-116">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="23f1e-117">ユーザーは独自の企業アカウント (AAD) でサインインする</span><span class="sxs-lookup"><span data-stu-id="23f1e-117">Users sign in with their own corporate account (AAD)</span></span>
  - <span data-ttu-id="23f1e-118">デバイスごとに1つまたは複数のユーザーがサポートされる</span><span class="sxs-lookup"><span data-stu-id="23f1e-118">Single or multiple users per device supported</span></span>
- <span data-ttu-id="23f1e-119">特定の用途に応じてさまざまなレベルのデバイスロックダウン構成が適用されます。これは、完全に開いて単一のアプリキオスクにする場合です。</span><span class="sxs-lookup"><span data-stu-id="23f1e-119">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>

![クラウド接続のシナリオ](./images/cloud-connected-deployment-chart.png)

<span data-ttu-id="23f1e-121">このガイドでは、追加のデバイス制限や構成は適用されませんが、これらのオプションをご確認いただくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="23f1e-121">No additional device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <span data-ttu-id="23f1e-122">リモートアシストについて</span><span class="sxs-lookup"><span data-stu-id="23f1e-122">Learn about Remote Assist</span></span>

<span data-ttu-id="23f1e-123">リモートアシスタンスでは、共同作業と修理、リモート検査、知識共有、トレーニングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="23f1e-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="23f1e-124">さまざまな役割や場所のユーザーを接続することによって、リモートアシスタンスを使用する技術者は、Microsoft Teams のリモートコラボレーターとつながることができます。</span><span class="sxs-lookup"><span data-stu-id="23f1e-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="23f1e-125">ビデオ、スクリーンショット、注釈を組み合わせて、同じ場所に&#39;していないときでも、リアルタイムで問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="23f1e-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="23f1e-126">リモートのコラボレーターは、技術者&#39;s の物理スペースを挿入して、お客様が登録を行っているときに、または HoloLens で作業しているときに、その他の役に立つ情報を挿入できます。</span><span class="sxs-lookup"><span data-stu-id="23f1e-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <span data-ttu-id="23f1e-127">このガイドでは、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="23f1e-127">In this guide you will:</span></span>

<span data-ttu-id="23f1e-128">備える</span><span class="sxs-lookup"><span data-stu-id="23f1e-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="23f1e-129">HoloLens 2 デバイスのインフラストラクチャの基礎について説明します。</span><span class="sxs-lookup"><span data-stu-id="23f1e-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="23f1e-130">AAD について詳しくは、「所有している&#39;」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23f1e-130">Learn more about AAD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="23f1e-131">Id 管理と AAD アカウントを最適に設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="23f1e-131">Learn about Identity management and how to best set up AAD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="23f1e-132">MDM の詳細については、「準備が完了しているかどうかを&#39;する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23f1e-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="23f1e-133">リモートアシストのネットワーク要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="23f1e-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="23f1e-134">必要に応じて: 組織のリソースに接続する VPN</span><span class="sxs-lookup"><span data-stu-id="23f1e-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="23f1e-135">設定</span><span class="sxs-lookup"><span data-stu-id="23f1e-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="23f1e-136">ユーザーとグループを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="23f1e-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="23f1e-137">AAD で自動登録を設定する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="23f1e-137">How to set up Auto-enrollment within AAD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="23f1e-138">アプリケーションライセンスを割り当てる方法。</span><span class="sxs-lookup"><span data-stu-id="23f1e-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="23f1e-139">Deploy</span><span class="sxs-lookup"><span data-stu-id="23f1e-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="23f1e-140">HoloLens 2 をセットアップし、登録を確認します。</span><span class="sxs-lookup"><span data-stu-id="23f1e-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="23f1e-141">リモートアシスタンス通話を発信できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="23f1e-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="23f1e-142">維持</span><span class="sxs-lookup"><span data-stu-id="23f1e-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="23f1e-143">Microsoft Store アプリを使ってリモートアシスタンスを更新する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="23f1e-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="23f1e-144">サポート計画を作成します。</span><span class="sxs-lookup"><span data-stu-id="23f1e-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="23f1e-145">開発計画。</span><span class="sxs-lookup"><span data-stu-id="23f1e-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <span data-ttu-id="23f1e-146">次のステップ</span><span class="sxs-lookup"><span data-stu-id="23f1e-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="23f1e-147">クラウド接続の展開-準備</span><span class="sxs-lookup"><span data-stu-id="23f1e-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

