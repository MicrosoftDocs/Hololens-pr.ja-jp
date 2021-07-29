---
title: ライセンスの要件
description: モバイル デバイス管理、HoloLens、Remote Assist に必要なすべてのライセンス要件とガイドラインを常に最新の状態に保ちます。
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
- HoloLens 2
ms.openlocfilehash: bd7a7d03c81dced4fb66d8ebb176887811e823c9
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640282"
---
# <a name="license-requirements"></a>ライセンスの要件

## <a name="hololens-2-device-managed"></a>HoloLens 2 デバイス (マネージド)

[Azure AD アカウント](/azure/active-directory/)

> [!IMPORTANT]
> Active Directory (AD) を使用して HoloLens デバイスを管理することはできません。

[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) または別の MDM。
- [Windows Autopilot for HoloLens 2](hololens2-autopilot.md) - IT 管理者とエンド ユーザーの両方にとってプロビジョニング エクスペリエンスが簡単になります。 IT 管理者は、HoloLens 2 のポリシーを事前に構成することができます。初回起動時には、エンドユーザーの操作を必要とせず、すぐに仕事ができる状態でデバイスが展開されます。 

  > [!NOTE]
  > Windows Autopilot を使用する場合、ロータッチの Autopilot フローとデバイスの展開のためには、[Azure P1](/azure/active-directory/fundamentals/active-directory-whatis) と[自動登録](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)を最初に構成する必要があります。 

### <a name="business-use-case"></a>ビジネスのユース ケース: 

- [展開シナリオ A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) - 概念実証またはパイロット展開。

- [展開シナリオ B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) - 大規模な展開。

## <a name="hololens-2-device-only-non-managed"></a>HoloLens 2 デバイスのみ (非マネージド)

Microsoft アカウント (MSA) またはローカル アカウントのいずれかを使用する場合、これらのアカウント用に追加のライセンスは必要ありません。

[ローカル アカウント](/windows/security/identity-protection/access-control/local-accounts)

- このアカウントは、Windows 構成デザイナー (WCD) を使用して事前に[プロビジョニング](hololens-provisioning.md#provisioning-package-hololens-wizard)しておく必要があります。

[Microsoft アカウント (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> これらのアカウントのいずれかを使用するデバイスでは、複数のユーザーはサポートされません。

### <a name="business-use-case"></a>ビジネスのユース ケース: 

- [展開シナリオ C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) - オフラインまたはセキュリティで保護された展開。
 
## <a name="dynamics-365-licensing-and-requirements"></a>Dynamics 365 のライセンスと要件

### <a name="dynamics-365-remote-assist"></a>Dynamics 365 Remote Assist 

#### <a name="admin"></a>管理者

- Azure AD アカウント (サブスクリプションの購入とライセンスの割り当てに必要です)
- [Remote Assist のサブスクリプション](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (または [Remote Assist 試用版](/dynamics365/mixed-reality/remote-assist/try-remote-assist))
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist ユーザー

- Azure AD アカウント

- Remote Assist ライセンス 

  > [!NOTE]
  > Microsoft Teams は Remote Assist にバンドルされています

- ネットワーク接続

#### <a name="microsoft-teams-user"></a>Microsoft Teams ユーザー

- Azure AD アカウント

- Microsoft Teams または [Teams Freemium](https://products.office.com/microsoft-teams/free)。

- ネットワーク接続

この[クロステナント シナリオ](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)を実装する予定の場合は、Information Barriers ライセンスが必要になる可能性があります。 Information Barriers ライセンスが必要かどうかを判断するには、[この記事](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary)を参照してください。

### <a name="dynamics-365-guides"></a>Dynamics 365 Guides 

#### <a name="admin"></a>管理者

- Azure AD アカウント (サブスクリプションの購入とライセンスの割り当てに必要です)
- Dynamics 365 [Guides のサブスクリプションまたは無料試用版](/dynamics365/mixed-reality/guides/setup-step-one)

#### <a name="guides-author"></a>Guides 作成者

1. Azure AD アカウント
1. [Dynamics 365 Guides ライセンス](/dynamics365/mixed-reality/guides/requirements)
1. PC または HoloLens にインストールされた Dynamics 365 Guides アプリケーション
1. [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (Analytics ダッシュボードの表示に使用されます)
1. 作成者ロール (ガイドの作成用)
1. ネットワーク接続

#### <a name="guides-user"></a>Guides ユーザー

1. Azure AD アカウント
1. [Dynamics 365 Guides ライセンス](/dynamics365/mixed-reality/guides/requirements)
1. HoloLens にインストールされた Dynamics 365 Guides アプリ
1. オペレーター ロール (Guides のテストまたは使用目的)
1. ネットワーク接続
