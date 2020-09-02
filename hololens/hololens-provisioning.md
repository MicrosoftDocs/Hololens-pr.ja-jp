---
title: プロビジョニングパッケージ (HoloLens) を使用して HoloLens を構成する
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
ms.openlocfilehash: da783756c271c589f67efca0c229ad0f777857e2
ms.sourcegitcommit: ccdd628cdbb5b89741f5dbc971143cb2fd2e451b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "10990910"
---
# プロビジョニングパッケージを使用して HoloLens を構成する

[Windows プロビジョニング](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) は、it 管理者がイメージングを使わずにエンドユーザーのデバイスを簡単に構成できるようにします。 Windows 構成デザイナーは、プロビジョニングパッケージに組み込まれるイメージとランタイム設定を構成するためのツールです。

プロビジョニングパッケージで適用できる HoloLens 構成の一部には、次のようなものがあります。

- [ここで](hololens1-upgrade-enterprise.md)一般法人向け Windows ホログラフィックにアップグレードする
- ローカル アカウントをセットアップする
- Wi-Fi 接続をセットアップする
- 証明書をデバイスに適用する
- 開発者モードを有効にする
- キオスクモードを構成する (キオスクモードを構成する詳細な手順については、 [こちら](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)を参照してください。

## プロビジョニングパッケージ HoloLens ウィザード

HoloLens ウィザードでは、プロビジョニングパッケージで次の設定を構成することができます。

- Enterprise edition にアップグレードする

    > [!NOTE]
    > これは、HoloLens 第1世代のデバイスに対してのみ使用する必要があります。 プロビジョニングパッケージの設定は、プロビジョニングパッケージに Windows ホログラフィック for Business のエディションアップグレードライセンスが含まれている場合、または [デバイスが既に Windows ホログラフィック For business にアップグレードされて](hololens1-upgrade-enterprise.md)いる場合にのみ適用されます。

- HoloLens の first experience (OOBE) を構成する
- Wi-fi ネットワークを構成する
- Azure Active Directory にデバイスを登録するか、ローカルアカウントを作成する
- 証明書を追加する
- 開発者モードを有効にする
- キオスクモードを構成します。 (キオスクモードを構成する詳細な手順については、 [こちら](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)を参照してください)。

> [!WARNING]
> いずれかのウィザードを使って Azure Active Directory の登録を構成するには、Windows 10 で Windows 構成デザイナーを実行する必要があります。

プロビジョニングパッケージには、管理の手順とポリシー、カスタムのネットワーク接続とポリシーなどを含めることができます。

> [!TIP]
> デスクトップ ウィザードを使用して、共通設定を含むパッケージを作成し、詳細エディターに切り替えて、他の設定、アプリ、ポリシーなどを追加します。

## プロビジョニングパッケージを作成する手順

1. **オプション 1:** [Microsoft ストアから](https://www.microsoft.com/store/apps/9nblggh4tx22) これには、HoloLens 2 の機能が含まれます。
2. **オプション 2:** windows [10 の Windows アセスメント & デプロイメントキット (ADK) から](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit)。 Windows ADK から Windows 構成デザイナーをインストールする場合は、[**インストールする機能を選択**してください] ダイアログボックスで [**構成デザイナー** ] を選択します。 このオプションには、HoloLens 2 機能は含まれません。

> [!NOTE]
> Windows 構成デザイナーへのアクセスが必要なオフライン PC を使用していることがわかっている場合は、 [この](https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) 後の「アドバンスト回復コンパニオンのためのオフラインアプリのインストール」を参照してください。ただし、代わりに windows Confiugration で選択を行うことができます。 

### 2. プロビジョニングパッケージを作成する

Windows 構成デザイナー ツールを使用して、プロビジョニング パッケージを作成します。

1. Windows 構成デザイナーを開きます (既定では %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe)。

2. [ **HoloLens デバイスのプロビジョニング**] を選びます。

   ![ICD の起動オプション](images/icd-create-options-1703.png)

3. プロジェクトに名前を指定し、[ **完了**] を選択します。

4. [ **はじめに] ページの** 手順を読み、[ **次へ**] を選びます。 デスクトッププロビジョニング用のページでは、次の手順を実行します。
  
> [!IMPORTANT]
> プロビジョニング パッケージを作成する場合、プロジェクト ファイルとプロビジョニング パッケージ (.ppkg) ファイルに機密情報を含めることができます。 .ppkg ファイルは暗号化するかどうかを選べますが、プロジェクト ファイルは暗号化されません。 プロジェクト ファイルは、安全な場所に保存し、不要になったときに削除する必要があります。

### 設定の構成

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>HoloLens エディションをアップグレードするエンタープライズライセンスファイルを参照して選びます。</br></br><strong>また、[はい] </strong> または [ <strong> いいえ] </strong> を切り替えて、最初のエクスペリエンスの一部を非表示にすることもできます。</br></br>Wi-fi ネットワークに接続しなくてもデバイスをセットアップするには、 <strong> [wi-fi のセットアップ </strong> をスキップします] をオンに切り替え <strong> </strong> ます。</br></br>デバイスが使用される地域とタイムゾーンを選択します。 </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>このセクションでは、デバイスが自動的に接続する Wi-fi ワイヤレスネットワークの詳細を入力できます。 これを行うには、[ <strong> オン] を選び </strong> 、SSID、ネットワーク <strong> の種類 ([オープン] </strong> または [ <strong> wpa2-パーソナル] </strong> )、および [ <strong> </strong> ワイヤレスネットワークのパスワード] (wpa2-個人用) を入力します。</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>Azure Active Directory にデバイスを登録するか、デバイスにローカルアカウントを作成することができます。</br></br>Windows 構成デザイナー ウィザードを使って Azure AD の登録を一括で構成する前に、<a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">組織での Azure AD 参加の設定</a>を行います。 Azure AD テナントの <strong>[ユーザーあたりのデバイスの最大数]</strong> の設定は、ウィザードで利用できる一括トークンを使用できる回数を決定します。 Azure AD にデバイスを登録するには、そのオプションを選択して、ウィザードを使って取得する一括トークンのフレンドリ名を入力します。 トークンの有効期限を設定します (最大、トークンの取得日から 30 日間)。 [ <strong> バルクトークンの取得] を選び </strong> ます。 <strong>[&#39;s にサインインします </strong> ] ウィンドウで、Azure AD にデバイスを参加するためのアクセス許可を持つアカウントを入力し、その後、パスワードを入力します。 [同意する] を選択し <strong> </strong> て、Windows 構成デザイナーに必要なアクセス許可を付与します。 </br></br>ローカルアカウントを作成するには、このオプションを選択し、ユーザー名とパスワードを入力します。 </br></br><strong>重要:</strong> <br />(Windows 10 バージョン1607のみ)プロビジョニングパッケージでローカルアカウントを作成する場合は、[設定] アプリで42日ごとにパスワードを変更する必要があり <strong> </strong> ます。 その期間内にパスワードを変更しない場合、アカウントがロックされてサインインできなくなる可能性があります。  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>証明書を使ってデバイスをプロビジョニングするには、<strong>[証明書の追加]</strong> をクリックします。 証明書の名前を入力し、使用する証明書を表示して選択します。</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br><strong> </strong> <strong> </strong> HoloLens で開発者モードを有効にするには、[はい] または [いいえ] をオンにします。 <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">開発者モードの詳細をご覧ください。</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finish"/></br></br>プロビジョニングパッケージを保護するためにパスワードを設定しないでください。 プロビジョニングパッケージがパスワードで保護されている場合、HoloLens デバイスのプロビジョニングは失敗します。</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

完了したら、[ **作成**] を選択します。 これは数秒で終わります。 パッケージがビルドされると、ページの下部に、パッケージの格納場所がハイパーリンクで表示されます。

### 3. advanced provisioning を使用して HoloLens 用のプロビジョニングパッケージを作成する

> [!NOTE]
> **Advanced provisioning**で作成するプロビジョニングパッケージでは、ビジネスが HoloLens (1 つ目の gen) に正常に適用されるようにするために、Windows ホログラフィックのエディションアップグレードライセンスを含める必要はありません。 [詳細については、「HoloLens For Business For ホログラフィック (第1世代)」を参照してください](hololens1-upgrade-enterprise.md)。

1. Windows 構成デザイナースタート ページで、**[プロビジョニングの詳細設定]** を選択します。
2. **[プロジェクトの詳細の入力]** ウィンドウで、プロジェクトの名前とプロジェクトの場所を指定します。 必要に応じて、プロジェクトの簡単な説明を入力します。

3. **[次へ]** を選択します。

4. [ **表示および構成する設定を選択** してください] ウィンドウで、[ **Windows 10 ホログラフィック**] を選び、[ **次へ**] を選びます。

5. [ **完了**] を選びます。

6. [この記事の後半で説明](#what-you-can-configure)する設定のいずれかを使用して、[**ランタイム設定**] を展開し、パッケージをカスタマイズします。

    > [!IMPORTANT]
    > (Windows 10 バージョン1607のみ)プロビジョニングパッケージでローカルアカウントを作成する場合は、[ **設定** ] アプリで42日ごとにパスワードを変更する必要があります。 その期間内にパスワードを変更しない場合、アカウントがロックされてサインインできなくなる可能性があります。 ユーザー アカウントがロックされた場合、[デバイスのフル回復](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)を実行する必要があります。

7. [**ファイル**  >  の**保存**] を選びます。

8. プロジェクトファイルに機密情報が含まれている可能性があるという警告を読み、[ **OK]** を選択します。

    > [!IMPORTANT]
    > プロビジョニング パッケージを作成する場合、プロジェクト ファイルとプロビジョニング パッケージ (.ppkg) ファイルに機密情報を含めることができます。 .ppkg ファイルは暗号化するかどうかを選べますが、プロジェクト ファイルは暗号化されません。 プロジェクト ファイルは、安全な場所に保存し、不要になったときに削除する必要があります。
    
9. [ **Export**  >  **プロビジョニングパッケージ**のエクスポート] を選びます。

10. **所有者**を**IT 管理**者に変更します。これにより、このプロビジョニングパッケージの優先順位が、他のソースからこのデバイスに適用されるプロビジョニングパッケージよりも高くなります。 **[次へ]** を選択します。

11. **[パッケージのバージョン]** の値を設定します。

    > [!TIP]
    > 既存のパッケージに変更を加えてバージョン番号を変更することで、以前に適用されたパッケージを更新できます。

12. **プロビジョニングパッケージの [セキュリティの詳細の選択**] で、[**次へ**] を選びます。

    > [!WARNING]
    > プロビジョニング パッケージを暗号化すると、HoloLens デバイスのプロビジョニングは失敗します。  

13. [ **次へ** ] を選択して、プロビジョニングパッケージをビルドするときの出力場所を指定します。 既定では、Windows 構成デザイナーはプロジェクト フォルダーを出力先として使います。

    必要に応じて [ **参照** ] を選択して、既定の出力場所を変更できます。

14. **[次へ]** を選択します。

15. [ **ビルド** ] を選択して、パッケージの作成を開始します。 ビルド ページにプロジェクト情報が表示され、進行状況バーでビルドの状態が示されます。

16. ビルドが完了したら、[ **完了**] を選びます。

<span id="apply" />

## セットアップ中に HoloLens にプロビジョニングパッケージを適用する

HoloLens 2 デバイス (ビルド [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 以降) では、USB ドライブを使用してプロビジョニングパッケージを適用することができます。 ファイルを USB ドライブのルートにコピーします。 プロビジョニングパッケージは、USB ドライブのルートにある場合にのみ適用されます。 複数のプロビジョニングパッケージが順番に適用されます。

1. USB ケーブルを使用して、デバイスを PC (上記で説明した HoloLens 2 の USB ドライブ) に接続してから、デバイスを起動します。 OOBE の **最初の押さモーメント** ページ以降は続行しないでください。   
    - HoloLens (第1世代) では、このページには青色のボックスが含まれています。 
    - HoloLens 2 では、このページに hummingbird が含まれています。

2. **[音量を下げる]** ボタンと**電源**ボタンを同時に短く押して離します。 

3. PC のエクスプローラーで、HoloLens がデバイスとして表示されます。

4. エクスプローラーで、プロビジョニング パッケージ (.ppkg) をデバイス ストレージに ドラッグ アンド ドロップします。

5. OOBE の**最初の押さ**の [] ページで、**音量**をすばやく押して、もう一度**電源**ボタンを放します。

6. パッケージを信頼しているかどうかをデバイスが確認し、アプリを適用します。 パッケージが信頼できることを確認します。

7. パッケージが正常に適用されたかどうかが表示されます。 失敗した場合、パッケージを修正してもう一度試します。 成功した場合は OOBE を続けます。

> [!NOTE]
> 2016年8月より前にデバイスを購入した場合は、Microsoft アカウントを使用してデバイスにサインインし、最新のオペレーティングシステム更新プログラムを入手して、プロビジョニングパッケージを適用するためにオペレーティングシステムをリセットする必要があります。

## セットアップ後に HoloLens にプロビジョニングパッケージを適用する

> [!NOTE]
> これらの手順は、Windows 10 バージョン1809にのみ適用されます。

PC の場合は、次の手順を実行します。
1. 「 [Hololens ウィザードを使って hololens 用のプロビジョニングパッケージを作成する](hololens-provisioning.md)」の説明に従ってプロビジョニングパッケージを作成します。
2. USB ケーブルを使用して、HoloLens デバイスを PC に接続します。 PC のエクスプローラーで、HoloLens がデバイスとして表示されます。
3. プロビジョニングパッケージを HoloLens の [ドキュメント] フォルダーにドラッグアンドドロップします。

HoloLens では、次の手順を実行します。
1. [ **Settings**  >  **アカウント**  >  **アクセスの職場または学校にアクセス**する] 設定に移動します。 
2. [ **関連設定**] で、[ **プロビジョニングパッケージの追加または削除**] を選択します。
3. 次のページで [ **パッケージの追加** ] を選択して、ファイルピッカーを起動し、プロビジョニングパッケージを選択します。 フォルダーが空の場合は、[ **このデバイス** ] を選択し、[ **ドキュメント**] を選択してください。

パッケージを適用すると、 **インストールされているパッケージ**の一覧に表示されます。 パッケージの詳細を表示するか、またはデバイスからパッケージを削除するには、一覧表示されたパッケージを選択します。

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

## プロビジョニングパッケージを使用したアプリのインストール

アプリは、HoloLens 2 デバイスのプロビジョニングパッケージを使ってインストールできます。 これにより、簡単に再利用できるパッケージを使用して、アプリの配布に役立ちます。 [プロビジョニングパッケージでアプリを展開](app-deploy-provisioning-package.md)するための詳しい手順を参照してください。  

> [!NOTE]
> HoloLens (第1世代) は、プロビジョニングパッケージを使ったアプリのインストール (**UniversalAppInstall**) をサポートしていません。
