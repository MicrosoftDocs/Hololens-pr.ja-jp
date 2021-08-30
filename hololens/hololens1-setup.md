---
title: 新しいサービスを準備HoloLens
description: 初めて(第 1 世代) Mixed Reality デバイスをHoloLens、調整、およびセットアップする方法について説明します。
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
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189258"
---
# <a name="get-your-hololens-1st-gen-ready-to-use"></a>HoloLens (第 1 世代) の使用準備

手順に従って、HoloLens (第 1 世代) を初めて設定します。

## <a name="charge-your-hololens-1st-gen"></a>お使HoloLens (第 1 世代) に課金する

デバイスを充電HoloLens付属のマイクロ USB ケーブルを使用して、電源を充電ポートに接続します。 その後、電源を電源プラグに差し込みます。 デバイスが充電中は、バッテリ インジケーターが波のパターンで点灯します。

![マイクロ USB ケーブルを接続する方法を示すHoloLens。](./images/hololens-charging.png)

電源がHoloLens、バッテリ インジケーターにバッテリ レベルが増分で表示されます。 5 個のライトのうち 1 個しか点灯していない場合は、バッテリー レベルが 20 パーセントを下回っています。 バッテリー レベルが極端に低い場合にデバイスの電源を入れようとすると、1 個のライトが短く点滅してから消えます。

> [!TIP]
> 現在のバッテリ レベルの見積もりを取得するには、"Hey Cortana, how much battery do i have left?

デバイスに付属する電源装置と USB ケーブルは、デバイス (第 1 世代) にHoloLens最適な方法です。  電源は 18W の電力 (9V 2A) を提供します。

充電率と速度は、デバイスが実行されている環境によって異なる場合があります。

## <a name="adjust-fit"></a>フィット調整

> [!VIDEO https://www.microsoft.com/videoplayer/embed/be3cb527-f2f1-4f85-b4f7-a34fbaba980d]

| &nbsp; | &nbsp; |
|:--- |:--- |
|1.ヘッドバンドを約 20 ~ 30 度回転させます。|![手順 1. ヘッドバンドを回転させます。](./images/FitGuideStep1.png)|
|2.ヘッドバンドを押し戻します。 時間がたつとバンドが破損する可能性があるため、ヒンジの背後にあるバンドを引き戻したり、操作したりしない。|![手順 2. ヘッドバンドを押し戻します。](./images/FitGuideStep2.png)|
|3.調整ホイールを回して、ヘッドバンドを引き伸ばします。 |![手順 3 では、調整ホイールを使用してヘッドバンドを拡張します。](./images/FitGuideStep3.png)|
|4.デバイスをデバイスのアームで保持し、頭の上に配置します。 ヘッドバンドが額の上部に位置し、調整ホイールを引き締めます。|![手順 4. デバイスに取り付け、ヘッドバンドを調整します。](./images/FitGuideStep4.png)|
|5.バイザーをスライドして戻し、デバイスの適合を確認します。 ヘッドバンドは、耳の上にスピーカーを付け、生え線の下にある額の上部に座る必要があります。 レンズは目の中央に位置する必要があります。|![手順 5. バイザーをスライドして戻り、適合を確認します。](./images/FitGuideSetep5.png)|

## <a name="turn-on-your-hololens"></a>デバイスの電源をオンHoloLens

電源ボタンを使用して、電源HoloLensオンとオフを切り替え、スタンバイ モードにします。

![電源ボタンのHoloLens画像。](./images/hololens-power.png)

デバイスが応答しない場合、または起動しない場合は、「再起動、リセット、または回復」を参照[HoloLens。](hololens-restart-recover.md)

電源がオフHoloLensスタンバイ状態の場合は、電源ボタンを 1 秒間押してオンにします。 オンにしない場合は、接続して少なくとも 30 分間課金します。

> [!TIP]
> 再起動するにはHoloLens"Hey Cortana、デバイスを再起動します。

### <a name="put-hololens-in-standby"></a>スタンバイHoloLensを設定する

電源がオンHoloLens状態で電源を入れるには、電源ボタンを 1 回押します。 バッテリ インジケーターが点滅します。 スタンバイからウェイクアップするには、電源ボタンを再度押します。

HoloLens、非アクティブ状態が 3 分後に自動的にスタンバイ状態になります。 スタンバイ状態の場合、4 時間後、またはバッテリ レベルが 10% 低下した後に自動的にシャットダウンされます。

### <a name="shut-down-hololens"></a>シャットダウンHoloLens

電源ボタンをシャットダウン (オフ) HoloLens、電源ボタンを 4 秒間押したままにします。 バッテリ インジケーターは 1 つ 1 つオフにされ、デバイスはシャットダウンします。

HoloLens接続されている場合でも、バッテリ レベルが 1% に低下すると、自動的にシャットダウンされます。 バッテリを 3% に切り取った後、電源を再びオンHoloLensできます。

## <a name="adjust-volume-and-brightness"></a>音量と明るさを調整する

明るさと音量のボタンは、デバイスのアームボリュームの上に右側に表示され、左 &mdash; に明るさが表示されます。

![次のボタンをHoloLens画像。](./images/hololens-buttons.jpg)

## <a name="hololens-indicator-lights"></a>HoloLensインジケーター ライト

![インジケーター ライトのHoloLens画像。](./images/hololens-lights.png)

HoloLens のインジケーター ライトの意味がわからない場合 いくつかのヘルプを次に示します。

|ライトがこれを行う場合 |意味 |
|---|---|
|中央から外側にスクロールします。 |HoloLens開始しています。 |
|点灯した (すべてまたは一部) |HoloLensがオンで、使用できる状態です。 バッテリの寿命は 20% 刻みで示されます。 |
|スクロールし、点灯してからスクロールします。 |HoloLensオンで充電中です。 バッテリの寿命は 20% 刻みで示されます。 |
|1 つ 1 つオフにします。 |HoloLensシャットダウン中です。 |
|一度にすべてオフにします。 |HoloLensスタンバイ状態になります。 |
|すべてが点灯し、1 つが短時間点滅してから、すべてオフになります。 |バッテリが非常に低い。 HoloLensする必要があります。 |
|すべてのスクロール、1 つの点滅、すべてのスクロール。 |バッテリが非常に低い。 HoloLens課金中です。 |

## <a name="safety-and-comfort"></a>安全性と快適性

### <a name="use-in-safe-surroundings"></a>安全な環境で使用する

障害やHoloLens危険が発生する安全な空間で、お使いください。 車両を運用している間や危険な可能性のあるその他のアクティビティを行っている間など、明確な視野と完全な注意が必要な場合は使用しない。

### <a name="stay-comfortable"></a>快適性を保つ

HoloLens を使用する最初の数セッションは短時間にとどめ、必ず休憩を取りましょう。 不快感を覚えた場合は使用を中止し、気分が良くなるまで休んでください。 考えられる症状には、一時的な吐き気、乗り物酔い、目まい、方向感覚障害、頭痛、疲労、疲れ目、ドライ アイなどがあります。

> [!div class="nextstepaction"]
> [デバイスを起動して構成HoloLens (第 1 世代)](hololens1-start.md)
