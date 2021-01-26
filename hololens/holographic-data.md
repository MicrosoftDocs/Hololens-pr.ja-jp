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
# HoloLens でファイルを検索し、開いて保存する

写真やビデオなど、HoloLens で作成したファイルは、HoloLens デバイスに直接保存されます。 Windows 10 でファイルを管理するのと同じ方法でファイルを表示および管理します。

- エクスプローラー アプリを使ってローカル フォルダーにアクセスする。
- アプリのストレージ内。
- 特別なフォルダー (ビデオや音楽ライブラリなど) 内。
- アプリとファイル ピッカー (OneDrive など) を含むストレージ サービスの使用。
- USB ケーブルを使用して HoloLens に接続されたデスクトップ PC を使い、MTP (メディア転送プロトコル) サポートを使用します。

## エクスプローラーを使用して HoloLens 上のファイルを表示する

> [HoloLens 用の Windows 10 April 2018 Update (RS4)](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)の現在、すべての HoloLens 2 デバイスと HoloLens (第 1 世代) に適用されます。

HoloLens のエクスプローラーを使って、3D オブジェクト、ドキュメント、画像など、デバイス上のファイルを表示および管理します。 [すべてのアプリ**を**   >  **起動]**   >  **エクスプローラーに移動して**開始します。

> [!TIP]
> エクスプローラーに一覧表示されるファイルがない場合は、左上のウィンドウで **[このデバイス** ] を選択します。

エクスプローラーにファイルが表示されなかっていない場合は、"最近使用した" フィルターがアクティブである可能性があります (左側のウィンドウで時計アイコンが強調表示されています)。 これを修正するには、左側の**** ウィンドウ (時計アイコンの下) で [このデバイス ドキュメント] アイコンを選択するか、メニューを開いて [このデバイス]**を選択します**。

## 写真とビデオを検索して表示する

[Mixed Reality キャプチャを](holographic-photos-and-videos.md) 使うと、HoloLens で Mixed Reality の写真やビデオを撮影できます。  これらの写真とビデオは、デバイスのカメラ ロール フォルダーに保存されます。

HoloLens で撮影した写真やビデオには、次の方法でアクセスできます。

- フォト アプリを通じてカメラ ロールに [直接アクセスする](holographic-photos-and-videos.md)。
- 写真とビデオを OneDrive に同期して、写真やビデオをクラウド ストレージにアップロードします。
- Using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### フォト アプリ

フォト アプリはスタート メニューの既定のアプリ**** の 1 つで、HoloLens に組み込されています。 フォト アプリを使 [ってコンテンツを表示する方法について詳しくは、以下をご覧ください](holographic-photos-and-videos.md)。

Microsoft Store から [OneDrive アプリ](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) をインストールして、写真を他のデバイスと同期することもできます。

### OneDrive アプリ

[OneDrive を](https://onedrive.live.com/) 使用すると、写真やビデオにアクセスし、管理し、任意のデバイスやユーザーと共有できます。 HoloLens でキャプチャした写真やビデオにアクセスするには、HoloLens の Microsoft Store から [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) アプリをダウンロードします。 ダウンロードしたら、OneDrive アプリを開き、[**カメラ**の設定のアップロード] を選択し、[  >  **** カメラのアップロード]**をオンにします**。

### PC に接続する

HoloLens で Windows [10 April 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) 更新プログラム以降を実行している場合は、USB ケーブルを使って MTP (メディア転送プロトコル) を使ってデバイス上の写真やビデオを参照することにより、HoloLens を Windows 10 PC に接続できます。 デバイスに PIN またはパスワードが設定されている場合は、ファイルを参照するためにデバイスのロックが解除されていないことを確認する必要があります。  

[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)を有効にしている場合は、それを使ってデバイスに保存されている写真やビデオを参照、取得、管理できます。

## アプリ内のファイルにアクセスする

アプリケーションがデバイスにファイルを保存する場合は、そのアプリケーションを使用してファイルにアクセスできます。

### 別のアプリからファイルを要求する

アプリケーションは、ファイル ピッカーを使用して、ファイルを保存するか、別のアプリからファイル [を開くことを要求できます](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)。

### 既知のフォルダー

HoloLens は、アプリがアクセス許可 [を要求](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) できる多くの既知のフォルダーをサポートしています。

## PC で HoloLens ファイルを表示する

他のモバイル デバイスと同様に、MTP (メディア転送プロトコル) を使って HoloLens をデスクトップ PC に接続し、PC でエクスプローラーを開いて HoloLens ライブラリにアクセスして簡単に転送できます。

PC のエクスプローラーで HoloLens ファイルを表示するには、次の手順を実行します。

1. HoloLens にサインインし、HoloLens に付属の USB ケーブルを使って PC に接続します。

1. [ **デバイスを開く**] を選択してエクスプローラーでファイルを表示するか、PC でエクスプローラーを開いてデバイスに移動します。

HoloLens に関する情報を表示するには、PC のエクスプローラーでデバイス名を右クリックし、[プロパティ] を選択 **します**。

> [!NOTE]
> HoloLens (第 1 世代) では、外部ハード ドライブまたは SD カードへの接続はサポートされていません。

## クラウドへの同期

写真などのファイルを HoloLens からクラウドに同期するには、HoloLens に OneDrive をインストールしてセットアップします。 OneDrive を取得するには、HoloLens の Microsoft Store で OneDrive を検索します。

HoloLens はアプリのファイルとデータをバックアップしないので、重要なファイルを OneDrive に保存すると良い方法です。 そうすることで、デバイスをリセットしたり、アプリをアンインストールしたりすると、情報がバックアップされます。
