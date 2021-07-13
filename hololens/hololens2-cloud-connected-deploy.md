---
title: デプロイガイド–リモートアシスタンスを使用した大規模なクラウド接続 HoloLens 2 デプロイ
description: クラウドに接続されたネットワーク経由で HoloLens デバイスの登録とリモートアシスタンスを検証する方法について説明します。
keywords: HoloLens、管理、クラウド接続、リモートアシスタンス、AAD、Azure AD、MDM、モバイルデバイス管理
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
ms.openlocfilehash: b0597806d58d7bf16fe6f6c766af3f9662fca7e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635179"
---
# <a name="deploy---cloud-connected-guide"></a><span data-ttu-id="3f1cb-104">デプロイ-クラウド接続ガイド</span><span class="sxs-lookup"><span data-stu-id="3f1cb-104">Deploy - Cloud connected Guide</span></span>

<span data-ttu-id="3f1cb-105">すべての構成が完了したので、デバイスを配布する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-105">Now that you have everything configured you should be ready to distribute devices.</span></span> <span data-ttu-id="3f1cb-106">ただし、ここでは、最初にセットアップを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-106">However, now is when you should first validate your setup.</span></span> <span data-ttu-id="3f1cb-107">まず、Azure AD 参加と MDM 登録プロセスを検証した後、リモートアシスタンスの呼び出しを配置できることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-107">First the Azure AD Join and MDM Enrollment process should be validated, followed by verifying that a Remote Assist call can be placed.</span></span>

## <a name="enrollment-validation"></a><span data-ttu-id="3f1cb-108">登録の検証</span><span class="sxs-lookup"><span data-stu-id="3f1cb-108">Enrollment Validation</span></span>

<span data-ttu-id="3f1cb-109">これで、Azure AD と MDM 登録のすべてが正しく構成されたので、残りはスナップになります。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-109">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="3f1cb-110">Wi-Fi 接続と HoloLens デバイス、および以前に構成した AAD ユーザーアカウントのいずれかが必要&#39;ます。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-110">You&#39;ll need a Wi-Fi connection and the HoloLens device, as well as one of the previously configured AAD user accounts.</span></span>

<span data-ttu-id="3f1cb-111">現在、デバイスが工場出荷時の設定状態に&#39;ていない場合は、ここで [デバイスを更新](/hololens/hololens-recovery#clean-reflash-the-device)することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-111">If your device isn&#39;t currently sitting in a factory settings state, now would be a good time to [reflash the device](/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="3f1cb-112">デバイスが OOBE になったら、操作を開始し、プロンプトに従って操作を開始する必要が&#39;ます。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-112">Once your device is in OOBE, you&#39;ll need to start interacting and following the prompts.</span></span> 
1. <span data-ttu-id="3f1cb-113">**この HoloLens を所有 Who** ことを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-113">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="3f1cb-114">[ **職場または学校が所有** する] を選択し、Azure AD アカウントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-114">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>
1. <span data-ttu-id="3f1cb-115">登録が成功すると、PIN の設定を求められ&#39;ます。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-115">When enrollment is successful, you&#39;ll be prompted to set up a PIN.</span></span> <span data-ttu-id="3f1cb-116">この PIN は、このユーザーに対してこのデバイスに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-116">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="3f1cb-117">また、虹彩スキャン、音声データ、テレメトリの設定を求められます。最後に、[スタート] メニューを開き、OOBE を完了する方法を学習でき&#39;ます。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-117">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you&#39;ll be able to learn how to open the start menu and complete OOBE.</span></span>
1. <span data-ttu-id="3f1cb-118">Mixed Reality ホームに移動したら、学習した **開始ジェスチャ** を使用してスタートメニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-118">Once you land in the Mixed Reality Home open the Start menu using the **Start gesture** you just learned.</span></span>
1. <span data-ttu-id="3f1cb-119">**設定** アプリを選択し、[システム] を選択し **ます。**</span><span class="sxs-lookup"><span data-stu-id="3f1cb-119">Select the **Settings** app and select **System.**</span></span> <span data-ttu-id="3f1cb-120">&#39;最初に表示される情報は、デバイス名です。これは、HoloLens 2 デバイスの場合は &quot; HoloLens- &quot; その後に6文字の文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-120">The first piece of information you&#39;ll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>
1. <span data-ttu-id="3f1cb-121">この名前をメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-121">Take note of this name.</span></span>

![HoloLens 2 設定](./images/hololens2-settings-about.jpg)

7. <span data-ttu-id="3f1cb-123">デバイスが設定アプリ内の Azure AD に正常に登録されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-123">You can verify that your device is successfully enrolled in the Azure AD within the Settings app.</span></span> <span data-ttu-id="3f1cb-124">**設定**[   ->  **職場または学校にアクセス** するアカウント] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-124">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="3f1cb-125">この画面では、 &quot; _Nameofaad_&#39;s Azure AD に接続されていることを確認して、正常に登録されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-125">From this screen you can verify you are successfully enrolled by seeing &quot;Connected to _nameofAAD_&#39;s Azure AD.</span></span> <span data-ttu-id="3f1cb-126">_ユーザー名_ @ _nameofaad_ によって接続され &quot; ます。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-126">Connected by _yourusername_@_nameofAAD_.onmicrosoft.com&quot;.</span></span>


<span data-ttu-id="3f1cb-127">デバイスが参加して Azure AD かどうかを検証するには、[ [Azure portal](https://portal.azure.com/#home)  ->  **Azure Active Directory** デバイスのすべてのデバイス] から Azure Active Directory を確認  ->    ->  し、デバイス名を検索します。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-127">To validate the device has Azure AD Joined we can check the Azure Active Directory from the [Azure portal](https://portal.azure.com/#home) -> **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="3f1cb-128">デバイスが Azure Active Directory の一部であることを確認でき&#39;ます。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-128">You&#39;ll be able to see the device is a part of the Azure Active Directory.</span></span>


![Azure Active Directory-デバイス](./images/aad-enrollment.png)

<span data-ttu-id="3f1cb-130">次に&#39;[Microsoft エンドポイントマネージャー管理センター](https://endpoint.microsoft.com/#home)にログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-130">Next you&#39;ll need to log into the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="3f1cb-131">ログインし、[ **デバイス** ]、[ **すべてのデバイス**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-131">Log in and select **Devices** then **All devices**.</span></span> <span data-ttu-id="3f1cb-132">ここから、HoloLens デバイス&#39;s 名を検索できます。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-132">From here you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="3f1cb-133">HoloLens が Intune に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-133">You should be able to see your HoloLens listed on Intune.</span></span>

![Intune-デバイス](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a><span data-ttu-id="3f1cb-135">リモートアシスタンス呼び出しの検証</span><span class="sxs-lookup"><span data-stu-id="3f1cb-135">Remote Assist Call Validation</span></span>

<span data-ttu-id="3f1cb-136">デバイスが AAD と MDM の両方に登録されていることを確認したら、テストリモートアシスタンス呼び出しを行う時間を&#39;&#39;ます。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-136">Once you&#39;ve verified that your device is enrolled in both your AAD and MDM, it&#39;s time to place a test Remote Assist call.</span></span> <span data-ttu-id="3f1cb-137">この検証では、HoloLens デバイスと Windows 10 pc、および pc の2つ目の Azure AD ユーザーアカウントが必要&#39;ます。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-137">For this validation you&#39;ll need to have the HoloLens device and a Windows 10 PC, as well as a second Azure AD user account for the PC.</span></span>

<span data-ttu-id="3f1cb-138">この検証手順では、前回の検証手順が既に完了していて、デバイスが登録されていて、Azure AD ユーザーがデバイス上にあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-138">This validation step will assume that you have previously completed the last validation step and your device is enrolled and your Azure AD user is on the device.</span></span>


1. <span data-ttu-id="3f1cb-139">PC にまだ Microsoft Teams がインストールされていない場合は、[こちら Teams をダウンロード](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)できます。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-139">If you don't already have Microsoft Teams installed on your PC, you can [download Teams here](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).</span></span>
2. <span data-ttu-id="3f1cb-140">HoloLens に現在サインインしているユーザーアカウントとは別の Azure AD ユーザーアカウントを使用して Teams サインインします。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-140">Sign into Teams using the second  Azure AD user account than the one currently signed into your HoloLens.</span></span> <span data-ttu-id="3f1cb-141">PC にサインインすると、電話を受ける準備が整います。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-141">Once signed in your PC you will be ready to receive the call.</span></span>
3. <span data-ttu-id="3f1cb-142">HoloLens のロックを解除してサインインします。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-142">Unlock your HoloLens and sign in.</span></span>
4. <span data-ttu-id="3f1cb-143">リモートアシスタンスアプリを起動するには、[ **スタート] メニュー** を開き、[ **リモート** アシスタンス] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-143">To launch the Remote Assist app open the **Start Menu** and select **Remote Assist**.</span></span> <span data-ttu-id="3f1cb-144">リモートアシスタンスは、受信トレイアプリとしてのみバンドルされていますが、HoloLens 2&#39;s スタートメニューにピン留めされています。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-144">Remote Assist is not only bundled as an inbox app but pinned to the HoloLens 2&#39;s start menu.</span></span> <span data-ttu-id="3f1cb-145">イベントでは、スタートメニューにピン留めされていない&#39;、[**すべてのアプリ**] の一覧を開いて検索します。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-145">In an event you don&#39;t see it pinned to the Start menu, then open the **All apps** list to look for it.</span></span>
5. <span data-ttu-id="3f1cb-146">リモートアシスタンスが開始されると、 [SSO](/azure/active-directory/manage-apps/what-is-single-sign-on) 経由でデバイスのユーザーを識別し、アプリにログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-146">Once Remote Assist starts it should identify the user of the device via [SSO](/azure/active-directory/manage-apps/what-is-single-sign-on) and log into the app.</span></span>
6. <span data-ttu-id="3f1cb-147">アプリ内で [ **検索** ] を選択し、PC で2番目のユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-147">From within the app, select **Search** and search for the second user on the PC.</span></span> <span data-ttu-id="3f1cb-148">呼び出しを開始するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-148">Select the user to start the call.</span></span>
7. <span data-ttu-id="3f1cb-149">PC から通話に応答します。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-149">From your PC, answer the call.</span></span>

<span data-ttu-id="3f1cb-150">正常に接続されましたが、リモートアシスタンスの電話に&#39;ます。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-150">Congratulations, you&#39;ve successfully connected and are on your remote assist call.</span></span> <span data-ttu-id="3f1cb-151">次のような特定のリモートアシスタンス機能を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="3f1cb-151">Make sure to try out specific remote assist features, such as using:</span></span>

- [<span data-ttu-id="3f1cb-152">インク注釈</span><span class="sxs-lookup"><span data-stu-id="3f1cb-152">Inking annotations</span></span>](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [<span data-ttu-id="3f1cb-153">ファイルとビューを mixed reality で共有する</span><span class="sxs-lookup"><span data-stu-id="3f1cb-153">Share a file and view in mixed reality</span></span>](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [<span data-ttu-id="3f1cb-154">別の HoloLens アプリのヘルプを取得する</span><span class="sxs-lookup"><span data-stu-id="3f1cb-154">Get help in another HoloLens app</span></span>](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a><span data-ttu-id="3f1cb-155">次のステップ</span><span class="sxs-lookup"><span data-stu-id="3f1cb-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3f1cb-156">クラウドに接続されたデプロイ-管理</span><span class="sxs-lookup"><span data-stu-id="3f1cb-156">Cloud connected deployment - Maintain</span></span>](hololens2-cloud-connected-maintain.md)