---
title: 商用HoloLens 2でのデプロイの計画
description: インフラストラクチャ、Azure Active Directory、モバイル デバイス管理など、エンタープライズ環境で HoloLens をデプロイおよび管理するための主要なニーズについて説明します。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 684059b1ab91860dc6af63cbd6f0927876fefb8c
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961484"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a><span data-ttu-id="34a46-103">商用HoloLens 2でのデプロイの計画</span><span class="sxs-lookup"><span data-stu-id="34a46-103">Planning HoloLens 2 deployment in a commercial environment</span></span>

## <a name="overview"></a><span data-ttu-id="34a46-104">概要</span><span class="sxs-lookup"><span data-stu-id="34a46-104">Overview</span></span>
> [!NOTE]
> <span data-ttu-id="34a46-105">この概要は、IT プロフェッショナルが組織内の 2 つのデバイスをMicrosoft HoloLens管理するための考慮事項を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="34a46-105">This overview is intended to help IT professionals understand considerations for deploying and managing Microsoft HoloLens 2 devices within an organization.</span></span> <span data-ttu-id="34a46-106">デバイス エンド ユーザーについては、「 [開始する基本」](hololens2-setup.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34a46-106">For device end users, see [The Basics](hololens2-setup.md) to get started.</span></span>

<span data-ttu-id="34a46-107">HoloLens 2は、堅牢でWindows 10 Holographicな組み込みのモバイル デバイスとアプリ管理テクノロジを組織に提供する、アプリケーション上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="34a46-107">HoloLens 2 runs on Windows 10 Holographic which provides organizations with robust, flexible, built-in mobile device and app management technologies.</span></span> <span data-ttu-id="34a46-108">Windows 10 Holographicは、デバイス、データ、アプリを会社が制御できるエンドツーエンドのデバイス ライフサイクル管理をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="34a46-108">Windows 10 Holographic supports end-to-end device lifecycle management to give companies control over their devices, data, and apps.</span></span> <span data-ttu-id="34a46-109">このHoloLens 2、包括的なモバイル デバイス管理ソリューションを使用して、デバイスの登録、構成、アプリケーション管理からメンテナンスと提供の削除まで、標準的なライフサイクル プラクティスに簡単に組み込みできます。</span><span class="sxs-lookup"><span data-stu-id="34a46-109">The HoloLens 2 can easily be incorporated into standard lifecycle practices, from device enrollment, configuration, and application management to maintenance and retirement using a comprehensive mobile device management solution.</span></span>

<span data-ttu-id="34a46-110">次の手順は、組織内で導入を開始するプロセスHoloLens 2に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="34a46-110">The following steps can help guide you through the process of HoloLens 2 adoption within your organization.</span></span>

| | |
|--|--|
| ![手順 1](images/1green.png)| <br/> <span data-ttu-id="34a46-112">**[一般的な展開シナリオ](hololens-requirements.md)**: 展開シナリオを理解し、デバイスを展開するために必要なコア コンポーネントHoloLens 2します。</span><span class="sxs-lookup"><span data-stu-id="34a46-112">**[Common Deployment Scenarios](hololens-requirements.md)**: Understand deployment scenarios and explore the core components needed to deploy HoloLens 2 devices.</span></span> |
| ![手順 2](images/2green.png)| <br/> <span data-ttu-id="34a46-114">**[準備](#prepare)**: アプリケーションの準備に必要なインフラストラクチャの要HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="34a46-114">**[Prepare](#prepare)**: Become familiar with the infrastructure essentials needed for HoloLens 2.</span></span> |
| ![手順 3.](images/3green.png) | <br/> <span data-ttu-id="34a46-116">**[構成](#configure)**: クラウドベースのデプロイに必要なコンポーネントを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="34a46-116">**[Configure](#configure)**: Learn how to configure your essential components for a cloud-based deployment.</span></span> |
| ![手順 4](images/4green.png) | <br/> <span data-ttu-id="34a46-118">**[デプロイ](#deploy)**: デバイスをデプロイし、アプリケーションを安全かつ効率的に配布する方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="34a46-118">**[Deploy](#deploy)**: Discover how to deploy your devices and distribute your applications securely and efficiently.</span></span> |
| ![手順 5.](images/5green.png) | <br/> <span data-ttu-id="34a46-120">**[メンテナンス](#maintain)**: デバイスの状態を適切に維持し、企業ポリシーに準拠するためにHoloLens 2必要な情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="34a46-120">**[Maintain](#maintain)**: Find out what's needed to properly maintain the state of your HoloLens 2 devices and ensure compliance with corporate policy.</span></span> |

## <a name="prepare"></a><span data-ttu-id="34a46-121">準備</span><span class="sxs-lookup"><span data-stu-id="34a46-121">Prepare</span></span>

<span data-ttu-id="34a46-122">機能の完全なセットをサポートするために必要な重要なインフラストラクチャ サービスHoloLens 2します。</span><span class="sxs-lookup"><span data-stu-id="34a46-122">Learn about essential infrastructure services required to support the full set of HoloLens 2 capabilities.</span></span> 

| <span data-ttu-id="34a46-123">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="34a46-123">Component</span></span> | <span data-ttu-id="34a46-124">説明</span><span class="sxs-lookup"><span data-stu-id="34a46-124">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="34a46-125">Azure AD</span><span class="sxs-lookup"><span data-stu-id="34a46-125">Azure AD</span></span>](hololens-identity.md) | <span data-ttu-id="34a46-126">アプリケーションの ID とアクセスの管理を提供HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="34a46-126">Provides identity and access management for the HoloLens 2</span></span>  |
| [<span data-ttu-id="34a46-127">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="34a46-127">Mobile Device Management</span></span>](hololens-mdm-configure.md)| <span data-ttu-id="34a46-128">テナントHoloLens 2デバイスを管理します</span><span class="sxs-lookup"><span data-stu-id="34a46-128">Manages HoloLens 2 devices connected to your tenant</span></span>  |
| [<span data-ttu-id="34a46-129">Wi-Fi ネットワーク</span><span class="sxs-lookup"><span data-stu-id="34a46-129">Wi-Fi Network</span></span>](hololens-commercial-infrastructure.md)| <span data-ttu-id="34a46-130">Wi-Fi利用可能で、デバイスをインターネットに接続できる</span><span class="sxs-lookup"><span data-stu-id="34a46-130">Wi-Fi is available and devices can be connected to the Internet</span></span>  |

## <a name="configure"></a><span data-ttu-id="34a46-131">構成</span><span class="sxs-lookup"><span data-stu-id="34a46-131">Configure</span></span>

<span data-ttu-id="34a46-132">Intune と Autopilot を低タッチ ソリューションとして使用して、組織HoloLens 2テナントと MDM にAzure ADを構成します。</span><span class="sxs-lookup"><span data-stu-id="34a46-132">Use Intune and Autopilot as low-touch solutions for enrolling and configuring HoloLens 2 to your organization’s Azure AD tenant and MDM.</span></span>

| <span data-ttu-id="34a46-133">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="34a46-133">Component</span></span> | <span data-ttu-id="34a46-134">説明</span><span class="sxs-lookup"><span data-stu-id="34a46-134">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="34a46-135">自動登録</span><span class="sxs-lookup"><span data-stu-id="34a46-135">Auto Enrollment</span></span>](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | <span data-ttu-id="34a46-136">初期ログイン後、デバイスは自動的にデバイスに登録Azure AD MDM に登録されます</span><span class="sxs-lookup"><span data-stu-id="34a46-136">After initial login, devices automatically register with Azure AD and enroll into MDM</span></span>  |
| [<span data-ttu-id="34a46-137">アプリケーション ライセンス</span><span class="sxs-lookup"><span data-stu-id="34a46-137">Application Licenses</span></span>](hololens2-cloud-connected-configure.md#application-licenses)| <span data-ttu-id="34a46-138">ユーザー、ユーザー グループ、またはデバイス グループに適用できます</span><span class="sxs-lookup"><span data-stu-id="34a46-138">Can be applied to either users, user groups, or device groups</span></span>  |
| [<span data-ttu-id="34a46-139">Azure ユーザーとグループ</span><span class="sxs-lookup"><span data-stu-id="34a46-139">Azure Users and Groups</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups) | <span data-ttu-id="34a46-140">アプリケーションの構成とライセンスを割り当HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="34a46-140">Helps assign configurations and licenses for the HoloLens 2</span></span>  |

## <a name="deploy"></a><span data-ttu-id="34a46-141">配置</span><span class="sxs-lookup"><span data-stu-id="34a46-141">Deploy</span></span>

<span data-ttu-id="34a46-142">デバイスを配布HoloLens 2、その構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="34a46-142">Distribute your HoloLens 2 devices and validate their configuration.</span></span> 

| <span data-ttu-id="34a46-143">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="34a46-143">Component</span></span> | <span data-ttu-id="34a46-144">説明</span><span class="sxs-lookup"><span data-stu-id="34a46-144">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="34a46-145">登録の検証</span><span class="sxs-lookup"><span data-stu-id="34a46-145">Enrollment Validation</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation) | <span data-ttu-id="34a46-146">デバイスが [設定Azure AD Azure Portal から参加済みである] を確認します</span><span class="sxs-lookup"><span data-stu-id="34a46-146">Validate the device has Azure AD Joined from Settings or the Azure Portal</span></span> |
| [<span data-ttu-id="34a46-147">証明書の検証</span><span class="sxs-lookup"><span data-stu-id="34a46-147">Certificate Validation</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | <span data-ttu-id="34a46-148">設定を確認し、正しく配布されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="34a46-148">Check settings and validate they have been distributed correctly</span></span> |
| [<span data-ttu-id="34a46-149">アプリのインストールを検証する</span><span class="sxs-lookup"><span data-stu-id="34a46-149">Validate app installs</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install) | <span data-ttu-id="34a46-150">アプリが存在し、アプリで動作HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="34a46-150">Confirm the app is present and working on your HoloLens 2</span></span> |

## <a name="maintain"></a><span data-ttu-id="34a46-151">管理</span><span class="sxs-lookup"><span data-stu-id="34a46-151">Maintain</span></span>

<span data-ttu-id="34a46-152">MDM Windows Update for Businessまたは MDM システムと共にMicrosoft Storeを使用して、デバイスとアプリのHoloLens 2を維持します。</span><span class="sxs-lookup"><span data-stu-id="34a46-152">Use Windows Update for Business along with your MDM system or the Microsoft Store to keep your fleet of HoloLens 2 and apps updated.</span></span>

| <span data-ttu-id="34a46-153">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="34a46-153">Component</span></span> | <span data-ttu-id="34a46-154">説明</span><span class="sxs-lookup"><span data-stu-id="34a46-154">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="34a46-155">更新HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="34a46-155">Update HoloLens 2</span></span>](hololens-updates.md) | <span data-ttu-id="34a46-156">ビジネス向け Windows 更新プログラムを使用して必要に応じて更新プログラムを構成する</span><span class="sxs-lookup"><span data-stu-id="34a46-156">Configure updates as needed through Windows Updates for Business</span></span> |
| [<span data-ttu-id="34a46-157">アプリを更新する</span><span class="sxs-lookup"><span data-stu-id="34a46-157">Update apps</span></span>](app-deploy-overview.md) | <span data-ttu-id="34a46-158">MDM システムまたはデバイスを使用して構成Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="34a46-158">Configure through your MDM system or the Microsoft Store</span></span>
