---
title: 一般的なシナリオ – オフライン セキュリティHoloLens 2
description: HoloLens デバイスのプロビジョニングを使用して、オフラインでセキュリティで保護された展開とアプリの展開シナリオを設定する方法について説明します。
keywords: HoloLens, 管理, オフライン, オフライン セキュリティで保護
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
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397883"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>一般的なシナリオ – オフライン セキュリティHoloLens 2

## <a name="overview"></a>概要

このガイドでは、セキュリティで保護された環境で使用するためにHoloLens 2プロビジョニング パッケージのサンプルを適用するためのガイダンスを提供します。これには次の制限があります。

-   WiFi を無効にします。
-   BlueTooth を無効にします。
-   マイクを無効にします。
-   プロビジョニング パッケージの追加または削除を防止します。
-   上記の制限付きコンポーネントを有効にできるユーザーはありません。

[![オフライン でセキュリティで保護されたシナリオ ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>準備

Windows 10 PC のセットアップ
1. [最新の HOLOLENS 2 OS ファイルを PC](https://aka.ms/hololens2download) に直接ダウンロードします。 
   1. この構成のサポートは、ビルド 19041.1117 以上に含まれています。
1. コンピューターから PC への Advanced Recovery Companion(ARC) [Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) ダウンロード/インストールする
1. 最新の Windows [構成デザイナー (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) ツールをダウンロードして、PC Microsoft Storeインストールします。
1. [プロジェクト ファイルOfflineSecureHL2_Sampleフォルダーをダウンロードして](https://aka.ms/HoloLensDocs-SecureOfflineSample) 、PPKG をビルドします。
1. オフラインの [Line of Business アプリケーションを PPKG デプロイ用に準備します](app-deploy-provisioning-package.md)。 


## <a name="configure"></a>構成

セキュリティで保護された構成プロビジョニング パッケージをビルドする

1. PC で WCD ツールを起動します。
1. [ **ファイル] > [プロジェクトを開く**] を選択します。
  1. 以前に保存した OfflineSecureHL2_Sample フォルダーの場所に移動し、次のように選択し OfflineSecureHL2_Sample.icdproj.xml
1. プロジェクトが開き、利用可能なカスタマイズの一覧が表示されます。

   > [!div class="mx-imgBorder"]
   > ![WCD で開かれている構成パッケージのスクリーンショット](images/offline-secure-sample-wcd.png)

   このプロビジョニングパッケージで設定される構成:
   
   |     Item                                                |     設定                       |     Description                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     アカウント/ユーザー                                    |     ローカルユーザー名 & パスワード    |     これらのオフラインデバイスでは、デバイスのすべてのユーザーが1つのユーザー名とパスワードを設定して共有する必要があります。          |
   |     最初のエクスペリエンス/HoloLens/SkipCalibration       |     ○                          |     初期デバイスのセットアップ中のみ調整をスキップします                                                                             |
   |     最初の経験/HoloLens/SkipTraining          |     ○                          |     初期デバイスのセットアップ中にデバイストレーニングをスキップします                                                                              |
   |     最初のエクスペリエンス/HoloLens/WiFi                  |     ○                          |     初期デバイスのセットアップ中に Wi-Fi 構成をスキップします                                                                                 |
   |     ポリシー/接続/AllowBluetooth                |     No                            |     Bluetooth を無効にします                                                                                                             |
   |     ポリシー/エクスペリエンス/AllowCortana                    |     No                            |     Cortana を無効にします (マイクが無効になっているために発生する可能性のある問題を除去します)                                          |
   |     Policies/MixedReality/マイクロ電話の無効化            |     Yes                           |     マイクを無効にする                                                                                                            |
   |     Policies/Privacy/LetAppsAccessLocation              |     強制的に拒否する                    |     アプリが位置情報データへのアクセスを試みるのを防ぐ (位置情報の追跡が無効になっているので、潜在的な問題を排除するため)    |
   |     Policies/Privacy/LetAppsAccessMicrophone            |     強制的に拒否する                    |     アプリがマイクへのアクセスを試みるのを防ぐ (マイクが無効になっているので、潜在的な問題を排除するため)           |
   |     Policies/Security/AllowAddProvisioningPackage       |     No                            |     ロックダウンされたポリシーをオーバーライドしようとする可能性があるプロビジョニング パッケージを追加するユーザーを防ぐ。                         |
   |     Policies/Security/AllowRemoveProvisioningPackage    |     No                            |     このロックダウンされたプロビジョニング パッケージを削除するユーザーを防止します。                                                           |
   |     Policies/System/AllowLocation                       |     No                            |     デバイスが位置情報データの追跡を試みるのを防ぐ。                                                                        |
   |     Policies/WiFi/AllowWiFi                             |     No                            |     を無効Wi-Fi                                                                                                                 |

1. [ランタイム設定] で、[ **アカウント/ ユーザー / ユーザー名: Holo / パスワード ] を選択します**。

   パスワードをメモし、必要に応じてリセットします。

1. UniversalAppInstall / UserContextApp に移動し、これらのデバイスに展開する [LOB](app-deploy-provisioning-package.md) アプリを構成します。

   > [!div class="mx-imgBorder"]
   > ![WCD でアプリを追加する場所のスクリーンショット。](images/offline-secure-sample-wcd-usercontextapp2.png)

1. 完了したら、[エクスポート] ボタンを選択し、プロビジョニング パッケージが作成されるまですべてのプロンプトに従います。

   > [!div class="mx-imgBorder"]
   > ![WCD のこのパッケージの [エクスポート] ボタンのスクリーンショット。](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>デプロイ

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
