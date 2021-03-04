---
title: 外部クライアント展開ガイド
description: 外部クライアント向け HoloLens 2 の展開ガイド (例としてリモート アシスト付き)
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
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385587"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a><span data-ttu-id="232eb-103">リモート アシストを使用した外部クライアントへの HoloLens 2 の展開</span><span class="sxs-lookup"><span data-stu-id="232eb-103">Deploying HoloLens 2 to External Clients with Remote Assist</span></span>

<span data-ttu-id="232eb-104">このガイドは、次の目標を持つ IT 担当者が組織に Microsoft HoloLens 2 デバイスを展開するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="232eb-104">This guide helps IT professionals with the following goals deploy Microsoft HoloLens 2 devices in their organization:</span></span>

1. <span data-ttu-id="232eb-105">クラウド接続 HoloLens 2 デバイス</span><span class="sxs-lookup"><span data-stu-id="232eb-105">Cloud connect HoloLens 2 devices</span></span>
1. <span data-ttu-id="232eb-106">HoloLens 2 デバイスを外部クライアントに貸与して使用する</span><span class="sxs-lookup"><span data-stu-id="232eb-106">Loan HoloLens 2 devices to external clients for use</span></span>
1. <span data-ttu-id="232eb-107">セキュリティで保護された貸し出しデバイス</span><span class="sxs-lookup"><span data-stu-id="232eb-107">Secure loaned devices</span></span>

<span data-ttu-id="232eb-108">このガイドでは、[ほとんどの HoloLens 2](#general-deployment-recommendations-and-instructions)展開シナリオに適用可能な HoloLens 2 の[](#common-concerns)一般的な展開推奨事項と、外部で使用するためにリモート アシストを展開するときにお客様が持つ一般的な懸念事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="232eb-108">This guide will provide [general HoloLens 2 deployment recommendations](#general-deployment-recommendations-and-instructions) that is applicable to most HoloLens 2 deployment scenarios and [common concerns](#common-concerns) that customers have when deploying Remote Assist for external use.</span></span>

## <a name="scenario-description"></a><span data-ttu-id="232eb-109">シナリオの説明</span><span class="sxs-lookup"><span data-stu-id="232eb-109">Scenario Description</span></span>

<span data-ttu-id="232eb-110">このドキュメントの目的で、Contoso 社は HoloLens 2 デバイスを短期的または長期的な使用のために外部クライアントの工場に出荷する必要があります。</span><span class="sxs-lookup"><span data-stu-id="232eb-110">For the purpose of this document, Contoso Company wants to ship a HoloLens 2 device to an external client's plant for short-term or long-term use.</span></span> <span data-ttu-id="232eb-111">クライアントが支援サービス 機械を必要とする場合、クライアントは Contoso 社が提供する資格情報を使用して HoloLens 2 デバイスにログインし、リモート アシストを使用して Contoso 社の専門家に連絡します。</span><span class="sxs-lookup"><span data-stu-id="232eb-111">When the client needs assistance servicing machinery, the client will log into the HoloLens 2 device using credentials provided by Contoso Company and use Remote Assist to contact Contoso Company's experts.</span></span>

<span data-ttu-id="232eb-112">リモート アシストの詳細については、こちらを [参照してください](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)。</span><span class="sxs-lookup"><span data-stu-id="232eb-112">Learn more about Remote Assist [here](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).</span></span>

### <a name="requirements-for-this-scenario"></a><span data-ttu-id="232eb-113">このシナリオの要件</span><span class="sxs-lookup"><span data-stu-id="232eb-113">Requirements for this Scenario</span></span>

1. [<span data-ttu-id="232eb-114">Azure AD</span><span class="sxs-lookup"><span data-stu-id="232eb-114">Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. <span data-ttu-id="232eb-115">モバイル デバイス マネージャー - [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)など</span><span class="sxs-lookup"><span data-stu-id="232eb-115">Mobile Device Manager - such as [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)</span></span>
1. <span data-ttu-id="232eb-116">リモート アシスト ライセンス</span><span class="sxs-lookup"><span data-stu-id="232eb-116">Remote Assist License</span></span>
    1. [<span data-ttu-id="232eb-117">リモート アシストの購入</span><span class="sxs-lookup"><span data-stu-id="232eb-117">Buy Remote Assist</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [<span data-ttu-id="232eb-118">試用版リモート アシスト</span><span class="sxs-lookup"><span data-stu-id="232eb-118">Trial Remote Assist</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a><span data-ttu-id="232eb-119">一般的な懸念事項</span><span class="sxs-lookup"><span data-stu-id="232eb-119">Common Concerns</span></span>

- [<span data-ttu-id="232eb-120">外部クライアントが相互に通信できない方法</span><span class="sxs-lookup"><span data-stu-id="232eb-120">How to ensure that external clients do not have the ability to communicate with one another</span></span>](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [<span data-ttu-id="232eb-121">クライアントが会社のリソースにアクセスできない方法</span><span class="sxs-lookup"><span data-stu-id="232eb-121">How to ensure that clients do not have access to company resources</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [<span data-ttu-id="232eb-122">アプリを制限する方法</span><span class="sxs-lookup"><span data-stu-id="232eb-122">How to restrict apps</span></span>](#how-to-restrict-apps)
- [<span data-ttu-id="232eb-123">パスワードを管理する方法</span><span class="sxs-lookup"><span data-stu-id="232eb-123">How to manage passwords</span></span>](#how-to-manage-passwords)
- [<span data-ttu-id="232eb-124">クライアントがチャット履歴にアクセスできない方法</span><span class="sxs-lookup"><span data-stu-id="232eb-124">How to ensure that clients do not have access to chat history</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a><span data-ttu-id="232eb-125">外部クライアントが相互に通信できない方法</span><span class="sxs-lookup"><span data-stu-id="232eb-125">How to ensure that external clients do not have the ability to communicate with one another</span></span>

<span data-ttu-id="232eb-126">HoloLens へのリモート アシスト HoloLens 呼び出しはサポートされていないので、クライアントは相互に通信できますが、検索できますが、通信できません。</span><span class="sxs-lookup"><span data-stu-id="232eb-126">Since Remote Assist HoloLens to HoloLens calls are not supported, clients are able to search for, but are unable to, communicate with one another.</span></span> <span data-ttu-id="232eb-127">クライアントが検索および呼び出しできるユーザーをさらに制限するために、  [情報](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) バリアは、クライアントが通信できるユーザーを制限できます。</span><span class="sxs-lookup"><span data-stu-id="232eb-127">To further restrict who clients can search for and call,  [Information barriers](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) can restrict who a client can communicate with.</span></span> <span data-ttu-id="232eb-128">考慮すべきもう 1 つのオプションは [、Scoped Directory Search を使用する方法です。](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)</span><span class="sxs-lookup"><span data-stu-id="232eb-128">Another option to consider is using [Scoped Directory Search](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)</span></span>

 > [!NOTE]
> <span data-ttu-id="232eb-129">シングル サインオンが有効になっているので、WDAC を使用してブラウザーを [**無効にすることが重要です**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)。</span><span class="sxs-lookup"><span data-stu-id="232eb-129">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="232eb-130">外部クライアントがブラウザーを開き、Web バージョンの Teams を使用する場合、クライアントは通話/チャット履歴にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="232eb-130">If an external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a><span data-ttu-id="232eb-131">クライアントが会社のリソースにアクセスできない方法</span><span class="sxs-lookup"><span data-stu-id="232eb-131">How to ensure that clients do not have access to company resources</span></span>

<span data-ttu-id="232eb-132">考慮すべき 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="232eb-132">There are two options to consider.</span></span>

<span data-ttu-id="232eb-133">最初のオプションは、多層的なアプローチです。</span><span class="sxs-lookup"><span data-stu-id="232eb-133">The first option is a multi-layer approach:</span></span>

1. <span data-ttu-id="232eb-134">ユーザーが必要とするライセンスのみを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="232eb-134">Only assign licenses that the user requires.</span></span> <span data-ttu-id="232eb-135">OneDrive、Outlook、SharePoint、Yammerなどをユーザーに割り当てない場合、それらのリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="232eb-135">If you do not assign OneDrive, Outlook, SharePoint, Yammer, etc. to the user, he/she will not have access to those resources.</span></span> <span data-ttu-id="232eb-136">ユーザーが必要とする唯一のライセンスは、開始するリモート アシスト、Intune、および AAD ライセンスです。</span><span class="sxs-lookup"><span data-stu-id="232eb-136">The only licenses the users will need is Remote Assist, Intune, and AAD licenses to begin.</span></span>
1. <span data-ttu-id="232eb-137">クライアントにアクセスしないアプリ (メールなど) をブロックします (「アプリを制限する [方法」を参照](#how-to-restrict-apps))。</span><span class="sxs-lookup"><span data-stu-id="232eb-137">Block apps (such as email) that you don’t want clients to access (See [How to restrict apps](#how-to-restrict-apps)).</span></span>
1. <span data-ttu-id="232eb-138">ユーザー名やパスワードをクライアントと共有しない。</span><span class="sxs-lookup"><span data-stu-id="232eb-138">Do NOT share usernames nor password with clients.</span></span> <span data-ttu-id="232eb-139">HoloLens 2 にログインするには、電子メールと数値の PIN が必要です。</span><span class="sxs-lookup"><span data-stu-id="232eb-139">To log into the HoloLens 2, an email and numerical PIN is required.</span></span>

<span data-ttu-id="232eb-140">2 つ目のオプションは、クライアントをホストする個別のテナントを作成する方法です (「イメージ 1.1」を参照)。</span><span class="sxs-lookup"><span data-stu-id="232eb-140">The second option is to create a separate tenant that hosts clients (see Image 1.1).</span></span>

**<span data-ttu-id="232eb-141">イメージ 1.1</span><span class="sxs-lookup"><span data-stu-id="232eb-141">Image 1.1</span></span>**

![サービス テナント イメージ](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a><span data-ttu-id="232eb-143">アプリを制限する方法</span><span class="sxs-lookup"><span data-stu-id="232eb-143">How to restrict apps</span></span>

<span data-ttu-id="232eb-144">[キオスク モード](https://docs.microsoft.com/hololens/hololens-kiosk) または [WDAC (Windows Defenderアプリケーション制御)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) は、アプリケーションを制限するためのオプションです。</span><span class="sxs-lookup"><span data-stu-id="232eb-144">[Kiosk Mode](https://docs.microsoft.com/hololens/hololens-kiosk) and/or [WDAC (Windows Defender Application Control)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) are options for restricting applications.</span></span>

### <a name="how-to-manage-passwords"></a><span data-ttu-id="232eb-145">パスワードを管理する方法</span><span class="sxs-lookup"><span data-stu-id="232eb-145">How to manage passwords</span></span>

1. <span data-ttu-id="232eb-146">パスワードの有効期限を削除します。</span><span class="sxs-lookup"><span data-stu-id="232eb-146">Remove password expiration.</span></span> <span data-ttu-id="232eb-147">ただし、これにより、アカウントが侵害される可能性が高されます。</span><span class="sxs-lookup"><span data-stu-id="232eb-147">However, this increases the chance that that an account will be compromised.</span></span> <span data-ttu-id="232eb-148">NIST パスワードの推奨事項は、30 ~ 90 日ごとにパスワードを変更します。</span><span class="sxs-lookup"><span data-stu-id="232eb-148">NIST password recommendation is change passwords every 30-90 days.</span></span>
1. <span data-ttu-id="232eb-149">HoloLens 2 デバイスのパスワードの有効期限を 90 日を超えるまで延長します。</span><span class="sxs-lookup"><span data-stu-id="232eb-149">Extend the password expiration for HoloLens 2 devices to exceed 90 days.</span></span>
1. <span data-ttu-id="232eb-150">パスワードを変更するには、デバイスを Contoso に返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="232eb-150">The devices should be returned to Contoso to change the passwords.</span></span> <span data-ttu-id="232eb-151">ただし、デバイスが 90 日以上クライアントの工場に含まれると予想される場合は、問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="232eb-151">However, this can cause issues if the devices are expected to be in the client's plant for 90+ days.</span></span>  
1. <span data-ttu-id="232eb-152">複数のクライアントに送信されるデバイスの場合は、デバイスをクライアントに出荷する前にパスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="232eb-152">For devices that are sent to multiple clients, reset passwords before shipping the device to clients.</span></span>

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a><span data-ttu-id="232eb-153">クライアントがチャット履歴にアクセスできない方法</span><span class="sxs-lookup"><span data-stu-id="232eb-153">How to ensure that clients do not have access to chat history</span></span>

<span data-ttu-id="232eb-154">リモート アシストは、各セッションの後にチャット履歴をクリアします。</span><span class="sxs-lookup"><span data-stu-id="232eb-154">Remote Assist clears chat history after each session.</span></span> <span data-ttu-id="232eb-155">ただし、チャット履歴は Microsoft Teams ユーザーが利用できます。</span><span class="sxs-lookup"><span data-stu-id="232eb-155">However, the chat history will be available for the Microsoft Teams user.</span></span>

> [!NOTE]
> <span data-ttu-id="232eb-156">シングル サインオンが有効になっているので、WDAC を使用してブラウザーを [**無効にすることが重要です**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)。</span><span class="sxs-lookup"><span data-stu-id="232eb-156">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="232eb-157">外部クライアントがブラウザーを開き、Web バージョンの Teams を使用する場合、クライアントは通話/チャット履歴にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="232eb-157">If a external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

## <a name="general-deployment-recommendations-and-instructions"></a><span data-ttu-id="232eb-158">一般的な展開の推奨事項と手順</span><span class="sxs-lookup"><span data-stu-id="232eb-158">General Deployment Recommendations and Instructions</span></span>

<span data-ttu-id="232eb-159">HoloLens 2 展開手順では、次の手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="232eb-159">We recommend the following for HoloLens 2 deployment Steps:</span></span>

1. <span data-ttu-id="232eb-160">ベースライン ビルド [として最新の HoloLens OS](https://aka.ms/hololens2download) リリースを使用します。</span><span class="sxs-lookup"><span data-stu-id="232eb-160">Use the [latest HoloLens OS release](https://aka.ms/hololens2download) as your baseline build.</span></span>
1. <span data-ttu-id="232eb-161">ユーザー ベースまたはデバイス ベースのライセンスを割り当てる:</span><span class="sxs-lookup"><span data-stu-id="232eb-161">Assign user-based or device-based licenses:</span></span>
    1. <span data-ttu-id="232eb-162">ユーザー ベースのライセンスとデバイス ベースのライセンスの両方が、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="232eb-162">User-based and device-based licenses both follow the following steps:</span></span>
        1. <span data-ttu-id="232eb-163">[AAD でグループを作成し](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) 、HoloLens/RA ユーザーのメンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="232eb-163">[Create a group in AAD and add members](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) for HoloLens/RA users.</span></span>
        1. <span data-ttu-id="232eb-164">[デバイス ベースまたはユーザー ベースのライセンスをこのグループ](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) に割り当てる。</span><span class="sxs-lookup"><span data-stu-id="232eb-164">[Assign device-based or user-based licenses](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) to this group.</span></span>
        1. <span data-ttu-id="232eb-165">(省略可能)MDM ポリシーのグループをターゲットにできます。</span><span class="sxs-lookup"><span data-stu-id="232eb-165">(Optional) You can target groups for MDM policies.</span></span>

1. <span data-ttu-id="232eb-166">デバイスは、AAD がテナントに参加し、 [自動登録](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)され、自動パイロットを介して [構成されている必要があります](https://docs.microsoft.com/hololens/hololens2-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="232eb-166">Devices should be AAD joined to your tenant, [Auto Enrolled](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm), and configured through [Auto Pilot](https://docs.microsoft.com/hololens/hololens2-autopilot).</span></span>
    1. <span data-ttu-id="232eb-167">デバイスの最初のユーザーはデバイスの所有者になります。</span><span class="sxs-lookup"><span data-stu-id="232eb-167">Please note that the first user on the device will be the device owner.</span></span>
    1. <span data-ttu-id="232eb-168">デバイスが AAD 参加の場合、参加を実行したユーザーはデバイス所有者になります。</span><span class="sxs-lookup"><span data-stu-id="232eb-168">Please note that if the device is AAD joined, the user that performed the join is made device owner.</span></span>
    1. <span data-ttu-id="232eb-169">詳細については、「デバイス所有者 [」を参照してください](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)。</span><span class="sxs-lookup"><span data-stu-id="232eb-169">For more, see [Device Owner](https://docs.microsoft.com/hololens/security-adminless-os#device-owner).</span></span>
1. <span data-ttu-id="232eb-170">[テナントは、](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) テナントに参加できるデバイスのみをロックします。</span><span class="sxs-lookup"><span data-stu-id="232eb-170">[Tenant lock](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) the device so that it can only joined your tenant.</span></span>
    1. <span data-ttu-id="232eb-171">**その他のリンク:** [テナント ロック CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)。</span><span class="sxs-lookup"><span data-stu-id="232eb-171">**Additional Link:** [Tenant lock CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp).</span></span>
1. <span data-ttu-id="232eb-172">ここにグローバルに割り当てられたアクセスを使用してキオスクを [構成します](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)。</span><span class="sxs-lookup"><span data-stu-id="232eb-172">Configure kiosk using global assigned access to [here](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk).</span></span>
1. <span data-ttu-id="232eb-173">フォロー (オプション) 機能を無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="232eb-173">We recommend disabling the follow (optional) capabilities:</span></span>
    1. <span data-ttu-id="232eb-174">ここでデバイスを開発者モードにする [機能](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)。</span><span class="sxs-lookup"><span data-stu-id="232eb-174">Ability to put the device into developer mode [here](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock).</span></span>
    1. <span data-ttu-id="232eb-175">HoloLens を PC に接続して日付をコピーする機能は [、USB を無効にします](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)。</span><span class="sxs-lookup"><span data-stu-id="232eb-175">Ability to connect the HoloLens to a PC to copy date [disable USB](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).</span></span>
       > [!NOTE]
        > <span data-ttu-id="232eb-176">USB を無効にしないが、USB を使用してデバイスにプロビジョニング パッケージを適用する機能が必要な場合は、ここに示す手順に従 [**います**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)。</span><span class="sxs-lookup"><span data-stu-id="232eb-176">If you don’t want to disable USB but want the ability to apply a provisioning package to the device using USB, follow the instructions listed [**here**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage).</span></span>

1. <span data-ttu-id="232eb-177">[WDAC を使用](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)して、HoloLens 2 デバイス上のアプリを許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="232eb-177">Use [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) to allow or block apps on the HoloLens 2 device.</span></span>
1. <span data-ttu-id="232eb-178">セットアップの一環として、リモート アシストを最新バージョンに更新します。</span><span class="sxs-lookup"><span data-stu-id="232eb-178">Update Remote Assist to the latest version as part of the setup.</span></span> <span data-ttu-id="232eb-179">これを行うには、次の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="232eb-179">There are two options to do this:</span></span>
    1. <span data-ttu-id="232eb-180">これは、Windows Microsoft Store --> リモート アシスト **-->更新アプリ にアクセスして実行できます**。</span><span class="sxs-lookup"><span data-stu-id="232eb-180">This can be done by going to Windows **Microsoft Store --> Remote Assist --> and Update App**.</span></span>
    1. <span data-ttu-id="232eb-181">[ApplicationManagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) (アプリの自動更新を許可する) は、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="232eb-181">[ApplicationManagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) - which allows automatic app updates - is enabled by default.</span></span> <span data-ttu-id="232eb-182">デバイスを接続して更新プログラムを受信します。</span><span class="sxs-lookup"><span data-stu-id="232eb-182">Keep the device plugged in to receive updates.</span></span>
1. <span data-ttu-id="232eb-183">[ネットワーク設定以外のすべての設定ページ](https://docs.microsoft.com/hololens/settings-uri-list) を無効にして、ユーザーがクライアント サイトでゲスト ネットワークに接続できます。</span><span class="sxs-lookup"><span data-stu-id="232eb-183">[Disable all settings pages](https://docs.microsoft.com/hololens/settings-uri-list) except the network settings to allow users to connect to guest networks at client sites.</span></span>
1. [<span data-ttu-id="232eb-184">HoloLens の更新プログラムの管理</span><span class="sxs-lookup"><span data-stu-id="232eb-184">Manage HoloLens Updates</span></span>](https://docs.microsoft.com/hololens/hololens-updates)
    1. <span data-ttu-id="232eb-185">OS の更新 [を制御するか、自由](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) にフローを許可するオプション。</span><span class="sxs-lookup"><span data-stu-id="232eb-185">Option to [control OS updates](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) or allow to flow freely.</span></span>
1. <span data-ttu-id="232eb-186">[一般的なデバイスの制限](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)。</span><span class="sxs-lookup"><span data-stu-id="232eb-186">[Common Device Restrictions](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).</span></span>
