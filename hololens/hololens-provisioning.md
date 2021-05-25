---
title: プロビジョニング パッケージを使用して HoloLens を構成する (HoloLens)
description: Windows プロビジョニングによって、IT 管理者はイメージングすることなく簡単にエンド ユーザー デバイスを設定できます。
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.custom:
- CI 115190
- CSSTroubleshooting
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: cf2abe249e40e522b4d8993449b9f19033a64744
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397403"
---
# <a name="configure-hololens-by-using-a-provisioning-package"></a>プロビジョニング パッケージを使用して HoloLens を構成する

[Windows プロビジョニングを使用](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) すると、IT 管理者はイメージングなしでエンドユーザー デバイスを簡単に構成できます。 Windows 構成デザイナーは、イメージとランタイム設定を構成するためのツールであり、その後、プロビジョニング パッケージに組み込まれます。

プロビジョニング パッケージで適用できる HoloLens 構成には、次のようなものがあります。

- アップグレードして [Windows Holographic for Business](hololens1-upgrade-enterprise.md)
- ローカル アカウントをセットアップする
- Wi-Fi 接続をセットアップする
- デバイスに証明書を適用する
- 開発者モードを有効にする
- 詳細な手順に従ってキオスク [モードを構成します](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)。

## <a name="provisioning-package-hololens-wizard"></a>プロビジョニング パッケージ HoloLens ウィザード

HoloLens ウィザードは、プロビジョニング パッケージで次の設定を構成するのに役立ちます。

- Enterprise Edition にアップグレードする

    > [!NOTE]
    > これは、HoloLens 第 1 世代デバイスにのみ使用する必要があります。 プロビジョニング パッケージの設定は、プロビジョニング パッケージに Windows Holographic for Business へのエディション アップグレード ライセンスが含まれる場合、またはデバイスが既に Windows Holographic for Business にアップグレードされている場合 [にのみ適用されます](hololens1-upgrade-enterprise.md)。

- HoloLens ファースト エクスペリエンス (OOBE) を構成する
- 仮想ネットワークWi-Fi構成する
- デバイスをローカル アカウントAzure Active Directory登録するか、ローカル アカウントを作成します
- 証明書の追加
- 開発者モードを有効にする
- の詳細な手順に従って [、キオスク モードを構成します](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)。

> [!WARNING]
> いずれかのウィザードを使って Azure Active Directory の登録を構成するには、Windows 10 で Windows 構成デザイナーを実行する必要があります。

プロビジョニング パッケージには、管理手順とポリシー、カスタム ネットワーク接続とポリシーなどがあります。

> [!TIP]
> デスクトップ ウィザードを使用して、共通設定を含むパッケージを作成し、詳細エディターに切り替えて、他の設定、アプリ、ポリシーなどを追加します。

## <a name="steps-for-creating-provisioning-packages"></a>プロビジョニング パッケージを作成する手順

1. **オプション 1:** [から Microsoft Store。](https://www.microsoft.com/store/apps/9nblggh4tx22) これには、HoloLens 2 の機能が含まれます。
2. **オプション 2:** windows [10 用 windows アセスメント & Amp; デプロイメントキット (ADK) から](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit)。 Windows ADK から Windows 構成デザイナーをインストールする場合は、[**インストールする機能を選択** してください] ダイアログボックスで [**構成デザイナー** ] を選択します。 このオプションには、HoloLens 2 の機能は含まれません。

> [!NOTE]
> Windows 構成デザイナーへのアクセスが必要なオフライン PC を使用することがわかっている場合は、「オフラインアプリ https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) のインストール (高度な回復コンパニオンの手順)」に従ってください。 Windows 構成デザイナーを選択してください。 

### <a name="2-create-the-provisioning-package"></a>2. プロビジョニングパッケージを作成する

Windows 構成デザイナー ツールを使用して、プロビジョニング パッケージを作成します。

1. Windows 構成デザイナーを開きます (既定では %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe)。

2. [ **HoloLens デバイスのプロビジョニング**] を選択します。

   ![ICD の起動オプション](images/icd-create-options-1703.png)

3. プロジェクトに名前を指定し、[ **完了**] を選択します。

4. [ **作業の開始** ] ページの指示を読み、[ **次へ**] を選択します。 デスクトッププロビジョニングのページでは、次の手順について説明します。
  
> [!IMPORTANT]
> プロビジョニング パッケージを作成する場合、プロジェクト ファイルとプロビジョニング パッケージ (.ppkg) ファイルに機密情報を含めることができます。 .ppkg ファイルは暗号化するかどうかを選べますが、プロジェクト ファイルは暗号化されません。 プロジェクト ファイルは、安全な場所に保存し、不要になったときに削除する必要があります。

### <a name="configure-settings"></a>設定の構成

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>HoloLens エディションをアップグレードするエンタープライズライセンスファイルを参照して選択します。</br></br>また、 <strong>[はい]</strong> または [ <strong>いいえ</strong> ] をオンにして、最初のエクスペリエンスの一部を非表示にすることもできます。</br></br>Wi-Fi ネットワークに接続せずにデバイスをセットアップするには、[ <strong>スキップ] Wi-Fi セットアップ</strong> を <strong>[オン</strong>] に切り替えます。</br></br>デバイスが使用されるリージョンとタイムゾーンを選択します。 </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>このセクションでは、デバイスが自動的に接続する Wi-Fi ワイヤレスネットワークの詳細を入力できます。 これを行うには、 <strong>[オン] を選択し</strong>、SSID、ネットワークの種類 (<strong>[開く</strong> ] または [ <strong>wpa2-個人用</strong>])、および ( <strong>WPA2-パーソナル</strong>の場合) ワイヤレスネットワークのパスワードを入力します。</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>デバイスを Azure Active Directory に登録するか、デバイスにローカルアカウントを作成することができます。</br></br>Windows 構成デザイナー ウィザードを使って Azure AD の登録を一括で構成する前に、<a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">組織での Azure AD 参加の設定</a>を行います。 Azure AD テナントの <strong>[ユーザーあたりのデバイスの最大数]</strong> の設定は、ウィザードで利用できる一括トークンを使用できる回数を決定します。 Azure AD にデバイスを登録するには、そのオプションを選択して、ウィザードを使って取得する一括トークンのフレンドリ名を入力します。 トークンの有効期限を設定します (最大、トークンの取得日から 30 日間)。 [ <strong>一括トークンの取得</strong>] を選択します。 [ <strong>&#39;にサインイン</strong> してください] ウィンドウで、Azure AD にデバイスを参加させるためのアクセス許可を持つアカウントを入力し、次にパスワードを入力します。 [同意 <strong>する] を</strong> 選択して、Windows 構成デザイナーに必要なアクセス許可を付与します。 </br></br>ローカル アカウントを作成するには、そのオプションを選択し、ユーザー名とパスワードを入力します。 </br></br><strong>大事な：</strong> <br />(Windows 10バージョン 1607 のみ)プロビジョニング パッケージでローカル アカウントを作成する場合は、42 日ごとに<strong></strong>設定アプリを使用してパスワードを変更する必要があります。 その期間内にパスワードを変更しない場合、アカウントがロックされてサインインできなくなる可能性があります。  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>証明書を使ってデバイスをプロビジョニングするには、<strong>[証明書の追加]</strong> をクリックします。 証明書の名前を入力し、使用する証明書を表示して選択します。</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>[ <strong>はい] または</strong> <strong>[いいえ]</strong> を切り替え、HoloLens で開発者モードを有効にします。 <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">開発者モードの詳細をご覧ください。</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>プロビジョニング パッケージを保護するためにパスワードを設定しない。 プロビジョニング パッケージがパスワードで保護されている場合、HoloLens デバイスのプロビジョニングは失敗します。</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

完了したら、 **[作成]** を選択します。 これは数秒で終わります。 パッケージがビルドされると、ページの下部に、パッケージの格納場所がハイパーリンクで表示されます。

### <a name="3-create-a-provisioning-package-for-hololens-by-using-advanced-provisioning"></a>3.高度なプロビジョニングを使用して HoloLens のプロビジョニング パッケージを作成する

> [!NOTE]
> 高度なプロビジョニングで作成するプロビジョニングパッケージには、HoloLens (第 1 世代) に完全に適用するために、Windows Holographic for Business へのエディション アップグレード ライセンスを含める必要があります。 [HoloLens Windows Holographic for Business (第 1](hololens1-upgrade-enterprise.md)世代) の詳細を参照してください。

1. Windows 構成デザイナースタート ページで、**[プロビジョニングの詳細設定]** を選択します。
2. **[プロジェクトの詳細の入力]** ウィンドウで、プロジェクトの名前とプロジェクトの場所を指定します。 必要に応じて、プロジェクトの簡単な説明を入力します。

3. **[次へ]** を選択します。

4. [表示 **および構成する設定を選択します]** ウィンドウで、[次へ] を **Windows 10 Holographic** 次へ] を **選択します**。

5. **[完了]** を選択します。

6. [ **ランタイム設定] を** 展開し、この記事で後述する設定を使用して [パッケージをカスタマイズします](#what-you-can-configure)。

    > [!IMPORTANT]
    > (Windows 10バージョン 1607 のみ)プロビジョニング パッケージでローカル アカウントを作成する場合は、42 日ごとに設定アプリを使用してパスワードを変更する必要があります。 その期間内にパスワードを変更しない場合、アカウントがロックされてサインインできなくなる可能性があります。 ユーザー アカウントがロックされた場合、[デバイスのフル回復](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)を実行する必要があります。

7. **[ファイル]**  >  **[保存]** を選びます。

8. プロジェクト ファイルに機密情報が含まれている可能性があるという警告を読み **、[OK] を選択します**。

    > [!IMPORTANT]
    > プロビジョニング パッケージを作成する場合、プロジェクト ファイルとプロビジョニング パッケージ (.ppkg) ファイルに機密情報を含めることができます。 .ppkg ファイルは暗号化するかどうかを選べますが、プロジェクト ファイルは暗号化されません。 プロジェクト ファイルは、安全な場所に保存し、不要になったときに削除する必要があります。
    
9. [**プロビジョニング パッケージ**  >  **のエクスポート] を選択します**。

10. 所有者 **を** IT 管理者 **に変更します**。これにより、このプロビジョニング パッケージの優先順位が、他のソースからこのデバイスに適用されるプロビジョニング パッケージよりも高くなります。 **[次へ]** を選択します。

11. **[パッケージのバージョン]** の値を設定します。

    > [!TIP]
    > 既存のパッケージに変更を加えてバージョン番号を変更することで、以前に適用されたパッケージを更新することができます。

12. プロビジョニング パッケージの **[セキュリティの詳細の選択] で、[次へ**] を **選択します**。

    > [!WARNING]
    > プロビジョニング パッケージを暗号化すると、HoloLens デバイスのプロビジョニングは失敗します。  

13. [ **次へ** ] を選択して、プロビジョニング パッケージがビルドされた後の出力場所を指定します。 既定では、Windows 構成デザイナーはプロジェクト フォルダーを出力先として使います。

    必要に応じて、[ **参照** ] を選択して既定の出力場所を変更することもできます。

14. **[次へ]** を選択します。

15. [ **ビルド** ] を選択して、パッケージのビルドを開始します。 ビルド ページにプロジェクト情報が表示され、進行状況バーでビルドの状態が示されます。

16. ビルドが完了したら、[ **完了**] を選択します。

<span id="apply" />

## <a name="apply-a-provisioning-package-to-hololens-during-setup"></a>セットアップ中に HoloLens にプロビジョニングパッケージを適用する

Windows Holographic バージョン2004またはビルド [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 以降の HoloLens 2 デバイスでは、USB ドライブを使用してプロビジョニングパッケージを適用できます。 単に、ppkg ファイルを USB ドライブのルートにコピーします。 プロビジョニングパッケージは、USB ドライブのルートにある場合にのみ適用されます。 複数のプロビジョニングパッケージが存在する場合は、順番に適用されます。

[Windows Holographic バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2)以降の HoloLens 2 デバイスには、このプロセスを自動化して簡素化するための新しい機能が搭載されています。 次のセクションを確認してください。

- [USB からのプロビジョニングの自動起動](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [OOBE でのプロビジョニングパッケージの自動確認](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [UI を使用しない自動プロビジョニング](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. USB ケーブルを使用して、デバイスを PC (前述のように HoloLens 2 の USB ドライブ) に接続し、デバイスを起動します。 OOBE の **最初の対話型モーメント** ページ以降は続行しないでください。   
    - HoloLens (第1世代) では、このページに青いボックスが表示されます。 
    - HoloLens 2 では、このページには hummingbird が含まれています。

2. **[音量を下げる]** ボタンと **電源** ボタンを同時に短く押して離します。 

3. HoloLens は、PC のエクスプローラーにデバイスとして表示されます。

4. エクスプローラーで、プロビジョニング パッケージ (.ppkg) をデバイス ストレージに ドラッグ アンド ドロップします。

5. OOBE の **最初の対話型モーメント** ページで、**ボリュームダウン** と **電源** ボタンを一時的にもう一度押しながら解放します。

6. パッケージを信頼できるかどうかを確認するメッセージが表示されます。 パッケージが信頼できることを確認します。

7. パッケージが正常に適用されたかどうかが表示されます。 失敗した場合、パッケージを修正してもう一度試します。 成功した場合は OOBE を続けます。

> [!NOTE]
> デバイスが 2016 年 8 月より前に購入された場合は、Microsoft アカウント を使用してデバイスにサインインし、最新のオペレーティング システムの更新プログラムを取得してから、プロビジョニング パッケージを適用するためにオペレーティング システムをリセットする必要があります。

### <a name="auto-launch-provisioning-from-usb"></a>USB からの自動起動プロビジョニング

- OOBE 中にプロビジョニング パッケージを備えた USB ドライブが使用されている場合、ユーザーの操作を減らして自動化されたプロセス。

このリリースより前は、ユーザーは、ボタンの組み合わせを使用してプロビジョニングするために、OOBE 中にプロビジョニング画面を手動で起動する必要があります。 これで、ユーザーは USB ストレージ ドライブ上のプロビジョニング パッケージを使用して、ボタンの組み合わせをスキップできます。 

1. OOBE の最初の対話可能な瞬間にプロビジョニング パッケージを使用して USB ドライブを接続する
1. デバイスをプロビジョニングする準備ができたら、プロビジョニング ページが表示されたプロンプトが自動的に開きます。 

注: デバイスの起動中に USB ドライブが接続された状態の場合、OOBE は既存の USB ストレージ デバイスを列挙し、追加の USB ストレージ デバイスが接続されているのを監視します。

OOBE の間の [プロビジョニング パッケージの適用に関するページを参照してください](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>OOBE でのプロビジョニング パッケージの自動確認
- [プロビジョニング パッケージ] ページが表示されている場合、ユーザーの操作を減らして自動プロセスを実行すると、一覧に表示されているすべてのパッケージが自動的に適用されます。

プロビジョニングのメイン画面が表示された場合、OOBE は、すべてのプロビジョニング パッケージの適用を自動的に開始する前に、10 秒をカウントダウンします。 ユーザーは、期待したパッケージを確認した後も、この 10 時間以内に確認または取り消しを行います。

### <a name="automatic-provisioning-without-using-ui"></a>UI を使用しない自動プロビジョニング
- プロビジョニングのためのデバイスの操作を減らした自動プロセスを組み合わせたもの。 

ユーザーは、USB デバイスからのプロビジョニングの自動起動とプロビジョニング パッケージの自動確認を組み合わせることで、デバイスの UI を使用したり、デバイスを装着したりすることなく、HoloLens 2 デバイスを自動的にプロビジョニングできます。 複数のデバイスに対して同じ USB ドライブとプロビジョニング パッケージを引き続き使用できます。 これは、同じ領域に複数のデバイスを一度に展開する場合に便利です。 

1. [Windows 構成デザイナー](https://www.microsoft.com/store/productId/9NBLGGH4TX22)を使用して[、プロビジョニングパッケージを作成](hololens-provisioning.md)します。 
1. パッケージを USB ストレージドライブにコピーします。
1. [HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) を [19041.1361 またはそれ以降のビルド](https://aka.ms/hololens2previewdownload)にフラッシュします。 
1. [Advanced Recovery コンパニオン](https://www.microsoft.com/store/productId/9P74Z35SFRS8)が完了したら、USB C ケーブルを取り外します。 
1. USB ドライブをデバイスに接続します。
1. HoloLens 2 デバイスが OOBE で起動すると、USB ドライブ上のプロビジョニングパッケージが自動的に検出され、[プロビジョニング] ページが起動します。
1. 10秒後に、デバイスはプロビジョニングパッケージを自動的に適用します。 

デバイスが構成され、[プロビジョニングが成功しました] 画面が表示されます。

## <a name="applyremove-a-provisioning-package-to-hololens-after-setup"></a>セットアップ後に HoloLens にプロビジョニングパッケージを適用/削除する

> [!NOTE]
> これらの手順は、Windows Holographic バージョン1809以降のすべての HoloLens 2 デバイスと HoloLens (第1世代) デバイスに適用されます。

PC で、次の手順を実行します。
1. 「Hololens [ウィザードを使用して hololens 用のプロビジョニングパッケージを作成](hololens-provisioning.md)する」の説明に従って、プロビジョニングパッケージを作成します。
2. USB ケーブルを使用して、HoloLens デバイスを PC に接続します。 HoloLens は、PC のエクスプローラーにデバイスとして表示されます。
3. プロビジョニングパッケージを HoloLens の Documents フォルダーにドラッグアンドドロップします。

HoloLens で、次の手順を実行します。
1. **[設定]**  >  **[アカウント]**  >  **[職場または学校にアクセスする]** の順に移動します。 
2. [ **関連設定**] で、[ **プロビジョニングパッケージの追加または削除**] を選択します。
3. 次のページで、[ **パッケージの追加** ] を選択してファイルピッカーを起動し、プロビジョニングパッケージを選択します。 フォルダーが空の場合は、必ず **このデバイス** を選択し、[ **ドキュメント**] を選択してください。

パッケージが適用されると、 **インストールされているパッケージ** の一覧に表示されます。 パッケージの詳細を表示したり、デバイスからパッケージを削除したりするには、一覧表示されているパッケージを選択します。

## <a name="what-you-can-configure"></a>構成内容

プロビジョニング パッケージは、構成サービス プロバイダー (CSP) を利用します。 CSP について詳しくない場合は、「[構成サービス プロバイダー (CSP) の概要 (IT 担当者向け)](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)」をご覧ください。

Windows 構成デザイナーで、Windows Holographic 向けプロビジョニング パッケージを作成する場合、**[利用可能なカスタマイズ]** の設定は [Windows Holographic でサポートされている CSP](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) によって異なります。 次の表では、HoloLens 用に構成できる設定について説明します。

![HoloLens 用の一般的な実行時設定](images/icd-settings.png)

| 設定 | Description |
| --- | --- |
| **証明書** | 証明書を HoloLens に展開します。  |
| **ConnectivityProfiles** | Wi-Fi プロファイルを HoloLens に展開します。   |
| **EditionUpgrade** | [にアップグレードWindows Holographic for Business。](hololens1-upgrade-enterprise.md)  |
| **ポリシー** | HoloLens で開発者モードを許可または禁止します。 [Windows Holographic for Business でサポートされているポリシー](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## <a name="app-install-via-provisioning-package"></a>プロビジョニング パッケージを使用したアプリのインストール

アプリは、デバイス上のプロビジョニング パッケージを使用HoloLens 2できます。 これにより、アプリの配布に役立つ簡単に再使用できるパッケージが可能になります。 プロビジョニング パッケージ を使用してアプリを [展開する手順の詳細については、以下を参照してください](app-deploy-provisioning-package.md)。  

> [!NOTE]
> HoloLens (第 1 世代) では、プロビジョニング パッケージを使用したアプリのインストール **(UniversalAppInstall)** のサポートが制限されています。 HoloLens (第 1 世代) デバイスでは、OOBE 中のみ、およびユーザー コンテキストのインストールでのみ、PPKG 経由でのアプリのインストールがサポートされます。
