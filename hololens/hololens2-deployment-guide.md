---
title: クラウドに接続されている HoloLens 2 を外部クライアントに展開する
description: 外部クライアント向けの HoloLens 2 の展開ガイド (例としてリモートアシスタンスを使用)
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/6/2021
ms.custom: ''
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: d5cd9c380e0d276f0a8aa9efac14cf44885446e5
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033400"
---
# <a name="deploy-cloud-connected-hololens-2-to-external-clients"></a>クラウドに接続されている HoloLens 2 を外部クライアントに展開する

このガイドは、 [クラウドに接続されたデプロイガイド](hololens2-cloud-connected-overview.md)を補足するものです。 これは、組織が短期または長期の使用のために外部クライアントの施設に HoloLens 2 デバイスを発送する必要がある状況で使用されます。 外部クライアントは、組織から提供された資格情報を使用して HoloLens 2 デバイスにログインし、[リモート](/dynamics365/mixed-reality/remote-assist/ra-overview)アシスタンスを使用して専門家に連絡します。 このガイドでは、ほとんどの外部 HoloLens 2 展開シナリオに適用される[一般的な HoloLens 2 展開の推奨事項](#general-deployment-recommendations)と、外部使用のためにリモートアシスタンスを展開するときの[一般的な考慮](#common-external-client-deployment-concerns)事項について説明します。 

## <a name="prerequisites"></a>必須コンポーネント

HoloLens 2 を外部にデプロイするには、[クラウドに接続されたデプロイガイド](hololens2-cloud-connected-overview.md)に従って、次のインフラストラクチャを配置する必要があります。

- MDM の自動登録を使用した Azure AD 参加-MDM 管理 (Intune)
- ユーザーが自分の会社のアカウントでサインインする (Azure AD)
    - デバイスごとに1つまたは複数のユーザーがサポートされています。

### <a name="remote-assist-licensing-and-requirements"></a>リモートアシスタンスのライセンスと要件

- Azure AD アカウント (サブスクリプションの購入とライセンスの割り当てに必要です)
- [Remote Assist のサブスクリプション](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (または [Remote Assist 試用版](/dynamics365/mixed-reality/remote-assist/try-remote-assist))

リモートアシスタンスの [詳細に](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)ついては、こちらを参照してください。

### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist ユーザー

- Remote Assist ライセンス
- ネットワーク接続

### <a name="microsoft-teams-user"></a>Microsoft Teams ユーザー

- Microsoft Teams または [Teams Freemium](https://products.office.com/microsoft-teams/free)
- ネットワーク接続

## <a name="general-deployment-recommendations"></a>一般的な展開に関する推奨事項

外部 HoloLens 2 の展開には、次の手順を実行することをお勧めします。

1. ベースラインビルドとして、[最新の HoloLens OS リリース](https://aka.ms/hololens2download)を使用します。
1. 次の手順に従って、ユーザーベースまたはデバイスベースのライセンスを割り当てます。
    1. [AAD にグループを作成し、](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) HoloLens/RA ユーザーのメンバーを追加します。
    1. [デバイスベースまたはユーザーベースのライセンス](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) をこのグループに割り当てます。
    1. Optional [モバイルデバイス管理 (MDM)](hololens-enroll-mdm.md) ポリシーのターゲットグループ。

1. AAD デバイスをテナントに参加させ、 [自動登録](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)し、自動 [操縦](/hololens/hololens2-autopilot)を通じて構成します。 詳細については、「 [デバイスの所有者](/hololens/security-adminless-os#device-owner)」を参照してください。
    1. デバイスの最初のユーザーは、デバイスの所有者になります。
    1. デバイスが AAD に参加している場合、結合を実行したユーザーはデバイスの所有者になります。
    
1. テナントは、テナントのみが参加できるようにデバイスを[ロック](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot)します。
    1. 「 [テナントロック CSP](/windows/client-management/mdm/tenantlockdown-csp)」も参照してください。

1. [グローバルに割り当てられたアクセスを使用してキオスクモードを構成](/hololens/hololens-global-assigned-access-kiosk)します。

1. 次の (オプション) 機能を無効にします。
    1. [ここで](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)、デバイスを開発者モードにする機能。
    1. HoloLens を PC に接続して日付をコピーする機能は、 [USB を無効](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)にします。
       > [!NOTE]
        > USB を無効にし、USB を使用してプロビジョニングパッケージをデバイスに適用する機能が必要な場合は、 [プロビジョニングパッケージのインストールを許可する方法に関する説明](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)に従ってください。

1. [Windows Defender アプリケーション制御 (WDAC)](/hololens/windows-defender-application-control-wdac)を使用して、HoloLens 2 デバイス上のアプリを許可またはブロックします。
1. セットアップの一部として、リモートアシスタンスを最新バージョンに更新します。 次の2つのオプションについて考えてみます。
    1. [Windows **Microsoft Store]--[リモートアシスタンスの >]--[> と更新アプリ**] にアクセスします。
    1. [Applicationmanagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) -アプリの自動更新を許可します。既定では有効になっています。 デバイスを接続したままにして、更新プログラムを受信します。
1. ネットワーク設定を除く[すべての設定ページを無効](/hololens/settings-uri-list)にして、ユーザーがクライアントサイトでゲストネットワークに接続できるようにします。
1. [HoloLens 更新プログラムの管理](/hololens/hololens-updates)
    1. OS の [更新プログラムを制御](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) したり、自由にフローを許可したりするためのオプションです。
1. [一般的なデバイスの制限](/hololens/hololens-common-device-restrictions)を設定します。

これで、外部クライアントは HoloLens 2 を使用する準備ができました。

## <a name="common-external-client-deployment-concerns"></a>外部クライアントの展開に関する一般的な問題

- [クライアントが相互に通信できないようにする](#ensure-that-external-clients-cant-communicate-with-one-another)
- [クライアントが会社のリソースにアクセスできないようにする](#ensure-that-clients-wont-have-access-to-company-resources)
- [アプリの非表示または制限](#hidden-or-restricted-apps)
- [クライアントのパスワードを管理する](#password-management-for-your-clients) 
- [クライアントがチャット履歴にアクセスできないようにする](#ensure-that-clients-wont-have-access-to-chat-history)

### <a name="ensure-that-external-clients-cant-communicate-with-one-another"></a>外部クライアントが互いに通信できないようにする

HoloLens 呼び出しへのリモートアシスタンス HoloLens はサポートされていません。 クライアントは検索できますが、相互に通信することはできません。 [Microsoft 365 の情報バリア](/microsoft-365/compliance/information-barriers)は、クライアントが検索して呼び出すことができるユーザーをさらに制限できます。 別の方法として、 [Microsoft Teams スコープのディレクトリ検索](/MicrosoftTeams/teams-scoped-directory-search)を使用することもできます。

 > [!NOTE]
> シングルサインオンが有効になっているため、 [Windows Defender アプリケーション制御 (WDAC)](/hololens/windows-defender-application-control-wdac)を使用してブラウザーを無効にすることが重要です。 外部クライアントがブラウザーを開いて Teams の web バージョンを使用すると、クライアントはチャット履歴にアクセスできるようになります。

### <a name="ensure-that-clients-wont-have-access-to-company-resources"></a>クライアントが会社のリソースにアクセスできないようにする

考慮すべき2つのオプションがあります。

1つ目のオプションは、マルチレイヤーアプローチです。

1. ユーザーが必要とするライセンスのみを割り当てます。 OneDrive、Outlook、SharePoint、Yammer などを割り当てない場合、ユーザーはこれらのリソースにアクセスできません。 ユーザーが必要とするライセンスは、リモートアシスタンス、Intune、および AAD のライセンスのみです。
1. クライアントにアクセスしたくないアプリ (電子メールなど) をブロックします (「 [アプリは非表示または制限されてい](#apps are hidden or restricted)ます」を参照してください)。
1. ユーザー名とパスワードをクライアントで共有しないでください。 HoloLens 2 にログインするには、電子メールと数字の PIN が必要です。

2つ目のオプションは、クライアントをホストする別のテナントを作成することです (「イメージ1.1」を参照してください)。

**イメージ1.1**

![サービステナントの画像。](./images/hololens-service-tenant-image.png)

### <a name="hidden-or-restricted-apps"></a>非表示または制限されたアプリ

[キオスクモード](/hololens/hololens-kiosk)や[Windows Defender アプリケーション制御 (WDAC)](/hololens/windows-efender-application-control-wdac)は、アプリケーションを非表示にしたり、制限したりするためのオプションです。

### <a name="password-management-for-your-clients"></a>クライアントのパスワード管理

1. パスワードの有効期限を削除します。 ただし、このオプションを使用すると、アカウントが侵害される可能性が高くなる可能性があります。 NIST パスワードの推奨事項は、30-90 日おきにパスワードを変更することです。
1. HoloLens 2 デバイスのパスワードの有効期限を90日を超えるように拡張します。
1. パスワードを変更するには、デバイスが組織に返される必要があります。 ただし、このオプションを使用すると、デバイスが90日以上クライアントのプラントにあると予想される場合、問題が発生する可能性があります。  
1. 複数のクライアントに送信されるデバイスの場合は、デバイスをクライアントに発送する前にパスワードをリセットします。

### <a name="ensure-that-clients-wont-have-access-to-chat-history"></a>クライアントがチャット履歴にアクセスできないようにする

リモートアシスタンスは、各セッションの後にチャットの履歴をクリアします。 ただし、Microsoft Teams のユーザーはチャットの履歴を利用できます。

> [!NOTE]
> シングルサインオンが有効になっているため、 [Windows Defender アプリケーション制御 (WDAC)](/hololens/windows-defender-application-control-wdac)を使用してブラウザーを無効にすることが重要です。  外部クライアントがブラウザーを開いて Teams の web バージョンを使用する場合、クライアントは通話/チャット履歴にアクセスできます。
