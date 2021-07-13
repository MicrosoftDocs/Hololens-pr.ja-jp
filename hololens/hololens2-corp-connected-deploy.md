---
title: デプロイ ガイド – 企業接続HoloLens 2 Dynamics 365 Guides - デプロイ
description: デバイスを使用して企業の接続済みネットワークHoloLens 2デバイスの展開を設定する方法についてDynamics 365 Guides。
keywords: HoloLens、管理、企業接続、Dynamics 365 Guides、AAD、Azure AD、MDM、Mobile デバイス管理
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
ms.openlocfilehash: 6407517bca9efd02fdaf45a78cba7a215ec05670
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637066"
---
# <a name="deploy---corporate-connected-guide"></a><span data-ttu-id="6a8aa-104">デプロイ - 企業接続ガイド</span><span class="sxs-lookup"><span data-stu-id="6a8aa-104">Deploy - Corporate Connected Guide</span></span>

<span data-ttu-id="6a8aa-105">各デプロイの重要な部分は、エンド ユーザーのスムーズなエクスペリエンスを確保するために、自分でテストする前にデプロイが適切に設定されていることを確認する点です。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-105">An important part of each deployment is ensuring that your deployment is properly set up before testing it yourself to ensure a smooth experience for the end user.</span></span>

<span data-ttu-id="6a8aa-106">MDM を使用して Wi-Fi 証明書を展開するために、最初に HoloLens を設定し、開いている Wi-Fi ネットワークまたは証明書を必要としないネットワークにデバイスを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-106">Because we are deploying the Wi-Fi certificate via MDM, we'll need to initially set up HoloLens and enroll devices on an open Wi-Fi network, or a network that doesn't require the certificate.</span></span> <span data-ttu-id="6a8aa-107">HoloLens OOBE と登録が完了すると、デバイスは前に構成したネットワーク証明書と LOB を受け取り、両方がデバイスによって受信されたと検証できます。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-107">Once the HoloLens has finished OOBE and Enrolled, the device will receive the network certificate and LOB configured previously and we'll be able to validate both were received by the device.</span></span>

<span data-ttu-id="6a8aa-108">その後、テスト ガイドを作成して操作できると確認できます。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-108">Afterwards, you'll be able confirm you can both author and operate a test Guide.</span></span>

## <a name="enrollment-validation"></a><span data-ttu-id="6a8aa-109">登録の検証</span><span class="sxs-lookup"><span data-stu-id="6a8aa-109">Enrollment Validation</span></span>

<span data-ttu-id="6a8aa-110">アプリケーションと MDM 登録用にすべてがAzure AD構成されたので、残りはスナップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-110">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="6a8aa-111">ユーザー アカウントに接続Wi-FiデバイスHoloLens、以前に構成したデバイスの 1 つAzure AD必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-111">You'll need a Wi-Fi connection and the HoloLens device, and one of the previously configured Azure AD user accounts.</span></span>

<span data-ttu-id="6a8aa-112">デバイスが現在出荷時の設定状態ではない場合は、デバイス を再フラッシュする [良い時期になります](/hololens/hololens-recovery#clean-reflash-the-device)。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-112">If your device isn't currently sitting in a factory settings state, now would be a good time to [reflash the device](/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="6a8aa-113">デバイスが OOBE に入った後は、対話を開始し、プロンプトに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-113">Once your device is in OOBE, you'll need to start interacting and following the prompts.</span></span>

2. <span data-ttu-id="6a8aa-114">Connectに参加する証明書Wi-Fiを必要としない、開いているネットワークに接続します。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-114">Connect to an open Wi-Fi network that does not require certificates to join the Wi-Fi.</span></span> <span data-ttu-id="6a8aa-115">これにより、デバイスは、初期セットアップ後に組織のアカウントで使用される証明書Wi-Fiダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-115">This will allow the device to download the certificate to be used on the organization's Wi-Fi after initial setup.</span></span>

3. <span data-ttu-id="6a8aa-116">重要なプロンプトは、このサービスを **Who求めるメッセージが表示HoloLens?**</span><span class="sxs-lookup"><span data-stu-id="6a8aa-116">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="6a8aa-117">[ **マイ ワークまたは学校が所有している] を選択し** 、アカウントの資格情報Azure AD入力します。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-117">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>

4. <span data-ttu-id="6a8aa-118">登録が成功すると、PIN の設定を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-118">When enrollment is successful, you'll be prompted to set up a PIN.</span></span> <span data-ttu-id="6a8aa-119">この PIN は、このユーザーに対してこのデバイスに固有です。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-119">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="6a8aa-120">あやめスキャン、音声データ、テレメトリ設定の入力も求め、最後にスタート メニューを開いて OOBE を完了する方法を学習できます。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-120">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you'll be able to learn how to open the start menu and complete OOBE.</span></span>

5. <span data-ttu-id="6a8aa-121">[ホーム] に移動Mixed Reality、学習スタート メニュー開始ジェスチャを使用して **アプリを開** きます。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-121">Once you land in the Mixed Reality Home, open the Start menu using the **Start gesture** you just learned.</span></span>

6. <span data-ttu-id="6a8aa-122">アプリを選択 **設定、[** システム] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-122">Select the **Settings** app and select **System**.</span></span> <span data-ttu-id="6a8aa-123">最初に表示される情報は、デバイス名です。HoloLens 2 デバイスの場合は HOLOLENS で、その後に 6 文字の文字列が &quot; &quot; 続きます。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-123">The first piece of information you'll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>

7. <span data-ttu-id="6a8aa-124">この名前をメモします。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-124">Take note of this name.</span></span>

    ![HoloLens 2 設定画面](./images/hololens2-settings-about.jpg)

8. <span data-ttu-id="6a8aa-126">デバイスがデバイスに正常に参加Azure AD。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-126">Verify that your device is successfully joined to Azure AD.</span></span> <span data-ttu-id="6a8aa-127">次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-127">There are two ways;</span></span>

    1.  <span data-ttu-id="6a8aa-128">アプリ設定します。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-128">The Settings app.</span></span> <span data-ttu-id="6a8aa-129">[アカウント **設定\*\*\*\*アクセスの**  ->  **仕事または学校] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-129">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="6a8aa-130">この画面から、[Connected &quot; to nameofAAD]/(nameofAAD に接続済み)[connected to s&#39;s Azure AD。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-130">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="6a8aa-131">によって接続されます *yourusername@nameofAAD.onmicrosoft.com* 。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-131">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="6a8aa-132">これにより、デバイスが組織の組織に参加&#39;確認Azure AD。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-132">This will verify your device is joined to your organization&#39;s Azure AD.</span></span>

    1. <span data-ttu-id="6a8aa-133">[Azure ポータル](https://portal.azure.com/#home)。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-133">The [Azure portal](https://portal.azure.com/#home).</span></span> <span data-ttu-id="6a8aa-134">[デバイス **Azure Active Directory**  ->  **すべてのデバイス**] に  ->  **移動** し、デバイス名を検索します。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-134">Go to **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="6a8aa-135">[結合の種類] の下に 、"結合されたAzure AD表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-135">Under Join Type, it will show as being 'Azure AD Joined'.</span></span>
        <span data-ttu-id="6a8aa-136">![[結合の種類] を [確認] Azure AD](./images/hololens2-devices-all-devices.png)</span><span class="sxs-lookup"><span data-stu-id="6a8aa-136">![Verify Join Type in Azure AD](./images/hololens2-devices-all-devices.png)</span></span>

9. <span data-ttu-id="6a8aa-137">デバイスが MDM に登録されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-137">Verify that your device is enrolled with MDM.</span></span> <span data-ttu-id="6a8aa-138">次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-138">There are two ways;</span></span>

    1. <span data-ttu-id="6a8aa-139">[アカウント **設定、**[アカウント] [**アクセス] の**  ->  **[仕事または学校] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-139">From **Settings**, select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="6a8aa-140">この画面から、[Connected &quot; to nameofAAD]/(nameofAAD に接続済み)[connected to s&#39;s Azure AD。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-140">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="6a8aa-141">によって接続されます *yourusername@nameofAAD.onmicrosoft.com* 。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-141">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="6a8aa-142">この [Access work or school account]/(この [仕事または学校アカウントにアクセスする]) で、[接続済み] &quot; [nameofAAD]&#39;選択Azure AD。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-142">From this Access work or school account by selecting &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="6a8aa-143">[接続者 yourusername@nameofAAD.onmicrosoft.com &quot; ] を選択し、[**情報] ボタンを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-143">Connected by yourusername@nameofAAD.onmicrosoft.com&quot; and select the **Info** button.</span></span>

    1. <span data-ttu-id="6a8aa-144">[Microsoft エンドポイント マネージャー 管理センター に移動します](https://endpoint.microsoft.com/#home)。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-144">[Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="6a8aa-145">ログインし、 [デバイス] 、  **[すべてのデバイス**  ]  **の順に選択します**。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-145">Log in and select  **Devices**  then  **All devices**.</span></span> <span data-ttu-id="6a8aa-146">ここから、デバイスの名前HoloLens検索&#39;できます。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-146">From here, you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="6a8aa-147">Intune に一覧表示されているHoloLens表示される必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-147">You should be able to see your HoloLens listed on Intune.</span></span>

        ![Intune によって管理されているのを確認Azure AD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a><span data-ttu-id="6a8aa-149">Wi-Fi証明書の検証</span><span class="sxs-lookup"><span data-stu-id="6a8aa-149">Wi-Fi certificate validation</span></span>

<span data-ttu-id="6a8aa-150">これで、デバイスは証明書を受け取Wi-Fiがあります。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-150">By now, the device should have received the Wi-Fi certificate.</span></span> <span data-ttu-id="6a8aa-151">実行できる最も簡単な検証は、証明書をWi-Fiした接続&#39;接続を試みる方法です。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-151">The simplest validation you can do is attempt to connect to the Wi-Fi connection for which you&#39;ve received the certificate.</span></span> <span data-ttu-id="6a8aa-152">アプリを開 **設定** Network **&amp; Internet** Wi-Fi に移動し  ->  **、Wi-Fi** 接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-152">Open up the **Settings** app and navigate to **Network &amp; Internet** -> **Wi-Fi** and select the Wi-fi connection.</span></span> <span data-ttu-id="6a8aa-153">接続したら、アプリで Microsoft Edge開き、Web サイトに移動できると確認します。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-153">Once connected, open up the Microsoft Edge app and confirm you can navigate to a website.</span></span>

<span data-ttu-id="6a8aa-154">デバイスで証明書を受信したと確認するには、証明書マネージャー を [使用できます](/hololens/certificate-manager)。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-154">To confirm that you have received the certificate on the device, you can use the [Certificate Manager](/hololens/certificate-manager).</span></span>

## <a name="validate-lob-app-install"></a><span data-ttu-id="6a8aa-155">LOB アプリのインストールを検証する</span><span class="sxs-lookup"><span data-stu-id="6a8aa-155">Validate LOB app install</span></span>

<span data-ttu-id="6a8aa-156">マネージド アプリのインストールの進行状況を確認するには、アプリがインストールされているのか、またはアプリのインストール設定。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-156">To see a managed app's install progress, you either see if the app is installed or check Settings.</span></span> <span data-ttu-id="6a8aa-157">LOB アプリをグループに必要なインストールとして構成することで、割り当てられたグループ内のユーザーと HoloLens を登録した後、アプリは自動的に HoloLens にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-157">By configuring a LOB app as a required installation for our group, after enrolling the HoloLens with a user in the assigned group, the app will automatically download to the HoloLens.</span></span>

<span data-ttu-id="6a8aa-158">[アプリ] をスタート メニュー[すべてのアプリ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-158">Open the Start menu and select **All apps**.</span></span> <span data-ttu-id="6a8aa-159">アプリの数によっては、ページアップボタンまたはページダウン ボタンの使用が必要 **な場合** があります。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-159">Depending on the number of apps you have, you may need to use the **page up** or **page down** buttons.</span></span>

<span data-ttu-id="6a8aa-160">デバイスへのアプリのインストールを検証するには **、設定**  ->  **Accounts**  ->  **Access** の仕事または学校を使用して行います。アカウントを選択し、[情報] ボタンを選択し、下にスクロールして MDM からデバイスに適用されているさまざまな構成とアプリを表示します。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-160">To validate the installation of the app on device, you can do so via **Settings** -> **Accounts** -> **Access work or school**; select the account then the **Info** button, and scroll down to see different configurations and apps applied to the device from MDM.</span></span>

<span data-ttu-id="6a8aa-161">Intune からインストールを検証するには [、MEM ポータル](https://endpoint.microsoft.com/#home)の [アプリ]  ->   -> [すべてのアプリ]   -> *[TheNameOfYourApp Device* install status] ページ  ->  **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-161">To validate the install from Intune, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** ->*TheNameOfYourApp* -> **Device install status** page.</span></span>

<span data-ttu-id="6a8aa-162">詳細については、以下をご覧ください[。Intune App Deployment for HoloLens](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="6a8aa-162">See more: [Intune App Deployment for HoloLens](/hololens/app-deploy-intune)</span></span>

## <a name="validate-dynamics-365-guides"></a><span data-ttu-id="6a8aa-163">検証Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="6a8aa-163">Validate Dynamics 365 Guides</span></span>

<span data-ttu-id="6a8aa-164">ガイド アプリには、アプリの作成、作成HoloLens操作に関するモードがあります。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-164">There are modes for the Guides app on HoloLens, authoring and operating.</span></span> <span data-ttu-id="6a8aa-165">ガイドを操作する前に、ガイドの作成を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-165">You'll need to finish authoring a guide before operating it.</span></span>

### <a name="authoring-the-guide"></a><span data-ttu-id="6a8aa-166">ガイドの作成</span><span class="sxs-lookup"><span data-stu-id="6a8aa-166">Authoring the Guide</span></span>

<span data-ttu-id="6a8aa-167">このクイック検証のために多くのことを行う必要はない。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-167">We don't need to do much for this quick validation.</span></span> <span data-ttu-id="6a8aa-168">PC で準備したガイドを選択します。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-168">Simply select the guide you prepared on your PC.</span></span> <span data-ttu-id="6a8aa-169">ホログラフィック アンカーを [使用して簡単](/dynamics365/mixed-reality/guides/hololens-app-anchor)に検証するには、ガイド を固定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-169">You'll need to [anchor the guide](/dynamics365/mixed-reality/guides/hololens-app-anchor), for a quick validation you can use a holographic anchor.</span></span> <span data-ttu-id="6a8aa-170">その後、手順と [モデル を配置する必要があります](/dynamics365/mixed-reality/guides/hololens-app-orientation)。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-170">Afterwards, you should [place your steps and models](/dynamics365/mixed-reality/guides/hololens-app-orientation).</span></span>

>[!NOTE]
> <span data-ttu-id="6a8aa-171">PC にログイン **し**、管理者アカウントで作成するには、オーサリング ロールがHoloLens。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-171">You will need the **Authoring** role to login to the PC and author on the HoloLens.</span></span> <span data-ttu-id="6a8aa-172">オペレーター ロールは読み取り専用であり、PC アプリにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-172">The Operator role is read-only and has no access to the PC app.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a><span data-ttu-id="6a8aa-173">ガイドの操作</span><span class="sxs-lookup"><span data-stu-id="6a8aa-173">Operating the Guide</span></span>

<span data-ttu-id="6a8aa-174">ホログラムが配置された後は、ガイドの操作をテストできます。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-174">Once your holograms are in place, you can test out operating your guide.</span></span> 
- <span data-ttu-id="6a8aa-175">演算子モード **の選択**</span><span class="sxs-lookup"><span data-stu-id="6a8aa-175">Select **Operator mode**</span></span>
- <span data-ttu-id="6a8aa-176">ガイドの手順をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-176">Click through the steps of your guide.</span></span>

<span data-ttu-id="6a8aa-177">ガイドの操作方法に関する詳細なガイダンスについては、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a8aa-177">For more in-depth guidance on how to operate a guide, check out these resources:</span></span>

[<span data-ttu-id="6a8aa-178">Dynamics 365 Guides でのガイドの操作の概要</span><span class="sxs-lookup"><span data-stu-id="6a8aa-178">Overview of operating a guide in Dynamics 365 Guides</span></span>](/dynamics365/mixed-reality/guides/operator-overview)

<span data-ttu-id="6a8aa-179">[[ステップ] カードを操作者として使用Dynamics 365 Guides](/dynamics365/mixed-reality/guides/operator-step-card-orientation)</span><span class="sxs-lookup"><span data-stu-id="6a8aa-179">[Get oriented with the Step card as an operator in Dynamics 365 Guides](/dynamics365/mixed-reality/guides/operator-step-card-orientation)</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a><span data-ttu-id="6a8aa-180">次のステップ</span><span class="sxs-lookup"><span data-stu-id="6a8aa-180">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="6a8aa-181">企業に接続されたデプロイ - 保守</span><span class="sxs-lookup"><span data-stu-id="6a8aa-181">Corporate connected deployment - Maintain</span></span>](hololens2-corp-connected-maintain.md)
