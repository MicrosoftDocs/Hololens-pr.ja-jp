---
title: 証明書マネージャー
description: HoloLens 2 で証明書を手動で管理する方法について説明します。
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
ms.openlocfilehash: 04d7e8cb78357b5398c58e0a0c55e6e530fa363a
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163224"
---
# <span data-ttu-id="4ae4d-103">証明書マネージャー</span><span class="sxs-lookup"><span data-stu-id="4ae4d-103">Certificate Manager</span></span>

- <span data-ttu-id="4ae4d-104">新しい証明書マネージャーを通じて、デバイスのセキュリティとコンプライアンスのための監査、診断、検証ツールが改善されました。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="4ae4d-105">この機能を使用すると、商用環境で証明書の展開、トラブルシューティング、検証を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="4ae4d-106">Windows ホログラフィックのバージョン20H2 では、HoloLens 2 設定アプリで証明書マネージャーを追加しています。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="4ae4d-107">[設定] に移動して **& セキュリティ > 証明書を更新 >** ます。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="4ae4d-108">この機能を使うと、デバイスで証明書の表示、インストール、削除を簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="4ae4d-109">新しい証明書マネージャーを使用すると、管理者とユーザーは、より高度な監査、診断、検証ツールを使って、デバイスの安全性と準拠性を維持できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="4ae4d-110">**監査:** 証明書が正しく展開されていることを確認したり、適切に削除されたことを確認したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="4ae4d-111">**診断:** 問題が発生した場合は、デバイス上に適切な証明書が存在することで、時間が節約され、トラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="4ae4d-112">**検証:** 証明書が意図したものであり、機能していることを確認することにより、より大規模な証明書を展開する前に、特に商用環境では時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="4ae4d-113">リスト内の特定の証明書をすばやく検索するには、名前、ストア、有効期限のいずれかで並べ替えを行うオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="4ae4d-114">ユーザーは、証明書を直接検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="4ae4d-115">証明書のプロパティを個別に表示するには、証明書を選択し、[ **情報**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="4ae4d-116">証明書のインストールでは、現在、.cer および .crt ファイルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="4ae4d-117">デバイスの所有者は、ローカルコンピューターおよび現在のユーザーに証明書をインストールできます。 他のすべてのユーザーは、現在のユーザーにのみインストールできます。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="4ae4d-118">ユーザーは、[設定] UI から直接インストールされた証明書のみを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="4ae4d-119">証明書が他の方法でインストールされている場合は、同じメカニズムでも削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <span data-ttu-id="4ae4d-120">証明書をインストールするには:</span><span class="sxs-lookup"><span data-stu-id="4ae4d-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="4ae4d-121">HoloLens 2 を PC に接続します。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="4ae4d-122">インストールする証明書ファイルを、HoloLens 2 の場所に配置します。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="4ae4d-123">[設定] アプリに移動して **& セキュリティ > 証明書を更新 >**、[証明書のインストール] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="4ae4d-124">[ **ファイルのインポート** ] をクリックし、証明書を保存した場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="4ae4d-125">[ **保存場所**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="4ae4d-126">[ **証明書ストア**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="4ae4d-127">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-127">Click **Install**.</span></span>

<span data-ttu-id="4ae4d-128">これで、証明書がデバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-128">The certificate should now be installed on the device.</span></span>

## <span data-ttu-id="4ae4d-129">証明書を削除するには:</span><span class="sxs-lookup"><span data-stu-id="4ae4d-129">To remove a certificate:</span></span> 
1. <span data-ttu-id="4ae4d-130">[設定] アプリに移動し **て、[更新] および [セキュリティ > 証明書] >** します。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-130">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="4ae4d-131">検索ボックスに名前で証明書を検索します。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-131">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="4ae4d-132">証明書を選びます。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-132">Select the certificate.</span></span>
1. <span data-ttu-id="4ae4d-133">[**削除**] をクリック</span><span class="sxs-lookup"><span data-stu-id="4ae4d-133">Click **Remove**</span></span>
1. <span data-ttu-id="4ae4d-134">確認のメッセージが表示されたら、[ **はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ae4d-134">Select **Yes** when prompted for confirmation.</span></span>


![Ceritifcates の設定アプリの証明書ビューアー](images/certificate-viewer-device.jpg)

![[設定] で証明書の UI を使用して証明書をインストールする方法を示す図](images/certificate-device-install.jpg)
