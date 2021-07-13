---
title: デプロイ ガイド – クラウドに接続されたHoloLens 2大規模なデプロイ - Remote Assist - メンテナンス
description: クラウドに接続されたネットワークを使用してデバイスを管理およびサポートHoloLens関するヒントを常に確認してください。
keywords: HoloLens、管理、クラウド接続、Remote Assist、AAD、Azure AD、MDM、Mobile デバイス管理
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
ms.openlocfilehash: 941de296d59713c098718b16431fa793bd1b60e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635162"
---
# <a name="maintain---cloud-connected-guide"></a><span data-ttu-id="3602d-104">メンテナンス - クラウド接続ガイド</span><span class="sxs-lookup"><span data-stu-id="3602d-104">Maintain - Cloud connected Guide</span></span>

## <a name="updates"></a><span data-ttu-id="3602d-105">更新プログラム</span><span class="sxs-lookup"><span data-stu-id="3602d-105">Updates</span></span>

<span data-ttu-id="3602d-106">Windows Update for Business は、IT 管理者に対して Windows Update を中心とした追加の管理機能を提供するように設計されています。これには、更新プログラムをデバイスのグループに展開する機能や、更新プログラムをインストールするためのメンテナンス ウィンドウを定義する機能などが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3602d-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="3602d-107">スケジュールされた日、[スケジュールHoloLens、](/hololens/hololens-updates)デバイスのアクティブな時間の設定など、スケジュールされた更新プログラムを管理して、作業時間外に更新する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="3602d-107">Learn how to [manage HoloLens updates](/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="3602d-108">Remote AssistはIn-Boxであり、アプリを使用して更新Microsoft Storeできます。</span><span class="sxs-lookup"><span data-stu-id="3602d-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="3602d-109">アプリを介してダウンロードMicrosoft Storeアプリ自体を使用して更新Microsoft Store更新できます[](/hololens/holographic-store-apps#update-apps)。</span><span class="sxs-lookup"><span data-stu-id="3602d-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="support-plan"></a><span data-ttu-id="3602d-110">サポート計画</span><span class="sxs-lookup"><span data-stu-id="3602d-110">Support Plan</span></span>

<span data-ttu-id="3602d-111">サポート プランは、優れた機能です。</span><span class="sxs-lookup"><span data-stu-id="3602d-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="3602d-112">HoloLens デバイスでの登録プロセスのトラブルシューティングと、組織内の HoloLens デバイスの一般的な使用に関するトレーニングを受けたユーザーやグループが役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="3602d-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="3602d-113">ユーザーが問題をより迅速に解決するには、エスカレーション プロセスを次の順序と同様の方法で処理してください。</span><span class="sxs-lookup"><span data-stu-id="3602d-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="3602d-114">サポート デスク。</span><span class="sxs-lookup"><span data-stu-id="3602d-114">Your Support desk.</span></span>
2. <span data-ttu-id="3602d-115">HoloLensエキスパート チーム</span><span class="sxs-lookup"><span data-stu-id="3602d-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="3602d-116">[HoloLens Docs](/hololens/)  / [HoloLensトラブルシューティング ドキュメント](/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="3602d-116">[HoloLens Docs](/hololens/) / [HoloLens Troubleshooting Docs](/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="3602d-117">サポートに問い合わせ</span><span class="sxs-lookup"><span data-stu-id="3602d-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a><span data-ttu-id="3602d-118">開発計画</span><span class="sxs-lookup"><span data-stu-id="3602d-118">Development Plan</span></span>

<span data-ttu-id="3602d-119">デバイスが正常に登録されると、Line of Business アプリ (LOB アプリ) をデバイスに展開する準備が完了しました。</span><span class="sxs-lookup"><span data-stu-id="3602d-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="3602d-120">これらは、組織のニーズに合&#39;アプリです。</span><span class="sxs-lookup"><span data-stu-id="3602d-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="3602d-121">既に一行のビジネス アプリがある場合は&#39;MDM を使用してアプリを [デプロイする準備が整います](/hololens/app-deploy-intune)。</span><span class="sxs-lookup"><span data-stu-id="3602d-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](/hololens/app-deploy-intune).</span></span> <span data-ttu-id="3602d-122">別の方法&#39;場合は[、HoloLens 2](/hololens/app-deploy-overview)のアプリケーション展開の概要に関するページを参照して、ご利用のデバイスに LOB アプリを展開する方法の詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="3602d-122">If you&#39;d prefer a different method, then review the [application deployment overview for HoloLens 2](/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="3602d-123">独自&#39;LOB アプリをまだ作成していない場合、または作成中の場合は、Mixed Reality 開発ドキュメントを参照して、設計[](/windows/mixed-reality/design/design)とプロトタイプ作成を開始するか、Mixed [Reality](/windows/mixed-reality/discover/get-started-with-mr)開発を開始する主要な概念を学習してください。</span><span class="sxs-lookup"><span data-stu-id="3602d-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="device-management"></a><span data-ttu-id="3602d-124">デバイス管理</span><span class="sxs-lookup"><span data-stu-id="3602d-124">Device Management</span></span> 

<span data-ttu-id="3602d-125">このガイドでは Mobile デバイス管理 (MDM) の設定について説明しましたが、デバイスの制限を適用したり、デバイスにポリシーを適用したりするために使用されません。</span><span class="sxs-lookup"><span data-stu-id="3602d-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="3602d-126">デバイス管理は、証明書をプッシュしてアクセスを許可したり、さまざまなデバイス制限でアクセスを制限したりするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="3602d-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="3602d-127">多くの場合、デバイスには、Bluetooth、VPN、USB などの接続制限がある場合や、カメラまたはマイクへのアクセスをオフにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3602d-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="3602d-128">これらの関心がある場合は、一般的なデバイスの制限に関する [ページをお読みください](hololens-common-device-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="3602d-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="3602d-129">使用できるその他の複雑なデバイス制限があります。</span><span class="sxs-lookup"><span data-stu-id="3602d-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="3602d-130">例:</span><span class="sxs-lookup"><span data-stu-id="3602d-130">Such as:</span></span>

- <span data-ttu-id="3602d-131">[SettingsPageVisibility](settings-uri-list.md)を使用して 設定 アプリで表示できるページを制限すると、ユーザーは、Wi-Fi 接続の変更など、調整する必要がある設定にのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3602d-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="3602d-132">キオスク [モードを使用](hololens-kiosk.md) して、デバイス上のユーザーに表示される UI を制限します。</span><span class="sxs-lookup"><span data-stu-id="3602d-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="3602d-133">キオスクを設定して、1 つのアプリを表示するか、カスタム スタート ページを使用して複数のアプリを表示できます。</span><span class="sxs-lookup"><span data-stu-id="3602d-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="3602d-134">キオスクでは、異なるユーザーに異なるエクスペリエンスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="3602d-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="3602d-135">[Windowsアプリケーション制御 (WDAC)](windows-defender-application-control-wdac.md)を使用して、特定のアプリやプロセスが完全に起動しなきを維持します。</span><span class="sxs-lookup"><span data-stu-id="3602d-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="3602d-136">デバイス管理またはデバイスの制限のより異なる方法について学習する場合は、次の手順に進み、「概要」をデバイス管理してください。</span><span class="sxs-lookup"><span data-stu-id="3602d-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <a name="next-step"></a><span data-ttu-id="3602d-137">次のステップ</span><span class="sxs-lookup"><span data-stu-id="3602d-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3602d-138">CSP とアプリケーションの概要をデバイス管理する</span><span class="sxs-lookup"><span data-stu-id="3602d-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)