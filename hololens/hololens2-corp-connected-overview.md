---
title: 展開ガイド– Dynamics 365 Guides による企業接続 HoloLens 2-概要
description: 企業に接続されたネットワーク経由で Dynamics 365 Guides を使用して HoloLens 2 デバイスを登録する方法について説明します。
keywords: HoloLens、管理、企業接続、Dynamics 365 Guides、AAD、Azure AD、MDM、モバイルデバイス管理
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
ms.openlocfilehash: 67e34ea275ef73adda840ee4f44d9c0c3c9440ef0bd2aef48cb7aaa971219220
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660133"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>展開ガイド-Dynamics 365 Guides による企業接続 HoloLens 2-概要

このガイドは、IT プロフェッショナルが Dynamics 365 Guides (ガイド) を使用して Microsoft HoloLens 2 つのデバイスを組織に計画して展開するのに役立ちます。 このガイドは、パイロットと運用環境の展開に適しており、 [シナリオ B: 組織のネットワークガイド内での展開](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) に似ています。 概念実証をテストした後は、このガイドを使用して、HoloLens を組織に統合することによって先に進むことができます。

このガイドでは、既存のデバイス管理にデバイスを登録する方法、必要に応じてライセンスを適用する方法、およびエンドユーザーが Dynamics 365 ガイドを操作できること、およびデバイスのセットアップ後にカスタムの基幹業務アプリを使用できることを検証する方法について説明します。 

## <a name="prerequisites"></a>前提条件

次のインフラストラクチャが既に配置されている必要があります。
- Wi-Fi
    - 内部リソースにアクセスし、インターネットまたはクラウドサービスへのアクセスが制限されている社内ネットワーク
    - デバイスベースの証明書認証。
- Azure Active Directory (Azure AD) MDM 自動登録を使用した参加 ([Azure AD P1 サブスクリプション](/azure/active-directory/fundamentals/active-directory-whatis)が必要)
- MDM (Intune) で管理
    - MDM を使用して1つ以上のアプリケーションがデプロイされています。
- ネットワーク 
    - 証明書 (SCEP または PKCS)
    - [プロキシ構成]
- ユーザーが自分の会社のアカウントでサインインする (Azure AD)
    - デバイスごとに1つまたは複数のユーザーがサポートされています。
- 完全にオープンからシングルアプリキオスクまで、特定のユースケースに基づいて適用されるさまざまなレベルのデバイスロックダウン構成。

## <a name="guides-licensing-and-requirements"></a>[ライセンスと要件のガイド](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- Azure AD アカウント
- Dynamics 365 Guides アプリケーション PC と HoloLens
- Dynamics 365 Guides サブスクリプション
    - Microsoft Dataverse 定型文 (含まれています)
    - Power Apps (含まれています)
- Power BI Desktop
- ネットワーク接続

[![Corp 接続ネットワーク図、ステージ 1 ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Corp 接続ネットワーク図、ステージ 2 ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

## <a name="in-this-guide-you-will"></a>このガイドで行うこと:
### <a name="prepare"></a>準備
> [!div class="checklist"]
>- [HoloLens 2 デバイスのインフラストラクチャに関する基本事項について説明します。](hololens2-corp-connected-prepare.md#infrastructure-essentials)
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
>- [Dynamics 365 Guides セットアップします。](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [キオスクモードを構成する方法 (省略可能)。](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [WDAC を構成する方法 (省略可能)。](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>デプロイ
> [!div class="checklist"]
>-  [デバイスと MDM を使用して登録を検証します。](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Wi-Fi 証明書を検証します。](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [LOB アプリのインストールを検証します。](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [作成と運用を通じてガイドを検証します。](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>管理
> [!div class="checklist"]
>- [HoloLens 2 を更新します。](hololens2-corp-connected-maintain.md#update-hololens)
>- [ガイドを更新する方法 (ストアアプリ)](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [LOB アプリを更新する方法。](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [開発計画。](hololens2-corp-connected-maintain.md#development-plan) 
>- [サポートプランを作成しています。](hololens2-corp-connected-maintain.md#support-plan)
>- [デバイス管理オプション。](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>次のステップ 
> [!div class="nextstepaction"]
> [企業に接続された展開-準備](hololens2-corp-connected-prepare.md)
