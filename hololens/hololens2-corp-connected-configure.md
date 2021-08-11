---
title: デプロイ ガイド - 企業接続HoloLens 2 Dynamics 365 Guides - 構成
description: デバイスを展開する構成を設定して、HoloLens 2を使用して企業の接続済みネットワーク上に展開する方法Dynamics 365 Guides。
keywords: HoloLens、管理、企業接続、Dynamics 365 Guides、AAD、Azure AD、MDM、Mobile デバイス管理
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
ms.openlocfilehash: 2b855f5891dfa4ca695e4ae3b2a2e82510c5b626f08b434643169be239b48291
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660189"
---
# <a name="configure---corporate-connected-guide"></a>構成 - 企業接続ガイド

## <a name="azure-users-and-groups"></a>Azure ユーザーとグループ

その拡張機能による Azure と Intune では、ユーザーとグループを使用して構成とライセンスの割り当てに役立ちます。 このデプロイ フローを検証し、ガイドを作成して操作&#39;確認するために、ユーザー アカウントが必要になります。

ライセンスの割り当て専用に 1 つのユーザー グループを作成できます。

ユーザー グループ内&#39;2 つのアカウントAzure ADまだアクセスできない場合は、次のコマンドを使用できます。次に示すのは、以下のクイック スタート ガイドです。

- [ユーザーを作成する方法](/mem/intune/fundamentals/quickstart-create-user)
- [グループを作成する方法](/mem/intune/fundamentals/quickstart-create-group)
- [グループにユーザーを追加する](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – 作成したユーザーを追加してグループを作成する
- [ユーザー Azure ADデバイスへの参加を](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) 許可するユーザー グループを構成する – 新しいユーザー グループにデバイスを登録するアクセス許可が付与Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>[自動登録] (HoloLens 2

スムーズでシームレスなエクスペリエンスを実現するには、Azure Active Directory デバイス用に Azure Active Directory Join (AADJ) と HoloLens 2 Intune への自動登録を設定します。 これにより、ユーザーは OOBE 中に組織のログイン資格情報を入力し、Azure AD に自動的に登録し、デバイスを MDM に登録できます。

を使用[Microsoft エンドポイント マネージャー](https://endpoint.microsoft.com/#home)サービスを選択し、[無料試用版を取得する] を選択するまで、いくつかのページプレミアムできます。 1 と 2 のAzure Active Directory Premiumがある場合があります。自動登録 P1 で十分です。 Intune を選択し、自動登録のユーザー スコープを選択し、以前に作成したグループを選択できます。

詳細と手順については、Intune の自動登録を有効 [にする方法に関するガイドを参照してください](/mem/intune/enrollment/quickstart-setup-auto-enrollment)。

## <a name="corporate-wi-fi-connectivity"></a>企業Wi-Fi接続

企業Wi-Fi接続では、通常、証明書ベースの認証を使用しているお客様にHoloLens 2。 このような証明書は、MDM ソリューションと統合された Simple Certificate Enrollment Protocol (SCEP) または公開キー暗号化標準 (PKCS) 証明書インフラストラクチャを使用して展開する必要があります。 Intune を使用してWi-Fi、証明書、プロキシ設定を展開すると、エンド ユーザーにシームレスなエクスペリエンスが作成されます。
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>証明書と証明書プロファイルWi-Fi展開する

証明書とプロファイルを展開するには、次Microsoft エンドポイント マネージャー手順に従います。

1. ルート証明書と中間証明書ごとにプロファイルを作成します (「信頼された証明書プロファイルを作成 [する」を参照してください](/intune/protect/certificates-configure#create-trusted-certificate-profiles))。 これらの各プロファイルには、DD/MM/YYYY 形式の有効期限を含む説明が必要です。

    > [!CAUTION]
    > **有効期限のない証明書プロファイルは展開されません**。

2. SCEP 証明書または PKCS 証明書のそれぞれにプロファイルを作成します ([「SCEP 証明書プロファイルの作成」または「PKCS 証明書プロファイルの作成」](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)を参照してください)。各プロファイルには、DD/MM/YYYY 形式による有効期限を含む説明が必要です。

    > [!CAUTION]
    > **有効期限のない証明書プロファイルは、展開されません。**

    > [!Note]
    > HoloLens 2 は共有デバイスと見なされます。つまり、デバイスごとに複数のユーザーを使用する場合は、可能であれば、Wi-Fi 認証用のユーザー証明書ではなく、デバイス証明書を展開してください。

3. 企業ネットワーク用のプロファイルを作成Wi-Fiネットワークの Wi-Fi 設定に関するページWindows 10[を参照してください](/intune/wi-fi-settings-windows))。 プロファイル内Wi-Fi組織内でプロキシ設定を使用する場合に選択できます。

    次のようなオプションがあります。
    - **なし**: プロキシ設定は構成されません。
    - **[手動で構成する]** : **[プロキシ サーバーの IP アドレス]** とその **[ポート番号]** を入力します。
    - **[自動的に構成する]** : プロキシ自動構成 (PAC) スクリプトを指す URL を入力します。 たとえば、「 *http://proxy.contoso.com/proxy.pac* 」と入力します。

    PAC ファイルの詳細については、[プロキシ自動構成 (PAC) ファイル](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (Microsoft 外のサイトが開きます) に関するページを参照してください。
 
    > [!Note]
    > Wi-Fi プロファイルは、可能であればユーザー グループではなくデバイス グループに割り当て済みにすることをお勧めします。
     
    > [!Tip]
    > また、企業ネットワーク上の Windows 10 PC から実行中の Wi-Fi プロファイルをエクスポートすることもできます。 このエクスポートでは、現在のすべての設定を含む XML ファイルが作成されます。 次に、このファイルを Intune にインポートして、HoloLens 2 デバイスの Wi-Fi プロファイルとして使用します。 [Windows デバイスの Wi-Fi 設定のエクスポートとインポート](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)に関するページをご覧ください。

1.  [デバイス](/mem/intune/configuration/device-profile-assign)プロファイルをデバイス グループのHoloLens割り当てる。

2.  Intune[でデバイス](/mem/intune/configuration/device-profile-monitor)プロファイルを監視します。

デバイス プロファイルに問題がある場合Wi-Fi Intune でのデバイス構成 [Wi-Fiのトラブルシューティングに関するページを参照してください](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)。

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Corp 接続時の外部インターネット アクセスのトラブルシューティング
サービスが設定されたプロキシを経由しない場合は、ファイアウォール経由で接続を試みる場合があります。 これらの問題をトラブルシューティングするために、ファイアウォール規則にエンドポイント固有の一覧を追加できます。

ファイアウォール ポートでブロックされている場合は、一般的なエンドポイント[](/hololens/hololens-offline)の一部を有効HoloLens。

また、ガイド固有のポートを有効にできます。 への接続に必要なインターネットにアクセスできる[URL](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)Microsoft Dynamics CRM Online。

## <a name="app-deployment"></a>アプリの展開

MDM を使用した LOB アプリのデプロイは、簡単にスケーラブルな方法であり、作成されたグループへの登録時にデバイスに自動的に展開できます。

まだアプリを開発している場合、またはアプリがまだない場合は、MRTK サンプル ハブのサンプル アプリを使用できます。 このサンプル アプリは使用する準備が整い、Unity または Visual Studio を使用する必要はありません。 [MRTK サンプル サンプル アプリ をダウンロードします](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)。

独自のアプリを使用する場合、または Mixed Reality 用のアプリ開発に関心がある場合は、開発者向けドキュメントをMixed Reality [してください](/windows/mixed-reality/design/design)。

> [!NOTE]
> HoloLens デバイスのシステム要件は、アプリのビルドのアーキテクチャに基づいています。 HoloLens 2は ARM アーキテクチャを使用します。 Visual Studio でアプリを構築する場合は、デバイスに適切なアーキテクチャを選択し、必要な依存関係を含める必要があります。

> [!IMPORTANT]
> LOB アプリを展開する場合は、証明書も Intune にアップロードし、アプリを使用することを目的とした同じグループに割り当てるか、正しくインストールされません。

### <a name="upload-and-assign-the-app"></a>アップロードの作成と割り当て

1. MEM 管理センター [に移動します](https://endpoint.microsoft.com/#home)。

2. [アプリ **]**  ->  **[すべてのアプリ]** を選択し **、[+ 追加] ボタンを選択** します。

3. [その他] の下にある **[Line-of-business app] を選択します**。 [] を **クリックします**。

4. アプリ パッケージ ファイルを選択します。これは APPXBUNDLE ファイルです。この例では、アプリは _MRTK Examples Hub \_ 2.4.2.0 \_ arm \_ Master.appxbundle_ です。

5. 依存関係が見つからないという通知が表示されます。 この場合は _、Microsoft.VCLibs.ARM.14.00.appx をアップロードする必要があります_。 [ファイルの選択] **で検索します**。

6. [OK] を選択します。

7. 次の画面では、必要なフィールドが自動的に入力されます。 **[次へ]** を選択します。

8. [必須] で、以前に作成したグループを追加して、このアプリをグループに必要とします。 これにより、アプリはグループ内の登録済みデバイスに自動的にダウンロードされます。 **[次へ]** を選択します。

9. **[作成]** を選択します。

詳細については、以下を参照[してください。アプリをグループに割り当Microsoft Intune](/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>セットアップ ガイド: アプリケーション ライセンス、データバース、および作成

アプリケーションを使用Dynamics 365 Guides、いくつかの準備を行う必要があります。 次の 3 つの領域を準備する必要があります。ユーザー、データバース、およびガイド自体。

### <a name="users-and-application-licenses"></a>ユーザーとアプリケーション ライセンス

ガイドを使用するには、前にこのガイドで設定した Azure AD アカウントを使用する必要があります。

また、作成したユーザーにDynamics 365 Guidesライセンスを割り当てる必要があります。 この操作は、 から行[Microsoft 365 管理センター。](https://admin.microsoft.com/AdminPortal/Home) また、プライマリ Azure アカウントにライセンスを割り当てる。

アプリケーション [ライセンスの適用に関](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) する詳細な手順については、この短いガイドに従ってください。

### <a name="set-up-the-dataverse"></a>Dataverse を設定する

実稼働環境 [を設定するには、2](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) つの前提条件を満たす必要があります。 システム管理者ロールを [](/power-platform/admin/database-security)持っている必要があります。また、Power Apps ライセンス [**(または**](/power-platform/admin/signup-question-and-answer)Dynamics 365 Guidesライセンスを [](/dynamics365/mixed-reality/guides/setup-step-one)含む Power Apps ライセンスが必要です。 このガイドに従ってアプリケーションを作成Azure AD、システム管理者のロール要件を満たします。 また、前の手順でガイド ライセンスを割り当てしました。

このガイドでは [、Microsoft Dataverse 環境を作成します](/dynamics365/mixed-reality/guides/setup-step-two)。

1. まず、新しい環境 [Power Platform 管理センター](https://admin.powerplatform.microsoft.com/environments) 新しい環境を作成します。
2. [新しい環境 **] を作成** するときに、[種類] **に対して** [&#39;] を選択 **します**。
3. [この環境用にデータベースを **作成する] を切り替える必要がありますか?**  オプションを [はい  **] に設定します**。
4. [データベースの  **追加] ダイアログ**  ボックスで  **、[Dynamics 365**  アプリを有効にする] オプションを [はい] に  **設定します。**

Dataverse に含まれる項目の最大ファイルサイズを増やす必要があります。 ファイルの最大サイズを大きくすると、後でガイドで使用する大きな3D モデルやビデオファイルをアップロードできます。 短いガイドに従っ [て、アップロードファイルの最大サイズを変更](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)します。

最後に、 [ソリューションをインストールして構成](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution)する必要があります。 [Power Platform 管理センター](https://admin.powerplatform.microsoft.com/environments)で、[**リソース**] > を選択し \& ます。 **Dynamics 365 アプリ** の場合は、一覧で [ **Dynamics 365 Guides** ] を選択し、[**インストール**] を選択します。  

アプリを使用できるようにするには、[ [ガイドの追加」セキュリティロール](/dynamics365/mixed-reality/guides/assign-role) が必要です。

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>オーサリングを使用した PC でのテストガイドの作成

ガイドを作成するときは、常に PC で開始されます。 手順の作成、モデルの選択、およびガイドの固定方法。 その後、HoloLens デバイスのオーサリングモードで、後でガイドのコンテンツを配置します。 このガイドでは、最小限の手順とモデルで簡単なテストガイドを作成することをお勧めします。

ガイドの作成について学習を開始する場合は、 [作成の概要](/dynamics365/mixed-reality/guides/authoring-overview)に関するページを参照してください。 または、こちらの短いビデオをご覧ください。

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>省略可能: キオスクモード

キオスクモードは、IT 管理者が、1つのアプリまたは選択したアプリのみを表示するように [スタート] メニューの UI を構成できるモードです。 キオスクは、特定のユーザー、グループ、またはデバイスレベルにも適用できます。場合によっては、キオスクから特定のユーザーを除外しても、通常の [スタート] メニューへのアクセスを許可することがあります。

キオスクモードには、設定可能なスコープと構成の両方と、キオスクを HoloLens に展開する方法の両方のさまざまな変数があります。 これらのすべての変数により、キオスクモードはこのガイドでは _省略可能_ として残されており、再検討されません。 利用可能なアプリをユーザーに制限する必要があると思われる場合や、さらに学習する必要がある場合は、 [HoloLens をキオスクとしてセットアップ](/hololens/hololens-kiosk)する方法を自由に習得してください。

## <a name="optional-wdac"></a>省略可能: WDAC

WDAC を使用すると、IT 管理者は、デバイスでのアプリの起動をブロックするようにデバイスを構成できます。 これは、デバイスの制限の方法 (キオスクモードなど) とは異なり、デバイス上のアプリを非表示にする UI がユーザーに表示されますが、それでも起動できます。 WDAC が実装されている場合でも、アプリは [すべてのアプリ] の一覧に表示されますが、WDAC はデバイスユーザーがこれらのアプリとプロセスを起動できなくなります。

詳細については、「 [WDAC と Windows PowerShell を使用して Microsoft Intune で HoloLens 2 デバイス上のアプリを許可またはブロックする」を](/mem/intune/configuration/custom-profile-hololens)参照してください。

[Windows Defender アプリケーション制御 - WDAC](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>次のステップ 
> [!div class="nextstepaction"]
> [企業に接続された展開-デプロイ](hololens2-corp-connected-deploy.md)