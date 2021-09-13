---
title: プロビジョニング パッケージ
description: アプリのパッケージ化、プロビジョニング、展開、およびデバイスのエンタープライズ アプリの展開についてHoloLensします。
keywords: アプリ, アプリの展開, エンタープライズ アプリの展開, プロビジョニング
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: d071f4326a35a9ea61e2069618da7107bb808f04
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033076"
---
# <a name="provisioning-package"></a>プロビジョニング パッケージ

プロビジョニング パッケージを使用すると、エンドポイント管理にアクセスせずに、環境内のデバイスを準備および構成できます。 また、ユーザーの ID、登録状態、Out of Box Experience (OOBE) の間、またはセットアップ中にプロビジョニング パッケージを適用する方法に関係なく、デバイス [に展開することもできます](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)。

## <a name="provisioning-packages-considerations"></a>プロビジョニング パッケージに関する考慮事項

* 非パブリック アプリ
* USB サイドロードのみ
* 自動更新なし (PPKG による手動更新が必要)

プロビジョニング パッケージを介してインストールされたアプリは、ローカル コンピューター ストア内の証明書によって署名されている必要があります。 プロビジョニング パッケージでは、デバイス (ローカル コンピューター) ストアにのみ証明書をインストールできます。 そのため、アプリと証明書は、同じプロビジョニング パッケージを使用してインストールできます。 MDM から証明書を展開する場合、または証明書マネージャー を[](certificate-manager.md)使用してをインストールする場合は、必ずローカル コンピューター ストアに証明書を展開して、この方法でインストールされたアプリに署名してください。

デバイス用のプロビジョニング パッケージの作成の基本については、「HoloLens」をHoloLens[してください](/hololens/hololens-provisioning)。 アプリをデプロイするには、高度なプロビジョニングから始める必要があります。

> [!NOTE]
> HoloLens (第 1 世代) では、プロビジョニング パッケージを使用したアプリのインストール **(UniversalAppInstall)** が制限されています。 HoloLens (第 1 世代) デバイスでは、OOBE 中のみ、およびユーザー コンテキストのインストールでのみ、PPKG 経由でのアプリのインストールがサポートされます。

## <a name="setup"></a>セットアップ

構成[Windows内で、次の](https://www.microsoft.com/store/productId/9NBLGGH4TX22)4 つの手順を実行します。

1. ApplicationManagement/AllowAllTrustedApps を "Yes" に設定します。 参照: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)。

2. **[UniversalAppInstall**  >  **UserContext]に移動し****、PackageFamilyName を入力します**。 [「UniversalAppInstall」を参照してください](/windows/configuration/wcd/wcd-universalappinstall)。

   アプリをインストールデバイス ポータルデバイスでアプリを使用できます。 [アプリ] ページにアクセスし、PackageRelativeID 行を見て、"!" の前のすべての情報を確認します。 **PackageFamilyName** です。

3. その後、新しいセクション ApplicationFile が **表示されます**。 この領域を使用して、appx バンドルをアップロードします。

4. アプリを購入した場合、または独自の LOB アプリを構築した場合は、ライセンス ファイルまたはセキュリティ証明書をアップロードする必要があります。

    - ライセンス ファイルの場合 **:UniversalAppInstall**  >  **UserContextAppLicence** に移動し、ライセンス製品 ID を入力します。 新しい <b>セクション LicenseProductID:</b><i>yourlicenseproductid</i> が作成されます。この新しいセクションを選択し、ライセンスの場所を参照してアップロードします。
        - [「UserContextAppLicense 」を参照してください](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)。
    - セキュリティ ファイルの場合は、[証明書] に **移動** し、.appx バンドルと共にインストールする証明書を選択します。

プロジェクトを安全な場所に保存してください。 次 **に、** プロビジョニング パッケージ **としてエクスポートします**。  

「プロビジョニング パッケージ[を に適用する」も参照HoloLens。](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)
