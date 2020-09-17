---
title: ハードウェアで支援された整合性と実行時認証
description: ハードウェアで支援された整合性と実行時認証
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: セキュリティ、hololens、ハードウェアによる整合性、実行時の認証、UEFI、UEFI セキュアブート、セキュアブート、TPM、脅威保護、Windows のAnti-Persistence（永続攻撃対策）保証、コードの整合性、コードの保護、
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: befd2d892403b7b6c7050f48ba9beffb45b241fe
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016681"
---
# <span data-ttu-id="96fc0-104">ハードウェアで支援された整合性とランタイム認証</span><span class="sxs-lookup"><span data-stu-id="96fc0-104">Hardware-backed integrity and runtime attestation</span></span>

<span data-ttu-id="96fc0-105">デバイスがハードウェアを使用するときは、オペレーティングシステム開始前から実行中にかけて発生する脅威に対してハードウェアで支援された整合性と実行時認証が保護します。またリモート認証サービスは、開始時と実行中整合性が確実に維持されるように、保護します。</span><span class="sxs-lookup"><span data-stu-id="96fc0-105">Hardware-backed integrity and runtime attestation protects against threats that originate prior to the start of an operating system, during runtime, when the device uses hardware, and remote attestation services to ensure integrity is maintained at startup and throughout runtime duration.</span></span>

## <span data-ttu-id="96fc0-106">UEFI セキュア ブート</span><span class="sxs-lookup"><span data-stu-id="96fc0-106">UEFI secure boot</span></span>

<span data-ttu-id="96fc0-107">HoloLens 2 はUnified Extensible Firmwaいますe Interface (UEFI) Secure Boot(統合拡張ファームウェアインターフェイス) を常時強制的に行う。UEFI はWindows Holographic for Businessのみ、再起動します。</span><span class="sxs-lookup"><span data-stu-id="96fc0-107">HoloLens 2 enforces Unified Extensible Firmware Interface (UEFI) Secure Boot at all times, and UEFI only boots Windows Holographic for Business.</span></span>
<span data-ttu-id="96fc0-108">セキュアブートを使用すると、ブートチェーン全体の整合性が検証され、Windows が常に正しいセキュリティポリシーを適用してブートすることになります。</span><span class="sxs-lookup"><span data-stu-id="96fc0-108">Secure Boot ensures that the entire boot chain is verified for integrity, and that Windows always boots with the correct security policies applied to it.</span></span> <span data-ttu-id="96fc0-109">セキュアブートの詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="96fc0-109">To learn more about Secure Boot go here.</span></span>

## <span data-ttu-id="96fc0-110">TPM</span><span class="sxs-lookup"><span data-stu-id="96fc0-110">TPM</span></span>

<span data-ttu-id="96fc0-111">Trusted Platform Module (TPM) は、エンドポイントデバイス上の特殊なチップです。</span><span class="sxs-lookup"><span data-stu-id="96fc0-111">The Trusted Platform Module (TPM) is a specialized chip on an endpoint device.</span></span> <span data-ttu-id="96fc0-112">HoloLens 2 は、ハードウェアによるキーの分離を提供する TPM 2.0 を使用します。</span><span class="sxs-lookup"><span data-stu-id="96fc0-112">HoloLens 2 uses a TPM 2.0 which provides hardware-enforced key isolation.</span></span>

## <span data-ttu-id="96fc0-113">Persistence Access Threat Protection（永続的アクセス脅威からの保護）</span><span class="sxs-lookup"><span data-stu-id="96fc0-113">Persistence Access Threat Protection</span></span>

<span data-ttu-id="96fc0-114">ほとんどの サイバー攻撃 の目標は、デバイスへのアクセスを永続的に維持することです。</span><span class="sxs-lookup"><span data-stu-id="96fc0-114">The goal of most cyberattacks is to maintain persistent access to a device.</span></span> <span data-ttu-id="96fc0-115">サイバー犯罪では、このような永続性が維持されることで、Windows デバイスのセキュリティが悪化して botnet に入り、デバイスやその他の悪意のあるユーザーにアクセスを販売したり、データ盗用の繰返しが可能になるのです。</span><span class="sxs-lookup"><span data-stu-id="96fc0-115">For cybercrime, maintaining this persistence enables a compromised Windows device to join a botnet, sell access to the device or other nefarious users, or to enable repeated data theft.</span></span> <span data-ttu-id="96fc0-116">標的を絞った攻撃の世界では、永続性がデバイスのみでなく、あるいは (より一般的には) ネットワーク全体にサイバー攻撃 を成功させるために不可欠です。</span><span class="sxs-lookup"><span data-stu-id="96fc0-116">In the world of targeted attacks, persistence is essential to a successful cyberattack – whether on a device or (more commonly), an entire network.</span></span>  

<span data-ttu-id="96fc0-117">実際に、標的を絞った攻撃は、対象デバイスやネットワークへのアクセスを維持するための戦略的なニーズを理由として、"高度に永続的な脅威" と考えられています。</span><span class="sxs-lookup"><span data-stu-id="96fc0-117">In fact, targeted attacks are considered “advanced persistent threats”, due to their strategic need to maintain access to a target device or network.</span></span> <span data-ttu-id="96fc0-118">このような理由から、Windows Holographic for Business は、この永続的攻撃に対する防護を最重要と考え、永続的攻撃対策テクノロジーを使用して、厳重な顧客セキュリティを行うことを約束しています。</span><span class="sxs-lookup"><span data-stu-id="96fc0-118">For this reason, Windows Holographic for Business considers defending against persistence absolutely crucial and uses anti-persistence technology to make an ironclad customer security promise.</span></span>

### <span data-ttu-id="96fc0-119">セキュア ブート</span><span class="sxs-lookup"><span data-stu-id="96fc0-119">Secure boot</span></span> 

<span data-ttu-id="96fc0-120">HoloLens 2 では、統合拡張ファームウェアインターフェイス (UEFI)セキュリティブートを すべてのコアオペレーティングシステムの状態に関して強制的に行います。</span><span class="sxs-lookup"><span data-stu-id="96fc0-120">HoloLens 2 enforces Unified Extensible Firmware Interface (UEFI) Secure Boot on all core operating system state.</span></span> <span data-ttu-id="96fc0-121">UEFI は、Microsoft のトラステッドプラットフォームのみを起動します。これにより、ブートチェーン全体で整合性が検証され、Windows は常に正しいセキュリティポリシーを適用してブートします。</span><span class="sxs-lookup"><span data-stu-id="96fc0-121">UEFI only boots Microsoft trusted platforms which ensures that the entire boot chain is verified for integrity, and that Windows always boots with the correct security policies applied to it.</span></span> <span data-ttu-id="96fc0-122">HoloLens 2 はセキュアブートをオフにすることはできません。また、第三者製ブートローダーを許可しません。</span><span class="sxs-lookup"><span data-stu-id="96fc0-122">HoloLens 2 does not Secure Boot to be turned off, nor does it allow 3rd party boot loaders.</span></span>

> [!Tip]
> <span data-ttu-id="96fc0-123">[セキュアブート](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)について説明します。</span><span class="sxs-lookup"><span data-stu-id="96fc0-123">Learn more about [Secure boot](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).</span></span>

### <span data-ttu-id="96fc0-124">Windows の永続的攻撃対策保証</span><span class="sxs-lookup"><span data-stu-id="96fc0-124">Windows Anti-Persistence Assurance</span></span>

<span data-ttu-id="96fc0-125">HoloLens 2 の永続的攻撃対策は、遠隔操作のような、システム実行中にセキュリティ侵害が起こるような稀な状況においても、デバイスの電源を切って悪意のあるコードをすべてシステムから削除することによって、そのイベントの害を緩和することを、ユーザーに対して保証しています。</span><span class="sxs-lookup"><span data-stu-id="96fc0-125">HoloLens 2 anti-persistence guarantees its users that even in the rare situation that a runtime compromise of the system were to ever occur – such as a remote exploit – such an event would be mitigated with all malicious code removed from the system simply by powering off the device.</span></span> <span data-ttu-id="96fc0-126">永続的攻撃対策をさらに強化するために、HoloLens 2 は、強力な整合性保護を追加し、読み取り専用の保護を設定しました。</span><span class="sxs-lookup"><span data-stu-id="96fc0-126">To further strengthen its anti-persistence, HoloLens 2 has added powerful integrity protection, and put read-only protections in place.</span></span>

<span data-ttu-id="96fc0-127">データ形式でのオペレーティングシステムデータの永続的攻撃は、変更可能なすべてのパーティションを消去するデバイスのPush-buttonリセット (PBR) をユーザーが実行しない限り、引き続き可能です。</span><span class="sxs-lookup"><span data-stu-id="96fc0-127">Persistence to operating system data in form of data is still possible, unless the user performs Push-button reset (PBR) of the device that wipes all mutable partitions.</span></span> <span data-ttu-id="96fc0-128">変更可能なパーティションに対する永続的攻撃がより激しくなる時は、ユーザーは Hololens 2 をPBRして、可変要素から永続的脅威を除去する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96fc0-128">While persistence to immutable partitions is made much harder, the user needs to PBR the Hololens 2 to remove any possible threat-persistence from mutable parts.</span></span>

## <span data-ttu-id="96fc0-129">コードの整合性保護</span><span class="sxs-lookup"><span data-stu-id="96fc0-129">Code integrity protection</span></span> 

<span data-ttu-id="96fc0-130">コードの整合性 (CI) は、最新のオペレーティングシステムの重要なセキュリティプロパティです。</span><span class="sxs-lookup"><span data-stu-id="96fc0-130">Code integrity (CI) is a key security property of a modern operating system.</span></span> <span data-ttu-id="96fc0-131">CI を強制適用すると、ユーザーとオペレーティングシステムの両方に対してコードの 由来が明瞭になることが保証されるので、適切なセキュリティ決定を可能にします。</span><span class="sxs-lookup"><span data-stu-id="96fc0-131">Enforcing CI enables sound security decisions, because it guarantees the provenance of code is transparent to both the user and operating system.</span></span> <span data-ttu-id="96fc0-132">コードの整合性を完全に維持するには、バイナリイメージの過去の署名を延長する必要があります。また、制御フローの整合性や動的なコードの制限などのランタイム強制を含む必要があります。</span><span class="sxs-lookup"><span data-stu-id="96fc0-132">Complete code integrity needs to extend past binary image signing and include runtime enforcement, such as control flow integrity and dynamic code restrictions.</span></span> <span data-ttu-id="96fc0-133">CI は、ランサムウェア、リモートコード実行攻撃、各種の攻撃など、一般的に利用されているマルウェアを含む複数の攻撃を防ぐために欠かせません。</span><span class="sxs-lookup"><span data-stu-id="96fc0-133">CI is critical to preventing multiple classes of attacks including socially engineered malware, such as ransomware, remote code execution exploits, and various other attack classes.</span></span>
