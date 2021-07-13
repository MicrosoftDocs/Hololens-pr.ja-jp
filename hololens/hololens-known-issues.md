---
title: HoloLens (第 1 世代) に関する既知の問題
description: Unity と Windows デバイス ポータル を使用しているお客様や開発者に影響を与える可能性がある既知の問題と回避策の一覧をHoloLens最新の状態に保つ。
keywords: トラブルシューティング, 既知の問題, ヘルプ
author: mattzmsft
ms.author: mazeller
ms.date: 6/15/2021
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
ms.openlocfilehash: 36991d62da91011b807dfb9ff52ab16eadac8bc7
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640306"
---
# <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="d5b74-104">HoloLens (第 1 世代) に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="d5b74-104">Known issues for HoloLens (1st Gen)</span></span>

<span data-ttu-id="d5b74-105">現在のデバイスの既知の問題の一覧をHoloLensします。</span><span class="sxs-lookup"><span data-stu-id="d5b74-105">Here is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="d5b74-106">まず、奇数の動作が表示される場合は、こちらを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d5b74-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="d5b74-107">この一覧は、新しい問題が検出または報告された時点で、またはソフトウェア更新プログラムを使用して問題が解決HoloLensされます。</span><span class="sxs-lookup"><span data-stu-id="d5b74-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="d5b74-108">ブロックされていない問題が検出された場合は、 を介してデバイスHoloLens報告[フィードバック Hub。](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="d5b74-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="d5b74-109">問題が発生している場合は、フィードバックの提出に加えて、サポート [リクエストを提出してください](https://aka.ms/hlsupport)。</span><span class="sxs-lookup"><span data-stu-id="d5b74-109">If the issue you are facing is blocking you, in addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).</span></span>


- [<span data-ttu-id="d5b74-110">すべての世代の既知のHoloLens問題</span><span class="sxs-lookup"><span data-stu-id="d5b74-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="d5b74-111">HoloLens (第 1 世代) に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="d5b74-111">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a><span data-ttu-id="d5b74-112">すべての世代の既知のHoloLens問題</span><span class="sxs-lookup"><span data-stu-id="d5b74-112">Known issues for all HoloLens generations</span></span>

### <a name="unity"></a><span data-ttu-id="d5b74-113">Unity</span><span class="sxs-lookup"><span data-stu-id="d5b74-113">Unity</span></span>

- <span data-ttu-id="d5b74-114">新[しい開発に推奨される](/windows/mixed-reality/install-the-tools)Unity の最新バージョンについては、「ツールをインストールするHoloLensしてください。</span><span class="sxs-lookup"><span data-stu-id="d5b74-114">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="d5b74-115">Unity HoloLens Technical Preview に関する既知の問題については、Unity フォーラムのHoloLens[を参照してください](https://forum.unity3d.com/threads/known-issues.394627/)。</span><span class="sxs-lookup"><span data-stu-id="d5b74-115">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <a name="windows-device-portal"></a><span data-ttu-id="d5b74-116">Windows デバイス ポータル</span><span class="sxs-lookup"><span data-stu-id="d5b74-116">Windows Device Portal</span></span>

- <span data-ttu-id="d5b74-117">キャプチャの Live Preview 機能Mixed Reality数秒の待機時間が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d5b74-117">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="d5b74-118">[仮想入力] ページの [仮想ジェスチャ] セクションの [ジェスチャ] コントロールと [スクロール] コントロールは機能しません。</span><span class="sxs-lookup"><span data-stu-id="d5b74-118">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="d5b74-119">それらを使用した場合、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="d5b74-119">Using them will have no effect.</span></span> <span data-ttu-id="d5b74-120">仮想入力ページの仮想キーボードは正しく動作します。</span><span class="sxs-lookup"><span data-stu-id="d5b74-120">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="d5b74-121">設定 で開発者モードを有効にした後、スイッチが有効になっているまで数秒デバイス ポータル場合があります。</span><span class="sxs-lookup"><span data-stu-id="d5b74-121">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <a name="onedrive-camera-upload"></a><span data-ttu-id="d5b74-122">OneDriveカメラのアップロード</span><span class="sxs-lookup"><span data-stu-id="d5b74-122">OneDrive camera upload</span></span>

<span data-ttu-id="d5b74-123">OneDriveアプリではHoloLensまたは学校アカウントの自動カメラ アップロードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d5b74-123">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="d5b74-124">回避策:</span><span class="sxs-lookup"><span data-stu-id="d5b74-124">Workarounds:</span></span>

- <span data-ttu-id="d5b74-125">ビジネスで実行可能な場合は、コンシューマー向け Microsoft アカウントでカメラの自動アップロードがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d5b74-125">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="d5b74-126">自分のアカウントまたは学校アカウントMicrosoft アカウント、自分のアカウントにサインインできます (OneDrive アプリはデュアル サインインをサポートしています)。</span><span class="sxs-lookup"><span data-stu-id="d5b74-126">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="d5b74-127">アプリ内のMicrosoft アカウントプロファイルOneDrive、バックグラウンド カメラの自動ロール アップロードを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="d5b74-127">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="d5b74-128">写真を自動的にアップロードするためにコンシューマー Microsoft アカウント を安全に使用できない場合は、OneDrive アプリから仕事用または学校アカウントに写真を手動でアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="d5b74-128">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="d5b74-129">これを行うには、アプリで、自分の学校アカウントにサインインOneDriveしてください。</span><span class="sxs-lookup"><span data-stu-id="d5b74-129">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="d5b74-130">ボタンを選択 **+** し、 []**をアップロード。**</span><span class="sxs-lookup"><span data-stu-id="d5b74-130">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="d5b74-131">[カメラ ロール] の [ピクチャ] に移動して、アップロード **する>を見つける。**</span><span class="sxs-lookup"><span data-stu-id="d5b74-131">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="d5b74-132">アップロードする写真またはビデオを選択し、[開く] ボタン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="d5b74-132">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="d5b74-133">HoloLens (第 1 世代) に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="d5b74-133">Known issues for HoloLens (1st Gen)</span></span>

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a><span data-ttu-id="d5b74-134">接続できないし、接続を使用してHoloLensにVisual Studio</span><span class="sxs-lookup"><span data-stu-id="d5b74-134">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="d5b74-135">最終更新日: 8/8 @ 5:11PM - Visual Studio では、この問題の修正が含まれる VS 2019 バージョン 16.2 がリリースされました。</span><span class="sxs-lookup"><span data-stu-id="d5b74-135">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="d5b74-136">このエラーが発生しないように、この最新バージョンに更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d5b74-136">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="d5b74-137">Visual Studio VS 2019 バージョン 16.2 がリリースされました。これには、この問題の修正プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d5b74-137">Visual Studio has released VS 2019 Version 16.2, which includes a fix to this issue.</span></span> <span data-ttu-id="d5b74-138">このエラーが発生しないように、この最新バージョンに更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d5b74-138">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="d5b74-139">問題の根本原因: Visual Studio 2015 または Visual Studio 2017 の初期リリースを使用して HoloLens でアプリケーションをデプロイおよびデバッグし、その後、同じ HoloLens で Visual Studio 2017 または Visual Studio 2019 の最新バージョンを使用したユーザーが影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d5b74-139">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="d5b74-140">新しいリリースの Visual Studioコンポーネントをデプロイする場合がありますが、古いバージョンのファイルはデバイスに残され、新しいバージョンは失敗します。</span><span class="sxs-lookup"><span data-stu-id="d5b74-140">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="d5b74-141">これにより、次のエラー メッセージが表示されます: DEP0100: ターゲット デバイスで開発者モードが有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5b74-141">This causes the following error message: DEP0100: Ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="d5b74-142">エラー \<ip\> 80004005 が原因で 開発者ライセンスを取得できない。</span><span class="sxs-lookup"><span data-stu-id="d5b74-142">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <a name="workaround"></a><span data-ttu-id="d5b74-143">回避策</span><span class="sxs-lookup"><span data-stu-id="d5b74-143">Workaround</span></span>

<span data-ttu-id="d5b74-144">現在、チームは修正に取り組み中です。</span><span class="sxs-lookup"><span data-stu-id="d5b74-144">Our team is currently working on a fix.</span></span> <span data-ttu-id="d5b74-145">その間は、次の手順を使用して問題を回避し、デプロイとデバッグのブロックを解除できます。</span><span class="sxs-lookup"><span data-stu-id="d5b74-145">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="d5b74-146">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="d5b74-146">Open Visual Studio.</span></span>

1. <span data-ttu-id="d5b74-147">**[File]**  >  **[New]**  >  **[Project]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d5b74-147">Select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="d5b74-148">[Visual **C#**  >  **Windows デスクトップ** コンソール アプリ  >  **(.NET Framework) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d5b74-148">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>

1. <span data-ttu-id="d5b74-149">プロジェクトに名前 ("HoloLensDeploymentFix" など) を付け、Framework が少なくとも .NET Framework 4.5 に設定 **.NET Framework、[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5b74-149">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>

1. <span data-ttu-id="d5b74-150">[参照]**ノードを** 右クリックしソリューション エクスプローラー参照を追加します ([参照] セクションを選択し、[参照] を **選択します**)。</span><span class="sxs-lookup"><span data-stu-id="d5b74-150">Right-click the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="d5b74-151">10.0.18362.0 がインストールされていない場合は、最新バージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="d5b74-151">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span>

1. <span data-ttu-id="d5b74-152">プロジェクトを右クリックし、 [既存の項目ソリューション エクスプローラー **を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d5b74-152">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>

1. <span data-ttu-id="d5b74-153">C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 に移動し、フィルターを **[すべてのファイル ] ( \* \* )** に変更します。</span><span class="sxs-lookup"><span data-stu-id="d5b74-153">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>

1. <span data-ttu-id="d5b74-154">[追加] と [SirepClient.dllの両方SshClient.dll選択し、 [追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d5b74-154">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>

1. <span data-ttu-id="d5b74-155">ソリューション エクスプローラー 内の両方のファイルを見つけて選択し (ファイルの一覧の一番下にある必要があります)、[プロパティ] ウィンドウで [出力ディレクトリにコピー] を [常にコピー]**に変更します**。</span><span class="sxs-lookup"><span data-stu-id="d5b74-155">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>

1. <span data-ttu-id="d5b74-156">ファイルの上部で、ステートメントの既存の一覧に次を `using` 追加します。</span><span class="sxs-lookup"><span data-stu-id="d5b74-156">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="d5b74-157">内に `static void Main(...)` 、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d5b74-157">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="d5b74-158">**[ビルド]**  >  **[ソリューションのビルド]** を順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d5b74-158">Select **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="d5b74-159">コマンド プロンプト ウィンドウを開き、コンパイル済みの .exe ファイルを含むフォルダーに cd を指定します (例: C:\MyProjects\HoloLensDeploymentFix\bin\Debug)。</span><span class="sxs-lookup"><span data-stu-id="d5b74-159">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span></span>

1. <span data-ttu-id="d5b74-160">実行可能ファイルを実行し、デバイスの IP アドレスをコマンド ライン引数として指定します。</span><span class="sxs-lookup"><span data-stu-id="d5b74-160">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="d5b74-161">(USB を使用して接続されている場合は、127.0.0.1 を使用できます。それ以外の場合は、デバイスの IP アドレスWi-Fi使用できます)。 たとえば、"HoloLensDeploymentFix 127.0.0.1" などです。</span><span class="sxs-lookup"><span data-stu-id="d5b74-161">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1".</span></span>

1. <span data-ttu-id="d5b74-162">ツールがメッセージなしで終了すると (数秒しかかからず)、Visual Studio 2017 以降からデプロイおよびデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="d5b74-162">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="d5b74-163">ツールを継続的に使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d5b74-163">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="d5b74-164">利用可能になったら、さらに更新プログラムを提供します。</span><span class="sxs-lookup"><span data-stu-id="d5b74-164">We will provide further updates as they become available.</span></span>

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a><span data-ttu-id="d5b74-165">アプリとアプリのMicrosoft Storeの起動に関するHoloLens</span><span class="sxs-lookup"><span data-stu-id="d5b74-165">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="d5b74-166">最終更新日: 4/2 @ 10 AM - 問題が解決されました。</span><span class="sxs-lookup"><span data-stu-id="d5b74-166">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span>

<span data-ttu-id="d5b74-167">アプリとアプリをアプリで起動しようとするときにMicrosoft Storeが発生するHoloLens。</span><span class="sxs-lookup"><span data-stu-id="d5b74-167">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="d5b74-168">バックグラウンド アプリの更新プログラムが特定のシーケンスで新しいバージョンのフレームワーク パッケージをデプロイするときに、1 つ以上の依存アプリがまだ実行されている間に問題が発生すると判断しました。</span><span class="sxs-lookup"><span data-stu-id="d5b74-168">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="d5b74-169">この場合、アプリの自動更新により、新しいバージョンの .NET ネイティブ Framework (バージョン 10.0.25531 から 10.0.27413) が提供され、実行中のアプリは、以前のバージョンのフレームワークを使用している実行中のすべてのアプリに対して正しく更新されませんでした。</span><span class="sxs-lookup"><span data-stu-id="d5b74-169">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="d5b74-170">フレームワークの更新のフローは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d5b74-170">The flow for framework update is as follows:</span></span>

1. <span data-ttu-id="d5b74-171">新しいフレームワーク パッケージがストアからダウンロードされ、インストールされます。</span><span class="sxs-lookup"><span data-stu-id="d5b74-171">The new framework package is downloaded from the store and installed.</span></span>

1. <span data-ttu-id="d5b74-172">古いフレームワークを使用しているすべてのアプリは、新しいバージョンを使用するように "更新" されます。</span><span class="sxs-lookup"><span data-stu-id="d5b74-172">All apps using the older framework are 'updated' to use the newer version.</span></span>

<span data-ttu-id="d5b74-173">手順 2 が完了する前に中断された場合、新しいフレームワークが登録されていないアプリは、スタート メニューから起動されません。</span><span class="sxs-lookup"><span data-stu-id="d5b74-173">If step 2 is interrupted before completion, then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="d5b74-174">この問題の影響を受ける可能性HoloLensアプリがインストールされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d5b74-174">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="d5b74-175">一部のユーザーは、ハングしたアプリを閉じ、フィードバック Hub、3D ビューアー、フォトなどの他のアプリを起動すると問題が解決すると報告されています。ただし、これは 100% の時間では機能しません。</span><span class="sxs-lookup"><span data-stu-id="d5b74-175">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them - however, this does not work 100% of the time.</span></span>

<span data-ttu-id="d5b74-176">この問題が原因で更新自体が発生したのではなく、os のバグが原因で .NET ネイティブ フレームワークの更新プログラムが正しく処理されないという根本原因がありました。</span><span class="sxs-lookup"><span data-stu-id="d5b74-176">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="d5b74-177">修正プログラムが特定され、修正プログラムを含む更新プログラム (OS バージョン 17763.380) がリリースされました。</span><span class="sxs-lookup"><span data-stu-id="d5b74-177">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="d5b74-178">デバイスが更新プログラムを受け取る可能性を確認するには:</span><span class="sxs-lookup"><span data-stu-id="d5b74-178">To see if your device can take the update:</span></span>

1. <span data-ttu-id="d5b74-179">アプリに移動し設定セキュリティの **更新&開きます**。</span><span class="sxs-lookup"><span data-stu-id="d5b74-179">Go to the Settings app and open **Update & Security**.</span></span>

1. <span data-ttu-id="d5b74-180">[更新 **プログラムの確認] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d5b74-180">Select **Check for Updates**.</span></span>

1. <span data-ttu-id="d5b74-181">17763.380 に更新できる場合は、このビルドに更新して、アプリハングバグの修正プログラムを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5b74-181">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug.</span></span>

1. <span data-ttu-id="d5b74-182">このバージョンの OS に更新すると、アプリは期待した通り動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5b74-182">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="d5b74-183">さらに、すべての OS リリースで行HoloLens、FFU イメージを Microsoft ダウンロード センター に[投稿しました](https://aka.ms/hololensdownload/10.0.17763.380)。</span><span class="sxs-lookup"><span data-stu-id="d5b74-183">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="d5b74-184">更新プログラムを利用しない場合は、3/29 のMicrosoft Store UWP アプリの新しいバージョンがリリースされました。</span><span class="sxs-lookup"><span data-stu-id="d5b74-184">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="d5b74-185">更新されたバージョンのストアを作成した後:</span><span class="sxs-lookup"><span data-stu-id="d5b74-185">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="d5b74-186">ストアを開き、それが読み込まれるか確認します。</span><span class="sxs-lookup"><span data-stu-id="d5b74-186">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="d5b74-187">花のジェスチャを使用してメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="d5b74-187">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="d5b74-188">以前に壊れたアプリを開くことを試みる。</span><span class="sxs-lookup"><span data-stu-id="d5b74-188">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="d5b74-189">起動できない場合は、壊れたアプリのアイコンを長押しし、[アンインストール] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5b74-189">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="d5b74-190">ストアからこれらのアプリを再インストールします。</span><span class="sxs-lookup"><span data-stu-id="d5b74-190">Reinstall these apps from the store.</span></span>

<span data-ttu-id="d5b74-191">デバイスがまだアプリを読み込めそうにできない場合は、次の手順に従って、ダウンロード センターから .NET ネイティブ Framework とランタイムのバージョンをサイドロードできます。</span><span class="sxs-lookup"><span data-stu-id="d5b74-191">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="d5b74-192">この zip [ファイルは、Microsoft](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) ダウンロード センターからダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="d5b74-192">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="d5b74-193">解凍すると、2 つのファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="d5b74-193">Unzipping will produce two files.</span></span>  <span data-ttu-id="d5b74-194">Microsoft .NET.Native.Runtime.1.7.appx と Microsoft .NET.Native.Framework.1.7.appx。</span><span class="sxs-lookup"><span data-stu-id="d5b74-194">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx.</span></span>

1. <span data-ttu-id="d5b74-195">デバイスのロックが解除されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d5b74-195">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="d5b74-196">この操作をまだ行っていない場合は、手順[については、](/windows/mixed-reality/using-the-windows-device-portal)次のWindows デバイス ポータルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5b74-196">If you haven't done that before, see [Using the Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal) for instructions.</span></span>

1. <span data-ttu-id="d5b74-197">次に、次のWindows デバイス ポータル。</span><span class="sxs-lookup"><span data-stu-id="d5b74-197">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="d5b74-198">これを USB で行い、ブラウザーに「」と入力して行うのが http://127.0.0.1:10080 推奨されます。</span><span class="sxs-lookup"><span data-stu-id="d5b74-198">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>

1. <span data-ttu-id="d5b74-199">新しいファイルをWindows デバイス ポータルダウンロードした 2 つのファイルを "サイド ロード" する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5b74-199">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="d5b74-200">これを行うには、[アプリ] セクションに移動して [アプリ] を選択するまで、左側のバーを下に移動する **必要があります**。</span><span class="sxs-lookup"><span data-stu-id="d5b74-200">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>

1. <span data-ttu-id="d5b74-201">次のような画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5b74-201">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="d5b74-202">「 **Install App** 」というセクションに移動し、これら2つの APPX ファイルを解凍した場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="d5b74-202">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="d5b74-203">一度に1つだけ実行できます。そのため、最初の1つを選択した後、[デプロイ] セクションで [実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5b74-203">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="d5b74-204">次に、2番目の APPX ファイルに対してこれを実行します。</span><span class="sxs-lookup"><span data-stu-id="d5b74-204">Then do this for the second APPX file.</span></span>

   ![WindowsSide-Loaded アプリをインストールするためのデバイスポータル](images/20190322-DevicePortal.png)

1. <span data-ttu-id="d5b74-206">この時点で、アプリケーションが再び動作を開始し、ストアにもアクセスできると思われます。</span><span class="sxs-lookup"><span data-stu-id="d5b74-206">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>

1. <span data-ttu-id="d5b74-207">場合によっては、影響を受けるアプリが起動する前に3D ビューアーアプリを起動する追加手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5b74-207">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span>

<span data-ttu-id="d5b74-208">この問題を解決するためのプロセスが完了したので、しばらくお待ちください。マイクロソフトのコミュニティと連携して、成功した Mixed Reality エクスペリエンスを作成してください。</span><span class="sxs-lookup"><span data-stu-id="d5b74-208">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <a name="device-update"></a><span data-ttu-id="d5b74-209">デバイスの更新</span><span class="sxs-lookup"><span data-stu-id="d5b74-209">Device Update</span></span>

- <span data-ttu-id="d5b74-210">30秒新しい更新の後、シェルが1回消えることがあります。</span><span class="sxs-lookup"><span data-stu-id="d5b74-210">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="d5b74-211">**ブルーム** ジェスチャを実行してセッションを再開してください。</span><span class="sxs-lookup"><span data-stu-id="d5b74-211">Please perform the **bloom** gesture to resume your session.</span></span>

### <a name="visual-studio"></a><span data-ttu-id="d5b74-212">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d5b74-212">Visual Studio</span></span>

- <span data-ttu-id="d5b74-213">HoloLens 開発に推奨される最新バージョンの Visual Studio については[、「ツールのインストール](/windows/mixed-reality/install-the-tools)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5b74-213">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>

- <span data-ttu-id="d5b74-214">Visual Studio から HoloLens にアプリを展開すると、次のエラーが表示されることがあります: ユーザーによって **マップされたセクションが開いているファイルに対して、要求された操作を実行することはできません。(HRESULT からの例外: 0x800704C8)**。</span><span class="sxs-lookup"><span data-stu-id="d5b74-214">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="d5b74-215">この問題が発生した場合は、もう一度やり直してください。通常、配置は成功します。</span><span class="sxs-lookup"><span data-stu-id="d5b74-215">If this happens, try again and your deployment will generally succeed.</span></span>

### <a name="api"></a><span data-ttu-id="d5b74-216">API</span><span class="sxs-lookup"><span data-stu-id="d5b74-216">API</span></span>

- <span data-ttu-id="d5b74-217">アプリケーションがユーザーの背後にある [フォーカスポイント](/windows/mixed-reality/focus-point-in-unity) を設定した場合、または通常はカメラから移動した場合、ホログラムは混合の現実キャプチャの写真またはビデオには表示されません。</span><span class="sxs-lookup"><span data-stu-id="d5b74-217">If the application sets the [focus point](/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="d5b74-218">このバグが Windows で修正されるまでは、アプリケーションが[フォーカスポイント](/windows/mixed-reality/focus-point-in-unity)をアクティブに設定している場合は、平面法線が反対のカメラフォワード (たとえば、normal =-camera. forward) に設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5b74-218">Until this bug is fixed in Windows, if applications actively set the [focus point](/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <a name="xbox-wireless-controller"></a><span data-ttu-id="d5b74-219">Xbox ワイヤレス コントローラー</span><span class="sxs-lookup"><span data-stu-id="d5b74-219">Xbox Wireless Controller</span></span>

- <span data-ttu-id="d5b74-220">HoloLens で使用する前に、Xbox ワイヤレスコントローラーを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5b74-220">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="d5b74-221">コントローラーと HoloLens をペアリングする前に、最新の状態[に](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter)なっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d5b74-221">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>

- <span data-ttu-id="d5b74-222">Xbox ワイヤレスコントローラーが接続されている間に HoloLens を再起動しても、コントローラーは HoloLens に自動的に再接続しません。</span><span class="sxs-lookup"><span data-stu-id="d5b74-222">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="d5b74-223">番組ガイドボタンのライトは、コントローラーが3分後に電源オフになるまで、ゆっくりと点滅します。</span><span class="sxs-lookup"><span data-stu-id="d5b74-223">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="d5b74-224">コントローラーをすぐに再接続するには、[ガイド] ボタンを押して、ライトがオフになるまでコントローラーの電源をオフにします。</span><span class="sxs-lookup"><span data-stu-id="d5b74-224">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="d5b74-225">コントローラーの電源を再度オンにすると、HoloLens に再接続されます。</span><span class="sxs-lookup"><span data-stu-id="d5b74-225">When you power your controller on again, it will reconnect to HoloLens.</span></span>

- <span data-ttu-id="d5b74-226">Xbox ワイヤレスコントローラーが接続されている間に HoloLens がスタンバイ状態になった場合、コントローラー上の入力があれば、その HoloLens を解除します。</span><span class="sxs-lookup"><span data-stu-id="d5b74-226">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="d5b74-227">コントローラーの使用が完了したら、コントローラーの電源をオフにすることで回避できます。</span><span class="sxs-lookup"><span data-stu-id="d5b74-227">You can prevent this by powering off your controller when you are done using it.</span></span>

