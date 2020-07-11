---
title: HoloLens の更新プログラムの管理
description: 管理者は、モバイル デバイス管理を使用して HoloLens デバイスの更新プログラムを管理できます。
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 07/09/2020
ms.reviewer: jarrettr
manager: jarrettr
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 384d33e72effd298e1874e5723e9c418061c3287
ms.sourcegitcommit: 0d4e67d8e21d34885e0eaee08646e28426c4f641
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2020
ms.locfileid: "10861910"
---
# <span data-ttu-id="7a2e7-103">HoloLens の更新プログラムの管理</span><span class="sxs-lookup"><span data-stu-id="7a2e7-103">Manage HoloLens updates</span></span>

<span data-ttu-id="7a2e7-104">HoloLens は、他の Windows 10 デバイスと同じように、Windows Update を使用します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-104">HoloLens uses Windows Update in the same manner as other Windows 10 devices.</span></span> <span data-ttu-id="7a2e7-105">更新プログラムが利用可能な場合は、次にデバイスに電源が入りインターネットに接続されたときに、自動的にダウンロードおよびインストールされます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-105">When an update is available, it is automatically downloaded and installed the next time that your device is plugged in and connected to the internet.</span></span> <span data-ttu-id="7a2e7-106">この記事では、エンタープライズ環境またはその他の管理環境で更新を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-106">This article describes how to manage updates in an enterprise or other managed environment.</span></span> <span data-ttu-id="7a2e7-107">個別の HoloLens デバイスへの更新プログラムを管理する方法については、「[HoloLens を更新する](hololens-update-hololens.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-107">For information about how to manage updates to individual HoloLens devices, see [Update HoloLens](hololens-update-hololens.md).</span></span>

## <span data-ttu-id="7a2e7-108">更新を自動的に管理する</span><span class="sxs-lookup"><span data-stu-id="7a2e7-108">Manage updates automatically</span></span>

### <span data-ttu-id="7a2e7-109">Windows Update for Business を使った更新プログラムの管理</span><span class="sxs-lookup"><span data-stu-id="7a2e7-109">Managing updates by using Windows Update for Business</span></span>

<span data-ttu-id="7a2e7-110">Windows Holographic for Business では、[Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) を使用して、更新を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-110">Windows Holographic for Business can use [Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) to manage updates.</span></span> <span data-ttu-id="7a2e7-111">すべての HoloLens 2 デバイスは、Windows Holographic for Business を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-111">All HoloLens 2 devices can use Windows Holographic for Business.</span></span> <span data-ttu-id="7a2e7-112">Windows Holographic for Business ビルド 10.0.18362.1042 またはそれ以降のビルドを使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-112">Make sure that they use Windows Holographic for Business build 10.0.18362.1042 or a later build.</span></span> <span data-ttu-id="7a2e7-113">HoloLens (第 1 世代) のデバイスを使用している場合は、更新を管理するために [Windows Holographic for Business に更新する](hololens1-upgrade-enterprise.md)必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-113">If you have HoloLens (1st gen) devices, you have to [upgrade them to Windows Holographic for Business](hololens1-upgrade-enterprise.md) in order to manage their updates.</span></span>

<span data-ttu-id="7a2e7-114">Windows Update for Business により、HoloLens デバイスを Windows Update サービスに直接接続します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-114">Windows Update for Business connects HoloLens devices directly to the Windows Update service.</span></span> <span data-ttu-id="7a2e7-115">Windows Update for Business を使用すると、更新プロセスの複数の側面として&mdash;いつ、どのデバイスで、どの更新プログラムを取得するか、などを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-115">By using Windows Update for Business, you can control multiple aspects of the update process&mdash;that is, which devices get which updates at what time.</span></span> <span data-ttu-id="7a2e7-116">たとえば、テスト用にデバイスのサブセットに更新プログラムをロールアウトし、後ほど残りのデバイスに更新プログラムをロールアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-116">For example, you can roll out updates to a subset of devices for testing, then later roll out updates to the remaining devices.</span></span> <span data-ttu-id="7a2e7-117">または、更新プログラムの種類によって、異なる更新スケジュールを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-117">Or, you can define different update schedules for different types of updates.</span></span>

> [!NOTE]  
> <span data-ttu-id="7a2e7-118">HoloLens デバイスでは、機能更新プログラム (年に 2 回リリース) と、品質更新プログラム (月ごとまたは必要に応じてリリースされ、重要なセキュリティ更新プログラムを含む) を、自動的に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-118">For HoloLens devices, you can automatically manage feature updates (released two times a year) and quality updates (released monthly or as required, including critical security updates).</span></span> <span data-ttu-id="7a2e7-119">更新プログラムの種類の詳細については、「[Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business) で管理される更新プログラムの種類」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-119">For more information about update types, see [Types of updates managed by Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).</span></span>

<span data-ttu-id="7a2e7-120">HoloLens 用の Windows Update for Business の設定は、Microsoft Intune などのモバイル デバイス管理 (MDM) ソリューションのポリシーを使用して構成することができます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-120">You can configure Windows Update for Business settings for HoloLens by using policies in a Mobile Device Management (MDM) solution such as Microsoft Intune.</span></span>

### <span data-ttu-id="7a2e7-121">Microsoft Intune を使った、 Windows Update for Business の管理</span><span class="sxs-lookup"><span data-stu-id="7a2e7-121">Managing Windows Update for Business by using Microsoft Intune</span></span>

<span data-ttu-id="7a2e7-122">Intune を使用して Windows Update for Business を構成する方法の詳細については、「[Windows 10 のソフトウェア更新プログラムを Intune で管理する](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-122">For a detailed discussion about how to use Intune to configure Windows Update for Business, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="7a2e7-123">HoloLens でサポートされている特定の Intune 機能の詳細については、「[HoloLens がをサポートする Intune の更新プログラム管理機能](#intune-update-management-functions-that-hololens-supports)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-123">For more information about the specific Intune functionality that HoloLens supports, see [Intune update management functions that HoloLens supports](#intune-update-management-functions-that-hololens-supports).</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="7a2e7-124">Intune には、更新を管理するために、*Windows 10 更新リング* と *Windows 10 機能更新プログラム*の 2 種類のポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-124">Intune provides two policy types for managing updates: *Windows 10 update ring* and *Windows 10 feature update*.</span></span> <span data-ttu-id="7a2e7-125">Windows 10 機能更新プログラムのポリシーの種類は、現時点ではパブリック プレビュー段階であり、HoloLens でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-125">The Windows 10 feature update policy type is in public preview at this time and is not supported for HoloLens.</span></span>
>  
> <span data-ttu-id="7a2e7-126">Windows 10 更新リング ポリシーを使用して HoloLens 2 の更新を管理できます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-126">You can use Windows 10 update ring policies to manage HoloLens 2 updates.</span></span>

### <span data-ttu-id="7a2e7-127">HoloLens 2 または HoloLens (第 1 世代) の更新ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="7a2e7-127">Configure update policies for HoloLens 2 or HoloLens (1st gen)</span></span>

<span data-ttu-id="7a2e7-128">このセクションでは、HoloLens 2 または HoloLens (第 1 世代) の更新を管理するのに使用できるポリシーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-128">This section describes the policies that you can use to manage updates for either HoloLens 2 or HoloLens (1st gen).</span></span> <span data-ttu-id="7a2e7-129">HoloLens 2 向けのその他の機能の詳細については、「[HoloLens 2 の更新プログラムのロールアウトについての計画と構成](#plan-and-configure-update-rollouts-for-hololens-2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-129">For more information about the functionality that is available for HoloLens 2, see [Plan and configure update rollouts for HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).</span></span>

<span data-ttu-id="7a2e7-130">[ポリシー CSP-更新プログラム](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) は、Windows Update for Business を構成するポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-130">[Policy CSP - Update](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) defines the policies that configure Windows Update for Business.</span></span>

> [!NOTE]  
> <span data-ttu-id="7a2e7-131">HoloLens の特定のエディションでサポートされているポリシー構成サービス プロバイダー (CSP) の一覧については、「[HoloLens デバイスでサポートされているポリシーの CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-131">For a list of specific policy configuration service providers (CSPs) that are supported by specific editions of HoloLens, see [Policy CSPs supported by HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices).</span></span>

#### <span data-ttu-id="7a2e7-132">更新プログラムの自動チェックを構成する</span><span class="sxs-lookup"><span data-stu-id="7a2e7-132">Configure automatic checks for updates</span></span>

<span data-ttu-id="7a2e7-133">**Update/AllowAutoUpdate** ポリシーを使用して、更新プログラムのスキャン、ダウンロード、インストールなど、自動更新の動作を管理できます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-133">You can use the **Update/AllowAutoUpdate** policy to manage automatic update behavior, such as scanning, downloading, and installing updates.</span></span> <span data-ttu-id="7a2e7-134">このポリシーの使用可能な設定の詳細については、「[Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-134">For more information about the available settings for this policy, see [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).</span></span>

> [!NOTE]  
> <span data-ttu-id="7a2e7-135">Microsoft Intune では、**自動更新動作**を使用して、このポリシーを変更できます </span><span class="sxs-lookup"><span data-stu-id="7a2e7-135">In Microsoft Intune, you can use **Automatic Update Behavior** to change this policy.</span></span> <span data-ttu-id="7a2e7-136">詳細については、「[Intune での Windows 10 のソフトウェア更新プログラムの管理](https://docs.microsoft.com/intune/windows-update-for-business-configure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-136">For more information, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span></span>

#### <span data-ttu-id="7a2e7-137">更新スケジュールを構成する</span><span class="sxs-lookup"><span data-stu-id="7a2e7-137">Configure an update schedule</span></span>

<span data-ttu-id="7a2e7-138">更新プログラムを適用する方法とタイミングを構成するには、次のポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-138">To configure how and when updates are applied, use the following policies:</span></span>

- [<span data-ttu-id="7a2e7-139">Update/ScheduledInstallDay</span><span class="sxs-lookup"><span data-stu-id="7a2e7-139">Update/ScheduledInstallDay</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - <span data-ttu-id="7a2e7-140">値: **0**–**7** (0 = 毎日、1 = 日曜日、7 = 土曜日)</span><span class="sxs-lookup"><span data-stu-id="7a2e7-140">Values: **0**–**7** (0 = every day, 1 = Sunday, 7 = Saturday)</span></span>
  - <span data-ttu-id="7a2e7-141">既定値: **0** (毎日)</span><span class="sxs-lookup"><span data-stu-id="7a2e7-141">Default value: **0** (every day)</span></span>
- [<span data-ttu-id="7a2e7-142">Update/ScheduledInstallTime</span><span class="sxs-lookup"><span data-stu-id="7a2e7-142">Update/ScheduledInstallTime</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - <span data-ttu-id="7a2e7-143">Values: 0–23 (0 = 午前 0:00、23 = 午後 11:00)</span><span class="sxs-lookup"><span data-stu-id="7a2e7-143">Values: 0–23 (0 = midnight, 23 = 11 PM)</span></span>
  - <span data-ttu-id="7a2e7-144">既定値: 午後 3:00</span><span class="sxs-lookup"><span data-stu-id="7a2e7-144">Default value: 3 PM</span></span>

#### <span data-ttu-id="7a2e7-145">Windows 10 バージョン 1607 を実行するデバイスのみ</span><span class="sxs-lookup"><span data-stu-id="7a2e7-145">For devices that run Windows 10, version 1607 only</span></span>

<span data-ttu-id="7a2e7-146">以下の更新ポリシーを使用して、Windows Update からではなく Windows Server Update Services (WSUS) から更新プログラムを取得するようにデバイスを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-146">You can use the following update policies to configure devices to get updates from Windows Server Update Service (WSUS), instead of from Windows Update:</span></span>

- [<span data-ttu-id="7a2e7-147">Update/AllowUpdateService</span><span class="sxs-lookup"><span data-stu-id="7a2e7-147">Update/AllowUpdateService</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [<span data-ttu-id="7a2e7-148">Update/RequireUpdateApproval</span><span class="sxs-lookup"><span data-stu-id="7a2e7-148">Update/RequireUpdateApproval</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [<span data-ttu-id="7a2e7-149">Update/UpdateServiceUrl</span><span class="sxs-lookup"><span data-stu-id="7a2e7-149">Update/UpdateServiceUrl</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <span data-ttu-id="7a2e7-150">HoloLens 2 の更新プログラムのロールアウトについての計画と構成</span><span class="sxs-lookup"><span data-stu-id="7a2e7-150">Plan and configure update rollouts for HoloLens 2</span></span>

<span data-ttu-id="7a2e7-151">HoloLens 2 は、HoloLens (第 1 世代) よりも多くの更新の自動化機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-151">HoloLens 2 supports more update automation features than HoloLens (1st gen) does.</span></span> <span data-ttu-id="7a2e7-152">Microsoft Intune を使用して Windows Update for Business のポリシーを管理する場合は、特にそうです。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-152">This is especially true if you use Microsoft Intune to manage Windows Update for Business policies.</span></span> <span data-ttu-id="7a2e7-153">これらの機能により、組織全体で行う更新プログラムのロールアウトを、より簡単に計画し、実装できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-153">These features make it easier for you to plan and implement update rollouts across your organization.</span></span>

#### <span data-ttu-id="7a2e7-154">更新戦略を計画する</span><span class="sxs-lookup"><span data-stu-id="7a2e7-154">Plan the update strategy</span></span>

<span data-ttu-id="7a2e7-155">Windows Updates for Business は繰延ポリシーをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-155">Windows Updates for Business supports deferral policies.</span></span> <span data-ttu-id="7a2e7-156">繰延ポリシーを使用して、更新プログラムがリリースされてから、どのぐらいの時間でデバイスにその更新プログラムをインストールするかを定義できます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-156">After Microsoft releases an update, you can use a deferral policy to define how long to wait before installing that update on devices.</span></span> <span data-ttu-id="7a2e7-157">異なる繰延ポリシーを使用して、デバイスのサブセット (*更新リング*とも呼ばれる) を関連付けることにより、組織の更新プログラムのロールアウト戦略を調整できます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-157">By associating subsets of your devices (also known as *update rings*) with different deferral policies, you can coordinate an update rollout strategy for your organization.</span></span>

<span data-ttu-id="7a2e7-158">たとえば、組織で 1,000 台のデバイスを所有していて、それを 5 つのウェーブで更新しなければならないとします。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-158">For example, consider an organization that has 1,000 devices, and has to update the devices in five waves.</span></span> <span data-ttu-id="7a2e7-159">組織では、次の表に示すような 5 つの更新リングを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-159">The organization can create five update rings, as shown in the following table.</span></span>

|<span data-ttu-id="7a2e7-160">Group</span><span class="sxs-lookup"><span data-stu-id="7a2e7-160">Group</span></span> |<span data-ttu-id="7a2e7-161">デバイスの数</span><span class="sxs-lookup"><span data-stu-id="7a2e7-161">Number of devices</span></span> |<span data-ttu-id="7a2e7-162">繰延 (日数)</span><span class="sxs-lookup"><span data-stu-id="7a2e7-162">Deferral (days)</span></span> |
| ---| :---: | :---: |
|<span data-ttu-id="7a2e7-163">グループ 1 (IT スタッフ)</span><span class="sxs-lookup"><span data-stu-id="7a2e7-163">Grp 1 (IT staff)</span></span> |<span data-ttu-id="7a2e7-164">5</span><span class="sxs-lookup"><span data-stu-id="7a2e7-164">5</span></span> |<span data-ttu-id="7a2e7-165">0</span><span class="sxs-lookup"><span data-stu-id="7a2e7-165">0</span></span> |
|<span data-ttu-id="7a2e7-166">グループ 2 (早期導入者)</span><span class="sxs-lookup"><span data-stu-id="7a2e7-166">Grp 2 (early adopters)</span></span> |<span data-ttu-id="7a2e7-167">50</span><span class="sxs-lookup"><span data-stu-id="7a2e7-167">50</span></span> |<span data-ttu-id="7a2e7-168">60</span><span class="sxs-lookup"><span data-stu-id="7a2e7-168">60</span></span> |
|<span data-ttu-id="7a2e7-169">グループ 3 (メイン 1)</span><span class="sxs-lookup"><span data-stu-id="7a2e7-169">Grp 3 (main 1)</span></span> |<span data-ttu-id="7a2e7-170">250</span><span class="sxs-lookup"><span data-stu-id="7a2e7-170">250</span></span> |<span data-ttu-id="7a2e7-171">120</span><span class="sxs-lookup"><span data-stu-id="7a2e7-171">120</span></span> |
|<span data-ttu-id="7a2e7-172">グループ 4 (メイン 2)</span><span class="sxs-lookup"><span data-stu-id="7a2e7-172">Grp 4 (main 2)</span></span> |<span data-ttu-id="7a2e7-173">300</span><span class="sxs-lookup"><span data-stu-id="7a2e7-173">300</span></span> |<span data-ttu-id="7a2e7-174">150</span><span class="sxs-lookup"><span data-stu-id="7a2e7-174">150</span></span> |
|<span data-ttu-id="7a2e7-175">グループ 5 (メイン 3)</span><span class="sxs-lookup"><span data-stu-id="7a2e7-175">Grp 5 (main 3)</span></span> |<span data-ttu-id="7a2e7-176">395</span><span class="sxs-lookup"><span data-stu-id="7a2e7-176">395</span></span> |<span data-ttu-id="7a2e7-177">180</span><span class="sxs-lookup"><span data-stu-id="7a2e7-177">180</span></span> |

<span data-ttu-id="7a2e7-178">時間の経過と共に組織全体にロールアウトする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-178">Here's how the rollout progresses over time to the whole organization.</span></span>

![更新プログラムを展開するタイムライン](./images/hololens-updates-timeline.png)

#### <span data-ttu-id="7a2e7-180">更新プログラムの繰延ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="7a2e7-180">Configure an update deferral policy</span></span>

<span data-ttu-id="7a2e7-181">繰延ポリシーにより、更新プログラムが入手可能になった日から更新プログラムをデバイスに提供する日までの日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-181">A deferral policy specifies the number of days between the date on which an update becomes available and the date on which the update is offered to a device.</span></span>

<span data-ttu-id="7a2e7-182">機能更新プログラムと品質更新プログラムに、異なる繰延を構成できます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-182">You can configure different deferrals for feature updates and quality updates.</span></span> <span data-ttu-id="7a2e7-183">次の表で、それぞれの種類に使える特定のポリシーと、それぞれの繰延の最大日数を示します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-183">The following table lists the specific policies to use for each type, and the maximum deferral for each.</span></span>

|<span data-ttu-id="7a2e7-184">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="7a2e7-184">Category</span></span> |<span data-ttu-id="7a2e7-185">ポリシー</span><span class="sxs-lookup"><span data-stu-id="7a2e7-185">Policy</span></span> |<span data-ttu-id="7a2e7-186">保留の最長期間</span><span class="sxs-lookup"><span data-stu-id="7a2e7-186">Maximum deferral</span></span> |
| --- | --- | --- |
|<span data-ttu-id="7a2e7-187">機能更新プログラム</span><span class="sxs-lookup"><span data-stu-id="7a2e7-187">Feature updates</span></span> |<span data-ttu-id="7a2e7-188">DeferFeatureUpdatesPeriodInDays</span><span class="sxs-lookup"><span data-stu-id="7a2e7-188">DeferFeatureUpdatesPeriodInDays</span></span> |<span data-ttu-id="7a2e7-189">365 日</span><span class="sxs-lookup"><span data-stu-id="7a2e7-189">365 days</span></span> |
|<span data-ttu-id="7a2e7-190">品質更新プログラム</span><span class="sxs-lookup"><span data-stu-id="7a2e7-190">Quality updates</span></span> |<span data-ttu-id="7a2e7-191">DeferQualityUpdatesPeriodInDays</span><span class="sxs-lookup"><span data-stu-id="7a2e7-191">DeferQualityUpdatesPeriodInDays</span></span> |<span data-ttu-id="7a2e7-192">30 日</span><span class="sxs-lookup"><span data-stu-id="7a2e7-192">30 days</span></span> |

#### <span data-ttu-id="7a2e7-193">HoloLens でサポートされている Intune 更新プログラム管理機能</span><span class="sxs-lookup"><span data-stu-id="7a2e7-193">Intune update management functions that HoloLens supports</span></span>

<span data-ttu-id="7a2e7-194">HoloLens の更新プログラムを管理するには、次の Intune 更新プログラム管理機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-194">You can use the following Intune update management functions to manage updates for HoloLens.</span></span>

- <span data-ttu-id="7a2e7-195">**作成**と**割り当て**:　これらの関数は、Windows 10 更新プログラム リングを、更新リングの一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-195">**Create** and **Assign**: These functions add a Windows 10 update ring to the list of update rings.</span></span> <span data-ttu-id="7a2e7-196">詳しくは、「[更新リングを作成して割り当てる](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-196">For more information, see [Create and assign update rings](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).</span></span>

- <span data-ttu-id="7a2e7-197">**一時停止**:機能更新プログラムまたは品質更新プログラムを展開するときに問題が発生した場合は、更新を (指定した日付から) 35 日間一時停止することができます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-197">**Pause**: If you encounter a problem when you deploy a feature or quality update, you can pause the update for 35 days (starting from a specified date).</span></span> <span data-ttu-id="7a2e7-198">この一時停止により、問題を解決するか、軽減するまで、他のデバイスで更新プログラムをインストールできなくなります。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-198">This pause prevents other devices from installing the update until you resolve or mitigate the problem.</span></span> <span data-ttu-id="7a2e7-199">機能更新プログラムを一時停止しても、品質更新プログラムは引き続きデバイスに提供され、セキュリティで保護された状態を保つことができます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-199">If you pause a feature update, quality updates are still offered to devices to make sure that they stay secure.</span></span> <span data-ttu-id="7a2e7-200">更新プログラムの種類が一時停止されると、そのリングの [概要] ウィンドウには、その種類の更新プログラムが再開するまでの日数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-200">When an update type is paused, the Overview pane for that ring displays how many days remain before that update type resumes.</span></span> <span data-ttu-id="7a2e7-201">指定した時間が経過すると、一時停止が自動的に期限切れになり、更新プロセスが再開します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-201">After the specified time has passed, the pause automatically expires, and the update process resumes.</span></span>

  <span data-ttu-id="7a2e7-202">更新リングが一時停止している間、次のいずれかのオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-202">While the update ring is paused, you can select either of the following options:</span></span>

  - <span data-ttu-id="7a2e7-203">**[延長]**: 35 日間の更新プログラムの種類の一時停止期間を延長します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-203">**Extend**: Extend the pause period for an update type for 35 days.</span></span>
  - <span data-ttu-id="7a2e7-204">**[再開]**: そのリングの更新をアクティブな操作に復元します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-204">**Resume**: Restore updates for that ring to active operation.</span></span> <span data-ttu-id="7a2e7-205">必要な場合は、更新リングを再び一時停止することができます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-205">You can pause the update ring again, if it is necessary.</span></span>

  > [!NOTE]  
  > <span data-ttu-id="7a2e7-206">HoloLens 2 デバイスでは、更新リングに対する**アンインストール**操作はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-206">The **Uninstall** operation for update rings is not supported for HoloLens 2 devices.</span></span>

## <span data-ttu-id="7a2e7-207">更新プログラムの手動での確認方法</span><span class="sxs-lookup"><span data-stu-id="7a2e7-207">Manually check for updates</span></span>

<span data-ttu-id="7a2e7-208">HoloLens ではシステム更新プログラムを定期的に確認しますが、場合によっては手動で確認したいことがあるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-208">Although HoloLens periodically checks for system updates, there may be circumstances in which you want to manually check.</span></span>

<span data-ttu-id="7a2e7-209">更新プログラムを手動で確認するには、**[設定]** > **[更新とセキュリティ]** > **[更新プログラムのチェック]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-209">To manually check for updates, go to **Settings** > **Update & Security** > **Check for updates**.</span></span> <span data-ttu-id="7a2e7-210">[設定] アプリに「お使いのデバイスは最新の状態です」と表示された場合は、現在利用できるすべての更新プログラムがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-210">If the Settings app indicates that your device is up to date, you have all the updates that are currently available.</span></span>

## <span data-ttu-id="7a2e7-211">更新プログラムを手動でロールバックする</span><span class="sxs-lookup"><span data-stu-id="7a2e7-211">Manually roll back an update</span></span>

<span data-ttu-id="7a2e7-212">場合によっては、HoloLens ソフトウェアの以前のバージョンに戻すこともできます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-212">In some cases, you might want to revert to a previous version of the HoloLens software.</span></span> <span data-ttu-id="7a2e7-213">HoloLens 2 を使っているか HoloLens (第 1 世代) を使っているかによって、これを行う手順が異なります。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-213">The process for doing this depends on whether you are using HoloLens 2 or HoloLens (1st gen).</span></span>

### <span data-ttu-id="7a2e7-214">以前のバージョンに戻す (HoloLens 2)</span><span class="sxs-lookup"><span data-stu-id="7a2e7-214">Revert to a previous version (HoloLens 2)</span></span>

<span data-ttu-id="7a2e7-215">[高度な回復コンパニオン](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)を使用して HoloLens を以前のバージョンにリセットすることにより、更新プログラムをロールバックし、HoloLens 2 を以前のバージョンに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-215">You can roll back updates and return to a previous version of HoloLens 2 by using the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="7a2e7-216">以前のバージョンに戻すと、個人用のファイルと設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-216">Reverting to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="7a2e7-217">以前のバージョンの HoloLens 2 に戻すには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-217">To revert to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="7a2e7-218">コンピューターにスマートフォンや Windows デバイスが接続されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-218">Make sure that you don't have any phones or Windows devices plugged in to your computer.</span></span>
1. <span data-ttu-id="7a2e7-219">コンピューターで、Microsoft Store から[高度な回復コンパニオン](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-219">On your computer, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="7a2e7-220">[最新の HoloLens 2 リリース](https://aka.ms/hololens2download)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-220">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="7a2e7-221">これらのダウンロードが完了したら、**エクスプローラー** > **[ダウンロード]** の順に開き、ダウンロードした圧縮 (zip 形式) フォルダーを右クリックし、**[すべて展開]** > **[展開]** を選択してファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-221">After these downloads finish, open **File explorer** > **Downloads**, right-click the compressed (.zip) folder that you just downloaded, and then select **Extract all** > **Extract** to expand the file.</span></span>
1. <span data-ttu-id="7a2e7-222">USB-A - USB-C ケーブルを使って HoloLens デバイスをコンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-222">Use a USB-A to USB-C cable to connect your HoloLens device to your computer.</span></span> <span data-ttu-id="7a2e7-223">HoloLens の接続に他のケーブルを使用していた場合も、この種類のケーブルが最適です。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-223">Even if you've been using other cables to connect your HoloLens, this kind of cable works best.</span></span>
1. <span data-ttu-id="7a2e7-224">高度な回復コンパニオンでは、HoloLens デバイスが自動的に検出されます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-224">The Advanced Recovery Companion automatically detects your HoloLens device.</span></span> <span data-ttu-id="7a2e7-225">**[Microsoft HoloLens]** タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-225">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="7a2e7-226">次の画面で、**[手動によるパッケージの選択]** を選択してから、先に展開しておいたフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-226">On the next screen, select **Manual package selection**, and then open the folder that you previously expanded.</span></span>
1. <span data-ttu-id="7a2e7-227">インストールファイル (.ffu) を選択します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-227">Select the installation (.ffu) file.</span></span>
1. <span data-ttu-id="7a2e7-228">**[ソフトウェアのインストール]** を選択し、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-228">Select **Install software**, and then follow the instructions.</span></span>

### <span data-ttu-id="7a2e7-229">以前のバージョンに戻す (HoloLens (第 1 世代))</span><span class="sxs-lookup"><span data-stu-id="7a2e7-229">Revert to a previous version (HoloLens (1st gen))</span></span>

<span data-ttu-id="7a2e7-230">[Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) を使用して HoloLens を以前のバージョンにリセットすることにより、更新プログラムをロールバックし、HoloLens (第 1 世代) を以前のバージョンに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-230">You can roll back updates and return to a previous version of HoloLens (1st gen) by using the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="7a2e7-231">以前のバージョンの HoloLens に戻すと、個人用のファイルと設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-231">Reverting to an earlier HoloLens version deletes your personal files and settings.</span></span>

<span data-ttu-id="7a2e7-232">以前のバージョンの HoloLens (第 1 世代) に戻すには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-232">To revert to a previous version of HoloLens (1st gen), follow these steps:</span></span>

1. <span data-ttu-id="7a2e7-233">コンピューターにスマートフォンや Windows デバイスが接続されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-233">Make sure that you don't have any phones or Windows devices plugged into your computer.</span></span>
1. <span data-ttu-id="7a2e7-234">コンピューターで、[Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-234">On your computer, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="7a2e7-235">[HoloLens Anniversary Update 回復パッケージ](https://aka.ms/hololensrecovery)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-235">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="7a2e7-236">ダウンロードが完了したら、**エクスプローラー** > **[ダウンロード]** の順に開き、ダウンロードした圧縮 (zip 形式) フォルダーを右クリックし、**[すべて展開]** > **[展開]** を選択してファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-236">After the downloads finish, open **File explorer** > **Downloads**, right-click the compressed (.zip) folder that you just downloaded, and then select **Extract all** > **Extract** to expand the file.</span></span>
1. <span data-ttu-id="7a2e7-237">HoloLens デバイスに付属していた micro-USB ケーブルを使用して、HoloLens デバイスをコンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-237">Use the micro-USB cable that was provided together with your HoloLens device to connect your HoloLens device to your computer.</span></span> <span data-ttu-id="7a2e7-238">HoloLens デバイスの接続に他のケーブルを使用していた場合も、このケーブルが最適です。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-238">Even if you've been using other cables to connect your HoloLens device, this one works best.</span></span>
1. <span data-ttu-id="7a2e7-239">WDRT により、HoloLens デバイスが自動的に検出されます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-239">The WDRT automatically detects your HoloLens device.</span></span> <span data-ttu-id="7a2e7-240">**[Microsoft HoloLens]** タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-240">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="7a2e7-241">次の画面で、**[手動によるパッケージの選択]** を選択してから、先に展開しておいたフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-241">On the next screen, select **Manual package selection**, and then open the folder that you previously expanded.</span></span>
1. <span data-ttu-id="7a2e7-242">インストールファイル (.ffu) を選択します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-242">Select the installation (.ffu) file.</span></span>
1. <span data-ttu-id="7a2e7-243">**[ソフトウェアのインストール]** を選択し、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-243">Select **Install software**, and then follow the instructions.</span></span>

**<span data-ttu-id="7a2e7-244">WDRT でデバイスが検出されない場合</span><span class="sxs-lookup"><span data-stu-id="7a2e7-244">If WDRT doesn't detect your device</span></span>**

<span data-ttu-id="7a2e7-245">WDRT で HoloLens デバイスが検出されない場合は、コンピューターを再起動してみてください。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-245">If WDRT doesn't detect your HoloLens device, try restarting your computer.</span></span> <span data-ttu-id="7a2e7-246">それでも問題が解決しない場合は、**[デバイスが検出されませんでした]** を選択し、**[Microsoft HoloLens]** を選択して、表示される指示に従って操作します。</span><span class="sxs-lookup"><span data-stu-id="7a2e7-246">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="7a2e7-247">関連記事</span><span class="sxs-lookup"><span data-stu-id="7a2e7-247">Related articles</span></span>

- [<span data-ttu-id="7a2e7-248">HoloLens 2 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="7a2e7-248">HoloLens 2 release notes</span></span>](https://docs.microsoft.com/hololens/hololens-release-notes)
- [<span data-ttu-id="7a2e7-249">Windows Update for Business とは?</span><span class="sxs-lookup"><span data-stu-id="7a2e7-249">What is Windows Update for Business?</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [<span data-ttu-id="7a2e7-250">Windows 10 更新プログラムのサービス チャネルにデバイスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="7a2e7-250">Assign devices to servicing channels for Windows 10 updates</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [<span data-ttu-id="7a2e7-251">Intune で Windows 10 のソフトウェア更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="7a2e7-251">Manage Windows 10 software updates in Intune</span></span>](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
