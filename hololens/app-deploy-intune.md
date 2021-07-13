---
title: Intune と ポータル サイト
description: Intune、モバイル デバイス管理、およびポータル サイトを使用して、快適なユーザー エクスペリエンスを設定、割り当て、作成する方法について説明します。
keywords: Intune, アプリ管理, アプリ, ポータル サイト, ポータル, Hololens
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
ms.openlocfilehash: b192732f5e7edffaa1d0ab081454e4034c416191
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635502"
---
# <a name="intune--company-portal"></a><span data-ttu-id="f2b47-104">Intune & ポータル サイト</span><span class="sxs-lookup"><span data-stu-id="f2b47-104">Intune & Company Portal</span></span>

<span data-ttu-id="f2b47-105">Mobile デバイス管理 (MDM) を使用すると[、Microsoft エンドポイント マネージャー (Intune)](/intune/windows-holographic-for-business)を使用して独自のカスタム アプリを使用して、HoloLens デバイスに直接展開できます。</span><span class="sxs-lookup"><span data-stu-id="f2b47-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="f2b47-106">Microsoft Intune は、モバイル デバイス管理 (MDM) とモバイル アプリケーション管理 (MAM) を中心にしたクラウドベースのサービスです。</span><span class="sxs-lookup"><span data-stu-id="f2b47-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="f2b47-107">Intune は、Microsoft の [Enterprise Mobility + Security (EMS) スイート](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)に含まれており、組織のデータを保護したまま、ユーザーの生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="f2b47-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="f2b47-108">Intune の詳細については、「Intune とは [」を参照してください](/mem/intune/fundamentals/what-is-intune)。</span><span class="sxs-lookup"><span data-stu-id="f2b47-108">To learn more about Intune, read [What is Intune](/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="f2b47-109">セットアップ</span><span class="sxs-lookup"><span data-stu-id="f2b47-109">Setup</span></span>

1. <span data-ttu-id="f2b47-110">アップロードを Line of Business にアップロードするか、カスタム アプリを Intune テナントにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="f2b47-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="f2b47-111">「アプリ管理[のEnterprise」も参照してください](/windows/client-management/mdm/enterprise-app-management)。</span><span class="sxs-lookup"><span data-stu-id="f2b47-111">See also: [Enterprise app management](/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="f2b47-112">[アプリをグループ に割り当てる](/mem/intune/apps/apps-deploy)。</span><span class="sxs-lookup"><span data-stu-id="f2b47-112">[Assign your app to a group](/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="f2b47-113">選択した割り当ての種類に基づいて、アプリを自動的に配信したり、選択したアプリがある場合は簡単に引き下げられたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="f2b47-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="f2b47-114">appx バンドルを構築する場合は、デプロイするデバイスのアーキテクチャを含め、必ず考慮してください。</span><span class="sxs-lookup"><span data-stu-id="f2b47-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="f2b47-115">HoloLens 2 ARM64 で、HoloLens (第 1 世代) は x86 です。</span><span class="sxs-lookup"><span data-stu-id="f2b47-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="f2b47-116">混在するデバイス環境を計画している場合は、両方を単一の appx バンドルに含める場合があります。</span><span class="sxs-lookup"><span data-stu-id="f2b47-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="f2b47-117">割り当ての種類</span><span class="sxs-lookup"><span data-stu-id="f2b47-117">Assignment types</span></span>

<span data-ttu-id="f2b47-118">登録後にアプリをデバイスに自動的にインストールするには、そのグループに対して[必須] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2b47-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="f2b47-119">ポータル サイトを使用して登録されたデバイスにアプリをダウンロードするには、[登録済みデバイスで使用可能] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f2b47-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="f2b47-120">エンドユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="f2b47-120">End-User Experience</span></span>

<span data-ttu-id="f2b47-121">Intune で構成を設定すると、エンド ユーザーが選択したアプリを受け取る準備が整います。</span><span class="sxs-lookup"><span data-stu-id="f2b47-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="f2b47-122">アプリを自動的に取得するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f2b47-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="f2b47-123">デバイスをテナントに登録します。</span><span class="sxs-lookup"><span data-stu-id="f2b47-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="f2b47-124">デバイスの登録が完了すると、デバイスでアプリを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2b47-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="f2b47-125">アプリがすぐに表示されない場合は、[設定アカウントの作業または学校のアカウント情報] に移動し、下にスクロールしてインストールされているアプリの状態に関する  >    >    >  情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f2b47-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="f2b47-126">次の方法でアプリにアクセスポータル サイト。</span><span class="sxs-lookup"><span data-stu-id="f2b47-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="f2b47-127">[スタート]**メニューを開き**、[ ]**をMicrosoft Store。**</span><span class="sxs-lookup"><span data-stu-id="f2b47-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="f2b47-128">アプリを **検索ポータル サイト** アプリをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f2b47-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="f2b47-129">アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="f2b47-129">Sign into your account.</span></span>
4. <span data-ttu-id="f2b47-130">受信するアプリを選択してダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f2b47-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="f2b47-131">Intune での[アプリの自動インストール](/mem/intune/apps/company-portal-app)とポータル サイトおよび管理の詳細については、[以下を参照してください](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)。</span><span class="sxs-lookup"><span data-stu-id="f2b47-131">Learn more about [auto-installing the Company Portal](/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
