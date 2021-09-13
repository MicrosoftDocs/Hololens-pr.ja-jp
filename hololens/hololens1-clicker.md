---
title: HoloLens clicker を使用する
description: この記事では、clicker のペアリング、課金、復旧など、HoloLens clicker の使用方法について説明します。
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
ms.openlocfilehash: 98ec5795974fa242225bb1048ead41892d8296e4
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033795"
---
# <a name="use-the-hololens-1st-gen-clicker"></a>HoloLens (第 1 世代) クリッカーの使用

clicker は HoloLens (第1世代) 専用に設計されており、ホログラムを操作する別の方法を提供しています。 これには、別のボックスに HoloLens (第1世代) が付属しています。

ハンドジェスチャの代わりに使用して、アプリの選択、スクロール、移動、およびサイズ変更を行います。

## <a name="clicker-hardware-and-pairing"></a>ハードウェアとペアリングの Clicker

HoloLens (第1世代) clicker には、ホールディングとインジケーターライトを簡単にするための指ループがあります。

![HoloLens Clicker。](images/use-hololens-clicker-1.png)

### <a name="clicker-indicator-lights"></a>Clicker インジケーターライト

Clicker のライトは次のようになります。

- **白を点滅** します。 Clicker はペアリングモードです。
- **高速点滅白**。 ペアリングに成功しました。
- **無地の白**。 Clicker は充電中です。
- **黄色で点滅** します。 バッテリが不足しています。
- 緑色で **点灯** します。 Clicker でエラーが発生したため、再起動する必要があります。 ペアリングボタンを押しながら、15秒間はクリックしたままにします。

### <a name="pair-the-clicker-with-your-hololens-1st-gen"></a>clicker を HoloLens とペアにする (第1世代)

1. ブルームジェスチャを使用して [**スタート**] にアクセスし、[**設定** デバイス] を選択して、  >   Bluetooth がオンになっていることを確認します。
1. Clicker で、ペアリングボタンを押したままにして、ステータスライトが白になるまで続けます。
1. [ペアリング] 画面で、[ **Clicker** Pair] を選択し  >  ます。

### <a name="charge-the-clicker"></a>Clicker を請求する

Clicker バッテリが低い場合、バッテリインジケーターは黄色で点滅します。 マイクロ USB ケーブルを USB 電源装置に接続して、デバイスを充電します。

## <a name="use-the-clicker-with-hololens-1st-gen"></a>HoloLens での clicker の使用 (第1世代)

### <a name="hold-the-clicker"></a>Clicker を保持する

Clicker を使用するには、このループをリングまたは真ん中の指でスライドさせることで、マイクロ USB ポートが手首に向くようにします。 インデントにつまみを置きます。

![Clicker を保持する方法。](images/use-hololens-clicker-2.png)

### <a name="clicker-gestures"></a>Clicker ジェスチャ

Clicker ジェスチャは、HoloLens ハンドジェスチャに使用される大きな動きではなく、小さな手首回転です。 clicker が[ジェスチャフレーム](hololens1-basic-usage.md)の外側にある場合でも、と HoloLens はジェスチャとクリックを認識するので、clicker を最も快適な位置に保持できます。

- **を選択** します。 ホログラム、ボタン、またはその他の要素を選択するには、その要素を見つめて、をクリックします。

- **クリック** したままにします。 ボタンのつまみをクリックしたままにすると、ホログラムの移動やサイズ変更など、タップして保持するものと同じことが実行されます。

- **スクロール**。 アプリバーで、[ **スクロールツール**] を選択します。 クリックしたままにして、clicker up、down、left、または right を回転させます。 スクロールを速くするには、スクロールツールの中央から離れた位置に移動します。

- **ズーム**。 アプリバーで、[ **ズームツール**] を選択します。 [拡大] をクリックし、clicker を回転して、ズームアウトします。

> [!TIP]
> Microsoft Edge を使用するときに拡大または縮小するには、ページを見つめ、をダブルクリックします。

## <a name="im-having-problems-using-the-hololens-clicker"></a>HoloLens clicker の使用に関する問題が発生しています

[Clicker](hololens1-clicker.md)を使用して、ホログラムの選択、スクロール、移動、およびサイズ変更を行います。 個々のアプリは、追加の clicker ジェスチャをサポートする場合があります。

Clicker の使用に問題がある場合は、課金され、HoloLens とペアになっていることを確認してください。 バッテリが低い場合は、インジケーターライトが黄色で点滅します。 clicker がペアリングされていることを確認するには、[**設定** デバイス] にアクセスし、  >  表示されているかどうかを確認します。 詳細については、「 [Pair the clicker](hololens1-clicker.md)」を参照してください。

Clicker が課金され、ペアリングされていても問題が発生する場合は、メインボタンを押したまま15秒のペアリングボタンを押してリセットします。 次に、clicker を HoloLens とペアにします。

clicker をリセットしても問題が解決しない場合は、「 [HoloLens clicker を再起動または回復する](hololens1-clicker.md#restart-or-recover-the-clicker)」を参照してください。
## <a name="restart-or-recover-the-clicker"></a>Clicker を再起動または回復する

HoloLens clicker が応答していないか、正しく機能していない場合は、次の点を試してみてください。

### <a name="restart-the-clicker"></a>Clicker を再起動します。

ペンの先端を使用して、ペアリングボタンを押したままにします。 同時に、clicker を15秒間クリックして保持します。 clicker が既に HoloLens とペアリングされている場合は、再起動後もペアリングされたままになります。

clicker が有効にならない場合、または再起動しない場合は、HoloLens チャージャーを使用して課金してみてください。 バッテリの残量が非常に少ない場合は、白いインジケーターライトが点灯するまで数分かかることがあります。

### <a name="re-pair-the-clicker"></a>Clicker を再ペアします。

[**設定** デバイス] を選択し  >   、[clicker] を選択します。 [ **削除**] を選択し、数秒待ってから、もう一度 clicker をペアリングします。

### <a name="recover-the-clicker"></a>Clicker を回復する

clicker を再起動して再ペアリングしても問題が解決しない場合は、Windows デバイス回復ツールを使用して回復できます。 回復プロセスには時間がかかる場合があり、最新バージョンの clicker ソフトウェアがインストールされます。 このツールを使用するには、少なくとも 4 GB の空き記憶領域がある Windows 10 以降を実行しているコンピューターが必要です。

Clicker を回復するには:

1. [Windows デバイス回復ツール](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/)をコンピューターにダウンロードしてインストールします。
1. HoloLens に付属のマイクロ USB ケーブルを使用して、clicker をコンピューターに Connect します。
1. Windows デバイス回復ツールを実行し、指示に従います。

Clicker が自動的に検出されない場合は、[ **デバイスが検出されませんでした** ] を選択し、指示に従ってデバイスを回復モードにします。

