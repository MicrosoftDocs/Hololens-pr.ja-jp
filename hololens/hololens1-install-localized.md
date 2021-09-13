---
title: HoloLens のローカライズ版をインストールする
description: 中国語と日本語のバージョンを含む HoloLens (第1世代) のローカライズ版をインストールする方法について説明します。
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
ms.openlocfilehash: 74eb003aafd23218b90988abe113d35f1fc3035a
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033670"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>HoloLens のローカライズ版をインストールする (第1世代)

HoloLens の簡体字中国語または日本語版に切り替えるには、Windows デバイス回復ツール (wdrt) を使用して、PC 上の言語のビルドをダウンロードし、HoloLens にインストールする必要があります。

> [!IMPORTANT]
> wdrt を使用して HoloLens の中国語版または日本語版をインストールすると、個人のファイルや設定などの既存のデータが HoloLens から削除されます。 

1. PC で、 [Windows Device Recovery Tool (wdrt)](https://support.microsoft.com/help/12379)をダウンロードしてインストールします。
1. お使いの PC に必要な言語 (簡  [体字中国語](https://aka.ms/hololensdownload-ch) または [日本語](https://aka.ms/hololensdownload-jp)) のパッケージをダウンロードします。
1. ダウンロードが完了したら、[**エクスプローラー** のダウンロード] を選択し  >  ます。 ダウンロードした zip 形式のフォルダーを右クリックし、[**すべて** 抽出] を選択し  >  て解凍します。
1. 付属のマイクロ USB ケーブルを使用して、HoloLens を PC に Connect します。 (他のケーブルを使って HoloLens に接続していたとしても、この方法は最適です)。
1. ツールによって HoloLens が自動的に検出されたら、[Microsoft HoloLens] タイルを選択します。
1. 次の画面で、[ **パッケージの手動選択**] を選択   し、手順 4. で解凍したフォルダーに存在するインストールファイルを選択します。 (拡張子が ". ffu" のファイルを探します)。 
1. [ **ソフトウェアのインストール** ] を選択し、指示に従います。 
1. ビルドがインストールされると、HoloLens セットアップが自動的に開始されます。 デバイスに移動し、セットアップの指示に従います。 

セットアップが完了したら、[**設定**  >  **Update & Security**  >  **Windows Insider program**] にアクセスし、最新のプレビュービルドを受信するように構成されていることを確認します。 英語版のプレビュービルドと同様、Windows Insider プログラムは、最新のプレビュービルドを使用して、HoloLens の中国語と日本語のバージョンを最新の状態に保ちます。

> [!NOTE]
>  
> - 設定アプリを使用して、英語、日本語、および中国語のシステム言語を変更することはできません。 デバイスシステムの言語を変更する唯一の方法は、新しいビルドを点滅させることです。
> - スクリーン Pinyin キーボードを使用して簡体字中国語または日本語のテキストを入力することはできますが、Bluetooth のハードウェアキーボードを使用して簡体字中国語または日本語のテキストを入力することは現時点ではサポートされていません。  ただし、簡体字中国語または日本語 HoloLens では、引き続き Bluetooth キーボードを使用して英語で入力できます (ハードウェアキーボードを使用して英語の種類に切り替えるには、~ キーを押します)。
