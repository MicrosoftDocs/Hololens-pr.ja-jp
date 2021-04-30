---
title: HoloLens を更新する
description: HoloLens のビルド番号を確認する方法、デバイスの更新を使用して最新の状態に保つ方法、Insider プログラムに参加する方法、および更新プログラムをロールバックする方法について説明します。
keywords: 操作方法、更新プログラム、ロールバック、HoloLens、ビルドの確認、ビルド番号
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309513"
---
# <a name="update-hololens"></a>HoloLens を更新する

HoloLens は、他の Windows 10 デバイスと同様に Windows Update を使用します。 HoloLens では、システムの更新プログラムが電源に接続され、インターネットに接続されると常に、システムの更新プログラムが自動的にダウンロードおよびインストールされます。

この記事では、次のための HoloLens ツールについて説明します。

- 現在のオペレーティングシステムのバージョンを表示しています (ビルド番号)
- 更新プログラムの確認
- HoloLens の手動更新
- 古い更新プログラムへのロールバック

## <a name="check-your-operating-system-version-build-number"></a>オペレーティングシステムのバージョンを確認する (ビルド番号)

システムのバージョン番号 (ビルド番号) を確認するには、[設定] アプリを開き、[**システム**] を選択し  >  ます。

## <a name="check-for-updates-and-manually-update"></a>更新プログラムを確認し、手動で更新する

更新プログラムは、[設定] でいつでも確認できます。  利用可能な更新プログラムを確認し、新しい更新プログラムを確認するには:

1. **[設定]** アプリを開きます。
1. [ **Update & Security**  >  **Windows Update** に移動します。
1. **[更新プログラムの確認]** をクリックします。

更新プログラムが利用可能な場合は、新しいバージョンのダウンロードが開始されます。 ダウンロードが完了したら、[ **今すぐ再起動** ] ボタンを選択してインストールを開始します。 デバイスが40% 未満で、電源に接続されていない場合、再起動しても更新プログラムのインストールは開始されません。

HoloLens が更新プログラムをインストールしている間、スピン歯車と進行状況インジケーターが表示されます。 この期間中は HoloLens をオフにしないでください。 インストールが完了すると、自動的に再起動します。

HoloLens は、一度に1つの更新プログラムを適用します。  HoloLens が最新のバージョンより複数のバージョンである場合は、更新プロセスを複数回実行して完全に最新の状態にすることが必要になる場合があります。

## <a name="go-back-to-a-previous-version---hololens-2"></a>前のバージョンに戻る-HoloLens 2

場合によっては、以前のバージョンの HoloLens ソフトウェアに戻ることが必要になることがあります。 これを行うには、Advanced Recovery コンパニオンを使用して、HoloLens を以前のバージョンにリセットします。

> [!NOTE]
> 以前のバージョンに戻すと、個人用ファイルと設定が削除されます。

以前のバージョンの HoloLens 2 に戻るには、次の手順を実行します。

1. 携帯電話や Windows デバイスが PC に接続されていないことを確認します。
1. PC で、Microsoft Store から [高度な回復コンパニオン](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) をダウンロードします。
1. 最新の [HoloLens 2 リリース](https://aka.ms/hololens2download)をダウンロードします。
1. これらのダウンロードが完了したら、**ファイルエクスプローラー** の  >  **ダウンロード** を開きます。 ダウンロードした zip 形式のフォルダーを右クリックし、[**すべて** 抽出] を選択し  >  て解凍します。
1. USB-A から USB C ケーブルを使用して HoloLens を PC に接続します。 (他のケーブルを使用して HoloLens に接続している場合でも、これは最適な方法です)。
1. Advanced Recovery コンパニオンは、自動的に HoloLens を検出します。 [ **Microsoft HoloLens** ] タイルを選択します。
1. 次の画面で、[ **パッケージの手動選択** ] を選択し、手順 4. で解凍したフォルダーに含まれているインストールファイルを選択します。 (拡張子が ffu のファイルを探します。)
1. [ **ソフトウェアのインストール**] を選択し、指示に従います。

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>以前のバージョン (HoloLens) に戻る (第1世代)

場合によっては、以前のバージョンの HoloLens ソフトウェアに戻ることが必要になることがあります。 これを行うには、Windows デバイス回復ツールを使用して、HoloLens を以前のバージョンにリセットします。

> [!NOTE]
> 以前のバージョンに戻すと、個人用ファイルと設定が削除されます。

以前のバージョンの HoloLens 1 に戻るには、次の手順を実行します。

1. 携帯電話や Windows デバイスが PC に接続されていないことを確認します。
1. PC で、 [Windows デバイス回復ツール (WDRT)](https://support.microsoft.com/help/12379)をダウンロードします。
1. [HoloLens 記念日更新の復旧パッケージ](https://aka.ms/hololensrecovery)をダウンロードします。
1. ダウンロードが完了したら、**エクスプローラー** の [ダウンロード] を開き  >  ます。 ダウンロードした zip 形式のフォルダーを右クリックし、[**すべて** 抽出] を選択し  >  て解凍します。
1. HoloLens を、付属のマイクロ USB ケーブルを使用して PC に接続します。 (他のケーブルを使用して HoloLens に接続している場合でも、これは最適な方法です)。
1. WDRT は、自動的に HoloLens を検出します。 [ **Microsoft HoloLens** ] タイルを選択します。
1. 次の画面で、[ **パッケージの手動選択** ] を選択し、手順 4. で解凍したフォルダーに格納されているインストールファイルを選択します。 (拡張子が ffu のファイルを探します。)
1. [ **ソフトウェアのインストール**] を選択し、指示に従います。

> [!NOTE]
> WDRT が HoloLens を検出しない場合は、PC を再起動してみてください。 それでもうまくいかない場合は、[ **デバイスが検出されませんでした**] を選択し、[ **Microsoft HoloLens**] を選択して、指示に従います。

## <a name="windows-insider-program-on-hololens"></a>HoloLens の Windows Insider プログラム

HoloLens の最新の機能を確認したい場合は、  その場合は、Windows Insider プログラムに参加してください。HoloLens ソフトウェア更新プログラムのプレビュービルドにアクセスしてから、一般公開されるようになります。

[Microsoft HoloLens の Windows Insider preview を入手](hololens-insider.md)します。
