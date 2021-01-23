---
title: HoloLens を更新する
description: HoloLens のビルド番号を確認し、デバイスの更新プログラムを最新の状態に保ち、Insider プログラムに参加し、更新プログラムをロールバックする方法について学習します。
keywords: 使い方, 更新, ロールバック, HoloLens, ビルドの確認, ビルド番号
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283938"
---
# <span data-ttu-id="77b86-104">HoloLens を更新する</span><span class="sxs-lookup"><span data-stu-id="77b86-104">Update HoloLens</span></span>

<span data-ttu-id="77b86-105">HoloLens は、他の Windows 10 デバイスと同じように、Windows Update を使用します。</span><span class="sxs-lookup"><span data-stu-id="77b86-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="77b86-106">HoloLens は、スタンバイ状態の場合でも、電源に接続され、インターネットに接続されると、システム更新プログラムを自動的にダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="77b86-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="77b86-107">この記事では、次の HoloLens ツールについて詳しい情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="77b86-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="77b86-108">現在のオペレーティング システムのバージョン (ビルド番号) の表示</span><span class="sxs-lookup"><span data-stu-id="77b86-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="77b86-109">更新プログラムの確認</span><span class="sxs-lookup"><span data-stu-id="77b86-109">checking for updates</span></span>
- <span data-ttu-id="77b86-110">HoloLens を手動で更新する</span><span class="sxs-lookup"><span data-stu-id="77b86-110">manually updating HoloLens</span></span>
- <span data-ttu-id="77b86-111">以前の更新プログラムへのロールバック</span><span class="sxs-lookup"><span data-stu-id="77b86-111">rolling back to an older update</span></span>

## <span data-ttu-id="77b86-112">オペレーティング システムのバージョン (ビルド番号) を確認する</span><span class="sxs-lookup"><span data-stu-id="77b86-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="77b86-113">[設定] アプリを開き、[システムバージョン情報] を選択すると、システム バージョン番号 (ビルド番号)**を確認**  >  **できます**。</span><span class="sxs-lookup"><span data-stu-id="77b86-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <span data-ttu-id="77b86-114">更新プログラムを確認して手動で更新する</span><span class="sxs-lookup"><span data-stu-id="77b86-114">Check for updates and manually update</span></span>

<span data-ttu-id="77b86-115">設定では、更新プログラムをいつでも確認できます。</span><span class="sxs-lookup"><span data-stu-id="77b86-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="77b86-116">利用可能な更新プログラムを確認し、新しい更新プログラムを確認するには:</span><span class="sxs-lookup"><span data-stu-id="77b86-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="77b86-117">設定アプリ **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="77b86-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="77b86-118">Windows Update**の更新&**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="77b86-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="77b86-119">[更新 **プログラムの確認] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="77b86-119">Select **Check for updates**.</span></span>

<span data-ttu-id="77b86-120">更新プログラムが利用可能な場合は、新しいバージョンのダウンロードが開始されます。</span><span class="sxs-lookup"><span data-stu-id="77b86-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="77b86-121">ダウンロードが完了したら、[今すぐ再起動] **ボタンを選択** してインストールをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="77b86-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="77b86-122">デバイスが 40% 未満で接続されていない場合、再起動によって更新プログラムのインストールが開始されません。</span><span class="sxs-lookup"><span data-stu-id="77b86-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="77b86-123">HoloLens が更新プログラムをインストールしている間は、回転するギアと進行状況インジケーターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="77b86-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="77b86-124">この間は HoloLens をオフにしない。</span><span class="sxs-lookup"><span data-stu-id="77b86-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="77b86-125">インストールが完了すると、自動的に再起動されます。</span><span class="sxs-lookup"><span data-stu-id="77b86-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="77b86-126">HoloLens は、一度に 1 つの更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="77b86-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="77b86-127">HoloLens が最新のバージョンより複数ある場合は、更新プロセスを複数回実行して、完全に最新の情報を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77b86-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <span data-ttu-id="77b86-128">以前のバージョンに戻る - HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="77b86-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="77b86-129">場合によっては、HoloLens ソフトウェアの以前のバージョンに戻すこともできます。</span><span class="sxs-lookup"><span data-stu-id="77b86-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="77b86-130">これは、高度な回復コンパニオンを使って HoloLens を以前のバージョンにリセットすることで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="77b86-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="77b86-131">以前のバージョンに戻すと、個人用のファイルと設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="77b86-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="77b86-132">以前のバージョンの HoloLens 2 に戻すには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="77b86-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="77b86-133">PC にスマートフォンや Windows デバイスが接続されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="77b86-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="77b86-134">PC で、Microsoft Store から[高度な回復コンパニオン](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="77b86-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="77b86-135">[最新の HoloLens 2 リリース](https://aka.ms/hololens2download)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="77b86-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="77b86-136">これらのダウンロードが完了したら、**[エクスプローラー]** > **[ダウンロード]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="77b86-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="77b86-137">ダウンロードした zip 形式のフォルダーを右クリックし、**[すべて展開]** > **[展開]** を選択して展開します。</span><span class="sxs-lookup"><span data-stu-id="77b86-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="77b86-138">USB-A から USB-C ケーブルを使って HoloLens を PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="77b86-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="77b86-139">(HoloLens の接続に他のケーブルを使用していた場合も、このケーブルが最適です)。</span><span class="sxs-lookup"><span data-stu-id="77b86-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="77b86-140">高度な回復コンパニオンでは、HoloLens が自動的に検出されます。</span><span class="sxs-lookup"><span data-stu-id="77b86-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="77b86-141">**[Microsoft HoloLens]** タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="77b86-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="77b86-142">次の画面で **[手動によるパッケージの選択]** を選択し、手順 4 で展開したフォルダーに含まれているインストール ファイルを選択します </span><span class="sxs-lookup"><span data-stu-id="77b86-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="77b86-143">(.ffu という拡張子のファイルを探します)。</span><span class="sxs-lookup"><span data-stu-id="77b86-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="77b86-144">**[ソフトウェアのインストール]** を選択し、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="77b86-144">Select **Install software**, and follow the instructions.</span></span>

## <span data-ttu-id="77b86-145">以前のバージョンに戻る - HoloLens (第 1 世代)</span><span class="sxs-lookup"><span data-stu-id="77b86-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="77b86-146">場合によっては、HoloLens ソフトウェアの以前のバージョンに戻すこともできます。</span><span class="sxs-lookup"><span data-stu-id="77b86-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="77b86-147">これには、Windows Device Recovery Tool を使って HoloLens を以前のバージョンにリセットすることで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="77b86-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="77b86-148">以前のバージョンに戻すと、個人用のファイルと設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="77b86-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="77b86-149">以前のバージョンの HoloLens 1 に戻る場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="77b86-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="77b86-150">PC にスマートフォンや Windows デバイスが接続されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="77b86-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="77b86-151">PC で、[Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="77b86-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="77b86-152">[HoloLens Anniversary Update 回復パッケージ](https://aka.ms/hololensrecovery)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="77b86-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="77b86-153">これらのダウンロードが完了したら、**[エクスプローラー]** > **[ダウンロード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77b86-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="77b86-154">ダウンロードした zip 形式のフォルダーを右クリックし、**[すべて展開]** > **[展開]** を選択して展開します。</span><span class="sxs-lookup"><span data-stu-id="77b86-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="77b86-155">付属していた micro-USB ケーブルを使用して、HoloLens を PC に接続します </span><span class="sxs-lookup"><span data-stu-id="77b86-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="77b86-156">(HoloLens の接続に他のケーブルを使用していた場合も、このケーブルが最適です)。</span><span class="sxs-lookup"><span data-stu-id="77b86-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="77b86-157">WDRT により、HoloLens が自動的に検出されます。</span><span class="sxs-lookup"><span data-stu-id="77b86-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="77b86-158">**[Microsoft HoloLens]** タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="77b86-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="77b86-159">次の画面で、**[手動によるパッケージの選択]** を選択し、手順 4 で展開したフォルダーに含まれていたインストール ファイルを選択します </span><span class="sxs-lookup"><span data-stu-id="77b86-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="77b86-160">(.ffu という拡張子のファイルを探します)。</span><span class="sxs-lookup"><span data-stu-id="77b86-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="77b86-161">**[ソフトウェアのインストール]** を選択し、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="77b86-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="77b86-162">WDRT で HoloLens が検出されない場合は、PC を再起動してみてください。</span><span class="sxs-lookup"><span data-stu-id="77b86-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="77b86-163">それでも問題が解決しない場合は、**[デバイスが検出されませんでした]** を選択し、**[Microsoft HoloLens]** を選択して、表示される指示に従って操作します。</span><span class="sxs-lookup"><span data-stu-id="77b86-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="77b86-164">HoloLens の Windows Insider Program</span><span class="sxs-lookup"><span data-stu-id="77b86-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="77b86-165">HoloLens の最新機能を確認する場合</span><span class="sxs-lookup"><span data-stu-id="77b86-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="77b86-166">その場合は、Windows Insider Program に参加します。HoloLens ソフトウェア更新プログラムを一般公開する前に、プレビュー ビルドにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="77b86-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="77b86-167">[Microsoft HoloLens の Windows Insider プレビューを取得します](hololens-insider.md)。</span><span class="sxs-lookup"><span data-stu-id="77b86-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
