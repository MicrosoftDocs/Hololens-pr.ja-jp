---
title: Microsoft HoloLens の Insider Preview
description: Insider ビルドを開始し、HoloLens の次の主要なオペレーティング システム更新プログラムに貴重なフィードバックを提供する方法について説明します。
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
ms.date: 3/4/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 327701c2f618fc8958704cef5f174efed08fff3a
ms.sourcegitcommit: f3e35e278f7841176982b411881f2791e9600e6a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "11388782"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens の Insider Preview

HoloLens 用の最新の Insider Preview ビルドへようこそ! HoloLens [の次](hololens-insider.md#start-receiving-insider-builds) の主要なオペレーティング システム更新プログラムを開始し、貴重なフィードバックを提供する方法は簡単です。

## <a name="windows-insider-release-notes"></a>Windows Insider リリース ノート

Windows Insiders に新しい機能のフライトを再度開始するのを楽しみにしています。 新しいビルドは、最新の更新プログラムを開発チャネルに提供します。 Windows Insider ビルドにさらに機能と更新プログラムを追加する場合は、引き続きこのページを更新します。  これらの更新プログラムを現実に組み合わせ、興奮して準備を整えます。

この機能更新プログラムには、2 人の対象ユーザーの機能が含まれている。 エンド ユーザーがデバイス上の誰でも使用できる機能と、IT 管理者が構成できる新しいデバイス管理オプション。 以下の機能テーブルは、各新機能を使用できるユーザーを特定します。 IT 管理者の場合は、IT 管理者 - 更新 [チェックリストをご覧ください。](#it-admin---update-checklist)

> [!IMPORTANT]
> 以前にキオスクで設定アプリまたは Microsoft Edge アプリを使用していた場合は、これらのアプリを別のアプリ ID を使用する新しいアプリに置き換えました。 以下のキオスク モードで新しい [アプリの新しい AUMIDs を読んでお勧](#use-the-new-settings-and-edge-apps-in-kiosk-modes) めいたします。 これにより、キオスクで引き続き設定アプリを使用するか、新しい Microsoft Edge アプリを含める必要があります。

<br>

| フィーチャー名                                              | 簡単な説明                                                                      | 対象ユーザー | ビルドで使用可能 |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|------|
| [新しい Microsoft Edge](#introducing-the-new-microsoft-edge) | 新しいクロム ベースの Microsoft Edge が HoloLens 2 で利用できる                         | エンド ユーザー | 20279.1006 |
| [WebXR および 360 ビューアー](#webxr-and-360-viewer)             | イマーシブ Web エクスペリエンスと 360 ビデオ再生を試す                                           | エンド ユーザー | 20289.1000 |
| [新しい設定アプリ](#new-settings-app)                     | 従来の設定アプリは、新しい機能と設定で更新されたバージョンに置き換えられる | エンド ユーザー | 20279.1006 |
| [色の調整を表示する](#display-color-calibration)   | HoloLens 2 ディスプレイの代替カラー プロファイルを選択する                                | エンド ユーザー | 20293.1000 |
| [既定のアプリピッカー](#default-app-picker)                 | ファイルまたはリンクの種類ごとに起動するアプリを選択する                                      | エンド ユーザー | 20279.1006 |
| [アプリごとのボリューム コントロール](#per-app-volume-control) |  システム ボリュームとは独立してアプリ レベルのボリュームを制御する | エンド ユーザー | 20293.1000 |
| [Office Web アプリ](#office-web-app)                         | [すべてのアプリ] Office Web アプリへのショートカットが表示されます。                                   | エンド ユーザー | 20279.1006 |
| [スワイプして入力する](#swipe-to-type)                           | ホログラフィック キーボードで指の先端を使って単語を "スワイプ" する                        | エンド ユーザー | 20279.1006 |
| [スタート画面の [電源] メニュー](#power-menu-from-start) | [スタート] メニューで、HoloLens デバイスを再起動してシャットダウンします。 | エンド ユーザー | 20293.1000 |
| [[サインイン] 画面に表示される複数のユーザー](#multiple-users-listed-on-sign-in-screen) | [サインイン] 画面に複数のユーザー アカウントを表示する | エンド ユーザー | 20293.1000 |
| [USB-C 外部マイクのサポート](#usb-c-external-microphone-support) | アプリおよび/またはリモート アシストに USB-C マイクを使用します。| エンド ユーザー | 20279.1006 |
| [キオスクの訪問者の自動ログオン](#visitor-auto-logon-for-kiosks)                          | キオスク モードで使用する訪問者アカウントの自動ログオンを有効にします。                         | IT 管理者 | 20279.1006                 |
| [キオスク モードの新しいアプリの新しい AUMIDs](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | 新しい設定とエッジ アプリの AUMIDs | IT 管理者 | 20279.1006 |
| [キオスク モードの失敗の手渡しの改善](#kiosk-mode-behavior-changes-for-handling-of-failures) | キオスク モードでは、空のスタート メニューの前にグローバル割り当てアクセスが表示されます。 | IT 管理者 | 20279.1006 |
| [ページ設定の表示に関する新しい SettingsURIs](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | 20 以上の新しい SettingsURIs for Settings/PageVisibilityList ポリシー | IT 管理者 | 20289.1000 |
| [フォールバック診断の構成](#configuring-fallback-diagnostics-via-settings-app) | 設定アプリでのフォールバック診断動作の設定 | IT 管理者 | 20279.1006 |
| [近くのデバイスと共有する](#share-things-with-nearby-devices) | HoloLens から PC へのファイルまたは URL の共有 | すべて | 20279.1006 |
| [新しい OS Update のトラブルシューティング ツール](#new-os-update-troubleshooter) | [OS 更新プログラムの設定] の新しいトラブルシューティング ツール | IT 管理者 | 20279.1006 |
| [配信の最適化プレビュー](#delivery-optimization-preview) | 複数の HoloLens デバイスからのダウンロードの帯域幅消費量を削減する | IT 管理者 | 20301.1000 |
| [更新プログラムの改善と修正](#improvements-and-fixes-in-the-update) | 更新プログラムの追加の修正。 | すべて | 20279.1006 |

### <a name="it-admin---update-checklist"></a>IT 管理者 - 更新チェックリスト

このチェックリストは、現在のデバイス管理構成に影響を与える可能性があるこの機能更新プログラムで追加される機能、または使用を開始する可能性がある新機能を知る際に役立ちます。

#### <a name="updates-to-kiosk-mode"></a>キオスク モードへの更新

[**キオスク モードの新しいアプリの新しい AUMIDs**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

以前にキオスクで設定アプリまたは Microsoft Edge アプリを使用していた場合は、これらのアプリを別のアプリ ID を使用する新しいアプリに置き換えました。 以下のキオスク モードで新しい [アプリの新しい AUMIDs を読んでお勧](#use-the-new-settings-and-edge-apps-in-kiosk-modes) めいたします。 これにより、キオスクで引き続き設定アプリを使用するか、新しい Microsoft Edge アプリを含める必要があります。

これらの変更を今すぐ行い、すべてのデバイスに展開し、更新時の移行をスムーズに行えます。

[**キオスクの訪問者の自動ログオン**](#visitor-auto-logon-for-kiosks)

訪問者はキオスクに自動的にログインできます。 この動作は既定でオンになっていますが、管理および無効化できます。

[**キオスク モードの失敗の手渡しの改善**](#kiosk-mode-behavior-changes-for-handling-of-failures)

この更新プログラムは、キオスク モードでデバイスを制御し続け、空のキオスクを提示する前に、さまざまな種類のキオスクに戻ります。 管理できませんが、構成に適用される可能性がある方法でキオスクを使用している場合は、サポート部門に通知する必要があります。

#### <a name="updates-to-page-settings-visibility"></a>ページ設定の表示の更新

[**ページ設定の表示に関する新しい SettingsURIs**](hololens-insider.md#new-settingsuris-for-page-settings-visibility)

現在ページ設定の表示[](settings-uri-list.md)を使用している場合は、許可またはブロックされている既存の URI を調整できます。

#### <a name="updates-for-your-wdac-policy"></a>WDAC ポリシーの更新プログラム

以前に WDAC 経由で Microsoft Edge をブロックしていた場合は、WDAC ポリシーを更新する必要があります。 以下 [を確認し、](#using-wdac-to-block-new-microsoft-edge) 提供されているサンプル コードを使用してください。

#### <a name="newly-configurable-items"></a>新しく構成可能なアイテム

- [フォールバック診断の構成](#configuring-fallback-diagnostics-via-settings-app)
  - フォールバック診断を収集する場合と収集するユーザーを構成できます。
- [近くのデバイスと共有する](#share-things-with-nearby-devices)
  - 近くの新しい共有機能を無効にできます。
- [新しい Microsoft Edge のポリシー設定の構成](#configuring-policy-settings-for-the-new-microsoft-edge)
  - Microsoft Edge で使用できる新しい構成を確認します。

#### <a name="new-diagnostic-tool"></a>新しい診断ツール

- [新しい OS Update のトラブルシューティング ツール](#new-os-update-troubleshooter)
  - OS 更新プログラムに関連するログを収集する

### <a name="introducing-the-new-microsoft-edge"></a>新しい Microsoft Edge の導入

![従来の Microsoft Edge ロゴから新しい Microsoft Edge ロゴへのアニメーション](images/new-edge.gif)

新しい Microsoft Edge では、 [クロム](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) オープンソース プロジェクトを採用して、お客様との互換性を向上し、Web 開発者向けの Web の断片化を少なくしています。

この Insider プレビューを使用すると、新しい Microsoft Edge が HoloLens 2 のお客様に初めて利用できます。 新しい Microsoft Edge は最終的に HoloLens 2 の従来の Microsoft Edge に置き換わるが、両方のブラウザーは現在 Insiders で利用できます。 フィードバックとバグは、新しい Microsoft **** Edge のフィードバック送信機能またはフィードバック ハブ経由でチームと[共有してください](hololens-feedback.md)。

![Microsoft Edge の新しいスクリーンショット](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>新しい Microsoft Edge の起動

Insiders には、新しい Microsoft Edge の新しい Microsoft Edge アイコン (青と緑の旋回アイコンで表される) と従来の Microsoft Edge (白い ![ "e" アイコンで表される) の 2 つのバージョンがあります ](images/new_edge_logo.png) 。 新しい Microsoft Edge は [スタート] メニューにピン留めされ、Web リンクをアクティブ化すると自動的に起動します。 従来の Microsoft Edge を既定の Web ブラウザーとして使用する場合は、既定のアプリをリセットする手順を参照 [してください](#default-app-picker)。

> [!NOTE]
> HoloLens 2 で新しい Microsoft Edge を初めて起動すると、設定とデータは従来の Microsoft Edge からインポートされます。 新しい Microsoft Edge を起動した後も従来の Microsoft Edge を使用し続ける場合、その新しいデータは従来の Microsoft Edge から新しい Microsoft Edge に同期されません。

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>新しい Microsoft Edge のポリシー設定の構成

新しい Microsoft Edge では、IT 管理者は、従来の Microsoft Edge で以前よりも HoloLens 2 のブラウザー ポリシーのセットがはるかに広く提供されています。

新しい Microsoft Edge のポリシー設定の管理の詳細については、次の参考資料を参照してください。

- [Microsoft Intune を使って Microsoft Edge ポリシー設定を構成する](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Microsoft Edge Legacy から Microsoft Edge ポリシーへのマッピング](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome から Microsoft Edge ポリシーへのマッピング](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- [Microsoft Edge Enterprise の完全なドキュメント](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> 新しい Microsoft Edge でサポートされるブラウザー ポリシーの量が多いので、新しい各ポリシーが HoloLens 2 で動作する保証をチームが行う必要があります。 ただし、HoloLens 2 で以前サポートされた各従来の Microsoft Edge ポリシーと同等の新しい Microsoft Edge よりもテストと確認が期待通り機能しています。 HoloLens 2 で使用していた従来の各 Microsoft Edge ブラウザー ポリシーに相当する新しい Microsoft Edge ポリシーを見つけるには [、「Microsoft](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) Edge Legacy to Microsoft Edge ポリシー マッピング」を参照してください。
>
> HoloLens 2 では動作しないという新** しい Microsoft Edge ポリシーが少なくとも 2 つあります。
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>HoloLens 2 の新しい Microsoft Edge に期待する機能

新しい Microsoft Edge は、新しい UWP アダプター層を持つネイティブ Win32 アプリなので、HoloLens 2 のような UWP 専用デバイスで実行できる場合があります。一部の機能はすぐには利用できない場合があります。 今後数か月間、新しいシナリオと機能をサポートしますので、この領域で最新の情報を確認してください。

**動作が予想されるシナリオと機能:**
- 初回実行エクスペリエンス、プロファイルへのサインイン、同期
- Web サイトは、期待どおりにレンダリングおよび動作する必要があります。
- ほとんどのブラウザー機能 (お気に入り、履歴など) は期待通りに動作する必要があります
- 濃色モード
- デバイスへの Web アプリのインストール
- 拡張機能のインストール (HoloLens 2 で正しく動作しない拡張機能を使用している場合は、お知らせください)
- PDF の表示とマーキング
- 1 つのブラウザー ウィンドウからの空間サウンド
- ブラウザーの自動および手動更新
- [印刷] メニューから PDF を保存する ([PDF に保存] オプションを使用)
- WebXR および 360 ビューアー拡張機能
- 環境内に配置された複数のウィンドウ間で参照する場合に、正しいウィンドウにコンテンツを復元する

**予期しないシナリオと機能:**
- 複数のウィンドウからの空間サウンドと同時オーディオ ストリーム
- "見て、言う"
- 印刷

**既知のブラウザーの上位の問題:**
- デバイスをリセットすると、新しい Microsoft Edge が削除されます
- ホログラフィック キーボードの拡大鏡のプレビューに正しくないコンテンツが表示される
- スクロールが時として吃音を引き出す場合があります
- Microsoft Store アプリの Web リンクがブラウザーを起動しない場合があります
- 以前に別のブラウザー ウィンドウからオーディオを再生した場合、間違ったブラウザー ウィンドウからオーディオが再生される可能性があります。

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider チャネル

Microsoft Edge チームは、Beta、Dev、Canary の 3 つのプレビュー チャネルを Edge Insider コミュニティで利用できます。 プレビュー チャネルをインストールしても、HoloLens 2 にリリースされたバージョンの Microsoft Edge はアンインストールされません。同時に複数のチャネルをインストールできます。 

エッジ インサイ [ダー コミュニティの詳細については、Microsoft Edge Insider](https://www.microsoftedgeinsider.com) のホームページをご覧ください。 さまざまな Edge Insider チャネルの詳細と開始方法については、「Edge Insider ダウンロード ページ [」を参照してください](https://www.microsoftedgeinsider.com/download)。

HoloLens 2 に Microsoft Edge Insider チャネルをインストールするには、次の 2 つの方法があります。

**デバイスへの直接インストール (現在は管理されていないデバイスでのみ使用可能)**
  1. HoloLens 2 で、Edge Insider ダウンロード [ページにアクセスします](https://www.microsoftedgeinsider.com/download)。
  1. インストールする **エッジ Insider チャネルの [HoloLens 2** のダウンロード] ボタンを選択します。
  1. ダウンロードした .msix ファイルをエッジ ダウンロード キューまたはデバイスの [ダウンロード] フォルダー (エクスプローラーを使用) から起動します。
  1. [アプリ インストーラーが](app-deploy-app-installer.md) 起動します。
  1. [インストール] **ボタンを選択** します。
  1. インストールが成功すると、[スタート] メニューの [すべてのアプリ] リストに Microsoft Edge **** Beta、Dev、または Canary が個別のエントリとして表示されます。

**Windows デバイス ポータルを使用して[](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)PC 経由でインストールする (HoloLens 2 で開発者モードを有効にする必要があります)**
  1. PC で、Edge Insider ダウンロード [ページにアクセスします](https://www.microsoftedgeinsider.com/download)。
  1. インストールする **エッジ Insider チャネル** の [Windows 10 用ダウンロード] ボタンの横にあるドロップダウン矢印ボタンを選択します。
  1. ドロップダウン **メニューで [HoloLens 2]** を選択します。
  1. .msix ファイルを PC の "ダウンロード" フォルダー (または簡単に見つけることができます別のフォルダー) に保存します。
  1. [PC で Windows デバイス ポータル](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)を使用して、ダウンロードした .msix ファイルを HoloLens 2 にインストールします。
  1. インストールが成功すると、[スタート] メニューの [すべてのアプリ] リストに Microsoft Edge **** Beta、Dev、または Canary が個別のエントリとして表示されます。

> [!NOTE]
> HoloLens 2 のこの Windows Insider プレビューでは、デバイス上の Microsoft Edge のバージョンが、Microsoft Edge Insider チャネルの一部 (またはすべて) で利用可能なバージョンよりも高くなる場合があります。 これは、HoloLens 2 の Web ブラウザーを対象とする新機能と修正プログラムが、可能な限り迅速に Windows Insiders にアクセスするための方法です。 次の Windows 更新プログラムの公開リリース直後に、Microsoft Edge Insider チャネルのビルドは HoloLens 2 の Microsoft Edge のバージョンを上回り、先に進む予定です。

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>WDAC を使用して新しい Microsoft Edge をブロックする

WDAC ポリシーを更新して新しい[](windows-defender-application-control-wdac.md)Microsoft Edge アプリをブロックする IT 管理者向けには、ポリシーに次の項目を追加する必要があります。

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

### <a name="webxr-and-360-viewer"></a>WebXR および 360 ビューアー

*Windows Insider ビルド 20289.1000 に追加されました*

新しい Microsoft Edge には、没入型 Web エクスペリエンスを作成するための新しい標準 (WebVR の置き換え) である WebXR のサポートが含まれています。 多くのイマーシブ Web エクスペリエンスは、VR を念頭に置いて設計されました (視野を仮想環境に置き換えます)、これらのエクスペリエンスは HoloLens 2 でもサポートされています。 WebXR 標準では、物理環境を使用する拡張現実と複合現実のイマーシブ Web エクスペリエンスも有効になります。 開発者が WebXR に多くの時間を費やすと、HoloLens 2 のお客様が試す新しい拡張現実と複合現実のイマーシブ エクスペリエンスが到着すると予想しています。

360 ビューアー拡張機能は WebXR 上に構築され、HoloLens 2 の新しい Microsoft Edge と共に自動的にインストールされます。 この Web 拡張機能を使用すると、360 度のビデオに没頭できます。 YouTube では、360 のビデオの中で最も大きな選択を提供しています。

#### <a name="how-to-use-webxr"></a>WebXR の使い方

1. WebXR がサポートされている Web サイトに移動します。
1. Web サイトの **[VR の入力** ] ボタンを選択します。 このボタンの場所と視覚的表現は Web サイトごとに異なる場合がありますが、次のような場合があります。

    ![ENTER VR ボタンの例](images/75px-enter-vr.png)

1. 特定のドメインで WebXR エクスペリエンスを初めて起動しようとすると、ブラウザーはイマーシブ ビューに入る同意を求め、「許可」を **選択します**。
1. [HoloLens 2 ジェスチャを使用して](hololens2-basic-usage.md#the-hand-tracking-frame)エクスペリエンスを操作します。
1. エクスペリエンスに [終了] ボタン**** が付かない場合は[、Start ジェスチャを使用して](hololens2-basic-usage.md#start-gesture)戻ります。

**推奨される WebXR サンプル**
- 360 Viewer (次のセクションを参照)
- [XR 恐竜](https://www.xrdinosaurs.com/)
- [バリスタ エクスプレス](https://constructarca.de/game/barista-express/)
- [WebXR ペイント](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>360 ビューアーの使い方

1. YouTube の 360 度ビデオに移動します。
1. ビデオ フレームで、複合現実ヘッドセット ボタンを選択します。

    ![360 ビューアーをアクティブにするボタン](images/enter-360-viewer.jpg)

1. 特定のドメインで 360 ビューアーを初めて起動しようとすると、ブラウザーはイマーシブ ビューに入る同意を求めます。 [許可 **] を選択します**。
1. [エア タップ](hololens2-basic-usage.md#select-using-air-tap) で再生コントロールを表示します。 手 [線とエア](hololens2-basic-usage.md#select-using-air-tap) タップを使用して、再生/一時停止、前方/背面のスキップ、キャプションのオン/オフの切り替え、エクスペリエンスの停止 (イマーシブ ビューを終了) を行います。 再生コントロールは、数秒の非アクティブ状態の後に消えます。

#### <a name="top-webxr-and-360-viewer-known-issues"></a>WebXR と 360 ビューアーの既知の問題
- WebXR エクスペリエンスでは、頭を傾けるか、環境の周りを移動するときにホログラムがシフトまたは傾く場合があります。
- WebXR エクスペリエンスの複雑さによっては、フレームレートが低下したり、吃音が発生したりする場合があります。
- 連結された手の関節は、WebXR ではまだ使用できません。
- WebXR または 360 ビューアー エクスペリエンスを終了する場合、複合現実ホーム内のホログラムが再表示するには 30 秒以上かかる場合があります。
- YouTube 以外の Web サイトから 360 のビデオが期待通り動作しない場合があります。
- 360 ビデオがイマーシブ ビューに入らない場合 (または複合現実ヘッドセット ボタンが表示されない) 場合は、ページを更新してみてください。
- HoloLens 2 の 360 ビューアーでは、キャプションはまだ表示されません。
- 360 ビューアーでビデオを一時停止すると、ビデオのレンダリングが停止します (ただし、再生ボタンを正しく選択すると、再生が再開されます)。
- 360 ビューアーの [次のビデオ] ボタンは現在機能しません。
- 2D ビデオはイマーシブな "シアター" モードで再生できますが、フレームレートは 30 fps 未満になります。

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>WebXR と 360 ビューアーに関するフィードバックの提供

新しい Microsoft Edge のフィードバックの**** 送信機能を使用して、フィードバックとバグをチームと共有してください。

### <a name="new-settings-app"></a>新しい設定アプリ

このリリースでは、新しいバージョンの設定アプリを導入しています。 新しい設定アプリには、サウンド、Power & スリープ、ネットワーク & インターネット、アプリ、アカウント、簡単操作など、HoloLens 2 の新機能と拡張された設定が含まれています。

> [!NOTE]
> 新しい設定アプリは従来の設定アプリとは異なるので、以前環境の周りに配置した設定ウィンドウは更新時に削除されます。

![新しい設定アプリのホームページ](images/new-settings-app.png)

**新機能と設定**
- 設定検索: キーワードまたは設定の名前を使用して設定ホームページから設定を検索します。
- システム >サウンド:
  - 入力および出力オーディオ デバイス: 入力および出力オーディオ デバイスを個別に選択します (たとえば、Bluetooth ヘッドフォンを介してオーディオを聴く、またはオーディオ入力に USB-C マイクを使用する)。
    > [!NOTE]
    > Bluetoothは HoloLens 2 ではサポートされていません。
  - アプリのボリューム: 各アプリの音量を個別に調整します。 アプリ [ごとのボリューム コントロールを参照してください](#per-app-volume-control)。
- システム >電源&スリープ状態: デバイスが非アクティブな期間後にスリープ状態に入る時期を選択します。
- System >バッテリー: バッテリー セーバー モードを手動で有効にするか、バッテリー セーバー モードが自動的に有効になる時点でバッテリーのしきい値を設定します。
- USB >デバイス: 既定で USB 接続を無効にできます。
- ネットワーク &インターネット:
  - USB-C イーサネット アダプターは、ネットワーク ネットワーク およびインターネット&されます。
  - IP アドレスを含む USB-C イーサネット アダプターの設定が利用可能になります。
  - HoloLens 2 で機内モードを有効にできます。
- アプリ: ファイルとリンクの種類に使用される既定のアプリをリセットできます。 詳細については、「既定のアプリ [ピッカー」を参照してください](#default-app-picker)。
- 他>アカウント: デバイス所有者は、ユーザーの追加、標準ユーザーのデバイス所有者へのアップグレード、デバイス所有者の標準ユーザーへのダウングレード、ユーザーの削除を行います。
- 簡単操作: テキストサイズと視覚効果を変更します。

**既知の問題**
- 以前に配置した [設定] ウィンドウは削除されます (上記の注意を参照)。
- イーサネット ページには、仮想イーサネット デバイス ("UsbNcm") が表示されます (調査中)。 この仮想イーサネット デバイスは、デバイスセットアップの [ネットワーク] ページにも表示されますが、無視できます (調査中)。
- 設定アプリを使用してデバイスの名前を変更できなくなりました (IT 管理者はプロビジョニング パッケージまたは MDM を使用してデバイスの名前を変更できます)。
- 新しい Microsoft Edge のバッテリー使用量は、UWP アダプター層でサポートされる Win32 デスクトップ アプリケーションとしての性質上、正確ではない場合があります (すぐには修正されません)。

### <a name="display-color-calibration"></a>色の調整を表示する

*Windows Insider ビルド 20293.1000 に追加されました*

この新しい設定では、HoloLens 2 ディスプレイの代替カラー プロファイルを選択できます。 これは、特にディスプレイの明るさのレベルが低い場合に、色の表示精度が向上する場合があります。 色の調整の表示は、[設定] アプリの [システムの調整] ページ>確認できます。

> [!NOTE]
> この設定は新しいカラー プロファイルをディスプレイ ファームウェアに保存しますので、デバイスごとの設定です (各ユーザー アカウントに固有ではありません)。

#### <a name="how-to-use-display-color-calibration"></a>表示色調整の使い方

1. 設定アプリ **を起動** し **、[System >調整] に移動します**。
1. [ **色の調整の表示]** で、[表示色の **調整を実行する] ボタンを選択** します。
1. 表示色の調整エクスペリエンスが起動し、バイザーが正しい位置にあるか確認してください。
1. 指示ダイアログ ボックスに進むと、ディスプレイが自動的に明るさ 30% に淡色表示されます。
    > [!TIP]
    > 環境で淡色表示のシーンが表示される場合は、デバイスの左側にある明るさボタンを使用して HoloLens 2 の明るさレベルを手動で調整できます。
1. ボタン 1 ~ 6 を選択すると、各カラー プロファイルを即座に試し、目に見栄えの良い色を見つける (これは通常、シーンが最もニュートラルに見えるプロファイルを意味し、グレースケール パターンとスキン トーンは期待通りになります)。

    ![色調整シーンの表示](images/color-cal-ui.png)
    
1. 選択したプロファイルに満足している場合は、[終了] ボタンをクリック& **選択** します。
1. 変更しない場合は、[終了] ボタンを****&を選択すると、変更が元に戻されます

> [!TIP]
> 表示色調整の設定を使用する場合に注意する役立つヒントを次に示します。
> - 必要なときにいつでも [設定] から表示色の調整を再実行できます。
> - デバイス上のユーザーが以前に設定を使用してカラー プロファイルを変更した場合、最新の変更の日付/時刻が [設定] ページに反映されます。
> - 表示色の調整を再実行すると、以前に保存されたカラー プロファイルが強調表示され、プロファイル 0 は表示されません (プロファイル 0 はディスプレイの元のカラー プロファイルを表します)。
> - ディスプレイの元のカラー プロファイルに戻す場合は、[設定] ページから行います (「カラー プロファイルをリセットする方法」[を参照)。](#how-to-reset-color-profile)

#### <a name="how-to-reset-color-profile"></a>カラー プロファイルをリセットする方法

HoloLens 2 に保存されたカスタム カラー プロファイルに不満がある場合は、デバイスの元のカラー プロファイルを復元できます。
1. 設定アプリ **を起動** し **、[System >調整] に移動します**。
1. [ **色の調整の表示]** で、[既定のカラー **プロファイルにリセット] ボタンを選択** します。
1. ダイアログ ボックスが開いたら、[ **再起動** ] を選択します。HoloLens 2 を再起動して変更を適用する準備ができている場合。

#### <a name="top-display-color-calibration-known-issues"></a>トップディスプレイの色の調整に関する既知の問題

- [設定] ページで、カラー プロファイルが最後に変更された日時を示す状態文字列は、[設定] のページを再読み込みするまで、最新の状態になります。 
    - 回避策: 別の [設定] ページを選択し、[調整] ページを再選択します。
- HoloLens 2 が表示色調整の実行中にスリープ状態になる場合、後で複合現実ホームに戻り、ディスプレイの明るさレベルは引き続き淡色表示されます。
- デバイスの左側にある明るさボタンを何度か上下に押してから、期待通りに動作する必要がある場合があります。
- ローカリゼーションがすべての市場で完了しているとは言え

### <a name="default-app-picker"></a>既定のアプリピッカー

ハイパーリンクをアクティブ化するか、複数のインストール済みアプリを含むファイルの種類を開く場合、ファイルまたはリンクの種類を処理するインストール済みアプリを選択するように求める新しいウィンドウが開きます。 このウィンドウでは、選択したアプリでファイルまたはリンクの種類 "Once" または "Always" を処理することもできます。

![アプリピッカー ウィンドウ](images/default-app-picker.png)

[常に] を選択した後で、特定のファイルまたはリンクの種類を処理するアプリを変更する場合は、[アプリの設定] で保存した既定値を> **できます**。 ページの下部までスクロールし、[ファイルの種類**** の既定のアプリ] または [リンクの種類の既定のアプリ] の下にある [クリア] ボタンを選択します。 デスクトップ PC の同様の設定とは異なり、個々のファイルの種類の既定値をリセットできない。

### <a name="per-app-volume-control"></a>アプリごとのボリューム コントロール

この Windows Insider ビルドでは、ユーザーは各アプリのボリューム レベルを手動で調整できます。 これにより、ユーザーは必要なアプリに集中したり、複数のアプリを使用する場合に聞き取りが良くなります。 別のアプリでリモートアシスタンスのために別のユーザーを呼び出している間に、あるアプリの音量を下にする必要があるなどです。

個々のアプリの音量を設定するには、[設定****] [システム サウンド] に移動し、[高度なサウンド オプション] で [アプリの音量とデバイスの基本設定  ->  ****  ->  ******] を選択します**。

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

### <a name="office-web-app"></a>Office Web アプリ

[Office] メニューの [すべてのアプリ] リストに Web アプリが追加されました。 この Web アプリは、スタート画面またはアンインストール画面にピン留めすることもできます。 これは Web アプリなので、その機能は、訪れたユーザーが体験した機能と完全に一致します https://www.office.com 。 Office Web アプリの機能は、HoloLens 2 がアクティブなインターネット接続を持つ場合にのみ使用できます。

**既知の問題**
- デバイスをリセットすると、Web アプリOffice削除されます

### <a name="swipe-to-type"></a>スワイプして入力する

一部のユーザーは、入力する単語の図形をスワイプして仮想キーボードを "入力" する方が速く見つかり、ホログラフィック キーボード用にこの機能をプレビューしています。 ホログラフィック キーボードの平面を指の先端を通過し、単語の図形をスワイプし、キーボードの平面から指の先端を引き出して、一度に 1 つの単語をスワイプできます。 単語間でキーボードから指を削除することで、スペース バーを押す必要なく、単語のフォローアップをスワイプできます。 キーボードで指の動きに従ってスワイプ の軌跡が表示される場合は、機能が機能しているのが分かっています。

この機能は、(携帯電話のディスプレイとは異なり) 指に対する抵抗を感じないホログラフィック キーボードの性質上、使い方やマスターが難しい場合があります。 この機能はパブリック リリース用に評価するため、フィードバックは重要です。機能が役に立つかどうか、または建設的なフィードバックがある場合は、フィードバック ハブからお知 [らせください](hololens-feedback.md)。

### <a name="power-menu-from-start"></a>スタート画面の [電源] メニュー

ユーザーがデバイスをサインアウト、シャットダウン、再起動できる新しいメニュー。 HoloLens の [スタート] 画面のインジケーターで、システム更新プログラムが利用可能なときに表示されます。

#### <a name="how-to-use"></a>使用方法

1. Start ジェスチャを使用して HoloLens の [スタート] 画面 [を開](hololens2-basic-usage.md#start-gesture) きます。または"Go to Start" と入力します。

2. ユーザー プロファイル画像の横にある省略記号アイコン (....) に注意してください。

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. 自分の手または音声コマンド "Power" を使用してユーザー プロファイル画像を選択します。

4. [サインアウト]、[再起動]、または [デバイスのシャットダウン] のオプションを含むメニューが表示されます。

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. HoloLens をサインアウト、再起動、またはシャットダウンするメニュー オプションを選択します。 デバイスが単一の Microsoft アカウント (MSA) またはローカル アカウントに設定されている場合は、[サインアウト] オプション [を使用できない場合があります](hololens-identity.md)。

6. メニューを閉じるには、他の場所をタッチするか、[スタート] メニューを [スタート] ジェスチャで閉じる必要があります。

#### <a name="update-indicator"></a>更新インジケーター

更新プログラムが使用可能な場合は、省略記号アイコンが点灯して、再起動によって更新プログラムがインストールされます。更新プログラムの存在を反映するようにメニュー オプションも変更されます。<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>[サインイン] 画面に表示される複数のユーザー

以前は、[サインイン] 画面には、最近サインインしたユーザーと'その他のユーザー' エントリ ポイントだけが表示されました。 複数のユーザーがデバイスにサインインしている場合、これでは十分ではないという顧客からのフィードバックを受け取っています。 ユーザー名などを再入力する必要が生じていました。

この Windows Insider ビルドで導入された、PIN 入力フィールドの右側にある [その他のユーザー] を選択すると、[サインイン] 画面に、以前にデバイスにサインインしている複数のユーザーが表示されます。 **** これにより、ユーザーは自分のユーザー プロファイルを選択し、Windows Hello 資格情報を使用してサインインできます。 [アカウントの追加] ボタンを使用して、この [その他のユーザー] ページから新しいユーザー **をデバイスに追加** することもできます。

[その他のユーザー] メニューで[その他のユーザー] ボタンをクリックすると、デバイスにサインインした最後のユーザーが表示されます。 このボタンを選択すると、このユーザーの [サインイン] 画面に戻ります。

![サインイン画面の既定](./images/multiusers1.jpg)

<br>

![サインイン画面他のユーザー](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C 外部マイクのサポート

> [!IMPORTANT]
> USB マイクを **接続すると、入力デバイスとして自動的に設定されません**。 一連の USB-C ヘッドホンを接続すると、ユーザーはヘッドホンのオーディオが自動的にヘッドホンにリダイレクトされるのを確認しますが、HoloLens OS は内部マイク アレイを他の入力デバイスよりも優先します。 **USB-C マイクを使用するには、次の手順に従います。**

ユーザーは、[サウンド設定] パネルを使用して USB-C 接続の外部マイク **を** 選択できます。 USB-C マイクは、通話、録音などに使用できます。

[設定]**アプリを開**き、[システム サウンド]**を**  >  **選択します**。

![サウンド設定](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> リモート アシストで外部マイクを **使用するには**、ユーザーが [サウンド デバイスの管理] ハイパーリンクをクリックする必要があります。
>
> 次に、ドロップダウンを使用して外部マイクを [既定] または [通信の**既定値]****に設定します。** [既定] **を選択** すると、外部マイクはどこでも使用されます。
>
> [ **通信の既定]** を選択すると、外部マイクはリモート アシストや他の通信アプリで使用されますが、HoloLens マイク配列は他のタスクでも使用できます。

![サウンド デバイスの管理](images/usbc-mic-2.png)

<br>

![マイクの既定の設定](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>マイクのサポートBluetoothについて

残念Bluetooth、HoloLens 2 では現在まだマイクがサポートされていません。

#### <a name="troubleshooting-usb-c-microphones"></a>USB-C マイクのトラブルシューティング

一部の USB-C マイクは、マイクとスピーカーの両方として誤って報告される点 *に* 注意してください。 これは、HoloLens ではなく、マイクの問題です。 これらのマイクの 1 つを HoloLens に接続すると、サウンドが失われる可能性があります。 幸いなことに、簡単な修正があります。  

[**設定**  ->  **システム**  ->  **サウンド]** で、組み込みのスピーカー **(アナログ機能オーディオ**ドライバー) を既定のデバイスとして明示的**に設定します**。 HoloLens は、マイクが削除され、後で再接続された場合でも、この設定を覚えておく必要があります。

![USB-C マイクのトラブルシューティング](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>キオスクの訪問者の自動ログオン

この新機能により、訪問者アカウントの自動ログオンをキオスク モードで使用できます。

AAD 以外の構成の場合、訪問者の自動ログオン用にデバイスを構成するには、次の手順を実行します。

1. 次のプロビジョニング パッケージを作成します。
    1. 訪問者アカウント **を許可するランタイム設定/AssignedAccess** を構成します。
    1. 必要に応じて、デバイスを MDM **(ランタイム設定/Workplace/Enrollments)** に登録して、後で管理できるようにします。
    1. ローカル アカウントを作成しない
1. [プロビジョニング パッケージを適用します](hololens-provisioning.md)。

AAD 構成の場合、ユーザーは、この変更を行わずに、今日のような機能を実現できます。 キオスク モード用に構成された AAD 参加デバイスは、サインイン画面から 1 つのボタン タップでビジター アカウントにサインインできます。 訪問者アカウントにサインインすると、訪問者がスタート メニューから明示的にサインアウトするか、デバイスが再起動されるまで、デバイスは再びサインインを求めるメッセージを表示しません。

訪問者の自動ログオンは、カスタム [OMA-URI ポリシーを使用して管理](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) できます。

- URI 値: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| ポリシー  | 説明   | 構成  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | キオスクへの訪問者の自動ログオンを許可する   | 1 (はい)、0 (いいえ、既定値)。  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>キオスク モードで新しい設定アプリとエッジ アプリを使用する

キオスクにアプリを含 [めた](hololens-kiosk.md)場合、IT 管理者はアプリをキオスクに追加しますが、アプリ ユーザー モデル ID (AUMID) を使用します。 設定アプリと Microsoft Edge アプリの両方が新しいアプリと見なされ、それらのアプリに AUMID を使用する古いアプリキオスクとは異なるので、新しい AUMID を使用するには更新する必要があります。

キオスクを変更して新しいアプリを含める場合は、新しい AUMID に追加し、古いアプリを残することをお勧めします。 これにより、ユーザーが OS を更新するときに簡単に移行し、キオスクを意図した通り使用し続ける新しいポリシーを受け取る必要がなされます。

| アプリ                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| 古い設定アプリ       | HolographicSystemSettings_cw5n1h2txyewy!アプリ            |
| 新しい設定アプリ       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!アプリ |
| 古い Microsoft Edge アプリ | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| 新しい Microsoft Edge アプリ | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>失敗の処理に関するキオスク モードの動作の変更

以前のビルドでは、デバイスにキオスク構成 (グローバル割り当てアクセスと AAD グループ メンバーの割り当てアクセスの両方の組み合わせ) がある場合、AAD グループ メンバーシップが失敗したと判断すると、ユーザーは "スタート画面に何も表示[されません"](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)メニューが表示されます。

Windows Insider リリースから、キオスク エクスペリエンスは AAD グループ キオスク モード中に障害が発生した場合にグローバル キオスク構成 (存在する場合) にフォールバックします。

### <a name="new-settingsuris-for-page-settings-visibility"></a>ページ設定の表示に関する新しい SettingsURIs

[Windows Holographic バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2)では、Settings/PageVisibilityList ポリシーを追加して、設定アプリ内に表示されるページを制限しました。 [](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) PageVisibilityList は、IT 管理者がシステム設定アプリの特定のページを表示またはアクセスできないようにしたり、または指定されたページ以外のすべてのページで同様に行うことを許可するポリシーです。

[ページ設定の [表示] にアクセスすると](settings-uri-list.md)、この CSP を使用する手順と、以前のリリースで使用できる URI の一覧を確認できます。

Windows Insider ビルドでは、IT 管理者が管理できる利用可能な設定 URI の一覧を拡張しています。 これらの URI の一部は、新しい設定アプリ内で新しく利用可能な領域用です。 Settings/PageVisibilityList ポリシーを使用している場合は、次の一覧を確認し、必要に応じて許可またはブロックされたページを調整します。

> [!NOTE]
> **非推奨: ms-settings:network-proxy**
>
> これらの新しいビルドでは、1 つの設定ページが非推奨です。 [インターネット**プロキシ] &古い [ネットワーク**  >  ****] ページは、グローバル設定として使用できなくなりました。 新しい接続ごとのプロキシ設定は、[ネットワーク ネットワーク] または [インターネット **&**  >  **Wi-Fi**プロパティ] または [ネットワーク & イーサネット プロパティ] の  >  ******下**に  >  **表示**  >  **されます**。

<br>

| 設定ページ                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| アプリ>アプリ&機能                               | `ms-settings:appsfeatures`                         |
| アプリ > アプリ &高度な>機能          | `ms-settings:appsfeatures-app`                     |
| オフライン >アプリ                                  | `ms-settings:maps`                                 |
| アプリ > オフライン マップ > ダウンロード マップ                  | `ms-settings:maps-downloadmaps`                    |
| デバイス > マウス                                      | `ms-settings:mouse`                                |
| USB >デバイス                                        | `ms-settings:usb`                                  |
| ネットワーク & インターネット >機内モード                   | `ms-settings:network-airplanemode`                 |
| プライバシー >全般                                    | `ms-settings:privacy-general`                      |
| プライバシー > Ink &入力の個人用設定             | `ms-settings:privacy-speechtyping`                 |
| プライバシー > Motion                                     | `ms-settings:privacy-motion`                       |
| プライバシー>スクリーンショットの境界線                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| プライバシー>スクリーンショットとアプリ                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| System > バッテリー                                     | `ms-settings:batterysaver`                         |
| System > バッテリー                                     | `ms-settings:batterysaver-settings`                |
| System > サウンド                                       | `ms-settings:sound`                                |
| System > サウンド >とデバイスの基本設定 | `ms-settings:apps-volume`                          |
| System > サウンド > サウンド デバイスの管理              | `ms-settings:sound-devices`                        |
| System > ストレージ >構成ストレージ センス         | `ms-settings:storagepolicies`                      |
| 時間 & 言語 > 日付 &時刻                        | `ms-settings:dateandtime`                          |
| タイム & 言語 > キーボード                           | `ms-settings:keyboard`                             |
| 言語&時間>言語                           | `ms-settings:language`                             |
| 言語&時間>言語                           | `ms-settings:regionlanguage-languageoptions`       |
| 更新& セキュリティ >回復&する               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>更新された URI

以前は、次の 2 つの URI は、指定されたページにユーザーを直接移動するのではなく、メインの更新ページのみをブロックしました。 ページに移動するために、次のアイテムが更新されました。

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>設定アプリによるフォールバック診断の構成

設定アプリで、ユーザーはフォールバック診断の動作 [を構成できます](hololens-diagnostic-logs.md)。 [設定] アプリで 、[プライバシーの**トラブルシューティング]**  ->  **ページに移動**して、この設定を構成します。

> [!NOTE]
> デバイスに対して構成されている MDM ポリシーがある場合、ユーザーは、その動作を上書きできます。  

### <a name="share-things-with-nearby-devices"></a>近くのデバイスと共有する

HoloLens Insider ビルド 20279.1006+を実行している PC と他の HoloLens 2 デバイスの両方を含む、Windows 10 デバイスによって近いデバイスと共有します。 「Settings System Shared ****  ->  ****  ->  **Experiences」** で試して、HoloLens から PC にファイルまたは URL を共有できます。 詳細については [、「Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)で近くのデバイスと共有する方法」を参照してください。

この機能は [Connectivity/AllowConnectedDevices を介して管理できます](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)。

### <a name="new-os-update-troubleshooter"></a>新しい OS Update のトラブルシューティング ツール

設定アプリ内の以前のトラブルシューティングツールに加えて、新しいトラブルシューティングツールが追加され、OS 更新プログラム用の新しい設定アプリが追加されました。 [設定更新**プログラム**  ->  **のセキュリティ &amp; のトラブルシューティング**] Windows Update に  >  ****  >  **移動し、[スタート**] を**選択します**。 これにより、OS 更新プログラムで問題を再現しながらトレースを収集し、IT またはサポートのトラブルシューティングを支援できます。

### <a name="delivery-optimization-preview"></a>配信の最適化プレビュー

この HoloLens Insider 更新プログラムを使用すると、Windows Holographic for Business を使用すると、配信の最適化設定を早期にプレビューして、複数の HoloLens デバイスからのダウンロードの帯域幅消費を削減できます。 推奨されるネットワーク構成と共に、この機能の詳細な説明については [、「Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)更新プログラムの配信の最適化」を参照してください。

次の設定は、管理画面の一部として有効にされ [、Intune から構成できます](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)。

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

このプレビュー機能に関するいくつかの注意点:

- HoloLens のサポートは、このプレビューでは OS の更新プログラムにのみ制限されます。
- Windows Holographic for Business は、Microsoft Connected Cache エンドポイントからの HTTP ダウンロード モードとダウンロード [のみをサポートします](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)。現時点では、HoloLens デバイスではピアツーピアのダウンロード モードとグループ割り当てはサポートされていません。
- HoloLens は、エンドポイントの展開または配信の最適化Windows Server Update Servicesサポートされていません。
- トラブルシューティングには、接続キャッシュ サーバー上の診断か、HoloLens の HoloLens のトレースを設定**** 更新プログラム & セキュリティ トラブルシューティング Windows Update 経由で収集する必要  >  ****  >   ****  >   **があります**。

### <a name="improvements-and-fixes-in-the-update"></a>更新プログラムの改善と修正:

- [オフライン診断には、](hololens-diagnostic-logs.md#offline-diagnostics) シリアル番号と OS バージョンの追加のデバイス情報も含まれます。






## <a name="start-receiving-insider-builds"></a>Insider ビルドの受信の開始

> [!NOTE]
> 最近更新していない場合は、デバイスを再起動して状態を更新し、最新のビルドを取得してください。
> - "デバイスの再起動" 音声コマンドが正常に動作します。 
> - [設定]/[Windows Insider Program]で再起動ボタンを選択することもできます。
>
> バック エンドで発生した可能性があるバグが発生し、これにより、トラックに戻る可能性があります。

HoloLens 2 デバイスで、**[設定]** > **[更新とセキュリティ]** > **[Windows Insider Program]** の順に移動し、**[開始する]** を選択します。 Windows Insider として登録するために使用したアカウントをリンクします。

Windows Insider がチャネルに移行中です。 Fast**リング**は開発チャネル**** になり、低速リング**** は**ベータ**チャネルになり、リリース プレビュー**** リングはリリース プレビュー チャネル**になります**。 マッピングの外観を次に示します。

![Windows Insider Channels の説明](images/WindowsInsiderChannels.png)

詳細については [、「Windows ブログでの Windows Insider チャネル](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) の導入」を参照してください。

次に **、[Windows のアクティブな**開発] を選択し、開発チャネル**** ビルドまたはベータ**** チャネル ビルドを受け取るかどうかを選択し、プログラムの用語を確認します。

[今 **すぐ再起動>確認する] を選択して** 終了します。 デバイスが再起動したら、[設定] >[セキュリティ&更新> **更新** プログラムを確認して最新のビルドを取得する] に移動します。

### <a name="update-error-0x80070490-work-around"></a>更新エラー 0x80070490回避
Dev または Beta チャネルで更新0x80070490更新エラーが発生した場合は、次の短期的な問題を回避してください。 インサイダー チャネルの移動、更新プログラムのピックアップ、Insider チャネルの移動が含まれる。

#### <a name="stage-one---release-preview"></a>ステージ 1 - リリース プレビュー
1.  設定、 Update & セキュリティ、 Windows Insider Program、 [リリース **プレビュー チャネル] を選択します**。
2.  設定, 更新プログラム&セキュリティ, Windows Update, **更新プログラムの確認**. 更新後、ステージ 2 に進む。

#### <a name="stage-two---dev-channel"></a>ステージ 2 - 開発チャネル
1. 設定、 セキュリティ&更新、 Windows Insider Program、 [開発チャネル] **を選択します**。
2. 設定, 更新プログラム&セキュリティ, Windows Update, **更新プログラムの確認**.

## <a name="ffu-download-and-flash-directions"></a>FFU のダウンロードとフラッシュの手順
フライト署名のある FFU でテストするには、フライト署名のある FFU をフラッシュする前にデバイスのフライト ロックを解除する必要があります。
1. PC の場合:

    1. から ffu を PC にダウンロードします [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. Microsoft Store から ARC (Advanced Recovery Companion) をインストール [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) します。
    
1. HoloLens - Flight Unlock: Open **Settings**Update & Windows Insider Program その後サインアップ  >  ****  >  **** し、デバイスを再起動します。

1. Flash FFU - ARC を使用してフライト署名済み FFU をフラッシュできます。

## <a name="provide-feedback-and-report-issues"></a>フィードバックを提供し、問題を報告する

HoloLens で[フィードバック Hub アプリ](hololens-feedback.md)を使用してフィードバックを提供し、問題を報告することができます。 フィードバック Hub を使用すると、エンジニアが問題を迅速にデバッグして解決するのに役立つすべての必要な診断情報が含まれるようになります。  中国語および日本語版の HoloLens に関する問題は、同じ方法で報告する必要があります。

> [!NOTE]
> フィードバック Hub を使用してドキュメント フォルダーにアクセスするかどうかを確認するプロンプトに必ず同意してください (メッセージが表示されたら **[はい]** を選択します)。

## <a name="note-for-developers"></a>開発者向けの注意事項

HoloLens の Insider ビルドを使用して自由にアプリケーションを開発してみることをお勧めします。  作業を始めるには、[HoloLens 開発者向けドキュメント](https://developer.microsoft.com/windows/mixed-reality/development)をご覧ください。 これらの同じ手順は HoloLens の Insider ビルドでも使用できます。  HoloLens 開発用に使用しているものと同じビルドの Unity と Visual Studio を使用できます。

## <a name="stop-receiving-insider-builds"></a>Insider ビルドの受信の停止

Windows Holographic の Insider ビルドを受け取りたくない場合は、HoloLens が製品版ビルドを実行しているときにオプトアウトすることができます。または、Advanced Recovery Companion を使用して[デバイスを回復](hololens-recovery.md)し、Windows Holographic の Insider バージョン以外にデバイスを回復することができます。

> [!CAUTION]
> 新しいプレビュー ビルドを手動で再インストールした後に Insider Preview ビルドの登録を解除すると、ブルー スクリーンが発生するという既知の問題があります。 その後、手動でデバイスを回復する必要があります。 影響を受けるかどうかの詳細については、この[既知の問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)の詳細をご覧ください。

HoloLens が製品版ビルドを実行していることを確認するには、次の操作を行います。

1. **[設定] > [システム] > [バージョン情報]** の順に移動し、ビルド番号を探します。

1. [実稼働ビルド番号については、リリース ノートを参照してください](hololens-release-notes.md)。

Insider ビルドをオプトアウトするには、次の操作を行います。

1. 製品版ビルドを実行している HoloLens で、**[設定] > [更新とセキュリティ] > [Windows Insider Program]** に移動して、**[Insider Preview ビルドの停止]** を選択します。

1. 画面の指示に従って、デバイスでの受信を停止します。
