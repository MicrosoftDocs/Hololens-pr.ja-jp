---
title: 外部クライアント展開ガイド
description: 外部クライアントのHoloLens 2の展開ガイド (例としてリモート 支援付き)
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
ms.openlocfilehash: 495be858c235931ed591b097e6b5951f7197c3f7a62bd1aaa16bea65a4e3885f
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115659894"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>次のHoloLens 2を使用して外部クライアントにRemote Assist

このガイドは、次の目標を持つ IT プロフェッショナルが、組織内Microsoft HoloLens 2 つのデバイスを展開するのに役立ちます。

1. クラウド接続HoloLens 2デバイス
1. 使用HoloLens 2にデバイスを外部クライアントに貸し出す
1. ローンされたデバイスをセキュリティで保護する

このガイド[では、ほとんどの](#general-deployment-recommendations-and-instructions)HoloLens 2 デプロイ シナリオに適用できる一般的な HoloLens 2 デプロイの推奨事項と、[](#common-concerns)お客様が外部で使用するために Remote Assist をデプロイするときに発生する一般的な問題について説明します。

## <a name="scenario-description"></a>シナリオの説明

このドキュメントの目的上、Contoso Company は、短期的または長期的な使用のために、HoloLens 2 デバイスを外部クライアントの工場に出荷したいと考っています。 クライアントがサポート サービス マシンを必要とする場合、クライアントは Contoso Company から提供された資格情報を使用して HoloLens 2 デバイスにログインし、Remote Assist を使用して Contoso 社の専門家に問い合わせてください。

詳細については、こちらをRemote Assist [してください](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)。

### <a name="requirements-for-this-scenario"></a>このシナリオの要件

1. [Azure AD](/azure/active-directory/fundamentals/active-directory-whatis)
1. モバイル デバイス マネージャー - Intune [など](/mem/intune/fundamentals/free-trial-sign-up)
1. Remote Assist ライセンス
    1. [購入Remote Assist](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [試用版Remote Assist](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>一般的な懸念事項

- [外部クライアントが相互に通信する機能を持たなかからずに行う方法](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [クライアントが会社のリソースにアクセスできないのを確認する方法](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [アプリを制限する方法](#how-to-restrict-apps)
- [パスワードを管理する方法](#how-to-manage-passwords)
- [クライアントがチャット履歴にアクセスできないのを確認する方法](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>外部クライアントが相互に通信する機能を持たなかからずに行う方法

呼Remote Assist HoloLens HoloLensサポートされていない場合、クライアントは相互に通信できますが、検索できますが、通信できません。 クライアントが検索して呼び出すユーザーをさらに制限するために、  [情報](/microsoft-365/compliance/information-barriers) バリアはクライアントが通信できるユーザーを制限できます。 考慮すべきもう 1 つのオプションは、 [スコープ付きディレクトリ検索の使用です](/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> シングル サインオンが有効になっているので、WDAC を使用してブラウザーを [**無効にすることが重要です**](/hololens/windows-defender-application-control-wdac)。 外部クライアントがブラウザーを開き、Web バージョンの Teams を使用している場合、クライアントは通話/チャット履歴にアクセスできます。

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>クライアントが会社のリソースにアクセスできないのを確認する方法

考慮すべき 2 つのオプションがあります。

1 つ目のオプションは、多層アプローチです。

1. ユーザーが必要とするライセンスのみを割り当てる。 OneDrive、Outlook、SharePoint、Yammer などをユーザーに割り当てない場合、ユーザーはそれらのリソースにアクセスできます。 ユーザーに必要なライセンスは、開始Remote Assist、Intune、AAD のライセンスのみです。
1. クライアントにアクセスしたくないアプリ (電子メールなど) をブロックする (「アプリを制限する[方法」を参照)。](#how-to-restrict-apps)
1. ユーザー名やパスワードをクライアントと共有しません。 ログインするには、電子HoloLens 2 PIN が必要です。

2 つ目のオプションは、クライアントをホストする別のテナントを作成する方法です (イメージ 1.1 を参照)。

**イメージ 1.1**

![サービス テナント イメージ](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>アプリを制限する方法

[キオスク モード](/hololens/hololens-kiosk)や[WDAC (Windows Defender アプリケーション制御)](/hololens/windows-defender-application-control-wdac)は、アプリケーションを制限するためのオプションです。

### <a name="how-to-manage-passwords"></a>パスワードを管理する方法

1. パスワードの有効期限を削除します。 ただし、これにより、アカウントが侵害される可能性が高されます。 NIST パスワードの推奨事項は、30 日から 90 日ごとにパスワードを変更します。
1. デバイスのパスワードの有効期限をHoloLens 2 90 日を超えるまで延長します。
1. パスワードを変更するには、デバイスを Contoso に返す必要があります。 ただし、デバイスがクライアントの工場に 90 日以上含まれると予想される場合は、問題が発生する可能性があります。  
1. 複数のクライアントに送信されるデバイスの場合は、デバイスをクライアントに発送する前にパスワードをリセットします。

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>クライアントがチャット履歴にアクセスできないのを確認する方法

Remote Assistセッションの後にチャット履歴がクリアされます。 ただし、チャット履歴は、ユーザーがMicrosoft Teamsされます。

> [!NOTE]
> シングル サインオンが有効になっているので、WDAC を使用してブラウザーを [**無効にすることが重要です**](/hololens/windows-defender-application-control-wdac)。 外部クライアントがブラウザーを開き、Web バージョンの Teams を使用する場合、クライアントは通話/チャット履歴にアクセスできます。

## <a name="general-deployment-recommendations-and-instructions"></a>一般的なデプロイの推奨事項と手順

デプロイの手順では、次HoloLens 2することをお勧めします。

1. ベースライン ビルド[として最新HoloLens OS](https://aka.ms/hololens2download)リリースを使用します。
1. ユーザーベースまたはデバイスベースのライセンスを割り当てる:
    1. ユーザーベースのライセンスとデバイス ベースのライセンスは、どちらも次の手順に従います。
        1. [AAD でグループを作成し、ユーザーまたは](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members)RA ユーザー HoloLensメンバーを追加します。
        1. [デバイスベースまたはユーザーベースのライセンスをこのグループに割](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) り当てる。
        1. (省略可能)MDM ポリシーのグループをターゲットにできます。

1. デバイスは、テナントに AAD 参加済みである [ [自動](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)登録] で、自動パイロット を使用 [して構成する必要があります](/hololens/hololens2-autopilot)。
    1. デバイスの最初のユーザーがデバイス所有者になる点に注意してください。
    1. デバイスが AAD 参加している場合、参加を実行したユーザーはデバイス所有者になります。
    1. 詳細については、「デバイス所有者」 [を参照してください](/hololens/security-adminless-os#device-owner)。
1. [テナントは](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) 、テナントにのみ参加できるようデバイスをロックします。
    1. **追加のリンク:** [テナント ロック CSP](/windows/client-management/mdm/tenantlockdown-csp)。
1. こちら へのグローバル割り当てアクセスを使用してキオスクを [構成します](/hololens/hololens-global-assigned-access-kiosk)。
1. 次の (省略可能) 機能を無効にすることをお勧めします。
    1. ここでデバイスを開発者モードにする [機能](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)。
    1. 日付をコピーする PC HoloLens接続する機能を使用すると[、USB が無効になります](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)。
       > [!NOTE]
        > USB を無効にしないが、USB を使用してデバイスにプロビジョニング パッケージを適用する機能を必要とする場合は、ここに記載されている手順に従 [**います**](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)。

1. [WDAC を使用](/hololens/windows-defender-application-control-wdac)して、デバイス上のアプリを許可HoloLens 2します。
1. セットアップRemote Assist最新バージョンに更新します。 これを行うには、次の 2 つのオプションがあります。
    1. これを行う場合は、 **--Windows Microsoft Store --> Remote Assist に>アプリを更新します**。
    1. [アプリの自動更新を許可する ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) は、既定で有効になっています。 更新プログラムを受信するには、デバイスを接続した状態に保つ必要があります。
1. [ユーザーがクライアント サイトのゲスト](/hololens/settings-uri-list) ネットワークに接続するには、ネットワーク設定を除くすべての設定ページを無効にします。
1. [更新プログラムHoloLens管理する](/hololens/hololens-updates)
    1. OS の更新 [を制御したり、自由](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) にフローしたりするオプション。
1. [一般的なデバイスの制限](/hololens/hololens-common-device-restrictions)。
