---
title: 展開ガイド – Dynamics 365 ガイドを使用した企業接続 HoloLens 2 - 展開
description: Dynamics 365 ガイドを使用して企業の接続ネットワークを使用して HoloLens 2 デバイスの展開をセットアップする方法について説明します。
keywords: HoloLens、管理、企業接続、Dynamics 365 ガイド、AAD、Azure AD、MDM、モバイル デバイス管理
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: febf56f94a5cab623fd7ad08ae7abf7050224717
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448587"
---
# <a name="deploy---corporate-connected-guide"></a><span data-ttu-id="303f7-104">展開 - 企業向けコネクテッド ガイド</span><span class="sxs-lookup"><span data-stu-id="303f7-104">Deploy - Corporate Connected Guide</span></span>

<span data-ttu-id="303f7-105">各展開の重要な部分は、エンド ユーザーのスムーズなエクスペリエンスを確保するために、展開を自分でテストする前に、展開が適切にセットアップされていることを確認する点です。</span><span class="sxs-lookup"><span data-stu-id="303f7-105">An important part of each deployment is ensuring that your deployment is properly set up before testing it yourself to ensure a smooth experience for the end user.</span></span>

<span data-ttu-id="303f7-106">MDM を介して Wi-Fi 証明書を展開する場合、最初に HoloLens をセットアップし、開いている Wi-Fi ネットワークまたは証明書を必要としないネットワークにデバイスを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="303f7-106">Because we are deploying the Wi-Fi certificate via MDM, we'll need to initially set up HoloLens and enroll devices on an open Wi-Fi network, or a network that doesn't require the certificate.</span></span> <span data-ttu-id="303f7-107">HoloLens が OOBE と登録を完了すると、デバイスは以前に構成されたネットワーク証明書と LOB を受け取り、両方がデバイスによって受信されたのを検証できます。</span><span class="sxs-lookup"><span data-stu-id="303f7-107">Once the HoloLens has finished OOBE and Enrolled, the device will receive the network certificate and LOB configured previously and we'll be able to validate both were received by the device.</span></span>

<span data-ttu-id="303f7-108">その後、テスト ガイドを作成して操作できると確認できます。</span><span class="sxs-lookup"><span data-stu-id="303f7-108">Afterwards, you'll be able confirm you can both author and operate a test Guide.</span></span>

## <a name="enrollment-validation"></a><span data-ttu-id="303f7-109">登録の検証</span><span class="sxs-lookup"><span data-stu-id="303f7-109">Enrollment Validation</span></span>

<span data-ttu-id="303f7-110">Azure AD MDM 登録用にすべてが適切に構成されたので、残りはスナップになるはずです。</span><span class="sxs-lookup"><span data-stu-id="303f7-110">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="303f7-111">接続と HoloLens Wi-Fi、以前に構成された Azure ユーザー アカウントの 1 つADがあります。</span><span class="sxs-lookup"><span data-stu-id="303f7-111">You'll need a Wi-Fi connection and the HoloLens device, and one of the previously configured Azure AD user accounts.</span></span>

<span data-ttu-id="303f7-112">デバイスが現在工場出荷時の設定状態に座ってない場合は、デバイスを再フラッシュ [する良い時期になります](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)。</span><span class="sxs-lookup"><span data-stu-id="303f7-112">If your device isn't currently sitting in a factory settings state, now would be a good time to [reflash the device](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="303f7-113">デバイスが OOBE に入った後、プロンプトの操作と実行を開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="303f7-113">Once your device is in OOBE, you'll need to start interacting and following the prompts.</span></span>

2. <span data-ttu-id="303f7-114">Wi-Fi に参加Wi-Fi証明書を必要としない開いているネットワークに接続します。</span><span class="sxs-lookup"><span data-stu-id="303f7-114">Connect to an open Wi-Fi network that does not require certificates to join the Wi-Fi.</span></span> <span data-ttu-id="303f7-115">これにより、デバイスは、初期セットアップ後に組織のサーバーで使用するWi-Fiダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="303f7-115">This will allow the device to download the certificate to be used on the organization's Wi-Fi after initial setup.</span></span>

3. <span data-ttu-id="303f7-116">重要なプロンプトは、この HoloLens を所有しているユーザーを **確認するメッセージが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="303f7-116">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="303f7-117">[ **自分の仕事または学校が所有している] を選択し** 、Azure アカウントAD入力します。</span><span class="sxs-lookup"><span data-stu-id="303f7-117">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>

4. <span data-ttu-id="303f7-118">登録が成功すると、PIN の設定を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="303f7-118">When enrollment is successful, you'll be prompted to set up a PIN.</span></span> <span data-ttu-id="303f7-119">この PIN は、このユーザーのこのデバイスに固有です。</span><span class="sxs-lookup"><span data-stu-id="303f7-119">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="303f7-120">また、Iris スキャン、音声データ、テレメトリ設定を求めるメッセージが表示され、最後にスタート メニューを開いて OOBE を完了する方法を学習できます。</span><span class="sxs-lookup"><span data-stu-id="303f7-120">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you'll be able to learn how to open the start menu and complete OOBE.</span></span>

5. <span data-ttu-id="303f7-121">Mixed Reality Home に着陸したら、学習したスタート ジェスチャを使用して **[スタート** ] メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="303f7-121">Once you land in the Mixed Reality Home, open the Start menu using the **Start gesture** you just learned.</span></span>

6. <span data-ttu-id="303f7-122">[設定] **アプリを選択** し、[システム] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="303f7-122">Select the **Settings** app and select **System**.</span></span> <span data-ttu-id="303f7-123">表示される情報の最初の部分はデバイス名です。HoloLens 2 デバイスの場合は HOLOLENS で、その後に 6 文字の文字列が &quot; &quot; 続きます。</span><span class="sxs-lookup"><span data-stu-id="303f7-123">The first piece of information you'll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>

7. <span data-ttu-id="303f7-124">この名前をメモします。</span><span class="sxs-lookup"><span data-stu-id="303f7-124">Take note of this name.</span></span>

    ![HoloLens 2 [設定] 画面](./images/hololens2-settings-about.jpg)

8. <span data-ttu-id="303f7-126">デバイスが Azure サーバーに正常に参加AD。</span><span class="sxs-lookup"><span data-stu-id="303f7-126">Verify that your device is successfully joined to Azure AD.</span></span> <span data-ttu-id="303f7-127">2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="303f7-127">There are two ways;</span></span>

    1.  <span data-ttu-id="303f7-128">設定アプリ。</span><span class="sxs-lookup"><span data-stu-id="303f7-128">The Settings app.</span></span> <span data-ttu-id="303f7-129">[設定 **] から 、[** アカウント**アクセス**  ->  **の作業時間または学校] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="303f7-129">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="303f7-130">この画面から、「接続済み nameofAAD」を参照して、正常に登録されたことを確認&#39;&quot; Azure AD。</span><span class="sxs-lookup"><span data-stu-id="303f7-130">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="303f7-131">によって接続\*\* yourusername@nameofAAD.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="303f7-131">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="303f7-132">これにより、デバイスが組織の Azure サーバーに参加&#39;確認AD。</span><span class="sxs-lookup"><span data-stu-id="303f7-132">This will verify your device is joined to your organization&#39;s Azure AD.</span></span>

    1. <span data-ttu-id="303f7-133">[Azure portal](https://portal.azure.com/#home).</span><span class="sxs-lookup"><span data-stu-id="303f7-133">The [Azure portal](https://portal.azure.com/#home).</span></span> <span data-ttu-id="303f7-134">[Azure **Active Directory**  ->  **Devices] [**  ->  **すべてのデバイス] に移動**し、デバイス名を検索します。</span><span class="sxs-lookup"><span data-stu-id="303f7-134">Go to **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="303f7-135">[参加の種類] の下に、'Azure AD' と表示されます。</span><span class="sxs-lookup"><span data-stu-id="303f7-135">Under Join Type, it will show as being 'Azure AD Joined'.</span></span>
        ![Azure サーバーで参加の種類を確認AD](./images/hololens2-devices-all-devices.png)

9. <span data-ttu-id="303f7-137">デバイスが MDM に登録されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="303f7-137">Verify that your device is enrolled with MDM.</span></span> <span data-ttu-id="303f7-138">2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="303f7-138">There are two ways;</span></span>

    1. <span data-ttu-id="303f7-139">[設定 **] から**、[アカウント**アクセスの**  ->  **仕事または学校] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="303f7-139">From **Settings**, select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="303f7-140">この画面から、「接続済み nameofAAD」を参照して、正常に登録されたことを確認&#39;&quot; Azure AD。</span><span class="sxs-lookup"><span data-stu-id="303f7-140">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="303f7-141">によって接続\*\* yourusername@nameofAAD.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="303f7-141">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="303f7-142">この Access の仕事または学校のアカウントで、[nameofAAD に接続] を選択&#39;&quot; Azure AD。</span><span class="sxs-lookup"><span data-stu-id="303f7-142">From this Access work or school account by selecting &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="303f7-143">[情報] &quot; yourusername@nameofAAD.onmicrosoft.com[情報] ボタンを **選択** します。</span><span class="sxs-lookup"><span data-stu-id="303f7-143">Connected by yourusername@nameofAAD.onmicrosoft.com&quot; and select the **Info** button.</span></span>

    1. <span data-ttu-id="303f7-144">[Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home).</span><span class="sxs-lookup"><span data-stu-id="303f7-144">[Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="303f7-145">ログインし、[デバイス] 、[**すべてのデバイス\*\*\*\*] の順に選択します**。</span><span class="sxs-lookup"><span data-stu-id="303f7-145">Log in and select  **Devices**  then  **All devices**.</span></span> <span data-ttu-id="303f7-146">ここから、HoloLens デバイスの名前&#39;検索できます。</span><span class="sxs-lookup"><span data-stu-id="303f7-146">From here, you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="303f7-147">HoloLens が Intune に一覧表示されているのを確認できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="303f7-147">You should be able to see your HoloLens listed on Intune.</span></span>

        ![Azure の Intune によって管理されるAD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a><span data-ttu-id="303f7-149">Wi-Fi証明書の検証</span><span class="sxs-lookup"><span data-stu-id="303f7-149">Wi-Fi certificate validation</span></span>

<span data-ttu-id="303f7-150">これで、デバイスは証明書を受け取Wi-Fiがあります。</span><span class="sxs-lookup"><span data-stu-id="303f7-150">By now, the device should have received the Wi-Fi certificate.</span></span> <span data-ttu-id="303f7-151">最も簡単な検証は、証明書を受け取ったWi-Fi接続&#39;試みです。</span><span class="sxs-lookup"><span data-stu-id="303f7-151">The simplest validation you can do is attempt to connect to the Wi-Fi connection for which you&#39;ve received the certificate.</span></span> <span data-ttu-id="303f7-152">[設定] アプリ**を開**き **、[ &amp; ネットワーク**インターネット  ->  **Wi-Fi] に移動し、Wi-Fi**接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="303f7-152">Open up the **Settings** app and navigate to **Network &amp; Internet** -> **Wi-Fi** and select the Wi-fi connection.</span></span> <span data-ttu-id="303f7-153">接続が完了したら、Microsoft Edge アプリを開き、Web サイトに移動できます。</span><span class="sxs-lookup"><span data-stu-id="303f7-153">Once connected, open up the Microsoft Edge app and confirm you can navigate to a website.</span></span>

<span data-ttu-id="303f7-154">デバイスで証明書を受信したと確認するには、証明書マネージャーを [使用します](https://docs.microsoft.com/hololens/certificate-manager)。</span><span class="sxs-lookup"><span data-stu-id="303f7-154">To confirm that you have received the certificate on the device, you can use the [Certificate Manager](https://docs.microsoft.com/hololens/certificate-manager).</span></span>

## <a name="validate-lob-app-install"></a><span data-ttu-id="303f7-155">LOB アプリのインストールを検証する</span><span class="sxs-lookup"><span data-stu-id="303f7-155">Validate LOB app install</span></span>

<span data-ttu-id="303f7-156">管理アプリのインストールの進行状況を確認するには、アプリがインストールされているのか、[設定] を確認します。</span><span class="sxs-lookup"><span data-stu-id="303f7-156">To see a managed app's install progress, you either see if the app is installed or check Settings.</span></span> <span data-ttu-id="303f7-157">LOB アプリをグループの必須インストールとして構成することで、HoloLens を割り当てられたグループのユーザーと登録した後、アプリは HoloLens に自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="303f7-157">By configuring a LOB app as a required installation for our group, after enrolling the HoloLens with a user in the assigned group, the app will automatically download to the HoloLens.</span></span>

<span data-ttu-id="303f7-158">[スタート] メニューを開き、[すべてのアプリ **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="303f7-158">Open the Start menu and select **All apps**.</span></span> <span data-ttu-id="303f7-159">アプリの数によっては、ページの上ボタンまたはページダウン ボタンを使用\*\*\*\*\*\*する必要\*\*があります。</span><span class="sxs-lookup"><span data-stu-id="303f7-159">Depending on the number of apps you have, you may need to use the **page up** or **page down** buttons.</span></span>

<span data-ttu-id="303f7-160">デバイス上のアプリのインストールを検証するには、Settings \*\*\*\*  ->  \*\*\*\*  ->  \*\*Accounts Access\*\*\*\*\*\* の作業または学校から行い、アカウントの [情報] ボタンを選択し、下にスクロールして MDM からデバイスに適用されるさまざまな構成とアプリを確認します。</span><span class="sxs-lookup"><span data-stu-id="303f7-160">To validate the installation of the app on device, you can do so via **Settings** -> **Accounts** -> **Access work or school**; select the account then the **Info** button, and scroll down to see different configurations and apps applied to the device from MDM.</span></span>

<span data-ttu-id="303f7-161">Intune からインストールを検証するには[、MEM](https://endpoint.microsoft.com/#home)ポータル アプリ  ->  \*\*\*\*-> [すべての\*\*\*\* アプリ]  -> *TheNameOfYourApp*デバイスのインストール状態ページ  ->  **に移動**します。</span><span class="sxs-lookup"><span data-stu-id="303f7-161">To validate the install from Intune, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** ->*TheNameOfYourApp* -> **Device install status** page.</span></span>

<span data-ttu-id="303f7-162">詳細: [HoloLens 用 Intune アプリの展開](https://docs.microsoft.com/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="303f7-162">See more: [Intune App Deployment for HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)</span></span>

## <a name="validate-dynamics-365-guides"></a><span data-ttu-id="303f7-163">Dynamics 365 ガイドの検証</span><span class="sxs-lookup"><span data-stu-id="303f7-163">Validate Dynamics 365 Guides</span></span>

<span data-ttu-id="303f7-164">HoloLens のガイド アプリには、オーサリングと操作のモードがあります。</span><span class="sxs-lookup"><span data-stu-id="303f7-164">There are modes for the Guides app on HoloLens, authoring and operating.</span></span> <span data-ttu-id="303f7-165">ガイドを操作する前に、ガイドの作成を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="303f7-165">You'll need to finish authoring a guide before operating it.</span></span>

### <a name="authoring-the-guide"></a><span data-ttu-id="303f7-166">ガイドの作成</span><span class="sxs-lookup"><span data-stu-id="303f7-166">Authoring the Guide</span></span>

<span data-ttu-id="303f7-167">この迅速な検証のために多くのことを行う必要はない。</span><span class="sxs-lookup"><span data-stu-id="303f7-167">We don't need to do much for this quick validation.</span></span> <span data-ttu-id="303f7-168">PC で準備したガイドを選択します。</span><span class="sxs-lookup"><span data-stu-id="303f7-168">Simply select the guide you prepared on your PC.</span></span> <span data-ttu-id="303f7-169">ガイドをアンカーする必要 [があります](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor)。簡単な検証のためには、ホログラフィック アンカーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="303f7-169">You'll need to [anchor the guide](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor), for a quick validation you can use a holographic anchor.</span></span> <span data-ttu-id="303f7-170">その後、手順と [モデルを配置する必要があります](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation)。</span><span class="sxs-lookup"><span data-stu-id="303f7-170">Afterwards, you should [place your steps and models](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation).</span></span>

>[!NOTE]
> <span data-ttu-id="303f7-171">HoloLens **で** PC と作成者にログインするには、オーサリング ロールが必要です。</span><span class="sxs-lookup"><span data-stu-id="303f7-171">You will need the **Authoring** role to login to the PC and author on the HoloLens.</span></span> <span data-ttu-id="303f7-172">Operator ロールは読み取り専用で、PC アプリにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="303f7-172">The Operator role is read-only and has no access to the PC app.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a><span data-ttu-id="303f7-173">ガイドの操作</span><span class="sxs-lookup"><span data-stu-id="303f7-173">Operating the Guide</span></span>

<span data-ttu-id="303f7-174">ホログラムを配置したら、ガイドの操作をテストできます。</span><span class="sxs-lookup"><span data-stu-id="303f7-174">Once your holograms are in place, you can test out operating your guide.</span></span> 
- <span data-ttu-id="303f7-175">[演算子 **モードの選択]**</span><span class="sxs-lookup"><span data-stu-id="303f7-175">Select **Operator mode**</span></span>
- <span data-ttu-id="303f7-176">ガイドの手順をクリックします。</span><span class="sxs-lookup"><span data-stu-id="303f7-176">Click through the steps of your guide.</span></span>

<span data-ttu-id="303f7-177">ガイドの操作方法に関する詳細なガイダンスについては、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="303f7-177">For more in-depth guidance on how to operate a guide, check out these resources:</span></span>

[<span data-ttu-id="303f7-178">Dynamics 365 ガイドでのガイドの操作の概要</span><span class="sxs-lookup"><span data-stu-id="303f7-178">Overview of operating a guide in Dynamics 365 Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-overview)

[<span data-ttu-id="303f7-179">Dynamics 365 Guides で Step カードをオペレーターとして使用する</span><span class="sxs-lookup"><span data-stu-id="303f7-179">Get oriented with the Step card as an operator in Dynamics 365 Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a><span data-ttu-id="303f7-180">次の手順</span><span class="sxs-lookup"><span data-stu-id="303f7-180">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="303f7-181">企業の接続展開 - メンテナンス</span><span class="sxs-lookup"><span data-stu-id="303f7-181">Corporate connected deployment - Maintain</span></span>](hololens2-corp-connected-maintain.md)
