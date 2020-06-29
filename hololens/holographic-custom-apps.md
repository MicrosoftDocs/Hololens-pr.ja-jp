---
title: HoloLens 用のカスタム アプリを管理する
description: HoloLens でカスタムアプリを読み込みます。 ホログラフィックアプリのインストールとアンインストールの詳細については、こちらを参照してください。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 07/01/2019
manager: v-miegge
keywords: hololens、サイドローディング、サイドロード、サイドロード、ストア、uwp、アプリ、インストール
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
- HoloLens 2
ms.openlocfilehash: 12c5eedfab580be8acea48c1fc19b56c1ead08ac
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828862"
---
# HoloLens 用のカスタム アプリを管理する

HoloLens では、Microsoft Store の既存のアプリケーションのほか、HoloLens 専用に構築された新しいアプリがサポートされています。 この記事では、カスタムのホログラフィックアプリケーションについて説明します。  

ストアアプリの詳細については、「[ストアを使用してアプリを管理する](holographic-store-apps.md)」を参照してください。

## カスタムアプリをインストールする

HoloLens に独自のアプリケーションをインストールするには、Device Portal を使用するか、Visual Studio からアプリを展開します。

### Device Portal でアプリケーションパッケージをインストールする

1. [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)からターゲット HoloLens への接続を確立します。
1. 左側のナビゲーションで、[**アプリ**] ページに移動します。
1. [**アプリパッケージ**] で、アプリケーションに関連付けられている .appx ファイルを参照します。
   > [!IMPORTANT]
   > 関連する依存関係と証明書ファイルを必ず参照してください。

1. [**移動**] を選びます。
   ![Microsoft HoloLens の Windows Device Portal でアプリフォームをインストールする](images/deviceportal-appmanager.jpg)

### Microsoft Visual Studio 2015 からの展開

1. アプリの Visual Studio ソリューション (.sln ファイル) を開きます。
1. プロジェクトの**プロパティ**を開きます。
1. 次のビルド構成を選択します: **Master/x86/リモートコンピューター**
1. [**リモートコンピューター**] を選択すると、次のようになります。
   - アドレスが HoloLens の Wi-fi IP アドレスを指していることを確認します。
   - 認証を**ユニバーサル (暗号化**されていないプロトコル) に設定します。
1. ソリューションを構築します。
1. 開発用 PC から HoloLens にアプリを展開するには、[**リモートコンピューター**] を選びます。 既存のビルドが HoloLens に既にある場合は、[**はい]** を選んで新しいバージョンをインストールします。  

   ![Visual Studio でのアプリのリモートコンピューターによる Microsoft HoloLens への展開](images/vs2015-remotedeployment.jpg)  
1. アプリは、HoloLens にインストールされ、自動起動します。

アプリをインストールすると、[**すべて**のアプリ] の一覧にアプリが表示されます (すべてのアプリを**起動**  >  **All apps**します)。
