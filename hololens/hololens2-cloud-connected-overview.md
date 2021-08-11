---
title: リモートアシスタンスを使用したクラウド接続 HoloLens 2 の概要
description: Dynamics 365 Remote Assist を使用して、クラウドに接続されたネットワーク経由で HoloLens 2 デバイスを登録する方法について説明します。
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
ms.openlocfilehash: 8bba313e7b5ee3d055c2b6ff2c60810baf428ecfa7d5554a1efb4e0aa9e1e98b
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660316"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>展開ガイド–リモートアシスタンスを使用したクラウド接続 HoloLens 2-概要

このガイドは、IT プロフェッショナルが、リモートアシスタンスを使用する Microsoft HoloLens 2 つのデバイスを組織に計画して展開するのに役立ちます。 これは、さまざまな HoloLens 2 のユースケースにわたる組織への概念実証展開のモデルとして機能します。 セットアップは、 [シナリオ A: クラウド接続デバイスへのデプロイ](common-scenarios.md#scenario-a)に似ています。 

このガイドでは、デバイスをデバイス管理に登録する方法、必要に応じてライセンスを適用する方法、およびエンドユーザーがデバイスのセットアップ時にすぐにリモートアシスタンスを使用できることを検証する方法について説明します。 これを行うには、セットアップと実行に必要なインフラストラクチャの重要な部分について説明します。 HoloLens 2 による大規模なデプロイを実現します。 このガイドでは、その他のデバイスの制限や構成は適用されませんが、これらのオプションについては、完了後に調査することをお勧めします。

## <a name="prerequisites"></a>前提条件

HoloLens 2 を展開するには、次のインフラストラクチャが配置されている必要があります。 Azure と Intune を設定していない場合は、次のガイドに記載されています。

これは、「 [シナリオ a: クラウド接続デバイスへの展開](/hololens/common-scenarios#scenario-a)」と同様のセットアップです。これは、多くの概念実証展開に適しています。これには、次のようなものが含まれます。

- Wi-Fi ネットワークは、通常、インターネットおよびクラウドサービスに対して完全に開いています。
- MDM の自動登録を使用した Azure AD 参加-MDM 管理 (Intune)
- ユーザーが自分の会社のアカウントでサインインする (Azure AD)
    - デバイスごとに1つまたは複数のユーザーがサポートされています。

:::image type="content" alt-text="クラウド接続シナリオ" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>リモートアシスタンスの詳細

リモートアシスタンスを使用すると、共同での保守と修復、リモート検査、知識の共有とトレーニングを行うことができます。 さまざまな役割と場所にいるユーザーを接続することで、リモートアシスタンスを使用する技術者は Microsoft Teams のリモートコラボレーターに接続できます。 ビデオ、スクリーンショット、注釈を組み合わせて、同じ場所にいなくてもリアルタイムで問題を解決できます。 リモートコラボレーターは、参照イメージ、概略図、その他の役に立つ情報を技術者の物理的な領域に挿入して、HoloLens でのヘッドアップとハンドフリーの作業中に、概略図を参照できます。

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>リモートアシスタンスのライセンスと要件

- Azure AD アカウント (サブスクリプションの購入とライセンスの割り当てに必要です)
- [Remote Assist のサブスクリプション](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (または [Remote Assist 試用版](/dynamics365/mixed-reality/remote-assist/try-remote-assist))
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist ユーザー

- Remote Assist ライセンス
- ネットワーク接続

#### <a name="microsoft-teams-user"></a>Microsoft Teams ユーザー

- Microsoft Teams または [Teams Freemium](https://products.office.com/microsoft-teams/free)。
- ネットワーク接続

この[クロステナント シナリオ](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)を実装する予定の場合は、Information Barriers ライセンスが必要になる可能性があります。 情報バリアライセンスが必要かどうかを判断するには、「[ベンダーと顧客がフル Dynamics 365 Remote Assist 機能を使用する](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation)」を参照してください。

## <a name="in-this-guide-you-will"></a>このガイドで行うこと:

準備:

> [!div class="checklist"]
> - [HoloLens 2 デバイスのインフラストラクチャに関する基本事項について説明します。](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
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
> - [HoloLens 2 を設定し、登録を検証します。](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [検証リモートアシスタンス通話を行うことができます。](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

保守:

> [!div class="checklist"]
> - [Microsoft Store アプリを使用してリモートアシスタンスを更新する方法。](hololens2-cloud-connected-maintain.md#updates)
> - [サポートプランを作成しています。](hololens2-cloud-connected-maintain.md#support-plan)
> - [開発計画。](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>次のステップ

> [!div class="nextstepaction"]
> [クラウドに接続されたデプロイ-準備](hololens2-cloud-connected-prepare.md)

