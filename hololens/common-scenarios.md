---
title: 一般的なインフラストラクチャのデプロイ シナリオ
description: Mixed Reality 用のさまざまなインフラストラクチャデプロイに基づく、最も一般的なデプロイ シナリオについて説明します。
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
keywords: hololens
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: v-evmill
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 30a35fb0fe5d5b669249df25ebff0228b552596c
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397425"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>一般的なインフラストラクチャのデプロイ シナリオの概要

次の情報では、エンタープライズ内の 2 つのデバイスを展開および管理する場合の 3 つの一般的Microsoft HoloLens概要を示します。 多くの場合、デバイスの管理方法と組織のリソースへのアクセス方法は、主に既に設定されている要因によって決まります。 既存のインフラストラクチャに基づいて、次のシナリオで一般的なデバイス管理スタイルを確認し、ニーズに合ったシナリオでのデプロイに関するガイドをお試しください。

## <a name="scenarios"></a>シナリオ

次の図は、次の 2 つの一般的なマネージド シナリオをHoloLens 2しています。
 

オフラインでセキュリティで保護されたデプロイを可能にする 3 番目のシナリオも用意されています。

### <a name="scenario-a-deploy-to-cloud-connected-devices"></a>シナリオ A: クラウドに接続されたデバイスにデプロイする

HoloLens 2は、主に企業ネットワークの外部環境で使用するためにデプロイされます。 企業リソースにはアクセスされないか、VPN 経由で制限される場合があります。 この展開は、会社内のマネージド モバイル デバイスに似ています。
 * 基本的な一般的な構成
   * Wi-Fiネットワークは、通常、インターネットおよびクラウド サービスに対して完全に開きます。
   * Azure AD Mobile デバイス管理 (MDM) 自動登録に参加する - MDM (Intune) マネージド
   * ユーザーが自分の企業アカウントでサインインする (Azure AD)
     * サポートされているデバイスごとに 1 人または複数のユーザー
   * デバイス ロックダウン構成のレベルは、フル オープンからシングル アプリ キオスクまで、特定の使用事例に基づいて適用されます。
   * 1 つ以上のアプリケーションが MDM 経由でデプロイされる



* 一般的な課題
   * シナリオの要件に基づいて、HoloLens 2 に適用する MDM 構成を決定します。

[![シナリオ図 ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

このシナリオに似たデプロイガイドについては、「 [クラウド接続環境の展開ガイド](hololens2-cloud-connected-overview.md)」を参照してください。

> [!div class="nextstepaction"]
> [クラウドに接続された環境のデプロイガイド](hololens2-cloud-connected-overview.md)
> [!div class="nextstepaction"]
> [クラウド接続環境 (外部クライアント) 配置ガイド](hololens2-deployment-guide.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a>シナリオ B: 組織のネットワーク内に展開する

HoloLens 2 は、主に企業ネットワーク上で企業内部リソースにアクセスするために展開されます。 インターネットおよびクラウドサービスは制限される場合があります。 この展開は、ほとんどの Windows 10 Pc における一般的な展開です。

 * 基本的な共通構成
   * Wi-Fi ネットワークは、内部リソースにアクセスし、インターネットまたはクラウドサービスへのアクセスが制限されている社内ネットワークです。
   * MDM の自動登録を使用した Azure AD 参加
   * MDM (Intune) で管理
   * ユーザーが自分の会社のアカウントでサインインする (Azure AD)
     * デバイスごとに1つまたは複数のユーザーがサポートされています
   * さまざまなレベルのデバイスロックダウン構成は、完全にオープンからシングルアプリキオスクまで、特定のユースケースに基づいて適用されます。
   * MDM を使用して1つ以上のアプリケーションが展開されている

 * 一般的な課題
   * HoloLens 2 では、オンプレミスの AD join または SCCM はサポートされていません。 MDM Azure AD参加する必要があります。 現在も多くの企業では、このシナリオで Windows 10 PC をオンプレミスの AD 参加済みデバイスとして展開し、System Center 構成マネージャー (SCCM) によって管理され、クラウドベースの MDM ソリューションを介して内部 Windows 10 デバイスを管理するためのインフラストラクチャがデプロイまたは構成されていない可能性があります。
   * クラウドHoloLens 2デバイスなので、ユーザー認証、OS の更新、MDM 管理などのために、インターネットとクラウドに接続されたサービスに大きく依存しています。 企業ネットワークに接続する場合は、HoloLens 2 と、そのネットワーク上で実行されるアプリケーションへのアクセスを有効にするためのプロキシ/ファイアウォール規則を調整する必要があります。
   * 企業Wi-Fi接続には、通常、ネットワークに対してデバイスまたはユーザーを認証するための証明書が必要です。 MDM を介してデバイスに証明書を展開するためにWindows 10必要なインフラストラクチャまたは設定は、構成が困難な場合があります。

[![シナリオ B1 図 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![シナリオ B2 図 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

このシナリオに似たデプロイ ガイドについては、企業ネットワーク展開ガイドの [ガイドを参照してください](hololens2-corp-connected-overview.md)。

> [!div class="nextstepaction"]
> [企業ネットワーク展開ガイド](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a>シナリオ C: 安全なオフライン環境にデプロイする

HoloLens 2は、主にネットワークやインターネットにアクセスする必要がないオフラインで使用するためにデプロイされます。 これは、安全性の高い場所または機密性の高い場所に対する一般的なデプロイです。
 * 基本的な一般的な構成
   * Wi-Fi接続が無効になっています。 必要に応じて、USB 経由のイーサネットで LAN 接続を有効にできます。
   * 管理されていない。
   * デバイス サインイン用のローカル ユーザー アカウント。
     * HoloLens 2は、1 つのローカル アカウントのみをサポートします。
   * デバイス ロックダウン構成のさまざまなレベルは、特定の使用例に基づいてプロビジョニング パッケージを介して適用されます。 これらの構成は、通常、セキュリティで保護された環境要件によって制限されます。
   * 1つ以上のアプリケーションがプロビジョニングパッケージを使用して展開されています

 * 一般的な課題
   * プロビジョニングパッケージで使用できる構成は限られています。
   * Cloud services は使用できないため、HoloLens 2 の機能が制限されます。
   * これらのデバイスは手動でセットアップ、構成、および更新する必要があるため、管理オーバーヘッドが高くなります。

[![オフラインのセキュリティで保護された図 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

このシナリオに似た展開ガイドについては、「 [オフラインの安全な環境の展開ガイド」](hololens-common-scenarios-offline-secure.md)を参照してください。

> [!div class="nextstepaction"]
> [オフライン安全環境の展開ガイド](hololens-common-scenarios-offline-secure.md)
