---
title: 暗号化とデータ保護
description: BitLocker と Azure の統合を含め、HoloLens 2 デバイスの暗号化とデータ保護について説明します。
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: セキュリティ、hololens、暗号化、データ保護、BitLocker デバイス、BitLocker、bitlocker、bitlocker 暗号化、azure 統合、
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: cd1d3ae238924537b1d36f4acdf239f0dc644326827d2c6041ceb94b013b3801
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665507"
---
# <a name="encryption-and-data-protection"></a>暗号化とデータ保護

暗号化とデータ保護は、デバイスの紛失や盗難があった場合にデータを保護し、認証されていないアプリケーションによる機密情報へのアクセスを防ぎます。

## <a name="bitlocker-device-encryption"></a>BitLocker によるデバイスの暗号化

BitLocker は、読み取り専用 (RO) メディアの整合性の保護と書き込み可能なメディアのプライバシー保護を目的としたフルボリューム暗号化機能です。  これまで、オフライン攻撃時のデータへの不正アクセスに対する効果的な防護壁となってきました。 HoloLens 2 の既定では Bitlocker Device Encryption (BDE) が有効であり、デバイスへの不正な物理的アクセスからデータが保護されます。 Microsoft は、常に将来のニーズを満たすために進化し続け、このテクノロジへの投資と強化を続けています。

BDE は、デバイスの状態によって区切られたレイアウトのすべてのボリュームにおいて、AES-XTS-256 暗号化を適用するデータ保護機能です。 BDE は、状態によって区切られたレイアウトにおいて、デバイス レベルの暗号化を提供します。 BitLocker デバイス暗号化は、オペレーティング システムと固定データ ボリュームに対して自動的に有効になっているため、デバイスは常に保護されていて、IT 管理者にもこれをオフにすることはできません。

BDE 暗号化キーは、デバイスの起動に必要なバイナリとデータを透過的に復号するために使用されます。 オペレーティング システムのボリュームのロックを解除してシステムを起動すると、ボリューム固有のバージョンの自動ロック解除プロテクターを使用して、他のボリュームにアクセスできるようになります。 ユーザーのプライバシーを維持するために使用できる他のプロテクターはありません。また、同じデバイス上でのみ、ドライブのロックを解除することができます。 最初の起動時より、読み取り専用の (RO) 強制が、必要なボリュームに対してすぐに適用されます。 HoloLens 2 ライフサイクルでは、Bitlocker 回復キーは必要ありません。

## <a name="azure-integration"></a>Azure の統合 

HoloLens 2 では、お客様は Azure サービスを使用して自分のデバイスを統合できます。 自身とクラウド サービス間を移動するデータを保護し、強力な認証、メッセージのプライバシー、整合性を実現するために、HoloLens 2 デバイスと Azure 間の通信には TLS (トランスポート層セキュリティ) プロトコルが使用されています。 すべての Azure サービスは、TLS 1.2 を完全にサポートし、お客様が TLS 1.2 のみを使用している場合は、TLS 1.2 トラフィックのみを受け入れます。 送信中のデータに対する Azure の暗号化標準については、「[Azure の暗号化の概要](/azure/security/fundamentals/encryption-overview)」を参照してください。 [Azure のデータ セキュリティと暗号化のベスト プラクティス](/azure/security/fundamentals/data-encryption-best-practices)の詳細については、Azure のドキュメントを参照してください。 

HoloLens 2 とのクラウド統合の例である OneDrive には、インターネットに接続したときにファイルとドキュメントをクラウドに自動的にアップロードできる、自動アップロード機能があります。 ファイルの自動同期の一時停止をポリシーでオフすることはできませんが、UX で直接構成することはできます。 
