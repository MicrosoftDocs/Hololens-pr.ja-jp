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
ms.date: 4/21/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: e00c043f7de1142e4d2e08e41ff0d91123d4a98b
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828612"
---
# Microsoft HoloLens の Insider Preview

HoloLens 用の最新の Insider Preview ビルドへようこそ!  簡単に使い始めて、HoloLens の次の主要なオペレーティング システムの更新プログラムに対する貴重なフィードバックをご提供いただけます。

## Insider ビルドの受信の開始

HoloLens 2 デバイスで、**[設定]** -> **[更新とセキュリティ]** -> **[Windows Insider Program]** の順に移動し、**[開始する]** を選択します。 Windows Insider として登録するために使用したアカウントをリンクします。

次に、**[Windows のアクティブな開発]** を選択し、**[ファスト]** または **[スロー]** ビルドを受信するかどうかを選択し、プログラム使用条件を確認します。

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

[Windows Holographic May 2020 Update](hololens-release-notes.md) のリリース以降、すべてのリリース プレビュー機能が一般的に利用可能になりました。 [HoloLens を更新して](hololens-update-hololens.md)、最新の機能をすべて入手してください。  

Windows Insider ビルドにリリースするときに、このページを新しい機能で再度更新します。 

### FFU のダウンロードとフラッシュの手順
フライト署名のある FFU でテストするには、フライト署名のある FFU をフラッシュする前にデバイスのフライト ロックを解除する必要があります。
1. PC で次の操作を実行します。
    1. [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) から PC に FFU をダウンロードします。
    1. Microsoft Store ([https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)) から ARC (Advanced Recovery Companion) をインストールします。 
1. HoloLens - フライト ロックを解除します。**[設定]** > **[更新とセキュリティ]** > **[Windows Insider Program]** の順に開き、サインアップして、デバイスを再起動します
1. フラッシュ FFU - ARC を使用してフライト署名された FFU をフラッシュできるようになりました 
