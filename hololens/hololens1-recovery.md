---
title: HoloLens 1 を再起動、リセット、または回復する
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Windows デバイス回復ツールを使用してイメージを HoloLens 最初の世代にフラッシュする方法。
keywords: 操作方法、再起動、リセット、回復、ハードリセット、ソフトリセット、電源サイクル、HoloLens、シャットダウン、wdrt、windows デバイス回復ツール
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
ms.openlocfilehash: d6eb706c50e97a81910180c70be1d9dbc52bc6603cbc77ad130c1dd3b6a9010e
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661806"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>HoloLens の再起動、リセット、または回復 (第1世代)

HoloLens で問題が発生している場合は、再起動またはリセットするか、デバイスの回復を使用してデバイスを更新することもできます。 この記事では、推奨される回復手順について順を追って説明します。

HoloLens 2 の回復を検討している場合は、「 [HoloLens 2 の回復](hololens-recovery.md)」を参照してください。

> [!NOTE]
> この記事では、HoloLens デバイスとソフトウェアに焦点を当てています。 ホログラムが正しく表示されない場合は、「 **[HoloLens 環境に関する考慮事項](hololens-environment-considerations.md)**」で、ホログラムの品質を向上させる要因についての情報を参照してください。

## <a name="restart"></a>やり直し

### <a name="do-a-safe-restart-by-using-cortana"></a>Cortana を使用して安全に再起動する

HoloLens を再起動する最も安全な方法は、Cortana を使用することです。これは通常、HoloLens に関する問題が発生したときに最初に試みることになります。

> [!NOTE] 
> Cortana は、すべてのデバイスで使用できるわけではありません。
> - Cortana は、すべての HoloLens (第1世代) デバイスで使用できます。 
> - Cortana は、Windows Holograpic バージョン 2004 update より前のビルドの HoloLens 2 デバイスで使用できます。

1. HoloLens をオンにします。
1. ユーザーがログインしていて、デバイスがパスワードのロックを解除するのを待機していないことを確認します。
2. 「Cortana、再起動」、Cortana 「再起動についてはこんにちは」と言います。
3. Cortana が応答し、確認を求めるメッセージが表示されます。 質問の後にサウンドが再生されるのを待ってから、「はい」と言います。 デバイスが再起動されます。

### <a name="use-the-power-button-to-do-a-safe-restart"></a>[電源] ボタンを使用して安全に再起動する

それでもデバイスを再起動できない場合は、 **電源** ボタンを使用してデバイスを再起動してみてください。

1. 5秒間、 **電源** ボタンを押したままにします。 1秒後に、5つのすべての Led が点灯し、右から左に1ずつ徐々にオフになります。 5秒後、すべての Led はオフになり、正常にシャットダウンされたことを示します。
      
   > [!IMPORTANT]
   > すべての Led がオフになった直後にボタンを押すのを止めます。
1. シャットダウンが完了するまで1分待ちます。 ディスプレイがオフになった後も、シャットダウンが進行中である可能性があります。
2. 1秒間、電源ボタンを押したままデバイスの **電源** を再度オンにします。

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Windows デバイスポータルを使用して安全に再起動する

> [!NOTE]
> このプロセスでは、HoloLens を開発者デバイスとして構成する必要があります。 詳細については、 [Windows デバイスポータル](/windows/mixed-reality/using-the-windows-device-portal)」を参照してください。

前の手順が機能しなかった場合は、 [Windows デバイスポータル](/windows/mixed-reality/using-the-windows-device-portal)を使用してデバイスを再起動してみてください。 右上隅で、デバイスを再起動またはシャットダウンするオプションを見つけます。

### <a name="do-an-unsafe-forced-restart"></a>安全でない強制再起動の実行

前の方法で HoloLens を再起動しなかった場合は、強制的に再起動します。 この方法は、バッテリを取り外して再インストールすることと同じです。 デバイスが破損した状態のままになる可能性があるため、危険です。 そのような場合は、HoloLens をフラッシュする必要があります。  

> [!WARNING]
> これは有害な可能性があるメソッドであり、前述のメソッドが機能しなかった場合にのみ使用してください。

1. 少なくとも10秒間、 **電源** ボタンを押したままにします。
   - ボタンは10秒より長く保持できます。
   - LED の動作を無視しても安全です。
1. ボタンを離し、2-3 秒間待機します。
1. 1秒間、 **電源** ボタンを押したままにします。
1. それでも問題が発生する場合は、 **電源** ボタンを4秒押して、すべてのバッテリインジケーターがフェードアウトし、画面がホログラムの表示を停止します。 1分待ってから、もう一度 **電源** ボタンを押してデバイスの電源を入れます。

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>前のバージョン HoloLens に戻る (第1世代)

場合によっては、以前のバージョンの HoloLens ソフトウェアに戻る必要があります。 これを行うには、Windows デバイスの回復ツールを使用して、HoloLens を以前のバージョンにリセットします。

> [!NOTE]
> 以前のバージョンに戻すと、個人用ファイルと設定が削除されます。

以前のバージョンの HoloLens 1 に戻るには、次の手順を実行します。

1. PC に接続されている携帯電話や Windows デバイスがないことを確認します。
1. PC で、 [Windows Device Recovery Tool (wdrt)](https://support.microsoft.com/help/12379)をダウンロードします。
1. [HoloLens Anniversary Update 回復パッケージ](https://aka.ms/hololensrecovery)をダウンロードします。
1. ダウンロードが完了したら、**エクスプローラー** の [ダウンロード] を開き  >  ます。 ダウンロードした zip 形式のフォルダーを右クリックし、[**すべて** 抽出] を選択し  >  て解凍します。
1. 付属のマイクロ USB ケーブルを使用して、HoloLens を PC に Connect します。 (他のケーブルを使って HoloLens に接続していたとしても、この方法は最適です)。
1. WDRT は、HoloLens を自動的に検出します。 **[Microsoft HoloLens]** タイルを選択します。
1. 次の画面で、[ **パッケージの手動選択** ] を選択し、手順 4. で解凍したフォルダーに格納されているインストールファイルを選択します。 (拡張子が ffu のファイルを探します。)
1. [ **ソフトウェアのインストール**] を選択し、指示に従います。

> [!NOTE]
> wdrt によって HoloLens が検出されない場合は、PC を再起動してみてください。 それでも機能しなかった場合は **[デバイスが検出されていない]** を選択し、 **[Microsoft HoloLens]** を選択して、指示に従います。

## <a name="reset-to-factory-settings"></a>工場出荷時の設定にリセットする

> [!NOTE]
> バッテリのリセットには、少なくとも40% の料金が必要です。

HoloLens に問題が解決しない場合は、工場出荷時の状態にリセットしてみてください。 このステップでは、インストールされている Windows Holographic ソフトウェアのバージョンを保持し、他のすべてを出荷時の設定に戻します。

>[!WARNING]
> デバイスをリセットすると、すべての個人データ、アプリ、および設定が削除されます (TPM リセット情報も含む)。 リセットすると、Windows Holographic のインストールされている最新バージョンのみがインストールされます。 すべての初期化手順 (調整、Wi-fi への接続、ユーザーアカウントの作成、アプリのダウンロードなど) を再実行する必要があります。

1. 設定アプリを開き、[**更新**] [回復] の順に選択し  >  ます。
1. [ **デバイスのリセット** ] オプションを選択し、確認メッセージを確認します。
1. リセットを確認します。 デバイスが再起動し、スピン歯車と進行状況バーのセットが表示されます。
1. このプロセスが完了するまで約30分待ちます。 この処理が完了すると、デバイスはすぐに使えるようになります。

## <a name="reinstall-the-operating-system"></a>オペレーティングシステムを再インストールする

再起動およびリセット後もデバイスに問題が発生する場合は、コンピューターで回復ツールを使用して、HoloLens オペレーティングシステムとファームウェアを再インストールできます。  

リセットに必要な HoloLens データは、.iso、.wim、.vhd ファイルに似た完全な Flash 更新プログラム (ffu) にパッケージ化されます。 [FFU イメージファイル形式について説明します。](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Windows デバイスの回復ツールを使用して、HoloLens (第1世代) に新しいオペレーティングシステムをインストールできます。 このツールを使用する前に、HoloLens の再起動またはリセットによって問題が解決されるかどうかを確認してください。

回復プロセスには時間がかかることがあります。 完了すると、Windows Holographic ソフトウェアの最新バージョンがインストールされます。

このツールを使用するには、少なくとも 4 GB の空き記憶領域がある Windows 10 以降を実行するコンピューターが必要です。 仮想マシンでこのツールを実行することはできません。

### <a name="recover-your-hololens"></a>HoloLens の回復

1. [Windows デバイス回復ツール](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)をコンピューターにダウンロードしてインストールします。
1. HoloLens に付属しているマイクロ USB ケーブルを使用して、HoloLens (第1世代) をコンピューターに Connect します。
1. Windows デバイスの回復ツールを開き、指示に従います。

HoloLens (第1世代) が自動的に検出されなかった場合は、[**デバイスが検出されませんでした**] を選択します。 次に、指示に従って、デバイスを回復モードにします。

### <a name="manual-flashing-mode"></a>手動フラッシュモード

デバイスが検出されない場合は、次の手順に従って、フラッシュモードにします。

1. 任意の電源からデバイスを取り外します。
1. デバイスがオンになっている場合は、 **電源** ボタンを押したままにすると、完全にオフになります。
2. 音量を **上げボタン** を押したまま、電源ボタンを簡単 **にタップ** します。 デバイスが起動し、中央の LED のみを表示する必要があります。
3. デバイスを PC に接続します。
4. Windows Device Recovery ツールを開きます。
5. [**デバイスが検出されていない] を選択し**、**をHoloLens。** 
6. 指示に従ってデバイスを回復します。
