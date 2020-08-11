---
title: HoloLens のユーザー ID とサインインを管理する
description: HoloLens のユーザー id、セキュリティ、サインインを管理します。
keywords: HoloLens、ユーザー、アカウント、aad、adfs、microsoft アカウント、msa、資格情報、参照
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: scooley
ms.author: scooley
ms.date: 1/6/2020
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
ms.openlocfilehash: 9829b90445be7f73cfdc0e330d9d57af1ef0a44b
ms.sourcegitcommit: 8b56f4b9b5f9c928fc361f18efcbea729055a0b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "10919124"
---
# HoloLens のユーザー ID とサインインを管理する

> [!NOTE]
> この記事は、IT プロフェッショナルと技術のお熱心な製品を対象としています。 HoloLens のセットアップ手順については、「HoloLens のセットアップ[(第1世代)](hololens1-start.md)」または「[hololens 2](hololens2-start.md)のセットアップ」を参照してください。

他の Windows デバイスと同様に、HoloLens は常にユーザーコンテキストで動作します。 常にユーザー id があります。 HoloLens では、他の Windows 10 デバイスとほぼ同じ方法で id が扱われます。 この記事では、HoloLens での id の詳細について説明し、HoloLens が他の Windows 10 デバイスとどのように異なるかについて重点的に説明します。

HoloLens は、いくつかの種類のユーザー id をサポートしています。 1つ以上のユーザーアカウントを使ってサインインすることができます。 HoloLens の id の種類と認証オプションの概要を以下に示します。

| Id 型 | デバイスあたりのアカウント数 | 認証オプション |
| --- | --- | --- |
| [Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/) | 64 | <ul><li>Azure web credential provider</li><li>Azure Authenticator アプリ</li><li>バイオメトリクス (虹彩) &ndash; HoloLens 2 のみ</li><li>Hololens &ndash; (最初の gen) での PIN (第1世代)、hololens 2 には必須</li><li>パスワード</li></ul> |
| [Microsoft アカウント (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 件 | <ul><li>バイオメトリクス (虹彩) &ndash; HoloLens 2 のみ</li><li>Hololens &ndash; (最初の gen) での PIN (第1世代)、hololens 2 には必須</li><li>パスワード</li></ul> |
| [ローカルアカウント](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 件 | パスワード |

クラウドに接続されたアカウント (AAD および MSA) には、Azure サービスを使うことができる機能が用意されています。  

## ユーザーのセットアップ

新しいユーザーを設定する最も一般的な方法は、HoloLens の box (OOBE) 環境中です。 セットアップ時に、HoloLens は、デバイスで使用するアカウントを使ってサインインするようにユーザーに求めます。 このアカウントは、コンシューマーの Microsoft アカウントまたは Azure で構成されているエンタープライズアカウントにすることができます。 「Hololens のセットアップ[(第1世代)](hololens1-start.md) 」または「 [hololens 2](hololens2-start.md)」を参照してください。

他のデバイスの Windows と同様に、セットアップ時にサインインすると、デバイスにユーザープロファイルが作成されます。 ユーザープロファイルには、アプリとデータが格納されます。 同じアカウントでは、Windows アカウントマネージャー Api を使用して、Edge や Skype などのアプリのシングルサインオンも提供されます。  

企業または組織のアカウントを使用して HoloLens にサインインした場合、HoloLens は組織の IT インフラストラクチャに登録します。 この登録によって、IT 管理者は、HoloLens にグループポリシーを送信するようにモバイルデバイス管理 (MDM) を構成することができます。

既定では、他の Windows 10 デバイスと同様に、HoloLens を再起動またはスタンバイ状態から再開するには、もう一度サインインする必要があります。 設定アプリを使用してこの動作を変更したり、グループポリシーによって動作を制御したりすることができます。

### リンクされたアカウント

デスクトップバージョンの Windows と同様に、追加の web アカウントの資格情報を HoloLens アカウントにリンクすることができます。 このようなリンクを使用すると、アプリ (ストアなど) のリソースへのアクセスや、個人リソースと作業リソースへのアクセスの組み合わせが簡単になります。 アカウントをデバイスに接続した後は、各アプリに個別にサインインする必要がないように、デバイスを使用するアクセス許可をアプリに与えることができます。

アカウントをリンクしても、画像やダウンロードなど、デバイス上で作成されたユーザーデータは分離されません。  

### マルチユーザーサポートのセットアップ (AAD のみ)

> [!NOTE]
> **HoloLens (第1世代)** では、Windows[ホログラフィック](hololens-upgrade-enterprise.md)[年 4 2018 月の更新プログラム](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)で複数の AAD ユーザーのサポートが開始されました。

HoloLens では、同じ AAD テナントの複数のユーザーがサポートされています。 この機能を使用するには、組織に属しているアカウントを使用して、デバイスをセットアップする必要があります。 その後、同じテナントの他のユーザーが、サインイン画面から、またはスタートパネルのユーザータイルをタップして、デバイスにサインインすることができます。 一度にサインインできるユーザーは1人だけです。 ユーザーがサインインすると、以前のユーザーは、HoloLens からサインアウトされます。  

すべてのユーザーが、デバイスにインストールされているアプリを使うことができます。 ただし、各ユーザーには、独自のアプリデータと基本設定があります。 デバイスからアプリを削除すると、すべてのユーザーに対してアプリが削除されます。  

## ユーザーの削除

[他のユーザーアカウントの**設定**] に移動して、デバイスからユーザーを削除でき  >  **Accounts**  >  **Other people**ます。 この操作を行うと、デバイスからそのユーザーのアプリデータがすべて削除され、領域がクリアされます。  

## アプリ内でシングルサインオンを使用する

アプリの開発者は、他の Windows デバイスの場合と同様に、 [Windows アカウントマネージャーの api](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)を使って、HoloLens でリンクされた id を利用できます。 [ここで](https://go.microsoft.com/fwlink/p/?LinkId=620621)は、これらの api のコードサンプルをいくつか紹介します。

アカウント情報に対するユーザーの同意を要求する、2要素認証など、発生する可能性があるアカウント割り込みは、アプリが認証トークンを要求したときに処理される必要があります。

アプリで、以前にリンクされていない特定のアカウントの種類が必要な場合は、アプリでユーザーに追加するように求めるメッセージを表示することができます。 この要求によって、アプリのモーダル子として [アカウント設定] ウィンドウが起動されます。 2D アプリの場合、このウィンドウはアプリの中央に直接レンダリングされます。 Unity アプリの場合、この要求は一時的に、ホログラフィックアプリから子ウィンドウを表示するために、ユーザーを一時的に受け取ります。 このウィンドウでのコマンドとアクションのカスタマイズについて詳しくは、「 [Webaccountcommand クラス](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)」をご覧ください。

## 企業およびその他の認証

アプリで、NTLM、Basic、Kerberos などの他の種類の認証を使用している場合は、 [Windows 資格情報 UI](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI)を使って、ユーザーの資格情報の収集、処理、格納を行うことができます。 これらの資格情報を収集するためのユーザーエクスペリエンスは、他のクラウド主導のアカウント割り込みと非常に似ており、2D アプリの上に子アプリとして表示されます。または、UI を表示するために Unity アプリを一時的に中断します。

## 廃止 Api

HoloLens 用の開発は、 [Onlineidauthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API が完全にはサポートされていないという点が異なります。 API はトークンを返しますが、プライマリアカウントが適切である場合は、この記事に記載されているような割り込みを行っても、ユーザーの UI が表示されず、アカウントが正しく認証されませんでした。

## よく寄せられる質問

### Windows Hello for Business は HoloLens (第1世代) でサポートされていますか?

Windows Hello for Business (PIN の使用をサポートします) は、HoloLens (第1世代) でサポートされています。 HoloLens で Windows Hello for Business PIN のサインインを許可するには、次の操作を行います。

1. HoloLens デバイスは[MDM によって管理](hololens-enroll-mdm.md)されている必要があります。
1. デバイスに対して Windows Hello for Business を有効にする必要があります。 ([「Microsoft Intune 用の手順」を参照して](https://docs.microsoft.com/intune/windows-hello)ください)。
1. HoloLens では、ユーザーは設定の**Settings**  >  **サインインオプション**を使用して pin を設定することができ  >  **Add PIN**ます。

> [!NOTE]
> Microsoft アカウントを使用してサインインしたユーザーも、[**設定**] の [  >  **サインインオプション]** で pin を設定でき  >  **Add PIN**ます。 この PIN は、 [Windows hello For business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)ではなく、 [windows hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)に関連付けられています。

### Iri 生体認証は、HoloLens 2 に実装されていますか?

HoloLens 2 は、虹彩認証をサポートしています。 虹彩は Windows Hello テクノロジをベースとしており、Azure Active Directory と Microsoft アカウントの両方で使用できるようにサポートされています。 虹彩認証は、他の Windows Hello テクノロジと同じ方法で実装され、1/10 の生体認証セキュリティを実現します。

Windows Hello の生体認証要件と仕様の詳細については、[こちら](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements)を参照してください。 [Windows hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)と[Windows hello for business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)について、詳細はこちらをご覧ください。 

### アカウントの種類は、サインインの動作にどのような影響を与えますか?

サインイン用のポリシーを適用する場合、ポリシーは常に考慮されます。 サインイン用のポリシーが適用されていない場合、これらは各アカウントの種類の既定の動作です。

- **AZURE AD**: 既定で認証が要求され、認証を要求しないように**設定**によって構成可能になります。
- **Microsoft アカウント**: ロック動作は、自動ロック解除の許可とは異なりますが、再起動時にサインイン認証が必要になります。
- **ローカルアカウント**: パスワードの形式で認証を要求しますが、**設定**では構成できません。

> [!NOTE]
> アイドル状態のタイマーは現在サポートされていません。つまり、デバイスがスタンバイ状態になったときに**AllowIdleReturnWithoutPassword**ポリシーが適用されるだけです。

## その他の資料

詳細について[は、「Windows 10 セキュリティと id](https://docs.microsoft.com/windows/security/identity-protection/)に関するドキュメント」を参照してください。

ハイブリッド id インフラストラクチャのセットアップの詳細については、「 [Azure ハイブリッド id ドキュメント](https://docs.microsoft.com/azure/active-directory/hybrid/)」を参照してください。
