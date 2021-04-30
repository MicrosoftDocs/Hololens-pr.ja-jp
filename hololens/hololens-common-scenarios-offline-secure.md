---
title: 一般的なシナリオ– Offline Secure HoloLens 2
description: HoloLens デバイスのプロビジョニングを使用して、オフラインのセキュリティで保護された展開とアプリの展開シナリオをセットアップする方法について説明します。
keywords: HoloLens、管理、オフライン、オフラインのセキュリティ
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 7eb084d3de222581fd2b97eaa1c1e2812310810c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309125"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>一般的なシナリオ– Offline Secure HoloLens 2

## <a name="overview"></a>概要

このガイドでは、セキュリティで保護された環境で使用するために HoloLens 2 をロックダウンするサンプルプロビジョニングパッケージを適用するためのガイダンスを提供します。次の制限があります。

-   WiFi を無効にします。
-   BlueTooth を無効にします。
-   マイクを無効にします。
-   プロビジョニングパッケージを追加または削除できないようにします。
-   上記の制限されたコンポーネントをユーザーが有効にすることはできません。

## <a name="prepare"></a>準備

Windows 10 PC セットアップ
1. [最新の HoloLens 2 OS ファイル](https://aka.ms/hololens2download) を PC に直接ダウンロードします。 
   1. この構成のサポートは、ビルド19041.1117 以降に含まれています。
1. [Microsoft Store から](https://www.microsoft.com/store/productId/9P74Z35SFRS8)PC に高度な回復コンパニオン (ARC) ツールをダウンロードしてインストールする
1. Microsoft Store から PC に最新の [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) ツールをダウンロードしてインストールします。
1. [OfflineSecureHL2_Sample フォルダーとプロジェクトファイルをダウンロード](https://aka.ms/HoloLensDocs-SecureOfflineSample) して、ppkg をビルドします。
1. [PPKG 展開用のオフライン基幹業務アプリケーションを](app-deploy-provisioning-package.md)準備します。 


## <a name="configure"></a>構成

セキュリティで保護された構成プロビジョニングパッケージを構築する

1. PC で WCD ツールを起動します。
1. [ **ファイル] > [プロジェクトを開く**] を選択します。
  1. 以前に保存した OfflineSecureHL2_Sample フォルダーの場所に移動し、次のように選択し OfflineSecureHL2_Sample.icdproj.xml
1. プロジェクトが開き、利用可能なカスタマイズの一覧が表示されます。

   > [!div class="mx-imgBorder"]
   > ![WCD で開かれている構成パッケージのスクリーンショット](images/offline-secure-sample-wcd.png)

   このプロビジョニングパッケージで設定される構成:
   
   |     アイテム                                                |     設定                       |     説明                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     アカウント/ユーザー                                    |     ローカルユーザー名 & パスワード    |     これらのオフラインデバイスでは、デバイスのすべてのユーザーが1つのユーザー名とパスワードを設定して共有する必要があります。          |
   |     最初のエクスペリエンス/HoloLens/SkipCalibration       |     正しい                          |     初期デバイスのセットアップ中のみ調整をスキップします                                                                             |
   |     最初の経験/HoloLens/SkipTraining          |     正しい                          |     初期デバイスのセットアップ中にデバイストレーニングをスキップします                                                                              |
   |     最初のエクスペリエンス/HoloLens/WiFi                  |     正しい                          |     初期デバイスのセットアップ中に Wi-Fi 構成をスキップします                                                                                 |
   |     ポリシー/接続/AllowBluetooth                |     いいえ                            |     Bluetooth を無効にします                                                                                                             |
   |     ポリシー/エクスペリエンス/AllowCortana                    |     いいえ                            |     Cortana を無効にします (マイクが無効になっているために発生する可能性のある問題を除去します)                                          |
   |     Policies/MixedReality/マイクロ電話の無効化            |     はい                           |     マイクを無効にする                                                                                                            |
   |     ポリシー/プライバシー/保管場所              |     強制拒否                    |     アプリが場所データにアクセスできないようにします (場所の追跡が無効になっているために発生する可能性のある問題を回避するため)    |
   |     ポリシー/プライバシー/お客様            |     強制拒否                    |     アプリがマイクにアクセスできないようにします (マイクが無効になったために発生する可能性のある問題を回避するため)           |
   |     Policies/Security/Allowaddプロビジョニングパッケージ       |     いいえ                            |     ロックダウンされたポリシーを上書きしようとする可能性があるプロビジョニングパッケージを誰も追加できないようにします。                         |
   |     Policies/Security/Allowremoveプロビジョニングパッケージ    |     いいえ                            |     このロックダウンされたプロビジョニングパッケージをすべてのユーザーが削除できないようにします。                                                           |
   |     ポリシー/システム/AllowLocation                       |     いいえ                            |     デバイスが場所データを追跡しないようにします。                                                                        |
   |     ポリシー/WiFi/AllowWiFi                             |     いいえ                            |     無効化 Wi-Fi                                                                                                                 |

1. [ランタイム設定] で、[ **Accounts/Users/UserName: Holo/Password**] を選択します。

   必要に応じて、パスワードとリセットを書き留めておきます。

1. UniversalAppInstall/UserContextApp に移動し、これらのデバイスにデプロイする [LOB アプリを構成](app-deploy-provisioning-package.md) します。

   > [!div class="mx-imgBorder"]
   > ![WCD でアプリを追加する場所のスクリーンショット。](images/offline-secure-sample-wcd-usercontextapp2.png)

1. 完了したら、[エクスポート] ボタンを選択し、プロビジョニングパッケージが作成されるまですべてのプロンプトに従います。

   > [!div class="mx-imgBorder"]
   > ![WCD 内のこのパッケージの [エクスポート] ボタンのスクリーンショット。](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>配置

1. USB ケーブル経由で HL2 を Windows 10 PC に接続します。
1. ARC ツールを起動し、[ **HoloLens 2** ] を選択します。

   ![HoloLens 2 clean 更新初期画面](images/ARC2.png)

1. 次の画面で、[ **パッケージの手動選択**] を選択します。

   ![HoloLens 2 弧情報画面](images/arc_device_info.png)

1. 以前にダウンロードした ffu ファイルに移動し、[ **開く**] を選択します。
1. [警告] ページで [ **続行**] を選択します。

   ![HoloLens 2 ARC 警告画面](images/arc_warning.png)

1. ARC ツールが HoloLens 2 OS のインストールを完了するのを待ちます。
1. デバイスのインストールが完了し、再起動されたら、PC からエクスプローラーに移動し、以前に保存した PPKG ファイルをデバイスフォルダーにコピーします。

   > [!div class="mx-imgBorder"]
   > ![ファイルエクスプローラーウィンドウで、PC 上の PPKG ファイルを表示します。](images/offline-secure-file-explorer.png)

1. HoloLens 2 で、次のボタンを押してプロビジョニングパッケージを実行します。 [ **ボリュームダウン** ] と [ **電源] ボタン** を同時にタップします。
1. プロビジョニングパッケージを適用するかどうかを確認するメッセージが表示されたら、[**確認**] を選択します。
1. プロビジョニングパッケージが完了したら、[ **OK]** を選択します。
1. 次に、共有ローカルアカウントとパスワードを使用してデバイスにサインインするように求められます。

## <a name="maintain"></a>管理

この構成では、上記のプロセスを再起動し、デバイスを ARC ツールで更新し、新しい PPKG を適用して OS やアプリケーションに更新を加えることをお勧めします。
