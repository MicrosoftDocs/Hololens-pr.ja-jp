---
title: HoloLens デバイスから診断情報を収集して使用する
description: ''
author: Teresa-Motiv
ms.author: v-tea
ms.date: 03/23/2020
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.custom:
- CI 115131
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f11128c66845f0e062a006855fd75ca66ffc4e5e
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829264"
---
# <span data-ttu-id="52a25-102">HoloLens デバイスから診断情報を収集して使用する</span><span class="sxs-lookup"><span data-stu-id="52a25-102">Collect and use diagnostic information from HoloLens devices</span></span>

<span data-ttu-id="52a25-103">HoloLens ユーザーおよび管理者は、HoloLens から診断情報を収集するために、次の4つの異なる方法から選択できます。</span><span class="sxs-lookup"><span data-stu-id="52a25-103">HoloLens users and administrators can choose from among four different methods to collect diagnostic information from HoloLens:</span></span>

- <span data-ttu-id="52a25-104">フィードバック Hub アプリ</span><span class="sxs-lookup"><span data-stu-id="52a25-104">Feedback Hub app</span></span>
- <span data-ttu-id="52a25-105">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="52a25-105">DiagnosticLog CSP</span></span>
- <span data-ttu-id="52a25-106">設定アプリ</span><span class="sxs-lookup"><span data-stu-id="52a25-106">Settings app</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="52a25-107">デバイスの診断ログには、ユーザーが通常の操作で開始したプロセスやアプリケーションなど、個人を特定できる情報 (PII) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="52a25-107">Device diagnostic logs contain personally identifiable information (PII), such as about what processes or applications the user starts during typical operations.</span></span> <span data-ttu-id="52a25-108">複数のユーザーが HoloLens デバイスを共有している場合 (たとえば、異なる Microsoft Azure Active Directory (AAD) アカウントを使用して同じデバイスにサインインした場合など)、診断ログには、複数のユーザーに適用される PII 情報が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="52a25-108">When multiple users share a HoloLens device (for example, users sign in to the same device by using different Microsoft Azure Active Directory (AAD) accounts) the diagnostic logs may contain PII information that applies to multiple users.</span></span> <span data-ttu-id="52a25-109">詳細については、「 [Microsoft のプライバシー](https://privacy.microsoft.com/privacystatement)に関する声明」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52a25-109">For more information, see [Microsoft Privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

<span data-ttu-id="52a25-110">次の表は、3つのコレクションメソッドを比較したものです。</span><span class="sxs-lookup"><span data-stu-id="52a25-110">The following table compares the three collection methods.</span></span> <span data-ttu-id="52a25-111">メソッド名は、表の後のセクションの詳細情報にリンクされています。</span><span class="sxs-lookup"><span data-stu-id="52a25-111">The method names link to more detailed information in the sections that follow the table.</span></span>

|<span data-ttu-id="52a25-112">メソッド</span><span class="sxs-lookup"><span data-stu-id="52a25-112">Method</span></span> |<span data-ttu-id="52a25-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="52a25-113">Prerequisites</span></span> |<span data-ttu-id="52a25-114">データの場所</span><span class="sxs-lookup"><span data-stu-id="52a25-114">Data locations</span></span> |<span data-ttu-id="52a25-115">データアクセスと使用</span><span class="sxs-lookup"><span data-stu-id="52a25-115">Data access and use</span></span> |<span data-ttu-id="52a25-116">データの保持</span><span class="sxs-lookup"><span data-stu-id="52a25-116">Data retention</span></span> |
| --- | --- | --- | --- | --- |
|[<span data-ttu-id="52a25-117">フィードバック Hub</span><span class="sxs-lookup"><span data-stu-id="52a25-117">Feedback Hub</span></span>](#feedback-hub) |<span data-ttu-id="52a25-118">ネットワークとインターネット接続</span><span class="sxs-lookup"><span data-stu-id="52a25-118">Network and internet connection</span></span><br /><br /><span data-ttu-id="52a25-119">フィードバック Hub アプリ</span><span class="sxs-lookup"><span data-stu-id="52a25-119">Feedback Hub app</span></span><br /><br /><span data-ttu-id="52a25-120">Microsoft cloud にファイルをアップロードするためのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="52a25-120">Permission to upload files to the Microsoft cloud</span></span> |<span data-ttu-id="52a25-121">Microsoft cloud</span><span class="sxs-lookup"><span data-stu-id="52a25-121">Microsoft cloud</span></span><br /><br /><span data-ttu-id="52a25-122">HoloLens デバイス (オプション)</span><span class="sxs-lookup"><span data-stu-id="52a25-122">HoloLens device (optional)</span></span> |<span data-ttu-id="52a25-123">ユーザーは支援を要求し、使用条件に同意し、データをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="52a25-123">User requests assistance, agrees to the terms of use, and uploads the data</span></span><br /><br /><span data-ttu-id="52a25-124">Microsoft の従業員は利用規約に従ってデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="52a25-124">Microsoft employees view the data, as consistent with the terms of use</span></span> |<span data-ttu-id="52a25-125">クラウド内のデータは、Next Generation Privacy (NGP) で定義されている期間保持されます。</span><span class="sxs-lookup"><span data-stu-id="52a25-125">Data in the cloud is retained for the period that is defined by Next Generation Privacy (NGP).</span></span> <span data-ttu-id="52a25-126">その後、データは自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="52a25-126">Then the data is deleted automatically.</span></span><br /><br /><span data-ttu-id="52a25-127">デバイス上のデータは、**デバイスの所有者**または**管理者**権限を持つユーザーが、いつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="52a25-127">Data on the device can be deleted at any time by a user who has **Device owner** or **Admin** permissions.</span></span> |
|[<span data-ttu-id="52a25-128">設定のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="52a25-128">Settings Troubleshooter</span></span>](#settings-troubleshooter) |<span data-ttu-id="52a25-129">設定アプリ</span><span class="sxs-lookup"><span data-stu-id="52a25-129">Settings app</span></span> |<span data-ttu-id="52a25-130">HoloLens デバイス</span><span class="sxs-lookup"><span data-stu-id="52a25-130">HoloLens device</span></span><br /><br /><span data-ttu-id="52a25-131">接続されているコンピューター (オプション)</span><span class="sxs-lookup"><span data-stu-id="52a25-131">Connected computer (optional)</span></span> |<span data-ttu-id="52a25-132">ユーザーはデータを保存し、ユーザーだけがデータにアクセスします (ユーザーが別のユーザーとデータを共有していない場合)。</span><span class="sxs-lookup"><span data-stu-id="52a25-132">The user stores the data, and only the user accesses the data (unless the user specifically shares the data with another user).</span></span> |<span data-ttu-id="52a25-133">データは、ユーザーが削除するまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="52a25-133">The data is retained until the user deletes it.\*</span></span> |
|[<span data-ttu-id="52a25-134">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="52a25-134">DiagnosticLog CSP</span></span>](#diagnosticlog-csp) |<span data-ttu-id="52a25-135">ネットワーク接続</span><span class="sxs-lookup"><span data-stu-id="52a25-135">Network connection</span></span><br /><br /><span data-ttu-id="52a25-136">DiagnosticLog CSP をサポートする MDM 環境</span><span class="sxs-lookup"><span data-stu-id="52a25-136">MDM environment that supports the DiagnosticLog CSP</span></span> |<span data-ttu-id="52a25-137">管理者が保存場所を構成する</span><span class="sxs-lookup"><span data-stu-id="52a25-137">Administrator configures storage locations</span></span> |<span data-ttu-id="52a25-138">管理環境では、ユーザーはデータへの管理者アクセス権を暗黙的に同意します。</span><span class="sxs-lookup"><span data-stu-id="52a25-138">In the managed environment, the user implicitly consents to administrator access to the data.</span></span><br /><br /><span data-ttu-id="52a25-139">管理者がアクセスの役割と権限を構成します。</span><span class="sxs-lookup"><span data-stu-id="52a25-139">Administrator configures access roles and permissions.</span></span> | <span data-ttu-id="52a25-140">管理者がアイテム保持ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="52a25-140">Administrator configures retention policy.</span></span> |


-   <span data-ttu-id="52a25-141">エンドユーザーは、ログを他のユーザーと共有する責任を負います。</span><span class="sxs-lookup"><span data-stu-id="52a25-141">End-user is responsible for sharing the logs responsibly with someone else.</span></span> <span data-ttu-id="52a25-142">これらのファイルは、顧客のサービスとサポートに連絡するときに主に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="52a25-142">These files are primarily useful when contacting customer service and support.</span></span>  

## <span data-ttu-id="52a25-143">フィードバック Hub</span><span class="sxs-lookup"><span data-stu-id="52a25-143">Feedback Hub</span></span>

<span data-ttu-id="52a25-144">HoloLens ユーザーは、Microsoft フィードバック Hub デスクトップアプリを使用して、Microsoft サポートに診断情報を送信できます。</span><span class="sxs-lookup"><span data-stu-id="52a25-144">A HoloLens user can use the Microsoft Feedback Hub desktop app to send diagnostic information to Microsoft Support.</span></span> <span data-ttu-id="52a25-145">詳細と手順については、「[フィードバック](hololens-feedback.md)を送信する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52a25-145">For details and complete instructions, see [Give us feedback](hololens-feedback.md).</span></span>  

> [!NOTE]  
> <span data-ttu-id="52a25-146">**一般法人向けまたは企業向けのユーザー:**[フィードバック Hub] アプリを使って、MDM、プロビジョニング、その他のデバイス管理の側面に関連する問題を報告する場合は、アプリのカテゴリを [**エンタープライズ管理**  >  **デバイス]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="52a25-146">**Commercial or enterprise users:** If you use the Feedback Hub app to report a problem that relates to MDM, provisioning, or any other device management aspect, change the app category to **Enterprise Management** > **Device category**.</span></span>

### <span data-ttu-id="52a25-147">前提条件</span><span class="sxs-lookup"><span data-stu-id="52a25-147">Prerequisites</span></span>

- <span data-ttu-id="52a25-148">デバイスがネットワークに接続されています。</span><span class="sxs-lookup"><span data-stu-id="52a25-148">The device is connected to a network.</span></span>
- <span data-ttu-id="52a25-149">フィードバック Hub アプリはユーザーのデスクトップコンピューターで利用でき、ユーザーはファイルを Microsoft cloud にアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="52a25-149">The Feedback Hub app is available on the user's desktop computer, and the user can upload files to the Microsoft cloud.</span></span>

### <span data-ttu-id="52a25-150">データの場所、アクセス、および保持</span><span class="sxs-lookup"><span data-stu-id="52a25-150">Data locations, access, and retention</span></span>

<span data-ttu-id="52a25-151">フィードバック Hub の利用規約に同意することによって、ユーザーはデータ (その契約で定義されている) の保存と使用について明示的に同意します。</span><span class="sxs-lookup"><span data-stu-id="52a25-151">By agreeing to the terms-of-use of the Feedback Hub, the user explicitly consents to the storage and usage of the data (as defined by that agreement).</span></span>

<span data-ttu-id="52a25-152">フィードバック Hub には、ユーザーが診断情報を格納するための2つの場所が用意されています。</span><span class="sxs-lookup"><span data-stu-id="52a25-152">The Feedback Hub provides two places for the user to store diagnostic information:</span></span>

- <span data-ttu-id="52a25-153">**Microsoft cloud**。</span><span class="sxs-lookup"><span data-stu-id="52a25-153">**The Microsoft cloud**.</span></span> <span data-ttu-id="52a25-154">フィードバック Hub アプリを使用してアップロードされたデータは、次世代のプライバシー (NGP) の要件に準拠している日数に対して保存されます。</span><span class="sxs-lookup"><span data-stu-id="52a25-154">Data that the user uploads by using the Feedback Hub app is stored for the number of days that is consistent with Next Generation Privacy (NGP) requirements.</span></span> <span data-ttu-id="52a25-155">Microsoft の従業員は、NGP に準拠したビューアーを使用して、この期間中に情報にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="52a25-155">Microsoft employees can use an NGP-compliant viewer to access the information during this period.</span></span>
   > [!NOTE]  
   > <span data-ttu-id="52a25-156">これらの要件は、すべてのフィードバック Hub カテゴリのデータに適用されます。</span><span class="sxs-lookup"><span data-stu-id="52a25-156">These requirements apply to data in all Feedback Hub categories.</span></span>

- <span data-ttu-id="52a25-157">**HoloLens デバイス**。</span><span class="sxs-lookup"><span data-stu-id="52a25-157">**The HoloLens device**.</span></span> <span data-ttu-id="52a25-158">フィードバック Hub でレポートをファイリングしているときに、ユーザーは**フィードバックを送信するときに作成された診断と添付ファイルのローカルコピーを保存**することができます。</span><span class="sxs-lookup"><span data-stu-id="52a25-158">While filing a report in Feedback Hub, the user can select **Save a local copy of diagnostics and attachments created when giving feedback**.</span></span> <span data-ttu-id="52a25-159">ユーザーがこのオプションを選択した場合、フィードバック Hub には、HoloLens デバイスの診断情報のコピーが格納されます。</span><span class="sxs-lookup"><span data-stu-id="52a25-159">If the user selects this option, the Feedback Hub stores a copy of the diagnostic information on the HoloLens device.</span></span> <span data-ttu-id="52a25-160">この情報は、ユーザー (またはそのアカウントを使用して HoloLens にサインインしているユーザー) からアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="52a25-160">This information remains accessible to the user (or anyone that uses that account to sign in to HoloLens).</span></span> <span data-ttu-id="52a25-161">この情報を削除するには、デバイスの**デバイス所有者**または**管理者**のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="52a25-161">To delete this information, a user must have **Device owner** or **Admin** permissions on the device.</span></span> <span data-ttu-id="52a25-162">適切な権限を持っているユーザーは、フィードバック Hub にサインインし、[**設定**] ビューの [診断ログ] を選択して、情報を削除することができ  >  **View diagnostics logs**ます。</span><span class="sxs-lookup"><span data-stu-id="52a25-162">A user who has the appropriate permissions can sign in to the Feedback Hub, select **Settings** > **View diagnostics logs**, and delete the information.</span></span>

## <span data-ttu-id="52a25-163">設定のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="52a25-163">Settings Troubleshooter</span></span>

<span data-ttu-id="52a25-164">HoloLens ユーザーは、デバイス上の設定アプリを使用して、問題のトラブルシューティングや診断情報の収集を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="52a25-164">A HoloLens user can use the Settings app on the device to troubleshoot problems and collect diagnostic information.</span></span> <span data-ttu-id="52a25-165">これを行うには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="52a25-165">To do this, follow these steps:</span></span>

1. <span data-ttu-id="52a25-166">設定アプリを開き、[**更新 & セキュリティ**の  >  **トラブルシューティング**] ページを選択します。</span><span class="sxs-lookup"><span data-stu-id="52a25-166">Open the Settings app and select **Update & Security** > **Troubleshoot** page.</span></span>
1. <span data-ttu-id="52a25-167">適切な領域を選択し、[**開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="52a25-167">Select the appropriate area, and select **Start**.</span></span>
1. <span data-ttu-id="52a25-168">問題を再現します。</span><span class="sxs-lookup"><span data-stu-id="52a25-168">Reproduce the issue.</span></span>
1. <span data-ttu-id="52a25-169">問題を再現した後、[設定] に戻り、[**停止**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="52a25-169">After you reproduce the issue, return to Settings and then select **Stop**.</span></span>

### <span data-ttu-id="52a25-170">前提条件</span><span class="sxs-lookup"><span data-stu-id="52a25-170">Prerequisites</span></span>

- <span data-ttu-id="52a25-171">設定アプリはデバイスにインストールされ、ユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="52a25-171">The Settings app is installed on the device and is available to the user.</span></span>

### <span data-ttu-id="52a25-172">データの場所、アクセス、および保持</span><span class="sxs-lookup"><span data-stu-id="52a25-172">Data locations, access, and retention</span></span>

<span data-ttu-id="52a25-173">ユーザーはデータ収集を開始するため、診断情報のストレージに暗黙的に同意されます。</span><span class="sxs-lookup"><span data-stu-id="52a25-173">Because the user starts the data collection, the user implicitly consents to the storage of the diagnostic information.</span></span> <span data-ttu-id="52a25-174">ユーザーのみ、またはユーザーがデータを共有しているすべてのユーザーのみがデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="52a25-174">Only the user, or anyone with whom that the user shares the data, can access the data.</span></span>

<span data-ttu-id="52a25-175">診断情報はデバイスに格納されます。</span><span class="sxs-lookup"><span data-stu-id="52a25-175">The diagnostic information is stored on the device.</span></span> <span data-ttu-id="52a25-176">デバイスがユーザーのコンピューターに接続されている場合は、次のファイルにもコンピューター上の情報が存在します。</span><span class="sxs-lookup"><span data-stu-id="52a25-176">If the device is connected to the user's computer, the information also resides on the computer in the following file:</span></span>

> <span data-ttu-id="52a25-177">この PC\ \ \<*HoloLens device name*> ¥ Internal Storage\\Documents\\Trace \<*ddmmyyhhmmss*></span><span class="sxs-lookup"><span data-stu-id="52a25-177">This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents\\Trace\<*ddmmyyhhmmss*>.etl</span></span>

> [!NOTE]  
> <span data-ttu-id="52a25-178">このファイルパスと名前は、 \<*HoloLens device name*> HoloLens デバイスの名前を表し、ファイルが \<*ddmmyyhhmmss*> 作成された日付と時刻を表します。</span><span class="sxs-lookup"><span data-stu-id="52a25-178">In this file path and name, \<*HoloLens device name*> represents the name of the HoloLens device, and \<*ddmmyyhhmmss*> represents the date and time that the file was created.</span></span>

<span data-ttu-id="52a25-179">診断情報は、ユーザーによって削除されるまで、これらの場所に残ります。</span><span class="sxs-lookup"><span data-stu-id="52a25-179">The diagnostic information remains in these locations until the user deletes it.</span></span>

## <span data-ttu-id="52a25-180">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="52a25-180">DiagnosticLog CSP</span></span>

<span data-ttu-id="52a25-181">IT 管理者は、モバイルデバイス管理 (MDM) 環境で、 [DiagnosticLog 構成サービスプロバイダー (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp)を使って、登録されている HoloLens デバイスで診断設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="52a25-181">In a Mobile Device Management (MDM) environment, the IT administrator can use the the [DiagnosticLog configuration service provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) to configure diagnostic settings on enrolled HoloLens devices.</span></span> <span data-ttu-id="52a25-182">IT 管理者は、登録済みデバイスからログを収集するためにこれらの設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="52a25-182">The IT administrator can configure these settings to collect logs from enrolled devices.</span></span>

### <span data-ttu-id="52a25-183">前提条件</span><span class="sxs-lookup"><span data-stu-id="52a25-183">Prerequisites</span></span>

- <span data-ttu-id="52a25-184">デバイスがネットワークに接続されています。</span><span class="sxs-lookup"><span data-stu-id="52a25-184">The device is connected to a network.</span></span>
- <span data-ttu-id="52a25-185">デバイスは、DiagnosticLog CSP をサポートする MDM 環境に登録されます。</span><span class="sxs-lookup"><span data-stu-id="52a25-185">The device is enrolled in an MDM environment that supports the DiagnosticLog CSP.</span></span>

### <span data-ttu-id="52a25-186">データの場所、アクセス、および保持</span><span class="sxs-lookup"><span data-stu-id="52a25-186">Data locations, access, and retention</span></span>

<span data-ttu-id="52a25-187">デバイスは管理環境の一部であるため、ユーザーは診断情報への管理アクセスを暗黙的に同意します。</span><span class="sxs-lookup"><span data-stu-id="52a25-187">Because the device is part of the managed environment, the user implicitly consents to administrative access to diagnostic information.</span></span>

<span data-ttu-id="52a25-188">IT 管理者は、DiagnosticLog CSP を使用して、次のことを管理するポリシーを含む、データストレージ、保持、アクセスポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="52a25-188">The IT administrator uses the DiagnosticLog CSP to configure the data storage, retention, and access policies, including the policies that govern the following:</span></span>

- <span data-ttu-id="52a25-189">診断情報を格納するクラウドインフラストラクチャ。</span><span class="sxs-lookup"><span data-stu-id="52a25-189">The cloud infrastructure that stores the diagnostic information.</span></span>
- <span data-ttu-id="52a25-190">診断情報の保持期間。</span><span class="sxs-lookup"><span data-stu-id="52a25-190">The retention period for the diagnostic information.</span></span>
- <span data-ttu-id="52a25-191">診断情報へのアクセスを制御するアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="52a25-191">Permissions that control access to the diagnostic information.</span></span>


