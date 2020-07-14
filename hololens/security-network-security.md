---
title: ネットワーク セキュリティ
description: ネットワーク セキュリティ
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: セキュリティ、hololens、ネットワーク、ネットワークセキュリティ
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: c88a9af7369a6a9d6fb115fb820c0a4da13eafdc
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865842"
---
# <span data-ttu-id="f8e99-104">ネットワーク セキュリティ</span><span class="sxs-lookup"><span data-stu-id="f8e99-104">Network security</span></span>

## <span data-ttu-id="f8e99-105">ネットワーク プロトコル</span><span class="sxs-lookup"><span data-stu-id="f8e99-105">Network protocols</span></span>

<span data-ttu-id="f8e99-106">以前の NetBIOS (ネットワーク基本入出力システム) は、LAN シナリオにおいて、多くの場合コンピューターや共有フォルダーに名前を付けるために広く使用されていました。</span><span class="sxs-lookup"><span data-stu-id="f8e99-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="f8e99-107">しかし、時間の経過と共に、NetBIOS は複数の攻撃に対して影響されやすいことがわかり、他のセキュリティで保護されたプロトコルがそれに代わるようになると、その関連度は減少しました。</span><span class="sxs-lookup"><span data-stu-id="f8e99-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="f8e99-108">この脆弱性の問題を解決するために、HoloLens 2 ではオペレーティング システムから NetBIOS 関連コードが除外されました。</span><span class="sxs-lookup"><span data-stu-id="f8e99-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="f8e99-109">TLS (トランスポート層セキュリティ) プロトコルは常に進化しています。</span><span class="sxs-lookup"><span data-stu-id="f8e99-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="f8e99-110">この分野で発見されたさまざまなセキュリティの攻略に常に対応するために、コンピューティング業界は、より新しくより効果的なバージョンへと進歩を遂げてきました。</span><span class="sxs-lookup"><span data-stu-id="f8e99-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="f8e99-111">すべてのサーバーの展開において、新しい TLS プロトコルのバージョンを採用する時間が必要になるため、フォールバック機構を使用して、クライアントとサーバーが別の既定のプロトコル バージョンを使用して、移行期間中も通信できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f8e99-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

<span data-ttu-id="f8e99-112">ただし、このようなフォールバック機構によってセキュリティ リスクは増大します。</span><span class="sxs-lookup"><span data-stu-id="f8e99-112">However, such fallback mechanisms increase security risks.</span></span> <span data-ttu-id="f8e99-113">こうした問題を受けて、HoloLens 2 では TLS 1.2 から TLS 1.1、または1.0 へのフォールバックは無効になっており、それを有効にするユーザーインターフェイスはありません。</span><span class="sxs-lookup"><span data-stu-id="f8e99-113">Understanding this issue, in HoloLens 2 the fallback from TLS 1.2 to TLS 1.1 or 1.0 has been disabled, and there is no user interface to enable it.</span></span> <span data-ttu-id="f8e99-114">さらに、TLS ハンドシェイク中は、クライアントは TLS 1.2 を要求し、サーバーはより下位バージョンへのダウングレードは実行できません。</span><span class="sxs-lookup"><span data-stu-id="f8e99-114">Furthermore, during the TLS handshake, the client will ask for TLS 1.2, and does not allow the server to downgrade to a lower version.</span></span>

## <span data-ttu-id="f8e99-115">セキュリティで保護された接続</span><span class="sxs-lookup"><span data-stu-id="f8e99-115">Secure connectivity</span></span> 

<span data-ttu-id="f8e99-116">Windows Defender ファイアウォールは、デバイスの接続をセキュリティで保護するために重要な機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="f8e99-116">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="f8e99-117">HoloLens 2 ではファイアウォールが常に有効になっています。ファイアウォールをプログラムによって無効にしたり、UI を介して無効にしたりする方法はありません。</span><span class="sxs-lookup"><span data-stu-id="f8e99-117">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="f8e99-118">モバイル クライアントのリモート アクセスと接続のプライバシーは、[UWP VPN プラグイン プラットフォーム](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041)によって保証されます。</span><span class="sxs-lookup"><span data-stu-id="f8e99-118">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="f8e99-119">サードパーティの VPN プロバイダーは、AppContainer サンドボックス内で実行される WinRT Api を使用して、独自のプラグインを作成できます。これにより、システム レベルのドライバーの作成に伴う複雑さや問題を排除することができます。</span><span class="sxs-lookup"><span data-stu-id="f8e99-119">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
