---
title: 一般的なシナリオ–オフラインで安全な HoloLens 2
description: プロビジョニングによるオフラインでの安全な展開とアプリの展開。
keywords: HoloLens、管理、オフライン、オフラインセキュリティ
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
ms.openlocfilehash: d53f9ce19b020a866770b756dde6ab97b8331362
ms.sourcegitcommit: e6885d03c980b33dd0bab5c418cbd1892d5ff123
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "11080511"
---
# 一般的なシナリオ–オフラインで安全な HoloLens 2

## 概要
このガイドでは、セキュリティ保護された環境で使用するために HoloLens 2 をロックするサンプルプロビジョニングパッケージの適用に関するガイダンスを、次の制限に従って説明します。
-   WiFi を無効にします。
-   BlueTooth を無効にします。
-   マイクを無効にします。
-   プロビジョニングパッケージを追加または削除できないようにします。
-   どのユーザーも、上記の制限されたコンポーネントを有効にすることはできません。

## 準備 
Windows 10 PC セットアップ
1. [最新の HoloLens 2 OS ファイル](https://aka.ms/hololens2download) を PC に直接ダウンロードします。 
   1. この構成のサポートは、ビルド19041.1117 以降に含まれています。
1. [Microsoft Store から](https://www.microsoft.com/store/productId/9P74Z35SFRS8)PC に高度な回復コンパニオン (ARC) ツールをダウンロードしてインストールする
1. Microsoft Store から PC に最新の [Windows 構成デザイナー (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) ツールをダウンロードしてインストールします。
1. [プロジェクトファイルを含む OfflineSecureHL2_Sample フォルダーをダウンロード](https://aka.ms/HoloLensDocs-SecureOfflineSample) して、ppkg を構築します。
1. [PPKG 展開用のオフラインのビジネスアプリケーションを](app-deploy-provisioning-package.md)準備します。 


## 構成
セキュリティで保護された構成プロビジョニングパッケージを作成する

1. PC で WCD ツールを起動します。
1. [ファイル] を選択し **、[プロジェクト > 開き**ます。
  1. 以前に保存した OfflineSecureHL2_Sample フォルダーの場所に移動し、次のように選択します。 OfflineSecureHL2_Sample.icdproj.xml
1. プロジェクトが開き、利用可能なカスタマイズの一覧が表示されます。 

   > [!div class="mx-imgBorder"]
   > ![WCD で開いた構成パッケージのスクリーンショット](images/offline-secure-sample-wcd.png)

このプロビジョニングパッケージで設定される構成:

|     項目                                                |     設定                       |     説明                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     アカウント/ユーザー                                    |     ローカルユーザー名 & パスワード    |     これらのオフラインデバイスでは、デバイスのすべてのユーザーが1つのユーザー名とパスワードを設定して共有する必要があります。          |
|     First Experience/HoloLens/SkipCalibration 調整       |     True                          |     デバイスの初期セットアップ時のみ、調整をスキップする                                                                             |
|     First Experience/HoloLens/SkipTraining          |     True                          |     初期デバイスのセットアップ中にデバイスのトレーニングをスキップします                                                                              |
|     第1のエクスペリエンス/HoloLens/WiFi                  |     True                          |     初期デバイスのセットアップ中に Wi-fi 構成をスキップします                                                                                 |
|     ポリシー/接続/AllowBluetooth                |     なし                            |     Bluetooth を無効にします                                                                                                             |
|     ポリシー/エクスペリエンス/AllowCortana                    |     なし                            |     Cortana を無効にします (マイクを無効にした後に発生する可能性のある問題を除去します)。                                          |
|     Policies/MixedReality/マイクロ電話が無効になっています            |     あり                           |     マイクを無効にします                                                                                                            |
|     ポリシー/プライバシー/保管場所              |     強制拒否                    |     アプリが位置情報にアクセスしようとしないようにします (位置情報の追跡が無効になった後に発生する可能性のある問題を除去します)。    |
|     ポリシー/プライバシー/アレイのアクセスマイク            |     強制拒否                    |     アプリがマイクにアクセスしようとしないようにします (マイクが無効になった後に発生する可能性のある問題を除去します)。           |
|     ポリシー/セキュリティ/Allowaddのパッケージ       |     なし                            |     ロックダウンポリシーを上書きしようとしている可能性があるプロビジョニングパッケージを、他の人が追加できないようにします。                         |
|     ポリシー/セキュリティ/Allowremoveプロビジョニングパッケージ    |     なし                            |     ロックダウンされたプロビジョニングパッケージを他の人が削除できないようにします。                                                           |
|     Policies/System/AllowLocation                       |     なし                            |     デバイスが位置情報データを追跡しないようにします。                                                                        |
|     ポリシー/WiFi/AllowWiFi                             |     なし                            |     Wi-fi を無効にします                                                                                                                 |

4. [ランタイムの設定] で、[**アカウント/ユーザー/ユーザー名: Holo/Password** ] を選びます。 
    - 必要に応じて、パスワードとリセットを書き留めます。
5. UniversalAppInstall/UserContextApp に移動して、これらのデバイスに展開する [LOB アプリを構成](app-deploy-provisioning-package.md) します。

   > [!div class="mx-imgBorder"]
   > ![WCD にアプリを追加する場所のスクリーンショット。](images/offline-secure-sample-wcd-usercontextapp.png)

6. 完了したら、[エクスポート] ボタンを選択し、プロビジョニングパッケージが作成されるまで、すべてのプロンプトに従います。

   > [!div class="mx-imgBorder"]
   > ![WCD のこのパッケージの [エクスポート] ボタンのスクリーンショット。](images/offline-secure-sample-wcd-export.png)


## 展開
1. USB ケーブルを使って、HL2 を Windows 10 PC に接続します。
1. ARC ツールを起動し、[ **HoloLens 2** ] を選択します。

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. 次の画面で、[ **パッケージの手動選択**] を選択します。
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. 前にダウンロードした ffu ファイルに移動して、[ **開く**] を選択します。
1. 警告ページで [ **Continue**] を選びます。

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. [ARC] ツールが HoloLens 2 OS インストールを完了するまで待ちます。
1. デバイスがインストールを完了して起動したら、PC からエクスプローラーに移動し、以前に保存した PPKG ファイルをデバイスフォルダーにコピーします。

   > [!div class="mx-imgBorder"]
   > ![ファイルエクスプローラーウィンドウの PC の PPKG ファイル。](images/offline-secure-file-explorer.png)

1. HoloLens 2 では、次のボタンのコンボを押してプロビジョニングパッケージを実行します。 [ **音量を下げる** ] と [ **電源ボタン]** を同時にタップします。
1. プロビジョニングパッケージを適用するかどうかを確認するメッセージが表示されたら、[**確認**] を選択します。
1. プロビジョニングパッケージが完了したら、[ **OK]** を選択します。
1. 次に、共有のローカルアカウントとパスワードを使用して、デバイスにサインインするように求められます。

## 保守
この構成では、上の手順を再起動して、ARC ツールを使ってデバイスを reflash し、新しい PPKG を適用して OS やアプリケーションの更新を行うことをお勧めします。 

