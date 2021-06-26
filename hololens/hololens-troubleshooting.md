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
# <a name="device-troubleshooting"></a><span data-ttu-id="93e14-104">デバイスのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="93e14-104">Device Troubleshooting</span></span>

<span data-ttu-id="93e14-105">この記事では、HoloLens のいくつかの一般的な問題を解決する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="93e14-105">This article describes how to resolve several common HoloLens issues.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="93e14-106">トラブルシューティング手順を開始する前に、可能であれば、デバイスにバッテリ容量の **20 ~ 40%** が課金されます。</span><span class="sxs-lookup"><span data-stu-id="93e14-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="93e14-107">電源 [ボタンの下](hololens2-setup.md#lights-that-indicate-the-battery-level) にあるバッテリ インジケーター ライトは、デバイスにログインせずにバッテリ容量を簡単に確認する方法です。</span><span class="sxs-lookup"><span data-stu-id="93e14-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<a id="list"></a>

<span data-ttu-id="93e14-108">**既知の問題**</span><span class="sxs-lookup"><span data-stu-id="93e14-108">**Known Issues**</span></span>
- [<span data-ttu-id="93e14-109">Remote Assist 20 分後にビデオがフリーズする</span><span class="sxs-lookup"><span data-stu-id="93e14-109">Remote Assist video freezes after 20 minutes</span></span>](#remote-assist-video-freezes-after-20-minutes)
- [<span data-ttu-id="93e14-110">自動ログインでログインを求める</span><span class="sxs-lookup"><span data-stu-id="93e14-110">Auto-login asks for log-in</span></span>](#auto-login-asks-for-log-in)
- [<span data-ttu-id="93e14-111">Microsoft Edge起動に失敗する</span><span class="sxs-lookup"><span data-stu-id="93e14-111">Microsoft Edge fails to launch</span></span>](#microsoft-edge-fails-to-launch)
- [<span data-ttu-id="93e14-112">キーボードが特殊文字に切り替えない</span><span class="sxs-lookup"><span data-stu-id="93e14-112">Keyboard doesn't switch to special characters</span></span>](#keyboard-doesnt-switch-to-special-characters)
- [<span data-ttu-id="93e14-113">ロックされたファイルをダウンロードしてもエラーが表示されません</span><span class="sxs-lookup"><span data-stu-id="93e14-113">Downloading locked files doesn't show error</span></span>](#downloading-locked-files-doesnt-error)
- [<span data-ttu-id="93e14-114">デバイス ポータルファイルのアップロード/ダウンロードがアウトした場合</span><span class="sxs-lookup"><span data-stu-id="93e14-114">Device Portal file upload/download times out</span></span>](#device-portal-file-uploaddownload-times-out)
- [<span data-ttu-id="93e14-115">Insider ビルドでフラッシュされたデバイスで Insider プレビューから登録を解除した後のブルー スクリーン</span><span class="sxs-lookup"><span data-stu-id="93e14-115">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [<span data-ttu-id="93e14-116">OneDrive で画像が自動的にアップロードされません</span><span class="sxs-lookup"><span data-stu-id="93e14-116">OneDrive doesn't automatically upload pictures</span></span>](#onedrive-doesnt-automatically-upload-pictures)

<span data-ttu-id="93e14-117">**全般**</span><span class="sxs-lookup"><span data-stu-id="93e14-117">**General**</span></span>
- [<span data-ttu-id="93e14-118">HoloLens が応答しないか、起動しない</span><span class="sxs-lookup"><span data-stu-id="93e14-118">HoloLens is unresponsive or won't start</span></span>](#hololens-is-unresponsive-or-wont-start)
- [<span data-ttu-id="93e14-119">"ディスク領域が少ない" エラー</span><span class="sxs-lookup"><span data-stu-id="93e14-119">"Low Disk Space" error</span></span>](#low-disk-space-error)
- [<span data-ttu-id="93e14-120">調整に失敗する</span><span class="sxs-lookup"><span data-stu-id="93e14-120">Calibration Fails</span></span>](#calibration-fails)
- [<span data-ttu-id="93e14-121">HoloLens が以前に他のユーザー用に設定されたため、サインインできない</span><span class="sxs-lookup"><span data-stu-id="93e14-121">Can't sign in because my HoloLens was previously set up for someone else</span></span>](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [<span data-ttu-id="93e14-122">Unity が機能しない</span><span class="sxs-lookup"><span data-stu-id="93e14-122">Unity isn't working</span></span>](#unity-isnt-working)
- [<span data-ttu-id="93e14-123">Windows デバイス ポータルが正しく動作しない</span><span class="sxs-lookup"><span data-stu-id="93e14-123">Windows Device Portal isn't working correctly</span></span>](#windows-device-portal-isnt-working-correctly)
- [<span data-ttu-id="93e14-124">HoloLens エミュレーターが動作しない</span><span class="sxs-lookup"><span data-stu-id="93e14-124">The HoloLens Emulator isn't working</span></span>](#the-hololens-emulator-isnt-working)

<span data-ttu-id="93e14-125">**入力**</span><span class="sxs-lookup"><span data-stu-id="93e14-125">**Input**</span></span>
- [<span data-ttu-id="93e14-126">音声コマンドが機能しない</span><span class="sxs-lookup"><span data-stu-id="93e14-126">Voice commands aren't working</span></span>](#voice-commands-arent-working)
- [<span data-ttu-id="93e14-127">手入力が機能しない</span><span class="sxs-lookup"><span data-stu-id="93e14-127">Hand input isn't working</span></span>](#hand-input-isnt-working)

<span data-ttu-id="93e14-128">**接続**</span><span class="sxs-lookup"><span data-stu-id="93e14-128">**Connectivity**</span></span>
- [<span data-ttu-id="93e14-129">Wi-Fi に接続できない</span><span class="sxs-lookup"><span data-stu-id="93e14-129">Can't connect to Wi-Fi</span></span>](#cant-connect-to-wi-fi)

<span data-ttu-id="93e14-130">**外部デバイス**</span><span class="sxs-lookup"><span data-stu-id="93e14-130">**External Devices**</span></span> 
- [<span data-ttu-id="93e14-131">Bluetooth デバイスがペアリングされていない</span><span class="sxs-lookup"><span data-stu-id="93e14-131">Bluetooth devices aren't pairing</span></span>](#bluetooth-devices-arent-pairing)
- [<span data-ttu-id="93e14-132">USB-C マイクが動作しない</span><span class="sxs-lookup"><span data-stu-id="93e14-132">USB-C Microphone isn't working</span></span>](#usb-c-microphone-isnt-working)
- <span data-ttu-id="93e14-133">[[設定] に使用可能として表示されているデバイスが機能しない](#devices-listed-as-available-in-settings-dont-work)</span><span class="sxs-lookup"><span data-stu-id="93e14-133">[Devices listed as available in Settings don't work](#devices-listed-as-available-in-settings-dont-work)</span></span>

## <a name="remote-assist-video-freezes-after-20-minutes"></a><span data-ttu-id="93e14-134">Remote Assist 20 分後にビデオがフリーズする</span><span class="sxs-lookup"><span data-stu-id="93e14-134">Remote Assist video freezes after 20 minutes</span></span>

> [!NOTE]
> <span data-ttu-id="93e14-135">この既知の問題の重大度により、現在、Windows Holographic バージョン 21H1 の可用性が一時停止されています。</span><span class="sxs-lookup"><span data-stu-id="93e14-135">Due to this Known Issue's severity we have currently paused the availability of Windows Holographic, version 21H1.</span></span> <span data-ttu-id="93e14-136">引き続きデバイスを 21H1 に更新する場合は、ページの上部にあるリリース ノートの [手順を参照してください。](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="93e14-136">If you would like to still update your devices to 21H1, please refer to [the instructions in our release notes at the top of the page.](hololens-release-notes.md)</span></span>

<span data-ttu-id="93e14-137">[Windows Holographic バージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1)の最新リリースでは、Remote Assist の一部のユーザーは、20 分を超える通話中にビデオの凍結を経験しました。</span><span class="sxs-lookup"><span data-stu-id="93e14-137">On the latest release of [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), some users of Remote Assist have experienced video freezing during calls over 20 minutes.</span></span> <span data-ttu-id="93e14-138">これは既知の **問題です**。</span><span class="sxs-lookup"><span data-stu-id="93e14-138">This is a **known issue**.</span></span>

### <a name="workarounds"></a><span data-ttu-id="93e14-139">回避策</span><span class="sxs-lookup"><span data-stu-id="93e14-139">Workarounds</span></span>

#### <a name="restart-in-between-calls"></a><span data-ttu-id="93e14-140">呼び出しの間に を再起動する</span><span class="sxs-lookup"><span data-stu-id="93e14-140">Restart in between calls</span></span>

<span data-ttu-id="93e14-141">通話が 20 分以上続き、この問題が発生している場合は、デバイスを再起動してみてください。</span><span class="sxs-lookup"><span data-stu-id="93e14-141">If your calls are going over a length of 20 minutes and you are experiencing this issue, try rebooting your device.</span></span> <span data-ttu-id="93e14-142">呼び出しの間にRemote Assistを再起動すると、デバイスが更新され、良好な状態に戻されます。</span><span class="sxs-lookup"><span data-stu-id="93e14-142">Rebooting your device between Remote Assist calls will refresh your device and put it back into a good state.</span></span>

<span data-ttu-id="93e14-143">[Windows Holographic バージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1)でデバイスをすばやく再起動するには、スタート メニューを開き、ユーザー アイコンを選択し、[再起動] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="93e14-143">To quickly restart a device on [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) open the start menu, and select the user icon, then select **Restart**.</span></span>

#### <a name="revert-to-an-older-build"></a><span data-ttu-id="93e14-144">古いビルドに戻す</span><span class="sxs-lookup"><span data-stu-id="93e14-144">Revert to an older build</span></span>

<span data-ttu-id="93e14-145">一部のお客様は、以前の OS バージョンに戻す際に、この問題が発生しなくなったと感じ取っています。</span><span class="sxs-lookup"><span data-stu-id="93e14-145">Some customers have found that when reverting to an earlier OS version they no longer experience this issue.</span></span> <span data-ttu-id="93e14-146">デバイスでこの問題が発生している場合は、次の手順を試してください。</span><span class="sxs-lookup"><span data-stu-id="93e14-146">If you have found that your devices are experiencing this issue, try these steps:</span></span>


<span data-ttu-id="93e14-147">回避策:</span><span class="sxs-lookup"><span data-stu-id="93e14-147">Workarounds:</span></span>

- <span data-ttu-id="93e14-148">ビジネスで実行可能な場合は、コンシューマー向け Microsoft アカウントでカメラの自動アップロードがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="93e14-148">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="93e14-149">自分のアカウントまたは学校アカウントMicrosoft アカウント、自分のアカウントにサインインできます (OneDrive アプリではデュアル サインインがサポートされています)。</span><span class="sxs-lookup"><span data-stu-id="93e14-149">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="93e14-150">OneDrive 内Microsoft アカウントプロファイルから、自動のバックグラウンド カメラ ロール アップロードを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="93e14-150">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="93e14-151">写真を自動的にアップロードするためにコンシューマー Microsoft アカウント を安全に使用できない場合は、OneDrive アプリから手動で写真を仕事または学校アカウントにアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="93e14-151">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="93e14-152">これを行うには、OneDrive アプリで、自分の仕事用または学校アカウントにサインインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="93e14-152">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="93e14-153">ボタンを選択 **+** し、 [アップロード] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="93e14-153">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="93e14-154">[カメラ ロール] の [ピクチャ] に移動して、アップロード **する>を見つける。**</span><span class="sxs-lookup"><span data-stu-id="93e14-154">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="93e14-155">アップロードする写真またはビデオを選択し、[開く] ボタン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="93e14-155">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>


1. [<span data-ttu-id="93e14-156">Windows Holographic バージョン 20H2 – 2021 年 5 月更新プログラムのビルドをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="93e14-156">Download the build for Windows Holographic, version 20H2 – May 2021 Update</span></span>](https://aka.ms/hololens2download/10.0.19041.1146)
1. <span data-ttu-id="93e14-157">以前の [OS バージョンに戻る手順に従います](hololens-update-hololens.md#go-back-to-a-previous-version)</span><span class="sxs-lookup"><span data-stu-id="93e14-157">Follow the [instructions return to a previous OS version](hololens-update-hololens.md#go-back-to-a-previous-version)</span></span>
1. <span data-ttu-id="93e14-158">デバイス [で OS 更新プログラムを手動で一時停止するか、多](hololens-updates.md#pause-updates-via-device) くのデバイスで MDM を介して [遅延を使用します](hololens-updates.md#configure-an-update-deferral-policy)。</span><span class="sxs-lookup"><span data-stu-id="93e14-158">Either [pause OS updates on the device manually](hololens-updates.md#pause-updates-via-device) or for many devices use [deferral through MDM](hololens-updates.md#configure-an-update-deferral-policy).</span></span>

[<span data-ttu-id="93e14-159">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="93e14-159">Back to list</span></span>](#list)

## <a name="auto-login-asks-for-log-in"></a><span data-ttu-id="93e14-160">自動ログインでログインを求める</span><span class="sxs-lookup"><span data-stu-id="93e14-160">Auto-login asks for log-in</span></span>

<span data-ttu-id="93e14-161">デバイスHoloLens 2設定アカウントサインイン オプション -> を使用して自動的にログインするように構成できます。[必須] で値を [Never] に  ->    ->  設定 **します**。 </span><span class="sxs-lookup"><span data-stu-id="93e14-161">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="93e14-162">一部のユーザーは、機能更新プログラムなど、大幅に大きな更新プログラムを使用してデバイスを更新するときに、デバイスに再度ログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="93e14-162">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span> <span data-ttu-id="93e14-163">これは既知の **問題です**。</span><span class="sxs-lookup"><span data-stu-id="93e14-163">This is a **known issue**.</span></span>

<span data-ttu-id="93e14-164">これが発生する可能性がある例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="93e14-164">Example of when this could occur:</span></span>

- <span data-ttu-id="93e14-165">Windows Holographic バージョン 2004 (ビルド 19041.xxxx) から Windows Holographic バージョン 21H1 (ビルド 20346.xxxx) へのデバイスの更新</span><span class="sxs-lookup"><span data-stu-id="93e14-165">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="93e14-166">同じメジャー ビルド (Windows Holographic バージョン 2004 から Windows Holographic バージョン 20H2 など) で大規模な更新を行うデバイスの更新</span><span class="sxs-lookup"><span data-stu-id="93e14-166">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="93e14-167">ファクトリ イメージから最新のイメージへのデバイスの更新</span><span class="sxs-lookup"><span data-stu-id="93e14-167">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="93e14-168">これは、次の場合には発生しません。</span><span class="sxs-lookup"><span data-stu-id="93e14-168">This should not occur during:</span></span>

- <span data-ttu-id="93e14-169">毎月のサービス更新プログラムを受け取るデバイス</span><span class="sxs-lookup"><span data-stu-id="93e14-169">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="93e14-170">メソッドの回避:</span><span class="sxs-lookup"><span data-stu-id="93e14-170">Work around methods:</span></span>

- <span data-ttu-id="93e14-171">PIN、パスワード、あやめ、Web 認証、FIDO2 キーなどのサインイン方法。</span><span class="sxs-lookup"><span data-stu-id="93e14-171">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="93e14-172">デバイス PIN を記憶できない場合、その他の認証方法を使用できない場合、ユーザーは手動 [の再フラッシュ モードを使用できます](hololens-recovery.md#manual-procedure)。</span><span class="sxs-lookup"><span data-stu-id="93e14-172">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

[<span data-ttu-id="93e14-173">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="93e14-173">Back to list</span></span>](#list)

## <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="93e14-174">Microsoft Edge起動に失敗する</span><span class="sxs-lookup"><span data-stu-id="93e14-174">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="93e14-175">この問題は、当初、出荷バージョンのバージョンを念頭Microsoft Edgeして作成されました。</span><span class="sxs-lookup"><span data-stu-id="93e14-175">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="93e14-176">この問題は、 の新しいバージョン[で解決Microsoft Edge。](hololens-new-edge.md)</span><span class="sxs-lookup"><span data-stu-id="93e14-176">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="93e14-177">そうではない場合は、フィードバックを送信してください。</span><span class="sxs-lookup"><span data-stu-id="93e14-177">If it is not, please file feedback.</span></span>

<span data-ttu-id="93e14-178">一部のお客様から、起動に失敗する問題Microsoft Edge報告されています。</span><span class="sxs-lookup"><span data-stu-id="93e14-178">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="93e14-179">これらのお客様の場合、この問題は再起動を通じて解決され、Windows またはアプリケーションの更新プログラムでは解決されません。</span><span class="sxs-lookup"><span data-stu-id="93e14-179">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="93e14-180">この問題が発生し [、Windows](hololens-updates.md#manually-check-for-updates)が最新の である確認済みである場合は、次のカテゴリとサブカテゴリを持つ [フィードバック Hub](hololens-feedback.md) アプリからバグを報告してください: > のダウンロード、インストール、および構成 Windows Update。</span><span class="sxs-lookup"><span data-stu-id="93e14-180">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="93e14-181">これまでに問題を根本原因にできなかったので、既知の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="93e14-181">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="93e14-182">レポートを使用してバグをフィードバック Hub調査に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="93e14-182">Filing a bug via Feedback Hub will help our investigation!</span></span> <span data-ttu-id="93e14-183">これは既知の **問題です**。</span><span class="sxs-lookup"><span data-stu-id="93e14-183">This is a **known issue**.</span></span>

[<span data-ttu-id="93e14-184">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="93e14-184">Back to list</span></span>](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a><span data-ttu-id="93e14-185">キーボードが特殊文字に切り替えない</span><span class="sxs-lookup"><span data-stu-id="93e14-185">Keyboard doesn't switch to special characters</span></span>

<span data-ttu-id="93e14-186">OOBE 中に問題が発生します。ユーザーが仕事用または学校アカウントを選択し、パスワードを入力すると、&123 ボタンをタップしてキーボードの特殊文字に切り替えようとしても、特殊文字に変わりません。</span><span class="sxs-lookup"><span data-stu-id="93e14-186">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> <span data-ttu-id="93e14-187">これは既知の **問題です**。</span><span class="sxs-lookup"><span data-stu-id="93e14-187">This is a **known issue**.</span></span>

<span data-ttu-id="93e14-188">回避方法:</span><span class="sxs-lookup"><span data-stu-id="93e14-188">Work-arounds:</span></span>
-   <span data-ttu-id="93e14-189">キーボードを閉じ、テキスト フィールドをタップして再度開きます。</span><span class="sxs-lookup"><span data-stu-id="93e14-189">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="93e14-190">パスワードを誤って入力します。</span><span class="sxs-lookup"><span data-stu-id="93e14-190">Incorrectly enter your password.</span></span> <span data-ttu-id="93e14-191">次回キーボードを再起動すると、期待した通り動作します。</span><span class="sxs-lookup"><span data-stu-id="93e14-191">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="93e14-192">Web 認証を行い、キーボードを閉じ、別の **デバイスから [サインイン] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="93e14-192">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="93e14-193">数値のみを入力する場合、ユーザーは特定のキーを長押しして展開されたメニューを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="93e14-193">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="93e14-194">USB キーボードを使用する。</span><span class="sxs-lookup"><span data-stu-id="93e14-194">Using a USB keyboard.</span></span>

<span data-ttu-id="93e14-195">これは、次の場合には影響を与え "ない" です。</span><span class="sxs-lookup"><span data-stu-id="93e14-195">This does not affect:</span></span>
- <span data-ttu-id="93e14-196">個人アカウントの使用を選択したユーザー。</span><span class="sxs-lookup"><span data-stu-id="93e14-196">Users who choose to use a personal account.</span></span>

[<span data-ttu-id="93e14-197">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="93e14-197">Back to list</span></span>](#list)


## <a name="downloading-locked-files-doesnt-error"></a><span data-ttu-id="93e14-198">ロックされたファイルをダウンロードしてもエラーが発生しない</span><span class="sxs-lookup"><span data-stu-id="93e14-198">Downloading locked files doesn't error</span></span>
> <span data-ttu-id="93e14-199">!注 これは、ビルド **バージョン** 20348.1403 で修正Windows Insider既知の問題です。</span><span class="sxs-lookup"><span data-stu-id="93e14-199">!NOTE This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span>


<span data-ttu-id="93e14-200">以前の Windows Holographic のビルドでは、ロックされたファイルをダウンロードしようとすると、結果は HTTP エラー ページになります。</span><span class="sxs-lookup"><span data-stu-id="93e14-200">In previous builds of Windows Holographic, when attempting to download a locked file, the result would be an HTTP error page.</span></span> <span data-ttu-id="93e14-201">Windows Holographic バージョン 21H1 更新プログラムでは、ロックされたファイルをダウンロードしようとしても、何も表示されません。ファイルはダウンロードされません。エラーはありません。</span><span class="sxs-lookup"><span data-stu-id="93e14-201">In the Windows Holographic, version 21H1 update, trying to download a locked file results in nothing visible happening—the file doesn’t download and there’s no error.</span></span> 

[<span data-ttu-id="93e14-202">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="93e14-202">Back to list</span></span>](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a><span data-ttu-id="93e14-203">デバイス ポータルファイルのアップロード/ダウンロードがアウトした場合</span><span class="sxs-lookup"><span data-stu-id="93e14-203">Device Portal file upload/download times out</span></span>
> <span data-ttu-id="93e14-204">!注 これは、ビルド **バージョン** 20348.1403 で修正Windows Insider既知の問題です。</span><span class="sxs-lookup"><span data-stu-id="93e14-204">!NOTE This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span> <span data-ttu-id="93e14-205">回避策の一環として以前に SSL 接続を無効にした場合は、再び有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="93e14-205">If you previously disabled SSL Connection as part of the workaround, we highly recommend you re-enable it.</span></span>


<span data-ttu-id="93e14-206">一部のお客様は、ファイルのアップロードまたはダウンロードを試みる際に、操作がハングし、その後に時間が切れたか、完了しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="93e14-206">Some customers have found, when attempting to upload or download files, the operation might appear to hang and then time out or never complete.</span></span> <span data-ttu-id="93e14-207">これは、"ファイル ロック["](#downloading-locked-files-doesnt-error) の既知の問題とは別です。これは、Windows Holographic、バージョン 2004、20H2、および 21H1 の市場内ビルドに影響します。</span><span class="sxs-lookup"><span data-stu-id="93e14-207">This is separate from the '[file locked' known issue](#downloading-locked-files-doesnt-error) -- this affects Windows Holographic, versions 2004, 20H2 and 21H1 in-market builds.</span></span> <span data-ttu-id="93e14-208">この問題は、デバイス ポータル による特定の要求の処理のバグが原因で根本原因であり、既定の https を使用すると最も一貫してヒットします。</span><span class="sxs-lookup"><span data-stu-id="93e14-208">The problem has been root caused to a bug in Device Portal's handling of certain requests, and is most consistently hit when using https, which is the default.</span></span> 

### <a name="workaround"></a><span data-ttu-id="93e14-209">回避策</span><span class="sxs-lookup"><span data-stu-id="93e14-209">Workaround</span></span>

<span data-ttu-id="93e14-210">この回避策は、Wi-Fi と UsbNcm に同じように適用され、"SSL 接続" の下で "必須" オプションを無効にします。</span><span class="sxs-lookup"><span data-stu-id="93e14-210">This workaround, which applies equally to Wi-Fi and UsbNcm, is to disable the "required" option under "SSL Connection".</span></span> <span data-ttu-id="93e14-211">これを行うには、[システム] の デバイス ポータル **に移動** し、[基本設定] **ページを選択** します。</span><span class="sxs-lookup"><span data-stu-id="93e14-211">To do so, navigate to Device Portal, **System**, and select the **Preferences** page.</span></span> <span data-ttu-id="93e14-212">[デバイス セキュリティ **] セクションで** 、[SSL 接続] **を探し**、[必須] を無効にするには **オフにします**。</span><span class="sxs-lookup"><span data-stu-id="93e14-212">In the **Device Security** section, locate **SSL Connection**, and uncheck to disable **Required**.</span></span>

<span data-ttu-id="93e14-213">その後、ユーザーは http:// にアクセスする必要 https:// (IP アドレス) ではなく、ファイルのアップロードやダウンロードのような機能が機能します。</span><span class="sxs-lookup"><span data-stu-id="93e14-213">The user should then go to http://, not https:// (IP address) and features like file upload and download will work.</span></span>

[<span data-ttu-id="93e14-214">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="93e14-214">Back to list</span></span>](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a><span data-ttu-id="93e14-215">Insider ビルドでフラッシュされたデバイスで Insider プレビューから登録を解除した後のブルー スクリーン</span><span class="sxs-lookup"><span data-stu-id="93e14-215">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>

<span data-ttu-id="93e14-216">これは、Insider プレビュー ビルドに含まれるユーザーに影響を与え、新しい Insider プレビュー ビルドで HoloLens 2 を再フラッシュした後、Insider プログラムから登録を解除したユーザーに影響する問題です。</span><span class="sxs-lookup"><span data-stu-id="93e14-216">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> <span data-ttu-id="93e14-217">これは既知の **問題です**。</span><span class="sxs-lookup"><span data-stu-id="93e14-217">This is a **known issue**.</span></span>

<span data-ttu-id="93e14-218">これは、次の場合には影響を与え "ない" です。</span><span class="sxs-lookup"><span data-stu-id="93e14-218">This does not affect:</span></span>
- <span data-ttu-id="93e14-219">アカウントに登録されていないWindows Insider</span><span class="sxs-lookup"><span data-stu-id="93e14-219">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="93e14-220">インサイダー：</span><span class="sxs-lookup"><span data-stu-id="93e14-220">Insiders:</span></span>
    - <span data-ttu-id="93e14-221">Insider ビルドがバージョン 18362.x 以降にデバイスが登録されている場合</span><span class="sxs-lookup"><span data-stu-id="93e14-221">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="93e14-222">Insider 署名済み 19041.x ビルドをフラッシュし、Insider プログラムに登録された</span><span class="sxs-lookup"><span data-stu-id="93e14-222">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="93e14-223">回避:</span><span class="sxs-lookup"><span data-stu-id="93e14-223">Work-around:</span></span> 
- <span data-ttu-id="93e14-224">問題を回避する</span><span class="sxs-lookup"><span data-stu-id="93e14-224">Avoid the issue</span></span> 
    - <span data-ttu-id="93e14-225">インサイダー以外のビルドをフラッシュします。</span><span class="sxs-lookup"><span data-stu-id="93e14-225">Flash a non-insider build.</span></span> <span data-ttu-id="93e14-226">定期的な毎月の更新プログラムの 1 つ。</span><span class="sxs-lookup"><span data-stu-id="93e14-226">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="93e14-227">Insider Preview を利用する</span><span class="sxs-lookup"><span data-stu-id="93e14-227">Stay on Insider Preview</span></span>
- <span data-ttu-id="93e14-228">デバイスを再フラッシュする</span><span class="sxs-lookup"><span data-stu-id="93e14-228">Reflash the device</span></span>

    1. <span data-ttu-id="93e14-229">接続していない [HoloLens 2電源](hololens-recovery.md) を完全にオフにすることで、デバイスを手動でフラッシュ モードにします。</span><span class="sxs-lookup"><span data-stu-id="93e14-229">Put the [HoloLens 2 into flashing mode](hololens-recovery.md) manually by fully powering down while not connect.</span></span> <span data-ttu-id="93e14-230">次に、ボリュームを上に保持している間に、[電源] ボタンをタップします。</span><span class="sxs-lookup"><span data-stu-id="93e14-230">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="93e14-231">PC に接続し、Advanced Recovery Companion を開きます。</span><span class="sxs-lookup"><span data-stu-id="93e14-231">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="93e14-232">既定のビルドHoloLens 2をフラッシュします。</span><span class="sxs-lookup"><span data-stu-id="93e14-232">Flash the HoloLens 2 to the default build.</span></span>

[<span data-ttu-id="93e14-233">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="93e14-233">Back to list</span></span>](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a><span data-ttu-id="93e14-234">OneDrive で画像が自動的にアップロードされません</span><span class="sxs-lookup"><span data-stu-id="93e14-234">OneDrive doesn't automatically upload pictures</span></span>

<span data-ttu-id="93e14-235">HoloLens 用の OneDrive アプリでは、仕事用または学校アカウントの自動カメラ アップロードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="93e14-235">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span> <span data-ttu-id="93e14-236">これは既知の **問題です**。</span><span class="sxs-lookup"><span data-stu-id="93e14-236">This is a **known issue**.</span></span>

<span data-ttu-id="93e14-237">回避策:</span><span class="sxs-lookup"><span data-stu-id="93e14-237">Workarounds:</span></span>

- <span data-ttu-id="93e14-238">ビジネスで実行可能な場合は、コンシューマー向け Microsoft アカウントでカメラの自動アップロードがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="93e14-238">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="93e14-239">自分のアカウントまたは学校アカウントMicrosoft アカウント、自分のアカウントにサインインできます (OneDrive アプリではデュアル サインインがサポートされています)。</span><span class="sxs-lookup"><span data-stu-id="93e14-239">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="93e14-240">OneDrive 内Microsoft アカウントプロファイルから、自動のバックグラウンド カメラ ロール アップロードを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="93e14-240">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="93e14-241">写真を自動的にアップロードするためにコンシューマー Microsoft アカウント を安全に使用できない場合は、OneDrive アプリから手動で写真を仕事または学校アカウントにアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="93e14-241">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="93e14-242">これを行うには、OneDrive アプリで、自分の仕事用または学校アカウントにサインインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="93e14-242">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="93e14-243">ボタンを選択 **+** し、 [アップロード] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="93e14-243">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="93e14-244">[カメラ ロール] の [ピクチャ] に移動して、アップロード **する>を見つける。**</span><span class="sxs-lookup"><span data-stu-id="93e14-244">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="93e14-245">アップロードする写真またはビデオを選択し、[開く] ボタン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="93e14-245">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

[<span data-ttu-id="93e14-246">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="93e14-246">Back to list</span></span>](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a><span data-ttu-id="93e14-247">HoloLens が応答しないか、起動しない</span><span class="sxs-lookup"><span data-stu-id="93e14-247">HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="93e14-248">HoloLens が起動しない場合:</span><span class="sxs-lookup"><span data-stu-id="93e14-248">If your HoloLens won't start:</span></span>

- <span data-ttu-id="93e14-249">電源ボタンの横にある LED が点灯しない場合、または短時間点滅する LED が 1 つしか表示されていない場合は[、HoloLens](hololens2-charging.md#charging-the-device)の課金が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="93e14-249">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens2-charging.md#charging-the-device)</span></span>
- <span data-ttu-id="93e14-250">電源ボタンを押すと LED が点灯するが、ディスプレイに何も表示できない場合は、デバイス のハード リセット [を行います](hololens-recovery.md#hard-reset-procedure)。</span><span class="sxs-lookup"><span data-stu-id="93e14-250">If the LEDs light up when you press the power button but you can't see anything on the displays, [do a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="93e14-251">HoloLens が固定または応答しなくなる場合:</span><span class="sxs-lookup"><span data-stu-id="93e14-251">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="93e14-252">5 つの LED すべてがオフになるまで電源ボタンを押し、LED が応答しない場合は 15 秒間、HoloLens をオフにします。</span><span class="sxs-lookup"><span data-stu-id="93e14-252">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="93e14-253">HoloLens を起動するには、電源ボタンを再度押します。</span><span class="sxs-lookup"><span data-stu-id="93e14-253">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="93e14-254">これらの手順が機能しない場合は、HoloLens 2 デバイス[](hololens-recovery.md)または[HoloLens (第 1 世代) デバイスの復旧を試みてみます。](hololens1-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="93e14-254">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

[<span data-ttu-id="93e14-255">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="93e14-255">Back to list</span></span>](#list)

## <a name="low-disk-space-error"></a><span data-ttu-id="93e14-256">"ディスク領域が少ない" エラー</span><span class="sxs-lookup"><span data-stu-id="93e14-256">"Low Disk Space" error</span></span>

<span data-ttu-id="93e14-257">次の 1 つ以上を実行して、一部の記憶域スペースを解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93e14-257">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="93e14-258">未使用のスペースを削除します。</span><span class="sxs-lookup"><span data-stu-id="93e14-258">Delete some unused spaces.</span></span> <span data-ttu-id="93e14-259">[設定]  >  **[システム**  >  **スペース]** に移動し、不要になった領域を選択して、[削除] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="93e14-259">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="93e14-260">配置したホログラムの一部を削除します。</span><span class="sxs-lookup"><span data-stu-id="93e14-260">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="93e14-261">フォト アプリからいくつかの画像とビデオを削除します。</span><span class="sxs-lookup"><span data-stu-id="93e14-261">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="93e14-262">HoloLens から一部のアプリをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="93e14-262">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="93e14-263">[すべての **アプリ] の一** 覧で、アンインストールするアプリをタップしたままにし、[ アンインストール] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="93e14-263">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

[<span data-ttu-id="93e14-264">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="93e14-264">Back to list</span></span>](#list)

## <a name="calibration-fails"></a><span data-ttu-id="93e14-265">調整が失敗する</span><span class="sxs-lookup"><span data-stu-id="93e14-265">Calibration fails</span></span>

<span data-ttu-id="93e14-266">調整はほとんどのユーザーに対して機能しますが、調整に失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="93e14-266">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="93e14-267">調整エラーの考え方としては、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="93e14-267">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="93e14-268">気を散らして調整ターゲットに従わなくなって</span><span class="sxs-lookup"><span data-stu-id="93e14-268">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="93e14-269">ダーティまたはスクラッチされたデバイス バイザーまたはデバイス バイザーが正しく配置されていない</span><span class="sxs-lookup"><span data-stu-id="93e14-269">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="93e14-270">ダーティまたはスクラッチの眼鏡</span><span class="sxs-lookup"><span data-stu-id="93e14-270">Dirty or scratched glasses</span></span>
- <span data-ttu-id="93e14-271">特定の種類のコンタクト レンズと眼鏡 (色付きコンタクト レンズ、一部の Toric コンタクト レンズ、IR ブロッキング 眼鏡、高い眼鏡、眼鏡など)</span><span class="sxs-lookup"><span data-stu-id="93e14-271">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="93e14-272">より顕著なメイクといくつかのまつげの拡張機能</span><span class="sxs-lookup"><span data-stu-id="93e14-272">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="93e14-273">デバイスが目を見るのを妨げている場合は、黒い眼鏡フレームまたは太い眼鏡フレーム</span><span class="sxs-lookup"><span data-stu-id="93e14-273">Hair or thick eyeglass frames if they're blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="93e14-274">特定の目の前部、目の状態、または狭い目、長いまつげ、アンブリータイン、ニタグマス、LASIK や他の目の治療の一部のケースなど、目の治療</span><span class="sxs-lookup"><span data-stu-id="93e14-274">Certain eye physiology, eye conditions, or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="93e14-275">調整に失敗した場合は、次の手順を試してください。</span><span class="sxs-lookup"><span data-stu-id="93e14-275">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="93e14-276">デバイス バイザーのクリーニング</span><span class="sxs-lookup"><span data-stu-id="93e14-276">Cleaning your device visor</span></span>
- <span data-ttu-id="93e14-277">眼鏡のクリーニング</span><span class="sxs-lookup"><span data-stu-id="93e14-277">Cleaning your glasses</span></span>
- <span data-ttu-id="93e14-278">デバイスバイザーを可能な限り目の近くにプッシュする</span><span class="sxs-lookup"><span data-stu-id="93e14-278">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="93e14-279">バイザー内のオブジェクトを外に移動する (生長など)</span><span class="sxs-lookup"><span data-stu-id="93e14-279">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="93e14-280">部屋の照明をオンにするか、直接の光から出て行く</span><span class="sxs-lookup"><span data-stu-id="93e14-280">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="93e14-281">すべてのガイドラインに従い、調整がまだ失敗している場合は、[設定] で調整プロンプトを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="93e14-281">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="93e14-282">また、 でフィードバックを送信して、お知[フィードバック Hub。](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="93e14-282">Also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="93e14-283">画像の色または明るさ [のトラブルシューティングについては、関連情報も参照してください。](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span><span class="sxs-lookup"><span data-stu-id="93e14-283">Also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="93e14-284">目の位置はシステムによって計算HoloLens 2、IPD の設定は適用されません。</span><span class="sxs-lookup"><span data-stu-id="93e14-284">Setting IPD is not applicable for HoloLens 2, since eye positions are computed by the system.</span></span> 

[<span data-ttu-id="93e14-285">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="93e14-285">Back to list</span></span>](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a><span data-ttu-id="93e14-286">HoloLens が以前に他のユーザー用に設定されたため、サインインできない</span><span class="sxs-lookup"><span data-stu-id="93e14-286">Can't sign in because my HoloLens was previously set up for someone else</span></span>

<span data-ttu-id="93e14-287">デバイスを[フラッシュ モードにし、Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device)を使用してデバイスを回復できます。</span><span class="sxs-lookup"><span data-stu-id="93e14-287">You can [put the device into **Flashing Mode** and use Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) to recover the device.</span></span>

[<span data-ttu-id="93e14-288">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="93e14-288">Back to list</span></span>](#list)


## <a name="unity-isnt-working"></a><span data-ttu-id="93e14-289">Unity が機能しない</span><span class="sxs-lookup"><span data-stu-id="93e14-289">Unity isn't working</span></span>

- <span data-ttu-id="93e14-290">HoloLens [開発](/windows/mixed-reality/install-the-tools) に推奨される Unity の最新バージョンについては、ツールのインストールに関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="93e14-290">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="93e14-291">Unity HoloLens Technical Preview に関する既知の問題については [、HoloLens Unity フォーラムを参照してください](https://forum.unity3d.com/threads/known-issues.394627/)。</span><span class="sxs-lookup"><span data-stu-id="93e14-291">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

[<span data-ttu-id="93e14-292">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="93e14-292">Back to list</span></span>](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a><span data-ttu-id="93e14-293">Windows デバイス ポータルが正しく動作しない</span><span class="sxs-lookup"><span data-stu-id="93e14-293">Windows Device Portal isn't working correctly</span></span>

- <span data-ttu-id="93e14-294">キャプチャの Live Preview 機能Mixed Reality数秒の待機時間が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="93e14-294">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="93e14-295">[仮想入力] ページの [仮想ジェスチャ] セクションの [ジェスチャ] コントロールと [スクロール] コントロールは機能しません。</span><span class="sxs-lookup"><span data-stu-id="93e14-295">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="93e14-296">それらを使用した場合、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="93e14-296">Using them will have no effect.</span></span> <span data-ttu-id="93e14-297">仮想入力ページの仮想キーボードは正しく動作します。</span><span class="sxs-lookup"><span data-stu-id="93e14-297">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="93e14-298">[設定] で開発者モードを有効にした後、スイッチが有効になっているまで数秒デバイス ポータル場合があります。</span><span class="sxs-lookup"><span data-stu-id="93e14-298">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

[<span data-ttu-id="93e14-299">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="93e14-299">Back to list</span></span>](#list)

## <a name="emulator"></a><span data-ttu-id="93e14-300">エミュレーター</span><span class="sxs-lookup"><span data-stu-id="93e14-300">Emulator</span></span>
### <a name="the-hololens-emulator-isnt-working"></a><span data-ttu-id="93e14-301">HoloLens エミュレーターが動作しない</span><span class="sxs-lookup"><span data-stu-id="93e14-301">The HoloLens Emulator isn't working</span></span>

<span data-ttu-id="93e14-302">HoloLens エミュレーターに関する情報は、開発者向けドキュメントに掲載されています。</span><span class="sxs-lookup"><span data-stu-id="93e14-302">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="93e14-303">[HoloLens エミュレーターのトラブルシューティングの詳細を参照してください](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)。</span><span class="sxs-lookup"><span data-stu-id="93e14-303">Read more about [troubleshooting the HoloLens emulator](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).</span></span>


- <span data-ttu-id="93e14-304">アプリ内のすべてのアプリMicrosoft Storeエミュレーターと互換性がある場合はありません。</span><span class="sxs-lookup"><span data-stu-id="93e14-304">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="93e14-305">たとえば、Young Conker と Fragments はエミュレーターで再生できません。</span><span class="sxs-lookup"><span data-stu-id="93e14-305">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="93e14-306">エミュレーターで PC Web カメラを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="93e14-306">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="93e14-307">アプリケーションのライブ プレビュー機能Windows デバイス ポータルエミュレーターでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="93e14-307">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="93e14-308">引き続き、ビデオMixed Reality画像をキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="93e14-308">You can still capture Mixed Reality videos and images.</span></span>

[<span data-ttu-id="93e14-309">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="93e14-309">Back to list</span></span>](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a><span data-ttu-id="93e14-310">キーボードを見つけたり、使用してエミュレーターに入力HoloLens 2できない</span><span class="sxs-lookup"><span data-stu-id="93e14-310">I cannot find or use the keyboard to type in the HoloLens 2 Emulator</span></span>

<span data-ttu-id="93e14-311">*近日公開予定*</span><span class="sxs-lookup"><span data-stu-id="93e14-311">*Coming soon*</span></span>

[<span data-ttu-id="93e14-312">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="93e14-312">Back to list</span></span>](#list)

## <a name="voice-commands-arent-working"></a><span data-ttu-id="93e14-313">音声コマンドが機能しない</span><span class="sxs-lookup"><span data-stu-id="93e14-313">Voice commands aren't working</span></span>

<span data-ttu-id="93e14-314">Cortana が音声コマンドに応答しない場合は、Cortana が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="93e14-314">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="93e14-315">[すべてのアプリ] の一覧で **[Cortana** Menu Notebook の設定]  >    >  **を**  >  **選択して** 変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="93e14-315">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="93e14-316">話し方の詳細については [、「HoloLens で音声を使用する」を参照してください](hololens-cortana.md)。</span><span class="sxs-lookup"><span data-stu-id="93e14-316">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

<span data-ttu-id="93e14-317">HoloLens (第 1 世代) では、組み込みの音声認識は構成できません。</span><span class="sxs-lookup"><span data-stu-id="93e14-317">On HoloLens (1st gen), built-in speech recognition is not configurable.</span></span> <span data-ttu-id="93e14-318">これは常にオンです。</span><span class="sxs-lookup"><span data-stu-id="93e14-318">It is always turned on.</span></span> <span data-ttu-id="93e14-319">デバイスHoloLens 2セットアップ中に音声認識と Cortana の両方を有効にするかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="93e14-319">On HoloLens 2, you can choose whether to turn on both speech recognition and Cortana during device setup.</span></span>

<span data-ttu-id="93e14-320">音声にHoloLens 2応答していない場合は、音声認識が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="93e14-320">If your HoloLens 2 is not responding to your voice, make sure Speech recognition is turned on.</span></span> <span data-ttu-id="93e14-321">[スタート設定 **] [**  >  **プライバシー音声**  >  **] に**  >  **移動し**、[音声認識]**をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="93e14-321">Go to **Start** > **Settings** > **Privacy** > **Speech** and turn on **Speech recognition**.</span></span>

[<span data-ttu-id="93e14-322">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="93e14-322">Back to list</span></span>](#list)

## <a name="hand-input-isnt-working"></a><span data-ttu-id="93e14-323">手入力が機能しない</span><span class="sxs-lookup"><span data-stu-id="93e14-323">Hand input isn't working</span></span>

<span data-ttu-id="93e14-324">HoloLens が手を確実に表示するには、ジェスチャ フレーム内に保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93e14-324">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="93e14-325">[Mixed Reality ホーム] には、手がいつ追跡されるのか知るフィードバックが提供されます。</span><span class="sxs-lookup"><span data-stu-id="93e14-325">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="93e14-326">フィードバックは、HoloLens のバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="93e14-326">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="93e14-327">HoloLens (第 1 世代) では、視線カーソルがドットからリングに変わります</span><span class="sxs-lookup"><span data-stu-id="93e14-327">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="93e14-328">このHoloLens 2、手がスレートに近いときに指先カーソルが表示され、スレートが離れたときに手の光線が表示されます</span><span class="sxs-lookup"><span data-stu-id="93e14-328">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="93e14-329">多くのイマーシブ アプリは、ホームに似た入力パターンMixed Realityします。</span><span class="sxs-lookup"><span data-stu-id="93e14-329">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="93e14-330">[HoloLens (第 1](hololens1-basic-usage.md#use-hololens-with-your-hands)世代) および HoloLens 2 で手入力を使用する方法[について学習します](hololens2-basic-usage.md#the-hand-tracking-frame)。</span><span class="sxs-lookup"><span data-stu-id="93e14-330">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="93e14-331">グラブを装着している場合は、一部の種類の靴下が手の追跡で動作しない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="93e14-331">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="93e14-332">一般的な例として、黒いゴムのグラブがあります。これは、赤外光を吸収する傾向があるが、深度カメラでは取り出されません。</span><span class="sxs-lookup"><span data-stu-id="93e14-332">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="93e14-333">作業にゴム製のグローブが含まれる場合は、青やグレーなどの薄い色を試することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="93e14-333">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="93e14-334">もう 1 つの例は、手の形があいまいになりがちな、大きなバッグ状のグラブです。</span><span class="sxs-lookup"><span data-stu-id="93e14-334">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="93e14-335">最適な結果を得る場合は、可能な限りフォームに合ったアダプターを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="93e14-335">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="93e14-336">バイザーに指紋やスマージがある場合は、HoloLens に備え付けられているマイクロファイバー クリーニング の布を使用して、バイザーをすいすくクリーニングします。</span><span class="sxs-lookup"><span data-stu-id="93e14-336">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

[<span data-ttu-id="93e14-337">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="93e14-337">Back to list</span></span>](#list)

## <a name="cant-connect-to-wi-fi"></a><span data-ttu-id="93e14-338">デバイスに接続Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="93e14-338">Can't connect to Wi-Fi</span></span>

<span data-ttu-id="93e14-339">HoloLens を新しいネットワークに接続できない場合に試Wi-Fiします。</span><span class="sxs-lookup"><span data-stu-id="93e14-339">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

- <span data-ttu-id="93e14-340">有効になっているWi-Fi確認します。</span><span class="sxs-lookup"><span data-stu-id="93e14-340">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="93e14-341">確認するには、[スタート] ジェスチャを使用し、[設定] **[**  >  **ネットワーク インターネット &amp;**  >  **Wi-Fi] の順に選択します**。</span><span class="sxs-lookup"><span data-stu-id="93e14-341">To check, use the Start gesture, then select **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="93e14-342">オンWi-Fi場合は、オフにしてから、もう一度オンにしてみてください。</span><span class="sxs-lookup"><span data-stu-id="93e14-342">If Wi-Fi is on, try turning it off and then on again.</span></span>
- <span data-ttu-id="93e14-343">ルーターまたはアクセス ポイントの近くに移動します。</span><span class="sxs-lookup"><span data-stu-id="93e14-343">Move closer to the router or access point.</span></span>
- <span data-ttu-id="93e14-344">新しいルーター [Wi-Fi、HoloLens を再起動します](hololens-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="93e14-344">Restart your Wi-Fi router, then [restart HoloLens](hololens-recovery.md).</span></span> <span data-ttu-id="93e14-345">接続を再試行してください。</span><span class="sxs-lookup"><span data-stu-id="93e14-345">Try connecting again.</span></span>
- <span data-ttu-id="93e14-346">これらのいずれも機能しない場合は、ルーターで最新のファームウェアが使用されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="93e14-346">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="93e14-347">この情報は、製造元の Web サイトで確認できます。</span><span class="sxs-lookup"><span data-stu-id="93e14-347">You can find this information on the manufacturer website.</span></span>

[<span data-ttu-id="93e14-348">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="93e14-348">Back to list</span></span>](#list)
## <a name="bluetooth-devices-arent-pairing"></a><span data-ttu-id="93e14-349">Bluetooth デバイスがペアリングされていない</span><span class="sxs-lookup"><span data-stu-id="93e14-349">Bluetooth devices aren't pairing</span></span>

<span data-ttu-id="93e14-350">[Bluetooth](hololens-connect-devices.md)デバイスのペアリングで問題が発生した場合は、次を試してください。</span><span class="sxs-lookup"><span data-stu-id="93e14-350">If you're having problems [pairing a Bluetooth device](hololens-connect-devices.md), try the following:</span></span>

- <span data-ttu-id="93e14-351">[設定] **[**  >  **デバイス]** に移動し、Bluetooth がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="93e14-351">Go to **Settings** > **Devices**, and make sure that Bluetooth is turned on.</span></span> <span data-ttu-id="93e14-352">有効な場合は、オフにし、再度オンにします。</span><span class="sxs-lookup"><span data-stu-id="93e14-352">If it is, turn it off and on again.</span></span>
- <span data-ttu-id="93e14-353">Bluetooth デバイスが完全に充電されている、または新しいバッテリが搭載されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="93e14-353">Make sure that your Bluetooth device is fully charged or has fresh batteries.</span></span>
- <span data-ttu-id="93e14-354">それでも接続できない場合は [、HoloLens を再起動します](hololens-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="93e14-354">If you still can't connect, [restart the HoloLens](hololens-recovery.md).</span></span>

[<span data-ttu-id="93e14-355">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="93e14-355">Back to list</span></span>](#list)

## <a name="usb-c-microphone-isnt-working"></a><span data-ttu-id="93e14-356">USB-C マイクが動作しない</span><span class="sxs-lookup"><span data-stu-id="93e14-356">USB-C Microphone isn't working</span></span>
<span data-ttu-id="93e14-357">一部の USB-C マイクでは、マイクとスピーカーの両方として誤って報告される *点に* 注意してください。</span><span class="sxs-lookup"><span data-stu-id="93e14-357">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="93e14-358">これは、HoloLens ではなく、マイクに関する問題です。</span><span class="sxs-lookup"><span data-stu-id="93e14-358">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="93e14-359">これらのマイクのいずれかを HoloLens に接続すると、サウンドが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="93e14-359">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="93e14-360">さいわい、簡単な修正があります。</span><span class="sxs-lookup"><span data-stu-id="93e14-360">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="93e14-361">[**設定**  ->  **システム**  ->  **サウンド]** で、組み込みのスピーカー **(アナログ機能オーディオ** ドライバー) を既定のデバイス として明示的 **に設定します**。</span><span class="sxs-lookup"><span data-stu-id="93e14-361">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="93e14-362">後でマイクを取り外して再接続した場合でも、HoloLens ではこの設定を記憶する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93e14-362">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![USB-C マイクのトラブルシューティング](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a><span data-ttu-id="93e14-364">[設定] に使用可能として表示されているデバイスが機能しない</span><span class="sxs-lookup"><span data-stu-id="93e14-364">Devices listed as available in Settings don't work</span></span>

<span data-ttu-id="93e14-365">HoloLens (第 1 世代) では、Bluetooth オーディオ プロファイルはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="93e14-365">HoloLens (1st gen) doesn't support Bluetooth audio profiles.</span></span> <span data-ttu-id="93e14-366">スピーカーやヘッドセットなどの Bluetooth オーディオ デバイスは、HoloLens の設定で使用できると表示される場合がありますが、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="93e14-366">Bluetooth audio devices, such as speakers and headsets, may appear as available in HoloLens settings, but they aren't supported.</span></span>

<span data-ttu-id="93e14-367">HoloLens 2、ステレオ再生用の Bluetooth A2DP オーディオ プロファイルがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="93e14-367">HoloLens 2 supports the Bluetooth A2DP audio profile for stereo playback.</span></span> <span data-ttu-id="93e14-368">Bluetooth 周辺機器からのマイク キャプチャを有効にする Bluetooth ハンズ フリー プロファイルは、HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="93e14-368">The Bluetooth Hands Free profile which enables microphone capture from a Bluetooth peripheral is not supported on HoloLens 2.</span></span>

<span data-ttu-id="93e14-369">Bluetooth デバイスの使用で問題が発生した場合は、それがサポートされているデバイスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="93e14-369">If you're having trouble using a Bluetooth device, make sure that it's a supported device.</span></span> <span data-ttu-id="93e14-370">サポートされているデバイスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="93e14-370">Supported devices include the following:</span></span>

- <span data-ttu-id="93e14-371">英語の QWERTY Bluetooth キーボード (ホログラフィック キーボードを使用する任意の場所で使用できます)。</span><span class="sxs-lookup"><span data-stu-id="93e14-371">English-language QWERTY Bluetooth keyboards (you can use these anywhere that you use the holographic keyboard).</span></span>
- <span data-ttu-id="93e14-372">Bluetooth マウス。</span><span class="sxs-lookup"><span data-stu-id="93e14-372">Bluetooth mice.</span></span>
- <span data-ttu-id="93e14-373">[HoloLens クッカー](hololens1-clicker.md)。</span><span class="sxs-lookup"><span data-stu-id="93e14-373">The [HoloLens clicker](hololens1-clicker.md).</span></span>

<span data-ttu-id="93e14-374">他の Bluetooth HID デバイスと GATT デバイスを HoloLens と組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="93e14-374">You can pair other Bluetooth HID and GATT devices together with your HoloLens.</span></span> <span data-ttu-id="93e14-375">ただし、デバイスを実際に使用するには、Microsoft Storeアプリをインストールする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="93e14-375">However, you may have to install corresponding companion apps from Microsoft Store to actually use the devices.</span></span>

[<span data-ttu-id="93e14-376">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="93e14-376">Back to list</span></span>](#list)
