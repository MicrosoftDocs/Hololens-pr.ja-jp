---
title: デプロイ ガイド – Dynamics 365 HoloLens 2を使用した企業の接続済みサービス - 概要
description: Dynamics 365 Guides を使用HoloLens 2デバイスを企業の接続済みネットワークに登録する方法について学習します。
keywords: HoloLens, 管理, 企業接続, Dynamics 365 ガイド, AAD, Azure AD, MDM, Mobile デバイス管理
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: ee6c24f65e5990f1e84a71d86b24dd782cf9f4cc
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397205"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>デプロイ ガイド - Dynamics 365 HoloLens 2を使用した企業接続済みサービス - 概要

このガイドは、IT プロフェッショナルが Dynamics 365 ガイド (ガイド) Microsoft HoloLens 2 つのデバイスを計画し、組織に展開するのに役立ちます。 このガイドは、パイロットおよび実稼働環境のデプロイに最適であり、「シナリオ B: 組織のネットワーク内にデプロイする」 [ガイドに似](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) ています。 概念実証をテストした後、このガイドを使用して、HoloLens を組織に統合します。

このガイドでは、デバイスを既存のデバイス管理に登録し、必要に応じてライセンスを適用し、エンド ユーザーが Dynamics 365 ガイドを操作できるだけでなく、デバイスのセットアップ後にカスタムの業務アプリを使用できるのを検証する方法について説明します。 

## <a name="prerequisites"></a>前提条件

次のインフラストラクチャが既に配置されている必要があります。
- Wi-Fi
    - 内部リソースにアクセスし、インターネットまたはクラウド サービスへのアクセスが制限されている内部企業ネットワーク
    - デバイス ベースの証明書認証。
- Azure Active Directory (Azure AD) MDM 自動登録との参加 (Azure AD[P1 サブスクリプションが](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) 必要)
- MDM (Intune) マネージド
    - 1 つ以上のアプリケーションが MDM 経由でデプロイされます。
- ネットワーク 
    - 証明書 (SCEP または PKCS)
    - [プロキシ構成]
- ユーザーが自分の企業アカウントでサインインする (Azure AD)
    - デバイスごとに 1 人または複数のユーザーがサポートされます。
- フル オープンからシングル アプリ キオスクまで、特定の使用事例に基づいて適用されるさまざまなレベルのデバイス ロックダウン構成。

## <a name="guides-licensing-and-requirements"></a>[ガイドのライセンスと要件](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- Azure AD アカウント
- Dynamics 365 Guides アプリケーション PC と HoloLens
- Dynamics 365 ガイドサブスクリプション
    - Microsoft Dataverse 定型文 (含まれています)
    - Power Apps (付属)
- Power BI Desktop
- ネットワーク接続

[![Corp 接続ネットワーク図、ステージ 1 ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Corp 接続ネットワーク図、ステージ 2 ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

## <a name="in-this-guide-you-will"></a>このガイドで行うこと:
### <a name="prepare"></a>準備
> [!div class="checklist"]
>- [HoloLens 2 デバイスのインフラストラクチャの基本について説明します。](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Azure AD の詳細については、「」を参照してください。](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Id 管理と Azure AD アカウントを最適に設定する方法について説明します。](hololens2-corp-connected-prepare.md#identity-management)
>- [まだ準備ができていない場合は、MDM の詳細を確認し、Intune をセットアップしてください。](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [証明書ベースの Wi-fi について理解を深めます。](hololens2-corp-connected-prepare.md#certificates)
>- [プロキシについて理解を深めます。](hololens2-corp-connected-prepare.md#proxy)
>- [基幹業務アプリを使用する方法について説明します。](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [組織にガイドを使用する方法の詳細については、こちらを参照してください。](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>構成
> [!div class="checklist"]
>- [ユーザーとグループを作成する方法。](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [自動登録をセットアップする方法。](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [企業 Wi-Fi 接続用の Wi-Fi 証明書とプロファイルを設定する方法について説明します。](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [基幹業務 (LOB) アプリパッケージをアップロードして割り当てます。](hololens2-corp-connected-configure.md#app-deployment)
>- [Dynamics 365 ガイドをセットアップします。](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [キオスクモードを構成する方法 (省略可能)。](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [WDAC を構成する方法 (省略可能)。](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>デプロイ
> [!div class="checklist"]
>-  [デバイスと MDM を使用して登録を検証します。](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [証明書Wi-Fi検証します。](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [LOB アプリのインストールを検証します。](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [作成と運用を通じてガイドを検証します。](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>管理
> [!div class="checklist"]
>- [更新HoloLens 2。](hololens2-corp-connected-maintain.md#update-hololens)
>- [ガイド (ストア アプリ) を更新する方法。](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [LOB アプリを更新する方法。](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [開発計画。](hololens2-corp-connected-maintain.md#development-plan) 
>- [サポート プランを作成する。](hololens2-corp-connected-maintain.md#support-plan)
>- [デバイス管理オプション。](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>次のステップ 
> [!div class="nextstepaction"]
> [企業に接続されたデプロイ - 準備](hololens2-corp-connected-prepare.md)
