---
title: 更新HoloLens 2
description: HoloLens のビルド番号を確認し、デバイスの更新プログラムを最新の状態に保ち、Insiders Program に参加して、更新プログラムをロールバックする方法について学習します。
keywords: 方法、更新、ロールバック、HoloLens、ビルドの確認、ビルド番号
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
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924113"
---
# <a name="update-hololens-2"></a>更新HoloLens 2

HoloLens では、他Windows Updateデバイスと同様に、Windows 10が使用されます。 HoloLens は、電源に接続され、インターネットに接続されている場合でも、スタンバイ状態の場合でも、システム更新プログラムを自動的にダウンロードしてインストールします。

この記事では、以下を行う HoloLens ツールについて詳しい情報を提供します。

- 現在のオペレーティング システムのバージョン (ビルド番号) の表示
- 更新プログラムの確認
- HoloLens を手動で更新する
- 古い更新プログラムへのロールバック

## <a name="check-your-operating-system-version-build-number"></a>オペレーティング システムのバージョン (ビルド番号) を確認する

システム バージョン番号 (ビルド番号) を確認するには、設定アプリを開き、[ システムバージョン情報 ]**を選択**  >  **します**。

## <a name="check-for-updates-and-manually-update"></a>更新プログラムを確認し、手動で更新する

設定では、いつでも更新プログラムを確認できます。  利用可能な更新プログラムを確認し、新しい更新プログラムを確認するには:

1. **[設定]** アプリを開きます。
1. [Update **& Security Windows Update]**  >  **に移動します**。
1. **[更新プログラムの確認]** をクリックします。

更新プログラムが利用可能な場合は、新しいバージョンのダウンロードが開始されます。 ダウンロードが完了したら、[今すぐ再起動 **] ボタンを** 選択してインストールをトリガーします。 デバイスが 40% を下回り、接続されていない場合、再起動によって更新プログラムのインストールは開始されません。

HoloLens が更新プログラムをインストールしている間に、回転する歯車と進行状況インジケーターが表示されます。 この期間中は HoloLens をオフにしない。 インストールが完了すると、自動的に再起動されます。

HoloLens では、一度に 1 つの更新プログラムが適用されます。  HoloLens が最新バージョンより複数遅れている場合は、更新プロセスを複数回実行して、完全に最新の情報に更新する必要があります。

## <a name="go-back-to-a-previous-version"></a>以前のバージョンに戻る

場合によっては、以前のバージョンの HoloLens ソフトウェアに戻したい場合があります。 推奨される手順は次のとおりです。

1. サポートに問い合わせ、問題を解決できる場合は、サポートにお問い合わせください。
    1. 省略可能 **または完全****な** テレメトリが有効になっているのを確認します。これにより、バグのアクションが容易になり、エンジニアが診断しやすくなります。
    1. [ファイル フィードバックは](hololens-feedback.md) 、可能な限り説明的です。 タイトルをメモするか、共有機能を使用して、バグをサポートと共有できます。
    1. サポートにお問 [い合わせください](https://aka.ms/hlsupport)。 問題が以前のバージョンに戻って解決する必要がある場合は、デバイスをフラッシュする FFU を提供できます。

1. それでも問題が生じない場合は、Advanced Recovery Companion を使用してHoloLens 2 [をリセットまたは再フラッシュします](hololens-recovery.md)。
    1. お使いの PC で、 [[Advanced Recovery Companion]](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) を [Microsoft Store] からダウンロードします。
    1. PC にスマートフォンや Windows デバイスが接続されていないことを確認します。
    1. フラッシュするバージョンを選択します。
        1. 最新のリリース [をダウンロードHoloLens 2できます](https://aka.ms/hololens2download)。
        1. ARC がホストする既定のビルドを使用できます。 (このオプションを選択した場合は、次の手順をスキップします)。
        1. 提供されているビルド サポートを使用できます。
    1. これらのダウンロードが完了したら、[ダウンロード]**をエクスプローラー**  >  **開きます**。 ダウンロードした zip 形式のフォルダーを右クリックし、[すべての抽出] を選択して  >  解凍します。
    1. USB-A から USB-C ケーブルを使用して HoloLens を PC に接続します。 (他のケーブルを使用して HoloLens を接続している場合でも、これは最適です)。
    1. Advanced Recovery Companion によって HoloLens が自動的に検出されます。 [新 **しい** Microsoft HoloLens選択します。
    1. 次の画面で、[手動 **パッケージの** 選択] を選択し、手順 4. で展開したフォルダーに含まれているインストール ファイルを選択します。 (拡張子が .ffu のファイルを探します)。
    1. [ **ソフトウェアのインストール] を** 選択し、指示に従います。

> [!NOTE]
> 以前のバージョンに戻って、個人用ファイルと設定が削除されます。

また、現在インストールされているリリースを使用する場合は、更新プログラム を手動で [一時停止することもできます](hololens-updates.md#pause-updates-via-device)。 これにより、エンジニアリング チームは問題を解決する時間が得されます。

## <a name="windows-insider-program-on-hololens"></a>Windows Insider Program HoloLens でのインストール

HoloLens の最新機能を確認したいですか?  その場合は、次のWindows Insider Program。HoloLens ソフトウェア更新プログラムが一般公開される前に、プレビュー ビルドにアクセスできます。

[のWindows Insiderプレビューを取得Microsoft HoloLens。](hololens-insider.md)
