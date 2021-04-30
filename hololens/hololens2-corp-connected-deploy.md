---
title: 展開ガイド– Dynamics 365 ガイドを使用した企業接続 HoloLens 2 ガイド-デプロイ
description: Dynamics 365 ガイドを使用して、企業に接続されたネットワーク経由で HoloLens 2 デバイスの展開を設定する方法について説明します。
keywords: HoloLens, 管理, 企業接続, Dynamics 365 ガイド, AAD, Azure AD, MDM, モバイルデバイス管理
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309340"
---
# <a name="deploy---corporate-connected-guide"></a><span data-ttu-id="94ec4-104">デプロイ-企業接続ガイド</span><span class="sxs-lookup"><span data-stu-id="94ec4-104">Deploy - Corporate Connected Guide</span></span>

<span data-ttu-id="94ec4-105">各デプロイの重要な部分は、エンドユーザーに対して円滑なエクスペリエンスを確保するために、自分でテストする前に、デプロイが適切に設定されていることを確認することです。</span><span class="sxs-lookup"><span data-stu-id="94ec4-105">An important part of each deployment is ensuring that your deployment is properly set up before testing it yourself to ensure a smooth experience for the end user.</span></span>

<span data-ttu-id="94ec4-106">MDM を使用して Wi-Fi 証明書を展開しているため、最初に HoloLens をセットアップし、Wi-Fi 開いているネットワークまたは証明書を必要としないネットワークにデバイスを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94ec4-106">Because we are deploying the Wi-Fi certificate via MDM, we'll need to initially set up HoloLens and enroll devices on an open Wi-Fi network, or a network that doesn't require the certificate.</span></span> <span data-ttu-id="94ec4-107">HoloLens が OOBE を完了し、登録されると、デバイスはネットワーク証明書と LOB を事前に構成し、デバイスが受信したことを確認できるようになります。</span><span class="sxs-lookup"><span data-stu-id="94ec4-107">Once the HoloLens has finished OOBE and Enrolled, the device will receive the network certificate and LOB configured previously and we'll be able to validate both were received by the device.</span></span>

<span data-ttu-id="94ec4-108">その後、テストガイドの作成と操作の両方ができることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="94ec4-108">Afterwards, you'll be able confirm you can both author and operate a test Guide.</span></span>

## <a name="enrollment-validation"></a><span data-ttu-id="94ec4-109">登録の検証</span><span class="sxs-lookup"><span data-stu-id="94ec4-109">Enrollment Validation</span></span>

<span data-ttu-id="94ec4-110">これで、Azure AD と MDM 登録のすべてが正しく構成されたので、残りはスナップになります。</span><span class="sxs-lookup"><span data-stu-id="94ec4-110">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="94ec4-111">Wi-Fi 接続と HoloLens デバイス、および以前に構成した Azure AD ユーザーアカウントのいずれかが必要です。</span><span class="sxs-lookup"><span data-stu-id="94ec4-111">You'll need a Wi-Fi connection and the HoloLens device, and one of the previously configured Azure AD user accounts.</span></span>

<span data-ttu-id="94ec4-112">現在デバイスが工場出荷時の設定状態になっていない場合は、ここで [デバイスを更新](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="94ec4-112">If your device isn't currently sitting in a factory settings state, now would be a good time to [reflash the device](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="94ec4-113">デバイスが OOBE になったら、操作を開始し、プロンプトに従って操作を開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94ec4-113">Once your device is in OOBE, you'll need to start interacting and following the prompts.</span></span>

2. <span data-ttu-id="94ec4-114">Wi-fi に参加するために証明書を必要としない、開いている Wi-Fi ネットワークに接続します。</span><span class="sxs-lookup"><span data-stu-id="94ec4-114">Connect to an open Wi-Fi network that does not require certificates to join the Wi-Fi.</span></span> <span data-ttu-id="94ec4-115">これにより、初期セットアップ後に、デバイスが組織の Wi-Fi で使用する証明書をダウンロードできるようになります。</span><span class="sxs-lookup"><span data-stu-id="94ec4-115">This will allow the device to download the certificate to be used on the organization's Wi-Fi after initial setup.</span></span>

3. <span data-ttu-id="94ec4-116">**この HoloLens を所有** していることを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="94ec4-116">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="94ec4-117">[ **職場または学校が所有** する] を選択し、Azure AD アカウントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="94ec4-117">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>

4. <span data-ttu-id="94ec4-118">登録が成功すると、PIN の設定を求められます。</span><span class="sxs-lookup"><span data-stu-id="94ec4-118">When enrollment is successful, you'll be prompted to set up a PIN.</span></span> <span data-ttu-id="94ec4-119">この PIN は、このユーザーに対してこのデバイスに固有のものです。</span><span class="sxs-lookup"><span data-stu-id="94ec4-119">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="94ec4-120">また、虹彩スキャン、音声データ、テレメトリの設定を求められます。最後に、[スタート] メニューを開き、OOBE を完了する方法を学習できます。</span><span class="sxs-lookup"><span data-stu-id="94ec4-120">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you'll be able to learn how to open the start menu and complete OOBE.</span></span>

5. <span data-ttu-id="94ec4-121">Mixed Reality ホームに移動したら、直前に学習した **開始ジェスチャ** を使用して [スタート] メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="94ec4-121">Once you land in the Mixed Reality Home, open the Start menu using the **Start gesture** you just learned.</span></span>

6. <span data-ttu-id="94ec4-122">[ **設定** ] アプリを選択し、[ **システム**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="94ec4-122">Select the **Settings** app and select **System**.</span></span> <span data-ttu-id="94ec4-123">最初に表示される情報は、デバイス名です。 HoloLens 2 デバイスの場合、 &quot; hololens と &quot; 6 文字の文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="94ec4-123">The first piece of information you'll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>

7. <span data-ttu-id="94ec4-124">この名前をメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="94ec4-124">Take note of this name.</span></span>

    ![HoloLens 2 の設定画面](./images/hololens2-settings-about.jpg)

8. <span data-ttu-id="94ec4-126">デバイスが Azure AD に正常に参加していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="94ec4-126">Verify that your device is successfully joined to Azure AD.</span></span> <span data-ttu-id="94ec4-127">2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="94ec4-127">There are two ways;</span></span>

    1.  <span data-ttu-id="94ec4-128">設定アプリ。</span><span class="sxs-lookup"><span data-stu-id="94ec4-128">The Settings app.</span></span> <span data-ttu-id="94ec4-129">[**設定**] で、[**アカウント**] [  ->  **職場または学校にアクセス** する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="94ec4-129">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="94ec4-130">この画面では、 &quot; nameofAAD&#39;s Azure AD に接続されていることを確認して、正常に登録されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="94ec4-130">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="94ec4-131">接続 *yourusername@nameofAAD.onmicrosoft.com* します。</span><span class="sxs-lookup"><span data-stu-id="94ec4-131">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="94ec4-132">これにより、デバイスが組織&#39;s Azure AD に参加していることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="94ec4-132">This will verify your device is joined to your organization&#39;s Azure AD.</span></span>

    1. <span data-ttu-id="94ec4-133">[Azure ポータル](https://portal.azure.com/#home)。</span><span class="sxs-lookup"><span data-stu-id="94ec4-133">The [Azure portal](https://portal.azure.com/#home).</span></span> <span data-ttu-id="94ec4-134">[ **Azure Active Directory**  ->  **デバイス**  ->  ] [**すべてのデバイス**] にアクセスし、デバイス名を検索します。</span><span class="sxs-lookup"><span data-stu-id="94ec4-134">Go to **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="94ec4-135">[結合の種類] では、"Azure AD" 結合 "として表示されます。</span><span class="sxs-lookup"><span data-stu-id="94ec4-135">Under Join Type, it will show as being 'Azure AD Joined'.</span></span>
        <span data-ttu-id="94ec4-136">![Azure AD での結合の種類の確認](./images/hololens2-devices-all-devices.png)</span><span class="sxs-lookup"><span data-stu-id="94ec4-136">![Verify Join Type in Azure AD](./images/hololens2-devices-all-devices.png)</span></span>

9. <span data-ttu-id="94ec4-137">デバイスが MDM に登録されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="94ec4-137">Verify that your device is enrolled with MDM.</span></span> <span data-ttu-id="94ec4-138">2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="94ec4-138">There are two ways;</span></span>

    1. <span data-ttu-id="94ec4-139">[**設定**] で、[**アカウント**] [  ->  **職場または学校にアクセス** する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="94ec4-139">From **Settings**, select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="94ec4-140">この画面では、 &quot; nameofAAD&#39;s Azure AD に接続されていることを確認して、正常に登録されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="94ec4-140">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="94ec4-141">接続 *yourusername@nameofAAD.onmicrosoft.com* します。</span><span class="sxs-lookup"><span data-stu-id="94ec4-141">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="94ec4-142">この職場または学校アカウントから、[ &quot; nameofAAD&#39;s に接続] を選択して Azure AD します。</span><span class="sxs-lookup"><span data-stu-id="94ec4-142">From this Access work or school account by selecting &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="94ec4-143">によって接続され yourusername@nameofAAD.onmicrosoft.com &quot; 、[**情報**] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="94ec4-143">Connected by yourusername@nameofAAD.onmicrosoft.com&quot; and select the **Info** button.</span></span>

    1. <span data-ttu-id="94ec4-144">[Microsoft Endpoint Manager 管理センター](https://endpoint.microsoft.com/#home)。</span><span class="sxs-lookup"><span data-stu-id="94ec4-144">[Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="94ec4-145">ログインし、[  **デバイス**  ]、[  **すべてのデバイス**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="94ec4-145">Log in and select  **Devices**  then  **All devices**.</span></span> <span data-ttu-id="94ec4-146">ここから、HoloLens デバイス&#39;s 名を検索できます。</span><span class="sxs-lookup"><span data-stu-id="94ec4-146">From here, you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="94ec4-147">HoloLens が Intune に表示されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="94ec4-147">You should be able to see your HoloLens listed on Intune.</span></span>

        ![Azure AD で Intune によって管理されていることを確認する](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a><span data-ttu-id="94ec4-149">証明書の検証の Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="94ec4-149">Wi-Fi certificate validation</span></span>

<span data-ttu-id="94ec4-150">これで、デバイスは Wi-Fi 証明書を受信しました。</span><span class="sxs-lookup"><span data-stu-id="94ec4-150">By now, the device should have received the Wi-Fi certificate.</span></span> <span data-ttu-id="94ec4-151">最も簡単な検証は、証明書を受信した Wi-Fi&#39;接続への接続を試みることです。</span><span class="sxs-lookup"><span data-stu-id="94ec4-151">The simplest validation you can do is attempt to connect to the Wi-Fi connection for which you&#39;ve received the certificate.</span></span> <span data-ttu-id="94ec4-152">**設定** アプリを開き、[ネットワーク] **[ &amp; インターネット**] [wi-fi] の順に移動して  ->   、[wi-fi 接続] を選択します。</span><span class="sxs-lookup"><span data-stu-id="94ec4-152">Open up the **Settings** app and navigate to **Network &amp; Internet** -> **Wi-Fi** and select the Wi-fi connection.</span></span> <span data-ttu-id="94ec4-153">接続したら、Microsoft Edge アプリを開き、web サイトに移動できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="94ec4-153">Once connected, open up the Microsoft Edge app and confirm you can navigate to a website.</span></span>

<span data-ttu-id="94ec4-154">デバイスで証明書を受信したことを確認するには、 [証明書マネージャー](https://docs.microsoft.com/hololens/certificate-manager)を使用します。</span><span class="sxs-lookup"><span data-stu-id="94ec4-154">To confirm that you have received the certificate on the device, you can use the [Certificate Manager](https://docs.microsoft.com/hololens/certificate-manager).</span></span>

## <a name="validate-lob-app-install"></a><span data-ttu-id="94ec4-155">LOB アプリのインストールの検証</span><span class="sxs-lookup"><span data-stu-id="94ec4-155">Validate LOB app install</span></span>

<span data-ttu-id="94ec4-156">管理対象アプリのインストールの進行状況を表示するには、アプリがインストールされているかどうか、または設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="94ec4-156">To see a managed app's install progress, you either see if the app is installed or check Settings.</span></span> <span data-ttu-id="94ec4-157">LOB アプリをグループの必須のインストールとして構成することで、HoloLens を割り当てられたグループのユーザーに登録した後、アプリが HoloLens に自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="94ec4-157">By configuring a LOB app as a required installation for our group, after enrolling the HoloLens with a user in the assigned group, the app will automatically download to the HoloLens.</span></span>

<span data-ttu-id="94ec4-158">[スタート] メニューを開き、[ **すべてのアプリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="94ec4-158">Open the Start menu and select **All apps**.</span></span> <span data-ttu-id="94ec4-159">使用しているアプリの数によっては、[pageup **]** ボタンまたは [ **pagedown] ボタン** の使用が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="94ec4-159">Depending on the number of apps you have, you may need to use the **page up** or **page down** buttons.</span></span>

<span data-ttu-id="94ec4-160">デバイスでのアプリのインストールを検証するには、**設定**  ->  **アカウント** から  ->  **職場または学校にアクセス** し、[**情報**] ボタンを選択してから下へスクロールして、MDM からデバイスに適用されているさまざまな構成とアプリを表示します。</span><span class="sxs-lookup"><span data-stu-id="94ec4-160">To validate the installation of the app on device, you can do so via **Settings** -> **Accounts** -> **Access work or school**; select the account then the **Info** button, and scroll down to see different configurations and apps applied to the device from MDM.</span></span>

<span data-ttu-id="94ec4-161">Intune からインストールを検証するには、[[メモリポータル](https://endpoint.microsoft.com/#home)  ->  **アプリ**-> すべての **アプリ**]  -> *TheNameOfYourApp*[  ->  **デバイスのインストール状態**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="94ec4-161">To validate the install from Intune, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** ->*TheNameOfYourApp* -> **Device install status** page.</span></span>

<span data-ttu-id="94ec4-162">詳細については[、「HoloLens の Intune アプリの展開」を](https://docs.microsoft.com/hololens/app-deploy-intune)参照してください。</span><span class="sxs-lookup"><span data-stu-id="94ec4-162">See more: [Intune App Deployment for HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)</span></span>

## <a name="validate-dynamics-365-guides"></a><span data-ttu-id="94ec4-163">Dynamics 365 ガイドの検証</span><span class="sxs-lookup"><span data-stu-id="94ec4-163">Validate Dynamics 365 Guides</span></span>

<span data-ttu-id="94ec4-164">HoloLens、オーサリング、および運用上のガイドアプリのモードが用意されています。</span><span class="sxs-lookup"><span data-stu-id="94ec4-164">There are modes for the Guides app on HoloLens, authoring and operating.</span></span> <span data-ttu-id="94ec4-165">運用する前に、ガイドの作成を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94ec4-165">You'll need to finish authoring a guide before operating it.</span></span>

### <a name="authoring-the-guide"></a><span data-ttu-id="94ec4-166">ガイドを作成する</span><span class="sxs-lookup"><span data-stu-id="94ec4-166">Authoring the Guide</span></span>

<span data-ttu-id="94ec4-167">このクイック検証については、あまり必要ありません。</span><span class="sxs-lookup"><span data-stu-id="94ec4-167">We don't need to do much for this quick validation.</span></span> <span data-ttu-id="94ec4-168">PC で準備した番組ガイドを選択するだけです。</span><span class="sxs-lookup"><span data-stu-id="94ec4-168">Simply select the guide you prepared on your PC.</span></span> <span data-ttu-id="94ec4-169">[ガイドを固定](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor)する必要があります。簡単な検証を行うには、holographic アンカーを使用します。</span><span class="sxs-lookup"><span data-stu-id="94ec4-169">You'll need to [anchor the guide](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor), for a quick validation you can use a holographic anchor.</span></span> <span data-ttu-id="94ec4-170">その後、 [ステップとモデルを配置](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94ec4-170">Afterwards, you should [place your steps and models](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation).</span></span>

>[!NOTE]
> <span data-ttu-id="94ec4-171">PC にログインし、HoloLens で作成するには、 **オーサリング** ロールが必要です。</span><span class="sxs-lookup"><span data-stu-id="94ec4-171">You will need the **Authoring** role to login to the PC and author on the HoloLens.</span></span> <span data-ttu-id="94ec4-172">オペレーターロールは読み取り専用で、PC アプリへのアクセス権はありません。</span><span class="sxs-lookup"><span data-stu-id="94ec4-172">The Operator role is read-only and has no access to the PC app.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a><span data-ttu-id="94ec4-173">ガイドを操作する</span><span class="sxs-lookup"><span data-stu-id="94ec4-173">Operating the Guide</span></span>

<span data-ttu-id="94ec4-174">ホログラムが配置されたら、ガイドの操作をテストできます。</span><span class="sxs-lookup"><span data-stu-id="94ec4-174">Once your holograms are in place, you can test out operating your guide.</span></span> 
- <span data-ttu-id="94ec4-175">**オペレーターモード** の選択</span><span class="sxs-lookup"><span data-stu-id="94ec4-175">Select **Operator mode**</span></span>
- <span data-ttu-id="94ec4-176">ガイドの手順をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94ec4-176">Click through the steps of your guide.</span></span>

<span data-ttu-id="94ec4-177">ガイドを操作する方法の詳細なガイダンスについては、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="94ec4-177">For more in-depth guidance on how to operate a guide, check out these resources:</span></span>

[<span data-ttu-id="94ec4-178">Dynamics 365 ガイドの操作ガイドの概要</span><span class="sxs-lookup"><span data-stu-id="94ec4-178">Overview of operating a guide in Dynamics 365 Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-overview)

[<span data-ttu-id="94ec4-179">Dynamics 365 ガイドで、ステップカードを演算子として使用する</span><span class="sxs-lookup"><span data-stu-id="94ec4-179">Get oriented with the Step card as an operator in Dynamics 365 Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a><span data-ttu-id="94ec4-180">次のステップ</span><span class="sxs-lookup"><span data-stu-id="94ec4-180">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="94ec4-181">企業に接続された展開-管理</span><span class="sxs-lookup"><span data-stu-id="94ec4-181">Corporate connected deployment - Maintain</span></span>](hololens2-corp-connected-maintain.md)
