---
title: HoloLens (第 1 世代) 用のカスタム アプリを管理する
description: Device Portal とデバイス ポータルを使用して、HoloLens デバイスにカスタム ホログラフィック アプリをインストール、アンインストール、サイド ロードする方法Visual Studio。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, サイドロード, サイドロード, サイドロード, ストア, UWP, アプリ, インストール
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
ms.sourcegitcommit: 4c6d982bee72195bef955532738711f2b00ac8be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "11296990"
---
# HoloLens (第 1 世代) 用のカスタム アプリを管理する

HoloLens は、HoloLens 用に特別に作られた新しいアプリだけでなく、Microsoft ストアにある既存のアプリケーションの多くもサポートします。 この記事では、カスタム ホログラフィック アプリケーションについて説明します。  

ストア アプリの詳細については、「ストアでアプリ [を管理する」を参照してください](holographic-store-apps.md)。

> [!IMPORTANT]
> 次の情報は、HoloLens (第 1 世代) (HoloLens Developer Edition とも呼ばれる) 用に作成されました。 そのため、デバイス ポータル経由でアプリをサイドローディングし、デバイス ポータルを使Visual Studioアプリをインストールする方法は一般的でした。 エンタープライズ展開では、両方の方法で使用する開発者モードを有効にすることをお勧めしません。 セキュリティで保護されたアプリの展開方法に関心がある場合は、「アプリ管理: 概要」を [確認してください](app-deploy-overview.md)。
>
> HoloLens 2 デバイス用のアプリのインストール方法を開発者向けにお探しの場合は、以下を参照してください。
> - [Device Portal: アプリのインストール](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [アプリVisual Studioを使用してアプリを展開およびデバッグする](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## カスタム アプリをインストールする

HoloLens に独自のアプリケーションをインストールするには、Device Portal を使用するか、デバイス ポータルからアプリを展開Visual Studio。

### Device Portal でのアプリケーション パッケージのインストール

1. Device Portal から [ターゲット HoloLens](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) への接続を確立します。

1. 左側のナビゲーションで、[アプリ] ページ **に移動** します。

1. [ **アプリ パッケージ]** で、アプリケーションに関連付けられている .appx ファイルを参照します。

   > [!IMPORTANT]
   > 関連付けられている依存関係ファイルと証明書ファイルを参照してください。

1. [移動 **] を選択します**。

   > [!div class="mx-imgBorder"]
   > ![Microsoft HoloLens の Windows Device Portal にアプリ フォームをインストールする](images/deviceportal-appmanager.jpg)

### Microsoft Visual Studio 2015 からの展開

1. アプリの新しいソリューションVisual Studio (.sln ファイル) を開きます。

1. プロジェクトのプロパティを開 **きます**。

1. 次のビルド構成を選択します **:Master/x86/Remote Machine**。

1. リモート コンピューターを **選択した場合**:
   - アドレスが HoloLens の Wi-Fi IP アドレスをポイントしている必要があります。
   - 認証を **ユニバーサル (暗号化されていないプロトコル) に設定します**。
   
1. ソリューションをビルドします。

1. 開発用 PC から HoloLens にアプリを展開するには、[リモート コンピューター] **を選択します**。 HoloLens に既にビルドがある場合は、[はい] **を選択して** この新しいバージョンをインストールします。  

   ![Microsoft HoloLens へのアプリのリモート コンピューター Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. アプリケーションが HoloLens にインストールされ、自動起動されます。

アプリをインストールすると、[すべてのアプリ] の一覧 ([**** すべてのアプリを起動] )**に**  >  **表示されます**。
