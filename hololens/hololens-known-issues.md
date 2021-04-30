---
title: HoloLens の既知の問題
description: Unity と Windows デバイスポータルを使用する HoloLens のお客様と開発者に影響を与える可能性のある既知の問題と回避策の一覧については、最新情報をご確認ください。
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
ms.openlocfilehash: 54bc090352983e814c64deea8f1f401c24e3261b
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309561"
---
# <a name="known-issues-for-hololens"></a><span data-ttu-id="7d13a-104">HoloLens の既知の問題</span><span class="sxs-lookup"><span data-stu-id="7d13a-104">Known issues for HoloLens</span></span>

<span data-ttu-id="7d13a-105">これは、HoloLens デバイスの既知の問題の現在の一覧です。</span><span class="sxs-lookup"><span data-stu-id="7d13a-105">This is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="7d13a-106">奇妙な動作が見られる場合は、まずこのチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="7d13a-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="7d13a-107">この一覧は、新しい問題が検出または報告されたとき、または将来の HoloLens ソフトウェア更新プログラムで問題が解決されると、更新されたままになります。</span><span class="sxs-lookup"><span data-stu-id="7d13a-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="7d13a-108">ブロックされていない問題が検出された場合は、 [フィードバックハブ](hololens-feedback.md)を使用して HoloLens デバイスで報告してください。</span><span class="sxs-lookup"><span data-stu-id="7d13a-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="7d13a-109">問題が発生している場合は、フィードバックを提出するだけでなく、 [サポート要求](https://aka.ms/hlsupport)を提出してください。</span><span class="sxs-lookup"><span data-stu-id="7d13a-109">If the issue you are facing is blocking you, in addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).</span></span>

- [<span data-ttu-id="7d13a-110">すべての HoloLens の世代に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="7d13a-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="7d13a-111">HoloLens 2 デバイスに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="7d13a-111">Known issues for HoloLens 2 devices</span></span>](#known-issues-for-hololens-2-devices)
- [<span data-ttu-id="7d13a-112">HoloLens の既知の問題 (第1世代)</span><span class="sxs-lookup"><span data-stu-id="7d13a-112">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)
- [<span data-ttu-id="7d13a-113">HoloLens エミュレーターの既知の問題</span><span class="sxs-lookup"><span data-stu-id="7d13a-113">Known issues for HoloLens emulator</span></span>](#known-issues-for-hololens-emulator)

## <a name="known-issues-for-all-hololens-generations"></a><span data-ttu-id="7d13a-114">すべての HoloLens の世代に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="7d13a-114">Known issues for all HoloLens generations</span></span>

### <a name="unity"></a><span data-ttu-id="7d13a-115">Unity</span><span class="sxs-lookup"><span data-stu-id="7d13a-115">Unity</span></span>

- <span data-ttu-id="7d13a-116">「HoloLens の開発に推奨される最新バージョンの Unity 用の [ツールをインストール](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d13a-116">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="7d13a-117">Unity HoloLens Technical Preview の既知の問題については、 [Hololens Unity フォーラム](https://forum.unity3d.com/threads/known-issues.394627/)に記載されています。</span><span class="sxs-lookup"><span data-stu-id="7d13a-117">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <a name="windows-device-portal"></a><span data-ttu-id="7d13a-118">Windows デバイス ポータル</span><span class="sxs-lookup"><span data-stu-id="7d13a-118">Windows Device Portal</span></span>

- <span data-ttu-id="7d13a-119">Mixed Reality キャプチャのライブプレビュー機能は、数秒の待機時間が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="7d13a-119">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="7d13a-120">[仮想入力] ページで、[仮想ジェスチャ] セクションのジェスチャとスクロールコントロールが機能していません。</span><span class="sxs-lookup"><span data-stu-id="7d13a-120">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="7d13a-121">使用すると、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="7d13a-121">Using them will have no effect.</span></span> <span data-ttu-id="7d13a-122">同じページ上の仮想キーボードが正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-122">The virtual keyboard on the same page works correctly.</span></span>

- <span data-ttu-id="7d13a-123">[設定] で開発者モードを有効にした後、デバイスポータルをオンにするスイッチが有効になるまで数秒かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="7d13a-123">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <a name="onedrive-camera-upload"></a><span data-ttu-id="7d13a-124">OneDrive カメラのアップロード</span><span class="sxs-lookup"><span data-stu-id="7d13a-124">OneDrive camera upload</span></span>

<span data-ttu-id="7d13a-125">HoloLens 用の OneDrive アプリでは、職場または学校アカウントのカメラの自動アップロードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7d13a-125">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="7d13a-126">回避策:</span><span class="sxs-lookup"><span data-stu-id="7d13a-126">Workarounds:</span></span>

- <span data-ttu-id="7d13a-127">お客様のビジネスで利用可能な場合、カメラの自動アップロードはコンシューマーの Microsoft アカウントでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7d13a-127">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="7d13a-128">職場または学校のアカウントに加えて、Microsoft アカウントにサインインできます (OneDrive アプリではデュアルサインインがサポートされています)。</span><span class="sxs-lookup"><span data-stu-id="7d13a-128">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="7d13a-129">OneDrive 内の Microsoft アカウントプロファイルから、自動、バックグラウンドカメラロールのアップロードを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-129">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="7d13a-130">写真を自動的にアップロードするためにコンシューマー Microsoft アカウントを安全に使用できない場合は、OneDrive アプリから職場または学校のアカウントに写真を手動でアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-130">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="7d13a-131">これを行うには、OneDrive アプリの職場または学校アカウントにサインインしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-131">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="7d13a-132">ボタンを選択 **+** し、[ **アップロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-132">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="7d13a-133">[ **ピクチャ > カメラロール** に移動して、アップロードする写真またはビデオを検索します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-133">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="7d13a-134">アップロードする写真またはビデオを選択し、[ **開く** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-134">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <a name="known-issues-for-hololens-2-devices"></a><span data-ttu-id="7d13a-135">HoloLens 2 デバイスに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="7d13a-135">Known issues for HoloLens 2 devices</span></span>

### <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="7d13a-136">Microsoft Edge を起動できない</span><span class="sxs-lookup"><span data-stu-id="7d13a-136">Microsoft Edge fails to launch</span></span>

<span data-ttu-id="7d13a-137">いくつかのお客様が、Microsoft Edge の起動に失敗したという問題を報告しています。</span><span class="sxs-lookup"><span data-stu-id="7d13a-137">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="7d13a-138">このようなお客様の場合、問題は再起動によって引き続き発生し、Windows またはアプリケーションの更新プログラムでは解決されません。</span><span class="sxs-lookup"><span data-stu-id="7d13a-138">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="7d13a-139">この問題が発生していて、 [Windows が](hololens-updates.md#manually-check-for-updates)最新の状態であることを確認した場合は、 [フィードバックハブアプリ](hololens-feedback.md) から次のカテゴリとサブカテゴリを使用してバグを報告してください。インストールと更新 > Windows Update のダウンロード、インストール、および構成を行います。</span><span class="sxs-lookup"><span data-stu-id="7d13a-139">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="7d13a-140">これまでに根本原因を根本的に解決できないため、既知の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="7d13a-140">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="7d13a-141">フィードバックハブを使用してバグを提出すると、調査に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-141">Filing a bug via Feedback Hub will help our investigation!</span></span>

### <a name="keyboard-does-not-switch-to-special-characters"></a><span data-ttu-id="7d13a-142">キーボードは特殊文字に切り替わりません。</span><span class="sxs-lookup"><span data-stu-id="7d13a-142">Keyboard does not switch to special characters</span></span>

<span data-ttu-id="7d13a-143">OOBE 中に、ユーザーが職場または学校のアカウントを選択してパスワードを入力した後に、[&123] ボタンをタップしてキーボードの特殊文字に切り替えようとしたときに、特殊文字に変更されないという問題があります。</span><span class="sxs-lookup"><span data-stu-id="7d13a-143">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> 

<span data-ttu-id="7d13a-144">回避策:</span><span class="sxs-lookup"><span data-stu-id="7d13a-144">Work-arounds:</span></span>
-   <span data-ttu-id="7d13a-145">キーボードを閉じて、[テキスト] フィールドをタップして再度開きます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-145">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="7d13a-146">パスワードが正しく入力できません。</span><span class="sxs-lookup"><span data-stu-id="7d13a-146">Incorrectly enter your password.</span></span> <span data-ttu-id="7d13a-147">キーボードが次に再起動されると、正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-147">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="7d13a-148">Web 認証。キーボードを閉じ、[ **別のデバイスからサインイン** する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-148">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span> 
-   <span data-ttu-id="7d13a-149">数値のみを入力した場合、ユーザーは特定のキーを押したままにして、展開されたメニューを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-149">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="7d13a-150">USB キーボードを使用する。</span><span class="sxs-lookup"><span data-stu-id="7d13a-150">Using a USB keyboard.</span></span>

<span data-ttu-id="7d13a-151">これは、次のようには影響しません。</span><span class="sxs-lookup"><span data-stu-id="7d13a-151">This does not affect:</span></span>
- <span data-ttu-id="7d13a-152">個人のアカウントを使用することを選択したユーザー。</span><span class="sxs-lookup"><span data-stu-id="7d13a-152">Users who choose to use a personal account.</span></span>

### <a name="blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build"></a><span data-ttu-id="7d13a-153">Insider build を使用してデバイス reflashed に Insider preview ビルドから登録解除した後にブルースクリーンが表示される</span><span class="sxs-lookup"><span data-stu-id="7d13a-153">Blue screen is shown after unenrolling from Insider preview builds on a device reflashed with a Insider build</span></span>

<span data-ttu-id="7d13a-154">これは、Insider preview ビルドで、HoloLens 2 を新しい insider preview ビルドで reflashed、Insider プログラムから登録解除されたユーザーに影響する問題です。</span><span class="sxs-lookup"><span data-stu-id="7d13a-154">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> 

<span data-ttu-id="7d13a-155">これは、次のようには影響しません。</span><span class="sxs-lookup"><span data-stu-id="7d13a-155">This does not affect:</span></span>
- <span data-ttu-id="7d13a-156">Windows Insider に登録されていないユーザー</span><span class="sxs-lookup"><span data-stu-id="7d13a-156">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="7d13a-157">Insider</span><span class="sxs-lookup"><span data-stu-id="7d13a-157">Insiders:</span></span>
    - <span data-ttu-id="7d13a-158">Insider ビルドがバージョン 18362. x であるためにデバイスが登録されている場合</span><span class="sxs-lookup"><span data-stu-id="7d13a-158">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="7d13a-159">内部で署名された19041ビルドをフラッシュし、Insider プログラムに登録したままにする場合</span><span class="sxs-lookup"><span data-stu-id="7d13a-159">If they flashed a Insider signed 19041.x build AND stay enrolled in the Insider program</span></span> 

<span data-ttu-id="7d13a-160">回避策:</span><span class="sxs-lookup"><span data-stu-id="7d13a-160">Work-around:</span></span> 
- <span data-ttu-id="7d13a-161">問題を回避する</span><span class="sxs-lookup"><span data-stu-id="7d13a-161">Avoid the issue</span></span> 
    - <span data-ttu-id="7d13a-162">Insider 以外のビルドをフラッシュします。</span><span class="sxs-lookup"><span data-stu-id="7d13a-162">Flash a non-insider build.</span></span> <span data-ttu-id="7d13a-163">毎月の定期的な更新の1つ。</span><span class="sxs-lookup"><span data-stu-id="7d13a-163">One of the regular monthly updates.</span></span> 
    - <span data-ttu-id="7d13a-164">Insider Preview を維持</span><span class="sxs-lookup"><span data-stu-id="7d13a-164">Stay on Insider Preview</span></span>
- <span data-ttu-id="7d13a-165">デバイスの更新</span><span class="sxs-lookup"><span data-stu-id="7d13a-165">Reflash the device</span></span>

    1. <span data-ttu-id="7d13a-166">接続しないで完全に電源を切ることによって、HoloLens 2 を手動で [点滅モードに](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-166">Put the [HoloLens 2 into flashing mode](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) manually by fully powering down while not connect.</span></span> <span data-ttu-id="7d13a-167">音量を上げたまま、[電源] ボタンをタップします。</span><span class="sxs-lookup"><span data-stu-id="7d13a-167">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="7d13a-168">PC に接続し、Advanced Recovery コンパニオンを開きます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-168">Connect to the PC and open Advanced Recovery Companion.</span></span> 
    
    1. <span data-ttu-id="7d13a-169">HoloLens 2 を既定のビルドにフラッシュします。</span><span class="sxs-lookup"><span data-stu-id="7d13a-169">Flash the HoloLens 2 to the default build.</span></span>   

## <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="7d13a-170">HoloLens の既知の問題 (第1世代)</span><span class="sxs-lookup"><span data-stu-id="7d13a-170">Known issues for HoloLens (1st Gen)</span></span>

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a><span data-ttu-id="7d13a-171">Visual Studio を使用して HoloLens に接続して展開できない</span><span class="sxs-lookup"><span data-stu-id="7d13a-171">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="7d13a-172">最終更新: 8/8 @ 5: 午後11時-Visual Studio は、この問題の修正を含む VS 2019 バージョン16.2 をリリースしました。</span><span class="sxs-lookup"><span data-stu-id="7d13a-172">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="7d13a-173">このエラーが発生しないように、この最新バージョンに更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7d13a-173">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="7d13a-174">Visual Studio には、この問題の修正を含む VS 2019 バージョン16.2 がリリースされています。</span><span class="sxs-lookup"><span data-stu-id="7d13a-174">Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="7d13a-175">このエラーが発生しないように、この最新バージョンに更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7d13a-175">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="7d13a-176">問題の根本原因: visual studio 2015 または Visual Studio 2017 の初期リリースを使用して、HoloLens でアプリケーションをデプロイおよびデバッグした後、同じ HoloLens で最新バージョンの Visual Studio 2017 または Visual Studio 2019 を使用したユーザーが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-176">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="7d13a-177">新しいリリースの Visual Studio では、新しいバージョンのコンポーネントが配置されますが、古いバージョンのファイルはデバイス上に残されるため、新しいバージョンのエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-177">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="7d13a-178">これにより、DEP0100: ターゲットデバイスの開発者モードが有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7d13a-178">This causes the following error message: DEP0100: Please ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="7d13a-179">エラー80004005が発生したため、で開発者ライセンスを取得できませんでした \<ip\> 。</span><span class="sxs-lookup"><span data-stu-id="7d13a-179">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <a name="workaround"></a><span data-ttu-id="7d13a-180">回避策</span><span class="sxs-lookup"><span data-stu-id="7d13a-180">Workaround</span></span>

<span data-ttu-id="7d13a-181">現在、チームは修正を行っています。</span><span class="sxs-lookup"><span data-stu-id="7d13a-181">Our team is currently working on a fix.</span></span> <span data-ttu-id="7d13a-182">それまでの間は、次の手順を使用して問題を回避し、デプロイとデバッグのブロックを解除できます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-182">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="7d13a-183">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-183">Open Visual Studio.</span></span>

1. <span data-ttu-id="7d13a-184">**[File]**  >  **[New]**  >  **[Project]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-184">Select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="7d13a-185">[ **Visual C#**  >  **Windows デスクトップ**  >  **コンソールアプリ (.NET Framework)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-185">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>

1. <span data-ttu-id="7d13a-186">プロジェクトに名前 ("HoloLensDeploymentFix" など) を付け、フレームワークが少なくとも .NET Framework 4.5 に設定されていることを確認してから、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-186">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>

1. <span data-ttu-id="7d13a-187">ソリューションエクスプローラーの [ **参照** ] ノードを右クリックし、次の参照を追加します ([ **参照** ] セクションを選択し、[ **参照**] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="7d13a-187">Right-click the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="7d13a-188">10.0.18362.0 がインストールされていない場合は、最新バージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-188">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span> 

1. <span data-ttu-id="7d13a-189">ソリューションエクスプローラーでプロジェクトを右クリックし、[   >  **既存項目** の追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-189">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>

1. <span data-ttu-id="7d13a-190">C:\Program Files (x86) \Windows Kits\10\bin\10.0.18362.0\x86 を参照し、フィルターを **すべてのファイル ( \* . \* )** に変更します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-190">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>

1. <span data-ttu-id="7d13a-191">[SirepClient.dll と SshClient.dll の両方を選択し、[ **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-191">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>

1. <span data-ttu-id="7d13a-192">ソリューションエクスプローラーで両方のファイルを見つけて選択し (ファイルの一覧の一番下にある必要があります)、[**プロパティ**] ウィンドウで [**出力ディレクトリにコピー** ] を [**常にコピー** する] に変更します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-192">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>

1. <span data-ttu-id="7d13a-193">ファイルの先頭に、ステートメントの既存のリストに次のを追加し `using` ます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-193">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="7d13a-194">内 `static void Main(...)` に、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-194">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="7d13a-195">**[ビルド]**  >  **[ソリューションのビルド]** を順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-195">Select **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="7d13a-196">コマンドプロンプトウィンドウを開き、コンパイルされた .exe ファイルを含むフォルダー (たとえば、C:\MyProjects\HoloLensDeploymentFix\bin\Debug) に cd を開きます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-196">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span></span>

1. <span data-ttu-id="7d13a-197">実行可能ファイルを実行し、デバイスの IP アドレスをコマンドライン引数として指定します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-197">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="7d13a-198">(USB を使用して接続されている場合は、127.0.0.1 を使用できます。それ以外の場合は、デバイスの Wi-Fi IP アドレスを使用します)。 たとえば、"HoloLensDeploymentFix 127.0.0.1" のようになります。</span><span class="sxs-lookup"><span data-stu-id="7d13a-198">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1".</span></span>

1. <span data-ttu-id="7d13a-199">ツールがメッセージなしで終了した後 (これには数秒しかかかりません)、Visual Studio 2017 以降からデプロイおよびデバッグできるようになります。</span><span class="sxs-lookup"><span data-stu-id="7d13a-199">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="7d13a-200">ツールを引き続き使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7d13a-200">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="7d13a-201">利用可能になると、さらに更新プログラムを提供します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-201">We will provide further updates as they become available.</span></span>

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a><span data-ttu-id="7d13a-202">HoloLens での Microsoft Store とアプリの起動に関する問題</span><span class="sxs-lookup"><span data-stu-id="7d13a-202">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="7d13a-203">最終更新日時: 4/2 @ 10 AM-問題が解決されました。</span><span class="sxs-lookup"><span data-stu-id="7d13a-203">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span> 

<span data-ttu-id="7d13a-204">HoloLens で Microsoft Store とアプリを起動しようとすると、問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="7d13a-204">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="7d13a-205">この問題が発生するのは、バックグラウンドアプリの更新プログラムによって、特定のシーケンスで新しいバージョンのフレームワークパッケージが配置されているにもかかわらず、1つまたは複数の依存アプリがまだ実行中である場合です。</span><span class="sxs-lookup"><span data-stu-id="7d13a-205">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="7d13a-206">この場合、アプリの自動更新によって新しいバージョンの .NET Native Framework (バージョン10.0.25531 から 10.0.27413) が提供されたため、以前のバージョンのフレームワークを使用している実行中のすべてのアプリに対して、実行中のアプリが正しく更新されませんでした。</span><span class="sxs-lookup"><span data-stu-id="7d13a-206">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="7d13a-207">Framework 更新のフローは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7d13a-207">The flow for framework update is as follows:</span></span> 

1. <span data-ttu-id="7d13a-208">新しいフレームワークパッケージがストアからダウンロードされ、インストールされます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-208">The new framework package is downloaded from the store and installed.</span></span>

1. <span data-ttu-id="7d13a-209">古いフレームワークを使用しているすべてのアプリは、新しいバージョンを使用するように "更新" されます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-209">All apps using the older framework are 'updated' to use the newer version.</span></span>

<span data-ttu-id="7d13a-210">手順 2. が完了する前に中断された場合、新しいフレームワークが登録されていないアプリは [スタート] メニューから起動できません。</span><span class="sxs-lookup"><span data-stu-id="7d13a-210">If step 2 is interrupted before completion then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="7d13a-211">HoloLens のアプリは、この問題の影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7d13a-211">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="7d13a-212">一部のユーザーは、ハングしたアプリを終了し、フィードバックハブ、3D ビューアー、写真などの他のアプリを起動すると、問題が解決しますが、 &mdash; 100% の時間は機能しません。</span><span class="sxs-lookup"><span data-stu-id="7d13a-212">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them&mdash;however, this does not work 100% of the time.</span></span>

<span data-ttu-id="7d13a-213">根本が発生したため、この問題は更新プログラム自体の原因ではなく、.NET Native framework の更新プログラムが正しく処理されなかった OS のバグが発生しました。</span><span class="sxs-lookup"><span data-stu-id="7d13a-213">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="7d13a-214">修正を特定し、修正を含む更新プログラム (OS バージョン 17763.380) をリリースしたことをお知らせします。</span><span class="sxs-lookup"><span data-stu-id="7d13a-214">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="7d13a-215">デバイスで更新プログラムを取得できるかどうかを確認するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="7d13a-215">To see if your device can take the update, please:</span></span>

1. <span data-ttu-id="7d13a-216">設定アプリにアクセスし、[ **Update & Security**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-216">Go to the Settings app and open **Update & Security**.</span></span>

1. <span data-ttu-id="7d13a-217">[ **更新プログラムの確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-217">Select **Check for Updates**.</span></span>

1. <span data-ttu-id="7d13a-218">17763.380 への更新が利用可能な場合は、このビルドに更新して、アプリのハングバグの修正を受け取るようにしてください。</span><span class="sxs-lookup"><span data-stu-id="7d13a-218">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug.</span></span>

1. <span data-ttu-id="7d13a-219">このバージョンの OS に更新すると、アプリは想定どおりに動作するはずです。</span><span class="sxs-lookup"><span data-stu-id="7d13a-219">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="7d13a-220">さらに、HoloLens OS のすべてのリリースで、 [Microsoft ダウンロードセンター](https://aka.ms/hololensdownload/10.0.17763.380)に ffu イメージを投稿しました。</span><span class="sxs-lookup"><span data-stu-id="7d13a-220">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="7d13a-221">更新を希望しない場合は、3/29 の時点で Microsoft Store UWP アプリの新しいバージョンをリリースしました。</span><span class="sxs-lookup"><span data-stu-id="7d13a-221">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="7d13a-222">更新されたバージョンのストアを作成したら、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="7d13a-222">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="7d13a-223">ストアを開き、それが読み込まれることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-223">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="7d13a-224">ブルームジェスチャを使用してメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-224">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="7d13a-225">以前に破損したアプリを開こうとしました。</span><span class="sxs-lookup"><span data-stu-id="7d13a-225">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="7d13a-226">それでも起動できない場合は、壊れているアプリのアイコンをタップしたままにして、[アンインストール] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-226">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="7d13a-227">これらのアプリをストアから再インストールします。</span><span class="sxs-lookup"><span data-stu-id="7d13a-227">Re-install these apps from the store.</span></span>

<span data-ttu-id="7d13a-228">デバイスがまだアプリを読み込むことができない場合は、次の手順に従って、ダウンロードセンターで .NET Native Framework および Runtime のバージョンをサイドロードできます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-228">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="7d13a-229">[この zip ファイル](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip)は、Microsoft ダウンロードセンターからダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="7d13a-229">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="7d13a-230">解凍すると2つのファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-230">Unzipping will produce two files.</span></span>  <span data-ttu-id="7d13a-231">[.NET.............................. .net............</span><span class="sxs-lookup"><span data-stu-id="7d13a-231">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx.</span></span>

1. <span data-ttu-id="7d13a-232">デバイスのロックが解除されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7d13a-232">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="7d13a-233">これをまだ行っていない場合は、「 [Windows デバイスポータルを使用](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) した手順」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d13a-233">If you haven't done that before, see [Using the Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) for instructions.</span></span>

1. <span data-ttu-id="7d13a-234">次に、Windows デバイスポータルにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="7d13a-234">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="7d13a-235">USB 経由でこれを行うことをお勧めします。これを行うには、ブラウザーに「」と入力し http://127.0.0.1:10080 ます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-235">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>

1. <span data-ttu-id="7d13a-236">Windows デバイスポータルを作成した後、ダウンロードした2つのファイルの "サイドロード" を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d13a-236">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="7d13a-237">これを行うには、[ **アプリ** ] セクションに移動して [ **アプリ**] を選択するまで、左側のバーを下に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d13a-237">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>

1. <span data-ttu-id="7d13a-238">次のような画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-238">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="7d13a-239">「 **Install App** 」というセクションに移動し、これら2つの APPX ファイルを解凍した場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-239">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="7d13a-240">一度に1つだけ実行できます。そのため、最初の1つを選択した後、[デプロイ] セクションで [実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7d13a-240">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="7d13a-241">次に、2番目の APPX ファイルに対してこれを実行します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-241">Then do this for the second APPX file.</span></span>

   ![Side-Loaded アプリをインストールするための Windows デバイスポータル](images/20190322-DevicePortal.png)
   
1. <span data-ttu-id="7d13a-243">この時点で、アプリケーションが再び動作を開始し、ストアにもアクセスできると思われます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-243">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>

1. <span data-ttu-id="7d13a-244">場合によっては、影響を受けるアプリが起動する前に3D ビューアーアプリを起動する追加手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d13a-244">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span> 

<span data-ttu-id="7d13a-245">この問題を解決するためのプロセスが完了したので、しばらくお待ちください。マイクロソフトのコミュニティと連携して、成功した Mixed Reality エクスペリエンスを作成してください。</span><span class="sxs-lookup"><span data-stu-id="7d13a-245">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <a name="device-update"></a><span data-ttu-id="7d13a-246">デバイスの更新</span><span class="sxs-lookup"><span data-stu-id="7d13a-246">Device Update</span></span>

- <span data-ttu-id="7d13a-247">30秒新しい更新の後、シェルが1回消えることがあります。</span><span class="sxs-lookup"><span data-stu-id="7d13a-247">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="7d13a-248">**ブルーム** ジェスチャを実行してセッションを再開してください。</span><span class="sxs-lookup"><span data-stu-id="7d13a-248">Please perform the **bloom** gesture to resume your session.</span></span>

### <a name="visual-studio"></a><span data-ttu-id="7d13a-249">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7d13a-249">Visual Studio</span></span>

- <span data-ttu-id="7d13a-250">HoloLens 開発に推奨されている最新バージョンの Visual Studio 用の [ツールをインストール](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) する方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d13a-250">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>

- <span data-ttu-id="7d13a-251">アプリを Visual Studio から HoloLens にデプロイすると、次のエラーが表示されることがあります。 **ユーザーマップセクションが開いているファイルに対して、要求された操作を実行することはできません。(HRESULT からの例外: 0x800704C8)**。</span><span class="sxs-lookup"><span data-stu-id="7d13a-251">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="7d13a-252">この問題が発生した場合は、もう一度やり直してください。通常、配置は成功します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-252">If this happens, try again and your deployment will generally succeed.</span></span>

### <a name="api"></a><span data-ttu-id="7d13a-253">API</span><span class="sxs-lookup"><span data-stu-id="7d13a-253">API</span></span>

- <span data-ttu-id="7d13a-254">アプリケーションがユーザーの背後にある [フォーカスポイント](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) を設定した場合、または通常はカメラから移動した場合、ホログラムは混合の現実キャプチャの写真またはビデオには表示されません。</span><span class="sxs-lookup"><span data-stu-id="7d13a-254">If the application sets the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="7d13a-255">Windows でこのバグが修正されるまで、アプリケーションが [フォーカスポイント](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) をアクティブに設定している場合は、平面法線が反対のカメラフォワード (たとえば、normal =-camera. forward) に設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d13a-255">Until this bug is fixed in Windows, if applications actively set the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <a name="xbox-wireless-controller"></a><span data-ttu-id="7d13a-256">Xbox ワイヤレス コントローラー</span><span class="sxs-lookup"><span data-stu-id="7d13a-256">Xbox Wireless Controller</span></span>

- <span data-ttu-id="7d13a-257">Xbox ワイヤレスコントローラーは、HoloLens で使用する前に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d13a-257">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="7d13a-258">コントローラーを HoloLens とペアリングする前に、最新の状態 [に](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) なっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7d13a-258">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>

- <span data-ttu-id="7d13a-259">Xbox ワイヤレスコントローラーが接続されている間に HoloLens を再起動すると、コントローラーは HoloLens に自動的に再接続されません。</span><span class="sxs-lookup"><span data-stu-id="7d13a-259">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="7d13a-260">番組ガイドボタンのライトは、コントローラーが3分後に電源オフになるまで、ゆっくりと点滅します。</span><span class="sxs-lookup"><span data-stu-id="7d13a-260">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="7d13a-261">コントローラーをすぐに再接続するには、[ガイド] ボタンを押して、ライトがオフになるまでコントローラーの電源をオフにします。</span><span class="sxs-lookup"><span data-stu-id="7d13a-261">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="7d13a-262">コントローラーの電源を再度オンにすると、HoloLens に再接続されます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-262">When you power your controller on again, it will reconnect to HoloLens.</span></span>

- <span data-ttu-id="7d13a-263">Xbox ワイヤレスコントローラーが接続されている間に HoloLens がスタンバイ状態になると、コントローラー上の入力があれば HoloLens がウェイクアップされます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-263">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="7d13a-264">コントローラーの使用が完了したら、コントローラーの電源をオフにすることで回避できます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-264">You can prevent this by powering off your controller when you are done using it.</span></span>

## <a name="known-issues-for-hololens-emulator"></a><span data-ttu-id="7d13a-265">HoloLens エミュレーターの既知の問題</span><span class="sxs-lookup"><span data-stu-id="7d13a-265">Known issues for HoloLens emulator</span></span>

- <span data-ttu-id="7d13a-266">Microsoft Store の一部のアプリは、エミュレーターと互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="7d13a-266">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="7d13a-267">たとえば、若い Conker とフラグメントは、エミュレーターでは再生できません。</span><span class="sxs-lookup"><span data-stu-id="7d13a-267">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="7d13a-268">エミュレーターでは、PC の web カメラを使用できません。</span><span class="sxs-lookup"><span data-stu-id="7d13a-268">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="7d13a-269">Windows デバイスポータルのライブプレビュー機能は、エミュレーターでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="7d13a-269">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="7d13a-270">混合した現実のビデオとイメージをキャプチャすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7d13a-270">You can still capture Mixed Reality videos and images.</span></span>
