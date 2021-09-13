---
title: Microsoft の エンドポイント マネージャー Intune を使用してデバイスHoloLensする
description: MDM を使用して、Intune を使用して大規模な複合現実デバイスHoloLens CSP、ポリシー、管理を構成する方法について説明します。
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033188"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a>Microsoft の エンドポイント マネージャー Intune を使用してデバイスHoloLensする

MDM を使用して管理できるさまざまな設定があります。 Intune デバイスを使用してグループ化し、それらのユーザーまたはデバイスのグループに構成を展開できます。 アプリを展開して管理し、ネットワークに接続するデバイスを設定し、必要な時点と必要な更新リングで更新プログラムを構成することもできます。 

## <a name="how-to-manage-via-intune"></a>Intune を使用して管理する方法

### <a name="device-categories-and-groups"></a>デバイスのカテゴリとグループ
Intune を使用すると、デバイス カテゴリを作成して、作成したカテゴリ (エンジニアリング、医療、開発者など) に基づいてデバイスをグループに自動的に追加できます。 このようにカテゴリを利用することで、Windows Holographic for Business を実行しているデバイスの管理が簡単になります。
詳細については、以下を参照 [してください。デバイスをグループに分類する](/mem/intune/enrollment/device-group-mapping)

### <a name="device-configuration-profiles"></a>デバイスの構成プロファイル
Intune には、組織内のさまざまなデバイスで有効または無効にできる設定と機能が含まれています。 これらの設定と機能は、プロファイルを使用して管理されます。 たとえば、Cortana を有効にするプロファイルや、Windows Holographic for Business を実行しているデバイスで Microsoft Defender SmartScreen を使用するプロファイルを作成できます。
プロファイルでは、OMA-URI を使用し、一部の設定をカスタマイズしたり、デバイス制限を作成したり、VPN (仮想プライベート ネットワーク) や Wi-Fi を構成したりできます。
[概要プロファイル、およびプロファイルの概要](/mem/intune/configuration/device-profiles)に関 [するページを参照してください](/mem/intune/configuration/device-profile-create)。

## <a name="examples-of-what-can-be-managed-and-configured"></a>管理と構成が可能な例

MDM を使用してデバイスを管理すると、さまざまな項目を選択できます。 

### <a name="wi-fi"></a>Wi-Fi
[Wi-Fi 設定](/mem/intune/configuration/wi-fi-settings-configure)は、ユーザーとデバイスにワイヤレス ネットワーク設定を割り当てます。 ユーザープロファイルを割り当Wi-Fi、ユーザーは自分で構成することなく、Wi-Fi企業アカウントにアクセスできます。
ネットワークの構成[の詳細については、次を参照HoloLens](hololens-commercial-infrastructure.md)

### <a name="certificates"></a>証明書
証明書は、Web コンテンツのアカウント認証、Wi-Fi VPN 暗号化、SSL 暗号化を提供することで、セキュリティを向上させるのに役立ちます。 管理者はプロビジョニング パッケージを使用してデバイス上の証明書を手動で管理することができますが、MDM システムを使用して、登録から更新、失効まで、ライフサイクル全体を通してそれらの証明書を管理するベスト プラクティスです。 MDM システムでは、デバイスの登録後に、これらの証明書をデバイスの証明書ストアに自動的に展開できます (MDM システムが Simple Certificate Enrollment Protocol (SCEP) または公開キー暗号化標準 #12 (PKCS #12) をサポートしている限り)。 MDM では、登録されたクライアント証明書の照会と削除、または現在の証明書の有効期限が切る前に新しい登録要求をトリガーすることもできます。 

### <a name="proxy"></a>プロキシ
ほとんどの企業イントラネット ネットワークでは、プロキシを利用して内部トラフィックを管理します。 このHoloLens 2、イーサネット接続とネットワーク接続用にプロキシ サーバーWi-Fiできます。 これらの設定は、VPN 接続には適用されません。 アプリケーションのプロキシ設定の詳細については[、「NetworkProxy CSP Windows 10」を参照してください](/windows/client-management/mdm/networkproxy-csp)。

### <a name="vpn"></a>VPN
多くの場合、組織では VPN を使用して、企業のイントラネット上のアプリとリソースにアクセスします。 HoloLens 2 SSL VPN 接続がサポートされています。この接続では、Microsoft Store からダウンロード可能なプラグインが必要であり、選択した VPN ベンダーに固有です。 
- 詳細については、 の[VPN に関するページHoloLens。](hololens-network.md#vpn)
- VPN プロファイルの詳細については [、VPNv2 CSP に関するページを参照してください](/windows/client-management/mdm/vpnv2-csp)。

### <a name="deploy-and-manage-apps"></a>アプリの展開と管理
Intune を使用し、Windows Holographic for Business を実行しているデバイスにアプリを追加できます。 MDM ソリューションを使用すると、IT の意思決定者と管理者は、企業内の業務アプリを非公開で自動インストール (プッシュ) したり、ユーザー グループのストアを通じてアプリを購入したりすることができます。 アプリは次のようなさまざまな方法でデプロイできます。
-   [Intune と ポータル サイト]( app-deploy-intune.md)
-   [ビジネス向け Microsoft ストア]( app-deploy-store-business.md)

Intune を使用したアプリ管理の詳細を確認します。
-   [Intune にアプリを追加する](/mem/intune/apps/apps-add)
-   [Microsoft Store のアプリを追加する](/mem/intune/apps/store-apps-windows)
-   [自分で開発したアプリを追加する](/mem/intune/apps/lob-apps-windows)
- [アプリをグループに割り当てる](/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a>ソフトウェア更新プログラム
Intune には、Windows 10 デバイス用に、更新プログラム リングと呼ばれている機能があります。 更新プログラム リングには、更新プログラムのインストール方法を決定する一連の設定が含まれています。 たとえば、更新プログラムをインストールするためのメンテナンス期間を作成したり、更新プログラムのインストール後に再起動を選択したりできます。 更新プログラム リングは、Windows Holographic for Business を実行している複数のデバイスに適用できます。
詳細については、「Intune で更新プログラムを管理[HoloLensソフトウェア](hololens-updates.md)更新プログラム[を管理する」を参照してください](/mem/intune/protect/windows-update-for-business-configure)。

### <a name="configure-kiosk-mode"></a>キオスク モードを構成する
Intune で利用できる共有またはゲスト PC 機能を利用し、キオスクとして実行されるように Windows Holographic for Business デバイスを構成できます。 キオスクとして構成したデバイスでは、1 つのアプリを実行するか (シングルアプリ キオスク モード)、複数のアプリを実行できます (マルチアプリ キオスク モード)。 キオスク モードは、既定でどのアプリにアクセスできる ID を制御するための UI です。
キオスクとして[アプリをHoloLensする方法について説明します]( hololens-kiosk.md)

