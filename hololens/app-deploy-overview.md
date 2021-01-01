---
title: 概要 - アプリ管理
description: アプリ, 管理, アプリの管理
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
ms.openlocfilehash: 2ca0b05b6ed61ddce327a44fedbbcf280b33a106
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252668"
---
# <span data-ttu-id="e25a0-104">アプリ管理の概要</span><span class="sxs-lookup"><span data-stu-id="e25a0-104">App Management: Overview</span></span>

<span data-ttu-id="e25a0-105">アプリは、モバイル デバイス管理 **(MDM)、** ビジネス向け **Microsoft Store、Microsoft** **Store**の 4 つの異なるパスに展開するか、プロビジョニングを使用してアプリを **インストールすることで展開できます**。</span><span class="sxs-lookup"><span data-stu-id="e25a0-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <span data-ttu-id="e25a0-106">モバイル デバイス管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="e25a0-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="e25a0-107">MDM ソリューションを使用すると、IT の意思決定者と管理者は、企業内アプリ、業務アプリをプライベートに自動インストール (プッシュ) したり、ユーザー グループのストアを通じてアプリを購入することができます。</span><span class="sxs-lookup"><span data-stu-id="e25a0-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="e25a0-108">HoloLens デバイスは、Microsoft Endpoint Manager (Intune) を使用してアプリケーション管理を行う場合に最適 [です](app-deploy-intune.md)。</span><span class="sxs-lookup"><span data-stu-id="e25a0-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="e25a0-109">Intune では、ポータル サイトのダウンロード可能なエクスペリエンスを通じて、ユーザーが IT 管理アプリを細かく制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="e25a0-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="e25a0-110">次の手順は、Intune でアプリケーションを管理するユーザー向けです。</span><span class="sxs-lookup"><span data-stu-id="e25a0-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="e25a0-111">Microsoft では、アプリケーションとデバイスの管理に Intune を使用する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e25a0-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="e25a0-112">モバイル デバイス管理 (MDM) は、次の場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e25a0-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="e25a0-113">MDM の展開 + ポータル サイト</span><span class="sxs-lookup"><span data-stu-id="e25a0-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="e25a0-114">Line of Business (非パブリック) アプリ</span><span class="sxs-lookup"><span data-stu-id="e25a0-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="e25a0-115">ポータル サイトを使用して利用可能なアプリケーションを手動でインストールする</span><span class="sxs-lookup"><span data-stu-id="e25a0-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="e25a0-116">管理者による MDM ポリシーのプッシュ</span><span class="sxs-lookup"><span data-stu-id="e25a0-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="e25a0-117">MDM による自動更新</span><span class="sxs-lookup"><span data-stu-id="e25a0-117">Auto update through MDM</span></span>

## <span data-ttu-id="e25a0-118">ビジネス向け Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="e25a0-118">Microsoft Store for Business</span></span>

<span data-ttu-id="e25a0-119">ビジネス [向け Microsoft Store](app-deploy-store-business.md) では、IT の意思決定者と管理者が無料アプリと有料アプリを検索、取得、管理、配布できます。</span><span class="sxs-lookup"><span data-stu-id="e25a0-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="e25a0-120">IT 管理者は、Microsoft Store アプリとプライベートな業務アプリを 1 つのインベントリで管理し、必要に応じてライセンスを割り当て、再利用できます。</span><span class="sxs-lookup"><span data-stu-id="e25a0-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="e25a0-121">詳細については、ビジネス向け [Microsoft Store を使用するための前提条件に関するページを参照してください](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)。</span><span class="sxs-lookup"><span data-stu-id="e25a0-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="e25a0-122">ビジネス向け Microsoft Store は、次の対象に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e25a0-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="e25a0-123">パブリック アプリまたは Line of Business アプリ</span><span class="sxs-lookup"><span data-stu-id="e25a0-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="e25a0-124">MDM 関連付けを使用した必要なアプリケーションの自動インストール</span><span class="sxs-lookup"><span data-stu-id="e25a0-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="e25a0-125">ユーザーがアプリを手動でダウンロードする</span><span class="sxs-lookup"><span data-stu-id="e25a0-125">User manually downloads apps</span></span>
* <span data-ttu-id="e25a0-126">自動更新</span><span class="sxs-lookup"><span data-stu-id="e25a0-126">Auto Update</span></span>

## <span data-ttu-id="e25a0-127">Microsoft Store アプリ</span><span class="sxs-lookup"><span data-stu-id="e25a0-127">Microsoft Store apps</span></span>

<span data-ttu-id="e25a0-128">Microsoft Store では、企業の IT 意思決定者と管理者がパブリック アプリの検索、取得、管理、配布を行います。</span><span class="sxs-lookup"><span data-stu-id="e25a0-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="e25a0-129">この Microsoft Store は、次の対象に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e25a0-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="e25a0-130">パブリック アプリのみ</span><span class="sxs-lookup"><span data-stu-id="e25a0-130">Public apps only</span></span>
* <span data-ttu-id="e25a0-131">ユーザーがアプリを手動でダウンロードする</span><span class="sxs-lookup"><span data-stu-id="e25a0-131">User manually downloads apps</span></span>
* <span data-ttu-id="e25a0-132">インターネットに接続されている場合の自動更新</span><span class="sxs-lookup"><span data-stu-id="e25a0-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="e25a0-133">詳しくは [、Holographic ストア アプリに関するページをご覧ください](https://docs.microsoft.com/hololens/holographic-store-apps)。</span><span class="sxs-lookup"><span data-stu-id="e25a0-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <span data-ttu-id="e25a0-134">プロビジョニング パッケージを使用してインストールする</span><span class="sxs-lookup"><span data-stu-id="e25a0-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="e25a0-135">[プロビジョニング パッケージを](app-deploy-provisioning-package.md) 使用すると、カスタム アプリまたは Line of Business アプリをインストールでき、IT 管理者は USB 経由でローカル デバイスにアプリをすばやくインストールできます。</span><span class="sxs-lookup"><span data-stu-id="e25a0-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="e25a0-136">このインストールは、インターネットに接続せずに、任意の ID の種類に対して実行できます。</span><span class="sxs-lookup"><span data-stu-id="e25a0-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="e25a0-137">プロビジョニング パッケージを使用したインストールは、次の場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e25a0-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="e25a0-138">Line of Business / 自己開発 (非パブリック) アプリ</span><span class="sxs-lookup"><span data-stu-id="e25a0-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="e25a0-139">パブリック アプリ (オフライン インストーラーが利用可能な場合)</span><span class="sxs-lookup"><span data-stu-id="e25a0-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="e25a0-140">USB サイドローディングのみ</span><span class="sxs-lookup"><span data-stu-id="e25a0-140">USB side-loading only</span></span>
* <span data-ttu-id="e25a0-141">自動更新なし (プロビジョニング パッケージによる手動更新が必要)</span><span class="sxs-lookup"><span data-stu-id="e25a0-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <span data-ttu-id="e25a0-142">アプリ インストーラーを使用して HoloLens 2 にアプリをインストールする</span><span class="sxs-lookup"><span data-stu-id="e25a0-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="e25a0-143">アプリ[](app-deploy-app-installer.md)インストーラーを使用すると、ローカル デバイスにアプリをインストールしたり、HoloLens 上の他のアプリのインストール方法に慣れていない他のユーザーとアプリを共有したりする操作が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="e25a0-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="e25a0-144">これは、開発者モードを有効にしたり、Device Portal を使用したりすることなく実行できます。</span><span class="sxs-lookup"><span data-stu-id="e25a0-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="e25a0-145">これは、完全にビルドされたアプリを配布する簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="e25a0-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="e25a0-146">HoloLens を使って他のユーザーにアプリをデモする場合や、アプリを展開する場合に関係なく、このメソッドは簡単に機能します。</span><span class="sxs-lookup"><span data-stu-id="e25a0-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="e25a0-147">アプリ インストーラーを使用したインストールは、次の場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e25a0-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="e25a0-148">Line of Business / Self developed (non-public) apps</span><span class="sxs-lookup"><span data-stu-id="e25a0-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="e25a0-149">サイドロードのみ</span><span class="sxs-lookup"><span data-stu-id="e25a0-149">Side-load only</span></span>
* <span data-ttu-id="e25a0-150">開発者モードや Device Portal は不要</span><span class="sxs-lookup"><span data-stu-id="e25a0-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="e25a0-151">エンド ユーザーが簡単にインストールできる</span><span class="sxs-lookup"><span data-stu-id="e25a0-151">Easy for end user to install</span></span>
