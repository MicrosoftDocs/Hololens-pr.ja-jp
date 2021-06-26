---
title: 商用HoloLens 2でのデプロイの計画
description: インフラストラクチャ、クラウド、モバイル デバイス管理など、エンタープライズ環境での HoloLens のデプロイと管理Azure Active Directory詳細を確認してください。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bogenera
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 2a0933bb754043934621a22ffa7764c9c88d93da
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924606"
---
# <a name="common-deployment-scenarios"></a>一般的な配置シナリオ

## <a name="overview"></a>概要

このページでは、エンタープライズ内の 2 つのデバイスを展開および管理する場合の 3 つの一般的Microsoft HoloLensアーキテクチャの概要について説明します。

多くの場合、デバイスを管理し、組織のリソースにアクセスする方法は、主に既に設定されている要因によって決まります。 既存のインフラストラクチャに基づいて、次のシナリオで一般的なデバイス管理スタイル (MDM) を確認してから、「商用環境での [HoloLens 2](hololens-core-components.md) デプロイの計画」を参照して、ニーズに一致するシナリオを特定してください。 デプロイ中に使用できる対応するガイドも 3 つ用意されています。


 1. [クラウド接続された環境のデプロイ ガイド](hololens2-cloud-connected-overview.md)
     1. [クラウド接続された環境 (外部クライアント) のデプロイ ガイド](hololens2-deployment-guide.md)
 1. [企業ネットワークの展開ガイド](hololens2-corp-connected-overview.md)
 1. [オフラインでの安全な環境展開ガイド](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>シナリオ A: クラウドに接続されたデバイスにデプロイする

このシナリオは、会社内にマネージド モバイル デバイスを展開する場合と同等です。 HoloLens 2は、主に企業ネットワークの外部環境で使用するためにデプロイされます。 企業リソースにはアクセスされないか、VPN 経由で制限される場合があります。 
 * 基本的な一般的な構成
   * Wi-Fiネットワークは、通常、インターネットおよびクラウド サービスに対して完全に開きます。
   * Azure AD Mobile デバイス管理 (MDM) 自動登録に参加する - MDM (Intune) マネージド
   * ユーザーが自分の企業アカウントでサインインする (Azure AD)
     * サポートされているデバイスごとに 1 人または複数のユーザー
   * デバイス ロックダウン構成のレベルは、フル オープンからシングル アプリ キオスクまで、特定の使用事例に基づいて適用されます。
   * 1 つ以上のアプリケーションが MDM 経由でデプロイされる

* 一般的な課題
   * シナリオの要件に基づいて、アプリケーションにHoloLens 2 MDM 構成を決定します。

[![シナリオ A 図 ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

対応するクラウド接続ガイドでは、デバイス管理に HoloLens 2 を登録し、必要に応じてライセンスを適用し、エンド ユーザーがデバイスのセットアップ時に Remote Assist をすぐに使用できると検証する方法について説明します。 短期的または長期的な外部使用のためにリモート サイトにデバイスを展開するには、外部クライアント ガイドを使用します。

> [!div class="nextstepaction"]
> [クラウド接続された環境のデプロイ ガイド](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [クラウド接続された環境 (外部クライアント) のデプロイ ガイド](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>シナリオ B: 組織のネットワーク内にデプロイする

このシナリオは、ほとんどの PC のクラシック デプロイとWindows 10です。 HoloLens 2は、主に社内リソースにアクセスできる企業ネットワークで使用するためにデプロイされます。 インターネットサービスとクラウド サービスは制限される場合があります。 

 * 基本的な一般的な構成
   * Wi-Fiネットワークは、内部リソースにアクセスできる内部企業ネットワークであり、インターネットまたはクラウド サービスへのアクセスが制限されています。
   * Azure AD MDM 自動登録との結合
   * MDM (Intune) マネージド
   * ユーザーが自分の企業アカウントでサインインする (Azure AD)
     * サポートされているデバイスごとに 1 人または複数のユーザー
   * デバイス ロックダウン構成のレベルは、フル オープンからシングル アプリ キオスクまで、特定の使用事例に基づいて適用されます。
   * 1 つ以上のアプリケーションが MDM 経由でデプロイされる

 * 一般的な課題
   * HoloLens 2オンプレミス AD 参加または SCCM はサポートされていません。 MDM Azure AD参加する必要があります。 現在も多くの企業では、このシナリオで Windows 10 PC をオンプレミスの AD 参加済みデバイスとして展開し、System Center 構成マネージャー (SCCM) によって管理され、クラウドベースの MDM ソリューションを介して内部 Windows 10 デバイスを管理するためのインフラストラクチャがデプロイまたは構成されていない可能性があります。
   * クラウドHoloLens 2デバイスなので、ユーザー認証、OS の更新、MDM 管理などのために、インターネットとクラウドに接続されたサービスに大きく依存しています。 企業ネットワークに接続する場合は、HoloLens 2 と、そのネットワーク上で実行されるアプリケーションへのアクセスを有効にするためのプロキシ/ファイアウォール規則を調整する必要があります。
   * 企業Wi-Fi接続には、通常、ネットワークに対してデバイスまたはユーザーを認証するための証明書が必要です。 MDM を介してデバイスに証明書を展開するためにWindows 10必要なインフラストラクチャまたは設定は、構成が困難な場合があります。

[![シナリオ B1 図 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![シナリオ B2 図 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

対応する企業ネットワーク ガイドでは、既存のデバイス管理に HoloLens 2 を登録し、必要に応じてライセンスを適用し、デバイスの設定後にエンド ユーザーが Dynamics 365 ガイドを操作できるだけでなく、カスタムのビジネス アプリを使用できるのを検証する方法について説明します。

> [!div class="nextstepaction"]
> [企業ネットワークの展開ガイド](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>シナリオ C: 安全なオフライン環境にデプロイする

これは、安全性の高い場所または機密性の高い場所に対する一般的なデプロイです。 HoloLens 2は、主にネットワークやインターネットにアクセスする必要がないオフラインで使用するためにデプロイされます。 
 * 基本的な一般的な構成
   * Wi-Fi接続が無効になっています。 必要に応じて、USB 経由のイーサネットで LAN 接続を有効にできます。
   * 管理されていない。
   * デバイス サインイン用のローカル ユーザー アカウント。
     * HoloLens 2は、1 つのローカル アカウントのみをサポートします。
   * デバイス ロックダウン構成のさまざまなレベルは、特定の使用例に基づいてプロビジョニング パッケージを介して適用されます。 これらの構成は、通常、セキュリティで保護された環境の要件のために制限されます。
   * プロビジョニング パッケージを使用して 1 つ以上のアプリケーションをデプロイする

 * 一般的な課題
   * プロビジョニング パッケージを通じて使用できる構成のセットは限られています
   * クラウド サービスを使用できないので、クラウド サービスのHoloLens 2制限されます。
   * これらのデバイスは手動で設定、構成、更新する必要があります。管理オーバーヘッドが高くなります。

[![オフライン セキュリティで保護された図 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

対応するオフライン セキュリティ ガイドでは、セキュリティで保護された環境で使用するためにアプリケーションをロックダウンするサンプル プロビジョニング HoloLens 2適用する手順を説明します。

> [!div class="nextstepaction"]
> [オフラインでの安全な環境展開ガイド](hololens-common-scenarios-offline-secure.md)


