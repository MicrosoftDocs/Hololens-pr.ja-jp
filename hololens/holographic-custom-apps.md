---
title: HoloLens (第 1 世代) 用のカスタム アプリを管理する
description: Device Portal とデバイス ポータルを使用して、HoloLens デバイスにカスタム ホログラフィック アプリをインストール、アンインストール、サイド ロードする方法Visual Studio。
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
ms.openlocfilehash: 721c169c8ad34acab6914448af8ffc6ceec97a0e
ms.sourcegitcommit: 4c6d982bee72195bef955532738711f2b00ac8be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "11296990"
---
# <span data-ttu-id="b45c2-104">HoloLens (第 1 世代) 用のカスタム アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="b45c2-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="b45c2-105">HoloLens は、HoloLens 用に特別に作られた新しいアプリだけでなく、Microsoft ストアにある既存のアプリケーションの多くもサポートします。</span><span class="sxs-lookup"><span data-stu-id="b45c2-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="b45c2-106">この記事では、カスタム ホログラフィック アプリケーションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b45c2-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="b45c2-107">ストア アプリの詳細については、「ストアでアプリ [を管理する」を参照してください](holographic-store-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="b45c2-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b45c2-108">次の情報は、HoloLens (第 1 世代) (HoloLens Developer Edition とも呼ばれる) 用に作成されました。</span><span class="sxs-lookup"><span data-stu-id="b45c2-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="b45c2-109">そのため、デバイス ポータル経由でアプリをサイドローディングし、デバイス ポータルを使Visual Studioアプリをインストールする方法は一般的でした。</span><span class="sxs-lookup"><span data-stu-id="b45c2-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="b45c2-110">エンタープライズ展開では、両方の方法で使用する開発者モードを有効にすることをお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="b45c2-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="b45c2-111">セキュリティで保護されたアプリの展開方法に関心がある場合は、「アプリ管理: 概要」を [確認してください](app-deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b45c2-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="b45c2-112">HoloLens 2 デバイス用のアプリのインストール方法を開発者向けにお探しの場合は、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b45c2-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="b45c2-113">Device Portal: アプリのインストール</span><span class="sxs-lookup"><span data-stu-id="b45c2-113">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="b45c2-114">アプリVisual Studioを使用してアプリを展開およびデバッグする</span><span class="sxs-lookup"><span data-stu-id="b45c2-114">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <span data-ttu-id="b45c2-115">カスタム アプリをインストールする</span><span class="sxs-lookup"><span data-stu-id="b45c2-115">Install custom apps</span></span>

<span data-ttu-id="b45c2-116">HoloLens に独自のアプリケーションをインストールするには、Device Portal を使用するか、デバイス ポータルからアプリを展開Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="b45c2-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="b45c2-117">Device Portal でのアプリケーション パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="b45c2-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="b45c2-118">Device Portal から [ターゲット HoloLens](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) への接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="b45c2-118">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="b45c2-119">左側のナビゲーションで、[アプリ] ページ **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="b45c2-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="b45c2-120">[ **アプリ パッケージ]** で、アプリケーションに関連付けられている .appx ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="b45c2-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="b45c2-121">関連付けられている依存関係ファイルと証明書ファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b45c2-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="b45c2-122">[移動 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b45c2-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Microsoft HoloLens の Windows Device Portal にアプリ フォームをインストールする](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="b45c2-124">Microsoft Visual Studio 2015 からの展開</span><span class="sxs-lookup"><span data-stu-id="b45c2-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="b45c2-125">アプリの新しいソリューションVisual Studio (.sln ファイル) を開きます。</span><span class="sxs-lookup"><span data-stu-id="b45c2-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="b45c2-126">プロジェクトのプロパティを開 **きます**。</span><span class="sxs-lookup"><span data-stu-id="b45c2-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="b45c2-127">次のビルド構成を選択します **:Master/x86/Remote Machine**。</span><span class="sxs-lookup"><span data-stu-id="b45c2-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="b45c2-128">リモート コンピューターを **選択した場合**:</span><span class="sxs-lookup"><span data-stu-id="b45c2-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="b45c2-129">アドレスが HoloLens の Wi-Fi IP アドレスをポイントしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b45c2-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="b45c2-130">認証を **ユニバーサル (暗号化されていないプロトコル) に設定します**。</span><span class="sxs-lookup"><span data-stu-id="b45c2-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="b45c2-131">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="b45c2-131">Build your solution.</span></span>

1. <span data-ttu-id="b45c2-132">開発用 PC から HoloLens にアプリを展開するには、[リモート コンピューター] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b45c2-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="b45c2-133">HoloLens に既にビルドがある場合は、[はい] **を選択して** この新しいバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b45c2-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Microsoft HoloLens へのアプリのリモート コンピューター Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="b45c2-135">アプリケーションが HoloLens にインストールされ、自動起動されます。</span><span class="sxs-lookup"><span data-stu-id="b45c2-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="b45c2-136">アプリをインストールすると、[すべてのアプリ] の一覧 ([\*\*\*\* すべてのアプリを起動] )**に**  >  **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="b45c2-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
