---
title: HoloLens のユーザー ID とサインインを管理する
description: HoloLens のユーザー ID、セキュリティ、サインインを管理します。
keywords: HoloLens、ユーザー、アカウント、aad、adfs、microsoft アカウント、msa、資料、参照
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
ms.openlocfilehash: 17d55d8cd5540c9beaf4b7348688c362b079f5da
ms.sourcegitcommit: ab9e70e68d546cc6965e1569e5d914995fa508da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "10955449"
---
# HoloLens のユーザー ID とサインインを管理する

> [!NOTE]
> この記事は、IT プロフェッショナルおよびテクニカル サポートのためのテクニカル リファレンスです。 HoloLens のセットアップ手順を探している場合は[、「HoloLens (1st gen) のセットアップ」または](hololens1-start.md)[「HoloLens 2](hololens2-start.md)のセットアップ」を参照してください。

他の Windows デバイスと同様に、HoloLens は常にユーザー コンテキストで動作します。 常にユーザー ID が存在します。 HoloLens では、他の Windows 10 デバイスとほぼ同じ方法で ID が評価されます。 この記事では、HoloLens の ID についての詳しいリファレンスを示し、他の Windows 10 デバイスとの HoloLens との区別に関して注文しています。

HoloLens では、いくつかの種類のユーザー ID をサポートしています。 サインインには 1 つ以上のユーザー アカウントを使用できます。 HoloLens の ID の種類と認証オプションの概要を示します。

| ID の種類 | デバイスあたりのアカウント | 認証オプション |
| --- | --- | --- |
| [Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/) | 64 | <ul><li>Azure Web 資情報プロバイダー</li><li>Azure Authenticator アプリ</li><li>Biometric (アイルドル) &ndash; HoloLens 2 のみ</li><li>&ndash;HoloLens 2 に必要な PIN オプション (1st gen) の場合</li><li>パスワード</li></ul> |
| [Microsoft アカウント (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Biometric (アイルドル) &ndash; HoloLens 2 のみ</li><li>&ndash;HoloLens 2 に必要な PIN オプション (1st gen) の場合</li><li>パスワード</li></ul> |
| [ローカル アカウント](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | パスワード |

クラウド接続されているアカウント (AAD と MSA) では、Azure サービスを使用できるため、より多くの機能が含まれています。  

## ユーザーのセットアップ

新しいユーザーをセットアップする最も一般的な方法は、HoloLens の既定の操作環境 (OOBE) 中に行う方法です。 セットアップ中に、HoloLens では、デバイスで使用するアカウントを使用してサインインするように求められます。 このアカウントには、コンシューマー Microsoft アカウント、または Azure で構成されているエンタープライズ アカウントを使用できます。 [HoloLens (1st ジェント)](hololens1-start.md)または[HoloLens 2 のセットアップを行います](hololens2-start.md)。

他のデバイス上の Windows と同様に、セットアップ時にサインインするとデバイス上にユーザー プロファイルが作成されます。 ユーザー プロファイルには、アプリとデータが格納されます。 また、同じアカウントで Windows アカウント マネージャー API を使用して、Edge や Skype などのアプリのシングル サインオンも提供します。  

HoloLens にサインインするためにエンタープライズまたは組織のアカウントを使用している場合、HoloLens は組織の IT インフラストラクチャに加わります。 このサブスクリプションを使用すると、IT 管理者がモバイル デバイス管理 (MDM) を構成して、グループ ポリシーを HoloLens に送信できます。

既定では、他の Windows 10 デバイスの場合と同様に、HoloLens が再起動またはスタンバイから再開されたときに再度サインインする必要があります。 設定アプリを使用してこの動作を変更することも、動作をグループ ポリシーで制御することもできます。

### リンクされているアカウント

デスクトップ 版の Windows では、追加の Web アカウント資料を HoloLens アカウントにリンクできます。 このようなリンク設定により、アプリ間またはアプリ (ストアなど) 間のリソースにアクセスしたり、個人と時間のリソースにアクセスしたりすることが簡単にできます。 アカウントをデバイスに接続したら、アプリをアプリに追加するアクセス許可をアプリに付与して、各アプリに個別にサインインする必要がないようにすることができます。

アカウントをリンクする場合、画像やダウンロードなど、デバイス上に作成されたユーザー データは分離されません。  

### マルチユーザー サポートのセットアップ (AAD のみ)

HoloLens では、同じ AAD テナントから複数のユーザーをサポートします。 この機能を使用するには、組織に属しているアカウントを使用してデバイスをセットアップする必要があります。 その後、同じテナントの他のユーザーはサインイン画面からデバイスにサインインするか、スタート パネルでユーザー タイルをタップします。 一度にサインインできるユーザーは 1 つのみです。 ユーザーがサインインすると、HoloLens は前のユーザーからサインアウトします。  

すべてのユーザーは、デバイスにインストールされているアプリを使用できます。 ただし、各ユーザーには独自のアプリ データと環境設定があります。 デバイスからアプリを削除すると、すべてのユーザーのアプリから削除されます。  

AAD アカウントでデバイスを設定しても、Microsoft アカウントを使ってデバイスにサインインすることはできません。 以降のアカウントはすべて、デバイスと同じテナントから AAD アカウントを使用する必要があります。 Microsoft アカウントを [使用してサインインしてサポート](hololens-identity.md#setting-up-multi-user-support-aad-only) しているアプリ (Microsoft Store など) にサインインすることもできます。 デバイスにサインインするには AAD アカウントを使用して Microsoft アカウントに変更するには、 [デバイスをリフラッシュする必要があります](hololens-recovery.md#clean-reflash-the-device)。

> [!NOTE]
> **HoloLens (1st gen)** は[、Windows Holographic for Business](hololens-upgrade-enterprise.md)の一部として[Windows 10 4 月の更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)プログラムで複数の AAD ユーザーをサポートする開く開入を開始しました。

## ユーザーの削除

[設定] の [アカウント] に移動**Settings**すると、ユーザーを  >  **デバイスから**  >  **削除できます**。 このアクションでは、そのユーザーのすべてのアプリ データをデバイスから削除することで、領域を取り戻します。  

## アプリ内でシングル サインオンを使用する

アプリ開発者は、他の Windows デバイスと同様に、Windows アカウント マネー [ジャー API](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)を使用して HoloLens でリンクされた ID を利用できます。 これらの API のコード サンプルは、GitHub: [Web アカウント管理のサンプルです](https://go.microsoft.com/fwlink/p/?LinkId=620621)。

アカウント情報、2 要素認証などのアカウントで発生する場合があるアカウントで中止される場合は、アプリが認証トークンを要求したときに処理する必要があります。

アプリで以前にリンクしていなかれていない特定の種類のアカウントが必要な場合は、アプリからアカウントを追加するように要求されることがあります。 この要求により、アプリのお子様として起動するアカウント設定ウィンドウがトリガーされます。 2D アプリの場合、このウィンドウはアプリの中央に直接表示されます。 Unity アプリの場合、この要求は簡単にホログラフィック アプリからユーザーに接続して子ウィンドウを表示します。 このウィンドウでのコマンドと操作のカスタマイズについては [、WebAccountCommand Class を参照してください](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)。

## エンタープライズとその他の認証

アプリで NTLM、基本、Kerberos など、他の種類の認証を使用している場合は、Windows 資ーデン [シャル UI を使用して](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) 、ユーザーの資情報の収集、プロセス、保存を行えます。 これらの資格情報を収集する操作環境は、他のクラウド ベースのアカウントが中止に近く、UI を表示する 2D アプリの上部に子アプリとして表示されます。これは、UI を表示する米国アプリの一時停止アプリとして表示されます。

## 非予期 API

HoloLens 用に開発とは異なる方法の 1 つは [、OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API が完全にはサポートされていないことです。 プライマリ アカウントが正常な状態である場合、API はトークンを返しますが、この記事で説明するアカウントの UI は表示せず、アカウントを正しく認証できなくなります。

## よく寄せられる質問

### HoloLens (1st Gen) で Windows Hello for Business はサポートされていますか?

HoloLens (1st Gen) では、Windows Hello for Business (PIN を使用したサインインをサポート) がサポートされています。 HoloLens で Windows Hello for Business の PIN サインインを許可するには:

1. HoloLens デバイスは [MDM で管理する必要があります](hololens-enroll-mdm.md)。
1. デバイスに対して Windows Hello for Business を有効にする必要があります。 (Microsoft[Intune の手順を参照してください](https://docs.microsoft.com/intune/windows-hello))。
1. HoloLens では、ユーザーは、設定**の**サインイン オプション  >  **の**  >  **追加 PIN**を使用して PIN を設定できます。

> [!NOTE]
> Microsoft アカウントを使用してサインインするユーザーは、[設定] サインイン オプションで**Settings**PIN を  >  **Sign-in Options**  >  **設定することもできます**。 この PIN は [、Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)for Business に代替える [Windows Hello に関連付けられています](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)。

### HoloLens 2 で実装された生文認証はどのようにしていませんか?

HoloLens 2 は Iris 認証をサポートしています。 Iris は Windows Hello テクノロジに基づいており、Azure Active Directory と Microsoft アカウントの両方で使用できます。 Iris は他の Windows Hello テクノロジと同じように実装され、生生性のセキュリティは 1/100K の 2 月 1 日に実装されます。

Windows Hello の生体認証要件と詳細については、ここを [参照してください](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements)。 [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)と[Windows Hello for Business の詳細をご覧ください](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)。 

### アカウントの種類がサインイン動作に与える影響

サインイン用のポリシーを適用する場合、ポリシーは常に考慮されます。 サインインのポリシーが適用されなかった場合、これらはアカウントの種類ごとに既定の動作になります。

- **Azure AD:** 既定で認証を要求し、認証を要求しなくなった**Settings**ように設定によって構成が可能です。
- **Microsoft アカウント**: ロック動作は自動でのロック解除を検行する方法とは異なりますが、再びサインインする必要があります。
- **ローカル アカウント**: 設定で構成できないパスワードの形式で認証を要求 **します。**

> [!NOTE]
> 現在、アクティビティ タイマーはサポートされていません。つまり、デバイスが StandBy に接続した場合に **のみ AllowIdleReturnPassword** ポリシーが応答されることを意味します。

## その他の資料

Windows 10 セキュリティと ID ドキュメントのユーザー ID 保護と認証の詳細については、こ [ちらを参照してください](https://docs.microsoft.com/windows/security/identity-protection/)。

Azure ハイブリッド ID ドキュメントを使用した場合のハイブリッド ID インフラストラクチャ [の設定について説明します](https://docs.microsoft.com/azure/active-directory/hybrid/)。
