---
title: プロビジョニングパッケージ
description: アプリのパッケージ化、プロビジョニング、デプロイ、および HoloLens デバイス向けのエンタープライズアプリの展開について説明します。
keywords: アプリ, アプリのデプロイ, エンタープライズアプリのデプロイ, プロビジョニング
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309409"
---
# <a name="provisioning-package"></a><span data-ttu-id="76bbd-104">プロビジョニングパッケージ</span><span class="sxs-lookup"><span data-stu-id="76bbd-104">Provisioning Package</span></span>

<span data-ttu-id="76bbd-105">プロビジョニングパッケージを使用して、エンドポイント管理にアクセスせずに、環境でデバイスの準備と構成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="76bbd-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="76bbd-106">また、ユーザーの id、登録ステータス、アウトオブボックスエクスペリエンス (OOBE) 中、または [セットアップ中にプロビジョニングパッケージを適用](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)して、デバイスに展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="76bbd-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <a name="provisioning-packages-considerations"></a><span data-ttu-id="76bbd-107">プロビジョニングパッケージに関する考慮事項:</span><span class="sxs-lookup"><span data-stu-id="76bbd-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="76bbd-108">パブリックでないアプリ</span><span class="sxs-lookup"><span data-stu-id="76bbd-108">Non-Public apps</span></span>
* <span data-ttu-id="76bbd-109">USB サイド読み込みのみ</span><span class="sxs-lookup"><span data-stu-id="76bbd-109">USB side-load only</span></span>
* <span data-ttu-id="76bbd-110">自動更新なし (PPKGs を使用した手動更新が必要)</span><span class="sxs-lookup"><span data-stu-id="76bbd-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="76bbd-111">プロビジョニングパッケージを使用してインストールされるアプリは、ローカルコンピューターストアの証明書によって署名されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="76bbd-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="76bbd-112">プロビジョニングパッケージでは、デバイス (ローカルコンピューター) ストアにのみ証明書をインストールできるため、同じプロビジョニングパッケージを使用してアプリと証明書をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="76bbd-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="76bbd-113">MDM から証明書を展開する場合、または [証明書マネージャー](certificate-manager.md)を使用してインストールする場合は、この方法でインストールされたアプリに署名するために、ローカルコンピューターストアに証明書をデプロイしてください。</span><span class="sxs-lookup"><span data-stu-id="76bbd-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="76bbd-114">HoloLens デバイス用のプロビジョニングパッケージを作成する方法の基本については、「 [Hololens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76bbd-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="76bbd-115">アプリを展開するには、高度なプロビジョニングから始める必要があります。</span><span class="sxs-lookup"><span data-stu-id="76bbd-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="76bbd-116">HoloLens (第1世代) では、プロビジョニングパッケージを使用したアプリのインストール (**UniversalAppInstall**) のサポートが制限されています。</span><span class="sxs-lookup"><span data-stu-id="76bbd-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="76bbd-117">HoloLens (第1世代) デバイスでは、OOBE 中にのみ PPKG を使用したアプリのインストールのみがサポートされ、ユーザーコンテキストのインストールのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="76bbd-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <a name="setup"></a><span data-ttu-id="76bbd-118">セットアップ</span><span class="sxs-lookup"><span data-stu-id="76bbd-118">Setup</span></span>

<span data-ttu-id="76bbd-119">[Windows 構成デザイナー](https://www.microsoft.com/store/productId/9NBLGGH4TX22)内で、次の4つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="76bbd-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="76bbd-120">ApplicationManagement/AllowAllTrustedApps を "Yes" に設定します。</span><span class="sxs-lookup"><span data-stu-id="76bbd-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="76bbd-121">参照してください: [Applicationmanagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)です。</span><span class="sxs-lookup"><span data-stu-id="76bbd-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="76bbd-122">**UniversalAppInstall**  >  **UserContextAppLicense** に移動し、[パッケージ] の **名前** を入力します。</span><span class="sxs-lookup"><span data-stu-id="76bbd-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="76bbd-123">「 [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76bbd-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="76bbd-124">参照: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)</span><span class="sxs-lookup"><span data-stu-id="76bbd-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="76bbd-125">デバイスポータルは、アプリが既にインストールされているデバイスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="76bbd-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="76bbd-126">アプリのページにアクセスし、PackageRelativeID の行の前にあるすべての情報を確認します。は、整理 **Efamilyname** です。</span><span class="sxs-lookup"><span data-stu-id="76bbd-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="76bbd-127">これで、新しいセクション **Applicationfile** が作成されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="76bbd-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="76bbd-128">この領域を使用して、appx バンドルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="76bbd-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="76bbd-129">アプリを購入したか、独自の LOB アプリを作成したかに応じて、ライセンスファイルまたはセキュリティ証明書をアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="76bbd-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="76bbd-130">ライセンスファイルの場合: **UniversalAppInstall**  >  **usercontextアプリケーション** に移動し、ライセンスの場所を参照してアップロードします。</span><span class="sxs-lookup"><span data-stu-id="76bbd-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="76bbd-131">セキュリティファイルの場合は、[ **証明書** ] に移動し、.appx バンドルと共にインストールする証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="76bbd-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="76bbd-132">プロジェクトは安全な場所に保存してください。</span><span class="sxs-lookup"><span data-stu-id="76bbd-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="76bbd-133">次に、それを **プロビジョニングパッケージ** として **エクスポート** します。</span><span class="sxs-lookup"><span data-stu-id="76bbd-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="76bbd-134">関連項目: 「 [HoloLens にプロビジョニングパッケージを適用する](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="76bbd-134">See also: [Apply your provisioning package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
