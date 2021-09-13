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
ms.openlocfilehash: 6224cd5e07794d9fca3c0a406e787d1a3fd88b43
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034398"
---
# <a name="license-requirements"></a>ライセンスの要件

## <a name="overview"></a>概要
このページでは、組織でマネージドおよびアンマネージド HoloLens 2 デバイスの両方の展開に必要となるライセンスとアカウントについて概要を示します。 Dynamics 365 のライセンスの[リモート アシスト](#dynamics-365-remote-assist)と[ガイド](#dynamics-365-guides)の情報も含まれています。

## <a name="hololens-2-license-and-account-requirements"></a>HoloLens 2 ライセンスとアカウントの要件

 
|       &nbsp;      | マネージド HoloLens | アンマネージド HoloLens |
|-------------------|-----------------|---------------------|
| **ビジネスのユース ケース** | | |
| [クラウドに接続されたデバイスへのデプロイ - 概念またはパイロット デプロイ](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices)  | ✔️| |
| [組織のネットワーク内での展開 - 大規模な展開](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) | ✔️| |
| [安全なオフライン環境での展開](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) | | ✔️ |
| **ライセンス** | | |
| Azure Active Directory | ✔️ | |
| MDM (Intune<sup>1</sup> または <sup>2</sup>) | ✔️  | |
| **Accounts** |  | |
| Azure AD 管理者アカウント | ✔️ |  |
| Azure AD ユーザー アカウント | ✔️ | |
| [Microsoft アカウント (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts)| | ✔️ |
| [ローカル アカウント](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | | ✔️ |
- <sup>1</sup> デバイスの初期セットアップ中の[自動登録](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)。Azure Active Directory を登録し、参加させ、Intune によるデバイスの管理を許可します。
- <sup>2</sup> [Windows Autopilot for HoloLens 2](hololens2-autopilot.md)。IT 管理者とエンド ユーザーの両方にとってプロビジョニング エクスペリエンスが簡単になります。 IT 管理者は、HoloLens 2 のポリシーを事前に構成することができます。初回起動時には、エンドユーザーの操作を必要とせず、すぐに仕事ができる状態でデバイスが展開されます。
- <sup>3</sup> このアカウントは、Windows 構成デザイナー (WCD) を使用して事前に[プロビジョニング](hololens-provisioning.md#provisioning-package-hololens-wizard)しておく必要があります。

> [!IMPORTANT]
> Active Directory (AD) を使用して HoloLens デバイスを管理することはできません。
 
> [!WARNING]
> MSA またはローカル アカウントのいずれかを使用するデバイスでは、複数のユーザーはサポートされません。

## <a name="dynamics-365-licensing-and-requirements"></a>Dynamics 365 のライセンスと要件

### <a name="dynamics-365-remote-assist"></a>Dynamics 365 Remote Assist 

#### <a name="admin"></a>[Admin]

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

- Microsoft Teams または [Teams Freemium](https://products.office.com/microsoft-teams/free)

- ネットワーク接続

この[クロステナント シナリオ](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)を実装する予定の場合は、Information Barriers ライセンスが必要になる可能性があります。 Information Barriers ライセンスが必要かどうかを判断するには、[この記事](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary)を参照してください。

### <a name="dynamics-365-guides"></a>Dynamics 365 Guides 

#### <a name="admin"></a>[Admin]

1. Azure AD アカウント (サブスクリプションの購入とライセンスの割り当てに必要です)
2. Dynamics 365 [Guides のサブスクリプションまたは無料試用版](/dynamics365/mixed-reality/guides/setup-step-one)

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
