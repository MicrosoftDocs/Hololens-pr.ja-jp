---
title: HoloLens でファイルを検索して保存する
description: HoloLens でファイルエクスプローラーを使用して、mixed reality デバイス上のファイルを開いて表示し、管理する方法について説明します。
keywords: 方法, ファイルピッカー, ファイル, 写真, ビデオ, 画像, OneDrive, ストレージ, ファイルエクスプローラー, hololens
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309185"
---
# <a name="find-open-and-save-files-on-hololens"></a>HoloLens でファイルを検索して開き、保存する

HoloLens で作成したファイル (写真やビデオを含む) は、HoloLens デバイスに直接保存されます。 Windows 10 でファイルを管理するのと同じ方法で、それらを表示して管理します。

- ファイルエクスプローラーアプリを使用してローカルフォルダーにアクセスする。
- アプリのストレージ内。
- 特別なフォルダー (ビデオや音楽ライブラリなど)。
- アプリとファイルピッカー (OneDrive など) を含むストレージサービスを使用する。
- USB ケーブルを使用して HoloLens に接続されているデスクトップ PC を使用する (MTP (Media Transfer Protocol) のサポート)。

## <a name="view-files-on-hololens-using-file-explorer"></a>ファイルエクスプローラーを使用して HoloLens のファイルを表示する

> Hololens [用の Windows 10 April 2018 Update (RS4)](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)の時点で、すべての hololens 2 デバイスと hololens (第1世代) に適用されます。

HoloLens のファイルエクスプローラーを使用して、3D オブジェクト、ドキュメント、画像など、デバイス上のファイルを表示および管理します。 開始するには、[すべてのアプリの **起動**] [エクスプローラー] に移動   >     >  します。

> [!TIP]
> ファイルエクスプローラーにファイルが表示されていない場合は、左上のウィンドウで [ **このデバイス** ] を選択します。

ファイルエクスプローラーにファイルが表示されない場合は、"最近" のフィルターがアクティブになっている可能性があります (時計のアイコンは左のウィンドウで強調表示されています)。 この問題を解決するには、左側のウィンドウ (時計のアイコンの下) で **このデバイス** ドキュメントアイコンを選択するか、メニューを開いて [ **このデバイス**] を選択します。

## <a name="find-and-view-your-photos-and-videos"></a>写真やビデオを検索して表示する

[Mixed reality キャプチャ](holographic-photos-and-videos.md) を使用すると、HoloLens で mixed reality の写真とビデオを取得できます。  これらの写真とビデオは、デバイスのカメラロールフォルダーに保存されます。

HoloLens で撮影した写真やビデオには、次の方法でアクセスできます。

- カメラのロールへのアクセスは、 [写真アプリ](holographic-photos-and-videos.md)から直接行うことができます。
- 写真やビデオを OneDrive に同期して、写真やビデオをクラウドの記憶域にアップロードします。
- [Windows デバイスポータル](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)の [Mixed Reality Capture] ページを使用します。

### <a name="photos-app"></a>フォト アプリ

Photos アプリは、[ **スタート** ] メニューの既定のアプリの1つであり、HoloLens が組み込まれています。 [写真アプリを使用してコンテンツを表示する](holographic-photos-and-videos.md)方法について説明します。

Microsoft Store から [OneDrive アプリ](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) をインストールして、写真を他のデバイスと同期させることもできます。

### <a name="onedrive-app"></a>OneDrive アプリ

[OneDrive](https://onedrive.live.com/) では、任意のデバイスと任意のユーザーとの写真やビデオのアクセス、管理、共有を行うことができます。 HoloLens でキャプチャされた写真やビデオにアクセスするには、HoloLens の Microsoft Store から [OneDrive アプリ](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) をダウンロードします。 ダウンロードしたら、OneDrive アプリを開き、[**設定**] [カメラのアップロード] の順に選択し、[  >  **カメラのアップロード**] をオンにします。

### <a name="connect-to-a-pc"></a>PC に接続する

HoloLens で [windows 10 April 2018 update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) 以降を実行している場合は、USB ケーブルを使用して WINDOWS 10 PC に hololens を接続し、MTP (media transfer protocol) を使用してデバイス上の写真とビデオを参照することができます。 デバイスに PIN またはパスワードを設定している場合は、ファイルを参照するためにデバイスのロックが解除されていることを確認する必要があります。  

[Windows デバイスポータル](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)を有効にしている場合は、デバイスに保存されている写真やビデオを参照、取得、および管理するために使用できます。

## <a name="access-files-within-an-app"></a>アプリ内のファイルにアクセスする

アプリケーションがデバイスにファイルを保存する場合、そのアプリケーションを使用してファイルにアクセスできます。

### <a name="requesting-files-from-another-app"></a>別のアプリからのファイルの要求

アプリケーションは、ファイル [ピッカー](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)を使用して、ファイルを保存したり、別のアプリからファイルを開いたりするように要求できます。

### <a name="known-folders"></a>既知のフォルダー

HoloLens では、アプリがアクセス許可を要求できる [既知のフォルダー](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) がいくつかサポートされています。

## <a name="view-hololens-files-on-your-pc"></a>PC での HoloLens ファイルの表示

他のモバイルデバイスと同様に、HoloLens (Media Transfer Protocol) を使用して HoloLens をデスクトップ PC に接続し、PC でファイルエクスプローラーを開いて、簡単に転送できるように HoloLens ライブラリにアクセスします。

PC のファイルエクスプローラーで HoloLens ファイルを表示するには、次のようにします。

1. HoloLens にサインインし、HoloLens に付属の USB ケーブルを使用して PC に接続します。

1. [デバイスを開く] を選択し **てファイルエクスプローラーでファイルを表示する** か、PC のエクスプローラーを開き、デバイスに移動します。

HoloLens に関する情報を表示するには、PC のエクスプローラーでデバイス名を右クリックし、[ **プロパティ**] を選択します。

> [!NOTE]
> HoloLens (第1世代) では、外部ハードドライブまたは SD カードへの接続はサポートされていません。

## <a name="sync-to-the-cloud"></a>クラウドへの同期

HoloLens からクラウドに写真やその他のファイルを同期するには、HoloLens に OneDrive をインストールしてセットアップします。 OneDrive を取得するには、HoloLens の Microsoft Store で検索します。

HoloLens では、アプリファイルとデータはバックアップされないため、重要なものを OneDrive に保存することをお勧めします。 このようにして、デバイスをリセットしたり、アプリをアンインストールしたりすると、情報がバックアップされます。
