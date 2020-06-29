---
title: HoloLens を Kiosk としてセットアップする
description: HoloLens でアプリをロックダウンするには、キオスクの構成を使用します。
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 04/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 0163e028756743922302b46f04309f3d7f738233
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829312"
---
# <span data-ttu-id="94a6c-103">HoloLens を Kiosk としてセットアップする</span><span class="sxs-lookup"><span data-stu-id="94a6c-103">Set up HoloLens as a kiosk</span></span>

<span data-ttu-id="94a6c-104">HoloLens デバイスを、キオスクモードで実行するように構成することによって、*キオスク*デバイス (キオスクとも呼ばれます) として機能させることができます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-104">You can configure a HoloLens device to function as a fixed-purpose device, also called a *kiosk*, by configuring the device to run in kiosk mode.</span></span> <span data-ttu-id="94a6c-105">キオスクモードでは、デバイスで利用可能なアプリケーション (またはユーザー) を制限します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-105">Kiosk mode limits the applications (or users) that are available on the device.</span></span> <span data-ttu-id="94a6c-106">キオスクモードは、HoloLens デバイスをビジネスアプリ専用にするために使うことができる便利な機能です。または、アプリデモで HoloLens デバイスを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-106">Kiosk mode is a convenient feature that you can use to dedicate a HoloLens device to business apps, or to use the HoloLens device in an app demo.</span></span>

<span data-ttu-id="94a6c-107">この記事では、HoloLens デバイスに固有のキオスク構成の要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-107">This article provides information about aspects of kiosk configuration that are specific to HoloLens devices.</span></span> <span data-ttu-id="94a6c-108">Windows ベースのキオスクのさまざまな種類とその構成方法については、「 [windows デスクトップエディションでのキオスクとデジタル署名の構成](https://docs.microsoft.com/windows/configuration/kiosk-methods)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-108">For general information about the different types of Windows-based kiosks and how to configure them, see [Configure kiosks and digital signs on Windows desktop editions](https://docs.microsoft.com/windows/configuration/kiosk-methods).</span></span>  

> [!IMPORTANT]  
> <span data-ttu-id="94a6c-109">キオスクモードは、ユーザーがデバイスにサインインしたときに利用できるアプリを決定します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-109">Kiosk mode determines which apps are available when a user signs in to the device.</span></span> <span data-ttu-id="94a6c-110">ただし、キオスクモードはセキュリティの方法ではありません。</span><span class="sxs-lookup"><span data-stu-id="94a6c-110">However, kiosk mode is not a security method.</span></span> <span data-ttu-id="94a6c-111">これにより、許可されていない別のアプリを開くことができなくなることはありません。</span><span class="sxs-lookup"><span data-stu-id="94a6c-111">It does not stop an "allowed" app from opening another app that is not allowed.</span></span> <span data-ttu-id="94a6c-112">アプリやプロセスが開かれないようにするには、 [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)を使って適切なポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-112">In order to block apps or processes from opening, use [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) to create appropriate policies.</span></span>  

<span data-ttu-id="94a6c-113">キオスクモードは1つのアプリまたは複数のアプリの構成で使うことができます。また、3つのプロセスのいずれかを使って、キオスク構成を設定して展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-113">You can use kiosk mode in either a single-app or a multi-app configuration, and you can use one of three processes to set up and deploy the kiosk configuration.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="94a6c-114">マルチアプリ構成を削除すると、割り当てられたアクセス機能で作成されたユーザーロックダウンプロファイルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-114">Deleting the multi-app configuration removes the user lockdown profiles that the assigned access feature created.</span></span> <span data-ttu-id="94a6c-115">ただし、すべてのポリシーの変更は元に戻すわけではありません。</span><span class="sxs-lookup"><span data-stu-id="94a6c-115">However, it does not revert all the policy changes.</span></span> <span data-ttu-id="94a6c-116">これらのポリシーを元に戻すには、デバイスを出荷時の設定にリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94a6c-116">To revert these policies, you have to reset the device to the factory settings.</span></span>

## <span data-ttu-id="94a6c-117">キオスク展開を計画する</span><span class="sxs-lookup"><span data-stu-id="94a6c-117">Plan the kiosk deployment</span></span>

### <span data-ttu-id="94a6c-118">キオスクモードの要件</span><span class="sxs-lookup"><span data-stu-id="94a6c-118">Kiosk mode requirements</span></span>

<span data-ttu-id="94a6c-119">すべての HoloLens 2 デバイスでキオスクモードを使用するように構成することができます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-119">You can configure any HoloLens 2 device to use kiosk mode.</span></span>

<span data-ttu-id="94a6c-120">HoloLens (第1世代) デバイスでキオスクモードを使用するように構成するには、デバイスが Windows 10、バージョン1803、またはそれ以降のバージョンを実行していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94a6c-120">To configure a HoloLens (1st gen) device to use kiosk mode, you must first make sure that the device runs Windows 10, version 1803, or a later version.</span></span> <span data-ttu-id="94a6c-121">HoloLens (第1世代) デバイスを既定のビルドに復元するために Windows デバイス回復ツールを使っている場合、または最新の更新プログラムがインストールされている場合は、デバイスを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-121">If you have used the Windows Device Recovery Tool to recover your HoloLens (1st gen) device to its default build, or if you have installed the most recent updates, your device is ready to configure.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="94a6c-122">キオスクモードで実行されているデバイスを保護するには、USB 接続などの機能をオフにするデバイス管理ポリシーを追加することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-122">To help protect devices that run in kiosk mode, consider adding device management policies that turn off features such as USB connectivity.</span></span> <span data-ttu-id="94a6c-123">さらに、更新プログラムのリング設定を確認して、営業時間中に自動更新が行われないようにします。</span><span class="sxs-lookup"><span data-stu-id="94a6c-123">Additionally, check your update ring settings to make sure that automatic updates do not occur during business hours.</span></span>

### <span data-ttu-id="94a6c-124">単一アプリのキオスクと複数アプリのキオスクのどちらを選択するかを決定する</span><span class="sxs-lookup"><span data-stu-id="94a6c-124">Decide between a single-app kiosk or a multi-app kiosk</span></span>

<span data-ttu-id="94a6c-125">1つのアプリのキオスクは、ユーザーがデバイスにサインインしたときに、指定されたアプリを起動します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-125">A single-app kiosk starts the specified app when the user signs in to the device.</span></span> <span data-ttu-id="94a6c-126">[スタート] メニューは、Cortana のように無効になっています。</span><span class="sxs-lookup"><span data-stu-id="94a6c-126">The Start menu is disabled, as is Cortana.</span></span> <span data-ttu-id="94a6c-127">HoloLens 2 デバイスは、[開始](hololens2-basic-usage.md#start-gesture)ジェスチャには応答しません。</span><span class="sxs-lookup"><span data-stu-id="94a6c-127">A HoloLens 2 device does not respond to the [Start](hololens2-basic-usage.md#start-gesture) gesture.</span></span> <span data-ttu-id="94a6c-128">HoloLens (第1世代) デバイスは、[ブルーム](hololens1-basic-usage.md)ジェスチャに対応していません。</span><span class="sxs-lookup"><span data-stu-id="94a6c-128">A HoloLens (1st gen) device does not respond to the [bloom](hololens1-basic-usage.md) gesture.</span></span> <span data-ttu-id="94a6c-129">1つのアプリのみを実行できるため、ユーザーは他のアプリを配置することはできません。</span><span class="sxs-lookup"><span data-stu-id="94a6c-129">Because only one app can run, the user cannot place other apps.</span></span>

<span data-ttu-id="94a6c-130">マルチアプリキオスクは、ユーザーがデバイスにサインインしたときに [スタート] メニューを表示します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-130">A multi-app kiosk displays the Start menu when the user signs in to the device.</span></span> <span data-ttu-id="94a6c-131">キオスクの構成では、[スタート] メニューで使用できるアプリを決定します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-131">The kiosk configuration determines which apps are available on the Start menu.</span></span> <span data-ttu-id="94a6c-132">複数アプリのキオスクを使って、ユーザーが使用する必要があるものだけを表示したり、使用する必要がないものを削除したりすることで、ユーザーにとってわかりやすいエクスペリエンスを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-132">You can use a multi-app kiosk to provide an easy-to-understand experience for users by presenting to them only the things that they have to use, and removing the things they don't need to use.</span></span>

<span data-ttu-id="94a6c-133">次の表に、さまざまなキオスクモードの機能の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-133">The following table lists the feature capabilities in the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="94a6c-134">スタート メニュー</span><span class="sxs-lookup"><span data-stu-id="94a6c-134">Start menu</span></span> |<span data-ttu-id="94a6c-135">クイック操作メニュー</span><span class="sxs-lookup"><span data-stu-id="94a6c-135">Quick Actions menu</span></span> |<span data-ttu-id="94a6c-136">カメラとビデオ</span><span class="sxs-lookup"><span data-stu-id="94a6c-136">Camera and video</span></span> |<span data-ttu-id="94a6c-137">Miracast</span><span class="sxs-lookup"><span data-stu-id="94a6c-137">Miracast</span></span> |<span data-ttu-id="94a6c-138">Cortana</span><span class="sxs-lookup"><span data-stu-id="94a6c-138">Cortana</span></span> |<span data-ttu-id="94a6c-139">組み込みの音声コマンド</span><span class="sxs-lookup"><span data-stu-id="94a6c-139">Built-in voice commands</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|<span data-ttu-id="94a6c-140">単一アプリのキオスク</span><span class="sxs-lookup"><span data-stu-id="94a6c-140">Single-app kiosk</span></span> |<span data-ttu-id="94a6c-141">無効</span><span class="sxs-lookup"><span data-stu-id="94a6c-141">Disabled</span></span> |<span data-ttu-id="94a6c-142">無効</span><span class="sxs-lookup"><span data-stu-id="94a6c-142">Disabled</span></span>   |<span data-ttu-id="94a6c-143">無効</span><span class="sxs-lookup"><span data-stu-id="94a6c-143">Disabled</span></span> |<span data-ttu-id="94a6c-144">無効</span><span class="sxs-lookup"><span data-stu-id="94a6c-144">Disabled</span></span>   |<span data-ttu-id="94a6c-145">無効</span><span class="sxs-lookup"><span data-stu-id="94a6c-145">Disabled</span></span> |<span data-ttu-id="94a6c-146">Enabled <sup> 1</span><span class="sxs-lookup"><span data-stu-id="94a6c-146">Enabled<sup>1</span></span></sup> |
|<span data-ttu-id="94a6c-147">マルチアプリのキオスク</span><span class="sxs-lookup"><span data-stu-id="94a6c-147">Multi-app kiosk</span></span> |<span data-ttu-id="94a6c-148">有効</span><span class="sxs-lookup"><span data-stu-id="94a6c-148">Enabled</span></span> |<span data-ttu-id="94a6c-149">Enabled <sup> 2</span><span class="sxs-lookup"><span data-stu-id="94a6c-149">Enabled<sup>2</span></span></sup> |<span data-ttu-id="94a6c-150">利用可能な <sup> 2</span><span class="sxs-lookup"><span data-stu-id="94a6c-150">Available<sup>2</span></span></sup> |<span data-ttu-id="94a6c-151">利用可能な <sup> 2</span><span class="sxs-lookup"><span data-stu-id="94a6c-151">Available<sup>2</span></span></sup> |<span data-ttu-id="94a6c-152">利用可能な <sup> 2、3</span><span class="sxs-lookup"><span data-stu-id="94a6c-152">Available<sup>2, 3</span></span></sup>  |<span data-ttu-id="94a6c-153">Enabled <sup> 1</span><span class="sxs-lookup"><span data-stu-id="94a6c-153">Enabled<sup>1</span></span></sup> |

> <sup><span data-ttu-id="94a6c-154">1 </sup> 無効な機能に関連する音声コマンドが機能しません。</span><span class="sxs-lookup"><span data-stu-id="94a6c-154">1</sup> Voice commands that relate to disabled features do not function.</span></span>  
> <sup><span data-ttu-id="94a6c-155">2 </sup> これらの機能を構成する方法の詳細については、「[キオスクアプリを選択](#plan-kiosk-apps)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-155">2</sup> For more information about how to configure these features, see [Select kiosk apps](#plan-kiosk-apps).</span></span>  
> <sup><span data-ttu-id="94a6c-156">3 </sup> Cortana が無効になっている場合でも、組み込みの音声コマンドは有効になります。</span><span class="sxs-lookup"><span data-stu-id="94a6c-156">3</sup> Even if Cortana is disabled, the built-in voice commands are enabled.</span></span>

<span data-ttu-id="94a6c-157">次の表は、さまざまなキオスクモードのユーザーサポート機能をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="94a6c-157">The following table lists the user support features of the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="94a6c-158">サポートされているユーザーの種類</span><span class="sxs-lookup"><span data-stu-id="94a6c-158">Supported user types</span></span> | <span data-ttu-id="94a6c-159">自動サインイン</span><span class="sxs-lookup"><span data-stu-id="94a6c-159">Automatic sign-in</span></span> | <span data-ttu-id="94a6c-160">複数のアクセスレベル</span><span class="sxs-lookup"><span data-stu-id="94a6c-160">Multiple access levels</span></span> |
| --- | --- | --- | --- |
|<span data-ttu-id="94a6c-161">単一アプリのキオスク</span><span class="sxs-lookup"><span data-stu-id="94a6c-161">Single-app kiosk</span></span> |<span data-ttu-id="94a6c-162">Azure Active Directory (AAD) またはローカルアカウントの管理されたサービスアカウント (MSA)</span><span class="sxs-lookup"><span data-stu-id="94a6c-162">Managed Service Account (MSA) in Azure Active Directory (AAD) or local account</span></span> |<span data-ttu-id="94a6c-163">あり</span><span class="sxs-lookup"><span data-stu-id="94a6c-163">Yes</span></span> |<span data-ttu-id="94a6c-164">なし</span><span class="sxs-lookup"><span data-stu-id="94a6c-164">No</span></span> |
|<span data-ttu-id="94a6c-165">マルチアプリのキオスク</span><span class="sxs-lookup"><span data-stu-id="94a6c-165">Multi-app kiosk</span></span> |<span data-ttu-id="94a6c-166">AAD アカウント</span><span class="sxs-lookup"><span data-stu-id="94a6c-166">AAD account</span></span> |<span data-ttu-id="94a6c-167">なし</span><span class="sxs-lookup"><span data-stu-id="94a6c-167">No</span></span> |<span data-ttu-id="94a6c-168">あり</span><span class="sxs-lookup"><span data-stu-id="94a6c-168">Yes</span></span> |

<span data-ttu-id="94a6c-169">これらの機能の使用方法の例については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-169">For examples of how to use these capabilities, see the following table.</span></span>

|<span data-ttu-id="94a6c-170">単一アプリのキオスクの用途:</span><span class="sxs-lookup"><span data-stu-id="94a6c-170">Use a single-app kiosk for:</span></span> |<span data-ttu-id="94a6c-171">複数のアプリでのキオスクの用途:</span><span class="sxs-lookup"><span data-stu-id="94a6c-171">Use a multi-app kiosk for:</span></span> |
| --- | --- |
|<span data-ttu-id="94a6c-172">新しい従業員向けの Dynamics 365 ガイドのみを実行するデバイス。</span><span class="sxs-lookup"><span data-stu-id="94a6c-172">A device that runs only a Dynamics 365 Guide for new employees.</span></span> |<span data-ttu-id="94a6c-173">さまざまな従業員のガイドとリモートアシスタンスの両方を実行するデバイス。</span><span class="sxs-lookup"><span data-stu-id="94a6c-173">A device that runs both Guides and Remote Assistance for a range of employees.</span></span> |
|<span data-ttu-id="94a6c-174">カスタムアプリのみを実行するデバイス。</span><span class="sxs-lookup"><span data-stu-id="94a6c-174">A device that runs only a custom app.</span></span> |<span data-ttu-id="94a6c-175">ほとんどのユーザーのためにキオスクとして機能する (カスタムアプリのみを実行します)、特定のユーザーグループの標準デバイスとして機能するデバイス。</span><span class="sxs-lookup"><span data-stu-id="94a6c-175">A device that functions as a kiosk for most users (running only a custom app), but functions as a standard device for a specific group of users.</span></span> |

### <span data-ttu-id="94a6c-176">キオスクアプリを計画する</span><span class="sxs-lookup"><span data-stu-id="94a6c-176">Plan kiosk apps</span></span>

<span data-ttu-id="94a6c-177">キオスクアプリの選択方法に関する一般的な情報については、「[割り当てられたアクセスのアプリを選ぶためのガイドライン (キオスクモード)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-177">For general information about how to choose kiosk apps, see [Guidelines for choosing an app for assigned access (kiosk mode)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app).</span></span>

<span data-ttu-id="94a6c-178">Windows Device Portal を使って単一アプリのキオスクを構成する場合は、セットアッププロセス中にアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-178">If you use the Windows Device Portal to configure a single-app kiosk, you select the app during the setup process.</span></span>  

<span data-ttu-id="94a6c-179">モバイルデバイス管理 (MDM) システムまたはプロビジョニングパッケージを使ってキオスクモードを構成する場合は、 [AssignedAccess 構成サービスプロバイダー (CSP)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp)を使ってアプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-179">If you use a Mobile Device Management (MDM) system or a provisioning package to configure kiosk mode, you use the [AssignedAccess Configuration Service Provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) to specify applications.</span></span> <span data-ttu-id="94a6c-180">CSP は、[アプリケーションユーザーモデル id (aumid)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app)を使ってアプリケーションを特定します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-180">The CSP uses [Application User Model IDs (AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) to identify applications.</span></span> <span data-ttu-id="94a6c-181">次の表に、マルチアプリキオスクで使用できる Aumid アプリケーションの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-181">The following table lists the AUMIDs of some in-box applications that you can use in a multi-app kiosk.</span></span>

> [!CAUTION]
> <span data-ttu-id="94a6c-182">Shell アプリをキオスクアプリとして選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="94a6c-182">You cannot select the Shell app as a kiosk app.</span></span> <span data-ttu-id="94a6c-183">さらに、Microsoft Edge、Microsoft ストア、またはエクスプローラーをキオスクアプリとして選択し**ない**ことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="94a6c-183">Addition, we recommend that you do **not** select Microsoft Edge, Microsoft Store, or File Explorer as a kiosk app.</span></span>  

<a id="aumids"></a>

|<span data-ttu-id="94a6c-184">アプリ名</span><span class="sxs-lookup"><span data-stu-id="94a6c-184">App Name</span></span> |<span data-ttu-id="94a6c-185">AUMID</span><span class="sxs-lookup"><span data-stu-id="94a6c-185">AUMID</span></span> |
| --- | --- |
|<span data-ttu-id="94a6c-186">3D ビューアー</span><span class="sxs-lookup"><span data-stu-id="94a6c-186">3D Viewer</span></span> |<span data-ttu-id="94a6c-187">Microsoft3DViewer \ _8wekyb3d8bbwe \!Microsoft3DViewer</span><span class="sxs-lookup"><span data-stu-id="94a6c-187">Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\!Microsoft.Microsoft3DViewer</span></span> |
|<span data-ttu-id="94a6c-188">カレンダー</span><span class="sxs-lookup"><span data-stu-id="94a6c-188">Calendar</span></span> |<span data-ttu-id="94a6c-189">windowscommunicationsapps \ _8wekyb3d8bbwe \! windowslive の予定表</span><span class="sxs-lookup"><span data-stu-id="94a6c-189">microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\!microsoft.windowslive.calendar</span></span> |
|<span data-ttu-id="94a6c-190">カメラ <sup> 1、2</span><span class="sxs-lookup"><span data-stu-id="94a6c-190">Camera<sup>1, 2</span></span></sup> |<span data-ttu-id="94a6c-191">HoloCamera \ _cw5n1h2txyewy \!HoloCamera</span><span class="sxs-lookup"><span data-stu-id="94a6c-191">HoloCamera\_cw5n1h2txyewy\!HoloCamera</span></span> |
|<span data-ttu-id="94a6c-192">Cortana <sup> 3</span><span class="sxs-lookup"><span data-stu-id="94a6c-192">Cortana<sup>3</span></span></sup> |<span data-ttu-id="94a6c-193">Microsoft 2015 9981C3F5F10 \ _8wekyb3d8bbwe \!アプリケーション</span><span class="sxs-lookup"><span data-stu-id="94a6c-193">Microsoft.549981C3F5F10\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="94a6c-194">デバイスピッカー</span><span class="sxs-lookup"><span data-stu-id="94a6c-194">Device Picker</span></span> |<span data-ttu-id="94a6c-195">HoloDevicesFlow \ _cw5n1h2txyewy \!HoloDevicesFlow</span><span class="sxs-lookup"><span data-stu-id="94a6c-195">HoloDevicesFlow\_cw5n1h2txyewy\!HoloDevicesFlow</span></span> |
|<span data-ttu-id="94a6c-196">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="94a6c-196">Dynamics 365 Guides</span></span> |<span data-ttu-id="94a6c-197">Dynamics365 () _8wekyb3d8bbwe \!Microsoft のガイド</span><span class="sxs-lookup"><span data-stu-id="94a6c-197">Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\!MicrosoftGuides</span></span> |
|<span data-ttu-id="94a6c-198">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="94a6c-198">Dynamics 365 Remote Assist</span></span> |<span data-ttu-id="94a6c-199">Microsoft office サポートの \ _8wekyb3d8bbwe \!Microsoft RemoteAssist</span><span class="sxs-lookup"><span data-stu-id="94a6c-199">Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\!Microsoft.RemoteAssist</span></span> |
|<span data-ttu-id="94a6c-200">フィードバック &nbsp; Hub</span><span class="sxs-lookup"><span data-stu-id="94a6c-200">Feedback&nbsp;Hub</span></span> |<span data-ttu-id="94a6c-201">Microsoft Windowsフィードバックハブ \ _8wekyb3d8bbwe \!アプリケーション</span><span class="sxs-lookup"><span data-stu-id="94a6c-201">Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="94a6c-202">エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="94a6c-202">File Explorer</span></span> |<span data-ttu-id="94a6c-203">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span><span class="sxs-lookup"><span data-stu-id="94a6c-203">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span></span> |
|<span data-ttu-id="94a6c-204">メール</span><span class="sxs-lookup"><span data-stu-id="94a6c-204">Mail</span></span> |<span data-ttu-id="94a6c-205">microsoft. windowscommunicationsapps_8wekyb3d8bbwe! windowslive</span><span class="sxs-lookup"><span data-stu-id="94a6c-205">microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail</span></span> |
|<span data-ttu-id="94a6c-206">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="94a6c-206">Microsoft Store</span></span> |<span data-ttu-id="94a6c-207">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span><span class="sxs-lookup"><span data-stu-id="94a6c-207">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span></span> |
|<span data-ttu-id="94a6c-208">Miracast <sup> 4</span><span class="sxs-lookup"><span data-stu-id="94a6c-208">Miracast<sup>4</span></span></sup> |&nbsp; |
|<span data-ttu-id="94a6c-209">映画 & テレビ</span><span class="sxs-lookup"><span data-stu-id="94a6c-209">Movies & TV</span></span> |<span data-ttu-id="94a6c-210">Microsoft ZuneVideo \ _8wekyb3d8bbweMicrosoft ZuneVideo</span><span class="sxs-lookup"><span data-stu-id="94a6c-210">Microsoft.ZuneVideo\_8wekyb3d8bbwe\!Microsoft.ZuneVideo</span></span> |
|<span data-ttu-id="94a6c-211">OneDrive</span><span class="sxs-lookup"><span data-stu-id="94a6c-211">OneDrive</span></span> |<span data-ttu-id="94a6c-212">microsoft office skydrive \ _8wekyb3d8bbweアプリケーション</span><span class="sxs-lookup"><span data-stu-id="94a6c-212">microsoft.microsoftskydrive\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="94a6c-213">フォト</span><span class="sxs-lookup"><span data-stu-id="94a6c-213">Photos</span></span> |<span data-ttu-id="94a6c-214">Microsoft. 写真 \ _8wekyb3d8bbwe \!アプリケーション</span><span class="sxs-lookup"><span data-stu-id="94a6c-214">Microsoft.Windows.Photos\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="94a6c-215">設定</span><span class="sxs-lookup"><span data-stu-id="94a6c-215">Settings</span></span> |<span data-ttu-id="94a6c-216">HolographicSystemSettings \ _cw5n1h2txyewy \!アプリケーション</span><span class="sxs-lookup"><span data-stu-id="94a6c-216">HolographicSystemSettings\_cw5n1h2txyewy\!App</span></span> |
|<span data-ttu-id="94a6c-217">ヒント</span><span class="sxs-lookup"><span data-stu-id="94a6c-217">Tips</span></span> |<span data-ttu-id="94a6c-218">HoloLensTips \ _8wekyb3d8bbwe \!HoloLensTips</span><span class="sxs-lookup"><span data-stu-id="94a6c-218">Microsoft.HoloLensTips\_8wekyb3d8bbwe\!HoloLensTips</span></span> |

> <sup><span data-ttu-id="94a6c-219">1 </sup> 写真またはビデオのキャプチャを有効にするには、カメラアプリをキオスクアプリとして有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94a6c-219">1</sup> To enable photo or video capture, you have to enable the Camera app as a kiosk app.</span></span>  
> <sup><span data-ttu-id="94a6c-220">2 </sup> カメラアプリを有効にする場合は、次の条件に注意してください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-220">2</sup> When you enable the Camera app, be aware of the following conditions:</span></span>
> - <span data-ttu-id="94a6c-221">[クイック操作] メニューには、写真とビデオのボタンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="94a6c-221">The Quick Actions menu includes the Photo and Video buttons.</span></span>  
> - <span data-ttu-id="94a6c-222">画像を操作したり、写真を取得したりできるアプリ (写真、メール、OneDrive など) も有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94a6c-222">You should also enable an app (such as Photos, Mail, or OneDrive) that can interact with or retrieve pictures.</span></span>  
>  
> <sup><span data-ttu-id="94a6c-223">3 </sup> キオスクアプリとして Cortana を有効にしていない場合でも、組み込みの音声コマンドは有効になります。</span><span class="sxs-lookup"><span data-stu-id="94a6c-223">3</sup> Even if you do not enable Cortana as a kiosk app, built-in voice commands are enabled.</span></span> <span data-ttu-id="94a6c-224">ただし、無効な機能に関連するコマンドには影響はありません。</span><span class="sxs-lookup"><span data-stu-id="94a6c-224">However, commands that are related to disabled features have no effect.</span></span>  
> <sup><span data-ttu-id="94a6c-225">4 </sup> Miracast を直接有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="94a6c-225">4</sup> You cannot enable Miracast directly.</span></span> <span data-ttu-id="94a6c-226">キオスクアプリとして Miracast を有効にするには、カメラアプリとデバイスピッカーアプリを有効にします。</span><span class="sxs-lookup"><span data-stu-id="94a6c-226">To enable Miracast as a kiosk app, enable the Camera app and the Device Picker app.</span></span>

### <span data-ttu-id="94a6c-227">ユーザーとデバイスグループを計画する</span><span class="sxs-lookup"><span data-stu-id="94a6c-227">Plan user and device groups</span></span>

<span data-ttu-id="94a6c-228">MDM 環境では、グループを使ってデバイスの構成とユーザーアクセスを管理します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-228">In an MDM environment, you use groups to manage device configurations and user access.</span></span> 

<span data-ttu-id="94a6c-229">キオスク構成プロファイルには、**ユーザーのログオンの種類**の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="94a6c-229">The kiosk configuration profile includes the **User logon type** setting.</span></span> <span data-ttu-id="94a6c-230">[**ユーザーのログオンの種類**] には、追加したアプリまたはアプリを使うことができるユーザー (またはユーザーが含まれているグループ) を指定します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-230">**User logon type** identifies the user (or group that contains the users) who can use the app or apps that you add.</span></span> <span data-ttu-id="94a6c-231">構成プロファイルに含まれていないアカウントを使用してサインインした場合、ユーザーはキオスクのアプリを使用できません。</span><span class="sxs-lookup"><span data-stu-id="94a6c-231">If a user signs in by using an account that is not included in the configuration profile, that user cannot use apps on the kiosk.</span></span>  

> [!NOTE]  
> <span data-ttu-id="94a6c-232">単一アプリのキオスクの**ユーザーログオンの種類**は、1つのユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-232">The **User logon type** of a single-app kiosk specifies a single user account.</span></span> <span data-ttu-id="94a6c-233">これは、キオスクを実行するユーザーコンテキストです。</span><span class="sxs-lookup"><span data-stu-id="94a6c-233">This is the user context under which the kiosk runs.</span></span> <span data-ttu-id="94a6c-234">マルチアプリキオスクの**ユーザーログオンの種類**では、キオスクを使用できる1つ以上のユーザーアカウントまたはグループを指定できます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-234">The **User logon type** of a multi-app kiosk can specify one or more user accounts or groups that can use the kiosk.</span></span>

<span data-ttu-id="94a6c-235">キオスクの構成をデバイスに展開するには、その前に、デバイスにサインインできるデバイスまたはユーザーが含まれているグループにキオスク構成プロファイルを*割り当てる*必要があります。</span><span class="sxs-lookup"><span data-stu-id="94a6c-235">Before you can deploy the kiosk configuration to a device, you have to *assign* the kiosk configuration profile to a group that contains the device or a user who can sign in to the device.</span></span> <span data-ttu-id="94a6c-236">この設定により、次のような動作が生成されます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-236">This setting produces behavior such as the following.</span></span>

- <span data-ttu-id="94a6c-237">デバイスが割り当てられたグループのメンバーである場合は、ユーザーが初めてデバイスにサインインしたときに、キオスクの構成がデバイスに展開されます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-237">If the device is a member of the assigned group, the kiosk configuration deploys to the device the first time that any user signs in on the device.</span></span>  
- <span data-ttu-id="94a6c-238">デバイスが割り当てられたグループのメンバーではなく、そのグループのメンバーであるユーザーがサインインすると、その時点で、キオスク構成がデバイスに展開されます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-238">If the device is not a member of the assigned group, but a user who is a member of that group signs in, the kiosk configuration deploys to the device at that time.</span></span>

<span data-ttu-id="94a6c-239">Intune で構成プロファイルを割り当てる場合の影響の詳細については、「 [Microsoft intune でユーザーとデバイスのプロファイルを割り当てる](https://docs.microsoft.com/intune/configuration/device-profile-assign)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-239">For a full discussion of the effects of assigning configuration profiles in Intune, see [Assign user and device profiles in Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).</span></span>

> [!NOTE]  
> <span data-ttu-id="94a6c-240">次の例では、マルチアプリのキオスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-240">The following examples describe multi-app kiosks.</span></span> <span data-ttu-id="94a6c-241">1つのアプリのキオスクは同様の方法で動作しますが、キオスクのエクスペリエンスを取得できるのは1つのユーザーアカウントだけです。</span><span class="sxs-lookup"><span data-stu-id="94a6c-241">Single-app kiosks behave in a similar manner, but only one user account gets the kiosk experience.</span></span>

**<span data-ttu-id="94a6c-242">例 1</span><span class="sxs-lookup"><span data-stu-id="94a6c-242">Example 1</span></span>**

<span data-ttu-id="94a6c-243">デバイスとユーザーの両方に1つのグループ (グループ 1) を使用します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-243">You use a single group (Group 1) for both devices and users.</span></span> <span data-ttu-id="94a6c-244">1つのデバイスとユーザー A、B、C はこのグループのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="94a6c-244">One device and users A, B, and C are members of this group.</span></span> <span data-ttu-id="94a6c-245">キオスク構成プロファイルは、次の手順で構成します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-245">You configure the kiosk configuration profile as follows:</span></span>  

- <span data-ttu-id="94a6c-246">**ユーザーログオンの種類**: グループ1</span><span class="sxs-lookup"><span data-stu-id="94a6c-246">**User logon type**: Group 1</span></span>
- <span data-ttu-id="94a6c-247">**割り当て済みグループ**: グループ1</span><span class="sxs-lookup"><span data-stu-id="94a6c-247">**Assigned group**: Group 1</span></span>

<span data-ttu-id="94a6c-248">最初にどのユーザーがデバイスにサインインしているかにかかわらず (そのため、既定のエクスペリエンスまたは OOBE を通過する)、キオスクの構成がデバイスに展開されます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-248">Regardless of which user signs on to the device first (and goes through the Out-of-Box Experience, or OOBE), the kiosk configuration deploys to the device.</span></span> <span data-ttu-id="94a6c-249">ユーザー A、B、および C では、すべてのデバイスにサインインして、キオスクのエクスペリエンスを利用することができます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-249">Users A, B, and C can all sign in to the device and get the kiosk experience.</span></span>

**<span data-ttu-id="94a6c-250">例 2</span><span class="sxs-lookup"><span data-stu-id="94a6c-250">Example 2</span></span>**

<span data-ttu-id="94a6c-251">さまざまなキオスクエクスペリエンスが必要な2つの異なるベンダーにデバイスをコントラクトアウトします。</span><span class="sxs-lookup"><span data-stu-id="94a6c-251">You contract out devices to two different vendors who need different kiosk experiences.</span></span> <span data-ttu-id="94a6c-252">どちらのベンダーもユーザーを所有しており、すべてのユーザーが自分のベンダーと他のベンダーの両方からキオスクにアクセスできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94a6c-252">Both vendors have users, and you want all the users to have access to kiosks from both their own vendor and the other vendor.</span></span> <span data-ttu-id="94a6c-253">グループを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-253">You configure groups as follows:</span></span>

- <span data-ttu-id="94a6c-254">デバイスグループ 1:</span><span class="sxs-lookup"><span data-stu-id="94a6c-254">Device Group 1:</span></span>
  - <span data-ttu-id="94a6c-255">デバイス 1 (ベンダー 1)</span><span class="sxs-lookup"><span data-stu-id="94a6c-255">Device 1 (Vendor 1)</span></span>
  - <span data-ttu-id="94a6c-256">デバイス 2 (ベンダー 1)</span><span class="sxs-lookup"><span data-stu-id="94a6c-256">Device 2 (Vendor 1)</span></span>

- <span data-ttu-id="94a6c-257">デバイスグループ 2:</span><span class="sxs-lookup"><span data-stu-id="94a6c-257">Device Group 2:</span></span>
  - <span data-ttu-id="94a6c-258">デバイス 3 (ベンダー 2)</span><span class="sxs-lookup"><span data-stu-id="94a6c-258">Device 3 (Vendor 2)</span></span>
  - <span data-ttu-id="94a6c-259">デバイス 4 (ベンダー 2)</span><span class="sxs-lookup"><span data-stu-id="94a6c-259">Device 4 (Vendor 2)</span></span>

- <span data-ttu-id="94a6c-260">ユーザグループ:</span><span class="sxs-lookup"><span data-stu-id="94a6c-260">User Group:</span></span>
  - <span data-ttu-id="94a6c-261">ユーザー A (ベンダー 1)</span><span class="sxs-lookup"><span data-stu-id="94a6c-261">User A (Vendor 1)</span></span>
  - <span data-ttu-id="94a6c-262">ユーザー B (ベンダー 2)</span><span class="sxs-lookup"><span data-stu-id="94a6c-262">User B (Vendor 2)</span></span>

<span data-ttu-id="94a6c-263">次の設定の2つのキオスク構成プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-263">You create two kiosk configuration profiles that have the following settings:</span></span>

- <span data-ttu-id="94a6c-264">キオスクプロファイル 1:</span><span class="sxs-lookup"><span data-stu-id="94a6c-264">Kiosk Profile 1:</span></span>
   - <span data-ttu-id="94a6c-265">**ユーザーのログオンの種類**: ユーザーグループ</span><span class="sxs-lookup"><span data-stu-id="94a6c-265">**User logon type**: User Group</span></span>
   - <span data-ttu-id="94a6c-266">**割り当て済みグループ**: デバイスグループ1</span><span class="sxs-lookup"><span data-stu-id="94a6c-266">**Assigned group**: Device Group 1</span></span>

- <span data-ttu-id="94a6c-267">キオスクプロファイル 2:</span><span class="sxs-lookup"><span data-stu-id="94a6c-267">Kiosk Profile 2:</span></span>
   - <span data-ttu-id="94a6c-268">**ユーザーのログオンの種類**: ユーザーグループ</span><span class="sxs-lookup"><span data-stu-id="94a6c-268">**User logon type**: User Group</span></span>
   - <span data-ttu-id="94a6c-269">**割り当て済みグループ**: デバイスグループ2</span><span class="sxs-lookup"><span data-stu-id="94a6c-269">**Assigned group**: Device Group 2</span></span>

<span data-ttu-id="94a6c-270">これらの構成では、次のような結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-270">These configurations produce the following results:</span></span>

- <span data-ttu-id="94a6c-271">ユーザーがデバイス1またはデバイス2にサインインすると、Intune によってそのデバイスにキオスクプロファイル1が展開されます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-271">When any user signs in to Device 1 or Device 2, Intune deploys Kiosk Profile 1 to that device.</span></span>
- <span data-ttu-id="94a6c-272">ユーザーがデバイス3またはデバイス4にサインインすると、Intune によってそのデバイスにキオスクプロファイル2が展開されます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-272">When any user signs in to Device 3 or Device 4, Intune deploys Kiosk Profile 2 to that device.</span></span>
- <span data-ttu-id="94a6c-273">ユーザー A とユーザー B は、4つのデバイスのいずれかにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-273">User A and user B can sign in to any of the four devices.</span></span> <span data-ttu-id="94a6c-274">デバイス1またはデバイス2にサインインすると、ベンダー1のキオスクエクスペリエンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-274">If they sign in to Device 1 or Device 2, they see the Vendor 1 kiosk experience.</span></span> <span data-ttu-id="94a6c-275">デバイス3またはデバイス4にサインインした場合は、ベンダー2のキオスクエクスペリエンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-275">If they sign in to Device 3 or Device 4, they see the Vendor 2 kiosk experience.</span></span>

#### <span data-ttu-id="94a6c-276">プロファイルの競合</span><span class="sxs-lookup"><span data-stu-id="94a6c-276">Profile conflicts</span></span>

<span data-ttu-id="94a6c-277">2つ以上のキオスク構成プロファイルが同じデバイスをターゲットとしている場合、それらは競合します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-277">If two or more kiosk configuration profiles target the same device, they conflict.</span></span> <span data-ttu-id="94a6c-278">Intune で管理されているデバイスの場合、Intune は競合するプロファイルを適用しません。</span><span class="sxs-lookup"><span data-stu-id="94a6c-278">In the case of Intune-managed devices, Intune does not apply any of the conflicting profiles.</span></span>

<span data-ttu-id="94a6c-279">キオスク構成プロファイルに関連付けられていないデバイスの制限など、他の種類のプロファイルとポリシーは、キオスク構成プロファイルと競合しません。</span><span class="sxs-lookup"><span data-stu-id="94a6c-279">Other kinds of profiles and policies, such as device restrictions that are not related to the kiosk configuration profile, do not conflict with the kiosk configuration profile.</span></span>

### <span data-ttu-id="94a6c-280">展開方法を選択する</span><span class="sxs-lookup"><span data-stu-id="94a6c-280">Select a deployment method</span></span>

<span data-ttu-id="94a6c-281">キオスクの構成を展開するには、次のいずれかの方法を選択できます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-281">You can select one of the following methods to deploy kiosk configurations:</span></span>

- [<span data-ttu-id="94a6c-282">Microsoft Intune またはその他のモバイルデバイス管理 (MDM) サービス</span><span class="sxs-lookup"><span data-stu-id="94a6c-282">Microsoft Intune or other mobile device management (MDM) service</span></span>](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="94a6c-283">プロビジョニング パッケージ</span><span class="sxs-lookup"><span data-stu-id="94a6c-283">Provisioning package</span></span>](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="94a6c-284">Windows Device Portal</span><span class="sxs-lookup"><span data-stu-id="94a6c-284">Windows Device Portal</span></span>](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > <span data-ttu-id="94a6c-285">このメソッドでは、デバイスで開発者モードが有効になっている必要があるため、デモ用にのみ使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="94a6c-285">Because this method requires that Developer Mode be enabled on the device, we recommend that you use it only for demonstrations.</span></span>

<span data-ttu-id="94a6c-286">次の表に、各展開方法の機能と利点を示します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-286">The following table lists the capabilities and benefits of each of the deployment methods.</span></span>

| &nbsp; |<span data-ttu-id="94a6c-287">Windows Device Portal を使用して展開する</span><span class="sxs-lookup"><span data-stu-id="94a6c-287">Deploy by using Windows Device Portal</span></span> |<span data-ttu-id="94a6c-288">プロビジョニングパッケージを使用して展開する</span><span class="sxs-lookup"><span data-stu-id="94a6c-288">Deploy by using a provisioning package</span></span> |<span data-ttu-id="94a6c-289">MDM を使用して展開する</span><span class="sxs-lookup"><span data-stu-id="94a6c-289">Deploy by using MDM</span></span> |
| --------------------------- | ------------- | -------------------- | ---- |
|<span data-ttu-id="94a6c-290">単一アプリのキオスクの展開</span><span class="sxs-lookup"><span data-stu-id="94a6c-290">Deploy single-app kiosks</span></span>   | <span data-ttu-id="94a6c-291">あり</span><span class="sxs-lookup"><span data-stu-id="94a6c-291">Yes</span></span>           | <span data-ttu-id="94a6c-292">要</span><span class="sxs-lookup"><span data-stu-id="94a6c-292">Yes</span></span>                  | <span data-ttu-id="94a6c-293">要</span><span class="sxs-lookup"><span data-stu-id="94a6c-293">Yes</span></span>  |
|<span data-ttu-id="94a6c-294">複数アプリのキオスクの展開</span><span class="sxs-lookup"><span data-stu-id="94a6c-294">Deploy multi-app kiosks</span></span>    | <span data-ttu-id="94a6c-295">なし</span><span class="sxs-lookup"><span data-stu-id="94a6c-295">No</span></span>            | <span data-ttu-id="94a6c-296">あり</span><span class="sxs-lookup"><span data-stu-id="94a6c-296">Yes</span></span>                  | <span data-ttu-id="94a6c-297">要</span><span class="sxs-lookup"><span data-stu-id="94a6c-297">Yes</span></span>  |
|<span data-ttu-id="94a6c-298">ローカルデバイスのみに展開する</span><span class="sxs-lookup"><span data-stu-id="94a6c-298">Deploy to local devices only</span></span> | <span data-ttu-id="94a6c-299">あり</span><span class="sxs-lookup"><span data-stu-id="94a6c-299">Yes</span></span>           | <span data-ttu-id="94a6c-300">可</span><span class="sxs-lookup"><span data-stu-id="94a6c-300">Yes</span></span>                  | <span data-ttu-id="94a6c-301">×</span><span class="sxs-lookup"><span data-stu-id="94a6c-301">No</span></span>   |
|<span data-ttu-id="94a6c-302">開発者モードを使用して展開する</span><span class="sxs-lookup"><span data-stu-id="94a6c-302">Deploy by using Developer Mode</span></span> |<span data-ttu-id="94a6c-303">必須かどうか</span><span class="sxs-lookup"><span data-stu-id="94a6c-303">Required</span></span>       | <span data-ttu-id="94a6c-304">任意</span><span class="sxs-lookup"><span data-stu-id="94a6c-304">Not required</span></span>            | <span data-ttu-id="94a6c-305">任意</span><span class="sxs-lookup"><span data-stu-id="94a6c-305">Not required</span></span>   |
|<span data-ttu-id="94a6c-306">Azure Active Directory (AAD) を使用して展開する</span><span class="sxs-lookup"><span data-stu-id="94a6c-306">Deploy by using Azure Active Directory (AAD)</span></span>  | <span data-ttu-id="94a6c-307">任意</span><span class="sxs-lookup"><span data-stu-id="94a6c-307">Not required</span></span>            | <span data-ttu-id="94a6c-308">任意</span><span class="sxs-lookup"><span data-stu-id="94a6c-308">Not required</span></span>                   | <span data-ttu-id="94a6c-309">必須かどうか</span><span class="sxs-lookup"><span data-stu-id="94a6c-309">Required</span></span>  |
|<span data-ttu-id="94a6c-310">自動的に展開する</span><span class="sxs-lookup"><span data-stu-id="94a6c-310">Deploy automatically</span></span>      | <span data-ttu-id="94a6c-311">なし</span><span class="sxs-lookup"><span data-stu-id="94a6c-311">No</span></span>            | <span data-ttu-id="94a6c-312">なし</span><span class="sxs-lookup"><span data-stu-id="94a6c-312">No</span></span>                   | <span data-ttu-id="94a6c-313">あり</span><span class="sxs-lookup"><span data-stu-id="94a6c-313">Yes</span></span>  |
|<span data-ttu-id="94a6c-314">展開の速度</span><span class="sxs-lookup"><span data-stu-id="94a6c-314">Deployment speed</span></span>            | <span data-ttu-id="94a6c-315">すばやく</span><span class="sxs-lookup"><span data-stu-id="94a6c-315">Fastest</span></span>       | <span data-ttu-id="94a6c-316">Fast (高速)</span><span class="sxs-lookup"><span data-stu-id="94a6c-316">Fast</span></span>                 | <span data-ttu-id="94a6c-317">スロー (低速)</span><span class="sxs-lookup"><span data-stu-id="94a6c-317">Slow</span></span> |
|<span data-ttu-id="94a6c-318">Scale で展開する</span><span class="sxs-lookup"><span data-stu-id="94a6c-318">Deploy at scale</span></span> | <span data-ttu-id="94a6c-319">推奨されない</span><span class="sxs-lookup"><span data-stu-id="94a6c-319">Not recommended</span></span>    | <span data-ttu-id="94a6c-320">推奨されない</span><span class="sxs-lookup"><span data-stu-id="94a6c-320">Not recommended</span></span>        | <span data-ttu-id="94a6c-321">推奨</span><span class="sxs-lookup"><span data-stu-id="94a6c-321">Recommended</span></span> |

## <span data-ttu-id="94a6c-322">Microsoft Intune またはその他の MDM を使用して、1つのアプリまたは複数のアプリのキオスクを設定する</span><span class="sxs-lookup"><span data-stu-id="94a6c-322">Use Microsoft Intune or other MDM to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="94a6c-323">Microsoft Intune または別の MDM システムを使用してキオスクモードを設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-323">To set up kiosk mode by using Microsoft Intune or another MDM system, follow these steps.</span></span>

1. <span data-ttu-id="94a6c-324">[デバイスの登録を準備](#mdmenroll)します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-324">[Prepare to enroll the devices](#mdmenroll).</span></span>
1. <span data-ttu-id="94a6c-325">[キオスク構成プロファイルを作成](#mdmprofile)します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-325">[Create a kiosk configuration profile](#mdmprofile).</span></span>
1. <span data-ttu-id="94a6c-326">キオスクを構成します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-326">Configure the kiosk.</span></span>
   - <span data-ttu-id="94a6c-327">[単一アプリのキオスクの設定を構成](#mdmconfigsingle)します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-327">[Configure the settings for a single-app kiosk](#mdmconfigsingle).</span></span>
   - <span data-ttu-id="94a6c-328">[マルチアプリキオスクの設定を構成](#mdmconfigmulti)します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-328">[Configure the settings for a multi-app kiosk](#mdmconfigmulti).</span></span>
1. <span data-ttu-id="94a6c-329">[キオスクの構成プロファイルをグループに割り当て](#mdmassign)ます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-329">[Assign the kiosk configuration profile to a group](#mdmassign).</span></span>
1. <span data-ttu-id="94a6c-330">デバイスを展開します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-330">Deploy the devices.</span></span>
   - <span data-ttu-id="94a6c-331">[単一アプリのキオスクを展開](#mdmsingledeploy)します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-331">[Deploy a single-app kiosk](#mdmsingledeploy).</span></span>
   - <span data-ttu-id="94a6c-332">[複数アプリのキオスクを展開](#mdmmultideploy)します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-332">[Deploy a multi-app kiosk](#mdmmultideploy).</span></span>

### <a id="mdmenroll"></a><span data-ttu-id="94a6c-333">MDM、ステップ 1 &ndash; デバイスの登録を準備する</span><span class="sxs-lookup"><span data-stu-id="94a6c-333">MDM, step 1 &ndash; Prepare to enroll the devices</span></span>

<span data-ttu-id="94a6c-334">ユーザーが最初にサインインしたとき、またはユーザーがデバイスを手動で登録したときに HoloLens デバイスを自動的に登録するように MDM システムを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-334">You can configure your MDM system to enroll HoloLens devices automatically when the user first signs in, or have users enroll devices manually.</span></span> <span data-ttu-id="94a6c-335">また、デバイスは、Azure AD ドメインに参加し、適切なグループに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="94a6c-335">The devices also have to be joined to your Azure AD domain, and assigned to the appropriate groups.</span></span>

<span data-ttu-id="94a6c-336">デバイスの登録方法の詳細については、「MDM および[Windows デバイスの Intune 登録方法](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)[に HoloLens を登録](hololens-enroll-mdm.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-336">For more information about how to enroll the devices, see [Enroll HoloLens in MDM](hololens-enroll-mdm.md) and [Intune enrollment methods for Windows devices](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods).</span></span>

### <a id="mdmprofile"></a><span data-ttu-id="94a6c-337">MDM、手順 2: &ndash; キオスク構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="94a6c-337">MDM, step 2 &ndash; Create a kiosk configuration profile</span></span>

1. <span data-ttu-id="94a6c-338">[Azure](https://portal.azure.com/) portal を開いて、Intune 管理者アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="94a6c-338">Open the [Azure](https://portal.azure.com/) portal and sign in to your Intune administrator account.</span></span>
1. <span data-ttu-id="94a6c-339">[ **Microsoft Intune**  >  **デバイス構成-プロファイルの**  >  **作成プロファイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-339">Select **Microsoft Intune** > **Device configuration - Profiles** > **Create profile**.</span></span>
1. <span data-ttu-id="94a6c-340">プロファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-340">Enter a profile name.</span></span>
1. <span data-ttu-id="94a6c-341">[ **Platform**  >  **Windows 10**以降] を選択し、[**プロファイルの種類**のデバイスの制限] を選択し  > **Device restrictions**ます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-341">Select **Platform** > **Windows 10 and later**, and then select **Profile type** >**Device restrictions**.</span></span>
1. <span data-ttu-id="94a6c-342">[キオスクの**構成**] を選択し、  >  **Kiosk**次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-342">Select **Configure** > **Kiosk**, and then select one of the following:</span></span>
   - <span data-ttu-id="94a6c-343">単一アプリのキオスクを作成するには、[**キオスクモード**  >  **単一アプリキオスク**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-343">To create a single-app kiosk, select **Kiosk Mode** > **Single-app kiosk**.</span></span>
   - <span data-ttu-id="94a6c-344">マルチアプリキオスクを作成するには、[**キオスクモード**  >  **マルチアプリキオスク**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-344">To create a multi-app kiosk, select **Kiosk Mode** > **Multi-app kiosk**.</span></span>
1. <span data-ttu-id="94a6c-345">キオスクの構成を開始するには、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-345">To start configuring the kiosk, select **Add**.</span></span>

<span data-ttu-id="94a6c-346">次の手順は、必要なキオスクの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="94a6c-346">Your next steps differ depending on the type of kiosk that you want.</span></span> <span data-ttu-id="94a6c-347">詳細については、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-347">For more information, select one of the following options:</span></span>  

- [<span data-ttu-id="94a6c-348">単一アプリのキオスク</span><span class="sxs-lookup"><span data-stu-id="94a6c-348">Single-app kiosk</span></span>](#mdmconfigsingle)
- [<span data-ttu-id="94a6c-349">マルチアプリのキオスク</span><span class="sxs-lookup"><span data-stu-id="94a6c-349">Multi-app kiosk</span></span>](#mdmconfigmulti)

<span data-ttu-id="94a6c-350">キオスク構成プロファイルの作成方法の詳細については、「 [windows 10 と Windows ホログラフィック For Business デバイスの設定」を参照して、Intune を使って専用のキオスクとして実行](https://docs.microsoft.com/intune/configuration/kiosk-settings)してください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-350">For more information about how to create a kiosk configuration profile, see [Windows 10 and Windows Holographic for Business device settings to run as a dedicated kiosk using Intune](https://docs.microsoft.com/intune/configuration/kiosk-settings).</span></span>

### <a id="mdmconfigsingle"></a><span data-ttu-id="94a6c-351">MDM、ステップ 3 (単一アプリ) &ndash; 1 つのアプリのキオスクの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="94a6c-351">MDM, step 3 (single-app) &ndash;  Configure the settings for a single-app kiosk</span></span>

<span data-ttu-id="94a6c-352">このセクションでは、単一アプリのキオスクで必要な設定の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-352">This section summarizes the settings that a single-app kiosk requires.</span></span> <span data-ttu-id="94a6c-353">詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-353">For more details, see the following articles:</span></span>

- <span data-ttu-id="94a6c-354">Intune でキオスク構成プロファイルを構成する方法については、「 [Microsoft Intune を使用してキオスクモードを構成する方法](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-354">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="94a6c-355">Intune での単一アプリのキオスクで利用可能な設定について詳しくは、「[全画面表示アプリのキオスク](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-355">For more information about the available settings for single-app kiosks in Intune, see [Single full-screen app kiosks](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)</span></span>
- <span data-ttu-id="94a6c-356">その他の MDM サービスについては、使用しているプロバイダーのドキュメントで手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-356">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="94a6c-357">MDM サービスでユーザー設定の XML 構成を使用してキオスクを設定する必要がある場合は、[キオスクの構成を定義する xml ファイルを作成](#ppkioskconfig)します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-357">If you have to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span>

1. <span data-ttu-id="94a6c-358">[**ユーザーログオンの種類**の  >  **ローカルユーザーアカウント**] を選択し、キオスクにサインインできるローカル (デバイス) アカウントまたは Microsoft アカウント (MSA) のユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-358">Select **User logon type** > **Local user account**, and then enter the user name of the local (device) account or Microsoft Account (MSA) that can sign in to the kiosk.</span></span>
   > [!NOTE]  
   > <span data-ttu-id="94a6c-359">**自動ログオン**ユーザーアカウントの種類は、Windows ホログラフィック for Business ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="94a6c-359">**Autologon** user account types aren't supported on Windows Holographic for Business.</span></span>
1. <span data-ttu-id="94a6c-360">[ **Application type**  >  **Store アプリ**] を選び、一覧からアプリを選びます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-360">Select **Application type** > **Store app**, and then select an app from the list.</span></span>

<span data-ttu-id="94a6c-361">次の手順では、プロファイルをグループに[割り当て](#mdmassign)ます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-361">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a id="mdmconfigmulti"></a><span data-ttu-id="94a6c-362">MDM、手順 3 (マルチアプリ) &ndash; マルチアプリキオスクの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="94a6c-362">MDM, step 3 (multi-app) &ndash; Configure the settings for a multi-app kiosk</span></span>

<span data-ttu-id="94a6c-363">このセクションでは、マルチアプリのキオスクで必要な設定の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-363">This section summarizes the settings that a multi-app kiosk requires.</span></span> <span data-ttu-id="94a6c-364">詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-364">For more detailed information, see the following articles:</span></span>

- <span data-ttu-id="94a6c-365">Intune でキオスク構成プロファイルを構成する方法については、「 [Microsoft Intune を使用してキオスクモードを構成する方法](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-365">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="94a6c-366">Intune でのマルチアプリキオスクで利用可能な設定の詳細については、「[マルチアプリキオスク](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-366">For more information about the available settings for multi-app kiosks in Intune, see [Multi-app kiosks](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)</span></span>
- <span data-ttu-id="94a6c-367">その他の MDM サービスについては、使用しているプロバイダーのドキュメントで手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-367">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="94a6c-368">カスタム XML 構成を使用して、MDM サービスでキオスクを設定する必要がある場合は、[キオスクの構成を定義する xml ファイルを作成](#ppkioskconfig)します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-368">If you need to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span> <span data-ttu-id="94a6c-369">XML ファイルを使用する場合は、[[開始] レイアウト](#start-layout-for-hololens)を含めるようにします。</span><span class="sxs-lookup"><span data-stu-id="94a6c-369">If you use an XML file, make sure to include the [Start layout](#start-layout-for-hololens).</span></span>  
- <span data-ttu-id="94a6c-370">必要に応じて、Intune またはその他の MDM サービスでカスタム開始レイアウトを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-370">You can optionally use a custom Start layout with Intune or other MDM services.</span></span> <span data-ttu-id="94a6c-371">詳細については、「 [MDM のレイアウトファイルを開始する (Intune など)](#start-layout-file-for-mdm-intune-and-others)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-371">For more information, see [Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

1. <span data-ttu-id="94a6c-372">**S モードデバイスのターゲット Windows 10**を選択し  >  **No**ます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-372">Select **Target Windows 10 in S mode devices** > **No**.</span></span>  
   >[!NOTE]  
   > <span data-ttu-id="94a6c-373">S モードは、Windows ホログラフィック for Business ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="94a6c-373">S mode isn't supported on Windows Holographic for Business.</span></span>
1. <span data-ttu-id="94a6c-374">[**ユーザーログオンの種類**] を選択し、[  >  **Azure AD ユーザー] また**は [グループ] または [**ユーザーログオンの種類**] を選び  >  ます。次に、1つ**以上の**ユーザーグループまたはアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-374">Select **User logon type** > **Azure AD user or group** or **User logon type** > **HoloLens visitor**, and then add one or more user groups or accounts.</span></span>  

   <span data-ttu-id="94a6c-375">**ユーザーのログオンの種類**で指定したグループまたはアカウントに属しているユーザーのみが、キオスクのエクスペリエンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-375">Only users who belong to the groups or accounts that you specify in **User logon type** can use the kiosk experience.</span></span>

1. <span data-ttu-id="94a6c-376">次のオプションを使用して、1つまたは複数のアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-376">Select one or more apps by using the following options:</span></span>
   - <span data-ttu-id="94a6c-377">アップロードした基幹業務アプリを追加するには、[**ストアアプリの追加**] を選択し、目的のアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-377">To add an uploaded line-of-business app, select **Add store app** and then select the app that you want.</span></span>
   - <span data-ttu-id="94a6c-378">AUMID を指定してアプリを追加するには、[ **AUMID によって追加**] を選択し、アプリの AUMID を入力します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-378">To add an app by specifying its AUMID, select **Add by AUMID** and then enter the AUMID of the app.</span></span> [<span data-ttu-id="94a6c-379">利用可能な Aumid のリストを表示する</span><span class="sxs-lookup"><span data-stu-id="94a6c-379">See the list of available AUMIDs</span></span>](#aumids)

<span data-ttu-id="94a6c-380">次の手順では、プロファイルをグループに[割り当て](#mdmassign)ます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-380">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a id="mdmassign"></a><span data-ttu-id="94a6c-381">MDM、手順 4 &ndash; グループにキオスク構成プロファイルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="94a6c-381">MDM, step 4 &ndash; Assign the kiosk configuration profile to a group</span></span>

<span data-ttu-id="94a6c-382">キオスク構成プロファイルの [**課題**] ページを使用して、キオスクの構成を展開する場所を設定します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-382">Use the **Assignments** page of the kiosk configuration profile to set where you want the kiosk configuration to deploy.</span></span> <span data-ttu-id="94a6c-383">最も単純なケースでは、MDM にデバイスを登録するときに、HoloLens デバイスを含むグループにキオスク構成プロファイルを割り当てることになります。</span><span class="sxs-lookup"><span data-stu-id="94a6c-383">In the simplest case, you assign the kiosk configuration profile to a group that will contain the HoloLens device when the device enrolls in MDM.</span></span>

### <a id="mdmsingledeploy"></a><span data-ttu-id="94a6c-384">MDM、ステップ 5 (単一アプリ) &ndash; 1 つのアプリでのキオスクの展開</span><span class="sxs-lookup"><span data-stu-id="94a6c-384">MDM, step 5 (single-app) &ndash; Deploy a single-app kiosk</span></span>

<span data-ttu-id="94a6c-385">MDM システムを使用する場合は、OOBE 中に MDM にデバイスを登録することができます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-385">When you use an MDM system, you can enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="94a6c-386">OOBE が終了したら、デバイスへのサインインは簡単です。</span><span class="sxs-lookup"><span data-stu-id="94a6c-386">After OOBE finishes, signing in to the device is easy.</span></span>

<span data-ttu-id="94a6c-387">OOBE 中に、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-387">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="94a6c-388">キオスク構成プロファイルで指定したアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="94a6c-388">Sign in by using the account that you specified in the kiosk configuration profile.</span></span>
1. <span data-ttu-id="94a6c-389">デバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-389">Enroll the device.</span></span> <span data-ttu-id="94a6c-390">キオスク構成プロファイルが割り当てられているグループに、デバイスが追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-390">Make sure that the device is added to the group that the kiosk configuration profile is assigned to.</span></span>
1. <span data-ttu-id="94a6c-391">OOBE が完了するのを待って、ストアアプリがダウンロードとインストールを行い、ポリシーが適用されるようにします。</span><span class="sxs-lookup"><span data-stu-id="94a6c-391">Wait for OOBE to finish, for the store app to download and install, and for policies to be applied.</span></span> <span data-ttu-id="94a6c-392">次に、デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-392">Then restart the device.</span></span>

<span data-ttu-id="94a6c-393">次にデバイスにサインインしたときに、キオスクアプリが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-393">The next time you sign in to the device, the kiosk app should automatically start.</span></span>

<span data-ttu-id="94a6c-394">この時点でキオスクの設定が表示されない場合は、[課題の状態を確認](https://docs.microsoft.com/intune/configuration/device-profile-monitor)してください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-394">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

### <a id="mdmmultideploy"></a><span data-ttu-id="94a6c-395">MDM、ステップ 5 (マルチアプリ) に &ndash; よるマルチアプリキオスクの展開</span><span class="sxs-lookup"><span data-stu-id="94a6c-395">MDM, step 5 (multi-app) &ndash; Deploy a multi-app kiosk</span></span>

<span data-ttu-id="94a6c-396">MDM システムを使用する場合は、デバイスを Azure AD テナントに参加させることができます。また、OOBE 中に MDM にデバイスを登録することもできます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-396">When you use an MDM system, you can join the device to your Azure AD tenant and enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="94a6c-397">必要に応じて、ユーザーに登録情報を提供します。これにより、そのユーザーは、OOBE プロセスで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="94a6c-397">If appropriate, provide the enrollment information to the users so that they have it available during the OOBE process.</span></span>

> [!NOTE]  
> <span data-ttu-id="94a6c-398">ユーザーを含むグループに [キオスク構成] プロファイルが割り当てられている場合は、これらのいずれかのユーザーアカウントが、デバイスにサインインする最初のアカウントであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-398">If you have assigned the kiosk configuration profile to a group that contains users, make sure that one of those user accounts is the first account to sign in to the device.</span></span>

<span data-ttu-id="94a6c-399">OOBE 中に、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-399">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="94a6c-400">[**ユーザーログオンの種類**] グループに属しているアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="94a6c-400">Sign in by using the account that belongs to the **User logon type** group.</span></span>
1. <span data-ttu-id="94a6c-401">デバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-401">Enroll the device.</span></span>
1. <span data-ttu-id="94a6c-402">キオスク構成プロファイルに含まれているすべてのアプリについて、ダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="94a6c-402">Wait for any apps that are part of the kiosk configuration profile to download and install.</span></span> <span data-ttu-id="94a6c-403">また、ポリシーが適用されるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-403">Also, wait for policies to be applied.</span></span>  
1. <span data-ttu-id="94a6c-404">OOBE が完了したら、Microsoft ストアまたはサイドローディングから追加のアプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-404">After OOBE finishes, you can install additional apps from the Microsoft store or by sideloading.</span></span> <span data-ttu-id="94a6c-405">デバイスが属しているグループに[必要なアプリ](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)が自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-405">[Required apps](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) for the group that the device belongs to install automatically.</span></span>
1. <span data-ttu-id="94a6c-406">インストールが完了したら、デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-406">After the installation finishes, restart the device.</span></span>

<span data-ttu-id="94a6c-407">次に、**ユーザーのログオンの種類**に属するアカウントを使用してデバイスにサインインすると、キオスクアプリが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-407">The next time you sign in to the device by using an account that belongs to the **User logon type**, the kiosk app should automatically launch.</span></span>

<span data-ttu-id="94a6c-408">この時点でキオスクの設定が表示されない場合は、[課題の状態を確認](https://docs.microsoft.com/intune/configuration/device-profile-monitor)してください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-408">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

## <span data-ttu-id="94a6c-409">プロビジョニングパッケージを使用して1つのアプリまたは複数のアプリのキオスクを設定する</span><span class="sxs-lookup"><span data-stu-id="94a6c-409">Use a provisioning package to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="94a6c-410">プロビジョニングパッケージを使用してキオスクモードを設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-410">To set up kiosk mode by using a provisioning package, follow these steps.</span></span>

1. <span data-ttu-id="94a6c-411">[キオスクの構成を定義する XML ファイルを作成します。](#ppkioskconfig)これには、[開始レイアウト](#start-layout-for-hololens)も含まれます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-411">[Create an XML file that defines the kiosk configuration.](#ppkioskconfig), including a [Start layout](#start-layout-for-hololens).</span></span>
2. [<span data-ttu-id="94a6c-412">プロビジョニングパッケージに XML ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-412">Add the XML file to a provisioning package.</span></span>](#ppconfigadd)
3. [<span data-ttu-id="94a6c-413">HoloLens にプロビジョニングパッケージを適用します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-413">Apply the provisioning package to HoloLens.</span></span>](#ppapply)

### <a id="ppkioskconfig"></a><span data-ttu-id="94a6c-414">プロビジョニングパッケージ、手順 1 &ndash; キオスク構成の XML ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="94a6c-414">Provisioning package, step 1 &ndash; Create a kiosk configuration XML file</span></span>

<span data-ttu-id="94a6c-415">次の点を除き、[一般的な手順に従って、Windows デスクトップ用のキオスク構成の XML ファイルを作成](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-415">Follow [the general instructions to create a kiosk configuration XML file for Windows desktop](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file), except for the following:</span></span>

- <span data-ttu-id="94a6c-416">クラシック Windows アプリケーション (Win32) は含まれません。</span><span class="sxs-lookup"><span data-stu-id="94a6c-416">Do not include Classic Windows applications (Win32).</span></span> <span data-ttu-id="94a6c-417">HoloLens はこれらのアプリケーションをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="94a6c-417">HoloLens does not support these applications.</span></span>
- <span data-ttu-id="94a6c-418">HoloLens 用の[プレースホルダーの開始レイアウト XML](#start-layout-for-hololens)を使用します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-418">Use the [placeholder Start layout XML](#start-layout-for-hololens) for HoloLens.</span></span>
- <span data-ttu-id="94a6c-419">オプション: キオスクの構成へのゲストアクセスの追加</span><span class="sxs-lookup"><span data-stu-id="94a6c-419">Optional: Add guest access to the kiosk configuration</span></span>

#### <a id="ppkioskguest"></a><span data-ttu-id="94a6c-420">オプション: キオスクの構成へのゲストアクセスの追加</span><span class="sxs-lookup"><span data-stu-id="94a6c-420">Optional: Add guest access to the kiosk configuration</span></span>

<span data-ttu-id="94a6c-421">[XML ファイルの **[構成**] セクション](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)で、[ゲスト] という名前の特別なグループを構成して、ゲストがキオスクを使用できるよう**にすること**ができます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-421">In the [**Configs** section of the XML file](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs), you can configure a special group named **Visitor** to allow guests to use the kiosk.</span></span> <span data-ttu-id="94a6c-422">**ユーザー**設定の特殊グループをサポートするようにキオスクを構成すると、サインインページに "**ゲスト**" オプションが追加されます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-422">When the kiosk is configured to support the **Visitor** special group, a "**Guest**" option is added to the sign-in page.</span></span> <span data-ttu-id="94a6c-423">**Guest**アカウントではパスワードは必要ありません。また、アカウントに関連付けられているすべてのデータは、アカウントのサインアウト時に削除されます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-423">The **Guest** account does not require a password, and any data that is associated with the account is deleted when the account signs out.</span></span>

<span data-ttu-id="94a6c-424">**ゲスト**アカウントを有効にするには、次のスニペットをキオスク構成 XML に追加します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-424">To enable the **Guest** account, add the following snippet to your kiosk configuration XML:</span></span>

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a><span data-ttu-id="94a6c-425">HoloLens のプレースホルダーの開始のレイアウト</span><span class="sxs-lookup"><span data-stu-id="94a6c-425">Placeholder Start layout for HoloLens</span></span>

<span data-ttu-id="94a6c-426">[プロビジョニングパッケージ](##use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)を使ってマルチアプリのキオスクを構成する場合は、この手順で開始レイアウトが必要になります。</span><span class="sxs-lookup"><span data-stu-id="94a6c-426">If you use a [provisioning package](##use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) to configure a multi-app kiosk, the procedure requires a Start layout.</span></span> <span data-ttu-id="94a6c-427">スタート画面のレイアウトのカスタマイズは、Windows ホログラフィック for Business ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="94a6c-427">Start layout customization isn't supported in Windows Holographic for Business.</span></span> <span data-ttu-id="94a6c-428">そのため、プレースホルダーの開始レイアウトを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94a6c-428">Therefore, you'll have to use a placeholder Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="94a6c-429">1つのアプリのキオスクでは、ユーザーがサインインしたときにキオスクアプリが起動されるため、スタートメニューを使っていないため、開始レイアウトを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="94a6c-429">Because a single-app kiosk starts the kiosk app when a user signs in, it does not use a Start menu and does not have to have a Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="94a6c-430">[MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)を使ってマルチアプリのキオスクを設定する場合は、必要に応じて開始レイアウトを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-430">If you use [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) to set up a multi-app kiosk, you can optionally use a Start layout.</span></span> <span data-ttu-id="94a6c-431">詳細については、「 [MDM (Intune およびその他) のプレースホルダーの開始レイアウトファイル](#start-layout-file-for-mdm-intune-and-others)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-431">For more information, see [Placeholder Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

<span data-ttu-id="94a6c-432">開始レイアウトの場合は、次の**startlayout**セクションを KIOSK provisioning XML ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-432">For the Start layout, add the following **StartLayout** section to the kiosk provisioning XML file:</span></span>

```xml
<!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
            <StartLayout>
                <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
                      <LayoutOptions StartTileGroupCellWidth="6" />
                      <DefaultLayoutOverride>
                        <StartLayoutCollection>
                          <defaultlayout:StartLayout GroupCellWidth="6">
                            <start:Group Name="">
                              <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
                            </start:Group>
                          </defaultlayout:StartLayout>
                        </StartLayoutCollection>
                      </DefaultLayoutOverride>
                    </LayoutModificationTemplate>
                ]]>
            </StartLayout>
            <!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
```

#### <a id="start-layout-file-for-mdm-intune-and-others"></a><span data-ttu-id="94a6c-433">MDM (Intune およびその他) のプレースホルダーの開始レイアウトファイル</span><span class="sxs-lookup"><span data-stu-id="94a6c-433">Placeholder Start layout file for MDM (Intune and others)</span></span>

<span data-ttu-id="94a6c-434">次のサンプルを XML ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-434">Save the following sample as an XML file.</span></span> <span data-ttu-id="94a6c-435">このファイルは、Microsoft Intune (またはキオスクプロファイルを提供する別の MDM サービス) でマルチアプリキオスクを構成するときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-435">You can use this file when you configure the multi-app kiosk in Microsoft Intune (or in another MDM service that provides a kiosk profile).</span></span>

> [!NOTE]
> <span data-ttu-id="94a6c-436">カスタム設定と完全な XML 構成を使って MDM サービスでキオスクを設定する必要がある場合は、[プロビジョニングパッケージの開始レイアウトの手順](#start-layout-for-hololens)を使用します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-436">If you have to use a custom setting and full XML configuration to set up a kiosk in your MDM service, use the [Start layout instructions for a provisioning package](#start-layout-for-hololens).</span></span>

```xml
<LayoutModificationTemplate
    xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"
    xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout"
    xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout"
    Version="1">
  <RequiredStartGroupsCollection>
    <RequiredStartGroups>
      <AppendGroup Name="">
        <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
      </AppendGroup>
    </RequiredStartGroups>
  </RequiredStartGroupsCollection>
 </LayoutModificationTemplate>
```

### <a id="ppconfigadd"></a><span data-ttu-id="94a6c-437">Prov.xml.</span><span class="sxs-lookup"><span data-stu-id="94a6c-437">Prov.</span></span> <span data-ttu-id="94a6c-438">パッケージ、手順2「 &ndash; キオスク構成 XML ファイルをプロビジョニングパッケージに追加する」</span><span class="sxs-lookup"><span data-stu-id="94a6c-438">package, step 2 &ndash; Add the kiosk configuration XML file to a provisioning package</span></span>

1. <span data-ttu-id="94a6c-439">[Windows 構成デザイナー](https://www.microsoft.com/store/apps/9nblggh4tx22)を開きます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-439">Open [Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22).</span></span>
1. <span data-ttu-id="94a6c-440">[ **Advanced provisioning**] を選んで、プロジェクトの名前を入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-440">Select **Advanced provisioning**, enter a name for your project, and then select **Next**.</span></span>
1. <span data-ttu-id="94a6c-441">[ **Windows 10 ホログラフィック**] を選び、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-441">Select **Windows 10 Holographic**, and then select **Next**.</span></span>
1. <span data-ttu-id="94a6c-442">[**完了**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-442">Select **Finish**.</span></span> <span data-ttu-id="94a6c-443">パッケージのワークスペースが開きます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-443">The workspace for your package opens.</span></span>
1. <span data-ttu-id="94a6c-444">[ **Runtime settings**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-444">Select **Runtime settings** > **AssignedAccess** > **MultiAppAssignedAccessSettings**.</span></span>
1. <span data-ttu-id="94a6c-445">中央のウィンドウで、[**参照**] を選択して、作成したキオスク構成の XML ファイルを見つけて選択します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-445">In the center pane, select **Browse** to locate and select the kiosk configuration XML file that you created.</span></span>

   ![Windows 構成デザイナーにおける MultiAppAssignedAccessSettings フィールドのスクリーンショット](./images/multiappassignedaccesssettings.png)

1. <span data-ttu-id="94a6c-447">**省略可能**。</span><span class="sxs-lookup"><span data-stu-id="94a6c-447">**Optional**.</span></span> <span data-ttu-id="94a6c-448">(デバイスの最初のセットアップ後にプロビジョニングパッケージを適用する場合、キオスクデバイスで既に管理者ユーザーが利用可能である場合は、この手順をスキップします)。[**ランタイム設定**アカウントユーザー] を選択し、 &gt; **Accounts** &gt; **Users**ユーザーアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-448">(If you want to apply the provisioning package after the initial setup of the device, and there is an admin user already available on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a user account.</span></span> <span data-ttu-id="94a6c-449">ユーザー名とパスワードを入力して、[ **UserGroup**  >  **管理者**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-449">Provide a user name and password, and then select **UserGroup** > **Administrators**.</span></span>  
  
     <span data-ttu-id="94a6c-450">このアカウントを使用すると、プロビジョニングの状態とログを表示できます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-450">By using this account, you can view the provisioning status and logs.</span></span>  
1. <span data-ttu-id="94a6c-451">**省略可能**。</span><span class="sxs-lookup"><span data-stu-id="94a6c-451">**Optional**.</span></span> <span data-ttu-id="94a6c-452">(キオスクデバイスで管理者以外のアカウントを既に持っている場合は、この手順をスキップします)。[**ランタイム設定**アカウントユーザー] を選択し &gt; **Accounts** &gt; **Users**、ローカルユーザーアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-452">(If you already have a non-admin account on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a local user account.</span></span> <span data-ttu-id="94a6c-453">ユーザー名が、構成 XML で指定したアカウントと同じであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-453">Make sure that the user name is the same as for the account that you specify in the configuration XML.</span></span> <span data-ttu-id="94a6c-454">[ **UserGroup**  >  **Standard ユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-454">Select **UserGroup** > **Standard Users**.</span></span>
1. <span data-ttu-id="94a6c-455">[**ファイル**  >  の**保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-455">Select **File** > **Save**.</span></span>
1. <span data-ttu-id="94a6c-456">[ **Export**  >  **プロビジョニングパッケージ**のエクスポート] を選択し、[**所有者**の  >  **IT 管理**者] を選択します。これにより、このプロビジョニングパッケージの優先順位が、他のソースからこのデバイスに適用されるプロビジョニングパッケージよりも高くなります。</span><span class="sxs-lookup"><span data-stu-id="94a6c-456">Select **Export** > **Provisioning package**, and then select **Owner** > **IT Admin**. This sets the precedence of this provisioning package higher than provisioning packages that are applied to this device from other sources.</span></span>
1. <span data-ttu-id="94a6c-457">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-457">Select **Next**.</span></span>
1. <span data-ttu-id="94a6c-458">[**プロビジョニングパッケージのセキュリティ**] ページで、セキュリティオプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-458">On the **Provisioning package security** page, select a security option.</span></span>
   > [!IMPORTANT]  
   > <span data-ttu-id="94a6c-459">[**パッケージ署名を有効**にする] を選択した場合は、パッケージの署名に使用する有効な証明書を選択する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="94a6c-459">If you select **Enable package signing**, you also have to select a valid certificate to use for signing the package.</span></span> <span data-ttu-id="94a6c-460">これを行うには、[**参照**] を選択し、パッケージの署名に使用する証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-460">To do this, select **Browse** and select the certificate that you want to use to sign the package.</span></span>
   
   > [!CAUTION]  
   > <span data-ttu-id="94a6c-461">[パッケージの**暗号化を有効にする**] を選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-461">Do not select **Enable package encryption**.</span></span> <span data-ttu-id="94a6c-462">HoloLens デバイスでは、この設定によってプロビジョニングが失敗します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-462">On HoloLens devices, this setting causes provisioning to fail.</span></span>
1. <span data-ttu-id="94a6c-463">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-463">Select **Next**.</span></span>
1. <span data-ttu-id="94a6c-464">プロビジョニングパッケージをビルドするときの出力場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-464">Specify the output location where you want the provisioning package to go when it's built.</span></span> <span data-ttu-id="94a6c-465">既定では、Windows 構成デザイナーはプロジェクト フォルダーを出力先として使います。</span><span class="sxs-lookup"><span data-stu-id="94a6c-465">By default, Windows Configuration Designer uses the project folder as the output location.</span></span> <span data-ttu-id="94a6c-466">出力場所を変更する場合は、[**参照**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-466">If you want to change the output location, select **Browse**.</span></span> <span data-ttu-id="94a6c-467">完了したら、[**次へ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-467">When you are finished, select **Next**.</span></span>
1. <span data-ttu-id="94a6c-468">[**ビルド**] を選択して、パッケージの作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-468">Select **Build** to start building the package.</span></span> <span data-ttu-id="94a6c-469">プロビジョニング パッケージのビルドにはそれほど時間はかかりません。</span><span class="sxs-lookup"><span data-stu-id="94a6c-469">The provisioning package doesn't take long to build.</span></span> <span data-ttu-id="94a6c-470">ビルドページにプロジェクト情報が表示され、進行状況バーにはビルドの状態が示されます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-470">The build page displays the project information, and the progress bar indicates the build status.</span></span>

### <a id="ppapply"></a><span data-ttu-id="94a6c-471">プロビジョニングパッケージ、手順 3 &ndash; プロビジョニングパッケージを HoloLens に適用する</span><span class="sxs-lookup"><span data-stu-id="94a6c-471">Provisioning package, step 3 &ndash; Apply the provisioning package to HoloLens</span></span>

<span data-ttu-id="94a6c-472">「プロビジョニングパッケージを使って HoloLens を構成する」の記事では、次のような状況でプロビジョニングパッケージを適用するための詳しい手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-472">The "Configure HoloLens by using a provisioning package" article provides detailed instructions to apply the provisioning package under the following circumstances:</span></span>

- <span data-ttu-id="94a6c-473">[セットアップ時に、最初にプロビジョニングパッケージを HoloLens に適用](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)することができます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-473">You can initially [apply a provisioning package to HoloLens during setup](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).</span></span>

- <span data-ttu-id="94a6c-474">[セットアップ後に、プロビジョニングパッケージを HoloLens に適用](hololens-provisioning.md#4-apply-a-provisioning-package-to-hololens-after-setup)することもできます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-474">You can also [apply a provisioning package to HoloLens after setup](hololens-provisioning.md#4-apply-a-provisioning-package-to-hololens-after-setup).</span></span>

## <span data-ttu-id="94a6c-475">Windows Device Portal を使用して単一アプリのキオスクを設定する</span><span class="sxs-lookup"><span data-stu-id="94a6c-475">Use the Windows Device Portal to set up a single-app kiosk</span></span>

<span data-ttu-id="94a6c-476">Windows Device Portal を使用してキオスクモードを設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-476">To set up kiosk mode by using the Windows Device Portal, follow these steps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94a6c-477">キオスクモードは、デバイスに[Windows ホログラフィック For Business](hololens1-upgrade-enterprise.md)がインストールされている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-477">Kiosk mode is available only if the device has [Windows Holographic for Business](hololens1-upgrade-enterprise.md) installed.</span></span>

1. <span data-ttu-id="94a6c-478">[Windows Device Portal を使用するように HoloLens デバイス](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="94a6c-478">[Set up the HoloLens device to use the Windows Device Portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal).</span></span> <span data-ttu-id="94a6c-479">デバイス ポータルは、お使いの PC に Web ブラウザーから接続することができる HoloLens 上の Web サーバーです。</span><span class="sxs-lookup"><span data-stu-id="94a6c-479">The Device Portal is a web server on your HoloLens that you can connect to from a web browser on your PC.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="94a6c-480">HoloLens で Device Portal を使うように設定する場合は、デバイスで開発者モードを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94a6c-480">When you set up HoloLens to use the Device Portal, you have to enable Developer Mode on the device.</span></span> <span data-ttu-id="94a6c-481">Windows ホログラフィック for Business がインストールされているデバイスの開発者モードでは、アプリをサイドロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-481">Developer Mode on a device that has Windows Holographic for Business enables you to side-load apps.</span></span> <span data-ttu-id="94a6c-482">ただし、この設定では、Microsoft Store によって認定されていないアプリをユーザーがインストールできるというリスクが生じます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-482">However, this setting creates a risk that a user can install apps that have not been certified by the Microsoft Store.</span></span> <span data-ttu-id="94a6c-483">管理者は、[ポリシー CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)の**Applicationmanagement/allowdeveloper Unlock**設定を使用して、開発者モードを有効にする機能をブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-483">Administrators can block the ability to enable Developer Mode by using the **ApplicationManagement/AllowDeveloper Unlock** setting in the [Policy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider).</span></span> [<span data-ttu-id="94a6c-484">開発者モードの詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-484">Learn more about Developer Mode.</span></span>](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. <span data-ttu-id="94a6c-485">コンピューターで、 [wi-fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi)または[USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)を使って HoloLens に接続します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-485">On a computer, connect to the HoloLens by using [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) or [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb).</span></span>

1. <span data-ttu-id="94a6c-486">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="94a6c-486">Do one of the following:</span></span>
   - <span data-ttu-id="94a6c-487">Windows Device Portal に初めて接続している場合は、[ユーザー名とパスワードを作成](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)する</span><span class="sxs-lookup"><span data-stu-id="94a6c-487">If you are connecting to the Windows Device Portal for the first time, [create a user name and password](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)</span></span>
   - <span data-ttu-id="94a6c-488">以前に設定したユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-488">Enter the user name and password that you previously set up.</span></span>

    > [!TIP]
    > <span data-ttu-id="94a6c-489">ブラウザーに証明書エラーが表示された場合は、[こちらのトラブルシューティング手順](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)に従います。</span><span class="sxs-lookup"><span data-stu-id="94a6c-489">If you see a certificate error in the browser, follow [these troubleshooting steps](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate).</span></span>

1. <span data-ttu-id="94a6c-490">Windows Device Portal で、[**キオスクモード**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-490">In the Windows Device Portal, select **Kiosk Mode**.</span></span>

1. <span data-ttu-id="94a6c-491">[**キオスクモードを有効**にする] を選択し、デバイスの起動時に実行するアプリを選択して、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-491">Select **Enable Kiosk Mode**, select an app to run when the device starts, and then select **Save**.</span></span>

    ![Kiosk Mode (キオスク モード)](images/kiosk.png)
1. <span data-ttu-id="94a6c-493">HoloLens を再起動します。</span><span class="sxs-lookup"><span data-stu-id="94a6c-493">Restart HoloLens.</span></span> <span data-ttu-id="94a6c-494">まだデバイスポータルページを開いている場合は、ページの上部にある [**再起動**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="94a6c-494">If you still have your Device Portal page open, you can select **Restart** at the top of the page.</span></span>

## <span data-ttu-id="94a6c-495">詳細情報</span><span class="sxs-lookup"><span data-stu-id="94a6c-495">More information</span></span>

<span data-ttu-id="94a6c-496">プロビジョニングパッケージを使用して、キオスクを構成する方法をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="94a6c-496">Watch how to configure a kiosk by using a provisioning package.</span></span>  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]
