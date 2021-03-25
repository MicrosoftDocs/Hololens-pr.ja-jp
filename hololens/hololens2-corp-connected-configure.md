---
title: 展開ガイド - Dynamics 365 ガイドを使用した企業接続 HoloLens 2 - Configure
description: Dynamics 365 Guides を使用して企業の接続ネットワーク上に HoloLens 2 デバイスを展開する構成をセットアップする方法について説明します。
keywords: HoloLens、管理、企業接続、Dynamics 365 ガイド、AAD、Azure AD、MDM、モバイル デバイス管理
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 939efc28a0c3255cc9a38af3cd8dd9aa8fc2ac98
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448586"
---
# <a name="configure---corporate-connected-guide"></a>構成 - 企業向けコネクテッド ガイド

## <a name="azure-users-and-groups"></a>Azure のユーザーとグループ

Azure、Intune は、ユーザーとグループを使用して構成とライセンスを割り当てるのに役立ちます。 この展開フローを検証し、ガイドを作成して操作&#39;確認するには、ユーザー アカウントが必要です。

ライセンスの割り当て専用に 1 つのユーザー グループを作成できます。

ユーザー グループ内&#39;2 つの Azure ADにアクセスできない場合は、使用できます。クイック スタート ガイドを次に示します。

- [ユーザーを作成する方法](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [グループを作成する方法](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [グループにユーザーを追加する](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – 作成したユーザーを追加してグループを作成する
- [ユーザー グループADデバイス](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) への参加を許可するように Azure AD を構成する – 新しいユーザー グループが Azure デバイスにデバイスを登録するアクセス許可を持AD

## <a name="auto-enrollment-on-hololens-2"></a>HoloLens 2 の自動登録

スムーズでシームレスなエクスペリエンスを実現するには、Azure Active Directory Join (AADJ) と HoloLens 2 デバイス用の Intune への自動登録を設定する方法があります。 これにより、ユーザーは OOBE 中に組織のログイン資格情報を入力し、Azure ADに自動的に登録し、デバイスを MDM に登録できます。

Microsoft Endpoint [Manager を使用すると、](https://endpoint.microsoft.com/#home)サービスを選択し、[プレミアム試用版を取得する] を選択するまで、いくつかのページを移動できます。 Azure Active Directory Premium 1 と 2 がある場合があります。自動登録 P1 で十分です。 Intune を選択し、自動登録のユーザー スコープを選択し、以前に作成したグループを選択できます。

詳細と手順については、Intune の自動登録を [有効にする方法に関するガイドを参照してください](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)。

## <a name="corporate-wi-fi-connectivity"></a>企業Wi-Fi接続

企業Wi-Fi接続では、HoloLens 2 を使用しているお客様に対して証明書ベースの認証が一般的に必要になります。 このような証明書は、MDM ソリューションと統合された簡易証明書登録プロトコル (SCEP) または公開キー暗号化標準 (PKCS) 証明書インフラストラクチャを使用して展開する必要があります。 Intune を使用して、Wi-Fi、証明書、およびプロキシ設定を展開すると、エンド ユーザーにシームレスなエクスペリエンスが作成されます。
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>証明書とプロファイルWi-Fi展開する

Microsoft Endpoint Manager を使用して証明書とプロファイルを展開するには、次の手順を実行します。

1. ルート証明書と中間証明書のそれぞれについてプロファイルを作成します (「信頼できる証明書プロファイルの作成[」を参照)。](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles) これらの各プロファイルには、DD/MM/YYYYY 形式の有効期限を含む説明が必要です。 

    > [!CAUTION]
    > **有効期限のない証明書プロファイルは展開されません**。

2.  SCEP 証明書または PKCS 証明書のそれぞれにプロファイルを作成します (「[Create a SCEP certificate profile or Create a PKCS certificate profile (SCEP 証明書プロファイルの作成または PKCS 証明書プロファイルの作成)](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)」を参照してください)。各プロファイルには、DD/MM/YYYY 形式による有効期限を含む説明が必要です。 

    > [!CAUTION]
    > **有効期限のない証明書プロファイルは、展開されません。**

    > [!Note]
    > HoloLens 2 は、多くのユーザーが共有デバイス (つまり、デバイスごとに複数のユーザー) であると考えられるので、可能な限り、Wi-Fi 認証用のユーザー証明書の代わりにデバイス証明書を展開をお勧めします。

3.  社内ネットワーク用のプロファイルをWi-Fiします (「Windows 10 以降のデバイスの[Wi-Fi 設定」を参照)。](https://docs.microsoft.com/intune/wi-fi-settings-windows) ユーザープロファイルWi-Fi、組織内でプロキシ設定を使用する場合に選択できます。
 
    オプション:
    - **なし**: プロキシ設定は構成されていません。
    - **手動で構成**する: プロキシ サーバー **の IP アドレスとその** ポート番号 **を入力します**。
    - **自動構成**: プロキシ自動構成 (PAC) スクリプトを指す URL を入力します。 たとえば、と入力します *http://proxy.contoso.com/proxy.pac* 。

    PAC ファイルの詳細については [、「Proxy Auto-Configuration (PAC) ファイル (Microsoft](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) 以外のサイトを開く)」を参照してください。
 
    > [!Note]
    > Wi-Fi プロファイルは、可能であればユーザー グループではなくデバイス グループに割り当てることをお勧めします。
     
    > [!Tip]
    > また、企業ネットワーク上の Windows 10 PC から実行中の Wi-Fi プロファイルをエクスポートすることもできます。 このエクスポートでは、現在のすべての設定を含む XML ファイルが作成されます。 次に、このファイルを Intune にインポートして、HoloLens 2 デバイスの Wi-Fi プロファイルとして使用します。 [「Windows デバイスの設定をエクスポートWi-Fiインポートする」を参照してください](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)。

1.  [デバイス](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) プロファイルを HoloLens デバイス グループに割り当てる。

2.  Intune[でデバイス](https://docs.microsoft.com/mem/intune/configuration/device-profile-monitor)プロファイルを監視します。

デバイス プロファイルに問題がある場合Wi-Fi Intune のデバイス [構成Wi-Fiトラブルシューティングを参照してください](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)。

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Corp が接続されている場合の外部インターネット アクセスのトラブルシューティング
サービスが設定されたプロキシを経由しない場合、ファイアウォール経由で接続を試みる場合があります。 ファイアウォール ルールにエンドポイント固有の一覧を追加して、これらの問題のトラブルシューティングを行います。

ファイアウォール ポートでブロックされている場合は、HoloLens の一般的 [なエンドポイントを](https://docs.microsoft.com/hololens/hololens-offline) 有効にします。

また、ガイド固有のポートを有効にできます。このポートへの接続に必要なインターネット [アクセス可能な URL](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)Microsoft Dynamics CRM Online。

## <a name="app-deployment"></a>アプリの展開

MDM 経由で LOB アプリを展開する方法は、簡単に拡張性が高く、作成したグループに登録するとデバイスに自動的に展開できる方法です。

まだアプリを開発している場合、またはまだアプリを持っていない場合は、MRTK サンプル ハブのサンプル アプリを使用できます。 このサンプル アプリは使用する準備が整い、Unity やアプリの使用はVisual Studio。 [MRTK サンプル アプリをダウンロードします](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)。

独自のアプリを使用する場合や、Mixed Reality のアプリ開発に興味がある場合は、Mixed Reality 開発者向けドキュメントを自由に [確認してください](https://docs.microsoft.com/windows/mixed-reality/design/design)。

> [!NOTE]
> HoloLens デバイスのシステム要件は、アプリのビルドのアーキテクチャに基づいています。 HoloLens 2 デバイスは、ARMアーキテクチャを使用します。 アプリを Visual Studioする場合は、デバイスに適切なアーキテクチャを選択し、必要な依存関係を含める必要があります。

> [!IMPORTANT]
> LOB アプリを展開する場合は、証明書を Intune にアップロードし、アプリを使用するグループと同じグループに割り当てるか、正しくインストールされません。

### <a name="upload-and-assign-the-app"></a>アプリのアップロードと割り当て

1. MEM 管理センター [に移動します](https://endpoint.microsoft.com/#home)。

2. [アプリ **]**  ->  **[すべてのアプリ] を**選択し **、[+ 追加] ボタンを選択**します。

3. [その他] の下にある **[Line-of-business アプリ] を選択します**。 [選択 **] をクリックします**。

4. アプリ パッケージ ファイルを選択します。これは APPXBUNDLE ファイルか、この例の場合、アプリは _MRTK Examples Hub\_2.4.2.0\_arm\_Master.appxbundle_です。

5. 依存関係が見つからないという通知が表示されます。 この場合 _、Microsoft.VCLibs.ARM.14.00.appx をアップロードする必要があります_。 [ファイルの選択] **で検索します**。

6. [OK] を選択します。

7. 次の画面では、必要なフィールドが自動的に入力されます。 **[次へ]** を選択します。

8. [必須] で、以前に作成したグループを追加して、このアプリをグループに必要とします。 これにより、アプリはグループ内の登録済みデバイスに自動的にダウンロードされます。 **[次へ]** を選択します。

9. **[作成]** を選択します。

続きを読む: [Microsoft Intune のグループにアプリを割り当てる](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>セットアップ ガイド: アプリケーション ライセンス、dataverse、およびオーサリング

Dynamics 365 ガイドを使用するには、準備を行う必要があります。 準備が必要な領域は 3 つ。ユーザー、dataverse、およびガイド自体。

### <a name="users-and-application-licenses"></a>ユーザーとアプリケーション ライセンス

ガイドを使用するには、以前にこのガイドで設定した Azure AD アカウントを使用する必要があります。

また、作成したユーザーに Dynamics 365 Guides ライセンスを割り当てる必要があります。 これを行うには [、Microsoft 365 管理センターから行います](https://admin.microsoft.com/AdminPortal/Home)。 また、プライマリ Azure アカウントにライセンスを割り当てる。

アプリケーション [ライセンスの適用に関](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) する詳細な手順については、この短いガイドに従って写真を参照してください。

### <a name="set-up-the-dataverse"></a>Dataverse のセットアップ

実稼働環境 [をセットアップするには、2](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) つの前提条件を満たす必要があります。 システム管理者の役割[**が必要**](https://docs.microsoft.com/power-platform/admin/database-security)**で**[**、Power Apps**](https://docs.microsoft.com/power-platform/admin/signup-question-and-answer)ライセンス (または Power Apps ライセンスを含む[**Dynamics 365 Guides**](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)ライセンス) が必要です。 このガイドに従って Azure AD作成した場合は、システム管理者の役割要件を満たします。 また、前の手順でガイド ライセンスを割り当ててください。

このガイドでは [、Microsoft Dataverse 環境を作成します](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two)。

1. まず、Power Platform 管理センター [を使用し、](https://admin.powerplatform.microsoft.com/environments) 新しい環境を作成します。
2. 新しい環境 **を作成する**場合は、[種類] **で** [&#39;] を選択 **します**。
3. [この環境用にデータベースを作成 **する] を切り替える必要があります。**  オプションを  **[はい] に設定します**。
4. [データベースの  **追加] ダイアログ**  ボックスで  **、[Dynamics 365 アプリ**  を有効にする] オプションを [はい] に  **設定します。**

データバース内のアイテムの最大ファイル サイズを大きくする必要があります。 最大ファイル サイズを大きくすると、ガイドで後で使用する 3D モデルやビデオ ファイルをアップロードできます。 アップロード ファイルの最大サイズを [変更するには、短いガイドに従います](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)。

最後に、ソリューションをインストール [して構成する必要があります](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution)。 Power [Platform 管理センターで](https://admin.powerplatform.microsoft.com/environments)、[**** リソース Dynamics 365 アプリ] を選択し、一覧で   \ &gt; ******[Dynamics 365 Guides]** を選択し、[インストール] を**選択します**。  

アプリを [使用するには、ガイドの](https://docs.microsoft.com/dynamics365/mixed-reality/guides/assign-role) セキュリティ ロールを追加する必要があります。

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>オーサリングを介して PC でテスト ガイドを作成する

ガイドを作成する場合は、常に PC から開始します。 手順の作成、モデルの選択、およびガイドのアンカー方法。 その後、ガイドのコンテンツを後で HoloLens デバイスのオーサリング モードに配置します。 このガイドの目的のために、最小限の手順とモデルで短いテスト ガイドを作成してください。

ガイドの作成の学習を開始する場合は、ここからオーサリングの [概要を参照してください](https://docs.microsoft.com/dynamics365/mixed-reality/guides/authoring-overview)。 または、高速トラックの概要を取得するには、この短いビデオをご覧ください。

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>オプション: キオスク モード

キオスク モードは、IT 管理者がスタート メニューの UI を 1 つのアプリまたはアプリの選択のみを表示するモードです。 キオスクは、特定のユーザー、グループ、またはデバイス レベルにも適用できます。場合によっては、キオスクから特定のユーザーを除外して、通常のスタート メニューへのアクセスを許可します。

キオスク モードには、スコープと構成の両方で設定できるさまざまな変数と、HoloLens にキオスクを展開する方法があります。 これらすべての変数のために、キオスク モードは、このガイドのオプション__ として残され、再訪されません。 ビジネスで利用可能なアプリをユーザーに制限する必要がある場合、または詳細を知りたがっている場合は [、HoloLens](https://docs.microsoft.com/hololens/hololens-kiosk)をキオスクとして設定する方法を自由に学ぶ必要があります。

## <a name="optional-wdac"></a>オプション: WDAC

WDAC を使用すると、IT 管理者はデバイス上のアプリの起動をブロックするデバイスを構成できます。 これは、デバイス上のアプリを非表示にする UI がユーザーに表示されるキオスク モードなど、デバイス制限のメソッドとは異なりますが、起動することもできます。 WDAC が実装されている間、アプリは [すべてのアプリ] リストに表示されますが、WDAC はそれらのアプリとプロセスがデバイス ユーザーによって起動されるのを停止します。

詳細については、「Use WDAC and Windows PowerShell Microsoft Intune を使用して [HoloLens 2](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)デバイス上のアプリを許可またはブロックする」を参照してください。

[Windows Defender アプリケーション制御 - WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>次の手順 
> [!div class="nextstepaction"]
> [企業接続展開 - 展開](hololens2-corp-connected-deploy.md)