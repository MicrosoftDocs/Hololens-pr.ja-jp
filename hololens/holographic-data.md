---
title: ファイルを検索して保存HoloLens
description: Mixed Reality デバイス上のエクスプローラーをHoloLensしてファイルを開き、表示、管理する方法について説明します。
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
ms.openlocfilehash: ad210c9d31d8d7c226345618b6dfabf8457ee2398882935920d7b3217259a644
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664878"
---
# <a name="find-open-and-save-files-on-hololens"></a>HoloLens でファイルを検索し、開いて保存する

写真やビデオなどHoloLens作成したファイルは、デバイスに直接HoloLensされます。 次の手順でファイルを管理するのと同じ方法で、それらを表示Windows 10。

- アプリを使用エクスプローラーローカル フォルダーにアクセスします。
- アプリのストレージ内。
- 特殊なフォルダー (ビデオや音楽ライブラリなど) 内。
- アプリとファイル ピッカーを含むストレージ サービスを使用する (OneDrive)。
- MTP (メディア転送プロトコル) サポートHoloLens USB ケーブルを使用して、デバイスに接続されたデスクトップ PC を使用します。

## <a name="view-files-on-hololens-using-file-explorer"></a>次のコマンドを使用してHoloLensファイルをエクスプローラー

> Windows 10 April [2018 Update (RS4)](/windows/mixed-reality/release-notes-april-2018)HoloLens の現在、すべての HoloLens 2 デバイスと HoloLens (第 1 世代) に適用されます。

3D エクスプローラー、HoloLens画像など、デバイス上のファイルを表示および管理するには、エクスプローラーを使用します。 [Start All   >  **apps]/(すべてのアプリ**   >  **のエクスプローラー** 開始する] に移動します。

> [!TIP]
> 一覧にファイルが表示エクスプローラー、左上のウィンドウで [ **このデバイス** ] を選択します。

[最近] フィルターがアクティブな場合エクスプローラーファイルが表示されません (左側のウィンドウで時計アイコンが強調表示されています)。 これを解決するには、左側のウィンドウ (時計アイコンの下) にある [This **Device** document]/(このデバイス ドキュメント)アイコンを選択するか、メニューを開いて [このデバイス] **を選択します**。

## <a name="find-and-view-your-photos-and-videos"></a>写真とビデオを検索して表示する

[Mixed Reality キャプチャを使用](holographic-photos-and-videos.md)すると、Mixed Reality の写真やビデオをビデオでHoloLens。  これらの写真とビデオは、デバイスの Camera Roll フォルダーに保存されます。

次の方法で、アプリで撮影した写真HoloLensアクセスできます。

- フォト アプリ を介してカメラ ロールに [直接アクセスする](holographic-photos-and-videos.md)。
- 写真とビデオをクラウド ストレージにアップロードするには、写真とビデオをクラウド ストレージにOneDrive。
- を使用Mixed Reality キャプチャページを使用[Windows デバイス ポータル。](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)

### <a name="photos-app"></a>フォト アプリ

Photos アプリは、[スタート] メニューの既定のアプリの 1 つであり、アプリに組み込HoloLens。 フォト アプリを使用 [してコンテンツを表示する方法の詳細については、以下を参照してください](holographic-photos-and-videos.md)。

他のデバイスと[写真を同期OneDrive、Microsoft Store](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3)アプリをインストールすることもできます。

### <a name="onedrive-app"></a>OneDrive アプリ

[OneDrive](https://onedrive.live.com/)を使用すると、写真やビデオにアクセスし、管理し、任意のデバイスと任意のユーザーと共有できます。 HoloLens でキャプチャされた写真やビデオにアクセスするには、OneDriveアプリを[](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3)Microsoft Store からダウンロードHoloLens。 ダウンロードしたら、アプリを開OneDrive、[カメラのアップロード設定] を選択し、[カメラ  >  のアップロード]**をオンにします**。

### <a name="connect-to-a-pc"></a>Connect PC への接続

HoloLens で[Windows 10 April 2018](/windows/mixed-reality/release-notes-april-2018)以降の更新プログラムを実行している場合は、USB ケーブルを使用して HoloLens を Windows 10 PC に接続し、MTP (メディア転送プロトコル) を使用してデバイス上の写真やビデオを参照できます。 デバイスに PIN またはパスワードが設定されている場合は、ファイルを参照するためにデバイスのロックが解除されている必要があります。  

を有効にしたWindows デバイス ポータル[](/windows/mixed-reality/using-the-windows-device-portal)デバイスに格納されている写真やビデオを参照、取得、管理するために使用できます。

## <a name="access-files-within-an-app"></a>アプリ内のファイルにアクセスする

アプリケーションがデバイスにファイルを保存する場合は、そのアプリケーションを使用してアクセスできます。

### <a name="requesting-files-from-another-app"></a>別のアプリからのファイルの要求

アプリケーションは、ファイル ピッカー を使用して、ファイルを保存するか、別のアプリからファイルを [開くことを要求できます](/windows/mixed-reality/app-model#file-pickers)。

### <a name="known-folders"></a>既知のフォルダー

HoloLensは、アプリがアクセス許可[を要求](/windows/mixed-reality/app-model#known-folders)できる既知のフォルダーを多数サポートしています。

## <a name="view-hololens-files-on-your-pc"></a>PC HoloLensファイルを表示する

他のモバイル デバイスと同様に、MTP (メディア転送プロトコル) を使用してデスクトップ PC に HoloLens を接続し、PC で エクスプローラー を開いて、簡単に転送するために HoloLens ライブラリにアクセスします。

PC 上の HoloLensファイルをエクスプローラーするには:

1. サインインして HoloLens、デバイスに付属の USB ケーブルを使用して PC に接続HoloLens。

1. [ **デバイスを開く] を選択して**、エクスプローラーファイルを表示するか、PC エクスプローラーを開いてデバイスに移動します。

デバイスに関する情報をHoloLens PC 上のデバイス名を右クリックしエクスプローラープロパティ] を選択 **します**。

> [!NOTE]
> HoloLens (第 1 世代) では、外部ハード ドライブまたは SD カードへの接続はサポートされていません。

## <a name="sync-to-the-cloud"></a>クラウドに同期する

写真や他のファイルを HoloLensクラウドに同期するには、OneDrive をインストールHoloLens。 この情報OneDrive、自分のページのMicrosoft Storeで検索HoloLens。

HoloLensはアプリ ファイルとデータをバックアップしないので、重要なデータをデータに保存OneDrive。 そうすることで、デバイスをリセットしたり、アプリをアンインストールしたりすると、情報がバックアップされます。
