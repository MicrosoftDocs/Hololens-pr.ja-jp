---
title: Windows Holographic for Business 機能のロック解除
description: Windows ホログラフィック for Business にアップグレードする場合、HoloLens にはビジネス向けに設計された追加機能が用意されています。
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
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829336"
---
# <span data-ttu-id="6ab28-103">Windows Holographic for Business 機能のロック解除</span><span class="sxs-lookup"><span data-stu-id="6ab28-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ab28-104">このページは、HoloLens 第1世代にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="6ab28-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="6ab28-105">Microsoft HoloLens は、Windows ホログラフィック (HoloLens 向けに設計された Windows 10 のエディション) と、ビジネス向けに設計された追加機能を提供する[商用スイート](hololens-commercial-features.md)で実行される*開発版*で利用できます。</span><span class="sxs-lookup"><span data-stu-id="6ab28-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="6ab28-106">Commercial Suite を購入すると、Windows Holographic を Windows Holographic for Business にアップグレードするライセンスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="6ab28-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="6ab28-107">このライセンスは、組織の[モバイルデバイス管理 (MDM) プロバイダー](#edition-upgrade-by-using-mdm)または[プロビジョニングパッケージ](#edition-upgrade-by-using-a-provisioning-package)を使って、デバイスに適用できます。</span><span class="sxs-lookup"><span data-stu-id="6ab28-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="6ab28-108">Windows 10 バージョン1803では、[**設定**システム] を選択することにより、HoloLens が business エディションにアップグレードされていることを確認でき  >  **System**ます。</span><span class="sxs-lookup"><span data-stu-id="6ab28-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <span data-ttu-id="6ab28-109">MDM を使用してエディションをアップグレードする</span><span class="sxs-lookup"><span data-stu-id="6ab28-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="6ab28-110">エンタープライズ ライセンスは、[WindowsLicensing 構成サービス プロバイダー (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) をサポートする任意の MDM プロバイダーを使って適用できます。</span><span class="sxs-lookup"><span data-stu-id="6ab28-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="6ab28-111">最新バージョンの Microsoft MDM API では、WindowsLicensing CSP がサポートされる予定です。</span><span class="sxs-lookup"><span data-stu-id="6ab28-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="6ab28-112">Microsoft Intune を使って HoloLens をアップグレードするための詳しい手順については、「 [Windows ホログラフィックを実行しているデバイスを Windows ホログラフィック For Business にアップグレードする](https://docs.microsoft.com/intune/holographic-upgrade)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ab28-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](https://docs.microsoft.com/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="6ab28-113">他の MDM プロバイダーでは、ポリシーをセットアップして展開する具体的な手順が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6ab28-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <span data-ttu-id="6ab28-114">プロビジョニングパッケージを使用したエディションのアップグレード</span><span class="sxs-lookup"><span data-stu-id="6ab28-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="6ab28-115">プロビジョニング パッケージは、Windows 構成デザイナー ツールにより作成された、指定された構成をデバイスに適用するファイルです。</span><span class="sxs-lookup"><span data-stu-id="6ab28-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <span data-ttu-id="6ab28-116">Windows Holographic エディションをアップグレードするプロビジョニング パッケージの作成</span><span class="sxs-lookup"><span data-stu-id="6ab28-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="6ab28-117">HoloLens 用プロビジョニング パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="6ab28-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="6ab28-118">**[実行時設定]** > **[EditionUpgrade]**、**[EditionUpgradeWithLicense]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="6ab28-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![選んだライセンス設定でエディションをアップグレード](images/icd1.png)

1. <span data-ttu-id="6ab28-120">商用製品を購入したときに提供された XML ライセンスファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="6ab28-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6ab28-121">[プロビジョニング パッケージでは追加の設定](hololens-provisioning.md)を構成できます。</span><span class="sxs-lookup"><span data-stu-id="6ab28-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="6ab28-122">[**ファイル**] メニューで、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6ab28-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="6ab28-123">プロジェクトファイルに機密情報が含まれている可能性があるという警告を読み、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ab28-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6ab28-124">プロビジョニングパッケージを作成する場合は、プロジェクトファイルとプロビジョニングパッケージ (ppkg) ファイルに機密情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6ab28-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="6ab28-125">.ppkg ファイルは暗号化するかどうかを選べますが、プロジェクト ファイルは暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="6ab28-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="6ab28-126">プロジェクトファイルは安全な場所に保存して、不要になった時点でプロジェクトファイルを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab28-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="6ab28-127">**[エクスポート]** メニューの **[プロビジョニング パッケージ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="6ab28-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="6ab28-128">[**所有者**] を**IT 管理**者に変更します。これにより、このプロビジョニングパッケージの優先順位が、別のソースからこのデバイスに適用されている他のアプリよりも高くなります。次に、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6ab28-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="6ab28-129">**[パッケージのバージョン]** の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="6ab28-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="6ab28-130">既存のパッケージに変更を加えてバージョン番号を変更することで、以前に適用されたパッケージを更新できます。</span><span class="sxs-lookup"><span data-stu-id="6ab28-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="6ab28-131">**プロビジョニングパッケージの [セキュリティの詳細の選択**] で、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6ab28-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="6ab28-132">[**次へ**] を選択して、プロビジョニングパッケージをビルドするときの出力場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="6ab28-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="6ab28-133">既定では、Windows ICD はプロジェクト フォルダーを出力先として使います。</span><span class="sxs-lookup"><span data-stu-id="6ab28-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="6ab28-134">必要に応じて [**参照**] を選択して、既定の出力場所を変更できます。</span><span class="sxs-lookup"><span data-stu-id="6ab28-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="6ab28-135">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6ab28-135">Select **Next**.</span></span>

1. <span data-ttu-id="6ab28-136">[**ビルド**] を選択して、パッケージの作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="6ab28-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="6ab28-137">ビルドページにプロジェクト情報が表示され、進行状況バーにはビルドの状態が示されます。</span><span class="sxs-lookup"><span data-stu-id="6ab28-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="6ab28-138">ビルドが完了したら、[**完了**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="6ab28-138">When the build completes, select **Finish**.</span></span>

### <span data-ttu-id="6ab28-139">HoloLens へのプロビジョニング パッケージの適用</span><span class="sxs-lookup"><span data-stu-id="6ab28-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="6ab28-140">USB ケーブルを使って、デバイスを PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="6ab28-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="6ab28-141">デバイスを起動しますが、最初のセットアップエクスペリエンスの [**自動調整**] ページ (青いボックスが付いた最初のページ) を超えて続行しないでください。</span><span class="sxs-lookup"><span data-stu-id="6ab28-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="6ab28-142">PC では、HoloLens がエクスプローラーでデバイスとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ab28-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6ab28-143">HoloLens デバイスで Windows 10 バージョン1607またはそれ以前のバージョンを実行している場合は、デバイス上で**ボリュームダウン**と**電源**ボタンを同時に押すことで、エクスプローラーを開きます。</span><span class="sxs-lookup"><span data-stu-id="6ab28-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="6ab28-144">エクスプローラーで、プロビジョニング パッケージ (.ppkg) をデバイス ストレージに ドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="6ab28-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="6ab28-145">HoloLens が [**自動調整**] ページに残っている状態で、**音量**を短くして、**電源**ボタンをもう一度同時に放します。</span><span class="sxs-lookup"><span data-stu-id="6ab28-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="6ab28-146">パッケージを信頼していて、それを適用する場合は、HoloLens から要求されます。</span><span class="sxs-lookup"><span data-stu-id="6ab28-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="6ab28-147">パッケージが信頼できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6ab28-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="6ab28-148">パッケージが正常に適用されたかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ab28-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="6ab28-149">正常に適用されなかった場合は、パッケージを修正して、もう一度試してください。</span><span class="sxs-lookup"><span data-stu-id="6ab28-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="6ab28-150">正常に終了したら、デバイスのセットアップを続行します。</span><span class="sxs-lookup"><span data-stu-id="6ab28-150">If successful, proceed with device setup.</span></span>
