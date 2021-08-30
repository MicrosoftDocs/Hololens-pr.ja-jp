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
ms.date: 08/10/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: be2fde329293b89698c0f6dd5d92df1c6260f1be
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190227"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 のリリース ノート

お使いのすべてのデバイスで生産性の高いエクスペリエンスをHoloLens、機能、バグ、およびセキュリティ更新プログラムを引き続きリリースします。 このページでは、各月の新しい機能HoloLens確認できます。 最新の更新プログラムHoloLens 2するには、更新プログラムを確認し[](hololens-update-hololens.md#check-for-updates-and-manually-update)、手動で更新するか、フル フラッシュ更新 (FFU) を取得して[、Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device)を使用してデバイスをフラッシュします。 ダウンロード [は](https://aka.ms/hololens2download) 最新の状態に保たれ、一般提供される最新のビルドが提供されます。

> [!NOTE]
> 最近の Windows 11 の発表は、Windows の PC バージョンに重点を置いていました。 マイクロソフトでは、2021 年 5 月に HoloLens 2 に[主要 OS のアップデート](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067)を開始したばかりであり、この秋に向けてお客様からのフィードバックに基づいて今後のリリースに取り組んでいます。

> [!IMPORTANT]
> Remote Assist ユーザーに影響を与えた[21H1](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)ビルドで既知の問題が解決されたので、Windows Holographic バージョン 21H1 更新プログラムのオファリングを一時的に一時停止しました。 また、既定の Advanced Recovery Companion (ARC) ビルドを[Windows Holographic バージョン 20H2 – June 2021 Update に変更しました](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update)。 ARC ビルドは、21H1 ビルドを対象として再開されます。

## <a name="windows-holographic-version-21h1---august-2021-update"></a>WindowsHolographic バージョン 21H1 - 2021 年 8 月の更新プログラム

- ビルド 20348.1014

更新プログラムの機能強化と修正:

- コントローラーをサポートするイマーシブ アプリケーションで Xbox コントローラーが動作しない問題を修正しました。
- デバイスの更新エラーの診断を改善しました。

## <a name="windows-holographic-version-20h2---august-2021-update"></a>WindowsHolographic バージョン 20H2 - 2021 年 8 月の更新プログラム

- ビルド 19041.1161

更新プログラムの機能強化と修正:

- この毎月の品質更新プログラムには、重要な変更が含まれているのではなく、最新のビルドである Windows Holographic バージョン 21H1 をお試しください。

## <a name="windows-holographic-version-21h1---july-2021-update"></a>WindowsHolographic バージョン 21H1 - 2021 年 7 月の更新プログラム

- ビルド 20348.1010

更新プログラムの機能強化と修正:

- デバイス ポータルファイルを開く際に問題が発生した場合にエクスプローラーする方法が強化されています。
- サポートされているブラウザーすべてで https を使用すると、ファイルのアップロード、ダウンロード、名前変更、削除が修正されました。
- **設定 -> Network & Internet > -& Status -> Properties** から Wi-Fi プロパティ UI を起動すると、Wi-Fi プロキシを保存できない問題を修正しました。
- OS 更新プログラム全体での eSIM 証明書の削除に関する問題に対処しました。 この修正により、21H1 リリースに更新するときに、eSIM 証明書と関連コンポーネントが確実に削除されます。
- OS のリセット全体でプレインストールされているアプリに影響する問題を修正しました。
- バッテリ充電のパフォーマンスは、CPU 読み込みを増やして充電するときにランタイムを向上させるチューニングを行いました。 デバイスへのHoloLens 2中に、デバイスがホットで動作しているのが検出された場合、内部バッテリの充電速度が遅くなると、熱が低下します。 肯定的なトレードオフは、温度の問題が原因でデバイスがシャットダウンする可能性が低く、影響を受け、デバイスの実行時間が長くなる点です。 デバイスがクールで実行されている場合、料金は影響を受けません。

## <a name="windows-holographic-version-20h2--july-2021-update"></a>WindowsHolographic バージョン 20H2 – 2021 年 7 月の更新プログラム

- ビルド 19041.1157

更新プログラムの機能強化と修正:

- デバイス ポータルファイルを開く際に問題が発生した場合にエクスプローラーする方法が強化されています。
- サポートされているブラウザーすべてで https を使用すると、ファイルのアップロード、ダウンロード、名前変更、削除が修正されました。

## <a name="windows-holographic-version-21h1---june-2021-update"></a>WindowsHolographic バージョン 21H1 - 2021 年 6 月更新

- ビルド 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDriveまたは学校のカメラ ロール のアップロードに関するページ

HoloLens 2 設定 アプリに新しい機能が追加されました。これにより、お客様はデバイスの Pictures > Camera Roll フォルダーから、対応する OneDrive for work または school フォルダーに Mixed Reality の写真とビデオを自動的にアップロードできます。 この機能は、HoloLens 2 上の[OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos)アプリ内の機能のギャップに対応します。これは、(仕事または学校アカウントではなく) 顧客の個人の Microsoft アカウント へのカメラ ロールの自動アップロードのみをサポートします。

**動作のしくみ**

- 「設定 > **System > Mixed Reality カメラ」** にアクセスして、"カメラのアップロード" を有効にしてください。
- この機能を [オン] の位置に設定すると、デバイスにキャプチャされた Mixed Reality の写真またはビデオは、自動的にキューに登録され、OneDrive の仕事用または学校アカウント用の Pictures > Camera Roll フォルダーにアップロードされます。
    >[!NOTE]
    >この機能を有効にする前にキャプチャされた写真とビデオは、アップロード用にキューに登録されるのではなく、引き続き手動でアップロードする必要があります。
- 設定 ページのステータス メッセージには、アップロードが保留中のファイルの数が表示されます (または、保留中のすべてのファイルがアップロードされると "OneDrive is up to date" と読み取ります)。
- 帯域幅が気になる場合や、何らかの理由でアップロードを "一時停止" したい場合は、機能を [オフ] の位置に **切り替** えます。 この機能を一時的に無効にすると、Camera Roll フォルダーに新しいファイルを追加するとアップロード キューが引き続き増加しますが、機能を再び有効にするまでファイルはアップロードされます。
- 最新のファイルが最初にアップロードされます (最後のファイル、最初のファイル)。
- お使OneDriveアカウントに問題がある場合 (パスワードの変更後など)、[今すぐ修正] ボタンが [設定されます。
- 最大ファイル サイズはありません。ただし、大きなファイルのアップロードには長い時間がかかる点に注意してください (特にアップロード帯域幅が制限されている場合)。 大きなファイルのアップロード中にアップロードを "一時停止" またはオフにした場合、部分的なアップロードは保持されます。 アップロードが "一時停止" またはオフになってから数時間以内に再び有効になっている場合、アップロードは中断された場所から続行されます。 ただし、数時間後にアップロードが再び有効になっている場合、大きなファイルのアップロードは最初から再開されます。

**既知の問題と注意点**

- この設定には、現在の帯域幅の使用量に基づく調整は組み込みはありません。 別のシナリオで帯域幅を最大化する必要がある場合は、手動で設定をオフにします。 アップロードは一時停止されますが、この機能はカメラ ロールに新しく追加されたファイルを引き続き監視します。 続行する準備ができたら、アップロードを再び有効にしてください。
- この機能は、デバイス上の各ユーザー アカウントに対して有効にする必要があります。また、デバイスに現在サインインしているユーザーのファイルのみをアクティブにアップロードできます。
- 設定 ページのアップロード数をリアルタイムで監視しながら写真やビデオを撮影している場合は、現在のファイルのアップロードが完了するまで、保留中のファイル数が変更されない可能性があります。
- アップロードデバイスがスリープ状態または電源がオフになっている場合は、一時停止します。 保留中のアップロードを確実に完了するには、設定 ページに "OneDrive が最新" と表示されるまでデバイスをアクティブに使用するか **、Power &** のスリープ設定を調整します。

### <a name="added-support-for-some-telemetry-policies"></a>一部のテレメトリ ポリシーのサポートを追加しました

次のテレメトリ ポリシーが、次のテレメトリ ポリシーでサポートHoloLens 2。

- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry と System\ConfigureTelemetryOptInSettingsUx の両方を一緒に使用して、設定 アプリのテレメトリと動作を完全に制御する必要があります。

更新プログラムの機能強化と修正:

- 色の調整を使用して、ビデオの大きな破損を修正します。
- [電源] メニューでテキストが切り捨てられる可能性がある問題を修正します。
- RequirePrivateStoreOnly ポリシーのサポートを有効にする。

## <a name="windows-holographic-version-20h2--june-2021-update"></a>WindowsHolographic バージョン 20H2 – 2021 年 6 月の更新プログラム

- ビルド 19041.1154

### <a name="added-support-for-some-telemetry-policies"></a>一部のテレメトリ ポリシーのサポートを追加しました

次のテレメトリ ポリシーが、次のテレメトリ ポリシーでサポートHoloLens 2。

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
>- WindowsHolographic、バージョン 20H2 (Build 19041.1128 +)
>- WindowsHolographic、バージョン 2004 (Build 19041.1103 +)
>- WindowsHolographic、バージョン 1903 (Build 18362 +)
>
> Windows Holographic バージョン21h1 の導入により、 **Windows Holographic バージョン1903の月単位のサービス更新プログラムを中止** します。 これにより、より新しいリリースに専念し、貴重な改善を続けることができます。


| 機能名                                              | 簡単な説明                                                                      | 対象読者 | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [新しい Microsoft Edge](#introducing-the-new-microsoft-edge)  | 新しい Chromium ベースの Microsoft Edge が HoloLens 2 で使用できるようになりました。 | エンド ユーザー | 
[WebXR および 360 ビューアー](#webxr-and-360-viewer) | イマーシブ web エクスペリエンスと360ビデオ再生を試してみてください。 | エンド ユーザー | 
[新しい設定アプリ](#new-settings-app) | レガシ設定アプリは、新しい機能と設定を使用して、更新されたバージョンに置き換えられています。 | エンド ユーザー |
[色の調整を表示する](#display-color-calibration) | HoloLens 2 表示の代替カラー プロファイルを選択します。 | エンド ユーザー |
[既定のアプリ ピッカー](#default-app-picker) | ファイルまたはリンクの種類ごとに起動するアプリを選択します。 | エンド ユーザー |
[アプリごとのボリューム制御](#per-app-volume-control) | システムボリュームとは独立してアプリレベルボリュームを制御します。 | エンド ユーザー |
[Web アプリのインストール](#install-web-apps) | 新しい Microsoft Edge ブラウザーを使用して、Microsoft Office などの HoloLens 2 に web アプリをインストールします。 | エンド ユーザー |
[スワイプして入力する](#swipe-to-type) | 指の先端を使用して、holographic キーボードで単語を "スワイプ" します。 | エンド ユーザー |
[[スタート] の [電源] メニュー](#power-menu-from-start) | [スタート] メニューで HoloLens デバイスを再起動してシャットダウンします。 | エンド ユーザー |
[サインイン画面に複数のユーザーが表示される](#multiple-users-listed-on-sign-in-screen) | サインイン画面に複数のユーザーアカウントを表示します。 | エンド ユーザー |
[USB-C 外部マイクのサポート](#usb-c-external-microphone-support) | アプリやリモートアシスタンスで USB C マイクを使用します。 | エンド ユーザー |
[キオスクのビジター自動ログオン](#visitor-auto-logon-for-kiosks) | ビジターアカウントの自動ログオンをキオスクモードで使用できるようにします。 | IT 管理者 |
[キオスクモードでの新しいアプリの新しい AUMIDs](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | AUMIDs は、新しい設定とエッジアプリを対象としています。 | IT 管理者 |
[キオスクモードのエラー処理の改善](#kiosk-mode-behavior-changes-for-handling-of-failures) | キオスクモードでは、空のスタートメニューの前に、グローバルに割り当てられたアクセスを検索します。 | IT 管理者 |
[新しい Settingはページ設定可視性を備えています](#new-settings-uris-for-page-settings-visibility) | 20 + 新しい Setting/PageVisibilityList は、設定ポリシーを対象としています。 | IT 管理者 |
[フォールバック診断の構成](#configuring-fallback-diagnostics-via-settings-app) | 設定アプリでフォールバック診断動作を設定しています。 | IT 管理者 |
[近くのデバイスとの共有](#share-things-with-nearby-devices) | ファイルまたは url を HoloLens から PC に共有します。 | すべて |
[新しい OS 診断トレース](#new-os-diagnostic-traces) | OS の更新のための設定の新しいトラブルシューティングです。 | IT 管理者 |
[配信の最適化のプレビュー](#delivery-optimization-preview) | 複数の HoloLens デバイスからのダウンロードの帯域幅の消費を削減します。 | IT 管理者 |

関連するリリースノートを確認する:

- [HoloLens Emulator アーカイブにアクセスする](/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>新しい Microsoft Edge について

![新しい Microsoft Edge ロゴへの従来の Microsoft Edge ロゴのアニメーション。](images/new-edge.gif)

新しいMicrosoft Edge[ は、Chromiumオープンソース プロジェクト](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/)を採用して、顧客との互換性を向上し、Web 開発者向けの Web の断片化を減らします。

> [!IMPORTANT]
> この新しい Microsoft Edge は、新しいリリースでは[サポートされなくなった](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/)レガシの Microsoft Edge を自動的に置き換える機能です。

![新しい Microsoft Edge のスクリーンショット。](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>新しい Microsoft Edge を起動する

新しい Microsoft Edge ![新しい Microsoft Edge アイコン。](images/new_edge_logo.png) (青と緑のスワイル アイコンで表されます) は、スタート メニュー にピン留めされ、Web リンクをアクティブ化すると自動的に起動します。

> [!NOTE]
> HoloLens 2 で新しい Microsoft Edge を初めて起動するとき、設定とデータはレガシの Microsoft Edgeからインポートされます。 新しい Microsoft Edge を起動した後も従来の Microsoft Edge を使用し続ける場合、新しいデータは従来の Microsoft Edge から新しい Microsoft Edge には同期されません。

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>新しい Microsoft Edge のポリシー設定を構成する

この新しいMicrosoft Edgeでは、IT 管理者に、従来の Microsoft Edge で以前に使用していたよりも、HoloLens 2 に対するはるかに広範なブラウザー ポリシーのセットを提供します。

新しい Microsoft Edge のポリシー設定の管理の詳細については、次のリソースを参照してください。

- [Microsoft Intune で Microsoft Edge ポリシー設定を構成](/deployedge/configure-edge-with-intune)
- [Microsoft Edge ポリシーと Microsoft Edge ポリシーのマッピング](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome と Microsoft Edge ポリシーのマッピング](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- 完全な [Microsoft Edge Enterprise ドキュメント](/deployedge/)

> [!IMPORTANT]
> 新しい Microsoft Edge でサポートされているブラウザー ポリシーの量が多いので、チームは新しい各ポリシーが HoloLens 2 で動作することを保証できません。 ただし、以前に HoloLens 2 でサポートされている各レガシの Microsoft Edge ポリシーと同等の新しい Microsoft Edge をテストし期待どおりに機能することを確認しました。 HoloLens 2 で使用していた各レガシ Microsoft Edge ブラウザー ポリシーと同等の新しい Microsoft Edge を確認するには、「[Microsoft Edge レガシと Microsoft Edge ポリシーのマッピング](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)」を参照してください。
>
> 次の 2 つ以上の当社が把握している新しい Microsoft Edge ポリシーは、HoloLens 2 では機能 *しません*。
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>HoloLens 2 で新しい Microsoft Edge から期待するもの

新しい Microsoft Edge は、新しい UWP アダプター レイヤーを備え、HoloLens 2 のような UWP 専用デバイスで実行できるネイティブ Win32 アプリなので、一部の機能はすぐには使用できない場合があります。 今後数か月間に新しいシナリオと機能をサポートする予定なので、この領域で最新の情報を確認してください。

**機能することが想定されるシナリオと機能:**
- 初回実行エクスペリエンス、プロファイルへのサインイン、同期
- Web サイトがレンダリングされ、期待どおりに動作する必要がある
- ほとんどのブラウザー機能 (お気に入り、履歴など) は期待した通りに動作する必要があります
- ダーク モード
- デバイスへの Web アプリのインストール
- 拡張機能のインストール (HoloLens 2 上で正常に機能しない拡張機能がある場合は、お知らせください)
- PDF の表示と設定
- 1 つのブラウザー ウィンドウからの空間サウンド
- ブラウザーの自動更新と手動更新
- [印刷] メニューから PDF を保存する ([PDF に保存] オプションを使用)
- WebXR および 360 ビューアー拡張機能
- 環境内に配置された複数のウィンドウ間で参照する場合の、正しいウィンドウへのコンテンツの復元

**機能することが想定されないシナリオと機能:**
- 同時オーディオ ストリームを使用した複数のウィンドウからの空間サウンド
- 「見て発音する」
- 印刷

**ブラウザーの上位の既知の問題:**

- ホログラフィック キーボードの拡大鏡プレビューは、新しい Microsoft Edge では無効になっています。 拡大が正しく機能したら、今後の更新プログラムでこの機能を再び有効にしてください。
- 別のブラウザー ウィンドウが開いておりアクティブな場合、間違ったブラウザー ウィンドウからオーディオが再生される可能性があります。 この問題を回避するには、オーディオを再生していてはいけない他のアクティブ ウィンドウを閉じます。
- "フォローする" モードでブラウザー[](hololens2-basic-usage.md#follow-me-stop-following)ウィンドウからオーディオを再生すると、"フォローする" モードを無効にした場合、オーディオは再生を続行します。 この問題を回避するには、"フォローする" モードを無効にする前にオーディオ再生を停止するか **、X** ボタンでウィンドウを閉じます。
- アクティブな Microsoft Edge ウィンドウとやりとりすると、他の 2D アプリ ウィンドウが予期せず非アクティブになる可能性があります。 これらのウィンドウは、もう一度操作すれば再アクティブ化できます。

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider アイコン

このMicrosoft Edge チームは、Edge Insider コミュニティで 3 つのプレビュー チャネル (ベータ、開発、カナリア) を利用できます。 プレビュー チャネルをインストールしても、リリースされたバージョンの Microsoft Edge は HoloLens 2 でアンインストールされません。また、複数を同時にインストールできます。 

Edge Insider コミュニティの詳細については、[Microsoft Edge Insider](https://www.microsoftedgeinsider.com) のホームページを参照してください。 さまざまな Edge Insider チャネルの詳細と使用を開始するには、[Edge Insider のダウンロード ページ](https://www.microsoftedgeinsider.com/download)を参照してください。

Microsoft Edge Insider チャネルを HoloLens 2 にインストールするには、複数の方法があります。

**デバイスへの直接インストール (現在はアンマネージド デバイスでのみ使用可能)**
  1. お使いの HoloLens 2 で、[Edge Insider ダウンロード ページ](https://www.microsoftedgeinsider.com/download)にアクセスします。
  1. インストールする Edge Insider チャネルの **[HoloLens 2 のためにダウンロード]** ボタンを選択します。
  1. ダウンロードした .msix ファイルを Edge ダウンロード キューから、またはデバイスの "ダウンロード" フォルダーから起動します (エクスプローラーを使用)。
  1. [アプリ インストーラー](app-deploy-app-installer.md)が起動します。
  1. **[インストール]** ボタンを選択します。
  1. インストールが成功すると、スタートメニューの **[すべてのアプリ]** の一覧に、Microsoft Edge Beta、Dev、または Canary が別のエントリとして表示されます。

**コンピューターを使用してWindows デバイス ポータル(HoloLens 2 で [開発者モード](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)を有効にする必要あり) をインストールします**
  1. お使いのコンピュータで、[Edge Insider ダウンロード ページ](https://www.microsoftedgeinsider.com/download)にアクセスします。
  1. インストールする Edge Insiderチャネルの [Windows 10 用にダウンロード] ボタンの横にある **ドロップダウン矢印ボタン** を選択します。
  1. ドロップダウンの **[HoloLens 2]** を選択します。
  1. .msix ファイルを PC の "ダウンロード" フォルダー (または簡単に見つけられている別のフォルダー) に保存します。
  1. PC 上の[Windows デバイス ポータル](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)を使用して、HoloLens 2 上のダウンロードした .msix ファイルをインストールします。
  1. インストールが成功すると、スタートメニューの **[すべてのアプリ]** の一覧に、Microsoft Edge Beta、Dev、または Canary が別のエントリとして表示されます。

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>WDAC を使用して新しい Microsoft Edge をブロック

[WDAC ポリシー](windows-defender-application-control-wdac.md)を更新して新しい Microsoft Edge アプリをブロックする IT 管理者の場合は、ポリシーに次を追加する必要があります。

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>新しい Microsoft Edge のエンドポイントを管理する

一部の環境には、考慮すべきネットワーク制限がある場合があります。 新しい Edge でスムーズなエクスペリエンスを実現するには、[これらの Microsoft エンドポイントを有効にして](/deployedge/microsoft-edge-security-endpoints)ください。

現在使用可能な[ HoloLens 用エンドポイントの詳細について](hololens-offline.md)参照してください。

### <a name="install-web-apps"></a>Web アプリのインストール
 > [!Note]
>[Holographic Windowsバージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1)では、Office Web アプリはプレインストールされなくなりました。

新しい Edge を使用して、Microsoft Store アプリと共に Web アプリをインストールします。 たとえば、Microsoft Office Web アプリをインストールして、SharePoint または OneDrive でホストされているファイルを表示および編集できます。 Office Web アプリをインストールするには、 https://www.office.com にアクセスし、アドレス バーの **[使用可能なアプリ]** または **[Office をインストール]**  ボタンをクリックします。 **[インストール]** を選択 して確定します。

> [!IMPORTANT]
> Office Web アプリの機能は、HoloLens 2 にアクティブなインターネットがある場合にのみ使用できます。

### <a name="webxr-and-360-viewer"></a>WebXR および 360 ビューアー

新しいMicrosoft Edge には WebXR のサポートが含まれています。これは、イマーシブ Web エクスペリエンスを作成するための新しい標準です (WebVR の後継)。 多くのイマーシブ Web エクスペリエンスは、VR を念頭に置いて設計されました (実際の視野を仮想環境に置き換えます)。ただし、これらのエクスペリエンスは、HoloLens 2 でもサポートされています。 WebXR 標準では、物理環境を使用する拡張および Mixed Reality のイマーシブ Web エクスペリエンスも可能になります。 開発者が WebXR により多くの時間を費やすと、HoloLens 2 のお客様が新しい拡張および Mixed Reality イマーシブ エクスペリエンスを試せるようになる予定です!

360 Viewer 拡張機能は WebXR 上に構築され、HoloLens 2 上で新しい Microsoft Edge と共に自動的にインストールされます。 この Web 拡張機能を使用すると、360 度のビデオに取り入れすることができます。 YouTube では最大 360 本の動画が提供されているため、そこから開始することをお勧めします。

#### <a name="how-to-use-webxr"></a>WebXR の使用方法

1. WebXR がサポートされている Web サイトに移動します。
1. Web サイトの **[VR の入力]** ボタンを選択します。 このボタンの場所と視覚的な表現は、Web サイトごとに異なる場合がありますが、次のような場合があります。

    ![VR ボタンの例を入力します。](images/75px-enter-vr.png)

1. 特定のドメインで初めて WebXR エクスペリエンスを起動しようとすると、ブラウザーでイマーシブ ビューに入る同意を求められます。 **[許可]** を選択 してください。
1. [HoloLens 2 ジェスチャ](hololens2-basic-usage.md#the-hand-tracking-frame) を使用して、エクスペリエンスを操作します。
1. エクスペリエンスに **[終了]** ボタンがない場合は、[スタート ジェスチャ](hololens2-basic-usage.md#start-gesture)を使用してホームに戻ります。

**推奨される WebXR サンプル**
- 360 ビューアー (次のセクションを参照)
- [XR Dinosaurs](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>360 ビューアーの使い方

1. YouTube で 360 度のビデオに移動します。
1. ビデオ フレームで、[Mixed Reality ヘッドセット] ボタンを選択します。

    ![360 ビューアーをアクティブ化するボタン。](images/enter-360-viewer.jpg)

1. 特定のドメインで初めて 360 ビューアーを起動しようとすると、ブラウザーでイマーシブ ビューに入る同意を求められます。 **[許可]** を選択します。
1. [エア タップ](hololens2-basic-usage.md#select-using-air-tap) で再生コントロールを表示します。 [ハンド レイとエア タップ](hololens2-basic-usage.md#select-using-air-tap) を使用して、再生/一時停止、前方/戻るスキップ、キャプションのオン/オフの切り替え、エクスペリエンスの停止 (イマーシブ ビューを終了) を行います。 再生コントロールは、数秒の非アクティブ状態の後に消えます。

#### <a name="top-webxr-and-360-viewer-known-issues"></a>WebXR と 360 ビューアーの既知の問題
- WebXR エクスペリエンスの複雑さによっては、フレームレートが低下したり、つまずく場合があります。
- WebXR での多関節手関節のサポートは、既定では有効になっていません。 開発者は、"WebXR ハンド入力" をオンにすることで、 を使用 `edge://flags` してサポートを有効にできます。
- YouTube 以外の Web サイト 360 本の動画は想定通り動作しない場合があります。

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>WebXR と 360 ビューアーに関するフィードバックの提供

新しい Microsoft Edge の **フィードバックを送る** 機能を通じて当社のチームにフィードバックやバグをお知らせください。

### <a name="new-settings-app"></a>新しい設定アプリ

このリリースでは、新しいバージョンの新しいバージョンの 設定しています。 新しい設定アプリには、サウンド、電源とスリープ、ネットワークとインターネット、アプリ、アカウント、コンピューターの簡単操作などの領域における HoloLens 2 の新機能と拡張設定が含まれています。

> [!NOTE]
> 新しい設定アプリは従来の設定アプリとは別であるため、以前に環境に配置した設定の windows は、更新時に削除されます。

![新設定アプリのホーム ページ。](images/new-settings-app.png)

**新機能と設定**
- 設定の検索: キーワードまたは設定の名前を使用して、設定ホームページから設定を検索します。
- [システム] > [サウンド]:
  - 入出力オーディオ デバイス: 入力と出力のオーディオ デバイスを個別に選択します (たとえば、Bluetooth ヘッドホンを使用してオーディオをリッスンするか、オーディオ入力に USB C マイクを使用します)。
    > [!NOTE]
    > Bluetooth のマイクは、HoloLens 2 ではサポートされていません。
  - アプリのボリューム: 各アプリのボリュームを個別に調整します。 [「アプリごとのボリューム制御」](#per-app-volume-control)を参照してください。
- [システム] > [電源とスリープ]: 操作のない状態が一定期間続いた後にスリープに移行するときに選択します。
- [システム] > [バッテリ]: バッテリ節約モードを手動で有効にするか、バッテリ省モードが自動的にオンになるようにバッテリのしきい値を設定します。
- [デバイス] > [USB]: USB 接続を既定で無効にすることができます。
- ネットワークとインターネット:
  - USB-C イーサネット アダプタが、[ネットワークとインターネット] に表示されます。
  - USB-C イーサネットアダプターの設定が、IP アドレスを含めて使用できるようになりました。
  - HoloLens 2 で機内モードを有効にできるようになりました。
- アプリ: ファイルとリンクの種類に使用される既定のアプリをリセットできます。 詳細については、[「既定のアプリ ピッカー」](#default-app-picker)を参照してください。
- [アカウント] > [他のユーザー]: デバイス所有者は、ユーザーを追加し、標準ユーザーをデバイス所有者にアップグレードし、デバイス所有者を標準ユーザーにダウングレードして、ユーザーを削除することができます。
- 簡単操作: テキストのサイズと視覚効果を変更します。

**既知の問題**
- 以前に配置した設定ウィンドウは削除されます (上のメモを参照)。
- 設定アプリでは、デバイスの名前を変更できなくなります。 IT 管理者は、[Windows Autopilot for HoloLens 2](hololens2-autopilot.md) のデバイス名テンプレートまたは MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName ノードを使用してデバイスの名前を変更できます。
- イーサネットのページには、常に仮想イーサネットデバイス ("UsbNcm") が表示されます。
- 新しい Microsoft Edge のバッテリ使用量は、UWP アダプター レイヤーによってサポートされている Win32 デスクトップ アプリケーションの性質上、正確ではない可能性があります (近日対応予定の修正プログラムはありません)。

#### <a name="display-color-calibration"></a>色の調整を表示する



この新しい設定では、HoloLens 2 表示に使用する代替カラープロファイルを選択できます。 これにより、特にディスプレイの明るさが低いレベルで、色が正確に表示される場合があります。 画面の色の調整は、設定アプリの [システム > の調整] ページで確認できます。

> [!NOTE]
> この設定により、ディスプレイ ファームウェアに新しいカラー プロファイルが保存されるため、デバイスごとの設定になります (各ユーザー アカウントに固有ではありません)。

##### <a name="how-to-use-display-color-calibration"></a>ディスプレイの色の調整を使用する方法

1. **設定** アプリを起動して、 **[システム] > [調整]** に移動します。
1. **[ディスプレイの色の調整]** で、 **[ディスプレイの色の調整を実行する]** ボタンを選択します。
1. ディスプレイのカラー調整エクスペリエンスが起動し、バイザーが正しい位置にあることを確認することをお勧めします。
1. 指示のダイアログボックスが表示された後、ディスプレイは自動的にグレーで30% の明るさになります。
    > [!TIP]
    > お使いの環境で単色表示されているシーンが表示されない場合は、デバイスの左側にある [明るさ] ボタンを使用して HoloLens 2 の明るさのレベルを手動で調整できます。
1. ボタン1-6 を選択すると、各カラープロファイルが瞬時に表示され、最もよく見られるものを見つけることができます (これは通常、シーンを最もニュートラルにするのに役立つプロファイルで、グレースケール パターンとスキントーンが予想どおりに見えることを意味します)。

    ![カラー調整シーンを表示します。](images/color-cal-ui.png)
    
1. 選択したプロフィールに満足している場合、 **[保存して終了]** ボタンを選択します
1. 変更しない場合は、 **[キャンセル して終了]** ボタンを選択すると、変更が元に戻されます

> [!TIP]
> ディスプレイの色の調整設定を使用する際に留意すべき便利なヒントを次に示します。
> - 必要に応じて、設定からディスプレイの色の調整を再実行することができます
> - デバイス上のすべてのユーザーが以前にカラー プロファイルを変更する設定を使用していた場合は、最新の変更の日付/時刻が [設定] ページに反映されます
> - ディスプレイの色の調整を再実行すると、以前に保存されたカラープロファイルが強調表示され、プロファイル 0 は表示されません (プロファイル 0 はディスプレイの元のカラープロファイルを表します)
> - ディスプレイの元のカラー プロファイルに戻す場合は、[設定] ページから変更できます ([「カラープロファイルをリセットする方法」](#how-to-reset-color-profile)を参照してください)

##### <a name="how-to-reset-color-profile"></a>カラープロファイルをリセットする方法 

HoloLens 2 に保存されたカスタム カラー プロファイルに不満がある場合は、デバイスの元のカラー プロファイルを復元できます。
1. **設定** アプリを起動して、 **[システム] > [調整]** に移動します。
1. **[ディスプレイの色の調整]** で、 **[既定のカラー プロファイルにリセット]** ボタンを選択します。
1. ダイアログ ボックスが開いたら、HoloLens 2 を再起動して変更を適用する準備ができたら、 **[再起動]** を選択します。

#### <a name="top-display-color-calibration-known-issues"></a>最上位のディスプレイの色の調整に関する既知の問題

- [設定] ページでは、カラープロファイルが最後に変更された日時を示すステータス文字列が、設定のページを再度読み込むまで最新の状態になっていません。
    - 回避策: 別の設定ページを選択し、[調整] ページを再選択します。

#### <a name="default-app-picker"></a>既定のアプリ ピッカー

ハイパーリンクをアクティブ化するか、複数のインストール済みアプリでファイルの種類を開くと、そのファイルまたはリンクの種類を処理するインストール済みアプリを選択するよう求めるメッセージが表示されます。 このウィンドウでは、選択したアプリがファイルまたはリンクの種類を「一度のみ」または「常時」として処理するように選択することもできます。

[常時] を選択した後、特定のファイルまたはリンクの種類を処理するアプリを変更する場合は、 **[設定] > [アプリ]** で保存されている既定値をリセットできます。 ページの一番下までスクロールし、[ファイルの種類の既定のアプリ] または [リンクの種類の既定のアプリ] の下にある **[クリア]** ボタンを選択します。 デスクトップ PC の同様の設定とは異なり、個々のファイルの種類の既定値をリセットすることはできません。

#### <a name="per-app-volume-control"></a>アプリごとのボリューム制御

この Windows ビルドでは、ユーザーは各アプリのボリュームレベルを手動で調整できます。 これにより、ユーザーは、必要なアプリに集中することができます。また、複数のアプリを使用する場合は、より適切に聞くことができます。 たとえば、あるアプリのボリュームを下げる必要があるものの、別のユーザーは別の場所でリモート アシスタンスが必要な場合などです。

個々のアプリのボリュームを設定するには **[設定]**  ->  **[システム]**  ->  **[サウンド]** に移動し、[高度なサウンドオプション] で **[アプリのボリュームとデバイスの設定]** を選択します。<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>スワイプして入力する

お客様によっては、入力しようとしている単語の形状をスワイプすることで仮想キーボードの "種類" を短縮し、holographic キーボードのこの機能をプレビューしています。 Holographic キーボードのプレーンで指の先端を渡し、単語の形状をスワイプして、キーボードの平面から指の先端を取り出すことで、一度に1つの単語をスワイプできます。 単語と単語の間ではキーボードから指を離せば、スペース バーを押さなくてもフォローアップ ワードをスワイプできます。 キーボード上で指の動きの後にスワイプ の跡が見えれば、機能が動作しているということです。

この機能は、(携帯電話のディスプレイとは異なり) 指に抵抗を感じないホログラフィック キーボードの性質上、使い方をマスターするのが難しい場合があります。 

### <a name="power-menu-from-start"></a>[スタート] の [電源] メニュー

ユーザーがデバイスをサインアウト、シャットダウン、再起動できる新しいメニュー。 システム更新プログラムが使用可能な場合に表示される HoloLens スタート画面のインジケーター。

#### <a name="how-to-use"></a>使用方法

1. [スタート ジェスチャ](hololens2-basic-usage.md#start-gesture)を使うか、「ホームに移動」と言って HoloLensの開始画面を開きます。

2. ユーザー プロファイルの画像の横にある省略記号アイコン (...) に注意してください。<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. 手または音声コマンド "Power" を使用して、ユーザー プロファイルの画像を選択します。

4. メニューが表示され、デバイスのサインアウト、再起動、シャットダウンのオプションが表示されます。<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. メニュー オプションを選択して、HoloLens をサインアウト、再起動、またはシャットダウンします。 デバイスが [1 つの Microsoft アカウント (MSA) またはローカル アカウント](hololens-identity.md)に設定されている場合は、[サインアウト ] オプションを使用できない場合があります。

6. メニューを閉じるには、他の場所にタッチするか、スタート ジェスチャでスタート メニューを閉じる必要があります。

#### <a name="update-indicator"></a>インジケーターの更新

更新プログラムが利用可能な場合、省略記号アイコンが表示され、再起動によって更新プログラムがインストールされることが示されます。また、メニューオプションも更新プログラムの存在を反映するように変更されます。<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>サインイン画面に複数のユーザーが表示される

以前にサインイン画面には、最近サインインしたユーザーだけでなく、"その他のユーザー" エントリポイントのみが表示されていました。 複数のユーザーがデバイスにサインインしている場合、これでは十分ではないというお客様からのフィードバックを受け取りました。 ユーザー名を再入力する必要がありました。

この Windows ビルドで導入された [PIN 入力] フィールドの右側にある **他のユーザー** を選択すると、サインイン画面に、以前にデバイスにサインインしている複数のユーザーが表示されます。 これにより、ユーザーは自分のユーザープロファイルを選択し、Windows Hello の資格情報を使用してサインインできます。 新しいユーザーは、[ **アカウントの追加** ] ボタンを使用して、[その他のユーザー] ページからデバイスに追加することもできます。

[その他のユーザー] メニューの [その他のユーザー] ボタンをクリックすると、デバイスに最後にサインインしたユーザーが表示されます。 このボタンを選択すると、このユーザーのサインイン画面に戻ります。

![サインイン画面の既定値。](./images/multiusers1.jpg)

<br>

![サインイン画面他のユーザー。](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C 外部マイクのサポート

> [!IMPORTANT]
> USB マイクを **接続すると、入力デバイス として自動的に設定されません**。 一連の USB C ヘッドホンに接続すると、ヘッドホンのオーディオがヘッドホンに自動的にリダイレクトされることがユーザーに確認されますが、HoloLens OS は、他の入力デバイスの上にある内部マイク配列の優先順位を設定します。 **USB-C マイクを使用するには、次の手順に従います。**

ユーザーは、 **[サウンド]** 設定パネルを使用して USB-C 接続外部マイク を 選択できます。 USB-C マイクは、通話や録音などに使用できます。

**設定** アプリを開いて **[システム]**  >  **[サウンド]** を選択します。

![サウンド設定。](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> 外部マイクを **Remote Assist** で使用するには、[サウンド デバイスの管理] ハイパーリンクをクリックする必要があります。
>
> 次に、ドロップダウンを使用して、外部マイクを **[既定]** または **[通信の既定値]** に設定します。 **[既定]** を選択すると、外部マイクはどこででも使用されます。
>
> **[通信の既定値]** を選択すると、外部マイクは Remote Assist や他の通信アプリで使用されますが、HoloLens マイク 配列は他のタスクにも引き続き使用できます。

![サウンド デバイスを管理する。](images/usbc-mic-2.png)

<br>

![マイクの既定値を設定します。](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Bluetooth のマイクのサポートについてはどうですか?

残念ながらBluetoothマイクは現在、デバイスでサポートHoloLens 2。

#### <a name="troubleshooting-usb-c-microphones"></a>USB-C マイクのトラブルシューティング

一部の USB-C マイクでは、マイクとスピーカーの両方として誤って報告される *点に* 注意してください。 これはマイクの問題であり、マイクには問題HoloLens。 これらのマイクの 1 つを電源に接続HoloLens音が失われる可能性があります。 さいわい、簡単な修正があります。  

システム **設定** では、組み込みのスピーカー (アナログ機能オーディオ ドライバー) を既定のデバイス として明示的  ->    ->  に **設定します**。  HoloLensマイクが削除され、後で再接続された場合でも、この設定を覚えておく必要があります。

![USB-C マイクのトラブルシューティング。](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>キオスクのビジター自動ログオン

この新機能により、キオスク モードでビジター アカウントの自動ログオンを使用できます。

AAD 以外の構成の場合は、訪問者の自動ログオン用にデバイスを構成します。

1. 次のプロビジョニング パッケージを作成します。
    1. ビジター アカウント **を許可するランタイム設定/AssignedAccess** を構成します。
    1. 後で管理できるよう、必要に応じてデバイスを MDM **(ランタイム設定/ワークプレース/登録)** に登録します。
    1. ローカル アカウントを作成しない
1. [プロビジョニング パッケージ を適用します](hololens-provisioning.md)。

AAD 構成の場合、ユーザーは、この変更を行わずに、現在、このようなことを実現できます。 キオスク モード用に構成された AAD 参加済みデバイスは、サインイン画面から 1 つのボタン タップで Visitor アカウントにサインインできます。 ビジター アカウントにサインインすると、ビジターがスタート メニューから明示的にサインアウトするか、デバイスが再起動されるまで、デバイスは再度サインインを求めるメッセージを表示しません。

ビジター自動ログオンは、カスタム [OMA-URI ポリシーを使用して管理](/mem/intune/configuration/custom-settings-windows-10) できます。

- URI 値: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| ポリシー  | 説明   | 構成  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | キオスクへの訪問者の自動ログオンを許可する   | 1 (はい)、0 (いいえ、既定値)。  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>キオスク モードで新設定 Edge アプリを使用する

キオスクにアプリを [含めた](hololens-kiosk.md)場合、IT 管理者は多くの場合、キオスクにアプリを追加しますが、アプリ ユーザー モデル ID (AUMID) を使用します。 設定 アプリと Microsoft Edge アプリの両方が新しいアプリと見なされ、それらのアプリに AUMID を使用する古いアプリキオスクとは異なるので、新しい AUMID を使用するには更新する必要があります。

キオスクを変更して新しいアプリを含める場合は、新しい AUMID に を追加し、古いアプリを残することをお勧めします。 これにより、ユーザーが OS を更新するときに簡単に切り替わるので、キオスクを意図した方法で使用し続ける新しいポリシーを受け取る必要がなされます。

| アプリ                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| 古い 設定 アプリ       | HolographicSystemSettings_cw5n1h2txyewy!アプリ            |
| 新設定アプリ       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!アプリ |
| 古Microsoft Edgeアプリ | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| 新Microsoft Edgeアプリ | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>エラー処理のためのキオスク モードの動作の変更

以前のビルドでは、デバイスにキオスク構成 (グローバル割り当てアクセスと AAD グループ メンバー割り当てアクセスの両方の組み合わせ) がある場合、AAD[](hololens-kiosk.md#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode)グループ メンバーシップが失敗した場合、ユーザーには "何も表示されません" メニューが表示されます。

このリリースWindows、AAD グループ キオスク モード中に障害が発生した場合、キオスク エクスペリエンスはグローバル キオスク構成 (存在する場合) にフォールバックします。

### <a name="new-settings-uris-for-page-settings-visibility"></a>ページ設定可視性の新しい 設定 URI

[Holographic Windowsバージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2)では[、設定/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)ポリシーを追加して、設定 アプリ内に表示されるページを制限しました。 PageVisibilityList は、IT 管理者がシステム設定アプリの特定のページを表示またはアクセスできないようにしたり、または指定されたページ以外のすべてのページで同様に行うことを許可するポリシーです。

[Page[設定 Visibility]に](settings-uri-list.md)アクセスした場合は、この CSP を使用する手順と、以前のリリースで使用できる URI の一覧を確認できます。

IT 管理者が管理できる使用可能な URI の一設定一覧を拡張しています。 これらの URI の一部は、新しいアプリ内で新しく使用可能な領域設定されています。 設定/PageVisibilityList ポリシーを使用している場合は、次の一覧を確認し、必要に応じて許可またはブロックされたページを調整します。

> [!NOTE]
> **非推奨: ms-settings:network-proxy**
>
> これらの新しいビルドでは、1 つの設定ページが非推奨とされます。 古い **[ネットワーク & インターネット**  >  **プロキシ]** ページは、グローバル設定として使用できなくなりました。 新しい接続ごとのプロキシ設定は、[ネットワーク]の [インターネット Wi-Fi プロパティ] & [ネットワーク] [インターネット イーサネットのプロパティ] &  >    >  **で**  >  **確認**  >  **できます**。

<br>

| [設定] ページ                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Apps > Apps &機能                               | `ms-settings:appsfeatures`                         |
| [アプリ> Apps &機能>詳細オプション          | `ms-settings:appsfeatures-app`                     |
| オフライン >アプリ                                  | `ms-settings:maps`                                 |
| オフライン >アプリとダウンロード > マップ                  | `ms-settings:maps-downloadmaps`                    |
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
| System > Sound > Manage sound devices              | `ms-settings:sound-devices`                        |
| System > Storage > Configure Storage Sense         | `ms-settings:storagepolicies`                      |
| Time & Language > Date & time                        | `ms-settings:dateandtime`                          |
| Time & Language > Keyboard                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| セキュリティ &の更新>回復&リセット               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>更新された URI

以前は、次の 2 つの URI は、指定されたページにユーザーを直接移動するのではなく、メインの更新ページのみをブロックしました。 ページに移動するために、次の項目が更新されました。

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>アプリを使用したフォールバック診断設定構成

アプリの設定、ユーザーはフォールバック診断 の動作[を構成できます](hololens-diagnostic-logs.md)。 [アプリ] 設定プライバシーのトラブルシューティング  ->  **ページに移動** して、この設定を構成します。

> [!NOTE]
> デバイスに対して MDM ポリシーが構成されている場合、ユーザーは、その動作をオーバーライドできます。  

### <a name="share-things-with-nearby-devices"></a>近くのデバイスと共有する

PC と他の HoloLens 2 デバイスの両方を含む、Windows 10 デバイスによって近いデバイスとHoloLens 2します。 システム共有エクスペリエンスで設定を試して、ファイルまたは URL を HoloLens  ->    ->   PC に共有できます。 詳細については、「 で近くのデバイスと物を共有する方法」[を参照Windows 10。](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)

この機能は [、Connectivity/AllowConnectedDevices を使用して管理できます](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)。

### <a name="new-os-diagnostic-traces"></a>新しい OS 診断トレース

設定アプリ内の前のトラブルシューティングツールに加えて、新しいトラブルシューティングツールが追加されました。 OS 更新プログラム用の新しい設定アプリが追加されました。 **設定**  ->  **更新の &amp; セキュリティ**  >  **トラブルシューティング**  >  **Windows Update** に移動し、[**開始**] を選択します。 これにより、OS の更新に関する問題を再現しながら、IT またはサポートによるトラブルシューティングを容易にするために、トレースを収集することができます。

### <a name="delivery-optimization-preview"></a>配信の最適化のプレビュー

この HoloLens の更新により、Windows Holographic for Business は配信の最適化の設定を有効にして、複数の HoloLens デバイスからのダウンロードにかかる帯域幅の消費を削減します。 推奨されるネットワーク構成と共に、この機能の詳細な説明については、[「Windows 10 更新プログラムの配信の最適化」](/windows/deployment/update/waas-delivery-optimization)を参照してください。

次の設定は管理画面の一部として有効にされ、[Intune から構成できます](/mem/intune/configuration/delivery-optimization-settings)。

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

このプレビューの内容に関する注意点を次に示します。

- HoloLens のサポートは、このプレビューでは OS の更新プログラムにのみ制限されます。
- Windows Holographic for Business は、HTTP ダウンロード モードと [Microsoft 接続キャッシュ エンドポイント](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)からのダウンロードのみをサポートします。ピア ツー ピア のダウンロード モードとグループの割り当ては、現時点では HoloLens デバイスではサポートされていません。
- HoloLens では、Windows Server Update Services エンドポイントのデプロイまたは配信の最適化はサポートされていません。
- トラブルシューティングを行う場合は、接続キャッシュ サーバーでの診断、または **[設定]**  >  **[アップデートとセキュリティ]**  >   **[トラブルシューティング]**  >   **[Windows Update]** を介して HoloLens 上で HoloLens のトレースを収集する必要があります。

### <a name="it-admin---update-checklist"></a>IT 管理者-更新プログラムのチェックリスト

このチェックリストは、現在のデバイス管理構成に影響を与える可能性がある、この機能更新プログラムに追加される新しい項目、または使用を開始する新機能を理解するのに役立ちます。

#### <a name="updates-to-kiosk-mode"></a>キオスクモードの更新プログラム

[**キオスクモードで新しいアプリの新しい AUMIDs を**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)✔️します。

キオスクで設定アプリまたは Microsoft Edge アプリを以前に使用していた場合、これらのアプリは別のアプリ ID を使用する新しいアプリに置き換えられました。 以下 [のキオスクモードで新しいアプリの新しい AUMIDs](#use-the-new-settings-and-edge-apps-in-kiosk-modes) を読むことを強くお勧めします。 これにより、キオスクで設定アプリを引き続き使用するか、新しい Microsoft Edge アプリを含めることができます。 これらの変更は、今すぐ実行し、すべてのデバイスに展開して、更新をスムーズに移行できるようにすることができます。

[**キオスクの✔️ビジターの自動ログオン**](#visitor-auto-logon-for-kiosks): 

訪問者がキオスクに自動的にログインできるようになりました。 この動作は既定で有効になっていますが、管理と無効化を行うことができます。

✔️ [**キオスクモードのエラー**](#kiosk-mode-behavior-changes-for-handling-of-failures)処理の改善:

サインインしている AAD ユーザーの AAD グループメンバーシップが正常に決定されていない場合、[スタート] メニュー (存在する場合) にはグローバルキオスク構成が使用されます。それ以外の場合、ユーザーには空の [スタート] メニューが表示されます。 空の [スタート] メニューは、直接設定できる構成ではありませんが、キオスクを使用している場合は、この新しい処理によってサポート部門に通知されることがあります。これは、構成に適用される可能性があります。また、割り当てられているアクセス構成に新しい調整を加える必要があります。

#### <a name="updates-to-page-settings-visibility"></a>ページ設定表示の更新

[**ページ設定可視性の新しい設定 uri** ✔️](#new-settings-uris-for-page-settings-visibility)

現在、[ページ設定可視性](settings-uri-list.md)を使用している場合は、許可またはブロックされている既存の uri に対して調整を行うことができます。

#### <a name="updates-for-your-wdac-policy"></a>WDAC ポリシーの更新
✔️、以前に wdac 経由で Microsoft Edge をブロックしていた場合は、wdac ポリシーを更新する必要があります。 次の内容を確認し、提供されているサンプルコードを使用してください。
#### <a name="enable-new-endpoints-for-edge"></a>エッジの新しいエンドポイントを有効にする
✔️プロキシやファイアウォールなどのネットワークエンドポイントを構成するインフラストラクチャがある場合は、新しい Microsoft Edge アプリに対してこれらの新しいエンドポイントを有効にしてください。

#### <a name="newly-configurable-items"></a>新しく構成可能な項目

[フォールバック診断の構成](#configuring-fallback-diagnostics-via-settings-app)✔️: フォールバック診断を収集するかどうかを構成できます。

[近くのデバイスで項目を共有](#share-things-with-nearby-devices)✔️: 新しい近くにある共有機能を無効にすることができます。

[新しい Microsoft Edge のポリシー設定を構成](#configuring-policy-settings-for-the-new-microsoft-edge)✔️には、Microsoft Edge で使用できるようになった新たな構成を確認します。

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


## <a name="windows-holographic-version-20h2--may-2021-update"></a>WindowsHolographic、バージョン20H2 –2021年5月更新
- ビルド19041.1146

更新プログラムの機能強化と修正:
- この月間品質更新プログラムには、重要な変更は含まれていません。最新のビルド (Windows Holographic、バージョン 21h1) を試すことをお勧めします。

## <a name="windows-holographic-version-1903---may-2021-update"></a>WindowsHolographic、バージョン 1903-2021 更新プログラム
- ビルド18362.1110

更新プログラムの機能強化と修正:
- この月間品質更新プログラムには、注目すべき変更は含まれていません。 **このビルドは、月ごとのサービス更新を受信しなく** なります。 最新のビルド (Windows Holographic、バージョン 21h1) を試すことをお勧めします。



## <a name="windows-holographic-version-20h2---april-2021-update"></a>WindowsHolographic、バージョン 20H2-2021 年4月更新
- ビルド19041.1144

更新プログラムの機能強化と修正:

- 基幹業務アプリケーションのインストール状態レポートに関する問題を修正しました。

## <a name="windows-holographic-version-1903---april-2021-update"></a>WindowsHolographic、バージョン 1903-2021 年4月更新
- ビルド18362.1108

更新プログラムの機能強化と修正:

- ローカルアカウントのパスワードを変更しようとしたときに設定アプリがクラッシュする問題に対処します。


## <a name="windows-holographic-version-20h2---march-2021-update"></a>WindowsHolographic、バージョン 20H2-2021 年3月更新
- ビルド19041.1140

更新プログラムの機能強化と修正:

- LowLagPhotoCapture を使用して HoloLens 2 写真をキャプチャするために、アドバンス photocapture またはを使用しているお客様は、写真がキャプチャされてから最大3秒間カメラを取得できるようになりました。
- デバイスポータルサービスのメモリリークを修正しました。この問題により、他のアプリケーションがメモリの割り当てに失敗する原因となったサービスによるメモリ使用量が増加しました。
- 段階的なロールアウトに登録されたユーザーがデバイスにサインインできないという問題を修正しています。

## <a name="windows-holographic-version-1903---march-2021-update"></a>WindowsHolographic、バージョン 1903-2021 年3月更新
- ビルド18362.1102

更新プログラムの機能強化と修正:

- デバイスポータルサービスのメモリリークを修正しました。この問題により、他のアプリケーションがメモリの割り当てに失敗する原因となったサービスによるメモリ使用量が増加しました。

## <a name="windows-holographic-version-20h2---february-2021-update"></a>WindowsHolographic、バージョン 20H2-2021 年2月更新
- ビルド19041.1136

更新プログラムの機能強化と修正:

- デバイスの初期セットアップとアプリの更新プログラムの保存に関する問題を修正します。
- 今後の HoloLens リリースでのアップグレードとフライトに関する問題に対処します。
- HoloLens デバイスから、使用されていないプレインストールされた証明書を eSIM ルートストアから削除しました。

## <a name="windows-holographic-version-1903---february-2021-update"></a>WindowsHolographic、バージョン 1903-2021 更新プログラム
- ビルド18362.1098

この月間品質更新プログラムには、重要な変更は含まれていません。 Windows Holographic バージョン2004の最新のビルドを試すことをお勧めします。

## <a name="windows-holographic-version-20h2---january-2021-update"></a>WindowsHolographic、バージョン 20H2-2021 年1月の更新プログラム
- ビルド19041.1134

更新プログラムの機能強化と修正:

- デバイスに多数のユーザーがいるときに、起動、再開、ユーザー切り替えの際のパフォーマンスが向上しました。
- 研究モード の arm32 サポートを [追加しました](/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)。

## <a name="windows-holographic-version-1903---january-2021-update"></a>WindowsHolographic バージョン 1903 - 2021 年 1 月更新
- ビルド 18362.1091

この毎月の品質更新プログラムには、重要な変更は含められないので、Windows Holographic バージョン 2004 の最新のビルドを試しに行ってみ事をお勧めしています。

## <a name="windows-holographic-version-20h2--december-2020-update"></a>WindowsHolographic バージョン 20H2 – 2020 年 12 月の更新プログラム
- ビルド 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>HoloLens 2 経由でアプリをインストールアプリ インストーラー

新しい **機能 (アプリ インストーラー)** を追加して、アプリケーションをデバイスにシームレスにインストールHoloLens 2しています。 この機能は、アン **マネージド デバイスでは既定でオンになります**。 企業の中断を防ぐために、現時点では、マネージド デバイスでアプリ インストーラー **を** 使用できません。  

次の条件に当てはまる場合、デバイスは "マネージド" と見なされます。
- MDM [登録済み](hololens-enroll-mdm.md)
- プロビジョニング パッケージ [を使用して構成する](hololens-provisioning.md)
- ユーザー [ID が](hololens-identity.md) Azure AD

開発者モードを有効にしたり、アプリを使用したりせずにアプリをインストールデバイス ポータル。  (USB 経由または Edge 経由で) Appx バンドルをデバイスにダウンロードし、エクスプローラー の Appx バンドルに移動するだけで、インストールを開始するように求めるメッセージが表示されます。  または、Web [ページ からインストールを開始します](/windows/msix/app-installer/installing-windows10-apps-web)。  MDM の LOB アプリ展開機能を使用して Microsoft Store またはサイドロードからインストールするアプリと同様に、アプリは署名ツールを[](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)使用してデジタル署名[](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)する必要があります。また、アプリを展開する前に、署名に使用される証明書が HoloLens デバイスによって信頼されている必要があります。

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

このフローをテストするには、ユニバーサル[サンプル Windowsサンプル GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)サンプル アプリを参照してください。

を使用してアプリをインストール[するプロセスの詳細については、HoloLens 2 を使用してアプリ インストーラー。](app-deploy-app-installer.md)  

![を使用した MRTK のアプリ インストーラー。](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>更新プログラムの機能強化と修正:

- 手の追跡では、以前に手が失われた可能性がある多くの新しいケースで追跡が維持されます。  これらの新しいケースの一部では、手のひらの位置だけがユーザーの実際の手に基づいて更新され続け、もう一方の関節は前の姿勢に基づいて推論されます。  この変更は、スラップ、スロー、傾斜、アプリの適用などの動きの追跡の一貫性を向上させるのに役立ちます。  また、手が表面に近い場合やオブジェクトを保持している場合にも役立ちます。  手の関節が推論されている場合 [、関節ごとの](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) 精度の値は 、"高" ではなく "近似" に設定されます。
- アカウントの PIN のリセットでAzure ADが表示される問題を修正しました。
- ET、Iris を設定アプリ、新しいユーザー、または通知トーストから起動すると、起動後の OOBE クラッシュがはるかに少なく表示される必要があります。
- ユーザーは、OOBE から正しいタイム ゾーンが出てくる必要があります。

## <a name="windows-holographic-version-1903--december-2020-update"></a>WindowsHolographic バージョン 1903 – 2020 年 12 月の更新プログラム
- ビルド 18362.1088

この毎月の品質更新プログラムには、特に重要な変更が含まれているのではなく、最新の Windows Holographic バージョン 20H2 – 2020 年 12 月の更新プログラムと、ビルドに追加された新しい アプリ インストーラー 機能をお試しください。


## <a name="windows-holographic-version-20h2"></a>WindowsHolographic バージョン 20H2
- ビルド 19041.1128

WindowsHolographic バージョン 20H2 が利用可能にされ、ユーザーや IT プロフェッショナルにHoloLens 2機能のセットが提供されます。 自動目のポジショニングから、設定 の証明書マネージャー、キオスク モード機能の向上、および新しい Autopilot セットアップ機能まで。 この新しい更新により、IT チームは、HoloLens デバイスの構成と管理をきめ細かく制御し、ユーザーにさらにシームレスなホログラフィック エクスペリエンスを提供できます。 

この最新リリースは、バージョン 2004 の月次更新プログラムですが、今回は新機能が含まれる予定です。 メジャー ビルド番号は変わりません。Windows Update は、バージョン 2004 (ビルド 19041) への月次リリースを示します。 [バージョン情報] 画面で [ビルド番号] を設定 >、利用可能な最新のビルド 19041.1128 以上を確認できます。 最新リリースに更新するには、設定 アプリを開き、[& Security の更新] に移動して、[更新プログラムの確認] をタップします。 更新プログラムを管理する方法の詳細については、「更新プログラムHoloLens管理[する」をHoloLensしてください](hololens-updates.md)。

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Holographic バージョン 20H2 Windowsの新機能  

| 機能                                              | 説明                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [視線の自動調整サポート](hololens-release-notes.md#auto-eye-position-support) | ユーザーが目の追跡の調整を行わずに、目の位置を積極的に計算します。   |
| [Certificate Manager](hololens-release-notes.md#certificate-manager)   | 新しい簡単な方法で、新しいアプリから証明書をインストール設定できます。     |
| [USB からの自動起動プロビジョニング](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | USB ドライブにパッケージをプロビジョニングすると、OOBE のプロビジョニング ページが自動的に表示されます。                                                         |
| [OOBE でのプロビジョニング パッケージの自動確認](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | プロビジョニング パッケージは、プロビジョニング ページから OOBE 中に自動的に適用されます。                                                         |
| [UI を使用しない自動プロビジョニング](hololens-release-notes.md#automatic-provisioning-without-using-ui) | プロビジョニングの自動起動と自動確認を組み合わせる方法。 |
| [Autopilot を使用した接続Wi-Fiする](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | イーサネット アダプターを必要とせずにWi-Fiデバイスからオートパイロットを使用します。 |
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

### <a name="auto-eye-position-support"></a>視線の自動調整サポート

このHoloLens 2、目の位置を使用すると、正確なホログラムの配置、快適な表示エクスペリエンス、および表示品質の向上が可能になります。 視線は、視線追跡計算の一部として内部的に計算されます。 ただし、これには、エクスペリエンスで視線の入力が必要ない場合でも、各ユーザーが視線追跡の調整を実行する必要があります。

**視線の自動調整 (AEP)** は、ユーザーの目の位置を計算するための操作のない方法でこれらのシナリオを可能にします。 自動目の位置は、ユーザーがデバイスを置いた瞬間から自動的にバックグラウンドで作業を開始します。 ユーザーが前の目追跡の調整を行っていない場合、自動目の位置は、20 - 30 秒の処理時間の後に、表示システムにユーザーの目の位置を提供し始める。 ユーザー データはデバイスに保持されません。そのため、ユーザーが離れてデバイスを再度起動した場合、またはデバイスが再起動またはスリープからウェイクアップした場合は、このプロセスが繰り返されます。

調整されていないユーザーがデバイスを装着した場合、視線の自動調整機能によるシステム動作の変更がいくつかあります。 このコンテキストでは、未調整のユーザーは、以前にデバイスで目の追跡の調整プロセスを実行していないユーザーを指します。

| アクティブなアプリケーション | 以前の動作 | Windows Holographic、バージョン 20H2 アップデートからの動作 |
|:-------------------|:-----------------|:-----------------------------------|
| 非視線対応アプリまたはホログラフィック シェル |視線追跡の調整プロンプト ダイアログが表示されます。 | プロンプトは表示されません。 |
| 視線対応アプリ | 視線追跡の調整プロンプト ダイアログが表示されます。 | 視線追跡の調整プロンプトは、アプリケーションが視線ストリームにアクセスした場合にのみ表示されます。 |

ユーザーが非視線対応アプリケーションから視線データにアクセスするアプリケーションに移行すると、調整プロンプトが表示されます。 

他のすべてのシステム動作は、現在のユーザーがアクティブな目追跡調整を行っていない場合と似ています。 たとえば、One-handed Start ジェスチャは有効になりません。 初期設定の既定のエクスペリエンスに変更はありません。

目の視線入力データまたは非常に正確なホログラムの配置を必要とするエクスペリエンスの場合は、未調整のユーザーに視線追跡の調整を実行することをお勧めします。 これは、目の追跡の調整プロンプトから、またはスタート メニューから 設定 アプリを起動し **、[System > Calibration > Eye Calibration > Run eye calibration**] を選択することでアクセスできます。

この情報は、後で他の調整 [情報 と一緒に確認できます](hololens-calibration.md#auto-eye-position-support)。 

### <a name="certificate-manager"></a>証明書マネージャー

- 新しい証明書マネージャーを使用して、デバイスのセキュリティとコンプライアンスのための監査、診断、検証ツールが改善されました。 この機能を使用すると、商用環境で大規模に証明書を展開、トラブルシューティング、検証できます。

Holographic Windows 20H2 では、アプリに証明書マネージャー HoloLens 2 設定しています。 [Update **設定 > Security & Certificates] に>移動します**。 この機能を使用すると、デバイス上の証明書を表示、インストール、削除する簡単で使い分け的な方法が提供されます。 新しい証明書マネージャーにより、管理者とユーザーは、デバイスのセキュリティと準拠を維持するために、監査、診断、検証ツールが改善されました。 

-   **監査:** 証明書が正しく展開されていることを検証する機能、または証明書が適切に削除されていることを確認する機能。 
-   **診断:** 問題が発生した場合は、デバイスに適切な証明書が存在する場合は、時間を節約し、トラブルシューティングに役立ちます。 
-   **検証:** 証明書が目的の目的に対応し、機能することを確認すると、特に商用環境で大規模に証明書を展開する前に、かなりの時間を節約できます。

一覧内の特定の証明書をすばやく検索するには、名前、ストア、または有効期限で並べ替えるオプションがあります。 ユーザーは証明書を直接検索することもできます。 個々の証明書のプロパティを表示するには、証明書を選択し、[情報] を **クリックします**。 

証明書のインストールでは現在、.cer ファイルと .crt ファイルがサポートされています。 デバイス所有者は、ローカル コンピューターと現在のユーザーに証明書をインストールできます。 他のすべてのユーザーは、現在のユーザーにのみインストールできます。 ユーザーは、UI から直接インストールされた証明書設定できます。 証明書が他の方法でインストールされている場合は、同じメカニズムでも削除する必要があります。

#### <a name="to-install-a-certificate"></a>証明書をインストールするには: 

1.  Connect PC HoloLens 2に接続します。
1.  インストールする証明書ファイルを、自分の証明書ファイルの場所にHoloLens 2。
1.  [App 設定 **Update > Security & Certificates**> に移動し、[ 証明書のインストール] を選択します。
1.  [ **ファイルのインポート]** をクリックし、証明書を保存した場所に移動します。
1.  [ストア **の場所] を選択します**。
1.  [証明書 **ストア] を選択します**。
1.  **[インストール]** をクリックします。

これで、証明書がデバイスにインストールされます。

#### <a name="to-remove-a-certificate"></a>証明書を削除するには: 
1. [App 設定 **Update > Security > に移動します**。
1. 検索ボックスで名前で証明書を検索します。
1. 証明書を選択します。
1. [削除] **をクリックします。**
1. 確認を求められたら、 **[はい]** を選択します。

![アプリの証明書ビューアー設定します。](images/certificate-viewer-device.jpg)

![証明書 UI を使用して証明書をインストールする方法を示す図。](images/certificate-device-install.jpg)

この情報は、後で新 [しい [証明書マネージャー] ページで確認できます](certificate-manager.md)。

### <a name="auto-launch-provisioning-from-usb"></a>USB からの自動起動プロビジョニング

- OOBE 中にプロビジョニング パッケージを備えた USB ドライブが使用されている場合、ユーザーの操作を減らして自動化されたプロセス。

このリリースより前は、ユーザーは、ボタンの組み合わせを使用してプロビジョニングするために、OOBE 中にプロビジョニング画面を手動で起動する必要があります。 これで、ユーザーは USB ストレージ ドライブ上のプロビジョニング パッケージを使用して、ボタンの組み合わせをスキップできます。 

1. OOBE の最初の対話可能な瞬間にプロビジョニング パッケージを使用して USB ドライブを接続する
1. デバイスをプロビジョニングする準備ができたら、プロビジョニング ページが表示されたプロンプトが自動的に開きます。 

注: デバイスの起動中に USB ドライブが接続された状態の場合、OOBE は既存の USB ストレージ デバイスを列挙し、追加の USB ストレージ デバイスが接続されているのを監視します。

OOBE 中にプロビジョニング パッケージを適用する方法の詳細については、プロビジョニングに関するドキュメント[HoloLens参照](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)してください。

USB からの[自動起動プロビジョニングに関](hololens-provisioning.md#auto-launch-provisioning-from-usb)する追加情報については、プロビジョニングに関するページHoloLens参照してください。

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
1. デバイスHoloLens 2 OOBE に起動すると、USB ドライブ上のプロビジョニング パッケージが自動的に検出され、プロビジョニング ページが起動します。
1. 10 秒後、デバイスによってプロビジョニング パッケージが自動的に適用されます。 

これでデバイスが構成され、[プロビジョニングに成功 [しました] 画面が表示されます](hololens-provisioning.md#automatic-provisioning-without-using-ui)。

### <a name="using-autopilot-with-wi-fi-connection"></a>Autopilot を使用して接続Wi-Fiする
- 接続されているデバイスで Autopilot が機能する機能を有効にすることで、ハードウェアのニーズを減らして、イーサネットに USB-C アダプターWi-Fi必要が取り除かれました。

OOBE 中に、Wi-Fi HoloLens 2接続すると、OOBE によってデバイスの Autopilot プロファイルが確認されます。 見つかった場合は、AAD 参加フローと登録フローの残りの部分を完了するために使用されます。 つまり、USB-C または Wi-Fi から USB-C アダプターへのイーサネットの使用は要件ではなくなりましたが、OOBE の開始時に提供されている場合は引き続き機能します。 デバイスの[Autopilot の詳細については、HoloLens 2してください](hololens2-autopilot.md)。

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP と Autopilot
- デバイスのリセットまたは再フラッシュを使用しても、デバイスをテナントにロックすることで、組織のテナント上のデバイスを保持します。 プロビジョニングを介した でのアカウントの作成を禁止することで、セキュリティを強化します。 

HoloLens 2 [Holographic バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2)の現在、Windowsデバイスで TenantLockdown CSP がサポートされています。 

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP は、HoloLens 2 が Autopilot のみを使用して MDM 登録に関連付けられるようにします。 TenantLockdown CSP の RequireNetworkInOOBE ノードが HoloLens 2 で true または false (最初に設定された) 値に設定されると、その値は、再フラッシュ、OS 更新プログラムなどにもかかわらずデバイスに残ります。 

HoloLens 2 で TenantLockdown CSP の RequireNetworkInOOBE ノードが true に設定されると、OOBE は、ネットワーク接続後、Autopilot プロファイルが正常にダウンロードおよび適用されるまで無期限に待機します。 

HoloLens 2 で TenantLockdown CSP の RequireNetworkInOOBE ノードが true に設定されると、OOBE では次の操作が許可されなくなります。 
- ランタイム プロビジョニングを使用したローカル ユーザーの作成 
- ランタイム プロビジョニングによる Azure AD への参加操作の実行 
- OOBE エクスペリエンスでデバイスの所有者を選択する 

#### <a name="how-to-set-this-using-intune"></a>Intune を使用してこれを設定する方法 
1. 以下に示すように、カスタム OMA URI デバイス構成プロファイルを作成し、RequireNetworkInOOBE ノードに true を指定します。
OMA-URI 値は ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE である必要があります

   > [!div class="mx-imgBorder"]
   > ![OMA-URI を使用してテナント lockdown を設定します。](images/hololens-tenant-lockdown.png)

1. グループを作成し、デバイス構成プロファイルをそのデバイス グループに割り当てます。 

1. 前の手順で作成したグループの HoloLens 2 デバイス メンバーを作成し、同期をトリガーします。  

Intune ポータルで、デバイス構成が正常に適用されていることを確認します。 このデバイスの構成が HoloLens 2 デバイスに正常に適用されると、TenantLockdown の効果がアクティブになります。

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Intune を使用して HoloLens 2 で TenantLockdown の RequireNetworkInOOBE の設定を解除する方法 
1. 上で作成したデバイス構成が以前に割り当てられていたデバイス グループから HoloLens 2 を削除します。 

1. 以下に示すように、カスタム OMA URI ベースのデバイス構成プロファイルを作成し、RequireNetworkInOOBE に false を指定します。 OMA-URI 値は ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE である必要があります

   > [!div class="mx-imgBorder"]
   > ![Intune の OMA-URI URI を使用して RequireNetworkInOOBE を false に設定するスクリーンショット。](images/hololens-tenant-lockdown-false.png)

1. グループを作成し、デバイス構成プロファイルをそのデバイス グループに割り当てます。

1. 前の手順で作成したグループの HoloLens 2 デバイス メンバーを作成し、同期をトリガーします。

Intune ポータルで、デバイス構成が正常に適用されていることを確認します。 このデバイスの構成が HoloLens 2 デバイスに正常に適用されると、TenantLockdown の効果が非アクティブになります。

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>TenantLockdown が true に設定された後、HoloLens で Autopilot プロファイルが割り当て解除された場合、OOBE 中にどうなりますか? 
OOBE は、Autopilot プロファイルがダウンロードされるのを無期限に待機し、次のダイアログが表示されます。 TenantLockdown の影響を取り除くには、最初に Autopilot のみを使用してデバイスを元のテナントに登録し、TenantLockdown CSP によって導入された制限を取り除く前に、前の手順で説明したように RequireNetworkInOOBE の設定を解除する必要があります。

![ポリシーがデバイスに適用される時のデバイス内ビュー。](images/hololens-autopilot-lockdown.png)

この情報は、 [Tenantlockdown CSP および自動操縦](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)の残りの自動操縦と共に見つかりました。

### <a name="global-assigned-access--kiosk-mode"></a>グローバルに割り当てられたアクセス: キオスクモード
- キオスクモードをシステムレベルで適用する新しいキオスク方法を有効にすることにより、キオスクの Id 管理を減らしました。

この新機能により、IT 管理者は、システムレベルで適用可能な複数のアプリキオスクモード用の HoloLens 2 デバイスを構成し、システム上の id との関係はなく、デバイスにサインインするすべてのユーザーに適用することができます。 この新機能の詳細については[HoloLens キオスクモード](hololens-kiosk.md)」を参照してください。

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
| MixedReality\AADGroupMembershipCacheValidityInDays | グループメンバーシップのキャッシュを使用して、Azure AD グループを対象とするキオスクの Azure AD 日数を制御します。 | 次を参照してください。                                                           |

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
- [AllowAddProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](/windows/client-management/mdm/remotelock-csp)

この2つの新しいポリシー Allowaddのパッケージと Allowremoveのパッケージは、 [一般的なデバイスの制限](hololens-common-device-restrictions.md)に追加されています。

> [!NOTE]
> [remotelock](/windows/client-management/mdm/remotelock-csp)に関しては、HoloLens は/Vendor/MSFT/RemoteLock/Lock 構成のみをサポートします。 リセットや回復などの PIN を処理する構成はサポートされていません。

### <a name="new-power-policies-for-hololens-2"></a>HoloLens 2 の新しい電源ポリシー
- 電源ポリシーを使用してスリープまたはロックを HoloLens する場合のその他のオプション。 

これらの新しく追加されたポリシーにより、管理者はアイドルタイムアウトなどの電源状態を制御できるようになります。 個々のポリシーの詳細を確認するには、そのポリシーのリンクをクリックしてください。

|     ポリシードキュメントのリンク                |     メモ                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Windows 構成デザイナーで使用する値の例を次に示します。`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Windows 構成デザイナーで使用する値の例を次に示します。`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Windows 構成デザイナーで使用する値の例 (100)                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Windows 構成デザイナーで使用する値の例 (100)                                                                          |
|     [スタンドアロン](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows 構成デザイナーで使用する値の例を次に示します。`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows 構成デザイナーで使用する値の例を次に示します。`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

DisplayOffTimeoutOnBattery と DisplayOffTimeoutPluggedIn 用のこれら2つの新しいポリシーは、 [デバイスの一般的な制限](hololens-common-device-restrictions.md)に追加されています。

> [!NOTE]
> HoloLens 2 の一貫したエクスペリエンスを得るには、displayofftimeoutonbattery とスタンドアロンの両方の値が同じ値として設定されていることを確認してください。 DisplayOffTimeoutPluggedIn と StandbyTimeoutPluggedIn にも同じことが当てはまります。 最新のスタンバイの詳細については [、「表示、スリープ、休止状態のタイマー」](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) を参照してください。

### <a name="newly-enabled-update-policies-for-hololens"></a>HoloLens 用に新しく有効になった更新ポリシー
- 更新プログラムをインストールするとき、または [更新の一時停止] ボタンを無効にして更新を確認する方法の詳細。

これらの更新ポリシーは HoloLens 2 デバイスで有効になりました。
-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

これらの更新ポリシーの詳細と HoloLens デバイスでの使用方法については、「 [HoloLens 更新プログラムの管理](hololens-updates.md)」を参照してください。

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>HoloLens 2 の設定ページ表示を有効にする
- 設定アプリの UI コントロールが向上しました。これは、限られたページの選択を示すために混同される可能性があります。

これで、IT 管理者がシステム設定アプリ内の特定のページを表示またはアクセスできないようにするか、指定されたページ以外のすべてのページに対して実行できるようにするポリシーが有効になりました。 この機能を完全にカスタマイズする方法については、下のリンクをクリックしてください。

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

HoloLens 2 でカスタマイズできるページ設定については、[設定の uri](settings-uri-list.md)に関するページを参照してください。 
 
![設定アプリで変更されているアクティブ時間のスクリーンショット。](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>リサーチモード
研究モードでは、HoloLens 2 はコンピュータービジョン調査の potent ツールになります。 以前のエディションと比較して、HoloLens 2 のリサーチモードには次の利点があります。
-   HoloLens (第1世代) リサーチモードで公開されるセンサーに加えて、加速度計、ジャイロスコープ、磁力計などの imu センサーアクセスを提供するようになりました。
-   HoloLens 2 には、リサーチモードと共に使用できる新しい機能が用意されています。 具体的には、より充実した一連の実験を提供できる、明確な追跡 Api と視点追跡 Api へのアクセスを提供します。

研究者は、HoloLens デバイスでリサーチモードを有効にして、これらの外部に面しているすべての未加工のイメージセンサーストリームにアクセスできるようになりました。 HoloLens 2 のリサーチモードでは、加速度計、ジャイロスコープ、および磁力計の読み取りにもアクセスできます。 ユーザーのプライバシーを保護するために、未加工の視点を追跡するカメライメージは、リサーチモードでは使用できませんが、既存の Api を通じて目を見つめます。

詳細については、 [調査モードのドキュメント](/windows/mixed-reality/research-mode) をご覧ください。

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
- デバイスが[シングルアプリキオスク](hololens-kiosk.md)として設定されている場合に、HoloLens デバイスが Media Transfer Protocol (MTP) 経由でファイルエクスプローラーに表示されない問題に対処します。 MTP (および一般的な USB 接続) は、 [Allowusbconnection](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) ポリシーを使用して無効にすることもできます。
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

- 追跡を失った場合や回復するときに Unity アプリケーションでホログラムが消える可能性がある問題を修正しました。
- 特定のデバイスでハードウェア アクセラレーションで HoloLensを使用している間に、排他的アプリがシェルにクラッシュする原因HoloLens Emulatorを修正しました。
- サーバー上のアプリケーションの HTTPS 転送に関するWindows デバイス ポータルに対処HoloLens 2。

## <a name="windows-holographic-version-2004---june-2020-update"></a>WindowsHolographic バージョン 2004 - 2020 年 6 月更新
- ビルド 19041.1106

更新プログラムの機能強化と修正:

- カスタム MRC レコーダーが指定されていない場合、特定のプロパティに新しい既定値が追加されました。
  - *MRC ビデオ効果の場合*:
    - PreferredOgramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (イマーシブ ヘッドセット))
  - *MRC Audio Effect で*:
    - LoopbackGain (現在の "App Audio Gain" の値は、Mixed Reality キャプチャ ページWindows デバイス ポータル)
    - MicrophoneGain (現在の "Mic Audio Gain" の値は、Mixed Reality キャプチャページWindows デバイス ポータル)
- Mixed Reality キャプチャ シナリオでオーディオ品質を向上させるバグを修正しました。 具体的には、この修正により、[スタート] メニューが表示されているときに、記録中のオーディオ **グリコが** 削除されます。
- 記録されたビデオでのホログラムの安定性が向上しました。
- デバイスがスタンバイ状態を数日間残した後、Mixed Reality キャプチャでビデオを記録できない問題を解決しました。
- Unity アプリケーションでは、HolographicSpace.UserPresence API は一般に無効になっています。 この動作により、"バックグラウンドで実行" 設定が有効になっている場合でも、バイザーが反転した場合に一部のアプリが一時停止する問題が回避されます。 この API は、Unity バージョン 2018.4.18 以降および 2019.3.4 以降で有効になっています。
- 接続を使用デバイス ポータルアクセスWi-Fi、無効な証明書が原因で Web ブラウザーによって へのアクセスが妨げる可能性があります。 デバイス証明書が以前に信頼されている場合でも、ブラウザーから "ERR_SSL_PROTOCOL_ERROR" などのエラーが報告される場合があります。 この場合、セキュリティ警告を無視するオプションデバイス ポータル、更新プログラムの作成に進む必要はありません。 この更新プログラムによって問題が解決されました。 デバイス証明書が以前にダウンロードされ、ブラウザーのセキュリティ警告を削除するために PC で信頼されている場合、SSL エラーが発生した場合は、ブラウザーのセキュリティ警告に対処するために新しい証明書をダウンロードして信頼する必要があります。
- MSIX パッケージを使用してアプリをインストールできるランタイム プロビジョニング パッケージを作成する機能を有効にしました。
- 設定 Systemホログラム に設定を追加しました。これにより、デバイスのシャットダウン時に、ユーザーは自宅からMixed Realityホログラムを自動的に  >    >  削除できます。
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
  - *MRC Audio Effect で*:
    - LoopbackGain (現在の "App Audio Gain" の値は、Mixed Reality キャプチャ ページWindows デバイス ポータル)
    - MicrophoneGain (現在の "Mic Audio Gain" の値は、Mixed Reality キャプチャページWindows デバイス ポータル)
- Unity アプリケーションでは、HolographicSpace.UserPresence API は一般に無効になっています。 この動作により、バックグラウンドで実行する設定が有効になっている場合でも、バイザーが反転した場合に一部のアプリが一時停止する問題が回避されます。 この API は、Unity バージョン 2018.4.18 以降および 2019.3.4 以降で有効になっています。
- ピクセル形式を変更し、HoloLensの黒にレンダリングするアプリの問題を修正HoloLens Emulator。
- 1903 リリースから更新した後の初期ブートでの Photos アプリの起動に関する問題を修正しました。

## <a name="windows-holographic-version-2004"></a>WindowsHolographic バージョン 2004  
- ビルド - 19041.1103

*HoloLens 2、Windows Holographic、バージョン 2004* の 2020 年 5 月のメジャー ソフトウェア更新プログラムには、Windows Autopilot のサポート、アプリのダーク モード、5G/LTE ホットスポットの USB イーサネット サポートなど、多くの重要な新機能が含まれています。 最新のリリースに更新するには、設定アプリを開き、[ & セキュリティの更新] に移動して、[ 更新プログラムの確認 ]    **** **ボタンを選択**   します。 

|             機能                              |          説明                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          AutoPilot を使用して、新しいデバイスを事前構成してシームレスにWindowsする                 |
|       FIDO 2 のサポート                             |          共有デバイスの高速かつ安全な認証を有効にする FIDO2 セキュリティ キーのサポート            |
|       プロビジョニングの改善                      |          USB ドライブからデバイスにプロビジョニング パッケージをシームレスに適用HoloLens                              |
|       アプリケーションのインストール状態                 |          アプリのアプリが MDM 経由設定にプッシュされている場合は、HoloLens 2の状態を確認します               |
|       構成サービス プロバイダー (AP)   |          管理者制御機能を強化する新しい構成サービス プロバイダーを追加しました                 |
|       USB 5G/LTE のサポート                       |          USB イーサネット機能の拡張により、5G/LTE のサポートが可能                                    |
|       ダーク アプリ モード                              |          ダーク モードとライト モードの両方をサポートするアプリで使用できるダーク アプリ モード。表示エクスペリエンスが向上します        |
|       音声指示コマンド                             |          ユーザーをハンズフリーで制御する追加HoloLensコマンドのサポート                           |
|       手の追跡の機能強化                 |          手の追跡の機能強化により、ボタンと 2D スレートの相互作用をより正確に行える                        |
|       品質の向上と修正                 |          プラットフォーム全体のさまざまなシステム パフォーマンスと信頼性の向上                            |

### <a name="support-for-windows-autopilot"></a>Autopilot Windowsのサポート

WindowsAutopilot for HoloLens 2デバイスの販売チャネルが Intune テナントにHoloLens登録できます。 デバイスが到着すると、テナントの下に共有デバイスとして自己展開する準備が整います。 自己展開を利用するには、USB-C からイーサネットを使用して、セットアップの最初の画面でデバイスがネットワークに接続する必要があります。

ユーザーが Autopilot の自己展開プロセスを開始すると、次の手順が完了します。

1. デバイスを Azure Active Directory (Azure AD) に参加させます。
1. デバイスAzure AD (または別の MDM サービス) にMicrosoft Intuneを登録するには、次のコマンドを使用します。
1. デバイスを対象とするポリシー、証明書、およびネットワーク プロファイルをダウンロードします。
1. デバイスをプロビジョニングします。
1. ユーザーにサインイン画面を提示します。

詳細については[、Autopilot のWindows評価ガイドHoloLens 2参照してください](hololens2-autopilot.md)。

*今すぐ AutoPilot プレビューに参加するには、アカウント マネージャーに問い合わせください。Autopilot 対応デバイスの出荷は間もなく開始されます。*

### <a name="fido2-security-key-support"></a>FIDO2 セキュリティ キーのサポート

一部のユーザーは、HoloLens環境内の他のユーザーとデバイスを共有します。 そのため、ユーザーは長いユーザー名とパスワードを入力せずに簡単に行える必要があります。 Fast Identity Online (FIDO) を使用すると、組織内のすべてのユーザー (Azure AD テナント) は、ユーザー名やパスワードを入力することなく、HoloLens にシームレスにサインインできます。

FIDO2 セキュリティ キーは、任意のフォーム ファクターで使用できる 、"未入力" の標準ベースのパスワードレス認証方法です。 FIDO は、パスワードレス認証のオープン標準です。 これにより、ユーザーと組織は、ユーザー名やパスワードを使用せずにリソースにサインインできます。 代わりに、外部セキュリティ キーまたはデバイスに組み込みのプラットフォーム キーを使用します。

開始するには、「パスワードレス セキュリティ [キーのサインインを有効にする」を参照してください](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)。

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>プロビジョニング パッケージを使用した MDM 登録の改善

プロビジョニング パッケージを使用すると、HoloLensではなく、構成ファイルを使用して構成を設定HoloLens out-of-box experience。 以前は、プロビジョニング パッケージを内部メモリの HoloLensする必要があります。 USB ドライブに接続できるので、複数の HoloLens デバイスで簡単に再利用し、デバイスを並列でプロビジョニングできます。 プロビジョニング パッケージでデバイス管理に登録するフィールドもサポートされるので、プロビジョニング後に手動でセットアップする必要はありません。

実行方法:

1. 最新バージョンの Windows 構成デザイナーを Windows PC にダウンロードします。
1. [Provision **HoloLens Devices Provision HoloLens 2**  >  **devices]を選択します**。
2. 構成プロファイルを作成します。 次に、作成されたファイルを USB-C ストレージ デバイスにコピーします。
3. USB-C デバイスをフラッシュした新しいデバイスに接続HoloLens。 次に、**ボリュームダウン電源**  +  **ボタンを** 押して、プロビジョニング パッケージを適用します。

### <a name="line-of-business-application-install-status"></a>Line-of-Business アプリケーションのインストール状態

ビジネス アプリの MDM アプリの展開と管理は、アプリケーションを展開HoloLens。 管理者とユーザーは、監査と診断のためにアプリのインストール状態を表示する必要があります。 このリリースでは、アカウントアクセスの詳細を「設定または学校にアクセスする」を参照してください。  >    >    >  **アカウント情報 をクリック**  >  **します**。

### <a name="additional-csps-and-policies"></a>その他の CSP とポリシー

構成 [サービス プロバイダー (CSP) は](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) 、デバイスの構成設定を読み取り、設定、変更、または削除するインターフェイスです。 このリリースでは、より多くのポリシーのサポートを追加して、管理者が展開されたデバイスに対して持っている制御をHoloLensしました。 HoloLens でサポートされている CSP の一覧については[、「NetworkQoSPolicy CSP 」を参照してください](/windows/client-management/mdm/networkqospolicy-csp)。

このリリースでの新しい内容

**Policy CSP** 

ポリシー構成サービス プロバイダーを使用すると、企業はデバイスに対してポリシー Windowsできます。 このリリースでは、この一覧に示す HoloLens新しいポリシーが追加されました。 詳細については、 でサポート[されているポリシーの PS に関するページをHoloLens 2。](/windows/client-management/mdm/policies-supported-by-hololens2)  

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

NetworkQoSPolicy 構成サービス プロバイダーは、ネットワークサービス品質 (QoS) ポリシーを作成します。 QoS ポリシーは、一連の照合条件に基づいて、ネットワーク トラフィックに一連のアクションを実行します。 詳細については [、「NetworkQoSPolicy CSP 」を参照してください](/windows/client-management/mdm/networkqospolicy-csp)。

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>5G/LTE テザリングされたデバイスに対する USB イーサネットサポートの拡張

USB 経由で HoloLens 2 にテザリングされている場合に、5G/LTE フォンや Wi-Fi ホットスポットなどの特定のモバイル ブロードバンド デバイスを有効にするためにサポートが追加されました。 これらのデバイスは、別のイーサネット **接続としてネットワーク** 設定に表示されます。 (外部ドライバーを必要とするモバイル ブロードバンド デバイスはサポートされていません)。この機能により、テザリングが十分にWi-Fiテザリングが十分にWi-Fi高帯域幅接続が可能になります。 サポートされている USB デバイスの詳細については、「CONNECT [Bluetooth USB-C デバイス」を参照してください](hololens-connect-devices.md)。  

### <a name="hand-tracking-improvements"></a>手の追跡の機能強化

このリリースには、いくつかのハンド トラッキングの機能強化が含まれています。

- **ポイント姿勢の安定性:** これで、人差し指が手のひらに取り込むときに、システムは人差し指を触れ込むのを抵抗します。 この変更により、ボタンのプッシュ、入力、コンテンツのスクロールなど、精度が向上します。 
- **エア タップの偶発的な減少:** エアタップ ジェスチャの検出を改善しました。 手をサイドにドロップする場合など、いくつかの一般的なシナリオでは、偶発的なアクティブ化が少なくなっています。
- **ユーザー スイッチの信頼性:** デバイスを共有するときに手のサイズを更新する際に、システムの速度と信頼性が向上しました。
- **手盗みを減らします。** センサーを見て、手が 2 つ以上あるケースの処理を改善しました。 複数のユーザーが密接に作業している場合、追跡された手がユーザーからシーン内の他のユーザーの手に "ジャンプ" する可能性がはるかに低くなります。
- **システムの信頼性:** デバイスの負荷が高いときに手の追跡が動作を停止する原因となる問題を修正しました。

### <a name="dark-mode"></a>ダーク モード

多くのWindowsアプリでは、ダーク モードとライト モードの両方がサポートされています。 HoloLens 2ユーザーは、両方をサポートするアプリの既定のモードを選択できます。 更新後、既定のアプリ モードは "濃色" になりますが、次の設定を簡単に変更できます **:[** システムの色] 設定既定のアプリ モードを  >    >    >  **選択します**。 

これらの "インボックス" アプリでは、ダーク モードがサポートされます。 

- 設定 
- Microsoft Store 
- Mail 
- Calendar 
- エクスプローラー 
- フィードバック Hub 
- OneDrive 
- 写真 
- 3D ビューアー 
- 映画 & テレビ 

![タイル表示されたダーク モードのウィンドウ。](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>システム音声コマンド

これで、デバイス上の任意のアプリで音声コマンドを使用できます。 詳細については、「音声を使用[して音声を操作する」をHoloLens。](hololens-cortana.md) 「サポート[されている言語」も参照HoloLens 2。](hololens2-language-support.md)  

### <a name="cortana-updates"></a>Cortana更新プログラム

更新されたアプリは Microsoft 365 と統合され、デバイス全体でより多くの作業を行うのに役立ちます (現在、US-Englishのみです)。 このHoloLens 2、Cortanaの調整や再起動など、特定のデバイス固有のコマンドがサポートされなくなりました。 これらのオプションは、新しいシステム音声コマンドでサポートされています。 新しいアプリの詳細についてはCortanaブログを[参照してください](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)。

### <a name="quality-improvements-and-fixes"></a>品質の向上と修正

更新プログラムの機能強化と修正:  
- アクティブなディスプレイ調整システムを導入しました。 この機能により、ホログラムの安定性と配置が向上します。 これで、頭を横から横に移動すると、その場所に残ることになります。
- ストリーム配信が定期的Wi-Fi中断HoloLensバグを修正しました。 アプリケーションで低待機時間のストリーミングが必要と示されている場合は [、SetSocketMediaStreamingMode](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)関数 を呼び出して修正プログラムを実装します。
- 調査モードでのストリーミング中に発生したデバイスハングを修正しました。
- セッションを終了するときに、サインイン画面に適切なユーザーが表示されない場合があるバグを修正しました。
- ユーザーが を使用して MDM ログをエクスポートできない問題を **設定。**
- すぐに設定した後の目の追跡の精度が予想よりも低い可能性がある問題を修正しました。
- 特定の条件下で、目の追跡サブシステムが初期化または調整を実行できなかった問題を修正しました。
- 既に調整されたユーザーに対して目の調整を求める問題を修正しました。
- 目の調整中にドライバーがクラッシュする問題を修正しました。
- 電源ボタンを繰り返し押すと、60 秒のシステム タイムアウトとシェル クラッシュが発生する可能性がある問題を修正しました。
- 深度バッファーの安定性が向上しました。
- ユーザーがフィードバック **を** 簡単に共有フィードバック Hubに [共有] ボタンを追加しました。
- RoboRaid wan が正しくインストールされないバグを修正しました。

### <a name="known-issues"></a>既知の問題

- zh-CN システム言語に関する問題により、音声コマンドが Mixed Reality キャプチャを取得したり、デバイスの IP アドレスを表示したり妨げる可能性があります。
- 問題では、Cortana"Hey Cortana" の音声アクティブ化を使用するデバイスを起動した後、アプリを起動する必要があります。 18362 ビルドから更新した場合は、以前のバージョンの Cortana アプリの 2 つ目のアプリ タイルも表示され、 [開始] で機能し **なくなる場合があります**。

## <a name="windows-holographic-version-1903---may-2020-update"></a>WindowsHolographic バージョン 1903 - 2020 年 5 月更新 
- ビルド 18362.1061

この毎月の品質更新プログラムには、前述のように、チームが Windows Holographic バージョン 2004 May Update に取り組っていたため、重要な変更は含められない。

## <a name="windows-holographic-version-1903---april-2020-update"></a>WindowsHolographic バージョン 1903 - 2020 年 4 月更新
- ビルド 18362.1059

**サポートされているアプリのダーク モード** 

多くのWindowsアプリでは、ダーク モードとライト モードの両方がサポートされています。 HoloLens 2両方の配色をサポートするアプリの既定のモードを選択できます。 お客様からのフィードバックに基づいて、既定のアプリ モードを "ダーク" に設定していますが、この設定はいつでも簡単に変更できます **。設定 > System > Colors** に移動して、"既定のアプリ モードを選択する" を見つける。

これらの "インボックス" アプリでは、ダーク モードがサポートされます。
- 設定
- Microsoft Store
- Mail
- Calendar
- エクスプローラー
- フィードバック Hub
- OneDrive
- 写真
- 3D ビューアー
- 映画 & テレビ

**更新プログラムの機能強化と修正:** 
- シェル オーバーレイが Mixed Reality キャプチャに含まれる必要があります。
- Unreal 開発者は、アプリの 3D ビュー ページをデバイス ポータルして、アプリケーションをテストおよびデバッグできます。
- *HolographicDepthReprojectionMethod DepthReprojection* アルゴリズムを使用すると、Mixed Reality キャプチャのホログラムの安定性が向上しました。
- 32 ビット ARM アプリで "WinRT IStreamSocketListener API クラスが登録されていません" というエラーを修正しました。

## <a name="windows-holographic-version-1903---march-2020-update"></a>WindowsHolographic バージョン 1903 - 2020 年 3 月更新 
- ビルド 18362.1056

更新プログラムの機能強化と修正:

- *HolographicDepthReprojectionMethod AutoPlanar* アルゴリズムを使用すると、Mixed Reality キャプチャのホログラムの安定性が向上しました。
- 深度 MF サンプルにアタッチされている座標系がパブリック ドキュメントと一致する必要があります。
- 顧客がデバイス ポータルを使用して大量のテキストを貼り付け可能にすることで、開発者の生産性が向上しました。

## <a name="windows-holographic-version-1903---february-2020-update"></a>WindowsHolographic バージョン 1903 - 2020 年 2 月更新 
- ビルド 18362.1053

更新プログラムの機能強化と修正:

- Unity アプリケーション用の HolographicSpace.UserPresence API を一時的に無効にしました。 この変更により、"バックグラウンドで実行" 設定が有効になっている場合でも、バイザーが反転した場合に一部のアプリが一時停止する問題が回避されます。
- ユーザーが UI がフリーズし、数秒後にシェルに戻るのをユーザーが気付いた、手の追跡によって発生するランダムな HUP クラッシュを修正しました。
- 人差し指で突っ込むときに、その指の上部が予期せず丸くならずになじむので、手の追跡が改善されました。
- ヘッドトラッキング、空間マッピング、その他のランタイムの信頼性が向上しました。

## <a name="windows-holographic-version-1903---january-2020-update"></a>WindowsHolographic バージョン 1903 - 2020 年 1 月更新 
- ビルド 18362.1043
 
更新プログラムの機能強化と修正:

- アプリケーション エミュレーターを使用する場合の排他アプリの安定性HoloLens 2しました。

## <a name="windows-holographic-version-1903---december-2019-update"></a>WindowsHolographic バージョン 1903 - 2019 年 12 月の更新プログラム 
- ビルド 18362.1042

更新プログラムの機能強化と修正:

- 最終ステージの再現 (LSR) の修正が導入されました。 ホログラムの深度をより正確に説明することで、ホログラムの視覚的なレンダリングが向上し、より安定して鮮明に見える。 この現象は、アプリがホログラムの深さを正しく設定しない場合、この更新後に顕著になります。
- 排他的なアプリと排他的なアプリ間のナビゲーションの安定性を修正しました。
- デバイスが数日間スタンバイ状態の後に Mixed Reality キャプチャでビデオを記録できない問題を解決しました。
- ホログラムの安定性が向上しました。

## <a name="windows-holographic-version-1903---november-2019-update"></a>WindowsHolographic バージョン 1903 - 2019 年 11 月の更新プログラム 
- ビルド 18362.1039

更新プログラムの機能強化と修正:

- en-CA **と** en-AU の初期セットアップ中に音声コマンドを選択する機能を修正しました。
- 最新の Unity および MRTK (MRTK) バージョンに配置されたオブジェクトMixed Reality Toolkit品質が向上しました。
- ホログラフィック アプリケーションが開いてから閉じるまで、起動時に一時停止状態でスタックする問題スタート メニュー修正しました。
- OpenXR ランタイム準拠の修正と、HoloLens 2エミュレーターの機能強化。
