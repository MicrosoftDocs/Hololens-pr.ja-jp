---
title: 展開ガイド - リモート アシストによるクラウド接続 HoloLens 2 の大規模な展開 - 保守
description: クラウド接続ネットワーク上で HoloLens デバイスを維持するためのヒント
keywords: HoloLens, 管理, クラウド接続, リモート アシスト, AAD, Azure AD, MDM, モバイル デバイス管理
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8117c73516d2775ec67f37bad524bcf377ece2e5
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252698"
---
# <span data-ttu-id="0fe5a-104">保守 - クラウド接続ガイド</span><span class="sxs-lookup"><span data-stu-id="0fe5a-104">Maintain - Cloud connected Guide</span></span>

## <span data-ttu-id="0fe5a-105">更新プログラム</span><span class="sxs-lookup"><span data-stu-id="0fe5a-105">Updates</span></span>

<span data-ttu-id="0fe5a-106">Windows Update for Business は、IT 管理者に対して Windows Update を中心とした追加の管理機能を提供するように設計されています。これには、更新プログラムをデバイスのグループに展開する機能や、更新プログラムをインストールするためのメンテナンス ウィンドウを定義する機能などが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="0fe5a-107">[HoloLens](https://docs.microsoft.com/hololens/hololens-updates)の更新プログラム (スケジュールされた日、スケジュールされた時刻、デバイスのアクティブ時間の設定など) を管理して、勤務時間外に更新する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-107">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="0fe5a-108">リモート アシストは、In-Boxアプリであり、Microsoft Store アプリを通じて更新できます。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="0fe5a-109">Microsoft Store を通じてダウンロードされるアプリについては [、Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) アプリ自体を使って手動で更新できます。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <span data-ttu-id="0fe5a-110">サポート プラン</span><span class="sxs-lookup"><span data-stu-id="0fe5a-110">Support Plan</span></span>

<span data-ttu-id="0fe5a-111">サポート プランは、この計画に取り入れるのに便利です。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="0fe5a-112">HoloLens デバイスでの登録プロセスのトラブルシューティングや、組織内での HoloLens デバイスの一般的な使用に関するトレーニングを受けたユーザーやグループが役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="0fe5a-113">ユーザーが問題をより迅速に解決するために、エスカレーション プロセスは次の順序と同様の方法で処理されます。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="0fe5a-114">サポート デスク。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-114">Your Support desk.</span></span>
2. <span data-ttu-id="0fe5a-115">HoloLens エキスパート チーム</span><span class="sxs-lookup"><span data-stu-id="0fe5a-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="0fe5a-116">[HoloLens ドキュメント](https://docs.microsoft.com/hololens/)  / [HoloLens のトラブルシューティングに関するドキュメント](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="0fe5a-116">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="0fe5a-117">サポートに問い合わせ</span><span class="sxs-lookup"><span data-stu-id="0fe5a-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <span data-ttu-id="0fe5a-118">開発計画</span><span class="sxs-lookup"><span data-stu-id="0fe5a-118">Development Plan</span></span>

<span data-ttu-id="0fe5a-119">デバイスが正常に登録されると、Line of Business アプリ (LOB アプリ) をデバイスに展開する準備が完了しました。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="0fe5a-120">これらは、組織のニーズに合&#39;アプリです。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="0fe5a-121">既に業務アプリがある場合は、MDM&#39;展開 [する準備が整っている必要があります](https://docs.microsoft.com/hololens/app-deploy-intune)。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="0fe5a-122">別の&#39;方法が必要な場合は [、HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) のアプリケーション展開の概要を確認して、LOB アプリをデバイスに展開する方法の詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-122">If you&#39;d prefer a different method then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="0fe5a-123">まだ独自&#39;LOB アプリを作成していない場合や、まだ作成中の場合は、Mixed Reality 開発ドキュメントを参照して、[](https://docs.microsoft.com/windows/mixed-reality/design/design)設計とプロトタイプの作成を開始したり[、Mixed Reality](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)開発を開始する中心概念を学習したりします。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <span data-ttu-id="0fe5a-124">デバイス管理</span><span class="sxs-lookup"><span data-stu-id="0fe5a-124">Device Management</span></span> 

<span data-ttu-id="0fe5a-125">このガイドでは、モバイル デバイス管理 (MDM) のセットアップについて説明しましたが、デバイスの制限を適用したり、デバイスにポリシーを適用したりするために使用されません。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="0fe5a-126">デバイス管理は、証明書をプッシュしてアクセスを許可したり、さまざまなデバイス制限でアクセスを制限したりするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="0fe5a-127">多くの場合、デバイスは Bluetooth、VPN、USB などの接続制限を持つ場合や、カメラやマイクへのアクセスをオフにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="0fe5a-128">これらの関心がある場合は、一般的なデバイス制限の [ページをお読み](hololens-common-device-restrictions.md)ください。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="0fe5a-129">使用できるその他のより複雑なデバイス制限があります。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="0fe5a-130">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-130">Such as:</span></span>

- <span data-ttu-id="0fe5a-131">[SettingsPageVisibility](settings-uri-list.md)を使用して設定アプリで表示できるページを制限し、ユーザーが調整する必要がある設定 (ユーザーの接続の変更など) にのみアクセスWi-Fiします。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="0fe5a-132">キオスク [モードを使](hololens-kiosk.md) って、デバイス上のユーザーに表示される UI を制限します。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="0fe5a-133">キオスクは、1 つのアプリを表示するか、カスタムのスタート ページを持つ複数のアプリを表示するために設定できます。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="0fe5a-134">キオスクでは、さまざまなユーザーに異なるエクスペリエンスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="0fe5a-135">[Windows アプリケーション制御 (WDAC)](windows-defender-application-control-wdac.md) を使って、特定のアプリやプロセスが完全に起動しなきを維持します。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="0fe5a-136">デバイス管理やデバイスの制限に関するさまざまな方法について詳しくは、次の手順に進み、「デバイス管理の概要」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0fe5a-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <span data-ttu-id="0fe5a-137">次のステップ</span><span class="sxs-lookup"><span data-stu-id="0fe5a-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="0fe5a-138">CSP とデバイス管理の概要を読む</span><span class="sxs-lookup"><span data-stu-id="0fe5a-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)