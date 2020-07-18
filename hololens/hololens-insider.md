---
title: Microsoft HoloLens の Insider Preview
description: 簡単に Insider ビルドを使い始めて、HoloLens の次の主要なオペレーティング システムの更新プログラムに対する貴重なフィードバックをご提供いただけます。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 7/17/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 879ff13b30fdce77d823b66035cd59fa0e217c5f
ms.sourcegitcommit: 209247c83eff5cbabbbdecb8cf6e974eabcb36ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "10883372"
---
# Microsoft HoloLens の Insider Preview

HoloLens 用の最新の Insider Preview ビルドへようこそ!  簡単に使い始めて、HoloLens の次の主要なオペレーティング システムの更新プログラムに対する貴重なフィードバックをご提供いただけます。

Windows insider がチャネルに移動するようになりました。 **ファスト**リングは**Dev チャネル**になります。**スロー**リングは**ベータチャネル**になり、 **release preview** ring は**リリースプレビューチャネル**になります。 マッピングの外観は次のようになります。

![Windows Insider チャネルの説明](images/WindowsInsiderChannels.png)

詳細については、「 [Windows のブログエントリ](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)」を参照してください。

## Insider ビルドの受信の開始

HoloLens 2 デバイスで、**[設定]** -> **[更新とセキュリティ]** -> **[Windows Insider Program]** の順に移動し、**[開始する]** を選択します。 Windows Insider として登録するために使用したアカウントをリンクします。

次に、[ **Windows のアクティブな開発**] を選択し、**開発者チャネル**または**ベータチャネル**のビルドを受け取るかどうかを選択して、プログラムの利用規約を確認します。

**[確認] -> [今すぐ再起動する]** を選択して完了します。 デバイスが再起動したら、**[設定] -> [更新とセキュリティ] -> [更新プログラムのチェック]** の順に移動して最新のビルドを入手します。

## Insider ビルドの受信の停止

Windows Holographic の Insider ビルドを受け取りたくない場合は、HoloLens が製品版ビルドを実行しているときにオプトアウトすることができます。または、Advanced Recovery Companion を使用して[デバイスを回復](hololens-recovery.md)し、Windows Holographic の Insider バージョン以外にデバイスを回復することができます。

> [!CAUTION]
> 新しいプレビュー ビルドを手動で再インストールした後に Insider Preview ビルドの登録を解除すると、ブルー スクリーンが発生するという既知の問題があります。 その後、手動でデバイスを回復する必要があります。 影響を受けるかどうかの詳細については、この[既知の問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)の詳細をご覧ください。

HoloLens が製品版ビルドを実行していることを確認するには、次の操作を行います。

1. **[設定] > [システム] > [バージョン情報]** の順に移動し、ビルド番号を探します。

1. [製品のビルド番号については、リリースノートを参照してください](hololens-release-notes.md)。

Insider ビルドをオプトアウトするには、次の操作を行います。

1. 製品版ビルドを実行している HoloLens で、**[設定] > [更新とセキュリティ] > [Windows Insider Program]** に移動して、**[Insider Preview ビルドの停止]** を選択します。

1. 画面の指示に従って、デバイスでの受信を停止します。


## フィードバックを提供し、問題を報告する

HoloLens で[フィードバック Hub アプリ](hololens-feedback.md)を使用してフィードバックを提供し、問題を報告することができます。 フィードバック Hub を使用すると、エンジニアが問題を迅速にデバッグして解決するのに役立つすべての必要な診断情報が含まれるようになります。  中国語および日本語版の HoloLens に関する問題は、同じ方法で報告する必要があります。

> [!NOTE]
> フィードバック Hub を使用してドキュメント フォルダーにアクセスするかどうかを確認するプロンプトに必ず同意してください (メッセージが表示されたら **[はい]** を選択します)。

## 開発者向けの注意事項

HoloLens の Insider ビルドを使用して自由にアプリケーションを開発してみることをお勧めします。  作業を始めるには、[HoloLens 開発者向けドキュメント](https://developer.microsoft.com/windows/mixed-reality/development)をご覧ください。 これらの同じ手順は HoloLens の Insider ビルドでも使用できます。  HoloLens 開発用に使用しているものと同じビルドの Unity と Visual Studio を使用できます。


## Windows Insider リリース ノート

ここに表示されていない機能を探している場合は、通常は利用可能になっています。 [リリースノート](hololens-release-notes.md)を参照して、どのような機能を利用しているかを確認してください。 [HoloLens を更新して](hololens-update-hololens.md)、最新の機能をすべて入手してください。

このページは、Windows Insider ビルドにリリースされるときに、もう一度新しい機能で更新されます。

| 機能                               | 説明                                                                                   | Insider ビルドで利用可能 |
|---------------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------|
| オートアイポジションのサポート             | アイポジションを積極的に検索して、正確なホログラムの配置を実現します。                       | 19041.1339 +                 |
| グローバルに割り当てられた                | システムレベルで適用可能な複数のアプリキオスクモード用に HoloLens 2 デバイスを構成します。  | 19041.1346 +                 |
| マルチアプリキオスクでアプリを自動起動する | 複数アプリのキオスクモードにサインインしたときに自動的に起動するようにアプリケーションを設定します。 | 19041.1346 +                 |
| Hololens 2 の新しい power policies     | Power timeout 設定に対して新しくサポートされているポリシー。                                          | 19041.1349 +                 |
| 証明書ビューアー                    | 設定アプリでユーザーとデバイスの証明書を表示します。                                        | 19041.1346 +                 |

### オートアイポジションのサポート

HoloLens 2 では、目の位置によって正確なホログラムの配置が可能になり、表示品質が向上しました。 目の位置は、目の追跡結果の一部として計算されます。 ただし、そのためには、各ユーザーがアイ見つめ入力を必要としない場合でも、各ユーザーが目のトラッキングの調整を行う必要があります。

**オートアイポジション (AEP)** では、これらのシナリオを対話式の方法でユーザーの視点を計算できます。  自動目の位置は、ユーザーがデバイスを配置した瞬間から自動的にバックグラウンドで作業を開始します。 ユーザーが前に目を通したトラッキングの調整を行っていない場合は、処理時間が短いときにユーザーの視点がディスプレイシステムに提供されるようになります。 通常、この処理時間は 20-60 秒以内に行われます。 ユーザーデータはデバイス上で保持されないため、ユーザーが停止し、デバイスを再起動するか、デバイスをスリープ状態に戻した場合は、このプロセスを繰り返します。  

Uncalibrated ユーザーがデバイスに配置したときに、オートアイ位置機能によって、システムの動作がいくつか変更されます。 Uncalibrated ユーザーは、以前にデバイスの目のトラッキング調整プロセスを経ていないユーザーを参照しています。

|     アクティブなアプリケーション                           |     現在の動作                                   |     Windows Insider ビルド19041.1339 以降の動作                                                      |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     見つめ対応でないアプリまたはホログラフィックシェル    |     アイトラッキング調整のプロンプトが表示されます。    |     プロンプトは表示されません。                                                                                |
|     宝石対応アプリ                             |     アイトラッキング調整のプロンプトが表示されます。    |     アイトラッキング調整プロンプトは、アプリケーションがアイ見つめストリームにアクセスしたときにのみ表示されます。     |

 ユーザーが、見つめデータにアクセスするアプリケーションから、または見つめ対応のアプリケーションに切り替えた場合、調整のプロンプトが表示されます。 ボックスのエクスペリエンスフローの廃止には変更されません。 
 
視力のデータを必要とするエクスペリエンスや、非常に正確なホログラムの配置が必要な場合は、ユーザーがアイトラッキングの調整プロンプトからアイトラッキングの調整を実行するか、[スタート] メニューから設定アプリを起動して、[**システム > 調整] >** 目の調整 > 実行することをお勧めします。

**既知の問題**
 - この問題を調査していますが、メモリ負荷が高い状態で実行するとアイトラッカードライバーのホストプロセスがクラッシュする可能性があります。 アイトラッキングドライバーのホストプロセスは、自動的に回復する必要があります。

### グローバル割り当てアクセス–キオスクモード
この新機能により、IT 管理者は、システムレベルで適用可能な複数のアプリキオスクモード用に HoloLens 2 デバイスを構成できます。また、システム上の id とのアフィニティはありません。また、デバイスにサインインしたすべてのユーザーに適用されます。 この新機能の詳細について[は、こちらをご覧](hololens-global-assigned-access-kiosk.md)ください。

### 複数アプリのキオスクモードでのアプリケーションの自動起動 
複数のアプリのキオスクモードにのみ適用され、[割り当て済みのアクセス構成] の下の強調表示された属性を使用して、1つのアプリのみを自動起動に指定できます。 

ユーザーがサインインすると、アプリケーションが自動的に起動します。 

```xml
<AllowedApps>                     
    <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Hololens 2 の新しい power policies
新しく追加されたポリシーにより、管理者はアイドルタイムアウトなどの電源状態を制御することができます。 個々のポリシーの詳細を確認するには、ポリシーのリンクをクリックしてください。

|     ポリシードキュメントリンク                |     備考                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Windows 構成デザイナーで使用する値の例:  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Windows 構成デザイナーで使用する値の例:  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Windows 構成デザイナー (100) で使用する値の例                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Windows 構成デザイナー (100) で使用する値の例                                                                          |
|     [スタンドアロン](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows 構成デザイナーで使用する値の例:   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows 構成デザイナーで使用する値の例:  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

### 証明書ビューアー

Windows Insider ビルド 19041.1346 + では、HoloLens 2 設定アプリで証明書ビューアーを追加しています。 この機能を使うと、デバイス上の証明書を簡単かつわかりやすい方法で確認できます。 特定の証明書をすばやく見つけるには、名前、ストア、有効期限のいずれかを指定して並べ替えを行うオプションがあります。 ユーザーは、証明書を直接検索することもできます。 新しい証明書ビューアーを使用すると、管理者とユーザーは、より高度な監査、診断、検証ツールを使用して、デバイスの安全性と準拠性を維持することができるようになりました。  個々の証明書の詳細を表示するには、証明書を選択し、[情報] をクリックします。

> [!NOTE]
> 今後の Windows Insider リリースで解決に向けて取り組んでいる米国以外の言語のローカライズには、既知の制限があります。

-   **監査:** 証明書が正しく展開されていることを確認したり、適切に削除されたことを確認したりすることができます。 
-   **診断:** 問題が発生した場合は、デバイス上に適切な証明書が存在することで、時間が節約され、トラブルシューティングに役立ちます。 
-   **検証:** 証明書が意図された目的であり、機能していることを確認することにより、より大規模な証明書を展開する前に、特に商用環境では時間を節約できます。

証明書を表示するには、[設定] に移動して **& セキュリティ > 証明書 > 更新**します。

![設定アプリの証明書ビューアー](images/hololens-certificate-viewer.png)

## FFU のダウンロードとフラッシュの手順
フライト署名のある FFU でテストするには、フライト署名のある FFU をフラッシュする前にデバイスのフライト ロックを解除する必要があります。
1. PC の場合:

    1. から PC に ffu をダウンロード [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) してください。
    
    1. Microsoft Store ([https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)) から ARC (Advanced Recovery Companion) をインストールします。
    
1. HoloLens でのロック解除:**設定**の  >  **更新 & セキュリティ**  >  **Windows Insider プログラム**を開くと、次にサインアップして、デバイスを再起動します。

1. Flash FFU-「ARC」を使って、フライト署名された FFU を点滅させることができます。
