---
title: MAC アドレスが制限された Wi-Fi 環境での HoloLens デバイスのエンタープライズ登録
description: HoloLens 2 デバイスでネットワークの MAC アドレスを設定する方法
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2b0ed266389ccc5a21117a604a6eb0abd214d4d1
ms.sourcegitcommit: 1793f53f9e1cc63ac40edc09e65bb4beb80a4575
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "11093240"
---
# <span data-ttu-id="a94d0-103">MAC アドレスが制限された Wi-Fi 環境での HoloLens デバイスのエンタープライズ登録</span><span class="sxs-lookup"><span data-stu-id="a94d0-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="a94d0-104">このドキュメントでは、Wi-Fi が MAC アドレスのために制限されている、またはワイヤレス ネットワークに参加するために証明書が必要な、お客様の環境内で特定された一般的なシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a94d0-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <span data-ttu-id="a94d0-105">シナリオ例</span><span class="sxs-lookup"><span data-stu-id="a94d0-105">Example Scenario</span></span>

<span data-ttu-id="a94d0-106">安全な環境にいる多くの顧客は、(MACアドレスに基づいて) 承認されたデバイスのみが正常に接続できる (ワイヤレスアクセスポイントまたはDHCPサーバーでのMACアドレスフィルタリングを使用) ようにするワイヤレスまたは有線ネットワークに制限があります。</span><span class="sxs-lookup"><span data-stu-id="a94d0-106">Many customers in secure environments have restrictions on their Wireless or wired networks which will only allow approved devices (based on MAC Addresses) to connect successfully (either with MAC Address filtering on a Wireless Access Point or on a DHCP server).</span></span> <span data-ttu-id="a94d0-107">さらに、一部のワイヤレスネットワークは PEAP で保護できます。これには、ワイヤレスネットワークを正常に認証する前に、デバイスに証明書を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a94d0-107">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to being able to successfully authenticate the Wireless network.</span></span>

<span data-ttu-id="a94d0-108">HoloLens デバイスでは、2 つの重要な問題が発生する可能性があります。これにより、HoloLens デバイスをネットワークに参加させる際に遅延や手作業が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a94d0-108">Two key issues can arise with HoloLens devices, which can cause delays and manual work in joining the HoloLens Devices to the network.</span></span>

- <span data-ttu-id="a94d0-109">デバイスがワイヤレスネットワークに正常に参加する前に、ワイヤレス PEAP 証明書をデバイスに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a94d0-109">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="a94d0-110">HoloLens Wi-fi アダプターの MAC アドレスが登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a94d0-110">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="a94d0-111">これに対する主な課題は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a94d0-111">The key challenges to this are:</span></span>

1. <span data-ttu-id="a94d0-112">現在、MACアドレスは、デバイスの設定アプリから、またはIntuneの登録が成功した後に、Intuneから識別できます。</span><span class="sxs-lookup"><span data-stu-id="a94d0-112">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful Intune enrollment.</span></span>
2. <span data-ttu-id="a94d0-113">MACアドレスがないと、デバイスはWi-Fiネットワークに参加して登録を開始できません。</span><span class="sxs-lookup"><span data-stu-id="a94d0-113">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>
3. <span data-ttu-id="a94d0-114">これらの課題を手動で解決するには、技術者がデバイスに関与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a94d0-114">Manual Solutions to these challenges require technician involvement with the devices.</span></span>

## <span data-ttu-id="a94d0-115">解決策</span><span class="sxs-lookup"><span data-stu-id="a94d0-115">Solutions</span></span>

<span data-ttu-id="a94d0-116">環境内で利用可能なインフラストラクチャに応じて、この状況を改善する方法はいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="a94d0-116">There are a number of ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="a94d0-117">解決策</span><span class="sxs-lookup"><span data-stu-id="a94d0-117">Solution</span></span> | <span data-ttu-id="a94d0-118">メリット</span><span class="sxs-lookup"><span data-stu-id="a94d0-118">Benefits</span></span> | <span data-ttu-id="a94d0-119">要件</span><span class="sxs-lookup"><span data-stu-id="a94d0-119">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="a94d0-120">イーサネット アダプターを使用したプロビジョニング パッケージ</span><span class="sxs-lookup"><span data-stu-id="a94d0-120">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="a94d0-121">OOBE エクスペリエンスを向上させ、より迅速な技術者エクスペリエンスを可能にします。</span><span class="sxs-lookup"><span data-stu-id="a94d0-121">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="a94d0-122">HoloLens と互換性のある USBC HubTechnician は、MAC キャプチャと OOBE のファイナライズのために引き続きデバイスと通信する必要があります</span><span class="sxs-lookup"><span data-stu-id="a94d0-122">HoloLens compatible USB C HubTechnician will still need to interact with the device for MAC Capture and OOBE finalisation</span></span> |
| <span data-ttu-id="a94d0-123">イーサネット経由の Intune 登録による Autopilot</span><span class="sxs-lookup"><span data-stu-id="a94d0-123">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="a94d0-124">シングルステップ接続と顧客環境へのデバイスの登録 MACキ ャプチャは、デバイスとの通信なしで完了できます</span><span class="sxs-lookup"><span data-stu-id="a94d0-124">Single Step connection and registration of the device to the customer environmentMAC capture can be completed without interacting with the device</span></span> | <span data-ttu-id="a94d0-125">お客様の AAD Tenant HoloLens 互換 USB-C ネットワーク アダプターで Intune が有効になっています</span><span class="sxs-lookup"><span data-stu-id="a94d0-125">Intune enabled for the customer AAD TenantHoloLens Compatible USB-C network adaptor</span></span> |
| <span data-ttu-id="a94d0-126">MAC アドレスの自動レポート</span><span class="sxs-lookup"><span data-stu-id="a94d0-126">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="a94d0-127">デバイスが Intune テナント内に登録されたら、技術者への MAC アドレスのレポートをスクリプト化します。</span><span class="sxs-lookup"><span data-stu-id="a94d0-127">When devices have been registered within the Intune Tenant, Script the reporting of the MAC address to the technician.</span></span> | <span data-ttu-id="a94d0-128">Intune Powershell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="a94d0-128">Intune Powershell Commandlets</span></span> |

## <span data-ttu-id="a94d0-129">イーサネット アダプターを使用したプロビジョニング パッケージ</span><span class="sxs-lookup"><span data-stu-id="a94d0-129">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="a94d0-130">有線ネットワークにも MAC 制限が適用される場合は、USB-C イーサネット アダプター/ハブの MAC アドレスを事前に承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a94d0-130">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Ethernet adaptor / Hub will need to be pre-approved.</span></span> <span data-ttu-id="a94d0-131">このハブには他のデバイスからネットワークにアクセスできるようになるため、注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="a94d0-131">Care should be taken with this hub as it will allow access to the network from other devices.</span></span>

### <span data-ttu-id="a94d0-132">要件</span><span class="sxs-lookup"><span data-stu-id="a94d0-132">Requirements</span></span>

- <span data-ttu-id="a94d0-133">カスタマー ネットワークにアクセスできる有線ネットワーク ポート</span><span class="sxs-lookup"><span data-stu-id="a94d0-133">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="a94d0-134">イーサネット アダプターを含む HoloLens 互換の USB-C ハブ – 追加のドライバーやアプリケーションのインストールを必要としないハブが適しています。</span><span class="sxs-lookup"><span data-stu-id="a94d0-134">HoloLens Compatible USB-C Hub containing an Ethernet adaptor – Any hub that doesn&#39;t require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="a94d0-135">以下を含むプロビジョニング パッケージ：</span><span class="sxs-lookup"><span data-stu-id="a94d0-135">Provisioning Package containing:</span></span>
  - <span data-ttu-id="a94d0-136">ワイヤレス ネットワーク情報と証明書が含まれている</span><span class="sxs-lookup"><span data-stu-id="a94d0-136">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="a94d0-137">オプションで、組織の AzureAD の登録情報が含まれている</span><span class="sxs-lookup"><span data-stu-id="a94d0-137">Optionally containing enrollment information for the Organisation&#39;s Azure AD</span></span>
  - <span data-ttu-id="a94d0-138">その他の必要なプロビジョニング設定が含まれている</span><span class="sxs-lookup"><span data-stu-id="a94d0-138">Containing any other required provisioning settings</span></span>

### <span data-ttu-id="a94d0-139">Process</span><span class="sxs-lookup"><span data-stu-id="a94d0-139">Process</span></span>

<span data-ttu-id="a94d0-140">このプロセスは、デバイスのソフトウェア レベルによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a94d0-140">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="a94d0-141">デバイスに [2004 年 5 月](hololens-release-notes.md#windows-holographic-version-2004)の更新がある場合は、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a94d0-141">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="a94d0-142">プロビジョニング パッケージを USB スティックのルートに配置し、ハブに接続します。</span><span class="sxs-lookup"><span data-stu-id="a94d0-142">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="a94d0-143">イーサネット ケーブルをハブに接続します。</span><span class="sxs-lookup"><span data-stu-id="a94d0-143">Connect Ethernet cable to the hub.</span></span>
3. <span data-ttu-id="a94d0-144">USB-C ハブを HoloLens デバイスに接続します。</span><span class="sxs-lookup"><span data-stu-id="a94d0-144">Connect USB-C hub to HoloLens device.</span></span>
4. <span data-ttu-id="a94d0-145">HoloLens デバイスの電源を入れ、デバイスを装着します。</span><span class="sxs-lookup"><span data-stu-id="a94d0-145">Turn on HoloLens Device and wear the device.</span></span>
5. <span data-ttu-id="a94d0-146">**ボリューム ダウン ボタンと電源ボタン**を押して、プロビジョニング パッケージを適用します。</span><span class="sxs-lookup"><span data-stu-id="a94d0-146">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="a94d0-147">これで、技術者は OOBE をフォロー出来るようになったので、完了後、設定アプリを開いて、デバイスの MAC アドレスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="a94d0-147">The technician can now follow OOBE, and when complete, open the Settings App, and retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="a94d0-148">デバイスに [2004 年 5 月の更新](hololens-release-notes.md#windows-holographic-version-2004)前の OS ビルドがある場合は、以下の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="a94d0-148">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="a94d0-149">HoloLens デバイスの電源を入れ、デバイスを PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="a94d0-149">Turn on the HoloLens Device, and plug the device into a PC.</span></span>
2. <span data-ttu-id="a94d0-150">デバイスは、ファイル ストレージ デバイスとして PC に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a94d0-150">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="a94d0-151">プロビジョニング パッケージをデバイスにコピーします</span><span class="sxs-lookup"><span data-stu-id="a94d0-151">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="a94d0-152">イーサネット ケーブルをハブに接続します。</span><span class="sxs-lookup"><span data-stu-id="a94d0-152">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="a94d0-153">USB-C ハブを HoloLens デバイスに接続します。</span><span class="sxs-lookup"><span data-stu-id="a94d0-153">Connect USB-C hub to HoloLens device.</span></span>
6. <span data-ttu-id="a94d0-154">デバイスを装着します。</span><span class="sxs-lookup"><span data-stu-id="a94d0-154">Wear the device.</span></span>
7. <span data-ttu-id="a94d0-155">**ボリューム ダウン ボタンと電源**ボタンを押して、プロビジョニング パッケージを適用します。</span><span class="sxs-lookup"><span data-stu-id="a94d0-155">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="a94d0-156">これで、技術者は OOBE をフォロー出来るようになったので、完了後、設定アプリを開いて、デバイスの MAC アドレスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="a94d0-156">The technician can now follow OOBE, and when complete, open the Settings App, and retrieve the MAC Address of the device.</span></span>

### <span data-ttu-id="a94d0-157">メリット</span><span class="sxs-lookup"><span data-stu-id="a94d0-157">Benefits</span></span>

<span data-ttu-id="a94d0-158">これにより、デバイスの&quot;シングル タッチ&quot;で正しいプロビジョニング パッケージを適用し、デバイスの MAC アドレスを収集できます。</span><span class="sxs-lookup"><span data-stu-id="a94d0-158">This will allow a &quot;Single touch&quot; of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="a94d0-159">プロビジョニングパッケージは、こちらのガイダンスに従って作成できます。</span><span class="sxs-lookup"><span data-stu-id="a94d0-159">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <span data-ttu-id="a94d0-160">Intune Enrolment を使用した Autopilot</span><span class="sxs-lookup"><span data-stu-id="a94d0-160">Autopilot with Intune Enrolment</span></span>

### <span data-ttu-id="a94d0-161">要件</span><span class="sxs-lookup"><span data-stu-id="a94d0-161">Requirements</span></span>

- <span data-ttu-id="a94d0-162">カスタマー ネットワークにアクセスできる有線ネットワーク ポート</span><span class="sxs-lookup"><span data-stu-id="a94d0-162">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="a94d0-163">Windows Holographic 2004 を実行している HoloLens デバイス</span><span class="sxs-lookup"><span data-stu-id="a94d0-163">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="a94d0-164">HoloLens Compatible USB-C Hub</span><span class="sxs-lookup"><span data-stu-id="a94d0-164">HoloLens Compatible USB-C Hub</span></span>
- <span data-ttu-id="a94d0-165">Intuneがセットアップされ、顧客のテナントに対して有効です</span><span class="sxs-lookup"><span data-stu-id="a94d0-165">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="a94d0-166">Autopilot に登録され、顧客のテナントにインポートされたデバイス</span><span class="sxs-lookup"><span data-stu-id="a94d0-166">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="a94d0-167">デバイスに定義されている Intune ポリシー</span><span class="sxs-lookup"><span data-stu-id="a94d0-167">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="a94d0-168">ワイヤレス ネットワーク情報と証明書が含まれている</span><span class="sxs-lookup"><span data-stu-id="a94d0-168">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="a94d0-169">その他の必要なプロビジョニング設定が含まれている</span><span class="sxs-lookup"><span data-stu-id="a94d0-169">Containing any other required provisioning settings</span></span>

<span data-ttu-id="a94d0-170">これにより、高度なネットワーク要件を持つお客様は、ハンズオフでスケーラブルなアプローチでデバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="a94d0-170">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="a94d0-171">必要な追加の前提条件は、次の通りです。</span><span class="sxs-lookup"><span data-stu-id="a94d0-171">Additional pre-requisites will be needed as below:</span></span>
1. [<span data-ttu-id="a94d0-172">Autopilot プレビューのテナントを有効にする</span><span class="sxs-lookup"><span data-stu-id="a94d0-172">Enable the Tenant for the Autopilot preview</span></span>](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. <span data-ttu-id="a94d0-173">HoloLens ポリシーを作成して、Intune 内のプロビジョニング パッケージを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a94d0-173">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="a94d0-174">HoloLens Intune ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a94d0-174">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="a94d0-175">デバイスを正しいグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a94d0-175">Assign the devices to the correct group.</span></span>

### <span data-ttu-id="a94d0-176">Process</span><span class="sxs-lookup"><span data-stu-id="a94d0-176">Process</span></span>

1. <span data-ttu-id="a94d0-177">USB-C ハブとイーサネット ケーブルを HoloLens 2 デバイスに接続します。</span><span class="sxs-lookup"><span data-stu-id="a94d0-177">Plug the USB-C hub and ethernet cable into the HoloLens 2 device.</span></span>
2. <span data-ttu-id="a94d0-178">HoloLens 2 を有効にします。</span><span class="sxs-lookup"><span data-stu-id="a94d0-178">Turn on the HoloLens 2.</span></span>
3. <span data-ttu-id="a94d0-179">デバイスは、イーサネットアダプターを介して OOBE でインターネットに自動的に接続し、自動操縦構成を検出し、AzureAD と Intune に自動的に登録する必要があります</span><span class="sxs-lookup"><span data-stu-id="a94d0-179">The device should automatically connect to the internet at OOBE via the Ethernet adaptor, detect the Autopilot configuration, and automatically register with Azure AD and Intune</span></span>
4. <span data-ttu-id="a94d0-180">デバイスは、必要に応じて Intune を介して必要な Wi-Fi 証明書とその他の構成を適用します</span><span class="sxs-lookup"><span data-stu-id="a94d0-180">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune</span></span>
5. <span data-ttu-id="a94d0-181">完了すると、技術者は Intune (エンドポイント マネージャー) ポータルをロードし、**[ホーム]-> [デバイス] -> [デバイス名] -> [ハードウェア]** にある デバイス プロパティ ページを表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a94d0-181">When complete, the technician will be able to load the Intune (Endpoint Manager) Portal, and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**</span></span>
6. <span data-ttu-id="a94d0-182">Wif iMAC アドレスは Intune ポータル内に表示されます</span><span class="sxs-lookup"><span data-stu-id="a94d0-182">The Wifi MAC address will be visible within the Intune Portal</span></span>

![Intune 経由の MAC アドレス](images/mac-address-intune.jpg)

7. <span data-ttu-id="a94d0-184">技術者は、この MAC アドレスを許可されたデバイスとして追加します。</span><span class="sxs-lookup"><span data-stu-id="a94d0-184">The technician will add this MAC address as an allowed device.</span></span>

### <span data-ttu-id="a94d0-185">メリット</span><span class="sxs-lookup"><span data-stu-id="a94d0-185">Benefits</span></span>

<span data-ttu-id="a94d0-186">これにより、技術者がデバイスを装着したり、HoloLens 環境を手動で操作したりしなくても、デバイスをボックスから AAD および Intune に登録できるため、技術者は&quot;ヘッドオフ&quot;展開を体験できます。</span><span class="sxs-lookup"><span data-stu-id="a94d0-186">This will allow a &quot;Heads off&quot; deployment experience for the Technician, with the device being able to go from the box to enrolled in AAD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <span data-ttu-id="a94d0-187">技術者への MAC アドレスの報告</span><span class="sxs-lookup"><span data-stu-id="a94d0-187">Reporting of MAC addresses to the Technician</span></span>

### <span data-ttu-id="a94d0-188">要件</span><span class="sxs-lookup"><span data-stu-id="a94d0-188">Requirements</span></span>

- <span data-ttu-id="a94d0-189">顧客テナントに対する &quot;Intune Graph Powershell&quot; の承認</span><span class="sxs-lookup"><span data-stu-id="a94d0-189">Authorisation of the &quot;Intune Graph Powershell&quot; against the customer Tenant</span></span>
- <span data-ttu-id="a94d0-190">技術者のコンピューターへの Intune Graph Powershell のインストール。</span><span class="sxs-lookup"><span data-stu-id="a94d0-190">Installation of the Intune Graph Powershell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="a94d0-191">Intune の &quot;管理対象デバイス&quot; 要素への読み取りアクセス。</span><span class="sxs-lookup"><span data-stu-id="a94d0-191">Read access to the &quot;Managed Devices&quot; elements of Intune.</span></span> <span data-ttu-id="a94d0-192">(ヘルプデスクオペレーター以上、またはカスタムロール)</span><span class="sxs-lookup"><span data-stu-id="a94d0-192">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="a94d0-193">現時点では、Intune内の新しいデバイスの登録に基づいて自動化コマンドをトリガーする&quot;簡単な&quot;方法はありません。</span><span class="sxs-lookup"><span data-stu-id="a94d0-193">At present, there is no &quot;simple&quot; way to trigger an automation command based on the enrolment of a new device within Intune.</span></span> <span data-ttu-id="a94d0-194">したがって、このコマンドは、ポータルにログオンして手動で取得する必要なしに、技術者に MAC アドレスを取得する簡単な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="a94d0-194">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="a94d0-195">これにより、過去30日間に登録された HoloLens デバイスの名前と MAC アドレスが返されます。</span><span class="sxs-lookup"><span data-stu-id="a94d0-195">This will return the name and MAC address of any HoloLens devices which have been enrolled in the last 30 days.</span></span>

![Powershell 経由の MAC アドレス](images/mac-address-powershell.jpg)

### <span data-ttu-id="a94d0-197">Process</span><span class="sxs-lookup"><span data-stu-id="a94d0-197">Process</span></span>

<span data-ttu-id="a94d0-198">Intune の登録が完了すると、技術者は上記のスクリプトを実行して MAC アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="a94d0-198">After the Intune enrolment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
