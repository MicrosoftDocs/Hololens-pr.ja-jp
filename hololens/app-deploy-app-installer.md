---
title: HoloLens 2 アプリインストーラーを使用してアプリをサイドロードおよびインストールする方法
description: UI を使用したスライドの読み込みとアプリのインストール
keywords: アプリ管理、アプリ、hololens、アプリインストーラー
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
ms.openlocfilehash: 53937881d6569e6aaa17d7e60083381b13502b87
ms.sourcegitcommit: 74e9989240dc0c324df35e8651b2f307f9d42148
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2020
ms.locfileid: "11201371"
---
# <span data-ttu-id="b8070-104">アプリインストーラーを使用して HoloLens 2 にアプリをインストールする</span><span class="sxs-lookup"><span data-stu-id="b8070-104">Install Apps on HoloLens 2 via App Installer</span></span>


<span data-ttu-id="b8070-105">お客様が HoloLens 2 デバイスで **シームレスにアプリケーションをインストールできるように、新しい機能 (アプリのインストーラー) を追加** しています。</span><span class="sxs-lookup"><span data-stu-id="b8070-105">We are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="b8070-106">この機能は、 **非管理対象デバイスでは既定でオンに**なります。</span><span class="sxs-lookup"><span data-stu-id="b8070-106">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="b8070-107">この時点では、企業が中断されないように、アプリインストーラーを **管理対象デバイスで利用できなく** なります。</span><span class="sxs-lookup"><span data-stu-id="b8070-107">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

> [!NOTE]
> <span data-ttu-id="b8070-108">この機能は [、Windows ホログラフィック、バージョン20H2 –2020年12月更新プログラム](hololens-release-notes.md)で利用可能になりました。</span><span class="sxs-lookup"><span data-stu-id="b8070-108">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="b8070-109">この機能を使用するには、デバイスが [更新](hololens-update-hololens.md) されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b8070-109">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="b8070-110">**新しい機能 (アプリのインストーラー) が追加され、** HoloLens 2 デバイスでアプリケーションをよりシームレスにインストールできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b8070-110">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="b8070-111">この機能は、 **非管理対象デバイスでは既定でオンに**なります。</span><span class="sxs-lookup"><span data-stu-id="b8070-111">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="b8070-112">この時点では、企業が中断されないように、アプリインストーラーを **管理対象デバイスで利用できなく** なります。</span><span class="sxs-lookup"><span data-stu-id="b8070-112">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="b8070-113">以下の **いずれか** に該当する場合、デバイスは "管理されています" と見なされます。</span><span class="sxs-lookup"><span data-stu-id="b8070-113">A device is considered “managed” if **any** of the following are true:</span></span>
- <span data-ttu-id="b8070-114">MDM[登録](hololens-enroll-mdm.md)済み</span><span class="sxs-lookup"><span data-stu-id="b8070-114">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="b8070-115">[プロビジョニングパッケージ](hololens-provisioning.md)で構成されている</span><span class="sxs-lookup"><span data-stu-id="b8070-115">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="b8070-116">ユーザー [id](hololens-identity.md) は AAD です</span><span class="sxs-lookup"><span data-stu-id="b8070-116">User [Identity](hololens-identity.md) is AAD</span></span>

<span data-ttu-id="b8070-117">開発者モードを有効にしたり、Device Portal を使用したりしなくても、アプリをインストールできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b8070-117">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="b8070-118">Appx バンドルをデバイスにダウンロード (USB 経由またはエッジ経由) するだけで、インストールを開始するように促すメッセージが表示されるように、ファイルエクスプローラーで Appx バンドルに移動できます。</span><span class="sxs-lookup"><span data-stu-id="b8070-118">Simply download (over USB or through Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="b8070-119">または、 [web ページからインストールを開始](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)します。</span><span class="sxs-lookup"><span data-stu-id="b8070-119">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="b8070-120">Microsoft Store またはサイドローディングで MDM の LOB アプリの展開機能を使用してインストールしたアプリと同様に、アプリを展開するには、アプリを展開する前に、アプリをインストールする前に、 [サインインツール](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) を使ってデジタル署名する必要があります。また、署名に使用する証明書は、HoloLens デバイスで [信頼される必要があり](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) ます</span><span class="sxs-lookup"><span data-stu-id="b8070-120">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>   

## <span data-ttu-id="b8070-121">要件</span><span class="sxs-lookup"><span data-stu-id="b8070-121">Requirements</span></span>

### <span data-ttu-id="b8070-122">デバイスの場合:</span><span class="sxs-lookup"><span data-stu-id="b8070-122">For your devices:</span></span> 
<span data-ttu-id="b8070-123">これは、現在 HoloLens 2 デバイス用の [Windows Insider ビルド](hololens-insider.md) で avalible されています。</span><span class="sxs-lookup"><span data-stu-id="b8070-123">This is currently avalible in [Windows Insider builds](hololens-insider.md) for HoloLens 2 devices.</span></span> <span data-ttu-id="b8070-124">この方法を使用しているデバイスが [更新](hololens-update-hololens.md)されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b8070-124">Please ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span> 

### <span data-ttu-id="b8070-125">アプリの場合:</span><span class="sxs-lookup"><span data-stu-id="b8070-125">For your apps:</span></span> 
<span data-ttu-id="b8070-126">アプリのインストーラーでストアからの依存関係が使用されるため、アプリのソリューション構成は **Master** または **Release** のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8070-126">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="b8070-127">詳細については、「 [アプリパッケージの作成](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8070-127">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="b8070-128">このメソッドを使ってインストールされたアプリは、デジタル署名されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8070-128">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="b8070-129">アプリに署名するには、証明書を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8070-129">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="b8070-130">[ [MS TRUSTED CA] リスト](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)から証明書を取得することができます。その場合は、追加の操作を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b8070-130">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any additional action.</span></span> <span data-ttu-id="b8070-131">または、独自の証明書に署名することもできます。ただし、証明書はデバイスにプッシュする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8070-131">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span> 
- <span data-ttu-id="b8070-132">[Sign Tool を使って](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)アプリに署名する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="b8070-132">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="b8070-133">証明書オプション:</span><span class="sxs-lookup"><span data-stu-id="b8070-133">Certificate options:</span></span>** 
- [<span data-ttu-id="b8070-134">MS Trusted CA リスト</span><span class="sxs-lookup"><span data-stu-id="b8070-134">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="b8070-135">証明書の展開方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8070-135">Pick a certificate deployment method.</span></span>** 
- <span data-ttu-id="b8070-136">[プロビジョニングパッケージ](hololens-provisioning.md) はローカルデバイスに適用できます。</span><span class="sxs-lookup"><span data-stu-id="b8070-136">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="b8070-137">MDM を使って、 [デバイスの構成に証明書を適用](https://docs.microsoft.com/mem/intune/protect/certificates-configure)することができます。</span><span class="sxs-lookup"><span data-stu-id="b8070-137">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="b8070-138">デバイス [証明書マネージャー](certificate-manager.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="b8070-138">Use the on device [Certificate Manager](certificate-manager.md).</span></span> 

## <span data-ttu-id="b8070-139">インストール方法</span><span class="sxs-lookup"><span data-stu-id="b8070-139">Installation method</span></span>

1.  <span data-ttu-id="b8070-140">デバイスが管理されていると見なされないようにします。</span><span class="sxs-lookup"><span data-stu-id="b8070-140">Ensure that your device is not considered managed.</span></span>
1.  <span data-ttu-id="b8070-141">HoloLens 2 デバイスの電源が入っていて、サインインしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b8070-141">Ensure that your HoloLens 2 device is powered on and you are signed in.</span></span>
1.  <span data-ttu-id="b8070-142">PC でカスタムアプリに移動し、yourapp を yourdevicename\Internal Storage\Downloads. にコピーします。</span><span class="sxs-lookup"><span data-stu-id="b8070-142">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span> 
    <span data-ttu-id="b8070-143">ファイルのコピーが完了したら、デバイスを切断して、後でインストールを完了することができます。</span><span class="sxs-lookup"><span data-stu-id="b8070-143">After your finish copying your file you may disconnect your device and finish the install later.</span></span>
1.  <span data-ttu-id="b8070-144">HoloLens 2 デバイスから [ **スタート] メニュー**を開き、[ **すべてのアプリ** ] を選択して、 **エクスプローラー** アプリを起動します。</span><span class="sxs-lookup"><span data-stu-id="b8070-144">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1.  <span data-ttu-id="b8070-145">[ダウンロード] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="b8070-145">Navigate to the Downloads folder.</span></span> <span data-ttu-id="b8070-146">アプリの左側のパネルで、[ **このデバイス** ] を選択してから、[ダウンロード] に移動することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="b8070-146">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="b8070-147">Yourapp ファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="b8070-147">Select the yourapp.appxbundle file.</span></span> 
1.  <span data-ttu-id="b8070-148">アプリのインストーラーが起動します。</span><span class="sxs-lookup"><span data-stu-id="b8070-148">The App Installer will launch.</span></span> <span data-ttu-id="b8070-149">アプリをインストールするには、[ **インストール** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="b8070-149">Select the **Install** button to install your app.</span></span> 

<span data-ttu-id="b8070-150">インストールされたアプリは、インストールの完了時に自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="b8070-150">The installed app will automatically launch upon the completion of installing.</span></span> 

![App Installer による MRTK の例のインストール](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="b8070-152">インストールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b8070-152">Troubleshooting Installs</span></span>
<span data-ttu-id="b8070-153">アプリのインストールに失敗した場合は、次のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b8070-153">If your app failed to install check the following:</span></span>
-   <span data-ttu-id="b8070-154">アプリがマスターまたはリリースビルドのどちらかです。</span><span class="sxs-lookup"><span data-stu-id="b8070-154">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="b8070-155">使用しているデバイスが、この機能を利用できるビルドに更新されます。</span><span class="sxs-lookup"><span data-stu-id="b8070-155">Your device is updated to a build on which this feature is available.</span></span> 
-   <span data-ttu-id="b8070-156">[インターネットに接続](hololens-network.md)されています。</span><span class="sxs-lookup"><span data-stu-id="b8070-156">You are [connected to the internet](hololens-network.md).</span></span>
-   <span data-ttu-id="b8070-157">[Microsoft Store のエンドポイント](hololens-offline.md)が適切に構成されている。</span><span class="sxs-lookup"><span data-stu-id="b8070-157">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="b8070-158">Web インストーラ</span><span class="sxs-lookup"><span data-stu-id="b8070-158">Web Installer</span></span>

<span data-ttu-id="b8070-159">ユーザーは、web サーバーから直接アプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="b8070-159">Users can install an app directly from a web server.</span></span> <span data-ttu-id="b8070-160">これにより、アプリのインストーラーが、簡単なダウンロードとインストールの配布方法と組み合わされて使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b8070-160">This takes use of the App Installer combined with an easy download and install distribution method.</span></span> 

### <span data-ttu-id="b8070-161">Web インストールのセットアップ方法:</span><span class="sxs-lookup"><span data-stu-id="b8070-161">How to set up web install:</span></span>
1.  <span data-ttu-id="b8070-162">アプリが正しくインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b8070-162">Ensure your app is correctly configured to install.</span></span>
1.  <span data-ttu-id="b8070-163">[Web ページでこの機能を有効にするには、次の手順を](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)実行します。</span><span class="sxs-lookup"><span data-stu-id="b8070-163">Follow these [steps to enable this on a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span> 

### <span data-ttu-id="b8070-164">エンドユーザーエクスペリエンス:</span><span class="sxs-lookup"><span data-stu-id="b8070-164">End user experience:</span></span>
1. <span data-ttu-id="b8070-165">ユーザーは、前に選択した方法を使用して、デバイスに証明書を受け取り、インストールします。</span><span class="sxs-lookup"><span data-stu-id="b8070-165">User receives and installs certificate to the device using a method previously chosen above.</span></span> 
1. <span data-ttu-id="b8070-166">ユーザーは、上の手順で作成した URL にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="b8070-166">User visits the URL created from the step above.</span></span>

<span data-ttu-id="b8070-167">これで、アプリがデバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b8070-167">The app will now install to the device.</span></span> <span data-ttu-id="b8070-168">アプリを見つけるには、[ **スタート] メニュー** を開き、[ **すべてのアプリ** ] ボタンを選んでアプリを見つけます。</span><span class="sxs-lookup"><span data-stu-id="b8070-168">To find the app open the **Start menu** and select the **All apps** button to find your app.</span></span> 

-   <span data-ttu-id="b8070-169">このインストール方法のトラブルシューティングについては、「 [アプリインストーラーの問題のトラブルシューティング](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8070-169">For help troubleshooting this installation method please visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span> 

> [!NOTE]
> <span data-ttu-id="b8070-170">更新プロセス中の UI はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="b8070-170">UI during the update process is not supported.</span></span> <span data-ttu-id="b8070-171">そのため、 [このページ](https://docs.microsoft.com/windows/msix/app-installer/update-settings) と関連オプションの showprompt オプションはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="b8070-171">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="b8070-172">サンプルアプリ</span><span class="sxs-lookup"><span data-stu-id="b8070-172">Sample Apps</span></span>

<span data-ttu-id="b8070-173">サンプルアプリを試してみたい場合は、利用可能なサンプルの一部を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b8070-173">If you'd like to try this out with some sample apps please check out some of our available samples:</span></span>
- [<span data-ttu-id="b8070-174">MRTK の例の Hub</span><span class="sxs-lookup"><span data-stu-id="b8070-174">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="b8070-175">Hba</span><span class="sxs-lookup"><span data-stu-id="b8070-175">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="b8070-176">テストに使用できる UWP サンプルアプリ</span><span class="sxs-lookup"><span data-stu-id="b8070-176">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
