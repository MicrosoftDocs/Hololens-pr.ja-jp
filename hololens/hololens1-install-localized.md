---
title: HoloLens のローカライズされたバージョンをインストールする
description: HoloLens の中国語または日本語版をインストールする方法について説明します。
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: high
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 9ccee2e11650926a5570967f1de5f6b341a17ae6
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829556"
---
# HoloLens (第 1 世代) のローカライズされたバージョンをインストールする

HoloLens の中国語版または日本語版に切り替えるには、Windows Device Recovery Tool (WDRT) を使用して、その言語のビルドを PC にダウンロードしてから HoloLens にインストールする必要があります。

> [!IMPORTANT]
> WDRT を使用して HoloLens の中国語版または日本語版のビルドをインストールすると、個人用ファイルや設定などの既存データが HoloLens から削除されます。 

1. PC に [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) をダウンロードし、インストールします。
1. 必要な言語 ([簡体字中国語](https://aka.ms/hololensdownload-ch)または[日本語](https://aka.ms/hololensdownload-jp)) のパッケージを PC にダウンロードします。
1. ダウンロードが完了したら、**[エクスプローラー]** > **[ダウンロード]** を選択します。 ダウンロードした zip 形式のフォルダーを右クリックし、**[すべて展開]** > **[展開]** を選択して展開します。
1. 付属していた micro-USB ケーブルを使用して、HoloLens を PC に接続します  (HoloLens の接続に他のケーブルを使用していた場合も、このケーブルが最適です)。
1. ツールによって HoloLens が自動的に検出されたら、Microsoft HoloLens タイルを選択します。
1. 次の画面で **[手動によるパッケージの選択]** を選択し、手順 4. で展開したフォルダーにあるインストール ファイルを選択します  (".ffu" という拡張子のファイルを探します)。 
1.  **[ソフトウェアのインストール]** を選択し、手順に従います。 
1. ビルドがインストールされると、HoloLens セットアップが自動的に開始します。 デバイスに配置し、セットアップの手順に従います。 

セットアップが完了したら、**[設定]** > **[更新とセキュリティ]** > **[Windows Insider Program]** に移動し、最新のプレビュー ビルドを受け取るよう構成されていることを確認します。 英語版のプレビュー ビルドと同様、Windows Insider Program では、最新のプレビュー ビルドを使用して HoloLens の中国語版および日本語版が最新の状態に維持されます。

> [!NOTE]
>  
> - 設定アプリを使用して、英語、日本語、中国語の間でシステム言語を変更することはできません。 デバイスのシステム言語を変更するためにサポートされている唯一の方法は、新しいビルドをフラッシュすることです。
> - Pinyin のスクリーン キーボードを使用して簡体字中国語または日本語のテキストを入力することはできますが、現時点では、Bluetooth ハードウェア キーボードでの簡体字中国語または日本語テキストの入力はサポートされていません。  ただし、中国語版または日本語版の HoloLens では、引き続き Bluetooth キーボードを使用して英語で入力できます (ハードウェア キーボードを英語入力に切り替えるには、~ キーを押します)。
