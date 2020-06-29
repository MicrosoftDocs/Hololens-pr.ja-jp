---
title: HoloLens のインフラストラクチャ ガイドライン
description: ''
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 65403589fa3d612290fdd59a4843da27c12a956c
ms.sourcegitcommit: f3cda6c6b3bfb7ba4be5f4da66d8ed5b03ca807d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830151"
---
# HoloLens 向けにネットワークを構成する

ドキュメントのこの部分には、次のユーザーが必要です。

1. プロキシ/ファイアウォールを変更するためのアクセス許可を持つネットワーク管理者
2. Azure Active Directory 管理者
3. モバイル デバイス マネージャー管理者

## インフラストラクチャの要件

HoloLens は、本質的には、Azure と統合された Windows モバイル デバイスです。  利用可能なワイヤレス ネットワーク (Wi-Fi) があり Microsoft サービスへアクセスできる商用環境で最もよく動作します。

必須のクラウド サービス:

- Azure Active Directory (AAD)
- Windows Update (WU)

商業利用のお客様は、HoloLens デバイスの大規模な管理を行うには Enterprise Mobility Management (EMM) またはモバイル デバイス管理 (MDM) インフラストラクチャが必要になります。    このガイドでは例として [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) を使用しますが、Microsoft ポリシーをフル サポートしているプロバイダーは、いずれも HoloLens をサポートできます。  使用しているモバイル デバイス管理プロバイダーに問い合わせて、HoloLens 2 をサポートしているかどうかを確認してください。

HoloLens は、一部の、クラウドに接続されていないエクスペリエンスをサポートしています。

### ワイヤレス ネットワーク EAP のサポート

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### HoloLens 固有のネットワーク要件

エンドポイントの[このリスト](hololens-offline.md)がネットワーク ファイアウォールで許可されていることを確認してください。 これにより、HoloLens が正常に機能します。

### リモート アシスト固有のネットワーク要件

1. リモート アシストの最適なパフォーマンスのために推奨される帯域幅は 1.5 Mbps です。 [こちら](https://docs.microsoft.com/MicrosoftTeams/prepare-network)で詳細なネットワーク要件と追加情報を見つけることができます。
**(ネットワーク速度が 1.5 Mbps 以上でないネットワークの場合でも、リモート アシストは機能します。 ただし、品質が低下する場合があります。)**
1. これらのポートと URL がネットワーク ファイアウォールで許可されていることを確認してください。 これにより、Microsoft Teams が機能します。 最新のリストについては、[こちら](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)を参照してください。

### 固有のネットワーク要件のガイド

ガイドには、アプリをダウンロードして使用するためのネットワーク アクセスのみが必要です。

## Azure Active Directory ガイダンス

> [!NOTE]
> この手順は、会社が HoloLens を管理する予定にしている場合にのみ必要です。

1. Azure AD ライセンスがあることを確認します。
追加情報については、「[HoloLens Licenses Requirements (HoloLens のライセンス要件)](hololens-licenses-requirements.md)」を参照してください。

1. 自動登録を使用することを予定している場合は、[Azure AD の登録を構成する](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)必要があります。

1. 会社のユーザーが Azure Active Directory (Azure AD) に含まれていることを確認します。
ユーザーを追加する手順については、[こちら](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory)を参照してください。

1. 同様のライセンスが必要なユーザーは、同じグループに追加することをお勧めします。
    1. [グループの作成](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [ユーザーをグループに追加する](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. 会社のユーザー (またはユーザー グループ) に必要なライセンスが割り当てられていることを確認します。
ライセンスを割り当てる方法は、[こちら](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)で確認できます。

1. この手順は、ユーザーが各自の HoloLens またはモバイル デバイスを会社のネットワークに登録することを想定している場合にのみ実行してください (3 つのオプションがあります)。これらの手順により、会社のユーザー (またはユーザー グループ) がデバイスを追加できるようになります。
    1. **オプション 1:** デバイスを Azure AD に参加させる許可をすべてのユーザーに与えます。
**管理者として Azure ポータルにサインインする** > **Azure Active Directory** > **デバイス** > **デバイス設定** >
 **[ユーザーはデバイスを Azure AD に参加させることができます] を [*All (すべてのユーザー)*] に設定する**

    1. **オプション 2:** デバイスを Azure AD に参加させる権限を、選択されたユーザーおよびグループに付与します。**Azure ポータルに管理者としてサインイン** > [**Azure Active Directory**] > [**デバイス**] > [**デバイス設定**] >
[**ユーザーはデバイスを Azure AD に参加させることができます] を [*Selected*] (選択されたユーザー) に設定**
![Azure AD に参加したデバイスの構成を示す画像](images/azure-ad-image.png)

    1. **オプション 3:** デバイスをドメインに参加させることをすべてのユーザーに対してブロックできます。 この場合、すべてのデバイスを手動で登録する必要があります。

## モバイル デバイス マネージャーのガイダンス

### 継続的なデバイス管理

> [!NOTE]
> この手順は、会社が HoloLens を管理する予定にしている場合にのみ必要です。

継続的なデバイス管理は、モバイル デバイスの管理インフラストラクチャに依存します。  ほとんどのインフラストラクチャでは同様の機能が備わっていますが、ユーザー インターフェイスが大きく異なる場合があります。

1. [CSP (構成サービス プロバイダー)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) を使用すると、ネットワーク上のデバイスの管理設定を作成および展開できます。 HoloLens の CSP の一覧については、[ここ](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)を参照してください。

1. [コンプライアンス ポリシー](https://docs.microsoft.com/intune/device-compliance-get-started)は、会社のインフラストラクチャに準拠するためにデバイスが満たす必要があるルールおよび設定 です。 非準拠デバイスについては、これらのポリシーを条件付きアクセスとともに使用して、会社のリソースへのアクセスをブロックします。 たとえば、Bitlocker が有効になっていることを要求するポリシーを作成することができます。

1. [コンプライアンス ポリシーの作成](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows)。

1. 条件付きアクセスは、モバイル デバイスおよびモバイル アプリケーションが会社のリソースにアクセスすることを許可または拒否します。 役に立つと思われる 2 つのドキュメントとして、「[Plan your CA Deployment (CA 展開を計画する)](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)」と「[ベスト プラクティス](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices)」があります。

1. [こちらの記事](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business)では、 Intune の HoloLens 向けの管理ツールについて説明しています。

1. [デバイス プロファイルの作成](https://docs.microsoft.com/intune/configuration/device-profile-create)

### 更新プログラムの管理

Intune には、HoloLens 2 や HoloLens v1 (Holographic for Business を含む) などの Windows 10 デバイス向けに、更新リングと呼ばれる機能が含まれています。 更新リングには、更新プログラムのインストール方法とタイミングを決めるための設定群が含まれています。

たとえば、更新プログラムをインストールするためのメンテナンス期間を作成することも、更新プログラムのインストール後に再起動することもできます。  更新の準備ができるまで、更新プログラムを無期限に一時停止することもできます。

詳細については、「[Intune を使用して更新リングを構成する](https://docs.microsoft.com/intune/windows-update-for-business-configure)」を参照してください。

### アプリケーション管理

HoloLens アプリケーションの管理には、次を使用します。

1. Microsoft Store  
  Microsoft Store は、HoloLens でアプリケーションを配布および使用するための最善の方法です。  Store では、HoloLens の優れた基本的なアプリ群が既に提供されています。[独自のアプリを公開](https://docs.microsoft.com/windows/uwp/publish/)することもできます。  
  Store 内のすべてのアプリケーションはすべてのユーザーに一般提供されていますが、お客様の要求を満たすアプリが見当たらない場合は、ビジネス向け Microsoft Store をご覧になってください。  

1. [ビジネス向け Microsoft Store](https://docs.microsoft.com/microsoft-store/)  
  ビジネスおよび教育機関向け Microsoft Storeは、企業環境に合わせてカスタマイズされたストアです。  ビジネスおよび教育機関向け Microsoft Store を使用することで、Windows 10 および HoloLens に組み込まれている Microsoft Store を使用して、組織用にアプリの検索、取得、配布、管理を行えます。  一般的な環境ではなくお客様の商用環境に特化したアプリを展開することも可能になります。

1. Intune またはその他のモバイル デバイス管理ソリューションを使用したアプリケーションの展開と管理  
  Intune を含むほとんどのモバイル デバイス管理ソリューションでは、基幹アプリケーションを登録済みのデバイス群に直接展開する方法が提供されます。  詳細については、[Intune アプリのインストール](https://docs.microsoft.com/intune/apps-deploy)についての記事を参照してください。

1. _非推奨_ Device Portal  
  アプリケーションは、Windows デバイス ポータルを使用して HoloLens に直接インストールすることもできます。  デバイス ポータルを使用するには開発者モードを有効にする必要があるため、この方法はお勧めできません。

[HoloLens にアプリをインストールする方法](https://docs.microsoft.com/hololens/hololens-install-apps)の詳細をご覧ください。

### 証明書

証明書は、MDM プロバイダー経由で配布できます。 会社で証明書が要求される場合、Intune では PKCS、PFX、および SCEP がサポートされています。 どの証明書が会社に適しているかについて理解することが重要です。 最適な証明書を決定するには、[こちら](https://docs.microsoft.com/intune/protect/certificates-configure)をご覧ください。 HoloLens 認証に証明書を使用する予定がある場合には、PFX または SCEP が最適です。

SCEP の手順については、[こちら](https://docs.microsoft.com/intune/protect/certificates-profile-scep)をご覧ください。

### Holographics for Business Commercial Suite へのアップグレード方法

> [!NOTE]
> Windows Holographics for Business (Commercial Suite) は、HoloLens の第 1 世代デバイスのみを対象としています。 プロファイルは HoloLens 2 デバイスには適用されません。

Commercial Suite へアップグレードする方法は、[こちらで](https://docs.microsoft.com/intune/configuration/holographic-upgrade)確認できます。

### Microsoft Intune を使用してキオスク モードを構成する方法 

1. Microsoft Store を Intune に同期します ([やり方](https://docs.microsoft.com/intune/apps/windows-store-for-business))。

1. アプリの設定を確認します
    1. ビジネス向け Microsoft Store のアカウントにログインします。
    1. **[管理]、[製品とサービス]、[アプリとソフトウェア]、[同期するアプリを選択する]、[プライベート ストアの利用許可] の順に選択し、[すべてのユーザー] または [特定のグループ] を選択します。**
        >[!NOTE]
        >目的のアプリが表示されない場合は、ストアを検索してアプリを「取得」する必要があります。 **右上隅の「検索」バーをクリックし、アプリの名前を入力し、アプリをクリックして、「取得」を選択します**。
    1. 目的のアプリが **[Intune]、[クライアント アプリ]、[アプリ]** の順に移動して表示されない場合は、再度[アプリを同期する](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps)必要があります。

1. [キオスク モード用のデバイス プロファイルを作成する](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> [Azure AD] を [User logon type] (ユーザー ログオン型) として使用することで、ユーザーごとにキオスク モードのエクスペリエンスが異なるように構成できます。 ただし、このオプションは複数アプリ キオスク モードでのみ使用できます。 複数アプリ キオスク モードは、1 つのアプリだけでなく複数のアプリでも機能します。

![Intune のキオスク モードの構成画面を示す画像](images/aad-kioskmode.png)

その他の MDM サービスについては、使用しているプロバイダーのドキュメントで手順を参照してください。 使用している MDM サービスでキオスクを設定するためにカスタム設定とフル XML 構成を使用する必要がある場合は、追加の手順を[こちら](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)で確認できます。

## 証明書と認証

証明書は、MDM 経由で展開できます ([MDM セクション](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)の「証明書」を参照してください)。 証明書は、パッケージ プロビジョニングを使用しても HoloLens にできます。 詳細については、「[HoloLens Provisioning (HoloLens のプロビジョニング)](hololens-provisioning.md)」を参照してください。

### その他の Intune クイック リンク

1. [プロファイルを作成する:](https://docs.microsoft.com/intune/configuration/device-profile-create) プロファイルを使用すると、組織内のデバイスにプッシュされる設定を追加および構成できます。

