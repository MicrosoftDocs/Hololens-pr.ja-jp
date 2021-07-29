---
title: ネットワークのセキュリティ
description: ネットワークのセキュリティ
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: セキュリティ、hololens、ネットワーク、ネットワークのセキュリティ
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 416a4f7b9e3cf2e52b79fb29f50424a9c573a18a
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640493"
---
# <a name="network-security"></a>ネットワークのセキュリティ

## <a name="network-protocols"></a>ネットワーク プロトコル

以前の NetBIOS (ネットワーク基本入出力システム) は、LAN シナリオにおいて、多くの場合コンピューターや共有フォルダーに名前を付けるために広く使用されていました。 ただし、時間の経過と共に、NetBIOS は複数の攻撃を受けやすいことがわかり、より安全性の高い他のプロトコルが利用されるようになり、その重要性は低下しました。 この脆弱性の問題を解決するために、HoloLens 2 ではオペレーティング システムから NetBIOS 関連コードが除外されました。

TLS (トランスポート層セキュリティ) プロトコルは常に進化しています。 この分野で発見されたさまざまなセキュリティの攻略に常に対応するために、コンピューティング業界は、より新しくより効果的なバージョンへと進歩を遂げてきました。 すべてのサーバーの展開において、新しい TLS プロトコルのバージョンを採用する時間が必要になるため、フォールバック機構を使用して、クライアントとサーバーが別の既定のプロトコル バージョンを使用して、移行期間中も通信できるようにすることができます。

## <a name="secure-connectivity"></a>セキュリティで保護された接続 

Windows Defender ファイアウォールには、デバイスの接続をセキュリティで保護する重要な機能が用意されています。 HoloLens 2 を使用する場合、ファイアウォールは常に有効です。ファイアウォールをプログラムによって無効にしたり、UI を介して無効にしたりする方法はありません。

モバイル クライアントのリモート アクセスと接続のプライバシーは、[UWP VPN プラグイン プラットフォーム](/uwp/api/Windows.Networking.Vpn?view=winrt-19041)によって保証されます。 サードパーティの VPN プロバイダーは、AppContainer サンドボックス内で実行される WinRT API を使用して、独自のプラグインを作成できます。これにより、システム レベルのドライバーの作成に伴う複雑さや問題を排除することができます。
