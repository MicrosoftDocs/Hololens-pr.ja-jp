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
ms.openlocfilehash: b12079142049cce28ec00803ad0a1f8dc92333e1
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163123"
---
# <span data-ttu-id="405b2-103">Windows Defender アプリケーション制御 - WDAC</span><span class="sxs-lookup"><span data-stu-id="405b2-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="405b2-104">WDAC は、IT 管理者がデバイス上のアプリの起動をブロックするようにデバイスを構成することを可能にします。</span><span class="sxs-lookup"><span data-stu-id="405b2-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="405b2-105">これは、キオスクモードなどのデバイス制限のメソッドとは異なり、デバイス上のアプリを非表示にする UI がユーザーに表示されますが、起動することはできます。</span><span class="sxs-lookup"><span data-stu-id="405b2-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="405b2-106">WDAC が実装されている間も、アプリは [すべてのアプリ] の一覧に表示されますが、WDAC では、デバイスユーザーがアプリとプロセスを起動することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="405b2-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="405b2-107">デバイスに複数の WDAC ポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="405b2-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="405b2-108">システムに複数の WDAC ポリシーが設定されている場合、最も制限の厳しいポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="405b2-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="405b2-109">HoloLens でブロックされているアプリをエンドユーザーが起動しようとすると、そのアプリを起動できないという通知が表示されません。</span><span class="sxs-lookup"><span data-stu-id="405b2-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="405b2-110">次に示すのは、 [WDAC と Windows PowerShell を使用して、Microsoft Intune との HoloLens 2 デバイスでアプリを許可またはブロックする](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)方法についてのガイドです。</span><span class="sxs-lookup"><span data-stu-id="405b2-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="405b2-111">ユーザーが最初の例の手順を使用して、Windows 10 PC にインストールされたアプリを検索するときに、結果を絞り込むためにいくつかの操作を行う必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="405b2-111">When users search for apps installed on their Windows 10 PC using the first example step they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="405b2-112">パッケージの完全な名前がわからない場合は、' Add-appxpackage-name \ \* YourBestGuess \ \* ' を数回実行して、検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="405b2-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="405b2-113">名前を指定したら、' $package 1 = Get-AppxPackage PackageName '</span><span class="sxs-lookup"><span data-stu-id="405b2-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="405b2-114">たとえば、Edge で次のように実行すると、複数の結果が返されますが、その一覧から必要な氏名が MicrosoftEdge であることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="405b2-114">For example running the following for Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span> 

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="405b2-115">HoloLens 上のアプリのパッケージファミリ名</span><span class="sxs-lookup"><span data-stu-id="405b2-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="405b2-116">上記のガイドでは、newPolicy.xml を手動で編集し、HoloLens にインストールされているパッケージファミリ名を持つアプリケーションのルールを追加できます。</span><span class="sxs-lookup"><span data-stu-id="405b2-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications which are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="405b2-117">場合によっては、ポリシーに追加する必要があるデスクトップ PC 以外のアプリを使うことがあります。</span><span class="sxs-lookup"><span data-stu-id="405b2-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span> 

<span data-ttu-id="405b2-118">以下は、HoloLens 2 デバイス用の一般的に使用されるアプリと In-Box アプリの一覧です。</span><span class="sxs-lookup"><span data-stu-id="405b2-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="405b2-119">アプリ名</span><span class="sxs-lookup"><span data-stu-id="405b2-119">App Name</span></span>                   | <span data-ttu-id="405b2-120">パッケージファミリ名</span><span class="sxs-lookup"><span data-stu-id="405b2-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="405b2-121">3D ビューアー</span><span class="sxs-lookup"><span data-stu-id="405b2-121">3D Viewer</span></span>                  | <span data-ttu-id="405b2-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="405b2-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="405b2-123">アプリ インストーラー</span><span class="sxs-lookup"><span data-stu-id="405b2-123">App Installer</span></span>              | <span data-ttu-id="405b2-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</span><span class="sxs-lookup"><span data-stu-id="405b2-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</span></span></sup>         |
| <span data-ttu-id="405b2-125">カレンダー</span><span class="sxs-lookup"><span data-stu-id="405b2-125">Calendar</span></span>                   | <span data-ttu-id="405b2-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="405b2-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="405b2-127">カメラ</span><span class="sxs-lookup"><span data-stu-id="405b2-127">Camera</span></span>                     | <span data-ttu-id="405b2-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="405b2-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="405b2-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="405b2-129">Cortana</span></span>                    | <span data-ttu-id="405b2-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="405b2-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="405b2-131">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="405b2-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="405b2-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="405b2-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="405b2-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="405b2-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="405b2-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="405b2-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="405b2-135">フィードバック Hub</span><span class="sxs-lookup"><span data-stu-id="405b2-135">Feedback Hub</span></span>               | <span data-ttu-id="405b2-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="405b2-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="405b2-137">エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="405b2-137">File Explorer</span></span>              | <span data-ttu-id="405b2-138">c5e2524a-ea46-4f67-84 1f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="405b2-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="405b2-139">メール</span><span class="sxs-lookup"><span data-stu-id="405b2-139">Mail</span></span>                       | <span data-ttu-id="405b2-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="405b2-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="405b2-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="405b2-141">Microsoft Store</span></span>            | <span data-ttu-id="405b2-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="405b2-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="405b2-143">映画 & テレビ</span><span class="sxs-lookup"><span data-stu-id="405b2-143">Movies & TV</span></span>                | <span data-ttu-id="405b2-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="405b2-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="405b2-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="405b2-145">OneDrive</span></span>                   | <span data-ttu-id="405b2-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="405b2-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="405b2-147">フォト</span><span class="sxs-lookup"><span data-stu-id="405b2-147">Photos</span></span>                     | <span data-ttu-id="405b2-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="405b2-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="405b2-149">設定</span><span class="sxs-lookup"><span data-stu-id="405b2-149">Settings</span></span>                   | <span data-ttu-id="405b2-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="405b2-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="405b2-151">ヒント</span><span class="sxs-lookup"><span data-stu-id="405b2-151">Tips</span></span>                       | <span data-ttu-id="405b2-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="405b2-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="405b2-153">1-アプリのインストーラーアプリがブロックされるのは、Microsoft Store や MDM ソリューションなどの他のソースからインストールされたアプリではなく、アプリのインストーラーアプリのみです。</span><span class="sxs-lookup"><span data-stu-id="405b2-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <span data-ttu-id="405b2-154">パッケージファミリ名を検索する方法</span><span class="sxs-lookup"><span data-stu-id="405b2-154">How to find a Package Family Name</span></span>

<span data-ttu-id="405b2-155">アプリがこの一覧に表示されていない場合は、デバイスポータルを使用して、ブロックする必要があるアプリをインストールしている HoloLens 2 に接続して、PackageRelativeID を判断し、その名前から「パッケージ Efamilyname」を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="405b2-155">If an app is not on this list then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="405b2-156">HoloLens 2 デバイスにアプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="405b2-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="405b2-157">開発者向け > & > 更新プログラムを開き、 **開発者モード** と **Device portal**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="405b2-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="405b2-158">詳細について [は、「device portal のセットアップと使用の](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)詳細」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="405b2-158">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="405b2-159">Device Portal が接続されたら、[ **ビュー** ]、[ **アプリ**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="405b2-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="405b2-160">[インストールされているアプリ] パネルで、ドロップダウンを使ってインストールされているアプリを選びます。</span><span class="sxs-lookup"><span data-stu-id="405b2-160">Within the Installed Apps panel use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="405b2-161">PackageRelativeID を見つけます。</span><span class="sxs-lookup"><span data-stu-id="405b2-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="405b2-162">の前にアプリの文字をコピーします。これは、パッケージの名前になります。</span><span class="sxs-lookup"><span data-stu-id="405b2-162">Copy app characters before the !, this will be your PackageFamilyName.</span></span>


