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
ms.openlocfilehash: 5963be84a5fbb186c77965d9bbf112713fea8242
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923518"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>HoloLens の再起動、リセット、または復旧 (第 1 世代)

HoloLens で問題が発生している場合は、再起動またはリセットを試したり、デバイスの回復を使用してデバイスを再フラッシュしたりすることもできます。 この記事では、推奨される復旧手順を順番に説明します。

アプリケーションの復旧を行う場合HoloLens 2プロセスが異なHoloLens 2の復旧[](hololens-recovery.md)に関するページを参照してください。

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

### <a name="use-the-power-button-to-do-a-safe-restart"></a>電源ボタンを使用して安全な再起動を行う

それでもデバイスを再起動できない場合は、電源ボタンを使用して **再起動してみてください。**

1. 電源ボタンを5 秒間長押しします。 1 秒後、5 つの LED すべてが点灯し、右から左に 1 つ 1 つ徐々にオフになります。 5 秒後、すべての LED がオフになります。シャットダウンが成功したことを示します。
      
   > [!IMPORTANT]
   > すべての LED がオフになった直後に、ボタンの押しを停止します。
1. シャットダウンが完了するまで 1 分待ちます。 表示をオフにした後でも、シャットダウンは進行中である可能性があります。
2. 電源ボタンを 1 秒間長押し **して、デバイス** の電源を再びオンにします。

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>を使用して安全な再起動を行Windows デバイス ポータル

> [!NOTE]
> このプロセスでは、HoloLens を開発者デバイスとして構成する必要があります。 詳細については、「 」を[参照Windows デバイス ポータル。](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)

前の手順で問題が発生した場合は、 を使用してデバイスを[再起動Windows デバイス ポータル。](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 右上隅で、デバイスを再起動またはシャットダウンするオプションを探します。

### <a name="do-an-unsafe-forced-restart"></a>安全でない強制再起動を実行する

前のメソッドで HoloLens が再起動しなかった場合は、強制的に再起動します。 この方法は、バッテリの取り外しと再インストールに相当します。 デバイスが破損した状態になる可能性があるため、危険です。 その場合は、HoloLens をフラッシュする必要があります。  

> [!WARNING]
> これは害を及ぼす可能性のあるメソッドであり、以前に引用したメソッドが機能しなかった場合にのみ使用する必要があります。

1. 電源ボタンを **少なくとも** 10 秒間長押しします。
   - ボタンを 10 秒以上保持しても問題ありません。
   - LED アクティビティは無視しても安全です。
1. ボタンを離し、2 ~ 3 秒待ちます。
1. 電源ボタンを **1** 秒間長押しします。
1. それでも問題が解決しない場合は、電源ボタンを 4 秒間押します。すべてのバッテリ インジケーターがフェードアウトし、画面にホログラムが表示されなくなってきます。 1 分待った後、もう一度電源ボタン **を** 押してデバイスをオンにします。

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>以前のバージョンに戻る - HoloLens (第 1 世代)

場合によっては、以前のバージョンの HoloLens ソフトウェアに戻したい場合があります。 これを行うには、Windows デバイス回復ツールを使用して HoloLens を以前のバージョンにリセットします。

> [!NOTE]
> 以前のバージョンに戻って、個人用ファイルと設定が削除されます。

以前のバージョンの HoloLens 1 に戻る場合は、次の手順に従います。

1. PC にスマートフォンや Windows デバイスが接続されていないことを確認します。
1. PC で [、Windows Device Recovery Tool (WDRT) をダウンロードします](https://support.microsoft.com/help/12379)。
1. [HoloLens Anniversary Update 回復パッケージ をダウンロードします](https://aka.ms/hololensrecovery)。
1. ダウンロードが完了したら、エクスプローラーの [**ダウンロード]**  >  **を開きます**。 ダウンロードした zip 形式のフォルダーを右クリックし、[すべての抽出] を **選択** して  >  解凍します。
1. 付属のマイクロ USB ケーブルを使用して、HoloLens を PC に接続します。 (他のケーブルを使用して HoloLens を接続している場合でも、これは最適です)。
1. WDRT によって HoloLens が自動的に検出されます。 [新 **しい** Microsoft HoloLens選択します。
1. 次の画面で、[手動 **パッケージの** 選択] を選択し、手順 4. で展開したフォルダーに含まれているインストール ファイルを選択します。 (拡張子が .ffu のファイルを探します)。
1. [ **ソフトウェアのインストール] を** 選択し、指示に従います。

> [!NOTE]
> WDRT で HoloLens が検出されない場合は、PC の再起動を試してください。 それでも問題が生じなかった場合は、[デバイスが検出されない] を選択し、[Microsoft HoloLens]**を** 選択して、指示に従います。

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

## <a name="reinstall-the-operating-system"></a>オペレーティング システムを再インストールする

再起動とリセット後もデバイスで問題が解決しない場合は、コンピューターの回復ツールを使用して、HoloLens オペレーティング システムとファームウェアを再インストールできます。  

HoloLens がリセットに必要なデータは、フル フラッシュ更新 (FFU) にパッケージ化されます。これは、.iso、.wim、または .vhd ファイルに似ています。 [FFU イメージ ファイル形式について学習します。](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Windows デバイス回復ツールを使用して、HoloLens (第 1 世代) に新しいオペレーティング システムをインストールできます。 このツールを使用する前に、HoloLens の再起動またはリセットによって問題が解決される場合を確認してください。

復旧プロセスには時間がかかる場合があります。 完了すると、最新バージョンの Windows Holographic ソフトウェアがインストールされます。

このツールを使用するには、少なくとも 4 GB の空きWindows 10空き領域があるコンピューターが必要です。 仮想マシンでこのツールを実行できない。

### <a name="recover-your-hololens"></a>HoloLens を回復する

1. コンピューターに [Windows Device Recovery ツールをダウンロードして](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) インストールします。
1. HoloLens に付属のマイクロ USB ケーブルを使用して、HoloLens (第 1 世代) をコンピューターに接続します。
1. Windows デバイス回復ツールを開き、指示に従います。

HoloLens (第 1 世代) が自動的に検出されない場合は、[デバイスが検出されません] **を選択します**。 次に、指示に従ってデバイスを回復モードにします。

### <a name="manual-flashing-mode"></a>手動フラッシュ モード

デバイスが検出されない場合は、次の手順に従ってフラッシュ モードにします。

1. 任意の電源からデバイスを取り外します。
1. デバイスがオンの場合は、電源ボタン **が完全** にオフになるまで押したままにします。
2. [ **音量** ] ボタンを押したまま、[ **電源** ] ボタンを簡単にタップします。 デバイスが起動し、中央の LED のみが表示されます。
3. デバイスを PC に接続します。
4. Windows デバイスの回復ツールを開きます。
5. [ **デバイスは検出されませんでした** ]、[ **HoloLens**] の順に選択します。 
6. 指示に従って、デバイスを回復します。
