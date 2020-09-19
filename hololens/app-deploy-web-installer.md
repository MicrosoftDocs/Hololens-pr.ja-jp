---
title: Web Installer を使用してアプリをインストールする方法
description: Web installer for app installer を使ってアプリをインストールする
keywords: アプリ管理、アプリ、hololens、アプリインストーラー、web インストール
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 186cbefb2822455dcf922804ea09533b833b8663
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027477"
---
# Web ページからのアプリのインストール

ユーザーは、web サーバーから直接アプリをインストールできます。 これにより、アプリのインストーラーが、簡単なダウンロードとインストールの配布方法と組み合わされて使用できるようになります。 

> [!IMPORTANT]
> この機能は、現時点では、Windows Insider ビルド 19041.1366 + でのみ avalible になっています。 [詳細については、「Windows Insider ビルドに登録する」を参照して](hololens-insider.md)ください。

## 設定方法:
1.  アプリが正しくインストールされていることを確認します。
1.  [Web ページでこの機能を有効にするには、次の手順を](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)実行します。 
1.  証明書の展開方法を選択します。 
    1.  [プロビジョニングパッケージ](hololens-provisioning.md) はローカルデバイスに適用できます。
    1.  MDM を使って、 [デバイスの構成に証明書を適用](https://docs.microsoft.com/mem/intune/protect/certificates-configure)することができます。
    1.  デバイス [証明書マネージャー](hololens-insider.md#certificate-manager)を使用します。 

## エンドユーザーエクスペリエンス:
1.  ユーザーは、前に選択した方法を使用して、デバイスに証明書を受け取り、インストールします。 
1.  ユーザーは、上の手順で作成した URL にアクセスします。

これで、アプリがデバイスにインストールされます。 アプリを見つけるには、[ **スタート] メニュー** を開き、[ **すべてのアプリ** ] ボタンを選んでアプリを見つけます。 

-   このインストール方法のトラブルシューティングについては、「 [アプリインストーラーの問題のトラブルシューティング](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)」を参照してください。 

> [!NOTE]
> 更新プロセス中の UI はサポートされません。 そのため、 [このページ](https://docs.microsoft.com/windows/msix/app-installer/update-settings) と関連オプションの showprompt オプションはサポートされません。
