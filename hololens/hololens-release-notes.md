---
title: HoloLens 2 のリリース ノート
description: 新しい HoloLens 2 リリースごとに最新情報を入手できます。
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 06/17/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 16aec0e60fde40f0a2bffefa871a7a3774b1eb2e
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924538"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 のリリース ノート

HoloLens デバイスの生産性を維持するために、今後も機能、バグ、およびセキュリティ更新プログラムをリリースします。 このページでは、1か月あたりの HoloLens の新機能を確認できます。 最新の HoloLens 2 更新プログラムを取得するには、 [更新プログラムを確認して手動で更新](hololens-update-hololens.md#check-for-updates-and-manually-update) するか、完全なフラッシュ更新プログラム (ffu) を取得して、 [Advanced Recovery コンパニオンでデバイスをフラッシュ](hololens-recovery.md#clean-reflash-the-device)します。 [ダウンロード](https://aka.ms/hololens2download)は最新の状態に保たれ、一般公開されている最新のビルドを提供します。

> [!NOTE]
> 最近の Windows 11 の発表は、Windows の PC バージョンに重点を置いていました。 現在、5月2021に HoloLens 2 の [OS の主要な更新](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) を開始しました。これは、お客様からのフィードバックに基づいて今後のリリースで取り組んでいます。

> [!IMPORTANT]
> Microsoft では、リモートアシスタンスの [ユーザーに影響を与える、21H1 ビルドの既知の問題](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)により、Windows Holographic Version 21H1 更新プログラムの提供を一時停止しています。 また、既定の高度な回復用コンパニオンビルドも、最新の20H2 リリースである [Windows Holographic バージョン20h2 – June 2021 Update](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update)に変更されました。
>
> この問題の影響を軽減するために21H1 の可用性を低下させていますが、まだ21H1 に更新しようとしているお客様があることを理解しています。 21H1 に更新したいお客様は、次の2つの異なるパスを利用できます。
>
> - [Windows insider としてデバイスを登録](hololens-insider.md#start-receiving-insider-builds) し、 **ベータチャネル** を選択します。これにより、これらのデバイスを21h1 に更新し、信頼性の高いビルドを行うことができます。
> - [最新の FFU を PC にダウンロード](https://aka.ms/hololens2download) し、 [Advanced Recovery コンパニオンを使用してデバイスをフラッシュ](hololens-recovery.md#clean-reflash-the-device)します。

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic、バージョン 21H1-2021 年6月更新
- ビルド20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive for work または school カメラロールのアップロード

HoloLens 2 設定アプリに新機能が追加されました。これにより、デバイスの画像 > カメラロールフォルダーから、対応する OneDrive for work または学校フォルダーに、混合した現実の写真とビデオを自動的にアップロードできます。 この機能は、HoloLens 2 の [OneDrive アプリ内の機能のギャップ](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) に対処します。これは、お客様の個人 Microsoft アカウント (職場または学校のアカウントではなく) に対するカメラロールの自動アップロードのみをサポートします。

**動作のしくみ**

- [設定] にアクセスして [ **System > Mixed Reality カメラ** ] を > し、"カメラのアップロード" を有効にします。
- この機能を On の位置に設定すると、デバイスにキャプチャされた mixed reality の写真またはビデオは、OneDrive for work または学校アカウントの **[** 画像 > カメラロール] フォルダーにアップロードするために、自動的にキューに登録されます。
    >[!NOTE]
    >この機能を有効にする前にキャプチャした写真やビデオは、アップロードのキューに登録され *ない* ため、手動でアップロードする必要があります。
- [設定] ページのステータスメッセージには、アップロードを保留中のファイルの数が表示されます (または、保留中のすべてのファイルがアップロードされている場合は、OneDrive が最新の状態になっています)。
- 帯域幅に関する問題や、何らかの理由でアップロードを "一時停止" する場合は、この機能を **オフ** の位置に切り替えることができます。 この機能を一時的に無効にすると、新しいファイルをカメラのロールフォルダーに追加してもアップロードキューのサイズが増加し続けますが、この機能を再度有効にするまでファイルはアップロードされません。
- 最新のファイルが最初にアップロードされます (後入れ先出し)。
- OneDrive アカウントに問題がある場合 (パスワードの変更後など)、[設定] ページに [ **今すぐ修正** ] ボタンが表示されます。
- ファイルの最大サイズはありませんが、大きなファイルはアップロードに時間がかかることに注意してください (アップロードの帯域幅が制限されている場合は特に)。 大きなファイルのアップロード中に [一時停止] または [アップロード] をオフにすると、部分的なアップロードが保持されます。 アップロードが "一時停止" から数時間以内に再び有効になった場合、またはオフになっている場合、アップロードは中断された箇所から続行されます。 ただし、数時間後にアップロードを再び有効にすると、大きなファイルのアップロードが最初から再開されます。

**既知の問題と注意事項**

- この設定には、現在の使用帯域幅に基づく制限が組み込まれていません。 別のシナリオの帯域幅を最大化する必要がある場合は、設定を手動でオフにします。 アップロードは一時停止されますが、この機能は、新たに追加されたファイルのカメラロールへの監視を継続します。 続行する準備ができたら、アップロードを再度有効にしてください。
- この機能は、デバイス上のユーザーアカウントごとに有効にする必要があります。また、デバイスに現在サインインしているユーザーのファイルのみをアクティブにアップロードできます。
- [設定] ページのアップロード回数をリアルタイムで監視しているときに写真やビデオを撮影している場合は、現在のファイルのアップロードが完了するまで保留中のファイルの数が変更されないことに注意してください。
- デバイスがスリープ状態になった場合、または電源がオフになっている場合、アップロードは一時停止します。 保留中のアップロードが完了したことを確認するには、[設定] ページで "OneDrive が最新の状態" になっているか、 **電源 & スリープ** 設定を調整するまで、デバイスをアクティブに使用します。
### <a name="added-support-for-some-telemetry-policies"></a>一部のテレメトリポリシーのサポートを追加しました

HoloLens 2 では、次のテレメトリポリシーがサポートされるようになりました。
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry と System\ConfigureTelemetryOptInSettingsUx の両方を一緒に使用して、設定アプリのテレメトリと動作を完全に制御する必要があります。

更新プログラムの機能強化と修正:
- カラー調整による主要なビデオの破損を修正します。
- Power menu でテキストが切り捨てられる可能性のある問題に対処します。
- RequirePrivateStoreOnly ポリシーのサポートを有効にします。

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows Holographic、バージョン20H2 –2021年6月更新
- ビルド19041.1154

### <a name="added-support-for-some-telemetry-policies"></a>一部のテレメトリポリシーのサポートを追加しました

HoloLens 2 では、次のテレメトリポリシーがサポートされるようになりました。
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry と System\ConfigureTelemetryOptInSettingsUx の両方を一緒に使用して、設定アプリのテレメトリと動作を完全に制御する必要があります。

最新のビルド、Windows Holographic、バージョン21H1 を試すことをお勧めします。

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows Holographic、バージョン 1903-6 月2021更新プログラム
- ビルド18362.1116

更新プログラムの機能強化と修正:
- この月間品質更新プログラムには、重要な変更は含まれていません。最新のビルド、Windows Holographic、バージョン21H1 を試すことをお勧めします。

>[!IMPORTANT]
> このビルドはサービスされなくなります。

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
| [新しい Microsoft Edge](#introducing-the-new-microsoft-edge)  | 新しい Chromium ベースの Microsoft Edge が HoloLens 2 で利用可能になりました。 | エンド ユーザー | 
[WebXR と360ビューアー](#webxr-and-360-viewer) | イマーシブ web エクスペリエンスと360ビデオ再生を試してみてください。 | エンド ユーザー | 
[新しい設定アプリ](#new-settings-app) | レガシ設定アプリは、新しい機能と設定を使用して、更新されたバージョンに置き換えられています。 | エンド ユーザー |
[色の調整を表示する](#display-color-calibration) | HoloLens 2 ディスプレイの代替カラープロファイルを選択します。 | エンド ユーザー |
[既定のアプリピッカー](#default-app-picker) | ファイルまたはリンクの種類ごとに起動するアプリを選択します。 | エンド ユーザー |
[アプリごとのボリューム制御](#per-app-volume-control) | システム ボリュームとは独立してアプリ レベルのボリュームを制御します。 | エンド ユーザー |
[Web アプリをインストールする](#install-web-apps) | 新しいブラウザーを使用HoloLens 2、Microsoft Office Web アプリを Microsoft Edgeします。 | エンド ユーザー |
[スワイプして入力する](#swipe-to-type) | ホログラフィック キーボードで指のヒントを使用して単語を "スワイプ" します。 | エンド ユーザー |
[[スタート] の [電源] メニュー](#power-menu-from-start) | [スタート] メニューで、HoloLens デバイスを再起動してシャットダウンします。 | エンド ユーザー |
[[サインイン] 画面に表示される複数のユーザー](#multiple-users-listed-on-sign-in-screen) | [サインイン] 画面に複数のユーザー アカウントを表示します。 | エンド ユーザー |
[USB-C 外部マイクのサポート](#usb-c-external-microphone-support) | アプリやアプリの USB-C マイクを使用Remote Assist。 | エンド ユーザー |
[キオスクのビジター自動ログオン](#visitor-auto-logon-for-kiosks) | キオスク モードでビジター アカウントの自動ログオンを使用できます。 | IT 管理者 |
[キオスク モードの新しいアプリの新しい AUMID](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | 新しい設定と Edge アプリの AUMID。 | IT 管理者 |
[キオスク モードのエラーの引き渡しの改善](#kiosk-mode-behavior-changes-for-handling-of-failures) | キオスク モードでは、空のスタート メニューの前にグローバル割り当てアクセスが見えます。 | IT 管理者 |
[ページ設定を表示する新しい設定のURIs](#new-settings-uris-for-page-settings-visibility) | 20 以上の新しい SettingsURIs for Settings/PageVisibilityList ポリシー。 | IT 管理者 |
[フォールバック診断の構成](#configuring-fallback-diagnostics-via-settings-app) | 設定アプリでのフォールバック診断動作の設定。 | IT 管理者 |
[近くのデバイスと共有する](#share-things-with-nearby-devices) | HoloLens から PC にファイルまたは URL を共有します。 | すべて |
[新しい OS 診断トレース](#new-os-diagnostic-traces) | OS 更新プログラムの設定に関するページの新しいトラブルシューティング ツール。 | IT 管理者 |
[配信の最適化 プレビュー](#delivery-optimization-preview) | 複数の HoloLens デバイスからのダウンロードの帯域幅消費量を削減します。 | IT 管理者 |

関連するリリース ノートを確認します。

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
> 次の 2 つ以上の新Microsoft Edgeポリシーでは動作しないというHoloLens 2。
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>新しいアプリケーションからMicrosoft EdgeされるHoloLens 2

新しい Microsoft Edge は、新しい UWP アダプター レイヤーを備え、HoloLens 2 のような UWP 専用デバイスで実行できるネイティブ Win32 アプリなので、一部の機能はすぐには使用できない場合があります。 今後数か月間に新しいシナリオと機能をサポートする予定なので、この領域で最新の情報を確認してください。

**想定されるシナリオと機能:**
- 初回実行エクスペリエンス、プロファイルへのサインイン、同期
- Web サイトがレンダリングされ、期待どおりに動作する必要がある
- ほとんどのブラウザー機能 (お気に入り、履歴など) は期待した通りに動作する必要があります
- ダーク モード
- デバイスへの Web アプリのインストール
- 拡張機能のインストール (お使いでは正しく機能しない拡張機能を使用している場合は、お知HoloLens 2)
- PDF の表示と設定
- 1 つのブラウザー ウィンドウからの空間サウンド
- ブラウザーの自動更新と手動更新
- [印刷] メニューから PDF を保存する ([PDF に保存] オプションを使用)
- WebXR および 360 ビューアー拡張機能
- 環境内に配置された複数のウィンドウ間で参照する場合の、正しいウィンドウへのコンテンツの復元

**想定されていないシナリオと機能:**
- 同時オーディオ ストリームを使用した複数のウィンドウからの空間サウンド
- "見て、言って"
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
  1. インストールが正常に完了すると、Microsoft Edge Beta アプリの [すべてのアプリ] 一覧に、Microsoft Edge Beta、Dev、または Canary が別のエントリとして表示スタート メニュー。 

**コンピューターを使用して PC をWindows デバイス ポータル [(コンピューターで](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) 開発者モードを有効にするHoloLens 2)**
  1. お使いの PC で [、Edge Insider のダウンロード ページにアクセスします](https://www.microsoftedgeinsider.com/download)。
  1. インストールする Edge Insider **チャネル** の [Windows 10 for Windows 10] ボタンの横にあるドロップダウン矢印ボタンを選択します。
  1. ドロップダウン **HoloLens 2** の [オプション] を選択します。
  1. .msix ファイルを PC の "ダウンロード" フォルダー (または簡単に見つけられている別のフォルダー) に保存します。
  1. PC [Windows デバイス ポータル](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) を使用して、ダウンロードした .msix ファイルをインストールHoloLens 2。
  1. インストールが正常に完了すると、Microsoft Edge Beta アプリの [すべてのアプリ] 一覧に、Microsoft Edge Beta、Dev、または Canary が別のエントリとして表示スタート メニュー。 

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>WDAC を使用して新しいデータをブロックMicrosoft Edge

WDAC ポリシーを更新して新しい[](windows-defender-application-control-wdac.md)Microsoft Edge アプリをブロックする IT 管理者向けには、ポリシーに次の項目を追加する必要があります。

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>新しいエンドポイントのエンドポイントのMicrosoft Edge

一部の環境には、考慮すべきネットワーク制限がある場合があります。 新しい Edge でスムーズなエクスペリエンスを実現するには、これらの [Microsoft エンドポイントを有効にしてください。](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

[HoloLens の現在使用可能なエンドポイントの詳細については、以下を参照してください](hololens-offline.md)。

### <a name="install-web-apps"></a>Web アプリをインストールする
 > [!Note]
>Windows [Holographic バージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1)では、Office Web アプリはプレインストールされなくなりました。

新しい Edge を使用して、新しいアプリと共に web アプリMicrosoft Storeできます。 たとえば、SharePoint または OneDrive でホストMicrosoft Officeファイルを表示および編集する Web アプリをインストールできます。 Office Web アプリをインストールするには、アドレス バーの [使用可能なアプリ] または https://www.office.com **[Office** のインストール] ボタンにアクセスして選択します。 [インストール **] を選択** して確定します。

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

#### <a name="how-to-use-360-viewer"></a>360 ビューアーの使い方

1. YouTube で 360 度のビデオに移動します。
1. ビデオ フレームで、Mixed Reality ヘッドセット ボタンを選択します。

    ![360 ビューアーをアクティブ化するボタン](images/enter-360-viewer.jpg)

1. 特定のドメインで 360 ビューアーを初めて起動しようとすると、ブラウザーはイマーシブ ビューに入る同意を求めます。 **[許可]** を選択します。
1. [エア タップ](hololens2-basic-usage.md#select-using-air-tap) で再生コントロールを表示します。 ハンド [レイとエア タップ](hololens2-basic-usage.md#select-using-air-tap) を使用して、再生/一時停止、前方/戻るスキップ、キャプションのオン/オフの切り替え、エクスペリエンスの停止 (イマーシブ ビューを終了) します。 再生コントロールは、数秒の非アクティブ状態の後に消えます。

#### <a name="top-webxr-and-360-viewer-known-issues"></a>WebXR と 360 ビューアーの既知の問題
- WebXR エクスペリエンスの複雑さによっては、フレームレートが低下したり、つまずく場合があります。
- WebXR での多関節手関節のサポートは、既定では有効になっていません。 開発者は、"WebXR ハンド入力" をオンにすることで、 を使用 `edge://flags` してサポートを有効にできます。
- YouTube 以外の Web サイトから 360 本の動画が想定通り動作しない場合があります。

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>WebXR と 360 ビューアーに関するフィードバックの提供

新しいサービスのフィードバックの送信機能を使用して、フィードバックとバグをチームと共有Microsoft Edge。

### <a name="new-settings-app"></a>新しい設定アプリ

このリリースでは、新しいバージョンの設定アプリが導入されます。 新しい設定アプリには、サウンド、Power & スリープ、ネットワーク & インターネット、アプリ、アカウント、簡単操作 など、HoloLens 2 の新機能と拡張された設定が含まれています。

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
- 以前に配置した [設定] ウィンドウは削除されます (上記の注を参照)。
- 設定アプリを使用してデバイスの名前を変更できなくなりました。 IT 管理者は、Windows Autopilot デバイス名テンプレートの [HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) または MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName ノードを使用して、デバイスの名前を変更できます。
- [イーサネット] ページには、仮想イーサネット デバイス ("UsbNcm") が表示されます。
- 新しい Microsoft Edge のバッテリ使用量は、UWP アダプター レイヤーでサポートされる Win32 デスクトップ アプリケーションとしての性質上、正確ではない可能性があります (間もなく修正は予定されていません)。

#### <a name="display-color-calibration"></a>色の調整を表示する



この新しい設定を使用すると、表示する別の色プロファイルをHoloLens 2できます。 これは、特にディスプレイの明るさレベルが低い場合に、色をより正確に表示するのに役立つ場合があります。 表示色の調整は、[設定] アプリの [システムの調整] ページ>確認できます。

> [!NOTE]
> この設定では、新しいカラー プロファイルがディスプレイ ファームウェアに保存されます。これはデバイスごとの設定です (各ユーザー アカウントに固有ではありません)。

##### <a name="how-to-use-display-color-calibration"></a>表示色の調整を使用する方法

1. 設定アプリ **を起動** し **、System > Calibration に移動します**。
1. [ **色の調整の表示] で**、[表示の色調整 **の実行] ボタンを選択** します。
1. ディスプレイの色調整エクスペリエンスが起動し、バイザーが正しい位置に配置されていることを確認する必要があります。
1. 指示ダイアログ ボックスに進むと、ディスプレイが自動的に明るさ 30% に淡色表示されます。
    > [!TIP]
    > 環境内で淡色表示されたシーンが表示される場合は、デバイスの左側にある明るさボタンを使用して、HoloLens 2 の明るさレベルを手動で調整できます。
1. ボタン 1 から 6 を選択して各カラー プロファイルをすぐに試し、目に最適なプロファイルを見つける (これは通常、シーンが最も中立的に見えるのに役立つプロファイルを意味し、グレースケール パターンとスキン トーンは期待したように見えます)。

    ![色調整シーンを表示する](images/color-cal-ui.png)
    
1. 選択したプロファイルに問題が表示された場合は、[Save **& Exit]を選択** します。
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

[常に] を選択した後で、特定のファイルまたはリンクの種類を処理するアプリを変更する場合は、保存した既定値を [設定] の [アプリ] でリセット> **できます**。 ページの下部までスクロールし、[ファイルの種類の既定のアプリ] または [リンクの種類の既定のアプリ] の下にある [クリア] ボタンを選択します。 デスクトップ PC での同様の設定とは異なり、個々のファイルの種類の既定値をリセットできない。

#### <a name="per-app-volume-control"></a>アプリごとのボリュームコントロール

この Windows ビルドでは、ユーザーは各アプリのボリューム レベルを手動で調整できます。 これにより、ユーザーは必要なアプリに集中したり、複数のアプリを使用する場合に聞き取りを向上することができます。 別のアプリでリモート アシスタンスのために別のユーザーを呼び出しながら、あるアプリのボリュームをダウンする必要があるなどです。

個々のアプリのボリュームを設定するには、[設定 **]**[システム サウンド] に移動し、[詳細なサウンド オプション] で [アプリのボリュームとデバイスの基本  ->    ->  **設定] を選択します**。<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>スワイプして入力する

一部のお客様は、入力する予定の単語の形をスワイプすることで、仮想キーボードで "入力" する方が速く見つかり、ホログラフィック キーボード用にこの機能をプレビューしています。 ホログラフィック キーボードの平面から指の先を渡し、単語の形をスワイプし、キーボードの平面から指のヒントを引き出して、一度に 1 つの単語をスワイプできます。 単語間でキーボードから指を削除することで、スペース バーを押す必要なく、フォローアップ ワードをスワイプできます。 キーボードで指の動きの後にスワイプ の道が見える場合は、機能が動作しているのがわかっています。

この機能は、(携帯電話のディスプレイとは異なり) 指に対する抵抗を感じないホログラフィック キーボードの性質上、使用とマスターが難しい場合があります。 

### <a name="power-menu-from-start"></a>[スタート] の [電源] メニュー

ユーザーがデバイスをサインアウト、シャットダウン、再起動できる新しいメニュー。 HoloLens アプリケーションのインジケータースタート画面、システム更新プログラムが利用可能な場合を示します。

#### <a name="how-to-use"></a>使用方法

1. 開始ジェスチャを使用するかスタート画面を使用して HoloLens ファイルを開[スタートに移動。](hololens2-basic-usage.md#start-gesture)

2. ユーザー プロファイルの画像の横にある省略記号アイコン (...) に注意してください。<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. 手または音声コマンド "Power" を使用して、ユーザー プロファイルの画像を選択します。

4. メニューが表示され、デバイスのサインアウト、再起動、シャットダウンのオプションが表示されます。<br/><br/>

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
> USB マイクを **接続すると、入力デバイス として自動的に設定されません**。 USB-C の一連のヘッドセットを接続すると、ユーザーは、ヘッドセットのオーディオが自動的にヘッドセットにリダイレクトされるのを確認しますが、HoloLens OS では、他の入力デバイスよりも内部マイク 配列の優先順位が優先されます。 **USB-C マイクを使用するには、次の手順に従います。**

ユーザーは、[サウンド設定] パネルを使用して USB-C 接続外部マイク **を** 選択できます。 USB-C マイクは、通話や録音などに使用できます。

設定アプリを **開き**、 [システム サウンド]**を**  >  **選択します**。

![サウンド設定](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> を使用して外部マイクを **Remote Assist、** ユーザーは [サウンド デバイスの管理] ハイパーリンクをクリックする必要があります。
>
> 次に、ドロップダウンを使用して、外部マイクを [既定] または [通信の既定値 **]** **に設定します。** [既定] **を** 選択すると、外部マイクがどこでも使用されます。
>
> [ **通信の既定値]** を選択すると、外部マイクは Remote Assist や他の通信アプリで使用されますが、HoloLens マイク配列は他のタスクにも引き続き使用できます。

![サウンド デバイスを管理する](images/usbc-mic-2.png)

<br>

![マイクの既定値を設定する](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Bluetooth マイクのサポートについて

残念ながら、Bluetooth マイクは現在、現在、HoloLens 2。

#### <a name="troubleshooting-usb-c-microphones"></a>USB-C マイクのトラブルシューティング

一部の USB-C マイクでは、マイクとスピーカーの両方として誤って報告される *点に* 注意してください。 これは、HoloLens ではなく、マイクに関する問題です。 これらのマイクのいずれかを HoloLens に接続すると、サウンドが失われる可能性があります。 さいわい、簡単な修正があります。  

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

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>キオスク モードで新しい設定アプリと Edge アプリを使用する

キオスクにアプリを [含めた](hololens-kiosk.md)場合、IT 管理者は多くの場合、キオスクにアプリを追加しますが、アプリ ユーザー モデル ID (AUMID) を使用します。 設定アプリと Microsoft Edge アプリの両方が新しいアプリと見なされ、それらのアプリに AUMID を使用する古いアプリキオスクとは異なるので、新しい AUMID を使用するには更新する必要があります。

キオスクを変更して新しいアプリを含める場合は、新しい AUMID に を追加し、古いアプリを残することをお勧めします。 これにより、ユーザーが OS を更新するときに簡単に切り替わるので、キオスクを意図した方法で使用し続ける新しいポリシーを受け取る必要がなされます。

| アプリ                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| 古い設定アプリ       | HolographicSystemSettings_cw5n1h2txyewy!アプリ            |
| 新しい設定アプリ       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!アプリ |
| 古いMicrosoft Edgeアプリ | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| 新Microsoft Edgeアプリ | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>エラー処理のためのキオスク モードの動作の変更

以前のビルドでは、デバイスにキオスク構成 (グローバル割り当てアクセスと AAD グループ メンバー割り当てアクセスの両方の組み合わせ) がある場合、AAD グループ メンバーシップが失敗したと判断すると、ユーザーには "[スタート"](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)メニューに何も表示されません。

この Windows リリースから、キオスク エクスペリエンスは、AAD グループ キオスク モード中に障害が発生した場合にグローバル キオスク構成 (存在する場合) にフォールバックします。

### <a name="new-settings-uris-for-page-settings-visibility"></a>ページ設定を表示する新しい設定 URI

[Windows Holographic バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2)では、設定アプリ内に表示されるページを制限する[Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)ポリシーを追加しました。 PageVisibilityList は、IT 管理者がシステム設定アプリ内の特定のページを表示またはアクセスできないか、指定したページを除くすべてのページに対してこれを行えるようにするポリシーです。

[ページ設定の [表示] に](settings-uri-list.md)アクセスすると、この CSP を使用する手順と、以前のリリースで使用できる URI の一覧が表示されます。

IT 管理者が管理できる使用可能な設定 URI の一覧が表示されます。 これらの URI の一部は、新しい設定アプリ内の新しく使用可能な領域用です。 Settings/PageVisibilityList ポリシーを使用している場合は、次の一覧を確認し、必要に応じて許可またはブロックされたページを調整します。

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
| System > Sound                                       | `ms-settings:sound`                                |
| System > Sound > アプリのボリュームとデバイスの基本設定 | `ms-settings:apps-volume`                          |
| System > Sound > サウンド デバイスの管理              | `ms-settings:sound-devices`                        |
| System > Storage > Configure ストレージ センサー         | `ms-settings:storagepolicies`                      |
| Time & Language > Date & time                        | `ms-settings:dateandtime`                          |
| Time & Language > Keyboard                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| セキュリティ &のリセット>回復&更新する               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>更新された URI

以前は、次の 2 つの URI は、指定されたページにユーザーを直接移動するのではなく、メインの更新ページのみをブロックしました。 ページに移動するために、次の項目が更新されました。

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>設定アプリを使用したフォールバック診断の構成

[設定アプリ] で、ユーザーはフォールバック診断 の動作 [を構成できます](hololens-diagnostic-logs.md)。 [設定] アプリで、[プライバシーの **トラブルシューティング]**  ->  **ページに移動** して、この設定を構成します。

> [!NOTE]
> デバイスに対して MDM ポリシーが構成されている場合、ユーザーは、その動作をオーバーライドできます。  

### <a name="share-things-with-nearby-devices"></a>近くのデバイスと共有する

PC と他の Windows 10 デバイスの両方を含め、近くのデバイスとHoloLens 2します。 「設定システム共有エクスペリエンス」で試して  ->    ->  、HoloLens から PC にファイルまたは URL を共有できます。 詳細については、 で近くのデバイスと情報を共有する方法[に関するページをWindows 10。](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)

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

- HoloLens のサポートは、このプレビューでは OS の更新プログラムにのみ制限されています。
- Windows Holographic for Businessは、HTTP ダウンロード モードと Microsoft 接続キャッシュ エンドポイント [からのダウンロードのみをサポートします](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)。現時点では、HoloLens デバイスでは、ピア ツー ピア のダウンロード モードとグループの割り当てはサポートされていません。
- HoloLens では、エンドポイントのデプロイまたは配信の最適化Windows Server Update Servicesサポートされていません。
- トラブルシューティングを行う場合は、接続キャッシュ サーバーで診断を行う必要があります。または、HoloLens 上の HoloLens で Settings Update & Security Troubleshooting Windows Update を使用してトレースを収集  >    >     >   **する必要があります**。

### <a name="it-admin---update-checklist"></a>IT 管理者 - 更新チェックリスト

このチェックリストは、現在のデバイス管理構成に影響を与える可能性がある、この機能更新プログラムに追加される新しい項目、または使用を開始する新機能を理解するのに役立ちます。

#### <a name="updates-to-kiosk-mode"></a>キオスクモードの更新プログラム

[**キオスクモードで新しいアプリの新しい AUMIDs を**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)✔️します。

キオスクで設定アプリまたは Microsoft Edge アプリを以前に使用していた場合、これらのアプリは別のアプリ ID を使用する新しいアプリに置き換えられました。 以下 [のキオスクモードで新しいアプリの新しい AUMIDs](#use-the-new-settings-and-edge-apps-in-kiosk-modes) を読むことを強くお勧めします。 これにより、キオスクの設定アプリを引き続き使用するか、新しい Microsoft Edge アプリを含めることができます。 これらの変更は、今すぐ実行し、すべてのデバイスに展開して、更新をスムーズに移行できるようにすることができます。

[**キオスクの✔️ビジターの自動ログオン**](#visitor-auto-logon-for-kiosks): 

訪問者がキオスクに自動的にログインできるようになりました。 この動作は既定で有効になっていますが、管理と無効化を行うことができます。

✔️ [**キオスクモードのエラー**](#kiosk-mode-behavior-changes-for-handling-of-failures)処理の改善:

サインインしている AAD ユーザーの AAD グループメンバーシップが正常に決定されていない場合、[スタート] メニュー (存在する場合) にはグローバルキオスク構成が使用されます。それ以外の場合、ユーザーには空の [スタート] メニューが表示されます。 空の [スタート] メニューは、直接設定できる構成ではありませんが、キオスクを使用している場合は、この新しい処理によってサポート部門に通知されることがあります。これは、構成に適用される可能性があります。また、割り当てられているアクセス構成に新しい調整を加える必要があります。

#### <a name="updates-to-page-settings-visibility"></a>ページ設定の表示に対する更新

[**ページ設定の表示用に新しい設定 uri を**✔️](#new-settings-uris-for-page-settings-visibility)

現在、 [ページ設定の可視性](settings-uri-list.md) を使用している場合は、許可またはブロックされている既存の uri に対して調整を行うことができます。

#### <a name="updates-for-your-wdac-policy"></a>WDAC ポリシーの更新
✔️、以前に WDAC 経由で Microsoft Edge をブロックしていた場合は、WDAC ポリシーを更新する必要があります。 次の内容を確認し、提供されているサンプルコードを使用してください。
#### <a name="enable-new-endpoints-for-edge"></a>エッジの新しいエンドポイントを有効にする
✔️プロキシやファイアウォールなどのネットワークエンドポイントを構成するインフラストラクチャがある場合は、新しい Microsoft Edge アプリに対してこれらの新しいエンドポイントを有効にしてください。

#### <a name="newly-configurable-items"></a>新しく構成可能な項目

[フォールバック診断の構成](#configuring-fallback-diagnostics-via-settings-app)✔️: フォールバック診断を収集するかどうかを構成できます。

[近くのデバイスで項目を共有](#share-things-with-nearby-devices)✔️: 新しい近くにある共有機能を無効にすることができます。

[新しい Microsoft edge のポリシー設定を構成](#configuring-policy-settings-for-the-new-microsoft-edge)✔️には、microsoft edge で使用できるようになった新たな構成を確認します。

#### <a name="new-diagnostic-tool"></a>新しい診断ツール

[新しい os 診断トレース](#new-os-diagnostic-traces)の✔️: Os の更新に関連するログを収集します。

### <a name="improvements-and-fixes-in-the-update"></a>更新プログラムの機能強化と修正:

- [オフライン診断](hololens-diagnostic-logs.md#offline-diagnostics) には、シリアル番号と OS バージョン用の追加のデバイス情報も含まれます。
- ランタイムプロビジョニングパッケージを使用した基幹業務アプリケーションの展開に関する問題を修正しました。
- 基幹業務アプリケーションのインストール状態レポートに関する問題を修正しました。
- デバイスのリセットを通じて新しいアプリパッケージの永続化に関する問題を修正します。
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

- ローカルアカウントのパスワードを変更しようとしたときに設定アプリがクラッシュする問題に対処します。


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic、バージョン 20H2-2021 年3月更新
- ビルド19041.1140

更新プログラムの機能強化と修正:

- Advanced Photocapture または LowLagPhotoCapture を使用して HoloLens 2 で写真を取り込むと、写真がキャプチャされてから最大3秒間カメラを取得できるようになりました。
- デバイスポータルサービスのメモリリークを修正しました。この問題により、他のアプリケーションがメモリの割り当てに失敗する原因となったサービスによるメモリ使用量が増加しました。
- 段階的なロールアウトに登録されたユーザーがデバイスにサインインできないという問題を修正しています。

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic、バージョン 1903-2021 年3月更新
- ビルド18362.1102

更新プログラムの機能強化と修正:

- デバイスポータルサービスのメモリリークを修正しました。この問題により、他のアプリケーションがメモリの割り当てに失敗する原因となったサービスによるメモリ使用量が増加しました。

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic、バージョン 20H2-2021 年2月更新
- ビルド19041.1136

更新プログラムの機能強化と修正:

- デバイスの初期セットアップとアプリの更新プログラムの保存に関する問題を修正します。
- 将来の HoloLens リリースでのアップグレードとフライトに関する問題に対処します。
- HoloLens デバイスから、使用されていないプレインストールされた証明書を eSIM ルートストアから削除しました。

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic、バージョン 1903-2021 更新プログラム
- ビルド18362.1098

この月間品質更新プログラムには、重要な変更は含まれていません。 Windows Holographic バージョン2004の最新のビルドを試すことをお勧めします。

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

開発者モードを有効にしたり、デバイスポータルを使用したりすることなく、アプリをインストールできるようになりました。  Appx バンドルをデバイスに (USB 経由またはエッジ経由で) ダウンロードし、エクスプローラーで Appx バンドルに移動するだけで、インストールを開始するように求められます。  または、 [web ページからインストールを開始](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)します。  MDM の LOB アプリのデプロイ機能を使用して Microsoft Store またはサイドロードからインストールするアプリと同様に、アプリは [署名ツール](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) でデジタル署名する必要があり、 [署名に使用する証明書](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) は、アプリを展開する前に HoloLens デバイスによって信頼されている必要があります。

**アプリケーションのインストール手順。**

1.  デバイスが管理対象と見なされないようにする
1.  HoloLens 2 デバイスの電源が入っていて、PC に接続されていることを確認します。
1.  HoloLens 2 デバイスにサインインしていることを確認します。
1.  お使いの PC でカスタムアプリに移動し、yourapp を yourdevicename\Internal Storage\Downloads. にコピーします。   ファイルのコピーが完了したら、デバイスを切断することができます。
1.  デバイスからHoloLens 2スタート メニューを開き、[すべてのアプリ] を選択し、アプリを起動エクスプローラーします。
1.  [ダウンロード] フォルダーに移動します。 アプリの左側のパネルで、[このデバイス] を最初に選択し、[ダウンロード] に移動する必要があります。
1.  yourapp.appxbundle ファイルを選択します。
1.  このアプリ インストーラーが起動します。 [インストール] ボタンを選択して、アプリをインストールします。
インストールが完了すると、インストールされたアプリが自動的に起動します。

このフローをテストするサンプル アプリは [、Windows ユニバーサル サンプル GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) にあります。

を使用してアプリをインストール[するプロセスの詳細については、HoloLens 2を参照アプリ インストーラー。](app-deploy-app-installer.md)  

![以下を使用した MRTK のアプリ インストーラー](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>更新プログラムの機能強化と修正:

- 手の追跡では、以前に手が失われた可能性がある多くの新しいケースで追跡が維持されます。  これらの新しいケースの一部では、手のひらの位置だけがユーザーの実際の手に基づいて更新され続け、もう一方の関節は前の姿勢に基づいて推論されます。  この変更は、スラップ、スロー、傾斜、アプリの適用などの動きの追跡の一貫性を向上させるのに役立ちます。  また、手が表面に近い場合やオブジェクトを保持している場合にも役立ちます。  手の関節が推論されている場合 [、関節ごとの](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) 精度の値は 、"高" ではなく "近似" に設定されます。
- アカウントの PIN リセットで、Azure ADが表示される問題を修正しました。
- ET、Iris を設定アプリ、新しいユーザー、または通知トーストから起動すると、起動後の OOBE クラッシュがはるかに少なく表示される必要があります。
- ユーザーは、OOBE から正しいタイム ゾーンが出てくる必要があります。

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic バージョン 1903 – 2020 年 12 月の更新プログラム
- ビルド 18362.1088

この毎月の品質更新プログラムには、特に重要な変更が含まれているのではなく、最新の Windows Holographic バージョン 20H2 – 2020 年 12 月の更新プログラムと、ビルドに追加された新しい アプリ インストーラー 機能をお試しください。


## <a name="windows-holographic-version-20h2"></a>Windows Holographic バージョン 20H2
- ビルド 19041.1128

Windows Holographic バージョン 20H2 が利用可能にされ、ユーザーや IT プロフェッショナルにHoloLens 2機能のセットが追加されました。 自動目の配置から、設定の証明書マネージャー、キオスク モード機能の向上、および新しい Autopilot セットアップ機能まで。 この新しい更新により、IT チームは HoloLens デバイスの構成と管理をきめ細かく制御し、ユーザーにさらにシームレスなホログラフィック エクスペリエンスを提供できます。 

この最新リリースは、バージョン 2004 の月次更新プログラムですが、今回は新機能を含めてお使いください。 メジャー ビルド番号は変わりません。Windows Updateバージョン 2004 (ビルド 19041) への月次リリースを示します。 [設定] 画面の [バージョン情報] 画面>ビルド番号を確認して、利用可能な最新のビルド 19041.1128 以上を確認できます。 最新リリースに更新するには、[設定] アプリを開き、[更新プログラムの更新&セキュリティ] に移動し、[更新プログラムの確認] をタップします。 HoloLens の更新プログラムを管理する方法の詳細については、このページを [参照してください](https://docs.microsoft.com/hololens/hololens-updates)。

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Windows Holographic バージョン 20H2 の新機能  

| 機能                                              | 説明                                                                                                                                     |
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
| [エラー処理のためのキオスク モードの動作の変更](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | キオスク モードの失敗に制限付きフォールバックが追加された。                                                                                                |
| [HoloLens ポリシー](hololens-release-notes.md#hololens-policies)                                    | HoloLens の新しいポリシー。     |
| [オフライン キオスクAzure ADグループ メンバーシップをキャッシュする](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | 新しいポリシーを使用すると、ユーザーはグループ メンバーシップ キャッシュを使用して、設定された日数のキオスク モードをオフラインで使用できます。                                        |
| [デバイスの新しい制限ポリシー HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | デバイス管理ポリシーが新しく有効になっていると、HoloLens 2。                                                                                |
| [新しい電源ポリシーのHoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | 電源タイムアウト設定で新しくサポートされたポリシー。  |
| [ポリシーの更新](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | 更新プログラムの制御を許可する新しく有効にされたポリシー。           |
| [[有効] [設定] ページの表示HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | 設定アプリに表示されるページを選択するポリシー。             |
| [調査モード](hololens-release-notes.md#research-mode) | 調査モードを使用HoloLens 2。 |
| [記録長の増加](hololens-release-notes.md#recording-length-increased) | MRC の記録は 5 分に制限されなくなりました。 |
| [更新プログラムの機能強化と修正](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | 更新プログラムの追加の修正。   |

### <a name="auto-eye-position-support"></a>自動目の位置のサポート

このHoloLens 2、目の位置により、正確なホログラムの配置、快適な表示エクスペリエンス、および表示品質の向上が可能になります。 目の位置は、目の追跡計算の一部として内部的に計算されます。 ただし、エクスペリエンスで視線入力が必要ない場合でも、各ユーザーは視線追跡の調整を行う必要があります。

**自動目の位置 (AEP) を使用** すると、ユーザーの目の位置を計算する操作を必要としません。 自動目の位置は、ユーザーがデバイスを置いた瞬間から自動的にバックグラウンドで作業を開始します。 ユーザーが前の目の追跡の調整を行っていない場合、自動目の位置は、20 - 30 秒の処理時間の後、表示システムにユーザーの目の位置を提供し始める。 ユーザー データはデバイスに保持されないので、ユーザーが離してデバイスを再度起動した場合、またはデバイスが再起動またはスリープからウェイクアップした場合は、このプロセスが繰り返されます。

自動目の位置機能では、未調整のユーザーがデバイスに配置すると、システム動作がいくつか変更されます。 このコンテキストでは、未調整のユーザーは、以前にデバイスで目の追跡の調整プロセスを実行していないユーザーを指します。

| アクティブ なアプリケーション | 以前の動作 | Windows Holographic バージョン 20H2 Update からの動作 |
|:-------------------|:-----------------|:-----------------------------------|
| 視線入力が有効でないアプリまたは Holographic Shell |[目の追跡の調整プロンプト] ダイアログが表示されます。 | プロンプトは表示されません。 |
| 視線入力が有効なアプリ | [目の追跡の調整プロンプト] ダイアログが表示されます。 | 視線追跡の調整プロンプトは、アプリケーションが視線入力ストリームにアクセスする場合にのみ表示されます。 |

ユーザーが視線入力が有効になっていないアプリケーションから視線入力データにアクセスするアプリケーションに切り替える場合は、調整プロンプトが表示されます。 

他のすべてのシステム動作は、現在のユーザーがアクティブな目追跡調整を行っていない場合と似ています。 たとえば、One-handed Start ジェスチャは有効になりません。 初期セットアップの Out-Of-Box-Experience に変更はありません。

目の視線入力データまたは非常に正確なホログラムの配置を必要とするエクスペリエンスの場合は、未調整のユーザーに視線追跡の調整を実行することをお勧めします。 これは、目の追跡の調整プロンプトからアクセスするか、スタート メニューから [設定] アプリを起動し **、[System > Calibration > Eye Calibration > Run eye calibration**] を選択することでアクセスできます。

この情報は、後で他の調整情報 [と一緒に確認できます](hololens-calibration.md#auto-eye-position-support)。 

### <a name="certificate-manager"></a>証明書マネージャー

- 新しい証明書マネージャーを使用して、デバイスのセキュリティとコンプライアンスのための監査、診断、検証ツールが改善されました。 この機能を使用すると、商用環境で大規模に証明書をデプロイ、トラブルシューティング、検証できます。

Windows Holographic バージョン 20H2 では、証明書の設定アプリに証明書マネージャー HoloLens 2追加しています。 [セキュリティ証明書 **の更新>設定&に>移動します**。 この機能を使用すると、デバイス上の証明書を表示、インストール、削除する簡単で使い分け的な方法が提供されます。 新しい証明書マネージャーにより、管理者とユーザーは、デバイスのセキュリティと準拠を維持するために、監査、診断、検証ツールが改善されました。 

-   **監査:** 証明書が正しく展開されていることを検証する機能、または証明書が適切に削除されていることを確認する機能。 
-   **診断:** 問題が発生した場合は、デバイスに適切な証明書が存在する場合は、時間を節約し、トラブルシューティングに役立ちます。 
-   **検証:** 証明書が目的の目的に対応し、機能することを確認すると、特に商用環境では、大規模に証明書を展開する前に、かなりの時間を節約できます。

一覧内の特定の証明書をすばやく検索するには、名前、ストア、または有効期限で並べ替えるオプションがあります。 ユーザーは証明書を直接検索することもできます。 個々の証明書のプロパティを表示するには、証明書を選択し、[情報] を **クリックします**。 

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

- OOBE 中にプロビジョニング パッケージを備えた USB ドライブが使用されている場合、ユーザーの操作を減らして自動化されたプロセス。

このリリースより前は、ユーザーは、ボタンの組み合わせを使用してプロビジョニングするために、OOBE 中にプロビジョニング画面を手動で起動する必要があります。 これで、ユーザーは USB ストレージ ドライブ上のプロビジョニング パッケージを使用して、ボタンの組み合わせをスキップできます。 

1. OOBE の最初の対話可能な瞬間にプロビジョニング パッケージを使用して USB ドライブを接続する
1. デバイスをプロビジョニングする準備ができたら、プロビジョニング ページが表示されたプロンプトが自動的に開きます。 

注: デバイスの起動中に USB ドライブが接続された状態の場合、OOBE は既存の USB ストレージ デバイスを列挙し、追加の USB ストレージ デバイスが接続されているのを監視します。

OOBE 中にプロビジョニング パッケージを適用する方法の詳細については [、HoloLens のプロビジョニングに関するドキュメントを参照](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) してください。

USB からの [自動起動プロビジョニングに関](hololens-provisioning.md#auto-launch-provisioning-from-usb) する追加情報については、HoloLens のプロビジョニングに関するドキュメントを参照してください。

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>OOBE でのプロビジョニング パッケージの自動確認
- [プロビジョニング パッケージ] ページが表示されている場合、ユーザーの操作を減らして自動プロセスを実行すると、一覧に表示されているすべてのパッケージが自動的に適用されます。

プロビジョニングのメイン画面が表示された場合、OOBE は、すべてのプロビジョニング パッケージの適用を自動的に開始する前に、10 秒をカウントダウンします。 ユーザーは、 [期待したパッケージを](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) 確認した後も、この 10 時間以内に確認または取り消しを行います。

### <a name="automatic-provisioning-without-using-ui"></a>UI を使用しない自動プロビジョニング
- プロビジョニングのためのデバイスの操作を減らした自動プロセスを組み合わせたもの。 

ユーザーは、USB デバイスからのプロビジョニングの自動起動とプロビジョニング パッケージの自動確認を組み合わせることで、デバイスの UI を使用したり、デバイスを装着したりすることなく、HoloLens 2 デバイスを自動的にプロビジョニングできます。 複数のデバイスに対して同じ USB ドライブとプロビジョニング パッケージを引き続き使用できます。 これは、同じ領域に複数のデバイスを一度に展開する場合に便利です。 

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

HoloLens 2 で TenantLockdown の CSP の RequireNetworkInOOBE ノードが true に設定されると、OOBE は、ネットワーク接続後に Autopilot プロファイルが正常にダウンロードされて適用されるのを無期限に待機します。 

HoloLens 2 で TenantLockdown の CSP の RequireNetworkInOOBE ノードが true に設定された後、OOBE では次の操作は許可されません。 
- ランタイム プロビジョニングを使用したローカル ユーザーの作成 
- ランタイム プロビジョニングAzure ADによる結合操作の実行 
- OOBE エクスペリエンスでデバイスを所有するユーザーの選択 

#### <a name="how-to-set-this-using-intune"></a>Intune を使用してこれを設定する方法 
1. カスタム OMA URI デバイス構成プロファイルを作成し、次に示すように RequireNetworkInOOBE ノードに true を指定します。
OMA-URI の値は、./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE である必要があります

   > [!div class="mx-imgBorder"]
   > ![OMA-URI を使用したテナント ロックダウンの設定](images/hololens-tenant-lockdown.png)

1. グループを作成し、そのデバイス グループにデバイス構成プロファイルを割り当てる。 

1. 前のHoloLens 2作成したグループのデバイス メンバーを作成し、同期をトリガーします。  

Intune ポータルで、デバイス構成が正常に適用されたことを確認します。 このデバイス構成がデバイスに正常に適用されるとHoloLens 2 TenantLockdown の効果がアクティブになります。

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Intune を使用してテナントロックダウンの RequireNetworkInOOBE を設定HoloLens 2方法 
1. 上記でHoloLens 2作成したデバイス構成が以前に割り当てられたデバイス グループから、デバイス グループを削除します。 

1. 次に示すように、カスタム OMA URI ベースのデバイス構成プロファイルを作成し、RequireNetworkInOOBE に false を指定します。 OMA-URI の値は、./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE である必要があります

   > [!div class="mx-imgBorder"]
   > ![Intune で OMA URI を使用して RequireNetworkInOOBE を false に設定しているスクリーンショット](images/hololens-tenant-lockdown-false.png)

1. グループを作成し、そのデバイス グループにデバイス構成プロファイルを割り当てる。 

1. 前のHoloLens 2作成したグループのデバイス メンバーを作成し、同期をトリガーします。

Intune ポータルで、デバイス構成が正常に適用されたことを確認します。 このデバイス構成がデバイスに正常に適用されるとHoloLens 2 TenantLockdown の影響は非アクティブになります。 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>TenantLockdown が true に設定された後、HoloLens で Autopilot プロファイルが割り当てられていない場合、OOBE 中に何が起こりますか? 
OOBE は Autopilot プロファイルがダウンロードされるのを無期限に待機し、次のダイアログが表示されます。 TenantLockdown の効果を削除するには、最初に Autopilot のみを使用してデバイスを元のテナントに登録する必要があります。また、TenantLockdown CSP によって導入された制限が削除される前に、前の手順で説明したように RequireNetworkInOOBE を設定解除する必要があります。 

![ポリシーがデバイスに適用される場合のデバイス内ビュー。](images/hololens-autopilot-lockdown.png)

この情報は [、Tenantlockdown CSP と Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)の下にある Autopilot の残りの部分と共に確認できます。

### <a name="global-assigned-access--kiosk-mode"></a>グローバル割り当てアクセス – キオスク モード
- キオスクモードをシステムレベルで適用する新しいキオスク方法を有効にすることにより、キオスクの Id 管理を減らしました。

この新機能により、IT 管理者は、システムレベルで適用可能な複数のアプリキオスクモード用に HoloLens 2 デバイスを構成することができます。また、システム上の id との関係がなく、デバイスにサインインするすべてのユーザーに適用されます。 この新機能については、「 [HoloLens グローバル割り当てアクセスキオスク](hololens-global-assigned-access-kiosk.md)」を参照してください。

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>マルチアプリキオスクモードでのアプリケーションの自動起動 
- アプリの自動起動に焦点を合わせ、キオスクモードエクスペリエンス用に選択された UI とアプリの選択範囲をさらに増やしています。

マルチアプリキオスクモードにのみ適用され、[割り当てられたアクセス構成] の下の強調表示された属性を使用して、1つのアプリのみを自動起動するように指定できます。 

ユーザーがサインインすると、アプリケーションが自動的に起動されます。 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>キオスクモードでのエラー処理の動作変更
- キオスクモードのエラーで利用可能なアプリを排除することで、より安全なキオスクモード。 

以前は、キオスクモードの適用中にエラーが発生した場合、[スタート] メニューのすべてのアプリケーションを表示するために HoloLens が使用されていました。 Windows Holographic バージョン20H2 でエラーが発生した場合は、次のように [スタート] メニューにアプリが表示されません。 

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
| MixedReality\AADGroupMembershipCacheValidityInDays | グループメンバーシップのキャッシュを使用して、Azure AD グループを対象とするキオスクの Azure AD 日数を制御します。 | 以下を参照してください。                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>オフラインキオスクのキャッシュ Azure AD グループメンバーシップ
- オフラインキオスクは、最大60日間、AAD グループで使用できます。

このポリシーでは、サインインしているユーザーのグループ Azure AD グループを対象とする割り当てられたアクセス構成で、Azure AD グループメンバーシップキャッシュを使用できる日数を制御します。 このポリシー値が0より大きい値に設定されている場合は、キャッシュが使用されます。  

名前: AADGroupMembershipCacheValidityInDays URI 値:./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最小-0 日  
最大-60 日 

このポリシーを正しく使用するための手順: 
1. Azure AD グループを対象とするキオスク用のデバイス構成プロファイルを作成し、HoloLens デバイスに割り当てます。 
1. カスタム OMA-URI ベースのデバイス構成を作成します。この構成では、このポリシー値を目的の日数 (> 0) に設定し、HoloLens デバイスに割り当てます。 
    1. URI 値は、/Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays のように OMA-URI テキストボックスに入力する必要があります。
    1. 許容される最小値と最大値の間の値を指定できます。
1. HoloLens デバイスを登録し、両方の構成がデバイスに適用されていることを確認します。 
1. インターネットが利用可能なときにユーザー1のサインインを Azure AD し、ユーザーのサインインと Azure AD グループのメンバーシップが正常に確認されると、キャッシュが作成されます。 
1. これで Azure AD ユーザー1が HoloLens をオフラインにして、ポリシー値で X 日の日数が許容される限り、キオスクモードで使用できるようになりました。 
1. 手順 4. と 5. は、他の Azure AD ユーザー N に対して繰り返すことができます。ここで重要なのは、Azure AD ユーザーは、少なくとも1回、キオスク構成の対象となる Azure AD グループのメンバーであることを確認できるように、インターネットを使用してデバイスにサインインする必要があるという点です。 
 
> [!NOTE]
> 手順 4. を実行すると Azure AD ユーザーに対して、"切断" 環境に記載されているエラー動作が発生します。 

### <a name="new-device-restriction-policies-for-hololens-2"></a>HoloLens 2 の新しいデバイス制限ポリシー
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
|     [スタンドアロン](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows 構成デザイナーで使用する値の例を次に示します。   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows 構成デザイナーで使用する値の例を次に示します。  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

DisplayOffTimeoutOnBattery と DisplayOffTimeoutPluggedIn 用のこれら2つの新しいポリシーは、 [デバイスの一般的な制限](hololens-common-device-restrictions.md)に追加されています。

> [!NOTE]
> HoloLens 2 での一貫したエクスペリエンスを実現するには、DisplayOffTimeoutOnBattery とスタンドアロンの両方の値が同じ値として設定されていることを確認してください。 DisplayOffTimeoutPluggedIn と StandbyTimeoutPluggedIn にも同じことが当てはまります。 最新のスタンバイの詳細については [、「表示、スリープ、休止状態のタイマー」](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) を参照してください。

### <a name="newly-enabled-update-policies-for-hololens"></a>HoloLens 用に新しく有効になった更新ポリシー
- 更新プログラムをインストールするとき、または [更新の一時停止] ボタンを無効にして更新を確認する方法の詳細。

これらの更新ポリシーは、HoloLens 2 デバイスで有効になりました。
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

これらの更新ポリシーと HoloLens デバイスでのそれらの使用方法の詳細については、「 [hololens 更新プログラムの管理](hololens-updates.md)」を参照してください。

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>HoloLens 2 で有効になっている設定ページの可視性
- 設定アプリの UI コントロールが増加しました。これは、限られたページの選択を示すために混同される可能性があります。

これで、IT 管理者がシステム設定アプリ内の特定のページを表示またはアクセスできないようにするか、指定されたページ以外のすべてのページで実行できるようにするポリシーが有効になりました。 この機能を完全にカスタマイズする方法については、下のリンクをクリックしてください。

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

HoloLens 2 でカスタマイズできるページ設定については、 [設定の uri](settings-uri-list.md)に関するページを参照してください。 
 
![設定アプリで変更されているアクティブ時間のスクリーンショット](images/hololens-page-visibility-list.jpg)

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
- 詳細については、オンラインで最新のプライバシーに関する声明を参照してください。
- ユーザーがプロビジョニングパッケージを使用して VPN プロファイルをプロビジョニングできない問題に対処しました。
- VPN 接続のプロキシ構成の問題を修正しています。
- NCM for AllowUsbConnection の MDM による USB 機能の列挙を無効にするポリシーが更新されました。
- デバイスが [シングルアプリキオスク](hololens-kiosk.md)として設定されている場合に、HoloLens デバイスが Media Transfer PROTOCOL (MTP) 経由でファイルエクスプローラーに表示されない問題に対処します。 MTP (および一般的な USB 接続) は、 [Allowusbconnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) ポリシーを使用して無効にすることもできます。
- [スタート] メニューのアイコンがキオスクモードで正しく拡大された問題を修正しました。
- Azure AD グループを対象としたキオスクモードでの HTTP キャッシュの妨害が原因で発生する問題を修正します。
- 開発者モードを無効にしてから再度有効にしない限り、ユーザーがプロビジョニングパッケージで開発者モードを有効にした後に [ペアリング] ボタンを使用できない問題を修正しました。

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic、バージョン 1903-2020 更新プログラム
- ビルド18362.1085

この月間品質更新プログラムには、重要な変更は含まれていません。最新の機能リリースビルド Windows Holographic (バージョン 20H2) を試すことをお勧めします。

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic、バージョン 2004-2020 更新プログラム
- ビルド19041.1124
 
更新プログラムの機能強化と修正:

- ランタイムシステム障害の原因となった不要なチェックを削除しました。

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic、バージョン 1903-2020 更新プログラム
- ビルド18362.1081

この月間品質更新プログラムには、重要な変更は含まれていません。 Windows Holographic バージョン2004の最新のビルドを試すことをお勧めします。

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic、バージョン 2004-9 月2020更新プログラム
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

- 設定アプリは、ユーザーが虹彩登録または視線追跡の調整エクスペリエンスに従うことができなくなります。
- デバイスの名前を変更し、その他の操作 (ネットワークへの接続など) を実行する OOBE 中にプロビジョニングパッケージを適用すると、名前の変更によってデバイスの再起動後に他の操作を実行できないというバグが修正されています。
- 視覚的な品質を向上させるために、初期のデバイスセットアップフローの配色を変更しました。

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic、バージョン 1903-2020 年8月更新
- ビルド18362.1074

この月間品質更新プログラムには、重要な変更は含まれていません。 Windows Holographic バージョン2004の最新のビルドを試すことをお勧めします。

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic、バージョン 2004-2020 年7月更新
- ビルド19041.1109

更新プログラムの機能強化と修正:

- 開発者は、デバイスポータルにセキュリティで保護された接続が必要であることを有効または無効にすることを選択できます。
- OS の更新後にアプリケーションが起動する信頼性が向上しました。
- 既定の受信トレイの明るさを100% に変更しました。
- HoloLens 2 で Windows デバイスポータルの HTTPS 転送に関する問題に対処します。

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic、バージョン 1903-2020 年7月更新
- ビルド18362.1071

更新プログラムの機能強化と修正:

- Unity アプリケーションが紛失または取り戻しの追跡によって削除される可能性がある問題を修正しました。
- 特定のデバイスで HoloLens エミュレーターとハードウェアアクセラレータを使用しているときに、排他的 HoloLens アプリがシェルにクラッシュする原因となった問題を修正しました。
- HoloLens 2 の Windows デバイスポータルでの HTTPS 転送に関する問題に対処しています。

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
- Wi-Fi 接続を介してデバイスポータルにアクセスすると、証明書が無効なために web ブラウザーがアクセスできなくなる可能性があります。 デバイス証明書が既に信頼されている場合でも、ブラウザーは "ERR_SSL_PROTOCOL_ERROR" などのエラーを報告することがあります。 この場合、セキュリティ警告を無視するオプションがないため、デバイスポータルに進行することはできません。 この更新プログラムにより、問題が解決されました。 デバイス証明書が以前にダウンロードされ、PC に信頼されていて、ブラウザーのセキュリティ警告を削除する場合は、ブラウザーのセキュリティの警告に対処するために、新しい証明書をダウンロードして信頼する必要があります。
- MSIX パッケージを使用してアプリをインストールできるランタイムプロビジョニングパッケージを作成する機能が有効になりました。
- **設定** システムホログラムに設定が追加されまし  >    >  た。これにより、デバイスのシャットダウン時にユーザーが Mixed Reality ホームからすべてのホログラムを自動的に削除できるようになります。
- Hololens エミュレーターで、ピクセル形式を変更する HoloLens アプリが黒をレンダーするような場合に発生する問題を修正しました。
- 虹彩ログイン中にクラッシュを引き起こしたバグを修正しました。
- 既存のアプリのストアの繰り返しダウンロードに関する問題を修正しています。
- イマーシブアプリによって Microsoft Edge が繰り返し開かれないようにするバグを修正した。
- 1903リリースから更新された後の最初の起動時の Photos アプリの起動に関する問題を修正しています。
- パフォーマンスと信頼性が向上しました。

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic、バージョン 1903-6 月2020更新プログラム
- ビルド18362.1064

更新プログラムの機能強化と修正:

- カスタム MRC レコーダーでは、特定のプロパティが指定されていない場合、その既定値が新しくなっています。
  - *MRC ビデオ効果* で、次のようにします。
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (イマーシブヘッドセット))
  - *MRC オーディオ効果* で、次のようにします。
    - LoopbackGain (Windows デバイスポータルの Mixed Reality キャプチャページの現在の "アプリオーディオゲイン" 値)
    - マイクロ電話の獲得 (Windows デバイスポータルの Mixed Reality キャプチャページの現在の "Mic オーディオゲイン" 値)
- Unity アプリケーションでは、HolographicSpace API は一般に無効になっています。 この動作により、バックグラウンドで実行する設定が有効になっている場合でも、バイザーが反転されたときに一部のアプリが一時停止する原因となる問題が回避されます。 この API は、Unity バージョン2018.4.18 以降、および2019.3.4 以降で有効になりました。
- Hololens エミュレーターで、ピクセル形式を変更する HoloLens アプリが黒をレンダーするような場合に発生する問題を修正しました。
- 1903リリースから更新された後の最初の起動時の Photos アプリの起動に関する問題を修正しています。

## <a name="windows-holographic-version-2004"></a>Windows Holographic、バージョン2004  
- ビルド-19041.1103

HoloLens 2、 *Windows Holographic、バージョン 2004* の2020年5月の主要なソフトウェア更新プログラムには、優れた新機能のホストが含まれています。たとえば、Windows 自動操縦、アプリのダークモード、USB イーサネットの 5G/LTE ホットスポットのサポートなどがあります。 最新のリリースに更新するには、**設定**   アプリを開き、[ **update & Security**] にアクセスして、[ **更新プログラムの確認**   ] ボタンを選択します。 

|             機能                              |          説明                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Windows 自動操縦を使用して新しいデバイスを事前に構成し、シームレスにセットアップする                 |
|       FIDO 2 のサポート                             |          共有デバイスの高速で安全な認証を実現するための FIDO2 セキュリティキーのサポート            |
|       プロビジョニングの向上                      |          USB ドライブから HoloLens にプロビジョニングパッケージをシームレスに適用する                              |
|       アプリケーションのインストール状態                 |          アプリ用の設定アプリが MDM 経由で HoloLens 2 にプッシュされていることを確認する               |
|       構成サービスプロバイダー (Csp)   |          管理者の制御機能を強化するための新しい構成サービスプロバイダーの追加                 |
|       USB 5G/LTE のサポート                       |          拡張された USB イーサネット機能により、5G/LTE のサポートが有効になります。                                    |
|       ダークアプリモード                              |          ダークモードとライトモードの両方をサポートするアプリで使用できるダークアプリモードで、表示エクスペリエンスが向上します。        |
|       音声指示コマンド                             |          HoloLens を制御する追加のシステム音声コマンドのサポート                           |
|       手動追跡の機能強化                 |          ハンドトラッキングの機能強化によって、ボタンと2D スレートの相互作用がより正確になりました                        |
|       品質の向上と修正                 |          プラットフォーム全体でのさまざまなシステムパフォーマンスと信頼性の向上                            |

### <a name="support-for-windows-autopilot"></a>Windows 自動操縦のサポート

HoloLens 2 の Windows 自動操縦機能を使用すると、デバイスの販売チャネルは HoloLens を Intune テナントに事前登録します。 デバイスが到着すると、テナント内の共有デバイスとして自己展開できるようになります。 自己展開を利用するには、USB-C からイーサネットを使用したセットアップの最初の画面で、デバイスをネットワークに接続する必要があります。

ユーザーが自動操縦用自己展開プロセスを開始すると、プロセスは次の手順を完了します。

1. デバイスを Azure Active Directory (Azure AD) に参加させます。
1. Azure AD を使用して、Microsoft Intune (または別の MDM サービス) にデバイスを登録します。
1. デバイスを対象とするポリシー、証明書、およびネットワークプロファイルをダウンロードします。
1. デバイスをプロビジョニングします。
1. サインイン画面をユーザーに表示します。

詳細については、「 [HoloLens 2 の Windows 自動操縦の評価ガイド」](https://docs.microsoft.com/hololens/hololens2-autopilot)を参照してください。

*今すぐ自動操縦プレビューに参加するには、アカウントマネージャーにお問い合わせください。自動操縦準備ができたデバイスは、間もなく発送が開始されます。*

### <a name="fido2-security-key-support"></a>FIDO2 セキュリティキーのサポート

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

基幹業務アプリの MDM アプリの展開と管理は、HoloLens にとって重要です。 管理者とユーザーは、監査と診断のためにアプリのインストール状態を表示する必要があります。 このリリースでは、   >    >  アカウント情報をクリックして設定アカウントに **アクセス職場または学校**  >    >  で詳細を追加しました。

### <a name="additional-csps-and-policies"></a>追加の Csp とポリシー

[構成サービスプロバイダー (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN)は、デバイスの構成設定を読み取り、設定、変更、または削除するためのインターフェイスです。 このリリースでは、追加のポリシーのサポートを追加して、管理者が展開した HoloLens デバイスよりも多くの制御を行うことができます。 HoloLens でサポートされる Csp の一覧については、「 [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)」を参照してください。

このリリースでの新しい内容

**Policy CSP** 

ポリシー構成サービスプロバイダーを使用すると、企業は Windows デバイスでポリシーを構成できます。 今回のリリースでは、ここに記載されている HoloLens の新しいポリシーを追加しました。 詳細については、「 [HoloLens 2 でサポートされているポリシー csp](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)」を参照してください。  

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

NetworkQoSPolicy 構成サービス プロバイダーは、ネットワークサービス品質 (QoS) ポリシーを作成します。 QoS ポリシーは、一連の照合条件に基づいて、ネットワーク トラフィックに一連のアクションを実行します。 詳細については [、「NetworkQoSPolicy CSP 」を参照してください](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>5G/LTE テザリングされたデバイスに対する USB イーサネットサポートの拡張

USB 経由で HoloLens 2 にテザリングされている場合に、5G/LTE フォンや Wi-Fi ホットスポットなどの特定のモバイル ブロードバンド デバイスを有効にするためにサポートが追加されました。 これらのデバイスは、別のイーサネット **接続としてネットワーク** 設定に表示されます。 (外部ドライバーを必要とするモバイル ブロードバンド デバイスはサポートされていません)。この機能を使用すると、テザリングWi-Fi十分なパフォーマンスWi-Fi高帯域幅接続が可能になります。 サポートされている USB デバイスの詳細については [、「Bluetooth および USB-C デバイスに接続する」を参照してください](https://docs.microsoft.com/hololens/hololens-connect-devices)。  

### <a name="hand-tracking-improvements"></a>手の追跡の機能強化

このリリースには、いくつかのハンド トラッキングの機能強化が含まれています。

- **ポイント姿勢の安定性:** これで、人差し指が手のひらに取り込むときに、システムは人差し指を触れ込むのを抵抗します。 この変更により、ボタンのプッシュ、入力、コンテンツのスクロールなど、精度が向上します。 
- **エア タップの偶発的な減少:** エアタップ ジェスチャの検出を改善しました。 手をサイドにドロップする場合など、いくつかの一般的なシナリオでは、偶発的なアクティブ化が少なくなっています。
- **ユーザー スイッチの信頼性:** デバイスを共有するときに手のサイズを更新する際に、システムの速度と信頼性が向上しました。
- **手盗みを減らします。** センサーを見て、手が 2 つ以上あるケースの処理を改善しました。 複数のユーザーが密接に作業している場合、追跡された手がユーザーからシーン内の他のユーザーの手に "ジャンプ" する可能性がはるかに低くなります。
- **システムの信頼性:** デバイスの負荷が高いときに手の追跡が動作を停止する原因となる問題を修正しました。

### <a name="dark-mode"></a>ダーク モード

多くの Windows アプリで、ダーク モードとライト モードの両方がサポートされています。 HoloLens 2ユーザーは、両方をサポートするアプリの既定のモードを選択できます。 更新後、既定のアプリ モードは "濃色" になりますが、この設定を簡単に変更できます。[設定] [システムの色] [既定のアプリ モードを選択]  >    >    >  **に移動します**。 

これらの "インボックス" アプリでは、ダーク モードがサポートされています。 

- Settings 
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
- 調査モードでのストリーミング中に発生したデバイスハングを修正しました。
- セッションを再び開始するときに、サインイン画面に適切なユーザーが表示されない場合があるバグを修正しました。
- ユーザーが [設定] を使用して MDM ログをエクスポートできない問題を **修正しました**。
- すぐに設定した後の目の追跡の精度が予想よりも低い可能性がある問題を修正しました。
- 特定の条件下で、目の追跡サブシステムが初期化または調整を実行できなかった問題を修正しました。
- 既に調整されたユーザーに対して目の調整を求める問題を修正しました。
- 目の調整中にドライバーがクラッシュする問題を修正しました。
- 電源ボタンを繰り返し押すと、60 秒のシステム タイムアウトとシェル クラッシュが発生する可能性がある問題を修正しました。
- 深度バッファーの安定性が向上しました。
- ユーザーがフィードバック **を** 簡単に共有フィードバック Hub共有] ボタンが追加されました。
- RoboRaid wan が正しくインストールされないバグを修正しました。

### <a name="known-issues"></a>既知の問題

- zh-CN システム言語に関する問題により、音声コマンドが Mixed Reality キャプチャを取得したり、デバイスの IP アドレスを表示したりするのを防止できます。
- 問題では、"Hey Cortana" 音声アクティブ化を使用するデバイスを起動した後、Cortana アプリを起動する必要があります。 18362 ビルドから更新した場合は、以前のバージョンの Cortana アプリの 2 つ目のアプリ タイルが表示され、 [開始] で機能しなくなる場合 **もあります**。

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic バージョン 1903 - 2020 年 5 月更新 
- ビルド 18362.1061

この毎月の品質更新プログラムには、前述のように、チームが Windows Holographic バージョン 2004 May Update に取り組っていたため、重要な変更は含め "一切" は含め "。"

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic バージョン 1903 - 2020 年 4 月の更新プログラム
- ビルド 18362.1059

**サポートされているアプリのダーク モード** 

多くの Windows アプリでは、ダーク モードとライト モードの両方がサポートされています。 HoloLens 2両方の配色をサポートするアプリの既定のモードを選択できます。 お客様からのフィードバックに基づいて、既定のアプリ モードを "ダーク" に設定していますが、この設定はいつでも簡単に変更できます。[設定] **> [システム] > [色**] に移動して [既定のアプリ モードを選択する] を見つける。 

これらの "インボックス" アプリでは、ダーク モードがサポートされています。
- Settings
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

- Unity アプリケーション用の HolographicSpace.UserPresence API を一時的に無効にしました。 この変更により、"バックグラウンドで実行" 設定が有効になっている場合でも、バイザーが反転した場合に一部のアプリが一時停止する問題が回避されます。
- ユーザーが UI がフリーズし、数秒後にシェルに戻るのをユーザーが気付いた、手の追跡によって発生するランダムな HUP クラッシュを修正しました。
- 人差し指で突っ込むときに、その指の上部が予期せず丸くならずになじむので、手の追跡が改善されました。
- ヘッドトラッキング、空間マッピング、その他のランタイムの信頼性が向上しました。

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic バージョン 1903 - 2020 年 1 月更新 
- ビルド 18362.1043
 
更新プログラムの機能強化と修正:

- アプリケーション エミュレーターを使用する場合の排他アプリの安定性HoloLens 2しました。

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic バージョン 1903 - 2019 年 12 月の更新プログラム 
- ビルド 18362.1042

更新プログラムの機能強化と修正:

- 最終ステージの再現 (LSR) の修正が導入されました。 ホログラムの深度をより正確に説明することで、ホログラムの視覚的なレンダリングが向上し、より安定して鮮明に見える。 この現象は、アプリがホログラムの深さを正しく設定しない場合、この更新後に顕著になります。
- 排他的なアプリと排他的なアプリ間のナビゲーションの安定性を修正しました。
- デバイスが数日間スタンバイ状態の後に Mixed Reality キャプチャでビデオを記録できない問題を解決しました。
- ホログラムの安定性が向上しました。

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic バージョン 1903 - 2019 年 11 月の更新プログラム 
- ビルド 18362.1039

更新プログラムの機能強化と修正:

- en-CA **と** en-AU の初期セットアップ中に音声コマンドを選択する機能を修正しました。
- 最新の Unity および MIXED REALITY Toolkit (MRTK) バージョンに配置されたオブジェクトのビジュアル品質が向上しました。
- ホログラフィック アプリケーションが開いてから閉じるまで、起動時に一時停止状態でスタックする問題スタート メニュー修正しました。
- OpenXR ランタイム準拠の修正と、HoloLens 2エミュレーターの機能強化。
