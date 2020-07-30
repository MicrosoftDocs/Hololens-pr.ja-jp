---
title: HoloLens 1 を再起動、リセット、または回復する
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
description: Windows Device Recovery Tool を使用して HoloLens 第 1 世代に画像をフラッシュする方法。
keywords: ハウツー、再起動、リセット、回復、ハード リセット、ソフト リセット、電源サイクル、HoloLens、シャットダウン、wdrt、windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: de53f8f2cccfe3ece8900c88c5379adf2fb55a7b
ms.sourcegitcommit: 5d38af8d17dfcc028e7e0b2bb888c6c9d1e40524
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "10899180"
---
# HoloLens 第 1 世代を再起動、リセット、または回復する

HoloLens で問題が発生している場合は、再起動、リセット、またはデバイスの回復を伴う更新を試してください。

HoloLens が正常に動作していない場合に試してみることがいくつかあります。  この記事では、推奨される回復手順を順に説明します。

HoloLens 2 の回復を検討している場合は、プロセスに違いがあるため、[HoloLens 2 の回復](https://docs.microsoft.com/hololens/hololens-recovery)ページをご覧ください。

この記事では HoloLens デバイスとソフトウェアに焦点を当てていますが、ホログラムが正しく表示されない場合は、[この記事](hololens-environment-considerations.md)で説明されているホログラムの品質を向上させる環境要因を参照してください。

## 再起動

### Cortana を使用して安全な再起動を実行する

HoloLens を再起動する最も安全な方法は、Cortana を使用することです。 これは通常、HoloLens で問題が発生した場合の簡単な最初の手順です。 

> [!NOTE]
> Cortana はすべてのデバイスで利用できるわけではありません。 Cortana は、すべての HoloLens (第 1 世代) デバイスで利用できます。
> Cortana は、Windows Holograpic バージョン 2004 更新プログラムより前のビルドの HoloLens 2 デバイスで使用できます。

1. デバイスを装着する
1. 電源が入っていること、ユーザーがログインしていること、およびデバイスがパスワードのロックを解除するのを待っていないことを確認します。
1. 「コルタナさん、再起動して」または「コルタナさん、再起動して」と言います。
1. Cortana が認識すると、確認を求めます。 Cortana が質問を終えた後、Cortana が自分の言うことを聞いていることを示す音が鳴るのを少し待ってから、「はい」と言います。
1. デバイスが再起動します。

### 電源ボタンを使用して安全に再起動する

それでもデバイスを再起動できない場合は、電源ボタンを使用して再起動してみてください。

1. 電源ボタンを 5 秒間押し続けます。
   1. 1 秒後、5 つのすべての LED が点灯してから、右から左にゆっくりと消灯します。
   1. 5 秒後、すべての LED がオフになり、シャットダウン コマンドが正常に発行されたことを示します。
   1. すべての LED がオフになった直後にボタンを押すのを停止することが重要であることに注意してください。
1. シャットダウンが完全に成功するまで 1 分間待ちます。 ディスプレイがオフになっていても、シャットダウンが進行中の場合があることに注意してください。
1. 電源ボタンを 1 秒間押し続けて、デバイスの電源を再度オンにします。

### Windows Device Portal を使用して安全な再起動を実行する

> [!NOTE]
> これを行うには、HoloLens を開発者デバイスとして構成する必要があります。  
> [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) の詳細をご覧ください。

前の手順が機能しない場合は、[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) を使用してデバイスを再起動してみてください。 右上隅に、デバイスを再起動またはシャットダウンするオプションがあります。

### 安全でない強制再起動を実行する

上記のいずれの方法でもデバイスを正常に再起動できない場合は、強制的に再起動できます。 この方法は、HoloLens からバッテリーを取り出すのと同じです。  これは、デバイスを破損する可能性がある危険な操作です。  その場合は、HoloLens をフラッシュする必要があります。  

> [!WARNING]
> これは有害な可能性のある方法であり、上記の方法がどれも機能しない場合にのみ使用してください。

1. 電源ボタンを 10 秒以上押し続けます。
   - ボタンを 10 秒以上押しても問題ありません。
   - LED アクティビティを無視しても安全です。
1. ボタンを離し、2 ~ 3 秒待ちます。
1. 電源ボタンを 1 秒間押し続けて、デバイスの電源を再度オンにします。
それでも問題が解決しない場合は、すべてのバッテリー インジケーターが消え、画面にホログラムが表示されなくなるまで、電源ボタンを 4 秒間押します。 1 分間待ってから、もう一度電源ボタンを押してデバイスの電源を入れます。

## 工場出荷時の設定にリセット

> [!NOTE]
> リセットするには、バッテリーを最低 40% 充電する必要があります。

再起動後も HoloLens に問題が発生する場合は、HoloLens を出荷時の状態にリセットしてみてください。  HoloLens をリセットすると、HoloLens にインストールされている Windows Holographic ソフトウェアのバージョンが保持され、それ以外はすべて工場出荷時の設定に戻ります。

デバイスをリセットすると、TPM リセットを含むすべての個人データ、アプリ、設定が消去されます。 リセットすると、インストールされている最新バージョンの Windows Holographic のみがインストールされ、すべての初期化手順 (調整、Wi-Fi への接続、ユーザー アカウントの作成、アプリのダウンロードなど) をやり直す必要があります。

1. 設定アプリを起動し、**[更新]** > **[回復]** の順に選択します。
1. [**デバイスのリセット**] オプションを選択し、確認メッセージを読みます。
1. デバイスをリセットすることに同意すると、デバイスが再起動し、プログレス バー付きの回転するギアのセットが表示されます。
1. このプロセスが完了するまで約 30 分待ちます。
1. リセットが完了し、デバイスはすぐに使用可能な状態で再起動します。

## オペレーティング システムを再インストールする

再起動してリセットした後もデバイスに問題がある場合は、コンピューターの回復ツールを使用して、HoloLens のオペレーティング システムとファームウェアを再インストールできます。  

HoloLens がリセットする必要があるすべてのデータは、Full Flash Update (ffu) にパッケージ化されています。  これは、iso、wim、または vhd に似ています。  [FFU 画像ファイル形式について学習します。](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

必要に応じて、Windows Device Recovery Tool を使用して、HoloLens (第 1 世代) に完全に新しいオペレーティング システムをインストールできます。

このツールを使用する前に、HoloLens を再起動またはリセットすると問題が解決するかどうかを確認してください。 回復プロセスには時間がかかる場合があります。  完了すると、HoloLens に承認された Windows Holographic ソフトウェアの最新バージョンがインストールされます。

このツールを使用するには、Windows 10 以降を実行し、4 GB 以上の空き容量があるコンピューターが必要です。  このツールは仮想マシンでは実行できないことに注意してください。

### HoloLens を回復する:

1. コンピューターに [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) をダウンロードしてインストールします。
1. HoloLens に付属の Micro USB ケーブルを使用して、HoloLens (第 1 世代) をコンピューターに接続します。
1. Windows Device Recovery Tool を実行し、指示に従います。

HoloLens (第 1 世代) が自動的に検出されない場合は、[**デバイスが検出されませんでした**] を選択し、指示に従ってデバイスを回復モードにします。

### 手動フラッシュ モード:

デバイスが検出されない場合は、次の方法を使用して手動でデバイスをフラッシュ モードにしてください。

1. すべての電源からデバイスを取り外します。
1. デバイスがオンになっている場合は、完全にオフになるまで電源ボタンを押し続けてください。
1. [**音量を上げる**] ボタンを押したまま、**電源ボタン**を軽くタップします。 
1. デバイスが起動し、中央の LED ライトのみが表示されます。
1. デバイスを PC に接続します。
1. Windows Device Recovery Tool を起動します。
1. [*デバイスが検出されませんでした**] を選択し、**HoloLens** を選択する必要があります。 
1. 指示に従ってデバイスを回復します。
