---
title: HoloLens を更新する
description: HoloLens の [ビルド番号]、[更新]、[ロールバック] の更新を確認します。
keywords: 使い方、更新、ロールバック、HoloLens、チェックビルド、ビルド番号
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
ms.openlocfilehash: ee007b00b350ea0f80cda34964d32a57dc6dc0c6
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828592"
---
# HoloLens を更新する

HoloLens は、他の Windows 10 デバイスと同じように、Windows Update を使用します。 HoloLens は、電源に接続されていて、スタンバイ状態にあるときでもシステムの更新プログラムを自動的にダウンロードしてインストールします。

この記事では、次のような HoloLens ツールについて説明します。

- 現在のオペレーティングシステムバージョン (ビルド番号) を表示する
- 更新プログラムの確認
- HoloLens を手動で更新する
- 以前の更新プログラムにロールバックする

## オペレーティングシステムのバージョン (ビルド番号) を確認する

システムのバージョン番号 (ビルド番号) を確認するには、設定アプリを開いて [**システム**情報] を選択し  >  **About**ます。

## 更新プログラムを確認して手動で更新する

[設定] では、いつでも更新を確認できます。  使用可能な更新プログラムを確認し、新しい更新プログラムを確認するには:

1. [**設定**] アプリを開きます。
1. **更新 & セキュリティ**  >  の**Windows update**に移動します。
1. [**更新プログラムの確認**] を選びます。

更新プログラムが利用可能な場合は、新しいバージョンのダウンロードが開始されます。 ダウンロードが完了したら、[**今すぐ再起動**] ボタンを選択してインストールを開始します。 使用しているデバイスが40% 未満で、接続されていない場合は、再起動すると更新プログラムのインストールが開始されません。

HoloLens で更新プログラムをインストールしている間に、回転する歯車と進行状況インジケーターが表示されます。 このとき、HoloLens をオフにしないでください。 インストールが完了すると、自動的に再起動します。

HoloLens は一度に1つの更新プログラムを適用します。  HoloLens が最新のバージョンより複数のバージョンである場合は、更新プロセスを複数回実行して、完全に最新の状態にすることが必要な場合があります。

## 以前のバージョンに戻る-HoloLens 2

場合によっては、HoloLens ソフトウェアの以前のバージョンに戻すこともできます。 これは、高度な回復コンパニオンを使って HoloLens を以前のバージョンにリセットすることで行うことができます。

> [!NOTE]
> 以前のバージョンに戻すと、個人用のファイルと設定が削除されます。

以前のバージョンの HoloLens 2 に戻すには、次の手順を実行します。

1. PC にスマートフォンや Windows デバイスが接続されていないことを確認します。
1. PC で、Microsoft Store から[高度な回復コンパニオン](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)をダウンロードします。
1. [最新の HoloLens 2 リリース](https://aka.ms/hololens2download)をダウンロードします。
1. これらのダウンロードが完了したら、**[エクスプローラー]** > **[ダウンロード]** を開きます。 ダウンロードした zip 形式のフォルダーを右クリックし、**[すべて展開]** > **[展開]** を選択して展開します。
1. USB を使って PC に HoloLens を接続します。 usb-C ケーブルを使用します。 (HoloLens の接続に他のケーブルを使用していた場合も、このケーブルが最適です)。
1. 高度な回復コンパニオンでは、HoloLens が自動的に検出されます。 **[Microsoft HoloLens]** タイルを選択します。
1. 次の画面で **[手動によるパッケージの選択]** を選択し、手順 4 で展開したフォルダーに含まれているインストール ファイルを選択します  (.ffu という拡張子のファイルを探します)。
1. **[ソフトウェアのインストール]** を選択し、手順に従います。

## 以前のバージョンの HoloLens に戻る (第1世代)

場合によっては、HoloLens ソフトウェアの以前のバージョンに戻すこともできます。 これには、Windows Device Recovery Tool を使って HoloLens を以前のバージョンにリセットすることで行うことができます。

> [!NOTE]
> 以前のバージョンに戻すと、個人用のファイルと設定が削除されます。

HoloLens 1 の以前のバージョンに戻るには、次の手順を実行します。

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

## HoloLens 上の Windows Insider プログラム

HoloLens の最新機能を確認するにはどうすればよいですか?  その場合は、Windows Insider Program に参加してください。HoloLens ソフトウェア更新プログラムのプレビュービルドにアクセスできるのは、一般公開されている場合です。

[Microsoft HoloLens 用 Windows Insider preview を入手](hololens-insider.md)します。
