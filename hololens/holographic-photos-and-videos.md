---
title: Mixed reality の写真とビデオをキャプチャして管理する
description: HoloLens を使って、mixed reality 写真とビデオのキャプチャ、表示、共有を行う方法について説明します。
keywords: hololens、写真、ビデオ、キャプチャ、mrc、mixed reality キャプチャ、写真、カメラ、ストリーム、livestream、デモ
ms.assetid: 1b636ec3-6186-4fbb-81b2-71155aef0593
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 10/28/2019
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4da70e73cd5949c77bc77a73f57f788ed51eff90
ms.sourcegitcommit: 973b0e71ebceeb2c614aea3dd3a1fbb90d7daed9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "11100272"
---
# Mixed Reality の写真とビデオを作成する

HoloLens は、現実世界とデジタル世界との混合のエクスペリエンスをユーザーに提供します。  複合現実キャプチャ (MRC) を使用すると、そのエクスペリエンスを写真やビデオとしてキャプチャしたり、他のユーザーとリアルタイムで共有したりすることができます。

Mixed reality キャプチャでは、他のユーザーが表示しているホログラムを他のユーザーが見ることができるように、最初のユーザーの視点を使います。 視点が3人の場合は、 [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view)を使用します。 Spectator view は、デモに特に便利です。

ビデオは、友達や同僚とビデオを共有するのに便利ですが、ビデオは、他のユーザーがアプリを使用したり、アプリやエクスペリエンスの問題を伝えたりするために役立つこともあります。

> [!NOTE]
> Mixed reality キャプチャエクスペリエンスを起動できず、HoloLens が作業デバイスである場合は、システム管理者に確認してください。 カメラへのアクセスは、会社のポリシーを通じて制限することができます。

## Mixed reality 写真をキャプチャする

HoloLens で mixed reality の写真を撮影するには、いくつかの方法があります。ハードウェアボタン、音声、または [スタート] メニューを使用できます。

### 写真を撮るためのハードウェアボタン

現在のビューの写真を撮影するには、[音量を上げる] ボタンと [音量を下げる] ボタンを同時に押します。  これは、HoloLens バージョンのスクリーンショットまたは印刷画面に似ています。

- [HoloLens 2 のボタンの場所](hololens2-hardware.md)
- [HoloLens 上のボタンの場所 (第1世代)](hololens1-hardware.md#hololens-components)

> [!NOTE]
> [ **音量を上げる** ] ボタンと [ **音量を下げる** ] ボタンを3回押すと、写真を撮影するのではなく、ビデオの録画が開始されます。 記録を停止するには、[ **音量を上げる** ] と [ **音量を下げる** ] の両方のボタンを同時にタップします。

### 写真を撮るための音声コマンド

HoloLens 2、バージョン 2004 (以降) では、「写真を撮る」と言ってください。

HoloLens (第1世代) または HoloLens 2、バージョン1903では、「コルタナさん、写真を撮影してください」と言っています。

### [スタート] メニューで写真を撮る

開始ジェスチャを使用して [ **スタート**] に移動し、[ **カメラ** ] アイコンを選択します。

キャプチャする内容の向きをポイントして、 [エアタップ](hololens2-basic-usage.md#touch-holograms-near-you) して写真を撮ります。 引き続き、空中でタップして追加の写真をキャプチャすることができます。 キャプチャした写真は、お使いのデバイスに保存されます。

もう一度開始ジェスチャを使って写真のキャプチャを終了します。  

## Mixed reality ビデオをキャプチャする

HoloLens で mixed reality のビデオを録画するには、いくつかの方法があります。ハードウェアボタン、音声、または [スタート] メニューを使用できます。

### ビデオを録画するためのハードウェアボタン

ビデオを録画する最も簡単な方法は、[ **音量を上げる** ] ボタンと [ **音量を下げる** ] ボタンを同時に押して、3秒のカウントダウンが開始されるようにすることです。 記録を停止するには、両方のボタンを同時にタップします。

> [!NOTE]
> [ **音量を上げる** ] ボタンと [ **音量を下げる** ] ボタンを同時に押すと、ビデオを録画するのではなく写真が撮影されます。

### 音声を録音してビデオを録画する

HoloLens 2、バージョン 2004 (以降) では、「レコーディングの開始」と言ってください。 記録を停止するには、「記録を停止」と発声します。

HoloLens (第1世代) または HoloLens 2、バージョン1903では、"コルタナさん、レコーディングを開始します" と言います。 記録を停止するには、「コルタナさん、レコーディングを停止」と発声します。

### ビデオを録画するためのスタートメニュー

開始ジェスチャを使用して [ **スタート**] に移動し、[ **ビデオ** ] アイコンを選択します。 キャプチャするものの向きをポイントして、[ [エアタップ](hololens2-basic-usage.md#touch-holograms-near-you) ] をクリックして録音を開始します。 3秒間のカウントダウンが表示され、レコーディングが開始されます。

記録を停止するには、開始ジェスチャを使用して、強調表示された **ビデオ** アイコンを選択します。 ビデオがデバイスに保存されます。

> [!NOTE]
> **HoloLens (第1世代) のみに適用されます**  
> [2018 年10月の更新プログラム](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)は、HoloLens (第1世代) で開始ジェスチャと Windows ボタンが動作する方法を変更します。 更新する前に、開始ジェスチャまたは Windows ボタンをクリックすると、ビデオ録画が停止します。 ただし、更新後、[スタート] または [Windows] ボタンをクリックすると、[ **スタート** ] メニュー (または [ **クイック操作] メニュー** ) が開きます。これは、強調表示された **ビデオ** アイコンを選択して記録を停止することができます。

## 表示される内容をリアルタイムで共有する

HoloLens での表示内容は、お友達や同僚とリアルタイムで共有できます。 次のような方法があります。

1. Miracast を有効にしたデバイスまたはアダプターに接続して、テレビで見ることができます。
1. [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)を使って PC を監視する
1. [Microsoft HoloLens コンパニオンアプリ](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)を使って PC を監視します。
1. [Microsoft Dynamics 365 リモート](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist)アシスタンスアプリを展開して、フロントラインワーカーがリモートエキスパートに表示される内容をストリーミングできるようにします。 次に、リモートの専門家は、フロントラインワーカーのコミュニケーションとるを案内するか、または世界で注釈を付けることができます。

> [!NOTE]
> Windows Device Portal または Microsoft HoloLens コンパニオンアプリでの表示内容を共有するには、HoloLens が [開発者モード](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)になっている必要があります。

### Miracast を使用したビデオのストリーミング

開始ジェスチャを使用して [ **スタート**] に移動し、[ **接続** ] アイコンを選択します。 表示されるピッカーで、接続する Miracast 対応デバイスまたはアダプターを選択します。

共有を停止するには、開始ジェスチャを使用し、強調表示されている **接続** アイコンを選択します。 ストリーミングを行っているため、デバイスに何も保存されません。

> [!NOTE]
> Miracast のサポートは、 [Windows 10 年 2018 10 月の更新プログラム](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)以降、HoloLens (第1世代) で有効にされています。

### Windows Device Portal を使ったリアルタイムビデオ

Windows Device Portal で共有するには、HoloLens で開発者モードが有効になっている必要があるため、開発者向けドキュメントの指示に従って [開発者モードを設定し、Windows Device portal に移動](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)します。

### Microsoft HoloLens コンパニオンアプリ

Microsoft HoloLens コンパニオンアプリで共有するには、HoloLens で開発者モードが有効になっている必要があるため、開発者向けドキュメントの指示に従って [開発者モードを設定](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)してください。 次に、 [Microsoft HoloLens コンパニオンアプリ](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) をダウンロードして、アプリ内の指示に従って HoloLens に接続します。

アプリが HoloLens で設定されたら、アプリのメインメニューから [ **ライブストリーム** ] オプションを選びます。

## Mixed reality の写真とビデオを表示する

Mixed reality の写真とビデオは、デバイスの "カメラロール" に保存されます。 HoloLens でこのフォルダーの内容を参照するには、エクスプローラーアプリを使用します ([ピクチャ > カメラロール] に移動します)。

また、mixed reality の写真やビデオを、HoloLens にプレインストールされている写真アプリで表示することもできます。 世界中の写真をピン留めするには、写真アプリで写真を選択し、[ **混合世界で配置**] を選択します。 世界中の写真は、配置後に移動することができます。

HoloLens に接続された PC で mixed reality の写真やビデオを表示したり保存したりするには、 [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) または [pc のエクスプローラーを MTP 経由](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)で使うことができます。

### エクスプローラーを使用して、画像、ビデオ、ファイルを取得する

他のモバイルデバイスと同様に、HoloLens を PC に接続して、ファイルエクスプローラーを使って、簡単に転送できる HoloLens ライブラリ (写真、ビデオ、ドキュメント) にアクセスできます。 この方法は使いやすいため、device portal または Wi-fi を使用する必要はありません。

1. デバイスのロックを解除します。
1. USB 経由でデバイスを PC に接続します。
1. PC 上でファイルエクスプローラーが開きます。
1. 移動先: この PC\ \*yourhololensname*\ Storage\Pictures\Camera ロール
1. 必要なファイルを PC にコピーします。

ヒント: 
- ファイルが表示されない場合は、HoloLens にサインインしてデータへのアクセスを有効にしていることを確認してください。
- [ドキュメント] フォルダーの [診断ファイル](hololens-diagnostic-logs.md#offline-diagnostics) など、他のフォルダーにある他のファイルを取得することができます。
- PC のエクスプローラーから、[デバイスのプロパティ] を選択して、Windows ホログラフィック OS のバージョン番号 (ファームウェアバージョン) とデバイスのシリアル番号とバッテリの割合を確認できます。
- 組織で MDM を使用して [接続/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) を無効にしている場合、デバイスに接続することはできません。

## Mixed reality の写真とビデオを共有する

Mixed reality の写真やビデオをキャプチャすると、プレビューが表示されます。 プレビューの上にある [ **共有** ] アイコンを選択して、共有アシスタントを表示します。 そこから、写真やビデオを共有するエンドポイントを選択できます。

また、mixed reality 写真とビデオを自動的にアップロードすることで、OneDrive から mixed reality 写真とビデオを共有することもできます。 HoloLens で OneDrive アプリを開き、個人の [Microsoft アカウント](https://account.microsoft.com) でサインインします (まだインストールしていない場合)。 [ **設定** ] アイコンを選択し、[ **カメラアップロード**] を選択します。 カメラのアップロードをオンにします。 Mixed reality の写真とビデオは、HoloLens でアプリを起動するたびに OneDrive にアップロードされるようになりました。

> [!NOTE]
> 個人用の Microsoft アカウントで OneDrive にサインインしている場合のみ、OneDrive でカメラアップロードを有効にすることができます。 HoloLens または学校のアカウントを使用して HoloLens をセットアップした場合は、OneDrive アプリで個人用の Microsoft アカウントを追加して、この機能を有効にすることができます。

## Mixed reality キャプチャの制限事項

- Mixed reality キャプチャを使う場合、HoloLens のフレームレートは 30 Hz に半減します。
- ビデオの最大文字数は5分です。
- 写真/ビデオカメラが別のアプリケーションで既に使用されている場合、ライブストリーミング中、またはシステムリソースが少ない場合は、写真やビデオの解像度が低くなることがあります。

## 既定のファイル形式と解像度

### 既定の写真の形式と解像度

|  デバイス  |  形式  |  拡張機能  |  解決方法  |
|----------|----------|----------|----------|
| HoloLens 2 | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens (第1世代) | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408x79 2px |

### 記録されたビデオ形式と解像度

| デバイス | 形式 | 拡張機能 | 解決方法 | 速度 | オーディオ |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30fps | 48 Khz ステレオ |
| HoloLens (第1世代) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | 48 Khz ステレオ |
