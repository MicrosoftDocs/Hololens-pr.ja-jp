---
title: HoloLens 1 を再起動、リセット、または回復する
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
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
ms.openlocfilehash: f0aa400be56d09a843a1b7c9bae78346551ad8af
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283918"
---
# HoloLens 第 1 世代を再起動、リセット、または回復する

HoloLens で問題が発生している場合は、再起動、リセット、またはデバイスの回復を使用してデバイスを再フラッシュしてみてください。 この記事では、推奨される回復手順を順に説明します。

HoloLens 2 を復元したい場合は、プロセスが異なるので [RHoloLens 2 を回復させる方法](https://docs.microsoft.com/hololens/hololens-recovery) を参照してください。

> [!NOTE]
> この記事では、HoloLens デバイスとソフトウェアに焦点を当てています。 ホログラムが正しく表示されない場合、ホログラムの品質を改善する要因の詳細については、「**[HoloLens 環境の考慮事項](hololens-environment-considerations.md)**」 を参照してください。

## 再起動

### Cortana を使用して安全に再起動する

HoloLens を再起動する最も安全な方法は、Cortana を使用することであり、通常、HoloLens に問題が発生した場合に最初に試みることになります。

> [!NOTE] 
> Cortana はすべてのデバイスで利用できるわけではありません。
> - Cortana は、すべての HoloLens (第 1 世代) デバイスで利用できます。 
> - Cortana は、Windows Holograpic バージョン 2004 更新プログラムより前のビルドの HoloLens 2 デバイスで使用できます。

1. HoloLens の電源を入れます。
1. ユーザーがログインしていること、およびデバイスがパスワードのロックを解除するのを待っていないことを確認します。
2. 「コルタナさん、再起動して」または「コルタナさん、再起動して」と言います。
3. Cortana が反応し、確認を求めます。 質問の後に音が鳴るのを待ってから、"はい" と音声で指示します。 デバイスが再起動します。

### 電源ボタンを使って安全に再起動する

それでもデバイスを再起動できない場合は、**電源** ボタンを使用して再起動してみてください。

1. **電源ボタン**を 5 秒間押し続けます。 1 秒後に 5 個の Led がすべて点灯してから、1 つずつ右から左にゆっくりと消灯していきます。 5 秒後にすべての Led が消灯し、正常にシャットダウンされたことが示されます。
      
   > [!IMPORTANT]
   > すべての LED が消灯した直後にすぐボタンを押すのはやめてください。
1. 完全にシャットダウンされるまで 1 分待ちます。 ディスプレイが消灯した後もシャットダウンが進行中の場合があります。
2. **電源** ボタンを 1 秒間押し続けて、デバイスの電源を再度オンにします。

### Windows デバイス ポータルを使用して安全な再起動を行う

> [!NOTE]
> これを行うには、HoloLens を開発者デバイスとして構成する必要があります。 詳細については、[Windows デバイス ポータル](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) をご参照ください。

前の手順が機能しない場合は、[Windows デバイス ポータル](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) を使用してデバイスを再起動してみてください。 右上隅に、デバイスを再起動またはシャットダウンするオプションがあります。

### 安全でない強制再起動を行う

前の方法でも HoloLens が再起動しない場合は、強制的に再起動させます。 この方法は、バッテリーを取り出して再インストールするのと同じです。 デバイスが破損する可能性があるため、危険です。 その場合は、HoloLens をフラッシュする必要があります。  

> [!WARNING]
> これは害を及ぼす可能性のある方法であり、これまでに紹介した方法がどれも機能しない場合にのみ使用してください。

1. **電源** ボタンを 10 秒以上押し続けます。
   - ボタンを 10 秒以上押しても問題ありません。
   - LED アクティビティを無視しても安全です。
1. ボタンを離し、2 ~ 3 秒待ちます。
1. **電源** ボタンを 1 秒間押し続けます。
1. それでも問題が解決しない場合は、すべてのバッテリー インジケーターが消え、画面にホログラムが表示されなくなるまで、**電源** ボタンを 4 秒間押します。 1 分間待ってから、もう一度 **電源** ボタンを押してデバイスの電源を入れます。

## 工場出荷時の設定にリセット

> [!NOTE]
> リセットするには、バッテリーを最低 40% 充電する必要があります。

HoloLens にまだ問題がある場合は、それを工場出荷時の状態に再設定してみてください。 この手順により、HoloLens にインストールされている Windows Holographic ソフトウェアのバージョンが保持され、それ以外はすべて工場出荷時の設定に戻ります。

>[!WARNING]
> デバイスをリセットすると、TPM リセットを含むすべての個人データ、アプリ、設定が消去されます。 リセットすると、最後にインストールされたバージョンの Windows Holographic のみがインストールされます。 すべての初期設定 （調整、Wi-Fi への接続、ユーザー アカウントの作成、アプリのダウンロードなど） をやり直す必要があります。

1. 設定アプリを起動し、[**更新**] > [**回復**] の順に選択します。
1. [**デバイスのリセット**] オプションを選択し、確認メッセージを読みます。
1. リセットを確認します。 デバイスが再起動し、回転する歯車とプログレス バーのセットが表示されます。
1. このプロセスが完了するまで約 30 分待ちます。 リセットが完了し、デバイスは 「すぐに使用可能」 な状態で再起動します。

## オペレーティング システムを再インストールする

再起動してリセットした後もデバイスに問題がある場合は、コンピューターの回復ツールを使用して、HoloLens のオペレーティング システムとファームウェアを再インストールできます。  

HoloLens がリセットに必要とするデータは、.iso、.wim、または .vhd ファイルに似たフル フラッシュ アップデート （FFU） にパッケージ化されています。 [FFU 画像ファイル形式について学習します。](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Windows Device Recovery Tool を使用して、HoloLens (第 1 世代) に新しいオペレーティング システムをインストールできます。 このツールを使用する前に、HoloLens を再起動またはリセットすると問題が解決するかどうかを確認してください。

回復プロセスには時間がかかる場合があります。 完了すると、Windows Holographic ソフトウェアの最新バージョンがインストールされます。

このツールを使用するには、Windows 10 以降を実行し、4 GB 以上の空き容量があるコンピューターが必要です。 このツールを仮想マシンで実行することはできません。

### HoloLens を回復する

1. コンピューターに [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) をダウンロードしてインストールします。
1. HoloLens に付属の Micro USB ケーブルを使用して、HoloLens (第 1 世代) をコンピューターに接続します。
1. Windows Device Recovery Tool を開き、指示に従います。

HoloLens (1 番目の世代) が自動的に検出されない場合は、[**デバイスが検出されませんでした**] を選びます。 次に、指示に従ってデバイスを回復モードにします。

### 手動フラッシュ モード

デバイスが検出されない場合は、次の手順に従って、フラッシュ モードにします。

1. すべての電源からデバイスを取り外します。
1. デバイスがオンになっている場合は、完全にオフになるまで **電源** ボタンを押し続けてください。
2. [**音量を上げる**] ボタンを押したまま、**電源** ボタンを軽くタップします。 デバイスが起動し、中央の LED ライトのみが表示されます。
3. デバイスを PC に接続します。
4. Windows Device Recovery Tool を開きます。
5. [**デバイスが検出されませんでした**]、**HoloLens** の順に選択します。 
6. 指示に従ってデバイスを回復します。
