---
title: HoloLens を再起動、リセット、または回復する
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
description: 高度な回復コンパニオンを使用してイメージを HoloLens 2 にフラッシュする方法。
keywords: ハウツー、再起動、リセット、回復、ハード リセット、ソフト リセット、電源サイクル、HoloLens、シャットダウン、アーク、高度な回復コンパニオン
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
ms.openlocfilehash: 8c028ed39cf0925ebff18ca69889de2d87f1e7eb
ms.sourcegitcommit: e3056a433aeebb8bc45dc3f6db9a75f212fdf53b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2020
ms.locfileid: "10996415"
---
# HoloLens 2 を再起動、リセット、または回復する

## デバイスを充電する

トラブルシューティングの手順を開始する前に、可能であれば、デバイスがバッテリ容量の 20 - 40% に充電されていることを確認してください。 HoloLens 2 デバイスに付属の充電器と USB Type-C ケーブルを使用します。 デバイスに付属している電源アダプターと USB-C-C ケーブルは、HoloLens 2 を充電する最適な方法です。 充電器は、18W の電力 (2A で 9V) を供給します。 これらのアクセサリが使用できない場合は、使用可能な充電器が少なくとも 15W の電力に対応していることを確認してください。

> [!NOTE]
> 可能であれば、PC を使用してデバイスを USB 経由で充電することは避けてください。これは遅いです。

デバイスが正常に起動し、動作している場合は、次の 3 つの方法でバッテリの充電レベルを確認できます。

- HoloLens デバイス UI のメイン メニューから。
- 電源ボタンの近くにある LED を確認します (40% が充電されている場合、少なくとも 2 つの点灯した LED が見えるはずです)。
    - デバイスの充電中は、バッテリー インジケーターが点灯し、現在の充電レベルを示します。  最後のライトはゆっくりと点滅し、充電中であることを示します。
    - HoloLens の電源が入っているときは、バッテリー インジケーターにバッテリー レベルが 5 段階的で表示されます。
    - 5 個のライトのうち 1 個しか点灯していない場合は、バッテリー レベルが 20 パーセントを下回っています。
    - バッテリー レベルが極端に低い場合にデバイスの電源を入れようとすると、1 個のライトが短く点滅してから消えます。
- ホスト PC で**エクスプローラー**を開き、左側の [**この PC**] の下にある HoloLens 2 デバイスを探します。 そのデバイスを右クリックし、**[プロパティ]** を選びます。 ダイアログ ボックスにバッテリの充電レベルが表示されます。

   ![HoloLens 2 のプロパティ画面にバッテリの残量レベルが表示されます。](images/ResetRecovery2.png)

デバイスが起動メニューから起動できない場合は、ホスト PC の LED の外観とデバイスの一覧を確認します。 次に、[トラブルシューティング ガイド](https://docs.microsoft.com/hololens/hololens-troubleshooting)に従います。 デバイスの状態がトラブルシューティング ガイドに記載されている状態と一致しない場合は、ホスト PC ではなく、電源に接続されたデバイスで[ハード リセット手順](hololens-recovery.md#hard-reset-procedure)を実行してください。 デバイスが充電されるまで少なくとも 1 時間待ちます。

## デバイスをリセットする

状況によっては、ソフトウェアの UI を使用せずにデバイスを手動でリセットする必要がある場合があります。

### 標準手順
1. Type-C ケーブルを抜いて、デバイスを電源またはホスト PC から切断します。

2. **電源**ボタンを 15 秒間押し続けます。 すべての LED がオフになるはずです。

3. 2 - 3 秒待ってから、**電源**ボタンを短く押します。 電源ボタンの近くの LED が点灯し、デバイスが起動します。

4. デバイスをホスト PC に接続し、デバイス マネージャーを開きます。 (Windows 10 の場合は、**Windows キー**を押し、次に**X キー**を押して、**デバイス マネージャー**を選択します)。次の図に示すように、デバイスが *Microsoft HoloLens* として正しく列挙されていることを確認します。

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

### ハード リセット手順

標準のリセット手順が機能しない場合は、ハード リセット手順を使用します。

1. Type-C ケーブルを抜いて、デバイスを電源またはホスト PC から切断します。

2. **音量減** + **電源**ボタンを 15 秒間押し続けます。 デバイスが自動的に再起動します。

4. デバイスをホスト PC に接続します。
5. デバイス マネージャーを開きます (Windows 10 の場合は、**Windows キー**を押し、次に**X キー**を押して、**デバイス マネージャー**を選択します)。 次の図に示すように、デバイスが *Microsoft HoloLens* として正しく列挙されていることを確認します。

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## デバイスをきれいに再フラッシュする

異常な状況では、HoloLens 2 のクリーン フラッシュが必要になることがあります。 なお、以下の問題については、クリーン再フラッシュの実行によって解決することは期待できません。
- [画面の色の均一性](hololens2-display.md)
- 起動時に音がするが、ディスプレイ出力がない
- [1-3-5 の LED パターン](hololens2-setup.md#lights-to-indicate-problems)
- [オーバーヒート](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- OS のクラッシュ (アプリケーションのクラッシュとは異なります)

デバイスを再フラッシュするには 2 つの方法があります。 両方の場合、まず、[Windows ストアから高度な回復コンパニオン](https://www.microsoft.com/store/productId/9P74Z35SFRS8)をインストールする必要があります。

>[!WARNING]
>デバイスを再フラッシュすると、TPM リセットを含むすべての個人データ、アプリ、設定が消去されます。

基本的に高度な回復コンパニオンは、現在 [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004) の機能リリース ビルドをダウンロードするように設定されています。 高度な回復コンパニオンを介してデバイスを再フラッシュするための最新の HoloLens 2 Full Flash Update (FFU) パッケージを取得するには、[ここからダウンロード](https://aka.ms/hololens2download)してください。 このバージョンは、一般的に利用可能な最新のビルドです。

再フラッシュ手順を開始する前に、アプリが Windows 10 PC にインストールされて実行されており、デバイスを検出する準備ができていることを確認してください。

![HoloLens 2 クリーン再フラッシュ スクリーンショット](images/ARC1.png)

### 通常の手順

1. HoloLens デバイスの実行中に、以前に高度な回復コンパニオン アプリを開いた Windows 10 PC に接続します。
 
   デバイスが自動的に検出され、高度な回復コンパニオン アプリの UI が更新プロセスを開始します。

   ![HoloLens 2 クリーン 再フラッシュの初期画面](images/ARC2.png)

3. 高度な回復コンパニオン アプリの UI で HoloLens 2 デバイスを選択し、指示に従って再フラッシュを完了します。

### 手動の手順

HoloLens 2 が正常に起動しない場合は、デバイスを回復モードにする必要があります。

1. Type-C ケーブルを抜いて、デバイスを電源またはホスト PC から切断します。

2. **電源**ボタンを 15 秒間押し続けます。 すべての LED がオフになります。

3. **[音量を上げる] ボタン**を押しながら、**電源ボタン**を押して離し、デバイスを起動します。 15 秒待ってから、**[音量を上げる]** ボタンを離します。 5 つの LED のうち中央の LED だけが点灯します。

4. デバイスをホスト PC に接続し、デバイス マネージャーを開きます。 (Windows 10 の場合は、**Windows キー**を押し、次に**X キー**を押して、**デバイス マネージャー**を選択します)。次の図に示すように、デバイスが Microsoft HoloLens として正しく列挙されていることを確認します。

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   デバイスが自動的に検出され、高度な回復コンパニオン アプリの UI が更新プロセスを開始します。

   ![HoloLens 2 クリーン再フラッシュの画面](images/ARC2.png)

6. 高度な回復コンパニオン アプリの UI で HoloLens 2 デバイスを選択し、指示に従って再フラッシュを完了します。

## アプリ ストアを使用せずに ARC をダウンロードする

IT 環境が Windows Store アプリの使用を妨げたり、小売店へのアクセスを制限したりする場合、IT 管理者は「オフライン」展開パスを通じてこのアプリを利用可能にすることができます。

 >[!NOTE] 
 > - IT 管​​理者は、System Center Configuration Manager (SCCM) または Intune を介してこのアプリを配布することもできます。
 > - このガイドでは高度な回復コンパニオンに焦点を当てますが、プロセスは、他の「オフライン」アプリにも使用できます。

展開パスを有効にする手順は、次のとおりです。
1. [ビジネス向け Microsoft Store](https://businessstore.microsoft.com) に移動し、Azure Active Directory ID を使用してサインインします。

1. **[管理]、[設定]** の順に移動します。 **[買い物エクスペリエンス]** で **[オフライン アプリの表示]** をオンにします。 
1. [**グループで買い物**] に移動し、[***高度な回復コンパニオン***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8) アプリを検索します。
1. [**ライセンスの種類**] を***オフライン***に変更し、**[管理]** を選択します。
1. **[オフラインで使用するためのパッケージをダウンロードする]** で、2 番目の青い **[ダウンロード]** ボタンを選択します。 ファイル拡張子が *.appxbundle* であることを確認します。

    - この段階で、デスクトップ PC がインターネットにアクセスできる場合は、パッケージをダブルクリックしてアプリをインストールします。


    - 接続先 PC にインターネット接続がない場合は、次の手順を実行します。 
       1. エンコードされていないライセンスを選択して、**[ライセンスを生成]** を選択します。
       2. **[必要なフレームワーク]** で **[ダウンロード]** を選択します。
       3. DISM を使用して、依存関係とライセンスを持つパッケージを適用します。 管理者のコマンド プロンプトから次のコマンドを実行します。

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > このコード例のバージョン番号は、現在利用可能なバージョンと一致しない場合があります。 例とは異なるダウンロード場所を選択した可能性もあります。 必要に応じてコマンドを変更します。

> [!TIP]
> 高度な回復コンパニオンを使用して FFU をオフラインでインストールする場合は、フラッシュ イメージをダウンロードすると便利です。 [**HoloLens 2**](https://aka.ms/hololens2download) の現在の画像をダウンロードします。 

その他のリソース:
- [オフライン アプリの配布](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [DISM アプリ パッケージ (.appx または .appxbundle) によるコマンドライン オプションのサービス](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
