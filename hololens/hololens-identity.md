---
title: HoloLens のユーザー ID とサインインを管理する
description: HoloLens デバイスのユーザー ID、マルチユーザー サポート、セキュリティ、エンタープライズ認証、サインインを管理する方法について説明します。
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
ms.openlocfilehash: 2d84658ef76ff2c5d8ef7dabe857892e7129a965
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400687"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>HoloLens のユーザー ID とサインインを管理する

> [!NOTE]
> この記事は、IT プロと技術ファン向けテクニカル リファレンスです。 HoloLens セットアップ手順を探している場合は[、「HoloLens (第 1](hololens1-start.md)世代) のセットアップ」または[「HoloLens 2](hololens2-start.md)のセットアップ」を参照してください。

他の Windows デバイスと同様に、HoloLens は常にユーザー コンテキストで動作します。 常にユーザー ID があります。 HoloLens は、他の Windows 10 デバイスとほぼ同じ方法で ID を処理します。 この記事は HoloLens での ID の詳細な参照であり、HoloLens が他の Windows 10 デバイスとどのように異なるかについて説明します。

HoloLens は、いくつかの種類のユーザー ID をサポートしています。 1 つ以上のユーザー アカウントを使用してサインインできます。 HoloLens の ID の種類と認証オプションの概要を次に示します。

| ID の種類 | デバイスごとのアカウント | 認証オプション |
| --- | --- | --- |
| [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (Azure AD Premium が必要) | 64 | <ul><li>Azure Web 資格情報プロバイダー</li><li>Azure Authenticator アプリ</li><li>生体認証 (Iris) &ndash; HoloLens 2 <sup> のみ 1</sup> </li><li>HoloLens 2 に必要な &ndash; HoloLens (第 1 世代) の PIN オプション</li><li>パスワード</li></ul> |
| [Microsoft アカウント (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>生体認証 (Iris) &ndash; HoloLens 2 のみ</li><li>HoloLens 2 に必要な &ndash; HoloLens (第 1 世代) の PIN オプション</li><li>パスワード</li></ul> |
| [ローカル アカウント](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | パスワード |

クラウド接続アカウント (Azure ADおよび MSA) は、Azure サービスを使用できる機能を提供します。  

> [!NOTE]
> 1 - HoloLens 2 デバイスは最大 64 の Azure AD アカウントをサポートすることができますが、虹彩認証に登録できるアカウントは 10 件のみです。 これは、Windows Hello for Business の他 [の生体認証オプションと一致しています](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)。

## <a name="setting-up-users"></a>ユーザーの設定

新しいユーザーを設定する最も一般的な方法は、HoloLens のアウトオブボックス エクスペリエンス (OOBE) の間です。 セットアップ中に、HoloLens は、デバイスで使用するアカウントを使用してサインインするようにユーザーに求めるメッセージを表示します。 このアカウントには、コンシューマー Microsoft アカウントまたは Azure で構成されているエンタープライズ アカウントを指定できます。 [「HoloLens のセットアップ (第 1](hololens1-start.md)世代)または[HoloLens 2」を参照してください](hololens2-start.md)。

他のデバイスの Windows と同様に、セットアップ中にサインインすると、デバイスにユーザー プロファイルが作成されます。 ユーザー プロファイルには、アプリとデータが格納されます。 また、同じアカウントは、Windows アカウント マネージャー API を使用してエッジや Skype などのアプリにシングル サインオンを提供します。  

企業または組織のアカウントを使用して HoloLens にサインインする場合、HoloLens は組織の IT インフラストラクチャに登録します。 この登録により、IT 管理者は、HoloLens にグループ ポリシーを送信するモバイル デバイス管理 (MDM) を構成できます。

既定では、他の Windows 10 デバイスと同様に、HoloLens が再起動またはスタンバイ状態から再開するときにもう一度サインインする必要があります。 設定アプリを使用してこの動作を変更するか、グループ ポリシーで動作を制御できます。

### <a name="linked-accounts"></a>リンクされたアカウント

デスクトップ バージョンの Windows と同様に、追加の Web アカウント資格情報を HoloLens アカウントにリンクできます。 このようなリンクを使用すると、アプリ全体またはアプリ内のリソース (ストアなど) に簡単にアクセスしたり、個人用リソースと仕事用リソースへのアクセスを組み合わせたりできます。 アカウントをデバイスに接続した後、デバイスをアプリに使用するアクセス許可を付与して、各アプリに個別にサインインする必要が生じないので、アプリにアクセスできます。

アカウントをリンクしても、イメージやダウンロードなど、デバイス上に作成されたユーザー データは分離されません。  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>マルチユーザー サポートのセットアップ (Azure ADのみ)

HoloLens は、同じ Azure テナントから複数のユーザー ADします。 この機能を使用するには、組織に属するアカウントを使用してデバイスをセットアップする必要があります。 その後、同じテナントの他のユーザーは、サインイン画面から、またはスタート パネルでユーザー タイルをタップしてデバイスにサインインできます。 一度にサインインできるユーザーは 1 人のみです。 ユーザーがサインインすると、HoloLens は前のユーザーをサインアウトします。 デバイス上の最初のユーザーはデバイス所有者と見なされます。Azure AD参加の場合を除き、デバイスの所有者について詳しくは、以下をご [覧ください](security-adminless-os.md#device-owner)。

すべてのユーザーは、デバイスにインストールされているアプリを使用できます。 ただし、各ユーザーは独自のアプリ データと基本設定を持っています。 デバイスからアプリを削除すると、すべてのユーザーに対してアプリが削除されます。  

Azure ADアカウントで設定されたデバイスでは、Microsoft アカウントを使用してデバイスにサインインできません。 以降に使用するアカウントはすべて、デバイスAD同じテナントの Azure アカウントである必要があります。 Microsoft アカウントを [使用して、それをサポートするアプリ (Microsoft](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) ストアなど) にサインインできます。 デバイスにサインインするために Azure AD アカウントを使用して Microsoft アカウントに変更するには、デバイス [を再フラッシュする必要があります](hololens-recovery.md#clean-reflash-the-device)。

> [!NOTE]
> **HoloLens (第 1**世代) は[、Windows Holographic for Business](hololens-upgrade-enterprise.md)の一環として[、Windows 10 April 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)で複数の Azure AD ユーザーのサポートを開始しました。

## <a name="removing-users"></a>ユーザーの削除

[設定アカウント] [その他のユーザー]**** に移動して、デバイス  >  **から**  >  **ユーザーを削除できます**。 また、このアクションでは、デバイスからそのユーザーのすべてのアプリ データを削除することで領域を再利用します。  

## <a name="using-single-sign-on-within-an-app"></a>アプリ内でのシングル サインオンの使用

アプリ開発者は、他の Windows デバイスと同様に [、Windows](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)アカウント マネージャー API を使用して HoloLens でリンクされた ID を利用できます。 これらの API のコード サンプルの一部は、GitHub: [Web アカウント管理サンプルで使用できます](https://go.microsoft.com/fwlink/p/?LinkId=620621)。

アカウント情報に対するユーザーの同意の要求、2 要素認証など、発生する可能性があるアカウントの中断は、アプリが認証トークンを要求するときに処理する必要があります。

アプリで、以前にリンクされていない特定のアカウントの種類が必要な場合、アプリはユーザーにアカウントの追加を求めるメッセージをシステムに表示できます。 この要求は、アプリのモーダル子として起動するアカウント設定ウィンドウをトリガーします。 2D アプリの場合、このウィンドウはアプリの中央に直接レンダリングされます。 Unity アプリの場合、この要求はユーザーをホログラフィック アプリから短時間取り出して、子ウィンドウをレンダリングします。 このウィンドウでのコマンドとアクションのカスタマイズの詳細については [、「WebAccountCommand Class」を参照してください](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)。

## <a name="enterprise-and-other-authentication"></a>エンタープライズおよび他の認証

アプリで NTLM、Basic、Kerberos などの他の種類の認証を使用している場合は [、Windows Credential UI](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) を使用して、ユーザーの資格情報を収集、処理、および保存できます。 これらの資格情報を収集するユーザー エクスペリエンスは、他のクラウド駆動型アカウントの割り込みと非常に似ています。2D アプリの上に子アプリとして表示される場合や、UI を表示するために Unity アプリを短時間中断します。

## <a name="deprecated-apis"></a>非推奨の API

HoloLens の開発がデスクトップ向け開発と異なる方法の 1 つは [、OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API が完全にサポートされていない点です。 プライマリ アカウントが良好な状態にある場合、API はトークンを返しますが、この記事で説明されている割り込みでは、ユーザーの UI は表示されません。アカウントを正しく認証できません。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Windows Hello for Business は HoloLens (第 1 世代) でサポートされていますか?

Windows Hello for Business (PIN を使用してサインインをサポート) は、HoloLens (第 1 世代) でサポートされています。 HoloLens で Windows Hello for Business PIN サインインを許可するには、次の方法を実行します。

1. HoloLens デバイスは MDM [で管理する必要があります](hololens-enroll-mdm.md)。
1. デバイスの Windows Hello for Business を有効にする必要があります。 ([Microsoft Intune の手順を参照してください。](https://docs.microsoft.com/intune/windows-hello)
1. HoloLens では、ユーザーは [**** 設定] サインイン オプション [PIN の追加] を使用して  >  ****  >  **PIN**を設定できます。

> [!NOTE]
> Microsoft アカウントを使用してサインインするユーザーは、[設定] [サインイン**** オプション] [PIN の追加] で PIN  >  **を**  >  **設定することもできます**。 この PIN は[、Windows Hello for Business](https://support.microsoft.com/help/17215/windows-10-what-is-hello)ではなく[、Windows Hello に関連付けられている。](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>HoloLens 2 に虹彩生体認証を実装する方法

HoloLens 2 は虹彩認証をサポートしています。 Iris は Windows Hello テクノロジに基づいており、Azure Active Directory と Microsoft アカウントの両方で使用できます。 Iris は、他の Windows Hello テクノロジと同じ方法で実装され、生体認証セキュリティ FAR の 1/100K を実現します。

詳細については [、「Windows Hello の生体認証要件と仕様」](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) を参照してください。 ビジネス向け [Windows Hello と](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) Windows Hello [の詳細を参照してください](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)。 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>アカウントの種類がサインイン動作に与える影響

サインイン用のポリシーを適用する場合、ポリシーは常に考慮されます。 サインインのポリシーが適用されない場合は、アカウントの種類ごとに既定の動作を次に示します。

- **Azure AD**: 既定で認証を求め、認証を要求しなくなった場合は **設定** で構成できます。
- **Microsoft アカウント**: ロック動作は、自動ロック解除を許可する方法が異なりますが、再起動時にサインイン認証が必要です。
- **ローカル アカウント**: 常にパスワードの形式で認証を要求します。設定では構成 **できません**

> [!NOTE]
> 非アクティブ タイマーは現在サポートされていません。つまり **、AllowIdleReturnWithoutPassword** ポリシーは、デバイスが StandBy に入った場合にのみ尊重されます。

## <a name="additional-resources"></a>その他の資料

Windows 10 のセキュリティと ID に関するドキュメントで、ユーザー ID の保護と認証の [詳細について説明します](https://docs.microsoft.com/windows/security/identity-protection/)。

ハイブリッド ID インフラストラクチャのセットアップの詳細については [、Azure Hybrid ID ドキュメントを参照してください](https://docs.microsoft.com/azure/active-directory/hybrid/)。
