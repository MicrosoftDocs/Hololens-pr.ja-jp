---
title: Windows Holographic for Business 機能のロック解除
description: Windows Holographic for Business にアップグレードすると、HoloLens はビジネス向けに設計された追加機能を提供します。
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: b5ae9b0d6859c0f916b5b906e2e9ec54cad6cbd9
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635196"
---
# <a name="unlock-windows-holographic-for-business-features"></a><span data-ttu-id="c12cf-103">Windows Holographic for Business 機能のロック解除</span><span class="sxs-lookup"><span data-stu-id="c12cf-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c12cf-104">このページは HoloLens 第1世代にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c12cf-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="c12cf-105">Microsoft HoloLens は、Windows Holographic (HoloLens 向けに設計された Windows 10 のエディション)、およびビジネス向けに設計された追加機能を提供する [商用スイート](hololens-commercial-features.md)で実行される *開発エディション* で使用できます。</span><span class="sxs-lookup"><span data-stu-id="c12cf-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="c12cf-106">Commercial Suite を購入すると、Windows Holographic を Windows Holographic for Business にアップグレードするライセンスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c12cf-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="c12cf-107">このライセンスは、組織の [モバイルデバイス管理 (MDM) プロバイダー](#edition-upgrade-by-using-mdm) または [プロビジョニングパッケージ](#edition-upgrade-by-using-a-provisioning-package)を使用して、デバイスに適用できます。</span><span class="sxs-lookup"><span data-stu-id="c12cf-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="c12cf-108">Windows 10 バージョン1803では、[**設定** システム] を選択して、HoloLens が business edition にアップグレードされていることを確認でき  >  ます。</span><span class="sxs-lookup"><span data-stu-id="c12cf-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <a name="edition-upgrade-by-using-mdm"></a><span data-ttu-id="c12cf-109">MDM を使用したエディションのアップグレード</span><span class="sxs-lookup"><span data-stu-id="c12cf-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="c12cf-110">エンタープライズ ライセンスは、[WindowsLicensing 構成サービス プロバイダー (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) をサポートする任意の MDM プロバイダーを使って適用できます。</span><span class="sxs-lookup"><span data-stu-id="c12cf-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="c12cf-111">最新バージョンの Microsoft MDM API では、WindowsLicensing CSP がサポートされる予定です。</span><span class="sxs-lookup"><span data-stu-id="c12cf-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="c12cf-112">Microsoft Intune を使用して HoloLens をアップグレードする手順の詳細については、「 [Windows Holographic を実行しているデバイスを Windows Holographic for Business にアップグレードする](/intune/holographic-upgrade)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c12cf-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="c12cf-113">他の MDM プロバイダーでは、ポリシーをセットアップして展開する具体的な手順が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c12cf-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <a name="edition-upgrade-by-using-a-provisioning-package"></a><span data-ttu-id="c12cf-114">プロビジョニングパッケージを使用したエディションのアップグレード</span><span class="sxs-lookup"><span data-stu-id="c12cf-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="c12cf-115">プロビジョニング パッケージは、Windows 構成デザイナー ツールにより作成された、指定された構成をデバイスに適用するファイルです。</span><span class="sxs-lookup"><span data-stu-id="c12cf-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a><span data-ttu-id="c12cf-116">Windows Holographic エディションをアップグレードするプロビジョニング パッケージの作成</span><span class="sxs-lookup"><span data-stu-id="c12cf-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="c12cf-117">HoloLens 用プロビジョニング パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="c12cf-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="c12cf-118">**ランタイム設定**  >  **EditionUpgrade** にアクセスし、[ **EditionUpgradeWithLicense**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c12cf-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![選んだライセンス設定でエディションをアップグレード](images/icd1.png)

1. <span data-ttu-id="c12cf-120">商用スイートを購入したときに提供された XML ライセンスファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="c12cf-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c12cf-121">[プロビジョニング パッケージでは追加の設定](hololens-provisioning.md)を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c12cf-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="c12cf-122">**[ファイル]** メニューの **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c12cf-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="c12cf-123">プロジェクトファイルに機密情報が含まれている可能性があることを示す警告を確認し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c12cf-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c12cf-124">プロビジョニングパッケージを作成するときに、プロジェクトファイルとプロビジョニングパッケージ (ppkg) ファイルに機密情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c12cf-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="c12cf-125">.ppkg ファイルは暗号化するかどうかを選べますが、プロジェクト ファイルは暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="c12cf-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="c12cf-126">プロジェクトファイルは安全な場所に保存し、不要になったときにプロジェクトファイルを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c12cf-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="c12cf-127">**[エクスポート]** メニューの **[プロビジョニング パッケージ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c12cf-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="c12cf-128">[ **所有者** ] を **IT 管理** 者に変更します。これにより、このプロビジョニングパッケージの優先順位が、別のソースからこのデバイスに適用されている他のものよりも高くなるように設定し、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c12cf-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="c12cf-129">**[パッケージのバージョン]** の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="c12cf-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="c12cf-130">既存のパッケージに変更を加えてバージョン番号を変更することで、以前に適用されたパッケージを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="c12cf-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="c12cf-131">[ **プロビジョニングパッケージのセキュリティの詳細の選択**] で、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c12cf-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="c12cf-132">[ **次** へ] を選択して、プロビジョニングパッケージを構築した後の出力場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="c12cf-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="c12cf-133">既定では、Windows ICD はプロジェクト フォルダーを出力先として使います。</span><span class="sxs-lookup"><span data-stu-id="c12cf-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="c12cf-134">必要に応じて、[ **参照** ] を選択して既定の出力場所を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="c12cf-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="c12cf-135">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c12cf-135">Select **Next**.</span></span>

1. <span data-ttu-id="c12cf-136">[ **ビルド** ] を選択して、パッケージのビルドを開始します。</span><span class="sxs-lookup"><span data-stu-id="c12cf-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="c12cf-137">[ビルド] ページにプロジェクト情報が表示され、進行状況バーにビルドの状態が示されます。</span><span class="sxs-lookup"><span data-stu-id="c12cf-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="c12cf-138">ビルドが完了したら、[ **完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c12cf-138">When the build completes, select **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="c12cf-139">HoloLens へのプロビジョニング パッケージの適用</span><span class="sxs-lookup"><span data-stu-id="c12cf-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="c12cf-140">USB ケーブルを使用して、デバイスを PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="c12cf-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="c12cf-141">デバイスを起動しますが、初期セットアップエクスペリエンス (青いボックスの最初のページ) の [ **フィット** ] ページを超えないで続行しないでください。</span><span class="sxs-lookup"><span data-stu-id="c12cf-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="c12cf-142">PC では、HoloLens はファイルエクスプローラーにデバイスとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="c12cf-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c12cf-143">HoloLens デバイスが Windows 10 バージョン1607またはそれ以前のバージョンを実行している場合は、デバイス上の **ボリュームダウン** と **電源** ボタンを同時に押すことで、ファイルエクスプローラーを開きます。</span><span class="sxs-lookup"><span data-stu-id="c12cf-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="c12cf-144">エクスプローラーで、プロビジョニング パッケージ (.ppkg) をデバイス ストレージに ドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="c12cf-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="c12cf-145">HoloLens が [**適合**] ページに残っている場合は、**ボリューム** を簡単に押したままにして、[**電源**] ボタンをもう一度押します。</span><span class="sxs-lookup"><span data-stu-id="c12cf-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="c12cf-146">パッケージを信頼できるかどうかを確認するメッセージが表示され、それを適用するかどうかが HoloLens ます。</span><span class="sxs-lookup"><span data-stu-id="c12cf-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="c12cf-147">パッケージが信頼できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c12cf-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="c12cf-148">パッケージが正常に適用されたかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c12cf-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="c12cf-149">正常に適用されなかった場合は、パッケージを修正して、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="c12cf-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="c12cf-150">成功した場合は、デバイスのセットアップを続行します。</span><span class="sxs-lookup"><span data-stu-id="c12cf-150">If successful, proceed with device setup.</span></span>
