---
title: HoloLens でファイルを検索して保存する
description: HoloLens でエクスプローラーを使用して、デバイス上のファイルを表示および管理する
keywords: HoloLens
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
ms.openlocfilehash: 50a13e1634344bea66bb6b7ce90d9e3fc8c2a783
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828559"
---
# HoloLens でファイルを検索、開く、および保存する

お客様が、写真や動画などの HoloLens で作成したファイルは、HoloLens デバイスに直接保存されます。 Windows 10 でファイルを管理する場合と同じ方法で、ファイルを表示して管理します。

- ファイルエクスプローラーアプリを使ってローカルフォルダーにアクセスする。
- アプリのストレージ内。
- 特別なフォルダー (ビデオライブラリや音楽ライブラリなど)
- アプリとファイルピッカー (OneDrive など) を含む記憶域サービスの使用。
- MTP (メディア転送プロトコル) を使用した USB ケーブルを使って HoloLens に接続されたデスクトップ PC を使用する。

## エクスプローラーを使用して HoloLens でファイルを表示する

> [Hololens の Windows 10 4 月2018更新プログラム (RS4)](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)の際に、すべての hololens 2 デバイスと hololens (第1世代) に適用されます。

HoloLens でエクスプローラーを使用して、3D オブジェクト、ドキュメント、画像など、デバイス上のファイルを表示して管理します。 **Start**   >  開始するには、[すべての**アプリ**を起動するエクスプローラーを開始する」を参照   >  **File Explorer**してください。

> [!TIP]
> エクスプローラーにファイルが表示されていない場合は、左上のウィンドウで [**このデバイス**] を選びます。

エクスプローラーにファイルが表示されない場合、"最近" フィルターがアクティブになっている可能性があります (左側のウィンドウで時計アイコンが強調表示されています)。 この問題を解決するには、左側のウィンドウで [**このデバイス**ドキュメント] アイコンを選択するか (時計アイコンの下)、メニューを開いて [**このデバイス**] を選択します。

## 写真やビデオを検索して表示する

[Mixed reality キャプチャ](holographic-photos-and-videos.md)では、HoloLens 上で mixed reality 写真とビデオを利用できます。  これらの写真とビデオは、デバイスのカメラロールフォルダーに保存されます。

HoloLens で撮影した写真やビデオには、次の方法でアクセスできます。

- [フォトアプリ](holographic-photos-and-videos.md)から直接カメラロールにアクセスする。
- 写真やビデオを OneDrive に同期することによって、写真やビデオをクラウドストレージにアップロードします。
- [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)の Mixed Reality キャプチャページを使用します。

### フォト アプリ

Photos アプリは、[**スタート**] メニューの既定のアプリの1つであり、HoloLens と共に組み込まれています。 詳細について[は、「写真アプリを使用してコンテンツを表示する](holographic-photos-and-videos.md)」を参照してください。

また、Microsoft ストアから[OneDrive アプリ](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3)をインストールして、他のデバイスと写真を同期することもできます。

### OneDrive アプリ

[OneDrive](https://onedrive.live.com/)を使用すると、任意のデバイスと任意のユーザーとの写真やビデオへのアクセス、管理、共有を行うことができます。 HoloLens でキャプチャされた写真やビデオにアクセスするには、HoloLens で Microsoft Store から[OneDrive アプリ](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3)をダウンロードします。 ダウンロードが完了したら、OneDrive アプリを**Settings**開き、[  >  **カメラアップロード**の設定] を選択して、[**カメラアップロード**] をオンにします。

### PC に接続する

HoloLens で[2018 年4月の更新プログラム](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)以降を実行している場合は、USB ケーブルを使用して WINDOWS 10 PC に hololens を接続し、MTP (メディア転送プロトコル) を使ってデバイス上の写真やビデオを参照することができます。 デバイスで PIN またはパスワードを設定している場合は、ファイルを参照するためにデバイスのロックが解除されていることを確認する必要があります。  

[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)を有効にしている場合は、それを使って、デバイスに保存されている写真やビデオの参照、取得、管理を行うことができます。

## アプリ内のファイルにアクセスする

アプリケーションでデバイスにファイルが保存されている場合は、そのアプリケーションを使用してファイルにアクセスすることができます。

### 他のアプリからファイルを要求する

アプリケーションは、[ファイルピッカー](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)を使用して、ファイルを保存するか、別のアプリからファイルを開くように要求することができます。

### 既知のフォルダー

HoloLens は、アプリがアクセス許可を要求できる[既知のフォルダー](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders)の数をサポートしています。

## PC で HoloLens ファイルを表示する

他のモバイルデバイスと同様に、MTP (メディア転送プロトコル) を使って HoloLens をデスクトップ PC に接続し、PC でエクスプローラーを開いて、簡単に転送できるように HoloLens ライブラリにアクセスします。

PC のエクスプローラーで HoloLens ファイルを表示するには、次の操作を行います。

1. HoloLens にサインインし、HoloLens に付属の USB ケーブルを使って PC に接続します。

1. [デバイスを開く] を選択し**て、エクスプローラーでファイルを表示する**か、PC でエクスプローラーを開いてデバイスに移動します。

HoloLens に関する情報を表示するには、PC のエクスプローラーでデバイス名を右クリックし、[**プロパティ**] を選択します。

> [!NOTE]
> HoloLens (第1世代) では、外部ハードドライブまたは SD カードへの接続をサポートしていません。

## クラウドとの同期

HoloLens からクラウドに写真やその他のファイルを同期するには、HoloLens で OneDrive をインストールしてセットアップします。 OneDrive を取得するには、HoloLens で Microsoft Store で検索します。

HoloLens では、アプリのファイルやデータはバックアップされないため、重要な情報を OneDrive に保存することをお勧めします。 こうすることで、デバイスをリセットしたり、アプリをアンインストールしたりすると、情報がバックアップされます。
