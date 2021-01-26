---
title: 展開ガイド - リモート アシストによるクラウド接続 HoloLens 2 の大規模な展開 - 準備
description: Azure Active Directory と ID 管理を使用して、クラウドに接続されたネットワーク上で HoloLens デバイスを登録する準備をする方法について説明します。
keywords: HoloLens, 管理, クラウド接続, リモート アシスト, AAD, Azure AD, MDM, モバイル デバイス管理
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283868"
---
# 準備 - クラウド接続ガイド

この記事の終わりまでに、Azure AD、MDM をセットアップし、Azure AD アカウントとネットワーク要件の使用について理解する必要があります。 このガイドのセクションでは、ユーザーと組織が HoloLens 2 をクラウドに展開し、Dynamics 365 リモート アシストを使用する準備を行うのに役立ちます。 インフラストラクチャの各部分の重要性に加え、必要に応じてこれらの部分をセットアップするのに役立つガイドへのリンクを提供します。

## Infrastructure Essentials

個人展開シナリオと企業展開シナリオの両方で、MDM システムは Windows 10 Holographic デバイスの展開と管理に必要な重要なインフラストラクチャです。 Azure AD Premium サブスクリプションは、ID プロバイダーとして推奨され、特定の機能をサポートするために必要です。

### Azure Active Directory

Azure AD は、ID とアクセス管理を提供する、クラウド ベースのディレクトリ サービスです。 Microsoft Office 365 または Intune を使用している組織は、既に Azure AD を使用しています。このエディションには、Free、Premium P1、Premium P2 の 3 つのエディションがあります [(Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions)エディションをご覧ください)。すべてのエディションで Azure AD デバイスの登録がサポートされますが、このガイドで後で使用する MDM 自動登録を有効にするには Premium P1 が必要です。

> [!IMPORTANT]
> HoloLens デバイスはオンプレミスのデバイスへの参加をサポートしていないので、Azure Active Directory をADです。 Azure Active Directory&#39;まだセットアップしていない場合は、このリンクの指示に従って [、Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)で新しいテナントを作成します。

## ID 管理

従業員は 1 つのアカウントのみを使用してデバイスを初期化できます。そのため&#39;アカウントを最初に制御する必要が生じません。 選択したアカウントによって、デバイスを制御するユーザーが決まり、管理機能に影響があります。

このガイドでは、使用する [ID](https://docs.microsoft.com/hololens/hololens-identity) に Azure AD アカウント、または Azure Active Directory アカウントを使用するように選択しました。 Azure アカウントには、次AD使用する複数の利点があります。

- 従業員は Azure AD アカウントを使用して Azure AD にデバイスを登録し、組織&#39;の MDM ソリューションに自動的に登録します (Azure AD + MDM – Azure AD Premium が必要)。
- Azure AD アカウントはシングル [サインオンをサポートしています](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on)。 ユーザーがリモート アシストにサインインすると、サインインしている Azure AD ユーザーの ID が認識され、ユーザーはアプリにサインインして効率的なエクスペリエンスを得る。
- Azure ADアカウントには、Windows Hello for Business 経由[で](https://docs.microsoft.com/hololens/hololens-identity)[追加の認証オプションがあります](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)。 虹彩ログイン ユーザーは、他のデバイスからサインインしたり、FIDO セキュリティ キーを使用したりすることもできます。

### モバイル デバイス管理

Enterprise Mobility + Security の一部である Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)は、テナントに接続されているデバイスを管理するクラウドベースの MDM システムです。 Office 365 と同様に、Intune は ID 管理に Azure AD を使用します。そのため、従業員は Intune にデバイスを登録するために使用する資格情報と同じ資格情報を使用して、Office 365 にサインインします。 Intune は、完全な MDM ソリューションを提供するために、iOS や Android などの他のオペレーティング システムを実行するデバイスもサポートしています。 このガイドの目的上、HoloLens 2&#39;大規模なクラウド展開を可能にするための Intune の使用に重点を置いて説明します。

> [!IMPORTANT]
> モバイル デバイス管理を使用する必要があります。 まだセットアップしていない&#39;、このガイドに従って Intune を使い始 [めましょう](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)。

> [!NOTE]
> 複数の MDM システムが Windows 10 をサポートしており、ほとんどは、個人のデバイスおよび企業のデバイスの展開のシナリオをサポートしています。 現在、Windows 10 Holographic をサポートする MDM プロバイダーには、AirWatch、MobileIron などが含まれます。 業界をリードする MDM ベンダーのほとんどは既に Azure AD との統合をサポートしています。 Azure AD をサポートする MDM ベンダーは [Azure Marketplace](https://azure.microsoft.com/marketplace/) で検索できます。

## ネットワーク

このセットアップでは、HoloLens 2 デバイスが、利用可能な開いているネットワークからインターネットに接続Wi-Fiしています。 ユーザーは場所に基づいてネットワーク接続を変更する必要がある可能性があるから[、HoloLens](https://docs.microsoft.com/hololens/hololens-network)デバイスを Wi-Fi に接続する方法を学習する必要があります。

Dynamics 365 リモート アシストには、帯域幅、待機時間、ジッター、パケット損失など、ビデオ通話のエクスペリエンスに影響を与える可能性があるさまざまなネットワーク条件があります。 帯域幅が少ない環境では音声通話やビデオ通話が可能な場合でも、機能低下が発生する可能性があります。 HoloLens で Dynamics 365 リモート アシストを使用する場合は、次のネットワーク要件に注意してください。

**30** fps で HD 1080p の解像度でピアツーピアの HD 品質ビデオ通話を行う場合は、最小 : 1.5 Mbps アップ/ダウンが必要です。

**最適:** HD 1080p の解像度のピアツーピア HD 品質ビデオ通話では、4 ~ 5 Mbps のアップ/ダウンが期待されます。

詳しくは、次の情報を参照してください。

- [ネットワーク要件](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [ネットワークの最適化に関する推奨事項](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### オプション: HoloLens を VPN に接続する

このガイドに接続されているデバイスは、外部クラウド ネットワーク経由でネットワークに接続します。 VPN 経由でデバイスを接続する必要&#39;会社のリソースにアクセスする場合があります。 デバイスを VPN に接続する方法には、エンド ユーザーがデバイス UI を使用して接続できる方法と、デバイスを管理して PPKG または MDM から VPN プロファイルを受信する方法の両方があります。 VPN の設定方法については&#39;この記事では説明しないので、&#39;でさまざまな VPN プロトコルや VPN を管理する方法について詳しくは[、HoloLens](https://docs.microsoft.com/hololens/hololens-network#vpn)と VPN に関するガイドをご覧ください。

## 次のステップ

> [!div class="nextstepaction"]
> [クラウド接続展開 - 構成](hololens2-cloud-connected-configure.md)
