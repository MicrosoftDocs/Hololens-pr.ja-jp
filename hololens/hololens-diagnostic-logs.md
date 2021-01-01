---
title: HoloLens デバイスから診断情報を収集する
description: HoloLens デバイスから診断情報を収集する
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/15/2020
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
ms.openlocfilehash: 24f9fc142581de5017e498b2c4591cdb8f79d533
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253154"
---
# <span data-ttu-id="fa600-103">HoloLens デバイスから診断情報を収集する</span><span class="sxs-lookup"><span data-stu-id="fa600-103">Collect and use diagnostic information from HoloLens devices</span></span>

<span data-ttu-id="fa600-104">HoloLens のユーザーと管理者は、HoloLens から診断情報を収集する次の 4 つの方法から選択できます。</span><span class="sxs-lookup"><span data-stu-id="fa600-104">HoloLens users and administrators can choose from among four different methods to collect diagnostic information from HoloLens:</span></span>

- <span data-ttu-id="fa600-105">フィードバック Hub アプリ</span><span class="sxs-lookup"><span data-stu-id="fa600-105">Feedback Hub app</span></span>
- <span data-ttu-id="fa600-106">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="fa600-106">DiagnosticLog CSP</span></span>
- <span data-ttu-id="fa600-107">設定アプリ</span><span class="sxs-lookup"><span data-stu-id="fa600-107">Settings app</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="fa600-108">デバイス診断ログには、ユーザーが一般的な操作中に開始するプロセスやアプリケーションなど、個人を特定できる情報 (PII) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fa600-108">Device diagnostic logs contain personally identifiable information (PII), such as about what processes or applications the user starts during typical operations.</span></span> <span data-ttu-id="fa600-109">複数のユーザーが HoloLens デバイスを共有する場合 (たとえば、ユーザーが異なる Microsoft Azure Active Directory (Azure AD) アカウントを使用して同じデバイスにサインインする場合)、診断ログには複数のユーザーに適用される PII 情報が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fa600-109">When multiple users share a HoloLens device (for example, users sign in to the same device by using different Microsoft Azure Active Directory (Azure AD) accounts) the diagnostic logs may contain PII information that applies to multiple users.</span></span> <span data-ttu-id="fa600-110">詳細については、Microsoft のプライバシー [に関する声明を参照してください](https://privacy.microsoft.com/privacystatement)。</span><span class="sxs-lookup"><span data-stu-id="fa600-110">For more information, see [Microsoft Privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

<span data-ttu-id="fa600-111">次の表は、3 つのコレクション メソッドを比較しています。</span><span class="sxs-lookup"><span data-stu-id="fa600-111">The following table compares the three collection methods.</span></span> <span data-ttu-id="fa600-112">メソッド名は、表に続くセクションの詳細な情報にリンクしています。</span><span class="sxs-lookup"><span data-stu-id="fa600-112">The method names link to more detailed information in the sections that follow the table.</span></span>

|<span data-ttu-id="fa600-113">メソッド</span><span class="sxs-lookup"><span data-stu-id="fa600-113">Method</span></span> |<span data-ttu-id="fa600-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="fa600-114">Prerequisites</span></span> |<span data-ttu-id="fa600-115">データの場所</span><span class="sxs-lookup"><span data-stu-id="fa600-115">Data locations</span></span> |<span data-ttu-id="fa600-116">データ アクセスと使用</span><span class="sxs-lookup"><span data-stu-id="fa600-116">Data access and use</span></span> |<span data-ttu-id="fa600-117">データの保持</span><span class="sxs-lookup"><span data-stu-id="fa600-117">Data retention</span></span> |
| --- | --- | --- | --- | --- |
|[<span data-ttu-id="fa600-118">フィードバック Hub</span><span class="sxs-lookup"><span data-stu-id="fa600-118">Feedback Hub</span></span>](#feedback-hub) |<span data-ttu-id="fa600-119">ネットワークとインターネット接続</span><span class="sxs-lookup"><span data-stu-id="fa600-119">Network and internet connection</span></span><br /><br /><span data-ttu-id="fa600-120">フィードバック Hub アプリ</span><span class="sxs-lookup"><span data-stu-id="fa600-120">Feedback Hub app</span></span><br /><br /><span data-ttu-id="fa600-121">Microsoft クラウドにファイルをアップロードするためのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="fa600-121">Permission to upload files to the Microsoft cloud</span></span> |<span data-ttu-id="fa600-122">Microsoft クラウド</span><span class="sxs-lookup"><span data-stu-id="fa600-122">Microsoft cloud</span></span><br /><br /><span data-ttu-id="fa600-123">HoloLens デバイス (オプション)</span><span class="sxs-lookup"><span data-stu-id="fa600-123">HoloLens device (optional)</span></span> |<span data-ttu-id="fa600-124">ユーザーが支援を要求し、利用規約に同意し、データをアップロードする</span><span class="sxs-lookup"><span data-stu-id="fa600-124">User requests assistance, agrees to the terms of use, and uploads the data</span></span><br /><br /><span data-ttu-id="fa600-125">Microsoft の従業員は、使用条件と一致するデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="fa600-125">Microsoft employees view the data, as consistent with the terms of use</span></span> |<span data-ttu-id="fa600-126">クラウド内のデータは、次世代プライバシー (NGP) で定義されている期間保持されます。</span><span class="sxs-lookup"><span data-stu-id="fa600-126">Data in the cloud is retained for the period that is defined by Next Generation Privacy (NGP).</span></span> <span data-ttu-id="fa600-127">その後、データは自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="fa600-127">Then the data is deleted automatically.</span></span><br /><br /><span data-ttu-id="fa600-128">デバイスの所有者または管理者のアクセス許可を持つユーザーは、デバイス上\*\*\*\* のデータを**いつでも**削除できます。</span><span class="sxs-lookup"><span data-stu-id="fa600-128">Data on the device can be deleted at any time by a user who has **Device owner** or **Admin** permissions.</span></span> |
|[<span data-ttu-id="fa600-129">設定のトラブルシューティング ツール</span><span class="sxs-lookup"><span data-stu-id="fa600-129">Settings Troubleshooter</span></span>](#settings-troubleshooter) |<span data-ttu-id="fa600-130">設定アプリ</span><span class="sxs-lookup"><span data-stu-id="fa600-130">Settings app</span></span> |<span data-ttu-id="fa600-131">HoloLens デバイス</span><span class="sxs-lookup"><span data-stu-id="fa600-131">HoloLens device</span></span><br /><br /><span data-ttu-id="fa600-132">接続されたコンピューター (オプション)</span><span class="sxs-lookup"><span data-stu-id="fa600-132">Connected computer (optional)</span></span> |<span data-ttu-id="fa600-133">ユーザーはデータを保存し、ユーザーだけがデータにアクセスします (ユーザーがデータを別のユーザーと特に共有しない場合)。</span><span class="sxs-lookup"><span data-stu-id="fa600-133">The user stores the data, and only the user accesses the data (unless the user specifically shares the data with another user).</span></span> |<span data-ttu-id="fa600-134">データは、ユーザーが削除するまで保持されます。\*</span><span class="sxs-lookup"><span data-stu-id="fa600-134">The data is retained until the user deletes it.\*</span></span> |
|[<span data-ttu-id="fa600-135">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="fa600-135">DiagnosticLog CSP</span></span>](#diagnosticlog-csp) |<span data-ttu-id="fa600-136">ネットワーク接続</span><span class="sxs-lookup"><span data-stu-id="fa600-136">Network connection</span></span><br /><br /><span data-ttu-id="fa600-137">DiagnosticLog CSP をサポートする MDM 環境</span><span class="sxs-lookup"><span data-stu-id="fa600-137">MDM environment that supports the DiagnosticLog CSP</span></span> |<span data-ttu-id="fa600-138">管理者が保存場所を構成する</span><span class="sxs-lookup"><span data-stu-id="fa600-138">Administrator configures storage locations</span></span> |<span data-ttu-id="fa600-139">管理環境では、ユーザーはデータへの管理者アクセスに暗黙的に同意します。</span><span class="sxs-lookup"><span data-stu-id="fa600-139">In the managed environment, the user implicitly consents to administrator access to the data.</span></span><br /><br /><span data-ttu-id="fa600-140">管理者は、アクセス ロールとアクセス許可を構成します。</span><span class="sxs-lookup"><span data-stu-id="fa600-140">Administrator configures access roles and permissions.</span></span> | <span data-ttu-id="fa600-141">管理者がアイテム保持ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="fa600-141">Administrator configures retention policy.</span></span> |
|[<span data-ttu-id="fa600-142">オフライン診断</span><span class="sxs-lookup"><span data-stu-id="fa600-142">Offline diagnostics</span></span>](#offline-diagnostics) |<span data-ttu-id="fa600-143">デバイス構成:</span><span class="sxs-lookup"><span data-stu-id="fa600-143">Device configuration:</span></span><ul><li><span data-ttu-id="fa600-144">電源をオンにし、コンピューターに接続する</span><span class="sxs-lookup"><span data-stu-id="fa600-144">Powered on and connected to computer</span></span></li><li><span data-ttu-id="fa600-145">電源ボタンと音量ボタンが機能している</span><span class="sxs-lookup"><span data-stu-id="fa600-145">Power and Volume buttons functioning</span></span></li></ul> |<span data-ttu-id="fa600-146">HoloLens デバイス</span><span class="sxs-lookup"><span data-stu-id="fa600-146">HoloLens device</span></span><br /><br /><span data-ttu-id="fa600-147">接続されたコンピューター</span><span class="sxs-lookup"><span data-stu-id="fa600-147">Connected computer</span></span> |<span data-ttu-id="fa600-148">ユーザーはデータを保存し、ユーザーだけがデータにアクセスします (ユーザーがデータを別のユーザーと特に共有しない場合)。</span><span class="sxs-lookup"><span data-stu-id="fa600-148">The user stores the data, and only the user accesses the data (unless the user specifically shares the data with another user).</span></span> |<span data-ttu-id="fa600-149">データは、ユーザーが削除するまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="fa600-149">The data is retained until the user deletes it.</span></span> | 


-   <span data-ttu-id="fa600-150">エンド ユーザーは、責任を持って他のユーザーとログを共有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa600-150">End-user is responsible for sharing the logs responsibly with someone else.</span></span> <span data-ttu-id="fa600-151">これらのファイルは、主にカスタマー サービスとサポートに問い合わせするときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fa600-151">These files are primarily useful when contacting customer service and support.</span></span>  

## <span data-ttu-id="fa600-152">フィードバック Hub</span><span class="sxs-lookup"><span data-stu-id="fa600-152">Feedback Hub</span></span>

<span data-ttu-id="fa600-153">HoloLens ユーザーは、Microsoft フィードバック Hub デスクトップ アプリを使用して、Microsoft サポートに診断情報を送信できます。</span><span class="sxs-lookup"><span data-stu-id="fa600-153">A HoloLens user can use the Microsoft Feedback Hub desktop app to send diagnostic information to Microsoft Support.</span></span> <span data-ttu-id="fa600-154">詳細と完全な手順については、「フィードバックをお寄せください [」を参照してください](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="fa600-154">For details and complete instructions, see [Give us feedback](hololens-feedback.md).</span></span>  

> [!NOTE]  
> <span data-ttu-id="fa600-155">**商用ユーザーまたはエンタープライズ ユーザー:** フィードバック Hub アプリを使って、MDM、プロビジョニング、その他のデバイス管理の側面に関連する問題を報告する場合は、アプリカテゴリを**Enterprise Management**Device カテゴリに変更  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="fa600-155">**Commercial or enterprise users:** If you use the Feedback Hub app to report a problem that relates to MDM, provisioning, or any other device management aspect, change the app category to **Enterprise Management** > **Device category**.</span></span>

### <span data-ttu-id="fa600-156">前提条件</span><span class="sxs-lookup"><span data-stu-id="fa600-156">Prerequisites</span></span>

- <span data-ttu-id="fa600-157">デバイスはネットワークに接続されています。</span><span class="sxs-lookup"><span data-stu-id="fa600-157">The device is connected to a network.</span></span>
- <span data-ttu-id="fa600-158">フィードバック Hub アプリはユーザーのデスクトップ コンピューターで利用できます。ユーザーは Microsoft クラウドにファイルをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="fa600-158">The Feedback Hub app is available on the user's desktop computer, and the user can upload files to the Microsoft cloud.</span></span>

### <span data-ttu-id="fa600-159">データの場所、アクセス、および保持</span><span class="sxs-lookup"><span data-stu-id="fa600-159">Data locations, access, and retention</span></span>

<span data-ttu-id="fa600-160">フィードバック Hub の使用条件に同意すると、ユーザーはデータの保存と使用に明示的に同意します (この同意で定義されます)。</span><span class="sxs-lookup"><span data-stu-id="fa600-160">By agreeing to the terms-of-use of the Feedback Hub, the user explicitly consents to the storage and usage of the data (as defined by that agreement).</span></span>

<span data-ttu-id="fa600-161">フィードバック Hub には、ユーザーが診断情報を格納する場所が 2 つ提供されます。</span><span class="sxs-lookup"><span data-stu-id="fa600-161">The Feedback Hub provides two places for the user to store diagnostic information:</span></span>

- <span data-ttu-id="fa600-162">**Microsoft クラウド**。</span><span class="sxs-lookup"><span data-stu-id="fa600-162">**The Microsoft cloud**.</span></span> <span data-ttu-id="fa600-163">フィードバック Hub アプリを使用してユーザーがアップロードしたデータは、次世代プライバシー (NGP) の要件と一致する日数保存されます。</span><span class="sxs-lookup"><span data-stu-id="fa600-163">Data that the user uploads by using the Feedback Hub app is stored for the number of days that is consistent with Next Generation Privacy (NGP) requirements.</span></span> <span data-ttu-id="fa600-164">Microsoft の従業員は、NGP 準拠のビューアーを使用して、この期間中に情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fa600-164">Microsoft employees can use an NGP-compliant viewer to access the information during this period.</span></span>
   > [!NOTE]  
   > <span data-ttu-id="fa600-165">これらの要件は、すべてのフィードバック Hub カテゴリのデータに適用されます。</span><span class="sxs-lookup"><span data-stu-id="fa600-165">These requirements apply to data in all Feedback Hub categories.</span></span>

- <span data-ttu-id="fa600-166">**HoloLens デバイス**。</span><span class="sxs-lookup"><span data-stu-id="fa600-166">**The HoloLens device**.</span></span> <span data-ttu-id="fa600-167">フィードバック Hub でレポートを提出するときに、ユーザーはフィードバックを送信するときに作成された診断と添付ファイルのローカル コピーを保存 **するを選択できます**。</span><span class="sxs-lookup"><span data-stu-id="fa600-167">While filing a report in Feedback Hub, the user can select **Save a local copy of diagnostics and attachments created when giving feedback**.</span></span> <span data-ttu-id="fa600-168">ユーザーがこのオプションを選択すると、フィードバック Hub は HoloLens デバイスに診断情報のコピーを保存します。</span><span class="sxs-lookup"><span data-stu-id="fa600-168">If the user selects this option, the Feedback Hub stores a copy of the diagnostic information on the HoloLens device.</span></span> <span data-ttu-id="fa600-169">この情報は、ユーザー (または、そのアカウントを使用して HoloLens にサインインするユーザー) が引き続きアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fa600-169">This information remains accessible to the user (or anyone that uses that account to sign in to HoloLens).</span></span> <span data-ttu-id="fa600-170">この情報を削除するには、ユーザーがデバイスに **対するデバイス所有者** または **管理者のアクセス** 許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa600-170">To delete this information, a user must have **Device owner** or **Admin** permissions on the device.</span></span> <span data-ttu-id="fa600-171">適切なアクセス許可を持つユーザーは、フィードバック Hub にサインインし\*\*\*\*、[設定ビュー] 診断ログを選択して、  >  \*\*\*\* 情報を削除できます。</span><span class="sxs-lookup"><span data-stu-id="fa600-171">A user who has the appropriate permissions can sign in to the Feedback Hub, select **Settings** > **View diagnostics logs**, and delete the information.</span></span>

## <span data-ttu-id="fa600-172">設定のトラブルシューティング ツール</span><span class="sxs-lookup"><span data-stu-id="fa600-172">Settings Troubleshooter</span></span>

<span data-ttu-id="fa600-173">HoloLens ユーザーは、デバイスの設定アプリを使用して、問題のトラブルシューティングと診断情報の収集を行います。</span><span class="sxs-lookup"><span data-stu-id="fa600-173">A HoloLens user can use the Settings app on the device to troubleshoot problems and collect diagnostic information.</span></span> <span data-ttu-id="fa600-174">これを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fa600-174">To do this, follow these steps:</span></span>

1. <span data-ttu-id="fa600-175">設定アプリを開き、[セキュリティのトラブルシューティング]**ページ&**  >  **を選択**します。</span><span class="sxs-lookup"><span data-stu-id="fa600-175">Open the Settings app and select **Update & Security** > **Troubleshoot** page.</span></span>
1. <span data-ttu-id="fa600-176">適切な領域を選択し、[スタート] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="fa600-176">Select the appropriate area, and select **Start**.</span></span>
1. <span data-ttu-id="fa600-177">問題を再現します。</span><span class="sxs-lookup"><span data-stu-id="fa600-177">Reproduce the issue.</span></span>
1. <span data-ttu-id="fa600-178">問題を再現した後、[設定] に戻り、[停止] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="fa600-178">After you reproduce the issue, return to Settings and then select **Stop**.</span></span>

### <span data-ttu-id="fa600-179">前提条件</span><span class="sxs-lookup"><span data-stu-id="fa600-179">Prerequisites</span></span>

- <span data-ttu-id="fa600-180">設定アプリはデバイスにインストールされ、ユーザーが利用できます。</span><span class="sxs-lookup"><span data-stu-id="fa600-180">The Settings app is installed on the device and is available to the user.</span></span>

### <span data-ttu-id="fa600-181">データの場所、アクセス、および保持</span><span class="sxs-lookup"><span data-stu-id="fa600-181">Data locations, access, and retention</span></span>

<span data-ttu-id="fa600-182">ユーザーがデータ収集を開始すると、ユーザーは診断情報の保存に暗黙的に同意します。</span><span class="sxs-lookup"><span data-stu-id="fa600-182">Because the user starts the data collection, the user implicitly consents to the storage of the diagnostic information.</span></span> <span data-ttu-id="fa600-183">データにアクセスできるのは、ユーザーまたはユーザーがデータを共有するユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="fa600-183">Only the user, or anyone with whom that the user shares the data, can access the data.</span></span>

<span data-ttu-id="fa600-184">診断情報はデバイスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="fa600-184">The diagnostic information is stored on the device.</span></span> <span data-ttu-id="fa600-185">デバイスがユーザーのコンピューターに接続されている場合、情報は次のファイル内のコンピューターにも存在します。</span><span class="sxs-lookup"><span data-stu-id="fa600-185">If the device is connected to the user's computer, the information also resides on the computer in the following file:</span></span>

> <span data-ttu-id="fa600-186">この PC\\ \<*HoloLens device name*> \\Internal Storage\\Documents\\Trace \<*ddmmyyhhmmss*> .etl</span><span class="sxs-lookup"><span data-stu-id="fa600-186">This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents\\Trace\<*ddmmyyhhmmss*>.etl</span></span>

> [!NOTE]  
> <span data-ttu-id="fa600-187">このファイル パスと名前では、HoloLens デバイスの名前を表し、ファイルが作成された日時 \<*HoloLens device name*> \<*ddmmyyhhmmss*> を表します。</span><span class="sxs-lookup"><span data-stu-id="fa600-187">In this file path and name, \<*HoloLens device name*> represents the name of the HoloLens device, and \<*ddmmyyhhmmss*> represents the date and time that the file was created.</span></span>

<span data-ttu-id="fa600-188">診断情報は、ユーザーが削除するまでこれらの場所に残ります。</span><span class="sxs-lookup"><span data-stu-id="fa600-188">The diagnostic information remains in these locations until the user deletes it.</span></span>

## <span data-ttu-id="fa600-189">DiagnosticLog CSP</span><span class="sxs-lookup"><span data-stu-id="fa600-189">DiagnosticLog CSP</span></span>

<span data-ttu-id="fa600-190">モバイル デバイス管理 (MDM) 環境では、IT 管理者は DiagnosticLog 構成サービス プロバイダー [(CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) を使用して、登録済み HoloLens デバイスの診断設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="fa600-190">In a Mobile Device Management (MDM) environment, the IT administrator can use the the [DiagnosticLog configuration service provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) to configure diagnostic settings on enrolled HoloLens devices.</span></span> <span data-ttu-id="fa600-191">IT 管理者は、登録済みデバイスからログを収集するためにこれらの設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="fa600-191">The IT administrator can configure these settings to collect logs from enrolled devices.</span></span>

### <span data-ttu-id="fa600-192">前提条件</span><span class="sxs-lookup"><span data-stu-id="fa600-192">Prerequisites</span></span>

- <span data-ttu-id="fa600-193">デバイスはネットワークに接続されています。</span><span class="sxs-lookup"><span data-stu-id="fa600-193">The device is connected to a network.</span></span>
- <span data-ttu-id="fa600-194">デバイスは、DiagnosticLog CSP をサポートする MDM 環境に登録されます。</span><span class="sxs-lookup"><span data-stu-id="fa600-194">The device is enrolled in an MDM environment that supports the DiagnosticLog CSP.</span></span>

### <span data-ttu-id="fa600-195">データの場所、アクセス、および保持</span><span class="sxs-lookup"><span data-stu-id="fa600-195">Data locations, access, and retention</span></span>

<span data-ttu-id="fa600-196">デバイスは管理環境の一部なので、ユーザーは診断情報への管理アクセスに暗黙的に同意します。</span><span class="sxs-lookup"><span data-stu-id="fa600-196">Because the device is part of the managed environment, the user implicitly consents to administrative access to diagnostic information.</span></span>

<span data-ttu-id="fa600-197">IT 管理者は、DiagnosticLog CSP を使用して、次のポリシーを管理するポリシーを含む、データ ストレージ、保持、およびアクセス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="fa600-197">The IT administrator uses the DiagnosticLog CSP to configure the data storage, retention, and access policies, including the policies that govern the following:</span></span>

- <span data-ttu-id="fa600-198">診断情報を格納するクラウド インフラストラクチャ。</span><span class="sxs-lookup"><span data-stu-id="fa600-198">The cloud infrastructure that stores the diagnostic information.</span></span>
- <span data-ttu-id="fa600-199">診断情報の保持期間。</span><span class="sxs-lookup"><span data-stu-id="fa600-199">The retention period for the diagnostic information.</span></span>
- <span data-ttu-id="fa600-200">診断情報へのアクセスを制御するアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="fa600-200">Permissions that control access to the diagnostic information.</span></span>

## <span data-ttu-id="fa600-201">オフライン診断</span><span class="sxs-lookup"><span data-stu-id="fa600-201">Offline diagnostics</span></span>
<span data-ttu-id="fa600-202">デバイスがフィードバック Hub または設定トラブルシューティング ツールを使用して診断を収集できない場合は、手動で診断を収集できます。</span><span class="sxs-lookup"><span data-stu-id="fa600-202">In situations where the device is not able to collect diagnostics via Feedback Hub or the Setting Troubleshooter, you can collect diagnostics manually.</span></span> <span data-ttu-id="fa600-203">これが必要なシナリオの 1 つは、デバイスが Wi-Fi に接続できない場合です。</span><span class="sxs-lookup"><span data-stu-id="fa600-203">One scenario where this is necessary is when the device cannot connect to Wi-Fi.</span></span> <span data-ttu-id="fa600-204">診断は、Microsoft サポート エンジニアが問題を分離するのに役立つクラッシュ ダンプとログをデバイスから収集します。</span><span class="sxs-lookup"><span data-stu-id="fa600-204">The diagnostics collect crash dumps and logs from the device that help a Microsoft support engineer isolate issues.</span></span>

<span data-ttu-id="fa600-205">これは、デバイスを USB ケーブルで PC に接続した後に、エクスプローラーにデバイスが表示される場合に機能します。</span><span class="sxs-lookup"><span data-stu-id="fa600-205">This works when the device shows up in File Explorer after connecting it to a PC via a USB cable.</span></span> 

> [!NOTE]
> <span data-ttu-id="fa600-206">オフライン診断の生成と管理は、OS のバージョンに応じて異なる方法で制御されます。</span><span class="sxs-lookup"><span data-stu-id="fa600-206">Offline Diagnostics generation and management is controlled differently depending on your OS version.</span></span> <span data-ttu-id="fa600-207">以前は利用統計情報の設定によって制御されましたが、現在はポリシーによって直接制御されています。</span><span class="sxs-lookup"><span data-stu-id="fa600-207">Previously it was controlled by the telemetry setting, but is now directly controlled via policy.</span></span> 

<span data-ttu-id="fa600-208">[Windows Holographic バージョン 20H2 より前の動作](hololens-release-notes.md#windows-holographic-version-20h2):</span><span class="sxs-lookup"><span data-stu-id="fa600-208">Behavior Prior to [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2):</span></span>
 - <span data-ttu-id="fa600-209">オフライン診断が有効になるのは、ユーザーが OOBE または [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) ポリシー値を Full に設定している場合のみです (HoloLens の既定値は Basic です)。</span><span class="sxs-lookup"><span data-stu-id="fa600-209">Offline diagnostics is only enabled when user is either going through OOBE or [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) policy value is set to Full (Basic is default value on HoloLens).</span></span> 
- <span data-ttu-id="fa600-210">オフライン診断を無効にするには、[設定] アプリの [プライバシー] **ページ>、[** 診断データ] で **[基本** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="fa600-210">To disable Offline diagnostics, go to **Settings App > Privacy** page and select **Basic** in **Diagnostic Data**.</span></span> <span data-ttu-id="fa600-211">オフライン診断が利用統計情報の設定に依存するビルドでは、ログが収集されるかどうかにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="fa600-211">On builds where offline diagnostics depends on telemetry setting, it only impacts whether any logs are collected or not.</span></span> <span data-ttu-id="fa600-212">収集されるファイルには影響を与えはありません。</span><span class="sxs-lookup"><span data-stu-id="fa600-212">It does not impact what files are collected.</span></span>
- <span data-ttu-id="fa600-213">デバイスがロックされている場合、ログは表示されません。</span><span class="sxs-lookup"><span data-stu-id="fa600-213">If device is locked then logs won't appear.</span></span>

<span data-ttu-id="fa600-214">On builds [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) and onwards:</span><span class="sxs-lookup"><span data-stu-id="fa600-214">On builds [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) and onwards:</span></span>
- <span data-ttu-id="fa600-215">フォールバック診断が有効になっている場合、対応する[設定 MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)を使用して特定の MDM ポリシーによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="fa600-215">When Fallback Diagnostics is enabled will be controlled by specific MDM policy with corresponding setting [MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)</span></span>
- <span data-ttu-id="fa600-216">デバイスがロックされている場合、ログは表示されません。</span><span class="sxs-lookup"><span data-stu-id="fa600-216">If device is locked then logs won't appear.</span></span>


<span data-ttu-id="fa600-217">詳細については、このビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fa600-217">Watch this video to learn more.</span></span> 

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

<span data-ttu-id="fa600-218">診断を収集するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fa600-218">Follow these steps to collect diagnostics:</span></span>
1.  <span data-ttu-id="fa600-219">デバイスを USB ケーブルで PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="fa600-219">Connect the device with a USB cable to your PC.</span></span>
2.  <span data-ttu-id="fa600-220">PC のエクスプローラーで、'This **PC \<hololens-device> \Internal Storage' に移動します**。</span><span class="sxs-lookup"><span data-stu-id="fa600-220">In File Explorer on your PC, navigate to **'This PC\<hololens-device>\Internal Storage'**.</span></span>
3.  <span data-ttu-id="fa600-221">内部ストレージ **フォルダーが** 表示されない場合、デバイスはユーザーのサインインを待機しています。</span><span class="sxs-lookup"><span data-stu-id="fa600-221">If the **Internal Storage** folder does not show up, the device is waiting for a user to sign in.</span></span> <span data-ttu-id="fa600-222">電源ボタンを 10 秒間押し続け、デバイスへのサインインまたは電源サイクルを行います。</span><span class="sxs-lookup"><span data-stu-id="fa600-222">Either sign-in or power cycle the device by holding the POWER button down for 10 seconds.</span></span>
4.  <span data-ttu-id="fa600-223">電源ボタンと音量を下すボタンを **一緒に押して** すぐに離します。</span><span class="sxs-lookup"><span data-stu-id="fa600-223">Press and immediately release the **POWER + VOLUME DOWN** buttons together.</span></span>
5.  <span data-ttu-id="fa600-224">デバイスが zip アーカイブを準備するまで少し待ちます。</span><span class="sxs-lookup"><span data-stu-id="fa600-224">Wait a minute for the device to prepare the zip archives.</span></span> <span data-ttu-id="fa600-225">(HololensDiagnostics.temp という名前の一時ファイルは、デバイスが zip アーカイブを生成している間に表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="fa600-225">(A temporary file named HololensDiagnostics.temp may become visible while the device generates the zip archives.</span></span> <span data-ttu-id="fa600-226">そのファイルにアクセスしたり、保存したりしない。</span><span class="sxs-lookup"><span data-stu-id="fa600-226">Do not access or save that file.</span></span> <span data-ttu-id="fa600-227">プロセスが完了すると、zip アーカイブに置き換えられる)。</span><span class="sxs-lookup"><span data-stu-id="fa600-227">When the process finishes it will be replaced by the zip archives.)</span></span>
6.  <span data-ttu-id="fa600-228">エクスプローラーを更新し **、'\Documents' フォルダーに移動** します。</span><span class="sxs-lookup"><span data-stu-id="fa600-228">Refresh file explorer, and navigate to the **'\Documents'** folder.</span></span>
7.  <span data-ttu-id="fa600-229">診断 ZIP ファイルをコピーし、Microsoft サポート チームと共有します。</span><span class="sxs-lookup"><span data-stu-id="fa600-229">Copy the diagnostics ZIP files and share them with the Microsoft support team.</span></span>

> [!NOTE]
> <span data-ttu-id="fa600-230">一部の診断 ZIP ファイルには、個人を特定できる情報が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="fa600-230">Some of the diagnostics ZIP files may contain personally identifiable information.</span></span>



