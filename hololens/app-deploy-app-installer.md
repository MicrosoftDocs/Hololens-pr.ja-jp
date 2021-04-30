---
title: HoloLens 2 アプリインストーラーを使用してアプリをサイドロードしてインストールする方法
description: アプリのインストーラーを使用してアプリをインストールおよびトラブルシューティングする方法と、UI を使用してアプリをサイドロードしてインストールする方法について説明します。
keywords: アプリ管理, アプリ, hololens, アプリインストーラー
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309273"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="84ac6-104">アプリインストーラーを使用して HoloLens 2 にアプリをインストールする</span><span class="sxs-lookup"><span data-stu-id="84ac6-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="84ac6-105">この機能は [、Windows Holographic、バージョン20H2 –2020年12月の更新プログラム](hololens-release-notes.md)で利用可能になりました。</span><span class="sxs-lookup"><span data-stu-id="84ac6-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="84ac6-106">この機能を使用するようにデバイスが [更新](hololens-update-hololens.md) されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="84ac6-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="84ac6-107">HoloLens 2 デバイスに **アプリケーションをシームレスにインストールできる新しい機能 (アプリインストーラー) が追加され** ました。</span><span class="sxs-lookup"><span data-stu-id="84ac6-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="84ac6-108">この機能は、管理されていない **デバイスに対しては既定でオンに** なります。</span><span class="sxs-lookup"><span data-stu-id="84ac6-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="84ac6-109">企業が中断されないように、現時点では、 **管理対象デバイス** でアプリインストーラーを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="84ac6-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="84ac6-110">次の **いずれか** に該当する場合、デバイスは "管理されている" と見なされます。</span><span class="sxs-lookup"><span data-stu-id="84ac6-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="84ac6-111">MDM[登録](hololens-enroll-mdm.md)済み</span><span class="sxs-lookup"><span data-stu-id="84ac6-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="84ac6-112">[プロビジョニングパッケージ](hololens-provisioning.md)で構成済み</span><span class="sxs-lookup"><span data-stu-id="84ac6-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="84ac6-113">ユーザー [id](hololens-identity.md) が Azure AD</span><span class="sxs-lookup"><span data-stu-id="84ac6-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="84ac6-114">開発者モードを有効にしたり、デバイスポータルを使用したりすることなく、アプリをインストールできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="84ac6-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="84ac6-115">Appx バンドルをデバイスに (USB 経由または Microsoft Edge 経由で) ダウンロードし、エクスプローラーで Appx バンドルに移動して、インストールを開始するように求められるようにします。</span><span class="sxs-lookup"><span data-stu-id="84ac6-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="84ac6-116">または、 [web ページからインストールを開始](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)します。</span><span class="sxs-lookup"><span data-stu-id="84ac6-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="84ac6-117">MDM の LOB アプリのデプロイ機能を使用して Microsoft Store またはサイドロードからインストールするアプリと同様に、アプリは [署名ツール](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) でデジタル署名する必要があり、 [署名に使用する証明書](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) は、アプリを展開する前に HoloLens デバイスによって信頼されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="84ac6-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <a name="requirements"></a><span data-ttu-id="84ac6-118">要件</span><span class="sxs-lookup"><span data-stu-id="84ac6-118">Requirements</span></span>

### <a name="for-your-devices"></a><span data-ttu-id="84ac6-119">デバイスの場合:</span><span class="sxs-lookup"><span data-stu-id="84ac6-119">For your devices:</span></span>

<span data-ttu-id="84ac6-120">この機能は現在、HoloLens 2 デバイス用の Windows Holographic 20H2 ビルドで使用できます。</span><span class="sxs-lookup"><span data-stu-id="84ac6-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="84ac6-121">この方法を使用しているデバイスがすべて [更新](hololens-update-hololens.md)されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="84ac6-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <a name="for-your-apps"></a><span data-ttu-id="84ac6-122">アプリの場合:</span><span class="sxs-lookup"><span data-stu-id="84ac6-122">For your apps:</span></span>

<span data-ttu-id="84ac6-123">アプリのインストーラーがストアからの依存関係を使用するため、アプリのソリューション構成は **マスター** または **リリース** のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="84ac6-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="84ac6-124">詳細については、「 [アプリパッケージの作成](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84ac6-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="84ac6-125">この方法でインストールされるアプリには、デジタル署名が必要です。</span><span class="sxs-lookup"><span data-stu-id="84ac6-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="84ac6-126">アプリに署名するには、証明書を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84ac6-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="84ac6-127">[MS 信頼さ](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)れた CA の一覧から証明書を取得することができます。この場合、特別な操作を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="84ac6-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="84ac6-128">または、証明書をデバイスにプッシュする必要がありますが、独自の証明書に署名することもできます。</span><span class="sxs-lookup"><span data-stu-id="84ac6-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="84ac6-129">[署名ツールを使用して](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)アプリに署名する方法。</span><span class="sxs-lookup"><span data-stu-id="84ac6-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

<span data-ttu-id="84ac6-130">**証明書のオプション:**</span><span class="sxs-lookup"><span data-stu-id="84ac6-130">**Certificate options:**</span></span>

- [<span data-ttu-id="84ac6-131">MS 信頼された CA の一覧</span><span class="sxs-lookup"><span data-stu-id="84ac6-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

<span data-ttu-id="84ac6-132">**証明書の展開方法を選択します。**</span><span class="sxs-lookup"><span data-stu-id="84ac6-132">**Pick a certificate deployment method.**</span></span>

- <span data-ttu-id="84ac6-133">[プロビジョニングパッケージ](hololens-provisioning.md) は、ローカルデバイスに適用できます。</span><span class="sxs-lookup"><span data-stu-id="84ac6-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="84ac6-134">MDM を使用し [て、デバイス構成を含む証明書を適用](https://docs.microsoft.com/mem/intune/protect/certificates-configure)できます。</span><span class="sxs-lookup"><span data-stu-id="84ac6-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="84ac6-135">デバイス [証明書マネージャー](certificate-manager.md)でを使用します。</span><span class="sxs-lookup"><span data-stu-id="84ac6-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <a name="installation-method"></a><span data-ttu-id="84ac6-136">インストール方法</span><span class="sxs-lookup"><span data-stu-id="84ac6-136">Installation method</span></span>

1. <span data-ttu-id="84ac6-137">デバイスが管理対象と見なされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="84ac6-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="84ac6-138">HoloLens 2 デバイスの電源が入っていて、サインインしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="84ac6-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="84ac6-139">お使いの PC でカスタムアプリに移動し、yourapp を yourdevicename\Internal Storage\Downloads. にコピーします。</span><span class="sxs-lookup"><span data-stu-id="84ac6-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="84ac6-140">ファイルのコピーが完了したら、デバイスを切断し、後でインストールを完了することができます。</span><span class="sxs-lookup"><span data-stu-id="84ac6-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="84ac6-141">HoloLens 2 デバイスから [ **スタート] メニュー** を開き、[ **すべてのアプリ** ] を選択して、 **エクスプローラー** アプリを起動します。</span><span class="sxs-lookup"><span data-stu-id="84ac6-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="84ac6-142">ダウンロードフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="84ac6-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="84ac6-143">アプリの左側のパネルで [ **このデバイス** を最初に選択する] をクリックし、[ダウンロード] に移動します。</span><span class="sxs-lookup"><span data-stu-id="84ac6-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="84ac6-144">Yourapp ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="84ac6-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="84ac6-145">アプリのインストーラーが起動します。</span><span class="sxs-lookup"><span data-stu-id="84ac6-145">The App Installer will launch.</span></span> <span data-ttu-id="84ac6-146">[ **インストール** ] ボタンを選択して、アプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="84ac6-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="84ac6-147">インストールの完了時に、インストールされているアプリが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="84ac6-147">The installed app will automatically launch upon the completion of installing.</span></span>

![アプリインストーラーを使用した MRTK の例のインストール](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a><span data-ttu-id="84ac6-149">インストールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="84ac6-149">Troubleshooting Installs</span></span>

<span data-ttu-id="84ac6-150">アプリをインストールできなかった場合は、次のことを確認してトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="84ac6-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="84ac6-151">アプリは、マスタービルドまたはリリースビルドのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="84ac6-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="84ac6-152">この機能が使用可能なビルドにデバイスが更新されます。</span><span class="sxs-lookup"><span data-stu-id="84ac6-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="84ac6-153">[インターネットに接続](hololens-network.md)されています。</span><span class="sxs-lookup"><span data-stu-id="84ac6-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="84ac6-154">[Microsoft Store のエンドポイント](hololens-offline.md)が正しく構成されています。</span><span class="sxs-lookup"><span data-stu-id="84ac6-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <a name="web-installer"></a><span data-ttu-id="84ac6-155">Web インストーラー</span><span class="sxs-lookup"><span data-stu-id="84ac6-155">Web Installer</span></span>

<span data-ttu-id="84ac6-156">ユーザーは、web サーバーから直接アプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="84ac6-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="84ac6-157">このフローでは、簡単なダウンロードとインストールの配布方法を組み合わせて、アプリインストーラーを使用します。</span><span class="sxs-lookup"><span data-stu-id="84ac6-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <a name="how-to-set-up-web-install"></a><span data-ttu-id="84ac6-158">Web インストールのセットアップ方法:</span><span class="sxs-lookup"><span data-stu-id="84ac6-158">How to set up web install:</span></span>

1. <span data-ttu-id="84ac6-159">アプリがインストールするように正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="84ac6-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="84ac6-160">[Web ページからのインストールを有効にするには、次の手順に](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)従います。</span><span class="sxs-lookup"><span data-stu-id="84ac6-160">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="84ac6-161">エンドユーザーエクスペリエンス:</span><span class="sxs-lookup"><span data-stu-id="84ac6-161">End user experience:</span></span>

1. <span data-ttu-id="84ac6-162">ユーザーは、前に選択した方法を使用して、デバイスに証明書を受信してインストールします。</span><span class="sxs-lookup"><span data-stu-id="84ac6-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="84ac6-163">ユーザーは、前の手順で作成した URL にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="84ac6-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="84ac6-164">これで、アプリがデバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="84ac6-164">The app will now install to the device.</span></span> <span data-ttu-id="84ac6-165">アプリを検索するには、[ **スタート] メニュー** を開き、[ **すべてのアプリ** ] ボタンをクリックしてアプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="84ac6-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="84ac6-166">アプリインストーラーのインストール方法のトラブルシューティングに関する詳細については、「 [アプリインストーラーの問題のトラブルシューティング](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84ac6-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="84ac6-167">更新プロセス中の UI はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="84ac6-167">UI during the update process is not supported.</span></span> <span data-ttu-id="84ac6-168">[このページ](https://docs.microsoft.com/windows/msix/app-installer/update-settings)の showprompt オプションと関連するオプションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="84ac6-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <a name="sample-apps"></a><span data-ttu-id="84ac6-169">サンプル アプリ</span><span class="sxs-lookup"><span data-stu-id="84ac6-169">Sample Apps</span></span>

<span data-ttu-id="84ac6-170">いくつかのサンプルアプリを使用してアプリインストーラーを試すには、使用可能なサンプルをいくつか確認してください。</span><span class="sxs-lookup"><span data-stu-id="84ac6-170">To try the App Installer with some sample apps check out some of our available samples:</span></span>

- [<span data-ttu-id="84ac6-171">MRTK Examples Hub</span><span class="sxs-lookup"><span data-stu-id="84ac6-171">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="84ac6-172">Surfaces</span><span class="sxs-lookup"><span data-stu-id="84ac6-172">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="84ac6-173">テストに使用できる UWP サンプルアプリ</span><span class="sxs-lookup"><span data-stu-id="84ac6-173">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
