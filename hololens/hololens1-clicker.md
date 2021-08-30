---
title: 新しいクリックHoloLens使用する
description: この記事では、クッカーのペアリング、HoloLens、回復など、新しいツールを使用する方法について説明します。
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
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189955"
---
# <a name="use-the-hololens-1st-gen-clicker"></a>HoloLens (第 1 世代) クリッカーの使用

このクッカーは、特にHoloLens (第 1 世代) 用に設計され、ホログラムと対話する別の方法を提供します。 別のボックスHoloLens (第 1 世代) が付属しています。

手のジェスチャの代用として、アプリの選択、スクロール、移動、サイズ変更を行います。

## <a name="clicker-hardware-and-pairing"></a>Clicker ハードウェアとペアリング

1 HoloLens (第 1 世代) のクッカーには、保持しやすくする指ループとインジケーター ライトがあります。

![[HoloLens Clicker] を選択します。](images/use-hololens-clicker-1.png)

### <a name="clicker-indicator-lights"></a>Clicker インジケーター ライト

クッカーのライトの意味を次に示します。

- **白で点滅する**。 クッカーはペアリング モードです。
- **高速点滅白**。 ペアリングに成功しました。
- **白の単色**。 クッカーが充電中です。
- **アンバー を点滅します**。 バッテリが少ない。
- **アンバーの単色**。 クリックツールでエラーが発生し、再起動する必要があります。 ペアリング ボタンを押しながら、15 秒間長押しします。

### <a name="pair-the-clicker-with-your-hololens-1st-gen"></a>クッカーを自分のHoloLens (第 1 世代) とペアリングする

1. 花のジェスチャを使用して **[スタート] に移動し**、[デバイス設定  >  **選択し**、BluetoothがオンBluetooth確認します。
1. クリンカーで、状態ライトが白に点滅するまでペアリング ボタンを長押しします。
1. ペアリング画面で **、[Clicker** Pair]を  >  **選択します**。

### <a name="charge-the-clicker"></a>Clicker を課金する

クッカーバッテリが少ない場合、バッテリ インジケーターがオレンジ色に点滅します。 マイクロ USB ケーブルを USB 電源に差し込み、デバイスを充電します。

## <a name="use-the-clicker-with-hololens-1st-gen"></a>[clicker with HoloLens (第 1 世代)

### <a name="hold-the-clicker"></a>クリックボタンを押したまま

クッカーを装着するには、ループをリングまたは中指の上にスライドして、Micro USB ポートが手の指の方に向かっている状態にしてください。 インデントに親指を入します。

![Clicker を保持する方法。](images/use-hololens-clicker-2.png)

### <a name="clicker-gestures"></a>Clicker ジェスチャ

クリックジェスチャは、手のジェスチャに使用される大きな動きではなく、HoloLens回転です。 またHoloLensは、クッカーがジェスチャ フレームの外側にある場合でもジェスチャとクリックを認識[](hololens1-basic-usage.md)し、ユーザーにとって最も快適な位置にクッカーを保持できます。

- **を選択します**。 ホログラム、ボタン、または他の要素を選択するには、その要素を視線入力してクリックします。

- **を長押しします**。 ボタンをクリックしたままにし、ホログラムの移動やサイズ変更など、タップアンドホールドと同じ操作を行います。

- **スクロール**。 アプリ バーで、[スクロール ツール] **を選択します**。 クリックして長押しし、クリックツールを上、下、左、または右に回転させます。 より速くスクロールするには、スクロール ツールの中央から手を遠くに移動します。

- **ズーム**。 アプリ バーで、[ズーム ツール] **を選択します**。 クリックして長押しし、クリックボタンを上に回転させて拡大するか、下に移動して縮小します。

> [!TIP]
> ウィンドウを使用するときに拡大または縮小Microsoft Edge、ページを視線入力してダブルクリックします。

## <a name="im-having-problems-using-the-hololens-clicker"></a>クリックツールの使用で問題HoloLensしています

クッカー [を使用して、](hololens1-clicker.md) ホログラムの選択、スクロール、移動、サイズ変更を行います。 個々のアプリで、追加のクリックジェスチャがサポートされる場合があります。

クリックツールの使用で問題が発生した場合は、課金され、アプリとペアリングHoloLens。 バッテリが少ない場合は、インジケーターライトがオレンジ色に点滅します。 クッカーがペアリングされているのを確認するには、[デバイス設定に移動し、そこに表示  >  されるのを確認します。 詳細については、「Clicker をペアリング [する」を参照してください](hololens1-clicker.md)。

クッカーが課金され、ペアリングされ、問題が解決しない場合は、メイン ボタンとペアリング ボタンを 15 秒間押してリセットします。 次に、clicker をもう一度HoloLensします。

クリックツールをリセットしても問題が発生しない場合は、「再起動または回復する」を参照HoloLens[してください](hololens1-clicker.md#restart-or-recover-the-clicker)。
## <a name="restart-or-recover-the-clicker"></a>Clicker を再起動または回復する

クリック機能が応答しないか、HoloLens機能しない場合に試してみる必要があるいくつかの操作を次に示します。

### <a name="restart-the-clicker"></a>Clicker を再起動する

ペンのチップを使用して、ペアリング ボタンを長押しします。 同時に、クリックボタンを 15 秒間長押しします。 クリックツールが既にアプリとペアリングされている場合HoloLens再起動後もペアリングされたが保持されます。

クッカーの電源が入らない場合や再起動しない場合は、ボタンを使用して充電HoloLensしてみてください。 バッテリが非常に低い場合は、白いインジケーター ライトがオンになるまで数分かかる場合があります。

### <a name="re-pair-the-clicker"></a>クッカーを再ペアリングする

[デバイス **設定**  >  **選択し**、クリックツールを選択します。 [ **削除]** を選択し、数秒待って、もう一度クッカーをペアリングします。

### <a name="recover-the-clicker"></a>Clicker を回復する

Clicker を再起動して再ペアリングして問題が解決しない場合は、Windows Device Recovery Tool を使用して回復できます。 回復プロセスには時間がかかる場合があります。また、最新バージョンの Clicker ソフトウェアがインストールされます。 このツールを使用するには、少なくとも 4 GB の空きストレージ領域をWindows 10以降を実行しているコンピューターが必要です。

クリックツールを回復するには:

1. お使いのコンピューターに[Windows Device Recovery Tool をダウンロードして](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/)インストールします。
1. Connect付属のマイクロ USB ケーブルを使用して、コンピューターにクッカーを接続HoloLens。
1. Windows Device Recovery Tool を実行し、指示に従います。

クリック機能が自動的に検出されない場合は、[デバイスが検出されていない] を選択し、指示に従ってデバイスを回復モードにします。

