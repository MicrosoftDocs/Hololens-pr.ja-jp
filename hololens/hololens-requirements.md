---
title: 商用環境での HoloLens のセットアップ
description: インフラストラクチャ、azure active directory、モバイルデバイス管理など、エンタープライズ環境での HoloLens のデプロイと管理の詳細について説明します。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
ms.reviewer: aboeger
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: e6aebfca076294de34068cd075d954220d7f4686
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397223"
---
# <a name="hololens-2-enterprise-deployment-and-management"></a>HoloLens 2 エンタープライズ展開と管理

この概要は、IT プロフェッショナルが企業内で Microsoft HoloLens 2 デバイスを展開および管理する際の考慮事項を理解できるようにすることを目的としています。

HoloLens 2 は Windows 10 Holographic 上で実行され、堅牢で柔軟性に富んだ、モバイルデバイスおよびアプリ管理テクノロジを組織に提供します。 Windows 10 Holographic は、エンドツーエンドのデバイスライフサイクル管理をサポートしており、企業がデバイス、データ、およびアプリを管理できるようにします。 HoloLens 2 は、包括的なモバイルデバイス管理ソリューションを使用して、デバイスの登録、構成、アプリケーションの管理からメンテナンスや提供終了まで、標準的なライフサイクルプラクティスに簡単に組み込むことができます。

## <a name="prepare"></a>準備

HoloLens 2 を企業のエンタープライズ環境に展開する準備をする際には、HoloLens 2 のスケール展開の計画を開始する際に確認して理解する必要がある考慮事項がいくつかあります。

### <a name="infrastructure-essentials"></a>インフラストラクチャの要点

企業のエンタープライズ展開シナリオにおける HoloLens 2 では、すべての機能をサポートするために必要不可欠なインフラストラクチャサービスがいくつかあります。 HoloLens 2 は、展開と管理のために、 [最新のモバイルデバイス管理](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) を念頭に置いて構築されています。 Azure AD Join + MDM は、増え続けるモバイルワーカーで実現するための主な手段となります。 以下のトピックでは、HoloLens 2 の展開計画で考慮する必要がある各インフラストラクチャコンポーネントの概要について説明します。

### <a name="azure-active-directory"></a>Azure Active Directory
Azure AD は、ID とアクセス管理を提供する、クラウド ベースのディレクトリ サービスです。 既存のオンプレミスのディレクトリと統合して、ハイブリッドの ID ソリューションを作成できます。 Microsoft Office 365 または Intune を使用する組織は、既に Azure AD を使用しています。これには、Free、Premium P1、Premium P2 の3つのエディションがあります ( [Azure Active Directory エディション](https://azure.microsoft.com/documentation/articles/active-directory-editions/)を参照)。 すべてのエディションでデバイスの登録 Azure AD サポートされていますが、MDM の自動登録を有効にするには Premium P1 が必要です。 HoloLens 2ほとんどのエンタープライズ レベルAzure Active Directory機能を有効にするには、Join を使用する必要があります。

> [!NOTE]
> オンプレミスの Active Directory 参加は、オンプレミスの Active Directory 参加HoloLens 2。

### <a name="mobile-device-management"></a>モバイル デバイス管理
HoloLens 2は、エンタープライズ環境で Mobile デバイス管理 (MDM) システムによって管理するように特別に設計されています。 Microsoft [Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune)は、Enterprise Mobility + Securityの一部として、企業内のデバイスを管理するクラウドベースの MDM システムです。 Office 365 と同様に、Intune では ID 管理に Azure AD が使用されます。そのため、従業員は Office 365 へのサインインに使用するデバイスを Intune に登録するために同じ資格情報を使用します。 複数の MDM システムが Windows 10 をサポートしており、ほとんどは、個人のデバイスおよび企業のデバイスの展開のシナリオをサポートしています。 MDM システムでは、アプリケーションの展開と更新プログラムを管理HoloLens 2することもできます。 現在、この機能をサポートしている他HoloLens 2 MDM プロバイダーには、AirWatch、MobileIron などが含まれます。 すべての MDM システム ベンダーは、Windows 10 デバイス管理構成サービス プロバイダー (CSP) に対して同じアクセス権を持ち、IT 組織は、Microsoft Intune またはサードパーティの MDM 製品のどちらでも、管理要件に最適なシステムを自由に選択できます。

> [!NOTE]
> System Center 構成マネージャー のような従来のオンプレミスの PC 管理システムは、HoloLens 2 でサポートされていません。

### <a name="windows-update-for-business"></a>Windows Update for Business
Windows Update for Business は、IT 管理者に対して Windows Update を中心とした追加の管理機能を提供するように設計されています。これには、更新プログラムをデバイスのグループに展開する機能や、更新プログラムをインストールするためのメンテナンス ウィンドウを定義する機能などが含まれています。 更新プログラム [の管理の詳細については、HoloLens](https://docs.microsoft.com/hololens/hololens-updates) 更新プログラムのHoloLens 2してください。

### <a name="certificates"></a>証明書
HoloLens 2環境で Corp Wi-Fi ネットワーク認証または他のリソースへのアクセスに証明書が必要な場合は、MDM を使用した証明書の展開がサポートされます。 証明書の展開を有効にするには、MDM インフラストラクチャの構成の一部が必要HoloLens 2。 の証明書とネットワーク[プロファイルを準備する方法についてHoloLens 2。](https://docs.microsoft.com/hololens/hololens-certificates-network) Intune を使用している場合は、認定構成の詳細 [を確認](https://docs.microsoft.com/mem/intune/protect/certificates-configure) してください。

## <a name="configure"></a>構成

MDM 管理者は、MDM システムに登録されている企業デバイスにポリシー設定を定義して実装できます。 使用する構成設定は、デプロイ シナリオによって異なります。 Windows 10 では、構成サービスプロバイダー (CSP) は、デバイスの構成設定を読み取り、設定、変更、または削除するためのインターフェイスです。 これらの設定は、レジストリ キーまたはファイルにマップされます。 HoloLens 2 用の Windows 10 デバイス管理 Csp の詳細については、「 [hololens デバイスでサポートされる csp](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)の完全な一覧」を参照してください。

HoloLens 2 では、カスタムプロビジョニングパッケージを使用して、限定された CSP 構成を設定することもできます。 プロビジョニングパッケージは、通常、MDM 以外の管理対象デバイスに使用され、各デバイスに手動で適用する必要があります。 カスタムプロビジョニングパッケージの構築の詳細については、 [HoloLens プロビジョニング](https://docs.microsoft.com/hololens/hololens-provisioning) のドキュメントを参照してください。

> [!NOTE]
> HoloLens 2 では [Windows 自動操縦](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)がサポートされており、企業の windows 10 デバイス構成を簡単かつ簡単に管理できます。

### <a name="identity-management"></a>ID 管理

従業員は、1つのアカウントを使用してデバイスを初期化することができます。これにより、最初に有効にするアカウントを組織が制御する必要が&#39;ます。 選択したアカウントによって、デバイスを制御するユーザーが決まり、管理機能に影響があります。 HoloLens 2 では、ローカルユーザーアカウント、個人用 Microsoft アカウント、Azure Active Directory アカウントの3種類のアカウントをサポートしています。 HoloLens 2 デバイスですべての機能を有効にするため、エンタープライズ id 管理ソリューションには Azure Active Directory を利用することを強くお勧めします。 HoloLens 2 の Id の詳細については、 [hololens id](https://docs.microsoft.com/hololens/hololens-identity) を確認してください。

### <a name="network-and-connectivity"></a>ネットワークと接続性

HoloLens 2 がクラウドの最初のデバイスであるため、すべての機能を利用するには、オンラインリソースへのネットワークアクセスが必要です。 企業イントラネットネットワークに接続された HoloLens 2 デバイスを展開する場合は、HoloLens 2 クラウドサービスへのアクセスを許可するようにプロキシ/ファイアウォール規則を更新することが必要になる場合があります。 詳細については、「 [HoloLens 2 オペレーティングシステムの一般的なエンドポイント](https://docs.microsoft.com/hololens/hololens-offline)の一覧」を参照してください。 アプリケーションやその他のクラウドサービスが HoloLens 2 で正常に実行されるためには、追加のエンドポイントへのアクセスが必要になる場合があります。

追加のエンドポイントアクセスを必要とする一般的な HoloLens 2 サービスは、次のとおりです。

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [D365 ガイド](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 Remote Assist (O365 Teams インフラストラクチャ)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### <a name="certificate-deployment"></a>証明書の展開

組織内の企業の Wi-Fi ネットワークまたは他のサービスにアクセスするために証明書が必要な場合、HoloLens 2 は MDM を使用したユーザーとデバイスの証明書の展開をサポートします。 注: MDM ソリューションでは、デバイスに証明書を展開するために追加のインフラストラクチャ構成Windows 10があります。

### <a name="security-review"></a>セキュリティ レビュー

ほとんどのエンタープライズ IT 部門では、企業のエンタープライズ ネットワークにデプロイされている新しいデバイスの評価とレビューが必要になります。 組織でセキュリティ レビューが必要HoloLens 2、セキュリティ承認の取得に役立つ詳細 [を確認できます](https://docs.microsoft.com/hololens/security-overview)。

### <a name="common-hololens-2-device-settings"></a>一般的HoloLens 2デバイス設定

企業のHoloLens 2環境にデバイスを展開する場合、HoloLens 2 の展開を計画するときに考慮される可能性がある一般的なデバイス構成が多数HoloLens 2。 この一覧では、非常に一般的な構成と設定が強調表示され、使用可能なオプションの完全な一覧では構成されません。

| デバイス設定 | 簡単な説明。                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [ハードウェアの制限](hololens-requirements.md#hardware-restrictions)               | ハードウェアの制限により、接続性が低下し、データ保護が支援されます。                        |
| [Wi-Fi プロファイル](hololens-requirements.md#wi-fi-profiles)               | ユーザーWi-Fi操作を行わずに、ユーザープロファイルを構成します。                              |
| [証明書](hololens-requirements.md#certificates-1)               | Web コンテンツの認証、VPN 暗号化Wi-Fi SSL 暗号化のアカウントや暗号化を提供します。 |
| [Proxy](hololens-requirements.md#proxy)              | 内部トラフィックを管理する。                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | 会社のイントラネット上のアプリとリソースへのアクセスを制御します。                               |
| [キオスク モード](hololens-requirements.md#kiosk-mode) | UI を介してユーザーに表示されるアプリケーションを制限します。 |

#### <a name="hardware-restrictions"></a>ハードウェアの制限

HoloLens 2は、カメラ、マイク、スピーカー、USB インターフェイス、Bluetooth インターフェイス、Wi-Fi などの一般的なハードウェア機能を含む最先端のテクノロジを使用します。 ハードウェアの制限を使って、これらの機能の利用を制御できます。

次に、HoloLens 2 がハードウェアの制限を構成するためにサポートする最も一般的に使用される MDM 設定を示します。 これらのハードウェアの制限の中には、接続の提供とデータ保護をサポートするものもあります。

- [**WiFi を許可する:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) ユーザーがデバイスで Wi-Fi ラジオを有効にして使用できるかどうか
- [**USB 接続を許可する:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) USB 接続が有効になっているかどうかを示します (USB 充電に影響&#39;ありません)。
- [**Bluetooth を許可する:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) ユーザーがデバイスで Bluetooth ラジオを有効にして使用できるかどうか

その他の[一般的なデバイス制限](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)については、こちらを参照してください。

#### <a name="wi-fi-profiles"></a>Wi-Fi プロファイル

多くの企業の Wi-Fi ネットワークは、ユーザー アクセスの制限とセキュリティ保護のため、証明書とその他の複雑な情報を必要とします。 この高度な Wi-Fi 情報は、一般的なユーザーが構成するのは困難ですが、MDM システムでは、ユーザーの介入なしにこれらの Wi-Fi プロファイルを完全に構成することができます。 複数の Wi-Fi プロファイルを MDM システムで作成できます。

Windows 10 の Wi-Fi 設定の詳細については、「 [Enterprise Profile WiFi settings](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)」を参照してください。

#### <a name="certificates"></a>証明書

証明書は、アカウント認証、Wi-Fi 認証、VPN 暗号化、web コンテンツの SSL 暗号化を提供することで、セキュリティを強化するのに役立ちます。 管理者はパッケージをプロビジョニングすることによってデバイスの証明書を手動で管理できますが、更新と失効による登録から、MDM システムを使用して、ライフサイクル全体にわたって証明書を管理することがベストプラクティスと&#39;ます。 Mdm システムは、デバイスを登録した後に、これらの証明書をデバイス&#39; 証明書ストアに自動的に展開できます (MDM システムで Simple Certificate Enrollment Protocol (SCEP) または公開キー暗号化標準 #12 (PKCS # 12)) がサポートされている必要があります。 また、MDM では、登録されているクライアント証明書を照会して削除したり、現在の証明書の有効期限が切れる前に新しい登録要求をトリガーしたりできます。

[HoloLens 2 の証明書とネットワークプロファイルを準備](https://docs.microsoft.com/hololens/hololens-certificates-network)する方法の詳細については、こちらを参照してください。

#### <a name="proxy"></a>プロキシ

ほとんどの企業イントラネットネットワークは、プロキシを利用して内部トラフィックを管理します。 HoloLens 2 では、イーサネットおよび Wi-Fi 接続用のプロキシサーバーを構成できます。 これらの設定は、VPN 接続には適用されません。

Windows 10 のプロキシ設定の詳細については、「 [Networkproxy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)」を参照してください。

#### <a name="vpn"></a>VPN

組織は多くの場合、VPN を使用して、会社&#39;s イントラネット上のアプリとリソースへのアクセスを制御します。 HoloLens 2 SSL VPN 接続がサポートされています。この接続には、Microsoft Store からのダウンロード可能なプラグインが必要であり、選択した VPN ベンダーに固有です。

VPN プロファイルについて詳しくは、「[VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)」をご覧ください。

#### <a name="kiosk-mode"></a>キオスク モード

キオスク モードで実行HoloLens 2デバイスを構成することで、固定目的のデバイス (キオスクとも呼ばれる) として機能するデバイスを構成できます。 キオスク モードでは、デバイスで使用できるアプリケーション (またはユーザー) が制限されます。 キオスク モードは、HoloLens 2 デバイスをビジネス アプリに割り当て、アプリデモで HoloLens 2 デバイスを使用するために使用できる便利な機能です。

キオスク モードでのデバイスの構成のHoloLens 2については、「キオスクとして [HoloLens をセットアップする」を参照してください。](https://docs.microsoft.com/hololens/hololens-kiosk)

## <a name="deploy"></a>デプロイ

### <a name="mdm-device-enrollment"></a>MDM デバイスの登録

エンタープライズ展開の場合、デバイスを企業デバイス[](https://docs.microsoft.com/hololens/hololens-enroll-mdm)として MDM に登録するには、Azure AD 参加と自動 MDM 登録 (Azure AD + MDM) のみを使用してください。 これには、Azure AD Premiumが必要であり、Intune を含む複数の MDM プロバイダーへの自動登録がサポートされます。

自己展開登録方法 [Autopilot の詳細については、以下を参照してください](https://docs.microsoft.com/hololens/hololens2-autopilot)。

### <a name="application-deployment"></a>アプリケーションのデプロイ

多くの場合、モバイル デバイスにおけるユーザーの生産性はアプリによって決まります。

Windows 10 は、Windows アプリ用のユニバーサル Windows プラットフォーム (UWP) を使用して、複数のデバイスでシームレスに動作するアプリの開発を可能にします。

アプリケーションを複数のデバイスに展開するHoloLens 2があります。 アプリは、MDM を介して直接デプロイするか、ビジネス向け Microsoft Storeを使用してサイドロードすることができます。 詳細については、 [アプリのデプロイに関](https://docs.microsoft.com/hololens/app-deploy-overview) するドキュメントを参照してください。

> [!NOTE]
> HoloLens 2は、UWP ARM64 アプリの実行のみをサポートしています。

## <a name="maintain"></a>管理

企業の IT 環境では、最新の技術をユーザーに提供したいという考えと、セキュリティおよびコスト管理のニーズのバランスを取る必要があります。 サイバー攻撃は日常的に発生する状態になったので、デバイスの状態を適切にWindows 10があります。 IT は、コンプライアンスから逸脱しないように構成設定を管理し、内部アプリケーションにアクセスできるデバイスを厳格に設定する必要があります。 HoloLens 2は、デバイスが企業ポリシーに準拠するために必要なモバイル操作管理機能を提供します。

### <a name="os-servicing-options"></a>OS サービス オプション

**合理化されたアップデート プロセス**

Microsoft は Windows 製品のエンジニアリングとリリースのサイクルを合理化し、市場から要求された新しい機能、エクスペリエンス、機能性を、これまでで最も迅速に提供できるようになりました。 Microsoft は、1 年 (12 か月の期間) あたり 2 回の機能更新プログラムを提供することを計画しています。 **機能更新** プログラムは、Current Branch CB を確立し、関連付けられているバージョンを持つ。

また、Microsoft は、セキュリティと安定性のための更新プログラムをデバイスに直接HoloLens 2します。 これらの **品質更新プログラム** は、Microsoft の管理下Windows Update月次で利用できます。 HoloLens 2 では、同じ標準の更新プロセスの一環として機能更新プログラムと品質更新プログラムが使用されます。

企業のお客様は、MDM システムを使用して、HoloLens 2s での更新エクスペリエンスとプロセスを管理できます。 ほとんどの場合、更新プロセスを管理するポリシーは、機能更新プログラムと品質更新プログラムの両方に適用されます。 詳細につい [ては、「HoloLens の更新用 MDM の構成](https://docs.microsoft.com/hololens/hololens-updates)」を参照してください。

### <a name="managing-applications"></a>アプリケーションの管理

IT 管理者は、HoloLens 2 へのインストールが許可されているアプリと、それらを最新の状態に保つ方法を制御できます。

HoloLens 2 では、 [Windows Defender Application Control (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)がサポートされています。これにより、管理者は、Microsoft Store のアプリの一覧を作成、許可、または禁止できます。 この機能は、組み込みアプリにも拡張されます。 アプリを許可または拒否する機能によって、ユーザーが自分のデバイスを目的どおりに使用できるようになります。 しかし、従業員が必要とする、または要求するアプリとセキュリティ上の考慮事項とのバランスを見つけることは、必ずしも容易ではありません。 許可リストまたは拒否リストを作成するには、Microsoft Store で変化するアプリの状況に対応する必要もあります。

詳細については、「 [Application CONTROL CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)」を参照してください。

### <a name="retire"></a>インベントリから削除

デバイスの廃棄は、デバイスのライフサイクルの最後のフェーズです。 データの機密性を損なう可能性がある破棄されたデバイスに会社のデータを残しておく必要が&#39;ないため、新しいモデルに置き換えられるデバイスは安全に削除されること&#39;重要です。 また、IT 部門では、紛失した、または盗難に遭ったデバイスをワイプする必要があるユーザーを適切にサポートする方法も必要です。

HoloLens 2 では、デバイスをワイプする3つの方法がサポートされています。

**MDM ファクトリワイプ:** 管理者が開始した MDM コマンドを使用して、HoloLens 2 を工場出荷時のイメージに戻します。 デバイスに格納されているすべてのデータを消去します。

**設定内からのデバイスのリセット:** エンドユーザーは、デバイスの設定アプリ内で HoloLens 2 を手動でリセットできます。 デバイスに格納されているすべてのデータを消去します。

**Advanced Recovery コンパニオン (弧):** ARC ツールを実行している PC から、ユーザーまたは管理者は、USB ケーブル経由で PC に接続された HoloLens 2 をフラッシュできます。 デバイスに格納されているすべてのデータを消去します。

> [!div class="nextstepaction"]
> [一般的なデプロイシナリオ](common-scenarios.md)
