---
title: 一般的なシナリオ – オフライン セキュリティHoloLens 2
description: HoloLens デバイスのプロビジョニングを使用して、オフラインでセキュリティで保護された展開とアプリの展開シナリオを設定する方法について説明します。
keywords: HoloLens, 管理, オフライン, オフライン セキュリティで保護
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397883"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="ae7ca-104">一般的なシナリオ – オフライン セキュリティHoloLens 2</span><span class="sxs-lookup"><span data-stu-id="ae7ca-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="ae7ca-105">概要</span><span class="sxs-lookup"><span data-stu-id="ae7ca-105">Overview</span></span>

<span data-ttu-id="ae7ca-106">このガイドでは、セキュリティで保護された環境で使用するためにHoloLens 2プロビジョニング パッケージのサンプルを適用するためのガイダンスを提供します。これには次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="ae7ca-107">WiFi を無効にします。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-107">Disable WiFi.</span></span>
-   <span data-ttu-id="ae7ca-108">BlueTooth を無効にします。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="ae7ca-109">マイクを無効にします。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-109">Disable Microphones.</span></span>
-   <span data-ttu-id="ae7ca-110">プロビジョニング パッケージの追加または削除を防止します。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="ae7ca-111">上記の制限付きコンポーネントを有効にできるユーザーはありません。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-111">No user can enable any of the above restricted components.</span></span>

<span data-ttu-id="ae7ca-112">[![オフライン でセキュリティで保護されたシナリオ ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ae7ca-112">[ ![Offline Secure scenario](./images/deployment-guides-revised-scenario-c-01.png) ](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

## <a name="prepare"></a><span data-ttu-id="ae7ca-113">準備</span><span class="sxs-lookup"><span data-stu-id="ae7ca-113">Prepare</span></span>

<span data-ttu-id="ae7ca-114">Windows 10 PC のセットアップ</span><span class="sxs-lookup"><span data-stu-id="ae7ca-114">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="ae7ca-115">[最新の HOLOLENS 2 OS ファイルを PC](https://aka.ms/hololens2download) に直接ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-115">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="ae7ca-116">この構成のサポートは、ビルド 19041.1117 以上に含まれています。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-116">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="ae7ca-117">コンピューターから PC への Advanced Recovery Companion(ARC) [Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) ダウンロード/インストールする</span><span class="sxs-lookup"><span data-stu-id="ae7ca-117">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="ae7ca-118">最新の Windows [構成デザイナー (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) ツールをダウンロードして、PC Microsoft Storeインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-118">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="ae7ca-119">[プロジェクト ファイルOfflineSecureHL2_Sampleフォルダーをダウンロードして](https://aka.ms/HoloLensDocs-SecureOfflineSample) 、PPKG をビルドします。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-119">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="ae7ca-120">オフラインの [Line of Business アプリケーションを PPKG デプロイ用に準備します](app-deploy-provisioning-package.md)。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-120">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="ae7ca-121">構成</span><span class="sxs-lookup"><span data-stu-id="ae7ca-121">Configure</span></span>

<span data-ttu-id="ae7ca-122">セキュリティで保護された構成プロビジョニング パッケージをビルドする</span><span class="sxs-lookup"><span data-stu-id="ae7ca-122">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="ae7ca-123">PC で WCD ツールを起動します。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-123">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="ae7ca-124">[ **ファイル] > [プロジェクトを開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-124">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="ae7ca-125">以前に保存した OfflineSecureHL2_Sample フォルダーの場所に移動し、次のように選択し OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="ae7ca-125">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="ae7ca-126">プロジェクトが開き、利用可能なカスタマイズの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-126">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ae7ca-127">![WCD で開かれている構成パッケージのスクリーンショット](images/offline-secure-sample-wcd.png)</span><span class="sxs-lookup"><span data-stu-id="ae7ca-127">![Screenshot of the configuration package open in WCD](images/offline-secure-sample-wcd.png)</span></span>

   <span data-ttu-id="ae7ca-128">このプロビジョニングパッケージで設定される構成:</span><span class="sxs-lookup"><span data-stu-id="ae7ca-128">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="ae7ca-129">Item</span><span class="sxs-lookup"><span data-stu-id="ae7ca-129">Item</span></span>                                                |     <span data-ttu-id="ae7ca-130">設定</span><span class="sxs-lookup"><span data-stu-id="ae7ca-130">Setting</span></span>                       |     <span data-ttu-id="ae7ca-131">Description</span><span class="sxs-lookup"><span data-stu-id="ae7ca-131">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="ae7ca-132">アカウント/ユーザー</span><span class="sxs-lookup"><span data-stu-id="ae7ca-132">Accounts / Users</span></span>                                    |     <span data-ttu-id="ae7ca-133">ローカルユーザー名 & パスワード</span><span class="sxs-lookup"><span data-stu-id="ae7ca-133">Local User Name & Password</span></span>    |     <span data-ttu-id="ae7ca-134">これらのオフラインデバイスでは、デバイスのすべてのユーザーが1つのユーザー名とパスワードを設定して共有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-134">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="ae7ca-135">最初のエクスペリエンス/HoloLens/SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="ae7ca-135">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="ae7ca-136">○</span><span class="sxs-lookup"><span data-stu-id="ae7ca-136">True</span></span>                          |     <span data-ttu-id="ae7ca-137">初期デバイスのセットアップ中のみ調整をスキップします</span><span class="sxs-lookup"><span data-stu-id="ae7ca-137">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="ae7ca-138">最初の経験/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="ae7ca-138">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="ae7ca-139">○</span><span class="sxs-lookup"><span data-stu-id="ae7ca-139">True</span></span>                          |     <span data-ttu-id="ae7ca-140">初期デバイスのセットアップ中にデバイストレーニングをスキップします</span><span class="sxs-lookup"><span data-stu-id="ae7ca-140">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="ae7ca-141">最初のエクスペリエンス/HoloLens/WiFi</span><span class="sxs-lookup"><span data-stu-id="ae7ca-141">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="ae7ca-142">○</span><span class="sxs-lookup"><span data-stu-id="ae7ca-142">True</span></span>                          |     <span data-ttu-id="ae7ca-143">初期デバイスのセットアップ中に Wi-Fi 構成をスキップします</span><span class="sxs-lookup"><span data-stu-id="ae7ca-143">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="ae7ca-144">ポリシー/接続/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="ae7ca-144">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="ae7ca-145">No</span><span class="sxs-lookup"><span data-stu-id="ae7ca-145">No</span></span>                            |     <span data-ttu-id="ae7ca-146">Bluetooth を無効にします</span><span class="sxs-lookup"><span data-stu-id="ae7ca-146">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="ae7ca-147">ポリシー/エクスペリエンス/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="ae7ca-147">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="ae7ca-148">No</span><span class="sxs-lookup"><span data-stu-id="ae7ca-148">No</span></span>                            |     <span data-ttu-id="ae7ca-149">Cortana を無効にします (マイクが無効になっているために発生する可能性のある問題を除去します)</span><span class="sxs-lookup"><span data-stu-id="ae7ca-149">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="ae7ca-150">Policies/MixedReality/マイクロ電話の無効化</span><span class="sxs-lookup"><span data-stu-id="ae7ca-150">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="ae7ca-151">Yes</span><span class="sxs-lookup"><span data-stu-id="ae7ca-151">Yes</span></span>                           |     <span data-ttu-id="ae7ca-152">マイクを無効にする</span><span class="sxs-lookup"><span data-stu-id="ae7ca-152">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="ae7ca-153">Policies/Privacy/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="ae7ca-153">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="ae7ca-154">強制的に拒否する</span><span class="sxs-lookup"><span data-stu-id="ae7ca-154">Force deny</span></span>                    |     <span data-ttu-id="ae7ca-155">アプリが位置情報データへのアクセスを試みるのを防ぐ (位置情報の追跡が無効になっているので、潜在的な問題を排除するため)</span><span class="sxs-lookup"><span data-stu-id="ae7ca-155">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="ae7ca-156">Policies/Privacy/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="ae7ca-156">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="ae7ca-157">強制的に拒否する</span><span class="sxs-lookup"><span data-stu-id="ae7ca-157">Force deny</span></span>                    |     <span data-ttu-id="ae7ca-158">アプリがマイクへのアクセスを試みるのを防ぐ (マイクが無効になっているので、潜在的な問題を排除するため)</span><span class="sxs-lookup"><span data-stu-id="ae7ca-158">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="ae7ca-159">Policies/Security/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="ae7ca-159">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="ae7ca-160">No</span><span class="sxs-lookup"><span data-stu-id="ae7ca-160">No</span></span>                            |     <span data-ttu-id="ae7ca-161">ロックダウンされたポリシーをオーバーライドしようとする可能性があるプロビジョニング パッケージを追加するユーザーを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-161">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="ae7ca-162">Policies/Security/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="ae7ca-162">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="ae7ca-163">No</span><span class="sxs-lookup"><span data-stu-id="ae7ca-163">No</span></span>                            |     <span data-ttu-id="ae7ca-164">このロックダウンされたプロビジョニング パッケージを削除するユーザーを防止します。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-164">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="ae7ca-165">Policies/System/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="ae7ca-165">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="ae7ca-166">No</span><span class="sxs-lookup"><span data-stu-id="ae7ca-166">No</span></span>                            |     <span data-ttu-id="ae7ca-167">デバイスが位置情報データの追跡を試みるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-167">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="ae7ca-168">Policies/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="ae7ca-168">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="ae7ca-169">No</span><span class="sxs-lookup"><span data-stu-id="ae7ca-169">No</span></span>                            |     <span data-ttu-id="ae7ca-170">を無効Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="ae7ca-170">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="ae7ca-171">[ランタイム設定] で、[ **アカウント/ ユーザー / ユーザー名: Holo / パスワード ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-171">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="ae7ca-172">パスワードをメモし、必要に応じてリセットします。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-172">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="ae7ca-173">UniversalAppInstall / UserContextApp に移動し、これらのデバイスに展開する [LOB](app-deploy-provisioning-package.md) アプリを構成します。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-173">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ae7ca-174">![WCD でアプリを追加する場所のスクリーンショット。](images/offline-secure-sample-wcd-usercontextapp2.png)</span><span class="sxs-lookup"><span data-stu-id="ae7ca-174">![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span></span>

1. <span data-ttu-id="ae7ca-175">完了したら、[エクスポート] ボタンを選択し、プロビジョニング パッケージが作成されるまですべてのプロンプトに従います。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-175">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ae7ca-176">![WCD のこのパッケージの [エクスポート] ボタンのスクリーンショット。](images/offline-secure-sample-wcd-export.png)</span><span class="sxs-lookup"><span data-stu-id="ae7ca-176">![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)</span></span>

## <a name="deploy"></a><span data-ttu-id="ae7ca-177">デプロイ</span><span class="sxs-lookup"><span data-stu-id="ae7ca-177">Deploy</span></span>

1. <span data-ttu-id="ae7ca-178">USB ケーブル経由で HL2 を Windows 10 PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-178">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="ae7ca-179">ARC ツールを起動し、[ **HoloLens 2** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-179">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![HoloLens 2 clean 更新初期画面](images/ARC2.png)

1. <span data-ttu-id="ae7ca-181">次の画面で、[ **パッケージの手動選択**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-181">On the next screen select **Manual package selection**.</span></span>

   ![HoloLens 2 弧情報画面](images/arc_device_info.png)

1. <span data-ttu-id="ae7ca-183">以前にダウンロードした ffu ファイルに移動し、[ **開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-183">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="ae7ca-184">[警告] ページで [ **続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-184">At the Warning page select **Continue**.</span></span>

   ![HoloLens 2 ARC 警告画面](images/arc_warning.png)

1. <span data-ttu-id="ae7ca-186">ARC ツールが HoloLens 2 OS のインストールを完了するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-186">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="ae7ca-187">デバイスのインストールが完了し、再起動されたら、PC からエクスプローラーに移動し、以前に保存した PPKG ファイルをデバイスフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-187">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ae7ca-188">![ファイルエクスプローラーウィンドウで、PC 上の PPKG ファイルを表示します。](images/offline-secure-file-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="ae7ca-188">![PPKG file on PC in File Explorer window.](images/offline-secure-file-explorer.png)</span></span>

1. <span data-ttu-id="ae7ca-189">HoloLens 2 で、次のボタンを押してプロビジョニングパッケージを実行します。 [ **ボリュームダウン** ] と [ **電源] ボタン** を同時にタップします。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-189">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="ae7ca-190">プロビジョニングパッケージを適用するかどうかを確認するメッセージが表示されたら、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-190">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="ae7ca-191">プロビジョニングパッケージが完了したら、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-191">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="ae7ca-192">次に、共有ローカルアカウントとパスワードを使用してデバイスにサインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-192">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="ae7ca-193">管理</span><span class="sxs-lookup"><span data-stu-id="ae7ca-193">Maintain</span></span>

<span data-ttu-id="ae7ca-194">この構成では、上記のプロセスを再起動し、デバイスを ARC ツールで更新し、新しい PPKG を適用して OS やアプリケーションに更新を加えることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ae7ca-194">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
