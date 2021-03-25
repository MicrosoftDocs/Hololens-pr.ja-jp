---
title: 一般的なインフラストラクチャの展開シナリオ
description: 複合現実向けさまざまなインフラストラクチャ展開に基づく最も一般的な展開シナリオについて説明します。
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
keywords: HoloLens
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
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448495"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>共通インフラストラクチャ展開シナリオの概要

次の情報は、エンタープライズ内で Microsoft HoloLens 2 デバイスを展開および管理する場合の 3 つの一般的なシナリオの概要を示します。 多くの場合、デバイスの管理方法と組織のリソースへのアクセス方法は、主に既に設定されている要因によって決まります。 既存のインフラストラクチャに基づいて、次のシナリオで一般的なデバイス管理スタイルを確認し、ニーズに合ったシナリオで展開するガイドを試してみてください。

## <a name="scenarios"></a>シナリオ

次の図は、HoloLens 2 展開の 3 つの一般的なシナリオを表しています。
![シナリオ図](images/scenarios.jpg)

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a>シナリオ A: クラウド接続デバイスへの展開

HoloLens 2 は、主に企業ネットワーク外の環境で使用するために展開されます。 企業のリソースにアクセスできないか、VPN を介して制限される場合があります。 この展開は、企業内の管理対象モバイル デバイスに似ています。
 * 基本的な一般的な構成
   * Wi-Fiネットワークは、通常、インターネットおよびクラウド サービスに対して完全に開きます。
   * Azure AD モバイル デバイス管理 (MDM) 自動登録に参加する--MDM (Intune) マネージ
   * ユーザーが自分の企業アカウントでサインインする (Azure AD)
     * サポートされるデバイスごとに 1 人または複数のユーザー
   * デバイス のロックダウン構成のレベルは、完全に開くから単一のアプリ キオスクまで、特定の使用例に基づいて適用されます。
   * 1 つ以上のアプリケーションが MDM 経由で展開される

* 一般的な課題
   * シナリオ要件に基づいて HoloLens 2 に適用する MDM 構成を決定します。

シナリオに似た展開ガイドについては、リモート アシストを使用した [クラウド接続 HoloLens 2 のガイドを参照してください](hololens2-cloud-connected-overview.md)。

> [!div class="nextstepaction"]
> [展開ガイド – リモート アシストを使用したクラウド接続 HoloLens 2](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a>シナリオ B: 組織のネットワーク内に展開する

HoloLens 2 は、主に内部の企業リソースにアクセスできる企業ネットワークで使用するために展開されます。 インターネットおよびクラウド サービスは制限される場合があります。 この展開は、ほとんどの Windows 10 PC の一般的な展開です。

 * 基本的な一般的な構成
   * Wi-Fiネットワークは、内部リソースにアクセスできる内部企業ネットワークであり、インターネットまたはクラウド サービスへのアクセスが制限されています。
   * Azure AD MDM 自動登録に参加する
   * MDM (Intune) マネージ
   * ユーザーが自分の企業アカウントでサインインする (Azure AD)
     * サポートされるデバイスごとに 1 人または複数のユーザー
   * デバイス のロックダウン構成のレベルは、完全に開くから単一のアプリ キオスクまで、特定の使用例に基づいて適用されます。
   * 1 つ以上のアプリケーションが MDM 経由で展開される

 * 一般的な課題
   * HoloLens 2 は、参加または SCCM のADサポートされていません。 MDM にADできるのは Azure のみです。 多くの企業は、現在もこのシナリオでは、オンプレミスの AD 参加デバイスとして Windows 10 PC を展開し、System Center Configuration Manager (SCCM) によって管理され、クラウドベースの MDM ソリューションを介して内部 Windows 10 デバイスを管理するためのインフラストラクチャが展開または構成されていない可能性があります。
   * HoloLens 2 はクラウド ファースト デバイスなので、ユーザー認証、OS 更新プログラム、MDM 管理などのインターネットおよびクラウド接続サービスに大きく依存しています。 企業ネットワークに接続する場合、HoloLens 2 と、その上で実行されるアプリケーションへのアクセスを有効にするには、プロキシ/ファイアウォールルールを調整する必要があります。
   * 企業Wi-Fi接続には、通常、デバイスまたはユーザーをネットワークに対して認証するための証明書が必要です。 MDM を介して Windows 10 デバイスに証明書を展開するために必要なインフラストラクチャまたは設定は、構成が困難な場合があります。

> [!div class="nextstepaction"]
> [展開ガイド – Dynamics 365 ガイドを使用した企業接続 HoloLens 2](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a>シナリオ C: 安全なオフライン環境での展開

HoloLens 2 は、主にネットワークやインターネット アクセスがないオフラインで使用するために展開されます。 これは、高度にセキュリティで保護された場所または機密の場所に対する一般的な展開です。
 * 基本的な一般的な構成
   * Wi-Fiが無効になっている場合。 必要に応じて、USB 経由のイーサネットで LAN 接続を有効にできます。
   * 管理されていない。
   * デバイス サインインのローカル ユーザー アカウント。
     * HoloLens 2 では、ローカル アカウントが 1 つしかサポートされません。
   * デバイスロックダウン構成のレベルは、特定の使用例に基づいてプロビジョニング パッケージを介して適用されます。 これらの構成は、通常、セキュリティで保護された環境要件のために制限されます。
   * 1 つ以上のアプリケーションがプロビジョニング パッケージ経由で展開される

 * 一般的な課題
   * プロビジョニング パッケージを使用して使用できる構成のセットは制限されています
   * クラウド サービスを使用できないので、HoloLens 2 の機能が制限されます。
   * これらのデバイスを手動で設定、構成、および更新する必要がある場合の管理オーバーヘッドが大きくなります。

このシナリオに似た展開ガイドについては、「オフライン セキュア展開ガイド [」を参照してください](hololens-common-scenarios-offline-secure.md)。

> [!div class="nextstepaction"]
> [展開ガイド – オフライン セキュア HoloLens 2](hololens-common-scenarios-offline-secure.md)
