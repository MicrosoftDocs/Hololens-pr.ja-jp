---
title: 展開ガイド-企業接続 HoloLens 2 と Dynamics 365 ガイド-構成
description: Dynamics 365 ガイドを使用して、企業に接続されたネットワーク経由で HoloLens 2 デバイスを展開する構成を設定する方法について説明します。
keywords: HoloLens, 管理, 企業接続, Dynamics 365 ガイド, AAD, Azure AD, MDM, モバイルデバイス管理
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309102"
---
# <a name="configure---corporate-connected-guide"></a>構成-企業の接続ガイド

## <a name="azure-users-and-groups"></a>Azure のユーザーとグループ

その拡張機能による Azure および Intune では、ユーザーとグループを使用して、構成とライセンスを割り当てることができます。 このデプロイフローを検証し、ガイドを作成および操作できることを確認できるようにするには、ユーザーアカウントが必要&#39;ます。

ライセンスの割り当て専用に1つのユーザーグループを作成できます。

ユーザーグループ内の2つの Azure AD アカウントに既にアクセス権がある&#39;は、次のように使用できます。次に、のクイックスタートガイドを示します。

- [ユーザーを作成する方法](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [グループを作成する方法](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [グループへのユーザーの追加](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) –作成されたユーザーをグループの作成に追加する
- [ユーザーグループがデバイスを参加できるように Azure AD を構成](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) する–新しいユーザーグループにデバイスを登録するアクセス許可があることを確認し Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>HoloLens 2 での自動登録

スムーズでシームレスなエクスペリエンスを実現するために、Intune への Azure Active Directory 参加 (AADJ) と Intune への自動登録を設定する方法があります。 これにより、OOBE 中に組織のログイン資格情報を入力し、Azure AD に自動的に登録して、デバイスを MDM に登録できます。

[Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)を使用して、サービスを選択し、いくつかのページに移動して、[Premium 試用版を取得する] を選択できます。 自動登録 P1 には Azure Active Directory Premium 1 と2があることに注意してください。 Intune を選択し、自動登録のユーザースコープを選択して、以前に作成したグループを選択できます。

詳細と手順については、 [Intune の自動登録を有効にする方法](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)に関するガイドを参照してください。

## <a name="corporate-wi-fi-connectivity"></a>企業の Wi-Fi 接続

企業の Wi-Fi 接続では、HoloLens 2 を使用しているお客様に証明書ベースの認証が必要になることがよくあります。 このような証明書は、MDM ソリューションと統合された Simple Certificate Enrollment Protocol (SCEP) または公開キー暗号化標準 (PKCS) 証明書インフラストラクチャを使用して展開する必要があります。 Intune を使用して Wi-Fi プロファイル、証明書、およびプロキシ設定を展開すると、エンドユーザーにシームレスなエクスペリエンスが提供されます。
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>証明書と Wi-Fi プロファイルを展開する

Microsoft Endpoint Manager を使用して証明書とプロファイルを展開するには、次の手順を実行します。

1. ルート証明書と中間証明書のプロファイルを作成します (「 [信頼された証明書プロファイルの作成](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles)」を参照してください)。 これらの各プロファイルには、有効期限の日付が DD/MM/YYYY 形式で含まれている必要があります。 

    > [!CAUTION]
    > **有効期限のない証明書プロファイルは展開されません**。

2.  SCEP または PKCS 証明書ごとにプロファイルを作成します (「 [scep 証明書プロファイルの作成」または「pkcs 証明書プロファイルの作成](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)」を参照してください)。これらの各プロファイルには、有効期限が DD/MM/YYYY の形式で含まれている必要があります。 

    > [!CAUTION]
    > **有効期限のない証明書プロファイルは展開されません。**

    > [!Note]
    > HoloLens 2 は、多くのユーザーが共有デバイス (つまり、デバイスごとに複数のユーザー) と見なされるため、可能な限り Wi-Fi 認証用のユーザー証明書ではなく、デバイス証明書を展開することをお勧めします。

3.  企業の Wi-Fi ネットワークのプロファイルを作成します ( [Windows 10 以降のデバイスの wi-fi 設定](https://docs.microsoft.com/intune/wi-fi-settings-windows)を参照してください)。 Wi-Fi プロファイル内で、組織内でプロキシ設定を使用するように選択できます。
 
    次のようなオプションがあります。
    - **なし**: プロキシ設定は構成されません。
    - **[手動で構成する]** : **[プロキシ サーバーの IP アドレス]** とその **[ポート番号]** を入力します。
    - **[自動的に構成する]** : プロキシ自動構成 (PAC) スクリプトを指す URL を入力します。 たとえば、「 *http://proxy.contoso.com/proxy.pac* 」と入力します。

    PAC ファイルの詳細については、[プロキシ自動構成 (PAC) ファイル](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (Microsoft 外のサイトが開きます) に関するページを参照してください。
 
    > [!Note]
    > 可能な場合は、Wi-Fi プロファイルをユーザーグループではなくデバイスグループに割り当てることをお勧めします。
     
    > [!Tip]
    > 企業ネットワーク上の Windows 10 PC から、作業中の Wi-Fi プロファイルをエクスポートすることもできます。 このエクスポートによって、現在のすべての設定を含む XML ファイルが作成されます。 次に、このファイルを Intune にインポートし、HoloLens 2 デバイスの Wi-Fi プロファイルとして使用します。 [Windows デバイスの Wi-Fi 設定のエクスポートとインポート](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)に関するページをご覧ください。

1.  デバイスプロファイルを HoloLens デバイスグループに[割り当て](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)ます。

2.  Intune でデバイスプロファイルを[監視](https://docs.microsoft.com/mem/intune/configuration/device-profile-monitor)します。

Wi-Fi プロファイルに問題がある場合は、「 [Intune で Wi-Fi デバイス構成プロファイルをトラブルシューティング](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)する」を参照してください。

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Corp 接続時の外部インターネットアクセスのトラブルシューティング
サービスがセットプロキシを通過しない場合は、ファイアウォール経由で接続を試みることがあります。 ファイアウォール規則にエンドポイントの詳細の一覧を追加して、これらの問題のトラブルシューティングを行うことができます。

ファイアウォールポートでブロックされている場合は、HoloLens のいくつかの一般的な [エンドポイント](https://docs.microsoft.com/hololens/hololens-offline) を有効にします。

また、ガイドの特定のポートを有効にすることもできます。これは、 [Microsoft DYNAMICS CRM Online への接続に必要なインターネットアクセス可能な url](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)です。

## <a name="app-deployment"></a>アプリの展開

MDM を使用した LOB アプリのデプロイは、簡単にスケーラブルな方法であり、作成されたグループへの登録時にデバイスに自動的にデプロイできます。

まだアプリを開発している場合、またはまだインストールしていない場合は、MRTK サンプルハブのサンプルアプリを使用できます。 このサンプルアプリは使用する準備ができており、Unity または Visual Studio を使用する必要はありません。 [MRTK サンプルアプリをダウンロード](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)します。

独自のアプリを使用する場合、または混合現実のアプリ開発に関心がある場合は、 [Mixed reality 開発者](https://docs.microsoft.com/windows/mixed-reality/design/design)向けのドキュメントをぜひお読みください。

> [!NOTE]
> HoloLens デバイスのシステム要件は、アプリビルドのアーキテクチャに基づいています。 HoloLens 2 デバイスは ARM アーキテクチャを使用します。 Visual Studio でアプリをビルドする場合は、デバイスの正しいアーキテクチャを選択していること、および必要な依存関係が含まれていることを確認してください。

> [!IMPORTANT]
> LOB アプリを展開する場合は、Intune に証明書をアップロードし、アプリを使用することを目的とした同じグループに割り当てることが重要です。そうしないと、正常にインストールされません。

### <a name="upload-and-assign-the-app"></a>アプリをアップロードして割り当てる

1. [メモリ管理センター](https://endpoint.microsoft.com/#home)に移動します。

2. [**アプリ**] [  ->  **すべてのアプリ**] を選択し、[ **+ 追加**] ボタンを選択します。

3. [その他] の下で、[ **基幹業務アプリ**] を選択します。 [ **選択] を** クリックします。

4. アプリパッケージファイルを選択します。これは、.APPXBUNDLE ファイルです。この例の場合、アプリは _Mrtk Example Hub \_ 2.4.2.0 \_ arm \_ マスターです_。

5. 依存関係が不足していることが通知されます。 このような場合は、 _v14.00_ をアップロードする必要があります。 [ **ファイルの選択]** で検索します。

6. [OK] を選択します。

7. 次の画面では、必須フィールドは自動入力されます。 **[次へ]** を選択します。

8. [必須] で、以前に作成したグループを追加して、このアプリがグループに必要なようにします。 これにより、アプリはグループ内の登録済みデバイスに自動的にダウンロードされます。 **[次へ]** を選択します。

9. **［作成］** を選択します

詳細: [Microsoft Intune のグループにアプリを割り当てる](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>セットアップガイド: アプリケーションライセンス、dataverse 定型文、作成

Dynamics 365 ガイドを使用するには、いくつかの準備を行う必要があります。 次の3つの領域を準備する必要があります。ユーザー、dataverse 定型文、およびガイド自体。

### <a name="users-and-application-licenses"></a>ユーザーとアプリケーションのライセンス

他のユーザーがガイドを使用するには、以前にこのガイドで設定した Azure AD アカウントを使用する必要があります。

また、作成したユーザーに Dynamics 365 ガイドのライセンスを割り当てる必要もあります。 これを行うには [Microsoft 365 管理センター](https://admin.microsoft.com/AdminPortal/Home)を使用します。 また、ライセンスをプライマリ Azure アカウントに割り当てます。

アプリケーションライセンスを適用するための詳細な手順については、こちらの [簡単なガイド](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) に従ってください。

### <a name="set-up-the-dataverse"></a>Dataverse 定型文を設定する

[運用環境](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only)をセットアップするには、2つの前提条件を満たす必要があります。 [**システム管理者**](https://docs.microsoft.com/power-platform/admin/database-security)**ロールを持っ** ている必要があります。また、 [**power apps ライセンス**](https://docs.microsoft.com/power-platform/admin/signup-question-and-answer)(または、power Apps ライセンスを含む [**Dynamics 365 ガイドライセンス**](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)) が必要です。 このガイドに従って Azure AD を作成した場合は、システム管理者の役割要件を満たしている必要があります。 また、前の手順では、ガイドライセンスが割り当てられています。

このガイドで [は、Microsoft Dataverse 定型文環境を作成](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two)します。

1. まず、 [Power Platform 管理センター](https://admin.powerplatform.microsoft.com/environments) を使用して、新しい環境を作成します。
2. **新しい環境** を作成するときに、[**種類**] に [**運用**] を選択する&#39;ます。
3. **この環境のデータベースの作成** を切り替えることが重要ですか。  **[はい]** を選択します。
4. [**データベースの追加**] ダイアログボックスで、[ **Dynamics 365 アプリを有効に** する] オプションを **[はい]** に設定します。

Dataverse に含まれる項目の最大ファイルサイズを増やす必要があります。 ファイルの最大サイズを大きくすると、後でガイドで使用する大きな3D モデルやビデオファイルをアップロードできます。 短いガイドに従っ [て、アップロードファイルの最大サイズを変更](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)します。

最後に、 [ソリューションをインストールして構成](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution)する必要があります。 [Power Platform 管理センター](https://admin.powerplatform.microsoft.com/environments)で、[**リソース**] > を選択し \& ます。 **Dynamics 365 アプリ** の場合は、一覧で [ **Dynamics 365 のガイド**] を選択し、[**インストール**] を選択します。  

アプリを使用できるようにするには、[ [ガイドの追加」セキュリティロール](https://docs.microsoft.com/dynamics365/mixed-reality/guides/assign-role) が必要です。

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>オーサリングを使用した PC でのテストガイドの作成

ガイドを作成するときは、常に PC で開始されます。 手順の作成、モデルの選択、およびガイドの固定方法。 これに続いて、後で HoloLens デバイスのオーサリングモードで、ガイドのコンテンツを配置します。 このガイドでは、最小限の手順とモデルで簡単なテストガイドを作成することをお勧めします。

ガイドの作成について学習を開始する場合は、 [作成の概要](https://docs.microsoft.com/dynamics365/mixed-reality/guides/authoring-overview)に関するページを参照してください。 または、こちらの短いビデオをご覧ください。

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>省略可能: キオスクモード

キオスクモードは、IT 管理者が、1つのアプリまたは選択したアプリのみを表示するように [スタート] メニューの UI を構成できるモードです。 キオスクは、特定のユーザー、グループ、またはデバイスレベルにも適用できます。場合によっては、キオスクから特定のユーザーを除外しても、通常の [スタート] メニューへのアクセスを許可することがあります。

キオスクモードには、設定可能なスコープと構成の両方と、HoloLens にキオスクをデプロイする方法の両方で、さまざまな変数があります。 これらのすべての変数により、キオスクモードはこのガイドでは _省略可能_ として残されており、再検討されません。 利用可能なアプリをユーザーに制限する必要があると思われる場合や、さらに学習する必要がある場合は、 [HoloLens をキオスクとしてセットアップ](https://docs.microsoft.com/hololens/hololens-kiosk)する方法を自由に確認してください。

## <a name="optional-wdac"></a>省略可能: WDAC

WDAC を使用すると、IT 管理者は、デバイスでのアプリの起動をブロックするようにデバイスを構成できます。 これは、デバイスの制限の方法 (キオスクモードなど) とは異なり、デバイス上のアプリを非表示にする UI がユーザーに表示されますが、それでも起動できます。 WDAC が実装されている場合でも、アプリは [すべてのアプリ] の一覧に表示されますが、WDAC はデバイスユーザーがこれらのアプリとプロセスを起動できなくなります。

詳細については、「 [WDAC および Windows PowerShell を使用して、Microsoft Intune で HoloLens 2 デバイス上のアプリを許可またはブロックする」を](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)参照してください。

[Windows Defender アプリケーション制御-WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>次のステップ 
> [!div class="nextstepaction"]
> [企業に接続された展開-デプロイ](hololens2-corp-connected-deploy.md)