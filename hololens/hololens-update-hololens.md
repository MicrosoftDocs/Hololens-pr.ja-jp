---
title: 更新HoloLens 2
description: HoloLens のビルド番号を確認し、デバイスの更新プログラムを最新の状態に保ち、Insiders Program に参加して、更新プログラムをロールバックする方法について学習します。
keywords: 方法、更新、ロールバック、HoloLens、ビルドの確認、ビルド番号
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
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924113"
---
# <a name="update-hololens-2"></a><span data-ttu-id="8a874-104">更新HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="8a874-104">Update HoloLens 2</span></span>

<span data-ttu-id="8a874-105">HoloLens では、他Windows Updateデバイスと同様に、Windows 10が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a874-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="8a874-106">HoloLens は、電源に接続され、インターネットに接続されている場合でも、スタンバイ状態の場合でも、システム更新プログラムを自動的にダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="8a874-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="8a874-107">この記事では、以下を行う HoloLens ツールについて詳しい情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="8a874-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="8a874-108">現在のオペレーティング システムのバージョン (ビルド番号) の表示</span><span class="sxs-lookup"><span data-stu-id="8a874-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="8a874-109">更新プログラムの確認</span><span class="sxs-lookup"><span data-stu-id="8a874-109">checking for updates</span></span>
- <span data-ttu-id="8a874-110">HoloLens を手動で更新する</span><span class="sxs-lookup"><span data-stu-id="8a874-110">manually updating HoloLens</span></span>
- <span data-ttu-id="8a874-111">古い更新プログラムへのロールバック</span><span class="sxs-lookup"><span data-stu-id="8a874-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="8a874-112">オペレーティング システムのバージョン (ビルド番号) を確認する</span><span class="sxs-lookup"><span data-stu-id="8a874-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="8a874-113">システム バージョン番号 (ビルド番号) を確認するには、設定アプリを開き、[ システムバージョン情報 ]**を選択**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="8a874-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="8a874-114">更新プログラムを確認し、手動で更新する</span><span class="sxs-lookup"><span data-stu-id="8a874-114">Check for updates and manually update</span></span>

<span data-ttu-id="8a874-115">設定では、いつでも更新プログラムを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8a874-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="8a874-116">利用可能な更新プログラムを確認し、新しい更新プログラムを確認するには:</span><span class="sxs-lookup"><span data-stu-id="8a874-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="8a874-117">**[設定]** アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="8a874-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="8a874-118">[Update **& Security Windows Update]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="8a874-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="8a874-119">**[更新プログラムの確認]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a874-119">Select **Check for updates**.</span></span>

<span data-ttu-id="8a874-120">更新プログラムが利用可能な場合は、新しいバージョンのダウンロードが開始されます。</span><span class="sxs-lookup"><span data-stu-id="8a874-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="8a874-121">ダウンロードが完了したら、[今すぐ再起動 **] ボタンを** 選択してインストールをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="8a874-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="8a874-122">デバイスが 40% を下回り、接続されていない場合、再起動によって更新プログラムのインストールは開始されません。</span><span class="sxs-lookup"><span data-stu-id="8a874-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="8a874-123">HoloLens が更新プログラムをインストールしている間に、回転する歯車と進行状況インジケーターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a874-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="8a874-124">この期間中は HoloLens をオフにしない。</span><span class="sxs-lookup"><span data-stu-id="8a874-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="8a874-125">インストールが完了すると、自動的に再起動されます。</span><span class="sxs-lookup"><span data-stu-id="8a874-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="8a874-126">HoloLens では、一度に 1 つの更新プログラムが適用されます。</span><span class="sxs-lookup"><span data-stu-id="8a874-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="8a874-127">HoloLens が最新バージョンより複数遅れている場合は、更新プロセスを複数回実行して、完全に最新の情報に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a874-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version"></a><span data-ttu-id="8a874-128">以前のバージョンに戻る</span><span class="sxs-lookup"><span data-stu-id="8a874-128">Go back to a previous version</span></span>

<span data-ttu-id="8a874-129">場合によっては、以前のバージョンの HoloLens ソフトウェアに戻したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="8a874-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="8a874-130">推奨される手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8a874-130">The recommended steps are:</span></span>

1. <span data-ttu-id="8a874-131">サポートに問い合わせ、問題を解決できる場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="8a874-131">Contact Support to see if they can fix your issue.</span></span>
    1. <span data-ttu-id="8a874-132">省略可能 **または完全\*\*\*\*な** テレメトリが有効になっているのを確認します。これにより、バグのアクションが容易になり、エンジニアが診断しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="8a874-132">Ensure that **Optional** or **Full** telemetry is enabled -  this makes your bug more actionable and easier for engineers to diagnose.</span></span>
    1. <span data-ttu-id="8a874-133">[ファイル フィードバックは](hololens-feedback.md) 、可能な限り説明的です。</span><span class="sxs-lookup"><span data-stu-id="8a874-133">[File Feedback](hololens-feedback.md) being as descriptive as possible.</span></span> <span data-ttu-id="8a874-134">タイトルをメモするか、共有機能を使用して、バグをサポートと共有できます。</span><span class="sxs-lookup"><span data-stu-id="8a874-134">Take note of the title or use the share feature so you can share your bug with Support.</span></span>
    1. <span data-ttu-id="8a874-135">サポートにお問 [い合わせください](https://aka.ms/hlsupport)。</span><span class="sxs-lookup"><span data-stu-id="8a874-135">Contact [Support](https://aka.ms/hlsupport).</span></span> <span data-ttu-id="8a874-136">問題が以前のバージョンに戻って解決する必要がある場合は、デバイスをフラッシュする FFU を提供できます。</span><span class="sxs-lookup"><span data-stu-id="8a874-136">If your issue is one that needs to be solved by returning to a previous version, they can supply you the FFU to flash your device.</span></span>

1. <span data-ttu-id="8a874-137">それでも問題が生じない場合は、Advanced Recovery Companion を使用してHoloLens 2 [をリセットまたは再フラッシュします](hololens-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="8a874-137">If that does not work, then [reset or reflash your HoloLens 2 with the Advanced Recovery Companion](hololens-recovery.md).</span></span>
    1. <span data-ttu-id="8a874-138">お使いの PC で、 [[Advanced Recovery Companion]](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) を [Microsoft Store] からダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8a874-138">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
    1. <span data-ttu-id="8a874-139">PC にスマートフォンや Windows デバイスが接続されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8a874-139">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
    1. <span data-ttu-id="8a874-140">フラッシュするバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="8a874-140">Choose which version you want to flash to:</span></span>
        1. <span data-ttu-id="8a874-141">最新のリリース [をダウンロードHoloLens 2できます](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="8a874-141">You can download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
        1. <span data-ttu-id="8a874-142">ARC がホストする既定のビルドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a874-142">You can use the default build that ARC hosts.</span></span> <span data-ttu-id="8a874-143">(このオプションを選択した場合は、次の手順をスキップします)。</span><span class="sxs-lookup"><span data-stu-id="8a874-143">(If you choose this option skip the next step.)</span></span>
        1. <span data-ttu-id="8a874-144">提供されているビルド サポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a874-144">You can use a build Support provided you with.</span></span>
    1. <span data-ttu-id="8a874-145">これらのダウンロードが完了したら、[ダウンロード]**をエクスプローラー**  >  **開きます**。</span><span class="sxs-lookup"><span data-stu-id="8a874-145">When you have finished these downloads, open **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="8a874-146">ダウンロードした zip 形式のフォルダーを右クリックし、[すべての抽出] を選択して  >  解凍します。</span><span class="sxs-lookup"><span data-stu-id="8a874-146">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
    1. <span data-ttu-id="8a874-147">USB-A から USB-C ケーブルを使用して HoloLens を PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="8a874-147">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="8a874-148">(他のケーブルを使用して HoloLens を接続している場合でも、これは最適です)。</span><span class="sxs-lookup"><span data-stu-id="8a874-148">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
    1. <span data-ttu-id="8a874-149">Advanced Recovery Companion によって HoloLens が自動的に検出されます。</span><span class="sxs-lookup"><span data-stu-id="8a874-149">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="8a874-150">[新 **しい** Microsoft HoloLens選択します。</span><span class="sxs-lookup"><span data-stu-id="8a874-150">Select the **Microsoft HoloLens** tile.</span></span>
    1. <span data-ttu-id="8a874-151">次の画面で、[手動 **パッケージの** 選択] を選択し、手順 4. で展開したフォルダーに含まれているインストール ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="8a874-151">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="8a874-152">(拡張子が .ffu のファイルを探します)。</span><span class="sxs-lookup"><span data-stu-id="8a874-152">(Look for a file with the .ffu extension.)</span></span>
    1. <span data-ttu-id="8a874-153">[ **ソフトウェアのインストール] を** 選択し、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="8a874-153">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="8a874-154">以前のバージョンに戻って、個人用ファイルと設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="8a874-154">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="8a874-155">また、現在インストールされているリリースを使用する場合は、更新プログラム を手動で [一時停止することもできます](hololens-updates.md#pause-updates-via-device)。</span><span class="sxs-lookup"><span data-stu-id="8a874-155">Additionally, if you would like to stay on your currently installed release, you can also manually [pause updates](hololens-updates.md#pause-updates-via-device).</span></span> <span data-ttu-id="8a874-156">これにより、エンジニアリング チームは問題を解決する時間が得されます。</span><span class="sxs-lookup"><span data-stu-id="8a874-156">This will give the Engineering Team time to fix the issue.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="8a874-157">Windows Insider Program HoloLens でのインストール</span><span class="sxs-lookup"><span data-stu-id="8a874-157">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="8a874-158">HoloLens の最新機能を確認したいですか?</span><span class="sxs-lookup"><span data-stu-id="8a874-158">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="8a874-159">その場合は、次のWindows Insider Program。HoloLens ソフトウェア更新プログラムが一般公開される前に、プレビュー ビルドにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8a874-159">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="8a874-160">[のWindows Insiderプレビューを取得Microsoft HoloLens。](hololens-insider.md)</span><span class="sxs-lookup"><span data-stu-id="8a874-160">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
