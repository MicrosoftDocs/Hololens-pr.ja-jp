---
title: プロビジョニングパッケージ
description: アプリ、アプリの展開、エンタープライズアプリの demployment、プロビジョニング
keywords: アプリ、アプリの展開、エンタープライズアプリの demployment、プロビジョニング
author: v-jodben
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
ms.openlocfilehash: 7417f9e8cf1921d9fdb57dbd96fff094e21c44f9
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857952"
---
# プロビジョニングパッケージ

プロビジョニングパッケージを使用すると、エンドポイントの管理にアクセスせずに、環境内のデバイスを準備して構成することができます。 また、ユーザーの id、登録状態、不在時のエクスペリエンス (OOBE) 中にデバイスに展開したり、[セットアップ時にプロビジョニングパッケージを適用](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)したりすることもできます。

## プロビジョニングパッケージに関する考慮事項:
* 非パブリックアプリ
* USB サイドロードのみ
* 自動更新なし (PPKGs 経由で手動で更新する必要があります)

> [!NOTE] 
> HoloLens デバイスのプロビジョニングパッケージの作成の基本については、「 [Hololens プロビジョニング](https://docs.microsoft.com/hololens/hololens-provisioning)」を参照してください。 アプリを展開するには、advanced provisioning から始める必要があります。 

## セットアップ

[Windows 構成デザイナー](https://www.microsoft.com/store/productId/9NBLGGH4TX22)では、次の4つの手順を実行します。

1. ApplicationManagement/AllowAllTrustedApps を "Yes" に設定します。 「 [Applicationmanagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)」を参照してください。
2. **UniversalAppInstall**  >  **UserContextAppLicense**の下で、[**パッケージ efamilyname**] を入力してください。 「 [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall)」をご覧ください。 「 [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)」も参照してください。
    - この情報がわからない場合は、既にアプリをインストールしているデバイスで Device Portal を使うことができます。 [アプリ] ページにアクセスして、"!" の前にあるすべての情報を PackageRelativeID の行で確認します。は、整理された**名前**です。
3. これにより、新しいセクションの**Applicationfile**が表示されます。 この領域を使用して、appx バンドルをアップロードします。 
4. アプリを購入したか、独自の LOB アプリを作成したかに応じて、ライセンスファイルまたはセキュリティ証明書をアップロードする必要があります。
    - ライセンスファイルの場合: [ **UniversalAppInstall**  >  **usercontext]** の下で、ライセンスの場所を参照してアップロードします。 
    - セキュリティファイルの場合 [**証明書**] に移動し、証明書を選択して、.appx バンドルと共にインストールします。 

セキュリティで保護された場所にプロジェクトを保存してください。 次に、**プロビジョニングパッケージ**として**エクスポート**します。  
    
「 [HoloLens にパッケージを適用する](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)」もご覧ください。
