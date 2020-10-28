---
title: HoloLens 2 アプリインストーラーを使用してアプリをサイドロードおよびインストールする方法
description: UI を使用したスライドの読み込みとアプリのインストール
keywords: アプリ管理、アプリ、hololens、アプリインストーラー
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 10/26/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 4e2256f1086c92cdf0e788ba9dddf5b74a733116
ms.sourcegitcommit: 72ae5a270f869393872eac160e43076eaa35fe4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135528"
---
# <span data-ttu-id="85d9d-104">アプリインストーラーを使用して HoloLens 2 にアプリをインストールする</span><span class="sxs-lookup"><span data-stu-id="85d9d-104">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="85d9d-105">Windows Insider のリリースでは、新しい機能 (アプリのインストーラー) を追加して、HoloLens 2 デバイスに **よりシームレスにアプリケーションをインストールできるように** しています。</span><span class="sxs-lookup"><span data-stu-id="85d9d-105">In our Windows Insider release, we are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span>  <span data-ttu-id="85d9d-106">開発者モードを有効にしたり、Device Portal を使用したりしなくても、アプリをインストールできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="85d9d-106">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="85d9d-107">Appx バンドルをデバイスにダウンロード (USB 経由またはエッジ経由) するだけで、インストールを開始するように促すメッセージが表示されるように、ファイルエクスプローラーで Appx バンドルに移動できます。</span><span class="sxs-lookup"><span data-stu-id="85d9d-107">Simply download (over USB or through Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="85d9d-108">または、 [web ページからインストールを開始](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)します。</span><span class="sxs-lookup"><span data-stu-id="85d9d-108">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="85d9d-109">Microsoft Store またはサイドローディングで MDM の LOB アプリの展開機能を使用してインストールしたアプリと同様に、アプリを展開するには、アプリを展開する前に、アプリをインストールする前に、 [サインインツール](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) を使ってデジタル署名する必要があります。また、署名に使用する証明書は、HoloLens デバイスで [信頼される必要があり](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) ます</span><span class="sxs-lookup"><span data-stu-id="85d9d-109">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>   

<span data-ttu-id="85d9d-110">この更新プログラム[は、既定でサイドローディングが有効になっ](https://blogs.windows.com/windows-insider/2019/08/07/announcing-windows-10-insider-preview-build-18956/)ているデスクトップと連携します</span><span class="sxs-lookup"><span data-stu-id="85d9d-110">This update aligns with desktop where [Sideloading is Enabled by Default](https://blogs.windows.com/windows-insider/2019/08/07/announcing-windows-10-insider-preview-build-18956/)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85d9d-111">この機能は、現時点では、Windows Insider ビルド 19041.1377 + でのみ avalible になっています。</span><span class="sxs-lookup"><span data-stu-id="85d9d-111">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="85d9d-112">[詳細については、「Windows Insider ビルドに登録する」を参照して](hololens-insider.md)ください。</span><span class="sxs-lookup"><span data-stu-id="85d9d-112">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

> [!NOTE]
> <span data-ttu-id="85d9d-113">この機能を無効にする IT 管理者は、次のパッケージファミリ名を、 [WDAC ポリシー](windows-defender-application-control-wdac.md)の一部として使用してください。</span><span class="sxs-lookup"><span data-stu-id="85d9d-113">For IT Admins who wish to disable this feature please use the following package family name as part of your [WDAC policy](windows-defender-application-control-wdac.md).</span></span> <span data-ttu-id="85d9d-114">これにより、アプリのインストーラーアプリがブロックされるだけで、Microsoft ストアや MDM ソリューションなどの他のソースからアプリをインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="85d9d-114">This will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>
```
Microsoft.DesktopAppInstaller_8wekyb3d8bbwe
```
> [!NOTE]
> <span data-ttu-id="85d9d-115">アプリの制御には、 [WDAC ポリシー](windows-defender-application-control-wdac.md) を使用することをお勧めします。ただし、microsoft store アプリを許可するのは、 [Applicationmanagement/allowalltrustedapps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) ポリシーを明示的に設定したデバイスのみが、microsoft store からアプリをインストールすることを許可します。</span><span class="sxs-lookup"><span data-stu-id="85d9d-115">It is recommended to use [WDAC policy](windows-defender-application-control-wdac.md) to control apps, however if you only want to allow Microsoft Store apps, devices configured to set the [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) policy explicitly to “not allow” will only allow apps to be installed from the Microsoft Store.</span></span> 

## <span data-ttu-id="85d9d-116">要件</span><span class="sxs-lookup"><span data-stu-id="85d9d-116">Requirements</span></span>

### <span data-ttu-id="85d9d-117">デバイスの場合:</span><span class="sxs-lookup"><span data-stu-id="85d9d-117">For your devices:</span></span> 
> [!NOTE]
> <span data-ttu-id="85d9d-118">この機能は、現時点では、Windows Insider ビルド 19041.1377 + でのみ avalible になっています。</span><span class="sxs-lookup"><span data-stu-id="85d9d-118">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="85d9d-119">[詳細については、「Windows Insider ビルドに登録する」を参照して](hololens-insider.md)ください。</span><span class="sxs-lookup"><span data-stu-id="85d9d-119">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

### <span data-ttu-id="85d9d-120">アプリの場合:</span><span class="sxs-lookup"><span data-stu-id="85d9d-120">For your apps:</span></span> 
<span data-ttu-id="85d9d-121">アプリのインストーラーでストアからの依存関係が使用されるため、アプリのソリューション構成は **Master** または **Release** のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="85d9d-121">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="85d9d-122">詳細については、「 [アプリパッケージの作成](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85d9d-122">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="85d9d-123">このメソッドを使ってインストールされたアプリは、デジタル署名されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="85d9d-123">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="85d9d-124">アプリに署名するには、証明書を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85d9d-124">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="85d9d-125">[ [MS TRUSTED CA] リスト](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)から証明書を取得することができます。その場合は、追加の操作を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="85d9d-125">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any additional action.</span></span> <span data-ttu-id="85d9d-126">または、独自の証明書に署名することもできます。ただし、証明書はデバイスにプッシュする必要があります。</span><span class="sxs-lookup"><span data-stu-id="85d9d-126">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span> 
- <span data-ttu-id="85d9d-127">[Sign Tool を使って](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)アプリに署名する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="85d9d-127">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="85d9d-128">証明書オプション:</span><span class="sxs-lookup"><span data-stu-id="85d9d-128">Certificate options:</span></span>** 
- [<span data-ttu-id="85d9d-129">MS Trusted CA リスト</span><span class="sxs-lookup"><span data-stu-id="85d9d-129">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="85d9d-130">証明書の展開方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="85d9d-130">Pick a certificate deployment method.</span></span>** 
- <span data-ttu-id="85d9d-131">[プロビジョニングパッケージ](hololens-provisioning.md) はローカルデバイスに適用できます。</span><span class="sxs-lookup"><span data-stu-id="85d9d-131">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="85d9d-132">MDM を使って、 [デバイスの構成に証明書を適用](https://docs.microsoft.com/mem/intune/protect/certificates-configure)することができます。</span><span class="sxs-lookup"><span data-stu-id="85d9d-132">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="85d9d-133">デバイス [証明書マネージャー](hololens-insider.md#certificate-manager)を使用します。</span><span class="sxs-lookup"><span data-stu-id="85d9d-133">Use the on device [Certificate Manager](hololens-insider.md#certificate-manager).</span></span> 

## <span data-ttu-id="85d9d-134">インストール方法</span><span class="sxs-lookup"><span data-stu-id="85d9d-134">Installation method</span></span>

1.  <span data-ttu-id="85d9d-135">HoloLens 2 デバイスの電源が入っていて、サインインしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="85d9d-135">Ensure that your HoloLens 2 device is powered on and you are signed in.</span></span>
1.  <span data-ttu-id="85d9d-136">PC でカスタムアプリに移動し、yourapp を yourdevicename\Internal Storage\Downloads. にコピーします。</span><span class="sxs-lookup"><span data-stu-id="85d9d-136">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span> 
    <span data-ttu-id="85d9d-137">ファイルのコピーが完了したら、デバイスを切断して、後でインストールを完了することができます。</span><span class="sxs-lookup"><span data-stu-id="85d9d-137">After your finish copying your file you may disconnect your device and finish the install later.</span></span>
1.  <span data-ttu-id="85d9d-138">HoloLens 2 デバイスから [ **スタート] メニュー**を開き、[ **すべてのアプリ** ] を選択して、 **エクスプローラー** アプリを起動します。</span><span class="sxs-lookup"><span data-stu-id="85d9d-138">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1.  <span data-ttu-id="85d9d-139">[ダウンロード] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="85d9d-139">Navigate to the Downloads folder.</span></span> <span data-ttu-id="85d9d-140">アプリの左側のパネルで、[ **このデバイス** ] を選択してから、[ダウンロード] に移動することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="85d9d-140">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="85d9d-141">Yourapp ファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="85d9d-141">Select the yourapp.appxbundle file.</span></span> 
1.  <span data-ttu-id="85d9d-142">アプリのインストーラーが起動します。</span><span class="sxs-lookup"><span data-stu-id="85d9d-142">The App Installer will launch.</span></span> <span data-ttu-id="85d9d-143">アプリをインストールするには、[ **インストール** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="85d9d-143">Select the **Install** button to install your app.</span></span> 

<span data-ttu-id="85d9d-144">インストールされたアプリは、インストールの完了時に自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="85d9d-144">The installed app will automatically launch upon the completion of installing.</span></span> 

![App Installer による MRTK の例のインストール](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="85d9d-146">インストールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="85d9d-146">Troubleshooting Installs</span></span>
<span data-ttu-id="85d9d-147">アプリのインストールに失敗した場合は、次のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="85d9d-147">If your app failed to install check the following:</span></span>
-   <span data-ttu-id="85d9d-148">アプリがマスターまたはリリースビルドのどちらかです。</span><span class="sxs-lookup"><span data-stu-id="85d9d-148">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="85d9d-149">使用しているデバイスが、この機能を利用できるビルドに更新されます。</span><span class="sxs-lookup"><span data-stu-id="85d9d-149">Your device is updated to a build on which this feature is available.</span></span> 
-   <span data-ttu-id="85d9d-150">[インターネットに接続](hololens-network.md)されています。</span><span class="sxs-lookup"><span data-stu-id="85d9d-150">You are [connected to the internet](hololens-network.md).</span></span>
-   <span data-ttu-id="85d9d-151">[Microsoft Store のエンドポイント](hololens-offline.md)が適切に構成されている。</span><span class="sxs-lookup"><span data-stu-id="85d9d-151">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="85d9d-152">Web インストーラ</span><span class="sxs-lookup"><span data-stu-id="85d9d-152">Web Installer</span></span>

<span data-ttu-id="85d9d-153">ユーザーは、web サーバーから直接アプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="85d9d-153">Users can install an app directly from a web server.</span></span> <span data-ttu-id="85d9d-154">これにより、アプリのインストーラーが、簡単なダウンロードとインストールの配布方法と組み合わされて使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="85d9d-154">This takes use of the App Installer combined with an easy download and install distribution method.</span></span> 

### <span data-ttu-id="85d9d-155">Web インストールのセットアップ方法:</span><span class="sxs-lookup"><span data-stu-id="85d9d-155">How to set up web install:</span></span>
1.  <span data-ttu-id="85d9d-156">アプリが正しくインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="85d9d-156">Ensure your app is correctly configured to install.</span></span>
1.  <span data-ttu-id="85d9d-157">[Web ページでこの機能を有効にするには、次の手順を](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)実行します。</span><span class="sxs-lookup"><span data-stu-id="85d9d-157">Follow these [steps to enable this on a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span> 

### <span data-ttu-id="85d9d-158">エンドユーザーエクスペリエンス:</span><span class="sxs-lookup"><span data-stu-id="85d9d-158">End user experience:</span></span>
1. <span data-ttu-id="85d9d-159">ユーザーは、前に選択した方法を使用して、デバイスに証明書を受け取り、インストールします。</span><span class="sxs-lookup"><span data-stu-id="85d9d-159">User receives and installs certificate to the device using a method previously chosen above.</span></span> 
1. <span data-ttu-id="85d9d-160">ユーザーは、上の手順で作成した URL にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="85d9d-160">User visits the URL created from the step above.</span></span>

<span data-ttu-id="85d9d-161">これで、アプリがデバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="85d9d-161">The app will now install to the device.</span></span> <span data-ttu-id="85d9d-162">アプリを見つけるには、[ **スタート] メニュー** を開き、[ **すべてのアプリ** ] ボタンを選んでアプリを見つけます。</span><span class="sxs-lookup"><span data-stu-id="85d9d-162">To find the app open the **Start menu** and select the **All apps** button to find your app.</span></span> 

-   <span data-ttu-id="85d9d-163">このインストール方法のトラブルシューティングについては、「 [アプリインストーラーの問題のトラブルシューティング](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85d9d-163">For help troubleshooting this installation method please visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span> 

> [!NOTE]
> <span data-ttu-id="85d9d-164">更新プロセス中の UI はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="85d9d-164">UI during the update process is not supported.</span></span> <span data-ttu-id="85d9d-165">そのため、 [このページ](https://docs.microsoft.com/windows/msix/app-installer/update-settings) と関連オプションの showprompt オプションはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="85d9d-165">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="85d9d-166">サンプルアプリ</span><span class="sxs-lookup"><span data-stu-id="85d9d-166">Sample Apps</span></span>

<span data-ttu-id="85d9d-167">サンプルアプリを試してみたい場合は、利用可能なサンプルの一部を確認してください。</span><span class="sxs-lookup"><span data-stu-id="85d9d-167">If you'd like to try this out with some sample apps please check out some of our available samples:</span></span>
- [<span data-ttu-id="85d9d-168">MRTK の例の Hub</span><span class="sxs-lookup"><span data-stu-id="85d9d-168">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="85d9d-169">Hba</span><span class="sxs-lookup"><span data-stu-id="85d9d-169">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="85d9d-170">テストに使用できる UWP サンプルアプリ</span><span class="sxs-lookup"><span data-stu-id="85d9d-170">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
