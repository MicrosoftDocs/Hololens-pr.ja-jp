---
title: HoloLens の既知の問題
description: Unity と Windows デバイスポータルを使用する HoloLens のお客様と開発者に影響を与える可能性のある既知の問題と回避策の一覧については、最新情報をご確認ください。
keywords: トラブルシューティング、既知の問題、ヘルプ
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
ms.openlocfilehash: bc1d399a07a6a0622c953178cad7be1b8a018fdb
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397783"
---
# <a name="known-issues-for-hololens"></a>HoloLens の既知の問題

HoloLens デバイスの既知の問題の現在の一覧を次に示します。 奇妙な動作が見られる場合は、まずこのチェックボックスをオンにします。 この一覧は、新しい問題が検出または報告されたとき、または将来の HoloLens ソフトウェア更新プログラムで問題が解決されると、更新されたままになります。

>[!NOTE]
> - ブロックされていない問題が検出された場合は、 [フィードバックハブ](hololens-feedback.md)を使用して HoloLens デバイスで報告してください。
> - 問題が発生している場合は、フィードバックを提出するだけでなく、 [サポート要求](https://aka.ms/hlsupport)を提出してください。

- [すべての HoloLens の世代に関する既知の問題](#known-issues-for-all-hololens-generations)
- [HoloLens 2 デバイスに関する既知の問題](#known-issues-for-hololens-2-devices)
- [HoloLens の既知の問題 (第1世代)](#known-issues-for-hololens-1st-gen)
- [HoloLens エミュレーターの既知の問題](#known-issues-for-hololens-emulator)

## <a name="known-issues-for-all-hololens-generations"></a>すべての HoloLens の世代に関する既知の問題

### <a name="unity"></a>Unity

- 「HoloLens の開発に推奨される最新バージョンの Unity 用の [ツールをインストール](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) する」を参照してください。
- Unity HoloLens Technical Preview の既知の問題については、 [Hololens Unity フォーラム](https://forum.unity3d.com/threads/known-issues.394627/)に記載されています。

### <a name="windows-device-portal"></a>Windows デバイス ポータル

- Mixed Reality キャプチャのライブプレビュー機能は、数秒の待機時間が発生する場合があります。

- [仮想入力] ページで、[仮想ジェスチャ] セクションのジェスチャとスクロールコントロールが機能していません。 使用すると、効果はありません。 仮想入力ページの仮想キーボードが正常に動作します。

- [設定] で開発者モードを有効にした後、スイッチが有効になっているまで数秒デバイス ポータル場合があります。

### <a name="onedrive-camera-upload"></a>OneDrive カメラのアップロード

HoloLens 用の OneDrive アプリでは、仕事用または学校アカウントの自動カメラ アップロードはサポートされていません。

回避策:

- ビジネスで実行可能な場合は、コンシューマー向け Microsoft アカウントでカメラの自動アップロードがサポートされます。 自分のアカウントまたは学校アカウントMicrosoft アカウント、自分のアカウントにサインインできます (OneDrive アプリではデュアル サインインがサポートされています)。 OneDrive 内Microsoft アカウントプロファイルから、自動のバックグラウンド カメラ ロール アップロードを有効にできます。

- 写真を自動的にアップロードするためにコンシューマー Microsoft アカウント を安全に使用できない場合は、OneDrive アプリから手動で写真を仕事または学校アカウントにアップロードできます。 これを行うには、OneDrive アプリで、自分の仕事用または学校アカウントにサインインしている必要があります。 ボタンを選択 **+** し、 [アップロード] を **選択します**。 [カメラ ロール] の [ピクチャ] に移動して、アップロード **する>を見つける。** アップロードする写真またはビデオを選択し、[開く] ボタン **を選択** します。

## <a name="known-issues-for-hololens-2-devices"></a>デバイスに関する既知HoloLens 2問題

### <a name="device-using-auto-login-asks-for-log-in"></a>自動ログインを使用するデバイスがログインを求める

デバイスHoloLens 2設定アカウントサインイン オプション -> を使用して自動的にログインするように構成できます。[必須] で値を [Never] に  ->    ->  設定 **します**。  一部のユーザーは、機能更新プログラムなど、大幅に大きな更新プログラムを使用してデバイスを更新するときに、デバイスに再度ログインする必要があります。

これが発生する可能性がある例を次に示します。

- Windows Holographic バージョン 2004 (ビルド 19041.xxxx) から Windows Holographic バージョン 21H1 (ビルド 20346.xxxx) へのデバイスの更新
- 同じメジャー ビルド (Windows Holographic バージョン 2004 から Windows Holographic バージョン 20H2 など) で大規模な更新を行うデバイスの更新
- ファクトリ イメージから最新のイメージへのデバイスの更新

これは、次の場合には発生しません。

- 月単位のサービス更新を行っているデバイス

メソッドに対処する:

- PIN、パスワード、虹彩、Web 認証、FIDO2 キーなどのサインイン方法。
- デバイスの PIN を記憶できず、他の認証方法を使用できない場合、ユーザーは [手動の reflashing モード](hololens-recovery.md#manual-procedure)を使用できます。

### <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge を起動できない

> [!NOTE]
> この問題は、もともと Microsoft Edge の出荷バージョンで作成されています。 この問題は、 [新しい Microsoft Edge](hololens-new-edge.md)で解決される場合があります。 そうでない場合は、フィードバックをお送りください。

いくつかのお客様が、Microsoft Edge の起動に失敗したという問題を報告しています。 このようなお客様の場合、問題は再起動によって引き続き発生し、Windows またはアプリケーションの更新プログラムでは解決されません。 この問題が発生していて、 [Windows が](hololens-updates.md#manually-check-for-updates)最新の状態であることを確認した場合は、 [フィードバックハブアプリ](hololens-feedback.md) から次のカテゴリとサブカテゴリを使用してバグを報告してください。インストールと更新 > Windows Update のダウンロード、インストール、および構成を行います。

これまでに根本原因を根本的に解決できないため、既知の回避策はありません。 フィードバックハブを使用してバグを提出すると、調査に役立ちます。

### <a name="keyboard-does-not-switch-to-special-characters"></a>キーボードは特殊文字に切り替わりません。

OOBE 中に、ユーザーが職場または学校のアカウントを選択してパスワードを入力した後に、[&123] ボタンをタップしてキーボードの特殊文字に切り替えようとしたときに、特殊文字に変更されないという問題があります。

回避策:
-   キーボードを閉じて、[テキスト] フィールドをタップして再度開きます。
-   パスワードが正しく入力できません。 キーボードが次に再起動されると、正常に動作します。
- Web 認証。キーボードを閉じ、[ **別のデバイスからサインイン** する] を選択します。
-   数値のみを入力する場合、ユーザーは特定のキーを長押しして展開されたメニューを開くことができます。
-   USB キーボードを使用する。

これは、次の場合には影響を与え "ない" です。
- 個人アカウントの使用を選択したユーザー。

### <a name="blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-an-insider-build"></a>Insider ビルドで再フラッシュされたデバイスで Insider プレビュー ビルドから登録を解除すると、ブルー スクリーンが表示されます

これは、Insider プレビュー ビルドに含まれるユーザーに影響を与え、新しい Insider プレビュー ビルドで HoloLens 2 を再フラッシュした後、Insider プログラムから登録を解除したユーザーに影響する問題です。

これは、次の場合には影響を与え "ない" です。
- アカウントに登録されていないWindows Insider 
- インサイダー：
    - Insider ビルドがバージョン 18362.x 以降にデバイスが登録されている場合
    - Insider 署名済み 19041.x ビルドをフラッシュし、Insider プログラムに登録された

回避: 
- 問題を回避する 
    - インサイダー以外のビルドをフラッシュします。 定期的な毎月の更新プログラムの 1 つ。
    - Insider Preview を利用する
- デバイスを再フラッシュする

    1. 接続していない [HoloLens 2電源](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) を完全にオフにすることで、デバイスを手動でフラッシュ モードにします。 次に、ボリュームを上に保持している間に、[電源] ボタンをタップします。
    
    1. PC に接続し、Advanced Recovery Companion を開きます。
    
    1. HoloLens 2 を既定のビルドにフラッシュします。

## <a name="known-issues-for-hololens-1st-gen"></a>HoloLens の既知の問題 (第1世代)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Visual Studio を使用して HoloLens に接続して展開できない

> [!NOTE]
> 最終更新: 8/8 @ 5: 午後11時-Visual Studio は、この問題の修正を含む VS 2019 バージョン16.2 をリリースしました。 このエラーが発生しないように、この最新バージョンに更新することをお勧めします。

Visual Studio では、VS 2019 バージョン16.2 がリリースされました。これには、この問題の修正が含まれています。 このエラーが発生しないように、この最新バージョンに更新することをお勧めします。

問題の根本原因: visual studio 2015 または Visual Studio 2017 の初期リリースを使用して、HoloLens でアプリケーションをデプロイおよびデバッグした後、同じ HoloLens で最新バージョンの Visual Studio 2017 または Visual Studio 2019 を使用したユーザーが影響を受けます。 新しいリリースの Visual Studio では、新しいバージョンのコンポーネントが配置されますが、古いバージョンのファイルはデバイス上に残されるため、新しいバージョンのエラーが発生します。  これにより、"DEP0100: ターゲットデバイスの開発者モードが有効になっていることを確認してください" というエラーメッセージが表示されます。 エラー80004005が発生したため、で開発者ライセンスを取得できませんでした \<ip\> 。

#### <a name="workaround"></a>回避策

現在、チームは修正を行っています。 それまでの間は、次の手順を使用して問題を回避し、デプロイとデバッグのブロックを解除できます。  

1. Visual Studio を開きます。

1. **[File]**  >  **[New]**  >  **[Project]** の順に選択します。

1. [ **Visual C#**  >  **Windows デスクトップ**  >  **コンソールアプリ (.NET Framework)**] を選択します。

1. プロジェクトに名前 ("HoloLensDeploymentFix" など) を付け、フレームワークが少なくとも .NET Framework 4.5 に設定されていることを確認してから、[ **OK]** を選択します。

1. ソリューションエクスプローラーの [ **参照** ] ノードを右クリックし、次の参照を追加します ([ **参照** ] セクションを選択し、[ **参照**] を選択します)。

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > 10.0.18362.0 がインストールされていない場合は、最新バージョンを使用します。 

1. ソリューションエクスプローラーでプロジェクトを右クリックし、[   >  **既存項目** の追加] を選択します。

1. C:\Program Files (x86) \Windows Kits\10\bin\10.0.18362.0\x86 を参照し、フィルターを **すべてのファイル ( \* . \* )** に変更します。

1. [追加] と [SirepClient.dllの両方SshClient.dll選択し、 [追加] を **選択します**。

1. ソリューション エクスプローラー 内の両方のファイルを見つけて選択し (ファイルの一覧の一番下にある必要があります)、[プロパティ] ウィンドウで [出力ディレクトリにコピー] を [常にコピー]**に変更します**。

1. ファイルの上部で、ステートメントの既存の一覧に次を `using` 追加します。

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. 内に `static void Main(...)` 、次のコードを追加します。

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. **[ビルド]**  >  **[ソリューションのビルド]** を順に選択します。

1. コマンド プロンプト ウィンドウを開き、コンパイル済みの .exe ファイルを含むフォルダーに cd を指定します (例: C:\MyProjects\HoloLensDeploymentFix\bin\Debug)。

1. 実行可能ファイルを実行し、デバイスの IP アドレスをコマンド ライン引数として指定します。 (USB を使用して接続されている場合は、127.0.0.1 を使用できます。それ以外の場合は、デバイスの IP アドレスWi-Fi使用できます)。 たとえば、"HoloLensDeploymentFix 127.0.0.1" などです。

1. ツールがメッセージなしで終了した後 (数秒しかかからず)、Visual Studio 2017 以降からデプロイおよびデバッグできます。  ツールを継続的に使用する必要はありません。

利用可能になったら、さらに更新プログラムを提供します。

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>HoloLens でのMicrosoft Storeアプリの起動に関する問題

> [!NOTE]
> 最終更新日: 4/2 @ 10 AM - 問題が解決されました。

HoloLens でアプリとアプリを起動しようとMicrosoft Storeが発生する場合があります。 バックグラウンド アプリの更新プログラムが特定のシーケンスで新しいバージョンのフレームワーク パッケージをデプロイするときに、1 つ以上の依存アプリがまだ実行されている間に問題が発生すると判断しました。 この場合、アプリの自動更新により、新しいバージョンの .NET Native Framework (バージョン 10.0.25531 から 10.0.27413) が提供され、実行中のアプリは、以前のバージョンのフレームワークを使用している実行中のすべてのアプリに対して正しく更新されませんでした。  フレームワークの更新のフローは次のとおりです。

1. 新しいフレームワーク パッケージがストアからダウンロードされ、インストールされます。

1. 古いフレームワークを使用しているすべてのアプリは、新しいバージョンを使用するように "更新" されます。

手順 2 が完了する前に中断された場合、新しいフレームワークが登録されていないアプリは、スタート メニューから起動されません。  HoloLens のアプリは、この問題の影響を受ける可能性があります。

一部のユーザーは、ハングしたアプリを終了し、フィードバックハブ、3D ビューアー、写真などの他のアプリを起動すると、問題が解決しますが、100% の時間は機能しません。

根本が発生したため、この問題は更新プログラム自体の原因ではなく、.NET Native framework の更新プログラムが正しく処理されなかった OS のバグが発生しました。 修正を特定し、修正を含む更新プログラム (OS バージョン 17763.380) をリリースしたことをお知らせします。  

デバイスで更新プログラムを取得できるかどうかを確認するには、次のようにします。

1. 設定アプリにアクセスし、[ **Update & Security**] を開きます。

1. [ **更新プログラムの確認**] を選択します。

1. 17763.380 への更新が利用可能な場合は、このビルドに更新して、アプリのハングバグの修正を受け取るようにしてください。

1. このバージョンの OS に更新すると、アプリは想定どおりに動作するはずです。

さらに、HoloLens OS のすべてのリリースで、 [Microsoft ダウンロードセンター](https://aka.ms/hololensdownload/10.0.17763.380)に ffu イメージを投稿しました。

更新を希望しない場合は、3/29 の時点で Microsoft Store UWP アプリの新しいバージョンをリリースしました。 更新されたバージョンのストアを作成したら、次のようにします。

1. ストアを開き、それが読み込まれることを確認します。
1. ブルームジェスチャを使用してメニューを開きます。
1. 以前に破損したアプリを開こうとしました。
1. それでも起動できない場合は、壊れているアプリのアイコンをタップしたままにして、[アンインストール] を選択します。
1. ストアからこれらのアプリを再インストールします。

デバイスがまだアプリを読み込むことができない場合は、次の手順に従って、ダウンロードセンターで .NET Native Framework および Runtime のバージョンをサイドロードできます。

1. [この zip ファイル](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip)は、Microsoft ダウンロードセンターからダウンロードしてください。 解凍すると2つのファイルが生成されます。  Microsoft .NET.Native.Runtime.1.7.appx と Microsoft .NET.Native.Framework.1.7.appx。

1. デバイスのロックが解除されていないことを確認してください。  この操作をまだ行っていない場合は、「方法の使用」を [参照Windows デバイス ポータル](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 手順を参照してください。

1. 次に、アプリケーションにアクセスWindows デバイス ポータル。 これを USB で行い、ブラウザーに「」と入力して行うのが http://127.0.0.1:10080 推奨されます。

1. 新しいファイルをWindows デバイス ポータル、ダウンロードした 2 つのファイルを "サイド ロード" する必要があります。 これを行うには、[アプリ] セクションに移動して [アプリ] を選択するまで、左側のバーを下に移動する **必要があります**。

1. 次のような画面が表示されます。  [アプリのインストール] というセクションに移動し、これらの 2 つの APPX ファイルを展開した場所を参照します。 一度に実行できるのは 1 つのみなので、最初の操作を選択した後、[デプロイ] セクションの [移動] をクリックします。 次に、2 番目の APPX ファイルに対してこれを行います。

   ![Windows デバイス ポータルアプリをインストールSide-Loadedする](images/20190322-DevicePortal.png)
   
1. この時点で、アプリケーションはもう一度動作し始める必要があります。また、ストアにアクセスできます。

1. 場合によっては、影響を受けるアプリが起動する前に、3D ビューアーアプリを起動する追加の手順を実行する必要があります。 

この問題を解決するためのプロセスを完了し、コミュニティと協力して成功したエクスペリエンスを作成し続けMixed Realityしています。

### <a name="device-update"></a>デバイスの更新

- 新しい更新から 30 秒後に、シェルが 1 回消える可能性があります。 セッションを再開 **するには、花の** ジェスチャを実行してください。

### <a name="visual-studio"></a>Visual Studio

- HoloLens [の開発](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) に推奨される最新バージョンのツールのインストールに関するページVisual Studioを参照してください。

- Visual Studio から HoloLens にアプリをデプロイすると、次のエラーが表示される場合があります。要求された操作は、ユーザーマップセクションが開いているファイルで **実行できません。(HRESULT からの例外: 0x800704C8)**。 この場合は、もう一度やり直してください。通常はデプロイが成功します。

### <a name="api"></a>API

- アプリケーションがユーザーの背後にある [フォーカスポイント](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) を設定した場合、または通常はカメラから移動した場合、ホログラムは混合の現実キャプチャの写真またはビデオには表示されません。 Windows でこのバグが修正されるまで、アプリケーションが [フォーカスポイント](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) をアクティブに設定している場合は、平面法線が反対のカメラフォワード (たとえば、normal =-camera. forward) に設定されていることを確認する必要があります。

### <a name="xbox-wireless-controller"></a>Xbox ワイヤレス コントローラー

- Xbox ワイヤレスコントローラーは、HoloLens で使用する前に更新する必要があります。 コントローラーを HoloLens とペアリングする前に、最新の状態 [に](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) なっていることを確認してください。

- Xbox ワイヤレスコントローラーが接続されている間に HoloLens を再起動すると、コントローラーは HoloLens に自動的に再接続されません。 番組ガイドボタンのライトは、コントローラーが3分後に電源オフになるまで、ゆっくりと点滅します。 コントローラーをすぐに再接続するには、[ガイド] ボタンを押して、ライトがオフになるまでコントローラーの電源をオフにします。 コントローラーの電源を再度オンにすると、HoloLens に再接続されます。

- Xbox ワイヤレスコントローラーが接続されている間に HoloLens がスタンバイ状態になると、コントローラー上の入力があれば HoloLens がウェイクアップされます。 コントローラーの使用が完了したら、コントローラーの電源をオフにすることで回避できます。

## <a name="known-issues-for-hololens-emulator"></a>HoloLens エミュレーターの既知の問題

- Microsoft Store の一部のアプリは、エミュレーターと互換性がありません。 たとえば、若い Conker とフラグメントは、エミュレーターでは再生できません。
- エミュレーターでは、PC の web カメラを使用できません。
- Windows デバイスポータルのライブプレビュー機能は、エミュレーターでは機能しません。 混合した現実のビデオとイメージをキャプチャすることもできます。
