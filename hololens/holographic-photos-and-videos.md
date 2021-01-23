---
title: Mixed Reality の写真とビデオのキャプチャと管理
description: HoloLens Mixed Reality デバイスを使って Mixed Reality の写真やビデオをキャプチャ、表示、共有する方法について学習します。
keywords: hololens, 写真, ビデオ, キャプチャ, mrc, Mixed Reality キャプチャ, 写真, カメラ, ストリーム, ライブストリーム, デモ
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
ms.openlocfilehash: 6b7bb29ab76a16aa518ca38ee04f434dfd0cf0c7
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283508"
---
# Mixed Reality の写真とビデオを作成する

HoloLens は、現実世界とデジタル世界を混在するエクスペリエンスをユーザーに提供します。  Mixed Reality キャプチャ (MRC) を使うと、そのエクスペリエンスを写真やビデオとしてキャプチャしたり、見た情報をリアルタイムで他のユーザーと共有することができます。

Mixed Reality キャプチャでは、一人一人の視点を使用して、他のユーザーがホログラムを見て見る可能性があります。 第三者視点の場合は、視点 [ビューを使用します](https://docs.microsoft.com/windows/mixed-reality/spectator-view)。 Spectator ビューは、デモに特に役立ちます。

友人や同僚の間でビデオを共有するのも楽しい一方で、ビデオは他のユーザーにアプリの使用やアプリやエクスペリエンスの問題の伝達を教えるのに役立ちます。

> [!NOTE]
> Mixed Reality キャプチャ エクスペリエンスを起動できない場合、HoloLens が作業デバイスである場合は、システム管理者に確認してください。 会社のポリシーを通じてカメラへのアクセスを制限できます。

## Mixed Reality の写真をキャプチャする

HoloLens で Mixed Reality の写真を撮影する方法は複数あります。ハードウェア ボタン、音声、またはスタート メニューを使用できます。

### 写真を撮影するハードウェア ボタン

現在のビューの簡単な写真を撮影するには、音量を上げ、音量を下げボタンを同時に押します。  これは、スクリーンショットや印刷画面の HoloLens バージョンと少し似たものになります。

- [HoloLens 2 のボタンの場所](hololens2-hardware.md)
- [HoloLens (第 1 世代) 上のボタンの場所](hololens1-hardware.md#hololens-components)

> [!NOTE]
> 音量を**上げ、****音量を下**げボタンを 3 秒間押すと、写真を撮影するのではなく、ビデオの録画が開始されます。 録音を停止するには、音量を**上げ下げ****ボタンと音量を下げボタンの両方を**同時にタップします。

### 写真を撮影する音声コマンド

HoloLens 2 バージョン 2004 (以降) では、「写真を撮る」と言います。

HoloLens (第 1 世代) または HoloLens 2 バージョン 1903 では、「コルタナさん、写真を撮って」と言います。

### 写真を撮影するスタート メニュー

スタート ジェスチャを使ってスタート画面に移動 **し、** カメラ アイコンを **選択** します。

キャプチャする画像の方向に頭を向け、エアタップで [写真を](hololens2-basic-usage.md#touch-holograms-near-you) 撮影します。 引き続きエアタップして、追加の写真をキャプチャできます。 キャプチャした写真は、デバイスに保存されます。

写真のキャプチャを終了するには、もう一度スタート ジェスチャを使います。  

## Mixed Reality ビデオをキャプチャする

HoloLens で Mixed Reality のビデオを録画する方法は複数あります。ハードウェア ボタン、音声、またはスタート メニューを使用できます。

### ビデオを記録するハードウェア ボタン

ビデオを記録する最も簡単な方法は、音量を上**** げ、音量**** を下げ、3 秒のカウントダウンが始まるまでボタンを同時に長押しする方法です。 レコーディングを停止するには、両方のボタンを同時にタップします。

> [!NOTE]
> 音量を上**げ、****音量を下**げボタンを同時にすばやく押すと、ビデオを録画するのではなく、写真を撮影できます。

### 音声によるビデオの録音

HoloLens 2 バージョン 2004 (以降) で、「記録を開始する」と言います。 レコーディングを停止するには、「記録を停止する」と言います。

HoloLens (第 1 世代) または HoloLens 2 バージョン 1903 では、「コルタナさん、レコーディングを開始してください」と言います。 レコーディングを停止するには、「Hey Cortana, stop recording」と言います。

### ビデオを録画するスタート メニュー

スタート ジェスチャを使ってスタート画面に移動 **し、** ビデオ アイコンを **選択** します。 キャプチャする情報の方向に頭を向け、エア [タップ](hololens2-basic-usage.md#touch-holograms-near-you) でレコーディングを開始します。 3 秒のカウントダウンが行い、レコーディングが開始されます。

記録を停止するには、スタート ジェスチャを使って、強調表示されているビデオ アイコン **を選択** します。 ビデオはデバイスに保存されます。

> [!NOTE]
> **HoloLens (第 1 世代) にのみ適用されます。**  
> [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)は、HoloLens (第 1 世代) でのスタート ジェスチャと Windows ボタンの動作を変更します。 更新の前に、スタート ジェスチャまたは Windows ボタンはビデオ録画を停止します。 ただし、更新後、スタート ジェスチャまたは Windows ボタンによってスタート メニュー (**** イマーシブ アプリの場合はクイック アクション メニュー) が開き、**** 強調表示されたビデオ アイコンを選択して録画を停止できます。 ****

## 表示される情報をリアルタイムで共有する

HoloLens で表示される情報を、友人や同僚とリアルタイムで共有できます。 いくつかの方法を使用できます。

1. Miracast 対応デバイスまたはアダプターに接続してテレビで視聴する。
1. [Windows Device Portal を使用](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)して PC で視聴する
1. Microsoft [HoloLens コンパニオン アプリを使って](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) PC で視聴する。
1. [Microsoft Dynamics 365 リモート](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist)アシスト アプリを展開すると、フロント ライン ワーカーはリモートの専門家に表示される情報をストリーミングできます。 リモートの専門家は、フロント ライン ワーカーを言葉で、または自分の世界で注釈を付ける方法で案内できます。

> [!NOTE]
> Windows Device Portal または Microsoft HoloLens コンパニオン アプリで表示される情報を共有するには、HoloLens が開発者モードである [必要があります](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。

### Miracast を使ったストリーム ビデオ

スタート ジェスチャを使ってスタート画面に移動 **し、** 接続アイコンを **選択** します。 表示されるピッカーから、接続する Miracast 対応デバイスまたはアダプターを選択します。

共有を停止するには、スタート ジェスチャを使って、強調表示されている接続アイコン **を選択** します。 ストリーミングしていたため、デバイスには何も保存されません。

> [!NOTE]
> Miracast のサポートは [、Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)から HoloLens (第 1 世代) で有効にされました。

### Windows Device Portal を使ったリアルタイム ビデオ

Windows Device Portal を使用して共有するには、HoloLens で開発者モードを有効にする必要があります。開発者向けドキュメントの指示に従って、開発者モードをセットアップし [、Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)に移動します。

### Microsoft HoloLens コンパニオン アプリ

Microsoft HoloLens コンパニオン アプリを使って共有するには、HoloLens で開発者モードを有効にする必要があります。開発者向けドキュメントの指示に従って、開発者モードを [設定します](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。 次に [、Microsoft HoloLens コンパニオン](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) アプリをダウンロードし、アプリ内の指示に従って HoloLens に接続します。

アプリを HoloLens でセットアップしたら、アプリのメイン メニューから **Live ストリーム** オプションを選択します。

## Mixed Reality の写真とビデオを表示する

Mixed Reality の写真とビデオは、デバイスの "カメラ ロール" に保存されます。 エクスプローラー アプリを使って、HoloLens でこのフォルダーの内容を参照できます ([ピクチャ] > [カメラ ロール] に移動します)。

HoloLens にプレインストールされているフォト アプリで、Mixed Reality の写真やビデオを表示することもできます。 自分の世界で写真をピン留めするには、フォト アプリで写真を選択し、[混在世界で **配置] を選択します**。 写真を配置した後で、世界中に写真を移動できます。

HoloLens に接続された PC で Mixed Reality の写真やビデオを表示または保存するには [、MTP](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) を使って Windows Device Portal または PC の [エクスプローラーを使います](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)。

### エクスプローラーを使って画像、ビデオ、ファイルを取得する

他のモバイル デバイスと同様に、HoloLens を PC に接続してエクスプローラーを表示し、HoloLens ライブラリ (写真、ビデオ、ドキュメント) にアクセスして簡単に転送できます。 この方法は使いやすく、デバイス ポータルや Wi-Fi の使用は必要とされません。

1. デバイスのロックを解除します。
1. USB 経由でデバイスを PC に接続します。
1. エクスプローラーが PC で開きます。
1. [Navigate to]: This PC\\*yourhololensname*\Internal Storage\Pictures\Camera Roll
1. 必要なファイルを PC にコピーします。

ヒント: 
- ファイルが表示されていない場合は、HoloLens にサインインしてデータへのアクセスを有効にしてください。
- [ドキュメント] フォルダーから診断ファイルなど、他のフォルダー内の [他](hololens-diagnostic-logs.md#offline-diagnostics) のファイルを取得できます。
- PC のエクスプローラーで[デバイスのプロパティ] を選択すると、Windows Holographic OS のバージョン番号 (ファームウェアバージョン)、デバイスのシリアル番号、バッテリの割合を確認できます。
- 組織が MDM を使用して [Connectivity/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) を無効にしている場合、デバイスに接続できません。

## Mixed Reality の写真とビデオを共有する

Mixed Reality の写真やビデオをキャプチャすると、プレビューが表示されます。 プレビューの **上にある** 共有アイコンを選択して、共有アシスタントを表示します。 そこから、その写真またはビデオを共有するエンド ポイントを選択できます。

Mixed Reality の写真やビデオを自動的にアップロードすることで、OneDrive から Mixed Reality の写真やビデオを共有することもできます。 HoloLens で OneDrive アプリを開き、まだサインインしていない場合は、個人用 [の Microsoft](https://account.microsoft.com) アカウントでサインインします。 設定アイコンを **選択し** 、[カメラのアップロード **] を選択します**。 カメラのアップロードを有効にする。 HoloLens でアプリを起動するごとに、Mixed Reality の写真とビデオが OneDrive にアップロードされます。

> [!NOTE]
> OneDrive でカメラのアップロードを有効にできるのは、個人用の Microsoft アカウントで OneDrive にサインインしている場合のみです。 HoloLens を仕事または学校のアカウントでセットアップする場合は、OneDrive アプリで個人用の Microsoft アカウントを追加して、この機能を有効にできます。

## Mixed Reality キャプチャの制限事項

- Mixed Reality キャプチャを使用している間、HoloLens のフレームレートは 30 Hz に半分になります。
- 写真/ビデオ カメラが別のアプリケーションで既に使用されている場合、ライブ ストリーミング中、またはシステム リソースが低い場合は、写真やビデオの解像度が低下する可能性があります。

### 最大録音長

Windows Holographic より前の HoloLens 2 デバイスでは、デバイスに記録されたバージョン 20H2 のビデオは、最大で 5 分の長さに制限されました。

お客様からのフィードバックにより、Mixed Reality キャプチャの記録 [の長さが長くなっています](holographic-photos-and-videos.md)。 Mixed Reality キャプチャは既定で 5 分に制限されず、使用可能なディスク領域に基づいて最大記録長が計算されます。 デバイスは、利用可能なディスク領域に基づいてビデオ録画の最大再生時間を、合計ディスク領域の 80% まで推定します。

> [!NOTE]
> 次のいずれかの場合、HoloLens は既定のビデオ録画の長さ (5 分) を使用します。
> - 推定最大記録時間は、既定の 5 分よりも小さくてす。
> - 使用可能なディスク領域は、ディスク領域全体の 20% 未満です。

## 既定のファイル形式と解像度

### 既定の写真の形式と解像度

|  デバイス  |  形式  |  拡張機能  |  解決方法  |
|----------|----------|----------|----------|
| HoloLens 2 | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens (第 1 世代) | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408x792px |

### 録画されたビデオの形式と解像度

| デバイス | 形式 | 拡張機能 | 解決方法 | 速度 | オーディオ |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30fps | 48kHz ステレオ |
| HoloLens (第 1 世代) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | 48kHz ステレオ |
