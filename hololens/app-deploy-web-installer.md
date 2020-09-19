---
title: Web Installer を使用してアプリをインストールする方法
description: Web installer for app installer を使ってアプリをインストールする
keywords: アプリ管理、アプリ、hololens、アプリインストーラー、web インストール
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
ms.openlocfilehash: 186cbefb2822455dcf922804ea09533b833b8663
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027477"
---
# <span data-ttu-id="41198-104">Web ページからのアプリのインストール</span><span class="sxs-lookup"><span data-stu-id="41198-104">Installing apps from a web page</span></span>

<span data-ttu-id="41198-105">ユーザーは、web サーバーから直接アプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="41198-105">Users can install an app directly from a web server.</span></span> <span data-ttu-id="41198-106">これにより、アプリのインストーラーが、簡単なダウンロードとインストールの配布方法と組み合わされて使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="41198-106">This takes use of the App Installer combined with an easy download and install distribution method.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="41198-107">この機能は、現時点では、Windows Insider ビルド 19041.1366 + でのみ avalible になっています。</span><span class="sxs-lookup"><span data-stu-id="41198-107">This feature is currently only avalible in Windows Insider builds 19041.1366+.</span></span> <span data-ttu-id="41198-108">[詳細については、「Windows Insider ビルドに登録する」を参照して](hololens-insider.md)ください。</span><span class="sxs-lookup"><span data-stu-id="41198-108">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

## <span data-ttu-id="41198-109">設定方法:</span><span class="sxs-lookup"><span data-stu-id="41198-109">How to set this up:</span></span>
1.  <span data-ttu-id="41198-110">アプリが正しくインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="41198-110">Ensure your app is correctly configured to install.</span></span>
1.  <span data-ttu-id="41198-111">[Web ページでこの機能を有効にするには、次の手順を](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)実行します。</span><span class="sxs-lookup"><span data-stu-id="41198-111">Follow these [steps to enable this on a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span> 
1.  <span data-ttu-id="41198-112">証明書の展開方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="41198-112">Pick a certificate deployment method.</span></span> 
    1.  <span data-ttu-id="41198-113">[プロビジョニングパッケージ](hololens-provisioning.md) はローカルデバイスに適用できます。</span><span class="sxs-lookup"><span data-stu-id="41198-113">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
    1.  <span data-ttu-id="41198-114">MDM を使って、 [デバイスの構成に証明書を適用](https://docs.microsoft.com/mem/intune/protect/certificates-configure)することができます。</span><span class="sxs-lookup"><span data-stu-id="41198-114">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
    1.  <span data-ttu-id="41198-115">デバイス [証明書マネージャー](hololens-insider.md#certificate-manager)を使用します。</span><span class="sxs-lookup"><span data-stu-id="41198-115">Use the on device [Certificate Manager](hololens-insider.md#certificate-manager).</span></span> 

## <span data-ttu-id="41198-116">エンドユーザーエクスペリエンス:</span><span class="sxs-lookup"><span data-stu-id="41198-116">End User Experience:</span></span>
1.  <span data-ttu-id="41198-117">ユーザーは、前に選択した方法を使用して、デバイスに証明書を受け取り、インストールします。</span><span class="sxs-lookup"><span data-stu-id="41198-117">User receives and installs certificate to the device using a method previously chosen above.</span></span> 
1.  <span data-ttu-id="41198-118">ユーザーは、上の手順で作成した URL にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="41198-118">User visits the URL created from the step above.</span></span>

<span data-ttu-id="41198-119">これで、アプリがデバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="41198-119">The app will now install to the device.</span></span> <span data-ttu-id="41198-120">アプリを見つけるには、[ **スタート] メニュー** を開き、[ **すべてのアプリ** ] ボタンを選んでアプリを見つけます。</span><span class="sxs-lookup"><span data-stu-id="41198-120">To find the app open the **Start menu** and select the **All apps** button to find your app.</span></span> 

-   <span data-ttu-id="41198-121">このインストール方法のトラブルシューティングについては、「 [アプリインストーラーの問題のトラブルシューティング](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41198-121">For help troubleshooting this installation method please visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span> 

> [!NOTE]
> <span data-ttu-id="41198-122">更新プロセス中の UI はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="41198-122">UI during the update process is not supported.</span></span> <span data-ttu-id="41198-123">そのため、 [このページ](https://docs.microsoft.com/windows/msix/app-installer/update-settings) と関連オプションの showprompt オプションはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="41198-123">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>
