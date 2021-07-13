---
title: HoloLensBitLocker 暗号化
description: BitLocker デバイス暗号化を有効にして、Mixed Reality デバイスに格納されているファイルHoloLensする方法について説明します。
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 37efab3ef3d68a9641320e144619008612f6efa2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635247"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a><span data-ttu-id="20ee2-103">HoloLens (第 1 世代) の BitLocker 暗号化</span><span class="sxs-lookup"><span data-stu-id="20ee2-103">HoloLens (1st Gen) BitLocker Encryption</span></span>

<span data-ttu-id="20ee2-104">HoloLens (第 1 世代) と HoloLens 2は両方とも BitLocker を使用したデバイス暗号化をサポートしますが、BitLocker は常に HoloLens 2 で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="20ee2-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="20ee2-105">この記事は、BitLocker を有効にして管理する (第 1 世代) HoloLensに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="20ee2-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="20ee2-106">[HoloLens (第 1 世代) では、BitLocker デバイスの暗号化を手動で有効にするか、モバイル デバイス管理 (MDM) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="20ee2-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="20ee2-107">次の手順に従って[、BitLocker デバイスの暗号化を有効](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption)にして、デバイスに格納されているファイルと情報をHoloLens。</span><span class="sxs-lookup"><span data-stu-id="20ee2-107">Follow these instructions to enable [BitLocker device encryption](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="20ee2-108">デバイスの暗号化は、AES-CBC 128 暗号化方法を使用してデータを保護するのに役立ちます。これは、BitLocker 構成サービス プロバイダー (CSP) の [EncryptionMethodByDriveType](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) メソッド 3 と同じです。</span><span class="sxs-lookup"><span data-stu-id="20ee2-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="20ee2-109">適切な暗号化キー (パスワードなど) を持つ担当者は、暗号化を解除したり、データ回復を実行したりできます。</span><span class="sxs-lookup"><span data-stu-id="20ee2-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <a name="enable-device-encryption-using-mdm"></a><span data-ttu-id="20ee2-110">MDM を使ってデバイスの暗号化を有効にする</span><span class="sxs-lookup"><span data-stu-id="20ee2-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="20ee2-111">Mobile デバイス管理 (MDM) プロバイダーを使用して、デバイスの暗号化を必要とするポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="20ee2-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="20ee2-112">使用するポリシーは、ポリシー CSP [の Security/RequireDeviceEncryption](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) 設定です。</span><span class="sxs-lookup"><span data-stu-id="20ee2-112">The policy to use is the [Security/RequireDeviceEncryption setting](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="20ee2-113">デバイスの暗号化を有効にする手順については、Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="20ee2-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="20ee2-114">他の MDM ツールについては、MDM プロバイダーのドキュメントで手順をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="20ee2-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="20ee2-115">MDM プロバイダーでデバイス暗号化のカスタム URI が必要な場合は、次の構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="20ee2-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="20ee2-116">**名前**: 任意の名前</span><span class="sxs-lookup"><span data-stu-id="20ee2-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="20ee2-117">**説明**: 省略可能</span><span class="sxs-lookup"><span data-stu-id="20ee2-117">**Description**: optional</span></span>
- <span data-ttu-id="20ee2-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span><span class="sxs-lookup"><span data-stu-id="20ee2-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span></span>
- <span data-ttu-id="20ee2-119">**データ型**: 整数</span><span class="sxs-lookup"><span data-stu-id="20ee2-119">**Data type**: integer</span></span>
- <span data-ttu-id="20ee2-120">**値**: `1`</span><span class="sxs-lookup"><span data-stu-id="20ee2-120">**Value**: `1`</span></span>

## <a name="enable-device-encryption-using-a-provisioning-package"></a><span data-ttu-id="20ee2-121">プロビジョニング パッケージを使ってデバイスの暗号化を有効にする</span><span class="sxs-lookup"><span data-stu-id="20ee2-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="20ee2-122">プロビジョニング パッケージは、Windows 構成デザイナー ツールにより作成された、指定された構成をデバイスに適用するファイルです。</span><span class="sxs-lookup"><span data-stu-id="20ee2-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a><span data-ttu-id="20ee2-123">Holographic エディションをアップグレードし、暗号化を有効にするWindowsパッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="20ee2-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="20ee2-124">HoloLens 用プロビジョニング パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="20ee2-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="20ee2-125">[ランタイム設定 **] [**  >  **ポリシー セキュリティ] に**  >  **移動** し、 **[RequireDeviceEncryption] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="20ee2-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![[はい] に構成されているデバイスの暗号化の設定が必要](images/device-encryption.png)

1. <span data-ttu-id="20ee2-127">Commercial Suite を購入するときに提供された XML ライセンス ファイルを見つける。</span><span class="sxs-lookup"><span data-stu-id="20ee2-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="20ee2-128">Commercial Suite の購入時に提供された XML ライセンス ファイルを参照して選びます。</span><span class="sxs-lookup"><span data-stu-id="20ee2-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="20ee2-129">[プロビジョニング パッケージでは追加の設定](hololens-provisioning.md)を構成できます。</span><span class="sxs-lookup"><span data-stu-id="20ee2-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="20ee2-130">**[ファイル]** メニューの **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20ee2-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="20ee2-131">プロジェクト ファイルに機密情報が含まれている可能性があるという警告を読み **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="20ee2-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="20ee2-132">プロビジョニング パッケージをビルドするときに、プロジェクト ファイルとプロビジョニング パッケージ (.ppkg) ファイルに機密情報を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="20ee2-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="20ee2-133">.ppkg ファイルは暗号化するかどうかを選べますが、プロジェクト ファイルは暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="20ee2-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="20ee2-134">プロジェクト ファイルは安全な場所に格納し、不要になったらプロジェクト ファイルを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20ee2-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="20ee2-135">**[エクスポート]** メニューの **[プロビジョニング パッケージ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20ee2-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="20ee2-136">[ **所有者]** **を [IT 管理者**] に変更します。これにより、このプロビジョニング パッケージの優先順位が、他のソースからこのデバイスに適用されるプロビジョニング パッケージよりも高く設定され、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="20ee2-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="20ee2-137">**[パッケージのバージョン]** の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="20ee2-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="20ee2-138">既存のパッケージに変更を加えてバージョン番号を変更することで、以前に適用されたパッケージを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="20ee2-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="20ee2-139">**[プロビジョニング パッケージのセキュリティ情報の選択]** で、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20ee2-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="20ee2-140">**[次へ]** をクリックし、ビルドしたプロビジョニング パッケージの出力先を指定します。</span><span class="sxs-lookup"><span data-stu-id="20ee2-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="20ee2-141">既定では、Windows ICD はプロジェクト フォルダーを出力先として使います。</span><span class="sxs-lookup"><span data-stu-id="20ee2-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="20ee2-142">必要に応じて、 [参照] をクリックして既定の出力先を変更できます。</span><span class="sxs-lookup"><span data-stu-id="20ee2-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="20ee2-143">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20ee2-143">Click **Next**.</span></span>
1. <span data-ttu-id="20ee2-144">パッケージのビルドを開始するには、**[ビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20ee2-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="20ee2-145">ビルド ページにプロジェクト情報が表示され、進行状況バーでビルドの状態が示されます。</span><span class="sxs-lookup"><span data-stu-id="20ee2-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="20ee2-146">ビルドが完了したら、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20ee2-146">When the build completes, click **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="20ee2-147">HoloLens へのプロビジョニング パッケージの適用</span><span class="sxs-lookup"><span data-stu-id="20ee2-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="20ee2-148">USB 経由でデバイスを PC に接続してデバイスを起動しますが、初期セットアップ エクスペリエンスの **調整** ページ (青のボックスが表示された最初のページ) より先には進まないでください。</span><span class="sxs-lookup"><span data-stu-id="20ee2-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="20ee2-149">**[音量を下げる]** ボタンと **電源** ボタンを同時に短く押して離します。</span><span class="sxs-lookup"><span data-stu-id="20ee2-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="20ee2-150">HoloLens が PC のエクスプローラーにデバイスとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="20ee2-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="20ee2-151">エクスプローラーで、プロビジョニング パッケージ (.ppkg) をデバイス ストレージに ドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="20ee2-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="20ee2-152">**調整** ページが表示されている間に、もう一度 **[音量を下げる]** ボタンと **電源** ボタンを同時に短く押して離します。</span><span class="sxs-lookup"><span data-stu-id="20ee2-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="20ee2-153">パッケージを信頼して適用するかどうかを確認するメッセージがデバイスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="20ee2-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="20ee2-154">パッケージが信頼できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="20ee2-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="20ee2-155">パッケージが正常に適用されたかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="20ee2-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="20ee2-156">失敗した場合、パッケージを修正してもう一度試します。</span><span class="sxs-lookup"><span data-stu-id="20ee2-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="20ee2-157">成功した場合はデバイスのセットアップを続けます。</span><span class="sxs-lookup"><span data-stu-id="20ee2-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="20ee2-158">2016 年 8 月より前に購入したデバイスの場合、プロビジョニング パッケージを適用するには、Microsoft アカウントを使ってデバイスにサインインして最新の OS 更新プログラムを入手し、OS をリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="20ee2-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <a name="verify-device-encryption"></a><span data-ttu-id="20ee2-159">デバイスの暗号化を確認する</span><span class="sxs-lookup"><span data-stu-id="20ee2-159">Verify device encryption</span></span>

<span data-ttu-id="20ee2-160">暗号化は、HoloLens で自動的に行われます。</span><span class="sxs-lookup"><span data-stu-id="20ee2-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="20ee2-161">デバイスの暗号化の状態を確認するには</span><span class="sxs-lookup"><span data-stu-id="20ee2-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="20ee2-162">[HoloLens] の **[設定**  >  System About]**に移動**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="20ee2-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="20ee2-163">デバイスが暗号化 **されている場合** は **、BitLocker** が有効になります。</span><span class="sxs-lookup"><span data-stu-id="20ee2-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![BitLocker が有効になっている画面について](images/about-encryption.png)
