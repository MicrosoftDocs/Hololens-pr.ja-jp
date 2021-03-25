---
title: 展開ガイド – Dynamics 365 ガイドを使用した企業接続 HoloLens 2 - Maintain
description: Dynamics 365 Guides を使用して企業の接続ネットワークを使用して HoloLens 2 デバイスを維持する方法について学習します。
keywords: HoloLens、管理、企業接続、Dynamics 365 ガイド、AAD、Azure AD、MDM、モバイル デバイス管理
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f231e65e17ab053e34e7174e1ed7ff6e7a0a56b8
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448584"
---
# <a name="maintain---corporate-connected-guide"></a><span data-ttu-id="09677-104">メンテナンス - 企業向けコネクテッド ガイド</span><span class="sxs-lookup"><span data-stu-id="09677-104">Maintain - Corporate Connected Guide</span></span>

## <a name="update-hololens"></a><span data-ttu-id="09677-105">HoloLens を更新する</span><span class="sxs-lookup"><span data-stu-id="09677-105">Update HoloLens</span></span>

<span data-ttu-id="09677-106">Windows Update for Business は、IT 管理者に対して Windows Update を中心とした追加の管理機能を提供するように設計されています。これには、更新プログラムをデバイスのグループに展開する機能や、更新プログラムをインストールするためのメンテナンス ウィンドウを定義する機能などが含まれています。</span><span class="sxs-lookup"><span data-stu-id="09677-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="09677-107">更新プログラムを管理する一般的な方法の 1 つは、30 日間の機能の延期を行う方法です。</span><span class="sxs-lookup"><span data-stu-id="09677-107">One popular method of managing updates is to do a feature deferral of 30 days.</span></span> <span data-ttu-id="09677-108">これにより、管理者は新機能を更新してプレビューし、最初の手で知識を得て、新しい変更をサポート デスクに通知できます。</span><span class="sxs-lookup"><span data-stu-id="09677-108">This allows Admins to update and preview new features, gaining first hand knowledge and informing your support desk of any new changes.</span></span>

<span data-ttu-id="09677-109">[HoloLens](https://docs.microsoft.com/hololens/hololens-updates)更新プログラム (スケジュールされた日、スケジュールされた時刻、デバイスのアクティブな時間の設定など) を管理して、勤務時間外に更新する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="09677-109">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates), including scheduled days, scheduled time, and setting active hours on the device, so it will update outside of working hours.</span></span>

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a><span data-ttu-id="09677-110">Dynamics 365 ガイド (および他のストア アプリ) を更新する方法</span><span class="sxs-lookup"><span data-stu-id="09677-110">How to update Dynamics 365 Guides (and other store apps)</span></span>

<span data-ttu-id="09677-111">Dynamics 365 Guides は、In-Boxアプリであり、Microsoft Store アプリを通じて更新できます。</span><span class="sxs-lookup"><span data-stu-id="09677-111">Dynamics 365 Guides is an In-Box app, and can be updated through the Microsoft Store app.</span></span> <span data-ttu-id="09677-112">Microsoft Store を通じてダウンロードされたアプリはすべて [、Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) アプリ自体を介して手動で更新できます。</span><span class="sxs-lookup"><span data-stu-id="09677-112">For all apps that are downloaded through the Microsoft Store, they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="how-to-update-lob-apps"></a><span data-ttu-id="09677-113">LOB アプリを更新する方法</span><span class="sxs-lookup"><span data-stu-id="09677-113">How to update LOB apps</span></span>

<span data-ttu-id="09677-114">LOB アプリは、Intune に追加されたのと同じ方法で更新できます。</span><span class="sxs-lookup"><span data-stu-id="09677-114">LOB apps can be updated in the same way they were added to Intune.</span></span> <span data-ttu-id="09677-115">Intune でアプリを更新するには、バージョン番号が大きい新しいアプリを既存のアプリ構成にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="09677-115">Apps can be updated in Intune by uploading the new app with a higher version number to the existing App configuration.</span></span> <span data-ttu-id="09677-116">デバイスが Intune に同期すると、新しいアプリ バージョンが作成され、新しいアプリがダウンロードされ、古いアプリが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="09677-116">When the device syncs to Intune, it will observe that there is a newer app version and the newer app will be downloaded and replace the old app.</span></span>

1. <span data-ttu-id="09677-117">新しいアプリをアップロードするには[、MEM ポータル](https://endpoint.microsoft.com/#home)アプリ  ->  \*\*\*\*->すべてのアプリ\*\*\*\*  ->  *TheNameOfYourApp プロパティに移動*  ->  **します。**</span><span class="sxs-lookup"><span data-stu-id="09677-117">To upload the newer app, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** -> *TheNameOfYourApp* -> **Properties.**</span></span>
2. <span data-ttu-id="09677-118">[アプリ情報] の横にある [編集] を **選択します。**</span><span class="sxs-lookup"><span data-stu-id="09677-118">Next to App information, select **Edit.**</span></span>
3. <span data-ttu-id="09677-119">更新するファイルの &quot; 選択の値については &quot; 、ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="09677-119">For the value of &quot;Select file to update&quot;, select your file.</span></span>
4. <span data-ttu-id="09677-120">ここから、コンテキスト メニューを使用してファイル エクスプローラーを開き、新しいバージョンの LOB アプリをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="09677-120">From here, use the context menu to open your file explorer and upload the newer version of the LOB app.</span></span> <span data-ttu-id="09677-121">必要に応じて依存関係を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="09677-121">Ensure to include dependencies as needed.</span></span>

<span data-ttu-id="09677-122">詳細: [HoloLens 用 Intune アプリの展開](https://docs.microsoft.com/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="09677-122">See more: [Intune App Deployment for HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)</span></span>

## <a name="development-plan"></a><span data-ttu-id="09677-123">開発計画</span><span class="sxs-lookup"><span data-stu-id="09677-123">Development Plan</span></span>

<span data-ttu-id="09677-124">デバイスが正常に登録されると、デバイスに追加の LOB アプリを展開する準備が完了しました。</span><span class="sxs-lookup"><span data-stu-id="09677-124">With your device successfully enrolled, you are now prepared to deploy more LOB apps to your devices.</span></span> <span data-ttu-id="09677-125">このガイドの期間中は、サンプル アプリを使用していますが、組織のニーズに合って構築されたカスタム アプリを使用する可能性が高い可能性があります。</span><span class="sxs-lookup"><span data-stu-id="09677-125">For the duration of this Guide, we're using a sample app, but it's more likely that you will want to use custom apps built for your organization's needs.</span></span>

<span data-ttu-id="09677-126">LOB アプリが既に存在する場合は、MDM を使用して [アプリを展開する準備が整いました](https://docs.microsoft.com/hololens/app-deploy-intune)。</span><span class="sxs-lookup"><span data-stu-id="09677-126">If you already have a LOB app, then you're ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="09677-127">別の方法を使用する場合は [、HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) のアプリケーション展開の概要を確認して、LOB アプリをデバイスに展開する方法の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="09677-127">If you'd prefer a different method, then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="09677-128">独自の LOB アプリをまだ作成していない場合や、まだ作成中の場合は、複合現実開発ドキュメントを確認して、[](https://docs.microsoft.com/windows/mixed-reality/design/design)設計とプロトタイプ作成を開始するか、複合現実開発を開始[](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)するコア概念を学ぶ必要があります。</span><span class="sxs-lookup"><span data-stu-id="09677-128">If you've yet to create your own LOB app or are still in the process of creation, then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="support-plan"></a><span data-ttu-id="09677-129">サポート プラン</span><span class="sxs-lookup"><span data-stu-id="09677-129">Support Plan</span></span>

<span data-ttu-id="09677-130">サポート プランは、優れた機能です。</span><span class="sxs-lookup"><span data-stu-id="09677-130">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="09677-131">HoloLens デバイスでの登録プロセスのトラブルシューティングと、組織内での HoloLens デバイスの一般的な使用に関するトレーニングを受けたユーザー(またはグループ)が役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="09677-131">Having someone, or a group, trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="09677-132">ユーザーが問題をより迅速に解決するために、エスカレーション プロセスは次の順序と同様の方法で処理されます。</span><span class="sxs-lookup"><span data-stu-id="09677-132">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="09677-133">サポート デスク。</span><span class="sxs-lookup"><span data-stu-id="09677-133">Your Support desk.</span></span>
2. <span data-ttu-id="09677-134">HoloLens エキスパート チーム</span><span class="sxs-lookup"><span data-stu-id="09677-134">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="09677-135">[HoloLens Docs](https://docs.microsoft.com/hololens/)  / [HoloLens トラブルシューティング ドキュメント](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="09677-135">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="09677-136">サポートに問い合わせ</span><span class="sxs-lookup"><span data-stu-id="09677-136">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a><span data-ttu-id="09677-137">デバイス管理</span><span class="sxs-lookup"><span data-stu-id="09677-137">Device Management</span></span>

<span data-ttu-id="09677-138">このガイドでは、モバイル デバイス管理 (MDM) のセットアップについて説明し、それを使用して、一部のデバイス構成をセットアップし、Wi-Fi 証明書とプロキシの観点からアクセスを許可する設定を適用しました。</span><span class="sxs-lookup"><span data-stu-id="09677-138">This guide talked about setting up Mobile Device Management (MDM) and used it to set up some device configurations and apply settings to allow access in terms of Wi-Fi certificates and proxy.</span></span> <span data-ttu-id="09677-139">ただし、MDM を使用して、CSP とポリシーを使用してデバイスの制限を適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="09677-139">However, MDM can also be used to apply device restrictions via CSPs and Policies.</span></span>

<span data-ttu-id="09677-140">多くの場合、デバイスには、Bluetooth、VPN、USB などの接続制限が設定されている場合や、カメラやマイクへのアクセスをオフにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="09677-140">In many cases, devices can have connectivity restrictions, such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="09677-141">これらの興味がある場合は、一般的なデバイス制限ページ [をお読みください](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)。</span><span class="sxs-lookup"><span data-stu-id="09677-141">If any of these interests you, then we encourage you to read our [common device restrictions page](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).</span></span>

<span data-ttu-id="09677-142">他にも、使用できるより複雑なデバイス制限があります。</span><span class="sxs-lookup"><span data-stu-id="09677-142">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="09677-143">次のようにします。</span><span class="sxs-lookup"><span data-stu-id="09677-143">Such as:</span></span>

- <span data-ttu-id="09677-144">[SettingsPageVisibility](https://docs.microsoft.com/hololens/settings-uri-list)を使用して設定アプリで表示できるページを制限し、ユーザーが調整する必要がある設定 (Wi-Fi 接続の変更など) にのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="09677-144">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](https://docs.microsoft.com/hololens/settings-uri-list), allowing users to only access the settings they need to adjust, such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="09677-145">キオスク [モードを使用](https://docs.microsoft.com/hololens/hololens-kiosk) して、デバイス上のユーザーに表示される UI を制限します。</span><span class="sxs-lookup"><span data-stu-id="09677-145">Use [Kiosk mode](https://docs.microsoft.com/hololens/hololens-kiosk) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="09677-146">キオスクを設定して、1 つのアプリを表示するか、カスタムスタート ページを使用して複数のアプリを表示できます。</span><span class="sxs-lookup"><span data-stu-id="09677-146">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="09677-147">キオスクでは、さまざまなユーザーに異なるエクスペリエンスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="09677-147">Kiosks can also present different experiences to different users.</span></span>
- <span data-ttu-id="09677-148">[Windows アプリケーションコントロール (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) を使用して、特定のアプリやプロセスを完全に起動し続ける。</span><span class="sxs-lookup"><span data-stu-id="09677-148">[Windows Application Control (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="09677-149">デバイス管理またはデバイス制限の追加の方法について説明する場合は、次の手順に進み、「デバイス管理の概要」 [を参照してください](https://docs.microsoft.com/hololens/hololens-csp-policy-overview)。</span><span class="sxs-lookup"><span data-stu-id="09677-149">If you'd like to learn about additional methods of device management or device restrictions, then take the next step and read our [Device Management Overview](https://docs.microsoft.com/hololens/hololens-csp-policy-overview).</span></span>





