---
title: 商用環境での HoloLens のセットアップ
description: エンタープライズ環境での HoloLens の展開と管理について説明します。
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
ms.openlocfilehash: 082064acd075451e7a8d55352249a0776cd19d76
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253214"
---
# HoloLens 2 Enterprise の展開と管理

この概要は、企業内での Microsoft HoloLens 2 デバイスの展開と管理に関する考慮事項を IT 担当者が理解するのに役立ちます。

HoloLens 2 は Windows 10 Holographic で動作し、堅牢で柔軟な組み込みモバイル デバイスとアプリ管理テクノロジを組織に提供します。 Windows 10 Holographic では、エンドツーエンドのデバイス ライフサイクル管理がサポートされ、企業はデバイス、データ、アプリを制御できます。 HoloLens 2 は、包括的なモバイル デバイス管理ソリューションを使用して、デバイスの登録、構成、アプリケーション管理から保守とサポートのサポートまで、標準的なライフサイクル プラクティスに簡単に組み込むできます。

## 準備

HoloLens 2 を企業のエンタープライズ環境に展開する準備をする際には、HoloLens 2 のスケール展開の計画を開始する際に、いくつかの考慮事項を確認して理解する必要があります。

### Infrastructure Essentials

企業エンタープライズ展開シナリオでの HoloLens 2 には、完全な機能セットをサポートするために必要な特定の重要なインフラストラクチャ サービスがあります。 HoloLens 2 は、展開と管理を行 [う最新のモバイル](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) デバイス管理を念頭に置いて構築されました。 Azure AD増加するモバイル要員を実現するための主要な手段として、参加と MDM を使用します。 以下のトピックでは、HoloLens 2 の展開計画で考慮する必要がある各インフラストラクチャ コンポーネントの概要について説明します。

### Azure Active Directory
Azure AD は、ID とアクセス管理を提供する、クラウド ベースのディレクトリ サービスです。 既存のオンプレミスのディレクトリと統合して、ハイブリッドの ID ソリューションを作成できます。 Microsoft Office 365 または Intune を使用している組織は、既に Azure AD を使用しています。このエディションには、Free、Premium P1、Premium P2 の 3 つのエディションがあります [(Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions/)エディションを参照)。 すべてのエディションで Azure ADデバイスの登録がサポートされますが、MDM の自動登録を有効にするには Premium P1 が必要です。 HoloLens 2 では、ほとんどのエンタープライズ レベルの機能を有効にするには、Azure Active Directory Join が必要です。

> [!NOTE]
> HoloLens 2 では、オンプレミスの Active Directory 参加はサポートされていません。

### モバイル デバイス管理
HoloLens 2 は、企業環境のモバイル デバイス管理 (MDM) システムによって管理するように特別に設計されています。 Enterprise Mobility + Security の一部である Microsoft [Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune)は、企業内のデバイスを管理するクラウドベースの MDM システムです。 Office 365 と同様に、Intune は ID 管理に Azure AD を使用します。そのため、従業員は Intune にデバイスを登録するために使用する資格情報と同じ資格情報を使用して、Office 365 にサインインします。 複数の MDM システムが Windows 10 をサポートしており、ほとんどは、個人のデバイスおよび企業のデバイスの展開のシナリオをサポートしています。 MDM システムでは、HoloLens 2 のアプリケーションの展開と更新も管理できます。 現在、HoloLens 2 をサポートする MDM プロバイダーには、AirWatch、MobileIron などが含まれます。 すべての MDM システム ベンダーは、Windows 10 デバイス管理構成サービス プロバイダー (CSP) に同じようにアクセスできます。IT 組織は、Microsoft Intune またはサード パーティ製の MDM 製品のどちらでも、管理要件に最も適したシステムを自由に選択できます。

> [!NOTE]
> System Center Configuration Manager のような従来のオンプレミス PC 管理システムは、HoloLens 2 ではサポートされていません。

### Windows Update for Business
Windows Update for Business は、IT 管理者に対して Windows Update を中心とした追加の管理機能を提供するように設計されています。これには、更新プログラムをデバイスのグループに展開する機能や、更新プログラムをインストールするためのメンテナンス ウィンドウを定義する機能などが含まれています。 HoloLens 2 の更新プログラムの管理の詳細については、こちらをご覧 [ください](https://docs.microsoft.com/hololens/hololens-updates)。

### 証明書
HoloLens 2 は、環境で Corp Wi-Fi ネットワーク認証の証明書や他のリソースへのアクセスが必要な場合に、MDM を介した証明書の展開をサポートします。 HoloLens 2 への証明書の展開を有効にするには、一部の MDM インフラストラクチャ構成が必要になる場合があります。 [HoloLens 2 の証明書とネットワーク](https://docs.microsoft.com/hololens/hololens-certificates-network)プロファイルを準備する方法についてお読みください。 Intune の詳細については、こちらをご [覧ください](https://docs.microsoft.com/mem/intune/protect/certificates-configure)。

## 構成

MDM 管理者は、MDM システムに登録されている企業デバイスにポリシー設定を定義して実装できます。 使用する構成設定は、展開シナリオによって異なります。 Windows 10 では、構成サービス プロバイダー (CSP) は、デバイスの構成設定を読み取り、設定、変更、または削除するインターフェイスです。 これらの設定は、レジストリ キーまたはファイルにマップされます。 HoloLens 2 用の Windows 10 デバイス管理の CSP について詳しくは [、HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)デバイスでサポートされている CSP の一覧をご覧ください。

HoloLens 2 では、カスタム プロビジョニング パッケージによる CSP 構成の制限付きセットの設定もサポートされています。 プロビジョニング パッケージは、通常、MDM 以外の管理対象デバイスで利用され、各デバイスに手動で適用する必要があります。 カスタム プロビジョニング パッケージの構築に関する詳細については、こちらを参照 [してください](https://docs.microsoft.com/hololens/hololens-provisioning)。

> [!NOTE]
> HoloLens 2 は [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)をサポートし、企業の Windows 10 デバイス構成を管理するための簡単で簡単なプロセスを提供します。

### ID 管理

従業員は 1 つのアカウントのみを使用してデバイスを初期化できます。そのため&#39;アカウントを最初に制御する必要が生じません。 選択したアカウントによって、デバイスを制御するユーザーが決まり、管理機能に影響があります。 HoloLens 2 は、ローカル ユーザー アカウント、個人用 Microsoft アカウント、Azure Active Directory アカウントの 3 種類のアカウントをサポートしています。 エンタープライズ ID 管理ソリューションには Azure Active Directory を活用することを強くお勧めします。HoloLens 2 デバイスですべての機能が有効になります。 HoloLens 2 の ID に関する詳細については、こちらを参照 [してください](https://docs.microsoft.com/hololens/hololens-identity)。

### ネットワークと接続

HoloLens 2 はクラウド ファースト デバイスであり、すべての機能を利用するにはオンライン リソースへのネットワーク アクセスが必要です。 企業イントラネット ネットワークに接続された HoloLens 2 デバイスを展開する場合は、HoloLens 2 クラウド サービスへのアクセスを許可するためにプロキシ/ファイアウォールの規則を更新する必要があります。 HoloLens 2 オペレーティング システムに必要な一般的なエンドポイントの一覧については、こちらを参照 [してください](https://docs.microsoft.com/hololens/hololens-offline)。 アプリケーションまたは他のクラウド サービスを HoloLens 2 で正常に実行するには、追加のエンドポイントへのアクセスが必要になる場合があります。

追加のエンドポイント アクセスを必要とする一般的な HoloLens 2 サービスは次のとおりです。

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [D365 ガイド](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 リモート アシスト (O365 Teams インフラストラクチャ)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### 証明書の展開

組織内の企業の Wi-Fi ネットワークまたは他のサービスへのアクセスに証明書が必要な場合、HoloLens 2 は MDM によるユーザー証明書とデバイス証明書の展開をサポートします。 注: MDM ソリューションでは、Windows 10 デバイスに証明書を展開するために追加のインフラストラクチャ構成が必要な場合があります。

### セキュリティ レビュー

ほとんどのエンタープライズ IT 部門では、企業のエンタープライズ ネットワークに展開される新しいデバイスの評価とレビューが必要です。 組織で HoloLens 2 のセキュリティ レビューが必要な場合は、セキュリティ承認の取得に役立つ詳細情報 [を参照してください](https://docs.microsoft.com/hololens/security-overview)。

### HoloLens 2 デバイスの共通設定

企業のエンタープライズ環境に HoloLens 2 デバイスを展開する場合、HoloLens 2 の展開を計画する際に考慮できる一般的なデバイス構成が多数ある可能性があります。 この一覧では、非常に一般的な構成と設定が強調表示され、使用可能なオプションの完全な一覧は構成されません。

| デバイス設定 | 簡単な説明。                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [ハードウェアの制限](hololens-requirements.md#hardware-restrictions)               | ハードウェアの制限により、接続性が低下し、データ保護が支援されます。                        |
| [Wi-Fi プロファイル](hololens-requirements.md#wi-fi-profiles)               | ユーザーWi-Fi操作を行わずに、ユーザー プロファイルを構成します。                              |
| [証明書](hololens-requirements.md#certificates-1)               | Web コンテンツの認証、VPN Wi-Fi SSL 暗号化のアカウントや暗号化を提供します。 |
| [プロキシ](hololens-requirements.md#proxy)              | 内部トラフィックを管理します。                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | 会社のイントラネット上のアプリとリソースへのアクセスを制御します。                               |
| [Kiosk Mode (キオスク モード)](hololens-requirements.md#kiosk-mode) | UI を介してユーザーに表示されるアプリケーションを制限します。 |

#### ハードウェアの制限

HoloLens 2 は、カメラ、マイク、スピーカー、USB インターフェイス、Bluetooth インターフェイス、Wi-Fi などの一般的なハードウェア機能を含む最新のテクノロジを使用します。 ハードウェアの制限を使って、これらの機能の利用を制御できます。

次に、ハードウェアの制限を構成するために HoloLens 2 がサポートする最も一般的に使用される MDM 設定を示します。 これらのハードウェアの制限の中には、接続の提供とデータ保護をサポートするものもあります。

- [**WiFi を許可する:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) ユーザーがデバイスでデバイスのWi-Fiを有効にして使用できるかどうかを指定します。
- [**USB 接続を許可します。**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) USB 接続を有効にするかどうかを指定します (&#39;USB 充電には影響しません)
- [**許可Bluetooth:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) ユーザーがデバイスでデバイスのBluetoothを有効にして使用できるかどうかを指定します。

その他の一般的なデバイス [の制限について詳しくは、以下を参照してください。](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### Wi-Fi プロファイル

多くの企業の Wi-Fi ネットワークは、ユーザー アクセスの制限とセキュリティ保護のため、証明書とその他の複雑な情報を必要とします。 この高度Wi-Fi情報は、一般的なユーザーが構成することは困難ですが、MDM システムでは、ユーザーの介入なしにこれらのWi-Fiプロファイルを完全に構成できます。 複数の Wi-Fi プロファイルを MDM システムで作成できます。

Windows 10 のデバイスWi-Fi詳細については [、「Enterprise Profile WiFi settings」を参照してください](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)。

#### 証明書

証明書は、アカウント認証、認証、VPN 暗号化Wi-Fi、Web コンテンツの SSL 暗号化を提供することで、セキュリティを向上させるのに役立ちます。 管理者はプロビジョニング パッケージを使用してデバイス上の証明書を手動で管理することができますが、登録から更新、失効まで、MDM システムを使用してそれらの証明書をライフサイクル全体にわたって管理するベスト プラクティスは&#39;です。 MDM システムは、デバイスの登録後に、これらの証明書をデバイス&#39; 証明書ストアに自動的に展開できます (MDM システムが簡易証明書登録プロトコル (SCEP) または公開キー暗号化標準 #12 (PKCS#12) をサポートしている場合)。 MDM では、現在の証明書の有効期限が切る前に、登録済みクライアント証明書を照会および削除したり、新しい登録要求をトリガーしたりすることもできます。

[HoloLens 2 の証明書とネットワーク](https://docs.microsoft.com/hololens/hololens-certificates-network)プロファイルを準備する方法について詳しくは、以下をご覧ください。

#### プロキシ

ほとんどの企業イントラネット ネットワークは、プロキシを利用して内部トラフィックを管理します。 HoloLens 2 を使用すると、イーサネット接続およびネットワーク接続用のプロキシ Wi-Fi構成できます。 これらの設定は、VPN 接続には適用されません。

Windows 10 のプロキシ設定について詳しくは [、「NetworkProxy CSP」をご覧ください](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)。

#### VPN

多くの場合、組織は VPN を使用して、企業のイントラネット上のアプリやリソース&#39;制御します。 HoloLens 2 は SSL VPN 接続をサポートしています。SSL VPN 接続には、Microsoft Store からダウンロード可能なプラグインが必要であり、お好きな VPN ベンダーに固有のプラグインが必要です。

VPN プロファイルについて詳しくは、「[VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)」をご覧ください。

#### Kiosk Mode (キオスク モード)

キオスク モードで実行するデバイスを構成することで、HoloLens 2 デバイスを固定用途デバイス (キオスクとも呼ばれる) として機能するために構成できます。 キオスク モードでは、デバイスで利用可能なアプリケーション (またはユーザー) が制限されます。 キオスク モードは、HoloLens 2 デバイスをビジネス アプリ専用にしたり、アプリ デモで HoloLens 2 デバイスを使用したりするために使用できる便利な機能です。

キオスク モードでの HoloLens 2 の構成の詳細については、「キオスクとしての[HoloLens](https://docs.microsoft.com/hololens/hololens-kiosk)のセットアップ」を参照してください。

## 展開

### MDM デバイスの登録

エンタープライズ展開の場合は、Azure AD[](https://docs.microsoft.com/hololens/hololens-enroll-mdm)への参加と自動 MDM 登録 (Azure AD + MDM) でのみ、デバイスを企業のデバイスとして MDM に登録するようにお勧めします。 これには Azure AD Premium が必要であり、Intune を含むいくつかの MDM プロバイダーへの自動登録をサポートします。

自己展開登録方法 [Autopilot について詳しくは、以下を参照してください](https://docs.microsoft.com/hololens/hololens2-autopilot)。

### アプリケーションの展開

多くの場合、モバイル デバイスにおけるユーザーの生産性はアプリによって決まります。

Windows 10 は、Windows アプリ用のユニバーサル Windows プラットフォーム (UWP) を使用して、複数のデバイスでシームレスに動作するアプリの開発を可能にします。

HoloLens 2 デバイスにアプリケーションを展開する方法は複数あります。 アプリは、MDM、ビジネス向け Microsoft Store を通じて直接展開するか、プロビジョニング パッケージを通じてサイドロードすることができます。 アプリ [の展開に関する詳細については、こちらを参照してください](https://docs.microsoft.com/hololens/app-deploy-overview)。

> [!NOTE]
> HoloLens 2 では、UWP ARM64 アプリの実行のみをサポートしています。

## 保守

企業の IT 環境では、最新の技術をユーザーに提供したいという考えと、セキュリティおよびコスト管理のニーズのバランスを取る必要があります。 サイバー攻撃は日常的に行われているので、Windows 10 デバイスの状態を適切に維持することが重要です。 IT は、コンプライアンスから逸脱しないように構成設定を管理し、内部アプリケーションにアクセスできるデバイスを厳格に設定する必要があります。 HoloLens 2 は、デバイスが企業ポリシーに準拠するために必要なモバイル操作管理機能を提供します。

### OS サービス オプション

**合理化されたアップデート プロセス**

Microsoft は Windows 製品のエンジニアリングとリリースのサイクルを合理化し、市場から要求された新しい機能、エクスペリエンス、機能性を、これまでで最も迅速に提供できるようになりました。 Microsoft は、1 年 (12 か月の期間) あたり 2 回の機能更新プログラムを提供することを計画しています。 **機能更新プログラム** は Current Branch または CB を確立し、関連付けられたバージョンを持つ。

Microsoft は、セキュリティと安定性のための更新プログラムを HoloLens 2 デバイスに直接配信してインストールします。 これらの **品質更新プログラム** は、Windows Update 経由で Microsoft の管理下でリリースされ、毎月提供されます。 HoloLens 2 は、同じ標準の更新プロセスの一部として機能更新プログラムと品質更新プログラムを使用します。

企業のお客様は、MDM システムを使って HoloLens 2s の更新エクスペリエンスとプロセスを管理できます。 ほとんどの場合、更新プロセスを管理するポリシーは、機能更新プログラムと品質更新プログラムの両方に適用されます。 [HoloLens 更新プログラムの MDM の構成に関する詳細](https://docs.microsoft.com/hololens/hololens-updates)。

### アプリケーションの管理

IT 管理者は、HoloLens 2 にインストールできるアプリと、アプリを最新の状態に保つ方法を制御できます。

HoloLens 2 は Windows Defender [Application Control (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)をサポートしています。これにより、管理者は Microsoft Store からアプリの一覧を作成、許可、または禁止できます。 この機能は、組み込みのアプリにも拡張されます。 アプリを許可または拒否する機能は、ユーザーが意図した目的のためにデバイスを使用することを保証するのに役立ちます。 しかし、従業員が必要とする、または要求するアプリとセキュリティ上の考慮事項とのバランスを見つけることは、必ずしも容易ではありません。 許可リストまたは拒否リストを作成するには、Microsoft Store で変化するアプリの状況に対応する必要もあります。

詳細については、「アプリケーション制御 [CSP」を参照してください](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)。

### 廃棄

デバイスのサポートは、デバイスのライフサイクルの最後のフェーズです。 新&#39;に置き換えられるデバイスは、データの機密性を損なう可能性のある破棄されたデバイスに会社のデータを残さ&#39;したくないので、安全に廃棄することが重要です。 また、IT 部門では、紛失した、または盗難に遭ったデバイスをワイプする必要があるユーザーを適切にサポートする方法も必要です。

HoloLens 2 は、デバイスをワイプする 3 つの方法をサポートしています

**MDM ファクトリ ワイプ:** 管理者が開始した MDM コマンドを使って HoloLens 2 を工場出荷時のイメージにリセットします。 デバイスに保存されているデータをすべて消去します。

**[設定] 内からのデバイスのリセット:** エンド ユーザーは、デバイスの設定アプリ内で HoloLens 2 を手動でリセットできます。 デバイスに保存されているデータをすべて消去します。

**Advanced Recovery Companion (ARC):** ARC ツールを実行している PC から、ユーザーまたは管理者は USB ケーブルを介して PC に接続された HoloLens 2 をフラッシュできます。 デバイスに保存されているデータをすべて消去します。

> [!div class="nextstepaction"]
> [一般的な展開シナリオ](common-scenarios.md)