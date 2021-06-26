---
title: HoloLens の既知の問題 (第1世代)
description: Unity と Windows デバイスポータルを使用する HoloLens のお客様と開発者に影響を与える可能性のある既知の問題と回避策の一覧については、最新情報をご確認ください。
keywords: トラブルシューティング、既知の問題、ヘルプ
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
ms.openlocfilehash: 558eba8c2260b24a228e957b27927d508a077ec4
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923552"
---
# <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="078d6-104">HoloLens の既知の問題 (第1世代)</span><span class="sxs-lookup"><span data-stu-id="078d6-104">Known issues for HoloLens (1st Gen)</span></span>

<span data-ttu-id="078d6-105">HoloLens デバイスの既知の問題の現在の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="078d6-105">Here is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="078d6-106">奇妙な動作が見られる場合は、まずこのチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="078d6-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="078d6-107">この一覧は、新しい問題が検出または報告されたとき、または将来の HoloLens ソフトウェア更新プログラムで問題が解決されると、更新されたままになります。</span><span class="sxs-lookup"><span data-stu-id="078d6-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="078d6-108">ブロックされていない問題が検出された場合は、 [フィードバックハブ](hololens-feedback.md)を使用して HoloLens デバイスで報告してください。</span><span class="sxs-lookup"><span data-stu-id="078d6-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="078d6-109">問題が発生している場合は、フィードバックを提出するだけでなく、 [サポート要求](https://aka.ms/hlsupport)を提出してください。</span><span class="sxs-lookup"><span data-stu-id="078d6-109">If the issue you are facing is blocking you, in addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).</span></span>


- [<span data-ttu-id="078d6-110">すべての HoloLens の世代に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="078d6-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="078d6-111">HoloLens の既知の問題 (第1世代)</span><span class="sxs-lookup"><span data-stu-id="078d6-111">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a><span data-ttu-id="078d6-112">すべての HoloLens の世代に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="078d6-112">Known issues for all HoloLens generations</span></span>

### <a name="unity"></a><span data-ttu-id="078d6-113">Unity</span><span class="sxs-lookup"><span data-stu-id="078d6-113">Unity</span></span>

- <span data-ttu-id="078d6-114">「HoloLens の開発に推奨される最新バージョンの Unity 用の [ツールをインストール](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="078d6-114">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="078d6-115">Unity HoloLens Technical Preview の既知の問題については、 [Hololens Unity フォーラム](https://forum.unity3d.com/threads/known-issues.394627/)に記載されています。</span><span class="sxs-lookup"><span data-stu-id="078d6-115">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <a name="windows-device-portal"></a><span data-ttu-id="078d6-116">Windows デバイス ポータル</span><span class="sxs-lookup"><span data-stu-id="078d6-116">Windows Device Portal</span></span>

- <span data-ttu-id="078d6-117">Mixed Reality キャプチャのライブプレビュー機能は、数秒の待機時間が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="078d6-117">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="078d6-118">[仮想入力] ページで、[仮想ジェスチャ] セクションのジェスチャとスクロールコントロールが機能していません。</span><span class="sxs-lookup"><span data-stu-id="078d6-118">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="078d6-119">使用すると、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="078d6-119">Using them will have no effect.</span></span> <span data-ttu-id="078d6-120">仮想入力ページの仮想キーボードが正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="078d6-120">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="078d6-121">[設定] で開発者モードを有効にした後、デバイスポータルをオンにするスイッチが有効になるまで数秒かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="078d6-121">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <a name="onedrive-camera-upload"></a><span data-ttu-id="078d6-122">OneDrive カメラのアップロード</span><span class="sxs-lookup"><span data-stu-id="078d6-122">OneDrive camera upload</span></span>

<span data-ttu-id="078d6-123">HoloLens 用の OneDrive アプリでは、職場または学校アカウントのカメラの自動アップロードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="078d6-123">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="078d6-124">回避策:</span><span class="sxs-lookup"><span data-stu-id="078d6-124">Workarounds:</span></span>

- <span data-ttu-id="078d6-125">お客様のビジネスで利用可能な場合、カメラの自動アップロードはコンシューマーの Microsoft アカウントでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="078d6-125">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="078d6-126">職場または学校のアカウントに加えて、Microsoft アカウントにサインインできます (OneDrive アプリではデュアルサインインがサポートされています)。</span><span class="sxs-lookup"><span data-stu-id="078d6-126">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="078d6-127">OneDrive 内の Microsoft アカウントプロファイルから、自動、バックグラウンドカメラロールのアップロードを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="078d6-127">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="078d6-128">写真を自動的にアップロードするためにコンシューマー Microsoft アカウントを安全に使用できない場合は、OneDrive アプリから職場または学校のアカウントに写真を手動でアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="078d6-128">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="078d6-129">これを行うには、OneDrive アプリの職場または学校アカウントにサインインしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="078d6-129">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="078d6-130">ボタンを選択 **+** し、[ **アップロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="078d6-130">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="078d6-131">[ **ピクチャ > カメラロール** に移動して、アップロードする写真またはビデオを検索します。</span><span class="sxs-lookup"><span data-stu-id="078d6-131">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="078d6-132">アップロードする写真またはビデオを選択し、[ **開く** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="078d6-132">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="078d6-133">HoloLens の既知の問題 (第1世代)</span><span class="sxs-lookup"><span data-stu-id="078d6-133">Known issues for HoloLens (1st Gen)</span></span>

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a><span data-ttu-id="078d6-134">Visual Studio を使用して HoloLens に接続して展開できない</span><span class="sxs-lookup"><span data-stu-id="078d6-134">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="078d6-135">最終更新: 8/8 @ 5: 午後11時-Visual Studio は、この問題の修正を含む VS 2019 バージョン16.2 をリリースしました。</span><span class="sxs-lookup"><span data-stu-id="078d6-135">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="078d6-136">このエラーが発生しないように、この最新バージョンに更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="078d6-136">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="078d6-137">Visual Studio では、VS 2019 バージョン16.2 がリリースされました。これには、この問題の修正が含まれています。</span><span class="sxs-lookup"><span data-stu-id="078d6-137">Visual Studio has released VS 2019 Version 16.2, which includes a fix to this issue.</span></span> <span data-ttu-id="078d6-138">このエラーが発生しないように、この最新バージョンに更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="078d6-138">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="078d6-139">問題の根本原因: visual studio 2015 または Visual Studio 2017 の初期リリースを使用して、HoloLens でアプリケーションをデプロイおよびデバッグした後、同じ HoloLens で最新バージョンの Visual Studio 2017 または Visual Studio 2019 を使用したユーザーが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="078d6-139">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="078d6-140">新しいリリースの Visual Studio では、新しいバージョンのコンポーネントが配置されますが、古いバージョンのファイルはデバイス上に残されるため、新しいバージョンのエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="078d6-140">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="078d6-141">これにより、"DEP0100: ターゲットデバイスの開発者モードが有効になっていることを確認してください" というエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="078d6-141">This causes the following error message: DEP0100: Ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="078d6-142">エラー80004005が発生したため、で開発者ライセンスを取得できませんでした \<ip\> 。</span><span class="sxs-lookup"><span data-stu-id="078d6-142">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <a name="workaround"></a><span data-ttu-id="078d6-143">回避策</span><span class="sxs-lookup"><span data-stu-id="078d6-143">Workaround</span></span>

<span data-ttu-id="078d6-144">現在、チームは修正を行っています。</span><span class="sxs-lookup"><span data-stu-id="078d6-144">Our team is currently working on a fix.</span></span> <span data-ttu-id="078d6-145">それまでの間は、次の手順を使用して問題を回避し、デプロイとデバッグのブロックを解除できます。</span><span class="sxs-lookup"><span data-stu-id="078d6-145">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="078d6-146">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="078d6-146">Open Visual Studio.</span></span>

1. <span data-ttu-id="078d6-147">**[File]**  >  **[New]**  >  **[Project]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="078d6-147">Select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="078d6-148">[ **Visual C#**  >  **Windows デスクトップ**  >  **コンソールアプリ (.NET Framework)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="078d6-148">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>

1. <span data-ttu-id="078d6-149">プロジェクトに名前 ("HoloLensDeploymentFix" など) を付け、フレームワークが少なくとも .NET Framework 4.5 に設定されていることを確認してから、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="078d6-149">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>

1. <span data-ttu-id="078d6-150">ソリューションエクスプローラーの [ **参照** ] ノードを右クリックし、次の参照を追加します ([ **参照** ] セクションを選択し、[ **参照**] を選択します)。</span><span class="sxs-lookup"><span data-stu-id="078d6-150">Right-click the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="078d6-151">10.0.18362.0 がインストールされていない場合は、最新バージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="078d6-151">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span>

1. <span data-ttu-id="078d6-152">ソリューションエクスプローラーでプロジェクトを右クリックし、[   >  **既存項目** の追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="078d6-152">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>

1. <span data-ttu-id="078d6-153">C:\Program Files (x86) \Windows Kits\10\bin\10.0.18362.0\x86 を参照し、フィルターを **すべてのファイル ( \* . \* )** に変更します。</span><span class="sxs-lookup"><span data-stu-id="078d6-153">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>

1. <span data-ttu-id="078d6-154">[SirepClient.dll と SshClient.dll の両方を選択し、[ **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="078d6-154">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>

1. <span data-ttu-id="078d6-155">ソリューションエクスプローラーで両方のファイルを見つけて選択し (ファイルの一覧の一番下にある必要があります)、[**プロパティ**] ウィンドウで [**出力ディレクトリにコピー** ] を [**常にコピー** する] に変更します。</span><span class="sxs-lookup"><span data-stu-id="078d6-155">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>

1. <span data-ttu-id="078d6-156">ファイルの先頭に、ステートメントの既存のリストに次のを追加し `using` ます。</span><span class="sxs-lookup"><span data-stu-id="078d6-156">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="078d6-157">内 `static void Main(...)` に、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="078d6-157">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="078d6-158">**[ビルド]**  >  **[ソリューションのビルド]** を順に選択します。</span><span class="sxs-lookup"><span data-stu-id="078d6-158">Select **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="078d6-159">コマンドプロンプトウィンドウを開き、コンパイルされた .exe ファイルが含まれているフォルダー (C:\MyProjects\HoloLensDeploymentFix\bin\Debug など) に cd を開きます。</span><span class="sxs-lookup"><span data-stu-id="078d6-159">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span></span>

1. <span data-ttu-id="078d6-160">実行可能ファイルを実行し、デバイスの IP アドレスをコマンドライン引数として指定します。</span><span class="sxs-lookup"><span data-stu-id="078d6-160">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="078d6-161">(USB を使用して接続されている場合は、127.0.0.1 を使用できます。それ以外の場合は、デバイスの Wi-Fi IP アドレスを使用します)。 たとえば、"HoloLensDeploymentFix 127.0.0.1" のようになります。</span><span class="sxs-lookup"><span data-stu-id="078d6-161">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1".</span></span>

1. <span data-ttu-id="078d6-162">ツールがメッセージなしで終了した後 (これには数秒しかかかりません)、Visual Studio 2017 以降からデプロイおよびデバッグできるようになります。</span><span class="sxs-lookup"><span data-stu-id="078d6-162">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="078d6-163">ツールを引き続き使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="078d6-163">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="078d6-164">利用可能になると、さらに更新プログラムを提供します。</span><span class="sxs-lookup"><span data-stu-id="078d6-164">We will provide further updates as they become available.</span></span>

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a><span data-ttu-id="078d6-165">HoloLens での Microsoft Store とアプリの起動に関する問題</span><span class="sxs-lookup"><span data-stu-id="078d6-165">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="078d6-166">最終更新日時: 4/2 @ 10 AM-問題が解決されました。</span><span class="sxs-lookup"><span data-stu-id="078d6-166">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span>

<span data-ttu-id="078d6-167">HoloLens で Microsoft Store とアプリを起動しようとすると、問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="078d6-167">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="078d6-168">この問題が発生するのは、バックグラウンドアプリの更新プログラムによって、特定のシーケンスで新しいバージョンのフレームワークパッケージが配置されているにもかかわらず、1つまたは複数の依存アプリがまだ実行中である場合です。</span><span class="sxs-lookup"><span data-stu-id="078d6-168">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="078d6-169">この場合、アプリの自動更新によって新しいバージョンの .NET Native Framework (バージョン10.0.25531 から 10.0.27413) が提供されたため、以前のバージョンのフレームワークを使用している実行中のすべてのアプリに対して、実行中のアプリが正しく更新されませんでした。</span><span class="sxs-lookup"><span data-stu-id="078d6-169">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="078d6-170">Framework 更新のフローは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="078d6-170">The flow for framework update is as follows:</span></span>

1. <span data-ttu-id="078d6-171">新しいフレームワークパッケージがストアからダウンロードされ、インストールされます。</span><span class="sxs-lookup"><span data-stu-id="078d6-171">The new framework package is downloaded from the store and installed.</span></span>

1. <span data-ttu-id="078d6-172">古いフレームワークを使用しているすべてのアプリは、新しいバージョンを使用するように "更新" されます。</span><span class="sxs-lookup"><span data-stu-id="078d6-172">All apps using the older framework are 'updated' to use the newer version.</span></span>

<span data-ttu-id="078d6-173">ステップ2が完了前に中断された場合、新しいフレームワークが登録されていないアプリは、[スタート] メニューから起動できません。</span><span class="sxs-lookup"><span data-stu-id="078d6-173">If step 2 is interrupted before completion, then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="078d6-174">HoloLens のアプリは、この問題の影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="078d6-174">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="078d6-175">一部のユーザーは、ハングしたアプリを終了し、フィードバックハブ、3D ビューアー、写真などの他のアプリを起動すると、問題が解決しますが、100% の時間は機能しません。</span><span class="sxs-lookup"><span data-stu-id="078d6-175">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them - however, this does not work 100% of the time.</span></span>

<span data-ttu-id="078d6-176">根本が発生したため、この問題は更新プログラム自体の原因ではなく、.NET Native framework の更新プログラムが正しく処理されなかった OS のバグが発生しました。</span><span class="sxs-lookup"><span data-stu-id="078d6-176">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="078d6-177">修正を特定し、修正を含む更新プログラム (OS バージョン 17763.380) をリリースしたことをお知らせします。</span><span class="sxs-lookup"><span data-stu-id="078d6-177">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="078d6-178">デバイスで更新プログラムを取得できるかどうかを確認するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="078d6-178">To see if your device can take the update:</span></span>

1. <span data-ttu-id="078d6-179">設定アプリにアクセスし、[ **Update & Security**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="078d6-179">Go to the Settings app and open **Update & Security**.</span></span>

1. <span data-ttu-id="078d6-180">[ **更新プログラムの確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="078d6-180">Select **Check for Updates**.</span></span>

1. <span data-ttu-id="078d6-181">17763.380 への更新が利用可能な場合は、このビルドに更新して、アプリのハングバグの修正を受け取るようにしてください。</span><span class="sxs-lookup"><span data-stu-id="078d6-181">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug.</span></span>

1. <span data-ttu-id="078d6-182">このバージョンの OS に更新すると、アプリは想定どおりに動作するはずです。</span><span class="sxs-lookup"><span data-stu-id="078d6-182">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="078d6-183">さらに、HoloLens OS のすべてのリリースで、 [Microsoft ダウンロードセンター](https://aka.ms/hololensdownload/10.0.17763.380)に ffu イメージを投稿しました。</span><span class="sxs-lookup"><span data-stu-id="078d6-183">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="078d6-184">更新を希望しない場合は、3/29 の時点で Microsoft Store UWP アプリの新しいバージョンをリリースしました。</span><span class="sxs-lookup"><span data-stu-id="078d6-184">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="078d6-185">更新されたバージョンのストアを作成したら、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="078d6-185">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="078d6-186">ストアを開き、それが読み込まれることを確認します。</span><span class="sxs-lookup"><span data-stu-id="078d6-186">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="078d6-187">ブルームジェスチャを使用してメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="078d6-187">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="078d6-188">以前に破損したアプリを開こうとしました。</span><span class="sxs-lookup"><span data-stu-id="078d6-188">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="078d6-189">それでも起動できない場合は、壊れているアプリのアイコンをタップしたままにして、[アンインストール] を選択します。</span><span class="sxs-lookup"><span data-stu-id="078d6-189">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="078d6-190">ストアからこれらのアプリを再インストールします。</span><span class="sxs-lookup"><span data-stu-id="078d6-190">Reinstall these apps from the store.</span></span>

<span data-ttu-id="078d6-191">デバイスがまだアプリを読み込むことができない場合は、次の手順に従って、ダウンロードセンターで .NET Native Framework および Runtime のバージョンをサイドロードできます。</span><span class="sxs-lookup"><span data-stu-id="078d6-191">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="078d6-192">[この zip ファイル](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip)は、Microsoft ダウンロードセンターからダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="078d6-192">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="078d6-193">解凍すると2つのファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="078d6-193">Unzipping will produce two files.</span></span>  <span data-ttu-id="078d6-194">[.NET.............................. .net............</span><span class="sxs-lookup"><span data-stu-id="078d6-194">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx.</span></span>

1. <span data-ttu-id="078d6-195">デバイスのロックが解除されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="078d6-195">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="078d6-196">これをまだ行っていない場合は、「 [Windows デバイスポータルを使用](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) した手順」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="078d6-196">If you haven't done that before, see [Using the Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) for instructions.</span></span>

1. <span data-ttu-id="078d6-197">次に、Windows デバイスポータルにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="078d6-197">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="078d6-198">USB 経由でこれを行うことをお勧めします。これを行うには、ブラウザーに「」と入力し http://127.0.0.1:10080 ます。</span><span class="sxs-lookup"><span data-stu-id="078d6-198">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>

1. <span data-ttu-id="078d6-199">Windows デバイスポータルを作成した後、ダウンロードした2つのファイルの "サイドロード" を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="078d6-199">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="078d6-200">これを行うには、[ **アプリ** ] セクションに移動して [ **アプリ**] を選択するまで、左側のバーを下に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="078d6-200">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>

1. <span data-ttu-id="078d6-201">次のような画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="078d6-201">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="078d6-202">「 **Install App** 」というセクションに移動し、これら2つの APPX ファイルを解凍した場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="078d6-202">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="078d6-203">一度に1つだけ実行できます。そのため、最初の1つを選択した後、[デプロイ] セクションで [実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="078d6-203">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="078d6-204">次に、2番目の APPX ファイルに対してこれを実行します。</span><span class="sxs-lookup"><span data-stu-id="078d6-204">Then do this for the second APPX file.</span></span>

   ![Side-Loaded アプリをインストールするための Windows デバイスポータル](images/20190322-DevicePortal.png)

1. <span data-ttu-id="078d6-206">この時点で、アプリケーションが再び動作を開始し、ストアにもアクセスできると思われます。</span><span class="sxs-lookup"><span data-stu-id="078d6-206">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>

1. <span data-ttu-id="078d6-207">場合によっては、影響を受けるアプリが起動する前に3D ビューアーアプリを起動する追加手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="078d6-207">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span>

<span data-ttu-id="078d6-208">この問題を解決するためのプロセスが完了したので、しばらくお待ちください。マイクロソフトのコミュニティと連携して、成功した Mixed Reality エクスペリエンスを作成してください。</span><span class="sxs-lookup"><span data-stu-id="078d6-208">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <a name="device-update"></a><span data-ttu-id="078d6-209">デバイスの更新</span><span class="sxs-lookup"><span data-stu-id="078d6-209">Device Update</span></span>

- <span data-ttu-id="078d6-210">30秒新しい更新の後、シェルが1回消えることがあります。</span><span class="sxs-lookup"><span data-stu-id="078d6-210">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="078d6-211">**ブルーム** ジェスチャを実行してセッションを再開してください。</span><span class="sxs-lookup"><span data-stu-id="078d6-211">Please perform the **bloom** gesture to resume your session.</span></span>

### <a name="visual-studio"></a><span data-ttu-id="078d6-212">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="078d6-212">Visual Studio</span></span>

- <span data-ttu-id="078d6-213">HoloLens 開発に推奨されている最新バージョンの Visual Studio 用の [ツールをインストール](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) する方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="078d6-213">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>

- <span data-ttu-id="078d6-214">アプリを Visual Studio から HoloLens にデプロイすると、次のエラーが表示されることがあります。 **ユーザーマップセクションが開いているファイルに対して、要求された操作を実行することはできません。(HRESULT からの例外: 0x800704C8)**。</span><span class="sxs-lookup"><span data-stu-id="078d6-214">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="078d6-215">この問題が発生した場合は、もう一度やり直してください。通常、配置は成功します。</span><span class="sxs-lookup"><span data-stu-id="078d6-215">If this happens, try again and your deployment will generally succeed.</span></span>

### <a name="api"></a><span data-ttu-id="078d6-216">API</span><span class="sxs-lookup"><span data-stu-id="078d6-216">API</span></span>

- <span data-ttu-id="078d6-217">アプリケーションがユーザーの背後にある [フォーカスポイント](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) を設定した場合、または通常はカメラから移動した場合、ホログラムは混合の現実キャプチャの写真またはビデオには表示されません。</span><span class="sxs-lookup"><span data-stu-id="078d6-217">If the application sets the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="078d6-218">Windows でこのバグが修正されるまで、アプリケーションが [フォーカスポイント](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) をアクティブに設定している場合は、平面法線が反対のカメラフォワード (たとえば、normal =-camera. forward) に設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="078d6-218">Until this bug is fixed in Windows, if applications actively set the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <a name="xbox-wireless-controller"></a><span data-ttu-id="078d6-219">Xbox ワイヤレス コントローラー</span><span class="sxs-lookup"><span data-stu-id="078d6-219">Xbox Wireless Controller</span></span>

- <span data-ttu-id="078d6-220">Xbox ワイヤレスコントローラーは、HoloLens で使用する前に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="078d6-220">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="078d6-221">コントローラーを HoloLens とペアリングする前に、最新の状態 [に](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) なっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="078d6-221">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>

- <span data-ttu-id="078d6-222">Xbox ワイヤレスコントローラーが接続されている間に HoloLens を再起動すると、コントローラーは HoloLens に自動的に再接続されません。</span><span class="sxs-lookup"><span data-stu-id="078d6-222">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="078d6-223">番組ガイドボタンのライトは、コントローラーが3分後に電源オフになるまで、ゆっくりと点滅します。</span><span class="sxs-lookup"><span data-stu-id="078d6-223">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="078d6-224">コントローラーをすぐに再接続するには、[ガイド] ボタンを押して、ライトがオフになるまでコントローラーの電源をオフにします。</span><span class="sxs-lookup"><span data-stu-id="078d6-224">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="078d6-225">コントローラーの電源を再度オンにすると、HoloLens に再接続されます。</span><span class="sxs-lookup"><span data-stu-id="078d6-225">When you power your controller on again, it will reconnect to HoloLens.</span></span>

- <span data-ttu-id="078d6-226">Xbox ワイヤレスコントローラーが接続されている間に HoloLens がスタンバイ状態になると、コントローラー上の入力があれば HoloLens がウェイクアップされます。</span><span class="sxs-lookup"><span data-stu-id="078d6-226">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="078d6-227">コントローラーの使用が完了したら、コントローラーの電源をオフにすることで回避できます。</span><span class="sxs-lookup"><span data-stu-id="078d6-227">You can prevent this by powering off your controller when you are done using it.</span></span>

