---
title: プロビジョニング パッケージ
description: デバイスのパッケージ化、プロビジョニング、デプロイ、エンタープライズ アプリの展開についてHoloLensします。
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
ms.openlocfilehash: 5aa554f9e7fdc09c3112b628e0978ac3332bc57d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635519"
---
# <a name="provisioning-package"></a><span data-ttu-id="1fa93-104">プロビジョニング パッケージ</span><span class="sxs-lookup"><span data-stu-id="1fa93-104">Provisioning Package</span></span>

<span data-ttu-id="1fa93-105">プロビジョニング パッケージを使用すると、エンドポイント管理にアクセスせずに環境内のデバイスを準備および構成できます。</span><span class="sxs-lookup"><span data-stu-id="1fa93-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="1fa93-106">また、ユーザーの ID、登録状態、Out of Box Experience (OOBE) の間、またはセットアップ中にプロビジョニング パッケージを適用する方法に関係なく、デバイス [に展開することもできます](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)。</span><span class="sxs-lookup"><span data-stu-id="1fa93-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <a name="provisioning-packages-considerations"></a><span data-ttu-id="1fa93-107">プロビジョニング パッケージに関する考慮事項:</span><span class="sxs-lookup"><span data-stu-id="1fa93-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="1fa93-108">非パブリック アプリ</span><span class="sxs-lookup"><span data-stu-id="1fa93-108">Non-Public apps</span></span>
* <span data-ttu-id="1fa93-109">USB サイドロードのみ</span><span class="sxs-lookup"><span data-stu-id="1fa93-109">USB side-load only</span></span>
* <span data-ttu-id="1fa93-110">自動更新なし (PPKG による手動更新が必要)</span><span class="sxs-lookup"><span data-stu-id="1fa93-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="1fa93-111">プロビジョニング パッケージを介してインストールされたアプリは、ローカル コンピューター ストア内の証明書によって署名されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fa93-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="1fa93-112">プロビジョニング パッケージでは、デバイス (ローカル コンピューター) ストアにのみ証明書をインストールできます。そのため、アプリと証明書は同じプロビジョニング パッケージを介してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="1fa93-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="1fa93-113">MDM から証明書を展開する場合、または証明書マネージャー を[](certificate-manager.md)使用してをインストールする場合は、必ずローカル コンピューター ストアに証明書を展開して、この方法でインストールされたアプリに署名してください。</span><span class="sxs-lookup"><span data-stu-id="1fa93-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="1fa93-114">デバイスのプロビジョニング パッケージを作成する基本については、「HoloLens」をHoloLens[してください](/hololens/hololens-provisioning)。</span><span class="sxs-lookup"><span data-stu-id="1fa93-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](/hololens/hololens-provisioning).</span></span> <span data-ttu-id="1fa93-115">アプリをデプロイするには、高度なプロビジョニングから始める必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fa93-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="1fa93-116">HoloLens (第 1 世代) では、プロビジョニング パッケージを使用したアプリのインストール **(UniversalAppInstall)** が制限されています。</span><span class="sxs-lookup"><span data-stu-id="1fa93-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="1fa93-117">HoloLens (第 1 世代) デバイスでは、OOBE 中のみ、およびユーザー コンテキストのインストールでのみ、PPKG 経由でのアプリのインストールがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1fa93-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <a name="setup"></a><span data-ttu-id="1fa93-118">セットアップ</span><span class="sxs-lookup"><span data-stu-id="1fa93-118">Setup</span></span>

<span data-ttu-id="1fa93-119">構成[Windows、次の 4](https://www.microsoft.com/store/productId/9NBLGGH4TX22)つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1fa93-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="1fa93-120">ApplicationManagement/AllowAllTrustedApps を "Yes" に設定します。</span><span class="sxs-lookup"><span data-stu-id="1fa93-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="1fa93-121">参照: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)。</span><span class="sxs-lookup"><span data-stu-id="1fa93-121">See: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="1fa93-122">**[UniversalAppInstall**  >  **UserContextAppLicense] に移動し\*\*\*\*、PackageFamilyName を入力します**。</span><span class="sxs-lookup"><span data-stu-id="1fa93-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="1fa93-123">[「UniversalAppInstall」を参照してください](/windows/configuration/wcd/wcd-universalappinstall)。</span><span class="sxs-lookup"><span data-stu-id="1fa93-123">See [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="1fa93-124">[「UserContextAppLicense 」も参照してください](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)。</span><span class="sxs-lookup"><span data-stu-id="1fa93-124">See also: [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="1fa93-125">アプリをインストールデバイス ポータルデバイスでアプリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1fa93-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="1fa93-126">[アプリ] ページにアクセスし、PackageRelativeID 行を見て、"!" の前のすべての情報を確認します。 **PackageFamilyName です**。</span><span class="sxs-lookup"><span data-stu-id="1fa93-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="1fa93-127">その後、新しいセクション ApplicationFile が **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="1fa93-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="1fa93-128">この領域を使用して、appx バンドルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="1fa93-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="1fa93-129">アプリを購入した場合、または独自の LOB アプリを構築した場合は、ライセンス ファイルまたはセキュリティ証明書をアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fa93-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="1fa93-130">ライセンス ファイルの場合 **:UniversalAppInstall**  >  **UserContextAppLicence** に移動し、ライセンスの場所を参照してアップロードします。</span><span class="sxs-lookup"><span data-stu-id="1fa93-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="1fa93-131">セキュリティ ファイルの場合は、[証明書] に **移動** し、.appx バンドルと共にインストールする証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="1fa93-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="1fa93-132">プロジェクトを安全な場所に保存してください。</span><span class="sxs-lookup"><span data-stu-id="1fa93-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="1fa93-133">次 **に、** プロビジョニング パッケージ **としてエクスポートします**。</span><span class="sxs-lookup"><span data-stu-id="1fa93-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="1fa93-134">「プロビジョニング パッケージ[を に適用する」もHoloLens。](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)</span><span class="sxs-lookup"><span data-stu-id="1fa93-134">See also: [Apply your provisioning package to HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
