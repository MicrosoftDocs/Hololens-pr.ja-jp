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
ms.openlocfilehash: f57aea52337f7ca7e15bda1363f73a3a7265a025
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309516"
---
# <a name="troubleshooting"></a>トラブルシューティング

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
 
1. 問題のビデオを記録し、 [Mixed Reality をキャプチャ](holographic-photos-and-videos.md#capture-a-mixed-reality-video) してください。 このビデオは、後でフィードバックハブを使用して添付ファイルとしてアップロードできます。  
1. **設定** アプリを使用して完全なテレメトリを有効にする->**プライバシー**  ->  **診断 & のフィードバック** と、**オプションの診断データ** で、トグルが **On** に設定されていることを確認します。
1. 最新の [Windows HOLOGRAPHIC OS (20H2 以降)](hololens-release-notes.md#windows-holographic-version-20h2)に更新して、最新のホログラムスケールと安定性の修正を取得します。 更新後、次の手順を実行します。
    1. **設定** アプリを使用してすべてのホログラムを削除する->**システム**  ->  **ホログラム**-> [**すべてのホログラムを削除** し、新しいマップで開始する] を選択します。
    1. HoloLens を装着して部屋に移動し、空間内のすべての領域とサーフェイスを確認することで、スペースの新しいマップを作成します。 これは、2-3 分間実行します。
    1. IPD の調整を実行します。 [**設定**] [システムユーティリティ] にアクセス  >    >  します。 [ **調整**] で [ **調整を開く**] を選択します。
    1. シナリオを再テストし、まだ永続化されているかどうかを確認します。
1. 更新によって問題が解決されない場合は、 [フィードバックハブの問題](hololens-feedback.md)を報告してください。 フィードバックを入力したら、[ **共有** ] ボタンを使用して、サポートに連絡するときに送信できる、共有の簡単なリンクを作成できます。

## <a name="hololens-doesnt-respond-to-hand-input"></a>HoloLens が手入力に応答しない

HoloLens が自分の手を見えるようにするには、それらをジェスチャフレームに保持する必要があります。  Mixed Reality ホームでは、自分がどのように追跡されるかを知ることができるフィードバックが提供されます。  このフィードバックは、HoloLens のバージョンによって異なります。
- HoloLens (第1世代) では、宝石カーソルがドットからリングに変わります。
- HoloLens 2 では、指先カーソルは、手がスレートの近くにあるときに表示され、スレートがさらに離れたときにハンドレイが表示されます。

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
- 適切な領域が読み込まれても問題が解決しない場合は、領域が破損している可能性があります。 この問題を解決するには、スペースを選択し、[ **削除**] を選択します。 この領域を削除すると、HoloLens は環境のマップを開始し、新しい領域を作成します。

## <a name="my-hololens-cant-tell-what-space-im-in"></a>HoloLens がどの領域に参加しているかを判別できない

HoloLens が自動的に使用している領域を特定して読み込むことができない場合は、次の要素を確認します。

- に接続されていることを確認し Wi-Fi
- 部屋に十分な光があることを確認します。
- 周囲に大きな変更がないことを確認します。

また、領域を手動で読み込むか、または **設定** システム領域に移動して、スペースを管理することもでき  >    >  ます。

## <a name="im-getting-a-low-disk-space-error"></a>"ディスク領域が不足しています" というエラーが発生する

次の1つまたは複数の操作を行って、記憶域スペースを解放する必要があります。

- 未使用の領域をいくつか削除します。 [**設定**] [システム領域]  >    >  の順に選択し、不要になった領域を選択して、[**削除**] を選択します。
- 配置したホログラムの一部を削除します。
- 写真アプリから一部の画像とビデオを削除します。
- HoloLens から一部のアプリをアンインストールします。 [ **すべてのアプリ** ] 一覧で、アンインストールするアプリをタップして保持し、[ **アンインストール**] を選択します。

## <a name="my-hololens-cant-create-a-new-space"></a>HoloLens で新しいスペースを作成できない

最も可能性の高い問題は、記憶域スペースが不足していることです。 前のいずれかの [ヒント](#im-getting-a-low-disk-space-error) を試して、ディスク領域を解放してください。

## <a name="the-hololens-emulator-isnt-working"></a>HoloLens エミュレーターが動作していません

HoloLens エミュレーターに関する情報は、開発者向けドキュメントに記載されています。  [HoloLens エミュレーターのトラブルシューティングの](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)詳細については、こちらを参照してください。
