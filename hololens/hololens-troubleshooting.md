---
title: HoloLensデバイスのトラブルシューティング
description: デバイスの問題とトラブルシューティング手法を HoloLens するための最も一般的な解決策については、最新情報を入手してください。
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: 問題、バグ、トラブルシューティング、修正、ヘルプ、サポート、HoloLens、エミュレーター
ms.openlocfilehash: b07514e73e43d267aa856c0fb9a256448e565000
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635451"
---
# <a name="device-troubleshooting"></a>デバイスのトラブルシューティング

この記事では、いくつかの一般的な HoloLens の問題を解決する方法について説明します。

>[!IMPORTANT]
> トラブルシューティングの手順を開始する前に、可能であれば、デバイスがバッテリ容量の **20 ~ 40%** に充電されていることを確認してください。 電源ボタンの下にある [バッテリインジケーターライト](hololens2-setup.md#lights-that-indicate-the-battery-level) は、デバイスにログインしなくてもバッテリ容量を確認するための簡単な方法です。

<a id="list"></a>

**既知の問題**
- [20分後にリモートアシスタンスビデオがフリーズする](#remote-assist-video-freezes-after-20-minutes)
- [自動ログインによるログインの要求](#auto-login-asks-for-log-in)
- [Microsoft Edge を起動できない](#microsoft-edge-fails-to-launch)
- [キーボードが特殊文字に切り替わることはありません](#keyboard-doesnt-switch-to-special-characters)
- [ロックされたファイルのダウンロードにエラーが表示されない](#downloading-locked-files-doesnt-error)
- [デバイスポータルファイルのアップロード/ダウンロードがタイムアウトする](#device-portal-file-uploaddownload-times-out)
- [Insider build を使用してフラッシュされたデバイスで Insider preview から登録解除した後のブルースクリーン](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [画像が自動的にアップロードされない OneDrive](#onedrive-doesnt-automatically-upload-pictures)

**全般**
- [HoloLens が応答していないか、開始されていません](#hololens-is-unresponsive-or-wont-start)
- ["ディスク領域が不足しています" エラー](#low-disk-space-error)
- [調整が失敗する](#calibration-fails)
- [HoloLens が既に他のユーザーに設定されているため、サインインできません](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity が動作しない](#unity-isnt-working)
- [Windowsデバイスポータルが正しく動作していません](#windows-device-portal-isnt-working-correctly)
- [HoloLens Emulator が機能していません](#the-hololens-emulator-isnt-working)

**入力**
- [音声コマンドが動作していません](#voice-commands-arent-working)
- [手書き入力が機能していません](#hand-input-isnt-working)

**接続**
- [Wi-fi に接続できません](#cant-connect-to-wi-fi)

**外部デバイス** 
- [Bluetooth デバイスがペアリングしていない](#bluetooth-devices-arent-pairing)
- [USB C マイクが動作していない](#usb-c-microphone-isnt-working)
- [設定で使用可能と表示されているデバイスが動作しない](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>20分後にリモートアシスタンスビデオがフリーズする

> [!NOTE]
> この問題を修正するリモートアシスタンスの新しいバージョンがあります。 この問題を回避するには、リモートアシスタンスを最新バージョンに [更新](holographic-store-apps.md#update-apps) してください。

> [!NOTE]
> この既知の問題の重要度により、Windows Holographic バージョン21h1 の可用性が一時的に一時停止されました。 21H1 ビルドが再び使用できるようになりました。そのため、デバイスは最新の21H1 ビルドに再び更新される可能性があります。

[Windows Holographic version 21h1](hololens-release-notes.md#windows-holographic-version-21h1)の最新リリースでは、リモートアシスタンスの一部のユーザーが20分間の通話中にビデオをフリーズしています。 これは **既知の問題** です。

### <a name="workarounds"></a>回避策

リモートアシスタンスを新しいビルドに更新できない場合は、次の回避策を試してください。

#### <a name="restart-in-between-calls"></a>呼び出し間での再起動

呼び出しの長さが20分を超えていて、この問題が発生している場合は、デバイスを再起動してみてください。 リモートアシスタンスの呼び出しの間にデバイスを再起動すると、デバイスが更新され、良好な状態に戻ります。

Windows Holographic でデバイスをすぐに再起動するには [、バージョン 21h1](hololens-release-notes.md#windows-holographic-version-21h1)で [スタート] メニューを開き、[ユーザー] アイコンを選択し、[**再起動**] を選択します。

[リストに戻る](#list)

## <a name="auto-login-asks-for-log-in"></a>自動ログインによるログインの要求

HoloLens 2 デバイスは、**設定** アカウントのサインイン > オプションを使用して自動的にログインするように構成でき  ->    ->  ます。また、[**必須**] の値を [**なし**] に設定します。 機能の更新など、大幅に大きな更新プログラムを使用してデバイスを更新する場合、一部のユーザーがデバイスに再度ログインする必要がある場合があります。 これは **既知の問題** です。

このような状況が発生する可能性のある例を次に示します。

- デバイスを Windows Holographic、バージョン 2004 (ビルド 19041) から Windows Holographic、バージョン 21h1 (ビルド 20346) に更新する
- 同じメジャービルドで大規模な更新を実行するようにデバイスを更新する (Windows Holographic、バージョン Windows 2004、Holographic、バージョン20h2 など)
- デバイスを工場出荷時のイメージから最新のイメージに更新する

これは、次の場合には発生しません。

- 月単位のサービス更新を行っているデバイス

メソッドに対処する:

- PIN、パスワード、虹彩、Web 認証、FIDO2 キーなどのサインイン方法。
- デバイスの PIN を記憶できず、他の認証方法を使用できない場合、ユーザーは [手動の reflashing モード](hololens-recovery.md#manual-procedure)を使用できます。

[リストに戻る](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge を起動できない

> [!NOTE]
> この問題は、もともと Microsoft Edge の出荷バージョンで作成されています。 この問題は、[新しい Microsoft Edge](hololens-new-edge.md)で解決される場合があります。 そうでない場合は、フィードバックをお送りください。

いくつかのお客様が、Microsoft Edge を起動できないという問題を報告しています。 このようなお客様の場合、問題は再起動によって引き続き発生し、Windows またはアプリケーションの更新プログラムでは解決されません。 この問題が発生して[いて Windows が最新](hololens-updates.md#manually-check-for-updates)であることを確認した場合は、[フィードバックハブアプリ](hololens-feedback.md)から次のカテゴリとサブカテゴリを使用してバグを報告してください: インストールと更新 >、Windows Update のダウンロード、インストール、および構成を行います。

これまでに根本原因を根本的に解決できないため、既知の回避策はありません。 フィードバックハブを使用してバグを提出すると、調査に役立ちます。 これは **既知の問題** です。

[リストに戻る](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>キーボードが特殊文字に切り替わることはありません

OOBE 中に、ユーザーが職場または学校のアカウントを選択してパスワードを入力した後に、[&123] ボタンをタップしてキーボードの特殊文字に切り替えようとしたときに、特殊文字に変更されないという問題があります。 これは **既知の問題** です。

回避策:
-   キーボードを閉じて、[テキスト] フィールドをタップして再度開きます。
-   パスワードが正しく入力できません。 キーボードが次に再起動されると、正常に動作します。
- Web 認証。キーボードを閉じ、[ **別のデバイスからサインイン** する] を選択します。
-   数値のみを入力した場合、ユーザーは特定のキーを押したままにして、展開されたメニューを開くことができます。
-   USB キーボードを使用する。

これは、次のようには影響しません。
- 個人のアカウントを使用することを選択したユーザー。

[リストに戻る](#list)

## <a name="downloading-locked-files-doesnt-error"></a>ロックされたファイルのダウンロードエラー

> [!NOTE]
> これは、Windows Insider build バージョン20348.1403 で修正された **既知の問題** です。

Windows Holographic の以前のビルドでは、ロックされたファイルをダウンロードしようとすると、結果は HTTP エラーページになります。 Windows Holographic バージョン21h1 更新プログラムでは、ロックされたファイルをダウンロードしようとしても、何も表示されません。ファイルはダウンロードされず、エラーもありません。

[リストに戻る](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>デバイスポータルファイルのアップロード/ダウンロードがタイムアウトする
> [!NOTE]
> これは、Windows Insider build バージョン20348.1403 で修正された **既知の問題** です。 回避策の一環として SSL 接続を無効にした場合は、再度有効にすることを強くお勧めします。


一部のお客様は、ファイルをアップロードまたはダウンロードしようとすると、操作がハングし、タイムアウトになるか、完了しないように見えることがあります。 これは、"ファイルがロックされています[" という既知の問題](#downloading-locked-files-doesnt-error)とは別のものです。これは Windows Holographic、バージョン2004、20h2、21h1 のマーケットビルドに影響します。 この問題は、デバイスポータルで特定の要求を処理するときのバグに起因し、既定の https を使用する場合に最も一貫してヒットしています。 

### <a name="workaround"></a>回避策

この回避策は Wi-Fi と UsbNcm に同様に適用されますが、[SSL 接続] の下の [必須] オプションを無効にすることをお勧めします。 これを行うには、[デバイスポータル]、[ **システム**] の順に移動し、[ **基本設定** ] ページを選択します。 [ **デバイスのセキュリティ** ] セクションで、[ **SSL 接続**] を見つけて、[ **必須** の無効化] をオフにします。

ユーザーは、https://(IP アドレス) ではなく http://にアクセスし、ファイルのアップロードやダウンロードなどの機能を使用できます。

[リストに戻る](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Insider build を使用してフラッシュされたデバイスで Insider preview から登録解除した後のブルースクリーン

これは、insider preview ビルドを使用しており、HoloLens 2 を新しい insider preview ビルドで reflashed した後、insider プログラムから登録解除されたユーザーに影響する問題です。 これは **既知の問題** です。

これは、次のようには影響しません。
- Windows Insider に登録されていないユーザー 
- Insider
    - Insider ビルドがバージョン 18362. x であるためにデバイスが登録されている場合
    - 内部で署名された19041ビルドをフラッシュし、Insider プログラムに登録したままにする場合

回避策: 
- 問題を回避する 
    - Insider 以外のビルドをフラッシュします。 毎月の定期的な更新の1つ。
    - Insider Preview を維持
- デバイスの更新

    1. 接続されていない状態で完全に電源を切ることによって、HoloLens 2 を手動で[点滅モードに](hololens-recovery.md)します。 音量を上げたまま、[電源] ボタンをタップします。
    
    1. PC に Connect し、高度な回復コンパニオンを開きます。
    
    1. HoloLens 2 を既定のビルドにフラッシュします。

[リストに戻る](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>画像が自動的にアップロードされない OneDrive

HoloLens 用の OneDrive アプリでは、職場または学校アカウントのカメラの自動アップロードはサポートされていません。 これは **既知の問題** です。

回避策:

- お客様のビジネスで利用可能な場合、カメラの自動アップロードはコンシューマーの Microsoft アカウントでサポートされています。 職場または学校のアカウントに加えて、Microsoft アカウントにサインインできます (OneDrive アプリではデュアルサインインがサポートされています)。 OneDrive 内の Microsoft アカウントプロファイルから、自動、バックグラウンドカメラロールのアップロードを有効にすることができます。

- 写真を自動的にアップロードするためにコンシューマー Microsoft アカウントを安全に使用できない場合は、OneDrive アプリから職場または学校のアカウントに写真を手動でアップロードできます。 これを行うには、OneDrive アプリで職場または学校のアカウントにサインインしていることを確認します。 ボタンを選択し、[ **+** **アップロード**] を選択します。 [ **ピクチャ > カメラロール** に移動して、アップロードする写真またはビデオを検索します。 アップロードする写真またはビデオを選択し、[ **開く** ] ボタンを選択します。

[リストに戻る](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens が応答していないか、開始されていません

HoloLens が開始されない場合:

- 電源ボタンの横にある Led が点灯していない場合、または LED が少し点滅している場合は、 [HoloLens の料金](hololens2-charging.md#charging-the-device)が発生することがあります。
- 電源ボタンを押したときに Led が点灯しても、ディスプレイに何も表示されない場合は、 [デバイスをハードリセット](hololens-recovery.md#hard-reset-procedure)します。

HoloLens がフリーズまたは応答しなくなった場合は、次のようになります。

- 電源ボタンを押して、5つの led がすべてオフになるまで、または led が応答していない場合は15秒間、HoloLens をオフにします。 HoloLens を開始するには、[電源] ボタンをもう一度押します。

これらの手順がうまくいかない場合は、HoloLens 2 デバイスまたは[HoloLens (第1世代) デバイス](hololens1-recovery.md)[の回復](hololens-recovery.md)を試すことができます。

[リストに戻る](#list)

## <a name="low-disk-space-error"></a>"ディスク領域が不足しています" エラー

次の1つまたは複数の操作を行って、記憶域スペースを解放する必要があります。

- 未使用の領域をいくつか削除します。 [**設定** システムスペース] にアクセスして  >    >  、不要になった領域を選択し、[**削除**] を選択します。
- 配置したホログラムの一部を削除します。
- 写真アプリから一部の画像とビデオを削除します。
- HoloLens から一部のアプリをアンインストールします。 [ **すべてのアプリ** ] 一覧で、アンインストールするアプリをタップして保持し、[ **アンインストール**] を選択します。

[リストに戻る](#list)

## <a name="calibration-fails"></a>調整が失敗する

調整はほとんどの従業員に対して機能しますが、調整が失敗する場合もあります。
  
調整エラーの考えられる原因には、次のようなものがあります。

- 調整ターゲットに従うのではなく、気をかける
- ダーティまたは傷のあるデバイスのバイザーまたはデバイスのバイザーが適切に配置されていない
- 汚れまたは傷
- 特定の種類の連絡先レンズとグラス (色分けされたコンタクトレンズ、一部の toric 連絡先レンズ、IR ブロックグラス、高処方箋グラス、サングラス、類似)
- その他の発音と eyelash の拡張機能
- デバイスが目に見えないようにブロックしている場合は、ヘアまたは太 eyeglass フレーム
- 特定の目の physiology、視線、eyelashes、amblyopia、n agmu、LASIK またはその他の目のような目になることがあります。

調整が失敗した場合は、次の操作を行います。

- デバイスのバイザーをクリーニングしています
- グラスをクリーニングする
- デバイスバイザーをできるだけ近くにプッシュする
- バイザーでのオブジェクトの移動 (髪など)
- 部屋のライトをオンにする、または直接日光を切る

すべてのガイドラインに従い、調整が引き続き失敗する場合は、設定で調整のプロンプトを無効にすることができます。 また、 [フィードバックハブ](hololens-feedback.md)でフィードバックを提出してお知らせください。

[イメージの色または明るさのトラブルシューティング](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)に関する関連情報も参照してください。

視線位置はシステムによって計算されるため、IPD の設定は HoloLens 2 には適用されません。 

[リストに戻る](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>HoloLens が既に他のユーザーに設定されているため、サインインできません

デバイスを [**点滅モード** にし、Advanced Recovery コンパニオンを使用](hololens-recovery.md#clean-reflash-the-device)してデバイスを回復することができます。

[リストに戻る](#list)


## <a name="unity-isnt-working"></a>Unity が動作しない

- HoloLens 開発に推奨される Unity の最新バージョン用の[ツールをインストール](/windows/mixed-reality/install-the-tools)することをお勧めします。
- unity HoloLens Technical Preview の既知の問題については、 [HoloLens unity フォーラム](https://forum.unity3d.com/threads/known-issues.394627/)をご覧ください。

[リストに戻る](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windowsデバイスポータルが正しく動作していません

- Mixed Reality キャプチャのライブプレビュー機能は、数秒の待機時間が発生する場合があります。

- [仮想入力] ページで、[仮想ジェスチャ] セクションのジェスチャとスクロールコントロールが機能していません。 使用すると、効果はありません。 仮想入力ページの仮想キーボードが正常に動作します。

- 設定で開発者モードを有効にした後、デバイスポータルをオンにするスイッチが有効になるまで数秒かかることがあります。

[リストに戻る](#list)

## <a name="the-hololens-emulator-isnt-working"></a>HoloLens Emulator が機能していません

HoloLens エミュレーターに関する情報は、開発者向けのドキュメントにあります。  [HoloLens エミュレーターのトラブルシューティングの](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)詳細については、こちらを参照してください。


- Microsoft Store の一部のアプリは、エミュレーターと互換性がありません。 たとえば、若い Conker とフラグメントは、エミュレーターでは再生できません。
- Emulator では、PC web カメラを使用できません。
- Windows デバイスポータルのライブプレビュー機能は、エミュレーターでは機能しません。 混合した現実のビデオとイメージをキャプチャすることもできます。

[リストに戻る](#list)

## <a name="voice-commands-arent-working"></a>音声コマンドが動作していません

Cortana が音声コマンドに応答しない場合は、Cortana が有効になっていることを確認します。 [すべてのアプリ] の一覧で **Cortana**  >  **メニュー** ノートブック設定を選択して  >    >  変更を行います。 説明できることの詳細については、「 [HoloLens での音声の使用](hololens-cortana.md)」を参照してください。

HoloLens (第1世代) では、組み込み音声認識は構成できません。 常に有効になっています。 HoloLens 2 では、デバイスのセットアップ時に音声認識と Cortana の両方をオンにするかどうかを選択できます。

HoloLens 2 が音声に応答していない場合は、音声認識が有効になっていることを確認します。 [**スタート**  >  **設定**  >  **のプライバシー** に関する音声] を開き  >   、**音声認識** をオンにします。

[リストに戻る](#list)

## <a name="hand-input-isnt-working"></a>手書き入力が機能していません

HoloLens が自分の手を見えるようにするには、ジェスチャフレームに保持する必要があります。  Mixed Reality ホームでは、自分がどのように追跡されるかを知ることができるフィードバックが提供されます。  HoloLens のバージョンによって、次のようなフィードバックが異なる場合があります。
- HoloLens (第1世代) では、宝石カーソルがドットからリングに変わります。
- HoloLens 2 では、指先カーソルがスレートの近くにあると表示され、スレートがさらに離れたときにハンドレイが表示されます。

多くのイマーシブアプリは、Mixed Reality ホームに似た入力パターンに従います。  [HoloLens (第1世代)](hololens1-basic-usage.md#use-hololens-with-your-hands)と[HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame)で手書き入力を使用する方法について説明します。

手袋を装着している場合は、一部の種類の手袋がハンドトラッキングで動作しないことに注意してください。  一般的な例としては、赤外線信号を吸収する傾向があり、深度カメラでは選択されていない黒色のゴムグローブがあります。  ゴムグローブが使用されている場合は、青や灰色などの明るい色を試すことをお勧めします。  もう1つの例として、大きな baggy グローブがあります。これは、手の形が見えにくくなる傾向があります。 最良の結果を得るには、できるだけフォーム継ぎ手として手袋を使用することをお勧めします。

バイザーに指紋または汚れがある場合は、HoloLens に付属しているマイクロファイバークリーニング布を使用して、バイザーをゆっくりとクリーニングします。

[リストに戻る](#list)

## <a name="cant-connect-to-wi-fi"></a>Wi-Fi に接続できません

HoloLens を Wi-Fi ネットワークに接続できない場合は、次の点を試してみてください。

- Wi-Fi が有効になっていることを確認します。 確認するには、開始ジェスチャを使用して、[**設定** ネットワーク] [  >  **&amp; インターネット** wi-fi] の順に選択し  >  ます。 Wi-Fi がオンになっている場合は、オフにしてから再度有効にしてみてください。
- ルーターまたはアクセスポイントに近い場所に移動します。
- Wi-Fi ルーターを再起動し、 [HoloLens を再起動](hololens-recovery.md)します。 接続を再試行してください。
- これらの問題が解決しない場合は、ルーターが最新のファームウェアを使用していることを確認してください。 この情報については、製造元の web サイトを参照してください。

[リストに戻る](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth デバイスがペアリングしていない

[Bluetooth デバイスのペアリング](hololens-connect-devices.md)で問題が発生した場合は、次の操作を試してください。

- **設定**  >  **デバイス** にアクセスし、Bluetooth が有効になっていることを確認します。 有効になっている場合は、オフにしてから再びオンにします。
- Bluetooth デバイスが完全に充電されていること、または電池が最新であることを確認します。
- それでも接続できない場合は、 [HoloLens を再起動](hololens-recovery.md)します。

[リストに戻る](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB C マイクが動作していない
USB C のマイクによっては、マイク *と* スピーカーの両方として誤って報告されることに注意してください。 これは、HoloLens ではなく、マイクに問題があります。 これらのマイクの1つを HoloLens に接続すると、サウンドが失われる可能性があります。 幸いにも、簡単な修正があります。  

**設定**  ->  **システム**  ->  **サウンド** で、組み込みのスピーカー **(アナログ機能オーディオドライバー)** を **既定のデバイス** として明示的に設定します。 マイクが取り外され、後で再接続された場合でも、HoloLens はこの設定を記憶する必要があります。

![USB C マイクのトラブルシューティング](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>設定で使用可能と表示されているデバイスが動作しない

HoloLens (第1世代) では Bluetooth オーディオプロファイルはサポートされていません。 スピーカーやヘッドセットなどの Bluetooth オーディオデバイスは、HoloLens 設定で使用できるように見えることがありますが、これらはサポートされていません。

HoloLens 2 は、ステレオ再生用の Bluetooth A2DP audio プロファイルをサポートしています。 Bluetooth 周辺機器からのマイクキャプチャを有効にする Bluetooth ハンドフリープロファイルは、HoloLens 2 ではサポートされていません。

Bluetooth デバイスの使用に問題がある場合は、それがサポートされているデバイスであることを確認してください。 サポートされているデバイスは次のとおりです。

- 英語の QWERTY Bluetooth キーボード (holographic キーボードを使用する任意の場所で使用できます)。
- マウスを Bluetooth します。
- [HoloLens clicker](hololens1-clicker.md)。

他の Bluetooth HID および GATT デバイスを HoloLens とペアリングできます。 ただし、デバイスを実際に使用するには、Microsoft Store から対応するコンパニオンアプリをインストールすることが必要になる場合があります。

[リストに戻る](#list)
