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
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="90c4a-103">Bluetooth および USB-C デバイスに接続する</span><span class="sxs-lookup"><span data-stu-id="90c4a-103">Connect to Bluetooth and USB-C devices</span></span>

> [!NOTE]
> <span data-ttu-id="90c4a-104">外付けマイクは使用できません。</span><span class="sxs-lookup"><span data-stu-id="90c4a-104">External microphones cannot be used.</span></span> <span data-ttu-id="90c4a-105">HoloLens 2 は、内蔵の[マイクロフォン アレイ](hololens2-hardware.md#audio-and-speech)を使用します。</span><span class="sxs-lookup"><span data-stu-id="90c4a-105">HoloLens 2 uses its built-in [microphone array](hololens2-hardware.md#audio-and-speech).</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="90c4a-106">Bluetooth デバイスをペアリングする</span><span class="sxs-lookup"><span data-stu-id="90c4a-106">Pair Bluetooth devices</span></span>

<span data-ttu-id="90c4a-107">HoloLens 2 は、次のクラスの Bluetooth デバイスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="90c4a-107">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="90c4a-108">マウス</span><span class="sxs-lookup"><span data-stu-id="90c4a-108">Mouse</span></span>
- <span data-ttu-id="90c4a-109">キーボード</span><span class="sxs-lookup"><span data-stu-id="90c4a-109">Keyboard</span></span>
- <span data-ttu-id="90c4a-110">Bluetooth オーディオ出力 (A2DP) デバイス</span><span class="sxs-lookup"><span data-stu-id="90c4a-110">Bluetooth audio output (A2DP) devices</span></span>

<span data-ttu-id="90c4a-111">HoloLens （第１世代） は、次のクラスの Bluetooth デバイスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="90c4a-111">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="90c4a-112">マウス</span><span class="sxs-lookup"><span data-stu-id="90c4a-112">Mouse</span></span>
- <span data-ttu-id="90c4a-113">キーボード</span><span class="sxs-lookup"><span data-stu-id="90c4a-113">Keyboard</span></span>
- [<span data-ttu-id="90c4a-114">HoloLens (第1世代) クリッカー</span><span class="sxs-lookup"><span data-stu-id="90c4a-114">HoloLens (1st gen) clicker</span></span>](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> <span data-ttu-id="90c4a-115">スピーカー、ヘッドセット、スマートフォン、ゲーム パッドなど、他の種類の Bluetooth デバイスは、HoloLens の [設定] で使用できるように表示されます。</span><span class="sxs-lookup"><span data-stu-id="90c4a-115">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="90c4a-116">ただし、これらのデバイスは HoloLens (第１世代) にはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="90c4a-116">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="90c4a-117">詳細については、[HoloLens の設定には使用可能なデバイスが表示されるが、デバイスが機能しない](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90c4a-117">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="90c4a-118">Bluetooth キーボードまたはマウスをペアリングする</span><span class="sxs-lookup"><span data-stu-id="90c4a-118">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="90c4a-119">キーボードまたはマウスの電源をオンにして、検出可能にします。</span><span class="sxs-lookup"><span data-stu-id="90c4a-119">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="90c4a-120">デバイスを検出可能にする方法については、デバイス (またはそのドキュメント) に記載されている情報を検索するか、製造元の web サイトにアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="90c4a-120">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="90c4a-121">ブルーム ジェスチャー (HoloLens (第１世代）) またはスタート ジェスチャー (HoloLens 2) を使用して、**[スタート]** に移動し、**[設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="90c4a-121">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="90c4a-122">**[デバイス]** を選択し、Bluetooth がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="90c4a-122">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="90c4a-123">デバイス名が表示されたら、**[ペアリング]** を選び、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="90c4a-123">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="90c4a-124">Bluetooth を無効にする</span><span class="sxs-lookup"><span data-stu-id="90c4a-124">Disable Bluetooth</span></span>

<span data-ttu-id="90c4a-125">この手順を実行すると、Bluetooth 無線の RF コンポーネントの電源がオフになり、Microsoft HoloLens の Bluetooth 機能がすべて無効になります。</span><span class="sxs-lookup"><span data-stu-id="90c4a-125">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="90c4a-126">ブルーム ジェスチャー (HoloLens (第１世代)) またはスタート ジェスチャー (HoloLens 2) を使用して **[スタート]** に移動し、**[設定]**  > **[デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="90c4a-126">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="90c4a-127">**Bluetooth** のスライダー スイッチを **[オフ]** の位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="90c4a-127">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="90c4a-128">HoloLens 2: USB-C デバイスに接続する</span><span class="sxs-lookup"><span data-stu-id="90c4a-128">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="90c4a-129">HoloLens 2 は、次のクラスの USB-C デバイスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="90c4a-129">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="90c4a-130">大容量記憶装置 （サム ドライブなど）</span><span class="sxs-lookup"><span data-stu-id="90c4a-130">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="90c4a-131">イーサネット アダプター （イーサネット + 充電を含む）</span><span class="sxs-lookup"><span data-stu-id="90c4a-131">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="90c4a-132">USB-C - 3.5 mm デジタル オーディオ アダプター</span><span class="sxs-lookup"><span data-stu-id="90c4a-132">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="90c4a-133">USB C デジタル オーディオ ヘッドセット (ヘッドセット アダプター + 充電を含む)</span><span class="sxs-lookup"><span data-stu-id="90c4a-133">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="90c4a-134">有線マウス</span><span class="sxs-lookup"><span data-stu-id="90c4a-134">Wired mouse</span></span>
- <span data-ttu-id="90c4a-135">有線キーボード</span><span class="sxs-lookup"><span data-stu-id="90c4a-135">Wired keyboard</span></span>
- <span data-ttu-id="90c4a-136">複合 PD ハブ （USB-A + PD 充電器）</span><span class="sxs-lookup"><span data-stu-id="90c4a-136">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="90c4a-137">お客様からのフィードバックに応えて、USB-C を使用して HoloLens に直接テザリングされたセルラー接続の限定的なサポートを有効にしました。</span><span class="sxs-lookup"><span data-stu-id="90c4a-137">In response to customer feedback we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="90c4a-138">詳細については、「[セルラーおよび 5G への接続](hololens-cellular.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90c4a-138">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="90c4a-139">USB-C ハブ</span><span class="sxs-lookup"><span data-stu-id="90c4a-139">USB-C Hubs</span></span>

<span data-ttu-id="90c4a-140">一部のユーザーは、複数のデバイスを同時に接続する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="90c4a-140">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="90c4a-141">Insider の機能をプレビューし、別の接続されたデバイスと共に [USB-C マイクを使用する](hololens-insider.md#usb-c-external-microphone-support)場合は、USB-C ハブがユーザーのニーズに合う場合があります。</span><span class="sxs-lookup"><span data-stu-id="90c4a-141">For users who would like to preview an Insider feature and [use a USB-C microphone](hololens-insider.md#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="90c4a-142">Microsoft は、これらのデバイスをテストしていないので、特定のブランドをお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="90c4a-142">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

**<span data-ttu-id="90c4a-143">USB-C ハブと接続されたデバイスの要件:</span><span class="sxs-lookup"><span data-stu-id="90c4a-143">Requirements for USB-C hub and connected devices:</span></span>**

- <span data-ttu-id="90c4a-144">接続されているデバイスでは、ドライバーをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="90c4a-144">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="90c4a-145">接続されているすべてのデバイスの総消費電力は、4.5 ワット未満である必要があります。</span><span class="sxs-lookup"><span data-stu-id="90c4a-145">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="90c4a-146">Miracast に接続する</span><span class="sxs-lookup"><span data-stu-id="90c4a-146">Connect to Miracast</span></span>

<span data-ttu-id="90c4a-147">Miracast を使うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="90c4a-147">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="90c4a-148">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="90c4a-148">Do one of the following:</span></span>  

   - <span data-ttu-id="90c4a-149">**[スタート]** メニューを開き、ディスプレイ アイコンを選択しましょう。</span><span class="sxs-lookup"><span data-stu-id="90c4a-149">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="90c4a-150">**[スタート]** メニューを見つめながら、「接続」 と音声で指示します。</span><span class="sxs-lookup"><span data-stu-id="90c4a-150">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="90c4a-151">表示されたデバイスの一覧で、使用可能なデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="90c4a-151">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="90c4a-152">ペアリングを完了させてプロジェクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="90c4a-152">Complete the pairing to begin projecting.</span></span>
