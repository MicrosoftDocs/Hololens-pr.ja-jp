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
ms.openlocfilehash: 92040019b093c5ef63d74f095dcb3809112ae7a0
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034425"
---
# <a name="page-settings-visibility"></a>ページ設定の可視性

HoloLens デバイスの管理可能な機能の 1 つは、[設定/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) ポリシーを使用して、設定 アプリ内に表示されるページを制限することです。 PageVisibilityList は、IT 管理者がシステム設定アプリの特定のページを表示またはアクセスできないようにしたり、または指定されたページ以外のすべてのページで同様に行うことを許可するポリシーです。

> [!NOTE]
> この機能は、[Windows Holographic バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 以降の HoloLens 2 デバイスでのみ使用できます。 この機能を使用するデバイスが更新されていることを確認してください。


## <a name="examples"></a>例
ページは、公開されている URI の短縮バージョン (URI から "ms-settings:" プレフィックスを取り除いたもの) により識別されます。

次の例では、情報ページと Bluetooth ページにのみアクセスを許可するポリシーを示しています。これには、それぞれ URI "network-wifi" と "bluetooth" があります。
- `showonly:network-wifi;network-proxy;bluetooth`

次の例は、OS の [リセット] ページを非表示にするポリシーを示しています。
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a>Intune を使用したこのポリシーの展開

Intune に提供される構成値を次に示します。

- **名前:** 管理者が選択したプロファイルの表示名。
- **OMA-URI:** [スコープ](/windows/client-management/mdm/policy-configuration-service-provider)を含む設定ページの完全修飾 URI。 このページの例では `./Device` スコープを使用しています。
- **値**: 指定したページ "*のみ*" を非表示にするか表示するかを示す文字列値。 設定可能な値は `hide:<pagename>` および `showonly:<pagename>` です。 
 
複数のページを指定するには、セミコロンで区切ります。一般的なページの一覧については後述します。

1. **カスタム ポリシー** を作成します。
1. **OMA-URI** を設定する場合は、完全なスコープが指定された URI を入力します。 例: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. 選択したデータを選ぶときは、**文字列** を選択します
1. **[値]** を指定する場合は、前述のガイダンスに従ってください。 例: **`showonly:network-wifi;network-proxy;bluetooth`** または **`hide:reset`** 
> [!IMPORTANT]
> カスタムデバイス構成は、デバイスが含まれる予定のグループに必ず割り当ててください。 この手順を実行しない場合、ポリシーはプッシュされますが、適用されません。

Intune グループのデバイス構成の詳細については、[「HoloLens MDM 構成」](hololens-mdm-configure.md)を参照してください。


## <a name="deploying-this-policy-via-a-provisioning-package"></a>プロビジョニング パッケージを使用したこのポリシーの展開

Windows Configuration Designer で指定される構成値を次に示します。

**値**: 指定したページ "*のみ*" を非表示にするか表示するかを示す文字列値。 設定可能な値は `hide:<pagename>` および `showonly:<pagename>` です。 複数のページを指定するには、セミコロンで区切ります。一般的なページの一覧については後述します。


1. Windows 構成デザイナーでパッケージを作成しているときに、 **[ポリシー] > [設定] > [PageVisibilityList]** の順に移動します。
1. 次の文字列を入力します: **`showonly:network-wifi;network-proxy;bluetooth`**
1. プロビジョニング パッケージをエクスポートします。
1. デバイスにパッケージを適用します。
プロビジョニング パッケージを作成し、適用する方法の詳細については、[HoloLens のプロビジョニングに関するページ](hololens-provisioning.md)を参照してください。


選択した方法に関係なく、デバイスは変更を受け取る必要があります。ユーザーには次の設定アプリが表示されます。

![設定アプリで変更されたアクティブ時間のスクリーンショット。](images/hololens-page-visibility-list.jpg)

独自の選択したページを表示または非表示に設定アプリ ページを構成するには、HoloLens で使用可能な設定 URI を確認します。

## <a name="settings-uris"></a>設定に関する URI

HoloLens デバイスと Windows 10 デバイスでは、設定アプリ内に用意されているページが異なります。 このページには、HoloLens に存在する設定だけが表示されます。

### <a name="accounts"></a>アカウント
| [設定] ページ           | URI                                            |
|-------------------------|------------------------------------------------|
| 職場または学校にアクセスする | `workplace`                         |
| 虹彩の登録       | `signinoptions-launchirisenrollment` |
| サインイン オプション         | ` signinoptions `                   |

### <a name="apps"></a>アプリ
| [設定] ページ | URI                          |
|---------------|------------------------------|
| アプリと機能 <sup>2</sup>     | `appsfeatures` <br> |
| [アプリと機能] > [詳細なオプション] <sup>2</sup>     | `appsfeatures-app` <br> |
| [アプリと機能] > [オフライン マップ] <sup>2</sup>     | `maps-maps` <br> |
| [アプリと機能] > [オフライン マップ] > [マップをダウンロード] <sup>2</sup>     | `maps-downloadmaps` <br> |

### <a name="devices"></a>デバイス
| [設定] ページ | URI                          |
|---------------|------------------------------|
| Bluetooth     | `bluetooth` <br> `connecteddevices` |
| マウス <sup>2</sup>      | `mouse` <br>  |
| USB <sup>2</sup>      | `usb` <br>  |

### <a name="privacy"></a>プライバシー
| [設定] ページ            | URI                                             |
|--------------------------|-------------------------------------------------|
| アカウント情報             | `privacy-accountinfo`              |
| アプリの診断        | `privacy-appdiagnostics`              |
| バックグラウンド アプリ        | `privacy-backgroundapps`              |
| 予定表                 | `privacy-calendar`                    |
| 通話履歴             | `privacy-callhistory`                 |
| カメラ                   | `privacy-webcam`                      |
| 連絡先                 | `privacy-contacts`                    |
| 診断とフィードバック | `privacy-feedback`                    |
| ドキュメント                | `privacy-documents`                   |
| Email                    | `privacy-email`                       |
| ファイル システム              | `privacy-broadfilesystemaccess`       |
| 全般 <sup>2</sup>             | `privacy-general`       |
| インクと入力の個人用設定<sup>2</sup>             | `privacy-speechtyping`       |
| 場所                 | `privacy-location`                    |
| メッセージング                | `privacy-messaging`                   |
| Microphone               | `privacy-microphone`                  |
| モーション <sup>2</sup>               | `privacy-motion`                  |
| 通知            | `privacy-notifications`               |
| その他のデバイス            | `privacy-customdevices`               |
| ピクチャ                 | `privacy-pictures`                    |
| 無線                   | `privacy-radios`                      |
| スクリーンショットの境界線 <sup>2</sup>             | `privacy-graphicsCaptureWithoutBorder`       |
| スクリーンショットとアプリ <sup>2</sup>             | `privacy-graphicsCaptureProgrammatic`       |
| 音声                   | `privacy-speech`                      |
| タスク                    | `privacy-tasks`                       |
| ユーザーの移動           | `privacy-backgroundspatialperception` |
| ビデオ                   | `privacy-videos`                      |
| 音声のアクティブ化       | `privacy-voiceactivation`             |

### <a name="network--internet"></a>ネットワークとインターネット
| [設定] ページ | URI                              |
|---------------|----------------------------------|
| 機内モード<sup>2</sup> | `network-airplanemode`        |
| プロキシ | `network-proxy`        |
| VPN   | `network-vpn`          |
| Wi-Fi  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a>システム
| [設定] ページ      | URI                                |
|--------------------|------------------------------------|
| バッテリー<sup>2</sup>           | `batterysaver`<br>|
| バッテリー<sup>2</sup>           | `batterysaver-settings`<br>|
| 色             | `colors`<br>`personalization-colors` |
| ホログラム<sup>2</sup>  |  `holograms`  |
| 調整<sup>2</sup> |  `calibration` |
| 通知とアクション  | `notifications`          |
| 共有エクスペリエンス | `crossdevice` 
| サウンド<sup>2</sup>           | `sound`<br>|
| [サウンド] > [アプリのボリュームとデバイスの優先順位] <sup>2</sup>           | `apps-volume`<br>|
| [サウンド] > [サウンド デバイスを管理] <sup>2</sup>           | `sound-devices`<br>|
| ストレージ            | `storagesense`           |
| [サウンド] > [記憶域センスの構成] <sup>2</sup>           | `storagepolicies`<br>|

### <a name="time--language"></a>時刻と言語
| [設定] ページ | URI                                           |
|---------------|-----------------------------------------------|
| 日付と時刻 <sup>2</sup> | `dateandtime`                  |
| キーボード <sup>2</sup> | `keyboard`                  |
| 言語 <sup>2</sup> | `language`                  |
| 言語 <sup>2</sup> | `regionlanguage-languageoptions`                  |
| Language      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| リージョン        | `regionformatting`                  |

### <a name="update--security"></a>アップデートとセキュリティ
| [設定] ページ                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| 詳細オプション                    | `windowsupdate-options`         |
| リセットと回復 <sup>2</sup>      | `reset`         |
| Windows Insider Program               | `windowsinsider` <br>`windowsinsider-optin`          |
| Windows Update                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><sup>1</sup>`windowsupdate-options`<br><sup>1</sup>`windowsupdate-restartoptions` |
| Windows Update - 更新プログラムの確認 | `windowsupdate-action`          |


- <sup>1</sup> - Windows Holographic バージョン 21H1 以前のバージョンの場合、次の 2 つの URI では、実際には **[詳細オプション]** ページまたは **[オプション]** ページに移動する必要があります。メインの Windows Update ページをブロックまたは表示するのみです。
  -  windowsupdate-options
  -  windowsupdate-restartoptions

- <sup>2</sup> - Holographic 21H1 Windows 21H1 以上で使用できます。


Windows 10 設定 URI の完全なリストについては、[起動設定](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)のドキュメントをご覧ください。
