---
title: HoloLens 2 のセットアップ
description: Microsoft (MSA) または Azure Active Directory (AAD) アカウントを使用して Wi-Fi ネットワーク上で初めて HoLens 2 をセットアップする方法について説明します。
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 9/17/2019
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 9824de1d81fd6ba9ccafc8627d660aebefeaed15
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283878"
---
# <span data-ttu-id="973a7-104">HoloLens 2 のセットアップ</span><span class="sxs-lookup"><span data-stu-id="973a7-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="973a7-105">初めて HoloLens の電源を入れたときは、デバイスのセットアップ、ユーザー アカウントによるサインイン、ユーザーの目に合わせた HoloLens の調整の手順を案内するガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="973a7-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="973a7-106">このセクションでは、HoloLens 2 の初期セットアップ エクスペリエンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="973a7-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="973a7-107">次のセクションでは、HoloLens とホログラムの操作方法を学びます。</span><span class="sxs-lookup"><span data-stu-id="973a7-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="973a7-108">直接この記事に進むには、「[HoloLens 2 の概要](hololens2-basic-usage.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="973a7-108">To skip ahead to that article, see [Get started with HoloLens 2](hololens2-basic-usage.md).</span></span>

## <span data-ttu-id="973a7-109">開始する前に</span><span class="sxs-lookup"><span data-stu-id="973a7-109">Before you start</span></span>

<span data-ttu-id="973a7-110">始める前に、以下が利用可能であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="973a7-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="973a7-111">**ネットワーク接続**。</span><span class="sxs-lookup"><span data-stu-id="973a7-111">**A network connection**.</span></span> <span data-ttu-id="973a7-112">HoloLens をセットアップするには、ネットワークに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="973a7-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="973a7-113">HoloLens 2 では、Wi-Fi またはイーサネットを使用して接続できます (USB-C to Ethernet Adapter が必要です)。</span><span class="sxs-lookup"><span data-stu-id="973a7-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="973a7-114">初回接続時には、Web サイトへの移動や証明書を必要とせずに接続できる、オープン ネットワークまたはパスワードで保護されたネットワークが必要です。</span><span class="sxs-lookup"><span data-stu-id="973a7-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="973a7-115">[HoloLens で使用する Web サイトについて詳しくは、こちらをご覧ください](hololens-offline.md)。</span><span class="sxs-lookup"><span data-stu-id="973a7-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="973a7-116">**Microsoft アカウント**。</span><span class="sxs-lookup"><span data-stu-id="973a7-116">**A Microsoft account**.</span></span> <span data-ttu-id="973a7-117">HoloLens には、Microsoft アカウント (または、組織がデバイスを所有している場合は職場アカウント) を使ってサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="973a7-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="973a7-118">Microsoft アカウントをお持ちでない場合は、[account.microsoft.com](https://account.microsoft.com) にアクセスして無料でセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="973a7-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="973a7-119">**つまずく危険性のない安全で明るい場所**。</span><span class="sxs-lookup"><span data-stu-id="973a7-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="973a7-120">[健康と安全に関する情報をご覧ください](https://go.microsoft.com/fwlink/p/?LinkId=746661)。</span><span class="sxs-lookup"><span data-stu-id="973a7-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="973a7-121">**快適さを高めるオプションのアクセサリ**。HoloLens には、より快適なフィット感を得られるように、オプションのアクセサリが付属しています。</span><span class="sxs-lookup"><span data-stu-id="973a7-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="973a7-122">[快適に使うための詳しい情報をご覧ください](hololens2-setup.md#adjust-fit)。</span><span class="sxs-lookup"><span data-stu-id="973a7-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <span data-ttu-id="973a7-123">Windows のセットアップ</span><span class="sxs-lookup"><span data-stu-id="973a7-123">Set up Windows</span></span>

<span data-ttu-id="973a7-124">HoloLens 2 を初めて起動する場合、最初のタスクは Windows Holographic をセットアップすることです。</span><span class="sxs-lookup"><span data-stu-id="973a7-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="973a7-125">HoloLens を起動すると、音楽が再生され、Windows ロゴが表示されます。</span><span class="sxs-lookup"><span data-stu-id="973a7-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![初回起動時の最初の画面](images/01-magic-moment.png)

<span data-ttu-id="973a7-127">HoloLens 2 に、以下の手順が表示されます。</span><span class="sxs-lookup"><span data-stu-id="973a7-127">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="973a7-128">言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="973a7-128">Select your language.</span></span>
    ![言語の選択](images/04-language.png)

1. <span data-ttu-id="973a7-130">地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="973a7-130">Select your region.</span></span>
    ![地域の選択](images/05-region.png)

1. <span data-ttu-id="973a7-132">HoloLens を自分の目に合わせて調整します。</span><span class="sxs-lookup"><span data-stu-id="973a7-132">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="973a7-133">調整のスキップを選択すると、次回のログイン時にメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="973a7-133">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span>

    <span data-ttu-id="973a7-134">調整するには、一連のターゲット ("ジェム" と呼ばれます) を目視します。</span><span class="sxs-lookup"><span data-stu-id="973a7-134">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="973a7-135">調整中にまばたきしたり目を閉じたりしても問題はありませんが、室内や物理空間内にある他の物体を見つめないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="973a7-135">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="973a7-136">HoloLens はこのプロセスを使用して、高い精度でホログラフィックの世界をレンダリングできるように、ユーザーの眼球位置を学習します。</span><span class="sxs-lookup"><span data-stu-id="973a7-136">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> <span data-ttu-id="973a7-137">調整後は、頭部に装着したバイザーの位置がずれても、ホログラムが正しく表示されます。</span><span class="sxs-lookup"><span data-stu-id="973a7-137">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

    <span data-ttu-id="973a7-138">調整情報は、デバイスにローカル保存され、アカウント情報には関連付けられません。</span><span class="sxs-lookup"><span data-stu-id="973a7-138">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="973a7-139">詳しくは、「[調整データとセキュリティ](hololens-calibration.md#calibration-data-and-security)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="973a7-139">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

    ![調整の選択画面](images/06-et-corners.png)

1. <span data-ttu-id="973a7-141">インターネットに接続します (Wi-Fi またはイーサネット接続を選択します)。</span><span class="sxs-lookup"><span data-stu-id="973a7-141">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>
     <span data-ttu-id="973a7-142">Wi-Fi ネットワークから取得した情報に基づいて、HoloLens のタイム ゾーンが自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="973a7-142">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="973a7-143">タイムゾーンは、セットアップの完了後に設定アプリを使用して変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="973a7-143">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Wi-Fi に接続する](images/11-network.png)
> [!NOTE] 
> <span data-ttu-id="973a7-145">Wi-Fi の手順よりも先に進んでいて、後でセットアップ中に別のネットワークに切り替える必要がある場合は、**[音量を下げる]** ボタンと **[電源]** ボタンを同時に押して、この手順に戻ることができます (October 2019 以降の OS バージョンを実行している場合)。</span><span class="sxs-lookup"><span data-stu-id="973a7-145">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="973a7-146">以前のバージョンでは、自動的に接続できないようにするために、Wi-Fi ネットワークが使用できない場所で[デバイスをリセットする](hololens-recovery.md)か、または再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="973a7-146">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
> 
> <span data-ttu-id="973a7-147">また、HoloLens のセットアップ時に、2 分間の資格情報のタイムアウトがあることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="973a7-147">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="973a7-148">ユーザー名/パスワードは 2 分以内に入力する必要があります。そうしないと、ユーザー名フィールドは自動的にクリアされます。</span><span class="sxs-lookup"><span data-stu-id="973a7-148">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="973a7-149">お使いのユーザー アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="973a7-149">Sign in to your user account.</span></span> <span data-ttu-id="973a7-150">**[職場または学校が所有しています]** または **[自分が所有しています]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="973a7-150">You'll choose between **My work or school owns it** and **I own it**.</span></span>
    - <span data-ttu-id="973a7-151">**[職場または学校が所有しています]** を選んだ場合、Azure AD アカウントを使ってサインインします。</span><span class="sxs-lookup"><span data-stu-id="973a7-151">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="973a7-152">組織で Azure AD Premium を使用しており、MDM への自動登録が構成されている場合は、HoloLens が自動的に MDM に登録されます。</span><span class="sxs-lookup"><span data-stu-id="973a7-152">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="973a7-153">組織で Azure AD Premium が使用されていない場合、MDM への自動登録は使用できません。</span><span class="sxs-lookup"><span data-stu-id="973a7-153">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="973a7-154">その場合は、[HoloLens をデバイス管理に手動で登録](hololens-enroll-mdm.md#different-ways-to-enroll)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="973a7-154">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>
        1. <span data-ttu-id="973a7-155">組織アカウントの情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="973a7-155">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="973a7-156">プライバシー ステートメントとソフトウェア ライセンス条項に同意します。</span><span class="sxs-lookup"><span data-stu-id="973a7-156">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="973a7-157">Azure AD 資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="973a7-157">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="973a7-158">組織のサインイン ページにリダイレクトされることがあります。</span><span class="sxs-lookup"><span data-stu-id="973a7-158">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="973a7-159">デバイスのセットアップを続行します。</span><span class="sxs-lookup"><span data-stu-id="973a7-159">Continue setting up the device.</span></span>
    - <span data-ttu-id="973a7-160">**[自分が所有しています]** を選んだ場合、Microsoft アカウントを使ってサインインします。</span><span class="sxs-lookup"><span data-stu-id="973a7-160">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="973a7-161">セットアップが完了したら、[手動で HoloLens をデバイス管理に登録](hololens-enroll-mdm.md#different-ways-to-enroll)できます。</span><span class="sxs-lookup"><span data-stu-id="973a7-161">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>
        1. <span data-ttu-id="973a7-162">Microsoft アカウントの情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="973a7-162">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="973a7-163">パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="973a7-163">Enter your password.</span></span> <span data-ttu-id="973a7-164">Microsoft アカウントで [2 段階認証 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/) が要求される場合、検証プロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="973a7-164">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

    ![ユーザーの設定](images/13-device-owner.png)

1. <span data-ttu-id="973a7-166">HoloLens 2 で音声認識を有効にするかどうかと、診断に関する製品利用統計情報を送信するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="973a7-166">Select whether to enable speech on HoloLens 2, and whether to send diagnostic telemetry.</span></span>
    ![Cortana を有効にする](images/22-do-more-with-voice.png)

1. <span data-ttu-id="973a7-168">製品利用統計情報レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="973a7-168">Select your telemetry level.</span></span> <span data-ttu-id="973a7-169">可能であれば、"完全" 利用統計情報レベルを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="973a7-169">If you can, please enable Full telemetry.</span></span> <span data-ttu-id="973a7-170">この情報は、HoloLens エンジニアリング チームの作業に大きく役立ちます。</span><span class="sxs-lookup"><span data-stu-id="973a7-170">This information really helps the HoloLens engineering team.</span></span>
     ![製品利用統計情報のレベル](images/24-telemetry.png)

1. <span data-ttu-id="973a7-172">HoloLens 2 でスタート ジェスチャを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="973a7-172">Learn how to use the start gesture on HoloLens 2.</span></span>
     ![スタート ジェスチャの使用方法、イメージ 1](images/26-01-startmenu-learning.png) ![スタート ジェスチャの使用方法、イメージ 2](images/26-02-startmenu-learning.png)

<span data-ttu-id="973a7-174">お疲れさまでした。</span><span class="sxs-lookup"><span data-stu-id="973a7-174">Congratulations!</span></span>  <span data-ttu-id="973a7-175">セットアップは完了です。HoloLens の使用準備ができました。</span><span class="sxs-lookup"><span data-stu-id="973a7-175">Setup is complete and you're ready to use HoloLens!</span></span>

## <span data-ttu-id="973a7-176">次のステップ</span><span class="sxs-lookup"><span data-stu-id="973a7-176">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="973a7-177">HoloLens 2 の概要</span><span class="sxs-lookup"><span data-stu-id="973a7-177">Get started with HoloLens 2</span></span>](hololens2-basic-usage.md)
