---
title: セキュリティ エンジニアリング
description: セキュリティ エンジニアリング
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: セキュリティ、hololens、セキュリティ エンジニアリング
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisl
appliesto:
- HoloLens 2
ms.openlocfilehash: 60b11e93ec68e7899403aeec17bba0da7f2ca391
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865817"
---
# <span data-ttu-id="36479-104">セキュリティ エンジニアリング</span><span class="sxs-lookup"><span data-stu-id="36479-104">Security engineering</span></span>

<span data-ttu-id="36479-105">Microsoft には、会社のエンジニアリング プロトコルの最適化、コンプライアンスへの取り組み、顧客の信頼の確保に専念するリソースとチームがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="36479-105">Microsoft has several resources and teams devoted to optimizing the company’s engineering protocols, addressing compliance, and ensuring customer trust.</span></span> 

  * <span data-ttu-id="36479-106">Microsoft のセキュリティ エンジニアリング開発手法の詳細については、「[セキュリティ開発ライフサイクル (SDL)](https://www.microsoft.com/securityengineering/sdl)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="36479-106">To learn more about Microsoft’s security engineering development practices, see the [Security Development Lifecycle (SDL)](https://www.microsoft.com/securityengineering/sdl).</span></span>
  * <span data-ttu-id="36479-107">Microsoft および HoloLens 2 では、データを収集して使用する方法と理由をお客様が選択できるようにしています。こちらは、[Microsoft のプライバシー ポリシー](https://privacy.microsoft.com/)にて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="36479-107">Microsoft, and therefore HoloLens 2, empowers customers to make choices about how and why data is collected and used, which can be further explored in [Microsoft’s Privacy policy](https://privacy.microsoft.com/).</span></span> 
  * <span data-ttu-id="36479-108">[Microsoft Security Response Center (MSRC)](https://www.microsoft.com/msrc) は防御側のコミュニティに含まれています。これにより、効果的な脆弱性レポートのエクスペリエンスが提供され、セキュリティバグの効果的な分類や対応が可能になります。</span><span class="sxs-lookup"><span data-stu-id="36479-108">[Microsoft Security Response Center (MSRC)](https://www.microsoft.com/msrc) is part of the defender community, providing an efficient vulnerability reporting experience and an effective categorization and response to security bugs.</span></span> 

## <span data-ttu-id="36479-109">更新プログラムと修正プログラム</span><span class="sxs-lookup"><span data-stu-id="36479-109">Updates and patches</span></span>

<span data-ttu-id="36479-110">セキュリティ更新プログラムと修正プログラムは、毎月第 2 火曜日にリリースされます。</span><span class="sxs-lookup"><span data-stu-id="36479-110">Security updates and patches are released on the second Tuesday of each month.</span></span> <span data-ttu-id="36479-111">報告された脆弱性の次の手順を評価するために Microsoft が使用する条件については、Microsoft Security Response Center の「[セキュリティのサービス基準](https://www.microsoft.com/msrc/windows-security-servicing-criteria)」ページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="36479-111">In order to understand the criteria used by Microsoft to evaluate next steps for a reported vulnerability, see the Microsoft Security Response Center’s [Security Servicing Criteria page](https://www.microsoft.com/msrc/windows-security-servicing-criteria).</span></span> 

<span data-ttu-id="36479-112">MDM を介して HoloLens 2 の更新プログラムを管理する方法については、「[HoloLens の更新プログラムの管理](https://docs.microsoft.com/hololens/hololens-updates)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="36479-112">For guidance on managing HoloLens 2 updates via MDM, see [Manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates).</span></span> <span data-ttu-id="36479-113">HoloLens 2 のオペレーティング システムの更新タイミングは、Windows 10 と一致しています。2 つの更新プログラムがあります。1 つは春に、もう 1 つは秋に行われます。</span><span class="sxs-lookup"><span data-stu-id="36479-113">The operating system update cadence for HoloLens 2 matches that of Windows 10; there are two updates per year, one taking place in Spring and the other in Fall.</span></span> <span data-ttu-id="36479-114">OS の更新中におけるデバイスのセキュリティ確保の詳細については、「[状態の分離と隔離](security-state-separation-isolation.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="36479-114">For more on how devices are secured during OS updates, see [State separation and isolation](security-state-separation-isolation.md).</span></span> 

<span data-ttu-id="36479-115">IT 管理者は、更新ポリシーの詳細について、「[ポリシー CSP - 更新プログラム](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="36479-115">IT admins can learn more about update policy at [Policy CSP - Update](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update).</span></span> 
