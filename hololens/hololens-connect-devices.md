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
ms.openlocfilehash: 53d426b4319dafd0dd976e67111992020507f719
ms.sourcegitcommit: 563797405f7470f979a27718c604df920efbb368
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881247"
---
# <span data-ttu-id="d1452-103">Bluetooth および USB-C デバイスに接続する</span><span class="sxs-lookup"><span data-stu-id="d1452-103">Connect to Bluetooth and USB-C devices</span></span>

## <span data-ttu-id="d1452-104">Bluetooth デバイスをペアリングする</span><span class="sxs-lookup"><span data-stu-id="d1452-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="d1452-105">HoloLens 2 は、次のクラスの Bluetooth デバイスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="d1452-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="d1452-106">マウス</span><span class="sxs-lookup"><span data-stu-id="d1452-106">Mouse</span></span>
- <span data-ttu-id="d1452-107">キーボード</span><span class="sxs-lookup"><span data-stu-id="d1452-107">Keyboard</span></span>
- <span data-ttu-id="d1452-108">Bluetooth オーディオ出力 (A2DP) デバイス</span><span class="sxs-lookup"><span data-stu-id="d1452-108">Bluetooth audio output (A2DP) devices</span></span>

> [!NOTE]
> <span data-ttu-id="d1452-109">外付けマイクは使用できません。</span><span class="sxs-lookup"><span data-stu-id="d1452-109">External microphones cannot be used.</span></span> <span data-ttu-id="d1452-110">HoloLens 2 は、内蔵の[マイクロフォン アレイ](hololens2-hardware.md#audio-and-speech)を使用します。</span><span class="sxs-lookup"><span data-stu-id="d1452-110">HoloLens 2 uses its built-in [microphone array](hololens2-hardware.md#audio-and-speech).</span></span>

<span data-ttu-id="d1452-111">HoloLens （第１世代） は、次のクラスの Bluetooth デバイスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="d1452-111">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="d1452-112">マウス</span><span class="sxs-lookup"><span data-stu-id="d1452-112">Mouse</span></span>
- <span data-ttu-id="d1452-113">キーボード</span><span class="sxs-lookup"><span data-stu-id="d1452-113">Keyboard</span></span>
- <span data-ttu-id="d1452-114">HoloLens (第1世代) クリッカー</span><span class="sxs-lookup"><span data-stu-id="d1452-114">HoloLens (1st gen) clicker</span></span>

> [!NOTE]
> <span data-ttu-id="d1452-115">スピーカー、ヘッドセット、スマートフォン、ゲーム パッドなど、他の種類の Bluetooth デバイスは、HoloLens の [設定] で使用できるように表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1452-115">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="d1452-116">ただし、これらのデバイスは HoloLens (第１世代) にはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d1452-116">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="d1452-117">詳細については、[HoloLens の設定には使用可能なデバイスが表示されるが、デバイスが機能しない](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1452-117">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <span data-ttu-id="d1452-118">Bluetooth キーボードまたはマウスをペアリングする</span><span class="sxs-lookup"><span data-stu-id="d1452-118">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="d1452-119">キーボードまたはマウスの電源をオンにして、検出可能にします。</span><span class="sxs-lookup"><span data-stu-id="d1452-119">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="d1452-120">デバイスを検出可能にする方法については、デバイス (またはそのドキュメント) に記載されている情報を検索するか、製造元の web サイトにアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="d1452-120">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="d1452-121">ブルーム ジェスチャー (HoloLens (第１世代）) またはスタート ジェスチャー (HoloLens 2) を使用して、**[スタート]** に移動し、**[設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1452-121">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="d1452-122">**[デバイス]** を選択し、Bluetooth がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d1452-122">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="d1452-123">デバイス名が表示されたら、**[ペアリング]** を選び、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="d1452-123">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

### <span data-ttu-id="d1452-124">HoloLens （第１世代） : クリッカーをペアリング</span><span class="sxs-lookup"><span data-stu-id="d1452-124">HoloLens (1st gen): Pair the clicker</span></span>

1. <span data-ttu-id="d1452-125">ブルーム ジェスチャを使用して **[スタート]** に移動し、**[設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1452-125">Use the bloom gesture to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="d1452-126">**[デバイス]** を選択し、Bluetooth がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d1452-126">Select **Devices**, and make sure that Bluetooth is on.</span></span>

1. <span data-ttu-id="d1452-127">ペンのヒントを使用して、クリッカー ステータスが白色に点滅するまでクリッカーのペアリング ボタンを押し続けます。</span><span class="sxs-lookup"><span data-stu-id="d1452-127">Use the tip of a pen to press and hold the clicker pairing button until the clicker status light blinks white.</span></span> <span data-ttu-id="d1452-128">ライトが点滅するまで、ボタンを押したままにします。</span><span class="sxs-lookup"><span data-stu-id="d1452-128">Make sure to hold down the button until the light starts blinking.</span></span>  

   <span data-ttu-id="d1452-129">ペアリング ボタンはクリッカーの下側、フィンガー ループの隣にあります。</span><span class="sxs-lookup"><span data-stu-id="d1452-129">The pairing button is on the underside of the clicker, next to the finger loop.</span></span>
   
   ![ペアリング ボタンは、フィンガー ループの隣にあります。](images/use-hololens-clicker-1.png)
   
1. <span data-ttu-id="d1452-131">ペアリング画面で、**[クリッカー]** > **[ペアリング]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1452-131">On the pairing screen, select **Clicker** > **Pair**.</span></span>

## <span data-ttu-id="d1452-132">HoloLens 2: USB-C デバイスに接続する</span><span class="sxs-lookup"><span data-stu-id="d1452-132">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="d1452-133">HoloLens 2 は、次のクラスの USB-C デバイスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="d1452-133">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="d1452-134">大容量記憶装置 （サム ドライブなど）</span><span class="sxs-lookup"><span data-stu-id="d1452-134">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="d1452-135">イーサネット アダプター （イーサネット + 充電を含む）</span><span class="sxs-lookup"><span data-stu-id="d1452-135">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="d1452-136">USB-C - 3.5 mm デジタル オーディオ アダプター</span><span class="sxs-lookup"><span data-stu-id="d1452-136">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="d1452-137">USB C デジタル オーディオ ヘッドセット (ヘッドセット アダプター + 充電を含む)</span><span class="sxs-lookup"><span data-stu-id="d1452-137">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="d1452-138">有線マウス</span><span class="sxs-lookup"><span data-stu-id="d1452-138">Wired mouse</span></span>
- <span data-ttu-id="d1452-139">有線キーボード</span><span class="sxs-lookup"><span data-stu-id="d1452-139">Wired keyboard</span></span>
- <span data-ttu-id="d1452-140">複合 PD ハブ （USB-A + PD 充電器）</span><span class="sxs-lookup"><span data-stu-id="d1452-140">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="d1452-141">USB-C 接続を使用しているモバイル デバイスの中には、イーサネット アダプターとして HoloLens に直接表示されるため、Windows ホログラフィックのバージョン2004からテザリング構成で使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d1452-141">Some mobile devices with USB-C connections present themselves to the HoloLens as ethernet adaptors, and therefore could be used in a tethering configuration, starting with Windows Holographic, version 2004.</span></span> <span data-ttu-id="d1452-142">別のドライバーが必要な USB LTE モデムと、構成用にインストールされるアプリケーションはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="d1452-142">USB LTE modems that require a separate driver, and/or application installed for configuration are not supported.</span></span>

## <span data-ttu-id="d1452-143">Miracast に接続する</span><span class="sxs-lookup"><span data-stu-id="d1452-143">Connect to Miracast</span></span>

<span data-ttu-id="d1452-144">Miracast を使うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d1452-144">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="d1452-145">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d1452-145">Do one of the following:</span></span>  

   - <span data-ttu-id="d1452-146">**[スタート]** メニューを開き、ディスプレイ アイコンを選択しましょう。</span><span class="sxs-lookup"><span data-stu-id="d1452-146">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="d1452-147">**[スタート]** メニューを見つめながら、「接続」 と音声で指示します。</span><span class="sxs-lookup"><span data-stu-id="d1452-147">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="d1452-148">表示されたデバイスの一覧で、使用可能なデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d1452-148">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="d1452-149">ペアリングを完了させてプロジェクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="d1452-149">Complete the pairing to begin projecting.</span></span>

## <span data-ttu-id="d1452-150">Bluetooth を無効にする</span><span class="sxs-lookup"><span data-stu-id="d1452-150">Disable Bluetooth</span></span>

<span data-ttu-id="d1452-151">この手順を実行すると、Bluetooth 無線の RF コンポーネントの電源がオフになり、Microsoft HoloLens の Bluetooth 機能がすべて無効になります。</span><span class="sxs-lookup"><span data-stu-id="d1452-151">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="d1452-152">ブルーム ジェスチャー (HoloLens (第１世代)) またはスタート ジェスチャー (HoloLens 2) を使用して **[スタート]** に移動し、**[設定]**  > **[デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1452-152">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="d1452-153">**Bluetooth** のスライダー スイッチを **[オフ]** の位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="d1452-153">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>
