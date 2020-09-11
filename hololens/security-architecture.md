---
title: HoloLens セキュリティ アーキテクチャ
description: セキュリティ アーキテクチャ
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: セキュリティ、hololens、hololens 2、hololens2 security、セキュリティの概要、セキュリティ アーキテクチャ、アーキテクチャ、hololens 2 のアーキテクチャ
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f8434ffe2442f270d6360018bea4b64064168d0c
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009555"
---
# <span data-ttu-id="c1c0e-104">セキュリティの概要とアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="c1c0e-104">Security overview and architecture</span></span>

<span data-ttu-id="c1c0e-105">HoloLens 2 のセキュリティ アーキテクチャは、攻撃を最小限に抑えるとともに、レガシーセキュリティの問題から解放されるようにゼロから設計および構築されました。</span><span class="sxs-lookup"><span data-stu-id="c1c0e-105">The HoloLens 2 security architecture was designed and engineered from the ground up to be free from legacy security issues, while creating a minimized attack surface.</span></span> <span data-ttu-id="c1c0e-106">この新しい革新的なアーキテクチャでは、セキュリティで保護されたストレージの場所と、高度なセキュリティ要素を提供し、オペレーティングシステムが潜在的な脅威や脆弱性から保護できるメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="c1c0e-106">This new, innovative architecture offers secure storage locations and advanced security elements, with mechanisms capable of shielding operating systems from potential threats and vulnerabilities.</span></span>

<span data-ttu-id="c1c0e-107">HoloLens 2 は、ハードウェア、ソフトウェア、ネットワーク、およびサービスを組み合わせて、エンドツーエンドのセキュリティを確保するとともに、ユーザーに最適なエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c1c0e-107">HoloLens 2 combines hardware, software, networking, and services to deliver end-to-end security, while providing the user with an optimal experience.</span></span> <span data-ttu-id="c1c0e-108">HoloLens 2 では、セキュリティ機能の大部分が自動的に有効になり、オペレーティング システムを正しくセットアップして構成するために必要な労力を最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="c1c0e-108">With HoloLens 2, a large majority of security features are now turned on automatically, minimizing the effort required to correctly set up and configure the operating system.</span></span>

<span data-ttu-id="c1c0e-109">Windows HoloLens 2 とオペレーティング システムのアーキテクチャには、次の革新的なセキュリティ機能があります。</span><span class="sxs-lookup"><span data-stu-id="c1c0e-109">Windows HoloLens 2 and operating system architecture offers these innovative security features:</span></span>

  * <span data-ttu-id="c1c0e-110">**状態の分割と分離**: この新しいアーキテクチャは、コア オペレーティング システムを信頼できる状態で起動するために必要な部分など、HoloLens 2 オペレーティング システムの重要部分が変わらないように保護します。</span><span class="sxs-lookup"><span data-stu-id="c1c0e-110">**State separation and isolation**:  This new architecture protects critical portions of the HoloLens 2 operating system from change - such as those required for the core operating system to boot into a trusted state.</span></span> <span data-ttu-id="c1c0e-111">分離技術を使用して、信頼されていないアプリをサンドボックス領域に限定し、システムのセキュリティに影響しないようにします。</span><span class="sxs-lookup"><span data-stu-id="c1c0e-111">Isolation technology is used to confine untrusted apps in a sandbox area, ensuring that they cannot impact the system security.</span></span> <span data-ttu-id="c1c0e-112">オペレーティングシステム全体は安全なセクションに分かれており、セクションごとに異なるセキュリティ技術を組み合わせることによって保護しています。</span><span class="sxs-lookup"><span data-stu-id="c1c0e-112">The entire operating system is segmented into secure sections, with each section shielded by a combination of different security technologies.</span></span>
  
  * <span data-ttu-id="c1c0e-113">**データ保護**: ユーザーのデバイスが紛失または盗難があった場合、HoloLens 2 はデータの BitLocker 暗号化によって、認証されていないアプリケーションが機密情報を読み取ることを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="c1c0e-113">**Data Protection**: If a user’s device is lost or stolen, HoloLens 2 prevents unauthorized applications from reading sensitive information by relying on BitLocker encryption of data.</span></span> 
  
  * <span data-ttu-id="c1c0e-114">**パスワードなしのオペレーティング システム**: 以前のパスワード ベースのオペレーティング システムでは、ユーザーが不注意によるフィッシング詐欺にさらされる可能性があったため、アカウントが侵害される原因となることがしばしばありました。</span><span class="sxs-lookup"><span data-stu-id="c1c0e-114">**Password-less operating system**:  Older, password-based operating systems could inadvertently expose users to phishing threats and were often responsible for compromised accounts.</span></span> <span data-ttu-id="c1c0e-115">Windows Holographic for Business では、MSA および AAD のサインインのパスワードの使用を排除し、Windows Hello™ と FIDO2 のサインインを使用してユーザー ID 保護を強化します。</span><span class="sxs-lookup"><span data-stu-id="c1c0e-115">Windows Holographic for Business eliminates the use of passwords for MSA and AAD sign-in and strengthens user-identity protection with Windows Hello™ and FIDO2 sign-in.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="c1c0e-116">FIDO2 のサポートを受けるには、デバイスがビルド 19041 以降である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1c0e-116">To have FIDO2 support, the device must be on Build 19041 or higher.</span></span> 

  * <span data-ttu-id="c1c0e-117">**ネットワークセキュリティ**: HoloLens 2 は、改善されたプロトコルと既定の設定により、ユーザーに強化されたネットワークセキュリティを提供します。</span><span class="sxs-lookup"><span data-stu-id="c1c0e-117">**Network security**: HoloLens 2 offers the user increased network security via improved protocols and default settings.</span></span>
