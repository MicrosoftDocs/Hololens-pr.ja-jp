---
title: 商用環境で HoloLens をセットアップする
description: エンタープライズ環境での HoloLens の展開と管理の詳細については、こちらを参照してください。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.openlocfilehash: 8aa8e0f679ad18a2e47f34c5f1233435a502dc0c
ms.sourcegitcommit: f3cda6c6b3bfb7ba4be5f4da66d8ed5b03ca807d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830131"
---
# <span data-ttu-id="9feb9-103">商用環境での HoloLens の展開</span><span class="sxs-lookup"><span data-stu-id="9feb9-103">Deploy HoloLens in a commercial environment</span></span>

<span data-ttu-id="9feb9-104">企業向けの設定では、HoloLens をスケールで展開して構成することができます。</span><span class="sxs-lookup"><span data-stu-id="9feb9-104">You can deploy and configure HoloLens at scale in a commercial setting.</span></span> <span data-ttu-id="9feb9-105">この記事では、商用環境で HoloLens デバイスを展開するための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="9feb9-105">This article provides instructions for deploying HoloLens devices in a commercial environment.</span></span> <span data-ttu-id="9feb9-106">このガイドでは、HoloLens の基本的な知識を前提としています。</span><span class="sxs-lookup"><span data-stu-id="9feb9-106">This guide assumes basic familiarity with HoloLens.</span></span> <span data-ttu-id="9feb9-107">「[はじめに」のガイド](hololens1-setup.md)に従って、初めて HoloLens をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="9feb9-107">Follow the [get started guide](hololens1-setup.md) to set up HoloLens for the first time.</span></span>

<span data-ttu-id="9feb9-108">また、このドキュメントでは、企業ネットワークでの使用に関しては、HoloLens がセキュリティチームによって評価されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="9feb9-108">This document also assumes that the HoloLens has been evaluated by security teams as safe to use on the corporate network.</span></span> <span data-ttu-id="9feb9-109">セキュリティに関するよく寄せられる質問については、[こちら](hololens-faq-security.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9feb9-109">Frequently asked security questions can be found [here](hololens-faq-security.md)</span></span>

## <span data-ttu-id="9feb9-110">展開手順の概要</span><span class="sxs-lookup"><span data-stu-id="9feb9-110">Overview of Deployment Steps</span></span>

1. [<span data-ttu-id="9feb9-111">必要な機能を決定する</span><span class="sxs-lookup"><span data-stu-id="9feb9-111">Determine what features you need</span></span>](hololens-requirements.md#step-1-determine-what-you-need)
1. [<span data-ttu-id="9feb9-112">必要なライセンスを決定する</span><span class="sxs-lookup"><span data-stu-id="9feb9-112">Determine what licenses you need</span></span>](hololens-licenses-requirements.md)
1. <span data-ttu-id="9feb9-113">[HoloLens 用にネットワークを構成](hololens-commercial-infrastructure.md)します。</span><span class="sxs-lookup"><span data-stu-id="9feb9-113">[Configure your network for HoloLens](hololens-commercial-infrastructure.md).</span></span>
    1. <span data-ttu-id="9feb9-114">このセクションでは、ファイアウォールで許可する必要がある帯域幅の要件、URL、ポートについて説明します。Azure AD ガイダンス;モバイルデバイス管理 (MDM) のガイダンスアプリの展開と管理のガイダンス証明書のガイダンス。</span><span class="sxs-lookup"><span data-stu-id="9feb9-114">This section includes bandwidth requirements, URL, and ports that need to be allowed on your firewall; Azure AD guidance; Mobile Device Management (MDM) Guidance; app deployment/management guidance; and certificate guidance.</span></span>
1. <span data-ttu-id="9feb9-115">省略[プロビジョニングパッケージを使用して HoloLens を構成](hololens-provisioning.md)する</span><span class="sxs-lookup"><span data-stu-id="9feb9-115">(Optional) [Configure HoloLens using a provisioning package](hololens-provisioning.md)</span></span>
1. [<span data-ttu-id="9feb9-116">デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="9feb9-116">Enroll Device</span></span>](hololens-enroll-mdm.md)
1. [<span data-ttu-id="9feb9-117">HoloLens のリング ベースの更新プログラムをセットアップする</span><span class="sxs-lookup"><span data-stu-id="9feb9-117">Set up ring based updates for HoloLens</span></span>](hololens-updates.md)
1. [<span data-ttu-id="9feb9-118">HoloLens の Bitlocker デバイスの暗号化を有効にする</span><span class="sxs-lookup"><span data-stu-id="9feb9-118">Enable Bitlocker device encryption for HoloLens</span></span>](hololens-encryption.md)

## <span data-ttu-id="9feb9-119">手順 1. </span><span class="sxs-lookup"><span data-stu-id="9feb9-119">Step 1.</span></span> <span data-ttu-id="9feb9-120">必要なものを決定する</span><span class="sxs-lookup"><span data-stu-id="9feb9-120">Determine what you need</span></span>

<span data-ttu-id="9feb9-121">お客様の環境に HoloLens を展開する前に、まず必要な機能、アプリ、および種類を特定することが重要です。</span><span class="sxs-lookup"><span data-stu-id="9feb9-121">Before deploying the HoloLens in your environment, it is important to first determine what features, apps, and type of identities are needed.</span></span> <span data-ttu-id="9feb9-122">また、セキュリティチームが会社のネットワークで HoloLens の使用を承認していることを確認することも重要です。</span><span class="sxs-lookup"><span data-stu-id="9feb9-122">It is also important to ensure that your security team has approved of the use of the HoloLens on the company's network.</span></span> <span data-ttu-id="9feb9-123">セキュリティの追加情報について[よく寄せられる質問](hololens-faq-security.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9feb9-123">Please see [Frequently ask security questions](hololens-faq-security.md) for additional security information.</span></span>

### <span data-ttu-id="9feb9-124">Id の種類</span><span class="sxs-lookup"><span data-stu-id="9feb9-124">Type of Identity</span></span>

<span data-ttu-id="9feb9-125">デバイスへのサインインに使用される id の種類を決定します。</span><span class="sxs-lookup"><span data-stu-id="9feb9-125">Determine the type of identity that will be used to sign into the device.</span></span>

1. <span data-ttu-id="9feb9-126">**ローカルアカウント:** このアカウントは、デバイスに対してローカル (windows PC のローカル管理者アカウントなど) になります。</span><span class="sxs-lookup"><span data-stu-id="9feb9-126">**Local Accounts:** This account is local to the device (like a local admin account on a windows PC).</span></span> <span data-ttu-id="9feb9-127">これにより、1ユーザーだけがデバイスにログインできるようになります。</span><span class="sxs-lookup"><span data-stu-id="9feb9-127">This will allow only 1 user to log into the device.</span></span>
2. <span data-ttu-id="9feb9-128">**MSA:** これは個人アカウント (outlook、hotmail、gmail、yahoo など) です。これにより、1ユーザーだけがデバイスにログインできるようになります。</span><span class="sxs-lookup"><span data-stu-id="9feb9-128">**MSA:** This is a personal account (like outlook, hotmail, gmail, yahoo, etc.) This will allow only 1 user to log into the device.</span></span>
3. <span data-ttu-id="9feb9-129">**Azure Active Directory (AZURE AD) アカウント:** これは、Azure AD で作成されたアカウントです。</span><span class="sxs-lookup"><span data-stu-id="9feb9-129">**Azure Active Directory (Azure AD) accounts:** This is an account created in Azure AD.</span></span> <span data-ttu-id="9feb9-130">これにより、企業は HoloLens デバイスを管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9feb9-130">This grants your corporation the ability to manage the HoloLens device.</span></span> <span data-ttu-id="9feb9-131">これにより、複数のユーザーが HoloLens 第1世代の商用スイート/HoloLens 2 デバイスにログインできるようになります。</span><span class="sxs-lookup"><span data-stu-id="9feb9-131">This will allow multiple users to log into the HoloLens 1st Gen Commercial Suite/the HoloLens 2 device.</span></span>

<span data-ttu-id="9feb9-132">Id 型の詳細については、HoloLens の[id](hololens-identity.md)の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9feb9-132">For more detailed information about identity types, please visit our [HoloLens Identity](hololens-identity.md) article.</span></span>

### <span data-ttu-id="9feb9-133">機能の種類</span><span class="sxs-lookup"><span data-stu-id="9feb9-133">Type of Features</span></span>

<span data-ttu-id="9feb9-134">お客様の機能要件によって、必要な HoloLens が決定されます。</span><span class="sxs-lookup"><span data-stu-id="9feb9-134">Your feature requirements will determine which HoloLens you need.</span></span> <span data-ttu-id="9feb9-135">顧客の環境に展開されることが多い一般的な機能の1つに、キオスクモードがあります。</span><span class="sxs-lookup"><span data-stu-id="9feb9-135">One popular feature that we see deployed in customer environments frequently is Kiosk Mode.</span></span> <span data-ttu-id="9feb9-136">HoloLens の主要機能と、それらをサポートする HoloLens のエディションの一覧については、[こちら](hololens-commercial-features.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9feb9-136">A list of HoloLens key features, and the editions of HoloLens that support them, can be found [here](hololens-commercial-features.md).</span></span>

**<span data-ttu-id="9feb9-137">キオスクモードとは</span><span class="sxs-lookup"><span data-stu-id="9feb9-137">What is Kiosk Mode?</span></span>**

<span data-ttu-id="9feb9-138">キオスクモードは、ユーザーがアクセスできるアプリを制限するための手段です。</span><span class="sxs-lookup"><span data-stu-id="9feb9-138">Kiosk mode is a way to restrict the apps that a user has access to.</span></span> <span data-ttu-id="9feb9-139">これは、ユーザーが特定のアプリにしかアクセスできないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="9feb9-139">This means that users will only be allowed to access certain apps.</span></span>

**<span data-ttu-id="9feb9-140">どのキオスクモードが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="9feb9-140">What Kiosk Mode do I require?</span></span>**

<span data-ttu-id="9feb9-141">キオスクモードには、単一アプリとマルチアプリの2種類があります。</span><span class="sxs-lookup"><span data-stu-id="9feb9-141">There are two types of Kiosk Modes: Single app and multi-app.</span></span> <span data-ttu-id="9feb9-142">1つのアプリのキオスクモードでは、ユーザーは1つのアプリにしかアクセスできません。マルチアプリのキオスクモードでは、複数の指定したアプリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9feb9-142">Single app kiosk mode allows user to only access one app while multi-app kiosk mode allows users to access multiple, specified apps.</span></span> <span data-ttu-id="9feb9-143">お客様の会社に適したキオスクモードを決定するには、次の2つの質問に回答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9feb9-143">To determine which kiosk mode is right for your corporation, the following two questions need to be answered:</span></span>

1. **<span data-ttu-id="9feb9-144">さまざまなユーザーがさまざまなエクスペリエンスと制限を必要とするかどうか</span><span class="sxs-lookup"><span data-stu-id="9feb9-144">Do different users require different experiences/restrictions?</span></span>** <span data-ttu-id="9feb9-145">次の例を参考にしてください。ユーザー A は、リモートアシストへのアクセスのみを必要とするフィールドサービスエンジニアです。</span><span class="sxs-lookup"><span data-stu-id="9feb9-145">Consider the following example: User A is a field service engineer who only needs access to Remote Assist.</span></span> <span data-ttu-id="9feb9-146">ユーザー B は、ガイドへのアクセスのみを必要とする研修者です。</span><span class="sxs-lookup"><span data-stu-id="9feb9-146">User B is a trainee who only needs access to Guides.</span></span>
    1. <span data-ttu-id="9feb9-147">[はい] の場合は、次のものが必要になります。</span><span class="sxs-lookup"><span data-stu-id="9feb9-147">If yes, you will require the following:</span></span>
        1. <span data-ttu-id="9feb9-148">Azure AD アカウントを、デバイスへのサインイン方法として使うことができます。</span><span class="sxs-lookup"><span data-stu-id="9feb9-148">Azure AD Accounts as the method of signing into the device.</span></span>
        1. <span data-ttu-id="9feb9-149">**マルチアプリ**キオスクモード。</span><span class="sxs-lookup"><span data-stu-id="9feb9-149">**Multi-app** kiosk mode.</span></span>
    1. <span data-ttu-id="9feb9-150">「いいえ」の場合は、引き続き質問2</span><span class="sxs-lookup"><span data-stu-id="9feb9-150">If no, continue to question two</span></span>
1. **<span data-ttu-id="9feb9-151">複数のアプリでのエクスペリエンスが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="9feb9-151">Do you require a multi-app experience?</span></span>**
    1. <span data-ttu-id="9feb9-152">[はい] の場合は、**マルチアプリ**のキオスクがモードである必要があります</span><span class="sxs-lookup"><span data-stu-id="9feb9-152">If yes, **Multi-app** kiosk is mode is needed</span></span>
    1. <span data-ttu-id="9feb9-153">質問1と2の答えが両方ともいいえの場合、**単一アプリ**のキオスクモードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9feb9-153">If your answer to question 1 and 2 are both no, **single-app** kiosk mode can be used</span></span>

**<span data-ttu-id="9feb9-154">キオスクモードを構成する方法:</span><span class="sxs-lookup"><span data-stu-id="9feb9-154">How to Configure Kiosk Mode:</span></span>**

<span data-ttu-id="9feb9-155">HoloLens 用のキオスクモードを展開するには、主に2つの方法 ([プロビジョニングパッケージ](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)と[MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) があります。</span><span class="sxs-lookup"><span data-stu-id="9feb9-155">There are two main ways ([provisioning packages](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) and [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) to deploy kiosk mode for HoloLens.</span></span> <span data-ttu-id="9feb9-156">これらのオプションについては、このドキュメントの後半で説明します。ただし、上記のリンクを使用して、このドキュメントの該当するセクションに移動することはできます。</span><span class="sxs-lookup"><span data-stu-id="9feb9-156">These options will be discussed later in the document; however, you can use the links above to jump to the respective sections in this doc.</span></span>

### <span data-ttu-id="9feb9-157">アプリとアプリ固有のシナリオ</span><span class="sxs-lookup"><span data-stu-id="9feb9-157">Apps and App Specific Scenarios</span></span>

<span data-ttu-id="9feb9-158">このドキュメントに記載されている手順の大半は、次のアプリにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="9feb9-158">The majority of the steps found in this document will also apply to the following apps:</span></span>

| <span data-ttu-id="9feb9-159">アプリ</span><span class="sxs-lookup"><span data-stu-id="9feb9-159">App</span></span> | <span data-ttu-id="9feb9-160">アプリ固有のシナリオ</span><span class="sxs-lookup"><span data-stu-id="9feb9-160">App Specific Scenarios</span></span> |
| --- | --- |
| <span data-ttu-id="9feb9-161">リモートアシスト</span><span class="sxs-lookup"><span data-stu-id="9feb9-161">Remote Assist</span></span> | [<span data-ttu-id="9feb9-162">クロステナント通信</span><span class="sxs-lookup"><span data-stu-id="9feb9-162">Cross Tenant Communication</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview)|
| <span data-ttu-id="9feb9-163">ガイド</span><span class="sxs-lookup"><span data-stu-id="9feb9-163">Guides</span></span>  | *<span data-ttu-id="9feb9-164">もうすぐです</span><span class="sxs-lookup"><span data-stu-id="9feb9-164">Coming Soon</span></span>* |
|<span data-ttu-id="9feb9-165">カスタムアプリ</span><span class="sxs-lookup"><span data-stu-id="9feb9-165">Custom Apps</span></span> | *<span data-ttu-id="9feb9-166">もうすぐです</span><span class="sxs-lookup"><span data-stu-id="9feb9-166">Coming Soon</span></span>* |

### <span data-ttu-id="9feb9-167">登録方法を決定する</span><span class="sxs-lookup"><span data-stu-id="9feb9-167">Determine your enrollment method</span></span>

1. <span data-ttu-id="9feb9-168">プロビジョニングパッケージのセキュリティトークンを使った一括登録。</span><span class="sxs-lookup"><span data-stu-id="9feb9-168">Bulk enrollment with a security token in a provisioning package.</span></span>  
  <span data-ttu-id="9feb9-169">長所: これが最も自動化された方法です。</span><span class="sxs-lookup"><span data-stu-id="9feb9-169">Pros: this is the most automated approach\</span></span>
  <span data-ttu-id="9feb9-170">短所: サーバー側の初期セットアップを行います。</span><span class="sxs-lookup"><span data-stu-id="9feb9-170">Cons: takes initial server-side setup</span></span>  
1. <span data-ttu-id="9feb9-171">ユーザーのサインイン時に自動登録を行います。</span><span class="sxs-lookup"><span data-stu-id="9feb9-171">Auto-enroll on user sign in.</span></span>  
  <span data-ttu-id="9feb9-172">長所: 最も簡単な方法</span><span class="sxs-lookup"><span data-stu-id="9feb9-172">Pros: easiest approach</span></span>  
  <span data-ttu-id="9feb9-173">欠点: プロビジョニングパッケージが適用された後、ユーザーはセットアップを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9feb9-173">Cons: users will need to complete set up after the provisioning package has been applied</span></span>
1. <span data-ttu-id="9feb9-174">_推奨しません_-セットアップ後に手動で登録してください。</span><span class="sxs-lookup"><span data-stu-id="9feb9-174">_not recommended_ - Manually enroll post-setup.</span></span>  
  <span data-ttu-id="9feb9-175">長所: セットアップ後に登録できる</span><span class="sxs-lookup"><span data-stu-id="9feb9-175">Pros: possible to enroll after set up</span></span>  
  <span data-ttu-id="9feb9-176">欠点: 手動のアプローチとデバイスは、手動で登録しない限り、一元管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="9feb9-176">Cons: most manual approach and devices aren't centrally manageable until they're manually enrolled.</span></span>

  <span data-ttu-id="9feb9-177">詳細については、こちらを参照して[ください](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="9feb9-177">More information can be found [here](hololens-enroll-mdm.md)</span></span>

### <span data-ttu-id="9feb9-178">プロビジョニングパッケージを作成する必要があるかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="9feb9-178">Determine if you need to create a provisioning package</span></span>

<span data-ttu-id="9feb9-179">HoloLens デバイス (プロビジョニングパッケージと MDMs) を構成するには、2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="9feb9-179">There are two methods to configure a HoloLens device (Provisioning packages and MDMs).</span></span> <span data-ttu-id="9feb9-180">HoloLens デバイスの構成には MDM を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9feb9-180">We suggest using your MDM to configure you HoloLens device.</span></span> <span data-ttu-id="9feb9-181">ただし、プロビジョニングパッケージの使用が適しているシナリオはいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="9feb9-181">However, there are some scenarios where using a provisioning package is the better choice:</span></span>

1. <span data-ttu-id="9feb9-182">不在時のエクスペリエンス (OOBE) をスキップするように HoloLens を構成する必要がある場合</span><span class="sxs-lookup"><span data-stu-id="9feb9-182">You want to configure the HoloLens to skip the Out of Box Experience (OOBE)</span></span>
1. <span data-ttu-id="9feb9-183">複雑なネットワークでの証明書の展開で問題が発生しています。</span><span class="sxs-lookup"><span data-stu-id="9feb9-183">You are having trouble deploying certificate in a complex network.</span></span> <span data-ttu-id="9feb9-184">多くの場合、MDM (複雑な環境でも) を使って証明書を展開できます。</span><span class="sxs-lookup"><span data-stu-id="9feb9-184">The majority of the time you can deploy certificates using MDM (even in complex environments).</span></span> <span data-ttu-id="9feb9-185">ただし、一部のシナリオでは、プロビジョニングパッケージを使用して証明書を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9feb9-185">However, some scenarios require certificates to be deployed through the provisioning package.</span></span>

<span data-ttu-id="9feb9-186">プロビジョニング パッケージで適用できる HoloLens 構成の例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9feb9-186">Some of the HoloLens configurations you can apply in a provisioning package:</span></span>

- <span data-ttu-id="9feb9-187">証明書をデバイスに適用する</span><span class="sxs-lookup"><span data-stu-id="9feb9-187">Apply certificates to the device</span></span>
- <span data-ttu-id="9feb9-188">Wi-Fi 接続をセットアップする</span><span class="sxs-lookup"><span data-stu-id="9feb9-188">Set up a Wi-Fi connection</span></span>
- <span data-ttu-id="9feb9-189">言語やロケールなどのすぐに使える質問を事前構成する</span><span class="sxs-lookup"><span data-stu-id="9feb9-189">Pre-configure out of box questions like language and locale</span></span>
- <span data-ttu-id="9feb9-190">(HoloLens 2) モバイル デバイス管理への一括登録をする</span><span class="sxs-lookup"><span data-stu-id="9feb9-190">(HoloLens 2) bulk enroll in mobile device management</span></span>
- <span data-ttu-id="9feb9-191">(HoloLens v1) キーを適用して Windows Holographic for Business を有効にする</span><span class="sxs-lookup"><span data-stu-id="9feb9-191">(HoloLens v1) Apply key to enable Windows Holographic for Business</span></span>

<span data-ttu-id="9feb9-192">プロビジョニングパッケージを使用する場合は、[このガイド](hololens-provisioning.md)に従ってください。</span><span class="sxs-lookup"><span data-stu-id="9feb9-192">If you decide to use provisioning packages, follow [this guide](hololens-provisioning.md).</span></span>

## <span data-ttu-id="9feb9-193">サポートを受ける</span><span class="sxs-lookup"><span data-stu-id="9feb9-193">Get support</span></span>

<span data-ttu-id="9feb9-194">Microsoft サポートサイトでサポートを利用します。</span><span class="sxs-lookup"><span data-stu-id="9feb9-194">Get support through the Microsoft support site.</span></span>

[<span data-ttu-id="9feb9-195">サポートリクエストをファイルに保存する</span><span class="sxs-lookup"><span data-stu-id="9feb9-195">File a support request</span></span>](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f)
