---
title: デプロイ ガイド – クラウド接続HoloLens 2大規模なデプロイ - Remote Assist - 準備
description: Azure Active Directory と ID 管理を使用して、クラウド接続ネットワークを使用して HoloLens デバイスを登録する準備をする方法について説明します。
keywords: HoloLens, 管理, クラウド接続, Remote Assist, AAD, Azure AD, MDM, モバイル デバイス管理
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
ms.openlocfilehash: 21132ed5d1e84d92a877747ac9a4c090b177ca08
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924572"
---
# <a name="prepare---cloud-connected-guide"></a>準備 - クラウド接続ガイド

この記事の最後までに、AZURE AD アカウントとネットワーク要件の使用に関するAzure ADを設定します。 このガイドのこのセクションは、ユーザーと組織がクラウドにデプロイし、HoloLens 2を使用する準備をするのにDynamics 365 Remote Assist。 インフラストラクチャの各部分の重要性に加え、必要に応じてこれらの部分を設定するのに役立つガイドへのリンクが提供されます。

## <a name="infrastructure-essentials"></a>Infrastructure Essentials

個人と企業の両方の展開シナリオでは、MDM システムは、デバイスを展開および管理するために必要Windows 10 Holographicです。 Azure AD Premium サブスクリプションは、ID プロバイダーとして推奨され、特定の機能をサポートするために必要です。

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD は、ID とアクセス管理を提供する、クラウド ベースのディレクトリ サービスです。 Microsoft Office 365 または Intune を使用する組織は、Free、Premium P1、Premium P2 の 3 つのエディションを持つ Azure AD を既に使用しています (Azure Active Directory エディション [を](https://azure.microsoft.com/documentation/articles/active-directory-editions)参照)。すべてのエディションでデバイスAzure ADがサポートされますが、後でこのガイドで使用する MDM 自動登録を有効にするには Premium P1 が必要です。

> [!IMPORTANT]
> HoloLens デバイスはオンプレミスの AD 参加Azure Active Directoryサポートしていないので、この機能を使用する必要があります。 新しいテナント&#39;まだ設定していない場合Azure Active Directoryに新しいテナントを作成する[」にAzure Active Directory。](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)

## <a name="identity-management"></a>ID 管理

従業員は、デバイスを初期化するために 1 つのアカウントのみを使用&#39;、組織が最初に有効にするアカウントを制御する必要があります。 選択したアカウントによって、デバイスを制御するユーザーが決まり、管理機能に影響があります。

このガイドでは、使用する ID[](https://docs.microsoft.com/hololens/hololens-identity)に対して、アカウントまたはアカウントAzure AD使用Azure Active Directoryしました。 使用するアカウントAzure ADにはいくつかの利点があります。次に例を示します。

- 従業員は、Azure AD アカウントを使用して Azure AD にデバイスを登録し、組織&#39;の MDM ソリューションに自動的に登録します (Azure AD + MDM – Azure AD Premium)。
- Azure ADアカウントでは、シングル [サインオン がサポートされます](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on)。 ユーザーが Remote Assist にサインインすると、サインインした Azure AD ユーザーの ID が認識され、ユーザーはアプリにサインインして、エクスペリエンスを効率化します。
- Azure ADアカウントには、 を[使用して追加の認証オプション](https://docs.microsoft.com/hololens/hololens-identity)[Windows Hello for Business。](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) Iris ログイン ユーザーに加えて、別のデバイスからサインインしたり、FIDO セキュリティ キーを使用したりすることもできます。

### <a name="mobile-device-management"></a>モバイル デバイス管理

Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)は、テナントEnterprise Mobility + Securityデバイスを管理するクラウドベースの MDM システムです。 Office 365 と同様に、Intune では ID 管理に Azure AD が使用されます。そのため、従業員は Office 365 へのサインインに使用するデバイスを Intune に登録するために同じ資格情報を使用します。 Intune では、完全な MDM ソリューションを提供するために、iOS や Android などの他のオペレーティング システムを実行するデバイスもサポートされています。 このガイドでは、&#39;を使用して大規模なクラウドデプロイを有効にするための Intune の使用に焦点を当HoloLens 2。

> [!IMPORTANT]
> Mobile デバイス管理。 まだ設定&#39;場合は、このガイドに従い [、Intune 概要を使用してください](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)。

> [!NOTE]
> 複数の MDM システムが Windows 10 をサポートしており、ほとんどは、個人のデバイスおよび企業のデバイスの展開のシナリオをサポートしています。 現在、この機能をWindows 10 Holographic MDM プロバイダーには、AirWatch、MobileIron などが含まれます。 業界をリードする MDM ベンダーのほとんどは既に Azure AD との統合をサポートしています。 Azure AD をサポートする MDM ベンダーは [Azure Marketplace](https://azure.microsoft.com/marketplace/)で検索できます。

## <a name="network"></a>ネットワーク

このセットアップでは、使用可能なHoloLens 2ネットワークからインターネットに接続するデバイスがWi-Fiされます。 ユーザーは場所に基づいてネットワーク接続を変更する必要がある可能性があるから、HoloLens デバイスを Wi-Fi に接続する方法を [学習する必要があります。](https://docs.microsoft.com/hololens/hololens-network)

たとえばDynamics 365 Remote Assist、帯域幅、待機時間、ジッター、パケット損失など、ビデオ通話エクスペリエンスに影響を与える可能性があるさまざまなネットワーク条件があります。 帯域幅が少ない環境ではオーディオとビデオの呼び出しが可能な場合でも、機能が低下する可能性があります。 HoloLens Dynamics 365 Remote Assistを使用する場合は、次のネットワーク要件に注意してください。

**最小** : HD 1080p の解像度が 30 fps のピア ツー ピア HD 品質ビデオ通話には、1.5 Mbps のアップ/ダウンが必要です。

**最適:** HD 1080p の解像度でピア ツー ピア HD 品質のビデオ通話を行う場合は、4 ~ 5 Mbps のアップ/ダウンが必要です。

詳細情報:

- [ネットワークの要件](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [ネットワークの最適化に関する推奨事項](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>省略可能: HoloLens を VPN に接続する

このガイドに接続されているデバイスは、外部クラウド ネットワークを介してネットワークに接続します。 VPN 経由でデバイスを接続する必要&#39;会社のリソースにアクセスする場合があります。 エンド ユーザーがデバイス UI を使用して接続できる VPN にデバイスを接続する方法と、デバイスを管理して PPKG または MDM から VPN プロファイルを受信する方法の両方があります。 VPN を設定する方法については、この記事では説明&#39;&#39;説明しないので、さまざまな VPN プロトコルや VPN の管理方法の詳細については[、HoloLens](https://docs.microsoft.com/hololens/hololens-network#vpn)と VPN に関するページを参照してください。

## <a name="next-step"></a>次のステップ

> [!div class="nextstepaction"]
> [クラウドに接続されたデプロイ - 構成](hololens2-cloud-connected-configure.md)
