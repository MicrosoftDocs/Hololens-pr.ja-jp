---
title: 一般的なシナリオ – オフラインセキュア HoloLens 2
description: HoloLens デバイスのプロビジョニングを使用して、オフラインでセキュリティ保護された展開とアプリの展開シナリオをセットアップする方法について説明します。
keywords: HoloLens, 管理, オフライン, オフラインセキュア
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
ms.openlocfilehash: 03003995f1e63708652955e6217e506d53555c1b
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283418"
---
# 一般的なシナリオ – オフラインセキュア HoloLens 2

## 概要

このガイドでは、次の制限がある安全な環境で使用するために HoloLens 2 をロックダウンするプロビジョニング パッケージのサンプルを適用するためのガイダンスを提供します。
-   WiFi を無効にします。
-   BlueTooth を無効にします。
-   マイクを無効にします。
-   プロビジョニング パッケージの追加または削除を防止します。
-   上記の制限付きコンポーネントを有効にできるユーザーはありません。

## 準備

Windows 10 PC のセットアップ
1. [最新の HoloLens 2 OS](https://aka.ms/hololens2download) ファイルを PC に直接ダウンロードします。 
   1. この構成のサポートは、ビルド 19041.1117 以上に含まれています。
1. [Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8)から PC に Advanced Recovery Companion(ARC) ツールをダウンロード/インストールする
1. Microsoft Store から PC に [最新の Windows 構成デザイナー (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) ツールをダウンロード/インストールします。
1. [PPKG をOfflineSecureHL2_Sampleプロジェクト ファイルを含む](https://aka.ms/HoloLensDocs-SecureOfflineSample) フォルダーをダウンロードします。
1. [PPKG 展開用にオフラインの Line of Business アプリケーションを準備します](app-deploy-provisioning-package.md)。 


## 構成

セキュリティで保護された構成プロビジョニング パッケージをビルドする

1. PC で WCD ツールを起動します。
1. Select **File -> Open project**.
  1. 以前に保存したフォルダーの場所にOfflineSecureHL2_Sampleし、次のオプションを選択OfflineSecureHL2_Sample.icdproj.xml
1. プロジェクトが開き、使用可能なカスタマイズの一覧が表示されます。 

   > [!div class="mx-imgBorder"]
   > ![WCD で開いている構成パッケージのスクリーンショット](images/offline-secure-sample-wcd.png)

このプロビジョニング パッケージで設定された構成:

|     項目                                                |     設定                       |     説明                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     アカウント/ユーザー                                    |     ローカル ユーザー名& パスワード    |     これらのオフライン デバイスでは、デバイスのすべてのユーザーが 1 つのユーザー名とパスワードを設定して共有する必要があります。          |
|     First Experience / HoloLens / SkipCalibration       |     True                          |     初期デバイスのセットアップ時にのみ調整をスキップします                                                                             |
|     First Experience / HoloLens / SkipTraining          |     True                          |     デバイスの初期セットアップ中にデバイストレーニングをスキップします                                                                              |
|     First Experience / HoloLens / WiFi                  |     True                          |     デバイスの初期Wi-Fi構成をスキップします。                                                                                 |
|     Policies/Connectivity/AllowBluetooth                |     なし                            |     無効Bluetooth                                                                                                             |
|     Policies/Experience/AllowCortana                    |     なし                            |     Cortana を無効にします (マイクが無効になっているので潜在的な問題を排除するため)                                          |
|     Policies/MixedReality/MicrophoneDisabled            |     あり                           |     マイクを無効にする                                                                                                            |
|     Policies/Privacy/LetAppsAccessLocation              |     強制的に拒否する                    |     アプリが位置情報データにアクセスしようとするのを防ぐ (位置情報の追跡が無効になっているので潜在的な問題を排除するため)    |
|     Policies/Privacy/LetAppsAccessMicrophone            |     強制的に拒否する                    |     アプリがマイクにアクセスしようとするのを防ぐ (マイクが無効になっているので潜在的な問題を排除するため)           |
|     Policies/Security/AllowAddProvisioningPackage       |     なし                            |     ロックダウンされたポリシーを上書きしようとする可能性があるプロビジョニング パッケージをだれも追加しません。                         |
|     Policies/Security/AllowRemoveProvisioningPackage    |     なし                            |     ロックダウンされたこのプロビジョニング パッケージを削除するユーザーを防止します。                                                           |
|     Policies/System/AllowLocation                       |     なし                            |     デバイスが位置情報データの追跡を試みない。                                                                        |
|     Policies/WiFi/AllowWiFi                             |     なし                            |     無効Wi-Fi                                                                                                                 |

4. [実行時の設定] で、[ **アカウント/ ユーザー/ ユーザー名: Holo / パスワード] を選択します。** 
    - パスワードをメモし、必要に応じてリセットします。
5. UniversalAppInstall / UserContextApp に移動し、これらのデバイスに展開する [LOB](app-deploy-provisioning-package.md) アプリを構成します。

   > [!div class="mx-imgBorder"]
   > ![WCD でアプリを追加する場所のスクリーンショット。](images/offline-secure-sample-wcd-usercontextapp.png)

6. 完了したら、[エクスポート] ボタンを選択し、プロビジョニング パッケージが作成されるまですべてのプロンプトに従います。

   > [!div class="mx-imgBorder"]
   > ![WCD のこのパッケージの [エクスポート] ボタンのスクリーンショット。](images/offline-secure-sample-wcd-export.png)


## 展開

1. HL2 を USB ケーブルで Windows 10 PC に接続します。
1. ARC ツールを起動して **HoloLens 2 を選択する**

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. On the next screen select **Manual package selection**.
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. 以前にダウンロードした .ffu ファイルに移動し、[開く] を選択 **します**。
1. [警告] ページで、[続行] を **選択します**。

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. ARC ツールが HoloLens 2 OS のインストールを完了するまで待ちます。
1. デバイスがインストールを完了して起動し、バックアップを起動したら、PC からエクスプローラーに移動し、以前に保存した PPKG ファイルをデバイス フォルダーにコピーします。

   > [!div class="mx-imgBorder"]
   > ![エクスプローラー ウィンドウの PC 上の PPKG ファイル。](images/offline-secure-file-explorer.png)

1. HoloLens 2 で、次のボタン コンボを押してプロビジョニング パッケージを**** 実行します。[音量を下げ] と [**電源**ボタン] を同時にタップします。
1. プロビジョニング パッケージを適用するように求めるメッセージが表示され、[確認] を選択 **します。**
1. プロビジョニング パッケージが完了したら **、[OK] を選択します**。
1. その後、共有ローカル アカウントとパスワードを使用してデバイスにサインインするように求めるメッセージが表示されます。

## 保守

この構成では、上記のプロセスを再起動し、ARC ツールでデバイスを再フラッシュし、新しい PPKG を適用して OS やアプリケーションを更新することを推奨します。 

