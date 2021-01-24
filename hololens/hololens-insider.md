---
title: Microsoft HoloLens の Insider Preview
description: Insider ビルドを使い始め、HoloLens の次の主要なオペレーティング システム更新プログラムに関する貴重なフィードバックを提供する方法について説明します。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 1/21/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 7cc08396925368be5230a078de6fb4c7cd0a8b24
ms.sourcegitcommit: 063aa10baa190429b7248f7f1384afba7975861e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2021
ms.locfileid: "11297767"
---
# <span data-ttu-id="b950a-103">Microsoft HoloLens の Insider Preview</span><span class="sxs-lookup"><span data-stu-id="b950a-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="b950a-104">HoloLens 用の最新の Insider Preview ビルドへようこそ!</span><span class="sxs-lookup"><span data-stu-id="b950a-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="b950a-105">HoloLens [の次](hololens-insider.md#start-receiving-insider-builds) の主要なオペレーティング システム更新プログラムの使用を開始し、貴重なフィードバックを提供する方法は簡単です。</span><span class="sxs-lookup"><span data-stu-id="b950a-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <span data-ttu-id="b950a-106">Windows Insider リリース ノート</span><span class="sxs-lookup"><span data-stu-id="b950a-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="b950a-107">Windows Insider の新機能のフライトを再び開始します。</span><span class="sxs-lookup"><span data-stu-id="b950a-107">We are excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="b950a-108">We will be flighting to the Dev Channel for the latest updates.</span><span class="sxs-lookup"><span data-stu-id="b950a-108">We will be flighting to the Dev Channel for the latest updates.</span></span> <span data-ttu-id="b950a-109">このページは、Windows Insider ビルドに追加された機能と更新プログラムが追加され、引き続き更新されます。</span><span class="sxs-lookup"><span data-stu-id="b950a-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span>  <span data-ttu-id="b950a-110">これらの更新プログラムを実際に組み合わせ、準備を整えます。</span><span class="sxs-lookup"><span data-stu-id="b950a-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="b950a-111">機能名</span><span class="sxs-lookup"><span data-stu-id="b950a-111">Feature Name</span></span>                                              | <span data-ttu-id="b950a-112">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="b950a-112">Short description</span></span>                                                                      | <span data-ttu-id="b950a-113">ビルドで使用可能</span><span class="sxs-lookup"><span data-stu-id="b950a-113">Available in build</span></span> |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [<span data-ttu-id="b950a-114">新しい Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b950a-114">New Microsoft Edge</span></span>](#introducing-the-new-microsoft-edge) | <span data-ttu-id="b950a-115">HoloLens 2 で、Chromium ベースの新しい Microsoft Edge を利用できる</span><span class="sxs-lookup"><span data-stu-id="b950a-115">The new, Chromium-based Microsoft Edge is now available for HoloLens 2</span></span>                         | <span data-ttu-id="b950a-116">20279.1006</span><span class="sxs-lookup"><span data-stu-id="b950a-116">20279.1006</span></span> |
| [<span data-ttu-id="b950a-117">新しい設定アプリ</span><span class="sxs-lookup"><span data-stu-id="b950a-117">New Settings app</span></span>](#new-settings-app)                     | <span data-ttu-id="b950a-118">従来の設定アプリは、新しい機能と設定で更新されたバージョンに置き換えられる</span><span class="sxs-lookup"><span data-stu-id="b950a-118">The legacy Settings app is being replaced by an updated version with new features and settings</span></span> | <span data-ttu-id="b950a-119">20279.1006</span><span class="sxs-lookup"><span data-stu-id="b950a-119">20279.1006</span></span> |
| [<span data-ttu-id="b950a-120">既定のアプリ ピッカー</span><span class="sxs-lookup"><span data-stu-id="b950a-120">Default app picker</span></span>](#default-app-picker)                 | <span data-ttu-id="b950a-121">ファイルまたはリンクの種類ごとに起動するアプリを選択する</span><span class="sxs-lookup"><span data-stu-id="b950a-121">Choose which app should launch for each file or link type</span></span>                                      | <span data-ttu-id="b950a-122">20279.1006</span><span class="sxs-lookup"><span data-stu-id="b950a-122">20279.1006</span></span> |
| [<span data-ttu-id="b950a-123">Office Web アプリ</span><span class="sxs-lookup"><span data-stu-id="b950a-123">Office web app</span></span>](#office-web-app)                         | <span data-ttu-id="b950a-124">新しい Web アプリOfficeが [すべてのアプリ] に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b950a-124">A shortcut to the Office web app is now listed in "All apps"</span></span>                                   | <span data-ttu-id="b950a-125">20279.1006</span><span class="sxs-lookup"><span data-stu-id="b950a-125">20279.1006</span></span> |
| [<span data-ttu-id="b950a-126">スワイプして入力する</span><span class="sxs-lookup"><span data-stu-id="b950a-126">Swipe to type</span></span>](#swipe-to-type)                           | <span data-ttu-id="b950a-127">ホログラフィック キーボードで指のヒントを使って単語を "スワイプ" する</span><span class="sxs-lookup"><span data-stu-id="b950a-127">Use the tip of your finger to "swipe" words on the holographic keyboard</span></span>                        | <span data-ttu-id="b950a-128">20279.1006</span><span class="sxs-lookup"><span data-stu-id="b950a-128">20279.1006</span></span> |
| [<span data-ttu-id="b950a-129">USB-C 外部マイクのサポート</span><span class="sxs-lookup"><span data-stu-id="b950a-129">USB-C External Microphone Support</span></span>](#usb-c-external-microphone-support) | <span data-ttu-id="b950a-130">アプリやリモート アシストには USB-C マイクを使用します。</span><span class="sxs-lookup"><span data-stu-id="b950a-130">Use USB-C microphones for apps and / or Remote Assist.</span></span>| <span data-ttu-id="b950a-131">20279.1006</span><span class="sxs-lookup"><span data-stu-id="b950a-131">20279.1006</span></span> |
| [<span data-ttu-id="b950a-132">キオスク モードの新しいアプリの新しい AUMID</span><span class="sxs-lookup"><span data-stu-id="b950a-132">New AUMIDs for new apps in Kiosk mode</span></span>](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | <span data-ttu-id="b950a-133">新しい設定とエッジ アプリの AUMID</span><span class="sxs-lookup"><span data-stu-id="b950a-133">AUMIDs for new Settings and Edge apps</span></span> | <span data-ttu-id="b950a-134">20279.1006</span><span class="sxs-lookup"><span data-stu-id="b950a-134">20279.1006</span></span> |
| [<span data-ttu-id="b950a-135">キオスク モードの失敗の手渡しの改善</span><span class="sxs-lookup"><span data-stu-id="b950a-135">Improved Kiosk mode failure handing</span></span>](#kiosk-mode-behavior-changes-for-handling-of-failures) | <span data-ttu-id="b950a-136">キオスク モードでは、空のスタート メニューの前にグローバル割り当てられたアクセスが見えます。</span><span class="sxs-lookup"><span data-stu-id="b950a-136">Kiosk mode looks for Global Assigned Access before empty start menu.</span></span> | <span data-ttu-id="b950a-137">20279.1006</span><span class="sxs-lookup"><span data-stu-id="b950a-137">20279.1006</span></span> |
| [<span data-ttu-id="b950a-138">フォールバック診断を構成する</span><span class="sxs-lookup"><span data-stu-id="b950a-138">Configure Fallback Diagnostics</span></span>](#configuring-fallback-diagnostics-via-settings-app) | <span data-ttu-id="b950a-139">設定アプリでのフォールバック診断動作の設定</span><span class="sxs-lookup"><span data-stu-id="b950a-139">Setting Fallback Diagnostic Behavior in Settings App</span></span> | <span data-ttu-id="b950a-140">20279.1006</span><span class="sxs-lookup"><span data-stu-id="b950a-140">20279.1006</span></span> |

### <span data-ttu-id="b950a-141">新しい Microsoft Edge の導入</span><span class="sxs-lookup"><span data-stu-id="b950a-141">Introducing the new Microsoft Edge</span></span>

![従来の Microsoft Edge ロゴから新しい Microsoft Edge ロゴへのアニメーション](images/new-edge.gif)

<span data-ttu-id="b950a-143">新しい Microsoft Edge は [Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) オープン ソース プロジェクトを採用して、お客様との互換性を向上し、Web 開発者向けの Web の断片化を減らします。</span><span class="sxs-lookup"><span data-stu-id="b950a-143">The new Microsoft Edge [adopts the Chromium open source project](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) to create better compatibility for customers and less fragmentation of the web for web developers.</span></span>

<span data-ttu-id="b950a-144">この Insider プレビューでは、HoloLens 2 のお客様が新しい Microsoft Edge を初めて利用できます。</span><span class="sxs-lookup"><span data-stu-id="b950a-144">With this Insider preview, the new Microsoft Edge is available to HoloLens 2 customers for the first time!</span></span> <span data-ttu-id="b950a-145">新しい Microsoft Edge は最終的に HoloLens 2 の従来の Microsoft Edge に取って代わる機能ですが、現在、両方のブラウザーが Insider で利用できます。</span><span class="sxs-lookup"><span data-stu-id="b950a-145">While the new Microsoft Edge will eventually replace legacy Microsoft Edge on HoloLens 2, both browsers are currently available to Insiders.</span></span> <span data-ttu-id="b950a-146">新しい Microsoft Edge のフィードバック送信\*\*\*\* 機能またはフィードバック Hub を介して、フィードバックやバグをチームと[共有してください](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="b950a-146">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge or via [Feedback Hub](hololens-feedback.md).</span></span>

![新しい Microsoft Edge のスクリーンショット](images/new-edge-ui.png)

#### <span data-ttu-id="b950a-148">新しい Microsoft Edge の起動</span><span class="sxs-lookup"><span data-stu-id="b950a-148">Launching the new Microsoft Edge</span></span>

<span data-ttu-id="b950a-149">Insider が利用できる Microsoft Edge には、新しい Microsoft Edge の新しい Microsoft Edge アイコン (青と緑のスループ アイコンで表される) と従来の Microsoft Edge (白い ![ "e" アイコンで表される) の 2 つのバージョンがあります。 ](images/new_edge_logo.png)</span><span class="sxs-lookup"><span data-stu-id="b950a-149">There are two versions of Microsoft Edge available to Insiders: the new Microsoft Edge ![new Microsoft Edge icon](images/new_edge_logo.png) (represented by a blue and green swirl icon) and legacy Microsoft Edge (represented by the white "e" icon).</span></span> <span data-ttu-id="b950a-150">新しい Microsoft Edge はスタート メニューにピン留めされ、Web リンクをアクティブ化すると自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="b950a-150">The new Microsoft Edge is pinned to the Start menu and will automatically launch when you activate a web link.</span></span> <span data-ttu-id="b950a-151">従来の Microsoft Edge を既定の Web ブラウザーとして使用する場合は、以下の手順を参照して既定のアプリを [リセットしてください](#default-app-picker)。</span><span class="sxs-lookup"><span data-stu-id="b950a-151">If you would like to revert to using legacy Microsoft Edge as your default web browser, see the instructions below for [resetting default apps](#default-app-picker).</span></span>

> [!NOTE]
> <span data-ttu-id="b950a-152">HoloLens 2 で新しい Microsoft Edge を初めて起動すると、設定とデータは従来の Microsoft Edge からインポートされます。</span><span class="sxs-lookup"><span data-stu-id="b950a-152">When you first launch the new Microsoft Edge on HoloLens 2, your settings and data will be imported from legacy Microsoft Edge.</span></span> <span data-ttu-id="b950a-153">新しい Microsoft Edge を起動した後も従来の Microsoft Edge を使用し続ける場合、その新しいデータは従来の Microsoft Edge から新しい Microsoft Edge に同期されません。</span><span class="sxs-lookup"><span data-stu-id="b950a-153">If you continue to use legacy Microsoft Edge after launching the new Microsoft Edge, that new data will not be synced from legacy Microsoft Edge to the new Microsoft Edge.</span></span>

#### <span data-ttu-id="b950a-154">新しい Microsoft Edge のポリシー設定の構成</span><span class="sxs-lookup"><span data-stu-id="b950a-154">Configuring policy settings for the new Microsoft Edge</span></span>

<span data-ttu-id="b950a-155">新しい Microsoft Edge では、IT 管理者は従来の Microsoft Edge で利用していたよりも、HoloLens 2 のブラウザー ポリシーの広範なセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="b950a-155">The new Microsoft Edge offers IT admins a much broader set of browser policies on HoloLens 2 than were previously available with legacy Microsoft Edge.</span></span>

<span data-ttu-id="b950a-156">新しい Microsoft Edge のポリシー設定の管理について詳しく知る上で役立つリソースを次に示します。</span><span class="sxs-lookup"><span data-stu-id="b950a-156">Here are some helpful resources for learning more about managing policy settings for the new Microsoft Edge:</span></span>

- [<span data-ttu-id="b950a-157">Microsoft Intune を使って Microsoft Edge ポリシー設定を構成する</span><span class="sxs-lookup"><span data-stu-id="b950a-157">Configure Microsoft Edge policy settings with Microsoft Intune</span></span>](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [<span data-ttu-id="b950a-158">Microsoft Edge Legacy から Microsoft Edge ポリシーへのマッピング</span><span class="sxs-lookup"><span data-stu-id="b950a-158">Microsoft Edge Legacy to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [<span data-ttu-id="b950a-159">Google Chrome から Microsoft Edge ポリシーへのマッピング</span><span class="sxs-lookup"><span data-stu-id="b950a-159">Google Chrome to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- <span data-ttu-id="b950a-160">[Microsoft Edge Enterprise の完全なドキュメント](https://docs.microsoft.com/deployedge/)</span><span class="sxs-lookup"><span data-stu-id="b950a-160">Full [Microsoft Edge Enterprise documentation](https://docs.microsoft.com/deployedge/)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b950a-161">新しい Microsoft Edge でサポートされているブラウザー ポリシーの量が多いので、新しい各ポリシーが HoloLens 2 で動作するとは、チームは保証できません。</span><span class="sxs-lookup"><span data-stu-id="b950a-161">Because of the volume of browser policies supported by the new Microsoft Edge, our team is unable to guarantee that each new policy works on HoloLens 2.</span></span> <span data-ttu-id="b950a-162">ただし、HoloLens 2 で以前サポートされた従来の各 Microsoft Edge ポリシーと同等の新しい Microsoft Edge が期待通り動作するテストを行い、確認しました。</span><span class="sxs-lookup"><span data-stu-id="b950a-162">However, we've tested and confirmed that the new Microsoft Edge equivalent of each legacy Microsoft Edge policy previously supported on HoloLens 2 work as expected.</span></span> <span data-ttu-id="b950a-163">HoloLens 2 で使用していた従来の各 Microsoft Edge ブラウザー ポリシーと同等の新しい Microsoft Edge を見つけるには [、Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) レガシから Microsoft Edge へのポリシー マッピングをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b950a-163">See [Microsoft Edge Legacy to Microsoft Edge policy mapping](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) to find the new Microsoft Edge equivalent of each legacy Microsoft Edge browser policy you were using with HoloLens 2.</span></span>
>
> <span data-ttu-id="b950a-164">HoloLens 2 では動作しない新しい\*\* Microsoft Edge ポリシーが 2 つ以上あります。</span><span class="sxs-lookup"><span data-stu-id="b950a-164">There are at least two new Microsoft Edge policies that we know *will not* work with HoloLens 2:</span></span>
> - <span data-ttu-id="b950a-165">EnterpriseModeSiteList</span><span class="sxs-lookup"><span data-stu-id="b950a-165">EnterpriseModeSiteList</span></span>
> - <span data-ttu-id="b950a-166">EnterpriseSiteListServiceURL</span><span class="sxs-lookup"><span data-stu-id="b950a-166">EnterpriseSiteListServiceURL</span></span>

#### <span data-ttu-id="b950a-167">HoloLens 2 の新しい Microsoft Edge に期待される機能</span><span class="sxs-lookup"><span data-stu-id="b950a-167">What to expect from the new Microsoft Edge on HoloLens 2</span></span>

<span data-ttu-id="b950a-168">新しい Microsoft Edge は、新しい UWP アダプター レイヤーを使ったネイティブの Win32 アプリで、HoloLens 2 のような UWP 専用デバイスで実行することができるため、一部の機能はすぐに利用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="b950a-168">Because the new Microsoft Edge is a native Win32 app with a new UWP adapter layer allowing it to run on UWP-only devices like HoloLens 2, some features may not be immediately available.</span></span> <span data-ttu-id="b950a-169">今後数か月の間に新しいシナリオと機能をサポートする予定なので、このスペースで最新の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b950a-169">We'll be supporting new scenarios and features over the coming months, so please check this space for up-to-date information.</span></span>

**<span data-ttu-id="b950a-170">動作が予想されるシナリオと機能:</span><span class="sxs-lookup"><span data-stu-id="b950a-170">Scenarios and features expected to work:</span></span>**
- <span data-ttu-id="b950a-171">初回実行エクスペリエンス、プロファイルへのサインイン、同期</span><span class="sxs-lookup"><span data-stu-id="b950a-171">First-run experience, sign-in to profile, and sync</span></span>
- <span data-ttu-id="b950a-172">Web サイトが期待どおりにレンダリングされ、動作する必要がある</span><span class="sxs-lookup"><span data-stu-id="b950a-172">Websites should render and behave as expected</span></span>
- <span data-ttu-id="b950a-173">ほとんどのブラウザー機能 (お気に入り、履歴など) は期待通りに動作する必要があります</span><span class="sxs-lookup"><span data-stu-id="b950a-173">Most browser functionality (Favorites, History, etc.) should work as expected</span></span>
- <span data-ttu-id="b950a-174">濃色モード</span><span class="sxs-lookup"><span data-stu-id="b950a-174">Dark mode</span></span>
- <span data-ttu-id="b950a-175">デバイスへの Web アプリのインストール</span><span class="sxs-lookup"><span data-stu-id="b950a-175">Installing web apps to the device</span></span>
- <span data-ttu-id="b950a-176">拡張機能のインストール (HoloLens 2 で正しく動作しない拡張機能を使用している場合は、お知らせください)</span><span class="sxs-lookup"><span data-stu-id="b950a-176">Installing extensions (please let us know if you use any extensions that don't work properly on HoloLens 2)</span></span>
- <span data-ttu-id="b950a-177">PDF の表示とマーキング</span><span class="sxs-lookup"><span data-stu-id="b950a-177">Viewing and marking up a PDF</span></span>
- <span data-ttu-id="b950a-178">1 つのブラウザー ウィンドウからの空間サウンド</span><span class="sxs-lookup"><span data-stu-id="b950a-178">Spatial sound from a single browser window</span></span>
- <span data-ttu-id="b950a-179">ブラウザーの自動更新と手動更新</span><span class="sxs-lookup"><span data-stu-id="b950a-179">Automatic and manual updating of the browser</span></span>
- <span data-ttu-id="b950a-180">[印刷] メニューから PDF を保存する ([PDF に保存] オプションを使用)</span><span class="sxs-lookup"><span data-stu-id="b950a-180">Saving a PDF from the Print menu (using "Save to PDF" option)</span></span>

**<span data-ttu-id="b950a-181">近日公開予定のシナリオと機能:</span><span class="sxs-lookup"><span data-stu-id="b950a-181">Scenarios and features coming soon:</span></span>**
- <span data-ttu-id="b950a-182">WebXR と 360 ビューアー拡張機能</span><span class="sxs-lookup"><span data-stu-id="b950a-182">WebXR and 360 Viewer extension</span></span>
- <span data-ttu-id="b950a-183">環境内に配置された複数のウィンドウを閲覧する場合の正しいウィンドウへのコンテンツの復元</span><span class="sxs-lookup"><span data-stu-id="b950a-183">Content restoration to correct window when browsing across multiple windows placed in your environment</span></span>

**<span data-ttu-id="b950a-184">動作しないシナリオと機能:</span><span class="sxs-lookup"><span data-stu-id="b950a-184">Scenarios and features not expected to work:</span></span>**
- <span data-ttu-id="b950a-185">同時オーディオ ストリームを備え、複数のウィンドウからの空間サウンド</span><span class="sxs-lookup"><span data-stu-id="b950a-185">Spatial sound from multiple windows with simultaneous audio streams</span></span>
- <span data-ttu-id="b950a-186">"見て、言ってみる"</span><span class="sxs-lookup"><span data-stu-id="b950a-186">"See it, say it"</span></span>
- <span data-ttu-id="b950a-187">印刷</span><span class="sxs-lookup"><span data-stu-id="b950a-187">Printing</span></span>

**<span data-ttu-id="b950a-188">既知のブラウザーの問題の上位:</span><span class="sxs-lookup"><span data-stu-id="b950a-188">Top known browser issues:</span></span>**
- <span data-ttu-id="b950a-189">デバイスをリセットすると、新しい Microsoft Edge が削除されます。</span><span class="sxs-lookup"><span data-stu-id="b950a-189">Resetting your device will remove the new Microsoft Edge</span></span>
- <span data-ttu-id="b950a-190">ホログラフィック キーボードの拡大鏡のプレビューに誤ったコンテンツが表示される</span><span class="sxs-lookup"><span data-stu-id="b950a-190">The magnifier preview in the holographic keyboard shows incorrect content</span></span>

#### <span data-ttu-id="b950a-191">Microsoft Edge Insider チャネル</span><span class="sxs-lookup"><span data-stu-id="b950a-191">Microsoft Edge Insider channels</span></span>

<span data-ttu-id="b950a-192">Microsoft Edge チームは、Edge Insider コミュニティ (ベータ、開発、Canary) の 3 つのプレビュー チャネルを利用できます。</span><span class="sxs-lookup"><span data-stu-id="b950a-192">The Microsoft Edge team makes three preview channels available to the Edge Insider community: Beta, Dev, and Canary.</span></span> <span data-ttu-id="b950a-193">プレビュー チャネルをインストールしても、HoloLens 2 にリリースされたバージョンの Microsoft Edge はアンインストールされません。また、複数の Microsoft Edge を同時にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="b950a-193">Installing a preview channel doesn't uninstall the released version of Microsoft Edge on your HoloLens 2, and you can install more than one at the same time.</span></span> 

<span data-ttu-id="b950a-194">Edge Insider [コミュニティについて詳しくは、Microsoft Edge Insider](https://www.microsoftedgeinsider.com) ホームページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b950a-194">Visit the [Microsoft Edge Insider homepage](https://www.microsoftedgeinsider.com) to learn more about the Edge Insider community.</span></span> <span data-ttu-id="b950a-195">さまざまな Edge Insider チャネルについて詳しくは、Edge Insider のダウンロード ページ [をご覧ください](https://www.microsoftedgeinsider.com/download)。</span><span class="sxs-lookup"><span data-stu-id="b950a-195">To learn more about the different Edge Insider channels and get started, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download).</span></span>

<span data-ttu-id="b950a-196">HoloLens 2 に Microsoft Edge Insider チャネルをインストールするには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="b950a-196">There are a couple methods available for installing Microsoft Edge Insider channels to HoloLens 2:</span></span>

**<span data-ttu-id="b950a-197">デバイスへの直接インストール (現在は非管理対象デバイスでのみ利用可能)</span><span class="sxs-lookup"><span data-stu-id="b950a-197">Direct install on device (currently only available to unmanaged devices)</span></span>**
  1. <span data-ttu-id="b950a-198">HoloLens 2 で、Edge Insider ダウンロード [ページにアクセスします。](https://www.microsoftedgeinsider.com/download)</span><span class="sxs-lookup"><span data-stu-id="b950a-198">On your HoloLens 2, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download)</span></span>
  1. <span data-ttu-id="b950a-199">インストールする Edge Insider チャネルの **HoloLens 2** のダウンロード ボタンを選択する</span><span class="sxs-lookup"><span data-stu-id="b950a-199">Select the **Download for HoloLens 2** button for the Edge Insider channel you wish to install</span></span>
  1. <span data-ttu-id="b950a-200">ダウンロードした .msix ファイルを、エッジ のダウンロード キューまたはデバイスの [ダウンロード] フォルダーから起動します (エクスプローラーを使用)</span><span class="sxs-lookup"><span data-stu-id="b950a-200">Launch the downloaded .msix file from the Edge download queue or from your device's "Downloads" folder (using File Explorer)</span></span>
  1. <span data-ttu-id="b950a-201">[アプリ インストーラーが](app-deploy-app-installer.md) 起動する</span><span class="sxs-lookup"><span data-stu-id="b950a-201">[App installer](app-deploy-app-installer.md) will launch</span></span>
  1. <span data-ttu-id="b950a-202">[インストール] **ボタンを選択** する</span><span class="sxs-lookup"><span data-stu-id="b950a-202">Select the **Install** button</span></span>
  1. <span data-ttu-id="b950a-203">インストールが成功すると、スタート メニューの [すべてのアプリ] の一覧に Microsoft \*\*\*\* Edge Beta、Dev、Canary が個別のエントリとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="b950a-203">After successful install, you will find Microsoft Edge Beta, Dev, or Canary as a separate entry in the **All apps** list of the Start menu</span></span>

**<span data-ttu-id="b950a-204">Windows Device Portal を使用して[](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)PC 経由でインストールする (HoloLens 2 で開発者モードを有効にする必要がある)</span><span class="sxs-lookup"><span data-stu-id="b950a-204">Install via PC with Windows Device Portal (requires [developer mode](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) to be enabled on HoloLens 2)</span></span>**
  1. <span data-ttu-id="b950a-205">PC で、Edge Insider ダウンロード [ページにアクセスします。](https://www.microsoftedgeinsider.com/download)</span><span class="sxs-lookup"><span data-stu-id="b950a-205">On your PC, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download)</span></span>
  1. <span data-ttu-id="b950a-206">インストールする\*\*\*\* Edge Insider チャネルの [Windows 10 のダウンロード] ボタンの横にあるドロップダウン矢印ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="b950a-206">Select the **drop-down arrow button** next to the "Download for Windows 10" button for the Edge Insider channel you wish to install</span></span>
  1. <span data-ttu-id="b950a-207">ドロップダウン **メニューで HoloLens 2** を選択する</span><span class="sxs-lookup"><span data-stu-id="b950a-207">Select **HoloLens 2** in the drop-down menu</span></span>
  1. <span data-ttu-id="b950a-208">.msix ファイルを PC の [ダウンロード] フォルダー (または簡単に見つけられている別のフォルダー) に保存します。</span><span class="sxs-lookup"><span data-stu-id="b950a-208">Save the .msix file to the "Downloads" folder of your PC (or another folder you can easily find)</span></span>
  1. <span data-ttu-id="b950a-209">PC [で Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) を使用して、ダウンロードした .msix ファイルを HoloLens 2 にインストールする</span><span class="sxs-lookup"><span data-stu-id="b950a-209">Use [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) on your PC to install the downloaded .msix file on HoloLens 2</span></span>
  1. <span data-ttu-id="b950a-210">インストールが成功すると、スタート メニューの [すべてのアプリ] の一覧に Microsoft \*\*\*\* Edge Beta、Dev、Canary が別のエントリとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="b950a-210">After successful install, you will find Microsoft Edge Beta, Dev, or Canary as a separate entry in the **All apps** list of the Start menu</span></span>

> [!NOTE]
> <span data-ttu-id="b950a-211">HoloLens 2 向け Windows Insider プレビューでは、デバイス上の Microsoft Edge のバージョンが、Microsoft Edge Insider チャネルの一部 (またはすべて) で利用可能なバージョンよりも高い場合があります。</span><span class="sxs-lookup"><span data-stu-id="b950a-211">During this Windows Insider preview for HoloLens 2, the version of Microsoft Edge on your device may be higher than those available in some (or all) of the Microsoft Edge Insider channels.</span></span> <span data-ttu-id="b950a-212">これは、HoloLens 2 の Web ブラウザーを特に対象とする新機能と修正プログラムが、可能な限り迅速に Windows Insider に提供されます。</span><span class="sxs-lookup"><span data-stu-id="b950a-212">This is to ensure new features and fixes specifically targeting the web browser on HoloLens 2 are getting to our Windows Insiders as quickly as possible.</span></span> <span data-ttu-id="b950a-213">次の Windows 更新プログラムの一般リリースの直後に、Microsoft Edge Insider チャネル ビルドは HoloLens 2 の Microsoft Edge のバージョンを上回り、先に進む予定です。</span><span class="sxs-lookup"><span data-stu-id="b950a-213">Shortly after the public release of the next Windows update, the Microsoft Edge Insider channel builds will surpass, and stay ahead of, the version of Microsoft Edge on your HoloLens 2.</span></span>

### <span data-ttu-id="b950a-214">新しい設定アプリ</span><span class="sxs-lookup"><span data-stu-id="b950a-214">New Settings app</span></span>

<span data-ttu-id="b950a-215">このリリースでは、設定アプリの新しいバージョンが導入されています。</span><span class="sxs-lookup"><span data-stu-id="b950a-215">With this release, we're introducing a new version of the Settings app.</span></span> <span data-ttu-id="b950a-216">新しい設定アプリには、サウンド、Power & スリープ、ネットワーク & インターネット、アプリ、アカウント、簡単操作など、HoloLens 2 の新機能と拡張された設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b950a-216">The new Settings app includes new features and expanded settings for HoloLens 2 in the following areas: Sound, Power & sleep, Network & Internet, Apps, Accounts, Ease of Access, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="b950a-217">新しい設定アプリは従来の設定アプリとは異なっているので、以前環境の周囲に配置した設定ウィンドウは、更新時に削除されます。</span><span class="sxs-lookup"><span data-stu-id="b950a-217">Because the new Settings app is distinct from the legacy Settings app, any Settings windows you previously placed around your environment will be removed upon update.</span></span>

![新しい設定アプリのホーム ページ](images/new-settings-app.png)

**<span data-ttu-id="b950a-219">新機能と設定</span><span class="sxs-lookup"><span data-stu-id="b950a-219">New features and settings</span></span>**
- <span data-ttu-id="b950a-220">設定検索: キーワードまたは設定名を使用して設定ホーム ページから設定を検索する</span><span class="sxs-lookup"><span data-stu-id="b950a-220">Settings search: search for settings from the Settings homepage using keywords or the setting's name</span></span>
- <span data-ttu-id="b950a-221">システム > サウンド:</span><span class="sxs-lookup"><span data-stu-id="b950a-221">System > Sound:</span></span>
  - <span data-ttu-id="b950a-222">入力オーディオ デバイスと出力オーディオ デバイス: 入力オーディオ デバイスと出力オーディオ デバイスを個別に選択します (たとえば、Bluetooth ヘッドホンでオーディオを聞く場合や、オーディオ入力に USB-C マイクを使用する場合など)。</span><span class="sxs-lookup"><span data-stu-id="b950a-222">Input and output audio devices: independently choose your input and output audio devices (for example, listen to audio via Bluetooth headphones or use a USB-C microphone for audio input).</span></span> <span data-ttu-id="b950a-223">注: Bluetooth HoloLens 2 ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b950a-223">Note: Bluetooth microphones are not supported by HoloLens 2.</span></span>
  - <span data-ttu-id="b950a-224">アプリのボリューム: 各アプリのボリュームを個別に調整する</span><span class="sxs-lookup"><span data-stu-id="b950a-224">App volume: independently adjust the volume of each app</span></span>
- <span data-ttu-id="b950a-225">システム>電源&スリープ: 非アクティブな状態が一時間続くとデバイスがスリープ状態にされる時期を選択する</span><span class="sxs-lookup"><span data-stu-id="b950a-225">System > Power & sleep: choose when the device should go to sleep after a period of inactivity</span></span>
- <span data-ttu-id="b950a-226">システム>バッテリー: バッテリー節約機能モードを手動で有効にするか、バッテリー節約機能モードが自動的に有効になる時点でバッテリーしきい値を設定する</span><span class="sxs-lookup"><span data-stu-id="b950a-226">System > Battery: manually enable battery saver mode or set a battery threshold at which point battery saver mode turns on automatically</span></span>
- <span data-ttu-id="b950a-227">USB >: 既定では USB 接続を無効にできます</span><span class="sxs-lookup"><span data-stu-id="b950a-227">Devices > USB: you can disable USB connections by default</span></span>
- <span data-ttu-id="b950a-228">ネットワーク & インターネット:</span><span class="sxs-lookup"><span data-stu-id="b950a-228">Network & Internet:</span></span>
  - <span data-ttu-id="b950a-229">USB-C イーサネット アダプターは、ネットワーク ネットワーク とインターネット&されます。</span><span class="sxs-lookup"><span data-stu-id="b950a-229">USB-C Ethernet adapters will now appear in Network & Internet</span></span>
  - <span data-ttu-id="b950a-230">USB-C イーサネット アダプターの設定 (IP アドレスを含む) が使用可能に</span><span class="sxs-lookup"><span data-stu-id="b950a-230">USB-C Ethernet adapter settings are now available, including its IP address</span></span>
  - <span data-ttu-id="b950a-231">HoloLens 2 でフライト モードを有効にできる</span><span class="sxs-lookup"><span data-stu-id="b950a-231">You can now enable airplane mode on HoloLens 2</span></span>
- <span data-ttu-id="b950a-232">アプリ: ファイルとリンクの種類に使用される既定のアプリをリセットできます。</span><span class="sxs-lookup"><span data-stu-id="b950a-232">Apps: you can reset the default apps used for file and link types.</span></span> <span data-ttu-id="b950a-233">詳 [しくは、「既定のアプリ ピッカー](#default-app-picker) 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b950a-233">See [Default app picker](#default-app-picker) for more information.</span></span>
- <span data-ttu-id="b950a-234">他>ユーザーのアカウント: デバイス所有者は、ユーザーの追加、標準ユーザーのデバイス所有者へのアップグレード、デバイス所有者の標準ユーザーへのダウングレード、ユーザーの削除を行います。</span><span class="sxs-lookup"><span data-stu-id="b950a-234">Accounts > Other users: device owners can add users, upgrade standard users to device owners, downgrade device owners to standard users, and remove users.</span></span>
- <span data-ttu-id="b950a-235">簡単操作: テキスト サイズと視覚効果を変更する</span><span class="sxs-lookup"><span data-stu-id="b950a-235">Ease of Access: change text size and some visual effects</span></span>

**<span data-ttu-id="b950a-236">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b950a-236">Known issues</span></span>**
- <span data-ttu-id="b950a-237">以前に配置した設定ウィンドウは削除されます (上記の注を参照)</span><span class="sxs-lookup"><span data-stu-id="b950a-237">Previously placed Settings windows will be removed (see note above)</span></span>
- <span data-ttu-id="b950a-238">[通知] ページにアクセスすると、設定アプリがクラッシュする可能性があります (調査中)</span><span class="sxs-lookup"><span data-stu-id="b950a-238">Visiting the Notifications page may crash the Settings app (investigating)</span></span>
- <span data-ttu-id="b950a-239">現在イーサネット ページが表示されていない (間もなく修正される予定)</span><span class="sxs-lookup"><span data-stu-id="b950a-239">The Ethernet page currently doesn't show up (to be fixed soon)</span></span>
- <span data-ttu-id="b950a-240">設定アプリを使ってデバイスの名前を変更できなくなりました (IT 管理者はプロビジョニング パッケージまたは MDM を使ってデバイスの名前を変更できます)。</span><span class="sxs-lookup"><span data-stu-id="b950a-240">You can no longer rename your device with the Settings app (IT admins can use provisioning packages or MDM to rename devices)</span></span>
- <span data-ttu-id="b950a-241">新しい Microsoft Edge のバッテリー使用量は、UWP アダプター レイヤーでサポートされる Win32 デスクトップ アプリケーションとしての性質上、正確ではない可能性があります (間もなく修正される予定はありません)</span><span class="sxs-lookup"><span data-stu-id="b950a-241">Battery usage for the new Microsoft Edge may not be accurate, due to its nature as a Win32 desktop application supported by a UWP adapter layer (no fix anticipated soon)</span></span>

### <span data-ttu-id="b950a-242">既定のアプリ ピッカー</span><span class="sxs-lookup"><span data-stu-id="b950a-242">Default app picker</span></span>

<span data-ttu-id="b950a-243">ハイパーリンクをアクティブにするか、複数のインストール済みアプリをサポートするファイルの種類を開いた場合は、新しいウィンドウが開き、ファイルまたはリンクの種類を処理するインストール済みアプリを選択するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b950a-243">When you activate a hyperlink or open a file type with more than one installed app which supports it, you will see a new window open prompting you to select which installed app should handle the file or link type.</span></span> <span data-ttu-id="b950a-244">このウィンドウでは、選択したアプリでファイルまたはリンクの種類として "Once" または "Always" を処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="b950a-244">In this window you can also choose to have the selected app handle the file or link type "Once" or "Always."</span></span>

![アプリ ピッカー ウィンドウ](images/default-app-picker.png)

<span data-ttu-id="b950a-246">If you choose "Always" but later want to change which app handles a particular file or link type, you can reset your saved defaults in **Settings > Apps**.</span><span class="sxs-lookup"><span data-stu-id="b950a-246">If you choose "Always" but later want to change which app handles a particular file or link type, you can reset your saved defaults in **Settings > Apps**.</span></span> <span data-ttu-id="b950a-247">ページの下部までスクロールし、[ファイルの種類\*\*\*\* 用の既定のアプリ] または [リンクの種類用の既定のアプリ] の下にある [クリア] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="b950a-247">Scroll to the bottom of the page and select the **Clear** button under "Default apps for file types" and/or "Default apps for link types."</span></span> <span data-ttu-id="b950a-248">デスクトップ PC の同様の設定とは異なり、個々のファイルの種類の既定値をリセットできます。</span><span class="sxs-lookup"><span data-stu-id="b950a-248">Unlike the similar setting on desktop PCs, you can't reset individual file type defaults.</span></span>

### <span data-ttu-id="b950a-249">Office Web アプリ</span><span class="sxs-lookup"><span data-stu-id="b950a-249">Office web app</span></span>

<span data-ttu-id="b950a-250">スタート Officeの [すべてのアプリ] の一覧に、新しい Web アプリが追加されました。</span><span class="sxs-lookup"><span data-stu-id="b950a-250">The Office web app has been added to the "All apps" list in the Start menu.</span></span> <span data-ttu-id="b950a-251">この Web アプリは、スタート画面にピン留めしたりアンインストールしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b950a-251">This web app can also be pinned to Start or uninstalled.</span></span> <span data-ttu-id="b950a-252">これは Web アプリなので、その機能はアクセスして体験した機能と正確に一致します https://www.office.com 。</span><span class="sxs-lookup"><span data-stu-id="b950a-252">Because this is a web app, its functionality matches exactly what you'd experience by visiting https://www.office.com.</span></span> <span data-ttu-id="b950a-253">Office Web アプリの機能は、HoloLens 2 にアクティブなインターネット接続がある場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b950a-253">Office web app functionality is only available when your HoloLens 2 has an active internet connection.</span></span>

### <span data-ttu-id="b950a-254">スワイプして入力する</span><span class="sxs-lookup"><span data-stu-id="b950a-254">Swipe to type</span></span>

<span data-ttu-id="b950a-255">一部のお客様は、入力する単語の形をスワイプすることで仮想キーボードを "入力" する方が速く見つかり、ホログラフィック キーボード用にこの機能をプレビューします。</span><span class="sxs-lookup"><span data-stu-id="b950a-255">Some customers find it faster to "type" on virtual keyboards by swiping the shape of the word they intend to type, and we're previewing this feature for the holographic keyboard.</span></span> <span data-ttu-id="b950a-256">ホログラフィック キーボードの平面を指の先端を通して一度に 1 つの単語をスワイプし、単語の形状をスワイプして、キーボードの平面から指の先端を引き出します。</span><span class="sxs-lookup"><span data-stu-id="b950a-256">You can swipe one word at a time by passing the tip of your finger through the plane of the holographic keyboard, swiping the shape of the word, and then withdrawing the tip of your finger from the plane of the keyboard.</span></span> <span data-ttu-id="b950a-257">単語間でキーボードから指を外して Space キーを押す必要なく、フォローアップ語をスワイプできます。</span><span class="sxs-lookup"><span data-stu-id="b950a-257">You can swipe follow-up words without needing to press the spacebar by removing your finger from the keyboard between words.</span></span> <span data-ttu-id="b950a-258">キーボードで指が動いた後にスワイプ の証跡が表示される場合は、この機能が動作しているのが分かっています。</span><span class="sxs-lookup"><span data-stu-id="b950a-258">You will know the feature is working if you see a swipe trail following your finger's movement on the keyboard.</span></span>

<span data-ttu-id="b950a-259">この機能は、(携帯電話のディスプレイとは異なり) 指に抵抗を感じないホログラフィック キーボードの性質上、使い方が難しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="b950a-259">Please note, this feature can be tricky to use and master because of the nature of a holographic keyboard where you don't feel resistance against your finger (unlike a mobile phone display).</span></span> <span data-ttu-id="b950a-260">この機能は一般リリース向けとして評価されています。そのため、お客様からのフィードバックは重要です。この機能が役に立つ場合も、構築的なフィードバックがある場合も、フィードバック Hub でお知 [らせください](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="b950a-260">We are evaluating this feature for public release, so your feedback is important; whether you find the feature useful or you have constructive feedback, please let us know via [Feedback Hub](hololens-feedback.md).</span></span>

### <span data-ttu-id="b950a-261">USB-C 外部マイクのサポート</span><span class="sxs-lookup"><span data-stu-id="b950a-261">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b950a-262">USB マイクを **接続すると、自動的に入力デバイスとして設定されません**。</span><span class="sxs-lookup"><span data-stu-id="b950a-262">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="b950a-263">一連の USB-C ヘッドホンを接続すると、ユーザーはヘッドホンのオーディオが自動的にヘッドホンにリダイレクトされるのを確認しますが、HoloLens OS では、他の入力デバイスよりも内部マイク アレイの優先順位が優先されます。</span><span class="sxs-lookup"><span data-stu-id="b950a-263">When plugging in a set of USB-C headphones users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> **<span data-ttu-id="b950a-264">USB-C マイクを使用するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b950a-264">In order to use a USB-C microphone follow the steps below.</span></span>**

<span data-ttu-id="b950a-265">ユーザーは、[サウンドの設定] パネルを使用して、USB-C に接続された外部マイク **を** 選択できます。</span><span class="sxs-lookup"><span data-stu-id="b950a-265">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="b950a-266">USB-C マイクは、通話、録音などに使用できます。</span><span class="sxs-lookup"><span data-stu-id="b950a-266">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="b950a-267">設定アプリ**を開き**、[システム サウンド]**を**  ->  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b950a-267">Open the **Settings** app and select **System** -> **Sound**.</span></span>

![サウンド設定](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="b950a-269">リモート アシストで外部マイクを **使用**するには、ユーザーが [サウンド デバイスの管理] ハイパーリンクをクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b950a-269">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="b950a-270">次に、ドロップダウンを使用して、外部マイクを **Default** または **Communications Default に設定します。**</span><span class="sxs-lookup"><span data-stu-id="b950a-270">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="b950a-271">**[Default] を**選択すると、外部マイクがすべての場所で使用されます。</span><span class="sxs-lookup"><span data-stu-id="b950a-271">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="b950a-272">Communications **Default を選択** すると、外部マイクはリモート アシストや他の通信アプリで使用されますが、HoloLens マイク アレイは他のタスクにも引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="b950a-272">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![サウンド デバイスを管理する](images/usbc-mic-2.png)

<br>

![マイクの既定値を設定する](images/usbc-mic-3.jpg)

#### <span data-ttu-id="b950a-275">マイクのBluetoothについて</span><span class="sxs-lookup"><span data-stu-id="b950a-275">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="b950a-276">残念Bluetoothは、HoloLens 2 では現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b950a-276">Unfortunately Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

#### <span data-ttu-id="b950a-277">USB-C マイクのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b950a-277">Troubleshooting USB-C microphones</span></span>

<span data-ttu-id="b950a-278">一部の USB-C マイクは、マイクとスピーカーの両方として誤 *って報告します* 。</span><span class="sxs-lookup"><span data-stu-id="b950a-278">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="b950a-279">これは、HoloLens ではなく、マイクの問題です。</span><span class="sxs-lookup"><span data-stu-id="b950a-279">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="b950a-280">これらのマイクのいずれかを HoloLens に接続すると、サウンドが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b950a-280">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="b950a-281">幸いなことに、単純な修正プログラムがあります。</span><span class="sxs-lookup"><span data-stu-id="b950a-281">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="b950a-282">[**設定**  ->  **システム**  ->  **サウンド]** で、組み込みのスピーカー **(アナログ機能オーディオ**ドライバー) を既定のデバイスとして明示的に**設定します**。</span><span class="sxs-lookup"><span data-stu-id="b950a-282">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="b950a-283">HoloLens は、マイクを取り外して後で再接続した場合でも、この設定を記憶する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b950a-283">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![USB-C マイクのトラブルシューティング](images/usbc-mic-4.png)

### <span data-ttu-id="b950a-285">キオスク モードで新しい設定アプリとエッジ アプリを使用する</span><span class="sxs-lookup"><span data-stu-id="b950a-285">Use the new Settings and Edge apps in Kiosk modes</span></span>

<span data-ttu-id="b950a-286">キオスクにアプリを含 [めた](hololens-kiosk.md)場合、IT 管理者は多くの場合、アプリをキオスクに追加しますが、アプリ ユーザー モデル ID (AUMID) を使用します。</span><span class="sxs-lookup"><span data-stu-id="b950a-286">When including apps in in [Kiosks](hololens-kiosk.md), an IT Admin often adds the app to the Kiosk but using it's App User Model ID (AUMID).</span></span> <span data-ttu-id="b950a-287">設定アプリと Microsoft Edge アプリはどちらも新しいアプリと見なされ、それらのアプリに AUMID を使用する古いアプリキオスクは、新しい AUMID を使用するために更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b950a-287">Because both the Settings app and Microsoft Edge app are considered new apps and different that the older apps Kiosks that use AUMIDs for those apps will need to be updated to use the new AUMID.</span></span>

<span data-ttu-id="b950a-288">キオスクを変更して新しいアプリを含める場合は、新しい AUMID を追加し、古い AUMID を残することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b950a-288">When modifying a Kiosk to include the new apps, we recommend adding in the new AUMID as well as leaving the old one.</span></span> <span data-ttu-id="b950a-289">これにより、ユーザーが OS を更新するときに簡単に移行が行え、意図した方法でキオスクを使用し続ける新しいポリシーを受け取る必要がなされます。</span><span class="sxs-lookup"><span data-stu-id="b950a-289">This will create an easy transition when users update the OS and won't need to receive new policies to keep using the Kiosk as intended.</span></span>

| <span data-ttu-id="b950a-290">アプリ</span><span class="sxs-lookup"><span data-stu-id="b950a-290">App</span></span>                    | <span data-ttu-id="b950a-291">AUMID</span><span class="sxs-lookup"><span data-stu-id="b950a-291">AUMID</span></span>                                                  |
|------------------------|--------------------------------------------------------|
| <span data-ttu-id="b950a-292">古い設定アプリ</span><span class="sxs-lookup"><span data-stu-id="b950a-292">Old Settings App</span></span>       | <span data-ttu-id="b950a-293">HolographicSystemSettings_cw5n1h2txyewy!App</span><span class="sxs-lookup"><span data-stu-id="b950a-293">HolographicSystemSettings_cw5n1h2txyewy!App</span></span>            |
| <span data-ttu-id="b950a-294">新しい設定アプリ</span><span class="sxs-lookup"><span data-stu-id="b950a-294">New Settings App</span></span>       | <span data-ttu-id="b950a-295">BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App</span><span class="sxs-lookup"><span data-stu-id="b950a-295">BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App</span></span> |
| <span data-ttu-id="b950a-296">古い Microsoft Edge アプリ</span><span class="sxs-lookup"><span data-stu-id="b950a-296">Old Microsoft Edge app</span></span> | <span data-ttu-id="b950a-297">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span><span class="sxs-lookup"><span data-stu-id="b950a-297">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span></span>    |
| <span data-ttu-id="b950a-298">新しい Microsoft Edge アプリ</span><span class="sxs-lookup"><span data-stu-id="b950a-298">New Microsoft Edge app</span></span> | <span data-ttu-id="b950a-299">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE</span><span class="sxs-lookup"><span data-stu-id="b950a-299">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE</span></span>    |

### <span data-ttu-id="b950a-300">エラーの処理に関するキオスク モードの動作の変更</span><span class="sxs-lookup"><span data-stu-id="b950a-300">Kiosk mode behavior changes for handling of failures</span></span>

<span data-ttu-id="b950a-301">以前のビルドでは、デバイスにキオスク構成 (グローバル割り当てアクセスと AAD グループ メンバーの割り当てアクセスの両方の組み合わせ) がある場合、AAD グループ メンバーシップの決定に失敗した場合、ユーザーには["スタート](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)" メニューに何も表示されません。</span><span class="sxs-lookup"><span data-stu-id="b950a-301">In older builds, if a device had a kiosk configuration, which is a combination of both global assigned access and AAD group member assigned access, if determining AAD group membership failed, the user would see “[nothing shown in start](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)” menu.</span></span>

<span data-ttu-id="b950a-302">Windows Insider リリースから、キオスク エクスペリエンスは AAD グループ キオスク モード中に障害が発生した場合に、グローバル キオスク構成 (存在する場合) にフォールバックします。</span><span class="sxs-lookup"><span data-stu-id="b950a-302">Starting in Windows Insider release, the kiosk experience will fallback to global kiosk configuration (if present) in case of failures during AAD group kiosk mode.</span></span>

### <span data-ttu-id="b950a-303">設定アプリによるフォールバック診断の構成</span><span class="sxs-lookup"><span data-stu-id="b950a-303">Configuring Fallback Diagnostics via Settings app</span></span>

<span data-ttu-id="b950a-304">設定アプリで、ユーザーはフォールバック診断の動作 [を構成できます](hololens-diagnostic-logs.md)。</span><span class="sxs-lookup"><span data-stu-id="b950a-304">Now in Settings App, a user can configure the behavior of [Fallback Diagnostics](hololens-diagnostic-logs.md).</span></span> <span data-ttu-id="b950a-305">設定アプリで、[プライバシーのトラブルシューティング **] ページ**  ->  **に移動**し、この設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="b950a-305">In the Settings app navigate to **Privacy** -> **Troubleshooting** page to configure this setting.</span></span>

> [!NOTE]
> <span data-ttu-id="b950a-306">デバイスに対して MDM ポリシーが構成されている場合、ユーザーはこの動作を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="b950a-306">If there is MDM policy configured for the device, user will not be able to override that behavior.</span></span>  






## <span data-ttu-id="b950a-307">Insider ビルドの受信の開始</span><span class="sxs-lookup"><span data-stu-id="b950a-307">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="b950a-308">最近更新していない場合は、デバイスを再起動して状態を更新し、最新のビルドを取得してください。</span><span class="sxs-lookup"><span data-stu-id="b950a-308">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="b950a-309">"再起動デバイス" 音声コマンドは正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="b950a-309">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="b950a-310">[設定] /[Windows Insider Program] で再起動ボタンを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="b950a-310">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="b950a-311">発生した可能性があるバック エンドにバグが発生しました。これにより、追跡が可能です。</span><span class="sxs-lookup"><span data-stu-id="b950a-311">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="b950a-312">HoloLens 2 デバイスで、**[設定]** > **[更新とセキュリティ]** > **[Windows Insider Program]** の順に移動し、**[開始する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b950a-312">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="b950a-313">Windows Insider として登録するために使用したアカウントをリンクします。</span><span class="sxs-lookup"><span data-stu-id="b950a-313">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="b950a-314">Windows Insider はチャネルに移行しています。</span><span class="sxs-lookup"><span data-stu-id="b950a-314">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="b950a-315">ファスト**リング**は開発チャネル\*\*\*\* になり、**スロー**リングは**ベータ**チャネルになり、**リリース**プレビュー リングはリリース プレビュー**チャネルになります**。</span><span class="sxs-lookup"><span data-stu-id="b950a-315">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="b950a-316">マッピングは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="b950a-316">Here is what that mapping looks like:</span></span>

![Windows Insider Channels の説明](images/WindowsInsiderChannels.png)

<span data-ttu-id="b950a-318">詳しくは [、Windows ブログの「Windows Insider チャネル](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) の紹介」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b950a-318">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>

<span data-ttu-id="b950a-319">次に **、Windows のアクティブな**開発を選択し、開発チャネルビルドまたは\*\*\*\* ベータ チャネル\*\*\*\* ビルドを受け取るかどうかを選択し、プログラムの条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="b950a-319">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="b950a-320">[ **今すぐ>確認] を選択して** 終了します。</span><span class="sxs-lookup"><span data-stu-id="b950a-320">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="b950a-321">デバイスが再起動したら、[設定] > [更新とセキュリティ] & > **更新** プログラムを確認して最新のビルドを取得します。</span><span class="sxs-lookup"><span data-stu-id="b950a-321">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

### <span data-ttu-id="b950a-322">更新エラー 0x80070490 の回避</span><span class="sxs-lookup"><span data-stu-id="b950a-322">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="b950a-323">Dev または Beta チャネルで更新中に更新エラー 0x80070490 が発生した場合は、次の短期の回避方法を試してください。</span><span class="sxs-lookup"><span data-stu-id="b950a-323">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="b950a-324">Insider チャネルを移動し、更新プログラムを受け取り、Insider チャネルを戻します。</span><span class="sxs-lookup"><span data-stu-id="b950a-324">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>

#### <span data-ttu-id="b950a-325">ステージ 1 - リリース プレビュー</span><span class="sxs-lookup"><span data-stu-id="b950a-325">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="b950a-326">設定, 更新プログラム&セキュリティ, Windows Insider Program, select **Release Preview Channel**.</span><span class="sxs-lookup"><span data-stu-id="b950a-326">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="b950a-327">設定, 更新プログラム&セキュリティ, Windows Update, **更新プログラムの確認**.</span><span class="sxs-lookup"><span data-stu-id="b950a-327">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="b950a-328">更新後、ステージ 2 に進む。</span><span class="sxs-lookup"><span data-stu-id="b950a-328">After the update, continue on to Stage two.</span></span>

#### <span data-ttu-id="b950a-329">ステージ 2 - 開発チャネル</span><span class="sxs-lookup"><span data-stu-id="b950a-329">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="b950a-330">設定, 更新&セキュリティ, Windows Insider Program, select **Dev Channel**.</span><span class="sxs-lookup"><span data-stu-id="b950a-330">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="b950a-331">設定, 更新プログラム&セキュリティ, Windows Update, **更新プログラムの確認**.</span><span class="sxs-lookup"><span data-stu-id="b950a-331">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>

## <span data-ttu-id="b950a-332">FFU のダウンロードとフラッシュの手順</span><span class="sxs-lookup"><span data-stu-id="b950a-332">FFU download and flash directions</span></span>
<span data-ttu-id="b950a-333">フライト署名のある FFU でテストするには、フライト署名のある FFU をフラッシュする前にデバイスのフライト ロックを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b950a-333">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="b950a-334">PC の場合:</span><span class="sxs-lookup"><span data-stu-id="b950a-334">On PC:</span></span>

    1. <span data-ttu-id="b950a-335">Ffu を PC からダウンロードします [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。</span><span class="sxs-lookup"><span data-stu-id="b950a-335">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="b950a-336">Microsoft Store ([https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)) から ARC (Advanced Recovery Companion) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="b950a-336">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span></span>
    
1. <span data-ttu-id="b950a-337">HoloLens で - [フライトのロック解除]: **Windows**Insider Program &設定の更新を開き、  >  \*\*\*\*  >  \*\*\*\* デバイスを再起動してサインアップします。</span><span class="sxs-lookup"><span data-stu-id="b950a-337">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="b950a-338">フラッシュ FFU - ARC を使用してフライト署名された FFU をフラッシュできます。</span><span class="sxs-lookup"><span data-stu-id="b950a-338">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

## <span data-ttu-id="b950a-339">フィードバックを提供し、問題を報告する</span><span class="sxs-lookup"><span data-stu-id="b950a-339">Provide feedback and report issues</span></span>

<span data-ttu-id="b950a-340">HoloLens で[フィードバック Hub アプリ](hololens-feedback.md)を使用してフィードバックを提供し、問題を報告することができます。</span><span class="sxs-lookup"><span data-stu-id="b950a-340">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="b950a-341">フィードバック Hub を使用すると、エンジニアが問題を迅速にデバッグして解決するのに役立つすべての必要な診断情報が含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="b950a-341">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="b950a-342">中国語および日本語版の HoloLens に関する問題は、同じ方法で報告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b950a-342">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="b950a-343">フィードバック Hub を使用してドキュメント フォルダーにアクセスするかどうかを確認するプロンプトに必ず同意してください (メッセージが表示されたら **[はい]** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="b950a-343">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="b950a-344">開発者向けの注意事項</span><span class="sxs-lookup"><span data-stu-id="b950a-344">Note for developers</span></span>

<span data-ttu-id="b950a-345">HoloLens の Insider ビルドを使用して自由にアプリケーションを開発してみることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b950a-345">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="b950a-346">作業を始めるには、[HoloLens 開発者向けドキュメント](https://developer.microsoft.com/windows/mixed-reality/development)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b950a-346">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="b950a-347">これらの同じ手順は HoloLens の Insider ビルドでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="b950a-347">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="b950a-348">HoloLens 開発用に使用しているものと同じビルドの Unity と Visual Studio を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b950a-348">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <span data-ttu-id="b950a-349">Insider ビルドの受信の停止</span><span class="sxs-lookup"><span data-stu-id="b950a-349">Stop receiving Insider builds</span></span>

<span data-ttu-id="b950a-350">Windows Holographic の Insider ビルドを受け取りたくない場合は、HoloLens が製品版ビルドを実行しているときにオプトアウトすることができます。または、Advanced Recovery Companion を使用して[デバイスを回復](hololens-recovery.md)し、Windows Holographic の Insider バージョン以外にデバイスを回復することができます。</span><span class="sxs-lookup"><span data-stu-id="b950a-350">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="b950a-351">新しいプレビュー ビルドを手動で再インストールした後に Insider Preview ビルドの登録を解除すると、ブルー スクリーンが発生するという既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="b950a-351">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="b950a-352">その後、手動でデバイスを回復する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b950a-352">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="b950a-353">影響を受けるかどうかの詳細については、この[既知の問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)の詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b950a-353">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="b950a-354">HoloLens が製品版ビルドを実行していることを確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b950a-354">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="b950a-355">**[設定] > [システム] > [バージョン情報]** の順に移動し、ビルド番号を探します。</span><span class="sxs-lookup"><span data-stu-id="b950a-355">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="b950a-356">[実稼働ビルド番号のリリース ノートを参照してください](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="b950a-356">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="b950a-357">Insider ビルドをオプトアウトするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b950a-357">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="b950a-358">製品版ビルドを実行している HoloLens で、**[設定] > [更新とセキュリティ] > [Windows Insider Program]** に移動して、**[Insider Preview ビルドの停止]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b950a-358">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="b950a-359">画面の指示に従って、デバイスでの受信を停止します。</span><span class="sxs-lookup"><span data-stu-id="b950a-359">Follow the instructions to opt out your device.</span></span>
