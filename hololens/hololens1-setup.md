---
title: 新しい HoloLens を準備する
description: 初めて HoloLens (第1世代) の mixed reality デバイスを準備、調整、設定する方法について説明します。
ms.prod: hololens
ms.sitesec: library
author: JesseMcCulloch
ms.author: jemccull
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/12/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- Hololens (1st gen)
ms.openlocfilehash: 5918e3dcb7f2504ae6e85cb584aaf21bc87217bc
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033651"
---
# <a name="get-your-hololens-1st-gen-ready-to-use"></a>HoloLens (第 1 世代) の使用準備

HoloLens (第1世代) を初めて設定するには、次の手順に従います。

## <a name="charge-your-hololens-1st-gen"></a>HoloLens の料金 (第1世代)

HoloLens を課金するには、付属のマイクロ USB ケーブルを使用して、電源装置を充電ポートに接続します。 その後、電源装置を電源コンセントに接続します。 デバイスの充電中は、バッテリインジケーターが波形パターンで点灯します。

![マイクロ USB ケーブルを HoloLens に接続する方法を示す画像。](./images/hololens-charging.png)

HoloLens がオンの場合、バッテリインジケーターには、バッテリレベルが増加して表示されます。 5 個のライトのうち 1 個しか点灯していない場合は、バッテリー レベルが 20 パーセントを下回っています。 バッテリー レベルが極端に低い場合にデバイスの電源を入れようとすると、1 個のライトが短く点滅してから消えます。

> [!TIP]
> 現在のバッテリレベルの推定値を取得するには、「バッテリ残量 (Cortana)」と言います。

デバイスに付属している電源と USB ケーブルは、HoloLens (第1世代) を請求するための最適な方法です。  電源装置には、18W の電力 (9V 2A) が用意されています。

充電率と速度は、デバイスが実行されている環境によって異なる場合があります。

## <a name="adjust-fit"></a>フィット調整

> [!VIDEO https://www.microsoft.com/videoplayer/embed/be3cb527-f2f1-4f85-b4f7-a34fbaba980d]

| &nbsp; | &nbsp; |
|:--- |:--- |
|1. ヘッドバンドを約20-30 度まで回転させます。|![ステップ1を実行し、ヘッドバンドを回転させます。](./images/FitGuideStep1.png)|
|2. ヘッドバンドをプッシュして戻します。 時間が経つにつれてバンドが破壊される可能性があるため、これをプルしたり、ヒンジの背後にあるバンドを操作したりしないでください。|![ステップ2では、ヘッドバンドを戻します。](./images/FitGuideStep2.png)|
|3. 調整ホイールをオンにして、すべての方向にヘッドバンドを拡張します。 |![手順 3. 調整ホイールを使用してヘッドバンドを延長します。](./images/FitGuideStep3.png)|
|4. デバイスのアームによってデバイスを保持し、ヘッドに配置します。 ヘッドバンドが、前の頭の一番上にあることを確認し、調整ホイールを締めます。|![手順 4. をデバイスに配置し、ヘッドバンドを調整します。](./images/FitGuideStep4.png)|
|5. バイザーをスライドバックし、デバイスの適合性を確認します。 ヘッドバンドは、耳の上にある、ヘアラインのすぐ下にある、耳の上に座っているはずです。 レンズが目の中央に配置されている必要があります。|![手順 5. で、バイザーをスライドバックし、適合することを確認します。](./images/FitGuideSetep5.png)|

## <a name="turn-on-your-hololens"></a>HoloLens をオンにする

電源ボタンを使用して、HoloLens のオンとオフを切り替えたり、スタンバイモードにしたりします。

![HoloLens 電源ボタンを表示するイメージ。](./images/hololens-power.png)

デバイスが応答しない場合、または起動しない場合は、「 [HoloLens の再起動、リセット、または回復](hololens-restart-recover.md)」を参照してください。

HoloLens がオフまたはスタンバイになっている場合は、1秒間電源ボタンを押してオンにします。 電源がオンになっていない場合は、接続し、少なくとも30分間課金します。

> [!TIP]
> Cortana HoloLens を再起動するには、デバイスを再起動してください。

### <a name="put-hololens-in-standby"></a>スタンバイに HoloLens を配置する

電源が入っている状態で HoloLens をスタンバイ状態にするには、電源ボタンを1回押します。 バッテリインジケーターが点滅します。 スタンバイから復帰させるには、もう一度 [電源] ボタンを押します。

HoloLens は、非アクティブな状態が3分続くと自動的にスタンバイ状態になります。 スタンバイ状態のときは、4時間後、またはバッテリレベルが10% 下がった後に、自動的にシャットダウンします。

### <a name="shut-down-hololens"></a>シャットダウン HoloLens

HoloLens をシャットダウン (オフ) するには、電源ボタンを4秒間押したままにします。 バッテリインジケーターは1つずつオフにし、デバイスはシャットダウンします。

電源が接続されている場合でも、バッテリレベルが1パーセントに低下すると、HoloLens は自動的にシャットダウンします。 バッテリを 3% recharged したら、再び HoloLens オンにすることができます。

## <a name="adjust-volume-and-brightness"></a>音量と明るさを調整する

[明るさ] ボタンと [音量] ボタンは、デバイスのアームボリュームの上にあり、 &mdash; 右側と明るさを左右します。

![HoloLens ボタンを表示する画像。](./images/hololens-buttons.jpg)

## <a name="hololens-indicator-lights"></a>インジケーターライトの HoloLens

![HoloLens インジケーターライトを示す画像。](./images/hololens-lights.png)

HoloLens のインジケーター ライトの意味がわからない場合 次のようなヘルプが表示されます。

|ライトがこれを行うとき |意味 |
|---|---|
|中央から外側へスクロールします。 |HoloLens を起動しています。 |
|すべてまたは一部を常に点灯します。 |HoloLens はオンになっており、使用準備ができています。 バッテリの寿命は20% 刻みで示されます。 |
|スクロールしてから、スクロールします。 |HoloLens がオンになっていて、課金されています。 バッテリの寿命は20% 刻みで示されます。 |
|1つずつオフにします。 |HoloLens をシャットダウンしています。 |
|すべてを一度にオフにします。 |HoloLens がスタンバイ状態になります。 |
|すべてが点灯した後、少し点滅してから、すべてオフになります。 |バッテリが非常に低くなっています。 HoloLens には課金が必要です。 |
|すべてスクロールし、次に点滅します。 |バッテリが非常に低くなっています。 HoloLens が課金されています。 |

## <a name="safety-and-comfort"></a>安全性と快適性

### <a name="use-in-safe-surroundings"></a>安全な環境での使用

HoloLens は、障害のある安全な領域で使用します。 車両を操作しているときや、他の危険な可能性のある活動を行っているときなど、明確なビューと完全な注意が必要な場合は、このフィールドを使用しないでください。

### <a name="stay-comfortable"></a>快適性を保つ

HoloLens を使用する最初の数セッションは短時間にとどめ、必ず休憩を取りましょう。 不快感を覚えた場合は使用を中止し、気分が良くなるまで休んでください。 考えられる症状には、一時的な吐き気、乗り物酔い、目まい、方向感覚障害、頭痛、疲労、疲れ目、ドライ アイなどがあります。

> [!div class="nextstepaction"]
> [HoloLens の開始と構成 (第1世代)](hololens1-start.md)
