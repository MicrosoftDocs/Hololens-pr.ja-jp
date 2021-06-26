---
title: 商用HoloLens 2でのデプロイの計画
description: インフラストラクチャ、Azure Active Directory、モバイル デバイス管理など、エンタープライズ環境で HoloLens をデプロイおよび管理するための主要なニーズについて説明します。
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
ms.openlocfilehash: 684059b1ab91860dc6af63cbd6f0927876fefb8c
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961484"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>商用HoloLens 2でのデプロイの計画

## <a name="overview"></a>概要
> [!NOTE]
> この概要は、IT プロフェッショナルが組織内の 2 つのデバイスをMicrosoft HoloLens管理するための考慮事項を理解するのに役立ちます。 デバイス エンド ユーザーについては、「 [開始する基本」](hololens2-setup.md) を参照してください。

HoloLens 2は、堅牢でWindows 10 Holographicな組み込みのモバイル デバイスとアプリ管理テクノロジを組織に提供する、アプリケーション上で実行されます。 Windows 10 Holographicは、デバイス、データ、アプリを会社が制御できるエンドツーエンドのデバイス ライフサイクル管理をサポートしています。 このHoloLens 2、包括的なモバイル デバイス管理ソリューションを使用して、デバイスの登録、構成、アプリケーション管理からメンテナンスと提供の削除まで、標準的なライフサイクル プラクティスに簡単に組み込みできます。

次の手順は、組織内で導入を開始するプロセスHoloLens 2に役立ちます。

| | |
|--|--|
| ![手順 1](images/1green.png)| <br/> **[一般的な展開シナリオ](hololens-requirements.md)**: 展開シナリオを理解し、デバイスを展開するために必要なコア コンポーネントHoloLens 2します。 |
| ![手順 2](images/2green.png)| <br/> **[準備](#prepare)**: アプリケーションの準備に必要なインフラストラクチャの要HoloLens 2。 |
| ![手順 3.](images/3green.png) | <br/> **[構成](#configure)**: クラウドベースのデプロイに必要なコンポーネントを構成する方法について説明します。 |
| ![手順 4](images/4green.png) | <br/> **[デプロイ](#deploy)**: デバイスをデプロイし、アプリケーションを安全かつ効率的に配布する方法を確認します。 |
| ![手順 5.](images/5green.png) | <br/> **[メンテナンス](#maintain)**: デバイスの状態を適切に維持し、企業ポリシーに準拠するためにHoloLens 2必要な情報を確認します。 |

## <a name="prepare"></a>準備

機能の完全なセットをサポートするために必要な重要なインフラストラクチャ サービスHoloLens 2します。 

| コンポーネント | 説明 |
|-----------|------------|
| [Azure AD](hololens-identity.md) | アプリケーションの ID とアクセスの管理を提供HoloLens 2  |
| [モバイル デバイス管理](hololens-mdm-configure.md)| テナントHoloLens 2デバイスを管理します  |
| [Wi-Fi ネットワーク](hololens-commercial-infrastructure.md)| Wi-Fi利用可能で、デバイスをインターネットに接続できる  |

## <a name="configure"></a>構成

Intune と Autopilot を低タッチ ソリューションとして使用して、組織HoloLens 2テナントと MDM にAzure ADを構成します。

| コンポーネント | 説明 |
|-----------|------------|
| [自動登録](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | 初期ログイン後、デバイスは自動的にデバイスに登録Azure AD MDM に登録されます  |
| [アプリケーション ライセンス](hololens2-cloud-connected-configure.md#application-licenses)| ユーザー、ユーザー グループ、またはデバイス グループに適用できます  |
| [Azure ユーザーとグループ](hololens2-cloud-connected-configure.md#azure-users-and-groups) | アプリケーションの構成とライセンスを割り当HoloLens 2  |

## <a name="deploy"></a>配置

デバイスを配布HoloLens 2、その構成を検証します。 

| コンポーネント | 説明 |
|-----------|------------|
| [登録の検証](hololens2-corp-connected-deploy.md#enrollment-validation) | デバイスが [設定Azure AD Azure Portal から参加済みである] を確認します |
| [証明書の検証](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | 設定を確認し、正しく配布されていることを確認する |
| [アプリのインストールを検証する](hololens2-corp-connected-deploy.md#validate-lob-app-install) | アプリが存在し、アプリで動作HoloLens 2 |

## <a name="maintain"></a>管理

MDM Windows Update for Businessまたは MDM システムと共にMicrosoft Storeを使用して、デバイスとアプリのHoloLens 2を維持します。

| コンポーネント | 説明 |
|-----------|------------|
| [更新HoloLens 2](hololens-updates.md) | ビジネス向け Windows 更新プログラムを使用して必要に応じて更新プログラムを構成する |
| [アプリを更新する](app-deploy-overview.md) | MDM システムまたはデバイスを使用して構成Microsoft Store
