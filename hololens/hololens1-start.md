---
title: HoloLens (第 1 世代) のセットアップ
description: Microsoft (MSA) アカウントまたは Azure Active Directory (AAD) アカウントを使用して、Wi-Fi ネットワーク上で初めて HoloLens (第 1 世代) をセットアップする方法について説明します。
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f0ec62e55f15fda6d5a8304ea2bb77039d644b9e
ms.sourcegitcommit: 01c0b0a789e156a9d29aaf6f61e36dfd09b8c01a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439063"
---
# <a name="set-up-your-hololens-1st-gen"></a><span data-ttu-id="bd70a-103">HoloLens (第 1 世代) のセットアップ</span><span class="sxs-lookup"><span data-stu-id="bd70a-103">Set up your HoloLens (1st gen)</span></span>

<span data-ttu-id="bd70a-104">初めて HoloLens の電源を入れたときは、デバイスの調整、デバイスのセットアップ、サインインの手順を案内するガイドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd70a-104">The first time you turn on your HoloLens, you'll be guided through calibrating your device, setting up your device, and signing in.</span></span>  <span data-ttu-id="bd70a-105">この記事では、HoloLens (第 1 世代) の初回起動時とセットアップ時のエクスペリエンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bd70a-105">This article walks through the HoloLens (1st gen) first start and setup experience.</span></span>

<span data-ttu-id="bd70a-106">次のセクションでは、HoloLens とホログラムの操作方法を学びます。</span><span class="sxs-lookup"><span data-stu-id="bd70a-106">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="bd70a-107">直接この記事に進むには、「[HoloLens (第 1 世代) の概要](hololens1-basic-usage.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bd70a-107">To skip ahead to that article, see [Get started with HoloLens (1st gen)](hololens1-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="bd70a-108">開始する前に</span><span class="sxs-lookup"><span data-stu-id="bd70a-108">Before you start</span></span>

<span data-ttu-id="bd70a-109">始める前に、以下が利用可能であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bd70a-109">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="bd70a-110">**Wi-Fi 接続**。</span><span class="sxs-lookup"><span data-stu-id="bd70a-110">**A Wi-Fi connection**.</span></span> <span data-ttu-id="bd70a-111">HoloLens をセットアップするには、Wi-Fi ネットワークに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd70a-111">You'll need to connect your HoloLens to a Wi-Fi network to set it up.</span></span> <span data-ttu-id="bd70a-112">初回接続時には、Web サイトへの移動や証明書を必要とせずに接続できる、オープン ネットワークまたはパスワードで保護されたネットワークが必要です。</span><span class="sxs-lookup"><span data-stu-id="bd70a-112">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="bd70a-113">[HoloLens で使用する Web サイトについて詳しくは、こちらをご覧ください](hololens-offline.md)。</span><span class="sxs-lookup"><span data-stu-id="bd70a-113">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="bd70a-114">**Microsoft アカウントまたは職場アカウント**。</span><span class="sxs-lookup"><span data-stu-id="bd70a-114">**A Microsoft account or a work account**.</span></span> <span data-ttu-id="bd70a-115">HoloLens にサインインするには、Microsoft アカウント (または、組織がデバイスを所有している場合は職場アカウント) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd70a-115">You'll also need to use a Microsoft account (or a work account, if your organization owns the device) to sign in to HoloLens.</span></span> <span data-ttu-id="bd70a-116">Microsoft アカウントをお持ちでない場合は、[account.microsoft.com](https://account.microsoft.com) にアクセスして無料でセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="bd70a-116">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="bd70a-117">**つまずく危険性のない安全で明るい場所**。</span><span class="sxs-lookup"><span data-stu-id="bd70a-117">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="bd70a-118">[健康と安全に関する情報をご覧ください](https://go.microsoft.com/fwlink/p/?LinkId=746661)。</span><span class="sxs-lookup"><span data-stu-id="bd70a-118">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="bd70a-119">**快適さを高めるオプションのアクセサリ**。HoloLens には、より快適なフィット感を得られるように、オプションのアクセサリが付属しています。</span><span class="sxs-lookup"><span data-stu-id="bd70a-119">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="bd70a-120">[快適に使うための詳しい情報をご覧ください](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)。</span><span class="sxs-lookup"><span data-stu-id="bd70a-120">[More on fit and comfort](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="bd70a-121">HoloLens を初めて使うときは、[Cortana](hololens-cortana.md) が既定でオンになり、ガイドが提供されます (ただし、デバイスのセットアップが完了するまでユーザーの質問に答えることはできません)。</span><span class="sxs-lookup"><span data-stu-id="bd70a-121">The first time that you use your HoloLens, [Cortana](hololens-cortana.md) is already on and ready to guide you (though she won't be able to respond to your questions until after you set up your device).</span></span> <span data-ttu-id="bd70a-122">Cortana の使用は、Cortana の設定を使用して、いつでもオフに変更できます。</span><span class="sxs-lookup"><span data-stu-id="bd70a-122">You can turn Cortana off at any time in Cortana's settings.</span></span>
> - <span data-ttu-id="bd70a-123">HoloLens の中国語版または日本語版に切り替えるには、その言語のビルドを PC にダウンロードしてから HoloLens にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd70a-123">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to download the build for the language on a PC and then install it on your HoloLens.</span></span> <span data-ttu-id="bd70a-124">詳細については、「[HoloLens (第 1 世代) のローカライズされたバージョンをインストールする](hololens1-install-localized.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd70a-124">For more information, see [Install localized versions of HoloLens (1st gen)](hololens1-install-localized.md).</span></span>

## <a name="start-your-hololens-and-set-up-windows"></a><span data-ttu-id="bd70a-125">Hololens の起動と Windows のセットアップ</span><span class="sxs-lookup"><span data-stu-id="bd70a-125">Start your Hololens and set up Windows</span></span>

<span data-ttu-id="bd70a-126">初めて HoloLens を起動する場合は、最初の作業として、デバイスで Windows Holographic をセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd70a-126">The first time you start your HoloLens, your first task is to set up Windows Holographic on your device.</span></span>

1. <span data-ttu-id="bd70a-127">インターネットに接続します (HoloLens により、Wi-Fi ネットワークを選択できるようにガイドが表示されます)。</span><span class="sxs-lookup"><span data-stu-id="bd70a-127">Connect to the internet (HoloLens guides you to select Wi-Fi network).</span></span>

1. <span data-ttu-id="bd70a-128">お使いのユーザー アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="bd70a-128">Sign in to your user account.</span></span> <span data-ttu-id="bd70a-129">**[職場または学校が所有しています]** または **[自分が所有しています]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd70a-129">Choose between **My work or school owns it** and **I own it**.</span></span>
    - <span data-ttu-id="bd70a-130">**[職場または学校が所有しています]** を選択し場合は、Azure AD アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="bd70a-130">When you choose **My work or school owns it**, you sign in by using an Azure AD account.</span></span> <span data-ttu-id="bd70a-131">組織で Azure AD Premium を使用しており、MDM への自動登録が構成されている場合は、HoloLens が自動的に MDM に登録されます。</span><span class="sxs-lookup"><span data-stu-id="bd70a-131">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="bd70a-132">組織で Azure AD Premium が使用されていない場合は MDM への自動登録を利用できないため、[HoloLens をデバイス管理に手動で登録](hololens-enroll-mdm.md#different-ways-to-enroll)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd70a-132">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available, so you will need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span> <span data-ttu-id="bd70a-133">職場または学校のアカウントを使用してデバイスへの初回サインインを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bd70a-133">To sign in to your device the first time by using a work or school account, follow these steps:</span></span>
        1. <span data-ttu-id="bd70a-134">組織アカウントの情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="bd70a-134">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="bd70a-135">プライバシー ステートメントに同意します。</span><span class="sxs-lookup"><span data-stu-id="bd70a-135">Accept the privacy statement.</span></span>
        1. <span data-ttu-id="bd70a-136">Azure AD 資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="bd70a-136">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="bd70a-137">組織のサインイン ページにリダイレクトされることがあります。</span><span class="sxs-lookup"><span data-stu-id="bd70a-137">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="bd70a-138">デバイスのセットアップを続行します。</span><span class="sxs-lookup"><span data-stu-id="bd70a-138">Continue setting up the device.</span></span>
    - <span data-ttu-id="bd70a-139">**[自分が所有しています]** を選んだ場合は、Microsoft アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="bd70a-139">When you choose **I own it**, you sign in by using a Microsoft account.</span></span> <span data-ttu-id="bd70a-140">セットアップが完了したら、[手動で HoloLens をデバイス管理に登録](hololens-enroll-mdm.md#different-ways-to-enroll)できます。</span><span class="sxs-lookup"><span data-stu-id="bd70a-140">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>
        1. <span data-ttu-id="bd70a-141">Microsoft アカウントの情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="bd70a-141">Enter your Microsoft account information.</span></span>
        1. <span data-ttu-id="bd70a-142">パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="bd70a-142">Enter your password.</span></span> <span data-ttu-id="bd70a-143">Microsoft アカウントで [2 段階認証 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/) が要求される場合、検証プロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="bd70a-143">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

1. <span data-ttu-id="bd70a-144">Wi-Fi ネットワークから取得された情報に基づいて、デバイスでタイム ゾーンが設定されます。</span><span class="sxs-lookup"><span data-stu-id="bd70a-144">The device sets your time zone based on information that it obtains from the Wi-Fi network.</span></span>

## <a name="calibration"></a><span data-ttu-id="bd70a-145">調整</span><span class="sxs-lookup"><span data-stu-id="bd70a-145">Calibration</span></span>

<span data-ttu-id="bd70a-146">Cortana の紹介後、次のセットアップ手順は調整です。</span><span class="sxs-lookup"><span data-stu-id="bd70a-146">After Cortana introduces herself, the next setup step is calibration.</span></span> <span data-ttu-id="bd70a-147">HoloLens のエクスペリエンスを最適化するには、セットアップ中に調整プロセスを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd70a-147">For the best HoloLens experience, you should complete the calibration process during setup.</span></span>

<span data-ttu-id="bd70a-148">HoloLens (第 1 世代) では、ホログラムをクリアに表示し、操作しやすくするために、瞳孔間距離 (IPD: [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance)) を使用します。</span><span class="sxs-lookup"><span data-stu-id="bd70a-148">HoloLens (1st gen) uses the distance between your pupils (IPD or [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance)) to make holograms clear and easy to interact with.</span></span> <span data-ttu-id="bd70a-149">IPD が正しくない場合は、ホログラムが不安定になったり、正しくない距離感で表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd70a-149">If the IPD is not correct, holograms may appear to be unstable or at an incorrect distance.</span></span>

<span data-ttu-id="bd70a-150">HoloLens の調整では、片目ごとに 6 つのターゲットに指を合わせるように求められます。</span><span class="sxs-lookup"><span data-stu-id="bd70a-150">During calibration, HoloLens asks you to align your finger with a series of six targets per eye.</span></span> <span data-ttu-id="bd70a-151">HoloLens はこのプロセスを使用し、ユーザーの目に合わせた適切な IPD を設定します。</span><span class="sxs-lookup"><span data-stu-id="bd70a-151">HoloLens uses this process to set the correct IPD for your eyes.</span></span> <span data-ttu-id="bd70a-152">新しいユーザー用に調整を更新または調整する必要がある場合、セットアップ外で調整アプリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="bd70a-152">If the calibration needs to be updated or adjusted for a new user, the new user can run the Calibration app  outside of setup.</span></span>

![IPD の指合わせ画面 (2 番目の手順)](./images/ipd-finger-alignment-300px.jpg)

*<span data-ttu-id="bd70a-154">IPD の指合わせ画面 (2 番目の手順)</span><span class="sxs-lookup"><span data-stu-id="bd70a-154">IPD finger-alignment screen at second step</span></span>*

<span data-ttu-id="bd70a-155">お疲れさまでした。</span><span class="sxs-lookup"><span data-stu-id="bd70a-155">Congratulations!</span></span> <span data-ttu-id="bd70a-156">セットアップは完了です。HoloLens の使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="bd70a-156">Setup is complete and you can begin using HoloLens.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bd70a-157">次のステップ</span><span class="sxs-lookup"><span data-stu-id="bd70a-157">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bd70a-158">HoloLens (第 1 世代) の概要</span><span class="sxs-lookup"><span data-stu-id="bd70a-158">Get started with HoloLens (1st gen)</span></span>](hololens1-basic-usage.md)
