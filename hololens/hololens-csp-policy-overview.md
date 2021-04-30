---
title: Csp およびデバイス管理の構成の概要
description: モバイルデバイス管理とプロビジョニングパッケージを使用して、Csp、ポリシー、およびデバイス管理を構成する方法について説明します。
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309721"
---
# <a name="configure-csps-and-device-management-overview"></a><span data-ttu-id="687e8-103">Csp およびデバイス管理の構成の概要</span><span class="sxs-lookup"><span data-stu-id="687e8-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="687e8-104">IT 管理者は、HoloLens 2 でポリシー設定を定義および実装できます。</span><span class="sxs-lookup"><span data-stu-id="687e8-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="687e8-105">使用する構成設定は展開シナリオによって異なり、企業のデバイスは幅広い制御機能を IT 部門に提供します。</span><span class="sxs-lookup"><span data-stu-id="687e8-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="687e8-106">Windows 10 では、構成サービスプロバイダー (CSP) は、デバイスの構成設定を読み取り、設定、変更、または削除するためのインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="687e8-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="687e8-107">これらの設定は、レジストリ キーまたはファイルにマップされます。</span><span class="sxs-lookup"><span data-stu-id="687e8-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="687e8-108">一部の構成サービスプロバイダーは、WAP 形式をサポートしています。また、SyncML をサポートしており、その両方をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="687e8-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="687e8-109">Windows 10 Holographic デバイス管理 Csp の詳細については、「 [HoloLens デバイスでサポートされる csp](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)の完全な一覧」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="687e8-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="687e8-110">IT 管理者は、デバイスでポリシー CSP を管理することもできます。 [HoloLens 2 でサポートされているポリシー](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)csp の完全な一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="687e8-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <a name="configuration-methods"></a><span data-ttu-id="687e8-111">構成方法</span><span class="sxs-lookup"><span data-stu-id="687e8-111">Configuration methods</span></span>

### <a name="configure-with-mdm"></a><span data-ttu-id="687e8-112">MDM を使用して構成する</span><span class="sxs-lookup"><span data-stu-id="687e8-112">Configure with MDM</span></span>

<span data-ttu-id="687e8-113">Csp とポリシーは、MDM システムに登録されている個人または会社のデバイスで簡単に管理できます。</span><span class="sxs-lookup"><span data-stu-id="687e8-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="687e8-114">デバイスが MDM ソリューションに登録されると、そのデバイスを管理できるようになり、デバイスの構成を使用してデバイスのセットを管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="687e8-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="687e8-115">MDM を使用して [HoloLens デバイスを管理](hololens-mdm-configure.md)する方法の詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="687e8-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <a name="configure-with-provisioning-packages"></a><span data-ttu-id="687e8-116">プロビジョニングパッケージを使用して構成する</span><span class="sxs-lookup"><span data-stu-id="687e8-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="687e8-117">HoloLens 2 では、カスタムプロビジョニングパッケージを使用して、HoloLens 2 デバイスに限定された CSP 構成を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="687e8-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="687e8-118">プロビジョニングパッケージは、通常、MDM 以外の管理対象デバイスに使用され、各デバイスに手動で適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="687e8-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="687e8-119">[HoloLens 用カスタムプロビジョニングパッケージ](https://docs.microsoft.com/hololens/hololens-provisioning)の構築については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="687e8-119">Read information on building custom [Provisioning Packages for HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span>

## <a name="configurations"></a><span data-ttu-id="687e8-120">構成</span><span class="sxs-lookup"><span data-stu-id="687e8-120">Configurations</span></span>

### <a name="common-device-restrictions"></a><span data-ttu-id="687e8-121">一般的なデバイスの制限</span><span class="sxs-lookup"><span data-stu-id="687e8-121">Common device restrictions</span></span>

<span data-ttu-id="687e8-122">デバイスの制限としては、単純に、デバイスへの機能や接続を無効にすることがあります。</span><span class="sxs-lookup"><span data-stu-id="687e8-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="687e8-123">これらの詳細については、[一般的なデバイスの制限](hololens-common-device-restrictions.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="687e8-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <a name="kiosk-modes"></a><span data-ttu-id="687e8-124">キオスクモード</span><span class="sxs-lookup"><span data-stu-id="687e8-124">Kiosk modes</span></span>

<span data-ttu-id="687e8-125">キオスクモードを使用すると、どの id が既定でどのアプリにアクセスできるかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="687e8-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="687e8-126">キオスクは、1つのアプリまたは複数のアプリの UI エクスペリエンスに使用できます。</span><span class="sxs-lookup"><span data-stu-id="687e8-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="687e8-127">キオスクの構成は、デバイスを使用するすべてのユーザーを対象とした1つのアプリから、さまざまなグループに対して異なるアプリを選択できます。</span><span class="sxs-lookup"><span data-stu-id="687e8-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="687e8-128">キオスクモードでは、"許可されたアプリ" が他のアプリの起動を停止することはなく、これまでは想定されていませんでした。</span><span class="sxs-lookup"><span data-stu-id="687e8-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="687e8-129">[キオスクモードとその使用方法については](hololens-kiosk.md)、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="687e8-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <a name="settings-page-visibility"></a><span data-ttu-id="687e8-130">[設定] ページの表示</span><span class="sxs-lookup"><span data-stu-id="687e8-130">Settings Page Visibility</span></span>

<span data-ttu-id="687e8-131">設定アプリポリシーを使用して、既定で設定にアクセスできる id を制御します。</span><span class="sxs-lookup"><span data-stu-id="687e8-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="687e8-132">このポリシーを使用して、設定アプリを構成して、選択したページのみを表示するか、選択したすべてのページを非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="687e8-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="687e8-133">[ページを構成する方法については、「」を参照して](settings-uri-list.md)ください。</span><span class="sxs-lookup"><span data-stu-id="687e8-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="687e8-134">この機能は、現在、 [Windows Insider ビルド](hololens-insider.md)でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="687e8-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="687e8-135">この機能を使用する予定のデバイスがビルド 19041.1349 + にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="687e8-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <a name="wdac"></a><span data-ttu-id="687e8-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="687e8-136">WDAC</span></span>

<span data-ttu-id="687e8-137">システムがキオスクモードであるかどうかに関係なく、どのアプリ/プロセスを起動できるかを制御するには、WDAC 構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="687e8-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="687e8-138">「WDAC の概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="687e8-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
