---
title: 一般的なシナリオ–オフラインで安全な HoloLens 2
description: プロビジョニングによるオフラインでの安全な展開とアプリの展開。
keywords: HoloLens、管理、オフライン、オフラインセキュリティ
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
ms.openlocfilehash: d53f9ce19b020a866770b756dde6ab97b8331362
ms.sourcegitcommit: e6885d03c980b33dd0bab5c418cbd1892d5ff123
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "11080511"
---
# <span data-ttu-id="3c8f4-104">一般的なシナリオ–オフラインで安全な HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="3c8f4-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <span data-ttu-id="3c8f4-105">概要</span><span class="sxs-lookup"><span data-stu-id="3c8f4-105">Overview</span></span>
<span data-ttu-id="3c8f4-106">このガイドでは、セキュリティ保護された環境で使用するために HoloLens 2 をロックするサンプルプロビジョニングパッケージの適用に関するガイダンスを、次の制限に従って説明します。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>
-   <span data-ttu-id="3c8f4-107">WiFi を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-107">Disable WiFi.</span></span>
-   <span data-ttu-id="3c8f4-108">BlueTooth を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="3c8f4-109">マイクを無効にします。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-109">Disable Microphones.</span></span>
-   <span data-ttu-id="3c8f4-110">プロビジョニングパッケージを追加または削除できないようにします。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="3c8f4-111">どのユーザーも、上記の制限されたコンポーネントを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-111">No user can enable any of the above restricted components.</span></span>

## <span data-ttu-id="3c8f4-112">準備</span><span class="sxs-lookup"><span data-stu-id="3c8f4-112">Prepare</span></span> 
<span data-ttu-id="3c8f4-113">Windows 10 PC セットアップ</span><span class="sxs-lookup"><span data-stu-id="3c8f4-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="3c8f4-114">[最新の HoloLens 2 OS ファイル](https://aka.ms/hololens2download) を PC に直接ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="3c8f4-115">この構成のサポートは、ビルド19041.1117 以降に含まれています。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="3c8f4-116">[Microsoft Store から](https://www.microsoft.com/store/productId/9P74Z35SFRS8)PC に高度な回復コンパニオン (ARC) ツールをダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="3c8f4-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="3c8f4-117">Microsoft Store から PC に最新の [Windows 構成デザイナー (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) ツールをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="3c8f4-118">[プロジェクトファイルを含む OfflineSecureHL2_Sample フォルダーをダウンロード](https://aka.ms/HoloLensDocs-SecureOfflineSample) して、ppkg を構築します。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="3c8f4-119">[PPKG 展開用のオフラインのビジネスアプリケーションを](app-deploy-provisioning-package.md)準備します。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <span data-ttu-id="3c8f4-120">構成</span><span class="sxs-lookup"><span data-stu-id="3c8f4-120">Configure</span></span>
<span data-ttu-id="3c8f4-121">セキュリティで保護された構成プロビジョニングパッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="3c8f4-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="3c8f4-122">PC で WCD ツールを起動します。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="3c8f4-123">[ファイル] を選択し **、[プロジェクト > 開き**ます。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="3c8f4-124">以前に保存した OfflineSecureHL2_Sample フォルダーの場所に移動し、次のように選択します。 OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="3c8f4-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="3c8f4-125">プロジェクトが開き、利用可能なカスタマイズの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-125">The project should open and you should now have a list of Available Customizations:</span></span> 

   > [!div class="mx-imgBorder"]
   > ![WCD で開いた構成パッケージのスクリーンショット](images/offline-secure-sample-wcd.png)

<span data-ttu-id="3c8f4-127">このプロビジョニングパッケージで設定される構成:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-127">Configurations set in this provisioning package:</span></span>

|     <span data-ttu-id="3c8f4-128">項目</span><span class="sxs-lookup"><span data-stu-id="3c8f4-128">Item</span></span>                                                |     <span data-ttu-id="3c8f4-129">設定</span><span class="sxs-lookup"><span data-stu-id="3c8f4-129">Setting</span></span>                       |     <span data-ttu-id="3c8f4-130">説明</span><span class="sxs-lookup"><span data-stu-id="3c8f4-130">Description</span></span>                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="3c8f4-131">アカウント/ユーザー</span><span class="sxs-lookup"><span data-stu-id="3c8f4-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="3c8f4-132">ローカルユーザー名 & パスワード</span><span class="sxs-lookup"><span data-stu-id="3c8f4-132">Local User Name & Password</span></span>    |     <span data-ttu-id="3c8f4-133">これらのオフラインデバイスでは、デバイスのすべてのユーザーが1つのユーザー名とパスワードを設定して共有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
|     <span data-ttu-id="3c8f4-134">First Experience/HoloLens/SkipCalibration 調整</span><span class="sxs-lookup"><span data-stu-id="3c8f4-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="3c8f4-135">True</span><span class="sxs-lookup"><span data-stu-id="3c8f4-135">True</span></span>                          |     <span data-ttu-id="3c8f4-136">デバイスの初期セットアップ時のみ、調整をスキップする</span><span class="sxs-lookup"><span data-stu-id="3c8f4-136">Skips calibration during initial device setup only</span></span>                                                                             |
|     <span data-ttu-id="3c8f4-137">First Experience/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="3c8f4-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="3c8f4-138">True</span><span class="sxs-lookup"><span data-stu-id="3c8f4-138">True</span></span>                          |     <span data-ttu-id="3c8f4-139">初期デバイスのセットアップ中にデバイスのトレーニングをスキップします</span><span class="sxs-lookup"><span data-stu-id="3c8f4-139">Skips device training during initial device setup</span></span>                                                                              |
|     <span data-ttu-id="3c8f4-140">第1のエクスペリエンス/HoloLens/WiFi</span><span class="sxs-lookup"><span data-stu-id="3c8f4-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="3c8f4-141">True</span><span class="sxs-lookup"><span data-stu-id="3c8f4-141">True</span></span>                          |     <span data-ttu-id="3c8f4-142">初期デバイスのセットアップ中に Wi-fi 構成をスキップします</span><span class="sxs-lookup"><span data-stu-id="3c8f4-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
|     <span data-ttu-id="3c8f4-143">ポリシー/接続/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="3c8f4-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="3c8f4-144">なし</span><span class="sxs-lookup"><span data-stu-id="3c8f4-144">No</span></span>                            |     <span data-ttu-id="3c8f4-145">Bluetooth を無効にします</span><span class="sxs-lookup"><span data-stu-id="3c8f4-145">Disables Bluetooth</span></span>                                                                                                             |
|     <span data-ttu-id="3c8f4-146">ポリシー/エクスペリエンス/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="3c8f4-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="3c8f4-147">なし</span><span class="sxs-lookup"><span data-stu-id="3c8f4-147">No</span></span>                            |     <span data-ttu-id="3c8f4-148">Cortana を無効にします (マイクを無効にした後に発生する可能性のある問題を除去します)。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
|     <span data-ttu-id="3c8f4-149">Policies/MixedReality/マイクロ電話が無効になっています</span><span class="sxs-lookup"><span data-stu-id="3c8f4-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="3c8f4-150">あり</span><span class="sxs-lookup"><span data-stu-id="3c8f4-150">Yes</span></span>                           |     <span data-ttu-id="3c8f4-151">マイクを無効にします</span><span class="sxs-lookup"><span data-stu-id="3c8f4-151">Disables Microphone</span></span>                                                                                                            |
|     <span data-ttu-id="3c8f4-152">ポリシー/プライバシー/保管場所</span><span class="sxs-lookup"><span data-stu-id="3c8f4-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="3c8f4-153">強制拒否</span><span class="sxs-lookup"><span data-stu-id="3c8f4-153">Force deny</span></span>                    |     <span data-ttu-id="3c8f4-154">アプリが位置情報にアクセスしようとしないようにします (位置情報の追跡が無効になった後に発生する可能性のある問題を除去します)。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
|     <span data-ttu-id="3c8f4-155">ポリシー/プライバシー/アレイのアクセスマイク</span><span class="sxs-lookup"><span data-stu-id="3c8f4-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="3c8f4-156">強制拒否</span><span class="sxs-lookup"><span data-stu-id="3c8f4-156">Force deny</span></span>                    |     <span data-ttu-id="3c8f4-157">アプリがマイクにアクセスしようとしないようにします (マイクが無効になった後に発生する可能性のある問題を除去します)。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
|     <span data-ttu-id="3c8f4-158">ポリシー/セキュリティ/Allowaddのパッケージ</span><span class="sxs-lookup"><span data-stu-id="3c8f4-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="3c8f4-159">なし</span><span class="sxs-lookup"><span data-stu-id="3c8f4-159">No</span></span>                            |     <span data-ttu-id="3c8f4-160">ロックダウンポリシーを上書きしようとしている可能性があるプロビジョニングパッケージを、他の人が追加できないようにします。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
|     <span data-ttu-id="3c8f4-161">ポリシー/セキュリティ/Allowremoveプロビジョニングパッケージ</span><span class="sxs-lookup"><span data-stu-id="3c8f4-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="3c8f4-162">なし</span><span class="sxs-lookup"><span data-stu-id="3c8f4-162">No</span></span>                            |     <span data-ttu-id="3c8f4-163">ロックダウンされたプロビジョニングパッケージを他の人が削除できないようにします。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
|     <span data-ttu-id="3c8f4-164">Policies/System/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="3c8f4-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="3c8f4-165">なし</span><span class="sxs-lookup"><span data-stu-id="3c8f4-165">No</span></span>                            |     <span data-ttu-id="3c8f4-166">デバイスが位置情報データを追跡しないようにします。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-166">Prevents the device from trying to track location data.</span></span>                                                                        |
|     <span data-ttu-id="3c8f4-167">ポリシー/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="3c8f4-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="3c8f4-168">なし</span><span class="sxs-lookup"><span data-stu-id="3c8f4-168">No</span></span>                            |     <span data-ttu-id="3c8f4-169">Wi-fi を無効にします</span><span class="sxs-lookup"><span data-stu-id="3c8f4-169">Disables Wi-Fi</span></span>                                                                                                                 |

4. <span data-ttu-id="3c8f4-170">[ランタイムの設定] で、[**アカウント/ユーザー/ユーザー名: Holo/Password** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**</span></span> 
    - <span data-ttu-id="3c8f4-171">必要に応じて、パスワードとリセットを書き留めます。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-171">Note the password and reset if desired.</span></span>
5. <span data-ttu-id="3c8f4-172">UniversalAppInstall/UserContextApp に移動して、これらのデバイスに展開する [LOB アプリを構成](app-deploy-provisioning-package.md) します。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![WCD にアプリを追加する場所のスクリーンショット。](images/offline-secure-sample-wcd-usercontextapp.png)

6. <span data-ttu-id="3c8f4-174">完了したら、[エクスポート] ボタンを選択し、プロビジョニングパッケージが作成されるまで、すべてのプロンプトに従います。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![WCD のこのパッケージの [エクスポート] ボタンのスクリーンショット。](images/offline-secure-sample-wcd-export.png)


## <span data-ttu-id="3c8f4-176">展開</span><span class="sxs-lookup"><span data-stu-id="3c8f4-176">Deploy</span></span>
1. <span data-ttu-id="3c8f4-177">USB ケーブルを使って、HL2 を Windows 10 PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="3c8f4-178">ARC ツールを起動し、[ **HoloLens 2** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. <span data-ttu-id="3c8f4-179">次の画面で、[ **パッケージの手動選択**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-179">On the next screen select **Manual package selection**.</span></span>
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. <span data-ttu-id="3c8f4-180">前にダウンロードした ffu ファイルに移動して、[ **開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-180">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="3c8f4-181">警告ページで [ **Continue**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-181">At the Warning page select **Continue**.</span></span>

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. <span data-ttu-id="3c8f4-182">[ARC] ツールが HoloLens 2 OS インストールを完了するまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-182">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="3c8f4-183">デバイスがインストールを完了して起動したら、PC からエクスプローラーに移動し、以前に保存した PPKG ファイルをデバイスフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-183">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![ファイルエクスプローラーウィンドウの PC の PPKG ファイル。](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="3c8f4-185">HoloLens 2 では、次のボタンのコンボを押してプロビジョニングパッケージを実行します。 [ **音量を下げる** ] と [ **電源ボタン]** を同時にタップします。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-185">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="3c8f4-186">プロビジョニングパッケージを適用するかどうかを確認するメッセージが表示されたら、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-186">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="3c8f4-187">プロビジョニングパッケージが完了したら、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-187">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="3c8f4-188">次に、共有のローカルアカウントとパスワードを使用して、デバイスにサインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-188">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <span data-ttu-id="3c8f4-189">保守</span><span class="sxs-lookup"><span data-stu-id="3c8f4-189">Maintain</span></span>
<span data-ttu-id="3c8f4-190">この構成では、上の手順を再起動して、ARC ツールを使ってデバイスを reflash し、新しい PPKG を適用して OS やアプリケーションの更新を行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3c8f4-190">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span> 

