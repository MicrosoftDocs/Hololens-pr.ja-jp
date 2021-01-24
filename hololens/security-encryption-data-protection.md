---
title: データ保護と暗号化
description: BitLocker と Azure の統合を含む、HoloLens 2 デバイスの暗号化とデータ保護について説明します。
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
ms.openlocfilehash: e005f04088127a0e38a4dd978cd63e5d4e5c0ab9
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284108"
---
# <span data-ttu-id="7a4e5-104">データ保護と暗号化</span><span class="sxs-lookup"><span data-stu-id="7a4e5-104">Encryption and data protection</span></span>

<span data-ttu-id="7a4e5-105">暗号化とデータ保護は、デバイスの紛失や盗難があった場合にデータを保護し、認証されていないアプリケーションが機密情報にアクセスするのを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="7a4e5-105">Encryption and Data Protection protects data when the device is lost or stolen and prevents unauthorized applications from accessing sensitive information.</span></span>

## <span data-ttu-id="7a4e5-106">BitLocker によるデバイスの暗号化</span><span class="sxs-lookup"><span data-stu-id="7a4e5-106">BitLocker device encryption</span></span>

<span data-ttu-id="7a4e5-107">BitLocker は、読み取り専用 (RO) メディアの整合性を保護し、書き込み可能なメディアのプライバシーを保護する、フル ボリュームの暗号化機能です。</span><span class="sxs-lookup"><span data-stu-id="7a4e5-107">BitLocker is a full-volume encryption feature for integrity protection of Read Only (RO) media and privacy protection of writable media.</span></span>  <span data-ttu-id="7a4e5-108">これまで、オフライン攻撃の際のデータへの不正アクセスに対する効果的な防護壁となってきました。</span><span class="sxs-lookup"><span data-stu-id="7a4e5-108">Since its inception, it has been an effective shield against unauthorized access to the data during offline attacks.</span></span> <span data-ttu-id="7a4e5-109">HoloLens 2 は、Bitlocker によるデバイスの暗号化 (BDE) を既定で有効にして、デバイスへの許可されていない物理的アクセスからデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="7a4e5-109">HoloLens 2 enables Bitlocker Device Encryption (BDE) by default to protect data from any unauthorized physical access to the device.</span></span> <span data-ttu-id="7a4e5-110">Microsoft は、常に将来のニーズを満たすために進化し続け、このテクノロジへの投資と強化を続けています。</span><span class="sxs-lookup"><span data-stu-id="7a4e5-110">Always evolving to meet the needs of the future, Microsoft continues to invest and enhance this technology.</span></span>

<span data-ttu-id="7a4e5-111">BDE は、デバイスの状態によって区切られたレイアウトのすべてのボリュームにおいて、AES-XTS-256 暗号化を適用するデータ保護機能です。</span><span class="sxs-lookup"><span data-stu-id="7a4e5-111">BDE is a data protection feature that employs AES-XTS-256 encryption on all volumes in the state-separated layout of the device.</span></span> <span data-ttu-id="7a4e5-112">BDE は、状態によって区切られたレイアウトにおいて、デバイス レベルの暗号化を提供します。</span><span class="sxs-lookup"><span data-stu-id="7a4e5-112">BDE provides device level encryption in a state-separated layout.</span></span> <span data-ttu-id="7a4e5-113">BitLocker デバイス暗号化は、オペレーティングシステムと固定データ ボリュームに対して自動的に有効になっているため、デバイスは常に保護されていて、 IT 管理者にもこれをオフにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7a4e5-113">BitLocker Device Encryption is enabled automatically on operating system and fixed data volumes and cannot be turned off, even by IT administrators, so that the device is always protected.</span></span>

<span data-ttu-id="7a4e5-114">その後、BDE の暗号化キーを使用して、バイナリやデバイスのブートに必要なデータを透過的に複合化します。</span><span class="sxs-lookup"><span data-stu-id="7a4e5-114">BDE encryption keys are then used to transparently decrypt binaries and the data required to boot the device.</span></span> <span data-ttu-id="7a4e5-115">オペレーティング システムのボリュームのロックを解除してシステムを起動すると、ボリューム固有のバージョンの自動ロック解除プロテクターを使用して、他のボリュームにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="7a4e5-115">As the operating system volume is unlocked and a system is booting up, other volumes become accessible using a volume-specific version of the auto-unlock protector.</span></span> <span data-ttu-id="7a4e5-116">ユーザーのプライバシーを維持するために使用できる他のプロテクターはありません。また、同じデバイス上でのみ、ドライブのロックを解除することができます。</span><span class="sxs-lookup"><span data-stu-id="7a4e5-116">No other protectors are available to maintain user privacy and the drive can only be unlocked on the same device.</span></span> <span data-ttu-id="7a4e5-117">最初の起動時より、読み取り専用の (RO) 強制が、必要なボリュームに対してすぐに適用されます。</span><span class="sxs-lookup"><span data-stu-id="7a4e5-117">Read Only (RO) enforcement on required volumes is applied and enforced immediately, starting from the first boot.</span></span>

## <span data-ttu-id="7a4e5-118">Azure の統合</span><span class="sxs-lookup"><span data-stu-id="7a4e5-118">Azure integration</span></span> 

<span data-ttu-id="7a4e5-119">HoloLens 2 では、お客様は Azure サービスを使用して自分のデバイスを統合できます。</span><span class="sxs-lookup"><span data-stu-id="7a4e5-119">HoloLens 2 enables customers to integrate their devices with Azure services.</span></span> <span data-ttu-id="7a4e5-120">HoloLens 2 デバイスと Azure 間の通信は、TLS (トランスポート層セキュリティ) プロトコルを使用し、自身とクラウド サービス間を移動するデータを保護し、強力な認証、メッセージのプライバシー、整合性を実現します。</span><span class="sxs-lookup"><span data-stu-id="7a4e5-120">Communications between HoloLens 2 devices and Azure use TLS (Transport Layer Security) protocol to protect data traveling between itself and cloud services which delivers strong authentication, message privacy, and integrity.</span></span> <span data-ttu-id="7a4e5-121">すべての Azure サービスは、TLS 1.2 を完全にサポートし、お客様が TLS 1.2 のみを使用している場合は、TLS 1.2 トラフィックのみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="7a4e5-121">All Azure services fully support TLS 1.2 and any services where customers are using only TLS 1.2 only accept TLS 1.2 traffic.</span></span> <span data-ttu-id="7a4e5-122">送信中のデータに対する Azure の暗号化標準は [Azure encryption の概要](https://docs.microsoft.com/azure/security/fundamentals/encryption-overview)で詳しく説明されています。</span><span class="sxs-lookup"><span data-stu-id="7a4e5-122">Azure’s encryption standards for data in transit are detailed in [Azure encryption overview](https://docs.microsoft.com/azure/security/fundamentals/encryption-overview).</span></span> <span data-ttu-id="7a4e5-123">[Azure データのセキュリティと暗号化](https://docs.microsoft.com/azure/security/fundamentals/data-encryption-best-practices)のベスト プラクティスの詳細については、Azure のドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7a4e5-123">Visit the Azure documentation to learn more about [best practices for Azure data security and encryption](https://docs.microsoft.com/azure/security/fundamentals/data-encryption-best-practices).</span></span> 

<span data-ttu-id="7a4e5-124">HoloLens 2 とのクラウド統合の例である OneDrive には、インターネットに接続したときにファイルとドキュメントをクラウドに自動的にアップロードできる、自動アップロード機能があります。</span><span class="sxs-lookup"><span data-stu-id="7a4e5-124">OneDrive, an example of cloud integration with HoloLens 2, has an auto upload feature where your files and documents can be automatically uploaded to the cloud when connected to the internet.</span></span> <span data-ttu-id="7a4e5-125">ファイルの自動同期を一時停止は、ポリシーからオフにすることはできませんが、UX から直接構成できます。</span><span class="sxs-lookup"><span data-stu-id="7a4e5-125">Pausing automatic syncing of files cannot be turned off via policy but is directly configurable via the UX.</span></span> 
