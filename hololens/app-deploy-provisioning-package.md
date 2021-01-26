---
title: プロビジョニング パッケージ
description: HoloLens デバイスのアプリのパッケージ化、プロビジョニング、展開、およびエンタープライズ アプリの展開について説明します。
keywords: アプリ, アプリの展開, エンタープライズ アプリの展開, プロビジョニング
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
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283698"
---
# <span data-ttu-id="881e1-104">プロビジョニング パッケージ</span><span class="sxs-lookup"><span data-stu-id="881e1-104">Provisioning Package</span></span>

<span data-ttu-id="881e1-105">プロビジョニング パッケージを使用すると、エンドポイント管理にアクセスすることなく、環境内のデバイスを準備および構成できます。</span><span class="sxs-lookup"><span data-stu-id="881e1-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="881e1-106">また、ユーザーの ID、登録状態、Out of Box Experience (OOBE) の間、またはセットアップ中にプロビジョニング パッケージを適用することで、デバイスに展開 [することもできます](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)。</span><span class="sxs-lookup"><span data-stu-id="881e1-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <span data-ttu-id="881e1-107">プロビジョニング パッケージに関する考慮事項:</span><span class="sxs-lookup"><span data-stu-id="881e1-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="881e1-108">非パブリック アプリ</span><span class="sxs-lookup"><span data-stu-id="881e1-108">Non-Public apps</span></span>
* <span data-ttu-id="881e1-109">USB サイドロードのみ</span><span class="sxs-lookup"><span data-stu-id="881e1-109">USB side-load only</span></span>
* <span data-ttu-id="881e1-110">自動更新なし (PPKG による手動更新が必要)</span><span class="sxs-lookup"><span data-stu-id="881e1-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="881e1-111">プロビジョニング パッケージ経由でインストールされたアプリは、ローカル コンピューター ストアの証明書で署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="881e1-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="881e1-112">プロビジョニング パッケージは証明書をデバイス (ローカル コンピューター) ストアにのみインストールできます。そのため、アプリと証明書は同じプロビジョニング パッケージ経由でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="881e1-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="881e1-113">MDM から証明書を展開する場合、または証明書マネージャーを使用[](certificate-manager.md)してインストールする場合は、ローカル コンピューター ストアに証明書を展開して、この方法でインストールされたアプリに署名してください。</span><span class="sxs-lookup"><span data-stu-id="881e1-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="881e1-114">HoloLens デバイス向けプロビジョニング パッケージの作成の基本については [、HoloLens のプロビジョニングに関するページをご覧ください](https://docs.microsoft.com/hololens/hololens-provisioning)。</span><span class="sxs-lookup"><span data-stu-id="881e1-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="881e1-115">アプリを展開するには、まず高度なプロビジョニングを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="881e1-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="881e1-116">HoloLens (第 1 世代) では、プロビジョニング パッケージを使用したアプリのインストール **(UniversalAppInstall)** のサポートが制限されています。</span><span class="sxs-lookup"><span data-stu-id="881e1-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="881e1-117">HoloLens (第 1 世代) デバイスは、OOBE 中にのみ PPKG 経由のアプリのインストールをサポートし、ユーザー コンテキストインストールでのみサポートします。</span><span class="sxs-lookup"><span data-stu-id="881e1-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <span data-ttu-id="881e1-118">セットアップ</span><span class="sxs-lookup"><span data-stu-id="881e1-118">Setup</span></span>

<span data-ttu-id="881e1-119">[Windows 構成デザイナーでは、次の](https://www.microsoft.com/store/productId/9NBLGGH4TX22)4 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="881e1-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="881e1-120">ApplicationManagement/AllowAllTrustedApps を "Yes" に設定します。</span><span class="sxs-lookup"><span data-stu-id="881e1-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="881e1-121">[ApplicationManagement/AllowAllTrustedApps を参照してください](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)。</span><span class="sxs-lookup"><span data-stu-id="881e1-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="881e1-122">**UniversalAppInstall**  >  **UserContextAppLicense に移動し\*\*\*\*、PackageFamilyName を入力します**。</span><span class="sxs-lookup"><span data-stu-id="881e1-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="881e1-123">[UniversalAppInstall を参照してください](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall)。</span><span class="sxs-lookup"><span data-stu-id="881e1-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="881e1-124">[「UserContextAppLicense」も参照してください](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)。</span><span class="sxs-lookup"><span data-stu-id="881e1-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="881e1-125">既にアプリをインストールしているデバイスで Device Portal を使用できます。</span><span class="sxs-lookup"><span data-stu-id="881e1-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="881e1-126">[アプリ] ページにアクセスし、PackageRelativeID 行 ("!" の前のすべての情報) を確認します。Is your **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="881e1-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="881e1-127">You will then see that you have a new section, **ApplicationFile**.</span><span class="sxs-lookup"><span data-stu-id="881e1-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="881e1-128">この領域を使って appx バンドルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="881e1-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="881e1-129">アプリを購入したのか、独自の LOB アプリを構築したのかによって、ライセンス ファイルまたはセキュリティ証明書をアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="881e1-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="881e1-130">ライセンス ファイルの場合: **UniversalAppInstall**  >  **UserContextAppLicence**に移動し、ライセンスの場所を参照してアップロードします。</span><span class="sxs-lookup"><span data-stu-id="881e1-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="881e1-131">セキュリティ ファイルの場合は、[証明書] **に移動** し、.appx バンドルと共にインストールする証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="881e1-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="881e1-132">プロジェクトは安全な場所に保存してください。</span><span class="sxs-lookup"><span data-stu-id="881e1-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="881e1-133">次 **に、** プロビジョニング パッケージ **としてエクスポートします**。</span><span class="sxs-lookup"><span data-stu-id="881e1-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="881e1-134">関連: [HoloLens にプロビジョニング パッケージを適用します](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)。</span><span class="sxs-lookup"><span data-stu-id="881e1-134">See also: [Apply your provisioning package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
