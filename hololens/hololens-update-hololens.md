---
title: HoloLens を更新する
description: HoloLens の [ビルド番号]、[更新]、[ロールバック] の更新を確認します。
keywords: 使い方、更新、ロールバック、HoloLens、チェックビルド、ビルド番号
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
ms.openlocfilehash: ee007b00b350ea0f80cda34964d32a57dc6dc0c6
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828592"
---
# <span data-ttu-id="b6ada-104">HoloLens を更新する</span><span class="sxs-lookup"><span data-stu-id="b6ada-104">Update HoloLens</span></span>

<span data-ttu-id="b6ada-105">HoloLens は、他の Windows 10 デバイスと同じように、Windows Update を使用します。</span><span class="sxs-lookup"><span data-stu-id="b6ada-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="b6ada-106">HoloLens は、電源に接続されていて、スタンバイ状態にあるときでもシステムの更新プログラムを自動的にダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="b6ada-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="b6ada-107">この記事では、次のような HoloLens ツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b6ada-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="b6ada-108">現在のオペレーティングシステムバージョン (ビルド番号) を表示する</span><span class="sxs-lookup"><span data-stu-id="b6ada-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="b6ada-109">更新プログラムの確認</span><span class="sxs-lookup"><span data-stu-id="b6ada-109">checking for updates</span></span>
- <span data-ttu-id="b6ada-110">HoloLens を手動で更新する</span><span class="sxs-lookup"><span data-stu-id="b6ada-110">manually updating HoloLens</span></span>
- <span data-ttu-id="b6ada-111">以前の更新プログラムにロールバックする</span><span class="sxs-lookup"><span data-stu-id="b6ada-111">rolling back to an older update</span></span>

## <span data-ttu-id="b6ada-112">オペレーティングシステムのバージョン (ビルド番号) を確認する</span><span class="sxs-lookup"><span data-stu-id="b6ada-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="b6ada-113">システムのバージョン番号 (ビルド番号) を確認するには、設定アプリを開いて [**システム**情報] を選択し  >  **About**ます。</span><span class="sxs-lookup"><span data-stu-id="b6ada-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <span data-ttu-id="b6ada-114">更新プログラムを確認して手動で更新する</span><span class="sxs-lookup"><span data-stu-id="b6ada-114">Check for updates and manually update</span></span>

<span data-ttu-id="b6ada-115">[設定] では、いつでも更新を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b6ada-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="b6ada-116">使用可能な更新プログラムを確認し、新しい更新プログラムを確認するには:</span><span class="sxs-lookup"><span data-stu-id="b6ada-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="b6ada-117">[**設定**] アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="b6ada-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="b6ada-118">**更新 & セキュリティ**  >  の**Windows update**に移動します。</span><span class="sxs-lookup"><span data-stu-id="b6ada-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="b6ada-119">[**更新プログラムの確認**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b6ada-119">Select **Check for updates**.</span></span>

<span data-ttu-id="b6ada-120">更新プログラムが利用可能な場合は、新しいバージョンのダウンロードが開始されます。</span><span class="sxs-lookup"><span data-stu-id="b6ada-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="b6ada-121">ダウンロードが完了したら、[**今すぐ再起動**] ボタンを選択してインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="b6ada-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="b6ada-122">使用しているデバイスが40% 未満で、接続されていない場合は、再起動すると更新プログラムのインストールが開始されません。</span><span class="sxs-lookup"><span data-stu-id="b6ada-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="b6ada-123">HoloLens で更新プログラムをインストールしている間に、回転する歯車と進行状況インジケーターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b6ada-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="b6ada-124">このとき、HoloLens をオフにしないでください。</span><span class="sxs-lookup"><span data-stu-id="b6ada-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="b6ada-125">インストールが完了すると、自動的に再起動します。</span><span class="sxs-lookup"><span data-stu-id="b6ada-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="b6ada-126">HoloLens は一度に1つの更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="b6ada-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="b6ada-127">HoloLens が最新のバージョンより複数のバージョンである場合は、更新プロセスを複数回実行して、完全に最新の状態にすることが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="b6ada-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <span data-ttu-id="b6ada-128">以前のバージョンに戻る-HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="b6ada-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="b6ada-129">場合によっては、HoloLens ソフトウェアの以前のバージョンに戻すこともできます。</span><span class="sxs-lookup"><span data-stu-id="b6ada-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="b6ada-130">これは、高度な回復コンパニオンを使って HoloLens を以前のバージョンにリセットすることで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b6ada-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="b6ada-131">以前のバージョンに戻すと、個人用のファイルと設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="b6ada-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="b6ada-132">以前のバージョンの HoloLens 2 に戻すには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b6ada-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="b6ada-133">PC にスマートフォンや Windows デバイスが接続されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6ada-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="b6ada-134">PC で、Microsoft Store から[高度な回復コンパニオン](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b6ada-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="b6ada-135">[最新の HoloLens 2 リリース](https://aka.ms/hololens2download)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b6ada-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="b6ada-136">これらのダウンロードが完了したら、**[エクスプローラー]** > **[ダウンロード]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="b6ada-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="b6ada-137">ダウンロードした zip 形式のフォルダーを右クリックし、**[すべて展開]** > **[展開]** を選択して展開します。</span><span class="sxs-lookup"><span data-stu-id="b6ada-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="b6ada-138">USB を使って PC に HoloLens を接続します。 usb-C ケーブルを使用します。</span><span class="sxs-lookup"><span data-stu-id="b6ada-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="b6ada-139">(HoloLens の接続に他のケーブルを使用していた場合も、このケーブルが最適です)。</span><span class="sxs-lookup"><span data-stu-id="b6ada-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="b6ada-140">高度な回復コンパニオンでは、HoloLens が自動的に検出されます。</span><span class="sxs-lookup"><span data-stu-id="b6ada-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="b6ada-141">**[Microsoft HoloLens]** タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="b6ada-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="b6ada-142">次の画面で **[手動によるパッケージの選択]** を選択し、手順 4 で展開したフォルダーに含まれているインストール ファイルを選択します </span><span class="sxs-lookup"><span data-stu-id="b6ada-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="b6ada-143">(.ffu という拡張子のファイルを探します)。</span><span class="sxs-lookup"><span data-stu-id="b6ada-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="b6ada-144">**[ソフトウェアのインストール]** を選択し、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b6ada-144">Select **Install software**, and follow the instructions.</span></span>

## <span data-ttu-id="b6ada-145">以前のバージョンの HoloLens に戻る (第1世代)</span><span class="sxs-lookup"><span data-stu-id="b6ada-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="b6ada-146">場合によっては、HoloLens ソフトウェアの以前のバージョンに戻すこともできます。</span><span class="sxs-lookup"><span data-stu-id="b6ada-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="b6ada-147">これには、Windows Device Recovery Tool を使って HoloLens を以前のバージョンにリセットすることで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b6ada-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="b6ada-148">以前のバージョンに戻すと、個人用のファイルと設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="b6ada-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="b6ada-149">HoloLens 1 の以前のバージョンに戻るには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b6ada-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="b6ada-150">PC にスマートフォンや Windows デバイスが接続されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6ada-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="b6ada-151">PC で、[Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b6ada-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="b6ada-152">[HoloLens Anniversary Update 回復パッケージ](https://aka.ms/hololensrecovery)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b6ada-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="b6ada-153">これらのダウンロードが完了したら、**[エクスプローラー]** > **[ダウンロード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b6ada-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="b6ada-154">ダウンロードした zip 形式のフォルダーを右クリックし、**[すべて展開]** > **[展開]** を選択して展開します。</span><span class="sxs-lookup"><span data-stu-id="b6ada-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="b6ada-155">付属していた micro-USB ケーブルを使用して、HoloLens を PC に接続します </span><span class="sxs-lookup"><span data-stu-id="b6ada-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="b6ada-156">(HoloLens の接続に他のケーブルを使用していた場合も、このケーブルが最適です)。</span><span class="sxs-lookup"><span data-stu-id="b6ada-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="b6ada-157">WDRT により、HoloLens が自動的に検出されます。</span><span class="sxs-lookup"><span data-stu-id="b6ada-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="b6ada-158">**[Microsoft HoloLens]** タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="b6ada-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="b6ada-159">次の画面で、**[手動によるパッケージの選択]** を選択し、手順 4 で展開したフォルダーに含まれていたインストール ファイルを選択します </span><span class="sxs-lookup"><span data-stu-id="b6ada-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="b6ada-160">(.ffu という拡張子のファイルを探します)。</span><span class="sxs-lookup"><span data-stu-id="b6ada-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="b6ada-161">**[ソフトウェアのインストール]** を選択し、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b6ada-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="b6ada-162">WDRT で HoloLens が検出されない場合は、PC を再起動してみてください。</span><span class="sxs-lookup"><span data-stu-id="b6ada-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="b6ada-163">それでも問題が解決しない場合は、**[デバイスが検出されませんでした]** を選択し、**[Microsoft HoloLens]** を選択して、表示される指示に従って操作します。</span><span class="sxs-lookup"><span data-stu-id="b6ada-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="b6ada-164">HoloLens 上の Windows Insider プログラム</span><span class="sxs-lookup"><span data-stu-id="b6ada-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="b6ada-165">HoloLens の最新機能を確認するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="b6ada-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="b6ada-166">その場合は、Windows Insider Program に参加してください。HoloLens ソフトウェア更新プログラムのプレビュービルドにアクセスできるのは、一般公開されている場合です。</span><span class="sxs-lookup"><span data-stu-id="b6ada-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="b6ada-167">[Microsoft HoloLens 用 Windows Insider preview を入手](hololens-insider.md)します。</span><span class="sxs-lookup"><span data-stu-id="b6ada-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
