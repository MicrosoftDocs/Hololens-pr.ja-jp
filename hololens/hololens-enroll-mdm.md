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
ms.openlocfilehash: 054c4ded7496957671c055e3161a1297de7abc1a
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828692"
---
# <span data-ttu-id="6844a-103">MDM での HoloLens の登録</span><span class="sxs-lookup"><span data-stu-id="6844a-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="6844a-104">[Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)などのソリューションを使用して、複数の microsoft HoloLens デバイスを同時に管理できます。</span><span class="sxs-lookup"><span data-stu-id="6844a-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="6844a-105">設定の管理、インストールするアプリの選択、組織のニーズに合わせたセキュリティ構成の設定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6844a-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="6844a-106">「[Microsoft Intune を使用して Windows Holographic を実行するデバイスを管理する](https://docs.microsoft.com/intune/windows-holographic-for-business)」、[Windows Holographic でサポートされている構成サービス プロバイダー (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) と [Windows Holographic for Business でサポートされているポリシー](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6844a-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="6844a-107">VPN、Bitlocker、キオスク モードの機能を含むモバイル デバイス管理 (MDM) は、[Windows Holographic for Business にアップグレード](hololens1-upgrade-enterprise.md)した場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6844a-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="6844a-108">要件</span><span class="sxs-lookup"><span data-stu-id="6844a-108">Requirements</span></span>

 <span data-ttu-id="6844a-109">HoloLens デバイスを管理するには、組織でモバイルデバイス管理 (MDM) を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6844a-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="6844a-110">MDM プロバイダーには、Microsoft Intune や、Microsoft MDM API を使うサード パーティ プロバイダーを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="6844a-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>

## <span data-ttu-id="6844a-111">MDM への自動登録</span><span class="sxs-lookup"><span data-stu-id="6844a-111">Auto-enrollment in MDM</span></span>

<span data-ttu-id="6844a-112">Azure Active Directory (Azure AD) と、認証用の AAD トークンを受け入れる MDM ソリューション (現在のところ、Microsoft Intune と AirWatch でのみサポートされている場合) を組織で使っている場合、IT 管理者はユーザーが Azure AD アカウントにサインインした後 MDM 登録が自動的に行われるように Azure AD を構成できます。</span><span class="sxs-lookup"><span data-stu-id="6844a-112">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an AAD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="6844a-113">Azure AD の登録を構成する方法をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6844a-113">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="6844a-114">自動登録が有効な場合、追加の手動登録は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6844a-114">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="6844a-115">ユーザーが Azure AD アカウントでサインインすると、最初の実行エクスペリエンスを完了した後デバイスが MDM に登録されます。</span><span class="sxs-lookup"><span data-stu-id="6844a-115">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

## <span data-ttu-id="6844a-116">設定アプリを使った登録</span><span class="sxs-lookup"><span data-stu-id="6844a-116">Enroll through Settings app</span></span>

 <span data-ttu-id="6844a-117">最初の実行エクスペリエンス時にデバイスが MDM に登録されない場合、ユーザーは設定アプリを使って組織の MDM サーバーにデバイスを手動で登録できます。</span><span class="sxs-lookup"><span data-stu-id="6844a-117">When the device is not enrolled in MDM during the first-run experience, the user can manually enroll the device with the organization's MDM server using the Settings app.</span></span>

1. <span data-ttu-id="6844a-118">**[設定]** > **[アカウント]** > **[職場のアクセス]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="6844a-118">Go to **Settings** > **Accounts** > **Work access**.</span></span>
1. <span data-ttu-id="6844a-119">**[デバイス管理 (MDM) に登録する]** を選び、組織アカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="6844a-119">Select **Enroll into device management** and enter your organizational account.</span></span> <span data-ttu-id="6844a-120">組織のサインイン ページにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="6844a-120">You will be redirected to your organization's sign in page.</span></span>
1. <span data-ttu-id="6844a-121">MDM サーバーでの認証に成功すると、成功を示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6844a-121">Upon successful authentication to the MDM server, a success message is shown.</span></span>

<span data-ttu-id="6844a-122">これで、デバイスが MDM サーバーに登録されました。</span><span class="sxs-lookup"><span data-stu-id="6844a-122">Your device is now enrolled with your MDM server.</span></span> <span data-ttu-id="6844a-123">設定アプリに、デバイスがデバイス管理に登録されたことが反映されます。</span><span class="sxs-lookup"><span data-stu-id="6844a-123">The Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="6844a-124">Intune からの HoloLens の登録解除</span><span class="sxs-lookup"><span data-stu-id="6844a-124">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="6844a-125">Intune からリモートで HoloLens を[登録解除する](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows)ことはできません。</span><span class="sxs-lookup"><span data-stu-id="6844a-125">You cannot [unenroll](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows) HoloLens from Intune remotely.</span></span> <span data-ttu-id="6844a-126">管理者が MDM を使用してデバイスを登録解除する場合、デバイスは Intune ダッシュボードから削除されます。</span><span class="sxs-lookup"><span data-stu-id="6844a-126">If the administrator unenrolls the device using MDM, the device will age out of the Intune dashboard.</span></span>
