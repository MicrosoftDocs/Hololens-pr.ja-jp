---
title: HoloLens (第 1 世代) の既知の問題
description: Unity と HoloLens Windows デバイス ポータル を使用しているお客様や開発者に影響する可能性がある既知の問題と回避策の一覧をWindows デバイス ポータル。
keywords: トラブルシューティング, 既知の問題, ヘルプ
author: mattzmsft
ms.author: mazeller
ms.date: 6/15/2021
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
ms.openlocfilehash: 5c942bae91c7684f2c2d36aca6ace6306b5fed54
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189292"
---
# <a name="known-issues-for-hololens-1st-gen"></a>HoloLens (第 1 世代) の既知の問題

現在のデバイスの既知の問題の一覧をHoloLensします。 まず、奇数の動作が表示される場合は、こちらを確認してください。 この一覧は、新しい問題が検出または報告された時点で、または将来のソフトウェア更新プログラムで対処HoloLensされます。

>[!NOTE]
> - ブロックされていない問題が検出された場合は、 を介してデバイスHoloLens報告[フィードバック Hub。](hololens-feedback.md)
> - 問題が発生している場合は、フィードバックの提出に加えて、サポート リクエスト [を提出してください](https://aka.ms/hlsupport)。


- [すべての世代の既知のHoloLens問題](#known-issues-for-all-hololens-generations)
- [HoloLens (第 1 世代) の既知の問題](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>すべての世代の既知のHoloLens問題

### <a name="unity"></a>Unity

- 新[しい開発に推奨される](/windows/mixed-reality/install-the-tools)Unity の最新バージョンについては、ツールのインストールに関するHoloLensしてください。
- Unity HoloLens Technical Preview に関する既知の問題については、Unity フォーラムのHoloLens[を参照してください](https://forum.unity3d.com/threads/known-issues.394627/)。

### <a name="windows-device-portal"></a>Windows デバイス ポータル

- キャプチャの Live Preview 機能Mixed Reality数秒の待機時間が発生する可能性があります。

- [仮想入力] ページの [仮想ジェスチャ] セクションの [ジェスチャ] コントロールと [スクロール] コントロールは機能しません。 それらを使用した場合、効果はありません。 仮想入力ページの仮想キーボードは正しく動作します。

- 設定 で開発者モードを有効にした後、スイッチが有効になっているまで数秒デバイス ポータル場合があります。

### <a name="onedrive-camera-upload"></a>OneDriveカメラのアップロード

OneDriveアプリでは、HoloLensまたは学校アカウントの自動カメラ アップロードはサポートされていません。

回避策:

- ビジネスで実行可能な場合は、コンシューマー向け Microsoft アカウントでカメラの自動アップロードがサポートされます。 自分のアカウントまたは学校アカウントMicrosoft アカウント、自分のアカウントにサインインできます (OneDrive アプリはデュアル サインインをサポートしています)。 アプリ内のMicrosoft アカウントプロファイルOneDrive、バックグラウンド カメラの自動ロール アップロードを有効にできます。

- 写真を自動的にアップロードするためにコンシューマー Microsoft アカウント を安全に使用できない場合は、OneDrive アプリから仕事用または学校アカウントに写真を手動でアップロードできます。 これを行うには、アプリで、自分の学校アカウントにサインインOneDriveしてください。 ボタンを選択 **+** し、 []**をアップロード。** [カメラ ロール] の [ピクチャ] に移動して、アップロード **する>を見つける。** アップロードする写真またはビデオを選択し、[開く] ボタン **を選択** します。

## <a name="known-issues-for-hololens-1st-gen"></a>HoloLens (第 1 世代) の既知の問題

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>接続を使用して接続し、HoloLensデプロイVisual Studio

> [!NOTE]
> 最終更新日: 8/8 @ 5:11PM - Visual Studio では、この問題の修正が含まれる VS 2019 バージョン 16.2 がリリースされました。 このエラーが発生しないように、この最新バージョンに更新することをお勧めします。

Visual Studio VS 2019 バージョン 16.2 がリリースされました。これには、この問題の修正プログラムが含まれています。 このエラーが発生しないように、この最新バージョンに更新することをお勧めします。

問題の根本原因: Visual Studio 2015 または Visual Studio 2017 の初期リリースを使用して HoloLens にアプリケーションをデプロイおよびデバッグし、その後、同じ HoloLens で Visual Studio 2017 または Visual Studio 2019 の最新バージョンを使用したユーザーが影響を受ける可能性があります。 新しいリリースの Visual Studioコンポーネントの新しいバージョンがデプロイされますが、古いバージョンのファイルはデバイスに残され、新しいバージョンは失敗します。  これにより、次のエラー メッセージが表示されます: DEP0100: ターゲット デバイスで開発者モードが有効になっている必要があります。 エラーが発生し、開発者ライセンスを取得 \<ip\> 80004005。

#### <a name="workaround"></a>回避策

現在、チームは修正に取り組み中です。 その間は、次の手順を使用して問題を回避し、デプロイとデバッグのブロックを解除できます。  

1. Visual Studio を開きます。

1. **[File]**  >  **[New]**  >  **[Project]** の順に選択します。

1. [Visual **C#**  >  **Windows デスクトップ** コンソール アプリ  >  **(.NET Framework) を選択します**。

1. プロジェクトに名前 ("HoloLensDeploymentFix" など) を付け、Framework が少なくとも .NET Framework 4.5 に設定されている場合は **、[OK]** を選択します。

1. [参照]**ノードを** 右クリックしソリューション エクスプローラー参照を追加します ([参照] セクションを選択し、[参照] を **選択します**)。

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > 10.0.18362.0 がインストールされていない場合は、最新バージョンを使用します。

1. プロジェクトを右クリックし、 [既存の項目ソリューション エクスプローラー **を**  >  **選択します**。

1. C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 に移動し、フィルターを [すべてのファイル **] ( \* \* )** に変更します。

1. [追加] と [SirepClient.dllの両方SshClient.dll選択し、[ 追加] を **選択します**。

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

1. コマンド プロンプト ウィンドウを開き、コンパイルされた .exe ファイルを含むフォルダーに cd を指定します (例: C:\MyProjects\HoloLensDeploymentFix\bin\Debug)。

1. 実行可能ファイルを実行し、デバイスの IP アドレスをコマンド ライン引数として指定します。 (USB を使用して接続されている場合は、127.0.0.1 を使用できます。それ以外の場合は、デバイスの IP アドレスWi-Fi使用できます)。 たとえば、"HoloLensDeploymentFix 127.0.0.1" などです。

1. ツールがメッセージなしで終了した後 (これには数秒しかかからず)、Visual Studio 2017 以降からデプロイおよびデバッグできます。  ツールを継続的に使用する必要はありません。

利用可能になったら、さらに更新プログラムを提供します。

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>アプリとアプリのMicrosoft Storeの起動に関するHoloLens

> [!NOTE]
> 最終更新日: 4/2 @ 10 AM - 問題が解決されました。

アプリとアプリをアプリで起動しようとするときにMicrosoft Storeが発生するHoloLens。 バックグラウンド アプリの更新プログラムが特定のシーケンスで新しいバージョンのフレームワーク パッケージをデプロイするときに、1 つ以上の依存アプリがまだ実行されている間に問題が発生すると判断しました。 この場合、アプリの自動更新により、新しいバージョンの .NET ネイティブ Framework (バージョン 10.0.25531 から 10.0.27413) が提供され、実行されているアプリは、以前のバージョンのフレームワークを使用している実行中のすべてのアプリに対して正しく更新されませんでした。  フレームワークの更新のフローは次のとおりです。

1. 新しいフレームワーク パッケージがストアからダウンロードされ、インストールされます。

1. 古いフレームワークを使用しているすべてのアプリは、新しいバージョンを使用するように "更新" されます。

手順 2 が完了する前に中断された場合、新しいフレームワークが登録されていないアプリは、スタート メニューから起動されません。  この問題の影響を受ける可能性HoloLensアプリがインストールされている可能性があります。

一部のユーザーは、ハングしたアプリを閉じ、フィードバック Hub、3D ビューアー、フォトなどの他のアプリを起動すると問題が解決すると報告されています。ただし、これは 100% の時間では機能しません。

この問題が原因で更新自体が発生したのではなく、os のバグが原因で .NET ネイティブ フレームワークの更新プログラムが正しく処理されないという根本原因がありました。 修正プログラムが特定され、修正プログラムを含む更新プログラム (OS バージョン 17763.380) がリリースされました。  

デバイスが更新プログラムを受け取る可能性を確認するには:

1. アプリに移動し設定 Update **& Security を開きます**。

1. [更新 **プログラムの確認] を選択します**。

1. 17763.380 への更新プログラムが利用可能な場合は、このビルドに更新して、アプリハングバグの修正プログラムを受け取る必要があります。

1. このバージョンの OS に更新すると、アプリは期待した通り動作する必要があります。

さらに、すべての OS リリースで行HoloLens、FFU イメージを Microsoft ダウンロード センター に[投稿しました](https://aka.ms/hololensdownload/10.0.17763.380)。

更新プログラムを利用しない場合は、3/29 のMicrosoft Store UWP アプリの新しいバージョンがリリースされました。 更新されたバージョンのストアを作成した後:

1. ストアを開き、それが読み込まれるか確認します。
1. 花のジェスチャを使用してメニューを開きます。
1. 以前に壊れたアプリを開くことを試みる。
1. 起動できない場合は、壊れたアプリのアイコンを長押しし、[アンインストール] を選択します。
1. ストアからこれらのアプリを再インストールします。

デバイスで引き続きアプリを読み込めできない場合は、次の手順に従って、ダウンロード センターから .NET ネイティブ Framework とランタイムのバージョンをサイドロードできます。

1. この zip [ファイルは、Microsoft](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) ダウンロード センターからダウンロードしてください。 解凍すると、2 つのファイルが生成されます。  Microsoft .NET.Native.Runtime.1.7.appx と Microsoft .NET.Native.Framework.1.7.appx。

1. デバイスのロックが解除されていないことを確認してください。  この操作をまだ行っていない場合は、手順に関するページ[の「Windows デバイス ポータル」](/windows/mixed-reality/using-the-windows-device-portal)を参照してください。

1. 次に、次のWindows デバイス ポータル。 USB を使用してこれを行い、ブラウザーに「」と入力して http://127.0.0.1:10080 行います。

1. 新しいファイルをWindows デバイス ポータル、ダウンロードした 2 つのファイルを "サイド ロード" する必要があります。 これを行うには、[アプリ] セクションに移動して [アプリ] を選択するまで、左側のバーを下に移動する **必要があります**。

1. 次のような画面が表示されます。  [アプリのインストール] というセクションに移動し、これらの 2 つの APPX ファイルを展開した場所を参照します。 一度に実行できるのは 1 つのみなので、最初の操作を選択した後、[デプロイ] セクションの [移動] をクリックします。 次に、2 番目の APPX ファイルに対してこれを行います。

   ![Windowsデバイス ポータルアプリをインストールSide-Loadedします。](images/20190322-DevicePortal.png)

1. この時点で、アプリケーションはもう一度動作し始め、ストアにアクセスできると思います。

1. 場合によっては、影響を受けるアプリが起動する前に、3D ビューアーアプリを起動する追加の手順を実行する必要があります。

この問題を解決するためのプロセスを完了し、コミュニティと協力して成功したエクスペリエンスを作成し続けMixed Realityしています。

### <a name="device-update"></a>デバイスの更新

- 新しい更新から 30 秒後に、シェルが 1 回消える可能性があります。 セッションを再開 **するには、花の** ジェスチャを実行してください。

### <a name="visual-studio"></a>Visual Studio

- 新[しい開発に推奨](/windows/mixed-reality/install-the-tools)される最新バージョンの Visual Studioについては、ツールのインストールに関するHoloLensしてください。

- Visual Studio から HoloLens にアプリをデプロイすると、次のエラーが表示される場合があります。要求された操作は、ユーザーマップセクションが開いているファイルに対して実行できません **。(HRESULT からの例外: 0x800704C8)**。 この場合は、もう一度やり直してください。通常はデプロイが成功します。

### <a name="api"></a>API

- アプリケーションがユーザーの背後にある [フォーカス](/windows/mixed-reality/focus-point-in-unity) ポイントを設定した場合、または通常のを camera.forward に設定した場合、ホログラムは写真やビデオMixed Reality キャプチャに表示されません。 Windows でこのバグが修正されるまで、アプリケーションがフォーカス ポイントをアクティブに[](/windows/mixed-reality/focus-point-in-unity)設定する場合は、平面の法線がカメラ前方に向かい合って設定されている必要があります (例: normal = -camera.forward)。

### <a name="xbox-wireless-controller"></a>Xbox ワイヤレス コントローラー

- Xbox ワイヤレス コントローラー S は、デバイスで使用する前に更新するHoloLens。 コントローラーとデバイス[をペアリング](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter)する前に、最新のHoloLens。

- Xbox ワイヤレス コントローラーのHoloLens中にデバイスを再起動した場合、コントローラーは自動的に接続HoloLens。 [ガイド] ボタンライトは、コントローラーの電源が切れるまで 3 分後に点滅します。 コントローラーを直ちに再接続するには、ライトがオフになるまで [ガイド] ボタンを押してコントローラーの電源をオフにします。 コントローラーの電源を再びオンにした場合は、コントローラーの電源HoloLens。

- Xbox ワイヤレス HoloLens接続中にデバイスがスタンバイ状態に切り替える場合、コントローラー上の入力によってデバイスが起動HoloLens。 これを防ぐには、コントローラーの使用が完了したら電源をオフにします。

