---
title: HoloLens のカスタムアプリを管理する (第1世代)
description: デバイスポータルと Visual Studio を使用して、カスタム holographic アプリを HoloLens デバイスにインストール、アンインストール、およびサイドロードする方法について説明します。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens、サイドロード、サイドロード、サイドロード、ストア、uwp、アプリ、インストール
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
ms.openlocfilehash: 721c169c8ad34acab6914448af8ffc6ceec97a0e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309308"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>HoloLens のカスタムアプリを管理する (第1世代)

HoloLens は、Microsoft Store からの多くの既存アプリケーションと、HoloLens 専用に構築された新しいアプリをサポートしています。 この記事では、カスタム holographic アプリケーションに焦点を当てています。  

ストアアプリの詳細については、「 [ストアアプリを使用したアプリの管理](holographic-store-apps.md)」を参照してください。

> [!IMPORTANT]
> HoloLens (第1世代) 用に次の情報が作成されました。この時点では、HoloLens Developer Edition とも呼ばれています。 このようなサイドローディングアプリは、デバイスポータルを使用して、Visual Studio でアプリをインストールすることが一般的でした。 エンタープライズ展開では、開発者モードを有効にしないことをお勧めします。これらの方法はどちらも使用します。 セキュリティで保護されたアプリのデプロイ方法に関心がある場合は、 [アプリ管理の概要](app-deploy-overview.md)に関する記事をご覧ください。
>
> HoloLens 2 デバイスに対して開発者向けのアプリのインストール方法をお探しの場合は、以下を参照してください。
> - [デバイスポータル: アプリのインストール](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Visual Studio を使用したアプリの配置とデバッグ](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>カスタム アプリをインストールする

デバイスポータルを使用するか、Visual Studio からアプリをデプロイして、独自のアプリケーションを HoloLens にインストールできます。

### <a name="installing-an-application-package-with-the-device-portal"></a>デバイスポータルを使用したアプリケーションパッケージのインストール

1. [デバイスポータル](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)からターゲット HoloLens への接続を確立します。

1. 左側のナビゲーションで、[ **アプリ** ] ページに移動します。

1. [ **アプリパッケージ** ] の下で、アプリケーションに関連付けられている .appx ファイルを参照します。

   > [!IMPORTANT]
   > 関連する依存関係および証明書ファイルを必ず参照してください。

1. **[Go] \(移動)** を選択します。

   > [!div class="mx-imgBorder"]
   > ![Microsoft HoloLens の Windows デバイスポータルでアプリフォームをインストールする](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>Microsoft Visual Studio 2015 からの展開

1. アプリの Visual Studio ソリューション (.sln ファイル) を開きます。

1. プロジェクトの **プロパティ** を開きます。

1. 次のビルド構成を選択します: **マスター/x86/リモートコンピューター**。

1. [ **リモートコンピューター**] を選択した場合:
   - アドレスが HoloLens の Wi-Fi IP アドレスを指していることを確認してください。
   - 認証を **Universal (暗号化** されていないプロトコル) に設定します。
   
1. ソリューションをビルドします。

1. 開発用 PC から HoloLens にアプリをデプロイするには、[ **リモートコンピューター**] を選択します。 HoloLens に既存のビルドが既に存在する場合は、[ **はい]** を選択して、この新しいバージョンをインストールします。  

   ![Visual Studio でのアプリの Microsoft HoloLens へのリモートコンピューターの展開](images/vs2015-remotedeployment.jpg)  
   
1. アプリケーションが HoloLens にインストールされ、自動的に起動します。

アプリをインストールすると、[**すべてのアプリ**] の一覧に表示されます ([すべてのアプリを **開始**]  >  )。
