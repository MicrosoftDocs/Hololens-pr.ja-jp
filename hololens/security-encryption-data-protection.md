---
title: データ保護と暗号化
description: データ保護と暗号化
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
ms.openlocfilehash: 6f67e43eaf3a20a7f6948a448af2e5efdaa83821
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009545"
---
# データ保護と暗号化

暗号化とデータ保護は、デバイスの紛失や盗難があった場合にデータを保護し、認証されていないアプリケーションが機密情報にアクセスするのを防ぎます。

## BitLocker によるデバイスの暗号化

BitLocker は、読み取り専用 (RO) メディアの整合性を保護し、書き込み可能なメディアのプライバシーを保護する、フル ボリュームの暗号化機能です。  これまで、オフライン攻撃の際のデータへの不正アクセスに対する効果的な防護壁となってきました。 HoloLens 2 は、Bitlocker によるデバイスの暗号化 (BDE) を既定で有効にして、デバイスへの許可されていない物理的アクセスからデータを保護します。 Microsoft は、常に将来のニーズを満たすために進化し続け、このテクノロジへの投資と強化を続けています。

BDE は、デバイスの状態によって区切られたレイアウトのすべてのボリュームにおいて、AES-XTS-256 暗号化を適用するデータ保護機能です。 BDE は、状態によって区切られたレイアウトにおいて、デバイス レベルの暗号化を提供します。 BitLocker デバイス暗号化は、オペレーティングシステムと固定データ ボリュームに対して自動的に有効になっているため、デバイスは常に保護されていて、 IT 管理者にもこれをオフにすることはできません。

その後、BDE の暗号化キーを使用して、バイナリやデバイスのブートに必要なデータを透過的に複合化します。 オペレーティング システムのボリュームのロックを解除してシステムを起動すると、ボリューム固有のバージョンの自動ロック解除プロテクターを使用して、他のボリュームにアクセスできるようになります。 ユーザーのプライバシーを維持するために使用できる他のプロテクターはありません。また、同じデバイス上でのみ、ドライブのロックを解除することができます。 最初の起動時より、読み取り専用の (RO) 強制が、必要なボリュームに対してすぐに適用されます。

## Azure の統合 

HoloLens 2 では、お客様は Azure サービスを使用して自分のデバイスを統合できます。 HoloLens 2 デバイスと Azure 間の通信は、TLS (トランスポート層セキュリティ) プロトコルを使用し、自身とクラウド サービス間を移動するデータを保護し、強力な認証、メッセージのプライバシー、整合性を実現します。 すべての Azure サービスは、TLS 1.2 を完全にサポートし、お客様が TLS 1.2 のみを使用している場合は、TLS 1.2 トラフィックのみを受け入れます。 送信中のデータに対する Azure の暗号化標準は [Azure encryption の概要](https://docs.microsoft.com/azure/security/fundamentals/encryption-overview)で詳しく説明されています。 [Azure データのセキュリティと暗号化](https://docs.microsoft.com/azure/security/fundamentals/data-encryption-best-practices)のベスト プラクティスの詳細については、Azure のドキュメントをご覧ください。 

HoloLens 2 とのクラウド統合の例である OneDrive には、インターネットに接続したときにファイルとドキュメントをクラウドに自動的にアップロードできる、自動アップロード機能があります。 ファイルの自動同期を一時停止は、ポリシーからオフにすることはできませんが、UX から直接構成できます。 
