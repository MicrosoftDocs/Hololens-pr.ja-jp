---
title: アプリケーションの検索、インストール、およびアンインストール
description: Microsoft Store は、HoloLens で動作するアプリやゲーム用のソースです。  Holographic アプリの検索、インストール、アンインストールの詳細については、こちらを参照してください。
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 10/27/2020
manager: jarrettr
keywords: Hololens, Store, UWP, アプリ, インストール
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: bbbc60decb74942bd7930afb04297f78df33028a
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635859"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>Microsoft Store のアプリケーションの検索、インストール、アンインストール

Microsoft Store は、HoloLens で動作するアプリやゲーム用のソースです。 HoloLens で Store に移動すると、そこに表示されているアプリはすべてその上で動作します。

HoloLens 上のアプリは、2D ビューとホログラフィック ビューのどちらかを使用しています。 2D ビューを利用したアプリは窓のように見えて、周り全体に配置されます。 ホログラフィック ビューを使用しているアプリでは、見えるのは周り一面アプリの画面だけになります。

HoloLens では、Microsoft Store の多くの既存のアプリケーションと、HoloLens 専用に構築された新しいアプリがサポートされています。  この記事では、Microsoft Store のホログラフィック アプリケーションについて説明します。

カスタム アプリのインストールと実行の詳細については、[カスタム ホログラフィック アプリケーション](holographic-custom-apps.md)に関する記事を参照してください。

## <a name="find-apps"></a>アプリを検索する

**[スタート]** メニューから Microsoft Store を開きます。 アプリやゲームを参照します。 [音声コマンド](hololens-cortana.md)を使用し、"検索" と声に出して検索できます。検索ウィンドウが表示されたら、"ディクテーションを開始" と声に出し、プロンプトが表示されたら、検索語句を読み上げます。

> [!NOTE]
> HoloLens デバイスのシステム要件は、アプリのビルドのアーキテクチャに基づいています。 HoloLens (第 1 世代) のアプリのビルドが、ARM アーキテクチャ パッケージを含めるようにストアの新しい UWP に更新されていない場合、HoloLens 2 デバイスでは使用できません。 同様に、HoloLens 2 アプリに x86 アーキテクチャパッケージが含まれていない場合は、HoloLens (第 1 世代) デバイスでは使用できません。 HoloLens デバイス アーキテクチャ:
> - x86 = HoloLens (第 1 世代)
> - ARM = HoloLens 2

> [!NOTE]
> 2021 年 1 月 12 日に、以下のアプリが HoloLens デバイスでサポートが終了します。 アプリの Web バージョンを使用するには、デバイスで次のリンクを使用することをお勧めします。

| アプリ        | Link                                          |
|------------|-----------------------------------------------|
| Excel Mobile      | https://office.live.com/start/Excel.aspx      |
| Word Mobile       | https://office.live.com/start/Word.aspx       |
| PowerPoint Mobile | https://office.live.com/start/PowerPoint.aspx |

## <a name="install-apps"></a>アプリのインストール

アプリをダウンロードするには、Microsoft アカウントでサインインする必要があります。 無料のアプリもあり、すぐにダウンロードできます。 購入が必要なアプリには、Microsoft アカウントを使用してストアにサインインし、有効な支払い方法をお持ちであることが必要です。

> [!NOTE]
> Microsoft Store で使用するアカウントは、サインインに使用するアカウントと同一のものである必要はありません。 職場または学校用の HoloLens アカウントを使用している場合、購入するには、Store アプリの個人用アカウントでサインインする必要がある場合があります。

> [!TIP]
> 支払い方法を設定するには、[account.microsoft.com](https://account.microsoft.com/) に移動し、 **[支払いと請求]**  >  **[支払いオプション]**  >  **[Add a payment option]\(支払いオプションの追加\)** を選択します。

1. [ **[スタート]** メニュー](holographic-home.md)を開くには、HoloLens (第 1 世代) で[スタート ジェスチャ](/hololens/hololens2-basic-usage#start-gesture)または[ブルーム](hololens1-basic-usage.md) ジェスチャを実行します。

1. Microsoft Store アプリを選択します。 Store アプリが開いたら、次の手順を実行します。
   1. 検索バーを使用してアプリケーションを検索します。 
   1. 整理されたカテゴリのいずれかの中から、必須アプリや HoloLens 専用に作成されたアプリを選択します。
   1. Store アプリの右上で、 **[...]** ボタンを選択し、 **[マイ ライブラリ]** を選択して、以前購入したアプリを表示します。

1. アプリケーションのページで、 **[取得]** または **[インストール]** (購入が必要になる場合があります) を選択します。

## <a name="update-apps"></a>アプリを更新する

Microsoft Store からインストールしたアプリを更新するには、Microsoft Store アプリからアプリを更新できます。 ビジネス向け Microsoft Store 用にインストールされたアプリの場合には、ビジネス向け Microsoft Store からそれらのアプリを更新することもできます。 

1. [ **[スタート]** メニュー](holographic-home.md)を開くには、HoloLens (第 1 世代) で[スタート ジェスチャ](/hololens/hololens2-basic-usage#start-gesture)または[ブルーム](hololens1-basic-usage.md) ジェスチャを実行します。

1. Store アプリを選択します。

1. Store アプリの右上に注目します。 

1. **[...]** または [詳細を表示] ボタンを選択します。

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store アプリのスクリーンショット。](images/store-update-1.png)

1. **[ダウンロードおよび更新]** を選択します。
    1. 使用しているデバイスで以前に更新プログラムが特定されている場合、下向きの矢印と保留中の更新プログラムを表す数字が表示されます。

1. **[更新プログラムの入手]** を選択します。 デバイスによって更新プログラムが検索され、ダウンロードしてインストールするように設定されます。 
 
   > [!div class="mx-imgBorder"]
   > ![Microsoft Store アプリによる更新プログラムの取得のスクリーンショット。](images/store-update-2.png.jpg)

> [!NOTE]
> お使いのデバイスのアプリが組織によって配布されている場合は、同じ商用アプリ管理方法で更新できます。 お客様の状況に当てはまる場合は、[商用アプリの展開の概要](app-deploy-overview.md)に関する記事を参照してください。
>
> サイドロードまたは導入されているカスタム アプリを更新する場合は、更新されたバージョンのアプリで同じ方法を使用する必要があります。 カスタム アプリのインストールと実行の詳細については、[カスタム ホログラフィック アプリケーション](holographic-custom-apps.md)に関する記事を参照してください。

## <a name="uninstall-apps"></a>アプリのアンインストール

アプリケーションをアンインストールするには、3 つの方法があります。 アプリケーションをアンインストールするには、Microsoft Store、[スタート] メニュー、または [設定] を使用します。 

> [!WARNING]
> システム アプリまたは Microsoft Store 自体をアンインストールすることはできません。

> [!IMPORTANT]
> 複数のユーザーで HoloLens 2 を使用している場合、アプリをアンインストールするには、それをインストールしたユーザーとしてログインする必要があります。 

### <a name="uninstall-from-the-microsoft-store"></a>Microsoft Store からアンインストールする

**[スタート]** メニューから Microsoft Store を開き、アンインストールするアプリケーションを表示します。  Store ページでは、インストールされている各アプリケーションに **[アンインストール]** ボタンが表示されます。

### <a name="uninstall-from-the-start-menu"></a>[スタート] メニューからアンインストールする

**[スタート]** メニューまたは **[すべてのアプリ]** 一覧で、アプリを参照します。 メニューが表示されるまで長押しして、**[アンインストール]** を選択します。

### <a name="uninstall-from-settings"></a>[設定] からアンインストールする
**[スタート]** メニューで **[設定] > [アプリ]** を選択します。 一覧でアプリを見つけ、それを選択し、**[アンインストール]** をクリックします。

アプリをアンインストールできない場合は、フィードバック Hub を使用して[フィードバック](/hololens/hololens-feedback)をお送りください。
