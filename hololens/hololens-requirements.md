---
title: 商用環境で HoloLens をセットアップする
description: エンタープライズ環境での HoloLens の展開と管理の詳細については、こちらを参照してください。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
ms.reviewer: aboeger
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/30/2020
ms.openlocfilehash: b7523b8ab38cfc37795ea6c99f9b22953baffe47
ms.sourcegitcommit: 30e910348f5d5b68e914219c8eadb34d93770eab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "11099806"
---
# HoloLens 2 のエンタープライズ展開と管理

この概要は、IT 担当者が企業内で Microsoft HoloLens 2 デバイスを展開および管理する際の考慮事項を理解するのに役立ちます。

HoloLens 2 は Windows 10 ホログラフィックで動作します。これにより、堅牢で柔軟な組み込みのモバイルデバイスとアプリ管理テクノロジを備えた組織が提供されます。 Windows 10 ホログラフィックは、エンドツーエンドのデバイスライフサイクル管理をサポートしており、会社がデバイス、データ、アプリを制御できるようになっています。 HoloLens 2 は、包括的なモバイルデバイス管理ソリューションを使用して、デバイスの登録、構成、アプリケーション管理からメンテナンスと廃棄まで、標準のライフサイクル慣行に簡単に組み込むことができます。

## 準備

Hololens 2 を企業のエンタープライズ環境に展開する準備ができたら、HoloLens 2 のスケール展開の計画を開始する際に、いくつかの考慮事項を確認して理解しておく必要があります。

### インフラストラクチャの基礎

企業のエンタープライズ展開シナリオの HoloLens 2 の場合、すべての機能をサポートするために、いくつかの重要なインフラストラクチャサービスが必要です。 HoloLens 2 は、展開と管理のために、 [最新のモバイルデバイス管理](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) を考慮して開発されました。 Azure AD Join + MDM は、増加し続けるモバイルワーカーの主要な手段として利用できます。 以下のトピックでは、HoloLens 2 の展開計画で考慮する必要がある各インフラストラクチャコンポーネントの概要を簡単に説明します。

### Azure Active Directory
Azure AD は、ID とアクセス管理を提供する、クラウド ベースのディレクトリ サービスです。 既存のオンプレミスのディレクトリと統合して、ハイブリッドの ID ソリューションを作成できます。 Microsoft Office 365 または Intune を使用する組織には、既に Azure AD が使用されています。これには、無料、Premium P1、Premium P2 (「 [Azure Active Directory edition](https://azure.microsoft.com/documentation/articles/active-directory-editions/)」をご覧ください) の3つのエディションがあります。 Azure AD デバイスの登録はすべてのエディションでサポートされていますが、MDM の自動登録を有効にするには Premium P1 が必要です。 HoloLens 2 のエンタープライズレベルのほとんどの機能を有効にするには、Azure Active Directory の参加が必要です。

> [!NOTE]
> オンプレミスの Active Directory の参加は、HoloLens 2 ではサポートされていません。

### モバイル デバイス管理
HoloLens 2 は、特に企業環境のモバイルデバイス管理 (MDM) システムによって管理されるように設計されています。 エンタープライズモビリティ + セキュリティの一部である Microsoft [Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune)は、企業内のデバイスを管理するクラウドベースの MDM システムです。 Office 365 と同様に、Intune は id 管理に Azure AD を使用するため、従業員は Office 365 にサインインするために使用するデバイスを Intune に登録するときに同じ資格情報を使用します。 複数の MDM システムが Windows 10 をサポートしており、ほとんどは、個人のデバイスおよび企業のデバイスの展開のシナリオをサポートしています。 MDM システムでは、HoloLens 2 のアプリケーションの展開と更新も管理できます。 現在、HoloLens 2 をサポートしているその他の MDM プロバイダーには、次のものが含まれます。放映監視、MobileIron、その他。 すべての MDM システムベンダーが Windows 10 デバイス管理構成サービスプロバイダー (CSP) にアクセスできるため、Microsoft Intune とサードパーティの MDM 製品のどちらを使用するかにかかわらず、IT 組織は、どのシステムを選択するかを自由に選ぶことができます。

> [!NOTE]
> System Center Configuration Manager などの従来のオンプレミス PC 管理システムは、HoloLens 2 ではサポートされていません。

### Windows Update for Business
Windows Update for Business は、IT 管理者に対して Windows Update を中心とした追加の管理機能を提供するように設計されています。これには、更新プログラムをデバイスのグループに展開する機能や、更新プログラムをインストールするためのメンテナンス ウィンドウを定義する機能などが含まれています。 HoloLens 2 更新プログラムの管理の詳細については、 [こちら](https://docs.microsoft.com/hololens/hololens-updates)を参照してください。

### 証明書
HoloLens 2 は、企業の Wi-fi ネットワーク認証または他のリソースへのアクセス用の証明書が必要な環境の場合に、MDM による証明書の展開をサポートします。 一部の MDM インフラストラクチャ構成では、HoloLens 2 への証明書の展開を有効にする必要があります。 [HoloLens 2 用の証明書とネットワークプロファイルを準備](https://docs.microsoft.com/hololens/hololens-certificates-network)する方法について説明します。 Intune の詳細については、 [こちら](https://docs.microsoft.com/mem/intune/protect/certificates-configure)を参照してください。

## 構成

MDM 管理者は、MDM システムに登録されているすべての企業デバイスでポリシー設定を定義して実装することができます。 使用する構成設定は、展開シナリオによって異なります。 Windows 10 では、構成サービスプロバイダー (CSP) は、デバイスの構成設定の読み取り、設定、変更、または削除を行うためのインターフェイスです。 これらの設定は、レジストリ キーまたはファイルにマップされます。 HoloLens 2 用の Windows 10 デバイス管理 Csp の詳細については、「 [hololens デバイスでサポートされている](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)すべての csp の一覧」を参照してください。

HoloLens 2 では、カスタムプロビジョニングパッケージを使用して、一部の CSP 構成の設定もサポートされています。 通常、プロビジョニングパッケージは、MDM 以外で管理されるデバイスで利用できます。また、各デバイスに手動で適用する必要があります。 カスタムプロビジョニングパッケージの作成の詳細については、 [こちら](https://docs.microsoft.com/hololens/hololens-provisioning)を参照してください。

> [!NOTE]
> HoloLens 2 は [Windows 自動操縦](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)をサポートしており、会社の windows 10 デバイスの構成を簡単かつ簡単に管理することができます。

### Id 管理

従業員は、1つのアカウントを使用してデバイスを初期化する必要があります。そのためには、組織が最初に有効にするアカウントを管理する必要があることを&#39;します。 選択したアカウントによって、デバイスを制御するユーザーが決まり、管理機能に影響があります。 HoloLens 2 では、ローカルユーザーアカウント、個人用 Microsoft アカウント、および Azure Active Directory アカウントの3種類のアカウントがサポートされています。 お客様の企業の id 管理ソリューションを使用する場合は、HoloLens 2 デバイスのすべての機能を有効にするため、Azure Active Directory を活用することを強くお勧めします。 HoloLens 2 の Id の詳細については、 [こちら](https://docs.microsoft.com/hololens/hololens-identity)を参照してください。

### ネットワークと接続

HoloLens 2 はクラウドの最初のデバイスであるため、すべての機能と機能を利用できるようにするには、オンラインリソースへのネットワークアクセスが必要です。 企業のイントラネットネットワークに接続できる HoloLens 2 デバイスを展開する場合は、HoloLens 2 クラウドサービスへのアクセスを許可するように、プロキシ/ファイアウォールルールの更新が必要になることがあります。 HoloLens 2 オペレーティングシステムに必要な一般的なエンドポイントの一覧については、 [こちら](https://docs.microsoft.com/hololens/hololens-offline)を参照してください。 アプリやその他のクラウドサービスが HoloLens 2 で正常に動作するためには、追加のエンドポイントへのアクセスが必要になることがあります。

追加のエンドポイントアクセスを必要とする一般的な HoloLens 2 サービスには、次のようなものがあります。

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [D365 ガイド](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 Remote Assist (O365 Teams インフラストラクチャ)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### 証明書の展開

組織内の企業の Wi-fi ネットワークや他のサービスにアクセスするために証明書が必要な場合、HoloLens 2 は MDM によるユーザーとデバイスの証明書の展開をサポートします。 注: MDM ソリューションでは、Windows 10 デバイスに証明書を展開するために、追加のインフラストラクチャ構成が必要になる場合があります。

### セキュリティレビュー

ほとんどのエンタープライズ IT 部門では、企業のエンタープライズネットワークに展開される新しいデバイスの評価とレビューを行う必要があります。 組織で HoloLens 2 のセキュリティレビューが必要な場合は、 [ここで詳細を確認して、セキュリティの承認を得る](https://docs.microsoft.com/hololens/security-overview)ことができます。

### 一般的な HoloLens 2 デバイスの設定

Hololens 2 デバイスを企業のエンタープライズ環境に展開する場合、HoloLens 2 の展開を計画するときに考慮する必要がある一般的なデバイス構成がいくつかあります。 この一覧では、よく使われる構成と設定について説明します。また、利用可能なオプションの完全な一覧も含まれていません。

| デバイスの設定 | 簡単な説明。                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [ハードウェアの制限](hololens-requirements.md#hardware-restrictions)               | ハードウェア制限により、接続性が低下し、データ保護がサポートされます。                        |
| [Wi-Fi プロファイル](hololens-requirements.md#wi-fi-profiles)               | ユーザーの介入や操作なしで Wi-fi プロファイルを構成します。                              |
| [証明書](hololens-requirements.md#certificates-1)               | アカウントまたは Wi-fi 認証、VPN 暗号化、web コンテンツの SSL 暗号化を提供します。 |
| [プロキシ](hololens-requirements.md#proxy)              | 内部トラフィックを管理する。                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | 会社のイントラネット上のアプリとリソースへのアクセスを制御します。                               |
| [Kiosk Mode (キオスク モード)](hololens-requirements.md#kiosk-mode) | UI 経由でユーザーに表示されるアプリケーションを制限します。 |

#### ハードウェアの制限

HoloLens 2 は、カメラ、マイク、スピーカー、USB インターフェイス、Bluetooth インターフェイス、Wi-fi などの一般的なハードウェア機能を含む、最先端の技術を使用します。 ハードウェアの制限を使って、これらの機能の利用を制御できます。

以下は、HoloLens 2 でハードウェアの制限を構成するために、一般的に使用される MDM 設定の一覧です。 これらのハードウェアの制限の中には、接続の提供とデータ保護をサポートするものもあります。

- [**WiFi を許可:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) ユーザーがデバイスで Wi-fi 無線を有効にして使用できるかどうか
- [**USB 接続を許可する:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) USB 接続が有効になっているかどうか (&#39;は USB 充電に影響しません)
- [**Bluetooth を許可する:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) ユーザーがデバイスで Bluetooth 無線を有効にして使用できるかどうか

その他の[一般的なデバイスの制限](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)については、こちらを参照してください。

#### Wi-Fi プロファイル

多くの企業の Wi-Fi ネットワークは、ユーザー アクセスの制限とセキュリティ保護のため、証明書とその他の複雑な情報を必要とします。 この高度な Wi-fi 情報は、一般的なユーザーが構成するのは困難ですが、MDM システムでは、ユーザーの介入なしでこれらの Wi-fi プロファイルを完全に構成できます。 複数の Wi-Fi プロファイルを MDM システムで作成できます。

Windows 10 の Wi-fi 設定の詳細については、「 [エンタープライズプロファイルの WiFi 設定](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)」を参照してください。

#### 証明書

[証明書] では、アカウント認証、Wi-fi 認証、VPN 暗号化、および web コンテンツの SSL 暗号化を提供して、セキュリティを向上させることができます。 管理者は、プロビジョニングパッケージを通じて手動でデバイスの証明書を管理することができますが、ベストプラクティスとしては、MDM システムを使用して、登録から更新と失効までの間に、それらの証明書を管理することをお&#39;します。 Mdm システムでは、デバイスの登録後に、これらの証明書をデバイス&#39; 証明書ストアに自動的に展開することができます (MDM システムで Simple Certificate Enrollment Protocol (SCEP) または公開キー暗号化標準 #12 (PKCS # 12) をサポートしている限り)。 MDM では、現在の証明書の有効期限が切れる前に、登録されているクライアント証明書を照会して削除したり、新しい登録要求をトリガーすることもできます。

「 [HoloLens 2 用の証明書とネットワークプロファイルを準備](https://docs.microsoft.com/hololens/hololens-certificates-network)する」を参照してください。

#### プロキシ

ほとんどの企業のイントラネットネットワークは、内部トラフィックを管理するためにプロキシを利用します。 HoloLens 2 では、イーサネット接続と Wi-fi 接続用にプロキシサーバーを構成できます。 これらの設定は、VPN 接続には適用されません。

Windows 10 のプロキシ設定の詳細については、「 [NETWORKPROXY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)」を参照してください。

#### VPN

組織では、多くの場合、会社&#39;s イントラネット上のアプリとリソースへのアクセスを制御するために VPN を使用しています。 HoloLens 2 は SSL VPN 接続をサポートします。これには、Microsoft Store からダウンロード可能なプラグインが必要であり、VPN ベンダーに固有のものである必要があります。

VPN プロファイルについて詳しくは、「[VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)」をご覧ください。

#### Kiosk Mode (キオスク モード)

HoloLens 2 デバイスを、キオスクモードで実行するように構成することによって、キオスクとも呼ばれる固定的なデバイスとして機能するように構成することができます。 キオスクモードでは、デバイスで利用可能なアプリケーション (またはユーザー) を制限します。 キオスクモードは、HoloLens 2 デバイスをビジネスアプリ専用にするために使うことができる便利な機能です。または、アプリデモで HoloLens 2 デバイスを使うことができます。

キオスクモードでの HoloLens 2 の構成の詳細については、「[キオスクとしてセットアップ](https://docs.microsoft.com/hololens/hololens-kiosk)する」を参照してください。

## 展開

### MDM デバイスの登録

エンタープライズ展開の場合、デバイスを MDM に登録することをお勧めします。 Azure AD join と MDM の自動登録 (AAD + MDM) を使用する場合にのみ、会社のデバイスとして MDM に [デバイスを登録](https://docs.microsoft.com/hololens/hololens-enroll-mdm) します。 これには、Azure AD Premium が必要です。また、Intune などのいくつかの MDM プロバイダーへの自動登録もサポートされています。

自己展開型登録方法の [自動操縦](https://docs.microsoft.com/hololens/hololens2-autopilot)について、詳細はこちらをご覧ください。

### アプリケーションの展開

多くの場合、モバイル デバイスにおけるユーザーの生産性はアプリによって決まります。

Windows 10 は、Windows アプリ用のユニバーサル Windows プラットフォーム (UWP) を使用して、複数のデバイスでシームレスに動作するアプリの開発を可能にします。

HoloLens 2 デバイスにアプリケーションを展開するには、複数の方法があります。 アプリは、MDM、一般法人向け Microsoft Store、プロビジョニングパッケージを通じて直接展開することができます。 アプリの展開について詳しくは [、こちらを](https://docs.microsoft.com/hololens/app-deploy-overview)ご覧ください。

> [!NOTE]
> HoloLens 2 は、UWP ARM64 アプリの実行のみをサポートしています。

## 保守

企業の IT 環境では、最新の技術をユーザーに提供したいという考えと、セキュリティおよびコスト管理のニーズのバランスを取る必要があります。 Cyberattacks は日常的に発生しているため、Windows 10 デバイスの状態を適切に維持することが重要です。 IT は、コンプライアンスから逸脱しないように構成設定を管理し、内部アプリケーションにアクセスできるデバイスを厳格に設定する必要があります。 HoloLens 2 は、デバイスが企業ポリシーに準拠していることを確認するために必要な、モバイル運用管理機能を提供します。

### OS サービスオプション

**合理化されたアップデート プロセス**

Microsoft は Windows 製品のエンジニアリングとリリースのサイクルを合理化し、市場から要求された新しい機能、エクスペリエンス、機能性を、これまでで最も迅速に提供できるようになりました。 Microsoft は、1 年 (12 か月の期間) あたり 2 回の機能更新プログラムを提供することを計画しています。 **機能更新プログラム** は、現在のブランチまたは CB を確立し、関連付けられたバージョンを持っています。

また、Microsoft は、セキュリティと安定性の更新プログラムを、HoloLens 2 デバイスに直接配布し、インストールします。 Windows Update を通じて Microsoft コントロールの下にリリースされたこれらの **品質更新プログラム** は、毎月利用できます。 HoloLens 2 は、同じ標準の更新プロセスの一部として機能更新プログラムと品質更新プログラムを利用します。

企業のお客様は、MDM システムを使用して、HoloLens 2s の更新エクスペリエンスとプロセスを管理できます。 ほとんどの場合、更新プロセスを管理するポリシーは、機能更新プログラムと品質更新プログラムの両方に適用されます。 詳細については、「 [HoloLens 更新プログラムの MDM を構成する](https://docs.microsoft.com/hololens/hololens-updates)」をご覧ください。

### アプリケーションを管理する 

IT 管理者は、HoloLens 2 にどのアプリをインストールできるかを制御し、それらのアプリを最新の状態に維持する方法を管理できます。

HoloLens 2 は [Windows Defender アプリケーション制御 (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)をサポートします。これにより、管理者は Microsoft ストアからのアプリの一覧の作成、許可、または禁止を行うことができます。 この機能は、組み込みのアプリにも拡張されます。 アプリを許可または拒否する機能によって、ユーザーは目的に応じてデバイスを確実に使うことができます。 しかし、従業員が必要とする、または要求するアプリとセキュリティ上の考慮事項とのバランスを見つけることは、必ずしも容易ではありません。 許可リストまたは拒否リストを作成するには、Microsoft Store で変化するアプリの状況に対応する必要もあります。

詳しくは、「 [アプリケーション制御 CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)」をご覧ください。

### 廃棄

デバイスの廃止とは、デバイスのライフサイクルの最後のフェーズです。 お客様は、お客様のデータの機密性を侵害する可能性のある廃棄されたデバイスに企業データを残しておく必要がある&#39;ため、新しいモデルに置き換えられるデバイスは、安全に廃止されることを&#39;ています。 また、IT 部門では、紛失した、または盗難に遭ったデバイスをワイプする必要があるユーザーを適切にサポートする方法も必要です。

HoloLens 2 では、デバイスをワイプする3つの方法がサポートされています。

**MDM ファクトリワイプ:** 管理者によって開始された MDM コマンドを使用して、HoloLens 2 を出荷時のイメージに戻します。 デバイス上の保存されているデータをすべて消去します。

**設定内でのデバイスのリセット:** エンドユーザーは、デバイスの設定アプリ内で HoloLens 2 を手動でリセットできます。 デバイス上の保存されているデータをすべて消去します。

**高度な回復コンパニオン (弧):** ARC ツールを実行している PC から、ユーザーまたは管理者は、USB ケーブル経由で PC に接続された HoloLens 2 をフラッシュすることができます。 デバイス上の保存されているデータをすべて消去します。
