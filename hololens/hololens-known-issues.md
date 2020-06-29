---
title: HoloLens の既知の問題
description: これは、HoloLens 開発者に影響を与える可能性がある既知の問題の一覧です。
keywords: トラブルシューティング、既知の問題、ヘルプ
author: mattzmsft
ms.author: mazeller
ms.date: 4/20/2020
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
ms.openlocfilehash: 330a7fd549a2b847f77715ca90d69f1d4df1fb1d
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829296"
---
# <span data-ttu-id="7ca78-104">HoloLens の既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ca78-104">Known issues for HoloLens</span></span>

<span data-ttu-id="7ca78-105">これは、HoloLens デバイスの既知の問題の最新の一覧です。</span><span class="sxs-lookup"><span data-stu-id="7ca78-105">This is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="7ca78-106">奇数の動作が表示される場合は、まずここを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7ca78-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="7ca78-107">この一覧は、新しい問題が検出または報告された場合、または今後の HoloLens ソフトウェアの更新で問題が解決された場合に、更新されます。</span><span class="sxs-lookup"><span data-stu-id="7ca78-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="7ca78-108">ブロックされていない問題が見つかった場合は、[フィードバック Hub](hololens-feedback.md)経由で HoloLens デバイスで報告してください。</span><span class="sxs-lookup"><span data-stu-id="7ca78-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="7ca78-109">問題が解決している場合は、フィードバックを送信するために、[サポートリクエスト](https://aka.ms/hlsupport)を提出してください。</span><span class="sxs-lookup"><span data-stu-id="7ca78-109">If the issue you are facing is blocking you, in addtion to filing feedback, please  [file a support request](https://aka.ms/hlsupport).</span></span>

- [<span data-ttu-id="7ca78-110">すべての HoloLens ジェネレーションの既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ca78-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="7ca78-111">HoloLens 2 デバイスの既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ca78-111">Known issues for HoloLens 2 devices</span></span>](#known-issues-for-hololens-2-devices)
- [<span data-ttu-id="7ca78-112">HoloLens の既知の問題 (第1世代)</span><span class="sxs-lookup"><span data-stu-id="7ca78-112">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)
- [<span data-ttu-id="7ca78-113">HoloLens エミュレーターの既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ca78-113">Known issues for HoloLens emulator</span></span>](#known-issues-for-hololens-emulator)

## <span data-ttu-id="7ca78-114">すべての HoloLens ジェネレーションの既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ca78-114">Known issues for all HoloLens generations</span></span>

### <span data-ttu-id="7ca78-115">Unity</span><span class="sxs-lookup"><span data-stu-id="7ca78-115">Unity</span></span>

- <span data-ttu-id="7ca78-116">「HoloLens の開発に推奨される最新バージョンの Unity 用の[ツールをインストール](https://docs.microsoft.com/windows/mixed-reality/install-the-tools)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ca78-116">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="7ca78-117">Unity HoloLens のテクニカルプレビューの既知の問題については、「 [HoloLens Unity フォーラム](https://forum.unity3d.com/threads/known-issues.394627/)」で説明しています。</span><span class="sxs-lookup"><span data-stu-id="7ca78-117">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <span data-ttu-id="7ca78-118">Windows Device Portal</span><span class="sxs-lookup"><span data-stu-id="7ca78-118">Windows Device Portal</span></span>

- <span data-ttu-id="7ca78-119">Mixed Reality キャプチャのライブプレビュー機能は、数秒間の待機時間を示す場合があります。</span><span class="sxs-lookup"><span data-stu-id="7ca78-119">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>
- <span data-ttu-id="7ca78-120">仮想入力ページでは、[仮想ジェスチャー] セクションのジェスチャとスクロールコントロールは機能しません。</span><span class="sxs-lookup"><span data-stu-id="7ca78-120">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="7ca78-121">これらを使用しても効果はありません。</span><span class="sxs-lookup"><span data-stu-id="7ca78-121">Using them will have no effect.</span></span> <span data-ttu-id="7ca78-122">同じページの仮想キーボードは正しく動作します。</span><span class="sxs-lookup"><span data-stu-id="7ca78-122">The virtual keyboard on the same page works correctly.</span></span>
- <span data-ttu-id="7ca78-123">[設定] で開発者モードを有効にした後、デバイスポータルが有効になるまでに数秒かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="7ca78-123">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

## <span data-ttu-id="7ca78-124">HoloLens 2 デバイスの既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ca78-124">Known issues for HoloLens 2 devices</span></span>

### <span data-ttu-id="7ca78-125">Insider ビルドを使用して、デバイス reflashed で Insider preview ビルドから登録解除した後に、青色の画面が表示される</span><span class="sxs-lookup"><span data-stu-id="7ca78-125">Blue screen is shown after unenrolling from Insider preview builds on a device reflashed with a Insider build</span></span>

<span data-ttu-id="7ca78-126">これは、Insider preview ビルドを行っているユーザーに影響を与える問題であり、新しい insider preview ビルドで HoloLens 2 を reflashed してから、Insider プログラムから登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="7ca78-126">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> 

<span data-ttu-id="7ca78-127">これは、次のような影響はありません。</span><span class="sxs-lookup"><span data-stu-id="7ca78-127">This does not affect:</span></span>
- <span data-ttu-id="7ca78-128">Windows Insider に登録されていないユーザー</span><span class="sxs-lookup"><span data-stu-id="7ca78-128">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="7ca78-129">者</span><span class="sxs-lookup"><span data-stu-id="7ca78-129">Insiders:</span></span>
    - <span data-ttu-id="7ca78-130">Insider ビルドがバージョン18362であるため、デバイスが登録されている場合</span><span class="sxs-lookup"><span data-stu-id="7ca78-130">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="7ca78-131">Insider 署名された19041ビルドをフラッシュして Insider プログラムに登録したままになっている場合</span><span class="sxs-lookup"><span data-stu-id="7ca78-131">If they flashed a Insider signed 19041.x build AND stay enrolled in the Insider program</span></span> 

<span data-ttu-id="7ca78-132">回避策:</span><span class="sxs-lookup"><span data-stu-id="7ca78-132">Work-around:</span></span> 
- <span data-ttu-id="7ca78-133">問題を回避する</span><span class="sxs-lookup"><span data-stu-id="7ca78-133">Avoid the issue</span></span> 
    - <span data-ttu-id="7ca78-134">Insider 以外のビルドをフラッシュします。</span><span class="sxs-lookup"><span data-stu-id="7ca78-134">Flash a non-insider build.</span></span> <span data-ttu-id="7ca78-135">通常の月次更新プログラムのいずれか。</span><span class="sxs-lookup"><span data-stu-id="7ca78-135">One of the regular monthly updates.</span></span> 
    - <span data-ttu-id="7ca78-136">Insider プレビューを表示する</span><span class="sxs-lookup"><span data-stu-id="7ca78-136">Stay on Insider Preview</span></span>
- <span data-ttu-id="7ca78-137">デバイスの Reflash</span><span class="sxs-lookup"><span data-stu-id="7ca78-137">Reflash the device</span></span>
    1. <span data-ttu-id="7ca78-138">接続していないときに完全に電源を切ることにより、 [HoloLens 2 を手動でフラッシュモードに](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2)します。</span><span class="sxs-lookup"><span data-stu-id="7ca78-138">Put the [HoloLens 2 into flashing mode](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) manually by fully powering down while not connect.</span></span> <span data-ttu-id="7ca78-139">音量を上げながら、Power ボタンをタップします。</span><span class="sxs-lookup"><span data-stu-id="7ca78-139">Then while holding Volume up, tap the Power button.</span></span>
    1. <span data-ttu-id="7ca78-140">PC に接続し、アドバンスト回復コンパニオンを開きます。</span><span class="sxs-lookup"><span data-stu-id="7ca78-140">Connect to the PC and open Advanced Recovery Companion.</span></span> 
    1. <span data-ttu-id="7ca78-141">HoloLens 2 を既定のビルドにフラッシュします。</span><span class="sxs-lookup"><span data-stu-id="7ca78-141">Flash the HoloLens 2 to the default build.</span></span>   

## <span data-ttu-id="7ca78-142">HoloLens の既知の問題 (第1世代)</span><span class="sxs-lookup"><span data-stu-id="7ca78-142">Known issues for HoloLens (1st Gen)</span></span>

### <span data-ttu-id="7ca78-143">Visual Studio 経由で HoloLens に接続して展開できない</span><span class="sxs-lookup"><span data-stu-id="7ca78-143">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="7ca78-144">最終更新日: 8/8 @ 5: 午後11時-Visual Studio は VS 2019 バージョン16.2 をリリースしました。この問題の修正プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7ca78-144">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="7ca78-145">このエラーが発生しないように、この最新バージョンに更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7ca78-145">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="7ca78-146">Visual Studio は VS 2019 バージョン16.2 をリリースしました。この問題の修正プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7ca78-146">Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="7ca78-147">このエラーが発生しないように、この最新バージョンに更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7ca78-147">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="7ca78-148">問題の原因: visual studio 2015 または Visual Studio 2017 の早期リリースを使用しているユーザーが、HoloLens でアプリケーションを展開してデバッグし、その後、同じ HoloLens で visual Studio 2017 または Visual Studio 2019 の最新バージョンを使用している場合は、この問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="7ca78-148">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="7ca78-149">Visual Studio の新しいリリースでは、新しいバージョンのコンポーネントが展開されますが、古いバージョンのファイルはデバイス上に残っているため、新しいバージョンは失敗します。</span><span class="sxs-lookup"><span data-stu-id="7ca78-149">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="7ca78-150">これにより、次のエラーメッセージが表示されます: DEP0100: ターゲットデバイスで開発者モードが有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7ca78-150">This causes the following error message: DEP0100: Please ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="7ca78-151">エラー80004005により、の開発者用ライセンスを取得できませんでした \<ip\> 。</span><span class="sxs-lookup"><span data-stu-id="7ca78-151">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <span data-ttu-id="7ca78-152">回避策</span><span class="sxs-lookup"><span data-stu-id="7ca78-152">Workaround</span></span>

<span data-ttu-id="7ca78-153">現在、チームは修正に向けて取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="7ca78-153">Our team is currently working on a fix.</span></span> <span data-ttu-id="7ca78-154">それまでの間、次の手順を使用して、問題を回避し、展開およびデバッグのブロックを解除することができます。</span><span class="sxs-lookup"><span data-stu-id="7ca78-154">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="7ca78-155">Visual Studio を開く</span><span class="sxs-lookup"><span data-stu-id="7ca78-155">Open Visual Studio</span></span>
1. <span data-ttu-id="7ca78-156">[**ファイル**] の [  >  **新しい**  >  **プロジェクト**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="7ca78-156">Select **File** > **New** > **Project**.</span></span>
1. <span data-ttu-id="7ca78-157">[ **Visual C#**  >  **Windows デスクトップ**  >  **コンソールアプリ (.net Framework)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ca78-157">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>
1. <span data-ttu-id="7ca78-158">プロジェクトに名前を付け ("HoloLensDeploymentFix" など)、フレームワークが少なくとも .NET Framework 4.5 に設定されていることを確認して、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ca78-158">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>
1. <span data-ttu-id="7ca78-159">ソリューションエクスプローラーで [**参照設定**] ノードを右クリックし、次の参照を追加します ([**参照**] セクションを選び、[**参照**] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="7ca78-159">Right-click on the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```CMD
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="7ca78-160">10.0.18362.0 をまだインストールしていない場合は、最新バージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="7ca78-160">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span> 

1. <span data-ttu-id="7ca78-161">ソリューションエクスプローラーでプロジェクトを右クリックし、[ **Add**  >  **既存項目**の追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ca78-161">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>
1. <span data-ttu-id="7ca78-162">C:\Program Files (x86) \Windows Kits\10\bin\10.0.18362.0\x86 を参照して、フィルターを\*\*すべてのファイル (\ *. \ *)** に変更します。</span><span class="sxs-lookup"><span data-stu-id="7ca78-162">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>
1. <span data-ttu-id="7ca78-163">SirepClient.dll と SshClient.dll の両方を選択して、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ca78-163">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>
1. <span data-ttu-id="7ca78-164">ソリューションエクスプローラーで両方のファイルを見つけて選び (ファイルの一覧の一番下にある必要があります)、[**プロパティ**] ウィンドウの [**出力ディレクトリにコピー** ] を選択して、**常にコピー**します。</span><span class="sxs-lookup"><span data-stu-id="7ca78-164">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>
1. <span data-ttu-id="7ca78-165">ファイルの上部で、次のステートメントを既存のステートメント一覧に追加し `using` ます。</span><span class="sxs-lookup"><span data-stu-id="7ca78-165">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```CMD
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="7ca78-166">の中 `static void Main(...)` に、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="7ca78-166">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="7ca78-167">[**ビルド**  >  **ビルドソリューション**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="7ca78-167">Select **Build** > **Build Solution**.</span></span>
1. <span data-ttu-id="7ca78-168">コマンドプロンプトウィンドウを開き、コンパイルされた .exe ファイルを含むフォルダー (C:\MyProjects\HoloLensDeploymentFix\bin\Debug など) を開きます。</span><span class="sxs-lookup"><span data-stu-id="7ca78-168">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug)</span></span>
1. <span data-ttu-id="7ca78-169">実行可能ファイルを実行して、デバイスの IP アドレスをコマンドライン引数として指定します。</span><span class="sxs-lookup"><span data-stu-id="7ca78-169">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="7ca78-170">(USB を使って接続している場合は、127.0.0.1 を使用できます。それ以外の場合は、デバイスの Wi-fi IP アドレスを使用してください)。 たとえば、"HoloLensDeploymentFix 127.0.0.1" とします。</span><span class="sxs-lookup"><span data-stu-id="7ca78-170">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1"</span></span>

1. <span data-ttu-id="7ca78-171">すべてのメッセージが表示されることなくツールが終了すると (数秒しかかかりません)、Visual Studio 2017 以降から展開とデバッグを行うことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="7ca78-171">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="7ca78-172">引き続きこのツールを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7ca78-172">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="7ca78-173">利用可能になったら、さらに更新プログラムを提供します。</span><span class="sxs-lookup"><span data-stu-id="7ca78-173">We will provide further updates as they become available.</span></span>

### <span data-ttu-id="7ca78-174">HoloLens での Microsoft ストアとアプリの起動に関する問題</span><span class="sxs-lookup"><span data-stu-id="7ca78-174">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="7ca78-175">最終更新: 4/2 @ 10 AM-問題が解決されました。</span><span class="sxs-lookup"><span data-stu-id="7ca78-175">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span> 

<span data-ttu-id="7ca78-176">HoloLens で Microsoft Store とアプリを起動しようとすると、問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7ca78-176">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="7ca78-177">バックグラウンドアプリの更新によって、1つ以上の依存アプリが実行されているときに、新しいバージョンの framework パッケージが特定のシーケンスで展開されると、問題が発生すると判断されました。</span><span class="sxs-lookup"><span data-stu-id="7ca78-177">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="7ca78-178">この場合、アプリの自動更新によって新しいバージョンの .NET ネイティブフレームワーク (バージョン10.0.25531 から 10.0.27413) が提供されたため、実行中のアプリは、以前のバージョンのフレームワークを使用するすべての実行中のアプリで正しく更新されませんでした。</span><span class="sxs-lookup"><span data-stu-id="7ca78-178">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="7ca78-179">フレームワークの更新のフローは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="7ca78-179">The flow for framework update is as follows:</span></span> 

1. <span data-ttu-id="7ca78-180">新しいフレームワークパッケージがストアからダウンロードされ、インストールされます。</span><span class="sxs-lookup"><span data-stu-id="7ca78-180">The new framework package is downloaded from the store and installed</span></span>
1. <span data-ttu-id="7ca78-181">以前のフレームワークを使用するすべてのアプリが新しいバージョンを使用するように更新されている</span><span class="sxs-lookup"><span data-stu-id="7ca78-181">All apps using the older framework are 'updated' to use the newer version</span></span>

<span data-ttu-id="7ca78-182">ステップ2が完了する前に中断された場合、新しいフレームワークが登録されていないアプリは、[スタート] メニューから起動できません。</span><span class="sxs-lookup"><span data-stu-id="7ca78-182">If step 2 is interrupted before completion then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="7ca78-183">HoloLens 上のアプリは、この問題の影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7ca78-183">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="7ca78-184">ハングしたアプリを閉じて、フィードバック Hub、3D Viewer、または写真などの他のアプリを起動すると、問題が解決されるという報告がありましたが、その場合、 &mdash; 100% は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="7ca78-184">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them&mdash;however, this does not work 100% of the time.</span></span>

<span data-ttu-id="7ca78-185">この問題によって更新プログラム自体は発生しませんでしたが、この問題は、.NET ネイティブフレームワークの更新によって不適切に処理されたバグであると考えられています。</span><span class="sxs-lookup"><span data-stu-id="7ca78-185">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="7ca78-186">修正プログラムを特定し、修正プログラム (OS バージョン 17763.380) をリリースしたことをお知らせします。</span><span class="sxs-lookup"><span data-stu-id="7ca78-186">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="7ca78-187">デバイスが更新プログラムを受け取ることができるかどうかを確認するには、次のことを行ってください。</span><span class="sxs-lookup"><span data-stu-id="7ca78-187">To see if your device can take the update, please:</span></span>

1. <span data-ttu-id="7ca78-188">[設定] アプリに移動して、[**更新 & セキュリティ**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="7ca78-188">Go to the Settings app and open **Update & Security**.</span></span>
1. <span data-ttu-id="7ca78-189">[**更新プログラムの確認**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="7ca78-189">Select **Check for Updates**.</span></span>
1. <span data-ttu-id="7ca78-190">17763.380 への更新プログラムが利用できる場合は、このビルドに更新して、アプリがハングするバグの修正プログラムを入手してください。</span><span class="sxs-lookup"><span data-stu-id="7ca78-190">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug</span></span>
1. <span data-ttu-id="7ca78-191">このバージョンの OS への更新時に、アプリは期待どおりに動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ca78-191">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="7ca78-192">さらに、すべての HoloLens OS リリースの場合と同様に、 [Microsoft ダウンロードセンター](https://aka.ms/hololensdownload/10.0.17763.380)に ffu イメージを投稿しました。</span><span class="sxs-lookup"><span data-stu-id="7ca78-192">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="7ca78-193">更新を実行したくない場合は、3/29 の時点で新しいバージョンの Microsoft Store UWP アプリをリリースしました。</span><span class="sxs-lookup"><span data-stu-id="7ca78-193">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="7ca78-194">ストアの更新版を入手したら、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7ca78-194">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="7ca78-195">ストアを開いて、読み込まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7ca78-195">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="7ca78-196">ブルームジェスチャを使用してメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="7ca78-196">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="7ca78-197">以前に壊れたアプリを開こうとしています。</span><span class="sxs-lookup"><span data-stu-id="7ca78-197">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="7ca78-198">それでも起動できない場合は、破損したアプリのアイコンをタップして押し続け、[アンインストール] を選びます。</span><span class="sxs-lookup"><span data-stu-id="7ca78-198">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="7ca78-199">Resinstall からこれらのアプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="7ca78-199">Resinstall these apps from the store.</span></span>

<span data-ttu-id="7ca78-200">デバイスで依然としてアプリを読み込むことができない場合は、次の手順に従って、ダウンロードセンターから .NET ネイティブフレームワークとランタイムのバージョンをサイドローディングできます。</span><span class="sxs-lookup"><span data-stu-id="7ca78-200">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="7ca78-201">Microsoft ダウンロードセンターから[この zip ファイル](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip)をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="7ca78-201">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="7ca78-202">解凍すると、2つのファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="7ca78-202">Unzipping will produce two files.</span></span>  <span data-ttu-id="7ca78-203">NET.TCP、.appx、および NET.EXE というように、.appx というようにします。</span><span class="sxs-lookup"><span data-stu-id="7ca78-203">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx</span></span>
1. <span data-ttu-id="7ca78-204">デバイスが dev のロック解除されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7ca78-204">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="7ca78-205">この手順を完了していない場合は、[こちら](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ca78-205">If you haven't done that before the instructions to do that are [here](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="7ca78-206">次に、Windows Device Portal にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="7ca78-206">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="7ca78-207">この操作は USB 経由で行うことをお勧めします。そのためには、 http://127.0.0.1:10080 ブラウザーに入力します。</span><span class="sxs-lookup"><span data-stu-id="7ca78-207">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>
1. <span data-ttu-id="7ca78-208">Windows Device Portal を起動したら、ダウンロードした2つのファイルを "サイドロード" する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ca78-208">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="7ca78-209">そのためには、左側のバーに移動して [**アプリ**] セクションに移動し、[**アプリ**] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ca78-209">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>
1. <span data-ttu-id="7ca78-210">次のような画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ca78-210">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="7ca78-211">[**アプリのインストール**] というセクションに移動して、2つの APPX ファイルを解凍した場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="7ca78-211">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="7ca78-212">一度に1つしか実行できないため、最初の1つを選んでから、[展開] セクションの [移動] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ca78-212">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="7ca78-213">次に、2つ目の APPX ファイルに対してこれを行います。</span><span class="sxs-lookup"><span data-stu-id="7ca78-213">Then do this for the second APPX file.</span></span>

   ![サイドロードアプリをインストールするための Windows Device Portal](images/20190322-DevicePortal.png)
1. <span data-ttu-id="7ca78-215">この時点で、アプリケーションは再び動作を開始する必要があり、ストアにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7ca78-215">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>
1. <span data-ttu-id="7ca78-216">場合によっては、影響を受けるアプリが起動する前に、3D ビューアーアプリを起動するための追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ca78-216">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span> 

<span data-ttu-id="7ca78-217">この問題を解決するための手続きを行っていますので、この問題を解決するためのご協力をお願いいたします。 skype では、共同作業を成功させるために、コミュニティを引き続き活用していきます。</span><span class="sxs-lookup"><span data-stu-id="7ca78-217">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <span data-ttu-id="7ca78-218">デバイスの更新</span><span class="sxs-lookup"><span data-stu-id="7ca78-218">Device Update</span></span>

- <span data-ttu-id="7ca78-219">30秒後に新しい更新プログラムを実行すると、シェルが1回表示されなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="7ca78-219">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="7ca78-220">セッションを再開するには、**ブルーム**ジェスチャを実行してください。</span><span class="sxs-lookup"><span data-stu-id="7ca78-220">Please perform the **bloom** gesture to resume your session.</span></span>

### <span data-ttu-id="7ca78-221">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7ca78-221">Visual Studio</span></span>

- <span data-ttu-id="7ca78-222">「HoloLens の開発に推奨される最新バージョンの Visual Studio 用の[ツールをインストール](https://docs.microsoft.com/windows/mixed-reality/install-the-tools)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ca78-222">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>
- <span data-ttu-id="7ca78-223">Visual Studio から HoloLens にアプリを展開すると、次のエラーが表示されることがあります。要求された操作は、ユーザーによってマップされた**セクションが開いているファイルでは実行できません。(HRESULT: 0x800704C8 の例外)**。</span><span class="sxs-lookup"><span data-stu-id="7ca78-223">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="7ca78-224">この問題が発生した場合は、通常、展開は成功します。</span><span class="sxs-lookup"><span data-stu-id="7ca78-224">If this happens, try again and your deployment will generally succeed.</span></span>

### <span data-ttu-id="7ca78-225">API</span><span class="sxs-lookup"><span data-stu-id="7ca78-225">API</span></span>

- <span data-ttu-id="7ca78-226">ユーザーまたは通常のカメラに[フォーカスポイント](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity)を設定すると、ホログラムは Mixed Reality キャプチャ写真またはビデオに表示されません。</span><span class="sxs-lookup"><span data-stu-id="7ca78-226">If the application sets the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="7ca78-227">このバグが Windows で修正されるまでは、アプリケーションが[フォーカスポイント](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity)をアクティブに設定した場合、機体の法線が反対のカメラフォワード (たとえば、normal =-camera. forward) に設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ca78-227">Until this bug is fixed in Windows, if applications actively set the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <span data-ttu-id="7ca78-228">Xbox ワイヤレスコントローラー</span><span class="sxs-lookup"><span data-stu-id="7ca78-228">Xbox Wireless Controller</span></span>

- <span data-ttu-id="7ca78-229">Xbox ワイヤレスコントローラー S は、HoloLens で使用する前に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ca78-229">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="7ca78-230">HoloLens とコントローラーをペアリングしようとする前に、[最新](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter)の状態であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7ca78-230">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>
- <span data-ttu-id="7ca78-231">Xbox ワイヤレスコントローラーが接続されているときに HoloLens を再起動すると、コントローラーが HoloLens に自動的に再接続されることはありません。</span><span class="sxs-lookup"><span data-stu-id="7ca78-231">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="7ca78-232">[ガイド] ボタンのライトは、3分後にコントローラーの電源が切れるまでゆっくり点滅します。</span><span class="sxs-lookup"><span data-stu-id="7ca78-232">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="7ca78-233">コントローラーをすぐに再接続するには、ライトがオフになるまでガイドボタンを押してコントローラーの電源を切ります。</span><span class="sxs-lookup"><span data-stu-id="7ca78-233">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="7ca78-234">コントローラーの電源を入れ直すと、HoloLens に再接続されます。</span><span class="sxs-lookup"><span data-stu-id="7ca78-234">When you power your controller on again, it will reconnect to HoloLens.</span></span>
- <span data-ttu-id="7ca78-235">Xbox ワイヤレスコントローラーが接続されているときに HoloLens がスタンバイ状態になると、コントローラーでの入力によって HoloLens が復帰します。</span><span class="sxs-lookup"><span data-stu-id="7ca78-235">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="7ca78-236">この機能を使用したら、コントローラーの電源を切ることで、これを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="7ca78-236">You can prevent this by powering off your controller when you are done using it.</span></span>

## <span data-ttu-id="7ca78-237">HoloLens エミュレーターの既知の問題</span><span class="sxs-lookup"><span data-stu-id="7ca78-237">Known issues for HoloLens emulator</span></span>

- <span data-ttu-id="7ca78-238">Microsoft Store のすべてのアプリがエミュレーターと互換性があるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="7ca78-238">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="7ca78-239">たとえば、ヤングと断片はエミュレーターでは再生できません。</span><span class="sxs-lookup"><span data-stu-id="7ca78-239">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="7ca78-240">エミュレーターで PC web カメラを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="7ca78-240">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="7ca78-241">Windows Device Portal のリアルタイムのプレビュー機能は、エミュレーターでは動作しません。</span><span class="sxs-lookup"><span data-stu-id="7ca78-241">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="7ca78-242">ただし、Mixed Reality のビデオとイメージをキャプチャすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7ca78-242">You can still capture Mixed Reality videos and images.</span></span>
