---
title: 一般的な配置シナリオ
description: インフラストラクチャ、Azure Active Directory、モバイルデバイス管理など、エンタープライズ環境での HoloLens の展開と管理の詳細について説明します。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bgener
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 5a4f251f3ca6eae5e85e4d763074e035039159cb
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189241"
---
# <a name="common-deployment-scenarios"></a>一般的な配置シナリオ

## <a name="overview"></a>概要

新しいデバイスを展開する方法については、最初に試してみると苦労することがあります。 ここでは、組織内で Microsoft HoloLens 2 つのデバイスを展開および管理するさまざまな方法を紹介します。

ソリューションを大規模にデプロイする必要がある。 このような情報を取得します。 まず、デバイスをデプロイする手順について説明します。これは、D365 リモートアシスタンス、ガイド、または作成した Azure mixed reality サービス対応アプリケーションを使用しているかどうかにかかわらず、ターゲットの混合現実シナリオの価値を実現するためです。

ビジネス上の意思決定者、IT プロフェッショナル、またはお客様の組織内で HoloLens を採用するイノベーションチームである場合があります。 概念実証から構築された展開に合わせて、展開ガイドでは、規模や規模に関係なく、IT インフラストラクチャ内の HoloLens を理解することができます。 最も一般的な展開シナリオを次に示します。

| シナリオ |使用 | 重要なポイント |
|---------|---------|---------|
| [シナリオ A: クラウド接続デバイス](hololens2-cloud-connected-overview.md) | 最初にデプロイを開始するときに、基本的なプロセスを表示するために、小規模に開始して、クラウドに接続された単一のデバイスをデプロイすることができます。 | デバイスは、クラウドサービスとパブリックインターネットに接続されます。 これは、お客様のユースケース、フィールドサービス、概念実証に最適です。|
| [シナリオ B: 組織のネットワーク](hololens2-corp-connected-overview.md) | 大規模な運用環境にデプロイする場合は、組織のネットワークとの統合が必要になることがあります。 | デバイスは、"企業" の wi-fi ネットワークに接続されます。 これは、社内ユーザーに最も適しているか、企業環境内で使用されています。|
| [シナリオ C: オフラインのセキュリティで保護された環境](hololens-common-scenarios-offline-secure.md) | ミッションクリティカルなプロセスや企業のポリシーによっては、オフライン環境の使用が必要になる場合があります。 | デバイスは、非常に制限の厳しいネットワークに接続されるか、純粋にオフラインデバイスになります。 これは、高度なセキュリティで保護された環境、またはリモート領域でのインターネット接続の制限に最適です。 |

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>シナリオ A: クラウド接続デバイスにデプロイする

このシナリオは、企業内で管理されているモバイルデバイスを展開することに相当します。 HoloLens 2 は、主に企業ネットワークの外部の環境で使用するためにデプロイされます。 企業リソースにアクセスできないか、VPN 経由で制限されている可能性があります。

[![シナリオ図。](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

### <a name="when-to-use"></a>使用する場合

このデプロイモデルを検討してください。

* 概念実証、パイロット、およびフィールドサービスのデプロイ
* [リモート](hololens2-options-remote-assist.md)アシスタンスの展開

### <a name="basic-common-configurations"></a>基本的な共通構成

* Wi-Fi ネットワークは、通常、インターネットおよびクラウドサービスに対して完全に開いています。
* モバイルデバイス管理 (MDM) の自動登録を使用した Azure AD 参加--MDM (Intune) で管理
* ユーザーが自分の会社のアカウントでサインインする (Azure AD)
  * デバイスごとに1つまたは複数のユーザーがサポートされています
* さまざまなレベルのデバイスロックダウン構成は、完全にオープンからシングルアプリキオスクまで、特定のユースケースに基づいて適用されます。
* MDM を使用して1つ以上のアプリケーションが展開されている

### <a name="common-challenges"></a>一般的な課題

* シナリオの要件に基づいて HoloLens 2 に適用する MDM 構成を決定する

対応するクラウド接続ガイドでは、HoloLens 2 をデバイス管理に登録する方法、必要に応じてライセンスを適用する方法、およびエンドユーザーがデバイスのセットアップ時にリモートアシスタンスをすぐに使用できることを検証する方法について説明します。

> [!div class="nextstepaction"]
> [クラウドに接続されたデプロイガイド](hololens2-cloud-connected-overview.md)

外部クライアントガイドを使用して、短期間または長期的な外部使用のためにデバイスをリモートサイトに展開します。

> [!div class="nextstepaction"]
> [クラウドに接続された (外部クライアント) 展開ガイド](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>シナリオ B: 組織のネットワーク内に展開する

このシナリオは、ほとんどの Windows 10 pc のクラシックデプロイと同じです。 HoloLens 2 は、主に企業ネットワーク上で社内の社内リソースにアクセスするために展開されます。 インターネットおよびクラウドサービスは制限される場合があります。 

[![シナリオ B1 の図。](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![シナリオ B2 の図。](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

### <a name="when-to-use"></a>使用する場合

このデプロイモデルを検討してください。

* 内部ユーザー
* 企業環境内の大規模なデプロイ (パイロットと運用)

### <a name="basic-common-configurations"></a>基本的な共通構成

* Wi-Fi ネットワークは、内部リソースにアクセスし、インターネットまたはクラウドサービスへのアクセスが制限されている社内ネットワークです。
* MDM の自動登録を使用した Azure AD 参加
* MDM (Intune) で管理
* ユーザーが自分の会社のアカウントでサインインする (Azure AD)
  * デバイスごとに1つまたは複数のユーザーがサポートされています
* さまざまなレベルのデバイスロックダウン構成は、完全にオープンからシングルアプリキオスクまで、特定のユースケースに基づいて適用されます。
* MDM を使用して1つ以上のアプリケーションが展開されている

### <a name="common-challenges"></a>一般的な課題

* HoloLens 2 は、オンプレミスの AD join または System Center Configuration Manager (SCCM) をサポートしていません。 MDM との結合のみ Azure AD ます。 現在、多くの企業では、SCCM で管理されているオンプレミスの AD 参加済みデバイスとして Windows 10 pc をデプロイし、クラウドベースの MDM ソリューションを介して内部 Windows 10 デバイスを管理するためにインフラストラクチャをデプロイまたは構成することはできません。
* クラウドの最初のデバイスとして HoloLens 2 は、ユーザー認証、OS の更新、MDM の管理などのために、インターネットおよびクラウドに接続されたサービスに大きく依存します。 企業ネットワークに接続する場合、プロキシ/ファイアウォールルールを調整して、HoloLens 2 およびそれで実行されるアプリケーションにアクセスできるようにする必要があります。
* 企業の Wi-Fi 接続では、通常、デバイスまたはユーザーをネットワークに認証するために証明書が必要です。 MDM を使用してデバイスを Windows 10 するために証明書を展開するために必要なインフラストラクチャや設定は、構成するのが困難な場合があります。

対応する企業接続ガイドでは、HoloLens 2 を既存のデバイス管理に登録する方法、必要に応じてライセンスを適用する方法、エンドユーザーが Dynamics 365 ガイドを操作できること、およびデバイスのセットアップ後にカスタムの基幹業務アプリを使用できることを検証する方法について説明します。

> [!div class="nextstepaction"]
> [企業に接続された展開ガイド](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>シナリオ C: セキュリティで保護されたオフライン環境に配置する

これは、セキュリティで保護された、または機密性の高い場所への一般的な展開です。 HoloLens 2 は、主にネットワークまたはインターネットアクセスなしでオフラインで使用するために展開されます。

[![オフラインのセキュリティで保護された図1。](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

### <a name="when-to-use"></a>使用する場合

このデプロイモデルを検討してください。

* データを社内に保持する必要がある、高度に保護された環境
* 公共のデバイスを使用する "エクスペリエンス"
* リモート領域でのインターネット接続の問題

### <a name="basic-common-configurations"></a>基本的な共通構成

* Wi-Fi 接続が無効になっています。 必要に応じて、LAN 経由のイーサネットが LAN 接続に対して有効になっている場合がある
* 管理されていない
* デバイスサインインのローカルユーザーアカウント
  * HoloLens 2 でサポートされるローカルアカウントは1つだけです。
* さまざまなレベルのデバイスロックダウン構成は、特定のユースケースに基づいてパッケージをプロビジョニングすることによって適用されます。 これらの構成は、通常、セキュリティで保護された環境要件によって制限されます。
* 1つ以上のアプリケーションがプロビジョニングパッケージを使用して展開されています

### <a name="common-challenges"></a>一般的な課題

* プロビジョニングパッケージで使用できる構成は限られています。
* クラウドサービスは使用できないため、HoloLens 2 の機能を制限します。
* これらのデバイスは手動でセットアップ、構成、および更新する必要があるため、管理オーバーヘッドが高くなります。

対応するオフラインセキュリティガイドには、セキュリティで保護された環境で使用するために HoloLens 2 をロックダウンするサンプルプロビジョニングパッケージを適用するための手順が記載されています。

> [!div class="nextstepaction"]
> [オフラインでの安全な環境展開ガイド](hololens-common-scenarios-offline-secure.md)
