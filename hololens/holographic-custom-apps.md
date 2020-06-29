---
title: HoloLens 用のカスタム アプリを管理する
description: HoloLens でカスタムアプリを読み込みます。 ホログラフィックアプリのインストールとアンインストールの詳細については、こちらを参照してください。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 07/01/2019
manager: v-miegge
keywords: hololens、サイドローディング、サイドロード、サイドロード、ストア、uwp、アプリ、インストール
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 12c5eedfab580be8acea48c1fc19b56c1ead08ac
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828862"
---
# <span data-ttu-id="a9a78-105">HoloLens 用のカスタム アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="a9a78-105">Manage custom apps for HoloLens</span></span>

<span data-ttu-id="a9a78-106">HoloLens では、Microsoft Store の既存のアプリケーションのほか、HoloLens 専用に構築された新しいアプリがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a9a78-106">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="a9a78-107">この記事では、カスタムのホログラフィックアプリケーションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a9a78-107">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="a9a78-108">ストアアプリの詳細については、「[ストアを使用してアプリを管理する](holographic-store-apps.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9a78-108">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

## <span data-ttu-id="a9a78-109">カスタムアプリをインストールする</span><span class="sxs-lookup"><span data-stu-id="a9a78-109">Install custom apps</span></span>

<span data-ttu-id="a9a78-110">HoloLens に独自のアプリケーションをインストールするには、Device Portal を使用するか、Visual Studio からアプリを展開します。</span><span class="sxs-lookup"><span data-stu-id="a9a78-110">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="a9a78-111">Device Portal でアプリケーションパッケージをインストールする</span><span class="sxs-lookup"><span data-stu-id="a9a78-111">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="a9a78-112">[Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)からターゲット HoloLens への接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="a9a78-112">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>
1. <span data-ttu-id="a9a78-113">左側のナビゲーションで、[**アプリ**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="a9a78-113">In the left navigation, navigate to the **Apps** page .</span></span>
1. <span data-ttu-id="a9a78-114">[**アプリパッケージ**] で、アプリケーションに関連付けられている .appx ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="a9a78-114">Under **App Package** browse to the .appx file that is associated with your application.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="a9a78-115">関連する依存関係と証明書ファイルを必ず参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9a78-115">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="a9a78-116">[**移動**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a9a78-116">Select **Go**.</span></span>
   ![Microsoft HoloLens の Windows Device Portal でアプリフォームをインストールする](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="a9a78-118">Microsoft Visual Studio 2015 からの展開</span><span class="sxs-lookup"><span data-stu-id="a9a78-118">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="a9a78-119">アプリの Visual Studio ソリューション (.sln ファイル) を開きます。</span><span class="sxs-lookup"><span data-stu-id="a9a78-119">Open your app's Visual Studio solution (.sln file).</span></span>
1. <span data-ttu-id="a9a78-120">プロジェクトの**プロパティ**を開きます。</span><span class="sxs-lookup"><span data-stu-id="a9a78-120">Open the project's **Properties**.</span></span>
1. <span data-ttu-id="a9a78-121">次のビルド構成を選択します: **Master/x86/リモートコンピューター**</span><span class="sxs-lookup"><span data-stu-id="a9a78-121">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>
1. <span data-ttu-id="a9a78-122">[**リモートコンピューター**] を選択すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a9a78-122">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="a9a78-123">アドレスが HoloLens の Wi-fi IP アドレスを指していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a9a78-123">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="a9a78-124">認証を**ユニバーサル (暗号化**されていないプロトコル) に設定します。</span><span class="sxs-lookup"><span data-stu-id="a9a78-124">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
1. <span data-ttu-id="a9a78-125">ソリューションを構築します。</span><span class="sxs-lookup"><span data-stu-id="a9a78-125">Build your solution.</span></span>
1. <span data-ttu-id="a9a78-126">開発用 PC から HoloLens にアプリを展開するには、[**リモートコンピューター**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a9a78-126">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="a9a78-127">既存のビルドが HoloLens に既にある場合は、[**はい]** を選んで新しいバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a9a78-127">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Visual Studio でのアプリのリモートコンピューターによる Microsoft HoloLens への展開](images/vs2015-remotedeployment.jpg)  
1. <span data-ttu-id="a9a78-129">アプリは、HoloLens にインストールされ、自動起動します。</span><span class="sxs-lookup"><span data-stu-id="a9a78-129">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="a9a78-130">アプリをインストールすると、[**すべて**のアプリ] の一覧にアプリが表示されます (すべてのアプリを**起動**  >  **All apps**します)。</span><span class="sxs-lookup"><span data-stu-id="a9a78-130">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
