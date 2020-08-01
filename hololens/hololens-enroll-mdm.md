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
ms.date: 07/15/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 1dd6c2e6cde980b86ac810f82d27b3b88f20f336
ms.sourcegitcommit: 7edbb99e0972d3d857e5e87c062c3c64cacc1f41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2020
ms.locfileid: "10903223"
---
# <span data-ttu-id="2193b-103">MDM での HoloLens の登録</span><span class="sxs-lookup"><span data-stu-id="2193b-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="2193b-104">[Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)などのソリューションを使用して、複数の microsoft HoloLens デバイスを同時に管理できます。</span><span class="sxs-lookup"><span data-stu-id="2193b-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="2193b-105">設定の管理、インストールするアプリの選択、組織のニーズに合わせたセキュリティ構成の設定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2193b-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="2193b-106">「[Microsoft Intune を使用して Windows Holographic を実行するデバイスを管理する](https://docs.microsoft.com/intune/windows-holographic-for-business)」、[Windows Holographic でサポートされている構成サービス プロバイダー (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) と [Windows Holographic for Business でサポートされているポリシー](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2193b-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="2193b-107">VPN、Bitlocker、キオスク モードの機能を含むモバイル デバイス管理 (MDM) は、[Windows Holographic for Business にアップグレード](hololens1-upgrade-enterprise.md)した場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2193b-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="2193b-108">要件</span><span class="sxs-lookup"><span data-stu-id="2193b-108">Requirements</span></span>

 <span data-ttu-id="2193b-109">HoloLens デバイスを管理するには、組織でモバイルデバイス管理 (MDM) を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2193b-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="2193b-110">MDM プロバイダーには、Microsoft Intune や、Microsoft MDM API を使うサード パーティ プロバイダーを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="2193b-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <span data-ttu-id="2193b-111">さまざまな登録方法</span><span class="sxs-lookup"><span data-stu-id="2193b-111">Different ways to enroll</span></span>

<span data-ttu-id="2193b-112">OOBE または投稿のサインインのいずれかで選択された id の種類に応じて、さまざまな登録方法があります。</span><span class="sxs-lookup"><span data-stu-id="2193b-112">Depending on the type of identity chosen either during OOBE or post sign-in there are different methods of enrollment.</span></span> <span data-ttu-id="2193b-113">HoloLens の各種類の Id の詳細については、[このページ](hololens-identity.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2193b-113">To learn more about each type of Identity on HoloLens please visit [this page](hololens-identity.md).</span></span>

- <span data-ttu-id="2193b-114">Id が AAD の場合は、OOBE または**設定アプリ**への [  ->  **職場または学校**の  ->  **接続**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2193b-114">If Identity is AAD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="2193b-115">AAD の場合、自動 MDM 登録は、AAD が登録 Url で構成されている場合にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="2193b-115">For AAD, automatic MDM enrollment only occurs if AAD has been configured with enrollment URLs.</span></span>
- <span data-ttu-id="2193b-116">Id が AAD であり、デバイスが、特定の構成プロファイルが割り当てられた Intune MDM サーバーに事前登録されている場合、AAD での参加と登録は自動的に行われます。</span><span class="sxs-lookup"><span data-stu-id="2193b-116">If Identity is AAD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then AAD-Join and enrollment will automatically occur during OOBE.</span></span>
    - <span data-ttu-id="2193b-117">[19041.1103 + ビルド](hololens-release-notes.md#windows-holographic-version-2004)で利用可能な[自動操縦フロー](hololens2-autopilot.md)とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="2193b-117">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
- <span data-ttu-id="2193b-118">Id が MSA の場合は、[**アプリ**  ->  **アクセスの職場または学校**の  ->  **接続**] ボタンを使用します。</span><span class="sxs-lookup"><span data-stu-id="2193b-118">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="2193b-119">[ワークアカウントの追加] (AWA) フローとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="2193b-119">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="2193b-120">Id が Local ユーザーの場合は、[**設定] アプリ**  ->  **へのアクセスは**、[  ->  **デバイス管理] リンクでのみ**機能します。</span><span class="sxs-lookup"><span data-stu-id="2193b-120">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="2193b-121">純粋 MDM の登録フローとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="2193b-121">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="2193b-122">デバイスが MDM サーバーに登録されると、設定アプリはデバイス管理にデバイスが登録されたことを反映するようになります。</span><span class="sxs-lookup"><span data-stu-id="2193b-122">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="2193b-123">MDM への自動登録</span><span class="sxs-lookup"><span data-stu-id="2193b-123">Auto-enrollment in MDM</span></span>

<span data-ttu-id="2193b-124">Azure Active Directory (Azure AD) と、認証用の AAD トークンを受け入れる MDM ソリューション (現在のところ、Microsoft Intune と AirWatch でのみサポートされている場合) を組織で使っている場合、IT 管理者はユーザーが Azure AD アカウントにサインインした後 MDM 登録が自動的に行われるように Azure AD を構成できます。</span><span class="sxs-lookup"><span data-stu-id="2193b-124">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an AAD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="2193b-125">Azure AD の登録を構成する方法をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2193b-125">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="2193b-126">自動登録が有効な場合、追加の手動登録は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="2193b-126">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="2193b-127">ユーザーが Azure AD アカウントでサインインすると、最初の実行エクスペリエンスを完了した後デバイスが MDM に登録されます。</span><span class="sxs-lookup"><span data-stu-id="2193b-127">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

## <span data-ttu-id="2193b-128">Intune からの HoloLens の登録解除</span><span class="sxs-lookup"><span data-stu-id="2193b-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="2193b-129">デバイスの未登録の詳細については、[このページ](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2193b-129">To learn more about unenrolling a device visit [this page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span></span> 
