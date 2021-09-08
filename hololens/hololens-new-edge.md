---
title: 新しい Microsoft Edge について
description: 新しい Edge アプリについて学習する
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens、エッジ、インターネット、ブラウザー
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: 8ef73733b9fa4f422335977be860371b9570d549
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189700"
---
# <a name="introducing-the-new-microsoft-edge"></a>新しい Microsoft Edge について

![レガシ Microsoft Edge ロゴから新しい Microsoft Edge ロゴへのアニメーション。](images/new-edge.gif)

新しいMicrosoft Edge[ は、Chromiumオープンソース プロジェクト](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/)を採用して、顧客との互換性を向上し、Web 開発者向けの Web の断片化を減らします。

[Holographic Windowsバージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1)では、新しい Microsoft Edge を HoloLens 2 顧客が初めて利用できます! 新しい Microsoft Edge の **フィードバック送信** 機能または [フィードバック Hub](hololens-feedback.md) を通じて当社のチームにフィードバックやバグをお知らせください。

> [!IMPORTANT]
> この新しい Microsoft Edge は、新しいリリースでは[サポートされなくなった](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/)レガシの Microsoft Edge を自動的に置き換える機能です。

![新しい Microsoft Edge のスクリーンショット。](images/new-edge-ui.png)

## <a name="launching-the-new-microsoft-edge"></a>新しい Microsoft Edge を起動する

新しい Microsoft Edge ![新しい Microsoft Edge アイコン。](images/new_edge_logo.png) (青と緑のスワイル アイコンで表されます) は、スタート メニュー にピン留めされ、Web リンクをアクティブ化すると自動的に起動します。

> [!NOTE]
> HoloLens 2 で新しい Microsoft Edge を初めて起動するとき、設定とデータはレガシの Microsoft Edgeからインポートされます。

## <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>新しい Microsoft Edge のポリシー設定を構成する

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

## <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>HoloLens 2 で新しい Microsoft Edge から期待するもの

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

**既知のブラウザーの上位の問題:**
- ホログラフィック キーボードの拡大鏡プレビューは、新しい Microsoft Edge では無効になっています。 拡大が正しく機能したら、今後の更新プログラムでこの機能を再び有効にしてください。
- 別のブラウザー ウィンドウが開いておりアクティブな場合、間違ったブラウザー ウィンドウからオーディオが再生される可能性があります。 この問題を回避するには、オーディオを再生していてはいけない他のアクティブ ウィンドウを閉じます。
- "一緒に移動" モードでブラウザー ウィンドウからオーディオを再生する場合、"一緒に移動" モードを無効にしたすればオーディオは再生されたままになります。 この問題を回避するには、"一緒に移動" モードを無効にする前にオーディオ再生を停止するか、X ボタンでウィンドウを閉じます。
- アクティブな Microsoft Edge ウィンドウとやりとりすると、他の 2D アプリ ウィンドウが予期せず非アクティブになる可能性があります。 これらのウィンドウは、もう一度操作すれば再アクティブ化できます。

## <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider アイコン

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

## <a name="using-wdac-to-block-new-microsoft-edge"></a>WDAC を使用して新しい Microsoft Edge をブロック

[WDAC ポリシー](windows-defender-application-control-wdac.md)を更新して新しい Microsoft Edge アプリをブロックする IT 管理者の場合は、ポリシーに次を追加する必要があります。

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

## <a name="managing-endpoints-for-the-new-microsoft-edge"></a>新しい Microsoft Edge のエンドポイントを管理する

一部の環境には、考慮すべきネットワーク制限がある場合があります。 新しい Edge でスムーズなエクスペリエンスを実現するには、[これらの Microsoft エンドポイントを有効にして](/deployedge/microsoft-edge-security-endpoints)ください。

現在使用可能な[ HoloLens 用エンドポイントの詳細について](hololens-offline.md)参照してください。

## <a name="install-web-apps"></a>Web アプリのインストール
 > [!Note]
> [Holographic Windowsバージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1)では、Office Web アプリはプレインストールされなくなりました。 

新しい Edge を使用して、Microsoft Store アプリと共に Web アプリをインストールします。 たとえば、Microsoft Office Web アプリをインストールして、SharePoint または OneDrive でホストされているファイルを表示および編集できます。 Office Web アプリをインストールするには、 https://www.office.com にアクセスし、アドレス バーの **[使用可能なアプリ]** または **[Office をインストール]**  ボタンをクリックします。 **[インストール]** を選択 して確定します。
> [!IMPORTANT]
> Office Web アプリの機能は、HoloLens 2 にアクティブなインターネットがある場合にのみ使用できます。

## <a name="webxr-and-360-viewer"></a>WebXR および 360 ビューアー


新しいMicrosoft Edge には WebXR のサポートが含まれています。これは、イマーシブ Web エクスペリエンスを作成するための新しい標準です (WebVR の後継)。 多くのイマーシブ Web エクスペリエンスは、VR を念頭に置いて設計されました (実際の視野を仮想環境に置き換えます)。ただし、これらのエクスペリエンスは、HoloLens 2 でもサポートされています。 WebXR 標準では、物理環境を使用する拡張および Mixed Reality のイマーシブ Web エクスペリエンスも可能になります。 開発者が WebXR により多くの時間を費やすと、HoloLens 2 のお客様が新しい拡張および Mixed Reality イマーシブ エクスペリエンスを試せるようになる予定です!

360 Viewer 拡張機能は WebXR 上に構築され、HoloLens 2 上で新しい Microsoft Edge と共に自動的にインストールされます。 この Web 拡張機能を使用すると、360 度のビデオに取り入れすることができます。 YouTube では最大 360 本の動画が提供されているため、そこから開始することをお勧めします。

### <a name="how-to-use-webxr"></a>WebXR の使用方法

1. WebXR がサポートされている Web サイトに移動します。
1. Web サイトの **[VR の入力]** ボタンを選択します。 このボタンの場所と視覚的な表現は、Web サイトごとに異なる場合がありますが、次のような場合があります。

    ![ENTER VR ボタンの例。](images/75px-enter-vr.png)

1. 特定のドメインで初めて WebXR エクスペリエンスを起動しようとすると、ブラウザーでイマーシブ ビューに入る同意を求められます。 **[許可]** を選択 してください。
1. [HoloLens 2 ジェスチャ](hololens2-basic-usage.md#the-hand-tracking-frame) を使用して、エクスペリエンスを操作します。
1. エクスペリエンスに **[終了]** ボタンがない場合は、[スタート ジェスチャ](hololens2-basic-usage.md#start-gesture)を使用してホームに戻ります。

**推奨される WebXR サンプル**
- 360 ビューアー (次のセクションを参照)
- [XR Dinosaurs](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

### <a name="how-to-use-360-viewer"></a>360 ビューアーの使い方

1. YouTube で 360 度のビデオに移動します。
1. ビデオ フレームで、[Mixed Reality ヘッドセット] ボタンを選択します。

    ![360 ビューアーをアクティブ化するボタン。](images/enter-360-viewer.jpg)

1. 特定のドメインで初めて 360 ビューアーを起動しようとすると、ブラウザーでイマーシブ ビューに入る同意を求められます。 **[許可]** を選択します。
1. [エア タップ](hololens2-basic-usage.md#select-using-air-tap) で再生コントロールを表示します。 [ハンド レイとエア タップ](hololens2-basic-usage.md#select-using-air-tap) を使用して、再生/一時停止、前方/戻るスキップ、キャプションのオン/オフの切り替え、エクスペリエンスの停止 (イマーシブ ビューを終了) を行います。 再生コントロールは、数秒の非アクティブ状態の後に消えます。

### <a name="top-webxr-and-360-viewer-known-issues"></a>WebXR と 360 ビューアーの既知の問題
- WebXR エクスペリエンスの複雑さによっては、フレームレートが低下したり、つまずく場合があります。
- WebXR での多関節手関節のサポートは、既定では有効になっていません。 開発者は、"WebXR ハンド入力" を有効にすることで、edge://flagsでサポートを有効にできます。
- YouTube 以外の Web サイト 360 本の動画は想定通り動作しない場合があります。

### <a name="providing-feedback-on-webxr-and-360-viewer"></a>WebXR と 360 ビューアーに関するフィードバックの提供

新しい Microsoft Edge の **フィードバックを送る** 機能を通じて当社のチームにフィードバックやバグをお知らせください。
