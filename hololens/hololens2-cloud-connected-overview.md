---
title: リモートアシスタンスを使用したクラウド接続型 HoloLens 2 の概要
description: Dynamics 365 Remote Assist を使用して、クラウドに接続されたネットワーク上に HoloLens 2 デバイスを登録する方法について説明します。
keywords: HoloLens、管理、クラウド接続、リモートアシスタンス、AAD、Azure AD、MDM、モバイルデバイス管理
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: a44247b4afea747e4b75c974fcae344380909989
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923535"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>展開ガイド–リモートアシスタンスを使用したクラウド接続型 HoloLens 2 –概要

このガイドは、IT プロフェッショナルが、リモートアシスタンスを使用する Microsoft HoloLens 2 デバイスを組織に計画し、展開するのに役立ちます。 これは、さまざまな HoloLens 2 ユースケースにわたる組織への概念実証展開のモデルとして機能します。 セットアップは、 [シナリオ A: クラウド接続デバイスへのデプロイ](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)に似ています。 

このガイドでは、デバイスをデバイス管理に登録する方法、必要に応じてライセンスを適用する方法、およびエンドユーザーがデバイスのセットアップ時にすぐにリモートアシスタンスを使用できることを検証する方法について説明します。 これを行うには、セットアップと実行に必要なインフラストラクチャの重要な部分について説明します。 HoloLens 2 を使用した大規模なデプロイを実現します。 このガイドでは、その他のデバイスの制限や構成は適用されませんが、これらのオプションについては、完了後に調査することをお勧めします。

## <a name="prerequisites"></a>[前提条件]

HoloLens 2 を展開するには、次のインフラストラクチャが適切に配置されている必要があります。 Azure と Intune を設定していない場合は、次のガイドに記載されています。

- Wi-Fi
    - ネットワークは通常、インターネットおよびクラウドサービスで開かれています。
- Azure Active Directory (Azure AD) MDM 自動登録を使用した参加 ([Azure AD P1 サブスクリプション](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) が必要)
- MDM (Intune) で管理
    - MDM を使用して1つ以上のアプリケーションがデプロイされています。
- ユーザーが自分の会社のアカウントでサインインする (Azure AD)
    - デバイスごとに1つまたは複数のユーザーがサポートされています。

:::image type="content" alt-text="クラウド接続シナリオ" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>リモートアシスタンスの詳細

リモートアシスタンスを使用すると、共同での保守と修復、リモート検査、知識の共有とトレーニングを行うことができます。 さまざまな役割と場所のメンバーを接続することで、リモートアシスタンスを使用する技術者は、Microsoft Teams のリモートコラボレーターに接続できます。 ビデオ、スクリーンショット、注釈を組み合わせることにより、同じ場所に t&#39;いなくても、リアルタイムで問題を解決できます。 リモートコラボレーターは参照イメージ、概略図、およびその他の役に立つ情報を挿入できます。技術者は、&#39;、HoloLens でのヘッドアップとハンドフリーの作業中に、概略図を参照できます。

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>リモートアシスタンスのライセンスと要件

- Azure AD アカウント (サブスクリプションの購入とライセンスの割り当てに必要)
- [リモートアシスタンスサブスクリプション](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (または [リモートアシスタンス試用版](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 リモートアシスタンスユーザー

- リモート支援ライセンス
- ネットワーク接続

#### <a name="microsoft-teams-user"></a>Microsoft Teams ユーザー

- Microsoft Teams または [Teams フリーミアム](https://products.office.com/microsoft-teams/free)。
- ネットワーク接続

この [クロステナントシナリオ](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)を実装する予定がある場合は、情報バリアライセンスが必要になることがあります。 情報バリアライセンスが必要かどうかを判断するには、 [この記事](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) をご覧ください。

## <a name="in-this-guide-you-will"></a>このガイドで行うこと:

準備:

> [!div class="checklist"]
> - [HoloLens 2 デバイスのインフラストラクチャの基本について説明します。](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Azure AD とセットアップの詳細について&#39;は、「」を参照してください。](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Id 管理と Azure AD アカウントを最適に設定する方法について説明します。](hololens2-cloud-connected-prepare.md#identity-management)
> - [MDM の詳細を確認し、まだ準備ができていない場合は、Intune を使用してセットアップします。&#39;。](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [リモートアシスタンスのネットワーク要件について説明します。](hololens2-cloud-connected-prepare.md#network)
> - [必要に応じて、組織のリソースに接続するための VPN](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

以下を構成します。

> [!div class="checklist"]
> - [ユーザーとグループを作成する方法。](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Azure AD 内で自動登録を設定する方法について説明します。](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [アプリケーションライセンスを割り当てる方法。](hololens2-cloud-connected-configure.md#application-licenses)

展開: 

> [!div class="checklist"]
> - [HoloLens 2 をセットアップし、登録を検証します。](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [検証リモートアシスタンス通話を行うことができます。](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

保守:

> [!div class="checklist"]
> - [Microsoft Store アプリを使用してリモートアシスタンスを更新する方法。](hololens2-cloud-connected-maintain.md#updates)
> - [サポートプランを作成しています。](hololens2-cloud-connected-maintain.md#support-plan)
> - [開発計画。](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>次のステップ

> [!div class="nextstepaction"]
> [クラウドに接続されたデプロイ-準備](hololens2-cloud-connected-prepare.md)

