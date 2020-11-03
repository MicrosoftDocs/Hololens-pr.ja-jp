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
ms.openlocfilehash: 415733bb2809b7ae2808edc097423f8928910c57
ms.sourcegitcommit: c4fd9a87bb7c728c73418f95a1b15dd93b0af7c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "11150918"
---
# <span data-ttu-id="5114c-104">アプリインストーラーを使用して HoloLens 2 にアプリをインストールする</span><span class="sxs-lookup"><span data-stu-id="5114c-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5114c-105">この機能は、現時点では、Windows Insider ビルド 19041.1377 + でのみ avalible になっています。</span><span class="sxs-lookup"><span data-stu-id="5114c-105">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="5114c-106">[詳細については、「Windows Insider ビルドに登録する」を参照して](hololens-insider.md)ください。</span><span class="sxs-lookup"><span data-stu-id="5114c-106">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

<span data-ttu-id="5114c-107">Windows Insider のリリースでは、新しい機能 (アプリのインストーラー) を追加して、HoloLens 2 デバイスに **よりシームレスにアプリケーションをインストールできるように** しています。</span><span class="sxs-lookup"><span data-stu-id="5114c-107">In our Windows Insider release, we are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="5114c-108">この機能は、 **非管理対象デバイスでは既定でオンに**なります。</span><span class="sxs-lookup"><span data-stu-id="5114c-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="5114c-109">この時点では、企業が中断されないように、アプリインストーラーを **管理対象デバイスで利用できなく** なります。</span><span class="sxs-lookup"><span data-stu-id="5114c-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="5114c-110">以下の **いずれか** に該当する場合、デバイスは "管理されています" と見なされます。</span><span class="sxs-lookup"><span data-stu-id="5114c-110">A device is considered “managed” if **any** of the following are true:</span></span>
- <span data-ttu-id="5114c-111">MDM[登録](hololens-enroll-mdm.md)済み</span><span class="sxs-lookup"><span data-stu-id="5114c-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="5114c-112">[プロビジョニングパッケージ](hololens-provisioning.md)で構成されている</span><span class="sxs-lookup"><span data-stu-id="5114c-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="5114c-113">ユーザー [id](hololens-identity.md) は AAD です</span><span class="sxs-lookup"><span data-stu-id="5114c-113">User [Identity](hololens-identity.md) is AAD</span></span>

<span data-ttu-id="5114c-114">開発者モードを有効にしたり、Device Portal を使用したりしなくても、アプリをインストールできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5114c-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="5114c-115">Appx バンドルをデバイスにダウンロード (USB 経由またはエッジ経由) するだけで、インストールを開始するように促すメッセージが表示されるように、ファイルエクスプローラーで Appx バンドルに移動できます。</span><span class="sxs-lookup"><span data-stu-id="5114c-115">Simply download (over USB or through Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="5114c-116">または、 [web ページからインストールを開始](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)します。</span><span class="sxs-lookup"><span data-stu-id="5114c-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="5114c-117">Microsoft Store またはサイドローディングで MDM の LOB アプリの展開機能を使用してインストールしたアプリと同様に、アプリを展開するには、アプリを展開する前に、アプリをインストールする前に、 [サインインツール](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) を使ってデジタル署名する必要があります。また、署名に使用する証明書は、HoloLens デバイスで [信頼される必要があり](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) ます</span><span class="sxs-lookup"><span data-stu-id="5114c-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>   

## <span data-ttu-id="5114c-118">要件</span><span class="sxs-lookup"><span data-stu-id="5114c-118">Requirements</span></span>

### <span data-ttu-id="5114c-119">デバイスの場合:</span><span class="sxs-lookup"><span data-stu-id="5114c-119">For your devices:</span></span> 
> [!NOTE]
> <span data-ttu-id="5114c-120">この機能は、現時点では、Windows Insider ビルド 19041.1377 + でのみ avalible になっています。</span><span class="sxs-lookup"><span data-stu-id="5114c-120">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="5114c-121">[詳細については、「Windows Insider ビルドに登録する」を参照して](hololens-insider.md)ください。</span><span class="sxs-lookup"><span data-stu-id="5114c-121">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

### <span data-ttu-id="5114c-122">アプリの場合:</span><span class="sxs-lookup"><span data-stu-id="5114c-122">For your apps:</span></span> 
<span data-ttu-id="5114c-123">アプリのインストーラーでストアからの依存関係が使用されるため、アプリのソリューション構成は **Master** または **Release** のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5114c-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="5114c-124">詳細については、「 [アプリパッケージの作成](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5114c-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="5114c-125">このメソッドを使ってインストールされたアプリは、デジタル署名されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5114c-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="5114c-126">アプリに署名するには、証明書を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5114c-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="5114c-127">[ [MS TRUSTED CA] リスト](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)から証明書を取得することができます。その場合は、追加の操作を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5114c-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any additional action.</span></span> <span data-ttu-id="5114c-128">または、独自の証明書に署名することもできます。ただし、証明書はデバイスにプッシュする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5114c-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span> 
- <span data-ttu-id="5114c-129">[Sign Tool を使って](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)アプリに署名する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="5114c-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="5114c-130">証明書オプション:</span><span class="sxs-lookup"><span data-stu-id="5114c-130">Certificate options:</span></span>** 
- [<span data-ttu-id="5114c-131">MS Trusted CA リスト</span><span class="sxs-lookup"><span data-stu-id="5114c-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="5114c-132">証明書の展開方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="5114c-132">Pick a certificate deployment method.</span></span>** 
- <span data-ttu-id="5114c-133">[プロビジョニングパッケージ](hololens-provisioning.md) はローカルデバイスに適用できます。</span><span class="sxs-lookup"><span data-stu-id="5114c-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="5114c-134">MDM を使って、 [デバイスの構成に証明書を適用](https://docs.microsoft.com/mem/intune/protect/certificates-configure)することができます。</span><span class="sxs-lookup"><span data-stu-id="5114c-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="5114c-135">デバイス [証明書マネージャー](hololens-insider.md#certificate-manager)を使用します。</span><span class="sxs-lookup"><span data-stu-id="5114c-135">Use the on device [Certificate Manager](hololens-insider.md#certificate-manager).</span></span> 

## <span data-ttu-id="5114c-136">インストール方法</span><span class="sxs-lookup"><span data-stu-id="5114c-136">Installation method</span></span>

1.  <span data-ttu-id="5114c-137">デバイスが管理されていると見なされないようにします。</span><span class="sxs-lookup"><span data-stu-id="5114c-137">Ensure that your device is not considered managed.</span></span>
1.  <span data-ttu-id="5114c-138">HoloLens 2 デバイスの電源が入っていて、サインインしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5114c-138">Ensure that your HoloLens 2 device is powered on and you are signed in.</span></span>
1.  <span data-ttu-id="5114c-139">PC でカスタムアプリに移動し、yourapp を yourdevicename\Internal Storage\Downloads. にコピーします。</span><span class="sxs-lookup"><span data-stu-id="5114c-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span> 
    <span data-ttu-id="5114c-140">ファイルのコピーが完了したら、デバイスを切断して、後でインストールを完了することができます。</span><span class="sxs-lookup"><span data-stu-id="5114c-140">After your finish copying your file you may disconnect your device and finish the install later.</span></span>
1.  <span data-ttu-id="5114c-141">HoloLens 2 デバイスから [ **スタート] メニュー**を開き、[ **すべてのアプリ** ] を選択して、 **エクスプローラー** アプリを起動します。</span><span class="sxs-lookup"><span data-stu-id="5114c-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1.  <span data-ttu-id="5114c-142">[ダウンロード] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="5114c-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="5114c-143">アプリの左側のパネルで、[ **このデバイス** ] を選択してから、[ダウンロード] に移動することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="5114c-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="5114c-144">Yourapp ファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="5114c-144">Select the yourapp.appxbundle file.</span></span> 
1.  <span data-ttu-id="5114c-145">アプリのインストーラーが起動します。</span><span class="sxs-lookup"><span data-stu-id="5114c-145">The App Installer will launch.</span></span> <span data-ttu-id="5114c-146">アプリをインストールするには、[ **インストール** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5114c-146">Select the **Install** button to install your app.</span></span> 

<span data-ttu-id="5114c-147">インストールされたアプリは、インストールの完了時に自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="5114c-147">The installed app will automatically launch upon the completion of installing.</span></span> 

![App Installer による MRTK の例のインストール](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="5114c-149">インストールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5114c-149">Troubleshooting Installs</span></span>
<span data-ttu-id="5114c-150">アプリのインストールに失敗した場合は、次のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5114c-150">If your app failed to install check the following:</span></span>
-   <span data-ttu-id="5114c-151">アプリがマスターまたはリリースビルドのどちらかです。</span><span class="sxs-lookup"><span data-stu-id="5114c-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="5114c-152">使用しているデバイスが、この機能を利用できるビルドに更新されます。</span><span class="sxs-lookup"><span data-stu-id="5114c-152">Your device is updated to a build on which this feature is available.</span></span> 
-   <span data-ttu-id="5114c-153">[インターネットに接続](hololens-network.md)されています。</span><span class="sxs-lookup"><span data-stu-id="5114c-153">You are [connected to the internet](hololens-network.md).</span></span>
-   <span data-ttu-id="5114c-154">[Microsoft Store のエンドポイント](hololens-offline.md)が適切に構成されている。</span><span class="sxs-lookup"><span data-stu-id="5114c-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="5114c-155">Web インストーラ</span><span class="sxs-lookup"><span data-stu-id="5114c-155">Web Installer</span></span>

<span data-ttu-id="5114c-156">ユーザーは、web サーバーから直接アプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="5114c-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="5114c-157">これにより、アプリのインストーラーが、簡単なダウンロードとインストールの配布方法と組み合わされて使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5114c-157">This takes use of the App Installer combined with an easy download and install distribution method.</span></span> 

### <span data-ttu-id="5114c-158">Web インストールのセットアップ方法:</span><span class="sxs-lookup"><span data-stu-id="5114c-158">How to set up web install:</span></span>
1.  <span data-ttu-id="5114c-159">アプリが正しくインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5114c-159">Ensure your app is correctly configured to install.</span></span>
1.  <span data-ttu-id="5114c-160">[Web ページでこの機能を有効にするには、次の手順を](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)実行します。</span><span class="sxs-lookup"><span data-stu-id="5114c-160">Follow these [steps to enable this on a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span> 

### <span data-ttu-id="5114c-161">エンドユーザーエクスペリエンス:</span><span class="sxs-lookup"><span data-stu-id="5114c-161">End user experience:</span></span>
1. <span data-ttu-id="5114c-162">ユーザーは、前に選択した方法を使用して、デバイスに証明書を受け取り、インストールします。</span><span class="sxs-lookup"><span data-stu-id="5114c-162">User receives and installs certificate to the device using a method previously chosen above.</span></span> 
1. <span data-ttu-id="5114c-163">ユーザーは、上の手順で作成した URL にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="5114c-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="5114c-164">これで、アプリがデバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="5114c-164">The app will now install to the device.</span></span> <span data-ttu-id="5114c-165">アプリを見つけるには、[ **スタート] メニュー** を開き、[ **すべてのアプリ** ] ボタンを選んでアプリを見つけます。</span><span class="sxs-lookup"><span data-stu-id="5114c-165">To find the app open the **Start menu** and select the **All apps** button to find your app.</span></span> 

-   <span data-ttu-id="5114c-166">このインストール方法のトラブルシューティングについては、「 [アプリインストーラーの問題のトラブルシューティング](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5114c-166">For help troubleshooting this installation method please visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span> 

> [!NOTE]
> <span data-ttu-id="5114c-167">更新プロセス中の UI はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="5114c-167">UI during the update process is not supported.</span></span> <span data-ttu-id="5114c-168">そのため、 [このページ](https://docs.microsoft.com/windows/msix/app-installer/update-settings) と関連オプションの showprompt オプションはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="5114c-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="5114c-169">サンプルアプリ</span><span class="sxs-lookup"><span data-stu-id="5114c-169">Sample Apps</span></span>

<span data-ttu-id="5114c-170">サンプルアプリを試してみたい場合は、利用可能なサンプルの一部を確認してください。</span><span class="sxs-lookup"><span data-stu-id="5114c-170">If you'd like to try this out with some sample apps please check out some of our available samples:</span></span>
- [<span data-ttu-id="5114c-171">MRTK の例の Hub</span><span class="sxs-lookup"><span data-stu-id="5114c-171">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="5114c-172">Hba</span><span class="sxs-lookup"><span data-stu-id="5114c-172">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="5114c-173">テストに使用できる UWP サンプルアプリ</span><span class="sxs-lookup"><span data-stu-id="5114c-173">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
