---
title: 商用環境での HoloLens 2 の展開計画
description: インフラストラクチャ、azure active directory、モバイルデバイス管理など、エンタープライズ環境で HoloLens をデプロイおよび管理するための主要なニーズについて説明します。
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
ms.openlocfilehash: 43162389eae82bc09135c62acd40d71048d14db1
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639082"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>商用環境での HoloLens 2 の展開計画

## <a name="overview"></a>概要

> [!NOTE]
> この概要は、IT プロフェッショナルが組織内で Microsoft HoloLens 2 つのデバイスを展開および管理する際の考慮事項を理解するのに役立ちます。 デバイスエンドユーザーについては、「 [HoloLens 2 を使用](hololens2-setup.md)して作業を開始する」を参照してください。

HoloLens 2 は Windows 10 Holographic で実行されます。これにより、堅牢で柔軟性に富んだ、モバイルデバイスおよびアプリ管理テクノロジを組織に提供できます。 Windows 10 Holographic は、エンドツーエンドのデバイスライフサイクル管理をサポートして、企業がデバイス、データ、およびアプリを管理できるようにします。 HoloLens 2 は、包括的なモバイルデバイス管理ソリューションを使用して、デバイスの登録、構成、アプリケーションの管理からメンテナンスや提供終了まで、標準的なライフサイクルプラクティスに簡単に組み込むことができます。

次の手順とビデオを参考にして、組織内で HoloLens 2 を導入することができます。

| &nbsp; | &nbsp; |
|--|--|
| ![手順 1](images/1green.png)| <br/> **[一般的な展開シナリオ](hololens-requirements.md)**: 展開シナリオについて理解し、HoloLens 2 デバイスを展開するために必要なコアコンポーネントについて説明します。 |
| ![手順 2](images/2green.png)| <br/> **[準備](#prepare)**: HoloLens 2 に必要なインフラストラクチャの要点に慣れることができます。 |
| ![手順 3.](images/3green.png) | <br/> **[構成](#configure)**: クラウドベースの展開のために不可欠なコンポーネントを構成する方法について説明します。 |
| ![手順 4](images/4green.png) | <br/> **[デプロイ](#deploy)**: デバイスをデプロイし、アプリケーションを安全かつ効率的に配布する方法について説明します。 |
| ![手順 5.](images/5green.png) | <br/> **[メンテナンス](#maintain)**: HoloLens 2 デバイスの状態を適切に維持し、企業のポリシーに準拠していることを確認するために必要な情報を確認します。 |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a>準備

HoloLens 2 のすべての機能をサポートするために必要な、基本的なインフラストラクチャサービスについて説明します。

| コンポーネント | 説明 |
|-----------|------------|
| [Azure AD](hololens-identity.md) | HoloLens 2 の id とアクセスの管理を提供します  |
| [モバイル デバイス管理](hololens-mdm-configure.md)| テナントに接続されている HoloLens 2 デバイスを管理します  |
| [Wi-fi ネットワーク](hololens-commercial-infrastructure.md)| Wi-Fi が利用可能で、デバイスをインターネットに接続できる  |

## <a name="configure"></a>構成

Intune と自動操縦を低タッチソリューションとして使用して、組織の Azure AD のテナントと MDM に HoloLens 2 を登録して構成することができます。

| コンポーネント | 説明 |
|-----------|------------|
| [自動登録](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | 初回ログイン後、デバイスは Azure AD に自動的に登録され、MDM に登録されます。  |
| [アプリケーションライセンス](hololens2-cloud-connected-configure.md#application-licenses)| ユーザー、ユーザーグループ、またはデバイスグループのいずれかに適用できます。  |
| [Azure のユーザーとグループ](hololens2-cloud-connected-configure.md#azure-users-and-groups) | HoloLens 2 の構成とライセンスを割り当てるのに役立ちます。  |

## <a name="deploy"></a>配置

HoloLens 2 デバイスを配布し、構成を検証します。 

| コンポーネント | 説明 |
|-----------|------------|
| [登録の検証](hololens2-corp-connected-deploy.md#enrollment-validation) | デバイスが設定または Azure Portal から参加して Azure AD かどうかを検証する |
| [証明書の検証](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | 設定を確認し、正常に配布されたことを検証する |
| [アプリのインストールの検証](hololens2-corp-connected-deploy.md#validate-lob-app-install) | アプリが存在し、HoloLens 2 で作業していることを確認します |

## <a name="maintain"></a>管理

MDM システムまたは Microsoft Store と共にビジネスに Windows Update を使用して、HoloLens 2 とアプリの継続的な更新を維持します。

| コンポーネント | 説明 |
|-----------|------------|
| [HoloLens 2 の更新](hololens-updates.md) | ビジネス向け Windows 更新プログラムを使用して、必要に応じて更新を構成します |
| [アプリを更新する](app-deploy-overview.md) | MDM システムまたは Microsoft Store を使用して構成する
