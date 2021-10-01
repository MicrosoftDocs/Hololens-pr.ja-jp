---
title: HoloLensデバイスのトラブルシューティング
description: デバイスの問題とトラブルシューティング手法を HoloLens するための最も一般的な解決策については、最新情報を入手してください。
author: mattzmsft
ms.author: mazeller
ms.date: 9/30/2021
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: 問題、バグ、トラブルシューティング、修正、ヘルプ、サポート、HoloLens、エミュレーター
ms.openlocfilehash: 3c4d6e22660e365acd2c3aca3119632c73926391
ms.sourcegitcommit: b9cd7ed5edb98249c609b547b90587863ea1cb9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2021
ms.locfileid: "129364618"
---
# <a name="device-troubleshooting"></a>デバイスのトラブルシューティング

この記事では、いくつかの一般的な HoloLens の問題を解決する方法について説明します。

>[!IMPORTANT]
> トラブルシューティングの手順を開始する前に、可能であれば、デバイスのバッテリ容量が **20 - 40%** 残っていることを確認してください。 電源 ボタンの下 にある[バッテリ インジケーター ライト](hololens2-setup.md#lights-that-indicate-the-battery-level)により、デバイスにログインせずにバッテリ容量を簡単に確認できます。

<a id="list"></a>

**既知の問題**
- [電力が18% になるたびに、デバイスが突然自動的にシャットダウンされます。](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
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

## <a name="every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically"></a>電力が18% になるたびに、デバイスが突然自動的にシャットダウンされます。

デバイスが18% のバッテリに達したときに、予期しないシャットダウンが発生する既知の問題があります。 これはソフトウェアの問題であり、ハードウェアやバッテリの問題ではありません。このため、デバイスを交換しないでください。 問題がこのバグと一致するかどうかわからない場合は、次のことを行ってください。

1. デバイスでオプションの診断が有効になっていることを確認します。
1. 問題を再現する
1. [フィードバックハブ](hololens-feedback.md)の送信の問題
1. フィードバックの発行 URL を共有する
1. [サポートに問い合わせ](https://aka.ms/hololenssupport)

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

[一覧に戻る](#list)

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

[一覧に戻る](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge を起動できない

> [!NOTE]
> この問題は、もともと Microsoft Edge の出荷バージョンで作成されています。 この問題は、[新しい Microsoft Edge](hololens-new-edge.md)で解決される場合があります。 そうでない場合は、フィードバックをお送りください。

いくつかのお客様が、Microsoft Edge を起動できないという問題を報告しています。 このようなお客様の場合、問題は再起動によって引き続き発生し、Windows またはアプリケーションの更新プログラムでは解決されません。 この問題が発生して[いて Windows が最新](hololens-updates.md#manually-check-for-updates)であることを確認した場合は、[フィードバックハブアプリ](hololens-feedback.md)から次のカテゴリとサブカテゴリを使用してバグを報告してください: インストールと更新 >、Windows Update のダウンロード、インストール、および構成を行います。

これまでに根本原因を根本的に解決できないため、既知の回避策はありません。 フィードバックハブを使用してバグを提出すると、調査に役立ちます。 これは **既知の問題** です。

[一覧に戻る](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>キーボードが特殊文字に切り替わることはありません

OOBE 中に、ユーザーが職場または学校のアカウントを選択してパスワードを入力した後に、[&123] ボタンをタップしてキーボードの特殊文字に切り替えようとしたときに、特殊文字に変更されないという問題があります。 これは **既知の問題** です。

回避策:

- キーボードを閉じて、[テキスト] フィールドをタップして再度開きます。
- パスワードが正しく入力できません。 キーボードが次に再起動されると、正常に動作します。
- Web 認証。キーボードを閉じ、[ **別のデバイスからサインイン** する] を選択します。
- 数値のみを入力した場合、ユーザーは特定のキーを押したままにして、展開されたメニューを開くことができます。
- USB キーボードを使用する。

これは、次のようには影響しません。

- 個人のアカウントを使用することを選択したユーザー。

[一覧に戻る](#list)

## <a name="downloading-locked-files-doesnt-error"></a>ロックされたファイルのダウンロードエラー

> [!NOTE]
> これは [、Windows Holographic バージョン 21h1-2021 年7月の更新](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)で修正された **既知の問題** です。

Windows Holographic の以前のビルドでは、ロックされたファイルをダウンロードしようとすると、結果は HTTP エラーページになります。 Windows Holographic バージョン21h1 更新プログラムでは、ロックされたファイルをダウンロードしようとしても、何も表示されません。ファイルはダウンロードされず、エラーもありません。

[一覧に戻る](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>デバイス ポータルファイルのアップロード/ダウンロードがアウトした場合
> [!NOTE]
> これは、Holographic **バージョン** [21H1 Windows 2021](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)年 7 月の更新プログラム で修正された既知の問題です。 回避策の一環として以前に SSL 接続を無効にした場合は、再び有効にすることを強くお勧めします。

一部のお客様は、ファイルのアップロードまたはダウンロードを試みる際に、操作がハングし、その後に時間が切れているか、完了しない可能性があります。 これは、'ファイル ロック['](#downloading-locked-files-doesnt-error)の既知の問題とは別です。これは、Windows Holographic、バージョン 2004、20H2、および 21H1 の市場内ビルドに影響します。 この問題は、デバイス ポータル による特定の要求の処理のバグが原因で根本原因であり、既定の https を使用すると最も一貫してヒットします。

### <a name="workaround"></a>回避策

この回避策は、Wi-Fi と UsbNcm に等しく適用され、"SSL 接続" で "必須" オプションを無効にします。 これを行うには、[システム] **デバイス ポータルに移動** し、[基本設定] **ページを選択** します。 [デバイス セキュリティ **] セクションで** 、[SSL 接続] **を探し、[** 必須] を無効にするにはオフ **にします**。

その後、ユーザーは http:// にアクセスする必要 https:// (IP アドレス) ではなく、ファイルのアップロードやダウンロードのような機能が機能します。

[一覧に戻る](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Insider ビルドでフラッシュされたデバイスで Insider プレビューから登録を解除した後のブルー スクリーン

これは、Insider プレビュー ビルドのユーザーに影響を与え、新しい Insider プレビュー ビルドで HoloLens 2 を再フラッシュした後、Insider プログラムから登録を解除したユーザーに影響を与える問題です。 これは既知の **問題です**。

これは、次の場合には影響を与え "ない" です。

- Insider に登録されていないWindowsユーザー
- インサイダー：
    - Insider ビルドがバージョン 18362.x 以降にデバイスが登録されている場合
    - Insider 署名済み 19041.x ビルドをフラッシュし、Insider プログラムに登録された

回避:

- 問題を回避する
    - インサイダー以外のビルドをフラッシュします。 定期的な毎月の更新プログラムの 1 つ。
    - Insider Preview を利用する
- デバイスを再フラッシュする

    1. 接続していない[HoloLens 2電源](hololens-recovery.md)を完全にオフにすることで、デバイスを手動でフラッシュ モードにします。 次に、ボリュームを上に保持している間に、[電源] ボタンをタップします。

    1. Connect PC に接続し、Advanced Recovery Companion を開きます。

    1. 既定のビルドHoloLens 2をフラッシュします。

[一覧に戻る](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive画像が自動的にアップロードされません

アプリOneDriveアプリではHoloLensまたは学校アカウントの自動カメラ アップロードはサポートされていません。 これは既知の **問題です**。

回避策:

- ビジネスで実行可能な場合は、コンシューマー向け Microsoft アカウントでカメラの自動アップロードがサポートされます。 自分のアカウントまたは学校アカウントMicrosoft アカウント、自分のアカウントにサインインできます (OneDrive アプリはデュアル サインインをサポートしています)。 アプリ内Microsoft アカウントプロファイルOneDrive、バックグラウンド カメラの自動ロール アップロードを有効にできます。

- 写真を自動的にアップロードするためにコンシューマー Microsoft アカウント を安全に使用できない場合は、アプリから手動で写真を仕事または学校アカウントにアップロードOneDriveできます。 これを行うには、アプリで自分の仕事用または学校アカウントにサインインOneDriveしてください。 ボタンを選択 **+** し、 [] を **アップロード。** [カメラ ロール] の [ピクチャ] に移動して、アップロード **する>を見つける。** アップロードする写真またはビデオを選択し、[開く] ボタン **を選択** します。

[一覧に戻る](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens応答しないか、起動しない

お使HoloLens開始しない場合:

- 電源ボタンの横にある LED が点灯しない場合、または短時間点滅する LED が 1 つしか表示されていない場合は、電源[HoloLens。](hololens2-charging.md#charging-the-device)
- 電源ボタンを押すと LED が点灯するが、ディスプレイに何も表示できない場合は、デバイス のハード リセット [を行います](hololens-recovery.md#hard-reset-procedure)。

お使HoloLensが固定または応答しなくなる場合:

- 5 つの LED HoloLens電源がオフになるまで電源ボタンを押し、LED が応答しない場合は 15 秒間電源をオフにします。 アプリケーションを起動するにはHoloLensもう一度電源ボタンを押します。

これらの手順が機能しない場合は、デバイスまたは (第[1](hololens-recovery.md)世代) HoloLens 2デバイスHoloLens[回復を試みてみます。](hololens1-recovery.md)

[一覧に戻る](#list)

## <a name="low-disk-space-error"></a>"ディスク領域が少ない" エラー

次の 1 つ以上を実行して、一部の記憶域スペースを解放する必要があります。

- 未使用のスペースを削除します。 [システム **スペース設定** に移動し、不要になった領域を選択して、 [削除  >    >  ] を **選択します**。
- 配置したホログラムの一部を削除します。
- フォト アプリからいくつかの画像とビデオを削除します。
- アプリから一部のアプリをアンインストールHoloLens。 [すべての **アプリ] の一** 覧で、アンインストールするアプリをタップしたままにし、[ アンインストール] を **選択します**。

[一覧に戻る](#list)

## <a name="calibration-fails"></a>調整が失敗する

調整はほとんどのユーザーに対して機能しますが、調整に失敗する場合があります。
  
調整エラーの考え方としては、次のようなものがあります。

- 気を散らして調整ターゲットに従わなくなって
- ダーティまたはスクラッチされたデバイス バイザーまたはデバイス バイザーが正しく配置されていない
- ダーティまたはスクラッチの眼鏡
- 特定の種類のコンタクト レンズと眼鏡 (色付きコンタクト レンズ、一部の Toric コンタクト レンズ、IR ブロッキング 眼鏡、高い眼鏡、眼鏡など)
- より顕著なメイクといくつかのまつげの拡張機能
- デバイスが目を見るのを妨げている場合は、黒い眼鏡フレームまたは太い眼鏡フレーム
- 特定の目の前部、目の状態、または狭い目、長いまつげ、アンブリータイン、nystagmus、LASIK や他の目の治療の一部のケースなど、目の治療

調整に失敗した場合は、次の手順を試してください。

- デバイス バイザーのクリーニング
- 眼鏡のクリーニング
- デバイスバイザーを可能な限り目の近くにプッシュする
- バイザー内のオブジェクトを外に移動する (生長など)
- 部屋の照明をオンにするか、直接の光から出て行く

すべてのガイドラインに従い、調整がまだ失敗している場合は、次の手順で調整プロンプトを設定。 また、 でフィードバックを送信して、お知[フィードバック Hub。](hololens-feedback.md)

画像の色または明るさ [のトラブルシューティングについては、関連情報も参照してください。](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

目の位置はシステムによって計算HoloLens 2、IPD の設定は適用されません。 

[一覧に戻る](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>自分のアカウントが他のユーザー HoloLens設定されたため、サインインできない

デバイスを[フラッシュ モードにし、Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device)を使用してデバイスを回復できます。

[一覧に戻る](#list)


## <a name="unity-isnt-working"></a>Unity が機能しない

- 新[しい開発に推奨される](/windows/mixed-reality/install-the-tools)Unity の最新バージョンについては、「ツールをインストールするHoloLensしてください。
- Unity HoloLens Technical Preview に関する既知の問題については、Unity フォーラムのHoloLens[を参照してください](https://forum.unity3d.com/threads/known-issues.394627/)。

[一覧に戻る](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windowsデバイス ポータルが正しく動作しない

- キャプチャの Live Preview 機能Mixed Reality数秒の待機時間が発生する可能性があります。

- [仮想入力] ページの [仮想ジェスチャ] セクションの [ジェスチャ] コントロールと [スクロール] コントロールは機能しません。 それらを使用した場合、効果はありません。 仮想入力ページの仮想キーボードは正しく動作します。

- 設定 で開発者モードを有効にした後、スイッチが有効になっているまで数秒デバイス ポータル場合があります。

[一覧に戻る](#list)

## <a name="the-hololens-emulator-isnt-working"></a>このHoloLens Emulator動作していません

このエミュレーターのHoloLensについては、開発者向けドキュメントを参照してください。  詳細については、HoloLens[エミュレーターのトラブルシューティングに関する記事を参照してください](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)。


- Microsoft Store の一部のアプリは、エミュレーターと互換性がありません。 たとえば、若い Conker とフラグメントは、エミュレーターでは再生できません。
- Emulator では、PC web カメラを使用できません。
- Windows デバイスポータルのライブプレビュー機能は、エミュレーターでは機能しません。 混合した現実のビデオとイメージをキャプチャすることもできます。

[一覧に戻る](#list)

## <a name="voice-commands-arent-working"></a>音声コマンドが動作していません

Cortana が音声コマンドに応答しない場合は、Cortana が有効になっていることを確認します。 [すべてのアプリ] の一覧で **Cortana**  >  **メニュー** ノートブック設定を選択して  >    >  変更を行います。 説明できることの詳細については、「 [HoloLens での音声の使用](hololens-cortana.md)」を参照してください。

HoloLens (第1世代) では、組み込み音声認識は構成できません。 常に有効になっています。 HoloLens 2 では、デバイスのセットアップ時に音声認識と Cortana の両方をオンにするかどうかを選択できます。

HoloLens 2 が音声に応答していない場合は、音声認識が有効になっていることを確認します。 [**スタート**  >  **設定**  >  **のプライバシー** に関する音声] を開き  >   、**音声認識** をオンにします。

[一覧に戻る](#list)

## <a name="hand-input-isnt-working"></a>手書き入力が機能していません

HoloLens が自分の手を見えるようにするには、ジェスチャフレームに保持する必要があります。  Mixed Reality ホームでは、自分がどのように追跡されるかを知ることができるフィードバックが提供されます。  HoloLens のバージョンによって、次のようなフィードバックが異なる場合があります。

- HoloLens (第1世代) では、宝石カーソルがドットからリングに変わります。
- HoloLens 2 では、指先カーソルがスレートの近くにあると表示され、スレートがさらに離れたときにハンドレイが表示されます。

多くのイマーシブアプリは、Mixed Reality ホームに似た入力パターンに従います。  [HoloLens (第1世代)](hololens1-basic-usage.md#use-hololens-with-your-hands)と[HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame)で手書き入力を使用する方法について説明します。

手袋を装着している場合は、一部の種類の手袋がハンドトラッキングで動作しないことに注意してください。  一般的な例としては、赤外線信号を吸収する傾向があり、深度カメラでは選択されていない黒色のゴムグローブがあります。  ゴムグローブが使用されている場合は、青や灰色などの明るい色を試すことをお勧めします。  もう1つの例として、大きな baggy グローブがあります。これは、手の形が見えにくくなる傾向があります。 最良の結果を得るには、できるだけフォーム継ぎ手として手袋を使用することをお勧めします。

バイザーに指紋または汚れがある場合は、HoloLens に付属しているマイクロファイバークリーニング布を使用して、バイザーをゆっくりとクリーニングします。

[一覧に戻る](#list)

## <a name="cant-connect-to-wi-fi"></a>Wi-Fi に接続できません

HoloLens を Wi-Fi ネットワークに接続できない場合は、以下を試してください。

- Wi-Fi がオンになっていることを確認してください。 確認するには、開始ジェスチャを使用して、[**設定** ネットワーク] [  >  **&amp; インターネット** wi-fi] の順に選択し  >  ます。 Wi-Fi がオンである場合は、オフにしてから、もう一度オンにしてみてください。
- ルーターまたはアクセス ポイントに PC を近づけます。
- Wi-Fi ルーターを再起動し、 [HoloLens を再起動](hololens-recovery.md)します。 接続を再試行してください。
- これらのいずれも機能しない場合は、ルーターのファームウェアが最新であるか確認します。 この情報は、製造元の Web サイトで見つけることができます。

[一覧に戻る](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth デバイスがペアリングしていない

[Bluetooth デバイスのペアリング](hololens-connect-devices.md)で問題が発生した場合は、次の操作を試してください。

- **設定**  >  **デバイス** にアクセスし、Bluetooth が有効になっていることを確認します。 有効になっている場合は、オフにしてから再びオンにします。
- Bluetooth デバイスが完全に充電されていること、または電池が最新であることを確認します。
- それでも接続できない場合は、 [HoloLens を再起動](hololens-recovery.md)します。

[一覧に戻る](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB C マイクが動作していない

USB C のマイクによっては、マイク *と* スピーカーの両方として誤って報告されることに注意してください。 これは、HoloLens ではなく、マイクに問題があります。 これらのマイクの1つを HoloLens に接続すると、サウンドが失われる可能性があります。 幸いにも、簡単な修正があります。  

**設定**  ->  **システム**  ->  **サウンド** で、組み込みのスピーカー **(アナログ機能オーディオドライバー)** を **既定のデバイス** として明示的に設定します。 マイクが取り外され、後で再接続された場合でも、HoloLens はこの設定を記憶する必要があります。

![USB C マイクのトラブルシューティング。](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>設定で使用可能と表示されているデバイスが動作しない

HoloLens (第1世代) では Bluetooth オーディオプロファイルはサポートされていません。 スピーカーやヘッドセットなどの Bluetooth オーディオデバイスは、HoloLens 設定で使用できるように見えることがありますが、これらはサポートされていません。

HoloLens 2 は、ステレオ再生用の Bluetooth A2DP audio プロファイルをサポートしています。 Bluetooth 周辺機器からのマイクキャプチャを有効にする Bluetooth ハンドフリープロファイルは、HoloLens 2 ではサポートされていません。

Bluetooth デバイスの使用に問題がある場合は、それがサポートされているデバイスであることを確認してください。 サポートされているデバイスは次のとおりです。

- 英語の QWERTY Bluetooth キーボード (holographic キーボードを使用する任意の場所で使用できます)。
- マウスを Bluetooth します。
- [HoloLens clicker](hololens1-clicker.md)。

他の Bluetooth HID および GATT デバイスを HoloLens とペアリングできます。 ただし、デバイスを実際に使用するには、Microsoft Store から対応するコンパニオンアプリをインストールすることが必要になる場合があります。

[一覧に戻る](#list)
