---
title: 展開ガイド–リモートアシスタンスでの展開による、クラウド接続型 HoloLens 2 展開
description: クラウドに接続されたネットワーク経由で HoloLens デバイスの登録およびリモートアシストを検証する方法
keywords: HoloLens、管理、クラウド接続、リモートアシスト、AAD、Azure AD、MDM、モバイルデバイス管理
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 4f4f787d6db16655d5fe3b54438a4524bc9df78f
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196343"
---
# <span data-ttu-id="56e46-104">展開-クラウド接続ガイド</span><span class="sxs-lookup"><span data-stu-id="56e46-104">Deploy - Cloud connected Guide</span></span>

<span data-ttu-id="56e46-105">これですべての設定が完了したので、デバイスを配布する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="56e46-105">Now that you have everything configured you should be ready to distribute devices.</span></span> <span data-ttu-id="56e46-106">ただし、まず設定を検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56e46-106">However, this is when you should first validate your set up.</span></span> <span data-ttu-id="56e46-107">まず、AAD の参加と MDM の登録プロセスを検証し、次にリモートアシスタンスの通話を配置できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="56e46-107">First the AAD Join and MDM Enrollment process should be validated, followed by verifying that a Remote Assist call can be placed.</span></span>

## <span data-ttu-id="56e46-108">登録の検証</span><span class="sxs-lookup"><span data-stu-id="56e46-108">Enrollment Validation</span></span>

<span data-ttu-id="56e46-109">AAD と MDM の登録に適切に構成されたすべての機能がスナップになります。</span><span class="sxs-lookup"><span data-stu-id="56e46-109">With everything properly configured for AAD and MDM Enrollment should now be a snap.</span></span> <span data-ttu-id="56e46-110">&#39;には、Wi-Fi 接続と HoloLens デバイスと、以前に構成された AAD ユーザーアカウントのいずれかが必要です。</span><span class="sxs-lookup"><span data-stu-id="56e46-110">You&#39;ll need a Wi-Fi connection and the HoloLens device, as well as one of the previously configured AAD user accounts.</span></span>

<span data-ttu-id="56e46-111">現在出荷時の設定状態になっているデバイスが&#39;いない場合は、 [デバイスを reflash](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="56e46-111">If your device isn&#39;t currently sitting in a factory settings state, now would be a good time to [reflash the device](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="56e46-112">デバイスが OOBE に表示されたら、操作を開始して、画面の指示に従う必要が&#39;ます。</span><span class="sxs-lookup"><span data-stu-id="56e46-112">Once your device is in OOBE, you&#39;ll need to start interacting and following the prompts.</span></span> 
1. <span data-ttu-id="56e46-113">**この HoloLens の所有者**をたずねるメッセージが表示されますか?</span><span class="sxs-lookup"><span data-stu-id="56e46-113">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="56e46-114">**自分の職場または学校**を選択して、AAD アカウントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="56e46-114">Select **My work or school owns it** and enter your AAD account credentials.</span></span>
1. <span data-ttu-id="56e46-115">登録に成功すると、PIN を設定するように求められ&#39;ます。</span><span class="sxs-lookup"><span data-stu-id="56e46-115">When enrollment is successful, you&#39;ll be prompted to set up a PIN.</span></span> <span data-ttu-id="56e46-116">これは、このユーザのデバイスに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="56e46-116">This is unique to this device for this user.</span></span> <span data-ttu-id="56e46-117">また、虹彩スキャン、音声データ、テレメトリ設定の入力を求められます。最後に、[スタート] メニューを開き、OOBE を完了する方法についても説明します&#39;。</span><span class="sxs-lookup"><span data-stu-id="56e46-117">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you&#39;ll be able to learn how to open the start menu and complete OOBE.</span></span>
1. <span data-ttu-id="56e46-118">Mixed Reality ホームに着陸したら、直前に学習した **開始ジェスチャ** を使って [スタート] メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="56e46-118">Once you land in the Mixed Reality Home open the Start menu using the **Start gesture** you just learned.</span></span> 
1. <span data-ttu-id="56e46-119">[ **設定** ] アプリを選択し、[システム] を選択し **ます。**</span><span class="sxs-lookup"><span data-stu-id="56e46-119">Select the **Settings** app and select **System.**</span></span> <span data-ttu-id="56e46-120">&#39;最初に表示される情報には、お使いのデバイス名が表示されます。 HoloLens 2 デバイスの場合は、 &quot; hololens- &quot; 6 文字の文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="56e46-120">The first piece of information you&#39;ll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a 6 character string.</span></span> 
1. <span data-ttu-id="56e46-121">この名前はメモしておいてください。</span><span class="sxs-lookup"><span data-stu-id="56e46-121">Take note of this name.</span></span>

![HoloLens 2 の設定-バージョン情報](./images/hololens2-settings-about.jpg)

7. <span data-ttu-id="56e46-123">デバイスが設定アプリ内で AAD に正常に登録されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="56e46-123">You can verify that your device is successfully enrolled in the AAD within the Settings app.</span></span> <span data-ttu-id="56e46-124">[**設定**] で、[**アカウント**  ->  **アクセスの職場または学校**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="56e46-124">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="56e46-125">この画面から、 &quot; _Nameofaad_&#39;s Azure AD に接続していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="56e46-125">From this screen you can verify you are successfully enrolled by seeing &quot;Connected to _nameofAAD_&#39;s Azure AD.</span></span> <span data-ttu-id="56e46-126">_ユーザー名_名 onmicrosoft.com によって接続されている @ _nameofAAD_ &quot; 。</span><span class="sxs-lookup"><span data-stu-id="56e46-126">Connected by _yourusername_@_nameofAAD_.onmicrosoft.com&quot;.</span></span>

<span data-ttu-id="56e46-127">デバイスで AAD が結合されていることを確認するには、azure [Portal](https://portal.azure.com/#home)  ->  **azure active directory**デバイスのすべてのデバイスから azure active directory を確認  ->  **Devices**  ->  **All devices**し、デバイス名を検索します。</span><span class="sxs-lookup"><span data-stu-id="56e46-127">To validate the device has AAD Joined we can check the Azure Active Directory from the [Azure Portal](https://portal.azure.com/#home) -> **Azure Active Directory** -> **Devices** -> **All devices** , and search the device name.</span></span> <span data-ttu-id="56e46-128">&#39;、デバイスが Azure Active Directory の一部であることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="56e46-128">You&#39;ll be able to see the device is a part of the Azure Active Directory.</span></span>

![Azure Active Directory-デバイス](./images/aad-enrollment.png)

<span data-ttu-id="56e46-130">次に、&#39;[Microsoft Endpoint Manager 管理センター](https://endpoint.microsoft.com/#home)にログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="56e46-130">Next you&#39;ll need to log into the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="56e46-131">ログインして、[ **デバイス** ]、[ **すべてのデバイス**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="56e46-131">Log in and select **Devices** then **All devices**.</span></span> <span data-ttu-id="56e46-132">ここから、HoloLens デバイス&#39;s 名を検索できます。</span><span class="sxs-lookup"><span data-stu-id="56e46-132">From here you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="56e46-133">Intune に、HoloLens が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="56e46-133">You should be able to see your HoloLens listed on Intune.</span></span>

![Intune デバイス](./images/endpoint-all-devices-enrolled.png)

## <span data-ttu-id="56e46-135">リモートアシスタンス通話の検証</span><span class="sxs-lookup"><span data-stu-id="56e46-135">Remote Assist Call Validation</span></span>

<span data-ttu-id="56e46-136">お使いのデバイスが AAD と MDM の両方に登録されていることを確認した&#39;、テストリモートアシスタンス通話を発信する時間を&#39;します。</span><span class="sxs-lookup"><span data-stu-id="56e46-136">Once you&#39;ve verified that your device is enrolled in both your AAD and MDM, it&#39;s time to place a test Remote Assist call.</span></span> <span data-ttu-id="56e46-137">この検証を&#39;行うには、HoloLens デバイスと Windows 10 PC、および PC 用の2つ目の AAD ユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="56e46-137">For this validation you&#39;ll need to have the HoloLens device and a Windows 10 PC, as well as a second AAD user account for the PC.</span></span>

<span data-ttu-id="56e46-138">この検証手順では、前回の検証手順を行っていて、デバイスが登録されており、AAD ユーザーがデバイスにあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="56e46-138">This validation step will assume that you have previously completed the last validation step and your device is enrolled and your AAD user is on the device.</span></span>

1. <span data-ttu-id="56e46-139">PC に Microsoft Teams をまだインストールしていない&#39;は、 [ここからチームをダウンロード](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)できます。</span><span class="sxs-lookup"><span data-stu-id="56e46-139">If you don&#39;t already have Microsoft Teams installed on your PC you can [download Teams here](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).</span></span>
2. <span data-ttu-id="56e46-140">現在 HoloLens にサインインしているユーザーとは別の AAD ユーザーアカウントを使用して、チームにサインインします。</span><span class="sxs-lookup"><span data-stu-id="56e46-140">Sign into Teams using the second AAD user account than the one currently signed into your HoloLens.</span></span> <span data-ttu-id="56e46-141">PC にサインインすると、通話を受信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="56e46-141">Once signed in your PC you will be ready to receive the call.</span></span>
3. <span data-ttu-id="56e46-142">HoloLens のロックを解除してサインインします。</span><span class="sxs-lookup"><span data-stu-id="56e46-142">Unlock your HoloLens and sign in.</span></span>
4. <span data-ttu-id="56e46-143">リモートアシスタンスアプリを起動するには、[ **スタート] メニュー** を開き、[ **リモートアシスト**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="56e46-143">To launch the Remote Assist app open the **Start Menu** and select **Remote Assist**.</span></span> <span data-ttu-id="56e46-144">リモートアシスタンスは、受信トレイアプリとしてバンドルされるだけでなく、HoloLens 2&#39;s の [スタート] メニューに固定されています。</span><span class="sxs-lookup"><span data-stu-id="56e46-144">Remote Assist is not only bundled as an inbox app but pinned to the HoloLens 2&#39;s start menu.</span></span> <span data-ttu-id="56e46-145">イベントでは、[スタート] メニューにピン留めされていることを確認し&#39;、[ **すべてのアプリ** ] の一覧を開いて探します。</span><span class="sxs-lookup"><span data-stu-id="56e46-145">In an event you don&#39;t see it pinned to the Start menu, then open the **All apps** list to look for it.</span></span>
5. <span data-ttu-id="56e46-146">リモートアシスタンスが開始されると、 [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) 経由でデバイスのユーザーを特定して、アプリにログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="56e46-146">Once Remote Assist starts it should identify the user of the device via [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) and log into the app.</span></span>
6. <span data-ttu-id="56e46-147">アプリ内で、[ **検索** ] を選び、PC 上の2番目のユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="56e46-147">From within the app select **Search** and search for the second user on the PC.</span></span> <span data-ttu-id="56e46-148">通話を開始するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="56e46-148">Select the user to start the call.</span></span>
7. <span data-ttu-id="56e46-149">PC から通話に応答します。</span><span class="sxs-lookup"><span data-stu-id="56e46-149">From your PC answer the call.</span></span>

<span data-ttu-id="56e46-150">お客さまの&#39;が正常に接続されました。リモートアシスタンス通話を利用しています。</span><span class="sxs-lookup"><span data-stu-id="56e46-150">Congratulations, you&#39;ve successfully connected and are on your remote assist call.</span></span> <span data-ttu-id="56e46-151">次のようなリモートアシスト機能を使用してください。</span><span class="sxs-lookup"><span data-stu-id="56e46-151">Make sure to try out specific remote assist features, such as using:</span></span>

- [<span data-ttu-id="56e46-152">手書き入力の注釈</span><span class="sxs-lookup"><span data-stu-id="56e46-152">Inking annotations</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [<span data-ttu-id="56e46-153">Mixed reality でファイルを共有して表示する</span><span class="sxs-lookup"><span data-stu-id="56e46-153">Share a file and view in mixed reality</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [<span data-ttu-id="56e46-154">別の HoloLens アプリのヘルプを表示する</span><span class="sxs-lookup"><span data-stu-id="56e46-154">Get help in another HoloLens app</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <span data-ttu-id="56e46-155">次のステップ</span><span class="sxs-lookup"><span data-stu-id="56e46-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="56e46-156">クラウド接続の展開-管理</span><span class="sxs-lookup"><span data-stu-id="56e46-156">Cloud connected deployment - Maintain</span></span>](hololens2-cloud-connected-maintain.md)