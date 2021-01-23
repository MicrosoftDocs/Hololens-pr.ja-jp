---
title: HoloLens の既知の問題
description: Unity と Windows Device Portal を使用している HoloLens のお客様や開発者に影響を与える可能性がある既知の問題と回避策の一覧を最新の状態に保ってください。
keywords: トラブルシューティング, 既知の問題, ヘルプ
author: mattzmsft
ms.author: mazeller
ms.date: 11/30/2020
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
- HoloLens 2
ms.openlocfilehash: 54bc090352983e814c64deea8f1f401c24e3261b
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284078"
---
# HoloLens の既知の問題

これは、HoloLens デバイスの既知の問題の現在の一覧です。 奇数の動作が表示される場合は、まずここで確認してください。 この一覧は、新しい問題が検出または報告された場合、または将来の HoloLens ソフトウェア更新プログラムで問題が解決された場合に更新されます。

>[!NOTE]
> - If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).
> - If the issue you are facing is blocking you, addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).

- [すべての HoloLens 世代の既知の問題](#known-issues-for-all-hololens-generations)
- [HoloLens 2 デバイスの既知の問題](#known-issues-for-hololens-2-devices)
- [HoloLens (第 1 世代) の既知の問題](#known-issues-for-hololens-1st-gen)
- [HoloLens エミュレーターの既知の問題](#known-issues-for-hololens-emulator)

## すべての HoloLens 世代の既知の問題

### Unity

- HoloLens [の開発](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) に推奨される最新バージョンの Unity のツールのインストールに関するページをご覧ください。
- Unity HoloLens Technical Preview に関する既知の問題については [、HoloLens Unity フォーラムに記載されています](https://forum.unity3d.com/threads/known-issues.394627/)。

### Windows Device Portal

- Mixed Reality キャプチャの Live Preview 機能では、数秒の待機時間が発生する可能性があります。

- [仮想入力] ページの [仮想ジェスチャ] セクションの下にある [ジェスチャ] コントロールと [スクロール] コントロールは機能しません。 それらを使用した場合、効果はありません。 同じページ上の仮想キーボードは正しく動作します。

- 設定で開発者モードを有効にした後、Device Portal を有効にする切り替えに数秒かかる場合があります。

### OneDrive カメラのアップロード

HoloLens 用 OneDrive アプリでは、仕事用または学校アカウントの自動カメラ アップロードはサポートされていません。

回避策:

- ビジネスで実行可能な場合は、コンシューマー向け Microsoft アカウントでカメラの自動アップロードがサポートされます。 Microsoft アカウントには、自分の仕事用または学校用のアカウントに加えてサインインできます (OneDrive アプリはデュアル サインインをサポートしています)。 OneDrive 内の Microsoft アカウント プロファイルから、カメラ ロールの自動アップロードを有効にできます。

- 写真を自動的にアップロードするためにコンシューマー向け Microsoft アカウントを安全に使用できない場合は、OneDrive アプリから手動で写真を仕事または学校のアカウントにアップロードできます。 これを行うには、OneDrive アプリで、自分の仕事または学校のアカウントにサインインしている必要があります。 ボタンを選択 **+** し、[アップロード] を **選択します**。 [ピクチャ] ページの [カメラ ロール] に移動して、アップロード **する>見つける**。 アップロードする写真またはビデオを選択し、[開く] ボタン **を選択** します。

## HoloLens 2 デバイスの既知の問題

### Microsoft Edge の起動に失敗する

少数のお客様から、Microsoft Edge の起動に失敗する問題が報告されています。 これらのお客様の場合、問題は再起動を通じて保持され、Windows またはアプリケーションの更新プログラムでは解決されません。 If you're experiencing this issue and you've confirmed [Windows is up-to-date,](hololens-updates.md#manually-check-for-updates)please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.

既知の回避策はありません。これまで問題の根本原因を特定できなかったので、回避策はありません。 フィードバック Hub 経由でバグを報告すると、調査に役立ちます。

### キーボードが特殊文字に切り替えない

OOBE 中に問題が発生し、ユーザーが仕事または学校のアカウントを選択してパスワードを入力すると、&123 ボタンをタップしてキーボードの特殊文字に切り替えようとしても、特殊文字に変わりません。 

回避方法:
-   キーボードを閉じ、テキスト フィールドをタップしてもう一度開きます。
-   パスワードを誤って入力します。 次回キーボードを再起動すると、期待通り動作します。
- Web 認証を行い、キーボードを閉じて、別 **のデバイスから [サインイン] を選択します**。 
-   数字のみを入力する場合、ユーザーは特定のキーを長押しして展開されたメニューを開くことができます。
-   USB キーボードを使用する。

これは、次に影響を与える影響ではありません。
- 個人アカウントの使用を選択したユーザー。

### Blue screen is shown after unenrolling from Insider preview builds on a device reflashed with a Insider build

これは、Insider プレビュー ビルドに含まれるユーザーに影響を与え、HoloLens 2 を新しい Insider Preview ビルドで再フラッシュし、Insider プログラムから登録解除したユーザーに影響を与える問題です。 

これは、次に影響を与える影響ではありません。
- Windows Insider に登録されていないユーザー 
- Insider:
    - Insider ビルドがバージョン 18362.x 以降にデバイスを登録している場合
    - Insider が署名した 19041.x ビルドをフラッシュし、Insider プログラムへの登録を行った場合 

回避: 
- 問題を回避する 
    - Insider 以外のビルドをフラッシュします。 定期的な月次更新プログラムの 1 つ。 
    - Insider Preview を利用する
- デバイスを再フラッシュする

    1. [HoloLens 2](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2)を手動でフラッシュ モードにします。接続していない間は電源を完全にオフにします。 次に、音量を上げながら電源ボタンをタップします。
    
    1. PC に接続し、Advanced Recovery Companion を開きます。 
    
    1. HoloLens 2 を既定のビルドにフラッシュします。   

## HoloLens (第 1 世代) の既知の問題

### デバイスから HoloLens に接続して展開Visual Studio

> [!NOTE]
> Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue. このエラーが発生しないように、この最新バージョンに更新することをお勧めします。

Visual Studio VS 2019 バージョン 16.2 がリリースされました。この問題の修正プログラムが含まれています。 このエラーが発生しないように、この最新バージョンに更新することをお勧めします。

問題の根本原因: Visual Studio 2015 または Visual Studio 2017 の初期リリースを使用して HoloLens にアプリケーションを展開およびデバッグし、その後、同じ HoloLens で最新バージョンの Visual Studio 2017 または Visual Studio 2019 を使用したユーザーが影響を受ける可能性があります。 新しいリリースの Visual Studioは新しいバージョンのコンポーネントを展開しますが、以前のバージョンのファイルはデバイスに残され、その結果、新しいバージョンが失敗します。  これにより、"DEP0100" というエラー メッセージが表示されます。ターゲット デバイスで開発者モードが有効になっているか確認してください。 エラー \<ip\> 80004005 が原因で開発者用ライセンスを取得できない。

#### 回避策

現在、チームは修正に取り組み中です。 その間、次の手順を使用して問題を回避し、展開とデバッグのブロックを解除できます。  

1. Visual Studio を開きます。

1. ファイルの**新しい**  >  **プロジェクトを選択**  >  **します**。

1. **Visual C#**  >  **Windows デスクトップ コンソール**アプリ  >  **(.NET Framework) を選択します**。

1. プロジェクトに名前 ("HoloLensDeploymentFix" など) を付け、フレームワークが少なくとも .NET Framework 4.5 に設定されている必要があります **。[OK]** を選択します。

1. ソリューション エクスプローラーで **[参照]** ノードを右クリックし、次の参照を追加します ([参照] セクションに **選択し、[** 参照] を **選択します**)。

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > 10.0.18362.0 がインストールされていない場合は、最新バージョンを使用してください。 

1. ソリューション エクスプローラーでプロジェクトを右クリックし、[既存**** の項目の追加  >  **] を選択します**。

1. C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 を参照し、フィルターを **[すべてのファイル] (\*.\*)** に変更します。

1. ユーザー設定とSirepClient.dll両方をSshClient.dll、[追加] を選択 **します**。

1. ソリューション エクスプローラーで両方のファイルを見つけて選択し (ファイルの一覧の一番下にある**** 必要があります)、[プロパティ]**** ウィンドウで [出力ディレクトリにコピー] を [常にコピー] に**変更します**。

1. ファイルの上部で、ステートメントの既存のリストに次を `using` 追加します。

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. 内部に `static void Main(...)` 、次のコードを追加します。

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. [ビルド**ソリューション**  >  **] を選択します**。

1. コマンド プロンプト ウィンドウを開き、コンパイル済みの .exe ファイルを含むフォルダー (C:\MyProjects\HoloLensDeploymentFix\bin\Debug など) に cd を開きます。

1. 実行可能ファイルを実行し、デバイスの IP アドレスをコマンド ライン引数として指定します。 (USB を使用して接続されている場合は、127.0.0.1 を使用できます。それ以外の場合は、デバイスの IP アドレスWi-Fi使用します)。 たとえば、"HoloLensDeploymentFix 127.0.0.1" などです。

1. メッセージが表示されることなくツールが終了すると (数秒で終了する必要があります)、Visual Studio 2017 以降から展開とデバッグが可能になります。  ツールを継続して使用する必要はありません。

今後、更新プログラムが利用可能になったら、その更新プログラムを提供します。

### HoloLens での Microsoft Store とアプリの起動に関する問題

> [!NOTE]
> Last Update: 4/2 @ 10 AM - Issue resolved. 

HoloLens で Microsoft Store とアプリを起動しようとするときに問題が発生する可能性があります。 バックグラウンド アプリの更新プログラムが特定のシーケンスでフレームワーク パッケージの新しいバージョンを展開し、1 つ以上の依存アプリが実行中であるときに、この問題が発生すると判断しました。 この場合、アプリの自動更新により、新しいバージョンの .NET Native Framework (バージョン 10.0.25531 から 10.0.27413) が配信され、実行中のアプリが以前のバージョンのフレームワークを使用しているすべての実行中のアプリに対して正しく更新されませんでした。  フレームワーク更新のフローは次のとおりです。 

1. 新しいフレームワーク パッケージがストアからダウンロードされ、インストールされます。

1. 以前のフレームワークを使用しているすべてのアプリは、新しいバージョンを使用するように "更新" されます。

完了前に手順 2 が中断された場合、新しいフレームワークが登録されていないアプリはスタート メニューから起動されません。  HoloLens 上のアプリは、この問題の影響を受ける可能性があります。

ハングしたアプリを閉じ、フィードバック Hub、3D ビューアー、フォトなどの他のアプリを起動すると問題が解決すると報告されているユーザーもいます。ただし、この問題は &mdash; 100% は機能しません。

この問題が原因で更新自体が発生したのではなく、OS のバグが原因で .NET Native Framework の更新プログラムが正しく処理されないという原因が根本原因です。 修正プログラムが特定され、修正プログラムを含む更新プログラム (OS バージョン 17763.380) がリリースされました。  

お使いのデバイスで更新プログラムを利用できる場合は、次の方法を使用してください。

1. 設定アプリに移動し、[セキュリティの更新 **] &開きます**。

1. [更新 **プログラムの確認] を選択します**。

1. 17763.380 への更新プログラムが利用可能な場合は、このビルドに更新して、アプリハングバグの修正プログラムを受信してください。

1. このバージョンの OS に更新すると、アプリは期待通り動作する必要があります。

さらに、すべての HoloLens OS リリースと同様に、FFU イメージを Microsoft ダウンロード センター [に投稿しました](https://aka.ms/hololensdownload/10.0.17763.380)。

更新プログラムを利用しない場合は、3/29 の現在、Microsoft Store UWP アプリの新しいバージョンがリリースされました。 ストアの更新バージョンを作成した後:

1. ストアを開き、読み込み確認します。
1. ブルーム ジェスチャを使ってメニューを開きます。
1. 以前に破損したアプリを開くことを試みる。
1. それでも起動できない場合は、破損したアプリのアイコンを長押ししてアンインストールを選択します。
1. ストアからこれらのアプリを再インストールします。

デバイスがまだアプリを読み込めない場合は、次の手順に従って、ダウンロード センターから .NET Native Framework とランタイムのバージョンをサイドロードできます。

1. この zip [ファイルは、Microsoft](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) ダウンロード センターからダウンロードしてください。 解凍すると、2 つのファイルが生成されます。  Microsoft.NET.Native.Runtime.1.7.appx と Microsoft.NET.Native.Framework.1.7.appx。

1. デバイスが開発者のロックを解除されていないことを確認してください。  手順については、Windows [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) の使用に関するページをご覧ください。

1. その後、Windows Device Portal にアクセスします。 USB を使用してこれを行うには、ブラウザーに入力します http://127.0.0.1:10080 。

1. Windows Device Portal をセットアップしたら、ダウンロードした 2 つのファイルを "サイド ロード" する必要があります。 これを行うには、[アプリ] セクションに移動して [アプリ] を**** 選択するまで、左側のバーを下に移動する必要**があります**。

1. 次のような画面が表示されます。  「アプリのインストール」というセクションに移動**** し、それらの 2 つの APPX ファイルを展開した場所を参照します。 一度に実行できるのは 1 つのみなので、最初の操作を選択した後、[展開] セクションの下の [移動] をクリックします。 次に、2 番目の APPX ファイルに対してこれを行います。

   ![Windows Device Portal でアプリをSide-Loadedする](images/20190322-DevicePortal.png)
   
1. この時点で、アプリケーションが再び動作し始め、ストアにアクセスできると思います。

1. 場合によっては、影響を受けるアプリが起動する前に、3D ビューアー アプリを起動する追加の手順を実行する必要があります。 

この問題を解決するためのプロセスを完了して、お待ちしています。また、コミュニティと協力して、Mixed Reality エクスペリエンスを成功に引き続きご利用ください。

### デバイス更新

- 新しい更新の 30 秒後に、シェルが一度消える場合があります。 ブルーム ジェスチャを **実行** してセッションを再開してください。

### Visual Studio

- HoloLens [の開発](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) に推奨される最新バージョンの Visual Studioインストールに関するページをご覧ください。

- Visual Studio から HoloLens にアプリを展開すると、次のエラーが表示される場合があります。要求された操作は、ユーザーマップセクションが開いているファイルに対して実行 **できません。(HRESULT からの例外: 0x800704C8)**。 この場合は、もう一度やり直してください。展開は一般に成功します。

### API

- アプリケーションがユーザーの背後の [フォーカス](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) ポイントまたは標準を camera.forward に設定すると、Mixed Reality キャプチャの写真やビデオにホログラムは表示されません。 このバグが Windows で修正されるまでは、アプリケーションがフォーカス[](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity)ポイントをアクティブに設定する場合は、平面の法線がカメラ前方とは逆に設定されている必要があります (たとえば、normal = -camera.forward)。

### Xbox ワイヤレス コントローラー

- Xbox ワイヤレス コントローラー S は、HoloLens で使用する前に更新する必要があります。 コントローラーと[](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter)HoloLens をペアリングする前に、最新の情報を確認してください。

- Xbox ワイヤレス コントローラーの接続中に HoloLens を再起動した場合、コントローラーは HoloLens に自動的に再接続されません。 [ガイド] ボタンのライトは、コントローラーの電源が 3 分後にオフになるまで、遅く点滅します。 コントローラーを直ちに再接続するには、ライトがオフになるまでガイド ボタンを押してコントローラーの電源を切ります。 コントローラーの電源を再び入れ、HoloLens に再接続します。

- Xbox ワイヤレス コントローラーの接続中に HoloLens がスタンバイ状態になる場合、コントローラー上の入力は HoloLens を起動します。 使用が完了したら、コントローラーの電源をオフにすることで、これを回避できます。

## HoloLens エミュレーターの既知の問題

- Microsoft Store のすべてのアプリがエミュレーターと互換性があるというのではありません。 たとえば、Young Conker と Fragments はエミュレーターで再生できません。
- エミュレーターで PC の Web カメラを使用することはできません。
- Windows Device Portal の Live Preview 機能はエミュレーターでは動作しません。 Mixed Reality のビデオや画像は引き続きキャプチャできます。
