---
title: Bluetooth および USB-C デバイスに接続する
description: HoloLens Mixed Reality デバイスから Bluetooth デバイスと USB-C デバイス、およびアクセサリへの接続を開始します。
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
ms.openlocfilehash: 728bf8547315be96f879ff94a1290c1e2b3e7bf8
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385488"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Bluetooth および USB-C デバイスに接続する

> [!NOTE]
> 外付けマイクは使用できません。 HoloLens 2 は、内蔵の[マイクロフォン アレイ](hololens2-hardware.md#audio-and-speech)を使用します。

## <a name="pair-bluetooth-devices"></a>Bluetooth デバイスをペアリングする

HoloLens 2 は、次のクラスの Bluetooth デバイスをサポートします。

- マウス
- キーボード
- Bluetooth オーディオ出力 (A2DP) デバイス

HoloLens （第１世代） は、次のクラスの Bluetooth デバイスをサポートします。

- マウス
- キーボード
- [HoloLens (第1世代) クリッカー](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> スピーカー、ヘッドセット、スマートフォン、ゲーム パッドなど、他の種類の Bluetooth デバイスは、HoloLens の [設定] で使用できるように表示されます。 ただし、これらのデバイスは HoloLens (第１世代) にはサポートされていません。 詳細については、[HoloLens の設定には使用可能なデバイスが表示されるが、デバイスが機能しない](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work) を参照してください。

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Bluetooth キーボードまたはマウスをペアリングする

1. キーボードまたはマウスの電源をオンにして、検出可能にします。 デバイスを検出可能にする方法については、デバイス (またはそのドキュメント) に記載されている情報を検索するか、製造元の web サイトにアクセスしてください。

1. ブルーム ジェスチャー (HoloLens (第１世代）) またはスタート ジェスチャー (HoloLens 2) を使用して、**[スタート]** に移動し、**[設定]** を選択します。

1. **[デバイス]** を選択し、Bluetooth がオンになっていることを確認します。  

1. デバイス名が表示されたら、**[ペアリング]** を選び、指示に従います。

## <a name="disable-bluetooth"></a>Bluetooth を無効にする

この手順を実行すると、Bluetooth 無線の RF コンポーネントの電源がオフになり、Microsoft HoloLens の Bluetooth 機能がすべて無効になります。

1. ブルーム ジェスチャー (HoloLens (第１世代)) またはスタート ジェスチャー (HoloLens 2) を使用して **[スタート]** に移動し、**[設定]**  > **[デバイス]** を選択します。

1. **Bluetooth** のスライダー スイッチを **[オフ]** の位置に移動します。

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: USB-C デバイスに接続する

HoloLens 2 は、次のクラスの USB-C デバイスをサポートします。

- 大容量記憶装置 （サム ドライブなど）
- イーサネット アダプター （イーサネット + 充電を含む）
- USB-C - 3.5 mm デジタル オーディオ アダプター
- USB C デジタル オーディオ ヘッドセット (ヘッドセット アダプター + 充電を含む)
- 有線マウス
- 有線キーボード
- 複合 PD ハブ （USB-A + PD 充電器）

> [!NOTE]
> お客様からのフィードバックに応えて、USB-C を使用して HoloLens に直接テザリングされたセルラー接続の限定的なサポートを有効にしました。 詳細については、「[セルラーおよび 5G への接続](hololens-cellular.md)」を参照してください。

### <a name="usb-c-hubs"></a>USB-C ハブ

一部のユーザーは、複数のデバイスを同時に接続する必要がある場合があります。 Insider の機能をプレビューし、別の接続されたデバイスと共に [USB-C マイクを使用する](hololens-insider.md#usb-c-external-microphone-support)場合は、USB-C ハブがユーザーのニーズに合う場合があります。 Microsoft は、これらのデバイスをテストしていないので、特定のブランドをお勧めできません。

**USB-C ハブと接続されたデバイスの要件:**

- 接続されているデバイスでは、ドライバーをインストールする必要はありません。
- 接続されているすべてのデバイスの総消費電力は、4.5 ワット未満である必要があります。

## <a name="connect-to-miracast"></a>Miracast に接続する

Miracast を使うには、次の手順を実行します。

1. 次のいずれかの操作を行います。  

   - **[スタート]** メニューを開き、ディスプレイ アイコンを選択しましょう。
   - **[スタート]** メニューを見つめながら、「接続」 と音声で指示します。  

1. 表示されたデバイスの一覧で、使用可能なデバイスを選択します。

1. ペアリングを完了させてプロジェクションを開始します。
