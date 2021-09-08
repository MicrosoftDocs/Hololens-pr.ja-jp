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
ms.openlocfilehash: d9c8b813ba54edbcfef8d1a32e641dad39a7f193
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189088"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Bluetooth および USB-C デバイスに接続する

## <a name="pair-bluetooth-devices"></a>Bluetooth デバイスをペアリングする

HoloLens 2 は、次のクラスの Bluetooth デバイスをサポートします。

- [HID](/windows-hardware/drivers/hid/):
    - マウス
    - キーボード
- オーディオ出力 (A2DP) デバイス

HoloLens 2では、次の Bluetooth API がサポートされます。
- GATT [サーバー](/windows/uwp/devices-sensors/gatt-server) と [クライアント](/windows/uwp/devices-sensors/gatt-client)
- [RFCOMM](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> HID デバイスと GATT デバイスを実際に使用するには、Microsoft Store から対応するコンパニオン アプリをインストールしなければならない場合があります。

HoloLens (第１世代) は、次のクラスの Bluetooth デバイスをサポートします。

- マウス
- キーボード
- [HoloLens (第1世代) クリッカー](hololens1-clicker.md)

> [!NOTE]
> スピーカー、ヘッドセット、スマートフォン、ゲーム パッドなど、他の種類の Bluetooth デバイスは、HoloLens の [設定] で使用できるように表示されます。 ただし、これらのデバイスは HoloLens (第１世代) にはサポートされていません。 詳細については、[「HoloLens 設定リストでは使用可能となっているデバイスが機能しない」](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)を参照してください。

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Bluetooth キーボードまたはマウスをペアリングする

1. キーボードまたはマウスの電源をオンにして、検出可能にします。 デバイスを検出可能にする方法については、デバイス (またはそのドキュメント) に記載されている情報を検索するか、製造元の Web サイトにアクセスしてください。

1. ブルーム ジェスチャー (HoloLens (第１世代)) またはスタート ジェスチャー (HoloLens 2) を使用して、**スタート** に移動し、 **[設定]** を選択します。

1. **[デバイス]** を選択し、Bluetooth がオンになっていることを確認します。  

1. デバイス名が表示されたら、 **[ペア]** を選び、指示に従います。

## <a name="disable-bluetooth"></a>Bluetooth を無効にする

この手順を実行すると、Bluetooth 無線の RF コンポーネントの電源がオフになり、Microsoft HoloLens の Bluetooth 機能がすべて無効になります。

1. ブルーム ジェスチャー (HoloLens (第１世代)) またはスタート ジェスチャー (HoloLens 2) を使用して、**スタート** に移動し、 **[設定]**  >  **[デバイス]** を選択します。

1. **Bluetooth** のスライダー スイッチを **[オフ]** の位置に移動します。

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: USB-C デバイスに接続する

HoloLens 2 は、次のクラスの USB-C デバイスをサポートします。

- 大容量記憶装置 (サム ドライブ) など）
- イーサネット アダプター (イーサネット + 充電を含む)
- USB-C - 3.5 mm デジタル オーディオ アダプター
- USB C デジタル オーディオ ヘッドセット (ヘッドセット アダプター + 充電を含む)
- USB-C 外部マイク ([Windows Holographic バージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1)以上)
- 有線マウス
- 有線キーボード
- 複合 PD ハブ (USB-A + PD 充電器)


> [!NOTE]
> お客様からのフィードバックに応えて、USB-C を使用して HoloLens に直接テザリングされたセルラー接続の限定的なサポートを有効にしました。 詳細については[「携帯電話と 5G への接続」](hololens-cellular.md)を参照してください。

### <a name="usb-c-external-microphone-support"></a>USB-C 外部マイクのサポート

> [!IMPORTANT]
> USB マイクを **接続すると、入力デバイス として自動的に設定されません**。 USB-C の一連のヘッドセットを接続すると、ユーザーは、ヘッドセットのオーディオが自動的にヘッドセットにリダイレクトされるのを確認しますが、HoloLens OS では、他の入力デバイスよりも内部マイク 配列が優先されます。 **USB-C マイクを使用するには、次の手順に従います。**

> [!NOTE]
> [Windows Holographic、バージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1) 以前のビルドでは外部マイクを使用できません。 

ユーザーは、 **[サウンド]** 設定パネルを使用して USB-C 接続外部マイク を 選択できます。 USB-C マイクは、通話や録音などに使用できます。

**設定** アプリを開いて **[システム]**  >  **[サウンド]** を選択します。

![サウンド設定。](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> 外部マイクを **Remote Assist** で使用するには、[サウンド デバイスの管理] ハイパーリンクをクリックする必要があります。
>
> 次に、ドロップダウンを使用して、外部マイクを **[既定]** または **[通信の既定値]** に設定します。 **[既定]** を選択すると、外部マイクはどこででも使用されます。
>
> **[通信の既定値]** を選択すると、外部マイクは Remote Assist や他の通信アプリで使用されますが、HoloLens マイク 配列は他のタスクにも引き続き使用できます。

![サウンド デバイスを管理する。](images/usbc-mic-2.png)

<br>

![マイクの既定値を設定する。](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Bluetooth のマイクのサポートについてはどうですか?

残念ながら、Bluetoothマイクは現在も HoloLens 2 でサポートされません。

### <a name="usb-c-hubs"></a>USB-C ハブ

一部のユーザーは、複数のデバイスを同時に接続する必要がある場合があります。 [USB-C マイク](#usb-c-external-microphone-support)を別の接続デバイスと共に使用するユーザーの場合、USB-C ハブは顧客のニーズに合う場合があります。 Microsoft は、これらのデバイスをテストしていないので、特定のブランドをお勧めできません。

**USB-C ハブと接続されたデバイスの要件:**

- 接続されているデバイスでは、ドライバーをインストールする必要はありません。
- 接続されているすべてのデバイスの総消費電力は、4.5 ワット未満である必要があります。

## <a name="connect-to-miracast"></a>Miracast に接続する

Miracast を使うには、次の手順を実行します。

1. 次のいずれかの操作を行います。  

   - **[スタート]** メニューを開き、 **[ディスプレイ]** アイコンを選択しましょう。
   - **[スタート]** メニューを見つめながら、「接続」 と音声で指示します。  

1. 表示されたデバイスの一覧で、使用可能なデバイスを選択します。

1. ペアリングを完了させてプロジェクションを開始します。
