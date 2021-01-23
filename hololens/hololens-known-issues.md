---
title: HoloLens の既知の問題
description: Unity と Windows Device Portal を使用している HoloLens のお客様や開発者に影響を与える可能性がある既知の問題と回避策の一覧を最新の状態に保ってください。
keywords: トラブルシューティング, 既知の問題, ヘルプ
author: mattzmsft
ms.author: mazeller
ms.date: 11/30/2020
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
- HoloLens 2
ms.openlocfilehash: 54bc090352983e814c64deea8f1f401c24e3261b
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284078"
---
# <span data-ttu-id="34a1c-104">HoloLens の既知の問題</span><span class="sxs-lookup"><span data-stu-id="34a1c-104">Known issues for HoloLens</span></span>

<span data-ttu-id="34a1c-105">これは、HoloLens デバイスの既知の問題の現在の一覧です。</span><span class="sxs-lookup"><span data-stu-id="34a1c-105">This is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="34a1c-106">奇数の動作が表示される場合は、まずここで確認してください。</span><span class="sxs-lookup"><span data-stu-id="34a1c-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="34a1c-107">この一覧は、新しい問題が検出または報告された場合、または将来の HoloLens ソフトウェア更新プログラムで問題が解決された場合に更新されます。</span><span class="sxs-lookup"><span data-stu-id="34a1c-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="34a1c-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="34a1c-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="34a1c-109">If the issue you are facing is blocking you, addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).</span><span class="sxs-lookup"><span data-stu-id="34a1c-109">If the issue you are facing is blocking you, in addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).</span></span>

- [<span data-ttu-id="34a1c-110">すべての HoloLens 世代の既知の問題</span><span class="sxs-lookup"><span data-stu-id="34a1c-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="34a1c-111">HoloLens 2 デバイスの既知の問題</span><span class="sxs-lookup"><span data-stu-id="34a1c-111">Known issues for HoloLens 2 devices</span></span>](#known-issues-for-hololens-2-devices)
- [<span data-ttu-id="34a1c-112">HoloLens (第 1 世代) の既知の問題</span><span class="sxs-lookup"><span data-stu-id="34a1c-112">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)
- [<span data-ttu-id="34a1c-113">HoloLens エミュレーターの既知の問題</span><span class="sxs-lookup"><span data-stu-id="34a1c-113">Known issues for HoloLens emulator</span></span>](#known-issues-for-hololens-emulator)

## <span data-ttu-id="34a1c-114">すべての HoloLens 世代の既知の問題</span><span class="sxs-lookup"><span data-stu-id="34a1c-114">Known issues for all HoloLens generations</span></span>

### <span data-ttu-id="34a1c-115">Unity</span><span class="sxs-lookup"><span data-stu-id="34a1c-115">Unity</span></span>

- <span data-ttu-id="34a1c-116">HoloLens [の開発](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) に推奨される最新バージョンの Unity のツールのインストールに関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="34a1c-116">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="34a1c-117">Unity HoloLens Technical Preview に関する既知の問題については [、HoloLens Unity フォーラムに記載されています](https://forum.unity3d.com/threads/known-issues.394627/)。</span><span class="sxs-lookup"><span data-stu-id="34a1c-117">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <span data-ttu-id="34a1c-118">Windows Device Portal</span><span class="sxs-lookup"><span data-stu-id="34a1c-118">Windows Device Portal</span></span>

- <span data-ttu-id="34a1c-119">Mixed Reality キャプチャの Live Preview 機能では、数秒の待機時間が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="34a1c-119">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="34a1c-120">[仮想入力] ページの [仮想ジェスチャ] セクションの下にある [ジェスチャ] コントロールと [スクロール] コントロールは機能しません。</span><span class="sxs-lookup"><span data-stu-id="34a1c-120">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="34a1c-121">それらを使用した場合、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="34a1c-121">Using them will have no effect.</span></span> <span data-ttu-id="34a1c-122">同じページ上の仮想キーボードは正しく動作します。</span><span class="sxs-lookup"><span data-stu-id="34a1c-122">The virtual keyboard on the same page works correctly.</span></span>

- <span data-ttu-id="34a1c-123">設定で開発者モードを有効にした後、Device Portal を有効にする切り替えに数秒かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="34a1c-123">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <span data-ttu-id="34a1c-124">OneDrive カメラのアップロード</span><span class="sxs-lookup"><span data-stu-id="34a1c-124">OneDrive camera upload</span></span>

<span data-ttu-id="34a1c-125">HoloLens 用 OneDrive アプリでは、仕事用または学校アカウントの自動カメラ アップロードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="34a1c-125">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="34a1c-126">回避策:</span><span class="sxs-lookup"><span data-stu-id="34a1c-126">Workarounds:</span></span>

- <span data-ttu-id="34a1c-127">ビジネスで実行可能な場合は、コンシューマー向け Microsoft アカウントでカメラの自動アップロードがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="34a1c-127">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="34a1c-128">Microsoft アカウントには、自分の仕事用または学校用のアカウントに加えてサインインできます (OneDrive アプリはデュアル サインインをサポートしています)。</span><span class="sxs-lookup"><span data-stu-id="34a1c-128">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="34a1c-129">OneDrive 内の Microsoft アカウント プロファイルから、カメラ ロールの自動アップロードを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="34a1c-129">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="34a1c-130">写真を自動的にアップロードするためにコンシューマー向け Microsoft アカウントを安全に使用できない場合は、OneDrive アプリから手動で写真を仕事または学校のアカウントにアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="34a1c-130">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="34a1c-131">これを行うには、OneDrive アプリで、自分の仕事または学校のアカウントにサインインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="34a1c-131">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="34a1c-132">ボタンを選択 **+** し、[アップロード] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="34a1c-132">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="34a1c-133">[ピクチャ] ページの [カメラ ロール] に移動して、アップロード **する>見つける**。</span><span class="sxs-lookup"><span data-stu-id="34a1c-133">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="34a1c-134">アップロードする写真またはビデオを選択し、[開く] ボタン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="34a1c-134">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <span data-ttu-id="34a1c-135">HoloLens 2 デバイスの既知の問題</span><span class="sxs-lookup"><span data-stu-id="34a1c-135">Known issues for HoloLens 2 devices</span></span>

### <span data-ttu-id="34a1c-136">Microsoft Edge の起動に失敗する</span><span class="sxs-lookup"><span data-stu-id="34a1c-136">Microsoft Edge fails to launch</span></span>

<span data-ttu-id="34a1c-137">少数のお客様から、Microsoft Edge の起動に失敗する問題が報告されています。</span><span class="sxs-lookup"><span data-stu-id="34a1c-137">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="34a1c-138">これらのお客様の場合、問題は再起動を通じて保持され、Windows またはアプリケーションの更新プログラムでは解決されません。</span><span class="sxs-lookup"><span data-stu-id="34a1c-138">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="34a1c-139">If you're experiencing this issue and you've confirmed [Windows is up-to-date,](hololens-updates.md#manually-check-for-updates)please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span><span class="sxs-lookup"><span data-stu-id="34a1c-139">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="34a1c-140">既知の回避策はありません。これまで問題の根本原因を特定できなかったので、回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="34a1c-140">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="34a1c-141">フィードバック Hub 経由でバグを報告すると、調査に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="34a1c-141">Filing a bug via Feedback Hub will help our investigation!</span></span>

### <span data-ttu-id="34a1c-142">キーボードが特殊文字に切り替えない</span><span class="sxs-lookup"><span data-stu-id="34a1c-142">Keyboard does not switch to special characters</span></span>

<span data-ttu-id="34a1c-143">OOBE 中に問題が発生し、ユーザーが仕事または学校のアカウントを選択してパスワードを入力すると、&123 ボタンをタップしてキーボードの特殊文字に切り替えようとしても、特殊文字に変わりません。</span><span class="sxs-lookup"><span data-stu-id="34a1c-143">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> 

<span data-ttu-id="34a1c-144">回避方法:</span><span class="sxs-lookup"><span data-stu-id="34a1c-144">Work-arounds:</span></span>
-   <span data-ttu-id="34a1c-145">キーボードを閉じ、テキスト フィールドをタップしてもう一度開きます。</span><span class="sxs-lookup"><span data-stu-id="34a1c-145">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="34a1c-146">パスワードを誤って入力します。</span><span class="sxs-lookup"><span data-stu-id="34a1c-146">Incorrectly enter your password.</span></span> <span data-ttu-id="34a1c-147">次回キーボードを再起動すると、期待通り動作します。</span><span class="sxs-lookup"><span data-stu-id="34a1c-147">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="34a1c-148">Web 認証を行い、キーボードを閉じて、別 **のデバイスから [サインイン] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="34a1c-148">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span> 
-   <span data-ttu-id="34a1c-149">数字のみを入力する場合、ユーザーは特定のキーを長押しして展開されたメニューを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="34a1c-149">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="34a1c-150">USB キーボードを使用する。</span><span class="sxs-lookup"><span data-stu-id="34a1c-150">Using a USB keyboard.</span></span>

<span data-ttu-id="34a1c-151">これは、次に影響を与える影響ではありません。</span><span class="sxs-lookup"><span data-stu-id="34a1c-151">This does not affect:</span></span>
- <span data-ttu-id="34a1c-152">個人アカウントの使用を選択したユーザー。</span><span class="sxs-lookup"><span data-stu-id="34a1c-152">Users who choose to use a personal account.</span></span>

### <span data-ttu-id="34a1c-153">Blue screen is shown after unenrolling from Insider preview builds on a device reflashed with a Insider build</span><span class="sxs-lookup"><span data-stu-id="34a1c-153">Blue screen is shown after unenrolling from Insider preview builds on a device reflashed with a Insider build</span></span>

<span data-ttu-id="34a1c-154">これは、Insider プレビュー ビルドに含まれるユーザーに影響を与え、HoloLens 2 を新しい Insider Preview ビルドで再フラッシュし、Insider プログラムから登録解除したユーザーに影響を与える問題です。</span><span class="sxs-lookup"><span data-stu-id="34a1c-154">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> 

<span data-ttu-id="34a1c-155">これは、次に影響を与える影響ではありません。</span><span class="sxs-lookup"><span data-stu-id="34a1c-155">This does not affect:</span></span>
- <span data-ttu-id="34a1c-156">Windows Insider に登録されていないユーザー</span><span class="sxs-lookup"><span data-stu-id="34a1c-156">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="34a1c-157">Insider:</span><span class="sxs-lookup"><span data-stu-id="34a1c-157">Insiders:</span></span>
    - <span data-ttu-id="34a1c-158">Insider ビルドがバージョン 18362.x 以降にデバイスを登録している場合</span><span class="sxs-lookup"><span data-stu-id="34a1c-158">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="34a1c-159">Insider が署名した 19041.x ビルドをフラッシュし、Insider プログラムへの登録を行った場合</span><span class="sxs-lookup"><span data-stu-id="34a1c-159">If they flashed a Insider signed 19041.x build AND stay enrolled in the Insider program</span></span> 

<span data-ttu-id="34a1c-160">回避:</span><span class="sxs-lookup"><span data-stu-id="34a1c-160">Work-around:</span></span> 
- <span data-ttu-id="34a1c-161">問題を回避する</span><span class="sxs-lookup"><span data-stu-id="34a1c-161">Avoid the issue</span></span> 
    - <span data-ttu-id="34a1c-162">Insider 以外のビルドをフラッシュします。</span><span class="sxs-lookup"><span data-stu-id="34a1c-162">Flash a non-insider build.</span></span> <span data-ttu-id="34a1c-163">定期的な月次更新プログラムの 1 つ。</span><span class="sxs-lookup"><span data-stu-id="34a1c-163">One of the regular monthly updates.</span></span> 
    - <span data-ttu-id="34a1c-164">Insider Preview を利用する</span><span class="sxs-lookup"><span data-stu-id="34a1c-164">Stay on Insider Preview</span></span>
- <span data-ttu-id="34a1c-165">デバイスを再フラッシュする</span><span class="sxs-lookup"><span data-stu-id="34a1c-165">Reflash the device</span></span>

    1. <span data-ttu-id="34a1c-166">[HoloLens 2](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2)を手動でフラッシュ モードにします。接続していない間は電源を完全にオフにします。</span><span class="sxs-lookup"><span data-stu-id="34a1c-166">Put the [HoloLens 2 into flashing mode](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) manually by fully powering down while not connect.</span></span> <span data-ttu-id="34a1c-167">次に、音量を上げながら電源ボタンをタップします。</span><span class="sxs-lookup"><span data-stu-id="34a1c-167">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="34a1c-168">PC に接続し、Advanced Recovery Companion を開きます。</span><span class="sxs-lookup"><span data-stu-id="34a1c-168">Connect to the PC and open Advanced Recovery Companion.</span></span> 
    
    1. <span data-ttu-id="34a1c-169">HoloLens 2 を既定のビルドにフラッシュします。</span><span class="sxs-lookup"><span data-stu-id="34a1c-169">Flash the HoloLens 2 to the default build.</span></span>   

## <span data-ttu-id="34a1c-170">HoloLens (第 1 世代) の既知の問題</span><span class="sxs-lookup"><span data-stu-id="34a1c-170">Known issues for HoloLens (1st Gen)</span></span>

### <span data-ttu-id="34a1c-171">デバイスから HoloLens に接続して展開Visual Studio</span><span class="sxs-lookup"><span data-stu-id="34a1c-171">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="34a1c-172">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span><span class="sxs-lookup"><span data-stu-id="34a1c-172">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="34a1c-173">このエラーが発生しないように、この最新バージョンに更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="34a1c-173">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="34a1c-174">Visual Studio VS 2019 バージョン 16.2 がリリースされました。この問題の修正プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="34a1c-174">Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="34a1c-175">このエラーが発生しないように、この最新バージョンに更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="34a1c-175">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="34a1c-176">問題の根本原因: Visual Studio 2015 または Visual Studio 2017 の初期リリースを使用して HoloLens にアプリケーションを展開およびデバッグし、その後、同じ HoloLens で最新バージョンの Visual Studio 2017 または Visual Studio 2019 を使用したユーザーが影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="34a1c-176">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="34a1c-177">新しいリリースの Visual Studioは新しいバージョンのコンポーネントを展開しますが、以前のバージョンのファイルはデバイスに残され、その結果、新しいバージョンが失敗します。</span><span class="sxs-lookup"><span data-stu-id="34a1c-177">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="34a1c-178">これにより、"DEP0100" というエラー メッセージが表示されます。ターゲット デバイスで開発者モードが有効になっているか確認してください。</span><span class="sxs-lookup"><span data-stu-id="34a1c-178">This causes the following error message: DEP0100: Please ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="34a1c-179">エラー \<ip\> 80004005 が原因で開発者用ライセンスを取得できない。</span><span class="sxs-lookup"><span data-stu-id="34a1c-179">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <span data-ttu-id="34a1c-180">回避策</span><span class="sxs-lookup"><span data-stu-id="34a1c-180">Workaround</span></span>

<span data-ttu-id="34a1c-181">現在、チームは修正に取り組み中です。</span><span class="sxs-lookup"><span data-stu-id="34a1c-181">Our team is currently working on a fix.</span></span> <span data-ttu-id="34a1c-182">その間、次の手順を使用して問題を回避し、展開とデバッグのブロックを解除できます。</span><span class="sxs-lookup"><span data-stu-id="34a1c-182">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="34a1c-183">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="34a1c-183">Open Visual Studio.</span></span>

1. <span data-ttu-id="34a1c-184">ファイルの**新しい**  >  **プロジェクトを選択**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="34a1c-184">Select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="34a1c-185">**Visual C#**  >  **Windows デスクトップ コンソール**アプリ  >  **(.NET Framework) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="34a1c-185">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>

1. <span data-ttu-id="34a1c-186">プロジェクトに名前 ("HoloLensDeploymentFix" など) を付け、フレームワークが少なくとも .NET Framework 4.5 に設定されている必要があります **。[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="34a1c-186">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>

1. <span data-ttu-id="34a1c-187">ソリューション エクスプローラーで **[参照]** ノードを右クリックし、次の参照を追加します ([参照] セクションに **選択し、[** 参照] を **選択します**)。</span><span class="sxs-lookup"><span data-stu-id="34a1c-187">Right-click the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="34a1c-188">10.0.18362.0 がインストールされていない場合は、最新バージョンを使用してください。</span><span class="sxs-lookup"><span data-stu-id="34a1c-188">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span> 

1. <span data-ttu-id="34a1c-189">ソリューション エクスプローラーでプロジェクトを右クリックし、[既存\*\*\*\* の項目の追加  >  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="34a1c-189">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>

1. <span data-ttu-id="34a1c-190">C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 を参照し、フィルターを **[すべてのファイル] (\*.\*)** に変更します。</span><span class="sxs-lookup"><span data-stu-id="34a1c-190">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>

1. <span data-ttu-id="34a1c-191">ユーザー設定とSirepClient.dll両方をSshClient.dll、[追加] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="34a1c-191">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>

1. <span data-ttu-id="34a1c-192">ソリューション エクスプローラーで両方のファイルを見つけて選択し (ファイルの一覧の一番下にある\*\*\*\* 必要があります)、[プロパティ]\*\*\*\* ウィンドウで [出力ディレクトリにコピー] を [常にコピー] に**変更します**。</span><span class="sxs-lookup"><span data-stu-id="34a1c-192">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>

1. <span data-ttu-id="34a1c-193">ファイルの上部で、ステートメントの既存のリストに次を `using` 追加します。</span><span class="sxs-lookup"><span data-stu-id="34a1c-193">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="34a1c-194">内部に `static void Main(...)` 、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="34a1c-194">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="34a1c-195">[ビルド**ソリューション**  >  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="34a1c-195">Select **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="34a1c-196">コマンド プロンプト ウィンドウを開き、コンパイル済みの .exe ファイルを含むフォルダー (C:\MyProjects\HoloLensDeploymentFix\bin\Debug など) に cd を開きます。</span><span class="sxs-lookup"><span data-stu-id="34a1c-196">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span></span>

1. <span data-ttu-id="34a1c-197">実行可能ファイルを実行し、デバイスの IP アドレスをコマンド ライン引数として指定します。</span><span class="sxs-lookup"><span data-stu-id="34a1c-197">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="34a1c-198">(USB を使用して接続されている場合は、127.0.0.1 を使用できます。それ以外の場合は、デバイスの IP アドレスWi-Fi使用します)。 たとえば、"HoloLensDeploymentFix 127.0.0.1" などです。</span><span class="sxs-lookup"><span data-stu-id="34a1c-198">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1".</span></span>

1. <span data-ttu-id="34a1c-199">メッセージが表示されることなくツールが終了すると (数秒で終了する必要があります)、Visual Studio 2017 以降から展開とデバッグが可能になります。</span><span class="sxs-lookup"><span data-stu-id="34a1c-199">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="34a1c-200">ツールを継続して使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="34a1c-200">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="34a1c-201">今後、更新プログラムが利用可能になったら、その更新プログラムを提供します。</span><span class="sxs-lookup"><span data-stu-id="34a1c-201">We will provide further updates as they become available.</span></span>

### <span data-ttu-id="34a1c-202">HoloLens での Microsoft Store とアプリの起動に関する問題</span><span class="sxs-lookup"><span data-stu-id="34a1c-202">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="34a1c-203">Last Update: 4/2 @ 10 AM - Issue resolved.</span><span class="sxs-lookup"><span data-stu-id="34a1c-203">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span> 

<span data-ttu-id="34a1c-204">HoloLens で Microsoft Store とアプリを起動しようとするときに問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="34a1c-204">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="34a1c-205">バックグラウンド アプリの更新プログラムが特定のシーケンスでフレームワーク パッケージの新しいバージョンを展開し、1 つ以上の依存アプリが実行中であるときに、この問題が発生すると判断しました。</span><span class="sxs-lookup"><span data-stu-id="34a1c-205">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="34a1c-206">この場合、アプリの自動更新により、新しいバージョンの .NET Native Framework (バージョン 10.0.25531 から 10.0.27413) が配信され、実行中のアプリが以前のバージョンのフレームワークを使用しているすべての実行中のアプリに対して正しく更新されませんでした。</span><span class="sxs-lookup"><span data-stu-id="34a1c-206">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="34a1c-207">フレームワーク更新のフローは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="34a1c-207">The flow for framework update is as follows:</span></span> 

1. <span data-ttu-id="34a1c-208">新しいフレームワーク パッケージがストアからダウンロードされ、インストールされます。</span><span class="sxs-lookup"><span data-stu-id="34a1c-208">The new framework package is downloaded from the store and installed.</span></span>

1. <span data-ttu-id="34a1c-209">以前のフレームワークを使用しているすべてのアプリは、新しいバージョンを使用するように "更新" されます。</span><span class="sxs-lookup"><span data-stu-id="34a1c-209">All apps using the older framework are 'updated' to use the newer version.</span></span>

<span data-ttu-id="34a1c-210">完了前に手順 2 が中断された場合、新しいフレームワークが登録されていないアプリはスタート メニューから起動されません。</span><span class="sxs-lookup"><span data-stu-id="34a1c-210">If step 2 is interrupted before completion then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="34a1c-211">HoloLens 上のアプリは、この問題の影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="34a1c-211">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="34a1c-212">ハングしたアプリを閉じ、フィードバック Hub、3D ビューアー、フォトなどの他のアプリを起動すると問題が解決すると報告されているユーザーもいます。ただし、この問題は &mdash; 100% は機能しません。</span><span class="sxs-lookup"><span data-stu-id="34a1c-212">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them&mdash;however, this does not work 100% of the time.</span></span>

<span data-ttu-id="34a1c-213">この問題が原因で更新自体が発生したのではなく、OS のバグが原因で .NET Native Framework の更新プログラムが正しく処理されないという原因が根本原因です。</span><span class="sxs-lookup"><span data-stu-id="34a1c-213">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="34a1c-214">修正プログラムが特定され、修正プログラムを含む更新プログラム (OS バージョン 17763.380) がリリースされました。</span><span class="sxs-lookup"><span data-stu-id="34a1c-214">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="34a1c-215">お使いのデバイスで更新プログラムを利用できる場合は、次の方法を使用してください。</span><span class="sxs-lookup"><span data-stu-id="34a1c-215">To see if your device can take the update, please:</span></span>

1. <span data-ttu-id="34a1c-216">設定アプリに移動し、[セキュリティの更新 **] &開きます**。</span><span class="sxs-lookup"><span data-stu-id="34a1c-216">Go to the Settings app and open **Update & Security**.</span></span>

1. <span data-ttu-id="34a1c-217">[更新 **プログラムの確認] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="34a1c-217">Select **Check for Updates**.</span></span>

1. <span data-ttu-id="34a1c-218">17763.380 への更新プログラムが利用可能な場合は、このビルドに更新して、アプリハングバグの修正プログラムを受信してください。</span><span class="sxs-lookup"><span data-stu-id="34a1c-218">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug.</span></span>

1. <span data-ttu-id="34a1c-219">このバージョンの OS に更新すると、アプリは期待通り動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34a1c-219">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="34a1c-220">さらに、すべての HoloLens OS リリースと同様に、FFU イメージを Microsoft ダウンロード センター [に投稿しました](https://aka.ms/hololensdownload/10.0.17763.380)。</span><span class="sxs-lookup"><span data-stu-id="34a1c-220">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="34a1c-221">更新プログラムを利用しない場合は、3/29 の現在、Microsoft Store UWP アプリの新しいバージョンがリリースされました。</span><span class="sxs-lookup"><span data-stu-id="34a1c-221">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="34a1c-222">ストアの更新バージョンを作成した後:</span><span class="sxs-lookup"><span data-stu-id="34a1c-222">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="34a1c-223">ストアを開き、読み込み確認します。</span><span class="sxs-lookup"><span data-stu-id="34a1c-223">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="34a1c-224">ブルーム ジェスチャを使ってメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="34a1c-224">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="34a1c-225">以前に破損したアプリを開くことを試みる。</span><span class="sxs-lookup"><span data-stu-id="34a1c-225">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="34a1c-226">それでも起動できない場合は、破損したアプリのアイコンを長押ししてアンインストールを選択します。</span><span class="sxs-lookup"><span data-stu-id="34a1c-226">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="34a1c-227">ストアからこれらのアプリを再インストールします。</span><span class="sxs-lookup"><span data-stu-id="34a1c-227">Re-install these apps from the store.</span></span>

<span data-ttu-id="34a1c-228">デバイスがまだアプリを読み込めない場合は、次の手順に従って、ダウンロード センターから .NET Native Framework とランタイムのバージョンをサイドロードできます。</span><span class="sxs-lookup"><span data-stu-id="34a1c-228">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="34a1c-229">この zip [ファイルは、Microsoft](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) ダウンロード センターからダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="34a1c-229">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="34a1c-230">解凍すると、2 つのファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="34a1c-230">Unzipping will produce two files.</span></span>  <span data-ttu-id="34a1c-231">Microsoft.NET.Native.Runtime.1.7.appx と Microsoft.NET.Native.Framework.1.7.appx。</span><span class="sxs-lookup"><span data-stu-id="34a1c-231">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx.</span></span>

1. <span data-ttu-id="34a1c-232">デバイスが開発者のロックを解除されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="34a1c-232">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="34a1c-233">手順については、Windows [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) の使用に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="34a1c-233">If you haven't done that before, see [Using the Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) for instructions.</span></span>

1. <span data-ttu-id="34a1c-234">その後、Windows Device Portal にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="34a1c-234">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="34a1c-235">USB を使用してこれを行うには、ブラウザーに入力します http://127.0.0.1:10080 。</span><span class="sxs-lookup"><span data-stu-id="34a1c-235">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>

1. <span data-ttu-id="34a1c-236">Windows Device Portal をセットアップしたら、ダウンロードした 2 つのファイルを "サイド ロード" する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34a1c-236">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="34a1c-237">これを行うには、[アプリ] セクションに移動して [アプリ] を\*\*\*\* 選択するまで、左側のバーを下に移動する必要**があります**。</span><span class="sxs-lookup"><span data-stu-id="34a1c-237">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>

1. <span data-ttu-id="34a1c-238">次のような画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="34a1c-238">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="34a1c-239">「アプリのインストール」というセクションに移動\*\*\*\* し、それらの 2 つの APPX ファイルを展開した場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="34a1c-239">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="34a1c-240">一度に実行できるのは 1 つのみなので、最初の操作を選択した後、[展開] セクションの下の [移動] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34a1c-240">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="34a1c-241">次に、2 番目の APPX ファイルに対してこれを行います。</span><span class="sxs-lookup"><span data-stu-id="34a1c-241">Then do this for the second APPX file.</span></span>

   ![Windows Device Portal でアプリをSide-Loadedする](images/20190322-DevicePortal.png)
   
1. <span data-ttu-id="34a1c-243">この時点で、アプリケーションが再び動作し始め、ストアにアクセスできると思います。</span><span class="sxs-lookup"><span data-stu-id="34a1c-243">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>

1. <span data-ttu-id="34a1c-244">場合によっては、影響を受けるアプリが起動する前に、3D ビューアー アプリを起動する追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34a1c-244">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span> 

<span data-ttu-id="34a1c-245">この問題を解決するためのプロセスを完了して、お待ちしています。また、コミュニティと協力して、Mixed Reality エクスペリエンスを成功に引き続きご利用ください。</span><span class="sxs-lookup"><span data-stu-id="34a1c-245">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <span data-ttu-id="34a1c-246">デバイス更新</span><span class="sxs-lookup"><span data-stu-id="34a1c-246">Device Update</span></span>

- <span data-ttu-id="34a1c-247">新しい更新の 30 秒後に、シェルが一度消える場合があります。</span><span class="sxs-lookup"><span data-stu-id="34a1c-247">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="34a1c-248">ブルーム ジェスチャを **実行** してセッションを再開してください。</span><span class="sxs-lookup"><span data-stu-id="34a1c-248">Please perform the **bloom** gesture to resume your session.</span></span>

### <span data-ttu-id="34a1c-249">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="34a1c-249">Visual Studio</span></span>

- <span data-ttu-id="34a1c-250">HoloLens [の開発](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) に推奨される最新バージョンの Visual Studioインストールに関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="34a1c-250">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>

- <span data-ttu-id="34a1c-251">Visual Studio から HoloLens にアプリを展開すると、次のエラーが表示される場合があります。要求された操作は、ユーザーマップセクションが開いているファイルに対して実行 **できません。(HRESULT からの例外: 0x800704C8)**。</span><span class="sxs-lookup"><span data-stu-id="34a1c-251">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="34a1c-252">この場合は、もう一度やり直してください。展開は一般に成功します。</span><span class="sxs-lookup"><span data-stu-id="34a1c-252">If this happens, try again and your deployment will generally succeed.</span></span>

### <span data-ttu-id="34a1c-253">API</span><span class="sxs-lookup"><span data-stu-id="34a1c-253">API</span></span>

- <span data-ttu-id="34a1c-254">アプリケーションがユーザーの背後の [フォーカス](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) ポイントまたは標準を camera.forward に設定すると、Mixed Reality キャプチャの写真やビデオにホログラムは表示されません。</span><span class="sxs-lookup"><span data-stu-id="34a1c-254">If the application sets the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="34a1c-255">このバグが Windows で修正されるまでは、アプリケーションがフォーカス[](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity)ポイントをアクティブに設定する場合は、平面の法線がカメラ前方とは逆に設定されている必要があります (たとえば、normal = -camera.forward)。</span><span class="sxs-lookup"><span data-stu-id="34a1c-255">Until this bug is fixed in Windows, if applications actively set the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <span data-ttu-id="34a1c-256">Xbox ワイヤレス コントローラー</span><span class="sxs-lookup"><span data-stu-id="34a1c-256">Xbox Wireless Controller</span></span>

- <span data-ttu-id="34a1c-257">Xbox ワイヤレス コントローラー S は、HoloLens で使用する前に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34a1c-257">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="34a1c-258">コントローラーと[](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter)HoloLens をペアリングする前に、最新の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="34a1c-258">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>

- <span data-ttu-id="34a1c-259">Xbox ワイヤレス コントローラーの接続中に HoloLens を再起動した場合、コントローラーは HoloLens に自動的に再接続されません。</span><span class="sxs-lookup"><span data-stu-id="34a1c-259">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="34a1c-260">[ガイド] ボタンのライトは、コントローラーの電源が 3 分後にオフになるまで、遅く点滅します。</span><span class="sxs-lookup"><span data-stu-id="34a1c-260">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="34a1c-261">コントローラーを直ちに再接続するには、ライトがオフになるまでガイド ボタンを押してコントローラーの電源を切ります。</span><span class="sxs-lookup"><span data-stu-id="34a1c-261">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="34a1c-262">コントローラーの電源を再び入れ、HoloLens に再接続します。</span><span class="sxs-lookup"><span data-stu-id="34a1c-262">When you power your controller on again, it will reconnect to HoloLens.</span></span>

- <span data-ttu-id="34a1c-263">Xbox ワイヤレス コントローラーの接続中に HoloLens がスタンバイ状態になる場合、コントローラー上の入力は HoloLens を起動します。</span><span class="sxs-lookup"><span data-stu-id="34a1c-263">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="34a1c-264">使用が完了したら、コントローラーの電源をオフにすることで、これを回避できます。</span><span class="sxs-lookup"><span data-stu-id="34a1c-264">You can prevent this by powering off your controller when you are done using it.</span></span>

## <span data-ttu-id="34a1c-265">HoloLens エミュレーターの既知の問題</span><span class="sxs-lookup"><span data-stu-id="34a1c-265">Known issues for HoloLens emulator</span></span>

- <span data-ttu-id="34a1c-266">Microsoft Store のすべてのアプリがエミュレーターと互換性があるというのではありません。</span><span class="sxs-lookup"><span data-stu-id="34a1c-266">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="34a1c-267">たとえば、Young Conker と Fragments はエミュレーターで再生できません。</span><span class="sxs-lookup"><span data-stu-id="34a1c-267">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="34a1c-268">エミュレーターで PC の Web カメラを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="34a1c-268">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="34a1c-269">Windows Device Portal の Live Preview 機能はエミュレーターでは動作しません。</span><span class="sxs-lookup"><span data-stu-id="34a1c-269">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="34a1c-270">Mixed Reality のビデオや画像は引き続きキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="34a1c-270">You can still capture Mixed Reality videos and images.</span></span>
