---
title: CSP の構成とデバイス管理の概要
description: Mobile デバイス管理 およびプロビジョニング パッケージを使用して、CSP、ポリシー、デバイス管理を構成する方法について説明します。
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
ms.openlocfilehash: b312f9d20c9a75c5e4c1906c4ec55f42fda977f6
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640459"
---
# <a name="configure-csps-and-device-management-overview"></a><span data-ttu-id="88e83-103">CSP の構成とデバイス管理の概要</span><span class="sxs-lookup"><span data-stu-id="88e83-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="88e83-104">IT 管理者は、ポリシー設定を定義して実装HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="88e83-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="88e83-105">使用する構成設定は展開シナリオによって異なり、企業のデバイスは幅広い制御機能を IT 部門に提供します。</span><span class="sxs-lookup"><span data-stu-id="88e83-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="88e83-106">このWindows 10構成サービス プロバイダー (CSP) は、デバイスの構成設定を読み取り、設定、変更、または削除するインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="88e83-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="88e83-107">これらの設定は、レジストリ キーまたはファイルにマップされます。</span><span class="sxs-lookup"><span data-stu-id="88e83-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="88e83-108">一部の構成サービス プロバイダーは WAP 形式をサポートし、一部は SyncML をサポートし、一部は両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="88e83-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="88e83-109">デバイス管理の WINDOWS 10 HOLOGRAPHICの詳細については、デバイスでサポートされている CSP の完全な一[覧をHoloLensしてください](/windows/client-management/mdm/configuration-service-provider-reference#hololens)。</span><span class="sxs-lookup"><span data-stu-id="88e83-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="88e83-110">IT 管理者は、デバイスでポリシー CSP を管理することもできます。詳細については、 でサポートされているポリシー CSP の完全な一覧[をHoloLens 2。](/windows/client-management/mdm/policy-csps-supported-by-hololens2)</span><span class="sxs-lookup"><span data-stu-id="88e83-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <a name="configuration-methods"></a><span data-ttu-id="88e83-111">構成方法</span><span class="sxs-lookup"><span data-stu-id="88e83-111">Configuration methods</span></span>

### <a name="configure-with-mdm"></a><span data-ttu-id="88e83-112">MDM を使用して構成する</span><span class="sxs-lookup"><span data-stu-id="88e83-112">Configure with MDM</span></span>

<span data-ttu-id="88e83-113">CSP とポリシーは、MDM システムに登録されている個人または企業のデバイスで簡単に管理できます。</span><span class="sxs-lookup"><span data-stu-id="88e83-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="88e83-114">MDM ソリューションにデバイスを登録すると、そのデバイスまたはデバイスのセットをデバイス構成を使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="88e83-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="88e83-115">MDM を使用してデバイスを[管理する方法HoloLensを確認してください](hololens-mdm-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="88e83-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <a name="configure-with-provisioning-packages"></a><span data-ttu-id="88e83-116">プロビジョニング パッケージを使用して構成する</span><span class="sxs-lookup"><span data-stu-id="88e83-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="88e83-117">HoloLens 2では、カスタム プロビジョニング パッケージを使用して、HoloLens 2デバイスの CSP 構成の制限付きセットを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="88e83-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="88e83-118">プロビジョニング パッケージは通常、MDM 以外のマネージド デバイスに利用され、各デバイスに手動で適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88e83-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="88e83-119">のカスタム プロビジョニング パッケージの[構築に関する情報をHoloLens。](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="88e83-119">Read information on building custom [Provisioning Packages for HoloLens](hololens-provisioning.md).</span></span>

## <a name="configurations"></a><span data-ttu-id="88e83-120">構成</span><span class="sxs-lookup"><span data-stu-id="88e83-120">Configurations</span></span>

### <a name="common-device-restrictions"></a><span data-ttu-id="88e83-121">一般的なデバイスの制限</span><span class="sxs-lookup"><span data-stu-id="88e83-121">Common device restrictions</span></span>

<span data-ttu-id="88e83-122">一部のデバイスの制限は、デバイスへの機能または接続を無効にした単純な制限です。</span><span class="sxs-lookup"><span data-stu-id="88e83-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="88e83-123">これらの詳細については、一般的なデバイスの [制限に関する記事を参照してください。](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="88e83-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <a name="kiosk-modes"></a><span data-ttu-id="88e83-124">キオスク モード</span><span class="sxs-lookup"><span data-stu-id="88e83-124">Kiosk modes</span></span>

<span data-ttu-id="88e83-125">キオスク モードを使用して、既定でどの ID にどのアプリにアクセス権を持つのか制御します。</span><span class="sxs-lookup"><span data-stu-id="88e83-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="88e83-126">キオスクは、1 つのアプリまたは複数のアプリ UI エクスペリエンスに使用できます。</span><span class="sxs-lookup"><span data-stu-id="88e83-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="88e83-127">キオスク構成は、デバイスを使用するユーザー向け 1 つのアプリから、異なるグループのアプリの異なる選択まで、さまざまな範囲です。</span><span class="sxs-lookup"><span data-stu-id="88e83-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="88e83-128">キオスク モードでは、"許可されたアプリ" が他のアプリの起動を停止するのではなく、これまでは意図して動作しません。</span><span class="sxs-lookup"><span data-stu-id="88e83-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="88e83-129">詳細については、キオスク [モードと、その使い方に関する記事を参照してください](hololens-kiosk.md)。</span><span class="sxs-lookup"><span data-stu-id="88e83-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <a name="settings-page-visibility"></a><span data-ttu-id="88e83-130">設定ページの表示</span><span class="sxs-lookup"><span data-stu-id="88e83-130">Settings Page Visibility</span></span>

<span data-ttu-id="88e83-131">既定設定アクセス権を持つ ID を制御するには、アプリ ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="88e83-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="88e83-132">このポリシーを使用設定選択したページのみを表示するか、選択したページをすべて非表示にするようにアプリを構成できます。</span><span class="sxs-lookup"><span data-stu-id="88e83-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="88e83-133">[使用可能なページを構成する方法を参照してください](settings-uri-list.md)。</span><span class="sxs-lookup"><span data-stu-id="88e83-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="88e83-134">この機能は現在、Insider ビルド[の Windowsでのみ使用できます](hololens-insider.md)。</span><span class="sxs-lookup"><span data-stu-id="88e83-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="88e83-135">この機能を使用するデバイスがビルド 19041.1349 以上に含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="88e83-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <a name="wdac"></a><span data-ttu-id="88e83-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="88e83-136">WDAC</span></span>

<span data-ttu-id="88e83-137">WDAC 構成を使用して、システムがキオスク モードかどうかに関係なく、起動を許可/禁止するアプリ/プロセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="88e83-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="88e83-138">WDAC の概要を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88e83-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
