---
title: Microsoft Endpoint Manager Intune を使用した HoloLens デバイスの管理
description: MDM を使用して CSP とポリシーを構成し、HoloLens をスケールで管理します。
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
ms.openlocfilehash: 4fda0b271e915e82350f806418d2f02cbdd5a796
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009641"
---
# Microsoft Endpoint Manager Intune を使用した HoloLens デバイスの管理

MDM では、さまざまな設定を管理できます。 Intune デバイスを使用してグループ化し、構成をユーザーまたはデバイスのグループに展開することができます。 また、アプリを展開して管理したり、ネットワークに接続するためのデバイスをセットアップしたり、必要に応じて更新を設定したり、必要な更新を実行したりすることもできます。 

## Intune で管理する方法

### デバイスのカテゴリとグループ
Intune を使用すると、デバイスカテゴリを作成して、エンジニアリング、医療、開発者など、作成したカテゴリに基づいて自動的にデバイスをグループに追加することができます。 これは、Windows ホログラフィック for Business を実行しているデバイスの管理を簡単にすることを目的としています。
詳しくはこちら:[デバイスをグループに分類](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)する

### デバイス構成プロファイル
Intune には、組織内のさまざまなデバイスで有効または無効にできる設定と機能が含まれています。 これらの設定と機能は、プロファイルを使って管理されます。 たとえば、Cortana を有効にするプロファイルを作成することができます。また、Windows ホログラフィック for Business を実行しているデバイスで Microsoft Defender Smart Screen を使用することもできます。
プロファイルでは、OMA-URI を使って、一部の設定のカスタマイズ、デバイスの制限の作成、仮想プライベートネットワーク (VPN) と Wi-fi の構成を行うことができます。
[構成プロファイル](https://docs.microsoft.com/mem/intune/configuration/device-profiles)と [プロファイルの概要](https://docs.microsoft.com/mem/intune/configuration/device-profile-create)について説明します。

## 管理および構成できる機能の例

MDM を使ってデバイスを管理すると、さまざまな項目を選択できます。 

### Wi-Fi
[Wi-fi 設定](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) は、ワイヤレスネットワーク設定をユーザーとデバイスに割り当てます。 Wi-fi プロファイルを割り当てると、ユーザーは自分の wi-fi を設定することなく、会社の wi-fi にアクセスできます。
[HoloLens 用のネットワークを構成する](hololens-commercial-infrastructure.md)方法については、こちらを参照してください。

### 証明書
[証明書] では、アカウント認証、Wi-fi 認証、VPN 暗号化、および web コンテンツの SSL 暗号化を提供して、セキュリティを向上させることができます。 管理者は、プロビジョニングパッケージを使用して手動でデバイスの証明書を管理できますが、登録から更新と失効までの間に MDM システムを使用して証明書を管理することをお勧めします。 Mdm システムでは、デバイスの登録後にこれらの証明書をデバイスの証明書ストアに自動的に展開することができます (MDM システムでは、Simple Certificate Enrollment Protocol (SCEP) または公開キー暗号化標準 #12 (PKCS # 12)) をサポートしている場合に限ります。 MDM では、現在の証明書の有効期限が切れる前に、登録されているクライアント証明書を照会して削除したり、新しい登録要求をトリガーすることもできます。 

### プロキシ
ほとんどの企業のイントラネットネットワークは、内部トラフィックを管理するためにプロキシを利用します。 HoloLens 2 では、イーサネット接続と Wi-fi 接続用にプロキシサーバーを構成できます。 これらの設定は、VPN 接続には適用されません。 Windows 10 のプロキシ設定の詳細については、「 [NETWORKPROXY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)」を参照してください。

### VPN
多くの場合、組織では VPN を使用して、企業のイントラネット上のアプリとリソースにアクセスします。 HoloLens 2 は SSL VPN 接続をサポートします。これには、Microsoft Store からダウンロード可能なプラグインが必要であり、VPN ベンダーに固有のものである必要があります。 
- 「 [HoloLens での VPN の](hololens-network.md#vpn)詳細」をご覧ください。
- VPN プロファイルの詳細については、 [VPNV2 CSP](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)を参照してください。

### アプリを展開して管理する
Intune を使用すると、Windows ホログラフィック for Business を実行しているデバイスにアプリを追加できます。 MDM ソリューションを使用すると、IT の意思決定者や管理者は、社内、基幹業務のアプリをプライベートに自動インストール (プッシュ) することができます。また、ユーザーのグループに対してストアを通じてアプリを購入することもできます。 アプリを展開するには、次のようなさまざまな方法があります。
-   [Intune と会社のポータル]( app-deploy-intune.md)
-   [ビジネス向け Microsoft Store]( app-deploy-store-business.md)

詳しくは、「Intune によるアプリの管理」をご覧ください。
-   [Intune にアプリを追加する](https://docs.microsoft.com/mem/intune/apps/apps-add)
-   [Microsoft Store アプリを追加する](https://docs.microsoft.com/mem/intune/apps/store-apps-windows)
-   [作成したアプリを追加する](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
- [アプリをグループに割り当てる](https://docs.microsoft.com/mem/intune/apps/apps-deploy)

### ソフトウェアの更新プログラム
Intune には、Windows 10 デバイスの更新リングという機能が含まれています。 これらの更新リングには、更新プログラムのインストール方法を決定する一連の設定が含まれています。 たとえば、更新プログラムをインストールするためのメンテナンス期間を作成することも、更新プログラムのインストール後に再起動することもできます。 更新リングは、Windows ホログラフィック for Business が実行されている複数のデバイスに適用できます。
「HoloLens の更新を [管理](hololens-updates.md) する方法」と「 [Intune でソフトウェアの更新プログラムを管理](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)する方法」を参照してください。

### キオスク モードを構成する
Intune で利用可能な共有またはゲストの PC 機能を使用すると、Windows ホログラフィックを構成して、ビジネスデバイスをキオスクとして実行することができます。 これらのデバイスは、1つのアプリ (単一アプリのキオスクモード) を実行するか、複数のアプリ (マルチアプリキオスクモード) を実行できます。 キオスクモードは、既定でどのアプリにどの id がアクセスできるかを制御するための UI です。
[HoloLens をキオスクとして]( hololens-kiosk.md)セットアップする方法について説明します。

