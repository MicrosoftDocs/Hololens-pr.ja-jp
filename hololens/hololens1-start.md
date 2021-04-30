---
title: HoloLens のセットアップ (第1世代)
description: Microsoft (MSA) アカウントまたは Azure Active Directory (AAD) アカウントを使用して Wi-Fi ネットワーク経由で初めて HoloLens をセットアップする方法について説明します。
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309364"
---
# <a name="set-up-your-hololens-1st-gen"></a><span data-ttu-id="07c24-103">HoloLens をセットアップする (第1世代)</span><span class="sxs-lookup"><span data-stu-id="07c24-103">Set up your HoloLens (1st gen)</span></span>

<span data-ttu-id="07c24-104">HoloLens を初めてオンにしたときに、デバイスの調整、デバイスの設定、およびサインインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="07c24-104">The first time you turn on your HoloLens, you'll be guided through calibrating your device, setting up your device, and signing in.</span></span>  <span data-ttu-id="07c24-105">この記事では、HoloLens (第1世代) の最初の開始とセットアップのエクスペリエンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="07c24-105">This article walks through the HoloLens (1st gen) first start and setup experience.</span></span>

<span data-ttu-id="07c24-106">次のセクションでは、HoloLens を操作し、ホログラムを操作する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="07c24-106">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="07c24-107">この記事に進むには、「 [HoloLens を使ってみる (第1世代)](hololens1-basic-usage.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07c24-107">To skip ahead to that article, see [Get started with HoloLens (1st gen)](hololens1-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="07c24-108">開始する前に</span><span class="sxs-lookup"><span data-stu-id="07c24-108">Before you start</span></span>

<span data-ttu-id="07c24-109">作業を開始する前に、次のものが用意されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="07c24-109">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="07c24-110">**Wi-Fi 接続** です。</span><span class="sxs-lookup"><span data-stu-id="07c24-110">**A Wi-Fi connection**.</span></span> <span data-ttu-id="07c24-111">HoloLens を Wi-Fi ネットワークに接続して設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07c24-111">You'll need to connect your HoloLens to a Wi-Fi network to set it up.</span></span> <span data-ttu-id="07c24-112">初めて接続するときは、web サイトへの移動や接続に証明書を使用する必要がない、開いている、またはパスワードで保護されたネットワークが必要です。</span><span class="sxs-lookup"><span data-stu-id="07c24-112">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="07c24-113">[HoloLens が使用する web サイトの詳細については、こちらを参照して](hololens-offline.md)ください。</span><span class="sxs-lookup"><span data-stu-id="07c24-113">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="07c24-114">**Microsoft アカウントまたは職場アカウント**。</span><span class="sxs-lookup"><span data-stu-id="07c24-114">**A Microsoft account or a work account**.</span></span> <span data-ttu-id="07c24-115">また、HoloLens にサインインするには、Microsoft アカウント (または、組織がデバイスを所有している場合は職場のアカウント) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07c24-115">You'll also need to use a Microsoft account (or a work account, if your organization owns the device) to sign in to HoloLens.</span></span> <span data-ttu-id="07c24-116">Microsoft アカウントがない場合は、 [account.microsoft.com](https://account.microsoft.com) にアクセスし、1つを無料で設定します。</span><span class="sxs-lookup"><span data-stu-id="07c24-116">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="07c24-117">**危険な状態にならない安全で十分に光がある領域**。</span><span class="sxs-lookup"><span data-stu-id="07c24-117">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="07c24-118">[正常性と安全性の情報](https://go.microsoft.com/fwlink/p/?LinkId=746661)。</span><span class="sxs-lookup"><span data-stu-id="07c24-118">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="07c24-119">お客様の HoloLens に付属している **オプションの快適なアクセサリは**、最適な適合性を得るのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="07c24-119">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="07c24-120">[より快適で安心](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)です。</span><span class="sxs-lookup"><span data-stu-id="07c24-120">[More on fit and comfort](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="07c24-121">HoloLens を初めて使用するときは、 [Cortana](hololens-cortana.md) は既にオンになっており、ガイドの準備ができています (ただし、デバイスをセットアップするまで質問に回答することはできません)。</span><span class="sxs-lookup"><span data-stu-id="07c24-121">The first time that you use your HoloLens, [Cortana](hololens-cortana.md) is already on and ready to guide you (though she won't be able to respond to your questions until after you set up your device).</span></span> <span data-ttu-id="07c24-122">Cortana の設定で、いつでも Cortana をオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="07c24-122">You can turn Cortana off at any time in Cortana's settings.</span></span>
> - <span data-ttu-id="07c24-123">HoloLens の簡体字中国語または日本語版に切り替えるには、その言語のビルドを PC にダウンロードしてから HoloLens にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="07c24-123">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to download the build for the language on a PC and then install it on your HoloLens.</span></span> <span data-ttu-id="07c24-124">詳細については、「 [HoloLens のローカライズ版をインストールする (第1世代)](hololens1-install-localized.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07c24-124">For more information, see [Install localized versions of HoloLens (1st gen)](hololens1-install-localized.md).</span></span>

## <a name="start-your-hololens-and-set-up-windows"></a><span data-ttu-id="07c24-125">Hololens を起動して Windows をセットアップする</span><span class="sxs-lookup"><span data-stu-id="07c24-125">Start your Hololens and set up Windows</span></span>

<span data-ttu-id="07c24-126">HoloLens を初めて起動するときは、まず、デバイスに Windows Holographic をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="07c24-126">The first time you start your HoloLens, your first task is to set up Windows Holographic on your device.</span></span>

1. <span data-ttu-id="07c24-127">インターネットに接続します (HoloLens のガイドに従って Wi-Fi ネットワークを選択します)。</span><span class="sxs-lookup"><span data-stu-id="07c24-127">Connect to the internet (HoloLens guides you to select Wi-Fi network).</span></span>

1. <span data-ttu-id="07c24-128">ユーザーアカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="07c24-128">Sign in to your user account.</span></span> <span data-ttu-id="07c24-129">**職場または学校が所有するかどうか** を選択 **します。**</span><span class="sxs-lookup"><span data-stu-id="07c24-129">Choose between **My work or school owns it** and **I own it**.</span></span>
    - <span data-ttu-id="07c24-130">**職場または学校で所有** している場合は、Azure AD アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="07c24-130">When you choose **My work or school owns it**, you sign in by using an Azure AD account.</span></span> <span data-ttu-id="07c24-131">組織で Azure AD Premium を使用し、自動 MDM 登録を構成している場合、HoloLens は自動的に MDM に登録されます。</span><span class="sxs-lookup"><span data-stu-id="07c24-131">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="07c24-132">組織で Azure AD Premium を使用していない場合、MDM の自動登録は利用できないため、 [デバイス管理に HoloLens を手動で登録](hololens-enroll-mdm.md#different-ways-to-enroll)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07c24-132">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available, so you will need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span> <span data-ttu-id="07c24-133">職場または学校のアカウントを使用して初めてデバイスにサインインするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="07c24-133">To sign in to your device the first time by using a work or school account, follow these steps:</span></span>
        1. <span data-ttu-id="07c24-134">組織のアカウント情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="07c24-134">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="07c24-135">プライバシーに関する声明に同意します。</span><span class="sxs-lookup"><span data-stu-id="07c24-135">Accept the privacy statement.</span></span>
        1. <span data-ttu-id="07c24-136">Azure AD の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="07c24-136">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="07c24-137">組織のサインイン ページにリダイレクトされることがあります。</span><span class="sxs-lookup"><span data-stu-id="07c24-137">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="07c24-138">デバイスのセットアップを続行します。</span><span class="sxs-lookup"><span data-stu-id="07c24-138">Continue setting up the device.</span></span>
    - <span data-ttu-id="07c24-139">**所有** している場合は、Microsoft アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="07c24-139">When you choose **I own it**, you sign in by using a Microsoft account.</span></span> <span data-ttu-id="07c24-140">セットアップが完了したら、 [デバイス管理に HoloLens を手動で登録](hololens-enroll-mdm.md#different-ways-to-enroll)できます。</span><span class="sxs-lookup"><span data-stu-id="07c24-140">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>
        1. <span data-ttu-id="07c24-141">Microsoft アカウント情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="07c24-141">Enter your Microsoft account information.</span></span>
        1. <span data-ttu-id="07c24-142">パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="07c24-142">Enter your password.</span></span> <span data-ttu-id="07c24-143">Microsoft アカウントで [2 段階認証 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/) が要求される場合、検証プロセスを実行します。</span><span class="sxs-lookup"><span data-stu-id="07c24-143">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

1. <span data-ttu-id="07c24-144">デバイスは、Wi-Fi ネットワークから取得した情報に基づいてタイムゾーンを設定します。</span><span class="sxs-lookup"><span data-stu-id="07c24-144">The device sets your time zone based on information that it obtains from the Wi-Fi network.</span></span>

## <a name="calibration"></a><span data-ttu-id="07c24-145">調整</span><span class="sxs-lookup"><span data-stu-id="07c24-145">Calibration</span></span>

<span data-ttu-id="07c24-146">Cortana が自分で導入された後、次のセットアップ手順は調整です。</span><span class="sxs-lookup"><span data-stu-id="07c24-146">After Cortana introduces herself, the next setup step is calibration.</span></span> <span data-ttu-id="07c24-147">最適な HoloLens エクスペリエンスを実現するには、セットアップ中に調整プロセスを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07c24-147">For the best HoloLens experience, you should complete the calibration process during setup.</span></span>

<span data-ttu-id="07c24-148">HoloLens (第1世代) では、pupils (IPD または [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance)) 間の距離を使用して、ホログラムをクリアし、簡単に操作できるようにします。</span><span class="sxs-lookup"><span data-stu-id="07c24-148">HoloLens (1st gen) uses the distance between your pupils (IPD or [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance)) to make holograms clear and easy to interact with.</span></span> <span data-ttu-id="07c24-149">IPD が正しくない場合、ホログラムが不安定であるか、または正しくない距離にあるように見えることがあります。</span><span class="sxs-lookup"><span data-stu-id="07c24-149">If the IPD is not correct, holograms may appear to be unstable or at an incorrect distance.</span></span>

<span data-ttu-id="07c24-150">調整中、HoloLens は、1つ目につき6つのターゲットに指を合わせるように求められます。</span><span class="sxs-lookup"><span data-stu-id="07c24-150">During calibration, HoloLens asks you to align your finger with a series of six targets per eye.</span></span> <span data-ttu-id="07c24-151">HoloLens は、このプロセスを使用して、目の IPD を適切なものに設定します。</span><span class="sxs-lookup"><span data-stu-id="07c24-151">HoloLens uses this process to set the correct IPD for your eyes.</span></span> <span data-ttu-id="07c24-152">新しいユーザーに対して調整を更新または調整する必要がある場合、新しいユーザーはセットアップの外部で調整アプリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="07c24-152">If the calibration needs to be updated or adjusted for a new user, the new user can run the Calibration app  outside of setup.</span></span>

![2番目の手順での IPD の指配置画面](./images/ipd-finger-alignment-300px.jpg)

<span data-ttu-id="07c24-154">*2番目の手順での IPD の指配置画面*</span><span class="sxs-lookup"><span data-stu-id="07c24-154">*IPD finger-alignment screen at second step*</span></span>

<span data-ttu-id="07c24-155">おめでとうございます。</span><span class="sxs-lookup"><span data-stu-id="07c24-155">Congratulations!</span></span> <span data-ttu-id="07c24-156">セットアップが完了し、HoloLens の使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="07c24-156">Setup is complete and you can begin using HoloLens.</span></span>

## <a name="next-steps"></a><span data-ttu-id="07c24-157">次のステップ</span><span class="sxs-lookup"><span data-stu-id="07c24-157">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="07c24-158">HoloLens を使ってみる (第1世代)</span><span class="sxs-lookup"><span data-stu-id="07c24-158">Get started with HoloLens (1st gen)</span></span>](hololens1-basic-usage.md)
