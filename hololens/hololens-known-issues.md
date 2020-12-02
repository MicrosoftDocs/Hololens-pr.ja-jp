---
title: HoloLens の既知の問題
description: これは、HoloLens のお客様や開発者に影響を与える可能性がある既知の問題の一覧です。
keywords: トラブルシューティング、既知の問題、ヘルプ
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
ms.openlocfilehash: e5450cc41406416ec1b6e7c0bd7c8205056cb7d4
ms.sourcegitcommit: bf9a784d1b5f221d0766c5ae90efa4e9a5979b84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "11194625"
---
# <span data-ttu-id="34709-104">HoloLens の既知の問題</span><span class="sxs-lookup"><span data-stu-id="34709-104">Known issues for HoloLens</span></span>

<span data-ttu-id="34709-105">これは、HoloLens デバイスの既知の問題の最新の一覧です。</span><span class="sxs-lookup"><span data-stu-id="34709-105">This is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="34709-106">奇数の動作が表示される場合は、まずここを確認してください。</span><span class="sxs-lookup"><span data-stu-id="34709-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="34709-107">この一覧は、新しい問題が検出または報告された場合、または今後の HoloLens ソフトウェアの更新で問題が解決された場合に、更新されます。</span><span class="sxs-lookup"><span data-stu-id="34709-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="34709-108">ブロックされていない問題が見つかった場合は、 [フィードバック Hub](hololens-feedback.md)経由で HoloLens デバイスで報告してください。</span><span class="sxs-lookup"><span data-stu-id="34709-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="34709-109">問題が発生していてもブロックしている場合は、フィードバックをファイリングするだけでなく、 [サポートリクエスト](https://aka.ms/hlsupport)を提出してください。</span><span class="sxs-lookup"><span data-stu-id="34709-109">If the issue you are facing is blocking you, in addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).</span></span>

- [<span data-ttu-id="34709-110">すべての HoloLens ジェネレーションの既知の問題</span><span class="sxs-lookup"><span data-stu-id="34709-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="34709-111">HoloLens 2 デバイスの既知の問題</span><span class="sxs-lookup"><span data-stu-id="34709-111">Known issues for HoloLens 2 devices</span></span>](#known-issues-for-hololens-2-devices)
- [<span data-ttu-id="34709-112">HoloLens の既知の問題 (第1世代)</span><span class="sxs-lookup"><span data-stu-id="34709-112">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)
- [<span data-ttu-id="34709-113">HoloLens エミュレーターの既知の問題</span><span class="sxs-lookup"><span data-stu-id="34709-113">Known issues for HoloLens emulator</span></span>](#known-issues-for-hololens-emulator)

## <span data-ttu-id="34709-114">すべての HoloLens ジェネレーションの既知の問題</span><span class="sxs-lookup"><span data-stu-id="34709-114">Known issues for all HoloLens generations</span></span>

### <span data-ttu-id="34709-115">Unity</span><span class="sxs-lookup"><span data-stu-id="34709-115">Unity</span></span>

- <span data-ttu-id="34709-116">「HoloLens の開発に推奨される最新バージョンの Unity 用の [ツールをインストール](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34709-116">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="34709-117">Unity HoloLens のテクニカルプレビューの既知の問題については、「 [HoloLens Unity フォーラム](https://forum.unity3d.com/threads/known-issues.394627/)」で説明しています。</span><span class="sxs-lookup"><span data-stu-id="34709-117">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <span data-ttu-id="34709-118">Windows Device Portal</span><span class="sxs-lookup"><span data-stu-id="34709-118">Windows Device Portal</span></span>

- <span data-ttu-id="34709-119">Mixed Reality キャプチャのライブプレビュー機能は、数秒間の待機時間を示す場合があります。</span><span class="sxs-lookup"><span data-stu-id="34709-119">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="34709-120">仮想入力ページでは、[仮想ジェスチャー] セクションのジェスチャとスクロールコントロールは機能しません。</span><span class="sxs-lookup"><span data-stu-id="34709-120">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="34709-121">これらを使用しても効果はありません。</span><span class="sxs-lookup"><span data-stu-id="34709-121">Using them will have no effect.</span></span> <span data-ttu-id="34709-122">同じページの仮想キーボードは正しく動作します。</span><span class="sxs-lookup"><span data-stu-id="34709-122">The virtual keyboard on the same page works correctly.</span></span>

- <span data-ttu-id="34709-123">[設定] で開発者モードを有効にした後、デバイスポータルが有効になるまでに数秒かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="34709-123">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <span data-ttu-id="34709-124">OneDrive カメラのアップロード</span><span class="sxs-lookup"><span data-stu-id="34709-124">OneDrive camera upload</span></span>

<span data-ttu-id="34709-125">HoloLens 用の OneDrive アプリでは、職場または学校アカウントの自動カメラアップロードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="34709-125">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="34709-126">対策</span><span class="sxs-lookup"><span data-stu-id="34709-126">Workarounds:</span></span>

- <span data-ttu-id="34709-127">ビジネスで利用可能であれば、カメラの自動アップロードは、コンシューマーの Microsoft アカウントでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="34709-127">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="34709-128">職場または学校のアカウントに加えて、Microsoft アカウントにサインインすることもできます (OneDrive アプリでは、2つのサインインがサポートされています)。</span><span class="sxs-lookup"><span data-stu-id="34709-128">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="34709-129">OneDrive 内の Microsoft アカウントプロファイルで、バックグラウンドカメラロールの自動アップロードを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="34709-129">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="34709-130">写真を自動的にアップロードするためにコンシューマーの Microsoft アカウントを安全に使用できない場合は、OneDrive アプリから職場または学校のアカウントに写真を手動でアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="34709-130">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="34709-131">そのためには、OneDrive アプリで職場または学校のアカウントにサインインしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="34709-131">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="34709-132">ボタンを選択 **+** して、[ **アップロード**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="34709-132">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="34709-133">アップロードする写真またはビデオを検索するには、[ **画像 > カメラロール**に移動します。</span><span class="sxs-lookup"><span data-stu-id="34709-133">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="34709-134">アップロードする写真またはビデオを選択し、[ **開く** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="34709-134">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <span data-ttu-id="34709-135">HoloLens 2 デバイスの既知の問題</span><span class="sxs-lookup"><span data-stu-id="34709-135">Known issues for HoloLens 2 devices</span></span>

### <span data-ttu-id="34709-136">Microsoft Edge を起動できない</span><span class="sxs-lookup"><span data-stu-id="34709-136">Microsoft Edge fails to launch</span></span>

<span data-ttu-id="34709-137">一部のお客様が、Microsoft Edge を起動できないという問題が報告されました。</span><span class="sxs-lookup"><span data-stu-id="34709-137">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="34709-138">これらのユーザーの場合、この問題は再起動によって引き続き発生し、Windows またはアプリケーションの更新プログラムでは解決されません。</span><span class="sxs-lookup"><span data-stu-id="34709-138">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="34709-139">この問題が発生していて、 [windows が](hololens-updates.md#manually-check-for-updates)最新の状態であることを確認している場合は、 [フィードバック Hub アプリ](hololens-feedback.md) の次のカテゴリとサブカテゴリを使用して、フィードバックを送信してください。インストールと更新 >、windows Update のダウンロード、インストール、構成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="34709-139">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="34709-140">現時点では、根本的な問題の原因となる可能性があるため、既知の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="34709-140">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="34709-141">フィードバック Hub からバグを提出すると、調査に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="34709-141">Filing a bug via Feedback Hub will help our investigation!</span></span>

### <span data-ttu-id="34709-142">キーボードが特殊文字に切り替わりません</span><span class="sxs-lookup"><span data-stu-id="34709-142">Keyboard does not switch to special characters</span></span>

<span data-ttu-id="34709-143">OOBE 中に、ユーザーが職場または学校のアカウントを選んでパスワードを入力している場合は、&123 ボタンをタップして特殊文字に変更しないで、キーボード上の特殊文字に切り替えようとしたときに問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="34709-143">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> 

<span data-ttu-id="34709-144">回避策:</span><span class="sxs-lookup"><span data-stu-id="34709-144">Work-arounds:</span></span>
-   <span data-ttu-id="34709-145">キーボードを閉じて、テキストフィールドをタップしてもう一度開きます。</span><span class="sxs-lookup"><span data-stu-id="34709-145">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="34709-146">パスワードが間違っています。</span><span class="sxs-lookup"><span data-stu-id="34709-146">Incorrectly enter your password.</span></span> <span data-ttu-id="34709-147">次回、キーボードが relaunched されると、期待どおりに動作するようになります。</span><span class="sxs-lookup"><span data-stu-id="34709-147">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="34709-148">Web 認証の場合は、キーボードを閉じて、[ **別のデバイスからサインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="34709-148">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span> 
-   <span data-ttu-id="34709-149">数値のみを入力した場合、ユーザーは特定のキーを押したままにして展開されたメニューを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="34709-149">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="34709-150">USB キーボードを使用しています。</span><span class="sxs-lookup"><span data-stu-id="34709-150">Using a USB keyboard.</span></span>

<span data-ttu-id="34709-151">これは、次のような影響はありません。</span><span class="sxs-lookup"><span data-stu-id="34709-151">This does not affect:</span></span>
- <span data-ttu-id="34709-152">個人アカウントの使用を選択したユーザー。</span><span class="sxs-lookup"><span data-stu-id="34709-152">Users who choose to use a personal account.</span></span>

### <span data-ttu-id="34709-153">Insider ビルドを使用して、デバイス reflashed で Insider preview ビルドから登録解除した後に、青色の画面が表示される</span><span class="sxs-lookup"><span data-stu-id="34709-153">Blue screen is shown after unenrolling from Insider preview builds on a device reflashed with a Insider build</span></span>

<span data-ttu-id="34709-154">これは、Insider preview ビルドを行っているユーザーに影響を与える問題であり、新しい insider preview ビルドで HoloLens 2 を reflashed してから、Insider プログラムから登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="34709-154">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> 

<span data-ttu-id="34709-155">これは、次のような影響はありません。</span><span class="sxs-lookup"><span data-stu-id="34709-155">This does not affect:</span></span>
- <span data-ttu-id="34709-156">Windows Insider に登録されていないユーザー</span><span class="sxs-lookup"><span data-stu-id="34709-156">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="34709-157">者</span><span class="sxs-lookup"><span data-stu-id="34709-157">Insiders:</span></span>
    - <span data-ttu-id="34709-158">Insider ビルドがバージョン18362であるため、デバイスが登録されている場合</span><span class="sxs-lookup"><span data-stu-id="34709-158">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="34709-159">Insider 署名された19041ビルドをフラッシュして Insider プログラムに登録したままになっている場合</span><span class="sxs-lookup"><span data-stu-id="34709-159">If they flashed a Insider signed 19041.x build AND stay enrolled in the Insider program</span></span> 

<span data-ttu-id="34709-160">回避策:</span><span class="sxs-lookup"><span data-stu-id="34709-160">Work-around:</span></span> 
- <span data-ttu-id="34709-161">問題を回避する</span><span class="sxs-lookup"><span data-stu-id="34709-161">Avoid the issue</span></span> 
    - <span data-ttu-id="34709-162">Insider 以外のビルドをフラッシュします。</span><span class="sxs-lookup"><span data-stu-id="34709-162">Flash a non-insider build.</span></span> <span data-ttu-id="34709-163">通常の月次更新プログラムのいずれか。</span><span class="sxs-lookup"><span data-stu-id="34709-163">One of the regular monthly updates.</span></span> 
    - <span data-ttu-id="34709-164">Insider プレビューを表示する</span><span class="sxs-lookup"><span data-stu-id="34709-164">Stay on Insider Preview</span></span>
- <span data-ttu-id="34709-165">デバイスの Reflash</span><span class="sxs-lookup"><span data-stu-id="34709-165">Reflash the device</span></span>

    1. <span data-ttu-id="34709-166">接続していないときに完全に電源を切ることにより、 [HoloLens 2 を手動でフラッシュモードに](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) します。</span><span class="sxs-lookup"><span data-stu-id="34709-166">Put the [HoloLens 2 into flashing mode](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) manually by fully powering down while not connect.</span></span> <span data-ttu-id="34709-167">音量を上げながら、Power ボタンをタップします。</span><span class="sxs-lookup"><span data-stu-id="34709-167">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="34709-168">PC に接続し、アドバンスト回復コンパニオンを開きます。</span><span class="sxs-lookup"><span data-stu-id="34709-168">Connect to the PC and open Advanced Recovery Companion.</span></span> 
    
    1. <span data-ttu-id="34709-169">HoloLens 2 を既定のビルドにフラッシュします。</span><span class="sxs-lookup"><span data-stu-id="34709-169">Flash the HoloLens 2 to the default build.</span></span>   

## <span data-ttu-id="34709-170">HoloLens の既知の問題 (第1世代)</span><span class="sxs-lookup"><span data-stu-id="34709-170">Known issues for HoloLens (1st Gen)</span></span>

### <span data-ttu-id="34709-171">Visual Studio 経由で HoloLens に接続して展開できない</span><span class="sxs-lookup"><span data-stu-id="34709-171">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="34709-172">最終更新日: 8/8 @ 5: 午後11時-Visual Studio は VS 2019 バージョン16.2 をリリースしました。この問題の修正プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="34709-172">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="34709-173">このエラーが発生しないように、この最新バージョンに更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="34709-173">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="34709-174">Visual Studio は VS 2019 バージョン16.2 をリリースしました。この問題の修正プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="34709-174">Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="34709-175">このエラーが発生しないように、この最新バージョンに更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="34709-175">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="34709-176">問題の原因: visual studio 2015 または Visual Studio 2017 の早期リリースを使用しているユーザーが、HoloLens でアプリケーションを展開してデバッグし、その後、同じ HoloLens で visual Studio 2017 または Visual Studio 2019 の最新バージョンを使用している場合は、この問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="34709-176">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="34709-177">Visual Studio の新しいリリースでは、新しいバージョンのコンポーネントが展開されますが、古いバージョンのファイルはデバイス上に残っているため、新しいバージョンは失敗します。</span><span class="sxs-lookup"><span data-stu-id="34709-177">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="34709-178">これにより、次のエラーメッセージが表示されます: DEP0100: ターゲットデバイスで開発者モードが有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="34709-178">This causes the following error message: DEP0100: Please ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="34709-179">エラー80004005により、の開発者用ライセンスを取得できませんでした \<ip\> 。</span><span class="sxs-lookup"><span data-stu-id="34709-179">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <span data-ttu-id="34709-180">回避策</span><span class="sxs-lookup"><span data-stu-id="34709-180">Workaround</span></span>

<span data-ttu-id="34709-181">現在、チームは修正に向けて取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="34709-181">Our team is currently working on a fix.</span></span> <span data-ttu-id="34709-182">それまでの間、次の手順を使用して、問題を回避し、展開およびデバッグのブロックを解除することができます。</span><span class="sxs-lookup"><span data-stu-id="34709-182">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="34709-183">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="34709-183">Open Visual Studio.</span></span>

1. <span data-ttu-id="34709-184">[**ファイル**] の [  >  **新しい**  >  **プロジェクト**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="34709-184">Select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="34709-185">[ **Visual C#**  >  **Windows デスクトップ**  >  **コンソールアプリ (.net Framework)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="34709-185">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>

1. <span data-ttu-id="34709-186">プロジェクトに名前を付け ("HoloLensDeploymentFix" など)、フレームワークが少なくとも .NET Framework 4.5 に設定されていることを確認して、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="34709-186">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>

1. <span data-ttu-id="34709-187">ソリューションエクスプローラーで [ **参照設定** ] ノードを右クリックし、次の参照を追加します ([ **参照** ] セクションを選び、[ **参照**] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="34709-187">Right-click the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="34709-188">10.0.18362.0 をまだインストールしていない場合は、最新バージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="34709-188">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span> 

1. <span data-ttu-id="34709-189">ソリューションエクスプローラーでプロジェクトを右クリックし、[ **Add**  >  **既存項目**の追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="34709-189">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>

1. <span data-ttu-id="34709-190">C:\Program Files (x86) \Windows Kits\10\bin\10.0.18362.0\x86 を参照して、フィルターを \*\*すべてのファイル (\ *. \ *)** に変更します。</span><span class="sxs-lookup"><span data-stu-id="34709-190">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>

1. <span data-ttu-id="34709-191">SirepClient.dll と SshClient.dll の両方を選択して、[ **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="34709-191">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>

1. <span data-ttu-id="34709-192">ソリューションエクスプローラーで両方のファイルを見つけて選び (ファイルの一覧の一番下にある必要があります)、[**プロパティ**] ウィンドウの [**出力ディレクトリにコピー** ] を選択して、**常にコピー**します。</span><span class="sxs-lookup"><span data-stu-id="34709-192">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>

1. <span data-ttu-id="34709-193">ファイルの上部で、次のステートメントを既存のステートメント一覧に追加し `using` ます。</span><span class="sxs-lookup"><span data-stu-id="34709-193">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="34709-194">の中 `static void Main(...)` に、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="34709-194">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="34709-195">[**ビルド**  >  **ビルドソリューション**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="34709-195">Select **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="34709-196">コマンドプロンプトウィンドウを開き、コンパイルされた .exe ファイルを含むフォルダー (C:\MyProjects\HoloLensDeploymentFix\bin\Debug など) に cd を挿入します。</span><span class="sxs-lookup"><span data-stu-id="34709-196">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span></span>

1. <span data-ttu-id="34709-197">実行可能ファイルを実行して、デバイスの IP アドレスをコマンドライン引数として指定します。</span><span class="sxs-lookup"><span data-stu-id="34709-197">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="34709-198">(USB を使って接続している場合は、127.0.0.1 を使用できます。それ以外の場合は、デバイスの Wi-Fi IP アドレスを使用してください)。 たとえば、"HoloLensDeploymentFix 127.0.0.1" とします。</span><span class="sxs-lookup"><span data-stu-id="34709-198">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1".</span></span>

1. <span data-ttu-id="34709-199">すべてのメッセージが表示されることなくツールが終了すると (数秒しかかかりません)、Visual Studio 2017 以降から展開とデバッグを行うことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="34709-199">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="34709-200">引き続きこのツールを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="34709-200">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="34709-201">利用可能になったら、さらに更新プログラムを提供します。</span><span class="sxs-lookup"><span data-stu-id="34709-201">We will provide further updates as they become available.</span></span>

### <span data-ttu-id="34709-202">HoloLens での Microsoft ストアとアプリの起動に関する問題</span><span class="sxs-lookup"><span data-stu-id="34709-202">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="34709-203">最終更新: 4/2 @ 10 AM-問題が解決されました。</span><span class="sxs-lookup"><span data-stu-id="34709-203">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span> 

<span data-ttu-id="34709-204">HoloLens で Microsoft Store とアプリを起動しようとすると、問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="34709-204">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="34709-205">バックグラウンドアプリの更新によって、1つ以上の依存アプリが実行されているときに、新しいバージョンの framework パッケージが特定のシーケンスで展開されると、問題が発生すると判断されました。</span><span class="sxs-lookup"><span data-stu-id="34709-205">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="34709-206">この場合、アプリの自動更新によって新しいバージョンの .NET ネイティブフレームワーク (バージョン10.0.25531 から 10.0.27413) が提供されたため、実行中のアプリは、以前のバージョンのフレームワークを使用するすべての実行中のアプリで正しく更新されませんでした。</span><span class="sxs-lookup"><span data-stu-id="34709-206">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="34709-207">フレームワークの更新のフローは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="34709-207">The flow for framework update is as follows:</span></span> 

1. <span data-ttu-id="34709-208">新しいフレームワークパッケージがストアからダウンロードされ、インストールされます。</span><span class="sxs-lookup"><span data-stu-id="34709-208">The new framework package is downloaded from the store and installed.</span></span>

1. <span data-ttu-id="34709-209">以前のフレームワークを使用しているすべてのアプリは、新しいバージョンを使用するために ' 更新されています。</span><span class="sxs-lookup"><span data-stu-id="34709-209">All apps using the older framework are 'updated' to use the newer version.</span></span>

<span data-ttu-id="34709-210">ステップ2が完了する前に中断された場合、新しいフレームワークが登録されていないアプリは、[スタート] メニューから起動できません。</span><span class="sxs-lookup"><span data-stu-id="34709-210">If step 2 is interrupted before completion then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="34709-211">HoloLens 上のアプリは、この問題の影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="34709-211">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="34709-212">ハングしたアプリを閉じて、フィードバック Hub、3D Viewer、または写真などの他のアプリを起動すると、問題が解決されるという報告がありましたが、その場合、 &mdash; 100% は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="34709-212">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them&mdash;however, this does not work 100% of the time.</span></span>

<span data-ttu-id="34709-213">この問題によって更新プログラム自体は発生しませんでしたが、この問題は、.NET ネイティブフレームワークの更新によって不適切に処理されたバグであると考えられています。</span><span class="sxs-lookup"><span data-stu-id="34709-213">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="34709-214">修正プログラムを特定し、修正プログラム (OS バージョン 17763.380) をリリースしたことをお知らせします。</span><span class="sxs-lookup"><span data-stu-id="34709-214">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="34709-215">デバイスが更新プログラムを受け取ることができるかどうかを確認するには、次のことを行ってください。</span><span class="sxs-lookup"><span data-stu-id="34709-215">To see if your device can take the update, please:</span></span>

1. <span data-ttu-id="34709-216">[設定] アプリに移動して、[ **更新 & セキュリティ**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="34709-216">Go to the Settings app and open **Update & Security**.</span></span>

1. <span data-ttu-id="34709-217">[ **更新プログラムの確認**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="34709-217">Select **Check for Updates**.</span></span>

1. <span data-ttu-id="34709-218">17763.380 への更新プログラムが利用できる場合は、このビルドに更新して、アプリのハングバグの修正プログラムを入手してください。</span><span class="sxs-lookup"><span data-stu-id="34709-218">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug.</span></span>

1. <span data-ttu-id="34709-219">このバージョンの OS への更新時に、アプリは期待どおりに動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34709-219">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="34709-220">さらに、すべての HoloLens OS リリースの場合と同様に、 [Microsoft ダウンロードセンター](https://aka.ms/hololensdownload/10.0.17763.380)に ffu イメージを投稿しました。</span><span class="sxs-lookup"><span data-stu-id="34709-220">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="34709-221">更新を実行したくない場合は、3/29 の時点で新しいバージョンの Microsoft Store UWP アプリをリリースしました。</span><span class="sxs-lookup"><span data-stu-id="34709-221">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="34709-222">ストアの更新版を入手したら、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="34709-222">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="34709-223">ストアを開いて、読み込まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="34709-223">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="34709-224">ブルームジェスチャを使用してメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="34709-224">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="34709-225">以前に壊れたアプリを開こうとしています。</span><span class="sxs-lookup"><span data-stu-id="34709-225">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="34709-226">それでも起動できない場合は、破損したアプリのアイコンをタップして押し続け、[アンインストール] を選びます。</span><span class="sxs-lookup"><span data-stu-id="34709-226">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="34709-227">これらのアプリをストアから再インストールします。</span><span class="sxs-lookup"><span data-stu-id="34709-227">Re-install these apps from the store.</span></span>

<span data-ttu-id="34709-228">デバイスで依然としてアプリを読み込むことができない場合は、次の手順に従って、ダウンロードセンターから .NET ネイティブフレームワークとランタイムのバージョンをサイドローディングできます。</span><span class="sxs-lookup"><span data-stu-id="34709-228">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="34709-229">Microsoft ダウンロードセンターから [この zip ファイル](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="34709-229">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="34709-230">解凍すると、2つのファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="34709-230">Unzipping will produce two files.</span></span>  <span data-ttu-id="34709-231">"NET.TCP. .appx. .appx" というように、.appx というようにします。</span><span class="sxs-lookup"><span data-stu-id="34709-231">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx.</span></span>

1. <span data-ttu-id="34709-232">デバイスが dev のロック解除されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="34709-232">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="34709-233">この作業をまだ行っていない場合は、「 [Windows Device Portal を使っ](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) て手順を確認する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34709-233">If you haven't done that before, see [Using the Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) for instructions.</span></span>

1. <span data-ttu-id="34709-234">次に、Windows Device Portal にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="34709-234">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="34709-235">この操作は USB 経由で行うことをお勧めします。そのためには、 http://127.0.0.1:10080 ブラウザーに入力します。</span><span class="sxs-lookup"><span data-stu-id="34709-235">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>

1. <span data-ttu-id="34709-236">Windows Device Portal を起動したら、ダウンロードした2つのファイルを "サイドロード" する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34709-236">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="34709-237">そのためには、左側のバーに移動して [ **アプリ** ] セクションに移動し、[ **アプリ**] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34709-237">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>

1. <span data-ttu-id="34709-238">次のような画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="34709-238">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="34709-239">[ **アプリのインストール** ] というセクションに移動して、2つの APPX ファイルを解凍した場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="34709-239">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="34709-240">一度に1つしか実行できないため、最初の1つを選んでから、[展開] セクションの [移動] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34709-240">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="34709-241">次に、2つ目の APPX ファイルに対してこれを行います。</span><span class="sxs-lookup"><span data-stu-id="34709-241">Then do this for the second APPX file.</span></span>

   ![Side-Loaded アプリをインストールするための Windows Device Portal](images/20190322-DevicePortal.png)
   
1. <span data-ttu-id="34709-243">この時点で、アプリケーションは再び動作を開始する必要があり、ストアにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="34709-243">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>

1. <span data-ttu-id="34709-244">場合によっては、影響を受けるアプリが起動する前に、3D ビューアーアプリを起動するための追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34709-244">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span> 

<span data-ttu-id="34709-245">この問題を解決するための手続きを行っていますので、この問題を解決するためのご協力をお願いいたします。 skype では、共同作業を成功させるために、コミュニティを引き続き活用していきます。</span><span class="sxs-lookup"><span data-stu-id="34709-245">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <span data-ttu-id="34709-246">デバイスの更新</span><span class="sxs-lookup"><span data-stu-id="34709-246">Device Update</span></span>

- <span data-ttu-id="34709-247">30秒後に新しい更新プログラムを実行すると、シェルが1回表示されなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="34709-247">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="34709-248">セッションを再開するには、 **ブルーム** ジェスチャを実行してください。</span><span class="sxs-lookup"><span data-stu-id="34709-248">Please perform the **bloom** gesture to resume your session.</span></span>

### <span data-ttu-id="34709-249">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="34709-249">Visual Studio</span></span>

- <span data-ttu-id="34709-250">「HoloLens の開発に推奨される最新バージョンの Visual Studio 用の [ツールをインストール](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34709-250">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>

- <span data-ttu-id="34709-251">Visual Studio から HoloLens にアプリを展開すると、次のエラーが表示されることがあります。要求された操作は、ユーザーによってマップされた **セクションが開いているファイルでは実行できません。(HRESULT: 0x800704C8 の例外)**。</span><span class="sxs-lookup"><span data-stu-id="34709-251">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="34709-252">この問題が発生した場合は、通常、展開は成功します。</span><span class="sxs-lookup"><span data-stu-id="34709-252">If this happens, try again and your deployment will generally succeed.</span></span>

### <span data-ttu-id="34709-253">API</span><span class="sxs-lookup"><span data-stu-id="34709-253">API</span></span>

- <span data-ttu-id="34709-254">ユーザーまたは通常のカメラに [フォーカスポイント](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) を設定すると、ホログラムは Mixed Reality キャプチャ写真またはビデオに表示されません。</span><span class="sxs-lookup"><span data-stu-id="34709-254">If the application sets the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="34709-255">このバグが Windows で修正されるまでは、アプリケーションが [フォーカスポイント](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) をアクティブに設定した場合、機体の法線が反対のカメラフォワード (たとえば、normal =-camera. forward) に設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34709-255">Until this bug is fixed in Windows, if applications actively set the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <span data-ttu-id="34709-256">Xbox ワイヤレス コントローラー</span><span class="sxs-lookup"><span data-stu-id="34709-256">Xbox Wireless Controller</span></span>

- <span data-ttu-id="34709-257">Xbox ワイヤレスコントローラー S は、HoloLens で使用する前に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34709-257">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="34709-258">HoloLens とコントローラーをペアリングしようとする前に、 [最新](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) の状態であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="34709-258">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>

- <span data-ttu-id="34709-259">Xbox ワイヤレスコントローラーが接続されているときに HoloLens を再起動すると、コントローラーが HoloLens に自動的に再接続されることはありません。</span><span class="sxs-lookup"><span data-stu-id="34709-259">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="34709-260">[ガイド] ボタンのライトは、3分後にコントローラーの電源が切れるまでゆっくり点滅します。</span><span class="sxs-lookup"><span data-stu-id="34709-260">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="34709-261">コントローラーをすぐに再接続するには、ライトがオフになるまでガイドボタンを押してコントローラーの電源を切ります。</span><span class="sxs-lookup"><span data-stu-id="34709-261">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="34709-262">コントローラーの電源を入れ直すと、HoloLens に再接続されます。</span><span class="sxs-lookup"><span data-stu-id="34709-262">When you power your controller on again, it will reconnect to HoloLens.</span></span>

- <span data-ttu-id="34709-263">Xbox ワイヤレスコントローラーが接続されているときに HoloLens がスタンバイ状態になると、コントローラーでの入力によって HoloLens が復帰します。</span><span class="sxs-lookup"><span data-stu-id="34709-263">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="34709-264">この機能を使用したら、コントローラーの電源を切ることで、これを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="34709-264">You can prevent this by powering off your controller when you are done using it.</span></span>

## <span data-ttu-id="34709-265">HoloLens エミュレーターの既知の問題</span><span class="sxs-lookup"><span data-stu-id="34709-265">Known issues for HoloLens emulator</span></span>

- <span data-ttu-id="34709-266">Microsoft Store のすべてのアプリがエミュレーターと互換性があるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="34709-266">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="34709-267">たとえば、ヤングと断片はエミュレーターでは再生できません。</span><span class="sxs-lookup"><span data-stu-id="34709-267">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="34709-268">エミュレーターで PC web カメラを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="34709-268">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="34709-269">Windows Device Portal のリアルタイムのプレビュー機能は、エミュレーターでは動作しません。</span><span class="sxs-lookup"><span data-stu-id="34709-269">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="34709-270">ただし、Mixed Reality のビデオとイメージをキャプチャすることもできます。</span><span class="sxs-lookup"><span data-stu-id="34709-270">You can still capture Mixed Reality videos and images.</span></span>
