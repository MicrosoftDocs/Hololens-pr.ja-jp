---
title: Windows Autopilot for HoloLens 2 (プライベート プレビュー)
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
ms.openlocfilehash: be9da0ec2f301705a0691bcfc9dcf9d75eac8922
ms.sourcegitcommit: cfbcdf562f949eef9cd797bbb08dfdf9f29e8fcd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "11168540"
---
# <span data-ttu-id="daf0f-104">Windows Autopilot for HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="daf0f-104">Windows Autopilot for HoloLens 2</span></span>

<span data-ttu-id="daf0f-105">Windows Autopilot プログラムに HoloLens 2 デバイスをセットアップするときに、ユーザーはシンプルなプロセスに従ってクラウドからデバイスをプロビジョニングできます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-105">When you set up HoloLens 2 devices for the Windows Autopilot program, your users can follow a simple process to provision the devices from the cloud.</span></span>

<span data-ttu-id="daf0f-106">この Autopilot プログラムは、HoloLens 2 デバイスをテナント下に共有デバイスとしてプロビジョニングする Autopilot 自己展開モードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="daf0f-106">This Autopilot program supports Autopilot self-deploying mode to provision HoloLens 2 devices as shared devices under your tenant.</span></span> <span data-ttu-id="daf0f-107">自己展開モードでは、プロビジョニング プロセス中に、デバイスのプレインストールされた OEM イメージとドライバーが利用されます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-107">Self-deploying mode leverages the device's preinstalled OEM image and drivers during the provisioning process.</span></span> <span data-ttu-id="daf0f-108">ユーザーは、デバイスを設置せず、かつ Out-of-the-box Experience (OOBE) を使用せずにデバイスをプロビジョニングできます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-108">A user can provision the device without putting the device on and going through the Out-of-the-box Experience (OOBE).</span></span> <span data-ttu-id="daf0f-109">Windows 10 の Windows Autopilot の詳細については、[ここを](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) クリックしてください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-109">To learn more about Windows Autopilot for Windows 10 click [here](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).</span></span>

<span data-ttu-id="daf0f-110">ユーザーが Autopilot の自己展開プロセスを開始すると、プロセスは次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-110">When a user starts the Autopilot self-deploying process, the process completes the following steps:</span></span>

1. <span data-ttu-id="daf0f-111">デバイスを Azure Active Directory (Azure AD) に参加させます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-111">Join the device to Azure Active Directory (Azure AD).</span></span>

   > [!NOTE]  
   > <span data-ttu-id="daf0f-112">Autopilot for HoloLens は、Active Directory への参加または Hybrid Azure AD への参加をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="daf0f-112">Autopilot for HoloLens does not support Active Directory join or Hybrid Azure AD join.</span></span>
   
1. <span data-ttu-id="daf0f-113">Azure AD を使用して、Microsoft Intune (または別の MDM サービス) にデバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-113">Use Azure AD to enroll the device in Microsoft Intune (or another MDM service).</span></span>

1. <span data-ttu-id="daf0f-114">デバイスを対象にしたポリシー、ユーザーに対象を絞ったアプリケーション、証明書、ネットワーク プロファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="daf0f-114">Download the device-targeted policies, user-targeted apps, certificates, and networking profiles.</span></span>

1. <span data-ttu-id="daf0f-115">デバイスをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="daf0f-115">Provision the device.</span></span>

1. <span data-ttu-id="daf0f-116">ユーザーにサインイン画面を提示します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-116">Present the sign-in screen to the user.</span></span>

## <span data-ttu-id="daf0f-117">Windows Autopilot for HoloLens 2 プライベート プレビュー</span><span class="sxs-lookup"><span data-stu-id="daf0f-117">Windows Autopilot for HoloLens 2 Private Preview</span></span>

<span data-ttu-id="daf0f-118">次の手順に従って、プライベート プレビューの環境を設定してください:</span><span class="sxs-lookup"><span data-stu-id="daf0f-118">Please follow the steps below to set up your environment for the private preview:</span></span>

1. <span data-ttu-id="daf0f-119">Windows Autopilot for HoloLens 2 の要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-119">Make sure that you meet the requirements for Windows Autopilot for HoloLens 2.</span></span>

1. <span data-ttu-id="daf0f-120">Windows Autopilot for HoloLens 2 プライベート プレビュー プログラムに登録します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-120">Enroll in the Windows Autopilot for HoloLens 2 private preview program.</span></span>

1. <span data-ttu-id="daf0f-121">テナントがフライトされている (プログラムに参加するために登録されている) ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-121">Verify that your tenant is flighted (enrolled to participate in the program).</span></span>

1. <span data-ttu-id="daf0f-122">Windows Autopilot にデバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-122">Register your devices in Windows Autopilot.</span></span>

1. <span data-ttu-id="daf0f-123">デバイス グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-123">Create a device group.</span></span>

1. <span data-ttu-id="daf0f-124">展開プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-124">Create a deployment profile.</span></span>

1. <span data-ttu-id="daf0f-125">ESP 構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-125">Verify the ESP configuration.</span></span>

1. <span data-ttu-id="daf0f-126">HoloLens デバイスのカスタム構成プロファイルを構成します (既知の問題)。</span><span class="sxs-lookup"><span data-stu-id="daf0f-126">Configure a custom configuration profile for HoloLens devices (known issue).</span></span>

1. <span data-ttu-id="daf0f-127">HoloLens デバイスのプロファイルの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-127">Verify the profile status of the HoloLens devices.</span></span>


### <span data-ttu-id="daf0f-128">1. Windows Autopilot for HoloLens 2 の要件を満たしていることを確認する</span><span class="sxs-lookup"><span data-stu-id="daf0f-128">1. Make sure that you meet the requirements for Windows Autopilot for HoloLens 2</span></span>

**<span data-ttu-id="daf0f-129">Windows Autopilot の要件に関する記事の次のセクションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-129">Review the following sections of the Windows Autopilot requirements article:</span></span>**

- [<span data-ttu-id="daf0f-130">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="daf0f-130">Network requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)  
- [<span data-ttu-id="daf0f-131">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="daf0f-131">Licensing requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#licensing-requirements)  
- [<span data-ttu-id="daf0f-132">構成要件</span><span class="sxs-lookup"><span data-stu-id="daf0f-132">Configuration requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#configuration-requirements)

**<span data-ttu-id="daf0f-133">Windows Autopilot 自己展開モードに関する記事の "[要件](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" のセクションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-133">Review the "[Requirements](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" section of the Windows Autopilot Self-Deploying mode article.</span></span>** <span data-ttu-id="daf0f-134">お客様の環境が、これらの要件に加えて、標準的な Windows Autopilot の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-134">Your environment has to meet these requirements as well as the standard Windows Autopilot requirements.</span></span> <span data-ttu-id="daf0f-135">記事の "ステップ バイ ステップ" と "検証" のセクションを確認する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="daf0f-135">You do not have to review the "Step by step" and "Validation" sections of the article.</span></span> <span data-ttu-id="daf0f-136">この記事の後半の手順では、HoloLens に固有の対応する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-136">The procedures later in this article provide corresponding steps that are specific to HoloLens.</span></span> <span data-ttu-id="daf0f-137">デバイスを登録して、プロファイルを構成する方法については、この記事の「[4. Windows Autopilot にデバイスを登録する](#4-register-devices-in-windows-autopilot)」および「[6. 展開プロファイルを作成する](#6-create-a-deployment-profile)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-137">For information about how to register devices and configure profiles, see [4. Register devices in Windows Autopilot](#4-register-devices-in-windows-autopilot) and [6. Create a deployment profile](#6-create-a-deployment-profile) in this article.</span></span> <span data-ttu-id="daf0f-138">これらのセクションでは、HoloLens に固有の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-138">These sections provide steps that are specific to HoloLens.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="daf0f-139">HoloLens 2 の Windows Autopilotには、オペレーティングシステム固有の要件があります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-139">Windows Autopilot for HoloLens 2 has specific operating system requirements.</span></span> <span data-ttu-id="daf0f-140">Autopilot は、HoloLens デバイスにプレインストールされている Windows Holographic バージョン 2004 (ビルド 19041.1103 以降) に依存します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-140">Autopilot relies on Windows Holographic, version 2004 (build 19041.1103 or later) being pre-installed on HoloLens devices.</span></span> <span data-ttu-id="daf0f-141">2020 年 9 月下旬までに出荷されたデバイスには、Windows Holographic バージョン 1903 がプレインストールされています。</span><span class="sxs-lookup"><span data-stu-id="daf0f-141">Devices delivered until late September 2020 have Windows Holographic, version 1903 pre-installed.</span></span> <span data-ttu-id="daf0f-142">Autopilot 対応デバイスをいつ出荷できるかについては、販売代理店にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-142">Please contact your distributor to learn about when Autopilot-ready devices can be shipped to you.</span></span> <span data-ttu-id="daf0f-143">プライベート プレビューに参加する場合は、以下の手順と要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-143">If you wish to participate to the private preview, please review instructions and requirements below.</span></span>

<span data-ttu-id="daf0f-144">HoloLens OS リリースごとの Autopilot の情報です。</span><span class="sxs-lookup"><span data-stu-id="daf0f-144">Autopilot specific information per HoloLens OS releases.</span></span>
- <span data-ttu-id="daf0f-145">Autopilot を使用するには、デバイスに [Windows ホログラフィック バージョン 2004](hololens-release-notes.md#windows-holographic-version-2004) リリース以降がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-145">In order to use Autopilot a device must have the [Windows Holographic, version 2004](hololens-release-notes.md#windows-holographic-version-2004) release or newer.</span></span>

- <span data-ttu-id="daf0f-146">Wi-Fi を使用して Autopilot を使用するには、デバイスに [Windows ホログラフィック バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2) リリース以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="daf0f-146">In order to use Autopilot by use of Wi-Fi a device must have the [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) release or newer.</span></span> <span data-ttu-id="daf0f-147">ただし、これらのビルドでは引き続きイーサネット アダプターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-147">However these builds may still use ethernet adapters.</span></span> 

- <span data-ttu-id="daf0f-148">ビルド [Windows ホログラフィック バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2) では、新しいデバイス管理オプションの [Tenantlockdown CSP と Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot) が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="daf0f-148">On builds [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) a new device management option [Tenantlockdown CSP and Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot) has been enabled.</span></span>  

<span data-ttu-id="daf0f-149">デバイスのビルド バージョンを確認または更新する場合は、デバイスを Windows 10 PC に接続して、[高度な回復コンパニオン](https://www.microsoft.com/store/productId/9P74Z35SFRS8)を起動してください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-149">If you would like to either confirm the build version on your device or update it, please connect it to your Windows 10 PC and launch [Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span> 

**<span data-ttu-id="daf0f-150">Autopilot プレビューを試す場合は、OOBE とプロビジョニング プロセスを開始する前に、HoloLens デバイスが次の要件を満たしていることを確認します:</span><span class="sxs-lookup"><span data-stu-id="daf0f-150">If you wish to try the Autopilot preview, before you start the OOBE and provisioning process, make sure that the HoloLens devices meet the following requirements:</span></span>**

- <span data-ttu-id="daf0f-151">デバイスが Windows Holographic、バージョン 2004 (ビルド19041.1103 以降) であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-151">Ensure your device is on Windows Holographic, version 2004 (build 19041.1103 or later).</span></span> <span data-ttu-id="daf0f-152">最新の OS がプレインストールされていない場合は、 [Advanced Recovery コンパニオン (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab)を使用して手動で更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-152">If the latest OS is not pre-installed you must manually update using the [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab).</span></span> <span data-ttu-id="daf0f-153">手順は [ここに](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device) あります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-153">You can find instructions [here](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span> 

- <span data-ttu-id="daf0f-154">Windows Autopilot にデバイスを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-154">Your devices must be registered in Windows Autopilot.</span></span> <span data-ttu-id="daf0f-155">デバイスを登録する方法については、[「4. Windows Autopilot にデバイスを登録する」](#4-register-devices-in-windows-autopilot) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-155">For information about how to register devices see [4. Register devices in Windows Autopilot](#4-register-devices-in-windows-autopilot).</span></span> <span data-ttu-id="daf0f-156">推奨されるパスは、リセラーまたはディストリビューターがデバイスを登録するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-156">The recommended path is for your reseller or distributor to register devices for you.</span></span>  

- <span data-ttu-id="daf0f-157">[Windows ホログラフィック バージョン 2004](hololens-release-notes.md#windows-holographic-version-2004) リリースでは、HoloLens をオンにし、Autopilot プロビジョニング プロセスを開始する前に、デバイスをインターネットに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-157">In the [Windows Holographic, version 2004](hololens-release-notes.md#windows-holographic-version-2004) release, devices need to be connected to the internet before turning on the HoloLens and initiating the Autopilot provisioning process.</span></span> <span data-ttu-id="daf0f-158">有線インターネット接続用の「USB-C to Ethernet」アダプターを使用して、デバイスをイーサネットに接続します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-158">Connect your device to Ethernet using a "USB-C to Ethernet" adapter for wired internet connectivity.</span></span>

- <span data-ttu-id="daf0f-159">[Windows ホログラフィック バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2) リリースでは、デバイスが OOBE の Wi-Fi に接続して、Autopilot を検出する場合があります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-159">In the [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) release, devices may connect to Wi-Fi in OOBE to detect Autopilot.</span></span> 

- <span data-ttu-id="daf0f-160">デバイスはまだ Azure AD のメンバーではなく、Intune (または別の MDM システム) に登録されていません。</span><span class="sxs-lookup"><span data-stu-id="daf0f-160">The devices are not already members of Azure AD, and are not enrolled in Intune (or another MDM system).</span></span> <span data-ttu-id="daf0f-161">Autopilot の自己展開プロセスが、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-161">The Autopilot self-deploying process completes these steps.</span></span> <span data-ttu-id="daf0f-162">デバイス関連のすべての情報がクリーン アップされていることを確認するには、Azure AD および Intune Portal の両方の **[デバイス]** ページを確認します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-162">To make sure that all the device-related information is cleaned up, check the **Devices** pages in both Azure AD and Intune Portals.</span></span>

- <span data-ttu-id="daf0f-163">Autopilot の自己展開モードプロファイルを構成および管理するには、[Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com)にアクセスできることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-163">To configure and manage the Autopilot self-deploying mode profiles, make sure that you have access to [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com).</span></span>


### <span data-ttu-id="daf0f-164">2. Windows Autopilot for HoloLens 2 プログラムに登録する</span><span class="sxs-lookup"><span data-stu-id="daf0f-164">2. Enroll in the Windows Autopilot for HoloLens 2 program</span></span>

**<span data-ttu-id="daf0f-165">プログラムに参加するには、テナントをプライベートプレビュープログラムに登録している必要があります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-165">To participate in the program, you must have your tenant enrolled to the Private Preview program.</span></span> <span data-ttu-id="daf0f-166">これにより、Autopilotの HoloLens 固有の Intune (別名MEM) UI コントロールが有効になります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-166">This enables HoloLens-specific Intune (aka MEM) UI controls for Autopilot.</span></span>** <span data-ttu-id="daf0f-167">これを行うには、[Windows Autopilot for HoloLens のプライベート プレゼンテーションモード要求](https://aka.ms/APHoloLensTAP)にアクセスするか、次の QR コードを使用して要求を提出します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-167">To do this, go to  [Windows Autopilot for HoloLens Private Preview request](https://aka.ms/APHoloLensTAP) or use the following QR code to submit a request.</span></span>  

![Autopilot QR コード](./images/hololens-ap-qrcode.png)  

<span data-ttu-id="daf0f-169">1週間に1回Microsoftはテナントをフライティングさせます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-169">Microsoft flights tenants once a week.</span></span> <span data-ttu-id="daf0f-170">フライティングが完了すると、メール通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-170">You will receive an email notification once the flighting is complete.</span></span> 

<span data-ttu-id="daf0f-171">この要求では、次の情報を提供してください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-171">In this request, provide the following information:</span></span>

- <span data-ttu-id="daf0f-172">テナント ドメイン</span><span class="sxs-lookup"><span data-stu-id="daf0f-172">Tenant domain</span></span>
- <span data-ttu-id="daf0f-173">テナント ID</span><span class="sxs-lookup"><span data-stu-id="daf0f-173">Tenant ID</span></span>
- <span data-ttu-id="daf0f-174">この評価に参加している HoloLens 2 デバイスの数</span><span class="sxs-lookup"><span data-stu-id="daf0f-174">Number of HoloLens 2 devices that are participating in this evaluation</span></span>
- <span data-ttu-id="daf0f-175">Autopilot の自己展開モードを使用して展開する予定の HoloLens 2 デバイスの数</span><span class="sxs-lookup"><span data-stu-id="daf0f-175">Number of HoloLens 2 devices that you plan to deploy by using Autopilot self-deploying mode</span></span>

### <span data-ttu-id="daf0f-176">3. テナントがフライトされていることを確認する</span><span class="sxs-lookup"><span data-stu-id="daf0f-176">3. Verify that your tenant is flighted</span></span>

<span data-ttu-id="daf0f-177">要求を提出した後、Autopilot プログラムに対してテナントがフライトされていることを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-177">To verify that your tenant is flighted for the Autopilot program after you submit your request, follow these steps:</span></span>

1. <span data-ttu-id="daf0f-178">[Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="daf0f-178">Sign in to [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com).</span></span>

1. <span data-ttu-id="daf0f-179">**[デバイス]**  >  **[Windows]**  >  **[Windows の登録]**  >  **[Windows Autopilot 展開プロファイル]**  >  \*\*[プロファイルの作成 \*\*]の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-179">Select **Devices** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile**.</span></span>  
   
   ![[プロファイルの作成] ドロップダウンには、HoloLens 項目が含まれています。](./images/hololens-ap-enrollment-profiles.png)
   
   <span data-ttu-id="daf0f-181">**HoloLens** を含む一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-181">You should see a list that includes **HoloLens**.</span></span> <span data-ttu-id="daf0f-182">このオプションが表示されない場合は、[[フィードバック]](hololens2-autopilot.md#feedback-for-autopilot) オプションのいずれかを使用してお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-182">If this option is not present, use one of the [Feedback](hololens2-autopilot.md#feedback-for-autopilot) options to contact us.</span></span>

### <span data-ttu-id="daf0f-183">4. Windows Autopilot にデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="daf0f-183">4. Register devices in Windows Autopilot</span></span>

<span data-ttu-id="daf0f-184">準備フェーズには、デバイスを Windows Autopilot に登録する主な方法が 2 つあります:</span><span class="sxs-lookup"><span data-stu-id="daf0f-184">In the preparation phase, there are two primary ways you can register devices to Windows Autopilot:</span></span> 

1. <span data-ttu-id="daf0f-185">**デバイスの登録を注文する場合は、販売代理店またはリセラーに連絡してください**。</span><span class="sxs-lookup"><span data-stu-id="daf0f-185">**Contact your distributor or reseller when you place an order to have your devices registered**.</span></span>

   <span data-ttu-id="daf0f-186">または</span><span class="sxs-lookup"><span data-stu-id="daf0f-186">or</span></span>
   
2. <span data-ttu-id="daf0f-187">**ハードウェアハッシュ (ハードウェア ID とも呼ばれます) を取得して、デバイスを手動で登録します**。</span><span class="sxs-lookup"><span data-stu-id="daf0f-187">**Retrieve the hardware hash (also known as the hardware ID) and register the device manually**.</span></span> 

<span data-ttu-id="daf0f-188">デバイス登録の詳細については、「[Autopilot にデバイスを追加する](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices)」のドキュメントを確認してください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-188">For more information on device registration please review the [Adding devices to Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices) documentation.</span></span>  

**<span data-ttu-id="daf0f-189">デバイス ハードウェア ハッシュを取得する</span><span class="sxs-lookup"><span data-stu-id="daf0f-189">Retrieve a device hardware hash</span></span>**

<span data-ttu-id="daf0f-190">デバイスは、OOBE プロセスの間に、またはデバイスの所有者が診断ログの収集プロセスを開始するときに、CSV ファイルにハードウェア ハッシュを 記録できます (次の手順を参照)。</span><span class="sxs-lookup"><span data-stu-id="daf0f-190">The device can record its hardware hash in a CSV file during the OOBE process, or later when a device owner starts the diagnostic log collection process (described in the following procedure).</span></span> <span data-ttu-id="daf0f-191">通常、デバイスの所有者がデバイスにサインインする最初のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="daf0f-191">Typically, the device owner is the first user to sign in to the device.</span></span>

1. <span data-ttu-id="daf0f-192">HoloLens 2 デバイスを起動します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-192">Start the HoloLens 2 device.</span></span>

1. <span data-ttu-id="daf0f-193">デバイスで、[電源] ボタンと [音量を下げる] ボタンを同時に押して離します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-193">On the device, press the Power and Volume Down buttons at the same time and then release them.</span></span> <span data-ttu-id="daf0f-194">デバイスは診断ログとハードウェア ハッシュを収集し、それらを一連の .zip ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-194">The device collects diagnostic logs and the hardware hash, and stores them in a set of .zip files.</span></span> 

   1. <span data-ttu-id="daf0f-195">詳細とこれを実行する方法の説明ビデオについては、[オフライン診断](hololens-diagnostic-logs.md#offline-diagnostics)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-195">For full details and an instructional video for how to preform this please read about [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span> 
   
1. <span data-ttu-id="daf0f-196">USB-C ケーブルを使用して、コンピューターにデバイスを接続します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-196">Use a USB-C cable to connect the device to a computer.</span></span>

1. <span data-ttu-id="daf0f-197">コンピューターで、エクスプローラーを開きます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-197">On the computer, open File Explorer.</span></span> <span data-ttu-id="daf0f-198">**この PC\\\<*HoloLens device name*>\\Internal Storage\\Documents** を開き、AutopilotDiagnostics.zip ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-198">Open **This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents**, and locate the AutopilotDiagnostics.zip file.</span></span>  

   > [!NOTE]  
   > <span data-ttu-id="daf0f-199">.zip ファイルはすぐに使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-199">The .zip file may not immediately be available.</span></span> <span data-ttu-id="daf0f-200">ファイルの準備ができていない場合は、[ドキュメント] フォルダーに HoloLensDiagnostics ファイルが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-200">If the file is not ready yet you may see a HoloLensDiagnostics.temp file in the Documents folder.</span></span> <span data-ttu-id="daf0f-201">ファイルの一覧を更新するには、ウィンドウを更新します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-201">To update the list of files, refresh the window.</span></span>

1. <span data-ttu-id="daf0f-202">AutopilotDiagnostics.zip ファイルの内容を抽出します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-202">Extract the contents of the AutopilotDiagnostics.zip file.</span></span>

1. <span data-ttu-id="daf0f-203">抽出されたファイルで、ファイル名に "DeviceHash" プレフィックスが付いた CSV ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-203">In the extracted files, locate the CSV file that has a file name prefix of "DeviceHash."</span></span> <span data-ttu-id="daf0f-204">そのファイルをコンピューターのドライブに保存し、後でアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="daf0f-204">Copy that file to a drive on the computer where you can access it later.</span></span>  

   > [!IMPORTANT]  
   > <span data-ttu-id="daf0f-205">CSV ファイル内のデータには、次のヘッダーと行の形式が使用されます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-205">The data in the CSV file should use the following header and line format:</span></span>
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

**<span data-ttu-id="daf0f-206">Windows Autopilot にデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="daf0f-206">Register the device in Windows Autopilot</span></span>**

1. <span data-ttu-id="daf0f-207">Microsoft エンドポイント マネージャー管理センターで、**[デバイス]**  >  **[Windows]**  >  **[Windows の登録]** を選択し、**[Windows Autopilot 展開プログラム]** の下の **[デバイス]**  >  **[インポート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-207">In Microsoft Endpoint Manager Admin Center, select **Devices** > **Windows** > **Windows enrollment**, and then select **Devices** > **Import** under **Windows Autopilot Deployment Program**.</span></span>

1. <span data-ttu-id="daf0f-208">**[Windows Autopilot デバイスの追加]** の下で、DeviceHash CSV ファイルを選択し、**[開く]** を選択して、**[インポート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-208">Under **Add Windows Autopilot devices**, select the DeviceHash CSV file, select **Open**, and then select **Import**.</span></span>  
   
   ![インポート コマンドを使用して、ハードウェア ハッシュをインポートします。](./images/hololens-ap-hash-import.png)
   
1. <span data-ttu-id="daf0f-210">インポートが完了したら、**[デバイス]**  >  **[Windows]**  >  **[Windows の登録]**  >  **[デバイス]**  >  **[同期]**] の順に選択します。同期するデバイスの数によっては、プロセスが完了するまでに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-210">After the import finishes, select **Devices** > **Windows** > **Windows enrollment** > **Devices** > **Sync**. The process might take a few minutes to complete, depending on how many devices are being synchronized.</span></span> <span data-ttu-id="daf0f-211">登録済みのデバイスを表示するには、**[更新]** を選択し ます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-211">To see the registered device, select **Refresh**.</span></span>  
   
   ![[同期] および [更新] コマンドを使用して、デバイスの一覧を表示します。](./images/hololens-ap-devices-sync.png)  

### <span data-ttu-id="daf0f-213">5. デバイス グループを作成する</span><span class="sxs-lookup"><span data-stu-id="daf0f-213">5. Create a device group</span></span>

1. <span data-ttu-id="daf0f-214">Microsoft エンドポイント マネージャー管理センターで、**[グループ]**  >  **[新しいグループ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-214">In Microsoft Endpoint Manager admin center, select **Groups** > **New group**.</span></span>

1. <span data-ttu-id="daf0f-215">**[グループの種類]** で、**[セキュリティ]** を選択し、グループの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-215">For **Group type**, select **Security**, and then enter a group name and description.</span></span>

1. <span data-ttu-id="daf0f-216">**[メンバーシップの種類]** で、**[割り当て済み]** または **[動的デバイス]** のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-216">For **Membership type**, select either **Assigned** or **Dynamic Device**.</span></span>

1. <span data-ttu-id="daf0f-217">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="daf0f-217">Do one of the following:</span></span>  
   
   - <span data-ttu-id="daf0f-218">前の手順で **[メンバーシップの種類]** に **[割り当て済み]** を選択した場合は、**[メンバー]** を選択し、グループに Autopilot デバイスを追加します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-218">If you selected **Assigned** for **Membership type** in the previous step, select **Members**, and then add Autopilot devices to the group.</span></span> <span data-ttu-id="daf0f-219">まだ登録されていない Autopilot デバイスは、デバイスのシリアル番号をデバイス名として使用して一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-219">Autopilot devices that aren't yet enrolled are listed by using the device serial number as the device name.</span></span>
   - <span data-ttu-id="daf0f-220">前の手順で **[メンバーシップの種類]** に **[動的デバイス]** を選択した場合は、**[動的デバイス メンバー]** を選択し、**[詳細ルール]** に次のようなコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-220">If you selected **Dynamic Devices** for **Membership type** in the previous step, select **Dynamic device members**, and then enter code in **Advanced rule** that resembles the following:</span></span>
     - <span data-ttu-id="daf0f-221">Autopilot デバイスをすべて含むグループを作成する場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-221">If you want to create a group that includes all of your Autopilot devices, type:</span></span> `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - <span data-ttu-id="daf0f-222">Intune のグループ タグ フィールドは、Azure AD デバイスの **OrderID** 属性にマッピングされます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-222">Intune's group tag field maps to the **OrderID** attribute on Azure AD devices.</span></span> <span data-ttu-id="daf0f-223">特定のグループ タグ (Azure AD デバイス OrderID) のあるすべての Autopilot デバイスを含むグループを作成する場合は、次のように入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-223">If you want to create a group that includes all of your Autopilot devices that have a specific group tag (the Azure AD device OrderID), you must type:</span></span> `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - <span data-ttu-id="daf0f-224">特定の発注書 ID のあるすべての Autopilot デバイスを含むグループを作成する場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-224">If you want to create a group that includes all your Autopilot devices that have a specific Purchase Order ID, type:</span></span> `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > <span data-ttu-id="daf0f-225">これらのルールは、Autopilot デバイスに固有の属性を対象としています。</span><span class="sxs-lookup"><span data-stu-id="daf0f-225">These rules target attributes that are unique to Autopilot devices.</span></span>
1. <span data-ttu-id="daf0f-226">**[保存]** を選択し、**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-226">Select **Save**, and then select **Create**.</span></span>

### <span data-ttu-id="daf0f-227">6. 展開プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="daf0f-227">6. Create a deployment profile</span></span>

1. <span data-ttu-id="daf0f-228">Microsoft エンドポイント マネージャー管理センターで、**[デバイス]**  >  **[Windows]**  >  **[Windows の登録]**  >  **[Windows Autopilot 展開プロファイル]**  >  **[プロファイルの作成]**  >  **[HoloLens]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-228">In Microsoft Endpoint Manager admin center, select **Devices** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile** > **HoloLens**.</span></span>
1. <span data-ttu-id="daf0f-229">[プロファイル名] と [説明] を入力し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-229">Enter a profile name and description, and then select **Next**.</span></span>  
   
   ![プロファイルの名前と説明を追加する](./images/hololens-ap-profile-name.png)
1. <span data-ttu-id="daf0f-231">**[Out-of-box experience (OOBE)]** ページでは、ほとんどの設定が、この評価のために OOBE を合理化するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="daf0f-231">On the **Out-of-box experience (OOBE)** page, most of the settings are pre-configured to streamline OOBE for this evaluation.</span></span> <span data-ttu-id="daf0f-232">オプションで、次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-232">Optionally, you can configure the following settings:</span></span>  

   - <span data-ttu-id="daf0f-233">**言語 (地域)**: OOBE の言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-233">**Language (Region)**: Select the language for OOBE.</span></span> <span data-ttu-id="daf0f-234">[[HoloLens 2 でサポートされている言語]](hololens2-language-support.md) の一覧から言語を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="daf0f-234">We recommend that you select a language from the list of [supported languages for HoloLens 2](hololens2-language-support.md).</span></span>
   - <span data-ttu-id="daf0f-235">**キーボードを自動的に構成する**: キーボードが選択した言語と一致するかどうかを確認するには、**[はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-235">**Automatically configure keyboard**: To make sure that the keyboard matches the selected language, select **Yes**.</span></span>
   - <span data-ttu-id="daf0f-236">**デバイス名テンプレートの適用**: OOBE 中にデバイス名を自動的に設定するには、**[はい]** を選択し、**[名前の入力]** にテンプレート フレーズとプレースホルダーを入力します。たとえば、4 桁の乱数のプレフィックスと`%RAND:4%`&mdash;プレースホルダーを入力します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-236">**Apply device name template**: To automatically set the device name during OOBE, select **Yes** and then enter the template phrase and placeholders in **Enter a name** For example, enter a prefix and `%RAND:4%`&mdash;a placeholder for a four-digit random number.</span></span>
     > [!NOTE]  
     > <span data-ttu-id="daf0f-237">デバイス名テンプレートを使用する場合、OOBE プロセスは、デバイス名を適用した後、Azure AD にデバイスを参加させる前に、デバイスをさらに 1 回再起動します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-237">If you use a device name template, the OOBE process restarts the device one additional time after it applies the device name and before it joins the device to Azure AD.</span></span> <span data-ttu-id="daf0f-238">この再起動により、新しい名前が有効になります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-238">This restart enables the new name to take effect.</span></span>  

   ![OOBE の設定を構成する](./images/hololens-ap-profile-oobe.png)
1. <span data-ttu-id="daf0f-240">設定を構成したら、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-240">After you configure the settings, select **Next**.</span></span>
1. <span data-ttu-id="daf0f-241">**[スコープ タグ]** ページで、オプションで、このプロファイルに適用するスコープ タグを追加します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-241">On the **Scope tags** page, optionally add the scope tags that you want to apply to this profile.</span></span> <span data-ttu-id="daf0f-242">スコープ タグの詳細については、「[分散型 IT に役割ベースのアクセス制御とスコープ タグを使用する](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-242">For more information about scope tags, see [Use role-based access control and scope tags for distributed IT](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md).</span></span> <span data-ttu-id="daf0f-243">完了したら、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-243">When finished, select **Next**.</span></span>
1. <span data-ttu-id="daf0f-244">**[割り当て]** ページで、**[割り当て先]** に **[選択したグループ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-244">On the **Assignments** page, select **Selected groups** for **Assign to**.</span></span>
1. <span data-ttu-id="daf0f-245">**[選択したグループ]** で、**[+ 含めるグループを選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-245">Under **SELECTED GROUPS**, select **+ Select groups to include**.</span></span>
1. <span data-ttu-id="daf0f-246">**[含めるグループを選択]** の一覧で、Autopilot HoloLens デバイス用に作成したデバイス グループを選択し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-246">In the **Select groups to include** list, select the device group that you created for the Autopilot HoloLens devices, and then select **Next**.</span></span>  
  
   <span data-ttu-id="daf0f-247">グループを除外する場合は、**[除外するグループを選択]** を選択し、除外するグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-247">If you want to exclude any groups, select **Select groups to exclude**, and select the groups that you want to exclude.</span></span>

   ![プロファイルにデバイス グループを割り当てます。](./images/hololens-ap-profile-assign-devicegroup.png)
   
1. <span data-ttu-id="daf0f-249">**[レビュー + 作成]** ページで、設定を確認し、**[作成]** を作成してプロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-249">On the **Review + Create** page, review the settings and then select **Create** to create the profile.</span></span>  
   
   ![レビュー + 作成](./images/hololens-ap-profile-summ.png)

### <span data-ttu-id="daf0f-251">7. ESP 構成を確認する</span><span class="sxs-lookup"><span data-stu-id="daf0f-251">7. Verify the ESP configuration</span></span>

<span data-ttu-id="daf0f-252">[登録状態] ページ (ESP) には、MDM 管理対象ユーザーが初めてデバイスにサインインするときに実行される完全なデバイス構成プロセスの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-252">The Enrollment Status Page (ESP) displays the status of the complete device configuration process that runs when an MDM managed user signs into a device for the first time.</span></span> <span data-ttu-id="daf0f-253">ESP 構成が次のようになっていることを確認し、割り当てが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-253">Make sure that your ESP configuration resembles the following, and verify that the assignments are correct.</span></span>  

> [!div class="mx-imgBorder"]
> ![ESP の構成](./images/hololens-ap-profile-settings.png)

### <span data-ttu-id="daf0f-255">8. HoloLens デバイスのプロファイルの状態を確認する</span><span class="sxs-lookup"><span data-stu-id="daf0f-255">8. Verify the profile status of the HoloLens devices</span></span>

1. <span data-ttu-id="daf0f-256">Microsoft エンドポイント マネージャー管理センターで、**[デバイス]**  >  **[Windows]**  >  **[Windows の登録]**  >  **[デバイス]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-256">In Microsoft Endpoint Manager Admin Center, select **Devices** > **Windows** > **Windows enrollment** > **Devices**.</span></span>

1. <span data-ttu-id="daf0f-257">HoloLens デバイスが一覧に表示されていること、およびプロファイルの状態が**割り当て済み**であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-257">Verify that the HoloLens devices are listed, and that their profile status is **Assigned**.</span></span>  

   > [!NOTE]  
   > <span data-ttu-id="daf0f-258">デバイスにプロファイルが割り当てられるまで、数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-258">It may take a few minutes for the profile to be assigned to the device.</span></span>  

   > [!div class="mx-imgBorder"]   
   > ![デバイスとプロファイルの割り当て。](./images/hololens-ap-devices-assignments.png)

## <span data-ttu-id="daf0f-260">Windows Autopilot for HoloLens 2 のユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="daf0f-260">Windows Autopilot for HoloLens 2 User Experience</span></span>

<span data-ttu-id="daf0f-261">上記の手順が完了すると、HoloLens 2 ユーザーは次のエクスペリエンスを実行して HoloLens デバイスをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="daf0f-261">Once the above instructions are completed, your HoloLens 2 users will go through the following experience to provision their HoloLens devices:</span></span>  

1. <span data-ttu-id="daf0f-262">Autopilot のエクスペリエンスには、インターネット アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="daf0f-262">Autopilot experience requires internet access.</span></span> <span data-ttu-id="daf0f-263">インターネットにアクセスするには、次のいずれかのオプションを使用してください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-263">Please use one of following options to provide internet access:</span></span>

    - <span data-ttu-id="daf0f-264">デバイスを OOBE の Wi-Fi ネットワークに接続し、Autopilot エクスペリエンスを自動的に検出できるようにします。</span><span class="sxs-lookup"><span data-stu-id="daf0f-264">Connect your device to a Wi-Fi network in OOBE and then let it detect Autopilot experience automatically.</span></span> <span data-ttu-id="daf0f-265">これは、Autopilot エクスペリエンスが自動的に完了するまで、OOBE を操作する必要がある唯一の場合です。</span><span class="sxs-lookup"><span data-stu-id="daf0f-265">This is the only time you will need to interact with OOBE until Autopilot experience completes on its own.</span></span> <span data-ttu-id="daf0f-266">既定では、HoloLens 2 は、インターネットを検出した後、Autopilot を検出するために 10 秒間待機することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-266">Please note that by default HoloLens 2 waits for 10 seconds to detect Autopilot after detecting internet.</span></span> <span data-ttu-id="daf0f-267">Autopilot プロファイルが 10 秒以内に検出されない場合は、OOBE に EULA が表示されます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-267">If no autopilot profile is detected within 10 seconds, OOBE will present EULA.</span></span> <span data-ttu-id="daf0f-268">このシナリオが発生した場合は、デバイスを再起動して、Autopilot の検出をもう一度試行できるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-268">If you encounter this scenario, please reboot your device so another attempt can be made to detect Autopilot.</span></span> <span data-ttu-id="daf0f-269">また、デバイスに TenantLockdown ポリシーが設定されている場合にのみ、OOBE が Autopilot を無期限に待機する場合があることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-269">Please also note that OOBE can wait indefinitely for Autopilot only if TenantLockdown policy is set on the device.</span></span>
    
    - <span data-ttu-id="daf0f-270">有線インターネット接続用の「USB-C to Ethernet」アダプターを使用してデバイスをイーサネットに接続し、HoloLens 2 に Autopilot エクスペリエンスを自動的に完了させます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-270">Connect your device with Ethernet using "USB-C to Ethernet" adapters for wired internet connectivity and let HoloLens 2 complete Autopilot experience automatically.</span></span>
    
    - <span data-ttu-id="daf0f-271">無線インターネット接続用の「USB-C to Wifi」アダプターを使用してデバイスを接続し、HoloLens 2 に Autopilot エクスペリエンスを自動的に完了させます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-271">Connect your device with "USB-C to Wifi" adapters for wireless internet connectivity and let HoloLens 2 complete Autopilot experience automatically.</span></span>

       > [!NOTE]
       > <span data-ttu-id="daf0f-272">Autopilot を使用すると、[デバイスの所有者](security-adminless-os.md#device-owner)に影響があります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-272">Using Autopilot will have an effect on the [device owner](security-adminless-os.md#device-owner).</span></span>
   
       > [!IMPORTANT]  
       > <span data-ttu-id="daf0f-273">Autopilot 用の OOBE で Wi-Fi ネットワークを使用しようとするデバイスは、[Windows ホログラフィック バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 上にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-273">Devices attempting to use Wi-Fi networks in OOBE for Autopilot must be on [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2).</span></span>
       >
       > <span data-ttu-id="daf0f-274">イーサネット アダプターを使用するデバイスの場合、Out-of-the-Box-Experience (OOBE) を開始する前に、デバイスをネットワークに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-274">For devices using ethernet adapters you must connect the device to the network before the Out-of-the-Box-Experience (OOBE) starts.</span></span> <span data-ttu-id="daf0f-275">デバイスは、最初の OOBE 画面で、Autopilot デバイスとしてプロビジョニングされているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-275">The device determines whether it is provisioning as an Autopilot device while on the first OOBE screen.</span></span> <span data-ttu-id="daf0f-276">デバイスがネットワークに接続できない場合、またはデバイスを Autopilot デバイスとしてプロビジョニングしないことを選択した場合、後で Autopilot プロビジョニングに変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="daf0f-276">If the device cannot connect to the network, or if you choose not to provision the device as an Autopilot device, you cannot change to Autopilot provisioning at a later time.</span></span> <span data-ttu-id="daf0f-277">代わりに、デバイスを Autopilot デバイスとしてプロビジョニングするには、この手順を最初からやり直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-277">Instead, you would have to start this procedure over in order to provision the device as an Autopilot device.</span></span>

1. <span data-ttu-id="daf0f-278">デバイスは OOBE を自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-278">The device should automatically start OOBE.</span></span> <span data-ttu-id="daf0f-279">OOBE を使って操作しないでください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-279">Do not interact with OOBE.</span></span> <span data-ttu-id="daf0f-280">何もせずにリラックスしてください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-280">Instead sit, back and relax!</span></span> <span data-ttu-id="daf0f-281">HoloLens 2 にネットワーク接続を検出させ、OOBE が自動的に完了するようにします。</span><span class="sxs-lookup"><span data-stu-id="daf0f-281">Let HoloLens 2 detect network connectivity and allow it complete OOBE automatically.</span></span> <span data-ttu-id="daf0f-282">OOBE 中にデバイスが再起動される場合があります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-282">The device may restart during OOBE.</span></span> <span data-ttu-id="daf0f-283">OOBE 画面は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-283">The OOBE screens should resemble the following.</span></span>
   
   <span data-ttu-id="daf0f-284">![OOBE 手順 1](./images/autopilot-welcome.jpg)
   ![OOBE 手順 2](./images/autopilot-step-complete.jpg)
   ![OOBE 手順 3](./images/autopilot-device-setup.jpg)</span><span class="sxs-lookup"><span data-stu-id="daf0f-284">![OOBE step 1](./images/autopilot-welcome.jpg)
![OOBE step 2](./images/autopilot-step-complete.jpg)
![OOBE step 3](./images/autopilot-device-setup.jpg)</span></span>

1. <span data-ttu-id="daf0f-285">OOBE の最後に、ユーザー名とパスワードを使用してデバイスにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-285">At the end of OOBE, you can sign in to the device by using your user name and password.</span></span>

   <br/><img src="./images/other-user.jpg" width="450" height="700" />

## <span data-ttu-id="daf0f-286">Tenantlockdown CSP と Autopilot</span><span class="sxs-lookup"><span data-stu-id="daf0f-286">Tenantlockdown CSP and Autopilot</span></span>
- <span data-ttu-id="daf0f-287">デバイスのリセットまたは再フラッシュを行っても、デバイスをテナントにロックすることにより、デバイスを組織のテナントに保持します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-287">Keeps devices on the organization's tenant by locking them to the tenant even through device reset or reflash.</span></span> <span data-ttu-id="daf0f-288">プロビジョニングを介したアカウントの作成を禁止することにより、セキュリティを強化します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-288">With further security by disallowing account creation in via provisioning.</span></span> 

<span data-ttu-id="daf0f-289">HoloLens 2 デバイスは、Windows ホログラフィック バージョン 20H2 以降、TenantLockdown CSP をサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="daf0f-289">HoloLens 2 devices now support TenantLockdown CSP as of Windows Holographic version 20H2.</span></span> 

<span data-ttu-id="daf0f-290">[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP は、HoloLens 2 が Autopilot のみを使用して MDM 登録に関連付けられるようにします。</span><span class="sxs-lookup"><span data-stu-id="daf0f-290">[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP enables HoloLens 2 to be tied to MDM enrollment using Autopilot only.</span></span> <span data-ttu-id="daf0f-291">TenantLockdown CSP の RequireNetworkInOOBE ノードが HoloLens 2 で true または false (最初に設定された) 値に設定されると、その値は、再フラッシュ、OS 更新プログラムなどにもかかわらずデバイスに残ります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-291">Once TenantLockdown CSP’s RequireNetworkInOOBE node is set to either true or false (initially set) value on HoloLens 2, that value remains on the device despite re-flashing, OS updates, etc.</span></span> 

<span data-ttu-id="daf0f-292">HoloLens 2 で TenantLockdown CSP の RequireNetworkInOOBE ノードが true に設定されると、OOBE は、ネットワーク接続後、Autopilot プロファイルが正常にダウンロードおよび適用されるまで無期限に待機します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-292">Once TenantLockdown CSPs’ RequireNetworkInOOBE node is set to true on HoloLens 2, OOBE waits indefinitely for Autopilot profile to be successfully downloaded and applied, after network connectivity.</span></span> 

<span data-ttu-id="daf0f-293">HoloLens 2 で TenantLockdown CSP の RequireNetworkInOOBE ノードが true に設定されると、OOBE では次の操作が許可されなくなります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-293">Once TenantLockdown CSPs’ RequireNetworkInOOBE node is set to true on HoloLens 2, following operations are disallowed in OOBE:</span></span> 
- <span data-ttu-id="daf0f-294">ランタイム プロビジョニングを使用したローカル ユーザーの作成</span><span class="sxs-lookup"><span data-stu-id="daf0f-294">Creating local user using runtime provisioning</span></span> 
- <span data-ttu-id="daf0f-295">ランタイム プロビジョニングによる AAD 参加操作の実行</span><span class="sxs-lookup"><span data-stu-id="daf0f-295">Performing AAD join operation via runtime provisioning</span></span> 
- <span data-ttu-id="daf0f-296">OOBE エクスペリエンスでデバイスの所有者を選択する</span><span class="sxs-lookup"><span data-stu-id="daf0f-296">Selecting who owns the device in OOBE experience</span></span> 

### <span data-ttu-id="daf0f-297">Intune を使用してこれを設定する方法</span><span class="sxs-lookup"><span data-stu-id="daf0f-297">How to set this using Intune?</span></span> 
1. <span data-ttu-id="daf0f-298">以下に示すように、カスタム OMA URI デバイス構成プロファイルを作成し、RequireNetworkInOOBE ノードに true を指定します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-298">Create a custom OMA URI device configuration profile and specify true for RequireNetworkInOOBE node as shown below.</span></span>
<span data-ttu-id="daf0f-299">OMA-URI 値は ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE である必要があります</span><span class="sxs-lookup"><span data-stu-id="daf0f-299">OMA-URI value should be ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span></span>

   > [!div class="mx-imgBorder"]
   > ![OMA-URI によるテナントのロックダウンの設定](images/hololens-tenant-lockdown.png)

1. <span data-ttu-id="daf0f-301">グループを作成し、デバイス構成プロファイルをそのデバイス グループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-301">Create a group and assign the device configuration profile to that device group.</span></span> 

1. <span data-ttu-id="daf0f-302">前の手順で作成したグループの HoloLens 2 デバイス メンバーを作成し、同期をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="daf0f-302">Make the HoloLens 2 device member of the group created in previous step and trigger sync.</span></span>  

<span data-ttu-id="daf0f-303">Intune ポータルで、デバイス構成が正常に適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-303">Verify in the Intune portal that device configuration has been successfully applied.</span></span> <span data-ttu-id="daf0f-304">このデバイスの構成が HoloLens 2 デバイスに正常に適用されると、TenantLockdown の効果がアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-304">Once this device configuration successfully applies on the HoloLens 2 device, effects of TenantLockdown will be active.</span></span>

### <span data-ttu-id="daf0f-305">Intune を使用して HoloLens 2 で TenantLockdown の RequireNetworkInOOBE の設定を解除する方法</span><span class="sxs-lookup"><span data-stu-id="daf0f-305">How to unset TenantLockdown’s RequireNetworkInOOBE on HoloLens 2 using Intune?</span></span> 
1. <span data-ttu-id="daf0f-306">上で作成したデバイス構成が以前に割り当てられていたデバイス グループから HoloLens 2 を削除します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-306">Remove the HoloLens 2 from the device group to which the device configuration created above was previously assigned.</span></span> 

1. <span data-ttu-id="daf0f-307">以下に示すように、カスタム OMA URI ベースのデバイス構成プロファイルを作成し、RequireNetworkInOOBE に false を指定します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-307">Create a custom OMA URI based device configuration profile and specify false for RequireNetworkInOOBE as shown below.</span></span> <span data-ttu-id="daf0f-308">OMA-URI 値は ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE である必要があります</span><span class="sxs-lookup"><span data-stu-id="daf0f-308">OMA-URI value should be ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span></span>

   > [!div class="mx-imgBorder"]
   > ![Intune の OMA URI を介して RequireNetworkInOOBE を false に設定するスクリーンショット](images/hololens-tenant-lockdown-false.png)

1. <span data-ttu-id="daf0f-310">グループを作成し、デバイス構成プロファイルをそのデバイス グループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-310">Create a group and assign the device configuration profile to that device group.</span></span> 

1. <span data-ttu-id="daf0f-311">前の手順で作成したグループの HoloLens 2 デバイス メンバーを作成し、同期をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="daf0f-311">Make the HoloLens 2 device member of the group created in previous step and trigger sync.</span></span>

<span data-ttu-id="daf0f-312">Intune ポータルで、デバイス構成が正常に適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-312">Verify in the Intune portal that device configuration has been successfully applied.</span></span> <span data-ttu-id="daf0f-313">このデバイスの構成が HoloLens 2 デバイスに正常に適用されると、TenantLockdown の効果が非アクティブになります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-313">Once this device configuration successfully applies on the HoloLens 2 device, effects of TenantLockdown will be inactive.</span></span> 

### <span data-ttu-id="daf0f-314">TenantLockdown が true に設定された後、HoloLens で Autopilot プロファイルが割り当て解除された場合、OOBE 中にどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="daf0f-314">What would happen during OOBE, if Autopilot profile is unassigned on a HoloLens after TenantLockdown was set to true?</span></span> 
<span data-ttu-id="daf0f-315">OOBE は、Autopilot プロファイルがダウンロードされるのを無期限に待機し、次のダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-315">OOBE will wait indefinitely for Autopilot profile to download and following dialog will be presented.</span></span> <span data-ttu-id="daf0f-316">TenantLockdown の影響を取り除くには、最初に Autopilot のみを使用してデバイスを元のテナントに登録し、TenantLockdown CSP によって導入された制限を取り除く前に、前の手順で説明したように RequireNetworkInOOBE の設定を解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-316">In order to remove effects of TenantLockdown, device must be enrolled with its original tenant first using Autopilot only and RequireNetworkInOOBE must be unset as described in previous step before restrictions introduced by TenantLockdown CSP are removed.</span></span> 

![ポリシーがデバイスに適用されるタイミングのデバイス内ビュー。](images/hololens-autopilot-lockdown.png)

## <span data-ttu-id="daf0f-318">既知の問題</span><span class="sxs-lookup"><span data-stu-id="daf0f-318">Known Issues</span></span>

- <span data-ttu-id="daf0f-319">Intune で構成されているデバイス コンテキスト ベースのアプリケーション インストールは、まだ機能しません。</span><span class="sxs-lookup"><span data-stu-id="daf0f-319">Device context based application install configured in Intune does not work yet.</span></span>
- <span data-ttu-id="daf0f-320">Wi-Fi で Autopilot を設定する際、インターネット接続が最初に確立され、エンド ユーザー ライセンス契約 (EULA) が表示され、ユーザーが Autopilot 以外のセットアップ エクスペリエンスを続行するオプションを使用しているときに、Autopilot プロファイルがダウンロードされない場合があります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-320">While setting up Autopilot over Wi-Fi, there may be an instance where the Autopilot profile is not downloaded when Internet connection is first established and the End User License Agreement (EULA) is presented and the user has the option to proceed with non-Autopilot setup experiences.</span></span> <span data-ttu-id="daf0f-321">Autopilot による設定を再試行するには、デバイスをスリープ状態にしてから電源を入れます。または、デバイスを再起動して、もう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-321">To retry setting up with Autopilot, put the device to sleep and then power up, or reboot the device and let it try again.</span></span>

### <span data-ttu-id="daf0f-322">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="daf0f-322">Troubleshooting</span></span>

<span data-ttu-id="daf0f-323">以下の記事は、Autopilot に関する問題の詳細情報を参照してトラブルシューティングを行う場合に役立つリソースです。ただし、これらの記事は、Windows 10 のデスクトップ版を使用しており、HoloLens には適用されない情報もあることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-323">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>
- [<span data-ttu-id="daf0f-324">Windows Autopilot - 既知の問題</span><span class="sxs-lookup"><span data-stu-id="daf0f-324">Windows Autopilot - known issues</span></span>](https://docs.microsoft.com/mem/autopilot/known-issues)
- [<span data-ttu-id="daf0f-325">Microsoft Intune での Windows デバイスの登録に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="daf0f-325">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="daf0f-326">Windows Autopilot - ポリシーの競合</span><span class="sxs-lookup"><span data-stu-id="daf0f-326">Windows Autopilot - Policy Conflicts</span></span>](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <span data-ttu-id="daf0f-327">Autopilot のフィードバック</span><span class="sxs-lookup"><span data-stu-id="daf0f-327">Feedback for Autopilot</span></span>

<span data-ttu-id="daf0f-328">フィードバックを提供する、または問題を報告する場合は、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-328">To provide feedback or report issues, use one of the following methods:</span></span>

- <span data-ttu-id="daf0f-329">フィードバック Hub アプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-329">Use the Feedback Hub app.</span></span> <span data-ttu-id="daf0f-330">このアプリは、HoloLens に接続されたコンピューターにあります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-330">You can find this app on a HoloLens-connected computer.</span></span> <span data-ttu-id="daf0f-331">フィードバック Hub で、**[エンタープライズ管理]**  >  **[デバイス]** カテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="daf0f-331">In Feedback Hub, select the **Enterprise Management** > **Device** category.</span></span> <span data-ttu-id="daf0f-332">フィードバックを提供する、または問題を報告する場合は、詳細な説明を提供してください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-332">When you provide feedback or report an issue, provide a detailed description.</span></span> <span data-ttu-id="daf0f-333">該当する場合は、スクリーンショットとログを含めてください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-333">If applicable, include screenshots and logs.</span></span>
- <span data-ttu-id="daf0f-334">デバイスの登録または Autopilot プロファイルが割り当てられていないときに、Intune で問題が発生した場合は、[https://aka.ms/apsupport](https://aka.ms/apsupport) でサポート チケットを開きます。</span><span class="sxs-lookup"><span data-stu-id="daf0f-334">If you encounter issues in Intune during registration of device or Autopilot profile not getting assigned, please open a support ticket at [https://aka.ms/apsupport](https://aka.ms/apsupport) .</span></span>
- <span data-ttu-id="daf0f-335">Autopilot での操作中に HoloLens デバイスで問題が発生した場合は、 [https://aka.ms/hlsupport](https://aka.ms/hlsupport) で [オフライン診断ログ](hololens-diagnostic-logs.md#offline-diagnostics)を使用してサポート チケットを開いてください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-335">If you encounter issues on HoloLens device during the Autopilot experience, please open a support ticket at [https://aka.ms/hlsupport](https://aka.ms/hlsupport) with [offline diagnostic logs](hololens-diagnostic-logs.md#offline-diagnostics).</span></span>

  <span data-ttu-id="daf0f-336">メッセージに詳細な説明を入力してください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-336">Provide a detailed description in your message.</span></span> <span data-ttu-id="daf0f-337">ただし、サポート担当者が特に要求しない限り、スクリーンショットやログなどのデータを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="daf0f-337">However, unless Support personnel specifically request it, do not include data such as screenshots or logs.</span></span> <span data-ttu-id="daf0f-338">このようなデータには、個人や個人を特定できる情報 (PII) が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="daf0f-338">Such data might include private or personally identifiable information (PII).</span></span>
