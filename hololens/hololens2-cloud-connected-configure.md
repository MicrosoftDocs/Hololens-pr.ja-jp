---
title: デプロイガイド–リモートアシスタンスを使用した大規模なクラウド接続 HoloLens 2 デプロイ
description: リモートアシスタンスを使用して大規模にクラウドに接続されたネットワーク経由でデバイス HoloLens 登録するように構成する方法について説明します。
keywords: HoloLens、管理、クラウド接続、リモートアシスタンス、AAD、Azure AD、MDM、モバイルデバイス管理
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
ms.openlocfilehash: eb96f1cdc799551297c0373268e8cc8f35c6bd06
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635145"
---
# <a name="configure---cloud-connected-guide"></a><span data-ttu-id="c255e-104">構成-クラウド接続ガイド</span><span class="sxs-lookup"><span data-stu-id="c255e-104">Configure - Cloud connected Guide</span></span>

<span data-ttu-id="c255e-105">ガイドのこのセクションでは、テナントの自動登録を設定する方法と、Intune とリモートアシスタンスの両方にライセンスを適用する方法について&#39;説明します。</span><span class="sxs-lookup"><span data-stu-id="c255e-105">In this section of the guide, we&#39;ll go over how to set up Auto Enrollment for your tenant, and how to apply licenses for both Intune and Remote Assist.</span></span>

## <a name="azure-users-and-groups"></a><span data-ttu-id="c255e-106">Azure のユーザーとグループ</span><span class="sxs-lookup"><span data-stu-id="c255e-106">Azure Users and Groups</span></span>

<span data-ttu-id="c255e-107">その拡張機能による Azure および Intune では、ユーザーとグループを使用して、構成とライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c255e-107">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="c255e-108">この展開フローを検証し、あるユーザーから別のユーザーにリモートアシスタンス呼び出しを行うことができるようにするには&#39;2 つのユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="c255e-108">For the sake of validating this deployment flow and being able to make a Remote Assist call from one user to another you&#39;ll need two user accounts.</span></span>

<span data-ttu-id="c255e-109">ライセンスを割り当てる目的で、1つのユーザーグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c255e-109">We can make a single user group for the purpose of assigning licenses.</span></span> <span data-ttu-id="c255e-110">両方のユーザーを同じグループに参加させ、Intune と Remote Assist のライセンスをそのグループに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="c255e-110">We can join both users to the same group and apply a license for Intune and Remote Assist to that group.</span></span>

<span data-ttu-id="c255e-111">ユーザーグループ内の2つの Azure AD アカウントに既にアクセス権がある&#39;は、次のように使用できます。次に、のクイックスタートガイドを示します。</span><span class="sxs-lookup"><span data-stu-id="c255e-111">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="c255e-112">ユーザーを作成する方法</span><span class="sxs-lookup"><span data-stu-id="c255e-112">How to create a user</span></span>](/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="c255e-113">グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="c255e-113">How to create a group</span></span>](/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="c255e-114">[グループへのユーザーの追加](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) –作成されたユーザーをグループの作成に追加する</span><span class="sxs-lookup"><span data-stu-id="c255e-114">[Add users to a group](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="c255e-115">[ユーザーグループがデバイスを参加できるように Azure AD を構成](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) する–新しいユーザーグループにデバイスを登録するアクセス許可があることを確認し Azure AD</span><span class="sxs-lookup"><span data-stu-id="c255e-115">[Configure Azure AD to allow a User Group to join devices](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <a name="auto-enrollment-on-hololens-2"></a><span data-ttu-id="c255e-116">HoloLens 2 での自動登録</span><span class="sxs-lookup"><span data-stu-id="c255e-116">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="c255e-117">スムーズでシームレスなエクスペリエンスを実現するために、HoloLens 2 デバイスに対して Azure Active Directory Join (aadj) と Intune への自動登録を設定する方法があります。</span><span class="sxs-lookup"><span data-stu-id="c255e-117">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="c255e-118">これにより、OOBE 中に組織のログイン資格情報を入力し、Azure AD に自動的に登録して、デバイスを MDM に登録できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c255e-118">This will allow users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="c255e-119">[Microsoft エンドポイントマネージャー](https://endpoint.microsoft.com/#home)を使用すると、サービスを選択し、[Get a プレミアム試用版] を選択するまでいくつかのページに移動できます。</span><span class="sxs-lookup"><span data-stu-id="c255e-119">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="c255e-120">自動登録 P1 の場合は Azure Active Directory Premium 1 と2があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c255e-120">You may notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="c255e-121">Intune を選択し、自動登録のユーザースコープを選択して、以前に作成したグループを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c255e-121">We can select Intune and select the user scope for automatic enrollment, and select the group that was previously created.</span></span>

<span data-ttu-id="c255e-122">詳細と手順については、 [Intune の自動登録を有効にする方法](/mem/intune/enrollment/quickstart-setup-auto-enrollment)に関するガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c255e-122">For full details and steps read the guide on [how to enable auto enrollment for Intune](/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <a name="application-licenses"></a><span data-ttu-id="c255e-123">アプリケーションライセンス</span><span class="sxs-lookup"><span data-stu-id="c255e-123">Application Licenses</span></span>

<span data-ttu-id="c255e-124">アプリケーションライセンスを使用すると、ユーザーは、会社が購入したアプリをインストールすることも、無料試用版からアプリの完全なバージョンにアップグレードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c255e-124">An application license allows a user to either install company purchased Apps or upgrade from a free trial to the full version of an app.</span></span> <span data-ttu-id="c255e-125">アプリケーションライセンスは、ユーザー、ユーザーグループ、またはデバイスグループのいずれかに適用できます。</span><span class="sxs-lookup"><span data-stu-id="c255e-125">Application licenses can be applied to either users, user groups, or device groups.</span></span> <span data-ttu-id="c255e-126">組織内のユーザーがリモートアシスタンスを使用するには、リモートアシスタンスのライセンスが必要&#39;ます。</span><span class="sxs-lookup"><span data-stu-id="c255e-126">You&#39;ll need Remote Assist licenses for users in your organization to use Remote Assist.</span></span> <span data-ttu-id="c255e-127">このガイドでは、 [Azure ユーザーとグループ](hololens2-cloud-connected-configure.md#azure-users-and-groups)の上で作成したユーザーグループに Remote Assist ライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c255e-127">For the purpose of this guide we'll assign Remote Assist licenses to the user group we created above in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span></span>

<span data-ttu-id="c255e-128">ライセンスの要件は、ユーザーがデバイスからリモートアシスタンス通話を行うか、Microsoft Teams からリモートコラボレーターになるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c255e-128">The requirements for licenses can be different depending on if the user will be making the Remote Assist call from a device or will be a remote collaborator from Microsoft Teams.</span></span> <span data-ttu-id="c255e-129">既定では、[リモートアシスタンス] チェックボックスと [Teams] チェックボックスは両方ともマークされています。</span><span class="sxs-lookup"><span data-stu-id="c255e-129">By default the Remote Assist and Teams check boxes are both marked.</span></span> <span data-ttu-id="c255e-130">このガイドでは、既定のボックスをオンのままにしておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c255e-130">For the purposes of this guide, we suggest leaving the default boxes checked.</span></span>

1. <span data-ttu-id="c255e-131">ロールごとのさまざまな [ライセンスと製品の要件](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)について説明します。</span><span class="sxs-lookup"><span data-stu-id="c255e-131">Learn more about the different [Licensing and product requirements per role](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span></span> <span data-ttu-id="c255e-132">リモートアシスタンスのライセンスにはいくつかの種類があります。そのため、ニーズに合わせて正しいものを入手してください。</span><span class="sxs-lookup"><span data-stu-id="c255e-132">There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.</span></span>
2. <span data-ttu-id="c255e-133">[ライセンスを取得](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)する必要が&#39;ます。</span><span class="sxs-lookup"><span data-stu-id="c255e-133">You&#39;ll need to [acquire the license](/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span></span>
3. <span data-ttu-id="c255e-134">グループに[ライセンスを適用](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist)します。</span><span class="sxs-lookup"><span data-stu-id="c255e-134">[Apply your licenses](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) to the group.</span></span>

## <a name="next-step"></a><span data-ttu-id="c255e-135">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c255e-135">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c255e-136">クラウドに接続されたデプロイ-デプロイ</span><span class="sxs-lookup"><span data-stu-id="c255e-136">Cloud connected deployment - Deploy</span></span>](hololens2-cloud-connected-deploy.md)