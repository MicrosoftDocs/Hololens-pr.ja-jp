---
title: HoloLens のローカライズ版をインストールする
description: HoloLens のローカライズ版 (第1世代) をインストールする方法について説明します (中国語と日本語のバージョンを含む)。
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 74eb003aafd23218b90988abe113d35f1fc3035a
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108310061"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a><span data-ttu-id="86edb-103">HoloLens のローカライズ版をインストールする (第1世代)</span><span class="sxs-lookup"><span data-stu-id="86edb-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="86edb-104">HoloLens の簡体字中国語または日本語版に切り替えるには、Windows デバイス回復ツール (WDRT) を使用して、PC の言語のビルドをダウンロードし、HoloLens にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="86edb-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="86edb-105">HoloLens の中国語版または日本語版をインストールするために WDRT を使用すると、個人のファイルや設定などの既存のデータが HoloLens から削除されます。</span><span class="sxs-lookup"><span data-stu-id="86edb-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="86edb-106">PC で、 [Windows デバイス回復ツール (WDRT)](https://support.microsoft.com/help/12379)をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="86edb-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="86edb-107">お使いの PC に必要な言語 (簡  [体字中国語](https://aka.ms/hololensdownload-ch) または [日本語](https://aka.ms/hololensdownload-jp)) のパッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="86edb-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="86edb-108">ダウンロードが完了したら、[**エクスプローラー** のダウンロード] を選択し  >  ます。</span><span class="sxs-lookup"><span data-stu-id="86edb-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="86edb-109">ダウンロードした zip 形式のフォルダーを右クリックし、[**すべて** 抽出] を選択し  >  て解凍します。</span><span class="sxs-lookup"><span data-stu-id="86edb-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="86edb-110">HoloLens を、同梱のマイクロ USB ケーブルを使用して PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="86edb-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="86edb-111">(他のケーブルを使用して HoloLens に接続している場合でも、これは最適な方法です)。</span><span class="sxs-lookup"><span data-stu-id="86edb-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="86edb-112">自動的に HoloLens が検出されたら、[Microsoft HoloLens] タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="86edb-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="86edb-113">次の画面で、[ **パッケージの手動選択**] を選択   し、手順 4. で解凍したフォルダーに存在するインストールファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="86edb-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="86edb-114">(拡張子が ". ffu" のファイルを探します)。</span><span class="sxs-lookup"><span data-stu-id="86edb-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="86edb-115">[ **ソフトウェアのインストール** ] を選択し、指示に従います。</span><span class="sxs-lookup"><span data-stu-id="86edb-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="86edb-116">ビルドのインストールが完了すると、HoloLens セットアップが自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="86edb-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="86edb-117">デバイスに移動し、セットアップの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="86edb-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="86edb-118">セットアップが完了したら、[**設定**] [  >  **更新 & セキュリティ**  >  ] [**Windows Insider program**] にアクセスして、最新のプレビュービルドを受信するように構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="86edb-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="86edb-119">英語版のプレビュービルドと同様に、Windows Insider Program では、最新のプレビュービルドを使用して、HoloLens の中国語および日本語バージョンを最新の状態に保つことができます。</span><span class="sxs-lookup"><span data-stu-id="86edb-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="86edb-120">設定アプリを使用して、英語、日本語、および中国語のシステム言語を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="86edb-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="86edb-121">デバイスシステムの言語を変更する唯一の方法は、新しいビルドを点滅させることです。</span><span class="sxs-lookup"><span data-stu-id="86edb-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="86edb-122">スクリーン Pinyin キーボードを使用して簡体字中国語または日本語のテキストを入力できますが、この時点では、Bluetooth ハードウェアキーボードを使用して簡体字中国語または日本語のテキストを入力することはできません。</span><span class="sxs-lookup"><span data-stu-id="86edb-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="86edb-123">ただし、中国語または日本語の HoloLens では、Bluetooth キーボードを使用して英語で入力できます (ハードウェアキーボードを使用して英語の種類に切り替えるには、~ キーを押します)。</span><span class="sxs-lookup"><span data-stu-id="86edb-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
