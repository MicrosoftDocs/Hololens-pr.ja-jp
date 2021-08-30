---
title: 展開ガイド– Dynamics 365 Guides による企業接続 HoloLens 2
description: Dynamics 365 Guides を使用して、企業に接続されたネットワーク経由で HoloLens 2 デバイスを登録する準備をする方法について説明します。
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
ms.openlocfilehash: 5d8fc2eb0a8dafaae0e1b222b7451877975cf90b
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190210"
---
# <a name="prepare---corporate-connected-guide"></a>準備-企業接続ガイド
## <a name="infrastructure-essentials"></a>インフラストラクチャの要点
個人と企業の両方の展開シナリオで、モバイルデバイス管理 (MDM) システムは、Windows 10 デバイス、特に HoloLens 2 を展開および管理するために必要不可欠なインフラストラクチャです。 [Azure AD Premium サブスクリプション](/azure/active-directory/fundamentals/active-directory-get-started-premium)は、id プロバイダーとして推奨され、特定の機能をサポートするために **必要** です。

> [!NOTE]
> HoloLens 2 はモバイルデバイスと同様に展開および管理されますが、通常、多くのユーザー間で共有デバイスとして使用されます。

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD は、ID とアクセス管理を提供する、クラウド ベースのディレクトリ サービスです。 Microsoft Office 365 または Intune を使用している組織は、既に Azure AD を使用しています。これには、無料、プレミアム P1、プレミアム P2 の3つのエディションがあります (「 [Azure Active Directory エディション](https://azure.microsoft.com/documentation/articles/active-directory-editions)」を参照してください)。 すべてのエディションでデバイス登録 Azure AD サポートされますが、後でこのガイドで使用する MDM 自動登録を有効にするにはプレミアム P1 が必要です。
> [!Important]
> HoloLens デバイスではオンプレミスの AD join がサポートされていないため、Azure AD を用意することが不可欠です。 まだ Azure AD がセットアップされていない場合は、「はじめに」の手順に従って[Azure Active Directory で新しいテナントを作成](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)します。

## <a name="identity-management"></a>ID 管理
このガイドでは、使用される [id](/hololens/hololens-identity) は Azure AD アカウントになります。 Azure AD アカウントには、次のようないくつかの利点があります。

- 従業員は Azure AD アカウントを使用して Azure AD にデバイスを登録し、組織の mdm ソリューションに自動的に登録することができます (Azure AD + mdm – [Azure AD Premium サブスクリプション](/azure/active-directory/fundamentals/active-directory-get-started-premium)が必要です)。
- Azure AD アカウント[には、Windows Hello for Business を](/windows/security/identity-protection/hello-for-business/hello-identity-verification)使用した追加の[認証オプション](/hololens/hololens-identity)があります。 虹彩ログインに加えて、ユーザーは別のデバイスからサインインすることも、FIDO セキュリティキーを使用することもできます。

> [!WARNING] 
> 従業員は1つのアカウントのみを使用してデバイスを初期化できるため、 **最初に有効にするアカウントを組織が制御する必要** があります。 選択したアカウントによって、デバイスを制御するユーザーが決まり、管理機能に影響があります。

## <a name="mobile-device-management"></a>モバイル デバイス管理
Enterprise Mobility + Security の一部である Microsoft Intune は、テナントに接続されているデバイスを管理するクラウドベースの MDM システムです。 Office 365 と同様に、intune は id 管理に Azure AD を使用するので、従業員は Office 365 にサインインするために使用するデバイスを intune に登録するために同じ資格情報を使用します。 Intune は、iOS や Android などの他のオペレーティングシステムを実行するデバイスもサポートして、完全な MDM ソリューションを提供します。 このガイドでは、Intune を使用して HoloLens 2 で内部ネットワークへのデプロイを有効にする方法について説明します。
> [!Important] 
> モバイルデバイス管理が不可欠です。 まだセットアップしていない場合は、このガイドに従って、Intune を使ってみてください。

> [!Important]
> ガイドを使用するには、Azure AD アカウントが必要です。

> [!Note] 
> 複数の MDM システムが Windows 10 をサポートしており、ほとんどは、個人のデバイスおよび企業のデバイスの展開のシナリオをサポートしています。 Windows 10 Holographic をサポートする MDM プロバイダーには、放映 watch、mobileiron などがあります。 業界をリードする MDM ベンダーのほとんどは既に Azure AD との統合をサポートしています。 [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps)で Azure AD をサポートする MDM ベンダーの最新の一覧を確認できます。

## <a name="network-access"></a>ネットワーク アクセス 
Dynamics 365 Guides は、クラウドベースのアプリケーションです。 ネットワーク管理者が承認リストを持っている場合は、Dynamics 365 サーバーへの接続に必要な IP アドレスやエンドポイントを追加することが必要になる場合があります。 [IP アドレスと url のブロックを解除する方法の詳細については、こちらをご覧](/power-platform/admin/online-requirements#ip-addresses-and-urls)ください。

## <a name="certificates"></a>証明書
証明書は、アカウント認証、Wi-Fi 認証、VPN 暗号化、web コンテンツの SSL 暗号化を提供することで、セキュリティを強化するのに役立ちます。 管理者はパッケージをプロビジョニングすることによってデバイスの証明書を手動で管理できますが、ベストプラクティスとして、MDM システムを使用して、証明書をライフサイクル全体にわたって管理することをお勧めします。これは、更新と失効による登録からです。 

Mdm システムでは、登録後に、デバイスの証明書ストアにこれらの証明書を自動的に展開できます (MDM システムが **Simple Certificate Enrollment Protocol (SCEP)** または **公開キー暗号化標準 #12 (PKCS # 12)**) をサポートしている必要があります。 [Microsoft Intune で使用する証明書の種類とプロファイルについて説明](/mem/intune/protect/certificates-configure)します。 また、MDM では、登録されているクライアント証明書を照会して削除したり、現在の証明書の有効期限が切れる前に新しい登録要求をトリガーしたりできます。

MDM システムが既に証明書用に構成されている場合は、「 [HoloLens 2 の証明書とネットワークプロファイルを準備](/hololens/hololens-certificates-network)する」を参照して、HoloLens 2 デバイスの証明書とプロファイルの展開を開始します。

## <a name="scep"></a>SCEP

SCEP の展開には、Web アプリケーションプロキシサーバーを除き、次のサービスが必要です。

- [証明機関](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [NDES サーバーの役割](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intuneケーブル](/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

また、 [Azure AD アプリケーションプロキシまたは Web アクセスプロキシ](/azure/active-directory/manage-apps/application-proxy-add-on-premises-application)を使用して、企業ネットワークの外部に NDES URL を発行する必要があります。 また、選択した別のリバース プロキシを使用することもできます。

![SCEP データフロー。](./images/hololens2-scep-info-flow.png)

ネットワークで SCEP がまだサポートされていない場合、またはネットワークが Intune で SCEP 用に正しく設定されているかどうかわからない場合は、「  [intune で scep をサポートするようにインフラストラクチャを構成する](/mem/intune/protect/certificates-scep-configure)」を参照してください。

インフラストラクチャで既に scep がサポートされている場合は、HoloLens 2 が使用する scep 証明書ごとに[プロファイル](/mem/configmgr/protect/deploy-use/create-certificate-profiles)を[作成](/mem/intune/protect/certificates-profile-scep)する必要があります。 SCEP に関する問題が発生した場合は、「 [scep 証明書プロファイルの使用に関するトラブルシューティング」を使用して、Microsoft Intune で証明書をプロビジョニング](/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)します。

## <a name="pkcs"></a>PKCS
Intune では、プライベートキーと公開キーのペア (PKCS) 証明書の使用もサポートされています。 リファレンス詳細については[、Microsoft Intune のプライベートキーと公開キーの証明書を](/mem/intune/protect/certificates-pfx-configure)参照してください。

## <a name="proxy"></a>プロキシ
ほとんどの企業イントラネットネットワークでは、プロキシを利用して外部トラフィックを管理します。 HoloLens 2 では、イーサネット、Wi-Fi、VPN 接続用のプロキシサーバーを構成できます。

プロキシの構成方法には、いくつかの種類があります。 このガイドでは、 **wi-fi プロキシを選択し、PAC URL を使用して設定し、MDM 経由でデプロイ** します。 これには、MDM によって自動的に展開されるという利点があります。サーバーのポート構成を使用する代わりに PAC ファイルを更新し、最後に Wi-Fi プロキシを使用して、別の場所に接続されている場合でもデバイスを使用できるようにするために1つの Wi-Fi 接続にのみ適用されるようにプロキシを構成

Windows 10 のプロキシ設定の詳細については、「 [Microsoft Intune-Azure でデバイスの Wi-Fi プロファイルを作成する](/mem/intune/configuration/wi-fi-settings-configure)」を参照してください。

## <a name="line-of-business-apps"></a>基幹業務アプリ 
Microsoft Store を使用して複数のアプリをインストールできますが、独自に作成した独自のカスタムアプリを使用して、特に mixed reality で使用することができます。 ビジネスのために組織全体に配布されるこれらのカスタムアプリは、基幹業務 (LOB) アプリと呼ばれます。
  
HoloLens 2 デバイスにアプリケーションを展開する方法は複数あります。 アプリは、MDM、ビジネス向け Microsoft Store (msfb)、またはプロビジョニングパッケージを介してサイドロードを使用して直接展開できます。 このガイドでは、必要なアプリのインストールを使用して、MDM 経由でアプリをデプロイします。 これにより、登録が完了したら、LOB アプリを HoloLens デバイスに自動的にダウンロードできます。

独自の LOB を持っていないユーザーのために、このデプロイフローをテストするサンプルアプリを提供します。 このアプリは [Mrtk サンプル](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) アプリになります。また、概念実証のためにあらかじめ構築され、パッケージ化されています。

アプリの展開に関する詳細については、 [「アプリ管理: 概要」](/hololens/app-deploy-overview)を参照してください。

> [!NOTE]
> HoloLens 2 は、UWP ARM64 アプリの実行のみをサポートしています。

## <a name="guides-playbook"></a>ガイドプレイブック
ガイドでは、ガイドアプリのデータストアとして Microsoft Dataverse 環境を使用します。 Dataverse 環境が、ガイドアプリやテナントとどのように連携するかを理解することが重要です。 このガイドでは、dataverse 管理する方法については説明しませんが、 [Dynamics 365 Guides Dynamics 365 Mixed Reality をデプロイするための基本的な概念](/dynamics365/mixed-reality/guides/admin-deployment-playbook)を確認してください。

## <a name="next-step"></a>次のステップ 
> [!div class="nextstepaction"]
> [企業に接続された展開-構成](hololens2-corp-connected-configure.md)