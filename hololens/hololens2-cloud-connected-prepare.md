---
title: デプロイ ガイド – クラウド接続HoloLens 2大規模なデプロイ - Remote Assist - 準備
description: Azure Active Directory と ID 管理を使用してHoloLensネットワークを使用してデバイスを登録する準備をする方法について説明します。
keywords: HoloLens、管理、クラウド接続、Remote Assist、AAD、Azure AD、MDM、Mobile デバイス管理
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
ms.openlocfilehash: 21fffdc24f8682bc44779e1cebe8cd6eacb59619
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639660"
---
# <a name="prepare---cloud-connected-guide"></a>準備 - クラウド接続ガイド

この記事の最後までに、AZURE AD アカウントとネットワーク要件の使用に関するAzure ADを設定します。 このガイドのこのセクションは、ユーザーと組織がクラウドにデプロイし、HoloLens 2を使用するための準備をDynamics 365 Remote Assist。 インフラストラクチャの各部分の重要性に加え、必要に応じてこれらの部分を設定するのに役立つガイドへのリンクが提供されます。

## <a name="infrastructure-essentials"></a>Infrastructure Essentials

個人と企業の両方の展開シナリオでは、MDM システムは、デバイスを展開および管理するために必要Windows 10 Holographicです。 Azure AD Premium サブスクリプションは、ID プロバイダーとして推奨され、特定の機能をサポートするために必要です。

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD は、ID とアクセス管理を提供する、クラウド ベースのディレクトリ サービスです。 Microsoft Office 365 または Intune を使用する組織では、3 つのエディション (Free、プレミアム P1、プレミアム P2) を持つ Azure AD を既に使用しています (「Azure Active Directory [editions](https://azure.microsoft.com/documentation/articles/active-directory-editions)」を参照)。すべてのエディションでデバイスAzure ADサポートされますが、このガイドプレミアム使用する MDM 自動登録を有効にするには、P1 を使用する必要があります。

> [!IMPORTANT]
> オンプレミスの AD 参加をAzure Active DirectoryデバイスHoloLens、この機能を使用する必要があります。 新しいテナント&#39;まだ設定していない場合Azure Active Directoryに新しいテナントを作成する[」にAzure Active Directory。](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)

## <a name="identity-management"></a>ID 管理

従業員は、デバイスを初期化するために 1 つのアカウントのみを使用&#39;、組織が最初に有効にするアカウントを制御する必要があります。 選択したアカウントによって、デバイスを制御するユーザーが決まり、管理機能に影響があります。

このガイドでは、使用する ID[](/hololens/hololens-identity)に対して、アカウントまたはアカウントAzure AD使用Azure Active Directoryしました。 使用するアカウントAzure ADにはいくつかの利点があります。次に例を示します。

- 従業員は、Azure AD アカウントを使用してデバイスを Azure AD に登録し、組織&#39;の MDM ソリューションに自動的に登録します (Azure AD + MDM – Azure AD Premium が必要)。
- Azure ADアカウントでは、シングル [サインオン がサポートされます](/azure/active-directory/manage-apps/what-is-single-sign-on)。 ユーザーが Remote Assist にサインインすると、サインインした Azure AD ユーザーの ID が認識され、ユーザーはアプリにサインインして、エクスペリエンスを効率化します。
- Azure ADアカウントには、Business 用[の Windows Hello](/hololens/hololens-identity)を[使用して追加の認証オプションがあります](/windows/security/identity-protection/hello-for-business/hello-identity-verification)。 Iris ログイン ユーザーに加えて、別のデバイスからサインインしたり、FIDO セキュリティ キーを使用したりすることもできます。

### <a name="mobile-device-management"></a>モバイル デバイス管理

Microsoft [Intune](/mem/intune/fundamentals/what-is-intune)は、テナントに接続Enterprise Mobility + Securityデバイスを管理するクラウドベースの MDM システムです。 たとえばOffice 365 Intune では ID 管理に Azure AD が使用されます。そのため、従業員は同じ資格情報を使用して、サインインに使用するデバイスを Intune に登録Office 365。 Intune では、完全な MDM ソリューションを提供するために、iOS や Android などの他のオペレーティング システムを実行するデバイスもサポートされています。 このガイドでは、&#39;を使用して大規模なクラウドデプロイを有効にするための Intune の使用に焦点を当HoloLens 2。

> [!IMPORTANT]
> Mobile デバイス管理。 まだ設定&#39;場合は、このガイドに従い [、Intune 概要を使用してください](/mem/intune/fundamentals/free-trial-sign-up)。

> [!NOTE]
> 複数の MDM システムが Windows 10 をサポートしており、ほとんどは、個人のデバイスおよび企業のデバイスの展開のシナリオをサポートしています。 現在、この機能をWindows 10 Holographic MDM プロバイダーには、AirWatch、MobileIron などが含まれます。 業界をリードする MDM ベンダーのほとんどは既に Azure AD との統合をサポートしています。 Azure AD をサポートする MDM ベンダーは [Azure Marketplace](https://azure.microsoft.com/marketplace/)で検索できます。

## <a name="network"></a>ネットワーク

このセットアップでは、使用可能なHoloLens 2ネットワークからインターネットに接続するデバイスがWi-Fiされます。 ユーザーは場所に基づいてネットワーク接続を変更する必要がある可能性があるから、ユーザーはデバイスを[Wi-Fi にHoloLensする方法を学習する必要があります。](/hololens/hololens-network)

たとえばDynamics 365 Remote Assist、帯域幅、待機時間、ジッター、パケット損失など、ビデオ通話エクスペリエンスに影響を与える可能性があるさまざまなネットワーク条件があります。 帯域幅が少ない環境ではオーディオとビデオの呼び出しが可能な場合でも、機能が低下する可能性があります。 デバイスで Dynamics 365 Remote AssistをHoloLens、次のネットワーク要件に注意してください。

**最小** : HD 1080p の解像度が 30 fps のピア ツー ピア HD 品質ビデオ通話には、1.5 Mbps のアップ/ダウンが必要です。

**最適:** HD 1080p の解像度でピア ツー ピア HD 品質のビデオ通話を行う場合は、4 ~ 5 Mbps のアップ/ダウンが必要です。

詳細情報:

- [ネットワーク要件](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [ネットワークの最適化に関する推奨事項](/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>省略可能: Connect VPN HoloLens接続する

このガイドに接続されているデバイスは、外部クラウド ネットワークを介してネットワークに接続します。 VPN 経由でデバイスを接続する必要&#39;会社のリソースにアクセスする場合があります。 エンド ユーザーがデバイス UI を使用して接続できる VPN にデバイスを接続する方法と、デバイスを管理して PPKG または MDM から VPN プロファイルを受信する方法の両方があります。 VPN を設定する方法については、この記事では説明&#39;説明しないので、さまざまな HoloLens VPN プロトコルや VPN の管理方法の詳細については、&#39;と[VPN](/hololens/hololens-network#vpn)の詳細については、これらのガイドを参照してください。

## <a name="next-step"></a>次のステップ

> [!div class="nextstepaction"]
> [クラウドに接続されたデプロイ - 構成](hololens2-cloud-connected-configure.md)
