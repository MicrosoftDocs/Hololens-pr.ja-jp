---
title: HoloLens のカスタムアプリを管理する (第1世代)
description: デバイスポータルと Visual Studio を使用して、カスタム holographic アプリを HoloLens デバイスにインストール、アンインストール、およびサイドロードする方法について説明します。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens、サイドロード、サイドロード、サイドロード、ストア、uwp、アプリ、インストール
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309308"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a><span data-ttu-id="707b1-104">HoloLens のカスタムアプリを管理する (第1世代)</span><span class="sxs-lookup"><span data-stu-id="707b1-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="707b1-105">HoloLens は、Microsoft Store からの多くの既存アプリケーションと、HoloLens 専用に構築された新しいアプリをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="707b1-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="707b1-106">この記事では、カスタム holographic アプリケーションに焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="707b1-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="707b1-107">ストアアプリの詳細については、「 [ストアアプリを使用したアプリの管理](holographic-store-apps.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="707b1-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="707b1-108">HoloLens (第1世代) 用に次の情報が作成されました。この時点では、HoloLens Developer Edition とも呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="707b1-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="707b1-109">このようなサイドローディングアプリは、デバイスポータルを使用して、Visual Studio でアプリをインストールすることが一般的でした。</span><span class="sxs-lookup"><span data-stu-id="707b1-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="707b1-110">エンタープライズ展開では、開発者モードを有効にしないことをお勧めします。これらの方法はどちらも使用します。</span><span class="sxs-lookup"><span data-stu-id="707b1-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="707b1-111">セキュリティで保護されたアプリのデプロイ方法に関心がある場合は、 [アプリ管理の概要](app-deploy-overview.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="707b1-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="707b1-112">HoloLens 2 デバイスに対して開発者向けのアプリのインストール方法をお探しの場合は、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="707b1-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="707b1-113">デバイスポータル: アプリのインストール</span><span class="sxs-lookup"><span data-stu-id="707b1-113">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="707b1-114">Visual Studio を使用したアプリの配置とデバッグ</span><span class="sxs-lookup"><span data-stu-id="707b1-114">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a><span data-ttu-id="707b1-115">カスタム アプリをインストールする</span><span class="sxs-lookup"><span data-stu-id="707b1-115">Install custom apps</span></span>

<span data-ttu-id="707b1-116">デバイスポータルを使用するか、Visual Studio からアプリをデプロイして、独自のアプリケーションを HoloLens にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="707b1-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <a name="installing-an-application-package-with-the-device-portal"></a><span data-ttu-id="707b1-117">デバイスポータルを使用したアプリケーションパッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="707b1-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="707b1-118">[デバイスポータル](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)からターゲット HoloLens への接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="707b1-118">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="707b1-119">左側のナビゲーションで、[ **アプリ** ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="707b1-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="707b1-120">[ **アプリパッケージ** ] の下で、アプリケーションに関連付けられている .appx ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="707b1-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="707b1-121">関連する依存関係および証明書ファイルを必ず参照してください。</span><span class="sxs-lookup"><span data-stu-id="707b1-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="707b1-122">**[Go] \(移動)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="707b1-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="707b1-123">![Microsoft HoloLens の Windows デバイスポータルでアプリフォームをインストールする](images/deviceportal-appmanager.jpg)</span><span class="sxs-lookup"><span data-stu-id="707b1-123">![Install app form in Windows Device Portal on Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span></span>

### <a name="deploying-from-microsoft-visual-studio-2015"></a><span data-ttu-id="707b1-124">Microsoft Visual Studio 2015 からの展開</span><span class="sxs-lookup"><span data-stu-id="707b1-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="707b1-125">アプリの Visual Studio ソリューション (.sln ファイル) を開きます。</span><span class="sxs-lookup"><span data-stu-id="707b1-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="707b1-126">プロジェクトの **プロパティ** を開きます。</span><span class="sxs-lookup"><span data-stu-id="707b1-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="707b1-127">次のビルド構成を選択します: **マスター/x86/リモートコンピューター**。</span><span class="sxs-lookup"><span data-stu-id="707b1-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="707b1-128">[ **リモートコンピューター**] を選択した場合:</span><span class="sxs-lookup"><span data-stu-id="707b1-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="707b1-129">アドレスが HoloLens の Wi-Fi IP アドレスを指していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="707b1-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="707b1-130">認証を **Universal (暗号化** されていないプロトコル) に設定します。</span><span class="sxs-lookup"><span data-stu-id="707b1-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="707b1-131">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="707b1-131">Build your solution.</span></span>

1. <span data-ttu-id="707b1-132">開発用 PC から HoloLens にアプリをデプロイするには、[ **リモートコンピューター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="707b1-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="707b1-133">HoloLens に既存のビルドが既に存在する場合は、[ **はい]** を選択して、この新しいバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="707b1-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Visual Studio でのアプリの Microsoft HoloLens へのリモートコンピューターの展開](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="707b1-135">アプリケーションが HoloLens にインストールされ、自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="707b1-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="707b1-136">アプリをインストールすると、[**すべてのアプリ**] の一覧に表示されます ([すべてのアプリを **開始**]  >  )。</span><span class="sxs-lookup"><span data-stu-id="707b1-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
