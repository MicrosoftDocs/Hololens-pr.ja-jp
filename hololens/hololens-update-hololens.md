---
title: HoloLens を更新する
description: HoloLens のビルド番号を確認し、デバイスの更新プログラムを最新の状態に保ち、Insider プログラムに参加し、更新プログラムをロールバックする方法について学習します。
keywords: 使い方, 更新, ロールバック, HoloLens, ビルドの確認, ビルド番号
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283938"
---
# HoloLens を更新する

HoloLens は、他の Windows 10 デバイスと同じように、Windows Update を使用します。 HoloLens は、スタンバイ状態の場合でも、電源に接続され、インターネットに接続されると、システム更新プログラムを自動的にダウンロードしてインストールします。

この記事では、次の HoloLens ツールについて詳しい情報を提供します。

- 現在のオペレーティング システムのバージョン (ビルド番号) の表示
- 更新プログラムの確認
- HoloLens を手動で更新する
- 以前の更新プログラムへのロールバック

## オペレーティング システムのバージョン (ビルド番号) を確認する

[設定] アプリを開き、[システムバージョン情報] を選択すると、システム バージョン番号 (ビルド番号)**を確認**  >  **できます**。

## 更新プログラムを確認して手動で更新する

設定では、更新プログラムをいつでも確認できます。  利用可能な更新プログラムを確認し、新しい更新プログラムを確認するには:

1. 設定アプリ **を開** きます。
1. Windows Update**の更新&**  >  **に移動します**。
1. [更新 **プログラムの確認] を選択します**。

更新プログラムが利用可能な場合は、新しいバージョンのダウンロードが開始されます。 ダウンロードが完了したら、[今すぐ再起動] **ボタンを選択** してインストールをトリガーします。 デバイスが 40% 未満で接続されていない場合、再起動によって更新プログラムのインストールが開始されません。

HoloLens が更新プログラムをインストールしている間は、回転するギアと進行状況インジケーターが表示されます。 この間は HoloLens をオフにしない。 インストールが完了すると、自動的に再起動されます。

HoloLens は、一度に 1 つの更新プログラムを適用します。  HoloLens が最新のバージョンより複数ある場合は、更新プロセスを複数回実行して、完全に最新の情報を取得する必要があります。

## 以前のバージョンに戻る - HoloLens 2

場合によっては、HoloLens ソフトウェアの以前のバージョンに戻すこともできます。 これは、高度な回復コンパニオンを使って HoloLens を以前のバージョンにリセットすることで行うことができます。

> [!NOTE]
> 以前のバージョンに戻すと、個人用のファイルと設定が削除されます。

以前のバージョンの HoloLens 2 に戻すには、次の手順を実行します。

1. PC にスマートフォンや Windows デバイスが接続されていないことを確認します。
1. PC で、Microsoft Store から[高度な回復コンパニオン](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)をダウンロードします。
1. [最新の HoloLens 2 リリース](https://aka.ms/hololens2download)をダウンロードします。
1. これらのダウンロードが完了したら、**[エクスプローラー]** > **[ダウンロード]** を開きます。 ダウンロードした zip 形式のフォルダーを右クリックし、**[すべて展開]** > **[展開]** を選択して展開します。
1. USB-A から USB-C ケーブルを使って HoloLens を PC に接続します。 (HoloLens の接続に他のケーブルを使用していた場合も、このケーブルが最適です)。
1. 高度な回復コンパニオンでは、HoloLens が自動的に検出されます。 **[Microsoft HoloLens]** タイルを選択します。
1. 次の画面で **[手動によるパッケージの選択]** を選択し、手順 4 で展開したフォルダーに含まれているインストール ファイルを選択します  (.ffu という拡張子のファイルを探します)。
1. **[ソフトウェアのインストール]** を選択し、手順に従います。

## 以前のバージョンに戻る - HoloLens (第 1 世代)

場合によっては、HoloLens ソフトウェアの以前のバージョンに戻すこともできます。 これには、Windows Device Recovery Tool を使って HoloLens を以前のバージョンにリセットすることで行うことができます。

> [!NOTE]
> 以前のバージョンに戻すと、個人用のファイルと設定が削除されます。

以前のバージョンの HoloLens 1 に戻る場合は、次の手順を実行します。

1. PC にスマートフォンや Windows デバイスが接続されていないことを確認します。
1. PC で、[Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) をダウンロードします。
1. [HoloLens Anniversary Update 回復パッケージ](https://aka.ms/hololensrecovery)をダウンロードします。
1. これらのダウンロードが完了したら、**[エクスプローラー]** > **[ダウンロード]** を選択します。 ダウンロードした zip 形式のフォルダーを右クリックし、**[すべて展開]** > **[展開]** を選択して展開します。
1. 付属していた micro-USB ケーブルを使用して、HoloLens を PC に接続します  (HoloLens の接続に他のケーブルを使用していた場合も、このケーブルが最適です)。
1. WDRT により、HoloLens が自動的に検出されます。 **[Microsoft HoloLens]** タイルを選択します。
1. 次の画面で、**[手動によるパッケージの選択]** を選択し、手順 4 で展開したフォルダーに含まれていたインストール ファイルを選択します  (.ffu という拡張子のファイルを探します)。
1. **[ソフトウェアのインストール]** を選択し、手順に従います。

> [!NOTE]
> WDRT で HoloLens が検出されない場合は、PC を再起動してみてください。 それでも問題が解決しない場合は、**[デバイスが検出されませんでした]** を選択し、**[Microsoft HoloLens]** を選択して、表示される指示に従って操作します。

## HoloLens の Windows Insider Program

HoloLens の最新機能を確認する場合  その場合は、Windows Insider Program に参加します。HoloLens ソフトウェア更新プログラムを一般公開する前に、プレビュー ビルドにアクセスできます。

[Microsoft HoloLens の Windows Insider プレビューを取得します](hololens-insider.md)。
