---
title: HoloLens (第 1 世代) の操作方法
description: HoloLens (第1世代) インターフェイス、ハンドトラッキング機能、holographic アプリケーションの使用に関する簡単なツアーを開始しましょう。
ms.assetid: 064f7eb0-190e-4643-abeb-ed3b09312042
ms.date: 9/16/2019
ms.reviewer: jarrettr
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
ms.openlocfilehash: 70ee881eb0c2ffaade173b31e5168371d042bbb2
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033796"
---
# <a name="getting-around-hololens-1st-gen"></a>HoloLens (第 1 世代) の操作方法

ホログラムの世界にステップインする準備はできましたか。 開始するには、次の情報を参照してください。

このガイドでは、mixed reality の概要、ホログラムとの対話に関するジェスチャ、Windows Holographic の概要について説明します。

## <a name="discover-mixed-reality"></a>Mixed Reality について

HoloLens では、ホログラムは物理的な環境に合わせて、世界の一部であるかのように見えます。 ホログラムがすべてのものであっても、周囲を見て自由に移動したり、他のユーザーやオブジェクトと対話したりすることができます。 このエクスペリエンスを "mixed reality" と呼びます。

Holographic フレームは、視線が最も機密性の高いものになるようにホログラムに配置します。また、「」を参照してください。 空間サウンドを使用すると、背後にある場合でも、ホログラムを特定できます。 また HoloLens は環境を学習して理解するため、ホログラムを実際のオブジェクトに配置して、アプリやゲームを可能にすることができます。 ゲーム内の文字がソファに表示されるか、または [スペースロボットが壁から胸像](https://www.microsoft.com/store/apps/9nblggh5fv3j)れる可能性があります。

## <a name="use-hololens-with-your-hands"></a>自分の手で HoloLens を使用する

HoloLens の操作は、スマートフォンの使用によく似ています。 自分の手で holographic ウィンドウ、メニュー、ボタンを操作できます。  ポイント、クリック、またはタップするのではなく、宝石、[音声](hololens-cortana.md)、ジェスチャを使用して、アプリとホログラムを選択し、HoloLens を回避します。

これらの基本的な操作を把握していると、HoloLens については、スナップになります。

初めて HoloLens を使用するときの基本について説明します。 また、[ **スタート** ] メニューにもジェスチャのチュートリアルがあります。このアプリについては、「」を参照してください。

### <a name="the-hand-tracking-frame"></a>ハンド トラッキング フレーム

HoloLens には、ユーザーの左右を数フィートずつ見ることのできるセンサーが搭載されています。 手を使用する場合は、手の位置をこのフレーム内に収める必要があります。そうしないと、HoloLens では認識できません。 移動すると、フレームが移動します。  

![HoloLens のハンド トラッキング フレームを示す画像。](./images/hololens-2-gesture-frame.png)

### <a name="open-the-start-menu-with-bloom"></a>ブルームを使用してスタートメニューを開きます。

[ **スタート** ] メニューを開くには

1. ジェスチャフレームにあるように、手の前に置いておきます。
1. ブルーム: すべての指をまとめて、手を開けます。
  ![ブルームジェスチャを示すアニメーション。](./images/hololens-bloom.gif)

### <a name="select-holograms-with-gaze-and-air-tap"></a>見つめとエアタップを使用したホログラムの選択

アプリまたはその他のホログラムを選択するには、選択しているホログラムを直接見ながら、エアタップします。 これを行うには、次の手順に従います。

1. 選択するホログラムを見つめます。
1. 人差し指をまっすぐ上に伸ばして、天井を指します。
1. エアタップ: 指を下げて、すぐに上げることができます。
   ![エアタップの手ぶりのアニメーション。](./images/hololens-air-tap.gif)

### <a name="select-a-hologram-by-using-your-voice"></a>音声を使用してホログラムを選択する

1. 見つめカーソルは、ヘッドを移動して移動するドットです。 有効桁数を使用して、音声コマンドを対象にすることができます。
1. 選択するホログラムを見つめます。
1. ホログラムを選択するには、「Select」と言います。

## <a name="holograms-and-apps"></a>ホログラムとアプリ

次に、テストにジェスチャを追加します。

インストールされているアプリが[スタートメニュー](holographic-home.md)にあり、Microsoft Store に HoloLens (第1世代) のアプリが他にもあります。

[ **スタート** ] メニューを開き、アプリを選択します。

HoloLens でのアプリの使用は、PC とは少し異なります。一部のアプリは、2d ビューを使用し、他の Windows アプリケーションのように見えます。 他のアプリ (イマーシブアプリ) は3D ビューを使用し、起動すると、表示される唯一のアプリになります。

アプリウィンドウまたはアプリランチャーを配置した場合は、削除するまで保存されたままになります。 これらのホログラムは、mixed reality ホームでいつでも移動またはサイズ変更できます。

## <a name="move-resize-and-rotate-apps"></a>アプリの移動、サイズ変更、および回転

HoloLens でのアプリの移動とサイズ変更は、PC の場合とは少し異なります。 アプリをドラッグする代わりに、宝石と [ジェスチャ](https://support.microsoft.com/help/12644/hololens-use-gestures) または [clicker](hololens1-clicker.md)を使用します。 また、3D 空間でアプリウィンドウを回転させることもできます。

> [!TIP]
> アプリで音声を使用してアプリを再配置し、"顔、" 大規模な "、" より小さい "と言うことができます。 または、アプリを移動 Cortana 必要があります。 "Cortana、 \* *アプリ名 \** をここに移動します。" と言います。

### <a name="move-an-app"></a>アプリを移動する

アプリを (アプリウィンドウのタイトルバーで) 見つめて、次のいずれかの操作を行います。

- タップしたまま、アプリを選択します。 アプリを配置するために手を移動し、指を動かしてアプリを配置します。
- [ **調整**]、[タップして保持] の順に選択し、ハンドを移動してアプリを配置します。 指を使用して配置し、[ **完了**] を選択します。
- [ **調整**] を選択し、clicker をクリックしたまま、アプリを配置するようにハンドを移動します。 Clicker を解放し、[ **完了**] を選択します。

> [!TIP]
> アプリを移動するときにアプリを削除する場合は、必ず、宝石を見つめた状態にしてください。

### <a name="resize-an-app"></a>アプリのサイズを変更する

アプリを見つめ、次のいずれかの操作を行います。

- アプリウィンドウの角または端を見つめ、タップして保持します。 アプリのサイズを変更し、完了したら指を上げるには、手を置きます。
- [ **調整**] を選択します。 アプリの隅にある青い四角形の1つを見つめ、タップしたままにして、アプリのサイズを変更します。 指を離してリリースし、[ **完了**] を選択します。
- [ **調整**] を選択します。 アプリの隅にある青い四角形の1つを見つめ、clicker をクリックしたままにして、アプリのサイズを変更します。 Clicker を解放し、[ **完了**] を選択します。

> [!TIP]
> 調整モードでは、ホログラムの移動やサイズ変更を行うことができます。

### <a name="rotate-an-app"></a>アプリを回転させる

アプリを見つめ、両方の手でタップして選択します。 アプリを回転させるには、1ハンドで安定した状態にして、もう一方を周りに移動します。 完了したら、両方のインデックス指を上げます。

### <a name="scroll-content-in-an-app-window"></a>アプリウィンドウのコンテンツをスクロールする

アプリウィンドウの内容を見つめます。 タップして押したまま、少し上または下に移動して、コンテンツをスクロールします。

## <a name="meet-the-hololens-1st-gen-clicker"></a>HoloLens (第1世代) Clicker を満たす

[HoloLens (第1世代) clicker](hololens1-clicker.md)は、ホログラムを操作する別の方法を提供します。 [これ](hololens-connect-devices.md)を HoloLens と組み合わせて使用し、選択、スクロールなどの目的に合わせて使用します。

## <a name="next-steps"></a>次のステップ

お疲れさまでした。 これで HoloLens (第1世代) を使用する準備が整いました。

これで、特定のニーズに合わせて HoloLens (第1世代) を構成できるようになりました。

[Connect bluetooth デバイス (マウス、キーボードなど)](hololens-connect-devices.md)

[音声と Cortana についての詳細情報](hololens-cortana.md)

### <a name="help-i-dont-see-my-holograms"></a>大変です。 ホログラムが表示されない

HoloLens の使用中に配置したホログラムが表示されない場合は、次の点を試してみてください。

- 右側の領域を見ていることを確認してください &mdash; 。ホログラムは残しておきます。
- 直接太陽のない部屋にいることを確認してください。
- 待機. スペースHoloLens認識に問題がある場合、以前に配置されたホログラムが再び表示されるのに最大で 1 分かかる場合があります。
- 問題が解決しない場合は **、設定** System ホログラム 内の ホログラム ストレージ データを消去してから、ホログラムを再び Mixed Reality ホーム  >    >  できます。
