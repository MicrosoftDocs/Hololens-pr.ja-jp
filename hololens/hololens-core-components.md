---
title: 商用環境での HoloLens 2 の展開計画
description: インフラストラクチャ、azure active directory、モバイルデバイス管理など、エンタープライズ環境で HoloLens をデプロイおよび管理するための主要なニーズについて説明します。
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
ms.openlocfilehash: 43162389eae82bc09135c62acd40d71048d14db1
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639082"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a><span data-ttu-id="42864-103">商用環境での HoloLens 2 の展開計画</span><span class="sxs-lookup"><span data-stu-id="42864-103">Planning HoloLens 2 deployment in a commercial environment</span></span>

## <a name="overview"></a><span data-ttu-id="42864-104">概要</span><span class="sxs-lookup"><span data-stu-id="42864-104">Overview</span></span>

> [!NOTE]
> <span data-ttu-id="42864-105">この概要は、IT プロフェッショナルが組織内で Microsoft HoloLens 2 つのデバイスを展開および管理する際の考慮事項を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="42864-105">This overview is intended to help IT professionals understand considerations for deploying and managing Microsoft HoloLens 2 devices within an organization.</span></span> <span data-ttu-id="42864-106">デバイスエンドユーザーについては、「 [HoloLens 2 を使用](hololens2-setup.md)して作業を開始する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42864-106">For device end users, see [Get your HoloLens 2 ready to use](hololens2-setup.md) to get started.</span></span>

<span data-ttu-id="42864-107">HoloLens 2 は Windows 10 Holographic で実行されます。これにより、堅牢で柔軟性に富んだ、モバイルデバイスおよびアプリ管理テクノロジを組織に提供できます。</span><span class="sxs-lookup"><span data-stu-id="42864-107">HoloLens 2 runs on Windows 10 Holographic which provides organizations with robust, flexible, built-in mobile device and app management technologies.</span></span> <span data-ttu-id="42864-108">Windows 10 Holographic は、エンドツーエンドのデバイスライフサイクル管理をサポートして、企業がデバイス、データ、およびアプリを管理できるようにします。</span><span class="sxs-lookup"><span data-stu-id="42864-108">Windows 10 Holographic supports end-to-end device lifecycle management to give companies control over their devices, data, and apps.</span></span> <span data-ttu-id="42864-109">HoloLens 2 は、包括的なモバイルデバイス管理ソリューションを使用して、デバイスの登録、構成、アプリケーションの管理からメンテナンスや提供終了まで、標準的なライフサイクルプラクティスに簡単に組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="42864-109">The HoloLens 2 can easily be incorporated into standard lifecycle practices, from device enrollment, configuration, and application management to maintenance and retirement using a comprehensive mobile device management solution.</span></span>

<span data-ttu-id="42864-110">次の手順とビデオを参考にして、組織内で HoloLens 2 を導入することができます。</span><span class="sxs-lookup"><span data-stu-id="42864-110">The following steps and video can help guide you through the process of HoloLens 2 adoption within your organization.</span></span>

| &nbsp; | &nbsp; |
|--|--|
| ![手順 1](images/1green.png)| <br/> <span data-ttu-id="42864-112">**[一般的な展開シナリオ](hololens-requirements.md)**: 展開シナリオについて理解し、HoloLens 2 デバイスを展開するために必要なコアコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="42864-112">**[Common Deployment Scenarios](hololens-requirements.md)**: Understand deployment scenarios and explore the core components needed to deploy HoloLens 2 devices.</span></span> |
| ![手順 2](images/2green.png)| <br/> <span data-ttu-id="42864-114">**[準備](#prepare)**: HoloLens 2 に必要なインフラストラクチャの要点に慣れることができます。</span><span class="sxs-lookup"><span data-stu-id="42864-114">**[Prepare](#prepare)**: Become familiar with the infrastructure essentials needed for HoloLens 2.</span></span> |
| ![手順 3.](images/3green.png) | <br/> <span data-ttu-id="42864-116">**[構成](#configure)**: クラウドベースの展開のために不可欠なコンポーネントを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="42864-116">**[Configure](#configure)**: Learn how to configure your essential components for a cloud-based deployment.</span></span> |
| ![手順 4](images/4green.png) | <br/> <span data-ttu-id="42864-118">**[デプロイ](#deploy)**: デバイスをデプロイし、アプリケーションを安全かつ効率的に配布する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="42864-118">**[Deploy](#deploy)**: Discover how to deploy your devices and distribute your applications securely and efficiently.</span></span> |
| ![手順 5.](images/5green.png) | <br/> <span data-ttu-id="42864-120">**[メンテナンス](#maintain)**: HoloLens 2 デバイスの状態を適切に維持し、企業のポリシーに準拠していることを確認するために必要な情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="42864-120">**[Maintain](#maintain)**: Find out what's needed to properly maintain the state of your HoloLens 2 devices and ensure compliance with corporate policy.</span></span> |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a><span data-ttu-id="42864-121">準備</span><span class="sxs-lookup"><span data-stu-id="42864-121">Prepare</span></span>

<span data-ttu-id="42864-122">HoloLens 2 のすべての機能をサポートするために必要な、基本的なインフラストラクチャサービスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="42864-122">Learn about essential infrastructure services required to support the full set of HoloLens 2 capabilities.</span></span>

| <span data-ttu-id="42864-123">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="42864-123">Component</span></span> | <span data-ttu-id="42864-124">説明</span><span class="sxs-lookup"><span data-stu-id="42864-124">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="42864-125">Azure AD</span><span class="sxs-lookup"><span data-stu-id="42864-125">Azure AD</span></span>](hololens-identity.md) | <span data-ttu-id="42864-126">HoloLens 2 の id とアクセスの管理を提供します</span><span class="sxs-lookup"><span data-stu-id="42864-126">Provides identity and access management for the HoloLens 2</span></span>  |
| [<span data-ttu-id="42864-127">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="42864-127">Mobile Device Management</span></span>](hololens-mdm-configure.md)| <span data-ttu-id="42864-128">テナントに接続されている HoloLens 2 デバイスを管理します</span><span class="sxs-lookup"><span data-stu-id="42864-128">Manages HoloLens 2 devices connected to your tenant</span></span>  |
| [<span data-ttu-id="42864-129">Wi-fi ネットワーク</span><span class="sxs-lookup"><span data-stu-id="42864-129">Wi-Fi Network</span></span>](hololens-commercial-infrastructure.md)| <span data-ttu-id="42864-130">Wi-Fi が利用可能で、デバイスをインターネットに接続できる</span><span class="sxs-lookup"><span data-stu-id="42864-130">Wi-Fi is available and devices can be connected to the Internet</span></span>  |

## <a name="configure"></a><span data-ttu-id="42864-131">構成</span><span class="sxs-lookup"><span data-stu-id="42864-131">Configure</span></span>

<span data-ttu-id="42864-132">Intune と自動操縦を低タッチソリューションとして使用して、組織の Azure AD のテナントと MDM に HoloLens 2 を登録して構成することができます。</span><span class="sxs-lookup"><span data-stu-id="42864-132">Use Intune and Autopilot as low-touch solutions for enrolling and configuring HoloLens 2 to your organization’s Azure AD tenant and MDM.</span></span>

| <span data-ttu-id="42864-133">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="42864-133">Component</span></span> | <span data-ttu-id="42864-134">説明</span><span class="sxs-lookup"><span data-stu-id="42864-134">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="42864-135">自動登録</span><span class="sxs-lookup"><span data-stu-id="42864-135">Auto Enrollment</span></span>](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | <span data-ttu-id="42864-136">初回ログイン後、デバイスは Azure AD に自動的に登録され、MDM に登録されます。</span><span class="sxs-lookup"><span data-stu-id="42864-136">After initial login, devices automatically register with Azure AD and enroll into MDM</span></span>  |
| [<span data-ttu-id="42864-137">アプリケーションライセンス</span><span class="sxs-lookup"><span data-stu-id="42864-137">Application Licenses</span></span>](hololens2-cloud-connected-configure.md#application-licenses)| <span data-ttu-id="42864-138">ユーザー、ユーザーグループ、またはデバイスグループのいずれかに適用できます。</span><span class="sxs-lookup"><span data-stu-id="42864-138">Can be applied to either users, user groups, or device groups</span></span>  |
| [<span data-ttu-id="42864-139">Azure のユーザーとグループ</span><span class="sxs-lookup"><span data-stu-id="42864-139">Azure Users and Groups</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups) | <span data-ttu-id="42864-140">HoloLens 2 の構成とライセンスを割り当てるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="42864-140">Helps assign configurations and licenses for the HoloLens 2</span></span>  |

## <a name="deploy"></a><span data-ttu-id="42864-141">配置</span><span class="sxs-lookup"><span data-stu-id="42864-141">Deploy</span></span>

<span data-ttu-id="42864-142">HoloLens 2 デバイスを配布し、構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="42864-142">Distribute your HoloLens 2 devices and validate their configuration.</span></span> 

| <span data-ttu-id="42864-143">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="42864-143">Component</span></span> | <span data-ttu-id="42864-144">説明</span><span class="sxs-lookup"><span data-stu-id="42864-144">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="42864-145">登録の検証</span><span class="sxs-lookup"><span data-stu-id="42864-145">Enrollment Validation</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation) | <span data-ttu-id="42864-146">デバイスが設定または Azure Portal から参加して Azure AD かどうかを検証する</span><span class="sxs-lookup"><span data-stu-id="42864-146">Validate the device has Azure AD Joined from Settings or the Azure Portal</span></span> |
| [<span data-ttu-id="42864-147">証明書の検証</span><span class="sxs-lookup"><span data-stu-id="42864-147">Certificate Validation</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | <span data-ttu-id="42864-148">設定を確認し、正常に配布されたことを検証する</span><span class="sxs-lookup"><span data-stu-id="42864-148">Check settings and validate they have been distributed correctly</span></span> |
| [<span data-ttu-id="42864-149">アプリのインストールの検証</span><span class="sxs-lookup"><span data-stu-id="42864-149">Validate app installs</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install) | <span data-ttu-id="42864-150">アプリが存在し、HoloLens 2 で作業していることを確認します</span><span class="sxs-lookup"><span data-stu-id="42864-150">Confirm the app is present and working on your HoloLens 2</span></span> |

## <a name="maintain"></a><span data-ttu-id="42864-151">管理</span><span class="sxs-lookup"><span data-stu-id="42864-151">Maintain</span></span>

<span data-ttu-id="42864-152">MDM システムまたは Microsoft Store と共にビジネスに Windows Update を使用して、HoloLens 2 とアプリの継続的な更新を維持します。</span><span class="sxs-lookup"><span data-stu-id="42864-152">Use Windows Update for Business along with your MDM system or the Microsoft Store to keep your fleet of HoloLens 2 and apps updated.</span></span>

| <span data-ttu-id="42864-153">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="42864-153">Component</span></span> | <span data-ttu-id="42864-154">説明</span><span class="sxs-lookup"><span data-stu-id="42864-154">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="42864-155">HoloLens 2 の更新</span><span class="sxs-lookup"><span data-stu-id="42864-155">Update HoloLens 2</span></span>](hololens-updates.md) | <span data-ttu-id="42864-156">ビジネス向け Windows 更新プログラムを使用して、必要に応じて更新を構成します</span><span class="sxs-lookup"><span data-stu-id="42864-156">Configure updates as needed through Windows Updates for Business</span></span> |
| [<span data-ttu-id="42864-157">アプリを更新する</span><span class="sxs-lookup"><span data-stu-id="42864-157">Update apps</span></span>](app-deploy-overview.md) | <span data-ttu-id="42864-158">MDM システムまたは Microsoft Store を使用して構成する</span><span class="sxs-lookup"><span data-stu-id="42864-158">Configure through your MDM system or the Microsoft Store</span></span>
