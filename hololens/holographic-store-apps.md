---
title: アプリケーションの検索、インストール、およびアンインストール
description: Microsoft Store は、HoloLens で動作するアプリやゲーム用のソースです。  Holographic アプリの検索、インストール、アンインストールの詳細については、こちらを参照してください。
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 9/7/2021
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
ms.openlocfilehash: 4705112ee41ce6de0598358b9c81775f261bb2fa
ms.sourcegitcommit: 8a3f925d2bda13c095b35f14d80afdd876aa859c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2021
ms.locfileid: "129800557"
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
>
> - x86 = HoloLens (第 1 世代)
> - ARM = HoloLens 2

> [!NOTE]
> 2021 年 1 月 12 日に、以下のアプリが HoloLens デバイスでサポートが終了します。 アプリの Web バージョンを使用するには、デバイスで次のリンクを使用することをお勧めします。

| アプリ        | Link                                          |
|------------|-----------------------------------------------|
| Excel Mobile      | [https://office.live.com/start/Excel.aspx](https://office.live.com/start/Excel.aspx)      |
| Word Mobile       | [https://office.live.com/start/Word.aspx](https://office.live.com/start/Word.aspx)       |
| PowerPoint Mobile | [https://office.live.com/start/PowerPoint.aspx](https://office.live.com/start/PowerPoint.aspx) |

> [!NOTE]
> 現在、OneDrive アプリは、HoloLens の Azure AD アカウントではサポートされていません。 Microsoft OneDrive PWA アプリをダウンロードすることをお勧めします。 [アプリをダウンロードするには、こちらの手順に従ってください。]

## <a name="install-apps"></a>アプリのインストール

アプリをダウンロードするには、Microsoft アカウントでサインインする必要があります。 無料のアプリもあり、すぐにダウンロードできます。 購入が必要なアプリには、Microsoft アカウントを使用してストアにサインインし、有効な支払い方法をお持ちであることが必要です。

> [!NOTE]
> Microsoft Store で使用するアカウントは、サインインに使用するアカウントと同一のものである必要はありません。 職場または学校用の HoloLens アカウントを使用している場合、購入するには、Store アプリの個人用アカウントでサインインする必要がある場合があります。

> [!TIP]
> 支払い方法を設定するには、[account.microsoft.com](https://account.microsoft.com/) に移動し、 **[支払いと請求]**  >  **[支払いオプション]**  >  **[Add a payment option]\(支払いオプションの追加\)** を選択します。

1. [ **[スタート]** メニュー](holographic-home.md)を開くには、HoloLens (第 1 世代) で [スタート ジェスチャ](/hololens/hololens2-basic-usage#start-gesture)または [ブルーム](hololens1-basic-usage.md) ジェスチャを実行します。

1. Microsoft Store アプリを選択します。 Store アプリが開いたら、次の手順を実行します。
   1. 検索バーを使用してアプリケーションを検索します。
   1. 整理されたカテゴリのいずれかの中から、必須アプリや HoloLens 専用に作成されたアプリを選択します。
   1. Store アプリの右上で、 **[...]** ボタンを選択し、 **[マイ ライブラリ]** を選択して、以前購入したアプリを表示します。

1. アプリケーションのページで、 **[取得]** または **[インストール]** (購入が必要になる場合があります) を選択します。

### <a name="install-microsoft-onedrive-pwa-app"></a>Microsoft OneDrive PWA アプリをインストールする

> [!NOTE]
> Microsoft Intune / MDM 経由で PWA を管理または展開することはできません。

前提条件: ユーザーは既に HoloLens 2 デバイスを作業テナントに参加させていること。

1. [スタート] メニューを開いて Edge ブラウザーを起動します。

    ![[スタート] メニュー](images/office-pwa-1.jpg)

1. HoloLens で [https://onedrive.live.com/about/signin](https://onedrive.live.com/about/signin) にアクセスし、職場アカウントの資格情報を入力します

    ![職場のサインイン](images/office-pwa-2.jpg)

1. OneDrive Web ポータルに正常にログインしたら、PWA ダウンロード ボタンが表示されるまで 30 から 60 秒待ちます

    ![PWA インストール ボタン](images/office-pwa-3.jpg)

1. PWA ダウンロード ボタンを選択してアプリをインストールします

    ![インストールのプロンプト](images/office-pwa-4.jpg)

1. Edge ブラウザーを閉じ、[スタート] メニューから **[すべてのアプリ]** ボタンを選択して、 **[Microsoft OneDrive]** というラベルが付いた OneDrive PWA アプリを起動します

    ![両方のアプリが表示されている [すべてのアプリ]。](images/office-pwa-5.jpg)

    > [!NOTE]
    > "Microsoft OneDrive" は PWA アプリですが、"OneDrive" は古い UWP です。

1. これで、OneDrive ファイルを表示できます。

    ![OneDrive PWA](images/office-pwa-6.jpg)

関連項目: [ビジネスのための OneDrive への自動アップロードの有効化](hololens-release-notes.md#onedrive-for-work-or-school-camera-roll-upload)

## <a name="update-apps"></a>アプリを更新する

### <a name="manual-updates"></a>手動更新

Microsoft Store からインストールしたアプリを更新するには、Microsoft Store アプリからアプリを更新できます。 ビジネス向け Microsoft Store 用にインストールされたアプリの場合には、ビジネス向け Microsoft Store からそれらのアプリを更新することもできます。

1. [ **[スタート]** メニュー](holographic-home.md)を開くには、HoloLens (第 1 世代) で [スタート ジェスチャ](/hololens/hololens2-basic-usage#start-gesture)または [ブルーム](hololens1-basic-usage.md) ジェスチャを実行します。

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

### <a name="automatic-app-updates"></a>アプリの自動更新

自動更新は Microsoft Store またはビジネス向け Microsoft Store のアプリに適用され、Store から直接インストールされている場合にのみ、自動的に更新できます。 Intune からインストールした場合は、ビジネス向け Microsoft Store の利用可能な最新バージョンのアプリと同期することで、MDM から更新プログラムを取得できます。

> [!NOTE]
> ビジネス向け Microsoft Store から入手したアプリの場合、Store にサインインし、デバイスで使用されるビジネス向け Microsoft Store カタログに関連付けられているのと同じテナントで認証を行う必要があります。

#### <a name="how-automatic-updates-work"></a>自動更新の仕組み

アプリの自動更新は、ネットワークの可用性に応じて、毎日 (約 24 時間ごとに) 実行されるようにスケジュールされています。 更新プログラムを受け取るには、デバイスをアクティブ状態または AC に接続した状態のままにしてください。 アプリの更新プログラムは、1 日のうちで活発に使用されている期間中にダウンロードされた場合でも、適用されるのは更新対象のアプリが使用されていないときだけです。

> [!TIP]
> 可能であれば、企業ネットワークに接続した状態で夜間にデバイスを充電してください。 更新プログラムを夜間にダウンロードしてインストールできる場合、デバイスの活発な使用が中断される可能性が低くなります。

#### <a name="how-it-administrators-can-control-automatic-updates"></a>IT 管理者が自動更新を制御する方法

IT 管理者は、[ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) ポリシーを使用して、アプリの自動更新を制御できます。 このポリシーを使用すると、アプリの自動更新を完全に有効または無効にすることはできますが、更新が行われるタイミングは制御されません。

[21H2](hololens-release-notes.md#windows-holographic-version-21h1) からは、IT 管理者は [ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures) ポリシーを使用して、使用中ではあったが以前の試行で更新できなかったアプリを、強制的に再起動するタイミングを制御できます。

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
