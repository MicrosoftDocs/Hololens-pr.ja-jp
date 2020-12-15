---
title: プロビジョニング パッケージ
description: アプリ, アプリの展開, エンタープライズ アプリ, プロビジョニング
keywords: アプリ, アプリの展開, エンタープライズ アプリ, プロビジョニング
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
ms.openlocfilehash: 60efc454f9e1221372279401da9f8ee918e061e7
ms.sourcegitcommit: efa3fb7e353c5e56ee467cc7fd94ffdfaf46e2e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2020
ms.locfileid: "11219224"
---
# <span data-ttu-id="3a30a-104">プロビジョニング パッケージ</span><span class="sxs-lookup"><span data-stu-id="3a30a-104">Provisioning Package</span></span>

<span data-ttu-id="3a30a-105">プロビジョニング パッケージを使用すると、エンドポイント管理にアクセスすることなく、環境内のデバイスを準備および構成できます。</span><span class="sxs-lookup"><span data-stu-id="3a30a-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="3a30a-106">また、ユーザーの ID、登録状態、Out of Box Experience (OOBE) の間、またはセットアップ中にプロビジョニング パッケージを適用することで、デバイスに展開 [することもできます](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)。</span><span class="sxs-lookup"><span data-stu-id="3a30a-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <span data-ttu-id="3a30a-107">プロビジョニング パッケージに関する考慮事項:</span><span class="sxs-lookup"><span data-stu-id="3a30a-107">Provisioning Packages considerations:</span></span>
* <span data-ttu-id="3a30a-108">非パブリック アプリ</span><span class="sxs-lookup"><span data-stu-id="3a30a-108">Non-Public apps</span></span>
* <span data-ttu-id="3a30a-109">USB サイドロードのみ</span><span class="sxs-lookup"><span data-stu-id="3a30a-109">USB side-load only</span></span>
* <span data-ttu-id="3a30a-110">自動更新なし (PPKG による手動更新が必要)</span><span class="sxs-lookup"><span data-stu-id="3a30a-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="3a30a-111">プロビジョニング パッケージ経由でインストールされたアプリは、ローカル コンピューター ストアの証明書で署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a30a-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="3a30a-112">プロビジョニング パッケージは証明書をデバイス (ローカル コンピューター) ストアにのみインストールできます。そのため、アプリと証明書は同じプロビジョニング パッケージ経由でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="3a30a-112">Provisioning packages can only install certificates to the device (local machine) store, therefore the app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="3a30a-113">MDM から証明書を展開する場合、または証明書マネージャーを使用[](certificate-manager.md)してインストールする場合は、ローカル コンピューター ストアに証明書を展開して、この方法でインストールされたアプリに署名してください。</span><span class="sxs-lookup"><span data-stu-id="3a30a-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), please make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="3a30a-114">HoloLens デバイス向けプロビジョニング パッケージの作成の基本については [、HoloLens のプロビジョニングに関するページをご覧ください](https://docs.microsoft.com/hololens/hololens-provisioning)。</span><span class="sxs-lookup"><span data-stu-id="3a30a-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="3a30a-115">アプリを展開するには、まず高度なプロビジョニングを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a30a-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="3a30a-116">HoloLens (第 1 世代) では、プロビジョニング パッケージを使用したアプリのインストール **(UniversalAppInstall)** のサポートが制限されています。</span><span class="sxs-lookup"><span data-stu-id="3a30a-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="3a30a-117">HoloLens (第 1 世代) デバイスは、OOBE 中のみ、およびユーザー コンテキストインストールでのみ PPKG 経由のアプリのインストールをサポートします。</span><span class="sxs-lookup"><span data-stu-id="3a30a-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <span data-ttu-id="3a30a-118">セットアップ</span><span class="sxs-lookup"><span data-stu-id="3a30a-118">Setup</span></span>

<span data-ttu-id="3a30a-119">[Windows 構成デザイナー内では、次](https://www.microsoft.com/store/productId/9NBLGGH4TX22)の 4 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3a30a-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following 4 steps.</span></span>

1. <span data-ttu-id="3a30a-120">ApplicationManagement/AllowAllTrustedApps を "Yes" に設定します。</span><span class="sxs-lookup"><span data-stu-id="3a30a-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="3a30a-121">[ApplicationManagement/AllowAllTrustedApps を参照してください](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)。</span><span class="sxs-lookup"><span data-stu-id="3a30a-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="3a30a-122">**[UniversalAppInstall**  >  **UserContextAppLicense] で\*\*\*\*、PackageFamilyName を入力してください**。</span><span class="sxs-lookup"><span data-stu-id="3a30a-122">Under **UniversalAppInstall** > **UserContextAppLicense** please enter the **PackageFamilyName**.</span></span> <span data-ttu-id="3a30a-123">[UniversalAppInstall を参照してください](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall)。</span><span class="sxs-lookup"><span data-stu-id="3a30a-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="3a30a-124">[「UserContextAppLicense」も参照してください](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)。</span><span class="sxs-lookup"><span data-stu-id="3a30a-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="3a30a-125">既にアプリをインストールしているデバイスで Device Portal を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3a30a-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="3a30a-126">[アプリ] ページにアクセスし、PackageRelativeID 行 ("!" の前のすべての情報) を確認します。Is your **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="3a30a-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>
    
3. <span data-ttu-id="3a30a-127">You will then see that you have a new section, **ApplicationFile**.</span><span class="sxs-lookup"><span data-stu-id="3a30a-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="3a30a-128">この領域を使って appx バンドルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="3a30a-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="3a30a-129">アプリを購入したのか、独自の LOB アプリを構築したのかによって、ライセンス ファイルまたはセキュリティ証明書をアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a30a-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="3a30a-130">ライセンス ファイルの場合: **UniversalAppInstall**  >  **UserContextAppLience の**下で、ライセンスの場所を参照してアップロードします。</span><span class="sxs-lookup"><span data-stu-id="3a30a-130">For license file: Under **UniversalAppInstall** > **UserContextAppLience** and browse to the location of your license and upload it.</span></span> 
    - <span data-ttu-id="3a30a-131">セキュリティ ファイルの場合は、[ **証明書** ] に移動し、.appx バンドルと共にインストールする証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a30a-131">For security file navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="3a30a-132">プロジェクトは安全な場所に保存してください。</span><span class="sxs-lookup"><span data-stu-id="3a30a-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="3a30a-133">次 **に、** プロビジョニング パッケージ **としてエクスポートします**。</span><span class="sxs-lookup"><span data-stu-id="3a30a-133">Then **Export** it as a **Provisioning Package**.</span></span>  
    
<span data-ttu-id="3a30a-134">関連: [HoloLens にプロビジョニング パッケージを適用します](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)。</span><span class="sxs-lookup"><span data-stu-id="3a30a-134">See also: [Apply your provisiong package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
