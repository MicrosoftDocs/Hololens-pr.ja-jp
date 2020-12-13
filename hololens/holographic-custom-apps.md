---
title: HoloLens 用のカスタム アプリを管理する
description: HoloLens でのカスタム アプリのサイド ロード。 ホログラフィック アプリのインストールとアンインストールについて詳しくは、以下をご覧ください。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, サイドロード, サイドロード, サイドロード, ストア, UWP, アプリ, インストール
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
ms.openlocfilehash: 67a857eb35126435f5642ee60168128300401394
ms.sourcegitcommit: cd2071c12eaabe46c829b53c22d13e21b8af5b53
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "11218634"
---
# <span data-ttu-id="d891b-105">HoloLens 用のカスタム アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="d891b-105">Manage custom apps for HoloLens</span></span>

<span data-ttu-id="d891b-106">HoloLens は、HoloLens 用に特別に作られた新しいアプリだけでなく、Microsoft ストアにある既存のアプリケーションの多くもサポートします。</span><span class="sxs-lookup"><span data-stu-id="d891b-106">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="d891b-107">この記事では、カスタム ホログラフィック アプリケーションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d891b-107">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="d891b-108">ストア アプリの詳細については、「ストアでアプリ [を管理する」を参照してください](holographic-store-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="d891b-108">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d891b-109">次の情報は、HoloLens (第 1 世代) (HoloLens Developer Edition とも呼ばれる) 用に作成されました。</span><span class="sxs-lookup"><span data-stu-id="d891b-109">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="d891b-110">そのため、デバイス ポータル経由でアプリをサイドローディングし、デバイス ポータルを使Visual Studioアプリをインストールする方法は一般的でした。</span><span class="sxs-lookup"><span data-stu-id="d891b-110">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="d891b-111">エンタープライズ展開では、両方の方法で使用する開発者モードを有効にすることをお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="d891b-111">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="d891b-112">セキュリティで保護されたアプリの展開方法に関心がある場合は、「アプリ管理: 概要」を [確認してください](app-deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d891b-112">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="d891b-113">HoloLens 2 デバイス用のアプリインストールの開発者向け方法をお探しの場合は、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d891b-113">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="d891b-114">Device Portal: アプリのインストール</span><span class="sxs-lookup"><span data-stu-id="d891b-114">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="d891b-115">アプリVisual Studioを使用してアプリを展開およびデバッグする</span><span class="sxs-lookup"><span data-stu-id="d891b-115">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <span data-ttu-id="d891b-116">カスタム アプリをインストールする</span><span class="sxs-lookup"><span data-stu-id="d891b-116">Install custom apps</span></span>

<span data-ttu-id="d891b-117">HoloLens に独自のアプリケーションをインストールするには、Device Portal を使用するか、デバイス ポータルからアプリを展開Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="d891b-117">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="d891b-118">Device Portal でのアプリケーション パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="d891b-118">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="d891b-119">Device Portal から [ターゲット HoloLens](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) への接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="d891b-119">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>
1. <span data-ttu-id="d891b-120">左側のナビゲーションで、[アプリ] ページ **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="d891b-120">In the left navigation, navigate to the **Apps** page .</span></span>
1. <span data-ttu-id="d891b-121">[ **アプリ パッケージ]** で、アプリケーションに関連付けられている .appx ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="d891b-121">Under **App Package** browse to the .appx file that is associated with your application.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="d891b-122">関連付けられている依存関係ファイルと証明書ファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d891b-122">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="d891b-123">[移動 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d891b-123">Select **Go**.</span></span>
   ![Microsoft HoloLens の Windows Device Portal にアプリ フォームをインストールする](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="d891b-125">Microsoft Visual Studio 2015 からの展開</span><span class="sxs-lookup"><span data-stu-id="d891b-125">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="d891b-126">アプリの新しいソリューションVisual Studio (.sln ファイル) を開きます。</span><span class="sxs-lookup"><span data-stu-id="d891b-126">Open your app's Visual Studio solution (.sln file).</span></span>
1. <span data-ttu-id="d891b-127">プロジェクトのプロパティを開 **きます**。</span><span class="sxs-lookup"><span data-stu-id="d891b-127">Open the project's **Properties**.</span></span>
1. <span data-ttu-id="d891b-128">次のビルド構成を選択します **:Master/x86/Remote Machine**。</span><span class="sxs-lookup"><span data-stu-id="d891b-128">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>
1. <span data-ttu-id="d891b-129">リモート コンピューターを **選択した場合**:</span><span class="sxs-lookup"><span data-stu-id="d891b-129">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="d891b-130">アドレスが HoloLens の Wi-Fi IP アドレスをポイントしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d891b-130">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="d891b-131">認証を **ユニバーサル (暗号化されていないプロトコル) に設定します**。</span><span class="sxs-lookup"><span data-stu-id="d891b-131">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
1. <span data-ttu-id="d891b-132">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="d891b-132">Build your solution.</span></span>
1. <span data-ttu-id="d891b-133">開発用 PC から HoloLens にアプリを展開するには、[リモート コンピューター] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d891b-133">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="d891b-134">HoloLens に既存のビルドが既にある場合は、[ **は** い] を選択してこの新しいバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d891b-134">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Microsoft HoloLens へのアプリのリモート コンピューター Visual Studio](images/vs2015-remotedeployment.jpg)  
1. <span data-ttu-id="d891b-136">アプリケーションが HoloLens にインストールされ、自動起動されます。</span><span class="sxs-lookup"><span data-stu-id="d891b-136">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="d891b-137">アプリをインストールすると、[すべてのアプリ] の一覧 ([\*\*\*\* すべてのアプリを起動] )**に**  >  **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="d891b-137">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
