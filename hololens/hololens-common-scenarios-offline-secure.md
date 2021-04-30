---
title: 一般的なシナリオ– Offline Secure HoloLens 2
description: HoloLens デバイスのプロビジョニングを使用して、オフラインのセキュリティで保護された展開とアプリの展開シナリオをセットアップする方法について説明します。
keywords: HoloLens、管理、オフライン、オフラインのセキュリティ
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
ms.openlocfilehash: 7eb084d3de222581fd2b97eaa1c1e2812310810c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309125"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="3cdf6-104">一般的なシナリオ– Offline Secure HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="3cdf6-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="3cdf6-105">概要</span><span class="sxs-lookup"><span data-stu-id="3cdf6-105">Overview</span></span>

<span data-ttu-id="3cdf6-106">このガイドでは、セキュリティで保護された環境で使用するために HoloLens 2 をロックダウンするサンプルプロビジョニングパッケージを適用するためのガイダンスを提供します。次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="3cdf6-107">WiFi を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-107">Disable WiFi.</span></span>
-   <span data-ttu-id="3cdf6-108">BlueTooth を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="3cdf6-109">マイクを無効にします。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-109">Disable Microphones.</span></span>
-   <span data-ttu-id="3cdf6-110">プロビジョニングパッケージを追加または削除できないようにします。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="3cdf6-111">上記の制限されたコンポーネントをユーザーが有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-111">No user can enable any of the above restricted components.</span></span>

## <a name="prepare"></a><span data-ttu-id="3cdf6-112">準備</span><span class="sxs-lookup"><span data-stu-id="3cdf6-112">Prepare</span></span>

<span data-ttu-id="3cdf6-113">Windows 10 PC セットアップ</span><span class="sxs-lookup"><span data-stu-id="3cdf6-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="3cdf6-114">[最新の HoloLens 2 OS ファイル](https://aka.ms/hololens2download) を PC に直接ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="3cdf6-115">この構成のサポートは、ビルド19041.1117 以降に含まれています。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="3cdf6-116">[Microsoft Store から](https://www.microsoft.com/store/productId/9P74Z35SFRS8)PC に高度な回復コンパニオン (ARC) ツールをダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="3cdf6-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="3cdf6-117">Microsoft Store から PC に最新の [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) ツールをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="3cdf6-118">[OfflineSecureHL2_Sample フォルダーとプロジェクトファイルをダウンロード](https://aka.ms/HoloLensDocs-SecureOfflineSample) して、ppkg をビルドします。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="3cdf6-119">[PPKG 展開用のオフライン基幹業務アプリケーションを](app-deploy-provisioning-package.md)準備します。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="3cdf6-120">構成</span><span class="sxs-lookup"><span data-stu-id="3cdf6-120">Configure</span></span>

<span data-ttu-id="3cdf6-121">セキュリティで保護された構成プロビジョニングパッケージを構築する</span><span class="sxs-lookup"><span data-stu-id="3cdf6-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="3cdf6-122">PC で WCD ツールを起動します。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="3cdf6-123">[ **ファイル] > [プロジェクトを開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="3cdf6-124">以前に保存した OfflineSecureHL2_Sample フォルダーの場所に移動し、次のように選択し OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="3cdf6-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="3cdf6-125">プロジェクトが開き、利用可能なカスタマイズの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-125">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3cdf6-126">![WCD で開かれている構成パッケージのスクリーンショット](images/offline-secure-sample-wcd.png)</span><span class="sxs-lookup"><span data-stu-id="3cdf6-126">![Screenshot of the configuration package open in WCD](images/offline-secure-sample-wcd.png)</span></span>

   <span data-ttu-id="3cdf6-127">このプロビジョニングパッケージで設定される構成:</span><span class="sxs-lookup"><span data-stu-id="3cdf6-127">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="3cdf6-128">アイテム</span><span class="sxs-lookup"><span data-stu-id="3cdf6-128">Item</span></span>                                                |     <span data-ttu-id="3cdf6-129">設定</span><span class="sxs-lookup"><span data-stu-id="3cdf6-129">Setting</span></span>                       |     <span data-ttu-id="3cdf6-130">説明</span><span class="sxs-lookup"><span data-stu-id="3cdf6-130">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="3cdf6-131">アカウント/ユーザー</span><span class="sxs-lookup"><span data-stu-id="3cdf6-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="3cdf6-132">ローカルユーザー名 & パスワード</span><span class="sxs-lookup"><span data-stu-id="3cdf6-132">Local User Name & Password</span></span>    |     <span data-ttu-id="3cdf6-133">これらのオフラインデバイスでは、デバイスのすべてのユーザーが1つのユーザー名とパスワードを設定して共有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="3cdf6-134">最初のエクスペリエンス/HoloLens/SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="3cdf6-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="3cdf6-135">正しい</span><span class="sxs-lookup"><span data-stu-id="3cdf6-135">True</span></span>                          |     <span data-ttu-id="3cdf6-136">初期デバイスのセットアップ中のみ調整をスキップします</span><span class="sxs-lookup"><span data-stu-id="3cdf6-136">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="3cdf6-137">最初の経験/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="3cdf6-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="3cdf6-138">正しい</span><span class="sxs-lookup"><span data-stu-id="3cdf6-138">True</span></span>                          |     <span data-ttu-id="3cdf6-139">初期デバイスのセットアップ中にデバイストレーニングをスキップします</span><span class="sxs-lookup"><span data-stu-id="3cdf6-139">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="3cdf6-140">最初のエクスペリエンス/HoloLens/WiFi</span><span class="sxs-lookup"><span data-stu-id="3cdf6-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="3cdf6-141">正しい</span><span class="sxs-lookup"><span data-stu-id="3cdf6-141">True</span></span>                          |     <span data-ttu-id="3cdf6-142">初期デバイスのセットアップ中に Wi-Fi 構成をスキップします</span><span class="sxs-lookup"><span data-stu-id="3cdf6-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="3cdf6-143">ポリシー/接続/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="3cdf6-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="3cdf6-144">いいえ</span><span class="sxs-lookup"><span data-stu-id="3cdf6-144">No</span></span>                            |     <span data-ttu-id="3cdf6-145">Bluetooth を無効にします</span><span class="sxs-lookup"><span data-stu-id="3cdf6-145">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="3cdf6-146">ポリシー/エクスペリエンス/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="3cdf6-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="3cdf6-147">いいえ</span><span class="sxs-lookup"><span data-stu-id="3cdf6-147">No</span></span>                            |     <span data-ttu-id="3cdf6-148">Cortana を無効にします (マイクが無効になっているために発生する可能性のある問題を除去します)</span><span class="sxs-lookup"><span data-stu-id="3cdf6-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="3cdf6-149">Policies/MixedReality/マイクロ電話の無効化</span><span class="sxs-lookup"><span data-stu-id="3cdf6-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="3cdf6-150">はい</span><span class="sxs-lookup"><span data-stu-id="3cdf6-150">Yes</span></span>                           |     <span data-ttu-id="3cdf6-151">マイクを無効にする</span><span class="sxs-lookup"><span data-stu-id="3cdf6-151">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="3cdf6-152">ポリシー/プライバシー/保管場所</span><span class="sxs-lookup"><span data-stu-id="3cdf6-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="3cdf6-153">強制拒否</span><span class="sxs-lookup"><span data-stu-id="3cdf6-153">Force deny</span></span>                    |     <span data-ttu-id="3cdf6-154">アプリが場所データにアクセスできないようにします (場所の追跡が無効になっているために発生する可能性のある問題を回避するため)</span><span class="sxs-lookup"><span data-stu-id="3cdf6-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="3cdf6-155">ポリシー/プライバシー/お客様</span><span class="sxs-lookup"><span data-stu-id="3cdf6-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="3cdf6-156">強制拒否</span><span class="sxs-lookup"><span data-stu-id="3cdf6-156">Force deny</span></span>                    |     <span data-ttu-id="3cdf6-157">アプリがマイクにアクセスできないようにします (マイクが無効になったために発生する可能性のある問題を回避するため)</span><span class="sxs-lookup"><span data-stu-id="3cdf6-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="3cdf6-158">Policies/Security/Allowaddプロビジョニングパッケージ</span><span class="sxs-lookup"><span data-stu-id="3cdf6-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="3cdf6-159">いいえ</span><span class="sxs-lookup"><span data-stu-id="3cdf6-159">No</span></span>                            |     <span data-ttu-id="3cdf6-160">ロックダウンされたポリシーを上書きしようとする可能性があるプロビジョニングパッケージを誰も追加できないようにします。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="3cdf6-161">Policies/Security/Allowremoveプロビジョニングパッケージ</span><span class="sxs-lookup"><span data-stu-id="3cdf6-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="3cdf6-162">いいえ</span><span class="sxs-lookup"><span data-stu-id="3cdf6-162">No</span></span>                            |     <span data-ttu-id="3cdf6-163">このロックダウンされたプロビジョニングパッケージをすべてのユーザーが削除できないようにします。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="3cdf6-164">ポリシー/システム/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="3cdf6-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="3cdf6-165">いいえ</span><span class="sxs-lookup"><span data-stu-id="3cdf6-165">No</span></span>                            |     <span data-ttu-id="3cdf6-166">デバイスが場所データを追跡しないようにします。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-166">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="3cdf6-167">ポリシー/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="3cdf6-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="3cdf6-168">いいえ</span><span class="sxs-lookup"><span data-stu-id="3cdf6-168">No</span></span>                            |     <span data-ttu-id="3cdf6-169">無効化 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="3cdf6-169">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="3cdf6-170">[ランタイム設定] で、[ **Accounts/Users/UserName: Holo/Password**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="3cdf6-171">必要に応じて、パスワードとリセットを書き留めておきます。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-171">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="3cdf6-172">UniversalAppInstall/UserContextApp に移動し、これらのデバイスにデプロイする [LOB アプリを構成](app-deploy-provisioning-package.md) します。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3cdf6-173">![WCD でアプリを追加する場所のスクリーンショット。](images/offline-secure-sample-wcd-usercontextapp2.png)</span><span class="sxs-lookup"><span data-stu-id="3cdf6-173">![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span></span>

1. <span data-ttu-id="3cdf6-174">完了したら、[エクスポート] ボタンを選択し、プロビジョニングパッケージが作成されるまですべてのプロンプトに従います。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3cdf6-175">![WCD 内のこのパッケージの [エクスポート] ボタンのスクリーンショット。](images/offline-secure-sample-wcd-export.png)</span><span class="sxs-lookup"><span data-stu-id="3cdf6-175">![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)</span></span>

## <a name="deploy"></a><span data-ttu-id="3cdf6-176">配置</span><span class="sxs-lookup"><span data-stu-id="3cdf6-176">Deploy</span></span>

1. <span data-ttu-id="3cdf6-177">USB ケーブル経由で HL2 を Windows 10 PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="3cdf6-178">ARC ツールを起動し、[ **HoloLens 2** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![HoloLens 2 clean 更新初期画面](images/ARC2.png)

1. <span data-ttu-id="3cdf6-180">次の画面で、[ **パッケージの手動選択**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-180">On the next screen select **Manual package selection**.</span></span>

   ![HoloLens 2 弧情報画面](images/arc_device_info.png)

1. <span data-ttu-id="3cdf6-182">以前にダウンロードした ffu ファイルに移動し、[ **開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-182">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="3cdf6-183">[警告] ページで [ **続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-183">At the Warning page select **Continue**.</span></span>

   ![HoloLens 2 ARC 警告画面](images/arc_warning.png)

1. <span data-ttu-id="3cdf6-185">ARC ツールが HoloLens 2 OS のインストールを完了するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-185">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="3cdf6-186">デバイスのインストールが完了し、再起動されたら、PC からエクスプローラーに移動し、以前に保存した PPKG ファイルをデバイスフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-186">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3cdf6-187">![ファイルエクスプローラーウィンドウで、PC 上の PPKG ファイルを表示します。](images/offline-secure-file-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="3cdf6-187">![PPKG file on PC in File Explorer window.](images/offline-secure-file-explorer.png)</span></span>

1. <span data-ttu-id="3cdf6-188">HoloLens 2 で、次のボタンを押してプロビジョニングパッケージを実行します。 [ **ボリュームダウン** ] と [ **電源] ボタン** を同時にタップします。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-188">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="3cdf6-189">プロビジョニングパッケージを適用するかどうかを確認するメッセージが表示されたら、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-189">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="3cdf6-190">プロビジョニングパッケージが完了したら、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-190">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="3cdf6-191">次に、共有ローカルアカウントとパスワードを使用してデバイスにサインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-191">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="3cdf6-192">管理</span><span class="sxs-lookup"><span data-stu-id="3cdf6-192">Maintain</span></span>

<span data-ttu-id="3cdf6-193">この構成では、上記のプロセスを再起動し、デバイスを ARC ツールで更新し、新しい PPKG を適用して OS やアプリケーションに更新を加えることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3cdf6-193">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
