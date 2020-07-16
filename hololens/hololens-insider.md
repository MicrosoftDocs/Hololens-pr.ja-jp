---
title: Microsoft HoloLens の Insider Preview
description: 簡単に Insider ビルドを使い始めて、HoloLens の次の主要なオペレーティング システムの更新プログラムに対する貴重なフィードバックをご提供いただけます。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 6/29/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 5cdb7302aec5b37a5071f2192f7c8bc5df760ac7
ms.sourcegitcommit: 3db43bc4a007b10901d8edb045f66e1e299c57a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882429"
---
# <span data-ttu-id="9fc1f-103">Microsoft HoloLens の Insider Preview</span><span class="sxs-lookup"><span data-stu-id="9fc1f-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="9fc1f-104">HoloLens 用の最新の Insider Preview ビルドへようこそ!</span><span class="sxs-lookup"><span data-stu-id="9fc1f-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span>  <span data-ttu-id="9fc1f-105">簡単に使い始めて、HoloLens の次の主要なオペレーティング システムの更新プログラムに対する貴重なフィードバックをご提供いただけます。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-105">It's simple to get started and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

<span data-ttu-id="9fc1f-106">Windows insider がチャネルに移動するようになりました。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-106">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="9fc1f-107">**ファスト**リングは**Dev チャネル**になります。**スロー**リングは**ベータチャネル**になり、 **release preview** ring は**リリースプレビューチャネル**になります。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-107">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="9fc1f-108">マッピングの外観は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-108">Here is what that mapping looks like:</span></span>

![Windows Insider チャネルの説明](images/WindowsInsiderChannels.png)

<span data-ttu-id="9fc1f-110">詳細については、「 [Windows のブログエントリ](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-110">For more information: [Windows Blog entry](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)</span></span>

## <span data-ttu-id="9fc1f-111">Insider ビルドの受信の開始</span><span class="sxs-lookup"><span data-stu-id="9fc1f-111">Start receiving Insider builds</span></span>

<span data-ttu-id="9fc1f-112">HoloLens 2 デバイスで、**[設定]** -> **[更新とセキュリティ]** -> **[Windows Insider Program]** の順に移動し、**[開始する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-112">On a HoloLens 2 device go to **Settings** -> **Update & Security** -> **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="9fc1f-113">Windows Insider として登録するために使用したアカウントをリンクします。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-113">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="9fc1f-114">次に、[ **Windows のアクティブな開発**] を選択し、**開発者チャネル**または**ベータチャネル**のビルドを受け取るかどうかを選択して、プログラムの利用規約を確認します。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-114">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="9fc1f-115">**[確認] -> [今すぐ再起動する]** を選択して完了します。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-115">Select **Confirm -> Restart Now** to finish up.</span></span> <span data-ttu-id="9fc1f-116">デバイスが再起動したら、**[設定] -> [更新とセキュリティ] -> [更新プログラムのチェック]** の順に移動して最新のビルドを入手します。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-116">After your device has rebooted, go to **Settings -> Update & Security -> Check for updates** to get the latest build.</span></span>

## <span data-ttu-id="9fc1f-117">Insider ビルドの受信の停止</span><span class="sxs-lookup"><span data-stu-id="9fc1f-117">Stop receiving Insider builds</span></span>

<span data-ttu-id="9fc1f-118">Windows Holographic の Insider ビルドを受け取りたくない場合は、HoloLens が製品版ビルドを実行しているときにオプトアウトすることができます。または、Advanced Recovery Companion を使用して[デバイスを回復](hololens-recovery.md)し、Windows Holographic の Insider バージョン以外にデバイスを回復することができます。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-118">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="9fc1f-119">新しいプレビュー ビルドを手動で再インストールした後に Insider Preview ビルドの登録を解除すると、ブルー スクリーンが発生するという既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-119">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="9fc1f-120">その後、手動でデバイスを回復する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-120">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="9fc1f-121">影響を受けるかどうかの詳細については、この[既知の問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)の詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-121">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="9fc1f-122">HoloLens が製品版ビルドを実行していることを確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-122">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="9fc1f-123">**[設定] > [システム] > [バージョン情報]** の順に移動し、ビルド番号を探します。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-123">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="9fc1f-124">[製品のビルド番号については、リリースノートを参照してください](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-124">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="9fc1f-125">Insider ビルドをオプトアウトするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-125">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="9fc1f-126">製品版ビルドを実行している HoloLens で、**[設定] > [更新とセキュリティ] > [Windows Insider Program]** に移動して、**[Insider Preview ビルドの停止]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-126">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="9fc1f-127">画面の指示に従って、デバイスでの受信を停止します。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-127">Follow the instructions to opt out your device.</span></span>


## <span data-ttu-id="9fc1f-128">フィードバックを提供し、問題を報告する</span><span class="sxs-lookup"><span data-stu-id="9fc1f-128">Provide feedback and report issues</span></span>

<span data-ttu-id="9fc1f-129">HoloLens で[フィードバック Hub アプリ](hololens-feedback.md)を使用してフィードバックを提供し、問題を報告することができます。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-129">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="9fc1f-130">フィードバック Hub を使用すると、エンジニアが問題を迅速にデバッグして解決するのに役立つすべての必要な診断情報が含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-130">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="9fc1f-131">中国語および日本語版の HoloLens に関する問題は、同じ方法で報告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-131">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="9fc1f-132">フィードバック Hub を使用してドキュメント フォルダーにアクセスするかどうかを確認するプロンプトに必ず同意してください (メッセージが表示されたら **[はい]** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-132">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="9fc1f-133">開発者向けの注意事項</span><span class="sxs-lookup"><span data-stu-id="9fc1f-133">Note for developers</span></span>

<span data-ttu-id="9fc1f-134">HoloLens の Insider ビルドを使用して自由にアプリケーションを開発してみることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-134">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="9fc1f-135">作業を始めるには、[HoloLens 開発者向けドキュメント](https://developer.microsoft.com/windows/mixed-reality/development)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-135">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="9fc1f-136">これらの同じ手順は HoloLens の Insider ビルドでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-136">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="9fc1f-137">HoloLens 開発用に使用しているものと同じビルドの Unity と Visual Studio を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-137">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>


## <span data-ttu-id="9fc1f-138">Windows Insider リリース ノート</span><span class="sxs-lookup"><span data-stu-id="9fc1f-138">Windows Insider Release Notes</span></span>

<span data-ttu-id="9fc1f-139">ここに表示されていない機能を探している場合は、通常は利用可能になっています。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-139">If you are looking for a feature that is no longer listed here, then it is now generally available.</span></span> <span data-ttu-id="9fc1f-140">[リリースノート](hololens-release-notes.md)を参照して、どのような機能を利用しているかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-140">Please review the [release notes](hololens-release-notes.md) to see what build has the feature(s) you are excited for.</span></span> <span data-ttu-id="9fc1f-141">[HoloLens を更新して](hololens-update-hololens.md)、最新の機能をすべて入手してください。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-141">Make sure to [update your HoloLens](hololens-update-hololens.md) to get all the latest features.</span></span>

<span data-ttu-id="9fc1f-142">このページは、Windows Insider ビルドにリリースされるときに、もう一度新しい機能で更新されます。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-142">We'll be updating this page with new features again as we release them to Windows Insider builds.</span></span>

| <span data-ttu-id="9fc1f-143">機能</span><span class="sxs-lookup"><span data-stu-id="9fc1f-143">Feature</span></span>                               | <span data-ttu-id="9fc1f-144">説明</span><span class="sxs-lookup"><span data-stu-id="9fc1f-144">Description</span></span>                                                                                   | <span data-ttu-id="9fc1f-145">Insider ビルドで利用可能</span><span class="sxs-lookup"><span data-stu-id="9fc1f-145">Available in insider builds</span></span> |
|---------------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------|
| <span data-ttu-id="9fc1f-146">オートアイポジションのサポート</span><span class="sxs-lookup"><span data-stu-id="9fc1f-146">Auto Eye Position Support</span></span>             | <span data-ttu-id="9fc1f-147">アイポジションを積極的に検索して、正確なホログラムの配置を実現します。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-147">Actively finds eye positions and enables accurate hologram positioning.</span></span>                       | <span data-ttu-id="9fc1f-148">19041.1339 +</span><span class="sxs-lookup"><span data-stu-id="9fc1f-148">19041.1339+</span></span>                 |
| <span data-ttu-id="9fc1f-149">グローバルに割り当てられたアクセス</span><span class="sxs-lookup"><span data-stu-id="9fc1f-149">Global Assigned Access</span></span>                | <span data-ttu-id="9fc1f-150">システムレベルで適用可能な複数のアプリキオスクモード用に HoloLens 2 デバイスを構成します。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-150">Configure HoloLens 2 device for multiple app kiosk mode which is applicable at system level.</span></span>  | <span data-ttu-id="9fc1f-151">19041.1346 +</span><span class="sxs-lookup"><span data-stu-id="9fc1f-151">19041.1346+</span></span>                 |
| <span data-ttu-id="9fc1f-152">マルチアプリキオスクでアプリを自動起動する</span><span class="sxs-lookup"><span data-stu-id="9fc1f-152">Auto launch an app in multi-app kiosk</span></span> | <span data-ttu-id="9fc1f-153">複数アプリのキオスクモードにサインインしたときに自動的に起動するようにアプリケーションを設定します。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-153">Sets an application to launch automatically when signing into into a multiple-app kiosk mode.</span></span> | <span data-ttu-id="9fc1f-154">19041.1346 +</span><span class="sxs-lookup"><span data-stu-id="9fc1f-154">19041.1346+</span></span>                 |

### <span data-ttu-id="9fc1f-155">オートアイポジションのサポート</span><span class="sxs-lookup"><span data-stu-id="9fc1f-155">Auto Eye Position Support</span></span>

<span data-ttu-id="9fc1f-156">HoloLens 2 では、目の位置によって正確なホログラムの配置が可能になり、表示品質が向上しました。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-156">In HoloLens 2, eye positions enable accurate hologram positioning, comfortable viewing experience and improved display quality.</span></span> <span data-ttu-id="9fc1f-157">目の位置は、目の追跡結果の一部として計算されます。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-157">Eye positions are computed as part of the eye tracking result.</span></span> <span data-ttu-id="9fc1f-158">ただし、そのためには、各ユーザーがアイ見つめ入力を必要としない場合でも、各ユーザーが目のトラッキングの調整を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-158">However, this requires each user to go through eye tracking calibration, even when the experience does not require eye gaze input.</span></span>

<span data-ttu-id="9fc1f-159">**オートアイポジション (AEP)** では、これらのシナリオを対話式の方法でユーザーの視点を計算できます。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-159">**Auto Eye Position (AEP)** enables these scenarios with an interaction-free way to compute eye positions for the user.</span></span>  <span data-ttu-id="9fc1f-160">自動目の位置は、ユーザーがデバイスを配置した瞬間から自動的にバックグラウンドで作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-160">Auto Eye Position starts working in the background automatically from the moment the user puts the device on.</span></span> <span data-ttu-id="9fc1f-161">ユーザーが前に目を通したトラッキングの調整を行っていない場合は、処理時間が短いときにユーザーの視点がディスプレイシステムに提供されるようになります。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-161">If the user does not have a prior eye tracking calibration, Auto Eye position will start providing the user's eye positions to the display system after a small processing time.</span></span> <span data-ttu-id="9fc1f-162">通常、この処理時間は 20-60 秒以内に行われます。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-162">This processing time typically is between 20 - 60 seconds.</span></span> <span data-ttu-id="9fc1f-163">ユーザーデータはデバイス上で保持されないため、ユーザーが停止し、デバイスを再起動するか、デバイスをスリープ状態に戻した場合は、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-163">The user data is not persisted on the device and hence this process is repeated if the user takes off and puts the device back on or if the device reboots or wakes up from sleep.</span></span>  

<span data-ttu-id="9fc1f-164">Uncalibrated ユーザーがデバイスに配置したときに、オートアイ位置機能によって、システムの動作がいくつか変更されます。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-164">There are a few system behavior changes with Auto Eye Position feature when an uncalibrated user puts on the device.</span></span> <span data-ttu-id="9fc1f-165">Uncalibrated ユーザーは、以前にデバイスの目のトラッキング調整プロセスを経ていないユーザーを参照しています。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-165">An uncalibrated user refers to someone who has not gone through the eye tracking calibration process on the device previously.</span></span>

|     <span data-ttu-id="9fc1f-166">アクティブなアプリケーション</span><span class="sxs-lookup"><span data-stu-id="9fc1f-166">Active Application</span></span>                           |     <span data-ttu-id="9fc1f-167">現在の動作</span><span class="sxs-lookup"><span data-stu-id="9fc1f-167">Current Behavior</span></span>                                   |     <span data-ttu-id="9fc1f-168">Windows Insider ビルド19041.1339 以降の動作</span><span class="sxs-lookup"><span data-stu-id="9fc1f-168">Behavior from Windows Insider   build 19041.1339+</span></span>                                                      |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="9fc1f-169">見つめ対応でないアプリまたはホログラフィックシェル</span><span class="sxs-lookup"><span data-stu-id="9fc1f-169">Non-gaze enabled app or Holographic Shell</span></span>    |     <span data-ttu-id="9fc1f-170">アイトラッキング調整のプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-170">Eye tracking calibration prompt is   displayed.</span></span>    |     <span data-ttu-id="9fc1f-171">プロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-171">No prompt is displayed.</span></span>                                                                                |
|     <span data-ttu-id="9fc1f-172">宝石対応アプリ</span><span class="sxs-lookup"><span data-stu-id="9fc1f-172">Gaze enabled app</span></span>                             |     <span data-ttu-id="9fc1f-173">アイトラッキング調整のプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-173">Eye tracking calibration prompt is   displayed.</span></span>    |     <span data-ttu-id="9fc1f-174">アイトラッキング調整プロンプトは、アプリケーションがアイ見つめストリームにアクセスしたときにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-174">Eye tracking calibration prompt is   displayed only when the application accesses eye gaze stream.</span></span>     |

 <span data-ttu-id="9fc1f-175">ユーザーが、見つめデータにアクセスするアプリケーションから、または見つめ対応のアプリケーションに切り替えた場合、調整のプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-175">If the user transitions from a non-gaze enabled application to one that accesses the gaze data, the calibration prompt will be displayed.</span></span> <span data-ttu-id="9fc1f-176">ボックスのエクスペリエンスフローの廃止には変更されません。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-176">There will be no changed to Out Of Box Experience flow.</span></span> 
 
<span data-ttu-id="9fc1f-177">視力のデータを必要とするエクスペリエンスや、非常に正確なホログラムの配置が必要な場合は、ユーザーがアイトラッキングの調整プロンプトからアイトラッキングの調整を実行するか、[スタート] メニューから設定アプリを起動して、[**システム > 調整] >** 目の調整 > 実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-177">For experiences that require eye gaze data or very precise hologram positioning, we recommend uncalibrated users to run eye tracking calibration from the eye tracking calibration prompt or by launching the Settings app from the start menu, and then selecting **System > Calibration > Eye Calibration > Run eye calibration**.</span></span>

**<span data-ttu-id="9fc1f-178">既知の問題</span><span class="sxs-lookup"><span data-stu-id="9fc1f-178">Known issues</span></span>**
 - <span data-ttu-id="9fc1f-179">この問題を調査していますが、メモリ負荷が高い状態で実行するとアイトラッカードライバーのホストプロセスがクラッシュする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-179">We're investigating an issue where the eye tracker driver host process could crash when running under heavy memory load.</span></span> <span data-ttu-id="9fc1f-180">アイトラッキングドライバーのホストプロセスは、自動的に回復する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-180">The eye tracking driver host process should auto recover.</span></span>

### <span data-ttu-id="9fc1f-181">グローバル割り当てアクセス–キオスクモード</span><span class="sxs-lookup"><span data-stu-id="9fc1f-181">Global Assigned Access – Kiosk Mode</span></span>
<span data-ttu-id="9fc1f-182">この新機能により、IT 管理者は、システムレベルで適用可能な複数のアプリキオスクモード用に HoloLens 2 デバイスを構成できます。また、システム上の id とのアフィニティはありません。また、デバイスにサインインしたすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-182">This new feature allows an IT Admin to configure a HoloLens 2 device for multiple app kiosk mode which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span> <span data-ttu-id="9fc1f-183">この新機能の詳細について[は、こちらをご覧](hololens-global-assigned-access-kiosk.md)ください。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-183">Read about this new feature in detail [here](hololens-global-assigned-access-kiosk.md).</span></span>

### <span data-ttu-id="9fc1f-184">複数アプリのキオスクモードでのアプリケーションの自動起動</span><span class="sxs-lookup"><span data-stu-id="9fc1f-184">Automatic launch of an application in multiple-app kiosk mode</span></span> 
<span data-ttu-id="9fc1f-185">複数のアプリのキオスクモードにのみ適用され、[割り当て済みのアクセス構成] の下の強調表示された属性を使用して、1つのアプリのみを自動起動に指定できます。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-185">Applies only to multiple-app kiosk mode and only 1 app can be designated to auto-launch using highlighted attribute below in Assigned Access configuration.</span></span> 

<span data-ttu-id="9fc1f-186">ユーザーがサインインすると、アプリケーションが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-186">Application is automatically launched when user signs-in.</span></span> 

```xml
<AllowedApps>                     
    <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

## <span data-ttu-id="9fc1f-187">FFU のダウンロードとフラッシュの手順</span><span class="sxs-lookup"><span data-stu-id="9fc1f-187">FFU download and flash directions</span></span>
<span data-ttu-id="9fc1f-188">フライト署名のある FFU でテストするには、フライト署名のある FFU をフラッシュする前にデバイスのフライト ロックを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-188">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="9fc1f-189">PC の場合:</span><span class="sxs-lookup"><span data-stu-id="9fc1f-189">On PC:</span></span>

    1. <span data-ttu-id="9fc1f-190">から PC に ffu をダウンロード [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) してください。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-190">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="9fc1f-191">Microsoft Store ([https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)) から ARC (Advanced Recovery Companion) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-191">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span></span>
    
1. <span data-ttu-id="9fc1f-192">HoloLens でのロック解除:**設定**の  >  **更新 & セキュリティ**  >  **Windows Insider プログラム**を開くと、次にサインアップして、デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-192">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="9fc1f-193">Flash FFU-「ARC」を使って、フライト署名された FFU を点滅させることができます。</span><span class="sxs-lookup"><span data-stu-id="9fc1f-193">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>
