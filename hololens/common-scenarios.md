---
title: 一般的なインフラストラクチャの展開シナリオ
description: さまざまなインフラストラクチャの展開に基づいて、さまざまなシナリオについて説明します。
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
ms.openlocfilehash: 4b9bd4335e45180276d69af2ce5f33a38ecb800f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309481"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>一般的なインフラストラクチャの展開シナリオの概要

ここでは、企業内で Microsoft HoloLens 2 デバイスを展開および管理する場合の3つの一般的なシナリオについて、大まかなアーキテクチャの概要を示します。 多くの場合、デバイスの管理方法と組織のリソースへのアクセス方法は、既に導入されている要因によって決まります。 既存のインフラストラクチャに基づいて、次のシナリオで一般的なデバイス管理スタイルを確認し、ニーズに合ったシナリオでデプロイするためのガイドを試してみることをお勧めします。

## <a name="scenarios"></a>シナリオ

次の図は、HoloLens 2 展開の一般的な3つのシナリオを示しています。
![シナリオ図](images/scenarios.jpg)

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a>シナリオ A: クラウド接続デバイスにデプロイする

HoloLens 2 は、主に企業ネットワークの外部の環境で使用するために展開されます。 企業リソースにアクセスできないか、VPN 経由で制限されている可能性があります。 この展開は、社内の管理対象モバイルデバイスに似ています。
 * 基本的な共通構成
   * Wi-Fi ネットワークは、通常、インターネットおよびクラウドサービスに対して完全に開いています。
   * モバイルデバイス管理 (MDM) の自動登録を使用した Azure AD 参加--MDM (Intune) で管理
   * ユーザーが自分の会社のアカウントでサインインする (Azure AD)
     * デバイスごとに1つまたは複数のユーザーがサポートされています
   * さまざまなレベルのデバイスロックダウン構成は、完全にオープンからシングルアプリキオスクまで、特定のユースケースに基づいて適用されます。
   * MDM を使用して1つ以上のアプリケーションが展開されている

* 一般的な課題
   * シナリオの要件に基づいて、HoloLens 2 に適用する MDM 構成を決定します。

シナリオ A と同様のデプロイガイドについては、「 [Cloud Connected HoloLens 2 とリモート](hololens2-cloud-connected-overview.md)アシスタンスのガイド」を参照してください。

> [!div class="nextstepaction"]
> [展開ガイド–リモートアシスタンスを使用したクラウド接続型 HoloLens 2](hololens2-cloud-connected-overview.md)

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
   * HoloLens 2 では、オンプレミスの AD join または SCCM はサポートされていません。 MDM との結合のみ Azure AD ます。 現在、多くの企業では、このシナリオでは、System Center Configuration Manager (SCCM) によって管理されているオンプレミス AD 参加済みデバイスとして Windows 10 Pc を展開します。また、クラウドベースの MDM ソリューションを使用して内部 Windows 10 デバイスを管理するためにインフラストラクチャをデプロイまたは構成することはできません。
   * HoloLens 2 はクラウドの最初のデバイスであるため、ユーザー認証、OS の更新、MDM の管理などのために、インターネットおよびクラウドに接続されたサービスに大きく依存します。 企業ネットワークに接続する場合、プロキシ/ファイアウォールルールを調整して、HoloLens 2 およびそれで実行されるアプリケーションにアクセスできるようにする必要があります。
   * 企業の Wi-Fi 接続では、通常、デバイスまたはユーザーをネットワークに認証するために証明書が必要です。 MDM を使用して Windows 10 デバイスに証明書を展開するために必要なインフラストラクチャまたは設定は、構成することが困難な場合があります。

> [!div class="nextstepaction"]
> [展開ガイド-企業接続 HoloLens 2 と Dynamics 365 ガイド](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a>シナリオ C: セキュリティで保護されたオフライン環境に配置する

HoloLens 2 は、主にネットワークやインターネットにアクセスすることなくオフラインで使用するように展開されています。 これは、セキュリティで保護された、または機密性の高い場所への一般的な展開です。
 * 基本的な共通構成
   * Wi-Fi 接続が無効になっています。 必要に応じて、LAN 経由のイーサネットが LAN 接続に対して有効になっている場合があります。
   * 管理されていません。
   * デバイスのサインイン用のローカルユーザーアカウント。
     * HoloLens 2 でサポートされるローカルアカウントは1つだけです。
   * さまざまなレベルのデバイスロックダウン構成は、特定のユースケースに基づいてパッケージをプロビジョニングすることによって適用されます。 これらの構成は、通常、セキュリティで保護された環境要件によって制限されます。
   * 1つ以上のアプリケーションがプロビジョニングパッケージを使用して展開されています

 * 一般的な課題
   * プロビジョニングパッケージで使用できる構成は限られています。
   * Cloud services は使用できないため、HoloLens 2 の機能が制限されます。
   * これらのデバイスは手動でセットアップ、構成、および更新する必要があるため、管理オーバーヘッドが高くなります。

このシナリオに似た展開ガイドについては、「 [オフラインのセキュリティで保護された展開ガイド」](hololens-common-scenarios-offline-secure.md)を参照してください。

> [!div class="nextstepaction"]
> [展開ガイド– Offline Secure HoloLens 2](hololens-common-scenarios-offline-secure.md)
