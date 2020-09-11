---
title: 概要-アプリ管理
description: アプリ、管理、アプリの管理
keywords: HoloLens、ユーザー、アカウント、アプリ、アプリケーション管理、
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e73a56e5a2fcef14e85f5f552e264dd8d796cc8f
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009455"
---
# <span data-ttu-id="7f05c-104">アプリ管理の概要</span><span class="sxs-lookup"><span data-stu-id="7f05c-104">App Management: Overview</span></span>

<span data-ttu-id="7f05c-105">アプリを展開するには、 **モバイルデバイス管理 (MDM)**、 **Microsoft ストア for Business**、 **Microsoft ストア**、または **プロビジョニング**によるインストールの4つの異なるパスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7f05c-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span> 

## <span data-ttu-id="7f05c-106">モバイル デバイス管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="7f05c-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="7f05c-107">MDM ソリューションを使用すると、IT の意思決定者や管理者は、社内、基幹業務のアプリをプライベートに自動インストール (プッシュ) することができます。また、ユーザーのグループに対してストアを通じてアプリを購入することもできます。</span><span class="sxs-lookup"><span data-stu-id="7f05c-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="7f05c-108">HoloLens デバイスは、 [アプリケーション管理](app-deploy-intune.md)用の Microsoft Endpoint Manager (Intune) と最適に動作します。</span><span class="sxs-lookup"><span data-stu-id="7f05c-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="7f05c-109">また、ユーザーは、会社のポータルのダウンロード操作を通じて、IT によって管理されたアプリをきめ細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="7f05c-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE] 
> <span data-ttu-id="7f05c-110">次の手順は、Intune を使ってアプリケーションを管理するユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="7f05c-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="7f05c-111">アプリケーションとデバイスの管理には Intune を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7f05c-111">Microsoft recommends using Intune for application and device management.</span></span>
    
<span data-ttu-id="7f05c-112">モバイルデバイス管理 (MDM) は、次の場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="7f05c-112">Mobile Device Management (MDM) is applicable for:</span></span> 
* <span data-ttu-id="7f05c-113">MDM の展開と会社のポータル</span><span class="sxs-lookup"><span data-stu-id="7f05c-113">MDM deployed + Company Portal</span></span> 
* <span data-ttu-id="7f05c-114">1行の Buisness (非パブリック) アプリ</span><span class="sxs-lookup"><span data-stu-id="7f05c-114">Line of Buisness (non-public) apps</span></span>
* <span data-ttu-id="7f05c-115">会社のポータル経由で利用可能なアプリケーションを手動でインストールする</span><span class="sxs-lookup"><span data-stu-id="7f05c-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="7f05c-116">MDM ポリシーによる管理者プッシュ</span><span class="sxs-lookup"><span data-stu-id="7f05c-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="7f05c-117">MDM による自動更新</span><span class="sxs-lookup"><span data-stu-id="7f05c-117">Auto update through MDM</span></span>

## <span data-ttu-id="7f05c-118">ビジネス向け Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="7f05c-118">Microsoft Store for Business</span></span>

<span data-ttu-id="7f05c-119">一般 [法人向け Microsoft ストア](app-deploy-store-business.md) では、ビジネスの意思決定者と管理者が、無料および有料のアプリを検索、入手、管理、配布することができます。</span><span class="sxs-lookup"><span data-stu-id="7f05c-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="7f05c-120">IT 管理者は、1 つのインベントリで Microsoft Store アプリとプライベートな基幹業務アプリを管理でき、必要に応じてライセンスの割り当てや再利用を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7f05c-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and re-use licenses as needed.</span></span> <span data-ttu-id="7f05c-121">詳細については、「 [Microsoft Store For Business を使用するための前提条件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f05c-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>
    
<span data-ttu-id="7f05c-122">ビジネス向けの Microsoft ストアは、次の場合に該当します。</span><span class="sxs-lookup"><span data-stu-id="7f05c-122">The Microsoft Store for Business is applicable for:</span></span> 
* <span data-ttu-id="7f05c-123">一般法人向けまたは基幹業務用のアプリ</span><span class="sxs-lookup"><span data-stu-id="7f05c-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="7f05c-124">MDM の関連付けによる必須アプリケーションの自動インストール</span><span class="sxs-lookup"><span data-stu-id="7f05c-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="7f05c-125">ユーザーが手動でアプリをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="7f05c-125">User manually downloads apps</span></span>
* <span data-ttu-id="7f05c-126">自動更新</span><span class="sxs-lookup"><span data-stu-id="7f05c-126">Auto Update</span></span>

## <span data-ttu-id="7f05c-127">Microsoft Store アプリ</span><span class="sxs-lookup"><span data-stu-id="7f05c-127">Microsoft Store apps</span></span>

<span data-ttu-id="7f05c-128">Microsoft Store では、企業の IT 意思決定者と管理者が公開アプリの検索、入手、管理、配布を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7f05c-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>
    
<span data-ttu-id="7f05c-129">この Microsoft ストアは、次の目的で使用できます。</span><span class="sxs-lookup"><span data-stu-id="7f05c-129">This Microsoft Store is applicable for:</span></span> 
* <span data-ttu-id="7f05c-130">公開アプリのみ</span><span class="sxs-lookup"><span data-stu-id="7f05c-130">Public apps only</span></span>
* <span data-ttu-id="7f05c-131">ユーザーが手動でアプリをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="7f05c-131">User manually downloads apps</span></span>
* <span data-ttu-id="7f05c-132">インターネットに接続されている場合に自動更新する</span><span class="sxs-lookup"><span data-stu-id="7f05c-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="7f05c-133">詳細については、「 [ホログラフィック Store アプリ](https://docs.microsoft.com/hololens/holographic-store-apps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f05c-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <span data-ttu-id="7f05c-134">プロビジョニングパッケージによるインストール</span><span class="sxs-lookup"><span data-stu-id="7f05c-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="7f05c-135">[プロビジョニングパッケージ](app-deploy-provisioning-package.md) では、カスタムまたは基幹業務アプリをインストールできるため、IT 担当者や管理者は、USB 経由でローカルデバイスにアプリをすばやくインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="7f05c-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="7f05c-136">これは、インターネットに接続しなくても、どのような種類の id でも実行できます。</span><span class="sxs-lookup"><span data-stu-id="7f05c-136">This can be done without an internet connection and for any identity type.</span></span>
    
<span data-ttu-id="7f05c-137">プロビジョニングパッケージによるインストールは、次の場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="7f05c-137">Installing via Provisioning Packages is applicable for:</span></span> 
* <span data-ttu-id="7f05c-138">1行の Buisness (非パブリック) アプリ</span><span class="sxs-lookup"><span data-stu-id="7f05c-138">Line of Buisness (non-public) apps</span></span>
* <span data-ttu-id="7f05c-139">公開アプリ (オフラインインストーラーが利用可能な場合)</span><span class="sxs-lookup"><span data-stu-id="7f05c-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="7f05c-140">USB サイドロードのみ</span><span class="sxs-lookup"><span data-stu-id="7f05c-140">USB side-load only</span></span>
* <span data-ttu-id="7f05c-141">自動更新なし (プロビジョニングパッケージ経由で手動で更新する必要があります)</span><span class="sxs-lookup"><span data-stu-id="7f05c-141">No auto update (requires manual updates via Provisioning Package)</span></span>
