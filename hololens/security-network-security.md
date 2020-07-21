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
ms.openlocfilehash: 147401331cb6da732a6fe37e57964d61a10dce99
ms.sourcegitcommit: 47bc3b696936dd7011b3f9dd683deb872ed25b90
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2020
ms.locfileid: "10883141"
---
# ネットワーク セキュリティ

## ネットワーク プロトコル

以前の NetBIOS (ネットワーク基本入出力システム) は、LAN シナリオにおいて、多くの場合コンピューターや共有フォルダーに名前を付けるために広く使用されていました。 しかし、時間の経過と共に、NetBIOS は複数の攻撃に対して影響されやすいことがわかり、他のセキュリティで保護されたプロトコルがそれに代わるようになると、その関連度は減少しました。 この脆弱性の問題を解決するために、HoloLens 2 ではオペレーティング システムから NetBIOS 関連コードが除外されました。

TLS (トランスポート層セキュリティ) プロトコルは常に進化しています。 この分野で発見されたさまざまなセキュリティの攻略に常に対応するために、コンピューティング業界は、より新しくより効果的なバージョンへと進歩を遂げてきました。 すべてのサーバーの展開において、新しい TLS プロトコルのバージョンを採用する時間が必要になるため、フォールバック機構を使用して、クライアントとサーバーが別の既定のプロトコル バージョンを使用して、移行期間中も通信できるようにすることができます。

## セキュリティで保護された接続 

Windows Defender ファイアウォールは、デバイスの接続をセキュリティで保護するために重要な機能を提供します。 HoloLens 2 ではファイアウォールが常に有効になっています。ファイアウォールをプログラムによって無効にしたり、UI を介して無効にしたりする方法はありません。

モバイル クライアントのリモート アクセスと接続のプライバシーは、[UWP VPN プラグイン プラットフォーム](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041)によって保証されます。 サードパーティの VPN プロバイダーは、AppContainer サンドボックス内で実行される WinRT Api を使用して、独自のプラグインを作成できます。これにより、システム レベルのドライバーの作成に伴う複雑さや問題を排除することができます。
