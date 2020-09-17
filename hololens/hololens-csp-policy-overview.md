---
title: Csp とデバイス管理の概要を構成する
description: Csp、ポリシー、デバイスの管理を構成する方法。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4c31f7f92116031535a2dc2860e3f048a2311a39
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016794"
---
# <span data-ttu-id="b3a7d-103">Csp とデバイス管理の概要を構成する</span><span class="sxs-lookup"><span data-stu-id="b3a7d-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="b3a7d-104">IT 管理者は、HoloLens 2 でポリシー設定を定義して実装することができます。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="b3a7d-105">使用する構成設定は展開シナリオによって異なり、企業のデバイスは幅広い制御機能を IT 部門に提供します。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="b3a7d-106">Windows 10 では、構成サービスプロバイダー (CSP) は、デバイスの構成設定の読み取り、設定、変更、または削除を行うためのインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="b3a7d-107">これらの設定は、レジストリ キーまたはファイルにマップされます。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="b3a7d-108">一部の構成サービスプロバイダーでは、WAP 形式をサポートしており、SyncML をサポートしていて、両方をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span> 

<span data-ttu-id="b3a7d-109">Windows 10 ホログラフィック device management Csp の詳細については、「 [HoloLens デバイスでサポートされている](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)すべての csp の一覧」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span> <span data-ttu-id="b3a7d-110">IT 管理者は、デバイスでポリシー CSP を管理することもできます。 [HoloLens 2 でサポートされているポリシー](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)の完全な一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <span data-ttu-id="b3a7d-111">構成方法</span><span class="sxs-lookup"><span data-stu-id="b3a7d-111">Configuration methods</span></span>

### <span data-ttu-id="b3a7d-112">MDM で構成する</span><span class="sxs-lookup"><span data-stu-id="b3a7d-112">Configure with MDM</span></span>
<span data-ttu-id="b3a7d-113">Csp とポリシーは、MDM システムに登録されている個人または企業のデバイスで簡単に管理できます。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="b3a7d-114">デバイスが MDM ソリューションに登録されると、デバイスの構成を使用してデバイスまたはデバイスのセットを管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="b3a7d-115">[MDM で HoloLens デバイスを管理](hololens-mdm-configure.md)する方法の詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <span data-ttu-id="b3a7d-116">プロビジョニングパッケージを使った構成</span><span class="sxs-lookup"><span data-stu-id="b3a7d-116">Configure with Provisioning Packages</span></span>
<span data-ttu-id="b3a7d-117">HoloLens 2 では、カスタムプロビジョニングパッケージを介して、HoloLens 2 デバイスの一部の CSP 構成の設定もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="b3a7d-118">通常、プロビジョニングパッケージは、MDM 以外で管理されるデバイスで利用できます。また、各デバイスに手動で適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="b3a7d-119">[HoloLens 用のカスタムプロビジョニングパッケージ](https://docs.microsoft.com/hololens/hololens-provisioning)の構築に関する情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-119">Read information on building custom [Provisioning Packages for HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> 

## <span data-ttu-id="b3a7d-120">構成</span><span class="sxs-lookup"><span data-stu-id="b3a7d-120">Configurations</span></span> 

### <span data-ttu-id="b3a7d-121">一般的なデバイスの制限</span><span class="sxs-lookup"><span data-stu-id="b3a7d-121">Common device restrictions</span></span>
<span data-ttu-id="b3a7d-122">デバイスの制限によっては、機能やデバイスへの接続を簡単に無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="b3a7d-123">詳細については、[一般的なデバイスの制限](hololens-common-device-restrictions.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <span data-ttu-id="b3a7d-124">キオスクモード</span><span class="sxs-lookup"><span data-stu-id="b3a7d-124">Kiosk modes</span></span>
<span data-ttu-id="b3a7d-125">キオスクモードを使用して、既定でどのアプリにアクセスできる id を制御します。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="b3a7d-126">キオスクは、1つのアプリまたは複数のアプリの UI エクスペリエンスに使用できます。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="b3a7d-127">[キオスクの構成] は、デバイスを使用するすべての人のための1つのアプリから、さまざまなグループ用のさまざまなアプリの選択までを対象としています。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="b3a7d-128">これにより、「許可されたアプリ」が他のアプリを起動することはなくなり、これまでは意図していませんでした。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-128">This does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="b3a7d-129">[キオスクモードの概要とその使い方](hololens-kiosk.md)については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-129">To learn more [start reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <span data-ttu-id="b3a7d-130">設定ページの表示</span><span class="sxs-lookup"><span data-stu-id="b3a7d-130">Settings Page Visibility</span></span>
<span data-ttu-id="b3a7d-131">設定アプリポリシーを使って、既定で設定にアクセスできる id を制御します。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="b3a7d-132">このポリシーを設定すると、設定アプリは、選択したページのみを表示するか、選択したすべてのページを非表示にするように構成することができます。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-132">With this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="b3a7d-133">[使用可能なページを構成する方法について](settings-uri-list.md)説明します。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="b3a7d-134">この機能は、現時点では、 [Windows Insider ビルド](hololens-insider.md)でのみ avalible ます。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-134">This feature is currently only avalible in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="b3a7d-135">これを使用するデバイスがビルド 19041.1349 + であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-135">Please ensure devices you intend to use this for are on build 19041.1349+.</span></span>

### <span data-ttu-id="b3a7d-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="b3a7d-136">WDAC</span></span>
<span data-ttu-id="b3a7d-137">WDAC 構成を使って、システムがキオスクモードであるかどうかに関係なく、どのアプリ/プロセスを起動するかを制御します。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="b3a7d-138">「WDAC の概要」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b3a7d-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
