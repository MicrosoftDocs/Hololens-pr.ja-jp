---
title: HoloLens 1 の再起動、リセット、または回復
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Windows デバイス回復ツールを使用して HoloLens 第 1 世代にイメージをフラッシュする方法。
keywords: 方法, 再起動, リセット, 回復, ハード リセット, ソフト リセット, 電源サイクル, HoloLens, シャットダウン, wdrt, Windows デバイス回復ツール
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f855aa84a347edc85e5b9f02458721778eb2515a
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397693"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>HoloLens の再起動、リセット、または復旧 (第 1 世代)

HoloLens で問題が発生している場合は、再起動またはリセットを試したり、デバイスの回復を使用してデバイスを再フラッシュしたりすることもできます。 この記事では、推奨される復旧手順を順番に説明します。

アプリケーションの復旧を行う場合HoloLens 2プロセスが異なHoloLens 2の復旧[](https://docs.microsoft.com/hololens/hololens-recovery)に関するページを参照してください。

> [!NOTE]
> この記事では、HoloLens デバイスとソフトウェアについて重点的に取り上にします。 ホログラムが正しそうに見えない場合は、ホログラムの品質を向上させる要因の詳細については **[、「HoloLens](hololens-environment-considerations.md)** 環境に関する考慮事項」を参照してください。

## <a name="restart"></a>やり直し

### <a name="do-a-safe-restart-by-using-cortana"></a>Cortana を使用して安全な再起動を行う

HoloLens を再起動する最も安全な方法は Cortana を使用する方法です。これは、通常、HoloLens で問題が発生した場合に最初に試す方法です。

> [!NOTE] 
> Cortana は、すべてのデバイスで使用できるとは言えす。
> - Cortana は、すべての HoloLens (第 1 世代) デバイスで使用できます。 
> - Cortana は、Windows Holograpic バージョン 2004 更新プログラムより前のビルドHoloLens 2デバイスで利用できます。

1. HoloLens を有効にする。
1. ユーザーがログインし、デバイスがパスワードのロック解除を待機していない状態にしてください。
2. "Hey Cortana, reboot" または "Hey Cortana, restart" と言います。
3. Cortana が応答し、確認を求めるメッセージが表示されます。 質問の後にサウンドが再生されるのを待ち、"はい" と言います。 デバイスが再起動します。

### <a name="use-the-power-button-to-do-a-safe-restart"></a>[電源] ボタンを使用して安全に再起動する

それでもデバイスを再起動できない場合は、 **電源** ボタンを使用してデバイスを再起動してみてください。

1. 5秒間、 **電源** ボタンを押したままにします。 1秒後に、5つのすべての Led が点灯し、右から左に1ずつ徐々にオフになります。 5秒後、すべての Led はオフになり、正常にシャットダウンされたことを示します。
      
   > [!IMPORTANT]
   > すべての Led がオフになった直後にボタンを押すのを止めます。
1. シャットダウンが完了するまで1分待ちます。 ディスプレイがオフになった後も、シャットダウンが進行中である可能性があります。
2. 1秒間、電源ボタンを押したままデバイスの **電源** を再度オンにします。

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Windows デバイスポータルを使用して安全に再起動する

> [!NOTE]
> このプロセスでは、HoloLens を開発者デバイスとして構成する必要があります。 詳細については、「 [Windows デバイスポータル](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)」を参照してください。

前の手順が機能しなかった場合は、 [Windows デバイスポータル](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)を使用してデバイスを再起動してみてください。 右上隅で、デバイスを再起動またはシャットダウンするオプションを見つけます。

### <a name="do-an-unsafe-forced-restart"></a>安全でない強制再起動の実行

前の方法で HoloLens を再起動しなかった場合は、強制的に再起動します。 この方法は、バッテリを取り外して再インストールすることと同じです。 デバイスが破損した状態のままになる可能性があるため、危険です。 そのような場合は、HoloLens をフラッシュする必要があります。  

> [!WARNING]
> これは有害な可能性があるメソッドであり、前述のメソッドが機能しなかった場合にのみ使用してください。

1. 電源ボタンを **少なくとも** 10 秒間長押しします。
   - ボタンを 10 秒以上保持しても問題ありません。
   - LED アクティビティは無視しても安全です。
1. ボタンを離し、2 ~ 3 秒待ちます。
1. 電源ボタンを **1** 秒間長押しします。
1. それでも問題が解決しない場合は、電源ボタンを 4 秒間押します。すべてのバッテリ インジケーターがフェードアウトし、画面にホログラムが表示されなくなってきます。 1 分待った後、もう一度電源ボタン **を** 押してデバイスをオンにします。

## <a name="reset-to-factory-settings"></a>出荷時の設定にリセットする

> [!NOTE]
> バッテリをリセットするには、少なくとも 40% の充電が必要です。

HoloLens に問題がある場合は、出荷時の状態にリセットしてみてください。 この手順では、インストールされている Windows Holographic ソフトウェアのバージョンを保持し、それ以外のすべてを出荷時の設定に返します。

>[!WARNING]
> デバイスをリセットすると、TPM リセット情報を含むすべての個人データ、アプリ、および設定が消去されます。 リセットでは、インストールされている最新バージョンの Windows Holographic だけがインストールされます。 すべての初期化手順をやり直す必要があります (調整、Wi-Fi への接続、ユーザー アカウントの作成、アプリのダウンロードなど)。

1. [設定] アプリを開き、[回復の更新]**を**  >  **選択します**。
1. [デバイスの **リセット] オプションを** 選択し、確認メッセージを読み取ります。
1. リセットを確認します。 デバイスが再起動し、一連の回転する歯車と進行状況バーが表示されます。
1. このプロセスが完了するまで約 30 分待ちます。 完了すると、デバイスは "Out-of-the-box" エクスペリエンスに再起動されます。

## <a name="reinstall-the-operating-system"></a>オペレーティングシステムを再インストールする

再起動およびリセット後もデバイスに問題が発生する場合は、コンピューターで回復ツールを使用して、HoloLens オペレーティングシステムとファームウェアを再インストールできます。  

HoloLens がリセットに必要とするデータは完全な Flash 更新プログラム (FFU) にパッケージ化されています。これは、.iso、.wim、.vhd ファイルに似ています。 [FFU イメージファイル形式について説明します。](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Windows デバイスの回復ツールを使用して、HoloLens (第1世代) に新しいオペレーティングシステムをインストールできます。 このツールを使用する前に、「HoloLens を再起動またはリセットすると問題が修正される」を参照してください。

回復プロセスには時間がかかることがあります。 完了すると、最新バージョンの Windows Holographic ソフトウェアがインストールされます。

このツールを使用するには、少なくとも 4 GB の空き領域がある Windows 10 以降を実行しているコンピューターが必要です。 仮想マシンでこのツールを実行することはできません。

### <a name="recover-your-hololens"></a>HoloLens を回復する

1. [Windows デバイス回復ツール](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)をコンピューターにダウンロードしてインストールします。
1. Hololens に付属しているマイクロ USB ケーブルを使用して、HoloLens をコンピューターに接続します。
1. Windows デバイスの回復ツールを開き、指示に従います。

HoloLens (第1世代) が自動的に検出されなかった場合は、[ **デバイスが検出されませんでした**] を選択します。 次に、指示に従って、デバイスを回復モードにします。

### <a name="manual-flashing-mode"></a>手動フラッシュモード

デバイスが検出されない場合は、次の手順に従って、フラッシュモードにします。

1. 任意の電源からデバイスを取り外します。
1. デバイスがオンになっている場合は、 **電源** ボタンを押したままにすると、完全にオフになります。
2. 音量を **上げボタン** を押したまま、電源ボタンを簡単 **にタップ** します。 デバイスが起動し、中央の LED のみを表示する必要があります。
3. デバイスを PC に接続します。
4. Windows デバイス回復ツールを開きます。
5. [**デバイスが検出されない] を選択し****、[HoloLens] を選択します**。 
6. 指示に従ってデバイスを回復します。
