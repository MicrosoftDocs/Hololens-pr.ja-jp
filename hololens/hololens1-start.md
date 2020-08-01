---
title: HoloLens (第 1 世代) のセットアップ
description: このガイドでは、初めてセットアップする場合の手順を説明します。  Wi-Fi ネットワークと、Microsoft アカウント (MSA) または Azure Active Directory (Azure AD) アカウントが必要になります。
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 9a20a2ddd52c08a2b44dad452aac07ad9e69de85
ms.sourcegitcommit: 7edbb99e0972d3d857e5e87c062c3c64cacc1f41
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2020
ms.locfileid: "10903233"
---
# <span data-ttu-id="fe4f3-104">HoloLens (第 1 世代) のセットアップ</span><span class="sxs-lookup"><span data-stu-id="fe4f3-104">Set up your HoloLens (1st gen)</span></span>

<span data-ttu-id="fe4f3-105">初めて HoloLens の電源を入れたときは、デバイスの調整、デバイスのセットアップ、サインインの手順を案内するガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-105">The first time you turn on your HoloLens, you'll be guided through calibrating your device, setting up your device, and signing in.</span></span>  <span data-ttu-id="fe4f3-106">この記事では、HoloLens (第 1 世代) の初回起動時とセットアップ時のエクスペリエンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-106">This article walks through the HoloLens (1st gen) first start and setup experience.</span></span>

<span data-ttu-id="fe4f3-107">次のセクションでは、HoloLens とホログラムの操作方法を学びます。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="fe4f3-108">直接この記事に進むには、「[HoloLens (第 1 世代) の概要](hololens1-basic-usage.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-108">To skip ahead to that article, see [Get started with HoloLens (1st gen)](hololens1-basic-usage.md).</span></span>

## <span data-ttu-id="fe4f3-109">開始する前に</span><span class="sxs-lookup"><span data-stu-id="fe4f3-109">Before you start</span></span>

<span data-ttu-id="fe4f3-110">始める前に、以下が利用可能であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="fe4f3-111">**Wi-Fi 接続**。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-111">**A Wi-Fi connection**.</span></span> <span data-ttu-id="fe4f3-112">HoloLens をセットアップするには、Wi-Fi ネットワークに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-112">You'll need to connect your HoloLens to a Wi-Fi network to set it up.</span></span> <span data-ttu-id="fe4f3-113">初回接続時には、Web サイトへの移動や証明書を必要とせずに接続できる、オープン ネットワークまたはパスワードで保護されたネットワークが必要です。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-113">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="fe4f3-114">[HoloLens で使用する Web サイトについて詳しくは、こちらをご覧ください](hololens-offline.md)。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-114">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="fe4f3-115">**Microsoft アカウントまたは職場アカウント**。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-115">**A Microsoft account or a work account**.</span></span> <span data-ttu-id="fe4f3-116">HoloLens にサインインするには、Microsoft アカウント (または、組織がデバイスを所有している場合は職場アカウント) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-116">You'll also need to use a Microsoft account (or a work account, if your organization owns the device) to sign in to HoloLens.</span></span> <span data-ttu-id="fe4f3-117">Microsoft アカウントをお持ちでない場合は、[account.microsoft.com](https://account.microsoft.com) にアクセスして無料でセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-117">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="fe4f3-118">**つまずく危険性のない安全で明るい場所**。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-118">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="fe4f3-119">[健康と安全に関する情報をご覧ください](https://go.microsoft.com/fwlink/p/?LinkId=746661)。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-119">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="fe4f3-120">**快適さを高めるオプションのアクセサリ**。HoloLens には、より快適なフィット感を得られるように、オプションのアクセサリが付属しています。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-120">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="fe4f3-121">[快適に使うための詳しい情報をご覧ください](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-121">[More on fit and comfort](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="fe4f3-122">HoloLens を初めて使うときは、[Cortana](hololens-cortana.md) が既定でオンになり、ガイドが提供されます (ただし、デバイスのセットアップが完了するまでユーザーの質問に答えることはできません)。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-122">The first time that you use your HoloLens, [Cortana](hololens-cortana.md) is already on and ready to guide you (though she won't be able to respond to your questions until after you set up your device).</span></span> <span data-ttu-id="fe4f3-123">Cortana の使用は、Cortana の設定を使用して、いつでもオフに変更できます。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-123">You can turn Cortana off at any time in Cortana's settings.</span></span>
> - <span data-ttu-id="fe4f3-124">HoloLens の中国語版または日本語版に切り替えるには、その言語のビルドを PC にダウンロードしてから HoloLens にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-124">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to download the build for the language on a PC and then install it on your HoloLens.</span></span> <span data-ttu-id="fe4f3-125">詳細については、「[HoloLens (第 1 世代) のローカライズされたバージョンをインストールする](hololens1-install-localized.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-125">For more information, see [Install localized versions of HoloLens (1st gen)](hololens1-install-localized.md).</span></span>

## <span data-ttu-id="fe4f3-126">Hololens の起動と Windows のセットアップ</span><span class="sxs-lookup"><span data-stu-id="fe4f3-126">Start your Hololens and set up Windows</span></span>

<span data-ttu-id="fe4f3-127">初めて HoloLens を起動する場合は、最初の作業として、デバイスで Windows Holographic をセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-127">The first time you start your HoloLens, your first task is to set up Windows Holographic on your device.</span></span>

1. <span data-ttu-id="fe4f3-128">インターネットに接続します (HoloLens により、Wi-Fi ネットワークを選択できるようにガイドが表示されます)。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-128">Connect to the internet (HoloLens guides you to select Wi-Fi network).</span></span>

1. <span data-ttu-id="fe4f3-129">お使いのユーザー アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-129">Sign in to your user account.</span></span> <span data-ttu-id="fe4f3-130">**[職場または学校が所有しています]** または **[自分が所有しています]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-130">Choose between **My work or school owns it** and **I own it**.</span></span>
    - <span data-ttu-id="fe4f3-131">**[職場または学校が所有しています]** を選択し場合は、Azure AD アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-131">When you choose **My work or school owns it**, you sign in by using an Azure AD account.</span></span> <span data-ttu-id="fe4f3-132">組織で Azure AD Premium を使用しており、MDM への自動登録が構成されている場合は、HoloLens が自動的に MDM に登録されます。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-132">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="fe4f3-133">組織で Azure AD Premium が使用されていない場合は MDM への自動登録を利用できないため、[HoloLens をデバイス管理に手動で登録](hololens-enroll-mdm.md#different-ways-to-enroll)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-133">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available, so you will need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span> <span data-ttu-id="fe4f3-134">職場または学校のアカウントを使用してデバイスへの初回サインインを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-134">To sign in to your device the first time by using a work or school account, follow these steps:</span></span>
        1. <span data-ttu-id="fe4f3-135">組織アカウントの情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-135">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="fe4f3-136">プライバシー ステートメントに同意します。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-136">Accept the privacy statement.</span></span>
        1. <span data-ttu-id="fe4f3-137">Azure AD 資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-137">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="fe4f3-138">組織のサインイン ページにリダイレクトされることがあります。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-138">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="fe4f3-139">デバイスのセットアップを続行します。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-139">Continue setting up the device.</span></span>
    - <span data-ttu-id="fe4f3-140">**[自分が所有しています]** を選んだ場合は、Microsoft アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-140">When you choose **I own it**, you sign in by using a Microsoft account.</span></span> <span data-ttu-id="fe4f3-141">セットアップが完了したら、[手動で HoloLens をデバイス管理に登録](hololens-enroll-mdm.md#different-ways-to-enroll)できます。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-141">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>
        1. <span data-ttu-id="fe4f3-142">Microsoft アカウントの情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-142">Enter your Microsoft account information.</span></span>
        1. <span data-ttu-id="fe4f3-143">パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-143">Enter your password.</span></span> <span data-ttu-id="fe4f3-144">Microsoft アカウントで [2 段階認証 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/) が要求される場合、検証プロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-144">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

1. <span data-ttu-id="fe4f3-145">Wi-Fi ネットワークから取得された情報に基づいて、デバイスでタイム ゾーンが設定されます。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-145">The device sets your time zone based on information that it obtains from the Wi-Fi network.</span></span>

## <span data-ttu-id="fe4f3-146">調整</span><span class="sxs-lookup"><span data-stu-id="fe4f3-146">Calibration</span></span>

<span data-ttu-id="fe4f3-147">Cortana の紹介後、次のセットアップ手順は調整です。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-147">After Cortana introduces herself, the next setup step is calibration.</span></span> <span data-ttu-id="fe4f3-148">HoloLens のエクスペリエンスを最適化するには、セットアップ中に調整プロセスを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-148">For the best HoloLens experience, you should complete the calibration process during setup.</span></span>

<span data-ttu-id="fe4f3-149">HoloLens (第 1 世代) では、ホログラムをクリアに表示し、操作しやすくするために、瞳孔間距離 (IPD: [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance)) を使用します。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-149">HoloLens (1st gen) uses the distance between your pupils (IPD or [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance)) to make holograms clear and easy to interact with.</span></span> <span data-ttu-id="fe4f3-150">IPD が正しくない場合は、ホログラムが不安定になったり、正しくない距離感で表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-150">If the IPD is not correct, holograms may appear to be unstable or at an incorrect distance.</span></span>

<span data-ttu-id="fe4f3-151">HoloLens の調整では、片目ごとに 6 つのターゲットに指を合わせるように求められます。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-151">During calibration, HoloLens asks you to align your finger with a series of six targets per eye.</span></span> <span data-ttu-id="fe4f3-152">HoloLens はこのプロセスを使用し、ユーザーの目に合わせた適切な IPD を設定します。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-152">HoloLens uses this process to set the correct IPD for your eyes.</span></span> <span data-ttu-id="fe4f3-153">新しいユーザー用に調整を更新または調整する必要がある場合、セットアップ外で調整アプリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-153">If the calibration needs to be updated or adjusted for a new user, the new user can run the Calibration app  outside of setup.</span></span>

![IPD の指合わせ画面 (2 番目の手順)](./images/ipd-finger-alignment-300px.jpg)

*<span data-ttu-id="fe4f3-155">IPD の指合わせ画面 (2 番目の手順)</span><span class="sxs-lookup"><span data-stu-id="fe4f3-155">IPD finger-alignment screen at second step</span></span>*

<span data-ttu-id="fe4f3-156">お疲れさまでした。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-156">Congratulations!</span></span> <span data-ttu-id="fe4f3-157">セットアップは完了です。HoloLens の使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="fe4f3-157">Setup is complete and you can begin using HoloLens.</span></span>

## <span data-ttu-id="fe4f3-158">次のステップ</span><span class="sxs-lookup"><span data-stu-id="fe4f3-158">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fe4f3-159">HoloLens (第 1 世代) の概要</span><span class="sxs-lookup"><span data-stu-id="fe4f3-159">Get started with HoloLens (1st gen)</span></span>](hololens1-basic-usage.md)
