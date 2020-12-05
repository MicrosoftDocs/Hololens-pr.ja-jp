---
title: 展開ガイド–クラウドに接続された HoloLens 2 展開でのリモートアシストの準備
description: クラウドに接続されたネットワーク経由で HoloLens デバイスを登録するための準備方法
keywords: HoloLens、管理、クラウド接続、リモートアシスト、AAD、Azure AD、MDM、モバイルデバイス管理
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
ms.openlocfilehash: 0e9222df2c387fab8f61a585d3a7f3966b9ecd31
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196340"
---
# クラウド接続ガイドの準備

この記事を終了すると、aad と MDM を設定し、AAD アカウントとネットワーク要件の詳細を理解することができます。 このセクションでは、お客様と組織が HoloLens 2 をクラウドに展開して Dynamics 365 リモートアシストを使用するための準備を行います。 インフラストラクチャの各要素の重要性に加え、必要に応じてこれらの要素を設定するためのガイドへのリンクが提供されます。

## インフラストラクチャの基礎

個人用と企業の両方の展開シナリオでは、MDM システムは Windows 10 ホログラフィックデバイスの展開と管理に必要不可欠なインフラストラクチャです。 Azure AD Premium サブスクリプションは、ID プロバイダーとして推奨され、特定の機能をサポートするために必要です。

### Azure Active Directory

Azure AD は、ID とアクセス管理を提供する、クラウド ベースのディレクトリ サービスです。 Microsoft Office 365 または Intune を使用している組織には、既に Azure AD が使用されています。これには、無料、Premium P1、Premium P2 (「 [Azure Active Directory edition](https://azure.microsoft.com/documentation/articles/active-directory-editions)」をご覧ください) が含まれています。Azure AD デバイスの登録はすべてのエディションでサポートされていますが、MDM の自動登録を有効にするには、このガイドで後ほど利用する必要があります。

> [!IMPORTANT]
> HoloLens デバイスがオンプレミスの AD join をサポートしていない場合は、Azure Active Directory を使用することが重要です。 Azure Active Directory を既にセットアップして&#39;ない場合は、このリンクの手順に従って、 [Azure Active directory で新しいテナントを作成](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)します。

## Id 管理

従業員は、1つのアカウントを使用してデバイスを初期化する必要があります。そのためには、組織が最初に有効にするアカウントを管理する必要があることを&#39;します。 選択したアカウントによって、デバイスを制御するユーザーが決まり、管理機能に影響があります。

このガイドでは、使用されている [id](https://docs.microsoft.com/hololens/hololens-identity) に対して、AAD アカウントまたは Azure Active Directory アカウントを使用することを選択しました。 使用する AAD アカウントには、次のようないくつかの利点があります。

- 従業員は azure AD アカウントを使用して、Azure ad にデバイスを登録し、組織&#39;s MDM ソリューション (AAD + MDM – Azure AD Premium が必要) に自動的に登録します。
- AAD アカウントでは、 [シングルサインオン](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on)がサポートされています。 ユーザーがリモートアシストにサインインすると、サインインした AAD ユーザーからのユーザーの Id が認識され、ユーザーはアプリにサインインして、簡素化されたエクスペリエンスを提供します。
- AAD アカウント[には、Windows Hello For business に](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)よる追加の[認証オプション](https://docs.microsoft.com/hololens/hololens-identity)があります。 虹彩のログインに加えて、他のデバイスからサインインしたり、FIDO のセキュリティキーを使用したりすることができます。

### モバイル デバイス管理

エンタープライズモビリティ + セキュリティの一部である Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)は、テナントに接続されたデバイスを管理するクラウドベースの MDM システムです。 Office 365 と同様に、Intune は id 管理に Azure AD を使用するため、従業員は Office 365 にサインインするために使用するデバイスを Intune に登録するときに同じ資格情報を使用します。 Intune は、iOS や Android などの他のオペレーティングシステムを実行しているデバイスもサポートしており、完全な MDM ソリューションを提供します。 このガイドの目的のために、ここでは、HoloLens 2 を使用して、規模の拡大/縮小でクラウドの展開を有効にするために、Intune の使用に重点を置いて&#39;ます。

> [!IMPORTANT]
> モバイルデバイス管理を使用することが重要です。 まだ&#39;していない場合は、このガイドに従って、「 [Intune の使用を開始](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)する」をご覧ください。

> [!NOTE]
> 複数の MDM システムが Windows 10 をサポートしており、ほとんどは、個人のデバイスおよび企業のデバイスの展開のシナリオをサポートしています。 現在、Windows 10 ホログラフィックをサポートしている MDM プロバイダーには、エアウォッチ、MobileIron、その他の機能が含まれています。 業界をリードする MDM ベンダーのほとんどは既に Azure AD との統合をサポートしています。 Azure AD をサポートする MDM ベンダーは [Azure Marketplace](https://azure.microsoft.com/marketplace/) で検索できます。

## ネットワーク

この設定では、使用可能な open Wi-Fi ネットワークから、HoloLens 2 デバイスがインターネットに接続されていることを想定しています。 ユーザーは場所に基づいてネットワーク接続を変更する必要があるため、 [HoloLens デバイスを wi-fi に接続](https://docs.microsoft.com/hololens/hololens-network)する方法について説明します。

Dynamics 365 リモートアシスタンスでは、ビデオ通話のエクスペリエンスに影響を与える可能性のある、帯域幅、待ち時間、ジッタ、パケット損失など、さまざまなネットワーク条件があります。 帯域幅が少なくなっている環境では、音声通話とビデオ通話が可能な場合がありますが、機能の低下が発生する可能性があります。 HoloLens で Dynamics 365 リモートアシストを使用する場合は、次のネットワーク要件を念頭に置いておく必要があります。

**最小** : 1.5 Mbps の最大速度は、hd 1080p の解像度 30 fps でピアツーピア HD 品質のビデオ通話に必要です。

**最適:** HD 1080p の解像度でピアツーピアの HD 品質ビデオ通話を行うには、4-5 Mbps が必要です。

詳細情報:

- [ネットワーク要件](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [ネットワーク最適化の推奨事項](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### オプション: HoloLens を VPN に接続する

このガイドに接続しているデバイスは、外部のクラウドネットワーク経由でネットワークに接続されます。 会社のリソースにアクセスするには、VPN 経由でデバイスを接続する必要が&#39;ます。 デバイスを VPN に接続するには、いくつかの方法があります。この方法では、エンドユーザーがデバイスの UI を使用して接続できるか、デバイスを管理して、PPKG または MDM から VPN プロファイルを受信するかのいずれかの方法があります。 VPN の勝ち&#39;を設定する方法については、この記事で説明します。 d&#39;、さまざまな VPN プロトコルの詳細や VPN の管理方法については、 [HoloLens と vpn に関する情報を](https://docs.microsoft.com/hololens/hololens-network#vpn)参照してください。

## 次のステップ

> [!div class="nextstepaction"]
> [クラウド接続展開-構成](hololens2-cloud-connected-configure.md)
