---
title: Microsoft HoloLens の Insider Preview
description: 次の主要なオペレーティングシステム更新プログラム (HoloLens) について、Insider ビルドの使用を開始し、貴重なフィードバックを提供する方法について説明します。
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
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: ebd3992458daa94726e73742b1fba4d7fa97a48b
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309604"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens の Insider Preview

HoloLens 用の最新の Insider Preview ビルドへようこそ。 この機能は簡単に [開始](hololens-insider.md#start-receiving-insider-builds) でき、HoloLens の次の主なオペレーティングシステムの更新に関する貴重なフィードバックを提供します。

## <a name="windows-insider-release-notes"></a>Windows Insider リリースノート

Windows Insider の新機能を再び開始します。 新しいビルドは、最新の更新プログラムの開発チャネルにフライトされます。 Windows Insider ビルドに機能と更新プログラムを追加すると、このページは引き続き更新されます。  これらの更新プログラムを実際のものに混在させることができます。

この機能更新プログラムには、2つの対象ユーザーのための機能が含まれています。 エンドユーザーによってデバイス上のすべてのユーザーが使用できる機能と、IT 管理者が構成できる新しいデバイス管理オプション。 以下の機能テーブルでは、各新機能を使用できるユーザーについて説明しています。 IT 管理者の場合は、 [it 管理者の更新チェックリスト](#it-admin---update-checklist)を参照してください。

> [!IMPORTANT]
> キオスクで設定アプリまたは Microsoft Edge アプリを以前に使用していた場合、これらのアプリは別のアプリ ID を使用する新しいアプリに置き換えられました。 以下 [のキオスクモードで新しいアプリの新しい AUMIDs](#use-the-new-settings-and-edge-apps-in-kiosk-modes) を読むことを強くお勧めします。 これにより、キオスクの設定アプリを引き続き使用するか、新しい Microsoft Edge アプリを含めることができます。

<br>

| 機能名                                              | 簡単な説明                                                                      | 対象読者 | ビルドで使用可能 |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|------|
| [新しい Microsoft Edge](#introducing-the-new-microsoft-edge) | 新しい Chromium ベースの Microsoft Edge が HoloLens 2 で利用可能になりました                         | エンド ユーザー | 20279.1006 |
| [WebXR と360ビューアー](#webxr-and-360-viewer)             | イマーシブ web エクスペリエンスと360ビデオ再生を試す                                           | エンド ユーザー | 20289.1000 |
| [新しい設定アプリ](#new-settings-app)                     | レガシ設定アプリは、新しい機能と設定を使用して、更新されたバージョンに置き換えられています | エンド ユーザー | 20279.1006 |
| [色の調整を表示する](#display-color-calibration)   | HoloLens 2 ディスプレイの代替カラープロファイルを選択します                                | エンド ユーザー | 20293.1000 |
| [既定のアプリピッカー](#default-app-picker)                 | ファイルまたはリンクの種類ごとに起動するアプリを選択する                                      | エンド ユーザー | 20279.1006 |
| [アプリごとのボリューム制御](#per-app-volume-control) |  システムボリュームとは独立してアプリレベルボリュームを制御する | エンド ユーザー | 20293.1000 |
| [Office web アプリ](#office-web-app)                         | Office web アプリへのショートカットが [すべてのアプリ] に表示されるようになりました。                                   | エンド ユーザー | 20279.1006 |
| [スワイプして入力します](#swipe-to-type)                           | 指の先端を使用して、holographic キーボードで単語を "スワイプ" します。                        | エンド ユーザー | 20279.1006 |
| [[スタート] の [電源] メニュー](#power-menu-from-start) | [スタート] メニューで、[HoloLens デバイス] を再起動してシャットダウンします。 | エンド ユーザー | 20293.1000 |
| [サインイン画面に複数のユーザーが表示される](#multiple-users-listed-on-sign-in-screen) | サインイン画面に複数のユーザーアカウントを表示する | エンド ユーザー | 20293.1000 |
| [USB-C 外部マイクのサポート](#usb-c-external-microphone-support) | アプリやリモートアシスタンスで USB C マイクを使用します。| エンド ユーザー | 20279.1006 |
| [キオスクのビジター自動ログオン](#visitor-auto-logon-for-kiosks)                          | ビジターアカウントの自動ログオンをキオスクモードで使用できるようにします。                         | IT 管理者 | 20279.1006                 |
| [キオスクモードでの新しいアプリの新しい AUMIDs](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | 新しい設定と Edge アプリの AUMIDs | IT 管理者 | 20279.1006 |
| [キオスクモードのエラー処理の改善](#kiosk-mode-behavior-changes-for-handling-of-failures) | キオスクモードでは、空のスタートメニューの前に、グローバルに割り当てられたアクセスを検索します。 | IT 管理者 | 20279.1006 |
| [新しい Settingは、ページ設定の可視性を示します](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | 20 + 新しい Settingの設定/PageVisibilityList ポリシー | IT 管理者 | 20289.1000 |
| [フォールバック診断の構成](#configuring-fallback-diagnostics-via-settings-app) | 設定アプリでフォールバック診断動作を設定しています | IT 管理者 | 20279.1006 |
| [近くのデバイスとの共有](#share-things-with-nearby-devices) | HoloLens から PC にファイルまたは Url を共有する | すべて | 20279.1006 |
| [新しい OS 更新のトラブルシューティング](#new-os-update-troubleshooter) | OS の更新の設定の新しいトラブルシューティング | IT 管理者 | 20279.1006 |
| [配信の最適化のプレビュー](#delivery-optimization-preview) | 複数の HoloLens デバイスからのダウンロードの帯域幅の消費を削減する | IT 管理者 | 20301.1000 |
| [更新プログラムの機能強化と修正](#improvements-and-fixes-in-the-update) | 更新プログラムの追加の修正。 | すべて | 20279.1006 |

### <a name="it-admin---update-checklist"></a>IT 管理者-更新プログラムのチェックリスト

このチェックリストは、現在のデバイス管理構成に影響を与える可能性がある、この機能更新プログラムに追加される新しい項目、または使用を開始する新機能を理解するのに役立ちます。

#### <a name="updates-to-kiosk-mode"></a>キオスクモードの更新プログラム

[**キオスクモードでの新しいアプリの新しい AUMIDs**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

キオスクで設定アプリまたは Microsoft Edge アプリを以前に使用していた場合、これらのアプリは別のアプリ ID を使用する新しいアプリに置き換えられました。 以下 [のキオスクモードで新しいアプリの新しい AUMIDs](#use-the-new-settings-and-edge-apps-in-kiosk-modes) を読むことを強くお勧めします。 これにより、キオスクの設定アプリを引き続き使用するか、新しい Microsoft Edge アプリを含めることができます。

これらの変更は、今すぐ実行し、すべてのデバイスに展開して、更新をスムーズに移行できるようにすることができます。

[**キオスクのビジター自動ログオン**](#visitor-auto-logon-for-kiosks)

訪問者がキオスクに自動的にログインできるようになりました。 この動作は既定で有効になっていますが、管理と無効化を行うことができます。

[**キオスクモードのエラー処理の改善**](#kiosk-mode-behavior-changes-for-handling-of-failures)

サインインしている AAD ユーザーの AAD グループメンバーシップが正常に決定されていない場合、[スタート] メニュー (存在する場合) にはグローバルキオスク構成が使用されます。それ以外の場合、ユーザーには空の [スタート] メニューが表示されます。 空の [スタート] メニューは、直接設定できる構成ではありませんが、キオスクを使用している場合は、この新しい処理によってサポート部門に通知されることがあります。これは、構成に適用される可能性があります。また、割り当てられているアクセス構成に新しい調整を加える必要があります。

#### <a name="updates-to-page-settings-visibility"></a>ページ設定の表示に対する更新

[**新しい Settingは、ページ設定の可視性を示します**](hololens-insider.md#new-settingsuris-for-page-settings-visibility)

現在、 [ページ設定の可視性](settings-uri-list.md) を使用している場合は、許可またはブロックされている既存の uri に対して調整を行うことができます。

#### <a name="updates-for-your-wdac-policy"></a>WDAC ポリシーの更新

以前に WDAC 経由で Microsoft Edge をブロックしていた場合は、WDAC ポリシーを更新する必要があります。 [次の内容を確認](#using-wdac-to-block-new-microsoft-edge)し、提供されているサンプルコードを使用してください。

#### <a name="enable-new-endpoints-for-edge"></a>エッジの新しいエンドポイントを有効にする

プロキシやファイアウォールなどのネットワークエンドポイントを構成するインフラストラクチャがある場合は、[新しい Microsoft Edge アプリに対してこれらの新しいエンドポイントを有効に](#managing-endpoints-for-the-new-microsoft-edge)してください。

#### <a name="newly-configurable-items"></a>新しく構成可能な項目

- [フォールバック診断の構成](#configuring-fallback-diagnostics-via-settings-app)
  - フォールバック診断を収集できるかどうかを構成できます。
- [近くのデバイスとの共有](#share-things-with-nearby-devices)
  - 隣接する新しい共有機能を無効にすることができます。
- [新しい Microsoft Edge のポリシー設定を構成する](#configuring-policy-settings-for-the-new-microsoft-edge)
  - Microsoft Edge で利用可能な新しくなった構成を確認します。

#### <a name="new-diagnostic-tool"></a>新しい診断ツール

- [新しい OS 更新のトラブルシューティング](#new-os-update-troubleshooter)
  - OS 更新プログラムに関連するログの収集

### <a name="introducing-the-new-microsoft-edge"></a>新しい Microsoft Edge の紹介

![従来の Microsoft Edge ロゴのアニメーションを新しい Microsoft Edge ロゴに](images/new-edge.gif)

新しい Microsoft Edge は、 [Chromium オープンソースプロジェクトを採用](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) して、お客様の互換性を高め、web 開発者のために web の断片化を減らすことができます。

この Insider preview では、初めて新しい Microsoft Edge が HoloLens 2 のお客様に提供されます。 新しい Microsoft Edge は、最終的には HoloLens 2 のレガシ Microsoft Edge を置き換えますが、現在は、両方のブラウザーを内部関係者が利用できます。 新しい Microsoft Edge または [フィードバックハブ](hololens-feedback.md)を使用してフィードバックの **送信** 機能を使用して、フィードバックとバグをチームと共有してください。

![新しい Microsoft Edge スクリーンショット](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>新しい Microsoft Edge を起動しています

Microsoft Edge には、新しい microsoft edge ![ 新しい Microsoft edge アイコン ](images/new_edge_logo.png) (青と緑の渦巻きアイコンで表されます) と従来の microsoft edge (白の "e" アイコンで表される) の2つのバージョンがあります。 新しい Microsoft Edge がスタートメニューにピン留めされ、web リンクをアクティブ化すると自動的に起動します。 既定の web ブラウザーとして従来の Microsoft Edge を使用するように戻すには、次の手順を参照して [既定のアプリをリセット](#default-app-picker)します。

> [!NOTE]
> HoloLens 2 で新しい Microsoft Edge を初めて起動すると、設定とデータが従来の Microsoft Edge からインポートされます。 新しい Microsoft Edge を起動した後も従来の Microsoft Edge を引き続き使用する場合、新しいデータは従来の Microsoft Edge から新しい Microsoft Edge には同期されません。

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>新しい Microsoft Edge のポリシー設定を構成する

新しい Microsoft Edge により、IT 管理者は、以前の Microsoft Edge で使用されていたものよりもはるかに幅広いブラウザーポリシーを HoloLens 2 で提供できます。

新しい Microsoft Edge のポリシー設定の管理の詳細については、次のリソースを参照してください。

- [Microsoft Intune を使用して Microsoft Edge ポリシー設定を構成する](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Microsoft Edge レガシから Microsoft Edge ポリシーへのマッピング](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome から Microsoft Edge ポリシーへのマッピング](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- [Microsoft Edge Enterprise](https://docs.microsoft.com/deployedge/)の完全なドキュメント

> [!IMPORTANT]
> 新しい Microsoft Edge でサポートされているブラウザーポリシーの数が原因で、チームは新しいポリシーが HoloLens 2 で動作することを保証できません。 ただし、以前に HoloLens 2 でサポートされていた各レガシ Microsoft Edge ポリシーに相当する、新しい Microsoft Edge が想定どおりに動作することをテストし、確認しました。 HoloLens 2 で使用していた各レガシ Microsoft Edge ブラウザーポリシーに相当する新しい Microsoft Edge を見つけるには、「microsoft edge [Legacy To Microsoft edge ポリシーマッピング](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) 」を参照してください。
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

**ブラウザーに関する既知の問題:**
- Wi-Fi プロキシ構成は、個々の Wi-Fi 接続を対象とするプロキシポリシーであり、現在は新しい Microsoft Edge では動作しません。 OS の更新プログラムが公開される前に、この問題のブロックを解除するために積極的に取り組んでいます。
- Holographic キーボードの拡大鏡プレビューが、新しい Microsoft Edge で無効になっています。 拡大率が正常に機能したら、今後の更新プログラムでこの機能を再度有効にすることをお勧めします。
- 日本語キーボードの2文字は、新しい Microsoft Edge では正しく機能しません。 この問題は根本原因であり、まもなく修正する必要があります。
- Microsoft Store アプリ内の Web リンクがブラウザーを起動しない場合がある
- 別のブラウザーウィンドウが開いてアクティブになっている場合、音声が間違ったブラウザーウィンドウから再生されることがあります。 この問題を回避するには、オーディオの再生が想定されていない他のアクティブウィンドウを閉じます。
- "フォローする" [モード](hololens2-basic-usage.md#follow-me-stop-following)でブラウザーウィンドウからオーディオを再生するときに、"フォローする" モードを無効にすると、オーディオの再生が続行されます。 この問題を回避するには、"フォローする" モードを無効にする前にオーディオの再生を停止するか、[ **X** ] ボタンを使用してウィンドウを閉じます。
- アクティブな Microsoft Edge ウィンドウとの対話によって、他の2D アプリウィンドウが予期せず非アクティブになる場合があります。 これらのウィンドウは、もう一度操作して再アクティブ化できます。
- 別のアプリから、または Pdf などの特定の種類のドキュメントから web リンクを開くと、ブラウザーで2番目の空のタブが開きます (web リンクまたはファイルリンクの内容で作成された新しいタブに加えて)。 この問題を回避するには、追加の空白のタブを閉じます。

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider チャンネル

Microsoft Edge チームは、Edge Insider community (ベータ、Dev、およびカナリア) で3つのプレビューチャネルを利用できるようにします。 プレビューチャネルをインストールしても、HoloLens 2 でリリースされたバージョンの Microsoft Edge はアンインストールされません。また、複数のを同時にインストールすることもできます。 

エッジ Insider コミュニティの詳細については、 [Microsoft Edge insider ホームページ](https://www.microsoftedgeinsider.com) を参照してください。 さまざまなエッジ Insider チャンネルの詳細を確認し、開始するには、 [Edge insider ダウンロードページ](https://www.microsoftedgeinsider.com/download)にアクセスしてください。

HoloLens 2 に Microsoft Edge Insider channel をインストールするには、次の2つの方法があります。

**デバイスへの直接インストール (現時点では管理されていないデバイスでのみ利用可能)**
  1. HoloLens 2 で、 [Edge Insider ダウンロードページ](https://www.microsoftedgeinsider.com/download)にアクセスします。
  1. インストールする Edge Insider channel の [ **HoloLens 2 のダウンロード** ] ボタンを選択します。
  1. ダウンロードした msix ファイルをエッジダウンロードキューから起動するか、デバイスの "ダウンロード" フォルダー (エクスプローラーを使用) から起動します。
  1. [アプリのインストーラー](app-deploy-app-installer.md) が起動します。
  1. **[インストール]** ボタンを選択します。
  1. インストールが正常に完了したら、[スタート] メニューの [ **すべてのアプリ** ] の一覧に、別のエントリとして Microsoft Edge Beta、Dev、またはカナリアが表示されます。

**Windows デバイスポータルを使用して PC 経由でインストールする (HoloLens 2 で [開発者モード](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) が有効になっている必要があります)**
  1. PC で、 [Edge Insider ダウンロードページ](https://www.microsoftedgeinsider.com/download)にアクセスします。
  1. インストールする Edge Insider channel の [Windows 10 用ダウンロード] ボタンの横に **あるドロップダウン矢印ボタン** を選択します。
  1. ドロップダウンメニューで [ **HoloLens 2** ] を選択します。
  1. Msix ファイルを PC の "ダウンロード" フォルダー (または簡単に見つけられる別のフォルダー) に保存します。
  1. PC で [Windows デバイスポータル](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) を使用して、HoloLens 2 にダウンロードした msix ファイルをインストールします。
  1. インストールが正常に完了したら、[スタート] メニューの [ **すべてのアプリ** ] の一覧に、別のエントリとして Microsoft Edge Beta、Dev、またはカナリアが表示されます。

> [!NOTE]
> HoloLens 2 用のこの Windows Insider preview では、デバイス上の Microsoft Edge のバージョンが、Microsoft Edge Insider channel の一部 (またはすべて) で利用できるバージョンよりも高くなる可能性があります。 これは、HoloLens 2 で web ブラウザーを特に対象とした新機能と修正プログラムが、Windows Insider にできるだけ迅速に到達するようにするためです。 Microsoft Edge Insider channel のビルドは、次の Windows update の公開リリースの直後に、HoloLens 2 の Microsoft Edge のバージョンを上回るようになります。

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>WDAC を使用して新しい Microsoft Edge をブロックする

IT 管理者が、新しい Microsoft Edge アプリをブロックするために、 [WDAC ポリシー](windows-defender-application-control-wdac.md) を更新することを検討している場合は、ポリシーに次のものを追加する必要があります。

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>新しい Microsoft Edge のエンドポイントを管理する

環境によっては、考慮として考慮する必要があるネットワークの制限がある場合があります。 新しいエッジでスムーズにエクスペリエンスを確保するには、[これらの Microsoft エンドポイントを有効に](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)してください。

HoloLens で現在使用できる [エンドポイント](hololens-offline.md)の詳細については、こちらを参照してください。

### <a name="webxr-and-360-viewer"></a>WebXR と360ビューアー

*Windows Insider build 20289.1000 で追加されました*

新しい Microsoft Edge には、WebXR のサポートが含まれています。これは、イマーシブ web エクスペリエンスを作成するための新しい標準です (WebVR を置き換えます)。 多くのイマーシブ web エクスペリエンスは、VR を念頭に置いて設計されています (ビューのフィールドは仮想環境に置き換わるものです) が、これらのエクスペリエンスは HoloLens 2 でもサポートされています。 また、WebXR standard では、物理環境を使用する、拡張された、mixed reality のイマーシブ web エクスペリエンスが可能になります。 開発者が WebXR を使用してより多くの時間を費やしている場合、HoloLens 2 のお客様には、新たに強化された、mixed reality が登場することを想定しています。

360 Viewer 拡張機能は WebXR 上に構築されており、新しい Microsoft Edge と共に HoloLens 2 に自動的にインストールされます。 この web 拡張機能を使用すると、360度のビデオで自分自身をこちらすることができます。 YouTube では、最大で360のビデオが選択されているので、ここから始めることをお勧めします。

#### <a name="how-to-use-webxr"></a>WebXR の使用方法

1. WebXR のサポートがある web サイトに移動します。
1. Web サイトの [ **Enter** ] をクリックします。 このボタンの位置と視覚表現は、web サイトごとに異なりますが、次のようになります。

    ![「VR ボタンの例」と入力します。](images/75px-enter-vr.png)

1. 特定のドメインで WebXR experience を初めて起動しようとすると、ブラウザーでは、イマーシブビューの入力に同意するように求めるメッセージが表示されます。 [ **許可**] を選択します。
1. [HoloLens 2 のジェスチャ](hololens2-basic-usage.md#the-hand-tracking-frame)を使用して、エクスペリエンスを操作します。
1. エクスペリエンスに [ **終了** ] ボタンがない場合は、 [開始ジェスチャ](hololens2-basic-usage.md#start-gesture) を使用してホームを返します。

**推奨される WebXR サンプル**
- 360ビューアー (次のセクションを参照)
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
- WebXR または360ビューアーのエクスペリエンスを終了する場合、mixed reality ホームのホログラムが再び表示されるまでに30秒以上かかることがあります。
- 360 YouTube 以外の web サイトからのビデオが想定どおりに動作しないことがあります。
- 360 Viewer on HoloLens 2 では、キャプションが現在無効になっています。 今後の更新では、この機能を有効にする予定です。
- 360ビューアーでビデオを一時停止すると、ビデオがレンダリングされなくなります (ただし、再生ボタンを選択すると再生が正しく再開されます)。
- 360ビューアーの [次のビデオ] ボタンは、現在は機能していません。
- "シアター" モードでは、2D ビデオを再生できますが、フレームレートは 30 fps 未満になることがあります。

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>WebXR と360ビューアーに関するフィードバックの提供

新しい Microsoft Edge の **フィードバックの送信** 機能を使用して、フィードバックとバグをチームと共有してください。

### <a name="new-settings-app"></a>新しい設定アプリ

今回のリリースでは、設定アプリの新しいバージョンが導入されています。 新しい設定アプリには、次の領域における HoloLens 2 の新機能と拡張設定が含まれています。サウンド、電源 & スリープ、ネットワーク & インターネット、アプリ、アカウント、使いやすさなどです。

> [!NOTE]
> 新しい設定アプリはレガシ設定アプリとは別であるため、以前に環境に配置した設定ウィンドウはすべて更新時に削除されます。

![新しい設定アプリのホームページ](images/new-settings-app.png)

**新機能と設定**
- 設定の検索: キーワードまたは設定の名前を使用して、設定のホームページから設定を検索します。
- システム > サウンド:
  - 入力および出力オーディオデバイス: 入力および出力オーディオデバイスを個別に選択します (たとえば、Bluetooth ヘッドホンを使用してオーディオをリッスンするか、オーディオ入力に USB C マイクを使用します)。
    > [!NOTE]
    > Bluetooth マイクは HoloLens 2 ではサポートされていません。
  - アプリボリューム: 各アプリのボリュームを個別に調整します。 「 [アプリごとのボリューム制御](#per-app-volume-control)」を参照してください。
- [システム > 電源 & スリープ]: 非アクティブな状態が一定時間続いた後にデバイスをスリープ状態にするかどうかを選択します。
- システム > バッテリ: バッテリ節約モードを手動で有効にするか、バッテリ省モードが自動的にオンになるようにバッテリのしきい値を設定します。
- デバイス > USB: 既定で USB 接続を無効にすることができます。
- ネットワーク & インターネット:
  - USB-C イーサネットアダプターがネットワーク & インターネットに表示されるようになりました。
  - USB-C イーサネットアダプターの設定が、IP アドレスを含めて使用できるようになりました。
  - HoloLens 2 で機内モードを有効にできるようになりました。
- アプリ: ファイルとリンクの種類に使用される既定のアプリをリセットできます。 詳細については、「 [既定のアプリピッカー](#default-app-picker)」を参照してください。
- 他のユーザー > アカウント: デバイス所有者は、ユーザーを追加し、標準ユーザーをデバイス所有者にアップグレードし、デバイス所有者を標準ユーザーにダウングレードして、ユーザーを削除することができます。
- コンピューターの簡単操作: テキストのサイズと視覚効果を変更します。

**既知の問題**
- 以前に配置した設定ウィンドウが削除されます (上のメモを参照してください)。
- 設定アプリでデバイスの名前を変更することはできなくなりました。 IT 管理者は、HoloLens 2 デバイス名テンプレートまたは MDM [Devdetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/dnscomputername ノードの[Windows 自動操縦](https://docs.microsoft.com/hololens/hololens2-autopilot)を使用して、デバイスの名前を変更できます。
- イーサネットのページには、常に仮想イーサネットデバイス ("UsbNcm") が表示されます。
- 新しい Microsoft Edge のバッテリ使用量は、UWP アダプターレイヤーによってサポートされる Win32 デスクトップアプリケーションの性質上、正確ではない可能性があります (近日中に修正が予定されていません)。

### <a name="display-color-calibration"></a>色の調整を表示する

*Windows Insider build 20293.1000 で追加されました*

この新しい設定で、HoloLens 2 ディスプレイの代替カラープロファイルを選択できます。 これにより、特にディスプレイの明るさが低いレベルで、色が正確に表示される場合があります。 ディスプレイの色の調整は、設定アプリの [システム > の調整] ページで確認できます。

> [!NOTE]
> この設定により、ディスプレイファームウェアに新しいカラープロファイルが保存されるため、デバイスごとの設定になります (各ユーザーアカウントに固有ではありません)。

#### <a name="how-to-use-display-color-calibration"></a>画面の色の調整を使用する方法

1. **設定** アプリを起動し、[**システム > の調整**] に移動します。
1. [ **ディスプレイの色の調整**] で、[ **画面の色の調整を実行** する] ボタンを選択します。
1. ディスプレイのカラー調整エクスペリエンスが起動し、バイザーが正しい位置にあることを確認することをお勧めします。
1. 指示のダイアログボックスが表示された後、画面は自動的にグレーで30% の明るさになります。
    > [!TIP]
    > 環境に淡色表示されているシーンが表示されない場合は、デバイスの左側にある [明るさ] ボタンを使用して、HoloLens 2 の輝度レベルを手動で調整できます。
1. ボタン1-6 を選択すると、各カラープロファイルが瞬時に表示され、最もよく見られるものを見つけることができます (これは通常、シーンを最もニュートラルにするのに役立つプロファイルで、グレースケールパターンとスキントーンが予想どおりに見えることを意味します)。

    ![色の調整シーンを表示する](images/color-cal-ui.png)
    
1. 選択したプロファイルに問題がなければ、[ **& の終了** ] ボタンをクリックします。
1. 変更しない場合は、[ **キャンセル & 終了** ] ボタンを選択すると、変更が元に戻されます。

> [!TIP]
> ディスプレイの色の調整設定を使用する際に留意すべき便利なヒントを次に示します。
> - 好みに応じて、設定から表示色の調整を再実行できます。
> - デバイス上のすべてのユーザーが以前にカラープロファイルを変更する設定を使用していた場合、最新の変更の日付/時刻が [設定] ページに反映されます。
> - 画面の色の調整を再実行すると、以前に保存されたカラープロファイルが強調表示され、プロファイル0は表示されません (プロファイル0はディスプレイの元のカラープロファイルを表します)
> - ディスプレイの元のカラープロファイルに戻す場合は、[設定] ページから変更できます (「 [カラープロファイルをリセットする方法](#how-to-reset-color-profile)」を参照してください)。

#### <a name="how-to-reset-color-profile"></a>カラープロファイルをリセットする方法

HoloLens 2 に保存されているカスタムカラープロファイルに満足できない場合は、デバイスの元のカラープロファイルを復元できます。
1. **設定** アプリを起動し、[**システム > の調整**] に移動します。
1. [ **色の調整の表示**] で、[ **既定のカラープロファイルにリセット** ] ボタンを選択します。
1. ダイアログボックスが開いたら、HoloLens 2 を再起動して変更を適用する準備ができたら、[ **再起動** ] を選択します。

#### <a name="top-display-color-calibration-known-issues"></a>画面の色の調整に関する既知の問題

- [設定] ページには、カラープロファイルが最後に変更された日時が表示されます。この文字列は、設定のページを再読み込みするまで最新の状態ではありません。
    - 回避策: 別の設定ページを選択し、[調整] ページを再選択します。

### <a name="default-app-picker"></a>既定のアプリピッカー

ハイパーリンクをアクティブ化するか、複数のインストール済みアプリでファイルの種類を開くと、そのファイルまたはリンクの種類を処理するインストール済みアプリを選択するよう求めるメッセージが表示されます。 このウィンドウでは、選択したアプリがファイルまたはリンクの種類を "Once" または "Always" として処理するように選択することもできます。

![アプリの選択ウィンドウ](images/default-app-picker.png)

"Always" を選択した後、特定のファイルまたはリンクの種類を処理するアプリを変更する場合は、[ **設定 > アプリ**] で保存した既定値をリセットできます。 ページの一番下までスクロールし、[ファイルの種類の既定のアプリ] または [リンクの種類の既定のアプリ] の下にある [ **クリア** ] ボタンを選択します。 デスクトップ Pc の同様の設定とは異なり、個々のファイルの種類の既定値をリセットすることはできません。

### <a name="per-app-volume-control"></a>アプリごとのボリューム制御

この Windows Insider build では、ユーザーは各アプリのボリュームレベルを手動で調整できます。 これにより、ユーザーは、必要なアプリに集中することができます。また、複数のアプリを使用する場合は、より適切に聞くことができます。 たとえば、あるアプリのボリュームを別のユーザーが別のユーザーに呼び出している間に、別のユーザーを呼び出す必要がある場合などです。

個々のアプリのボリュームを設定するには、[**設定**]  ->  [**システム**  ->  **サウンド**] に移動し、[サウンドの詳細オプション] で [**アプリのボリュームとデバイスの設定**] を選択します。

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

### <a name="office-web-app"></a>Office web アプリ

>[!NOTE]
>Windows Insider build 20325.1000 の時点では、Office web アプリはプレインストールされなくなりました (今後のリリースの OS 更新プログラムにはプレインストールされません)。 Office web アプリをインストールするには、にアクセス https://www.office.com して、[ **アプリで利用可能** ] または [ **office のインストール** ] ボタンをアドレスバーにクリックします。 [ **インストール** ] を選択して確認します。

Office web アプリが、[スタート] メニューの [すべてのアプリ] の一覧に追加されました。 この web アプリは、開始またはアンインストールにピン留めすることもできます。 これは web アプリであるため、この機能は、アクセスしたときに表示されるものと完全に一致 https://www.office.com します。 Office web アプリの機能は、HoloLens 2 にアクティブなインターネット接続がある場合にのみ使用できます。

**既知の問題**
- デバイスをリセットすると、Office web アプリが削除されます

### <a name="swipe-to-type"></a>スワイプして入力します

お客様によっては、入力しようとしている単語の形状をスワイプすることで仮想キーボードの "種類" を短縮し、holographic キーボードのこの機能をプレビューしています。 Holographic キーボードのプレーンで指の先端を渡し、単語の形状をスワイプして、キーボードの平面から指の先端を取り出すことで、一度に1つの単語をスワイプできます。 単語の間でキーボードから指を削除することによって、スペースバーを押すことなくフォローアップ語をスワイプできます。 キーボードの指の動きの後にスワイプの軌跡が表示されている場合は、機能が動作していることがわかります。

この機能は、holographic キーボードの性質上、指に対する抵抗力を持たない (携帯電話ディスプレイとは異なります) ため、およびマスターを使用しても注意が必要です。 この機能はパブリックリリース向けに評価されているので、お客様のフィードバックは重要です。機能が役に立つ場合でも、建設的なフィードバックがある場合でも、 [フィードバックハブ](hololens-feedback.md)を通じてお知らせください。

### <a name="power-menu-from-start"></a>[スタート] の [電源] メニュー

ユーザーがサインアウトし、デバイスをシャットダウンして再起動できる新しいメニュー。 HoloLens のスタート画面に、システムの更新プログラムが利用可能になったことを示すインジケーター。

#### <a name="how-to-use"></a>使用方法

1. [開始] [ジェスチャ](hololens2-basic-usage.md#start-gesture) を使用するか、[スタート画面に進む] を使用して、HoloLens のスタート画面を開きます。

2. ユーザープロファイルの画像の横にある省略記号アイコン (...) に注意してください。

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. ハンドまたは音声コマンド "Power" を使用して、ユーザープロファイルの画像を選択します。

4. デバイスをサインアウト、再起動、またはシャットダウンするためのオプションを含むメニューが表示されます。

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. [サインアウト] メニューオプションを選択し、HoloLens を再起動またはシャットダウンします。 デバイスが [1 つの Microsoft アカウント (MSA) またはローカルアカウント](hololens-identity.md)に対して設定されている場合、[サインアウト] オプションが使用できない可能性があります。

6. 他の場所に接してメニューを閉じるか、開始ジェスチャを使用して [スタート] メニューを閉じます。

#### <a name="update-indicator"></a>インジケーターの更新

更新プログラムが利用可能な場合、省略記号アイコンが表示され、再起動によって更新プログラムがインストールされることが示されます。また、メニューオプションも更新プログラムの存在を反映するように変更されます。<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>サインイン画面に複数のユーザーが表示される

以前にサインイン画面には、最近サインインしたユーザーだけでなく、"その他のユーザー" エントリポイントのみが表示されていました。 複数のユーザーがデバイスにサインインしている場合、これでは十分ではないというお客様からのフィードバックを受け取りました。 ユーザー名を再入力する必要がありました。

この Windows Insider ビルドで導入された [PIN 入力] フィールドの右側にある **他のユーザー** を選択すると、サインイン画面に、以前にデバイスにサインインしている複数のユーザーが表示されます。 これにより、ユーザーは自分のユーザープロファイルを選択し、Windows Hello 資格情報を使用してサインインできます。 新しいユーザーは、[ **アカウントの追加** ] ボタンを使用して、[その他のユーザー] ページからデバイスに追加することもできます。

[その他のユーザー] メニューの [その他のユーザー] ボタンをクリックすると、デバイスに最後にサインインしたユーザーが表示されます。 このボタンを選択すると、このユーザーのサインイン画面に戻ります。

![サインイン画面の既定値](./images/multiusers1.jpg)

<br>

![サインイン画面のその他のユーザー](./images/multiusers2.jpg)

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

USB C のマイクによっては、マイク *と* スピーカーの両方として誤って報告されることに注意してください。 これは、HoloLens ではなくマイクに問題があります。 これらのマイクの1つを HoloLens に接続すると、サウンドが失われる可能性があります。 幸いにも、簡単な修正があります。  

[**設定**  ->  ] [**システム**  ->  **サウンド**] で、組み込みのスピーカー **(アナログ機能オーディオドライバー)** を **既定のデバイス** として明示的に設定します。 HoloLens は、マイクが取り外され、後で再接続された場合でも、この設定を記憶する必要があります。

![USB C マイクのトラブルシューティング](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>キオスクのビジター自動ログオン

この新機能により、ビジターアカウントの自動ログオンがキオスクモードで使用できるようになります。

AAD 以外の構成の場合、訪問者の自動ログオン用にデバイスを構成するには、次のようにします。

1. 次のようなプロビジョニングパッケージを作成します。
    1. ユーザーアカウントを許可するように **ランタイム設定/AssignedAccess** を構成します。
    1. 必要に応じて、後で管理できるように MDM **(ランタイム設定/ワークプレース/登録)** にデバイスを登録します。
    1. ローカルアカウントを作成しない
1. [プロビジョニングパッケージを適用](hololens-provisioning.md)します。

AAD 構成の場合、ユーザーはこの変更を行わずに、このような問題を解決することができます。 キオスクモード用に構成された AAD 参加済みデバイスは、サインイン画面からボタンを1回タップするだけで、ビジターアカウントにサインインできます。 ビジターアカウントにサインインすると、ユーザーが [スタート] メニューから明示的にサインアウトするか、デバイスが再起動されるまで、もう一度サインインするように求められることはありません。

ビジター自動ログオンは、 [カスタム oma-uri](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) ポリシーを使用して管理できます。

- URI 値:./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| ポリシー  | 説明   | 構成  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | 訪問者がキオスクに自動ログオンすることを許可します   | 1 (はい)、0 (いいえ、既定値)  |

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

Windows Insider リリース以降では、AAD グループキオスクモードでのエラーが発生した場合、キオスクのエクスペリエンスがグローバルキオスク構成 (存在する場合) にフォールバックします。

### <a name="new-settingsuris-for-page-settings-visibility"></a>新しい Settingは、ページ設定の可視性を示します

[Windows Holographic のバージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2)では、Settings [/PageVisibilityList ポリシー](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)を追加して、設定アプリ内で表示されるページを制限しました。 PageVisibilityList は、IT 管理者がシステム設定アプリ内の特定のページを表示またはアクセスできないようにするか、指定されたものを除くすべてのページに対して実行できるようにするポリシーです。

[ [ページ設定の表示](settings-uri-list.md)] にアクセスすると、この CSP を使用する手順と、以前のリリースで使用可能な uri の一覧を確認できます。

Windows Insider ビルドでは、IT 管理者が管理できる使用可能な設定 Uri の一覧が拡張されています。 これらの Uri の一部は、新しい設定アプリ内で新しく利用できる領域用です。 Settings/PageVisibilityList ポリシーを使用している場合は、次の一覧を確認し、必要に応じて、許可または禁止されたページを調整します。

> [!NOTE]
> **非推奨: ms 設定: ネットワーク-プロキシ**
>
> これらの新しいビルドでは、1つの設定ページが非推奨とされます。 [古い **ネットワーク & のインターネット**  >  **プロキシ**] ページは、グローバル設定として使用できなくなりました。 接続ごとの新しいプロキシ設定は、[**ネットワーク & インターネット**  >  **wi-fi**  >  **プロパティ**] または [**ネットワーク & インターネット**  >  **イーサネット** のプロパティ] にあり  >  ます。

<br>

| [設定] ページ                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| アプリ > アプリの & 機能                               | `ms-settings:appsfeatures`                         |
| アプリ > アプリ & 機能 > 詳細オプション          | `ms-settings:appsfeatures-app`                     |
| オフラインマップ > アプリ                                  | `ms-settings:maps`                                 |
| アプリ > オフラインマップ > ダウンロードマップ                  | `ms-settings:maps-downloadmaps`                    |
| マウス > デバイス                                      | `ms-settings:mouse`                                |
| USB > デバイス                                        | `ms-settings:usb`                                  |
| ネットワーク & インターネット > 機内モード                   | `ms-settings:network-airplanemode`                 |
| プライバシー > 全般                                    | `ms-settings:privacy-general`                      |
| プライバシー > インク & 個人設定の入力             | `ms-settings:privacy-speechtyping`                 |
| プライバシー > モーション                                     | `ms-settings:privacy-motion`                       |
| プライバシー > スクリーンショットの枠線                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| プライバシー > スクリーンショットとアプリ                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
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

Pc と、HoloLens Insider 20279.1006 を実行している他の HoloLens 2 デバイスを含む Windows 10 デバイスの近くで、を共有します。   ->    ->  HoloLens から PC にファイルまたは url を共有するには、[設定] [システム **共有**] で試してみることができます。 詳細については、 [Windows 10 で近くのデバイスと項目を共有](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)する方法を参照してください。

この機能は、 [接続/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)を介して管理できます。

### <a name="new-os-update-troubleshooter"></a>新しい OS 更新のトラブルシューティング

設定アプリ内の前のトラブルシューティングツールに加えて、新しい設定アプリの OS 更新プログラムを追加した新しいトラブルシューティングツールが追加されました。 [**設定**  ->  ] [**&amp; セキュリティ** の  >  **トラブルシューティング**  >  **Windows Update** に移動し、[**開始**] を選択します。 これにより、OS の更新に関する問題を再現しながら、IT またはサポートによるトラブルシューティングを容易にするために、トレースを収集することができます。

### <a name="delivery-optimization-preview"></a>配信の最適化のプレビュー

この HoloLens Insider update を使用すると、Windows Holographic for Business では、配信の最適化設定を早期にプレビューして、複数の HoloLens デバイスからのダウンロードにかかる帯域幅の消費を減らすことができます。 この機能と推奨されるネットワーク構成の詳細については、「 [Windows 10 更新プログラムの配信の最適化](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)」を参照してください。

次の設定は管理画面の一部として有効になっており、 [Intune から構成でき](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)ます。

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth 幅](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

このプレビューオファリングについて、いくつかの注意事項があります。

- このプレビューでは、HoloLens のサポートは OS の更新プログラムに限定されています。
- Windows Holographic for Business は、HTTP ダウンロードモードと、 [Microsoft 接続キャッシュエンドポイント](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)からのダウンロードのみをサポートしています。現時点では、ピアツーピアのダウンロードモードとグループの割り当ては、HoloLens デバイスではサポートされていません。
- HoloLens は Windows Server Update Services エンドポイントの展開または配信の最適化をサポートしていません。
- トラブルシューティングを行うには、接続されているキャッシュサーバーの診断、または **設定** の更新による hololens 上の hololens でのトレースの収集  >  **& セキュリティ**  >   **トラブルシューティング**  >   **Windows Update** を行う必要があります。

### <a name="improvements-and-fixes-in-the-update"></a>更新プログラムの機能強化と修正:

- [オフライン診断](hololens-diagnostic-logs.md#offline-diagnostics) には、シリアル番号と OS バージョン用の追加のデバイス情報も含まれます。

### <a name="known-issues-and-work-around"></a>既知の問題と回避策

#### <a name="pairing-hololens-to-pc"></a>HoloLens と PC のペアリング

Windows Insider ビルド20325.1000 より前では、ユーザーが [Windows Holographic、バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 、または [windows Holographic、version 2004](hololens-release-notes.md#windows-holographic-version-2004) のいずれかでペアリング資格情報を設定し、windows insider ビルドに更新した場合、Visual Studio などのアプリをデプロイおよびデバッグする目的で、HoloLens と PC をペアリングするための資格情報が以前に設定されています。 Windows Insider build 20325.1000 ではこの問題が解決され、デバイスポータルを使用して再開するための追加の操作は必要ありません。

[Insider ビルドを使用](#ffu-download-and-flash-directions)してデバイスをアップデートしたユーザーは、デバイスを PC とペアリングするために、デバイスを (20325.1000 + または GA ビルドのいずれかに) 更新する必要があります。

Windows Insider に登録されておらず、一般公開されたときに機能更新を実行するユーザーには影響しません。


## <a name="start-receiving-insider-builds"></a>Insider ビルドの受信を開始します

> [!NOTE]
> 最近更新したことがない場合は、デバイスを再起動して状態を更新し、最新のビルドを取得してください。
> - "デバイスの再起動" 音声コマンドは正常に機能します。 
> - [設定]/[Windows Insider Program] で [再起動] ボタンを選択することもできます。
>
> バックエンドには、発生した可能性があるバグがあり、これによって追跡が再開されます。

HoloLens 2 デバイスで、[**設定**  >  ] [**更新 & セキュリティ**] [  >  **Windows Insider program** ] に移動し、[**開始**] を選択します。 Windows Insider として登録するために使用したアカウントをリンクします。

Windows insider がチャネルに移動するようになりました。 **高速** リングが **開発チャネル** になり、**低速** リングが **ベータチャネル** になり、 **release preview** リングが **release preview チャネル** になります。 マッピングは次のようになります。

![Windows Insider channel の説明](images/WindowsInsiderChannels.png)

詳細については、windows ブログの「 [Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) Channel の概要」を参照してください。

次に、[ **Windows のアクティブな開発**] を選択し、 **開発チャネル** または **ベータチャネル** のビルドを受信するかどうかを選択して、プログラムの条件を確認します。

[ **Confirm > Restart Now** ] を選択して終了します。 デバイスが再起動したら、[設定] [& のセキュリティ > 更新プログラムをチェックし、最新のビルドを取得するため **の更新プログラムを確認 >** ます。

### <a name="update-error-0x80070490-work-around"></a>Update エラー0x80070490 の回避策
Dev または Beta チャネルで更新するときに更新エラー0x80070490 が発生した場合は、次の短期的な対処を試してください。 これには、insider チャネルを移動し、更新を選択して、Insider channel を戻す必要があります。

#### <a name="stage-one---release-preview"></a>ステージワンリリースプレビュー
1.  [設定]、[更新プログラム & セキュリティ]、[Windows Insider Program] を選択し、[ **Release Preview Channel**] を選択します。
2.  設定、更新 & セキュリティ、Windows Update、 **更新を確認** します。 更新後、段階2に進みます。

#### <a name="stage-two---dev-channel"></a>ステージ2開発チャネル
1. [設定]、[更新プログラム & セキュリティ]、[Windows Insider Program] の [ **開発チャネル**] を選択します。
2. 設定、更新 & セキュリティ、Windows Update、 **更新を確認** します。

## <a name="ffu-download-and-flash-directions"></a>FFU のダウンロードとフラッシュの方向
フライト署名済み ffu を使用してテストするには、フライト署名済み ffu を点滅させる前にデバイスのロックを解除する必要があります。
1. PC の場合:

    1. から PC に ffu をダウンロード [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) します。
    
    1. Microsoft Store から ARC (Advanced Recovery コンパニオン) をインストール [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) します。
    
1. HoloLens-フライトのロック解除: [**設定** の  >  **更新] & セキュリティ**]  >  [**Windows Insider program** ] の順に選択し、サインアップして、デバイスを再起動します。

1. Flash FFU-atc を使用して、デジタル署名された FFU をフラッシュできるようになりました。

## <a name="provide-feedback-and-report-issues"></a>フィードバックの提供と問題の報告

HoloLens で [フィードバックハブアプリ](hololens-feedback.md) を使用して、フィードバックを提供し、問題を報告してください。 フィードバックハブを使用すると、エンジニアが迅速に問題をデバッグして解決できるように、必要な診断情報がすべて含まれるようになります。  HoloLens の中国語と日本語バージョンの問題は、同じように報告する必要があります。

> [!NOTE]
> フィードバックハブがドキュメントフォルダーにアクセスするかどうかを確認するメッセージが表示されることを確認します (メッセージが表示されたら [ **はい]** を選択します)。

## <a name="note-for-developers"></a>開発者向けのメモ

HoloLens の Insider ビルドを使用してアプリケーションを開発することをお勧めします。  ご利用を開始するには、 [HoloLens 開発者ドキュメント](https://developer.microsoft.com/windows/mixed-reality/development) を参照してください。 これらの命令は、HoloLens の Insider ビルドでも機能します。  既に HoloLens 開発に使用している Unity と Visual Studio の同じビルドを使用できます。

## <a name="stop-receiving-insider-builds"></a>Insider ビルドの受信を停止します

Windows Holographic の Insider ビルドを受信する必要がなくなった場合は、HoloLens が運用ビルドを実行しているときにオプトアウトできます。または、Advanced Recovery コンパニオンを使用してデバイスを [回復](hololens-recovery.md) し、デバイスを Insider バージョン以外の windows Holographic に回復することもできます。

> [!CAUTION]
> 新しいプレビュービルドを手動で再インストールした後に、Insider Preview ビルドから登録を解除したユーザーがブルースクリーンを使用するという既知の問題があります。 その後、デバイスを手動で回復する必要があります。 影響を受けるかどうかに関する詳細については、この既知の [問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)を参照してください。

HoloLens で運用ビルドが実行されていることを確認するには、次のようにします。

1. [設定] にアクセスし、[ **バージョン情報] を > >**、ビルド番号を見つけます。

1. [実稼働ビルド番号については、リリースノートを参照してください](hololens-release-notes.md)。

Insider ビルドをオプトアウトするには、次のようにします。

1. 実稼働ビルドを実行する HoloLens で、[ **設定] [& セキュリティ > Windows Insider program に更新 >**、[ **Insider ビルドの停止**] を選択します。

1. 指示に従ってデバイスをオプトアウトします。
