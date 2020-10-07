---
title: Enroll HoloLens in MDM
description: Enroll HoloLens in mobile device management (MDM) for easier management of multiple devices.
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
ms.openlocfilehash: 5adc1b48c4603f3a9d3145bef4f1d8aa1867a9d1
ms.sourcegitcommit: 5877c3e51de49f949b35ab840a3312a009a4487a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "11102326"
---
# <span data-ttu-id="bfc0e-103">Enroll HoloLens in MDM</span><span class="sxs-lookup"><span data-stu-id="bfc0e-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="bfc0e-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span><span class="sxs-lookup"><span data-stu-id="bfc0e-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="bfc0e-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span><span class="sxs-lookup"><span data-stu-id="bfc0e-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="bfc0e-106">「[Microsoft Intune を使用して Windows Holographic を実行するデバイスを管理する](https://docs.microsoft.com/intune/windows-holographic-for-business)」、[Windows Holographic でサポートされている構成サービス プロバイダー (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) と [Windows Holographic for Business でサポートされているポリシー](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfc0e-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="bfc0e-107">VPN、Bitlocker、キオスク モードの機能を含むモバイル デバイス管理 (MDM) は、[Windows Holographic for Business にアップグレード](hololens1-upgrade-enterprise.md)した場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="bfc0e-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="bfc0e-108">Requirements</span><span class="sxs-lookup"><span data-stu-id="bfc0e-108">Requirements</span></span>

 <span data-ttu-id="bfc0e-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span><span class="sxs-lookup"><span data-stu-id="bfc0e-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="bfc0e-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span><span class="sxs-lookup"><span data-stu-id="bfc0e-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <span data-ttu-id="bfc0e-111">Different ways to enroll</span><span class="sxs-lookup"><span data-stu-id="bfc0e-111">Different ways to enroll</span></span>

<span data-ttu-id="bfc0e-112">Depending on the type of identity chosen either during OOBE or post sign-in there are different methods of enrollment.</span><span class="sxs-lookup"><span data-stu-id="bfc0e-112">Depending on the type of identity chosen either during OOBE or post sign-in there are different methods of enrollment.</span></span> <span data-ttu-id="bfc0e-113">To learn more about each type of Identity on HoloLens please visit [this page](hololens-identity.md).</span><span class="sxs-lookup"><span data-stu-id="bfc0e-113">To learn more about each type of Identity on HoloLens please visit [this page](hololens-identity.md).</span></span>

- <span data-ttu-id="bfc0e-114">If Identity is AAD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span><span class="sxs-lookup"><span data-stu-id="bfc0e-114">If Identity is AAD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="bfc0e-115">For AAD, automatic MDM enrollment only occurs if AAD has been configured with enrollment URLs.</span><span class="sxs-lookup"><span data-stu-id="bfc0e-115">For AAD, automatic MDM enrollment only occurs if AAD has been configured with enrollment URLs.</span></span>
- <span data-ttu-id="bfc0e-116">If Identity is AAD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then AAD-Join and enrollment will automatically occur during OOBE.</span><span class="sxs-lookup"><span data-stu-id="bfc0e-116">If Identity is AAD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then AAD-Join and enrollment will automatically occur during OOBE.</span></span>
    - <span data-ttu-id="bfc0e-117">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span><span class="sxs-lookup"><span data-stu-id="bfc0e-117">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
- <span data-ttu-id="bfc0e-118">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span><span class="sxs-lookup"><span data-stu-id="bfc0e-118">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="bfc0e-119">Also called Add Work Account (AWA) flow.</span><span class="sxs-lookup"><span data-stu-id="bfc0e-119">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="bfc0e-120">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span><span class="sxs-lookup"><span data-stu-id="bfc0e-120">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="bfc0e-121">Also called pure MDM enrollment flow.</span><span class="sxs-lookup"><span data-stu-id="bfc0e-121">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="bfc0e-122">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span><span class="sxs-lookup"><span data-stu-id="bfc0e-122">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="bfc0e-123">Auto-enrollment in MDM</span><span class="sxs-lookup"><span data-stu-id="bfc0e-123">Auto-enrollment in MDM</span></span>

<span data-ttu-id="bfc0e-124">Azure Active Directory (Azure AD) と、認証用の AAD トークンを受け入れる MDM ソリューション (現在のところ、Microsoft Intune と AirWatch でのみサポートされている場合) を組織で使っている場合、IT 管理者はユーザーが Azure AD アカウントにサインインした後 MDM 登録が自動的に行われるように Azure AD を構成できます。</span><span class="sxs-lookup"><span data-stu-id="bfc0e-124">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an AAD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="bfc0e-125">Azure AD の登録を構成する方法をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bfc0e-125">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="bfc0e-126">自動登録が有効な場合、追加の手動登録は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bfc0e-126">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="bfc0e-127">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span><span class="sxs-lookup"><span data-stu-id="bfc0e-127">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="bfc0e-128">When a device is AAD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span><span class="sxs-lookup"><span data-stu-id="bfc0e-128">When a device is AAD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <span data-ttu-id="bfc0e-129">Unenroll HoloLens from Intune</span><span class="sxs-lookup"><span data-stu-id="bfc0e-129">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="bfc0e-130">To learn more about unenrolling a device visit [this page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span><span class="sxs-lookup"><span data-stu-id="bfc0e-130">To learn more about unenrolling a device visit [this page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span></span> 
