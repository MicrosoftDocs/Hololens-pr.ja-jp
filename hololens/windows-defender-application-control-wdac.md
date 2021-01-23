---
title: Windows Defender アプリケーション制御 - WDAC
description: アプリケーション コントロールWindows Defender概要と、それを使って HoloLens Mixed Reality デバイスを管理する方法について説明します。
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
ms.openlocfilehash: 23c9a274387424e8f084a4729ee621e130820716
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284138"
---
# <span data-ttu-id="da364-103">Windows Defender アプリケーション制御 - WDAC</span><span class="sxs-lookup"><span data-stu-id="da364-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="da364-104">WDAC を使うと、IT 管理者はデバイス上のアプリの起動をブロックするデバイスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="da364-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="da364-105">これは、キオスク モードなどのデバイス制限の方法とは異なります。キオスク モードでは、ユーザーにデバイス上のアプリを非表示にする UI が表示されますが、起動は可能です。</span><span class="sxs-lookup"><span data-stu-id="da364-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="da364-106">WDAC が実装されている間、アプリは [すべてのアプリ] の一覧に表示されますが、WDAC はそれらのアプリとプロセスをデバイス ユーザーが起動できないのを停止します。</span><span class="sxs-lookup"><span data-stu-id="da364-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="da364-107">1 つのデバイスに複数の WDAC ポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="da364-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="da364-108">システムに複数の WDAC ポリシーが設定されている場合、最も制限の厳しいポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="da364-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="da364-109">エンド ユーザーが WDAC によってブロックされているアプリを起動しようとすると、HoloLens では、そのアプリを起動できないという通知は表示されません。</span><span class="sxs-lookup"><span data-stu-id="da364-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="da364-110">Microsoft Intune で [HoloLens 2](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)デバイス上のアプリを許可またはブロックするために WDAC と Windows PowerShell を使用する方法について説明するガイドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="da364-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="da364-111">ユーザーが最初の例の手順を使って Windows 10 PC にインストールされているアプリを検索する場合、結果を絞り込むには、いくつかの試行が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="da364-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="da364-112">パッケージの完全な名前が分からない場合は、'Get-AppxPackage -name \*YourBestGuess\*' を数回実行して検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da364-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="da364-113">名前を実行すると、'$package 1 = Get-AppxPackage -name Actual.PackageName' が実行されます。</span><span class="sxs-lookup"><span data-stu-id="da364-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="da364-114">たとえば、Microsoft Edge で次のコマンドを実行すると、複数の結果が返されますが、その一覧から、必要な完全な名前が Microsoft.MicrosoftEdge である必要があります。</span><span class="sxs-lookup"><span data-stu-id="da364-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="da364-115">HoloLens 上のアプリのパッケージ ファミリ名</span><span class="sxs-lookup"><span data-stu-id="da364-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="da364-116">上記のガイドでは、HoloLens にのみインストールされているアプリケーションのnewPolicy.xmlを手動で編集し、パッケージ ファミリ名で規則を追加できます。</span><span class="sxs-lookup"><span data-stu-id="da364-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="da364-117">場合によっては、ポリシーに追加するデスクトップ PC にはないアプリを使う場合があります。</span><span class="sxs-lookup"><span data-stu-id="da364-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="da364-118">HoloLens 2 デバイス用の一般的In-Boxアプリの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="da364-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="da364-119">アプリ名</span><span class="sxs-lookup"><span data-stu-id="da364-119">App Name</span></span>                   | <span data-ttu-id="da364-120">パッケージ ファミリ名</span><span class="sxs-lookup"><span data-stu-id="da364-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="da364-121">3D ビューアー</span><span class="sxs-lookup"><span data-stu-id="da364-121">3D Viewer</span></span>                  | <span data-ttu-id="da364-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="da364-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="da364-123">アプリ インストーラー</span><span class="sxs-lookup"><span data-stu-id="da364-123">App Installer</span></span>              | <span data-ttu-id="da364-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</span><span class="sxs-lookup"><span data-stu-id="da364-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</span></span></sup>         |
| <span data-ttu-id="da364-125">カレンダー</span><span class="sxs-lookup"><span data-stu-id="da364-125">Calendar</span></span>                   | <span data-ttu-id="da364-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="da364-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="da364-127">カメラ</span><span class="sxs-lookup"><span data-stu-id="da364-127">Camera</span></span>                     | <span data-ttu-id="da364-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="da364-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="da364-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="da364-129">Cortana</span></span>                    | <span data-ttu-id="da364-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="da364-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="da364-131">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="da364-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="da364-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="da364-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="da364-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="da364-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="da364-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="da364-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="da364-135">フィードバック Hub</span><span class="sxs-lookup"><span data-stu-id="da364-135">Feedback Hub</span></span>               | <span data-ttu-id="da364-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="da364-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="da364-137">エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="da364-137">File Explorer</span></span>              | <span data-ttu-id="da364-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="da364-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="da364-139">メール</span><span class="sxs-lookup"><span data-stu-id="da364-139">Mail</span></span>                       | <span data-ttu-id="da364-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="da364-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="da364-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="da364-141">Microsoft Store</span></span>            | <span data-ttu-id="da364-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="da364-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="da364-143">映画 & テレビ</span><span class="sxs-lookup"><span data-stu-id="da364-143">Movies & TV</span></span>                | <span data-ttu-id="da364-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="da364-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="da364-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="da364-145">OneDrive</span></span>                   | <span data-ttu-id="da364-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="da364-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="da364-147">フォト</span><span class="sxs-lookup"><span data-stu-id="da364-147">Photos</span></span>                     | <span data-ttu-id="da364-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="da364-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="da364-149">設定</span><span class="sxs-lookup"><span data-stu-id="da364-149">Settings</span></span>                   | <span data-ttu-id="da364-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="da364-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="da364-151">ヒント</span><span class="sxs-lookup"><span data-stu-id="da364-151">Tips</span></span>                       | <span data-ttu-id="da364-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="da364-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="da364-153">1 - アプリ インストーラーをブロックすると、アプリ インストーラー アプリだけがブロックされ、Microsoft Store などの他のソースや MDM ソリューションからインストールされたアプリはブロックされません。</span><span class="sxs-lookup"><span data-stu-id="da364-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <span data-ttu-id="da364-154">パッケージ ファミリ名を見つける方法</span><span class="sxs-lookup"><span data-stu-id="da364-154">How to find a Package Family Name</span></span>

<span data-ttu-id="da364-155">アプリがこの一覧に表示されていない場合、ユーザーは Device Portal を使って、アプリをインストールした HoloLens 2 に接続し、ブロックする必要がある場合に PackageRelativeID を特定し、そこから PackageFamilyName を取得できます。</span><span class="sxs-lookup"><span data-stu-id="da364-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="da364-156">HoloLens 2 デバイスにアプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="da364-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="da364-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span><span class="sxs-lookup"><span data-stu-id="da364-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="da364-158">詳しくは、デバイス ポータルのセットアップと使用 [に関する詳細をご覧ください](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="da364-158">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="da364-159">Device Portal に接続したら、[ビュー] の [ **アプリ]** に **移動します**。</span><span class="sxs-lookup"><span data-stu-id="da364-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="da364-160">[インストールされたアプリ] パネルで、ドロップダウンを使用してインストール済みアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="da364-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="da364-161">PackageRelativeID を探します。</span><span class="sxs-lookup"><span data-stu-id="da364-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="da364-162">!の前にアプリの文字をコピーします。これらの文字は PackageFamilyName になります。</span><span class="sxs-lookup"><span data-stu-id="da364-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


