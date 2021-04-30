---
title: HoloLens を更新する
description: HoloLens のビルド番号を確認する方法、デバイスの更新を使用して最新の状態に保つ方法、Insider プログラムに参加する方法、および更新プログラムをロールバックする方法について説明します。
keywords: 操作方法、更新プログラム、ロールバック、HoloLens、ビルドの確認、ビルド番号
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309513"
---
# <a name="update-hololens"></a><span data-ttu-id="3829a-104">HoloLens を更新する</span><span class="sxs-lookup"><span data-stu-id="3829a-104">Update HoloLens</span></span>

<span data-ttu-id="3829a-105">HoloLens は、他の Windows 10 デバイスと同様に Windows Update を使用します。</span><span class="sxs-lookup"><span data-stu-id="3829a-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="3829a-106">HoloLens では、システムの更新プログラムが電源に接続され、インターネットに接続されると常に、システムの更新プログラムが自動的にダウンロードおよびインストールされます。</span><span class="sxs-lookup"><span data-stu-id="3829a-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="3829a-107">この記事では、次のための HoloLens ツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3829a-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="3829a-108">現在のオペレーティングシステムのバージョンを表示しています (ビルド番号)</span><span class="sxs-lookup"><span data-stu-id="3829a-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="3829a-109">更新プログラムの確認</span><span class="sxs-lookup"><span data-stu-id="3829a-109">checking for updates</span></span>
- <span data-ttu-id="3829a-110">HoloLens の手動更新</span><span class="sxs-lookup"><span data-stu-id="3829a-110">manually updating HoloLens</span></span>
- <span data-ttu-id="3829a-111">古い更新プログラムへのロールバック</span><span class="sxs-lookup"><span data-stu-id="3829a-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="3829a-112">オペレーティングシステムのバージョンを確認する (ビルド番号)</span><span class="sxs-lookup"><span data-stu-id="3829a-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="3829a-113">システムのバージョン番号 (ビルド番号) を確認するには、[設定] アプリを開き、[**システム**] を選択し  >  ます。</span><span class="sxs-lookup"><span data-stu-id="3829a-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="3829a-114">更新プログラムを確認し、手動で更新する</span><span class="sxs-lookup"><span data-stu-id="3829a-114">Check for updates and manually update</span></span>

<span data-ttu-id="3829a-115">更新プログラムは、[設定] でいつでも確認できます。</span><span class="sxs-lookup"><span data-stu-id="3829a-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="3829a-116">利用可能な更新プログラムを確認し、新しい更新プログラムを確認するには:</span><span class="sxs-lookup"><span data-stu-id="3829a-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="3829a-117">**[設定]** アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="3829a-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="3829a-118">[ **Update & Security**  >  **Windows Update** に移動します。</span><span class="sxs-lookup"><span data-stu-id="3829a-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="3829a-119">**[更新プログラムの確認]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3829a-119">Select **Check for updates**.</span></span>

<span data-ttu-id="3829a-120">更新プログラムが利用可能な場合は、新しいバージョンのダウンロードが開始されます。</span><span class="sxs-lookup"><span data-stu-id="3829a-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="3829a-121">ダウンロードが完了したら、[ **今すぐ再起動** ] ボタンを選択してインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="3829a-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="3829a-122">デバイスが40% 未満で、電源に接続されていない場合、再起動しても更新プログラムのインストールは開始されません。</span><span class="sxs-lookup"><span data-stu-id="3829a-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="3829a-123">HoloLens が更新プログラムをインストールしている間、スピン歯車と進行状況インジケーターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3829a-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="3829a-124">この期間中は HoloLens をオフにしないでください。</span><span class="sxs-lookup"><span data-stu-id="3829a-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="3829a-125">インストールが完了すると、自動的に再起動します。</span><span class="sxs-lookup"><span data-stu-id="3829a-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="3829a-126">HoloLens は、一度に1つの更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="3829a-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="3829a-127">HoloLens が最新のバージョンより複数のバージョンである場合は、更新プロセスを複数回実行して完全に最新の状態にすることが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3829a-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version---hololens-2"></a><span data-ttu-id="3829a-128">前のバージョンに戻る-HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="3829a-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="3829a-129">場合によっては、以前のバージョンの HoloLens ソフトウェアに戻ることが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="3829a-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="3829a-130">これを行うには、Advanced Recovery コンパニオンを使用して、HoloLens を以前のバージョンにリセットします。</span><span class="sxs-lookup"><span data-stu-id="3829a-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="3829a-131">以前のバージョンに戻すと、個人用ファイルと設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="3829a-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="3829a-132">以前のバージョンの HoloLens 2 に戻るには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3829a-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="3829a-133">携帯電話や Windows デバイスが PC に接続されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3829a-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="3829a-134">PC で、Microsoft Store から [高度な回復コンパニオン](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="3829a-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="3829a-135">最新の [HoloLens 2 リリース](https://aka.ms/hololens2download)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="3829a-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="3829a-136">これらのダウンロードが完了したら、**ファイルエクスプローラー** の  >  **ダウンロード** を開きます。</span><span class="sxs-lookup"><span data-stu-id="3829a-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="3829a-137">ダウンロードした zip 形式のフォルダーを右クリックし、[**すべて** 抽出] を選択し  >  て解凍します。</span><span class="sxs-lookup"><span data-stu-id="3829a-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="3829a-138">USB-A から USB C ケーブルを使用して HoloLens を PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="3829a-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="3829a-139">(他のケーブルを使用して HoloLens に接続している場合でも、これは最適な方法です)。</span><span class="sxs-lookup"><span data-stu-id="3829a-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="3829a-140">Advanced Recovery コンパニオンは、自動的に HoloLens を検出します。</span><span class="sxs-lookup"><span data-stu-id="3829a-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="3829a-141">[ **Microsoft HoloLens** ] タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="3829a-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="3829a-142">次の画面で、[ **パッケージの手動選択** ] を選択し、手順 4. で解凍したフォルダーに含まれているインストールファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="3829a-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="3829a-143">(拡張子が ffu のファイルを探します。)</span><span class="sxs-lookup"><span data-stu-id="3829a-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="3829a-144">[ **ソフトウェアのインストール**] を選択し、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="3829a-144">Select **Install software**, and follow the instructions.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="3829a-145">以前のバージョン (HoloLens) に戻る (第1世代)</span><span class="sxs-lookup"><span data-stu-id="3829a-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="3829a-146">場合によっては、以前のバージョンの HoloLens ソフトウェアに戻ることが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="3829a-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="3829a-147">これを行うには、Windows デバイス回復ツールを使用して、HoloLens を以前のバージョンにリセットします。</span><span class="sxs-lookup"><span data-stu-id="3829a-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="3829a-148">以前のバージョンに戻すと、個人用ファイルと設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="3829a-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="3829a-149">以前のバージョンの HoloLens 1 に戻るには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3829a-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="3829a-150">携帯電話や Windows デバイスが PC に接続されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3829a-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="3829a-151">PC で、 [Windows デバイス回復ツール (WDRT)](https://support.microsoft.com/help/12379)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="3829a-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="3829a-152">[HoloLens 記念日更新の復旧パッケージ](https://aka.ms/hololensrecovery)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="3829a-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="3829a-153">ダウンロードが完了したら、**エクスプローラー** の [ダウンロード] を開き  >  ます。</span><span class="sxs-lookup"><span data-stu-id="3829a-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="3829a-154">ダウンロードした zip 形式のフォルダーを右クリックし、[**すべて** 抽出] を選択し  >  て解凍します。</span><span class="sxs-lookup"><span data-stu-id="3829a-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="3829a-155">HoloLens を、付属のマイクロ USB ケーブルを使用して PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="3829a-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="3829a-156">(他のケーブルを使用して HoloLens に接続している場合でも、これは最適な方法です)。</span><span class="sxs-lookup"><span data-stu-id="3829a-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="3829a-157">WDRT は、自動的に HoloLens を検出します。</span><span class="sxs-lookup"><span data-stu-id="3829a-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="3829a-158">[ **Microsoft HoloLens** ] タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="3829a-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="3829a-159">次の画面で、[ **パッケージの手動選択** ] を選択し、手順 4. で解凍したフォルダーに格納されているインストールファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="3829a-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="3829a-160">(拡張子が ffu のファイルを探します。)</span><span class="sxs-lookup"><span data-stu-id="3829a-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="3829a-161">[ **ソフトウェアのインストール**] を選択し、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="3829a-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="3829a-162">WDRT が HoloLens を検出しない場合は、PC を再起動してみてください。</span><span class="sxs-lookup"><span data-stu-id="3829a-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="3829a-163">それでもうまくいかない場合は、[ **デバイスが検出されませんでした**] を選択し、[ **Microsoft HoloLens**] を選択して、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="3829a-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="3829a-164">HoloLens の Windows Insider プログラム</span><span class="sxs-lookup"><span data-stu-id="3829a-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="3829a-165">HoloLens の最新の機能を確認したい場合は、</span><span class="sxs-lookup"><span data-stu-id="3829a-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="3829a-166">その場合は、Windows Insider プログラムに参加してください。HoloLens ソフトウェア更新プログラムのプレビュービルドにアクセスしてから、一般公開されるようになります。</span><span class="sxs-lookup"><span data-stu-id="3829a-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="3829a-167">[Microsoft HoloLens の Windows Insider preview を入手](hololens-insider.md)します。</span><span class="sxs-lookup"><span data-stu-id="3829a-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
