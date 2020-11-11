---
title: Microsoft HoloLens の Insider Preview
description: 簡単に Insider ビルドを使い始めて、HoloLens の次の主要なオペレーティング システムの更新プログラムに対する貴重なフィードバックをご提供いただけます。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 11/10/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: cb8ac3b6b74fd6998cde4d32df12dcbd84556597
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162949"
---
# <span data-ttu-id="9f245-103">Microsoft HoloLens の Insider Preview</span><span class="sxs-lookup"><span data-stu-id="9f245-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="9f245-104">HoloLens 用の最新の Insider Preview ビルドへようこそ!</span><span class="sxs-lookup"><span data-stu-id="9f245-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="9f245-105">HoloLens 向けの次の主要オペレーティングシステム更新プログラムについては、簡単に [作業を開始](hololens-insider.md#start-receiving-insider-builds) して、貴重なフィードバックを提供していただくことができます。</span><span class="sxs-lookup"><span data-stu-id="9f245-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <span data-ttu-id="9f245-106">Windows Insider リリース ノート</span><span class="sxs-lookup"><span data-stu-id="9f245-106">Windows Insider Release Notes</span></span>

### <span data-ttu-id="9f245-107">アプリインストーラーを使用して HoloLens 2 にアプリをインストールする</span><span class="sxs-lookup"><span data-stu-id="9f245-107">Install Apps on HoloLens 2 via App Installer</span></span>
<span data-ttu-id="9f245-108">Windows ホログラフィック、バージョン20H2 の更新プログラムをインストールした後、すぐにアプリのインストーラー機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="9f245-108">We will ship the app installer capability soon after our Windows Holographic, version 20H2 update.</span></span> <span data-ttu-id="9f245-109">お客様が HoloLens 2 デバイスで **シームレスにアプリケーションをインストールできるように、新しい機能 (アプリのインストーラー) を追加** しています。</span><span class="sxs-lookup"><span data-stu-id="9f245-109">We are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="9f245-110">この機能は、 **非管理対象デバイスでは既定でオンに**なります。</span><span class="sxs-lookup"><span data-stu-id="9f245-110">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="9f245-111">この時点では、企業が中断されないように、アプリインストーラーを **管理対象デバイスで利用できなく** なります。</span><span class="sxs-lookup"><span data-stu-id="9f245-111">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="9f245-112">以下の **いずれか** に該当する場合、デバイスは "管理されています" と見なされます。</span><span class="sxs-lookup"><span data-stu-id="9f245-112">A device is considered “managed” if **any** of the following are true:</span></span>
- <span data-ttu-id="9f245-113">MDM[登録](hololens-enroll-mdm.md)済み</span><span class="sxs-lookup"><span data-stu-id="9f245-113">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="9f245-114">[プロビジョニングパッケージ](hololens-provisioning.md)で構成されている</span><span class="sxs-lookup"><span data-stu-id="9f245-114">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="9f245-115">ユーザー [id](hololens-identity.md) は AAD です</span><span class="sxs-lookup"><span data-stu-id="9f245-115">User [Identity](hololens-identity.md) is AAD</span></span>

<span data-ttu-id="9f245-116">開発者モードを有効にしたり、Device Portal を使用したりしなくても、アプリをインストールできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9f245-116">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="9f245-117">Appx バンドルをデバイスにダウンロード (USB 経由またはエッジ経由) するだけで、インストールを開始するように促すメッセージが表示されるように、ファイルエクスプローラーで Appx バンドルに移動できます。</span><span class="sxs-lookup"><span data-stu-id="9f245-117">Simply download (over USB or through Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="9f245-118">または、 [web ページからインストールを開始](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)します。</span><span class="sxs-lookup"><span data-stu-id="9f245-118">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="9f245-119">Microsoft Store またはサイドローディングで MDM の LOB アプリの展開機能を使用してインストールしたアプリと同様に、アプリを展開するには、アプリを展開する前に、アプリをインストールする前に、 [サインインツール](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) を使ってデジタル署名する必要があります。また、署名に使用する証明書は、HoloLens デバイスで [信頼される必要があり](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) ます</span><span class="sxs-lookup"><span data-stu-id="9f245-119">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

**<span data-ttu-id="9f245-120">アプリケーションのインストール手順。</span><span class="sxs-lookup"><span data-stu-id="9f245-120">Application install instructions.</span></span>**

1.  <span data-ttu-id="9f245-121">デバイスが管理されていると見なされないようにします。</span><span class="sxs-lookup"><span data-stu-id="9f245-121">Ensure that your device is not considered managed</span></span>
1.  <span data-ttu-id="9f245-122">HoloLens 2 デバイスの電源が入っていて、PC に接続されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="9f245-122">Ensure that your HoloLens 2 device is powered on and connected to your PC</span></span>
1.  <span data-ttu-id="9f245-123">HoloLens 2 デバイスにサインインしていることを確認する</span><span class="sxs-lookup"><span data-stu-id="9f245-123">Ensure that you are signed into the HoloLens 2 device</span></span>
1.  <span data-ttu-id="9f245-124">PC でカスタムアプリに移動し、yourapp を yourdevicename\Internal Storage\Downloads. にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9f245-124">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>   <span data-ttu-id="9f245-125">ファイルのコピーが完了したら、デバイスを切断することができます。</span><span class="sxs-lookup"><span data-stu-id="9f245-125">After you’ve finished copying your file you can disconnect your device</span></span>
1.  <span data-ttu-id="9f245-126">HoloLens 2 デバイスから [スタート] メニューを開き、[すべてのアプリ] を選択して、エクスプローラーアプリを起動します。</span><span class="sxs-lookup"><span data-stu-id="9f245-126">From your HoloLens 2 device Open the Start Menu, select All apps and launch the File Explorer app.</span></span>
1.  <span data-ttu-id="9f245-127">[ダウンロード] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="9f245-127">Navigate to the Downloads folder.</span></span> <span data-ttu-id="9f245-128">アプリの左側のパネルで、[このデバイス] を選択してから、[ダウンロード] に移動することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9f245-128">You may need to on the left panel of the app select This device first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="9f245-129">Yourapp ファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="9f245-129">Select the yourapp.appxbundle file.</span></span>
1.  <span data-ttu-id="9f245-130">アプリのインストーラーが起動します。</span><span class="sxs-lookup"><span data-stu-id="9f245-130">The App Installer will launch.</span></span> <span data-ttu-id="9f245-131">アプリをインストールするには、[インストール] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="9f245-131">Select the Install button to install your app.</span></span>
<span data-ttu-id="9f245-132">インストールされたアプリは、インストールの完了時に自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="9f245-132">The installed app will automatically launch upon completion of installation.</span></span>

<span data-ttu-id="9f245-133">このフローをテストするには、 [Windows Universal Sample GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) のサンプルアプリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f245-133">You can find sample apps on [Windows Universal Samples GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) to test this flow.</span></span>

<span data-ttu-id="9f245-134">[アプリインストーラーで HoloLens 2 にアプリをインストールする](app-deploy-app-installer.md)方法については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f245-134">Read about the full process of [installing apps on HoloLens 2 with the App Installer](app-deploy-app-installer.md).</span></span>  

![App Installer による MRTK の例のインストール](images/hololens-app-installer-picture.jpg)

## <span data-ttu-id="9f245-136">Insider ビルドの受信の開始</span><span class="sxs-lookup"><span data-stu-id="9f245-136">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="9f245-137">最近更新していない場合は、デバイスを再起動して、状態を更新し、最新のビルドを取得してください。</span><span class="sxs-lookup"><span data-stu-id="9f245-137">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="9f245-138">"デバイスの再起動" 音声コマンドは適切に動作します。</span><span class="sxs-lookup"><span data-stu-id="9f245-138">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="9f245-139">[設定] または [Windows Insider Program] で [再起動] を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="9f245-139">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="9f245-140">バックエンドに、発生した可能性のあるバグがありました。これで、この問題が報告されます。</span><span class="sxs-lookup"><span data-stu-id="9f245-140">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="9f245-141">HoloLens 2 デバイスで、**[設定]** > **[更新とセキュリティ]** > **[Windows Insider Program]** の順に移動し、**[開始する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f245-141">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="9f245-142">Windows Insider として登録するために使用したアカウントをリンクします。</span><span class="sxs-lookup"><span data-stu-id="9f245-142">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="9f245-143">Windows insider がチャネルに移動するようになりました。</span><span class="sxs-lookup"><span data-stu-id="9f245-143">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="9f245-144">**ファスト**リングは**Dev チャネル**になります。**スロー**リングは**ベータチャネル**になり、 **release preview** ring は**リリースプレビューチャネル**になります。</span><span class="sxs-lookup"><span data-stu-id="9f245-144">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="9f245-145">マッピングの外観は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9f245-145">Here is what that mapping looks like:</span></span>

![Windows Insider チャネルの説明](images/WindowsInsiderChannels.png)

<span data-ttu-id="9f245-147">詳細については、「windows のブログに [Windows Insider チャネルを導入](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f245-147">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>

<span data-ttu-id="9f245-148">次に、[ **Windows のアクティブな開発**] を選択し、 **開発者チャネル** または **ベータチャネル** のビルドを受け取るかどうかを選択して、プログラムの利用規約を確認します。</span><span class="sxs-lookup"><span data-stu-id="9f245-148">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="9f245-149">[確認] を選択し、[ **今すぐ再起動 >** ます。] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9f245-149">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="9f245-150">デバイスが再起動したら、[設定] に移動して **& セキュリティ > 更新** プログラムを確認し > 最新のビルドを入手します。</span><span class="sxs-lookup"><span data-stu-id="9f245-150">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

## <span data-ttu-id="9f245-151">FFU のダウンロードとフラッシュの手順</span><span class="sxs-lookup"><span data-stu-id="9f245-151">FFU download and flash directions</span></span>
<span data-ttu-id="9f245-152">フライト署名のある FFU でテストするには、フライト署名のある FFU をフラッシュする前にデバイスのフライト ロックを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f245-152">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="9f245-153">PC の場合:</span><span class="sxs-lookup"><span data-stu-id="9f245-153">On PC:</span></span>

    1. <span data-ttu-id="9f245-154">から PC に ffu をダウンロード [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) してください。</span><span class="sxs-lookup"><span data-stu-id="9f245-154">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="9f245-155">Microsoft Store ([https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)) から ARC (Advanced Recovery Companion) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="9f245-155">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span></span>
    
1. <span data-ttu-id="9f245-156">HoloLens でのロック解除:**設定**の  >  **更新 & セキュリティ**  >  **Windows Insider プログラム**を開くと、次にサインアップして、デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="9f245-156">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="9f245-157">Flash FFU-「ARC」を使って、フライト署名された FFU を点滅させることができます。</span><span class="sxs-lookup"><span data-stu-id="9f245-157">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

## <span data-ttu-id="9f245-158">フィードバックを提供し、問題を報告する</span><span class="sxs-lookup"><span data-stu-id="9f245-158">Provide feedback and report issues</span></span>

<span data-ttu-id="9f245-159">HoloLens で[フィードバック Hub アプリ](hololens-feedback.md)を使用してフィードバックを提供し、問題を報告することができます。</span><span class="sxs-lookup"><span data-stu-id="9f245-159">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="9f245-160">フィードバック Hub を使用すると、エンジニアが問題を迅速にデバッグして解決するのに役立つすべての必要な診断情報が含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="9f245-160">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="9f245-161">中国語および日本語版の HoloLens に関する問題は、同じ方法で報告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f245-161">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="9f245-162">フィードバック Hub を使用してドキュメント フォルダーにアクセスするかどうかを確認するプロンプトに必ず同意してください (メッセージが表示されたら **[はい]** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="9f245-162">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="9f245-163">開発者向けの注意事項</span><span class="sxs-lookup"><span data-stu-id="9f245-163">Note for developers</span></span>

<span data-ttu-id="9f245-164">HoloLens の Insider ビルドを使用して自由にアプリケーションを開発してみることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9f245-164">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="9f245-165">作業を始めるには、[HoloLens 開発者向けドキュメント](https://developer.microsoft.com/windows/mixed-reality/development)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9f245-165">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="9f245-166">これらの同じ手順は HoloLens の Insider ビルドでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f245-166">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="9f245-167">HoloLens 開発用に使用しているものと同じビルドの Unity と Visual Studio を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f245-167">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <span data-ttu-id="9f245-168">Insider ビルドの受信の停止</span><span class="sxs-lookup"><span data-stu-id="9f245-168">Stop receiving Insider builds</span></span>

<span data-ttu-id="9f245-169">Windows Holographic の Insider ビルドを受け取りたくない場合は、HoloLens が製品版ビルドを実行しているときにオプトアウトすることができます。または、Advanced Recovery Companion を使用して[デバイスを回復](hololens-recovery.md)し、Windows Holographic の Insider バージョン以外にデバイスを回復することができます。</span><span class="sxs-lookup"><span data-stu-id="9f245-169">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="9f245-170">新しいプレビュー ビルドを手動で再インストールした後に Insider Preview ビルドの登録を解除すると、ブルー スクリーンが発生するという既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="9f245-170">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="9f245-171">その後、手動でデバイスを回復する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f245-171">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="9f245-172">影響を受けるかどうかの詳細については、この[既知の問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)の詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9f245-172">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="9f245-173">HoloLens が製品版ビルドを実行していることを確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9f245-173">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="9f245-174">**[設定] > [システム] > [バージョン情報]** の順に移動し、ビルド番号を探します。</span><span class="sxs-lookup"><span data-stu-id="9f245-174">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="9f245-175">[製品のビルド番号については、リリースノートを参照してください](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="9f245-175">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="9f245-176">Insider ビルドをオプトアウトするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9f245-176">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="9f245-177">製品版ビルドを実行している HoloLens で、**[設定] > [更新とセキュリティ] > [Windows Insider Program]** に移動して、**[Insider Preview ビルドの停止]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f245-177">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="9f245-178">画面の指示に従って、デバイスでの受信を停止します。</span><span class="sxs-lookup"><span data-stu-id="9f245-178">Follow the instructions to opt out your device.</span></span>
