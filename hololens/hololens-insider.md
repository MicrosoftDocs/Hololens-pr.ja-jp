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
ms.openlocfilehash: cd2b055679f5e1a9a529ad4947773e412211f9c4
ms.sourcegitcommit: 2b1518675b9962518e08b13c12b43b6d9827fe17
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "10858011"
---
# <span data-ttu-id="b8cbb-103">Microsoft HoloLens の Insider Preview</span><span class="sxs-lookup"><span data-stu-id="b8cbb-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="b8cbb-104">HoloLens 用の最新の Insider Preview ビルドへようこそ!</span><span class="sxs-lookup"><span data-stu-id="b8cbb-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span>  <span data-ttu-id="b8cbb-105">簡単に使い始めて、HoloLens の次の主要なオペレーティング システムの更新プログラムに対する貴重なフィードバックをご提供いただけます。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-105">It's simple to get started and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

<span data-ttu-id="b8cbb-106">Windows insider がチャネルに移動するようになりました。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-106">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="b8cbb-107">**ファスト**リングは**Dev チャネル**になります。**スロー**リングは**ベータチャネル**になり、 **release preview** ring は**リリースプレビューチャネル**になります。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-107">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="b8cbb-108">マッピングの外観は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-108">Here is what that mapping looks like:</span></span>

![Windows Insider チャンネル explination](images/WindowsInsiderChannels.png)

<span data-ttu-id="b8cbb-110">詳細については、「 [Windows のブログエントリ](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-110">For more information: [Windows Blog entry](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)</span></span>

## <span data-ttu-id="b8cbb-111">Insider ビルドの受信の開始</span><span class="sxs-lookup"><span data-stu-id="b8cbb-111">Start receiving Insider builds</span></span>

<span data-ttu-id="b8cbb-112">HoloLens 2 デバイスで、**[設定]** -> **[更新とセキュリティ]** -> **[Windows Insider Program]** の順に移動し、**[開始する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-112">On a HoloLens 2 device go to **Settings** -> **Update & Security** -> **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="b8cbb-113">Windows Insider として登録するために使用したアカウントをリンクします。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-113">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="b8cbb-114">次に、[ **Windows のアクティブな開発**] を選択し、**開発者チャネル**または**ベータチャネル**のビルドを受け取るかどうかを選択して、プログラムの利用規約を確認します。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-114">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="b8cbb-115">**[確認] -> [今すぐ再起動する]** を選択して完了します。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-115">Select **Confirm -> Restart Now** to finish up.</span></span> <span data-ttu-id="b8cbb-116">デバイスが再起動したら、**[設定] -> [更新とセキュリティ] -> [更新プログラムのチェック]** の順に移動して最新のビルドを入手します。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-116">After your device has rebooted, go to **Settings -> Update & Security -> Check for updates** to get the latest build.</span></span>

## <span data-ttu-id="b8cbb-117">Insider ビルドの受信の停止</span><span class="sxs-lookup"><span data-stu-id="b8cbb-117">Stop receiving Insider builds</span></span>

<span data-ttu-id="b8cbb-118">Windows Holographic の Insider ビルドを受け取りたくない場合は、HoloLens が製品版ビルドを実行しているときにオプトアウトすることができます。または、Advanced Recovery Companion を使用して[デバイスを回復](hololens-recovery.md)し、Windows Holographic の Insider バージョン以外にデバイスを回復することができます。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-118">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="b8cbb-119">新しいプレビュー ビルドを手動で再インストールした後に Insider Preview ビルドの登録を解除すると、ブルー スクリーンが発生するという既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-119">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="b8cbb-120">その後、手動でデバイスを回復する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-120">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="b8cbb-121">影響を受けるかどうかの詳細については、この[既知の問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)の詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-121">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="b8cbb-122">HoloLens が製品版ビルドを実行していることを確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-122">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="b8cbb-123">**[設定] > [システム] > [バージョン情報]** の順に移動し、ビルド番号を探します。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-123">Go to **Settings > System > About**, and find the build number.</span></span>
1. [<span data-ttu-id="b8cbb-124">製品版ビルド番号については、リリース ノートをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-124">See the release notes for production build numbers.</span></span>](hololens-release-notes.md)

<span data-ttu-id="b8cbb-125">Insider ビルドをオプトアウトするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-125">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="b8cbb-126">製品版ビルドを実行している HoloLens で、**[設定] > [更新とセキュリティ] > [Windows Insider Program]** に移動して、**[Insider Preview ビルドの停止]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-126">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>
1. <span data-ttu-id="b8cbb-127">画面の指示に従って、デバイスでの受信を停止します。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-127">Follow the instructions to opt out your device.</span></span>



## <span data-ttu-id="b8cbb-128">フィードバックを提供し、問題を報告する</span><span class="sxs-lookup"><span data-stu-id="b8cbb-128">Provide feedback and report issues</span></span>

<span data-ttu-id="b8cbb-129">HoloLens で[フィードバック Hub アプリ](hololens-feedback.md)を使用してフィードバックを提供し、問題を報告することができます。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-129">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="b8cbb-130">フィードバック Hub を使用すると、エンジニアが問題を迅速にデバッグして解決するのに役立つすべての必要な診断情報が含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-130">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="b8cbb-131">中国語および日本語版の HoloLens に関する問題は、同じ方法で報告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-131">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="b8cbb-132">フィードバック Hub を使用してドキュメント フォルダーにアクセスするかどうかを確認するプロンプトに必ず同意してください (メッセージが表示されたら **[はい]** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-132">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="b8cbb-133">開発者向けの注意事項</span><span class="sxs-lookup"><span data-stu-id="b8cbb-133">Note for developers</span></span>

<span data-ttu-id="b8cbb-134">HoloLens の Insider ビルドを使用して自由にアプリケーションを開発してみることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-134">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="b8cbb-135">作業を始めるには、[HoloLens 開発者向けドキュメント](https://developer.microsoft.com/windows/mixed-reality/development)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-135">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="b8cbb-136">これらの同じ手順は HoloLens の Insider ビルドでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-136">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="b8cbb-137">HoloLens 開発用に使用しているものと同じビルドの Unity と Visual Studio を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-137">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>


## <span data-ttu-id="b8cbb-138">Windows Insider リリース ノート</span><span class="sxs-lookup"><span data-stu-id="b8cbb-138">Windows Insider Release Notes</span></span>

<span data-ttu-id="b8cbb-139">ここに記載されている機能が、insider 以外のビルドでは表示されていない場合は、[リリースノート](hololens-release-notes.md)をお読みになっていることを確認してください。すべての機能を利用できるようになっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-139">If you are looking for a feature previously listed here that you don't see then it has made it's way into the non-insider builds, please make sure to read the [Release notes](hololens-release-notes.md) to see all features generally available.</span></span> <span data-ttu-id="b8cbb-140">[HoloLens を更新して](hololens-update-hololens.md)、最新の機能をすべて入手してください。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-140">Make sure to [update your HoloLens](hololens-update-hololens.md) to get all the latest features.</span></span>  

<span data-ttu-id="b8cbb-141">このページは、Windows Insider ビルドにリリースするときに、新しい機能を使ってもう一度更新します。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-141">We'll be updating this page again with new features as we release them to Windows Insider builds.</span></span> 

### <span data-ttu-id="b8cbb-142">オートアイポジションのサポート</span><span class="sxs-lookup"><span data-stu-id="b8cbb-142">Auto Eye Position Support</span></span>

<span data-ttu-id="b8cbb-143">HoloLens 2 では、目の位置によって正確なホログラムの配置が可能になり、表示品質が向上しました。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-143">In HoloLens 2, eye positions enable accurate hologram positioning, comfortable viewing experience and improved display quality.</span></span> <span data-ttu-id="b8cbb-144">目の位置は、目の追跡結果の一部として計算されます。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-144">Eye positions are computed as part of the eye tracking result.</span></span> <span data-ttu-id="b8cbb-145">ただし、そのためには、各ユーザーがアイ見つめ入力を必要としない場合でも、各ユーザーが目のトラッキングの調整を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-145">However, this requires each user to go through eye tracking calibration, even when the experience does not require eye gaze input.</span></span>

<span data-ttu-id="b8cbb-146">**オートアイポジション (AEP)** では、これらのシナリオを対話式の方法でユーザーの視点を計算できます。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-146">**Auto Eye Position (AEP)** enables these scenarios with an interaction-free way to compute eye positions for the user.</span></span>  <span data-ttu-id="b8cbb-147">自動目の位置は、ユーザーがデバイスを配置した瞬間から自動的にバックグラウンドで作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-147">Auto Eye Position starts working in the background automatically from the moment the user puts the device on.</span></span> <span data-ttu-id="b8cbb-148">ユーザーが前に目を通したトラッキングの調整を行っていない場合は、処理時間が短いときにユーザーの視点がディスプレイシステムに提供されるようになります。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-148">If the user does not have a prior eye tracking calibration, Auto Eye position will start providing the user's eye positions to the display system after a small processing time.</span></span> <span data-ttu-id="b8cbb-149">通常、この処理時間は 20-60 秒以内に行われます。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-149">This processing time typically is between 20 - 60 seconds.</span></span> <span data-ttu-id="b8cbb-150">ユーザーデータはデバイス上で保持されないため、ユーザーが停止し、デバイスを再起動するか、デバイスをスリープ状態に戻した場合は、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-150">The user data is not persisted on the device and hence this process is repeated if the user takes off and puts the device back on or if the device reboots or wakes up from sleep.</span></span>  

<span data-ttu-id="b8cbb-151">Uncalibrated ユーザーがデバイスに配置したときに、オートアイ位置機能によって、システムの動作がいくつか変更されます。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-151">There are a few system behavior changes with Auto Eye Position feature when an uncalibrated user puts on the device.</span></span> <span data-ttu-id="b8cbb-152">Uncalibrated ユーザーは、以前にデバイスの目のトラッキング調整プロセスを経ていないユーザーを参照しています。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-152">An uncalibrated user refers to someone who has not gone through the eye tracking calibration process on the device previously.</span></span>

|     <span data-ttu-id="b8cbb-153">アクティブなアプリケーション</span><span class="sxs-lookup"><span data-stu-id="b8cbb-153">Active Application</span></span>                           |     <span data-ttu-id="b8cbb-154">現在の動作</span><span class="sxs-lookup"><span data-stu-id="b8cbb-154">Current Behavior</span></span>                                   |     <span data-ttu-id="b8cbb-155">Windows Insider ビルド19041.1339 以降の動作</span><span class="sxs-lookup"><span data-stu-id="b8cbb-155">Behavior from Windows Insider   build 19041.1339+</span></span>                                                      |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="b8cbb-156">見つめ対応でないアプリまたはホログラフィックシェル</span><span class="sxs-lookup"><span data-stu-id="b8cbb-156">Non-gaze enabled app or Holographic Shell</span></span>    |     <span data-ttu-id="b8cbb-157">アイトラッキング調整のプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-157">Eye tracking calibration prompt is   displayed.</span></span>    |     <span data-ttu-id="b8cbb-158">プロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-158">No prompt is displayed.</span></span>                                                                                |
|     <span data-ttu-id="b8cbb-159">宝石対応アプリ</span><span class="sxs-lookup"><span data-stu-id="b8cbb-159">Gaze enabled app</span></span>                             |     <span data-ttu-id="b8cbb-160">アイトラッキング調整のプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-160">Eye tracking calibration prompt is   displayed.</span></span>    |     <span data-ttu-id="b8cbb-161">アイトラッキング調整プロンプトは、アプリケーションがアイ見つめストリームにアクセスしたときにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-161">Eye tracking calibration prompt is   displayed only when the application accesses eye gaze stream.</span></span>     |

 <span data-ttu-id="b8cbb-162">ユーザーが、見つめデータにアクセスするアプリケーションから、または見つめ対応のアプリケーションに切り替えた場合、調整のプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-162">If the user transitions from a non-gaze enabled application to one that accesses the gaze data, the calibration prompt will be displayed.</span></span> <span data-ttu-id="b8cbb-163">ボックスのエクスペリエンスフローの廃止には変更されません。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-163">There will be no changed to Out Of Box Experience flow.</span></span> 
 
<span data-ttu-id="b8cbb-164">視力のデータを必要とするエクスペリエンスや、非常に正確なホログラムの配置が必要な場合は、ユーザーがアイトラッキングの調整プロンプトからアイトラッキングの調整を実行するか、[スタート] メニューから設定アプリを起動して、[**システム > 調整] >** 目の調整 > 実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-164">For experiences that require eye gaze data or very precise hologram positioning, we recommend uncalibrated users to run eye tracking calibration from the eye tracking calibration prompt or by launching the Settings app from the start menu, and then selecting **System > Calibration > Eye Calibration > Run eye calibration**.</span></span>

**<span data-ttu-id="b8cbb-165">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b8cbb-165">Known issues</span></span>**
1.  <span data-ttu-id="b8cbb-166">この問題を調査していますが、メモリ負荷が高い状態で実行するとアイトラッカードライバーのホストプロセスがクラッシュする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-166">We're investigating an issue where the eye tracker driver host process could crash when running under heavy memory load.</span></span> <span data-ttu-id="b8cbb-167">アイトラッキングドライバーのホストプロセスは、自動的に回復する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-167">The eye tracking driver host process should auto recover.</span></span>

## <span data-ttu-id="b8cbb-168">FFU のダウンロードとフラッシュの手順</span><span class="sxs-lookup"><span data-stu-id="b8cbb-168">FFU download and flash directions</span></span>
<span data-ttu-id="b8cbb-169">フライト署名のある FFU でテストするには、フライト署名のある FFU をフラッシュする前にデバイスのフライト ロックを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-169">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="b8cbb-170">PC で次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-170">On PC</span></span>
    1. <span data-ttu-id="b8cbb-171">[https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) から PC に FFU をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-171">Download ffu to your PC from: [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload)</span></span>
    1. <span data-ttu-id="b8cbb-172">Microsoft Store ([https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)) から ARC (Advanced Recovery Companion) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="b8cbb-172">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span></span> 
1. <span data-ttu-id="b8cbb-173">HoloLens - フライト ロックを解除します。**[設定]** > **[更新とセキュリティ]** > **[Windows Insider Program]** の順に開き、サインアップして、デバイスを再起動します</span><span class="sxs-lookup"><span data-stu-id="b8cbb-173">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device</span></span>
1. <span data-ttu-id="b8cbb-174">フラッシュ FFU - ARC を使用してフライト署名された FFU をフラッシュできるようになりました</span><span class="sxs-lookup"><span data-stu-id="b8cbb-174">Flash FFU - Now you can flash the flight signed FFU using ARC</span></span> 
