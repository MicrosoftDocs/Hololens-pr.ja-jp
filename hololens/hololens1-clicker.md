---
title: HoloLens クリッカーの使用
description: この記事では、クリッカーのペアリング、充電、回復など、HoloLens クリッカーの使用方法について説明します。
ms.assetid: 7d4a30fd-cf1d-4c9a-8eb1-1968ccecbe59
ms.date: 09/16/2019
manager: jarrettr
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4b17fc134846a66046a819c56755d87206c5643e
ms.sourcegitcommit: 01c0b0a789e156a9d29aaf6f61e36dfd09b8c01a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439053"
---
# <a name="use-the-hololens-1st-gen-clicker"></a>HoloLens (第1世代) クリッカーの使用

クリッカーは HoloLens (第1世代) 用に特別に設計されており、ホログラムを操作する別の方法を提供します。 HoloLens (第1世代) が別のボックスに入っています。

手のジェスチャの代わりに使用して、アプリを選択、スクロール、移動、サイズ変更します。

## <a name="clicker-hardware-and-pairing"></a>クリッカー ハードウェアとペアリング

HoloLens (第1世代) クリッカーには、持ちやすくするための指のループとインジケーター ライトがあります。

![HoloLens クリッカー](images/use-hololens-clicker-1.png)

### <a name="clicker-indicator-lights"></a>クリッカー インジケーター ライト

クリッカーのライトの意味は次のとおりです。

- **白の点滅**。 クリッカーはペアリング モードです。
- **白の速い点滅**。 ペアリングが正常に終了しました。
- **白の点灯**。 クリッカーは充電中です。
- **オレンジで点滅**。 バッテリーが少なくなっています。
- **オレンジの点灯**。 クリッカーにエラーが発生し、再起動する必要があります。 ペアリング ボタンを押しながら、クリックして 15 秒間押し続けます。

### <a name="pair-the-clicker-with-your-hololens-1st-gen"></a>クリッカーを HoloLens (第1世代) とペアリングします

1. ブルーム ジェスチャを使用して、[**スタート**] に移動し、[**設定**] > [**デバイス**] の順に選択して、Bluetooth がオンになっていることを確認します。
1. クリッカーで、状態ライトが白く点滅するまでペアリング ボタンを押し続けます。
1. ペアリング画面で、**[クリッカー]** > **[ペアリング]** を選択します。

### <a name="charge-the-clicker"></a>クリッカーを充電する

クリッカー バッテリーが少なくなると、バッテリーのインジケーターがオレンジ色に点滅します。 Micro USB ケーブルを USB 電源に接続して、デバイスを充電します。

## <a name="use-the-clicker-with-hololens-1st-gen"></a>HoloLens (第1世代) でクリッカーを使用する

### <a name="hold-the-clicker"></a>クリッカーを押し続ける

クリッカーを装着するには、Micro USB ポートが手首を向くように、ループを薬指または中指にスライドさせます。 くぼみに親指を置きます。

![クリッカーの持ち方](images/use-hololens-clicker-2.png)

### <a name="clicker-gestures"></a>クリッカーのジェスチャ

クリッカーのジェスチャは手首の小さな回転であり、HoloLens ハンド ジェスチャで使用される大きな動きではありません。 HoloLens は、クリッカーが[ジェスチャ フレーム](hololens1-basic-usage.md)の外側にある場合でもジェスチャとクリックを認識します。そのため、クリッカーを最も快適な位置に保持できます。

- **選択します**。 ホログラム、ボタン、またはその他の要素を選択するには、それを見つめて、クリックします。

- **クリックしたままにします**。 ボタンを親指で長押しすると、ホログラムの移動やサイズ変更など、長押しした場合と同じ操作を実行できます。

- **スクロール**。 アプリ バーで、[**スクロール モード**] を選択します。 クリックしたままにして、クリッカーを上下左右に回転させます。 高速でスクロールするには、スクロール ツールの中心から手を速く動かします。

- **ズーム**。 アプリ バーで、[**ズーム モード**] を選択します。 クリックしたまま、クリッカーを上に回転するとズーム イン、下に回転するとズーム アウトします。

> [!TIP]
> Microsoft Edge を使用しているときにズーム インまたはズーム アウトするには、ページを注視してダブル クリックします。

## <a name="restart-or-recover-the-clicker"></a>クリッカーを再起動または回復する

HoloLens クリッカーが応答しない、またはうまく機能しない場合に試してみることがいくつかあります。

### <a name="restart-the-clicker"></a>クリッカーを再起動する

ペンの先を使って、ペアリング ボタンを押し続けます。 同時に、クリッカーをクリックして 15 秒間押し続けます。 クリッカーがすでに HoloLens とペアリングされている場合、クリッカーは再起動後もペアリングされたままになります。

クリッカーがオンにならないか、再起動しない場合は、HoloLens 充電器を使用してクリッカーを充電してみてください。 バッテリー残量が非常に少ない場合、白いインジケーター ライトがオンになるまで数分かかることがあります。

### <a name="re-pair-the-clicker"></a>クリッカーを再ペアリングする

[**設定**] > [**デバイス**] を選択して、クリッカーを選択します。 [**削除**] を選択し、数秒待ってから、クリッカーを再度ペアリングします。

### <a name="recover-the-clicker"></a>クリッカーを回復する

クリッカーを再起動してペアリングしても問題が解決しない場合は、Windows Device Recovery Tool を使用して問題を回復できます。 回復プロセスには時間がかかる場合があり、最新バージョンのクリッカー ソフトウェアがインストールされます。 このツールを使用するには、Windows 10 以降を実行し、4 GB 以上の空き容量があるコンピューターが必要です。

クリッカーを回復するには:

1. コンピューターに [Windows Device Recovery Tool](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) をダウンロードしてインストールします。
1. HoloLens に付属の Micro USB ケーブルを使用して、クリッカーをコンピューターに接続します。
1. Windows Device Recovery Tool を実行し、指示に従います。

クリッカーが自動的に検出されない場合は、[**デバイスが検出されませんでした**] を選択し、指示に従ってデバイスを回復モードにします。
