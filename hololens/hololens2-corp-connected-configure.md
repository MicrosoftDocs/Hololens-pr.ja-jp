---
title: 展開ガイド-Dynamics 365 Guides 構成を使用した企業接続 HoloLens 2
description: Dynamics 365 Guides を使用して、企業に接続されたネットワーク経由で HoloLens 2 デバイスを展開する構成を設定する方法について説明します。
keywords: HoloLens、管理、企業接続、Dynamics 365 Guides、AAD、Azure AD、MDM、モバイルデバイス管理
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
ms.openlocfilehash: 9457acd2f53d0d3127d6c68d620b660f6e09866d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637083"
---
# <a name="configure---corporate-connected-guide"></a>構成-企業の接続ガイド

## <a name="azure-users-and-groups"></a>Azure のユーザーとグループ

その拡張機能による Azure および Intune では、ユーザーとグループを使用して、構成とライセンスを割り当てることができます。 このデプロイフローを検証し、ガイドを作成および操作できることを確認できるようにするには、ユーザーアカウントが必要&#39;ます。

ライセンスの割り当て専用に1つのユーザーグループを作成できます。

ユーザーグループ内の2つの Azure AD アカウントに既にアクセス権がある&#39;は、次のように使用できます。次に、のクイックスタートガイドを示します。

- [ユーザーを作成する方法](/mem/intune/fundamentals/quickstart-create-user)
- [グループを作成する方法](/mem/intune/fundamentals/quickstart-create-group)
- [グループへのユーザーの追加](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) –作成されたユーザーをグループの作成に追加する
- [ユーザーグループがデバイスを参加できるように Azure AD を構成](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) する–新しいユーザーグループにデバイスを登録するアクセス許可があることを確認し Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>HoloLens 2 での自動登録

スムーズでシームレスなエクスペリエンスを実現するために、HoloLens 2 デバイスに対して Azure Active Directory Join (aadj) と Intune への自動登録を設定する方法があります。 これにより、OOBE 中に組織のログイン資格情報を入力し、Azure AD に自動的に登録して、デバイスを MDM に登録できます。

[Microsoft エンドポイントマネージャー](https://endpoint.microsoft.com/#home)を使用すると、サービスを選択し、[Get a プレミアム試用版] を選択するまでいくつかのページに移動できます。 自動登録 P1 には Azure Active Directory Premium 1 と2があることに注意してください。 Intune を選択し、自動登録のユーザースコープを選択して、以前に作成したグループを選択できます。

詳細と手順については、 [Intune の自動登録を有効にする方法](/mem/intune/enrollment/quickstart-setup-auto-enrollment)に関するガイドを参照してください。

## <a name="corporate-wi-fi-connectivity"></a>企業の Wi-Fi 接続

企業の Wi-Fi 接続では、通常、HoloLens 2 を使用するお客様に証明書ベースの認証が必要になります。 このような証明書は、MDM ソリューションと統合された Simple Certificate Enrollment Protocol (SCEP) または公開キー暗号化標準 (PKCS) 証明書インフラストラクチャを使用して展開する必要があります。 Intune を使用して Wi-Fi プロファイル、証明書、およびプロキシ設定を展開すると、エンドユーザーにシームレスなエクスペリエンスが提供されます。
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>証明書と Wi-Fi プロファイルを展開する

Microsoft エンドポイントマネージャー経由で証明書とプロファイルを展開するには、次の手順を実行します。

1. ルート証明書と中間証明書のプロファイルを作成します (「 [信頼された証明書プロファイルの作成](/intune/protect/certificates-configure#create-trusted-certificate-profiles)」を参照してください)。 これらの各プロファイルには、有効期限の日付が DD/MM/YYYY 形式で含まれている必要があります。

    > [!CAUTION]
    > **有効期限のない証明書プロファイルは展開されません**。

2. SCEP または PKCS 証明書ごとにプロファイルを作成します (「 [scep 証明書プロファイルの作成」または「pkcs 証明書プロファイルの作成](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)」を参照してください)。これらの各プロファイルには、有効期限が DD/MM/YYYY の形式で含まれている必要があります。

    > [!CAUTION]
    > **有効期限のない証明書プロファイルは展開されません。**

    > [!Note]
    > HoloLens 2 は、多くのユーザーが共有デバイス (つまり、デバイスごとに複数のユーザー) と見なされるため、可能な限り Wi-Fi 認証用のユーザー証明書ではなく、デバイス証明書を展開することをお勧めします。

3. 企業の Wi-Fi ネットワークのプロファイルを作成します ( [Windows 10 以降のデバイスの wi-fi 設定を](/intune/wi-fi-settings-windows)参照してください)。 Wi-Fi プロファイル内で、組織内でプロキシ設定を使用するように選択できます。

    次のようなオプションがあります。
    - **なし**: プロキシ設定は構成されません。
    - **[手動で構成する]** : **[プロキシ サーバーの IP アドレス]** とその **[ポート番号]** を入力します。
    - **[自動的に構成する]** : プロキシ自動構成 (PAC) スクリプトを指す URL を入力します。 たとえば、「 *http://proxy.contoso.com/proxy.pac* 」と入力します。

    PAC ファイルの詳細については、[プロキシ自動構成 (PAC) ファイル](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (Microsoft 外のサイトが開きます) に関するページを参照してください。
 
    > [!Note]
    > 可能な場合は、Wi-Fi プロファイルをユーザーグループではなくデバイスグループに割り当てることをお勧めします。
     
    > [!Tip]
    > また、会社のネットワークの Windows 10 PC から、作業中の Wi-Fi プロファイルをエクスポートすることもできます。 このエクスポートによって、現在のすべての設定を含む XML ファイルが作成されます。 次に、このファイルを Intune にインポートし、HoloLens 2 デバイスの Wi-Fi プロファイルとして使用します。 [Windows デバイスの Wi-Fi 設定のエクスポートとインポート](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)に関するページをご覧ください。

1.  デバイスプロファイルを HoloLens デバイスグループに[割り当て](/mem/intune/configuration/device-profile-assign)ます。

2.  Intune でデバイスプロファイルを[監視](/mem/intune/configuration/device-profile-monitor)します。

Wi-Fi プロファイルに問題がある場合は、「 [Intune で Wi-Fi デバイス構成プロファイルをトラブルシューティング](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)する」を参照してください。

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Corp 接続時の外部インターネットアクセスのトラブルシューティング
サービスがセットプロキシを通過しない場合は、ファイアウォール経由で接続を試みることがあります。 ファイアウォール規則にエンドポイントの詳細の一覧を追加して、これらの問題のトラブルシューティングを行うことができます。

ファイアウォールポートでブロックされている場合は、HoloLens に対していくつかの一般的な[エンドポイント](/hololens/hololens-offline)を有効にします。

また、ガイドの特定のポートを有効にすることもできます。 [Microsoft Dynamics CRM Online に接続するために必要なインターネットアクセス可能な url](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)です。

## <a name="app-deployment"></a>アプリの展開

MDM を使用した LOB アプリのデプロイは、簡単にスケーラブルな方法であり、作成されたグループへの登録時にデバイスに自動的にデプロイできます。

まだアプリを開発している場合、またはまだインストールしていない場合は、MRTK サンプルハブのサンプルアプリを使用できます。 このサンプルアプリは使用する準備ができており、Unity と Visual Studio のどちらも使用する必要がありません。 [MRTK サンプルアプリをダウンロード](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)します。

独自のアプリを使用する場合、または混合現実のアプリ開発に関心がある場合は、 [Mixed reality 開発者](/windows/mixed-reality/design/design)向けのドキュメントをぜひお読みください。

> [!NOTE]
> HoloLens デバイスのシステム要件は、アプリビルドのアーキテクチャに基づいています。 HoloLens 2 デバイスは ARM アーキテクチャを使用します。 Visual Studio でアプリをビルドするときは、デバイスに適したアーキテクチャを選択し、必要な依存関係を含めるようにしてください。

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

詳細: [Microsoft Intune のグループにアプリを割り当てる](/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>セットアップガイド: アプリケーションライセンス、dataverse 定型文、作成

Dynamics 365 Guides を使用するには、いくつかの準備を行う必要があります。 次の3つの領域を準備する必要があります。ユーザー、dataverse 定型文、およびガイド自体。

### <a name="users-and-application-licenses"></a>ユーザーとアプリケーションのライセンス

他のユーザーがガイドを使用するには、以前にこのガイドで設定した Azure AD アカウントを使用する必要があります。

また、作成したユーザーに Dynamics 365 Guides ライセンスを割り当てる必要があります。 これを行うには、 [Microsoft 365 管理センター](https://admin.microsoft.com/AdminPortal/Home)を使用します。 また、ライセンスをプライマリ Azure アカウントに割り当てます。

アプリケーションライセンスを適用するための詳細な手順については、こちらの [簡単なガイド](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) に従ってください。

### <a name="set-up-the-dataverse"></a>Dataverse 定型文を設定する

[運用環境](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only)をセットアップするには、2つの前提条件を満たす必要があります。 [**システム管理者**](/power-platform/admin/database-security)**ロールを持っ** ている必要があります。また、 [**Power Apps ライセンス**](/power-platform/admin/signup-question-and-answer)(または、Power Apps ライセンスを含む [**Dynamics 365 Guides ライセンス**](/dynamics365/mixed-reality/guides/setup-step-one)) が必要です。 このガイドに従って Azure AD を作成した場合は、システム管理者の役割要件を満たしている必要があります。 また、前の手順では、ガイドライセンスが割り当てられています。

このガイドで [は、Microsoft Dataverse 定型文環境を作成](/dynamics365/mixed-reality/guides/setup-step-two)します。

1. まず、 [Power Platform 管理センター](https://admin.powerplatform.microsoft.com/environments) を使用して、新しい環境を作成します。
2. **新しい環境** を作成するときに、[**種類**] に [**運用**] を選択する&#39;ます。
3. **この環境のデータベースの作成** を切り替えることが重要ですか。  **[はい]** を選択します。
4. [**データベースの追加**] ダイアログボックスで、[ **Dynamics 365 アプリを有効に** する] オプションを **[はい]** に設定します。

データバース内の項目の最大ファイル サイズを増やす必要があります。 最大ファイル サイズを大きくすると、より大きな 3D モデルまたはビデオ ファイルをアップロードできます。このファイルは、後でガイドで使用します。 アップロード ファイルの最大サイズを [変更するには、短いガイドに従ってください](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)。

最後に、ソリューション をインストールして [構成する必要があります](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution)。 [リソース] [Power Platform 管理センター](https://admin.powerplatform.microsoft.com/environments)リソース gt;**を** \& 選択します。 **Dynamics 365 アプリ**: 一 **覧Dynamics 365 Guides** を選択し、 [インストール] を **選択します**。  

アプリを [使用するには、ガイド セキュリティ ロール](/dynamics365/mixed-reality/guides/assign-role) を追加する必要があります。

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Authoring を使用して PC にテスト ガイドを作成する

ガイドを作成する場合は、常に PC から開始します。 手順の作成、モデルの選択、ガイドの固定方法。 その後、後でガイドのコンテンツを作成モードでデバイスに配置HoloLensされます。 このガイドの目的のために、最小限の手順とモデルで簡単なテスト ガイドを作成する方法をお勧めしています。

ガイドの作成について学習する場合は、オーサリングの概要から [始める必要があります](/dynamics365/mixed-reality/guides/authoring-overview)。 または、高速トラックの概要を取得するには、この短いビデオをご覧ください。

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>省略可能: キオスク モード

キオスク モードは、IT 管理者が 1 つのアプリまたはアプリの選択のみを表示するためにスタート メニューの UI を構成するモードです。 キオスクは、特定のユーザー、グループ、またはデバイス レベルでも適用できます。場合によっては、キオスクから特定のユーザーを除外して、通常のスタート メニューへのアクセスを許可します。

キオスク モードには多くの異なる変数があります。スコープと構成の両方で設定できるだけでなく、キオスクを展開する方法HoloLens。 これらすべての変数により、キオスク モードはこのガイドでは省略可能な形式で残され、再検討されません。 利用可能なアプリをユーザーに制限するビジネス上の必要性がある場合、または詳細を確認する必要がある場合は、キオスク として HoloLens を設定する方法を自由に[学習してください](/hololens/hololens-kiosk)。

## <a name="optional-wdac"></a>省略可能: WDAC

WDAC を使用すると、IT 管理者はデバイスでのアプリの起動をブロックするデバイスを構成できます。 これは、キオスク モードなどのデバイス制限の方法とは異なります。この場合、ユーザーにはデバイス上のアプリを非表示にする UI が表示されますが、起動することもできます。 WDAC が実装されている間、アプリは [すべてのアプリ] の一覧に引き続き表示されますが、WDAC では、これらのアプリとプロセスがデバイス ユーザーによって起動されるのを停止します。

詳細については、「WDAC とデバイスを使用Windows PowerShellを使用して、 がインストールされているデバイス上のアプリを許可HoloLens 2[ブロックMicrosoft Intune。](/mem/intune/configuration/custom-profile-hololens)

[Windows Defender アプリケーション制御 - WDAC](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>次のステップ 
> [!div class="nextstepaction"]
> [企業に接続されたデプロイ - デプロイ](hololens2-corp-connected-deploy.md)