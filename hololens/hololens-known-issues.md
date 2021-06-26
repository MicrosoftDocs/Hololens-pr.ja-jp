---
title: HoloLens の既知の問題 (第1世代)
description: Unity と Windows デバイスポータルを使用する HoloLens のお客様と開発者に影響を与える可能性のある既知の問題と回避策の一覧については、最新情報をご確認ください。
keywords: トラブルシューティング、既知の問題、ヘルプ
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
ms.openlocfilehash: 558eba8c2260b24a228e957b27927d508a077ec4
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923552"
---
# <a name="known-issues-for-hololens-1st-gen"></a>HoloLens の既知の問題 (第1世代)

HoloLens デバイスの既知の問題の現在の一覧を次に示します。 奇妙な動作が見られる場合は、まずこのチェックボックスをオンにします。 この一覧は、新しい問題が検出または報告されたとき、または将来の HoloLens ソフトウェア更新プログラムで問題が解決されると、更新されたままになります。

>[!NOTE]
> - ブロックされていない問題が検出された場合は、 [フィードバックハブ](hololens-feedback.md)を使用して HoloLens デバイスで報告してください。
> - 問題が発生している場合は、フィードバックを提出するだけでなく、 [サポート要求](https://aka.ms/hlsupport)を提出してください。


- [すべての HoloLens の世代に関する既知の問題](#known-issues-for-all-hololens-generations)
- [HoloLens の既知の問題 (第1世代)](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>すべての HoloLens の世代に関する既知の問題

### <a name="unity"></a>Unity

- 「HoloLens の開発に推奨される最新バージョンの Unity 用の [ツールをインストール](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) する」を参照してください。
- Unity HoloLens Technical Preview の既知の問題については、 [Hololens Unity フォーラム](https://forum.unity3d.com/threads/known-issues.394627/)に記載されています。

### <a name="windows-device-portal"></a>Windows デバイス ポータル

- Mixed Reality キャプチャのライブプレビュー機能は、数秒の待機時間が発生する場合があります。

- [仮想入力] ページで、[仮想ジェスチャ] セクションのジェスチャとスクロールコントロールが機能していません。 使用すると、効果はありません。 仮想入力ページの仮想キーボードが正常に動作します。

- [設定] で開発者モードを有効にした後、デバイスポータルをオンにするスイッチが有効になるまで数秒かかることがあります。

### <a name="onedrive-camera-upload"></a>OneDrive カメラのアップロード

HoloLens 用の OneDrive アプリでは、職場または学校アカウントのカメラの自動アップロードはサポートされていません。

回避策:

- お客様のビジネスで利用可能な場合、カメラの自動アップロードはコンシューマーの Microsoft アカウントでサポートされています。 職場または学校のアカウントに加えて、Microsoft アカウントにサインインできます (OneDrive アプリではデュアルサインインがサポートされています)。 OneDrive 内の Microsoft アカウントプロファイルから、自動、バックグラウンドカメラロールのアップロードを有効にすることができます。

- 写真を自動的にアップロードするためにコンシューマー Microsoft アカウントを安全に使用できない場合は、OneDrive アプリから職場または学校のアカウントに写真を手動でアップロードすることができます。 これを行うには、OneDrive アプリの職場または学校アカウントにサインインしていることを確認します。 ボタンを選択 **+** し、[ **アップロード**] を選択します。 [ **ピクチャ > カメラロール** に移動して、アップロードする写真またはビデオを検索します。 アップロードする写真またはビデオを選択し、[ **開く** ] ボタンを選択します。

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

1. [SirepClient.dll と SshClient.dll の両方を選択し、[ **追加**] を選択します。

1. ソリューションエクスプローラーで両方のファイルを見つけて選択し (ファイルの一覧の一番下にある必要があります)、[**プロパティ**] ウィンドウで [**出力ディレクトリにコピー** ] を [**常にコピー** する] に変更します。

1. ファイルの先頭に、ステートメントの既存のリストに次のを追加し `using` ます。

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. 内 `static void Main(...)` に、次のコードを追加します。

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

1. コマンドプロンプトウィンドウを開き、コンパイルされた .exe ファイルが含まれているフォルダー (C:\MyProjects\HoloLensDeploymentFix\bin\Debug など) に cd を開きます。

1. 実行可能ファイルを実行し、デバイスの IP アドレスをコマンドライン引数として指定します。 (USB を使用して接続されている場合は、127.0.0.1 を使用できます。それ以外の場合は、デバイスの Wi-Fi IP アドレスを使用します)。 たとえば、"HoloLensDeploymentFix 127.0.0.1" のようになります。

1. ツールがメッセージなしで終了した後 (これには数秒しかかかりません)、Visual Studio 2017 以降からデプロイおよびデバッグできるようになります。  ツールを引き続き使用する必要はありません。

利用可能になると、さらに更新プログラムを提供します。

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>HoloLens での Microsoft Store とアプリの起動に関する問題

> [!NOTE]
> 最終更新日時: 4/2 @ 10 AM-問題が解決されました。

HoloLens で Microsoft Store とアプリを起動しようとすると、問題が発生することがあります。 この問題が発生するのは、バックグラウンドアプリの更新プログラムによって、特定のシーケンスで新しいバージョンのフレームワークパッケージが配置されているにもかかわらず、1つまたは複数の依存アプリがまだ実行中である場合です。 この場合、アプリの自動更新によって新しいバージョンの .NET Native Framework (バージョン10.0.25531 から 10.0.27413) が提供されたため、以前のバージョンのフレームワークを使用している実行中のすべてのアプリに対して、実行中のアプリが正しく更新されませんでした。  Framework 更新のフローは次のとおりです。

1. 新しいフレームワークパッケージがストアからダウンロードされ、インストールされます。

1. 古いフレームワークを使用しているすべてのアプリは、新しいバージョンを使用するように "更新" されます。

ステップ2が完了前に中断された場合、新しいフレームワークが登録されていないアプリは、[スタート] メニューから起動できません。  HoloLens のアプリは、この問題の影響を受ける可能性があります。

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

1. [この zip ファイル](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip)は、Microsoft ダウンロードセンターからダウンロードしてください。 解凍すると2つのファイルが生成されます。  [.NET.............................. .net............

1. デバイスのロックが解除されていることを確認してください。  これをまだ行っていない場合は、「 [Windows デバイスポータルを使用](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) した手順」を参照してください。

1. 次に、Windows デバイスポータルにアクセスします。 USB 経由でこれを行うことをお勧めします。これを行うには、ブラウザーに「」と入力し http://127.0.0.1:10080 ます。

1. Windows デバイスポータルを作成した後、ダウンロードした2つのファイルの "サイドロード" を行う必要があります。 これを行うには、[ **アプリ** ] セクションに移動して [ **アプリ**] を選択するまで、左側のバーを下に表示する必要があります。

1. 次のような画面が表示されます。  「 **Install App** 」というセクションに移動し、これら2つの APPX ファイルを解凍した場所を参照します。 一度に1つだけ実行できます。そのため、最初の1つを選択した後、[デプロイ] セクションで [実行] をクリックします。 次に、2番目の APPX ファイルに対してこれを実行します。

   ![Side-Loaded アプリをインストールするための Windows デバイスポータル](images/20190322-DevicePortal.png)

1. この時点で、アプリケーションが再び動作を開始し、ストアにもアクセスできると思われます。

1. 場合によっては、影響を受けるアプリが起動する前に3D ビューアーアプリを起動する追加手順を実行する必要があります。

この問題を解決するためのプロセスが完了したので、しばらくお待ちください。マイクロソフトのコミュニティと連携して、成功した Mixed Reality エクスペリエンスを作成してください。

### <a name="device-update"></a>デバイスの更新

- 30秒新しい更新の後、シェルが1回消えることがあります。 **ブルーム** ジェスチャを実行してセッションを再開してください。

### <a name="visual-studio"></a>Visual Studio

- HoloLens 開発に推奨されている最新バージョンの Visual Studio 用の [ツールをインストール](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) する方法を参照してください。

- アプリを Visual Studio から HoloLens にデプロイすると、次のエラーが表示されることがあります。 **ユーザーマップセクションが開いているファイルに対して、要求された操作を実行することはできません。(HRESULT からの例外: 0x800704C8)**。 この問題が発生した場合は、もう一度やり直してください。通常、配置は成功します。

### <a name="api"></a>API

- アプリケーションがユーザーの背後にある [フォーカスポイント](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) を設定した場合、または通常はカメラから移動した場合、ホログラムは混合の現実キャプチャの写真またはビデオには表示されません。 Windows でこのバグが修正されるまで、アプリケーションが [フォーカスポイント](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) をアクティブに設定している場合は、平面法線が反対のカメラフォワード (たとえば、normal =-camera. forward) に設定されていることを確認する必要があります。

### <a name="xbox-wireless-controller"></a>Xbox ワイヤレス コントローラー

- Xbox ワイヤレスコントローラーは、HoloLens で使用する前に更新する必要があります。 コントローラーを HoloLens とペアリングする前に、最新の状態 [に](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) なっていることを確認してください。

- Xbox ワイヤレスコントローラーが接続されている間に HoloLens を再起動すると、コントローラーは HoloLens に自動的に再接続されません。 番組ガイドボタンのライトは、コントローラーが3分後に電源オフになるまで、ゆっくりと点滅します。 コントローラーをすぐに再接続するには、[ガイド] ボタンを押して、ライトがオフになるまでコントローラーの電源をオフにします。 コントローラーの電源を再度オンにすると、HoloLens に再接続されます。

- Xbox ワイヤレスコントローラーが接続されている間に HoloLens がスタンバイ状態になると、コントローラー上の入力があれば HoloLens がウェイクアップされます。 コントローラーの使用が完了したら、コントローラーの電源をオフにすることで回避できます。

