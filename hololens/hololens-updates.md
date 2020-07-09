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
ms.date: 03/24/2020
ms.reviewer: jarrettr
manager: jarrettr
ms.custom:
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: f8d0c788756b0a24ac8a26b8258b267483f1a890
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857755"
---
# <span data-ttu-id="d48f7-103">HoloLens の更新プログラムの管理</span><span class="sxs-lookup"><span data-stu-id="d48f7-103">Manage HoloLens Updates</span></span>

<span data-ttu-id="d48f7-104">HoloLens は、他の Windows 10 デバイスと同じように、Windows Update を使用します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-104">HoloLens uses Windows Update in the same manner as other Windows 10 devices.</span></span> <span data-ttu-id="d48f7-105">更新プログラムが利用可能な場合は、次にデバイスに電源が入りインターネットに接続されたときに、自動的にダウンロードおよびインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-105">When an update is available, it is automatically downloaded and installed the next time that your device is plugged in and connected to the internet.</span></span> <span data-ttu-id="d48f7-106">この記事では、エンタープライズ環境またはその他の管理環境で更新を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-106">This article describes how to manage updates in an enterprise or other managed environment.</span></span> <span data-ttu-id="d48f7-107">個別の HoloLens デバイスへの更新の管理については、「[HoloLens を更新する](hololens-update-hololens.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d48f7-107">For information about managing updates to individual HoloLens devices, see [Update HoloLens](hololens-update-hololens.md).</span></span>

## <span data-ttu-id="d48f7-108">更新を自動的に管理する</span><span class="sxs-lookup"><span data-stu-id="d48f7-108">Manage updates automatically</span></span>

<span data-ttu-id="d48f7-109">Windows Holographic for Business では、[Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) を使用して、更新を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-109">Windows Holographic for Business can use [Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) to manage updates.</span></span> <span data-ttu-id="d48f7-110">すべての HoloLens 2 デバイスは、Windows Holographic for Business を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-110">All HoloLens 2 devices can use Windows Holographic for Business.</span></span> <span data-ttu-id="d48f7-111">Windows Holographic for Business ビルド 10.0.18362.1042 またはそれ以降のビルドを使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d48f7-111">Make sure that they use Windows Holographic for Business build 10.0.18362.1042 or a later build.</span></span> <span data-ttu-id="d48f7-112">HoloLens (第 1 世代) のデバイスを使用している場合は、更新を管理するために [Windows Holographic for Business に更新する](hololens1-upgrade-enterprise.md)必要があります。</span><span class="sxs-lookup"><span data-stu-id="d48f7-112">If you have HoloLens (1st gen) devices, you have to [upgrade them to Windows Holographic for Business](hololens1-upgrade-enterprise.md) to manage their updates.</span></span>

<span data-ttu-id="d48f7-113">Windows Update for Business により、HoloLens デバイスを Windows Update サービスに直接接続します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-113">Windows Update for Business connects HoloLens devices directly to the Windows Update service.</span></span> <span data-ttu-id="d48f7-114">Windows Update for Business を使用すると、更新プロセスの複数の側面として&mdash;いつ、どのデバイスで、どの更新プログラムを取得するか、などを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-114">By using Windows Update for Business, you can control multiple aspects of the update process&mdash;that is, which devices get which updates at what time.</span></span> <span data-ttu-id="d48f7-115">たとえば、テスト用にデバイスのサブセットに更新プログラムをロールアウトし、後日残りのデバイスに更新プログラムをロールアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-115">For example, you can roll out updates to a subset of devices for testing, then roll out updates to the remaining devices at a later date.</span></span> <span data-ttu-id="d48f7-116">または、更新プログラムの種類によって、異なる更新スケジュールを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-116">Or, you can define different update schedules for different types of updates.</span></span>

> [!NOTE]  
> <span data-ttu-id="d48f7-117">HoloLens デバイスでは、機能更新プログラム (年に 2 回リリース) と、品質更新プログラム (月ごとまたは必要に応じてリリースされ、重要なセキュリティ更新プログラムを含む) を、自動的に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-117">For HoloLens devices, you can automatically manage feature updates (released twice a year) and quality updates (released monthly or as required, including critical security updates).</span></span> <span data-ttu-id="d48f7-118">更新プログラムの種類の詳細については、「[Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business) で管理される更新プログラムの種類」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d48f7-118">For more information about update types, see [Types of updates managed by Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).</span></span>

<span data-ttu-id="d48f7-119">HoloLens 用の Windows Update for Business の設定は、Microsoft Intune などのモバイル デバイス管理 (MDM) ソリューションのポリシーを使用して構成することができます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-119">You can configure Windows Update for Business settings for HoloLens by using policies in a Mobile Device Management (MDM) solution such as Microsoft Intune.</span></span>

<span data-ttu-id="d48f7-120">Intune を使用して Windows Update for Business を構成する方法の詳細については、「[Windows 10 のソフトウェア更新プログラムを Intune で管理する](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d48f7-120">For a detailed discussion about how to use Intune to configure Windows Update for Business, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure).</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="d48f7-121">Intune には、更新を管理するために、*Windows 10 更新リング* と *Windows 10 機能更新プログラム*の 2 種類のポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="d48f7-121">Intune provides two policy types for managing updates: *Windows 10 update ring* and *Windows 10 feature updates*.</span></span> <span data-ttu-id="d48f7-122">Windows 10 機能更新プログラムのポリシーの種類は、現時点ではパブリック プレビュー段階であり、HoloLens でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d48f7-122">The Windows 10 feature update policy type is in public preview at this time and is not supported for HoloLens.</span></span>
>  
> <span data-ttu-id="d48f7-123">Windows 10 更新リング ポリシーを使用して HoloLens 2 の更新を管理できます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-123">You can use Windows 10 update ring policies to manage HoloLens 2 updates.</span></span>

### <span data-ttu-id="d48f7-124">HoloLens 2 または HoloLens (第 1 世代) の更新ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="d48f7-124">Configure update policies for HoloLens 2 or HoloLens (1st gen)</span></span>

<span data-ttu-id="d48f7-125">このセクションでは、HoloLens 2 または HoloLens (第 1 世代) の更新を管理するのに使用できるポリシーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-125">This section describes the policies that you can use to manage updates for either HoloLens 2 or HoloLens (1st gen).</span></span> <span data-ttu-id="d48f7-126">HoloLens 2 向けのその他の機能の詳細については、「[HoloLens 2 の更新プログラムのロールアウトについての計画と構成](#plan-and-configure-update-rollouts-for-hololens-2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d48f7-126">For information about additional functionality that is available for HoloLens 2, see [Plan and configure update rollouts for HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).</span></span>

<span data-ttu-id="d48f7-127">[ポリシー構成サービス プロバイダー (CSP)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) は、Windows Update for Business を構成するポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-127">The [Policy configuration service provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) defines the policies that configure Windows Update for Business.</span></span>

> [!NOTE]  
> <span data-ttu-id="d48f7-128">HoloLens の特定のエディションでサポートされている特定のポリシーの詳細については、「[HoloLens デバイスでサポートされているポリシー](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-hololens-devices)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d48f7-128">For details about specific policies that are supported by specific editions of HoloLens, see [Policies supported by HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-hololens-devices).</span></span>

#### <span data-ttu-id="d48f7-129">更新プログラムの自動チェックを構成する</span><span class="sxs-lookup"><span data-stu-id="d48f7-129">Configure automatic checks for updates</span></span>

<span data-ttu-id="d48f7-130">**Update/AllowAutoUpdate** ポリシーを使用して、更新プログラムのスキャン、ダウンロード、インストールなど、自動更新の動作を管理できます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-130">You can use the **Update/AllowAutoUpdate** policy to manage automatic update behavior, such as scanning, downloading, and installing updates.</span></span>

<span data-ttu-id="d48f7-131">このポリシーでは、次の値をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d48f7-131">This policy supports the following values:</span></span>

- <span data-ttu-id="d48f7-132">**0** - デバイスに適用されるダウンロード可能な更新プログラムがある場合にユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-132">**0** - Notify the user when there is an update that is ready to download that applies to the device.</span></span>
- <span data-ttu-id="d48f7-133">**1** - 更新プログラムを自動的にインストールし、デバイスの再起動をスケジュールするように、ユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-133">**1** - Automatically install the update, and then notify the user to schedule a device restart.</span></span>  
- <span data-ttu-id="d48f7-134">**2** - 更新プログラムを自動的にインストールしてから、デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-134">**2** - Automatically install the update, and then restart the device.</span></span> <span data-ttu-id="d48f7-135">これは推奨値であり、このポリシーの既定値です。</span><span class="sxs-lookup"><span data-stu-id="d48f7-135">This is the recommended value, and it is the default value for this policy.</span></span>  

- <span data-ttu-id="d48f7-136">**3** - 更新プログラムを自動的にインストールしてから、指定の時間にデバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-136">**3** - Automatically install the update, and then restart at a specified time.</span></span> <span data-ttu-id="d48f7-137">インストールの日付と時刻を指定します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-137">Specify the installation day and time.</span></span> <span data-ttu-id="d48f7-138">日付と時刻を指定しない場合、既定値は毎日午前 3 時になります。</span><span class="sxs-lookup"><span data-stu-id="d48f7-138">If no day and time are specified, the default is daily at 3 A.M.</span></span>  

- <span data-ttu-id="d48f7-139">**4** - 更新プログラムを自動的にインストールしてから、デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-139">**4** - Automatically install the update, and then restart the device.</span></span> <span data-ttu-id="d48f7-140">このオプションでは、[設定] ページが読み取り専用に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-140">This option also sets the Settings page to read-only.</span></span>

- <span data-ttu-id="d48f7-141">**5** - 自動更新を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d48f7-141">**5** - Turn off automatic updates.</span></span>

<span data-ttu-id="d48f7-142">このポリシーの使用可能な設定の詳細については、「[Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d48f7-142">For more details about the available settings for this policy, see [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).</span></span>

> [!NOTE]  
> <span data-ttu-id="d48f7-143">Microsoft Intune では、**自動更新動作**を使用して、このポリシーを変更できます </span><span class="sxs-lookup"><span data-stu-id="d48f7-143">In Microsoft Intune, you can use **Automatic Update Behavior** to change this policy.</span></span> <span data-ttu-id="d48f7-144">詳細については、「[Microsoft Intune でのソフトウェア更新プログラムの管理](https://docs.microsoft.com/intune/windows-update-for-business-configure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d48f7-144">For more information, see [Manage software updates in Microsoft Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span></span>

#### <span data-ttu-id="d48f7-145">更新スケジュールを構成する</span><span class="sxs-lookup"><span data-stu-id="d48f7-145">Configure an update schedule</span></span>

<span data-ttu-id="d48f7-146">更新プログラムを適用する方法とタイミングを構成するには、次のポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-146">To configure how and when updates are applied, use the following policies:</span></span>

- <span data-ttu-id="d48f7-147">[Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)。</span><span class="sxs-lookup"><span data-stu-id="d48f7-147">[Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday).</span></span>  
   - <span data-ttu-id="d48f7-148">値: **0**–**7** (0 = 毎日、1 = 日曜日、7 = 土曜日)</span><span class="sxs-lookup"><span data-stu-id="d48f7-148">Values: **0**–**7** (0 = every day, 1 = Sunday, 7 = Saturday)</span></span>
   - <span data-ttu-id="d48f7-149">既定値: **0** (毎日)</span><span class="sxs-lookup"><span data-stu-id="d48f7-149">Default value: **0** (every day)</span></span>
- <span data-ttu-id="d48f7-150">[Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)。</span><span class="sxs-lookup"><span data-stu-id="d48f7-150">[Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime).</span></span>
   - <span data-ttu-id="d48f7-151">Values: 0–23 (0 = 午前 0:00、23 = 午後 11:00)</span><span class="sxs-lookup"><span data-stu-id="d48f7-151">Values: 0–23 (0 = midnight, 23 = 11 P.M.)</span></span>
   - <span data-ttu-id="d48f7-152">既定値: 午後 3:00</span><span class="sxs-lookup"><span data-stu-id="d48f7-152">Default value: 3 P.M.</span></span>

#### <span data-ttu-id="d48f7-153">Windows 10 バージョン 1607 を実行するデバイスのみ</span><span class="sxs-lookup"><span data-stu-id="d48f7-153">For devices that run Windows 10, version 1607 only</span></span>

<span data-ttu-id="d48f7-154">以下の更新ポリシーを使用して、Windows Update ではなく Windows Server Update Services (WSUS) から更新プログラムを取得するようにデバイスを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-154">You can use the following update policies to configure devices to get updates from the Windows Server Update Service (WSUS), instead of Windows Update:</span></span>

- [<span data-ttu-id="d48f7-155">Update/AllowUpdateService</span><span class="sxs-lookup"><span data-stu-id="d48f7-155">Update/AllowUpdateService</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [<span data-ttu-id="d48f7-156">Update/RequireUpdateApproval</span><span class="sxs-lookup"><span data-stu-id="d48f7-156">Update/RequireUpdateApproval</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [<span data-ttu-id="d48f7-157">Update/UpdateServiceUrl</span><span class="sxs-lookup"><span data-stu-id="d48f7-157">Update/UpdateServiceUrl</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <span data-ttu-id="d48f7-158">HoloLens 2 の更新プログラムのロールアウトについての計画と構成</span><span class="sxs-lookup"><span data-stu-id="d48f7-158">Plan and configure update rollouts for HoloLens 2</span></span>

<span data-ttu-id="d48f7-159">HoloLens 2 は、HoloLens (第 1 世代) よりも多くの更新の自動化機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d48f7-159">HoloLens 2 supports more update automation features than HoloLens (1st gen).</span></span> <span data-ttu-id="d48f7-160">Microsoft Intune を使用して Windows Update for Business のポリシーを管理する場合は、特にそうです。</span><span class="sxs-lookup"><span data-stu-id="d48f7-160">this is especially true if you use Microsoft Intune to manage Windows Update for Business policy.</span></span> <span data-ttu-id="d48f7-161">これらの機能により、組織全体で行う更新プログラムのロールアウトを、より簡単に計画し、実装できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d48f7-161">These features make it easier for you to plan and implement update rollouts across your organization.</span></span>

#### <span data-ttu-id="d48f7-162">更新戦略を計画する</span><span class="sxs-lookup"><span data-stu-id="d48f7-162">Plan the update strategy</span></span>

<span data-ttu-id="d48f7-163">Windows Updates for Business は繰延ポリシーをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d48f7-163">Windows Updates for Business supports deferral policies.</span></span> <span data-ttu-id="d48f7-164">繰延ポリシーを使用して、更新プログラムがリリースされてから、どのぐらいの時間でデバイスにその更新プログラムをインストールするかを定義できます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-164">After Microsoft releases an update, you can use a deferral policy to define how long to wait before installing that update on devices.</span></span> <span data-ttu-id="d48f7-165">異なる繰延ポリシーを使用して、デバイスのサブセット (*更新リング*とも呼ばれる) を関連付けることにより、組織の更新プログラムのロールアウト戦略を調整できます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-165">By associating subsets of your devices (referred to as *update rings*) with different deferral policies, you can coordinate an update rollout strategy for your organization.</span></span>

<span data-ttu-id="d48f7-166">たとえば、組織で 1000 台のデバイスを所有していて、それを 5 通りの方法で更新しなければならないとします。</span><span class="sxs-lookup"><span data-stu-id="d48f7-166">For example, consider an organization that has 1,000 devices and has to update them in five ways.</span></span> <span data-ttu-id="d48f7-167">組織では、次の表に示すような 5 つの更新リングを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-167">The organization can create five update rings, as shown in the following table.</span></span>

|<span data-ttu-id="d48f7-168">Group</span><span class="sxs-lookup"><span data-stu-id="d48f7-168">Group</span></span> |<span data-ttu-id="d48f7-169">デバイスの数</span><span class="sxs-lookup"><span data-stu-id="d48f7-169">Number of devices</span></span> |<span data-ttu-id="d48f7-170">繰延 (日数)</span><span class="sxs-lookup"><span data-stu-id="d48f7-170">Deferral (days)</span></span> |
| ---| :---: | :---: |
|<span data-ttu-id="d48f7-171">グループ 1 (IT スタッフ)</span><span class="sxs-lookup"><span data-stu-id="d48f7-171">Grp 1 (IT staff)</span></span> |<span data-ttu-id="d48f7-172">5</span><span class="sxs-lookup"><span data-stu-id="d48f7-172">5</span></span> |<span data-ttu-id="d48f7-173">0</span><span class="sxs-lookup"><span data-stu-id="d48f7-173">0</span></span> |
|<span data-ttu-id="d48f7-174">グループ 2 (早期導入者)</span><span class="sxs-lookup"><span data-stu-id="d48f7-174">Grp 2 (early adopters)</span></span> |<span data-ttu-id="d48f7-175">50</span><span class="sxs-lookup"><span data-stu-id="d48f7-175">50</span></span> |<span data-ttu-id="d48f7-176">60</span><span class="sxs-lookup"><span data-stu-id="d48f7-176">60</span></span> |
|<span data-ttu-id="d48f7-177">グループ 3 (メイン 1)</span><span class="sxs-lookup"><span data-stu-id="d48f7-177">Grp 3 (main 1)</span></span> |<span data-ttu-id="d48f7-178">250</span><span class="sxs-lookup"><span data-stu-id="d48f7-178">250</span></span> |<span data-ttu-id="d48f7-179">120</span><span class="sxs-lookup"><span data-stu-id="d48f7-179">120</span></span> |
|<span data-ttu-id="d48f7-180">グループ 4 (メイン 2)</span><span class="sxs-lookup"><span data-stu-id="d48f7-180">Grp 4 (main 2)</span></span> |<span data-ttu-id="d48f7-181">300</span><span class="sxs-lookup"><span data-stu-id="d48f7-181">300</span></span> |<span data-ttu-id="d48f7-182">150</span><span class="sxs-lookup"><span data-stu-id="d48f7-182">150</span></span> |
|<span data-ttu-id="d48f7-183">グループ 5 (メイン 3)</span><span class="sxs-lookup"><span data-stu-id="d48f7-183">Grp 5 (main 3)</span></span> |<span data-ttu-id="d48f7-184">395</span><span class="sxs-lookup"><span data-stu-id="d48f7-184">395</span></span> |<span data-ttu-id="d48f7-185">180</span><span class="sxs-lookup"><span data-stu-id="d48f7-185">180</span></span> |

<span data-ttu-id="d48f7-186">時間の経過と共に組織全体にロールアウトする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-186">Here's how the rollout progresses over time to the entire organization.</span></span>

![更新プログラムを展開するタイムライン](./images/hololens-updates-timeline.png)

#### <span data-ttu-id="d48f7-188">更新プログラムの繰延ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="d48f7-188">Configure an update deferral policy</span></span>

<span data-ttu-id="d48f7-189">繰延ポリシーにより、更新プログラムが入手可能になった日から更新プログラムをデバイスに提供する日までの日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-189">A deferral policy specifies the number of days between the date that an update becomes available and the date that the update is offered to a device.</span></span>

<span data-ttu-id="d48f7-190">機能更新プログラムと品質更新プログラムに、異なる繰延を構成できます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-190">You can configure different deferrals for feature updates and quality updates.</span></span> <span data-ttu-id="d48f7-191">次の表で、それぞれの種類に使える特定のポリシーと、それぞれの繰延の最大日数を示します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-191">The following table lists the specific policies to use for each type, as well as the maximum deferral for each.</span></span>

|<span data-ttu-id="d48f7-192">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="d48f7-192">Category</span></span> |<span data-ttu-id="d48f7-193">ポリシー</span><span class="sxs-lookup"><span data-stu-id="d48f7-193">Policy</span></span> |<span data-ttu-id="d48f7-194">保留の最長期間</span><span class="sxs-lookup"><span data-stu-id="d48f7-194">Maximum deferral</span></span> |
| --- | --- | --- |
|<span data-ttu-id="d48f7-195">機能更新プログラム</span><span class="sxs-lookup"><span data-stu-id="d48f7-195">Feature updates</span></span> |<span data-ttu-id="d48f7-196">DeferFeatureUpdatesPeriodInDays</span><span class="sxs-lookup"><span data-stu-id="d48f7-196">DeferFeatureUpdatesPeriodInDays</span></span> |<span data-ttu-id="d48f7-197">365 日</span><span class="sxs-lookup"><span data-stu-id="d48f7-197">365 days</span></span> |
|<span data-ttu-id="d48f7-198">品質更新プログラム</span><span class="sxs-lookup"><span data-stu-id="d48f7-198">Quality updates</span></span> |<span data-ttu-id="d48f7-199">DeferQualityUpdatesPeriodInDays</span><span class="sxs-lookup"><span data-stu-id="d48f7-199">DeferQualityUpdatesPeriodInDays</span></span> |<span data-ttu-id="d48f7-200">30 日</span><span class="sxs-lookup"><span data-stu-id="d48f7-200">30 days</span></span> |

####  <span data-ttu-id="d48f7-201">例: Intune を使用して更新を管理する</span><span class="sxs-lookup"><span data-stu-id="d48f7-201">Examples: Using Intune to manage updates</span></span>

**<span data-ttu-id="d48f7-202">例 1: 更新リングを作成して割り当てる</span><span class="sxs-lookup"><span data-stu-id="d48f7-202">Example 1: Create and assign an update ring</span></span>**

<span data-ttu-id="d48f7-203">この例の詳細版については、「[更新リングの作成と割り当て](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d48f7-203">For a more detailed version of this example, see [Create and assign update rings](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).</span></span>

1. <span data-ttu-id="d48f7-204">[Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)にサインインし、Intune プロファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-204">Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431), and navigate to your Intune profiles.</span></span>
1. <span data-ttu-id="d48f7-205">**[ソフトウェアの更新]** > **[Windows 10 更新リング]** > **[作成]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-205">Select **Software Updates** > **Windows 10 update rings** > **Create**.</span></span>
1. <span data-ttu-id="d48f7-206">**[基本事項]** で、名前と説明 (省略可能) を指定し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-206">Under **Basics**, specify a name and a description (optional), and then select **Next**.</span></span>
1. <span data-ttu-id="d48f7-207">**[更新リングの設定]** の **[サービス チャネル]** で、**[半期チャネル]** を選択し、**[機能更新プログラムの繰延期間]** を **120** に変更します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-207">Under **Update ring settings**, for **Servicing channel**, select **Semi-Annual Channel**, and then change **Feature update deferral period** to **120**.</span></span> <span data-ttu-id="d48f7-208">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-208">Then, select **Next**.</span></span>
1. <span data-ttu-id="d48f7-209">**[割り当て]** で、**[+ 含めるグループを選択する]** を選択し、1 つまたは複数のグループに更新リングを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-209">Under **Assignments**, select **+ Select groups to include**, and then assign the update ring to one or more groups.</span></span> <span data-ttu-id="d48f7-210">**[+ 除外するグループを選択する]** を使って、割り当てを微調整します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-210">Use **+ Select groups to exclude** to fine-tune the assignments.</span></span> <span data-ttu-id="d48f7-211">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-211">Then, select **Next**.</span></span>
1. <span data-ttu-id="d48f7-212">**[確認 + 作成]** で設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-212">Under **Review + create**, review the settings.</span></span> <span data-ttu-id="d48f7-213">更新リングの構成を保存する準備ができたら、**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-213">When you're ready to save the update ring configuration, select **Create**.</span></span>

<span data-ttu-id="d48f7-214">更新リングの一覧に、新しい Windows 10 更新リングが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-214">The list of update rings now includes the new Windows 10 update ring.</span></span>

**<span data-ttu-id="d48f7-215">例 2: 更新リングを一時停止する</span><span class="sxs-lookup"><span data-stu-id="d48f7-215">Example 2: Pause an update ring</span></span>**

<span data-ttu-id="d48f7-216">機能更新プログラムまたは品質更新プログラムを展開するときに問題が発生した場合は、更新を (指定した日付から) 35 日間一時停止することができます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-216">If you encounter a problem when you deploy a feature or quality update, you can pause the update for 35 days (starting from a specified date).</span></span> <span data-ttu-id="d48f7-217">この一時停止により、問題を解決するか、軽減するまで、他のデバイスで更新プログラムをインストールできなくなります。</span><span class="sxs-lookup"><span data-stu-id="d48f7-217">This pause prevents other devices from installing the update until you resolve or mitigate the issue.</span></span> <span data-ttu-id="d48f7-218">機能更新プログラムを一時停止しても、品質更新プログラムは引き続きデバイスに提供され、セキュリティで保護された状態を保つことができます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-218">If you pause a feature update, quality updates are still offered to devices to make sure that they stay secure.</span></span> <span data-ttu-id="d48f7-219">指定した時間が経過すると、一時停止が自動的に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="d48f7-219">After the specified time has passed, the pause automatically expires.</span></span> <span data-ttu-id="d48f7-220">その時点で更新プロセスが再開します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-220">At that point, the update process resumes.</span></span>

<span data-ttu-id="d48f7-221">Intune で更新リングを一時停止するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-221">To pause an update ring in Intune, follow these steps:</span></span>

1. <span data-ttu-id="d48f7-222">更新リングの概要ページで、**[一時停止]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-222">On the overview page for the update ring, select **Pause**.</span></span>
1. <span data-ttu-id="d48f7-223">一時停止する更新プログラムの種類 (**機能**または**品質**) を選択し、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-223">Select the type of update (**Feature** or **Quality**) to pause, and then select **OK**.</span></span>

<span data-ttu-id="d48f7-224">更新プログラムの種類が一時停止されると、そのリングの [概要] ウィンドウには、その種類の更新プログラムが再開するまでの日数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-224">When an update type is paused, the Overview pane for that ring displays how many days remain before that update type resumes.</span></span>

<span data-ttu-id="d48f7-225">更新リングが一時停止している間、次のいずれかのオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-225">While the update ring is paused, you can select either of the following options:</span></span>

- <span data-ttu-id="d48f7-226">35 日間の更新プログラムの種類の一時停止期間を延長するには、**[延長]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-226">To extend the pause period for an update type for 35 days, select **Extend**.</span></span>
- <span data-ttu-id="d48f7-227">そのリングの更新をアクティブな操作に復元するには、**[再開]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-227">To restore updates for that ring to active operation, select **Resume**.</span></span> <span data-ttu-id="d48f7-228">必要な場合は、更新リングを再び一時停止することができます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-228">You can pause the update ring again if it is necessary.</span></span>

> [!NOTE]  
> <span data-ttu-id="d48f7-229">HoloLens 2 デバイスでは、更新リングに対する**アンインストール**操作はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d48f7-229">The **Uninstall** operation for update rings is not supported for HoloLens 2 devices.</span></span>

## <span data-ttu-id="d48f7-230">更新プログラムの手動での確認方法</span><span class="sxs-lookup"><span data-stu-id="d48f7-230">Manually check for updates</span></span>

<span data-ttu-id="d48f7-231">HoloLens ではシステム更新プログラムを定期的に確認するので、手動で確認する必要はありませんが、場合によっては手動で確認したいことがあるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="d48f7-231">Although HoloLens periodically checks for system updates so that you don't have to, there may be circumstances in which you want to manually check.</span></span>

<span data-ttu-id="d48f7-232">更新プログラムを手動で確認するには、**[設定]** > **[更新とセキュリティ]** > **[更新プログラムのチェック]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-232">To manually check for updates, go to **Settings** > **Update & Security** > **Check for updates**.</span></span> <span data-ttu-id="d48f7-233">[設定] アプリに「お使いのデバイスは最新の状態です」と表示された場合は、現在利用できるすべての更新プログラムがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="d48f7-233">If the Settings app indicates that your device is up to date, you have all the updates that are currently available.</span></span>

## <span data-ttu-id="d48f7-234">更新プログラムを手動で元に戻す</span><span class="sxs-lookup"><span data-stu-id="d48f7-234">Manually revert an update</span></span>

<span data-ttu-id="d48f7-235">場合によっては、HoloLens ソフトウェアの以前のバージョンに戻すこともできます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-235">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="d48f7-236">HoloLens 2 を使っているか HoloLens (第 1 世代) を使っているかによって、これを行う手順が異なります。</span><span class="sxs-lookup"><span data-stu-id="d48f7-236">The process for doing this depends on whether you are using HoloLens 2 or HoloLens (1st gen).</span></span>

### <span data-ttu-id="d48f7-237">以前のバージョンに戻す (HoloLens 2)</span><span class="sxs-lookup"><span data-stu-id="d48f7-237">Go back to a previous version (HoloLens 2)</span></span>

<span data-ttu-id="d48f7-238">高度な回復コンパニオンを使用して HoloLens を以前のバージョンにリセットすることにより、更新プログラムをロールバックし、HoloLens 2 を以前のバージョンに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-238">You can roll back updates and return to a previous version of HoloLens 2 by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="d48f7-239">以前のバージョンに戻すと、個人用のファイルと設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-239">Reverting to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="d48f7-240">以前のバージョンの HoloLens 2 に戻すには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-240">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="d48f7-241">コンピューターにスマートフォンや Windows デバイスが接続されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-241">Make sure that you don't have any phones or Windows devices plugged in to your computer.</span></span>
1. <span data-ttu-id="d48f7-242">コンピューターで、Microsoft Store から[高度な回復コンパニオン](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d48f7-242">On your computer, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="d48f7-243">[最新の HoloLens 2 リリース](https://aka.ms/hololens2download)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d48f7-243">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="d48f7-244">ダウンロードが完了したら、**エクスプローラー** > **[ダウンロード]** の順に開き、ダウンロードした圧縮 (zip 形式) フォルダーを右クリックし、**[すべて展開]** > **[展開]** を選択してファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-244">When you have finished these downloads, open **File explorer** > **Downloads**, right-click the compressed (zipped) folder that you just downloaded, and then select **Extract all** > **Extract** to expand the file.</span></span>
1. <span data-ttu-id="d48f7-245">USB-A - USB-C ケーブルを使って HoloLens デバイスをコンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-245">Use a USB-A to USB-C cable to connect your HoloLens device to your computer.</span></span> <span data-ttu-id="d48f7-246">HoloLens の接続に他のケーブルを使用していた場合も、この種類のケーブルが最適です。</span><span class="sxs-lookup"><span data-stu-id="d48f7-246">Even if you've been using other cables to connect your HoloLens, this kind of cable works best.</span></span>
1. <span data-ttu-id="d48f7-247">高度な回復コンパニオンでは、HoloLens デバイスが自動的に検出されます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-247">The Advanced Recovery Companion automatically detects your HoloLens device.</span></span> <span data-ttu-id="d48f7-248">**[Microsoft HoloLens]** タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-248">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="d48f7-249">次の画面で、**[手動によるパッケージの選択]** を選択してから、先に展開しておいたフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-249">On the next screen, select **Manual package selection**, and then open the folder that you previously expanded.</span></span> 
1. <span data-ttu-id="d48f7-250">インストール ファイル (拡張子が .ffu のファイル) を選択します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-250">Select the installation file (the file that has an .ffu extension).</span></span>
1. <span data-ttu-id="d48f7-251">**[ソフトウェアのインストール]** を選択し、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d48f7-251">Select **Install software**, and then follow the instructions.</span></span>

### <span data-ttu-id="d48f7-252">以前のバージョンに戻す (HoloLens (第 1 世代))</span><span class="sxs-lookup"><span data-stu-id="d48f7-252">Go back to a previous version (HoloLens (1st gen))</span></span>

<span data-ttu-id="d48f7-253">Windows Device Recovery Tool を使用して HoloLens を以前のバージョンにリセットすることにより、更新プログラムをロールバックし、HoloLens (第 1 世代) を以前のバージョンに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-253">You can roll back updates and return to a previous version of HoloLens (1st gen) by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="d48f7-254">以前のバージョンに戻すと、個人用のファイルと設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-254">Reverting to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="d48f7-255">以前のバージョンの HoloLens (第 1 世代) に戻すには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-255">To go back to a previous version of HoloLens (1st gen), follow these steps:</span></span>

1. <span data-ttu-id="d48f7-256">コンピューターにスマートフォンや Windows デバイスが接続されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-256">Make sure that you don't have any phones or Windows devices plugged in to your computer.</span></span>
1. <span data-ttu-id="d48f7-257">コンピューターで、[Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d48f7-257">On your computer, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="d48f7-258">[HoloLens Anniversary Update 回復パッケージ](https://aka.ms/hololensrecovery)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d48f7-258">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="d48f7-259">ダウンロードが完了したら、**エクスプローラー** > **[ダウンロード]** の順に開き、ダウンロードした圧縮 (zip 形式) フォルダーを右クリックし、**[すべて展開]** > **[展開]** を選択してファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-259">After the downloads finish, open **File explorer** > **Downloads**, right-click the compressed (zipped) folder that you just downloaded, and then select **Extract all** > **Extract** to expand the file.</span></span>
1. <span data-ttu-id="d48f7-260">HoloLens デバイスに付属していた micro-USB ケーブルを使用して、HoloLens デバイスをコンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-260">Use the micro-USB cable that was provided together with your HoloLens device to connect your HoloLens device to your computer.</span></span> <span data-ttu-id="d48f7-261">HoloLens デバイスの接続に他のケーブルを使用していた場合も、このケーブルが最適です。</span><span class="sxs-lookup"><span data-stu-id="d48f7-261">Even if you've been using other cables to connect your HoloLens device, this one works best.</span></span>
1. <span data-ttu-id="d48f7-262">WDRT により、HoloLens デバイスが自動的に検出されます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-262">The WDRT automatically detects your HoloLens device.</span></span> <span data-ttu-id="d48f7-263">**[Microsoft HoloLens]** タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-263">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="d48f7-264">次の画面で、**[手動によるパッケージの選択]** を選択してから、先に展開しておいたフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="d48f7-264">On the next screen, select **Manual package selection**, and then open the folder that you previously expanded.</span></span> 
1. <span data-ttu-id="d48f7-265">インストール ファイル (拡張子が .ffu のファイル) を選択します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-265">Select the installation file (the file that has an .ffu extension).</span></span>
1. <span data-ttu-id="d48f7-266">**[ソフトウェアのインストール]** を選択し、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d48f7-266">Select **Install software**, and then follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="d48f7-267">WDRT で HoloLens デバイスが検出されない場合は、コンピューターを再起動してみてください。</span><span class="sxs-lookup"><span data-stu-id="d48f7-267">If the WDRT doesn't detect your HoloLens device, try restarting your computer.</span></span> <span data-ttu-id="d48f7-268">それでも問題が解決しない場合は、**[デバイスが検出されませんでした]** を選択し、**[Microsoft HoloLens]** を選択して、表示される指示に従って操作します。</span><span class="sxs-lookup"><span data-stu-id="d48f7-268">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="d48f7-269">関連記事</span><span class="sxs-lookup"><span data-stu-id="d48f7-269">Related articles</span></span>

- [<span data-ttu-id="d48f7-270">Windows Update for Business を使った更新プログラムの展開</span><span class="sxs-lookup"><span data-stu-id="d48f7-270">Deploy updates using Windows Update for Business</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [<span data-ttu-id="d48f7-271">Windows 10 更新プログラムのサービス チャネルにデバイスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="d48f7-271">Assign devices to servicing channels for Windows 10 updates</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [<span data-ttu-id="d48f7-272">Intune で Windows 10 のソフトウェア更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="d48f7-272">Manage Windows 10 software updates in Intune</span></span>](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
