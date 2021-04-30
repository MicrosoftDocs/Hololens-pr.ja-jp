---
title: デプロイガイド–クラウドに接続された HoloLens 2 の大規模なデプロイとリモートサポート
description: クラウドに接続されたネットワーク経由での HoloLens デバイスの保守とサポートに関するヒントをご覧ください。
keywords: HoloLens、管理、クラウド接続、リモートアシスタンス、AAD、Azure AD、MDM、モバイルデバイス管理
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
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309784"
---
# <a name="maintain---cloud-connected-guide"></a><span data-ttu-id="8d709-104">保守-クラウド接続ガイド</span><span class="sxs-lookup"><span data-stu-id="8d709-104">Maintain - Cloud connected Guide</span></span>

## <a name="updates"></a><span data-ttu-id="8d709-105">更新プログラム</span><span class="sxs-lookup"><span data-stu-id="8d709-105">Updates</span></span>

<span data-ttu-id="8d709-106">Windows Update for Business は、IT 管理者に対して Windows Update を中心とした追加の管理機能を提供するように設計されています。これには、更新プログラムをデバイスのグループに展開する機能や、更新プログラムをインストールするためのメンテナンス ウィンドウを定義する機能などが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8d709-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="8d709-107">スケジュールされた日、スケジュールされた時刻、デバイスでのアクティブ時間の設定など、 [HoloLens の更新を管理](https://docs.microsoft.com/hololens/hololens-updates) して、勤務時間外に更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d709-107">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="8d709-108">リモートアシスタンスは In-Box アプリであり、Microsoft Store アプリを使用して更新できます。</span><span class="sxs-lookup"><span data-stu-id="8d709-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="8d709-109">Microsoft Store によってダウンロードされたすべてのアプリについて、Microsoft Store アプリ自体を [使用して](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) 手動で更新することができます。</span><span class="sxs-lookup"><span data-stu-id="8d709-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="support-plan"></a><span data-ttu-id="8d709-110">サポート計画</span><span class="sxs-lookup"><span data-stu-id="8d709-110">Support Plan</span></span>

<span data-ttu-id="8d709-111">サポートプランは、適切な場所に配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d709-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="8d709-112">HoloLens デバイスでの登録プロセスのトラブルシューティングに関する他のユーザーやグループを持っている場合、または組織内での HoloLens デバイスの一般的な使用が役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8d709-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="8d709-113">ユーザーがより迅速に問題を解決できるようにするために、エスカレーションプロセスは次の順序と同様の方法で処理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d709-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="8d709-114">サポートデスク。</span><span class="sxs-lookup"><span data-stu-id="8d709-114">Your Support desk.</span></span>
2. <span data-ttu-id="8d709-115">HoloLens エキスパートチーム</span><span class="sxs-lookup"><span data-stu-id="8d709-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="8d709-116">[HoloLens ドキュメント](https://docs.microsoft.com/hololens/)  / [HoloLens のトラブルシューティングに関するドキュメント](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="8d709-116">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="8d709-117">サポートにお問い合わせください</span><span class="sxs-lookup"><span data-stu-id="8d709-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a><span data-ttu-id="8d709-118">開発計画</span><span class="sxs-lookup"><span data-stu-id="8d709-118">Development Plan</span></span>

<span data-ttu-id="8d709-119">デバイスが正常に登録されると、基幹業務アプリ (LOB アプリ) をデバイスに展開する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="8d709-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="8d709-120">これらは、組織&#39;のニーズに合わせて構築されたカスタムアプリです。</span><span class="sxs-lookup"><span data-stu-id="8d709-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="8d709-121">基幹業務アプリを既にお持ちの場合は、 [MDM を使用してアプリをデプロイ](https://docs.microsoft.com/hololens/app-deploy-intune)する準備が&#39;ます。</span><span class="sxs-lookup"><span data-stu-id="8d709-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="8d709-122">&#39;d で別の方法を選択する場合は、 [「HoloLens 2 のアプリケーション展開の概要」](https://docs.microsoft.com/hololens/app-deploy-overview) を参照して、LOB アプリをデバイスにデプロイする方法の詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="8d709-122">If you&#39;d prefer a different method then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="8d709-123">独自の LOB アプリをまだ作成していない&#39;場合、またはまだ作成プロセスが完了している場合は、mixed reality の開発に関するドキュメントを参照して、[設計とプロトタイプ](https://docs.microsoft.com/windows/mixed-reality/design/design)作成を開始するか、 [mixed reality 開発](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)を開始するための主要な概念を学習してください。</span><span class="sxs-lookup"><span data-stu-id="8d709-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="device-management"></a><span data-ttu-id="8d709-124">デバイス管理</span><span class="sxs-lookup"><span data-stu-id="8d709-124">Device Management</span></span> 

<span data-ttu-id="8d709-125">このガイドではモバイルデバイス管理 (MDM) のセットアップについて説明しましたが、デバイスの制限を適用するために使用されていなかったか、デバイスにポリシーが適用されました。</span><span class="sxs-lookup"><span data-stu-id="8d709-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="8d709-126">デバイス管理を使用して、証明書をプッシュしてアクセスを許可するか、さまざまなデバイス制限を使用してアクセスを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="8d709-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="8d709-127">多くの場合、デバイスには、Bluetooth、VPN、USB などの接続制限や、カメラやマイクへのアクセスをオフにする機能があります。</span><span class="sxs-lookup"><span data-stu-id="8d709-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="8d709-128">これらのいずれかに興味がある場合は、 [一般的なデバイスの制限に関するページ](hololens-common-device-restrictions.md)をお読みになることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d709-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="8d709-129">使用できるデバイスには、他にも複雑な制限があります。</span><span class="sxs-lookup"><span data-stu-id="8d709-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="8d709-130">例:</span><span class="sxs-lookup"><span data-stu-id="8d709-130">Such as:</span></span>

- <span data-ttu-id="8d709-131">[Settingspagevisibility](settings-uri-list.md)を使用して設定アプリで表示できるページ数を制限することで、ユーザーは Wi-Fi 接続の変更など、調整が必要な設定にのみアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="8d709-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="8d709-132">[キオスクモード](hololens-kiosk.md)を使用して、デバイス上のユーザーに表示される UI を制限します。</span><span class="sxs-lookup"><span data-stu-id="8d709-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="8d709-133">キオスクを設定して、1つのアプリ、またはカスタムスタートページを持つ複数のアプリを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="8d709-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="8d709-134">キオスクでは、ユーザーごとに異なるエクスペリエンスを提示することもできます。</span><span class="sxs-lookup"><span data-stu-id="8d709-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="8d709-135">特定のアプリまたはプロセスを完全に起動しないようにするための[Windows アプリケーション制御 (WDAC)](windows-defender-application-control-wdac.md) 。</span><span class="sxs-lookup"><span data-stu-id="8d709-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="8d709-136">デバイス管理またはデバイスの制限の別の方法について学習する場合は、次の手順を実行し、デバイス管理の概要に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d709-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <a name="next-step"></a><span data-ttu-id="8d709-137">次のステップ</span><span class="sxs-lookup"><span data-stu-id="8d709-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8d709-138">Csp とデバイス管理の概要を読む</span><span class="sxs-lookup"><span data-stu-id="8d709-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)