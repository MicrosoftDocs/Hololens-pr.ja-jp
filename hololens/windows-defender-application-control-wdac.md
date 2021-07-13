---
title: Windows Defender アプリケーション制御 - WDAC
description: Windows Defender アプリケーション制御の概要と、それを使用して HoloLens mixed reality デバイスを管理する方法について説明します。
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
ms.openlocfilehash: a27a16913873c5245f734dbe084eb2b7ed007c20
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639932"
---
# <a name="windows-defender-application-control---wdac"></a><span data-ttu-id="0f9ba-103">Windows Defender アプリケーション制御 - WDAC</span><span class="sxs-lookup"><span data-stu-id="0f9ba-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="0f9ba-104">WDAC を使用すると、IT 管理者は、デバイスでのアプリの起動をブロックするようにデバイスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="0f9ba-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="0f9ba-105">これは、キオスクモードなどのデバイス制限の方法とは異なり、デバイス上のアプリを非表示にする UI がユーザーに表示されますが、それでも起動できます。</span><span class="sxs-lookup"><span data-stu-id="0f9ba-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="0f9ba-106">WDAC が実装されている場合でも、アプリはすべてのアプリの一覧に表示されますが、WDAC はデバイスユーザーがこれらのアプリとプロセスを起動できなくなります。</span><span class="sxs-lookup"><span data-stu-id="0f9ba-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="0f9ba-107">1つのデバイスに複数の WDAC ポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="0f9ba-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="0f9ba-108">システムに複数の WDAC ポリシーが設定されている場合、最も制限の厳しいポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="0f9ba-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="0f9ba-109">エンドユーザーが、WDAC によってブロックされているアプリを起動しようとすると、HoloLens、そのアプリを起動できないという通知は表示されません。</span><span class="sxs-lookup"><span data-stu-id="0f9ba-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="0f9ba-110">次に、ユーザーが[Microsoft Intune で HoloLens 2 デバイス上のアプリを許可またはブロックするために、WDAC と Windows PowerShell を使用](/mem/intune/configuration/custom-profile-hololens)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0f9ba-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="0f9ba-111">最初の例の手順を使用して Windows 10 PC にインストールされているアプリをユーザーが検索する場合、結果を絞り込むためにいくつかの試行が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="0f9ba-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="0f9ba-112">パッケージの完全な名前がわからない場合は、' Get-appxpackage-name \* YourBestGuess ' を何回か実行しなければならないことがあり \* ます。</span><span class="sxs-lookup"><span data-stu-id="0f9ba-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="0f9ba-113">名前を指定すると、' $package 1 = Get-AppxPackage-name PackageName ' という名前になります。</span><span class="sxs-lookup"><span data-stu-id="0f9ba-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="0f9ba-114">たとえば、次の Microsoft Edge を実行すると複数の結果が返されますが、その一覧からは、必要な完全な名前が MicrosoftEdge であることを識別できます。</span><span class="sxs-lookup"><span data-stu-id="0f9ba-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a><span data-ttu-id="0f9ba-115">HoloLens 上のアプリのパッケージファミリ名</span><span class="sxs-lookup"><span data-stu-id="0f9ba-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="0f9ba-116">上記のガイドでは、newPolicy.xml を手動で編集し、HoloLens にのみインストールされるアプリケーションのパッケージファミリ名と共に規則を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="0f9ba-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="0f9ba-117">場合によっては、ポリシーに追加するデスクトップ PC 上にないアプリが使用されることがあります。</span><span class="sxs-lookup"><span data-stu-id="0f9ba-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="0f9ba-118">HoloLens 2 デバイス用の一般的に使用されるアプリと In-Box アプリの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0f9ba-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="0f9ba-119">アプリ名</span><span class="sxs-lookup"><span data-stu-id="0f9ba-119">App Name</span></span>                   | <span data-ttu-id="0f9ba-120">パッケージ ファミリ名</span><span class="sxs-lookup"><span data-stu-id="0f9ba-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="0f9ba-121">3D ビューアー</span><span class="sxs-lookup"><span data-stu-id="0f9ba-121">3D Viewer</span></span>                  | <span data-ttu-id="0f9ba-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="0f9ba-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="0f9ba-123">アプリ インストーラー</span><span class="sxs-lookup"><span data-stu-id="0f9ba-123">App Installer</span></span>              | <span data-ttu-id="0f9ba-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0f9ba-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span></span>         |
| <span data-ttu-id="0f9ba-125">Calendar</span><span class="sxs-lookup"><span data-stu-id="0f9ba-125">Calendar</span></span>                   | <span data-ttu-id="0f9ba-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="0f9ba-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="0f9ba-127">カメラ</span><span class="sxs-lookup"><span data-stu-id="0f9ba-127">Camera</span></span>                     | <span data-ttu-id="0f9ba-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="0f9ba-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="0f9ba-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="0f9ba-129">Cortana</span></span>                    | <span data-ttu-id="0f9ba-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="0f9ba-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="0f9ba-131">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="0f9ba-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="0f9ba-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="0f9ba-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="0f9ba-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="0f9ba-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="0f9ba-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="0f9ba-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="0f9ba-135">フィードバック Hub</span><span class="sxs-lookup"><span data-stu-id="0f9ba-135">Feedback Hub</span></span>               | <span data-ttu-id="0f9ba-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="0f9ba-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="0f9ba-137">エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="0f9ba-137">File Explorer</span></span>              | <span data-ttu-id="0f9ba-138">c5e2524a-ea46-4f67-84 1f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="0f9ba-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="0f9ba-139">Mail</span><span class="sxs-lookup"><span data-stu-id="0f9ba-139">Mail</span></span>                       | <span data-ttu-id="0f9ba-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="0f9ba-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="0f9ba-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="0f9ba-141">Microsoft Store</span></span>            | <span data-ttu-id="0f9ba-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="0f9ba-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="0f9ba-143">映画 & テレビ</span><span class="sxs-lookup"><span data-stu-id="0f9ba-143">Movies & TV</span></span>                | <span data-ttu-id="0f9ba-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="0f9ba-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="0f9ba-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="0f9ba-145">OneDrive</span></span>                   | <span data-ttu-id="0f9ba-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="0f9ba-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="0f9ba-147">Photos</span><span class="sxs-lookup"><span data-stu-id="0f9ba-147">Photos</span></span>                     | <span data-ttu-id="0f9ba-148">エクスプローラー.Windows。Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="0f9ba-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="0f9ba-149">設定</span><span class="sxs-lookup"><span data-stu-id="0f9ba-149">Settings</span></span>                   | <span data-ttu-id="0f9ba-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="0f9ba-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="0f9ba-151">ヒント</span><span class="sxs-lookup"><span data-stu-id="0f9ba-151">Tips</span></span>                       | <span data-ttu-id="0f9ba-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="0f9ba-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="0f9ba-153">1-ブロックしているアプリのインストーラーは、アプリインストーラーアプリをブロックするだけで、Microsoft Store などの他のソースや MDM ソリューションからインストールされたアプリはブロックしません。</span><span class="sxs-lookup"><span data-stu-id="0f9ba-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <a name="how-to-find-a-package-family-name"></a><span data-ttu-id="0f9ba-154">パッケージファミリ名を検索する方法</span><span class="sxs-lookup"><span data-stu-id="0f9ba-154">How to find a Package Family Name</span></span>

<span data-ttu-id="0f9ba-155">アプリがこの一覧にない場合、ユーザーはデバイスポータルを使用して、ブロックするアプリがインストールされている HoloLens 2 に接続することで、PackageRelativeID を特定し、その中にパッケージ化 efamilyname を取得できます。</span><span class="sxs-lookup"><span data-stu-id="0f9ba-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="0f9ba-156">HoloLens 2 デバイスにアプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="0f9ba-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="0f9ba-157">開発者のために設定-> 更新プログラム & セキュリティ-> を開き、**開発者モード** と **デバイスポータル** を有効にします。</span><span class="sxs-lookup"><span data-stu-id="0f9ba-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="0f9ba-158">詳細について [は、こちらのデバイスポータルのセットアップと使用](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f9ba-158">More more details instructions read more about [setup and use of device portal here](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="0f9ba-159">デバイスポータルが接続されたら、[ **ビュー** ]、[ **アプリ**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="0f9ba-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="0f9ba-160">[インストールされているアプリ] パネルで、ドロップダウンを使用して、インストールされているアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="0f9ba-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="0f9ba-161">PackageRelativeID を見つけます。</span><span class="sxs-lookup"><span data-stu-id="0f9ba-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="0f9ba-162">の前にアプリ文字をコピーします。これらの文字は、整理 Efamilyname になります。</span><span class="sxs-lookup"><span data-stu-id="0f9ba-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


