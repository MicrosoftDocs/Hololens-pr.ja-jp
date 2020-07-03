---
title: Bluetooth および USB-C デバイスに接続する
description: このガイドでは、Bluetooth、USB-C デバイスおよびアクセサリに接続する方法について説明します。
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: d4c5441c1df198ae1c85be5d8f4fe38f10f0be4b
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828712"
---
# Bluetooth および USB-C デバイスに接続する

## Bluetooth デバイスをペアリングする

HoloLens 2 は、次のクラスの Bluetooth デバイスをサポートします。

- マウス
- キーボード
- Bluetooth オーディオ出力 (A2DP) デバイス

HoloLens （第１世代） は、次のクラスの Bluetooth デバイスをサポートします。

- マウス
- キーボード
- HoloLens (第1世代) クリッカー

> [!NOTE]
> スピーカー、ヘッドセット、スマートフォン、ゲーム パッドなど、他の種類の Bluetooth デバイスは、HoloLens の [設定] で使用できるように表示されます。 ただし、これらのデバイスは HoloLens (第１世代) にはサポートされていません。 詳細については、[HoloLens の設定には使用可能なデバイスが表示されるが、デバイスが機能しない](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work) を参照してください。

### Bluetooth キーボードまたはマウスをペアリングする

1. キーボードまたはマウスの電源をオンにして、検出可能にします。 デバイスを検出可能にする方法については、デバイス (またはそのドキュメント) に記載されている情報を検索するか、製造元の web サイトにアクセスしてください。

1. ブルーム ジェスチャー (HoloLens (第１世代）) またはスタート ジェスチャー (HoloLens 2) を使用して、**[スタート]** に移動し、**[設定]** を選択します。
1. **[デバイス]** を選択し、Bluetooth がオンになっていることを確認します。  
1. デバイス名が表示されたら、**[ペアリング]** を選び、指示に従います。

### HoloLens （第１世代） : クリッカーをペアリング

1. ブルーム ジェスチャを使用して **[スタート]** に移動し、**[設定]** を選択します。

1. **[デバイス]** を選択し、Bluetooth がオンになっていることを確認します。

1. ペンのヒントを使用して、クリッカー ステータスが白色に点滅するまでクリッカーのペアリング ボタンを押し続けます。 ライトが点滅するまで、ボタンを押したままにします。  

   ペアリング ボタンはクリッカーの下側、フィンガー ループの隣にあります。
   
   ![ペアリング ボタンは、フィンガー ループの隣にあります。](images/use-hololens-clicker-1.png)
   
1. ペアリング画面で、**[クリッカー]** > **[ペアリング]** を選択します。

## HoloLens 2: USB-C デバイスに接続する

HoloLens 2 は、次のクラスの USB-C デバイスをサポートします。

- 大容量記憶装置 （サム ドライブなど）
- イーサネット アダプター （イーサネット + 充電を含む）
- USB-C - 3.5 mm デジタル オーディオ アダプター
- USB C デジタル オーディオ ヘッドセット (ヘッドセット アダプター + 充電を含む)
- 有線マウス
- 有線キーボード
- 複合 PD ハブ （USB-A + PD 充電器）

> [!NOTE]
> USB-C 接続を使用しているモバイル デバイスの中には、イーサネット アダプターとして HoloLens に直接表示されるため、Windows ホログラフィックのバージョン2004からテザリング構成で使用することができます。 別のドライバーを必要とする USB LTE モデム、および構成用にインストールされるアプリケーションがサポートされない

## Miracast に接続する

Miracast を使うには、次の手順を実行します。

1. 次のいずれかの操作を行います。  

   - **[スタート]** メニューを開き、ディスプレイ アイコンを選択しましょう。
   - **[スタート]** メニューを見つめながら、「接続」 と音声で指示します。  

1. 表示されたデバイスの一覧で、使用可能なデバイスを選択します。
1. ペアリングを完了させてプロジェクションを開始します。

## Bluetooth を無効にする

この手順を実行すると、Bluetooth 無線の RF コンポーネントの電源がオフになり、Microsoft HoloLens の Bluetooth 機能がすべて無効になります。

1. ブルーム ジェスチャー (HoloLens (第１世代)) またはスタート ジェスチャー (HoloLens 2) を使用して **[スタート]** に移動し、**[設定]**  > **[デバイス]** を選択します。
1. **Bluetooth** のスライダー スイッチを **[オフ]** の位置に移動します。
