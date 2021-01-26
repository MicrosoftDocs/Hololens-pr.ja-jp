---
title: プロビジョニング パッケージ
description: HoloLens デバイスのアプリのパッケージ化、プロビジョニング、展開、およびエンタープライズ アプリの展開について説明します。
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
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283698"
---
# プロビジョニング パッケージ

プロビジョニング パッケージを使用すると、エンドポイント管理にアクセスすることなく、環境内のデバイスを準備および構成できます。 また、ユーザーの ID、登録状態、Out of Box Experience (OOBE) の間、またはセットアップ中にプロビジョニング パッケージを適用することで、デバイスに展開 [することもできます](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)。

## プロビジョニング パッケージに関する考慮事項:

* 非パブリック アプリ
* USB サイドロードのみ
* 自動更新なし (PPKG による手動更新が必要)

プロビジョニング パッケージ経由でインストールされたアプリは、ローカル コンピューター ストアの証明書で署名する必要があります。 プロビジョニング パッケージは証明書をデバイス (ローカル コンピューター) ストアにのみインストールできます。そのため、アプリと証明書は同じプロビジョニング パッケージ経由でインストールできます。 MDM から証明書を展開する場合、または証明書マネージャーを使用[](certificate-manager.md)してインストールする場合は、ローカル コンピューター ストアに証明書を展開して、この方法でインストールされたアプリに署名してください。

HoloLens デバイス向けプロビジョニング パッケージの作成の基本については [、HoloLens のプロビジョニングに関するページをご覧ください](https://docs.microsoft.com/hololens/hololens-provisioning)。 アプリを展開するには、まず高度なプロビジョニングを行う必要があります。

> [!NOTE]
> HoloLens (第 1 世代) では、プロビジョニング パッケージを使用したアプリのインストール **(UniversalAppInstall)** のサポートが制限されています。 HoloLens (第 1 世代) デバイスは、OOBE 中にのみ PPKG 経由のアプリのインストールをサポートし、ユーザー コンテキストインストールでのみサポートします。

## セットアップ

[Windows 構成デザイナーでは、次の](https://www.microsoft.com/store/productId/9NBLGGH4TX22)4 つの手順を実行します。

1. ApplicationManagement/AllowAllTrustedApps を "Yes" に設定します。 [ApplicationManagement/AllowAllTrustedApps を参照してください](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)。

2. **UniversalAppInstall**  >  **UserContextAppLicense に移動し****、PackageFamilyName を入力します**。 [UniversalAppInstall を参照してください](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall)。 [「UserContextAppLicense」も参照してください](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)。

   既にアプリをインストールしているデバイスで Device Portal を使用できます。 [アプリ] ページにアクセスし、PackageRelativeID 行 ("!" の前のすべての情報) を確認します。Is your **PackageFamilyName**.

3. You will then see that you have a new section, **ApplicationFile**. この領域を使って appx バンドルをアップロードします。

4. アプリを購入したのか、独自の LOB アプリを構築したのかによって、ライセンス ファイルまたはセキュリティ証明書をアップロードする必要があります。

    - ライセンス ファイルの場合: **UniversalAppInstall**  >  **UserContextAppLicence**に移動し、ライセンスの場所を参照してアップロードします。
    - セキュリティ ファイルの場合は、[証明書] **に移動** し、.appx バンドルと共にインストールする証明書を選択します。

プロジェクトは安全な場所に保存してください。 次 **に、** プロビジョニング パッケージ **としてエクスポートします**。  

関連: [HoloLens にプロビジョニング パッケージを適用します](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)。
