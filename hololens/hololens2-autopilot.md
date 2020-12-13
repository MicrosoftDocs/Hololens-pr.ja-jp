---
title: Windows Autopilot for HoloLens 2
description: HoloLens 2 デバイスで Autopilot を設定する方法を説明します。
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
ms.openlocfilehash: 95f187b2a4b6a86b59e05f3b12414c84ca0f6460
ms.sourcegitcommit: fac3e62c1fd4dd531c2c8620870213cd570980dc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "11205769"
---
# <span data-ttu-id="54c28-104">Windows Autopilot for HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="54c28-104">Windows Autopilot for HoloLens 2</span></span>

<span data-ttu-id="54c28-105">Windows Holographic バージョン 2004 以降では、HoloLens 2 は Windows Autopilot[自動展開 モード](https://docs.microsoft.com/mem/autopilot/self-deploying)をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="54c28-105">Starting with Windows Holographic version 2004, HoloLens 2 supports Windows Autopilot [Self-Deploying Mode](https://docs.microsoft.com/mem/autopilot/self-deploying).</span></span> <span data-ttu-id="54c28-106">管理者は、Microsoft エンドポイント マネージャーでOut-of-box experience (OOBE) を構成できます。また、エンドユーザーは、ほとんどの操作なしで、ビジネス用のデバイスを準備することができます。</span><span class="sxs-lookup"><span data-stu-id="54c28-106">Administrators can configure the out-of-box experience (OOBE) in Microsoft Endpoint Manager and enable end-users to prepare devices for business use with little to no interaction.</span></span> <span data-ttu-id="54c28-107">これにより、セットアップ エクスペリエンスの際に、在庫管理のオーバーヘッド、実地で使用するデバイス準備のコスト、および従業員からの通話のサポートが削減されます。</span><span class="sxs-lookup"><span data-stu-id="54c28-107">This reduces inventory management overhead, cost of hands-on device preparation and support calls from employees during the setup experience.</span></span> <span data-ttu-id="54c28-108">Windows Autopilot の詳細については、 [ここ](https://docs.microsoft.com/mem/autopilot/windows-autopilot)をクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="54c28-108">To learn more about Windows Autopilot, click [here](https://docs.microsoft.com/mem/autopilot/windows-autopilot).</span></span>

<span data-ttu-id="54c28-109">Surface デバイスの場合と同様に、お客様が Microsoft[クラウド ソリューション プロバイダー](https://partner.microsoft.com/cloud-solution-provider)(販売店または卸売業者) と協力して、パートナー センターを通じてAutopilot サービスにデバイスに登録することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="54c28-109">Like for Surface devices, it is recommended that customers work with their Microsoft [Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) (reseller or distributor) to get devices registered with the Autopilot service through Partner Center.</span></span> <span data-ttu-id="54c28-110">デバイス登録のその他の方法については、 [ここ](https://docs.microsoft.com/mem/autopilot/add-devices)で説明していますが、Microsoft のチャネル パートナーを活用すると、最も有効なエンドツーエンドのパスを確実に実現できます。</span><span class="sxs-lookup"><span data-stu-id="54c28-110">Other methods for device registration are outlined [here](https://docs.microsoft.com/mem/autopilot/add-devices), though leveraging Microsoft's channel partners ensures the most effective end-to-end path.</span></span> 

> [!NOTE]
> <span data-ttu-id="54c28-111">11/20/2020 時点で、Microsoft エンドポイント マネージャーでの HoloLens 用 Autopilot の構成は、**パブリック プレビュー**に移行中 です。</span><span class="sxs-lookup"><span data-stu-id="54c28-111">As of 11/20/2020 Autopilot configuration for HoloLens in Microsoft Endpoint Manager is transitioning to **Public Preview**.</span></span> <span data-ttu-id="54c28-112">お客様はプライベート プレビューに登録する必要がなくなりました。すべてのテナントは、MEM 管理センターでAutopilot を設定することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="54c28-112">Customers no longer need to enroll in the private preview and all tenants will be able to setup Autopilot in the MEM admin center.</span></span>

<span data-ttu-id="54c28-113">ユーザーが Autopilot の自動展開プロセスを開始すると、Autopilot が次の手順を完了します:</span><span class="sxs-lookup"><span data-stu-id="54c28-113">When a user starts the Autopilot self-deploying process, Autopilot completes the following steps:</span></span>

1. <span data-ttu-id="54c28-114">デバイスを Azure Active Directory (Azure AD) に参加させます。</span><span class="sxs-lookup"><span data-stu-id="54c28-114">Join the device to Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="54c28-115">Autopilot for HoloLens は、Active Directory への参加またはハイブリッド Azure AD への参加をサポートしていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="54c28-115">Note that Autopilot for HoloLens does not support Active Directory join or Hybrid Azure AD join.</span></span>
   
1. <span data-ttu-id="54c28-116">Azure AD を使用して、デバイスを Microsoft エンドポイント マネージャー (または別の MDM サービス) に登録します。</span><span class="sxs-lookup"><span data-stu-id="54c28-116">Use Azure AD to enroll the device in Microsoft Endpoint Manager (or another MDM service).</span></span>

1. <span data-ttu-id="54c28-117">デバイスを対象としたポリシー、証明書、ネットワーク プロファイル、アプリケーションをダウンロードして適用します。</span><span class="sxs-lookup"><span data-stu-id="54c28-117">Download and apply device-targeted policies, certificates, networking profiles and applications.</span></span>

1. <span data-ttu-id="54c28-118">デバイスをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="54c28-118">Provision the device.</span></span>

1. <span data-ttu-id="54c28-119">ユーザーにサインイン画面を提示します。</span><span class="sxs-lookup"><span data-stu-id="54c28-119">Present the sign-in screen to the user.</span></span>


## <span data-ttu-id="54c28-120">Autopilot for HoloLens 2 を構成する</span><span class="sxs-lookup"><span data-stu-id="54c28-120">Configuring Autopilot for HoloLens 2</span></span>

<span data-ttu-id="54c28-121">環境をセット アップするには、次の手順に従ってください:</span><span class="sxs-lookup"><span data-stu-id="54c28-121">Please follow the steps below to set up your environment:</span></span>

1. [<span data-ttu-id="54c28-122">Windows Autopilot for HoloLens 2 の要件を確認します。</span><span class="sxs-lookup"><span data-stu-id="54c28-122">Review requirements for Windows Autopilot for HoloLens 2.</span></span>](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [<span data-ttu-id="54c28-123">Windows Autopilot にデバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="54c28-123">Register devices in Windows Autopilot.</span></span>](#2-register-devices-in-windows-autopilot)

1. [<span data-ttu-id="54c28-124">デバイス グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="54c28-124">Create a device group.</span></span>](#3-create-a-device-group)

1. [<span data-ttu-id="54c28-125">展開プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="54c28-125">Create a deployment profile.</span></span>](#4-create-a-deployment-profile)

1. [<span data-ttu-id="54c28-126">登録状態ページ (ESP) の構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="54c28-126">Verify the Enrollment Status Page (ESP) configuration.</span></span>](#5-verify-the-esp-configuration)

1. [<span data-ttu-id="54c28-127">HoloLens デバイスのプロファイルの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="54c28-127">Verify the profile status of the HoloLens devices.</span></span>](#6-verify-the-profile-status-of-the-hololens-devices)


#### <span data-ttu-id="54c28-128">1. Windows Autopilot for HoloLens 2 の要件を確認する</span><span class="sxs-lookup"><span data-stu-id="54c28-128">1. Review requirements for Windows Autopilot for HoloLens 2</span></span>

**<span data-ttu-id="54c28-129">Windows Autopilot の要件に関する記事の次のセクションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="54c28-129">Review the following sections of the Windows Autopilot requirements article:</span></span>**

- [<span data-ttu-id="54c28-130">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="54c28-130">Network requirements</span></span>](https://docs.microsoft.com/mem/autopilot/networking-requirements)  
- [<span data-ttu-id="54c28-131">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="54c28-131">Licensing requirements</span></span>](https://docs.microsoft.com/mem/autopilot/licensing-requirements)  
- [<span data-ttu-id="54c28-132">構成要件</span><span class="sxs-lookup"><span data-stu-id="54c28-132">Configuration requirements</span></span>](https://docs.microsoft.com/mem/autopilot/configuration-requirements)

**<span data-ttu-id="54c28-133">Windows Autopilot 自己展開モードに関する記事の "[要件](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" のセクションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="54c28-133">Review the "[Requirements](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" section of the Windows Autopilot Self-Deploying mode article.</span></span>** <span data-ttu-id="54c28-134">お客様の環境が、これらの要件に加えて、標準的な Windows Autopilot の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c28-134">Your environment has to meet these requirements as well as the standard Windows Autopilot requirements.</span></span> <span data-ttu-id="54c28-135">記事の "ステップ バイ ステップ" と "検証" のセクションを確認する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="54c28-135">You do not have to review the "Step by step" and "Validation" sections of the article.</span></span> <span data-ttu-id="54c28-136">この記事の後半の手順では、HoloLens に固有の対応する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="54c28-136">The procedures later in this article provide corresponding steps that are specific to HoloLens.</span></span> <span data-ttu-id="54c28-137">デバイスの登録とプロファイルの構成の詳細については、この記事の「[2. Windows Autopilot でデバイスを登録する](#2-register-devices-in-windows-autopilot)」と 「[4. 展開プロファイルを作成する](#4-create-a-deployment-profile)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c28-137">For information about how to register devices and configure profiles, see [2. Register devices in Windows Autopilot](#2-register-devices-in-windows-autopilot) and [4. Create a deployment profile](#4-create-a-deployment-profile) in this article.</span></span> <span data-ttu-id="54c28-138">Autopilot の自己展開モード プロファイルを構成および管理するには、[Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com)にアクセスできることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="54c28-138">To configure and manage the Autopilot self-deploying mode profiles, make sure that you have access to [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com).</span></span>

**<span data-ttu-id="54c28-139">HoloLens OS の要件を確認します:</span><span class="sxs-lookup"><span data-stu-id="54c28-139">Review HoloLens OS requirements:</span></span>**

- <span data-ttu-id="54c28-140">デバイスは [Windows Holographic、バージョン 2004](hololens-release-notes.md#windows-holographic-version-2004)(ビルド 19041.1103) 以降である必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c28-140">Devices must be on [Windows Holographic, version 2004](hololens-release-notes.md#windows-holographic-version-2004) (build 19041.1103) or later.</span></span> <span data-ttu-id="54c28-141">デバイスのビルド バージョンを確認するか、最新の OS に再フラッシュするには、 [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="54c28-141">To confirm the build version on your device or re-flash to the latest OS, you can use the [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab).</span></span> <span data-ttu-id="54c28-142">手順は [ここに](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device) あります。</span><span class="sxs-lookup"><span data-stu-id="54c28-142">You can find instructions [here](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span> <span data-ttu-id="54c28-143">2020 年 9 月の後半までに配信されたデバイスには、Windows Holographic バージョン 1903 がプリインストールされていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="54c28-143">Note that devices delivered until late September 2020 have Windows Holographic version 1903 pre-installed.</span></span> <span data-ttu-id="54c28-144">販売業者に連絡して、Autopilot 対応のデバイスが発送されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="54c28-144">Please contact your reseller to ensure that Autopilot-ready devices are shipped to you.</span></span>

- <span data-ttu-id="54c28-145">Windows Holographic、バージョン 2004 では、イーサネット接続経由の Autopilot のみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="54c28-145">Windows Holographic, version 2004 only supports Autopilot over ethernet connection.</span></span> <span data-ttu-id="54c28-146">「USB-C to Ethernet」アダプターを使って、**電源を入れる前に**HoloLens が イーサネットに接続されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="54c28-146">Ensure the HoloLens is connected to ethernet using a "USB-C to Ethernet" adapter **before turning it on**.</span></span> <span data-ttu-id="54c28-147">デバイスの起動時に、ユーザーの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="54c28-147">Upon device boot no user interaction is required.</span></span> <span data-ttu-id="54c28-148">多くの HoloLens デバイスに Autopilot ロールアウトを計画している場合は、アダプター インフラストラクチャの計画を立てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="54c28-148">If you are planning for an Autopilot roll-out to many HoloLens devices, we recommend that you plan for the adapter infrastructure.</span></span> <span data-ttu-id="54c28-149">USB ハブは、HoloLens でサポートされていないサードパーティ製のドライバーを追加でインストールすることを要求することが多いため、お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="54c28-149">We do not recommend USB Hubs, as they often require additional third-party drivers to be installed which is not supported on HoloLens.</span></span> 

- <span data-ttu-id="54c28-150">[Windows Holographic、バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2)(ビルド 19041.1128) 以降では、ユーザーはイーサネットアダプターを引き続き使用するかもしれませんが、Wi-Fi 経由で Autopilot がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="54c28-150">[Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (build 19041.1128) or later support Autopilot over Wi-Fi, although you may still use ethernet adapters.</span></span> <span data-ttu-id="54c28-151">Wi-fi 経由で接続されているデバイスの場合、ユーザーは次のことのみを行う必要があります:</span><span class="sxs-lookup"><span data-stu-id="54c28-151">For devices connected via Wi-fi, the user must only:</span></span>

     - <span data-ttu-id="54c28-152">ハチドリのシーンに移動する</span><span class="sxs-lookup"><span data-stu-id="54c28-152">Go through the hummingbird scene</span></span>
     - <span data-ttu-id="54c28-153">言語とロケールを選ぶ</span><span class="sxs-lookup"><span data-stu-id="54c28-153">Choose the language and locale</span></span>
     - <span data-ttu-id="54c28-154">目の調整を実行する</span><span class="sxs-lookup"><span data-stu-id="54c28-154">Run eye-calibration</span></span>
     - <span data-ttu-id="54c28-155">ネットワーク接続を確立する</span><span class="sxs-lookup"><span data-stu-id="54c28-155">Establish network connection</span></span>


- <span data-ttu-id="54c28-156">Windows Holographic、バージョン 20H2 では、 [Tenantlockdown CSP とAutopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot) をサポートしています。これにより、デバイスがテナントにロックされ、偶発的または故意にリセットまたはワイプが行われた場合でも、デバイスがそのテナントにバインドされたままになります。</span><span class="sxs-lookup"><span data-stu-id="54c28-156">Windows Holographic, version 20H2 supports [Tenantlockdown CSP and Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot), which locks a device to a tenant and  ensures that the device remains bound to that tenant in case of accidental or intentional resets or wipes.</span></span>  

- <span data-ttu-id="54c28-157">デバイスがまだ Azure AD のメンバーではなく、Intune (または別の MDM システム) に登録されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="54c28-157">Ensure that the devices are not already members of Azure AD, and are not enrolled in Intune (or another MDM system).</span></span> <span data-ttu-id="54c28-158">Autopilot の自己展開プロセスが、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="54c28-158">The Autopilot self-deploying process completes these steps.</span></span> <span data-ttu-id="54c28-159">デバイス関連のすべての情報がクリーン アップされていることを確認するには、Azure AD および Intune ポータル の両方の **[デバイス]** ページを確認します。</span><span class="sxs-lookup"><span data-stu-id="54c28-159">To make sure that all the device-related information is cleaned up, check the **Devices** pages in both Azure AD and Intune Portals.</span></span> <span data-ttu-id="54c28-160">「すべてのターゲットデバイスを Autopilot に変換する」機能は、HoloLens では現在サポートされていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="54c28-160">Note that "Convert all targeted devices to Autopilot" feature is not supported on HoloLens at the moment.</span></span>  

### <span data-ttu-id="54c28-161">2. Windows Autopilot でデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="54c28-161">2. Register devices in Windows Autopilot</span></span>

<span data-ttu-id="54c28-162">最初のセットアップの前に、お使いのデバイスが Windows Autopilot に登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c28-162">Your devices must be registered in Windows Autopilot before first setup.</span></span> <span data-ttu-id="54c28-163">デバイスの登録に関する MEM ドキュメントについては、「[Autopilot へのデバイスの追加」](https://docs.microsoft.com/mem/autopilot/add-devices)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="54c28-163">For MEM documentation on device registration please see [Adding devices to Autopilot](https://docs.microsoft.com/mem/autopilot/add-devices).</span></span>  

<span data-ttu-id="54c28-164">HoloLens デバイスを登録する主な方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="54c28-164">There are two primary ways to register HoloLens devices:</span></span> 

 - **<span data-ttu-id="54c28-165">販売業者は、注文時にパートナー センターにデバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="54c28-165">Reseller can register devices in the Partner Center when you place an order.</span></span>** 

   > [!NOTE]  
   > <span data-ttu-id="54c28-166">これは、デバイスを Autopilot サービスに追加する際に推奨されるパスです。</span><span class="sxs-lookup"><span data-stu-id="54c28-166">This is the recommended path for adding devices to the Autopilot service.</span></span> <span data-ttu-id="54c28-167">[詳しくはこちらをご覧ください](https://docs.microsoft.com/mem/autopilot/add-devices#reseller-distributor-or-partner-registration)。</span><span class="sxs-lookup"><span data-stu-id="54c28-167">[Learn more](https://docs.microsoft.com/mem/autopilot/add-devices#reseller-distributor-or-partner-registration).</span></span>  
   
 - <span data-ttu-id="54c28-168">**ハードウェア ハッシュ (ハードウェア ID とも呼ばれます) を取得し、MEM 管理センターにデバイスを手動で登録します**。</span><span class="sxs-lookup"><span data-stu-id="54c28-168">**Retrieve the hardware hash (also known as the hardware ID) and register the device manually in MEM admin center**.</span></span> 

**<span data-ttu-id="54c28-169">ハードウェア ハッシュを取得する</span><span class="sxs-lookup"><span data-stu-id="54c28-169">Retrieve hardware hash</span></span>**

<span data-ttu-id="54c28-170">デバイスは、OOBE プロセスの間、または後ほどデバイスの所有者が診断ログの収集プロセス ( 次の手順で説明します ) を開始したときに、そのハードウェア ハッシュを CSV ファイルに記録します。</span><span class="sxs-lookup"><span data-stu-id="54c28-170">The device records its hardware hash in a CSV file during the OOBE process, or later when a device owner starts the diagnostic log collection process (described in the following procedure).</span></span> <span data-ttu-id="54c28-171">通常、デバイスの所有者がデバイスにサインインする最初のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="54c28-171">Typically, the device owner is the first user to sign in to the device.</span></span>

1. <span data-ttu-id="54c28-172">HoloLens 2 デバイスを起動します。</span><span class="sxs-lookup"><span data-stu-id="54c28-172">Start the HoloLens 2 device.</span></span>

1. <span data-ttu-id="54c28-173">デバイスで、[ **電源** ] と [ **音量を下げる** ] のボタンを同時に押してから離します。</span><span class="sxs-lookup"><span data-stu-id="54c28-173">On the device, press the **Power** and **Volume Down** buttons at the same time and then release them.</span></span> <span data-ttu-id="54c28-174">デバイスは診断ログとハードウェア ハッシュを収集し、それらを一連の .zip ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="54c28-174">The device collects diagnostic logs and the hardware hash, and stores them in a set of .zip files.</span></span> 

   1. <span data-ttu-id="54c28-175">詳細とこれを実行する方法の説明ビデオについては、[オフライン診断](hololens-diagnostic-logs.md#offline-diagnostics)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c28-175">For full details and an instructional video for how to preform this please read about [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span> 
   
1. <span data-ttu-id="54c28-176">USB-C ケーブルを使用して、コンピューターにデバイスを接続します。</span><span class="sxs-lookup"><span data-stu-id="54c28-176">Use a USB-C cable to connect the device to a computer.</span></span>

1. <span data-ttu-id="54c28-177">コンピューターで、エクスプローラーを開きます。</span><span class="sxs-lookup"><span data-stu-id="54c28-177">On the computer, open File Explorer.</span></span> <span data-ttu-id="54c28-178">**この PC\\\<*HoloLens device name*>\\Internal Storage\\Documents** を開き、AutopilotDiagnostics.zip ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="54c28-178">Open **This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents**, and locate the AutopilotDiagnostics.zip file.</span></span>  

   > [!NOTE]  
   > <span data-ttu-id="54c28-179">.zip ファイルはすぐに使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="54c28-179">The .zip file may not immediately be available.</span></span> <span data-ttu-id="54c28-180">ファイルの準備ができていない場合は、[ドキュメント] フォルダーに HoloLensDiagnostics ファイルが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="54c28-180">If the file is not ready yet you may see a HoloLensDiagnostics.temp file in the Documents folder.</span></span> <span data-ttu-id="54c28-181">ファイルの一覧を更新するには、ウィンドウを更新します。</span><span class="sxs-lookup"><span data-stu-id="54c28-181">To update the list of files, refresh the window.</span></span>

1. <span data-ttu-id="54c28-182">AutopilotDiagnostics.zip ファイルの内容を抽出します。</span><span class="sxs-lookup"><span data-stu-id="54c28-182">Extract the contents of the AutopilotDiagnostics.zip file.</span></span>

1. <span data-ttu-id="54c28-183">抽出されたファイルで、ファイル名に "DeviceHash" プレフィックスが付いた CSV ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="54c28-183">In the extracted files, locate the CSV file that has a file name prefix of "DeviceHash."</span></span> <span data-ttu-id="54c28-184">そのファイルをコンピューターのドライブに保存し、後でアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="54c28-184">Copy that file to a drive on the computer where you can access it later.</span></span>  

   > [!IMPORTANT]  
   > <span data-ttu-id="54c28-185">CSV ファイル内のデータには、次のヘッダーと行の形式が使用されます:</span><span class="sxs-lookup"><span data-stu-id="54c28-185">The data in the CSV file should use the following header and line format:</span></span>
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

**<span data-ttu-id="54c28-186">MEM でデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="54c28-186">Register device through MEM</span></span>**

1. <span data-ttu-id="54c28-187">[Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com)で、[**デバイス]** > **[Windows]** > **[Windows 登録]** の順に選択し、[**Windows Autopilot 展開プログラム**] の [**デバイスの** > **インポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="54c28-187">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Devices** > **Windows** > **Windows enrollment**, and then select **Devices** > **Import** under **Windows Autopilot Deployment Program**.</span></span>

1. <span data-ttu-id="54c28-188">**[Windows Autopilot デバイスの追加]** の下で、[DeviceHash CSV ファイル]、**[開く]** の順に選択して、**[インポート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="54c28-188">Under **Add Windows Autopilot devices**, select the DeviceHash CSV file, select **Open**, and then select **Import**.</span></span>  
   
   > [!div class="mx-imgBorder"]
   > ![インポート コマンドを使用して、ハードウェア ハッシュをインポートします。](./images/hololens-ap-hash-import.png)
   
1. <span data-ttu-id="54c28-190">インポートが完了したら、**[デバイス]**  >  **[Windows]**  >  **[Windows の登録]**  >  **[デバイス]**  >  **[同期]**] の順に選択します。同期するデバイスの数によっては、プロセスが完了するまでに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="54c28-190">After the import finishes, select **Devices** > **Windows** > **Windows enrollment** > **Devices** > **Sync**. The process might take a few minutes to complete, depending on how many devices are being synchronized.</span></span> <span data-ttu-id="54c28-191">登録済みのデバイスを表示するには、**[更新]** を選択し ます。</span><span class="sxs-lookup"><span data-stu-id="54c28-191">To see the registered device, select **Refresh**.</span></span>  
   
   > [!div class="mx-imgBorder"]
   > ![[同期] および [更新] コマンドを使用して、デバイスの一覧を表示します。](./images/hololens-ap-devices-sync.png)  

### <span data-ttu-id="54c28-193">3. デバイスグループを作成する</span><span class="sxs-lookup"><span data-stu-id="54c28-193">3. Create a device group</span></span>

1. <span data-ttu-id="54c28-194">[Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com)で、[**グループ**の  >  **新規グループ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="54c28-194">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Groups** > **New group**.</span></span>

1. <span data-ttu-id="54c28-195">**[グループの種類]** で、**[セキュリティ]** を選択し、グループの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="54c28-195">For **Group type**, select **Security**, and then enter a group name and description.</span></span>

1. <span data-ttu-id="54c28-196">**[メンバーシップの種類]** で、**[割り当て済み]** または **[動的デバイス]** のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="54c28-196">For **Membership type**, select either **Assigned** or **Dynamic Device**.</span></span>

1. <span data-ttu-id="54c28-197">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="54c28-197">Do one of the following:</span></span>  
   
   - <span data-ttu-id="54c28-198">前の手順で **[メンバーシップの種類]** に **[割り当て済み]** を選択した場合は、**[メンバー]** を選択し、グループに Autopilot デバイスを追加します。</span><span class="sxs-lookup"><span data-stu-id="54c28-198">If you selected **Assigned** for **Membership type** in the previous step, select **Members**, and then add Autopilot devices to the group.</span></span> <span data-ttu-id="54c28-199">まだ登録されていない Autopilot デバイスは、デバイスのシリアル番号をデバイス名として使用して一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="54c28-199">Autopilot devices that aren't yet enrolled are listed by using the device serial number as the device name.</span></span>
   - <span data-ttu-id="54c28-200">前の手順で **[メンバーシップの種類]** に **[動的デバイス]** を選択した場合は、**[動的デバイス メンバー]** を選択し、**[詳細ルール]** に次のようなコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="54c28-200">If you selected **Dynamic Devices** for **Membership type** in the previous step, select **Dynamic device members**, and then enter code in **Advanced rule** that resembles the following:</span></span>
     - <span data-ttu-id="54c28-201">Autopilot デバイスをすべて含むグループを作成する場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="54c28-201">If you want to create a group that includes all of your Autopilot devices, type:</span></span> `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - <span data-ttu-id="54c28-202">Intune のグループ タグ フィールドは、Azure AD デバイスの **OrderID** 属性にマッピングされます。</span><span class="sxs-lookup"><span data-stu-id="54c28-202">Intune's group tag field maps to the **OrderID** attribute on Azure AD devices.</span></span> <span data-ttu-id="54c28-203">特定のグループ タグ (Azure AD デバイス OrderID) のあるすべての Autopilot デバイスを含むグループを作成する場合は、次のように入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c28-203">If you want to create a group that includes all of your Autopilot devices that have a specific group tag (the Azure AD device OrderID), you must type:</span></span> `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - <span data-ttu-id="54c28-204">特定の発注書 ID のあるすべての Autopilot デバイスを含むグループを作成する場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="54c28-204">If you want to create a group that includes all your Autopilot devices that have a specific Purchase Order ID, type:</span></span> `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > <span data-ttu-id="54c28-205">これらのルールは、Autopilot デバイスに固有の属性を対象としています。</span><span class="sxs-lookup"><span data-stu-id="54c28-205">These rules target attributes that are unique to Autopilot devices.</span></span>
1. <span data-ttu-id="54c28-206">**[保存]** を選択し、**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="54c28-206">Select **Save**, and then select **Create**.</span></span>

### <span data-ttu-id="54c28-207">4. 展開プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="54c28-207">4. Create a deployment profile</span></span>

1. <span data-ttu-id="54c28-208">[Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com)で、**[デバイス]**  >  **[Windows]**  >  **[Windows 登録]**  >  **[Windows Autopilot の展開プロファイル]**  >  **[プロファイルの作成]**  >  **[HoloLens]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="54c28-208">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Devices** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile** > **HoloLens**.</span></span>
   ![[プロファイルの作成] ドロップダウンには、HoloLens 項目が含まれています。](./images/hololens-ap-enrollment-profiles.png)

1. <span data-ttu-id="54c28-210">プロファイル名 と説明を入力し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="54c28-210">Enter a profile name and description, and then select **Next**.</span></span>  
   <span data-ttu-id="54c28-211">**HoloLens** を含む一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="54c28-211">You should see a list that includes **HoloLens**.</span></span> <span data-ttu-id="54c28-212">このオプションが表示されない場合は、[[フィードバック]](hololens2-autopilot.md#feedback-and-support-for-autopilot) オプションのいずれかを使用してお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="54c28-212">If this option is not present, use one of the [Feedback](hololens2-autopilot.md#feedback-and-support-for-autopilot) options to contact us.</span></span>

   > [!div class="mx-imgBorder"]
   > ![プロファイルの名前と説明を追加する](./images/hololens-ap-profile-name.png)
   
1. <span data-ttu-id="54c28-214">**[Out-of-box experience (OOBE)]** ページでは、ほとんどの設定が、この評価のために OOBE を合理化するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="54c28-214">On the **Out-of-box experience (OOBE)** page, most of the settings are pre-configured to streamline OOBE for this evaluation.</span></span> <span data-ttu-id="54c28-215">オプションで、次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="54c28-215">Optionally, you can configure the following settings:</span></span>  

   - <span data-ttu-id="54c28-216">**言語 (地域)**: OOBE の言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="54c28-216">**Language (Region)**: Select the language for OOBE.</span></span> <span data-ttu-id="54c28-217">[[HoloLens 2 でサポートされている言語]](hololens2-language-support.md) の一覧から言語を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="54c28-217">We recommend that you select a language from the list of [supported languages for HoloLens 2](hololens2-language-support.md).</span></span>
   - <span data-ttu-id="54c28-218">**キーボードを自動的に構成する**: キーボードが選択した言語と一致するかどうかを確認するには、**[はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="54c28-218">**Automatically configure keyboard**: To make sure that the keyboard matches the selected language, select **Yes**.</span></span>
   - <span data-ttu-id="54c28-219">**デバイス名テンプレートの適用**: OOBE 中にデバイス名を自動的に設定するには、**[はい]** を選択し、**[名前の入力]** にテンプレート フレーズとプレースホルダーを入力します。たとえば、4 桁の乱数のプレフィックスと`%RAND:4%`&mdash;プレースホルダーを入力します。</span><span class="sxs-lookup"><span data-stu-id="54c28-219">**Apply device name template**: To automatically set the device name during OOBE, select **Yes** and then enter the template phrase and placeholders in **Enter a name** For example, enter a prefix and `%RAND:4%`&mdash;a placeholder for a four-digit random number.</span></span>
     > [!NOTE]  
     > <span data-ttu-id="54c28-220">デバイス名テンプレートを使用する場合、OOBE プロセスは、デバイス名を適用した後、Azure AD にデバイスを参加させる前に、デバイスをさらに 1 回再起動します。</span><span class="sxs-lookup"><span data-stu-id="54c28-220">If you use a device name template, the OOBE process restarts the device one additional time after it applies the device name and before it joins the device to Azure AD.</span></span> <span data-ttu-id="54c28-221">この再起動により、新しい名前が有効になります。</span><span class="sxs-lookup"><span data-stu-id="54c28-221">This restart enables the new name to take effect.</span></span>  

   > [!div class="mx-imgBorder"]
   > ![OOBE の設定を構成する](./images/hololens-ap-profile-oobe.png)
   
1. <span data-ttu-id="54c28-223">設定を構成したら、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="54c28-223">After you configure the settings, select **Next**.</span></span>
1. <span data-ttu-id="54c28-224">**[スコープ タグ]** ページで、オプションで、このプロファイルに適用するスコープ タグを追加します。</span><span class="sxs-lookup"><span data-stu-id="54c28-224">On the **Scope tags** page, optionally add the scope tags that you want to apply to this profile.</span></span> <span data-ttu-id="54c28-225">スコープ タグの詳細については、「[分散型 IT に役割ベースのアクセス制御とスコープ タグを使用する](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="54c28-225">For more information about scope tags, see [Use role-based access control and scope tags for distributed IT](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md).</span></span> <span data-ttu-id="54c28-226">完了したら、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="54c28-226">When finished, select **Next**.</span></span>
1. <span data-ttu-id="54c28-227">**[割り当て]** ページで、**[割り当て先]** に **[選択したグループ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="54c28-227">On the **Assignments** page, select **Selected groups** for **Assign to**.</span></span>
1. <span data-ttu-id="54c28-228">**[選択したグループ]** で、**[+ 含めるグループを選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="54c28-228">Under **SELECTED GROUPS**, select **+ Select groups to include**.</span></span>
1. <span data-ttu-id="54c28-229">**[含めるグループを選択]** の一覧で、Autopilot HoloLens デバイス用に作成したデバイス グループを選択し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="54c28-229">In the **Select groups to include** list, select the device group that you created for the Autopilot HoloLens devices, and then select **Next**.</span></span>  
  
   <span data-ttu-id="54c28-230">グループを除外する場合は、**[除外するグループを選択]** を選択し、除外するグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="54c28-230">If you want to exclude any groups, select **Select groups to exclude**, and select the groups that you want to exclude.</span></span>

   > [!div class="mx-imgBorder"]
   > ![プロファイルにデバイス グループを割り当てます。](./images/hololens-ap-profile-assign-devicegroup.png)
   
1. <span data-ttu-id="54c28-232">**[レビュー + 作成]** ページで、設定を確認し、**[作成]** を作成してプロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="54c28-232">On the **Review + Create** page, review the settings and then select **Create** to create the profile.</span></span>  
   
   > [!div class="mx-imgBorder"]
   > ![レビュー + 作成](./images/hololens-ap-profile-summ.png)

### <span data-ttu-id="54c28-234">5. ESP 構成を確認する</span><span class="sxs-lookup"><span data-stu-id="54c28-234">5. Verify the ESP configuration</span></span>

<span data-ttu-id="54c28-235">[登録状態] ページ (ESP) には、MDM 管理対象ユーザーが初めてデバイスにサインインするときに実行される完全なデバイス構成プロセスの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="54c28-235">The Enrollment Status Page (ESP) displays the status of the complete device configuration process that runs when an MDM managed user signs into a device for the first time.</span></span> <span data-ttu-id="54c28-236">ESP 構成が次のようになっていることを確認し、割り当てが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="54c28-236">Make sure that your ESP configuration resembles the following, and verify that the assignments are correct.</span></span>  

> [!div class="mx-imgBorder"]
> ![ESP の構成](./images/hololens-ap-profile-settings.png)

### <span data-ttu-id="54c28-238">6. HoloLens デバイスのプロファイルの状態を確認する</span><span class="sxs-lookup"><span data-stu-id="54c28-238">6. Verify the profile status of the HoloLens devices</span></span>

1. <span data-ttu-id="54c28-239">Microsoft エンドポイント マネージャー管理センターで、**[デバイス]**  >  **[Windows]**  >  **[Windows の登録]**  >  **[デバイス]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="54c28-239">In Microsoft Endpoint Manager Admin Center, select **Devices** > **Windows** > **Windows enrollment** > **Devices**.</span></span>

1. <span data-ttu-id="54c28-240">HoloLens デバイスが一覧に表示されていること、およびプロファイルの状態が**割り当て済み**であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="54c28-240">Verify that the HoloLens devices are listed, and that their profile status is **Assigned**.</span></span>  

   > [!NOTE]  
   > <span data-ttu-id="54c28-241">デバイスにプロファイルが割り当てられるまで、数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="54c28-241">It may take a few minutes for the profile to be assigned to the device.</span></span>  

   > [!div class="mx-imgBorder"]   
   > ![デバイスとプロファイルの割り当て。](./images/hololens-ap-devices-assignments.png)

## <span data-ttu-id="54c28-243">Windows Autopilot for HoloLens 2 のユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="54c28-243">Windows Autopilot for HoloLens 2 User Experience</span></span>

<span data-ttu-id="54c28-244">上記の手順が完了すると、HoloLens 2 ユーザーは次のエクスペリエンスを実行して HoloLens デバイスをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="54c28-244">Once the above instructions are completed, your HoloLens 2 users will go through the following experience to provision their HoloLens devices:</span></span>  

1. <span data-ttu-id="54c28-245">Autopilot のエクスペリエンスには、インターネット アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="54c28-245">Autopilot experience requires internet access.</span></span> <span data-ttu-id="54c28-246">インターネットにアクセスするには、次のいずれかのオプションを使用してください。</span><span class="sxs-lookup"><span data-stu-id="54c28-246">Please use one of following options to provide internet access:</span></span>

    - <span data-ttu-id="54c28-247">デバイスを OOBE の Wi-Fi ネットワークに接続し、Autopilot エクスペリエンスを自動的に検出できるようにします。</span><span class="sxs-lookup"><span data-stu-id="54c28-247">Connect your device to a Wi-Fi network in OOBE and then let it detect Autopilot experience automatically.</span></span> <span data-ttu-id="54c28-248">これは、Autopilot エクスペリエンスが自動的に完了するまで、OOBE を操作する必要がある唯一の場合です。</span><span class="sxs-lookup"><span data-stu-id="54c28-248">This is the only time you will need to interact with OOBE until Autopilot experience completes on its own.</span></span> <span data-ttu-id="54c28-249">既定では、HoloLens 2 は、インターネットを検出した後、Autopilot を検出するために 10 秒間待機することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="54c28-249">Please note that by default HoloLens 2 waits for 10 seconds to detect Autopilot after detecting internet.</span></span> <span data-ttu-id="54c28-250">Autopilot プロファイルが 10 秒以内に検出されない場合は、OOBE に EULA が表示されます。</span><span class="sxs-lookup"><span data-stu-id="54c28-250">If no autopilot profile is detected within 10 seconds, OOBE will present EULA.</span></span> <span data-ttu-id="54c28-251">このシナリオが発生した場合は、デバイスを再起動して、Autopilot の検出をもう一度試行できるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="54c28-251">If you encounter this scenario, please reboot your device so another attempt can be made to detect Autopilot.</span></span> <span data-ttu-id="54c28-252">また、デバイスに TenantLockdown ポリシーが設定されている場合にのみ、OOBE が Autopilot を無期限に待機する場合があることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="54c28-252">Please also note that OOBE can wait indefinitely for Autopilot only if TenantLockdown policy is set on the device.</span></span>
    
    - <span data-ttu-id="54c28-253">有線インターネット接続用の「USB-C to Ethernet」アダプターを使用してデバイスをイーサネットに接続し、HoloLens 2 に Autopilot エクスペリエンスを自動的に完了させます。</span><span class="sxs-lookup"><span data-stu-id="54c28-253">Connect your device with Ethernet using "USB-C to Ethernet" adapters for wired internet connectivity and let HoloLens 2 complete Autopilot experience automatically.</span></span>
    
    - <span data-ttu-id="54c28-254">無線インターネット接続用の「USB-C to Wifi」アダプターを使用してデバイスを接続し、HoloLens 2 に Autopilot エクスペリエンスを自動的に完了させます。</span><span class="sxs-lookup"><span data-stu-id="54c28-254">Connect your device with "USB-C to Wifi" adapters for wireless internet connectivity and let HoloLens 2 complete Autopilot experience automatically.</span></span>

        > [!IMPORTANT]  
       > <span data-ttu-id="54c28-255">Autopilot 用の OOBE で Wi-Fi ネットワークを使用しようとするデバイスは、[Windows ホログラフィック バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 上にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c28-255">Devices attempting to use Wi-Fi networks in OOBE for Autopilot must be on [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2).</span></span>
       >
       > <span data-ttu-id="54c28-256">イーサネット アダプターを使用するデバイスの場合、Out-of-the-Box-Experience (OOBE) を開始する前に、デバイスをネットワークに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c28-256">For devices using ethernet adapters you must connect the device to the network before the Out-of-the-Box-Experience (OOBE) starts.</span></span> <span data-ttu-id="54c28-257">デバイスは、最初の OOBE 画面で、Autopilot デバイスとしてプロビジョニングされているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="54c28-257">The device determines whether it is provisioning as an Autopilot device while on the first OOBE screen.</span></span> <span data-ttu-id="54c28-258">デバイスがネットワークに接続できない場合、またはデバイスを Autopilot デバイスとしてプロビジョニングしないことを選択した場合、後で Autopilot プロビジョニングに変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="54c28-258">If the device cannot connect to the network, or if you choose not to provision the device as an Autopilot device, you cannot change to Autopilot provisioning at a later time.</span></span> <span data-ttu-id="54c28-259">代わりに、デバイスを Autopilot デバイスとしてプロビジョニングするには、この手順を最初からやり直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c28-259">Instead, you would have to start this procedure over in order to provision the device as an Autopilot device.</span></span>

1. <span data-ttu-id="54c28-260">デバイスは OOBE を自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="54c28-260">The device should automatically start OOBE.</span></span> <span data-ttu-id="54c28-261">OOBE を使って操作しないでください。</span><span class="sxs-lookup"><span data-stu-id="54c28-261">Do not interact with OOBE.</span></span> <span data-ttu-id="54c28-262">何もせずにリラックスしてください。</span><span class="sxs-lookup"><span data-stu-id="54c28-262">Instead sit, back and relax!</span></span> <span data-ttu-id="54c28-263">HoloLens 2 にネットワーク接続を検出させ、OOBE が自動的に完了するようにします。</span><span class="sxs-lookup"><span data-stu-id="54c28-263">Let HoloLens 2 detect network connectivity and allow it complete OOBE automatically.</span></span> <span data-ttu-id="54c28-264">OOBE 中にデバイスが再起動される場合があります。</span><span class="sxs-lookup"><span data-stu-id="54c28-264">The device may restart during OOBE.</span></span> <span data-ttu-id="54c28-265">OOBE 画面は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="54c28-265">The OOBE screens should resemble the following.</span></span>
   
   <span data-ttu-id="54c28-266">![OOBE 手順 1](./images/autopilot-welcome.jpg)
   ![OOBE 手順 2](./images/autopilot-step-complete.jpg)
   ![OOBE 手順 3](./images/autopilot-device-setup.jpg)</span><span class="sxs-lookup"><span data-stu-id="54c28-266">![OOBE step 1](./images/autopilot-welcome.jpg)
![OOBE step 2](./images/autopilot-step-complete.jpg)
![OOBE step 3](./images/autopilot-device-setup.jpg)</span></span>

1. <span data-ttu-id="54c28-267">OOBE の最後に、ユーザー名とパスワードを使用してデバイスにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="54c28-267">At the end of OOBE, you can sign in to the device by using your user name and password.</span></span>

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <span data-ttu-id="54c28-268">Tenantlockdown CSP と Autopilot</span><span class="sxs-lookup"><span data-stu-id="54c28-268">Tenantlockdown CSP and Autopilot</span></span>

<span data-ttu-id="54c28-269">HoloLens 2 デバイスでは、Windows Holographic のバージョン 20H2 での TenantLockdown CSP がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="54c28-269">HoloLens 2 devices support TenantLockdown CSP as of Windows Holographic, version 20H2.</span></span> <span data-ttu-id="54c28-270">この CSP は、デバイスのリセットまたは再フラッシュ によっても、デバイスをそのテナントにロックすることによって、デバイスを組織のテナント上に保持します。</span><span class="sxs-lookup"><span data-stu-id="54c28-270">This CSP keeps devices on the organization's tenant by locking them to that tenant even through device reset or reflash.</span></span> 

<span data-ttu-id="54c28-271">[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP は、HoloLens 2 が Autopilot のみを使用して MDM 登録に関連付けられるようにします。</span><span class="sxs-lookup"><span data-stu-id="54c28-271">[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP enables HoloLens 2 to be tied to MDM enrollment using Autopilot only.</span></span> <span data-ttu-id="54c28-272">TenantLockdown CSP の RequireNetworkInOOBE ノードが HoloLens 2 で true または false (最初に設定された) 値に設定されると、その値は、再フラッシュ、OS 更新プログラムなどにもかかわらずデバイスに残ります。</span><span class="sxs-lookup"><span data-stu-id="54c28-272">Once TenantLockdown CSP’s RequireNetworkInOOBE node is set to either true or false (initially set) value on HoloLens 2, that value remains on the device despite re-flashing, OS updates, etc.</span></span> 

<span data-ttu-id="54c28-273">HoloLens 2 で TenantLockdown CSP の RequireNetworkInOOBE ノードが true に設定されると、OOBE は、ネットワーク接続後、Autopilot プロファイルが正常にダウンロードおよび適用されるまで無期限に待機します。</span><span class="sxs-lookup"><span data-stu-id="54c28-273">Once TenantLockdown CSPs’ RequireNetworkInOOBE node is set to true on HoloLens 2, OOBE waits indefinitely for Autopilot profile to be successfully downloaded and applied, after network connectivity.</span></span> 

<span data-ttu-id="54c28-274">HoloLens 2 で TenantLockdown CSP の RequireNetworkInOOBE ノードが true に設定されると、OOBE では次の操作が許可されなくなります。</span><span class="sxs-lookup"><span data-stu-id="54c28-274">Once TenantLockdown CSPs’ RequireNetworkInOOBE node is set to true on HoloLens 2, following operations are disallowed in OOBE:</span></span> 
- <span data-ttu-id="54c28-275">ランタイム プロビジョニングを使用したローカル ユーザーの作成</span><span class="sxs-lookup"><span data-stu-id="54c28-275">Creating local user using runtime provisioning</span></span> 
- <span data-ttu-id="54c28-276">ランタイム プロビジョニングによる AAD 参加操作の実行</span><span class="sxs-lookup"><span data-stu-id="54c28-276">Performing AAD join operation via runtime provisioning</span></span> 
- <span data-ttu-id="54c28-277">OOBE エクスペリエンスでデバイスの所有者を選択する</span><span class="sxs-lookup"><span data-stu-id="54c28-277">Selecting who owns the device in OOBE experience</span></span> 

#### <span data-ttu-id="54c28-278">Intune を使用してこれを設定する方法</span><span class="sxs-lookup"><span data-stu-id="54c28-278">How to set this using Intune?</span></span> 
1. <span data-ttu-id="54c28-279">以下に示すように、カスタム OMA URI デバイス構成プロファイルを作成し、RequireNetworkInOOBE ノードに true を指定します。</span><span class="sxs-lookup"><span data-stu-id="54c28-279">Create a custom OMA URI device configuration profile and specify true for RequireNetworkInOOBE node as shown below.</span></span>
<span data-ttu-id="54c28-280">OMA-URI 値は ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE である必要があります</span><span class="sxs-lookup"><span data-stu-id="54c28-280">OMA-URI value should be ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span></span>

   > [!div class="mx-imgBorder"]
   > ![OMA-URI によるテナントのロックダウンの設定](images/hololens-tenant-lockdown.png)

1. <span data-ttu-id="54c28-282">グループを作成し、デバイス構成プロファイルをそのデバイス グループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="54c28-282">Create a group and assign the device configuration profile to that device group.</span></span> 

1. <span data-ttu-id="54c28-283">前の手順で作成したグループの HoloLens 2 デバイス メンバーを作成し、同期をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="54c28-283">Make the HoloLens 2 device member of the group created in previous step and trigger sync.</span></span>  

<span data-ttu-id="54c28-284">Intune ポータルで、デバイス構成が正常に適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="54c28-284">Verify in the Intune portal that device configuration has been successfully applied.</span></span> <span data-ttu-id="54c28-285">このデバイスの構成が HoloLens 2 デバイスに正常に適用されると、TenantLockdown の効果がアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="54c28-285">Once this device configuration successfully applies on the HoloLens 2 device, effects of TenantLockdown will be active.</span></span>

#### <span data-ttu-id="54c28-286">Intune を使用して HoloLens 2 で TenantLockdown の RequireNetworkInOOBE の設定を解除する方法</span><span class="sxs-lookup"><span data-stu-id="54c28-286">How to unset TenantLockdown’s RequireNetworkInOOBE on HoloLens 2 using Intune?</span></span> 
1. <span data-ttu-id="54c28-287">上で作成したデバイス構成が以前に割り当てられていたデバイス グループから HoloLens 2 を削除します。</span><span class="sxs-lookup"><span data-stu-id="54c28-287">Remove the HoloLens 2 from the device group to which the device configuration created above was previously assigned.</span></span> 

1. <span data-ttu-id="54c28-288">以下に示すように、カスタム OMA URI ベースのデバイス構成プロファイルを作成し、RequireNetworkInOOBE に false を指定します。</span><span class="sxs-lookup"><span data-stu-id="54c28-288">Create a custom OMA URI based device configuration profile and specify false for RequireNetworkInOOBE as shown below.</span></span> <span data-ttu-id="54c28-289">OMA-URI 値は ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE である必要があります</span><span class="sxs-lookup"><span data-stu-id="54c28-289">OMA-URI value should be ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span></span>

   > [!div class="mx-imgBorder"]
   > ![Intune の OMA URI を介して RequireNetworkInOOBE を false に設定するスクリーンショット](images/hololens-tenant-lockdown-false.png)

1. <span data-ttu-id="54c28-291">グループを作成し、デバイス構成プロファイルをそのデバイス グループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="54c28-291">Create a group and assign the device configuration profile to that device group.</span></span> 

1. <span data-ttu-id="54c28-292">前の手順で作成したグループの HoloLens 2 デバイス メンバーを作成し、同期をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="54c28-292">Make the HoloLens 2 device member of the group created in previous step and trigger sync.</span></span>

<span data-ttu-id="54c28-293">Intune ポータルで、デバイス構成が正常に適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="54c28-293">Verify in the Intune portal that device configuration has been successfully applied.</span></span> <span data-ttu-id="54c28-294">このデバイスの構成が HoloLens 2 デバイスに正常に適用されると、TenantLockdown の効果が非アクティブになります。</span><span class="sxs-lookup"><span data-stu-id="54c28-294">Once this device configuration successfully applies on the HoloLens 2 device, effects of TenantLockdown will be inactive.</span></span> 

#### <span data-ttu-id="54c28-295">TenantLockdown が true に設定された後、HoloLens で Autopilot プロファイルが割り当て解除された場合、OOBE 中にどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="54c28-295">What would happen during OOBE, if Autopilot profile is unassigned on a HoloLens after TenantLockdown was set to true?</span></span> 
<span data-ttu-id="54c28-296">OOBE は、Autopilot プロファイルがダウンロードされるのを無期限に待機し、次のダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="54c28-296">OOBE will wait indefinitely for Autopilot profile to download and following dialog will be presented.</span></span> <span data-ttu-id="54c28-297">TenantLockdown の影響を取り除くには、最初に Autopilot のみを使用してデバイスを元のテナントに登録し、TenantLockdown CSP によって導入された制限を取り除く前に、前の手順で説明したように RequireNetworkInOOBE の設定を解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c28-297">In order to remove effects of TenantLockdown, device must be enrolled with its original tenant first using Autopilot only and RequireNetworkInOOBE must be unset as described in previous step before restrictions introduced by TenantLockdown CSP are removed.</span></span> 

![ポリシーがデバイスに適用される時のデバイス内ビュー。](images/hololens-autopilot-lockdown.png)

## <span data-ttu-id="54c28-299">既知の問題 と制限事項</span><span class="sxs-lookup"><span data-stu-id="54c28-299">Known Issues & limitations</span></span>

- <span data-ttu-id="54c28-300">MEM に構成されているデバイスコンテキスト ベースのアプリケーション インストールが HoloLens に適用されない問題を調査しています。</span><span class="sxs-lookup"><span data-stu-id="54c28-300">We are investigating an issue where device-context based application install configured in MEM does not apply to HoloLens.</span></span> [<span data-ttu-id="54c28-301">「デバイス コンテキストとユーザー コンテキストのインストールの詳細」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="54c28-301">Learn more about device context and user context installs.</span></span>](https://docs.microsoft.com/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- <span data-ttu-id="54c28-302">Wi-Fi 経由で Autopilot を設定しているときに、インターネット接続が最初に確立されたときに Autopilot プロファイルがダウンロードされない場合があります。</span><span class="sxs-lookup"><span data-stu-id="54c28-302">While setting up Autopilot over Wi-Fi, there may be an instance where the Autopilot profile is not downloaded when Internet connection is first established.</span></span> <span data-ttu-id="54c28-303">この場合、使用許諾契約書 (EULA) が提示され、ユーザーは Autopilot 以外のセットアップを続行することができます。</span><span class="sxs-lookup"><span data-stu-id="54c28-303">In this case End User License Agreement (EULA) is presented and the user has the option to proceed with non-Autopilot setup experience.</span></span> <span data-ttu-id="54c28-304">Autopilot による設定を再試行するには、デバイスをスリープ状態にしてから電源を入れます。または、デバイスを再起動して、もう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="54c28-304">To retry setting up with Autopilot, put the device to sleep and then power up, or reboot the device and let it try again.</span></span>
- <span data-ttu-id="54c28-305">現時点では、HoloLens で [すべての対象デバイスをAutopilot に変換する] 機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="54c28-305">"Convert all targeted devices to Autopilot" feature is not supported on HoloLens at the moment.</span></span>  

### <span data-ttu-id="54c28-306">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="54c28-306">Troubleshooting</span></span>

<span data-ttu-id="54c28-307">以下の記事は、Autopilot に関する問題の詳細情報を参照してトラブルシューティングを行う場合に役立つリソースです。ただし、これらの記事は、Windows 10 のデスクトップ版を使用しており、HoloLens には適用されない情報もあることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="54c28-307">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>
- [<span data-ttu-id="54c28-308">Windows Autopilot - 既知の問題</span><span class="sxs-lookup"><span data-stu-id="54c28-308">Windows Autopilot - known issues</span></span>](https://docs.microsoft.com/mem/autopilot/known-issues)
- [<span data-ttu-id="54c28-309">Microsoft Intune での Windows デバイスの登録に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="54c28-309">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="54c28-310">Windows Autopilot - ポリシーの競合</span><span class="sxs-lookup"><span data-stu-id="54c28-310">Windows Autopilot - Policy Conflicts</span></span>](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <span data-ttu-id="54c28-311">Autopilot のフィードバックとサポート</span><span class="sxs-lookup"><span data-stu-id="54c28-311">Feedback and support for Autopilot</span></span>

<span data-ttu-id="54c28-312">フィードバックを提供する、または問題を報告する場合は、次のいずれかの方法を使用します:</span><span class="sxs-lookup"><span data-stu-id="54c28-312">To provide feedback or report issues, use one of the following methods:</span></span>

- <span data-ttu-id="54c28-313">デバイス登録のサポートについては、販売店または販売代理店にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="54c28-313">For support on device registration please contact your reseller or distributor.</span></span>
- <span data-ttu-id="54c28-314">Windows Autopilot についての一般的なサポートの質問、またはプロファイルの割り当て、グループの作成、または MEM ポータル コントロールに関する問題については、 [「Microsoft エンドポイント マネージャーのサポート」にお問い合わせください。](https://docs.microsoft.com/mem/get-support)</span><span class="sxs-lookup"><span data-stu-id="54c28-314">For general support inquiries about Windows Autopilot, or for issues like profile assignments, group creation or MEM portal controls, [please contact Microsoft Endpoint Manager support](https://docs.microsoft.com/mem/get-support)</span></span>  
- <span data-ttu-id="54c28-315">デバイスが Autopilot サービスに登録されていて、プロファイルが MEM ポータルに割り当てられている場合は、「HoloLens の [サポート](https://docs.microsoft.com/hololens/)」にお問い合わせください (「サポートカード」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="54c28-315">If your device is registered to the Autopilot service and the profile is assigned on MEM portal, contact HoloLens [support](https://docs.microsoft.com/hololens/) (see 'Support' card).</span></span> <span data-ttu-id="54c28-316">サポート チケットを開いて、(該当する場合は)Out-of-box-experience (OOBE) 中に [オフライン診断ログ](hololens-diagnostic-logs.md#offline-diagnostics) をキャプチャして、 スクリーンショットとログを追加します。</span><span class="sxs-lookup"><span data-stu-id="54c28-316">Please open a support ticket and if applicable, include screenshots and logs by capturing [offline diagnostic logs](hololens-diagnostic-logs.md#offline-diagnostics) during the out-of-box-experience (OOBE).</span></span>
- <span data-ttu-id="54c28-317">デバイスから問題を報告するには、HoloLens でフィードバック Hub アプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="54c28-317">To report an issue from the device, use the Feedback Hub app on your HoloLens.</span></span> <span data-ttu-id="54c28-318">フィードバック Hub で、**[エンタープライズ管理]**  >  **[デバイス]**[カテゴリ]の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="54c28-318">In Feedback Hub, select the **Enterprise Management** > **Device** category.</span></span> 
- <span data-ttu-id="54c28-319">Autopilot for HoloLens に関する一般的なフィードバックを提供するには、この[アンケート](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)を提出してください。</span><span class="sxs-lookup"><span data-stu-id="54c28-319">To provide general feedback on Autopilot for HoloLens, you can submit this [survey](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)</span></span> 


