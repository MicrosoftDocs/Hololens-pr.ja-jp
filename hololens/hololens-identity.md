---
title: HoloLens のユーザー id とサインインを管理する
description: HoloLens デバイスのユーザー id、マルチユーザーサポート、セキュリティ、エンタープライズ認証、およびサインインを管理する方法について説明します。
keywords: HoloLens、user、account、AAD、Azure AD、adfs、microsoft アカウント、msa、資格情報、リファレンス
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
ms.openlocfilehash: 2d84658ef76ff2c5d8ef7dabe857892e7129a965
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309884"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>HoloLens のユーザー id とサインインを管理する

> [!NOTE]
> この記事は、IT プロフェッショナルおよびテクニカル愛好家向けのテクニカルリファレンスです。 HoloLens の設定手順については、「HoloLens のセットアップ[(第1世代)](hololens1-start.md)」または「[hololens 2](hololens2-start.md)のセットアップ」を参照してください。

他の Windows デバイスと同様に、HoloLens は常にユーザーコンテキストで動作します。 常にユーザー id が存在します。 HoloLens は、他の Windows 10 デバイスとほとんど同じ方法で id を扱います。 この記事は、HoloLens での id の詳細なリファレンスであり、HoloLens と他の Windows 10 デバイスとの違いに焦点を当てています。

HoloLens では、複数の種類のユーザー id がサポートされています。 1つ以上のユーザーアカウントを使用してサインインできます。 HoloLens の id の種類と認証オプションの概要を次に示します。

| ID の種類 | デバイスごとのアカウント数 | 認証オプション |
| --- | --- | --- |
| [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (Azure AD Premium が必要) | 64 | <ul><li>Azure web 資格情報プロバイダー</li><li>Azure Authenticator アプリ</li><li>生体認証 (虹彩) &ndash; HoloLens 2 のみ<sup>1</sup> </li><li>Hololens &ndash; (第1世代) の PIN (オプション) (hololens 2 に必須)</li><li>パスワード</li></ul> |
| [Microsoft アカウント (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>生体認証 (虹彩) &ndash; HoloLens 2 のみ</li><li>Hololens &ndash; (第1世代) の PIN (オプション) (hololens 2 に必須)</li><li>パスワード</li></ul> |
| [ローカル アカウント](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | パスワード |

クラウドに接続されたアカウント (Azure AD と MSA) は、Azure サービスを使用できるため、より多くの機能を提供します。  

> [!NOTE]
> 1-HoloLens 2 デバイスは最大64の Azure AD アカウントをサポートできますが、これらのアカウントのうち10個だけが虹彩認証で登録できます。 これは、 [Windows Hello For business 用の他の生体認証オプション](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)に合わせて調整されています。

## <a name="setting-up-users"></a>ユーザーの設定

新しいユーザーの設定方法として最も一般的なのは、HoloLens の非インボックスエクスペリエンス (OOBE) です。 セットアップ中に、デバイスで使用するアカウントを使用してユーザーにサインインを求めるメッセージが表示されます。 このアカウントは、コンシューマー Microsoft アカウントでも、Azure で構成されているエンタープライズアカウントでもかまいません。 「Hololens のセットアップ [(第1世代)](hololens1-start.md) 」または「 [hololens 2](hololens2-start.md)」を参照してください。

他のデバイスの Windows と同様に、セットアップ中にサインインすると、デバイスにユーザープロファイルが作成されます。 ユーザープロファイルには、アプリとデータが格納されます。 同じアカウントでは、Windows アカウントマネージャー Api を使用して、Edge や Skype などのアプリにシングルサインオンを提供することもできます。  

企業または組織のアカウントを使用して HoloLens にサインインすると、HoloLens は組織の IT インフラストラクチャに登録します。 この登録により、IT 管理者は、グループポリシーを HoloLens に送信するようにモバイルデバイス管理 (MDM) を構成できます。

既定では、他の Windows 10 デバイスと同様に、HoloLens を再起動するか、スタンバイから再開するときに、もう一度サインインする必要があります。 設定アプリを使用してこの動作を変更することも、グループポリシーで動作を制御することもできます。

### <a name="linked-accounts"></a>リンク済みのアカウント

Windows のデスクトップバージョンと同様に、追加の web アカウント資格情報を HoloLens アカウントにリンクすることができます。 このようなリンクを使用すると、アプリ間またはアプリ内でのリソースへのアクセスが容易になり (ストアなど)、個人用リソースと職場リソースへのアクセスを組み合わせることができます。 アカウントをデバイスに接続した後、デバイスをアプリに使用するアクセス許可を付与して、各アプリに個別にサインインする必要がないようにすることができます。

アカウントをリンクしても、イメージやダウンロードなど、デバイス上に作成されたユーザーデータは分離されません。  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>マルチユーザーサポートを設定する (Azure AD のみ)

HoloLens では、同じ Azure AD テナントからの複数のユーザーがサポートされています。 この機能を使用するには、組織に属しているアカウントを使用してデバイスを設定する必要があります。 その後、同じテナントの他のユーザーは、サインイン画面からデバイスにサインインすることも、[スタート] パネルの [ユーザー] タイルをタップして、デバイスにサインインすることもできます。 一度にサインインできるユーザーは1人だけです。 ユーザーがサインインすると、HoloLens は前のユーザーをサインアウトします。 デバイスの最初のユーザーはデバイスの所有者と見なされますが、Azure AD 参加する場合を除き、 [デバイスの所有](security-adminless-os.md#device-owner)者の詳細を確認してください。

すべてのユーザーは、デバイスにインストールされているアプリを使用できます。 ただし、各ユーザーには独自のアプリデータと設定があります。 デバイスからアプリを削除すると、すべてのユーザーに対して削除されます。  

Azure AD アカウントを使用してセットアップしたデバイスでは、Microsoft アカウントを使用してデバイスにサインインすることはできません。 今後使用されるすべてのアカウントは、デバイスと同じテナントのアカウントを Azure AD する必要があります。 [Microsoft アカウントを使用し](hololens-identity.md#setting-up-multi-user-support-azure-ad-only)て、それをサポートするアプリ (Microsoft Store など) にサインインすることもできます。 デバイスへのサインインに Azure AD アカウントを使用して Microsoft アカウントに変更するには、 [デバイスを更新](hololens-recovery.md#clean-reflash-the-device)する必要があります。

> [!NOTE]
> **HoloLens (第1世代)** は、windows [Holographic for Business](hololens-upgrade-enterprise.md)の一部として、 [Windows 10 April 2018 更新プログラム](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)で複数の Azure AD ユーザーのサポートを開始しました。

## <a name="removing-users"></a>ユーザーの削除

デバイスからユーザーを削除するには、[**設定**] [アカウント] [  >    >  **その他のユーザー**] の順に移動します。 この操作では、デバイスからユーザーのアプリデータをすべて削除することで、領域を解放します。  

## <a name="using-single-sign-on-within-an-app"></a>アプリ内でのシングルサインオンの使用

アプリ開発者は、他の Windows デバイスと同様に、 [Windows アカウントマネージャー api](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)を使用して、HoloLens でリンクされた id を利用できます。 これらの Api のコードサンプルについては、GitHub の [Web アカウント管理サンプル](https://go.microsoft.com/fwlink/p/?LinkId=620621)を参照してください。

アカウント情報に対するユーザーの同意の要求、2要素認証など、発生する可能性のあるすべてのアカウント割り込みは、アプリが認証トークンを要求するときに処理する必要があります。

前にリンクされていない特定の種類のアカウントがアプリに必要な場合は、アプリでユーザーにメッセージを追加するように求めるメッセージを表示することができます。 この要求により、アプリのモーダル子として [アカウントの設定] ウィンドウが起動されます。 2D アプリの場合、このウィンドウはアプリの中央に直接表示されます。 Unity アプリの場合、この要求は、子ウィンドウを表示するためにユーザーを holographic アプリから簡単に取得します。 このペインでのコマンドとアクションのカスタマイズの詳細については、「 [Webaccountcommand クラス](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)」を参照してください。

## <a name="enterprise-and-other-authentication"></a>エンタープライズ認証とその他の認証

アプリが NTLM、Basic、または Kerberos などの他の種類の認証を使用している場合は、 [Windows 資格情報 UI](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) を使用してユーザーの資格情報を収集、処理、および保存できます。 これらの資格情報を収集するためのユーザーエクスペリエンスは、他のクラウド駆動型のアカウント割り込みとよく似ており、2D アプリの上に子アプリとして表示されるか、または UI を表示するために Unity アプリを一時的に中断します。

## <a name="deprecated-apis"></a>非推奨の API

HoloLens 向けの開発は、デスクトップ向けの開発とは異なり、 [Onlineidauthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API は完全にはサポートされていません。 プライマリアカウントが良好な場合、API はトークンを返しますが、この記事で説明されているような割り込みはユーザーの UI を表示せず、アカウントを正しく認証できません。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Windows Hello for Business は HoloLens (第1世代) でサポートされていますか?

HoloLens (第1世代) では、Windows Hello for Business (PIN の使用をサポート) がサポートされています。 HoloLens で Windows Hello for Business の PIN のサインインを許可するには

1. HoloLens デバイスは [MDM によって管理](hololens-enroll-mdm.md)されている必要があります。
1. デバイスの Windows Hello for Business を有効にする必要があります。 ([Microsoft Intune については、「」を参照してください。](https://docs.microsoft.com/intune/windows-hello))
1. HoloLens では、ユーザーは設定の  >  **サインインオプション**[  >  **pin の追加**] を使用して pin を設定できます。

> [!NOTE]
> Microsoft アカウントを使用してサインインしたユーザーは、[**設定**  >  **] [サインインオプション]**[pin の追加] で pin を設定することもでき  >  ます。 この PIN は、windows hello [For business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)ではなく、 [windows hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)に関連付けられています。

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>HoloLens 2 では、虹彩認証認証はどのように実装されていますか。

HoloLens 2 では、虹彩認証がサポートされています。 虹彩は Windows Hello テクノロジをベースとしており、Azure Active Directory と Microsoft アカウントの両方で使用できます。 虹彩は他の Windows Hello テクノロジと同じように実装されており、1/10 万以上の生体認証セキュリティを実現します。

詳細については、「 [Windows Hello の生体認証の要件と仕様](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) 」を参照してください。 [Windows hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)と[Windows hello for business の](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)詳細については、こちらを参照してください。 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>アカウントの種類はサインインの動作にどのような影響を与えますか。

サインイン用のポリシーを適用する場合、ポリシーは常に考慮されます。 サインインのポリシーが適用されていない場合、各アカウントの種類の既定の動作は次のとおりです。

- **Azure AD**: 既定で認証を要求し、認証を要求しないように **設定** によって構成できます。
- **Microsoft アカウント**: ロック動作は、自動ロック解除を許可することとは異なりますが、再起動時にはサインイン認証が必要です。
- **ローカルアカウント**: 常にパスワードの形式で認証を要求します。**設定** で構成することはできません。

> [!NOTE]
> 現在、非アクティブタイマーはサポートされていません。つまり、 **AllowIdleReturnWithoutPassword** ポリシーは、デバイスがスタンバイ状態になったときにのみ尊重されます。

## <a name="additional-resources"></a>その他のリソース

ユーザー id の保護と認証の詳細について [は、Windows 10 のセキュリティと id](https://docs.microsoft.com/windows/security/identity-protection/)に関するドキュメントを参照してください。

ハイブリッド id インフラストラクチャの設定の詳細については、 [Azure ハイブリッド id のドキュメント](https://docs.microsoft.com/azure/active-directory/hybrid/)を参照してください。
