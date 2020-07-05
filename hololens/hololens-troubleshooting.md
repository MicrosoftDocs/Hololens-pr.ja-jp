---
title: HoloLens の問題のトラブルシューティング
description: HoloLens の一般的な問題に対する解決策です。
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: 問題、バグ、トラブルシューティング、修正プログラム、ヘルプ、サポート、HoloLens
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4897d02f4b789c77204d57c0a7750e3c3803d7bb
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829022"
---
# HoloLens の問題のトラブルシューティング

この記事では、いくつかの一般的な HoloLens の問題を解決する方法について説明します。

## HoloLens が応答しない、または起動しない

HoloLens が起動しない場合は、次の操作を行います。

- 電源ボタンの横にある Led が点灯しない場合、または1つの LED がわずかに点滅する場合は、HoloLens の充電が必要になることがあり[ます。](hololens-recovery.md#charging-the-device)
- 電源ボタンを押したときに Led が点灯したが、ディスプレイに何も表示されない場合は、[デバイスのハードリセットを preform](hololens-recovery.md#hard-reset-procedure)します。

HoloLens がフリーズまたは応答しなくなった場合は、次の操作を行います。

- すべての Led がオフになるまで、または15秒間、Led が反応しない場合は、電源ボタンを押して HoloLens をオフにします。 HoloLens を起動するには、もう一度 power ボタンを押します。

以上の手順で問題が解決しない場合は、 [hololens 2 デバイス](hololens-recovery.md)または[hololens (第1世代) デバイス](hololens1-recovery.md)を回復してみてください。

## ホログラムが適切に表示されない

ホログラムが不安定な場合、jumpy されている場合、または適切に表示されない場合は、次の操作を試してください。

- HoloLens の前面にあるデバイスのバイザーとセンサーバーをクリーニングします。
- 室内での光の増加。
- HoloLens でより完全にスキャンされるように、お客様の環境を調査して見ていきましょう。
- お客様のニーズに応じた HoloLens の調整。 [**設定**  >  **システム**  >  **ユーティリティ**] に移動します。 **[調整]** で、**[調整を開く]** を選択します。

## HoloLens がジェスチャに応答しない

を選び、HoloLens がジェスチャを見られるようにします。  ジェスチャのフレームに手を置く-HoloLens で手を見られるようになると、カーソルがドットからリングに変わります。

[Hololens (第1世代)](hololens1-basic-usage.md#use-hololens-with-your-hands)または[hololens 2](hololens2-basic-usage.md#the-hand-tracking-frame)でのジェスチャの使い方については、こちらを参照してください。

環境が暗すぎると、HoloLens で手が見えない場合があるため、十分なライトがあることを確認してください。

お使いのバイザーに指紋や汚れがある場合は、HoloLens に付属のマイクロファイバーのクリーニング布を使って、お使いのバイザーを軽く拭きます。

## HoloLens が音声コマンドに応答しない

Cortana が音声コマンドに応答しない場合は、[Cortana] がオンになっていることを確認します。 [すべてのアプリ] の一覧で、[ **Cortana**メニューノートブックの設定] を選択して  >  **Menu**  >  **Notebook**  >  **Settings**変更を加えます。 発声できる内容の詳細については、「[HoloLens で音声を使う](hololens-cortana.md)」をご覧ください。

## ホログラムを配置できない、または以前に配置したホログラムが表示されない

HoloLens でスペースをマップまたは読み込むことができない場合は、制限モードになり、ホログラムを配置したり、配置したホログラムを表示したりすることはできません。 以下をお試しください。

- お使いの環境に、HoloLens がスペースを表示してマップできる十分なライトがあることを確認してください。
- Wi-fi ネットワークに接続していることを確認します。 Wi-fi に接続していない場合は、HoloLens で既知のスペースを特定して読み込むことはできません。
- 新しいスペースを作成する必要がある場合は、Wi-fi に接続して、HoloLens を再起動します。
- 適切な領域がアクティブであるか、または手動でスペースを読み込むかを確認するには、[**設定**  >  **システム**スペース] に移動し  >  **Spaces**ます。
- 適切な領域が読み込まれても問題が解決しない場合は、領域が破損している可能性があります。 この問題を解決するには、領域を選択し、[**削除**] を選択します。 この領域を削除すると、HoloLens で環境のマッピングが開始され、新しいスペースが作成されます。

## HoloLens で現在のスペースがわからない

HoloLens で自動的に使用されている領域を特定して読み込むことができない場合は、次の点を確認してください。

- Wi-fi に接続していることを確認する
- 会議室に光が十分あることを確認する
- 環境に大きな変更が加えられていないことを確認してください。

また、**設定**システムの領域に移動して、スペースを手動で読み込むか、スペースを管理することもでき  >  **System**  >  **Spaces**ます。

## "ディスク領域が不足しています" というエラーが表示になる

次の操作のいずれか、または複数の操作を行って、記憶域を解放する必要があります。

- 未使用のスペースを削除します。 [**設定**システムスペース] に移動して、不要になったスペースを選択し、[  >  **System**  >  **Spaces****削除**] を選択します。
- 配置したホログラムの一部を削除します。
- 写真アプリから一部の画像とビデオを削除します。
- HoloLens からいくつかのアプリをアンインストールします。 [**すべてのアプリ**] の一覧で、アンインストールするアプリをタップして押し続け、[**アンインストール**] を選択します。

## HoloLens で新しいスペースを作成できない

最も可能性が高いのは、記憶領域が少なくなっていることです。 ディスク領域を解放するには、[上記のヒント](#im-getting-a-low-disk-space-error)のいずれかを試してみてください。

## HoloLens エミュレーターが動作していない

HoloLens エミュレーターに関する情報は、開発者向けドキュメントに記載されています。  「 [HoloLens エミュレーターのトラブルシューティング](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)」を参照してください。