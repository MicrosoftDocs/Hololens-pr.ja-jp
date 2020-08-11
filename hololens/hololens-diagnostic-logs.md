---
title: HoloLens デバイスから診断情報を収集する
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
ms.openlocfilehash: b3071c2c66bf1e9c07ba2481b3e22a0d5125bc6d
ms.sourcegitcommit: 8b56f4b9b5f9c928fc361f18efcbea729055a0b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "10919138"
---
# <span data-ttu-id="02229-102">HoloLens デバイスから診断情報を収集する</span><span class="sxs-lookup"><span data-stu-id="02229-102">Collect and use diagnostic information from HoloLens devices</span></span>

<span data-ttu-id="02229-103">HoloLens ユーザーおよび管理者は、HoloLens から診断情報を収集するために、次の4つの異なる方法から選択できます。</span><span class="sxs-lookup"><span data-stu-id="02229-103">HoloLens users and administrators can choose from among four different methods to collect diagnostic information from HoloLens:</span></span>

- <span data-ttu-id="02229-104">フィードバック Hub アプリ</span><span class="sxs-lookup"><span data-stu-id="02229-104">Feedback Hub app</span></span>
- <span data-ttu-id="02229-105">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="02229-105">DiagnosticLog CSP</span></span>
- <span data-ttu-id="02229-106">設定アプリ</span><span class="sxs-lookup"><span data-stu-id="02229-106">Settings app</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="02229-107">デバイスの診断ログには、ユーザーが通常の操作で開始したプロセスやアプリケーションなど、個人を特定できる情報 (PII) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="02229-107">Device diagnostic logs contain personally identifiable information (PII), such as about what processes or applications the user starts during typical operations.</span></span> <span data-ttu-id="02229-108">複数のユーザーが HoloLens デバイスを共有している場合 (たとえば、異なる Microsoft Azure Active Directory (AAD) アカウントを使用して同じデバイスにサインインした場合など)、診断ログには、複数のユーザーに適用される PII 情報が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="02229-108">When multiple users share a HoloLens device (for example, users sign in to the same device by using different Microsoft Azure Active Directory (AAD) accounts) the diagnostic logs may contain PII information that applies to multiple users.</span></span> <span data-ttu-id="02229-109">詳細については、「 [Microsoft のプライバシー](https://privacy.microsoft.com/privacystatement)に関する声明」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02229-109">For more information, see [Microsoft Privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

<span data-ttu-id="02229-110">次の表は、3つのコレクションメソッドを比較したものです。</span><span class="sxs-lookup"><span data-stu-id="02229-110">The following table compares the three collection methods.</span></span> <span data-ttu-id="02229-111">メソッド名は、表の後のセクションの詳細情報にリンクされています。</span><span class="sxs-lookup"><span data-stu-id="02229-111">The method names link to more detailed information in the sections that follow the table.</span></span>

|<span data-ttu-id="02229-112">メソッド</span><span class="sxs-lookup"><span data-stu-id="02229-112">Method</span></span> |<span data-ttu-id="02229-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="02229-113">Prerequisites</span></span> |<span data-ttu-id="02229-114">データの場所</span><span class="sxs-lookup"><span data-stu-id="02229-114">Data locations</span></span> |<span data-ttu-id="02229-115">データアクセスと使用</span><span class="sxs-lookup"><span data-stu-id="02229-115">Data access and use</span></span> |<span data-ttu-id="02229-116">データの保持</span><span class="sxs-lookup"><span data-stu-id="02229-116">Data retention</span></span> |
| --- | --- | --- | --- | --- |
|[<span data-ttu-id="02229-117">フィードバック Hub</span><span class="sxs-lookup"><span data-stu-id="02229-117">Feedback Hub</span></span>](#feedback-hub) |<span data-ttu-id="02229-118">ネットワークとインターネット接続</span><span class="sxs-lookup"><span data-stu-id="02229-118">Network and internet connection</span></span><br /><br /><span data-ttu-id="02229-119">フィードバック Hub アプリ</span><span class="sxs-lookup"><span data-stu-id="02229-119">Feedback Hub app</span></span><br /><br /><span data-ttu-id="02229-120">Microsoft cloud にファイルをアップロードするためのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="02229-120">Permission to upload files to the Microsoft cloud</span></span> |<span data-ttu-id="02229-121">Microsoft cloud</span><span class="sxs-lookup"><span data-stu-id="02229-121">Microsoft cloud</span></span><br /><br /><span data-ttu-id="02229-122">HoloLens デバイス (オプション)</span><span class="sxs-lookup"><span data-stu-id="02229-122">HoloLens device (optional)</span></span> |<span data-ttu-id="02229-123">ユーザーは支援を要求し、使用条件に同意し、データをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="02229-123">User requests assistance, agrees to the terms of use, and uploads the data</span></span><br /><br /><span data-ttu-id="02229-124">Microsoft の従業員は利用規約に従ってデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="02229-124">Microsoft employees view the data, as consistent with the terms of use</span></span> |<span data-ttu-id="02229-125">クラウド内のデータは、Next Generation Privacy (NGP) で定義されている期間保持されます。</span><span class="sxs-lookup"><span data-stu-id="02229-125">Data in the cloud is retained for the period that is defined by Next Generation Privacy (NGP).</span></span> <span data-ttu-id="02229-126">その後、データは自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="02229-126">Then the data is deleted automatically.</span></span><br /><br /><span data-ttu-id="02229-127">デバイス上のデータは、**デバイスの所有者**または**管理者**権限を持つユーザーが、いつでも削除できます。</span><span class="sxs-lookup"><span data-stu-id="02229-127">Data on the device can be deleted at any time by a user who has **Device owner** or **Admin** permissions.</span></span> |
|[<span data-ttu-id="02229-128">設定のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="02229-128">Settings Troubleshooter</span></span>](#settings-troubleshooter) |<span data-ttu-id="02229-129">設定アプリ</span><span class="sxs-lookup"><span data-stu-id="02229-129">Settings app</span></span> |<span data-ttu-id="02229-130">HoloLens デバイス</span><span class="sxs-lookup"><span data-stu-id="02229-130">HoloLens device</span></span><br /><br /><span data-ttu-id="02229-131">接続されているコンピューター (オプション)</span><span class="sxs-lookup"><span data-stu-id="02229-131">Connected computer (optional)</span></span> |<span data-ttu-id="02229-132">ユーザーはデータを保存し、ユーザーだけがデータにアクセスします (ユーザーが別のユーザーとデータを共有していない場合)。</span><span class="sxs-lookup"><span data-stu-id="02229-132">The user stores the data, and only the user accesses the data (unless the user specifically shares the data with another user).</span></span> |<span data-ttu-id="02229-133">データは、ユーザーが削除するまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="02229-133">The data is retained until the user deletes it.\*</span></span> |
|[<span data-ttu-id="02229-134">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="02229-134">DiagnosticLog CSP</span></span>](#diagnosticlog-csp) |<span data-ttu-id="02229-135">ネットワーク接続</span><span class="sxs-lookup"><span data-stu-id="02229-135">Network connection</span></span><br /><br /><span data-ttu-id="02229-136">DiagnosticLog CSP をサポートする MDM 環境</span><span class="sxs-lookup"><span data-stu-id="02229-136">MDM environment that supports the DiagnosticLog CSP</span></span> |<span data-ttu-id="02229-137">管理者が保存場所を構成する</span><span class="sxs-lookup"><span data-stu-id="02229-137">Administrator configures storage locations</span></span> |<span data-ttu-id="02229-138">管理環境では、ユーザーはデータへの管理者アクセス権を暗黙的に同意します。</span><span class="sxs-lookup"><span data-stu-id="02229-138">In the managed environment, the user implicitly consents to administrator access to the data.</span></span><br /><br /><span data-ttu-id="02229-139">管理者がアクセスの役割と権限を構成します。</span><span class="sxs-lookup"><span data-stu-id="02229-139">Administrator configures access roles and permissions.</span></span> | <span data-ttu-id="02229-140">管理者がアイテム保持ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="02229-140">Administrator configures retention policy.</span></span> |
|[<span data-ttu-id="02229-141">オフライン診断</span><span class="sxs-lookup"><span data-stu-id="02229-141">Offline diagnostics</span></span>](#offline-diagnostics) |<span data-ttu-id="02229-142">デバイス構成:</span><span class="sxs-lookup"><span data-stu-id="02229-142">Device configuration:</span></span><ul><li><span data-ttu-id="02229-143">電源が入っていて、コンピュータに接続されています</span><span class="sxs-lookup"><span data-stu-id="02229-143">Powered on and connected to computer</span></span></li><li><span data-ttu-id="02229-144">電源と音量のボタンが機能している</span><span class="sxs-lookup"><span data-stu-id="02229-144">Power and Volume buttons functioning</span></span></li></ul> |<span data-ttu-id="02229-145">HoloLens デバイス</span><span class="sxs-lookup"><span data-stu-id="02229-145">HoloLens device</span></span><br /><br /><span data-ttu-id="02229-146">接続されているコンピューター</span><span class="sxs-lookup"><span data-stu-id="02229-146">Connected computer</span></span> |<span data-ttu-id="02229-147">ユーザーはデータを保存し、ユーザーだけがデータにアクセスします (ユーザーが別のユーザーとデータを共有していない場合)。</span><span class="sxs-lookup"><span data-stu-id="02229-147">The user stores the data, and only the user accesses the data (unless the user specifically shares the data with another user).</span></span> |<span data-ttu-id="02229-148">データは、ユーザーが削除するまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="02229-148">The data is retained until the user deletes it.</span></span> | 


-   <span data-ttu-id="02229-149">エンドユーザーは、ログを他のユーザーと共有する責任を負います。</span><span class="sxs-lookup"><span data-stu-id="02229-149">End-user is responsible for sharing the logs responsibly with someone else.</span></span> <span data-ttu-id="02229-150">これらのファイルは、顧客のサービスとサポートに連絡するときに主に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="02229-150">These files are primarily useful when contacting customer service and support.</span></span>  

## <span data-ttu-id="02229-151">フィードバック Hub</span><span class="sxs-lookup"><span data-stu-id="02229-151">Feedback Hub</span></span>

<span data-ttu-id="02229-152">HoloLens ユーザーは、Microsoft フィードバック Hub デスクトップアプリを使用して、Microsoft サポートに診断情報を送信できます。</span><span class="sxs-lookup"><span data-stu-id="02229-152">A HoloLens user can use the Microsoft Feedback Hub desktop app to send diagnostic information to Microsoft Support.</span></span> <span data-ttu-id="02229-153">詳細と手順については、「[フィードバック](hololens-feedback.md)を送信する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02229-153">For details and complete instructions, see [Give us feedback](hololens-feedback.md).</span></span>  

> [!NOTE]  
> <span data-ttu-id="02229-154">**一般法人向けまたは企業向けのユーザー:**[フィードバック Hub] アプリを使って、MDM、プロビジョニング、その他のデバイス管理の側面に関連する問題を報告する場合は、アプリのカテゴリを [**エンタープライズ管理**  >  **デバイス]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="02229-154">**Commercial or enterprise users:** If you use the Feedback Hub app to report a problem that relates to MDM, provisioning, or any other device management aspect, change the app category to **Enterprise Management** > **Device category**.</span></span>

### <span data-ttu-id="02229-155">前提条件</span><span class="sxs-lookup"><span data-stu-id="02229-155">Prerequisites</span></span>

- <span data-ttu-id="02229-156">デバイスがネットワークに接続されています。</span><span class="sxs-lookup"><span data-stu-id="02229-156">The device is connected to a network.</span></span>
- <span data-ttu-id="02229-157">フィードバック Hub アプリはユーザーのデスクトップコンピューターで利用でき、ユーザーはファイルを Microsoft cloud にアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="02229-157">The Feedback Hub app is available on the user's desktop computer, and the user can upload files to the Microsoft cloud.</span></span>

### <span data-ttu-id="02229-158">データの場所、アクセス、および保持</span><span class="sxs-lookup"><span data-stu-id="02229-158">Data locations, access, and retention</span></span>

<span data-ttu-id="02229-159">フィードバック Hub の利用規約に同意することによって、ユーザーはデータ (その契約で定義されている) の保存と使用について明示的に同意します。</span><span class="sxs-lookup"><span data-stu-id="02229-159">By agreeing to the terms-of-use of the Feedback Hub, the user explicitly consents to the storage and usage of the data (as defined by that agreement).</span></span>

<span data-ttu-id="02229-160">フィードバック Hub には、ユーザーが診断情報を格納するための2つの場所が用意されています。</span><span class="sxs-lookup"><span data-stu-id="02229-160">The Feedback Hub provides two places for the user to store diagnostic information:</span></span>

- <span data-ttu-id="02229-161">**Microsoft cloud**。</span><span class="sxs-lookup"><span data-stu-id="02229-161">**The Microsoft cloud**.</span></span> <span data-ttu-id="02229-162">フィードバック Hub アプリを使用してアップロードされたデータは、次世代のプライバシー (NGP) の要件に準拠している日数に対して保存されます。</span><span class="sxs-lookup"><span data-stu-id="02229-162">Data that the user uploads by using the Feedback Hub app is stored for the number of days that is consistent with Next Generation Privacy (NGP) requirements.</span></span> <span data-ttu-id="02229-163">Microsoft の従業員は、NGP に準拠したビューアーを使用して、この期間中に情報にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="02229-163">Microsoft employees can use an NGP-compliant viewer to access the information during this period.</span></span>
   > [!NOTE]  
   > <span data-ttu-id="02229-164">これらの要件は、すべてのフィードバック Hub カテゴリのデータに適用されます。</span><span class="sxs-lookup"><span data-stu-id="02229-164">These requirements apply to data in all Feedback Hub categories.</span></span>

- <span data-ttu-id="02229-165">**HoloLens デバイス**。</span><span class="sxs-lookup"><span data-stu-id="02229-165">**The HoloLens device**.</span></span> <span data-ttu-id="02229-166">フィードバック Hub でレポートをファイリングしているときに、ユーザーは**フィードバックを送信するときに作成された診断と添付ファイルのローカルコピーを保存**することができます。</span><span class="sxs-lookup"><span data-stu-id="02229-166">While filing a report in Feedback Hub, the user can select **Save a local copy of diagnostics and attachments created when giving feedback**.</span></span> <span data-ttu-id="02229-167">ユーザーがこのオプションを選択した場合、フィードバック Hub には、HoloLens デバイスの診断情報のコピーが格納されます。</span><span class="sxs-lookup"><span data-stu-id="02229-167">If the user selects this option, the Feedback Hub stores a copy of the diagnostic information on the HoloLens device.</span></span> <span data-ttu-id="02229-168">この情報は、ユーザー (またはそのアカウントを使用して HoloLens にサインインしているユーザー) からアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="02229-168">This information remains accessible to the user (or anyone that uses that account to sign in to HoloLens).</span></span> <span data-ttu-id="02229-169">この情報を削除するには、デバイスの**デバイス所有者**または**管理者**のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="02229-169">To delete this information, a user must have **Device owner** or **Admin** permissions on the device.</span></span> <span data-ttu-id="02229-170">適切な権限を持っているユーザーは、フィードバック Hub にサインインし、[**設定**] ビューの [診断ログ] を選択して、情報を削除することができ  >  **View diagnostics logs**ます。</span><span class="sxs-lookup"><span data-stu-id="02229-170">A user who has the appropriate permissions can sign in to the Feedback Hub, select **Settings** > **View diagnostics logs**, and delete the information.</span></span>

## <span data-ttu-id="02229-171">設定のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="02229-171">Settings Troubleshooter</span></span>

<span data-ttu-id="02229-172">HoloLens ユーザーは、デバイス上の設定アプリを使用して、問題のトラブルシューティングや診断情報の収集を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="02229-172">A HoloLens user can use the Settings app on the device to troubleshoot problems and collect diagnostic information.</span></span> <span data-ttu-id="02229-173">これを行うためには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="02229-173">To do this, follow these steps:</span></span>

1. <span data-ttu-id="02229-174">設定アプリを開き、[**更新 & セキュリティ**の  >  **トラブルシューティング**] ページを選択します。</span><span class="sxs-lookup"><span data-stu-id="02229-174">Open the Settings app and select **Update & Security** > **Troubleshoot** page.</span></span>
1. <span data-ttu-id="02229-175">適切な領域を選択し、[**開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="02229-175">Select the appropriate area, and select **Start**.</span></span>
1. <span data-ttu-id="02229-176">問題を再現します。</span><span class="sxs-lookup"><span data-stu-id="02229-176">Reproduce the issue.</span></span>
1. <span data-ttu-id="02229-177">問題を再現した後、[設定] に戻り、[**停止**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="02229-177">After you reproduce the issue, return to Settings and then select **Stop**.</span></span>

### <span data-ttu-id="02229-178">前提条件</span><span class="sxs-lookup"><span data-stu-id="02229-178">Prerequisites</span></span>

- <span data-ttu-id="02229-179">設定アプリはデバイスにインストールされ、ユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="02229-179">The Settings app is installed on the device and is available to the user.</span></span>

### <span data-ttu-id="02229-180">データの場所、アクセス、および保持</span><span class="sxs-lookup"><span data-stu-id="02229-180">Data locations, access, and retention</span></span>

<span data-ttu-id="02229-181">ユーザーはデータ収集を開始するため、診断情報のストレージに暗黙的に同意されます。</span><span class="sxs-lookup"><span data-stu-id="02229-181">Because the user starts the data collection, the user implicitly consents to the storage of the diagnostic information.</span></span> <span data-ttu-id="02229-182">ユーザーのみ、またはユーザーがデータを共有しているすべてのユーザーのみがデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="02229-182">Only the user, or anyone with whom that the user shares the data, can access the data.</span></span>

<span data-ttu-id="02229-183">診断情報はデバイスに格納されます。</span><span class="sxs-lookup"><span data-stu-id="02229-183">The diagnostic information is stored on the device.</span></span> <span data-ttu-id="02229-184">デバイスがユーザーのコンピューターに接続されている場合は、次のファイルにもコンピューター上の情報が存在します。</span><span class="sxs-lookup"><span data-stu-id="02229-184">If the device is connected to the user's computer, the information also resides on the computer in the following file:</span></span>

> <span data-ttu-id="02229-185">この PC\ \ \<*HoloLens device name*> ¥ Internal Storage\\Documents\\Trace \<*ddmmyyhhmmss*></span><span class="sxs-lookup"><span data-stu-id="02229-185">This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents\\Trace\<*ddmmyyhhmmss*>.etl</span></span>

> [!NOTE]  
> <span data-ttu-id="02229-186">このファイルパスと名前は、 \<*HoloLens device name*> HoloLens デバイスの名前を表し、ファイルが \<*ddmmyyhhmmss*> 作成された日付と時刻を表します。</span><span class="sxs-lookup"><span data-stu-id="02229-186">In this file path and name, \<*HoloLens device name*> represents the name of the HoloLens device, and \<*ddmmyyhhmmss*> represents the date and time that the file was created.</span></span>

<span data-ttu-id="02229-187">診断情報は、ユーザーによって削除されるまで、これらの場所に残ります。</span><span class="sxs-lookup"><span data-stu-id="02229-187">The diagnostic information remains in these locations until the user deletes it.</span></span>

## <span data-ttu-id="02229-188">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="02229-188">DiagnosticLog CSP</span></span>

<span data-ttu-id="02229-189">IT 管理者は、モバイルデバイス管理 (MDM) 環境で、 [DiagnosticLog 構成サービスプロバイダー (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp)を使って、登録されている HoloLens デバイスで診断設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="02229-189">In a Mobile Device Management (MDM) environment, the IT administrator can use the the [DiagnosticLog configuration service provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) to configure diagnostic settings on enrolled HoloLens devices.</span></span> <span data-ttu-id="02229-190">IT 管理者は、登録済みデバイスからログを収集するためにこれらの設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="02229-190">The IT administrator can configure these settings to collect logs from enrolled devices.</span></span>

### <span data-ttu-id="02229-191">前提条件</span><span class="sxs-lookup"><span data-stu-id="02229-191">Prerequisites</span></span>

- <span data-ttu-id="02229-192">デバイスがネットワークに接続されています。</span><span class="sxs-lookup"><span data-stu-id="02229-192">The device is connected to a network.</span></span>
- <span data-ttu-id="02229-193">デバイスは、DiagnosticLog CSP をサポートする MDM 環境に登録されます。</span><span class="sxs-lookup"><span data-stu-id="02229-193">The device is enrolled in an MDM environment that supports the DiagnosticLog CSP.</span></span>

### <span data-ttu-id="02229-194">データの場所、アクセス、および保持</span><span class="sxs-lookup"><span data-stu-id="02229-194">Data locations, access, and retention</span></span>

<span data-ttu-id="02229-195">デバイスは管理環境の一部であるため、ユーザーは診断情報への管理アクセスを暗黙的に同意します。</span><span class="sxs-lookup"><span data-stu-id="02229-195">Because the device is part of the managed environment, the user implicitly consents to administrative access to diagnostic information.</span></span>

<span data-ttu-id="02229-196">IT 管理者は、DiagnosticLog CSP を使用して、次のことを管理するポリシーを含む、データストレージ、保持、アクセスポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="02229-196">The IT administrator uses the DiagnosticLog CSP to configure the data storage, retention, and access policies, including the policies that govern the following:</span></span>

- <span data-ttu-id="02229-197">診断情報を格納するクラウドインフラストラクチャ。</span><span class="sxs-lookup"><span data-stu-id="02229-197">The cloud infrastructure that stores the diagnostic information.</span></span>
- <span data-ttu-id="02229-198">診断情報の保持期間。</span><span class="sxs-lookup"><span data-stu-id="02229-198">The retention period for the diagnostic information.</span></span>
- <span data-ttu-id="02229-199">診断情報へのアクセスを制御するアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="02229-199">Permissions that control access to the diagnostic information.</span></span>

## <span data-ttu-id="02229-200">オフライン診断</span><span class="sxs-lookup"><span data-stu-id="02229-200">Offline diagnostics</span></span>
<span data-ttu-id="02229-201">フィードバック Hub またはトラブルシューティングツールを使用して、デバイスで診断を収集できない場合は、診断を手動で収集できます。</span><span class="sxs-lookup"><span data-stu-id="02229-201">In situations where the device is not able to collect diagnostics via Feedback Hub or the Setting Troubleshooter, you can collect diagnostics manually.</span></span> <span data-ttu-id="02229-202">このような状況の1つは、デバイスが Wi-fi に接続できない場合です。</span><span class="sxs-lookup"><span data-stu-id="02229-202">One scenario where this is necessary is when the device cannot connect to Wi-Fi.</span></span> <span data-ttu-id="02229-203">診断は、Microsoft サポートエンジニアが問題を特定するのに役立つデバイスからのクラッシュダンプとログを収集します。</span><span class="sxs-lookup"><span data-stu-id="02229-203">The diagnostics collect crash dumps and logs from the device that help a Microsoft support engineer isolate issues.</span></span>

<span data-ttu-id="02229-204">これは、USB ケーブルを使って PC に接続した後、デバイスがエクスプローラーに表示される場合に有効です。</span><span class="sxs-lookup"><span data-stu-id="02229-204">This works when the device shows up in File Explorer after connecting it to a PC via a USB cable.</span></span> 


> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

<span data-ttu-id="02229-205">診断を収集するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="02229-205">Follow these steps to collect diagnostics:</span></span>
1.  <span data-ttu-id="02229-206">USB ケーブルを使ってデバイスを PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="02229-206">Connect the device with a USB cable to your PC.</span></span>
2.  <span data-ttu-id="02229-207">PC のエクスプローラーで、[**この pc \<hololens-device> \ 内部ストレージ]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="02229-207">In File Explorer on your PC, navigate to **'This PC\<hololens-device>\Internal Storage'**.</span></span>
3.  <span data-ttu-id="02229-208">**内部記憶域**フォルダーが表示されない場合、デバイスはユーザーのサインインを待機しています。</span><span class="sxs-lookup"><span data-stu-id="02229-208">If the **Internal Storage** folder does not show up, the device is waiting for a user to sign in.</span></span> <span data-ttu-id="02229-209">サインインするか、電源ボタンを10秒間押したままにして、デバイスの電源を入れ直します。</span><span class="sxs-lookup"><span data-stu-id="02229-209">Either sign-in or power cycle the device by holding the POWER button down for 10 seconds.</span></span>
4.  <span data-ttu-id="02229-210">**POWER + ボリュームの下矢印**を同時に押します。</span><span class="sxs-lookup"><span data-stu-id="02229-210">Press and immediately release the **POWER + VOLUME DOWN** buttons together.</span></span>
5.  <span data-ttu-id="02229-211">デバイスが zip アーカイブを準備できるようになるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="02229-211">Wait a minute for the device to prepare the zip archives.</span></span> <span data-ttu-id="02229-212">(HololensDiagnostics という名前の一時ファイルが、デバイスで zip アーカイブが生成されている間に表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="02229-212">(A temporary file named HololensDiagnostics.temp may become visible while the device generates the zip archives.</span></span> <span data-ttu-id="02229-213">このファイルにアクセスしたり、保存したりしないでください。</span><span class="sxs-lookup"><span data-stu-id="02229-213">Do not access or save that file.</span></span> <span data-ttu-id="02229-214">プロセスが完了すると、zip アーカイブに置き換わります。)</span><span class="sxs-lookup"><span data-stu-id="02229-214">When the process finishes it will be replaced by the zip archives.)</span></span>
6.  <span data-ttu-id="02229-215">エクスプローラーを更新して、[ **\Documents]** フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="02229-215">Refresh file explorer, and navigate to the **'\Documents'** folder.</span></span>
7.  <span data-ttu-id="02229-216">診断 ZIP ファイルをコピーして、Microsoft サポートチームと共有します。</span><span class="sxs-lookup"><span data-stu-id="02229-216">Copy the diagnostics ZIP files and share them with the Microsoft support team.</span></span>

<span data-ttu-id="02229-217">注: 一部の diagnostics の ZIP ファイルには、個人情報が含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="02229-217">Note, some of the diagnostics ZIP files may contain personally identifiable information.</span></span>

