---
title: アプリケーションの検索、インストール、およびアンインストール
description: Microsoft ストアは、HoloLens で動作するアプリやゲーム用のソースです。  Holographic アプリの検索、インストール、アンインストールの詳細については、こちらを参照してください。
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 10/27/2020
manager: jarrettr
keywords: Hololens、ストア、UWP、アプリ、インストール
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 44c79a41d7864cd6000ffed1bdd32dab8ffabc39
ms.sourcegitcommit: b437c738f101ac870a29bbdb7fd642eda3d67f00
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2021
ms.locfileid: "11406269"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a><span data-ttu-id="d45ca-105">Microsoft Store のアプリケーションの検索、インストール、アンインストール</span><span class="sxs-lookup"><span data-stu-id="d45ca-105">Find, install, and uninstall applications from the Microsoft Store</span></span>

<span data-ttu-id="d45ca-106">Microsoft ストアは、HoloLens で動作するアプリやゲーム用のソースです。</span><span class="sxs-lookup"><span data-stu-id="d45ca-106">The Microsoft Store is your go-to source for apps and games that work with HoloLens.</span></span> <span data-ttu-id="d45ca-107">HoloLens のストアに移動すると、そこに表示されているアプリはすべてその上で動作します。</span><span class="sxs-lookup"><span data-stu-id="d45ca-107">When you go to the Store on your HoloLens, any apps you see there will run on it.</span></span>

<span data-ttu-id="d45ca-108">HoloLens 上のアプリは、2D ビューとホログラフィック ビューのどちらかを使用しています。</span><span class="sxs-lookup"><span data-stu-id="d45ca-108">Apps on HoloLens use either 2D view or holographic view.</span></span> <span data-ttu-id="d45ca-109">2D ビューを利用したアプリは窓のように見えて、周り全体に配置されます。</span><span class="sxs-lookup"><span data-stu-id="d45ca-109">Apps that use 2D view look like windows and can be positioned all around you.</span></span> <span data-ttu-id="d45ca-110">ホログラフィック ビューを使用しているアプリでは、見えるのは周り一面アプリの画面だけになります。</span><span class="sxs-lookup"><span data-stu-id="d45ca-110">Apps that use holographic view surround you and become the only app you see.</span></span>

<span data-ttu-id="d45ca-111">HoloLens は、Microsoft Store の多くの既存のアプリケーションと、HoloLens 専用に構築された新しいアプリをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d45ca-111">HoloLens supports many existing applications from the Microsoft Store, and new apps built specifically for HoloLens.</span></span>  <span data-ttu-id="d45ca-112">この記事では、Microsoft Store の ホログラフィック アプリケーションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d45ca-112">This article focuses on holographic applications from the Microsoft Store.</span></span>

<span data-ttu-id="d45ca-113">カスタム アプリのインストールと実行の詳細については、「[ホログラフィック アプリケーションのカスタム設計](holographic-custom-apps.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d45ca-113">To learn more about installing and running custom apps, read [Custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="find-apps"></a><span data-ttu-id="d45ca-114">アプリの検索</span><span class="sxs-lookup"><span data-stu-id="d45ca-114">Find apps</span></span>

<span data-ttu-id="d45ca-115">**スタート** メニューの Microsoft Store を開きます。</span><span class="sxs-lookup"><span data-stu-id="d45ca-115">Open the Microsoft Store from the **Start** menu.</span></span> <span data-ttu-id="d45ca-116">アプリやゲームを参照します。</span><span class="sxs-lookup"><span data-stu-id="d45ca-116">Then browse for apps and games.</span></span> <span data-ttu-id="d45ca-117">[音声コマンド](hololens-cortana.md)を使用し、"検索"と声に出して検索できます。検索ウィンドウが表示されたら、"ディクテーションを開始"と声に出し、プロンプトが表示されたら、検索語句を読み上げます。</span><span class="sxs-lookup"><span data-stu-id="d45ca-117">You can use [voice commands](hololens-cortana.md) to search by saying "Search", once the search window opens say "Start dictating" and then when prompted begin saying your search terms.</span></span>

> [!NOTE]
> <span data-ttu-id="d45ca-118">HoloLens デバイスのシステム要件は、アプリのビルドのアーキテクチャに基づいています。</span><span class="sxs-lookup"><span data-stu-id="d45ca-118">The System Requirements for HoloLens devices are based on the architecture of the app build.</span></span> <span data-ttu-id="d45ca-119">HoloLens (第 1 世代) のアプリのビルドが、ARM アーキテクチャ パッケージを含めるようにストアの新しい UWP に更新されていない場合、HoloLens 2 デバイスでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="d45ca-119">If an app build for HoloLens (1st gen) has not been updated with to a newer UWP in the store to include the ARM architecture package, then it will not be available for HoloLens 2 devices.</span></span> <span data-ttu-id="d45ca-120">同様に、HoloLens 2 アプリに x86 アーキテクチャパッケージが含まれていない場合は、HoloLens (第 1 世代) デバイスでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="d45ca-120">Likewise, if a HoloLens 2 app does not include the x86 architecture package, it will not be available for HoloLens (1st gen) devices.</span></span> <span data-ttu-id="d45ca-121">HoloLens デバイス アーキテクチャ:</span><span class="sxs-lookup"><span data-stu-id="d45ca-121">HoloLens device architectures:</span></span>
> - <span data-ttu-id="d45ca-122">x86 = HoloLens (第 1 世代)</span><span class="sxs-lookup"><span data-stu-id="d45ca-122">x86 = HoloLens (1st gen)</span></span>
> - <span data-ttu-id="d45ca-123">ARM = HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="d45ca-123">ARM = HoloLens 2</span></span>

> [!NOTE]
> <span data-ttu-id="d45ca-124">2021 年 1 月 12 日に、以下のアプリが HoloLens デバイスでサポートが終了します。</span><span class="sxs-lookup"><span data-stu-id="d45ca-124">On January 12, 2021 the following apps will reach End of Support on HoloLens devices.</span></span> <span data-ttu-id="d45ca-125">アプリの web バージョンを使用するには、デバイスで次のリンクを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d45ca-125">We encourage you to use the following link on your device to use the web version of the app.</span></span>

| <span data-ttu-id="d45ca-126">アプリ</span><span class="sxs-lookup"><span data-stu-id="d45ca-126">App</span></span>        | <span data-ttu-id="d45ca-127">Link</span><span class="sxs-lookup"><span data-stu-id="d45ca-127">Link</span></span>                                          |
|------------|-----------------------------------------------|
| <span data-ttu-id="d45ca-128">Excel Mobile</span><span class="sxs-lookup"><span data-stu-id="d45ca-128">Excel mobile</span></span>      | https://office.live.com/start/Excel.aspx      |
| <span data-ttu-id="d45ca-129">Word Mobile</span><span class="sxs-lookup"><span data-stu-id="d45ca-129">Word mobile</span></span>       | https://office.live.com/start/Word.aspx       |
| <span data-ttu-id="d45ca-130">PowerPoint Mobile</span><span class="sxs-lookup"><span data-stu-id="d45ca-130">PowerPoint mobile</span></span> | https://office.live.com/start/PowerPoint.aspx |

## <a name="install-apps"></a><span data-ttu-id="d45ca-131">アプリのインストール</span><span class="sxs-lookup"><span data-stu-id="d45ca-131">Install apps</span></span>

<span data-ttu-id="d45ca-132">アプリをダウンロードするには、Microsoft アカウントでサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d45ca-132">To download apps, you'll need to be signed in with a Microsoft account.</span></span> <span data-ttu-id="d45ca-133">無料のアプリもあり、すぐにダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="d45ca-133">Some apps are free and can be downloaded right away.</span></span> <span data-ttu-id="d45ca-134">購入が必要なアプリには、Microsoft アカウントを使用してストアにサインインし、有効な支払い方法をお持ちであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="d45ca-134">For apps that require a purchase, you must be signed in to the Store with your Microsoft account and have a valid payment method.</span></span>
> [!NOTE]
> <span data-ttu-id="d45ca-135">Microsoft Store で使用するアカウントは、サインインに使用するアカウントと同一のものである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d45ca-135">The account you use on Microsoft Store does not have to be the same as the account you are signed in with.</span></span> <span data-ttu-id="d45ca-136">職場または学校用の HoloLens アカウントを使用している場合、購入するには、ストア アプリの個人用アカウントでサインインする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d45ca-136">If you are using a Work or School account on your HoloLens then you may need to sign in with your personal account in the Store App to make a purchase.</span></span>

> [!TIP]
> <span data-ttu-id="d45ca-137">支払い方法を設定するには、[account.microsoft.com](https://account.microsoft.com/) に移動し、**[支払いと請求]** > **[支払オプション]** > **[支払オプションの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d45ca-137">To set up a payment method, go to [account.microsoft.com](https://account.microsoft.com/) and select **Payment & billing** > **Payment options** > **Add a payment option**.</span></span>

1. <span data-ttu-id="d45ca-138">[**[スタート]** メニューを開くには](holographic-home.md)、HoloLens (第1世代) の [[スタート ジェスチャ]](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) または [[ブルーム]](hololens1-basic-usage.md) ジェスチャを実行します。</span><span class="sxs-lookup"><span data-stu-id="d45ca-138">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>
1. <span data-ttu-id="d45ca-139">Microsoft Store アプリを選択する。</span><span class="sxs-lookup"><span data-stu-id="d45ca-139">Select the Microsoft Store app.</span></span> <span data-ttu-id="d45ca-140">ストア アプリが開いたら、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d45ca-140">After the Store app opens:</span></span>
   1. <span data-ttu-id="d45ca-141">検索バーを使用してアプリケーションを検索します。</span><span class="sxs-lookup"><span data-stu-id="d45ca-141">Use the search bar to look for applications.</span></span> 
   1. <span data-ttu-id="d45ca-142">整理されたカテゴリのいずれかの中から、必須アプリや HoloLens 専用に作成されたアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="d45ca-142">Select essential apps or apps made specifically for HoloLens from one of the curated categories.</span></span>
   1. <span data-ttu-id="d45ca-143">ストア アプリの右上で、[**...**] ボタンを選択し、[**マイライブラリ**] を選択して、以前購入したアプリを表示します。</span><span class="sxs-lookup"><span data-stu-id="d45ca-143">On the top right of the Store app, select the **"..."** button and then select **My Library** to view any previously purchased apps.</span></span>
1. <span data-ttu-id="d45ca-144">アプリケーションのページで、[**取得**] または [**インストール**] (購入が必要になる場合があります) を選びます。</span><span class="sxs-lookup"><span data-stu-id="d45ca-144">Select **Get** or **Install** on the application's page (a purchase may be required).</span></span>

## <a name="update-apps"></a><span data-ttu-id="d45ca-145">アプリの更新</span><span class="sxs-lookup"><span data-stu-id="d45ca-145">Update Apps</span></span>
<span data-ttu-id="d45ca-146">Microsoft Store からインストールしたアプリを更新するには、Microsoft Store アプリからアプリを更新できます。</span><span class="sxs-lookup"><span data-stu-id="d45ca-146">To update an app you installed from the Microsoft Store, you can update the app from the Microsoft Store app.</span></span> <span data-ttu-id="d45ca-147">ビジネス向け Microsoft Store 用にインストールされたアプリの場合には、ビジネス向け Microsoft Store からそれらのアプリを更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="d45ca-147">For apps installed for the Microsoft Store for Business, you can also update those apps from the Microsoft Store for Business.</span></span> 
1. <span data-ttu-id="d45ca-148">[[**スタート**] メニュー](holographic-home.md)を開くには、HoloLens (第1世代) で [[スタート ジェスチャ](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture)] または [[ブルーム](hololens1-basic-usage.md)] ジェスチャを実行します。</span><span class="sxs-lookup"><span data-stu-id="d45ca-148">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>
1. <span data-ttu-id="d45ca-149">[ストア] アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="d45ca-149">Select the Store app.</span></span>
1. <span data-ttu-id="d45ca-150">ストア アプリの右上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d45ca-150">Look to the top right of the Store app.</span></span> 
1. <span data-ttu-id="d45ca-151">[**...**] または [詳細を表示] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="d45ca-151">Select the **"..."** or “See more” button.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Microsoft ストア アプリのスクリーンショット。](images/store-update-1.png)

1. <span data-ttu-id="d45ca-153">[**ダウンロードと更新プログラム**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d45ca-153">Select **Downloads and updates**.</span></span>
    1. <span data-ttu-id="d45ca-154">ご利用のデバイスが以前に更新プログラムを特定している場合には、下向きの矢印と保留中の更新プログラムを表す数字が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d45ca-154">If your device has previously identified updates, there may be a down arrow and a number that represents pending updates.</span></span>
1. <span data-ttu-id="d45ca-155">[**更新プログラムを取得する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d45ca-155">Select **Get updates**.</span></span> <span data-ttu-id="d45ca-156">デバイスが更新プログラムを検索するので、ダウンロードしてインストールするように設定します。</span><span class="sxs-lookup"><span data-stu-id="d45ca-156">Your device will now search for updates and set them to download and install.</span></span> 
 
   > [!div class="mx-imgBorder"]
   > ![Microsoft ストア アプリが更新プログラムを取得している様子のスクリーンショット。](images/store-update-2.png.jpg)

> [!NOTE]
> <span data-ttu-id="d45ca-158">お使いのデバイスのアプリが組織によって配布されている場合は、同じ商用アプリ管理方法で更新できます。</span><span class="sxs-lookup"><span data-stu-id="d45ca-158">If the apps on your device were distrubted by your organization they can be updated through the same commercial app management methods.</span></span> <span data-ttu-id="d45ca-159">お客様の状況に当てはまる場合は、[商用アプリの導入の概要](app-deploy-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d45ca-159">If this applies to your situation, read more via our [overview of commercial app deployment.](app-deploy-overview.md)</span></span>
>
> <span data-ttu-id="d45ca-160">サイドロードまたは導入されているカスタム アプリを更新する場合は、更新されたバージョンのアプリで同じ方法を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d45ca-160">If you would like to update a custom app that has been sideloaded or deployed, you will need to use the same method with the updated version of your app.</span></span> <span data-ttu-id="d45ca-161">カスタム アプリのインストールと実行の詳細については、「[ホログラフィック アプリケーションのカスタム設計](holographic-custom-apps.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d45ca-161">To learn more about installing and running custom apps, read [custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="uninstall-apps"></a><span data-ttu-id="d45ca-162">アプリのアンインストール</span><span class="sxs-lookup"><span data-stu-id="d45ca-162">Uninstall apps</span></span>

<span data-ttu-id="d45ca-163">アプリケーションをアンインストールするには、2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="d45ca-163">There are two ways to uninstall applications.</span></span>  <span data-ttu-id="d45ca-164">アプリケーションをアンインストールするには、Microsoft ストアまたは [スタート] メニューを使用します。</span><span class="sxs-lookup"><span data-stu-id="d45ca-164">You can uninstall applications through the Microsoft Store or Start menu.</span></span>

### <a name="uninstall-from-the-start-menu"></a><span data-ttu-id="d45ca-165">[スタート] メニューからアンインストールする場合</span><span class="sxs-lookup"><span data-stu-id="d45ca-165">Uninstall from the Start menu</span></span>

<span data-ttu-id="d45ca-166">[**スタート**] メニューまたは [**すべてのアプリ**] リストから、アプリを参照します。</span><span class="sxs-lookup"><span data-stu-id="d45ca-166">On the **Start** menu or in the **All apps** list, browse to the app.</span></span> <span data-ttu-id="d45ca-167">メニューが表示されるまで選択して長押しし、[**アンインストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d45ca-167">Select and hold until the menu appears, then select **Uninstall**.</span></span>

### <a name="uninstall-from-the-microsoft-store"></a><span data-ttu-id="d45ca-168">Microsoft Store からアンインストールする</span><span class="sxs-lookup"><span data-stu-id="d45ca-168">Uninstall from the Microsoft Store</span></span>

<span data-ttu-id="d45ca-169">[**スタート**] メニューから Microsoft Store を開き、アンインストールするアプリケーションを表示します。</span><span class="sxs-lookup"><span data-stu-id="d45ca-169">Open the Microsoft Store from the **Start** menu, and then browse for the application you want to uninstall.</span></span>  <span data-ttu-id="d45ca-170">[ストア] ページでは、インストールされている各アプリケーションに [**アンインストール**] ボタンが表示されています。</span><span class="sxs-lookup"><span data-stu-id="d45ca-170">On the Store page, each installed application has an **Uninstall** button.</span></span>
