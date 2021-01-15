---
title: Microsoft HoloLens の Insider Preview
description: 簡単に Insider ビルドを使い始めて、HoloLens の次の主要なオペレーティング システムの更新プログラムに対する貴重なフィードバックをご提供いただけます。
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
ms.date: 1/13/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 5da96d2838cbe1a02956a3e567c6ecf6da9d6b10
ms.sourcegitcommit: c93f23fe7c27dfa45fef300a4fc91aa811bc8126
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2021
ms.locfileid: "11269482"
---
# Microsoft HoloLens の Insider Preview

HoloLens 用の最新の Insider Preview ビルドへようこそ! HoloLens [の次](hololens-insider.md#start-receiving-insider-builds) の主要なオペレーティング システム更新プログラムの使用を開始し、貴重なフィードバックを提供する方法は簡単です。

## Windows Insider リリース ノート

Windows Insider の新機能のフライトを再び開始します。 We will be flighting to the Dev Channel for the latest updates. このページは、Windows Insider ビルドに追加された機能と更新プログラムが追加され、引き続き更新されます。  これらの更新プログラムを実際に組み合わせ、準備を整えます。 

| 機能名                                              | 簡単な説明                                                                      | ビルドで使用可能 |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [新しい Microsoft Edge](#introducing-the-new-microsoft-edge) | HoloLens 2 で、Chromium ベースの新しい Microsoft Edge を利用できる                         | 20279.1006 |
| [新しい設定アプリ](#new-settings-app)                     | 従来の設定アプリは、新しい機能と設定で更新されたバージョンに置き換えられる | 20279.1006 |
| [既定のアプリ ピッカー](#default-app-picker)                 | ファイルまたはリンクの種類ごとに起動するアプリを選択する                                      | 20279.1006 |
| [Office Web アプリ](#office-web-app)                         | 新しい Web アプリOfficeが [すべてのアプリ] に表示されます。                                   | 20279.1006 |
| [スワイプして入力する](#swipe-to-type)                           | ホログラフィック キーボードで指のヒントを使って単語を "スワイプ" する                        | 20279.1006 |

### 新しい Microsoft Edge の導入

![従来の Microsoft Edge ロゴから新しい Microsoft Edge ロゴへのアニメーション](images/new-edge.gif)

新しい Microsoft Edge は [Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) オープン ソース プロジェクトを採用して、お客様との互換性を向上し、Web 開発者向けの Web の断片化を減らします。 

この Insider プレビューでは、HoloLens 2 のお客様が新しい Microsoft Edge を初めて利用できます。 新しい Microsoft Edge は最終的に HoloLens 2 の従来の Microsoft Edge に取って代わる機能ですが、現在、両方のブラウザーが Insider で利用できます。 新しい Microsoft Edge のフィードバック送信**** 機能またはフィードバック Hub を介して、フィードバックやバグをチームと[共有してください](hololens-feedback.md)。

![新しい Microsoft Edge のスクリーンショット](images/new-edge-ui.png)

#### 新しい Microsoft Edge の起動

Insider が利用できる Microsoft Edge には、新しい Microsoft Edge の新しい Microsoft Edge アイコン (青と緑のスループ アイコンで表される) と従来の Microsoft Edge (白い ![ "e" アイコンで表される) の 2 つのバージョンがあります。 ](images/new_edge_logo.png) 新しい Microsoft Edge はスタート メニューにピン留めされ、Web リンクをアクティブ化すると自動的に起動します。 従来の Microsoft Edge を既定の Web ブラウザーとして使用する場合は、以下の手順を参照して既定のアプリを [リセットしてください](#default-app-picker)。

> [!NOTE]
> HoloLens 2 で新しい Microsoft Edge を初めて起動すると、設定とデータは従来の Microsoft Edge からインポートされます。 新しい Microsoft Edge を起動した後も従来の Microsoft Edge を使用し続ける場合、その新しいデータは従来の Microsoft Edge から新しい Microsoft Edge に同期されません。

#### 新しい Microsoft Edge のポリシー設定の構成

新しい Microsoft Edge は、従来の Microsoft Edge で提供していたよりも、HoloLens 2 のブラウザー ポリシーの広範なセットを IT プロに提供します。 

新しい Microsoft Edge のポリシー設定の管理について詳しく知る上で役立つリソースを次に示します。
- [Microsoft Intune を使って Microsoft Edge ポリシー設定を構成する](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Microsoft Edge Legacy から Microsoft Edge ポリシーへのマッピング](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome から Microsoft Edge ポリシーへのマッピング](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- [Microsoft Edge Enterprise の完全なドキュメント](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> 新しい Microsoft Edge でサポートされているブラウザー ポリシーの量が多いので、新しい各ポリシーが HoloLens 2 で動作するとは、チームは保証できません。 ただし、HoloLens 2 で以前サポートされた従来の各 Microsoft Edge ポリシーと同等の新しい Microsoft Edge が期待通り動作するテストを行い、確認しました。 HoloLens 2 で使用していた従来の各 Microsoft Edge ブラウザー ポリシーと同等の新しい Microsoft Edge を見つけるには [、Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) レガシから Microsoft Edge へのポリシー マッピングをご覧ください。
>
> HoloLens 2 では動作しない新しい** Microsoft Edge ポリシーが 2 つ以上あります。
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### HoloLens 2 の新しい Microsoft Edge に期待される機能

新しい Microsoft Edge は、新しい UWP アダプター レイヤーを使ったネイティブの Win32 アプリで、HoloLens 2 のような UWP 専用デバイスで実行することができるため、一部の機能はすぐに利用できない場合があります。 今後数か月の間に新しいシナリオと機能をサポートする予定なので、このスペースで最新の情報を確認してください。

**動作が予想されるシナリオと機能:**
- 初回実行エクスペリエンス、プロファイルへのサインイン、同期
- Web サイトが期待どおりにレンダリングされ、動作する必要がある
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
- 環境内に配置された複数のウィンドウを閲覧する場合の正しいウィンドウに対するコンテンツの復元
- 同時オーディオ ストリームを使用する複数のウィンドウの空間サウンド
- ビデオ、Mixed Reality キャプチャ、または画面共有を使用してブラウザー経由で Microsoft Teams 通話に参加する (通話とオーディオの参加がうまく機能)
- "見て、言ってみる"
- 印刷

**既知のブラウザーの問題の上位:**
- デバイスをリセットすると、新しい Microsoft Edge が削除されます。
- ホログラフィック キーボードの拡大鏡のプレビューに誤ったコンテンツが表示される

### 新しい設定アプリ

このリリースでは、設定アプリの新しいバージョンが導入されています。 新しい設定アプリには、サウンド、Power & スリープ、ネットワーク & インターネット、アプリ、アカウント、簡単操作など、HoloLens 2 の新機能と拡張された設定が含まれています。

> [!NOTE]
> 新しい設定アプリは従来の設定アプリとは異なっているので、以前環境の周囲に配置した設定ウィンドウは、更新時に削除されます。

![新しい設定アプリのホーム ページ](images/new-settings-app.png)

**新機能と設定**
- 設定検索: キーワードまたは設定名を使用して設定ホーム ページから設定を検索する
- システム > サウンド:
  - 入力オーディオ デバイスと出力オーディオ デバイス: 入力オーディオ デバイスと出力オーディオ デバイスを個別に選択します (たとえば、Bluetooth ヘッドホンでオーディオを聞く場合や、オーディオ入力に USB-C マイクを使用する場合など)。 注: Bluetooth HoloLens 2 ではサポートされていません。
  - アプリのボリューム: 各アプリのボリュームを個別に調整する
- システム>電源&スリープ: 非アクティブな状態が一時間続くとデバイスがスリープ状態にされる時期を選択する
- システム>バッテリー: バッテリー節約機能モードを手動で有効にするか、バッテリー節約機能モードが自動的に有効になる時点でバッテリーしきい値を設定する
- デバイス> USB: 既定で USB 接続を無効にできます
- ネットワーク & インターネット:
  - USB-C イーサネット アダプターは、ネットワーク ネットワーク とインターネット&されます。
  - USB-C イーサネット アダプターの設定 (IP アドレスを含む) が使用可能に
  - HoloLens 2 でフライト モードを有効にできる
- アプリ: ファイルとリンクの種類に使用する既定のアプリをリセットできます。 詳 [しくは、「既定のアプリ ピッカー](#default-app-picker) 」をご覧ください。
- 他>ユーザーのアカウント: デバイス所有者は、ユーザーの追加、標準ユーザーのデバイス所有者へのアップグレード、デバイス所有者の標準ユーザーへのダウングレード、ユーザーの削除を行います。
- 簡単操作: テキスト サイズと視覚効果を変更する

**既知の問題**
- 以前に配置した設定ウィンドウは削除されます (上記の注を参照してください)。
- [通知] ページにアクセスすると、設定アプリがクラッシュする可能性があります (調査中)
- 現在イーサネット ページが表示されていない (間もなく修正される予定)
- 新しい Microsoft Edge のバッテリー使用量は、UWP アダプター レイヤーでサポートされる Win32 デスクトップ アプリケーションとしての性質上、正確ではない可能性があります (間もなく修正される予定はありません)

### 既定のアプリ ピッカー

ハイパーリンクをアクティブにするか、複数のインストール済みアプリをサポートするファイルの種類を開いた場合は、新しいウィンドウが開き、ファイルまたはリンクの種類を処理するインストール済みアプリを選択するように求めるメッセージが表示されます。 このウィンドウでは、選択したアプリでファイルまたはリンクの種類として "Once" または "Always" を処理することもできます。 

![アプリ ピッカー ウィンドウ](images/default-app-picker.png)

If you choose "Always" but later want to change which app handles a particular file or link type, you can reset your saved defaults in **Settings > Apps**. ページの下部までスクロールし、[ファイルの種類**** 用の既定のアプリ] または [リンクの種類用の既定のアプリ] の下にある [クリア] ボタンを選択します。 デスクトップ PC の同様の設定とは異なり、個々のファイルの種類の既定値をリセットできます。

### Office Web アプリ

スタート Officeの [すべてのアプリ] の一覧に、新しい Web アプリが追加されました。 この Web アプリは、スタート画面にピン留めしたりアンインストールしたりすることもできます。 これは Web アプリなので、その機能はアクセスして体験した機能と正確に一致します https://www.office.com 。 Office Web アプリの機能は、HoloLens 2 にアクティブなインターネット接続がある場合にのみ使用できます。

### スワイプして入力する

一部のお客様は、入力する単語の形をスワイプすることで仮想キーボードを "入力" する方が速く見つかり、ホログラフィック キーボード用にこの機能をプレビューします。 ホログラフィック キーボードの平面を指の先端を通して一度に 1 つの単語をスワイプし、単語の形状をスワイプし、キーボードの平面から指の先端を引き出します。 単語間でキーボードから指を外して Space キーを押す必要なく、フォローアップ語をスワイプできます。 キーボードで指が動いた後にスワイプ の証跡が表示される場合は、この機能が動作しているのが分かっています。

この機能は、(携帯電話のディスプレイとは異なり) 指に抵抗を感じないホログラフィック キーボードの性質上、使い方が難しい場合があります。 この機能は一般リリース向けとして評価されています。そのため、お客様からのフィードバックは重要です。この機能が役に立つ場合も、構築的なフィードバックがある場合も、フィードバック Hub でお知 [らせください](hololens-feedback.md)。





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

次に **、Windows のアクティブな**開発を選択し、開発チャネルビルドまたは**** ベータ チャネル**** ビルドを受け取るかどうかを選択し、プログラムの条件を確認します。

[ **Confirm > Restart Now]** を選び、完了します。 デバイスが再起動したら、[設定] > [更新とセキュリティ&] > **最新** のビルドを取得するための更新プログラムを確認する] に移動します。

## FFU のダウンロードとフラッシュの手順
フライト署名のある FFU でテストするには、フライト署名のある FFU をフラッシュする前にデバイスのフライト ロックを解除する必要があります。
1. PC の場合:

    1. Ffu を PC からダウンロードします [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. Microsoft Store ([https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)) から ARC (Advanced Recovery Companion) をインストールします。
    
1. HoloLens で - [フライトのロック解除]: **Windows**Insider Program &設定の更新を開き、  >  ****  >  **** デバイスを再起動してサインアップします。

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
