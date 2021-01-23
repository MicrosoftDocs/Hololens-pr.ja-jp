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
ms.openlocfilehash: d9b7bebd9fd326def4ddfc2982bfecb09cb14186
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283278"
---
# HoloLens のユーザー ID とサインインを管理する

> [!NOTE]
> この記事は、IT 技術者および技術技術者向けテクニカル リファレンスです。 HoloLens のセットアップ手順については[、「HoloLens (第 1](hololens1-start.md)世代) のセットアップ」または[「HoloLens 2](hololens2-start.md)のセットアップ」をご覧ください。

他の Windows デバイスと同様に、HoloLens は常にユーザー コンテキストで動作します。 常にユーザー ID があります。 HoloLens は、他の Windows 10 デバイスとほぼ同じ方法で ID を扱います。 この記事は、HoloLens での ID に関する詳しいリファレンスであり、HoloLens と他の Windows 10 デバイスとの違いについて説明します。

HoloLens は、いくつかの種類のユーザー ID をサポートしています。 1 つ以上のユーザー アカウントを使用してサインインできます。 HoloLens の ID の種類と認証オプションの概要を次に示します。

| ID の種類 | デバイスごとのアカウント | 認証オプション |
| --- | --- | --- |
| [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/) | 64 | <ul><li>Azure Web 資格情報プロバイダー</li><li>Azure Authenticator アプリ</li><li>生体認証 (虹彩) &ndash; HoloLens 2 <sup> のみ 1</sup> </li><li>HoloLens (第 1 世代) の PIN (省略可能 &ndash; )、HoloLens 2 に必要</li><li>パスワード</li></ul> |
| [Microsoft アカウント (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>生体認証 (虹彩) &ndash; HoloLens 2 のみ</li><li>HoloLens (第 1 世代) の PIN (省略可能 &ndash; )、HoloLens 2 に必要</li><li>パスワード</li></ul> |
| [ローカル アカウント](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | パスワード |

クラウド接続アカウント (Azure AD および MSA) では、Azure サービスを使用できる機能が多く提供されます。  

> [!NOTE]
> 1 - HoloLens 2 デバイスは最大 64 の Azure AD アカウントをサポートすることができますが、虹彩認証に登録できるのはそれらのアカウントの 10 台のみです。 これは [、Windows Hello for Business の他の生体認証オプションと一致しています](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)。

## ユーザーの設定

新しいユーザーをセットアップする最も一般的な方法は、HoloLens の Out-of-Box Experience (OOBE) です。 セットアップ中に、HoloLens はデバイスで使用するアカウントを使用してサインインするように求めるメッセージをユーザーに表示します。 このアカウントには、コンシューマー Microsoft アカウントまたは Azure で構成されているエンタープライズ アカウントを指定できます。 [「HoloLens (第 1 世代)](hololens1-start.md)または[HoloLens 2](hololens2-start.md)のセットアップ」をご覧ください。

他のデバイスの Windows と同様に、セットアップ中にサインインすると、デバイスにユーザー プロファイルが作成されます。 ユーザー プロファイルには、アプリとデータが格納されます。 また、同じアカウントは、Windows アカウント マネージャー API を使用して Edge や Skype などのアプリにシングル サインオンを提供します。  

企業または組織のアカウントを使用して HoloLens にサインインする場合、HoloLens は組織の IT インフラストラクチャに登録します。 この登録により、IT 管理者は、HoloLens にグループ ポリシーを送信するモバイル デバイス管理 (MDM) を構成できます。

既定では、他の Windows 10 デバイスと同様に、HoloLens が再起動するかスタンバイ状態から再開するときに、もう一度サインインする必要があります。 設定アプリを使ってこの動作を変更するか、グループ ポリシーで動作を制御できます。

### リンクされたアカウント

デスクトップ バージョンの Windows と同様に、追加の Web アカウント資格情報を HoloLens アカウントにリンクできます。 このようなリンクを使用すると、アプリ (ストアなど) 全体またはアプリ内のリソースに簡単にアクセスしたり、個人用リソースと仕事用リソースへのアクセスを組み合わせたりすることができます。 アカウントをデバイスに接続した後、デバイスを使用するアクセス許可をアプリに付与して、各アプリに個別にサインインする必要がなくなんかできます。

アカウントをリンクしても、イメージやダウンロードなど、デバイスで作成されたユーザー データは分離されません。  

### マルチユーザー サポートの設定 (Azure ADのみ)

HoloLens は、同じ Azure テナントから複数のユーザー ADします。 この機能を使用するには、組織に属するアカウントを使用してデバイスをセットアップする必要があります。 その後、同じテナントの他のユーザーは、サインイン画面からデバイスにサインインするか、スタート パネルのユーザー タイルをタップしてデバイスにサインインできます。 一度にサインインできるユーザーは 1 人のみです。 ユーザーがサインインすると、HoloLens は前のユーザーをサインアウトします。 デバイスの最初のユーザーはデバイスの所有者と見なされます。ただし、Azure AD Join の場合は、デバイスの所有者について詳しくは、以下をご [覧ください](security-adminless-os.md#device-owner)。

すべてのユーザーは、デバイスにインストールされているアプリを使用できます。 ただし、各ユーザーは独自のアプリ データと基本設定を持っています。 デバイスからアプリを削除すると、すべてのユーザーに対してアプリが削除されます。  

Azure AD アカウントでセットアップされたデバイスでは、Microsoft アカウントを使ったデバイスへのサインインは許可されません。 以降に使用されるアカウントはすべて、デバイスとADテナントの Azure アカウントである必要があります。 Microsoft アカウント [を使用して、その](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) アカウントをサポートするアプリ (Microsoft Store など) にサインインすることもできます。 デバイスにサインインするために Azure AD アカウントから Microsoft アカウントに変更するには、デバイス [を再フラッシュする必要があります](hololens-recovery.md#clean-reflash-the-device)。

> [!NOTE]
> **HoloLens (第 1**世代) は[、Windows Holographic for Business](hololens-upgrade-enterprise.md)の一部として[、Windows 10 April 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)で複数の Azure AD ユーザーのサポートを開始しました。

## ユーザーの削除

[設定] アカウントの [その他の**** ユーザー] に移動して、デバイス  >  **からユーザー**  >  **を削除できます**。 このアクションは、そのユーザーのすべてのアプリ データをデバイスから削除することで、領域を解放します。  

## アプリ内でのシングル サインオンの使用

アプリ開発者は、他の Windows デバイスと同様に [、Windows](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)アカウント マネージャー API を使用して、HoloLens 上のリンクされた ID を利用できます。 これらの API のコード サンプルの一部は、GitHub で入手できます [。Web アカウント管理のサンプルです](https://go.microsoft.com/fwlink/p/?LinkId=620621)。

アカウント情報に対するユーザーの同意の要求、2 要素認証など、発生する可能性があるアカウントの中断は、アプリが認証トークンを要求するときに処理する必要があります。

以前にリンクされていない特定のアカウントの種類がアプリで必要な場合、アプリはユーザーにアカウントの追加を求めるメッセージをシステムに表示できます。 この要求は、アカウント設定ウィンドウをトリガーして、アプリのモーダルな子として起動します。 2D アプリの場合、このウィンドウはアプリの中央に直接レンダリングされます。 Unity アプリの場合、この要求はユーザーをホログラフィック アプリから簡単に取り出して、子ウィンドウをレンダリングします。 このウィンドウのコマンドとアクションのカスタマイズについては [、「WebAccountCommand クラス」を参照してください](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)。

## エンタープライズおよび他の認証

アプリで NTLM、基本、Kerberos などの他の種類の認証を使用する場合は [、Windows 資格情報 UI](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) を使用して、ユーザーの資格情報を収集、処理、および保存できます。 これらの資格情報を収集するためのユーザー エクスペリエンスは、他のクラウド 駆動型アカウントの割り込みと非常に似ています。また、2D アプリの上に子アプリとして表示されます。また、UI を表示するために Unity アプリを一時的に中断します。

## 非推奨の API

HoloLens の開発とデスクトップ用の開発が異なる方法の 1 つは [、OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API が完全にはサポートされていない点です。 API は、プライマリ アカウントが良好な状態にある場合にトークンを返しますが、この記事で説明する割り込みではユーザーの UI が表示されないので、アカウントを正しく認証できません。

## よく寄せられる質問

### Windows Hello for Business は HoloLens (第 1 世代) でサポートされていますか?

Windows Hello for Business (PIN を使用したサインインをサポート) は、HoloLens (第 1 世代) でサポートされています。 HoloLens で Windows Hello for Business PIN サインインを許可するには、次の方法を使用します。

1. HoloLens デバイスは MDM [で管理する必要があります](hololens-enroll-mdm.md)。
1. デバイスで Windows Hello for Business を有効にする必要があります。 (Microsoft[Intune の手順を参照してください)。](https://docs.microsoft.com/intune/windows-hello)
1. HoloLens では、ユーザーは設定サインイン**** オプション [PIN の追加] を使用して  >  ****  >  **PIN**を設定できます。

> [!NOTE]
> Microsoft アカウントを使用してサインインするユーザーは、[設定] サインイン**** オプションの [PIN の追加] で PIN  >  **を**  >  **設定することもできます**。 この PIN は [、Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)for Business ではなく [、Windows Hello に関連付けされます](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)。

### HoloLens 2 に虹彩生体認証を実装する方法

HoloLens 2 は虹彩認証をサポートしています。 虹彩は Windows Hello テクノロジに基づいており、Azure Active Directory と Microsoft アカウントの両方で使用できます。 虹彩は、他の Windows Hello テクノロジと同じ方法で実装され、1/100K という生体認証セキュリティを実現します。

詳しくは [、Windows Hello の生体認証の要件と仕様](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) をご覧ください。 Windows Hello と [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) for Business について [詳しくは、次をご覧ください](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)。 

### アカウントの種類がサインイン動作に与える影響

サインイン用のポリシーを適用する場合、ポリシーは常に考慮されます。 サインインに関するポリシーが適用されなき場合、各アカウントの種類に対する既定の動作は次のとおりです。

- **Azure AD:** 既定で認証を要求し、認証を要求しなくなった場合は **[** 設定] で構成できます。
- **Microsoft アカウント**: ロック動作が異なって自動ロック解除が可能になりますが、再起動時にはサインイン認証が必要です。
- **ローカル アカウント**: 常にパスワードの形式で認証を要求し、[設定] で構成 **することはできません**

> [!NOTE]
> 現在、非アクティブ タイマーはサポートされていません。つまり **、AllowIdleReturnWithoutPassword** ポリシーは、デバイスが StandBy に入った場合にのみ考慮されます。

## その他の資料

ユーザー ID 保護と認証の詳細については [、Windows 10 のセキュリティ](https://docs.microsoft.com/windows/security/identity-protection/)と ID に関するドキュメントを参照してください。

ハイブリッド ID インフラストラクチャのセットアップに関する詳細については [、Azure ハイブリッド ID のドキュメントを参照してください](https://docs.microsoft.com/azure/active-directory/hybrid/)。
