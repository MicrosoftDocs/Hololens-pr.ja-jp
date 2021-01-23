---
title: CSP の構成とデバイス管理の概要
description: モバイル デバイス管理とプロビジョニング パッケージを使用して、CSP、ポリシー、デバイス管理を構成する方法について説明します。
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
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283248"
---
# <span data-ttu-id="a786e-103">CSP の構成とデバイス管理の概要</span><span class="sxs-lookup"><span data-stu-id="a786e-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="a786e-104">IT 管理者は、HoloLens 2 でポリシー設定を定義して実装できます。</span><span class="sxs-lookup"><span data-stu-id="a786e-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="a786e-105">使用する構成設定は展開シナリオによって異なり、企業のデバイスは幅広い制御機能を IT 部門に提供します。</span><span class="sxs-lookup"><span data-stu-id="a786e-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="a786e-106">Windows 10 では、構成サービス プロバイダー (CSP) は、デバイスの構成設定を読み取り、設定、変更、または削除するインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="a786e-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="a786e-107">これらの設定は、レジストリ キーまたはファイルにマップされます。</span><span class="sxs-lookup"><span data-stu-id="a786e-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="a786e-108">一部の構成サービス プロバイダーは WAP 形式をサポートし、一部は SyncML をサポートし、一部は両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="a786e-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="a786e-109">Windows 10 Holographic デバイス管理の CSP について詳しくは [、HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)デバイスでサポートされている CSP の一覧をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a786e-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="a786e-110">IT 管理者はデバイスでポリシー CSP を管理することもできます [。HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)でサポートされているポリシー CSP の完全な一覧をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a786e-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <span data-ttu-id="a786e-111">構成方法</span><span class="sxs-lookup"><span data-stu-id="a786e-111">Configuration methods</span></span>

### <span data-ttu-id="a786e-112">MDM を使用して構成する</span><span class="sxs-lookup"><span data-stu-id="a786e-112">Configure with MDM</span></span>

<span data-ttu-id="a786e-113">CSP とポリシーは、MDM システムに登録されている個人または企業のデバイスで簡単に管理できます。</span><span class="sxs-lookup"><span data-stu-id="a786e-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="a786e-114">MDM ソリューションにデバイスを登録すると、そのデバイスまたはデバイス構成を使用してデバイスのセットを管理できます。</span><span class="sxs-lookup"><span data-stu-id="a786e-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="a786e-115">MDM を使って [HoloLens デバイスを管理する方法について詳しくは、次をご覧ください](hololens-mdm-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="a786e-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <span data-ttu-id="a786e-116">プロビジョニング パッケージを使用して構成する</span><span class="sxs-lookup"><span data-stu-id="a786e-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="a786e-117">HoloLens 2 では、カスタム プロビジョニング パッケージによる HoloLens 2 デバイスの CSP 構成の制限付きセットの設定もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a786e-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="a786e-118">プロビジョニング パッケージは、通常、MDM 以外の管理対象デバイスで利用され、各デバイスに手動で適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a786e-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="a786e-119">[HoloLens 用のカスタム プロビジョニング パッケージの構築に関する情報を読み取る](https://docs.microsoft.com/hololens/hololens-provisioning)。</span><span class="sxs-lookup"><span data-stu-id="a786e-119">Read information on building custom [Provisioning Packages for HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span>

## <span data-ttu-id="a786e-120">構成</span><span class="sxs-lookup"><span data-stu-id="a786e-120">Configurations</span></span>

### <span data-ttu-id="a786e-121">一般的なデバイスの制限</span><span class="sxs-lookup"><span data-stu-id="a786e-121">Common device restrictions</span></span>

<span data-ttu-id="a786e-122">一部のデバイスの制限は単純で、機能やデバイスへの接続を無効にします。</span><span class="sxs-lookup"><span data-stu-id="a786e-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="a786e-123">これらの詳細については、一般的なデバイスの [制限に関する記事を参照してください。](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="a786e-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <span data-ttu-id="a786e-124">キオスク モード</span><span class="sxs-lookup"><span data-stu-id="a786e-124">Kiosk modes</span></span>

<span data-ttu-id="a786e-125">キオスク モードを使って、既定でどのアプリにアクセスできる ID を制御します。</span><span class="sxs-lookup"><span data-stu-id="a786e-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="a786e-126">キオスクは、1 つのアプリまたは複数のアプリの UI エクスペリエンスに使用できます。</span><span class="sxs-lookup"><span data-stu-id="a786e-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="a786e-127">キオスク構成は、デバイスを使うユーザー向け 1 つのアプリから、グループごとに異なる選択のアプリまでです。</span><span class="sxs-lookup"><span data-stu-id="a786e-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="a786e-128">キオスク モードでは、"許可されたアプリ" が他のアプリの起動を停止するのではなく、これまで意図された動作ではありません。</span><span class="sxs-lookup"><span data-stu-id="a786e-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="a786e-129">詳しくは、 [キオスク モードと使い方に関する記事をご覧ください](hololens-kiosk.md)。</span><span class="sxs-lookup"><span data-stu-id="a786e-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <span data-ttu-id="a786e-130">[設定] ページの可視性</span><span class="sxs-lookup"><span data-stu-id="a786e-130">Settings Page Visibility</span></span>

<span data-ttu-id="a786e-131">設定アプリ ポリシーを使って、既定で設定にアクセスできる ID を制御します。</span><span class="sxs-lookup"><span data-stu-id="a786e-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="a786e-132">このポリシーを使って、選択したページのみを表示するか、選択したページを非表示にするように設定アプリを構成できます。</span><span class="sxs-lookup"><span data-stu-id="a786e-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="a786e-133">[使用可能なページを構成する方法についてお読みください](settings-uri-list.md)。</span><span class="sxs-lookup"><span data-stu-id="a786e-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="a786e-134">この機能は現在 [、Windows Insider ビルドでのみ使用できます](hololens-insider.md)。</span><span class="sxs-lookup"><span data-stu-id="a786e-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="a786e-135">この機能を使用するデバイスがビルド 19041.1349 以上のデバイスにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a786e-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <span data-ttu-id="a786e-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="a786e-136">WDAC</span></span>

<span data-ttu-id="a786e-137">WDAC 構成を使って、システムがキオスク モードかどうかに関係なく、起動を許可/禁止するアプリ/プロセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="a786e-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="a786e-138">WDAC の概要をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a786e-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
