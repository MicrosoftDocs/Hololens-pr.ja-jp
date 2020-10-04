---
title: グローバルに割り当てられた
description: グローバルに割り当てられた Access キオスク向けの OMA URI の使用ガイド
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens、hololens 2、割り当てられたアクセス、kiosk
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 9c7e4e37b54e6dd81341a64165e1e742a2242d00
ms.sourcegitcommit: a0f6ff5c36aab0ed94e16e136728e4b8753203db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2020
ms.locfileid: "11093937"
---
# <span data-ttu-id="3e856-104">グローバルに割り当てられたアクセス-キオスク</span><span class="sxs-lookup"><span data-stu-id="3e856-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="3e856-105">この機能は、システムレベルで適用可能なマルチアプリキオスクモード用に Hololens 2 デバイスを構成します。システム上のID とのアフィニティはありません。また、デバイスにサインインするすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3e856-105">This feature configures Hololens 2 device for multiple app kiosk mode which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span> 

> [!NOTE]
> <span data-ttu-id="3e856-106">この機能は現在、Windows Insider ビルドでのみ利用可能です。 </span><span class="sxs-lookup"><span data-stu-id="3e856-106">This feature is currently only avalible in Windows Insider builds.</span></span> <span data-ttu-id="3e856-107">HoloLensリリースで一般に利用可能になる前にこの機能を試してみたい場合は、[Windows Insider](hololens-insider.md)ビルドの詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3e856-107">If you would like to try this feature before it is generally avalible in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>
 
## <span data-ttu-id="3e856-108">Intuneでこれを使用する方法</span><span class="sxs-lookup"><span data-stu-id="3e856-108">How to use this in Intune?</span></span> 

> [!NOTE]
> <span data-ttu-id="3e856-109">[<!-] が付いている領域に注意してください。</span><span class="sxs-lookup"><span data-stu-id="3e856-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="3e856-110">これらの領域には、ユーザー設定に基づいて変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e856-110">These areas will require you to make modifications based on your preferences.</span></span> 

1.  <span data-ttu-id="3e856-111">次のようにカスタム OMA URI デバイス構成プロファイルを作成し、HoloLens デバイスグループに適用します。</span><span class="sxs-lookup"><span data-stu-id="3e856-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group:</span></span> 

    <span data-ttu-id="3e856-112">URI 値: .Device/Vendor/MSFT/AssignedAccess/Configuration</span><span class="sxs-lookup"><span data-stu-id="3e856-112">URI value: .Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>
   
    > [!div class="mx-imgBorder"]
    > ![Intune のグローバル割り当てアクセス OMA - URI](images/global-assigned-access-omauri.png)

2.  <span data-ttu-id="3e856-114">値については、以下の内容を更新して貼り付けます:</span><span class="sxs-lookup"><span data-stu-id="3e856-114">For value, update and paste following content:</span></span> 

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <span data-ttu-id="3e856-115">Windows 構成デザイナーでこれを使用する方法</span><span class="sxs-lookup"><span data-stu-id="3e856-115">How to use this in Windows Configuration Designer?</span></span> 
 
1.  <span data-ttu-id="3e856-116">上記のXML blob を XML ファイルとして更新して保存します。</span><span class="sxs-lookup"><span data-stu-id="3e856-116">Update and save XML blob mentioned above as XML file.</span></span> 

2.  <span data-ttu-id="3e856-117">[プロビジョニングパッケージを使用して、単一アプリまたはマルチアプリキオスクをセットアップする](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) の手順に従います。特にセクション "Prov について。</span><span class="sxs-lookup"><span data-stu-id="3e856-117">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="3e856-118">パッケージ、ステップ 2-キオスクの構成 XML ファイルをプロビジョニングパッケージに追加し、前の手順で保存された XML ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="3e856-118">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span> 

## <span data-ttu-id="3e856-119">グローバルが全員に適用され、個別の構成が 1 つの AAD アカウントまたは AAD グループに適用される構成を作成できますか?</span><span class="sxs-lookup"><span data-stu-id="3e856-119">Can I create a configuration where global applies to everyone and separate configuration applies to 1 AAD account or AAD group?</span></span> 

<span data-ttu-id="3e856-120">はい。以下の XML blog の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e856-120">Yes, please refer to the example XML blob below.</span></span> <span data-ttu-id="3e856-121">グローバルに割り当てられたアクセスプロファイルは、サインインしたユーザーの特定のプロファイルが見つからない場合に Hololens に適用されるため、サインインしたユーザーの既定キオスクモードの構成になっています。</span><span class="sxs-lookup"><span data-stu-id="3e856-121">Global Assigned Access profile is applied on Hololens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span> <span data-ttu-id="3e856-122">使用する XML blob の例を表示します。</span><span class="sxs-lookup"><span data-stu-id="3e856-122">Here is an example of XML blob to be used:</span></span> 

> [!NOTE]
> <span data-ttu-id="3e856-123">`<!-`でマークされた、強調表示された領域に注意してください。</span><span class="sxs-lookup"><span data-stu-id="3e856-123">Please be aware of the highlighted areas marked with `<!-`.</span></span> <span data-ttu-id="3e856-124">これらの領域には、ユーザー設定に基づいて変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e856-124">These areas will require you to make modifications based on your preferences.</span></span> 

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <span data-ttu-id="3e856-125">デバイスの所有者をグローバルに割り当てられているアクセスプロファイルから除外する</span><span class="sxs-lookup"><span data-stu-id="3e856-125">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="3e856-126">この機能を使用すると、Hololens の 「[デバイス所有者](security-adminless-os.md)」 と見なされているユーザーは、グローバルに割り当てられたアクセスから除外されます。</span><span class="sxs-lookup"><span data-stu-id="3e856-126">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on Hololens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="3e856-127">この機能を利用するには、マルチアプリキオスク構成用の XML blob で、強調表示されている行を追加します。</span><span class="sxs-lookup"><span data-stu-id="3e856-127">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span> 

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::
 
