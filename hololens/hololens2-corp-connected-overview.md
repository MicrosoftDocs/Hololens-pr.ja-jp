---
title: 展開ガイド – Dynamics 365 ガイドを使用した企業接続 HoloLens 2 - 概要
description: 企業の接続ネットワーク上で Dynamics 365 ガイドを使用して HoloLens 2 デバイスを登録する方法について学習します。
keywords: HoloLens、管理、企業接続、Dynamics 365 ガイド、AAD、Azure AD、MDM、モバイル デバイス管理
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
ms.openlocfilehash: 3041a31e6a4f8b51385fa02dfddc21d56993721d
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448585"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>展開ガイド - Dynamics 365 ガイドを使用した企業接続 HoloLens 2 - 概要

このガイドは、IT 担当者が組織に Dynamics 365 ガイド (ガイド) を使用して Microsoft HoloLens 2 デバイスを計画および展開するのに役立ちます。 このガイドは、パイロットおよび実稼働環境に最適で、シナリオ [B: 組織](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) のネットワーク ガイド内での展開に似ています。 概念実証をテストした後、このガイドを使用して、HoloLens を組織に統合します。

このガイドでは、デバイスを既存のデバイス管理に登録し、必要に応じてライセンスを適用し、デバイスのセットアップ後にエンドユーザーが Dynamics 365 Guide を操作できるだけでなく、カスタム ラインのビジネス アプリを使用できるのか検証する方法について説明します。 

## <a name="prerequisites"></a>前提条件

次のインフラストラクチャが既に配置されている必要があります。
- Wi-Fi
    - 内部リソースにアクセスし、インターネットまたはクラウド サービスへのアクセスが制限された内部企業ネットワーク
    - デバイス ベースの証明書認証。
- Azure Active Directory (Azure AD) MDM 自動登録に参加する[(Azure AD P1 サブスクリプションが](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) 必要)
- MDM (Intune) マネージ
    - 1 つ以上のアプリケーションが MDM 経由で展開されます。
- ネットワーク 
    - 証明書 (SCEP または PKCS)
    - プロキシの構成
- ユーザーが自分の企業アカウントでサインインする (Azure AD)
    - デバイスごとに 1 人または複数のユーザーがサポートされます。
- 特定の使用例に基づいて適用されるデバイス ロックダウン構成のレベルは、完全に開いたアプリキオスクから単一アプリ キオスクまでさまざまです。

## [<a name="guides-licensing-and-requirements"></a>ガイド ライセンスと要件](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- Azure AD アカウント
- Dynamics 365 アプリケーション PC と HoloLens のガイド
- Dynamics 365 Guides サブスクリプション
    - Microsoft Dataverse (付属)
    - Power Apps (含まれる)
- Power BI Desktop
- ネットワーク接続

![Corp 接続ネットワーク図](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a>展開のステージ
### <a name="prepare"></a>準備
> [!div class="checklist"]
>- [HoloLens 2 デバイスのインフラストラクチャの必需品について学ぶ。](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Azure ADの詳細とセットアップについて説明します。必要な場合は、その設定を行います。](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Id 管理と、Azure アカウントを最適にセットアップする方法ADします。](hololens2-corp-connected-prepare.md#identity-management)
>- [MDM について詳しく知り、Intune でセットアップする準備ができていない場合は、このページを参照してください。](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [証明書ベースの Wi-Fi について理解する。](hololens2-corp-connected-prepare.md#certificates)
>- [プロキシに慣れ親しむ。](hololens2-corp-connected-prepare.md#proxy)
>- [Line of Business Apps の使い方を理解します。](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [組織でガイドを使用する方法について詳しくは、ご覧ください。](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>構成
> [!div class="checklist"]
>- [ユーザーとグループを作成する方法。](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [自動登録を設定する方法。](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [企業の接続Wi-Fiの証明書とプロファイルをWi-Fiする方法。](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [ビジネス行 (LOB) アプリ パッケージのアップロードと割り当て。](hololens2-corp-connected-configure.md#app-deployment)
>- [Dynamics 365 ガイドのセットアップ。](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [キオスク モードを構成する方法 (オプション)。](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [WDAC を構成する方法 (オプション)。](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>展開
> [!div class="checklist"]
>-  [デバイスと MDM を使用して登録を検証します。](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [証明書Wi-Fi検証します。](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [LOB アプリのインストールを検証します。](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [作成と操作を通じてガイドを検証します。](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>保守
> [!div class="checklist"]
>- [HoloLens 2 を更新します。](hololens2-corp-connected-maintain.md#update-hololens)
>- [ガイド (ストア アプリ) を更新する方法。](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [LOB アプリを更新する方法。](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [開発計画。](hololens2-corp-connected-maintain.md#development-plan) 
>- [サポート プランを作成する。](hololens2-corp-connected-maintain.md#support-plan)
>- [デバイス管理オプション。](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>次の手順 
> [!div class="nextstepaction"]
> [企業接続展開 - 準備](hololens2-corp-connected-prepare.md)
