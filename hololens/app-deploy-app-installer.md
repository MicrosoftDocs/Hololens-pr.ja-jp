---
title: HoloLens 2 アプリ インストーラーを使用してアプリをサイド ロードしてインストールする方法
description: アプリ インストーラーを使ってアプリをインストールし、トラブルシューティングを行い、UI を使ってアプリをサイド ロードしてインストールする方法について説明します。
keywords: アプリ管理, アプリ, hololens, アプリ インストーラー
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 9e413963dbf34dd071fc9603487590065b967ee7
ms.sourcegitcommit: af4e222a4f83ab82466a383099897986ddf6b8c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "11297292"
---
# <span data-ttu-id="349d8-104">アプリ インストーラーを使用して HoloLens 2 にアプリをインストールする</span><span class="sxs-lookup"><span data-stu-id="349d8-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="349d8-105">この機能は [、Windows Holographic バージョン 20H2 ~ December 2020 Update で利用できます](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="349d8-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="349d8-106">この機能を使用 [するためにデバイスが](hololens-update-hololens.md) 更新されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="349d8-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="349d8-107">HoloLens 2 デバイスにアプリケーションをシームレスにインストールできる新しい機能 (アプリ インストーラー **)** が追加されました。</span><span class="sxs-lookup"><span data-stu-id="349d8-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="349d8-108">この機能は、非 **管理対象デバイスに対して既定で有効になります**。</span><span class="sxs-lookup"><span data-stu-id="349d8-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="349d8-109">企業の中断を防ぐため、現時点では管理対象デバイスでアプリ **インストーラーを** 利用できません。</span><span class="sxs-lookup"><span data-stu-id="349d8-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="349d8-110">次の条件に当てはまる場合、デバイス\*\*\*\* は "管理対象" と見なされます。</span><span class="sxs-lookup"><span data-stu-id="349d8-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="349d8-111">MDM [の登録](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="349d8-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="349d8-112">プロビジョニング パッケージ [で構成](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="349d8-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="349d8-113">ユーザー [ID は](hololens-identity.md) Azure AD</span><span class="sxs-lookup"><span data-stu-id="349d8-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="349d8-114">開発者モードを有効にしたり、Device Portal を使用したりすることなく、アプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="349d8-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="349d8-115">(USB 経由または Microsoft Edge 経由で) Appx バンドルをデバイスにダウンロードし、エクスプローラーで Appx バンドルに移動して、インストールを開始するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="349d8-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="349d8-116">または、Web [ページからインストールを開始します](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。</span><span class="sxs-lookup"><span data-stu-id="349d8-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="349d8-117">Microsoft Store からインストールしたアプリや MDM の LOB アプリ展開機能を使ってサイドロードするアプリと同様に、[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)アプリは署名ツール[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)でデジタル署名する必要があります。また、アプリを展開する前に、署名に使用する証明書が HoloLens デバイスによって信頼されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="349d8-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <span data-ttu-id="349d8-118">要件</span><span class="sxs-lookup"><span data-stu-id="349d8-118">Requirements</span></span>

### <span data-ttu-id="349d8-119">デバイスの場合:</span><span class="sxs-lookup"><span data-stu-id="349d8-119">For your devices:</span></span>

<span data-ttu-id="349d8-120">この機能は現在、HoloLens 2 デバイス用の Windows Holographic 20H2 ビルドで利用できます。</span><span class="sxs-lookup"><span data-stu-id="349d8-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="349d8-121">この方法を使用しているすべてのデバイスが[更新されます。](hololens-update-hololens.md)</span><span class="sxs-lookup"><span data-stu-id="349d8-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <span data-ttu-id="349d8-122">アプリの場合:</span><span class="sxs-lookup"><span data-stu-id="349d8-122">For your apps:</span></span>

<span data-ttu-id="349d8-123">アプリ インストーラーはストアからの依存関係を使\*\*\*\* うの\*\*\*\* で、アプリのソリューション構成はマスターまたはリリースである必要があります。</span><span class="sxs-lookup"><span data-stu-id="349d8-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="349d8-124">アプリ パッケージの作成 [について詳しくは、以下をご覧ください](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)。</span><span class="sxs-lookup"><span data-stu-id="349d8-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="349d8-125">この方法でインストールされるアプリは、デジタル署名されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="349d8-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="349d8-126">アプリに署名するには、証明書を使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="349d8-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="349d8-127">MS Trusted [CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)から証明書を取得できます。その場合は、追加の操作を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="349d8-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="349d8-128">または、独自の証明書に署名することもできますが、証明書をデバイスにプッシュする必要があります。</span><span class="sxs-lookup"><span data-stu-id="349d8-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="349d8-129">署名ツールを使って [アプリに署名する方法。](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="349d8-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="349d8-130">証明書オプション:</span><span class="sxs-lookup"><span data-stu-id="349d8-130">Certificate options:</span></span>**

- [<span data-ttu-id="349d8-131">MS Trusted CA List</span><span class="sxs-lookup"><span data-stu-id="349d8-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="349d8-132">証明書の展開方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="349d8-132">Pick a certificate deployment method.</span></span>**

- <span data-ttu-id="349d8-133">[プロビジョニング パッケージは](hololens-provisioning.md) 、ローカル デバイスに適用できます。</span><span class="sxs-lookup"><span data-stu-id="349d8-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="349d8-134">MDM を使って、デバイス [構成で証明書を適用できます](https://docs.microsoft.com/mem/intune/protect/certificates-configure)。</span><span class="sxs-lookup"><span data-stu-id="349d8-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="349d8-135">デバイス証明書マネージャーを [使用します](certificate-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="349d8-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <span data-ttu-id="349d8-136">インストール方法</span><span class="sxs-lookup"><span data-stu-id="349d8-136">Installation method</span></span>

1. <span data-ttu-id="349d8-137">デバイスが管理対象と見なされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="349d8-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="349d8-138">HoloLens 2 デバイスの電源がオンで、サインイン中です。</span><span class="sxs-lookup"><span data-stu-id="349d8-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="349d8-139">PC でカスタム アプリに移動し、app.appxbundle をdevicename\Internal Storage\Downloads にコピーします。</span><span class="sxs-lookup"><span data-stu-id="349d8-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="349d8-140">ファイルのコピーが完了したら、デバイスを切断して後でインストールを完了できます。</span><span class="sxs-lookup"><span data-stu-id="349d8-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="349d8-141">HoloLens 2 デバイスから [スタート]\*\*\*\* メニューを**開**き、[すべてのアプリ] を選択し、エクスプローラー アプリ**を起動**します。</span><span class="sxs-lookup"><span data-stu-id="349d8-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="349d8-142">[ダウンロード] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="349d8-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="349d8-143">アプリの左側のパネルで、最初に [この\*\*\*\* デバイス] を選択し、[ダウンロード] に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="349d8-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="349d8-144">yourapp.appxbundle ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="349d8-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="349d8-145">アプリ インストーラーが起動します。</span><span class="sxs-lookup"><span data-stu-id="349d8-145">The App Installer will launch.</span></span> <span data-ttu-id="349d8-146">[インストール **] ボタン** を選択してアプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="349d8-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="349d8-147">インストールが完了すると、インストールされたアプリが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="349d8-147">The installed app will automatically launch upon the completion of installing.</span></span>

![アプリ インストーラーによる MRTK の例のインストール](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="349d8-149">インストールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="349d8-149">Troubleshooting Installs</span></span>

<span data-ttu-id="349d8-150">アプリのインストールに失敗した場合は、以下を確認してトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="349d8-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="349d8-151">アプリは、マスター ビルドまたはリリース ビルドのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="349d8-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="349d8-152">デバイスは、この機能が利用可能なビルドに更新されます。</span><span class="sxs-lookup"><span data-stu-id="349d8-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="349d8-153">インターネット [に接続されています](hololens-network.md)。</span><span class="sxs-lookup"><span data-stu-id="349d8-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="349d8-154">[Microsoft Store のエンドポイントが正しく](hololens-offline.md)構成されている。</span><span class="sxs-lookup"><span data-stu-id="349d8-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="349d8-155">Web インストーラー</span><span class="sxs-lookup"><span data-stu-id="349d8-155">Web Installer</span></span>

<span data-ttu-id="349d8-156">ユーザーは、Web サーバーから直接アプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="349d8-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="349d8-157">このフローでは、アプリ インストーラーと簡単なダウンロードとインストールの配布方法を組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="349d8-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <span data-ttu-id="349d8-158">Web インストールをセットアップする方法:</span><span class="sxs-lookup"><span data-stu-id="349d8-158">How to set up web install:</span></span>

1. <span data-ttu-id="349d8-159">アプリがインストールするように正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="349d8-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="349d8-160">Web ページから [インストールを有効にするには、次の手順を実行します](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。</span><span class="sxs-lookup"><span data-stu-id="349d8-160">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <span data-ttu-id="349d8-161">エンド ユーザー エクスペリエンス:</span><span class="sxs-lookup"><span data-stu-id="349d8-161">End user experience:</span></span>

1. <span data-ttu-id="349d8-162">ユーザーは、上記で選択した方法を使用して、デバイスに証明書を受信してインストールします。</span><span class="sxs-lookup"><span data-stu-id="349d8-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="349d8-163">ユーザーは、上記の手順で作成した URL にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="349d8-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="349d8-164">アプリがデバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="349d8-164">The app will now install to the device.</span></span> <span data-ttu-id="349d8-165">アプリを見つけるには、スタート メニュー**を開**き\*\*\*\*、[すべてのアプリ] ボタンを選択してアプリを探します。</span><span class="sxs-lookup"><span data-stu-id="349d8-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="349d8-166">アプリ インストーラーのインストール方法のトラブルシューティングについて詳しくは、アプリ インストーラーの問題 [のトラブルシューティングに関するページをご覧ください](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)。</span><span class="sxs-lookup"><span data-stu-id="349d8-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="349d8-167">更新プロセス中の UI はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="349d8-167">UI during the update process is not supported.</span></span> <span data-ttu-id="349d8-168">したがって、このページの ShowPrompt [オプションと](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 関連オプションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="349d8-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="349d8-169">サンプル アプリ</span><span class="sxs-lookup"><span data-stu-id="349d8-169">Sample Apps</span></span>

<span data-ttu-id="349d8-170">いくつかのサンプル アプリでアプリ インストーラーを試す場合は、利用可能なサンプルを確認してください。</span><span class="sxs-lookup"><span data-stu-id="349d8-170">To try the App Installer with some sample apps check out some of our available samples:</span></span>

- [<span data-ttu-id="349d8-171">MRTK の例ハブ</span><span class="sxs-lookup"><span data-stu-id="349d8-171">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="349d8-172">サーフェス</span><span class="sxs-lookup"><span data-stu-id="349d8-172">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="349d8-173">テストに使用できる UWP サンプル アプリ</span><span class="sxs-lookup"><span data-stu-id="349d8-173">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
