---
title: HoloLens デバイスのトラブルシューティング
description: HoloLens デバイスの問題とトラブルシューティング手法に関する最も一般的な解決策を最新の情報にしてください。
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
keywords: 問題, バグ, トラブルシューティング, 修正, ヘルプ, サポート, HoloLens, エミュレーター
ms.openlocfilehash: b69dddf04ac31b69f0b2f8759d095806189f33ab
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924623"
---
# <a name="device-troubleshooting"></a>デバイスのトラブルシューティング

この記事では、HoloLens のいくつかの一般的な問題を解決する方法について説明します。

>[!IMPORTANT]
> トラブルシューティング手順を開始する前に、可能であれば、デバイスにバッテリ容量の **20 ~ 40%** が課金されます。 電源 [ボタンの下](hololens2-setup.md#lights-that-indicate-the-battery-level) にあるバッテリ インジケーター ライトは、デバイスにログインせずにバッテリ容量を簡単に確認する方法です。

<a id="list"></a>

**既知の問題**
- [Remote Assist 20 分後にビデオがフリーズする](#remote-assist-video-freezes-after-20-minutes)
- [自動ログインでログインを求める](#auto-login-asks-for-log-in)
- [Microsoft Edge起動に失敗する](#microsoft-edge-fails-to-launch)
- [キーボードが特殊文字に切り替えない](#keyboard-doesnt-switch-to-special-characters)
- [ロックされたファイルをダウンロードしてもエラーが表示されません](#downloading-locked-files-doesnt-error)
- [デバイス ポータルファイルのアップロード/ダウンロードがアウトした場合](#device-portal-file-uploaddownload-times-out)
- [Insider ビルドでフラッシュされたデバイスで Insider プレビューから登録を解除した後のブルー スクリーン](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive で画像が自動的にアップロードされません](#onedrive-doesnt-automatically-upload-pictures)

**全般**
- [HoloLens が応答しないか、起動しない](#hololens-is-unresponsive-or-wont-start)
- ["ディスク領域が少ない" エラー](#low-disk-space-error)
- [調整に失敗する](#calibration-fails)
- [HoloLens が以前に他のユーザー用に設定されたため、サインインできない](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity が機能しない](#unity-isnt-working)
- [Windows デバイス ポータルが正しく動作しない](#windows-device-portal-isnt-working-correctly)
- [HoloLens エミュレーターが動作しない](#the-hololens-emulator-isnt-working)

**入力**
- [音声コマンドが機能しない](#voice-commands-arent-working)
- [手入力が機能しない](#hand-input-isnt-working)

**接続**
- [Wi-Fi に接続できない](#cant-connect-to-wi-fi)

**外部デバイス** 
- [Bluetooth デバイスがペアリングされていない](#bluetooth-devices-arent-pairing)
- [USB-C マイクが動作しない](#usb-c-microphone-isnt-working)
- [[設定] に使用可能として表示されているデバイスが機能しない](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Remote Assist 20 分後にビデオがフリーズする

> [!NOTE]
> この既知の問題の重大度により、現在、Windows Holographic バージョン 21H1 の可用性が一時停止されています。 引き続きデバイスを 21H1 に更新する場合は、ページの上部にあるリリース ノートの [手順を参照してください。](hololens-release-notes.md)

[Windows Holographic バージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1)の最新リリースでは、Remote Assist の一部のユーザーは、20 分を超える通話中にビデオの凍結を経験しました。 これは既知の **問題です**。

### <a name="workarounds"></a>回避策

#### <a name="restart-in-between-calls"></a>呼び出しの間に を再起動する

通話が 20 分以上続き、この問題が発生している場合は、デバイスを再起動してみてください。 呼び出しの間にRemote Assistを再起動すると、デバイスが更新され、良好な状態に戻されます。

[Windows Holographic バージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1)でデバイスをすばやく再起動するには、スタート メニューを開き、ユーザー アイコンを選択し、[再起動] を **選択します**。

#### <a name="revert-to-an-older-build"></a>古いビルドに戻す

一部のお客様は、以前の OS バージョンに戻す際に、この問題が発生しなくなったと感じ取っています。 デバイスでこの問題が発生している場合は、次の手順を試してください。


回避策:

- ビジネスで実行可能な場合は、コンシューマー向け Microsoft アカウントでカメラの自動アップロードがサポートされます。 自分のアカウントまたは学校アカウントMicrosoft アカウント、自分のアカウントにサインインできます (OneDrive アプリではデュアル サインインがサポートされています)。 OneDrive 内Microsoft アカウントプロファイルから、自動のバックグラウンド カメラ ロール アップロードを有効にできます。

- 写真を自動的にアップロードするためにコンシューマー Microsoft アカウント を安全に使用できない場合は、OneDrive アプリから手動で写真を仕事または学校アカウントにアップロードできます。 これを行うには、OneDrive アプリで、自分の仕事用または学校アカウントにサインインしている必要があります。 ボタンを選択 **+** し、 [アップロード] を **選択します**。 [カメラ ロール] の [ピクチャ] に移動して、アップロード **する>を見つける。** アップロードする写真またはビデオを選択し、[開く] ボタン **を選択** します。


1. [Windows Holographic バージョン 20H2 – 2021 年 5 月更新プログラムのビルドをダウンロードする](https://aka.ms/hololens2download/10.0.19041.1146)
1. 以前の [OS バージョンに戻る手順に従います](hololens-update-hololens.md#go-back-to-a-previous-version)
1. デバイス [で OS 更新プログラムを手動で一時停止するか、多](hololens-updates.md#pause-updates-via-device) くのデバイスで MDM を介して [遅延を使用します](hololens-updates.md#configure-an-update-deferral-policy)。

[リストに戻る](#list)

## <a name="auto-login-asks-for-log-in"></a>自動ログインでログインを求める

デバイスHoloLens 2設定アカウントサインイン オプション -> を使用して自動的にログインするように構成できます。[必須] で値を [Never] に  ->    ->  設定 **します**。  一部のユーザーは、機能更新プログラムなど、大幅に大きな更新プログラムを使用してデバイスを更新するときに、デバイスに再度ログインする必要があります。 これは既知の **問題です**。

これが発生する可能性がある例を次に示します。

- Windows Holographic バージョン 2004 (ビルド 19041.xxxx) から Windows Holographic バージョン 21H1 (ビルド 20346.xxxx) へのデバイスの更新
- 同じメジャー ビルド (Windows Holographic バージョン 2004 から Windows Holographic バージョン 20H2 など) で大規模な更新を行うデバイスの更新
- ファクトリ イメージから最新のイメージへのデバイスの更新

これは、次の場合には発生しません。

- 毎月のサービス更新プログラムを受け取るデバイス

メソッドの回避:

- PIN、パスワード、あやめ、Web 認証、FIDO2 キーなどのサインイン方法。
- デバイス PIN を記憶できない場合、その他の認証方法を使用できない場合、ユーザーは手動 [の再フラッシュ モードを使用できます](hololens-recovery.md#manual-procedure)。

[リストに戻る](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge起動に失敗する

> [!NOTE]
> この問題は、当初、出荷バージョンのバージョンを念頭Microsoft Edgeして作成されました。 この問題は、 の新しいバージョン[で解決Microsoft Edge。](hololens-new-edge.md) そうではない場合は、フィードバックを送信してください。

一部のお客様から、起動に失敗する問題Microsoft Edge報告されています。 これらのお客様の場合、この問題は再起動を通じて解決され、Windows またはアプリケーションの更新プログラムでは解決されません。 この問題が発生し [、Windows](hololens-updates.md#manually-check-for-updates)が最新の である確認済みである場合は、次のカテゴリとサブカテゴリを持つ [フィードバック Hub](hololens-feedback.md) アプリからバグを報告してください: > のダウンロード、インストール、および構成 Windows Update。

これまでに問題を根本原因にできなかったので、既知の回避策はありません。 レポートを使用してバグをフィードバック Hub調査に役立ちます。 これは既知の **問題です**。

[リストに戻る](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>キーボードが特殊文字に切り替えない

OOBE 中に問題が発生します。ユーザーが仕事用または学校アカウントを選択し、パスワードを入力すると、&123 ボタンをタップしてキーボードの特殊文字に切り替えようとしても、特殊文字に変わりません。 これは既知の **問題です**。

回避方法:
-   キーボードを閉じ、テキスト フィールドをタップして再度開きます。
-   パスワードを誤って入力します。 次回キーボードを再起動すると、期待した通り動作します。
- Web 認証を行い、キーボードを閉じ、別の **デバイスから [サインイン] を選択します**。
-   数値のみを入力する場合、ユーザーは特定のキーを長押しして展開されたメニューを開くことができます。
-   USB キーボードを使用する。

これは、次の場合には影響を与え "ない" です。
- 個人アカウントの使用を選択したユーザー。

[リストに戻る](#list)


## <a name="downloading-locked-files-doesnt-error"></a>ロックされたファイルをダウンロードしてもエラーが発生しない
> !注 これは、ビルド **バージョン** 20348.1403 で修正Windows Insider既知の問題です。


以前の Windows Holographic のビルドでは、ロックされたファイルをダウンロードしようとすると、結果は HTTP エラー ページになります。 Windows Holographic バージョン 21H1 更新プログラムでは、ロックされたファイルをダウンロードしようとしても、何も表示されません。ファイルはダウンロードされません。エラーはありません。 

[リストに戻る](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>デバイス ポータルファイルのアップロード/ダウンロードがアウトした場合
> !注 これは、ビルド **バージョン** 20348.1403 で修正Windows Insider既知の問題です。 回避策の一環として以前に SSL 接続を無効にした場合は、再び有効にすることを強くお勧めします。


一部のお客様は、ファイルのアップロードまたはダウンロードを試みる際に、操作がハングし、その後に時間が切れたか、完了しない可能性があります。 これは、"ファイル ロック["](#downloading-locked-files-doesnt-error) の既知の問題とは別です。これは、Windows Holographic、バージョン 2004、20H2、および 21H1 の市場内ビルドに影響します。 この問題は、デバイス ポータル による特定の要求の処理のバグが原因で根本原因であり、既定の https を使用すると最も一貫してヒットします。 

### <a name="workaround"></a>回避策

この回避策は、Wi-Fi と UsbNcm に同じように適用され、"SSL 接続" の下で "必須" オプションを無効にします。 これを行うには、[システム] の デバイス ポータル **に移動** し、[基本設定] **ページを選択** します。 [デバイス セキュリティ **] セクションで** 、[SSL 接続] **を探し**、[必須] を無効にするには **オフにします**。

その後、ユーザーは http:// にアクセスする必要 https:// (IP アドレス) ではなく、ファイルのアップロードやダウンロードのような機能が機能します。

[リストに戻る](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Insider ビルドでフラッシュされたデバイスで Insider プレビューから登録を解除した後のブルー スクリーン

これは、Insider プレビュー ビルドに含まれるユーザーに影響を与え、新しい Insider プレビュー ビルドで HoloLens 2 を再フラッシュした後、Insider プログラムから登録を解除したユーザーに影響する問題です。 これは既知の **問題です**。

これは、次の場合には影響を与え "ない" です。
- アカウントに登録されていないWindows Insider 
- インサイダー：
    - Insider ビルドがバージョン 18362.x 以降にデバイスが登録されている場合
    - Insider 署名済み 19041.x ビルドをフラッシュし、Insider プログラムに登録された

回避: 
- 問題を回避する 
    - インサイダー以外のビルドをフラッシュします。 定期的な毎月の更新プログラムの 1 つ。
    - Insider Preview を利用する
- デバイスを再フラッシュする

    1. 接続していない [HoloLens 2電源](hololens-recovery.md) を完全にオフにすることで、デバイスを手動でフラッシュ モードにします。 次に、ボリュームを上に保持している間に、[電源] ボタンをタップします。
    
    1. PC に接続し、Advanced Recovery Companion を開きます。
    
    1. 既定のビルドHoloLens 2をフラッシュします。

[リストに戻る](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive で画像が自動的にアップロードされません

HoloLens 用の OneDrive アプリでは、仕事用または学校アカウントの自動カメラ アップロードはサポートされていません。 これは既知の **問題です**。

回避策:

- ビジネスで実行可能な場合は、コンシューマー向け Microsoft アカウントでカメラの自動アップロードがサポートされます。 自分のアカウントまたは学校アカウントMicrosoft アカウント、自分のアカウントにサインインできます (OneDrive アプリではデュアル サインインがサポートされています)。 OneDrive 内Microsoft アカウントプロファイルから、自動のバックグラウンド カメラ ロール アップロードを有効にできます。

- 写真を自動的にアップロードするためにコンシューマー Microsoft アカウント を安全に使用できない場合は、OneDrive アプリから手動で写真を仕事または学校アカウントにアップロードできます。 これを行うには、OneDrive アプリで、自分の仕事用または学校アカウントにサインインしている必要があります。 ボタンを選択 **+** し、 [アップロード] を **選択します**。 [カメラ ロール] の [ピクチャ] に移動して、アップロード **する>を見つける。** アップロードする写真またはビデオを選択し、[開く] ボタン **を選択** します。

[リストに戻る](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens が応答しないか、起動しない

HoloLens が起動しない場合:

- 電源ボタンの横にある LED が点灯しない場合、または短時間点滅する LED が 1 つしか表示されていない場合は[、HoloLens](hololens2-charging.md#charging-the-device)の課金が必要な場合があります。
- 電源ボタンを押すと LED が点灯するが、ディスプレイに何も表示できない場合は、デバイス のハード リセット [を行います](hololens-recovery.md#hard-reset-procedure)。

HoloLens が固定または応答しなくなる場合:

- 5 つの LED すべてがオフになるまで電源ボタンを押し、LED が応答しない場合は 15 秒間、HoloLens をオフにします。 HoloLens を起動するには、電源ボタンを再度押します。

これらの手順が機能しない場合は、HoloLens 2 デバイス[](hololens-recovery.md)または[HoloLens (第 1 世代) デバイスの復旧を試みてみます。](hololens1-recovery.md)

[リストに戻る](#list)

## <a name="low-disk-space-error"></a>"ディスク領域が少ない" エラー

次の 1 つ以上を実行して、一部の記憶域スペースを解放する必要があります。

- 未使用のスペースを削除します。 [設定]  >  **[システム**  >  **スペース]** に移動し、不要になった領域を選択して、[削除] を **選択します**。
- 配置したホログラムの一部を削除します。
- フォト アプリからいくつかの画像とビデオを削除します。
- HoloLens から一部のアプリをアンインストールします。 [すべての **アプリ] の一** 覧で、アンインストールするアプリをタップしたままにし、[ アンインストール] を **選択します**。

[リストに戻る](#list)

## <a name="calibration-fails"></a>調整が失敗する

調整はほとんどのユーザーに対して機能しますが、調整に失敗する場合があります。
  
調整エラーの考え方としては、次のようなものがあります。

- 気を散らして調整ターゲットに従わなくなって
- ダーティまたはスクラッチされたデバイス バイザーまたはデバイス バイザーが正しく配置されていない
- ダーティまたはスクラッチの眼鏡
- 特定の種類のコンタクト レンズと眼鏡 (色付きコンタクト レンズ、一部の Toric コンタクト レンズ、IR ブロッキング 眼鏡、高い眼鏡、眼鏡など)
- より顕著なメイクといくつかのまつげの拡張機能
- デバイスが目を見るのを妨げている場合は、黒い眼鏡フレームまたは太い眼鏡フレーム
- 特定の目の前部、目の状態、または狭い目、長いまつげ、アンブリータイン、ニタグマス、LASIK や他の目の治療の一部のケースなど、目の治療

調整に失敗した場合は、次の手順を試してください。

- デバイス バイザーのクリーニング
- 眼鏡のクリーニング
- デバイスバイザーを可能な限り目の近くにプッシュする
- バイザー内のオブジェクトを外に移動する (生長など)
- 部屋の照明をオンにするか、直接の光から出て行く

すべてのガイドラインに従い、調整がまだ失敗している場合は、[設定] で調整プロンプトを無効にできます。 また、 でフィードバックを送信して、お知[フィードバック Hub。](hololens-feedback.md)

画像の色または明るさ [のトラブルシューティングについては、関連情報も参照してください。](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

目の位置はシステムによって計算HoloLens 2、IPD の設定は適用されません。 

[リストに戻る](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>HoloLens が以前に他のユーザー用に設定されたため、サインインできない

デバイスを[フラッシュ モードにし、Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device)を使用してデバイスを回復できます。

[リストに戻る](#list)


## <a name="unity-isnt-working"></a>Unity が機能しない

- HoloLens [開発](/windows/mixed-reality/install-the-tools) に推奨される Unity の最新バージョンについては、ツールのインストールに関するページを参照してください。
- Unity HoloLens Technical Preview に関する既知の問題については [、HoloLens Unity フォーラムを参照してください](https://forum.unity3d.com/threads/known-issues.394627/)。

[リストに戻る](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows デバイス ポータルが正しく動作しない

- キャプチャの Live Preview 機能Mixed Reality数秒の待機時間が発生する場合があります。

- [仮想入力] ページの [仮想ジェスチャ] セクションの [ジェスチャ] コントロールと [スクロール] コントロールは機能しません。 それらを使用した場合、効果はありません。 仮想入力ページの仮想キーボードは正しく動作します。

- [設定] で開発者モードを有効にした後、スイッチが有効になっているまで数秒デバイス ポータル場合があります。

[リストに戻る](#list)

## <a name="emulator"></a>エミュレーター
### <a name="the-hololens-emulator-isnt-working"></a>HoloLens エミュレーターが動作しない

HoloLens エミュレーターに関する情報は、開発者向けドキュメントに掲載されています。  [HoloLens エミュレーターのトラブルシューティングの詳細を参照してください](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)。


- アプリ内のすべてのアプリMicrosoft Storeエミュレーターと互換性がある場合はありません。 たとえば、Young Conker と Fragments はエミュレーターで再生できません。
- エミュレーターで PC Web カメラを使用することはできません。
- アプリケーションのライブ プレビュー機能Windows デバイス ポータルエミュレーターでは機能しません。 引き続き、ビデオMixed Reality画像をキャプチャできます。

[リストに戻る](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a>キーボードを見つけたり、使用してエミュレーターに入力HoloLens 2できない

*近日公開予定*

[リストに戻る](#list)

## <a name="voice-commands-arent-working"></a>音声コマンドが機能しない

Cortana が音声コマンドに応答しない場合は、Cortana が有効になっていることを確認します。 [すべてのアプリ] の一覧で **[Cortana** Menu Notebook の設定]  >    >  **を**  >  **選択して** 変更を加えます。 話し方の詳細については [、「HoloLens で音声を使用する」を参照してください](hololens-cortana.md)。

HoloLens (第 1 世代) では、組み込みの音声認識は構成できません。 これは常にオンです。 デバイスHoloLens 2セットアップ中に音声認識と Cortana の両方を有効にするかどうかを選択できます。

音声にHoloLens 2応答していない場合は、音声認識が有効になっていることを確認します。 [スタート設定 **] [**  >  **プライバシー音声**  >  **] に**  >  **移動し**、[音声認識]**をオンにします**。

[リストに戻る](#list)

## <a name="hand-input-isnt-working"></a>手入力が機能しない

HoloLens が手を確実に表示するには、ジェスチャ フレーム内に保持する必要があります。  [Mixed Reality ホーム] には、手がいつ追跡されるのか知るフィードバックが提供されます。  フィードバックは、HoloLens のバージョンによって異なります。
- HoloLens (第 1 世代) では、視線カーソルがドットからリングに変わります
- このHoloLens 2、手がスレートに近いときに指先カーソルが表示され、スレートが離れたときに手の光線が表示されます

多くのイマーシブ アプリは、ホームに似た入力パターンMixed Realityします。  [HoloLens (第 1](hololens1-basic-usage.md#use-hololens-with-your-hands)世代) および HoloLens 2 で手入力を使用する方法[について学習します](hololens2-basic-usage.md#the-hand-tracking-frame)。

グラブを装着している場合は、一部の種類の靴下が手の追跡で動作しない点に注意してください。  一般的な例として、黒いゴムのグラブがあります。これは、赤外光を吸収する傾向があるが、深度カメラでは取り出されません。  作業にゴム製のグローブが含まれる場合は、青やグレーなどの薄い色を試することをお勧めします。  もう 1 つの例は、手の形があいまいになりがちな、大きなバッグ状のグラブです。 最適な結果を得る場合は、可能な限りフォームに合ったアダプターを使用することをお勧めします。

バイザーに指紋やスマージがある場合は、HoloLens に備え付けられているマイクロファイバー クリーニング の布を使用して、バイザーをすいすくクリーニングします。

[リストに戻る](#list)

## <a name="cant-connect-to-wi-fi"></a>デバイスに接続Wi-Fi

HoloLens を新しいネットワークに接続できない場合に試Wi-Fiします。

- 有効になっているWi-Fi確認します。 確認するには、[スタート] ジェスチャを使用し、[設定] **[**  >  **ネットワーク インターネット &amp;**  >  **Wi-Fi] の順に選択します**。 オンWi-Fi場合は、オフにしてから、もう一度オンにしてみてください。
- ルーターまたはアクセス ポイントの近くに移動します。
- 新しいルーター [Wi-Fi、HoloLens を再起動します](hololens-recovery.md)。 接続を再試行してください。
- これらのいずれも機能しない場合は、ルーターで最新のファームウェアが使用されていないことを確認します。 この情報は、製造元の Web サイトで確認できます。

[リストに戻る](#list)
## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth デバイスがペアリングされていない

[Bluetooth](hololens-connect-devices.md)デバイスのペアリングで問題が発生した場合は、次を試してください。

- [設定] **[**  >  **デバイス]** に移動し、Bluetooth がオンになっていることを確認します。 有効な場合は、オフにし、再度オンにします。
- Bluetooth デバイスが完全に充電されている、または新しいバッテリが搭載されていないことを確認します。
- それでも接続できない場合は [、HoloLens を再起動します](hololens-recovery.md)。

[リストに戻る](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB-C マイクが動作しない
一部の USB-C マイクでは、マイクとスピーカーの両方として誤って報告される *点に* 注意してください。 これは、HoloLens ではなく、マイクに関する問題です。 これらのマイクのいずれかを HoloLens に接続すると、サウンドが失われる可能性があります。 さいわい、簡単な修正があります。  

[**設定**  ->  **システム**  ->  **サウンド]** で、組み込みのスピーカー **(アナログ機能オーディオ** ドライバー) を既定のデバイス として明示的 **に設定します**。 後でマイクを取り外して再接続した場合でも、HoloLens ではこの設定を記憶する必要があります。

![USB-C マイクのトラブルシューティング](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>[設定] に使用可能として表示されているデバイスが機能しない

HoloLens (第 1 世代) では、Bluetooth オーディオ プロファイルはサポートされていません。 スピーカーやヘッドセットなどの Bluetooth オーディオ デバイスは、HoloLens の設定で使用できると表示される場合がありますが、サポートされていません。

HoloLens 2、ステレオ再生用の Bluetooth A2DP オーディオ プロファイルがサポートされます。 Bluetooth 周辺機器からのマイク キャプチャを有効にする Bluetooth ハンズ フリー プロファイルは、HoloLens 2。

Bluetooth デバイスの使用で問題が発生した場合は、それがサポートされているデバイスである必要があります。 サポートされているデバイスは次のとおりです。

- 英語の QWERTY Bluetooth キーボード (ホログラフィック キーボードを使用する任意の場所で使用できます)。
- Bluetooth マウス。
- [HoloLens クッカー](hololens1-clicker.md)。

他の Bluetooth HID デバイスと GATT デバイスを HoloLens と組み合わせて使用できます。 ただし、デバイスを実際に使用するには、Microsoft Storeアプリをインストールする必要がある場合があります。

[リストに戻る](#list)
