---
title: デプロイガイド-クラウドに接続された HoloLens 2 の大規模なデプロイとリモートアシスタンス-準備
description: Azure active directory と id 管理を使用して、クラウドに接続されたネットワーク経由で HoloLens デバイスを登録する準備をする方法について説明します。
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
ms.openlocfilehash: 067917396631f9a89a50b13ef1b7dcca8b631f52
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309348"
---
# <a name="prepare---cloud-connected-guide"></a>準備-クラウド接続ガイド

この記事を終了すると、Azure AD、MDM がセットアップされ、Azure AD アカウントとネットワーク要件の使用方法について理解できるようになります。 ガイドのこのセクションでは、お客様の組織が HoloLens 2 をクラウドに展開し、Dynamics 365 リモートアシスタンスを使用するための準備について説明します。 インフラストラクチャの各部分の重要性を確認すると共に、必要に応じてこれらの要素を設定するためのガイドへのリンクも提供します。

## <a name="infrastructure-essentials"></a>インフラストラクチャの要点

個人と企業の両方の展開シナリオで、MDM システムは、Windows 10 Holographic デバイスを展開および管理するために必要不可欠なインフラストラクチャです。 Azure AD Premium サブスクリプションは、ID プロバイダーとして推奨され、特定の機能をサポートするために必要です。

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD は、ID とアクセス管理を提供する、クラウド ベースのディレクトリ サービスです。 Microsoft Office 365 または Intune を使用する組織は、既に Azure AD を使用しています。これには、Free、Premium P1、Premium P2 の3つのエディションがあります ( [Azure Active Directory のエディション](https://azure.microsoft.com/documentation/articles/active-directory-editions)を参照)。すべてのエディションでデバイスの登録 Azure AD サポートされますが、後でこのガイドで使用する MDM の自動登録を有効にするには Premium P1 が必要です。

> [!IMPORTANT]
> HoloLens デバイスはオンプレミスの AD join をサポートしていないため、Azure Active Directory を用意することが不可欠です。 まだ Azure Active Directory がセットアップされていない場合&#39;は、このリンクの手順に従って作業を開始し、 [Azure Active Directory で新しいテナントを作成](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)します。

## <a name="identity-management"></a>ID 管理

従業員は、1つのアカウントを使用してデバイスを初期化することができます。これにより、最初に有効にするアカウントを組織が制御する必要が&#39;ます。 選択したアカウントによって、デバイスを制御するユーザーが決まり、管理機能に影響があります。

このガイドでは、使用する [id](https://docs.microsoft.com/hololens/hololens-identity) に Azure AD アカウントまたは Azure Active Directory アカウントを使用することを選択しました。 使用する Azure AD アカウントには、次のようないくつかの利点があります。

- 従業員は Azure AD アカウントを使用して Azure AD にデバイスを登録し、組織&#39;の MDM ソリューションに自動的に登録します (Azure AD + MDM – Azure AD Premium が必要です)。
- Azure AD アカウントは [シングルサインオンを](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on)サポートします。 ユーザーがリモートアシスタンスにサインインすると、サインインした Azure AD ユーザーからの Id が認識され、ユーザーはアプリにサインインして使いやすくなります。
- Azure AD アカウント[には、Windows Hello For Business を](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)使用した追加の[認証オプション](https://docs.microsoft.com/hololens/hololens-identity)があります。 虹彩サインインに加えて、ユーザーは別のデバイスからサインインすることも、FIDO セキュリティキーを使用することもできます。

### <a name="mobile-device-management"></a>モバイル デバイス管理

Enterprise Mobility + Security の一部である Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)は、テナントに接続されているデバイスを管理するクラウドベースの MDM システムです。 Office 365 と同様に、Intune は id 管理に Azure AD を使用するので、従業員は同じ資格情報を使用して、Office 365 へのサインインに使用するデバイスを Intune に登録します。 Intune は、iOS や Android などの他のオペレーティングシステムを実行するデバイスもサポートして、完全な MDM ソリューションを提供します。 このガイドでは、Intune を使用して、HoloLens 2 で大規模なクラウドデプロイを有効にする方法について&#39;説明します。

> [!IMPORTANT]
> モバイルデバイス管理が不可欠です。 まだセットアップしていない場合は、このガイドに従って、 [Intune の使用を開始](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)してください。&#39;します。

> [!NOTE]
> 複数の MDM システムが Windows 10 をサポートしており、ほとんどは、個人のデバイスおよび企業のデバイスの展開のシナリオをサポートしています。 現在、Windows 10 Holographic をサポートする MDM プロバイダーには、放映 Watch、MobileIron などが含まれています。 業界をリードする MDM ベンダーのほとんどは既に Azure AD との統合をサポートしています。 Azure AD をサポートする MDM ベンダーは [Azure Marketplace](https://azure.microsoft.com/marketplace/)で検索できます。

## <a name="network"></a>ネットワーク

このセットアップでは、使用可能な任意のオープン Wi-Fi ネットワークから、インターネットに接続する HoloLens 2 デバイスを想定しています。 ユーザーは、場所に基づいてネットワーク接続を変更する必要があるため、 [HoloLens デバイスを wi-fi に接続](https://docs.microsoft.com/hololens/hololens-network)する方法について説明します。

Dynamics 365 リモートアシスタンスでは、ビデオの呼び出しエクスペリエンスに影響を与える可能性がある、帯域幅、待ち時間、ジッター、パケット損失など、さまざまなネットワーク状態があります。 帯域幅が狭い環境では、音声通話やビデオ通話が可能な場合がありますが、機能の低下が発生する可能性があります。 HoloLens で Dynamics 365 リモートアシスタンスを使用する場合は、次のネットワーク要件を念頭に置く必要があります。

**最小** : 1.5 Mbps のアップ/ダウンは、hd 1080p を 30 fps で解決することで、ピアツーピアの hd 品質ビデオを呼び出すときに必要です。

**最適:** HD 1080p の解像度を使用したピアツーピアの HD 品質のビデオ通話では、4-5 Mbps のアップ/ダウンが想定されています。

詳細情報:

- [ネットワークの要件](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [ネットワーク最適化に関する推奨事項](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>省略可能: HoloLens を VPN に接続する

このガイドに接続されているデバイスは、および外部クラウドネットワーク経由でネットワークに接続します。 会社のリソースにアクセスするには、VPN 経由でデバイスを接続する必要が&#39;ます。 デバイスを VPN に接続する方法はいくつかあり、エンドユーザーがデバイス UI を使用して接続することも、デバイスを管理して、PPKG または MDM から VPN プロファイルを受け取ることもできます。 この記事では、VPN が&#39;使用されている&#39;t を設定する方法について説明します。そのため、さまざまな VPN プロトコルの詳細や VPN の管理方法については、次のガイドを参照してください[。 HoloLens と vpn に関する情報については、これらのガイド](https://docs.microsoft.com/hololens/hololens-network#vpn)を参照してください。

## <a name="next-step"></a>次のステップ

> [!div class="nextstepaction"]
> [クラウドに接続されたデプロイ-構成](hololens2-cloud-connected-configure.md)
