---
title: HoloLensデバイスのトラブルシューティング
description: デバイスに関する問題やトラブルシューティングの手法をHoloLens最も一般的な解決策を最新の情報にしてください。
author: evmill
ms.author: v-evmill
ms.date: 10/7/2021
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: ranjibb
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: 問題, バグ, トラブルシューティング, 修正, ヘルプ, サポート, HoloLens, エミュレーター
ms.openlocfilehash: ceb6f2670b15f46d17a0cb36f6602ae3d4e3ec1d
ms.sourcegitcommit: 8a3f925d2bda13c095b35f14d80afdd876aa859c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2021
ms.locfileid: "129800540"
---
# <a name="device-troubleshooting"></a>デバイスのトラブルシューティング

この記事では、一般的な問題を解決するHoloLens説明します。

>[!IMPORTANT]
> トラブルシューティングの手順を開始する前に、可能であれば、デバイスのバッテリ容量が **20 - 40%** 残っていることを確認してください。 電源 ボタンの下 にある[バッテリ インジケーター ライト](hololens2-setup.md#lights-that-indicate-the-battery-level)により、デバイスにログインせずにバッテリ容量を簡単に確認できます。

<a id="list"></a>

**既知の問題**
- [電源が 18% に入るたび、デバイスが突然自動的にシャットダウンする](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- [OneDriveUWP アプリがユーザーに対Azure ADしない](#onedrive-uwp-app-doesnt-work-for-azure-ad-users)
- [Remote Assist 20 分後にビデオがフリーズする](#remote-assist-video-freezes-after-20-minutes)
- [自動ログインでログインを求める](#auto-login-asks-for-log-in)
- [Microsoft Edge起動に失敗する](#microsoft-edge-fails-to-launch)
- [キーボードが特殊文字に切り替えない](#keyboard-doesnt-switch-to-special-characters)
- [ロックされたファイルをダウンロードしてもエラーが表示されません](#downloading-locked-files-doesnt-error)
- [デバイス ポータルファイルのアップロード/ダウンロードがアウトした場合](#device-portal-file-uploaddownload-times-out)
- [Insider ビルドでフラッシュされたデバイスで Insider プレビューから登録を解除した後のブルー スクリーン](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive画像が自動的にアップロードされません](#onedrive-doesnt-automatically-upload-pictures)

**全般**
- [HoloLens応答しないか、起動しない](#hololens-is-unresponsive-or-wont-start)
- ["ディスク領域が少ない" エラー](#low-disk-space-error)
- [調整に失敗する](#calibration-fails)
- [自分のアカウントが他のユーザー HoloLens設定されたため、サインインできない](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity が機能しない](#unity-isnt-working)
- [Windowsデバイス ポータルが正しく動作しない](#windows-device-portal-isnt-working-correctly)
- [このHoloLens Emulator動作していません](#the-hololens-emulator-isnt-working)

**入力**
- [音声コマンドが機能しない](#voice-commands-arent-working)
- [手入力が機能しない](#hand-input-isnt-working)

**接続**
- [Wi-Fi に接続できない](#cant-connect-to-wi-fi)

**外部デバイス** 
- [Bluetoothデバイスがペアリングされていない](#bluetooth-devices-arent-pairing)
- [USB-C マイクが動作しない](#usb-c-microphone-isnt-working)
- [[デバイス] で使用可能として一設定デバイスが機能しない](#devices-listed-as-available-in-settings-dont-work)

## <a name="every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically"></a>電源が 18% に入るたび、デバイスが突然自動的にシャットダウンする

デバイスが 18% のバッテリに達すると、予期せずシャットダウンする既知の問題があります。 これは、ハードウェアやバッテリの問題ではなく、ソフトウェアの問題です。そのため、デバイスを交換することはおやめください。 問題がこのバグと一致する場合は、次のコマンドを実行してください。

1. デバイスでオプションの診断が有効になっているか確認する
1. 問題を再現する
1. 問題の [フィードバック Hub](hololens-feedback.md) する
1. フィードバックの問題の URL を共有する
1. [サポートに問い合わせ](https://aka.ms/hololenssupport)

[一覧に戻る](#list)

## <a name="onedrive-uwp-app-doesnt-work-for-azure-ad-users"></a>OneDriveUWP アプリがユーザーに対Azure ADしない

Azure AD アカウントを使用して OneDrive For Business を使用している場合は、アプリで受信トレイにサインインするときにエラーが発生OneDriveがあります。 アプリからアプリにサインインできないOneDriveカメラ アプリによってキャプチャされた画像とビデオの自動アップロードには影響を与え "されません"。 ファイルは引き続きクラウド ストレージのOneDrive for Businessできます。 チームOneDriveチームHoloLens、この問題に取り組み中です。

### <a name="workarounds"></a>回避策

前提条件: お客様は Microsoft Edge使用できます。デバイス OS は Windows Holographic、21H1 ビルド以降に更新されます。

この問題が発生している場合は、次のいずれかを試してください。

- ユーザーは、OneDrive For Business から直接アクセスMicrosoft Edge、ブラウザーから Web サイトのファイルを操作できます。
- ユーザーは、OneDrive PWAからダウンロードHoloLensアプリをインストールMicrosoft Edge。 これにより、ユーザーはデバイス上のファイルを再び表示および管理できます。 アプリをインストールするには、[次の手順に従ってOneDrive PWAアプリをインストールHoloLens。](holographic-store-apps.md#install-microsoft-onedrive-pwa-app)

[一覧に戻る](#list)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Remote Assist 20 分後にビデオがフリーズする

> [!NOTE]
> この問題に対する修正プログラムRemote Assist新しいバージョンのアプリケーションがあります。 この [問題をRemote Assist](holographic-store-apps.md#update-apps) を最新バージョンに更新してください。

> [!NOTE]
> この既知の問題の重大度により、Holographic バージョン 21H1 のWindows一時停止しました。 21H1 ビルドが再び利用可能になります。そのため、デバイスが最新の 21H1 ビルドに再び更新される可能性があります。

[Windows Holographic バージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1)の最新リリースでは、Remote Assist の一部のユーザーが 20 分を超える通話中にビデオの凍結を経験しました。 これは既知の **問題です**。

### <a name="workarounds"></a>回避策

新しいビルドに更新できないRemote Assist、次の問題を回避してください。

#### <a name="restart-in-between-calls"></a>呼び出しの間に を再起動する

呼び出しが 20 分以上続き、この問題が発生している場合は、デバイスを再起動してみてください。 呼び出しの間にRemote Assistを再起動すると、デバイスが更新され、良好な状態に戻されます。

[Windows Holographic バージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1)でデバイスをすばやく再起動するには、スタート メニューを開き、ユーザー アイコンを選択し、[再起動] を **選択します**。

[一覧に戻る](#list)

## <a name="auto-login-asks-for-log-in"></a>自動ログインでログインを求める

HoloLens 2デバイスは、設定 アカウントサインイン オプション **->** を使用して自動的にログインするように構成できます。[必須] で値を [Never] に設定  ->    ->  **します**。  一部のユーザーは、機能更新プログラムなど、大幅に大きな更新プログラムを使用してデバイスを更新するときに、デバイスに再度ログインする必要があります。 これは既知の **問題です**。

これが発生する可能性がある例を次に示します。

- Windows Holographic バージョン 2004 (ビルド 19041.xxxx) から Windows Holographic バージョン 21H1 (ビルド 20346.xxxx) へのデバイスの更新
- 同じメジャー ビルド (Windows Holographic バージョン 2004 から Windows Holographic バージョン 20H2 など) で大規模な更新を行うデバイスの更新
- ファクトリ イメージから最新のイメージへのデバイスの更新

これは、次の場合には発生しません。

- 毎月のサービス更新プログラムを受け取るデバイス

メソッドの回避:

- PIN、パスワード、あやめ、Web 認証、FIDO2 キーなどのサインイン方法。
- デバイス PIN を記憶できない場合、その他の認証方法を使用できない場合、ユーザーは手動 [の再スラッシュ モードを使用できます](hololens-recovery.md#manual-procedure)。

[一覧に戻る](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge起動に失敗する

> [!NOTE]
> この問題は、当初、出荷バージョンのバージョンを念頭Microsoft Edgeして作成されました。 この問題は、 の新しいバージョン[で解決Microsoft Edge。](hololens-new-edge.md) そうではない場合は、フィードバックを送信してください。

一部のお客様から、起動に失敗する問題Microsoft Edge報告されています。 これらのお客様の場合、この問題は再起動を通じて解決され、Windows更新プログラムでは解決されません。 この問題が発生し[、Windows](hololens-updates.md#manually-check-for-updates)が最新である場合は、次のカテゴリとサブカテゴリを持つ フィードバック Hub Windows アプリからの[](hololens-feedback.md)バグを報告してください:> > Update のダウンロード、インストール、および構成。

これまでに問題を根本原因にできなかったので、既知の回避策はありません。 レポートを使用してバグをフィードバック Hub調査に役立ちます。 これは既知の **問題です**。

[一覧に戻る](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>キーボードが特殊文字に切り替えない

OOBE 中に問題が発生します。ユーザーが仕事用または学校アカウントを選択し、パスワードを入力すると、&123 ボタンをタップしてキーボードの特殊文字に切り替えようとしても、特殊文字に変わりません。 これは既知の **問題です**。

回避方法:

- キーボードを閉じ、テキスト フィールドをタップして再度開きます。
- パスワードを誤って入力します。 次回キーボードを再起動すると、期待した通り動作します。
- Web 認証を行い、キーボードを閉じて、別の **デバイスから [サインイン] を選択します**。
- 数値のみを入力する場合、ユーザーは特定のキーを長押しして展開されたメニューを開くことができます。
- USB キーボードを使用する。

これは、次の場合には影響を与え "ない" です。

- 個人アカウントの使用を選択したユーザー。

[一覧に戻る](#list)

## <a name="downloading-locked-files-doesnt-error"></a>ロックされたファイルをダウンロードしてもエラーが発生しない

> [!NOTE]
> これは、Holographic バージョン[21H1 Windows 2021](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)年 7 月の更新プログラム で修正された既知の問題です。 

Holographic の以前Windowsでは、ロックされたファイルをダウンロードしようとすると、結果は HTTP エラー ページになります。 Windows Holographic バージョン 21H1 更新プログラムでは、ロックされたファイルをダウンロードしようとしても、何も表示されません。ファイルはダウンロードされません。エラーはありません。

[一覧に戻る](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>デバイス ポータルファイルのアップロード/ダウンロードがアウトした場合
> [!NOTE]
> これは、Holographic バージョン[21H1 Windows 2021](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)年 7 月の更新プログラム で修正された既知の問題です。  回避策の一環として SSL 接続を以前に無効にした場合は、再び有効にすることを強くお勧めします。

一部のお客様は、ファイルのアップロードまたはダウンロードを試みる際に、操作がハングし、その後に時間が切れているか、完了しない可能性があります。 これは、'ファイル ロック['](#downloading-locked-files-doesnt-error)の既知の問題とは別です。これは、Windows Holographic、バージョン 2004、20H2、および 21H1 の市場内ビルドに影響します。 この問題は、デバイス ポータル による特定の要求の処理のバグが原因で根本原因であり、既定の https を使用すると最も一貫してヒットします。

### <a name="workaround"></a>回避策

この回避策は、Wi-Fi と UsbNcm に等しく適用され、"SSL 接続" で "必須" オプションを無効にします。 これを行うには、[システム] の デバイス ポータル **に移動** し、[基本設定] **ページを選択** します。 [デバイス セキュリティ **] セクションで** 、[SSL 接続] **を探し、[** 必須] を無効にするにはオフ **にします**。

その後、ユーザーは http:// に移動する必要 https:// (IP アドレス) ではなく、ファイルのアップロードやダウンロードのような機能が機能します。

[一覧に戻る](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Insider ビルドでフラッシュされたデバイスで Insider プレビューから登録を解除した後のブルー スクリーン

これは、Insider プレビュー ビルドに含まれるユーザーに影響を与え、新しい Insider プレビュー ビルドで HoloLens 2 を再フラッシュした後、Insider プログラムから登録を解除したユーザーに影響を与える問題です。 これは既知の **問題です**。

これは、次の場合には影響を与え "ない" です。

- Windows Insider に登録されていないユーザー
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

- ビジネスで実行可能な場合は、コンシューマー向け Microsoft アカウントでカメラの自動アップロードがサポートされます。 自分のアカウントまたは学校アカウントMicrosoft アカウント、自分のアカウントにサインインできます (OneDrive アプリはデュアル サインインをサポートしています)。 アプリ内Microsoft アカウントプロファイルからOneDrive、バックグラウンド カメラのロール アップロードを有効にできます。

- 写真を自動的にアップロードするためにコンシューマー Microsoft アカウント を安全に使用できない場合は、OneDrive アプリから仕事用または学校アカウントに写真を手動でアップロードできます。 これを行うには、アプリで自分の学校または学校アカウントにサインインOneDriveしてください。 ボタンを選択 **+** し、 [] を **アップロード。** [カメラ ロール] の [ピクチャ] に移動して、アップロード **する>を見つける。** アップロードする写真またはビデオを選択し、[開く] ボタン **を選択** します。

[一覧に戻る](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens応答しないか、起動しない

お使HoloLensが開始しない場合:

- 電源ボタンの横にある LED が点灯しない場合、または短時間点滅する LED が 1 つしか表示されていない場合は、電源[HoloLens。](hololens2-charging.md#charging-the-device)
- 電源ボタンを押すと LED が点灯するが、ディスプレイに何も表示できない場合は、デバイス のハード リセット [を行います](hololens-recovery.md#hard-reset-procedure)。

お使HoloLensが固定または応答しなくなる場合:

- 電源ボタンHoloLens 5 つの LED すべてがオフになるまで、または LED が応答しない場合は 15 秒間、電源ボタンを押して電源をオフにします。 アプリケーションを起動するにはHoloLensもう一度電源ボタンを押します。

これらの手順が機能しない場合は、HoloLens 2 ([](hololens-recovery.md)第 1 世代) HoloLensデバイスの復旧を[試みてみます。](hololens1-recovery.md)

[一覧に戻る](#list)

## <a name="low-disk-space-error"></a>"ディスク領域が少ない" エラー

次の 1 つ以上を実行して、一部の記憶域スペースを解放する必要があります。

- 未使用のスペースを削除します。 [システム **設定** に移動し、不要になったスペースを選択して、[ 削除  >    >  ] を **選択します**。
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
- 特定の目の前部、目の状態、または狭い目、長いまつげ、アンブリータイン、nystagmus、LASIK や他の目の治療の場合など、目の治療

調整に失敗した場合は、次の手順を試してください。

- デバイス バイザーのクリーニング
- 眼鏡のクリーニング
- デバイスバイザーを可能な限り目の近くにプッシュする
- バイザー内のオブジェクトを外に移動する (生長など)
- 部屋の照明をオンにするか、直接の光から出て行く

すべてのガイドラインに従い、調整がまだ失敗している場合は、次の手順で調整プロンプトを設定。 また、 でフィードバックを提出して、お知[フィードバック Hub。](hololens-feedback.md)

画像の色または明るさ [のトラブルシューティングについては、関連情報も参照してください。](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

目の位置はシステムによって計算HoloLens 2、IPD の設定は適用されません。 

[一覧に戻る](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>自分のアカウントが他のユーザー HoloLens設定されたため、サインインできない

デバイスを[フラッシュ モードにし、Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device)を使用してデバイスを回復できます。

[一覧に戻る](#list)


## <a name="unity-isnt-working"></a>Unity が動作しない

- HoloLens 開発に推奨される Unity の最新バージョン用の[ツールをインストール](/windows/mixed-reality/install-the-tools)することをお勧めします。
- unity HoloLens Technical Preview の既知の問題については、 [HoloLens unity フォーラム](https://forum.unity3d.com/threads/known-issues.394627/)をご覧ください。

[一覧に戻る](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windowsデバイスポータルが正しく動作していません

- Mixed Reality キャプチャのライブプレビュー機能は、数秒の待機時間が発生する場合があります。

- [仮想入力] ページで、[仮想ジェスチャ] セクションのジェスチャとスクロールコントロールが機能していません。 使用すると、効果はありません。 仮想入力ページの仮想キーボードが正常に動作します。

- 設定で開発者モードを有効にした後、デバイスポータルをオンにするスイッチが有効になるまで数秒かかることがあります。

[一覧に戻る](#list)

## <a name="the-hololens-emulator-isnt-working"></a>HoloLens Emulator が機能していません

HoloLens エミュレーターに関する情報は、開発者向けのドキュメントにあります。  [HoloLens エミュレーターのトラブルシューティングの](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)詳細については、こちらを参照してください。


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
