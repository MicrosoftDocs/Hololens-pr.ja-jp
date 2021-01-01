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
ms.openlocfilehash: f91b77be846b585de8d89c17e516923f97304d57
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253204"
---
# <span data-ttu-id="75812-104">グローバルに割り当てられたアクセス-キオスク</span><span class="sxs-lookup"><span data-stu-id="75812-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="75812-105">この機能は、システム レベルで適用可能な複数のアプリ キオスク モード用に HoloLens 2 デバイスを構成し、システム上の ID とのアフィニティを持たず、デバイスにサインインするユーザー全員に適用されます。</span><span class="sxs-lookup"><span data-stu-id="75812-105">This feature configures HoloLens 2 device for multiple app kiosk mode, which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span>

> [!NOTE]
> <span data-ttu-id="75812-106">この機能は現在、Windows Insider ビルドでのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="75812-106">This feature is currently only available in Windows Insider builds.</span></span> <span data-ttu-id="75812-107">HoloLens リリースで一般公開される前にこの機能を試す場合は [、Windows Insider](hololens-insider.md) ビルドの詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="75812-107">If you would like to try this feature before it is generally available in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>

## <span data-ttu-id="75812-108">Intune でグローバルに割り当てられたアクセスを使用する方法</span><span class="sxs-lookup"><span data-stu-id="75812-108">How to use Global Assigned Access in Intune?</span></span>

> [!NOTE]
> <span data-ttu-id="75812-109">[<!-] が付いている領域に注意してください。</span><span class="sxs-lookup"><span data-stu-id="75812-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="75812-110">これらの領域には、ユーザー設定に基づいて変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75812-110">These areas will require you to make modifications based on your preferences.</span></span>

1. <span data-ttu-id="75812-111">次のようにカスタム OMA URI デバイス構成プロファイルを作成し、HoloLens デバイスグループに適用します。</span><span class="sxs-lookup"><span data-stu-id="75812-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group:</span></span>

    <span data-ttu-id="75812-112">URI 値: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span><span class="sxs-lookup"><span data-stu-id="75812-112">URI value: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>

    > [!div class="mx-imgBorder"]
    > ![Intune のグローバル割り当てアクセス OMA - URI](images/global-assigned-access-omauri.png)

2. <span data-ttu-id="75812-114">値については、以下の内容を更新して貼り付けます:</span><span class="sxs-lookup"><span data-stu-id="75812-114">For value, update and paste following content:</span></span>

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <span data-ttu-id="75812-115">Windows 構成デザイナーでグローバルに割り当てられたアクセスを使用する方法</span><span class="sxs-lookup"><span data-stu-id="75812-115">How to use Global Assigned Access in Windows Configuration Designer?</span></span>

1. <span data-ttu-id="75812-116">上記のXML blob を XML ファイルとして更新して保存します。</span><span class="sxs-lookup"><span data-stu-id="75812-116">Update and save XML blob mentioned above as XML file.</span></span> 

2. <span data-ttu-id="75812-117">[プロビジョニングパッケージを使用して、単一アプリまたはマルチアプリキオスクをセットアップする](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) の手順に従います。特にセクション "Prov について。</span><span class="sxs-lookup"><span data-stu-id="75812-117">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="75812-118">パッケージ、ステップ 2-キオスクの構成 XML ファイルをプロビジョニングパッケージに追加し、前の手順で保存された XML ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="75812-118">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span>

## <span data-ttu-id="75812-119">グローバルがすべてのユーザーに適用され、個別の構成が 1 つの Azure AD アカウントまたは Azure AD グループに適用される構成を作成できますか?</span><span class="sxs-lookup"><span data-stu-id="75812-119">Can I create a configuration where global applies to everyone and separate configuration applies to 1 Azure AD account or Azure AD group?</span></span> 

<span data-ttu-id="75812-120">はい、以下の XML BLOB の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75812-120">Yes, refer to the example XML blob below.</span></span> <span data-ttu-id="75812-121">グローバルに割り当てられたアクセス プロファイルは、サインインしているユーザーの特定のプロファイルが見つからない場合に HoloLens に適用されます。そのため、サインインしているユーザーの既定のキオスク モード構成です。</span><span class="sxs-lookup"><span data-stu-id="75812-121">Global Assigned Access profile is applied on HoloLens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span>
<span data-ttu-id="75812-122">使用する XML blob の例を表示します。</span><span class="sxs-lookup"><span data-stu-id="75812-122">Here is an example of XML blob to be used:</span></span>

> [!NOTE]
> <span data-ttu-id="75812-123">`<!-`でマークされた、強調表示された領域に注意してください。</span><span class="sxs-lookup"><span data-stu-id="75812-123">Please be aware of the highlighted areas marked with `<!-`.</span></span> <span data-ttu-id="75812-124">これらの領域には、ユーザー設定に基づいて変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75812-124">These areas will require you to make modifications based on your preferences.</span></span>

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <span data-ttu-id="75812-125">デバイスの所有者をグローバルに割り当てられているアクセスプロファイルから除外する</span><span class="sxs-lookup"><span data-stu-id="75812-125">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="75812-126">この機能を使用すると、HoloLens で "[デバイスの所有者](security-adminless-os.md)" と見なされるユーザーをグローバルに割り当てられたアクセスから除外できます。</span><span class="sxs-lookup"><span data-stu-id="75812-126">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on HoloLens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="75812-127">この機能を利用するには、マルチアプリキオスク構成用の XML blob で、強調表示されている行を追加します。</span><span class="sxs-lookup"><span data-stu-id="75812-127">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span>

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <span data-ttu-id="75812-128">他のグローバルに割り当てられたアクセスの例</span><span class="sxs-lookup"><span data-stu-id="75812-128">Additional Global Assigned Access Examples</span></span>

<span data-ttu-id="75812-129">これは、グローバルに割り当てられたアクセス キオスクの例で、ユーザーがサインインすると、設定アプリ、フィードバック Hub、Microsoft Edge で複数アプリのキオスクを使用できます。</span><span class="sxs-lookup"><span data-stu-id="75812-129">This is an example Global Assigned Access kiosk that when any user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

<span data-ttu-id="75812-130">この例は、デバイスの所有者を除外するグローバルに割り当てられたアクセス キオスクです。他の Azure AD ユーザーがサインインすると、設定アプリ、フィードバック Hub、および Microsoft Edge を使って複数アプリのキオスクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="75812-130">This example is a Global Assigned Access kiosk that excludes the device owner, when any other Azure AD user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span> <span data-ttu-id="75812-131">このキオスクには、ゲストのアカウントに対するセカンダリ キオスク構成も含まれます。これは、ロック画面で誰でもサインイン可能です。</span><span class="sxs-lookup"><span data-stu-id="75812-131">This kiosk also includes a secondary kiosk configuration for a Visitor account, which may be signed into by anyone on the lock screen.</span></span> <span data-ttu-id="75812-132">ユーザーがゲストのアカウントにサインインすると、フィードバック Hub アプリのみを含むマルチアプリ キオスクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="75812-132">When a user signs into the Visitor account they will have a multi-app kiosk that only has the Feedback Hub app.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
