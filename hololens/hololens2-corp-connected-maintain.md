---
title: 展開ガイド– Dynamics 365 を使用した企業接続 HoloLens 2 ガイド-メンテナンス
description: Dynamics 365 ガイドを使用して、企業に接続されたネットワーク経由で HoloLens 2 デバイスを保守する方法について説明します。
keywords: HoloLens, 管理, 企業接続, Dynamics 365 ガイド, AAD, Azure AD, MDM, モバイルデバイス管理
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309500"
---
# <a name="maintain---corporate-connected-guide"></a><span data-ttu-id="c5b09-104">保守-企業の接続ガイド</span><span class="sxs-lookup"><span data-stu-id="c5b09-104">Maintain - Corporate Connected Guide</span></span>

## <a name="update-hololens"></a><span data-ttu-id="c5b09-105">HoloLens を更新する</span><span class="sxs-lookup"><span data-stu-id="c5b09-105">Update HoloLens</span></span>

<span data-ttu-id="c5b09-106">Windows Update for Business は、IT 管理者に対して Windows Update を中心とした追加の管理機能を提供するように設計されています。これには、更新プログラムをデバイスのグループに展開する機能や、更新プログラムをインストールするためのメンテナンス ウィンドウを定義する機能などが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c5b09-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="c5b09-107">更新プログラムを管理する一般的な方法の1つは、機能の遅延を30日間にすることです。</span><span class="sxs-lookup"><span data-stu-id="c5b09-107">One popular method of managing updates is to do a feature deferral of 30 days.</span></span> <span data-ttu-id="c5b09-108">これにより、管理者は新しい機能を更新してプレビューし、最初の知識を取得し、新しい変更をサポートデスクに通知することができます。</span><span class="sxs-lookup"><span data-stu-id="c5b09-108">This allows Admins to update and preview new features, gaining first hand knowledge and informing your support desk of any new changes.</span></span>

<span data-ttu-id="c5b09-109">スケジュールされた日、スケジュールされた時刻、デバイスのアクティブ時間の設定など、 [HoloLens の更新を管理](https://docs.microsoft.com/hololens/hololens-updates)する方法について説明します。これにより、勤務時間外に更新されるようになります。</span><span class="sxs-lookup"><span data-stu-id="c5b09-109">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates), including scheduled days, scheduled time, and setting active hours on the device, so it will update outside of working hours.</span></span>

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a><span data-ttu-id="c5b09-110">Dynamics 365 ガイド (およびその他のストアアプリ) を更新する方法</span><span class="sxs-lookup"><span data-stu-id="c5b09-110">How to update Dynamics 365 Guides (and other store apps)</span></span>

<span data-ttu-id="c5b09-111">Dynamics 365 ガイドは In-Box アプリであり、Microsoft Store アプリを使用して更新できます。</span><span class="sxs-lookup"><span data-stu-id="c5b09-111">Dynamics 365 Guides is an In-Box app, and can be updated through the Microsoft Store app.</span></span> <span data-ttu-id="c5b09-112">Microsoft Store によってダウンロードされたすべてのアプリについて、Microsoft Store アプリ自体を [使用して](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) 手動で更新することができます。</span><span class="sxs-lookup"><span data-stu-id="c5b09-112">For all apps that are downloaded through the Microsoft Store, they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="how-to-update-lob-apps"></a><span data-ttu-id="c5b09-113">LOB アプリを更新する方法</span><span class="sxs-lookup"><span data-stu-id="c5b09-113">How to update LOB apps</span></span>

<span data-ttu-id="c5b09-114">LOB アプリは、Intune に追加したときと同じ方法で更新できます。</span><span class="sxs-lookup"><span data-stu-id="c5b09-114">LOB apps can be updated in the same way they were added to Intune.</span></span> <span data-ttu-id="c5b09-115">Intune でアプリを更新するには、新しいバージョン番号を持つ新しいアプリを既存のアプリ構成にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="c5b09-115">Apps can be updated in Intune by uploading the new app with a higher version number to the existing App configuration.</span></span> <span data-ttu-id="c5b09-116">デバイスが Intune に同期すると、新しいバージョンのアプリがあることが確認され、新しいアプリがダウンロードされて、古いアプリが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="c5b09-116">When the device syncs to Intune, it will observe that there is a newer app version and the newer app will be downloaded and replace the old app.</span></span>

1. <span data-ttu-id="c5b09-117">新しいアプリをアップロードするには、[[メモリポータル](https://endpoint.microsoft.com/#home)  ->  **アプリ**>-すべての **アプリ** の TheNameOfYourApp] プロパティに移動し  ->    ->  **ます。**</span><span class="sxs-lookup"><span data-stu-id="c5b09-117">To upload the newer app, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** -> *TheNameOfYourApp* -> **Properties.**</span></span>
2. <span data-ttu-id="c5b09-118">[アプリ情報] の横にある [編集] を選択し **ます。**</span><span class="sxs-lookup"><span data-stu-id="c5b09-118">Next to App information, select **Edit.**</span></span>
3. <span data-ttu-id="c5b09-119">&quot;[更新するファイルを選択してください] の値とし &quot; て、ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="c5b09-119">For the value of &quot;Select file to update&quot;, select your file.</span></span>
4. <span data-ttu-id="c5b09-120">ここから、コンテキストメニューを使用してファイルエクスプローラーを開き、新しいバージョンの LOB アプリをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="c5b09-120">From here, use the context menu to open your file explorer and upload the newer version of the LOB app.</span></span> <span data-ttu-id="c5b09-121">必要に応じて依存関係を含めてください。</span><span class="sxs-lookup"><span data-stu-id="c5b09-121">Ensure to include dependencies as needed.</span></span>

<span data-ttu-id="c5b09-122">詳細については[、「HoloLens の Intune アプリの展開」を](https://docs.microsoft.com/hololens/app-deploy-intune)参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5b09-122">See more: [Intune App Deployment for HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)</span></span>

## <a name="development-plan"></a><span data-ttu-id="c5b09-123">開発計画</span><span class="sxs-lookup"><span data-stu-id="c5b09-123">Development Plan</span></span>

<span data-ttu-id="c5b09-124">デバイスが正常に登録されたら、より多くの LOB アプリをデバイスにデプロイする準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="c5b09-124">With your device successfully enrolled, you are now prepared to deploy more LOB apps to your devices.</span></span> <span data-ttu-id="c5b09-125">このガイドの期間中はサンプルアプリを使用していますが、組織のニーズに合わせて構築されたカスタムアプリを使用することが必要になる可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="c5b09-125">For the duration of this Guide, we're using a sample app, but it's more likely that you will want to use custom apps built for your organization's needs.</span></span>

<span data-ttu-id="c5b09-126">LOB アプリを既にお持ちの場合は、MDM を [使用](https://docs.microsoft.com/hololens/app-deploy-intune)してアプリをデプロイする準備ができています。</span><span class="sxs-lookup"><span data-stu-id="c5b09-126">If you already have a LOB app, then you're ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="c5b09-127">別の方法を使用する場合は、 [「HoloLens 2 のアプリケーション展開の概要」](https://docs.microsoft.com/hololens/app-deploy-overview) を参照して、LOB アプリをデバイスにデプロイする方法の詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="c5b09-127">If you'd prefer a different method, then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="c5b09-128">独自の LOB アプリをまだ作成していない場合、またはまだ作成プロセスが完了している場合は、mixed reality の開発に関するドキュメントを参照して、[設計とプロトタイプ](https://docs.microsoft.com/windows/mixed-reality/design/design)作成を開始するか、または[mixed reality 開発を開始](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)するための主要な概念を学習してください。</span><span class="sxs-lookup"><span data-stu-id="c5b09-128">If you've yet to create your own LOB app or are still in the process of creation, then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="support-plan"></a><span data-ttu-id="c5b09-129">サポート計画</span><span class="sxs-lookup"><span data-stu-id="c5b09-129">Support Plan</span></span>

<span data-ttu-id="c5b09-130">サポートプランは、適切な場所に配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c5b09-130">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="c5b09-131">HoloLens デバイスでの登録プロセスのトラブルシューティングに関するトレーニングを受けているユーザーやグループがあれば、組織内での HoloLens デバイスの一般的な使用が役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c5b09-131">Having someone, or a group, trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="c5b09-132">ユーザーがより迅速に問題を解決できるようにするために、エスカレーションプロセスは次の順序と同様の方法で処理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c5b09-132">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="c5b09-133">サポートデスク。</span><span class="sxs-lookup"><span data-stu-id="c5b09-133">Your Support desk.</span></span>
2. <span data-ttu-id="c5b09-134">HoloLens エキスパートチーム</span><span class="sxs-lookup"><span data-stu-id="c5b09-134">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="c5b09-135">[HoloLens ドキュメント](https://docs.microsoft.com/hololens/)  / [HoloLens のトラブルシューティングに関するドキュメント](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="c5b09-135">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="c5b09-136">サポートにお問い合わせください</span><span class="sxs-lookup"><span data-stu-id="c5b09-136">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a><span data-ttu-id="c5b09-137">デバイス管理</span><span class="sxs-lookup"><span data-stu-id="c5b09-137">Device Management</span></span>

<span data-ttu-id="c5b09-138">このガイドでは、モバイルデバイス管理 (MDM) を設定し、それを使用して一部のデバイス構成を設定し、Wi-Fi 証明書とプロキシの観点からアクセスを許可する設定を適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5b09-138">This guide talked about setting up Mobile Device Management (MDM) and used it to set up some device configurations and apply settings to allow access in terms of Wi-Fi certificates and proxy.</span></span> <span data-ttu-id="c5b09-139">ただし、MDM を使用して、Csp とポリシーを使用してデバイスの制限を適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c5b09-139">However, MDM can also be used to apply device restrictions via CSPs and Policies.</span></span>

<span data-ttu-id="c5b09-140">多くの場合、デバイスには、Bluetooth、VPN、USB などの接続制限や、カメラやマイクへのアクセスをオフにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c5b09-140">In many cases, devices can have connectivity restrictions, such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="c5b09-141">これらのいずれかが興味をお持ちの場合は、 [一般的なデバイスの制限に関するページ](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)をお読みになることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c5b09-141">If any of these interests you, then we encourage you to read our [common device restrictions page](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).</span></span>

<span data-ttu-id="c5b09-142">使用できるデバイスには、他にも複雑な制限があります。</span><span class="sxs-lookup"><span data-stu-id="c5b09-142">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="c5b09-143">例:</span><span class="sxs-lookup"><span data-stu-id="c5b09-143">Such as:</span></span>

- <span data-ttu-id="c5b09-144">[Settingspagevisibility](https://docs.microsoft.com/hololens/settings-uri-list)を使用して設定アプリで表示できるページ数を制限することで、ユーザーは Wi-Fi 接続の変更など、調整が必要な設定にのみアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="c5b09-144">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](https://docs.microsoft.com/hololens/settings-uri-list), allowing users to only access the settings they need to adjust, such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="c5b09-145">[キオスクモード](https://docs.microsoft.com/hololens/hololens-kiosk)を使用して、デバイス上のユーザーに表示される UI を制限します。</span><span class="sxs-lookup"><span data-stu-id="c5b09-145">Use [Kiosk mode](https://docs.microsoft.com/hololens/hololens-kiosk) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="c5b09-146">キオスクを設定して、1つのアプリ、またはカスタムスタートページを持つ複数のアプリを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="c5b09-146">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="c5b09-147">キオスクでは、ユーザーごとに異なるエクスペリエンスを提示することもできます。</span><span class="sxs-lookup"><span data-stu-id="c5b09-147">Kiosks can also present different experiences to different users.</span></span>
- <span data-ttu-id="c5b09-148">特定のアプリまたはプロセスを完全に起動しないようにするための[Windows アプリケーション制御 (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 。</span><span class="sxs-lookup"><span data-stu-id="c5b09-148">[Windows Application Control (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="c5b09-149">デバイス管理またはデバイスの制限のその他の方法について学習する場合は、次の手順を実行し、 [デバイス管理の概要](https://docs.microsoft.com/hololens/hololens-csp-policy-overview)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5b09-149">If you'd like to learn about additional methods of device management or device restrictions, then take the next step and read our [Device Management Overview](https://docs.microsoft.com/hololens/hololens-csp-policy-overview).</span></span>





