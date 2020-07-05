---
title: HoloLens の既知の問題
description: これは、HoloLens 開発者に影響を与える可能性がある既知の問題の一覧です。
keywords: トラブルシューティング、既知の問題、ヘルプ
author: mattzmsft
ms.author: mazeller
ms.date: 4/20/2020
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
ms.openlocfilehash: 330a7fd549a2b847f77715ca90d69f1d4df1fb1d
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829296"
---
# HoloLens の既知の問題

これは、HoloLens デバイスの既知の問題の最新の一覧です。 奇数の動作が表示される場合は、まずここを確認してください。 この一覧は、新しい問題が検出または報告された場合、または今後の HoloLens ソフトウェアの更新で問題が解決された場合に、更新されます。

>[!NOTE]
> - ブロックされていない問題が見つかった場合は、[フィードバック Hub](hololens-feedback.md)経由で HoloLens デバイスで報告してください。
> - 問題が解決している場合は、フィードバックを送信するために、[サポートリクエスト](https://aka.ms/hlsupport)を提出してください。

- [すべての HoloLens ジェネレーションの既知の問題](#known-issues-for-all-hololens-generations)
- [HoloLens 2 デバイスの既知の問題](#known-issues-for-hololens-2-devices)
- [HoloLens の既知の問題 (第1世代)](#known-issues-for-hololens-1st-gen)
- [HoloLens エミュレーターの既知の問題](#known-issues-for-hololens-emulator)

## すべての HoloLens ジェネレーションの既知の問題

### Unity

- 「HoloLens の開発に推奨される最新バージョンの Unity 用の[ツールをインストール](https://docs.microsoft.com/windows/mixed-reality/install-the-tools)する」を参照してください。
- Unity HoloLens のテクニカルプレビューの既知の問題については、「 [HoloLens Unity フォーラム](https://forum.unity3d.com/threads/known-issues.394627/)」で説明しています。

### Windows Device Portal

- Mixed Reality キャプチャのライブプレビュー機能は、数秒間の待機時間を示す場合があります。
- 仮想入力ページでは、[仮想ジェスチャー] セクションのジェスチャとスクロールコントロールは機能しません。 これらを使用しても効果はありません。 同じページの仮想キーボードは正しく動作します。
- [設定] で開発者モードを有効にした後、デバイスポータルが有効になるまでに数秒かかることがあります。

## HoloLens 2 デバイスの既知の問題

### Insider ビルドを使用して、デバイス reflashed で Insider preview ビルドから登録解除した後に、青色の画面が表示される

これは、Insider preview ビルドを行っているユーザーに影響を与える問題であり、新しい insider preview ビルドで HoloLens 2 を reflashed してから、Insider プログラムから登録を解除します。 

これは、次のような影響はありません。
- Windows Insider に登録されていないユーザー 
- 者
    - Insider ビルドがバージョン18362であるため、デバイスが登録されている場合
    - Insider 署名された19041ビルドをフラッシュして Insider プログラムに登録したままになっている場合 

回避策: 
- 問題を回避する 
    - Insider 以外のビルドをフラッシュします。 通常の月次更新プログラムのいずれか。 
    - Insider プレビューを表示する
- デバイスの Reflash
    1. 接続していないときに完全に電源を切ることにより、 [HoloLens 2 を手動でフラッシュモードに](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2)します。 音量を上げながら、Power ボタンをタップします。
    1. PC に接続し、アドバンスト回復コンパニオンを開きます。 
    1. HoloLens 2 を既定のビルドにフラッシュします。   

## HoloLens の既知の問題 (第1世代)

### Visual Studio 経由で HoloLens に接続して展開できない

> [!NOTE]
> 最終更新日: 8/8 @ 5: 午後11時-Visual Studio は VS 2019 バージョン16.2 をリリースしました。この問題の修正プログラムが含まれています。 このエラーが発生しないように、この最新バージョンに更新することをお勧めします。

Visual Studio は VS 2019 バージョン16.2 をリリースしました。この問題の修正プログラムが含まれています。 このエラーが発生しないように、この最新バージョンに更新することをお勧めします。

問題の原因: visual studio 2015 または Visual Studio 2017 の早期リリースを使用しているユーザーが、HoloLens でアプリケーションを展開してデバッグし、その後、同じ HoloLens で visual Studio 2017 または Visual Studio 2019 の最新バージョンを使用している場合は、この問題が発生します。 Visual Studio の新しいリリースでは、新しいバージョンのコンポーネントが展開されますが、古いバージョンのファイルはデバイス上に残っているため、新しいバージョンは失敗します。  これにより、次のエラーメッセージが表示されます: DEP0100: ターゲットデバイスで開発者モードが有効になっていることを確認してください。 エラー80004005により、の開発者用ライセンスを取得できませんでした \<ip\> 。

#### 回避策

現在、チームは修正に向けて取り組んでいます。 それまでの間、次の手順を使用して、問題を回避し、展開およびデバッグのブロックを解除することができます。  

1. Visual Studio を開く
1. [**ファイル**] の [  >  **新しい**  >  **プロジェクト**] を選びます。
1. [ **Visual C#**  >  **Windows デスクトップ**  >  **コンソールアプリ (.net Framework)**] を選択します。
1. プロジェクトに名前を付け ("HoloLensDeploymentFix" など)、フレームワークが少なくとも .NET Framework 4.5 に設定されていることを確認して、[ **OK]** を選択します。
1. ソリューションエクスプローラーで [**参照設定**] ノードを右クリックし、次の参照を追加します ([**参照**] セクションを選び、[**参照**] を選択します)。

    ```CMD
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > 10.0.18362.0 をまだインストールしていない場合は、最新バージョンを使用します。 

1. ソリューションエクスプローラーでプロジェクトを右クリックし、[ **Add**  >  **既存項目**の追加] を選択します。
1. C:\Program Files (x86) \Windows Kits\10\bin\10.0.18362.0\x86 を参照して、フィルターを**すべてのファイル (\ *. \ *)** に変更します。
1. SirepClient.dll と SshClient.dll の両方を選択して、[**追加**] を選択します。
1. ソリューションエクスプローラーで両方のファイルを見つけて選び (ファイルの一覧の一番下にある必要があります)、[**プロパティ**] ウィンドウの [**出力ディレクトリにコピー** ] を選択して、**常にコピー**します。
1. ファイルの上部で、次のステートメントを既存のステートメント一覧に追加し `using` ます。

    ```CMD
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. の中 `static void Main(...)` に、次のコードを追加します。

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. [**ビルド**  >  **ビルドソリューション**] を選びます。
1. コマンドプロンプトウィンドウを開き、コンパイルされた .exe ファイルを含むフォルダー (C:\MyProjects\HoloLensDeploymentFix\bin\Debug など) を開きます。
1. 実行可能ファイルを実行して、デバイスの IP アドレスをコマンドライン引数として指定します。 (USB を使って接続している場合は、127.0.0.1 を使用できます。それ以外の場合は、デバイスの Wi-fi IP アドレスを使用してください)。 たとえば、"HoloLensDeploymentFix 127.0.0.1" とします。

1. すべてのメッセージが表示されることなくツールが終了すると (数秒しかかかりません)、Visual Studio 2017 以降から展開とデバッグを行うことができるようになります。  引き続きこのツールを使用する必要はありません。

利用可能になったら、さらに更新プログラムを提供します。

### HoloLens での Microsoft ストアとアプリの起動に関する問題

> [!NOTE]
> 最終更新: 4/2 @ 10 AM-問題が解決されました。 

HoloLens で Microsoft Store とアプリを起動しようとすると、問題が発生する可能性があります。 バックグラウンドアプリの更新によって、1つ以上の依存アプリが実行されているときに、新しいバージョンの framework パッケージが特定のシーケンスで展開されると、問題が発生すると判断されました。 この場合、アプリの自動更新によって新しいバージョンの .NET ネイティブフレームワーク (バージョン10.0.25531 から 10.0.27413) が提供されたため、実行中のアプリは、以前のバージョンのフレームワークを使用するすべての実行中のアプリで正しく更新されませんでした。  フレームワークの更新のフローは、次のようになります。 

1. 新しいフレームワークパッケージがストアからダウンロードされ、インストールされます。
1. 以前のフレームワークを使用するすべてのアプリが新しいバージョンを使用するように更新されている

ステップ2が完了する前に中断された場合、新しいフレームワークが登録されていないアプリは、[スタート] メニューから起動できません。  HoloLens 上のアプリは、この問題の影響を受ける可能性があります。

ハングしたアプリを閉じて、フィードバック Hub、3D Viewer、または写真などの他のアプリを起動すると、問題が解決されるという報告がありましたが、その場合、 &mdash; 100% は有効ではありません。

この問題によって更新プログラム自体は発生しませんでしたが、この問題は、.NET ネイティブフレームワークの更新によって不適切に処理されたバグであると考えられています。 修正プログラムを特定し、修正プログラム (OS バージョン 17763.380) をリリースしたことをお知らせします。  

デバイスが更新プログラムを受け取ることができるかどうかを確認するには、次のことを行ってください。

1. [設定] アプリに移動して、[**更新 & セキュリティ**] を開きます。
1. [**更新プログラムの確認**] を選びます。
1. 17763.380 への更新プログラムが利用できる場合は、このビルドに更新して、アプリがハングするバグの修正プログラムを入手してください。
1. このバージョンの OS への更新時に、アプリは期待どおりに動作する必要があります。

さらに、すべての HoloLens OS リリースの場合と同様に、 [Microsoft ダウンロードセンター](https://aka.ms/hololensdownload/10.0.17763.380)に ffu イメージを投稿しました。

更新を実行したくない場合は、3/29 の時点で新しいバージョンの Microsoft Store UWP アプリをリリースしました。 ストアの更新版を入手したら、次の操作を行います。

1. ストアを開いて、読み込まれていることを確認します。
1. ブルームジェスチャを使用してメニューを開きます。
1. 以前に壊れたアプリを開こうとしています。
1. それでも起動できない場合は、破損したアプリのアイコンをタップして押し続け、[アンインストール] を選びます。
1. Resinstall からこれらのアプリをインストールします。

デバイスで依然としてアプリを読み込むことができない場合は、次の手順に従って、ダウンロードセンターから .NET ネイティブフレームワークとランタイムのバージョンをサイドローディングできます。

1. Microsoft ダウンロードセンターから[この zip ファイル](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip)をダウンロードしてください。 解凍すると、2つのファイルが生成されます。  NET.TCP、.appx、および NET.EXE というように、.appx というようにします。
1. デバイスが dev のロック解除されていることを確認してください。  この手順を完了していない場合は、[こちら](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)を参照してください。
1. 次に、Windows Device Portal にアクセスします。 この操作は USB 経由で行うことをお勧めします。そのためには、 http://127.0.0.1:10080 ブラウザーに入力します。
1. Windows Device Portal を起動したら、ダウンロードした2つのファイルを "サイドロード" する必要があります。 そのためには、左側のバーに移動して [**アプリ**] セクションに移動し、[**アプリ**] を選択する必要があります。
1. 次のような画面が表示されます。  [**アプリのインストール**] というセクションに移動して、2つの APPX ファイルを解凍した場所を参照します。 一度に1つしか実行できないため、最初の1つを選んでから、[展開] セクションの [移動] をクリックします。 次に、2つ目の APPX ファイルに対してこれを行います。

   ![サイドロードアプリをインストールするための Windows Device Portal](images/20190322-DevicePortal.png)
1. この時点で、アプリケーションは再び動作を開始する必要があり、ストアにアクセスすることもできます。
1. 場合によっては、影響を受けるアプリが起動する前に、3D ビューアーアプリを起動するための追加の手順を実行する必要があります。 

この問題を解決するための手続きを行っていますので、この問題を解決するためのご協力をお願いいたします。 skype では、共同作業を成功させるために、コミュニティを引き続き活用していきます。

### デバイスの更新

- 30秒後に新しい更新プログラムを実行すると、シェルが1回表示されなくなることがあります。 セッションを再開するには、**ブルーム**ジェスチャを実行してください。

### Visual Studio

- 「HoloLens の開発に推奨される最新バージョンの Visual Studio 用の[ツールをインストール](https://docs.microsoft.com/windows/mixed-reality/install-the-tools)する」を参照してください。
- Visual Studio から HoloLens にアプリを展開すると、次のエラーが表示されることがあります。要求された操作は、ユーザーによってマップされた**セクションが開いているファイルでは実行できません。(HRESULT: 0x800704C8 の例外)**。 この問題が発生した場合は、通常、展開は成功します。

### API

- ユーザーまたは通常のカメラに[フォーカスポイント](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity)を設定すると、ホログラムは Mixed Reality キャプチャ写真またはビデオに表示されません。 このバグが Windows で修正されるまでは、アプリケーションが[フォーカスポイント](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity)をアクティブに設定した場合、機体の法線が反対のカメラフォワード (たとえば、normal =-camera. forward) に設定されていることを確認する必要があります。

### Xbox ワイヤレスコントローラー

- Xbox ワイヤレスコントローラー S は、HoloLens で使用する前に更新する必要があります。 HoloLens とコントローラーをペアリングしようとする前に、[最新](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter)の状態であることを確認します。
- Xbox ワイヤレスコントローラーが接続されているときに HoloLens を再起動すると、コントローラーが HoloLens に自動的に再接続されることはありません。 [ガイド] ボタンのライトは、3分後にコントローラーの電源が切れるまでゆっくり点滅します。 コントローラーをすぐに再接続するには、ライトがオフになるまでガイドボタンを押してコントローラーの電源を切ります。 コントローラーの電源を入れ直すと、HoloLens に再接続されます。
- Xbox ワイヤレスコントローラーが接続されているときに HoloLens がスタンバイ状態になると、コントローラーでの入力によって HoloLens が復帰します。 この機能を使用したら、コントローラーの電源を切ることで、これを防ぐことができます。

## HoloLens エミュレーターの既知の問題

- Microsoft Store のすべてのアプリがエミュレーターと互換性があるとは限りません。 たとえば、ヤングと断片はエミュレーターでは再生できません。
- エミュレーターで PC web カメラを使用することはできません。
- Windows Device Portal のリアルタイムのプレビュー機能は、エミュレーターでは動作しません。 ただし、Mixed Reality のビデオとイメージをキャプチャすることもできます。