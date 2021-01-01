---
title: CSP の構成とデバイス管理の概要
description: CSP、ポリシー、デバイス管理を構成する方法。
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
ms.openlocfilehash: c6da29506035525b1b1b5141a04603f63de1ef24
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252778"
---
# <span data-ttu-id="239b7-103">CSP の構成とデバイス管理の概要</span><span class="sxs-lookup"><span data-stu-id="239b7-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="239b7-104">IT 管理者は、HoloLens 2 でポリシー設定を定義および実装できます。</span><span class="sxs-lookup"><span data-stu-id="239b7-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="239b7-105">使用する構成設定は展開シナリオによって異なり、企業のデバイスは幅広い制御機能を IT 部門に提供します。</span><span class="sxs-lookup"><span data-stu-id="239b7-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="239b7-106">Windows 10 では、構成サービス プロバイダー (CSP) は、デバイスの構成設定を読み取り、設定、変更、または削除するインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="239b7-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="239b7-107">これらの設定は、レジストリ キーまたはファイルにマップされます。</span><span class="sxs-lookup"><span data-stu-id="239b7-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="239b7-108">一部の構成サービス プロバイダーは WAP 形式をサポートし、一部は SyncML をサポートし、一部は両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="239b7-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="239b7-109">Windows 10 Holographic デバイス管理の CSP について詳しくは [、HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)デバイスでサポートされている CSP の一覧をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="239b7-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="239b7-110">IT 管理者はデバイスでポリシー CSP を管理することもできます [。HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)でサポートされているポリシー CSP の完全な一覧をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="239b7-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <span data-ttu-id="239b7-111">構成方法</span><span class="sxs-lookup"><span data-stu-id="239b7-111">Configuration methods</span></span>

### <span data-ttu-id="239b7-112">MDM を使用して構成する</span><span class="sxs-lookup"><span data-stu-id="239b7-112">Configure with MDM</span></span>

<span data-ttu-id="239b7-113">CSP とポリシーは、MDM システムに登録されている個人または企業のデバイスで簡単に管理できます。</span><span class="sxs-lookup"><span data-stu-id="239b7-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="239b7-114">MDM ソリューションにデバイスを登録すると、そのデバイスまたはデバイス構成を使用してデバイスのセットを管理できます。</span><span class="sxs-lookup"><span data-stu-id="239b7-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="239b7-115">MDM を使って [HoloLens デバイスを管理する方法について詳しくは、次をご覧ください](hololens-mdm-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="239b7-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <span data-ttu-id="239b7-116">プロビジョニング パッケージを使用して構成する</span><span class="sxs-lookup"><span data-stu-id="239b7-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="239b7-117">HoloLens 2 は、カスタム プロビジョニング パッケージによる HoloLens 2 デバイスの CSP 構成の制限されたセットの設定もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="239b7-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="239b7-118">プロビジョニング パッケージは、通常、MDM 以外の管理対象デバイスで利用され、各デバイスに手動で適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="239b7-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="239b7-119">[HoloLens 用のカスタム プロビジョニング パッケージの構築に関する情報を読み取る](https://docs.microsoft.com/hololens/hololens-provisioning)。</span><span class="sxs-lookup"><span data-stu-id="239b7-119">Read information on building custom [Provisioning Packages for HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span>

## <span data-ttu-id="239b7-120">構成</span><span class="sxs-lookup"><span data-stu-id="239b7-120">Configurations</span></span>

### <span data-ttu-id="239b7-121">一般的なデバイスの制限</span><span class="sxs-lookup"><span data-stu-id="239b7-121">Common device restrictions</span></span>

<span data-ttu-id="239b7-122">一部のデバイスの制限は単純で、機能やデバイスへの接続を無効にします。</span><span class="sxs-lookup"><span data-stu-id="239b7-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="239b7-123">これらの詳細については、一般的なデバイスの [制限に関する記事を参照してください。](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="239b7-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <span data-ttu-id="239b7-124">キオスク モード</span><span class="sxs-lookup"><span data-stu-id="239b7-124">Kiosk modes</span></span>

<span data-ttu-id="239b7-125">キオスク モードを使って、既定でどのアプリにアクセスできる ID を制御します。</span><span class="sxs-lookup"><span data-stu-id="239b7-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="239b7-126">キオスクは、1 つのアプリまたは複数のアプリの UI エクスペリエンスに使用できます。</span><span class="sxs-lookup"><span data-stu-id="239b7-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="239b7-127">キオスク構成は、デバイスを使うユーザー向け 1 つのアプリから、グループごとに異なる選択のアプリまでです。</span><span class="sxs-lookup"><span data-stu-id="239b7-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="239b7-128">キオスク モードでは、"許可されたアプリ" が他のアプリの起動を停止するのではなく、これまで意図された動作ではありません。</span><span class="sxs-lookup"><span data-stu-id="239b7-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="239b7-129">詳しくは、 [キオスク モードと使い方をご覧ください](hololens-kiosk.md)。</span><span class="sxs-lookup"><span data-stu-id="239b7-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <span data-ttu-id="239b7-130">[設定] ページの可視性</span><span class="sxs-lookup"><span data-stu-id="239b7-130">Settings Page Visibility</span></span>

<span data-ttu-id="239b7-131">設定アプリ ポリシーを使って、既定で設定にアクセスできる ID を制御します。</span><span class="sxs-lookup"><span data-stu-id="239b7-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="239b7-132">このポリシーを使って、選択したページのみを表示するか、選択したページを非表示にするように設定アプリを構成できます。</span><span class="sxs-lookup"><span data-stu-id="239b7-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="239b7-133">[使用可能なページを構成する方法についてお読みください](settings-uri-list.md)。</span><span class="sxs-lookup"><span data-stu-id="239b7-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="239b7-134">この機能は現在 [、Windows Insider ビルドでのみ利用できます](hololens-insider.md)。</span><span class="sxs-lookup"><span data-stu-id="239b7-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="239b7-135">この機能を使用するデバイスがビルド 19041.1349 以上のデバイスにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="239b7-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <span data-ttu-id="239b7-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="239b7-136">WDAC</span></span>

<span data-ttu-id="239b7-137">WDAC 構成を使って、システムがキオスク モードかどうかに関係なく、起動を許可/禁止するアプリ/プロセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="239b7-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="239b7-138">WDAC の概要をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="239b7-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
