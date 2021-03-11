---
title: HoloLens 2 のハードウェア
description: Windows 10 を実行する、Microsoft の自立型ホログラフィック コンピューターの最新版である Microsoft HoloLens 2 を構成するコンポーネントについて説明します。
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 10/20/2020
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: feedb0093b8766de75079a61c286c99817ab18f9
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400697"
---
# <a name="hololens-2-hardware"></a>HoloLens 2 のハードウェア

![HoloLens 2 の側面図](images/hololens2-breakdown.png)

Microsoft HoloLens 2 は、自立型ホログラフィック コンピューターです。  HoloLens (第 1 世代) から始まったホログラフィック コンピューティングをさらに改良し、より快適でイマーシブなエクスペリエンスを実現しています。Mixed Reality でのコラボレーションに必要なオプションも多数追加されています。

## <a name="hololens-components"></a>HoloLens のコンポーネント

- **バイザー**。 HoloLens のセンサーとディスプレイが含まれます。 バイザーは、HoloLens を装着した状態で、上に回転させて持ち上げることができます。
- **ヘッドバンド**。 HoloLens を使用するには、調整ホイールを使用してヘッドバンドを展開します。 HoloLens を装着したら、ヘッドバンドが快適にフィットするまで、調整ノブを右に回して締めます。
- **明るさ調整ボタン**。 HoloLens を装着している状態では、明るさボタンは、こめかみ近くのバイザーの左側にあります。
- **音量ボタン**。 HoloLens を装着している状態では、音量ボタンは、こめかみ近くのバイザーの右側にあります。
- **電源ボタン**。 HoloLens を装着している状態では、電源ボタンは背面の外側のカバーの右側にあります。
- **USB-C ポート**。 HoloLens を装着している状態では、USB-C ポートは背面の外側のカバーの右側の電源ボタンの下にあります。

## <a name="in-the-box"></a>付属品

- **[ブロー パッド](https://www.microsoft.com/p/microsoft-hololens-2-brow-pad/90z10rsslqp0)**。 ブロー パッドは、必要に応じて取り外すことも、再装着することもできます。
- **[オーバーヘッド ストラップ](https://www.microsoft.com/p/microsoft-hololens-2-overhead-strap/8wxl8wmk1f7z)**。 HoloLens を装着した状態で動き回る場合は、オーバーヘッド ストラップを使用してデバイスの位置を固定します。 HoloLens を長時間装着する場合に、オーバーヘッド ストラップを使用すると、より快適な装着感が実現します。
- **[USB-C 充電器とケーブル](https://www.microsoft.com/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5)**。 電源モジュールは電源コンセントに差し込みます。 USB-C ケーブルを使用すると、HoloLens を電源に接続して充電することも、HoloLens をコンピューターに接続することもできます。
- **マイクロファイバー クロス**。 HoloLens バイザーの清掃に使用します。

### <a name="power-supply-details"></a>電源アダプターの詳細

デバイスに付属している電源アダプターと USB ケーブルは、充電に対応する最適なメカニズムです。 電源アダプターは 18W の充電器です。  2A で 9V を供給します。

充電率と速度は、デバイスが実行されている環境によって異なる場合があります。

デバイスがオンになっているときに、内部バッテリー充電率を維持または高めるためには、15W 以上の充電器に接続する必要があります。

## <a name="device-specifications"></a>デバイスの仕様

### <a name="display"></a>ディスプレイ

|   |   |
| - | - |
| 光学 | シースルー ホログラフィック レンズ (導波路) |
| ホログラフィック解像度 | 2 k 3:2 光エンジン |
| ホログラフィック密度 | >2.5 k 光点 (ラジアンあたりの光点) |
| アイベースのレンダリング | 3 次元での目の位置に対するディスプレイの最適化 |

### <a name="sensors"></a>センサー

|   |   |
| - | - |
| ヘッド トラッキング | 4 台の可視光カメラ |
| アイ トラッキング | 2 台の赤外線 (IR) カメラ |
| 深度 | 1-MP ToF (Time of Flight) 深度センサー |
| 慣性計測装置 (IMU: Inertial measurement unit) | 加速度計、ジャイロスコープ、磁力計 |
| カメラ | 静止画 8-MP、1080p30 ビデオ |

![HoloLens 2 センサー](images/hololens2-front-view.png)

> [!NOTE]
> 写真で呼び出されるセンサーを覆い隠さないでください。 ヘッド トラッキング カメラは非常に幅広い FOV を持っています。覆い隠さないだけでなく、カメラの周囲には何も配置しないでください。

### <a name="audio-and-speech"></a>オーディオと音声認識

|   |   |
| - | - |
| マイクロフォン アレイ | 5 チャネル |
| スピーカー | 空間音響を搭載 |

### <a name="compute-and-connectivity"></a>コンピューティングと接続性

|   |   |
| - | - |
| SoC (System on chip) | Qualcomm Snapdragon 850 コンピューティング プラットフォーム ([詳細情報](https://www.qualcomm.com/products/snapdragon-850-mobile-compute-platform)) |
| HPU (Holographic processing unit) | 第 2 世代オーダーメイド ホログラフィック処理装置 |
| メモリ | 4 GB LPDDR4x システム DRAM |
| 記憶域 | 64 GB UFS 2.1 |
| Wi-Fi | 802.11ac 2x2 |
| Bluetooth | 5.0 |
| USB | USB Type-C |

### <a name="power"></a>電源

|   |   |
| - | - |
| バッテリー残量 | 2 - 3 時間のアクティブな使用。 最大 2 週間のスタンバイ時間。 |
| バッテリー技術 | [リチウム バッテリ](https://www.microsoft.com/download/details.aspx?id=43388) |
| 充電動作 | 充電時に完全に機能 |
| 冷却の種類 | 受動的に冷却 (ファンなし) |
| 電力供給 | デバイスがオンになっているときに、内部バッテリー充電率を維持または高めるためには、15W 以上の充電器に接続する必要があります。 |

### <a name="fit"></a>適合性

|   |   |
| - | - |
| サイズ | バンドで調整できる単一サイズ。  眼鏡の上から装着可能。 |
| 重量 | 566 g |

## <a name="device-capabilities"></a>デバイス機能

### <a name="human-understanding"></a>人間の認識

|   |   |
| - | - |
| ハンド トラッキング | 両手完全連動モデル、直接操作 |
| アイ トラッキング | リアルタイム追跡 |
| 音声 | オンデバイスのコマンドとコントロール、インターネット接続を利用した Cortana 自然言語 |

### <a name="environment-understanding"></a>環境の認識

|   |   |
| - | - |
| 6DoF トラッキング | 世界規模の位置追跡 |
| 空間マッピング | リアルタイム環境メッシュ |
| Mixed Reality キャプチャ | ホログラムと物理環境の複合写真、複合ビデオ |

## <a name="pre-installed-software"></a>プレインストール済みソフトウェア

|   |   |
| - | - |
| Windows Holographic オペレーティング システム | Windows Holographic により、Windows 10 ユーザーは HoloLens 2 を使用して、アプリやゲームの一部を Mixed Reality 環境で使用できます。
| 3D ビューアー | [3D ビューアー](https://www.microsoft.com/p/3d-viewer/9nblggh42ths?activetab=pivot:overviewtab)では、3D モデルやアニメーションをリアルタイムで簡単に見ることができます。|
| Cortana | パーソナル生産性アシスタントの [Cortana](https://www.microsoft.com/p/cortana/9nffx4szz23l?activetab=pivot:overviewtab) は、重要なことを常に把握し、必要なものを見つける時間を短縮します。  |
| Dynamics 365 Guides |  [Dynamics 365 Guides](https://www.microsoft.com/p/microsoft-dynamics-365-guides/9n038fb42kkb?activetab=pivot:overviewtab) は、従業員が HoloLens デバイスでより早く新しいスキルを習得できるよう支援します。 |
| Dynamics 365 Remote Assist | [Microsoft Dynamics 365 Remote Assist](https://www.microsoft.com/p/microsoft-dynamics-365-remote-assist/9p77qgw10k9m?activetab=pivot:overviewtab) を使用すると、技術者は Microsoft Teams または Dynamics 365 Remote Assist を使用してリモートの共同作業者と協力し、問題を解決できます。  |
| フィードバック Hub | [フィードバック Hub](https://www.microsoft.com/p/feedback-hub/9nblggh4r32n?activetab=pivot:overviewtab) では、提案や問題を共有することで、Windows とアプリに関するフィードバックを提供できます。  |
| エクスプローラー | エクスプローラーには、ファイル システムにアクセスするためのグラフィカル ユーザー インターフェイスが用意されています。 |
| メールと予定表 | [メール アプリと予定表アプリ](https://www.microsoft.com/p/mail-and-calendar/9wzdncrfhvqm#activetab=pivot:overviewtab)を使用すると、メールの最新の情報を取得し、スケジュールを管理し、連絡先と連絡を取り合うのに役立ちます。 |  
| Microsoft Edge | Microsoft Edge は、閲覧時のプライバシー、生産性、価値の向上を実現する国際的レベルのパフォーマンスを提供します。 |
| Microsoft Store | [Microsoft ストア](https://www.microsoft.com)は、HoloLens で動作するアプリやゲーム用のソースです。|
| 映画 & テレビ | [映画 & テレビ](https://www.microsoft.com/p/movies-tv/9wzdncrfj3p2?activetab=pivot:overviewtab)は、最新のエンターテインメントを 1 つのシンプルで高速かつエレガントなアプリでお届けします。 |
| OneDrive | [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3?activetab=pivot:overviewtab) を使用すると、すべてのデバイスからどこからでもファイルにアクセスし、編集できます。  |
| フォト| [フォト](https://www.microsoft.com/p/microsoft-photos/9wzdncrfjbh4?activetab=pivot:overviewtab)では、写真やビデオの表示と編集、ムービーの作成、アルバムの作成が可能です。  |
| 設定 | 設定アプリでは、Windows Holographic の動作を詳細にカスタマイズできます。  |
| ヒント | [ヒント](https://www.microsoft.com/p/microsoft-tips/9wzdncrdtbjj?activetab=pivot:overviewtab)を使用すると、Windows Holographic で実行できる驚きの操作やあまり知られていない操作をマスターできます。 |

## <a name="device-certifications"></a>デバイスの認定規格

### <a name="safety"></a>安全性

* [製品の安全性](https://support.microsoft.com/en-us/help/4023454/safety-information)
* [製品の安全性に関する警告と手順](https://support.microsoft.com/en-us/help/4558037/product-safety-warnings-and-instructions)
* 目の保護: HoloLens 2 は、ANSI Z87.1、CSA Z94.3、および EN 166 の規格試験済みであり、基本的な衝撃保護要件に準拠しています。
* [SAR 情報](https://support.microsoft.com/help/12673/mobile-devices-sar-information)

### <a name="regulatory-information"></a>規制に関する情報
[HoloLens の規制](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information): 温度、廃棄、ラジオやテレビの電波妨害に関する情報を含みます。

## <a name="warranty-information"></a>保証情報

Microsoft HoloLens 2 には、標準の限定[保証](https://support.microsoft.com/topic/warranties-extended-service-plans-and-terms-conditions-for-your-device-eedf7a23-84a7-1a47-480b-0e10503eedf5)が付属しています。 

購入は、[Microsoft Store の使用条件と販売](https://www.microsoft.com/storedocs/terms-of-sale?rtc=1)の対象です。 

HoloLens 2 を購入すると、[ソフトウェア使用許諾契約書](https://www.microsoft.com/Useterms/)に同意したものとします。

## <a name="package-dimensions"></a>パッケージのサイズ

|      測定値               |      ユニットのメトリック     |      ヤード ポンド単位     |
|--------------------------------|-----------------------|-------------------------|
|     ユニットの長さ                |     378.97 mm          |     14.920 インチ       |
|     ユニットの幅                 |     247.90 mm          |     9.760 インチ        |
|     ユニットの深さ                 |     163.07 mm          |     6.420 インチ        |
|     ユニットの重量                |     2.878 kg           |     6.344 ポンド           |
|     出荷時の外装の長さ    |     446.00 mm          |     17.559 インチ       |
|     出荷時の外装の幅     |     257.99 mm          |     10.157 インチ       |
|     出荷時の外装の深さ     |     172.01 mm          |     6.772 インチ        |
|     出荷時の外装の重量    |     3.284 kg           |     7.240 ポンド           |

> [!NOTE]
> - ユニット: 黒い小売スタイル ボックスの HoloLens 2 が販売されています。
> - 出荷時の外装: ユニットを包んで保護する出荷用のパッケージ。

## <a name="finding-the-serial-number"></a>シリアル番号を見つける

HoloLens 2 デバイスのシリアル番号はバイザーの下に印刷されています。

1. デバイスのバイザーを持ち上げます。
1. Brow パッドの近くを見てください。
1. ヒンジの近くにあるシリアル番号を見つけることができます。

<img src="images/serial-number-diagram-hl2.png" alt=Null width="625" height="903" />

シリアル番号は、接続されている PC でも確認できます。

1. デバイスを接続します
1. ファイル エクスプローラーで **[PC]** に移動します
1. HoloLens デバイスを右クリックして、**[プロパティ]** を選択します
1. これにより、以下のスクリーンショットに示すように、デバイスのシリアル番号が表示されます。

<img src="images/ResetRecovery2.png" alt=null line width="400" height="600" />

## <a name="next-step"></a>次の手順

> [!div class="nextstepaction"]
> [HoloLens 2 のセットアップと起動](hololens2-setup.md)
