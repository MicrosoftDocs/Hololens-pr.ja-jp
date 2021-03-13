---
title: 一般的なシナリオ – オフラインの安全な HoloLens 2
description: HoloLens デバイスのプロビジョニングを使用してオフラインでセキュリティで保護された展開とアプリの展開シナリオをセットアップする方法について説明します。
keywords: HoloLens, 管理, オフライン, オフライン セキュア
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
ms.sourcegitcommit: 04b7e789fe69615a60571b769e13a01a9d7aee70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2021
ms.locfileid: "11407590"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="5dfb5-104">一般的なシナリオ – オフラインの安全な HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="5dfb5-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="5dfb5-105">概要</span><span class="sxs-lookup"><span data-stu-id="5dfb5-105">Overview</span></span>

<span data-ttu-id="5dfb5-106">このガイドでは、安全な環境で使用するために HoloLens 2 をロックダウンするプロビジョニング パッケージのサンプルを適用するためのガイダンスを以下の制限で提供します。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="5dfb5-107">WiFi を無効にします。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-107">Disable WiFi.</span></span>
-   <span data-ttu-id="5dfb5-108">BlueTooth を無効にします。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="5dfb5-109">マイクを無効にします。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-109">Disable Microphones.</span></span>
-   <span data-ttu-id="5dfb5-110">プロビジョニング パッケージの追加または削除を防止します。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="5dfb5-111">ユーザーは、上記の制限されたコンポーネントを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-111">No user can enable any of the above restricted components.</span></span>

## <a name="prepare"></a><span data-ttu-id="5dfb5-112">準備</span><span class="sxs-lookup"><span data-stu-id="5dfb5-112">Prepare</span></span>

<span data-ttu-id="5dfb5-113">Windows 10 PC セットアップ</span><span class="sxs-lookup"><span data-stu-id="5dfb5-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="5dfb5-114">[最新の HoloLens 2 OS ファイルを PC](https://aka.ms/hololens2download) に直接ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="5dfb5-115">この構成のサポートは、ビルド 19041.1117 以上に含まれています。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="5dfb5-116">[Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8)から PC に Advanced Recovery Companion(ARC) ツールをダウンロード/インストールする</span><span class="sxs-lookup"><span data-stu-id="5dfb5-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="5dfb5-117">Microsoft Store から PC に [最新の Windows 構成デザイナー (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) ツールをダウンロード/インストールします。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="5dfb5-118">[プロジェクト ファイルOfflineSecureHL2_Sampleフォルダーをダウンロードして](https://aka.ms/HoloLensDocs-SecureOfflineSample) 、PPKG をビルドします。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="5dfb5-119">[PPKG 展開用にオフラインの Line of Business アプリケーションを準備します](app-deploy-provisioning-package.md)。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="5dfb5-120">構成</span><span class="sxs-lookup"><span data-stu-id="5dfb5-120">Configure</span></span>

<span data-ttu-id="5dfb5-121">セキュリティで保護された構成プロビジョニング パッケージを構築する</span><span class="sxs-lookup"><span data-stu-id="5dfb5-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="5dfb5-122">PC で WCD ツールを起動します。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="5dfb5-123">[ **ファイル - ファイルを開>プロジェクト] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="5dfb5-124">以前に保存したフォルダーの場所に移動しOfflineSecureHL2_Sampleを選択しますOfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="5dfb5-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="5dfb5-125">プロジェクトが開き、利用可能なカスタマイズの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-125">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > ![WCD で開いている構成パッケージのスクリーンショット](images/offline-secure-sample-wcd.png)

   <span data-ttu-id="5dfb5-127">このプロビジョニング パッケージで設定された構成:</span><span class="sxs-lookup"><span data-stu-id="5dfb5-127">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="5dfb5-128">項目</span><span class="sxs-lookup"><span data-stu-id="5dfb5-128">Item</span></span>                                                |     <span data-ttu-id="5dfb5-129">設定</span><span class="sxs-lookup"><span data-stu-id="5dfb5-129">Setting</span></span>                       |     <span data-ttu-id="5dfb5-130">説明</span><span class="sxs-lookup"><span data-stu-id="5dfb5-130">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="5dfb5-131">アカウント/ユーザー</span><span class="sxs-lookup"><span data-stu-id="5dfb5-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="5dfb5-132">ローカル ユーザー名 & パスワード</span><span class="sxs-lookup"><span data-stu-id="5dfb5-132">Local User Name & Password</span></span>    |     <span data-ttu-id="5dfb5-133">これらのオフライン デバイスでは、1 つのユーザー名とパスワードをデバイスのすべてのユーザーが設定して共有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="5dfb5-134">First Experience / HoloLens / SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="5dfb5-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="5dfb5-135">True</span><span class="sxs-lookup"><span data-stu-id="5dfb5-135">True</span></span>                          |     <span data-ttu-id="5dfb5-136">初期デバイスのセットアップ時にのみ調整をスキップする</span><span class="sxs-lookup"><span data-stu-id="5dfb5-136">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="5dfb5-137">First Experience / HoloLens / SkipTraining</span><span class="sxs-lookup"><span data-stu-id="5dfb5-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="5dfb5-138">True</span><span class="sxs-lookup"><span data-stu-id="5dfb5-138">True</span></span>                          |     <span data-ttu-id="5dfb5-139">デバイスの初期セットアップ中にデバイストレーニングをスキップする</span><span class="sxs-lookup"><span data-stu-id="5dfb5-139">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="5dfb5-140">First Experience / HoloLens / WiFi</span><span class="sxs-lookup"><span data-stu-id="5dfb5-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="5dfb5-141">True</span><span class="sxs-lookup"><span data-stu-id="5dfb5-141">True</span></span>                          |     <span data-ttu-id="5dfb5-142">デバイスの初期Wi-Fi時に設定をスキップする</span><span class="sxs-lookup"><span data-stu-id="5dfb5-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="5dfb5-143">ポリシー/接続/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="5dfb5-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="5dfb5-144">いいえ</span><span class="sxs-lookup"><span data-stu-id="5dfb5-144">No</span></span>                            |     <span data-ttu-id="5dfb5-145">無効にするBluetooth</span><span class="sxs-lookup"><span data-stu-id="5dfb5-145">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="5dfb5-146">ポリシー/エクスペリエンス/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="5dfb5-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="5dfb5-147">いいえ</span><span class="sxs-lookup"><span data-stu-id="5dfb5-147">No</span></span>                            |     <span data-ttu-id="5dfb5-148">Cortana を無効にします (マイクが無効になっているので、潜在的な問題を排除するため)</span><span class="sxs-lookup"><span data-stu-id="5dfb5-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="5dfb5-149">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="5dfb5-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="5dfb5-150">はい</span><span class="sxs-lookup"><span data-stu-id="5dfb5-150">Yes</span></span>                           |     <span data-ttu-id="5dfb5-151">マイクを無効にする</span><span class="sxs-lookup"><span data-stu-id="5dfb5-151">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="5dfb5-152">ポリシー/プライバシー/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="5dfb5-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="5dfb5-153">強制的に拒否する</span><span class="sxs-lookup"><span data-stu-id="5dfb5-153">Force deny</span></span>                    |     <span data-ttu-id="5dfb5-154">アプリが位置情報データにアクセスしようとするのを防ぐ (位置情報の追跡が無効になっているので、潜在的な問題を排除するため)</span><span class="sxs-lookup"><span data-stu-id="5dfb5-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="5dfb5-155">ポリシー/プライバシー/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="5dfb5-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="5dfb5-156">強制的に拒否する</span><span class="sxs-lookup"><span data-stu-id="5dfb5-156">Force deny</span></span>                    |     <span data-ttu-id="5dfb5-157">アプリがマイクにアクセスしようとするのを防ぐ (マイクが無効になっているので、潜在的な問題を排除するため)</span><span class="sxs-lookup"><span data-stu-id="5dfb5-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="5dfb5-158">ポリシー/セキュリティ/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="5dfb5-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="5dfb5-159">いいえ</span><span class="sxs-lookup"><span data-stu-id="5dfb5-159">No</span></span>                            |     <span data-ttu-id="5dfb5-160">ロックダウン ポリシーを上書きしようとする可能性があるプロビジョニング パッケージを追加するユーザーを防止します。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="5dfb5-161">Policies/Security/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="5dfb5-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="5dfb5-162">いいえ</span><span class="sxs-lookup"><span data-stu-id="5dfb5-162">No</span></span>                            |     <span data-ttu-id="5dfb5-163">このロックダウンプロビジョニング パッケージを削除するユーザーを防止します。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="5dfb5-164">ポリシー/システム/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="5dfb5-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="5dfb5-165">いいえ</span><span class="sxs-lookup"><span data-stu-id="5dfb5-165">No</span></span>                            |     <span data-ttu-id="5dfb5-166">デバイスが位置情報の追跡を試みるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-166">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="5dfb5-167">ポリシー/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="5dfb5-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="5dfb5-168">いいえ</span><span class="sxs-lookup"><span data-stu-id="5dfb5-168">No</span></span>                            |     <span data-ttu-id="5dfb5-169">無効にするWi-Fi</span><span class="sxs-lookup"><span data-stu-id="5dfb5-169">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="5dfb5-170">[ランタイム設定] で、[ **アカウント/ ユーザー/ UserName: Holo / Password ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="5dfb5-171">パスワードをメモし、必要に応じてリセットします。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-171">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="5dfb5-172">UniversalAppInstall / UserContextApp に移動し、これらのデバイスに展開する [LOB](app-deploy-provisioning-package.md) アプリを構成します。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![WCD でアプリを追加する場所のスクリーンショット。](images/offline-secure-sample-wcd-usercontextapp2.png)

1. <span data-ttu-id="5dfb5-174">完了したら、[エクスポート] ボタンを選択し、プロビジョニング パッケージが作成されるまですべてのプロンプトに従います。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![WCD のこのパッケージの [エクスポート] ボタンのスクリーンショット。](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a><span data-ttu-id="5dfb5-176">展開</span><span class="sxs-lookup"><span data-stu-id="5dfb5-176">Deploy</span></span>

1. <span data-ttu-id="5dfb5-177">HL2 を USB ケーブルで Windows 10 PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="5dfb5-178">ARC ツールを起動し **、[HoloLens 2] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="5dfb5-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![HoloLens 2 クリーン 再フラッシュの初期画面](images/ARC2.png)

1. <span data-ttu-id="5dfb5-180">次の画面で、[手動パッケージの **選択] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-180">On the next screen select **Manual package selection**.</span></span>

   ![HoloLens 2 ARC 情報画面](images/arc_device_info.png)

1. <span data-ttu-id="5dfb5-182">以前にダウンロードした .ffu ファイルに移動し、[開く] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-182">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="5dfb5-183">[警告] ページで、[続行] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-183">At the Warning page select **Continue**.</span></span>

   ![HoloLens 2 ARC 警告画面](images/arc_warning.png)

1. <span data-ttu-id="5dfb5-185">ARC ツールが HoloLens 2 OS のインストールを完了するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-185">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="5dfb5-186">デバイスがインストールを完了し、バックアップを起動したら、PC からエクスプローラーに移動し、以前に保存した PPKG ファイルをデバイス フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-186">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![[エクスプローラー] ウィンドウの PC 上の PPKG ファイル。](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="5dfb5-188">HoloLens 2 で、次のボタン コンボを押してプロビジョニング パッケージ: **[音量** を下げ] と [ **電源** ボタン] を同時に実行します。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-188">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="5dfb5-189">プロビジョニング パッケージの適用を求めるメッセージが表示されます。[確認] を **選択します。**</span><span class="sxs-lookup"><span data-stu-id="5dfb5-189">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="5dfb5-190">プロビジョニング パッケージが完了したら **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-190">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="5dfb5-191">その後、共有ローカル アカウントとパスワードを使用してデバイスにサインインするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-191">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="5dfb5-192">保守</span><span class="sxs-lookup"><span data-stu-id="5dfb5-192">Maintain</span></span>

<span data-ttu-id="5dfb5-193">この構成では、上記のプロセスを再起動し、ARC ツールを使用してデバイスを再フラッシュし、新しい PPKG を適用して OS やアプリケーションを更新することを推奨します。</span><span class="sxs-lookup"><span data-stu-id="5dfb5-193">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
