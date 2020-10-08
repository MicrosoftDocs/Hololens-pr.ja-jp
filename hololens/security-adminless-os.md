---
title: セキュリティ adminless os
description: adminless os および hololens セキュリティ
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: セキュリティ、hololens、adminless、管理者不要、オペレーティング システム、管理者不要のオペレーティング システム、管理 os、管理者不要の os、hololens 2、hololens2 セキュリティ、
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: c7c54c624fe2e1c48eee468e2d30fe3460f7e786
ms.sourcegitcommit: 5877c3e51de49f949b35ab840a3312a009a4487a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "11102316"
---
# <span data-ttu-id="379b0-104">管理者不要のオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="379b0-104">Admin-less operating system</span></span>

<span data-ttu-id="379b0-105">HoloLens 2 は、管理者グループのサポートを無効にして、すべてのサードパーティ UWP アプリケーション コードを AppContainer サンドボックス内で標準ユーザーとしてのみ実行できるようにすることで、特権昇格の対象領域を最小化します。</span><span class="sxs-lookup"><span data-stu-id="379b0-105">HoloLens 2 minimizes the surface area for privilege escalation by disabling support for the Administrators group and limiting all third-party UWP application code to only execute as standard users within the AppContainer sandbox.</span></span> <span data-ttu-id="379b0-106">このコードには、すべての AppContainers がアクセスできるリソースだけでなく、昇格されていないユーザーに対する、アプリケーションで明示的に指定された機能によって保護されたリソースへのアクセス権のみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="379b0-106">This code is only granted access to those resources protected by capabilities explicitly manifested in the application for an unelevated user in addition to resources accessible to all AppContainers.</span></span>
<span data-ttu-id="379b0-107">これらのアプリケーション機能には、引き続き 3 階層の分類モデルがあります。</span><span class="sxs-lookup"><span data-stu-id="379b0-107">These application capabilities continue to have the three-tiered classification model:</span></span>
  * <span data-ttu-id="379b0-108">全般的な情報</span><span class="sxs-lookup"><span data-stu-id="379b0-108">General</span></span>
  * <span data-ttu-id="379b0-109">制限されます</span><span class="sxs-lookup"><span data-stu-id="379b0-109">Restricted</span></span>
  * <span data-ttu-id="379b0-110">Windows</span><span class="sxs-lookup"><span data-stu-id="379b0-110">Windows</span></span>

<span data-ttu-id="379b0-111">Windows コンポーネントは、システム UWP を介して AppContainer サンドボックスを利用することもできます。</span><span class="sxs-lookup"><span data-stu-id="379b0-111">Windows components can also leverage the AppContainer sandbox through System UWPs.</span></span> <span data-ttu-id="379b0-112">ユニバーサル Windows プラットフォーム (UWP) の詳細については、「[UWP ドキュメント](https://docs.microsoft.com/windows/uwp/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="379b0-112">To learn more about Universal Windows Platform (UWP), see [UWP documentation](https://docs.microsoft.com/windows/uwp/).</span></span> <span data-ttu-id="379b0-113">また、特権を削減する必要がある Windows コンポーネント (ブラウザーのコンテンツ ページ、パーサーなど) は、すべての AppContainers がアクセスできるリソースのセットへのアクセスを遮断する、Less Privileged AppContainer (LPAC) サンドボックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="379b0-113">Additionally, Windows components with greater privilege reduction needs (e.g. browser content pages, parsers) use the Less Privileged AppContainer (LPAC) sandbox which cuts off access to the set of resources accessible to all AppContainers.</span></span>

## <span data-ttu-id="379b0-114">デバイスの所有者</span><span class="sxs-lookup"><span data-stu-id="379b0-114">Device owner</span></span>

<span data-ttu-id="379b0-115">最後に、デバイスのテナントへの参加やユーザーの管理など、特定のデバイス全体の操作の実行は、"デバイス オーナー" にのみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="379b0-115">Finally, the execution of specific device-wide operations, such as joining the device to a tenant or user management, is only permitted for “device owners”.</span></span> <span data-ttu-id="379b0-116">デバイス上のユーザーは、次のいずれかの手順でこのグループに入ることができます。</span><span class="sxs-lookup"><span data-stu-id="379b0-116">This group is populated by users on the device through one of the following steps:</span></span>
  * <span data-ttu-id="379b0-117">デバイスの最初のユーザーは、常にオーナーとして指定されます。</span><span class="sxs-lookup"><span data-stu-id="379b0-117">The first user on the device is always designated an Owner.</span></span> 
    * <span data-ttu-id="379b0-118">このルールの例外は、デバイスが AAD 結合されている場合、結合を実行したユーザーがデバイス オーナーになることです。</span><span class="sxs-lookup"><span data-stu-id="379b0-118">The exception to this rule is that if the device is AAD joined, the user that performed the join is made device owner.</span></span> <span data-ttu-id="379b0-119">たとえば、デバイスが自動操縦によって AAD 結合されている場合、デバイスに最初にサインインしているユーザーはデバイスに対して AAD 結合を行わないので、デバイス オーナーにはなりません。</span><span class="sxs-lookup"><span data-stu-id="379b0-119">This is applicable, for example, if a device is AAD joined via Autopilot in which case the first user to sign into the device did not AAD join the device and therefore will not be made a device owner.</span></span> <span data-ttu-id="379b0-120">AAD 結合しているデバイスのデバイス オーナーについての詳細については、["ローカル管理者に割り当てる" の](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin)ドキュメントをご覧ください。(ただし、HoloLens には管理者が存在しないため、「ローカル管理者」を「デバイス オーナー」とみなします)。</span><span class="sxs-lookup"><span data-stu-id="379b0-120">To understand more about who is made a device owner on an AAD joined device, see [“Assign Local Admin” documentation](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) (but read ‘local admin’ as ‘device owner’ since admin does not exist on HoloLens).</span></span>
  * <span data-ttu-id="379b0-121">ユーザーがデバイス上の別のオーナーによって設定 UX からオーナーに昇格された場合。</span><span class="sxs-lookup"><span data-stu-id="379b0-121">When a user is promoted to be an Owner from Settings UX by another Owner on the device.</span></span>
  * <span data-ttu-id="379b0-122">デバイス オーナーが利用できなくなった場合 (会社を退職した場合など)、デバイスが AAD 結合されている場合、テナント管理者は、Azure ポータルでデバイス オーナーを新しいユーザーに変更できます。</span><span class="sxs-lookup"><span data-stu-id="379b0-122">If the device owner is no longer available (e.g. leaves the company) and the device is AAD joined, the Tenant Admin can change the device owner to a new user in Azure Portal.</span></span>
<span data-ttu-id="379b0-123">Azure AD テナントのグローバル管理者は、前の手順を必要とせずに、デバイスの所有者として暗黙の内にサインインされます。</span><span class="sxs-lookup"><span data-stu-id="379b0-123">Global Administrators of an Azure AD tenant are implicitly signed in as Owners on the device without requiring either of the previous steps.</span></span> 

<span data-ttu-id="379b0-124">IT 管理者は [プライバシー](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) ポリシーを使用して、アクセスできるアプリを管理できます。</span><span class="sxs-lookup"><span data-stu-id="379b0-124">IT administrators can manage what apps can access through [Privacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) policies.</span></span> 
