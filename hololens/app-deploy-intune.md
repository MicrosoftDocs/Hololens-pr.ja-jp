---
title: Intune とポータル サイト
description: Intune、モバイル デバイス管理、およびポータル サイトで快適なユーザー エクスペリエンスをセットアップ、割り当て、作成する方法について説明します。
keywords: intune, アプリ管理, アプリ, ポータル, ポータル, hololens
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283718"
---
# <span data-ttu-id="070a0-104">Intune と会社のポータル</span><span class="sxs-lookup"><span data-stu-id="070a0-104">Intune & Company Portal</span></span>

<span data-ttu-id="070a0-105">モバイル デバイス管理 (MDM) を使用すると [、Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) を通じて独自のカスタム アプリを使用して、HoloLens デバイスに直接展開できます。</span><span class="sxs-lookup"><span data-stu-id="070a0-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="070a0-106">Microsoft Intune は、モバイル デバイス管理 (MDM) とモバイル アプリケーション管理 (MAM) に重点を置いたクラウドベースのサービスです。</span><span class="sxs-lookup"><span data-stu-id="070a0-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="070a0-107">Intune は Microsoft の [Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)スイートに含まれており、組織のデータを保護しながら生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="070a0-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="070a0-108">Intune の詳細については、「Intune とは [」を参照してください](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)。</span><span class="sxs-lookup"><span data-stu-id="070a0-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <span data-ttu-id="070a0-109">セットアップ</span><span class="sxs-lookup"><span data-stu-id="070a0-109">Setup</span></span>

1. <span data-ttu-id="070a0-110">アプリを Line of Business にアップロードするか、カスタム アプリを Intune テナントにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="070a0-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="070a0-111">「エンタープライズ アプリ [管理」も参照してください](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)。</span><span class="sxs-lookup"><span data-stu-id="070a0-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="070a0-112">[アプリをグループに割り当てる](https://docs.microsoft.com/mem/intune/apps/apps-deploy)。</span><span class="sxs-lookup"><span data-stu-id="070a0-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="070a0-113">選択した割り当ての種類に基づいて、アプリを自動的に配信したり、選択したアプリがある場合は簡単に取得できます。</span><span class="sxs-lookup"><span data-stu-id="070a0-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="070a0-114">appx バンドルを構築する場合は、展開するデバイスのアーキテクチャを含めて考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="070a0-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="070a0-115">HoloLens 2 は ARM64、HoloLens (第 1 世代) は x86 です。</span><span class="sxs-lookup"><span data-stu-id="070a0-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="070a0-116">混在するデバイス環境を計画している場合は、両方を単一の appx バンドルに含めできます。</span><span class="sxs-lookup"><span data-stu-id="070a0-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <span data-ttu-id="070a0-117">割り当ての種類</span><span class="sxs-lookup"><span data-stu-id="070a0-117">Assignment types</span></span>

<span data-ttu-id="070a0-118">登録後にアプリをデバイスに自動的にインストールするには、そのグループに対して **[必須** ] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="070a0-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="070a0-119">ポータル サイトから登録されたデバイスにアプリをダウンロードするには、[登録済みデバイスで利用可能] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="070a0-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <span data-ttu-id="070a0-120">End-User エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="070a0-120">End-User Experience</span></span>

<span data-ttu-id="070a0-121">Intune で構成を設定すると、エンド ユーザーが選択したアプリを受け取る準備が整います。</span><span class="sxs-lookup"><span data-stu-id="070a0-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="070a0-122">アプリを自動的に取得するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="070a0-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="070a0-123">テナントにデバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="070a0-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="070a0-124">デバイスの登録が完了したら、デバイスでアプリを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="070a0-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="070a0-125">If you are not see you app immediately, go to **Settings**  >  **Accounts**  >  **Work or School**your  >  *account* Info, and scroll down to see information on installed app status.</span><span class="sxs-lookup"><span data-stu-id="070a0-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="070a0-126">ポータル サイトからアプリにアクセスする方法:</span><span class="sxs-lookup"><span data-stu-id="070a0-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="070a0-127">スタート メニュー **を開き、Microsoft** **Store を選択します**。</span><span class="sxs-lookup"><span data-stu-id="070a0-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="070a0-128">ポータル サイト **を検索し** 、アプリをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="070a0-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="070a0-129">アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="070a0-129">Sign into your account.</span></span>
4. <span data-ttu-id="070a0-130">受信するアプリを選択し、ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="070a0-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="070a0-131">ポータル サイトの [自動インストールと](https://docs.microsoft.com/mem/intune/apps/company-portal-app) Intune でのアプリの展開と管理について [詳しく知る](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)。</span><span class="sxs-lookup"><span data-stu-id="070a0-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
