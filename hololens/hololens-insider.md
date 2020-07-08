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
ms.date: 6/29/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: cd2b055679f5e1a9a529ad4947773e412211f9c4
ms.sourcegitcommit: 2b1518675b9962518e08b13c12b43b6d9827fe17
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "10858011"
---
# Microsoft HoloLens の Insider Preview

HoloLens 用の最新の Insider Preview ビルドへようこそ!  簡単に使い始めて、HoloLens の次の主要なオペレーティング システムの更新プログラムに対する貴重なフィードバックをご提供いただけます。

Windows insider がチャネルに移動するようになりました。 **ファスト**リングは**Dev チャネル**になります。**スロー**リングは**ベータチャネル**になり、 **release preview** ring は**リリースプレビューチャネル**になります。 マッピングの外観は次のようになります。

![Windows Insider チャンネル explination](images/WindowsInsiderChannels.png)

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
1. [製品版ビルド番号については、リリース ノートをご覧ください。](hololens-release-notes.md)

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

ここに記載されている機能が、insider 以外のビルドでは表示されていない場合は、[リリースノート](hololens-release-notes.md)をお読みになっていることを確認してください。すべての機能を利用できるようになっていることを確認してください。 [HoloLens を更新して](hololens-update-hololens.md)、最新の機能をすべて入手してください。  

このページは、Windows Insider ビルドにリリースするときに、新しい機能を使ってもう一度更新します。 

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
1.  この問題を調査していますが、メモリ負荷が高い状態で実行するとアイトラッカードライバーのホストプロセスがクラッシュする可能性があります。 アイトラッキングドライバーのホストプロセスは、自動的に回復する必要があります。

## FFU のダウンロードとフラッシュの手順
フライト署名のある FFU でテストするには、フライト署名のある FFU をフラッシュする前にデバイスのフライト ロックを解除する必要があります。
1. PC で次の操作を実行します。
    1. [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) から PC に FFU をダウンロードします。
    1. Microsoft Store ([https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)) から ARC (Advanced Recovery Companion) をインストールします。 
1. HoloLens - フライト ロックを解除します。**[設定]** > **[更新とセキュリティ]** > **[Windows Insider Program]** の順に開き、サインアップして、デバイスを再起動します
1. フラッシュ FFU - ARC を使用してフライト署名された FFU をフラッシュできるようになりました 
