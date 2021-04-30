---
title: 概要-アプリ管理
description: モバイルデバイス管理、ビジネス向け Microsoft ストア、およびプロビジョニングパッケージを使用した mixed reality アプリ管理の概要について説明します。
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
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309281"
---
# <a name="app-management-overview"></a><span data-ttu-id="25e42-104">アプリ管理: 概要</span><span class="sxs-lookup"><span data-stu-id="25e42-104">App Management: Overview</span></span>

<span data-ttu-id="25e42-105">アプリは、 **モバイルデバイス管理 (MDM)**、 **Microsoft Store for Business**、 **Microsoft Store** の4つの異なるパスにデプロイすることも、 **プロビジョニング** によってインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="25e42-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="25e42-106">モバイル デバイス管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="25e42-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="25e42-107">MDM ソリューションを使用すると、IT の意思決定者および管理者は、社内の基幹業務アプリをプライベートに自動インストール (プッシュ) したり、ストアを介してユーザーのグループに対してアプリを購入したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="25e42-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="25e42-108">HoloLens デバイスは、 [アプリケーション管理](app-deploy-intune.md)のために Microsoft Endpoint Manager (Intune) で最適に動作します。</span><span class="sxs-lookup"><span data-stu-id="25e42-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="25e42-109">また、Intune では、ポータルサイトダウンロード可能なエクスペリエンスを通じて、IT 管理対象アプリをよりきめ細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="25e42-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="25e42-110">次の手順は、Intune を使用してアプリケーションを管理するユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="25e42-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="25e42-111">Microsoft では、アプリケーションとデバイスの管理に Intune を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="25e42-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="25e42-112">モバイルデバイス管理 (MDM) は、次の場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="25e42-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="25e42-113">MDM の展開 + ポータルサイト</span><span class="sxs-lookup"><span data-stu-id="25e42-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="25e42-114">基幹業務 (非パブリック) アプリ</span><span class="sxs-lookup"><span data-stu-id="25e42-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="25e42-115">ポータルサイトによる使用可能なアプリケーションの手動インストール</span><span class="sxs-lookup"><span data-stu-id="25e42-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="25e42-116">管理者が MDM ポリシーを使用してプッシュする</span><span class="sxs-lookup"><span data-stu-id="25e42-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="25e42-117">MDM を使用した自動更新</span><span class="sxs-lookup"><span data-stu-id="25e42-117">Auto update through MDM</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="25e42-118">ビジネス向け Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="25e42-118">Microsoft Store for Business</span></span>

<span data-ttu-id="25e42-119">[ビジネスの Microsoft Store](app-deploy-store-business.md)により、IT の意思決定者と企業の管理者は、無料および有料のアプリの検索、取得、管理、配布を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="25e42-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="25e42-120">IT 管理者は、1つのインベントリで Microsoft Store アプリとプライベート基幹業務アプリを管理し、必要に応じてライセンスを割り当てて再利用することができます。</span><span class="sxs-lookup"><span data-stu-id="25e42-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="25e42-121">詳細については、「 [ビジネス向け Microsoft Store を使用するための前提条件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25e42-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="25e42-122">ビジネス向け Microsoft Store は次の対象に適用されます。</span><span class="sxs-lookup"><span data-stu-id="25e42-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="25e42-123">パブリックまたは基幹業務アプリ</span><span class="sxs-lookup"><span data-stu-id="25e42-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="25e42-124">MDM アソシエーションを使用した必要なアプリケーションの自動インストール</span><span class="sxs-lookup"><span data-stu-id="25e42-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="25e42-125">ユーザーによるアプリの手動ダウンロード</span><span class="sxs-lookup"><span data-stu-id="25e42-125">User manually downloads apps</span></span>
* <span data-ttu-id="25e42-126">自動更新</span><span class="sxs-lookup"><span data-stu-id="25e42-126">Auto Update</span></span>

## <a name="microsoft-store-apps"></a><span data-ttu-id="25e42-127">Microsoft Store アプリ</span><span class="sxs-lookup"><span data-stu-id="25e42-127">Microsoft Store apps</span></span>

<span data-ttu-id="25e42-128">Microsoft Store は、企業の IT 意思決定者および管理者が、パブリックアプリの検索、取得、管理、配布を行います。</span><span class="sxs-lookup"><span data-stu-id="25e42-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="25e42-129">この Microsoft Store は、次の場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="25e42-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="25e42-130">パブリックアプリのみ</span><span class="sxs-lookup"><span data-stu-id="25e42-130">Public apps only</span></span>
* <span data-ttu-id="25e42-131">ユーザーによるアプリの手動ダウンロード</span><span class="sxs-lookup"><span data-stu-id="25e42-131">User manually downloads apps</span></span>
* <span data-ttu-id="25e42-132">インターネットに接続されている場合は自動更新</span><span class="sxs-lookup"><span data-stu-id="25e42-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="25e42-133">詳細については、 [Holographic ストアアプリ](https://docs.microsoft.com/hololens/holographic-store-apps)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="25e42-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <a name="install-via-provisioning-packages"></a><span data-ttu-id="25e42-134">プロビジョニングパッケージを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="25e42-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="25e42-135">[プロビジョニングパッケージ](app-deploy-provisioning-package.md) を使用すると、カスタムまたは基幹業務アプリをインストールできます。これにより、IT 担当者および管理者は、USB を使用してローカルデバイスにアプリをすばやくインストールできます。</span><span class="sxs-lookup"><span data-stu-id="25e42-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="25e42-136">このインストールは、インターネットに接続せずに、任意の id の種類に対して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="25e42-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="25e42-137">プロビジョニングパッケージを使用したのインストールは、次の場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="25e42-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="25e42-138">基幹業務/自己開発 (非パブリック) アプリ</span><span class="sxs-lookup"><span data-stu-id="25e42-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="25e42-139">パブリックアプリ (オフラインインストーラーが使用可能な場合)</span><span class="sxs-lookup"><span data-stu-id="25e42-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="25e42-140">USB サイドローディングのみ</span><span class="sxs-lookup"><span data-stu-id="25e42-140">USB side-loading only</span></span>
* <span data-ttu-id="25e42-141">自動更新なし (プロビジョニングパッケージを使用した手動更新が必要)</span><span class="sxs-lookup"><span data-stu-id="25e42-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="25e42-142">アプリインストーラーを使用して HoloLens 2 にアプリをインストールする</span><span class="sxs-lookup"><span data-stu-id="25e42-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="25e42-143">アプリの [インストーラー](app-deploy-app-installer.md) を使用すると、ローカルデバイスにアプリをインストールしたり、HoloLens で他のアプリのインストール方法に慣れていない他のユーザーとアプリを共有したりするための、簡単なエクスペリエンスを利用できます。</span><span class="sxs-lookup"><span data-stu-id="25e42-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="25e42-144">これを行うには、開発者モードを有効にしたり、デバイスポータルを使用したりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="25e42-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="25e42-145">これは、完全にビルドされたアプリを配布するための簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="25e42-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="25e42-146">HoloLens を使用して別のユーザーにアプリをデモするだけの場合でも、アプリをデプロイする場合でも、この方法は簡単に機能します。</span><span class="sxs-lookup"><span data-stu-id="25e42-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="25e42-147">アプリインストーラーを使用したのインストールは、次の場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="25e42-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="25e42-148">基幹業務/自己開発 (非パブリック) アプリ</span><span class="sxs-lookup"><span data-stu-id="25e42-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="25e42-149">サイドロードのみ</span><span class="sxs-lookup"><span data-stu-id="25e42-149">Side-load only</span></span>
* <span data-ttu-id="25e42-150">開発者モードまたはデバイスポータルは必要ありません</span><span class="sxs-lookup"><span data-stu-id="25e42-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="25e42-151">エンドユーザーが簡単にインストール</span><span class="sxs-lookup"><span data-stu-id="25e42-151">Easy for end user to install</span></span>
