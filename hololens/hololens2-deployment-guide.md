---
title: 展開ガイド
description: HoloLens 2 の展開ガイド (例としてリモート アシスト付き)
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/7/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 0cd75fdbe5f6a4e6da87770768ce9f22bce491c0
ms.sourcegitcommit: 58bffba63ed581351d80d13b1437aca74d7ed64a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "11266374"
---
# <span data-ttu-id="b50e2-103">リモート アシストによる外部クライアントへの HoloLens 2 の展開</span><span class="sxs-lookup"><span data-stu-id="b50e2-103">Deploying HoloLens 2 to External Clients with Remote Assist</span></span>

<span data-ttu-id="b50e2-104">このドキュメントは、リモート アシストに重点を置いて HoloLens 2 デバイスを計画および展開する IT 専門職に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b50e2-104">This document helps IT professions plan for and deploy HoloLens 2 devices with a focus on Remote Assist.</span></span> <span data-ttu-id="b50e2-105">[リモート アシストについて詳しくは、次のリンクを参照してください](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)。</span><span class="sxs-lookup"><span data-stu-id="b50e2-105">[Learn more about Remote Assist](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).</span></span>

## <span data-ttu-id="b50e2-106">シナリオの説明</span><span class="sxs-lookup"><span data-stu-id="b50e2-106">Scenario Description</span></span>

<span data-ttu-id="b50e2-107">このドキュメントの目的上、Contoso Company は、短期的または長期的な使用のために、HoloLens 2 デバイスを外部クライアントの工場に出荷する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b50e2-107">For the purpose of this document, Contoso Company wants to ship a HoloLens 2 device to an external client's plant for short-term or long-term use.</span></span> <span data-ttu-id="b50e2-108">クライアントがアシスタンス サービス マシンを必要とする場合、クライアントは Contoso Company が提供する資格情報を使用して HoloLens 2 デバイスにログインし、リモート アシストを使用して Contoso Company の専門家に問い合わせています。</span><span class="sxs-lookup"><span data-stu-id="b50e2-108">When the client needs assistance servicing machinery, the client will log into the HoloLens 2 device using credentials provided by Contoso Company and use Remote Assist to contact Contoso Company's experts.</span></span>

### <span data-ttu-id="b50e2-109">このシナリオの要件</span><span class="sxs-lookup"><span data-stu-id="b50e2-109">Requirements for this Scenario</span></span>

1. [<span data-ttu-id="b50e2-110">Azure AD</span><span class="sxs-lookup"><span data-stu-id="b50e2-110">Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. <span data-ttu-id="b50e2-111">モバイル デバイス マネージャー - [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)など</span><span class="sxs-lookup"><span data-stu-id="b50e2-111">Mobile Device Manager - such as [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)</span></span>
1. <span data-ttu-id="b50e2-112">リモート アシスト ライセンス</span><span class="sxs-lookup"><span data-stu-id="b50e2-112">Remote Assist License</span></span>
    1. [<span data-ttu-id="b50e2-113">リモート アシストを購入する</span><span class="sxs-lookup"><span data-stu-id="b50e2-113">Buy Remote Assist</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [<span data-ttu-id="b50e2-114">試用版リモート アシスト</span><span class="sxs-lookup"><span data-stu-id="b50e2-114">Trial Remote Assist</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <span data-ttu-id="b50e2-115">一般的な問題</span><span class="sxs-lookup"><span data-stu-id="b50e2-115">Common Concerns</span></span>

- [<span data-ttu-id="b50e2-116">外部クライアントが相互に通信する機能を持たなことを確認する方法</span><span class="sxs-lookup"><span data-stu-id="b50e2-116">How to ensure that external clients do not have the ability to communicate with one another</span></span>](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [<span data-ttu-id="b50e2-117">クライアントが会社のリソースにアクセスできないか確認する方法</span><span class="sxs-lookup"><span data-stu-id="b50e2-117">How to ensure that clients do not have access to company resources</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [<span data-ttu-id="b50e2-118">アプリを制限する方法</span><span class="sxs-lookup"><span data-stu-id="b50e2-118">How to restrict apps</span></span>](#how-to-restrict-apps)
- [<span data-ttu-id="b50e2-119">パスワードを管理する方法</span><span class="sxs-lookup"><span data-stu-id="b50e2-119">How to manage passwords</span></span>](#how-to-manage-passwords)
- [<span data-ttu-id="b50e2-120">クライアントがチャット履歴にアクセスできないか確認する方法</span><span class="sxs-lookup"><span data-stu-id="b50e2-120">How to ensure that clients do not have access to chat history</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <span data-ttu-id="b50e2-121">外部クライアントが相互に通信する機能を持たなことを確認する方法</span><span class="sxs-lookup"><span data-stu-id="b50e2-121">How to ensure that external clients do not have the ability to communicate with one another</span></span>

<span data-ttu-id="b50e2-122">HoloLens から HoloLens へのリモート アシスト呼び出しはサポートされていないので、クライアントは互いに通信を検索できますが、相互に通信できません。</span><span class="sxs-lookup"><span data-stu-id="b50e2-122">Since Remote Assist HoloLens to HoloLens calls are not supported, clients are able to search for, but are unable to, communicate with one another.</span></span> <span data-ttu-id="b50e2-123">クライアントが検索および通話できるユーザーをさらに制限するために、[](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide)情報バリアはクライアントが通信できるユーザーを制限できます。</span><span class="sxs-lookup"><span data-stu-id="b50e2-123">To further restrict who clients can search for and call,  [Information barriers](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) can restrict who a client can communicate with.</span></span> <span data-ttu-id="b50e2-124">もう 1 つの検討すべきオプションは [、スコープ指定ディレクトリ検索の使用です。](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)</span><span class="sxs-lookup"><span data-stu-id="b50e2-124">Another option to consider is using [Scoped Directory Search](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)</span></span>

 > [!NOTE]
> <span data-ttu-id="b50e2-125">シングル サインオンが有効になっているので [**、WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)を使用してブラウザーを無効にすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="b50e2-125">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="b50e2-126">外部クライアントがブラウザーを開き、Web バージョンの Teams を使用する場合、クライアントは通話/チャット履歴にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b50e2-126">If an external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

### <span data-ttu-id="b50e2-127">クライアントが会社のリソースにアクセスできないか確認する方法</span><span class="sxs-lookup"><span data-stu-id="b50e2-127">How to ensure that clients do not have access to company resources</span></span>

<span data-ttu-id="b50e2-128">考慮すべき 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="b50e2-128">There are two options to consider.</span></span>

<span data-ttu-id="b50e2-129">最初のオプションは、多層的なアプローチです。</span><span class="sxs-lookup"><span data-stu-id="b50e2-129">The first option is a multi-layer approach:</span></span>

1. <span data-ttu-id="b50e2-130">ユーザーが必要とするライセンスのみを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="b50e2-130">Only assign licenses that the user requires.</span></span> <span data-ttu-id="b50e2-131">OneDrive、Outlook、SharePoint、Yammer などをユーザーに割り当てない場合、ユーザーはそれらのリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b50e2-131">If you do not assign OneDrive, Outlook, SharePoint, Yammer, etc. to the user, he/she will not have access to those resources.</span></span> <span data-ttu-id="b50e2-132">ユーザーが必要とするライセンスは、リモート アシスト、Intune、および AAD ライセンスのみです。</span><span class="sxs-lookup"><span data-stu-id="b50e2-132">The only licenses the users will need is Remote Assist, Intune, and AAD licenses to begin.</span></span>
1. <span data-ttu-id="b50e2-133">クライアントにアクセスしたくないアプリ (メールなど) をブロックする (「アプリを制限する[方法」を参照)。](#how-to-restrict-apps)</span><span class="sxs-lookup"><span data-stu-id="b50e2-133">Block apps (such as email) that you don’t want clients to access (See [How to restrict apps](#how-to-restrict-apps)).</span></span>
1. <span data-ttu-id="b50e2-134">ユーザー名やパスワードをクライアントと共有しません。</span><span class="sxs-lookup"><span data-stu-id="b50e2-134">Do NOT share usernames nor password with clients.</span></span> <span data-ttu-id="b50e2-135">HoloLens 2 にログインするには、電子メールと数値の PIN が必要です。</span><span class="sxs-lookup"><span data-stu-id="b50e2-135">To log into the HoloLens 2, an email and numerical PIN is required.</span></span>

<span data-ttu-id="b50e2-136">2 つ目のオプションは、クライアントをホストする個別のテナントを作成する方法です (イメージ 1.1 を参照)。</span><span class="sxs-lookup"><span data-stu-id="b50e2-136">The second option is to create a separate tenant that hosts clients (see Image 1.1).</span></span>

**<span data-ttu-id="b50e2-137">画像 1.1</span><span class="sxs-lookup"><span data-stu-id="b50e2-137">Image 1.1</span></span>**

![サービス テナント イメージ](./images/hololens-service-tenant-image.png)

### <span data-ttu-id="b50e2-139">アプリを制限する方法</span><span class="sxs-lookup"><span data-stu-id="b50e2-139">How to restrict apps</span></span>

<span data-ttu-id="b50e2-140">[キオスク モード](https://docs.microsoft.com/hololens/hololens-kiosk) や [WDAC (Windows Defender アプリケーション制御)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) は、アプリケーションを制限するためのオプションです。</span><span class="sxs-lookup"><span data-stu-id="b50e2-140">[Kiosk Mode](https://docs.microsoft.com/hololens/hololens-kiosk) and/or [WDAC (Windows Defender Application Control)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) are options for restricting applications.</span></span>

### <span data-ttu-id="b50e2-141">パスワードを管理する方法</span><span class="sxs-lookup"><span data-stu-id="b50e2-141">How to manage passwords</span></span>

1. <span data-ttu-id="b50e2-142">パスワードの有効期限を削除します。</span><span class="sxs-lookup"><span data-stu-id="b50e2-142">Remove password expiration.</span></span> <span data-ttu-id="b50e2-143">ただし、これにより、アカウントが侵害される可能性が高くなっています。</span><span class="sxs-lookup"><span data-stu-id="b50e2-143">However, this increases the chance that that an account will be compromised.</span></span> <span data-ttu-id="b50e2-144">NIST パスワードの推奨事項は、30 ~ 90 日ごとにパスワードを変更する方法です。</span><span class="sxs-lookup"><span data-stu-id="b50e2-144">NIST password recommendation is change passwords every 30-90 days.</span></span>
1. <span data-ttu-id="b50e2-145">HoloLens 2 デバイスのパスワードの有効期限を 90 日を超えるまで延長します。</span><span class="sxs-lookup"><span data-stu-id="b50e2-145">Extend the password expiration for HoloLens 2 devices to exceed 90 days.</span></span>
1. <span data-ttu-id="b50e2-146">パスワードを変更するには、デバイスを Contoso に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b50e2-146">The devices should be returned to Contoso to change the passwords.</span></span> <span data-ttu-id="b50e2-147">ただし、デバイスがクライアントの工場に 90 日以上稼働すると予想される場合は、問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b50e2-147">However, this can cause issues if the devices are expected to be in the client's plant for 90+ days.</span></span>  
1. <span data-ttu-id="b50e2-148">複数のクライアントに送信されるデバイスの場合は、デバイスをクライアントに出荷する前にパスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="b50e2-148">For devices that are sent to multiple clients, reset passwords before shipping the device to clients.</span></span>

### <span data-ttu-id="b50e2-149">クライアントがチャット履歴にアクセスできないか確認する方法</span><span class="sxs-lookup"><span data-stu-id="b50e2-149">How to ensure that clients do not have access to chat history</span></span>

<span data-ttu-id="b50e2-150">リモート アシストは、セッションごとにチャット履歴をクリアします。</span><span class="sxs-lookup"><span data-stu-id="b50e2-150">Remote Assist clears chat history after each session.</span></span> <span data-ttu-id="b50e2-151">ただし、チャット履歴は Microsoft Teams ユーザーが利用できます。</span><span class="sxs-lookup"><span data-stu-id="b50e2-151">However, the chat history will be available for the Microsoft Teams user.</span></span>

> [!NOTE]
> <span data-ttu-id="b50e2-152">シングル サインオンが有効になっているので [**、WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)を使用してブラウザーを無効にすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="b50e2-152">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="b50e2-153">外部クライアントがブラウザーを開き、Web バージョンの Teams を使用する場合、クライアントは通話/チャット履歴にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b50e2-153">If a external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

## <span data-ttu-id="b50e2-154">一般的な展開の推奨事項と手順</span><span class="sxs-lookup"><span data-stu-id="b50e2-154">General Deployment Recommendations and Instructions</span></span>

<span data-ttu-id="b50e2-155">HoloLens 2 の展開手順では、次の手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b50e2-155">We recommend the following for HoloLens 2 deployment Steps:</span></span>

1. <span data-ttu-id="b50e2-156">ベースライン ビルド [として最新の HoloLens OS](https://aka.ms/hololens2download) リリースを使用します。</span><span class="sxs-lookup"><span data-stu-id="b50e2-156">Use the [latest HoloLens OS release](https://aka.ms/hololens2download) as your baseline build.</span></span>
1. <span data-ttu-id="b50e2-157">ユーザー ベースまたはデバイス ベースのライセンスを割り当てる:</span><span class="sxs-lookup"><span data-stu-id="b50e2-157">Assign user-based or device-based licenses:</span></span>
    1. <span data-ttu-id="b50e2-158">ユーザー ベースのライセンスとデバイス ベースのライセンスの両方は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b50e2-158">User-based and device-based licenses both follow the following steps:</span></span>
        1. <span data-ttu-id="b50e2-159">[AAD でグループを作成し](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) 、HoloLens/RA ユーザーのメンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="b50e2-159">[Create a group in AAD and add members](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) for HoloLens/RA users.</span></span>
        1. <span data-ttu-id="b50e2-160">[デバイス ベースまたはユーザー ベースのライセンスをこのグループに割](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) り当てる。</span><span class="sxs-lookup"><span data-stu-id="b50e2-160">[Assign device-based or user-based licenses](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) to this group.</span></span>
        1. <span data-ttu-id="b50e2-161">(省略可能)MDM ポリシーのグループをターゲットにできます。</span><span class="sxs-lookup"><span data-stu-id="b50e2-161">(Optional) You can target groups for MDM policies.</span></span>

1. <span data-ttu-id="b50e2-162">デバイスは、AAD がテナントに参加し、 [自動登録され](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)、自動パイロットによって [構成されている必要があります](https://docs.microsoft.com/hololens/hololens2-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="b50e2-162">Devices should be AAD joined to your tenant, [Auto Enrolled](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm), and configured through [Auto Pilot](https://docs.microsoft.com/hololens/hololens2-autopilot).</span></span>
    1. <span data-ttu-id="b50e2-163">デバイスの最初のユーザーがデバイスの所有者になる点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b50e2-163">Please note that the first user on the device will be the device owner.</span></span>
    1. <span data-ttu-id="b50e2-164">デバイスが AAD に参加している場合、参加を実行したユーザーはデバイス所有者になります。</span><span class="sxs-lookup"><span data-stu-id="b50e2-164">Please note that if the device is AAD joined, the user that performed the join is made device owner.</span></span>
    1. <span data-ttu-id="b50e2-165">詳しくは、「デバイス所有者 [」をご覧ください](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)。</span><span class="sxs-lookup"><span data-stu-id="b50e2-165">For more, see [Device Owner](https://docs.microsoft.com/hololens/security-adminless-os#device-owner).</span></span>
1. <span data-ttu-id="b50e2-166">[テナントが](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) テナントにのみ参加できるよう、デバイスをロックします。</span><span class="sxs-lookup"><span data-stu-id="b50e2-166">[Tenant lock](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) the device so that it can only joined your tenant.</span></span>
    1. <span data-ttu-id="b50e2-167">**追加リンク:** [テナント ロック CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)。</span><span class="sxs-lookup"><span data-stu-id="b50e2-167">**Additional Link:** [Tenant lock CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp).</span></span>
1. <span data-ttu-id="b50e2-168">ここにグローバルに割り当てられたアクセスを使用してキオスクを [構成します](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)。</span><span class="sxs-lookup"><span data-stu-id="b50e2-168">Configure kiosk using global assigned access to [here](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk).</span></span>
1. <span data-ttu-id="b50e2-169">次の (オプション) 機能を無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b50e2-169">We recommend disabling the follow (optional) capabilities:</span></span>
    1. <span data-ttu-id="b50e2-170">ここでデバイスを開発者モードにする [機能](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)。</span><span class="sxs-lookup"><span data-stu-id="b50e2-170">Ability to put the device into developer mode [here](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock).</span></span>
    1. <span data-ttu-id="b50e2-171">日付をコピーするために HoloLens を PC に接続する機能は [、USB を無効にします](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)。</span><span class="sxs-lookup"><span data-stu-id="b50e2-171">Ability to connect the HoloLens to a PC to copy date [disable USB](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).</span></span>
       > [!NOTE]
        > <span data-ttu-id="b50e2-172">USB を無効にしないが、USB を使ってデバイスにプロビジョニング パッケージを適用する機能が必要な場合は、次の手順に従 [**います**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)。</span><span class="sxs-lookup"><span data-stu-id="b50e2-172">If you don’t want to disable USB but want the ability to apply a provisioning package to the device using USB, follow the instructions listed [**here**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage).</span></span>

1. <span data-ttu-id="b50e2-173">[WDAC を使](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)って、HoloLens 2 デバイスでアプリを許可または黒にします。</span><span class="sxs-lookup"><span data-stu-id="b50e2-173">Use [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) to allow or black apps on the HoloLens 2 device.</span></span>
1. <span data-ttu-id="b50e2-174">セットアップの一環として、リモート アシストを最新バージョンに更新します。</span><span class="sxs-lookup"><span data-stu-id="b50e2-174">Update Remote Assist to the latest version as part of the setup.</span></span> <span data-ttu-id="b50e2-175">これを行うには、次の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="b50e2-175">There are two options to do this:</span></span>
    1. <span data-ttu-id="b50e2-176">これは、Windows Microsoft Store **--> Remote Assist --> App にアクセスして行います**。</span><span class="sxs-lookup"><span data-stu-id="b50e2-176">This can be done by going to Windows **Microsoft Store --> Remote Assist --> and Update App**.</span></span>
    1. <span data-ttu-id="b50e2-177">もう 1 つの方法は、自動更新のために HoloLens 2 を夜間に接続したままにしておく方法です。</span><span class="sxs-lookup"><span data-stu-id="b50e2-177">Another method is to leave the HoloLens 2 plugged in overnight for auto update.</span></span>
1. <span data-ttu-id="b50e2-178">[ネットワーク設定以外のすべての設定](https://docs.microsoft.com/hololens/settings-uri-list) ページを無効にして、ユーザーがクライアント サイトのゲスト ネットワークに接続できます。</span><span class="sxs-lookup"><span data-stu-id="b50e2-178">[Disable all settings pages](https://docs.microsoft.com/hololens/settings-uri-list) except the network settings to allow users to connect to guest networks at client sites.</span></span>
1. [<span data-ttu-id="b50e2-179">HoloLens の更新プログラムの管理</span><span class="sxs-lookup"><span data-stu-id="b50e2-179">Manage HoloLens Updates</span></span>](https://docs.microsoft.com/hololens/hololens-updates)
    1. <span data-ttu-id="b50e2-180">OS の更新 [を制御するか、自由](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) にフローを許可するオプション。</span><span class="sxs-lookup"><span data-stu-id="b50e2-180">Option to [control OS updates](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) or allow to flow freely.</span></span>
1. <span data-ttu-id="b50e2-181">[一般的なデバイスの制限](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)。</span><span class="sxs-lookup"><span data-stu-id="b50e2-181">[Common Device Restrictions](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).</span></span>
