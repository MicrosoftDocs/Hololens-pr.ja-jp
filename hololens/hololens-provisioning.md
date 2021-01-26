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
ms.openlocfilehash: b22baa62488bbdf6d2a8a43b6487bbe5ec3277cb
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284158"
---
# プロビジョニング パッケージを使用して HoloLens を構成する

[Windows プロビジョニングを使用](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) すると、IT 管理者はイメージングを行わずにエンド ユーザー のデバイスを簡単に構成できます。 Windows 構成デザイナーは、プロビジョニング パッケージに組み込むイメージと実行時の設定を構成するためのツールです。

プロビジョニング パッケージで適用できる HoloLens 構成には、次のようなものがあります。

- Windows [Holographic for Business へのアップグレード](hololens1-upgrade-enterprise.md)
- ローカル アカウントをセットアップする
- Wi-Fi 接続をセットアップする
- 証明書をデバイスに適用する
- 開発者モードを有効にする
- 詳しい手順に従ってキオスク [モードを構成します](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)。

## プロビジョニング パッケージ HoloLens ウィザード

HoloLens ウィザードは、プロビジョニング パッケージで次の設定を構成するのに役立ちます。

- Enterprise Edition にアップグレードする

    > [!NOTE]
    > これは、HoloLens の第 1 世代デバイスでのみ使用してください。 プロビジョニング パッケージの設定は、プロビジョニング パッケージに Windows Holographic for Business へのエディション アップグレード ライセンスが含まれている場合、またはデバイスが既に [Windows Holographic for Business](hololens1-upgrade-enterprise.md)にアップグレードされている場合にのみ適用されます。

- HoloLens の最初のエクスペリエンスを構成する (OOBE)
- 新しいネットワークWi-Fi構成する
- Azure Active Directory にデバイスを登録するか、ローカル アカウントを作成する
- 証明書を追加する
- 開発者モードを有効にする
- 詳しい手順に従ってキオスク [モードを構成します](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)。

> [!WARNING]
> いずれかのウィザードを使って Azure Active Directory の登録を構成するには、Windows 10 で Windows 構成デザイナーを実行する必要があります。

プロビジョニング パッケージには、管理手順とポリシー、カスタム ネットワーク接続とポリシー、その他を含めできます。

> [!TIP]
> デスクトップ ウィザードを使用して、共通設定を含むパッケージを作成し、詳細エディターに切り替えて、他の設定、アプリ、ポリシーなどを追加します。

## プロビジョニング パッケージを作成する手順

1. **オプション 1:** [Microsoft Store から](https://www.microsoft.com/store/apps/9nblggh4tx22)。 これには、HoloLens 2 の機能が含まれます。
2. **オプション 2:** [Windows 10 用 Windows アセスメント デプロイメント キット (ADK) から](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit)。 Windows ADK から Windows 構成デザイナーをインストール**** する場合は、[インストールする機能の選択] ダイアログ ボックスから [構成デザイナー]**を**選択します。 このオプションには、HoloLens 2 の機能は含まれます。

> [!NOTE]
> Windows 構成デザイナーにアクセスする必要があるオフライン PC を使用する場合は、[オフライン アプリのインストール( Advanced Recovery Companion の手順) に https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) 従ってください。 Windows 構成デザイナーを選択します。 

### 2. プロビジョニング パッケージを作成する

Windows 構成デザイナー ツールを使用して、プロビジョニング パッケージを作成します。

1. Windows 構成デザイナーを開きます (既定では %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe)。

2. **[HoloLens デバイスのプロビジョニング] を選択します**。

   ![ICD の起動オプション](images/icd-create-options-1703.png)

3. プロジェクトに名前を付け、[完了] を **選択します**。

4. [開始] ページの手順 **を読み** 、[次へ] を選択 **します**。 デスクトップ プロビジョニングのページでは、次の手順を実行します。
  
> [!IMPORTANT]
> プロビジョニング パッケージを作成する場合、プロジェクト ファイルとプロビジョニング パッケージ (.ppkg) ファイルに機密情報を含めることができます。 .ppkg ファイルは暗号化するかどうかを選べますが、プロジェクト ファイルは暗号化されません。 プロジェクト ファイルは、安全な場所に保存し、不要になったときに削除する必要があります。

### 設定の構成

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>HoloLens エディションをアップグレードするエンタープライズ ライセンス ファイルを参照して選択します。</br></br>[はい] または <strong> [ </strong> いいえ] を切り替 <strong> え、 </strong> 最初のエクスペリエンスの一部を非表示にできます。</br></br>Wi-Fi ネットワークに接続せずにデバイスをセットアップするには、セットアップを [スキップWi-Fi <strong> オンに </strong> 切り替える] を <strong> オンにします </strong> 。</br></br>デバイスを使用する地域とタイムゾーンを選択します。 </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>このセクションでは、デバイスが自動的に接続するWi-Fiネットワークの詳細を入力できます。 これを行うには、[オン] を選択し、SSID、ネットワークの種類 <strong> </strong> <strong> (Open または WPA2-Personal)、ワイヤレス ネットワークのパスワード </strong> <strong> </strong> <strong> (WPA2 -Personal の場合) を </strong> 入力します。</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>デバイスを Azure Active Directory に登録するか、デバイスにローカル アカウントを作成できます。</br></br>Windows 構成デザイナー ウィザードを使って Azure AD の登録を一括で構成する前に、<a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">組織での Azure AD 参加の設定</a>を行います。 Azure AD テナントの <strong>[ユーザーあたりのデバイスの最大数]</strong> の設定は、ウィザードで利用できる一括トークンを使用できる回数を決定します。 Azure AD にデバイスを登録するには、そのオプションを選択して、ウィザードを使って取得する一括トークンのフレンドリ名を入力します。 トークンの有効期限を設定します (最大、トークンの取得日から 30 日間)。 [一括 <strong> トークンの取得] を選択します </strong> 。 [サインイン&#39;許可] ウィンドウで、デバイスを Azure AD に参加するためのアクセス許可を持つアカウントを入力し、パスワードを <strong> </strong> 入力します。 [ <strong> 承諾] </strong> を選択して、Windows 構成デザイナーに必要なアクセス許可を付与します。 </br></br>ローカル アカウントを作成するには、そのオプションを選択し、ユーザー名とパスワードを入力します。 </br></br><strong>重要:</strong> <br />(Windows 10 バージョン 1607 の場合のみ)プロビジョニング パッケージでローカル アカウントを作成する場合は、42 日ごとに設定アプリを使用してパスワードを <strong> </strong> 変更する必要があります。 その期間内にパスワードを変更しない場合、アカウントがロックされてサインインできなくなる可能性があります。  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>証明書を使ってデバイスをプロビジョニングするには、<strong>[証明書の追加]</strong> をクリックします。 証明書の名前を入力し、使用する証明書を表示して選択します。</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br><strong>[はい </strong> ] または <strong> [ </strong> いいえ] を切り替え、HoloLens で開発者モードを有効にします。 <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">開発者モードの詳細をご覧ください。</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>プロビジョニング パッケージを保護するためのパスワードを設定しない。 プロビジョニング パッケージがパスワードで保護されている場合、HoloLens デバイスのプロビジョニングは失敗します。</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

完了したら、[作成] を選択 **します**。 これは数秒で終わります。 パッケージがビルドされると、ページの下部に、パッケージの格納場所がハイパーリンクで表示されます。

### 3. 高度なプロビジョニングを使用して HoloLens のプロビジョニング パッケージを作成する

> [!NOTE]
> 高度なプロビジョニングで作成するプロビジョニング**** パッケージは、HoloLens (第 1 世代) に完全に適用するために、Windows Holographic for Business へのエディション アップグレード ライセンスを含める必要があります。 [HoloLens (第 1 世代) 向け Windows Holographic for Business の詳細をご覧ください](hololens1-upgrade-enterprise.md)。

1. Windows 構成デザイナースタート ページで、**[プロビジョニングの詳細設定]** を選択します。
2. **[プロジェクトの詳細の入力]** ウィンドウで、プロジェクトの名前とプロジェクトの場所を指定します。 必要に応じて、プロジェクトの簡単な説明を入力します。

3. **[次へ]** を選択します。

4. [表示 **および構成する設定** の選択] ウィンドウで **、[Windows 10 Holographic]** を選択し、[次へ] を選択 **します**。

5. [完了] **を選択します**。

6. [ **実行時の設定]** を展開し、この記事で後述する設定を使用して [パッケージをカスタマイズします](#what-you-can-configure)。

    > [!IMPORTANT]
    > (Windows 10 バージョン 1607 の場合のみ)プロビジョニング パッケージでローカル アカウントを作成する場合は、42 日ごとに**** 設定アプリを使用してパスワードを変更する必要があります。 その期間内にパスワードを変更しない場合、アカウントがロックされてサインインできなくなる可能性があります。 ユーザー アカウントがロックされた場合、[デバイスのフル回復](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)を実行する必要があります。

7. [ファイル**の保存]**  >  **を選択します**。

8. プロジェクト ファイルに機密情報が含まれている可能性があるという警告を読み **、OK**を選択します。

    > [!IMPORTANT]
    > プロビジョニング パッケージを作成する場合、プロジェクト ファイルとプロビジョニング パッケージ (.ppkg) ファイルに機密情報を含めることができます。 .ppkg ファイルは暗号化するかどうかを選べますが、プロジェクト ファイルは暗号化されません。 プロジェクト ファイルは、安全な場所に保存し、不要になったときに削除する必要があります。
    
9. [プロビジョニング**パッケージ**  >  **のエクスポート] を選択します**。

10. 所有者 **を** **IT 管理者に変更します**。これにより、このプロビジョニング パッケージの優先順位が、他のソースからこのデバイスに適用されるプロビジョニング パッケージよりも高く設定されます。 **[次へ]** を選択します。

11. **[パッケージのバージョン]** の値を設定します。

    > [!TIP]
    > 既存のパッケージに変更を加えてバージョン番号を変更することで、以前に適用されたパッケージを更新できます。

12. [プロビジョニング パッケージ **のセキュリティの詳細の選択] で、[次へ**] を選択 **します**。

    > [!WARNING]
    > プロビジョニング パッケージを暗号化すると、HoloLens デバイスのプロビジョニングは失敗します。  

13. [ **次へ** ] を選択して、ビルド後にプロビジョニング パッケージを実行する出力場所を指定します。 既定では、Windows 構成デザイナーはプロジェクト フォルダーを出力先として使います。

    必要に応じて、[参照] **を選択** して既定の出力場所を変更できます。

14. **[次へ]** を選択します。

15. [ **ビルド] を** 選択してパッケージのビルドを開始します。 ビルド ページにプロジェクト情報が表示され、進行状況バーでビルドの状態が示されます。

16. ビルドが完了したら、[完了] を選択 **します**。

<span id="apply" />

## セットアップ中に HoloLens にプロビジョニング パッケージを適用する

Windows Holographic バージョン 2004 またはビルド [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 以降の HoloLens 2 デバイスでは、USB ドライブを使ってプロビジョニング パッケージを適用できます。 .ppkg ファイルを USB ドライブのルートにコピーします。 プロビジョニング パッケージは、USB ドライブのルートにある場合にのみ適用されます。 存在する複数のプロビジョニング パッケージが順番に適用されます。

[Windows Holographic Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2)以降の HoloLens 2 デバイスには、このプロセスを効率化して簡素化するための新しい機能が追加されています。 次のセクションを確認してください。

- [USB からの自動起動プロビジョニング](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [OOBE でのプロビジョニング パッケージの自動確認](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [UI を使用しない自動プロビジョニング](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. USB ケーブルを使ってデバイスを PC (または前述の HoloLens 2 の USB ドライブ) に接続し、デバイスを起動します。 OOBE の [対話可能な **最初の瞬間]** ページを過ぎて続行しない。   
    - HoloLens (第 1 世代) では、このページには青いボックスが表示されます。 
    - HoloLens 2 では、このページに hummingbird が含まれている。

2. **[音量を下げる]** ボタンと**電源**ボタンを同時に短く押して離します。 

3. HoloLens は、PC のエクスプローラーにデバイスとして表示されます。

4. エクスプローラーで、プロビジョニング パッケージ (.ppkg) をデバイス ストレージに ドラッグ アンド ドロップします。

5. OOBE の [**** 操作可能な最初の瞬間] ページで、**** ボリューム ダウン ボタンと**電源**ボタンを同時に簡単に押して離します。

6. パッケージを信頼して適用する場合は、デバイスから確認が表示されます。 パッケージが信頼できることを確認します。

7. パッケージが正常に適用されたかどうかが表示されます。 失敗した場合、パッケージを修正してもう一度試します。 成功した場合は OOBE を続けます。

> [!NOTE]
> デバイスが 2016 年 8 月より前に購入された場合、プロビジョニング パッケージを適用するには、Microsoft アカウントを使用してデバイスにサインインし、最新のオペレーティング システム更新プログラムを取得し、オペレーティング システムをリセットする必要があります。

### USB からの自動起動プロビジョニング

- OOBE 中にプロビジョニング パッケージ付き USB ドライブを使用する場合に、ユーザー操作を減らす自動プロセス。

このリリースの前に、ユーザーは OOBE 中にプロビジョニング画面を手動で起動して、ボタンの組み合わせを使用してプロビジョニングする必要があります。 これで、ユーザーは USB ストレージ ドライブ上のプロビジョニング パッケージを使って、ボタンの組み合わせをスキップできます。 

1. OOBE の最初の対話可能な瞬間にプロビジョニング パッケージを使って USB ドライブを接続する
1. デバイスをプロビジョニングする準備ができたら、プロビジョニング ページでプロンプトが自動的に開きます。 

注: デバイスの起動中に USB ドライブが電源に接続された状態の場合、OOBE は既存の USB ストレージ デバイスを列挙し、追加の USB ストレージ デバイスが接続されているのを監視します。

OOBE 中に [プロビジョニング パッケージを適用する方法についてお読みください](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。

### OOBE でのプロビジョニング パッケージの自動確認
- [プロビジョニング パッケージ] ページが表示されているときに、ユーザー操作を減らして自動化されたプロセスを実行すると、一覧に表示されているパッケージすべてが自動的に適用されます。

プロビジョニングのメイン画面が表示された場合、OOBE は、すべてのプロビジョニング パッケージの適用を自動的に開始する前に 10 秒カウント ダウンします。 ユーザーは、期待したパッケージを確認した後、この 10 分以内に確認またはキャンセルできます。

### UI を使用しない自動プロビジョニング
- プロビジョニングのためのデバイス操作を減らした場合の自動プロセスの組み合わせ。 

USB デバイスからのプロビジョニングの自動起動とプロビジョニング パッケージの自動確認を組み合わせることで、ユーザーはデバイスの UI を使用したり、デバイスを装着したりすることなく、HoloLens 2 デバイスを自動的にプロビジョニングできます。 複数のデバイスに同じ USB ドライブとプロビジョニング パッケージを引き続き使う場合があります。 これは、同じ領域に複数のデバイスを一度に展開する場合に便利です。 

1. Windows[構成デザイナーを使用して](hololens-provisioning.md)プロビジョニング[パッケージを作成します](https://www.microsoft.com/store/productId/9NBLGGH4TX22)。 
1. パッケージを USB ストレージ ドライブにコピーします。
1. [HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) から [19041.1361 以降のビルドをフラッシュします](https://aka.ms/hololens2previewdownload)。 
1. Advanced [Recovery Companion が](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 完了したら、デバイスのフラッシュを完了し、USB-C ケーブルを取り外します。 
1. USB ドライブをデバイスに接続します。
1. HoloLens 2 デバイスが OOBE で起動すると、USB ドライブ上のプロビジョニング パッケージが自動的に検出され、プロビジョニング ページが起動します。
1. 10 秒後、デバイスはプロビジョニング パッケージを自動的に適用します。 

これで、デバイスが構成され、[プロビジョニング成功] 画面が表示されます。

## セットアップ後にプロビジョニング パッケージを HoloLens に適用する

> [!NOTE]
> これらの手順は、Windows 10 バージョン 1809 にのみ適用されます。

PC で、次の手順を実行します。
1. 「HoloLens のプロビジョニング パッケージを作成する」の説明に従って [、HoloLens](hololens-provisioning.md)ウィザードを使用してプロビジョニング パッケージを作成します。
2. USB ケーブルを使って HoloLens デバイスを PC に接続します。 HoloLens は、PC のエクスプローラーにデバイスとして表示されます。
3. プロビジョニング パッケージを HoloLens の Documents フォルダーにドラッグ アンド ドロップします。

HoloLens で、次の手順を実行します。
1. [設定アカウント **]**  >  **に移動**  >  **して、仕事または学校にアクセスします**。 
2. [ **関連する設定]** で、[プロビジョニング パッケージ **の追加または削除] を選択します**。
3. 次のページで、[パッケージの追加] **を** 選択してファイル ピッカーを起動し、プロビジョニング パッケージを選択します。 フォルダーが空の場合は、[このデバイス] **を選択し** 、[ドキュメント] を **選択します**。

パッケージが適用されると、インストール済みパッケージの一覧に **表示されます**。 パッケージの詳細を表示したり、デバイスからパッケージを削除したりするには、一覧表示されているパッケージを選択します。

## 構成可能なもの

プロビジョニング パッケージは、構成サービス プロバイダー (CSP) を利用します。 CSP について詳しくない場合は、「[構成サービス プロバイダー (CSP) の概要 (IT 担当者向け)](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)」をご覧ください。

Windows 構成デザイナーで、Windows Holographic 向けプロビジョニング パッケージを作成する場合、**[利用可能なカスタマイズ]** の設定は [Windows Holographic でサポートされている CSP](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) によって異なります。 次の表では、HoloLens 用に構成できる設定について説明します。

![HoloLens 用の一般的な実行時設定](images/icd-settings.png)

| 設定 | 説明 |
| --- | --- |
| **証明書** | 証明書を HoloLens に展開します。  |
| **ConnectivityProfiles** | Wi-Fi プロファイルを HoloLens に展開します。   |
| **EditionUpgrade** | [Windows Holographic for Business にアップグレードします。](hololens1-upgrade-enterprise.md)  |
| **Policies** | HoloLens で開発者モードを許可または禁止します。 [Windows Holographic for Business でサポートされているポリシー](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## プロビジョニング パッケージによるアプリのインストール

アプリは、HoloLens 2 デバイスのプロビジョニング パッケージを使ってインストールできます。 これにより、アプリの配布に役立つ簡単に再使用できるパッケージが可能になります。 プロビジョニング パッケージを使ったアプリの [展開に関する詳しい手順をお読みください](app-deploy-provisioning-package.md)。  

> [!NOTE]
> HoloLens (第 1 世代) では、プロビジョニング パッケージを使用したアプリのインストール **(UniversalAppInstall)** のサポートが制限されています。 HoloLens (第 1 世代) デバイスは、OOBE 中のみ、およびユーザー コンテキストインストールでのみ PPKG 経由のアプリのインストールをサポートします。
