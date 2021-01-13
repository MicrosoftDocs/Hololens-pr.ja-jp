---
title: 展開ガイド
description: HoloLens 2 の展開ガイド (例としてリモート アシスト付き)
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/7/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 0cd75fdbe5f6a4e6da87770768ce9f22bce491c0
ms.sourcegitcommit: 58bffba63ed581351d80d13b1437aca74d7ed64a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "11266374"
---
# リモート アシストによる外部クライアントへの HoloLens 2 の展開

このドキュメントは、リモート アシストに重点を置いて HoloLens 2 デバイスを計画および展開する IT 専門職に役立ちます。 [リモート アシストについて詳しくは、次のリンクを参照してください](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)。

## シナリオの説明

このドキュメントの目的上、Contoso Company は、短期的または長期的な使用のために、HoloLens 2 デバイスを外部クライアントの工場に出荷する必要があります。 クライアントがアシスタンス サービス マシンを必要とする場合、クライアントは Contoso Company が提供する資格情報を使用して HoloLens 2 デバイスにログインし、リモート アシストを使用して Contoso Company の専門家に問い合わせています。

### このシナリオの要件

1. [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. モバイル デバイス マネージャー - [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)など
1. リモート アシスト ライセンス
    1. [リモート アシストを購入する](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [試用版リモート アシスト](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## 一般的な問題

- [外部クライアントが相互に通信する機能を持たなことを確認する方法](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [クライアントが会社のリソースにアクセスできないか確認する方法](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [アプリを制限する方法](#how-to-restrict-apps)
- [パスワードを管理する方法](#how-to-manage-passwords)
- [クライアントがチャット履歴にアクセスできないか確認する方法](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### 外部クライアントが相互に通信する機能を持たなことを確認する方法

HoloLens から HoloLens へのリモート アシスト呼び出しはサポートされていないので、クライアントは互いに通信を検索できますが、相互に通信できません。 クライアントが検索および通話できるユーザーをさらに制限するために、[](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide)情報バリアはクライアントが通信できるユーザーを制限できます。 もう 1 つの検討すべきオプションは [、スコープ指定ディレクトリ検索の使用です。](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> シングル サインオンが有効になっているので [**、WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)を使用してブラウザーを無効にすることが重要です。 外部クライアントがブラウザーを開き、Web バージョンの Teams を使用する場合、クライアントは通話/チャット履歴にアクセスできます。

### クライアントが会社のリソースにアクセスできないか確認する方法

考慮すべき 2 つのオプションがあります。

最初のオプションは、多層的なアプローチです。

1. ユーザーが必要とするライセンスのみを割り当てる。 OneDrive、Outlook、SharePoint、Yammer などをユーザーに割り当てない場合、ユーザーはそれらのリソースにアクセスできます。 ユーザーが必要とするライセンスは、リモート アシスト、Intune、および AAD ライセンスのみです。
1. クライアントにアクセスしたくないアプリ (メールなど) をブロックする (「アプリを制限する[方法」を参照)。](#how-to-restrict-apps)
1. ユーザー名やパスワードをクライアントと共有しません。 HoloLens 2 にログインするには、電子メールと数値の PIN が必要です。

2 つ目のオプションは、クライアントをホストする個別のテナントを作成する方法です (イメージ 1.1 を参照)。

**画像 1.1**

![サービス テナント イメージ](./images/hololens-service-tenant-image.png)

### アプリを制限する方法

[キオスク モード](https://docs.microsoft.com/hololens/hololens-kiosk) や [WDAC (Windows Defender アプリケーション制御)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) は、アプリケーションを制限するためのオプションです。

### パスワードを管理する方法

1. パスワードの有効期限を削除します。 ただし、これにより、アカウントが侵害される可能性が高くなっています。 NIST パスワードの推奨事項は、30 ~ 90 日ごとにパスワードを変更する方法です。
1. HoloLens 2 デバイスのパスワードの有効期限を 90 日を超えるまで延長します。
1. パスワードを変更するには、デバイスを Contoso に戻す必要があります。 ただし、デバイスがクライアントの工場に 90 日以上稼働すると予想される場合は、問題が発生する可能性があります。  
1. 複数のクライアントに送信されるデバイスの場合は、デバイスをクライアントに出荷する前にパスワードをリセットします。

### クライアントがチャット履歴にアクセスできないか確認する方法

リモート アシストは、セッションごとにチャット履歴をクリアします。 ただし、チャット履歴は Microsoft Teams ユーザーが利用できます。

> [!NOTE]
> シングル サインオンが有効になっているので [**、WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)を使用してブラウザーを無効にすることが重要です。 外部クライアントがブラウザーを開き、Web バージョンの Teams を使用する場合、クライアントは通話/チャット履歴にアクセスできます。

## 一般的な展開の推奨事項と手順

HoloLens 2 の展開手順では、次の手順を実行することをお勧めします。

1. ベースライン ビルド [として最新の HoloLens OS](https://aka.ms/hololens2download) リリースを使用します。
1. ユーザー ベースまたはデバイス ベースのライセンスを割り当てる:
    1. ユーザー ベースのライセンスとデバイス ベースのライセンスの両方は、次の手順に従います。
        1. [AAD でグループを作成し](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) 、HoloLens/RA ユーザーのメンバーを追加します。
        1. [デバイス ベースまたはユーザー ベースのライセンスをこのグループに割](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) り当てる。
        1. (省略可能)MDM ポリシーのグループをターゲットにできます。

1. デバイスは、AAD がテナントに参加し、 [自動登録され](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)、自動パイロットによって [構成されている必要があります](https://docs.microsoft.com/hololens/hololens2-autopilot)。
    1. デバイスの最初のユーザーがデバイスの所有者になる点に注意してください。
    1. デバイスが AAD に参加している場合、参加を実行したユーザーはデバイス所有者になります。
    1. 詳しくは、「デバイス所有者 [」をご覧ください](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)。
1. [テナントが](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) テナントにのみ参加できるよう、デバイスをロックします。
    1. **追加リンク:** [テナント ロック CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)。
1. ここにグローバルに割り当てられたアクセスを使用してキオスクを [構成します](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)。
1. 次の (オプション) 機能を無効にすることをお勧めします。
    1. ここでデバイスを開発者モードにする [機能](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)。
    1. 日付をコピーするために HoloLens を PC に接続する機能は [、USB を無効にします](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)。
       > [!NOTE]
        > USB を無効にしないが、USB を使ってデバイスにプロビジョニング パッケージを適用する機能が必要な場合は、次の手順に従 [**います**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)。

1. [WDAC を使](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)って、HoloLens 2 デバイスでアプリを許可または黒にします。
1. セットアップの一環として、リモート アシストを最新バージョンに更新します。 これを行うには、次の 2 つのオプションがあります。
    1. これは、Windows Microsoft Store **--> Remote Assist --> App にアクセスして行います**。
    1. もう 1 つの方法は、自動更新のために HoloLens 2 を夜間に接続したままにしておく方法です。
1. [ネットワーク設定以外のすべての設定](https://docs.microsoft.com/hololens/settings-uri-list) ページを無効にして、ユーザーがクライアント サイトのゲスト ネットワークに接続できます。
1. [HoloLens の更新プログラムの管理](https://docs.microsoft.com/hololens/hololens-updates)
    1. OS の更新 [を制御するか、自由](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) にフローを許可するオプション。
1. [一般的なデバイスの制限](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)。
