---
title: プロビジョニング パッケージ
description: アプリ、アプリの展開、エンタープライズアプリの demployment、プロビジョニング
keywords: アプリ、アプリの展開、エンタープライズアプリの demployment、プロビジョニング
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 0803b5f1b77ac7f123d534d101cd24903b87094c
ms.sourcegitcommit: 89ce6cdc0fc6d70a88217791c5f6d613778af614
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "11052584"
---
# <span data-ttu-id="89503-104">プロビジョニング パッケージ</span><span class="sxs-lookup"><span data-stu-id="89503-104">Provisioning Package</span></span>

<span data-ttu-id="89503-105">プロビジョニングパッケージを使用すると、エンドポイントの管理にアクセスせずに、環境内のデバイスを準備して構成することができます。</span><span class="sxs-lookup"><span data-stu-id="89503-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="89503-106">また、ユーザーの id、登録状態、不在時のエクスペリエンス (OOBE) 中にデバイスに展開したり、 [セットアップ時にプロビジョニングパッケージを適用](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="89503-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <span data-ttu-id="89503-107">プロビジョニングパッケージに関する考慮事項:</span><span class="sxs-lookup"><span data-stu-id="89503-107">Provisioning Packages considerations:</span></span>
* <span data-ttu-id="89503-108">非パブリックアプリ</span><span class="sxs-lookup"><span data-stu-id="89503-108">Non-Public apps</span></span>
* <span data-ttu-id="89503-109">USB サイドロードのみ</span><span class="sxs-lookup"><span data-stu-id="89503-109">USB side-load only</span></span>
* <span data-ttu-id="89503-110">自動更新なし (PPKGs 経由で手動で更新する必要があります)</span><span class="sxs-lookup"><span data-stu-id="89503-110">No auto update (requires manual updates via PPKGs)</span></span>

> [!NOTE] 
> <span data-ttu-id="89503-111">HoloLens デバイスのプロビジョニングパッケージの作成の基本については、「 [Hololens プロビジョニング](https://docs.microsoft.com/hololens/hololens-provisioning)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89503-111">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="89503-112">アプリを展開するには、advanced provisioning から始める必要があります。</span><span class="sxs-lookup"><span data-stu-id="89503-112">To deploy an app, you must start with advanced provisioning.</span></span> 

> [!NOTE] 
> <span data-ttu-id="89503-113">HoloLens (第1世代) では、プロビジョニングパッケージを使用して、アプリのインストール (**UniversalAppInstall**) のサポートが制限されています。</span><span class="sxs-lookup"><span data-stu-id="89503-113">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="89503-114">HoloLens (第1世代) デバイスでは、OOBE 中のみ、ユーザーコンテキストによってインストールされるアプリのインストールのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="89503-114">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <span data-ttu-id="89503-115">セットアップ</span><span class="sxs-lookup"><span data-stu-id="89503-115">Setup</span></span>

<span data-ttu-id="89503-116">[Windows 構成デザイナー](https://www.microsoft.com/store/productId/9NBLGGH4TX22)では、次の4つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="89503-116">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following 4 steps.</span></span>

1. <span data-ttu-id="89503-117">ApplicationManagement/AllowAllTrustedApps を "Yes" に設定します。</span><span class="sxs-lookup"><span data-stu-id="89503-117">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="89503-118">「 [Applicationmanagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89503-118">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>
2. <span data-ttu-id="89503-119">**UniversalAppInstall**  >  **UserContextAppLicense**の下で、[**パッケージ efamilyname**] を入力してください。</span><span class="sxs-lookup"><span data-stu-id="89503-119">Under **UniversalAppInstall** > **UserContextAppLicense** please enter the **PackageFamilyName**.</span></span> <span data-ttu-id="89503-120">「 [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="89503-120">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="89503-121">「 [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="89503-121">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>
    - <span data-ttu-id="89503-122">この情報がわからない場合は、既にアプリをインストールしているデバイスで Device Portal を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="89503-122">If you don’t know this, you can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="89503-123">[アプリ] ページにアクセスして、"!" の前にあるすべての情報を PackageRelativeID の行で確認します。は、整理された **名前**です。</span><span class="sxs-lookup"><span data-stu-id="89503-123">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>
3. <span data-ttu-id="89503-124">これにより、新しいセクションの **Applicationfile**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="89503-124">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="89503-125">この領域を使用して、appx バンドルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="89503-125">Use this area to upload your appx bundle.</span></span> 
4. <span data-ttu-id="89503-126">アプリを購入したか、独自の LOB アプリを作成したかに応じて、ライセンスファイルまたはセキュリティ証明書をアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="89503-126">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>
    - <span data-ttu-id="89503-127">ライセンスファイルの場合: [ **UniversalAppInstall**  >  **usercontext]** の下で、ライセンスの場所を参照してアップロードします。</span><span class="sxs-lookup"><span data-stu-id="89503-127">For license file: Under **UniversalAppInstall** > **UserContextAppLience** and browse to the location of your license and upload it.</span></span> 
    - <span data-ttu-id="89503-128">セキュリティファイルの場合 [ **証明書** ] に移動し、証明書を選択して、.appx バンドルと共にインストールします。</span><span class="sxs-lookup"><span data-stu-id="89503-128">For security file navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span> 

<span data-ttu-id="89503-129">セキュリティで保護された場所にプロジェクトを保存してください。</span><span class="sxs-lookup"><span data-stu-id="89503-129">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="89503-130">次に、**プロビジョニングパッケージ**として**エクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="89503-130">Then **Export** it as a **Provisioning Package**.</span></span>  
    
<span data-ttu-id="89503-131">「 [HoloLens にパッケージを適用する](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="89503-131">See also: [Apply your provisiong package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
