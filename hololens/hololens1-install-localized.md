---
title: HoloLens のローカライズされたバージョンをインストールする
description: HoloLens の中国語または日本語版をインストールする方法について説明します。
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: high
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 9ccee2e11650926a5570967f1de5f6b341a17ae6
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829556"
---
# <span data-ttu-id="b4f65-103">HoloLens (第 1 世代) のローカライズされたバージョンをインストールする</span><span class="sxs-lookup"><span data-stu-id="b4f65-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="b4f65-104">HoloLens の中国語版または日本語版に切り替えるには、Windows Device Recovery Tool (WDRT) を使用して、その言語のビルドを PC にダウンロードしてから HoloLens にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4f65-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4f65-105">WDRT を使用して HoloLens の中国語版または日本語版のビルドをインストールすると、個人用ファイルや設定などの既存データが HoloLens から削除されます。</span><span class="sxs-lookup"><span data-stu-id="b4f65-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="b4f65-106">PC に [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) をダウンロードし、インストールします。</span><span class="sxs-lookup"><span data-stu-id="b4f65-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="b4f65-107">必要な言語 ([簡体字中国語](https://aka.ms/hololensdownload-ch)または[日本語](https://aka.ms/hololensdownload-jp)) のパッケージを PC にダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b4f65-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="b4f65-108">ダウンロードが完了したら、**[エクスプローラー]** > **[ダウンロード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4f65-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="b4f65-109">ダウンロードした zip 形式のフォルダーを右クリックし、**[すべて展開]** > **[展開]** を選択して展開します。</span><span class="sxs-lookup"><span data-stu-id="b4f65-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="b4f65-110">付属していた micro-USB ケーブルを使用して、HoloLens を PC に接続します </span><span class="sxs-lookup"><span data-stu-id="b4f65-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="b4f65-111">(HoloLens の接続に他のケーブルを使用していた場合も、このケーブルが最適です)。</span><span class="sxs-lookup"><span data-stu-id="b4f65-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="b4f65-112">ツールによって HoloLens が自動的に検出されたら、Microsoft HoloLens タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="b4f65-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="b4f65-113">次の画面で **[手動によるパッケージの選択]** を選択し、手順 4. で展開したフォルダーにあるインストール ファイルを選択します </span><span class="sxs-lookup"><span data-stu-id="b4f65-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="b4f65-114">(".ffu" という拡張子のファイルを探します)。</span><span class="sxs-lookup"><span data-stu-id="b4f65-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="b4f65-115"> *\*[ソフトウェアのインストール]** を選択し、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b4f65-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="b4f65-116">ビルドがインストールされると、HoloLens セットアップが自動的に開始します。</span><span class="sxs-lookup"><span data-stu-id="b4f65-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="b4f65-117">デバイスに配置し、セットアップの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b4f65-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="b4f65-118">セットアップが完了したら、**[設定]** > **[更新とセキュリティ]** > **[Windows Insider Program]** に移動し、最新のプレビュー ビルドを受け取るよう構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b4f65-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="b4f65-119">英語版のプレビュー ビルドと同様、Windows Insider Program では、最新のプレビュー ビルドを使用して HoloLens の中国語版および日本語版が最新の状態に維持されます。</span><span class="sxs-lookup"><span data-stu-id="b4f65-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="b4f65-120">設定アプリを使用して、英語、日本語、中国語の間でシステム言語を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="b4f65-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="b4f65-121">デバイスのシステム言語を変更するためにサポートされている唯一の方法は、新しいビルドをフラッシュすることです。</span><span class="sxs-lookup"><span data-stu-id="b4f65-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="b4f65-122">Pinyin のスクリーン キーボードを使用して簡体字中国語または日本語のテキストを入力することはできますが、現時点では、Bluetooth ハードウェア キーボードでの簡体字中国語または日本語テキストの入力はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b4f65-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="b4f65-123">ただし、中国語版または日本語版の HoloLens では、引き続き Bluetooth キーボードを使用して英語で入力できます (ハードウェア キーボードを英語入力に切り替えるには、~ キーを押します)。</span><span class="sxs-lookup"><span data-stu-id="b4f65-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
