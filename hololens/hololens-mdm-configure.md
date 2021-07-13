---
title: Microsoft のエンドポイントマネージャー Intune を使用した HoloLens デバイスの管理
description: MDM を使用して、Intune を使用して大規模な HoloLens 混在した現実デバイスを構成する方法について説明します。
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
ms.openlocfilehash: 5485a4b2558a11a6c0545ec8b3405c120cff287c
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640281"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a>Microsoft のエンドポイントマネージャー Intune を使用した HoloLens デバイスの管理

MDM を使用して管理できるさまざまな設定があります。 Intune デバイスを使用すると、グループ化して、ユーザーまたはデバイスのグループに構成を展開することができます。 また、アプリを展開および管理したり、ネットワークに接続するようにデバイスを設定したり、必要な時点で更新プログラムが必要になったときに実行するように構成したりすることもできます。 

## <a name="how-to-manage-via-intune"></a>Intune を使用して管理する方法

### <a name="device-categories-and-groups"></a>デバイスのカテゴリとグループ
Intune を使用すると、デバイスカテゴリを作成して、作成したカテゴリ (エンジニアリング、医療、開発者など) に基づいてデバイスを自動的にグループに追加することができます。 このようにカテゴリを利用することで、Windows Holographic for Business を実行しているデバイスの管理が簡単になります。
詳細:[デバイスをグループに分類](/mem/intune/enrollment/device-group-mapping)する

### <a name="device-configuration-profiles"></a>デバイスの構成プロファイル
Intune には、組織内のさまざまなデバイスで有効または無効にできる設定と機能が含まれています。 これらの設定と機能は、プロファイルを使用して管理されます。 たとえば、Cortana を有効にするプロファイルや、Windows Holographic for Business を実行しているデバイスで Microsoft Defender SmartScreen を使用するプロファイルを作成できます。
プロファイルでは、OMA-URI を使用し、一部の設定をカスタマイズしたり、デバイス制限を作成したり、VPN (仮想プライベート ネットワーク) や Wi-Fi を構成したりできます。
まず、[構成プロファイル](/mem/intune/configuration/device-profiles)とプロファイルの[概要](/mem/intune/configuration/device-profile-create)を確認します。

## <a name="examples-of-what-can-be-managed-and-configured"></a>管理および構成できるものの例

MDM を使用してデバイスを管理すると、さまざまな項目を選択できます。 

### <a name="wi-fi"></a>Wi-Fi
[Wi-Fi 設定](/mem/intune/configuration/wi-fi-settings-configure)は、ユーザーとデバイスにワイヤレス ネットワーク設定を割り当てます。 Wi-Fi プロファイルを割り当てると、ユーザーは自分で構成しなくても、会社の Wi-Fi にアクセスできるようになります。
[HoloLens 用にネットワークを構成する](hololens-commercial-infrastructure.md)方法について説明します。

### <a name="certificates"></a>証明書
証明書は、アカウント認証、Wi-Fi 認証、VPN 暗号化、web コンテンツの SSL 暗号化を提供することで、セキュリティを強化するのに役立ちます。 管理者はパッケージをプロビジョニングすることによってデバイスの証明書を手動で管理できますが、ベストプラクティスとして、MDM システムを使用して、証明書をライフサイクル全体にわたって管理することをお勧めします。これは、更新と失効による登録からです。 Mdm システムは、デバイスを登録した後に、デバイスの証明書ストアにこれらの証明書を自動的に展開できます (MDM システムが Simple Certificate Enrollment Protocol (SCEP) または公開キー暗号化標準 #12 (PKCS # 12)) をサポートしている必要があります。 また、MDM では、登録されているクライアント証明書を照会して削除したり、現在の証明書の有効期限が切れる前に新しい登録要求をトリガーしたりできます。 

### <a name="proxy"></a>Proxy (プロキシ)
ほとんどの企業イントラネットネットワークは、プロキシを利用して内部トラフィックを管理します。 HoloLens 2 では、イーサネットおよび Wi-Fi 接続用のプロキシサーバーを構成できます。 これらの設定は、VPN 接続には適用されません。 Windows 10 のプロキシ設定の詳細については、「 [networkproxy CSP](/windows/client-management/mdm/networkproxy-csp)」を参照してください。

### <a name="vpn"></a>VPN
多くの場合、組織では VPN を使用して、企業のイントラネット上のアプリとリソースにアクセスします。 HoloLens 2 は、Microsoft Store からダウンロード可能なプラグインを必要とし、任意の VPN ベンダーに固有の SSL VPN 接続をサポートしています。 
- VPN の詳細については[HoloLens を](hololens-network.md#vpn)参照してください。
- VPN プロファイルの詳細については、「 [VPNV2 CSP](/windows/client-management/mdm/vpnv2-csp)」を参照してください。

### <a name="deploy-and-manage-apps"></a>アプリの展開と管理
Intune を使用し、Windows Holographic for Business を実行しているデバイスにアプリを追加できます。 MDM ソリューションを使用すると、IT の意思決定者および管理者は、社内の基幹業務アプリをプライベートに自動インストール (プッシュ) したり、ストアを介してユーザーのグループに対してアプリを購入したりすることができます。 アプリは次のようなさまざまな方法でデプロイできます。
-   [Intune とポータルサイト]( app-deploy-intune.md)
-   [ビジネス向け Microsoft ストア]( app-deploy-store-business.md)

Intune を使用したアプリ管理の詳細については、こちらをご覧ください。
-   [Intune にアプリを追加する](/mem/intune/apps/apps-add)
-   [Microsoft Store のアプリを追加する](/mem/intune/apps/store-apps-windows)
-   [自分で開発したアプリを追加する](/mem/intune/apps/lob-apps-windows)
- [アプリをグループに割り当てる](/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a>ソフトウェア更新プログラム
Intune には、Windows 10 デバイス用に、更新プログラム リングと呼ばれている機能があります。 更新プログラム リングには、更新プログラムのインストール方法を決定する一連の設定が含まれています。 たとえば、更新プログラムをインストールするためのメンテナンス期間を作成したり、更新プログラムのインストール後に再起動を選択したりできます。 更新プログラム リングは、Windows Holographic for Business を実行している複数のデバイスに適用できます。
詳細については、Intune を使用して[HoloLens 更新プログラムを管理](hololens-updates.md)し、[ソフトウェア更新プログラムを管理](/mem/intune/protect/windows-update-for-business-configure)する方法を参照してください。

### <a name="configure-kiosk-mode"></a>キオスク モードを構成する
Intune で利用できる共有またはゲスト PC 機能を利用し、キオスクとして実行されるように Windows Holographic for Business デバイスを構成できます。 キオスクとして構成したデバイスでは、1 つのアプリを実行するか (シングルアプリ キオスク モード)、複数のアプリを実行できます (マルチアプリ キオスク モード)。 キオスクモードは、どの id が既定でどのアプリにアクセスできるかを制御するための UI です。
[キオスクとして HoloLens を設定]( hololens-kiosk.md)する方法について説明します。

