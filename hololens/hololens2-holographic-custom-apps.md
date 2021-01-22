---
title: HoloLens 2 用のカスタム アプリを管理する
description: Device Portal と Visual Studio を使って、HoloLens 2 デバイスにカスタム ホログラフィック アプリをインストール、アンインストール、サイド ロードする方法について説明します。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 01/21/2021
manager: yannisle
keywords: hololens, hololens 2, サイドロード, ストア, UWP, アプリ, インストール
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
ms.openlocfilehash: e3ae180697c889a426108992ba345dc23b96505c
ms.sourcegitcommit: 4c6d982bee72195bef955532738711f2b00ac8be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "11297006"
---
# <span data-ttu-id="e44a0-104">HoloLens 2 用のカスタム アプリを管理する</span><span class="sxs-lookup"><span data-stu-id="e44a0-104">Manage custom apps for HoloLens 2</span></span>

<span data-ttu-id="e44a0-105">HoloLens は、HoloLens 用に特別に作られた新しいアプリだけでなく、Microsoft ストアにある既存のアプリケーションの多くもサポートします。</span><span class="sxs-lookup"><span data-stu-id="e44a0-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> 

<span data-ttu-id="e44a0-106">ストア アプリの詳細については、「ストアでアプリ [を管理する」を参照してください](holographic-store-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="e44a0-106">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e44a0-107">エンタープライズ展開では、両方の方法で使用する開発者モードを有効にすることをお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="e44a0-107">For enterprise deployments, we don't recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="e44a0-108">セキュリティで保護されたアプリの展開方法に関心がある場合は、「アプリ管理: 概要」を [確認してください](app-deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e44a0-108">If you're interested in a secure app deployment method, please review our [App Management: Overview](app-deploy-overview.md).</span></span>

<span data-ttu-id="e44a0-109">HoloLens 2 デバイス用のアプリのインストール方法を探している場合は、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e44a0-109">If you're looking for either developer method of app installation for HoloLens 2 devices, refer to:</span></span>
- [<span data-ttu-id="e44a0-110">Device Portal: アプリのインストール</span><span class="sxs-lookup"><span data-stu-id="e44a0-110">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
- [<span data-ttu-id="e44a0-111">アプリVisual Studioを使用してアプリを展開およびデバッグする</span><span class="sxs-lookup"><span data-stu-id="e44a0-111">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

<span data-ttu-id="e44a0-112">HoloLens (第 1 世代) にカスタム アプリを展開する場合は、このガイドをご覧ください。 [](holographic-custom-apps.md)</span><span class="sxs-lookup"><span data-stu-id="e44a0-112">See our [guide](holographic-custom-apps.md) if you'd like to deploy custom apps on HoloLens (1st gen).</span></span>