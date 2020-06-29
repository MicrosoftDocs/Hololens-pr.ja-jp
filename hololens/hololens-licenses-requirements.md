---
title: Mixed Reality 展開のライセンス
description: ''
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 0da2a2337b3b1f361ffbb698607f304efbf6d193
ms.sourcegitcommit: f3cda6c6b3bfb7ba4be5f4da66d8ed5b03ca807d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830141"
---
# 必要なライセンスを決定する

## モバイル デバイス管理 (MDM) ライセンス ガイダンス

HoloLens デバイスの管理を計画している場合は、Azure AD と MDM が必要です。 Active Directory (AD) を使用して HoloLens デバイスを管理することはできません。
Intune 以外の MDM の使用を計画している場合、[Azure Active Directory ライセンス](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)が必要です。
Intune を MDM として使用する場合は、Intune ライセンスを含むスイートのリストを[以下](https://docs.microsoft.com/intune/fundamentals/licenses)に示します。 **Azure AD はこれらのスイートの大部分に含まれていることにご注意ください。**

## シナリオと製品に必要なライセンスを特定する

### HoloLens ライセンスの要件

HoloLens 第 1 世代デバイスを Windows Holographic for Business にアップグレードする必要がある場合があります。 (アップグレードが必要かどうかを判断するには、「[HoloLens commercial features (HoloLensの商用機能)](holoLens-commercial-features.md#feature-comparison-between-editions)」を参照してください)。

 その場合、次の操作をする必要があります。

- HoloLens Enterprise ライセンスの XML ファイルを取得します
- XML ファイルを HoloLens に適用します。 これは、[プロビジョニング パッケージ](hololens-provisioning.md)または[モバイル デバイス マネージャー](https://docs.microsoft.com/intune/configuration/holographic-upgrade)を使用して実行できます。

### リモート アシスト ライセンスの要件

必要なライセンスとデバイスがあることを確認してください。 更新されたライセンスおよび製品の要件は、[こちら](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements)で確認できます。

1. [リモート アシスト ライセンス](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
1. [Teams フリーミアム/Teams](https://products.office.com/microsoft-teams/free)
1. [Azure Active Directory (Azure AD) ライセンス](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

**[このクロステナント シナリオ](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** の実装を計画している場合、情報バリア ライセンスが必要になる場合があります。 情報バリア ライセンスが必要かどうかを確認するには、[この記事](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary)を参照してください。

### ライセンス要件のガイド

更新されたライセンスおよびデバイスの要件は、[こちら](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)で確認できます。

1. [Azure Active Directory (Azure AD) ライセンス](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [Power BI](https://powerbi.microsoft.com/desktop/)
1. [ガイド](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
