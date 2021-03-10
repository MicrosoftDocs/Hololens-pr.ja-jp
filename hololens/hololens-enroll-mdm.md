---
title: MDM での HoloLens の登録
description: 複数のデバイスを簡単に管理するために、HoloLens をモバイル デバイス管理 (MDM) に登録する方法について説明します。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4042cce40bea2c3d52d6ffc5d2908f6fde7cf222
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400677"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="72461-103">MDM での HoloLens の登録</span><span class="sxs-lookup"><span data-stu-id="72461-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="72461-104">Microsoft Intune のようなソリューションを使用して、複数の Microsoft HoloLens デバイスを同時 [に管理できます](https://docs.microsoft.com/intune/windows-holographic-for-business)。</span><span class="sxs-lookup"><span data-stu-id="72461-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="72461-105">設定の管理、インストールするアプリの選択、組織のニーズに合わせたセキュリティ構成の設定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="72461-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="72461-106">「[Microsoft Intune を使用して Windows Holographic を実行するデバイスを管理する](https://docs.microsoft.com/intune/windows-holographic-for-business)」、[Windows Holographic でサポートされている構成サービス プロバイダー (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) と [Windows Holographic for Business でサポートされているポリシー](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="72461-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="72461-107">VPN、Bitlocker、キオスク モードの機能を含むモバイル デバイス管理 (MDM) は、[Windows Holographic for Business にアップグレード](hololens1-upgrade-enterprise.md)した場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="72461-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="72461-108">要件</span><span class="sxs-lookup"><span data-stu-id="72461-108">Requirements</span></span>

 <span data-ttu-id="72461-109">HoloLens デバイスを管理するには、組織でモバイル デバイス管理 (MDM) を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72461-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="72461-110">MDM プロバイダーには、Microsoft Intune や、Microsoft MDM API を使うサード パーティ プロバイダーを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="72461-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="72461-111">さまざまな登録方法</span><span class="sxs-lookup"><span data-stu-id="72461-111">Different ways to enroll</span></span>

<span data-ttu-id="72461-112">OOBE またはサインイン後に選択された [ID](hololens-identity.md) の種類に応じて、登録方法は異なります。</span><span class="sxs-lookup"><span data-stu-id="72461-112">Depending on the type of [identity](hololens-identity.md) chosen either during OOBE or post sign-in, there are different methods of enrollment.</span></span>

- <span data-ttu-id="72461-113">Identity が Azure AD場合は、OOBE または **[** 設定] アプリ アクセス作業時間または学校接続  ->  \*\*\*\*  ->  ボタン**のどちらか**です。</span><span class="sxs-lookup"><span data-stu-id="72461-113">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="72461-114">Azure AD、 [自動 MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 登録は、Azure サーバーが登録 URL AD構成されている場合にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="72461-114">For Azure AD, [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) only occurs if Azure AD has been configured with enrollment URLs.</span></span> 
     
- <span data-ttu-id="72461-115">Identity が Azure AD であり、デバイスが特定の構成プロファイルが割り当てられた Intune MDM サーバーに事前登録されている場合、Azure AD-Join および [自動 MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 登録は OOBE 中に行われます。</span><span class="sxs-lookup"><span data-stu-id="72461-115">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) will occur during OOBE.</span></span>
    - <span data-ttu-id="72461-116">また [、Autopilot flow Available in](hololens2-autopilot.md) [19041.1103+ ビルドとも呼ばれる](hololens-release-notes.md#windows-holographic-version-2004)。</span><span class="sxs-lookup"><span data-stu-id="72461-116">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
    

- <span data-ttu-id="72461-117">Identity が MSA の場合は、[設定]**アプリ**アクセス作業時間または学校  ->  **接続ボタン**  ->  **を使用**します。</span><span class="sxs-lookup"><span data-stu-id="72461-117">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="72461-118">作業アカウントの追加 (AWA) フローとも呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="72461-118">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="72461-119">Id がローカル ユーザーの場合は、[設定]**アプリ**アクセス作業時間または学校登録のみをデバイス管理  ->  \*\*\*\*  ->  **リンクで使用**します。</span><span class="sxs-lookup"><span data-stu-id="72461-119">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="72461-120">純粋な MDM 登録フローとも呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="72461-120">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="72461-121">デバイスが MDM サーバーに登録された後、設定アプリはデバイスがデバイス管理に登録されたと反映されます。</span><span class="sxs-lookup"><span data-stu-id="72461-121">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="72461-122">MDM への自動登録</span><span class="sxs-lookup"><span data-stu-id="72461-122">Auto-enrollment in MDM</span></span>

<span data-ttu-id="72461-123">組織に Azure [](https://azure.microsoft.com/overview/)Premium サブスクリプションがある場合は、Azure Active Directory (Azure AD) と認証用の Azure AD トークンを受け入れる MDM ソリューション (現在は Microsoft Intune と AirWatch でのみサポート) を使用している場合、IT 管理者は、ユーザーが Azure AD アカウントでサインインした後に MDM 登録を自動的に許可するように Azure AD を構成できます。</span><span class="sxs-lookup"><span data-stu-id="72461-123">If your organization has an [Azure Premium subscription](https://azure.microsoft.com/overview/), is using Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="72461-124">Azure AD の登録を構成する方法をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="72461-124">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="72461-125">自動登録が有効な場合、追加の手動登録は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="72461-125">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="72461-126">ユーザーが Azure AD アカウントでサインインすると、最初の実行エクスペリエンスを完了した後デバイスが MDM に登録されます。</span><span class="sxs-lookup"><span data-stu-id="72461-126">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="72461-127">デバイスが Azure デバイスの場合AD参加している場合、デバイスの所有者と見なされるユーザーに [影響を与える可能性があります](security-adminless-os.md#device-owner)。</span><span class="sxs-lookup"><span data-stu-id="72461-127">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="72461-128">Intune から HoloLens の登録を解除する</span><span class="sxs-lookup"><span data-stu-id="72461-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="72461-129">HoloLens 2 は Windows 10 デバイスですが、Intune から単に登録解除することはできません。</span><span class="sxs-lookup"><span data-stu-id="72461-129">Although HoloLens 2 is Windows 10 device, it cannot be simply unenrolled from Intune.</span></span> <span data-ttu-id="72461-130">Azure AD から HoloLens の接続を解除するか、Azure AD テナントとは別のテナントに再び追加する場合は、デバイスをリセット [または再](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) フラッシュする必要があります。</span><span class="sxs-lookup"><span data-stu-id="72461-130">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) the device.</span></span>