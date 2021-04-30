---
title: Intune とポータルサイト
description: Intune、モバイルデバイス管理、およびポータルサイトで、快適なユーザーエクスペリエンスをセットアップ、割り当て、作成する方法について説明します。
keywords: intune、アプリ管理、アプリ、ポータルサイト、ポータル、hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309731"
---
# <a name="intune--company-portal"></a><span data-ttu-id="1ca07-104">Intune & ポータルサイト</span><span class="sxs-lookup"><span data-stu-id="1ca07-104">Intune & Company Portal</span></span>

<span data-ttu-id="1ca07-105">モバイルデバイス管理 (MDM) を使用すると、 [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) を通じて独自のカスタムアプリを使用して、直接 HoloLens デバイスに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="1ca07-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="1ca07-106">Microsoft Intune は、モバイル デバイス管理 (MDM) とモバイル アプリケーション管理 (MAM) を中心にしたクラウドベースのサービスです。</span><span class="sxs-lookup"><span data-stu-id="1ca07-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="1ca07-107">Intune は、Microsoft の [Enterprise Mobility + Security (EMS) スイート](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)に含まれており、組織のデータを保護したまま、ユーザーの生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="1ca07-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="1ca07-108">Intune の詳細については、「 [intune とは](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ca07-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="1ca07-109">セットアップ</span><span class="sxs-lookup"><span data-stu-id="1ca07-109">Setup</span></span>

1. <span data-ttu-id="1ca07-110">アプリを基幹業務にアップロードするか、Intune テナントにカスタムアプリをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="1ca07-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="1ca07-111">「 [エンタープライズアプリ管理](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ca07-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="1ca07-112">[アプリをグループに割り当て](https://docs.microsoft.com/mem/intune/apps/apps-deploy)ます。</span><span class="sxs-lookup"><span data-stu-id="1ca07-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="1ca07-113">選択した割り当ての種類に基づいて、アプリを自動的に配信することも、アプリを選択している場合はすぐに利用できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1ca07-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="1ca07-114">Appx バンドルを構築するときは、デプロイ先のデバイスのアーキテクチャを含めるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="1ca07-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="1ca07-115">HoloLens 2 は ARM64、HoloLens (第1世代) は x86 です。</span><span class="sxs-lookup"><span data-stu-id="1ca07-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="1ca07-116">混合デバイス環境を使用する場合は、両方を1つの appx バンドルに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1ca07-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="1ca07-117">割り当ての種類</span><span class="sxs-lookup"><span data-stu-id="1ca07-117">Assignment types</span></span>

<span data-ttu-id="1ca07-118">登録後にアプリがデバイスに自動的にインストールされるようにするには、そのグループに対して [ **必須** ] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ca07-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="1ca07-119">ポータルサイトで登録されているデバイスにアプリをダウンロードできるようにするには、[ **登録済みデバイスで利用可能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ca07-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="1ca07-120">エンドユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="1ca07-120">End-User Experience</span></span>

<span data-ttu-id="1ca07-121">Intune で構成を設定した後、エンドユーザーが選択したアプリを受信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1ca07-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="1ca07-122">アプリを自動的に取得するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1ca07-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="1ca07-123">テナントにデバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="1ca07-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="1ca07-124">デバイスの登録が完了したら、デバイスでアプリを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ca07-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="1ca07-125">アプリがすぐに表示されない場合は、[**設定**] [  >  **アカウント**  >  ] [職場]**または [学校** の  >  *アカウント* 情報] に移動し、下にスクロールして、インストールされているアプリの状態に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="1ca07-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="1ca07-126">ポータルサイトを通じてアプリにアクセスする方法:</span><span class="sxs-lookup"><span data-stu-id="1ca07-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="1ca07-127">[ **スタート] メニュー** を開き、[ **Microsoft Store**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ca07-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="1ca07-128">**ポータルサイト** を検索し、アプリをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="1ca07-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="1ca07-129">アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="1ca07-129">Sign into your account.</span></span>
4. <span data-ttu-id="1ca07-130">受信してダウンロードするアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="1ca07-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="1ca07-131">[ポータルサイトの自動インストール](https://docs.microsoft.com/mem/intune/apps/company-portal-app)と[Intune でのアプリの展開と管理の](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ca07-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
