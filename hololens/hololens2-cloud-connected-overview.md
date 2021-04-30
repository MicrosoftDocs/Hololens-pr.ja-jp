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
ms.openlocfilehash: 69b31657a7efaebd5b25b742023dc8767f9c5038
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309112"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="1365c-104">展開ガイド–リモートアシスタンスを使用したクラウド接続型 HoloLens 2 –概要</span><span class="sxs-lookup"><span data-stu-id="1365c-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="1365c-105">このガイドは、IT プロフェッショナルが Microsoft HoloLens 2 デバイスを組織に接続する際の全体的な目標を計画し、組織に展開するのに役立ちます。これらのデバイスは、Dynamics 365 リモートアシスタンスを使用する準備が整っている組織に接続されています。</span><span class="sxs-lookup"><span data-stu-id="1365c-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="1365c-106">これは、さまざまな HoloLens 2 ユースケースで組織に対する概念実証展開のモデルとして機能することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1365c-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="1365c-107">このガイドでは、デバイスをデバイス管理に登録する方法、必要に応じてライセンスを適用する方法、およびエンドユーザーがデバイスのセットアップ時にリモートアシスタンスをすぐに使用できることを検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1365c-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="1365c-108">これを行うには、設定と実行に必要なインフラストラクチャの重要な部分について説明します。これは、HoloLens 2 を使用した大規模なデプロイを実現するために必要です。</span><span class="sxs-lookup"><span data-stu-id="1365c-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

![クラウドに接続されたバナー](./images/cloud-connected-hololens-large.png)

## <a name="in-this-guide"></a><span data-ttu-id="1365c-110">このガイドの内容</span><span class="sxs-lookup"><span data-stu-id="1365c-110">In this Guide</span></span>

<span data-ttu-id="1365c-111">このガイドには、お客様の HoloLens デバイスで組織内にリモートアシスタンスを設定するための特定の目標があります。</span><span class="sxs-lookup"><span data-stu-id="1365c-111">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="1365c-112">この目標を達成するために必要な virtual-machines-windows-classic-ps-sql-alwayson-availability-groups について説明します。</span><span class="sxs-lookup"><span data-stu-id="1365c-112">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="1365c-113">この目標に焦点を当てるために、この展開を最適化するため、または構成する必要がある項目を減らすために、特定の準備と構成があらかじめ選択されています。</span><span class="sxs-lookup"><span data-stu-id="1365c-113">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="1365c-114">これらの選択が通知され、ビジネスニーズに基づいてデプロイをカスタマイズできるようになります。</span><span class="sxs-lookup"><span data-stu-id="1365c-114">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="1365c-115">これは、 [シナリオ a: クラウド接続デバイスへのデプロイ](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)に似ています。これは、多くの概念実証展開に適しています。これには、次のようなものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1365c-115">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="1365c-116">Wi-Fi ネットワークは、通常、インターネットおよびクラウドサービスに対して完全に開いています。</span><span class="sxs-lookup"><span data-stu-id="1365c-116">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="1365c-117">MDM の自動登録による Azure AD 参加--MDM (Intune) で管理</span><span class="sxs-lookup"><span data-stu-id="1365c-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="1365c-118">ユーザーが自分の会社のアカウントでサインインする (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="1365c-118">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="1365c-119">デバイスごとに1つまたは複数のユーザーがサポートされています</span><span class="sxs-lookup"><span data-stu-id="1365c-119">Single or multiple users per device supported</span></span>
- <span data-ttu-id="1365c-120">さまざまなレベルのデバイスロックダウン構成は、完全にオープンからシングルアプリキオスクまで、特定のユースケースに基づいて適用されます。</span><span class="sxs-lookup"><span data-stu-id="1365c-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>

![クラウド接続シナリオ](./images/cloud-connected-guide-diagram.png)

<span data-ttu-id="1365c-122">このガイドでは、その他のデバイスの制限や構成は適用されませんが、完了後にこれらのオプションを調べることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1365c-122">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <a name="learn-about-remote-assist"></a><span data-ttu-id="1365c-123">リモートアシスタンスの詳細</span><span class="sxs-lookup"><span data-stu-id="1365c-123">Learn about Remote Assist</span></span>

<span data-ttu-id="1365c-124">リモートアシスタンスを使用すると、共同での保守と修復、リモート検査、知識の共有とトレーニングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1365c-124">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="1365c-125">さまざまな役割と場所のメンバーを接続することで、リモートアシスタンスを使用する技術者は、Microsoft Teams のリモートコラボレーターに接続できます。</span><span class="sxs-lookup"><span data-stu-id="1365c-125">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="1365c-126">ビデオ、スクリーンショット、注釈を組み合わせることにより、同じ場所に t&#39;いなくても、リアルタイムで問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="1365c-126">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="1365c-127">リモートコラボレーターは参照イメージ、概略図、およびその他の役に立つ情報を挿入できます。技術者は、&#39;、HoloLens でのヘッドアップとハンドフリーの作業中に、概略図を参照できます。</span><span class="sxs-lookup"><span data-stu-id="1365c-127">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="1365c-128">このガイドで行うこと:</span><span class="sxs-lookup"><span data-stu-id="1365c-128">In this guide you will:</span></span>

<span data-ttu-id="1365c-129">準備:</span><span class="sxs-lookup"><span data-stu-id="1365c-129">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="1365c-130">HoloLens 2 デバイスのインフラストラクチャの基本について説明します。</span><span class="sxs-lookup"><span data-stu-id="1365c-130">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="1365c-131">Azure AD とセットアップの詳細について&#39;は、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1365c-131">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="1365c-132">Id 管理と Azure AD アカウントを最適に設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1365c-132">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="1365c-133">MDM の詳細を確認し、まだ準備ができていない場合は、Intune を使用してセットアップします。&#39;。</span><span class="sxs-lookup"><span data-stu-id="1365c-133">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="1365c-134">リモートアシスタンスのネットワーク要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="1365c-134">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="1365c-135">必要に応じて、組織のリソースに接続するための VPN</span><span class="sxs-lookup"><span data-stu-id="1365c-135">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="1365c-136">以下を構成します。</span><span class="sxs-lookup"><span data-stu-id="1365c-136">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="1365c-137">ユーザーとグループを作成する方法。</span><span class="sxs-lookup"><span data-stu-id="1365c-137">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="1365c-138">Azure AD 内で自動登録を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1365c-138">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="1365c-139">アプリケーションライセンスを割り当てる方法。</span><span class="sxs-lookup"><span data-stu-id="1365c-139">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="1365c-140">展開: </span><span class="sxs-lookup"><span data-stu-id="1365c-140">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="1365c-141">HoloLens 2 をセットアップし、登録を検証します。</span><span class="sxs-lookup"><span data-stu-id="1365c-141">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="1365c-142">検証リモートアシスタンス通話を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1365c-142">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="1365c-143">保守:</span><span class="sxs-lookup"><span data-stu-id="1365c-143">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="1365c-144">Microsoft Store アプリを使用してリモートアシスタンスを更新する方法。</span><span class="sxs-lookup"><span data-stu-id="1365c-144">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="1365c-145">サポートプランを作成しています。</span><span class="sxs-lookup"><span data-stu-id="1365c-145">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="1365c-146">開発計画。</span><span class="sxs-lookup"><span data-stu-id="1365c-146">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="1365c-147">次のステップ</span><span class="sxs-lookup"><span data-stu-id="1365c-147">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1365c-148">クラウドに接続されたデプロイ-準備</span><span class="sxs-lookup"><span data-stu-id="1365c-148">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

