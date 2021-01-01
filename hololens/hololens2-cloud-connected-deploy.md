---
title: 展開ガイド - リモート アシストによるクラウド接続 HoloLens 2 の大規模な展開 - 展開
description: クラウド接続ネットワークを使用して HoloLens デバイスの登録とリモート アシストを検証する方法
keywords: HoloLens, 管理, クラウド接続, リモート アシスト, AAD, Azure AD, MDM, モバイル デバイス管理
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
ms.openlocfilehash: 2b38f4a76ee088d4f892c86de07d8f5a10d2a3bf
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253194"
---
# <span data-ttu-id="aaf54-104">展開 - クラウド接続ガイド</span><span class="sxs-lookup"><span data-stu-id="aaf54-104">Deploy - Cloud connected Guide</span></span>

<span data-ttu-id="aaf54-105">すべての構成が完了したので、デバイスを配布する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="aaf54-105">Now that you have everything configured you should be ready to distribute devices.</span></span> <span data-ttu-id="aaf54-106">ただし、最初にセットアップを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaf54-106">However, now is when you should first validate your setup.</span></span> <span data-ttu-id="aaf54-107">まず、Azure AD Join および MDM 登録プロセスを検証し、次にリモート アシストの呼び出しが可能なか確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaf54-107">First the Azure AD Join and MDM Enrollment process should be validated, followed by verifying that a Remote Assist call can be placed.</span></span>

## <span data-ttu-id="aaf54-108">登録検証</span><span class="sxs-lookup"><span data-stu-id="aaf54-108">Enrollment Validation</span></span>

<span data-ttu-id="aaf54-109">Azure AD と MDM 登録用にすべてが適切に構成されたので、残りはスナップです。</span><span class="sxs-lookup"><span data-stu-id="aaf54-109">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="aaf54-110">以前&#39;AAD ユーザー アカウントWi-Fi接続と HoloLens デバイスの 1 つが必要です。</span><span class="sxs-lookup"><span data-stu-id="aaf54-110">You&#39;ll need a Wi-Fi connection and the HoloLens device, as well as one of the previously configured AAD user accounts.</span></span>

<span data-ttu-id="aaf54-111">デバイスが現在&#39;設定の状態ではない場合は、デバイスを再フラッシュする良 [い時期です](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)。</span><span class="sxs-lookup"><span data-stu-id="aaf54-111">If your device isn&#39;t currently sitting in a factory settings state, now would be a good time to [reflash the device](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="aaf54-112">デバイスが OOBE に入った後、&#39;操作を開始し、プロンプトに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaf54-112">Once your device is in OOBE, you&#39;ll need to start interacting and following the prompts.</span></span> 
1. <span data-ttu-id="aaf54-113">重要なプロンプトは、この **HoloLens の所有者を尋ねらた場合に表示されます。**</span><span class="sxs-lookup"><span data-stu-id="aaf54-113">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="aaf54-114">[ **自分の仕事または学校が所有している** ] を選択し、Azure AD資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="aaf54-114">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>
1. <span data-ttu-id="aaf54-115">登録が成功すると&#39;PIN の設定を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="aaf54-115">When enrollment is successful, you&#39;ll be prompted to set up a PIN.</span></span> <span data-ttu-id="aaf54-116">この PIN は、このユーザーのこのデバイスに固有です。</span><span class="sxs-lookup"><span data-stu-id="aaf54-116">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="aaf54-117">虹彩スキャン、音声データ、テレメトリ設定の入力も求め、最後に&#39;でスタート メニューを開いて OOBE を完了する方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="aaf54-117">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you&#39;ll be able to learn how to open the start menu and complete OOBE.</span></span>
1. <span data-ttu-id="aaf54-118">Mixed Reality ホームに移動したら、学習したスタート ジェスチャを使ってスタート **メニューを** 開きます。</span><span class="sxs-lookup"><span data-stu-id="aaf54-118">Once you land in the Mixed Reality Home open the Start menu using the **Start gesture** you just learned.</span></span>
1. <span data-ttu-id="aaf54-119">設定アプリ **を選択し** 、[システム] を選択 **します。**</span><span class="sxs-lookup"><span data-stu-id="aaf54-119">Select the **Settings** app and select **System.**</span></span> <span data-ttu-id="aaf54-120">表示される最初の情報&#39;デバイス名です。HoloLens 2 デバイスの場合は HOLOLENS、その後に 6 つの文字文字列が続 &quot; &quot; きます。</span><span class="sxs-lookup"><span data-stu-id="aaf54-120">The first piece of information you&#39;ll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>
1. <span data-ttu-id="aaf54-121">この名前をメモします。</span><span class="sxs-lookup"><span data-stu-id="aaf54-121">Take note of this name.</span></span>

![HoloLens 2 の設定 - 概要](./images/hololens2-settings-about.jpg)

7. <span data-ttu-id="aaf54-123">デバイスが設定アプリ内の Azure ADに正常に登録されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="aaf54-123">You can verify that your device is successfully enrolled in the Azure AD within the Settings app.</span></span> <span data-ttu-id="aaf54-124">From **Settings** select **Accounts**Access work  ->  **or school**.</span><span class="sxs-lookup"><span data-stu-id="aaf54-124">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="aaf54-125">この画面で &quot; 、[Connected to _nameofAAD] (nameofAAD_ に接続済み) を表示して、Azure&#39;に登録AD。</span><span class="sxs-lookup"><span data-stu-id="aaf54-125">From this screen you can verify you are successfully enrolled by seeing &quot;Connected to _nameofAAD_&#39;s Azure AD.</span></span> <span data-ttu-id="aaf54-126">接続名__ @ _nameofAAD_.onmicrosoft.com &quot; .</span><span class="sxs-lookup"><span data-stu-id="aaf54-126">Connected by _yourusername_@_nameofAAD_.onmicrosoft.com&quot;.</span></span>


<span data-ttu-id="aaf54-127">デバイスに Azure AD 参加を確認するには[、Azure Portal](https://portal.azure.com/#home)の Azure Active Directory デバイスすべてのデバイスから Azure Active Directory を確認し、デバイス名  ->  \*\*\*\*  ->  \*\*\*\*  ->  \*\*\*\* を検索します。</span><span class="sxs-lookup"><span data-stu-id="aaf54-127">To validate the device has Azure AD Joined we can check the Azure Active Directory from the [Azure portal](https://portal.azure.com/#home) -> **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="aaf54-128">デバイス&#39;Azure Active Directory の一部であるのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="aaf54-128">You&#39;ll be able to see the device is a part of the Azure Active Directory.</span></span>


![Azure Active Directory - デバイス](./images/aad-enrollment.png)

<span data-ttu-id="aaf54-130">次に&#39;Microsoft Endpoint Manager 管理センターに [ログインする必要があります](https://endpoint.microsoft.com/#home)。</span><span class="sxs-lookup"><span data-stu-id="aaf54-130">Next you&#39;ll need to log into the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="aaf54-131">ログインし、[デバイス] を選択 **し、[すべての** デバイス] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="aaf54-131">Log in and select **Devices** then **All devices**.</span></span> <span data-ttu-id="aaf54-132">ここから、HoloLens デバイスの名前&#39;検索できます。</span><span class="sxs-lookup"><span data-stu-id="aaf54-132">From here you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="aaf54-133">Intune に表示されている HoloLens を確認できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaf54-133">You should be able to see your HoloLens listed on Intune.</span></span>

![Intune - デバイス](./images/endpoint-all-devices-enrolled.png)

## <span data-ttu-id="aaf54-135">リモート アシスト通話の検証</span><span class="sxs-lookup"><span data-stu-id="aaf54-135">Remote Assist Call Validation</span></span>

<span data-ttu-id="aaf54-136">デバイス&#39;AAD と MDM の両方に登録されているのを確認したら、&#39;リモート アシスト呼び出しを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaf54-136">Once you&#39;ve verified that your device is enrolled in both your AAD and MDM, it&#39;s time to place a test Remote Assist call.</span></span> <span data-ttu-id="aaf54-137">この検証では&#39;HoloLens デバイスと Windows 10 PC、および PC 用の 2 番目の Azure AD ユーザー アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="aaf54-137">For this validation you&#39;ll need to have the HoloLens device and a Windows 10 PC, as well as a second Azure AD user account for the PC.</span></span>

<span data-ttu-id="aaf54-138">この検証手順では、前回の検証手順が完了し、デバイスが登録され、Azure AD ユーザーがデバイスに登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaf54-138">This validation step will assume that you have previously completed the last validation step and your device is enrolled and your Azure AD user is on the device.</span></span>


1. <span data-ttu-id="aaf54-139">お使いの PC に Microsoft Teams がインストールされていない場合は、ここで [Teams をダウンロードできます](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)。</span><span class="sxs-lookup"><span data-stu-id="aaf54-139">If you don't already have Microsoft Teams installed on your PC, you can [download Teams here](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).</span></span>
2. <span data-ttu-id="aaf54-140">HoloLens に現在サインインしているアカウントAD 2 番目の Azure アカウントを使用して Teams にサインインします。</span><span class="sxs-lookup"><span data-stu-id="aaf54-140">Sign into Teams using the second  Azure AD user account than the one currently signed into your HoloLens.</span></span> <span data-ttu-id="aaf54-141">PC にサインインすると、通話を受信する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="aaf54-141">Once signed in your PC you will be ready to receive the call.</span></span>
3. <span data-ttu-id="aaf54-142">HoloLens のロックを解除し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="aaf54-142">Unlock your HoloLens and sign in.</span></span>
4. <span data-ttu-id="aaf54-143">リモート アシスト アプリを起動するには、[スタート] メニュー **を開き、[** リモート アシスト] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="aaf54-143">To launch the Remote Assist app open the **Start Menu** and select **Remote Assist**.</span></span> <span data-ttu-id="aaf54-144">リモート アシストは、受信トレイ アプリとしてバンドルされているだけでなく、HoloLens 2 のスタート メニュー&#39;ピン留めされています。</span><span class="sxs-lookup"><span data-stu-id="aaf54-144">Remote Assist is not only bundled as an inbox app but pinned to the HoloLens 2&#39;s start menu.</span></span> <span data-ttu-id="aaf54-145">スタート メニューにピン&#39;表示されていない場合は、[すべてのアプリ] の一覧を開\*\*\*\* いて探します。</span><span class="sxs-lookup"><span data-stu-id="aaf54-145">In an event you don&#39;t see it pinned to the Start menu, then open the **All apps** list to look for it.</span></span>
5. <span data-ttu-id="aaf54-146">リモート アシストを起動すると [、SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) を介してデバイスのユーザーを識別し、アプリにログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaf54-146">Once Remote Assist starts it should identify the user of the device via [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) and log into the app.</span></span>
6. <span data-ttu-id="aaf54-147">アプリ内から[検索] **を選択** し、PC で 2 番目のユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="aaf54-147">From within the app, select **Search** and search for the second user on the PC.</span></span> <span data-ttu-id="aaf54-148">通話を開始するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="aaf54-148">Select the user to start the call.</span></span>
7. <span data-ttu-id="aaf54-149">PC から通話に応答します。</span><span class="sxs-lookup"><span data-stu-id="aaf54-149">From your PC, answer the call.</span></span>

<span data-ttu-id="aaf54-150">これで完了です&#39;正常に接続され、リモート アシスト呼び出しに対応しています。</span><span class="sxs-lookup"><span data-stu-id="aaf54-150">Congratulations, you&#39;ve successfully connected and are on your remote assist call.</span></span> <span data-ttu-id="aaf54-151">次の使用など、特定のリモート アシスト機能を試してください。</span><span class="sxs-lookup"><span data-stu-id="aaf54-151">Make sure to try out specific remote assist features, such as using:</span></span>

- [<span data-ttu-id="aaf54-152">インク注釈</span><span class="sxs-lookup"><span data-stu-id="aaf54-152">Inking annotations</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [<span data-ttu-id="aaf54-153">Mixed Reality でファイルとビューを共有する</span><span class="sxs-lookup"><span data-stu-id="aaf54-153">Share a file and view in mixed reality</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [<span data-ttu-id="aaf54-154">別の HoloLens アプリでヘルプを表示する</span><span class="sxs-lookup"><span data-stu-id="aaf54-154">Get help in another HoloLens app</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <span data-ttu-id="aaf54-155">次のステップ</span><span class="sxs-lookup"><span data-stu-id="aaf54-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="aaf54-156">クラウド接続展開 - 保守</span><span class="sxs-lookup"><span data-stu-id="aaf54-156">Cloud connected deployment - Maintain</span></span>](hololens2-cloud-connected-maintain.md)