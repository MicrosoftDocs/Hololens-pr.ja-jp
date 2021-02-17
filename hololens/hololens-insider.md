---
title: Microsoft HoloLens の Insider Preview
description: Insider ビルドを使い始め、HoloLens の次の主要なオペレーティング システム更新プログラムに関する貴重なフィードバックを提供する方法について説明します。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 2/16/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 885f9a841c5f59f2816667256de0856f8a1f2612
ms.sourcegitcommit: ab35169529776f0682eeb8fa448c9d9e8f598513
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/17/2021
ms.locfileid: "11340542"
---
# Microsoft HoloLens の Insider Preview

HoloLens 用の最新の Insider Preview ビルドへようこそ! HoloLens [の次](hololens-insider.md#start-receiving-insider-builds) の主要なオペレーティング システム更新プログラムの使用を開始し、貴重なフィードバックを提供する方法は簡単です。

## Windows Insider リリース ノート

Windows Insider の新機能のフライトを再び開始します。 新しいビルドは、最新の更新プログラムの開発チャネルへのフライトです。 このページは、Windows Insider ビルドに追加された機能と更新プログラムが追加され、引き続き更新されます。  これらの更新プログラムを実際に組み合わせ、準備を整えます。

> [!IMPORTANT]
> 以前にキオスクで設定アプリまたは Microsoft Edge アプリを使用していた場合は、これらのアプリを別のアプリ ID を使用する新しいアプリに置き換えました。 キオスク モードの新しいアプリの新しい [AUMID については、以下を参照することを強くお勧](#use-the-new-settings-and-edge-apps-in-kiosk-modes) めしています。 これにより、キオスクで設定アプリを引き続き使用するか、新しい Microsoft Edge アプリを含めるかのどちらかが保証されます。

<br>

| 機能名                                              | 簡単な説明                                                                      | ビルドで使用可能 |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [新しい Microsoft Edge](#introducing-the-new-microsoft-edge) | HoloLens 2 では、Chromium ベースの新しい Microsoft Edge を使用できます。                         | 20279.1006 |
| [WebXR と 360 ビューアー](#webxr-and-360-viewer)             | イマーシブな Web エクスペリエンスと 360 のビデオ再生を試す                                           | 20289.1000 |
| [新しい設定アプリ](#new-settings-app)                     | 従来の設定アプリは、新しい機能と設定で更新されたバージョンに置き換えられる | 20279.1006 |
| [色の調整を表示する](#display-color-calibration)   | HoloLens 2 ディスプレイの代替カラー プロファイルを選択する                                | 20293.1000 |
| [既定のアプリ ピッカー](#default-app-picker)                 | ファイルまたはリンクの種類ごとに起動するアプリを選択する                                      | 20279.1006 |
| [Office Web アプリ](#office-web-app)                         | 新しい Web アプリOfficeが [すべてのアプリ] に表示されます。                                   | 20279.1006 |
| [スワイプして入力する](#swipe-to-type)                           | ホログラフィック キーボードで指のヒントを使って単語を "スワイプ" する                        | 20279.1006 |
| [USB-C 外部マイクのサポート](#usb-c-external-microphone-support) | アプリやリモート アシストには USB-C マイクを使います。| 20279.1006 |
| [キオスク モードの新しいアプリの新しい AUMID](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | 新しい設定とエッジ アプリの AUMID | 20279.1006 |
| [ページ設定を表示する新しい SettingsURIs](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | 20 以上の新しい SettingsURIs for Settings/PageVisibilityList ポリシー | 20289.1000 |
| [キオスク モードの失敗の手渡しの改善](#kiosk-mode-behavior-changes-for-handling-of-failures) | キオスク モードでは、空のスタート メニューの前にグローバル割り当てられたアクセスが見えます。 | 20279.1006 |
| [フォールバック診断を構成する](#configuring-fallback-diagnostics-via-settings-app) | 設定アプリでのフォールバック診断動作の設定 | 20279.1006 |
| [近くのデバイスと情報を共有する](#share-things-with-nearby-devices) | HoloLens から PC へのファイルまたは URL の共有 | 20279.1006 |
| [新しい OS 更新プログラムのトラブルシューティング ツール](#new-os-update-troubleshooter) | OS 更新プログラムの設定の新しいトラブルシューティング ツール | 20279.1006 |
| [更新プログラムの機能強化と修正](#improvements-and-fixes-in-the-update) | 更新プログラムの追加の修正。 | 20279.1006 |

### 新しい Microsoft Edge の導入

![従来の Microsoft Edge ロゴから新しい Microsoft Edge ロゴへのアニメーション](images/new-edge.gif)

新しい Microsoft Edge は [Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) オープン ソース プロジェクトを採用して、お客様との互換性を向上し、Web 開発者向けの Web の断片化を減らしています。

この Insider プレビューでは、HoloLens 2 のお客様が新しい Microsoft Edge を初めて利用できます。 新しい Microsoft Edge は最終的に HoloLens 2 の従来の Microsoft Edge に取って代わる機能ですが、現在、両方のブラウザーが Insider で利用できます。 新しい Microsoft Edge のフィードバック送信**** 機能またはフィードバック Hub を介して、フィードバックやバグをチームと[共有してください](hololens-feedback.md)。

![新しい Microsoft Edge のスクリーンショット](images/new-edge-ui.png)

#### 新しい Microsoft Edge の起動

Insider が利用できる Microsoft Edge には、新しい Microsoft Edge の新しい Microsoft Edge アイコン (青と緑のスループ アイコンで表される) と従来の Microsoft Edge (白い ![ "e" アイコンで表される) の 2 つのバージョンがあります。 ](images/new_edge_logo.png) 新しい Microsoft Edge はスタート メニューにピン留めされ、Web リンクをアクティブ化すると自動的に起動します。 従来の Microsoft Edge を既定の Web ブラウザーとして使用する場合は、以下の手順に従って既定のアプリ [をリセットしてください](#default-app-picker)。

> [!NOTE]
> HoloLens 2 で新しい Microsoft Edge を初めて起動すると、設定とデータは従来の Microsoft Edge からインポートされます。 新しい Microsoft Edge を起動した後も従来の Microsoft Edge を使用し続ける場合、その新しいデータは従来の Microsoft Edge から新しい Microsoft Edge に同期されません。

#### 新しい Microsoft Edge のポリシー設定の構成

新しい Microsoft Edge では、IT 管理者は、従来の Microsoft Edge で利用していたよりも、HoloLens 2 のブラウザー ポリシーの広範なセットを提供します。

新しい Microsoft Edge のポリシー設定の管理について詳しく知る上で役立つリソースを次に示します。

- [Microsoft Intune を使って Microsoft Edge ポリシー設定を構成する](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Microsoft Edge Legacy から Microsoft Edge ポリシーへのマッピング](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome から Microsoft Edge ポリシーへのマッピング](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- [Microsoft Edge Enterprise の完全なドキュメント](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> 新しい Microsoft Edge でサポートされているブラウザー ポリシーの量が多いので、新しい各ポリシーが HoloLens 2 で動作するとは、チームは保証できません。 ただし、HoloLens 2 で以前サポートされた従来の各 Microsoft Edge ポリシーと同等の新しい Microsoft Edge よりもテストと確認が期待通り動作します。 HoloLens 2 で使用していた従来の各 Microsoft Edge ブラウザー ポリシーと同等の新しい Microsoft Edge を見つけるには [、Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) レガシから Microsoft Edge へのポリシー マッピングをご覧ください。
>
> HoloLens 2 では動作しない新しい** Microsoft Edge ポリシーが 2 つ以上あります。
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### HoloLens 2 の新しい Microsoft Edge に期待される機能

新しい Microsoft Edge は、新しい UWP アダプター レイヤーを使ったネイティブの Win32 アプリで、HoloLens 2 のような UWP 専用デバイスで実行することができるため、一部の機能はすぐに利用できない場合があります。 今後数か月の間に新しいシナリオと機能をサポートする予定なので、このスペースで最新の情報を確認してください。

**動作が予想されるシナリオと機能:**
- 初回実行時のエクスペリエンス、プロファイルへのサインイン、同期
- Web サイトは期待どおりにレンダリングされ、動作する必要があります
- ほとんどのブラウザー機能 (お気に入り、履歴など) は期待通りに動作する必要があります
- 濃色モード
- デバイスへの Web アプリのインストール
- 拡張機能のインストール (HoloLens 2 で正しく動作しない拡張機能を使用している場合は、お知らせください)
- PDF の表示とマーキング
- 1 つのブラウザー ウィンドウからの空間サウンド
- ブラウザーの自動更新と手動更新
- [印刷] メニューから PDF を保存する ([PDF に保存] オプションを使用)

**近日公開予定のシナリオと機能:**
- WebXR と 360 ビューアー拡張機能
- 環境内に配置された複数のウィンドウを閲覧する場合の正しいウィンドウへのコンテンツの復元

**動作しないシナリオと機能:**
- 同時オーディオ ストリームを使用する複数のウィンドウからの空間サウンド
- "見て、言ってみる"
- 印刷

**既知のブラウザーの問題の上位:**
- デバイスをリセットすると、新しい Microsoft Edge が削除されます。
- ホログラフィック キーボードの拡大鏡のプレビューに正しくないコンテンツが表示される

#### Microsoft Edge Insider チャネル

Microsoft Edge チームは、Edge Insider コミュニティ (ベータ、開発、Canary) の 3 つのプレビュー チャネルを利用できます。 プレビュー チャネルをインストールしても、HoloLens 2 にリリースされたバージョンの Microsoft Edge はアンインストールされません。また、複数の Microsoft Edge を同時にインストールできます。 

Edge Insider [コミュニティについて詳しくは、Microsoft Edge Insider](https://www.microsoftedgeinsider.com) ホームページをご覧ください。 さまざまな Edge Insider チャネルについて詳しくは、Edge Insider のダウンロード ページ [をご覧ください](https://www.microsoftedgeinsider.com/download)。

HoloLens 2 に Microsoft Edge Insider チャネルをインストールするには、次の 2 つの方法があります。

**デバイスへの直接インストール (現在は非管理対象デバイスでのみ利用可能)**
  1. HoloLens 2 で、Edge Insider ダウンロード [ページにアクセスします](https://www.microsoftedgeinsider.com/download)。
  1. インストールする Edge Insider チャネルの **HoloLens 2** のダウンロード ボタンを選択します。
  1. ダウンロードした .msix ファイルを、エッジ のダウンロード キューまたはデバイスの [ダウンロード] フォルダーから起動します (エクスプローラーを使用)。
  1. [アプリ インストーラーが](app-deploy-app-installer.md) 起動します。
  1. [インストール] **ボタンを選択** します。
  1. インストールが成功すると、スタート メニューの [すべてのアプリ] の一覧に Microsoft Edge **** Beta、Dev、Canary が個別のエントリとして表示されます。

**Windows Device Portal を使用して[](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)PC 経由でインストールする (HoloLens 2 で開発者モードを有効にする必要がある)**
  1. PC で、Edge Insider ダウンロード [ページにアクセスします](https://www.microsoftedgeinsider.com/download)。
  1. インストールする Edge Insider **チャネル** の [Windows 10 のダウンロード] ボタンの横にあるドロップダウン矢印ボタンを選択します。
  1. ドロップダウン **メニューで HoloLens 2** を選択します。
  1. .msix ファイルを PC の "Downloads" フォルダー (または簡単に見つけられている別のフォルダー) に保存します。
  1. PC [で Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) を使って、ダウンロードした .msix ファイルを HoloLens 2 にインストールします。
  1. インストールが成功すると、スタート メニューの [すべてのアプリ] の一覧に Microsoft Edge **** Beta、Dev、Canary が個別のエントリとして表示されます。

> [!NOTE]
> HoloLens 2 向け Windows Insider プレビューでは、デバイス上の Microsoft Edge のバージョンが、Microsoft Edge Insider チャネルの一部 (またはすべて) で利用可能なバージョンよりも高い場合があります。 これは、HoloLens 2 の Web ブラウザーを特に対象とする新機能と修正プログラムが、可能な限り迅速に Windows Insider に提供されます。 次の Windows 更新プログラムの一般リリースの直後に、Microsoft Edge Insider チャネル のビルドは HoloLens 2 の Microsoft Edge のバージョンを上回り、先に進む予定です。

### WebXR と 360 ビューアー

*Windows Insider ビルド 20289.1000 で追加*

新しい Microsoft Edge には、イマーシブな Web エクスペリエンスを作成するための新しい標準である WebXR のサポートが含まれています (WebVR に置き換わる)。 多くのイマーシブ Web エクスペリエンスは VR を念頭に置いて設計されました (ユーザーの視野を仮想環境に置き換えます)、これらのエクスペリエンスは HoloLens 2 でもサポートされています。 WebXR 標準では、物理環境を使用する拡張現実と複合現実のイマーシブ Web エクスペリエンスも可能になります。 開発者が WebXR でより多くの時間を費やすと、HoloLens 2 のお客様が試す新しい拡張および Mixed Reality イマーシブ エクスペリエンスが提供される予定です。

360 Viewer 拡張機能は WebXR 上に構築され、HoloLens 2 の新しい Microsoft Edge と共に自動的にインストールされます。 この Web 拡張機能を使用すると、360 度のビデオを体験できます。 YouTube では、最大で 360 のビデオを選択できます。そのため、最初に開始してください。

#### WebXR の使い方

1. WebXR がサポートされている Web サイトに移動します。
1. Web サイトの **[ENTER VR]** ボタンを選択します。 このボタンの場所と視覚的な表現は、Web サイトごとに異なる場合がありますが、次のように表示される場合があります。

    ![ENTER VR ボタンの例](images/75px-enter-vr.png)

1. 特定のドメインで WebXR エクスペリエンスを初めて起動しようとすると、ブラウザーはイマーシブ ビューに入る同意を求め、許可を選択 **します**。
1. [HoloLens 2 ジェスチャを使ってエクスペリエンス](hololens2-basic-usage.md#the-hand-tracking-frame)を操作します。
1. エクスペリエンスに [終了] ボタン**** が表示できない場合は、スタート ジェスチャを使[って](hololens2-basic-usage.md#start-gesture)戻ります。

**推奨 WebXR サンプル**
- 360 ビューアー (次のセクションを参照)
- [XR 恐竜](https://www.xrdinosaurs.com/)
- [バリタ エクスプレス](https://constructarca.de/game/barista-express/)
- [WebXR ペイント](https://threejs.org/examples/webxr_vr_paint.html)

#### 360 ビューアーの使い方

1. YouTube で 360 度のビデオに移動します。
1. ビデオ フレームで、Mixed Reality ヘッドセット ボタンを選択します。

    ![360 ビューアーをアクティブ化するボタン](images/enter-360-viewer.jpg)

1. 特定のドメインで 360 ビューアーを初めて起動しようとすると、ブラウザーはイマーシブ ビューに入る同意を求めます。 [許可] **を選択します**。
1. [エアタップ](hololens2-basic-usage.md#select-using-air-tap) を使って再生コントロールを表示します。 ハンド [レイと](hololens2-basic-usage.md#select-using-air-tap) エア タップを使用して、再生/一時停止、前方/戻るスキップ、キャプションのオン/オフ、エクスペリエンスの停止 (イマーシブ ビューを終了) します。 再生コントロールは、数秒間非アクティブ状態が続くと消えます。

#### WebXR と 360 ビューアーの既知の問題
- WebXR エクスペリエンスでは、ホログラムは、頭を傾けるか、環境内を移動するときにシフトまたは傾く可能性があります。
- WebXR エクスペリエンスの複雑さによっては、フレームレートが低下したり、引きつまずく場合があります。
- WebXR では、連結された手のジョイントはまだ使用できません。
- WebXR または 360 ビューアー エクスペリエンスを終了すると、Mixed Reality ホーム内のホログラムが再表示されるのに 30 秒以上かかる場合があります。
- YouTube 以外の Web サイトから 360 のビデオが期待通り動作しない場合があります。
- 360 のビデオがイマーシブ ビューに入らない場合 (または Mixed Reality ヘッドセット ボタンが表示されない場合) は、ページを更新してみてください。
- キャプションは、HoloLens 2 の 360 Viewer では表示されません。
- 360 ビューアーでビデオを一時停止すると、ビデオのレンダリングが停止します (ただし、再生ボタンを選択すると、再生が正しく再開されます)。
- 360 ビューアーの [次のビデオ] ボタンは、現在は機能しません。
- 2D ビデオはイマーシブな "theater" モードで再生できますが、フレームレートは 30 fps 未満になります。

#### WebXR と 360 ビューアーに関するフィードバックの提供

新しい Microsoft Edge のフィードバック送信**** 機能を使用して、フィードバックやバグをチームと共有してください。

### 新しい設定アプリ

このリリースでは、設定アプリの新しいバージョンが導入されています。 新しい設定アプリには、サウンド、Power & スリープ、ネットワーク & インターネット、アプリ、アカウント、簡単操作など、HoloLens 2 の新機能と拡張された設定が含まれています。

> [!NOTE]
> 新しい設定アプリは従来の設定アプリとは異なっているので、以前環境の周囲に配置した設定ウィンドウは、更新時に削除されます。

![新しい設定アプリのホーム ページ](images/new-settings-app.png)

**新機能と設定**
- 設定検索: キーワードまたは設定名を使用して、[設定] ホーム ページから設定を検索します。
- システム > サウンド:
  - 入力オーディオ デバイスと出力オーディオ デバイス: 入力オーディオ デバイスと出力オーディオ デバイスを個別に選択します (たとえば、Bluetooth ヘッドホンでオーディオを聞く場合や、オーディオ入力に USB-C マイクを使用する場合など)。
    > [!NOTE]
    > Bluetoothは HoloLens 2 ではサポートされていません。
  - アプリのボリューム: 各アプリのボリュームを個別に調整します。
- システム>電源&スリープ: 非アクティブな状態が一時間続くとデバイスがスリープ状態になるべき時期を選択します。
- システム>バッテリー: バッテリー節約機能モードを手動で有効にするか、バッテリー節約機能モードが自動的に有効になる時点でバッテリーしきい値を設定します。
- デバイス> USB: 既定では USB 接続を無効にできます。
- ネットワーク & インターネット:
  - これで、USB-C イーサネット アダプターがネットワーク 接続とインターネット&されます。
  - IP アドレスなど、USB-C イーサネット アダプターの設定が利用可能になります。
  - HoloLens 2 で、フライト モードを有効にできます。
- アプリ: ファイルとリンクの種類に使用する既定のアプリをリセットできます。 詳しくは、既定の [アプリ ピッカーに関するページをご覧ください](#default-app-picker)。
- 他>ユーザーのアカウント: デバイス所有者は、ユーザーの追加、標準ユーザーのデバイス所有者へのアップグレード、デバイス所有者の標準ユーザーへのダウングレード、ユーザーの削除を行います。
- 簡単操作: テキストサイズと視覚効果を変更します。

**既知の問題**
- 以前に配置した設定ウィンドウは削除されます (上記の注を参照)。
- [通知] ページにアクセスすると、設定アプリがクラッシュする可能性があります (調査中)。
- 現在、イーサネット ページは表示されます (間もなく修正されます)。
- 設定アプリを使ってデバイスの名前を変更できなくなりました (IT 管理者はプロビジョニング パッケージまたは MDM を使ってデバイスの名前を変更できます)。
- 新しい Microsoft Edge のバッテリー使用量は、UWP アダプター レイヤーでサポートされる Win32 デスクトップ アプリケーションとしての性質上、正確ではない可能性があります (間もなく修正される予定はありません)。

### 色の調整を表示する

*Windows Insider ビルド 20293.1000 で追加*

この新しい設定では、HoloLens 2 ディスプレイの代替カラー プロファイルを選択できます。 これは、特にディスプレイの明るさレベルが低い場合に、色の正確な表示に役立ちます。 色の調整の表示は、[設定] アプリの [システムの調整] ページ>確認できます。

#### 表示色調整の使い方

1. 設定アプリ **を起動** し、[System > **調整] に移動します**。
1. [ **表示色の調整] で**、[表示色調整 **の実行] ボタンを選択** します。
1. 表示色調整エクスペリエンスが起動し、バイザーが正しい位置に配置されていることを確認する必要があります。
1. 指示ダイアログ ボックスに進むと、ディスプレイは自動的に明るさ 30% に淡色表示されます。
    > [!TIP]
    > 環境内で淡色表示のシーンが表示される問題が発生した場合は、デバイスの左側にある明るさボタンを使って HoloLens 2 の明るさレベルを手動で調整できます。
1. ボタン 1 ~ 6 を選択すると、各カラー プロファイルを瞬時に試し、ユーザーの目に最適なプロファイルを見つける (これは通常、シーンが最もニュートラルに見え、グレースケール パターンとスキントーンが期待通りに表示されるプロファイルを意味します)。

    ![色調整シーンの表示](images/color-cal-ui.png)
    
1. 選択したプロファイルに問題が生じそうなら、[Save **& Exit] (終了) ボタンを選択** します。
1. 変更しない場合は、[Cancel & **Exit]** ボタンを選択すると、変更内容が元に戻されます。

> [!TIP]
> 表示色の調整設定を使用する場合に注意する必要があるヒントを次に示します。
> - 必要なときに、[設定] から表示色の調整を再実行できます。
> - デバイス上のユーザーが以前に設定を使用してカラー プロファイルを変更した場合、最新の変更の日付/時刻が [設定] ページに反映されます。
> - 表示色の調整を再び実行すると、以前に保存されたカラー プロファイルが強調表示され、プロファイル 0 は表示されません (プロファイル 0 はディスプレイの元のカラー プロファイルを表します)。
> - ディスプレイの元のカラー プロファイルに戻す場合は、[設定] ページから元の色プロファイルに戻します (カラー プロファイルをリセットする方法 [を参照してください](#how-to-reset-color-profile))。

#### カラー プロファイルをリセットする方法

HoloLens 2 に保存されたカスタム カラー プロファイルに問題がある場合は、デバイスの元のカラー プロファイルを復元できます。
1. 設定アプリ **を起動** し、[System > **調整] に移動します**。
1. [ **色の調整の表示] で**、[既定のカラー プロファイルに **リセット] ボタンを選択** します。
1. ディスプレイがリセットされる数秒間、ディスプレイはオフになります。 ディスプレイの電源を入れ戻した *後* も、デバイスを再起動することをお [勧めします](#top-display-color-calibration-known-issues)(既知の問題を参照)。

#### 上位表示色調整の既知の問題

- [設定] ページで、カラー プロファイルが最後に変更された日時を示す状態文字列は、[設定] ページを再読み込みするまで最新の状態に更新されません。 
    - 回避策: 別の [設定] ページを選択し、[調整] ページを再選択します。
- [既定のカラー プロファイルにリセット] ボタンをクリックすると、テキストを含むダイアログ ボックスが開きます。 ただし、ダイアログ ボックスの [リセット] ボタンは意図した動作をします。
- [リセット] ボタンを選択すると、表示が 5 ~ 10 秒間空白になる場合があります。Mixed Reality ホームで予期しない動作が発生する可能性があります。 Please restart your device after using the "Reset" button (we'll be fixing this soon to automatically restart your device and we'll update the Settings text accordingly).
- HoloLens 2 が表示色調整の実行中にスリープ状態になる場合、後で Mixed Reality ホームに戻り、ディスプレイの明るさレベルは淡色表示になります。
- デバイスの左側にある明るさボタンを数回上下に押してから、期待通りに動作する必要がある場合があります。

### 既定のアプリ ピッカー

ハイパーリンクをアクティブにするか、複数のインストール済みアプリを使ってファイルの種類を開く場合は、新しいウィンドウが開き、ファイルまたはリンクの種類を処理するインストール済みアプリを選択するように求めるメッセージが表示されます。 このウィンドウでは、選択したアプリでファイルまたはリンクの種類として "Once" または "Always" を処理することもできます。

![アプリピッカー ウィンドウ](images/default-app-picker.png)

If you choose "Always" but later want to change which app handles a particular file or link type, you can reset your saved defaults in **Settings > Apps**. ページの下部までスクロールし、[ファイルの種類**** 用の既定のアプリ] や [リンクの種類用の既定のアプリ] の下にある [クリア] ボタンを選択します。 デスクトップ PC の同様の設定とは異なり、個々のファイルの種類の既定値をリセットできます。

### Office Web アプリ

スタート Officeの [すべてのアプリ] の一覧に、新しい Web アプリが追加されました。 この Web アプリは、スタート画面にピン留めしたりアンインストールしたりすることもできます。 これは Web アプリなので、その機能はアクセスして体験した機能と正確に一致します https://www.office.com 。 Office Web アプリの機能は、HoloLens 2 にアクティブなインターネット接続がある場合にのみ使用できます。

### スワイプして入力する

一部のお客様は、入力する単語の形をスワイプすることで仮想キーボードを "入力" する方が速く見つかり、ホログラフィック キーボード用にこの機能をプレビューします。 ホログラフィック キーボードの平面を指の先端を通して一度に 1 つの単語をスワイプし、単語の形状をスワイプして、キーボードの平面から指の先端を引き出します。 単語間でキーボードから指を外して Space キーを押す必要なく、単語のフォローアップをスワイプできます。 キーボードで指が動いた後にスワイプ の証跡が表示される場合は、この機能が動作しているのが分かっています。

この機能は、(携帯電話のディスプレイとは異なり) 指に抵抗を感じないホログラフィック キーボードの性質上、使い方が難しい場合があります。 この機能は一般リリース向けとして評価されています。そのため、お客様からのフィードバックは重要です。この機能が役に立つ場合も、構築的なフィードバックがある場合も、フィードバック Hub でお知 [らせください](hololens-feedback.md)。

### USB-C 外部マイクのサポート

> [!IMPORTANT]
> USB マイクを **接続すると、自動的に入力デバイスとして設定されません**。 一連の USB-C ヘッドホンを接続すると、ユーザーはヘッドホンのオーディオが自動的にヘッドホンにリダイレクトされるのを確認しますが、HoloLens OS では、他の入力デバイスよりも内部マイク アレイの優先順位が優先されます。 **USB-C マイクを使用するには、次の手順に従います。**

ユーザーは、[サウンドの設定] パネルを使用して、USB-C に接続された外部マイク **を** 選択できます。 USB-C マイクは、通話、録音などに使用できます。

設定アプリ**を開き**、[システム サウンド]**を**  ->  **選択します**。

![サウンド設定](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> リモート アシストで外部マイクを **使用**するには、ユーザーが [サウンド デバイスの管理] ハイパーリンクをクリックする必要があります。
>
> 次に、ドロップダウンを使用して、外部マイクを **Default** または **Communications Default に設定します。** **[Default] を**選択すると、外部マイクがすべての場所で使用されます。
>
> Communications **Default を選択** すると、外部マイクはリモート アシストや他の通信アプリで使用されますが、HoloLens マイク アレイは他のタスクにも引き続き使用できます。

![サウンド デバイスを管理する](images/usbc-mic-2.png)

<br>

![マイクの既定値を設定する](images/usbc-mic-3.jpg)

#### マイクのBluetoothについて

残念Bluetoothは、HoloLens 2 では現在サポートされていません。

#### USB-C マイクのトラブルシューティング

一部の USB-C マイクは、マイクとスピーカーの両方として誤 *って報告します* 。 これは、HoloLens ではなく、マイクの問題です。 これらのマイクのいずれかを HoloLens に接続すると、サウンドが失われる可能性があります。 幸いなことに、単純な修正プログラムがあります。  

[**設定**  ->  **システム**  ->  **サウンド]** で、組み込みのスピーカー **(アナログ機能オーディオ**ドライバー) を既定のデバイスとして明示的に**設定します**。 HoloLens では、マイクを後で取り外して再接続した場合でも、この設定を記憶する必要があります。

![USB-C マイクのトラブルシューティング](images/usbc-mic-4.png)

### キオスク モードで新しい設定アプリとエッジ アプリを使用する

キオスクにアプリを含 [めた](hololens-kiosk.md)場合、IT 管理者は多くの場合、アプリをキオスクに追加しますが、アプリ ユーザー モデル ID (AUMID) を使用します。 設定アプリと Microsoft Edge アプリはどちらも新しいアプリと見なされ、それらのアプリに AUMID を使用する以前のアプリのキオスクとは異なっているので、新しい AUMID を使用するには更新する必要があります。

キオスクを変更して新しいアプリを含める場合は、新しい AUMID を追加し、古い AUMID を残することをお勧めします。 これにより、ユーザーが OS を更新するときに簡単に移行が行え、意図した方法でキオスクを使用し続ける新しいポリシーを受け取る必要がなされます。

| アプリ                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Old Settings App       | HolographicSystemSettings_cw5n1h2txyewy!App            |
| 新しい設定アプリ       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App |
| 古い Microsoft Edge アプリ | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| 新しい Microsoft Edge アプリ | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE    |

### ページ設定を表示する新しい SettingsURIs

[Windows Holographic バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2)では、Settings/PageVisibilityList ポリシーを追加して、設定アプリ内に表示されるページを制限しました。 [](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) PageVisibilityList は、IT 管理者がシステム設定アプリの特定のページを表示またはアクセスできないようにしたり、または指定されたページ以外のすべてのページで同様に行うことを許可するポリシーです。

[ページ設定の表示 []](settings-uri-list.md)にアクセスすると、この CSP を使用する手順と、以前のリリースで利用可能な URI の一覧が表示されます。

Windows Insider ビルドでは、IT 管理者が管理できる利用可能な設定 URI の一覧を拡張しています。 これらの URI の一部は、新しい設定アプリ内で新しく利用可能な領域用です。 Settings/PageVisibilityList ポリシーを使用している場合は、次の一覧を確認し、必要に応じて許可またはブロックするページを調整します。

> [!NOTE]
> **非推奨: ms-settings:network-proxy**
>
> これらの新しいビルドでは、1 つの設定ページは推奨されていません。 [インターネット**プロキシ&古いネットワーク**ネットワーク]  >  **** ページは、グローバル設定として使用できなくなりました。 新しい接続ごとのプロキシ設定は、[ネットワークとインターネット****& Wi-Fi のプロパティ] または [ネットワーク & インターネット イーサネットのプロパティ]  >  ****  >  ******で**  >  **確認**  >  **できます**。

<br>

| 設定ページ                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Apps > Apps & features                               | `ms-settings:appsfeatures`                         |
| Apps > Apps & features > Advanced options          | `ms-settings:appsfeatures-app`                     |
| オフライン > アプリ                                  | `ms-settings:maps`                                 |
| オフライン > マップとダウンロード > アプリ                  | `ms-settings:maps-downloadmaps`                    |
| デバイス>マウス                                      | `ms-settings:mouse`                                |
| USB >デバイス                                        | `ms-settings:usb`                                  |
| ネットワーク& インターネット>フライト モード                   | `ms-settings:network-airplanemode`                 |
| プライバシー >全般                                    | `ms-settings:privacy-general`                      |
| プライバシー > Ink & typing personalization             | `ms-settings:privacy-speechtyping`                 |
| プライバシー>モーション                                     | `ms-settings:privacy-motion`                       |
| プライバシー>スクリーンショットの境界線                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| プライバシー>スクリーンショットとアプリ                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| System > Battery                                     | `ms-settings:batterysaver`                         |
| System > Battery                                     | `ms-settings:batterysaver-settings`                |
| システム > サウンド                                       | `ms-settings:sound`                                |
| System > Sound > アプリのボリュームとデバイスの基本設定 | `ms-settings:apps-volume`                          |
| System > Sound > Manage sound devices              | `ms-settings:sound-devices`                        |
| System > Storage > Configure Storage Sense         | `ms-settings:storagepolicies`                      |
| Time & Language > Date & time                        | `ms-settings:dateandtime`                          |
| Time & Language > Keyboard                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| セキュリティ&の更新>回復のリセット&する               | `ms-settings:reset`                                |

#### 更新された URI

以前は、次の 2 つの URI は、示されているページにユーザーを直接移動するのではなく、メインの更新ページのみをブロックしました。 ページに移動するために、次の項目が更新されました。

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### エラーの処理に関するキオスク モードの動作の変更

以前のビルドでは、デバイスにキオスク構成 (グローバル割り当てアクセスと AAD グループ メンバーの割り当てアクセスの両方の組み合わせ) がある場合、AAD グループ メンバーシップの決定に失敗した場合、ユーザーには["スタート](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)" メニューに何も表示されません。

Windows Insider リリースから、キオスク エクスペリエンスは AAD グループ キオスク モード中に障害が発生した場合に、グローバル キオスク構成 (存在する場合) にフォールバックします。

### 設定アプリによるフォールバック診断の構成

設定アプリで、ユーザーはフォールバック診断の動作 [を構成できます](hololens-diagnostic-logs.md)。 設定アプリで、[プライバシーのトラブルシューティング **] ページ**  ->  **に移動**し、この設定を構成します。

> [!NOTE]
> デバイスに対して MDM ポリシーが構成されている場合、ユーザーはこの動作を上書きできます。  

### 近くのデバイスと情報を共有する

Pc と HoloLens Insider ビルド 20279.1006+ を実行している他の HoloLens 2 デバイスの両方を含め、Windows 10 デバイスで近いデバイスと情報を共有します。 設定システムの共有エクスペリエンスで**** 試して  ->  ****  ->  ****、HoloLens から PC にファイルや URL を共有できます。 詳しくは [、Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)で近くのデバイスと情報を共有する方法をご覧ください。

この機能は [、Connectivity/AllowConnectedDevices を使用して管理できます](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)。

### 新しい OS 更新プログラムのトラブルシューティング ツール

設定アプリ内の以前のトラブルシューティング ツールに加えて、OS 更新プログラム用の新しい設定アプリが追加された新しいトラブルシューティング ツールが追加されました。 [設定の更新**の**  ->  **セキュリティの &amp; トラブルシューティング**  ->  ****  ->  **] Windows Update に移動し、[スタート**] を選択**します**。 これにより、IT またはサポートのトラブルシューティングに役立つ、OS 更新プログラムの問題を再現しながらトレースを収集できます。

### 更新プログラムの機能強化と修正:

- [オフライン診断には、](hololens-diagnostic-logs.md#offline-diagnostics) シリアル番号と OS バージョンに関する追加のデバイス情報も含まれます。






## Insider ビルドの受信の開始

> [!NOTE]
> 最近更新していない場合は、デバイスを再起動して状態を更新し、最新のビルドを取得してください。
> - "再起動デバイス" 音声コマンドは正常に動作します。 
> - [設定] /[Windows Insider Program] で再起動ボタンを選択することもできます。
>
> 発生した可能性があるバック エンドにバグが発生しました。これにより、追跡が可能です。

HoloLens 2 デバイスで、**[設定]** > **[更新とセキュリティ]** > **[Windows Insider Program]** の順に移動し、**[開始する]** を選択します。 Windows Insider として登録するために使用したアカウントをリンクします。

Windows Insider はチャネルに移行しています。 ファスト**リング**は開発チャネル**** になり、**スロー**リングは**ベータ**チャネルになり、**リリース**プレビュー リングはリリース プレビュー**チャネルになります**。 マッピングは次のように表示されます。

![Windows Insider チャネルの説明](images/WindowsInsiderChannels.png)

詳しくは [、Windows ブログの「Windows Insider チャネル](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) の紹介」をご覧ください。

次に **、Windows のアクティブな**開発を選択し、開発者チャネルビルドまたは**** ベータ チャネル**** ビルドを受け取るかどうかを選択し、プログラムの条件を確認します。

[ **Confirm > Restart Now]** を選び、完了します。 デバイスが再起動したら、[設定] > [更新とセキュリティ] & > **更新** プログラムを確認して最新のビルドを取得します。

### 更新エラー 0x80070490回避
Dev または Beta チャネルで更新0x80070490更新エラーが発生した場合は、次の短期的な問題を回避してください。 Insider チャネルを移動し、更新プログラムを受け取り、Insider チャネルを戻します。

#### ステージ 1 - リリース プレビュー
1.  設定, 更新プログラム&セキュリティ, Windows Insider Program, select **Release Preview Channel**.
2.  設定, 更新プログラム&セキュリティ, Windows Update, **更新プログラムの確認**. 更新後、ステージ 2 に進む。

#### ステージ 2 - 開発チャネル
1. 設定, 更新&セキュリティ, Windows Insider Program, select **Dev Channel**.
2. 設定, 更新プログラム&セキュリティ, Windows Update, **更新プログラムの確認**.

## FFU のダウンロードとフラッシュの手順
フライト署名のある FFU でテストするには、フライト署名のある FFU をフラッシュする前にデバイスのフライト ロックを解除する必要があります。
1. PC の場合:

    1. Ffu を PC からダウンロードします [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. Microsoft Store から ARC (Advanced Recovery Companion) をインストールします [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 。
    
1. HoloLens で -Flight Unlock: Open **Settings**  >  **Update & Security**Windows Insider  >  **Program** then sign up, reboot device.

1. フラッシュ FFU - ARC を使用してフライト署名された FFU をフラッシュできます。

## フィードバックを提供し、問題を報告する

HoloLens で[フィードバック Hub アプリ](hololens-feedback.md)を使用してフィードバックを提供し、問題を報告することができます。 フィードバック Hub を使用すると、エンジニアが問題を迅速にデバッグして解決するのに役立つすべての必要な診断情報が含まれるようになります。  中国語および日本語版の HoloLens に関する問題は、同じ方法で報告する必要があります。

> [!NOTE]
> フィードバック Hub を使用してドキュメント フォルダーにアクセスするかどうかを確認するプロンプトに必ず同意してください (メッセージが表示されたら **[はい]** を選択します)。

## 開発者向けの注意事項

HoloLens の Insider ビルドを使用して自由にアプリケーションを開発してみることをお勧めします。  作業を始めるには、[HoloLens 開発者向けドキュメント](https://developer.microsoft.com/windows/mixed-reality/development)をご覧ください。 これらの同じ手順は HoloLens の Insider ビルドでも使用できます。  HoloLens 開発用に使用しているものと同じビルドの Unity と Visual Studio を使用できます。

## Insider ビルドの受信の停止

Windows Holographic の Insider ビルドを受け取りたくない場合は、HoloLens が製品版ビルドを実行しているときにオプトアウトすることができます。または、Advanced Recovery Companion を使用して[デバイスを回復](hololens-recovery.md)し、Windows Holographic の Insider バージョン以外にデバイスを回復することができます。

> [!CAUTION]
> 新しいプレビュー ビルドを手動で再インストールした後に Insider Preview ビルドの登録を解除すると、ブルー スクリーンが発生するという既知の問題があります。 その後、手動でデバイスを回復する必要があります。 影響を受けるかどうかの詳細については、この[既知の問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)の詳細をご覧ください。

HoloLens が製品版ビルドを実行していることを確認するには、次の操作を行います。

1. **[設定] > [システム] > [バージョン情報]** の順に移動し、ビルド番号を探します。

1. [実稼働ビルド番号のリリース ノートを参照してください](hololens-release-notes.md)。

Insider ビルドをオプトアウトするには、次の操作を行います。

1. 製品版ビルドを実行している HoloLens で、**[設定] > [更新とセキュリティ] > [Windows Insider Program]** に移動して、**[Insider Preview ビルドの停止]** を選択します。

1. 画面の指示に従って、デバイスでの受信を停止します。
