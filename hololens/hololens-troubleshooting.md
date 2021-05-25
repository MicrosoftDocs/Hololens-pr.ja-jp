---
title: トラブルシューティング
description: HoloLens デバイスの問題とトラブルシューティング手法に関する最も一般的な解決策については、最新情報を入手してください。
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: 懸案事項, バグ, トラブルシューティング, 修正, ヘルプ, サポート, HoloLens
ms.openlocfilehash: 1039af533b5039eb4eef6599c7cbb480955b0661
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397263"
---
# <a name="troubleshoot-common-issues"></a>一般的な問題のトラブルシューティング

この記事では、いくつかの一般的な HoloLens の問題を解決する方法について説明します。

## <a name="my-hololens-is-unresponsive-or-wont-start"></a>HoloLens が応答していないか、起動しない

HoloLens が開始されない場合:

- 電源ボタンの横にある Led が点灯していない場合、または1つの LED だけが少し点滅している場合は、 [HoloLens の料金を支払う](hololens-recovery.md#charge-the-device)必要があります。
- 電源ボタンを押したときに Led が点灯しても、ディスプレイに何も表示されない場合は、 [検査によってデバイスのハードリセットが](hololens-recovery.md#hard-reset-procedure)発生します。

HoloLens がフリーズまたは応答しなくなった場合:

- 5つの Led がすべてオフになるまで電源ボタンを押すか、Led が応答していない場合は15秒間、HoloLens をオフにします。 HoloLens を開始するには、もう一度 [電源] ボタンを押します。

これらの手順がうまくいかない場合は、 [hololens 2 デバイス](hololens-recovery.md)または[hololens (第1世代) デバイス](hololens1-recovery.md)の復旧を試すことができます。

## <a name="holograms-dont-look-good"></a>ホログラムが正しく表示されない

ホログラムが不安定な場合、過敏ていない場合、または正しく表示されない場合は、次を試してください。

- HoloLens の前面にあるデバイスのバイザーとセンサーバーをクリーニングします。
- 部屋の光を増やします。
- お客様の環境を調べて、HoloLens がより完全にスキャンできるようにします。
- お客様の HoloLens を調整します。 [**設定**] [システムユーティリティ] にアクセス  >    >  します。 [ **調整**] で [ **調整を開く**] を選択します。
 
### <a name="reporting-issues-where-holograms-are-unstable-or-dont-look-right"></a>ホログラムが不安定であるか、または正しくない問題を報告しています
 
1. 問題のビデオ [とMixed Reality キャプチャビデオ](holographic-photos-and-videos.md#capture-a-mixed-reality-video) を記録してください。 このビデオは、後で添付ファイルとして フィードバック Hubアップロードできます。  
1. [設定アプリ] -> **[** プライバシー診断] & フィードバックを使用して完全なテレメトリを有効にし、[オプションの診断データ] でトグルを[オン]  ->  に設定 **します**
1. 最新の [Windows Holographic OS (20H2](hololens-release-notes.md#windows-holographic-version-20h2)以上) に更新することで、ホログラムのスケールと安定性に関する最新の修正プログラムを取得します。 更新後、次の手順を実行します。
    1. [設定] アプリ-> **[** システム ホログラム] ->を使用してすべてのホログラムを削除し、[すべてのホログラムを削除] を選択し、新しい  ->  マップから開始します。
    1. HoloLens を装着し、部屋を歩き回り、空間内のすべての領域と表面を見て、空間の新しいマップを作成します。 これを 2 ~ 3 分間実行します。
    1. IPD 調整を実行します。 [設定] **[**  >  **システム ユーティリティ]**  >  **に移動します**。 [調整 **] で**、[ 調整を **開く] を選択します**。
    1. シナリオを再テストし、引き続き永続化されるかどうかを確認します。
1. 更新しても問題が解決しない場合は、問題を報告フィードバック Hub [してください](hololens-feedback.md)。 フィードバックを入力した後は、[共有]ボタンを使用して、サポートに連絡するときに送信できる簡単に共有できるリンクを作成できます。

## <a name="hololens-doesnt-respond-to-hand-input"></a>HoloLens が手入力に応答しない

HoloLens が手を確実に表示するには、ジェスチャ フレーム内に保持する必要があります。  [Mixed Reality ホーム] には、手がいつ追跡されるのか知るフィードバックが提供されます。  フィードバックは、HoloLens のバージョンによって異なります。
- HoloLens (第 1 世代) では、視線カーソルがドットからリングに変わります
- このHoloLens 2、手がスレートに近いときに指先カーソルが表示され、スレートが離れたときに手の光線が表示されます

多くのイマーシブアプリは、Mixed Reality ホームに似た入力パターンに従います。  [Hololens (第1世代)](hololens1-basic-usage.md#use-hololens-with-your-hands)と[hololens 2](hololens2-basic-usage.md#the-hand-tracking-frame)で手書き入力を使用する方法の詳細については、こちらを参照してください。

手袋を装着している場合は、一部の種類の手袋がハンドトラッキングで動作しないことに注意してください。  一般的な例としては、赤外線信号を吸収する傾向があり、深度カメラでは選択されていない黒色のゴムグローブがあります。  ゴムグローブが使用されている場合は、青や灰色などの明るい色を試すことをお勧めします。  もう1つの例として、大きな baggy グローブがあります。これは、手の形が見えにくくなる傾向があります。 最良の結果を得るには、できるだけフォーム継ぎ手として手袋を使用することをお勧めします。

バイザーに指紋または汚れがある場合は、HoloLens に付属している microfiber 掃除布を使用して、バイザーをゆっくりとクリーニングします。

## <a name="hololens-doesnt-respond-to-my-voice-commands"></a>HoloLens が音声コマンドに応答しない

Cortana が音声コマンドに応答しない場合は、Cortana が有効になっていることを確認します。 [すべてのアプリ] の一覧で、[ **Cortana** メニューノートブックの設定] を選択して  >    >    >  変更を行います。 説明できることの詳細については、「 [HoloLens での音声の使用](hololens-cortana.md)」を参照してください。

## <a name="i-cant-place-holograms-or-see-holograms-that-i-previously-placed"></a>ホログラムを配置できない、または以前に配置したホログラムを表示できない

HoloLens がスペースをマップまたは読み込むことができない場合、制限モードになり、ホログラムを配置したり、配置したホログラムを表示したりすることはできません。 以下のことを試してみてください。

- HoloLens が領域を参照してマップできるように、環境内に十分な光があることを確認します。
- Wi-Fi ネットワークに接続していることを確認します。 Wi-fi に接続していない場合、HoloLens は既知の領域を特定して読み込むことができません。
- 新しいスペースを作成する必要がある場合は、Wi-fi に接続してから、HoloLens を再起動します。
- 正しい領域がアクティブかどうかを確認したり、手動で領域を読み込んだりするには、[**設定**] [システム領域] にアクセスし  >    >  ます。
- 適切な領域が読み込まれても問題が解決しない場合は、領域が破損している可能性があります。 この問題を解決するには、スペースを選択し、 [削除] を **選択します**。 スペースを削除すると、HoloLens によって周囲のマップが開始され、新しいスペースが作成されます。

## <a name="my-hololens-cant-tell-what-space-im-in"></a>HoloLens で、自分が入っている領域を見分けできない

HoloLens で、自分が入っている領域を自動的に識別して読み込めなかった場合は、次の要因を確認します。

- 接続されていることを確認Wi-Fi
- 部屋に十分な光が入っているのを確認する
- 周囲に大きな変更が加えっていないか確認します。

[設定] [システムスペース] に移動して、スペースを手動で読み込むか、スペース  >  **を管理**  >  **することもできます**。

## <a name="im-getting-a-low-disk-space-error"></a>"ディスク領域が少ない" エラーが発生する

次の 1 つ以上を実行して、一部の記憶域スペースを解放する必要があります。

- 未使用のスペースを削除します。 [設定]  >  **[システム**  >  **スペース]** に移動し、不要になった領域を選択して、[削除] を **選択します**。
- 配置したホログラムの一部を削除します。
- フォト アプリからいくつかの画像とビデオを削除します。
- HoloLens から一部のアプリをアンインストールします。 [すべての **アプリ] の一** 覧で、アンインストールするアプリをタップしたままにし、[ アンインストール] を **選択します**。

## <a name="my-hololens-cant-create-a-new-space"></a>HoloLens で新しい領域を作成できない

最も可能性の高い問題は、記憶域スペースが少なかっているという問題です。 前のヒントのいずれかを [試して、](#im-getting-a-low-disk-space-error) ディスク領域を解放してください。

## <a name="the-hololens-emulator-isnt-working"></a>HoloLens エミュレーターが動作しない

HoloLens エミュレーターに関する情報は、開発者向けドキュメントに記載されています。  [HoloLens エミュレーターのトラブルシューティングの](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)詳細については、こちらを参照してください。
