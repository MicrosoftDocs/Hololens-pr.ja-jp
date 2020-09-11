---
title: Intune と会社のポータル
description: intune、アプリ管理、アプリ、会社ポータル、ポータル
keywords: intune、アプリ管理、アプリ、会社ポータル、ポータル、hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
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
ms.openlocfilehash: 5fc369caa2e5e26c91c07f9270c3984177507dbd
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009465"
---
# <span data-ttu-id="a6101-104">Intune と会社のポータル</span><span class="sxs-lookup"><span data-stu-id="a6101-104">Intune & Company Portal</span></span>

<span data-ttu-id="a6101-105">モバイルデバイス管理 (MDM) を使用すると、 [Microsoft エンドポイントマネージャー (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) を介して独自のカスタムアプリを使って、直接 HoloLens デバイスに展開できます。</span><span class="sxs-lookup"><span data-stu-id="a6101-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="a6101-106">Microsoft Intune は、モバイルデバイス管理 (MDM) およびモバイルアプリケーション管理 (MAM) に重点を置いたクラウドベースのサービスです。</span><span class="sxs-lookup"><span data-stu-id="a6101-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="a6101-107">Intune は Microsoft[Enterprise Mobility + Security (EMS) スイート](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)に含まれており、組織のデータを保護したまま、ユーザーが生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="a6101-107">Intune is included in Microsoft's[Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="a6101-108">Intune の詳細については、「 [intune とは](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6101-108">To learn more about Intune, please read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <span data-ttu-id="a6101-109">セットアップ</span><span class="sxs-lookup"><span data-stu-id="a6101-109">Setup</span></span>

1. <span data-ttu-id="a6101-110">アプリを基幹業務にアップロードするか、カスタムアプリを Intune テナントにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="a6101-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="a6101-111">「 [エンタープライズアプリの管理](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a6101-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="a6101-112">[アプリをグループに割り当て](https://docs.microsoft.com/mem/intune/apps/apps-deploy)ます。</span><span class="sxs-lookup"><span data-stu-id="a6101-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="a6101-113">選択した課題の種類に基づいて、アプリが自動的に配信されるようにするか、アプリが選択されている場合は、すぐに表示されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a6101-113">Based on the assignment type you choose you can have the app delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span> 

> [!NOTE] 
> <span data-ttu-id="a6101-114">Appx バンドルを構築するときは、展開先のデバイスのアーキテクチャを含める必要があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a6101-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="a6101-115">HoloLens 2 は ARM64、HoloLens (第1世代) は x86 です。</span><span class="sxs-lookup"><span data-stu-id="a6101-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="a6101-116">混合デバイス環境を計画している場合は、両方を1つの appx バンドルに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a6101-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <span data-ttu-id="a6101-117">課題の種類</span><span class="sxs-lookup"><span data-stu-id="a6101-117">Assignment types</span></span>

<span data-ttu-id="a6101-118">アプリを登録後、デバイスに自動的にインストールされるようにする場合は、そのグループに対して [ **必須** ] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6101-118">If you prefer your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="a6101-119">会社のポータルを通じて登録されたアプリにアプリをダウンロードできるようにするには、[登録されている **デバイスで利用可能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6101-119">If you prefer to make your app available for download to those enrolled through the company portal, select **Available for enrolled devices**.</span></span>


## <span data-ttu-id="a6101-120">エンドユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="a6101-120">End User Experience</span></span>

<span data-ttu-id="a6101-121">Intune で構成を設定した後、エンドユーザーは選んだアプリを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="a6101-121">After you have set up configuration on Intune you are ready for end users to recieve your selected apps.</span></span>

<span data-ttu-id="a6101-122">自動的にアプリを取得するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a6101-122">Follow these steps to automatically get your app(s):</span></span>
1. <span data-ttu-id="a6101-123">テナントにデバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="a6101-123">Enroll your device with your tenant.</span></span> 
2. <span data-ttu-id="a6101-124">デバイスの登録が完了したら、デバイスでアプリを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6101-124">Once your device has completed enrollment, you should receive the app on your device.</span></span> 
3. <span data-ttu-id="a6101-125">アプリがすぐに表示されない場合は、[アカウント情報] の [アカウントの**設定**] に移動  >  **Accounts**  >  **Work or School**  >  **youraccount**し、下にスクロールして、インストールされているアプリの状態に関する情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="a6101-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > **youraccount** Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="a6101-126">会社のポータルからアプリにアクセスする方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="a6101-126">How to get to apps through the Company Portal:</span></span>
1. <span data-ttu-id="a6101-127">[ **スタート] メニュー** を開き、[ **Microsoft Store**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6101-127">Open the **Start Menu** and select **Microsoft Store**.</span></span> 
2. <span data-ttu-id="a6101-128">会社の **ポータル** を検索して、アプリをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a6101-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="a6101-129">アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="a6101-129">Sign into your account.</span></span>
4. <span data-ttu-id="a6101-130">受け取りたいアプリを選択してダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a6101-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="a6101-131">[会社のポータルの自動インストール](https://docs.microsoft.com/mem/intune/apps/company-portal-app)と、 [Intune でのアプリの展開と管理](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)の詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6101-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
