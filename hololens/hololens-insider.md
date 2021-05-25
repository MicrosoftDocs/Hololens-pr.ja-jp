---
title: Microsoft HoloLens の Insider Preview
description: Insider ビルドの使用を開始し、HoloLens の次の主要なオペレーティング システム更新プログラムに関する貴重なフィードバックを提供する方法について説明します。
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
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 8545b5f23dc81c194b68ea8b40feb83e525dfdf7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397823"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens の Insider Preview

HoloLens の最新の Insider Preview ビルドへようこそ。 HoloLens [の次](hololens-insider.md#start-receiving-insider-builds) の主要なオペレーティング システム更新プログラムの開始と貴重なフィードバックの提供は簡単です。

## <a name="windows-insider-release-notes"></a>Windows Insider リリース ノート

Windows Insider に新しい機能を再び提供し始め、楽しみに思います。 新しいビルドは、最新の更新プログラムのために Dev および Beta チャネルにフライトします。 このページは引き続き更新されます。このページでは、新しいビルドの機能と更新プログラムWindows Insiderします。 これらの更新プログラムを実際に組み合わせ、準備を整えます。 

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive for work または school Camera Roll upload

*ビルド 20346.1402 で導入*

HoloLens 2 設定アプリに新しい機能が追加されました。これにより、お客様はデバイスの Pictures > Camera Roll フォルダーから対応する OneDrive for work または school フォルダーに Mixed Reality の写真とビデオを自動的にアップロードできます。 この機能は、HoloLens 2 上の [OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) アプリ内の機能のギャップに対応します。これは、(仕事または学校アカウントではなく) 顧客の個人の Microsoft アカウント へのカメラ ロールの自動アップロードのみをサポートします。

**動作のしくみ**

- [Settings **> System > Mixed Reality カメラ]** にアクセスして、"カメラのアップロード" を有効にします。
- この機能を [オン] の位置に設定すると、デバイスにキャプチャされた Mixed Reality の写真またはビデオは、OneDrive for work または School アカウントの Pictures > Camera Roll フォルダーにアップロードするために自動的にキューに登録されます。
    >[!NOTE]
    >この機能を有効にする前にキャプチャされた写真とビデオは、アップロード用にキューに登録されるのではなく、引き続き手動でアップロードする必要があります。
- [設定] ページのステータス メッセージに、アップロード保留中のファイルの数が表示されます (または、保留中のすべてのファイルがアップロードされると "OneDrive が最新の状態" と表示されます)。
- 帯域幅が気になる場合や、何らかの理由でアップロードを "一時停止" したい場合は、機能を [オフ] の位置に **切り替** えます。 この機能を一時的に無効にすると、新しいファイルをカメラのロールフォルダーに追加してもアップロードキューのサイズが増加し続けますが、この機能を再度有効にするまでファイルはアップロードされません。
- 最新のファイルが最初にアップロードされます (後入れ先出し)。
- OneDrive アカウントに問題がある場合 (パスワードの変更後など)、[設定] ページに [ **今すぐ修正** ] ボタンが表示されます。
- ファイルの最大サイズはありませんが、大きなファイルはアップロードに時間がかかることに注意してください (アップロードの帯域幅が制限されている場合は特に)。 大きなファイルのアップロード中に [一時停止] または [アップロード] をオフにすると、アップロードがすぐにキャンセルされます。 この機能を再度有効にすると、アップロードが再開されます。ファイルは失われませんが、部分的なアップロードは破棄されます。

**既知の問題と注意事項**

- この設定には、現在の使用帯域幅に基づく制限が組み込まれていません。 別のシナリオの帯域幅を最大化する必要がある場合は、設定を手動でオフにします。 アップロードは一時停止されますが、この機能は、新たに追加されたファイルのカメラロールへの監視を継続します。 続行する準備ができたら、アップロードを再度有効にしてください。
- この機能は、デバイス上のユーザーアカウントごとに有効にする必要があります。また、デバイスに現在サインインしているユーザーのファイルのみをアクティブにアップロードできます。
- [設定] ページのアップロード回数をリアルタイムで監視しているときに写真やビデオを撮影している場合は、現在のファイルのアップロードが完了するまで保留中のファイルの数が変更されないことに注意してください。
- デバイスがスリープ状態になった場合、または電源がオフになっている場合、アップロードは一時停止します。 保留中のアップロードが完了したことを確認するには、[設定] ページで "OneDrive が最新の状態" になっているか、 **電源 & スリープ** 設定を調整するまで、デバイスをアクティブに使用します。

## <a name="start-receiving-insider-builds"></a>Insider ビルドの受信を開始します
> [!NOTE]
> 最近更新したことがない場合は、デバイスを再起動して状態を更新し、最新のビルドを取得してください。
> - "デバイスの再起動" 音声コマンドは正常に機能します。 
> - [設定]/[Windows Insider Program] で [再起動] ボタンを選択することもできます。
>
> 発生した可能性があるバック エンドにバグがありました。これにより、追跡が戻されます。

デバイス上HoloLens 2 [設定の **更新]** に移動し&セキュリティ  >  **Windows Insider Program]** を選択  >  **概要。** アカウントとして登録するために使用したアカウントをリンクWindows Insider。
Windows Insider は現在、チャネルに移行しています。 高速 **リング** は開発チャネルになり、低速リングはベータ チャネル になり、リリース プレビュー リングはリリースプレビュー チャネル **になります**。 マッピングは次のように表示されます。Windows Insider チャネルの説明 については、「Windows ブログでの Windows Insider チャネルの紹介」 ![ ](images/WindowsInsiderChannels.png) を参照してください。 [](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)
次に、 **[Windows のアクティブ** な開発] を選択し、開発チャネルを受け取るのとビルドをベータ チャネル、プログラムの用語を確認します。
[Confirm **> Restart Now]を選択して** 完了します。 デバイスが再起動したら、[設定] > [更新&セキュリティ] > **更新** プログラムを確認して最新のビルドを取得します。
### <a name="update-error-0x80070490-work-around"></a>更新エラー 0x80070490回避
Dev または Beta チャネルで更新0x80070490更新エラーが発生した場合は、次の短期的な回避を試してください。 インサイダー チャネルを移動し、更新プログラムを選択してから、Insider チャネルを戻す必要があります。
#### <a name="stage-one---release-preview"></a>ステージ 1 - リリース プレビュー
1.  [設定] 、 [セキュリティ&更新] 、 [Windows Insider Program、 [リリース プレビュー チャネル **] を選択します**。
2.  設定、更新プログラム&セキュリティ、Windows Update、 **更新プログラムの確認**。 更新後、ステージ 2 に進む。
#### <a name="stage-two---dev-channel"></a>ステージ 2 - 開発チャネル
1. [設定] 、 [セキュリティ&更新Windows Insider Program、 [開発チャネル] **を選択します**。
2. 設定、更新プログラム&セキュリティ、Windows Update、 **更新プログラムの確認**。
## <a name="ffu-download-and-flash-directions"></a>FFU のダウンロードとフラッシュの方向
フライト署名済み ffu を使用してテストするには、フライト署名済み ffu を点滅させる前にデバイスのロックを解除する必要があります。
1. PC の場合:
    1. から PC に ffu をダウンロード [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) します。
    
    1. Microsoft Store から ARC (Advanced Recovery コンパニオン) をインストール [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) します。
    
1. HoloLens-フライトのロック解除: [**設定** の  >  **更新] & セキュリティ**]  >  [**Windows Insider program** ] の順に選択し、サインアップして、デバイスを再起動します。
1. Flash FFU-atc を使用して、デジタル署名された FFU をフラッシュできるようになりました。
### <a name="provide-feedback-and-report-issues"></a>フィードバックの提供と問題の報告
HoloLens で [フィードバックハブアプリ](hololens-feedback.md) を使用して、フィードバックを提供し、問題を報告してください。 フィードバックハブを使用すると、エンジニアが迅速に問題をデバッグして解決できるように、必要な診断情報がすべて含まれるようになります。  HoloLens の中国語と日本語バージョンの問題は、同じように報告する必要があります。
> [!NOTE]
> フィードバックハブがドキュメントフォルダーにアクセスするかどうかを確認するメッセージが表示されることを確認します (メッセージが表示されたら [ **はい]** を選択します)。
## <a name="note-for-developers"></a>開発者向けのメモ
HoloLens の Insider ビルドを使用してアプリケーションを開発することをお勧めします。  ご利用を開始するには、 [HoloLens 開発者ドキュメント](https://developer.microsoft.com/windows/mixed-reality/development) を参照してください。 これらの命令は、HoloLens の Insider ビルドでも機能します。  既に HoloLens 開発に使用している Unity と Visual Studio の同じビルドを使用できます。
## <a name="stop-receiving-insider-builds"></a>Insider ビルドの受信を停止します
Windows Holographic の Insider ビルドを受信する必要がなくなった場合は、HoloLens が運用ビルドを実行しているときにオプトアウトできます。または、Advanced Recovery コンパニオンを使用してデバイスを [回復](hololens-recovery.md) し、デバイスを Insider バージョン以外の windows Holographic に回復することもできます。
> [!CAUTION]
> 新しいプレビュービルドを手動で再インストールした後に、Insider Preview ビルドから登録を解除したユーザーがブルースクリーンを使用するという既知の問題があります。 その後、デバイスを手動で回復する必要があります。 影響を受け取る可能性がある場合の詳細については、この既知の問題に関するページを [参照してください](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)。
HoloLens で実稼働ビルドが実行されていないことを確認するには:
1. [システムの **設定] > [>について**] に移動し、ビルド番号を見つける。
1. [実稼働ビルド番号については、リリース ノートを参照してください](hololens-release-notes.md)。
Insider ビルドをオプトアウトするには:
1. 実稼働ビルドを実行している HoloLens で、[設定] > **[Update & Security**> Windows Insider Program] に移動し、[Stop Insider builds]/(Insider ビルドの停止)を選択 **します**。
1. 指示に従ってデバイスをオプトアウトします。
