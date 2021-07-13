---
title: HoloLens 2 用のカスタム アプリを管理する
description: デバイスポータルと Visual Studio を使用して HoloLens 2 デバイスにカスタム holographic アプリをインストール、アンインストール、およびサイドロードする方法について説明します。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 01/21/2021
manager: yannisle
keywords: hololens、hololens 2、サイドロード、サイドロード、サイドロード、ストア、uwp、アプリ、インストール
ms.prod: hololens
ms.sitesec: library
author: joyjaz
ms.author: v-jjaswinski
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens 2
ms.openlocfilehash: d2280a794455090c61a7bf30bc5dc5b8faf5adbe
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636403"
---
# <a name="manage-custom-apps-for-hololens-2"></a><span data-ttu-id="ba1a6-104">HoloLens 2 用のカスタム アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="ba1a6-104">Manage custom apps for HoloLens 2</span></span>

<span data-ttu-id="ba1a6-105">HoloLens は、Microsoft Store から多くの既存のアプリケーションをサポートするだけでなく、HoloLens 専用に構築された新しいアプリもサポートします。</span><span class="sxs-lookup"><span data-stu-id="ba1a6-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> 

<span data-ttu-id="ba1a6-106">ストアアプリの詳細については、「 [ストアアプリを使用したアプリの管理](holographic-store-apps.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba1a6-106">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ba1a6-107">企業の展開では、開発者モードを有効にすることはお勧めしません。どちらの方法でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="ba1a6-107">For enterprise deployments, we don't recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="ba1a6-108">セキュリティで保護されたアプリのデプロイ方法に関心がある場合は、 [アプリ管理の概要](app-deploy-overview.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba1a6-108">If you're interested in a secure app deployment method, please review our [App Management: Overview](app-deploy-overview.md).</span></span>

<span data-ttu-id="ba1a6-109">HoloLens 2 デバイスに対して開発者向けのアプリのインストール方法をお探しの場合は、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba1a6-109">If you're looking for either developer method of app installation for HoloLens 2 devices, refer to:</span></span>

- [<span data-ttu-id="ba1a6-110">デバイスポータル: アプリのインストール</span><span class="sxs-lookup"><span data-stu-id="ba1a6-110">Device Portal: Installing an App</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
- [<span data-ttu-id="ba1a6-111">Visual Studio を使用したアプリの配置とデバッグ</span><span class="sxs-lookup"><span data-stu-id="ba1a6-111">Using Visual Studio to deploy and debug Apps</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

<span data-ttu-id="ba1a6-112">HoloLens (第1世代) でカスタムアプリをデプロイする場合は、[ガイド](holographic-custom-apps.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba1a6-112">See our [guide](holographic-custom-apps.md) if you'd like to deploy custom apps on HoloLens (1st gen).</span></span>
