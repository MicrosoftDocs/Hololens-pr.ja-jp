---
title: HoloLens 2 バッテリーと充電
description: HoloLens を充電し、外部のバッテリ パックを使用する方法。
ms.assetid: E0AB903E-454E-46F6-AB25-4DFA0A475B0C
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 05/14/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: acbc3e52240f420d384fa372684966d7220d53c6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923586"
---
# <a name="hololens-2-battery-and-charging"></a><span data-ttu-id="33f53-103">HoloLens 2 バッテリーと充電</span><span class="sxs-lookup"><span data-stu-id="33f53-103">HoloLens 2 Battery and Charging</span></span>

<span data-ttu-id="33f53-104">このページでは、HoloLens 2 の充電と外部バッテリ パックの使用に関する詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="33f53-104">This page offers details about charging HoloLens 2 and using external battery packs.</span></span>

## <a name="charging-the-device"></a><span data-ttu-id="33f53-105">デバイスの充電</span><span class="sxs-lookup"><span data-stu-id="33f53-105">Charging the device</span></span>

<span data-ttu-id="33f53-106">HoloLens 2 に付属している[充電器と USB タイプ C ケーブル](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1)を使用します。これは、デバイスの充電に最適な方法です。</span><span class="sxs-lookup"><span data-stu-id="33f53-106">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="33f53-107">HoloLens 2 に含まれる充電器には、2A で最大 9V (18W) が用意されています。</span><span class="sxs-lookup"><span data-stu-id="33f53-107">The charger included with HoloLens 2 provides up to 9V @ 2A (18W).</span></span> <span data-ttu-id="33f53-108">提供される壁の充電器を使用すると、HoloLens 2 デバイスは、デバイスがスタンバイ状態のときに 65 分未満でバッテリーを完全に充電できます。</span><span class="sxs-lookup"><span data-stu-id="33f53-108">Along with the supplied wall charger, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="33f53-109">これらのアクセサリが使用できない場合は、使用可能な充電器が少なくとも 15W の電力に対応していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="33f53-109">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="33f53-110">可能であれば、PC を使用してデバイスを USB 経由で充電することは避けてください。遅いです。</span><span class="sxs-lookup"><span data-stu-id="33f53-110">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

## <a name="checking-the-battery-charge-level"></a><span data-ttu-id="33f53-111">バッテリの充電レベルを確認しています</span><span class="sxs-lookup"><span data-stu-id="33f53-111">Checking the battery charge level</span></span>
<span data-ttu-id="33f53-112">デバイスが正常に起動し、動作している場合は、次の 3 つの方法でバッテリの充電レベルを確認できます。</span><span class="sxs-lookup"><span data-stu-id="33f53-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="33f53-113">HoloLens デバイス UI のメイン メニューから。</span><span class="sxs-lookup"><span data-stu-id="33f53-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="33f53-114">電源ボタンの近くにある LED を確認します (40% が充電されている場合、少なくとも 2 つの点灯した LED が見えるはずです)。</span><span class="sxs-lookup"><span data-stu-id="33f53-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="33f53-115">デバイスの充電中は、バッテリー インジケーターが点灯し、現在の充電レベルを示します。</span><span class="sxs-lookup"><span data-stu-id="33f53-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="33f53-116">最後のライトはゆっくりと点滅し、充電中であることを示します。</span><span class="sxs-lookup"><span data-stu-id="33f53-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="33f53-117">HoloLens の電源が入っているときは、バッテリー インジケーターにバッテリー レベルが 5 段階で表示されます。</span><span class="sxs-lookup"><span data-stu-id="33f53-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="33f53-118">5 個のライトのうち 1 個しか点灯していない場合は、バッテリー レベルが 20 パーセントを下回っています。</span><span class="sxs-lookup"><span data-stu-id="33f53-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="33f53-119">バッテリー レベルが極端に低い場合にデバイスの電源を入れようとすると、1 個のライトが短く点滅してから消えます。</span><span class="sxs-lookup"><span data-stu-id="33f53-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="33f53-120">ホスト PC で、**エクスプローラー** を開き、 **[この PC]** の下にある HoloLens 2 デバイスを探します。</span><span class="sxs-lookup"><span data-stu-id="33f53-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="33f53-121">そのデバイスを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33f53-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="33f53-122">ダイアログ ボックスにバッテリの充電レベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="33f53-122">A dialog box will show the battery charge level.</span></span>

   ![HoloLens 2 のプロパティ画面にバッテリの残量レベルが表示されます](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a><span data-ttu-id="33f53-124">代替充電の仕様</span><span class="sxs-lookup"><span data-stu-id="33f53-124">Alternative charging specifications</span></span>

<span data-ttu-id="33f53-125">HoloLens 2 は、 [USB 電力配信](https://www.usb.org/usb-charger-pd)の電源によって最大 27 ワットまで充電されます。</span><span class="sxs-lookup"><span data-stu-id="33f53-125">HoloLens 2 can be charged by [USB Power Delivery](https://www.usb.org/usb-charger-pd) sources up to 27 Watts.</span></span> <span data-ttu-id="33f53-126">電源が少なくとも 10 ワットを提供できる場合、HoloLens の動作時間を延長できます (一部のワークロードでは無期限)。</span><span class="sxs-lookup"><span data-stu-id="33f53-126">If the source is able supply at least 10 Watts, HoloLens operating time can be extended (potentially indefinitely for some workloads).</span></span> 

> [!NOTE]
> <span data-ttu-id="33f53-127">USB-A - USB C の充電ケーブルを使用すると、充電は 7.5 ワットに制限されます。</span><span class="sxs-lookup"><span data-stu-id="33f53-127">Using a USB-A to USB-C charging cable will limit the charge to 7.5 Watts.</span></span> <span data-ttu-id="33f53-128">操作時間は長くなりますが、USB-C - C を使用した場合ほどではありません。</span><span class="sxs-lookup"><span data-stu-id="33f53-128">Operating time will still be extended, but not as long as using USB-C to C.</span></span>

<span data-ttu-id="33f53-129">HoloLens がスタンバイ モードの場合、内部バッテリの最大充電率に達しても 18 ワットで十分です。</span><span class="sxs-lookup"><span data-stu-id="33f53-129">When HoloLens is in standby mode, 18 Watts is sufficient to reach the maximum charge rate for the internal battery.</span></span> <span data-ttu-id="33f53-130">HoloLens が使用されている場合は、HoloLens の優先順位は充電よりも操作の方が高いため、充電率は低くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="33f53-130">When HoloLens is in use, the charge rate may be reduced since HoloLens prioritizes operating over charging.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33f53-131">HoloLens 2 は、最低でも 5V/1.5 A で充電することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="33f53-131">It's recommended that HoloLens 2 be charged at 5V/1.5A minimum.</span></span> <span data-ttu-id="33f53-132">少なくとも 5V/1.5 A を供給できない充電器は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="33f53-132">Chargers that can't supply at least 5V/1.5A should not be used.</span></span> 

### <a name="external-battery-packs"></a><span data-ttu-id="33f53-133">外部のバッテリパック</span><span class="sxs-lookup"><span data-stu-id="33f53-133">External Battery Packs</span></span>

<span data-ttu-id="33f53-134">上記の仕様を満たすバッテリパックは、HoloLens 2 で使用できます。</span><span class="sxs-lookup"><span data-stu-id="33f53-134">Battery packs that meet the specifications above can be used with HoloLens 2.</span></span> <span data-ttu-id="33f53-135">ただし、一部の USB C バッテリ パックは再充電し、同じ USB C ポートを使用して電源を供給するのでご注意ください。</span><span class="sxs-lookup"><span data-stu-id="33f53-135">However, note that some USB-C battery packs recharge and provide power through the same USB-C port.</span></span> <span data-ttu-id="33f53-136">これらのバッテリパックは [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) を実装して、外部バッテリが HoloLens から充電されるのでなく HoloLens を確実に充電するので重要です。</span><span class="sxs-lookup"><span data-stu-id="33f53-136">It's important that these battery packs implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) to ensure they charge HoloLens rather than charge from it.</span></span> 

### <a name="managing-heat"></a><span data-ttu-id="33f53-137">ヒートの管理</span><span class="sxs-lookup"><span data-stu-id="33f53-137">Managing Heat</span></span>

<span data-ttu-id="33f53-138">すべてのデバイスと同様に、HoloLens を充電すると熱が発生します。</span><span class="sxs-lookup"><span data-stu-id="33f53-138">As with any device, charging HoloLens generates heat.</span></span> <span data-ttu-id="33f53-139">充電速度が速いほど、熱も多く生まれます。</span><span class="sxs-lookup"><span data-stu-id="33f53-139">The more rapid the charge, the more heat is generated.</span></span> <span data-ttu-id="33f53-140">また、バッテリ残量が少ないときに充電を開始すると、バッテリがほとんどいっぱいのときよりも多くの熱が発生します。</span><span class="sxs-lookup"><span data-stu-id="33f53-140">Also, starting a charge at a lower battery level will generate more heat than starting a charge when the battery is mostly full.</span></span> <span data-ttu-id="33f53-141">熱い環境で長時間にわたって HoloLens を運用する必要がある場合は、次の手法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="33f53-141">Customers who need to operate HoloLens for extended periods of time in hot environments can use the following techniques:</span></span>

- <span data-ttu-id="33f53-142">内部バッテリが完全に充電されている場合でも、外部電源に HoloLens 2 を接続するのは問題ありません。</span><span class="sxs-lookup"><span data-stu-id="33f53-142">It's OK to connect HoloLens 2 to an external power source even when the internal battery is fully charged.</span></span>
- <span data-ttu-id="33f53-143">外部バッテリが使い果たされると、HoloLens は引き続き内部バッテリで動作します。</span><span class="sxs-lookup"><span data-stu-id="33f53-143">When an external battery is depleted, HoloLens will continue operating on its internal battery.</span></span>    
- <span data-ttu-id="33f53-144">上記の手順を実行しても熱が問題になる場合は、充電を 1.5 A に制限する充電器またはバッテリパックを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="33f53-144">If heat is still an issue after following steps above, consider using a charger or battery pack that limits charging to 1.5A.</span></span> <span data-ttu-id="33f53-145">このオプションを使用しても、内部バッテリが徐々に消費されるため、操作時間は長くありません。</span><span class="sxs-lookup"><span data-stu-id="33f53-145">Note that this option won't provide as much operating time since the internal battery will still slowly deplete.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="33f53-146">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="33f53-146">Troubleshooting</span></span>


### <a name="hololens-charges-external-battery"></a><span data-ttu-id="33f53-147">HoloLens が外部バッテリで充電する</span><span class="sxs-lookup"><span data-stu-id="33f53-147">HoloLens Charges External Battery</span></span>
<span data-ttu-id="33f53-148">HoloLens 2 が外部バッテリに充電されるのではなく外部バッテリを充電する場合、そのバッテリは [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) を実装していないということです。</span><span class="sxs-lookup"><span data-stu-id="33f53-148">If HoloLens 2 charges an external battery rather than being charged by it, this indicates that the battery doesn't implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span></span> <span data-ttu-id="33f53-149">この問題を解決するには、新しいバッテリパックに切り替えることをお勧めしますが、別の方法として、USB-A から USB C ケーブルへ切り替えてみることもできます。</span><span class="sxs-lookup"><span data-stu-id="33f53-149">Switching to a newer battery pack is the recommended way to solve this issue, but alternatively you can try switching to a USB-A to USB-C cable.</span></span> <span data-ttu-id="33f53-150">これにより、充電速度は7.5 ワットに制限されるのでご注意ください。</span><span class="sxs-lookup"><span data-stu-id="33f53-150">Keep in mind this will limit the charging rate to 7.5 watts.</span></span>
