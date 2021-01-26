---
title: HoloLens でファイルを検索して保存する
description: HoloLens のエクスプローラーを使用して、Mixed Reality デバイス上のファイルを開き、表示、管理する方法について説明します。
keywords: 使い方, ファイル ピッカー, ファイル, 写真, ビデオ, 画像, OneDrive, ストレージ, エクスプローラー, hololens
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
ms.openlocfilehash: 2d979b2cffd20589ddef7f11db5c7206eaea23cb
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283528"
---
# <span data-ttu-id="73514-104">HoloLens でファイルを検索し、開いて保存する</span><span class="sxs-lookup"><span data-stu-id="73514-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="73514-105">写真やビデオなど、HoloLens で作成したファイルは、HoloLens デバイスに直接保存されます。</span><span class="sxs-lookup"><span data-stu-id="73514-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="73514-106">Windows 10 でファイルを管理するのと同じ方法でファイルを表示および管理します。</span><span class="sxs-lookup"><span data-stu-id="73514-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="73514-107">エクスプローラー アプリを使ってローカル フォルダーにアクセスする。</span><span class="sxs-lookup"><span data-stu-id="73514-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="73514-108">アプリのストレージ内。</span><span class="sxs-lookup"><span data-stu-id="73514-108">Within an app's storage.</span></span>
- <span data-ttu-id="73514-109">特別なフォルダー (ビデオや音楽ライブラリなど) 内。</span><span class="sxs-lookup"><span data-stu-id="73514-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="73514-110">アプリとファイル ピッカー (OneDrive など) を含むストレージ サービスの使用。</span><span class="sxs-lookup"><span data-stu-id="73514-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="73514-111">USB ケーブルを使用して HoloLens に接続されたデスクトップ PC を使い、MTP (メディア転送プロトコル) サポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="73514-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <span data-ttu-id="73514-112">エクスプローラーを使用して HoloLens 上のファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="73514-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="73514-113">[HoloLens 用の Windows 10 April 2018 Update (RS4)](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)の現在、すべての HoloLens 2 デバイスと HoloLens (第 1 世代) に適用されます。</span><span class="sxs-lookup"><span data-stu-id="73514-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="73514-114">HoloLens のエクスプローラーを使って、3D オブジェクト、ドキュメント、画像など、デバイス上のファイルを表示および管理します。</span><span class="sxs-lookup"><span data-stu-id="73514-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="73514-115">[すべてのアプリ**を**   >  **起動]**   >  **エクスプローラーに移動して**開始します。</span><span class="sxs-lookup"><span data-stu-id="73514-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="73514-116">エクスプローラーに一覧表示されるファイルがない場合は、左上のウィンドウで **[このデバイス** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="73514-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="73514-117">エクスプローラーにファイルが表示されなかっていない場合は、"最近使用した" フィルターがアクティブである可能性があります (左側のウィンドウで時計アイコンが強調表示されています)。</span><span class="sxs-lookup"><span data-stu-id="73514-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="73514-118">これを修正するには、左側の\*\*\*\* ウィンドウ (時計アイコンの下) で [このデバイス ドキュメント] アイコンを選択するか、メニューを開いて [このデバイス]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="73514-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <span data-ttu-id="73514-119">写真とビデオを検索して表示する</span><span class="sxs-lookup"><span data-stu-id="73514-119">Find and view your photos and videos</span></span>

<span data-ttu-id="73514-120">[Mixed Reality キャプチャを](holographic-photos-and-videos.md) 使うと、HoloLens で Mixed Reality の写真やビデオを撮影できます。</span><span class="sxs-lookup"><span data-stu-id="73514-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="73514-121">これらの写真とビデオは、デバイスのカメラ ロール フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="73514-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="73514-122">HoloLens で撮影した写真やビデオには、次の方法でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="73514-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="73514-123">フォト アプリを通じてカメラ ロールに [直接アクセスする](holographic-photos-and-videos.md)。</span><span class="sxs-lookup"><span data-stu-id="73514-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="73514-124">写真とビデオを OneDrive に同期して、写真やビデオをクラウド ストレージにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="73514-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="73514-125">Using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span><span class="sxs-lookup"><span data-stu-id="73514-125">using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <span data-ttu-id="73514-126">フォト アプリ</span><span class="sxs-lookup"><span data-stu-id="73514-126">Photos app</span></span>

<span data-ttu-id="73514-127">フォト アプリはスタート メニューの既定のアプリ\*\*\*\* の 1 つで、HoloLens に組み込されています。</span><span class="sxs-lookup"><span data-stu-id="73514-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="73514-128">フォト アプリを使 [ってコンテンツを表示する方法について詳しくは、以下をご覧ください](holographic-photos-and-videos.md)。</span><span class="sxs-lookup"><span data-stu-id="73514-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="73514-129">Microsoft Store から [OneDrive アプリ](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) をインストールして、写真を他のデバイスと同期することもできます。</span><span class="sxs-lookup"><span data-stu-id="73514-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <span data-ttu-id="73514-130">OneDrive アプリ</span><span class="sxs-lookup"><span data-stu-id="73514-130">OneDrive app</span></span>

<span data-ttu-id="73514-131">[OneDrive を](https://onedrive.live.com/) 使用すると、写真やビデオにアクセスし、管理し、任意のデバイスやユーザーと共有できます。</span><span class="sxs-lookup"><span data-stu-id="73514-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="73514-132">HoloLens でキャプチャした写真やビデオにアクセスするには、HoloLens の Microsoft Store から [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) アプリをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="73514-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="73514-133">ダウンロードしたら、OneDrive アプリを開き、[**カメラ**の設定のアップロード] を選択し、[  >  \*\*\*\* カメラのアップロード]**をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="73514-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <span data-ttu-id="73514-134">PC に接続する</span><span class="sxs-lookup"><span data-stu-id="73514-134">Connect to a PC</span></span>

<span data-ttu-id="73514-135">HoloLens で Windows [10 April 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) 更新プログラム以降を実行している場合は、USB ケーブルを使って MTP (メディア転送プロトコル) を使ってデバイス上の写真やビデオを参照することにより、HoloLens を Windows 10 PC に接続できます。</span><span class="sxs-lookup"><span data-stu-id="73514-135">If your HoloLens is running the [Windows 10 April 2018 update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="73514-136">デバイスに PIN またはパスワードが設定されている場合は、ファイルを参照するためにデバイスのロックが解除されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73514-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="73514-137">[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)を有効にしている場合は、それを使ってデバイスに保存されている写真やビデオを参照、取得、管理できます。</span><span class="sxs-lookup"><span data-stu-id="73514-137">If you have enabled the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <span data-ttu-id="73514-138">アプリ内のファイルにアクセスする</span><span class="sxs-lookup"><span data-stu-id="73514-138">Access files within an app</span></span>

<span data-ttu-id="73514-139">アプリケーションがデバイスにファイルを保存する場合は、そのアプリケーションを使用してファイルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="73514-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <span data-ttu-id="73514-140">別のアプリからファイルを要求する</span><span class="sxs-lookup"><span data-stu-id="73514-140">Requesting files from another app</span></span>

<span data-ttu-id="73514-141">アプリケーションは、ファイル ピッカーを使用して、ファイルを保存するか、別のアプリからファイル [を開くことを要求できます](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)。</span><span class="sxs-lookup"><span data-stu-id="73514-141">An application can request to save a file or open a file from another app by using [file pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span></span>

### <span data-ttu-id="73514-142">既知のフォルダー</span><span class="sxs-lookup"><span data-stu-id="73514-142">Known folders</span></span>

<span data-ttu-id="73514-143">HoloLens は、アプリがアクセス許可 [を要求](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) できる多くの既知のフォルダーをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="73514-143">HoloLens supports a number of [known folders](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <span data-ttu-id="73514-144">PC で HoloLens ファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="73514-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="73514-145">他のモバイル デバイスと同様に、MTP (メディア転送プロトコル) を使って HoloLens をデスクトップ PC に接続し、PC でエクスプローラーを開いて HoloLens ライブラリにアクセスして簡単に転送できます。</span><span class="sxs-lookup"><span data-stu-id="73514-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="73514-146">PC のエクスプローラーで HoloLens ファイルを表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="73514-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="73514-147">HoloLens にサインインし、HoloLens に付属の USB ケーブルを使って PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="73514-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="73514-148">[ **デバイスを開く**] を選択してエクスプローラーでファイルを表示するか、PC でエクスプローラーを開いてデバイスに移動します。</span><span class="sxs-lookup"><span data-stu-id="73514-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="73514-149">HoloLens に関する情報を表示するには、PC のエクスプローラーでデバイス名を右クリックし、[プロパティ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="73514-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="73514-150">HoloLens (第 1 世代) では、外部ハード ドライブまたは SD カードへの接続はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="73514-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <span data-ttu-id="73514-151">クラウドへの同期</span><span class="sxs-lookup"><span data-stu-id="73514-151">Sync to the cloud</span></span>

<span data-ttu-id="73514-152">写真などのファイルを HoloLens からクラウドに同期するには、HoloLens に OneDrive をインストールしてセットアップします。</span><span class="sxs-lookup"><span data-stu-id="73514-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="73514-153">OneDrive を取得するには、HoloLens の Microsoft Store で OneDrive を検索します。</span><span class="sxs-lookup"><span data-stu-id="73514-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="73514-154">HoloLens はアプリのファイルとデータをバックアップしないので、重要なファイルを OneDrive に保存すると良い方法です。</span><span class="sxs-lookup"><span data-stu-id="73514-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="73514-155">そうすることで、デバイスをリセットしたり、アプリをアンインストールしたりすると、情報がバックアップされます。</span><span class="sxs-lookup"><span data-stu-id="73514-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
