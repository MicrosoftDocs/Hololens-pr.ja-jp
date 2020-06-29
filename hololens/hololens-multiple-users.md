---
title: 複数のユーザーと HoloLens を共有する
description: 複数の Azure Active Directory アカウントで、または1つのアカウントを使用する複数のユーザーが共有するように HoloLens を構成することができます。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829288"
---
# <span data-ttu-id="17ea5-103">複数のユーザーと HoloLens を共有する</span><span class="sxs-lookup"><span data-stu-id="17ea5-103">Share your HoloLens with multiple people</span></span>

<span data-ttu-id="17ea5-104">1つの HoloLens を多くのユーザーと共有したり、多数のユーザーが一連の HoloLens デバイスを共有したりすることは一般的です。</span><span class="sxs-lookup"><span data-stu-id="17ea5-104">It's common to share one HoloLens with many people or to have many people share a set of HoloLens devices.</span></span>  <span data-ttu-id="17ea5-105">この記事では、デバイスを共有するさまざまな方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="17ea5-105">This article describes the different ways in which you can share a device.</span></span>

## <span data-ttu-id="17ea5-106">自分のアカウントを使用して複数のユーザーと共有する</span><span class="sxs-lookup"><span data-stu-id="17ea5-106">Share with multiple people, each using their own account</span></span>

<span data-ttu-id="17ea5-107">**前提条件**: HoloLens デバイスでは、Windows 10 バージョン1803以降を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="17ea5-107">**Prerequisite**: The HoloLens device must be running Windows 10, version 1803 or later.</span></span>  <span data-ttu-id="17ea5-108">HoloLens (第1世代) も、 [Windows ホログラフィック For Business にアップグレード](hololens-upgrade-enterprise.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17ea5-108">HoloLens (1st gen) also need to be [upgraded to Windows Holographic for Business](hololens-upgrade-enterprise.md).</span></span>

<span data-ttu-id="17ea5-109">独自の Azure Active Directory (Azure AD) アカウントを使用している場合、複数のユーザーが自分のユーザー設定とユーザーデータをデバイス上に保持することができます。</span><span class="sxs-lookup"><span data-stu-id="17ea5-109">When they use their own Azure Active Directory (Azure AD) accounts, multiple users can each keep their own user settings and user data on the device.</span></span>

<span data-ttu-id="17ea5-110">複数のユーザーが HoloLens で自分のアカウントを使用できるようにするには、次の手順に従って設定します。</span><span class="sxs-lookup"><span data-stu-id="17ea5-110">To make sure that multiple people can use their own accounts on your HoloLens, follow these steps to configure it:</span></span>

1. <span data-ttu-id="17ea5-111">デバイスで Windows 10 バージョン1803以降が実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="17ea5-111">Make sure the the device is running Windows 10, version 1803 or later.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="17ea5-112">HoloLens (第1世代) デバイスを使っている場合は、[デバイスを Windows ホログラフィック For Business にアップグレード](hololens1-upgrade-enterprise.md)します。</span><span class="sxs-lookup"><span data-stu-id="17ea5-112">If you are using a HoloLens (1st gen) device, [upgrade the device to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>
1. <span data-ttu-id="17ea5-113">デバイスをセットアップするときに、[**自分の職場または学校**] を選択して、Azure AD アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="17ea5-113">When you set up the device, select **My work or school owns it** and sign in by using an Azure AD account.</span></span>
1. <span data-ttu-id="17ea5-114">セットアップが完了したら、アカウント設定 ([設定]**Settings**  >  **アカウント**) に**他のユーザー**が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="17ea5-114">After you finish setup, make sure that the account settings (**Settings** > **Accounts**) includes **Other users**.</span></span>

<span data-ttu-id="17ea5-115">HoloLens を使用するには、各ユーザーが次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="17ea5-115">To use HoloLens, each user follows these steps:</span></span>

1. <span data-ttu-id="17ea5-116">他のユーザーがデバイスを使っている場合は、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="17ea5-116">If another user has been using the device, do one of the following:</span></span>
   - <span data-ttu-id="17ea5-117">電源ボタンを1回押して [スタンバイ] に移動し、もう一度電源ボタンを押してロック画面に戻ります。</span><span class="sxs-lookup"><span data-stu-id="17ea5-117">Press the power button once to go to standby, and then press the power button again to return to the lock screen</span></span>
   - <span data-ttu-id="17ea5-118">HoloLens 2 ユーザーは、[スタート] メニューからユーザータイルを選択して、現在のユーザーからサインアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="17ea5-118">HoloLens 2 users may select the user tile from the Start menu to sign out the current user.</span></span>

1. <span data-ttu-id="17ea5-119">Azure AD アカウントの資格情報を使用して、デバイスにサインインします。</span><span class="sxs-lookup"><span data-stu-id="17ea5-119">Use your Azure AD account credentials to sign in to the device.</span></span>  
    <span data-ttu-id="17ea5-120">初めてデバイスを使った場合は、HoloLens を自分の目に合わせて[調整](hololens-calibration.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17ea5-120">If this is the first time that you have used the device, you have to [calibrate](hololens-calibration.md) HoloLens to your own eyes.</span></span>

<span data-ttu-id="17ea5-121">デバイスユーザーの一覧を表示したり、デバイスからユーザーを削除したりするには、[**設定**  >  **アカウント**  >  **の他のユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="17ea5-121">To see a list of the device users or to remove a user from the device, go to **Settings** > **Accounts** > **Other users**.</span></span>

## <span data-ttu-id="17ea5-122">同じアカウントを使用して複数のユーザーと共有する</span><span class="sxs-lookup"><span data-stu-id="17ea5-122">Share with multiple people, all using the same account</span></span>

<span data-ttu-id="17ea5-123">複数のユーザーが1つのユーザーアカウントを使用しているときに、HoloLens デバイスを共有することもできます。</span><span class="sxs-lookup"><span data-stu-id="17ea5-123">Multiple users can also share a HoloLens device while using a single user account.</span></span>

<span data-ttu-id="17ea5-124">**HoloLens 2 で**は、新しいユーザーが初めて (同じアカウントでサインインしたまま) デバイスをそのヘッド上に配置すると、デバイスは新しいユーザーに対して、表示エクスペリエンスの調整とカスタマイズをすばやく行うように求めます。</span><span class="sxs-lookup"><span data-stu-id="17ea5-124">**On HoloLens 2**, when a new user puts the device on their head for the first time (while keeping the same account signed in), the device prompts the new user to quickly calibrate and personalize the viewing experience.</span></span> <span data-ttu-id="17ea5-125">デバイスには調整情報が保存されているため、デバイスは、各ユーザーの表示エクスペリエンスの品質と快適さを自動的に最適化することができます。</span><span class="sxs-lookup"><span data-stu-id="17ea5-125">The device can store the calibration information so that in the future, the device can automatically optimize the quality and comfort of each user's viewing experience.</span></span> <span data-ttu-id="17ea5-126">ユーザーはデバイスを再調整する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="17ea5-126">The users do not need to calibrate the device again.</span></span>

<span data-ttu-id="17ea5-127">**HoloLens (第1世代) で**は、アカウントを共有しているユーザーは、設定アプリで再調整を要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17ea5-127">**On HoloLens (1st gen)** users sharing an account will need to ask to recalibrate in the Settings app.</span></span>  <span data-ttu-id="17ea5-128">詳細については、「[調整](hololens-calibration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17ea5-128">Read more about [calibration](hololens-calibration.md).</span></span>
