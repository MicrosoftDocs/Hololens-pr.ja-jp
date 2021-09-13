---
title: プロビジョニング HoloLensを使用して構成を構成する (HoloLens)
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
ms.openlocfilehash: 9474774b47858003cc11363a5f325f589b0732ab
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033900"
---
# <a name="configure-hololens-by-using-a-provisioning-package"></a>プロビジョニング HoloLensを使用して構成を構成する

[Windowsを使用すると](/windows/configuration/provisioning-packages/provisioning-packages)、IT 管理者はイメージングなしでエンド ユーザー デバイスを簡単に構成できます。 Windows構成デザイナーは、プロビジョニング パッケージに組み込むイメージとランタイム設定を構成するためのツールです。

プロビジョニング パッケージHoloLens適用できる構成の一部を次に示します。

- アップグレードして[Windows Holographic for Business](hololens1-upgrade-enterprise.md)
- ローカル アカウントをセットアップする
- Wi-Fi 接続をセットアップする
- デバイスに証明書を適用する
- 開発者モードを有効にする
- 詳細な手順に従ってキオスク [モードを構成します](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)。

## <a name="provisioning-package-hololens-wizard"></a>プロビジョニング パッケージ HoloLens ウィザード

このHoloLensは、プロビジョニング パッケージで次の設定を構成するのに役立ちます。

- Enterprise Edition にアップグレードする

    > [!NOTE]
    > これは、第 1 世代デバイスHoloLensにのみ使用する必要があります。 設定パッケージ内のパッケージは、プロビジョニング パッケージに Windows Holographic for Business へのエディション アップグレード ライセンスが含まれる場合、またはデバイスが既に Windows Holographic for Business にアップグレードされている場合[にのみ適用されます](hololens1-upgrade-enterprise.md)。

- 最初のエクスペリエンスHoloLens (OOBE) を構成する
- 仮想ネットワークWi-Fi構成する
- デバイスをローカル アカウントAzure Active Directory登録するか、ローカル アカウントを作成します
- 証明書の追加
- 開発者モードを有効にする
- の詳細な手順に従ってキオスク [モードを構成します](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)。

> [!WARNING]
> いずれかのウィザードを使って Azure Active Directory の登録を構成するには、Windows 10 で Windows 構成デザイナーを実行する必要があります。

プロビジョニング パッケージには、管理手順とポリシー、カスタム ネットワーク接続とポリシーなどがあります。

> [!TIP]
> デスクトップ ウィザードを使用して、共通設定を含むパッケージを作成し、詳細エディターに切り替えて、他の設定、アプリ、ポリシーなどを追加します。

## <a name="steps-for-creating-provisioning-packages"></a>プロビジョニング パッケージを作成する手順

1. **オプション 1:** [から Microsoft Store。](https://www.microsoft.com/store/apps/9nblggh4tx22) これには、次のHoloLens 2含まれます。
2. **オプション 2:** Windows の評価およびデプロイ キット [(ADK) からWindows 10。](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit) ADK のWindows構成デザイナー Windowsする場合は、 [インストールする機能の選択] ダイアログ ボックスから [構成デザイナー **] を** 選択します。 このオプションには、一部のHoloLens 2含まれます。

> [!NOTE]
> Windows 構成デザイナーへのアクセスが必要なオフライン PC を使用する場合は、Advanced Recovery Companion の [オフライン アプリ のインストール (hololens-recovery.md#downloading-arc-without-using-the-app-store) の手順に従ってください。 構成Windowsを選択します。 

### <a name="2-create-the-provisioning-package"></a>2.プロビジョニング パッケージを作成する

Windows 構成デザイナー ツールを使用して、プロビジョニング パッケージを作成します。

1. Windows 構成デザイナーを開きます (既定では %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe)。

2. [Provision **HoloLens devices]を選択します**。

   ![ICD の開始オプション。](images/icd-create-options-1703.png)

3. プロジェクトに名前を付け、[ 完了] を **選択します**。

4. [開始] ページの手順を読 **み** 、[次へ] を **選択します**。 デスクトップ プロビジョニングのページでは、次の手順を実行します。
  
> [!IMPORTANT]
> プロビジョニング パッケージを作成する場合、プロジェクト ファイルとプロビジョニング パッケージ (.ppkg) ファイルに機密情報を含めることができます。 .ppkg ファイルは暗号化するかどうかを選べますが、プロジェクト ファイルは暗号化されません。 プロジェクト ファイルは、安全な場所に保存し、不要になったときに削除する必要があります。

### <a name="configure-settings"></a>設定の構成

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>エンタープライズ ライセンス ファイルを参照して選択し、エディションをHoloLensします。</br></br>[はい] または <strong>[いいえ]</strong> <strong>を切り</strong> 替え、最初のエクスペリエンスの一部を非表示にできます。</br></br>デバイスをネットワークに接続する必要なくデバイスを設定するには、[Wi-Fiをスキップ] を <strong>[オンWi-Fiに切り</strong> 替 <strong>える] をオンにします</strong>。</br></br>デバイスが使用されるリージョンとタイムゾーンを選択します。 </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>このセクションでは、デバイスが自動的に接続するWi-Fiネットワークの詳細を入力できます。 これを行うには、[オン<strong></strong>] を選択し、SSID、ネットワークの種類<strong>(Open</strong>または WPA2-Personal)、ワイヤレス ネットワークのパスワード<strong>(WPA2-Personal</strong>の場合) を入力します。 <strong></strong></td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>デバイスをデバイスに登録するかAzure Active Directoryにローカル アカウントを作成できます。</br></br>Windows 構成デザイナー ウィザードを使って Azure AD の登録を一括で構成する前に、<a href="/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](/azure/active-directory/active-directory-azureadjoin-setup)">組織での Azure AD 参加の設定</a>を行います。 Azure AD テナントの <strong>[ユーザーあたりのデバイスの最大数]</strong> の設定は、ウィザードで利用できる一括トークンを使用できる回数を決定します。 Azure AD にデバイスを登録するには、そのオプションを選択して、ウィザードを使って取得する一括トークンのフレンドリ名を入力します。 トークンの有効期限を設定します (最大、トークンの取得日から 30 日間)。 [一括 <strong>トークンの取得] を選択します</strong>。 [ <strong>サインイン&#39;</strong> 許可] ウィンドウで、デバイスをサインインに参加するアクセス許可を持つアカウントをAzure AD、パスワードを入力します。 [同意<strong>する]</strong>を選択Windows必要なアクセス許可を構成デザイナーに付与します。 </br></br>ローカル アカウントを作成するには、そのオプションを選択し、ユーザー名とパスワードを入力します。 </br></br><strong>大事な：</strong> <br />(Windows 10バージョン 1607 のみ)プロビジョニング パッケージでローカル アカウントを作成する場合は、42 日お<strong></strong>きに 設定 アプリを使用してパスワードを変更する必要があります。 その期間内にパスワードを変更しない場合、アカウントがロックされてサインインできなくなる可能性があります。  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>証明書を使ってデバイスをプロビジョニングするには、<strong>[証明書の追加]</strong> をクリックします。 証明書の名前を入力し、使用する証明書を表示して選択します。</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>[<strong>はい]</strong>または<strong>[いいえ]</strong>を切り替え、HoloLens。 <a href="/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">開発者モードの詳細をご覧ください。</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>プロビジョニング パッケージを保護するためにパスワードを設定しない。 プロビジョニング パッケージがパスワードで保護されている場合、デバイスのプロビジョニングHoloLens失敗します。</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

完了したら、 **[作成]** を選択します。 これは数秒で終わります。 パッケージがビルドされると、ページの下部に、パッケージの格納場所がハイパーリンクで表示されます。

### <a name="3-create-a-provisioning-package-for-hololens-by-using-advanced-provisioning"></a>3.高度なプロビジョニングを使用して、HoloLensプロビジョニング パッケージを作成する

> [!NOTE]
> 高度なプロビジョニングで作成するプロビジョニングパッケージは、Windows Holographic for Business (第 1 世代) に完全に適用するために、エディションのアップグレード ライセンスを HoloLens Windows Holographic for Business に含める必要があります。 [詳細については、「Windows Holographic for Business (第 1 世代HoloLens)」を参照してください](hololens1-upgrade-enterprise.md)。

1. Windows 構成デザイナースタート ページで、**[プロビジョニングの詳細設定]** を選択します。
2. **[プロジェクトの詳細の入力]** ウィンドウで、プロジェクトの名前とプロジェクトの場所を指定します。 必要に応じて、プロジェクトの簡単な説明を入力します。

3. **[次へ]** を選択します。

4. [表示および **構成する設定を選択します]** ウィンドウで、[ ] を **Windows 10 Holographic** 次へ ] を **選択します**。

5. **[完了]** を選択します。

6. [ **ランタイム設定] を** 展開し、この記事で後述する設定を使用して [パッケージをカスタマイズします](#what-you-can-configure)。

    > [!IMPORTANT]
    > (Windows 10バージョン 1607 のみ)プロビジョニング パッケージでローカル アカウントを作成する場合は、42 日おきに 設定 アプリを使用してパスワードを変更する必要があります。 その期間内にパスワードを変更しない場合、アカウントがロックされてサインインできなくなる可能性があります。 ユーザー アカウントがロックされた場合、[デバイスのフル回復](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)を実行する必要があります。

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

    必要に応じて、 [参照] **を選択** して、既定の出力場所を変更できます。

14. **[次へ]** を選択します。

15. [ビルド **] を** 選択して、パッケージのビルドを開始します。 ビルド ページにプロジェクト情報が表示され、進行状況バーでビルドの状態が示されます。

16. ビルドが完了したら、 [完了] を **選択します**。

<span id="apply" />

## <a name="apply-a-provisioning-package-to-hololens-during-setup"></a>セットアップ中にプロビジョニング パッケージを HoloLens適用する

Windows HoloLens 2 Holographic バージョン 2004 またはビルド[19041.1103](hololens-release-notes.md#windows-holographic-version-2004)以降のデバイスでは、USB ドライブを使用してプロビジョニング パッケージを適用できます。 .ppkg ファイルを USB ドライブのルートにコピーします。 プロビジョニング パッケージは、USB ドライブのルートにある場合にのみ適用されます。 存在する複数のプロビジョニング パッケージが順番に適用されます。

HoloLens 2 [Holographic バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2)以降の Windows デバイスには、このプロセスを効率化し、自動化するために役立つ新しい機能があります。 次のセクションを確認してください。

- [USB からの自動起動プロビジョニング](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [OOBE でのプロビジョニング パッケージの自動確認](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [UI を使用しない自動プロビジョニング](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. USB ケーブルを使用してデバイスを PC に接続し (または前述HoloLens 2 USB ドライブ)、デバイスを起動します。 OOBE の [対話可能 **な最初の瞬間]** ページを過ぎて続行しない。
    - このHoloLens (第 1 世代) には、青いボックスが表示されます。
    - このHoloLens 2には、このページにingbird が含まれている必要があります。

2. **[音量を下げる]** ボタンと **電源** ボタンを同時に短く押して離します。

3. HoloLens PC 上のデバイスとしてエクスプローラーデバイスとして表示されます。

4. エクスプローラーで、プロビジョニング パッケージ (.ppkg) をデバイス ストレージに ドラッグ アンド ドロップします。

5. OOBE の [最初の対話可能な瞬間] ページで、ボリューム ダウンボタンと **電源** ボタンを同時に少し押して離します。

6. デバイスは、パッケージを信頼し、適用する必要がある場合に、ユーザーに確認を求める情報を表示します。 パッケージが信頼できることを確認します。

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

USB デバイスからのプロビジョニングの自動起動とプロビジョニング パッケージの自動確認を組み合わせることで、ユーザーはデバイスの UI を使用したり、デバイスを装着したりすることなく、HoloLens 2 デバイスを自動的にプロビジョニングできます。 複数のデバイスに対して同じ USB ドライブとプロビジョニング パッケージを引き続き使用できます。 これは、同じ領域に複数のデバイスを一度に展開する場合に便利です。 

1. [構成デザイナー を使用してプロビジョニング](hololens-provisioning.md)[パッケージWindows作成します](https://www.microsoft.com/store/productId/9NBLGGH4TX22)。 
1. パッケージを USB ストレージ ドライブにコピーします。
1. [19041.1361](https://aka.ms/hololens2previewdownload)以降[の](hololens-insider.md#ffu-download-and-flash-directions)ビルド にHoloLens 2をフラッシュします。 
1. Advanced [Recovery Companion で](https://www.microsoft.com/store/productId/9P74Z35SFRS8) デバイスのフラッシュが完了したら、USB-C ケーブルを取り外します。 
1. USB ドライブをデバイスに接続します。
1. デバイスHoloLens 2 OOBE に起動すると、USB ドライブ上のプロビジョニング パッケージが自動的に検出され、プロビジョニング ページが起動します。
1. 10 秒後、デバイスによってプロビジョニング パッケージが自動的に適用されます。 

これでデバイスが構成され、[プロビジョニングに成功しました] 画面が表示されます。

## <a name="applyremove-a-provisioning-package-to-hololens-after-setup"></a>セットアップ後にプロビジョニング パッケージを適用または削除HoloLensする

> [!NOTE]
> これらの手順は、HoloLens 2 Holographic バージョン 1809 以上の Windows デバイスと HoloLens (第 1 世代) のすべてのデバイスに適用されます。

PC で、次の手順に従います。
1. 「プロビジョニング ウィザードを使用してプロビジョニング パッケージを作成する」の説明に従HoloLensプロビジョニング パッケージ[HoloLensします](hololens-provisioning.md)。
2. Connect USB HoloLens使用して、デバイスを PC に接続します。 HoloLens PC 上のデバイスとしてエクスプローラーデバイスとして表示されます。
3. プロビジョニング パッケージを、プロビジョニング パッケージの [ドキュメント] フォルダーにドラッグ アンド ドロップHoloLens。

次のHoloLens手順に従います。
1. **[設定]**  >  **[アカウント]**  >  **[職場または学校にアクセスする]** の順に移動します。 
2. [**関連する設定]** で、[**プロビジョニング パッケージの追加または削除] を選択します**。
3. 次のページで[パッケージの **追加]** を選択してファイル ピッカーを起動し、プロビジョニング パッケージを選択します。 フォルダーが空の場合は、必ず [このデバイス] を **選択し、[** ドキュメント] **を選択します**。

パッケージが適用されると、インストール済みパッケージ の一覧に **表示されます**。 パッケージの詳細を表示したり、デバイスからパッケージを削除したりするには、一覧表示されているパッケージを選択します。

## <a name="what-you-can-configure"></a>構成内容

プロビジョニング パッケージは、構成サービス プロバイダー (CSP) を利用します。 CSP について詳しくない場合は、「[構成サービス プロバイダー (CSP) の概要 (IT 担当者向け)](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)」をご覧ください。

Windows 構成デザイナーで、Windows Holographic 向けプロビジョニング パッケージを作成する場合、**[利用可能なカスタマイズ]** の設定は [Windows Holographic でサポートされている CSP](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) によって異なります。 次の表では、HoloLens 用に構成できる設定について説明します。

![アプリケーションの一般的なランタイムHoloLens。](images/icd-settings.png)

| 設定 | 説明 |
| --- | --- |
| **証明書** | 証明書を HoloLens に展開します。  |
| **ConnectivityProfiles** | Wi-Fi プロファイルを HoloLens に展開します。   |
| **EditionUpgrade** | [にアップグレードWindows Holographic for Business。](hololens1-upgrade-enterprise.md)  |
| **ポリシー** | HoloLens で開発者モードを許可または禁止します。 [Windows Holographic for Business でサポートされているポリシー](/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## <a name="app-install-via-provisioning-package"></a>プロビジョニング パッケージを使用したアプリのインストール

アプリは、デバイス上のプロビジョニング パッケージを使用HoloLens 2できます。 これにより、アプリの配布に役立つ簡単に再使用できるパッケージが可能になります。 プロビジョニング パッケージ を使用してアプリを [展開する手順の詳細については、以下を参照してください](app-deploy-provisioning-package.md)。  

> [!NOTE]
> HoloLens (第 1 世代) では、プロビジョニング パッケージを使用したアプリのインストール **(UniversalAppInstall)** が制限されています。 HoloLens (第 1 世代) デバイスでは、OOBE 中のみ、およびユーザー コンテキストのインストールでのみ、PPKG 経由でのアプリのインストールがサポートされます。
