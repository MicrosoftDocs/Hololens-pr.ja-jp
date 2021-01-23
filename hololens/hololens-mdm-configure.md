---
title: Microsoft のエンドポイント マネージャー Intune を使用して HoloLens デバイスを管理する
description: MDM を使用して Intune を使用して大規模な HoloLens Mixed Reality デバイスの CSP、ポリシー、管理を構成する方法について説明します。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/9/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ce288afdcb112c17ffde75078d641f3637a8448c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283958"
---
# Microsoft のエンドポイント マネージャー Intune を使用して HoloLens デバイスを管理する

MDM で管理できるさまざまな設定があります。 Intune デバイスを使用してグループ化し、ユーザーまたはデバイスのグループに構成を展開できます。 アプリを展開および管理し、ネットワークに接続するデバイスを設定し、必要な時間と更新リングで発生する更新プログラムを構成することもできます。 

## Intune を使用して管理する方法

### デバイスのカテゴリとグループ
Intune を使用すると、デバイス カテゴリを作成して、エンジニアリング、医療、開発者など、作成したカテゴリに基づいてグループにデバイスを自動的に追加できます。 Windows Holographic for Business を実行しているデバイスの管理を容易にするためのアイデアです。
続きを読む: [デバイスをグループに分類する](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)

### デバイス構成プロファイル
Intune には、組織内の異なるデバイスで有効または無効にできる設定と機能が含まれています。 これらの設定と機能は、プロファイルを使用して管理されます。 たとえば、Cortana を有効にするプロファイルを作成したり、Windows Holographic for Business を実行しているデバイスで Microsoft Defender Smart Screen を使用したりすることができます。
プロファイルでは、OMA-URI を使用して、一部の設定のカスタマイズ、デバイス制限の作成、仮想プライベート ネットワーク (VPN) と Wi-Fi の構成を行います。
[構成プロファイルとプロファイルの概要](https://docs.microsoft.com/mem/intune/configuration/device-profiles)について [説明します](https://docs.microsoft.com/mem/intune/configuration/device-profile-create)。

## 管理と構成が可能な例

MDM を使ってデバイスを管理すると、さまざまな項目を選択できます。 

### Wi-Fi
[Wi-Fi 設定は、](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) ワイヤレス ネットワーク設定をユーザーとデバイスに割り当てる。 ユーザー プロファイルを割り当Wi-Fi、ユーザーは自分で構成することなくWi-Fi企業のサイトにアクセスできます。
[HoloLens 用のネットワークの構成について詳しくは、次のリンクをご覧ください。](hololens-commercial-infrastructure.md)

### 証明書
証明書は、Web コンテンツのアカウント認証、Wi-Fi認証、VPN 暗号化、および SSL 暗号化を提供することで、セキュリティを向上させるのに役立ちます。 管理者はプロビジョニング パッケージを使用してデバイス上の証明書を手動で管理することができますが、MDM システムを使用して、登録から更新、失効まで、ライフサイクル全体にわたってそれらの証明書を管理するベスト プラクティスです。 MDM システムは、デバイスの登録後にこれらの証明書をデバイスの証明書ストアに自動的に展開できます (MDM システムが簡易証明書登録プロトコル (SCEP) または公開キー暗号化標準 #12 (PKCS#12) をサポートしている場合)。 MDM では、現在の証明書の有効期限が切る前に、登録済みクライアント証明書を照会して削除したり、新しい登録要求をトリガーしたりすることもできます。 

### プロキシ
ほとんどの企業イントラネット ネットワークは、プロキシを利用して内部トラフィックを管理します。 HoloLens 2 を使用すると、イーサネット接続およびネットワーク接続用のプロキシ Wi-Fi構成できます。 これらの設定は、VPN 接続には適用されません。 Windows 10 のプロキシ設定について詳しくは [、「NetworkProxy CSP」をご覧ください](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)。

### VPN
多くの場合、組織では VPN を使用して、企業のイントラネット上のアプリとリソースにアクセスします。 HoloLens 2 は SSL VPN 接続をサポートしています。SSL VPN 接続には、Microsoft Store からダウンロード可能なプラグインが必要であり、選択した VPN ベンダーに固有のプラグインが必要です。 
- [HoloLens の VPN について詳しくは、以下を参照してください](hololens-network.md#vpn)。
- VPN プロファイルの詳細については [、VPNv2 CSP を参照してください](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)。

### アプリの展開と管理
Intune を使用すると、Windows Holographic for Business を実行しているデバイスにアプリを追加できます。 MDM ソリューションを使用すると、IT の意思決定者と管理者は、企業内アプリ、業務アプリをプライベートに自動インストール (プッシュ) したり、ユーザー グループのストアを通じてアプリを購入することができます。 アプリを展開するには、次の多くの方法があります。
-   [Intune とポータル サイト]( app-deploy-intune.md)
-   [ビジネス向け Microsoft Store]( app-deploy-store-business.md)

Intune によるアプリ管理の詳細について説明します。
-   [Intune へのアプリの追加](https://docs.microsoft.com/mem/intune/apps/apps-add)
-   [Microsoft Store アプリを追加する](https://docs.microsoft.com/mem/intune/apps/store-apps-windows)
-   [作成するアプリを追加する](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
- [アプリをグループに割り当てる](https://docs.microsoft.com/mem/intune/apps/apps-deploy)

### ソフトウェア更新プログラム
Intune には、Windows 10 デバイスの更新リングと呼ばれる機能が含まれています。 これらの更新リングには、更新プログラムのインストール方法を決定する設定のグループが含まれます。 たとえば、更新プログラムをインストールするためのメンテナンス期間を作成することも、更新プログラムのインストール後に再起動することもできます。 更新リングは、Windows Holographic for Business を実行している複数のデバイスに適用できます。
Intune で [HoloLens の更新プログラムを管理する](hololens-updates.md) 方法とソフトウェア更新 [プログラムを管理する方法について詳しくは、以下をご覧ください](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。

### キオスク モードを構成する
Intune で利用可能な共有またはゲスト PC の機能を使用して、キオスクとして実行される Windows Holographic for Business デバイスを構成できます。 これらのデバイスは、1 つのアプリ (単一アプリキオスク モード) を実行するか、複数のアプリ (複数アプリキオスク モード) を実行できます。 キオスク モードは、既定でどのアプリにアクセスできる ID を制御するための UI です。
[HoloLens をキオスクとしてセットアップする方法について説明します。]( hololens-kiosk.md)

