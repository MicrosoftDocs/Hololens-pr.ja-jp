---
title: 外部クライアントの展開ガイド
description: 外部クライアント向けの HoloLens 2 の展開ガイド (例としてリモートアシスタンスを使用)
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/12/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 56930ceea05cd5713b9c7eb57e0967a9d0cd4988
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309337"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>リモートアシスタンスを使用した外部クライアントへの HoloLens 2 の展開

このガイドは、次の目標を持つ IT プロフェッショナルが組織で Microsoft HoloLens 2 デバイスを展開するのに役立ちます。

1. Cloud connect HoloLens 2 デバイス
1. ローン HoloLens 2 デバイスを外部クライアントに使用する
1. セキュリティで保護された貸与デバイス

このガイドでは、多くの HoloLens 2 展開シナリオに適用される [一般的な hololens 2 展開の推奨事項](#general-deployment-recommendations-and-instructions) と、外部使用のためにリモートアシスタンスを展開するときの [一般的な懸念](#common-concerns) 事項について説明します。

## <a name="scenario-description"></a>シナリオの説明

このドキュメントでは、Contoso 社は、短期または長期的に使用するために、外部クライアントのプラントに HoloLens 2 デバイスを発送することを希望しています。 クライアントがサポートサービスメカニズムを必要とする場合、クライアントは Contoso 社から提供された資格情報を使用して HoloLens 2 デバイスにログインし、リモートアシスタンスを使用して Contoso 社の専門家に問い合わせます。

リモートアシスタンスの詳細について [は、こちら](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)を参照してください。

### <a name="requirements-for-this-scenario"></a>このシナリオの要件

1. [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. モバイル Device Manager ( [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)など)
1. リモート支援ライセンス
    1. [リモートアシスタンスの購入](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [試用版リモートアシスタンス](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>一般的な懸念事項

- [外部のクライアントが互いに通信することができないようにする方法](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [クライアントが会社のリソースにアクセスできないようにする方法](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [アプリを制限する方法](#how-to-restrict-apps)
- [パスワードを管理する方法](#how-to-manage-passwords)
- [クライアントがチャット履歴にアクセスできないようにする方法](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>外部のクライアントが互いに通信することができないようにする方法

リモートアシスタンス HoloLens から HoloLens への呼び出しはサポートされていないため、クライアントは検索できますが、相互に通信することはできません。 クライアントが検索して呼び出すことができるユーザーをさらに制限するために、  [情報バリア](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) はクライアントが通信できるユーザーを制限することができます。 考慮すべきもう1つのオプションは、スコープを指定した[ディレクトリ検索](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)の使用

 > [!NOTE]
> シングルサインオンが有効になっているため、 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)を使用してブラウザーを無効にすることが重要です。 外部クライアントがブラウザーを開き、チームの web バージョンを使用する場合、クライアントは通話/チャット履歴にアクセスできます。

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>クライアントが会社のリソースにアクセスできないようにする方法

考慮すべき2つのオプションがあります。

1つ目のオプションは、マルチレイヤーアプローチです。

1. ユーザーが必要とするライセンスのみを割り当てます。 OneDrive、Outlook、SharePoint、Yammer などをユーザーに割り当てないと、それらのリソースにアクセスすることはできません。 ユーザーが必要とするライセンスは、リモートアシスタンス、Intune、および AAD のライセンスのみです。
1. クライアントにアクセスしたくないアプリ (電子メールなど) をブロックします (「 [アプリを制限する方法」を](#how-to-restrict-apps)参照してください)。
1. ユーザー名とパスワードをクライアントで共有しないでください。 HoloLens 2 にログインするには、電子メールと数字の PIN が必要です。

2つ目のオプションは、クライアントをホストする別のテナントを作成することです (「イメージ1.1」を参照してください)。

**イメージ1.1**

![サービステナントの画像](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>アプリを制限する方法

[キオスクモード](https://docs.microsoft.com/hololens/hololens-kiosk) または [WDAC (Windows Defender Application Control)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) は、アプリケーションを制限するためのオプションです。

### <a name="how-to-manage-passwords"></a>パスワードを管理する方法

1. パスワードの有効期限を削除します。 ただし、これにより、アカウントが侵害される可能性が高くなります。 NIST パスワードの推奨事項は、30-90 日おきにパスワードを変更することです。
1. HoloLens 2 デバイスのパスワードの有効期限を90日を超えるように拡張します。
1. デバイスは、パスワードを変更するために Contoso に返される必要があります。 ただし、デバイスが90日以上クライアントのプラントにあると予想される場合は、問題が発生する可能性があります。  
1. 複数のクライアントに送信されるデバイスの場合は、デバイスをクライアントに発送する前にパスワードをリセットします。

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>クライアントがチャット履歴にアクセスできないようにする方法

リモートアシスタンスは、各セッションの後にチャットの履歴をクリアします。 ただし、チャットの履歴は、Microsoft Teams ユーザーが使用できるようになります。

> [!NOTE]
> シングルサインオンが有効になっているため、 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)を使用してブラウザーを無効にすることが重要です。 外部クライアントがブラウザーを開き、チームの web バージョンを使用する場合、クライアントは通話/チャット履歴にアクセスできます。

## <a name="general-deployment-recommendations-and-instructions"></a>デプロイに関する一般的な推奨事項と手順

HoloLens 2 のデプロイ手順については、次のことをお勧めします。

1. 最新の [HOLOLENS OS リリース](https://aka.ms/hololens2download) をベースラインビルドとして使用します。
1. ユーザーベースまたはデバイスベースのライセンスを割り当てる:
    1. ユーザーベースおよびデバイスベースのライセンスは、次の手順に従います。
        1. [AAD にグループを作成し、](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) HOLOLENS/RA ユーザーのメンバーを追加します。
        1. [デバイスベースまたはユーザーベースのライセンス](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) をこのグループに割り当てます。
        1. OptionalMDM ポリシーのグループを対象にすることができます。

1. デバイスは、AAD をテナントに参加させ、 [自動登録](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)し、 [自動パイロット](https://docs.microsoft.com/hololens/hololens2-autopilot)によって構成する必要があります。
    1. デバイスの最初のユーザーがデバイスの所有者であることに注意してください。
    1. デバイスが AAD に参加している場合は、結合を実行したユーザーがデバイスの所有者になります。
    1. 詳細については、「 [デバイスの所有者](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)」を参照してください。
1. テナントは、テナントにのみ参加できるようにデバイスを[ロック](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot)します。
    1. **追加リンク:** [テナントロック CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)。
1. グローバルに割り当てられたアクセスを使用してキオスクを [構成します](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)。
1. 次の (オプション) 機能を無効にすることをお勧めします。
    1. [ここで](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)、デバイスを開発者モードにする機能。
    1. HoloLens を PC に接続して日付をコピーする機能は、 [USB を無効](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)にします。
       > [!NOTE]
        > Usb を無効にし、USB を使用してプロビジョニングパッケージをデバイスに適用する機能が必要な場合は、 [**こちら**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)の手順に従ってください。

1. [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)を使用して、HoloLens 2 デバイスでアプリを許可またはブロックします。
1. セットアップの一部として、リモートアシスタンスを最新バージョンに更新します。 これを行うには、次の2つのオプションがあります。
    1. これを行うには、[Windows **Microsoft Store--> リモートアシスタンス--> およびアプリの更新**] に移動します。
    1. [Applicationmanagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) -アプリの自動更新を許可します。既定では有効になっています。 デバイスを接続したままにして、更新プログラムを受信します。
1. ネットワーク設定を除く[すべての設定ページを無効](https://docs.microsoft.com/hololens/settings-uri-list)にして、ユーザーがクライアントサイトでゲストネットワークに接続できるようにします。
1. [HoloLens 更新プログラムの管理](https://docs.microsoft.com/hololens/hololens-updates)
    1. OS の [更新プログラムを制御](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) したり、自由にフローを許可したりするためのオプションです。
1. [一般的なデバイスの制限](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)。
