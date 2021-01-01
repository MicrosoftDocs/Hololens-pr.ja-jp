---
title: MDM での HoloLens の登録
description: 複数のデバイスを管理しやすいように、モバイル デバイス管理 (MDM) に HoloLens を登録します。
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
ms.openlocfilehash: 7c17cbf88fc2e7a6dcd9aa600ad6e6910edb29a8
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253234"
---
# <span data-ttu-id="87d9a-103">MDM での HoloLens の登録</span><span class="sxs-lookup"><span data-stu-id="87d9a-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="87d9a-104">Microsoft Intune のようなソリューションを使用して、複数の Microsoft HoloLens デバイスを同時 [に管理できます](https://docs.microsoft.com/intune/windows-holographic-for-business)。</span><span class="sxs-lookup"><span data-stu-id="87d9a-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="87d9a-105">設定の管理、インストールするアプリの選択、組織のニーズに合わせたセキュリティ構成の設定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="87d9a-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="87d9a-106">「[Microsoft Intune を使用して Windows Holographic を実行するデバイスを管理する](https://docs.microsoft.com/intune/windows-holographic-for-business)」、[Windows Holographic でサポートされている構成サービス プロバイダー (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) と [Windows Holographic for Business でサポートされているポリシー](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="87d9a-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="87d9a-107">VPN、Bitlocker、キオスク モードの機能を含むモバイル デバイス管理 (MDM) は、[Windows Holographic for Business にアップグレード](hololens1-upgrade-enterprise.md)した場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="87d9a-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="87d9a-108">要件</span><span class="sxs-lookup"><span data-stu-id="87d9a-108">Requirements</span></span>

 <span data-ttu-id="87d9a-109">HoloLens デバイスを管理するには、組織でモバイル デバイス管理 (MDM) をセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="87d9a-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="87d9a-110">MDM プロバイダーには、Microsoft Intune や、Microsoft MDM API を使うサード パーティ プロバイダーを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="87d9a-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <span data-ttu-id="87d9a-111">さまざまな登録方法</span><span class="sxs-lookup"><span data-stu-id="87d9a-111">Different ways to enroll</span></span>

<span data-ttu-id="87d9a-112">OOBE またはサインイン後に選択される ID の種類に応じて、登録方法が異なります。</span><span class="sxs-lookup"><span data-stu-id="87d9a-112">Depending on the type of identity chosen either during OOBE or post sign-in there are different methods of enrollment.</span></span> <span data-ttu-id="87d9a-113">HoloLens の ID の各種類の詳細については、このページを [参照してください](hololens-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="87d9a-113">To learn more about each type of Identity on HoloLens please visit [this page](hololens-identity.md).</span></span>

- <span data-ttu-id="87d9a-114">Identity が Azure ADの場合は、OOBE または**設定**アプリアクセスの [仕事用または学校用接続]  ->  **ボタンのいずれかの操作を**  ->  **行**います。</span><span class="sxs-lookup"><span data-stu-id="87d9a-114">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="87d9a-115">Azure ADの場合、MDM の自動登録は、Azure AD URL で構成されている場合にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="87d9a-115">For Azure AD, automatic MDM enrollment only occurs if Azure AD has been configured with enrollment URLs.</span></span>
- <span data-ttu-id="87d9a-116">Identity が Azure AD であり、特定の構成プロファイルが割り当てられた Intune MDM サーバーにデバイスが事前登録されている場合、Azure AD-Join と登録は OOBE 中に自動的に行われます。</span><span class="sxs-lookup"><span data-stu-id="87d9a-116">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and enrollment will automatically occur during OOBE.</span></span>
    - <span data-ttu-id="87d9a-117">[19041.1103+](hololens-release-notes.md#windows-holographic-version-2004)ビルドで利用可能な[Autopilot](hololens2-autopilot.md)フローとも呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="87d9a-117">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
- <span data-ttu-id="87d9a-118">IDENTITY が MSA の場合は、[設定]**アプリ**アクセスの [仕事用] ボタンまたは [学校接続]  ->  **ボタン**  ->  **を使用**します。</span><span class="sxs-lookup"><span data-stu-id="87d9a-118">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="87d9a-119">作業アカウントの追加 (AWA) フローとも呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="87d9a-119">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="87d9a-120">IDENTITY がローカル ユーザーの場合は、[設定]**アプリ**アクセスの [仕事または学校の登録] をデバイス  ->  \*\*\*\*  ->  **管理リンクでのみ使用**します。</span><span class="sxs-lookup"><span data-stu-id="87d9a-120">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="87d9a-121">純粋な MDM 登録フローとも呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="87d9a-121">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="87d9a-122">デバイスが MDM サーバーに登録された後、設定アプリには、デバイスがデバイス管理に登録されたと反映されます。</span><span class="sxs-lookup"><span data-stu-id="87d9a-122">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="87d9a-123">MDM への自動登録</span><span class="sxs-lookup"><span data-stu-id="87d9a-123">Auto-enrollment in MDM</span></span>

<span data-ttu-id="87d9a-124">組織で Azure Active Directory (Azure AD) と認証用に Azure AD トークンを受け入れる MDM ソリューションを使用している場合 (現在、Microsoft Intune と AirWatch でのみサポートされています)、IT 管理者は、ユーザーが Azure AD アカウントでサインインした後に MDM 登録を自動的に許可するように Azure AD を構成できます。</span><span class="sxs-lookup"><span data-stu-id="87d9a-124">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="87d9a-125">Azure AD の登録を構成する方法をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="87d9a-125">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="87d9a-126">自動登録が有効な場合、追加の手動登録は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="87d9a-126">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="87d9a-127">ユーザーが Azure AD アカウントでサインインすると、最初の実行エクスペリエンスを完了した後デバイスが MDM に登録されます。</span><span class="sxs-lookup"><span data-stu-id="87d9a-127">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="87d9a-128">デバイスが Azure デバイスに参加AD、デバイスの所有者と見なされたユーザーに [影響を与える可能性があります](security-adminless-os.md#device-owner)。</span><span class="sxs-lookup"><span data-stu-id="87d9a-128">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <span data-ttu-id="87d9a-129">Intune から HoloLens を登録解除する</span><span class="sxs-lookup"><span data-stu-id="87d9a-129">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="87d9a-130">デバイスの登録解除の詳細については、このページ [を参照してください](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment)。</span><span class="sxs-lookup"><span data-stu-id="87d9a-130">To learn more about unenrolling a device visit [this page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span></span> 
