---
title: 外部クライアント展開ガイド
description: 外部クライアント向け HoloLens 2 の展開ガイド (例としてリモート アシスト付き)
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
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385587"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>リモート アシストを使用した外部クライアントへの HoloLens 2 の展開

このガイドは、次の目標を持つ IT 担当者が組織に Microsoft HoloLens 2 デバイスを展開するのに役立ちます。

1. クラウド接続 HoloLens 2 デバイス
1. HoloLens 2 デバイスを外部クライアントに貸与して使用する
1. セキュリティで保護された貸し出しデバイス

このガイドでは、[ほとんどの HoloLens 2](#general-deployment-recommendations-and-instructions)展開シナリオに適用可能な HoloLens 2 の[](#common-concerns)一般的な展開推奨事項と、外部で使用するためにリモート アシストを展開するときにお客様が持つ一般的な懸念事項について説明します。

## <a name="scenario-description"></a>シナリオの説明

このドキュメントの目的で、Contoso 社は HoloLens 2 デバイスを短期的または長期的な使用のために外部クライアントの工場に出荷する必要があります。 クライアントが支援サービス 機械を必要とする場合、クライアントは Contoso 社が提供する資格情報を使用して HoloLens 2 デバイスにログインし、リモート アシストを使用して Contoso 社の専門家に連絡します。

リモート アシストの詳細については、こちらを [参照してください](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)。

### <a name="requirements-for-this-scenario"></a>このシナリオの要件

1. [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. モバイル デバイス マネージャー - [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)など
1. リモート アシスト ライセンス
    1. [リモート アシストの購入](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [試用版リモート アシスト](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>一般的な懸念事項

- [外部クライアントが相互に通信できない方法](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [クライアントが会社のリソースにアクセスできない方法](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [アプリを制限する方法](#how-to-restrict-apps)
- [パスワードを管理する方法](#how-to-manage-passwords)
- [クライアントがチャット履歴にアクセスできない方法](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>外部クライアントが相互に通信できない方法

HoloLens へのリモート アシスト HoloLens 呼び出しはサポートされていないので、クライアントは相互に通信できますが、検索できますが、通信できません。 クライアントが検索および呼び出しできるユーザーをさらに制限するために、  [情報](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) バリアは、クライアントが通信できるユーザーを制限できます。 考慮すべきもう 1 つのオプションは [、Scoped Directory Search を使用する方法です。](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> シングル サインオンが有効になっているので、WDAC を使用してブラウザーを [**無効にすることが重要です**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)。 外部クライアントがブラウザーを開き、Web バージョンの Teams を使用する場合、クライアントは通話/チャット履歴にアクセスできます。

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>クライアントが会社のリソースにアクセスできない方法

考慮すべき 2 つのオプションがあります。

最初のオプションは、多層的なアプローチです。

1. ユーザーが必要とするライセンスのみを割り当てる。 OneDrive、Outlook、SharePoint、Yammerなどをユーザーに割り当てない場合、それらのリソースにアクセスできます。 ユーザーが必要とする唯一のライセンスは、開始するリモート アシスト、Intune、および AAD ライセンスです。
1. クライアントにアクセスしないアプリ (メールなど) をブロックします (「アプリを制限する [方法」を参照](#how-to-restrict-apps))。
1. ユーザー名やパスワードをクライアントと共有しない。 HoloLens 2 にログインするには、電子メールと数値の PIN が必要です。

2 つ目のオプションは、クライアントをホストする個別のテナントを作成する方法です (「イメージ 1.1」を参照)。

**イメージ 1.1**

![サービス テナント イメージ](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>アプリを制限する方法

[キオスク モード](https://docs.microsoft.com/hololens/hololens-kiosk) または [WDAC (Windows Defenderアプリケーション制御)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) は、アプリケーションを制限するためのオプションです。

### <a name="how-to-manage-passwords"></a>パスワードを管理する方法

1. パスワードの有効期限を削除します。 ただし、これにより、アカウントが侵害される可能性が高されます。 NIST パスワードの推奨事項は、30 ~ 90 日ごとにパスワードを変更します。
1. HoloLens 2 デバイスのパスワードの有効期限を 90 日を超えるまで延長します。
1. パスワードを変更するには、デバイスを Contoso に返す必要があります。 ただし、デバイスが 90 日以上クライアントの工場に含まれると予想される場合は、問題が発生する可能性があります。  
1. 複数のクライアントに送信されるデバイスの場合は、デバイスをクライアントに出荷する前にパスワードをリセットします。

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>クライアントがチャット履歴にアクセスできない方法

リモート アシストは、各セッションの後にチャット履歴をクリアします。 ただし、チャット履歴は Microsoft Teams ユーザーが利用できます。

> [!NOTE]
> シングル サインオンが有効になっているので、WDAC を使用してブラウザーを [**無効にすることが重要です**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)。 外部クライアントがブラウザーを開き、Web バージョンの Teams を使用する場合、クライアントは通話/チャット履歴にアクセスできます。

## <a name="general-deployment-recommendations-and-instructions"></a>一般的な展開の推奨事項と手順

HoloLens 2 展開手順では、次の手順を実行することをお勧めします。

1. ベースライン ビルド [として最新の HoloLens OS](https://aka.ms/hololens2download) リリースを使用します。
1. ユーザー ベースまたはデバイス ベースのライセンスを割り当てる:
    1. ユーザー ベースのライセンスとデバイス ベースのライセンスの両方が、次の手順に従います。
        1. [AAD でグループを作成し](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) 、HoloLens/RA ユーザーのメンバーを追加します。
        1. [デバイス ベースまたはユーザー ベースのライセンスをこのグループ](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) に割り当てる。
        1. (省略可能)MDM ポリシーのグループをターゲットにできます。

1. デバイスは、AAD がテナントに参加し、 [自動登録](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)され、自動パイロットを介して [構成されている必要があります](https://docs.microsoft.com/hololens/hololens2-autopilot)。
    1. デバイスの最初のユーザーはデバイスの所有者になります。
    1. デバイスが AAD 参加の場合、参加を実行したユーザーはデバイス所有者になります。
    1. 詳細については、「デバイス所有者 [」を参照してください](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)。
1. [テナントは、](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) テナントに参加できるデバイスのみをロックします。
    1. **その他のリンク:** [テナント ロック CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)。
1. ここにグローバルに割り当てられたアクセスを使用してキオスクを [構成します](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)。
1. フォロー (オプション) 機能を無効にすることをお勧めします。
    1. ここでデバイスを開発者モードにする [機能](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)。
    1. HoloLens を PC に接続して日付をコピーする機能は [、USB を無効にします](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)。
       > [!NOTE]
        > USB を無効にしないが、USB を使用してデバイスにプロビジョニング パッケージを適用する機能が必要な場合は、ここに示す手順に従 [**います**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)。

1. [WDAC を使用](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)して、HoloLens 2 デバイス上のアプリを許可またはブロックします。
1. セットアップの一環として、リモート アシストを最新バージョンに更新します。 これを行うには、次の 2 つのオプションがあります。
    1. これは、Windows Microsoft Store --> リモート アシスト **-->更新アプリ にアクセスして実行できます**。
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) (アプリの自動更新を許可する) は、既定で有効になっています。 デバイスを接続して更新プログラムを受信します。
1. [ネットワーク設定以外のすべての設定ページ](https://docs.microsoft.com/hololens/settings-uri-list) を無効にして、ユーザーがクライアント サイトでゲスト ネットワークに接続できます。
1. [HoloLens の更新プログラムの管理](https://docs.microsoft.com/hololens/hololens-updates)
    1. OS の更新 [を制御するか、自由](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) にフローを許可するオプション。
1. [一般的なデバイスの制限](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)。
