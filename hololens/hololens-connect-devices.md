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
ms.openlocfilehash: afbcfd0762bea9e7a6bc217d5e4a2910eaab7359
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283348"
---
# <span data-ttu-id="211df-103">Bluetooth および USB-C デバイスに接続する</span><span class="sxs-lookup"><span data-stu-id="211df-103">Connect to Bluetooth and USB-C devices</span></span>

> [!NOTE]
> <span data-ttu-id="211df-104">外付けマイクは使用できません。</span><span class="sxs-lookup"><span data-stu-id="211df-104">External microphones cannot be used.</span></span> <span data-ttu-id="211df-105">HoloLens 2 は、内蔵の[マイクロフォン アレイ](hololens2-hardware.md#audio-and-speech)を使用します。</span><span class="sxs-lookup"><span data-stu-id="211df-105">HoloLens 2 uses its built-in [microphone array](hololens2-hardware.md#audio-and-speech).</span></span>

## <span data-ttu-id="211df-106">Bluetooth デバイスをペアリングする</span><span class="sxs-lookup"><span data-stu-id="211df-106">Pair Bluetooth devices</span></span>

<span data-ttu-id="211df-107">HoloLens 2 は、次のクラスの Bluetooth デバイスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="211df-107">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="211df-108">マウス</span><span class="sxs-lookup"><span data-stu-id="211df-108">Mouse</span></span>
- <span data-ttu-id="211df-109">キーボード</span><span class="sxs-lookup"><span data-stu-id="211df-109">Keyboard</span></span>
- <span data-ttu-id="211df-110">Bluetooth オーディオ出力 (A2DP) デバイス</span><span class="sxs-lookup"><span data-stu-id="211df-110">Bluetooth audio output (A2DP) devices</span></span>

<span data-ttu-id="211df-111">HoloLens （第１世代） は、次のクラスの Bluetooth デバイスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="211df-111">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="211df-112">マウス</span><span class="sxs-lookup"><span data-stu-id="211df-112">Mouse</span></span>
- <span data-ttu-id="211df-113">キーボード</span><span class="sxs-lookup"><span data-stu-id="211df-113">Keyboard</span></span>
- <span data-ttu-id="211df-114">HoloLens (第1世代) クリッカー</span><span class="sxs-lookup"><span data-stu-id="211df-114">HoloLens (1st gen) clicker</span></span>

> [!NOTE]
> <span data-ttu-id="211df-115">スピーカー、ヘッドセット、スマートフォン、ゲーム パッドなど、他の種類の Bluetooth デバイスは、HoloLens の [設定] で使用できるように表示されます。</span><span class="sxs-lookup"><span data-stu-id="211df-115">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="211df-116">ただし、これらのデバイスは HoloLens (第１世代) にはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="211df-116">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="211df-117">詳細については、[HoloLens の設定には使用可能なデバイスが表示されるが、デバイスが機能しない](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="211df-117">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <span data-ttu-id="211df-118">Bluetooth キーボードまたはマウスをペアリングする</span><span class="sxs-lookup"><span data-stu-id="211df-118">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="211df-119">キーボードまたはマウスの電源をオンにして、検出可能にします。</span><span class="sxs-lookup"><span data-stu-id="211df-119">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="211df-120">デバイスを検出可能にする方法については、デバイス (またはそのドキュメント) に記載されている情報を検索するか、製造元の web サイトにアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="211df-120">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="211df-121">ブルーム ジェスチャー (HoloLens (第１世代）) またはスタート ジェスチャー (HoloLens 2) を使用して、**[スタート]** に移動し、**[設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="211df-121">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="211df-122">**[デバイス]** を選択し、Bluetooth がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="211df-122">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="211df-123">デバイス名が表示されたら、**[ペアリング]** を選び、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="211df-123">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

### <span data-ttu-id="211df-124">HoloLens （第１世代） : クリッカーをペアリング</span><span class="sxs-lookup"><span data-stu-id="211df-124">HoloLens (1st gen): Pair the clicker</span></span>

1. <span data-ttu-id="211df-125">ブルーム ジェスチャを使用して **[スタート]** に移動し、**[設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="211df-125">Use the bloom gesture to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="211df-126">**[デバイス]** を選択し、Bluetooth がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="211df-126">Select **Devices**, and make sure that Bluetooth is on.</span></span>

1. <span data-ttu-id="211df-127">ペンのヒントを使用して、クリッカー ステータスが白色に点滅するまでクリッカーのペアリング ボタンを押し続けます。</span><span class="sxs-lookup"><span data-stu-id="211df-127">Use the tip of a pen to press and hold the clicker pairing button until the clicker status light blinks white.</span></span> <span data-ttu-id="211df-128">ライトが点滅するまで、ボタンを押したままにします。</span><span class="sxs-lookup"><span data-stu-id="211df-128">Make sure to hold down the button until the light starts blinking.</span></span>  

   <span data-ttu-id="211df-129">ペアリング ボタンはクリッカーの下側、フィンガー ループの隣にあります。</span><span class="sxs-lookup"><span data-stu-id="211df-129">The pairing button is on the underside of the clicker, next to the finger loop.</span></span>
   
   ![ペアリング ボタンは、フィンガー ループの隣にあります。](images/use-hololens-clicker-1.png)
   
1. <span data-ttu-id="211df-131">ペアリング画面で、**[クリッカー]** > **[ペアリング]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="211df-131">On the pairing screen, select **Clicker** > **Pair**.</span></span>

## <span data-ttu-id="211df-132">Bluetooth を無効にする</span><span class="sxs-lookup"><span data-stu-id="211df-132">Disable Bluetooth</span></span>

<span data-ttu-id="211df-133">この手順を実行すると、Bluetooth 無線の RF コンポーネントの電源がオフになり、Microsoft HoloLens の Bluetooth 機能がすべて無効になります。</span><span class="sxs-lookup"><span data-stu-id="211df-133">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="211df-134">ブルーム ジェスチャー (HoloLens (第１世代)) またはスタート ジェスチャー (HoloLens 2) を使用して **[スタート]** に移動し、**[設定]**  > **[デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="211df-134">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="211df-135">**Bluetooth** のスライダー スイッチを **[オフ]** の位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="211df-135">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <span data-ttu-id="211df-136">HoloLens 2: USB-C デバイスに接続する</span><span class="sxs-lookup"><span data-stu-id="211df-136">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="211df-137">HoloLens 2 は、次のクラスの USB-C デバイスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="211df-137">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="211df-138">大容量記憶装置 （サム ドライブなど）</span><span class="sxs-lookup"><span data-stu-id="211df-138">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="211df-139">イーサネット アダプター （イーサネット + 充電を含む）</span><span class="sxs-lookup"><span data-stu-id="211df-139">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="211df-140">USB-C - 3.5 mm デジタル オーディオ アダプター</span><span class="sxs-lookup"><span data-stu-id="211df-140">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="211df-141">USB C デジタル オーディオ ヘッドセット (ヘッドセット アダプター + 充電を含む)</span><span class="sxs-lookup"><span data-stu-id="211df-141">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="211df-142">有線マウス</span><span class="sxs-lookup"><span data-stu-id="211df-142">Wired mouse</span></span>
- <span data-ttu-id="211df-143">有線キーボード</span><span class="sxs-lookup"><span data-stu-id="211df-143">Wired keyboard</span></span>
- <span data-ttu-id="211df-144">複合 PD ハブ （USB-A + PD 充電器）</span><span class="sxs-lookup"><span data-stu-id="211df-144">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="211df-145">USB-C 接続を使用しているモバイル デバイスの中には、イーサネット アダプターとして HoloLens に直接表示されるため、Windows ホログラフィックのバージョン2004からテザリング構成で使用することができます。</span><span class="sxs-lookup"><span data-stu-id="211df-145">Some mobile devices with USB-C connections present themselves to the HoloLens as ethernet adaptors, and therefore could be used in a tethering configuration, starting with Windows Holographic, version 2004.</span></span> <span data-ttu-id="211df-146">別のドライバーが必要な USB LTE モデムと、構成用にインストールされるアプリケーションはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="211df-146">USB LTE modems that require a separate driver, and/or application installed for configuration are not supported.</span></span>

<span data-ttu-id="211df-147">お客様からのフィードバックに応えて、USB-C を使用して HoloLens に直接テザリングされた Cellular 接続の限定的なサポートを有効にしました。</span><span class="sxs-lookup"><span data-stu-id="211df-147">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span>  <span data-ttu-id="211df-148">テザリング接続 は、汎用 Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) ドライバーの実装をサポートし、追加のドライバーやアプリケーションのインストールを必要としないデバイスでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="211df-148">Tethered connectivity only works for devices that support the generic Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver implementation and that don’t require any additional drivers or application installs.</span></span>  <span data-ttu-id="211df-149">このようなデバイスが接続されると、HoloLens 2 のネットワーク設定 UI に新しいイーサネット接続として自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="211df-149">Such device, when connected, will automatically appear as a new Ethernet connection in the HoloLens 2 Network Settings UI.</span></span> <span data-ttu-id="211df-150">汎用 Microsoft RNDIS ドライバーをサポートしているかどうかの詳細については、デバイスの製造元にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="211df-150">Please consult your device’s manufacturer for further details on whether it supports the generic Microsoft RNDIS driver.</span></span>

## <span data-ttu-id="211df-151">Miracast に接続する</span><span class="sxs-lookup"><span data-stu-id="211df-151">Connect to Miracast</span></span>

<span data-ttu-id="211df-152">Miracast を使うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="211df-152">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="211df-153">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="211df-153">Do one of the following:</span></span>  

   - <span data-ttu-id="211df-154">**[スタート]** メニューを開き、ディスプレイ アイコンを選択しましょう。</span><span class="sxs-lookup"><span data-stu-id="211df-154">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="211df-155">**[スタート]** メニューを見つめながら、「接続」 と音声で指示します。</span><span class="sxs-lookup"><span data-stu-id="211df-155">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="211df-156">表示されたデバイスの一覧で、使用可能なデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="211df-156">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="211df-157">ペアリングを完了させてプロジェクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="211df-157">Complete the pairing to begin projecting.</span></span>
