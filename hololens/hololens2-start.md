---
title: HoloLens 2 のセットアップ
description: Microsoft (MSA) または Azure Active Directory (AAD) アカウントを使用して Wi-Fi ネットワーク上で初めて HoloLens 2 をセットアップする方法について説明します。
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 0d087037e94bcaed2cd79d9cff77ed3039919a09
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923784"
---
# <a name="set-up-your-hololens-2"></a><span data-ttu-id="97561-104">HoloLens 2 のセットアップ</span><span class="sxs-lookup"><span data-stu-id="97561-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="97561-105">初めて HoloLens の電源を入れたときは、デバイスのセットアップ、ユーザー アカウントによるサインイン、ユーザーの目に合わせた HoloLens の調整の手順を案内するガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97561-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="97561-106">このセクションでは、HoloLens 2 の初期セットアップ エクスペリエンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="97561-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="97561-107">次のセクションでは、HoloLens とホログラムの操作方法を学びます。</span><span class="sxs-lookup"><span data-stu-id="97561-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="97561-108">この記事に進むには、[「HoloLens 2 について」](hololens2-basic-usage.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97561-108">To skip ahead to that article, see [Getting around HoloLens 2](hololens2-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="97561-109">開始する前に</span><span class="sxs-lookup"><span data-stu-id="97561-109">Before you start</span></span>

<span data-ttu-id="97561-110">始める前に、以下が利用可能であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="97561-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="97561-111">**ネットワーク接続**。</span><span class="sxs-lookup"><span data-stu-id="97561-111">**A network connection**.</span></span> <span data-ttu-id="97561-112">HoloLens をセットアップするには、ネットワークに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97561-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="97561-113">HoloLens 2 では、Wi-Fi またはイーサネットを使用して接続できます (USB-C to Ethernet Adapter が必要です)。</span><span class="sxs-lookup"><span data-stu-id="97561-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="97561-114">初回接続時には、Web サイトへの移動や証明書を必要とせずに接続できる、オープン ネットワークまたはパスワードで保護されたネットワークが必要です。</span><span class="sxs-lookup"><span data-stu-id="97561-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="97561-115">[HoloLens を使用する Web サイトの詳細について説明します](hololens-offline.md)。</span><span class="sxs-lookup"><span data-stu-id="97561-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="97561-116">**Microsoft アカウント**。</span><span class="sxs-lookup"><span data-stu-id="97561-116">**A Microsoft account**.</span></span> <span data-ttu-id="97561-117">HoloLens には、Microsoft アカウント (または、組織がデバイスを所有している場合は職場アカウント) を使ってサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="97561-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="97561-118">Microsoft アカウントをお持ち出ない場合は、[account.microsoft.com](https://account.microsoft.com) に進んで作成してください。無料です。</span><span class="sxs-lookup"><span data-stu-id="97561-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="97561-119">**トリップの危険性がない、安全で明るく照らされた空間**。</span><span class="sxs-lookup"><span data-stu-id="97561-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="97561-120">[正常性と安全性に関する情報](https://go.microsoft.com/fwlink/p/?LinkId=746661)。</span><span class="sxs-lookup"><span data-stu-id="97561-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="97561-121">HoloLens に付属する **最適なフィット感のアクセサリ** で、快適なフィット感が得られます。</span><span class="sxs-lookup"><span data-stu-id="97561-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="97561-122">[フィット感と快適性の詳細について](hololens2-setup.md#adjust-fit)。</span><span class="sxs-lookup"><span data-stu-id="97561-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <a name="set-up-windows"></a><span data-ttu-id="97561-123">Windows の設定</span><span class="sxs-lookup"><span data-stu-id="97561-123">Set up Windows</span></span>

<span data-ttu-id="97561-124">HoloLens 2 を初めて起動する場合、最初のタスクは Windows Holographic をセットアップすることです。</span><span class="sxs-lookup"><span data-stu-id="97561-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="97561-125">HoloLens を起動すると、音楽が再生され、Windows ロゴが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97561-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![初回起動時の最初の画面](images/01-magic-moment.png)

<span data-ttu-id="97561-127">HoloLens 2 に、以下の手順が表示されます。</span><span class="sxs-lookup"><span data-stu-id="97561-127">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="97561-128">言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="97561-128">Select your language.</span></span>

    ![言語を選択](images/04-language.png)

1. <span data-ttu-id="97561-130">自分のリージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="97561-130">Select your region.</span></span>

    ![地域を選択](images/05-region.png)

1. <span data-ttu-id="97561-132">HoloLens を自分の目に合わせて調整します。</span><span class="sxs-lookup"><span data-stu-id="97561-132">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="97561-133">調整のスキップを選択すると、次回のログイン時にメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97561-133">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span> 

    1. <span data-ttu-id="97561-134">まず、バイザーを調整します。</span><span class="sxs-lookup"><span data-stu-id="97561-134">First, you'll adjust your visor.</span></span>
    
        ![調整の選択画面](images/06-et-corners.png)

    2. <span data-ttu-id="97561-136">調整するには、一連のターゲット (「宝石」 と呼ばれます) を目視します。</span><span class="sxs-lookup"><span data-stu-id="97561-136">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="97561-137">調整中にまばたきしたり目を閉じたりしても問題はありませんが、室内や物理空間内にある他の物体を見つめないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="97561-137">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="97561-138">HoloLens はこのプロセスを使用して、高い精度でホログラフィックの世界をレンダリングできるように、ユーザーの眼球位置を学習します。</span><span class="sxs-lookup"><span data-stu-id="97561-138">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> 

        ![目に合わせて調整する](images/07-adjust-eyes.png)

        <span data-ttu-id="97561-140">調整後は、頭部に装着したバイザーの位置がずれても、ホログラムが正しく表示されます。</span><span class="sxs-lookup"><span data-stu-id="97561-140">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span> <span data-ttu-id="97561-141">調整情報は、デバイスにローカル保存され、アカウント情報には関連付けられません。</span><span class="sxs-lookup"><span data-stu-id="97561-141">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="97561-142">詳細については、[「調整データと セキュリティ」](hololens-calibration.md#calibration-data-and-security)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97561-142">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

        ![調整が完了しました](images/calibration-complete.png)

1. <span data-ttu-id="97561-144">インターネットに接続します (Wi-Fi またはイーサネット接続を選択します)。</span><span class="sxs-lookup"><span data-stu-id="97561-144">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>

     <span data-ttu-id="97561-145">Wi-Fi ネットワークから取得した情報に基づいて、HoloLens のタイム ゾーンが自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="97561-145">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="97561-146">タイムゾーンは、セットアップの完了後に設定アプリを使用して変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="97561-146">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Wi-Fi に接続する](images/11-network.png)

    > [!NOTE] 
    > <span data-ttu-id="97561-148">Wi-Fi の手順よりも先に進んでいて、後でセットアップ中に別のネットワークに切り替える必要がある場合は、 **[ボリューム ダウン]** ボタンと **[電源]** ボタンを同時に押して、この手順に戻ることができます (October 2019 以降の OS バージョンを実行している場合)。</span><span class="sxs-lookup"><span data-stu-id="97561-148">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="97561-149">以前のバージョンでは、自動的に接続できないようにするために、Wi-Fi ネットワークが使用できない場所で[デバイスをリセットする](hololens-recovery.md)か、または再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97561-149">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
    > 
    > <span data-ttu-id="97561-150">また、HoloLens のセットアップ時に、2 分間の資格情報のタイムアウトがあることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="97561-150">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="97561-151">ユーザー名/パスワードは 2 分以内に入力する必要があります。そうしないと、ユーザー名フィールドは自動的にクリアされます。</span><span class="sxs-lookup"><span data-stu-id="97561-151">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="97561-152">HoloLens 2 Autopilot プロファイルが存在する場合は、そのプロファイルを検索して適用します。</span><span class="sxs-lookup"><span data-stu-id="97561-152">HoloLens 2 will search and apply an Autopilot profile if one exists.</span></span> <span data-ttu-id="97561-153">この画面では、操作は必要はありません。</span><span class="sxs-lookup"><span data-stu-id="97561-153">No action is needed on this screen.</span></span>
 
    ![Autopilot プロファイルの検索](images/autopilot-profile-search.png) 

1. <span data-ttu-id="97561-155">ライセンス 画面で **[同意する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97561-155">Click **Accept** on the licensing screen.</span></span>

    ![Windows ライセンス契約](images/windows-license-agreement.png)

1. <span data-ttu-id="97561-157">お使いのユーザー アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="97561-157">Sign in to your user account.</span></span> <span data-ttu-id="97561-158">**自分の職場または学校 が所有し**、 **自分が所有している** から 選択します。</span><span class="sxs-lookup"><span data-stu-id="97561-158">You'll choose between **My work or school owns it** and **I own it**.</span></span>

    - <span data-ttu-id="97561-159">**[職場または学校が所有しています]** を選んだ場合、Azure AD アカウントを使ってサインインします。</span><span class="sxs-lookup"><span data-stu-id="97561-159">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="97561-160">組織で Azure AD Premium を使用しており、MDM への自動登録が構成されている場合は、HoloLens が自動的に MDM に登録されます。</span><span class="sxs-lookup"><span data-stu-id="97561-160">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="97561-161">組織で Azure AD Premium が使用されていない場合、MDM への自動登録は使用できません。</span><span class="sxs-lookup"><span data-stu-id="97561-161">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="97561-162">その場合は、[デバイス管理で手動で HoloLens を登録する必要があります](hololens-enroll-mdm.md#different-ways-to-enroll)。</span><span class="sxs-lookup"><span data-stu-id="97561-162">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="97561-163">組織アカウントの情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="97561-163">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="97561-164">プライバシー ステートメントとエンドユーザーのライセンス条項に同意します。</span><span class="sxs-lookup"><span data-stu-id="97561-164">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="97561-165">Azure AD 資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="97561-165">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="97561-166">組織のサインイン ページにリダイレクトされることがあります。</span><span class="sxs-lookup"><span data-stu-id="97561-166">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="97561-167">デバイスのセットアップを続行します。</span><span class="sxs-lookup"><span data-stu-id="97561-167">Continue setting up the device.</span></span>

    - <span data-ttu-id="97561-168">**[自分が所有しています]** を選んだ場合、Microsoft アカウントを使ってサインインします。</span><span class="sxs-lookup"><span data-stu-id="97561-168">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="97561-169">セットアップが完了したら、[HoloLens をデバイス管理に手動で登録](hololens-enroll-mdm.md#different-ways-to-enroll)できます。</span><span class="sxs-lookup"><span data-stu-id="97561-169">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="97561-170">Microsoft アカウントの情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="97561-170">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="97561-171">パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="97561-171">Enter your password.</span></span> <span data-ttu-id="97561-172">Microsoft アカウントで [2 段階認証 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/) が要求される場合、検証プロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="97561-172">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

    ![ユーザーの設定](images/13-device-owner.png)

1. <span data-ttu-id="97561-174">**[次へ**] を選択して虹彩認証サインインを設定します。</span><span class="sxs-lookup"><span data-stu-id="97561-174">Setup Iris sign-in by selecting **Next**.</span></span> <span data-ttu-id="97561-175">目の調整と同様のエクスペリエンスを体験します。</span><span class="sxs-lookup"><span data-stu-id="97561-175">You will go through a similar experience to the eye calibration.</span></span> <span data-ttu-id="97561-176">スキャンが完了したら 、 **[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="97561-176">Select **Done** when the scan is complete.</span></span> <span data-ttu-id="97561-177">**[スキップ]** を選択 して、この手順をバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="97561-177">You may also select **Skip** to bypass this step.</span></span>
    
    <span data-ttu-id="97561-178">![虹彩認証](images/setup-iris.png) ![虹彩認証のセットアップが完了](images/iris-setup-complete.png)</span><span class="sxs-lookup"><span data-stu-id="97561-178">![Iris setup](images/setup-iris.png) ![Iris setup completion](images/iris-setup-complete.png)</span></span> 
     
  
1. <span data-ttu-id="97561-179">デバイスにログインする PIN を設定します。</span><span class="sxs-lookup"><span data-stu-id="97561-179">You'll setup a PIN to log into the device.</span></span> <span data-ttu-id="97561-180">この PIN はデバイス固有です。</span><span class="sxs-lookup"><span data-stu-id="97561-180">This PIN is device specific.</span></span> 

    ![Windows Hello の設定](images/setup-windows-hello.png)

    ![Windows Hello PIN の設定](images/windows-hello-pin.png)

    ![Windows Hello セットアップが成功しました](images/windows-hello-successful.png) 
    
1. <span data-ttu-id="97561-184">HoloLens 2 で音声を有効にするかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="97561-184">Select whether to enable speech on HoloLens 2.</span></span>

    ![Cortana を有効にする](images/22-do-more-with-voice.png)

1. <span data-ttu-id="97561-186">HoloLens 2 で位置を有効にするかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="97561-186">Select whether to enable location on HoloLens 2.</span></span>
    
    ![位置サービスを有効にする](images/setup-location-services.png)

1. <span data-ttu-id="97561-188">テレメトリ レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="97561-188">Select your telemetry level.</span></span> <span data-ttu-id="97561-189">可能な場合は、オプションのテレメトリを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="97561-189">If you can, please enable Optional telemetry.</span></span> <span data-ttu-id="97561-190">この情報は、HoloLens エンジニアリング チームの作業に大きく役立ちます。</span><span class="sxs-lookup"><span data-stu-id="97561-190">This information really helps the HoloLens engineering team.</span></span>

     ![テレメトリのレベル](images/24-telemetry.png)

1. <span data-ttu-id="97561-192">HoloLens 2 でスタート ジェスチャを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="97561-192">Learn how to use the start gesture on HoloLens 2.</span></span>

     ![スタート ジェスチャを使用する方法について説明します (画像 1)](images/26-01-startmenu-learning.png)

     ![スタート ジェスチャを使用する方法について説明します (画像 2)](images/26-02-startmenu-learning.png)

<span data-ttu-id="97561-195">おめでとうございます。</span><span class="sxs-lookup"><span data-stu-id="97561-195">Congratulations!</span></span>  <span data-ttu-id="97561-196">セットアップは完了です。HoloLens の使用準備ができました。</span><span class="sxs-lookup"><span data-stu-id="97561-196">Setup is complete and you're ready to use HoloLens!</span></span>

## <a name="next-steps"></a><span data-ttu-id="97561-197">次のステップ</span><span class="sxs-lookup"><span data-stu-id="97561-197">Next steps</span></span>

1. <span data-ttu-id="97561-198">すぐに Mixed Reality の操作を開始し、HoloLens で Windows 10 をナビゲートします。手の操作に関する実践的なチュートリアルについては、**ヒント** アプリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="97561-198">Start interacting right away with Mixed Reality and navigating Windows 10 on your HoloLens - check out the **Tips** app for hands-on tutorials for hand interactions.</span></span> <span data-ttu-id="97561-199">スタート ジェスチャを使用して [スタート] に移動するか、「スタートに移動」と言って [ヒント] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97561-199">Use the start gesture to go to Start or say "Go to Start" and select Tips.</span></span>

1. <span data-ttu-id="97561-200">HoloLens 2 の操作方法について読み続けるには、以下をクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="97561-200">Click below to continue reading about getting around HoloLens 2.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="97561-201">HoloLens 2 の基本操作</span><span class="sxs-lookup"><span data-stu-id="97561-201">Getting around HoloLens 2</span></span>](hololens2-basic-usage.md)
