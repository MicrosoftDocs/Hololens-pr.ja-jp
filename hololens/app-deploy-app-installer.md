---
title: アプリの読み込みとインストールのサイド HoloLens 2 アプリ インストーラー
description: アプリ インストーラーを使用してアプリをインストールし、トラブルシューティングを行い、UI を使用してアプリをサイド ロードしてインストールする方法について説明します。
keywords: アプリ管理, アプリ, Hololens, アプリ インストーラー
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
ms.openlocfilehash: 8f236ee27903069b65d3ded8eb7a1f37c65f535e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635587"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="42bf0-104">HoloLens 2 経由でアプリを アプリ インストーラー</span><span class="sxs-lookup"><span data-stu-id="42bf0-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="42bf0-105">この機能は[、Holographic バージョン 20H2 Windows 2020 年 12](hololens-release-notes.md)月の更新プログラム で使用できます。</span><span class="sxs-lookup"><span data-stu-id="42bf0-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="42bf0-106">この機能を使用するには [、デバイス](hololens-update-hololens.md) が更新されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="42bf0-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="42bf0-107">新しい **機能 (アプリ インストーラー)** が追加され、お使いのデバイスにアプリケーションをシームレスにHoloLens 2しました。</span><span class="sxs-lookup"><span data-stu-id="42bf0-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="42bf0-108">この機能は、アン **マネージド デバイスでは既定でオンになります**。</span><span class="sxs-lookup"><span data-stu-id="42bf0-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="42bf0-109">企業の中断を防ぐために、現時点では、マネージド デバイスでアプリ インストーラー **を** 使用できません。</span><span class="sxs-lookup"><span data-stu-id="42bf0-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="42bf0-110">次の条件に当てはまる場合、デバイスは "マネージド" と見なされます。</span><span class="sxs-lookup"><span data-stu-id="42bf0-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="42bf0-111">MDM [登録済み](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="42bf0-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="42bf0-112">プロビジョニング パッケージ [を使用して構成する](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="42bf0-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="42bf0-113">ユーザー [ID が](hololens-identity.md) Azure AD</span><span class="sxs-lookup"><span data-stu-id="42bf0-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="42bf0-114">開発者モードを有効にしたり、アプリを使用したりせずにアプリをインストールデバイス ポータル。</span><span class="sxs-lookup"><span data-stu-id="42bf0-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="42bf0-115">(USB 経由または Microsoft Edge 経由で) Appx バンドルをデバイスにダウンロードし、エクスプローラー の Appx バンドルに移動して、インストールを開始するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="42bf0-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="42bf0-116">または、Web [ページ からインストールを開始します](/windows/msix/app-installer/installing-windows10-apps-web)。</span><span class="sxs-lookup"><span data-stu-id="42bf0-116">Alternatively, [initiate an install from a web page](/windows/msix/app-installer/installing-windows10-apps-web).</span></span> <span data-ttu-id="42bf0-117">mdm の LOB アプリ展開機能を使用して Microsoft Store またはサイドロードからインストールするアプリと同様に、アプリは署名ツールでデジタル[](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)署名する必要があります[](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)。また、アプリを展開する前に、署名に使用される証明書が HoloLens デバイスによって信頼されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="42bf0-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <a name="requirements"></a><span data-ttu-id="42bf0-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="42bf0-118">Requirements</span></span>

### <a name="for-your-devices"></a><span data-ttu-id="42bf0-119">デバイスの場合:</span><span class="sxs-lookup"><span data-stu-id="42bf0-119">For your devices:</span></span>

<span data-ttu-id="42bf0-120">この機能は、現在、デバイスWindows Holographic 20H2 ビルドでHoloLens 2されています。</span><span class="sxs-lookup"><span data-stu-id="42bf0-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="42bf0-121">この方法を使用しているデバイスが[更新されます。](hololens-update-hololens.md)</span><span class="sxs-lookup"><span data-stu-id="42bf0-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <a name="for-your-apps"></a><span data-ttu-id="42bf0-122">アプリの場合:</span><span class="sxs-lookup"><span data-stu-id="42bf0-122">For your apps:</span></span>

<span data-ttu-id="42bf0-123">アプリのソリューション構成は、ストアからの依存関係を使用アプリ インストーラーマスターまたはリリースのいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="42bf0-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="42bf0-124">アプリ パッケージの作成に [関する詳細を参照してください](/windows/msix/app-installer/create-appinstallerfile-vs)。</span><span class="sxs-lookup"><span data-stu-id="42bf0-124">See more about [creating app packages](/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="42bf0-125">この方法でインストールされるアプリは、デジタル署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42bf0-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="42bf0-126">証明書を使用してアプリに署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42bf0-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="42bf0-127">MS の信頼された [CA](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)リストから証明書を取得できます。その場合は、追加のアクションを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="42bf0-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="42bf0-128">または、独自の証明書に署名することもできますが、その証明書をデバイスにプッシュする必要があります。</span><span class="sxs-lookup"><span data-stu-id="42bf0-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="42bf0-129">署名ツールを使用 [してアプリに署名する方法。](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="42bf0-129">How to sign apps [using the Sign Tool.](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

<span data-ttu-id="42bf0-130">**証明書のオプション:**</span><span class="sxs-lookup"><span data-stu-id="42bf0-130">**Certificate options:**</span></span>

- [<span data-ttu-id="42bf0-131">MS 信頼された CA リスト</span><span class="sxs-lookup"><span data-stu-id="42bf0-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

<span data-ttu-id="42bf0-132">**証明書の展開方法を選択します。**</span><span class="sxs-lookup"><span data-stu-id="42bf0-132">**Pick a certificate deployment method.**</span></span>

- <span data-ttu-id="42bf0-133">[プロビジョニング パッケージは](hololens-provisioning.md) 、ローカル デバイスに適用できます。</span><span class="sxs-lookup"><span data-stu-id="42bf0-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="42bf0-134">MDM を使用して、 [デバイス構成 を使用して証明書を適用できます](/mem/intune/protect/certificates-configure)。</span><span class="sxs-lookup"><span data-stu-id="42bf0-134">MDM can be used to [apply certificates with device configurations](/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="42bf0-135">デバイスの証明書マネージャー で [を使用します](certificate-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="42bf0-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <a name="installation-method"></a><span data-ttu-id="42bf0-136">インストール方法</span><span class="sxs-lookup"><span data-stu-id="42bf0-136">Installation method</span></span>

1. <span data-ttu-id="42bf0-137">デバイスが管理対象と見なされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="42bf0-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="42bf0-138">デバイスの電源HoloLens 2、サインイン済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="42bf0-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="42bf0-139">PC でカスタム アプリに移動し、yourapp.appxbundle を yourdevicename\Internal Storage\Downloads にコピーします。</span><span class="sxs-lookup"><span data-stu-id="42bf0-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="42bf0-140">ファイルのコピーが完了したら、デバイスを切断し、後でインストールを完了できます。</span><span class="sxs-lookup"><span data-stu-id="42bf0-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="42bf0-141">デバイスからHoloLens 2スタート メニューを **開** き **、[すべてのアプリ**] を選択し、アプリを起動 **エクスプローラーします。**</span><span class="sxs-lookup"><span data-stu-id="42bf0-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="42bf0-142">[ダウンロード] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="42bf0-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="42bf0-143">アプリの左側のパネルで、[このデバイス] を最初に選択し、[ダウンロード] に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42bf0-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="42bf0-144">yourapp.appxbundle ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="42bf0-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="42bf0-145">このアプリ インストーラーが起動します。</span><span class="sxs-lookup"><span data-stu-id="42bf0-145">The App Installer will launch.</span></span> <span data-ttu-id="42bf0-146">[インストール **] ボタンを** 選択して、アプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="42bf0-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="42bf0-147">インストールが完了すると、インストールされたアプリが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="42bf0-147">The installed app will automatically launch upon the completion of installing.</span></span>

![以下を使用した MRTK のアプリ インストーラー](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a><span data-ttu-id="42bf0-149">インストールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="42bf0-149">Troubleshooting Installs</span></span>

<span data-ttu-id="42bf0-150">アプリのインストールに失敗した場合は、次を確認してトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="42bf0-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="42bf0-151">アプリはマスター ビルドまたはリリース ビルドのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="42bf0-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="42bf0-152">デバイスは、この機能を使用できるビルドに更新されます。</span><span class="sxs-lookup"><span data-stu-id="42bf0-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="42bf0-153">インターネット [に接続されています](hololens-network.md)。</span><span class="sxs-lookup"><span data-stu-id="42bf0-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="42bf0-154">アプリケーション[のエンドポイントMicrosoft Store](hololens-offline.md)正しく構成されています。</span><span class="sxs-lookup"><span data-stu-id="42bf0-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <a name="web-installer"></a><span data-ttu-id="42bf0-155">Web インストーラー</span><span class="sxs-lookup"><span data-stu-id="42bf0-155">Web Installer</span></span>

<span data-ttu-id="42bf0-156">ユーザーは Web サーバーから直接アプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="42bf0-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="42bf0-157">このフローでは、簡単なダウンロードとインストールアプリ インストーラー方法と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42bf0-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <a name="how-to-set-up-web-install"></a><span data-ttu-id="42bf0-158">Web インストールを設定する方法:</span><span class="sxs-lookup"><span data-stu-id="42bf0-158">How to set up web install:</span></span>

1. <span data-ttu-id="42bf0-159">アプリがインストールするように正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="42bf0-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="42bf0-160">Web ページ から [インストールを有効にするには、次の手順に従います](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。</span><span class="sxs-lookup"><span data-stu-id="42bf0-160">Follow these [steps to enable install from a web page](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="42bf0-161">エンド ユーザー エクスペリエンス:</span><span class="sxs-lookup"><span data-stu-id="42bf0-161">End user experience:</span></span>

1. <span data-ttu-id="42bf0-162">ユーザーは、前に選択した方法を使用して、デバイスに証明書を受信してインストールします。</span><span class="sxs-lookup"><span data-stu-id="42bf0-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="42bf0-163">ユーザーは、上記の手順で作成した URL にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="42bf0-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="42bf0-164">これで、アプリがデバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="42bf0-164">The app will now install to the device.</span></span> <span data-ttu-id="42bf0-165">アプリを見つけるには、アプリ **を開** スタート メニュー[すべてのアプリ]ボタンを選択してアプリを見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="42bf0-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="42bf0-166">アプリ インストーラーのインストール方法のトラブルシューティングの詳細については、アプリ インストーラーの [問題のトラブルシューティングに関するページを参照してください](/windows/msix/app-installer/troubleshoot-appinstaller-issues)。</span><span class="sxs-lookup"><span data-stu-id="42bf0-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="42bf0-167">更新プロセス中の UI はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="42bf0-167">UI during the update process is not supported.</span></span> <span data-ttu-id="42bf0-168">そのため、このページの ShowPrompt [オプションと](/windows/msix/app-installer/update-settings) 関連オプションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="42bf0-168">So the ShowPrompt option on [this page](/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <a name="sample-apps"></a><span data-ttu-id="42bf0-169">サンプル アプリ</span><span class="sxs-lookup"><span data-stu-id="42bf0-169">Sample Apps</span></span>

<span data-ttu-id="42bf0-170">使用可能なサンプル アプリ インストーラーを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="42bf0-170">Try out the App Installer with one of our available sample apps.</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="42bf0-171">サンプル アプリ</span><span class="sxs-lookup"><span data-stu-id="42bf0-171">Sample apps</span></span>](/windows/mixed-reality/develop/features-and-samples)
