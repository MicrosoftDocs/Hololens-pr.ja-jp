---
title: プロビジョニング パッケージ
description: HoloLens デバイスのアプリのパッケージ化、プロビジョニング、デプロイ、エンタープライズアプリのデプロイについて説明します。
keywords: アプリ, アプリのデプロイ, エンタープライズアプリのデプロイ, プロビジョニング
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
ms.openlocfilehash: 2cb497d850ff7ba2de66f69e8ec53e6dd36b773cc13d01b038def8d539e3b0c1
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665218"
---
# <a name="provisioning-package"></a>プロビジョニング パッケージ

プロビジョニングパッケージを使用して、エンドポイント管理にアクセスせずに、環境でデバイスの準備と構成を行うことができます。 また、ユーザーの id、登録ステータス、アウトオブボックスエクスペリエンス (OOBE) 中、または [セットアップ中にプロビジョニングパッケージを適用](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)して、デバイスに展開することもできます。

## <a name="provisioning-packages-considerations"></a>プロビジョニングパッケージに関する考慮事項:

* パブリックでないアプリ
* USB サイド読み込みのみ
* 自動更新なし (PPKGs を使用した手動更新が必要)

プロビジョニングパッケージを使用してインストールされるアプリは、ローカルコンピューターストアの証明書によって署名されている必要があります。 プロビジョニングパッケージでは、デバイス (ローカルコンピューター) ストアにのみ証明書をインストールできるため、同じプロビジョニングパッケージを使用してアプリと証明書をインストールできます。 MDM から証明書を展開する場合、または [証明書マネージャー](certificate-manager.md)を使用してインストールする場合は、この方法でインストールされたアプリに署名するために、ローカルコンピューターストアに証明書をデプロイしてください。

HoloLens デバイスのプロビジョニングパッケージを作成する方法の基本については、 [HoloLens プロビジョニング](/hololens/hololens-provisioning)に関するページを参照してください。 アプリを展開するには、高度なプロビジョニングから始める必要があります。

> [!NOTE]
> HoloLens (第1世代) では、プロビジョニングパッケージを使用したアプリのインストール (**UniversalAppInstall**) のサポートが制限されています。 HoloLens (第1世代) デバイスでは、OOBE 中にのみ ppkg を使用したアプリのインストールと、ユーザーコンテキストのインストールのみがサポートされます。

## <a name="setup"></a>セットアップ

[Windows 構成デザイナー](https://www.microsoft.com/store/productId/9NBLGGH4TX22)内で、次の4つの手順を実行します。

1. ApplicationManagement/AllowAllTrustedApps を "Yes" に設定します。 参照してください: [Applicationmanagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)です。

2. **UniversalAppInstall**  >  **UserContextAppLicense** に移動し、[パッケージ] の **名前** を入力します。 「 [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall)」を参照してください。 参照: [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)

   デバイスポータルは、アプリが既にインストールされているデバイスで使用できます。 アプリのページにアクセスし、PackageRelativeID の行の前にあるすべての情報を確認します。は、整理 **Efamilyname** です。

3. これで、新しいセクション **Applicationfile** が作成されていることがわかります。 この領域を使用して、appx バンドルをアップロードします。

4. アプリを購入したか、独自の LOB アプリを作成したかに応じて、ライセンスファイルまたはセキュリティ証明書をアップロードする必要があります。

    - ライセンスファイルの場合: **UniversalAppInstall**  >  **usercontextアプリケーション** に移動し、ライセンスの場所を参照してアップロードします。
    - セキュリティファイルの場合は、[ **証明書** ] に移動し、.appx バンドルと共にインストールする証明書を選択します。

プロジェクトは安全な場所に保存してください。 次に、それを **プロビジョニングパッケージ** として **エクスポート** します。  

関連項目:[プロビジョニングパッケージを HoloLens に適用](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)します。
