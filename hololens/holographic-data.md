---
title: HoloLens でのファイルの検索と保存
description: HoloLens のエクスプローラーを使用して、mixed reality デバイス上でファイルを開いて表示し、管理する方法について説明します。
keywords: 操作方法、ファイルピッカー、ファイル、写真、ビデオ、画像、OneDrive、ストレージ、ファイルエクスプローラー、hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 18dc962b869dafaea9ff9c605eef51fcbb35bfb2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636182"
---
# <a name="find-open-and-save-files-on-hololens"></a><span data-ttu-id="06ac5-104">HoloLens でファイルを検索し、開いて保存する</span><span class="sxs-lookup"><span data-stu-id="06ac5-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="06ac5-105">HoloLens に作成したファイル (写真やビデオを含む) は、HoloLens デバイスに直接保存されます。</span><span class="sxs-lookup"><span data-stu-id="06ac5-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="06ac5-106">Windows 10 でファイルを管理するのと同じ方法で、それらを表示して管理します。</span><span class="sxs-lookup"><span data-stu-id="06ac5-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="06ac5-107">ファイルエクスプローラーアプリを使用してローカルフォルダーにアクセスする。</span><span class="sxs-lookup"><span data-stu-id="06ac5-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="06ac5-108">アプリのストレージ内。</span><span class="sxs-lookup"><span data-stu-id="06ac5-108">Within an app's storage.</span></span>
- <span data-ttu-id="06ac5-109">特別なフォルダー (ビデオや音楽ライブラリなど)。</span><span class="sxs-lookup"><span data-stu-id="06ac5-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="06ac5-110">アプリとファイルピッカー (OneDrive など) を含むストレージサービスを使用する。</span><span class="sxs-lookup"><span data-stu-id="06ac5-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="06ac5-111">USB ケーブルを使用して、HoloLens に接続されているデスクトップ PC を使用する (MTP (Media Transfer Protocol) のサポート)。</span><span class="sxs-lookup"><span data-stu-id="06ac5-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <a name="view-files-on-hololens-using-file-explorer"></a><span data-ttu-id="06ac5-112">エクスプローラーを使用して HoloLens でファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="06ac5-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="06ac5-113">[HoloLens の2018年4月更新 (RS4) Windows 10](/windows/mixed-reality/release-notes-april-2018)の時点で、すべての HoloLens 2 デバイスと HoloLens (第1世代) に適用されます。</span><span class="sxs-lookup"><span data-stu-id="06ac5-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="06ac5-114">HoloLens のファイルエクスプローラーを使用して、3d オブジェクト、ドキュメント、画像など、デバイス上のファイルを表示および管理します。</span><span class="sxs-lookup"><span data-stu-id="06ac5-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="06ac5-115">開始するには、[すべてのアプリの **起動**] [エクスプローラー] に移動   >     >  します。</span><span class="sxs-lookup"><span data-stu-id="06ac5-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="06ac5-116">ファイルエクスプローラーにファイルが表示されていない場合は、左上のウィンドウで [ **このデバイス** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="06ac5-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="06ac5-117">ファイルエクスプローラーにファイルが表示されない場合は、"最近" のフィルターがアクティブになっている可能性があります (時計のアイコンは左のウィンドウで強調表示されています)。</span><span class="sxs-lookup"><span data-stu-id="06ac5-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="06ac5-118">この問題を解決するには、左側のウィンドウ (時計のアイコンの下) で **このデバイス** ドキュメントアイコンを選択するか、メニューを開いて [ **このデバイス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="06ac5-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <a name="find-and-view-your-photos-and-videos"></a><span data-ttu-id="06ac5-119">写真やビデオを検索して表示する</span><span class="sxs-lookup"><span data-stu-id="06ac5-119">Find and view your photos and videos</span></span>

<span data-ttu-id="06ac5-120">[Mixed reality キャプチャ](holographic-photos-and-videos.md)を使用すると、HoloLens で mixed reality の写真とビデオを取得できます。</span><span class="sxs-lookup"><span data-stu-id="06ac5-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="06ac5-121">これらの写真とビデオは、デバイスのカメラロールフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="06ac5-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="06ac5-122">HoloLens で撮影した写真やビデオには、次の方法でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="06ac5-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="06ac5-123">カメラのロールへのアクセスは、 [写真アプリ](holographic-photos-and-videos.md)から直接行うことができます。</span><span class="sxs-lookup"><span data-stu-id="06ac5-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="06ac5-124">写真やビデオを OneDrive に同期して、写真やビデオをクラウドの記憶域にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="06ac5-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="06ac5-125">[Windows デバイスポータル](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)の [Mixed Reality Capture] ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="06ac5-125">using the Mixed Reality Capture page of the [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <a name="photos-app"></a><span data-ttu-id="06ac5-126">フォト アプリ</span><span class="sxs-lookup"><span data-stu-id="06ac5-126">Photos app</span></span>

<span data-ttu-id="06ac5-127">Photos アプリは、[**スタート**] メニューの既定のアプリの1つであり、HoloLens で組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="06ac5-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="06ac5-128">[写真アプリを使用してコンテンツを表示する](holographic-photos-and-videos.md)方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="06ac5-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="06ac5-129">また、Microsoft Store から[OneDrive アプリ](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3)をインストールして、写真を他のデバイスと同期させることもできます。</span><span class="sxs-lookup"><span data-stu-id="06ac5-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <a name="onedrive-app"></a><span data-ttu-id="06ac5-130">OneDrive アプリ</span><span class="sxs-lookup"><span data-stu-id="06ac5-130">OneDrive app</span></span>

<span data-ttu-id="06ac5-131">[OneDrive](https://onedrive.live.com/)を使用すると、任意のデバイスや任意のユーザーとの写真やビデオにアクセスしたり、管理したり、共有したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="06ac5-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="06ac5-132">HoloLens でキャプチャした写真やビデオにアクセスするには、HoloLens の Microsoft Store から[OneDrive アプリ](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="06ac5-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="06ac5-133">ダウンロードが完了したら、OneDrive アプリを開き **設定**  >  **カメラのアップロード** を選択し、**カメラのアップロード** を有効にします。</span><span class="sxs-lookup"><span data-stu-id="06ac5-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <a name="connect-to-a-pc"></a><span data-ttu-id="06ac5-134">PC への Connect</span><span class="sxs-lookup"><span data-stu-id="06ac5-134">Connect to a PC</span></span>

<span data-ttu-id="06ac5-135">HoloLens で[2018 年4月以降 Windows 10 の更新プログラム](/windows/mixed-reality/release-notes-april-2018)を実行している場合は、USB ケーブルを使用して HoloLens を Windows 10 PC に接続し、MTP (media transfer protocol) を使用してデバイス上の写真とビデオを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="06ac5-135">If your HoloLens is running the [Windows 10 April 2018 update](/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="06ac5-136">デバイスに PIN またはパスワードを設定している場合は、ファイルを参照するためにデバイスのロックが解除されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06ac5-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="06ac5-137">[Windows デバイスポータル](/windows/mixed-reality/using-the-windows-device-portal)を有効にしている場合は、デバイスに保存されている写真やビデオを参照、取得、および管理するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="06ac5-137">If you have enabled the [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <a name="access-files-within-an-app"></a><span data-ttu-id="06ac5-138">アプリ内のファイルにアクセスする</span><span class="sxs-lookup"><span data-stu-id="06ac5-138">Access files within an app</span></span>

<span data-ttu-id="06ac5-139">アプリケーションがデバイスにファイルを保存する場合、そのアプリケーションを使用してファイルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="06ac5-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <a name="requesting-files-from-another-app"></a><span data-ttu-id="06ac5-140">別のアプリからのファイルの要求</span><span class="sxs-lookup"><span data-stu-id="06ac5-140">Requesting files from another app</span></span>

<span data-ttu-id="06ac5-141">アプリケーションは、ファイル [ピッカー](/windows/mixed-reality/app-model#file-pickers)を使用して、ファイルを保存したり、別のアプリからファイルを開いたりするように要求できます。</span><span class="sxs-lookup"><span data-stu-id="06ac5-141">An application can request to save a file or open a file from another app by using [file pickers](/windows/mixed-reality/app-model#file-pickers).</span></span>

### <a name="known-folders"></a><span data-ttu-id="06ac5-142">既知のフォルダー</span><span class="sxs-lookup"><span data-stu-id="06ac5-142">Known folders</span></span>

<span data-ttu-id="06ac5-143">HoloLens では、アプリがアクセス許可を要求できる[既知のフォルダー](/windows/mixed-reality/app-model#known-folders)がいくつかサポートされています。</span><span class="sxs-lookup"><span data-stu-id="06ac5-143">HoloLens supports a number of [known folders](/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <a name="view-hololens-files-on-your-pc"></a><span data-ttu-id="06ac5-144">PC 上の HoloLens ファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="06ac5-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="06ac5-145">他のモバイルデバイスと同様に、MTP (Media Transfer Protocol) を使用してデスクトップ pc に HoloLens を接続し、PC 上でファイルエクスプローラーを開き、転送ツールで HoloLens ライブラリにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="06ac5-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="06ac5-146">PC のファイルエクスプローラーで HoloLens ファイルを表示するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="06ac5-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="06ac5-147">HoloLens にサインインし、HoloLens に付属の USB ケーブルを使用して PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="06ac5-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="06ac5-148">[デバイスを開く] を選択し **てファイルエクスプローラーでファイルを表示する** か、PC のエクスプローラーを開き、デバイスに移動します。</span><span class="sxs-lookup"><span data-stu-id="06ac5-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="06ac5-149">HoloLens に関する情報を表示するには、PC のエクスプローラーでデバイス名を右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="06ac5-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="06ac5-150">HoloLens (第1世代) では、外部ハードドライブまたは SD カードへの接続はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="06ac5-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <a name="sync-to-the-cloud"></a><span data-ttu-id="06ac5-151">クラウドへの同期</span><span class="sxs-lookup"><span data-stu-id="06ac5-151">Sync to the cloud</span></span>

<span data-ttu-id="06ac5-152">写真やその他のファイルを HoloLens からクラウドに同期するには、HoloLens に OneDrive をインストールしてセットアップします。</span><span class="sxs-lookup"><span data-stu-id="06ac5-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="06ac5-153">OneDrive を取得するには、HoloLens の Microsoft Store で検索します。</span><span class="sxs-lookup"><span data-stu-id="06ac5-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="06ac5-154">HoloLens では、アプリのファイルとデータをバックアップしません。そのため、重要な内容を OneDrive に保存することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="06ac5-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="06ac5-155">このようにして、デバイスをリセットしたり、アプリをアンインストールしたりすると、情報がバックアップされます。</span><span class="sxs-lookup"><span data-stu-id="06ac5-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
