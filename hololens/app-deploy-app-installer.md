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
ms.openlocfilehash: eba1fd00215ef197f9e32949e958bdbded089d6d
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162889"
---
# <span data-ttu-id="848c6-104">アプリインストーラーを使用して HoloLens 2 にアプリをインストールする</span><span class="sxs-lookup"><span data-stu-id="848c6-104">Install Apps on HoloLens 2 via App Installer</span></span>


<span data-ttu-id="848c6-105">Windows ホログラフィック、バージョン20H2 の更新プログラムをインストールした後、すぐにアプリのインストーラー機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="848c6-105">We will ship the app installer capability soon after our Windows Holographic, version 20H2 update.</span></span> <span data-ttu-id="848c6-106">お客様が HoloLens 2 デバイスで **シームレスにアプリケーションをインストールできるように、新しい機能 (アプリのインストーラー) を追加** しています。</span><span class="sxs-lookup"><span data-stu-id="848c6-106">We are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="848c6-107">この機能は、 **非管理対象デバイスでは既定でオンに**なります。</span><span class="sxs-lookup"><span data-stu-id="848c6-107">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="848c6-108">この時点では、企業が中断されないように、アプリインストーラーを **管理対象デバイスで利用できなく** なります。</span><span class="sxs-lookup"><span data-stu-id="848c6-108">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="848c6-109">この機能は現在、Windows Insider ビルドでのみ利用可能です。 </span><span class="sxs-lookup"><span data-stu-id="848c6-109">This feature is currently only avalible in Windows Insider builds.</span></span> <span data-ttu-id="848c6-110">[詳細については、「Windows Insider ビルドに登録する」を参照して](hololens-insider.md)ください。</span><span class="sxs-lookup"><span data-stu-id="848c6-110">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

<span data-ttu-id="848c6-111">Windows Insider のリリースでは、新しい機能 (アプリのインストーラー) を追加して、HoloLens 2 デバイスに **よりシームレスにアプリケーションをインストールできるように** しています。</span><span class="sxs-lookup"><span data-stu-id="848c6-111">In our Windows Insider release, we are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="848c6-112">この機能は、 **非管理対象デバイスでは既定でオンに**なります。</span><span class="sxs-lookup"><span data-stu-id="848c6-112">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="848c6-113">この時点では、企業が中断されないように、アプリインストーラーを **管理対象デバイスで利用できなく** なります。</span><span class="sxs-lookup"><span data-stu-id="848c6-113">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="848c6-114">以下の **いずれか** に該当する場合、デバイスは "管理されています" と見なされます。</span><span class="sxs-lookup"><span data-stu-id="848c6-114">A device is considered “managed” if **any** of the following are true:</span></span>
- <span data-ttu-id="848c6-115">MDM[登録](hololens-enroll-mdm.md)済み</span><span class="sxs-lookup"><span data-stu-id="848c6-115">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="848c6-116">[プロビジョニングパッケージ](hololens-provisioning.md)で構成されている</span><span class="sxs-lookup"><span data-stu-id="848c6-116">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="848c6-117">ユーザー [id](hololens-identity.md) は AAD です</span><span class="sxs-lookup"><span data-stu-id="848c6-117">User [Identity](hololens-identity.md) is AAD</span></span>

<span data-ttu-id="848c6-118">開発者モードを有効にしたり、Device Portal を使用したりしなくても、アプリをインストールできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="848c6-118">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="848c6-119">Appx バンドルをデバイスにダウンロード (USB 経由またはエッジ経由) するだけで、インストールを開始するように促すメッセージが表示されるように、ファイルエクスプローラーで Appx バンドルに移動できます。</span><span class="sxs-lookup"><span data-stu-id="848c6-119">Simply download (over USB or through Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="848c6-120">または、 [web ページからインストールを開始](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)します。</span><span class="sxs-lookup"><span data-stu-id="848c6-120">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="848c6-121">Microsoft Store またはサイドローディングで MDM の LOB アプリの展開機能を使用してインストールしたアプリと同様に、アプリを展開するには、アプリを展開する前に、アプリをインストールする前に、 [サインインツール](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) を使ってデジタル署名する必要があります。また、署名に使用する証明書は、HoloLens デバイスで [信頼される必要があり](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) ます</span><span class="sxs-lookup"><span data-stu-id="848c6-121">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>   

## <span data-ttu-id="848c6-122">要件</span><span class="sxs-lookup"><span data-stu-id="848c6-122">Requirements</span></span>

### <span data-ttu-id="848c6-123">デバイスの場合:</span><span class="sxs-lookup"><span data-stu-id="848c6-123">For your devices:</span></span> 
<span data-ttu-id="848c6-124">これは、現在 HoloLens 2 デバイス用の [Windows Insider ビルド](hololens-insider.md) で avalible されています。</span><span class="sxs-lookup"><span data-stu-id="848c6-124">This is currently avalible in [Windows Insider builds](hololens-insider.md) for HoloLens 2 devices.</span></span> <span data-ttu-id="848c6-125">この方法を使用しているデバイスが [更新](hololens-update-hololens.md)されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="848c6-125">Please ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span> 

### <span data-ttu-id="848c6-126">アプリの場合:</span><span class="sxs-lookup"><span data-stu-id="848c6-126">For your apps:</span></span> 
<span data-ttu-id="848c6-127">アプリのインストーラーでストアからの依存関係が使用されるため、アプリのソリューション構成は **Master** または **Release** のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="848c6-127">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="848c6-128">詳細については、「 [アプリパッケージの作成](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="848c6-128">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="848c6-129">このメソッドを使ってインストールされたアプリは、デジタル署名されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="848c6-129">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="848c6-130">アプリに署名するには、証明書を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="848c6-130">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="848c6-131">[ [MS TRUSTED CA] リスト](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)から証明書を取得することができます。その場合は、追加の操作を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="848c6-131">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any additional action.</span></span> <span data-ttu-id="848c6-132">または、独自の証明書に署名することもできます。ただし、証明書はデバイスにプッシュする必要があります。</span><span class="sxs-lookup"><span data-stu-id="848c6-132">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span> 
- <span data-ttu-id="848c6-133">[Sign Tool を使って](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)アプリに署名する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="848c6-133">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="848c6-134">証明書オプション:</span><span class="sxs-lookup"><span data-stu-id="848c6-134">Certificate options:</span></span>** 
- [<span data-ttu-id="848c6-135">MS Trusted CA リスト</span><span class="sxs-lookup"><span data-stu-id="848c6-135">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="848c6-136">証明書の展開方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="848c6-136">Pick a certificate deployment method.</span></span>** 
- <span data-ttu-id="848c6-137">[プロビジョニングパッケージ](hololens-provisioning.md) はローカルデバイスに適用できます。</span><span class="sxs-lookup"><span data-stu-id="848c6-137">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="848c6-138">MDM を使って、 [デバイスの構成に証明書を適用](https://docs.microsoft.com/mem/intune/protect/certificates-configure)することができます。</span><span class="sxs-lookup"><span data-stu-id="848c6-138">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="848c6-139">デバイス [証明書マネージャー](certificate-manager.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="848c6-139">Use the on device [Certificate Manager](certificate-manager.md).</span></span> 

## <span data-ttu-id="848c6-140">インストール方法</span><span class="sxs-lookup"><span data-stu-id="848c6-140">Installation method</span></span>

1.  <span data-ttu-id="848c6-141">デバイスが管理されていると見なされないようにします。</span><span class="sxs-lookup"><span data-stu-id="848c6-141">Ensure that your device is not considered managed.</span></span>
1.  <span data-ttu-id="848c6-142">HoloLens 2 デバイスの電源が入っていて、サインインしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="848c6-142">Ensure that your HoloLens 2 device is powered on and you are signed in.</span></span>
1.  <span data-ttu-id="848c6-143">PC でカスタムアプリに移動し、yourapp を yourdevicename\Internal Storage\Downloads. にコピーします。</span><span class="sxs-lookup"><span data-stu-id="848c6-143">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span> 
    <span data-ttu-id="848c6-144">ファイルのコピーが完了したら、デバイスを切断して、後でインストールを完了することができます。</span><span class="sxs-lookup"><span data-stu-id="848c6-144">After your finish copying your file you may disconnect your device and finish the install later.</span></span>
1.  <span data-ttu-id="848c6-145">HoloLens 2 デバイスから [ **スタート] メニュー**を開き、[ **すべてのアプリ** ] を選択して、 **エクスプローラー** アプリを起動します。</span><span class="sxs-lookup"><span data-stu-id="848c6-145">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1.  <span data-ttu-id="848c6-146">[ダウンロード] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="848c6-146">Navigate to the Downloads folder.</span></span> <span data-ttu-id="848c6-147">アプリの左側のパネルで、[ **このデバイス** ] を選択してから、[ダウンロード] に移動することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="848c6-147">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="848c6-148">Yourapp ファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="848c6-148">Select the yourapp.appxbundle file.</span></span> 
1.  <span data-ttu-id="848c6-149">アプリのインストーラーが起動します。</span><span class="sxs-lookup"><span data-stu-id="848c6-149">The App Installer will launch.</span></span> <span data-ttu-id="848c6-150">アプリをインストールするには、[ **インストール** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="848c6-150">Select the **Install** button to install your app.</span></span> 

<span data-ttu-id="848c6-151">インストールされたアプリは、インストールの完了時に自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="848c6-151">The installed app will automatically launch upon the completion of installing.</span></span> 

![App Installer による MRTK の例のインストール](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="848c6-153">インストールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="848c6-153">Troubleshooting Installs</span></span>
<span data-ttu-id="848c6-154">アプリのインストールに失敗した場合は、次のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="848c6-154">If your app failed to install check the following:</span></span>
-   <span data-ttu-id="848c6-155">アプリがマスターまたはリリースビルドのどちらかです。</span><span class="sxs-lookup"><span data-stu-id="848c6-155">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="848c6-156">使用しているデバイスが、この機能を利用できるビルドに更新されます。</span><span class="sxs-lookup"><span data-stu-id="848c6-156">Your device is updated to a build on which this feature is available.</span></span> 
-   <span data-ttu-id="848c6-157">[インターネットに接続](hololens-network.md)されています。</span><span class="sxs-lookup"><span data-stu-id="848c6-157">You are [connected to the internet](hololens-network.md).</span></span>
-   <span data-ttu-id="848c6-158">[Microsoft Store のエンドポイント](hololens-offline.md)が適切に構成されている。</span><span class="sxs-lookup"><span data-stu-id="848c6-158">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="848c6-159">Web インストーラ</span><span class="sxs-lookup"><span data-stu-id="848c6-159">Web Installer</span></span>

<span data-ttu-id="848c6-160">ユーザーは、web サーバーから直接アプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="848c6-160">Users can install an app directly from a web server.</span></span> <span data-ttu-id="848c6-161">これにより、アプリのインストーラーが、簡単なダウンロードとインストールの配布方法と組み合わされて使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="848c6-161">This takes use of the App Installer combined with an easy download and install distribution method.</span></span> 

### <span data-ttu-id="848c6-162">Web インストールのセットアップ方法:</span><span class="sxs-lookup"><span data-stu-id="848c6-162">How to set up web install:</span></span>
1.  <span data-ttu-id="848c6-163">アプリが正しくインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="848c6-163">Ensure your app is correctly configured to install.</span></span>
1.  <span data-ttu-id="848c6-164">[Web ページでこの機能を有効にするには、次の手順を](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)実行します。</span><span class="sxs-lookup"><span data-stu-id="848c6-164">Follow these [steps to enable this on a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span> 

### <span data-ttu-id="848c6-165">エンドユーザーエクスペリエンス:</span><span class="sxs-lookup"><span data-stu-id="848c6-165">End user experience:</span></span>
1. <span data-ttu-id="848c6-166">ユーザーは、前に選択した方法を使用して、デバイスに証明書を受け取り、インストールします。</span><span class="sxs-lookup"><span data-stu-id="848c6-166">User receives and installs certificate to the device using a method previously chosen above.</span></span> 
1. <span data-ttu-id="848c6-167">ユーザーは、上の手順で作成した URL にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="848c6-167">User visits the URL created from the step above.</span></span>

<span data-ttu-id="848c6-168">これで、アプリがデバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="848c6-168">The app will now install to the device.</span></span> <span data-ttu-id="848c6-169">アプリを見つけるには、[ **スタート] メニュー** を開き、[ **すべてのアプリ** ] ボタンを選んでアプリを見つけます。</span><span class="sxs-lookup"><span data-stu-id="848c6-169">To find the app open the **Start menu** and select the **All apps** button to find your app.</span></span> 

-   <span data-ttu-id="848c6-170">このインストール方法のトラブルシューティングについては、「 [アプリインストーラーの問題のトラブルシューティング](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="848c6-170">For help troubleshooting this installation method please visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span> 

> [!NOTE]
> <span data-ttu-id="848c6-171">更新プロセス中の UI はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="848c6-171">UI during the update process is not supported.</span></span> <span data-ttu-id="848c6-172">そのため、 [このページ](https://docs.microsoft.com/windows/msix/app-installer/update-settings) と関連オプションの showprompt オプションはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="848c6-172">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="848c6-173">サンプルアプリ</span><span class="sxs-lookup"><span data-stu-id="848c6-173">Sample Apps</span></span>

<span data-ttu-id="848c6-174">サンプルアプリを試してみたい場合は、利用可能なサンプルの一部を確認してください。</span><span class="sxs-lookup"><span data-stu-id="848c6-174">If you'd like to try this out with some sample apps please check out some of our available samples:</span></span>
- [<span data-ttu-id="848c6-175">MRTK の例の Hub</span><span class="sxs-lookup"><span data-stu-id="848c6-175">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="848c6-176">Hba</span><span class="sxs-lookup"><span data-stu-id="848c6-176">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="848c6-177">テストに使用できる UWP サンプルアプリ</span><span class="sxs-lookup"><span data-stu-id="848c6-177">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
