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
ms.openlocfilehash: 6233e9f422022dc3fb4f3e615261504b9686f501
ms.sourcegitcommit: ab35169529776f0682eeb8fa448c9d9e8f598513
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/17/2021
ms.locfileid: "11340492"
---
# パスワードの使用制限

今日では、ほとんどのコンピューター システムが、セキュリティの基礎としてユーザーの資格情報を使用し、ユーザーが作成した再利用可能なパスワードに依存しています。 これにより、パスワードもまた、アカウントが侵害され、データが侵害される最も一般的な原因になります。 この例として、パスワードの送信中に傍受されたり、フィッシング攻撃やパスワード スプレー攻撃によってサーバーから盗まれたりしてユーザー アカウントにアクセスされることにより、危険にさらされることがあります。

セキュリティとアカウント保護を向上させるために、HoloLens 2は、デバイスのサインイン用に、ハードウェアでバックアップされた強力な「パスワードレス」の資格情報 （Windows Helloを含む） を有効にする機能を備えており、Microsoft クラウドへのシームレスなアクセスを提供します。

## 別のデバイスからのサインイン

HoloLens 2は、デバイスの初期設定時やユーザー サインイン時に Azure Active Directory 職場アカウント用のリモート デバイス サインイン オプションを提供し、複雑な種類のパスワードを入力する必要性を減らし、資格情報としてのパスワードの必要性を最小限に抑えます。 スマートカードを使用して認証を行うユーザーや組織は、HoloLens 2 などのデバイスで資格情報を使用することが困難であり、多くの場合、組織はこの問題を回避するために複雑なシステムやコストのかかるプロセスを開発しています。 この問題を解決するために、Azure AD では、HoloLens 2でパスワードなしのサインインを行うための2つのオプションを提供しています。

最初の認証方法は、Microsoft Authenticator アプリの新機能に依存しており、デバイスに関連付けられているユーザー資格情報を有効にするキーベースの認証を提供します。 管理者がテナントで有効にすると、HoloLens デバイスのセットアップ中に、ユーザーがアプリ上の番号をタップするように指示するメッセージが表示されます。 次に、ユーザーの認証アプリの番号と一致させてから [承認] を選択し、PINまたは生体認証を提供し、HoloLens のセットアップを完了させて認証する必要があります。 この方法の詳細については、「[パスワードレス サインイン](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)」 を参照してください。

2番目の例は、ユーザーにとって直観的で、追加のインフラストラクチャが必要ないデバイス コード フローです。  このリモート・サインイン動作は、組織の優先認証メカニズムをサポートする別の信頼できるデバイスに依存しています。完了すると、トークンが HoloLens に発行され、サインインまたはデバイスのセットアップが完了します。 このフローの手順は次のとおりです。

  1. OOBE でデバイスの初期セットアップやサインインのフローを進めるユーザーには、"他のデバイスからサインイン" のリンクが表示されるため、それをタップします。 これで、リモート サインイン セッションが開始されます。
  1. ユーザーには、Azure AD Secure Token Service (STS) のデバイス認証エンドポイントを示す短い URI ([https://microsoft.com/devicelogin](https://microsoft.com/devicelogin)) を含む、ポーリング ページが表示されます。 また、ユーザーには、クラウドに安全に生成され、最大15分の有効期限を持つワンタイム コードが表示されます。 コードを生成するだけでなく、Azure AD は、前の手順でリモート サインイン要求を開始したときに、暗号化されたセッションも作成します。併せて、URI とコードを使用してリモート サインイン要求を承認します。
  1. ユーザーが別のデバイスから URI に移動すると、そのユーザーの HoloLens 2 デバイスに表示されたコードの入力を求められます。
  1. ユーザーがコードを入力すると、Azure AD STS は、リモート サインイン要求をトリガーし、コードの生成を要求したユーザーの HoloLens 2デバイスを示すページを表示します。 その後、ユーザーには、フィッシング攻撃を防ぐための確認画面が表示されます。
  1. ユーザーが表示されている ' アプリケーション ' にサインインを続けることを選択すると、Azure AD STS がユーザーの資格情報の入力を求めます。 認証が成功した場合、Azure AD STS は、認証コードと共にキャッシュされたリモート セッションを ' 承認済み ' として更新します。
  1. 最後に、ユーザーの HoloLens 2デバイスにあるポーリング ページは、Azure AD から ' 承認済み ' 応答を受信し、ユーザー コード、および関連する保存された認証コードの検証を行い、デバイス セットアップを完了するために要求されたように OAuth トークンを生成します。 作成された認証トークンは1時間有効で、更新トークンの有効期間は90日です。

このフローで使用されるコード生成および暗号化アルゴリズムは、ともに FIPS に準拠しています。 HoloLens 2 デバイスは、TPM を使用してデバイス キーを保護し、ハードウェア保護されたキーを使用してユーザー認証の後に生成されるトークンを暗号化します。 HoloLens 2 のトークン セキュリティの詳細については、「[プライマリ更新トークン (PRT)](https://docs.microsoft.com/azure/active-directory/devices/concept-primary-refresh-token)」 で共有されています。

## Windows Hello を使用したデバイス サインイン

[Windows Hello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) は、オペレーティング システムに直接組み込まれたパスワードフリーのオプションを提供し、ユーザーが虹彩または PIN を使用してデバイスにサインインできるようにします。 PIN は常に資格情報として使用可能であり、デバイスのセットアップに必要ですが、虹彩は省略可能で、スキップすることができます。 ユーザーは、 *パスワード入力* をしなくても、個人用の Microsoft アカウント、または [Azure Active Directory の職場アカウント](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless) を入力して HoloLens デバイスにサインインすることができます。 このようなオプションを使うと、ユーザーは、完全な Windows エクスペリエンス、アプリ、データ、Web サイト、およびサービスに迅速かつ安全にアクセスできるようになります。 パスワードレス体験に向けた Microsoft の戦略について、こちらで詳しく説明します。

Windows Hello の資格情報の作成時には、ID プロバイダとの信頼関係が確立され、認証に使われる非対称キー ペアが作成されます。 Windows Hello のジェスチャ (虹彩や PIN など) は、デバイスのトラステッド プラットフォーム モジュール (TPM) チップに裏付けられた秘密キーを解読するためのエントロピーを提供します。 この秘密キーは、認証サーバーに送信された要求に署名するために使用され、認証が成功すると、ユーザーには、メール、画像、およびその他のアカウント設定へのアクセス権が付与されます。

詳しくは、次のインフォグラフィックをご覧ください。

  ![Windows Hello のサインイン](images/security-hello-sign-in.png)
  
上記のグラフィックで、「nonce」 は "一度きりの数字" を表し、ランダムまたはセミランダムに生成された数であることに注意してください。 Windows Hello 生体認証または PIN の資格情報が一度設定されると、それがプロビジョニングされているデバイスを離れることはありません。 フィッシング攻撃などでユーザーの Windows Hello PIN が盗まれた場合でも、それは [ユーザーの物理デバイスがなければ役に立ちません](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password)。

セキュリティを強化するために、Windows Hello の資格情報は トラステッド プラットフォーム モジュール (TPM) によって保護されます。これは、資格情報の改ざんを防止し、複数の不正エントリに対するハンマリング対策保護、およびマルウェアからの保護によって補強し、暴露を防止します。 シングル サインオン (SSO) の詳細については、この 「[SSO の使用方法の概要](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on)」 を参照してください。

虹彩認証は PIN にフォール バックします。 デバイスで新しい PIN (強力な認証機能) を設定するには、そのユーザーがプロセスを完了するために [多要素認証 (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) を直近で使用している必要があります。

## Web アカウント マネージャーでのシングル サインオン

シングルサインオン (SSO) では、ユーザーの個人、職場または学校アカウントを使用して、ユーザーがパスワードを使用することなくデバイスにサインインできるようになります。 ユーザーは、「[Web アカウント マネージャー API](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)」 を介して、すべての統合されたアプリやサービスに SSO で自動的に承認されます。

1つのアプリケーションを使用して ID を追加した後は、ユーザーの同意があれば、システム レベルの統合を使用してすべてのアプリとサービスで利用できるようになります。 これにより、アプリにサインインする負担が大幅に軽減され、シームレスな ID 体験を提供します。

Web アカウント マネージャー API の実装の詳細については、「[Web アカウント マネージャー API の実装](https://docs.microsoft.com/windows/uwp/security/web-account-manager)」 を参照してください。

  ![セキュリティ API](images/security-api-img.png)
  
特殊な認証要件を持つアプリ スイートの場合、Web アカウント マネージャー (WAM) フレームワークは、カスタム ID プロバイダーにも拡張できます。 ユーザーは、Microsoft Store からユニバーサル Windows プラットフォーム (UWP) アプリとしてパッケージ化されたカスタム ID プロバイダーをダウンロードし、その ID プロバイダーと統合された他のアプリで SSO を有効にできます。

カスタムの WAM ID プロバイダーの実装の詳細については、「[カスタム WAM ID プロバイダーの API リファレンス](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)」 を参照してください。

## WebAuthn を使用した Windows Hello および FIDO2 のサインイン

HoloLens 2は、パスワードを使用しないユーザーの資格情報 （Windows Hello や FIDO2セキュリティ キーなど） を採用して、Microsoft Edge を介して Web 上で安全にサインインしたり、WebAuthn をサポートする Web サイトにアクセスしたりすることができます。 FIDO2は、標準ベースのデバイスを利用してオンライン サービスへの認証を行うために、ユーザーの資格情報を利用することを可能にします。

> [!Note]
> [WebAuthn](https://www.w3.org/TR/webauthn/) と FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) の仕様は、サービスに実装されています。 WebAuthn および FIDO2 によって指定された署名済みメタデータは、ユーザーが存在していたかどうかなどの情報を提供し、ローカル ジェスチャを介して認証を検証します。

Windows Hello の場合と同様に、ユーザーが FIDO2 資格情報を作成して登録すると、デバイス (HoloLens 2 または FIDO2 セキュリティ キー) によってデバイス上に秘密キーと公開キーが生成されます。 秘密キーはデバイスに安全に保存され、生体認証や PIN などのローカル ジェスチャを使用してロックを解除した後にのみ使用できます。 秘密キーが保存される場合は、公開キーがクラウドの Microsoft アカウントシステムに送信され、関連付けられているユーザー アカウントで登録されます。

MSA および Azure AD アカウントでサインインすると、システムは生成された番号またはデータ変数を HoloLens 2 または FIDO2 デバイスに送信します。 HoloLens 2 またはデバイスは、秘密キーを使用して ID に署名します。 署名済みの ID とメタデータは、Microsoft アカウント システムに返送され、公開キーを使用して確認されます。

Windows Hello および FIDO2 デバイスは、HoloLens デバイス、特に組み込みのトラステッド プラットフォーム モジュールの安全な孤立領域に基づいて、資格情報を実装します。 TPM の孤立領域には秘密キーが格納され、ロックを解除するには生体認証または PIN が必要です。 同様に、FIDO2セキュリティ キーは、秘密キーを格納する安全な孤立領域を内蔵した小型の外部デバイスであり、ロックを解除するには生体認証または PIN が必要です。

どちらのオプションでも、1 つの手順で 2 要素認証が提供されます。この認証では、正常にサインインするには、登録されたデバイスと生体認証または PIN の両方が必要です。 詳細については、以下の「FIDO2 セキュリティ キーのグラフィックとプロセスを使用した強力な認証」を参照してください。

### FIDO2 セキュリティ キーを使用した強力な認証

  ![FIDO img](images/security-fido2-whfb-smaller.png)

1. ユーザーが FIDO2 セキュリティ キーを HoloLens 2 に接続します
1. Windows が FIDO2 セキュリティ キーを検出します
1. HoloLens が認証要求を送信します
1. AzureAD が nonce を送り返します
1. ユーザーがジェスチャーを完了して、セキュリティ キーの安全な孤立領域にあるプライベート キー ストアのロックを解除します
1. FIDO2 セキュリティ キーは、プライベート キーを使用して nonce に署名します
1. 署名された nonce を含む PRT トークン要求が Azure AD に送信されます
1. Azure AD が FIDO キーを確認します
1. Azure AD は PRT と TGT を返し、リソースへのアクセスを有効にします

MSA と Azure AD は、WebAuthn を実装してパスワードレス認証をサポートする最初の証明書利用者の 1 つです。

アプリケーションや SDK で WebAuthn を使用する方法の詳細については、「[WebAuthn API を使用して Windows 10 のパスワードレス認証を行う](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/webauthnapis)」を参照してください。

HoloLens 2 は、「[Azure Active Directory パスワードレス サインイン - FIDO2 セキュリティ キー](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless#fido2-security-keys)」に記載されている要件を満たすように実装された FIDO2 セキュリティ デバイスをサポートします。

## ローカル アカウント

オフライン モードでの展開のために、単一のローカル アカウントを構成することができます。 ローカル アカウントは既定では有効になっていません。デバイスのプロビジョニング中に構成する必要があります。 パスワードを使用してサインインする必要があります。また、代替認証方法 [(Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview) や Windows Hello など) は [サポートされていません](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)。

HoloLens ユーザー アカウントの詳細については、「[HoloLens Identity](https://docs.microsoft.com/hololens/hololens-identity)」 を参照してください。

IT管理者は、[AllowMicrosoftAccountConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection) を通じて、ユーザーがメール関連ではない接続の認証とサービスに MSA アカウントを使用できるようにするかどうかを調整します。 パスワード構成ポリシー、idling ポリシー、ロック画面ポリシーについては、「[デバイス ロック](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock)」を参照してください。
