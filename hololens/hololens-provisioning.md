---
title: プロビジョニング パッケージ (HoloLens) を使用して HoloLens を構成する
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
ms.date: 03/10/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 917e9fd0e8bf69eb0b7c53165029cb8e42904582
ms.sourcegitcommit: ab9e70e68d546cc6965e1569e5d914995fa508da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "10955459"
---
# プロビジョニング パッケージを使用して HoloLens を構成する

[Windows プロビジョニング](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) を行うと、IT 管理者は、イメージを使用せずにエンドユーザーのデバイスを簡単に構成できます。 Windows 構成デザイナーは、画像とランタイムの設定を構成するツールで、プロビジョニング パッケージに組み込まれたものです。

プロビジョニング パッケージに適用できる HoloLens 構成の一部は次のとおりです。

- ここでは Windows Holographic for Business にアップグレード [する](hololens1-upgrade-enterprise.md)
- ローカル アカウントをセットアップする
- Wi-Fi 接続をセットアップする
- 証明書をデバイスに適用する
- 開発者モードを有効にする
- Kiosk モードを構成します (キオスク モードの構成に関する詳細な手順については、ここを参照 [してください](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)。

## パッケージ HoloLens ウィザード

HoloLens ウィザードを使用すると、プロビジョニング パッケージで次の設定を構成できます。

- エンタープライズ エディションにアップグレードする

    > [!NOTE]
    > これは、HoloLens 1st ジン デバイスでのみ使用してください。 プロビジョニング パッケージの設定は、プロビジョニング パッケージに Windows Holographic for Business へのエディション アップグレード ライセンスが含まれている場合、または [デバイスが既に Windows Holographic for Business にアップグレード](hololens1-upgrade-enterprise.md)されている場合にのみ適用されます。

- HoloLens の最初のエクスペリエンスを構成する (OOBE)
- Wi-Fi ネットワークを構成する
- Azure Active Directory でデバイスをアナル化するか、ローカル アカウントを作成する
- 証明書を追加する
- 開発者モードを有効にする
- キオスク モードを構成します。 (キオスク モードを構成するための詳細な手順についてはここを参照[してください)。](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

> [!WARNING]
> いずれかのウィザードを使って Azure Active Directory の登録を構成するには、Windows 10 で Windows 構成デザイナーを実行する必要があります。

プロビジョニング パッケージには、管理の指示とポリシー、カスタム ネットワーク接続とポリシーなどを含めることができます。

> [!TIP]
> デスクトップ ウィザードを使用して、共通設定を含むパッケージを作成し、詳細エディターに切り替えて、他の設定、アプリ、ポリシーなどを追加します。

## パッケージのプロビジョニングを作成するための手順

1. **オプション 1:** [Microsoft ストアから。](https://www.microsoft.com/store/apps/9nblggh4tx22) これには HoloLens 2 機能が含まれます。
2. **オプション 2:** [Windows 10 の Windows 評価および配置キット (ADK) から。](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit) Windows ADK から Windows 構成デザイナ**Configuration Designer**ーをインストールする場合は、[構成デザイナー] ダイアログ ボックスから [構成デザ**イナー] を**選択します。 このオプションには、HoloLens 2 の機能は含まれません。

> [!NOTE]
> Windows 構成デザイナーへのアクセスが必要なオフライン PC を使用していることをごわかっている場合[here](https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store)は、高度な回復コンパニオンのオフライン アプリインストールに従ってください。代わりに Windows 構成の検出を下げてください。 

### 2. プロビジョニング パッケージを作成する

Windows 構成デザイナー ツールを使用して、プロビジョニング パッケージを作成します。

1. Windows 構成デザイナーを開きます (既定では %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe)。

2. **HoloLens デバイスのプロビジョニング を選択します**。

   ![ICD の起動オプション](images/icd-create-options-1703.png)

3. プロジェクトに名前を付け、[完了] を **選びます**。

4. [作業の開始] ページの **手順を読み、[** 次へ] を選択 **します**。 デスクトップ プロビジョニングのページでは、次の手順を実行します。
  
> [!IMPORTANT]
> プロビジョニング パッケージを作成する場合、プロジェクト ファイルとプロビジョニング パッケージ (.ppkg) ファイルに機密情報を含めることができます。 .ppkg ファイルは暗号化するかどうかを選べますが、プロジェクト ファイルは暗号化されません。 プロジェクト ファイルは、安全な場所に保存し、不要になったときに削除する必要があります。

### 設定の構成

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>HoloLens エディションをアップグレードするには、エンタープライズ ライセンス ファイルを参照して選択します。</br></br>[はい] または [いいえ] を切り替え <strong> </strong> <strong> </strong> 、最初のエクスペリエンスの一部を非表示にすることもできます。</br></br>Wi-Fi ネットワークに接続する必要がないデバイスをセットアップするには、[Wi-Fi 設定 <strong> をオン] に </strong> 切り切り切ります <strong> </strong> 。</br></br>デバイスを使用する地域とタイムゾーンを選択します。 </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>このセクションでは、デバイスが自動的に接続する Wi-Fi ワイヤレス ネットワークの詳細を入力できます。 これを行うには、[ <strong> オン] を </strong> 選び、SSID、ネットワークの種類 (オープンまたは <strong> </strong> <strong> WPA2-Personal) を </strong> 入力し、ワイヤレス ネットワークのパスワード <strong> (WPA2-Personal </strong> の場合) を入力します。</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>Azure Active Directory にデバイスを追加したり、デバイスのローカル アカウントを作成したりすることができます。</br></br>Windows 構成デザイナー ウィザードを使って Azure AD の登録を一括で構成する前に、<a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">組織での Azure AD 参加の設定</a>を行います。 Azure AD テナントの <strong>[ユーザーあたりのデバイスの最大数]</strong> の設定は、ウィザードで利用できる一括トークンを使用できる回数を決定します。 Azure AD にデバイスを登録するには、そのオプションを選択して、ウィザードを使って取得する一括トークンのフレンドリ名を入力します。 トークンの有効期限を設定します (最大、トークンの取得日から 30 日間)。 [ <strong> 一括トークンを取得する] を選択します </strong> 。 [サインイン&#39;ス&#39;を取得する] ウィンドウで、Azure AD へのデバイスへの参加許可 <strong> </strong> を持つアカウントを入力し、パスワードを入力します。 [ <strong> 承 </strong> 諾] を選択して、Windows 構成デザイナーに必要なアクセス許可を与えます。 </br></br>ローカル アカウントを作成するには、そのオプションを選択し、ユーザー名とパスワードを入力します。 </br></br><strong>重要:</strong> <br />(Windows 10 の場合、バージョン 1607 のみ)プロビジョニング パッケージでローカル アカウントを作成する場合は、[ <strong> </strong> 設定] アプリを 42 日ごとに設定アプリを使用してパスワードを変更する必要があります。 その期間内にパスワードを変更しない場合、アカウントがロックされてサインインできなくなる可能性があります。  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>証明書を使ってデバイスをプロビジョニングするには、<strong>[証明書の追加]</strong> をクリックします。 証明書の名前を入力し、使用する証明書を表示して選択します。</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br><strong>HoloLens でデベロッパー </strong> <strong> モードを有効にするには、Yes または No </strong> をオンに切り替えます。 <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">開発者モードの詳細をご覧ください。</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finish"/></br></br>プロビジョニング パッケージを保護するパスワードを設定しないでください。 パスワードによってプロビジョニング パッケージが保護されている場合、HoloLens デバイスのプロビジョニングは失敗します。</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

完了したら、[作成] を **選択します**。 これは数秒で終わります。 パッケージがビルドされると、ページの下部に、パッケージの格納場所がハイパーリンクで表示されます。

### 3. 高度なプロビジョニングを使用して HoloLens 用のプロビジョニング パッケージを作成する

> [!NOTE]
> **Advanced provisioning**で作成するプロビジョニング パッケージには、HoloLens (1st gen) に正常に適用できるように、Windows Holographic for Business へのエディション アップグレード ライセンスを含める必要はありません。 [Windows Holographic for HoloLens (1st gen) について詳しくは、こちらをご覧ください](hololens1-upgrade-enterprise.md)。

1. Windows 構成デザイナースタート ページで、**[プロビジョニングの詳細設定]** を選択します。
2. **[プロジェクトの詳細の入力]** ウィンドウで、プロジェクトの名前とプロジェクトの場所を指定します。 必要に応じて、プロジェクトの簡単な説明を入力します。

3. **[次へ]** を選択します。

4. ウィンドウを**表示および構成する設定を選択し****、[Windows 10 Holographic] を選択し**、[次へ] を選択**します**。

5. [完了 **] を選びます**。

6. **ランタイム設定を展開し**、この記事で後述するいずれかの設定[を使用してパッケージをカスタマイズします](#what-you-can-configure)。

    > [!IMPORTANT]
    > (Windows 10 の場合、バージョン 1607 のみ)プロビジョニング パッケージでローカル アカウントを作成する場合は、[ **設定** ] アプリを 42 日ごとに設定アプリを使用してパスワードを変更する必要があります。 その期間内にパスワードを変更しない場合、アカウントがロックされてサインインできなくなる可能性があります。 ユーザー アカウントがロックされた場合、[デバイスのフル回復](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)を実行する必要があります。

7. [ファイル**の保存]**  >  **を選びます**。

8. プロジェクト ファイルに、大文字とする情報が含まれる可能性があることを示す警告を読み **、[OK]** を選択します。

    > [!IMPORTANT]
    > プロビジョニング パッケージを作成する場合、プロジェクト ファイルとプロビジョニング パッケージ (.ppkg) ファイルに機密情報を含めることができます。 .ppkg ファイルは暗号化するかどうかを選べますが、プロジェクト ファイルは暗号化されません。 プロジェクト ファイルは、安全な場所に保存し、不要になったときに削除する必要があります。
    
9. [Export **Export**  >  **Provisioning package] を選びます**。

10. 所有者 **を** IT 管理者 **に変更します**。これにより、このプロビジョニング パッケージよりもこのプロビジョニング パッケージの事前に、このプロビジョニング パッケージの事前に、このプロビジョニング パッケージの事前に、このプロビジョニング パッケージの優先度が設定されます。 **[次へ]** を選択します。

11. **[パッケージのバージョン]** の値を設定します。

    > [!TIP]
    > 既存のパッケージに変更を加えてバージョン番号を変更することで、以前に適用されたパッケージを更新できます。

12. プロビ **ジョニング パッケージの [セキュリティの詳細を選択] で、[次**へ] を選択 **します**。

    > [!WARNING]
    > プロビジョニング パッケージを暗号化すると、HoloLens デバイスのプロビジョニングは失敗します。  

13. [ **次へ** ] を選択して、プロビジョニング パッケージを作成した後にプロビジョニング パッケージを配置する出力場所を指定します。 既定では、Windows 構成デザイナーはプロジェクト フォルダーを出力先として使います。

    必要に応じて、[参照 **] を選択** して既定の出力場所を変更できます。

14. **[次へ]** を選択します。

15. [ **ビルド]** を選択してパッケージの作成を開始します。 ビルド ページにプロジェクト情報が表示され、進行状況バーでビルドの状態が示されます。

16. ビルドが完了したら、[完了] を **選択します**。

<span id="apply" />

## セットアップ時に HoloLens にプロビジョニング パッケージを適用する

ビルド [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 以降では HoloLens 2 デバイスでは、USB ドライブを使用してプロビジョニング パッケージを適用することができます。 USB ドライブのルートに .ppkg ファイルをコピーする必要があります。 プロビジョニング パッケージは、USB ドライブのルートにある場合にのみ適用されます。 複数のプロビジョニング パッケージのプレゼンテーションは順に適用されます。

1. USB ケーブルを使用して、上で説明した PC (または HoloLens 2 用 USB ドライブ) にデバイスを接続してから、デバイスを起動します。 OOBE の最初のイン **ターフェイスに使用できる計上のタ** イル ページを継続しません。   
    - HoloLens (1st gen) では、このページには青いボックスが表示されます。 
    - HoloLens 2 では、このページにはハンマリングビードが含まれている。

2. **[音量を下げる]** ボタンと**電源**ボタンを同時に短く押して離します。 

3. HoloLens は、PC のエクスプローラーにデバイスとして表示されます。

4. エクスプローラーで、プロビジョニング パッケージ (.ppkg) をデバイス ストレージに ドラッグ アンド ドロップします。

5. OOBE の最初のインタ**Volume Down**ーフェイス率のページで電源ボ**タン**と**電**源ボタンを同時に押して離します。

6. デバイスからパッケージを信頼できるもので、適用する必要があるかを確認するメッセージが表示されます。 パッケージが信頼できることを確認します。

7. パッケージが正常に適用されたかどうかが表示されます。 失敗した場合、パッケージを修正してもう一度試します。 成功した場合は OOBE を続けます。

> [!NOTE]
> デバイスが 2016 年 8 月以前に購入された場合は、Microsoft アカウントを使用してデバイスにサインインし、最新のオペレーティング システムの更新プログラムを入手し、プロビジョニング パッケージを適用するには、オペレーティング システムをリセットする必要があります。

## セットアップ後に HoloLens にプロビジョニング パッケージを適用する

> [!NOTE]
> これらの手順は、Windows 10 バージョン 1809 にのみ適用されます。

PC で、次の手順を実行します。
1. HoloLens ウィザードを使用して、HoloLens のプロビジョニング [パッケージを作成する方法で説明したプロビジョニング パッケージを作成します](hololens-provisioning.md)。
2. USB ケーブルを使用して、HoloLens デバイスを PC に接続します。 HoloLens は、PC のエクスプローラーにデバイスとして表示されます。
3. HoloLens の [ドキュメント] フォルダーにプロビジョニング パッケージをドラッグ アンド ドロップします。

HoloLens で、次の手順を実行します。
1. [設定 **]**  >  **に移動して**  >  **、職場または学校のアクセスを行います**。 
2. [ **関連設定] で**、 **プロビジョニング パッケージを追加または削除します**。
3. 次のページで、[ **パッケージの追加** ] を選択してファイル ピッカーを起動し、プロビジョニング パッケージを選択します。 フォルダーが 1 つも含めない場合は、[このデバイス] を選択 **していることを確認し** 、[ドキュメント] を選 **びます**。

パッケージが適用されると、インストール済みパッケージの一覧 **に表示されます**。 パッケージの詳細を表示するか、またはパッケージをデバイスから削除するには、一覧から一覧表示されているパッケージを選びます。

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

> [!NOTE]
> HoloLens では、プロビジョニング パッケージを使用してアプリ **(UniversalAppInstall)** のインストールはサポートされていません。
