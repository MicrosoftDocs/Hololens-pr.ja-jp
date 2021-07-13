---
title: 概要 - アプリ管理
description: 概要デバイス管理、ビジネス向け Microsoft ストア、およびプロビジョニング パッケージを使用した Mixed Reality アプリ管理の概要について説明します。
keywords: HoloLens、ユーザー、アカウント、アプリ、アプリケーション管理、
author: evmill
ms.author: v-evmill
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
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635553"
---
# <a name="app-management-overview"></a><span data-ttu-id="0b3cd-104">アプリ管理: 概要</span><span class="sxs-lookup"><span data-stu-id="0b3cd-104">App Management: Overview</span></span>

<span data-ttu-id="0b3cd-105">アプリは **、Mobile デバイス管理 (MDM)** **、ビジネス向け Microsoft Store** **、Microsoft Store** の 4 つの異なるパスにデプロイできます。または、プロビジョニング を使用してアプリを **インストールします**。</span><span class="sxs-lookup"><span data-stu-id="0b3cd-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="0b3cd-106">モバイル デバイス管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="0b3cd-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="0b3cd-107">MDM ソリューションを使用すると、IT の意思決定者と管理者は、企業内の業務アプリを非公開で自動インストール (プッシュ) したり、ユーザー グループのストアを通じてアプリを購入したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="0b3cd-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="0b3cd-108">HoloLensデバイスは、アプリケーション管理のために Microsoft エンドポイント マネージャー (Intune) で最適[に動作します](app-deploy-intune.md)。</span><span class="sxs-lookup"><span data-stu-id="0b3cd-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="0b3cd-109">Intune では、ダウンロード可能なエクスペリエンスを通じて、IT で管理されたアプリをユーザーポータル サイト制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="0b3cd-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="0b3cd-110">次の手順は、Intune でアプリケーションを管理するユーザー向けです。</span><span class="sxs-lookup"><span data-stu-id="0b3cd-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="0b3cd-111">Microsoft では、アプリケーションとデバイスの管理に Intune を使用する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0b3cd-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="0b3cd-112">モバイル デバイス管理 (MDM) は次の場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0b3cd-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="0b3cd-113">MDM のデプロイ + ポータル サイト</span><span class="sxs-lookup"><span data-stu-id="0b3cd-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="0b3cd-114">Line of Business (非パブリック) アプリ</span><span class="sxs-lookup"><span data-stu-id="0b3cd-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="0b3cd-115">アプリケーションを使用して使用可能なアプリケーションを手動ポータル サイト</span><span class="sxs-lookup"><span data-stu-id="0b3cd-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="0b3cd-116">MDM ポリシーによる管理者プッシュ</span><span class="sxs-lookup"><span data-stu-id="0b3cd-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="0b3cd-117">MDM による自動更新</span><span class="sxs-lookup"><span data-stu-id="0b3cd-117">Auto update through MDM</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="0b3cd-118">ビジネス向け Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="0b3cd-118">Microsoft Store for Business</span></span>

<span data-ttu-id="0b3cd-119">この[ビジネス向け Microsoft Store、IT](app-deploy-store-business.md)の意思決定者と企業の管理者が、無料アプリと有料アプリを検索、取得、管理、配布できます。</span><span class="sxs-lookup"><span data-stu-id="0b3cd-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="0b3cd-120">IT 管理者は、1 Microsoft Storeアプリとプライベートの業務アプリを 1 つのインベントリで管理し、必要に応じてライセンスを割り当て、再利用することができます。</span><span class="sxs-lookup"><span data-stu-id="0b3cd-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="0b3cd-121">詳細については、「 を使用するための[前提条件」を参照ビジネス向け Microsoft Store。](/microsoft-store/prerequisites-microsoft-store-for-business)</span><span class="sxs-lookup"><span data-stu-id="0b3cd-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="0b3cd-122">このビジネス向け Microsoft Storeは次の場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0b3cd-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="0b3cd-123">パブリック アプリまたは Line of Business アプリ</span><span class="sxs-lookup"><span data-stu-id="0b3cd-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="0b3cd-124">MDM 関連付けを使用した必要なアプリケーションの自動インストール</span><span class="sxs-lookup"><span data-stu-id="0b3cd-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="0b3cd-125">ユーザーがアプリを手動でダウンロードする</span><span class="sxs-lookup"><span data-stu-id="0b3cd-125">User manually downloads apps</span></span>
* <span data-ttu-id="0b3cd-126">自動更新</span><span class="sxs-lookup"><span data-stu-id="0b3cd-126">Auto Update</span></span>

## <a name="microsoft-store-apps"></a><span data-ttu-id="0b3cd-127">Microsoft Store アプリ</span><span class="sxs-lookup"><span data-stu-id="0b3cd-127">Microsoft Store apps</span></span>

<span data-ttu-id="0b3cd-128">このMicrosoft Store、IT の意思決定者と企業の管理者が、パブリック アプリの検索、取得、管理、配布を行います。</span><span class="sxs-lookup"><span data-stu-id="0b3cd-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="0b3cd-129">このMicrosoft Storeは次の場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0b3cd-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="0b3cd-130">パブリック アプリのみ</span><span class="sxs-lookup"><span data-stu-id="0b3cd-130">Public apps only</span></span>
* <span data-ttu-id="0b3cd-131">ユーザーがアプリを手動でダウンロードする</span><span class="sxs-lookup"><span data-stu-id="0b3cd-131">User manually downloads apps</span></span>
* <span data-ttu-id="0b3cd-132">インターネットに接続されている場合の自動更新</span><span class="sxs-lookup"><span data-stu-id="0b3cd-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="0b3cd-133">詳細については [、「Holographic Store Apps 」を参照してください](/hololens/holographic-store-apps)。</span><span class="sxs-lookup"><span data-stu-id="0b3cd-133">For more information, visit [Holographic Store Apps](/hololens/holographic-store-apps).</span></span>

## <a name="install-via-provisioning-packages"></a><span data-ttu-id="0b3cd-134">プロビジョニング パッケージを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="0b3cd-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="0b3cd-135">[プロビジョニング パッケージを](app-deploy-provisioning-package.md) 使用すると、カスタムアプリまたは Line of Business アプリをインストールできます。IT のプロや管理者は、USB 経由でローカル デバイスにアプリをすばやくインストールできます。</span><span class="sxs-lookup"><span data-stu-id="0b3cd-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="0b3cd-136">このインストールは、インターネットに接続せずに、任意の ID の種類に対して実行できます。</span><span class="sxs-lookup"><span data-stu-id="0b3cd-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="0b3cd-137">プロビジョニング パッケージを使用したインストールは、次の場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0b3cd-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="0b3cd-138">Line of Business / 自己開発 (非パブリック) アプリ</span><span class="sxs-lookup"><span data-stu-id="0b3cd-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="0b3cd-139">パブリック アプリ (オフライン インストーラーが使用可能な場合)</span><span class="sxs-lookup"><span data-stu-id="0b3cd-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="0b3cd-140">USB サイドローディングのみ</span><span class="sxs-lookup"><span data-stu-id="0b3cd-140">USB side-loading only</span></span>
* <span data-ttu-id="0b3cd-141">自動更新なし (プロビジョニング パッケージを使用した手動更新が必要)</span><span class="sxs-lookup"><span data-stu-id="0b3cd-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="0b3cd-142">HoloLens 2 経由でアプリを アプリ インストーラー</span><span class="sxs-lookup"><span data-stu-id="0b3cd-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="0b3cd-143">[アプリ インストーラー](app-deploy-app-installer.md)ユーザーは、ローカル デバイスにアプリをインストールしたり、HoloLens で他のアプリのインストール方法に慣れていない他のユーザーとアプリを共有したりする簡単なエクスペリエンスを利用できます。</span><span class="sxs-lookup"><span data-stu-id="0b3cd-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="0b3cd-144">これは、開発者モードを有効にしたり、開発者モードを使用したりすることなくデバイス ポータル。</span><span class="sxs-lookup"><span data-stu-id="0b3cd-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="0b3cd-145">これは、完全に構築されたアプリを配布する簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="0b3cd-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="0b3cd-146">HoloLens を使用してアプリを別のユーザーにデモする場合や、アプリをデプロイする場合は、この方法が簡単に機能します。</span><span class="sxs-lookup"><span data-stu-id="0b3cd-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="0b3cd-147">次のアプリ インストーラーを使用してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="0b3cd-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="0b3cd-148">Line of Business / Self developed (非パブリック) アプリ</span><span class="sxs-lookup"><span data-stu-id="0b3cd-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="0b3cd-149">サイドロードのみ</span><span class="sxs-lookup"><span data-stu-id="0b3cd-149">Side-load only</span></span>
* <span data-ttu-id="0b3cd-150">開発者モードまたはデバイス ポータルは必要ない</span><span class="sxs-lookup"><span data-stu-id="0b3cd-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="0b3cd-151">エンド ユーザーが簡単にインストールできる</span><span class="sxs-lookup"><span data-stu-id="0b3cd-151">Easy for end user to install</span></span>
