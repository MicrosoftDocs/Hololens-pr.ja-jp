---
title: HoloLens のユーザー ID とサインインを管理する
description: HoloLens デバイスのユーザー id、マルチユーザーサポート、セキュリティ、エンタープライズ認証、およびサインインを管理する方法について説明します。
keywords: HoloLens、ユーザー、アカウント、AAD、Azure AD、adfs、microsoft アカウント、msa、資格情報、リファレンス
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
ms.openlocfilehash: 1081ed512183592e66e65f2e69323752b822f1c1
ms.sourcegitcommit: 5130823947caffd2a444e9d8fb15cd24cbb6414c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2021
ms.locfileid: "114659184"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>HoloLens のユーザー ID とサインインを管理する

> [!NOTE]
> この記事は、IT プロフェッショナルおよびテクニカル愛好家向けのテクニカルリファレンスです。 手順をお探し HoloLens の場合は、「[HoloLens (第1世代)](hololens1-start.md)のセットアップ」または「[HoloLens 2 の](hololens2-start.md)セットアップ」を参照してください。

他の Windows デバイスと同様に、HoloLens は常にユーザーコンテキストで動作します。 常にユーザー id が存在します。 HoloLens は、他の Windows 10 デバイスとほぼ同じ方法で id を扱います。 この記事では HoloLens の id に関する詳細なリファレンスを紹介し、HoloLens が他の Windows 10 デバイスとどのように異なるかについて重点的に説明します。

HoloLens では、いくつかの種類のユーザー id がサポートされています。 1つ以上のユーザーアカウントを使用してサインインできます。 HoloLens の id の種類と認証オプションの概要を次に示します。

| ID の種類 | デバイスごとのアカウント数 | 認証オプション |
| --- | --- | --- |
| [Azure Active Directory](/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Azure web 資格情報プロバイダー</li><li>Azure Authenticator アプリ</li><li>生体認証 (虹彩) &ndash; HoloLens 2<sup>2</sup>のみ </li><li>&ndash;HoloLens (第1世代) に対しては省略可能です。 HoloLens 2 には必須です</li><li>Password (パスワード)</li></ul> |
| [Microsoft アカウント (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>生体認証 (虹彩) &ndash; HoloLens 2 のみ</li><li>&ndash;HoloLens (第1世代) に対しては省略可能です。 HoloLens 2 には必須です</li><li>Password (パスワード)</li></ul> |
| [ローカル アカウント](/windows/security/identity-protection/access-control/local-accounts) | 1 | Password (パスワード) |

クラウドに接続されたアカウント (Azure AD と MSA) は、Azure サービスを使用できるため、より多くの機能を提供します。  
> [!IMPORTANT]
> 1-デバイスにサインインするために Azure AD Premium は必要ありません。 ただし、自動登録や自動操縦など、低タッチのクラウドベースの展開のその他の機能に必要です。

> [!NOTE]
> 2-HoloLens 2 デバイスは最大64の Azure AD アカウントをサポートできますが、これらのアカウントのうち31個だけが虹彩認証に登録できます。 これは、Windows Hello for [Business の他の生体認証オプション](/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)に合わせて調整されています。

## <a name="setting-up-users"></a>ユーザーの設定

新しいユーザーの設定方法として最も一般的なのは、HoloLens の既定のエクスペリエンス (OOBE) です。 セットアップ中に、デバイスで使用するアカウントを使用してサインインするようにユーザーに求めるメッセージが HoloLens されます。 このアカウントは、コンシューマー Microsoft アカウントでも、Azure で構成されているエンタープライズアカウントでもかまいません。 「 [HoloLens (第1世代)](hololens1-start.md) 」または「 [HoloLens 2](hololens2-start.md)のセットアップ」を参照してください。

他のデバイスでの Windows と同様に、セットアップ中にサインインすると、デバイスにユーザープロファイルが作成されます。 ユーザープロファイルには、アプリとデータが格納されます。 また、このアカウントは、Windows account Manager api を使用して、Edge や Microsoft Store などのアプリにシングルサインオンを提供します。  

エンタープライズアカウントまたは組織アカウントを使用して HoloLens にサインインすると、組織の IT インフラストラクチャに登録 HoloLens ます。 この登録により、IT 管理者は、HoloLens にグループポリシーを送信するようにモバイルデバイス管理 (MDM) を構成できます。

既定では、他の Windows 10 デバイスと同様に、HoloLens を再起動するか、スタンバイから再開するときに、もう一度サインインする必要があります。 設定アプリを使用してこの動作を変更することも、グループポリシーで動作を制御することもできます。

### <a name="linked-accounts"></a>リンク済みのアカウント

Windows のデスクトップバージョンと同様に、追加の web アカウント資格情報を HoloLens アカウントにリンクすることができます。 このようなリンクを使用すると、アプリ間またはアプリ内でのリソースへのアクセスが容易になり (ストアなど)、個人用リソースと職場リソースへのアクセスを組み合わせることができます。 アカウントをデバイスに接続した後、デバイスをアプリに使用するアクセス許可を付与して、各アプリに個別にサインインする必要がないようにすることができます。

アカウントをリンクしても、イメージやダウンロードなど、デバイス上に作成されたユーザーデータは分離されません。  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>マルチユーザーサポートを設定する (Azure AD のみ)

HoloLens は、同じ Azure AD テナントからの複数のユーザーをサポートしています。 この機能を使用するには、組織に属しているアカウントを使用してデバイスを設定する必要があります。 その後、同じテナントの他のユーザーは、サインイン画面からデバイスにサインインすることも、[スタート] パネルの [ユーザー] タイルをタップして、デバイスにサインインすることもできます。 一度にサインインできるユーザーは1人だけです。 ユーザーがサインインすると、前のユーザーがサインアウト HoloLens ます。 デバイスの最初のユーザーはデバイスの所有者と見なされますが、Azure AD 参加する場合を除き、 [デバイスの所有](security-adminless-os.md#device-owner)者の詳細を確認してください。

すべてのユーザーは、デバイスにインストールされているアプリを使用できます。 ただし、各ユーザーには独自のアプリデータと設定があります。 デバイスからアプリを削除すると、すべてのユーザーに対して削除されます。  

Azure AD アカウントを使用してセットアップしたデバイスでは、Microsoft アカウントを使用してデバイスにサインインすることはできません。 今後使用されるすべてのアカウントは、デバイスと同じテナントのアカウントを Azure AD する必要があります。 [Microsoft アカウントを使用し](hololens-identity.md#setting-up-multi-user-support-azure-ad-only)て、それをサポートするアプリ (Microsoft Store など) にサインインすることもできます。 デバイスへのサインインに Azure AD アカウントを使用して Microsoft アカウントに変更するには、 [デバイスを更新](hololens-recovery.md#clean-reflash-the-device)する必要があります。

> [!NOTE]
> **HoloLens (第1世代)** では、 [Windows Holographic for Business](hololens-upgrade-enterprise.md)の一部として [2018 年4月の更新](/windows/mixed-reality/release-notes-april-2018)で複数の Azure AD ユーザーのサポート Windows 10 が開始されました。

### <a name="multiple-users-listed-on-sign-in-screen"></a>サインイン画面に複数のユーザーが表示される

以前にサインイン画面には、最近サインインしたユーザーだけでなく、"その他のユーザー" エントリポイントのみが表示されていました。 複数のユーザーがデバイスにサインインしている場合、これでは十分ではないというお客様からのフィードバックを受け取りました。 ユーザー名を再入力する必要がありました。

[Windows Holographic version 21h1](hololens-release-notes.md#windows-holographic-version-21h1)で導入された [PIN 入力] フィールドの右側にある **他のユーザー** を選択すると、サインイン画面に、以前にデバイスにサインインしている複数のユーザーが表示されます。 これにより、ユーザーは自分のユーザープロファイルを選択し、Windows Hello の資格情報を使用してサインインできます。 新しいユーザーは、[ **アカウントの追加** ] ボタンを使用して、[その他のユーザー] ページからデバイスに追加することもできます。

[その他のユーザー] メニューの [その他のユーザー] ボタンをクリックすると、デバイスに最後にサインインしたユーザーが表示されます。 このボタンを選択すると、このユーザーのサインイン画面に戻ります。

![サインイン画面の既定値](./images/multiusers1.jpg)

<br>

![サインイン画面のその他のユーザー](./images/multiusers2.jpg)

## <a name="removing-users"></a>ユーザーの削除

デバイスからユーザーを削除するには、[   >    >  **他のユーザー** 設定アカウントに移動します。 この操作では、デバイスからユーザーのアプリデータをすべて削除することで、領域を解放します。  

## <a name="using-single-sign-on-within-an-app"></a>アプリ内でのシングルサインオンの使用

アプリ開発者は、他の Windows デバイスと同様に、 [Windows Account Manager api](/uwp/api/Windows.Security.Authentication.Web.Core)を使用して、HoloLens のリンクされた id を利用できます。 これらの api のコードサンプルについては、GitHub: [Web アカウント管理のサンプル](https://go.microsoft.com/fwlink/p/?LinkId=620621)を参照してください。

アカウント情報に対するユーザーの同意の要求、2要素認証など、発生する可能性のあるすべてのアカウント割り込みは、アプリが認証トークンを要求するときに処理する必要があります。

前にリンクされていない特定の種類のアカウントがアプリに必要な場合は、アプリでユーザーにメッセージを追加するように求めるメッセージを表示することができます。 この要求により、アプリのモーダル子として [アカウントの設定] ウィンドウが起動されます。 2D アプリの場合、このウィンドウはアプリの中央に直接表示されます。 Unity アプリの場合、この要求は、子ウィンドウを表示するためにユーザーを holographic アプリから簡単に取得します。 このペインでのコマンドとアクションのカスタマイズの詳細については、「 [Webaccountcommand クラス](/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)」を参照してください。

## <a name="enterprise-and-other-authentication"></a>Enterprise 認証とその他の認証

アプリが NTLM、Basic、または Kerberos などの他の種類の認証を使用している場合は、 [Windows 資格情報 UI](/uwp/api/Windows.Security.Credentials.UI)を使用して、ユーザーの資格情報を収集、処理、および保存できます。 これらの資格情報を収集するためのユーザーエクスペリエンスは、他のクラウド駆動型のアカウント割り込みとよく似ており、2D アプリの上に子アプリとして表示されるか、または UI を表示するために Unity アプリを一時的に中断します。

## <a name="deprecated-apis"></a>非推奨の API

HoloLens 用に開発する方法の1つとして、 [onlineidauthenticator](/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API が完全にサポートされていないという点があります。 プライマリアカウントが良好な場合、API はトークンを返しますが、この記事で説明されているような割り込みはユーザーの UI を表示せず、アカウントを正しく認証できません。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>HoloLens (第1世代) でサポートされているビジネスの Windows Hello

Windows Hello for Business (PIN を使用したサインインをサポート) は HoloLens (第1世代) でサポートされています。 HoloLens で Windows Hello for Business PIN のサインインを許可するには:

1. HoloLens デバイスは[MDM によって管理](hololens-enroll-mdm.md)されている必要があります。
1. デバイスの Windows Hello for Business を有効にする必要があります。 ([Microsoft Intune については、「」を参照してください。](/intune/windows-hello))
1. HoloLens では、ユーザーは **設定**  >  **サインインオプション**[  >  **pin の追加**] を使用して pin を設定できます。

> [!NOTE]
> Microsoft アカウントを使用してサインインしたユーザーは、**設定**  >  **サインインオプション**[pin の追加] で pin を設定することもでき  >  ます。 この PIN は、 [Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-overview)ではなく[Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)に関連付けられています。

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>HoloLens 2 には、虹彩認証認証はどのように実装されていますか。

HoloLens 2 は、虹彩認証をサポートしています。 虹彩は Windows Hello テクノロジに基づいており、Azure Active Directory と Microsoft アカウントの両方で使用できます。 虹彩は他の Windows Hello テクノロジと同じように実装されており、1/10 万以上の生体認証セキュリティを実現します。

詳細については、 [Windows Hello の生体認証の要件と仕様](/windows-hardware/design/device-experiences/windows-hello-biometric-requirements)を参照してください。 [Windows Hello](/windows-hardware/design/device-experiences/windows-hello)と[Windows Hello for Business の](/windows/security/identity-protection/hello-for-business/hello-identity-verification)詳細については、こちらを参照してください。 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>アカウントの種類はサインインの動作にどのような影響を与えますか。

サインイン用のポリシーを適用する場合、ポリシーは常に考慮されます。 サインインのポリシーが適用されていない場合、各アカウントの種類の既定の動作は次のとおりです。

- **Azure AD**: 既定で認証を要求し、**設定** が認証を要求しないように構成できます。
- **Microsoft アカウント**: ロック動作は、自動ロック解除を許可することとは異なりますが、再起動時にはサインイン認証が必要です。
- **ローカルアカウント**: 常にパスワードの形式で認証を要求します。で構成することはできません **設定**

> [!NOTE]
> 現在、非アクティブタイマーはサポートされていません。つまり、 **AllowIdleReturnWithoutPassword** ポリシーは、デバイスがスタンバイ状態になったときにのみ尊重されます。

## <a name="additional-resources"></a>その他の技術情報

ユーザー id の保護と認証の詳細について[は、Windows 10 のセキュリティと id](/windows/security/identity-protection/)に関するドキュメントを参照してください。

ハイブリッド id インフラストラクチャの設定の詳細については、 [Azure ハイブリッド id のドキュメント](/azure/active-directory/hybrid/)を参照してください。
