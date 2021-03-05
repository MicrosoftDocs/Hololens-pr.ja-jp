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
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="c9d84-103">携帯電話と 5G に接続する</span><span class="sxs-lookup"><span data-stu-id="c9d84-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="c9d84-104">HoloLens 2 は、携帯電話や 5G ネットワークに接続するための2 つの方法に対応しています。</span><span class="sxs-lookup"><span data-stu-id="c9d84-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="c9d84-105">携帯電話デバイスで提供されるアドホック WiFi ネットワーク (一般に "ホットスポット" と呼ばれます)</span><span class="sxs-lookup"><span data-stu-id="c9d84-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="c9d84-106">USB-C テザード デバイスの制限付きサポート</span><span class="sxs-lookup"><span data-stu-id="c9d84-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="c9d84-107">ホットスポット (WiFi)</span><span class="sxs-lookup"><span data-stu-id="c9d84-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="c9d84-108">ほとんどの携帯電話接続のニーズは、ホットスポットで満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="c9d84-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="c9d84-109">HoloLens 2 WiFi は 802.11ac をサポートしています。これは、最も一般的なユース ケースに必要な帯域幅と待機時間の要件を満たします。</span><span class="sxs-lookup"><span data-stu-id="c9d84-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="c9d84-110">WiFi もケーブルフリーで、携帯電話デバイスの数が最も多い場合でも互換性があります。</span><span class="sxs-lookup"><span data-stu-id="c9d84-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="c9d84-111">ホットスポットへの接続</span><span class="sxs-lookup"><span data-stu-id="c9d84-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="c9d84-112">ホットスポット モードを有効にする方法については、デバイスのマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9d84-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="c9d84-113">ホットスポット モードを有効にし、ネットワークの名前と既知のパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="c9d84-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="c9d84-114">HoloLens 2 ネットワーク設定で、手順 2 で作成した WiFi ネットワークを検索して参加します。</span><span class="sxs-lookup"><span data-stu-id="c9d84-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="c9d84-115">USB-C テザリング</span><span class="sxs-lookup"><span data-stu-id="c9d84-115">USB-C Tethering</span></span>

<span data-ttu-id="c9d84-116">USB-C テザリングを使用すると、それを必要とする高度なワークロードの待機時間が短くなります。</span><span class="sxs-lookup"><span data-stu-id="c9d84-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="c9d84-117">たとえば、[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering) は、テザリングによるメリットがあります。</span><span class="sxs-lookup"><span data-stu-id="c9d84-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="c9d84-118">テザリングには携帯電話デバイスと HoloLens の間のケーブルが必要であり、テザリングは限られた数のデバイスでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c9d84-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="c9d84-119">USB-C の互換性</span><span class="sxs-lookup"><span data-stu-id="c9d84-119">USB-C compatibility</span></span>

<span data-ttu-id="c9d84-120">イーサネット アダプターとして表示されるデバイスは、Windows Holographic バージョン 2004 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9d84-120">Devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="c9d84-121">イーサネット アダプターとして表示されないデバイスは、汎用 Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) ドライバーをサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9d84-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="c9d84-122">汎用 Microsoft RNDIS ドライバーをサポートしているかどうかの詳細については、デバイスの製造元にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="c9d84-122">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="c9d84-123">RNDIS と互換性がないデバイス、またはドライバーやアプリケーションをインストールする必要があるデバイスはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c9d84-123">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="c9d84-124">Microsoft は互換性のあるデバイスの一覧を保持していませんが、[こちら](https://aka.ms/HLCommunityCell)のトピックにコミュニティ ディスカッションがあります。</span><span class="sxs-lookup"><span data-stu-id="c9d84-124">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="c9d84-125">テザリングされたデバイスへの接続</span><span class="sxs-lookup"><span data-stu-id="c9d84-125">Connecting to a tethered device</span></span>

1. <span data-ttu-id="c9d84-126">USB でデータ共有を有効にする方法については、デバイスのマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9d84-126">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="c9d84-127">この設定は、多くの場合、"USB テザリング"、"データ共有" または "USB モデム" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c9d84-127">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="c9d84-128">USB でのデータ共有を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c9d84-128">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="c9d84-129">デバイスを HoloLens USB-C ポートに接続します。</span><span class="sxs-lookup"><span data-stu-id="c9d84-129">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="c9d84-130">HoloLens 2 ネットワーク設定では、デバイスはイーサネット接続として自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9d84-130">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
