---
title: 展開ガイド–クラウドに接続された HoloLens 2 展開でのリモートアシストの維持
description: クラウドに接続されたネットワーク経由で HoloLens デバイスを管理するためのヒント
keywords: HoloLens、管理、クラウド接続、リモートアシスト、AAD、Azure AD、MDM、モバイルデバイス管理
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
ms.openlocfilehash: beee64159415c0635812463f81c0b5565e44e4a8
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196336"
---
# <span data-ttu-id="cb20f-104">保守-クラウド接続ガイド</span><span class="sxs-lookup"><span data-stu-id="cb20f-104">Maintain - Cloud connected Guide</span></span>

## <span data-ttu-id="cb20f-105">更新プログラム</span><span class="sxs-lookup"><span data-stu-id="cb20f-105">Updates</span></span>

<span data-ttu-id="cb20f-106">Windows Update for Business は、IT 管理者に対して Windows Update を中心とした追加の管理機能を提供するように設計されています。これには、更新プログラムをデバイスのグループに展開する機能や、更新プログラムをインストールするためのメンテナンス ウィンドウを定義する機能などが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cb20f-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="cb20f-107">スケジュールされた日数、スケジュールされた時間、およびデバイスのアクティブ時間の設定などの [HoloLens の更新を管理](https://docs.microsoft.com/hololens/hololens-updates) する方法について説明します。これにより、稼働時間外に更新されます。</span><span class="sxs-lookup"><span data-stu-id="cb20f-107">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="cb20f-108">リモートアシスタンスは In-Box アプリであり、Microsoft ストアアプリを通じて更新できます。</span><span class="sxs-lookup"><span data-stu-id="cb20f-108">Remote Assist is a In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="cb20f-109">Microsoft Store からダウンロードされたすべてのアプリは、Microsoft ストアアプリ自体を [通じて](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) 手動で更新することができます。</span><span class="sxs-lookup"><span data-stu-id="cb20f-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <span data-ttu-id="cb20f-110">サポート プラン</span><span class="sxs-lookup"><span data-stu-id="cb20f-110">Support Plan</span></span>

<span data-ttu-id="cb20f-111">サポート計画は、適切な場所に配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cb20f-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="cb20f-112">HoloLens デバイスでの登録プロセスのトラブルシューティングや、組織内での HoloLens デバイスの一般的な使用については、他のユーザーやグループがトレーニングアップしていることもあります。</span><span class="sxs-lookup"><span data-stu-id="cb20f-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="cb20f-113">ユーザーが問題をより迅速に解決できるようにするために、エスカレーションプロセスは次のような方法で処理されることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cb20f-113">In order to allow your users to have the faster resolution of their issues we suggest that your escalation process is handled in a similar manner to this:</span></span>

1. <span data-ttu-id="cb20f-114">サポートデスク。</span><span class="sxs-lookup"><span data-stu-id="cb20f-114">Your Support desk.</span></span>
2. <span data-ttu-id="cb20f-115">HoloLens の専門家チーム</span><span class="sxs-lookup"><span data-stu-id="cb20f-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="cb20f-116">[HoloLens ドキュメント](https://docs.microsoft.com/hololens/)  / [HoloLens トラブルシューティングドキュメント](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="cb20f-116">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="cb20f-117">サポートに問い合わせ</span><span class="sxs-lookup"><span data-stu-id="cb20f-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <span data-ttu-id="cb20f-118">開発計画</span><span class="sxs-lookup"><span data-stu-id="cb20f-118">Development Plan</span></span>

<span data-ttu-id="cb20f-119">デバイスが正常に登録されたら、基幹業務アプリ (LOB アプリ) をデバイスに展開する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="cb20f-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="cb20f-120">これらは、組織&#39;s ニーズに合わせて構築されたカスタムアプリです。</span><span class="sxs-lookup"><span data-stu-id="cb20f-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="cb20f-121">基幹業務アプリを既にお持ちの場合は、 [MDM でアプリを展開](https://docs.microsoft.com/hololens/app-deploy-intune)する準備ができたら&#39;ます。</span><span class="sxs-lookup"><span data-stu-id="cb20f-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="cb20f-122">&#39;d で別の方法を使用したい場合は、 [HoloLens 2 のアプリケーション展開の概要](https://docs.microsoft.com/hololens/app-deploy-overview) を確認して、LOB アプリをデバイスに展開するためのその他の方法について確認してください。</span><span class="sxs-lookup"><span data-stu-id="cb20f-122">If you&#39;d prefer a different method then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="cb20f-123">独自の LOB アプリを作成しているか、まだ作成プロセスの途中で&#39;ある場合は、mixed reality 開発ドキュメントを参照して[設計とプロトタイプ](https://docs.microsoft.com/windows/mixed-reality/design/design)の作成を開始するか、または[mixed reality の開発](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)を開始するための基本的な概念について学習します。</span><span class="sxs-lookup"><span data-stu-id="cb20f-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <span data-ttu-id="cb20f-124">デバイス管理</span><span class="sxs-lookup"><span data-stu-id="cb20f-124">Device Management</span></span> 

<span data-ttu-id="cb20f-125">このガイドでは、モバイルデバイス管理 (MDM) を設定する方法について説明していますが、デバイスの制限やポリシーを適用するためには採用していませんでした。</span><span class="sxs-lookup"><span data-stu-id="cb20f-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="cb20f-126">デバイス管理は、証明書をプッシュするか、さまざまなデバイスの制限を使用してアクセスを制限することで、アクセスを許可するために使うことができます。</span><span class="sxs-lookup"><span data-stu-id="cb20f-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="cb20f-127">多くの場合、デバイスは、Bluetooth、VPN、USB などの接続制限を行うことができます。また、カメラやマイクへのアクセスをオフにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cb20f-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="cb20f-128">上記のいずれかが該当する場合は、 [デバイスの一般的な制限のページ](hololens-common-device-restrictions.md)を参照することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cb20f-128">If any of these interest you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="cb20f-129">使用できるその他の複雑なデバイス制限があります。</span><span class="sxs-lookup"><span data-stu-id="cb20f-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="cb20f-130">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="cb20f-130">Such as:</span></span>

- <span data-ttu-id="cb20f-131">[Settingspagevisibility](settings-uri-list.md)を使用して、設定アプリで表示できるページを制限します。ユーザーは、Wi-Fi 接続の変更など、調整する必要がある設定にのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cb20f-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="cb20f-132">[キオスクモード](hololens-kiosk.md)を使って、デバイスのユーザーに表示される UI を制限します。</span><span class="sxs-lookup"><span data-stu-id="cb20f-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="cb20f-133">キオスクを設定すると、1つのアプリを表示したり、カスタムスタートページを持つ複数のアプリを表示したりできます。</span><span class="sxs-lookup"><span data-stu-id="cb20f-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="cb20f-134">キオスクでは、ユーザーごとに異なるエクスペリエンスを提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="cb20f-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="cb20f-135">特定のアプリまたはプロセスをまったく起動しないようにするための[Windows アプリケーション制御 (WDAC)](windows-defender-application-control-wdac.md) 。</span><span class="sxs-lookup"><span data-stu-id="cb20f-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="cb20f-136">デバイス管理またはデバイス制限のその他の方法については、次の手順に進み、「デバイス管理の概要」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cb20f-136">If you'd like to learn about more different methods of device management or device restrictions then take the next step and read our Device Management Overview.</span></span>

## <span data-ttu-id="cb20f-137">次のステップ</span><span class="sxs-lookup"><span data-stu-id="cb20f-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="cb20f-138">「Csp とデバイス管理の概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb20f-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)