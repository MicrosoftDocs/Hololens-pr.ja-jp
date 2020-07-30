---
title: Windows Autopilot for HoloLens 2 (プライベート プレビュー)
description: ''
author: Teresa-Motiv
ms.author: v-tea
ms.date: 4/10/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Autopilot
manager: jarrettr
ms.openlocfilehash: 33463685818c3e864c698160776c76ec7d8cbefd
ms.sourcegitcommit: 9197b9d507d8b9b195bdf512d1b832888b53162d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "10899109"
---
# <span data-ttu-id="bcc8b-103">Windows Autopilot for HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="bcc8b-103">Windows Autopilot for HoloLens 2</span></span>

<span data-ttu-id="bcc8b-104">Windows Autopilot プログラムに HoloLens 2 デバイスをセットアップするときに、ユーザーはシンプルなプロセスに従ってクラウドからデバイスをプロビジョニングできます。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-104">When you set up HoloLens 2 devices for the Windows Autopilot program, your users can follow a simple process to provision the devices from the cloud.</span></span>

<span data-ttu-id="bcc8b-105">この Autopilot プログラムは、HoloLens 2 デバイスをテナント下に共有デバイスとしてプロビジョニングする Autopilot 自己展開モードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-105">This Autopilot program supports Autopilot self-deploying mode to provision HoloLens 2 devices as shared devices under your tenant.</span></span> <span data-ttu-id="bcc8b-106">自己展開モードでは、プロビジョニング プロセス中に、デバイスのプレインストールされた OEM イメージとドライバーが利用されます。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-106">Self-deploying mode leverages the device's preinstalled OEM image and drivers during the provisioning process.</span></span> <span data-ttu-id="bcc8b-107">ユーザーは、デバイスを設置せず、かつ Out-of-the-box Experience (OOBE) を使用せずにデバイスをプロビジョニングできます。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-107">A user can provision the device without putting the device on and going through the Out-of-the-box Experience (OOBE).</span></span> <span data-ttu-id="bcc8b-108">Windows 10 の Windows Autopilot の詳細については、[ここを](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) クリックしてください。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-108">To learn more about Windows Autopilot for Windows 10 click [here](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).</span></span>

<span data-ttu-id="bcc8b-109">ユーザーが Autopilot の自己展開プロセスを開始すると、プロセスは次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-109">When a user starts the Autopilot self-deploying process, the process completes the following steps:</span></span>

1. <span data-ttu-id="bcc8b-110">デバイスを Azure Active Directory (Azure AD) に参加させます。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-110">Join the device to Azure Active Directory (Azure AD).</span></span>
   > [!NOTE]  
   > <span data-ttu-id="bcc8b-111">Autopilot for HoloLens は、Active Directory への参加または Hybrid Azure AD への参加をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-111">Autopilot for HoloLens does not support Active Directory join or Hybrid Azure AD join.</span></span>
1. <span data-ttu-id="bcc8b-112">Azure AD を使用して、Microsoft Intune (または別の MDM サービス) にデバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-112">Use Azure AD to enroll the device in Microsoft Intune (or another MDM service).</span></span>
1. <span data-ttu-id="bcc8b-113">デバイスを対象にしたポリシー、ユーザーに対象を絞ったアプリケーション、証明書、ネットワーク プロファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-113">Download the device-targeted policies, user-targeted apps, certificates, and networking profiles.</span></span>
1. <span data-ttu-id="bcc8b-114">デバイスをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-114">Provision the device.</span></span>
1. <span data-ttu-id="bcc8b-115">ユーザーにサインイン画面を提示します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-115">Present the sign-in screen to the user.</span></span>

## <span data-ttu-id="bcc8b-116">Windows Autopilot for HoloLens 2 プライベート プレビュー</span><span class="sxs-lookup"><span data-stu-id="bcc8b-116">Windows Autopilot for HoloLens 2 Private Preview</span></span>

<span data-ttu-id="bcc8b-117">次の手順に従って、プライベート プレビューの環境を設定してください:</span><span class="sxs-lookup"><span data-stu-id="bcc8b-117">Please follow the steps below to set up your environment for the private preview:</span></span>

1. <span data-ttu-id="bcc8b-118">Windows Autopilot for HoloLens 2 の要件を満たしていることを確認する</span><span class="sxs-lookup"><span data-stu-id="bcc8b-118">Make sure that you meet the requirements for Windows Autopilot for HoloLens 2</span></span>
1. <span data-ttu-id="bcc8b-119">Windows Autopilot for HoloLens 2 プライベート プレビュー プログラムに登録する</span><span class="sxs-lookup"><span data-stu-id="bcc8b-119">Enroll in the Windows Autopilot for HoloLens 2 private preview program</span></span>
1. <span data-ttu-id="bcc8b-120">テナントがフライトされている (プログラムに参加するために登録されている) ことを確認する</span><span class="sxs-lookup"><span data-stu-id="bcc8b-120">Verify that your tenant is flighted (enrolled to participate in the program)</span></span>
1. <span data-ttu-id="bcc8b-121">Windows Autopilot にデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="bcc8b-121">Register your devices in Windows Autopilot</span></span>
1. <span data-ttu-id="bcc8b-122">デバイス グループを作成する</span><span class="sxs-lookup"><span data-stu-id="bcc8b-122">Create a device group</span></span>
1. <span data-ttu-id="bcc8b-123">展開プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="bcc8b-123">Create a deployment profile</span></span>
1. <span data-ttu-id="bcc8b-124">ESP 構成を確認する</span><span class="sxs-lookup"><span data-stu-id="bcc8b-124">Verify the ESP configuration</span></span>
1. <span data-ttu-id="bcc8b-125">HoloLens デバイスのカスタム構成プロファイルを構成する (既知の問題)</span><span class="sxs-lookup"><span data-stu-id="bcc8b-125">Configure a custom configuration profile for HoloLens devices (known issue)</span></span>
1. <span data-ttu-id="bcc8b-126">HoloLens デバイスのプロファイルの状態を確認する</span><span class="sxs-lookup"><span data-stu-id="bcc8b-126">Verify the profile status of the HoloLens devices</span></span>


### <span data-ttu-id="bcc8b-127">1. Windows Autopilot for HoloLens 2 の要件を満たしていることを確認する</span><span class="sxs-lookup"><span data-stu-id="bcc8b-127">1. Make sure that you meet the requirements for Windows Autopilot for HoloLens 2</span></span>

**<span data-ttu-id="bcc8b-128">Windows Autopilot の要件に関する記事の次のセクションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-128">Review the following sections of the Windows Autopilot requirements article:</span></span>**

- [<span data-ttu-id="bcc8b-129">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="bcc8b-129">Network requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)  
- [<span data-ttu-id="bcc8b-130">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="bcc8b-130">Licensing requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#licensing-requirements)  
- [<span data-ttu-id="bcc8b-131">構成要件</span><span class="sxs-lookup"><span data-stu-id="bcc8b-131">Configuration requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#configuration-requirements)

**<span data-ttu-id="bcc8b-132">Windows Autopilot 自己展開モードに関する記事の "[要件](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" のセクションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-132">Review the "[Requirements](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" section of the Windows Autopilot Self-Deploying mode article.</span></span>** <span data-ttu-id="bcc8b-133">お客様の環境が、これらの要件に加えて、標準的な Windows Autopilot の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-133">Your environment has to meet these requirements as well as the standard Windows Autopilot requirements.</span></span> <span data-ttu-id="bcc8b-134">記事の "ステップ バイ ステップ" と "検証" のセクションを確認する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-134">You do not have to review the "Step by step" and "Validation" sections of the article.</span></span> <span data-ttu-id="bcc8b-135">この記事の後半の手順では、HoloLens に固有の対応する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-135">The procedures later in this article provide corresponding steps that are specific to HoloLens.</span></span> <span data-ttu-id="bcc8b-136">デバイスを登録して、プロファイルを構成する方法については、この記事の「[4. Windows Autopilot にデバイスを登録する](#4-register-devices-in-windows-autopilot)」および「[6. 展開プロファイルを作成する](#6-create-a-deployment-profile)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-136">For information about how to register devices and configure profiles, see [4. Register devices in Windows Autopilot](#4-register-devices-in-windows-autopilot) and [6. Create a deployment profile](#6-create-a-deployment-profile) in this article.</span></span> <span data-ttu-id="bcc8b-137">これらのセクションでは、HoloLens に固有の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-137">These sections provide steps that are specific to HoloLens.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="bcc8b-138">他の Windows Autopilot プログラムとは異なり、Windows Autopilot for HoloLens 2 には、特定のオペレーティング システムの要件があります。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-138">Unlike other Windows Autopilot programs, Windows Autopilot for HoloLens 2 has specific operating system requirements.</span></span> <span data-ttu-id="bcc8b-139">Autopilot は、HoloLens デバイスにプレインストールされている Windows Holographic バージョン 2004 (ビルド 19041.1103 以降) に依存します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-139">Autopilot relies on Windows Holographic version 2004 (build 19041.1103 or later) being pre-installed on HoloLens devices.</span></span> <span data-ttu-id="bcc8b-140">2020 年 8 月下旬までに出荷されたデバイスには、Windows Holographic バージョン 1903 がプレインストールされています。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-140">Devices delivered until late August 2020 have Windows Holographic version 1903 pre-installed.</span></span> <span data-ttu-id="bcc8b-141">Autopilot 対応デバイスをいつ出荷できるかについては、販売代理店にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-141">Please contact your distributor to learn about when Autopilot-ready devices can be shipped to you.</span></span> <span data-ttu-id="bcc8b-142">プライベート プレビューに参加する場合は、以下の手順と要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-142">If you wish to participate to the private preview, please review instructions and requirements below.</span></span>

**<span data-ttu-id="bcc8b-143">Autopilot プレビューを試す場合は、OOBE とプロビジョニング プロセスを開始する前に、HoloLens デバイスが次の要件を満たしていることを確認します:</span><span class="sxs-lookup"><span data-stu-id="bcc8b-143">If you wish to try the Autopilot preview, before you start the OOBE and provisioning process, make sure that the HoloLens devices meet the following requirements:</span></span>**

- <span data-ttu-id="bcc8b-144">[Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) を使用して、最新の OS (Windows Holographic バージョン 2004 (ビルド 19041.1103 以降)) を手動でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-144">You must manually install the latest OS (Windows Holographic version 2004 (build 19041.1103 or later) using the [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab).</span></span> <span data-ttu-id="bcc8b-145">手順は [ここに](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device) あります。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-145">You can find instructions [here](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span> 
- <span data-ttu-id="bcc8b-146">Windows Autopilot にデバイスを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-146">Your devices must be registered in Windows Autopilot.</span></span> <span data-ttu-id="bcc8b-147">デバイスを登録する方法については、[「4. Windows Autopilot にデバイスを登録する」](#4-register-devices-in-windows-autopilot) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-147">For information about how to register devices see [4. Register devices in Windows Autopilot](#4-register-devices-in-windows-autopilot).</span></span> 
- <span data-ttu-id="bcc8b-148">現在のリリースでは、HoloLens をオンにし、Autopilot プロビジョニング プロセスを開始する前に、デバイスをインターネットに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-148">In the current release, devices need to be connected to the internet before turning on the HoloLens and initiating the Autopilot provisioning process.</span></span> <span data-ttu-id="bcc8b-149">有線インターネット接続用の「USB-C to Ethernet」アダプターを使用して、デバイスをイーサネットに接続します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-149">Connect your device to Ethernet using a "USB-C to Ethernet" adapter for wired internet connectivity.</span></span> 
- <span data-ttu-id="bcc8b-150">デバイスは、まだ Azure AD のメンバーではなく、Intune (または別の MDM システム) に登録されていません。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-150">The devices are not already members of Azure AD, and are not enrolled in Intune (or another MDM system).</span></span> <span data-ttu-id="bcc8b-151">Autopilot の自己展開プロセスが、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-151">The Autopilot self-deploying process completes these steps.</span></span> <span data-ttu-id="bcc8b-152">デバイス関連のすべての情報がクリーン アップされていることを確認するには、Azure AD および Intune Portal の両方の **[デバイス]** ページを確認します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-152">To make sure that all the device-related information is cleaned up, check the **Devices** pages in both Azure AD and Intune Portals.</span></span>
- <span data-ttu-id="bcc8b-153">Autopilot の自己展開モードプロファイルを構成および管理するには、[Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com)にアクセスできることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-153">To configure and manage the Autopilot self-deploying mode profiles, make sure that you have access to [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com).</span></span>


### <span data-ttu-id="bcc8b-154">2. Windows Autopilot for HoloLens 2 プログラムに登録する</span><span class="sxs-lookup"><span data-stu-id="bcc8b-154">2. Enroll in the Windows Autopilot for HoloLens 2 program</span></span>

**<span data-ttu-id="bcc8b-155">プログラムに参加するには、プライベート プレビュー プログラムにテナントを登録して、Autopilot の HoloLens 固有の Intune UI コントロールを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-155">To participate in the program, you must have your tenant enrolled to the Private Preview program to get the HoloLens-specific Intune UI controls for Autopilot.</span></span>** <span data-ttu-id="bcc8b-156">これを行うには、[Windows Autopilot for HoloLens のプライベート プレゼンテーションモード要求](https://aka.ms/APHoloLensTAP)にアクセスするか、次の QR コードを使用して要求を提出します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-156">To do this, go to  [Windows Autopilot for HoloLens Private Preview request](https://aka.ms/APHoloLensTAP) or use the following QR code to submit a request.</span></span>  

![Autopilot QR コード](./images/hololens-ap-qrcode.png)  

<span data-ttu-id="bcc8b-158">この要求では、次の情報を提供してください。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-158">In this request, provide the following information:</span></span>

- <span data-ttu-id="bcc8b-159">テナント ドメイン</span><span class="sxs-lookup"><span data-stu-id="bcc8b-159">Tenant domain</span></span>
- <span data-ttu-id="bcc8b-160">テナント ID</span><span class="sxs-lookup"><span data-stu-id="bcc8b-160">Tenant ID</span></span>
- <span data-ttu-id="bcc8b-161">この評価に参加している HoloLens 2 デバイスの数</span><span class="sxs-lookup"><span data-stu-id="bcc8b-161">Number of HoloLens 2 devices that are participating in this evaluation</span></span>
- <span data-ttu-id="bcc8b-162">Autopilot の自己展開モードを使用して展開する予定の HoloLens 2 デバイスの数</span><span class="sxs-lookup"><span data-stu-id="bcc8b-162">Number of HoloLens 2 devices that you plan to deploy by using Autopilot self-deploying mode</span></span>

### <span data-ttu-id="bcc8b-163">3. テナントがフライトされていることを確認する</span><span class="sxs-lookup"><span data-stu-id="bcc8b-163">3. Verify that your tenant is flighted</span></span>

<span data-ttu-id="bcc8b-164">要求を提出した後、Autopilot プログラムに対してテナントがフライトされていることを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-164">To verify that your tenant is flighted for the Autopilot program after you submit your request, follow these steps:</span></span>

1. <span data-ttu-id="bcc8b-165">[Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-165">Sign in to [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com).</span></span>
1. <span data-ttu-id="bcc8b-166">**[デバイス]**  >  **[Windows]**  >  **[Windows の登録]**  >  **[Windows Autopilot 展開プロファイル]**  >  \*\*[プロファイルの作成 \*\*]の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-166">Select **Devices** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile**.</span></span>  
   
   ![[プロファイルの作成] ドロップダウンには、HoloLens 項目が含まれています。](./images/hololens-ap-enrollment-profiles.png)
  <span data-ttu-id="bcc8b-168">**HoloLens** を含む一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-168">You should see a list that includes **HoloLens**.</span></span> <span data-ttu-id="bcc8b-169">このオプションが表示されない場合は、[[フィードバック]](#feedback) オプションのいずれかを使用してお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-169">If this option is not present, use one of the [Feedback](#feedback) options to contact us.</span></span>

### <span data-ttu-id="bcc8b-170">4. Windows Autopilot にデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="bcc8b-170">4. Register devices in Windows Autopilot</span></span>

<span data-ttu-id="bcc8b-171">準備フェーズには、デバイスを Windows Autopilot に登録する主な方法が 2 つあります:</span><span class="sxs-lookup"><span data-stu-id="bcc8b-171">In the preparation phase, there are two primary ways you can register devices to Windows Autopilot:</span></span> 

1. <span data-ttu-id="bcc8b-172">**デバイスの登録を注文する場合は、販売代理店またはリセラーに連絡してください**、または</span><span class="sxs-lookup"><span data-stu-id="bcc8b-172">**Contact your distributor or reseller when you place an order to have your devices registered** or</span></span>
2. **<span data-ttu-id="bcc8b-173">ハードウェア ハッシュ (ハードウェア ID とも呼ばれる) を取得し、デバイスを手動で登録します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-173">Retrieve the hardware hash (also known as the hardware ID) and register the device manually.</span></span>** 

<span data-ttu-id="bcc8b-174">デバイス登録の詳細については、[「Autopilot にデバイスを追加する」](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices) の文書を確認してください。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-174">For more information on device registration please review the [Adding devices to Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices) documentation.</span></span>  

**<span data-ttu-id="bcc8b-175">デバイス ハードウェア ハッシュを取得する</span><span class="sxs-lookup"><span data-stu-id="bcc8b-175">Retrieve a device hardware hash</span></span>**

<span data-ttu-id="bcc8b-176">デバイスは、OOBE プロセスの間に、またはデバイスの所有者が診断ログの収集プロセスを開始するときに、CSV ファイルにハードウェア ハッシュを 記録できます (次の手順を参照)。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-176">The device can record its hardware hash in a CSV file during the OOBE process, or later when a device owner starts the diagnostic log collection process (described in the following procedure).</span></span> <span data-ttu-id="bcc8b-177">通常、デバイスの所有者がデバイスにサインインする最初のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-177">Typically, the device owner is the first user to sign in to the device.</span></span>

1. <span data-ttu-id="bcc8b-178">HoloLens 2 デバイスを起動します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-178">Start the HoloLens 2 device.</span></span>
1. <span data-ttu-id="bcc8b-179">デバイスで、[電源] ボタンと [音量を下げる] ボタンを同時に押して離します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-179">On the device, press the Power and Volume Down buttons at the same time and then release them.</span></span> <span data-ttu-id="bcc8b-180">デバイスは診断ログとハードウェア ハッシュを収集し、それらを一連の .zip ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-180">The device collects diagnostic logs and the hardware hash, and stores them in a set of .zip files.</span></span>
1. <span data-ttu-id="bcc8b-181">USB-C ケーブルを使用して、コンピューターにデバイスを接続します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-181">Use a USB-C cable to connect the device to a computer.</span></span>
1. <span data-ttu-id="bcc8b-182">コンピューターで、エクスプローラーを開きます。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-182">On the computer, open File Explorer.</span></span> <span data-ttu-id="bcc8b-183">**この PC\\\<*HoloLens device name*>\\Internal Storage\\Documents** を開き、AutopilotDiagnostics.zip ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-183">Open **This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents**, and locate the AutopilotDiagnostics.zip file.</span></span>  

   > [!NOTE]  
   > <span data-ttu-id="bcc8b-184">.zip ファイルはすぐに使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-184">The .zip file may not immediately be available.</span></span> <span data-ttu-id="bcc8b-185">ファイルの準備ができていない場合は、[ドキュメント] フォルダーに HoloLensDiagnostics ファイルが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-185">If the file is not ready yet you may see a HoloLensDiagnostics.temp file in the Documents folder.</span></span> <span data-ttu-id="bcc8b-186">ファイルの一覧を更新するには、ウィンドウを更新します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-186">To update the list of files, refresh the window.</span></span>

1. <span data-ttu-id="bcc8b-187">AutopilotDiagnostics.zip ファイルの内容を抽出します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-187">Extract the contents of the AutopilotDiagnostics.zip file.</span></span>
1. <span data-ttu-id="bcc8b-188">抽出されたファイルで、ファイル名に "DeviceHash" プレフィックスが付いた CSV ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-188">In the extracted files, locate the CSV file that has a file name prefix of "DeviceHash."</span></span> <span data-ttu-id="bcc8b-189">そのファイルをコンピューターのドライブに保存し、後でアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-189">Copy that file to a drive on the computer where you can access it later.</span></span>  
   > [!IMPORTANT]  
   > <span data-ttu-id="bcc8b-190">CSV ファイル内のデータには、次のヘッダーと行の形式が使用されます。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-190">The data in the CSV file should use the following header and line format:</span></span>
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

**<span data-ttu-id="bcc8b-191">Windows Autopilot にデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="bcc8b-191">Register the device in Windows Autopilot</span></span>**

1. <span data-ttu-id="bcc8b-192">Microsoft エンドポイント マネージャー管理センターで、**[デバイス]**  >  **[Windows]**  >  **[Windows の登録]** を選択し、**[Windows Autopilot 展開プログラム]** の下の **[デバイス]**  >  **[インポート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-192">In Microsoft Endpoint Manager Admin Center, select **Devices** > **Windows** > **Windows enrollment**, and then select **Devices** > **Import** under **Windows Autopilot Deployment Program**.</span></span>

1. <span data-ttu-id="bcc8b-193">**[Windows Autopilot デバイスの追加]** の下で、DeviceHash CSV ファイルを選択し、**[開く]** を選択して、**[インポート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-193">Under **Add Windows Autopilot devices**, select the DeviceHash CSV file, select **Open**, and then select **Import**.</span></span>  
   
   ![インポート コマンドを使用して、ハードウェア ハッシュをインポートします。](./images/hololens-ap-hash-import.png)
1. <span data-ttu-id="bcc8b-195">インポートが完了したら、**[デバイス]**  >  **[Windows]**  >  **[Windows の登録]**  >  **[デバイス]**  >  **[同期]**] の順に選択します。同期するデバイスの数によっては、プロセスが完了するまでに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-195">After the import finishes, select **Devices** > **Windows** > **Windows enrollment** > **Devices** > **Sync**. The process might take a few minutes to complete, depending on how many devices are being synchronized.</span></span> <span data-ttu-id="bcc8b-196">登録済みのデバイスを表示するには、**[更新]** を選択し ます。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-196">To see the registered device, select **Refresh**.</span></span>  
   
   ![[同期] および [更新] コマンドを使用して、デバイスの一覧を表示します。](./images/hololens-ap-devices-sync.png)  

### <span data-ttu-id="bcc8b-198">5. デバイス グループを作成する</span><span class="sxs-lookup"><span data-stu-id="bcc8b-198">5. Create a device group</span></span>

1. <span data-ttu-id="bcc8b-199">Microsoft エンドポイント マネージャー管理センターで、**[グループ]**  >  **[新しいグループ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-199">In Microsoft Endpoint Manager admin center, select **Groups** > **New group**.</span></span>
1. <span data-ttu-id="bcc8b-200">**[グループの種類]** で、**[セキュリティ]** を選択し、グループの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-200">For **Group type**, select **Security**, and then enter a group name and description.</span></span>
1. <span data-ttu-id="bcc8b-201">**[メンバーシップの種類]** で、**[割り当て済み]** または **[動的デバイス]** のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-201">For **Membership type**, select either **Assigned** or **Dynamic Device**.</span></span>
1. <span data-ttu-id="bcc8b-202">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-202">Do one of the following:</span></span>  
   
   - <span data-ttu-id="bcc8b-203">前の手順で **[メンバーシップの種類]** に **[割り当て済み]** を選択した場合は、**[メンバー]** を選択し、グループに Autopilot デバイスを追加します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-203">If you selected **Assigned** for **Membership type** in the previous step, select **Members**, and then add Autopilot devices to the group.</span></span> <span data-ttu-id="bcc8b-204">まだ登録されていない Autopilot デバイスは、デバイスのシリアル番号をデバイス名として使用して一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-204">Autopilot devices that aren't yet enrolled are listed by using the device serial number as the device name.</span></span>
   - <span data-ttu-id="bcc8b-205">前の手順で **[メンバーシップの種類]** に **[動的デバイス]** を選択した場合は、**[動的デバイス メンバー]** を選択し、**[詳細ルール]** に次のようなコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-205">If you selected **Dynamic Devices** for **Membership type** in the previous step, select **Dynamic device members**, and then enter code in **Advanced rule** that resembles the following:</span></span>
     - <span data-ttu-id="bcc8b-206">Autopilot デバイスをすべて含むグループを作成する場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-206">If you want to create a group that includes all of your Autopilot devices, type:</span></span> `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - <span data-ttu-id="bcc8b-207">Intune のグループ タグ フィールドは、Azure AD デバイスの **OrderID** 属性にマッピングされます。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-207">Intune's group tag field maps to the **OrderID** attribute on Azure AD devices.</span></span> <span data-ttu-id="bcc8b-208">特定のグループ タグ (Azure AD デバイス OrderID) のあるすべての Autopilot デバイスを含むグループを作成する場合は、次のように入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-208">If you want to create a group that includes all of your Autopilot devices that have a specific group tag (the Azure AD device OrderID), you must type:</span></span> `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - <span data-ttu-id="bcc8b-209">特定の発注書 ID のあるすべての Autopilot デバイスを含むグループを作成する場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-209">If you want to create a group that includes all your Autopilot devices that have a specific Purchase Order ID, type:</span></span> `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > <span data-ttu-id="bcc8b-210">これらのルールは、Autopilot デバイスに固有の属性を対象としています。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-210">These rules target attributes that are unique to Autopilot devices.</span></span>
1. <span data-ttu-id="bcc8b-211">**[保存]** を選択し、**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-211">Select **Save**, and then select **Create**.</span></span>

### <span data-ttu-id="bcc8b-212">6. 展開プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="bcc8b-212">6. Create a deployment profile</span></span>

1. <span data-ttu-id="bcc8b-213">Microsoft エンドポイント マネージャー管理センターで、**[デバイス]**  >  **[Windows]**  >  **[Windows の登録]**  >  **[Windows Autopilot 展開プロファイル]**  >  **[プロファイルの作成]**  >  **[HoloLens]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-213">In Microsoft Endpoint Manager admin center, select **Devices** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile** > **HoloLens**.</span></span>
1. <span data-ttu-id="bcc8b-214">[プロファイル名] と [説明] を入力し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-214">Enter a profile name and description, and then select **Next**.</span></span>  
   
   ![プロファイルの名前と説明を追加する](./images/hololens-ap-profile-name.png)
1. <span data-ttu-id="bcc8b-216">**[Out-of-box experience (OOBE)]** ページでは、ほとんどの設定が、この評価のために OOBE を合理化するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-216">On the **Out-of-box experience (OOBE)** page, most of the settings are pre-configured to streamline OOBE for this evaluation.</span></span> <span data-ttu-id="bcc8b-217">オプションで、次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-217">Optionally, you can configure the following settings:</span></span>  

   - <span data-ttu-id="bcc8b-218">**言語 (地域)**: OOBE の言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-218">**Language (Region)**: Select the language for OOBE.</span></span> <span data-ttu-id="bcc8b-219">[[HoloLens 2 でサポートされている言語]](hololens2-language-support.md) の一覧から言語を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-219">We recommend that you select a language from the list of [supported languages for HoloLens 2](hololens2-language-support.md).</span></span>
   - <span data-ttu-id="bcc8b-220">**キーボードを自動的に構成する**: キーボードが選択した言語と一致するかどうかを確認するには、**[はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-220">**Automatically configure keyboard**: To make sure that the keyboard matches the selected language, select **Yes**.</span></span>
   - <span data-ttu-id="bcc8b-221">**デバイス名テンプレートの適用**: OOBE 中にデバイス名を自動的に設定するには、**[はい]** を選択し、**[名前の入力]** にテンプレート フレーズとプレースホルダーを入力します。たとえば、4 桁の乱数のプレフィックスと`%RAND:4%`&mdash;プレースホルダーを入力します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-221">**Apply device name template**: To automatically set the device name during OOBE, select **Yes** and then enter the template phrase and placeholders in **Enter a name** For example, enter a prefix and `%RAND:4%`&mdash;a placeholder for a four-digit random number.</span></span>
     > [!NOTE]  
     > <span data-ttu-id="bcc8b-222">デバイス名テンプレートを使用する場合、OOBE プロセスは、デバイス名を適用した後、Azure AD にデバイスを参加させる前に、デバイスをさらに 1 回再起動します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-222">If you use a device name template, the OOBE process restarts the device one additional time after it applies the device name and before it joins the device to Azure AD.</span></span> <span data-ttu-id="bcc8b-223">この再起動により、新しい名前が有効になります。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-223">This restart enables the new name to take effect.</span></span>  

   ![OOBE の設定を構成する](./images/hololens-ap-profile-oobe.png)
1. <span data-ttu-id="bcc8b-225">設定を構成したら、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-225">After you configure the settings, select **Next**.</span></span>
1. <span data-ttu-id="bcc8b-226">**[スコープ タグ]** ページで、オプションで、このプロファイルに適用するスコープ タグを追加します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-226">On the **Scope tags** page, optionally add the scope tags that you want to apply to this profile.</span></span> <span data-ttu-id="bcc8b-227">スコープ タグの詳細については、「[分散型 IT に役割ベースのアクセス制御とスコープ タグを使用する](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-227">For more information about scope tags, see [Use role-based access control and scope tags for distributed IT](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md).</span></span> <span data-ttu-id="bcc8b-228">完了したら、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-228">When finished, select **Next**.</span></span>
1. <span data-ttu-id="bcc8b-229">**[割り当て]** ページで、**[割り当て先]** に **[選択したグループ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-229">On the **Assignments** page, select **Selected groups** for **Assign to**.</span></span>
1. <span data-ttu-id="bcc8b-230">**[選択したグループ]** で、**[+ 含めるグループを選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-230">Under **SELECTED GROUPS**, select **+ Select groups to include**.</span></span>
1. <span data-ttu-id="bcc8b-231">**[含めるグループを選択]** の一覧で、Autopilot HoloLens デバイス用に作成したデバイス グループを選択し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-231">In the **Select groups to include** list, select the device group that you created for the Autopilot HoloLens devices, and then select **Next**.</span></span>  
  
   <span data-ttu-id="bcc8b-232">グループを除外する場合は、**[除外するグループを選択]** を選択し、除外するグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-232">If you want to exclude any groups, select **Select groups to exclude**, and select the groups that you want to exclude.</span></span>

   ![プロファイルにデバイス グループを割り当てます。](./images/hololens-ap-profile-assign-devicegroup.png)
1. <span data-ttu-id="bcc8b-234">**[レビュー + 作成]** ページで、設定を確認し、**[作成]** を作成してプロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-234">On the **Review + Create** page, review the settings and then select **Create** to create the profile.</span></span>  
   
   ![レビュー + 作成](./images/hololens-ap-profile-summ.png)

### <span data-ttu-id="bcc8b-236">7. ESP 構成を確認する</span><span class="sxs-lookup"><span data-stu-id="bcc8b-236">7. Verify the ESP configuration</span></span>

<span data-ttu-id="bcc8b-237">[登録状態] ページ (ESP) には、MDM 管理対象ユーザーが初めてデバイスにサインインするときに実行される完全なデバイス構成プロセスの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-237">The Enrollment Status Page (ESP) displays the status of the complete device configuration process that runs when an MDM managed user signs into a device for the first time.</span></span> <span data-ttu-id="bcc8b-238">ESP 構成が次のようになっていることを確認し、割り当てが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-238">Make sure that your ESP configuration resembles the following, and verify that the assignments are correct.</span></span>  

![ESP の構成](./images/hololens-ap-profile-settings.png)

### <span data-ttu-id="bcc8b-240">8. HoloLens デバイスのプロファイルの状態を確認する</span><span class="sxs-lookup"><span data-stu-id="bcc8b-240">8. Verify the profile status of the HoloLens devices</span></span>

1. <span data-ttu-id="bcc8b-241">Microsoft エンドポイント マネージャー管理センターで、**[デバイス]**  >  **[Windows]**  >  **[Windows の登録]**  >  **[デバイス]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-241">In Microsoft Endpoint Manager Admin Center, select **Devices** > **Windows** > **Windows enrollment** > **Devices**.</span></span>
1. <span data-ttu-id="bcc8b-242">HoloLens デバイスが一覧に表示されていること、およびプロファイルの状態が**割り当て済み**であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-242">Verify that the HoloLens devices are listed, and that their profile status is **Assigned**.</span></span>  
   > [!NOTE]  
   > <span data-ttu-id="bcc8b-243">デバイスにプロファイルが割り当てられるまで、数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-243">It may take a few minutes for the profile to be assigned to the device.</span></span>  
   
   ![デバイスとプロファイルの割り当て。](./images/hololens-ap-devices-assignments.png)

## <span data-ttu-id="bcc8b-245">Windows Autopilot for HoloLens 2 のユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="bcc8b-245">Windows Autopilot for HoloLens 2 User Experience</span></span>

<span data-ttu-id="bcc8b-246">上記の手順が完了すると、HoloLens 2 のユーザーは、次のようにして HoloLens デバイスをプロビジョニングします:</span><span class="sxs-lookup"><span data-stu-id="bcc8b-246">Once the above instructions are completed, your HoloLens 2 users will go through the following experience to provision their HoloLens devices:</span></span>  

1. <span data-ttu-id="bcc8b-247">前述のように、現在のリリースでは、HoloLens をオンにし、Autopilot プロビジョニング プロセスを開始する前に、デバイスをインターネットに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-247">As mentioned, in the current release, devices need to be connected to the internet before turning on the HoloLens and initiating the Autopilot provisioning process.</span></span> <span data-ttu-id="bcc8b-248">有線インターネット接続には「USB-C to Ethernet」アダプターを、無線インターネット接続には「USB-C to Wifi」アダプターを使用して、デバイスを Ethernet に接続します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-248">Connect your device to Ethernet using "USB-C to Ethernet" adapters for wired internet connectivity or "USB-C to Wifi" adapters for wireless internet connectivity.</span></span>
   
   > [!IMPORTANT]  
   > <span data-ttu-id="bcc8b-249">Out-of-the-Box-Experience (OOBE) を開始する前に、ネットワークにデバイスを接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-249">You must connect the device to the network before the Out-of-the-Box-Experience (OOBE) starts.</span></span> <span data-ttu-id="bcc8b-250">デバイスは、最初の OOBE 画面で、Autopilot デバイスとしてプロビジョニングされているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-250">The device determines whether it is provisioning as an Autopilot device while on the first OOBE screen.</span></span> <span data-ttu-id="bcc8b-251">デバイスがネットワークに接続できない場合、またはデバイスを Autopilot デバイスとしてプロビジョニングしないことを選択した場合、後で Autopilot プロビジョニングに変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-251">If the device cannot connect to the network, or if you choose not to provision the device as an Autopilot device, you cannot change to Autopilot provisioning at a later time.</span></span> <span data-ttu-id="bcc8b-252">代わりに、デバイスを Autopilot デバイスとしてプロビジョニングするには、この手順を最初からやり直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-252">Instead, you would have to start this procedure over in order to provision the device as an Autopilot device.</span></span>

1. <span data-ttu-id="bcc8b-253">デバイスは OOBE を自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-253">The device should automatically start OOBE.</span></span> <span data-ttu-id="bcc8b-254">OOBE を使って操作しないでください。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-254">Do not interact with OOBE.</span></span> <span data-ttu-id="bcc8b-255">何もせずにリラックスしてください。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-255">Instead sit, back and relax!</span></span> <span data-ttu-id="bcc8b-256">HoloLens 2 にネットワーク接続を検出させ、OOBE が自動的に完了するようにします。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-256">Let HoloLens 2 detect network connectivity and allow it complete OOBE automatically.</span></span> <span data-ttu-id="bcc8b-257">OOBE 中にデバイスが再起動される場合があります。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-257">The device may restart during OOBE.</span></span> <span data-ttu-id="bcc8b-258">OOBE 画面は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-258">The OOBE screens should resemble the following.</span></span>
   
   <span data-ttu-id="bcc8b-259">![OOBE 手順 1](./images/hololens-ap-uex-1.png)
   ![OOBE 手順 2](./images/hololens-ap-uex-2.png)
   ![OOBE 手順 3](./images/hololens-ap-uex-3.png)
   ![OOBE 手順4](./images/hololens-ap-uex-4.png)</span><span class="sxs-lookup"><span data-stu-id="bcc8b-259">![OOBE step 1](./images/hololens-ap-uex-1.png)
![OOBE step 2](./images/hololens-ap-uex-2.png)
![OOBE step 3](./images/hololens-ap-uex-3.png)
![OOBE step 4](./images/hololens-ap-uex-4.png)</span></span>

1. <span data-ttu-id="bcc8b-260">OOBE の最後に、ユーザー名とパスワードを使用してデバイスにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-260">At the end of OOBE, you can sign in to the device by using your user name and password.</span></span>

  ![OOBE 手順 5](./images/hololens-ap-uex-5.png)

## <span data-ttu-id="bcc8b-262">既知の問題</span><span class="sxs-lookup"><span data-stu-id="bcc8b-262">Known Issues</span></span>

- <span data-ttu-id="bcc8b-263">デバイス セキュリティ コンテキストを使うアプリケーションをインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-263">You cannot install applications that use the device security context.</span></span>

## <span data-ttu-id="bcc8b-264">フィードバック</span><span class="sxs-lookup"><span data-stu-id="bcc8b-264">Feedback</span></span>

<span data-ttu-id="bcc8b-265">フィードバックを提供する、または問題を報告する場合は、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-265">To provide feedback or report issues, use one of the following methods:</span></span>

- <span data-ttu-id="bcc8b-266">フィードバック Hub アプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-266">Use the Feedback Hub app.</span></span> <span data-ttu-id="bcc8b-267">このアプリは、HoloLens に接続されたコンピューターにあります。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-267">You can find this app on a HoloLens-connected computer.</span></span> <span data-ttu-id="bcc8b-268">フィードバック Hub で、**[エンタープライズ管理]**  >  **[デバイス]** カテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-268">In Feedback Hub, select the **Enterprise Management** > **Device** category.</span></span>  

  <span data-ttu-id="bcc8b-269">フィードバックを提供する、または問題を報告する場合は、詳細な説明を提供してください。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-269">When you provide feedback or report an issue, provide a detailed description.</span></span> <span data-ttu-id="bcc8b-270">該当する場合は、スクリーンショットとログを含めてください。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-270">If applicable, include screenshots and logs.</span></span>
- <span data-ttu-id="bcc8b-271">[hlappreview@microsoft.com](mailto:hlappreview@microsoft.com) にメール メッセージを送信してください。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-271">Send an email message to [hlappreview@microsoft.com](mailto:hlappreview@microsoft.com).</span></span> <span data-ttu-id="bcc8b-272">メールの件名については、**\<*Tenant*> Autopilot for HoloLens 2 評価フィードバック** (ここで、\<*Tenant*> は Intune テナントの名前です) と入力してください。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-272">For the email subject, enter **\<*Tenant*> Autopilot for HoloLens 2 evaluation feedback** (where \<*Tenant*> is the name of your Intune tenant).</span></span>

  <span data-ttu-id="bcc8b-273">メッセージに詳細な説明を入力してください。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-273">Provide a detailed description in your message.</span></span> <span data-ttu-id="bcc8b-274">ただし、サポート担当者が特に要求しない限り、スクリーンショットやログなどのデータを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-274">However, unless Support personnel specifically request it, do not include data such as screenshots or logs.</span></span> <span data-ttu-id="bcc8b-275">このようなデータには、個人や個人を特定できる情報 (PII) が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bcc8b-275">Such data might include private or personally identifiable information (PII).</span></span>
