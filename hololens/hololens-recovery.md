---
title: HoloLens 2 を再起動、リセット、または回復する
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Advanced Recovery Companion を使用してイメージを HoloLens 2 にフラッシュする方法。
keywords: ハウツー, 再起動, リセット, 回復, ハード リセット, ソフト リセット, 電源サイクル, HoloLens, シャットダウン, アーク, Advanced Recovery Companion
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 08/30/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: e9aad32891bb093cbce18671b76549788b19afcb
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034371"
---
# <a name="restart-reset-or-recover-hololens-2"></a>HoloLens 2 を再起動、リセット、または回復する

>[!IMPORTANT]
> トラブルシューティングの手順を開始する前に、可能であれば、デバイスのバッテリ容量が **20 - 40%** 残っていることを確認してください。 電源 ボタンの下 にある[バッテリ インジケーター ライト](hololens2-setup.md#lights-that-indicate-the-battery-level)により、デバイスにログインせずにバッテリ容量を簡単に確認できます。

HoloLens 2 に付属している[充電器と USB タイプ C ケーブル](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1)を使用します。これは、デバイスの充電に最適な方法です。 充電器は、18W の電力 (2A で 9V) を供給します。 付属のプラグを使用すると、HoloLens 2 デバイスは、デバイスがスタンバイ状態のときに 65 分未満でバッテリーを完全に充電できます。 これらのアクセサリが使用できない場合は、使用可能な充電器が少なくとも 15W の電力に対応していることを確認してください。

> [!NOTE]
> 可能であれば、PC を使用してデバイスを USB 経由で充電することは避けてください。遅いです。

デバイスが正常に起動し、動作している場合は、次の 3 つの方法でバッテリの充電レベルを確認できます。

- HoloLens デバイス UI のメイン メニューから。
- 電源ボタンの近くにある LED を確認します (40% が充電されている場合、少なくとも 2 つの点灯した LED が見えるはずです)。
    - デバイスの充電中は、バッテリー インジケーターが点灯し、現在の充電レベルを示します。  最後のライトはゆっくりと点滅し、充電中であることを示します。
    - HoloLens の電源が入っているときは、バッテリー インジケーターにバッテリー レベルが 5 段階で表示されます。
    - 5 個のライトのうち 1 個しか点灯していない場合は、バッテリー レベルが 20 パーセントを下回っています。
    - バッテリー レベルが極端に低い場合にデバイスの電源を入れようとすると、1 個のライトが短く点滅してから消えます。
- ホスト PC で、**エクスプローラー** を開き、 **[この PC]** の下にある HoloLens 2 デバイスを探します。 そのデバイスを右クリックし、 **[プロパティ]** を選択します。 ダイアログ ボックスにバッテリの充電レベルが表示されます。

   ![HoloLens 2 のプロパティ画面にバッテリの残量レベルが表示されます。](images/ResetRecovery2.png)

デバイスが起動メニューから起動できない場合は、ホスト PC の LED の外観とデバイスの一覧を確認します。 次に、[トラブルシューティング ガイド](hololens-troubleshooting.md)に従います。 デバイスの状態がトラブルシューティング ガイドに記載されている状態と一致しない場合は、ホスト PC ではなく、電源に接続されたデバイスで[ハード的なリセット手順](hololens-recovery.md#hard-reset-procedure)を実行してください。 デバイスが充電されるまで少なくとも 1 時間待ちます。

## <a name="reset-the-device"></a>デバイスをリセットする

状況によっては、ソフトウェアの UI を使用せずにデバイスを手動でリセットする必要がある場合があります。

### <a name="standard-procedure"></a>標準手順

1. Type-C ケーブルを抜いて、デバイスを電源またはホスト PC から切断します。

2. **[電源]** ボタンを 15 秒間押し続けます。 すべての LED がオフになるはずです。

3. 2 - 3 秒待ってから、 **[電源]** ボタンを短く押します。 電源ボタンの近くの LED が点灯し、デバイスが起動します。

4. デバイスをホスト PC に接続し、デバイス マネージャーを開きます。 (Windows 10 の場合は、**Windows** キーを押し、次に **X** キーを押して、**デバイス マネージャー** を選択します)。次の図に示すように、デバイスが *Microsoft HoloLens* として正しく列挙されていることを確認します。

   ![HoloLens 2 MicrosoftHoloLensRecovery デバイス マネージャー。](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a>ハード リセット手順

標準のリセット手順が機能しない場合は、ハード リセット手順を使用します。

1. Type-C ケーブルを抜いて、デバイスを電源またはホスト PC から切断します。

1. **[ボリューム ダウン]** ボタン +  **[電源]** ボタンを 15 秒間押したままにします。 デバイスが自動的に再起動します。

1. デバイスをホスト PC に接続します。

1. デバイス マネージャーを開きます (Windows 10 の場合は **Windows** キー、次に **X** キーを押して、**デバイス マネージャー** を選択します)。 次の図に示すように、デバイスが *Microsoft HoloLens* として正しく列挙されていることを確認します。

   ![HoloLens 2 MicrosoftHoloLensRecovery デバイス マネージャー 2。](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a>デバイスをきれいに再フラッシュする

異常な状況では、HoloLens 2 のクリーン フラッシュが必要になることがあります。 なお、以下の問題については、クリーン再フラッシュの実行によって解決することは期待できません。

- [ディスプレイの色の均一性](hololens2-display.md)
- 起動時に音がするが、ディスプレイ出力がない
- [1-3-5 の LED パターン](hololens2-setup.md#lights-to-indicate-problems)
- [過熱](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- OS のクラッシュ (アプリケーションのクラッシュとは異なります)

デバイスを再フラッシュするには 2 つの方法があります。 どちらの場合も、最初に、[Windows Store から Advanced Recovery Companion をインストールする必要があります](https://www.microsoft.com/store/productId/9P74Z35SFRS8)。

>[!WARNING]
>デバイスを再フラッシュすると、TPM リセットを含むすべての個人データ、アプリ、設定が消去されます。

既定では、Advanced Recovery Companion は最新の機能リリース ビルドをダウンロードするように設定されています。最新の機能リリースについては、[HoloLens 2 のリリース ノート](hololens-release-notes.md)を参照してください。 最新の HoloLens 2 Full Flash Update (FFU) パッケージを取得し、Advanced Recovery Companion を使用してデバイスを再フラッシュするには、最新のマンスリー HoloLens 2 イメージをダウンロードしてください: [https://aka.ms/hololens2download](https://aka.ms/hololens2download)。 このバージョンは、一般的に利用可能な最新のビルドです。

再フラッシュ手順を開始する前に、アプリが Windows 10 PC にインストールされて実行されており、デバイスを検出する準備ができていることを確認してください。 また、HoloLens の充電が少なくとも 40% 以上になっていることをご確認ください。

![HoloLens 2 クリーン再フラッシュのスクリーンショット。](images/ARC1.png)

### <a name="normal-procedure"></a>通常の手順

1. HoloLens デバイスの実行中に、以前に Advanced Recovery Companion アプリを開いた Windows 10 PC に接続します。

   デバイスが自動的に検出され、Advanced Recovery Companion アプリの UI が更新プロセスを開始します。

   ![HoloLens 2 クリーン 再フラッシュの初期画面。](images/ARC2.png)

1. Advanced Recovery Companion アプリの UI で HoloLens 2 デバイスを選択し、指示に従って再フラッシュを完了します。

### <a name="manual-procedure"></a>手動の手順

次の場合は、デバイスを回復モードにする必要がある可能性があります。

- HoloLens 2 が正常に起動しない
- Advanced Recovery Companion がデバイスを検出できない
- ユーザーが 1 人しかいないデバイスのパスワード/PIN がわからなくなった

1. Type-C ケーブルを抜いて、デバイスを電源またはホスト PC から切断します。

2. **[電源]** ボタンを 15 秒間押し続けます。 すべての LED がオフになります。

3. **[ボリューム アップ]** ボタンを押 しながら **[電源]** ボタンを 押して離 し、デバイスを起動します。 15 秒待って、 **[ボリューム アップ]** ボタンを離します。 5 つの LED のうち中央の LED だけが点灯します。

4. デバイスをホスト PC に接続し、デバイス マネージャーを開きます。 (Windows 10 の場合は、**Windows** キーを押し、次に **X** キーを押して、**デバイス マネージャー** を選択します)。次の図に示すように、デバイスが Microsoft HoloLens として正しく列挙されていることを確認します。

   ![HoloLens 2 MicrosoftHoloLensRecovery。](images/MicrosoftHoloLensRecovery.png)

   デバイスが自動的に検出され、Advanced Recovery Companion アプリの UI が更新プロセスを開始します。

   ![HoloLens 2 クリーン再フラッシュの画面。](images/ARC2.png)

6. Advanced Recovery Companion アプリの UI で HoloLens 2 デバイスを選択し、指示に従って再フラッシュを完了します。

## <a name="troubleshoot-advanced-recovery-companion"></a>Advanced Recovery Companion のトラブルシューティング

1. フラッシュを試みる前に、デバイスが 40% 以上に充電されるようにしてください。

1. デバイスがロックされていないことを確認します。

1. デバイスがハブではなくホスト PC に直接接続されていることを確認します。

1. デバイスがユニバーサル シリアル バス ドライバーに HoloLens/HoloLens Recovery デバイスと表示されない場合は、次のことを確認します。
    1. **[ポート]** (Qualcomm HS-USB デバイスの場合)
    1. **[その他のデバイス]** (QUSB_BULK デバイスの場合) - HoloLens を検出するために必要なドライバーがホスト PC にありません。 右クリックして [ドライバーの更新] を選択し、オンラインでドライバーを検索するか、[Windows Update の設定で [オプションの更新プログラム] をオンにします](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674)。 ドライバーをダウンロードすると、ARC によって検出できるようになります。

1. ARC によってデバイスが検出されない場合は、PC 上のデバイスからデバイスへエクスプローラーから接続できます。 それができない場合、

    1. デバイスに、その接続を無効にする USB ポリシーがある可能性があります。 その場合は、[手動フラッシュ モード](hololens-recovery.md#manual-procedure)を試してください。
    2. ポリシーがない場合は、別の USB ケーブルを試してください。

1. デバイスに [1-3-5-LED パターン](hololens2-setup.md#lights-to-indicate-problems)が表示されていないことを確認します。

## <a name="download-arc-without-using-the-app-store"></a>アプリ ストアを使用せずに ARC をダウンロードする

IT 環境が Windows Store アプリの使用を妨げたり、小売店へのアクセスを制限したりする場合、IT 管理者は「オフライン」展開パスを通じてこのアプリを利用可能にすることができます。

 >[!NOTE]
 > - IT 管​​理者は、System Center Configuration Manager (SCCM) または Intune を介してこのアプリを配布することもできます。
 > - このガイドでは高度な回復コンパニオンに焦点を当てますが、プロセスは、他の「オフライン」アプリにも使用できます。

展開パスを有効にする手順は、次のとおりです。

1. [Microsoft Store for Business](https://businessstore.microsoft.com) に進み、Azure Active Directory ID を使用してサインインします。

1. **[管理][設定]** の順にクリックします。 **[ショッピング エクスペリエンス]** で **[オフライン アプリを表示]** をオンにします。

1. **[グループのショッピング**] にアクセスし、 [**_[Advanced Recovery Companion]_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8) を検索します。

1. **ライセンスの種類** を **_[オフライン_ *] _ に変更し、* [_ 管理]** を選択します。

1. **[オフラインで使用するパッケージをダウンロード]** で、2番目の青い **[ダウンロード]** ボタンを選択します。 ファイル拡張子が *.appxbundle* であることを確認します。

    - この段階で、デスクトップ PC がインターネットにアクセスできる場合は、パッケージをダブルクリックしてアプリをインストールします。

    - 接続先 PC にインターネット接続がない場合は、次の手順を実行します。
       1. エンコードされていないライセンスを選択し、 **[ライセンスの生成]** を選択します。
       2. **[必須のフレームワーク]** で、 **[ダウンロード]** を選択します。
       3. DISM を使用して、依存関係とライセンスを持つパッケージを適用します。 管理者のコマンド プロンプトから次のコマンドを実行します。

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > このコード例のバージョン番号は、現在利用可能なバージョンと一致しない場合があります。 例とは異なるダウンロード場所を選択した可能性もあります。 必要に応じてコマンドを変更します。

> [!TIP]
> Advanced Recovery Companion を使用して FFU をオフラインでインストールする場合は、フラッシュ イメージをダウンロードすると便利です。 [**HoloLens 2 の現在のイメージをダウンロードします**](https://aka.ms/hololens2download)。

その他のリソース:

- [オフライン アプリの配布](/microsoft-store/distribute-offline-apps) 
- [DISM アプリ パッケージ (.appx または .appxbundle) によるコマンドライン オプションのサービス](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
