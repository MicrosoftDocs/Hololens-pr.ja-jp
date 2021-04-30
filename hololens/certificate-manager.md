---
title: 証明書マネージャー
description: HoloLens 2 mixed reality デバイスで証明書を手動でインストール、管理、および削除する方法について説明します。
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309244"
---
# <a name="certificate-manager"></a><span data-ttu-id="aee48-103">証明書マネージャー</span><span class="sxs-lookup"><span data-stu-id="aee48-103">Certificate Manager</span></span>

- <span data-ttu-id="aee48-104">新しい証明書マネージャーを使用した、デバイスのセキュリティとコンプライアンスのための監査、診断、検証のツールが改善されました。</span><span class="sxs-lookup"><span data-stu-id="aee48-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="aee48-105">この機能により、商用環境で大規模に証明書をデプロイ、トラブルシューティング、および検証することができます。</span><span class="sxs-lookup"><span data-stu-id="aee48-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="aee48-106">Windows Holographic バージョン20H2 では、HoloLens 2 設定アプリに証明書マネージャーを追加しています。</span><span class="sxs-lookup"><span data-stu-id="aee48-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="aee48-107">[設定] にアクセスして **& セキュリティ > 証明書を更新 >** ます。</span><span class="sxs-lookup"><span data-stu-id="aee48-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="aee48-108">この機能は、デバイス上の証明書を表示、インストール、削除するための簡単でわかりやすい方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="aee48-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="aee48-109">新しい証明書マネージャーを使用すると、管理者とユーザーは、デバイスが安全で準拠していることを確認するための監査、診断、検証のツールが改善されました。</span><span class="sxs-lookup"><span data-stu-id="aee48-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="aee48-110">**監査:** 証明書が正しく展開されていることを検証したり、適切に削除されたことを確認したりする機能。</span><span class="sxs-lookup"><span data-stu-id="aee48-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="aee48-111">**診断:** 問題が発生した場合、デバイスに適切な証明書が存在することを検証すると、時間が節約され、トラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="aee48-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="aee48-112">**検証:** 証明書が意図した目的を果たし、機能していることを確認することにより、証明書を大規模に展開する前に、特に商用環境においてかなりの時間を節約することができます。</span><span class="sxs-lookup"><span data-stu-id="aee48-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="aee48-113">リスト内の特定の証明書をすばやく検索するには、名前、ストア、または有効期限の日付で並べ替えるオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="aee48-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="aee48-114">ユーザーは、証明書を直接検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="aee48-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="aee48-115">個々の証明書のプロパティを表示するには、証明書を選択し、[ **情報**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aee48-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="aee48-116">証明書のインストールでは、.cer ファイルと .crt ファイルが現在サポートされています。</span><span class="sxs-lookup"><span data-stu-id="aee48-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="aee48-117">デバイスの所有者は、ローカルコンピューターと現在のユーザーに証明書をインストールできます。 他のすべてのユーザーは、現在のユーザーにのみインストールできます。</span><span class="sxs-lookup"><span data-stu-id="aee48-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="aee48-118">ユーザーは、設定 UI から直接インストールされた証明書のみを削除できます。</span><span class="sxs-lookup"><span data-stu-id="aee48-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="aee48-119">証明書が他の方法でインストールされている場合は、同じメカニズムでも削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aee48-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <a name="to-install-a-certificate"></a><span data-ttu-id="aee48-120">証明書をインストールするには:</span><span class="sxs-lookup"><span data-stu-id="aee48-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="aee48-121">HoloLens 2 を PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="aee48-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="aee48-122">インストールする証明書ファイルを HoloLens 2 の場所に配置します。</span><span class="sxs-lookup"><span data-stu-id="aee48-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="aee48-123">[設定] [アプリ] に移動して **& セキュリティ > 証明書を更新 >**、[証明書のインストール] を選択します。</span><span class="sxs-lookup"><span data-stu-id="aee48-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="aee48-124">[ **ファイルのインポート** ] をクリックし、証明書を保存した場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="aee48-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="aee48-125">[ **ストアの場所**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="aee48-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="aee48-126">[ **証明書ストア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="aee48-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="aee48-127">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aee48-127">Click **Install**.</span></span>

<span data-ttu-id="aee48-128">これで、証明書がデバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="aee48-128">The certificate should now be installed on the device.</span></span>

## <a name="to-remove-a-certificate"></a><span data-ttu-id="aee48-129">証明書を削除するには:</span><span class="sxs-lookup"><span data-stu-id="aee48-129">To remove a certificate:</span></span> 
1. <span data-ttu-id="aee48-130">**[設定] [アプリ]、[更新とセキュリティ > 証明書**] の順に移動し > ます。</span><span class="sxs-lookup"><span data-stu-id="aee48-130">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="aee48-131">検索ボックスで、名前を指定して証明書を検索します。</span><span class="sxs-lookup"><span data-stu-id="aee48-131">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="aee48-132">証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="aee48-132">Select the certificate.</span></span>
1. <span data-ttu-id="aee48-133">[**削除**] をクリック</span><span class="sxs-lookup"><span data-stu-id="aee48-133">Click **Remove**</span></span>
1. <span data-ttu-id="aee48-134">確認を求められたら、 **[はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aee48-134">Select **Yes** when prompted for confirmation.</span></span>


![設定アプリの証明書ビューアー (Ceritifcates](images/certificate-viewer-device.jpg)

![証明書 UI を使用して、[設定] に証明書をインストールする方法を示す画像。](images/certificate-device-install.jpg)
