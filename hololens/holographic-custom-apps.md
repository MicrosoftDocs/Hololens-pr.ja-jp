---
title: HoloLens (第 1 世代) 用のカスタム アプリを管理する
description: デバイス ポータル と Visual Studio を使用して、HoloLens デバイスにカスタム ホログラフィック アプリをインストール、アンインストール、サイド ロードする方法について説明します。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, サイドロード, サイドロード, サイドロード, ストア, uwp, アプリ, インストール
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: b6769c36f821ee3619ac9b62efd637ac561192bb
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033107"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>HoloLens (第 1 世代) 用のカスタム アプリを管理する

HoloLensは、Microsoft Store アプリケーション専用に構築された新しいアプリだけでなく、HoloLens。 この記事では、カスタム ホログラフィック アプリケーションについて説明します。  

ストア アプリの詳細については、「ストアを使用してアプリ [を管理する」を参照してください](holographic-store-apps.md)。

> [!IMPORTANT]
> 次の情報は、HoloLens (第 1 世代) に対して作成され、HoloLens Developer Edition とも呼ばされています。 そのため、デバイス ポータル経由でアプリをサイドローディングし、アプリをインストールする方法Visual Studio一般的でした。 エンタープライズデプロイの場合は、開発者モードを有効にすることをお勧めしません。どちらの方法でも使用されます。 セキュリティで保護されたアプリの展開方法に関心がある場合は、アプリ管理の概要に関する [ページを参照してください](app-deploy-overview.md)。
>
> デバイスのアプリインストールの開発者向け方法を探している場合は、HoloLens 2を参照してください。
>
> - [デバイス ポータル: アプリのインストール](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [アプリVisual Studioを使用してアプリをデプロイおよびデバッグする](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>カスタム アプリをインストールする

独自のアプリケーションを HoloLens にインストールするには、デバイス ポータル を使用するか、Visual Studio からアプリをデプロイします。

### <a name="installing-an-application-package-with-the-device-portal"></a>次のコマンドを使用してアプリケーション パッケージをインストールデバイス ポータル

1. クライアントからターゲット サーバー[デバイス ポータル](/windows/mixed-reality/using-the-windows-device-portal)接続を確立HoloLens。

1. 左側のナビゲーションで、[アプリ] ページ **に移動** します。

1. [ **アプリ パッケージ]** で、アプリケーションに関連付けられている .appx ファイルを参照します。

   > [!IMPORTANT]
   > 関連付けられている依存関係ファイルと証明書ファイルを参照してください。

1. **[Go] \(移動)** を選択します。

   > [!div class="mx-imgBorder"]
   > ![アプリ フォームを Windows デバイス ポータル にインストールMicrosoft HoloLens。](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>Microsoft Visual Studio 2015 からのデプロイ

1. アプリのソリューション (.sln Visual Studio開きます。

1. プロジェクトの [プロパティ] を **開きます**。

1. 次のビルド構成を選択します: **Master/x86/Remote Machine**。

1. [リモート コンピューター]**を選択すると、**
   - アドレスが、ご利用のデバイスのWi-Fi IP アドレスをポイントHoloLens。
   - 認証をユニバーサル **(暗号化されていないプロトコル) に設定します**。
   
1. ソリューションをビルドします。

1. 開発用 PC から自分のコンピューターにアプリをデプロイするにはHoloLens[リモート コンピューター]**を選択します**。 既存のビルドが既にインストールされている場合はHoloLens[はい]を選択して、この新しいバージョンをインストールします。  

   ![アプリのリモート コンピューターのデプロイがMicrosoft HoloLensにVisual Studio。](images/vs2015-remotedeployment.jpg)  
   
1. アプリケーションがインストールされ、アプリケーションが自動的に起動HoloLens。

アプリをインストールすると、[すべてのアプリ] の一覧 ([すべてのアプリを開始] )**に**  >  **表示されます**。
