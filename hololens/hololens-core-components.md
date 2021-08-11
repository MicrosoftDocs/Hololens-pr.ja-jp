---
title: 商用環境での HoloLens 2 の展開計画
description: インフラストラクチャ、Azure Active Directory、モバイル デバイス管理など、HoloLens環境でアプリケーションをデプロイおよび管理するための主要なニーズについて説明します。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 8273813d85c3b2df2c1a551fb0322a867a5a9c64fdd05e9a85a2097b1590fb62
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664364"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>商用環境での HoloLens 2 の展開計画

## <a name="overview"></a>概要

> [!NOTE]
> この概要は、IT プロフェッショナルが組織内の 2 つのデバイスを展開および管理するための考慮事項Microsoft HoloLens理解するのに役立ちます。 デバイス エンド ユーザーについては、「Get [your HoloLens 2 ready to use to started」](hololens2-setup.md)を参照してください。

HoloLens 2は Windows 10 Holographicで実行され、堅牢で柔軟な組み込みのモバイル デバイスとアプリ管理テクノロジを組織に提供します。 Windows 10 Holographicは、デバイス、データ、アプリを会社が制御できるエンドツーエンドのデバイス ライフサイクル管理をサポートしています。 このHoloLens 2、包括的なモバイル デバイス管理ソリューションを使用して、デバイスの登録、構成、アプリケーション管理からメンテナンスと提供の削除まで、標準的なライフサイクル プラクティスに簡単に組み込みできます。

次の手順とビデオは、組織内で導入を開始するプロセスHoloLens 2に役立ちます。

| &nbsp; | &nbsp; |
|--|--|
| ![手順 1](images/1green.png)| <br/> **[一般的な展開](hololens-requirements.md)** シナリオ: 展開シナリオを理解し、デバイスをデプロイするために必要なコア コンポーネントHoloLens 2します。 |
| ![手順 2.](images/2green.png)| <br/> **[準備](#prepare)**: アプリケーションの準備に必要なインフラストラクチャの要HoloLens 2。 |
| ![手順 3.](images/3green.png) | <br/> **[構成](#configure)**: クラウドベースのデプロイに必要なコンポーネントを構成する方法について説明します。 |
| ![手順 4.](images/4green.png) | <br/> **[デプロイ](#deploy)**: デバイスをデプロイし、アプリケーションを安全かつ効率的に配布する方法を確認します。 |
| ![手順 5.](images/5green.png) | <br/> **[メンテナンス](#maintain)**: デバイスの状態を適切に維持し、企業ポリシーに準拠するためにHoloLens 2必要な情報を確認します。 |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a>準備

機能の完全なセットをサポートするために必要な重要なインフラストラクチャ HoloLens 2します。

| コンポーネント | [説明] |
|-----------|------------|
| [Azure AD](hololens-identity.md) | アプリケーションの ID とアクセスの管理を提供HoloLens 2  |
| [モバイル デバイス管理](hololens-mdm-configure.md)| テナントHoloLens 2デバイスの管理  |
| [Wi-Fi ネットワーク](hololens-commercial-infrastructure.md)| Wi-Fi利用可能で、デバイスをインターネットに接続できる  |

## <a name="configure"></a>構成

Intune と Autopilot を低タッチ ソリューションとして使用して、組織の HoloLens 2 テナントと MDM にAzure ADを構成します。

| コンポーネント | [説明] |
|-----------|------------|
| [自動登録](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | 初期ログイン後、デバイスは自動的にデバイスに登録Azure AD MDM に登録されます  |
| [アプリケーション ライセンス](hololens2-cloud-connected-configure.md#application-licenses)| ユーザー、ユーザー グループ、またはデバイス グループに適用できます  |
| [Azure ユーザーとグループ](hololens2-cloud-connected-configure.md#azure-users-and-groups) | アプリケーションの構成とライセンスを割り当HoloLens 2  |

## <a name="deploy"></a>デプロイ

デバイスを配布HoloLens 2、その構成を検証します。 

| コンポーネント | [説明] |
|-----------|------------|
| [登録の検証](hololens2-corp-connected-deploy.md#enrollment-validation) | デバイスが Azure ADまたは Azure Portal 設定参加済みである場合の検証 |
| [証明書の検証](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | 設定を確認し、正しく配布されていることを確認する |
| [アプリのインストールを検証する](hololens2-corp-connected-deploy.md#validate-lob-app-install) | アプリが存在し、アプリで動作HoloLens 2 |

## <a name="maintain"></a>管理

mdm Windowsまたは mdm システムと共に Windows Update for Microsoft Store Business を使用して、HoloLens 2アプリのフリートを更新します。

| コンポーネント | [説明] |
|-----------|------------|
| [更新HoloLens 2](hololens-updates.md) | ビジネス向け更新プログラムのWindowsに応じて更新プログラムを構成する |
| [アプリを更新する](app-deploy-overview.md) | MDM システムまたはデバイスを使用して構成Microsoft Store
