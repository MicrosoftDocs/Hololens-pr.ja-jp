---
title: HoloLens 2 アプリ インストーラーを使ってアプリをサイド ロードしてインストールする方法
description: UI を使ったアプリのスライドの読み込みとインストール
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
ms.openlocfilehash: e52cc2f031c284b619c61ffa04f259f76397faf5
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253094"
---
# <span data-ttu-id="b66ee-104">アプリ インストーラーを使用して HoloLens 2 にアプリをインストールする</span><span class="sxs-lookup"><span data-stu-id="b66ee-104">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="b66ee-105">HoloLens 2 デバイスにアプリケーションをシームレスにインストールできる新しい機能 (アプリ インストーラー **)** が追加されています。</span><span class="sxs-lookup"><span data-stu-id="b66ee-105">We are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="b66ee-106">この機能は、非 **管理対象デバイスに対して既定で有効になります**。</span><span class="sxs-lookup"><span data-stu-id="b66ee-106">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="b66ee-107">企業の中断を防ぐため、現時点では管理対象デバイスでアプリ **インストーラーを** 利用できません。</span><span class="sxs-lookup"><span data-stu-id="b66ee-107">To prevent disruption to enterprises, app installer will **not be available for managed devices** at this time.</span></span>  

> [!NOTE]
> <span data-ttu-id="b66ee-108">この機能は [、Windows Holographic バージョン 20H2 から 2020 年 12 月の更新プログラムで利用できます](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="b66ee-108">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="b66ee-109">この機能を使用するために [デバイスが](hololens-update-hololens.md) 更新されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b66ee-109">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="b66ee-110">HoloLens 2 デバイスにアプリケーションをシームレスにインストールできる新しい機能 (アプリ インストーラー **)** が追加されました。</span><span class="sxs-lookup"><span data-stu-id="b66ee-110">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="b66ee-111">この機能は、非 **管理対象デバイスに対して既定で有効になります**。</span><span class="sxs-lookup"><span data-stu-id="b66ee-111">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="b66ee-112">企業の中断を防ぐため、現時点では管理対象デバイスでアプリ **インストーラーを** 利用できません。</span><span class="sxs-lookup"><span data-stu-id="b66ee-112">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="b66ee-113">次の条件に当てはまる場合、デバイス\*\*\*\* は "管理対象" と見なされます。</span><span class="sxs-lookup"><span data-stu-id="b66ee-113">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="b66ee-114">MDM [の登録](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="b66ee-114">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="b66ee-115">プロビジョニング パッケージ [で構成](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="b66ee-115">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="b66ee-116">ユーザー [ID は](hololens-identity.md) Azure AD</span><span class="sxs-lookup"><span data-stu-id="b66ee-116">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="b66ee-117">開発者モードを有効にしたり、Device Portal を使用したりすることなく、アプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="b66ee-117">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="b66ee-118">(USB 経由または Microsoft Edge 経由で) Appx バンドルをデバイスにダウンロードし、エクスプローラーで Appx バンドルに移動して、インストールを開始するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b66ee-118">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="b66ee-119">または、Web [ページからインストールを開始します](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。</span><span class="sxs-lookup"><span data-stu-id="b66ee-119">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="b66ee-120">Microsoft Store からインストールするアプリや MDM の LOB アプリ展開機能を使ってサイドロードする場合と同様に、[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)アプリは署名ツール[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)でデジタル署名する必要があります。また、アプリを展開する前に、署名に使用する証明書が HoloLens デバイスによって信頼されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b66ee-120">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <span data-ttu-id="b66ee-121">要件</span><span class="sxs-lookup"><span data-stu-id="b66ee-121">Requirements</span></span>

### <span data-ttu-id="b66ee-122">デバイスの場合:</span><span class="sxs-lookup"><span data-stu-id="b66ee-122">For your devices:</span></span>

 <span data-ttu-id="b66ee-123">この機能は現在、HoloLens 2 デバイス用の Windows Holographic 20H2 ビルドで利用できます。</span><span class="sxs-lookup"><span data-stu-id="b66ee-123">feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="b66ee-124">この方法を使用しているすべてのデバイス [が更新されます](hololens-update-hololens.md)。</span><span class="sxs-lookup"><span data-stu-id="b66ee-124">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <span data-ttu-id="b66ee-125">アプリの場合:</span><span class="sxs-lookup"><span data-stu-id="b66ee-125">For your apps:</span></span> 
<span data-ttu-id="b66ee-126">アプリ インストーラーはストアからの依存関係を使\*\*\*\* うの\*\*\*\* で、アプリのソリューション構成はマスターまたはリリースである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b66ee-126">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="b66ee-127">アプリ パッケージの作成 [について詳しくは、以下をご覧ください](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)。</span><span class="sxs-lookup"><span data-stu-id="b66ee-127">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="b66ee-128">この方法でインストールされるアプリは、デジタル署名されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b66ee-128">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="b66ee-129">アプリに署名するには、証明書を使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b66ee-129">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="b66ee-130">MS Trusted [CA リスト](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)から証明書を取得できます。その場合、追加の操作を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b66ee-130">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any additional action.</span></span> <span data-ttu-id="b66ee-131">または、独自の証明書に署名することもできますが、証明書をデバイスにプッシュする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b66ee-131">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="b66ee-132">署名ツールを使って [アプリに署名する方法。](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="b66ee-132">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="b66ee-133">証明書オプション:</span><span class="sxs-lookup"><span data-stu-id="b66ee-133">Certificate options:</span></span>**

- [<span data-ttu-id="b66ee-134">MS Trusted CA List</span><span class="sxs-lookup"><span data-stu-id="b66ee-134">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="b66ee-135">証明書の展開方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="b66ee-135">Pick a certificate deployment method.</span></span>**

- <span data-ttu-id="b66ee-136">[プロビジョニング パッケージは](hololens-provisioning.md) 、ローカル デバイスに適用できます。</span><span class="sxs-lookup"><span data-stu-id="b66ee-136">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="b66ee-137">MDM を使って、デバイス [構成で証明書を適用できます](https://docs.microsoft.com/mem/intune/protect/certificates-configure)。</span><span class="sxs-lookup"><span data-stu-id="b66ee-137">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="b66ee-138">デバイス証明書マネージャーを [使用します](certificate-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="b66ee-138">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <span data-ttu-id="b66ee-139">インストール方法</span><span class="sxs-lookup"><span data-stu-id="b66ee-139">Installation method</span></span>

1. <span data-ttu-id="b66ee-140">デバイスが管理対象と見なされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b66ee-140">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="b66ee-141">HoloLens 2 デバイスの電源がオンで、サインイン中です。</span><span class="sxs-lookup"><span data-stu-id="b66ee-141">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="b66ee-142">PC でカスタム アプリに移動し、app.appxbundle をdevicename\Internal Storage\Downloads にコピーします。</span><span class="sxs-lookup"><span data-stu-id="b66ee-142">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="b66ee-143">ファイルのコピーが完了したら、デバイスを切断して後でインストールを完了できます。</span><span class="sxs-lookup"><span data-stu-id="b66ee-143">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="b66ee-144">HoloLens 2 デバイスから [スタート]\*\*\*\* メニューを**開**き、[すべてのアプリ] を選択し、エクスプローラー アプリ**を起動**します。</span><span class="sxs-lookup"><span data-stu-id="b66ee-144">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="b66ee-145">[ダウンロード] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="b66ee-145">Navigate to the Downloads folder.</span></span> <span data-ttu-id="b66ee-146">アプリの左側のパネルで、最初に [この\*\*\*\* デバイス] を選択し、[ダウンロード] に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b66ee-146">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="b66ee-147">yourapp.appxbundle ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="b66ee-147">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="b66ee-148">アプリ インストーラーが起動します。</span><span class="sxs-lookup"><span data-stu-id="b66ee-148">The App Installer will launch.</span></span> <span data-ttu-id="b66ee-149">[インストール **] ボタン** を選択してアプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b66ee-149">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="b66ee-150">インストールが完了すると、インストールされたアプリが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="b66ee-150">The installed app will automatically launch upon the completion of installing.</span></span>

![アプリ インストーラーによる MRTK の例のインストール](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="b66ee-152">インストールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b66ee-152">Troubleshooting Installs</span></span>

<span data-ttu-id="b66ee-153">アプリのインストールに失敗した場合は、次を確認してトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="b66ee-153">If your app failed to install check the following to troubleshoot:</span></span>

- <span data-ttu-id="b66ee-154">アプリは、マスター ビルドまたはリリース ビルドのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="b66ee-154">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="b66ee-155">デバイスは、この機能が利用可能なビルドに更新されます。</span><span class="sxs-lookup"><span data-stu-id="b66ee-155">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="b66ee-156">インターネット [に接続しています](hololens-network.md)。</span><span class="sxs-lookup"><span data-stu-id="b66ee-156">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="b66ee-157">[Microsoft Store のエンドポイントが正しく](hololens-offline.md)構成されている。</span><span class="sxs-lookup"><span data-stu-id="b66ee-157">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="b66ee-158">Web インストーラー</span><span class="sxs-lookup"><span data-stu-id="b66ee-158">Web Installer</span></span>

<span data-ttu-id="b66ee-159">ユーザーは、Web サーバーから直接アプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="b66ee-159">Users can install an app directly from a web server.</span></span> <span data-ttu-id="b66ee-160">このフローでは、アプリ インストーラーと簡単なダウンロードとインストールの配布方法を組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="b66ee-160">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <span data-ttu-id="b66ee-161">Web インストールを設定する方法:</span><span class="sxs-lookup"><span data-stu-id="b66ee-161">How to set up web install:</span></span>

1. <span data-ttu-id="b66ee-162">アプリがインストールするように正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b66ee-162">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="b66ee-163">Web ページから [インストールを有効にするには、次の手順を実行します](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。</span><span class="sxs-lookup"><span data-stu-id="b66ee-163">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <span data-ttu-id="b66ee-164">エンド ユーザー エクスペリエンス:</span><span class="sxs-lookup"><span data-stu-id="b66ee-164">End user experience:</span></span>

1. <span data-ttu-id="b66ee-165">ユーザーは、上記で選択した方法を使用して、デバイスに証明書を受信してインストールします。</span><span class="sxs-lookup"><span data-stu-id="b66ee-165">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="b66ee-166">ユーザーは、上記の手順で作成した URL にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="b66ee-166">User visits the URL created from the step above.</span></span>

<span data-ttu-id="b66ee-167">アプリがデバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b66ee-167">The app will now install to the device.</span></span> <span data-ttu-id="b66ee-168">アプリを見つけるには、スタート メニュー **を開** き、[すべてのアプリ] ボタン **を選択して** アプリを探します。</span><span class="sxs-lookup"><span data-stu-id="b66ee-168">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="b66ee-169">アプリ インストーラーのインストール方法のトラブルシューティングについて詳しくは、アプリ インストーラーの問題 [のトラブルシューティングに関するページをご覧ください](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)。</span><span class="sxs-lookup"><span data-stu-id="b66ee-169">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="b66ee-170">更新プロセス中の UI はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b66ee-170">UI during the update process is not supported.</span></span> <span data-ttu-id="b66ee-171">したがって、このページの ShowPrompt [オプションと](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 関連オプションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b66ee-171">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="b66ee-172">サンプル アプリ</span><span class="sxs-lookup"><span data-stu-id="b66ee-172">Sample Apps</span></span>

<span data-ttu-id="b66ee-173">いくつかのサンプル アプリでアプリ インストーラーを試す場合は、利用可能なサンプルを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b66ee-173">To try the App Installer with some sample apps check out some of our available samples:</span></span>

- [<span data-ttu-id="b66ee-174">MRTK の例ハブ</span><span class="sxs-lookup"><span data-stu-id="b66ee-174">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="b66ee-175">サーフェス</span><span class="sxs-lookup"><span data-stu-id="b66ee-175">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="b66ee-176">テストに使用できる UWP サンプル アプリ</span><span class="sxs-lookup"><span data-stu-id="b66ee-176">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
