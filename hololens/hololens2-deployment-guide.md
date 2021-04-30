---
title: 外部クライアントの展開ガイド
description: 外部クライアント向けの HoloLens 2 の展開ガイド (例としてリモートアシスタンスを使用)
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/12/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 56930ceea05cd5713b9c7eb57e0967a9d0cd4988
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309337"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a><span data-ttu-id="68add-103">リモートアシスタンスを使用した外部クライアントへの HoloLens 2 の展開</span><span class="sxs-lookup"><span data-stu-id="68add-103">Deploying HoloLens 2 to External Clients with Remote Assist</span></span>

<span data-ttu-id="68add-104">このガイドは、次の目標を持つ IT プロフェッショナルが組織で Microsoft HoloLens 2 デバイスを展開するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="68add-104">This guide helps IT professionals with the following goals deploy Microsoft HoloLens 2 devices in their organization:</span></span>

1. <span data-ttu-id="68add-105">Cloud connect HoloLens 2 デバイス</span><span class="sxs-lookup"><span data-stu-id="68add-105">Cloud connect HoloLens 2 devices</span></span>
1. <span data-ttu-id="68add-106">ローン HoloLens 2 デバイスを外部クライアントに使用する</span><span class="sxs-lookup"><span data-stu-id="68add-106">Loan HoloLens 2 devices to external clients for use</span></span>
1. <span data-ttu-id="68add-107">セキュリティで保護された貸与デバイス</span><span class="sxs-lookup"><span data-stu-id="68add-107">Secure loaned devices</span></span>

<span data-ttu-id="68add-108">このガイドでは、多くの HoloLens 2 展開シナリオに適用される [一般的な hololens 2 展開の推奨事項](#general-deployment-recommendations-and-instructions) と、外部使用のためにリモートアシスタンスを展開するときの [一般的な懸念](#common-concerns) 事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="68add-108">This guide will provide [general HoloLens 2 deployment recommendations](#general-deployment-recommendations-and-instructions) that is applicable to most HoloLens 2 deployment scenarios and [common concerns](#common-concerns) that customers have when deploying Remote Assist for external use.</span></span>

## <a name="scenario-description"></a><span data-ttu-id="68add-109">シナリオの説明</span><span class="sxs-lookup"><span data-stu-id="68add-109">Scenario Description</span></span>

<span data-ttu-id="68add-110">このドキュメントでは、Contoso 社は、短期または長期的に使用するために、外部クライアントのプラントに HoloLens 2 デバイスを発送することを希望しています。</span><span class="sxs-lookup"><span data-stu-id="68add-110">For the purpose of this document, Contoso Company wants to ship a HoloLens 2 device to an external client's plant for short-term or long-term use.</span></span> <span data-ttu-id="68add-111">クライアントがサポートサービスメカニズムを必要とする場合、クライアントは Contoso 社から提供された資格情報を使用して HoloLens 2 デバイスにログインし、リモートアシスタンスを使用して Contoso 社の専門家に問い合わせます。</span><span class="sxs-lookup"><span data-stu-id="68add-111">When the client needs assistance servicing machinery, the client will log into the HoloLens 2 device using credentials provided by Contoso Company and use Remote Assist to contact Contoso Company's experts.</span></span>

<span data-ttu-id="68add-112">リモートアシスタンスの詳細について [は、こちら](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68add-112">Learn more about Remote Assist [here](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).</span></span>

### <a name="requirements-for-this-scenario"></a><span data-ttu-id="68add-113">このシナリオの要件</span><span class="sxs-lookup"><span data-stu-id="68add-113">Requirements for this Scenario</span></span>

1. [<span data-ttu-id="68add-114">Azure AD</span><span class="sxs-lookup"><span data-stu-id="68add-114">Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. <span data-ttu-id="68add-115">モバイル Device Manager ( [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)など)</span><span class="sxs-lookup"><span data-stu-id="68add-115">Mobile Device Manager - such as [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)</span></span>
1. <span data-ttu-id="68add-116">リモート支援ライセンス</span><span class="sxs-lookup"><span data-stu-id="68add-116">Remote Assist License</span></span>
    1. [<span data-ttu-id="68add-117">リモートアシスタンスの購入</span><span class="sxs-lookup"><span data-stu-id="68add-117">Buy Remote Assist</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [<span data-ttu-id="68add-118">試用版リモートアシスタンス</span><span class="sxs-lookup"><span data-stu-id="68add-118">Trial Remote Assist</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a><span data-ttu-id="68add-119">一般的な懸念事項</span><span class="sxs-lookup"><span data-stu-id="68add-119">Common Concerns</span></span>

- [<span data-ttu-id="68add-120">外部のクライアントが互いに通信することができないようにする方法</span><span class="sxs-lookup"><span data-stu-id="68add-120">How to ensure that external clients do not have the ability to communicate with one another</span></span>](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [<span data-ttu-id="68add-121">クライアントが会社のリソースにアクセスできないようにする方法</span><span class="sxs-lookup"><span data-stu-id="68add-121">How to ensure that clients do not have access to company resources</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [<span data-ttu-id="68add-122">アプリを制限する方法</span><span class="sxs-lookup"><span data-stu-id="68add-122">How to restrict apps</span></span>](#how-to-restrict-apps)
- [<span data-ttu-id="68add-123">パスワードを管理する方法</span><span class="sxs-lookup"><span data-stu-id="68add-123">How to manage passwords</span></span>](#how-to-manage-passwords)
- [<span data-ttu-id="68add-124">クライアントがチャット履歴にアクセスできないようにする方法</span><span class="sxs-lookup"><span data-stu-id="68add-124">How to ensure that clients do not have access to chat history</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a><span data-ttu-id="68add-125">外部のクライアントが互いに通信することができないようにする方法</span><span class="sxs-lookup"><span data-stu-id="68add-125">How to ensure that external clients do not have the ability to communicate with one another</span></span>

<span data-ttu-id="68add-126">リモートアシスタンス HoloLens から HoloLens への呼び出しはサポートされていないため、クライアントは検索できますが、相互に通信することはできません。</span><span class="sxs-lookup"><span data-stu-id="68add-126">Since Remote Assist HoloLens to HoloLens calls are not supported, clients are able to search for, but are unable to, communicate with one another.</span></span> <span data-ttu-id="68add-127">クライアントが検索して呼び出すことができるユーザーをさらに制限するために、  [情報バリア](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) はクライアントが通信できるユーザーを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="68add-127">To further restrict who clients can search for and call,  [Information barriers](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) can restrict who a client can communicate with.</span></span> <span data-ttu-id="68add-128">考慮すべきもう1つのオプションは、スコープを指定した[ディレクトリ検索](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)の使用</span><span class="sxs-lookup"><span data-stu-id="68add-128">Another option to consider is using [Scoped Directory Search](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)</span></span>

 > [!NOTE]
> <span data-ttu-id="68add-129">シングルサインオンが有効になっているため、 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)を使用してブラウザーを無効にすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="68add-129">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="68add-130">外部クライアントがブラウザーを開き、チームの web バージョンを使用する場合、クライアントは通話/チャット履歴にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="68add-130">If an external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a><span data-ttu-id="68add-131">クライアントが会社のリソースにアクセスできないようにする方法</span><span class="sxs-lookup"><span data-stu-id="68add-131">How to ensure that clients do not have access to company resources</span></span>

<span data-ttu-id="68add-132">考慮すべき2つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="68add-132">There are two options to consider.</span></span>

<span data-ttu-id="68add-133">1つ目のオプションは、マルチレイヤーアプローチです。</span><span class="sxs-lookup"><span data-stu-id="68add-133">The first option is a multi-layer approach:</span></span>

1. <span data-ttu-id="68add-134">ユーザーが必要とするライセンスのみを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="68add-134">Only assign licenses that the user requires.</span></span> <span data-ttu-id="68add-135">OneDrive、Outlook、SharePoint、Yammer などをユーザーに割り当てないと、それらのリソースにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="68add-135">If you do not assign OneDrive, Outlook, SharePoint, Yammer, etc. to the user, he/she will not have access to those resources.</span></span> <span data-ttu-id="68add-136">ユーザーが必要とするライセンスは、リモートアシスタンス、Intune、および AAD のライセンスのみです。</span><span class="sxs-lookup"><span data-stu-id="68add-136">The only licenses the users will need is Remote Assist, Intune, and AAD licenses to begin.</span></span>
1. <span data-ttu-id="68add-137">クライアントにアクセスしたくないアプリ (電子メールなど) をブロックします (「 [アプリを制限する方法」を](#how-to-restrict-apps)参照してください)。</span><span class="sxs-lookup"><span data-stu-id="68add-137">Block apps (such as email) that you don’t want clients to access (See [How to restrict apps](#how-to-restrict-apps)).</span></span>
1. <span data-ttu-id="68add-138">ユーザー名とパスワードをクライアントで共有しないでください。</span><span class="sxs-lookup"><span data-stu-id="68add-138">Do NOT share usernames nor password with clients.</span></span> <span data-ttu-id="68add-139">HoloLens 2 にログインするには、電子メールと数字の PIN が必要です。</span><span class="sxs-lookup"><span data-stu-id="68add-139">To log into the HoloLens 2, an email and numerical PIN is required.</span></span>

<span data-ttu-id="68add-140">2つ目のオプションは、クライアントをホストする別のテナントを作成することです (「イメージ1.1」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="68add-140">The second option is to create a separate tenant that hosts clients (see Image 1.1).</span></span>

<span data-ttu-id="68add-141">**イメージ1.1**</span><span class="sxs-lookup"><span data-stu-id="68add-141">**Image 1.1**</span></span>

![サービステナントの画像](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a><span data-ttu-id="68add-143">アプリを制限する方法</span><span class="sxs-lookup"><span data-stu-id="68add-143">How to restrict apps</span></span>

<span data-ttu-id="68add-144">[キオスクモード](https://docs.microsoft.com/hololens/hololens-kiosk) または [WDAC (Windows Defender Application Control)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) は、アプリケーションを制限するためのオプションです。</span><span class="sxs-lookup"><span data-stu-id="68add-144">[Kiosk Mode](https://docs.microsoft.com/hololens/hololens-kiosk) and/or [WDAC (Windows Defender Application Control)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) are options for restricting applications.</span></span>

### <a name="how-to-manage-passwords"></a><span data-ttu-id="68add-145">パスワードを管理する方法</span><span class="sxs-lookup"><span data-stu-id="68add-145">How to manage passwords</span></span>

1. <span data-ttu-id="68add-146">パスワードの有効期限を削除します。</span><span class="sxs-lookup"><span data-stu-id="68add-146">Remove password expiration.</span></span> <span data-ttu-id="68add-147">ただし、これにより、アカウントが侵害される可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="68add-147">However, this increases the chance that that an account will be compromised.</span></span> <span data-ttu-id="68add-148">NIST パスワードの推奨事項は、30-90 日おきにパスワードを変更することです。</span><span class="sxs-lookup"><span data-stu-id="68add-148">NIST password recommendation is change passwords every 30-90 days.</span></span>
1. <span data-ttu-id="68add-149">HoloLens 2 デバイスのパスワードの有効期限を90日を超えるように拡張します。</span><span class="sxs-lookup"><span data-stu-id="68add-149">Extend the password expiration for HoloLens 2 devices to exceed 90 days.</span></span>
1. <span data-ttu-id="68add-150">デバイスは、パスワードを変更するために Contoso に返される必要があります。</span><span class="sxs-lookup"><span data-stu-id="68add-150">The devices should be returned to Contoso to change the passwords.</span></span> <span data-ttu-id="68add-151">ただし、デバイスが90日以上クライアントのプラントにあると予想される場合は、問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="68add-151">However, this can cause issues if the devices are expected to be in the client's plant for 90+ days.</span></span>  
1. <span data-ttu-id="68add-152">複数のクライアントに送信されるデバイスの場合は、デバイスをクライアントに発送する前にパスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="68add-152">For devices that are sent to multiple clients, reset passwords before shipping the device to clients.</span></span>

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a><span data-ttu-id="68add-153">クライアントがチャット履歴にアクセスできないようにする方法</span><span class="sxs-lookup"><span data-stu-id="68add-153">How to ensure that clients do not have access to chat history</span></span>

<span data-ttu-id="68add-154">リモートアシスタンスは、各セッションの後にチャットの履歴をクリアします。</span><span class="sxs-lookup"><span data-stu-id="68add-154">Remote Assist clears chat history after each session.</span></span> <span data-ttu-id="68add-155">ただし、チャットの履歴は、Microsoft Teams ユーザーが使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="68add-155">However, the chat history will be available for the Microsoft Teams user.</span></span>

> [!NOTE]
> <span data-ttu-id="68add-156">シングルサインオンが有効になっているため、 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)を使用してブラウザーを無効にすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="68add-156">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="68add-157">外部クライアントがブラウザーを開き、チームの web バージョンを使用する場合、クライアントは通話/チャット履歴にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="68add-157">If a external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

## <a name="general-deployment-recommendations-and-instructions"></a><span data-ttu-id="68add-158">デプロイに関する一般的な推奨事項と手順</span><span class="sxs-lookup"><span data-stu-id="68add-158">General Deployment Recommendations and Instructions</span></span>

<span data-ttu-id="68add-159">HoloLens 2 のデプロイ手順については、次のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="68add-159">We recommend the following for HoloLens 2 deployment Steps:</span></span>

1. <span data-ttu-id="68add-160">最新の [HOLOLENS OS リリース](https://aka.ms/hololens2download) をベースラインビルドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="68add-160">Use the [latest HoloLens OS release](https://aka.ms/hololens2download) as your baseline build.</span></span>
1. <span data-ttu-id="68add-161">ユーザーベースまたはデバイスベースのライセンスを割り当てる:</span><span class="sxs-lookup"><span data-stu-id="68add-161">Assign user-based or device-based licenses:</span></span>
    1. <span data-ttu-id="68add-162">ユーザーベースおよびデバイスベースのライセンスは、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="68add-162">User-based and device-based licenses both follow the following steps:</span></span>
        1. <span data-ttu-id="68add-163">[AAD にグループを作成し、](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) HOLOLENS/RA ユーザーのメンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="68add-163">[Create a group in AAD and add members](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) for HoloLens/RA users.</span></span>
        1. <span data-ttu-id="68add-164">[デバイスベースまたはユーザーベースのライセンス](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) をこのグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="68add-164">[Assign device-based or user-based licenses](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) to this group.</span></span>
        1. <span data-ttu-id="68add-165">OptionalMDM ポリシーのグループを対象にすることができます。</span><span class="sxs-lookup"><span data-stu-id="68add-165">(Optional) You can target groups for MDM policies.</span></span>

1. <span data-ttu-id="68add-166">デバイスは、AAD をテナントに参加させ、 [自動登録](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)し、 [自動パイロット](https://docs.microsoft.com/hololens/hololens2-autopilot)によって構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68add-166">Devices should be AAD joined to your tenant, [Auto Enrolled](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm), and configured through [Auto Pilot](https://docs.microsoft.com/hololens/hololens2-autopilot).</span></span>
    1. <span data-ttu-id="68add-167">デバイスの最初のユーザーがデバイスの所有者であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="68add-167">Please note that the first user on the device will be the device owner.</span></span>
    1. <span data-ttu-id="68add-168">デバイスが AAD に参加している場合は、結合を実行したユーザーがデバイスの所有者になります。</span><span class="sxs-lookup"><span data-stu-id="68add-168">Please note that if the device is AAD joined, the user that performed the join is made device owner.</span></span>
    1. <span data-ttu-id="68add-169">詳細については、「 [デバイスの所有者](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68add-169">For more, see [Device Owner](https://docs.microsoft.com/hololens/security-adminless-os#device-owner).</span></span>
1. <span data-ttu-id="68add-170">テナントは、テナントにのみ参加できるようにデバイスを[ロック](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot)します。</span><span class="sxs-lookup"><span data-stu-id="68add-170">[Tenant lock](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) the device so that it can only joined your tenant.</span></span>
    1. <span data-ttu-id="68add-171">**追加リンク:** [テナントロック CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)。</span><span class="sxs-lookup"><span data-stu-id="68add-171">**Additional Link:** [Tenant lock CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp).</span></span>
1. <span data-ttu-id="68add-172">グローバルに割り当てられたアクセスを使用してキオスクを [構成します](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)。</span><span class="sxs-lookup"><span data-stu-id="68add-172">Configure kiosk using global assigned access to [here](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk).</span></span>
1. <span data-ttu-id="68add-173">次の (オプション) 機能を無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="68add-173">We recommend disabling the follow (optional) capabilities:</span></span>
    1. <span data-ttu-id="68add-174">[ここで](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)、デバイスを開発者モードにする機能。</span><span class="sxs-lookup"><span data-stu-id="68add-174">Ability to put the device into developer mode [here](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock).</span></span>
    1. <span data-ttu-id="68add-175">HoloLens を PC に接続して日付をコピーする機能は、 [USB を無効](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)にします。</span><span class="sxs-lookup"><span data-stu-id="68add-175">Ability to connect the HoloLens to a PC to copy date [disable USB](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).</span></span>
       > [!NOTE]
        > <span data-ttu-id="68add-176">Usb を無効にし、USB を使用してプロビジョニングパッケージをデバイスに適用する機能が必要な場合は、 [**こちら**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="68add-176">If you don’t want to disable USB but want the ability to apply a provisioning package to the device using USB, follow the instructions listed [**here**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage).</span></span>

1. <span data-ttu-id="68add-177">[WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)を使用して、HoloLens 2 デバイスでアプリを許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="68add-177">Use [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) to allow or block apps on the HoloLens 2 device.</span></span>
1. <span data-ttu-id="68add-178">セットアップの一部として、リモートアシスタンスを最新バージョンに更新します。</span><span class="sxs-lookup"><span data-stu-id="68add-178">Update Remote Assist to the latest version as part of the setup.</span></span> <span data-ttu-id="68add-179">これを行うには、次の2つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="68add-179">There are two options to do this:</span></span>
    1. <span data-ttu-id="68add-180">これを行うには、[Windows **Microsoft Store--> リモートアシスタンス--> およびアプリの更新**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="68add-180">This can be done by going to Windows **Microsoft Store --> Remote Assist --> and Update App**.</span></span>
    1. <span data-ttu-id="68add-181">[Applicationmanagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) -アプリの自動更新を許可します。既定では有効になっています。</span><span class="sxs-lookup"><span data-stu-id="68add-181">[ApplicationManagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) - which allows automatic app updates - is enabled by default.</span></span> <span data-ttu-id="68add-182">デバイスを接続したままにして、更新プログラムを受信します。</span><span class="sxs-lookup"><span data-stu-id="68add-182">Keep the device plugged in to receive updates.</span></span>
1. <span data-ttu-id="68add-183">ネットワーク設定を除く[すべての設定ページを無効](https://docs.microsoft.com/hololens/settings-uri-list)にして、ユーザーがクライアントサイトでゲストネットワークに接続できるようにします。</span><span class="sxs-lookup"><span data-stu-id="68add-183">[Disable all settings pages](https://docs.microsoft.com/hololens/settings-uri-list) except the network settings to allow users to connect to guest networks at client sites.</span></span>
1. [<span data-ttu-id="68add-184">HoloLens 更新プログラムの管理</span><span class="sxs-lookup"><span data-stu-id="68add-184">Manage HoloLens Updates</span></span>](https://docs.microsoft.com/hololens/hololens-updates)
    1. <span data-ttu-id="68add-185">OS の [更新プログラムを制御](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) したり、自由にフローを許可したりするためのオプションです。</span><span class="sxs-lookup"><span data-stu-id="68add-185">Option to [control OS updates](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) or allow to flow freely.</span></span>
1. <span data-ttu-id="68add-186">[一般的なデバイスの制限](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)。</span><span class="sxs-lookup"><span data-stu-id="68add-186">[Common Device Restrictions](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).</span></span>
