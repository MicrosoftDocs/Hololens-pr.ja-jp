---
title: デプロイ ガイド – 企業接続HoloLens 2 Dynamics 365 Guides - 準備
description: デバイスを使用して企業接続ネットワークHoloLens 2デバイスを登録する準備をする方法についてDynamics 365 Guides。
keywords: HoloLens、管理、企業接続、Dynamics 365 Guides、AAD、Azure AD、MDM、Mobile デバイス管理
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
ms.openlocfilehash: 88e7d0614cf95f32eaa0434724eddbcb5b8cf863
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636981"
---
# <a name="prepare---corporate-connected-guide"></a>準備 - 企業接続ガイド
## <a name="infrastructure-essentials"></a>Infrastructure Essentials
個人と企業の両方の展開シナリオでは、モバイル デバイス管理 (MDM) システムは、Windows 10 デバイス (特に HoloLens 2) の展開と管理に必要なインフラストラクチャです。 サブスクリプション[Azure AD Premium ID](/azure/active-directory/fundamentals/active-directory-get-started-premium)プロバイダーとして推奨され、特定の機能をサポートするために必要です。

> [!NOTE]
> デバイスHoloLens 2モバイル デバイスのように展開および管理しますが、通常は多くのユーザー間で共有デバイスとして使用されます。

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD は、ID とアクセス管理を提供する、クラウド ベースのディレクトリ サービスです。 Microsoft Office 365 または Intune を使用する組織では、3 つのエディション (Free、プレミアム P1、プレミアム P2) を持つ Azure AD を既に使用しています (「Azure Active Directory [editions 」を参照](https://azure.microsoft.com/documentation/articles/active-directory-editions)してください)。 すべてのエディションでデバイスAzure ADサポートされますが、このガイドプレミアム使用する MDM 自動登録を有効にするには、P1 を使用する必要があります。
> [!Important]
> オンプレミスの AD 参加をAzure ADデバイスHoloLensをサポートしていないので、この機能を使用する必要があります。 新しいテナントをまだ設定していない場合Azure AD手順に従って開始し、 で新しいテナントを作成[Azure Active Directory。](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)

## <a name="identity-management"></a>ID 管理
このガイドでは、使用 [される ID](/hololens/hololens-identity) がAzure ADされます。 次のような複数のアカウントAzure AD利点があります。

- 従業員は Azure AD アカウントを使用して Azure AD にデバイスを登録し、組織の MDM ソリューション (Azure AD + MDM – Azure AD Premium サブスクリプションが必要) にデバイス[を自動的に登録できます](/azure/active-directory/fundamentals/active-directory-get-started-premium)。
- Azure ADアカウントには、Business 用[の Windows Hello](/hololens/hololens-identity)を[使用して追加の認証オプションがあります](/windows/security/identity-protection/hello-for-business/hello-identity-verification)。 Iris ログインに加えて、ユーザーは別のデバイスからサインインするか、FIDO セキュリティ キーを使用できます。

> [!WARNING] 
> 従業員は 1 つのアカウントのみを使用してデバイスを初期化できます。そのため、組織で最初に有効になっている **アカウントを制御する必要があります**。 選択したアカウントによって、デバイスを制御するユーザーが決まり、管理機能に影響があります。

## <a name="mobile-device-management"></a>モバイル デバイス管理
Microsoft Intuneの一Enterprise Mobility + Securityは、テナントに接続されているデバイスを管理するクラウドベースの MDM システムです。 たとえばOffice 365 Intune では ID 管理に Azure AD が使用されます。そのため、従業員は同じ資格情報を使用して、サインインに使用するデバイスを Intune に登録Office 365。 Intune では、完全な MDM ソリューションを提供するために、iOS や Android などの他のオペレーティング システムを実行するデバイスもサポートされています。 このガイドでは、Intune を使用して、内部ネットワークへのデプロイを有効にする方法に焦点を当てHoloLens 2。
> [!Important] 
> Mobile デバイス管理。 まだ設定していない場合は、このガイドに従って Intune を使用概要してください。

> [!Important]
> Guides を使用するには、Azure ADアカウントが必要です。

> [!Note] 
> 複数の MDM システムが Windows 10 をサポートしており、ほとんどは、個人のデバイスおよび企業のデバイスの展開のシナリオをサポートしています。 この機能をサポートする MDM Windows 10 Holographic、AirWatch、MobileIron などです。 業界をリードする MDM ベンダーのほとんどは既に Azure AD との統合をサポートしています。 この機能をサポートする MDM ベンダーの最新の一覧は、 Azure ADで[Azure Marketplace。](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps)

## <a name="network-access"></a>ネットワーク アクセス 
Dynamics 365 Guidesはクラウドベースのアプリケーションです。 ネットワーク管理者が承認リストを持っている場合は、Dynamics 365 サーバーへの接続に必要な IP アドレスやエンドポイントの追加が必要になる場合があります。 [IP アドレスと URL のブロック解除の詳細については、を参照してください](/power-platform/admin/online-requirements#ip-addresses-and-urls)。

## <a name="certificates"></a>証明書
証明書は、Web コンテンツのアカウント認証、Wi-Fi、VPN 暗号化、SSL 暗号化を提供することで、セキュリティを向上させるのに役立ちます。 管理者はプロビジョニング パッケージを使用してデバイス上の証明書を手動で管理することができますが、MDM システムを使用して、登録から更新、失効まで、ライフサイクル全体を通してそれらの証明書を管理するベスト プラクティスです。 

MDM システムでは、登録後にこれらの証明書をデバイスの証明書ストアに自動的に展開できます (MDM システムが Simple Certificate Enrollment Protocol **(SCEP)** または公開キー暗号化標準 **#12 (PKCS #12)** をサポートしている限り)。 [で使用する証明書の種類とプロファイルについてMicrosoft Intune。](/mem/intune/protect/certificates-configure) MDM では、登録されたクライアント証明書の照会と削除、または現在の証明書の有効期限が切る前に新しい登録要求をトリガーすることもできます。

MDM システムが既に証明書用に構成されている場合は、「HoloLens 2 用の証明書とネットワーク プロファイルを準備する」を参照して[、HoloLens 2](/hololens/hololens-certificates-network)デバイスの証明書とプロファイルの展開を開始してください。

## <a name="scep"></a>SCEP

SCEP 展開には次のサービスが必要ですが、Web アプリケーション プロキシ Server を除く。

- [証明機関](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [NDES サーバーの役割](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intune コネクタ](/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

また、アプリケーション プロキシまたはプロキシを使用して、企業ネットワークの外部Azure AD NDES URL [をWeb アクセスがあります](/azure/active-directory/manage-apps/application-proxy-add-on-premises-application)。 また、選択した別のリバース プロキシを使用することもできます。

![SCEP データ フロー](./images/hololens2-scep-info-flow.png)

ネットワークで SCEP がまだサポートされていない場合、またはネットワークが Intune で SCEP 用に正しく設定されているのか不明な場合は、「Intune で  [SCEP](/mem/intune/protect/certificates-scep-configure)をサポートするようにインフラストラクチャを構成する」を参照してください。

インフラストラクチャで既に SCEP がサポートされている場合[](/mem/intune/protect/certificates-profile-scep)は、SCEP 証明書ごとにプロファイルを作成する必要があります。このプロファイルHoloLens 2必要があります。 [](/mem/configmgr/protect/deploy-use/create-certificate-profiles) SCEP で問題が発生した場合は、SCEP 証明書プロファイルの使用に関するトラブルシューティングを使用して、 を使用して証明書[をプロビジョニングMicrosoft Intune。](/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)

## <a name="pkcs"></a>PKCS
Intune では、公開キーと公開キーのペア (PKCS) 証明書の使用もサポートされています。 詳細[については、「プライベート キー証明書と公開キー証明書を使用する」Microsoft Intune](/mem/intune/protect/certificates-pfx-configure)を参照してください。

## <a name="proxy"></a>Proxy (プロキシ)
ほとんどの企業イントラネット ネットワークでは、プロキシを利用して外部トラフィックを管理します。 このHoloLens 2、イーサネット、接続、VPN 接続用にプロキシ Wi-Fi構成できます。

プロキシには、いくつかの異なる種類のプロキシと、プロキシを構成する方法があります。 このガイドでは **、Wi-Fi** プロキシを選択し、PAC URL を使用して設定し、MDM を介してデプロイすることを選択します。 これには、MDM を介して自動的に展開され、server:port 構成を使用する代わりに PAC ファイルを更新でき、最後に Wi-Fi プロキシを使用して 1 つの Wi-Fi 接続にのみ適用されるプロキシを構成し、別の場所に接続されている場合でもデバイスを引き続き使用できるという利点があります。

Windows 10 のプロキシ設定の詳細については、「Windows 10 でデバイス用の Wi-Fi プロファイルを作成する[- Azure Microsoft Intune」](/mem/intune/configuration/wi-fi-settings-configure)を参照してください。

## <a name="line-of-business-apps"></a>Line of Business Apps 
複数のアプリを Microsoft Store 経由でインストールすることもできますが、Mixed Reality で使用するために作成した独自のカスタム アプリがある可能性があります。 ビジネスのために組織全体に配布されるこれらのカスタム アプリは、Line of Business (LOB) アプリと呼ばれるものになります。
  
アプリケーションをデバイスに展開するには、複数HoloLens 2があります。 アプリは、MDM、ビジネス向け Microsoft Store (MSfB)、またはプロビジョニング パッケージを介してサイドロードを介して直接デプロイできます。 このガイドでは、必要なアプリのインストールを使用して、MDM 経由でアプリをデプロイします。 これにより、登録が完了すると、LOB アプリが HoloLensデバイスに自動的にダウンロードされます。

独自の LOB をお持ちではない方のために、このデプロイ フローをテストするサンプル アプリを提供します。 このアプリは [MRTK Examples](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) アプリであり、概念実証をテストするために既に構築およびパッケージ化されています。

アプリのデプロイの詳細については、「App [Management: Overview 」を参照してください](/hololens/app-deploy-overview)。

> [!NOTE]
> HoloLens 2は、UWP ARM64 アプリの実行のみをサポートしています。

## <a name="guides-playbook"></a>ガイドプレイブック
ガイドでは、ガイド アプリのデータストアとして Microsoft Dataverse 環境を使用します。 Dataverse 環境が Guides アプリやテナントとどのように対話するのかの大きな画像を理解することが重要です。 このガイドではデータバースを管理する方法については説明しますが[、Dynamics 365 Guides - Dynamics 365](/dynamics365/mixed-reality/guides/admin-deployment-playbook)Mixed Reality をデプロイするための基本的な概念を確認してください。

## <a name="next-step"></a>次のステップ 
> [!div class="nextstepaction"]
> [企業に接続されたデプロイ - 構成](hololens2-corp-connected-configure.md)