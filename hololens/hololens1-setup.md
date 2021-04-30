---
title: 新しい HoloLens を準備する
description: HoloLens (第1世代) mixed reality デバイスを初めて準備、調整、設定する方法について説明します。
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
ms.openlocfilehash: 30912fda53d5d8b9ea5e60f29eeb93ea29cca2d2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309425"
---
# <a name="get-your-hololens-1st-gen-ready-to-use"></a>HoloLens (第1世代) を使用する準備ができました

HoloLens (第1世代) を初めてセットアップするには、次の手順に従います。

## <a name="charge-your-hololens-1st-gen"></a>HoloLens を充電する (第1世代)

HoloLens を充電するには、付属のマイクロ USB ケーブルを使用して、電源装置を充電ポートに接続します。 その後、電源装置を電源コンセントに接続します。 デバイスの充電中は、バッテリインジケーターが波形パターンで点灯します。

![マイクロ USB ケーブルを HoloLens に接続する方法を示す画像](./images/hololens-charging.png)

HoloLens がオンの場合、バッテリインジケーターには、バッテリレベルが増加して表示されます。 5つのライトのうちの1つだけが点灯している場合、バッテリレベルは20% 未満です。 バッテリレベルが非常に低く、デバイスの電源を入れようとすると、1つのライトが短時間点滅し、次に消えます。

> [!TIP]
> 現在のバッテリレベルの推定値を取得するには、「Cortana の残りバッテリの残量」と言います。

デバイスに付属する電源と USB ケーブルは、HoloLens (第1世代) を使用するための最適な方法です。  電源装置には、18W の電力 (9V 2A) が用意されています。

課金速度と速度は、デバイスが実行されている環境によって異なる場合があります。

## <a name="adjust-fit"></a>合わせる

> [!VIDEO https://www.microsoft.com/videoplayer/embed/be3cb527-f2f1-4f85-b4f7-a34fbaba980d]

|     |     |
|:--- |:--- |
|1. ヘッドバンドを約20-30 度まで回転させます。|![ステップ1、ヘッドバンドを回転させる](./images/FitGuideStep1.png)|
|2. ヘッドバンドをプッシュして戻します。 時間が経つにつれてバンドが破壊される可能性があるため、これをプルしたり、ヒンジの背後にあるバンドを操作したりしないでください。|![手順 2. ヘッドバンドをプッシュする](./images/FitGuideStep2.png)|
|3. 調整ホイールをオンにして、すべての方向にヘッドバンドを拡張します。 |![手順 3. 調整ホイールを使用してヘッドバンドを延長する](./images/FitGuideStep3.png)|
|4. デバイスのアームによってデバイスを保持し、ヘッドに配置します。 ヘッドバンドが、前の頭の一番上にあることを確認し、調整ホイールを締めます。|![ステップ4、デバイスに配置し、ヘッドバンドを調整する](./images/FitGuideStep4.png)|
|5. バイザーをスライドバックし、デバイスの適合性を確認します。 ヘッドバンドは、耳の上にある、ヘアラインのすぐ下にある、耳の上に座っているはずです。 レンズが目の中央に配置されている必要があります。|![手順 5. で、バイザーをスライドバックし、適合していることを確認します。](./images/FitGuideSetep5.png)|

## <a name="turn-on-your-hololens"></a>HoloLens をオンにする

[電源] ボタンを使用して、HoloLens のオンとオフを切り替えるか、スタンバイモードにします。

![HoloLens の電源ボタンを表示する画像](./images/hololens-power.png)

デバイスが応答しない場合、または起動しない場合は、「 [HoloLens を再起動、リセット、または回復](hololens-restart-recover.md)する」を参照してください。

HoloLens がオフになっている場合、またはスタンバイ状態になっている場合は、1秒間、電源ボタンを押して電源をオンにします。 電源がオンになっていない場合は、接続し、少なくとも30分間課金します。

> [!TIP]
> HoloLens を再起動するには、「Cortana さん、デバイスを再起動する」と言ってください。

### <a name="put-hololens-in-standby"></a>HoloLens をスタンバイにする

HoloLens をオンにしたままスタンバイ状態にするには、電源ボタンを1回押します。 バッテリインジケーターが点滅します。 スタンバイから復帰させるには、もう一度 [電源] ボタンを押します。

HoloLens は、非アクティブな状態が3分続くと自動的にスタンバイ状態になります。 スタンバイ状態のときは、4時間後、またはバッテリレベルが10% 下がった後に、自動的にシャットダウンします。

### <a name="shut-down-hololens"></a>HoloLens をシャットダウンする

HoloLens をシャットダウン (オフにする) するには、電源ボタンを4秒間押したままにします。 バッテリインジケーターは1つずつオフにし、デバイスはシャットダウンします。

HoloLens は、電源が接続されている場合でも、バッテリレベルが1パーセント下がると自動的にシャットダウンします。 バッテリを3% に recharged と、HoloLens を再び有効にすることができます。

## <a name="adjust-volume-and-brightness"></a>音量と明るさを調整する

[明るさ] ボタンと [音量] ボタンは、デバイスのアームボリュームの上にあり、 &mdash; 右側と明るさを左右します。

![HoloLens ボタンを表示する画像](./images/hololens-buttons.jpg)

## <a name="hololens-indicator-lights"></a>HoloLens インジケーターライト

![HoloLens インジケーターライトを示す画像](./images/hololens-lights.png)

HoloLens のインジケーターライトが何を意味するのかわからない場合は、 次のようなヘルプが表示されます。

|ライトがこれを行うとき |ということです |
| - | - |
|中央から外側へスクロールします。 |HoloLens を起動しています。 |
|すべてまたは一部を常に点灯します。 |HoloLens はオンになっており、使用する準備ができています。 バッテリの寿命は20% 刻みで示されます。 |
|スクロールしてから、スクロールします。 |HoloLens はオンになっており、課金されています。 バッテリの寿命は20% 刻みで示されます。 |
|1つずつオフにします。 |HoloLens をシャットダウンしています。 |
|すべてを一度にオフにします。 |HoloLens がスタンバイ状態になります。 |
|すべてが点灯した後、少し点滅してから、すべてオフになります。 |バッテリが非常に低くなっています。 HoloLens は課金する必要があります。 |
|すべてスクロールし、次に点滅します。 |バッテリが非常に低くなっています。 HoloLens は充電中です。 |

## <a name="safety-and-comfort"></a>安全性と快適さ

### <a name="use-in-safe-surroundings"></a>安全な環境での使用

お客様の HoloLens は、障害のない安全なスペースで使用してください。 車両を操作しているときや、他の危険な可能性のある活動を行っているときなど、明確なビューと完全な注意が必要な場合は、このフィールドを使用しないでください。

### <a name="stay-comfortable"></a>お使いのまま

最初のいくつかのセッションを HoloLens brief で保持し、必ず中断してください。 不快感が発生した場合は、より良い感覚になるまで停止してください。 これには、嘔吐、motion sickness、頭痛、disorientation、頭痛、疲労、目の歪み、ドライアイなどの一時的な感情が含まれる場合があります。

> [!div class="nextstepaction"]
> [HoloLens を起動して構成する (第1世代)](hololens1-start.md)
