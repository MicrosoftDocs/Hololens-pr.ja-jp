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
ms.openlocfilehash: 5fed56d7a0beeda0a0d96eddc63aaee872f3e52d
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639099"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="e34be-103">Bluetooth および USB-C デバイスに接続する</span><span class="sxs-lookup"><span data-stu-id="e34be-103">Connect to Bluetooth and USB-C devices</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="e34be-104">Bluetooth デバイスをペアリングする</span><span class="sxs-lookup"><span data-stu-id="e34be-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="e34be-105">HoloLens 2 は、次のクラスの Bluetooth デバイスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e34be-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="e34be-106">[HID](/windows-hardware/drivers/hid/):</span><span class="sxs-lookup"><span data-stu-id="e34be-106">[HID](/windows-hardware/drivers/hid/):</span></span>
    - <span data-ttu-id="e34be-107">マウス</span><span class="sxs-lookup"><span data-stu-id="e34be-107">Mouse</span></span>
    - <span data-ttu-id="e34be-108">キーボード</span><span class="sxs-lookup"><span data-stu-id="e34be-108">Keyboard</span></span>
- <span data-ttu-id="e34be-109">オーディオ出力 (A2DP) デバイス</span><span class="sxs-lookup"><span data-stu-id="e34be-109">Audio output (A2DP) devices</span></span>

<span data-ttu-id="e34be-110">HoloLens 2では、次の Bluetooth API がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e34be-110">HoloLens 2 supports the following Bluetooth APIs:</span></span>
- <span data-ttu-id="e34be-111">GATT [サーバー](/windows/uwp/devices-sensors/gatt-server) と [クライアント](/windows/uwp/devices-sensors/gatt-client)</span><span class="sxs-lookup"><span data-stu-id="e34be-111">GATT [Server](/windows/uwp/devices-sensors/gatt-server) and [Client](/windows/uwp/devices-sensors/gatt-client)</span></span>
- [<span data-ttu-id="e34be-112">RFCOMM</span><span class="sxs-lookup"><span data-stu-id="e34be-112">RFCOMM</span></span>](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> <span data-ttu-id="e34be-113">HID デバイスと GATT デバイスを実際に使用するには、Microsoft Store から対応するコンパニオン アプリをインストールしなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e34be-113">You may have to install corresponding companion apps from Microsoft Store to actually use the HID and GATT devices.</span></span>

<span data-ttu-id="e34be-114">HoloLens (第１世代) は、次のクラスの Bluetooth デバイスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e34be-114">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="e34be-115">マウス</span><span class="sxs-lookup"><span data-stu-id="e34be-115">Mouse</span></span>
- <span data-ttu-id="e34be-116">キーボード</span><span class="sxs-lookup"><span data-stu-id="e34be-116">Keyboard</span></span>
- [<span data-ttu-id="e34be-117">HoloLens (第1世代) クリッカー</span><span class="sxs-lookup"><span data-stu-id="e34be-117">HoloLens (1st gen) clicker</span></span>](hololens1-clicker.md)

> [!NOTE]
> <span data-ttu-id="e34be-118">スピーカー、ヘッドセット、スマートフォン、ゲーム パッドなど、他の種類の Bluetooth デバイスは、HoloLens の [設定] で使用できるように表示されます。</span><span class="sxs-lookup"><span data-stu-id="e34be-118">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="e34be-119">ただし、これらのデバイスは HoloLens (第１世代) にはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e34be-119">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="e34be-120">詳細については、[「HoloLens 設定リストでは使用可能となっているデバイスが機能しない」](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e34be-120">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="e34be-121">Bluetooth キーボードまたはマウスをペアリングする</span><span class="sxs-lookup"><span data-stu-id="e34be-121">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="e34be-122">キーボードまたはマウスの電源をオンにして、検出可能にします。</span><span class="sxs-lookup"><span data-stu-id="e34be-122">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="e34be-123">デバイスを検出可能にする方法については、デバイス (またはそのドキュメント) に記載されている情報を検索するか、製造元の Web サイトにアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="e34be-123">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="e34be-124">ブルーム ジェスチャー (HoloLens (第１世代)) またはスタート ジェスチャー (HoloLens 2) を使用して、**スタート** に移動し、 **[設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e34be-124">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="e34be-125">**[デバイス]** を選択し、Bluetooth がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e34be-125">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="e34be-126">デバイス名が表示されたら、 **[ペア]** を選び、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="e34be-126">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="e34be-127">Bluetooth を無効にする</span><span class="sxs-lookup"><span data-stu-id="e34be-127">Disable Bluetooth</span></span>

<span data-ttu-id="e34be-128">この手順を実行すると、Bluetooth 無線の RF コンポーネントの電源がオフになり、Microsoft HoloLens の Bluetooth 機能がすべて無効になります。</span><span class="sxs-lookup"><span data-stu-id="e34be-128">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="e34be-129">ブルーム ジェスチャー (HoloLens (第１世代)) またはスタート ジェスチャー (HoloLens 2) を使用して、**スタート** に移動し、 **[設定]**  >  **[デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e34be-129">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="e34be-130">**Bluetooth** のスライダー スイッチを **[オフ]** の位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="e34be-130">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="e34be-131">HoloLens 2: USB-C デバイスに接続する</span><span class="sxs-lookup"><span data-stu-id="e34be-131">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="e34be-132">HoloLens 2 は、次のクラスの USB-C デバイスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e34be-132">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="e34be-133">大容量記憶装置 (サム ドライブ) など）</span><span class="sxs-lookup"><span data-stu-id="e34be-133">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="e34be-134">イーサネット アダプター (イーサネット + 充電を含む)</span><span class="sxs-lookup"><span data-stu-id="e34be-134">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="e34be-135">USB-C - 3.5 mm デジタル オーディオ アダプター</span><span class="sxs-lookup"><span data-stu-id="e34be-135">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="e34be-136">USB C デジタル オーディオ ヘッドセット (ヘッドセット アダプター + 充電を含む)</span><span class="sxs-lookup"><span data-stu-id="e34be-136">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="e34be-137">USB-C 外部マイク ([Windows Holographic バージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1)以上)</span><span class="sxs-lookup"><span data-stu-id="e34be-137">USB-C External Microphones ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher)</span></span>
- <span data-ttu-id="e34be-138">有線マウス</span><span class="sxs-lookup"><span data-stu-id="e34be-138">Wired mouse</span></span>
- <span data-ttu-id="e34be-139">有線キーボード</span><span class="sxs-lookup"><span data-stu-id="e34be-139">Wired keyboard</span></span>
- <span data-ttu-id="e34be-140">複合 PD ハブ (USB-A + PD 充電器)</span><span class="sxs-lookup"><span data-stu-id="e34be-140">Combination PD hubs (USB A plus PD charging)</span></span>


> [!NOTE]
> <span data-ttu-id="e34be-141">お客様からのフィードバックに応えて、USB-C を使用して HoloLens に直接テザリングされたセルラー接続の限定的なサポートを有効にしました。</span><span class="sxs-lookup"><span data-stu-id="e34be-141">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="e34be-142">詳細については[「携帯電話と 5G への接続」](hololens-cellular.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e34be-142">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="e34be-143">USB-C 外部マイクのサポート</span><span class="sxs-lookup"><span data-stu-id="e34be-143">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e34be-144">USB マイクを **接続すると、入力デバイス として自動的に設定されません**。</span><span class="sxs-lookup"><span data-stu-id="e34be-144">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="e34be-145">USB-C の一連のヘッドセットを接続すると、ユーザーは、ヘッドセットのオーディオが自動的にヘッドセットにリダイレクトされるのを確認しますが、HoloLens OS では、他の入力デバイスよりも内部マイク 配列が優先されます。</span><span class="sxs-lookup"><span data-stu-id="e34be-145">When plugging in a set of USB-C headphones, users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> <span data-ttu-id="e34be-146">**USB-C マイクを使用するには、次の手順に従います。**</span><span class="sxs-lookup"><span data-stu-id="e34be-146">**In order to use a USB-C microphone follow the steps below.**</span></span>

> [!NOTE]
> <span data-ttu-id="e34be-147">[Windows Holographic、バージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1) 以前のビルドでは外部マイクを使用できません。</span><span class="sxs-lookup"><span data-stu-id="e34be-147">External microphones cannot be used in builds prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher.</span></span> 

<span data-ttu-id="e34be-148">ユーザーは、 **[サウンド]** 設定パネルを使用して USB-C 接続外部マイク を 選択できます。</span><span class="sxs-lookup"><span data-stu-id="e34be-148">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="e34be-149">USB-C マイクは、通話や録音などに使用できます。</span><span class="sxs-lookup"><span data-stu-id="e34be-149">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="e34be-150">**設定** アプリを開いて **[システム]**  >  **[サウンド]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e34be-150">Open the **Settings** app and select **System** > **Sound**.</span></span>

![サウンド設定](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="e34be-152">外部マイクを **Remote Assist** で使用するには、[サウンド デバイスの管理] ハイパーリンクをクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e34be-152">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="e34be-153">次に、ドロップダウンを使用して、外部マイクを **[既定]** または **[通信の既定値]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="e34be-153">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="e34be-154">**[既定]** を選択すると、外部マイクはどこででも使用されます。</span><span class="sxs-lookup"><span data-stu-id="e34be-154">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="e34be-155">**[通信の既定値]** を選択すると、外部マイクは Remote Assist や他の通信アプリで使用されますが、HoloLens マイク 配列は他のタスクにも引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="e34be-155">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![サウンド デバイスを管理する](images/usbc-mic-2.png)

<br>

![マイクの既定値を設定する](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="e34be-158">Bluetooth のマイクのサポートについてはどうですか?</span><span class="sxs-lookup"><span data-stu-id="e34be-158">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="e34be-159">残念ながら、Bluetoothマイクは現在も HoloLens 2 でサポートされません。</span><span class="sxs-lookup"><span data-stu-id="e34be-159">Unfortunately, Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="e34be-160">USB-C ハブ</span><span class="sxs-lookup"><span data-stu-id="e34be-160">USB-C Hubs</span></span>

<span data-ttu-id="e34be-161">一部のユーザーは、複数のデバイスを同時に接続する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e34be-161">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="e34be-162">[USB-C マイク](#usb-c-external-microphone-support)を別の接続デバイスと共に使用するユーザーの場合、USB-C ハブは顧客のニーズに合う場合があります。</span><span class="sxs-lookup"><span data-stu-id="e34be-162">For users who would like to use a [USB-C microphone](#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="e34be-163">Microsoft は、これらのデバイスをテストしていないので、特定のブランドをお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="e34be-163">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

<span data-ttu-id="e34be-164">**USB-C ハブと接続されたデバイスの要件:**</span><span class="sxs-lookup"><span data-stu-id="e34be-164">**Requirements for USB-C hub and connected devices:**</span></span>

- <span data-ttu-id="e34be-165">接続されているデバイスでは、ドライバーをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e34be-165">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="e34be-166">接続されているすべてのデバイスの総消費電力は、4.5 ワット未満である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e34be-166">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="e34be-167">Miracast に接続する</span><span class="sxs-lookup"><span data-stu-id="e34be-167">Connect to Miracast</span></span>

<span data-ttu-id="e34be-168">Miracast を使うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e34be-168">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="e34be-169">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e34be-169">Do one of the following:</span></span>  

   - <span data-ttu-id="e34be-170">**[スタート]** メニューを開き、 **[ディスプレイ]** アイコンを選択しましょう。</span><span class="sxs-lookup"><span data-stu-id="e34be-170">Open the **Start** menu, and select the **Display** icon.</span></span>
   - <span data-ttu-id="e34be-171">**[スタート]** メニューを見つめながら、「接続」 と音声で指示します。</span><span class="sxs-lookup"><span data-stu-id="e34be-171">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="e34be-172">表示されたデバイスの一覧で、使用可能なデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="e34be-172">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="e34be-173">ペアリングを完了させてプロジェクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="e34be-173">Complete the pairing to begin projecting.</span></span>
