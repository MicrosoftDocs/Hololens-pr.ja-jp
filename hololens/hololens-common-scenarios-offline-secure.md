---
title: 一般的なシナリオ – オフラインセキュア HoloLens 2
description: HoloLens デバイスのプロビジョニングを使用して、オフラインでセキュリティ保護された展開とアプリの展開シナリオをセットアップする方法について説明します。
keywords: HoloLens, 管理, オフライン, オフラインセキュア
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
ms.openlocfilehash: 03003995f1e63708652955e6217e506d53555c1b
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283418"
---
# <span data-ttu-id="69e13-104">一般的なシナリオ – オフラインセキュア HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="69e13-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <span data-ttu-id="69e13-105">概要</span><span class="sxs-lookup"><span data-stu-id="69e13-105">Overview</span></span>

<span data-ttu-id="69e13-106">このガイドでは、次の制限がある安全な環境で使用するために HoloLens 2 をロックダウンするプロビジョニング パッケージのサンプルを適用するためのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="69e13-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>
-   <span data-ttu-id="69e13-107">WiFi を無効にします。</span><span class="sxs-lookup"><span data-stu-id="69e13-107">Disable WiFi.</span></span>
-   <span data-ttu-id="69e13-108">BlueTooth を無効にします。</span><span class="sxs-lookup"><span data-stu-id="69e13-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="69e13-109">マイクを無効にします。</span><span class="sxs-lookup"><span data-stu-id="69e13-109">Disable Microphones.</span></span>
-   <span data-ttu-id="69e13-110">プロビジョニング パッケージの追加または削除を防止します。</span><span class="sxs-lookup"><span data-stu-id="69e13-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="69e13-111">上記の制限付きコンポーネントを有効にできるユーザーはありません。</span><span class="sxs-lookup"><span data-stu-id="69e13-111">No user can enable any of the above restricted components.</span></span>

## <span data-ttu-id="69e13-112">準備</span><span class="sxs-lookup"><span data-stu-id="69e13-112">Prepare</span></span>

<span data-ttu-id="69e13-113">Windows 10 PC のセットアップ</span><span class="sxs-lookup"><span data-stu-id="69e13-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="69e13-114">[最新の HoloLens 2 OS](https://aka.ms/hololens2download) ファイルを PC に直接ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="69e13-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="69e13-115">この構成のサポートは、ビルド 19041.1117 以上に含まれています。</span><span class="sxs-lookup"><span data-stu-id="69e13-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="69e13-116">[Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8)から PC に Advanced Recovery Companion(ARC) ツールをダウンロード/インストールする</span><span class="sxs-lookup"><span data-stu-id="69e13-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="69e13-117">Microsoft Store から PC に [最新の Windows 構成デザイナー (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) ツールをダウンロード/インストールします。</span><span class="sxs-lookup"><span data-stu-id="69e13-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="69e13-118">[PPKG をOfflineSecureHL2_Sampleプロジェクト ファイルを含む](https://aka.ms/HoloLensDocs-SecureOfflineSample) フォルダーをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="69e13-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="69e13-119">[PPKG 展開用にオフラインの Line of Business アプリケーションを準備します](app-deploy-provisioning-package.md)。</span><span class="sxs-lookup"><span data-stu-id="69e13-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <span data-ttu-id="69e13-120">構成</span><span class="sxs-lookup"><span data-stu-id="69e13-120">Configure</span></span>

<span data-ttu-id="69e13-121">セキュリティで保護された構成プロビジョニング パッケージをビルドする</span><span class="sxs-lookup"><span data-stu-id="69e13-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="69e13-122">PC で WCD ツールを起動します。</span><span class="sxs-lookup"><span data-stu-id="69e13-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="69e13-123">Select **File -> Open project**.</span><span class="sxs-lookup"><span data-stu-id="69e13-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="69e13-124">以前に保存したフォルダーの場所にOfflineSecureHL2_Sampleし、次のオプションを選択OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="69e13-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="69e13-125">プロジェクトが開き、使用可能なカスタマイズの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="69e13-125">The project should open and you should now have a list of Available Customizations:</span></span> 

   > [!div class="mx-imgBorder"]
   > ![WCD で開いている構成パッケージのスクリーンショット](images/offline-secure-sample-wcd.png)

<span data-ttu-id="69e13-127">このプロビジョニング パッケージで設定された構成:</span><span class="sxs-lookup"><span data-stu-id="69e13-127">Configurations set in this provisioning package:</span></span>

|     <span data-ttu-id="69e13-128">項目</span><span class="sxs-lookup"><span data-stu-id="69e13-128">Item</span></span>                                                |     <span data-ttu-id="69e13-129">設定</span><span class="sxs-lookup"><span data-stu-id="69e13-129">Setting</span></span>                       |     <span data-ttu-id="69e13-130">説明</span><span class="sxs-lookup"><span data-stu-id="69e13-130">Description</span></span>                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="69e13-131">アカウント/ユーザー</span><span class="sxs-lookup"><span data-stu-id="69e13-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="69e13-132">ローカル ユーザー名& パスワード</span><span class="sxs-lookup"><span data-stu-id="69e13-132">Local User Name & Password</span></span>    |     <span data-ttu-id="69e13-133">これらのオフライン デバイスでは、デバイスのすべてのユーザーが 1 つのユーザー名とパスワードを設定して共有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69e13-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
|     <span data-ttu-id="69e13-134">First Experience / HoloLens / SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="69e13-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="69e13-135">True</span><span class="sxs-lookup"><span data-stu-id="69e13-135">True</span></span>                          |     <span data-ttu-id="69e13-136">初期デバイスのセットアップ時にのみ調整をスキップします</span><span class="sxs-lookup"><span data-stu-id="69e13-136">Skips calibration during initial device setup only</span></span>                                                                             |
|     <span data-ttu-id="69e13-137">First Experience / HoloLens / SkipTraining</span><span class="sxs-lookup"><span data-stu-id="69e13-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="69e13-138">True</span><span class="sxs-lookup"><span data-stu-id="69e13-138">True</span></span>                          |     <span data-ttu-id="69e13-139">デバイスの初期セットアップ中にデバイストレーニングをスキップします</span><span class="sxs-lookup"><span data-stu-id="69e13-139">Skips device training during initial device setup</span></span>                                                                              |
|     <span data-ttu-id="69e13-140">First Experience / HoloLens / WiFi</span><span class="sxs-lookup"><span data-stu-id="69e13-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="69e13-141">True</span><span class="sxs-lookup"><span data-stu-id="69e13-141">True</span></span>                          |     <span data-ttu-id="69e13-142">デバイスの初期Wi-Fi構成をスキップします。</span><span class="sxs-lookup"><span data-stu-id="69e13-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
|     <span data-ttu-id="69e13-143">Policies/Connectivity/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="69e13-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="69e13-144">なし</span><span class="sxs-lookup"><span data-stu-id="69e13-144">No</span></span>                            |     <span data-ttu-id="69e13-145">無効Bluetooth</span><span class="sxs-lookup"><span data-stu-id="69e13-145">Disables Bluetooth</span></span>                                                                                                             |
|     <span data-ttu-id="69e13-146">Policies/Experience/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="69e13-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="69e13-147">なし</span><span class="sxs-lookup"><span data-stu-id="69e13-147">No</span></span>                            |     <span data-ttu-id="69e13-148">Cortana を無効にします (マイクが無効になっているので潜在的な問題を排除するため)</span><span class="sxs-lookup"><span data-stu-id="69e13-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
|     <span data-ttu-id="69e13-149">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="69e13-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="69e13-150">あり</span><span class="sxs-lookup"><span data-stu-id="69e13-150">Yes</span></span>                           |     <span data-ttu-id="69e13-151">マイクを無効にする</span><span class="sxs-lookup"><span data-stu-id="69e13-151">Disables Microphone</span></span>                                                                                                            |
|     <span data-ttu-id="69e13-152">Policies/Privacy/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="69e13-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="69e13-153">強制的に拒否する</span><span class="sxs-lookup"><span data-stu-id="69e13-153">Force deny</span></span>                    |     <span data-ttu-id="69e13-154">アプリが位置情報データにアクセスしようとするのを防ぐ (位置情報の追跡が無効になっているので潜在的な問題を排除するため)</span><span class="sxs-lookup"><span data-stu-id="69e13-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
|     <span data-ttu-id="69e13-155">Policies/Privacy/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="69e13-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="69e13-156">強制的に拒否する</span><span class="sxs-lookup"><span data-stu-id="69e13-156">Force deny</span></span>                    |     <span data-ttu-id="69e13-157">アプリがマイクにアクセスしようとするのを防ぐ (マイクが無効になっているので潜在的な問題を排除するため)</span><span class="sxs-lookup"><span data-stu-id="69e13-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
|     <span data-ttu-id="69e13-158">Policies/Security/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="69e13-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="69e13-159">なし</span><span class="sxs-lookup"><span data-stu-id="69e13-159">No</span></span>                            |     <span data-ttu-id="69e13-160">ロックダウンされたポリシーを上書きしようとする可能性があるプロビジョニング パッケージをだれも追加しません。</span><span class="sxs-lookup"><span data-stu-id="69e13-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
|     <span data-ttu-id="69e13-161">Policies/Security/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="69e13-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="69e13-162">なし</span><span class="sxs-lookup"><span data-stu-id="69e13-162">No</span></span>                            |     <span data-ttu-id="69e13-163">ロックダウンされたこのプロビジョニング パッケージを削除するユーザーを防止します。</span><span class="sxs-lookup"><span data-stu-id="69e13-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
|     <span data-ttu-id="69e13-164">Policies/System/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="69e13-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="69e13-165">なし</span><span class="sxs-lookup"><span data-stu-id="69e13-165">No</span></span>                            |     <span data-ttu-id="69e13-166">デバイスが位置情報データの追跡を試みない。</span><span class="sxs-lookup"><span data-stu-id="69e13-166">Prevents the device from trying to track location data.</span></span>                                                                        |
|     <span data-ttu-id="69e13-167">Policies/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="69e13-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="69e13-168">なし</span><span class="sxs-lookup"><span data-stu-id="69e13-168">No</span></span>                            |     <span data-ttu-id="69e13-169">無効Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="69e13-169">Disables Wi-Fi</span></span>                                                                                                                 |

4. <span data-ttu-id="69e13-170">[実行時の設定] で、[ **アカウント/ ユーザー/ ユーザー名: Holo / パスワード] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="69e13-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**</span></span> 
    - <span data-ttu-id="69e13-171">パスワードをメモし、必要に応じてリセットします。</span><span class="sxs-lookup"><span data-stu-id="69e13-171">Note the password and reset if desired.</span></span>
5. <span data-ttu-id="69e13-172">UniversalAppInstall / UserContextApp に移動し、これらのデバイスに展開する [LOB](app-deploy-provisioning-package.md) アプリを構成します。</span><span class="sxs-lookup"><span data-stu-id="69e13-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![WCD でアプリを追加する場所のスクリーンショット。](images/offline-secure-sample-wcd-usercontextapp.png)

6. <span data-ttu-id="69e13-174">完了したら、[エクスポート] ボタンを選択し、プロビジョニング パッケージが作成されるまですべてのプロンプトに従います。</span><span class="sxs-lookup"><span data-stu-id="69e13-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![WCD のこのパッケージの [エクスポート] ボタンのスクリーンショット。](images/offline-secure-sample-wcd-export.png)


## <span data-ttu-id="69e13-176">展開</span><span class="sxs-lookup"><span data-stu-id="69e13-176">Deploy</span></span>

1. <span data-ttu-id="69e13-177">HL2 を USB ケーブルで Windows 10 PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="69e13-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="69e13-178">ARC ツールを起動して **HoloLens 2 を選択する**</span><span class="sxs-lookup"><span data-stu-id="69e13-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. <span data-ttu-id="69e13-179">On the next screen select **Manual package selection**.</span><span class="sxs-lookup"><span data-stu-id="69e13-179">On the next screen select **Manual package selection**.</span></span>
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. <span data-ttu-id="69e13-180">以前にダウンロードした .ffu ファイルに移動し、[開く] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="69e13-180">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="69e13-181">[警告] ページで、[続行] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="69e13-181">At the Warning page select **Continue**.</span></span>

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. <span data-ttu-id="69e13-182">ARC ツールが HoloLens 2 OS のインストールを完了するまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="69e13-182">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="69e13-183">デバイスがインストールを完了して起動し、バックアップを起動したら、PC からエクスプローラーに移動し、以前に保存した PPKG ファイルをデバイス フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="69e13-183">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![エクスプローラー ウィンドウの PC 上の PPKG ファイル。](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="69e13-185">HoloLens 2 で、次のボタン コンボを押してプロビジョニング パッケージを\*\*\*\* 実行します。[音量を下げ] と [**電源**ボタン] を同時にタップします。</span><span class="sxs-lookup"><span data-stu-id="69e13-185">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="69e13-186">プロビジョニング パッケージを適用するように求めるメッセージが表示され、[確認] を選択 **します。**</span><span class="sxs-lookup"><span data-stu-id="69e13-186">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="69e13-187">プロビジョニング パッケージが完了したら **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="69e13-187">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="69e13-188">その後、共有ローカル アカウントとパスワードを使用してデバイスにサインインするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="69e13-188">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <span data-ttu-id="69e13-189">保守</span><span class="sxs-lookup"><span data-stu-id="69e13-189">Maintain</span></span>

<span data-ttu-id="69e13-190">この構成では、上記のプロセスを再起動し、ARC ツールでデバイスを再フラッシュし、新しい PPKG を適用して OS やアプリケーションを更新することを推奨します。</span><span class="sxs-lookup"><span data-stu-id="69e13-190">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span> 

