---
title: 一般的な配置シナリオ
description: インフラストラクチャ、デバイス管理、モバイル デバイス管理HoloLens、エンタープライズ環境でのAzure Active Directoryの展開と管理について説明します。
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
ms.openlocfilehash: 529dde590c30d4a51fa8ae61e9d37d22170dc271
ms.sourcegitcommit: 5130823947caffd2a444e9d8fb15cd24cbb6414c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2021
ms.locfileid: "114659065"
---
# <a name="common-deployment-scenarios"></a>一般的な配置シナリオ

## <a name="overview"></a>概要

新しいデバイスをデプロイする方法を見つめ直すのは、初めて試す際に苦労する可能性があります。 ここでは、組織内の 2 つのデバイスをMicrosoft HoloLens管理するさまざまな方法を共有しています。

ソリューションを大規模にデプロイする必要があります。 お客様をそこにお手に入れしたいと思います。 最初に、デバイス (つまりホログラム) を展開してターゲット Mixed Reality シナリオの価値を実現する手順について説明します。作成した D365 Remote Assist、ガイド、または Azure Mixed Reality サービス対応アプリケーションを使用しているかに関係はありません。

あなたは、ビジネス上の意思決定者、IT プロフェッショナル、または組織内の組織内でHoloLensを探しているイノベーション チームである可能性があります。 概念実証からスケーリングされたデプロイに構築する場合、デプロイ ガイドは、IT インフラストラクチャ内の HoloLens の規模に関係なく意味を持っています。 最も一般的なデプロイ シナリオは次のとおりです。

| シナリオ |使用 | 重要なポイント |
|---------|---------|---------|
| [シナリオ A: クラウドに接続されたデバイス](hololens2-cloud-connected-overview.md) | 最初にデプロイを開始すると、基本的なプロセスを確認するために、小規模から開始し、クラウドに接続された 1 つのデバイスをデプロイできます。 | デバイスはクラウド サービスとパブリック インターネットに接続されます。 これは、お客様の使用事例、フィールド サービス、概念実証に最適です。|
| [シナリオ B: 組織のネットワーク](hololens2-corp-connected-overview.md) | 大規模な運用にデプロイする場合は、組織のネットワークとの統合が必要な場合があります。 | デバイスは "企業" の Wi-Fi ネットワークに接続されます。 これは、内部ユーザー、または企業環境内での使用に最適です。|
| [シナリオ C: オフラインでセキュリティで保護された環境](hololens-common-scenarios-offline-secure.md) | ミッション クリティカルなプロセスや企業ポリシーによっては、オフライン環境の使用が要求される場合があります。 | デバイスは非常に制限の厳しいネットワークに接続されます。または、純粋にオフラインのデバイスになります。 これは、安全性の高い環境、またはリモート領域でのインターネット接続の制限に最適です。 |

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>シナリオ A: クラウドに接続されたデバイスにデプロイする

このシナリオは、会社内にマネージド モバイル デバイスを展開する場合と同等です。 HoloLens 2は、主に企業ネットワークの外部環境で使用するためにデプロイされます。 企業リソースにはアクセスされないか、VPN 経由で制限される場合があります。

[![シナリオ A 図](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

### <a name="when-to-use"></a>使用する場合

次の場合は、このデプロイ モデルを検討してください。

* 概念実証、パイロット、およびフィールド サービスのデプロイ
* デプロイRemote Assist [](hololens2-options-remote-assist.md)

### <a name="basic-common-configurations"></a>基本的な一般的な構成

* Wi-Fiネットワークは、通常、インターネットおよびクラウド サービスに対して完全に開きます
* Azure AD Mobile デバイス管理 (MDM) 自動登録に参加する - MDM (Intune) マネージド
* ユーザーが自分の企業アカウントでサインインする (Azure AD)
  * サポートされているデバイスごとに 1 人または複数のユーザー
* デバイス ロックダウン構成のレベルは、フル オープンからシングル アプリ キオスクまで、特定の使用事例に基づいて適用されます。
* 1 つ以上のアプリケーションが MDM 経由でデプロイされる

### <a name="common-challenges"></a>一般的な課題

* シナリオの要件に基づいて、アプリケーションに適用HoloLens 2 MDM 構成を決定する

対応するクラウド接続ガイドでは、HoloLens 2 をデバイス管理に登録し、必要に応じてライセンスを適用し、エンド ユーザーがデバイスのセットアップ時に Remote Assist をすぐに使用できると検証する方法について説明します。

> [!div class="nextstepaction"]
> [クラウド接続デプロイ ガイド](hololens2-cloud-connected-overview.md)

短期的または長期的な外部使用のためにリモート サイトにデバイスを展開するには、外部クライアント ガイドを使用します。

> [!div class="nextstepaction"]
> [クラウド接続 (外部クライアント) デプロイ ガイド](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>シナリオ B: 組織のネットワーク内にデプロイする

このシナリオは、ほとんどの PC のクラシック デプロイとWindows 10です。 HoloLens 2は、主に社内リソースにアクセスできる企業ネットワークで使用するためにデプロイされます。 インターネットサービスとクラウド サービスは制限される場合があります。 

[![シナリオ B1 図](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![シナリオ B2 図](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

### <a name="when-to-use"></a>使用する場合

次の場合は、このデプロイ モデルを検討してください。

* 内部ユーザー
* 企業環境内での大規模なデプロイ (パイロットと実稼働)

### <a name="basic-common-configurations"></a>基本的な一般的な構成

* Wi-Fiネットワークは、内部リソースにアクセスできる内部企業ネットワークであり、インターネットまたはクラウド サービスへのアクセスが制限されています。
* Azure AD MDM 自動登録との結合
* MDM (Intune) マネージド
* ユーザーが自分の企業アカウントでサインインする (Azure AD)
  * サポートされているデバイスごとに 1 人または複数のユーザー
* デバイス ロックダウン構成のレベルは、フル オープンからシングル アプリ キオスクまで、特定の使用事例に基づいて適用されます。
* 1 つ以上のアプリケーションが MDM 経由でデプロイされる

### <a name="common-challenges"></a>一般的な課題

* HoloLens 2オンプレミス AD 参加またはオンプレミス の AD 参加 (SCCM) System Center Configuration Managerサポートされていません。 MDM Azure AD参加する必要があります。 現在、多くの企業では、このシナリオでは、SCCM によって管理されるオンプレミスの AD 参加済みデバイスとして Windows 10 PC をデプロイし、クラウドベースの MDM ソリューションを介して内部 Windows 10 デバイスを管理するためのインフラストラクチャがデプロイまたは構成されていない可能性があります。
* クラウドHoloLens 2デバイスなので、ユーザー認証、OS の更新、MDM 管理などのために、インターネットとクラウドに接続されたサービスに大きく依存しています。 企業ネットワークに接続する場合は、HoloLens 2 と、そのネットワーク上で実行されるアプリケーションに対してアクセスを有効にするために、プロキシ/ファイアウォール規則を調整する必要があります。
* 企業Wi-Fi接続には、通常、ネットワークに対してデバイスまたはユーザーを認証するための証明書が必要です。 MDM を介してデバイスに証明書を展開するためにWindows 10必要なインフラストラクチャまたは設定は、構成が困難な場合があります。

対応する企業接続ガイドでは、既存のデバイス管理に HoloLens 2 を登録し、必要に応じてライセンスを適用し、デバイスの設定後にエンド ユーザーが Dynamics 365 ガイドを操作できるだけでなく、カスタムのビジネス アプリを使用できるのを検証する方法について説明します。

> [!div class="nextstepaction"]
> [企業接続デプロイ ガイド](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>シナリオ C: 安全なオフライン環境にデプロイする

これは、安全性の高い場所または機密性の高い場所に対する一般的なデプロイです。 HoloLens 2は、主にネットワークやインターネットにアクセスする必要がないオフラインで使用するためにデプロイされます。

[![オフライン セキュリティで保護された図 1](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

### <a name="when-to-use"></a>使用する場合

次の場合は、このデプロイ モデルを検討してください。

* データを家に保持する必要がある安全性の高い環境
* 一般のユーザーがデバイスを使用する "エクスペリエンス"
* リモート領域でのインターネット接続の問題

### <a name="basic-common-configurations"></a>基本的な一般的な構成

* Wi-Fi接続が無効になっています。 必要に応じて、USB 経由のイーサネットで LAN 接続を有効にできます
* 管理されていない
* デバイス サインイン用のローカル ユーザー アカウント
  * HoloLens 2は 1 つのローカル アカウントのみをサポートします
* デバイス ロックダウン構成のさまざまなレベルは、特定の使用例に基づいてプロビジョニング パッケージを介して適用されます。 これらの構成は、通常、セキュリティで保護された環境の要件のために制限されます
* プロビジョニング パッケージを使用して 1 つ以上のアプリケーションをデプロイする

### <a name="common-challenges"></a>一般的な課題

* プロビジョニング パッケージを通じて使用できる構成のセットは限られています
* クラウド サービスを使用できないので、クラウド サービスのHoloLens 2制限されます。
* これらのデバイスは手動で設定、構成、更新する必要があります。管理オーバーヘッドが高くなります。

対応するオフライン セキュリティ ガイドでは、セキュリティで保護された環境で使用するためにアプリケーションをロックダウンHoloLens 2プロビジョニング パッケージのサンプルを適用する方法について説明します。

> [!div class="nextstepaction"]
> [オフラインでの安全な環境展開ガイド](hololens-common-scenarios-offline-secure.md)
