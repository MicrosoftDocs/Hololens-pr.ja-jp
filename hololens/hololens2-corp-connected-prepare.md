---
title: 展開ガイド – Dynamics 365 ガイドを使用した企業接続 HoloLens 2 - 準備
description: Dynamics 365 ガイドを使用して企業の接続ネットワークを使用して HoloLens 2 デバイスを登録する準備をする方法について学習します。
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
ms.openlocfilehash: 2ab24aeac371b8d4a17d6121c3adf317cac7daf1
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448583"
---
# <a name="prepare---corporate-connected-guide"></a>準備 - 企業向けコネクテッド ガイド
## <a name="infrastructure-essentials"></a>インフラストラクチャの重要な要素
個人と企業の両方の展開シナリオでは、モバイル デバイス管理 (MDM) システムは、Windows 10 デバイス 、特に HoloLens 2 を展開および管理するために必要な不可欠なインフラストラクチャです。 [Azure AD Premium サブスクリプションは](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium)ID プロバイダーとして推奨され、特定の機能をサポートするために必要です。 ****

> [!NOTE]
> HoloLens 2 はモバイル デバイスと同様に展開および管理されますが、通常は多くのユーザー間で共有デバイスとして使用されます。

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD は、ID とアクセス管理を提供する、クラウド ベースのディレクトリ サービスです。 Microsoft Office 365 または Intune を使用する組織は、既に Azure AD を使用しています。このエディションには、Free、Premium P1、Premium P2 の 3 つのエディションがあります [(「Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions)エディション」を参照)。 すべてのエディションで Azure ADデバイス登録がサポートされますが、後でこのガイドで使用する MDM 自動登録を有効にするには、Premium P1 が必要です。
> [!Important]
> HoloLens デバイスがオンプレミスのAD参加をサポートしていないので、Azure サーバーをADです。 Azure サーバーをまだセットアップしていないAD手順に従って、Azure Active Directory で新しいテナントを [作成します](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)。

## <a name="identity-management"></a>ID 管理
このガイドでは、 [使用される ID](https://docs.microsoft.com/hololens/hololens-identity) は Azure ADされます。 Azure アカウントには、次のようなAD利点があります。
- 従業員は Azure AD アカウントを使用して Azure AD にデバイスを登録し、組織の MDM ソリューション (Azure AD+MDM - Azure AD Premium サブスクリプションが必要) に自動的 [に登録できます](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium)。
- Azure ADアカウントには、Windows Hello for Business[経由](https://docs.microsoft.com/hololens/hololens-identity)[で追加の認証オプションがあります](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)。 Iris ログインに加えて、ユーザーは別のデバイスからサインインするか、FIDO セキュリティ キーを使用できます。

> [!WARNING] 
> 従業員は 1 つのアカウントのみを使用してデバイスを初期化できます。そのため、組織が最初に有効にするアカウント **を制御する必要があります**。 選択したアカウントによって、デバイスを制御するユーザーが決まり、管理機能に影響があります。

## <a name="mobile-device-management"></a>モバイル デバイス管理
エンタープライズ モビリティ + セキュリティの一部である Microsoft Intune は、テナントに接続されているデバイスを管理するクラウドベースの MDM システムです。 Intune Office 365 と同様に、Intune は Azure AD を ID 管理に使用します。そのため、従業員は同じ資格情報を使用して、365 へのサインインに使用するデバイスを Intune に登録Officeします。 Intune は、完全な MDM ソリューションを提供するために、iOS や Android などの他のオペレーティング システムを実行するデバイスもサポートしています。 このガイドでは、HoloLens 2 を使用して内部ネットワークへの展開を有効にするための Intune の使用に重点を置きます。
> [!Important] 
> モバイル デバイスの管理を行う必要があります。 まだセットアップしていない場合は、このガイドと Intune の使用を開始してください。

> [!Important]
> ガイドを使用するには、Azure ADが必要です。

> [!Note] 
> 複数の MDM システムが Windows 10 をサポートしており、ほとんどは、個人のデバイスおよび企業のデバイスの展開のシナリオをサポートしています。 Windows 10 Holographic をサポートする MDM プロバイダーには、AirWatch、MobileIron、その他が含まれます。 業界をリードする MDM ベンダーのほとんどは既に Azure AD との統合をサポートしています。 Azure Marketplace をサポートする MDM ベンダーの最新の一覧AD [確認できます](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps)。

## <a name="network-access"></a>ネットワーク アクセス 
Dynamics 365 Guides はクラウドベースのアプリケーションです。 ネットワーク管理者が承認リストを持っている場合、Dynamics 365 サーバーへの接続に必要な IP アドレスやエンドポイントを追加する必要がある場合があります。 [IP アドレスと URL のブロック解除について詳しくは、次のページをご覧ください](https://docs.microsoft.com/power-platform/admin/online-requirements#ip-addresses-and-urls)。

## <a name="certificates"></a>証明書
証明書は、Web コンテンツのアカウント認証、Wi-Fi VPN 暗号化、SSL 暗号化を提供することで、セキュリティを向上させるのに役立ちます。 管理者はプロビジョニング パッケージを使用してデバイス上の証明書を手動で管理することができますが、MDM システムを使用して、登録から更新、失効まで、ライフサイクル全体にわたってそれらの証明書を管理するベスト プラクティスです。 

MDM システムは、登録後にこれらの証明書をデバイスの証明書ストアに自動的に展開できます (MDM システムが簡易証明書登録プロトコル **(SCEP)** または公開キー暗号化標準 #12 **(PKCS#12)** をサポートしている限り)。 [Microsoft Intune で使用する証明書の種類とプロファイルについて説明します](https://docs.microsoft.com/mem/intune/protect/certificates-configure)。 MDM は、現在の証明書の有効期限が切れている前に、登録済みクライアント証明書を照会および削除したり、新しい登録要求をトリガーしたりすることもできます。
 
MDM システムが既に証明書用に構成されている場合は [、「Prepare certificates and network profiles for HoloLens 2」を参照して、HoloLens 2](https://docs.microsoft.com/hololens/hololens-certificates-network) デバイスの証明書とプロファイルの展開を開始します。

## <a name="scep"></a>SCEP

WEB アプリケーション プロキシ サーバーを除き、SCEP 展開には次のサービスが必要です。
- [証明機関](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [NDES Server の役割](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intune コネクタ](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

また、Azure アプリケーション プロキシまたは Web アクセス プロキシを使用して、企業ネットワークAD NDES URL を [公開する必要があります](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-add-on-premises-application)。 また、選択した別のリバース プロキシを使用できます。

![SCEP データ フロー](./images/hololens2-scep-info-flow.png)

ネットワークが SCEP をまだサポートしていない場合、またはネットワークが Intune を使用して SCEP 用に正しくセットアップされている場合は、「Intune で  [SCEP](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure)をサポートするようにインフラストラクチャを構成する」を参照してください。

インフラストラクチャが既に SCEP をサポートしている場合[](https://docs.microsoft.com/mem/intune/protect/certificates-profile-scep)は、HoloLens 2 が使用する SCEP 証明書ごとにプロファイルを作成する必要があります。 [](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-certificate-profiles) SCEP に問題がある場合は、[SCEP 証明書プロファイルの使用のトラブルシューティング] を使用して、Microsoft Intune で証明書 [をプロビジョニングします](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)。

## <a name="pkcs"></a>PKCS
Intune では、プライベートキーと公開キーのペア (PKCS) 証明書の使用もサポートされています。 リファレンス [詳細については、Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/certificates-pfx-configure) でプライベートキー証明書と公開キー証明書を使用します。

## <a name="proxy"></a>プロキシ
ほとんどの企業イントラネット ネットワークでは、プロキシを使用して外部トラフィックを管理します。 HoloLens 2 を使用すると、イーサネット接続、ネットワーク接続、VPN 接続用のWi-Fi構成できます。

プロキシには、いくつかの異なる種類のプロキシと、プロキシを構成する方法があります。 このガイドでは **、Wi-Fi**プロキシを選択し、PAC URL 経由で設定し、MDM 経由で展開することを選択します。 これは、MDM を介して自動的に展開され、サーバー:ポート構成を使用する代わりに PAC ファイルを更新でき、最後に Wi-Fi プロキシを使用して 1 つの Wi-Fi 接続にのみ適用されるプロキシを構成し、別の場所に接続されている場合でもデバイスを使用できるという利点があります。 


Windows 10 のプロキシ設定の詳細については、「Microsoft Intune - Azure でデバイスWi-Fiプロファイルを作成する」 [を参照してください](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure)。

## <a name="line-of-business-apps"></a>Line of Business Apps 
Microsoft Store を介して複数のアプリをインストールすることもできますが、複合現実で使用するために特別に作成した独自のカスタム アプリがある可能性があります。 ビジネス用に組織全体に配布されるこれらのカスタム アプリは、Line of Business (LOB) アプリと呼ばれる。
  
HoloLens 2 デバイスにアプリケーションを展開する方法は複数あります。 アプリは、MDM、Microsoft Store for Business(MSfB)を介して直接展開するか、プロビジョニング パッケージを介してサイドロードできます。 このガイドのために、必要なアプリインストールを使用して、MDM 経由でアプリを展開します。 これにより、登録が完了すると、LOB アプリが HoloLens デバイスに自動的にダウンロードされます。

独自の LOB を持ってないユーザーのために、この展開フローをテストするサンプル アプリを提供します。 このアプリは [MRTK Examples](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) アプリであり、概念実証をテストするために既に構築され、パッケージ化されています。
 
アプリの展開に関する詳細については、「アプリの管理: [概要」を参照してください](https://docs.microsoft.com/hololens/app-deploy-overview)。

> [!NOTE]
> HoloLens 2 では、UWP ARM64 アプリの実行のみをサポートしています。

## <a name="guides-playbook"></a>ガイドプレイブック
ガイドでは、ガイド アプリのデータストアとして Microsoft Dataverse 環境を使用します。 Dataverse 環境がガイド アプリやテナントとどのようにやり取りを行うのか、より大きな画像を理解することが重要です。 このガイドでは、データバースを管理する方法については説明しますが [、Dynamics 365 Guides - Dynamics 365 Mixed Reality](https://docs.microsoft.com/dynamics365/mixed-reality/guides/admin-deployment-playbook)を展開するための基本的な概念を確認してください。

## <a name="next-step"></a>次の手順 
> [!div class="nextstepaction"]
> [企業接続展開 - 構成](hololens2-corp-connected-configure.md)