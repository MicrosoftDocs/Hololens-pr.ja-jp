---
title: HoloLens を再起動、リセット、または回復する
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
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
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5da7f954454b5713823c5aa94742f9c9c0033ca2
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828599"
---
# HoloLens 2 のリセットと回復

## デバイスの充電

トラブルシューティング手順を開始する前に、可能であれば、デバイスが少なくとも 20 ~ 40% 充電されていることを確認してください。

HoloLens 2 デバイスに付属の充電器と USB Type-C ケーブルを使用していることを確認してください。 それらが利用できない場合は、利用可能な充電器が少なくとも 15W の電力をサポートできることを確認してください。

> [!NOTE]
> 可能であれば、PC を使用して USB 経由でデバイスを充電しないでください。充電が非常に遅くなるためです。

デバイスが正しく起動して実行されている場合、バッテリーの充電をチェックするには 3 つの方法があります。

1. HoloLens デバイス UI のメイン メニューから。
2. 電源ボタンの近くにある LED を使用する (40% の場合、少なくとも 2 つの点灯した LED が見えるはずです)。
3. ホスト PC でエクスプローラー ウィンドウを開き、左側の [この PC] の下にある HoloLens 2 デバイスを探します。
    
      a.  デバイス名を右クリックして、プロパティを選択します。 デバイスのバッテリー レベルを示すダイアログが表示されます。

![HoloLens 2 ResetRecovery](images/ResetRecovery2.png)

デバイスをスタートアップ メニューから起動できない場合は、ホスト PC の LED と列挙値を記録し、トラブルシューティング ガイド (https://docs.microsoft.com/hololens/hololens-troubleshooting)) に従います。 デバイスの状態がトラブルシューティング ガイドに記載されている状態のいずれにも該当しない場合は、デバイスをホスト PC に再接続せずに、**ハード リセット手順**を実行しますが、代わりに電源に接続します。 デバイスが充電されるまで少なくとも 1 時間待ちます。

## デバイスをリセットする

特定の状況下では、SW UI を使用せずにデバイスを手動でリセットする必要がある場合があります。 

### 標準手順
1. Type-C ケーブルを抜いて、デバイスを電源またはホスト PC から切断します。

2. **電源ボタン**を 15 秒間押し続けます。 すべての LED がオフになるはずです。

3. 2 ~ 3 秒待ってから**電源ボタン**を短く押します。電源ボタンの近くの LED が点灯し、デバイスの起動が始まります。 

4. デバイスをホスト PC に接続し、デバイス マネージャーを開きます (Windows 10 の場合は、**「Windows」キー**を押し、次に **「x」キー**を押して、「デバイス マネージャー」をクリックします)。下の図に示すように、デバイスが Microsoft HoloLens として正しく列挙されていることを確認します。

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

### ハード リセット手順

標準のリセット手順が機能しない場合は、ハード リセット手順を使用できます。

1. Type-C ケーブルを抜いて、デバイスを電源またはホスト PC から切断します。

2. **[音量を下げる] + 電源ボタン**を 15 秒間押し続けます。

3. デバイスは自動的に再起動します。 

4. デバイスをホスト PC に接続し、デバイス マネージャーを開きます (Windows 10 の場合は、**「Windows」キー**を押し、次に **「x」キー**を押して、「デバイス マネージャー」をクリックします)。下の図に示すように、デバイスが Microsoft HoloLens として正しく列挙されていることを確認します。

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLens_DeviceManager.png)

## デバイスをきれいに再フラッシュする

異常な状況では、デバイスのクリーン フラッシュが必要になることがあります。 HoloLens 2 デバイスを再フラッシュするには 2 つの方法があります。 すべての再フラッシュ手順では、[Windows Store から高度な回復コンパニオン アプリをインストールする](https://www.microsoft.com/store/productId/9P74Z35SFRS8)必要があります。 デバイスをリセットすると、TPM リセットを含むすべての個人データ、アプリ、設定が消去されます。

高度な回復コンパニオンは現在、[Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004) の機能リリース ビルドをダウンロードするように設定されています。最新の HoloLens 2 FFU をダウンロードして高度な回復コンパニオン経由でデバイスをフラッシュする場合は、[こちら](https://aka.ms/hololens2download)からダウンロードできます。 これは最新の状態に保たれ、最新の一般に入手可能なビルドと一致します。 

フラッシュ手順を開始する前に、アプリが Windows 10 PC にインストールされて実行されており、デバイスを検出する準備ができていることを確認してください。

![HoloLens 2 クリーン再フラッシュ](images/ARC1.png)

### 通常の手順

1. HoloLens デバイスの実行中に、以前に高度な回復コンパニオン アプリを起動した Windows 10 PC に接続します。

2. デバイスが自動的に検出され、高度な回復コンパニオン アプリの UI が次のように更新されます。

![HoloLens 2 クリーン再フラッシュ](images/ARC2.png)

3. 高度な回復コンパニオン アプリの UI で HoloLens 2 デバイスを選択し、指示に従ってフラッシュを完了します。

### 手動の手順

デバイスが正しく起動しない場合は、HoloLens 2 デバイスを回復モードにする必要がある場合があります。

1. Type-C ケーブルを抜いて、デバイスを電源またはホスト PC から切断します。 

2. **電源ボタン**を 15 秒間押し続けます。 すべての LED がオフになります。 

3. **[音量を上げる] ボタン**を押しながら、**電源ボタン**を押して離し、デバイスを起動します。 15 秒待ってから、[音量を上げる] ボタンを離します。 デバイスの 5 つの LED のうち、真ん中の LED のみが点灯します。

4. デバイスをホスト PC に接続し、デバイス マネージャーを開きます (Windows 10 の場合は、**「Windows」キー**を押し、次に **「x」キー**を押して、「デバイス マネージャー」をクリックします)。下の図に示すように、デバイスが Microsoft HoloLens として正しく列挙されていることを確認します。

![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

5. デバイスが自動的に検出され、高度な回復コンパニオン アプリの UI が次のように更新されます。

![HoloLens 2 クリーン再フラッシュ](images/ARC2.png)

6. 高度な回復コンパニオン アプリの UI で HoloLens 2 デバイスを選択し、指示に従ってフラッシュを完了します。

## アプリ ストアを使用せずに ARC をダウンロードする

IT 環境が Windows Store アプリの使用を妨げたり、小売店へのアクセスを制限したりする場合、IT 管理者は他の「オフライン」展開パスを通じてこのアプリを利用可能にすることができます。 

- このプロセスは、手順 2 に示すように、他のアプリにも使用できます。 このガイドでは高度な回復コンパニオンに焦点を当てますが、他のオフライン アプリ用に変更することもできます。  

この展開パスは、次の手順で有効にできます。
1.  [ビジネス向けストアの Web サイト](https://businessstore.microsoft.com)に移動し、Azure AD ID でサインインします。
1.  **[管理]、[設定]** の順に移動し、https://businessstore.microsoft.com/manage/settings/shop で説明されているように、[**ショッピング エクスペリエンス**] の下で [**オフライン アプリを表示する**] をオンにします 
1.  [**グループで買い物**] に移動し、[高度な回復コンパニオン](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8) アプリを検索します。
1.  [**ライセンスの種類**] ボックスをオフラインに変更し、[**管理**] をクリックします。
1.  [オフラインで使用するためのパッケージをダウンロードする] で、2 番目の青い [**ダウンロード**] ボタンをクリックします。 ファイル拡張子が .appxbundle であることを確認します。
1.  この段階で、デスクトップ PC がインターネットにアクセスできる場合は、ダブル クリックしてインストールするだけです。 
1.  IT 管​​理者は、System Center Configuration Manager (SCCM) または Intune を介してこのアプリを配布することもできます。
1.  対象の PC にインターネット接続がない場合は、いくつかの追加手順が必要です。 
    1.  エンコードされていないライセンスを選択し、[**ライセンスを生成**] をクリックし、[**必要なフレームワーク**] の下で、[**ダウンロード**] をクリックします。 
    1.  インターネットにアクセスできない PC は、依存関係とライセンスを含むパッケージを適用するために DISM を使用する必要があります。 管理者のコマンド プロンプトで、次のように入力します。

      ```console
      C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
      ```
> [!NOTE]
> このコード例のバージョン番号は、現在利用可能なバージョンと一致しない場合があります。 指定された例とは異なるダウンロード場所を選択した可能性もあります。 必要に応じて変更してください。

> [!TIP]
> 高度な回復コンパニオンを使用して ffu をオフラインでインストールすることを計画している場合、フラッシュ画像をダウンロードして使用できるようにすると便利な場合があります。「[HoloLens 2 の現在の画像](https://aka.ms/hololens2download)」です。 

その他のリソース:
- https://docs.microsoft.com/microsoft-store/distribute-offline-apps 
- https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options


