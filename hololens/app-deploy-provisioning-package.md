---
title: プロビジョニング パッケージ
description: デバイスのパッケージ化、プロビジョニング、デプロイ、エンタープライズ アプリの展開についてHoloLensします。
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
ms.openlocfilehash: 5aa554f9e7fdc09c3112b628e0978ac3332bc57d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635519"
---
# <a name="provisioning-package"></a>プロビジョニング パッケージ

プロビジョニング パッケージを使用すると、エンドポイント管理にアクセスせずに環境内のデバイスを準備および構成できます。 また、ユーザーの ID、登録状態、Out of Box Experience (OOBE) の間、またはセットアップ中にプロビジョニング パッケージを適用する方法に関係なく、デバイス [に展開することもできます](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)。

## <a name="provisioning-packages-considerations"></a>プロビジョニング パッケージに関する考慮事項:

* 非パブリック アプリ
* USB サイドロードのみ
* 自動更新なし (PPKG による手動更新が必要)

プロビジョニング パッケージを介してインストールされたアプリは、ローカル コンピューター ストア内の証明書によって署名されている必要があります。 プロビジョニング パッケージでは、デバイス (ローカル コンピューター) ストアにのみ証明書をインストールできます。そのため、アプリと証明書は同じプロビジョニング パッケージを介してインストールできます。 MDM から証明書を展開する場合、または証明書マネージャー を[](certificate-manager.md)使用してをインストールする場合は、必ずローカル コンピューター ストアに証明書を展開して、この方法でインストールされたアプリに署名してください。

デバイスのプロビジョニング パッケージを作成する基本については、「HoloLens」をHoloLens[してください](/hololens/hololens-provisioning)。 アプリをデプロイするには、高度なプロビジョニングから始める必要があります。

> [!NOTE]
> HoloLens (第 1 世代) では、プロビジョニング パッケージを使用したアプリのインストール **(UniversalAppInstall)** が制限されています。 HoloLens (第 1 世代) デバイスでは、OOBE 中のみ、およびユーザー コンテキストのインストールでのみ、PPKG 経由でのアプリのインストールがサポートされます。

## <a name="setup"></a>セットアップ

構成[Windows、次の 4](https://www.microsoft.com/store/productId/9NBLGGH4TX22)つの手順を実行します。

1. ApplicationManagement/AllowAllTrustedApps を "Yes" に設定します。 参照: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)。

2. **[UniversalAppInstall**  >  **UserContextAppLicense] に移動し****、PackageFamilyName を入力します**。 [「UniversalAppInstall」を参照してください](/windows/configuration/wcd/wcd-universalappinstall)。 [「UserContextAppLicense 」も参照してください](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)。

   アプリをインストールデバイス ポータルデバイスでアプリを使用できます。 [アプリ] ページにアクセスし、PackageRelativeID 行を見て、"!" の前のすべての情報を確認します。 **PackageFamilyName です**。

3. その後、新しいセクション ApplicationFile が **表示されます**。 この領域を使用して、appx バンドルをアップロードします。

4. アプリを購入した場合、または独自の LOB アプリを構築した場合は、ライセンス ファイルまたはセキュリティ証明書をアップロードする必要があります。

    - ライセンス ファイルの場合 **:UniversalAppInstall**  >  **UserContextAppLicence** に移動し、ライセンスの場所を参照してアップロードします。
    - セキュリティ ファイルの場合は、[証明書] に **移動** し、.appx バンドルと共にインストールする証明書を選択します。

プロジェクトを安全な場所に保存してください。 次 **に、** プロビジョニング パッケージ **としてエクスポートします**。  

「プロビジョニング パッケージ[を に適用する」もHoloLens。](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)
