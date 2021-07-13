---
title: 新しい設定アプリの概要
description: 新しい設定アプリの詳細
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens、設定、アプリ ピッカー、ボリューム
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: bf1a2080c15346843b9ea9b2d0dc93154e185107
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "110398909"
---
# <a name="new-settings-app"></a><span data-ttu-id="31969-104">新しい設定アプリ</span><span class="sxs-lookup"><span data-stu-id="31969-104">New Settings app</span></span>

<span data-ttu-id="31969-105">[Windows Holographic バージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1)では、設定アプリの新しいバージョンを導入しています。</span><span class="sxs-lookup"><span data-stu-id="31969-105">With [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), we're introducing a new version of the Settings app.</span></span> <span data-ttu-id="31969-106">新しい設定アプリには、サウンド、電源とスリープ、ネットワークとインターネット、アプリ、アカウント、コンピューターの簡単操作などの領域における HoloLens 2 の新機能と拡張設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="31969-106">The new Settings app includes new features and expanded settings for HoloLens 2 in the following areas: Sound, Power & sleep, Network & Internet, Apps, Accounts, Ease of Access, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="31969-107">新しい設定アプリは従来の設定アプリとは別であるため、以前に環境に配置した設定の windows は、更新時に削除されます。</span><span class="sxs-lookup"><span data-stu-id="31969-107">Because the new Settings app is distinct from the legacy Settings app, any Settings windows you previously placed around your environment will be removed upon update.</span></span>

![新しい設定アプリのホームページ](images/new-settings-app.png)

<span data-ttu-id="31969-109">**新機能と設定**</span><span class="sxs-lookup"><span data-stu-id="31969-109">**New features and settings**</span></span>
- <span data-ttu-id="31969-110">設定の検索: キーワードまたは設定の名前を使用して、設定ホームページから設定を検索します。</span><span class="sxs-lookup"><span data-stu-id="31969-110">Settings search: search for settings from the Settings homepage using keywords or the setting's name.</span></span>
- <span data-ttu-id="31969-111">[設定] > [[色の調整]](hololens2-display.md#how-to-use-display-color-calibration)</span><span class="sxs-lookup"><span data-stu-id="31969-111">System > [Color calibration](hololens2-display.md#how-to-use-display-color-calibration)</span></span>
    - <span data-ttu-id="31969-112">HoloLens 2 表示の代替カラー プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="31969-112">Select an alternative color profile for your HoloLens 2 display.</span></span>
- <span data-ttu-id="31969-113">[システム] > [サウンド]:</span><span class="sxs-lookup"><span data-stu-id="31969-113">System > Sound:</span></span>
  - <span data-ttu-id="31969-114">入出力オーディオ デバイス: 入力と出力のオーディオ デバイスを個別に選択します (たとえば、Bluetooth ヘッドホンを使用してオーディオをリッスンするか、オーディオ入力に USB C マイクを使用します)。</span><span class="sxs-lookup"><span data-stu-id="31969-114">Input and output audio devices: independently choose your input and output audio devices (for example, listen to audio via Bluetooth headphones or use a USB-C microphone for audio input).</span></span>
    > [!NOTE]
    > <span data-ttu-id="31969-115">Bluetooth のマイクは、HoloLens 2 ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="31969-115">Bluetooth microphones are not supported by HoloLens 2.</span></span>
  - <span data-ttu-id="31969-116">アプリのボリューム: 各アプリのボリュームを個別に調整します。</span><span class="sxs-lookup"><span data-stu-id="31969-116">App volume: independently adjust the volume of each app.</span></span> <span data-ttu-id="31969-117">[「アプリごとのボリューム制御」](holographic-home.md#per-app-volume-control)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31969-117">See [per app volume control](holographic-home.md#per-app-volume-control).</span></span>
- <span data-ttu-id="31969-118">[システム] > [電源とスリープ]: 操作のない状態が一定期間続いた後にスリープに移行するときに選択します。</span><span class="sxs-lookup"><span data-stu-id="31969-118">System > Power & sleep: choose when the device should go to sleep after a period of inactivity.</span></span>
- <span data-ttu-id="31969-119">[システム] > [バッテリ]: バッテリ節約モードを手動で有効にするか、バッテリ省モードが自動的にオンになるようにバッテリのしきい値を設定します。</span><span class="sxs-lookup"><span data-stu-id="31969-119">System > Battery: manually enable battery saver mode or set a battery threshold at which point battery saver mode turns on automatically.</span></span>
- <span data-ttu-id="31969-120">[デバイス] > [USB]: USB 接続を既定で無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="31969-120">Devices > USB: you can disable USB connections by default.</span></span>
- <span data-ttu-id="31969-121">ネットワークとインターネット:</span><span class="sxs-lookup"><span data-stu-id="31969-121">Network & Internet:</span></span>
  - <span data-ttu-id="31969-122">USB-C イーサネット アダプタが、[ネットワークとインターネット] に表示されます。</span><span class="sxs-lookup"><span data-stu-id="31969-122">USB-C Ethernet adapters will now appear in Network & Internet.</span></span>
  - <span data-ttu-id="31969-123">USB-C イーサネットアダプターの設定が、IP アドレスを含めて使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="31969-123">USB-C Ethernet adapter settings are now available, including its IP address.</span></span>
  - <span data-ttu-id="31969-124">HoloLens 2 で機内モードを有効にできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="31969-124">You can now enable airplane mode on HoloLens 2.</span></span>
- <span data-ttu-id="31969-125">アプリ: ファイルとリンクの種類に使用される既定のアプリをリセットできます。</span><span class="sxs-lookup"><span data-stu-id="31969-125">Apps: you can reset the default apps used for file and link types.</span></span> <span data-ttu-id="31969-126">詳細については、[「既定のアプリ ピッカー」](holographic-home.md#default-app-picker)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31969-126">For more information see [Default app picker](holographic-home.md#default-app-picker).</span></span>
- <span data-ttu-id="31969-127">[アカウント] > [他のユーザー]: デバイス所有者は、ユーザーを追加し、標準ユーザーをデバイス所有者にアップグレードし、デバイス所有者を標準ユーザーにダウングレードして、ユーザーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="31969-127">Accounts > Other users: device owners can add users, upgrade standard users to device owners, downgrade device owners to standard users, and remove users.</span></span>
- <span data-ttu-id="31969-128">簡単操作: テキストのサイズと視覚効果を変更します。</span><span class="sxs-lookup"><span data-stu-id="31969-128">Ease of Access: change text size and some visual effects.</span></span>

<span data-ttu-id="31969-129">**既知の問題**</span><span class="sxs-lookup"><span data-stu-id="31969-129">**Known issues**</span></span>
- <span data-ttu-id="31969-130">以前に配置した設定ウィンドウは削除されます (上のメモを参照)。</span><span class="sxs-lookup"><span data-stu-id="31969-130">Previously placed Settings windows will be removed (see note above).</span></span>
- <span data-ttu-id="31969-131">設定アプリでは、デバイスの名前を変更できなくなります。</span><span class="sxs-lookup"><span data-stu-id="31969-131">You can no longer rename your device with the Settings app.</span></span> <span data-ttu-id="31969-132">IT 管理者は、[Windows Autopilot for HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) のデバイス名テンプレートまたは MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName ノードを使用してデバイスの名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="31969-132">IT admins can rename devices by using the [Windows Autopilot for HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) device name template or the MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName node.</span></span>
- <span data-ttu-id="31969-133">イーサネットのページには、常に仮想イーサネットデバイス ("UsbNcm") が表示されます。</span><span class="sxs-lookup"><span data-stu-id="31969-133">The Ethernet page shows a virtual Ethernet device ("UsbNcm") at all times.</span></span>
- <span data-ttu-id="31969-134">新しい Microsoft Edge のバッテリ使用量は、UWP アダプター レイヤーによってサポートされている Win32 デスクトップ アプリケーションの性質上、正確ではない可能性があります (近日対応予定の修正プログラムはありません)。</span><span class="sxs-lookup"><span data-stu-id="31969-134">Battery usage for the new Microsoft Edge may not be accurate, due to its nature as a Win32 desktop application supported by a UWP adapter layer (no fix anticipated soon).</span></span>

