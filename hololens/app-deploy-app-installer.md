---
title: HoloLens 2 アプリインストーラーを使用してアプリをサイドロードおよびインストールする方法
description: UI を使用したスライドの読み込みとアプリのインストール
keywords: アプリ管理、アプリ、hololens、アプリインストーラー
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
ms.openlocfilehash: 2387c0eb65efc312db4eea7118f3cca44ce6d4b6
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027478"
---
# アプリインストーラーを使用して HoloLens 2 にアプリをインストールする

ユーザーは、開発者モードを有効にしたり、Device Portal を使用したりする必要がないので、Appx バンドルを使ってアプリをインストールできるようになりました。 このエクスペリエンスは、ローカルデバイスにアプリをインストールしたり、HoloLens で他のアプリのインストール方法に慣れていない他のユーザーとアプリを共有したりする場合に簡単です。 

> [!IMPORTANT]
> この機能は、現時点では、Windows Insider ビルド 19041.1377 + でのみ avalible になっています。 [詳細については、「Windows Insider ビルドに登録する」を参照して](hololens-insider.md)ください。

> [!NOTE]
> アプリのインストーラーでストアからの依存関係が使用されるため、アプリのソリューション構成は **Master** または **Release** のいずれかである必要があります。 詳細については、「 [アプリパッケージの作成](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)」を参照してください。

1.  HoloLens 2 デバイスの電源が入っていて、サインインしていることを確認します。
1.  PC でカスタムアプリに移動し、yourapp を yourdevicename\Internal Storage\Downloads. にコピーします。 
    ファイルのコピーが完了したら、デバイスを切断して、後でインストールを完了することができます。
1.  HoloLens 2 デバイスから [ **スタート] メニュー**を開き、[ **すべてのアプリ** ] を選択して、 **エクスプローラー** アプリを起動します。
1.  [ダウンロード] フォルダーに移動します。 アプリの左側のパネルで、[ **このデバイス** ] を選択してから、[ダウンロード] に移動することが必要な場合があります。
1.  Yourapp ファイルを選びます。 
1.  アプリのインストーラーが起動します。 アプリをインストールするには、[ **インストール** ] ボタンを選択します。 

インストールされたアプリは、インストールの完了時に自動的に起動します。 

![App Installer による MRTK の例のインストール](images/hololens-app-installer-picture.jpg)

アプリのインストールに失敗した場合は、次のことを確認してください。
-   アプリがマスターまたはリリースビルドのどちらかです。
-   [インターネットに接続](hololens-network.md)されています。
-   [Microsoft Store のエンドポイント](hololens-offline.md)が適切に構成されている。  
