---
title: ページ設定の可視性
description: PageVisibilityList および HoloLens Mixed Reality デバイスのガイドでサポートされている URI のリストを最新の状態に保ちます。
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, 割り当てられたアクセス, キオスク, 設定ページ
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d28994d911532a940d82756aa45609571ee80ac3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924334"
---
# <a name="page-settings-visibility"></a>ページ設定の可視性

HoloLens デバイスの管理可能な機能の 1 つは、[設定/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) ポリシーを使用して、設定 アプリ内に表示されるページを制限することです。 PageVisibilityList は、IT 管理者がシステム設定アプリの特定のページを表示またはアクセスできないようにしたり、または指定されたページ以外のすべてのページで同様に行うことを許可するポリシーです。

> [!NOTE]
> この機能は、[Windows Holographic バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 以降の HoloLens 2 デバイスでのみ使用できます。 この機能を使用するデバイスが更新されていることを確認してください。

次の例では、情報ページと Bluetooth ページにのみアクセスを許可するポリシーを示しています。これには、それぞれ URI "ms-settings:network-wifi" と "ms-settings:bluetooth" があります。
- `showonly:network-wifi;network-proxy;bluetooth`

プロビジョニング パッケージを通して設定するには:

1. Windows 構成デザイナーでパッケージを作成しているときに、 **[ポリシー] > [設定] > [PageVisibilityList]** の順に移動します。
1. 次の文字列を入力します: **`showonly:network-wifi;network-proxy;bluetooth`**
1. プロビジョニング パッケージをエクスポートします。
1. デバイスにパッケージを適用します。
プロビジョニング パッケージを作成して適用する方法の詳細については、[このページ](hololens-provisioning.md)を参照してください。

これは、OMA-URI を使用して Intune 経由で行います。

1. **カスタム ポリシー** を作成します。
1. OMA-URI を設定する場合は、次の文字列を使用します: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. 選択したデータを選ぶときは、**文字列** を選択します
1. 値を入力する場合は、次の値を使用します: **`showonly:network-wifi;network-proxy;bluetooth`**
1. カスタムデバイス構成は、デバイスが含まれる予定のグループに必ず割り当ててください。

Intune グループのデバイス構成の詳細については、[「HoloLens MDM 構成」](hololens-mdm-configure.md)を参照してください。

選択した方法に関係なく、デバイスは変更を受け取る必要があります。ユーザーには次の設定アプリが表示されます。

![設定アプリで変更されたアクティブ時間のスクリーンショット](images/hololens-page-visibility-list.jpg)

独自の選択したページを表示または非表示に設定アプリ ページを構成するには、HoloLens で使用可能な設定 URI を確認します。

## <a name="settings-uris"></a>設定に関する URI

HoloLens デバイスと Windows 10 デバイスでは、設定アプリ内に用意されているページが異なります。 このページには、HoloLens に存在する設定だけが表示されます。

### <a name="accounts"></a>アカウント
| [設定] ページ           | URI                                            |
|-------------------------|------------------------------------------------|
| 職場または学校にアクセスする | `ms-settings:workplace`                         |
| 虹彩の登録       | `ms-settings:signinoptions-launchirisenrollment` |
| サインイン オプション         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a>アプリ
| [設定] ページ | URI                          |
|---------------|------------------------------|
| アプリと機能<sup>2</sup>     | `ms-settings:appsfeatures` <br> |
| [アプリと機能] > [詳細なオプション] <sup>2</sup>     | `ms-settings::appsfeatures-app` <br> |
| [アプリと機能] > [オフライン マップ] <sup>2</sup>     | `ms-settings:maps-maps` <br> |
| [アプリと機能] > [オフライン マップ] > [マップをダウンロード] <sup>2</sup>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a>デバイス
| [設定] ページ | URI                          |
|---------------|------------------------------|
| Bluetooth     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| マウス <sup>2</sup>      | `ms-settings:mouse` <br>  |
| USB <sup>2</sup>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a>プライバシー
| [設定] ページ            | URI                                             |
|--------------------------|-------------------------------------------------|
| アカウント情報             | `ms-settings:privacy-accountinfo`              |
| アプリの診断        | `ms-settings:privacy-appdiagnostics`              |
| バックグラウンド アプリ        | `ms-settings:privacy-backgroundapps`              |
| 予定表                 | `ms-settings:privacy-calendar`                    |
| 通話履歴             | `ms-settings:privacy-callhistory`                 |
| カメラ                   | `ms-settings:privacy-webcam`                      |
| 連絡先                 | `ms-settings:privacy-contacts`                    |
| 診断とフィードバック | `ms-settings:privacy-feedback`                    |
| ドキュメント                | `ms-settings:privacy-documents`                   |
| Email                    | `ms-settings:privacy-email`                       |
| ファイル システム              | `ms-settings:privacy-broadfilesystemaccess`       |
| 全般 <sup>2</sup>             | `ms-settings:privacy-general`       |
| インクと入力の個人用設定<sup>2</sup>             | `ms-settings:privacy-speechtyping`       |
| 場所                 | `ms-settings:privacy-location`                    |
| メッセージング                | `ms-settings:privacy-messaging`                   |
| Microphone               | `ms-settings:privacy-microphone`                  |
| モーション <sup>2</sup>               | `ms-settings:privacy-motion`                  |
| 通知            | `ms-settings:privacy-notifications`               |
| その他のデバイス            | `ms-settings:privacy-customdevices`               |
| ピクチャ                 | `ms-settings:privacy-pictures`                    |
| 無線                   | `ms-settings:privacy-radios`                      |
| スクリーンショットの境界線 <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| スクリーンショットとアプリ <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| 音声                   | `ms-settings:privacy-speech`                      |
| タスク                    | `ms-settings:privacy-tasks`                       |
| ユーザーの移動           | `ms-settings:privacy-backgroundspatialperception` |
| ビデオ                   | `ms-settings:privacy-videos`                      |
| 音声のアクティブ化       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a>ネットワークとインターネット
| [設定] ページ | URI                              |
|---------------|----------------------------------|
| 機内モード<sup>2</sup> | `ms-settings:network-airplanemode`        |
| プロキシ | `ms-settings:network-proxy`        |
| VPN   | `ms-settings:network-vpn`          |
| Wi-Fi  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a>システム
| [設定] ページ      | URI                                |
|--------------------|------------------------------------|
| バッテリー<sup>2</sup>           | `ms-settings:batterysaver`<br>|
| バッテリー<sup>2</sup>           | `ms-settings:batterysaver-settings`<br>|
| 色             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| ホログラム<sup>2</sup>  |  `ms-settings:holograms`  |
| 調整<sup>2</sup> |  `ms-settings:calibration` |
| 通知とアクション  | `ms-settings:notifications`          |
| 共有エクスペリエンス | `ms-settings:crossdevice` 
| サウンド<sup>2</sup>           | `ms-settings:sound`<br>|
| [サウンド] > [アプリのボリュームとデバイスの優先順位] <sup>2</sup>           | `ms-settings:apps-volume`<br>|
| [サウンド] > [サウンド デバイスを管理] <sup>2</sup>           | `ms-settings:sound-devices`<br>|
| ストレージ            | `ms-settings:storagesense`           |
| [サウンド] > [記憶域センスの構成] <sup>2</sup>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a>時刻と言語
| [設定] ページ | URI                                           |
|---------------|-----------------------------------------------|
| 日付と時刻 <sup>2</sup> | `ms-settings:dateandtime`                  |
| キーボード <sup>2</sup> | `ms-settings:keyboard`                  |
| 言語 <sup>2</sup> | `ms-settings:language`                  |
| 言語 <sup>2</sup> | `ms-settings:regionlanguage-languageoptions`                  |
| Language      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| リージョン        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a>アップデートとセキュリティ
| [設定] ページ                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| 詳細オプション                    | `ms-settings:windowsupdate-options`         |
| リセットと回復 <sup>2</sup>      | `ms-settings:reset`         |
| Windows Insider Program               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| Windows Update                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup>1</sup>`ms-settings:windowsupdate-options`<br><sup>1</sup>`ms-settings:windowsupdate-restartoptions` |
| Windows Update - 更新プログラムの確認 | `ms-settings:windowsupdate-action`          |


- <sup>1</sup> - Windows Holographic バージョン 21H1 以前のバージョンの場合、次の 2 つの URI では、実際には **[詳細オプション]** ページまたは **[オプション]** ページに移動する必要があります。メインの Windows Update ページをブロックまたは表示するのみです。
  -  ms-settings:windowsupdate-options
  -  ms-settings:windowsupdate-restartoptions

- <sup>2</sup> - Holographic 21H1 Windows 21H1 以上で使用できます。


Windows 10 設定 URI の完全なリストについては、[起動設定](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)のドキュメントをご覧ください。
