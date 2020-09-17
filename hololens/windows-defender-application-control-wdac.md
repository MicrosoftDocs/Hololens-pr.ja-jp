---
title: Windows Defender アプリケーションコントロール-WDAC
description: WDAC の概要と、HoloLens デバイスを管理するための使い方について説明します。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d1147b202d3b575fa1f2dd20f620005c786ea9fc
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016790"
---
# <span data-ttu-id="50c0e-103">Windows Defender アプリケーションコントロール-WDAC</span><span class="sxs-lookup"><span data-stu-id="50c0e-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="50c0e-104">WDAC は、IT 管理者がデバイス上のアプリの起動をブロックするようにデバイスを構成することを可能にします。</span><span class="sxs-lookup"><span data-stu-id="50c0e-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="50c0e-105">これは、キオスクモードなどのデバイス制限のメソッドとは異なり、デバイス上のアプリを非表示にする UI がユーザーに表示されますが、起動することはできます。</span><span class="sxs-lookup"><span data-stu-id="50c0e-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="50c0e-106">WDAC が実装されている間も、アプリは [すべてのアプリ] の一覧に表示されますが、WDAC では、デバイスユーザーがアプリとプロセスを起動することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="50c0e-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

> [!NOTE]
> <span data-ttu-id="50c0e-107">HoloLens でブロックされているアプリをエンドユーザーが起動しようとすると、そのアプリを起動できないという通知が表示されません。</span><span class="sxs-lookup"><span data-stu-id="50c0e-107">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="50c0e-108">次に示すのは、 [WDAC と Windows PowerShell を使用して、Microsoft Intune との HoloLens 2 デバイスでアプリを許可またはブロックする](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)方法についてのガイドです。</span><span class="sxs-lookup"><span data-stu-id="50c0e-108">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="50c0e-109">ユーザーが最初の例の手順を使用して、Windows 10 PC にインストールされたアプリを検索するときに、結果を絞り込むためにいくつかの操作を行う必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="50c0e-109">When users search for apps installed on their Windows 10 PC using the first example step they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="50c0e-110">パッケージの完全な名前がわからない場合は、' Add-appxpackage-name \ \* YourBestGuess \ \* ' を数回実行して、検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50c0e-110">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="50c0e-111">名前として「$package 1」と入力し、「Add-appxpackage-PackageName」という名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="50c0e-111">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="50c0e-112">たとえば、Edge で次のように実行すると、複数の結果が返されますが、その一覧から必要な氏名が MicrosoftEdge であることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="50c0e-112">For example running the following for Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span> 

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="50c0e-113">HoloLens 上のアプリのパッケージファミリ名</span><span class="sxs-lookup"><span data-stu-id="50c0e-113">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="50c0e-114">上記のガイドでは、newPolicy.xml を手動で編集し、HoloLens にインストールされているパッケージファミリ名を持つアプリケーションのルールを追加できます。</span><span class="sxs-lookup"><span data-stu-id="50c0e-114">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications which are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="50c0e-115">場合によっては、ポリシーに追加する必要があるデスクトップ PC 以外のアプリを使うことがあります。</span><span class="sxs-lookup"><span data-stu-id="50c0e-115">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span> 

<span data-ttu-id="50c0e-116">以下は、HoloLens 2 デバイスで一般的に使用されるアプリとインボックスアプリの一覧です。</span><span class="sxs-lookup"><span data-stu-id="50c0e-116">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="50c0e-117">アプリ名</span><span class="sxs-lookup"><span data-stu-id="50c0e-117">App Name</span></span>                   | <span data-ttu-id="50c0e-118">パッケージファミリ名</span><span class="sxs-lookup"><span data-stu-id="50c0e-118">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="50c0e-119">3D ビューアー</span><span class="sxs-lookup"><span data-stu-id="50c0e-119">3D Viewer</span></span>                  | <span data-ttu-id="50c0e-120">Microsoft. Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="50c0e-120">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="50c0e-121">カレンダー</span><span class="sxs-lookup"><span data-stu-id="50c0e-121">Calendar</span></span>                   | <span data-ttu-id="50c0e-122">microsoft. windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="50c0e-122">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="50c0e-123">カメラ</span><span class="sxs-lookup"><span data-stu-id="50c0e-123">Camera</span></span>                     | <span data-ttu-id="50c0e-124">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="50c0e-124">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="50c0e-125">Cortana</span><span class="sxs-lookup"><span data-stu-id="50c0e-125">Cortana</span></span>                    | <span data-ttu-id="50c0e-126">Microsoft. 549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="50c0e-126">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="50c0e-127">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="50c0e-127">Dynamics 365 Guides</span></span>        | <span data-ttu-id="50c0e-128">Guides_8wekyb3d8bbwe Dynamics365</span><span class="sxs-lookup"><span data-stu-id="50c0e-128">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="50c0e-129">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="50c0e-129">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="50c0e-130">Microsoft. MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="50c0e-130">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="50c0e-131">フィードバック Hub</span><span class="sxs-lookup"><span data-stu-id="50c0e-131">Feedback Hub</span></span>               | <span data-ttu-id="50c0e-132">Microsoft. WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="50c0e-132">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="50c0e-133">エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="50c0e-133">File Explorer</span></span>              | <span data-ttu-id="50c0e-134">c5e2524a-ea46-4f67-84 1f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="50c0e-134">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="50c0e-135">メール</span><span class="sxs-lookup"><span data-stu-id="50c0e-135">Mail</span></span>                       | <span data-ttu-id="50c0e-136">microsoft. windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="50c0e-136">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="50c0e-137">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="50c0e-137">Microsoft Store</span></span>            | <span data-ttu-id="50c0e-138">Microsoft. WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="50c0e-138">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="50c0e-139">映画 & テレビ</span><span class="sxs-lookup"><span data-stu-id="50c0e-139">Movies & TV</span></span>                | <span data-ttu-id="50c0e-140">Microsoft. ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="50c0e-140">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="50c0e-141">OneDrive</span><span class="sxs-lookup"><span data-stu-id="50c0e-141">OneDrive</span></span>                   | <span data-ttu-id="50c0e-142">microsoft. microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="50c0e-142">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="50c0e-143">フォト</span><span class="sxs-lookup"><span data-stu-id="50c0e-143">Photos</span></span>                     | <span data-ttu-id="50c0e-144">Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="50c0e-144">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="50c0e-145">設定</span><span class="sxs-lookup"><span data-stu-id="50c0e-145">Settings</span></span>                   | <span data-ttu-id="50c0e-146">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="50c0e-146">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="50c0e-147">ヒント</span><span class="sxs-lookup"><span data-stu-id="50c0e-147">Tips</span></span>                       | <span data-ttu-id="50c0e-148">Microsoft. HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="50c0e-148">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

<span data-ttu-id="50c0e-149">アプリがこの一覧に表示されていない場合は、デバイスポータルを使用して、ブロックする必要があるアプリをインストールしている HoloLens 2 に接続して、PackageRelativeID を判断し、その名前から「パッケージ Efamilyname」を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="50c0e-149">If an app is not on this list then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="50c0e-150">HoloLens 2 デバイスにアプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="50c0e-150">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="50c0e-151">開発者のために設定を開いて & > > 更新を開き、 **開発者モード** と **Device portal**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="50c0e-151">Open Settings -> Updates & Securtiy -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="50c0e-152">詳細について [は、「device portal のセットアップと使用の](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)詳細」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50c0e-152">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="50c0e-153">Device Portal が接続されたら、[ **ビュー** ]、[ **アプリ**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="50c0e-153">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="50c0e-154">[インストールされているアプリ] パネルで、ドロップダウンを使ってインストールされているアプリを選びます。</span><span class="sxs-lookup"><span data-stu-id="50c0e-154">Within the Installed Apps panel use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="50c0e-155">PackageRelativeID を見つけます。</span><span class="sxs-lookup"><span data-stu-id="50c0e-155">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="50c0e-156">の前にアプリの文字をコピーします。これは、パッケージの名前になります。</span><span class="sxs-lookup"><span data-stu-id="50c0e-156">Copy app characters before the !, this will be your PackageFamilyName.</span></span>

