---
title: MDM での HoloLens の登録
description: 複数のデバイスの管理を容易にするために、HoloLens をモバイルデバイス管理 (MDM) に登録する方法について説明します。
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
ms.openlocfilehash: 624ebd17335820b1d2858f9d39cabb7032a83bfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309714"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="f2659-103">MDM での HoloLens の登録</span><span class="sxs-lookup"><span data-stu-id="f2659-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="f2659-104">[Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)などのソリューションを使用して、複数の Microsoft HoloLens デバイスを同時に管理できます。</span><span class="sxs-lookup"><span data-stu-id="f2659-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="f2659-105">設定の管理、インストールするアプリの選択、組織のニーズに合わせたセキュリティ構成の設定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f2659-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="f2659-106">「[Microsoft Intune を使用して Windows Holographic を実行するデバイスを管理する](https://docs.microsoft.com/intune/windows-holographic-for-business)」、[Windows Holographic でサポートされている構成サービス プロバイダー (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) と [Windows Holographic for Business でサポートされているポリシー](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2659-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="f2659-107">VPN、Bitlocker、キオスク モードの機能を含むモバイル デバイス管理 (MDM) は、[Windows Holographic for Business にアップグレード](hololens1-upgrade-enterprise.md)した場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2659-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="f2659-108">要件</span><span class="sxs-lookup"><span data-stu-id="f2659-108">Requirements</span></span>

 <span data-ttu-id="f2659-109">HoloLens デバイスを管理するためには、組織でモバイルデバイス管理 (MDM) を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2659-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="f2659-110">MDM プロバイダーには、Microsoft Intune や、Microsoft MDM API を使うサード パーティ プロバイダーを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="f2659-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="f2659-111">さまざまな登録方法</span><span class="sxs-lookup"><span data-stu-id="f2659-111">Different ways to enroll</span></span>

<span data-ttu-id="f2659-112">OOBE 中に選択された [id](hololens-identity.md) の種類によって、またはサインイン後に、さまざまな登録方法があります。</span><span class="sxs-lookup"><span data-stu-id="f2659-112">Depending on the type of [identity](hololens-identity.md) chosen either during OOBE or post sign-in, there are different methods of enrollment.</span></span>

- <span data-ttu-id="f2659-113">Id が Azure AD 場合は、OOBE または **設定アプリ** で [  ->  **職場または学校へ** の  ->  **接続**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2659-113">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="f2659-114">Azure AD の場合、 [自動 MDM 登録](hololens-enroll-mdm.md#auto-enrollment-in-mdm) は、Azure AD が登録 url で構成されている場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="f2659-114">For Azure AD, [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) only occurs if Azure AD has been configured with enrollment URLs.</span></span>
     
- <span data-ttu-id="f2659-115">Id が Azure AD、デバイスが、割り当てられている特定の構成プロファイルを使用して Intune MDM サーバーに事前登録されている場合は、OOBE 中に Azure AD-Join と [自動 MDM 登録](hololens-enroll-mdm.md#auto-enrollment-in-mdm) が行われます。</span><span class="sxs-lookup"><span data-stu-id="f2659-115">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) will occur during OOBE.</span></span>
    - <span data-ttu-id="f2659-116">[19041.1103 + ビルド](hololens-release-notes.md#windows-holographic-version-2004)で使用可能な[自動操縦フロー](hololens2-autopilot.md)とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f2659-116">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
    

- <span data-ttu-id="f2659-117">Id が MSA の場合は、[設定] [**アプリ**  ->  へのアクセス] [**職場または学校** への  ->  **接続**] ボタンを使用します。</span><span class="sxs-lookup"><span data-stu-id="f2659-117">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="f2659-118">"職場アカウントの追加 (AWA)" フローとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f2659-118">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="f2659-119">Id がローカルユーザーの場合は、[設定] [**アプリ** へのアクセス] [  ->  **職場または学校**  ->  **に登録** する] リンクを使用します。</span><span class="sxs-lookup"><span data-stu-id="f2659-119">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="f2659-120">純粋 MDM 登録フローとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f2659-120">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="f2659-121">デバイスが MDM サーバーに登録されると、デバイスがデバイス管理に登録されていることが設定アプリに反映されるようになります。</span><span class="sxs-lookup"><span data-stu-id="f2659-121">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="f2659-122">MDM への自動登録</span><span class="sxs-lookup"><span data-stu-id="f2659-122">Auto-enrollment in MDM</span></span>

<span data-ttu-id="f2659-123">組織が [Azure Premium サブスクリプション](https://azure.microsoft.com/overview/)を持っていて、Azure Active Directory (Azure AD) を使用していて、認証用の Azure AD トークンを受け入れる mdm ソリューション (現時点では Microsoft Intune と航空監視でのみサポートされている) を使用している場合、IT 管理者は Azure AD アカウントでユーザーがサインインした後に MDM 登録を自動的に許可するように Azure AD を構成</span><span class="sxs-lookup"><span data-stu-id="f2659-123">If your organization has an [Azure Premium subscription](https://azure.microsoft.com/overview/), is using Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="f2659-124">Azure AD の登録を構成する方法をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2659-124">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="f2659-125">自動登録が有効になっている場合、追加の手動登録は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f2659-125">When auto-enrollment is enabled, no extra manual enrollment is needed.</span></span> <span data-ttu-id="f2659-126">ユーザーが Azure AD アカウントでサインインすると、最初の実行エクスペリエンスを完了した後デバイスが MDM に登録されます。</span><span class="sxs-lookup"><span data-stu-id="f2659-126">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="f2659-127">デバイスが参加 Azure AD と、 [デバイスの所有者](security-adminless-os.md#device-owner)と見なされたユーザーに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f2659-127">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="f2659-128">Intune から HoloLens の登録を解除する</span><span class="sxs-lookup"><span data-stu-id="f2659-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="f2659-129">登録方法によっては、デバイスの登録解除が利用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f2659-129">Depending on the enrollment method, unenrolling your device may not be available.</span></span>

<span data-ttu-id="f2659-130">デバイスが Azure AD アカウントまたは自動操縦装置に登録されている場合、Intune から登録解除することはできません。</span><span class="sxs-lookup"><span data-stu-id="f2659-130">If your device was enrolled with an Azure AD account or Autopilot, it cannot be unenrolled from Intune.</span></span> <span data-ttu-id="f2659-131">HoloLens を Azure AD から切断する場合、または Azure AD 別のテナントに再度参加させる場合は、デバイスを [リセット/更新](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2659-131">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) the device.</span></span>

<span data-ttu-id="f2659-132">仕事用アカウントを追加した MSA アカウント、またはデバイス管理のみに登録されているローカルアカウントからデバイスが登録されている場合は、デバイスの登録を解除することができます。</span><span class="sxs-lookup"><span data-stu-id="f2659-132">If your device was enrolled from a MSA account that added a work account or from a Local account that enrolled only in device management, then you may unenroll the device.</span></span> <span data-ttu-id="f2659-133">[スタート] メニューを開き、[設定] [**アプリ**  ->  **アクセス] [職場または学校**  ->  *アカウント* の  ->  **切断**] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="f2659-133">Open the Start menu and then select **Settings App** -> **Access Work or School** -> *YourAccount* -> **Disconnect** button.</span></span>