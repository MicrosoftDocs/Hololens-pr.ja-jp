---
title: 管理者不要のオペレーティング システム セキュリティ
description: 管理者不要のオペレーティング システム、デバイス所有者、および HoloLens Mixed Reality デバイスでのセキュリティについて説明します。
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
ms.openlocfilehash: 972bbc689505d42993cf47d82351ceeb79a0606b
ms.sourcegitcommit: 257720deb27f3bbc301175ce2a4afa79001862d3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2021
ms.locfileid: "11440338"
---
# <a name="admin-less-operating-system"></a><span data-ttu-id="ebedd-104">管理者不要のオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="ebedd-104">Admin-less operating system</span></span>

<span data-ttu-id="ebedd-105">HoloLens 2 は、管理者グループのサポートを無効にして、すべてのサードパーティ UWP アプリケーション コードを AppContainer サンドボックス内で標準ユーザーとしてのみ実行できるようにすることで、特権昇格の対象領域を最小化します。</span><span class="sxs-lookup"><span data-stu-id="ebedd-105">HoloLens 2 minimizes the surface area for privilege escalation by disabling support for the Administrators group and limiting all third-party UWP application code to only execute as standard users within the AppContainer sandbox.</span></span> <span data-ttu-id="ebedd-106">このコードには、すべての AppContainers がアクセスできるリソースだけでなく、昇格されていないユーザーに対する、アプリケーションで明示的に指定された機能によって保護されたリソースへのアクセス権のみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="ebedd-106">This code is only granted access to those resources protected by capabilities explicitly manifested in the application for an unelevated user in addition to resources accessible to all AppContainers.</span></span>
<span data-ttu-id="ebedd-107">これらのアプリケーション機能には、引き続き 3 階層の分類モデルがあります。</span><span class="sxs-lookup"><span data-stu-id="ebedd-107">These application capabilities continue to have the three-tiered classification model:</span></span>
  * <span data-ttu-id="ebedd-108">全般的な情報</span><span class="sxs-lookup"><span data-stu-id="ebedd-108">General</span></span>
  * <span data-ttu-id="ebedd-109">制限されます</span><span class="sxs-lookup"><span data-stu-id="ebedd-109">Restricted</span></span>
  * <span data-ttu-id="ebedd-110">Windows</span><span class="sxs-lookup"><span data-stu-id="ebedd-110">Windows</span></span>

<span data-ttu-id="ebedd-111">Windows コンポーネントは、システム UWP を介して AppContainer サンドボックスを利用することもできます。</span><span class="sxs-lookup"><span data-stu-id="ebedd-111">Windows components can also leverage the AppContainer sandbox through System UWPs.</span></span> <span data-ttu-id="ebedd-112">ユニバーサル Windows プラットフォーム (UWP) の詳細については、「[UWP ドキュメント](https://docs.microsoft.com/windows/uwp/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebedd-112">To learn more about Universal Windows Platform (UWP), see [UWP documentation](https://docs.microsoft.com/windows/uwp/).</span></span> <span data-ttu-id="ebedd-113">また、特権を削減する必要がある Windows コンポーネント (ブラウザーのコンテンツ ページ、またはパーサーなど) は、すべての AppContainers がアクセスできるリソースのセットへのアクセスを遮断する、Less Privileged AppContainer (LPAC) サンドボックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="ebedd-113">Additionally, Windows components with greater privilege reduction needs (like browser content pages or parsers) use the Less Privileged AppContainer (LPAC) sandbox, which cuts off access to the set of resources accessible to all AppContainers.</span></span>

## <a name="device-owner"></a><span data-ttu-id="ebedd-114">デバイスの所有者</span><span class="sxs-lookup"><span data-stu-id="ebedd-114">Device owner</span></span>

<span data-ttu-id="ebedd-115">最後に、デバイスのテナントへの参加やユーザーの管理など、特定のデバイス全体の操作の実行は、"デバイス オーナー" にのみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="ebedd-115">Finally, the execution of specific device-wide operations, such as joining the device to a tenant or user management, is only permitted for “device owners”.</span></span> <span data-ttu-id="ebedd-116">デバイス上のユーザーは、次のいずれかの手順でこのグループに入ることができます。</span><span class="sxs-lookup"><span data-stu-id="ebedd-116">This group is populated by users on the device through one of the following steps:</span></span>
  * <span data-ttu-id="ebedd-117">デバイスの最初のユーザーは、常にオーナーとして指定されます。</span><span class="sxs-lookup"><span data-stu-id="ebedd-117">The first user on the device is always designated an Owner.</span></span> 
> [!IMPORTANT]
><span data-ttu-id="ebedd-118">Azure AD ユーザーの場合、このルールの例外は、デバイスが Azure AD でオートパイロットまたは非実ユーザーを使用するバルク Azure AD を介して参加している場合です。</span><span class="sxs-lookup"><span data-stu-id="ebedd-118">For Azure AD Users, the exception to this rule is that if the device is Azure AD joined via Autopilot or bulk Azure AD enrollment, which uses a non-real user.</span></span> <span data-ttu-id="ebedd-119">この場合、Azure portal で"グローバル管理者"または"デバイス管理者"の役割が割り当てられていない限り、デバイスにサインインする最初の AAD ユーザーを自動的にデバイスの所有者にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ebedd-119">In this case, the first AAD user to sign into the device may not be made device owner automatically unless that user has the "global administrator" or "device administrator" role assigned in Azure portal.</span></span> <span data-ttu-id="ebedd-120">詳細については、次の表をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ebedd-120">For more information, see the note below.</span></span>  

  * <span data-ttu-id="ebedd-121">ユーザーがデバイス上の別のオーナーによって設定 UX からオーナーに昇格された場合。</span><span class="sxs-lookup"><span data-stu-id="ebedd-121">When a user is promoted to be an Owner from the Settings UX by another Owner on the device.</span></span>
  * <span data-ttu-id="ebedd-122">デバイスの所有者が利用できなくなった場合 (会社を離れた)、かつデバイスが Azure AD に参加している場合、テナント管理者は Azure portal でデバイスの所有者を新しいユーザーに変更できます。</span><span class="sxs-lookup"><span data-stu-id="ebedd-122">If the device owner is no longer available (leaves the company) and the device is Azure AD joined, the Tenant Admin can change the device owner to a new user in Azure portal.</span></span> <span data-ttu-id="ebedd-123">Azure AD テナントのグローバル管理者とデバイス管理者は、前の手順を必要とせずに、デバイスの所有者として暗黙の内にサインインされます。</span><span class="sxs-lookup"><span data-stu-id="ebedd-123">Global Administrators and Device Administrators of an Azure AD tenant are implicitly signed in as Owners on the device without requiring either of the previous steps.</span></span>  

 <span data-ttu-id="ebedd-124">IT 管理者は [プライバシー](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) ポリシーを使用して、アクセスできるアプリを管理できます。</span><span class="sxs-lookup"><span data-stu-id="ebedd-124">IT administrators can manage what apps can access through [Privacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) policies.</span></span> 

> [!NOTE]
> <span data-ttu-id="ebedd-125">Azure AD に参加しているデバイスでデバイスの所有者になるユーザーの詳細については、[「ローカル管理者の割り当て」のドキュメント](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin)を参照してください (ただし、管理者は HoloLens に存在しないので、「ローカル管理者」を「デバイスの所有者」としてお読みください)。</span><span class="sxs-lookup"><span data-stu-id="ebedd-125">To understand more about who is made a device owner on an Azure AD joined device, see [“Assign Local Admin” documentation](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) (but read ‘local admin’ as ‘device owner’ since admin does not exist on HoloLens).</span></span>