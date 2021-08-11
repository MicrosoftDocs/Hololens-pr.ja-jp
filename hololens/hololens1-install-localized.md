---
title: ローカライズされたバージョンのアプリケーションをインストールHoloLens
description: 中国語と日本語のバージョンを含む、HoloLens (第 1 世代) のローカライズされたバージョンをインストールする方法について説明します。
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: fe29e4ed611f86764f0db576b1a8794fa0ceec3047cadd26f502209faadea8b0
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661805"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>ローカライズされたバージョンの HoloLens (第 1 世代) をインストールする

中国語または日本語バージョンの HoloLens に切り替えるには、Windows Device Recovery Tool (WDRT) を使用して、PC 上の言語のビルドをダウンロードし、HoloLens にインストールする必要があります。

> [!IMPORTANT]
> WDRT を使用して、中国語または日本語のビルドをインストールすると、HoloLensファイルや設定などの既存のデータが削除HoloLens。 

1. お使いの PC で、Windows [Device Recovery Tool (WDRT) をダウンロードしてインストールします](https://support.microsoft.com/help/12379)。
1. PC に必要な言語のパッケージをダウンロードします:[簡体中国語または日本語](https://aka.ms/hololensdownload-ch)[。](https://aka.ms/hololensdownload-jp)
1. ダウンロードが完了したら、[ダウンロード]**をエクスプローラー**  >  **選択します**。 ダウンロードした zip 形式のフォルダーを右クリックし、[すべての抽出] を選択して  >  解凍します。
1. Connect付属HoloLensマイクロ USB ケーブルを使用して、PC に接続します。 (他のケーブルを使用して接続している場合でも、HoloLens最適です)。
1. ツールによってアプリケーションが自動的に検出された後HoloLensタイルをMicrosoft HoloLensします。
1. 次の画面で、[手動 **パッケージの** 選択] を選択し、手順 4. で展開したフォルダーにあるインストール ファイル   を選択します。 (拡張子が ".ffu" のファイルを探します)。) 
1. [ソフトウェア **のインストール] を** 選択し、指示に従います。 
1. ビルドがインストールされると、セットアップHoloLens自動的に開始されます。 デバイスに取り付け、セットアップの指示に従います。 

セットアップが完了したら、設定 Update & Security Windows Insider Program に移動し、最新のプレビュー ビルドを受信するように構成されていることを  >    >  確認します。 英語のプレビュー ビルドと同様に、Windows Insider Programは最新のプレビュー ビルドを使用して、HoloLensの中国語と日本語のバージョンを最新のバージョンに保っています。

> [!NOTE]
>  
> - 英語、日本語、中国語設定の間でシステム言語を変更するには、アプリでアプリを使用することはできません。 新しいビルドをフラッシュする方法は、デバイス システムの言語を変更する唯一のサポートされている方法です。
> - 画面の Pinyin キーボードを使用して簡体中国語または日本語のテキストを入力することもできますが、現時点では、Bluetooth ハードウェア キーボードを使用して簡体中国語または日本語のテキストを入力することはできません。  ただし、中国語または日本語の HoloLens では、引き続き Bluetooth キーボードを使用して英語で入力できます (ハードウェア キーボードを英語で入力するには、 ~ キーを押します)。
