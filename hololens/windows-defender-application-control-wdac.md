---
title: Windows Defender アプリケーション制御 - WDAC
description: WDAC の概要と、HoloLens デバイスを管理するための使い方について説明します。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: dc1deb2b159d3d41b1a1f73c33f1cd44731f8e4d
ms.sourcegitcommit: 72ae5a270f869393872eac160e43076eaa35fe4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135574"
---
# <span data-ttu-id="613b0-103">Windows Defender アプリケーション制御 - WDAC</span><span class="sxs-lookup"><span data-stu-id="613b0-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="613b0-104">WDAC は、IT 管理者がデバイス上のアプリの起動をブロックするようにデバイスを構成することを可能にします。</span><span class="sxs-lookup"><span data-stu-id="613b0-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="613b0-105">これは、キオスクモードなどのデバイス制限のメソッドとは異なり、デバイス上のアプリを非表示にする UI がユーザーに表示されますが、起動することはできます。</span><span class="sxs-lookup"><span data-stu-id="613b0-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="613b0-106">WDAC が実装されている間も、アプリは [すべてのアプリ] の一覧に表示されますが、WDAC では、デバイスユーザーがアプリとプロセスを起動することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="613b0-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

> [!NOTE]
> <span data-ttu-id="613b0-107">HoloLens でブロックされているアプリをエンドユーザーが起動しようとすると、そのアプリを起動できないという通知が表示されません。</span><span class="sxs-lookup"><span data-stu-id="613b0-107">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="613b0-108">次に示すのは、 [WDAC と Windows PowerShell を使用して、Microsoft Intune との HoloLens 2 デバイスでアプリを許可またはブロックする](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)方法についてのガイドです。</span><span class="sxs-lookup"><span data-stu-id="613b0-108">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="613b0-109">ユーザーが最初の例の手順を使用して、Windows 10 PC にインストールされたアプリを検索するときに、結果を絞り込むためにいくつかの操作を行う必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="613b0-109">When users search for apps installed on their Windows 10 PC using the first example step they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="613b0-110">パッケージの完全な名前がわからない場合は、' Add-appxpackage-name \ \* YourBestGuess \ \* ' を数回実行して、検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="613b0-110">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="613b0-111">名前を指定したら、' $package 1 = Get-AppxPackage PackageName '</span><span class="sxs-lookup"><span data-stu-id="613b0-111">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="613b0-112">たとえば、Edge で次のように実行すると、複数の結果が返されますが、その一覧から必要な氏名が MicrosoftEdge であることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="613b0-112">For example running the following for Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span> 

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="613b0-113">HoloLens 上のアプリのパッケージファミリ名</span><span class="sxs-lookup"><span data-stu-id="613b0-113">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="613b0-114">上記のガイドでは、newPolicy.xml を手動で編集し、HoloLens にインストールされているパッケージファミリ名を持つアプリケーションのルールを追加できます。</span><span class="sxs-lookup"><span data-stu-id="613b0-114">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications which are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="613b0-115">場合によっては、ポリシーに追加する必要があるデスクトップ PC 以外のアプリを使うことがあります。</span><span class="sxs-lookup"><span data-stu-id="613b0-115">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span> 

<span data-ttu-id="613b0-116">以下は、HoloLens 2 デバイス用の一般的に使用されるアプリと In-Box アプリの一覧です。</span><span class="sxs-lookup"><span data-stu-id="613b0-116">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="613b0-117">アプリ名</span><span class="sxs-lookup"><span data-stu-id="613b0-117">App Name</span></span>                   | <span data-ttu-id="613b0-118">パッケージファミリ名</span><span class="sxs-lookup"><span data-stu-id="613b0-118">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="613b0-119">3D ビューアー</span><span class="sxs-lookup"><span data-stu-id="613b0-119">3D Viewer</span></span>                  | <span data-ttu-id="613b0-120">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="613b0-120">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="613b0-121">アプリ インストーラー</span><span class="sxs-lookup"><span data-stu-id="613b0-121">App Installer</span></span>              | <span data-ttu-id="613b0-122">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</span><span class="sxs-lookup"><span data-stu-id="613b0-122">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</span></span></sup>         |
| <span data-ttu-id="613b0-123">カレンダー</span><span class="sxs-lookup"><span data-stu-id="613b0-123">Calendar</span></span>                   | <span data-ttu-id="613b0-124">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="613b0-124">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="613b0-125">カメラ</span><span class="sxs-lookup"><span data-stu-id="613b0-125">Camera</span></span>                     | <span data-ttu-id="613b0-126">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="613b0-126">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="613b0-127">Cortana</span><span class="sxs-lookup"><span data-stu-id="613b0-127">Cortana</span></span>                    | <span data-ttu-id="613b0-128">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="613b0-128">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="613b0-129">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="613b0-129">Dynamics 365 Guides</span></span>        | <span data-ttu-id="613b0-130">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="613b0-130">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="613b0-131">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="613b0-131">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="613b0-132">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="613b0-132">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="613b0-133">フィードバック Hub</span><span class="sxs-lookup"><span data-stu-id="613b0-133">Feedback Hub</span></span>               | <span data-ttu-id="613b0-134">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="613b0-134">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="613b0-135">エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="613b0-135">File Explorer</span></span>              | <span data-ttu-id="613b0-136">c5e2524a-ea46-4f67-84 1f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="613b0-136">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="613b0-137">メール</span><span class="sxs-lookup"><span data-stu-id="613b0-137">Mail</span></span>                       | <span data-ttu-id="613b0-138">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="613b0-138">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="613b0-139">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="613b0-139">Microsoft Store</span></span>            | <span data-ttu-id="613b0-140">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="613b0-140">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="613b0-141">映画 & テレビ</span><span class="sxs-lookup"><span data-stu-id="613b0-141">Movies & TV</span></span>                | <span data-ttu-id="613b0-142">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="613b0-142">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="613b0-143">OneDrive</span><span class="sxs-lookup"><span data-stu-id="613b0-143">OneDrive</span></span>                   | <span data-ttu-id="613b0-144">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="613b0-144">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="613b0-145">フォト</span><span class="sxs-lookup"><span data-stu-id="613b0-145">Photos</span></span>                     | <span data-ttu-id="613b0-146">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="613b0-146">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="613b0-147">設定</span><span class="sxs-lookup"><span data-stu-id="613b0-147">Settings</span></span>                   | <span data-ttu-id="613b0-148">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="613b0-148">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="613b0-149">ヒント</span><span class="sxs-lookup"><span data-stu-id="613b0-149">Tips</span></span>                       | <span data-ttu-id="613b0-150">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="613b0-150">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="613b0-151">1-アプリのインストーラーアプリがブロックされるのは、Microsoft Store や MDM ソリューションなどの他のソースからインストールされたアプリではなく、アプリのインストーラーアプリのみです。</span><span class="sxs-lookup"><span data-stu-id="613b0-151">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <span data-ttu-id="613b0-152">パッケージファミリ名を検索する方法</span><span class="sxs-lookup"><span data-stu-id="613b0-152">How to find a Package Family Name</span></span>

<span data-ttu-id="613b0-153">アプリがこの一覧に表示されていない場合は、デバイスポータルを使用して、ブロックする必要があるアプリをインストールしている HoloLens 2 に接続して、PackageRelativeID を判断し、その名前から「パッケージ Efamilyname」を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="613b0-153">If an app is not on this list then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="613b0-154">HoloLens 2 デバイスにアプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="613b0-154">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="613b0-155">開発者のために設定を開いて & > > 更新を開き、 **開発者モード** と **Device portal**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="613b0-155">Open Settings -> Updates & Securtiy -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="613b0-156">詳細について [は、「device portal のセットアップと使用の](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)詳細」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="613b0-156">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="613b0-157">Device Portal が接続されたら、[ **ビュー** ]、[ **アプリ**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="613b0-157">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="613b0-158">[インストールされているアプリ] パネルで、ドロップダウンを使ってインストールされているアプリを選びます。</span><span class="sxs-lookup"><span data-stu-id="613b0-158">Within the Installed Apps panel use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="613b0-159">PackageRelativeID を見つけます。</span><span class="sxs-lookup"><span data-stu-id="613b0-159">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="613b0-160">の前にアプリの文字をコピーします。これは、パッケージの名前になります。</span><span class="sxs-lookup"><span data-stu-id="613b0-160">Copy app characters before the !, this will be your PackageFamilyName.</span></span>

## <span data-ttu-id="613b0-161">アプリインストーラーの例</span><span class="sxs-lookup"><span data-stu-id="613b0-161">Sample - Blocking App Installer</span></span>

<span data-ttu-id="613b0-162">例として、 [アプリのインストーラ](app-deploy-app-installer.md) アプリをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="613b0-162">As an example you may wish to block the [App Installer](app-deploy-app-installer.md) app.</span></span> <span data-ttu-id="613b0-163">この例のサンプルコードをいくつか紹介しています。</span><span class="sxs-lookup"><span data-stu-id="613b0-163">We have included some sample code for this example.</span></span> <span data-ttu-id="613b0-164">[この例については、次のコードサンプルを](https://aka.ms/HoloLensDocs-Sample-WDAC-App-Installer)ダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="613b0-164">Please download these [code samples for this example](https://aka.ms/HoloLensDocs-Sample-WDAC-App-Installer).</span></span> <span data-ttu-id="613b0-165">Zip ファイルに次の内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="613b0-165">In the zip file you'll find:</span></span>

| <span data-ttu-id="613b0-166">ファイル</span><span class="sxs-lookup"><span data-stu-id="613b0-166">File</span></span> | <span data-ttu-id="613b0-167">使用</span><span class="sxs-lookup"><span data-stu-id="613b0-167">Use</span></span> |
|-|-|
| <span data-ttu-id="613b0-168">compiledPolicy</span><span class="sxs-lookup"><span data-stu-id="613b0-168">compiledPolicy.bin</span></span> | [<span data-ttu-id="613b0-169">手順9で作成しました。最終手順10で使用します。</span><span class="sxs-lookup"><span data-stu-id="613b0-169">Created in Step 9, used in final Step 10.</span></span>](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) |
| <span data-ttu-id="613b0-170">mergedPolicy.xml</span><span class="sxs-lookup"><span data-stu-id="613b0-170">mergedPolicy.xml</span></span> | [<span data-ttu-id="613b0-171">手順6で作成します。</span><span class="sxs-lookup"><span data-stu-id="613b0-171">Created in Step 6.</span></span>](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) |
| <span data-ttu-id="613b0-172">Syncml WDAC_Set</span><span class="sxs-lookup"><span data-stu-id="613b0-172">WDAC_Set.syncml</span></span> | <span data-ttu-id="613b0-173">WDAC では使用されませんが、 [ENTERPRISEMODERNAPPMANAGEMENT CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp)の場合に使用できます</span><span class="sxs-lookup"><span data-stu-id="613b0-173">Not used in WDAC but can be used for for [EnterpriseModernAppManagement CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp)</span></span> |

<span data-ttu-id="613b0-174">アプリをすぐにブロックする場合は、この例ではアプリインストーラアプリの場合、compiledPolicy ファイルを使用して、上記のリンクの手順10に進みます。</span><span class="sxs-lookup"><span data-stu-id="613b0-174">If you would like to try immediately blocking an app, in this case the App Installer app, then use the compiledPolicy.bin file and skip to step 10 in the link above.</span></span> <span data-ttu-id="613b0-175">これにより、カスタムポリシーをテストし、グループの割り当てとポリシーの構成が正しいことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="613b0-175">This will allow you to test out the custom policy and ensure the group assignments and policy configuration is correct.</span></span> 

<span data-ttu-id="613b0-176">アプリインストーラーをブロックするための WDAC ポリシーを上の一覧の一覧の他のアプリと組み合わせて使用したい場合は、mergedPolicy.xml ファイルを使用して、新しいポリシーを結合することができます。</span><span class="sxs-lookup"><span data-stu-id="613b0-176">If you would like to combine the WDAC policy for blocking App Installer with other apps from the list above, or any other app, then you may use the mergedPolicy.xml file and continue to merge new policies.</span></span> <span data-ttu-id="613b0-177">上で説明したように、WDAC ポリシーは付加的であるため、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="613b0-177">As stated above WDAC policies are additive so this is not required.</span></span> 

<span data-ttu-id="613b0-178">ファイルを開こうとすると、アプリのインストーラーアプリが起動されるため、プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="613b0-178">Since the App Installer app is launched via trying to open a file will be presented with a prompt.</span></span> <span data-ttu-id="613b0-179">前述したように、WDAC によってブロックされるアプリは、ブロックされていることを示すメッセージを表示しません。ただし、ユーザーはデバイス上のファイルを開こうとしているため、ファイルを開くためのエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="613b0-179">As stated above Apps blocked by WDAC do not present a prompt they are blocked, however since the user is attempting to open a file on their device they are presented with an error for opening the file.</span></span> 

![WDAC からブロックされているアプリのインストール](images\wdac-app-installer-no-launch.jpg)

<span data-ttu-id="613b0-181">WDAC を使用しない場合は、別の方法として、 [ENTERPRISEMODERNAPPMANAGEMENT CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp) を使用してアプリインストーラー UX を削除することもできます。これは、アプリがすべてのアプリです。</span><span class="sxs-lookup"><span data-stu-id="613b0-181">If you do not wish to use WDAC, you may as an alternative use [EnterpriseModernAppManagement CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp) to remove the App Installer UX, which is an app after all.</span></span> <span data-ttu-id="613b0-182">これにより、アプリのインストーラーアプリがデバイスからアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="613b0-182">The result of this is that the App Installer app will be uninstalled from the device.</span></span> <span data-ttu-id="613b0-183">.appx、msixbundle、その他のファイル拡張子、および web とアプリの起動のプロトコルは、アプリのインストーラーアプリで処理されなくなります。</span><span class="sxs-lookup"><span data-stu-id="613b0-183">.appx, .msix, .msixbundle, and other file extensions as well as protocol for web-to-app launch will no longer be handled by the App Installer app.</span></span> <span data-ttu-id="613b0-184">ユーザーは、ストア内のファイル拡張子/プロトコルのハンドラーを検索するかどうかを確認するメッセージを受け取ります。このリストにないため、アプリは見つかりません。</span><span class="sxs-lookup"><span data-stu-id="613b0-184">The user will get a prompt to search for a handler for the file extension/protocol in the store and they will not find the app because it’s not listed.</span></span>