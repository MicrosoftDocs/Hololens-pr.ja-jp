---
title: HoloLens 2 のリリースノート
description: 新しい HoloLens 2 リリースごとに最新情報を入手できます。
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 02/16/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 554dc796ee793a3f7e81108c6eb614a9555f10d7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397343"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 のリリースノート

HoloLens デバイスの生産性を維持するために、今後も機能、バグ、およびセキュリティ更新プログラムをリリースします。 このページでは、1か月あたりの HoloLens の新機能を確認できます。 最新の HoloLens 2 更新プログラムを取得するには、 [更新プログラムを確認して手動で更新](hololens-update-hololens.md#check-for-updates-and-manually-update) するか、完全なフラッシュ更新プログラム (ffu) を取得して、 [Advanced Recovery コンパニオンでデバイスをフラッシュ](hololens-recovery.md#clean-reflash-the-device)します。 [ダウンロード](https://aka.ms/hololens2download)は最新の状態に保たれ、一般公開されている最新のビルドを提供します。

## <a name="windows-holographic-version-21h1"></a>Windows Holographic、バージョン21H1
- ビルド20346.1002

この更新プログラムには、2つの対象ユーザーのための機能が含まれています。エンドユーザーによってデバイス上のすべてのユーザーが使用できる機能と、IT 管理者が構成できる新しいデバイス管理オプション。 次の表は、各ユーザーに関連する機能を示しています。 IT 管理者の場合は、 [it 管理者の更新チェックリスト](#it-admin---update-checklist)を参照してください。
>[!IMPORTANT]
>このビルドに更新するには、HoloLens 2 デバイスが2021年2月の更新プログラム (ビルド 19041.1136) 以降を実行している必要があります。 この機能更新プログラムが利用可能になっていない場合は、まずデバイスを更新してから、もう一度お試しください。

>[!NOTE]
>現在、Microsoft HoloLens 2 では、次のリリースの月ごとのサービス更新 (バグおよびセキュリティの修正) がサポートされています。
>- Windows Holographic、バージョン 20H2 (Build 19041.1128 +)
>- Windows Holographic、バージョン 2004 (Build 19041.1103 +)
>- Windows Holographic、バージョン 1903 (Build 18362 +) 
>
> Windows Holographic バージョン21H1 の導入により、 **Windows Holographic バージョン1903の月単位のサービス更新プログラムを中止** します。 これにより、より新しいリリースに専念し、貴重な改善を続けることができます。 


| 機能名                                              | 簡単な説明                                                                      | 対象読者 | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [新しいMicrosoft Edge](#introducing-the-new-microsoft-edge)  | Chromium ベースの新しいMicrosoft Edgeは、新しいHoloLens 2。 | エンド ユーザー | 
[WebXR および 360 ビューアー](#webxr-and-360-viewer) | イマーシブ Web エクスペリエンスと 360 ビデオ再生をお試しください。 | エンド ユーザー | 
[新しい設定アプリ](#new-settings-app) | レガシ設定アプリは、新しい機能と設定で更新されたバージョンに置き換え中です。 | エンド ユーザー |
[色の調整を表示する](#display-color-calibration) | 表示する別の色プロファイルを選択HoloLens 2します。 | エンド ユーザー |
[既定のアプリ ピッカー](#default-app-picker) | ファイルまたはリンクの種類ごとに起動するアプリを選択します。 | エンド ユーザー |
[アプリごとのボリュームコントロール](#per-app-volume-control) | システム ボリュームとは独立してアプリ レベルのボリュームを制御します。 | エンド ユーザー |
[Web アプリをインストールする](#install-web-apps) | 新しいブラウザーを使用HoloLens 2、Microsoft Office Web アプリを Microsoft Edgeします。 | エンド ユーザー |
[スワイプして入力する](#swipe-to-type) | ホログラフィック キーボードで指のヒントを使用して単語を "スワイプ" します。 | エンド ユーザー |
[[スタート] の [電源] メニュー](#power-menu-from-start) | [スタート] メニューで、HoloLens デバイスを再起動してシャットダウンします。 | エンド ユーザー |
[[サインイン] 画面に表示される複数のユーザー](#multiple-users-listed-on-sign-in-screen) | [サインイン] 画面に複数のユーザー アカウントを表示します。 | エンド ユーザー |
[USB-C 外部マイクのサポート](#usb-c-external-microphone-support) | アプリやリモートアシスタンスで USB C マイクを使用します。 | エンド ユーザー |
[キオスクのビジター自動ログオン](#visitor-auto-logon-for-kiosks) | ビジターアカウントの自動ログオンをキオスクモードで使用できるようにします。 | IT 管理者 |
[キオスクモードでの新しいアプリの新しい AUMIDs](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | AUMIDs は、新しい設定とエッジアプリを対象としています。 | IT 管理者 |
[キオスクモードのエラー処理の改善](#kiosk-mode-behavior-changes-for-handling-of-failures) | キオスクモードでは、空のスタートメニューの前に、グローバルに割り当てられたアクセスを検索します。 | IT 管理者 |
[新しい Settingは、ページ設定の可視性を示します](#new-settings-uris-for-page-settings-visibility) | 20 + 新しい SettingPageVisibilityList は、Settings/ポリシーを対象としています。 | IT 管理者 |
[フォールバック診断の構成](#configuring-fallback-diagnostics-via-settings-app) | 設定アプリでフォールバック診断動作を設定しています。 | IT 管理者 |
[近くのデバイスとの共有](#share-things-with-nearby-devices) | HoloLens から PC にファイルまたは Url を共有します。 | すべて |
[新しい OS 診断トレース](#new-os-diagnostic-traces) | OS の更新の設定の新しいトラブルシューティング。 | IT 管理者 |
[配信の最適化のプレビュー](#delivery-optimization-preview) | 複数の HoloLens デバイスからのダウンロードの帯域幅の消費を削減します。 | IT 管理者 |

関連するリリースノートを確認する:

- [HoloLens Emulator アーカイブにアクセスする](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>新しい機能のMicrosoft Edge

![レガシ ロゴMicrosoft Edge新しいロゴへのMicrosoft Edgeアニメーション](images/new-edge.gif)

新しいMicrosoft Edge [Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) オープン ソース プロジェクトを採用して、顧客との互換性を向上し、Web 開発者向けの Web の断片化を減らします。

> [!IMPORTANT]
> この新しいMicrosoft Edgeは、新しいリリースMicrosoft Edgeサポートされなくなったレガシ バージョンを [自動的に置](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) き換える機能です。

![新しいMicrosoft Edgeスクリーンショット](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>新しいアプリケーションを起動Microsoft Edge

新しい Microsoft Edge ![新しいMicrosoft Edgeアイコン](images/new_edge_logo.png) (青と緑のスワイル アイコンで表されます) は スタート メニュー にピン留めされ、Web リンクをアクティブ化すると自動的に起動します。

> [!NOTE]
> アプリで新しいアプリをMicrosoft Edge HoloLens 2、設定とデータはレガシ データ からインポートMicrosoft Edge。 新しい Microsoft Edge を起動した後もレガシ Microsoft Edge を引き続き使用する場合、その新しいデータはレガシ Microsoft Edge から新しい Microsoft Edge に同期されません。

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>新しいポリシーのポリシー設定を構成Microsoft Edge

この新しいMicrosoft Edgeでは、IT 管理者は、従来のアプリケーションで以前に使用していたよりも、HoloLens 2 に対するブラウザー ポリシーのはるかに広範なセットを提供Microsoft Edge。

新しいアプリケーションのポリシー設定の管理の詳細については、次のリソースを参照Microsoft Edge。

- [次のMicrosoft Edgeポリシー設定を構成Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Microsoft Edge 従来版ポリシー マッピングMicrosoft Edgeする方法](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome を使用してMicrosoft Edgeマッピングを作成する](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Microsoft Edge Enterprise の [完全なドキュメント](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> 新しい Microsoft Edge でサポートされているブラウザー ポリシーの量が多いので、チームは新しい各ポリシーが HoloLens 2 で動作する保証を受けHoloLens 2。 ただし、以前に Microsoft Edge でサポートされている各レガシ Microsoft Edge ポリシーと同等の新しい HoloLens 2 を想定したテストと確認を行いました。 ポリシー [マッピングMicrosoft Edge 従来版をMicrosoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) Microsoft Edgeして、HoloLens 2 で使用していた各レガシ Microsoft Edge ブラウザー ポリシーに相当する新しい Microsoft Edge を見つける方法に関するページを参照HoloLens 2。
>
> HoloLens 2 では動作し *ないことが* わかっている Microsoft Edge ポリシーが2つ以上あります。
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>HoloLens 2 の新しい Microsoft Edge から期待されること

新しい Microsoft Edge は新しい UWP アダプターレイヤーを使用するネイティブ Win32 アプリであるため、HoloLens 2 などの UWP 専用デバイスで実行できますが、一部の機能がすぐに利用できない可能性があります。 今後数か月の間に新しいシナリオと機能をサポートするため、最新情報については、この領域を確認してください。

**動作が期待されるシナリオと機能:**
- 最初の実行エクスペリエンス、プロファイルへのサインイン、および同期
- Web サイトが期待どおりにレンダリングされ、動作する必要がある
- ほとんどのブラウザー機能 (お気に入り、履歴など) は期待どおりに機能します。
- ダーク モード
- デバイスへの web アプリのインストール
- 拡張機能をインストールしています (HoloLens 2 で正しく動作しない拡張機能を使用する場合は、お知らせください)
- PDF の表示とマークアップ
- 1つのブラウザーウィンドウからの空間サウンド
- ブラウザーの自動更新と手動更新
- [印刷] メニューから PDF を保存する ([PDF に保存] オプションを使用する)
- WebXR と360ビューアーの拡張機能
- 環境に配置されている複数のウィンドウを参照するときに、正しいウィンドウにコンテンツを復元する

**使用する予定のないシナリオと機能:**
- オーディオストリームが同時に使用される複数のウィンドウからの空間サウンド
- 「言ってください。
- 印刷

**ブラウザーの上位の既知の問題:**

- ホログラフィック キーボードの拡大鏡プレビューは、新しいウィンドウでMicrosoft Edge。 拡大が正しく機能したら、今後の更新プログラムでこの機能を再び有効にしてください。
- 別のブラウザー ウィンドウが開いてアクティブな場合、間違ったブラウザー ウィンドウからオーディオが再生される可能性があります。 この問題を回避するには、オーディオを再生しているはずの他のアクティブウィンドウを閉じます。
- "フォローする" モードでブラウザー[](hololens2-basic-usage.md#follow-me-stop-following)ウィンドウからオーディオを再生する場合、"フォローする" モードを無効にした場合、オーディオは再生を続行します。 この問題を回避するには、"フォローする" モードを無効にする前にオーディオ再生を停止するか **、X** ボタンでウィンドウを閉じます。
- アクティブなウィンドウMicrosoft Edge操作すると、他の 2D アプリ ウィンドウが予期せず非アクティブになる可能性があります。 これらのウィンドウは、もう一度操作することで再アクティブ化できます。

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider チャネル

このMicrosoft Edge、Edge Insider コミュニティで 3 つのプレビュー チャネル (ベータ、開発、カナリア) を利用できます。 プレビュー チャネルをインストールしても、HoloLens 2 にリリースされたバージョンの Microsoft Edge はアンインストールされません。また、複数のバージョンを同時にインストールできます。 

Edge Insider コミュニティ [Microsoft Edge詳細については、Microsoft Edge Insider](https://www.microsoftedgeinsider.com) のホームページを参照してください。 さまざまな Edge Insider チャネルの詳細と使用を開始するには、Edge Insider のダウンロード [ページを参照してください](https://www.microsoftedgeinsider.com/download)。

Insider チャネルをインストールしてインストールするには、次Microsoft Edgeいくつかの方法HoloLens 2。

**デバイスへの直接インストール (現在はアンマネージド デバイスでのみ使用可能)**
  1. お使HoloLens 2 Edge Insider ダウンロード ページ [にアクセスします](https://www.microsoftedgeinsider.com/download)。
  1. インストールする **Edge Insider チャネルHoloLens 2** の [ダウンロード] ボタンを選択します。
  1. ダウンロードした .msix ファイルを Edge ダウンロード キューから、またはデバイスの "ダウンロード" フォルダーから起動します (エクスプローラー)。
  1. [アプリ インストーラーが](app-deploy-app-installer.md) 起動します。
  1. **[インストール]** ボタンを選択します。
  1. インストールが正常に完了したら、[スタート] メニューの [ **すべてのアプリ** ] の一覧に、別のエントリとして Microsoft Edge Beta、Dev、またはカナリアが表示されます。

**Windows デバイスポータルを使用して PC 経由でインストールする (HoloLens 2 で [開発者モード](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) が有効になっている必要があります)**
  1. PC で、 [Edge Insider ダウンロードページ](https://www.microsoftedgeinsider.com/download)にアクセスします。
  1. インストールする Edge Insider channel の [Windows 10 用ダウンロード] ボタンの横に **あるドロップダウン矢印ボタン** を選択します。
  1. ドロップダウンメニューで [ **HoloLens 2** ] を選択します。
  1. Msix ファイルを PC の "ダウンロード" フォルダー (または簡単に見つけられる別のフォルダー) に保存します。
  1. PC で [Windows デバイスポータル](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) を使用して、HoloLens 2 にダウンロードした msix ファイルをインストールします。
  1. インストールが正常に完了したら、[スタート] メニューの [ **すべてのアプリ** ] の一覧に、別のエントリとして Microsoft Edge Beta、Dev、またはカナリアが表示されます。

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>WDAC を使用して新しい Microsoft Edge をブロックする

IT 管理者が、新しい Microsoft Edge アプリをブロックするために、 [WDAC ポリシー](windows-defender-application-control-wdac.md) を更新することを検討している場合は、ポリシーに次のものを追加する必要があります。

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>新しい Microsoft Edge のエンドポイントを管理する

環境によっては、考慮として考慮する必要があるネットワークの制限がある場合があります。 新しいエッジでスムーズにエクスペリエンスを確保するには、[これらの Microsoft エンドポイントを有効に](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)してください。

HoloLens で現在使用できる [エンドポイント](hololens-offline.md)の詳細については、こちらを参照してください。

### <a name="install-web-apps"></a>Web アプリのインストール
 > [!Note]
>[Windows Holographic バージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1)では、Office web アプリはプレインストールされなくなりました。

新しいエッジを使用して、Microsoft Store アプリと共に web アプリをインストールできます。 たとえば、Microsoft Office web アプリをインストールして、SharePoint または OneDrive でホストされているファイルを表示および編集できます。 Office web アプリをインストールするには、にアクセス https://www.office.com して、[ **アプリで利用可能** ] または [ **office のインストール** ] ボタンをアドレスバーにクリックします。 [ **インストール** ] を選択して確認します。

> [!IMPORTANT]
> Office Web アプリの機能は、お使HoloLens 2インターネットに接続している場合にのみ使用できます。

### <a name="webxr-and-360-viewer"></a>WebXR および 360 ビューアー

新しいMicrosoft Edge WebXR のサポートが含まれています。これは、イマーシブ Web エクスペリエンスを作成するための新しい標準です (WebVR の置き換え)。 多くのイマーシブ Web エクスペリエンスは、VR を念頭に置いて設計されました (実際の視野を仮想環境に置き換えます)。ただし、これらのエクスペリエンスは、仮想環境HoloLens 2。 WebXR 標準では、物理環境を使用する拡張および Mixed Reality のイマーシブ Web エクスペリエンスも可能になります。 開発者が WebXR に多くの時間を費やすと、新しい拡張および Mixed Reality イマーシブ エクスペリエンスが、お客様HoloLens 2試しに来る予定です。

360 Viewer 拡張機能は WebXR 上に構築され、新しいバージョンと共に自動的にインストールされ、Microsoft EdgeにHoloLens 2。 この Web 拡張機能を使用すると、360 度のビデオに取り入れすることができます。 YouTube では最大 360 本の動画が提供されています。そのため、最初から開始してください。

#### <a name="how-to-use-webxr"></a>WebXR を使用する方法

1. WebXR がサポートされている Web サイトに移動します。
1. Web サイトの **[VR の入力** ] ボタンを選択します。 このボタンの場所と視覚的な表現は、Web サイトごとに異なる場合がありますが、次のような場合があります。

    ![ENTER VR ボタンの例](images/75px-enter-vr.png)

1. 特定のドメインで初めて WebXR エクスペリエンスを起動しようとすると、ブラウザーはイマーシブ ビューに入る同意を求め、許可を選択 **します**。
1. ジェスチャ [HoloLens 2使用して](hololens2-basic-usage.md#the-hand-tracking-frame) 、エクスペリエンスを操作します。
1. エクスペリエンスに [終了] ボタンが表示しない **場合は、**[開始ジェスチャを使用して](hololens2-basic-usage.md#start-gesture)戻ります。

**推奨される WebXR サンプル**
- 360 ビューアー (次のセクションを参照)
- [XR 恐竜](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR ペイント](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>360ビューアーの使用方法

1. YouTube の360度のビデオに移動します。
1. ビデオフレームで、[mixed reality ヘッドセット] ボタンを選択します。

    ![360ビューアーをアクティブにするためのボタン](images/enter-360-viewer.jpg)

1. 特定のドメインで 360 Viewer を初めて起動しようとすると、ブラウザーによって、イマーシブビューへの入力に同意するように求めるメッセージが表示されます。 **[許可]** を選択します。
1. 再生コントロールを表示するための[エアタップ](hololens2-basic-usage.md#select-using-air-tap)。 [ハンド光線とエアタップ](hololens2-basic-usage.md#select-using-air-tap)を使用して、再生/一時停止、前方/後方へのスキップ、キャプションのオン/オフの切り替え、またはエクスペリエンスの停止 (イマーシブビューを終了) を行います。 再生コントロールは、数秒の非アクティブな状態で表示されなくなります。

#### <a name="top-webxr-and-360-viewer-known-issues"></a>上位の WebXR と360のビューアーに関する既知の問題
- WebXR エクスペリエンスの複雑さによっては、フレームレートが低下したり、途切れたりする可能性があります。
- WebXR での標準の関節のサポートは、既定では有効になっていません。 開発者は `edge://flags` 、"WebXR 手書き入力" をオンにすることで、を使用してサポートを有効にできます。
- 360 YouTube 以外の web サイトからのビデオが想定どおりに動作しないことがあります。

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>WebXR と360ビューアーに関するフィードバックの提供

新しい Microsoft Edge の **フィードバックの送信** 機能を使用して、フィードバックとバグをチームと共有してください。

### <a name="new-settings-app"></a>新しい設定アプリ

今回のリリースでは、設定アプリの新しいバージョンが導入されています。 新しい設定アプリには、次の領域における HoloLens 2 の新機能と拡張設定が含まれています。サウンド、電源 & スリープ、ネットワーク & インターネット、アプリ、アカウント、使いやすさなどです。

> [!NOTE]
> 新しい設定アプリは従来の設定アプリとは異なっているので、以前に環境の周囲に配置した設定ウィンドウは、更新時に削除されます。

![新しい設定アプリのホームページ](images/new-settings-app.png)

**新機能と設定**
- 設定検索: キーワードまたは設定の名前を使用して、設定ホームページから設定を検索します。
- System > Sound:
  - 入出力オーディオ デバイス: 入力および出力オーディオ デバイスを個別に選択します (たとえば、Bluetooth ヘッドセットを介してオーディオをリッスンしたり、オーディオ入力に USB-C マイクを使用したりします)。
    > [!NOTE]
    > Bluetooth マイクは、HoloLens 2 ではサポートHoloLens 2。
  - アプリのボリューム: 各アプリのボリュームを個別に調整します。 アプリ [ごとのボリューム コントロールに関するページを参照してください](#per-app-volume-control)。
- System > Power & スリープ: 非アクティブな期間が続くとデバイスがスリープ状態に戻る時期を選択します。
- システム >バッテリ: 手動でバッテリー節約機能モードを有効にするか、バッテリのしきい値を設定します。この時点で、バッテリー節約機能が自動的にオンになります。
- USB >デバイス: 既定で USB 接続を無効にできます。
- ネットワーク & インターネット:
  - USB-C イーサネット アダプターは、ネットワーク 接続とインターネット&されます。
  - USB-C イーサネット アダプターの設定 (IP アドレスを含む) が利用可能になっています。
  - これで、デバイスで航空機モードを有効HoloLens 2。
- アプリ: ファイルとリンクの種類に使用される既定のアプリをリセットできます。 詳細については、「既定のアプリ ピ [ッカー」を参照してください](#default-app-picker)。
- 他>アカウント: デバイス所有者は、ユーザーの追加、標準ユーザーのデバイス所有者へのアップグレード、デバイス所有者の標準ユーザーへのダウングレード、ユーザーの削除を行います。
- 簡単操作: テキスト サイズと視覚効果を変更します。

**既知の問題**
- 以前に配置した設定ウィンドウが削除されます (上のメモを参照してください)。
- 設定アプリでデバイスの名前を変更することはできなくなりました。 IT 管理者は、HoloLens 2 デバイス名テンプレートまたは MDM [Devdetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/dnscomputername ノードの[Windows 自動操縦](https://docs.microsoft.com/hololens/hololens2-autopilot)を使用して、デバイスの名前を変更できます。
- イーサネットのページには、常に仮想イーサネットデバイス ("UsbNcm") が表示されます。
- 新しい Microsoft Edge のバッテリ使用量は、UWP アダプターレイヤーによってサポートされる Win32 デスクトップアプリケーションの性質上、正確ではない可能性があります (近日中に修正が予定されていません)。

#### <a name="display-color-calibration"></a>色の調整を表示する



この新しい設定で、HoloLens 2 ディスプレイの代替カラープロファイルを選択できます。 これにより、特にディスプレイの明るさが低いレベルで、色が正確に表示される場合があります。 ディスプレイの色の調整は、設定アプリの [システム > の調整] ページで確認できます。

> [!NOTE]
> この設定により、ディスプレイファームウェアに新しいカラープロファイルが保存されるため、デバイスごとの設定になります (各ユーザーアカウントに固有ではありません)。

##### <a name="how-to-use-display-color-calibration"></a>画面の色の調整を使用する方法

1. **設定** アプリを起動し、[**システム > の調整**] に移動します。
1. [ **ディスプレイの色の調整**] で、[ **画面の色の調整を実行** する] ボタンを選択します。
1. ディスプレイのカラー調整エクスペリエンスが起動し、バイザーが正しい位置にあることを確認することをお勧めします。
1. 指示のダイアログボックスが表示された後、画面は自動的にグレーで30% の明るさになります。
    > [!TIP]
    > 環境に淡色表示されているシーンが表示されない場合は、デバイスの左側にある [明るさ] ボタンを使用して、HoloLens 2 の輝度レベルを手動で調整できます。
1. ボタン1-6 を選択すると、各カラープロファイルが瞬時に表示され、最もよく見られるものを見つけることができます (これは通常、シーンを最もニュートラルにするのに役立つプロファイルで、グレースケールパターンとスキントーンが予想どおりに見えることを意味します)。

    ![色の調整シーンを表示する](images/color-cal-ui.png)
    
1. 選択したプロファイルに問題がなければ、[ **& の終了** ] ボタンをクリックします。
1. 変更しない場合は、[キャンセル] ボタンを選択& **すると** 、変更が元に戻されます

> [!TIP]
> ここでは、ディスプレイの色調整設定を使用する場合に注意する必要がある便利なヒントを示します。
> - 必要なときにいつでも [設定] から表示色の調整を再び実行できます
> - デバイス上の誰かが以前に設定を使用して色プロファイルを変更した場合は、最新の変更の日付/時刻が [設定] ページに反映されます
> - 表示色の調整を再び実行すると、以前に保存されたカラー プロファイルが強調表示され、プロファイル 0 は表示されません (プロファイル 0 はディスプレイの元のカラー プロファイルを表します)。
> - ディスプレイの元のカラー プロファイルに戻す場合は、[設定] ページから行います (カラー プロファイルをリセットする方法 [を参照してください](#how-to-reset-color-profile))。

##### <a name="how-to-reset-color-profile"></a>カラー プロファイルをリセットする方法 

HoloLens 2 に保存されたカスタム カラー プロファイルに問題が生じ場合は、デバイスの元のカラー プロファイルを復元できます。
1. 設定アプリ **を起動** し **、System > Calibration に移動します**。
1. [ **色の調整の表示]** で、[既定の色 **プロファイルにリセット] ボタンを選択** します。
1. ダイアログ ボックスが開いたら、再起動して変更を適用する準備ができたらHoloLens 2を選択します。

#### <a name="top-display-color-calibration-known-issues"></a>上位の表示色調整に関する既知の問題

- [設定] ページで、カラー プロファイルが最後に変更された日時を示す状態文字列は、[設定] のページを再度読み込むまで、最新の状態になっていません。
    - 回避策: 別の [設定] ページを選択し、[調整] ページを再選択します。

#### <a name="default-app-picker"></a>既定のアプリ ピッカー

ハイパーリンクをアクティブにするか、複数のインストール済みアプリを含むファイルの種類を開いた場合、新しいウィンドウが開き、ファイルまたはリンクの種類を処理するインストール済みアプリを選択するように求めるメッセージが表示されます。 このウィンドウでは、選択したアプリでファイルまたはリンクの種類として "Once" または "Always" を処理することもできます。

"Always" を選択した後、特定のファイルまたはリンクの種類を処理するアプリを変更する場合は、[ **設定 > アプリ**] で保存した既定値をリセットできます。 ページの一番下までスクロールし、[ファイルの種類の既定のアプリ] または [リンクの種類の既定のアプリ] の下にある [ **クリア** ] ボタンを選択します。 デスクトップ Pc の同様の設定とは異なり、個々のファイルの種類の既定値をリセットすることはできません。

#### <a name="per-app-volume-control"></a>アプリごとのボリューム制御

現在、この Windows ビルドでは、ユーザーは各アプリのボリュームレベルを手動で調整できます。 これにより、ユーザーは、必要なアプリに集中することができます。また、複数のアプリを使用する場合は、より適切に聞くことができます。 たとえば、あるアプリのボリュームを別のユーザーが別のユーザーに呼び出している間に、別のユーザーを呼び出す必要がある場合などです。

個々のアプリのボリュームを設定するには、[**設定**]  ->  [**システム**  ->  **サウンド**] に移動し、[サウンドの詳細オプション] で [**アプリのボリュームとデバイスの設定**] を選択します。

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>スワイプして入力します

お客様によっては、入力しようとしている単語の形状をスワイプすることで仮想キーボードの "種類" を短縮し、holographic キーボードのこの機能をプレビューしています。 Holographic キーボードのプレーンで指の先端を渡し、単語の形状をスワイプして、キーボードの平面から指の先端を取り出すことで、一度に1つの単語をスワイプできます。 単語の間でキーボードから指を削除することによって、スペースバーを押すことなくフォローアップ語をスワイプできます。 キーボードの指の動きの後にスワイプの軌跡が表示されている場合は、機能が動作していることがわかります。

この機能は、holographic キーボードの性質上、指に対する抵抗力を持たない (携帯電話ディスプレイとは異なります) ため、およびマスターを使用しても注意が必要です。 

### <a name="power-menu-from-start"></a>[スタート] の [電源] メニュー

ユーザーがサインアウトし、デバイスをシャットダウンして再起動できる新しいメニュー。 HoloLens のスタート画面に、システムの更新プログラムが利用可能になったことを示すインジケーター。

#### <a name="how-to-use"></a>使用方法

1. 開始ジェスチャを使用するかスタート画面を使用して HoloLens ファイルを開[スタートに移動。](hololens2-basic-usage.md#start-gesture)

2. ユーザー プロファイルの画像の横にある省略記号アイコン (...) に注意してください。

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. 手または音声コマンド "Power" を使用して、ユーザー プロファイルの画像を選択します。

4. メニューが表示され、デバイスのサインアウト、再起動、シャットダウンのオプションが表示されます。

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. メニュー オプションを選択して、HoloLens をサインアウト、再起動、またはシャットダウンします。 デバイスが 1 つの Microsoft アカウント (MSA) またはローカル アカウント に設定されている場合は、[サインアウト [] オプションを使用できない場合があります](hololens-identity.md)。

6. メニューを閉じるには、他の場所にタッチするか、[開始] ジェスチャスタート メニューを閉じる必要があります。

#### <a name="update-indicator"></a>インジケーターの更新

更新プログラムが使用可能な場合は、更新プログラムが再起動によってインストールされるという省略記号アイコンが点灯します。更新プログラムの存在を反映するようにメニュー オプションも変更されます。<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>[サインイン] 画面に表示される複数のユーザー

以前は、[サインイン] 画面には、最近サインインしたユーザーと "その他のユーザー" エントリ ポイントだけが表示されました。 複数のユーザーがデバイスにサインインしている場合は、これでは十分ではないというお客様からのフィードバックを受け取っています。 それでも、ユーザー名などを再入力する必要があります。

この Windows ビルドで導入された[PINエントリ] フィールドの右側にある [その他のユーザー] を選択すると、[サインイン] 画面に、以前にデバイスにサインインしたユーザーが複数表示されます。 これにより、ユーザーは自分のユーザー プロファイルを選択し、資格情報を使用してサインインWindows Helloできます。 [アカウントの追加] ボタンを使用して、この [その他のユーザー] ページからデバイスに新しい **ユーザーを追加** することもできます。

[その他のユーザー] メニューの [その他のユーザー] ボタンには、デバイスにサインインした最後のユーザーが表示されます。 このボタンを選択すると、このユーザーのサインイン画面に戻ります。

![サインイン画面の既定値](./images/multiusers1.jpg)

<br>

![他のユーザーのサインイン画面](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C 外部マイクのサポート

> [!IMPORTANT]
> USB mic に接続して **も、自動的に入力デバイスとして設定されることはありません**。 一連の USB C ヘッドホンに接続すると、ヘッドホンのオーディオが自動的にヘッドホンにリダイレクトされることがユーザーに確認されますが、HoloLens OS は、他の入力デバイスの上にある内部マイク配列に優先順位を設定します。 **USB-C マイクを使用するには、次の手順に従います。**

ユーザーは、 **サウンド** 設定パネルを使用して、USB C 接続外部マイクを選択できます。 USB C マイクは、通話や記録などに使用できます。

**設定** アプリを開き、[**システム** サウンド] を選択し  >  ます。

![サウンドの設定](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> **リモート** アシスタンスで外部マイクを使用するには、ユーザーは [サウンドデバイスの管理] ハイパーリンクをクリックする必要があります。
>
> 次に、ドロップダウンを使用して、 **既定** または通信の既定値として外部マイクを設定し **ます。** **既定値** を選択すると、外部マイクがすべての場所で使用されます。
>
> [ **通信の既定値** ] を選択すると、リモートアシスタンスやその他の通信アプリで外部マイクが使用されますが、他のタスクには HoloLens mic 配列が引き続き使用される可能性があります。

![サウンドデバイスの管理](images/usbc-mic-2.png)

<br>

![マイクの既定値の設定](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Bluetooth マイクのサポートについて

ただし、現在のところ、Bluetooth マイクは HoloLens 2 ではサポートされていません。

#### <a name="troubleshooting-usb-c-microphones"></a>USB C マイクのトラブルシューティング

USB C のマイクによっては、マイク *と* スピーカーの両方として誤って報告されることに注意してください。 これは、HoloLens ではなくマイクに問題があります。 これらのマイクの1つを HoloLens に接続すると、サウンドが失われる可能性があります。 さいわい、簡単な修正があります。  

[**設定**  ->  **システム**  ->  **サウンド]** で、組み込みのスピーカー **(アナログ機能オーディオ** ドライバー) を既定のデバイス として明示的 **に設定します**。 後でマイクを取り外して再接続した場合でも、HoloLens ではこの設定を記憶する必要があります。

![USB-C マイクのトラブルシューティング](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>キオスクのビジター自動ログオン

この新機能により、キオスク モードでビジター アカウントの自動ログオンを使用できます。

AAD 以外の構成の場合は、訪問者の自動ログオン用にデバイスを構成します。

1. 次のプロビジョニング パッケージを作成します。
    1. ビジター アカウント **を許可するランタイム設定/AssignedAccess** を構成します。
    1. 後で管理できるよう、必要に応じてデバイスを MDM **(ランタイム設定/ワークプレース/登録)** に登録します。
    1. ローカル アカウントを作成しない
1. [プロビジョニング パッケージ を適用します](hololens-provisioning.md)。

AAD 構成の場合、ユーザーは、この変更を行わずに、現在、このようなことを実現できます。 キオスク モード用に構成された AAD 参加済みデバイスは、サインイン画面から 1 つのボタン タップで Visitor アカウントにサインインできます。 ビジター アカウントにサインインすると、ビジターがスタート メニューから明示的にサインアウトするか、デバイスが再起動されるまで、デバイスは再度サインインを求めるメッセージを表示しません。

ビジター自動ログオンは、カスタム [OMA-URI ポリシーを使用して管理](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) できます。

- URI 値: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| ポリシー  | 説明   | 構成  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | キオスクへの訪問者の自動ログオンを許可する   | 1 (はい)、0 (いいえ、既定値)。  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>キオスクモードでの新しい設定とエッジアプリの使用

[キオスク](hololens-kiosk.md)にアプリを含めると、多くの場合、It 管理者はアプリをキオスクに追加しますが、アプリユーザーモデル ID (AUMID) を使用します。 設定アプリと Microsoft Edge アプリは両方とも新しいアプリと見なされ、これらのアプリで AUMIDs を使用する古いアプリキオスクとは異なるため、新しい AUMID を使用するように更新する必要があります。

新しいアプリを含めるようにキオスクを変更する場合は、新しい AUMID にを追加することをお勧めします。 これにより、ユーザーが OS を更新するときに簡単に移行できるようになります。また、意図したとおりにキオスクを使用し続けるために新しいポリシーを受け取る必要はありません。

| アプリ                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| 古い設定アプリ       | HolographicSystemSettings_cw5n1h2txyewy!アプリケーション            |
| 新しい設定アプリ       | BAEAEF15-9BAB-47 FC-800B-ACECAD2AE94B_cw5n1h2txyewy!アプリケーション |
| 以前の Microsoft Edge アプリ | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| 新しい Microsoft Edge アプリ | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>キオスクモードでのエラー処理の動作変更

以前のビルドでは、グローバルに割り当てられたアクセスと AAD グループメンバーの両方を組み合わせたキオスク構成がデバイスにある場合、AAD グループのメンバーシップの確認に失敗すると、ユーザーには [スタート] メニュー[に表示](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)されないものが表示されます。

この Windows リリース以降では、AAD グループキオスクモード中にエラーが発生した場合、キオスクエクスペリエンスがグローバルキオスク構成 (存在する場合) にフォールバックします。

### <a name="new-settings-uris-for-page-settings-visibility"></a>ページ設定の表示用の新しい設定 Uri

[Windows Holographic のバージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2)では、Settings [/PageVisibilityList ポリシー](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)を追加して、設定アプリ内で表示されるページを制限しました。 PageVisibilityList は、IT 管理者がシステム設定アプリ内の特定のページを表示またはアクセスできないようにするか、指定されたものを除くすべてのページに対して実行できるようにするポリシーです。

[ [ページ設定の表示](settings-uri-list.md)] にアクセスすると、この CSP を使用する手順と、以前のリリースで使用可能な uri の一覧を確認できます。

ここでは、IT 管理者が管理できる、使用可能な設定 Uri の一覧について説明します。 これらの URI の一部は、新しい設定アプリ内の新しく使用可能な領域用です。 Settings/PageVisibilityList ポリシーを使用している場合は、次の一覧を確認し、必要に応じて許可またはブロックされたページを調整します。

> [!NOTE]
> **非推奨: ms-settings:network-proxy**
>
> これらの新しいビルドでは、1 つの設定ページが非推奨とされます。 古い **[ネットワーク & インターネット**  >  **プロキシ]** ページは、グローバル設定として使用できなくなりました。 新しい接続ごとのプロキシ設定は、[ネットワーク]の [インターネット Wi-Fi プロパティ] & [ネットワーク] [インターネット イーサネットのプロパティ] &  >    >  **で**  >  **確認**  >  **できます**。

<br>

| [設定] ページ                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Apps > Apps &機能                               | `ms-settings:appsfeatures`                         |
| アプリ > Apps &機能>詳細オプション          | `ms-settings:appsfeatures-app`                     |
| オフライン >アプリ                                  | `ms-settings:maps`                                 |
| オフライン マップ>アプリ>マップのダウンロード                  | `ms-settings:maps-downloadmaps`                    |
| デバイス > マウス                                      | `ms-settings:mouse`                                |
| USB >デバイス                                        | `ms-settings:usb`                                  |
| ネットワーク & インターネット >フライト モード                   | `ms-settings:network-airplanemode`                 |
| プライバシー>全般                                    | `ms-settings:privacy-general`                      |
| プライバシー > Ink &入力パーソナル化             | `ms-settings:privacy-speechtyping`                 |
| Privacy > Motion                                     | `ms-settings:privacy-motion`                       |
| プライバシー>スクリーンショットの境界線                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| プライバシー>スクリーンショットとアプリ                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| システム > バッテリ                                     | `ms-settings:batterysaver`                         |
| システム > バッテリ                                     | `ms-settings:batterysaver-settings`                |
| システム > サウンド                                       | `ms-settings:sound`                                |
| システム > サウンド > アプリのボリュームとデバイスの基本設定 | `ms-settings:apps-volume`                          |
| システム > サウンド > サウンドデバイスの管理              | `ms-settings:sound-devices`                        |
| 記憶域の意味を構成 > システム > ストレージ         | `ms-settings:storagepolicies`                      |
| 時刻 & 言語 > 日付 & 時刻                        | `ms-settings:dateandtime`                          |
| 時刻 & 言語 > キーボード                           | `ms-settings:keyboard`                             |
| 時刻 & 言語 > 言語                           | `ms-settings:language`                             |
| 時刻 & 言語 > 言語                           | `ms-settings:regionlanguage-languageoptions`       |
| 更新 & セキュリティ > リセット & 回復               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>更新された Uri

以前は、次の2つの Uri は、指定されたページに直接ユーザーを移動しませんが、メイン更新ページはブロックされています。 次の項目が更新され、ページに直接移動しました。

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>設定アプリを使用したフォールバック診断の構成

現在、設定アプリでは、ユーザーは [フォールバック診断](hololens-diagnostic-logs.md)の動作を構成できます。 設定アプリで、プライバシーに  ->  **関するトラブルシューティング** ページに移動し、この設定を構成します。

> [!NOTE]
> デバイスに MDM ポリシーが構成されている場合、ユーザーはその動作をオーバーライドすることはできません。  

### <a name="share-things-with-nearby-devices"></a>近くのデバイスとの共有

Pc とその他の HoloLens 2 デバイスを含む、Windows 10 デバイスの近くでを共有します。   ->    ->  HoloLens から PC にファイルまたは url を共有するには、[設定] [システム **共有**] で試してみることができます。 詳細については、 [Windows 10 で近くのデバイスと項目を共有](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)する方法を参照してください。

この機能は [、Connectivity/AllowConnectedDevices を使用して管理できます](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)。

### <a name="new-os-diagnostic-traces"></a>新しい OS 診断トレース

設定アプリ内の以前のトラブルシューティング ツールに加えて、新しいトラブルシューティング ツールが追加され、OS 更新用の新しい設定アプリが追加されました。 [設定] **[**  ->  **セキュリティの更新 &amp; のトラブルシューティング]**  >  **Windows Update**  >  し **、[ 開始**] を **選択します**。 これにより、OS の更新に関する問題を再現しながらトレースを収集し、IT またはサポートのトラブルシューティングに役立ちます。

### <a name="delivery-optimization-preview"></a>配信の最適化 プレビュー

この HoloLens 更新プログラムを使用するとWindows Holographic for Business、配信の最適化設定を使用して、複数の HoloLens デバイスからのダウンロードの帯域幅消費量を削減できます。 推奨されるネットワーク構成と共に、この機能の詳細な説明については [、「配信の最適化」をWindows 10してください](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)。

次の設定は管理画面の一部として有効にされ [、Intune から構成できます](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)。

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

このプレビュー オファリングに関する注意点を次に示します。

- このプレビューでは、HoloLens のサポートは OS の更新プログラムに限定されています。
- Windows Holographic for Business は、HTTP ダウンロードモードと、 [Microsoft 接続キャッシュエンドポイント](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)からのダウンロードのみをサポートしています。現時点では、ピアツーピアのダウンロードモードとグループの割り当ては、HoloLens デバイスではサポートされていません。
- HoloLens は Windows Server Update Services エンドポイントの展開または配信の最適化をサポートしていません。
- トラブルシューティングを行うには、接続されているキャッシュサーバーの診断、または **設定** の更新による hololens 上の hololens でのトレースの収集  >  **& セキュリティ**  >   **トラブルシューティング**  >   **Windows Update** を行う必要があります。

### <a name="it-admin---update-checklist"></a>IT 管理者-更新プログラムのチェックリスト

このチェックリストは、現在のデバイス管理構成に影響を与える可能性がある、この機能更新プログラムに追加される新しい項目、または使用を開始する新機能を理解するのに役立ちます。

#### <a name="updates-to-kiosk-mode"></a>キオスクモードの更新プログラム

[**キオスクモードで新しいアプリの新しい AUMIDs を**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)✔️します。

キオスクで設定アプリまたは Microsoft Edge アプリを以前に使用していた場合、これらのアプリは別のアプリ ID を使用する新しいアプリに置き換えられました。 以下 [のキオスクモードで新しいアプリの新しい AUMIDs](#use-the-new-settings-and-edge-apps-in-kiosk-modes) を読むことを強くお勧めします。 これにより、キオスクの設定アプリを引き続き使用するか、新しい Microsoft Edge アプリを含めることができます。 これらの変更は、今すぐ実行し、すべてのデバイスに展開して、更新をスムーズに移行できるようにすることができます。

[**キオスクの✔️ビジターの自動ログオン**](#visitor-auto-logon-for-kiosks): 

訪問者がキオスクに自動的にログインできるようになりました。 この動作は既定で有効になっていますが、管理と無効化を行うことができます。

✔️ [**キオスクモードのエラー**](#kiosk-mode-behavior-changes-for-handling-of-failures)処理の改善:

サインインしている AAD ユーザーの AAD グループメンバーシップが正常に決定されていない場合、[スタート] メニュー (存在する場合) にはグローバルキオスク構成が使用されます。それ以外の場合、ユーザーには空の [スタート] メニューが表示されます。 空のスタート メニューは直接設定できる構成ではありません。この新しい処理は、キオスクを使用している場合、構成に適用される場合や、割り当てられたアクセス構成に対して新しい調整を行う場合など、サポート部門に通知する必要がある場合があります。

#### <a name="updates-to-page-settings-visibility"></a>ページ設定の可視性の更新

✔️ [**設定を表示する新しい設定 URI の追加**](#new-settings-uris-for-page-settings-visibility)

現在ページ [設定の可視性](settings-uri-list.md) を使用している場合は、許可またはブロックされている既存の URI を調整することができます。

#### <a name="updates-for-your-wdac-policy"></a>WDAC ポリシーの更新
✔️ WDAC を使用してMicrosoft Edgeブロックしていた場合は、WDAC ポリシーを更新する必要があります。 以下を確認し、提供されているサンプル コードを使用してください。
#### <a name="enable-new-endpoints-for-edge"></a>Edge の新しいエンドポイントを有効にする
✔️ プロキシやファイアウォールなどのネットワーク エンドポイントの構成を含むインフラストラクチャがある場合は、新しい Microsoft Edge アプリに対してこれらの新しいエンドポイントを有効にしてください。

#### <a name="newly-configurable-items"></a>新しく構成可能な項目

✔️ [診断の構成:](#configuring-fallback-diagnostics-via-settings-app)フォールバック診断を収集する場合と収集するユーザーを構成できます。

✔️[近くのデバイスと共有する](#share-things-with-nearby-devices): 近くの新しい共有機能を無効にできます。

✔️ [のポリシー設定の](#configuring-policy-settings-for-the-new-microsoft-edge)構成: Microsoft Edgeで使用できる新しい構成を確認Microsoft Edge。

#### <a name="new-diagnostic-tool"></a>新しい診断ツール

✔️[新しい OS 診断トレース:](#new-os-diagnostic-traces)OS の更新に関連するログを収集します。

### <a name="improvements-and-fixes-in-the-update"></a>更新プログラムの機能強化と修正:

- [オフライン診断には、](hololens-diagnostic-logs.md#offline-diagnostics) シリアル番号と OS バージョンに関する追加のデバイス情報も含まれます。
- ランタイム プロビジョニング パッケージを使用した業務アプリケーションの展開に関する問題を修正します。
- ビジネス アプリケーションのインストール状態レポートの行に関する問題を修正します。
- デバイスのリセット全体での新しいアプリ パッケージの永続化に関する問題を修正します。
- 日本のお客様に対して、エッジに間違った記号が入力された場合に発生する可能性のある問題を修正します。
- エッジなど、プレインストールされているアプリに関連する OS 更新プログラムの回復性を向上させます。 
- Microsoft Edge のインストールに影響を与える更新の信頼性に対処します。 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic、バージョン20H2 –2021年5月の更新プログラム
- ビルド19041.1146

更新プログラムの機能強化と修正:
- この月間品質更新プログラムには、重要な変更は含まれていません。最新のビルド、Windows Holographic、バージョン21H1 を試すことをお勧めします。

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic、バージョン 1903-2021 更新プログラム
- ビルド18362.1110

更新プログラムの機能強化と修正:
- この月間品質更新プログラムには、注目すべき変更は含まれていません。 **このビルドは、月ごとのサービス更新を受信しなく** なります。 最新のビルド、Windows Holographic、バージョン21H1 を試すことをお勧めします。



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic、バージョン 20H2-2021 年4月更新
- ビルド19041.1144

更新プログラムの機能強化と修正:

- 基幹業務アプリケーションのインストール状態レポートに関する問題を修正しました。

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic、バージョン 1903-2021 年4月更新
- ビルド18362.1108

更新プログラムの機能強化と修正:

- ローカル アカウントのパスワードを変更しようとするときに設定アプリがクラッシュする問題を修正します。


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic バージョン 20H2 - 2021 年 3 月の更新プログラム
- ビルド 19041.1140

更新プログラムの機能強化と修正:

- AdvancedPhotoCapture または LowLagPhotoCapture を使用して HoloLens 2 で写真をキャプチャしているお客様は、写真がキャプチャされた後、最大 3 秒後にカメラの姿勢を取得できます。
- デバイス ポータル Service のメモリ リークを修正しました。この問題により、他のアプリケーションがメモリの割り当てに失敗する原因となるサービスによるメモリ使用量が増加しました。
- 段階的なロールアウトに登録されているユーザーがデバイスにサインインできない問題を修正しました。

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic バージョン 1903 - 2021 年 3 月の更新プログラム
- ビルド 18362.1102

更新プログラムの機能強化と修正:

- デバイス ポータル Service のメモリ リークを修正しました。この問題により、他のアプリケーションがメモリの割り当てに失敗する原因となるサービスによるメモリ使用量が増加しました。

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic バージョン 20H2 - 2021 年 2 月の更新プログラム
- ビルド 19041.1136

更新プログラムの機能強化と修正:

- デバイスの初期セットアップとストア アプリの更新に関する問題を修正します。
- 以降の HoloLens リリースのアップグレードとフライトに関する問題に取り組む。
- HoloLens デバイスから eSIM ルート ストアから未使用のプレインストール済み証明書を削除しました。

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic バージョン 1903 - 2021 年 2 月の更新プログラム
- ビルド 18362.1098

この毎月の品質更新プログラムには、重要な変更は含まれているのではなく、Windows Holographic バージョン 2004 用の最新のビルドをお試しください。

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic、バージョン 20H2-2021 年1月更新
- ビルド19041.1134

更新プログラムの機能強化と修正:

- デバイスに多数のユーザーがいるときに、起動、再開、ユーザー切り替えの際のパフォーマンスが向上しました。
- [リサーチモード](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)の arm32 サポートを追加しました。

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic、バージョン 1903-1 月2021更新プログラム
- ビルド18362.1091

この月間品質更新プログラムには、重要な変更は含まれていません。 Windows Holographic バージョン2004の最新のビルドを試すことをお勧めします。

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic、バージョン20H2 –2020年12月更新
- ビルド19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>アプリインストーラーを使用して HoloLens 2 にアプリをインストールする

HoloLens 2 デバイスに **アプリケーションをシームレスにインストールできる新しい機能 (アプリインストーラー) を追加** しています。 この機能は、管理されていない **デバイスに対しては既定でオンに** なります。 企業が中断されないように、現時点では、 **管理対象デバイス** でアプリインストーラーを使用できなくなります。  

次の **いずれか** に該当する場合、デバイスは "管理されている" と見なされます。
- MDM[登録](hololens-enroll-mdm.md)済み
- [プロビジョニングパッケージ](hololens-provisioning.md)で構成済み
- ユーザー [id](hololens-identity.md) が Azure AD

開発者モードを有効にしたり、デバイスポータルを使用したりすることなく、アプリをインストールできるようになりました。  Appx バンドルをデバイスに (USB 経由またはエッジ経由で) ダウンロードし、エクスプローラーで Appx バンドルに移動するだけで、インストールを開始するように求められます。  または、Web [ページ からインストールを開始します](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。  MDM の LOB アプリ展開機能を使用して Microsoft Store またはサイドロードからインストールするアプリと同様に、アプリは署名ツールを[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)使用してデジタル署名[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)する必要があります。また、アプリを展開する前に、署名に使用される証明書が HoloLens デバイスによって信頼されている必要があります。

**アプリケーションのインストール手順。**

1.  デバイスが管理対象と見なされていないことを確認する
1.  デバイスの電源HoloLens 2 PC に接続されていることを確認します
1.  デバイスにサインインHoloLens 2する
1.  PC でカスタム アプリに移動し、yourapp.appxbundle を yourdevicename\Internal Storage\Downloads にコピーします。   ファイルのコピーが完了したら、デバイスを切断できます
1.  デバイスからHoloLens 2スタート メニューを開き、[すべてのアプリ] を選択し、アプリを起動エクスプローラーします。
1.  [ダウンロード] フォルダーに移動します。 アプリの左側のパネルで、[このデバイス] を最初に選択し、[ダウンロード] に移動する必要があります。
1.  yourapp.appxbundle ファイルを選択します。
1.  このアプリ インストーラーが起動します。 [インストール] ボタンを選択して、アプリをインストールします。
インストールが完了すると、インストールされたアプリが自動的に起動します。

このフローをテストするサンプル アプリは [、Windows ユニバーサル サンプル GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) にあります。

を使用してアプリをインストール[するプロセスの詳細については、HoloLens 2を参照アプリ インストーラー。](app-deploy-app-installer.md)  

![以下を使用した MRTK のアプリ インストーラー](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>更新プログラムの機能強化と修正:

- 手の追跡では、以前に手が失われた可能性がある多くの新しいケースで追跡が維持されます。  これらの新しいケースの一部では、ユーザーの実際の位置に基づいて、パーム位置のみが引き続き更新されますが、他の関節は前のポーズに基づいて推論されます。  この変更により、称する、フランカ、scooping、clapping などの移動における追跡の一貫性が向上します。  また、手が表面に近い場合や、オブジェクトを保持している場合にも役立ちます。  手の継手が推論されると、"高" [ではなく](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) "近似値" に設定されます。
- Azure AD アカウントの PIN をリセットすると、問題が発生したことを示す問題が修正されました。
- ユーザーは、[設定] [アプリ]、[新しいユーザー]、または [通知トースト] を起動したときに、起動後に発生した OOBE のクラッシュを大幅に少なくする必要があります。
- ユーザーは、OOBE から正しいタイムゾーンを取得する必要があります。

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic、バージョン1903–12月2020更新プログラム
- ビルド18362.1088

この月間品質更新プログラムには、重要な変更は含まれていません。最新の Windows Holographic、バージョン20H2 – December 2020 更新プログラム、およびビルドに追加された新しいアプリインストーラー機能を試すことをお勧めします。


## <a name="windows-holographic-version-20h2"></a>Windows Holographic、バージョン20H2
- ビルド19041.1128

Windows Holographic、バージョン20H2 が利用可能になりました。 HoloLens 2 ユーザーと IT プロフェッショナルに優れた新機能が提供されます。 自動監視、設定内の証明書マネージャー、キオスクモード機能の向上、および新しい自動操縦用セットアップ機能を備えています。 この新しい更新プログラムにより、IT チームは HoloLens デバイスの構成と管理をより細かく制御し、よりシームレスな holographic エクスペリエンスを提供できるようになります。 

この最新リリースは、バージョン2004の毎月の更新プログラムですが、今回は新機能を追加しています。 メジャービルド番号は変わりません。 Windows Update は、バージョン 2004 (ビルド 19041) の月単位のリリースを示します。 [設定] 画面 > のビルド番号を確認して、利用可能な最新のビルド 19041.1128 + が表示されていることを確認できます。 最新のリリースに更新するには、設定アプリを開き、[Update & Security] にアクセスして、[更新プログラムの確認] をタップします。 HoloLens の更新プログラムを管理する方法の詳細については、このページを [参照してください](https://docs.microsoft.com/hololens/hololens-updates)。

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Windows Holographic バージョン 20H2 の新機能  

| 機能                                              | Description                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [自動目の位置のサポート](hololens-release-notes.md#auto-eye-position-support) | ユーザーが目の追跡の調整を行わずに、目の位置を積極的に計算します。   |
| [Certificate Manager](hololens-release-notes.md#certificate-manager)   | 新しい簡単な方法で、設定アプリから証明書をインストールおよび削除できます。     |
| [USB からの自動起動プロビジョニング](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | USB ドライブにパッケージをプロビジョニングすると、OOBE のプロビジョニング ページが自動的に表示されます。                                                         |
| [OOBE でのプロビジョニング パッケージの自動確認](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | プロビジョニング パッケージは、プロビジョニング ページから OOBE 中に自動的に適用されます。                                                         |
| [UI を使用しない自動プロビジョニング](hololens-release-notes.md#automatic-provisioning-without-using-ui) | プロビジョニングの自動起動と自動確認を組み合わせる方法。 |
| [Autopilot と接続のWi-Fiする](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | イーサネット アダプターを必要とせずにWi-Fiデバイスからオートパイロットを使用します。 |
| [Tenantlockdown CSP と Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | テナントの登録とポリシーが適用された後は、デバイスがリセットまたは再フラッシュされた場合にのみ、そのテナントにデバイスを登録できます。 |
| [グローバル割り当てアクセス](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | システム レベルでキオスクを適用し、すべてのユーザーに適用できる、複数のアプリ キオスク モードの新しい構成方法。                  |
| [マルチアプリ キオスクでアプリを自動起動する](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | 複数アプリキオスク モードにサインインするときに自動的に起動するアプリケーションを設定します。                                                        |
| [エラー処理のためのキオスク モードの動作の変更](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | キオスクモードのエラーのフォールバックが制限されるようになりました。                                                                                                |
| [HoloLens ポリシー](hololens-release-notes.md#hololens-policies)                                    | HoloLens の新しいポリシー。     |
| [オフラインキオスクのキャッシュ Azure AD グループメンバーシップ](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | 新しいポリシーを使用すると、ユーザーはグループメンバーシップキャッシュを使用して、設定した日数でキオスクモードをオフラインで使用できます。                                        |
| [HoloLens 2 の新しいデバイス制限ポリシー](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | HoloLens 2 に対して新しく有効になったデバイス管理ポリシー。                                                                                |
| [HoloLens 2 の新しい電源ポリシー](hololens-release-notes.md#new-power-policies-for-hololens-2)       | 新しくサポートされている電源タイムアウト設定のポリシー。  |
| [ポリシーの更新](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | 新しく有効になったポリシーにより、更新を制御できます。           |
| [HoloLens 2 で有効になっている設定ページの可視性](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | 設定アプリに表示されるページを選択するポリシー。             |
| [リサーチモード](hololens-release-notes.md#research-mode) | HoloLens 2 でのリサーチモードの使用。 |
| [記録の長さが増加しました](hololens-release-notes.md#recording-length-increased) | MRC 録音は5分ではなくなりました。 |
| [更新プログラムの機能強化と修正](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | 更新プログラムの追加の修正。   |

### <a name="auto-eye-position-support"></a>自動アイポジションのサポート

このHoloLens 2、目の位置により、正確なホログラムの配置、快適な表示エクスペリエンス、および表示品質の向上が可能になります。 目の位置は、目の追跡計算の一部として内部的に計算されます。 ただし、エクスペリエンスで視線入力が必要ない場合でも、各ユーザーは視線追跡の調整を行う必要があります。

**自動目の位置 (AEP) を使用** すると、ユーザーの目の位置を計算する操作を必要としません。 自動目の位置は、ユーザーがデバイスを置いた瞬間から自動的にバックグラウンドで作業を開始します。 ユーザーが前の目の追跡の調整を行っていない場合、自動目の位置は、20 - 30 秒の処理時間の後、表示システムにユーザーの目の位置を提供し始める。 ユーザー データはデバイスに保持されないので、ユーザーが離してデバイスを再度起動した場合、またはデバイスが再起動またはスリープからウェイクアップした場合は、このプロセスが繰り返されます。

自動目の位置機能では、未調整のユーザーがデバイスに配置すると、システム動作がいくつか変更されます。 このコンテキストでは、未調整のユーザーは、以前にデバイスで目の追跡の調整プロセスを実行していないユーザーを指します。

| アクティブ なアプリケーション | 以前の動作 | Windows Holographic バージョン 20H2 Update からの動作 |
|:-------------------|:-----------------|:-----------------------------------|
| 視線入力が有効でないアプリまたは Holographic Shell |[目の追跡の調整プロンプト] ダイアログが表示されます。 | プロンプトは表示されません。 |
| 視線入力が有効なアプリ | [目の追跡の調整プロンプト] ダイアログが表示されます。 | 視線追跡の調整プロンプトは、アプリケーションが視線入力ストリームにアクセスする場合にのみ表示されます。 |

ユーザーが視線入力が有効になっていないアプリケーションから視線入力データにアクセスするアプリケーションに切り替える場合は、調整プロンプトが表示されます。 

他のすべてのシステム動作は、現在のユーザーがアクティブな目追跡調整を行っていない場合と似ています。 たとえば、ワンききの開始ジェスチャは有効になりません。 初期セットアップの既定のエクスペリエンスに変更はありません。

視線データを必要とするエクスペリエンスや、正確にホログラムを配置する必要がある経験については、ユーザーが視線追跡の調整を実行することを uncalibrated ことをお勧めします。 これには、視線追跡調整のプロンプトからアクセスするか、[スタート] メニューから設定アプリを起動し、[ **システム > の調整] > [目の調整 > 実行**] を選択します。

この情報については、後で [その他の調整情報](hololens-calibration.md#auto-eye-position-support)を参照してください。 

### <a name="certificate-manager"></a>証明書マネージャー

- 新しい証明書マネージャーを使用した、デバイスのセキュリティとコンプライアンスのための監査、診断、検証のツールが改善されました。 この機能により、商用環境で大規模に証明書をデプロイ、トラブルシューティング、および検証することができます。

Windows Holographic バージョン20H2 では、HoloLens 2 設定アプリに証明書マネージャーを追加しています。 [設定] にアクセスして **& セキュリティ > 証明書を更新 >** ます。 この機能は、デバイス上の証明書を表示、インストール、削除するための簡単でわかりやすい方法を提供します。 新しい証明書マネージャーを使用すると、管理者とユーザーは、デバイスが安全で準拠していることを確認するための監査、診断、検証のツールが改善されました。 

-   **監査:** 証明書が正しく展開されていることを検証したり、適切に削除されたことを確認したりする機能。 
-   **診断:** 問題が発生した場合、デバイスに適切な証明書が存在することを検証すると、時間が節約され、トラブルシューティングに役立ちます。 
-   **検証:** 証明書が意図した目的を果たし、機能していることを確認することにより、証明書を大規模に展開する前に、特に商用環境においてかなりの時間を節約することができます。

リスト内の特定の証明書をすばやく検索するには、名前、ストア、または有効期限の日付で並べ替えるオプションがあります。 ユーザーは、証明書を直接検索することもできます。 個々の証明書のプロパティを表示するには、証明書を選択し、[ **情報**] をクリックします。 

証明書のインストールでは現在、.cer ファイルと .crt ファイルがサポートされています。 デバイス所有者は、ローカル コンピューターと現在のユーザーに証明書をインストールできます。 他のすべてのユーザーは、現在のユーザーにのみインストールできます。 ユーザーは、設定 UI から直接インストールされた証明書のみを削除できます。 証明書が他の方法でインストールされている場合は、同じメカニズムでも削除する必要があります。

#### <a name="to-install-a-certificate"></a>証明書をインストールするには: 

1.  PC にHoloLens 2接続します。
1.  インストールする証明書ファイルを、自分の証明書ファイルの場所にHoloLens 2。
1.  [設定 **] [App > Update & Security > 証明書**] に移動し、[証明書のインストール] を選択します。
1.  [ **ファイルのインポート]** をクリックし、証明書を保存した場所に移動します。
1.  [ストア **の場所] を選択します**。
1.  [証明書 **ストア] を選択します**。
1.  **[インストール]** をクリックします。

これで、証明書がデバイスにインストールされます。

#### <a name="to-remove-a-certificate"></a>証明書を削除するには: 
1. [設定] **[アプリ] > [更新とセキュリティ] >移動します**。
1. 検索ボックスで名前で証明書を検索します。
1. 証明書を選択します。
1. [削除] **をクリックします。**
1. 確認を求められたら、 **[はい]** を選択します。

![設定アプリの証明書ビューアー](images/certificate-viewer-device.jpg)

![証明書 UI を使用して証明書をインストールする方法を示す図](images/certificate-device-install.jpg)

この情報は、後で新 [しい [証明書マネージャー] ページで確認できます](certificate-manager.md)。

### <a name="auto-launch-provisioning-from-usb"></a>USB からの自動起動プロビジョニング

- プロビジョニングパッケージのある USB ドライブが OOBE 中に使用される場合に、ユーザー操作を減らすことができる自動プロセス。

このリリースの前では、ボタンの組み合わせを使用して、OOBE 中にプロビジョニング画面を手動で起動する必要がありました。 これで、ユーザーは USB ストレージドライブでプロビジョニングパッケージを使用して、ボタンの組み合わせをスキップできるようになりました。 

1. OOBE の最初の対話型モーメント中に、プロビジョニングパッケージを使用して USB ドライブにプラグインする
1. デバイスをプロビジョニングする準備が整うと、[プロビジョニング] ページでプロンプトが自動的に開きます。 

注: デバイスの起動中に USB ドライブが接続されたままになっている場合、OOBE は既存の USB 記憶装置を列挙し、接続されている追加のデバイスを監視します。

OOBE 中にプロビジョニングパッケージを適用する方法の詳細については、 [HoloLens プロビジョニング](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) のドキュメントを参照してください。

[USB からの自動起動のプロビジョニング](hololens-provisioning.md#auto-launch-provisioning-from-usb)に関する追加情報については、HoloLens プロビジョニングのドキュメントを参照してください。

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>OOBE でのプロビジョニングパッケージの自動確認
- 自動プロセスでは、ユーザーの操作を減らすことができます。 [プロビジョニングパッケージ] ページが表示されると、一覧にあるすべてのパッケージが自動的に適用されます。

プロビジョニングのメイン画面が表示されると、OOBE は、すべてのプロビジョニングパッケージの適用が自動的に開始されるまで10秒後にカウントされます。 ユーザーは、必要なパッケージを確認した後、この10秒以内に [確認または取り消し](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) を行うことができます。

### <a name="automatic-provisioning-without-using-ui"></a>UI を使用しない自動プロビジョニング
- プロビジョニングのためにデバイスの相互作用を削減するための自動プロセスを結合しました。 

USB デバイスからのプロビジョニングの自動起動とプロビジョニングパッケージの自動確認を組み合わせることによって、ユーザーは、デバイスの UI を使用したり、デバイスを装着したりせずに、HoloLens 2 デバイスを自動的にプロビジョニングできます。 複数のデバイスに同じ USB ドライブとプロビジョニングパッケージを使用し続けることができます。 これは、複数のデバイスを同じ領域に一度に展開する場合に便利です。 

1. Windows[構成デザイナー を使用してプロビジョニング](hololens-provisioning.md)[パッケージを作成します](https://www.microsoft.com/store/productId/9NBLGGH4TX22)。 
1. パッケージを USB ストレージ ドライブにコピーします。
1. [19041.1361](https://aka.ms/hololens2previewdownload)[以降HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions)ビルド にフラッシュします。 
1. Advanced [Recovery Companion で](https://www.microsoft.com/store/productId/9P74Z35SFRS8) デバイスのフラッシュが完了したら、USB-C ケーブルを取り外します。 
1. USB ドライブをデバイスに接続します。
1. デバイスHoloLens 2 OOBE に起動すると、USB ドライブ上のプロビジョニング パッケージが自動的に検出され、プロビジョニング ページが起動します。
1. 10 秒後、デバイスによってプロビジョニング パッケージが自動的に適用されます。 

これでデバイスが構成され、[プロビジョニングに成功しました [] 画面が表示されます](hololens-provisioning.md#automatic-provisioning-without-using-ui)。

### <a name="using-autopilot-with-wi-fi-connection"></a>Autopilot と接続のWi-Fiする
- 接続されているデバイスで Autopilot が機能する機能を有効にすることで、ハードウェアのニーズを減らすイーサネットへの USB-C アダプターWi-Fi必要が取り除かれました。

OOBE 中に、Wi-Fi HoloLens 2接続すると、OOBE によってデバイスの Autopilot プロファイルが確認されます。 見つかった場合は、AAD 参加フローと登録フローの残りの部分を完了するために使用されます。 つまり、USB-C または Wi-Fi から USB-C アダプターへのイーサネットの使用は要件ではなくなりましたが、OOBE の開始時に提供されている場合は引き続き機能します。 デバイスの [Autopilot の詳細については、HoloLens 2してください](hololens2-autopilot.md)。

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP と Autopilot
- デバイスのリセットまたは再フラッシュを使用しても、デバイスをテナントにロックすることで、組織のテナント上のデバイスを保持します。 プロビジョニングを介した でのアカウントの作成を禁止することで、セキュリティを強化します。 

HoloLens 2 Windows [Holographic バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2)の現在、テナントロックダウン CSP がサポートされます。 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP を使用HoloLens 2 Autopilot のみを使用して MDM 登録に関連付けできます。 tenantLockdown CSP の RequireNetworkInOOBE ノードが HoloLens 2 で true または false (最初に設定) の値に設定された後、その値は、再フラッシュや OS の更新などにもかかわらずデバイス上に残ります。 

HoloLens 2 で TenantLockdown Csp ' RequireNetworkInOOBE node ' が true に設定されると、ネットワーク接続後、OOBE は自動操縦プロファイルが正常にダウンロードおよび適用されるまで無期限に待機します。 

HoloLens 2 で TenantLockdown Csp ' RequireNetworkInOOBE node ' が true に設定されると、次の操作は OOBE で許可されません。 
- ランタイムプロビジョニングを使用したローカルユーザーの作成 
- ランタイムプロビジョニングによる Azure AD 参加操作の実行 
- OOBE エクスペリエンスでデバイスを所有するユーザーを選択する 

#### <a name="how-to-set-this-using-intune"></a>Intune を使用してこれを設定する方法 
1. 次に示すように、カスタムの OMA-URI デバイス構成プロファイルを作成し、RequireNetworkInOOBE ノードに true を指定します。
OMA-URI 値は./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE にする必要があります

   > [!div class="mx-imgBorder"]
   > ![OMA-URI によるテナント lockdown の設定](images/hololens-tenant-lockdown.png)

1. グループを作成し、そのデバイスグループにデバイス構成プロファイルを割り当てます。 

1. 前の手順で作成したグループの HoloLens 2 デバイスメンバーを作成し、同期をトリガーします。  

Intune ポータルで、デバイスの構成が正常に適用されたことを確認します。 このデバイス構成が HoloLens 2 デバイスに正常に適用されると、TenantLockdown の効果がアクティブになります。

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Intune を使用して HoloLens 2 で TenantLockdown の RequireNetworkInOOBE を解除する方法 
1. 上記で作成したデバイス構成が既に割り当てられているデバイスグループから HoloLens 2 を削除します。 

1. 次に示すように、カスタムの OMA-URI ベースのデバイス構成プロファイルを作成し、RequireNetworkInOOBE に false を指定します。 OMA-URI 値は./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE にする必要があります

   > [!div class="mx-imgBorder"]
   > ![Intune で OMA URI を使用して RequireNetworkInOOBE を false に設定するスクリーンショット](images/hololens-tenant-lockdown-false.png)

1. グループを作成し、そのデバイスグループにデバイス構成プロファイルを割り当てます。 

1. 前の手順で作成したグループの HoloLens 2 デバイスメンバーを作成し、同期をトリガーします。

Intune ポータルで、デバイス構成が正常に適用されたことを確認します。 このデバイス構成がデバイスに正常に適用されるとHoloLens 2 TenantLockdown の影響は非アクティブになります。 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>TenantLockdown が true に設定された後、HoloLens で Autopilot プロファイルが割り当てられていない場合、OOBE 中に何が起こりますか? 
OOBE は Autopilot プロファイルがダウンロードされるのを無期限に待機し、次のダイアログが表示されます。 TenantLockdown の効果を削除するには、最初に Autopilot のみを使用してデバイスを元のテナントに登録する必要があります。また、TenantLockdown CSP によって導入された制限が削除される前に、前の手順で説明したように RequireNetworkInOOBE を設定解除する必要があります。 

![ポリシーがデバイスに適用される場合のデバイス内ビュー。](images/hololens-autopilot-lockdown.png)

この情報は [、Tenantlockdown CSP と Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)の下にある Autopilot の残りの部分と共に確認できます。

### <a name="global-assigned-access--kiosk-mode"></a>グローバル割り当てアクセス – キオスク モード
- システム レベルでキオスク モードを適用する新しいキオスク 方法を有効にすることで、キオスクの ID 管理を減らしました。

この新機能を使用すると、IT 管理者は、システム レベルで適用できる複数のアプリ キオスク モード用に HoloLens 2 デバイスを構成できます。このモードは、システム上の任意の ID とアフィニティを持たず、デバイスにサインインするすべてのユーザーに適用されます。 この新機能の詳細については [、「HoloLens グローバル割り当てアクセス キオスク」を参照してください](hololens-global-assigned-access-kiosk.md)。

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>複数アプリキオスク モードでのアプリケーションの自動起動 
- アプリの自動起動に重点を置いてエクスペリエンスを向上し、キオスク モード エクスペリエンス用に選択された UI とアプリの選択をさらに増やします。

複数アプリキオスク モードにのみ適用され、割り当て済みアクセス構成で以下の強調表示された属性を使用して、1 つのアプリのみを自動起動に指定できます。 

ユーザーがサインインすると、アプリケーションが自動的に起動されます。 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>エラー処理のためのキオスク モードの動作の変更
- キオスク モードのエラーで使用可能なアプリを排除することで、より安全なキオスク モード。 

以前は、キオスク モードの適用でエラーが発生しました。HoloLens は、すべてのアプリケーションを [スタート] メニューに表示するために使用しました。 Windows Holographic バージョン20H2 でエラーが発生した場合は、次のように [スタート] メニューにアプリが表示されません。 

![キオスクモードが失敗したときにどのように表示されるかを示した画像。](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens ポリシー
- デバイスを管理するために作成される HoloLens 専用のデバイス管理オプション。 

Windows Holographic バージョン20H2 の HoloLens 2 デバイスに対して、新しい mixed reality ポリシーが作成されました。 新しい制御可能な設定には、明るさの設定、音量の設定、混合 reality キャプチャでのオーディオ記録の無効化、診断が収集されるタイミングの設定、AAD グループメンバーシップキャッシュなどがあります。  

| 新しい HoloLens ポリシー                                | 説明                                                                               | メモ                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 明るさのボタンを無効にして、押したときに明るさを変更しないようにします。       | 1 Yes、0 No (既定値)                                                |
| MixedReality\VolumeButtonDisabled                  | ボリュームボタンを無効にして、押しても音量を変更できないようにします。               | 1 Yes、0 No (既定値)                                                |
| MixedReality\MicrophoneDisabled                    | HoloLens 2 でオーディオの記録ができないようにマイクを無効にします。                      | 1 Yes、0 No (既定値)                                                |
| MixedReality\FallbackDiagnostics                   | 診断ログを収集できるタイミングを制御します。                               | 0無効、デバイス所有者に対しては1が有効、すべての場合は 2 (既定) |
| MixedReality\HeadTrackingMode                      | 将来使用するために予約されています。                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | キオスクがグループを対象Azure ADに使用されるグループ メンバーシップ キャッシュの日数Azure AD制御します。 | 以下を参照してください。                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>オフライン キオスクAzure ADグループ メンバーシップをキャッシュする
- オフライン キオスクを AAD グループで最大 60 日間使用できます。

このポリシーでは、サインインしたユーザーの Azure AD グループを対象とする割り当てアクセス構成に対して、Azure AD グループ メンバーシップ キャッシュを使用できる日数を制御します。 このポリシー値が 0 より大きい値にのみ設定されている場合は、キャッシュが使用されます。それ以外の場合は使用されません。  

名前: AADGroupMembershipCacheValidityInDays URI 値: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最小 - 0 日  
最大 - 60 日 

このポリシーを正しく使用する手順: 
1. デバイス グループを対象とするキオスク用のデバイスAzure AD作成し、HoloLens デバイスに割り当てる。 
1. このポリシー値を必要な日数 (> 0) に設定し、HoloLens デバイスに割り当てるカスタム OMA URI ベースのデバイス構成を作成します。 
    1. URI の値は、./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays として OMA-URI テキスト ボックスに入力する必要があります。
    1. 値は、min または max allowed の間で指定できます。
1. HoloLens デバイスを登録し、両方の構成がデバイスに適用されるのを確認します。 
1. インターネットAzure ADユーザー 1 のサインインを許可し、ユーザーがサインインし、Azure AD グループ メンバーシップが正常に確認されると、キャッシュが作成されます。 
1. これでAzure ADユーザー 1 は HoloLens をオフラインにし、ポリシー値で X 日が許可されている限りキオスク モードに使用できます。 
1. 手順 4 と 5 は、他の Azure AD ユーザー N に対して繰り返し実行できます。ここで重要な点は、すべての Azure AD ユーザーがインターネットを使用してデバイスにサインインする必要がある点です。少なくとも 1 回は、キオスク構成の対象となる Azure AD グループのメンバーと判断できます。 
 
> [!NOTE]
> 手順 4. が実行されるまで、ユーザー Azure AD"切断" 環境で説明されているエラー動作が発生します。 

### <a name="new-device-restriction-policies-for-hololens-2"></a>デバイスの新しい制限ポリシー HoloLens 2
- プロビジョニングパッケージの追加や削除をブロックするなど、特定のデバイス管理ポリシーをユーザーが管理できるようにします。

新しく有効にされたポリシーにより、HoloLens 2 デバイスの管理オプションを追加できるようになりました。 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

この2つの新しいポリシー Allowaddのパッケージと Allowremoveのパッケージは、 [一般的なデバイスの制限](hololens-common-device-restrictions.md)に追加されています。

> [!NOTE]
> [Remotelock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)に関して、HoloLens では/Vendor/MSFT/RemoteLock/Lock 構成のみがサポートされます。 リセットや回復などの PIN を処理する構成はサポートされていません。

### <a name="new-power-policies-for-hololens-2"></a>HoloLens 2 の新しい電源ポリシー
- HoloLens が電源ポリシーを使用してスリープまたはロックする場合のその他のオプション。 

これらの新しく追加されたポリシーにより、管理者はアイドルタイムアウトなどの電源状態を制御できるようになります。 個々のポリシーの詳細を確認するには、そのポリシーのリンクをクリックしてください。

|     ポリシードキュメントのリンク                |     メモ                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Windows 構成デザイナーで使用する値の例を次に示します。  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Windows 構成デザイナーで使用する値の例を次に示します。  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Windows 構成デザイナーで使用する値の例、つまり100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Windows 構成デザイナーで使用する値の例、つまり100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows 構成デザイナーで使用する値の例 (つまり、   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows 構成デザイナーで使用する値の例 (つまり、  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

DisplayOffTimeoutOnBattery と DisplayOffTimeoutPluggedIn のこれら 2 つの新しいポリシーが、一般的なデバイス制限 [に追加されています](hololens-common-device-restrictions.md)。

> [!NOTE]
> HoloLens 2で一貫したエクスペリエンスを得る場合は、DisplayOffTimeoutOnBattery と StandbyTimeoutOnBattery の両方の値が同じ値として設定されている必要があります。 DisplayOffTimeoutPluggedIn と StandbyTimeoutPluggedIn にも同じことが適用されます。 モダン スタンバイ [の詳細については、「ディスプレイ、スリープ](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) 、休止状態のアイドル タイマー」を参照してください。

### <a name="newly-enabled-update-policies-for-hololens"></a>HoloLens の新しく有効にされた更新ポリシー
- 更新プログラムをインストールする場合や、[更新プログラムの一時停止] ボタンを無効にして更新を確認するその他のオプション。

これらの更新ポリシーは、次のデバイスでHoloLens 2されています。
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

これらの更新プログラム ポリシーと HoloLens デバイスに使用する方法の詳細については [、「HoloLens](hololens-updates.md)更新プログラムの管理」を参照してください。

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>[有効] [設定] ページの表示HoloLens 2
- 設定アプリの UI コントロールが増え、ページの選択が限られていると混乱する可能性があります。

IT 管理者がシステム設定アプリの特定のページを表示またはアクセスできないか、指定したページを除くすべてのページに対してこれを行えるようにするポリシーを有効にしました。 この機能を完全にカスタマイズする方法については、以下のリンクをクリックしてください。

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

このページでカスタマイズできるページ設定については、HoloLens 2 の [設定 [URI] ページを参照してください](settings-uri-list.md)。 
 
![設定アプリで変更されているアクティブな時間のスクリーンショット](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>リサーチモード
研究モードでは、HoloLens 2 はコンピュータービジョン研究の potent ツールになります。 HoloLens 2 の Research モードには、以前のエディションと比較して次のような利点があります。
-   HoloLens (第1世代) リサーチモードで公開されているセンサーに加えて、加速度計、ジャイロスコープ、磁力計を含む IMU センサーへのアクセスが提供されるようになりました。
-   HoloLens 2 には、リサーチモードと共に使用できる新しい機能が用意されています。 具体的には、より充実した一連の実験を提供できる、明確な追跡 Api と視点追跡 Api へのアクセスを提供します。

現在、調査担当者は、HoloLens デバイスでリサーチモードを有効にして、これらの外部に面しているすべての未加工のイメージセンサーストリームにアクセスできるようになりました。 HoloLens 2 の研究モードでは、加速度計、ジャイロスコープ、および磁力計の読み取りにもアクセスできます。 ユーザーのプライバシーを保護するために、未加工の視点を追跡するカメライメージは、リサーチモードでは使用できませんが、既存の Api を通じて目を見つめます。

詳細については、 [調査モードのドキュメント](https://docs.microsoft.com/windows/mixed-reality/research-mode) をご覧ください。

### <a name="recording-length-increased"></a>記録の長さが増加しました
お客様からのフィードバックにより、 [混合現実のキャプチャ](holographic-photos-and-videos.md)の記録長さが増加しています。 混合の現実のキャプチャは、既定では5分に制限されなくなりましたが、代わりに使用可能なディスク領域に基づいて最大記録長が計算されます。 デバイスは、ディスクの空き領域の最大80% まで、使用可能なディスク領域に基づいて、最大ビデオ記録期間を見積もります。

> [!NOTE]
> 次のいずれかが発生した場合、HoloLens では既定のビデオ記録の長さ (5 分) が使用されます。
> - 推定最大記録期間は、既定の5分よりも小さくなっています。
> - 使用可能なディスク領域が、合計ディスク領域の20% 未満です。

完全な要件については、 [holographic の写真とビデオ](holographic-photos-and-videos.md#maximum-recording-length) のドキュメントを参照してください。 

### <a name="improvements-and-fixes-in-the-update"></a>更新プログラムの機能強化と修正:
- OOBE の他の画面がダークモードになりました。
- 詳細については、オンラインの最新のプライバシーに関する声明を参照してください。
- ユーザーがプロビジョニング パッケージを使用して VPN プロファイルをプロビジョニングできない問題に対処しました。
- VPN 接続のプロキシ構成の問題を修正しました。
- AllowUsbConnection 用の NCM 用 MDM を使用して USB 関数の列挙を無効にするポリシーを更新しました。
- デバイスがシングル アプリ キオスク として設定されている場合に、HoloLens デバイスがメディア転送プロトコル (MTP) を使用して エクスプローラー に表示されるのを妨げる問題に [対処しました](hololens-kiosk.md)。 MTP (および USB 接続全般) は [、AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) ポリシーを使用して引き続き無効にできます。
- キオスク モードで、デバイスのアイコンがスタート メニュー正しくスケーリングされる問題を修正しました。
- 特定のグループを対象とするキオスク モードに HTTP キャッシュが干渉Azure AD修正しました。
- 開発者モードを無効にし、開発者モードを再び有効にしない限り、プロビジョニング パッケージで開発者モードを有効にした後、ユーザーが [ペア] ボタンを使用できない問題を修正しました。

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic バージョン 1903 - 2020 年 11 月の更新プログラム
- ビルド 18362.1085

この毎月の品質更新プログラムには、重要な変更は含められないので、最新の機能リリース ビルドである Windows Holographic バージョン 20H2 をお試しください。

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic バージョン 2004 - 2020 年 10 月の更新プログラム
- ビルド 19041.1124
 
更新プログラムの機能強化と修正:

- ランタイム システム エラーの原因となる不要なチェックを削除しました。

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic バージョン 1903 - 2020 年 10 月の更新プログラム
- ビルド 18362.1081

この毎月の品質更新プログラムには、重要な変更は含まれているのではなく、Windows Holographic バージョン 2004 用の最新のビルドをお試しください。

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic バージョン 2004 - 2020 年 9 月の更新プログラム
- ビルド19041.1117

更新プログラムの機能強化と修正:

- Supports複数インスタンス = "true" が package.appxmanifest に存在する場合、Visual Studio がアプリケーションをデバッグできない問題に対処します。
- このリリースには、ネットワークプロキシ経由のインターネット検出の失敗に対処するための NCSI プロキシ検出修正が含まれています。 NCSI は、コンピュータープロキシとプロファイルごとのプロキシを使用して、インターネット接続を検出できます。 ユーザーごとのプロキシは、将来のリリースでは NCSI によってサポートされる予定です。
- ほとんどの Windows Mixed Reality デバイスでは、ユーザーのヘッドが前方にあるニュートラルな位置にあるときに、前方方向ベクトルが地面に平行になります。 ただし、以前のバージョンの HoloLens 2 では、ベクターがディスプレイパネルに対して垂直に配置されています。これは、理想的な向きに対して数度下に傾斜します。 新しいバージョンの HoloLens 2 では、フォームファクター間のセマンティクスの一貫性を確保するために、これが修正されています。
- 特定のシナリオでの追跡の損失を軽減する、手作業による追跡の堅牢性が向上しました。
- このリリースには、ビデオキャプチャの問題に寄与する可能性があるオーディオタイムスタンプの品質を向上させる修正が含まれています。

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic、バージョン 1903-9 月2020更新プログラム
- ビルド18362.1079

更新プログラムの機能強化と修正:

- ほとんどの Windows Mixed Reality デバイスでは、ユーザーのヘッドが前方にあるニュートラルな位置にあるときに、前方方向ベクトルが地面に平行になります。 ただし、以前のバージョンの HoloLens 2 では、ベクターがディスプレイパネルに対して垂直に配置されています。これは、理想的な向きに対して数度下に傾斜します。 新しいバージョンの HoloLens 2 では、フォームファクター間のセマンティクスの一貫性を確保するために、これが修正されています。
- 特定のシナリオでの追跡の損失を軽減する、手作業による追跡の堅牢性が向上しました。

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic、バージョン 2004-2020 年8月更新
- ビルド19041.1113

更新プログラムの機能強化と修正:

- 設定アプリは、ユーザーに従って Iris Enrollment または Eye Tracking の調整エクスペリエンスに移動しなくなりました。
- デバイスの名前を変更し、他のアクション (ネットワークへの接続など) を実行するプロビジョニング パッケージを OOBE 中に適用すると、名前の変更のためにデバイスの再起動後に他のアクションを実行できなかったバグを修正しました。
- 初期デバイス設定の変更された配色は、視覚的な品質を向上させるためにフローします。

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic バージョン 1903 - 2020 年 8 月の更新プログラム
- ビルド 18362.1074

この毎月の品質更新プログラムには、重要な変更は含まれているのではなく、Windows Holographic バージョン 2004 用の最新のビルドをお試しください。

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic バージョン 2004 - 2020 年 7 月の更新プログラム
- ビルド 19041.1109

更新プログラムの機能強化と修正:

- 開発者は、セキュリティで保護された接続が必要なデバイス ポータルを有効または無効にするか選択できます。
- OS の更新後のアプリケーションの起動に対する信頼性が向上しました。
- 既定の受信トレイの明るさを 100% に変更しました。
- Windows デバイス ポータル の HTTPS 転送に関する問題に対処HoloLens 2。

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic バージョン 1903 - 2020 年 7 月の更新プログラム
- ビルド 18362.1071

更新プログラムの機能強化と修正:

- 追跡を失った場合や回復するときに Unity アプリケーションでホログラムが消える可能性がある問題を修正しました。
- 特定のデバイスでハードウェア アクセラレーションで HoloLens エミュレーターを使用している間に、排他的な HoloLens アプリがシェルにクラッシュする原因となる問題を修正しました。
- サーバー上のアプリケーションの HTTPS 転送に関するWindows デバイス ポータルに対処HoloLens 2。

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic、バージョン 2004-6 月2020更新プログラム
- ビルド19041.1106

更新プログラムの機能強化と修正:

- カスタム MRC レコーダーでは、特定のプロパティの既定値が指定されていない場合、その既定値が新しくなりました。
  - *MRC ビデオ効果* で、次のようにします。
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (イマーシブヘッドセット))
  - *MRC オーディオ効果* で、次のようにします。
    - LoopbackGain (Windows デバイスポータルの Mixed Reality キャプチャページの現在の "アプリオーディオゲイン" 値)
    - マイクロ電話の獲得 (Windows デバイスポータルの Mixed Reality キャプチャページの現在の "Mic オーディオゲイン" 値)
- 混合現実のキャプチャシナリオでオーディオ品質を向上させるバグを修正した。 具体的には、この修正によって、[ **スタート** ] メニューが表示されたときに、録音のオーディオ glitching が削除されます。
- 記録されたビデオにおけるホログラムの安定性が向上しました。
- デバイスが複数日間スタンバイ状態のままになった後に、mixed reality capture がビデオを記録できない問題を解決しました。
- Unity アプリケーションでは、HolographicSpace API は一般に無効になっています。 この動作により、[バックグラウンドで実行する] 設定が有効になっている場合でも、バイザーが反転されたときに一部のアプリが一時停止する原因となる問題が回避されます。 この API は、Unity バージョン2018.4.18 以降および2019.3.4 以降で有効になりました。
- Wi-Fi 接続を介してデバイスポータルにアクセスすると、証明書が無効なために web ブラウザーがアクセスできなくなる可能性があります。 デバイス証明書が既に信頼されている場合でも、ブラウザーは "ERR_SSL_PROTOCOL_ERROR" などのエラーを報告することがあります。 この場合、セキュリティ警告を無視するオプションがないため、デバイスポータルに進行することはできません。 この更新プログラムによって問題が解決されました。 デバイス証明書が以前にダウンロードされ、ブラウザーのセキュリティ警告を削除するために PC で信頼されている場合、SSL エラーが発生した場合は、ブラウザーのセキュリティ警告に対処するために新しい証明書をダウンロードして信頼する必要があります。
- MSIX パッケージを使用してアプリをインストールできるランタイム プロビジョニング パッケージを作成する機能を有効にしました。
- [設定] [システム ホログラム] に設定を追加しました。これにより、ユーザーはデバイスのシャットダウン時に、Mixed Realityからすべてのホログラムを  >    >  自動的に削除できます。
- HoloLens エミュレーターでピクセル形式を黒にレンダリングする HoloLens アプリの原因となる問題を修正しました。
- Iris ログイン中にクラッシュを引き起こしたバグを修正しました。
- 既に現在のアプリに対するストアのダウンロードの繰り返しに関する問題を修正しました。
- イマーシブ アプリがアプリを繰り返し開かMicrosoft Edge修正しました。
- 1903 リリースから更新した後の初期ブートでの Photos アプリの起動に関する問題を修正しました。
- パフォーマンスと信頼性の向上。

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic バージョン 1903 - 2020 年 6 月の更新プログラム
- ビルド 18362.1064

更新プログラムの機能強化と修正:

- カスタム MRC レコーダーは、指定されていない場合、特定のプロパティに対して新しい既定値を持っています。
  - *MRC ビデオ効果の場合*:
    - PreferredOgramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (イマーシブ ヘッドセット))
  - *MRC オーディオ効果:*
    - LoopbackGain (現在の "App Audio Gain" の値は、Mixed Reality キャプチャ ページWindows デバイス ポータル)
    - MicrophoneGain (現在の "Mic Audio Gain" の値は、Mixed Reality キャプチャページWindows デバイス ポータル)
- Unity アプリケーションでは、HolographicSpace API は一般に無効になっています。 この動作により、バックグラウンドで実行する設定が有効になっている場合でも、バイザーが反転されたときに一部のアプリが一時停止する原因となる問題が回避されます。 この API は、Unity バージョン2018.4.18 以降、および2019.3.4 以降で有効になりました。
- Hololens エミュレーターで、ピクセル形式を変更する HoloLens アプリが黒をレンダーするような場合に発生する問題を修正しました。
- 1903リリースから更新された後の最初の起動時の Photos アプリの起動に関する問題を修正しています。

## <a name="windows-holographic-version-2004"></a>Windows Holographic、バージョン2004  
- ビルド-19041.1103

HoloLens 2、 *Windows Holographic、バージョン 2004* の2020年5月の主要なソフトウェア更新プログラムには、優れた新機能のホストが含まれています。たとえば、Windows 自動操縦、アプリのダークモード、USB イーサネットの 5G/LTE ホットスポットのサポートなどがあります。 最新のリリースに更新するには、**設定**   アプリを開き、[ **update & Security**] にアクセスして、[ **更新プログラムの確認**   ] ボタンを選択します。 

|             機能                              |          Description                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Windows 自動操縦を使用して新しいデバイスを事前に構成し、シームレスにセットアップする                 |
|       FIDO 2 のサポート                             |          共有デバイスの高速で安全な認証を実現するための FIDO2 セキュリティキーのサポート            |
|       プロビジョニングの向上                      |          USB ドライブから HoloLens にプロビジョニングパッケージをシームレスに適用する                              |
|       アプリケーションのインストール状態                 |          アプリ用の設定アプリが MDM 経由で HoloLens 2 にプッシュされていることを確認する               |
|       構成サービスプロバイダー (Csp)   |          管理者の制御機能を強化するための新しい構成サービスプロバイダーの追加                 |
|       USB 5G/LTE のサポート                       |          拡張された USB イーサネット機能により、5G/LTE のサポートが有効になります。                                    |
|       ダーク アプリ モード                              |          ダーク モードとライト モードの両方をサポートするアプリで使用できるダーク アプリ モード。表示エクスペリエンスが向上します        |
|       音声指示コマンド                             |          HoloLens をハンズフリーで制御する追加のシステム音声コマンドのサポート                           |
|       手の追跡の機能強化                 |          手の追跡の機能強化により、ボタンと 2D スレートの相互作用をより正確に行える                        |
|       品質の向上と修正                 |          プラットフォーム全体のさまざまなシステム パフォーマンスと信頼性の向上                            |

### <a name="support-for-windows-autopilot"></a>サービスのWindows Autopilot

Windows AutopilotをHoloLens 2、デバイスの販売チャネルが HoloLens を Intune テナントに事前登録できます。 デバイスが到着すると、テナントの下に共有デバイスとして自己展開する準備が整います。 自己展開を利用するには、USB-C からイーサネットを使用して、セットアップの最初の画面でデバイスがネットワークに接続する必要があります。

ユーザーが Autopilot の自己展開プロセスを開始すると、次の手順が完了します。

1. デバイスをデバイスに参加Azure Active Directory (Azure AD)。
1. デバイスAzure AD (または別の MDM サービス) にMicrosoft Intuneを使用します。
1. デバイスを対象とするポリシー、証明書、およびネットワーク プロファイルをダウンロードします。
1. デバイスをプロビジョニングします。
1. ユーザーにサインイン画面を表示します。

詳細については、評価ガイド [のWindows AutopilotのHoloLens 2を参照してください](https://docs.microsoft.com/hololens/hololens2-autopilot)。

*今すぐ AutoPilot プレビューに参加するには、アカウント マネージャーに問い合わせください。Autopilot 対応デバイスの出荷は間もなく開始されます。*

### <a name="fido2-security-key-support"></a>FIDO2 セキュリティ キーのサポート

一部のユーザーは、職場または学校環境で HoloLens デバイスを他のユーザーと共有します。 このため、ユーザーが長いユーザー名とパスワードを入力しなくても簡単に実行できるようにすることが重要です。 高速 Id オンライン (FIDO) を使用すると、組織内のすべてのユーザー (Azure AD テナント) は、ユーザー名やパスワードを入力しなくても HoloLens にシームレスにサインインできます。

FIDO2 セキュリティキーは、"unphishable" 標準ベースのパスワードなし認証方法であり、任意のフォームファクターで使用できます。 FIDO は、パスワードなし認証用のオープンスタンダードです。 これにより、ユーザーと組織はユーザー名やパスワードを使用せずに自分のリソースにサインインできるようになります。 代わりに、デバイスに組み込まれている外部セキュリティキーまたはプラットフォームキーを使用します。

開始するには、「 [パスワードなしセキュリティキーのサインインを有効に](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)する」を参照してください。

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>プロビジョニングパッケージによる MDM 登録の向上

プロビジョニングパッケージを使用すると、HoloLens の既定の操作ではなく、構成ファイルを使用して HoloLens 構成を設定できます。 以前は、プロビジョニングパッケージを HoloLens 内部メモリにコピーする必要がありました。 USB ドライブを使用すると、複数の HoloLens デバイスでの再利用が容易になり、デバイスを並行してプロビジョニングすることができます。 プロビジョニングパッケージでは、デバイス管理に登録するためのフィールドもサポートされるようになりました。プロビジョニング後に手動で設定する必要はありません。

実行方法:

1. Windows ストアから最新バージョンの Windows 構成デザイナーを PC にダウンロードします。
1. [ **Hololens デバイス** のプロビジョニング] [  >  **hololens 2 デバイスのプロビジョニング**] を選択します。
2. 構成プロファイルを作成します。 次に、作成されたすべてのファイルを USB C ストレージデバイスにコピーします。
3. USB C デバイスを、新たにアップデートされた HoloLens に接続します。 次に、**音量を下げ** た電源ボタンを押して、  +  プロビジョニングパッケージを適用します。

### <a name="line-of-business-application-install-status"></a>基幹業務アプリケーションのインストール状態

HoloLens にとって、業務アプリの MDM アプリの展開と管理は非常に重要です。 管理者とユーザーは、監査と診断のためにアプリのインストール状態を表示する必要があります。 このリリースでは、アカウントアクセスの設定に関する記事の「仕事 **または学校に** アクセスする」の詳細を  >    >  **追加しました**  >  **。アカウント情報 をクリック**  >  **します**。

### <a name="additional-csps-and-policies"></a>その他の CSP とポリシー

構成 [サービス プロバイダー (CSP) は](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) 、デバイスの構成設定を読み取り、設定、変更、または削除するインターフェイスです。 このリリースでは、展開された HoloLens デバイスよりも管理者のコントロールを増やすポリシーのサポートを追加しました。 HoloLens でサポートされている CSP の一覧については [、「NetworkQoSPolicy CSP 」を参照してください](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。

このリリースでの新しい内容

**Policy CSP** 

ポリシー構成サービス プロバイダーを使用すると、企業は Windows デバイスでポリシーを構成できます。 このリリースでは、HoloLens の新しいポリシーを追加しました。ここに記載されています。 詳細については、 でサポート[されているポリシーの PS に関するページをHoloLens 2。](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessGazeInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- AllowWiFi 

**NetworkQoSPolicy CSP**

NetworkQoSPolicy 構成サービスプロバイダーは、ネットワークのサービス品質 (QoS) ポリシーを作成します。 QoS ポリシーは、一連の照合条件に基づいて、ネットワーク トラフィックに一連のアクションを実行します。 詳細については、「 [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)」を参照してください。

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>5G/LTE テザリングさデバイス向けの拡張された USB イーサネットサポート

5G/LTE フォンや Wi-Fi ホットスポットなど、特定のモバイルブロードバンドデバイスを USB 経由で HoloLens 2 にテザリングさするときに、サポートが追加されました。 これらのデバイスは、別のイーサネット接続として [ **ネットワーク設定** ] に表示されるようになりました。 (外部ドライバーを必要とするモバイルブロードバンドデバイスはサポートされていません)。この機能により、Wi-Fi を利用できず Wi-Fi テザリングで十分なパフォーマンスが得られない場合に、高帯域幅の接続が可能になります。 サポートされている USB デバイスの詳細については、「 [Bluetooth および Usb C デバイスへの接続](https://docs.microsoft.com/hololens/hololens-connect-devices)」を参照してください。  

### <a name="hand-tracking-improvements"></a>手動追跡の機能強化

このリリースには、いくつかの手動追跡の機能強化が含まれています。

- **ポイントの安定性:** これで、システムは、palm によって occluded されたときにインデックスの指を resists 曲げます。 この変更により、ボタン、型、コンテンツのスクロールなどをプッシュするときの精度が向上します。 
- **偶発的なエアタップの削減:** エアタップジェスチャの検出を改善しました。 いくつかの一般的なシナリオでは、ユーザーを自分の側にドロップしたときなど、誤ったアクティベーションが減ります。
- **ユーザースイッチの信頼性:** デバイスを共有するときに、手動でサイズを更新すると、システムの速度と信頼性が向上しました。
- **手作業の盗難:** センサーの2つ以上のハンズオンビューがあるケースの処理を改善しました。 複数の人が近くに作業している場合、追跡されたハンドがシーン内の他のユーザーの手に "ジャンプ" する可能性は非常に低くなります。
- **システムの信頼性:** デバイスの負荷が高いときに、ハンドトラッキングが動作を停止する原因となった問題を修正しました。

### <a name="dark-mode"></a>ダーク モード

多くの Windows アプリで、ダークモードとライトモードの両方がサポートされるようになりました。 HoloLens 2 ユーザーは、両方をサポートするアプリの既定のモードを選択できます。 更新後、既定のアプリ モードは "濃色" になりますが、この設定を簡単に変更できます。[設定] [システムの色] [既定のアプリ モードを選択]  >    >    >  **に移動します**。 

これらの "インボックス" アプリでは、ダーク モードがサポートされています。 

- 設定 
- Microsoft Store 
- Mail 
- 予定表 
- エクスプローラー 
- フィードバック Hub 
- OneDrive 
- Photos 
- 3D ビューアー 
- 映画 & テレビ 

![タイル表示されたダーク モードのウィンドウ](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>システム音声コマンド

これで、デバイス上の任意のアプリで音声コマンドを使用できます。 詳細については、「音声を [使用して HoloLens を操作する」を参照してください](https://docs.microsoft.com/hololens/hololens-cortana)。 「サポート[されている言語」も参照HoloLens 2。](https://docs.microsoft.com/hololens/hololens2-language-support)  

### <a name="cortana-updates"></a>Cortana の更新プログラム

更新されたアプリは、Microsoft 365と統合され、デバイス全体で (現在、US-Englishされます)。 このHoloLens 2 Cortana では、ボリュームの調整や再起動など、特定のデバイス固有のコマンドがサポートされなくなりました。 これらのオプションは、新しいシステム音声コマンドでサポートされています。 新しい Cortana アプリの詳細については、ブログを [参照してください](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)。

### <a name="quality-improvements-and-fixes"></a>品質の向上と修正

更新プログラムの機能強化と修正:  
- アクティブなディスプレイ調整システムを導入しました。 この機能により、ホログラムの安定性と配置が向上します。 これで、頭を横から横に移動すると、その場所に残ることになります。
- HoloLens へのWi-Fiが定期的に中断されるバグを修正しました。 アプリケーションで低待機時間のストリーミングが必要と示されている場合は [、SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)関数 を呼び出して修正プログラムを実装します。
- リサーチモードでのストリーミング中に発生したデバイスのハングを修正しました。
- セッションの再開時に、適切なユーザーがサインイン画面に表示されない場合があるバグを修正します。
- ユーザーが **設定** を使用して MDM ログをエクスポートできない問題を修正した。
- すぐに使用できるセットアップの直後にある目の追跡の精度が予想よりも低くなるという問題を修正しました。
- 特定の条件下で、視線追跡サブシステムが初期化または調整を実行できなかった問題を修正しました。
- 既に調整されたユーザーに対して目の調整が求められる問題を修正した。
- 目の調整中にドライバーがクラッシュする問題を修正した。
- 電源ボタンを繰り返し押すと60秒のシステムタイムアウトが発生し、シェルがクラッシュする問題を修正しました。
- 深度バッファーの安定性が向上しました。
- フィードバックを簡単に共有できるように、フィードバックハブに [ **共有** ] ボタンが追加されました。
- RoboRaid wan't が正しくインストールされているバグを修正しました。

### <a name="known-issues"></a>既知の問題

- Zh-tw システム言語の問題により、音声コマンドが mixed reality を撮影したり、デバイスの IP アドレスを表示したりするのを防ぐことができます。
- 問題が発生した場合は、デバイスの起動後に Cortana アプリを起動して、"Cortana" ボイスアクティベーションを使用する必要があります。 18362ビルドから更新した場合は、 **スタート** で動作しなくなった以前のバージョンの Cortana アプリ用に2つ目のアプリタイルが表示されることもあります。

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic、バージョン 1903-2020 更新プログラム 
- ビルド18362.1061

前に説明したように、この毎月の品質更新プログラムには、チームが Windows Holographic バージョン2004で更新プログラムを実行していたため、重要な変更は含まれていません。

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic、バージョン 1903-2020 年4月更新
- ビルド18362.1059

**サポートされているアプリのダークモード** 

多くの Windows アプリでは、ダーク モードとライト モードの両方がサポートされています。 HoloLens 2両方の配色をサポートするアプリの既定のモードを選択できます。 お客様からのフィードバックに基づいて、既定のアプリ モードを "ダーク" に設定していますが、この設定はいつでも簡単に変更できます。[設定] **> [システム] > [色**] に移動して [既定のアプリ モードを選択する] を見つける。 

これらの "インボックス" アプリでは、ダーク モードがサポートされています。
- 設定
- Microsoft Store
- Mail
- 予定表
- エクスプローラー
- フィードバック Hub
- OneDrive
- Photos
- 3D ビューアー
- 映画 & テレビ

**更新プログラムの機能強化と修正:** 
- シェル オーバーレイが Mixed Reality キャプチャに含まれる必要があります。
- Unreal 開発者は、アプリの 3D ビュー ページを使用デバイス ポータルアプリケーションをテストおよびデバッグできます。
- *HolographicDepthReprojectionMethod DepthReprojection* アルゴリズムを使用すると、Mixed Reality キャプチャのホログラムの安定性が向上しました。
- 32 ビット ARM アプリで "WinRT IStreamSocketListener API クラスが登録されていません" というエラーを修正しました。

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic バージョン 1903 - 2020 年 3 月更新 
- ビルド 18362.1056

更新プログラムの機能強化と修正:

- *HolographicDepthReprojectionMethod AutoPlanar* アルゴリズムを使用すると、Mixed Reality キャプチャのホログラムの安定性が向上しました。
- 深度 MF サンプルにアタッチされている座標系がパブリック ドキュメントと一致する必要があります。
- 顧客がデバイス ポータルを使用して大量のテキストを貼り付け可能にすることで、開発者の生産性が向上しました。

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic バージョン 1903 - 2020 年 2 月の更新プログラム 
- ビルド 18362.1053

更新プログラムの機能強化と修正:

- Unity アプリケーション用の HolographicSpace.UserPresence API を一時的に無効にしました。 この変更により、[バックグラウンドで実行する] 設定が有効になっている場合でも、バイザーが反転されたときに一部のアプリが一時停止する原因となった問題が回避されます。
- 手動追跡によって発生するランダムな HUP クラッシュを修正しました。この場合、ユーザーは UI をフリーズしてから、数秒後にシェルに戻ることに気付きました。
- インデックス指をからかうすると、その指の上部が予期せずに curl される可能性が低くなるように、ハンドトラッキングが向上しました。
- ヘッド追跡、空間マッピング、およびその他のランタイムの信頼性が向上しました。

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic、バージョン 1903-1 月2020更新プログラム 
- ビルド18362.1043
 
更新プログラムの機能強化と修正:

- HoloLens 2 のエミュレーターを使用する場合の排他的なアプリの安定性が向上しました。

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic、バージョン 1903-12 月2019更新プログラム 
- ビルド18362.1042

更新プログラムの機能強化と修正:

- 最終ステージ再現 (LSR) 修正が導入されました。 ホログラムの視覚的レンダリングが改善され、詳細をより正確に把握できるようになりました。 この現象は、アプリがホログラムの深さを正しく設定していない場合に、この更新後により顕著になります。
- 排他アプリの安定性と排他アプリ間のナビゲーションを修正します。
- デバイスが数日間スタンバイ状態になった後に、mixed reality capture がビデオを記録できない問題を解決しました。
- ホログラムの安定性が向上しました。

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic、バージョン 1903-2019 更新プログラム 
- ビルド18362.1039

更新プログラムの機能強化と修正:

- en-CA **と** en-AU の初期セットアップ中に音声コマンドを選択する機能を修正しました。
- 最新の Unity および MIXED REALITY Toolkit (MRTK) バージョンに配置されたオブジェクトのビジュアル品質が向上しました。
- ホログラフィック アプリケーションが開いてから閉じるまで、起動時に一時停止状態でスタックする問題スタート メニュー修正しました。
- OpenXR ランタイム準拠の修正と、HoloLens 2エミュレーターの機能強化。
