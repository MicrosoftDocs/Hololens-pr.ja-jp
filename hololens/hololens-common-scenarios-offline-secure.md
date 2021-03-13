---
title: 一般的なシナリオ – オフラインの安全な HoloLens 2
description: HoloLens デバイスのプロビジョニングを使用してオフラインでセキュリティで保護された展開とアプリの展開シナリオをセットアップする方法について説明します。
keywords: HoloLens, 管理, オフライン, オフライン セキュア
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
ms.sourcegitcommit: 04b7e789fe69615a60571b769e13a01a9d7aee70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2021
ms.locfileid: "11407590"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>一般的なシナリオ – オフラインの安全な HoloLens 2

## <a name="overview"></a>概要

このガイドでは、安全な環境で使用するために HoloLens 2 をロックダウンするプロビジョニング パッケージのサンプルを適用するためのガイダンスを以下の制限で提供します。

-   WiFi を無効にします。
-   BlueTooth を無効にします。
-   マイクを無効にします。
-   プロビジョニング パッケージの追加または削除を防止します。
-   ユーザーは、上記の制限されたコンポーネントを有効にできます。

## <a name="prepare"></a>準備

Windows 10 PC セットアップ
1. [最新の HoloLens 2 OS ファイルを PC](https://aka.ms/hololens2download) に直接ダウンロードします。 
   1. この構成のサポートは、ビルド 19041.1117 以上に含まれています。
1. [Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8)から PC に Advanced Recovery Companion(ARC) ツールをダウンロード/インストールする
1. Microsoft Store から PC に [最新の Windows 構成デザイナー (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) ツールをダウンロード/インストールします。
1. [プロジェクト ファイルOfflineSecureHL2_Sampleフォルダーをダウンロードして](https://aka.ms/HoloLensDocs-SecureOfflineSample) 、PPKG をビルドします。
1. [PPKG 展開用にオフラインの Line of Business アプリケーションを準備します](app-deploy-provisioning-package.md)。 


## <a name="configure"></a>構成

セキュリティで保護された構成プロビジョニング パッケージを構築する

1. PC で WCD ツールを起動します。
1. [ **ファイル - ファイルを開>プロジェクト] を選択します**。
  1. 以前に保存したフォルダーの場所に移動しOfflineSecureHL2_Sampleを選択しますOfflineSecureHL2_Sample.icdproj.xml
1. プロジェクトが開き、利用可能なカスタマイズの一覧が表示されます。

   > [!div class="mx-imgBorder"]
   > ![WCD で開いている構成パッケージのスクリーンショット](images/offline-secure-sample-wcd.png)

   このプロビジョニング パッケージで設定された構成:
   
   |     項目                                                |     設定                       |     説明                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     アカウント/ユーザー                                    |     ローカル ユーザー名 & パスワード    |     これらのオフライン デバイスでは、1 つのユーザー名とパスワードをデバイスのすべてのユーザーが設定して共有する必要があります。          |
   |     First Experience / HoloLens / SkipCalibration       |     True                          |     初期デバイスのセットアップ時にのみ調整をスキップする                                                                             |
   |     First Experience / HoloLens / SkipTraining          |     True                          |     デバイスの初期セットアップ中にデバイストレーニングをスキップする                                                                              |
   |     First Experience / HoloLens / WiFi                  |     True                          |     デバイスの初期Wi-Fi時に設定をスキップする                                                                                 |
   |     ポリシー/接続/AllowBluetooth                |     いいえ                            |     無効にするBluetooth                                                                                                             |
   |     ポリシー/エクスペリエンス/AllowCortana                    |     いいえ                            |     Cortana を無効にします (マイクが無効になっているので、潜在的な問題を排除するため)                                          |
   |     Policies/MixedReality/MicrophoneDisabled            |     はい                           |     マイクを無効にする                                                                                                            |
   |     ポリシー/プライバシー/LetAppsAccessLocation              |     強制的に拒否する                    |     アプリが位置情報データにアクセスしようとするのを防ぐ (位置情報の追跡が無効になっているので、潜在的な問題を排除するため)    |
   |     ポリシー/プライバシー/LetAppsAccessMicrophone            |     強制的に拒否する                    |     アプリがマイクにアクセスしようとするのを防ぐ (マイクが無効になっているので、潜在的な問題を排除するため)           |
   |     ポリシー/セキュリティ/AllowAddProvisioningPackage       |     いいえ                            |     ロックダウン ポリシーを上書きしようとする可能性があるプロビジョニング パッケージを追加するユーザーを防止します。                         |
   |     Policies/Security/AllowRemoveProvisioningPackage    |     いいえ                            |     このロックダウンプロビジョニング パッケージを削除するユーザーを防止します。                                                           |
   |     ポリシー/システム/AllowLocation                       |     いいえ                            |     デバイスが位置情報の追跡を試みるのを防ぐ。                                                                        |
   |     ポリシー/WiFi/AllowWiFi                             |     いいえ                            |     無効にするWi-Fi                                                                                                                 |

1. [ランタイム設定] で、[ **アカウント/ ユーザー/ UserName: Holo / Password ] を選択します**。

   パスワードをメモし、必要に応じてリセットします。

1. UniversalAppInstall / UserContextApp に移動し、これらのデバイスに展開する [LOB](app-deploy-provisioning-package.md) アプリを構成します。

   > [!div class="mx-imgBorder"]
   > ![WCD でアプリを追加する場所のスクリーンショット。](images/offline-secure-sample-wcd-usercontextapp2.png)

1. 完了したら、[エクスポート] ボタンを選択し、プロビジョニング パッケージが作成されるまですべてのプロンプトに従います。

   > [!div class="mx-imgBorder"]
   > ![WCD のこのパッケージの [エクスポート] ボタンのスクリーンショット。](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>展開

1. HL2 を USB ケーブルで Windows 10 PC に接続します。
1. ARC ツールを起動し **、[HoloLens 2] を選択します。**

   ![HoloLens 2 クリーン 再フラッシュの初期画面](images/ARC2.png)

1. 次の画面で、[手動パッケージの **選択] を選択します**。

   ![HoloLens 2 ARC 情報画面](images/arc_device_info.png)

1. 以前にダウンロードした .ffu ファイルに移動し、[開く] を **選択します**。
1. [警告] ページで、[続行] を **選択します**。

   ![HoloLens 2 ARC 警告画面](images/arc_warning.png)

1. ARC ツールが HoloLens 2 OS のインストールを完了するのを待ちます。
1. デバイスがインストールを完了し、バックアップを起動したら、PC からエクスプローラーに移動し、以前に保存した PPKG ファイルをデバイス フォルダーにコピーします。

   > [!div class="mx-imgBorder"]
   > ![[エクスプローラー] ウィンドウの PC 上の PPKG ファイル。](images/offline-secure-file-explorer.png)

1. HoloLens 2 で、次のボタン コンボを押してプロビジョニング パッケージ: **[音量** を下げ] と [ **電源** ボタン] を同時に実行します。
1. プロビジョニング パッケージの適用を求めるメッセージが表示されます。[確認] を **選択します。**
1. プロビジョニング パッケージが完了したら **、[OK] を選択します**。
1. その後、共有ローカル アカウントとパスワードを使用してデバイスにサインインするように求めるメッセージが表示されます。

## <a name="maintain"></a>保守

この構成では、上記のプロセスを再起動し、ARC ツールを使用してデバイスを再フラッシュし、新しい PPKG を適用して OS やアプリケーションを更新することを推奨します。
