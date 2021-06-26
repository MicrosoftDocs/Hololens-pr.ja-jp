---
title: HoloLens 2 アプリ インストーラー を使用してアプリをサイド ロードしてインストールするHoloLens 2 アプリ インストーラー
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
ms.openlocfilehash: d8be5c2ed7fba38b6710aba9c122557a36073a79
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924130"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="87b68-104">アプリ インストーラー 経由でアプリを HoloLens 2 にインストールアプリ インストーラー</span><span class="sxs-lookup"><span data-stu-id="87b68-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="87b68-105">この機能は [、Windows Holographic バージョン 20H2 から 2020 年 12 月の更新プログラム で使用できます](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="87b68-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="87b68-106">この機能を使用するには [、デバイス](hololens-update-hololens.md) が更新されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="87b68-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="87b68-107">新しい **機能 (アプリ インストーラー)** が追加され、お使いのデバイスにアプリケーションをシームレスにHoloLens 2しました。</span><span class="sxs-lookup"><span data-stu-id="87b68-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="87b68-108">この機能は、アン **マネージド デバイスでは既定でオンになります**。</span><span class="sxs-lookup"><span data-stu-id="87b68-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="87b68-109">企業の中断を防ぐために、現時点では、マネージド デバイスでアプリ インストーラー **を** 使用できません。</span><span class="sxs-lookup"><span data-stu-id="87b68-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="87b68-110">次の条件に当てはまる場合、デバイスは "マネージド" と見なされます。</span><span class="sxs-lookup"><span data-stu-id="87b68-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="87b68-111">MDM [登録済み](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="87b68-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="87b68-112">プロビジョニング パッケージ [を使用して構成する](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="87b68-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="87b68-113">ユーザー [ID が](hololens-identity.md) Azure AD</span><span class="sxs-lookup"><span data-stu-id="87b68-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="87b68-114">開発者モードを有効にしたり、アプリを使用したりせずにアプリをインストールデバイス ポータル。</span><span class="sxs-lookup"><span data-stu-id="87b68-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="87b68-115">(USB 経由または Microsoft Edge 経由で) Appx バンドルをデバイスにダウンロードし、エクスプローラー の Appx バンドルに移動して、インストールを開始するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87b68-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="87b68-116">または、Web [ページ からインストールを開始します](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。</span><span class="sxs-lookup"><span data-stu-id="87b68-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="87b68-117">MDM の LOB アプリ展開機能を使用して Microsoft Store またはサイドロードからインストールするアプリと同様に、アプリは署名ツールを[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)使用してデジタル署名[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)する必要があります。また、アプリを展開する前に、署名に使用される証明書が HoloLens デバイスによって信頼されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="87b68-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <a name="requirements"></a><span data-ttu-id="87b68-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="87b68-118">Requirements</span></span>

### <a name="for-your-devices"></a><span data-ttu-id="87b68-119">デバイスの場合:</span><span class="sxs-lookup"><span data-stu-id="87b68-119">For your devices:</span></span>

<span data-ttu-id="87b68-120">この機能は、現在、Windows Holographic 20H2 ビルドで、HoloLens 2できます。</span><span class="sxs-lookup"><span data-stu-id="87b68-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="87b68-121">この方法を使用しているデバイスが[更新されます。](hololens-update-hololens.md)</span><span class="sxs-lookup"><span data-stu-id="87b68-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <a name="for-your-apps"></a><span data-ttu-id="87b68-122">アプリの場合:</span><span class="sxs-lookup"><span data-stu-id="87b68-122">For your apps:</span></span>

<span data-ttu-id="87b68-123">アプリのソリューション構成は、ストアからの依存関係を使用アプリ インストーラーマスターまたはリリースのいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="87b68-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="87b68-124">アプリ パッケージの作成に [関する詳細を参照してください](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)。</span><span class="sxs-lookup"><span data-stu-id="87b68-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="87b68-125">この方法でインストールされるアプリは、デジタル署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87b68-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="87b68-126">証明書を使用してアプリに署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87b68-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="87b68-127">MS の信頼された [CA](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)リストから証明書を取得できます。その場合は、追加のアクションを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="87b68-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="87b68-128">または、独自の証明書に署名することもできますが、その証明書をデバイスにプッシュする必要があります。</span><span class="sxs-lookup"><span data-stu-id="87b68-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="87b68-129">署名ツールを使用 [してアプリに署名する方法。](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="87b68-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

<span data-ttu-id="87b68-130">**証明書のオプション:**</span><span class="sxs-lookup"><span data-stu-id="87b68-130">**Certificate options:**</span></span>

- [<span data-ttu-id="87b68-131">MS 信頼された CA リスト</span><span class="sxs-lookup"><span data-stu-id="87b68-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

<span data-ttu-id="87b68-132">**証明書の展開方法を選択します。**</span><span class="sxs-lookup"><span data-stu-id="87b68-132">**Pick a certificate deployment method.**</span></span>

- <span data-ttu-id="87b68-133">[プロビジョニング パッケージは](hololens-provisioning.md) 、ローカル デバイスに適用できます。</span><span class="sxs-lookup"><span data-stu-id="87b68-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="87b68-134">MDM を使用して、 [デバイス構成 を使用して証明書を適用できます](https://docs.microsoft.com/mem/intune/protect/certificates-configure)。</span><span class="sxs-lookup"><span data-stu-id="87b68-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="87b68-135">デバイスの証明書マネージャー で [を使用します](certificate-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="87b68-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <a name="installation-method"></a><span data-ttu-id="87b68-136">インストール方法</span><span class="sxs-lookup"><span data-stu-id="87b68-136">Installation method</span></span>

1. <span data-ttu-id="87b68-137">デバイスが管理対象と見なされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="87b68-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="87b68-138">デバイスの電源HoloLens 2、サインイン済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="87b68-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="87b68-139">PC でカスタム アプリに移動し、yourapp.appxbundle を yourdevicename\Internal Storage\Downloads にコピーします。</span><span class="sxs-lookup"><span data-stu-id="87b68-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="87b68-140">ファイルのコピーが完了したら、デバイスを切断し、後でインストールを完了できます。</span><span class="sxs-lookup"><span data-stu-id="87b68-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="87b68-141">デバイスからHoloLens 2スタート メニューを **開** き、[**すべてのアプリ]** を選択し、アプリの **エクスプローラーします。**</span><span class="sxs-lookup"><span data-stu-id="87b68-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="87b68-142">[ダウンロード] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="87b68-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="87b68-143">アプリの左側のパネルで、[このデバイス] を最初に選択し、[ダウンロード] に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87b68-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="87b68-144">yourapp.appxbundle ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="87b68-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="87b68-145">このアプリ インストーラーが起動します。</span><span class="sxs-lookup"><span data-stu-id="87b68-145">The App Installer will launch.</span></span> <span data-ttu-id="87b68-146">[インストール **] ボタンを** 選択して、アプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="87b68-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="87b68-147">インストールが完了すると、インストールされたアプリが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="87b68-147">The installed app will automatically launch upon the completion of installing.</span></span>

![以下を使用した MRTK のアプリ インストーラー](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a><span data-ttu-id="87b68-149">インストールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="87b68-149">Troubleshooting Installs</span></span>

<span data-ttu-id="87b68-150">アプリのインストールに失敗した場合は、次を確認してトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="87b68-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="87b68-151">アプリはマスター ビルドまたはリリース ビルドのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="87b68-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="87b68-152">デバイスは、この機能を使用できるビルドに更新されます。</span><span class="sxs-lookup"><span data-stu-id="87b68-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="87b68-153">インターネット [に接続されています](hololens-network.md)。</span><span class="sxs-lookup"><span data-stu-id="87b68-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="87b68-154">アプリケーション [のエンドポイントがMicrosoft Store](hololens-offline.md) 正しく構成されています。</span><span class="sxs-lookup"><span data-stu-id="87b68-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <a name="web-installer"></a><span data-ttu-id="87b68-155">Web インストーラー</span><span class="sxs-lookup"><span data-stu-id="87b68-155">Web Installer</span></span>

<span data-ttu-id="87b68-156">ユーザーは Web サーバーから直接アプリをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="87b68-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="87b68-157">このフローでは、簡単なダウンロードとインストールアプリ インストーラー方法と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87b68-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <a name="how-to-set-up-web-install"></a><span data-ttu-id="87b68-158">Web インストールを設定する方法:</span><span class="sxs-lookup"><span data-stu-id="87b68-158">How to set up web install:</span></span>

1. <span data-ttu-id="87b68-159">アプリがインストールするように正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="87b68-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="87b68-160">Web ページ から [インストールを有効にするには、次の手順に従います](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。</span><span class="sxs-lookup"><span data-stu-id="87b68-160">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="87b68-161">エンド ユーザー エクスペリエンス:</span><span class="sxs-lookup"><span data-stu-id="87b68-161">End user experience:</span></span>

1. <span data-ttu-id="87b68-162">ユーザーは、前に選択した方法を使用して、デバイスに証明書を受信してインストールします。</span><span class="sxs-lookup"><span data-stu-id="87b68-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="87b68-163">ユーザーは、上記の手順で作成した URL にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="87b68-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="87b68-164">これで、アプリがデバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="87b68-164">The app will now install to the device.</span></span> <span data-ttu-id="87b68-165">アプリを見つけるには、アプリ **を開** スタート メニュー[すべてのアプリ] ボタン **を選択して** アプリを検索します。</span><span class="sxs-lookup"><span data-stu-id="87b68-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="87b68-166">アプリ インストーラーのインストール方法のトラブルシューティングの詳細については、アプリ インストーラーの [問題のトラブルシューティングに関するページを参照してください](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)。</span><span class="sxs-lookup"><span data-stu-id="87b68-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="87b68-167">更新プロセス中の UI はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="87b68-167">UI during the update process is not supported.</span></span> <span data-ttu-id="87b68-168">そのため、このページの ShowPrompt [オプションと](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 関連オプションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="87b68-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <a name="sample-apps"></a><span data-ttu-id="87b68-169">サンプル アプリ</span><span class="sxs-lookup"><span data-stu-id="87b68-169">Sample Apps</span></span>

<span data-ttu-id="87b68-170">使用可能なサンプル アプリ インストーラーを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="87b68-170">Try out the App Installer with one of our available sample apps.</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="87b68-171">サンプル アプリ</span><span class="sxs-lookup"><span data-stu-id="87b68-171">Sample apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/features-and-samples?tabs=unity#sample-apps)
