---
title: HoloLens 2 バッテリーと充電
description: HoloLens を充電し、外部のバッテリ パックを使用する方法。
ms.assetid: E0AB903E-454E-46F6-AB25-4DFA0A475B0C
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 05/14/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: b4692468942da88877370864eda2ce173cc499af
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034348"
---
# <a name="hololens-2-battery-and-charging"></a>HoloLens 2 バッテリーと充電

このページでは、HoloLens 2 の充電と外部バッテリ パックの使用に関する詳細を提供します。

## <a name="charging-the-device"></a>デバイスの充電

HoloLens 2 に付属している[充電器と USB タイプ C ケーブル](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1)を使用します。これは、デバイスの充電に最適な方法です。 HoloLens 2 に含まれる充電器には、2A で最大 9V (18W) が用意されています。 提供される壁の充電器を使用すると、HoloLens 2 デバイスは、デバイスがスタンバイ状態のときに 65 分未満でバッテリーを完全に充電できます。 これらのアクセサリが使用できない場合は、使用可能な充電器が少なくとも 15W の電力に対応していることを確認してください。

> [!NOTE]
> 可能であれば、PC を使用してデバイスを USB 経由で充電することは避けてください。遅いです。

## <a name="checking-the-battery-charge-level"></a>バッテリの充電レベルを確認しています
デバイスが正常に起動し、動作している場合は、次の 3 つの方法でバッテリの充電レベルを確認できます。

- HoloLens デバイス UI のメイン メニューから。
- 電源ボタンの近くにある LED を確認します (40% が充電されている場合、少なくとも 2 つの点灯した LED が見えるはずです)。
    - デバイスの充電中は、バッテリー インジケーターが点灯し、現在の充電レベルを示します。  最後のライトはゆっくりと点滅し、充電中であることを示します。
    - HoloLens の電源が入っているときは、バッテリー インジケーターにバッテリー レベルが 5 段階で表示されます。
    - 5 個のライトのうち 1 個しか点灯していない場合は、バッテリー レベルが 20 パーセントを下回っています。
    - バッテリー レベルが極端に低い場合にデバイスの電源を入れようとすると、1 個のライトが短く点滅してから消えます。
- ホスト PC で、**エクスプローラー** を開き、 **[この PC]** の下にある HoloLens 2 デバイスを探します。 そのデバイスを右クリックし、 **[プロパティ]** を選択します。 ダイアログ ボックスにバッテリの充電レベルが表示されます。

   ![HoloLens 2 のプロパティ画面にバッテリの残量レベルが表示されます。](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>代替充電の仕様

HoloLens 2 は、 [USB 電力配信](https://www.usb.org/usb-charger-pd)の電源によって最大 27 ワットまで充電されます。 電源が少なくとも 10 ワットを提供できる場合、HoloLens の動作時間を延長できます (一部のワークロードでは無期限)。 

> [!NOTE]
> USB-A - USB C の充電ケーブルを使用すると、充電は 7.5 ワットに制限されます。 操作時間は長くなりますが、USB-C - C を使用した場合ほどではありません。

HoloLens がスタンバイ モードの場合、内部バッテリの最大充電率に達しても 18 ワットで十分です。 HoloLens が使用されている場合は、HoloLens の優先順位は充電よりも操作の方が高いため、充電率は低くなる可能性があります。

> [!IMPORTANT]
> HoloLens 2 は、最低でも 5V/1.5 A で充電することをお勧めします。 少なくとも 5V/1.5 A を供給できない充電器は使用しないでください。 

### <a name="external-battery-packs"></a>外部のバッテリパック

上記の仕様を満たすバッテリパックは、HoloLens 2 で使用できます。 ただし、一部の USB C バッテリ パックは再充電し、同じ USB C ポートを使用して電源を供給するのでご注意ください。 これらのバッテリパックは [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) を実装して、外部バッテリが HoloLens から充電されるのでなく HoloLens を確実に充電するので重要です。 

### <a name="managing-heat"></a>ヒートの管理

すべてのデバイスと同様に、HoloLens を充電すると熱が発生します。 充電速度が速いほど、熱も多く生まれます。 また、バッテリ残量が少ないときに充電を開始すると、バッテリがほとんどいっぱいのときよりも多くの熱が発生します。 熱い環境で長時間にわたって HoloLens を運用する必要がある場合は、次の手法を使用できます。

- 内部バッテリが完全に充電されている場合でも、外部電源に HoloLens 2 を接続するのは問題ありません。
- 外部バッテリが使い果たされると、HoloLens は引き続き内部バッテリで動作します。    
- 上記の手順を実行しても熱が問題になる場合は、充電を 1.5 A に制限する充電器またはバッテリパックを使用することを検討してください。 このオプションを使用しても、内部バッテリが徐々に消費されるため、操作時間は長くありません。

## <a name="troubleshooting"></a>トラブルシューティング


### <a name="hololens-charges-external-battery"></a>HoloLens が外部バッテリで充電する
HoloLens 2 が外部バッテリに充電されるのではなく外部バッテリを充電する場合、そのバッテリは [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) を実装していないということです。 この問題を解決するには、新しいバッテリパックに切り替えることをお勧めしますが、別の方法として、USB-A から USB C ケーブルへ切り替えてみることもできます。 これにより、充電速度は7.5 ワットに制限されるのでご注意ください。
