---
title: 展開ガイド–リモートアシスタンスによる構成による、クラウド接続の HoloLens 2 展開
description: クラウドに接続されたネットワーク経由で HoloLens デバイスを登録するための構成を設定する方法
keywords: HoloLens、管理、クラウド接続、リモートアシスト、AAD、Azure AD、MDM、モバイルデバイス管理
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
ms.openlocfilehash: 43b9db96a2c29d1e3a798d0c695ab6edaa8199ac
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196337"
---
# <span data-ttu-id="93776-104">構成-クラウド接続ガイド</span><span class="sxs-lookup"><span data-stu-id="93776-104">Configure - Cloud connected Guide</span></span>

<span data-ttu-id="93776-105">このセクションでは、テナントの自動登録のセットアップ方法、および Intune とリモートアシストの両方のライセンスの適用方法について説明し&#39;します。</span><span class="sxs-lookup"><span data-stu-id="93776-105">In this section of the guide we&#39;ll go over how to set up Auto Enrollment for your tenant, and how to apply licenses for both Intune and Remote Assist.</span></span>

## <span data-ttu-id="93776-106">Azure ユーザーとグループ</span><span class="sxs-lookup"><span data-stu-id="93776-106">Azure Users and Groups</span></span>

<span data-ttu-id="93776-107">Azure、およびその拡張機能により、ユーザーとグループを使用して、構成とライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="93776-107">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="93776-108">このような展開フローを検証して、あるユーザーから別のユーザーにリモートアシスタンス通話を発信できるようにするためには、2つのユーザーアカウントが必要です。&#39;ます。</span><span class="sxs-lookup"><span data-stu-id="93776-108">For the sake of validating this deployment flow and being able to make a Remote Assist call from one user to another you&#39;ll need 2 user accounts.</span></span>

<span data-ttu-id="93776-109">ライセンスの割り当てを目的とした1つのユーザーグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="93776-109">We can make a single user group for the purpose of assigning licenses.</span></span> <span data-ttu-id="93776-110">両方のユーザーを同じグループに参加させることができ、そのグループに Intune およびリモートアシスタンスのライセンスを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="93776-110">We can join both users to the same group and apply a license for Intune and Remote Assist to that group.</span></span>

<span data-ttu-id="93776-111">ユーザーグループ内の2つの AAD アカウントにまだアクセスできない場合は、次のような方法で&#39;ます。次のクイックスタートガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="93776-111">If you don&#39;t already have access to two AAD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="93776-112">ユーザーを作成する方法</span><span class="sxs-lookup"><span data-stu-id="93776-112">How to create a user</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="93776-113">グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="93776-113">How to create a group</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="93776-114">[グループにユーザーを追加](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) する–作成したユーザーを追加してグループを作成する</span><span class="sxs-lookup"><span data-stu-id="93776-114">[Add users to a group](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="93776-115">[ユーザーグループがデバイスに参加することを許可するように AAD を構成](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) する–新しいユーザーグループに、デバイスを AAD に登録する権限があることを確認する</span><span class="sxs-lookup"><span data-stu-id="93776-115">[Configure AAD to allow a User Group to join devices](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to AAD</span></span>

## <span data-ttu-id="93776-116">HoloLens 2 での自動登録</span><span class="sxs-lookup"><span data-stu-id="93776-116">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="93776-117">円滑かつシームレスなエクスペリエンスを実現するために、Azure Active Directory の参加 (AADJ) と、Intune の自動登録機能を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="93776-117">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="93776-118">これにより、ユーザーは OOBE 中に組織のログイン資格情報を入力し、AAD に自動的に登録し、デバイスを MDM に登録することができます。</span><span class="sxs-lookup"><span data-stu-id="93776-118">This will allow users to simply input their organization log-in credentials during OOBE and automatically register with AAD and enroll the device into MDM.</span></span>

<span data-ttu-id="93776-119">[Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)を使用することで、[サービス] を選択し、[Premium 試用版の取得] が選択されるまで、いくつかのページに移動できます。</span><span class="sxs-lookup"><span data-stu-id="93776-119">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home) we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="93776-120">自動登録 P1 には、Azure Active Directory Premium 1 と2が用意されています。</span><span class="sxs-lookup"><span data-stu-id="93776-120">You many notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="93776-121">[Intune] を選択し、自動登録のユーザー範囲を選択して、以前に作成されたグループを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="93776-121">We can select Intune and select the user scope for automatic enrollment, and select the group that was previously created.</span></span>

<span data-ttu-id="93776-122">詳細と手順については、「 [Intune の自動登録を有効](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)にする」のガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="93776-122">For full details and steps please read the guide on [how to enable auto enrollment for Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <span data-ttu-id="93776-123">アプリケーションライセンス</span><span class="sxs-lookup"><span data-stu-id="93776-123">Application Licenses</span></span>

<span data-ttu-id="93776-124">アプリケーションライセンスにより、ユーザーは会社で購入したアプリをインストールしたり、無料トライアルをアプリの完全バージョンにアップグレードしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="93776-124">An application license allows a user to either install company purchased Apps or upgrade from a free trial to the full version of an app.</span></span> <span data-ttu-id="93776-125">アプリケーションライセンスは、ユーザー、ユーザーグループ、またはデバイスグループのいずれかに適用できます。</span><span class="sxs-lookup"><span data-stu-id="93776-125">Application licenses can be applied to either users, user groups, or device groups.</span></span> <span data-ttu-id="93776-126">リモートアシストを使用するには、組織内のユーザーに対してリモートアシスタンスライセンスが必要です&#39;ます。</span><span class="sxs-lookup"><span data-stu-id="93776-126">You&#39;ll need Remote Assist licenses for users in your organization to use Remote Assist.</span></span> <span data-ttu-id="93776-127">このガイドでは、前述のように、 [Azure ユーザーとグループ](hololens2-cloud-connected-configure.md#azure-users-and-groups)で作成したユーザーグループにリモートアシスタンスライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="93776-127">For the purpose of this guide we'll assign Remote Assist licenses to the user group we created above in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span></span>

<span data-ttu-id="93776-128">ライセンスの要件は、ユーザーがデバイスからリモートアシスタンス通話を行う場合や、Microsoft Teams のリモートコラボレーターであるかによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="93776-128">The requirements for licenses can be different depending on if the user will be making the Remote Assist call from a device or will be a remote collaborator from Microsoft Teams.</span></span> <span data-ttu-id="93776-129">既定では、[リモートアシスタンス] と [チーム] チェックボックスは両方としてマークされています。</span><span class="sxs-lookup"><span data-stu-id="93776-129">By default the Remote Assist and Teams check boxes are both marked.</span></span> <span data-ttu-id="93776-130">このガイドでは、既定のボックスをオンのままにしておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="93776-130">For the purposes of this guide, we suggest to leave the default boxes checked.</span></span>

1. <span data-ttu-id="93776-131">さまざまな [ライセンスと製品の要件](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)の詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="93776-131">Learn more about the different [Licensing and product requirements per role](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span></span> <span data-ttu-id="93776-132">リモートアシスタンスライセンスには、いくつかの種類があります。必要に応じて、正しいものを入手してください。</span><span class="sxs-lookup"><span data-stu-id="93776-132">There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.</span></span>
2. <span data-ttu-id="93776-133">&#39;[、ライセンスを取得](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93776-133">You&#39;ll need to [acquire the license](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span></span>
3. <span data-ttu-id="93776-134">[ライセンス](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) をグループに適用します。</span><span class="sxs-lookup"><span data-stu-id="93776-134">[Apply your licenses](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) to the group.</span></span>

## <span data-ttu-id="93776-135">次のステップ</span><span class="sxs-lookup"><span data-stu-id="93776-135">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="93776-136">クラウド接続展開-展開</span><span class="sxs-lookup"><span data-stu-id="93776-136">Cloud connected deployment - Deploy</span></span>](hololens2-cloud-connected-deploy.md)