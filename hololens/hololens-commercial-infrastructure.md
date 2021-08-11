---
title: HoloLens のインフラストラクチャ ガイドライン
description: ワイヤレス ネットワーク サポート、Remote Assist、モバイル デバイス管理など、HoloLens デバイスのインフラストラクチャ ガイドラインについて説明します。
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
ms.openlocfilehash: 3aa5ed676a9f8864904752da3d965cba5fab7ce98db51abb4ff9444f1a0a370b
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664437"
---
# <a name="configure-your-network-for-hololens"></a>HoloLens 向けにネットワークを構成する

ドキュメントのこの部分には、次のユーザーが必要です。

1. プロキシまたはファイアウォールを変更するアクセス許可を持つネットワーク管理者
2. Azure Active Directory 管理者
3. モバイル デバイス マネージャー管理者

## <a name="infrastructure-requirements"></a>インフラストラクチャの要件

HoloLens は、本質的には、Azure と統合された Windows モバイル デバイスです。  利用可能なワイヤレス ネットワーク (Wi-Fi) があり Microsoft サービスへアクセスできる商用環境に最適です。

必須のクラウド サービス:

- Azure Active Directory (Azure AD)
- Windows Update (WU)

商用のお客様が HoloLens デバイスを大規模に管理するには、エンタープライズ モビリティ管理 (EMM) またはモバイル デバイス管理 (MDM) のインフラストラクチャが必要です。  このガイドでは例として [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) を使用しますが、Microsoft ポリシーをフル サポートしているプロバイダーは、いずれも HoloLens をサポートできます。  使用しているモバイル デバイス管理プロバイダーに問い合わせて、HoloLens 2 をサポートしているかどうかを確認してください。

HoloLens は、一部の、クラウドに接続されていないエクスペリエンスをサポートしています。

### <a name="wireless-network-eap-support"></a>ワイヤレス ネットワーク EAP のサポート

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### <a name="hololens-specific-network-requirements"></a>HoloLens 固有のネットワーク要件

お使いのネットワーク ファイアウォールで[こちらの一覧](hololens-offline.md)のエンドポイントが許可されていることを確認してください。 これにより、HoloLens が正常に機能します。

### <a name="remote-assist-specific-network-requirements"></a>Remote Assist 固有のネットワーク要件

1. Remote Assist の最適なパフォーマンスのために推奨される帯域幅は 1.5 Mbps です。 詳細については、[詳細なネットワーク要件](/MicrosoftTeams/prepare-network)に関するページを参照してください
**(ネットワーク速度が 1.5 Mbps 以上のネットワークがない場合でも、Remote Assist は動作しますが、品質が低下する場合があることに注意してください)。**
1. Microsoft Teams が機能するように、これらのポートと URL がネットワーク ファイアウォールで許可されていることを確認します。 [最新のポート一覧](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)で最新情報を入手してください。

- [Remote Assist に固有のネットワーク要件](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)を参照してください。 
- [Microsoft Teams に合わせて組織のネットワークを準備する](/MicrosoftTeams/prepare-network)方法を参照してください。

### <a name="guides-specific-network-requirements"></a>Guides 固有のネットワーク要件

Guides には、アプリをダウンロードして使用するためのネットワーク アクセスのみが必要です。

## <a name="azure-active-directory-guidance"></a>Azure Active Directory のガイダンス

> [!NOTE]
> この手順は、会社が HoloLens を管理する予定の場合にのみ必要です。

1. Azure AD ライセンスがあることを確認します。
その他の情報については、[HoloLens の「ライセンスの要件」](hololens-licenses-requirements.md)を参照してください。

1. 自動登録を使用する予定の場合は、[Azure AD 登録を構成する](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)必要があります。

1. 会社のユーザーが Azure Active Directory (Azure AD) に登録されていることを確認します。
ユーザーを追加するには、次の[手順](/azure/active-directory/fundamentals/add-users-azure-active-directory)を参照してください。

1. 同様のライセンスが必要なユーザーは、同じグループに追加することをお勧めします。
    1. [グループを作成する](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [ユーザーをグループに追加する](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. 会社のユーザー (またはユーザー グループ) に必要なライセンスが割り当てられていることを確認します。
ライセンスを割り当てる必要がある場合は、次の[手順](/azure/active-directory/fundamentals/license-users-groups)を実行します。

1. この手順は、ユーザーが各自の HoloLens またはモバイル デバイスを会社のネットワークに登録することを想定している場合にのみ実行してください (3 つのオプションがあります)。これらの手順により、会社のユーザー (またはユーザー グループ) がデバイスを追加できるようになります。
    1. **オプション 1:** デバイスを Azure AD に参加させるアクセス許可をすべてのユーザーに与えます。
**Azure portal に管理者としてサインインし** >  **[Azure Active Directory]**  >  **[デバイス]**  >  **[デバイスの設定] の順に選択し** >
 **[ユーザーはデバイスを Azure AD に参加させることができます] を *[すべて]*** に設定します

    1. **オプション 2:** デバイスを Azure AD に参加させるアクセス許可を、選択したユーザーまたはグループに与えます。**管理者として Azure portal にサインインし** >  **[Azure Active Directory]**  >  **[デバイス]**  >  **[デバイスの設定] の順に選択し** >
 **[ユーザーはデバイスを Azure AD に参加させることができます] を *[選択]*** に設定します
![Azure AD 参加済みデバイスの構成を示す画像](images/azure-ad-image.png)

    1. **オプション 3:** デバイスをドメインに参加させることをすべてのユーザーに対してブロックできます。 この場合、すべてのデバイスを手動で登録する必要があります。

## <a name="mobile-device-manager-guidance"></a>モバイル デバイス マネージャーのガイダンス

### <a name="ongoing-device-management"></a>継続的なデバイス管理

> [!NOTE]
> この手順は、会社が HoloLens を管理する予定の場合にのみ必要です。

継続的なデバイス管理は、モバイル デバイスの管理インフラストラクチャによって変わります。  ほとんどの場合、一般的な機能は同様ですが、ユーザー インターフェイスが大きく異なる場合があります。

1. [CSP (構成サービス プロバイダー)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) を使用すると、ネットワーク上のデバイスの管理設定を作成および展開できます。 [HoloLens の CSP 一覧](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)を参照してください。

1. [コンプライアンス ポリシー](/intune/device-compliance-get-started)は、会社のインフラストラクチャに準拠するためにデバイスが満たす必要があるルールおよび設定です。 これらのポリシーを条件付きアクセスとともに使用して、準拠していないデバイスから会社のリソースへのアクセスをブロックします。 たとえば、Bitlocker を有効にすることを要求するポリシーを作成できます。

1. [コンプライアンス ポリシーを作成します](/intune/protect/compliance-policy-create-windows)。

1. 条件付きアクセスを使用して、モバイル デバイスとモバイル アプリケーションから会社のリソースへのアクセスを許可または拒否します。 「[条件付きアクセスのデプロイを計画する](/azure/active-directory/conditional-access/plan-conditional-access)」と[ベスト プラクティス](/azure/active-directory/conditional-access/best-practices)に関するページという 2 つのドキュメントが参考になります。

1. [この記事](/intune/fundamentals/windows-holographic-for-business)では、Intune の HoloLens 向け管理ツールについて説明しています。

1. [デバイス プロファイルの作成](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>更新プログラムの管理

Intune には、HoloLens 2 や HoloLens v1 (Holographic for Business を含む) などの Windows 10 デバイス向けに、更新リングと呼ばれる機能があります。 更新リングには、更新プログラムのインストール方法とタイミングを決める一連の設定があります。

たとえば、更新プログラムをインストールするためのメンテナンス期間を作成したり、更新プログラムのインストール後に再起動を選択したりできます。  更新の準備ができるまで、更新プログラムを無期限に一時停止することもできます。

詳細については、[Intune を使用した更新リングの構成](/intune/windows-update-for-business-configure)に関するページを参照してください。

### <a name="application-management"></a>アプリケーション管理

HoloLens アプリケーションの管理には、次を使用します。

1. Microsoft Store  
  Microsoft Store は、HoloLens 上でアプリケーションを配布および使用するための最適な方法です。  Store には優れたコア HoloLens アプリケーション群が既に提供されていますが、[自作のものを公開する](/windows/uwp/publish/)こともできます。  
  Store 内のすべてのアプリケーションはすべてのユーザーに一般提供されていますが、お客様の要求を満たすアプリが見当たらない場合は、ビジネス向け Microsoft Store をご覧になってください。  

1. [ビジネス向け Microsoft ストア](/microsoft-store/)  
  ビジネスおよび教育機関向け Microsoft Store は、企業環境に合わせてカスタマイズされたストアです。  ビジネスおよび教育機関向け Microsoft Store を使用することで、Windows 10 および HoloLens に組み込まれている Microsoft Store を使用して、組織用にアプリの検索、取得、配布、管理を行えます。  一般的な環境ではなくお客様の商用環境に特化したアプリを展開することもできます。

1. Intune またはその他のモバイル デバイス管理ソリューションを使用したアプリケーションの展開と管理  
  Intune を含むほとんどのモバイル デバイス管理ソリューションでは、基幹業務アプリケーションを登録済みのデバイス群に直接展開する方法が提供されます。  [Intune アプリのインストール](/intune/apps-deploy)に関するこちらの記事を参照してください。

1. _非推奨_ デバイス ポータル  
  Windows デバイス ポータルを使用して、アプリケーションを HoloLens に直接インストールすることもできます。  デバイス ポータルを使用するには開発者モードを有効にする必要があるため、この方法はお勧めできません。

詳細については、[HoloLens へのアプリのインストール](hololens-install-apps.md)に関するページを参照してください。

### <a name="certificates"></a>証明書

証明書は、MDM プロバイダー経由で配布できます。 会社で証明書が要求される場合、Intune では PKCS、PFX、および SCEP がサポートされています。 どの証明書が会社に適しているかについて理解することが重要です。 [証明書の構成](/intune/protect/certificates-configure)に関するドキュメントを参照し、ご自分に最適な証明書を判断してください。 HoloLens 認証に証明書を使用する予定がある場合には、PFX または SCEP が最適です。

[SCEP](/intune/protect/certificates-profile-scep) を使用するには、次の手順を参照してください。

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a>Holographics for Business Commercial Suite へのアップグレード方法

> [!NOTE]
> Windows Holographics for Business (Commercial Suite) は、HoloLens の第 1 世代デバイスのみを対象としています。 プロファイルは HoloLens 2 デバイスには適用されません。

Commercial Suite へのアップグレード手順については、[Holographic のアップグレード](/intune/configuration/holographic-upgrade)に関するドキュメントを参照してください。

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a>Microsoft Intune を使用してキオスク モードを構成する方法

1. Microsoft Store を Intune に同期します (こちら[手順](/intune/apps/windows-store-for-business)を参照してください)。

1. アプリの設定を確認します
    1. ビジネス向け Microsoft Store のアカウントにログインします
    1. **[管理] > [製品とサービス] > [アプリとソフトウェア] の順に選択し、同期するアプリを選択し、[Private Store Availability]\(プライベート ストアの可用性\) を選択し、[すべてのユーザー] または [Specific Groups]\(特定のグループ\) を選択します**
        >[!NOTE]
        >目的のアプリが表示されない場合は、ストアを検索してアプリを "取得" する必要があります。 **右上隅にある [検索] バーをクリックし、アプリの名前を入力し、アプリをクリックし、[取得] を選択します**。
    1. **[Intune] > [クライアント アプリ] > [アプリ]** にアプリが表示されない場合は、必要に応じてもう一度 [アプリを同期](/intune/apps/windows-store-for-business#synchronize-apps)します。

1. [キオスク モード用のデバイス プロファイルを作成します](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> [ユーザーのログオンの種類] として [Azure AD] を使用することで、ユーザーごとにキオスク モードのエクスペリエンスが変わるように構成できます。 ただし、このオプションはマルチアプリ キオスク モードでのみ使用できます。 マルチアプリ キオスク モードは、複数のアプリだけでなくアプリが 1 つのみでも機能します。

![Intune のキオスク モードの構成画面を示す画像](images/aad-kioskmode.png)

その他の MDM サービスについては、使用しているプロバイダーのドキュメントで手順を参照してください。 カスタム設定と完全な XML 構成を使用して MDM サービスでキオスクを設定する必要がある場合は、[HoloLens キオスク](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)に関するページの手順を参照してください。

## <a name="certificates-and-authentication"></a>証明書と認証

証明書は、MDM 経由で展開できます ([MDM のセクション](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)の「証明書」を参照してください)。 証明書は、パッケージのプロビジョニングを使用して HoloLens に展開することもできます。 詳細については、[HoloLens のプロビジョニング](hololens-provisioning.md)に関するページを参照してください。

### <a name="additional-intune-quick-links"></a>Intune に関するその他のクイック リンク

1. [プロファイルを作成する:](/intune/configuration/device-profile-create) プロファイルを使用すると、組織内のデバイスにプッシュされる設定を追加および構成できます。

