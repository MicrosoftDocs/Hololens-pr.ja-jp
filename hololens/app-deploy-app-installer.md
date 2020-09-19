---
title: HoloLens 2 アプリインストーラーを使用してアプリをサイドロードおよびインストールする方法
description: UI を使用したスライドの読み込みとアプリのインストール
keywords: アプリ管理、アプリ、hololens、アプリインストーラー
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2387c0eb65efc312db4eea7118f3cca44ce6d4b6
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027478"
---
# <span data-ttu-id="74797-104">アプリインストーラーを使用して HoloLens 2 にアプリをインストールする</span><span class="sxs-lookup"><span data-stu-id="74797-104">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="74797-105">ユーザーは、開発者モードを有効にしたり、Device Portal を使用したりする必要がないので、Appx バンドルを使ってアプリをインストールできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="74797-105">Users can now install Apps via Appx Bundles now without the need to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="74797-106">このエクスペリエンスは、ローカルデバイスにアプリをインストールしたり、HoloLens で他のアプリのインストール方法に慣れていない他のユーザーとアプリを共有したりする場合に簡単です。</span><span class="sxs-lookup"><span data-stu-id="74797-106">This experience is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="74797-107">この機能は、現時点では、Windows Insider ビルド 19041.1377 + でのみ avalible になっています。</span><span class="sxs-lookup"><span data-stu-id="74797-107">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="74797-108">[詳細については、「Windows Insider ビルドに登録する」を参照して](hololens-insider.md)ください。</span><span class="sxs-lookup"><span data-stu-id="74797-108">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

> [!NOTE]
> <span data-ttu-id="74797-109">アプリのインストーラーでストアからの依存関係が使用されるため、アプリのソリューション構成は **Master** または **Release** のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="74797-109">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="74797-110">詳細については、「 [アプリパッケージの作成](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74797-110">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

1.  <span data-ttu-id="74797-111">HoloLens 2 デバイスの電源が入っていて、サインインしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="74797-111">Ensure that your HoloLens 2 device is powered on and you are signed in.</span></span>
1.  <span data-ttu-id="74797-112">PC でカスタムアプリに移動し、yourapp を yourdevicename\Internal Storage\Downloads. にコピーします。</span><span class="sxs-lookup"><span data-stu-id="74797-112">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span> 
    <span data-ttu-id="74797-113">ファイルのコピーが完了したら、デバイスを切断して、後でインストールを完了することができます。</span><span class="sxs-lookup"><span data-stu-id="74797-113">After your finish copying your file you may disconnect your device and finish the install later.</span></span>
1.  <span data-ttu-id="74797-114">HoloLens 2 デバイスから [ **スタート] メニュー**を開き、[ **すべてのアプリ** ] を選択して、 **エクスプローラー** アプリを起動します。</span><span class="sxs-lookup"><span data-stu-id="74797-114">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1.  <span data-ttu-id="74797-115">[ダウンロード] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="74797-115">Navigate to the Downloads folder.</span></span> <span data-ttu-id="74797-116">アプリの左側のパネルで、[ **このデバイス** ] を選択してから、[ダウンロード] に移動することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="74797-116">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="74797-117">Yourapp ファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="74797-117">Select the yourapp.appxbundle file.</span></span> 
1.  <span data-ttu-id="74797-118">アプリのインストーラーが起動します。</span><span class="sxs-lookup"><span data-stu-id="74797-118">The App Installer will launch.</span></span> <span data-ttu-id="74797-119">アプリをインストールするには、[ **インストール** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="74797-119">Select the **Install** button to install your app.</span></span> 

<span data-ttu-id="74797-120">インストールされたアプリは、インストールの完了時に自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="74797-120">The installed app will automatically launch upon the completion of installing.</span></span> 

![App Installer による MRTK の例のインストール](images/hololens-app-installer-picture.jpg)

<span data-ttu-id="74797-122">アプリのインストールに失敗した場合は、次のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="74797-122">If your app failed to install check the following:</span></span>
-   <span data-ttu-id="74797-123">アプリがマスターまたはリリースビルドのどちらかです。</span><span class="sxs-lookup"><span data-stu-id="74797-123">Your app is either a Master or Release build.</span></span>
-   <span data-ttu-id="74797-124">[インターネットに接続](hololens-network.md)されています。</span><span class="sxs-lookup"><span data-stu-id="74797-124">You are [connected to the internet](hololens-network.md).</span></span>
-   <span data-ttu-id="74797-125">[Microsoft Store のエンドポイント](hololens-offline.md)が適切に構成されている。</span><span class="sxs-lookup"><span data-stu-id="74797-125">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  
