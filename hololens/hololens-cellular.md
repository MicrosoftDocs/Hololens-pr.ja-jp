---
title: 携帯電話と 5G に接続する
description: HoloLens Mixed Reality デバイスから携帯電話ネットワークに接続します。
ms.assetid: f1aaadce-8762-41f8-bfeb-3b6067a2ec78
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 02/24/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 3fd5f6baf05277bcbf2bf4152ba4735ca91e5bd0
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385645"
---
# <a name="connect-to-cellular-and-5g"></a>携帯電話と 5G に接続する

HoloLens 2 は、携帯電話や 5G ネットワークに接続するための2 つの方法に対応しています。

- 携帯電話デバイスで提供されるアドホック WiFi ネットワーク (一般に "ホットスポット" と呼ばれます)
- USB-C テザード デバイスの制限付きサポート

## <a name="hotspot-wifi"></a>ホットスポット (WiFi)

ほとんどの携帯電話接続のニーズは、ホットスポットで満たすことができます。 HoloLens 2 WiFi は 802.11ac をサポートしています。これは、最も一般的なユース ケースに必要な帯域幅と待機時間の要件を満たします。 WiFi もケーブルフリーで、携帯電話デバイスの数が最も多い場合でも互換性があります。

### <a name="connecting-to-a-hotspot"></a>ホットスポットへの接続

1. ホットスポット モードを有効にする方法については、デバイスのマニュアルを参照してください。
1. ホットスポット モードを有効にし、ネットワークの名前と既知のパスワードを入力します。
1. HoloLens 2 ネットワーク設定で、手順 2 で作成した WiFi ネットワークを検索して参加します。

## <a name="usb-c-tethering"></a>USB-C テザリング

USB-C テザリングを使用すると、それを必要とする高度なワークロードの待機時間が短くなります。 たとえば、[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering) は、テザリングによるメリットがあります。 テザリングには携帯電話デバイスと HoloLens の間のケーブルが必要であり、テザリングは限られた数のデバイスでサポートされます。

### <a name="usb-c-compatibility"></a>USB-C の互換性

イーサネット アダプターとして表示されるデバイスは、Windows Holographic バージョン 2004 以降で使用できます。

イーサネット アダプターとして表示されないデバイスは、汎用 Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) ドライバーをサポートしている必要があります。 汎用 Microsoft RNDIS ドライバーをサポートしているかどうかの詳細については、デバイスの製造元にお問い合わせください。

RNDIS と互換性がないデバイス、またはドライバーやアプリケーションをインストールする必要があるデバイスはサポートされていません。

Microsoft は互換性のあるデバイスの一覧を保持していませんが、[こちら](https://aka.ms/HLCommunityCell)のトピックにコミュニティ ディスカッションがあります。

### <a name="connecting-to-a-tethered-device"></a>テザリングされたデバイスへの接続

1. USB でデータ共有を有効にする方法については、デバイスのマニュアルを参照してください。 この設定は、多くの場合、"USB テザリング"、"データ共有" または "USB モデム" と呼ばれます。
1. USB でのデータ共有を有効にします。
1. デバイスを HoloLens USB-C ポートに接続します。
1. HoloLens 2 ネットワーク設定では、デバイスはイーサネット接続として自動的に表示されます。
