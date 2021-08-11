---
title: パスワードの使用制限
description: HoloLens のパスワードの使用を制限する
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: セキュリティ、hololens、パスワード使用の制限、パスワード、hololens パスワード、サインイン、サインイン、windows hello、hello、windows アカウント マネージャー、FIDO2 のサインイン、FIDO 2、WEBAUTHN、ローカル アカウント、hololens セキュリティ
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: a4ceaa1a741ec63153cd9112d04547165b46b0fa72c32ee7f9580f15368a2f88
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665454"
---
# <a name="limiting-password-use"></a>パスワードの使用制限

今日では、ほとんどのコンピューター システムが、セキュリティの基礎としてユーザーの資格情報を使用し、ユーザーが作成した再利用可能なパスワードに依存しています。 その結果、パスワードは、アカウントの漏えいやデータ流出の最も一般的な原因にもなっています。 この例として、パスワードの送信中に傍受されたり、フィッシング攻撃やパスワード スプレー攻撃によってサーバーから盗まれたりしてユーザー アカウントにアクセスされることにより、危険にさらされることがあります。

セキュリティとアカウント保護を向上させるために、HoloLens 2 は、デバイスのサインイン用に、ハードウェアでバックアップされた強力な "パスワードレス" 資格情報 (Windows Hello など) を有効にする機能を備えており、Microsoft クラウドへのシームレスなアクセスを提供します。

## <a name="signing-in-from-another-device"></a>別のデバイスからサインインする

HoloLens 2 は、デバイスの初期設定時やユーザー サインイン時に Azure Active Directory 職場アカウント用のリモート デバイス サインイン オプションを提供し、複雑な種類のパスワードを入力する必要性を減らし、資格情報としてのパスワードの必要性を最小限に抑えます。 スマートカードを使用して認証を行うユーザーや組織は、HoloLens 2 などのデバイスで資格情報を使用することが困難であり、多くの場合、組織はこの問題を回避するために複雑なシステムやコストのかかるプロセスを開発しています。 この問題を解決するために、Azure AD では、HoloLens 2 でパスワードレス サインインを行うための 2 つのオプションを提供しています。

最初の認証方法は、Microsoft Authenticator アプリの新機能に依存しており、デバイスに関連付けられているユーザー資格情報を有効にするキーベースの認証を提供します。 管理者がテナントで有効にすると、HoloLens デバイスのセットアップ中に、ユーザーがアプリ上の番号をタップするように指示するメッセージが表示されます。 次に、ユーザーの認証アプリの番号と一致させてから [承認] を選択し、PIN または生体認証を提供し、HoloLens のセットアップを完了させて認証する必要があります。 この詳細については、[パスワードなしのサインイン](/azure/active-directory/authentication/howto-authentication-passwordless-phone)に関するページを参照してください。

2 つ目の例は、ユーザーにとって直感的で、追加のインフラストラクチャが必要ないデバイス コード フローです。  このリモート サインイン動作は、組織の優先認証メカニズムをサポートする別の信頼できるデバイスに依存しています。完了すると、トークンが HoloLens に発行され、サインインまたはデバイスのセットアップが完了します。 このフローの手順は次のとおりです。

  1. OOBE でデバイスの初期セットアップやサインインのフローを進めるユーザーには、[別のデバイスからサインインする] リンクが表示されるため、それをタップします。 これで、リモート サインイン セッションが開始されます。
  1. ユーザーには、Azure AD Secure Token Service (STS) のデバイス認証エンドポイントを示す短い URI ([https://microsoft.com/devicelogin](https://microsoft.com/devicelogin)) を含む、ポーリング ページが表示されます。 また、ユーザーには、クラウドに安全に生成され、最大 15 分の有効期限を持つワンタイム コードが表示されます。 Azure AD により、コードが生成されるだけでなく、前の手順でリモート サインイン要求を開始したときに、暗号化されたセッションも作成されます。また、URI とコードを使用してリモート サインイン要求が承認されます。
  1. ユーザーが別のデバイスから URI に移動すると、そのユーザーの HoloLens 2 デバイスに表示されたコードの入力を求められます。
  1. ユーザーがコードを入力すると、Azure AD STS により、リモート サインイン要求がトリガーされ、コードの生成を要求したユーザーの HoloLens 2 デバイスを示すページが表示されます。 その後、ユーザーには、フィッシング攻撃を防ぐための確認画面が表示されます。
  1. 表示された 'アプリケーション' へのサインインを続行することをユーザーが選択した場合、Azure AD STS からユーザーに対して資格情報の入力が求められます。 認証が成功した場合、Azure AD STS により、キャッシュされたリモート セッションは承認コードと共に '承認済み' として更新されます。
  1. 最後に、ユーザーの HoloLens 2 デバイス上のポーリング ページで、Azure AD から '承認済み' 応答を受け取り、ユーザー コードの検証、それに関連する格納された認証コードの検証が進められ、デバイスの設定を完了するために要求に応じて OAuth トークンが生成されます。 作成された認証トークンは 1 時間有効であり、更新トークンの有効期間は 90 日です。

このフローで使用されるコード生成および暗号化アルゴリズムは、ともに FIPS に準拠しています。 HoloLens 2 デバイスでは、デバイス キーを保護し、ハードウェア保護されたキーを使用してユーザー認証の後に生成されるトークンを暗号化するために TPM が使用されています。 HoloLens 2 上のトークン セキュリティの詳細については、「[プライマリ更新トークン (PRT) とは](/azure/active-directory/devices/concept-primary-refresh-token)」を参照してください。

## <a name="device-sign-in-with-windows-hello"></a>Windows Hello を使用したデバイス サインイン

[Windows Hello](/windows/security/identity-protection/hello-for-business/hello-identity-verification) には、オペレーティング システムに直接組み込まれたパスワードフリーのオプションが用意されており、ユーザーは虹彩または PIN を使用してデバイスにサインインできるようになります。 PIN は常に資格情報として使用可能であり、デバイスのセットアップに必要ですが、虹彩は省略可能で、スキップすることができます。 ユーザーは、パスワード入力を "*しなくても*"、個人用の Microsoft アカウント、または [Azure Active Directory の職場アカウント](/azure/active-directory/authentication/concept-authentication-passwordless)を使用して HoloLens デバイスにサインインすることができます。 このようなオプションを使うと、ユーザーは、完全な Windows エクスペリエンス、アプリ、データ、Web サイト、およびサービスに迅速かつ安全にアクセスできるようになります。 ここでは、パスワードレス エクスペリエンスに向けた Microsoft の戦略について詳しく説明します。

Windows Hello の資格情報の作成時には、ID プロバイダーとの信頼関係が確立され、認証に使われる非対称キー ペアが作成されます。 Windows Hello のジェスチャ (虹彩や PIN など) は、デバイスのトラステッド プラットフォーム モジュール (TPM) チップに裏付けられた秘密キーを解読するためのエントロピーを提供します。 この秘密キーは、認証サーバーに送信された要求に署名するために使用され、認証が成功すると、ユーザーには、メール、画像、およびその他のアカウント設定へのアクセス権が付与されます。

詳細については、次のインフォグラフィックをご覧ください。

  ![Windows Hello のサインイン](images/security-hello-sign-in.png)
  
上記のグラフィックで、"nonce" は "一度きりの数字" を表し、ランダムまたはセミランダムに生成された数であることに注意してください。 Windows Hello 生体認証または PIN の資格情報が一度設定されると、それがプロビジョニングされているデバイスから離れることはありません。 フィッシング攻撃などでユーザーの Windows Hello PIN が盗まれた場合でも、[ユーザーの物理デバイスがないと役に立ちません](/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password)。

セキュリティを強化するために、Windows Hello の資格情報は TPM (Trusted Platform Module) によって保護されており、資格情報の改ざんを防止すると共に、複数回の誤入力に対するハンマリング防止機能や、漏えいを防止する悪意のあるソフトウェアからの保護機能を備えています。 シングル サインオン (SSO) の詳細については、こちらの「[シングル サインオン (SSO) とは](/azure/active-directory/manage-apps/what-is-single-sign-on)」を参照してください。

虹彩認証は PIN の代替手段です。 デバイスに新しい PIN (強力な認証手段) を設定する場合、このプロセスを完了するには、ユーザーが[多要素認証 (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks) を最近実行している必要があります。

## <a name="single-sign-on-with-web-account-manager"></a>Web アカウント マネージャーでのシングル サインオン

シングル サインオン (SSO) を使用すると、ユーザーの個人アカウント、職場または学校アカウントを使用して、ユーザーがパスワードを使用することなくデバイスにサインインできるようになります。 ユーザーは、[Web アカウント マネージャー API](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true) を介して、すべての統合されたアプリやサービスに SSO で自動的に承認されます。

1 つのアプリケーションを使用して ID を追加した後は、ユーザーの同意があれば、システム レベルの統合を使用してすべてのアプリとサービスで利用できるようになります。 これにより、アプリにサインインする負担が大幅に軽減され、シームレスな ID エクスペリエンスがユーザーに提供されます。

Web アカウント マネージャー API の実装の詳細については、[Web アカウント マネージャー API の実装](/windows/uwp/security/web-account-manager)に関するページを参照してください。

  ![Security API](images/security-api-img.png)
  
特殊な認証要件を持つアプリ スイートの場合、Web アカウント マネージャー (WAM) フレームワークは、カスタム ID プロバイダーにも拡張できます。 ユーザーは、Microsoft Store からユニバーサル Windows プラットフォーム (UWP) アプリとしてパッケージ化されたカスタム ID プロバイダーをダウンロードし、その ID プロバイダーと統合された他のアプリで SSO を有効にできます。

カスタム WAM ID プロバイダーの実装の詳細については、[カスタム WAM ID プロバイダー API リファレンス](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)を参照してください。

## <a name="windows-hello-and-fido2-sign-in-with-webauthn"></a>WebAuthn を使用した Windows Hello および FIDO2 のサインイン

HoloLens 2 を使用すると、パスワードを使用しないユーザーの資格情報 (Windows Hello や FIDO2 セキュリティ キーなど) を採用し、Microsoft Edge を介して Web 上で安全にサインインしたり、WebAuthn をサポートする Web サイトにアクセスしたりすることができます。 FIDO2 を使用すると、ユーザーの資格情報で標準ベースのデバイスを使用してオンライン サービスを認証できるようになります。

> [!Note]
> [WebAuthn](https://www.w3.org/TR/webauthn/) と FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) の仕様は、サービスに実装されています。 WebAuthn や FIDO2 に規定されている署名付きメタデータから、ユーザーがその場にいたかどうかなどの情報がわかります。また、ローカル ジェスチャーによる認証を検証することができます。

Windows Hello の場合と同様に、ユーザーが FIDO2 資格情報を作成して登録すると、デバイス (HoloLens 2 または FIDO2 セキュリティ キー) によってデバイス上に秘密キーと公開キーが生成されます。 秘密キーはデバイスに安全に格納され、生体認証や PIN などのローカル ジェスチャを使用してロックを解除した後にのみ使用できます。 秘密キーが格納される場合は、公開キーがクラウドの Microsoft アカウントシステムに送信され、関連付けられているユーザー アカウントで登録されます。

MSA および Azure AD アカウントでサインインすると、生成された番号またはデータ変数がシステムから HoloLens 2 または FIDO2 デバイスに送信されます。 HoloLens 2 またはデバイスにより、秘密キーを使用して ID に署名されます。 署名済みの ID とメタデータは、Microsoft アカウント システムに返送され、公開キーを使用して検証されます。

Windows Hello および FIDO2 デバイスには、HoloLens デバイス、特に組み込みのトラステッド プラットフォーム モジュールの安全なエンクレーブに基づいて、資格情報が実装されています。 TPM のエンクレーブには秘密キーが格納され、ロックを解除するには生体認証または PIN が必要です。 同様に、FIDO2 セキュリティ キーは、秘密キーを格納する安全なエンクレーブを内蔵した小型の外部デバイスであり、ロックを解除するには生体認証または PIN が必要です。

どちらのオプションでも、1 つの手順で 2 要素認証が提供されます。この認証では、正常にサインインするには、登録されたデバイスと生体認証または PIN の両方が必要です。 詳細については、以下の「FIDO2 セキュリティ キーのグラフィックとプロセスを使用した強力な認証」を参照してください。

### <a name="strong-authentication-with-fido2-security-key"></a>FIDO2 セキュリティ キーを使用した強力な認証

  ![FIDO の画像](images/security-fido2-whfb-smaller.png)

1. ユーザーが FIDO2 セキュリティ キーを HoloLens 2 に接続します
1. Windows によって FIDO2 セキュリティ キーが検出されます
1. HoloLens から認証要求が送信されます
1. Azure AD から nonce が返送されます
1. ユーザーがジェスチャーを完了して、セキュリティ キーの安全なエンクレーブ内にある秘密キー ストアのロックを解除します
1. FIDO2 セキュリティ キーにより、秘密キーを使用して nonce に署名されます
1. 署名された nonce を含む PRT トークン要求が Azure AD に送信されます
1. Azure AD によって FIDO キーが検証されます
1. Azure AD から PRT と TGT が返され、リソースへのアクセスを有効になります

MSA と Azure AD は、WebAuthn を実装してパスワードレス認証をサポートする最初の証明書利用者の 1 つです。

アプリケーションや SDK で WebAuthn を使用する方法の詳細については、[Windows 10 上でのパスワードレス認証のための WebAuthn API](/windows/security/identity-protection/hello-for-business/webauthnapis) に関するページを参照してください。

HoloLens 2 は、[Azure Active Directory のパスワードレス サインインに関するページの「FIDO2 セキュリティ キー」](/azure/active-directory/authentication/concept-authentication-passwordless#fido2-security-keys)に記載されている要件を満たし、仕様に沿って実装された FIDO2 セキュリティ デバイスをサポートしています。

## <a name="local-accounts"></a>ローカル アカウント

オフライン モードでの展開のために、単一のローカル アカウントを構成することができます。 ローカル アカウントは既定では有効になっていません。デバイス プロビジョニング中に構成する必要があります。 サインインにはパスワードを使用する必要があります。また、代替認証方法 ([Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-overview) や [Windows Hello](/windows-hardware/design/device-experiences/windows-hello) など) はサポートされていません。

HoloLens ユーザー アカウントの詳細については、[HoloLens の ID](hololens-identity.md) に関するページを参照してください。

IT 管理者は、[AllowMicrosoftAccountConnection](/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection) を使用して、ユーザーがメール関連ではない接続の認証とサービスに MSA アカウントを使用できるようにするかどうかを調整します。 パスワード構成ポリシー、アイドリング ポリシー、ロック画面ポリシーについては、[デバイスのロック](/windows/client-management/mdm/policy-csp-devicelock)に関するページを参照してください。
