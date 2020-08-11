---
title: HoloLens でファイルを検索して保存する
description: HoloLens でエクスプローラーを使用して、デバイス上のファイルを表示および管理する
keywords: 使い方、ファイルピッカー、ファイル、写真、ビデオ、画像、OneDrive、ストレージ、エクスプローラー、hololens
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
ms.openlocfilehash: fb3287f0a074eddeac0c7ee2871e289b93eafcac
ms.sourcegitcommit: 8b56f4b9b5f9c928fc361f18efcbea729055a0b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "10919128"
---
# <span data-ttu-id="a21da-104">HoloLens でファイルを検索し、開いて保存する</span><span class="sxs-lookup"><span data-stu-id="a21da-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="a21da-105">お客様が、写真や動画などの HoloLens で作成したファイルは、HoloLens デバイスに直接保存されます。</span><span class="sxs-lookup"><span data-stu-id="a21da-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="a21da-106">Windows 10 でファイルを管理する場合と同じ方法で、ファイルを表示して管理します。</span><span class="sxs-lookup"><span data-stu-id="a21da-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="a21da-107">ファイルエクスプローラーアプリを使ってローカルフォルダーにアクセスする。</span><span class="sxs-lookup"><span data-stu-id="a21da-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="a21da-108">アプリのストレージ内。</span><span class="sxs-lookup"><span data-stu-id="a21da-108">Within an app's storage.</span></span>
- <span data-ttu-id="a21da-109">特別なフォルダー (ビデオライブラリや音楽ライブラリなど)</span><span class="sxs-lookup"><span data-stu-id="a21da-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="a21da-110">アプリとファイルピッカー (OneDrive など) を含む記憶域サービスの使用。</span><span class="sxs-lookup"><span data-stu-id="a21da-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="a21da-111">MTP (メディア転送プロトコル) を使用した USB ケーブルを使って HoloLens に接続されたデスクトップ PC を使用する。</span><span class="sxs-lookup"><span data-stu-id="a21da-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <span data-ttu-id="a21da-112">エクスプローラーを使用して HoloLens でファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="a21da-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="a21da-113">[Hololens の Windows 10 4 月2018更新プログラム (RS4)](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)の際に、すべての hololens 2 デバイスと hololens (第1世代) に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a21da-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="a21da-114">HoloLens でエクスプローラーを使用して、3D オブジェクト、ドキュメント、画像など、デバイス上のファイルを表示して管理します。</span><span class="sxs-lookup"><span data-stu-id="a21da-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="a21da-115">**Start**   >  開始するには、[すべての**アプリ**を起動するエクスプローラーを開始する」を参照   >  **File Explorer**してください。</span><span class="sxs-lookup"><span data-stu-id="a21da-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="a21da-116">エクスプローラーにファイルが表示されていない場合は、左上のウィンドウで [**このデバイス**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a21da-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="a21da-117">エクスプローラーにファイルが表示されない場合、"最近" フィルターがアクティブになっている可能性があります (左側のウィンドウで時計アイコンが強調表示されています)。</span><span class="sxs-lookup"><span data-stu-id="a21da-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="a21da-118">この問題を解決するには、左側のウィンドウで [**このデバイス**ドキュメント] アイコンを選択するか (時計アイコンの下)、メニューを開いて [**このデバイス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a21da-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <span data-ttu-id="a21da-119">写真やビデオを検索して表示する</span><span class="sxs-lookup"><span data-stu-id="a21da-119">Find and view your photos and videos</span></span>

<span data-ttu-id="a21da-120">[Mixed reality キャプチャ](holographic-photos-and-videos.md)では、HoloLens 上で mixed reality 写真とビデオを利用できます。</span><span class="sxs-lookup"><span data-stu-id="a21da-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="a21da-121">これらの写真とビデオは、デバイスのカメラロールフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="a21da-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="a21da-122">HoloLens で撮影した写真やビデオには、次の方法でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a21da-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="a21da-123">[フォトアプリ](holographic-photos-and-videos.md)から直接カメラロールにアクセスする。</span><span class="sxs-lookup"><span data-stu-id="a21da-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="a21da-124">写真やビデオを OneDrive に同期することによって、写真やビデオをクラウドストレージにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="a21da-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="a21da-125">[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)の Mixed Reality キャプチャページを使用します。</span><span class="sxs-lookup"><span data-stu-id="a21da-125">using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <span data-ttu-id="a21da-126">フォト アプリ</span><span class="sxs-lookup"><span data-stu-id="a21da-126">Photos app</span></span>

<span data-ttu-id="a21da-127">Photos アプリは、[**スタート**] メニューの既定のアプリの1つであり、HoloLens と共に組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="a21da-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="a21da-128">詳細について[は、「写真アプリを使用してコンテンツを表示する](holographic-photos-and-videos.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21da-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="a21da-129">また、Microsoft ストアから[OneDrive アプリ](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3)をインストールして、他のデバイスと写真を同期することもできます。</span><span class="sxs-lookup"><span data-stu-id="a21da-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <span data-ttu-id="a21da-130">OneDrive アプリ</span><span class="sxs-lookup"><span data-stu-id="a21da-130">OneDrive app</span></span>

<span data-ttu-id="a21da-131">[OneDrive](https://onedrive.live.com/)を使用すると、任意のデバイスと任意のユーザーとの写真やビデオへのアクセス、管理、共有を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a21da-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="a21da-132">HoloLens でキャプチャされた写真やビデオにアクセスするには、HoloLens で Microsoft Store から[OneDrive アプリ](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a21da-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="a21da-133">ダウンロードが完了したら、OneDrive アプリを**Settings**開き、[  >  **カメラアップロード**の設定] を選択して、[**カメラアップロード**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="a21da-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <span data-ttu-id="a21da-134">PC に接続する</span><span class="sxs-lookup"><span data-stu-id="a21da-134">Connect to a PC</span></span>

<span data-ttu-id="a21da-135">HoloLens で[2018 年4月の更新プログラム](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)以降を実行している場合は、USB ケーブルを使用して WINDOWS 10 PC に hololens を接続し、MTP (メディア転送プロトコル) を使ってデバイス上の写真やビデオを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="a21da-135">If your HoloLens is running the [Windows 10 April 2018 update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="a21da-136">デバイスで PIN またはパスワードを設定している場合は、ファイルを参照するためにデバイスのロックが解除されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a21da-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="a21da-137">[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)を有効にしている場合は、それを使って、デバイスに保存されている写真やビデオの参照、取得、管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a21da-137">If you have enabled the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <span data-ttu-id="a21da-138">アプリ内のファイルにアクセスする</span><span class="sxs-lookup"><span data-stu-id="a21da-138">Access files within an app</span></span>

<span data-ttu-id="a21da-139">アプリケーションでデバイスにファイルが保存されている場合は、そのアプリケーションを使用してファイルにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="a21da-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <span data-ttu-id="a21da-140">他のアプリからファイルを要求する</span><span class="sxs-lookup"><span data-stu-id="a21da-140">Requesting files from another app</span></span>

<span data-ttu-id="a21da-141">アプリケーションは、[ファイルピッカー](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)を使用して、ファイルを保存するか、別のアプリからファイルを開くように要求することができます。</span><span class="sxs-lookup"><span data-stu-id="a21da-141">An application can request to save a file or open a file from another app by using [file pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span></span>

### <span data-ttu-id="a21da-142">既知のフォルダー</span><span class="sxs-lookup"><span data-stu-id="a21da-142">Known folders</span></span>

<span data-ttu-id="a21da-143">HoloLens は、アプリがアクセス許可を要求できる[既知のフォルダー](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders)の数をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a21da-143">HoloLens supports a number of [known folders](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <span data-ttu-id="a21da-144">PC で HoloLens ファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="a21da-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="a21da-145">他のモバイルデバイスと同様に、MTP (メディア転送プロトコル) を使って HoloLens をデスクトップ PC に接続し、PC でエクスプローラーを開いて、簡単に転送できるように HoloLens ライブラリにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a21da-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="a21da-146">PC のエクスプローラーで HoloLens ファイルを表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a21da-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="a21da-147">HoloLens にサインインし、HoloLens に付属の USB ケーブルを使って PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="a21da-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="a21da-148">[デバイスを開く] を選択し**て、エクスプローラーでファイルを表示する**か、PC でエクスプローラーを開いてデバイスに移動します。</span><span class="sxs-lookup"><span data-stu-id="a21da-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="a21da-149">HoloLens に関する情報を表示するには、PC のエクスプローラーでデバイス名を右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a21da-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="a21da-150">HoloLens (第1世代) では、外部ハードドライブまたは SD カードへの接続をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a21da-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <span data-ttu-id="a21da-151">クラウドとの同期</span><span class="sxs-lookup"><span data-stu-id="a21da-151">Sync to the cloud</span></span>

<span data-ttu-id="a21da-152">HoloLens からクラウドに写真やその他のファイルを同期するには、HoloLens で OneDrive をインストールしてセットアップします。</span><span class="sxs-lookup"><span data-stu-id="a21da-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="a21da-153">OneDrive を取得するには、HoloLens で Microsoft Store で検索します。</span><span class="sxs-lookup"><span data-stu-id="a21da-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="a21da-154">HoloLens では、アプリのファイルやデータはバックアップされないため、重要な情報を OneDrive に保存することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a21da-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="a21da-155">こうすることで、デバイスをリセットしたり、アプリをアンインストールしたりすると、情報がバックアップされます。</span><span class="sxs-lookup"><span data-stu-id="a21da-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
