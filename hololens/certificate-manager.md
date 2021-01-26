---
title: 証明書マネージャー
description: HoloLens 2 Mixed Reality デバイスに証明書を手動でインストール、管理、削除する方法について学習します。
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 9d221321adcb8062206695e3e610d35dee14523e
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283688"
---
# <span data-ttu-id="db468-103">証明書マネージャー</span><span class="sxs-lookup"><span data-stu-id="db468-103">Certificate Manager</span></span>

- <span data-ttu-id="db468-104">新しい証明書マネージャーを通じて、デバイスのセキュリティとコンプライアンスのための監査、診断、検証ツールが改善されました。</span><span class="sxs-lookup"><span data-stu-id="db468-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="db468-105">この機能を使用すると、商用環境で大規模に証明書を展開、トラブルシューティング、検証できます。</span><span class="sxs-lookup"><span data-stu-id="db468-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="db468-106">Windows Holographic バージョン 20H2 では、HoloLens 2 の設定アプリに証明書マネージャーを追加します。</span><span class="sxs-lookup"><span data-stu-id="db468-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="db468-107">[セキュリティと **証明書>更新&設定>移動します**。</span><span class="sxs-lookup"><span data-stu-id="db468-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="db468-108">この機能を使用すると、デバイス上の証明書を表示、インストール、および削除するための簡単で使い方が容易です。</span><span class="sxs-lookup"><span data-stu-id="db468-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="db468-109">新しい証明書マネージャーにより、管理者とユーザーは監査、診断、検証ツールが改善され、デバイスのセキュリティと準拠が維持されます。</span><span class="sxs-lookup"><span data-stu-id="db468-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="db468-110">**監査:** 証明書が正しく展開されていることを検証する機能、または証明書が適切に削除されていることを確認する機能。</span><span class="sxs-lookup"><span data-stu-id="db468-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="db468-111">**診断:** 問題が発生した場合、デバイスに適切な証明書が存在する場合は、時間を節約し、トラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="db468-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="db468-112">**検証:** 証明書が目的の目的を持ち、機能することを確認すると、特に商用環境で証明書を大規模に展開する前に、大幅な時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="db468-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="db468-113">一覧内の特定の証明書をすばやく検索するには、名前、ストア、または有効期限で並べ替えるオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="db468-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="db468-114">ユーザーは証明書を直接検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="db468-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="db468-115">個々の証明書のプロパティを表示するには、証明書を選択し、[情報] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="db468-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="db468-116">証明書のインストールでは、.cer ファイルと .crt ファイルが現在サポートされています。</span><span class="sxs-lookup"><span data-stu-id="db468-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="db468-117">デバイス所有者は、ローカル コンピューターと現在のユーザーに証明書をインストールできます。 他のすべてのユーザーは現在のユーザーにのみインストールできます。</span><span class="sxs-lookup"><span data-stu-id="db468-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="db468-118">ユーザーは、設定 UI から直接インストールされた証明書のみを削除できます。</span><span class="sxs-lookup"><span data-stu-id="db468-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="db468-119">証明書が他の方法でインストールされている場合は、同じメカニズムでも削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db468-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <span data-ttu-id="db468-120">証明書をインストールするには:</span><span class="sxs-lookup"><span data-stu-id="db468-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="db468-121">HoloLens 2 を PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="db468-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="db468-122">HoloLens 2 上の場所にインストールする証明書ファイルを配置します。</span><span class="sxs-lookup"><span data-stu-id="db468-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="db468-123">[設定アプリ **とセキュリティ>更新&証明書>に移動**し、[証明書のインストール] を選択します。</span><span class="sxs-lookup"><span data-stu-id="db468-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="db468-124">[ **ファイルのインポート]** をクリックし、証明書を保存した場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="db468-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="db468-125">[ストア **の場所] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="db468-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="db468-126">証明書ストア **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="db468-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="db468-127">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db468-127">Click **Install**.</span></span>

<span data-ttu-id="db468-128">これで、証明書がデバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="db468-128">The certificate should now be installed on the device.</span></span>

## <span data-ttu-id="db468-129">証明書を削除するには:</span><span class="sxs-lookup"><span data-stu-id="db468-129">To remove a certificate:</span></span> 
1. <span data-ttu-id="db468-130">[設定] **アプリの [更新>セキュリティと証明書] >移動します**。</span><span class="sxs-lookup"><span data-stu-id="db468-130">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="db468-131">検索ボックスで名前で証明書を検索します。</span><span class="sxs-lookup"><span data-stu-id="db468-131">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="db468-132">証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="db468-132">Select the certificate.</span></span>
1. <span data-ttu-id="db468-133">[削除 **] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="db468-133">Click **Remove**</span></span>
1. <span data-ttu-id="db468-134">確認 **を求める** メッセージが表示されたら、[はい] を選択します。</span><span class="sxs-lookup"><span data-stu-id="db468-134">Select **Yes** when prompted for confirmation.</span></span>


![Ceritifcates の下の設定アプリの証明書ビューアー](images/certificate-viewer-device.jpg)

![[設定] で証明書 UI を使用して証明書をインストールする方法を示す図。](images/certificate-device-install.jpg)
