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
# <a name="device-troubleshooting"></a><span data-ttu-id="7dea4-104">デバイスのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7dea4-104">Device Troubleshooting</span></span>

<span data-ttu-id="7dea4-105">この記事では、いくつかの一般的な HoloLens の問題を解決する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-105">This article describes how to resolve several common HoloLens issues.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="7dea4-106">トラブルシューティングの手順を開始する前に、可能であれば、デバイスがバッテリ容量の **20 ~ 40%** に充電されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7dea4-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="7dea4-107">電源ボタンの下にある [バッテリインジケーターライト](hololens2-setup.md#lights-that-indicate-the-battery-level) は、デバイスにログインしなくてもバッテリ容量を確認するための簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="7dea4-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<a id="list"></a>

<span data-ttu-id="7dea4-108">**既知の問題**</span><span class="sxs-lookup"><span data-stu-id="7dea4-108">**Known Issues**</span></span>
- [<span data-ttu-id="7dea4-109">20分後にリモートアシスタンスビデオがフリーズする</span><span class="sxs-lookup"><span data-stu-id="7dea4-109">Remote Assist video freezes after 20 minutes</span></span>](#remote-assist-video-freezes-after-20-minutes)
- [<span data-ttu-id="7dea4-110">自動ログインによるログインの要求</span><span class="sxs-lookup"><span data-stu-id="7dea4-110">Auto-login asks for log-in</span></span>](#auto-login-asks-for-log-in)
- [<span data-ttu-id="7dea4-111">Microsoft Edge を起動できない</span><span class="sxs-lookup"><span data-stu-id="7dea4-111">Microsoft Edge fails to launch</span></span>](#microsoft-edge-fails-to-launch)
- [<span data-ttu-id="7dea4-112">キーボードが特殊文字に切り替わることはありません</span><span class="sxs-lookup"><span data-stu-id="7dea4-112">Keyboard doesn't switch to special characters</span></span>](#keyboard-doesnt-switch-to-special-characters)
- [<span data-ttu-id="7dea4-113">ロックされたファイルのダウンロードにエラーが表示されない</span><span class="sxs-lookup"><span data-stu-id="7dea4-113">Downloading locked files doesn't show error</span></span>](#downloading-locked-files-doesnt-error)
- [<span data-ttu-id="7dea4-114">デバイスポータルファイルのアップロード/ダウンロードがタイムアウトする</span><span class="sxs-lookup"><span data-stu-id="7dea4-114">Device Portal file upload/download times out</span></span>](#device-portal-file-uploaddownload-times-out)
- [<span data-ttu-id="7dea4-115">Insider build を使用してフラッシュされたデバイスで Insider preview から登録解除した後のブルースクリーン</span><span class="sxs-lookup"><span data-stu-id="7dea4-115">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [<span data-ttu-id="7dea4-116">画像が自動的にアップロードされない OneDrive</span><span class="sxs-lookup"><span data-stu-id="7dea4-116">OneDrive doesn't automatically upload pictures</span></span>](#onedrive-doesnt-automatically-upload-pictures)

<span data-ttu-id="7dea4-117">**全般**</span><span class="sxs-lookup"><span data-stu-id="7dea4-117">**General**</span></span>
- [<span data-ttu-id="7dea4-118">HoloLens が応答していないか、開始されていません</span><span class="sxs-lookup"><span data-stu-id="7dea4-118">HoloLens is unresponsive or won't start</span></span>](#hololens-is-unresponsive-or-wont-start)
- [<span data-ttu-id="7dea4-119">"ディスク領域が不足しています" エラー</span><span class="sxs-lookup"><span data-stu-id="7dea4-119">"Low Disk Space" error</span></span>](#low-disk-space-error)
- [<span data-ttu-id="7dea4-120">調整が失敗する</span><span class="sxs-lookup"><span data-stu-id="7dea4-120">Calibration Fails</span></span>](#calibration-fails)
- [<span data-ttu-id="7dea4-121">HoloLens が既に他のユーザーに設定されているため、サインインできません</span><span class="sxs-lookup"><span data-stu-id="7dea4-121">Can't sign in because my HoloLens was previously set up for someone else</span></span>](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [<span data-ttu-id="7dea4-122">Unity が動作しない</span><span class="sxs-lookup"><span data-stu-id="7dea4-122">Unity isn't working</span></span>](#unity-isnt-working)
- [<span data-ttu-id="7dea4-123">Windowsデバイスポータルが正しく動作していません</span><span class="sxs-lookup"><span data-stu-id="7dea4-123">Windows Device Portal isn't working correctly</span></span>](#windows-device-portal-isnt-working-correctly)
- [<span data-ttu-id="7dea4-124">HoloLens Emulator が機能していません</span><span class="sxs-lookup"><span data-stu-id="7dea4-124">The HoloLens Emulator isn't working</span></span>](#the-hololens-emulator-isnt-working)

<span data-ttu-id="7dea4-125">**入力**</span><span class="sxs-lookup"><span data-stu-id="7dea4-125">**Input**</span></span>
- [<span data-ttu-id="7dea4-126">音声コマンドが動作していません</span><span class="sxs-lookup"><span data-stu-id="7dea4-126">Voice commands aren't working</span></span>](#voice-commands-arent-working)
- [<span data-ttu-id="7dea4-127">手書き入力が機能していません</span><span class="sxs-lookup"><span data-stu-id="7dea4-127">Hand input isn't working</span></span>](#hand-input-isnt-working)

<span data-ttu-id="7dea4-128">**接続**</span><span class="sxs-lookup"><span data-stu-id="7dea4-128">**Connectivity**</span></span>
- [<span data-ttu-id="7dea4-129">Wi-fi に接続できません</span><span class="sxs-lookup"><span data-stu-id="7dea4-129">Can't connect to Wi-Fi</span></span>](#cant-connect-to-wi-fi)

<span data-ttu-id="7dea4-130">**外部デバイス**</span><span class="sxs-lookup"><span data-stu-id="7dea4-130">**External Devices**</span></span> 
- [<span data-ttu-id="7dea4-131">Bluetooth デバイスがペアリングしていない</span><span class="sxs-lookup"><span data-stu-id="7dea4-131">Bluetooth devices aren't pairing</span></span>](#bluetooth-devices-arent-pairing)
- [<span data-ttu-id="7dea4-132">USB C マイクが動作していない</span><span class="sxs-lookup"><span data-stu-id="7dea4-132">USB-C Microphone isn't working</span></span>](#usb-c-microphone-isnt-working)
- [<span data-ttu-id="7dea4-133">設定で使用可能と表示されているデバイスが動作しない</span><span class="sxs-lookup"><span data-stu-id="7dea4-133">Devices listed as available in Settings don't work</span></span>](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a><span data-ttu-id="7dea4-134">20分後にリモートアシスタンスビデオがフリーズする</span><span class="sxs-lookup"><span data-stu-id="7dea4-134">Remote Assist video freezes after 20 minutes</span></span>

> [!NOTE]
> <span data-ttu-id="7dea4-135">この問題を修正するリモートアシスタンスの新しいバージョンがあります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-135">There is a newer version of Remote Assist which has a fix for this issue.</span></span> <span data-ttu-id="7dea4-136">この問題を回避するには、リモートアシスタンスを最新バージョンに [更新](holographic-store-apps.md#update-apps) してください。</span><span class="sxs-lookup"><span data-stu-id="7dea4-136">Please [update Remote Assist](holographic-store-apps.md#update-apps) to the latest version to avoid this issue.</span></span>

> [!NOTE]
> <span data-ttu-id="7dea4-137">この既知の問題の重要度により、Windows Holographic バージョン21h1 の可用性が一時的に一時停止されました。</span><span class="sxs-lookup"><span data-stu-id="7dea4-137">Due to this Known Issue's severity we had temporarily paused the availability of Windows Holographic, version 21H1.</span></span> <span data-ttu-id="7dea4-138">21H1 ビルドが再び使用できるようになりました。そのため、デバイスは最新の21H1 ビルドに再び更新される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-138">The 21H1 build is now available again, so devices may once again be updated to the latest 21H1 build.</span></span>

<span data-ttu-id="7dea4-139">[Windows Holographic version 21h1](hololens-release-notes.md#windows-holographic-version-21h1)の最新リリースでは、リモートアシスタンスの一部のユーザーが20分間の通話中にビデオをフリーズしています。</span><span class="sxs-lookup"><span data-stu-id="7dea4-139">On the latest release of [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), some users of Remote Assist have experienced video freezing during calls over 20 minutes.</span></span> <span data-ttu-id="7dea4-140">これは **既知の問題** です。</span><span class="sxs-lookup"><span data-stu-id="7dea4-140">This is a **known issue**.</span></span>

### <a name="workarounds"></a><span data-ttu-id="7dea4-141">回避策</span><span class="sxs-lookup"><span data-stu-id="7dea4-141">Workarounds</span></span>

<span data-ttu-id="7dea4-142">リモートアシスタンスを新しいビルドに更新できない場合は、次の回避策を試してください。</span><span class="sxs-lookup"><span data-stu-id="7dea4-142">If you are unable to update Remote Assist to a newer build try the following work around.</span></span>

#### <a name="restart-in-between-calls"></a><span data-ttu-id="7dea4-143">呼び出し間での再起動</span><span class="sxs-lookup"><span data-stu-id="7dea4-143">Restart in between calls</span></span>

<span data-ttu-id="7dea4-144">呼び出しの長さが20分を超えていて、この問題が発生している場合は、デバイスを再起動してみてください。</span><span class="sxs-lookup"><span data-stu-id="7dea4-144">If your calls are going over a length of 20 minutes and you are experiencing this issue, try rebooting your device.</span></span> <span data-ttu-id="7dea4-145">リモートアシスタンスの呼び出しの間にデバイスを再起動すると、デバイスが更新され、良好な状態に戻ります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-145">Rebooting your device between Remote Assist calls will refresh your device and put it back into a good state.</span></span>

<span data-ttu-id="7dea4-146">Windows Holographic でデバイスをすぐに再起動するには [、バージョン 21h1](hololens-release-notes.md#windows-holographic-version-21h1)で [スタート] メニューを開き、[ユーザー] アイコンを選択し、[**再起動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-146">To quickly restart a device on [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) open the start menu, and select the user icon, then select **Restart**.</span></span>

[<span data-ttu-id="7dea4-147">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="7dea4-147">Back to list</span></span>](#list)

## <a name="auto-login-asks-for-log-in"></a><span data-ttu-id="7dea4-148">自動ログインによるログインの要求</span><span class="sxs-lookup"><span data-stu-id="7dea4-148">Auto-login asks for log-in</span></span>

<span data-ttu-id="7dea4-149">HoloLens 2 デバイスは、**設定** アカウントのサインイン > オプションを使用して自動的にログインするように構成でき  ->    ->  ます。また、[**必須**] の値を [**なし**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-149">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="7dea4-150">機能の更新など、大幅に大きな更新プログラムを使用してデバイスを更新する場合、一部のユーザーがデバイスに再度ログインする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-150">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span> <span data-ttu-id="7dea4-151">これは **既知の問題** です。</span><span class="sxs-lookup"><span data-stu-id="7dea4-151">This is a **known issue**.</span></span>

<span data-ttu-id="7dea4-152">このような状況が発生する可能性のある例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-152">Example of when this could occur:</span></span>

- <span data-ttu-id="7dea4-153">デバイスを Windows Holographic、バージョン 2004 (ビルド 19041) から Windows Holographic、バージョン 21h1 (ビルド 20346) に更新する</span><span class="sxs-lookup"><span data-stu-id="7dea4-153">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="7dea4-154">同じメジャービルドで大規模な更新を実行するようにデバイスを更新する (Windows Holographic、バージョン Windows 2004、Holographic、バージョン20h2 など)</span><span class="sxs-lookup"><span data-stu-id="7dea4-154">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="7dea4-155">デバイスを工場出荷時のイメージから最新のイメージに更新する</span><span class="sxs-lookup"><span data-stu-id="7dea4-155">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="7dea4-156">これは、次の場合には発生しません。</span><span class="sxs-lookup"><span data-stu-id="7dea4-156">This should not occur during:</span></span>

- <span data-ttu-id="7dea4-157">月単位のサービス更新を行っているデバイス</span><span class="sxs-lookup"><span data-stu-id="7dea4-157">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="7dea4-158">メソッドに対処する:</span><span class="sxs-lookup"><span data-stu-id="7dea4-158">Work around methods:</span></span>

- <span data-ttu-id="7dea4-159">PIN、パスワード、虹彩、Web 認証、FIDO2 キーなどのサインイン方法。</span><span class="sxs-lookup"><span data-stu-id="7dea4-159">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="7dea4-160">デバイスの PIN を記憶できず、他の認証方法を使用できない場合、ユーザーは [手動の reflashing モード](hololens-recovery.md#manual-procedure)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7dea4-160">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

[<span data-ttu-id="7dea4-161">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="7dea4-161">Back to list</span></span>](#list)

## <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="7dea4-162">Microsoft Edge を起動できない</span><span class="sxs-lookup"><span data-stu-id="7dea4-162">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="7dea4-163">この問題は、もともと Microsoft Edge の出荷バージョンで作成されています。</span><span class="sxs-lookup"><span data-stu-id="7dea4-163">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="7dea4-164">この問題は、[新しい Microsoft Edge](hololens-new-edge.md)で解決される場合があります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-164">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="7dea4-165">そうでない場合は、フィードバックをお送りください。</span><span class="sxs-lookup"><span data-stu-id="7dea4-165">If it is not, please file feedback.</span></span>

<span data-ttu-id="7dea4-166">いくつかのお客様が、Microsoft Edge を起動できないという問題を報告しています。</span><span class="sxs-lookup"><span data-stu-id="7dea4-166">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="7dea4-167">このようなお客様の場合、問題は再起動によって引き続き発生し、Windows またはアプリケーションの更新プログラムでは解決されません。</span><span class="sxs-lookup"><span data-stu-id="7dea4-167">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="7dea4-168">この問題が発生して[いて Windows が最新](hololens-updates.md#manually-check-for-updates)であることを確認した場合は、[フィードバックハブアプリ](hololens-feedback.md)から次のカテゴリとサブカテゴリを使用してバグを報告してください: インストールと更新 >、Windows Update のダウンロード、インストール、および構成を行います。</span><span class="sxs-lookup"><span data-stu-id="7dea4-168">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="7dea4-169">これまでに根本原因を根本的に解決できないため、既知の回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="7dea4-169">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="7dea4-170">フィードバックハブを使用してバグを提出すると、調査に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7dea4-170">Filing a bug via Feedback Hub will help our investigation!</span></span> <span data-ttu-id="7dea4-171">これは **既知の問題** です。</span><span class="sxs-lookup"><span data-stu-id="7dea4-171">This is a **known issue**.</span></span>

[<span data-ttu-id="7dea4-172">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="7dea4-172">Back to list</span></span>](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a><span data-ttu-id="7dea4-173">キーボードが特殊文字に切り替わることはありません</span><span class="sxs-lookup"><span data-stu-id="7dea4-173">Keyboard doesn't switch to special characters</span></span>

<span data-ttu-id="7dea4-174">OOBE 中に、ユーザーが職場または学校のアカウントを選択してパスワードを入力した後に、[&123] ボタンをタップしてキーボードの特殊文字に切り替えようとしたときに、特殊文字に変更されないという問題があります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-174">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> <span data-ttu-id="7dea4-175">これは **既知の問題** です。</span><span class="sxs-lookup"><span data-stu-id="7dea4-175">This is a **known issue**.</span></span>

<span data-ttu-id="7dea4-176">回避策:</span><span class="sxs-lookup"><span data-stu-id="7dea4-176">Work-arounds:</span></span>
-   <span data-ttu-id="7dea4-177">キーボードを閉じて、[テキスト] フィールドをタップして再度開きます。</span><span class="sxs-lookup"><span data-stu-id="7dea4-177">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="7dea4-178">パスワードが正しく入力できません。</span><span class="sxs-lookup"><span data-stu-id="7dea4-178">Incorrectly enter your password.</span></span> <span data-ttu-id="7dea4-179">キーボードが次に再起動されると、正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-179">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="7dea4-180">Web 認証。キーボードを閉じ、[ **別のデバイスからサインイン** する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-180">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="7dea4-181">数値のみを入力した場合、ユーザーは特定のキーを押したままにして、展開されたメニューを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="7dea4-181">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="7dea4-182">USB キーボードを使用する。</span><span class="sxs-lookup"><span data-stu-id="7dea4-182">Using a USB keyboard.</span></span>

<span data-ttu-id="7dea4-183">これは、次のようには影響しません。</span><span class="sxs-lookup"><span data-stu-id="7dea4-183">This does not affect:</span></span>
- <span data-ttu-id="7dea4-184">個人のアカウントを使用することを選択したユーザー。</span><span class="sxs-lookup"><span data-stu-id="7dea4-184">Users who choose to use a personal account.</span></span>

[<span data-ttu-id="7dea4-185">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="7dea4-185">Back to list</span></span>](#list)

## <a name="downloading-locked-files-doesnt-error"></a><span data-ttu-id="7dea4-186">ロックされたファイルのダウンロードエラー</span><span class="sxs-lookup"><span data-stu-id="7dea4-186">Downloading locked files doesn't error</span></span>

> [!NOTE]
> <span data-ttu-id="7dea4-187">これは、Windows Insider build バージョン20348.1403 で修正された **既知の問題** です。</span><span class="sxs-lookup"><span data-stu-id="7dea4-187">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span>

<span data-ttu-id="7dea4-188">Windows Holographic の以前のビルドでは、ロックされたファイルをダウンロードしようとすると、結果は HTTP エラーページになります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-188">In previous builds of Windows Holographic, when attempting to download a locked file, the result would be an HTTP error page.</span></span> <span data-ttu-id="7dea4-189">Windows Holographic バージョン21h1 更新プログラムでは、ロックされたファイルをダウンロードしようとしても、何も表示されません。ファイルはダウンロードされず、エラーもありません。</span><span class="sxs-lookup"><span data-stu-id="7dea4-189">In the Windows Holographic, version 21H1 update, trying to download a locked file results in nothing visible happening—the file doesn’t download and there’s no error.</span></span>

[<span data-ttu-id="7dea4-190">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="7dea4-190">Back to list</span></span>](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a><span data-ttu-id="7dea4-191">デバイスポータルファイルのアップロード/ダウンロードがタイムアウトする</span><span class="sxs-lookup"><span data-stu-id="7dea4-191">Device Portal file upload/download times out</span></span>
> [!NOTE]
> <span data-ttu-id="7dea4-192">これは、Windows Insider build バージョン20348.1403 で修正された **既知の問題** です。</span><span class="sxs-lookup"><span data-stu-id="7dea4-192">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span> <span data-ttu-id="7dea4-193">回避策の一環として SSL 接続を無効にした場合は、再度有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7dea4-193">If you previously disabled SSL Connection as part of the workaround, we highly recommend you re-enable it.</span></span>


<span data-ttu-id="7dea4-194">一部のお客様は、ファイルをアップロードまたはダウンロードしようとすると、操作がハングし、タイムアウトになるか、完了しないように見えることがあります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-194">Some customers have found, when attempting to upload or download files, the operation might appear to hang and then time out or never complete.</span></span> <span data-ttu-id="7dea4-195">これは、"ファイルがロックされています[" という既知の問題](#downloading-locked-files-doesnt-error)とは別のものです。これは Windows Holographic、バージョン2004、20h2、21h1 のマーケットビルドに影響します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-195">This is separate from the '[file locked' known issue](#downloading-locked-files-doesnt-error) -- this affects Windows Holographic, versions 2004, 20H2 and 21H1 in-market builds.</span></span> <span data-ttu-id="7dea4-196">この問題は、デバイスポータルで特定の要求を処理するときのバグに起因し、既定の https を使用する場合に最も一貫してヒットしています。</span><span class="sxs-lookup"><span data-stu-id="7dea4-196">The problem has been root caused to a bug in Device Portal's handling of certain requests, and is most consistently hit when using https, which is the default.</span></span> 

### <a name="workaround"></a><span data-ttu-id="7dea4-197">回避策</span><span class="sxs-lookup"><span data-stu-id="7dea4-197">Workaround</span></span>

<span data-ttu-id="7dea4-198">この回避策は Wi-Fi と UsbNcm に同様に適用されますが、[SSL 接続] の下の [必須] オプションを無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7dea4-198">This workaround, which applies equally to Wi-Fi and UsbNcm, is to disable the "required" option under "SSL Connection".</span></span> <span data-ttu-id="7dea4-199">これを行うには、[デバイスポータル]、[ **システム**] の順に移動し、[ **基本設定** ] ページを選択します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-199">To do so, navigate to Device Portal, **System**, and select the **Preferences** page.</span></span> <span data-ttu-id="7dea4-200">[ **デバイスのセキュリティ** ] セクションで、[ **SSL 接続**] を見つけて、[ **必須** の無効化] をオフにします。</span><span class="sxs-lookup"><span data-stu-id="7dea4-200">In the **Device Security** section, locate **SSL Connection**, and uncheck to disable **Required**.</span></span>

<span data-ttu-id="7dea4-201">ユーザーは、https://(IP アドレス) ではなく http://にアクセスし、ファイルのアップロードやダウンロードなどの機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7dea4-201">The user should then go to http://, not https:// (IP address) and features like file upload and download will work.</span></span>

[<span data-ttu-id="7dea4-202">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="7dea4-202">Back to list</span></span>](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a><span data-ttu-id="7dea4-203">Insider build を使用してフラッシュされたデバイスで Insider preview から登録解除した後のブルースクリーン</span><span class="sxs-lookup"><span data-stu-id="7dea4-203">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>

<span data-ttu-id="7dea4-204">これは、insider preview ビルドを使用しており、HoloLens 2 を新しい insider preview ビルドで reflashed した後、insider プログラムから登録解除されたユーザーに影響する問題です。</span><span class="sxs-lookup"><span data-stu-id="7dea4-204">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> <span data-ttu-id="7dea4-205">これは **既知の問題** です。</span><span class="sxs-lookup"><span data-stu-id="7dea4-205">This is a **known issue**.</span></span>

<span data-ttu-id="7dea4-206">これは、次のようには影響しません。</span><span class="sxs-lookup"><span data-stu-id="7dea4-206">This does not affect:</span></span>
- <span data-ttu-id="7dea4-207">Windows Insider に登録されていないユーザー</span><span class="sxs-lookup"><span data-stu-id="7dea4-207">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="7dea4-208">Insider</span><span class="sxs-lookup"><span data-stu-id="7dea4-208">Insiders:</span></span>
    - <span data-ttu-id="7dea4-209">Insider ビルドがバージョン 18362. x であるためにデバイスが登録されている場合</span><span class="sxs-lookup"><span data-stu-id="7dea4-209">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="7dea4-210">内部で署名された19041ビルドをフラッシュし、Insider プログラムに登録したままにする場合</span><span class="sxs-lookup"><span data-stu-id="7dea4-210">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="7dea4-211">回避策:</span><span class="sxs-lookup"><span data-stu-id="7dea4-211">Work-around:</span></span> 
- <span data-ttu-id="7dea4-212">問題を回避する</span><span class="sxs-lookup"><span data-stu-id="7dea4-212">Avoid the issue</span></span> 
    - <span data-ttu-id="7dea4-213">Insider 以外のビルドをフラッシュします。</span><span class="sxs-lookup"><span data-stu-id="7dea4-213">Flash a non-insider build.</span></span> <span data-ttu-id="7dea4-214">毎月の定期的な更新の1つ。</span><span class="sxs-lookup"><span data-stu-id="7dea4-214">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="7dea4-215">Insider Preview を維持</span><span class="sxs-lookup"><span data-stu-id="7dea4-215">Stay on Insider Preview</span></span>
- <span data-ttu-id="7dea4-216">デバイスの更新</span><span class="sxs-lookup"><span data-stu-id="7dea4-216">Reflash the device</span></span>

    1. <span data-ttu-id="7dea4-217">接続されていない状態で完全に電源を切ることによって、HoloLens 2 を手動で[点滅モードに](hololens-recovery.md)します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-217">Put the [HoloLens 2 into flashing mode](hololens-recovery.md) manually by fully powering down while not connect.</span></span> <span data-ttu-id="7dea4-218">音量を上げたまま、[電源] ボタンをタップします。</span><span class="sxs-lookup"><span data-stu-id="7dea4-218">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="7dea4-219">PC に Connect し、高度な回復コンパニオンを開きます。</span><span class="sxs-lookup"><span data-stu-id="7dea4-219">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="7dea4-220">HoloLens 2 を既定のビルドにフラッシュします。</span><span class="sxs-lookup"><span data-stu-id="7dea4-220">Flash the HoloLens 2 to the default build.</span></span>

[<span data-ttu-id="7dea4-221">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="7dea4-221">Back to list</span></span>](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a><span data-ttu-id="7dea4-222">画像が自動的にアップロードされない OneDrive</span><span class="sxs-lookup"><span data-stu-id="7dea4-222">OneDrive doesn't automatically upload pictures</span></span>

<span data-ttu-id="7dea4-223">HoloLens 用の OneDrive アプリでは、職場または学校アカウントのカメラの自動アップロードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7dea4-223">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span> <span data-ttu-id="7dea4-224">これは **既知の問題** です。</span><span class="sxs-lookup"><span data-stu-id="7dea4-224">This is a **known issue**.</span></span>

<span data-ttu-id="7dea4-225">回避策:</span><span class="sxs-lookup"><span data-stu-id="7dea4-225">Workarounds:</span></span>

- <span data-ttu-id="7dea4-226">お客様のビジネスで利用可能な場合、カメラの自動アップロードはコンシューマーの Microsoft アカウントでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7dea4-226">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="7dea4-227">職場または学校のアカウントに加えて、Microsoft アカウントにサインインできます (OneDrive アプリではデュアルサインインがサポートされています)。</span><span class="sxs-lookup"><span data-stu-id="7dea4-227">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="7dea4-228">OneDrive 内の Microsoft アカウントプロファイルから、自動、バックグラウンドカメラロールのアップロードを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7dea4-228">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="7dea4-229">写真を自動的にアップロードするためにコンシューマー Microsoft アカウントを安全に使用できない場合は、OneDrive アプリから職場または学校のアカウントに写真を手動でアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="7dea4-229">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="7dea4-230">これを行うには、OneDrive アプリで職場または学校のアカウントにサインインしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-230">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="7dea4-231">ボタンを選択し、[ **+** **アップロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-231">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="7dea4-232">[ **ピクチャ > カメラロール** に移動して、アップロードする写真またはビデオを検索します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-232">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="7dea4-233">アップロードする写真またはビデオを選択し、[ **開く** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-233">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

[<span data-ttu-id="7dea4-234">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="7dea4-234">Back to list</span></span>](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a><span data-ttu-id="7dea4-235">HoloLens が応答していないか、開始されていません</span><span class="sxs-lookup"><span data-stu-id="7dea4-235">HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="7dea4-236">HoloLens が開始されない場合:</span><span class="sxs-lookup"><span data-stu-id="7dea4-236">If your HoloLens won't start:</span></span>

- <span data-ttu-id="7dea4-237">電源ボタンの横にある Led が点灯していない場合、または LED が少し点滅している場合は、 [HoloLens の料金](hololens2-charging.md#charging-the-device)が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-237">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens2-charging.md#charging-the-device)</span></span>
- <span data-ttu-id="7dea4-238">電源ボタンを押したときに Led が点灯しても、ディスプレイに何も表示されない場合は、 [デバイスをハードリセット](hololens-recovery.md#hard-reset-procedure)します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-238">If the LEDs light up when you press the power button but you can't see anything on the displays, [do a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="7dea4-239">HoloLens がフリーズまたは応答しなくなった場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-239">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="7dea4-240">電源ボタンを押して、5つの led がすべてオフになるまで、または led が応答していない場合は15秒間、HoloLens をオフにします。</span><span class="sxs-lookup"><span data-stu-id="7dea4-240">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="7dea4-241">HoloLens を開始するには、[電源] ボタンをもう一度押します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-241">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="7dea4-242">これらの手順がうまくいかない場合は、HoloLens 2 デバイスまたは[HoloLens (第1世代) デバイス](hololens1-recovery.md)[の回復](hololens-recovery.md)を試すことができます。</span><span class="sxs-lookup"><span data-stu-id="7dea4-242">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

[<span data-ttu-id="7dea4-243">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="7dea4-243">Back to list</span></span>](#list)

## <a name="low-disk-space-error"></a><span data-ttu-id="7dea4-244">"ディスク領域が不足しています" エラー</span><span class="sxs-lookup"><span data-stu-id="7dea4-244">"Low Disk Space" error</span></span>

<span data-ttu-id="7dea4-245">次の1つまたは複数の操作を行って、記憶域スペースを解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-245">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="7dea4-246">未使用の領域をいくつか削除します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-246">Delete some unused spaces.</span></span> <span data-ttu-id="7dea4-247">[**設定** システムスペース] にアクセスして  >    >  、不要になった領域を選択し、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-247">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="7dea4-248">配置したホログラムの一部を削除します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-248">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="7dea4-249">写真アプリから一部の画像とビデオを削除します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-249">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="7dea4-250">HoloLens から一部のアプリをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="7dea4-250">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="7dea4-251">[ **すべてのアプリ** ] 一覧で、アンインストールするアプリをタップして保持し、[ **アンインストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-251">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

[<span data-ttu-id="7dea4-252">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="7dea4-252">Back to list</span></span>](#list)

## <a name="calibration-fails"></a><span data-ttu-id="7dea4-253">調整が失敗する</span><span class="sxs-lookup"><span data-stu-id="7dea4-253">Calibration fails</span></span>

<span data-ttu-id="7dea4-254">調整はほとんどの従業員に対して機能しますが、調整が失敗する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-254">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="7dea4-255">調整エラーの考えられる原因には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-255">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="7dea4-256">調整ターゲットに従うのではなく、気をかける</span><span class="sxs-lookup"><span data-stu-id="7dea4-256">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="7dea4-257">ダーティまたは傷のあるデバイスのバイザーまたはデバイスのバイザーが適切に配置されていない</span><span class="sxs-lookup"><span data-stu-id="7dea4-257">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="7dea4-258">汚れまたは傷</span><span class="sxs-lookup"><span data-stu-id="7dea4-258">Dirty or scratched glasses</span></span>
- <span data-ttu-id="7dea4-259">特定の種類の連絡先レンズとグラス (色分けされたコンタクトレンズ、一部の toric 連絡先レンズ、IR ブロックグラス、高処方箋グラス、サングラス、類似)</span><span class="sxs-lookup"><span data-stu-id="7dea4-259">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="7dea4-260">その他の発音と eyelash の拡張機能</span><span class="sxs-lookup"><span data-stu-id="7dea4-260">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="7dea4-261">デバイスが目に見えないようにブロックしている場合は、ヘアまたは太 eyeglass フレーム</span><span class="sxs-lookup"><span data-stu-id="7dea4-261">Hair or thick eyeglass frames if they're blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="7dea4-262">特定の目の physiology、視線、eyelashes、amblyopia、n agmu、LASIK またはその他の目のような目になることがあります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-262">Certain eye physiology, eye conditions, or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="7dea4-263">調整が失敗した場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7dea4-263">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="7dea4-264">デバイスのバイザーをクリーニングしています</span><span class="sxs-lookup"><span data-stu-id="7dea4-264">Cleaning your device visor</span></span>
- <span data-ttu-id="7dea4-265">グラスをクリーニングする</span><span class="sxs-lookup"><span data-stu-id="7dea4-265">Cleaning your glasses</span></span>
- <span data-ttu-id="7dea4-266">デバイスバイザーをできるだけ近くにプッシュする</span><span class="sxs-lookup"><span data-stu-id="7dea4-266">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="7dea4-267">バイザーでのオブジェクトの移動 (髪など)</span><span class="sxs-lookup"><span data-stu-id="7dea4-267">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="7dea4-268">部屋のライトをオンにする、または直接日光を切る</span><span class="sxs-lookup"><span data-stu-id="7dea4-268">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="7dea4-269">すべてのガイドラインに従い、調整が引き続き失敗する場合は、設定で調整のプロンプトを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7dea4-269">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="7dea4-270">また、 [フィードバックハブ](hololens-feedback.md)でフィードバックを提出してお知らせください。</span><span class="sxs-lookup"><span data-stu-id="7dea4-270">Also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="7dea4-271">[イメージの色または明るさのトラブルシューティング](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)に関する関連情報も参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dea4-271">Also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="7dea4-272">視線位置はシステムによって計算されるため、IPD の設定は HoloLens 2 には適用されません。</span><span class="sxs-lookup"><span data-stu-id="7dea4-272">Setting IPD is not applicable for HoloLens 2, since eye positions are computed by the system.</span></span> 

[<span data-ttu-id="7dea4-273">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="7dea4-273">Back to list</span></span>](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a><span data-ttu-id="7dea4-274">HoloLens が既に他のユーザーに設定されているため、サインインできません</span><span class="sxs-lookup"><span data-stu-id="7dea4-274">Can't sign in because my HoloLens was previously set up for someone else</span></span>

<span data-ttu-id="7dea4-275">デバイスを [**点滅モード** にし、Advanced Recovery コンパニオンを使用](hololens-recovery.md#clean-reflash-the-device)してデバイスを回復することができます。</span><span class="sxs-lookup"><span data-stu-id="7dea4-275">You can [put the device into **Flashing Mode** and use Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) to recover the device.</span></span>

[<span data-ttu-id="7dea4-276">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="7dea4-276">Back to list</span></span>](#list)


## <a name="unity-isnt-working"></a><span data-ttu-id="7dea4-277">Unity が動作しない</span><span class="sxs-lookup"><span data-stu-id="7dea4-277">Unity isn't working</span></span>

- <span data-ttu-id="7dea4-278">HoloLens 開発に推奨される Unity の最新バージョン用の[ツールをインストール](/windows/mixed-reality/install-the-tools)することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7dea4-278">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="7dea4-279">unity HoloLens Technical Preview の既知の問題については、 [HoloLens unity フォーラム](https://forum.unity3d.com/threads/known-issues.394627/)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7dea4-279">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

[<span data-ttu-id="7dea4-280">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="7dea4-280">Back to list</span></span>](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a><span data-ttu-id="7dea4-281">Windowsデバイスポータルが正しく動作していません</span><span class="sxs-lookup"><span data-stu-id="7dea4-281">Windows Device Portal isn't working correctly</span></span>

- <span data-ttu-id="7dea4-282">Mixed Reality キャプチャのライブプレビュー機能は、数秒の待機時間が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-282">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="7dea4-283">[仮想入力] ページで、[仮想ジェスチャ] セクションのジェスチャとスクロールコントロールが機能していません。</span><span class="sxs-lookup"><span data-stu-id="7dea4-283">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="7dea4-284">使用すると、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="7dea4-284">Using them will have no effect.</span></span> <span data-ttu-id="7dea4-285">仮想入力ページの仮想キーボードが正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-285">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="7dea4-286">設定で開発者モードを有効にした後、デバイスポータルをオンにするスイッチが有効になるまで数秒かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-286">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

[<span data-ttu-id="7dea4-287">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="7dea4-287">Back to list</span></span>](#list)

## <a name="the-hololens-emulator-isnt-working"></a><span data-ttu-id="7dea4-288">HoloLens Emulator が機能していません</span><span class="sxs-lookup"><span data-stu-id="7dea4-288">The HoloLens Emulator isn't working</span></span>

<span data-ttu-id="7dea4-289">HoloLens エミュレーターに関する情報は、開発者向けのドキュメントにあります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-289">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="7dea4-290">[HoloLens エミュレーターのトラブルシューティングの](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dea4-290">Read more about [troubleshooting the HoloLens emulator](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).</span></span>


- <span data-ttu-id="7dea4-291">Microsoft Store の一部のアプリは、エミュレーターと互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="7dea4-291">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="7dea4-292">たとえば、若い Conker とフラグメントは、エミュレーターでは再生できません。</span><span class="sxs-lookup"><span data-stu-id="7dea4-292">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="7dea4-293">Emulator では、PC web カメラを使用できません。</span><span class="sxs-lookup"><span data-stu-id="7dea4-293">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="7dea4-294">Windows デバイスポータルのライブプレビュー機能は、エミュレーターでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="7dea4-294">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="7dea4-295">混合した現実のビデオとイメージをキャプチャすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7dea4-295">You can still capture Mixed Reality videos and images.</span></span>

[<span data-ttu-id="7dea4-296">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="7dea4-296">Back to list</span></span>](#list)

## <a name="voice-commands-arent-working"></a><span data-ttu-id="7dea4-297">音声コマンドが動作していません</span><span class="sxs-lookup"><span data-stu-id="7dea4-297">Voice commands aren't working</span></span>

<span data-ttu-id="7dea4-298">Cortana が音声コマンドに応答しない場合は、Cortana が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-298">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="7dea4-299">[すべてのアプリ] の一覧で **Cortana**  >  **メニュー** ノートブック設定を選択して  >    >  変更を行います。</span><span class="sxs-lookup"><span data-stu-id="7dea4-299">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="7dea4-300">説明できることの詳細については、「 [HoloLens での音声の使用](hololens-cortana.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dea4-300">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

<span data-ttu-id="7dea4-301">HoloLens (第1世代) では、組み込み音声認識は構成できません。</span><span class="sxs-lookup"><span data-stu-id="7dea4-301">On HoloLens (1st gen), built-in speech recognition is not configurable.</span></span> <span data-ttu-id="7dea4-302">常に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="7dea4-302">It is always turned on.</span></span> <span data-ttu-id="7dea4-303">HoloLens 2 では、デバイスのセットアップ時に音声認識と Cortana の両方をオンにするかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7dea4-303">On HoloLens 2, you can choose whether to turn on both speech recognition and Cortana during device setup.</span></span>

<span data-ttu-id="7dea4-304">HoloLens 2 が音声に応答していない場合は、音声認識が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-304">If your HoloLens 2 is not responding to your voice, make sure Speech recognition is turned on.</span></span> <span data-ttu-id="7dea4-305">[**スタート**  >  **設定**  >  **のプライバシー** に関する音声] を開き  >   、**音声認識** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="7dea4-305">Go to **Start** > **Settings** > **Privacy** > **Speech** and turn on **Speech recognition**.</span></span>

[<span data-ttu-id="7dea4-306">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="7dea4-306">Back to list</span></span>](#list)

## <a name="hand-input-isnt-working"></a><span data-ttu-id="7dea4-307">手書き入力が機能していません</span><span class="sxs-lookup"><span data-stu-id="7dea4-307">Hand input isn't working</span></span>

<span data-ttu-id="7dea4-308">HoloLens が自分の手を見えるようにするには、ジェスチャフレームに保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-308">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="7dea4-309">Mixed Reality ホームでは、自分がどのように追跡されるかを知ることができるフィードバックが提供されます。</span><span class="sxs-lookup"><span data-stu-id="7dea4-309">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="7dea4-310">HoloLens のバージョンによって、次のようなフィードバックが異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-310">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="7dea4-311">HoloLens (第1世代) では、宝石カーソルがドットからリングに変わります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-311">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="7dea4-312">HoloLens 2 では、指先カーソルがスレートの近くにあると表示され、スレートがさらに離れたときにハンドレイが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7dea4-312">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="7dea4-313">多くのイマーシブアプリは、Mixed Reality ホームに似た入力パターンに従います。</span><span class="sxs-lookup"><span data-stu-id="7dea4-313">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="7dea4-314">[HoloLens (第1世代)](hololens1-basic-usage.md#use-hololens-with-your-hands)と[HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame)で手書き入力を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-314">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="7dea4-315">手袋を装着している場合は、一部の種類の手袋がハンドトラッキングで動作しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7dea4-315">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="7dea4-316">一般的な例としては、赤外線信号を吸収する傾向があり、深度カメラでは選択されていない黒色のゴムグローブがあります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-316">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="7dea4-317">ゴムグローブが使用されている場合は、青や灰色などの明るい色を試すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7dea4-317">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="7dea4-318">もう1つの例として、大きな baggy グローブがあります。これは、手の形が見えにくくなる傾向があります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-318">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="7dea4-319">最良の結果を得るには、できるだけフォーム継ぎ手として手袋を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7dea4-319">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="7dea4-320">バイザーに指紋または汚れがある場合は、HoloLens に付属しているマイクロファイバークリーニング布を使用して、バイザーをゆっくりとクリーニングします。</span><span class="sxs-lookup"><span data-stu-id="7dea4-320">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

[<span data-ttu-id="7dea4-321">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="7dea4-321">Back to list</span></span>](#list)

## <a name="cant-connect-to-wi-fi"></a><span data-ttu-id="7dea4-322">Wi-Fi に接続できません</span><span class="sxs-lookup"><span data-stu-id="7dea4-322">Can't connect to Wi-Fi</span></span>

<span data-ttu-id="7dea4-323">HoloLens を Wi-Fi ネットワークに接続できない場合は、次の点を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="7dea4-323">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

- <span data-ttu-id="7dea4-324">Wi-Fi が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-324">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="7dea4-325">確認するには、開始ジェスチャを使用して、[**設定** ネットワーク] [  >  **&amp; インターネット** wi-fi] の順に選択し  >  ます。</span><span class="sxs-lookup"><span data-stu-id="7dea4-325">To check, use the Start gesture, then select **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="7dea4-326">Wi-Fi がオンになっている場合は、オフにしてから再度有効にしてみてください。</span><span class="sxs-lookup"><span data-stu-id="7dea4-326">If Wi-Fi is on, try turning it off and then on again.</span></span>
- <span data-ttu-id="7dea4-327">ルーターまたはアクセスポイントに近い場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-327">Move closer to the router or access point.</span></span>
- <span data-ttu-id="7dea4-328">Wi-Fi ルーターを再起動し、 [HoloLens を再起動](hololens-recovery.md)します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-328">Restart your Wi-Fi router, then [restart HoloLens](hololens-recovery.md).</span></span> <span data-ttu-id="7dea4-329">接続を再試行してください。</span><span class="sxs-lookup"><span data-stu-id="7dea4-329">Try connecting again.</span></span>
- <span data-ttu-id="7dea4-330">これらの問題が解決しない場合は、ルーターが最新のファームウェアを使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7dea4-330">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="7dea4-331">この情報については、製造元の web サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dea4-331">You can find this information on the manufacturer website.</span></span>

[<span data-ttu-id="7dea4-332">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="7dea4-332">Back to list</span></span>](#list)

## <a name="bluetooth-devices-arent-pairing"></a><span data-ttu-id="7dea4-333">Bluetooth デバイスがペアリングしていない</span><span class="sxs-lookup"><span data-stu-id="7dea4-333">Bluetooth devices aren't pairing</span></span>

<span data-ttu-id="7dea4-334">[Bluetooth デバイスのペアリング](hololens-connect-devices.md)で問題が発生した場合は、次の操作を試してください。</span><span class="sxs-lookup"><span data-stu-id="7dea4-334">If you're having problems [pairing a Bluetooth device](hololens-connect-devices.md), try the following:</span></span>

- <span data-ttu-id="7dea4-335">**設定**  >  **デバイス** にアクセスし、Bluetooth が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-335">Go to **Settings** > **Devices**, and make sure that Bluetooth is turned on.</span></span> <span data-ttu-id="7dea4-336">有効になっている場合は、オフにしてから再びオンにします。</span><span class="sxs-lookup"><span data-stu-id="7dea4-336">If it is, turn it off and on again.</span></span>
- <span data-ttu-id="7dea4-337">Bluetooth デバイスが完全に充電されていること、または電池が最新であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-337">Make sure that your Bluetooth device is fully charged or has fresh batteries.</span></span>
- <span data-ttu-id="7dea4-338">それでも接続できない場合は、 [HoloLens を再起動](hololens-recovery.md)します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-338">If you still can't connect, [restart the HoloLens](hololens-recovery.md).</span></span>

[<span data-ttu-id="7dea4-339">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="7dea4-339">Back to list</span></span>](#list)

## <a name="usb-c-microphone-isnt-working"></a><span data-ttu-id="7dea4-340">USB C マイクが動作していない</span><span class="sxs-lookup"><span data-stu-id="7dea4-340">USB-C Microphone isn't working</span></span>
<span data-ttu-id="7dea4-341">USB C のマイクによっては、マイク *と* スピーカーの両方として誤って報告されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7dea4-341">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="7dea4-342">これは、HoloLens ではなく、マイクに問題があります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-342">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="7dea4-343">これらのマイクの1つを HoloLens に接続すると、サウンドが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-343">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="7dea4-344">幸いにも、簡単な修正があります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-344">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="7dea4-345">**設定**  ->  **システム**  ->  **サウンド** で、組み込みのスピーカー **(アナログ機能オーディオドライバー)** を **既定のデバイス** として明示的に設定します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-345">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="7dea4-346">マイクが取り外され、後で再接続された場合でも、HoloLens はこの設定を記憶する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-346">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![USB C マイクのトラブルシューティング](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a><span data-ttu-id="7dea4-348">設定で使用可能と表示されているデバイスが動作しない</span><span class="sxs-lookup"><span data-stu-id="7dea4-348">Devices listed as available in Settings don't work</span></span>

<span data-ttu-id="7dea4-349">HoloLens (第1世代) では Bluetooth オーディオプロファイルはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7dea4-349">HoloLens (1st gen) doesn't support Bluetooth audio profiles.</span></span> <span data-ttu-id="7dea4-350">スピーカーやヘッドセットなどの Bluetooth オーディオデバイスは、HoloLens 設定で使用できるように見えることがありますが、これらはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7dea4-350">Bluetooth audio devices, such as speakers and headsets, may appear as available in HoloLens settings, but they aren't supported.</span></span>

<span data-ttu-id="7dea4-351">HoloLens 2 は、ステレオ再生用の Bluetooth A2DP audio プロファイルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7dea4-351">HoloLens 2 supports the Bluetooth A2DP audio profile for stereo playback.</span></span> <span data-ttu-id="7dea4-352">Bluetooth 周辺機器からのマイクキャプチャを有効にする Bluetooth ハンドフリープロファイルは、HoloLens 2 ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7dea4-352">The Bluetooth Hands Free profile which enables microphone capture from a Bluetooth peripheral is not supported on HoloLens 2.</span></span>

<span data-ttu-id="7dea4-353">Bluetooth デバイスの使用に問題がある場合は、それがサポートされているデバイスであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7dea4-353">If you're having trouble using a Bluetooth device, make sure that it's a supported device.</span></span> <span data-ttu-id="7dea4-354">サポートされているデバイスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7dea4-354">Supported devices include the following:</span></span>

- <span data-ttu-id="7dea4-355">英語の QWERTY Bluetooth キーボード (holographic キーボードを使用する任意の場所で使用できます)。</span><span class="sxs-lookup"><span data-stu-id="7dea4-355">English-language QWERTY Bluetooth keyboards (you can use these anywhere that you use the holographic keyboard).</span></span>
- <span data-ttu-id="7dea4-356">マウスを Bluetooth します。</span><span class="sxs-lookup"><span data-stu-id="7dea4-356">Bluetooth mice.</span></span>
- <span data-ttu-id="7dea4-357">[HoloLens clicker](hololens1-clicker.md)。</span><span class="sxs-lookup"><span data-stu-id="7dea4-357">The [HoloLens clicker](hololens1-clicker.md).</span></span>

<span data-ttu-id="7dea4-358">他の Bluetooth HID および GATT デバイスを HoloLens とペアリングできます。</span><span class="sxs-lookup"><span data-stu-id="7dea4-358">You can pair other Bluetooth HID and GATT devices together with your HoloLens.</span></span> <span data-ttu-id="7dea4-359">ただし、デバイスを実際に使用するには、Microsoft Store から対応するコンパニオンアプリをインストールすることが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7dea4-359">However, you may have to install corresponding companion apps from Microsoft Store to actually use the devices.</span></span>

[<span data-ttu-id="7dea4-360">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="7dea4-360">Back to list</span></span>](#list)
