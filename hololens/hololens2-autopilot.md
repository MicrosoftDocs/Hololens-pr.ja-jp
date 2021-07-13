---
title: Windows Autopilot for HoloLens 2
description: HoloLens 2 デバイスで Autopilot をセットアップ、構成、およびトラブルシューティングする方法を説明します。
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/13/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Autopilot
manager: jarrettr
ms.openlocfilehash: 10a577cf77a5c6faf0e7e07fa2fd5ad8603ec5ae
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923654"
---
# <a name="windows-autopilot-for-hololens-2"></a><span data-ttu-id="caa4d-104">Windows Autopilot for HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="caa4d-104">Windows Autopilot for HoloLens 2</span></span>

<span data-ttu-id="caa4d-105">Windows Holographic バージョン 2004 より、HoloLens 2 では Microsoft Intune を使用して Windows Autopilot [自己展開モード](https://docs.microsoft.com/mem/autopilot/self-deploying)がサポートされています (サードパーティの MDM はサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="caa4d-105">Starting with Windows Holographic version 2004, HoloLens 2 supports Windows Autopilot [Self-Deploying Mode](https://docs.microsoft.com/mem/autopilot/self-deploying) with Microsoft Intune (3rd party MDMs are not supported).</span></span> <span data-ttu-id="caa4d-106">管理者は、Microsoft エンドポイント マネージャーでOut-of-box experience (OOBE) を構成できます。また、エンドユーザーは、ほとんどの操作なしで、ビジネス用のデバイスを準備することができます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-106">Administrators can configure the out-of-box experience (OOBE) in Microsoft Endpoint Manager and enable end-users to prepare devices for business use with little to no interaction.</span></span> <span data-ttu-id="caa4d-107">これにより、セットアップ エクスペリエンスの際に、在庫管理のオーバーヘッド、実地で使用するデバイス準備のコスト、および従業員からの通話のサポートが削減されます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-107">This reduces inventory management overhead, cost of hands-on device preparation and support calls from employees during the setup experience.</span></span> <span data-ttu-id="caa4d-108">詳細については、[Windows Autopilot](https://docs.microsoft.com/mem/autopilot/windows-autopilot) のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="caa4d-108">Learn more in the [Windows Autopilot](https://docs.microsoft.com/mem/autopilot/windows-autopilot) documentation.</span></span>

<span data-ttu-id="caa4d-109">Surface デバイスの場合と同様に、お客様が Microsoft [クラウド ソリューション プロバイダー](https://partner.microsoft.com/cloud-solution-provider)(販売店または卸売業者) と協力して、パートナー センターを通じてAutopilot サービスにデバイスに登録することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="caa4d-109">Like for Surface devices, it is recommended that customers work with their Microsoft [Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) (reseller or distributor) to get devices registered with the Autopilot service through Partner Center.</span></span> <span data-ttu-id="caa4d-110">デバイス登録のその他の方法については、[デバイスの追加](https://docs.microsoft.com/mem/autopilot/add-devices)ドキュメントに説明されていますが、Microsoft のチャネル パートナーを活用すると、最も有効なエンドツーエンドのパスを確実に実現できます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-110">Other methods for device registration are outlined in the [add device](https://docs.microsoft.com/mem/autopilot/add-devices) documentation, though leveraging Microsoft's channel partners ensures the most effective end-to-end path.</span></span>

> [!NOTE]
> <span data-ttu-id="caa4d-111">11/20/2020 時点で、Microsoft エンドポイント マネージャーでの HoloLens 用 Autopilot の構成は、**パブリック プレビュー** に移行中 です。</span><span class="sxs-lookup"><span data-stu-id="caa4d-111">As of 11/20/2020 Autopilot configuration for HoloLens in Microsoft Endpoint Manager is transitioning to **Public Preview**.</span></span> <span data-ttu-id="caa4d-112">お客様はプライベート プレビューに登録する必要がなくなりました。すべてのテナントは、MEM 管理センターでAutopilot を設定することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-112">Customers no longer need to enroll in the private preview and all tenants will be able to setup Autopilot in the MEM admin center.</span></span>

<span data-ttu-id="caa4d-113">ユーザーが Autopilot の自動展開プロセスを開始すると、Autopilot が次の手順を完了します:</span><span class="sxs-lookup"><span data-stu-id="caa4d-113">When a user starts the Autopilot self-deploying process, Autopilot completes the following steps:</span></span>

1. <span data-ttu-id="caa4d-114">デバイスを Azure Active Directory (Azure AD) に参加させます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-114">Join the device to Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="caa4d-115">Autopilot for HoloLens は、Active Directory への参加またはハイブリッド Azure AD への参加をサポートしていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="caa4d-115">Note that Autopilot for HoloLens does not support Active Directory join or Hybrid Azure AD join.</span></span>

1. <span data-ttu-id="caa4d-116">Azure AD を使用して、デバイスを Microsoft エンドポイント マネージャー (または別の MDM サービス) に登録します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-116">Use Azure AD to enroll the device in Microsoft Endpoint Manager (or another MDM service).</span></span>

1. <span data-ttu-id="caa4d-117">デバイスを対象としたポリシー、証明書、ネットワーク プロファイル、アプリケーションをダウンロードして適用します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-117">Download and apply device-targeted policies, certificates, networking profiles and applications.</span></span>

1. <span data-ttu-id="caa4d-118">デバイスをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="caa4d-118">Provision the device.</span></span>

1. <span data-ttu-id="caa4d-119">ユーザーにサインイン画面を提示します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-119">Present the sign-in screen to the user.</span></span>

## <a name="configuring-autopilot-for-hololens-2"></a><span data-ttu-id="caa4d-120">Autopilot for HoloLens 2 を構成する</span><span class="sxs-lookup"><span data-stu-id="caa4d-120">Configuring Autopilot for HoloLens 2</span></span>

<span data-ttu-id="caa4d-121">環境をセット アップするには、次の手順に従ってください:</span><span class="sxs-lookup"><span data-stu-id="caa4d-121">Please follow the steps below to set up your environment:</span></span>

1. [<span data-ttu-id="caa4d-122">Windows Autopilot for HoloLens 2 の要件を確認します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-122">Review requirements for Windows Autopilot for HoloLens 2.</span></span>](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [<span data-ttu-id="caa4d-123">MDM の自動登録を有効にする</span><span class="sxs-lookup"><span data-stu-id="caa4d-123">Enable Automatic MDM Enrollment</span></span>](#2-enable-automatic-mdm-enrollment)

1. [<span data-ttu-id="caa4d-124">Windows Autopilot にデバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-124">Register devices in Windows Autopilot.</span></span>](#3-register-devices-in-windows-autopilot)

1. [<span data-ttu-id="caa4d-125">デバイス グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-125">Create a device group.</span></span>](#4-create-a-device-group)

1. [<span data-ttu-id="caa4d-126">展開プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-126">Create a deployment profile.</span></span>](#5-create-a-deployment-profile)

1. [<span data-ttu-id="caa4d-127">登録状態ページ (ESP) の構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-127">Verify the Enrollment Status Page (ESP) configuration.</span></span>](#6-verify-the-esp-configuration)

1. [<span data-ttu-id="caa4d-128">HoloLens デバイスのプロファイルの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-128">Verify the profile status of the HoloLens devices.</span></span>](#7-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a><span data-ttu-id="caa4d-129">1. Windows Autopilot for HoloLens 2 の要件を確認します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-129">1. Review requirements for Windows Autopilot for HoloLens 2</span></span>

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a><span data-ttu-id="caa4d-130">Windows Autopilot の要件に関する記事の次のセクションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="caa4d-130">Review the following sections of the Windows Autopilot requirements article:</span></span>

- [<span data-ttu-id="caa4d-131">ネットワークの要件</span><span class="sxs-lookup"><span data-stu-id="caa4d-131">Network requirements</span></span>](https://docs.microsoft.com/mem/autopilot/networking-requirements)  
- [<span data-ttu-id="caa4d-132">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="caa4d-132">Licensing requirements</span></span>](https://docs.microsoft.com/mem/autopilot/licensing-requirements)  
- [<span data-ttu-id="caa4d-133">構成要件</span><span class="sxs-lookup"><span data-stu-id="caa4d-133">Configuration requirements</span></span>](https://docs.microsoft.com/mem/autopilot/configuration-requirements)

<span data-ttu-id="caa4d-134">**Windows Autopilot 自己展開モードに関する記事の「[要件](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)」のセクションを確認してください。**</span><span class="sxs-lookup"><span data-stu-id="caa4d-134">**Review the "[Requirements](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" section of the Windows Autopilot Self-Deploying mode article.**</span></span> <span data-ttu-id="caa4d-135">お客様の環境が、これらの要件に加えて、標準的な Windows Autopilot の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-135">Your environment has to meet these requirements as well as the standard Windows Autopilot requirements.</span></span> <span data-ttu-id="caa4d-136">記事の「ステップ バイ ステップ」と「検証」のセクションを確認する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="caa4d-136">You do not have to review the "Step by step" and "Validation" sections of the article.</span></span> <span data-ttu-id="caa4d-137">この記事の後半の手順では、HoloLens に固有の対応する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-137">The procedures later in this article provide corresponding steps that are specific to HoloLens.</span></span>

<span data-ttu-id="caa4d-138">デバイスを登録してプロファイルを構成する方法については、この記事の[「2.Windows Autopilot にデバイスを登録する」](#3-register-devices-in-windows-autopilot)と[「4. 展開プロファイルを作成する」](#5-create-a-deployment-profile)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="caa4d-138">For information about how to register devices and configure profiles, see [2. Register devices in Windows Autopilot](#3-register-devices-in-windows-autopilot) and [4. Create a deployment profile](#5-create-a-deployment-profile) in this article.</span></span> <span data-ttu-id="caa4d-139">Autopilot 自己展開モード プロファイルを構成して管理するには、[Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com)にアクセスできることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="caa4d-139">To configure and manage the Autopilot self-deploying mode profiles, make sure that you have access to [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com).</span></span>

#### <a name="review-hololens-os-requirements"></a><span data-ttu-id="caa4d-140">HoloLens OS の要件を確認します:</span><span class="sxs-lookup"><span data-stu-id="caa4d-140">Review HoloLens OS requirements:</span></span>

- <span data-ttu-id="caa4d-141">デバイスは、[Windows Holographic、バージョン 2004](hololens-release-notes.md#windows-holographic-version-2004) (build 19041.1103) 以降にインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-141">Devices must be on [Windows Holographic, version 2004](hololens-release-notes.md#windows-holographic-version-2004) (build 19041.1103) or later.</span></span> <span data-ttu-id="caa4d-142">デバイスのビルド バージョンを確認するか、最新の OS に再フラッシュするには、[Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) と[デバイスの再フラッシュ手順](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)を使用します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-142">To confirm the build version on your device or re-flash to the latest OS, use the [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) and our [device re-flash instructions](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span> <span data-ttu-id="caa4d-143">2020 年 9 月の後半までに配信されたデバイスには、Windows Holographic バージョン 1903 がプリインストールされていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="caa4d-143">Note that devices delivered until late September 2020 have Windows Holographic version 1903 pre-installed.</span></span> <span data-ttu-id="caa4d-144">販売業者に連絡して、Autopilot 対応のデバイスが発送されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="caa4d-144">Please contact your reseller to ensure that Autopilot-ready devices are shipped to you.</span></span>

- <span data-ttu-id="caa4d-145">Windows Holographic、バージョン 2004 では、イーサネット接続経由の Autopilot のみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="caa4d-145">Windows Holographic, version 2004 only supports Autopilot over ethernet connection.</span></span> <span data-ttu-id="caa4d-146">**電源を入れる前に**、「USB-C to Ethernet」アダプターを使って、HoloLens が イーサネットに接続されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-146">Ensure the HoloLens is connected to ethernet using a "USB-C to Ethernet" adapter **before turning it on**.</span></span> <span data-ttu-id="caa4d-147">デバイスの起動時に、ユーザーの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="caa4d-147">Upon device boot no user interaction is required.</span></span> <span data-ttu-id="caa4d-148">多くの HoloLens デバイスに Autopilot ロールアウトを計画している場合は、アダプター インフラストラクチャの計画を立てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="caa4d-148">If you are planning for an Autopilot roll-out to many HoloLens devices, we recommend that you plan for the adapter infrastructure.</span></span> <span data-ttu-id="caa4d-149">USB ハブは、HoloLens でサポートされていないサードパーティ製のドライバーを追加でインストールすることを要求することが多いため、お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="caa4d-149">We do not recommend USB Hubs, as they often require additional third-party drivers to be installed which is not supported on HoloLens.</span></span>

- <span data-ttu-id="caa4d-150">[Windows Holographic、バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (ビルド 19041.1128) 以降では、Wi-Fi 経由の Autopilot がサポートされています。ただし、イーサネット アダプターを引き続き使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-150">[Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (build 19041.1128) or later support Autopilot over Wi-Fi, although you may still use ethernet adapters.</span></span> <span data-ttu-id="caa4d-151">Wi-fi 経由で接続されているデバイスの場合、ユーザーは次のことのみを行う必要があります:</span><span class="sxs-lookup"><span data-stu-id="caa4d-151">For devices connected via Wi-fi, the user must only:</span></span>

     - <span data-ttu-id="caa4d-152">ハチドリのシーンに移動する</span><span class="sxs-lookup"><span data-stu-id="caa4d-152">Go through the hummingbird scene</span></span>
     - <span data-ttu-id="caa4d-153">言語とロケールを選ぶ</span><span class="sxs-lookup"><span data-stu-id="caa4d-153">Choose the language and locale</span></span>
     - <span data-ttu-id="caa4d-154">視線の調整を実行</span><span class="sxs-lookup"><span data-stu-id="caa4d-154">Run eye-calibration</span></span>
     - <span data-ttu-id="caa4d-155">ネットワーク接続を確立する</span><span class="sxs-lookup"><span data-stu-id="caa4d-155">Establish network connection</span></span>

- <span data-ttu-id="caa4d-156">Windows Holographic、バージョン 20H2 では、 [Tenantlockdown CSP と Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot) をサポートしています。これにより、デバイスがテナントにロックされ、偶発的または故意にリセットまたはワイプが行われた場合でも、デバイスがそのテナントにバインドされたままになります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-156">Windows Holographic, version 20H2 supports [Tenantlockdown CSP and Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot), which locks a device to a tenant and  ensures that the device remains bound to that tenant in case of accidental or intentional resets or wipes.</span></span>  

- <span data-ttu-id="caa4d-157">デバイスがまだ Azure AD のメンバーではなく、Intune (または別の MDM システム) に登録されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-157">Ensure that the devices are not already members of Azure AD, and are not enrolled in Intune (or another MDM system).</span></span> <span data-ttu-id="caa4d-158">Autopilot の自己展開プロセスが、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-158">The Autopilot self-deploying process completes these steps.</span></span> <span data-ttu-id="caa4d-159">デバイス関連のすべての情報がクリーン アップされていることを確認するには、Azure AD および Intune ポータル の両方の **デバイス** ページを確認します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-159">To make sure that all the device-related information is cleaned up, check the **Devices** pages in both Azure AD and Intune Portals.</span></span> <span data-ttu-id="caa4d-160">現時点では、HoloLens で [すべての対象デバイスを Autopilot に変換する] 機能はサポートされていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="caa4d-160">Note that "Convert all targeted devices to Autopilot" feature is not supported on HoloLens at the moment.</span></span>  

### <a name="2-enable-automatic-mdm-enrollment"></a><span data-ttu-id="caa4d-161">2. MDM の自動登録を有効にする</span><span class="sxs-lookup"><span data-stu-id="caa4d-161">2. Enable Automatic MDM Enrollment:</span></span>

<span data-ttu-id="caa4d-162">Autopilot を正常に実行するには、Azure Portal で MDM の自動登録を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-162">In order for Autopilot to succeed you'll need to enable Automatic MDM Enrollment in your Azure portal.</span></span> <span data-ttu-id="caa4d-163">これにより、デバイスはユーザーなしで登録できるようになります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-163">This will enable the device to enroll without a user.</span></span>

<span data-ttu-id="caa4d-164">[Azure portal](https://portal.azure.com/#home) で、 **[Azure Active Directory]**  ->  **[モビリティ (MDM および MAM)]**  ->  **[Microsoft Intune]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-164">In the [Azure portal](https://portal.azure.com/#home) select **Azure Active Directory** -> **Mobility (MDM and MAM)** -> **Microsoft Intune**.</span></span> <span data-ttu-id="caa4d-165">次に、**MDM ユーザー スコープ** を構成します。 **[すべて]** を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-165">Then configure the **MDM user scope**, you will need to select **All**.</span></span>

<span data-ttu-id="caa4d-166">設定の詳細については、[MDM自動登録の有効化に関する次の短いガイド](https://docs.microsoft.com/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal)または[自動登録クイック スタート ガイド](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="caa4d-166">Please review the following short [guide on enabling MDM Automatic Enrollment](https://docs.microsoft.com/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) or the [Auto Enrollment Quick start guide](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment) for even more information getting set up.</span></span>

### <a name="3-register-devices-in-windows-autopilot"></a><span data-ttu-id="caa4d-167">3. Windows Autopilot にデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="caa4d-167">3. Register devices in Windows Autopilot</span></span>

<span data-ttu-id="caa4d-168">最初のセットアップの前に、お使いのデバイスが Windows Autopilot に登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-168">Your devices must be registered in Windows Autopilot before first setup.</span></span> <span data-ttu-id="caa4d-169">デバイス登録に関する MEM ドキュメントについては、[「Autopilot へのデバイスの追加」](https://docs.microsoft.com/mem/autopilot/add-devices)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="caa4d-169">For MEM documentation on device registration please see [Adding devices to Autopilot](https://docs.microsoft.com/mem/autopilot/add-devices).</span></span>  

<span data-ttu-id="caa4d-170">HoloLens デバイスを登録する主な方法は 3 つあります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-170">There are three primary ways to register HoloLens devices:</span></span>

 - <span data-ttu-id="caa4d-171">**販売業者は、注文時にパートナー センターにデバイスを登録できます。**</span><span class="sxs-lookup"><span data-stu-id="caa4d-171">**Reseller can register devices in the Partner Center when you place an order.**</span></span>

   > [!NOTE]  
   > <span data-ttu-id="caa4d-172">これは、デバイスを Autopilot サービスに追加する際に推奨されるパスです。</span><span class="sxs-lookup"><span data-stu-id="caa4d-172">This is the recommended path for adding devices to the Autopilot service.</span></span> <span data-ttu-id="caa4d-173">[詳細については、こちらを参照してください](https://docs.microsoft.com/mem/autopilot/partner-registration)。</span><span class="sxs-lookup"><span data-stu-id="caa4d-173">[Learn more](https://docs.microsoft.com/mem/autopilot/partner-registration).</span></span>  

 - <span data-ttu-id="caa4d-174">**サポートリクエスト[は、Microsoft に直接](hololens2-autopilot-registration-support.md) 送信できます。**</span><span class="sxs-lookup"><span data-stu-id="caa4d-174">**You can [submit a support request](hololens2-autopilot-registration-support.md) directly to Microsoft.**</span></span>
 - <span data-ttu-id="caa4d-175">**ハードウェア ハッシュ (ハードウェア ID とも呼ばれる) を取得し、MEM 管理センター にデバイスを手動で登録します**。</span><span class="sxs-lookup"><span data-stu-id="caa4d-175">**Retrieve the hardware hash (also known as the hardware ID) and register the device manually in MEM admin center**.</span></span>

#### <a name="obtain-hardware-hash"></a><span data-ttu-id="caa4d-176">ハードウェア ハッシュを取得する</span><span class="sxs-lookup"><span data-stu-id="caa4d-176">Obtain hardware hash</span></span>
<span data-ttu-id="caa4d-177">ハードウェア ハッシュを取得するには、2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-177">There are two ways to retrieve the hardware hash.</span></span>
1. <span data-ttu-id="caa4d-178">[サポートリクエストは、Microsoft に直接](hololens2-autopilot-registration-support.md) 送信できます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-178">You can [submit a support request](hololens2-autopilot-registration-support.md) directly to Microsoft.</span></span>
2. <span data-ttu-id="caa4d-179">これはデバイスから取得できます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-179">You can retrieve it from the device.</span></span> <span data-ttu-id="caa4d-180">デバイスは、OOBE プロセスの間、または後ほどデバイスの所有者が診断ログの収集プロセス ( 次の手順で説明します ) を開始したときに、そのハードウェア ハッシュを CSV ファイルに記録します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-180">The device records its hardware hash in a CSV file during the OOBE process, or later when a device owner starts the diagnostic log collection process (described in the following procedure).</span></span> <span data-ttu-id="caa4d-181">通常、デバイスの所有者がデバイスにサインインする最初のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="caa4d-181">Typically, the device owner is the first user to sign in to the device.</span></span>
     > [!WARNING]
     > <span data-ttu-id="caa4d-182">20H2 より前のビルドでは、OOBE を実行し、テレメトリが [必須] に設定されている場合、このメソッドを使用して Autopilot のハードウェア ハッシュを収集することはできません。</span><span class="sxs-lookup"><span data-stu-id="caa4d-182">In builds prior to 20H2, if you have gone through OOBE and the telemetry was set to Required, you cannot collect the hardware hash for Autopilot through this method.</span></span> <span data-ttu-id="caa4d-183">この方法を使用してハードウェア ハッシュを収集するには、設定 アプリを使用してテレメトリ オプションを [完全] に設定し、[プライバシー] -[診断] を選択します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-183">In          order to collect your hardware hash via this method set your telemetry option to Full via the Settings App and select Privacy -> Diagnostics.</span></span>

    1. <span data-ttu-id="caa4d-184">HoloLens 2 デバイスを起動します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-184">Start the HoloLens 2 device.</span></span>

    1. <span data-ttu-id="caa4d-185">デバイスで、 **[電源]** ボタンと **[ボリューム ダウン]** ボタンを同時に押し、それらを離します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-185">On the device, press the **Power** and **Volume Down** buttons at the same time and then release them.</span></span> <span data-ttu-id="caa4d-186">デバイスは診断ログとハードウェア ハッシュを収集し、それらを一連の .zip ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-186">The device collects diagnostic logs and the hardware hash, and stores them in a set of .zip files.</span></span>

   1. <span data-ttu-id="caa4d-187">詳細とこれを実行する方法の説明ビデオについては、[オフライン診断](hololens-diagnostic-logs.md#offline-diagnostics)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="caa4d-187">For full details and an instructional video for how to preform this please read about [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span>

    1. <span data-ttu-id="caa4d-188">USB-C ケーブルを使用して、コンピューターにデバイスを接続します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-188">Use a USB-C cable to connect the device to a computer.</span></span>

    1. <span data-ttu-id="caa4d-189">コンピューターで、エクスプローラーを開きます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-189">On the computer, open File Explorer.</span></span> <span data-ttu-id="caa4d-190">**[この PC]\\\<*HoloLens device name*>\\[内部ストレージ]\\[ドキュメント]** を開き、AutopilotDiagnostics.zip ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-190">Open **This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents**, and locate the AutopilotDiagnostics.zip file.</span></span>  

       > [!NOTE]  
       > <span data-ttu-id="caa4d-191">.zip ファイルはすぐに使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-191">The .zip file may not immediately be available.</span></span> <span data-ttu-id="caa4d-192">ファイルの準備ができていない場合は、[ドキュメント] フォルダーに HoloLensDiagnostics ファイルが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-192">If the file is not ready yet you may see a HoloLensDiagnostics.temp file in the Documents folder.</span></span> <span data-ttu-id="caa4d-193">ファイルの一覧を更新するには、ウィンドウを更新します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-193">To update the list of files, refresh the window.</span></span>
    
    1. <span data-ttu-id="caa4d-194">AutopilotDiagnostics.zip ファイルの内容を抽出します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-194">Extract the contents of the AutopilotDiagnostics.zip file.</span></span>

    1. <span data-ttu-id="caa4d-195">抽出されたファイルで、ファイル名に "DeviceHash" プレフィックスが付いた CSV ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-195">In the extracted files, locate the CSV file that has a file name prefix of "DeviceHash."</span></span> <span data-ttu-id="caa4d-196">そのファイルをコンピューターのドライブに保存し、後でアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="caa4d-196">Copy that file to a drive on the computer where you can access it later.</span></span>  

       > [!IMPORTANT]  
       > <span data-ttu-id="caa4d-197">CSV ファイル内のデータには、次のヘッダーと行の形式が使用されます:</span><span class="sxs-lookup"><span data-stu-id="caa4d-197">The data in the CSV file should use the following header and line format:</span></span>
       > ```
       > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
       >```

#### <a name="register-device-through-mem"></a><span data-ttu-id="caa4d-198">MEM でデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="caa4d-198">Register device through MEM</span></span>

1. <span data-ttu-id="caa4d-199">[Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com)で、 **[デバイス]**  >  **[Windows]**  >  **[Windows 加入契約]** を選択し、次に **Windows Autopilot 展開プログラム** 下で **[デバイス]**  >  **[インポート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-199">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Devices** > **Windows** > **Windows enrollment**, and then select **Devices** > **Import** under **Windows Autopilot Deployment Program**.</span></span>

1. <span data-ttu-id="caa4d-200">**[Windows Autopilot デバイスの追加]** で、DeviceHash CSV ファイルを選択し、 **[開く]** を選択して、 **[インポート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-200">Under **Add Windows Autopilot devices**, select the DeviceHash CSV file, select **Open**, and then select **Import**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="caa4d-201">![インポート コマンドを使用して、ハードウェア ハッシュをインポートします。](./images/hololens-ap-hash-import.png)</span><span class="sxs-lookup"><span data-stu-id="caa4d-201">![Use the Import command to import the hardware hash.](./images/hololens-ap-hash-import.png)</span></span>

1. <span data-ttu-id="caa4d-202">インポートが完了したら、 **[デバイス]**  >  **[Windows]**  >  **[Windows 加入契約]**  >  **[デバイス]**  >  **[同期]** を選択します。同期されているデバイスの数によっては、プロセスが完了するには数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-202">After the import finishes, select **Devices** > **Windows** > **Windows enrollment** > **Devices** > **Sync**. The process might take a few minutes to complete, depending on how many devices are being synchronized.</span></span> <span data-ttu-id="caa4d-203">登録済みのデバイスを表示するには、 **[更新]** を選択し ます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-203">To see the registered device, select **Refresh**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="caa4d-204">![[同期] および [更新] のコマンドを使用して、デバイスの一覧を表示します。](./images/hololens-ap-devices-sync.png)</span><span class="sxs-lookup"><span data-stu-id="caa4d-204">![Use the Sync and Refresh commands to view the device list.](./images/hololens-ap-devices-sync.png)</span></span>  

### <a name="4-create-a-device-group"></a><span data-ttu-id="caa4d-205">4. デバイス グループを作成する</span><span class="sxs-lookup"><span data-stu-id="caa4d-205">4. Create a device group</span></span>

1. <span data-ttu-id="caa4d-206">[Microsoft エンドポイント　管理者センター](https://endpoint.microsoft.com)で、 **[グループ]**  >  **[新しいグループ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-206">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Groups** > **New group**.</span></span>

1. <span data-ttu-id="caa4d-207">**[グループの種類]** に **[セキュリティ]** を選択し、グループ名と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-207">For **Group type**, select **Security**, and then enter a group name and description.</span></span>

1. <span data-ttu-id="caa4d-208">**[メンバーシップの種類]** に、 **[割り当て済み]** または **[動的デバイス]** のどちらかを選択します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-208">For **Membership type**, select either **Assigned** or **Dynamic Device**.</span></span>

1. <span data-ttu-id="caa4d-209">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="caa4d-209">Do one of the following:</span></span>  

   - <span data-ttu-id="caa4d-210">前の手順で **[メンバーシップの種類]** で **[割り当て済み]** を選択した場合は、 **[メンバー]** を選択し、Autopilot デバイスをグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-210">If you selected **Assigned** for **Membership type** in the previous step, select **Members**, and then add Autopilot devices to the group.</span></span> <span data-ttu-id="caa4d-211">まだ登録されていない Autopilot デバイスは、デバイスのシリアル番号をデバイス名として使用して一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-211">Autopilot devices that aren't yet enrolled are listed by using the device serial number as the device name.</span></span>
   - <span data-ttu-id="caa4d-212">前の手順で **[メンバーシップの種類]** で **[動的デバイス]** を選択した場合は、 **[動的デバイス メンバー]** を選択し、次のような **詳細ルール** にコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-212">If you selected **Dynamic Devices** for **Membership type** in the previous step, select **Dynamic device members**, and then enter code in **Advanced rule** that resembles the following:</span></span>
     - <span data-ttu-id="caa4d-213">Autopilot デバイスをすべて含むグループを作成する場合は、「`(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`」と入力します</span><span class="sxs-lookup"><span data-stu-id="caa4d-213">If you want to create a group that includes all of your Autopilot devices, type: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`</span></span>
     - <span data-ttu-id="caa4d-214">Intune のグループ タグ フィールドは、Azure AD デバイス上の **OrderID** 属性にマップされます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-214">Intune's group tag field maps to the **OrderID** attribute on Azure AD devices.</span></span> <span data-ttu-id="caa4d-215">特定のグループ タグ (Azure AD デバイス OrderID) のあるすべての Autopilot デバイスを含むグループを作成する場合は、次のように入力する必要があります。`(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`</span><span class="sxs-lookup"><span data-stu-id="caa4d-215">If you want to create a group that includes all of your Autopilot devices that have a specific group tag (the Azure AD device OrderID), you must type: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`</span></span>
     - <span data-ttu-id="caa4d-216">特定の発注書 ID のあるすべての Autopilot デバイスを含むグループを作成する場合は、次のように入力します。`(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`</span><span class="sxs-lookup"><span data-stu-id="caa4d-216">If you want to create a group that includes all your Autopilot devices that have a specific Purchase Order ID, type: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`</span></span>

     > [!NOTE]  
     > <span data-ttu-id="caa4d-217">これらのルールは、Autopilot デバイスに固有の属性を対象としています。</span><span class="sxs-lookup"><span data-stu-id="caa4d-217">These rules target attributes that are unique to Autopilot devices.</span></span>
1. <span data-ttu-id="caa4d-218">**[保存]** を選択し、 **[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-218">Select **Save**, and then select **Create**.</span></span>

### <a name="5-create-a-deployment-profile"></a><span data-ttu-id="caa4d-219">5.展開プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="caa4d-219">5. Create a deployment profile</span></span>

1. <span data-ttu-id="caa4d-220">[Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com)で、 **[デバイス]**  >  **[Windows]**  >  **[Windows 加入契約]**  >  **[Windows Autopilot 展開プロファイル]**  >  **[プロファイルの作成]**  >  **[HoloLens]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-220">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Devices** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile** > **HoloLens**.</span></span>
   <span data-ttu-id="caa4d-221">![[プロファイルの作成] ドロップダウンには、HoloLens 項目が含まれています。](./images/hololens-ap-enrollment-profiles.png)</span><span class="sxs-lookup"><span data-stu-id="caa4d-221">![Create profile dropdown includes a HoloLens item.](./images/hololens-ap-enrollment-profiles.png)</span></span>

1. <span data-ttu-id="caa4d-222">プロファイル名 と説明を入力し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-222">Enter a profile name and description, and then select **Next**.</span></span>  
   <span data-ttu-id="caa4d-223">**HoloLens** を含む一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-223">You should see a list that includes **HoloLens**.</span></span> <span data-ttu-id="caa4d-224">このオプションが表示されない場合は、[フィードバック](hololens2-autopilot.md#feedback-and-support-for-autopilot) オプションのいずれかを使用してお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="caa4d-224">If this option is not present, use one of the [Feedback](hololens2-autopilot.md#feedback-and-support-for-autopilot) options to contact us.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="caa4d-225">![プロファイルの名前と説明を追加する](./images/hololens-ap-profile-name.png)</span><span class="sxs-lookup"><span data-stu-id="caa4d-225">![Add a profile name and description](./images/hololens-ap-profile-name.png)</span></span>

1. <span data-ttu-id="caa4d-226">**Out-of-box experience (OOBE)** ページでは、この評価のために OOBE を効率化するようにほとんどの設定が事前に構成されています。</span><span class="sxs-lookup"><span data-stu-id="caa4d-226">On the **Out-of-box experience (OOBE)** page, most of the settings are pre-configured to streamline OOBE for this evaluation.</span></span> <span data-ttu-id="caa4d-227">オプションで、次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-227">Optionally, you can configure the following settings:</span></span>  

   - <span data-ttu-id="caa4d-228">**言語 (リージョン)** : OOBE の言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-228">**Language (Region)**: Select the language for OOBE.</span></span> <span data-ttu-id="caa4d-229">[HoloLens 2 用にサポートされている言語](hololens2-language-support.md)の一覧から言語を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="caa4d-229">We recommend that you select a language from the list of [supported languages for HoloLens 2](hololens2-language-support.md).</span></span>
   - <span data-ttu-id="caa4d-230">**キーボードを自動的に構成する**: キーボードが選択した言語と一致することを確かめるには、 **[はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-230">**Automatically configure keyboard**: To make sure that the keyboard matches the selected language, select **Yes**.</span></span>
   - <span data-ttu-id="caa4d-231">**デバイス名テンプレートを適用**: OOBE 中にデバイス名を自動的に設定するには、 **[はい]** を選択し、 **[名前を入力]** にテンプレート フレーズとプレースホルダーを入力します。たとえば、4 桁の乱数のプレフィックスと `%RAND:4%`&mdash; プレースホルダーを入力します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-231">**Apply device name template**: To automatically set the device name during OOBE, select **Yes** and then enter the template phrase and placeholders in **Enter a name** For example, enter a prefix and `%RAND:4%`&mdash;a placeholder for a four-digit random number.</span></span>
     > [!NOTE]  
     > <span data-ttu-id="caa4d-232">デバイス名テンプレートを使用する場合、OOBE プロセスは、デバイス名を適用した後、Azure AD にデバイスを参加させる前に、デバイスをさらに 1 回再起動します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-232">If you use a device name template, the OOBE process restarts the device one additional time after it applies the device name and before it joins the device to Azure AD.</span></span> <span data-ttu-id="caa4d-233">この再起動により、新しい名前が有効になります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-233">This restart enables the new name to take effect.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="caa4d-234">![OOBE の設定を構成する](./images/hololens-ap-profile-oobe.png)</span><span class="sxs-lookup"><span data-stu-id="caa4d-234">![Configure OOBE settings](./images/hololens-ap-profile-oobe.png)</span></span>

1. <span data-ttu-id="caa4d-235">設定を構成したら、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-235">After you configure the settings, select **Next**.</span></span>
1. <span data-ttu-id="caa4d-236">**[スコープ タグ]** ページ上で、このプロファイルに適用するスコープ タグをオプションで追加します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-236">On the **Scope tags** page, optionally add the scope tags that you want to apply to this profile.</span></span> <span data-ttu-id="caa4d-237">スコープのタグの詳細については、[分散 IT のためのロールベースのアクセス制御とスコープのタグの使用](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="caa4d-237">For more information about scope tags, see [Use role-based access control and scope tags for distributed IT](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md).</span></span> <span data-ttu-id="caa4d-238">完了したら **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-238">When finished, select **Next**.</span></span>
1. <span data-ttu-id="caa4d-239">**[割り当て]** ページで、 **[割り当て先]** として **[選択したグループ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-239">On the **Assignments** page, select **Selected groups** for **Assign to**.</span></span>
1. <span data-ttu-id="caa4d-240">**[選択したグループ]** で、 **[+ 含めるグループの選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-240">Under **SELECTED GROUPS**, select **+ Select groups to include**.</span></span>
1. <span data-ttu-id="caa4d-241">**含めるグループの選択** の一覧で、Autopilot HoloLens デバイス用に作成したデバイス グループを選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-241">In the **Select groups to include** list, select the device group that you created for the Autopilot HoloLens devices, and then select **Next**.</span></span>  
  
   <span data-ttu-id="caa4d-242">いずれかのグループを除外する場合は、 **[含めないグループを選択]** を選択して、除外するグループを選びます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-242">If you want to exclude any groups, select **Select groups to exclude**, and select the groups that you want to exclude.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="caa4d-243">![プロファイルにデバイス グループを割り当てます。](./images/hololens-ap-profile-assign-devicegroup.png)</span><span class="sxs-lookup"><span data-stu-id="caa4d-243">![Assigning a device group to the profile.](./images/hololens-ap-profile-assign-devicegroup.png)</span></span>

1. <span data-ttu-id="caa4d-244">**[確認と作成]** ページで 設定を確認し、 **[作成]** を選択 してプロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-244">On the **Review + Create** page, review the settings and then select **Create** to create the profile.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="caa4d-245">![確認および作成](./images/hololens-ap-profile-summ.png)</span><span class="sxs-lookup"><span data-stu-id="caa4d-245">![Review + create](./images/hololens-ap-profile-summ.png)</span></span>

### <a name="6-verify-the-esp-configuration"></a><span data-ttu-id="caa4d-246">6. ESP 構成を確認する</span><span class="sxs-lookup"><span data-stu-id="caa4d-246">6. Verify the ESP configuration</span></span>

<span data-ttu-id="caa4d-247">[登録状態] ページ (ESP) には、MDM 管理対象ユーザーが初めてデバイスにサインインするときに実行される完全なデバイス構成プロセスの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-247">The Enrollment Status Page (ESP) displays the status of the complete device configuration process that runs when an MDM managed user signs into a device for the first time.</span></span> <span data-ttu-id="caa4d-248">ESP 構成が次のようになっていることを確認し、割り当てが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-248">Make sure that your ESP configuration resembles the following, and verify that the assignments are correct.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="caa4d-249">![ESP の構成](./images/hololens-ap-profile-settings.png)</span><span class="sxs-lookup"><span data-stu-id="caa4d-249">![ESP configuration](./images/hololens-ap-profile-settings.png)</span></span>

### <a name="7-verify-the-profile-status-of-the-hololens-devices"></a><span data-ttu-id="caa4d-250">7. HoloLens デバイスのプロファイルの状態を確認する</span><span class="sxs-lookup"><span data-stu-id="caa4d-250">7. Verify the profile status of the HoloLens devices</span></span>

1. <span data-ttu-id="caa4d-251">Microsoft エンドポイント マネージャー管理センターで、 **[デバイス]**  >  **[Windows]**  >  **[Windows 加入契約]**  >  **[デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-251">In Microsoft Endpoint Manager Admin Center, select **Devices** > **Windows** > **Windows enrollment** > **Devices**.</span></span>

1. <span data-ttu-id="caa4d-252">HoloLens デバイスが一覧に表示されていること、およびプロファイルの状態が **割り当て済み** であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-252">Verify that the HoloLens devices are listed, and that their profile status is **Assigned**.</span></span>  

   > [!NOTE]  
   > <span data-ttu-id="caa4d-253">デバイスにプロファイルが割り当てられるまで、数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-253">It may take a few minutes for the profile to be assigned to the device.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="caa4d-254">![デバイスとプロファイルの割り当て](./images/hololens-ap-devices-assignments.png)。</span><span class="sxs-lookup"><span data-stu-id="caa4d-254">![Device and profile assignments.](./images/hololens-ap-devices-assignments.png)</span></span>

## <a name="windows-autopilot-for-hololens-2-user-experience"></a><span data-ttu-id="caa4d-255">Windows Autopilot for HoloLens 2 のユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="caa4d-255">Windows Autopilot for HoloLens 2 User Experience</span></span>

<span data-ttu-id="caa4d-256">上記の手順が完了すると、HoloLens 2 ユーザーは次のエクスペリエンスを実行して HoloLens デバイスをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="caa4d-256">Once the above instructions are completed, your HoloLens 2 users will go through the following experience to provision their HoloLens devices:</span></span>  

1. <span data-ttu-id="caa4d-257">Autopilot のエクスペリエンスには、インターネット アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="caa4d-257">Autopilot experience requires internet access.</span></span> <span data-ttu-id="caa4d-258">インターネットにアクセスするには、次のいずれかのオプションを使用してください。</span><span class="sxs-lookup"><span data-stu-id="caa4d-258">Please use one of following options to provide internet access:</span></span>

    - <span data-ttu-id="caa4d-259">デバイスを OOBE の Wi-Fi ネットワークに接続し、Autopilot エクスペリエンスを自動的に検出できるようにします。</span><span class="sxs-lookup"><span data-stu-id="caa4d-259">Connect your device to a Wi-Fi network in OOBE and then let it detect Autopilot experience automatically.</span></span> <span data-ttu-id="caa4d-260">これは、Autopilot エクスペリエンスが自動的に完了するまで、OOBE を操作する必要がある唯一の場合です。</span><span class="sxs-lookup"><span data-stu-id="caa4d-260">This is the only time you will need to interact with OOBE until Autopilot experience completes on its own.</span></span> <span data-ttu-id="caa4d-261">既定では、HoloLens 2 は、インターネットを検出した後、Autopilot を検出するために 10 秒間待機することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="caa4d-261">Please note that by default HoloLens 2 waits for 10 seconds to detect Autopilot after detecting internet.</span></span> <span data-ttu-id="caa4d-262">Autopilot プロファイルが 10 秒以内に検出されない場合は、OOBE に EULA が表示されます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-262">If no autopilot profile is detected within 10 seconds, OOBE will present EULA.</span></span> <span data-ttu-id="caa4d-263">このシナリオが発生した場合は、デバイスを再起動して、Autopilot の検出をもう一度試行できるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="caa4d-263">If you encounter this scenario, please reboot your device so another attempt can be made to detect Autopilot.</span></span> <span data-ttu-id="caa4d-264">また、デバイスに TenantLockdown ポリシーが設定されている場合にのみ、OOBE が Autopilot を無期限に待機する場合があることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="caa4d-264">Please also note that OOBE can wait indefinitely for Autopilot only if TenantLockdown policy is set on the device.</span></span>

    - <span data-ttu-id="caa4d-265">有線インターネット接続用の「USB-C to Ethernet」アダプターを使用してデバイスをイーサネットに接続し、HoloLens 2 に Autopilot エクスペリエンスを自動的に完了させます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-265">Connect your device with Ethernet using "USB-C to Ethernet" adapters for wired internet connectivity and let HoloLens 2 complete Autopilot experience automatically.</span></span>

    - <span data-ttu-id="caa4d-266">無線インターネット接続用の「USB-C to Wifi」アダプターを使用してデバイスを接続し、HoloLens 2 に Autopilot エクスペリエンスを自動的に完了させます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-266">Connect your device with "USB-C to Wifi" adapters for wireless internet connectivity and let HoloLens 2 complete Autopilot experience automatically.</span></span>

        > [!IMPORTANT]  
       > <span data-ttu-id="caa4d-267">Autopilot 用の OOBE で Wi-Fi ネットワークを使用しようとするデバイスは、[Windows Holographic、バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2)上にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-267">Devices attempting to use Wi-Fi networks in OOBE for Autopilot must be on [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2).</span></span>
       >
       > <span data-ttu-id="caa4d-268">イーサネット アダプターを使用するデバイスの場合、Out-of-the-Box-Experience (OOBE) を開始する前に、デバイスをネットワークに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-268">For devices using ethernet adapters you must connect the device to the network before the Out-of-the-Box-Experience (OOBE) starts.</span></span> <span data-ttu-id="caa4d-269">デバイスは、最初の OOBE 画面で、Autopilot デバイスとしてプロビジョニングされているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-269">The device determines whether it is provisioning as an Autopilot device while on the first OOBE screen.</span></span> <span data-ttu-id="caa4d-270">デバイスがネットワークに接続できない場合、またはデバイスを Autopilot デバイスとしてプロビジョニングしないことを選択した場合、後で Autopilot プロビジョニングに変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="caa4d-270">If the device cannot connect to the network, or if you choose not to provision the device as an Autopilot device, you cannot change to Autopilot provisioning at a later time.</span></span> <span data-ttu-id="caa4d-271">代わりに、デバイスを Autopilot デバイスとしてプロビジョニングするには、この手順を最初からやり直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-271">Instead, you would have to start this procedure over in order to provision the device as an Autopilot device.</span></span>

1. <span data-ttu-id="caa4d-272">デバイスは OOBE を自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-272">The device should automatically start OOBE.</span></span> <span data-ttu-id="caa4d-273">OOBE を使って操作しないでください。</span><span class="sxs-lookup"><span data-stu-id="caa4d-273">Do not interact with OOBE.</span></span> <span data-ttu-id="caa4d-274">何もせずにリラックスしてください。</span><span class="sxs-lookup"><span data-stu-id="caa4d-274">Instead sit, back and relax!</span></span> <span data-ttu-id="caa4d-275">HoloLens 2 にネットワーク接続を検出させ、OOBE が自動的に完了するようにします。</span><span class="sxs-lookup"><span data-stu-id="caa4d-275">Let HoloLens 2 detect network connectivity and allow it complete OOBE automatically.</span></span> <span data-ttu-id="caa4d-276">OOBE 中にデバイスが再起動される場合があります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-276">The device may restart during OOBE.</span></span> <span data-ttu-id="caa4d-277">OOBE 画面は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-277">The OOBE screens should resemble the following.</span></span>

   <span data-ttu-id="caa4d-278">![OOBE ステップ 1 ](./images/autopilot-welcome.jpg)
    ![ OOBE ステップ 2 ](./images/autopilot-step-complete.jpg)
    ![ OOBE ステップ 3](./images/autopilot-device-setup.jpg)</span><span class="sxs-lookup"><span data-stu-id="caa4d-278">![OOBE step 1](./images/autopilot-welcome.jpg)
![OOBE step 2](./images/autopilot-step-complete.jpg)
![OOBE step 3](./images/autopilot-device-setup.jpg)</span></span>

1. <span data-ttu-id="caa4d-279">OOBE の最後に、ユーザー名とパスワードを使用してデバイスにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-279">At the end of OOBE, you can sign in to the device by using your user name and password.</span></span>

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenantlockdown-csp-and-autopilot"></a><span data-ttu-id="caa4d-280">Tenantlockdown CSP と Autopilot</span><span class="sxs-lookup"><span data-stu-id="caa4d-280">Tenantlockdown CSP and Autopilot</span></span>

<span data-ttu-id="caa4d-281">HoloLens 2 デバイスでは、Windows Holographic のバージョン 20H2 での TenantLockdown CSP がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="caa4d-281">HoloLens 2 devices support TenantLockdown CSP as of Windows Holographic, version 20H2.</span></span> <span data-ttu-id="caa4d-282">この CSP は、デバイスのリセットまたは再フラッシュ によっても、デバイスをそのテナントにロックすることによって、デバイスを組織のテナント上に保持します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-282">This CSP keeps devices on the organization's tenant by locking them to that tenant even through device reset or reflash.</span></span>

<span data-ttu-id="caa4d-283">[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP は、HoloLens 2 が Autopilot のみを使用して MDM 登録に関連付けられるようにします。</span><span class="sxs-lookup"><span data-stu-id="caa4d-283">[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP enables HoloLens 2 to be tied to MDM enrollment using Autopilot only.</span></span> <span data-ttu-id="caa4d-284">TenantLockdown CSP の RequireNetworkInOOBE ノードが HoloLens 2 で true または false (最初に設定された) 値に設定されると、その値は、再フラッシュ、OS 更新プログラムなどにもかかわらずデバイスに残ります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-284">Once TenantLockdown CSP’s RequireNetworkInOOBE node is set to either true or false (initially set) value on HoloLens 2, that value remains on the device despite re-flashing, OS updates, etc.</span></span>

<span data-ttu-id="caa4d-285">HoloLens 2 で TenantLockdown CSP の RequireNetworkInOOBE ノードが true に設定されると、OOBE は、ネットワーク接続後、Autopilot プロファイルが正常にダウンロードおよび適用されるまで無期限に待機します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-285">Once TenantLockdown CSPs’ RequireNetworkInOOBE node is set to true on HoloLens 2, OOBE waits indefinitely for Autopilot profile to be successfully downloaded and applied, after network connectivity.</span></span>

<span data-ttu-id="caa4d-286">HoloLens 2 で TenantLockdown CSP の RequireNetworkInOOBE ノードが true に設定されると、OOBE では次の操作が許可されなくなります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-286">Once TenantLockdown CSPs’ RequireNetworkInOOBE node is set to true on HoloLens 2, following operations are disallowed in OOBE:</span></span>

- <span data-ttu-id="caa4d-287">ランタイム プロビジョニングを使用したローカル ユーザーの作成</span><span class="sxs-lookup"><span data-stu-id="caa4d-287">Creating local user using runtime provisioning</span></span> 
- <span data-ttu-id="caa4d-288">ランタイム プロビジョニングによる Azure AD への参加操作の実行</span><span class="sxs-lookup"><span data-stu-id="caa4d-288">Performing Azure AD join operation via runtime provisioning</span></span> 
- <span data-ttu-id="caa4d-289">OOBE エクスペリエンスでデバイスの所有者を選択する</span><span class="sxs-lookup"><span data-stu-id="caa4d-289">Selecting who owns the device in OOBE experience</span></span> 

#### <a name="how-to-set-this-using-intune"></a><span data-ttu-id="caa4d-290">Intune を使用してこれを設定する方法</span><span class="sxs-lookup"><span data-stu-id="caa4d-290">How to set this using Intune?</span></span> 
1. <span data-ttu-id="caa4d-291">以下に示すように、カスタム OMA URI デバイス構成プロファイルを作成し、RequireNetworkInOOBE ノードに true を指定します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-291">Create a custom OMA URI device configuration profile and specify true for RequireNetworkInOOBE node as shown below.</span></span>
<span data-ttu-id="caa4d-292">OMA-URI 値は ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE である必要があります</span><span class="sxs-lookup"><span data-stu-id="caa4d-292">OMA-URI value should be ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="caa4d-293">![OMA-URI によるテナントのロックダウンの設定](images/hololens-tenant-lockdown.png)</span><span class="sxs-lookup"><span data-stu-id="caa4d-293">![Setting tennant lockdown via OMA-URI](images/hololens-tenant-lockdown.png)</span></span>

1. <span data-ttu-id="caa4d-294">グループを作成し、デバイス構成プロファイルをそのデバイス グループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-294">Create a group and assign the device configuration profile to that device group.</span></span>

1. <span data-ttu-id="caa4d-295">前の手順で作成したグループの HoloLens 2 デバイス メンバーを作成し、同期をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="caa4d-295">Make the HoloLens 2 device member of the group created in previous step and trigger sync.</span></span>  

<span data-ttu-id="caa4d-296">Intune ポータルで、デバイス構成が正常に適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-296">Verify in the Intune portal that device configuration has been successfully applied.</span></span> <span data-ttu-id="caa4d-297">このデバイスの構成が HoloLens 2 デバイスに正常に適用されると、TenantLockdown の効果がアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-297">Once this device configuration successfully applies on the HoloLens 2 device, effects of TenantLockdown will be active.</span></span>

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a><span data-ttu-id="caa4d-298">Intune を使用して HoloLens 2 で TenantLockdown の RequireNetworkInOOBE の設定を解除する方法</span><span class="sxs-lookup"><span data-stu-id="caa4d-298">How to unset TenantLockdown’s RequireNetworkInOOBE on HoloLens 2 using Intune?</span></span>

1. <span data-ttu-id="caa4d-299">上で作成したデバイス構成が以前に割り当てられていたデバイス グループから HoloLens 2 を削除します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-299">Remove the HoloLens 2 from the device group to which the device configuration created above was previously assigned.</span></span>

1. <span data-ttu-id="caa4d-300">以下に示すように、カスタム OMA URI ベースのデバイス構成プロファイルを作成し、RequireNetworkInOOBE に false を指定します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-300">Create a custom OMA URI based device configuration profile and specify false for RequireNetworkInOOBE as shown below.</span></span>
<span data-ttu-id="caa4d-301">OMA-URI 値は ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE である必要があります</span><span class="sxs-lookup"><span data-stu-id="caa4d-301">OMA-URI value should be ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="caa4d-302">![Intune の OMA URI を介して RequireNetworkInOOBE を false に設定するスクリーンショット](images/hololens-tenant-lockdown-false.png)</span><span class="sxs-lookup"><span data-stu-id="caa4d-302">![Screenshot of setting RequireNetworkInOOBE to false via OMA URI in Intune](images/hololens-tenant-lockdown-false.png)</span></span>

1. <span data-ttu-id="caa4d-303">グループを作成し、デバイス構成プロファイルをそのデバイス グループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-303">Create a group and assign the device configuration profile to that device group.</span></span> 

1. <span data-ttu-id="caa4d-304">前の手順で作成したグループの HoloLens 2 デバイス メンバーを作成し、同期をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="caa4d-304">Make the HoloLens 2 device member of the group created in previous step and trigger sync.</span></span>

<span data-ttu-id="caa4d-305">Intune ポータルで、デバイス構成が正常に適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-305">Verify in the Intune portal that device configuration has been successfully applied.</span></span> <span data-ttu-id="caa4d-306">このデバイスの構成が HoloLens 2 デバイスに正常に適用されると、TenantLockdown の効果が非アクティブになります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-306">Once this device configuration successfully applies on the HoloLens 2 device, effects of TenantLockdown will be inactive.</span></span>

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a><span data-ttu-id="caa4d-307">TenantLockdown が true に設定された後、HoloLens で Autopilot プロファイルが割り当て解除された場合、OOBE 中にどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="caa4d-307">What would happen during OOBE, if Autopilot profile is unassigned on a HoloLens after TenantLockdown was set to true?</span></span> 
<span data-ttu-id="caa4d-308">OOBE は、Autopilot プロファイルがダウンロードされるのを無期限に待機し、次のダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-308">OOBE will wait indefinitely for Autopilot profile to download and following dialog will be presented.</span></span> <span data-ttu-id="caa4d-309">TenantLockdown の影響を取り除くには、最初に Autopilot のみを使用してデバイスを元のテナントに登録し、TenantLockdown CSP によって導入された制限を取り除く前に、前の手順で説明したように RequireNetworkInOOBE の設定を解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-309">In order to remove effects of TenantLockdown, device must be enrolled with its original tenant first using Autopilot only and RequireNetworkInOOBE must be unset as described in previous step before restrictions introduced by TenantLockdown CSP are removed.</span></span>

![ポリシーがデバイスに適用される時のデバイス内ビュー。](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a><span data-ttu-id="caa4d-311">既知の問題と制限事項</span><span class="sxs-lookup"><span data-stu-id="caa4d-311">Known Issues & limitations</span></span>

- <span data-ttu-id="caa4d-312">MEM に構成されているデバイスコンテキスト ベースのアプリケーション インストールが HoloLens に適用されない問題を調査しています。</span><span class="sxs-lookup"><span data-stu-id="caa4d-312">We are investigating an issue where device-context based application install configured in MEM does not apply to HoloLens.</span></span> [<span data-ttu-id="caa4d-313">「デバイス コンテキストとユーザー コンテキストのインストールの詳細」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="caa4d-313">Learn more about device context and user context installs.</span></span>](https://docs.microsoft.com/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- <span data-ttu-id="caa4d-314">Wi-Fi 経由で Autopilot を設定しているときに、インターネット接続が最初に確立されたときに Autopilot プロファイルがダウンロードされない場合があります。</span><span class="sxs-lookup"><span data-stu-id="caa4d-314">While setting up Autopilot over Wi-Fi, there may be an instance where the Autopilot profile is not downloaded when Internet connection is first established.</span></span> <span data-ttu-id="caa4d-315">この場合、使用許諾契約書 (EULA) が提示され、ユーザーは Autopilot 以外のセットアップを続行することができます。</span><span class="sxs-lookup"><span data-stu-id="caa4d-315">In this case End User License Agreement (EULA) is presented and the user has the option to proceed with non-Autopilot setup experience.</span></span> <span data-ttu-id="caa4d-316">Autopilot による設定を再試行するには、デバイスをスリープ状態にしてから電源を入れます。または、デバイスを再起動して、もう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="caa4d-316">To retry setting up with Autopilot, put the device to sleep and then power up, or reboot the device and let it try again.</span></span>
- <span data-ttu-id="caa4d-317">現時点では、HoloLens で [すべての対象デバイスをAutopilot に変換する] 機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="caa4d-317">"Convert all targeted devices to Autopilot" feature is not supported on HoloLens at the moment.</span></span>  


## <a name="feedback-and-support-for-autopilot"></a><span data-ttu-id="caa4d-318">Autopilot のフィードバックとサポート</span><span class="sxs-lookup"><span data-stu-id="caa4d-318">Feedback and support for Autopilot</span></span>

<span data-ttu-id="caa4d-319">フィードバックを提供する、または問題を報告する場合は、次のいずれかの方法を使用します:</span><span class="sxs-lookup"><span data-stu-id="caa4d-319">To provide feedback or report issues, use one of the following methods:</span></span>

- <span data-ttu-id="caa4d-320">デバイス登録のサポートについては、販売店または販売代理店にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="caa4d-320">For support on device registration, please contact your reseller or distributor.</span></span>
- <span data-ttu-id="caa4d-321">Windows Autopilot に関する一般的なサポートに関する問い合わせ、またはプロファイルの割り当て、グループの作成、MEM ポータルコントロールのような問題については、[Microsoft エンドポイント マネージャーのサポートにお問い合わせください](https://docs.microsoft.com/mem/get-support)</span><span class="sxs-lookup"><span data-stu-id="caa4d-321">For general support inquiries about Windows Autopilot, or for issues like profile assignments, group creation or MEM portal controls, [please contact Microsoft Endpoint Manager support](https://docs.microsoft.com/mem/get-support)</span></span>  
- <span data-ttu-id="caa4d-322">デバイスが Autopilot サービスに登録されていて、プロファイルが MEM ポータルに割り当てられている場合は、HoloLens の[サポート](https://docs.microsoft.com/hololens/)にお問い合わせください (「サポートカード」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="caa4d-322">If your device is registered to the Autopilot service and the profile is assigned on MEM portal, contact HoloLens [support](https://docs.microsoft.com/hololens/) (see 'Support' card).</span></span> <span data-ttu-id="caa4d-323">サポート チケットを開いて、(該当する場合は)Out-of-box-experience (OOBE) 中に [オフライン診断ログ](hololens-diagnostic-logs.md#offline-diagnostics) をキャプチャして、 スクリーンショットとログを追加します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-323">Please open a support ticket and if applicable, include screenshots and logs by capturing [offline diagnostic logs](hololens-diagnostic-logs.md#offline-diagnostics) during the out-of-box-experience (OOBE).</span></span>
- <span data-ttu-id="caa4d-324">デバイスから問題を報告するには、HoloLens でフィードバック Hub アプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-324">To report an issue from the device, use the Feedback Hub app on your HoloLens.</span></span> <span data-ttu-id="caa4d-325">フィードバック Hub で **[エンタープライズ管理]**  >  **[デバイス]** カテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="caa4d-325">In Feedback Hub, select the **Enterprise Management** > **Device** category.</span></span>
- <span data-ttu-id="caa4d-326">Autopilot for HoloLens に関する一般的なフィードバックを提供するには、この[アンケート](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)を提出してください</span><span class="sxs-lookup"><span data-stu-id="caa4d-326">To provide general feedback on Autopilot for HoloLens, you can submit this [survey](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)</span></span>
