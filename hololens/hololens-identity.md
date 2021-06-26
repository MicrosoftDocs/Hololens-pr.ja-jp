---
title: HoloLens のユーザー ID とサインインを管理する
description: HoloLens デバイスのユーザー ID、マルチユーザー サポート、セキュリティ、エンタープライズ認証、サインインを管理する方法について説明します。
keywords: HoloLens, ユーザー, アカウント, AAD, Azure AD, adfs, microsoft アカウント, msa, 資格情報, リファレンス
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: scooley
ms.author: scooley
ms.date: 10/6/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: fbef357053900f6495cb59f52cba8669f0d0a3db
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924419"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>HoloLens のユーザー ID とサインインを管理する

> [!NOTE]
> この記事は、IT 技術者と技術技術者向けテクニカル リファレンスです。 HoloLens のセットアップ手順をお探しの場合は、「HoloLens (第 1 世代) の設定」または「Set up your HoloLens 2 」[(HoloLens (第 1](hololens1-start.md)世代) の設定) を[参照してください](hololens2-start.md)。

他の Windows デバイスと同様に、HoloLens は常にユーザー コンテキストで動作します。 常にユーザー ID があります。 HoloLens は、他のデバイスと同じように ID Windows 10扱います。 この記事は HoloLens での ID の詳細なリファレンスであり、HoloLens が他のデバイスとどのように異なるWindows 10されています。

HoloLens では、いくつかの種類のユーザー ID がサポートされています。 1 つ以上のユーザー アカウントを使用してサインインできます。 HoloLens の ID の種類と認証オプションの概要を次に示します。

| ID の種類 | デバイスあたりのアカウント数 | 認証オプション |
| --- | --- | --- |
| [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Azure Web 資格情報プロバイダー</li><li>Azure Authenticator アプリ</li><li>生体認証 (あやめ) &ndash; HoloLens 2<sup>のみ 2</sup> </li><li>HoloLens (第 1 世代) の PIN (省略 &ndash; 可能)、HoloLens 2</li><li>Password</li></ul> |
| [Microsoft アカウント (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>生体認証 (あやめ) &ndash; HoloLens 2のみ</li><li>HoloLens (第 1 世代) の PIN (省略 &ndash; 可能)、HoloLens 2</li><li>Password</li></ul> |
| [ローカル アカウント](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | Password |

クラウドに接続されたアカウント (Azure AD MSA) では、Azure サービスを使用できるより多くの機能が提供されます。  
> [!IMPORTANT]
> 1 - Azure AD Premiumにサインインする必要はありません。 ただし、自動登録や Autopilot など、低タッチのクラウドベースのデプロイの他の機能に必要です。

> [!NOTE]
> 2 - HoloLens 2 デバイスで最大 64 の Azure AD アカウントをサポートできる一方で、Iris Authentication に登録できるアカウントは 10 台のみです。 これは、 の他の[生体認証オプションとWindows Hello for Business。](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

## <a name="setting-up-users"></a>ユーザーの設定

新しいユーザーを設定する最も一般的な方法は、HoloLens out-of-box experience (OOBE) の間です。 セットアップ中に、HoloLens は、ユーザーがデバイスで使用するアカウントを使用してサインインするように求めるメッセージを表示します。 このアカウントには、コンシューマー アカウントMicrosoft アカウント Azure で構成されているエンタープライズ アカウントを使用できます。 [「HoloLens (第 1](hololens1-start.md)世代)[](hololens2-start.md)の設定」または「HoloLens 2。

他のデバイスの Windows と同様に、セットアップ中にサインインすると、デバイスにユーザー プロファイルが作成されます。 ユーザー プロファイルには、アプリとデータが格納されます。 また、同じアカウントでは、Windows アカウント マネージャー API を使用して、Edge や Microsoft Store などのアプリにシングル サインオンを提供します。  

企業または組織のアカウントを使用して HoloLens にサインインすると、HoloLens は組織の IT インフラストラクチャに登録されます。 この登録により、IT 管理者は、グループ ポリシーを HoloLens に送信デバイス管理 Mobile デバイス管理 (MDM) を構成できます。

既定では、他の Windows 10 デバイスの場合と同様に、HoloLens の再起動またはスタンバイからの再開時にもう一度サインインする必要があります。 設定アプリを使用してこの動作を変更するか、グループ ポリシーによって動作を制御できます。

### <a name="linked-accounts"></a>リンク済みのアカウント

Windows のデスクトップ バージョンと同様に、追加の Web アカウント資格情報を HoloLens アカウントにリンクできます。 このようなリンクを使用すると、アプリ (ストアなど) 間またはアプリ内のリソースに簡単にアクセスしたり、個人用リソースと仕事用リソースへのアクセスを組み合わせたりすることができます。 アカウントをデバイスに接続した後、デバイスをアプリに使用するアクセス許可を付与して、各アプリに個別にサインインする必要がなくなんの問題も生じかねない。

アカウントをリンクしても、イメージやダウンロードなど、デバイス上に作成されたユーザー データは分離されません。  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>マルチユーザー サポートの設定 (Azure ADのみ)

HoloLens では、同じテナントから複数のユーザー Azure ADできます。 この機能を使用するには、組織に属するアカウントを使用してデバイスを設定する必要があります。 その後、同じテナントの他のユーザーは、サインイン画面から、または [スタート] パネルのユーザー タイルをタップして、デバイスにサインインできます。 一度にサインインできるユーザーは 1 人のみです。 ユーザーがサインインすると、HoloLens は前のユーザーをサインアウトします。 デバイスの最初のユーザーはデバイス所有者と見なされます。ただし、参加の場合を除き、Azure ADの詳細については、デバイスの所有者に関する [ページを参照してください](security-adminless-os.md#device-owner)。

すべてのユーザーは、デバイスにインストールされているアプリを使用できます。 ただし、各ユーザーには独自のアプリ データと設定があります。 デバイスからアプリを削除すると、すべてのユーザーに対して削除されます。  

Azure ADアカウントで設定されたデバイスでは、Microsoft アカウントを使用したデバイスへのサインインは許可されません。 以降使用するアカウントはすべて、デバイスAzure AD同じテナントのアカウントに追加する必要があります。 引き続き Microsoft アカウント [を使用して](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) 、それをサポートするアプリ (Microsoft Store など) にサインインできます。 デバイスにサインインするためにAzure ADアカウントを Microsoft アカウントに変更するには、デバイス [を再フラッシュする必要があります](hololens-recovery.md#clean-reflash-the-device)。

> [!NOTE]
> **HoloLens (第 1** 世代) は、Azure AD の一 [](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)部として、Windows 10 April 2018 Updateユーザーのサポート [を開始Windows Holographic for Business。](hololens-upgrade-enterprise.md)

### <a name="multiple-users-listed-on-sign-in-screen"></a>[サインイン] 画面に表示される複数のユーザー

以前は、[サインイン] 画面には、最近サインインしたユーザーと "その他のユーザー" エントリ ポイントだけが表示されました。 複数のユーザーがデバイスにサインインしている場合は、これでは十分ではないというお客様からのフィードバックを受け取っています。 それでも、ユーザー名などを再入力する必要があります。

[Windows Holographic バージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1)で導入され、PIN 入力フィールドの右側にある [その他のユーザー] を選択すると、[サインイン] 画面に、以前にデバイスにサインインしたユーザーが複数表示されます。  これにより、ユーザーは自分のユーザー プロファイルを選択し、資格情報を使用してサインインWindows Helloできます。 [アカウントの追加] ボタンを使用して、この [その他のユーザー] ページからデバイスに新しい **ユーザーを追加** することもできます。

[その他のユーザー] メニューの [その他のユーザー] ボタンには、デバイスにサインインした最後のユーザーが表示されます。 このボタンを選択すると、このユーザーのサインイン画面に戻ります。

![サインイン画面の既定値](./images/multiusers1.jpg)

<br>

![他のユーザーのサインイン画面](./images/multiusers2.jpg)

## <a name="removing-users"></a>ユーザーの削除

[設定アカウント] [その他のユーザー]に移動して、デバイス  >  **からユーザー**  >  **を削除できます**。 このアクションでは、そのユーザーのすべてのアプリ データをデバイスから削除することで、領域も再利用されます。  

## <a name="using-single-sign-on-within-an-app"></a>アプリ内でのシングル サインオンの使用

アプリ開発者は、他の Windows デバイスと同様に [、Windows アカウント](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)マネージャー API を使用して、HoloLens でリンクされた ID を利用できます。 これらの API のコード サンプルの一部は、GitHub の [Web アカウント管理サンプル で入手できます](https://go.microsoft.com/fwlink/p/?LinkId=620621)。

アカウント情報に対するユーザーの同意の要求、2 要素認証など、発生する可能性があるアカウントの割り込みは、アプリが認証トークンを要求するときに処理する必要があります。

アプリで、以前にリンクされていない特定のアカウントの種類が必要な場合、アプリはユーザーにアカウントの追加を求めるメッセージをシステムに要求できます。 この要求は、アカウント設定ウィンドウをトリガーして、アプリのモーダル子として起動します。 2D アプリの場合、このウィンドウはアプリの中央に直接レンダリングされます。 Unity アプリの場合、この要求は、ユーザーをホログラフィック アプリから短時間取り出して、子ウィンドウをレンダリングします。 このペインでのコマンドとアクションのカスタマイズの詳細については [、「WebAccountCommand クラス」を参照してください](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)。

## <a name="enterprise-and-other-authentication"></a>エンタープライズおよび他の認証

アプリで NTLM、Basic、Kerberos などの他の種類の認証を使用している場合は [、Windows 資格情報 UI](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) を使用して、ユーザーの資格情報を収集、処理、保存できます。 これらの資格情報を収集するためのユーザー エクスペリエンスは、他のクラウド駆動型アカウントの割り込みと非常に似ています。2D アプリの上に子アプリとして表示されます。または、UI を表示するために Unity アプリを短時間中断します。

## <a name="deprecated-apis"></a>非推奨の API

HoloLens の開発が Desktop 用の開発と異なる方法の 1 つは [、OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API が完全にサポートされていない点です。 プライマリ アカウントが良好な状態にある場合、API はトークンを返しますが、この記事で説明されている割り込みでは、ユーザーの UI は表示されません。また、アカウントを正しく認証できません。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>HoloLens Windows Hello for Business (第 1 世代) でサポートされていますか?

Windows Hello for Business (PIN を使用したサインインをサポート) は、HoloLens (第 1 世代) でサポートされています。 HoloLens Windows Hello for Business PIN サインインを許可するには:

1. HoloLens デバイスは MDM [で管理する必要があります](hololens-enroll-mdm.md)。
1. デバイスに対してWindows Hello for Business有効にする必要があります。 ([の手順を参照Microsoft Intune)。](https://docs.microsoft.com/intune/windows-hello)
1. HoloLens では、ユーザーは [設定] [サインイン オプション] [PIN の追加] を使用して  >    >  **PIN** を設定できます。

> [!NOTE]
> アプリを使用してサインインするユーザー Microsoft アカウント、[設定] [サインイン オプション] [PIN の追加] で PIN を  >    >  **設定することもできます**。 この PIN は、 ではなく[Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)に関連付[Windows Hello for Business。](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Iris 生体認証は、HoloLens 2 に実装されていますか?

HoloLens 2は Iris 認証をサポートしています。 Iris は、Windows Helloテクノロジに基づいており、Azure Active Directory アカウントと Microsoft アカウントの両方で使用できます。 あやめは、他の Windows Hello テクノロジと同じように実装され、1/100K の生体認証セキュリティ FAR を実現します。

詳細については [、生体認証の要件とWindows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) を参照してください。 の [詳細については](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 、Windows Hello [と](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)Windows Hello for Business。 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>アカウントの種類はサインインの動作にどのような影響を与えるでしょうか。

サインイン用のポリシーを適用する場合、ポリシーは常に考慮されます。 サインインのポリシーが適用されない場合は、アカウントの種類ごとに既定の動作が次のとおりです。

- **Azure AD:** 既定で認証を求め、認証を要求しなくなった場合は **[** 設定] で構成できます。
- **Microsoft アカウント:** ロック動作が異なって自動ロック解除を許可しますが、再起動時にはサインイン認証が必要です。
- **ローカル アカウント**: 常にパスワードの形式で認証を要求します。設定では構成 **できません**

> [!NOTE]
> 非アクティブ タイマーは現在サポートされていません。つまり **、AllowIdleReturnWithoutPassword** ポリシーは、デバイスが StandBy に入った場合にのみ適用されます。

## <a name="additional-resources"></a>その他のリソース

ユーザー ID の保護と認証の詳細については、セキュリティと ID に関するWindows 10 [ドキュメントを参照してください](https://docs.microsoft.com/windows/security/identity-protection/)。

ハイブリッド ID インフラストラクチャの設定の詳細については、Azure ハイブリッド ID に関する [ドキュメントを参照してください](https://docs.microsoft.com/azure/active-directory/hybrid/)。
