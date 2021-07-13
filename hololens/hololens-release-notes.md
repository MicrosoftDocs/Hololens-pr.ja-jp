---
title: HoloLens 2 のリリース ノート
description: 新しいリリースごとにすべての更新プログラムを最新のHoloLens 2してください。
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
ms.openlocfilehash: e0dd7d02ad923438134f2a45812db67f73fdcd8d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637185"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 のリリース ノート

ご利用のデバイスで生産性の高いエクスペリエンスをHoloLens、機能、バグ、およびセキュリティ更新プログラムを引き続きリリースします。 このページでは、各月の新しい機能HoloLens確認できます。 最新の更新プログラムHoloLens 2するには、更新プログラムを確認し、[](hololens-update-hololens.md#check-for-updates-and-manually-update)手動で更新するか、フル フラッシュ更新 (FFU) を取得して[、Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device)を使用してデバイスをフラッシュします。 ダウンロード [は](https://aka.ms/hololens2download) 最新の状態に保たれ、一般提供される最新のビルドが提供されます。

> [!NOTE]
> 最近の Windows 11 の発表では、PC バージョンの Windows。 最近、2021 年 5 月に HoloLens 2 に対する大規模な[OS](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067)更新プログラムを開始し、この年の今年の今年度のお客様からのフィードバックに基づいて、今後のリリースに取り組む予定です。

> [!IMPORTANT]
> Remote Assist ユーザーに影響を与えた[21H1](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)ビルドで既知の問題が解決されたので、Windows Holographic バージョン 21H1 更新プログラムのオファリングを一時的に一時停止しました。 また、既定の Advanced Recovery Companion (ARC) ビルドを[Windows Holographic バージョン 20H2 – June 2021 Update に変更しました](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update)。 ARC ビルドは、21H1 ビルドを対象として再開されます。

## <a name="windows-holographic-version-21h1---june-2021-update"></a>WindowsHolographic バージョン 21H1 - 2021 年 6 月更新
- ビルド 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDriveまたは学校のカメラ ロール のアップロードに関するページ

HoloLens 2 設定 アプリに新しい機能が追加されました。これにより、お客様はデバイスの Pictures > Camera Roll フォルダーから、対応する OneDrive for work または school フォルダーに Mixed Reality の写真とビデオを自動的にアップロードできます。 この機能は、HoloLens 2 上の[OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos)アプリ内の機能のギャップに対応します。これは、(仕事または学校アカウントではなく) 顧客の個人の Microsoft アカウント へのカメラ ロールの自動アップロードのみをサポートします。

**動作のしくみ**

- 「設定 > **System > Mixed Reality カメラ」にアクセス** して、"カメラのアップロード" を有効にしてください。
- この機能を [オン] の位置に設定すると、デバイスにキャプチャされた Mixed Reality の写真やビデオは、自動的にキューに登録され、OneDrive の仕事用または学校アカウント用の Pictures > Camera Roll フォルダーにアップロードされます。
    >[!NOTE]
    >この機能を有効にする前にキャプチャされた写真とビデオは、アップロード用にキューに登録されるのではなく、引き続き手動でアップロードする必要があります。
- 設定 ページのステータス メッセージには、アップロードが保留中のファイルの数が表示されます (または、保留中のすべてのファイルがアップロードされると "OneDrive が最新の状態" と読み取ります)。
- 帯域幅が気になる場合や、何らかの理由でアップロードを "一時停止" したい場合は、機能を [オフ] の位置に **切り替** えます。 この機能を一時的に無効にすると、Camera Roll フォルダーに新しいファイルを追加する間、アップロード キューは引き続き増加しますが、機能を再び有効にするまでファイルはアップロードされます。
- 最新のファイルが最初にアップロードされます (最後のファイル、最初のファイル)。
- お使OneDriveアカウントに問題がある場合 (パスワードの変更後など)、[今すぐ修正] ボタンが [設定されます。
- 最大ファイル サイズはありません。ただし、大きなファイルのアップロードには長い時間がかかる点に注意してください (特にアップロード帯域幅が制限されている場合)。 大きなファイルのアップロード中にアップロードを "一時停止" またはオフにした場合、部分的なアップロードは保持されます。 アップロードが "一時停止" またはオフになってから数時間以内に再び有効になっている場合、アップロードは中断された場所から続行されます。 ただし、数時間後にアップロードが再び有効になっている場合、大きなファイルのアップロードは最初から再開されます。

**既知の問題と注意点**

- この設定には、現在の帯域幅の使用量に基づく調整は組み込みはありません。 別のシナリオで帯域幅を最大化する必要がある場合は、手動で設定をオフにします。 アップロードは一時停止されますが、この機能はカメラ ロールに新しく追加されたファイルを引き続き監視します。 続行する準備ができたら、アップロードを再び有効にしてください。
- この機能は、デバイス上の各ユーザー アカウントに対して有効にする必要があります。また、デバイスに現在サインインしているユーザーのファイルのみをアクティブにアップロードできます。
- 設定 ページのアップロード数をリアルタイムで監視しながら写真やビデオを撮影している場合は、現在のファイルのアップロードが完了するまで、保留中のファイル数が変更されない可能性があります。
- アップロードがスリープ状態になっている場合、または電源がオフになっている場合は、一時停止します。 保留中のアップロードを確実に完了するには、設定 ページに "OneDrive が最新の状態" になるまでデバイスをアクティブに使用するか **、Power &** のスリープ設定を調整します。
### <a name="added-support-for-some-telemetry-policies"></a>一部のテレメトリ ポリシーのサポートを追加しました

次のテレメトリ ポリシーが、次のアプリケーションでサポートHoloLens 2。
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry と System\ConfigureTelemetryOptInSettingsUx の両方を一緒に使用して、設定 アプリのテレメトリと動作を完全に制御する必要があります。

更新プログラムの機能強化と修正:
- 色の調整を使用して、ビデオの大きな破損を修正します。
- [電源] メニューでテキストが切り捨てられる可能性がある問題を修正します。
- RequirePrivateStoreOnly ポリシーのサポートを有効にする。

## <a name="windows-holographic-version-20h2--june-2021-update"></a>WindowsHolographic バージョン 20H2 – 2021 年 6 月更新
- ビルド 19041.1154

### <a name="added-support-for-some-telemetry-policies"></a>一部のテレメトリ ポリシーのサポートを追加しました

次のテレメトリ ポリシーが、次のアプリケーションでサポートHoloLens 2。
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry と System\ConfigureTelemetryOptInSettingsUx の両方を一緒に使用して、設定 アプリのテレメトリと動作を完全に制御する必要があります。

Holographic バージョン 21H1 の最新Windowsをお試しください。

## <a name="windows-holographic-version-1903---june-2021-update"></a>WindowsHolographic バージョン 1903 - 2021 年 6 月の更新プログラム
- ビルド 18362.1116

更新プログラムの機能強化と修正:
- この毎月の品質更新プログラムには、重要な変更が含まれているのではなく、最新のビルドである Windows Holographic バージョン 21H1 をお試しください。

>[!IMPORTANT]
> このビルドはサービス提供されなくなりました。

## <a name="windows-holographic-version-21h1"></a>WindowsHolographic バージョン 21H1
- ビルド 20346.1002

この更新プログラムには、2 つの対象ユーザーの機能が含まれている。エンド ユーザーがデバイス上のだれでも使用できる機能と、IT 管理者が構成できる新しいデバイス管理オプション。 次の表は、各対象ユーザーに関連する機能を示しています。 IT 管理者の場合は、IT 管理者の更新チェックリスト [を参照してください](#it-admin---update-checklist)。
>[!IMPORTANT]
>このビルドに更新するには、HoloLens 2 デバイスが現在、2021 年 2 月の更新プログラム (ビルド 19041.1136) 以降を実行している必要があります。 この機能更新プログラムが利用できない場合は、まずデバイスを更新して、もう一度お試しください。

>[!NOTE]
>現在、Microsoft HoloLens 2 では、次のリリースの月次サービス更新プログラム (バグとセキュリティ修正プログラム) がサポートされています。
>- WindowsHolographic バージョン 20H2 (ビルド 19041.1128 以上)
>- WindowsHolographic バージョン 2004 (ビルド 19041.1103 以上)
>- WindowsHolographic バージョン 1903 (ビルド 18362+) 
>
> Windows Holographic バージョン 21H1 の導入により、Windows **Holographic バージョン 1903** の月次サービス更新プログラムは廃止されます。 これにより、より新しいリリースに集中し、貴重な改善を引き続き提供できます。 


| 機能名                                              | 簡単な説明                                                                      | 対象読者 | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [新しいMicrosoft Edge](#introducing-the-new-microsoft-edge)  | 新しいChromiumベースのMicrosoft Edgeは、新しいHoloLens 2。 | エンド ユーザー | 
[WebXR および 360 ビューアー](#webxr-and-360-viewer) | イマーシブ Web エクスペリエンスと 360 ビデオ再生をお試しください。 | エンド ユーザー | 
[新設定アプリ](#new-settings-app) | レガシ 設定アプリは、新しい機能と設定で更新されたバージョンに置き換え中です。 | エンド ユーザー |
[色の調整を表示する](#display-color-calibration) | 表示する別の色プロファイルを選択HoloLens 2します。 | エンド ユーザー |
[既定のアプリ ピッカー](#default-app-picker) | ファイルまたはリンクの種類ごとに起動するアプリを選択します。 | エンド ユーザー |
[アプリごとのボリュームコントロール](#per-app-volume-control) | システム ボリュームとは独立してアプリ レベルのボリュームを制御します。 | エンド ユーザー |
[Web アプリをインストールする](#install-web-apps) | 新しいブラウザーを使用HoloLens 2、Microsoft Office Web アプリを Microsoft Edgeします。 | エンド ユーザー |
[スワイプして入力する](#swipe-to-type) | ホログラフィック キーボードで指のヒントを使用して単語を "スワイプ" します。 | エンド ユーザー |
[[スタート] の [電源] メニュー](#power-menu-from-start) | [スタート] メニューで、デバイスを再起動HoloLensシャットダウンします。 | エンド ユーザー |
[[サインイン] 画面に表示される複数のユーザー](#multiple-users-listed-on-sign-in-screen) | [サインイン] 画面に複数のユーザー アカウントを表示します。 | エンド ユーザー |
[USB-C 外部マイクのサポート](#usb-c-external-microphone-support) | アプリやアプリの USB-C マイクを使用Remote Assist。 | エンド ユーザー |
[キオスクのビジター自動ログオン](#visitor-auto-logon-for-kiosks) | キオスク モードでビジター アカウントの自動ログオンを使用できます。 | IT 管理者 |
[キオスク モードの新しいアプリの新しい AUMID](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | 新しい 設定 Edge アプリ用の AUMID。 | IT 管理者 |
[キオスク モードのエラーの引き渡しの改善](#kiosk-mode-behavior-changes-for-handling-of-failures) | キオスク モードでは、空のスタート メニューの前にグローバル割り当てアクセスが見えます。 | IT 管理者 |
[ページの可視性のための新しい設定URIs](#new-settings-uris-for-page-settings-visibility) | 20 以上の新しい SettingsURIs for 設定/PageVisibilityList ポリシー。 | IT 管理者 |
[フォールバック診断の構成](#configuring-fallback-diagnostics-via-settings-app) | アプリのフォールバック診断動作設定設定します。 | IT 管理者 |
[近くのデバイスと共有する](#share-things-with-nearby-devices) | ファイルまたは URL を PC にHoloLensファイルまたは URL を共有します。 | すべて |
[新しい OS 診断トレース](#new-os-diagnostic-traces) | OS の更新設定の新しいトラブルシューティング ツール。 | IT 管理者 |
[配信の最適化 プレビュー](#delivery-optimization-preview) | 複数のデバイスからダウンロードする帯域幅の消費HoloLens減らします。 | IT 管理者 |

関連するリリース ノートを確認します。

- [HoloLens Emulator アーカイブにアクセスする](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>新しい機能のMicrosoft Edge

![レガシ Microsoft Edgeロゴから新しいロゴMicrosoft Edgeアニメーション](images/new-edge.gif)

新しいMicrosoft Edge[は](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/)、Chromiumオープンソース プロジェクトを採用して、顧客との互換性を向上し、Web 開発者向けの Web の断片化を減らします。

> [!IMPORTANT]
> この新しいMicrosoft Edgeは、新しいリリースMicrosoft Edgeサポートされなくなったレガシ バージョンを[自動的に置](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/)き換える機能です。

![新しいMicrosoft Edgeスクリーンショット](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>新しいアプリケーションを起動Microsoft Edge

新しい Microsoft Edge ![新しいMicrosoft Edgeアイコン](images/new_edge_logo.png) (青と緑のスワイル アイコンで表されます) は、スタート メニュー にピン留めされ、Web リンクをアクティブ化すると自動的に起動します。

> [!NOTE]
> 新しいアプリを Microsoft Edge初めてHoloLens 2すると、設定とデータはレガシ アカウントからインポートMicrosoft Edge。 新しい Microsoft Edge を起動した後もレガシ Microsoft Edge を引き続き使用する場合、その新しいデータはレガシ Microsoft Edge から新しい Microsoft Edge に同期されません。

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>新しいポリシーのポリシー設定を構成Microsoft Edge

この新しいMicrosoft Edgeでは、IT 管理者は、従来のアプリケーションで以前に使用していたよりも、HoloLens 2 に対するブラウザー ポリシーのはるかに広範なセットを提供Microsoft Edge。

新しいサービスのポリシー設定の管理の詳細については、次のリソースを参照Microsoft Edge。

- [次のMicrosoft Edgeポリシー設定を構成Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Microsoft Edge 従来版ポリシー マッピングMicrosoft Edgeする方法](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome を使用Microsoft Edgeポリシー マッピング](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- 完全[なMicrosoft Edge Enterpriseドキュメント](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> 新しい Microsoft Edge でサポートされているブラウザー ポリシーの量が多いので、チームは新しい各ポリシーが HoloLens 2 で動作する保証を受けHoloLens 2。 ただし、以前に Microsoft Edge でサポートされている各レガシ Microsoft Edge ポリシーと同等の新しい HoloLens 2 を想定してテストし、確認しました。 ポリシー[マッピングMicrosoft Edge 従来版をMicrosoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) Microsoft Edgeして、HoloLens 2 で使用していた各レガシ Microsoft Edge ブラウザー ポリシーと同等の新しい Microsoft Edge を見つける方法に関するページを参照してください。
>
> 次の 2 つ以上の新Microsoft Edgeポリシーは、次の *2* つで動作HoloLens 2。
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>新しいアプリケーションからMicrosoft Edge必要HoloLens 2

新しい Microsoft Edge は、新しい UWP アダプター レイヤーを備え、HoloLens 2 のような UWP 専用デバイスで実行できるネイティブ Win32 アプリなので、一部の機能はすぐには使用できない場合があります。 今後数か月間に新しいシナリオと機能をサポートする予定なので、この領域で最新の情報を確認してください。

**想定されるシナリオと機能:**
- 初回実行エクスペリエンス、プロファイルへのサインイン、同期
- Web サイトがレンダリングされ、期待どおりに動作する必要がある
- ほとんどのブラウザー機能 (お気に入り、履歴など) は期待した通りに動作する必要があります
- ダーク モード
- デバイスへの Web アプリのインストール
- 拡張機能のインストール (拡張機能が正常に機能しない拡張機能を使用している場合は、お知HoloLens 2)
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
- アクティブなウィンドウとMicrosoft Edgeすると、他の 2D アプリ ウィンドウが予期せず非アクティブになる可能性があります。 これらのウィンドウは、もう一度操作することで再アクティブ化できます。

#### <a name="microsoft-edge-insider-channels"></a>Microsoft EdgeInsider チャネル

このMicrosoft Edgeチームは、Edge Insider コミュニティで 3 つのプレビュー チャネル (ベータ、開発、カナリア) を利用できます。 プレビュー チャネルをインストールしても、リリースされたバージョンの Microsoft Edge は HoloLens 2 にアンインストールされません。また、複数の HoloLens 2 を同時にインストールできます。 

Edge Insider コミュニティ[Microsoft Edge詳細については、Microsoft Edge Insider](https://www.microsoftedgeinsider.com)のホームページを参照してください。 さまざまな Edge Insider チャネルの詳細と使用を開始するには、Edge Insider のダウンロード [ページを参照してください](https://www.microsoftedgeinsider.com/download)。

HoloLens 2 に Microsoft Edge Insider チャネルをインストールする方法はいくつかあります。

**デバイスへの直接インストール (現時点では管理されていないデバイスでのみ利用可能)**
  1. HoloLens 2 で、[エッジ Insider のダウンロードページ](https://www.microsoftedgeinsider.com/download)にアクセスします。
  1. インストールする Edge Insider channel の [ **HoloLens 2 のダウンロード**] ボタンを選択します。
  1. ダウンロードした msix ファイルをエッジダウンロードキューから起動するか、デバイスの "ダウンロード" フォルダー (エクスプローラーを使用) から起動します。
  1. [アプリのインストーラー](app-deploy-app-installer.md) が起動します。
  1. **[インストール]** ボタンを選択します。
  1. インストールが正常に終了すると、スタートメニューの [**すべてのアプリ**] の一覧に個別のエントリとして Microsoft Edge Beta、Dev、またはカナリアが表示されます。

**Windows デバイスポータルを使用して PC 経由でインストールする (HoloLens 2 で [開発者モード](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)を有効にする必要があります)**
  1. PC で、 [Edge Insider ダウンロードページ](https://www.microsoftedgeinsider.com/download)にアクセスします。
  1. インストールする Edge Insider channel の [Download for Windows 10] \ (ダウンロード用にダウンロード \) ボタンの横に **あるドロップダウン矢印ボタン** を選択します。
  1. ドロップダウンメニューの [ **HoloLens 2** ] を選択します。
  1. Msix ファイルを PC の "ダウンロード" フォルダー (または簡単に見つけられる別のフォルダー) に保存します。
  1. PC で[Windows デバイスポータル](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)を使用して、ダウンロードした msix ファイルを HoloLens 2 にインストールします。
  1. インストールが正常に終了すると、スタートメニューの [**すべてのアプリ**] の一覧に個別のエントリとして Microsoft Edge Beta、Dev、またはカナリアが表示されます。

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>WDAC を使用した新しい Microsoft Edge のブロック

新しい Microsoft Edge アプリをブロックするために、 [WDAC ポリシー](windows-defender-application-control-wdac.md)を更新することを検討している IT 管理者は、ポリシーに次のものを追加する必要があります。

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>新しい Microsoft Edge のエンドポイントを管理する

環境によっては、考慮として考慮する必要があるネットワークの制限がある場合があります。 新しいエッジでスムーズにエクスペリエンスを確保するには、[これらの Microsoft エンドポイントを有効に](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)してください。

現在使用できるエンドポイントの詳細については、 [HoloLens を](hololens-offline.md)参照してください。

### <a name="install-web-apps"></a>Web アプリのインストール
 > [!Note]
>[Windows Holographic バージョン 21h1](hololens-release-notes.md#windows-holographic-version-21h1)では、Office web アプリが事前にインストールされなくなりました。

新しいエッジを使用して、Microsoft Store アプリと共に web アプリをインストールできます。 たとえば、SharePoint または OneDrive でホストされているファイルを表示および編集するために Microsoft Office web アプリをインストールできます。 Office web アプリをインストールするには、にアクセスして https://www.office.com 、**利用可能なアプリ** を選択するか、アドレスバーに Office のボタンを **インストール** します。 [ **インストール** ] を選択して確認します。

> [!IMPORTANT]
> Office web アプリの機能は、HoloLens 2 がアクティブなインターネット接続を使用している場合にのみ使用できます。

### <a name="webxr-and-360-viewer"></a>WebXR と360ビューアー

新しい Microsoft Edge には、WebXR のサポートが含まれています。これは、イマーシブ web エクスペリエンスを作成するための新しい標準です (webvr を置き換える)。 多くのイマーシブ web エクスペリエンスは、VR を念頭に置いて設計されています (これはビューのフィールドを仮想環境に置き換えるものです) が、これらのエクスペリエンスは HoloLens 2 でもサポートされています。 また、WebXR standard では、物理環境を使用する、拡張された、mixed reality のイマーシブ web エクスペリエンスが可能になります。 開発者が WebXR を使用してより多くの時間を費やしている場合は、新たに強化された新しい現実を想定して、HoloLens 2 のお客様がお試しください。

360 Viewer 拡張機能は WebXR 上に構築され、HoloLens 2 に新しい Microsoft Edge と共に自動的にインストールされます。 この web 拡張機能を使用すると、360度のビデオで自分自身をこちらすることができます。 YouTube では、最大で360のビデオが選択されているので、ここから始めることをお勧めします。

#### <a name="how-to-use-webxr"></a>WebXR の使用方法

1. WebXR のサポートがある web サイトに移動します。
1. Web サイトの [ **Enter** ] をクリックします。 このボタンの位置と視覚表現は、web サイトごとに異なりますが、次のようになります。

    ![「VR ボタンの例」と入力します。](images/75px-enter-vr.png)

1. 特定のドメインで WebXR experience を初めて起動しようとすると、ブラウザーでは、イマーシブビューの入力に同意するように求めるメッセージが表示されます。 [ **許可**] を選択します。
1. [HoloLens 2 ジェスチャ](hololens2-basic-usage.md#the-hand-tracking-frame)を使用して、エクスペリエンスを操作します。
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
- 360 YouTube 以外の web サイトからのビデオが想定どおりに動作しないことがあります。

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>WebXR と360ビューアーに関するフィードバックの提供

新しい Microsoft Edge の **フィードバックの送信** 機能を使用して、フィードバックとバグをチームと共有してください。

### <a name="new-settings-app"></a>新しい設定アプリ

今回のリリースでは、設定アプリの新しいバージョンが導入されています。 新しい設定アプリには、サウンド、電源 & スリープ、ネットワーク & インターネット、アプリ、アカウント、コンピューターの簡単操作などの領域における HoloLens 2 の新機能と拡張設定が含まれています。

> [!NOTE]
> 新しい設定アプリは従来の設定アプリとは別であるため、以前に環境に配置した設定の windows は、更新時に削除されます。

![新しい設定アプリのホームページ](images/new-settings-app.png)

**新機能と設定**
- 設定検索: キーワードまたは設定の名前を使用して、設定ホームページから設定を検索します。
- システム > サウンド:
  - 入出力オーディオデバイス: 入力と出力のオーディオデバイスを個別に選択します (たとえば、Bluetooth ヘッドホンを使用してオーディオをリッスンするか、オーディオ入力に USB C マイクを使用します)。
    > [!NOTE]
    > Bluetooth のマイクは、HoloLens 2 ではサポートされていません。
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
- 以前に配置した設定ウィンドウは削除されます (上のメモを参照)。
- 設定アプリでは、デバイスの名前を変更できなくなります。 IT 管理者は、デバイス名テンプレートまたは MDM [devdetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/dnscomputername ノード[HoloLens 2 の Windows 自動操縦](https://docs.microsoft.com/hololens/hololens2-autopilot)装置を使用して、デバイスの名前を変更できます。
- イーサネットのページには、常に仮想イーサネットデバイス ("UsbNcm") が表示されます。
- 新しい Microsoft Edge のバッテリ使用量は、UWP アダプターレイヤーによってサポートされている Win32 デスクトップアプリケーションの性質上、正確ではない可能性があります (近日対応予定の修正プログラムはありません)。

#### <a name="display-color-calibration"></a>色の調整を表示する



この新しい設定では、HoloLens 2 表示に使用する代替カラープロファイルを選択できます。 これにより、特にディスプレイの明るさが低いレベルで、色が正確に表示される場合があります。 画面の色の調整は、設定アプリの [システム > の調整] ページで確認できます。

> [!NOTE]
> この設定により、ディスプレイファームウェアに新しいカラープロファイルが保存されるため、デバイスごとの設定になります (各ユーザーアカウントに固有ではありません)。

##### <a name="how-to-use-display-color-calibration"></a>画面の色の調整を使用する方法

1. アプリを **起動設定、System** > **Calibration に移動します**。
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
> - 表示色の調整は、必要に設定から再び実行できます
> - デバイス上の誰かが以前に設定を使用してカラー プロファイルを変更した場合、最新の変更の日付/時刻が [設定 ページに反映されます
> - 表示色の調整を再び実行すると、以前に保存されたカラー プロファイルが強調表示され、プロファイル 0 は表示されません (プロファイル 0 はディスプレイの元のカラー プロファイルを表します)。
> - ディスプレイの元のカラー プロファイルに戻す場合は、設定 ページから行います (カラー プロファイルをリセットする方法[を参照してください](#how-to-reset-color-profile))。

##### <a name="how-to-reset-color-profile"></a>カラー プロファイルをリセットする方法 

HoloLens 2 に保存されたカスタム カラー プロファイルに問題が生じ場合は、デバイスの元のカラー プロファイルを復元できます。
1. アプリを **起動設定、System** > **Calibration に移動します**。
1. [ **色の調整の表示]** で、[既定の色 **プロファイルにリセット] ボタンを選択** します。
1. ダイアログ ボックスが開いたら、再起動して変更を適用する準備ができたらHoloLens 2を選択します。

#### <a name="top-display-color-calibration-known-issues"></a>上位の表示色調整に関する既知の問題

- [設定] ページで、カラー プロファイルが最後に変更された日時を示すステータス文字列は、そのページのページを再度読み込むまで設定。
    - 対応策: 別の設定ページを選択し、[調整] ページを再選択します。

#### <a name="default-app-picker"></a>既定のアプリ ピッカー

ハイパーリンクをアクティブにするか、複数のインストール済みアプリを含むファイルの種類を開いた場合、新しいウィンドウが開き、ファイルまたはリンクの種類を処理するインストール済みアプリを選択するように求めるメッセージが表示されます。 このウィンドウでは、選択したアプリでファイルまたはリンクの種類として "Once" または "Always" を処理することもできます。

[常に] を選択した後で、特定のファイルまたはリンクの種類を処理するアプリを変更する場合は、 [アプリ] で保存した既定値を **設定 >できます**。 ページの下部までスクロールし、[ファイルの種類の既定のアプリ] または [リンクの種類の既定のアプリ] の下にある [クリア] ボタンを選択します。 デスクトップ PC での同様の設定とは異なり、個々のファイルの種類の既定値をリセットできない。

#### <a name="per-app-volume-control"></a>アプリごとのボリュームコントロール

このビルドWindows、ユーザーは各アプリのボリューム レベルを手動で調整できます。 これにより、ユーザーは必要なアプリに集中したり、複数のアプリを使用する場合に聞き取りを向上することができます。 別のアプリでリモート アシスタンスのために別のユーザーを呼び出しながら、あるアプリのボリュームをダウンする必要があるなどです。

個々のアプリのボリュームを設定するには、[システム サウンド] 設定に移動し、[詳細なサウンド オプション]**で**[アプリのボリュームとデバイスの基本設定]  ->    ->  **を選択します**。<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>スワイプして入力する

一部のお客様は、入力する予定の単語の形をスワイプすることで、仮想キーボードで "入力" する方が速く見つかり、ホログラフィック キーボード用にこの機能をプレビューしています。 ホログラフィック キーボードの平面から指の先を渡し、単語の形をスワイプし、キーボードの平面から指のヒントを引き出して、一度に 1 つの単語をスワイプできます。 単語間でキーボードから指を削除することで、スペース バーを押す必要なく、フォローアップ ワードをスワイプできます。 キーボードで指の動きの後にスワイプ の道が見える場合は、機能が動作しているのがわかっています。

この機能は、(携帯電話のディスプレイとは異なり) 指に対する抵抗を感じないホログラフィック キーボードの性質上、使用とマスターが難しい場合があります。 

### <a name="power-menu-from-start"></a>[スタート] の [電源] メニュー

ユーザーがデバイスをサインアウト、シャットダウン、再起動できる新しいメニュー。 システム更新プログラムがHoloLens スタート画面を示すインジケーター。

#### <a name="how-to-use"></a>使用方法

1. Start ジェスチャを[HoloLens スタート画面、または "開始](hololens2-basic-usage.md#start-gesture)" と入力して、スタートに移動。

2. ユーザー プロファイルの画像の横にある省略記号アイコン (...) に注意してください。<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. 手または音声コマンド "Power" を使用して、ユーザー プロファイルの画像を選択します。

4. メニューが表示され、デバイスのサインアウト、再起動、シャットダウンのオプションが表示されます。<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. メニュー オプションを選択して、サインアウト、再起動、またはシャットダウンHoloLens。 デバイスが 1 つの Microsoft アカウント (MSA) またはローカル アカウント に設定されている場合は、[サインアウト [] オプションを使用できない場合があります](hololens-identity.md)。

6. メニューを閉じるには、他の場所にタッチするか、[開始] ジェスチャスタート メニューを閉じる必要があります。

#### <a name="update-indicator"></a>インジケーターの更新

更新プログラムが使用可能な場合は、更新プログラムが再起動によってインストールされるという省略記号アイコンが点灯します。更新プログラムの存在を反映するようにメニュー オプションも変更されます。<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>[サインイン] 画面に表示される複数のユーザー

以前は、[サインイン] 画面には、最近サインインしたユーザーと "その他のユーザー" エントリ ポイントだけが表示されました。 複数のユーザーがデバイスにサインインしている場合は、これでは十分ではないというお客様からのフィードバックを受け取っています。 それでも、ユーザー名などを再入力する必要があります。

この Windows ビルドで導入された[PIN エントリ] フィールドの右側にある [その他のユーザー] を選択すると、[サインイン] 画面に、以前にデバイスにサインインしたユーザーが複数表示されます。 これにより、ユーザーは自分のユーザー プロファイルを選択し、自分の資格情報を使用Windows Helloできます。 [アカウントの追加] ボタンを使用して、この [その他のユーザー] ページからデバイスに新しい **ユーザーを追加** することもできます。

[その他のユーザー] メニューの [その他のユーザー] ボタンには、デバイスにサインインした最後のユーザーが表示されます。 このボタンを選択すると、このユーザーのサインイン画面に戻ります。

![サインイン画面の既定値](./images/multiusers1.jpg)

<br>

![他のユーザーのサインイン画面](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C 外部マイクのサポート

> [!IMPORTANT]
> USB マイクを **接続すると、入力デバイス として自動的に設定されません**。 USB-C の一連のヘッドセットを接続すると、ユーザーは、ヘッドセットのオーディオが自動的にヘッドセットにリダイレクトされるのを確認しますが、HoloLens OS では、他の入力デバイスよりも内部マイク 配列の優先順位が優先されます。 **USB-C マイクを使用するには、次の手順に従います。**

ユーザーは、[サウンド設定] パネルを使用して USB-C 接続外部マイク **を** 選択できます。 USB-C マイクは、通話や録音などに使用できます。

アプリを開 **設定** システム サウンド ]**を**  >  **選択します**。

![サウンド 設定](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> を使用して外部マイクを **Remote Assist、** ユーザーは [サウンド デバイスの管理] ハイパーリンクをクリックする必要があります。
>
> 次に、ドロップダウンを使用して、外部マイクを [既定] または [通信の既定値 **]** **に設定します。** [既定] **を** 選択すると、外部マイクがどこでも使用されます。
>
> [**通信の既定値]** を選択すると、外部マイクは Remote Assist や他の通信アプリで使用されますが、HoloLens マイク 配列は他のタスクにも引き続き使用できます。

![サウンド デバイスを管理する](images/usbc-mic-2.png)

<br>

![マイクの既定値を設定する](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>マイクのBluetoothについてはどうですか?

残念Bluetooth、マイクは現在、デバイスでHoloLens 2。

#### <a name="troubleshooting-usb-c-microphones"></a>USB-C マイクのトラブルシューティング

一部の USB-C マイクでは、マイクとスピーカーの両方として誤って報告される *点に* 注意してください。 これはマイクの問題であり、マイクには問題HoloLens。 これらのマイクの 1 つを電源に接続HoloLens音が失われる可能性があります。 さいわい、簡単な修正があります。  

**[設定** サウンド] で、組み込みのスピーカー (アナログ機能オーディオ ドライバー) を既定のデバイス として明示的  ->    ->  **に設定します**。  HoloLensマイクが削除され、後で再接続された場合でも、この設定を覚えておく必要があります。

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
| MixedReality/VisitorAutoLogon  | 訪問者がキオスクに自動ログオンすることを許可します   | 1 (はい)、0 (いいえ、既定値)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>キオスクモードでの新しい設定とエッジアプリの使用

[キオスク](hololens-kiosk.md)にアプリを含めると、多くの場合、It 管理者はアプリをキオスクに追加しますが、アプリユーザーモデル ID (AUMID) を使用します。 設定アプリと Microsoft Edge アプリは両方とも新しいアプリと見なされるため、これらのアプリで AUMIDs を使用する古いアプリキオスクとは異なるものとして、新しい AUMID を使用するように更新する必要があります。

新しいアプリを含めるようにキオスクを変更する場合は、新しい AUMID にを追加することをお勧めします。 これにより、ユーザーが OS を更新するときに簡単に移行できるようになります。また、意図したとおりにキオスクを使用し続けるために新しいポリシーを受け取る必要はありません。

| アプリ                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| 古い設定アプリ       | HolographicSystemSettings_cw5n1h2txyewy!アプリケーション            |
| 新しい設定アプリ       | BAEAEF15-9BAB-47 FC-800B-ACECAD2AE94B_cw5n1h2txyewy!アプリケーション |
| 古い Microsoft Edge アプリ | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| 新しい Microsoft Edge アプリ | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>キオスクモードでのエラー処理の動作変更

以前のビルドでは、グローバルに割り当てられたアクセスと AAD グループメンバーの両方を組み合わせたキオスク構成がデバイスにある場合、AAD グループのメンバーシップの確認に失敗すると、ユーザーには [スタート] メニュー[に表示](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)されないものが表示されます。

この Windows リリース以降、AAD グループキオスクモードでのエラーが発生した場合、キオスクエクスペリエンスはグローバルキオスク構成 (存在する場合) にフォールバックします。

### <a name="new-settings-uris-for-page-settings-visibility"></a>ページ設定表示用の新しい設定 uri

[Windows Holographic のバージョン 20h2](hololens-release-notes.md#windows-holographic-version-20h2)では、設定アプリ内で表示されるページを制限する[設定/PageVisibilityList ポリシー](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)を追加しました。 PageVisibilityList は、IT 管理者がシステム設定アプリ内の特定のページを表示またはアクセスできないようにするか、指定されたものを除くすべてのページに対して実行することを IT 管理者に許可するポリシーです。

[ページ設定表示](settings-uri-list.md)にアクセスする場合は、この CSP を使用する手順と、以前のリリースで使用可能な uri の一覧を確認できます。

ここでは、IT 管理者が管理できる、使用可能な設定 uri の一覧について説明します。 これらの Uri の一部は、新しい設定アプリ内で新しく利用できる領域用です。 設定/PageVisibilityList ポリシーを使用している場合は、次の一覧を確認し、許可または禁止されているページを必要に応じて調整します。

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
| システム > Storage > Storage Sense の構成         | `ms-settings:storagepolicies`                      |
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

現在設定アプリでは、ユーザーは[フォールバック診断](hololens-diagnostic-logs.md)の動作を構成できます。 設定アプリで、プライバシーに  ->  **関するトラブルシューティング** ページに移動し、この設定を構成します。

> [!NOTE]
> デバイスに MDM ポリシーが構成されている場合、ユーザーはその動作をオーバーライドすることはできません。  

### <a name="share-things-with-nearby-devices"></a>近くのデバイスとの共有

pc とその他の HoloLens 2 デバイスの両方を含めて、Windows 10 デバイスの近くで共有できます。   ->    ->  HoloLens から PC にファイルまたは url を共有するために設定システム **共有エクスペリエンス** で試してみることができます。 詳細については、 [Windows 10 で近くのデバイスと項目を共有](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)する方法を参照してください。

この機能は、 [接続/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)を介して管理できます。

### <a name="new-os-diagnostic-traces"></a>新しい OS 診断トレース

設定アプリ内の前のトラブルシューティングツールに加えて、新しいトラブルシューティングツールが追加されました。 OS 更新プログラム用の新しい設定アプリが追加されました。 **設定**  ->  **更新の &amp; セキュリティ**  >  **トラブルシューティング**  >  **Windows Update** に移動し、[**開始**] を選択します。 これにより、OS の更新に関する問題を再現しながら、IT またはサポートによるトラブルシューティングを容易にするために、トレースを収集することができます。

### <a name="delivery-optimization-preview"></a>配信の最適化のプレビュー

この HoloLens の更新により、Windows Holographic for Business は配信の最適化の設定を有効にして、複数の HoloLens デバイスからのダウンロードにかかる帯域幅の消費を削減します。 この機能と推奨されるネットワーク構成の詳細については、「 [Windows 10 更新プログラムの配信の最適化](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)」を参照してください。

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

- このプレビューでは、HoloLens サポートは OS の更新プログラムに限定されます。
- Windows Holographic for Business は、HTTP ダウンロードモードと、 [Microsoft 接続キャッシュエンドポイント](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)からのダウンロードのみをサポートしています。現時点では、ピアツーピアのダウンロードモードとグループの割り当ては、HoloLens デバイスではサポートされていません。
- HoloLens は、Windows Server Update Services エンドポイントの展開または配信の最適化をサポートしていません。
- トラブルシューティングを行うには、接続されているキャッシュサーバーの診断を使用するか、**設定**  >  **更新プログラム & セキュリティ** の  >   **トラブルシューティング**  >   **Windows Update** 経由で HoloLens に対して HoloLens でトレースを収集する必要があります。

### <a name="it-admin---update-checklist"></a>IT 管理者-更新プログラムのチェックリスト

このチェックリストは、現在のデバイス管理構成に影響を与える可能性がある、この機能更新プログラムに追加される新しい項目、または使用を開始する新機能を理解するのに役立ちます。

#### <a name="updates-to-kiosk-mode"></a>キオスクモードの更新プログラム

[**キオスクモードで新しいアプリの新しい AUMIDs を**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)✔️します。

以前にキオスクで 設定 アプリまたは Microsoft Edge アプリを使用していた場合は、これらのアプリを別のアプリ ID を使用する新しいアプリに置き換えました。 以下のキオスク モードで新しい [アプリの新しい AUMID を読み取る方法を強くお勧](#use-the-new-settings-and-edge-apps-in-kiosk-modes) めしています。 これにより、キオスクで引き続き設定アプリを使用するか、新しいアプリをMicrosoft Edgeできます。 これらの変更を今すぐ実行し、すべてのデバイスに展開して、更新時の移行をスムーズに行えます。

✔️ [**キオスクのビジター自動ログオン**](#visitor-auto-logon-for-kiosks): 

訪問者はキオスクに自動的にログインできます。 この動作は既定でオンになっていますが、管理および無効化できます。

✔️キオスク [**モードエラーの引き渡しの改善**](#kiosk-mode-behavior-changes-for-handling-of-failures):

サインインした AAD ユーザーの AAD グループ メンバーシップが正常に決定されない場合は、グローバル キオスク構成がスタート メニュー (存在する場合) に使用されます。それ以外の場合、ユーザーには空のスタート メニューが表示されます。 空のスタート メニューは直接設定できる構成ではありません。この新しい処理は、キオスクを使用している場合、構成に適用される場合や、割り当てられたアクセス構成に対して新しい調整を行う場合など、サポート部門に通知する必要がある場合があります。

#### <a name="updates-to-page-settings-visibility"></a>ページビューの可視性設定更新

✔️ [**の表示設定の新しい 設定 URI**](#new-settings-uris-for-page-settings-visibility)

現在 Page 設定[Visibility](settings-uri-list.md)を使用している場合は、許可またはブロックされている既存の URI を調整することができます。

#### <a name="updates-for-your-wdac-policy"></a>WDAC ポリシーの更新
✔️ WDAC を使用してMicrosoft Edgeブロックしていた場合は、WDAC ポリシーを更新する必要があります。 以下を確認し、提供されているサンプル コードを使用してください。
#### <a name="enable-new-endpoints-for-edge"></a>Edge の新しいエンドポイントを有効にする
✔️ プロキシやファイアウォールなどのネットワーク エンドポイントの構成を含むインフラストラクチャがある場合は、新しい Microsoft Edge アプリに対してこれらの新しいエンドポイントを有効にしてください。

#### <a name="newly-configurable-items"></a>新しく構成可能な項目

✔️ [診断の構成:](#configuring-fallback-diagnostics-via-settings-app)フォールバック診断を収集する場合と収集するユーザーを構成できます。

✔️[近くのデバイスと共有する](#share-things-with-nearby-devices): 近くの新しい共有機能を無効にできます。

✔️[のポリシー設定の](#configuring-policy-settings-for-the-new-microsoft-edge)構成: Microsoft Edgeで使用できる新しい構成を確認Microsoft Edge。

#### <a name="new-diagnostic-tool"></a>新しい診断ツール

✔️[新しい OS 診断トレース:](#new-os-diagnostic-traces)OS の更新に関連するログを収集します。

### <a name="improvements-and-fixes-in-the-update"></a>更新プログラムの機能強化と修正:

- [オフライン診断には、](hololens-diagnostic-logs.md#offline-diagnostics) シリアル番号と OS バージョンに関する追加のデバイス情報も含まれます。
- ランタイム プロビジョニング パッケージを使用した業務アプリケーションの展開に関する問題を修正します。
- ビジネス アプリケーションのインストール状態レポートの行に関する問題を修正します。
- デバイスのリセット全体での新しいアプリ パッケージの永続化に関する問題を修正します。
- 日本のお客様向け Edge で正しくないシンボルが入力される可能性がある問題を修正しました。
- Edge などのプレインストールされたアプリに関する OS 更新プログラムの回復性が向上します。 
- 更新プログラムのインストールに影響する更新プログラムの信頼性にMicrosoft Edge。 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>WindowsHolographic バージョン 20H2 – 2021 年 5 月の更新プログラム
- ビルド 19041.1146

更新プログラムの機能強化と修正:
- この毎月の品質更新プログラムには、重要な変更が含まれているのではなく、最新のビルドである Windows Holographic バージョン 21H1 をお試しください。

## <a name="windows-holographic-version-1903---may-2021-update"></a>WindowsHolographic バージョン 1903 - 2021 年 5 月の更新プログラム
- ビルド 18362.1110

更新プログラムの機能強化と修正:
- この毎月の品質更新プログラムには、重要な変更は含め "一切" は含め " ではありません。 **このビルドでは、毎月のサービス更新プログラム が受信されなくなりました**。 Holographic バージョン 21H1 の最新Windowsをお試しください。



## <a name="windows-holographic-version-20h2---april-2021-update"></a>WindowsHolographic バージョン 20H2 - 2021 年 4 月の更新プログラム
- ビルド 19041.1144

更新プログラムの機能強化と修正:

- ビジネス アプリケーションのインストール状態レポートの行に関する問題を修正します。

## <a name="windows-holographic-version-1903---april-2021-update"></a>WindowsHolographic バージョン 1903 - 2021 年 4 月の更新プログラム
- ビルド 18362.1108

更新プログラムの機能強化と修正:

- ローカル アカウントのパスワードを変更設定アプリがクラッシュする問題を修正します。


## <a name="windows-holographic-version-20h2---march-2021-update"></a>WindowsHolographic バージョン 20H2 - 2021 年 3 月更新
- ビルド 19041.1140

更新プログラムの機能強化と修正:

- AdvancedPhotoCapture または LowLagPhotoCapture を使用して HoloLens 2 で写真をキャプチャしているお客様は、写真がキャプチャされた後、最大 3 秒後にカメラの姿勢を取得できます。
- デバイス ポータル Service のメモリ リークを修正しました。この問題により、他のアプリケーションがメモリの割り当てに失敗する原因となるサービスによるメモリ使用量が増加しました。
- 段階的なロールアウトに登録されているユーザーがデバイスにサインインできない問題を修正しました。

## <a name="windows-holographic-version-1903---march-2021-update"></a>WindowsHolographic バージョン 1903 - 2021 年 3 月の更新プログラム
- ビルド 18362.1102

更新プログラムの機能強化と修正:

- デバイス ポータル Service のメモリ リークを修正しました。この問題により、他のアプリケーションがメモリの割り当てに失敗する原因となるサービスによるメモリ使用量が増加しました。

## <a name="windows-holographic-version-20h2---february-2021-update"></a>WindowsHolographic バージョン 20H2 - 2021 年 2 月更新
- ビルド 19041.1136

更新プログラムの機能強化と修正:

- デバイスの初期セットアップとストア アプリの更新に関する問題を修正します。
- 以降のリリースでのアップグレードとフライトに関する問題HoloLensします。
- デバイスから eSIM ルート ストアから未使用のプレインストール済み証明書HoloLens削除しました。

## <a name="windows-holographic-version-1903---february-2021-update"></a>WindowsHolographic バージョン 1903 - 2021 年 2 月更新
- ビルド 18362.1098

この毎月の品質更新プログラムには、重要な変更が含まれているのではなく、Windows Holographic バージョン 2004 の最新ビルドをお試しください。

## <a name="windows-holographic-version-20h2---january-2021-update"></a>WindowsHolographic バージョン 20H2 - 2021 年 1 月更新
- ビルド 19041.1134

更新プログラムの機能強化と修正:

- デバイス上に多数のユーザーがいて、起動時、再開中、ユーザー切り替え中のパフォーマンスが向上しました。
- 研究モード の arm32 サポートを [追加しました](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)。

## <a name="windows-holographic-version-1903---january-2021-update"></a>WindowsHolographic バージョン 1903 - 2021 年 1 月更新
- ビルド 18362.1091

この毎月の品質更新プログラムには、重要な変更が含まれているのではなく、Windows Holographic バージョン 2004 の最新ビルドをお試しください。

## <a name="windows-holographic-version-20h2--december-2020-update"></a>WindowsHolographic バージョン 20H2 – 2020 年 12 月の更新プログラム
- ビルド 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>HoloLens 2 経由でアプリを アプリ インストーラー

新しい **機能 (アプリ インストーラー)** を追加して、アプリケーションをデバイスにシームレスにインストールHoloLens 2しています。 この機能は、アン **マネージド デバイスでは既定でオンになります**。 企業の中断を防ぐために、現時点では、マネージド デバイスでアプリ インストーラー **を** 使用できません。  

次の条件に当てはまる場合、デバイスは "マネージド" と見なされます。
- MDM [登録済み](hololens-enroll-mdm.md)
- プロビジョニング パッケージ [を使用して構成する](hololens-provisioning.md)
- ユーザー [ID が](hololens-identity.md) Azure AD

開発者モードを有効にしたり、アプリを使用したりせずにアプリをインストールデバイス ポータル。  (USB 経由または Edge 経由で) Appx バンドルをデバイスにダウンロードし、エクスプローラー の Appx バンドルに移動するだけで、インストールを開始するように求めるメッセージが表示されます。  または、Web [ページ からインストールを開始します](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。  mdm の LOB アプリ展開機能を使用して Microsoft Store またはサイドロードからインストールするアプリと同様に、アプリは署名ツールでデジタル[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)署名する必要があります[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)。また、アプリを展開する前に、署名に使用される証明書が HoloLens デバイスによって信頼されている必要があります。

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

このフローをテストするには、[ユニバーサル サンプル Windowsサンプル GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)サンプル アプリを見つける必要があります。

を使用してアプリをインストール[するプロセスの詳細については、HoloLens 2 を使用してアプリ インストーラー。](app-deploy-app-installer.md)  

![以下を使用した MRTK のアプリ インストーラー](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>更新プログラムの機能強化と修正:

- 手の追跡では、以前に手が失われた可能性がある多くの新しいケースで追跡が維持されます。  これらの新しいケースの一部では、手のひらの位置だけがユーザーの実際の手に基づいて更新され続け、もう一方の関節は前の姿勢に基づいて推論されます。  この変更は、スラップ、スロー、傾斜、アプリの適用などの動きの追跡の一貫性を向上させるのに役立ちます。  また、手が表面に近い場合やオブジェクトを保持している場合にも役立ちます。  手の関節が推論されている場合 [、関節ごとの](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) 精度の値は 、"高" ではなく "近似" に設定されます。
- アカウントの PIN リセットで、Azure ADが表示される問題を修正しました。
- ET、Iris を設定アプリ、新しいユーザー、または通知トーストから起動すると、起動後の OOBE クラッシュがはるかに少なく表示される必要があります。
- ユーザーは、OOBE から正しいタイム ゾーンが出てくる必要があります。

## <a name="windows-holographic-version-1903--december-2020-update"></a>WindowsHolographic バージョン 1903 – 2020 年 12 月の更新プログラム
- ビルド 18362.1088

この毎月の品質更新プログラムには、特に重要な変更が含まれているのではなく、最新の Windows Holographic バージョン 20H2 – 2020 年 12 月の更新プログラムと、ビルドに追加された新しい アプリ インストーラー 機能をお試しください。


## <a name="windows-holographic-version-20h2"></a>WindowsHolographic バージョン 20H2
- ビルド 19041.1128

WindowsHolographic バージョン 20H2 が利用可能にされ、ユーザーや IT プロフェッショナルにHoloLens 2機能のセットが提供されます。 自動目の配置から、設定 の証明書マネージャー、キオスク モード機能の向上、および新しい Autopilot セットアップ機能まで。 この新しい更新により、IT チームは、HoloLens デバイスの構成と管理をきめ細かく制御し、ユーザーにさらにシームレスなホログラフィック エクスペリエンスを提供できます。 

この最新リリースは、バージョン 2004 の月次更新プログラムですが、今回は新機能を含めてお使いください。 メジャー ビルド番号は変わりません。Windows Update では、バージョン 2004 (ビルド 19041) への月次リリースが示されます。 [バージョン情報] 画面で [ビルド番号] を設定 >、利用可能な最新のビルド 19041.1128 以上を確認できます。 最新リリースに更新するには、アプリを開き、[設定 セキュリティの更新] &[更新プログラムの確認] をタップします。 更新プログラムを管理する方法の詳細についてはHoloLensページ[を参照してください](https://docs.microsoft.com/hololens/hololens-updates)。

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Holographic バージョン 20H2 Windowsの新機能  

| 機能                                              | 説明                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [自動目の位置のサポート](hololens-release-notes.md#auto-eye-position-support) | ユーザーが目の追跡の調整を行わずに、目の位置を積極的に計算します。   |
| [Certificate Manager](hololens-release-notes.md#certificate-manager)   | 新しい簡単な方法で、新しいアプリから証明書をインストール設定できます。     |
| [USB からの自動起動プロビジョニング](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | USB ドライブにパッケージをプロビジョニングすると、OOBE のプロビジョニング ページが自動的に表示されます。                                                         |
| [OOBE でのプロビジョニング パッケージの自動確認](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | プロビジョニング パッケージは、プロビジョニング ページから OOBE 中に自動的に適用されます。                                                         |
| [UI を使用しない自動プロビジョニング](hololens-release-notes.md#automatic-provisioning-without-using-ui) | プロビジョニングの自動起動と自動確認を組み合わせる方法。 |
| [Autopilot と接続のWi-Fiする](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | イーサネット アダプターを必要とせずにWi-Fiデバイスからオートパイロットを使用します。 |
| [Tenantlockdown CSP と Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | テナントの登録とポリシーが適用された後は、デバイスがリセットまたは再フラッシュされた場合にのみ、そのテナントにデバイスを登録できます。 |
| [グローバル割り当てアクセス](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | システム レベルでキオスクを適用し、すべてのユーザーに適用できる、複数のアプリ キオスク モードの新しい構成方法。                  |
| [マルチアプリ キオスクでアプリを自動起動する](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | 複数アプリキオスク モードにサインインするときに自動的に起動するアプリケーションを設定します。                                                        |
| [エラー処理のためのキオスク モードの動作の変更](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | キオスク モードの失敗に制限付きフォールバックが追加された。                                                                                                |
| [HoloLensポリシー](hololens-release-notes.md#hololens-policies)                                    | 新しいポリシー HoloLens。     |
| [オフライン キオスクAzure ADグループ メンバーシップをキャッシュする](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | 新しいポリシーを使用すると、ユーザーはグループ メンバーシップ キャッシュを使用して、設定された日数のキオスク モードをオフラインで使用できます。                                        |
| [デバイスの新しい制限ポリシー HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | デバイス管理ポリシーが新しく有効になっていると、HoloLens 2。                                                                                |
| [新しい電源ポリシーのHoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | 電源タイムアウト設定で新しくサポートされたポリシー。  |
| [ポリシーの更新](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | 更新プログラムの制御を許可する新しく有効にされたポリシー。           |
| [データ設定ページの表示を有効HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | アプリに表示されるページを選択設定ポリシー。             |
| [調査モード](hololens-release-notes.md#research-mode) | 調査モードを使用HoloLens 2。 |
| [記録長の増加](hololens-release-notes.md#recording-length-increased) | MRC の記録は 5 分に制限されなくなりました。 |
| [更新プログラムの機能強化と修正](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | 更新プログラムの追加の修正。   |

### <a name="auto-eye-position-support"></a>自動目の位置のサポート

このHoloLens 2、目の位置を使用すると、正確なホログラムの配置、快適な表示エクスペリエンス、および表示品質の向上が可能になります。 目の位置は、目の追跡計算の一部として内部的に計算されます。 ただし、エクスペリエンスで視線入力が必要ない場合でも、各ユーザーは視線追跡の調整を行う必要があります。

**自動目の位置 (AEP) を使用** すると、ユーザーの目の位置を計算する操作を必要としません。 自動目の位置は、ユーザーがデバイスを置いた瞬間から自動的にバックグラウンドで作業を開始します。 ユーザーが前の目の追跡の調整を行っていない場合、自動目の位置は、20 - 30 秒の処理時間の後、表示システムにユーザーの目の位置を提供し始める。 ユーザー データはデバイスに保持されないので、ユーザーが離してデバイスを再度起動した場合、またはデバイスが再起動またはスリープからウェイクアップした場合は、このプロセスが繰り返されます。

自動目の位置機能では、未調整のユーザーがデバイスに配置すると、システム動作がいくつか変更されます。 このコンテキストでは、未調整のユーザーは、以前にデバイスで目の追跡の調整プロセスを実行していないユーザーを指します。

| アクティブ なアプリケーション | 以前の動作 | Holographic Windowsバージョン 20H2 Update からの動作 |
|:-------------------|:-----------------|:-----------------------------------|
| 視線入力が有効でないアプリまたは Holographic Shell |[目の追跡の調整プロンプト] ダイアログが表示されます。 | プロンプトは表示されません。 |
| 視線入力が有効なアプリ | [目の追跡の調整プロンプト] ダイアログが表示されます。 | 視線追跡の調整プロンプトは、アプリケーションが視線入力ストリームにアクセスする場合にのみ表示されます。 |

ユーザーが視線入力が有効になっていないアプリケーションから視線入力データにアクセスするアプリケーションに切り替える場合は、調整プロンプトが表示されます。 

他のすべてのシステム動作は、現在のユーザーがアクティブな目追跡調整を行っていない場合と似ています。 たとえば、One-handed Start ジェスチャは有効になりません。 初期セットアップの Out-Of-Box-Experience に変更はありません。

目の視線入力データまたは非常に正確なホログラムの配置を必要とするエクスペリエンスの場合は、未調整のユーザーに視線追跡の調整を実行することをお勧めします。 これは、目の追跡の調整プロンプトから、またはスタート メニューから 設定 アプリを起動し **、[System > Calibration > Eye Calibration > Run eye calibration ]** を選択することでアクセスできます。

この情報は、後で他の調整情報 [と一緒に確認できます](hololens-calibration.md#auto-eye-position-support)。 

### <a name="certificate-manager"></a>証明書マネージャー

- 新しい証明書マネージャーを使用して、デバイスのセキュリティとコンプライアンスのための監査、診断、検証ツールが改善されました。 この機能を使用すると、商用環境で大規模に証明書をデプロイ、トラブルシューティング、検証できます。

Holographic Windows 20H2 では、アプリに証明書マネージャーをHoloLens 2 設定しています。 [Update **設定 > Security & Certificates]>移動します**。 この機能を使用すると、デバイス上の証明書を表示、インストール、削除する簡単で使い分け的な方法が提供されます。 新しい証明書マネージャーにより、管理者とユーザーは、デバイスのセキュリティと準拠を維持するために、監査、診断、検証ツールが改善されました。 

-   **監査:** 証明書が正しく展開されていることを検証する機能、または証明書が適切に削除されていることを確認する機能。 
-   **診断:** 問題が発生した場合は、デバイスに適切な証明書が存在する場合は、時間を節約し、トラブルシューティングに役立ちます。 
-   **検証:** 証明書が目的の目的に対応し、機能することを確認すると、特に商用環境では、大規模に証明書を展開する前に、かなりの時間を節約できます。

一覧内の特定の証明書をすばやく検索するには、名前、ストア、または有効期限で並べ替えるオプションがあります。 ユーザーは証明書を直接検索することもできます。 個々の証明書のプロパティを表示するには、証明書を選択し、[情報] を **クリックします**。 

証明書のインストールでは現在、.cer ファイルと .crt ファイルがサポートされています。 デバイス所有者は、ローカル コンピューターと現在のユーザーに証明書をインストールできます。 他のすべてのユーザーは、現在のユーザーにのみインストールできます。 ユーザーは、UI から直接インストールされた証明書設定できます。 証明書が他の方法でインストールされている場合は、同じメカニズムでも削除する必要があります。

#### <a name="to-install-a-certificate"></a>証明書をインストールするには: 

1.  Connect PC HoloLens 2接続します。
1.  インストールする証明書ファイルを、自分のコンピューター上の場所にHoloLens 2。
1.  [App 設定 **Update > & Security > 証明書**] に移動し、[証明書のインストール] を選択します。
1.  [ **ファイルのインポート]** をクリックし、証明書を保存した場所に移動します。
1.  [ストア **の場所] を選択します**。
1.  [証明書 **ストア] を選択します**。
1.  **[インストール]** をクリックします。

これで、証明書がデバイスにインストールされます。

#### <a name="to-remove-a-certificate"></a>証明書を削除するには: 
1. [App 設定 **Update and Security > Certificates] に移動>します**。
1. 検索ボックスで名前で証明書を検索します。
1. 証明書を選択します。
1. [削除] **をクリックします。**
1. 確認を求められたら、 **[はい]** を選択します。

![設定 アプリの証明書ビューアー](images/certificate-viewer-device.jpg)

![証明書 UI を使用して証明書をインストールする方法を示す図](images/certificate-device-install.jpg)

この情報は、後で新 [しい [証明書マネージャー] ページで確認できます](certificate-manager.md)。

### <a name="auto-launch-provisioning-from-usb"></a>USB からの自動起動プロビジョニング

- OOBE 中にプロビジョニング パッケージを備えた USB ドライブが使用されている場合、ユーザーの操作を減らして自動化されたプロセス。

このリリースより前は、ユーザーは、ボタンの組み合わせを使用してプロビジョニングするために、OOBE 中にプロビジョニング画面を手動で起動する必要があります。 これで、ユーザーは USB ストレージ ドライブ上のプロビジョニング パッケージを使用して、ボタンの組み合わせをスキップできます。 

1. OOBE の最初の対話可能な瞬間にプロビジョニング パッケージを使用して USB ドライブを接続する
1. デバイスをプロビジョニングする準備ができたら、プロビジョニング ページが表示されたプロンプトが自動的に開きます。 

注: デバイスの起動中に USB ドライブが接続された状態の場合、OOBE は既存の USB ストレージ デバイスを列挙し、追加の USB ストレージ デバイスが接続されているのを監視します。

OOBE 中にプロビジョニング パッケージを適用する方法の詳細については、プロビジョニングに関するドキュメントHoloLens[参照](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)してください。

USB からの[自動起動プロビジョニングに関](hololens-provisioning.md#auto-launch-provisioning-from-usb)する追加情報については、プロビジョニングに関するドキュメントHoloLens参照してください。

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>OOBE でのプロビジョニング パッケージの自動確認
- [プロビジョニング パッケージ] ページが表示されている場合、ユーザーの操作を減らして自動プロセスを実行すると、一覧に表示されているすべてのパッケージが自動的に適用されます。

プロビジョニングのメイン画面が表示された場合、OOBE は、すべてのプロビジョニング パッケージの適用を自動的に開始する前に、10 秒をカウントダウンします。 ユーザーは、 [期待したパッケージを](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) 確認した後も、この 10 時間以内に確認または取り消しを行います。

### <a name="automatic-provisioning-without-using-ui"></a>UI を使用しない自動プロビジョニング
- プロビジョニングのためのデバイスの操作を減らした自動プロセスを組み合わせたもの。 

USB デバイスからのプロビジョニングの自動起動とプロビジョニング パッケージの自動確認を組み合わせることで、ユーザーはデバイスの UI を使用したり、デバイスを装着したりすることなく、HoloLens 2 デバイスを自動的にプロビジョニングできます。 複数のデバイスに対して同じ USB ドライブとプロビジョニング パッケージを引き続き使用できます。 これは、同じ領域に複数のデバイスを一度に展開する場合に便利です。 

1. [構成デザイナー を使用してプロビジョニング](hololens-provisioning.md)[パッケージWindows作成します](https://www.microsoft.com/store/productId/9NBLGGH4TX22)。 
1. パッケージを USB ストレージ ドライブにコピーします。
1. [19041.1361](https://aka.ms/hololens2previewdownload)[以降の](hololens-insider.md#ffu-download-and-flash-directions)ビルド にHoloLens 2をフラッシュします。 
1. Advanced [Recovery Companion で](https://www.microsoft.com/store/productId/9P74Z35SFRS8) デバイスのフラッシュが完了したら、USB-C ケーブルを取り外します。 
1. USB ドライブをデバイスに接続します。
1. デバイスが HoloLens 2 OOBE に起動すると、USB ドライブ上のプロビジョニング パッケージが自動的に検出され、プロビジョニング ページが起動します。
1. 10 秒後、デバイスによってプロビジョニング パッケージが自動的に適用されます。 

これでデバイスが構成され、[プロビジョニングに成功しました [] 画面が表示されます](hololens-provisioning.md#automatic-provisioning-without-using-ui)。

### <a name="using-autopilot-with-wi-fi-connection"></a>Autopilot と接続のWi-Fiする
- 接続されているデバイスで Autopilot が機能する機能を有効にすることで、ハードウェアのニーズを減らすイーサネットへの USB-C アダプターWi-Fi必要が取り除かれました。

OOBE 中に、Wi-Fi HoloLens 2接続すると、OOBE によってデバイスの Autopilot プロファイルが確認されます。 見つかった場合は、AAD 参加フローと登録フローの残りの部分を完了するために使用されます。 つまり、USB-C または Wi-Fi から USB-C アダプターへのイーサネットの使用は要件ではなくなりましたが、OOBE の開始時に提供されている場合は引き続き機能します。 デバイスの[Autopilot の詳細については、HoloLens 2してください](hololens2-autopilot.md)。

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP と Autopilot
- デバイスのリセットまたは再フラッシュを使用しても、デバイスをテナントにロックすることで、組織のテナント上のデバイスを保持します。 プロビジョニングを介した でのアカウントの作成を禁止することで、セキュリティを強化します。 

HoloLens 2デバイスでは[、Holographic バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2)のWindows TenantLockdown CSP がサポートされます。 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)CSP を使用HoloLens 2 Autopilot のみを使用して MDM 登録に関連付けできます。 tenantLockdown CSP の RequireNetworkInOOBE ノードが HoloLens 2 で true または false (最初に設定) の値に設定された後、再フラッシュや OS の更新などにもかかわらず、その値はデバイス上に残ります。 

tenantLockdown の CSP の RequireNetworkInOOBE ノードが HoloLens 2 で true に設定されると、OOBE は、ネットワーク接続後に Autopilot プロファイルが正常にダウンロードされて適用されるのを無期限に待機します。 

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

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>TenantLockdown が true に設定された後に、Autopilot プロファイルが HoloLensに割り当てられていない場合、OOBE の間に何が起こりますか? 
OOBE は Autopilot プロファイルがダウンロードされるのを無期限に待機し、次のダイアログが表示されます。 TenantLockdown の効果を削除するには、最初に Autopilot のみを使用してデバイスを元のテナントに登録する必要があります。また、TenantLockdown CSP によって導入された制限が削除される前に、前の手順で説明したように RequireNetworkInOOBE を設定解除する必要があります。 

![ポリシーがデバイスに適用される場合のデバイス内ビュー。](images/hololens-autopilot-lockdown.png)

この情報は [、Tenantlockdown CSP と Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)の下にある Autopilot の残りの部分と共に確認できます。

### <a name="global-assigned-access--kiosk-mode"></a>グローバル割り当てアクセス – キオスク モード
- システム レベルでキオスク モードを適用する新しいキオスク 方法を有効にすることで、キオスクの ID 管理を減らしました。

この新機能により、IT 管理者は、システム レベルで適用可能な複数のアプリ キオスク モード用に HoloLens 2 デバイスを構成できます。システム上の ID とのアフィニティは持たず、デバイスにサインインするすべてのユーザーに適用されます。 この新機能の詳細については、「グローバル割り当てアクセス キオスク[HoloLensを参照してください](hololens-global-assigned-access-kiosk.md)。

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

キオスクモードの適用中にエラーが発生した場合は、HoloLens [スタート] メニューのすべてのアプリケーションを表示するために使用されます。 Holographic バージョン20h2 でエラーが発生した場合は、次のように [スタート] メニューにアプリが表示されなくなり Windows ます。 

![キオスクモードが失敗したときにどのように表示されるかを示した画像。](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLensポリシー
- デバイスを管理するために作成された HoloLens 専用のデバイス管理オプション。 

Windows Holographic バージョン20h2 の HoloLens 2 デバイスに対して、新しい mixed reality ポリシーが作成されました。 新しい制御可能な設定には、明るさの設定、音量の設定、混合 reality キャプチャでのオーディオ記録の無効化、診断が収集されるタイミングの設定、AAD グループメンバーシップキャッシュなどがあります。  

| 新しい HoloLens ポリシー                                | 説明                                                                               | メモ                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 明るさのボタンを無効にして、押したときに明るさを変更しないようにします。       | 1 Yes、0 No (既定値)                                                |
| MixedReality\VolumeButtonDisabled                  | ボリュームボタンを無効にして、押しても音量を変更できないようにします。               | 1 Yes、0 No (既定値)                                                |
| MixedReality\MicrophoneDisabled                    | マイクを無効にして HoloLens 2 でオーディオの記録を実行できないようにします。                      | 1 Yes、0 No (既定値)                                                |
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
1. カスタム oma-uri ベースのデバイス構成を作成します。この構成では、このポリシー値が必要な日数 (> 0) に設定され、HoloLens デバイスに割り当てられます。 
    1. URI 値は、/Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays のように OMA-URI テキストボックスに入力する必要があります。
    1. 許容される最小値と最大値の間の値を指定できます。
1. HoloLens デバイスを登録し、両方の構成がデバイスに適用されていることを確認します。 
1. インターネットが利用可能なときにユーザー1のサインインを Azure AD し、ユーザーのサインインと Azure AD グループのメンバーシップが正常に確認されると、キャッシュが作成されます。 
1. これで Azure AD ユーザー1がオフライン HoloLens して、ポリシー値で X 日の日数が許可されている限り、キオスクモードで使用できるようになりました。 
1. 手順 4. と 5. は、他の Azure AD ユーザー N に対して繰り返すことができます。ここで重要なのは、Azure AD ユーザーは、少なくとも1回、キオスク構成の対象となる Azure AD グループのメンバーであることを確認できるように、インターネットを使用してデバイスにサインインする必要があるという点です。 
 
> [!NOTE]
> 手順 4. を実行すると Azure AD ユーザーに対して、"切断" 環境に記載されているエラー動作が発生します。 

### <a name="new-device-restriction-policies-for-hololens-2"></a>HoloLens 2 の新しいデバイス制限ポリシー
- プロビジョニングパッケージの追加や削除をブロックするなど、特定のデバイス管理ポリシーをユーザーが管理できるようにします。

新しく有効になったポリシーにより、HoloLens 2 デバイスの管理オプションを追加できるようになりました。 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

この2つの新しいポリシー Allowaddのパッケージと Allowremoveのパッケージは、 [一般的なデバイスの制限](hololens-common-device-restrictions.md)に追加されています。

> [!NOTE]
> [remotelock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)に関しては、HoloLens は/Vendor/MSFT/RemoteLock/Lock 構成のみをサポートします。 リセットや回復などの PIN を処理する構成はサポートされていません。

### <a name="new-power-policies-for-hololens-2"></a>HoloLens 2 の新しい電源ポリシー
- 電源ポリシーを使用してスリープまたはロックを HoloLens する場合のその他のオプション。 

これらの新しく追加されたポリシーにより、管理者はアイドルタイムアウトなどの電源状態を制御できるようになります。 個々のポリシーの詳細を確認するには、そのポリシーのリンクをクリックしてください。

|     ポリシードキュメントのリンク                |     メモ                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Windows 構成デザイナーで使用する値の例を次に示します。`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Windows 構成デザイナーで使用する値の例を次に示します。`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Windows 構成デザイナーで使用する値の例 (100)                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Windows 構成デザイナーで使用する値の例 (100)                                                                          |
|     [スタンドアロン](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows 構成デザイナーで使用する値の例を次に示します。`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows 構成デザイナーで使用する値の例を次に示します。`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

DisplayOffTimeoutOnBattery と DisplayOffTimeoutPluggedIn 用のこれら2つの新しいポリシーは、 [デバイスの一般的な制限](hololens-common-device-restrictions.md)に追加されています。

> [!NOTE]
> HoloLens 2 の一貫したエクスペリエンスを得るには、displayofftimeoutonbattery とスタンドアロンの両方の値が同じ値として設定されていることを確認してください。 DisplayOffTimeoutPluggedIn と StandbyTimeoutPluggedIn にも同じことが当てはまります。 最新のスタンバイの詳細については [、「表示、スリープ、休止状態のタイマー」](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) を参照してください。

### <a name="newly-enabled-update-policies-for-hololens"></a>HoloLens 用に新しく有効になった更新ポリシー
- 更新プログラムをインストールするとき、または [更新の一時停止] ボタンを無効にして更新を確認する方法の詳細。

これらの更新ポリシーは HoloLens 2 デバイスで有効になりました。
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

これらの更新ポリシーの詳細と HoloLens デバイスでの使用方法については、「 [HoloLens 更新プログラムの管理](hololens-updates.md)」を参照してください。

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>HoloLens 2 の設定ページ表示を有効にする
- 設定アプリの UI コントロールが向上しました。これは、限られたページの選択を示すために混同される可能性があります。

これで、IT 管理者がシステム設定アプリ内の特定のページを表示またはアクセスできないようにするか、指定されたページ以外のすべてのページに対して実行できるようにするポリシーが有効になりました。 この機能を完全にカスタマイズする方法については、下のリンクをクリックしてください。

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

HoloLens 2 でカスタマイズできるページ設定については、[設定の uri](settings-uri-list.md)に関するページを参照してください。 
 
![設定アプリで変更されているアクティブ時間のスクリーンショット](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>リサーチモード
研究モードでは、HoloLens 2 はコンピュータービジョン調査の potent ツールになります。 以前のエディションと比較して、HoloLens 2 のリサーチモードには次の利点があります。
-   HoloLens (第1世代) リサーチモードで公開されるセンサーに加えて、加速度計、ジャイロスコープ、磁力計などの imu センサーアクセスを提供するようになりました。
-   HoloLens 2 には、リサーチモードと共に使用できる新しい機能が用意されています。 具体的には、より充実した一連の実験を提供できる、明確な追跡 Api と視点追跡 Api へのアクセスを提供します。

研究者は、HoloLens デバイスでリサーチモードを有効にして、これらの外部に面しているすべての未加工のイメージセンサーストリームにアクセスできるようになりました。 HoloLens 2 のリサーチモードでは、加速度計、ジャイロスコープ、および磁力計の読み取りにもアクセスできます。 ユーザーのプライバシーを保護するために、未加工の視点を追跡するカメライメージは、リサーチモードでは使用できませんが、既存の Api を通じて目を見つめます。

詳細については、 [調査モードのドキュメント](https://docs.microsoft.com/windows/mixed-reality/research-mode) をご覧ください。

### <a name="recording-length-increased"></a>記録の長さが増加しました
お客様からのフィードバックにより、 [混合現実のキャプチャ](holographic-photos-and-videos.md)の記録長さが増加しています。 混合の現実のキャプチャは、既定では5分に制限されなくなりましたが、代わりに使用可能なディスク領域に基づいて最大記録長が計算されます。 デバイスは、ディスクの空き領域の最大80% まで、使用可能なディスク領域に基づいて、最大ビデオ記録期間を見積もります。

> [!NOTE]
> 次のいずれかが発生した場合、HoloLens は既定のビデオ記録の長さ (5 分) を使用します。
> - 推定最大記録期間は、既定の5分よりも小さくなっています。
> - 使用可能なディスク領域が、合計ディスク領域の20% 未満です。

完全な要件については、 [holographic の写真とビデオ](holographic-photos-and-videos.md#maximum-recording-length) のドキュメントを参照してください。 

### <a name="improvements-and-fixes-in-the-update"></a>更新プログラムの機能強化と修正:
- OOBE の他の画面がダークモードになりました。
- 詳細については、オンラインで最新のプライバシーに関する声明を参照してください。
- ユーザーがプロビジョニングパッケージを使用して VPN プロファイルをプロビジョニングできない問題に対処しました。
- VPN 接続のプロキシ構成の問題を修正しています。
- NCM for AllowUsbConnection の MDM による USB 機能の列挙を無効にするポリシーが更新されました。
- デバイスが[シングルアプリキオスク](hololens-kiosk.md)として設定されている場合に、HoloLens デバイスが Media Transfer Protocol (MTP) 経由でファイルエクスプローラーに表示されない問題に対処します。 MTP (および一般的な USB 接続) は、 [Allowusbconnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) ポリシーを使用して無効にすることもできます。
- スタートメニューのアイコンがキオスクモードで正しく拡大縮小された問題を修正しました。
- Azure AD グループを対象としたキオスクモードでの HTTP キャッシュの妨害が原因で発生する問題を修正します。
- 開発者モードを無効にしてから再度有効にしない限り、ユーザーがプロビジョニングパッケージで開発者モードを有効にした後に [ペアリング] ボタンを使用できない問題を修正しました。

## <a name="windows-holographic-version-1903---november-2020-update"></a>WindowsHolographic、バージョン 1903-2020 の11月の更新プログラム
- ビルド18362.1085

この月間品質更新プログラムには、重要な変更は含まれていません。最新の機能リリースビルド Windows Holographic、バージョン20h2 を試すことをお勧めします。

## <a name="windows-holographic-version-2004---october-2020-update"></a>WindowsHolographic、バージョン 2004-2020 更新プログラム
- ビルド19041.1124
 
更新プログラムの機能強化と修正:

- ランタイムシステム障害の原因となった不要なチェックを削除しました。

## <a name="windows-holographic-version-1903---october-2020-update"></a>WindowsHolographic、バージョン 1903-2020 更新プログラム
- ビルド18362.1081

この月間品質更新プログラムには、重要な変更は含まれていません。 Windows Holographic バージョン2004の最新のビルドを試すことをお勧めします。

## <a name="windows-holographic-version-2004---september-2020-update"></a>WindowsHolographic、バージョン 2004-9 月2020更新プログラム
- ビルド19041.1117

更新プログラムの機能強化と修正:

- package.appxmanifest に supports複数インスタンス = "true" が存在する場合に、アプリケーションのデバッグを Visual Studio できない問題に対処します。
- このリリースには、ネットワークプロキシ経由のインターネット検出の失敗に対処するための NCSI プロキシ検出修正が含まれています。 NCSI は、コンピュータープロキシとプロファイルごとのプロキシを使用して、インターネット接続を検出できます。 ユーザーごとのプロキシは、将来のリリースでは NCSI によってサポートされる予定です。
- ほとんどの Windows Mixed Reality デバイスでは、ユーザーのヘッドが前方にあるニュートラルな位置にあるときに、前方方向ベクトルが地面に平行になります。 ただし、以前のバージョンの HoloLens 2 では、ベクターを表示パネルに対して垂直方向に配置しています。これは、理想的な向きに対して数度下に傾斜します。 新しいバージョンの HoloLens 2 により、フォームファクター間のセマンティックの一貫性を確保するために、この修正が修正されました。
- 特定のシナリオでの追跡の損失を軽減する、手作業による追跡の堅牢性が向上しました。
- このリリースには、ビデオキャプチャの問題に寄与する可能性があるオーディオタイムスタンプの品質を向上させる修正が含まれています。

## <a name="windows-holographic-version-1903---september-2020-update"></a>WindowsHolographic、バージョン 1903-9 月2020更新プログラム
- ビルド18362.1079

更新プログラムの機能強化と修正:

- ほとんどの Windows Mixed Reality デバイスでは、ユーザーのヘッドが前方にあるニュートラルな位置にあるときに、前方方向ベクトルが地面に平行になります。 ただし、以前のバージョンの HoloLens 2 では、ベクターを表示パネルに対して垂直方向に配置しています。これは、理想的な向きに対して数度下に傾斜します。 新しいバージョンの HoloLens 2 により、フォームファクター間のセマンティックの一貫性を確保するために、この修正が修正されました。
- 特定のシナリオでの追跡の損失を軽減する、手作業による追跡の堅牢性が向上しました。

## <a name="windows-holographic-version-2004---august-2020-update"></a>WindowsHolographic、バージョン 2004-2020 年8月更新
- ビルド19041.1113

更新プログラムの機能強化と修正:

- 設定アプリは、ユーザーが虹彩登録または視線追跡の調整エクスペリエンスに従うことができなくなります。
- デバイスの名前を変更し、その他の操作 (ネットワークへの接続など) を実行する OOBE 中にプロビジョニングパッケージを適用すると、名前の変更によってデバイスの再起動後に他の操作を実行できないというバグが修正されています。
- 視覚的な品質を向上させるために、初期のデバイスセットアップフローの配色を変更しました。

## <a name="windows-holographic-version-1903---august-2020-update"></a>WindowsHolographic、バージョン 1903-2020 年8月更新
- ビルド18362.1074

この月間品質更新プログラムには、重要な変更は含まれていません。 Windows Holographic バージョン2004の最新のビルドを試すことをお勧めします。

## <a name="windows-holographic-version-2004---july-2020-update"></a>WindowsHolographic、バージョン 2004-2020 年7月更新
- ビルド19041.1109

更新プログラムの機能強化と修正:

- 開発者は、デバイスポータルにセキュリティで保護された接続が必要であることを有効または無効にすることを選択できます。
- OS の更新後にアプリケーションが起動する信頼性が向上しました。
- 既定の受信トレイの明るさを100% に変更しました。
- HoloLens 2 の Windows デバイスポータルでの HTTPS 転送に関する問題に対処します。

## <a name="windows-holographic-version-1903---july-2020-update"></a>WindowsHolographic、バージョン 1903-2020 年7月更新
- ビルド18362.1071

更新プログラムの機能強化と修正:

- Unity アプリケーションが紛失または取り戻しの追跡によって削除される可能性がある問題を修正しました。
- 特定のデバイスでハードウェアアクセラレータを使用して HoloLens Emulator を使用しながら、排他的な HoloLens アプリがシェルにクラッシュする原因となった問題を修正しました。
- HoloLens 2 の Windows デバイスポータルでの HTTPS 転送に関する問題に対処します。

## <a name="windows-holographic-version-2004---june-2020-update"></a>WindowsHolographic、バージョン 2004-6 月2020更新プログラム
- ビルド19041.1106

更新プログラムの機能強化と修正:

- カスタム MRC レコーダーでは、特定のプロパティの既定値が指定されていない場合、その既定値が新しくなりました。
  - *MRC ビデオ効果* で、次のようにします。
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - globalopacitycoefficient (0.9 (HoloLens) 1.0 (イマーシブヘッドセット)
  - *MRC オーディオ効果* で、次のようにします。
    - LoopbackGain (Windows デバイスポータルの Mixed Reality キャプチャページの現在の "アプリオーディオゲイン" 値)
    - マイクロ電話の利得 (Windows デバイスポータルの Mixed Reality キャプチャページの現在の "Mic オーディオゲイン" 値)
- 混合現実のキャプチャシナリオでオーディオ品質を向上させるバグを修正した。 具体的には、この修正によって、[ **スタート** ] メニューが表示されたときに、録音のオーディオ glitching が削除されます。
- 記録されたビデオにおけるホログラムの安定性が向上しました。
- デバイスが複数日間スタンバイ状態のままになった後に、mixed reality capture がビデオを記録できない問題を解決しました。
- Unity アプリケーションでは、HolographicSpace API は一般に無効になっています。 この動作により、[バックグラウンドで実行する] 設定が有効になっている場合でも、バイザーが反転されたときに一部のアプリが一時停止する原因となる問題が回避されます。 この API は、Unity バージョン2018.4.18 以降および2019.3.4 以降で有効になりました。
- Wi-Fi 接続を介してデバイスポータルにアクセスすると、証明書が無効なために web ブラウザーがアクセスできなくなる可能性があります。 デバイス証明書が既に信頼されている場合でも、ブラウザーは "ERR_SSL_PROTOCOL_ERROR" などのエラーを報告することがあります。 この場合、セキュリティ警告を無視するオプションがないため、デバイスポータルに進行することはできません。 この更新プログラムにより、問題が解決されました。 デバイス証明書が以前にダウンロードされ、PC に信頼されていて、ブラウザーのセキュリティ警告を削除する場合は、ブラウザーのセキュリティの警告に対処するために、新しい証明書をダウンロードして信頼する必要があります。
- MSIX パッケージを使用してアプリをインストールできるランタイムプロビジョニングパッケージを作成する機能が有効になりました。
- 設定 System ホログラム に設定を追加しました。これにより、デバイスのシャットダウン時に、ユーザーは自宅からMixed Realityホログラムを自動的  >    >  に削除できます。
- ピクセル形式を変更し、HoloLensエミュレーターで黒にレンダリングするアプリのHoloLens修正しました。
- Iris ログイン中にクラッシュを引き起こしたバグを修正しました。
- 既に現在のアプリに対するストアのダウンロードの繰り返しに関する問題を修正しました。
- イマーシブ アプリがアプリを繰り返し開かMicrosoft Edge修正しました。
- 1903 リリースから更新した後の初期ブートでの Photos アプリの起動に関する問題を修正しました。
- パフォーマンスと信頼性の向上。

## <a name="windows-holographic-version-1903---june-2020-update"></a>WindowsHolographic バージョン 1903 - 2020 年 6 月更新
- ビルド 18362.1064

更新プログラムの機能強化と修正:

- カスタム MRC レコーダーは、指定されていない場合、特定のプロパティに対して新しい既定値を持っています。
  - *MRC ビデオ効果の場合*:
    - PreferredOgramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (イマーシブ ヘッドセット))
  - *MRC オーディオ効果:*
    - LoopbackGain (現在の "App Audio Gain" の値は、Mixed Reality キャプチャ ページWindows デバイス ポータル)
    - MicrophoneGain (Mixed Reality キャプチャ ページの現在の "Mic Audio Gain" Windows デバイス ポータル)
- Unity アプリケーションでは、HolographicSpace.UserPresence API は一般に無効になっています。 この動作により、バックグラウンドで実行する設定が有効になっている場合でも、バイザーが反転した場合に一部のアプリが一時停止する問題が回避されます。 この API は、Unity バージョン 2018.4.18 以降および 2019.3.4 以降で有効になっています。
- ピクセル形式を変更し、HoloLensを黒にレンダリングするアプリの問題を修正HoloLens Emulator。
- 1903 リリースから更新した後の初期ブートでの Photos アプリの起動に関する問題を修正しました。

## <a name="windows-holographic-version-2004"></a>WindowsHolographic バージョン 2004  
- ビルド - 19041.1103

*HoloLens 2、Windows Holographic、バージョン 2004* の 2020 年 5 月のメジャー ソフトウェア更新プログラムには、Windows Autopilot のサポート、アプリダーク モード、5G/LTE ホットスポットの USB イーサネット サポートなど、多くの重要な新機能が含まれています。 最新のリリースに更新するには、設定アプリを開き、[ & セキュリティの更新] に移動して、[ 更新プログラムの確認]    **** **ボタンを選択**   します。 

|             機能                              |          説明                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          AutoPilot を使用して、新しいデバイスを事前構成してシームレスにWindowsする                 |
|       FIDO 2 のサポート                             |          共有デバイスの高速かつ安全な認証を有効にする FIDO2 セキュリティ キーのサポート            |
|       プロビジョニングの改善                      |          USB ドライブからデバイスにプロビジョニング パッケージをシームレスに適用HoloLens                              |
|       アプリケーションのインストール状態                 |          アプリのアプリが MDM 経由設定にプッシュされているアプリのインストール状態HoloLens 2確認する               |
|       構成サービス プロバイダー (AP)   |          管理者制御機能を強化する新しい構成サービス プロバイダーを追加しました                 |
|       USB 5G/LTE のサポート                       |          USB イーサネット機能の拡張により、5G/LTE のサポートが可能                                    |
|       ダーク アプリ モード                              |          ダーク モードとライト モードの両方をサポートするアプリで使用できるダーク アプリ モード。表示エクスペリエンスが向上します        |
|       音声指示コマンド                             |          システム音声コマンドをハンズフリーで制御HoloLensサポート                           |
|       手の追跡の機能強化                 |          手の追跡の機能強化により、ボタンと 2D スレートの相互作用をより正確に行える                        |
|       品質の向上と修正                 |          プラットフォーム全体のさまざまなシステム パフォーマンスと信頼性の向上                            |

### <a name="support-for-windows-autopilot"></a>Autopilot Windowsのサポート

WindowsAutopilot for HoloLens 2を使用すると、デバイスの販売チャネルが Intune テナントにHoloLensを事前に登録できます。 デバイスが到着すると、テナントの下に共有デバイスとして自己展開する準備が整います。 自己展開を利用するには、USB-C からイーサネットを使用して、セットアップの最初の画面でデバイスがネットワークに接続する必要があります。

ユーザーが Autopilot の自己展開プロセスを開始すると、次の手順が完了します。

1. デバイスをデバイスに参加Azure Active Directory (Azure AD)。
1. デバイスAzure AD (または別の MDM サービス) Microsoft Intune登録するには、 を使用します。
1. デバイスを対象とするポリシー、証明書、およびネットワーク プロファイルをダウンロードします。
1. デバイスをプロビジョニングします。
1. ユーザーにサインイン画面を表示します。

詳細については[、Autopilot Windows評価ガイドに関するHoloLens 2参照してください](https://docs.microsoft.com/hololens/hololens2-autopilot)。

*今すぐ AutoPilot プレビューに参加するには、アカウント マネージャーに問い合わせください。Autopilot 対応デバイスの出荷は間もなく開始されます。*

### <a name="fido2-security-key-support"></a>FIDO2 セキュリティ キーのサポート

一部のユーザーは、HoloLens環境内の他のユーザーとデバイスを共有します。 そのため、ユーザーは長いユーザー名とパスワードを入力せずに簡単に行える必要があります。 Fast Identity Online (FIDO) を使用すると、組織内のすべてのユーザー (Azure AD テナント) は、ユーザー名やパスワードを入力せずに HoloLens にシームレスにサインインできます。

FIDO2 セキュリティ キーは、任意のフォーム ファクターで受け取る可能性がある、"未強化の" 標準ベースのパスワードレス認証方法です。 FIDO は、パスワードレス認証のオープン標準です。 これにより、ユーザーと組織は、ユーザー名やパスワードを使用せずにリソースにサインインできます。 代わりに、外部セキュリティ キーまたはデバイスに組み込みのプラットフォーム キーを使用します。

開始するには、「パスワードレス セキュリティ [キーのサインインを有効にする」を参照してください](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)。

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>プロビジョニング パッケージを使用した MDM 登録の改善

プロビジョニング パッケージを使用すると、HoloLensではなく、構成ファイルを使用して構成を設定HoloLens out-of-box experience。 以前は、プロビジョニング パッケージを内部メモリ内の HoloLensする必要があります。 USB ドライブに接続できるので、複数の HoloLens デバイスで簡単に再利用し、デバイスを並列でプロビジョニングできます。 プロビジョニング パッケージでデバイス管理に登録するフィールドもサポートされるので、プロビジョニング後に手動でセットアップする必要はありません。

実行方法:

1. 最新バージョンの Windows 構成デザイナーを Windows PC にダウンロードします。
1. [Provision **HoloLens Devices Provision HoloLens 2**  >  **devices]を選択します**。
2. 構成プロファイルを作成します。 次に、作成されたファイルを USB-C ストレージ デバイスにコピーします。
3. USB-C デバイスをフラッシュした新しいデバイスに接続HoloLens。 次に、**ボリュームダウン電源**  +  **ボタンを** 押して、プロビジョニング パッケージを適用します。

### <a name="line-of-business-application-install-status"></a>Line-of-Business アプリケーションのインストール状態

ビジネス アプリの MDM アプリの展開と管理は、アプリケーションを展開HoloLens。 管理者とユーザーは、監査と診断のためにアプリのインストール状態を表示する必要があります。 このリリースでは、アカウントアクセスの詳細を設定または学校で追加しました。  >    >    >  **アカウント情報 をクリック**  >  **します**。

### <a name="additional-csps-and-policies"></a>その他の CSP とポリシー

構成 [サービス プロバイダー (CSP) は](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) 、デバイスの構成設定を読み取り、設定、変更、または削除するインターフェイスです。 このリリースでは、展開されたデバイスに対して管理者が持つ制御を増やHoloLensしました。 HoloLens でサポートされている CSP の一覧については[、「NetworkQoSPolicy CSP 」を参照してください](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。

このリリースでの新しい内容

**Policy CSP** 

ポリシー構成サービス プロバイダーを使用すると、企業はデバイスに対してポリシー Windowsできます。 このリリースでは、次に示す HoloLens新しいポリシーを追加しました。 詳細については、 でサポート[されているポリシーの CSP に関するページをHoloLens 2。](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)  

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

5G/LTE フォンや Wi-Fi ホットスポットなど、特定のモバイルブロードバンドデバイスを USB 経由で HoloLens 2 にテザリングさするときに、サポートが追加されました。 これらのデバイスは、別のイーサネット接続として [ **ネットワーク設定** ] に表示されるようになりました。 (外部ドライバーを必要とするモバイルブロードバンドデバイスはサポートされていません)。この機能により、Wi-Fi を利用できず Wi-Fi テザリングで十分なパフォーマンスが得られない場合に、高帯域幅の接続が可能になります。 サポートされている usb デバイスの詳細については、「 [Connect Bluetooth と usb C デバイス](https://docs.microsoft.com/hololens/hololens-connect-devices)」を参照してください。  

### <a name="hand-tracking-improvements"></a>手動追跡の機能強化

このリリースには、いくつかの手動追跡の機能強化が含まれています。

- **ポイントの安定性:** これで、システムは、palm によって occluded されたときにインデックスの指を resists 曲げます。 この変更により、ボタン、型、コンテンツのスクロールなどをプッシュするときの精度が向上します。 
- **偶発的なエアタップの削減:** エアタップジェスチャの検出を改善しました。 いくつかの一般的なシナリオでは、ユーザーを自分の側にドロップしたときなど、誤ったアクティベーションが減ります。
- **ユーザースイッチの信頼性:** デバイスを共有するときに、手動でサイズを更新すると、システムの速度と信頼性が向上しました。
- **手作業の盗難:** センサーの2つ以上のハンズオンビューがあるケースの処理を改善しました。 複数の人が近くに作業している場合、追跡されたハンドがシーン内の他のユーザーの手に "ジャンプ" する可能性は非常に低くなります。
- **システムの信頼性:** デバイスの負荷が高いときに、ハンドトラッキングが動作を停止する原因となった問題を修正しました。

### <a name="dark-mode"></a>ダーク モード

多くの Windows アプリで、ダークモードとライトモードの両方がサポートされるようになりました。 HoloLens 2 ユーザーは、両方をサポートするアプリの既定のモードを選択できます。 更新後、既定のアプリモードは "ダーク" になりますが、この設定を簡単に変更できます。 [**設定**  >  **システム** の色] に移動し  >    >  **て、既定のアプリモードを選択** します。 

これらの "インボックス" アプリでは、ダークモードがサポートされるようになります。 

- 設定 
- Microsoft Store 
- Mail 
- Calendar 
- エクスプローラー 
- フィードバック Hub 
- OneDrive 
- Photos 
- 3D ビューアー 
- 映画 & テレビ 

![ダークモードのウィンドウ (並べて表示)](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>システム音声コマンド

デバイス上の任意のアプリで音声コマンドを使用できるようになりました。 詳細については、「[音声を使用](https://docs.microsoft.com/hololens/hololens-cortana)した HoloLens の操作」を参照してください。 「 [HoloLens 2 でサポートされる言語](https://docs.microsoft.com/hololens/hololens2-language-support)」も参照してください。  

### <a name="cortana-updates"></a>Cortana の更新プログラム

更新されたアプリは Microsoft 365 と統合されているため、デバイス全体でより多くの作業を行うことができます (現時点では US-English のみ)。 HoloLens 2 では Cortana、ボリュームの調整や再起動など、デバイス固有の特定のコマンドがサポートされなくなりました。 これらのオプションは、新しいシステムの音声コマンドでサポートされるようになりました。 新しい Cortana アプリの詳細については、こちらの[ブログ](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)を参照してください。

### <a name="quality-improvements-and-fixes"></a>品質の向上と修正

更新プログラムの機能強化と修正:  
- アクティブなディスプレイ調整システムが導入されました。 この機能により、ホログラムの安定性とアラインメントが向上します。 ここでは、ヘッドを左右に移動したときにそのままにしておきます。
- HoloLens への Wi-Fi ストリーミングが定期的に中断されているバグを修正しています。 アプリケーションで、待機時間の短いストリーミングが必要であることが示された場合は、 [SetSocketMediaStreamingMode 関数](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)を呼び出して修正プログラムを実装します。
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
- 問題が発生した場合は、デバイスを起動した後、音声ライセンス認証を Cortana 使用するように Cortana アプリを起動する必要があります。 18362ビルドから更新した場合は、**スタート** で動作しなくなった以前のバージョンの Cortana アプリの2つ目のアプリタイルが表示されることもあります。

## <a name="windows-holographic-version-1903---may-2020-update"></a>WindowsHolographic、バージョン 1903-2020 更新プログラム 
- ビルド18362.1061

この毎月の品質更新プログラムに Windows は、前に説明したように、Holographic バージョン2004の更新プログラムでチームが作業していたため、重要な変更は含まれていません。

## <a name="windows-holographic-version-1903---april-2020-update"></a>WindowsHolographic、バージョン 1903-2020 年4月更新
- ビルド18362.1059

**サポートされているアプリのダークモード** 

多くの Windows アプリは、ダークモードとライトモードの両方をサポートしています。 HoloLens 2 のお客様は、両方の配色をサポートするアプリの既定のモードを選択できるようになりました。 お客様からのフィードバックに基づいて、既定のアプリモードを "ダーク" に設定しますが、この設定はいつでも簡単に変更できます。**設定 > システム > の色** に移動し **て、[既定のアプリモードを選択してください]** を見つけます。

これらの "インボックス" アプリでは、ダークモードがサポートされるようになります。
- 設定
- Microsoft Store
- Mail
- Calendar
- エクスプローラー
- フィードバック Hub
- OneDrive
- Photos
- 3D ビューアー
- 映画 & テレビ

**更新プログラムの機能強化と修正:** 
- シェルオーバーレイが混合現実キャプチャに含まれることを確認します。
- Unreal の開発者は、デバイスポータルの [3D ビュー] ページを使用して、アプリケーションをテストおよびデバッグできるようになりました。
- *HolographicDepthReprojectionMethod Dep の予測* アルゴリズムが使用されている場合に、mixed reality キャプチャでのホログラムの安定性が向上しました。
- 32ビット ARM アプリで "WinRT IStreamSocketListener API クラスが登録されていません" エラーを修正しました。

## <a name="windows-holographic-version-1903---march-2020-update"></a>WindowsHolographic、バージョン 1903-2020 年3月更新 
- ビルド18362.1056

更新プログラムの機能強化と修正:

- *HolographicDepthReprojectionMethod AutoPlanar* アルゴリズムが使用されている場合に、mixed reality キャプチャでのホログラムの安定性が向上しました。
- 深度の MF サンプルにアタッチされている座標系が、パブリックドキュメントと一致していることを確認します。
- 顧客がデバイスポータルを使用して大量のテキストを貼り付けることで、開発者の生産性が向上しました。

## <a name="windows-holographic-version-1903---february-2020-update"></a>WindowsHolographic、バージョン 1903-2020 更新プログラム 
- ビルド18362.1053

更新プログラムの機能強化と修正:

- Unity アプリケーションの HolographicSpace API を一時的に無効にしました。 この変更により、[バックグラウンドで実行する] 設定が有効になっている場合でも、バイザーが反転されたときに一部のアプリが一時停止する原因となった問題が回避されます。
- 手動追跡によって発生するランダムな HUP クラッシュを修正しました。この場合、ユーザーは UI をフリーズしてから、数秒後にシェルに戻ることに気付きました。
- インデックス指をからかうすると、その指の上部が予期せずに curl される可能性が低くなるように、ハンドトラッキングが向上しました。
- ヘッド追跡、空間マッピング、およびその他のランタイムの信頼性が向上しました。

## <a name="windows-holographic-version-1903---january-2020-update"></a>WindowsHolographic、バージョン 1903-1 月2020更新プログラム 
- ビルド18362.1043
 
更新プログラムの機能強化と修正:

- HoloLens 2 エミュレーターを使用する場合の排他的なアプリの安定性が向上しました。

## <a name="windows-holographic-version-1903---december-2019-update"></a>WindowsHolographic、バージョン 1903-12 月2019更新プログラム 
- ビルド18362.1042

更新プログラムの機能強化と修正:

- 最終ステージ再現 (LSR) 修正が導入されました。 ホログラムの視覚的レンダリングが改善され、詳細をより正確に把握できるようになりました。 この現象は、アプリがホログラムの深さを正しく設定していない場合に、この更新後により顕著になります。
- 排他アプリの安定性と排他アプリ間のナビゲーションを修正します。
- デバイスが数日間スタンバイ状態になった後に、mixed reality capture がビデオを記録できない問題を解決しました。
- ホログラムの安定性が向上しました。

## <a name="windows-holographic-version-1903---november-2019-update"></a>WindowsHolographic、バージョン 1903-2019 の11月の更新プログラム 
- ビルド18362.1039

更新プログラムの機能強化と修正:

- En-us と en-us の初回セットアップ時に **選択し** た音声コマンドの機能を修正しました。
- 最新の Unity と Mixed Reality Toolkit (mrtk) バージョンには遠く離れたオブジェクトの視覚的な品質が向上しました。
- スタートメニューが開かれた後に閉じられるまで、holographic アプリケーションの問題を解決して、起動時に一時停止状態になります。
- HoloLens 2 とエミュレーターの OpenXR ランタイム準拠の修正と改善。
