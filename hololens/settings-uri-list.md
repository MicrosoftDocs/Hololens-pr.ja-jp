---
title: 設定に関する URI
description: PageVisibilityList の HoloLens に対応している URI の一覧
author: evmill
ms.author: v-evmill
ms.date: 09/16/2020
ms.topic: article
keywords: hololens、hololens 2、割り当てられたアクセス、キオスク、設定ページ
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 17959fa25763d2c6b89d0956f29b9999b3012e60
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016701"
---
# 設定に関する URI

HoloLens デバイスの管理可能な機能の 1 つに、[Settings/PageVisibilityList ポリシー](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)を使用した設定アプリ内で閲覧されるページの制限があります。 PageVisibilityList は、IT 管理者がシステム設定アプリの特定のページを表示またはアクセスできないようにしたり、または指定されたページ以外のすべてのページで同様に行うことを許可するポリシーです。 

> [!IMPORTANT]
> この機能は現在、[Windows Insider ビルド](hololens-insider.md)でのみ利用可能です。 これに使用しようとしているデバイスをビルド 19041.1349+ にしてください。

次の例では、情報ページと Bluetooth ページにのみアクセスを許可するポリシーを示しています。これには、それぞれ URI "ms-settings:network-wifi" と "ms-settings:bluetooth" があります。
- showonly:network-wifi;network-proxy;bluetooth

プロビジョニング パッケージでこれを設定するには、次の操作を行います。 
1. Windows 構成デザイナーでパッケージを作成しているときに、**[ポリシー] > [設定] > [PageVisibilityList]** の順に移動します。
1. 次の文字列を入力します: **showonly:network-wifi;network-proxy;bluetooth**
1. プロビジョニング パッケージをエクスポートします。
1. デバイスにパッケージを適用します。 プロビジョニング パッケージを作成して適用する方法の詳細については、[「このページ」](hololens-provisioning.md)を参照してください。 

これは、OMA-URI を使用して Intune を介して行うことができます。
1. **カスタム ポリシー**を作成する。
1. OMA URI を設定するには、 次の文字列を使用します:**./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList** 
1. 選択したデータを選ぶときは、**文字列**を選択します。
1. 値を入力する時は、次のように使います: **showonly:network-wifi;network-proxy;bluetooth**
1. デバイスが使用されるグループにカスタム デバイス構成が割り当てられていることを確認します。
Intune グループとデバイス構成の詳細については、[こちらを確認](hololens-mdm-configure.md)を参照してください。

方法の選択に関係なく、デバイスは変更を受信するようになり、ユーザーには次の設定アプリが表示されます。 

![設定アプリで変更されたアクティブ時間のスクリーンショット](images/hololens-page-visibility-list.jpg)

独自に選択したページを表示または非表示にするように設定アプリ ページを構成するには、HoloLens で確認できる設定に関する URI を参照してください。 

## 設定に関する URI

HoloLens デバイスと Windows 10 デバイスでは、設定アプリ内に用意されているページが異なります。 このページでは、HoloLens に存在する設定のみを確認することができます。 

### Accounts
| 設定ページ           | URI                                            |
|-------------------------|------------------------------------------------|
| サインイン オプション         | ms-settings:signinoptions                      |
| 虹彩の登録       | ms-settings:signinoptions-launchirisenrollment |
| 職場または学校にアクセスする | ms-settings:workplace                          |

### デバイス
| 設定ページ | URI                          |
|---------------|------------------------------|
| Bluetooth     | ms-settings:bluetooth <br> ms-settings:connecteddevices |

### プライバシー
| 設定ページ            | URI                                             |
|--------------------------|-------------------------------------------------|
| アカウント情報             | ms-settings:privacy-accountinfo                 |
| アプリの診断        | ms-settings:privacy-appdiagnostics              |
| バックグラウンド アプリ        | ms-settings:privacy-backgroundapps              |
| ユーザーの移動           | ms-settings:privacy-backgroundspatialperception |
| ファイル システム              | ms-settings:privacy-broadfilesystemaccess       |
| カレンダー                 | ms-settings:privacy-calendar                    |
| 通話履歴             | ms-settings:privacy-callhistory                 |
| 連絡先                 | ms-settings:privacy-contacts                    |
| その他のデバイス            | ms-settings:privacy-customdevices               |
| ドキュメント                | ms-settings:privacy-documents                   |
| Email                    | ms-settings:privacy-email                       |
| 診断とフィードバック | ms-settings:privacy-feedback                    |
| Location                 | ms-settings:privacy-location                    |
| メッセージング                | ms-settings:privacy-messaging                   |
| マイク               | ms-settings:privacy-microphone                  |
| 通知            | ms-settings:privacy-notifications               |
| 画像                 | ms-settings:privacy-pictures                    |
| 無線                   | ms-settings:privacy-radios                      |
| 音声認識                   | ms-settings:privacy-speech                      |
| タスク                    | ms-settings:privacy-tasks                       |
| ビデオ                   | ms-settings:privacy-videos                      |
| 音声によるアクティブ化       | ms-settings:privacy-voiceactivation             |
| カメラ                   | ms-settings:privacy-webcam                      |

### ネットワークとインターネット
| 設定ページ | URI                              |
|---------------|----------------------------------|
| Wi-Fi  | ms-settings:network-wifi<br>ms-settings:network-wifisettings<br>ms-settings:network-status<br>ms-settings:wifi-provisioning    |
| VPN   | ms-settings:network-vpn          |
| プロキシ | ms-settings:network-proxy        |

### System
| 設定ページ      | URI                                |
|--------------------|------------------------------------|
| 共有エクスペリエンス | ms-settings:crossdevice            |
| 色             | ms-settings:colors<br>ms-settings:personalization-colors |
| 通知とアクション  | ms-settings:notifications          |
| 記憶域            | ms-settings:storagesense           |

### 時刻と言語
| 設定ページ | URI                                           |
|---------------|-----------------------------------------------|
| Region        | ms-settings:regionformatting                  |
| 言語      | ms-settings:regionlanguage<br>ms-settings:regionlanguage-adddisplaylanguage<br>ms-settings:regionlanguage-setdisplaylanguage |

### 更新とセキュリティ
| 設定ページ                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Windows Insider Program               | ms-settings:windowsinsider <br>ms-settings:windowsinsider-optin          |
| Windows Update                        | ms-settings:windowsupdate<br> ms-settings:windowsupdate-activehours  <br> ms-settings:windowsupdate-history <br> ms-settings:windowsupdate-optionalupdates <br><sup>1</sup>ms-settings:windowsupdate-options<br><sup>1</sup>ms-settings:windowsupdate-restartoptions |
| Windows Update - 更新プログラムの確認 | ms-settings:windowsupdate-action          |
| 詳細オプション                    | ms-settings:windowsupdate-options         |

> [!NOTE]
>  1 次の 2 つの URI は、実際には [詳細オプション] や [オプション] ページへの移動を行いません。Windows Update のメイン ページをブロックしたり、表示したりするだけです。 
> - ms-settings:windowsupdate-options
> - ms-settings:windowsupdate-restartoptions 

Windows 10 の設定に関する URI の完全な一覧については、[こちら](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)を参照してください。 
