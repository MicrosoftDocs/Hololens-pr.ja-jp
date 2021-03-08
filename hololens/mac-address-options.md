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
ms.openlocfilehash: fe365248332f8e78b15ab362f169b84e48dfe594
ms.sourcegitcommit: 07ffe1bf2f45dcb2ba9d7fbe54b4773a0fb9d525
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393841"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a><span data-ttu-id="1f109-103">MAC アドレスが制限された Wi-Fi 環境での HoloLens デバイスのエンタープライズ登録</span><span class="sxs-lookup"><span data-stu-id="1f109-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="1f109-104">このドキュメントでは、Wi-Fi が MAC アドレスのために制限されている、またはワイヤレス ネットワークに参加するために証明書が必要な、お客様の環境内で特定された一般的なシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1f109-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="1f109-105">シナリオ例</span><span class="sxs-lookup"><span data-stu-id="1f109-105">Example Scenario</span></span>

<span data-ttu-id="1f109-106">セキュリティで保護された環境では、多くの場合ワイヤレスまたは有線のネットワークに制限が設定されており、接続が許可されるのは (MAC アドレスに基づき) 承認されたデバイスのみとなっています。</span><span class="sxs-lookup"><span data-stu-id="1f109-106">Many customers in secure environments have restrictions on their Wireless or wired networks which will only allow approved devices (based on MAC Addresses) to connect successfully.</span></span> <span data-ttu-id="1f109-107">このような制限は、ワイヤレス アクセス ポイント上の MAC アドレス フィルターまたは DHCP サーバーを介して適用されます。</span><span class="sxs-lookup"><span data-stu-id="1f109-107">This may be enforced through MAC Address filtering on a Wireless Access Point or through a DHCP server.</span></span> <span data-ttu-id="1f109-108">また、一部のワイヤレス ネットワークは PEAP を用いて保護することもできます。この方式では、ワイヤレス ネットワークで認証する前にデバイスに証明書を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f109-108">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to authenticating on the Wireless network.</span></span>

<span data-ttu-id="1f109-109">このシナリオでは、以下の 2 つの主要な要件が原因となり、HoloLens デバイスをネットワークに参加させる際に遅延が発生したり、手動による介入が必要になったりする場合があります。</span><span class="sxs-lookup"><span data-stu-id="1f109-109">In this scenario, two key requirements may introduce delays or require manual intervention when joining HoloLens devices to the network:</span></span>

- <span data-ttu-id="1f109-110">デバイスをワイヤレス ネットワークに正常に参加させるには、その前にワイヤレス PEAP 証明書をデバイスに適用する必要がある。</span><span class="sxs-lookup"><span data-stu-id="1f109-110">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="1f109-111">HoloLens Wi-Fi アダプターの MAC アドレスは登録済みである必要がある。</span><span class="sxs-lookup"><span data-stu-id="1f109-111">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="1f109-112">上記の要件に関する主な課題は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1f109-112">The core challenges with the requirements above are:</span></span>

1. <span data-ttu-id="1f109-113">現在、MAC アドレスは、デバイスの設定アプリから、または登録の完了後に Intune からのみ確認できます。</span><span class="sxs-lookup"><span data-stu-id="1f109-113">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful enrollment.</span></span>
2. <span data-ttu-id="1f109-114">MACアドレスがない場合、デバイスは Wi-Fi ネットワークに参加して登録手続きを開始できません。</span><span class="sxs-lookup"><span data-stu-id="1f109-114">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>
3. <span data-ttu-id="1f109-115">これらの課題を手動で回避するには、技術者がデバイスを操作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f109-115">Manual workarounds to these challenges require a technician to interact with the device.</span></span>

## <a name="solutions"></a><span data-ttu-id="1f109-116">解決策</span><span class="sxs-lookup"><span data-stu-id="1f109-116">Solutions</span></span>

<span data-ttu-id="1f109-117">環境内で使用可能なインフラストラクチャに応じて、この状況を改善する方法は多数あります。</span><span class="sxs-lookup"><span data-stu-id="1f109-117">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="1f109-118">解決策</span><span class="sxs-lookup"><span data-stu-id="1f109-118">Solution</span></span> | <span data-ttu-id="1f109-119">メリット</span><span class="sxs-lookup"><span data-stu-id="1f109-119">Benefits</span></span> | <span data-ttu-id="1f109-120">要件</span><span class="sxs-lookup"><span data-stu-id="1f109-120">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="1f109-121">イーサネット アダプターを使用したプロビジョニング パッケージ</span><span class="sxs-lookup"><span data-stu-id="1f109-121">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="1f109-122">OOBE エクスペリエンスを向上させ、より迅速な技術者エクスペリエンスを可能にします。</span><span class="sxs-lookup"><span data-stu-id="1f109-122">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="1f109-123">HoloLens 互換の USB-C ハブ + イーサネット アダプター。技術者は、MAC キャプチャと OOBE の終了処理のためにデバイスを操作する必要があります</span><span class="sxs-lookup"><span data-stu-id="1f109-123">HoloLens compatible USB-C Hub + Ethernet adaptor, and technician will still need to interact with the device for MAC capture and OOBE finalisation</span></span> |
| <span data-ttu-id="1f109-124">イーサネット経由の Intune 登録による Autopilot</span><span class="sxs-lookup"><span data-stu-id="1f109-124">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="1f109-125">この解決策では、1 回の手順でデバイスを顧客環境に接続および登録できます。</span><span class="sxs-lookup"><span data-stu-id="1f109-125">This is a single step connection and registration of the device to the customer environment.</span></span> <span data-ttu-id="1f109-126">MAC キャプチャは、デバイスの操作を必要とすることなく完了できます。</span><span class="sxs-lookup"><span data-stu-id="1f109-126">MAC capture can be completed without needing to interact with the device</span></span> | <span data-ttu-id="1f109-127">顧客の AAD テナントに対して有効になっている Intune および HoloLens 互換の USB-C イーサネット アダプター。</span><span class="sxs-lookup"><span data-stu-id="1f109-127">Intune enabled for the customer AAD tenant and a HoloLens compatible USB-C Ethernet adaptor</span></span> |
| <span data-ttu-id="1f109-128">MAC アドレスの自動レポート</span><span class="sxs-lookup"><span data-stu-id="1f109-128">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="1f109-129">デバイスが Intune テナントに登録されている場合、スクリプトを使用して MAC アドレスを技術者に報告することができます。</span><span class="sxs-lookup"><span data-stu-id="1f109-129">When devices are registered with the Intune tenant, a script can report the MAC address to the technician.</span></span> | <span data-ttu-id="1f109-130">Intune PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="1f109-130">Intune Powershell Commandlets</span></span> |

## <a name="provisioning-package-with-ethernet-adaptor"></a><span data-ttu-id="1f109-131">イーサネット アダプターを使用したプロビジョニング パッケージ</span><span class="sxs-lookup"><span data-stu-id="1f109-131">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="1f109-132">有線ネットワークに対しても MAC 制限が適用されている場合は、USB-C ハブ + イーサネット アダプターの MAC アドレスも事前承認を受ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f109-132">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Hub + Ethernet adaptor will also need to be pre-approved.</span></span> <span data-ttu-id="1f109-133">このアダプターを介して他のデバイスがネットワークにアクセスできるようになるため、このアダプターを使用する場合は注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="1f109-133">Care should be taken with this adapter as it will allow access to the network from other devices.</span></span>

### <a name="requirements"></a><span data-ttu-id="1f109-134">要件</span><span class="sxs-lookup"><span data-stu-id="1f109-134">Requirements</span></span>

- <span data-ttu-id="1f109-135">顧客のネットワークにアクセスできる有線ネットワーク ポート</span><span class="sxs-lookup"><span data-stu-id="1f109-135">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="1f109-136">HoloLens 互換のイーサネット アダプター付き USB-C ハブ。追加のドライバーやアプリケーションのインストールを必要としないアダプターが適しています。</span><span class="sxs-lookup"><span data-stu-id="1f109-136">HoloLens Compatible USB-C Hub with Ethernet adaptor – Any adapter that doesn&#39;t require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="1f109-137">以下を含むプロビジョニング パッケージ：</span><span class="sxs-lookup"><span data-stu-id="1f109-137">Provisioning Package containing:</span></span>
  - <span data-ttu-id="1f109-138">ワイヤレス ネットワーク情報と証明書が含まれている</span><span class="sxs-lookup"><span data-stu-id="1f109-138">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="1f109-139">オプションで、組織の &#39;s Azure AD の登録情報が含まれている</span><span class="sxs-lookup"><span data-stu-id="1f109-139">Optionally containing enrollment information for the Organization&#39;s Azure AD</span></span>
  - <span data-ttu-id="1f109-140">その他の必要なプロビジョニング設定が含まれている</span><span class="sxs-lookup"><span data-stu-id="1f109-140">Containing any other required provisioning settings</span></span>

### <a name="process"></a><span data-ttu-id="1f109-141">Process</span><span class="sxs-lookup"><span data-stu-id="1f109-141">Process</span></span>

<span data-ttu-id="1f109-142">このプロセスは、デバイスのソフトウェア レベルによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1f109-142">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="1f109-143">デバイスに [2004 年 5 月](hololens-release-notes.md#windows-holographic-version-2004)の更新がある場合は、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1f109-143">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="1f109-144">プロビジョニング パッケージを USB スティックのルートに配置し、ハブに接続します。</span><span class="sxs-lookup"><span data-stu-id="1f109-144">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="1f109-145">イーサネット ケーブルをハブ + イーサネット アダプターに接続します。</span><span class="sxs-lookup"><span data-stu-id="1f109-145">Connect Ethernet cable to the Hub + Ethernet adapter.</span></span>
3. <span data-ttu-id="1f109-146">USB-C ハブを HoloLens デバイスに接続します。</span><span class="sxs-lookup"><span data-stu-id="1f109-146">Connect USB-C Hub to HoloLens device.</span></span>
4. <span data-ttu-id="1f109-147">HoloLens をオンにし、デバイスを装着します。</span><span class="sxs-lookup"><span data-stu-id="1f109-147">Turn on the HoloLens and put on the device.</span></span>
5. <span data-ttu-id="1f109-148">**ボリューム ダウン ボタンと電源ボタン**を押して、プロビジョニング パッケージを適用します。</span><span class="sxs-lookup"><span data-stu-id="1f109-148">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="1f109-149">これで、技術者は OOBE の手順を実行できるようになりました。手順を完了したら、設定アプリを開いてデバイスの MAC アドレスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="1f109-149">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="1f109-150">デバイスに [May 2004 Update](hololens-release-notes.md#windows-holographic-version-2004) より前の OS ビルドがインストールされている場合は、以下の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="1f109-150">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="1f109-151">HoloLens をオンにし、デバイスを PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="1f109-151">Turn on the HoloLens and plug the device into a PC.</span></span>
2. <span data-ttu-id="1f109-152">デバイスは、ファイル ストレージ デバイスとして PC に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f109-152">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="1f109-153">プロビジョニング パッケージをデバイスにコピーします</span><span class="sxs-lookup"><span data-stu-id="1f109-153">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="1f109-154">イーサネット ケーブルをハブに接続します。</span><span class="sxs-lookup"><span data-stu-id="1f109-154">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="1f109-155">USB-C ハブを HoloLens デバイスに接続します。</span><span class="sxs-lookup"><span data-stu-id="1f109-155">Connect USB-C Hub to HoloLens device.</span></span>
6. <span data-ttu-id="1f109-156">HoloLens を装着します。</span><span class="sxs-lookup"><span data-stu-id="1f109-156">Put on the HoloLens</span></span>
7. <span data-ttu-id="1f109-157">**ボリューム ダウン ボタンと電源**ボタンを押して、プロビジョニング パッケージを適用します。</span><span class="sxs-lookup"><span data-stu-id="1f109-157">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="1f109-158">これで、技術者は OOBE の手順を実行できるようになりました。手順を完了したら、設定アプリを開いてデバイスの MAC アドレスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="1f109-158">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

### <a name="benefits"></a><span data-ttu-id="1f109-159">メリット</span><span class="sxs-lookup"><span data-stu-id="1f109-159">Benefits</span></span>

<span data-ttu-id="1f109-160">これにより、デバイスの&quot;シングル タッチ&quot;で正しいプロビジョニング パッケージを適用し、デバイスの MAC アドレスを収集できます。</span><span class="sxs-lookup"><span data-stu-id="1f109-160">This will allow a &quot;Single touch&quot; of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="1f109-161">プロビジョニングパッケージは、こちらのガイダンスに従って作成できます。</span><span class="sxs-lookup"><span data-stu-id="1f109-161">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a><span data-ttu-id="1f109-162">Intune の登録を使用した Autopilot</span><span class="sxs-lookup"><span data-stu-id="1f109-162">Autopilot with Intune Enrollment</span></span>

### <a name="requirements"></a><span data-ttu-id="1f109-163">要件</span><span class="sxs-lookup"><span data-stu-id="1f109-163">Requirements</span></span>

- <span data-ttu-id="1f109-164">カスタマー ネットワークにアクセスできる有線ネットワーク ポート</span><span class="sxs-lookup"><span data-stu-id="1f109-164">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="1f109-165">Windows Holographic 2004 を実行している HoloLens デバイス</span><span class="sxs-lookup"><span data-stu-id="1f109-165">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="1f109-166">HoloLens 互換の USB-C イーサネット アダプター</span><span class="sxs-lookup"><span data-stu-id="1f109-166">HoloLens Compatible USB-C Ethernet adapter</span></span>
- <span data-ttu-id="1f109-167">顧客のテナントに対して構成および有効に設定されている Intune。</span><span class="sxs-lookup"><span data-stu-id="1f109-167">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="1f109-168">Autopilot に登録され、顧客のテナントにインポートされたデバイス</span><span class="sxs-lookup"><span data-stu-id="1f109-168">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="1f109-169">デバイスに定義されている Intune ポリシー</span><span class="sxs-lookup"><span data-stu-id="1f109-169">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="1f109-170">ワイヤレス ネットワーク情報と証明書が含まれている</span><span class="sxs-lookup"><span data-stu-id="1f109-170">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="1f109-171">その他の必要なプロビジョニング設定が含まれている</span><span class="sxs-lookup"><span data-stu-id="1f109-171">Containing any other required provisioning settings</span></span>

<span data-ttu-id="1f109-172">これにより、高度なネットワーク要件を持つお客様は、ハンズオフでスケーラブルなアプローチでデバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="1f109-172">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="1f109-173">必要な追加の前提条件は、次の通りです。</span><span class="sxs-lookup"><span data-stu-id="1f109-173">Additional pre-requisites will be needed as below:</span></span>
1. [<span data-ttu-id="1f109-174">Autopilot プレビューのテナントを有効にする</span><span class="sxs-lookup"><span data-stu-id="1f109-174">Enable the Tenant for the Autopilot preview</span></span>](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. <span data-ttu-id="1f109-175">HoloLens ポリシーを作成して、Intune 内のプロビジョニング パッケージを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="1f109-175">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="1f109-176">HoloLens Intune ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f109-176">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="1f109-177">デバイスを正しいグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1f109-177">Assign the devices to the correct group.</span></span>

### <a name="process"></a><span data-ttu-id="1f109-178">プロセス</span><span class="sxs-lookup"><span data-stu-id="1f109-178">Process</span></span>

1. <span data-ttu-id="1f109-179">イーサネット ケーブルをアダプターに接続し、アダプターを HoloLens 2 デバイスの USB-C ポートに接続します。</span><span class="sxs-lookup"><span data-stu-id="1f109-179">Connect the ethernet cable to the adapter and plug the adapter into the USB-C port on the HoloLens 2 device.</span></span>
2. <span data-ttu-id="1f109-180">HoloLens をオンにします。</span><span class="sxs-lookup"><span data-stu-id="1f109-180">Turn on the HoloLens.</span></span>
3. <span data-ttu-id="1f109-181">OOBE 中、デバイスがイーサネット アダプターを介してインターネットに自動的に接続します。</span><span class="sxs-lookup"><span data-stu-id="1f109-181">The device should automatically connect to the internet during OOBE via the Ethernet adaptor.</span></span> <span data-ttu-id="1f109-182">Autopilot の構成が検出され、Azure AD および Intune に自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="1f109-182">It should detect the Autopilot configuration and automatically register with Azure AD and Intune</span></span>
4. <span data-ttu-id="1f109-183">デバイスは、要求される Wi-Fi 証明書および必要に応じてとその他の構成を Intune を介して適用します。</span><span class="sxs-lookup"><span data-stu-id="1f109-183">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune</span></span>
5. <span data-ttu-id="1f109-184">完了すると、技術者は Intune (エンドポイント マネージャー) ポータルを読み込み、**[ホーム] > [デバイス] > [デバイス名] > [ハードウェア]** からデバイス プロパティ ページを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="1f109-184">When complete, the technician can load the Intune (Endpoint Manager) Portal and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**</span></span>
6. <span data-ttu-id="1f109-185">Wi-Fi MAC アドレスは Intune ポータル内に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f109-185">The Wifi MAC address will be visible within the Intune Portal</span></span>

![Intune 経由の MAC アドレス](images/mac-address-intune.jpg)

7. <span data-ttu-id="1f109-187">技術者は、この MAC アドレスを許可されたデバイスとして追加します。</span><span class="sxs-lookup"><span data-stu-id="1f109-187">The technician will add this MAC address as an allowed device.</span></span>

### <a name="benefits"></a><span data-ttu-id="1f109-188">メリット</span><span class="sxs-lookup"><span data-stu-id="1f109-188">Benefits</span></span>

<span data-ttu-id="1f109-189">これにより、技術者がデバイスを装着したり、HoloLens 環境を手動で操作したりすることなく、デバイスをボックスから Azure AD および Intune に登録できる、技術者の&quot;ヘッドオフ&quot;展開エクスペリエンスが可能になります。</span><span class="sxs-lookup"><span data-stu-id="1f109-189">This will allow a &quot;Heads off&quot; deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <a name="reporting-of-mac-addresses-to-the-technician"></a><span data-ttu-id="1f109-190">技術者への MAC アドレスの報告</span><span class="sxs-lookup"><span data-stu-id="1f109-190">Reporting of MAC addresses to the Technician</span></span>

### <a name="requirements"></a><span data-ttu-id="1f109-191">要件</span><span class="sxs-lookup"><span data-stu-id="1f109-191">Requirements</span></span>

- <span data-ttu-id="1f109-192">顧客テナントに対する &quot;Intune Graph PowerShell&quot; の承認</span><span class="sxs-lookup"><span data-stu-id="1f109-192">Authorization of the &quot;Intune Graph PowerShell&quot; against the customer Tenant</span></span>
- <span data-ttu-id="1f109-193">技術者のコンピューターへの Intune Graph PowerShell のインストール。</span><span class="sxs-lookup"><span data-stu-id="1f109-193">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="1f109-194">Intune の &quot;管理対象デバイス&quot; 要素への読み取りアクセス。</span><span class="sxs-lookup"><span data-stu-id="1f109-194">Read access to the &quot;Managed Devices&quot; elements of Intune.</span></span> <span data-ttu-id="1f109-195">(ヘルプデスクオペレーター以上、またはカスタムロール)</span><span class="sxs-lookup"><span data-stu-id="1f109-195">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="1f109-196">現時点では、Intune内の新しいデバイスの登録に基づいて自動化コマンドをトリガーする&quot;簡単な&quot;方法はありません。</span><span class="sxs-lookup"><span data-stu-id="1f109-196">At present, there is no &quot;simple&quot; way to trigger an automation command based on the enrolment of a new device within Intune.</span></span> <span data-ttu-id="1f109-197">したがって、このコマンドは、ポータルにログオンして手動で取得する必要なしに、技術者に MAC アドレスを取得する簡単な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="1f109-197">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="1f109-198">これにより、過去30日間に登録された HoloLens デバイスの名前と MAC アドレスが返されます。</span><span class="sxs-lookup"><span data-stu-id="1f109-198">This will return the name and MAC address of any HoloLens devices which have been enrolled in the last 30 days.</span></span>

![Powershell 経由の MAC アドレス](images/mac-address-powershell.jpg)

### <a name="process"></a><span data-ttu-id="1f109-200">Process</span><span class="sxs-lookup"><span data-stu-id="1f109-200">Process</span></span>

<span data-ttu-id="1f109-201">Intune の登録が完了すると、技術者は上記のスクリプトを実行して MAC アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="1f109-201">After the Intune enrolment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
