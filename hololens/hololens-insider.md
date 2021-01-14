---
title: Microsoft HoloLens の Insider Preview
description: 簡単に Insider ビルドを使い始めて、HoloLens の次の主要なオペレーティング システムの更新プログラムに対する貴重なフィードバックをご提供いただけます。
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
ms.date: 1/13/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 06c3faf573adabe158a72a66fc4b8a45afec48fb
ms.sourcegitcommit: e26aa9059a7d8e73914205e80a89ea9637926e74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2021
ms.locfileid: "11269398"
---
# <span data-ttu-id="6177d-103">Microsoft HoloLens の Insider Preview</span><span class="sxs-lookup"><span data-stu-id="6177d-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="6177d-104">HoloLens 用の最新の Insider Preview ビルドへようこそ!</span><span class="sxs-lookup"><span data-stu-id="6177d-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="6177d-105">HoloLens [の次](hololens-insider.md#start-receiving-insider-builds) の主要なオペレーティング システム更新プログラムの使用を開始し、貴重なフィードバックを提供する方法は簡単です。</span><span class="sxs-lookup"><span data-stu-id="6177d-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <span data-ttu-id="6177d-106">Windows Insider リリース ノート</span><span class="sxs-lookup"><span data-stu-id="6177d-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="6177d-107">Windows Insider の新機能のフライトを再び開始します。</span><span class="sxs-lookup"><span data-stu-id="6177d-107">We are excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="6177d-108">We will be flighting to the Dev Channel for the latest updates.</span><span class="sxs-lookup"><span data-stu-id="6177d-108">We will be flighting to the Dev Channel for the latest updates.</span></span> <span data-ttu-id="6177d-109">このページは、Windows Insider ビルドに追加された機能と更新プログラムが追加され、引き続き更新されます。</span><span class="sxs-lookup"><span data-stu-id="6177d-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span>  <span data-ttu-id="6177d-110">これらの更新プログラムを実際に組み合わせ、準備を整えます。</span><span class="sxs-lookup"><span data-stu-id="6177d-110">Get excited and ready to mix these updates into your reality.</span></span> 

| <span data-ttu-id="6177d-111">機能名</span><span class="sxs-lookup"><span data-stu-id="6177d-111">Feature Name</span></span>                                              | <span data-ttu-id="6177d-112">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="6177d-112">Short description</span></span>                                                                      | <span data-ttu-id="6177d-113">ビルドで使用可能</span><span class="sxs-lookup"><span data-stu-id="6177d-113">Available in build</span></span> |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [<span data-ttu-id="6177d-114">新しい Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6177d-114">New Microsoft Edge</span></span>](#introducing-the-new-microsoft-edge) | <span data-ttu-id="6177d-115">HoloLens 2 で、Chromium ベースの新しい Microsoft Edge を利用できる</span><span class="sxs-lookup"><span data-stu-id="6177d-115">The new, Chromium-based Microsoft Edge is now available for HoloLens 2</span></span>                         | <span data-ttu-id="6177d-116">20279.1006</span><span class="sxs-lookup"><span data-stu-id="6177d-116">20279.1006</span></span> |
| [<span data-ttu-id="6177d-117">新しい設定アプリ</span><span class="sxs-lookup"><span data-stu-id="6177d-117">New Settings app</span></span>](#new-settings-app)                     | <span data-ttu-id="6177d-118">従来の設定アプリは、新しい機能と設定で更新されたバージョンに置き換えられる</span><span class="sxs-lookup"><span data-stu-id="6177d-118">The legacy Settings app is being replaced by an updated version with new features and settings</span></span> | <span data-ttu-id="6177d-119">20279.1006</span><span class="sxs-lookup"><span data-stu-id="6177d-119">20279.1006</span></span> |
| [<span data-ttu-id="6177d-120">既定のアプリ ピッカー</span><span class="sxs-lookup"><span data-stu-id="6177d-120">Default app picker</span></span>](#default-app-picker)                 | <span data-ttu-id="6177d-121">ファイルまたはリンクの種類ごとに起動するアプリを選択する</span><span class="sxs-lookup"><span data-stu-id="6177d-121">Choose which app should launch for each file or link type</span></span>                                      | <span data-ttu-id="6177d-122">20279.1006</span><span class="sxs-lookup"><span data-stu-id="6177d-122">20279.1006</span></span> |
| [<span data-ttu-id="6177d-123">Office Web アプリ</span><span class="sxs-lookup"><span data-stu-id="6177d-123">Office web app</span></span>](#office-web-app)                         | <span data-ttu-id="6177d-124">新しい Web アプリOfficeが [すべてのアプリ] に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6177d-124">A shortcut to the Office web app is now listed in "All apps"</span></span>                                   | <span data-ttu-id="6177d-125">20279.1006</span><span class="sxs-lookup"><span data-stu-id="6177d-125">20279.1006</span></span> |
| [<span data-ttu-id="6177d-126">スワイプして入力する</span><span class="sxs-lookup"><span data-stu-id="6177d-126">Swipe to type</span></span>](#swipe-to-type)                           | <span data-ttu-id="6177d-127">ホログラフィック キーボードで指のヒントを使って単語を "スワイプ" する</span><span class="sxs-lookup"><span data-stu-id="6177d-127">Use the tip of your finger to "swipe" words on the holographic keyboard</span></span>                        | <span data-ttu-id="6177d-128">20279.1006</span><span class="sxs-lookup"><span data-stu-id="6177d-128">20279.1006</span></span> |

### <span data-ttu-id="6177d-129">新しい Microsoft Edge の導入</span><span class="sxs-lookup"><span data-stu-id="6177d-129">Introducing the new Microsoft Edge</span></span>

![従来の Microsoft Edge ロゴから新しい Microsoft Edge ロゴへのアニメーション](images/new-edge.gif)

<span data-ttu-id="6177d-131">新しい Microsoft Edge は [Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) オープン ソース プロジェクトを採用して、お客様との互換性を向上し、Web 開発者向けの Web の断片化を減らします。</span><span class="sxs-lookup"><span data-stu-id="6177d-131">The new Microsoft Edge [adopts the Chromium open source project](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) to create better compatibility for customers and less fragmentation of the web for web developers.</span></span> 

<span data-ttu-id="6177d-132">この Insider プレビューでは、HoloLens 2 のお客様が新しい Microsoft Edge を初めて利用できます。</span><span class="sxs-lookup"><span data-stu-id="6177d-132">With this Insider preview, the new Microsoft Edge is available to HoloLens 2 customers for the first time!</span></span> <span data-ttu-id="6177d-133">新しい Microsoft Edge は最終的に HoloLens 2 の従来の Microsoft Edge に取って代わる機能ですが、現在、両方のブラウザーが Insider で利用できます。</span><span class="sxs-lookup"><span data-stu-id="6177d-133">While the new Microsoft Edge will eventually replace legacy Microsoft Edge on HoloLens 2, both browsers are currently available to Insiders.</span></span> <span data-ttu-id="6177d-134">新しい Microsoft Edge のフィードバック送信\*\*\*\* 機能またはフィードバック Hub を介して、フィードバックやバグをチームと[共有してください](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="6177d-134">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge or via [Feedback Hub](hololens-feedback.md).</span></span>

![新しい Microsoft Edge のスクリーンショット](images/new-edge-ui.png)

#### <span data-ttu-id="6177d-136">新しい Microsoft Edge の起動</span><span class="sxs-lookup"><span data-stu-id="6177d-136">Launching the new Microsoft Edge</span></span>

<span data-ttu-id="6177d-137">Insider が利用できる Microsoft Edge には、新しい Microsoft Edge の新しい Microsoft Edge アイコン (青と緑のスループ アイコンで表される) と従来の Microsoft Edge (白い ![ "e" アイコンで表される) の 2 つのバージョンがあります。 ](images/new_edge_logo.png)</span><span class="sxs-lookup"><span data-stu-id="6177d-137">There are two versions of Microsoft Edge available to Insiders: the new Microsoft Edge ![new Microsoft Edge icon](images/new_edge_logo.png) (represented by a blue and green swirl icon) and the legacy Microsoft Edge (represented by the white "e" icon).</span></span> <span data-ttu-id="6177d-138">新しい Microsoft Edge はスタート メニューにピン留めされ、Web リンクをアクティブ化すると自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="6177d-138">The new Microsoft Edge is pinned to the Start menu and will automatically launch when you activate a web link.</span></span> <span data-ttu-id="6177d-139">従来の Microsoft Edge を既定の Web ブラウザーとして使用する場合は、以下の手順を参照して既定のアプリを [リセットしてください](#default-app-picker)。</span><span class="sxs-lookup"><span data-stu-id="6177d-139">If you would like to revert to using legacy Microsoft Edge as your default web browser, see the instructions below for [resetting default apps](#default-app-picker).</span></span>

> [!NOTE]
> <span data-ttu-id="6177d-140">HoloLens 2 で新しい Microsoft Edge を初めて起動すると、設定とデータは従来の Microsoft Edge からインポートされます。</span><span class="sxs-lookup"><span data-stu-id="6177d-140">When you first launch the new Microsoft Edge on HoloLens 2, your settings and data will be imported from legacy Microsoft Edge.</span></span> <span data-ttu-id="6177d-141">新しい Microsoft Edge を起動した後も従来の Microsoft Edge を使用し続ける場合、その新しいデータは従来の Microsoft Edge から新しい Microsoft Edge に同期されません。</span><span class="sxs-lookup"><span data-stu-id="6177d-141">If you continue to use legacy Microsoft Edge after launching the new Microsoft Edge, that new data will not be synced from legacy Microsoft Edge to the new Microsoft Edge.</span></span>

#### <span data-ttu-id="6177d-142">新しい Microsoft Edge のポリシー設定の構成</span><span class="sxs-lookup"><span data-stu-id="6177d-142">Configuring policy settings for the new Microsoft Edge</span></span>

<span data-ttu-id="6177d-143">新しい Microsoft Edge は、従来の Microsoft Edge で提供していたよりも、HoloLens 2 のブラウザー ポリシーの広範なセットを IT プロに提供します。</span><span class="sxs-lookup"><span data-stu-id="6177d-143">The new Microsoft Edge offers IT Pros a much broader set of browser policies on HoloLens 2 than were previously available with legacy Microsoft Edge.</span></span> 

<span data-ttu-id="6177d-144">新しい Microsoft Edge のポリシー設定の管理について詳しく知る上で役立つリソースを次に示します。</span><span class="sxs-lookup"><span data-stu-id="6177d-144">Here are some helpful resources for learning more about managing policy settings for the new Microsoft Edge:</span></span>
- [<span data-ttu-id="6177d-145">Microsoft Intune を使って Microsoft Edge ポリシー設定を構成する</span><span class="sxs-lookup"><span data-stu-id="6177d-145">Configure Microsoft Edge policy settings with Microsoft Intune</span></span>](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [<span data-ttu-id="6177d-146">Microsoft Edge Legacy から Microsoft Edge ポリシーへのマッピング</span><span class="sxs-lookup"><span data-stu-id="6177d-146">Microsoft Edge Legacy to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [<span data-ttu-id="6177d-147">Google Chrome から Microsoft Edge ポリシーへのマッピング</span><span class="sxs-lookup"><span data-stu-id="6177d-147">Google Chrome to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- <span data-ttu-id="6177d-148">[Microsoft Edge Enterprise の完全なドキュメント](https://docs.microsoft.com/deployedge/)</span><span class="sxs-lookup"><span data-stu-id="6177d-148">Full [Microsoft Edge Enterprise documentation](https://docs.microsoft.com/deployedge/)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6177d-149">新しい Microsoft Edge でサポートされているブラウザー ポリシーの量が多いので、新しい各ポリシーが HoloLens 2 で動作するとは、チームは保証できません。</span><span class="sxs-lookup"><span data-stu-id="6177d-149">Because of the volume of browser policies supported by the new Microsoft Edge, our team is unable to guarantee that each new policy works on HoloLens 2.</span></span> <span data-ttu-id="6177d-150">ただし、HoloLens 2 で以前サポートされた従来の各 Microsoft Edge ポリシーと同等の新しい Microsoft Edge が期待通り動作するテストを行い、確認しました。</span><span class="sxs-lookup"><span data-stu-id="6177d-150">However, we've tested and confirmed that the new Microsoft Edge equivalent of each legacy Microsoft Edge policy previously supported on HoloLens 2 work as expected.</span></span> <span data-ttu-id="6177d-151">HoloLens 2 で使用していた従来の各 Microsoft Edge ブラウザー ポリシーと同等の新しい Microsoft Edge を見つけるには [、Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) レガシから Microsoft Edge へのポリシー マッピングをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6177d-151">See [Microsoft Edge Legacy to Microsoft Edge policy mapping](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) to find the new Microsoft Edge equivalent of each legacy Microsoft Edge browser policy you were using with HoloLens 2.</span></span>
>
> <span data-ttu-id="6177d-152">HoloLens 2 では動作しない新しい\*\* Microsoft Edge ポリシーが 2 つ以上あります。</span><span class="sxs-lookup"><span data-stu-id="6177d-152">There are at least two new Microsoft Edge policies that we know *will not* work with HoloLens 2:</span></span>
> - <span data-ttu-id="6177d-153">EnterpriseModeSiteList</span><span class="sxs-lookup"><span data-stu-id="6177d-153">EnterpriseModeSiteList</span></span>
> - <span data-ttu-id="6177d-154">EnterpriseSiteListServiceURL</span><span class="sxs-lookup"><span data-stu-id="6177d-154">EnterpriseSiteListServiceURL</span></span>

#### <span data-ttu-id="6177d-155">HoloLens 2 の新しい Microsoft Edge に期待される機能</span><span class="sxs-lookup"><span data-stu-id="6177d-155">What to expect from the new Microsoft Edge on HoloLens 2</span></span>

<span data-ttu-id="6177d-156">新しい Microsoft Edge は、新しい UWP アダプター レイヤーを使ったネイティブの Win32 アプリで、HoloLens 2 のような UWP 専用デバイスで実行することができるため、一部の機能はすぐに利用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="6177d-156">Because the new Microsoft Edge is a native Win32 app with a new UWP adapter layer allowing it to run on UWP-only devices like HoloLens 2, some features may not be immediately available.</span></span> <span data-ttu-id="6177d-157">今後数か月の間に新しいシナリオと機能をサポートする予定なので、このスペースで最新の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="6177d-157">We'll be supporting new scenarios and features over the coming months, so please check this space for up-to-date information.</span></span>

**<span data-ttu-id="6177d-158">動作が予想されるシナリオと機能:</span><span class="sxs-lookup"><span data-stu-id="6177d-158">Scenarios and features expected to work:</span></span>**
- <span data-ttu-id="6177d-159">初回実行エクスペリエンス、プロファイルへのサインイン、同期</span><span class="sxs-lookup"><span data-stu-id="6177d-159">First-run experience, sign-in to profile, and sync</span></span>
- <span data-ttu-id="6177d-160">Web サイトが期待どおりにレンダリングされ、動作する必要がある</span><span class="sxs-lookup"><span data-stu-id="6177d-160">Websites should render and behave as expected</span></span>
- <span data-ttu-id="6177d-161">ほとんどのブラウザー機能 (お気に入り、履歴など) は期待通りに動作する必要があります</span><span class="sxs-lookup"><span data-stu-id="6177d-161">Most browser functionality (Favorites, History, etc.) should work as expected</span></span>
- <span data-ttu-id="6177d-162">濃色モード</span><span class="sxs-lookup"><span data-stu-id="6177d-162">Dark mode</span></span>
- <span data-ttu-id="6177d-163">デバイスへの Web アプリのインストール</span><span class="sxs-lookup"><span data-stu-id="6177d-163">Installing web apps to the device</span></span>
- <span data-ttu-id="6177d-164">拡張機能のインストール (HoloLens 2 で正しく動作しない拡張機能を使用している場合は、お知らせください)</span><span class="sxs-lookup"><span data-stu-id="6177d-164">Installing extensions (please let us know if you use any extensions that don't work properly on HoloLens 2)</span></span>
- <span data-ttu-id="6177d-165">PDF の表示とマーキング</span><span class="sxs-lookup"><span data-stu-id="6177d-165">Viewing and marking up a PDF</span></span>
- <span data-ttu-id="6177d-166">1 つのブラウザー ウィンドウからの空間サウンド</span><span class="sxs-lookup"><span data-stu-id="6177d-166">Spatial sound from a single browser window</span></span>
- <span data-ttu-id="6177d-167">ブラウザーの自動更新と手動更新</span><span class="sxs-lookup"><span data-stu-id="6177d-167">Automatic and manual updating of the browser</span></span>
- <span data-ttu-id="6177d-168">[印刷] メニューから PDF を保存する ([PDF に保存] オプションを使用)</span><span class="sxs-lookup"><span data-stu-id="6177d-168">Saving a PDF from the Print menu (using "Save to PDF" option)</span></span>

**<span data-ttu-id="6177d-169">近日公開予定のシナリオと機能:</span><span class="sxs-lookup"><span data-stu-id="6177d-169">Scenarios and features coming soon:</span></span>**
- <span data-ttu-id="6177d-170">WebXR と 360 ビューアー拡張機能</span><span class="sxs-lookup"><span data-stu-id="6177d-170">WebXR and 360 Viewer extension</span></span>
- <span data-ttu-id="6177d-171">環境内に配置された複数のウィンドウを閲覧する場合の正しいウィンドウに対するコンテンツの復元</span><span class="sxs-lookup"><span data-stu-id="6177d-171">Content restoration to correct window when browsing across multiple windows placed in your environment</span></span>
- <span data-ttu-id="6177d-172">同時オーディオ ストリームを使用する複数のウィンドウの空間サウンド</span><span class="sxs-lookup"><span data-stu-id="6177d-172">Spatial sound for multiple windows with simultaneous audio streams</span></span>
- <span data-ttu-id="6177d-173">ビデオ、Mixed Reality キャプチャ、または画面共有を使用してブラウザー経由で Microsoft Teams 通話に参加する (通話とオーディオの参加がうまく機能)</span><span class="sxs-lookup"><span data-stu-id="6177d-173">Joining a Microsoft Teams call via the browser with video, mixed reality capture, or screen-sharing (joining calls with audio works well)</span></span>
- <span data-ttu-id="6177d-174">"見て、言ってみる"</span><span class="sxs-lookup"><span data-stu-id="6177d-174">"See it, say it"</span></span>
- <span data-ttu-id="6177d-175">印刷</span><span class="sxs-lookup"><span data-stu-id="6177d-175">Printing</span></span>

**<span data-ttu-id="6177d-176">既知のブラウザーの問題の上位:</span><span class="sxs-lookup"><span data-stu-id="6177d-176">Top known browser issues:</span></span>**
- <span data-ttu-id="6177d-177">デバイスをリセットすると、新しい Microsoft Edge が削除されます。</span><span class="sxs-lookup"><span data-stu-id="6177d-177">Resetting your device will remove the new Microsoft Edge</span></span>
- <span data-ttu-id="6177d-178">ホログラフィック キーボードの拡大鏡のプレビューに誤ったコンテンツが表示される</span><span class="sxs-lookup"><span data-stu-id="6177d-178">The magnifier preview in the holographic keyboard shows incorrect content</span></span>

### <span data-ttu-id="6177d-179">新しい設定アプリ</span><span class="sxs-lookup"><span data-stu-id="6177d-179">New Settings app</span></span>

<span data-ttu-id="6177d-180">このリリースでは、設定アプリの新しいバージョンが導入されています。</span><span class="sxs-lookup"><span data-stu-id="6177d-180">With this release, we're introducing a new version of the Settings app.</span></span> <span data-ttu-id="6177d-181">新しい設定アプリには、入力/出力オーディオ デバイス、個々のアプリのボリューム、電源とスリープ、イーサネット アダプター、簡単操作、フライト モード、既定のアプリなど、HoloLens 2 の新機能と拡張された設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6177d-181">The new Settings app includes new features and expanded settings for HoloLens 2 in the following areas: input/output audio devices, individual app volume, power and sleep, Ethernet adapter, Ease of Access, airplane mode, and default apps.</span></span>

> [!NOTE]
> <span data-ttu-id="6177d-182">新しい設定アプリは従来の設定アプリとは異なっているので、以前環境の周囲に配置した設定ウィンドウは、更新時に削除されます。</span><span class="sxs-lookup"><span data-stu-id="6177d-182">Because the new Settings app is distinct from the legacy Settings app, any Settings windows you previously placed around your environment will be removed upon update.</span></span>

![新しい設定アプリのホーム ページ](images/new-settings-app.png)

**<span data-ttu-id="6177d-184">新機能と設定</span><span class="sxs-lookup"><span data-stu-id="6177d-184">New features and settings</span></span>**
- <span data-ttu-id="6177d-185">設定検索: キーワードまたは設定名を使用して設定ホーム ページから設定を検索する</span><span class="sxs-lookup"><span data-stu-id="6177d-185">Settings search: search for settings from the Settings homepage using keywords or the setting's name</span></span>
- <span data-ttu-id="6177d-186">サウンド:</span><span class="sxs-lookup"><span data-stu-id="6177d-186">Sound:</span></span>
  - <span data-ttu-id="6177d-187">入力オーディオ デバイスと出力オーディオ デバイス: 入力オーディオ デバイスと出力オーディオ デバイスを個別に選択します (たとえば、Bluetooth ヘッドホンでオーディオを聞く場合や、オーディオ入力に USB-C マイクを使用する場合など)。</span><span class="sxs-lookup"><span data-stu-id="6177d-187">Input and output audio devices: independently choose your input and output audio devices (for example, listen to audio via Bluetooth headphones or use a USB-C microphone for audio input).</span></span> <span data-ttu-id="6177d-188">注: Bluetooth HoloLens 2 ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6177d-188">Note: Bluetooth microphones are not supported by HoloLens 2.</span></span>
  - <span data-ttu-id="6177d-189">アプリのボリューム: 各アプリのボリュームを個別に調整する</span><span class="sxs-lookup"><span data-stu-id="6177d-189">App volume: independently adjust the volume of each app</span></span>
- <span data-ttu-id="6177d-190">バッテリー 節約機能: バッテリー節約機能モードを手動で有効にするか、バッテリー節約機能モードが自動的に有効になる時点でバッテリーしきい値を設定する</span><span class="sxs-lookup"><span data-stu-id="6177d-190">Battery saver: manually enable battery saver mode or set a battery threshold at which point battery saver mode turns on automatically</span></span>
- <span data-ttu-id="6177d-191">電源&スリープ: 非アクティブな状態が一時間続くとデバイスをスリープ状態にすべき時期を選択する</span><span class="sxs-lookup"><span data-stu-id="6177d-191">Power & sleep: choose when the device should go to sleep after a period of inactivity</span></span>
- <span data-ttu-id="6177d-192">USB: 既定では USB 接続を無効にできます</span><span class="sxs-lookup"><span data-stu-id="6177d-192">USB: you can disable USB connections by default</span></span>
- <span data-ttu-id="6177d-193">ネットワーク & インターネット:</span><span class="sxs-lookup"><span data-stu-id="6177d-193">Network & Internet:</span></span>
  - <span data-ttu-id="6177d-194">USB-C イーサネット アダプターは、ネットワーク ネットワーク とインターネット&されます。</span><span class="sxs-lookup"><span data-stu-id="6177d-194">USB-C Ethernet adapters will now appear in Network & Internet</span></span>
  - <span data-ttu-id="6177d-195">USB-C イーサネット アダプターの設定 (IP アドレスを含む) が使用可能に</span><span class="sxs-lookup"><span data-stu-id="6177d-195">USB-C Ethernet adapter settings are now available, including its IP address</span></span>
  - <span data-ttu-id="6177d-196">HoloLens 2 でフライト モードを有効にできる</span><span class="sxs-lookup"><span data-stu-id="6177d-196">You can now enable airplane mode on HoloLens 2</span></span>
- <span data-ttu-id="6177d-197">アプリ: ファイルとリンクの種類に使用する既定のアプリをリセットできます。</span><span class="sxs-lookup"><span data-stu-id="6177d-197">Apps: you can reset the default apps used for file and link types.</span></span> <span data-ttu-id="6177d-198">詳 [しくは、「既定のアプリ ピッカー](#default-app-picker) 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6177d-198">See [Default app picker](#default-app-picker) for more information.</span></span>
- <span data-ttu-id="6177d-199">簡単操作: テキスト サイズと視覚効果を変更する</span><span class="sxs-lookup"><span data-stu-id="6177d-199">Ease of Access: change text size and some visual effects</span></span>

**<span data-ttu-id="6177d-200">既知の問題</span><span class="sxs-lookup"><span data-stu-id="6177d-200">Known issues</span></span>**
- <span data-ttu-id="6177d-201">以前に配置した設定ウィンドウは削除されます (上記の注を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="6177d-201">Previously placed Settings windows will be removed (see note above)</span></span>
- <span data-ttu-id="6177d-202">[通知] ページにアクセスすると、設定アプリがクラッシュする可能性があります (調査中)</span><span class="sxs-lookup"><span data-stu-id="6177d-202">Visiting the Notifications page may crash the Settings app (investigating)</span></span>
- <span data-ttu-id="6177d-203">現在イーサネット ページが表示されていない (間もなく修正される予定)</span><span class="sxs-lookup"><span data-stu-id="6177d-203">The Ethernet page currently doesn't show up (to be fixed soon)</span></span>
- <span data-ttu-id="6177d-204">新しい Microsoft Edge のバッテリー使用量は、UWP アダプター レイヤーでサポートされる Win32 デスクトップ アプリケーションとしての性質上、正確ではない可能性があります (間もなく修正される予定はありません)</span><span class="sxs-lookup"><span data-stu-id="6177d-204">Battery usage for the new Microsoft Edge may not be accurate, due to its nature as a Win32 desktop application supported by a UWP adapter layer (no fix anticipated soon)</span></span>

### <span data-ttu-id="6177d-205">既定のアプリ ピッカー</span><span class="sxs-lookup"><span data-stu-id="6177d-205">Default app picker</span></span>

<span data-ttu-id="6177d-206">ハイパーリンクをアクティブにするか、複数のインストール済みアプリをサポートするファイルの種類を開いた場合は、新しいウィンドウが開き、ファイルまたはリンクの種類を処理するインストール済みアプリを選択するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6177d-206">When you activate a hyperlink or open a file type with more than one installed app which supports it, you will see a new window open prompting you to select which installed app should handle the file or link type.</span></span> <span data-ttu-id="6177d-207">このウィンドウでは、選択したアプリでファイルまたはリンクの種類として "Once" または "Always" を処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="6177d-207">In this window you can also choose to have the selected app handle the file or link type "Once" or "Always."</span></span> 

![アプリ ピッカー ウィンドウ](images/default-app-picker.png)

<span data-ttu-id="6177d-209">If you choose "Always" but later want to change which app handles a particular file or link type, you can reset your saved defaults in **Settings > Apps**.</span><span class="sxs-lookup"><span data-stu-id="6177d-209">If you choose "Always" but later want to change which app handles a particular file or link type, you can reset your saved defaults in **Settings > Apps**.</span></span> <span data-ttu-id="6177d-210">ページの下部までスクロールし、[ファイルの種類\*\*\*\* 用の既定のアプリ] または [リンクの種類用の既定のアプリ] の下にある [クリア] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="6177d-210">Scroll to the bottom of the page and select the **Clear** button under "Default apps for file types" and/or "Default apps for link types."</span></span> <span data-ttu-id="6177d-211">デスクトップ PC の同様の設定とは異なり、個々のファイルの種類の既定値をリセットできます。</span><span class="sxs-lookup"><span data-stu-id="6177d-211">Unlike the similar setting on desktop PCs, you can't reset individual file type defaults.</span></span>

### <span data-ttu-id="6177d-212">Office Web アプリ</span><span class="sxs-lookup"><span data-stu-id="6177d-212">Office web app</span></span>

<span data-ttu-id="6177d-213">スタート Officeの [すべてのアプリ] の一覧に、新しい Web アプリが追加されました。</span><span class="sxs-lookup"><span data-stu-id="6177d-213">The Office web app has been added to the "All apps" list in the Start menu.</span></span> <span data-ttu-id="6177d-214">この Web アプリは、スタート画面にピン留めしたりアンインストールしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6177d-214">This web app can also be pinned to Start or uninstalled.</span></span> <span data-ttu-id="6177d-215">これは Web アプリなので、その機能はアクセスして体験した機能と正確に一致します https://www.office.com 。</span><span class="sxs-lookup"><span data-stu-id="6177d-215">Because this is a web app, its functionality matches exactly what you'd experience by visiting https://www.office.com.</span></span> <span data-ttu-id="6177d-216">Office Web アプリの機能は、HoloLens 2 にアクティブなインターネット接続がある場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6177d-216">Office web app functionality is only available when your HoloLens 2 has an active internet connection.</span></span>

### <span data-ttu-id="6177d-217">スワイプして入力する</span><span class="sxs-lookup"><span data-stu-id="6177d-217">Swipe to type</span></span>

<span data-ttu-id="6177d-218">一部のお客様は、入力する単語の形をスワイプすることで仮想キーボードを "入力" する方が速く見つかり、ホログラフィック キーボード用にこの機能をプレビューします。</span><span class="sxs-lookup"><span data-stu-id="6177d-218">Some customers find it faster to "type" on virtual keyboards by swiping the shape of the word they intend to type, and we're previewing this feature for the holographic keyboard.</span></span> <span data-ttu-id="6177d-219">ホログラフィック キーボードの平面を指の先端を通して一度に 1 つの単語をスワイプし、単語の形状をスワイプし、キーボードの平面から指の先端を引き出します。</span><span class="sxs-lookup"><span data-stu-id="6177d-219">You can swipe one word at a time by passing the tip of your finger through the plane of the holographic keyboard, swiping the shape of the word, and then withdrawing the tip of your finger from the plane of the keyboard.</span></span> <span data-ttu-id="6177d-220">単語間でキーボードから指を外して Space キーを押す必要なく、フォローアップ語をスワイプできます。</span><span class="sxs-lookup"><span data-stu-id="6177d-220">You can swipe follow-up words without needing to press the spacebar by removing your finger from the keyboard between words.</span></span> <span data-ttu-id="6177d-221">キーボードで指が動いた後にスワイプ の証跡が表示される場合は、この機能が動作しているのが分かっています。</span><span class="sxs-lookup"><span data-stu-id="6177d-221">You will know the feature is working if you see a swipe trail following your finger's movement on the keyboard.</span></span>

<span data-ttu-id="6177d-222">この機能は、(携帯電話のディスプレイとは異なり) 指に抵抗を感じないホログラフィック キーボードの性質上、使い方が難しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="6177d-222">Please note, this feature can be tricky to use and master because of the nature of a holographic keyboard where you don't feel resistance against your finger (unlike a mobile phone display).</span></span> <span data-ttu-id="6177d-223">この機能は一般リリース向けとして評価されています。そのため、お客様からのフィードバックは重要です。この機能が役に立つ場合も、構築的なフィードバックがある場合も、フィードバック Hub でお知 [らせください](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="6177d-223">We are evaluating this feature for public release, so your feedback is important; whether you find the feature useful or you have constructive feedback, please let us know via [Feedback Hub](hololens-feedback.md).</span></span>





## <span data-ttu-id="6177d-224">Insider ビルドの受信の開始</span><span class="sxs-lookup"><span data-stu-id="6177d-224">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="6177d-225">最近更新していない場合は、デバイスを再起動して状態を更新し、最新のビルドを取得してください。</span><span class="sxs-lookup"><span data-stu-id="6177d-225">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="6177d-226">"再起動デバイス" 音声コマンドは正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="6177d-226">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="6177d-227">[設定] /[Windows Insider Program] で再起動ボタンを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="6177d-227">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="6177d-228">発生した可能性があるバック エンドにバグが発生しました。これにより、追跡が可能です。</span><span class="sxs-lookup"><span data-stu-id="6177d-228">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="6177d-229">HoloLens 2 デバイスで、**[設定]** > **[更新とセキュリティ]** > **[Windows Insider Program]** の順に移動し、**[開始する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6177d-229">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="6177d-230">Windows Insider として登録するために使用したアカウントをリンクします。</span><span class="sxs-lookup"><span data-stu-id="6177d-230">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="6177d-231">Windows Insider はチャネルに移行しています。</span><span class="sxs-lookup"><span data-stu-id="6177d-231">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="6177d-232">ファスト**リング**は開発チャネル\*\*\*\* になり、**スロー**リングは**ベータ**チャネルになり、**リリース**プレビュー リングはリリース プレビュー**チャネルになります**。</span><span class="sxs-lookup"><span data-stu-id="6177d-232">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="6177d-233">マッピングは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="6177d-233">Here is what that mapping looks like:</span></span>

![Windows Insider チャネルの説明](images/WindowsInsiderChannels.png)

<span data-ttu-id="6177d-235">詳しくは [、Windows ブログの「Windows Insider チャネル](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) の紹介」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6177d-235">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>

<span data-ttu-id="6177d-236">次に **、Windows のアクティブな**開発を選択し、開発チャネルビルドまたは\*\*\*\* ベータ チャネル\*\*\*\* ビルドを受け取るかどうかを選択し、プログラムの条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="6177d-236">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="6177d-237">[ **Confirm > Restart Now]** を選び、完了します。</span><span class="sxs-lookup"><span data-stu-id="6177d-237">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="6177d-238">デバイスが再起動したら、[設定] > [更新とセキュリティ&] > **最新** のビルドを取得するための更新プログラムを確認する] に移動します。</span><span class="sxs-lookup"><span data-stu-id="6177d-238">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

## <span data-ttu-id="6177d-239">FFU のダウンロードとフラッシュの手順</span><span class="sxs-lookup"><span data-stu-id="6177d-239">FFU download and flash directions</span></span>
<span data-ttu-id="6177d-240">フライト署名のある FFU でテストするには、フライト署名のある FFU をフラッシュする前にデバイスのフライト ロックを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6177d-240">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="6177d-241">PC の場合:</span><span class="sxs-lookup"><span data-stu-id="6177d-241">On PC:</span></span>

    1. <span data-ttu-id="6177d-242">Ffu を PC からダウンロードします [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。</span><span class="sxs-lookup"><span data-stu-id="6177d-242">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="6177d-243">Microsoft Store ([https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)) から ARC (Advanced Recovery Companion) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="6177d-243">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span></span>
    
1. <span data-ttu-id="6177d-244">HoloLens で - [フライトのロック解除]: **Windows**Insider Program &設定の更新を開き、  >  \*\*\*\*  >  \*\*\*\* デバイスを再起動してサインアップします。</span><span class="sxs-lookup"><span data-stu-id="6177d-244">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="6177d-245">フラッシュ FFU - ARC を使用してフライト署名された FFU をフラッシュできます。</span><span class="sxs-lookup"><span data-stu-id="6177d-245">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

## <span data-ttu-id="6177d-246">フィードバックを提供し、問題を報告する</span><span class="sxs-lookup"><span data-stu-id="6177d-246">Provide feedback and report issues</span></span>

<span data-ttu-id="6177d-247">HoloLens で[フィードバック Hub アプリ](hololens-feedback.md)を使用してフィードバックを提供し、問題を報告することができます。</span><span class="sxs-lookup"><span data-stu-id="6177d-247">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="6177d-248">フィードバック Hub を使用すると、エンジニアが問題を迅速にデバッグして解決するのに役立つすべての必要な診断情報が含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="6177d-248">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="6177d-249">中国語および日本語版の HoloLens に関する問題は、同じ方法で報告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6177d-249">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="6177d-250">フィードバック Hub を使用してドキュメント フォルダーにアクセスするかどうかを確認するプロンプトに必ず同意してください (メッセージが表示されたら **[はい]** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="6177d-250">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="6177d-251">開発者向けの注意事項</span><span class="sxs-lookup"><span data-stu-id="6177d-251">Note for developers</span></span>

<span data-ttu-id="6177d-252">HoloLens の Insider ビルドを使用して自由にアプリケーションを開発してみることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6177d-252">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="6177d-253">作業を始めるには、[HoloLens 開発者向けドキュメント](https://developer.microsoft.com/windows/mixed-reality/development)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6177d-253">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="6177d-254">これらの同じ手順は HoloLens の Insider ビルドでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="6177d-254">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="6177d-255">HoloLens 開発用に使用しているものと同じビルドの Unity と Visual Studio を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6177d-255">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <span data-ttu-id="6177d-256">Insider ビルドの受信の停止</span><span class="sxs-lookup"><span data-stu-id="6177d-256">Stop receiving Insider builds</span></span>

<span data-ttu-id="6177d-257">Windows Holographic の Insider ビルドを受け取りたくない場合は、HoloLens が製品版ビルドを実行しているときにオプトアウトすることができます。または、Advanced Recovery Companion を使用して[デバイスを回復](hololens-recovery.md)し、Windows Holographic の Insider バージョン以外にデバイスを回復することができます。</span><span class="sxs-lookup"><span data-stu-id="6177d-257">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="6177d-258">新しいプレビュー ビルドを手動で再インストールした後に Insider Preview ビルドの登録を解除すると、ブルー スクリーンが発生するという既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="6177d-258">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="6177d-259">その後、手動でデバイスを回復する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6177d-259">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="6177d-260">影響を受けるかどうかの詳細については、この[既知の問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)の詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6177d-260">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="6177d-261">HoloLens が製品版ビルドを実行していることを確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6177d-261">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="6177d-262">**[設定] > [システム] > [バージョン情報]** の順に移動し、ビルド番号を探します。</span><span class="sxs-lookup"><span data-stu-id="6177d-262">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="6177d-263">[実稼働ビルド番号のリリース ノートを参照してください](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="6177d-263">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="6177d-264">Insider ビルドをオプトアウトするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6177d-264">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="6177d-265">製品版ビルドを実行している HoloLens で、**[設定] > [更新とセキュリティ] > [Windows Insider Program]** に移動して、**[Insider Preview ビルドの停止]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6177d-265">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="6177d-266">画面の指示に従って、デバイスでの受信を停止します。</span><span class="sxs-lookup"><span data-stu-id="6177d-266">Follow the instructions to opt out your device.</span></span>
