---
title: 展開ガイド - リモート アシストによるクラウド接続 HoloLens 2 の大規模な展開 - 構成
description: クラウド接続ネットワークを使用して HoloLens デバイスを登録する構成を設定する方法
keywords: HoloLens, 管理, クラウド接続, リモート アシスト, AAD, Azure AD, MDM, モバイル デバイス管理
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 042a29fe436b21ca37a2fcd7921fc53d6a9686d5
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253044"
---
# <span data-ttu-id="741c4-104">構成 - クラウド接続ガイド</span><span class="sxs-lookup"><span data-stu-id="741c4-104">Configure - Cloud connected Guide</span></span>

<span data-ttu-id="741c4-105">このガイドのセクションでは、&#39;の自動登録の設定方法と、Intune とリモート アシストの両方にライセンスを適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="741c4-105">In this section of the guide, we&#39;ll go over how to set up Auto Enrollment for your tenant, and how to apply licenses for both Intune and Remote Assist.</span></span>

## <span data-ttu-id="741c4-106">Azure ユーザーとグループ</span><span class="sxs-lookup"><span data-stu-id="741c4-106">Azure Users and Groups</span></span>

<span data-ttu-id="741c4-107">Azure と Intune をその拡張機能で使用すると、ユーザーとグループを使用して構成とライセンスを割り当てるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="741c4-107">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="741c4-108">この展開フローを検証し、あるユーザーから別のユーザーへのリモート アシスト呼び出しを行&#39;2 つのユーザー アカウントが必要になります。</span><span class="sxs-lookup"><span data-stu-id="741c4-108">For the sake of validating this deployment flow and being able to make a Remote Assist call from one user to another you&#39;ll need two user accounts.</span></span>

<span data-ttu-id="741c4-109">ライセンスを割り当てる目的で、1 つのユーザー グループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="741c4-109">We can make a single user group for the purpose of assigning licenses.</span></span> <span data-ttu-id="741c4-110">両方のユーザーを同じグループに参加し、Intune とリモート アシストのライセンスをそのグループに適用できます。</span><span class="sxs-lookup"><span data-stu-id="741c4-110">We can join both users to the same group and apply a license for Intune and Remote Assist to that group.</span></span>

<span data-ttu-id="741c4-111">1 つのユーザー&#39;内の 2 つの Azure ADアカウントにまだアクセスできない場合は、次の方法を使用できます。以下にクイック スタート ガイドを示します。</span><span class="sxs-lookup"><span data-stu-id="741c4-111">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="741c4-112">ユーザーを作成する方法</span><span class="sxs-lookup"><span data-stu-id="741c4-112">How to create a user</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="741c4-113">グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="741c4-113">How to create a group</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="741c4-114">[グループにユーザーを追加する](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) - 作成したユーザーを追加してグループを作成する</span><span class="sxs-lookup"><span data-stu-id="741c4-114">[Add users to a group](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="741c4-115">[Azure AD](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) を構成して、ユーザー グループがデバイスに参加するようにします。新しいユーザー グループに、Azure AD にデバイスを登録するアクセス許可を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="741c4-115">[Configure Azure AD to allow a User Group to join devices](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <span data-ttu-id="741c4-116">HoloLens 2 の自動登録</span><span class="sxs-lookup"><span data-stu-id="741c4-116">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="741c4-117">スムーズでシームレスなエクスペリエンスを実現するには、Azure Active Directory Join (AADJ) と Auto Enrollment to Intune for HoloLens 2 デバイスをセットアップする方法があります。</span><span class="sxs-lookup"><span data-stu-id="741c4-117">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="741c4-118">これにより、ユーザーは OOBE 中に組織のログイン資格情報を入力し、Azure AD に自動的に登録し、デバイスを MDM に登録できます。</span><span class="sxs-lookup"><span data-stu-id="741c4-118">This will allow users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="741c4-119">Microsoft Endpoint [Manager を使用](https://endpoint.microsoft.com/#home)すると、サービスを選択し、[プレミアム評価版を取得] を選択できるまで、いくつかのページを移動できます。</span><span class="sxs-lookup"><span data-stu-id="741c4-119">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="741c4-120">自動登録 P1 では Azure Active Directory Premium 1 と Azure Active Directory Premium 2 で十分です。</span><span class="sxs-lookup"><span data-stu-id="741c4-120">You may notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="741c4-121">Intune を選択し、自動登録のユーザー スコープを選択し、以前に作成したグループを選択できます。</span><span class="sxs-lookup"><span data-stu-id="741c4-121">We can select Intune and select the user scope for automatic enrollment, and select the group that was previously created.</span></span>

<span data-ttu-id="741c4-122">詳細と手順については、Intune の自動登録を有効にする [方法に関するガイドを参照してください](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="741c4-122">For full details and steps read the guide on [how to enable auto enrollment for Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <span data-ttu-id="741c4-123">アプリケーション ライセンス</span><span class="sxs-lookup"><span data-stu-id="741c4-123">Application Licenses</span></span>

<span data-ttu-id="741c4-124">アプリケーション ライセンスを使用すると、ユーザーは会社が購入したアプリをインストールするか、無料試用版からアプリの完全版にアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="741c4-124">An application license allows a user to either install company purchased Apps or upgrade from a free trial to the full version of an app.</span></span> <span data-ttu-id="741c4-125">アプリケーション ライセンスは、ユーザー、ユーザー グループ、またはデバイス グループに適用できます。</span><span class="sxs-lookup"><span data-stu-id="741c4-125">Application licenses can be applied to either users, user groups, or device groups.</span></span> <span data-ttu-id="741c4-126">リモート&#39;を使用するには、組織内のユーザーのリモート アシスト ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="741c4-126">You&#39;ll need Remote Assist licenses for users in your organization to use Remote Assist.</span></span> <span data-ttu-id="741c4-127">このガイドの目的上、上記の Azure ユーザーとグループで作成したユーザー グループにリモート アシスト ライセンス [を割り当てる必要があります](hololens2-cloud-connected-configure.md#azure-users-and-groups)。</span><span class="sxs-lookup"><span data-stu-id="741c4-127">For the purpose of this guide we'll assign Remote Assist licenses to the user group we created above in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span></span>

<span data-ttu-id="741c4-128">ライセンスの要件は、ユーザーがデバイスからリモート アシスト通話を行うのか、Microsoft Teams のリモートコラボレーターになるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="741c4-128">The requirements for licenses can be different depending on if the user will be making the Remote Assist call from a device or will be a remote collaborator from Microsoft Teams.</span></span> <span data-ttu-id="741c4-129">既定では、リモート アシストと Teams の両方のチェック ボックスがマークされます。</span><span class="sxs-lookup"><span data-stu-id="741c4-129">By default the Remote Assist and Teams check boxes are both marked.</span></span> <span data-ttu-id="741c4-130">このガイドの目的上、既定のチェック ボックスはオンのままにしてください。</span><span class="sxs-lookup"><span data-stu-id="741c4-130">For the purposes of this guide, we suggest leaving the default boxes checked.</span></span>

1. <span data-ttu-id="741c4-131">ロールごとのさまざまなライセンス要件と製品 [要件について説明します](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)。</span><span class="sxs-lookup"><span data-stu-id="741c4-131">Learn more about the different [Licensing and product requirements per role](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span></span> <span data-ttu-id="741c4-132">リモート アシスト ライセンスにはいくつかの種類があります。そのため、必要に応じて適切なライセンスを取得してください。</span><span class="sxs-lookup"><span data-stu-id="741c4-132">There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.</span></span>
2. <span data-ttu-id="741c4-133">ライセンス&#39;取得する [必要があります](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)。</span><span class="sxs-lookup"><span data-stu-id="741c4-133">You&#39;ll need to [acquire the license](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span></span>
3. <span data-ttu-id="741c4-134">[グループにライセンス](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) を適用します。</span><span class="sxs-lookup"><span data-stu-id="741c4-134">[Apply your licenses](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) to the group.</span></span>

## <span data-ttu-id="741c4-135">次のステップ</span><span class="sxs-lookup"><span data-stu-id="741c4-135">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="741c4-136">クラウド接続展開 - 展開</span><span class="sxs-lookup"><span data-stu-id="741c4-136">Cloud connected deployment - Deploy</span></span>](hololens2-cloud-connected-deploy.md)