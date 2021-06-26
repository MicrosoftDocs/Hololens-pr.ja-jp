---
title: Microsoft HoloLens の Insider Preview
description: 次の主要なオペレーティングシステム更新プログラム (HoloLens) について、Insider ビルドの使用を開始し、貴重なフィードバックを提供する方法について説明します。
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
ms.openlocfilehash: a4949ab68121cb772fdb8a62411ed70868a6ccb6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924368"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="1efef-103">Microsoft HoloLens の Insider Preview</span><span class="sxs-lookup"><span data-stu-id="1efef-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="1efef-104">HoloLens 用の最新の Insider Preview ビルドへようこそ。</span><span class="sxs-lookup"><span data-stu-id="1efef-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="1efef-105">この機能は簡単に [開始](hololens-insider.md#start-receiving-insider-builds) でき、HoloLens の次の主なオペレーティングシステムの更新に関する貴重なフィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="1efef-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="1efef-106">Windows Insider リリースノート</span><span class="sxs-lookup"><span data-stu-id="1efef-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="1efef-107">Windows Insider の新機能を再び開始します。</span><span class="sxs-lookup"><span data-stu-id="1efef-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="1efef-108">新しいビルドは、最新の更新プログラムの開発およびベータチャネルに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="1efef-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="1efef-109">Windows Insider ビルドに機能と更新プログラムを追加すると、このページは引き続き更新されます。</span><span class="sxs-lookup"><span data-stu-id="1efef-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="1efef-110">これらの更新プログラムを実際のものに混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="1efef-110">Get excited and ready to mix these updates into your reality.</span></span> 

### <a name="csp-changes-on-hololens"></a><span data-ttu-id="1efef-111">HoloLens での CSP の変更</span><span class="sxs-lookup"><span data-stu-id="1efef-111">CSP changes on HoloLens</span></span>
 
- <span data-ttu-id="1efef-112">Windows Insider build 20348.1403 で導入されました</span><span class="sxs-lookup"><span data-stu-id="1efef-112">Introduced in Windows Insider build, 20348.1403</span></span>

#### <a name="devdetail-csp"></a><span data-ttu-id="1efef-113">DevDetail CSP</span><span class="sxs-lookup"><span data-stu-id="1efef-113">DevDetail CSP</span></span>

<span data-ttu-id="1efef-114">DevDetail CSP は、HoloLens デバイスの空き記憶領域も報告するようになりました。</span><span class="sxs-lookup"><span data-stu-id="1efef-114">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="1efef-115">これは、[設定] [アプリのストレージ] ページに表示される値とほぼ一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1efef-115">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="1efef-116">この情報を含む特定のノードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="1efef-116">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="1efef-117">./DevDetail/Ext/Microsoft/FreeStorage (GET 操作のみ)</span><span class="sxs-lookup"><span data-stu-id="1efef-117">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp"></a><span data-ttu-id="1efef-118">DeviceStatus CSP</span><span class="sxs-lookup"><span data-stu-id="1efef-118">DeviceStatus CSP</span></span>

<span data-ttu-id="1efef-119">DeviceStatus CSP は、HoloLens がアクティブに接続されている、Wifi ネットワークの SSID と BSSID も報告するようになりました。</span><span class="sxs-lookup"><span data-stu-id="1efef-119">DeviceStatus CSP now also reports SSID and BSSID of Wifi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="1efef-120">この情報を含む特定のノードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="1efef-120">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="1efef-121">*Wi-Fi アダプタ/SSID の/Vendor/MSFT/DeviceStatus/NetworkIdentifiers/mac アドレス*</span><span class="sxs-lookup"><span data-stu-id="1efef-121">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="1efef-122">*Wi-Fi アダプタ/BSSID の/Vendor/MSFT/DeviceStatus/NetworkIdentifiers/mac アドレス*</span><span class="sxs-lookup"><span data-stu-id="1efef-122">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="1efef-123">ネットワーク識別子を照会するための syncml blob の例 (MDM ベンダー向け)</span><span class="sxs-lookup"><span data-stu-id="1efef-123">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="fixes-and-improvements"></a><span data-ttu-id="1efef-124">修正と改善:</span><span class="sxs-lookup"><span data-stu-id="1efef-124">Fixes and improvements:</span></span>

- <span data-ttu-id="1efef-125">[ロックされたファイルをダウンロードするプロンプトがないデバイスポータルの既知の問題を修正しました。](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="1efef-125">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="1efef-126">[ファイルのアップロードとダウンロードのタイムアウトを含むデバイスポータルの既知の問題](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)を修正した。</span><span class="sxs-lookup"><span data-stu-id="1efef-126">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>

## <a name="start-receiving-insider-builds"></a><span data-ttu-id="1efef-127">Insider ビルドの受信を開始します</span><span class="sxs-lookup"><span data-stu-id="1efef-127">Start receiving Insider builds</span></span>
> [!NOTE]
> <span data-ttu-id="1efef-128">最近更新したことがない場合は、デバイスを再起動して状態を更新し、最新のビルドを取得してください。</span><span class="sxs-lookup"><span data-stu-id="1efef-128">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="1efef-129">"デバイスの再起動" 音声コマンドは正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="1efef-129">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="1efef-130">[設定]/[Windows Insider Program] で [再起動] ボタンを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="1efef-130">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="1efef-131">バックエンドには、発生した可能性があるバグがあり、これによって追跡が再開されます。</span><span class="sxs-lookup"><span data-stu-id="1efef-131">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="1efef-132">HoloLens 2 デバイスで、[**設定**  >  ] [**更新 & セキュリティ**] [  >  **Windows Insider program** ] に移動し、[**開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1efef-132">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="1efef-133">Windows Insider として登録するために使用したアカウントをリンクします。</span><span class="sxs-lookup"><span data-stu-id="1efef-133">Link the account you used to register as a Windows Insider.</span></span>
<span data-ttu-id="1efef-134">Windows insider がチャネルに移動するようになりました。</span><span class="sxs-lookup"><span data-stu-id="1efef-134">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="1efef-135">**高速** リングが **開発チャネル** になり、**低速** リングが **ベータチャネル** になり、 **release preview** リングが **release preview チャネル** になります。</span><span class="sxs-lookup"><span data-stu-id="1efef-135">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="1efef-136">マッピングは次のようになります。 ![ Windows insider channel の説明 ](images/WindowsInsiderChannels.png) 詳細については、windows ブログの「windows insider Channel の [概要](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1efef-136">Here is what that mapping looks like: ![Windows Insider Channels explanation](images/WindowsInsiderChannels.png) For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="1efef-137">次に、[ **Windows のアクティブな開発**] を選択し、 **開発チャネル** または **ベータチャネル** のビルドを受信するかどうかを選択して、プログラムの条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="1efef-137">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="1efef-138">[ **Confirm > Restart Now** ] を選択して終了します。</span><span class="sxs-lookup"><span data-stu-id="1efef-138">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="1efef-139">デバイスが再起動したら、[設定] [& のセキュリティ > 更新プログラムをチェックし、最新のビルドを取得するため **の更新プログラムを確認 >** ます。</span><span class="sxs-lookup"><span data-stu-id="1efef-139">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>
### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="1efef-140">Update エラー0x80070490 の回避策</span><span class="sxs-lookup"><span data-stu-id="1efef-140">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="1efef-141">Dev または Beta チャネルで更新するときに更新エラー0x80070490 が発生した場合は、次の短期的な対処を試してください。</span><span class="sxs-lookup"><span data-stu-id="1efef-141">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="1efef-142">これには、insider チャネルを移動し、更新を選択して、Insider channel を戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="1efef-142">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>
#### <a name="stage-one---release-preview"></a><span data-ttu-id="1efef-143">ステージワンリリースプレビュー</span><span class="sxs-lookup"><span data-stu-id="1efef-143">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="1efef-144">[設定]、[更新プログラム & セキュリティ]、[Windows Insider Program] を選択し、[ **Release Preview Channel**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1efef-144">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="1efef-145">設定、更新 & セキュリティ、Windows Update、 **更新を確認** します。</span><span class="sxs-lookup"><span data-stu-id="1efef-145">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="1efef-146">更新後、段階2に進みます。</span><span class="sxs-lookup"><span data-stu-id="1efef-146">After the update, continue on to Stage two.</span></span>
#### <a name="stage-two---dev-channel"></a><span data-ttu-id="1efef-147">ステージ2開発チャネル</span><span class="sxs-lookup"><span data-stu-id="1efef-147">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="1efef-148">[設定]、[更新プログラム & セキュリティ]、[Windows Insider Program] の [ **開発チャネル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1efef-148">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="1efef-149">設定、更新 & セキュリティ、Windows Update、 **更新を確認** します。</span><span class="sxs-lookup"><span data-stu-id="1efef-149">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>
## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="1efef-150">FFU のダウンロードとフラッシュの方向</span><span class="sxs-lookup"><span data-stu-id="1efef-150">FFU download and flash directions</span></span>
<span data-ttu-id="1efef-151">フライト署名済み ffu を使用してテストするには、フライト署名済み ffu を点滅させる前にデバイスのロックを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1efef-151">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="1efef-152">PC の場合:</span><span class="sxs-lookup"><span data-stu-id="1efef-152">On PC:</span></span>
    1. <span data-ttu-id="1efef-153">から PC に ffu をダウンロード [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) します。</span><span class="sxs-lookup"><span data-stu-id="1efef-153">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="1efef-154">Microsoft Store から ARC (Advanced Recovery コンパニオン) をインストール [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) します。</span><span class="sxs-lookup"><span data-stu-id="1efef-154">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="1efef-155">HoloLens-フライトのロック解除: [**設定** の  >  **更新] & セキュリティ**]  >  [**Windows Insider program** ] の順に選択し、サインアップして、デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="1efef-155">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>
1. <span data-ttu-id="1efef-156">Flash FFU-atc を使用して、デジタル署名された FFU をフラッシュできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1efef-156">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>
### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="1efef-157">フィードバックの提供と問題の報告</span><span class="sxs-lookup"><span data-stu-id="1efef-157">Provide feedback and report issues</span></span>
<span data-ttu-id="1efef-158">HoloLens で [フィードバックハブアプリ](hololens-feedback.md) を使用して、フィードバックを提供し、問題を報告してください。</span><span class="sxs-lookup"><span data-stu-id="1efef-158">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="1efef-159">フィードバックハブを使用すると、エンジニアが迅速に問題をデバッグして解決できるように、必要な診断情報がすべて含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="1efef-159">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="1efef-160">HoloLens の中国語と日本語バージョンの問題は、同じように報告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1efef-160">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>
> [!NOTE]
> <span data-ttu-id="1efef-161">フィードバックハブがドキュメントフォルダーにアクセスするかどうかを確認するメッセージが表示されることを確認します (メッセージが表示されたら [ **はい]** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="1efef-161">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>
## <a name="note-for-developers"></a><span data-ttu-id="1efef-162">開発者向けのメモ</span><span class="sxs-lookup"><span data-stu-id="1efef-162">Note for developers</span></span>
<span data-ttu-id="1efef-163">HoloLens の Insider ビルドを使用してアプリケーションを開発することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1efef-163">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="1efef-164">ご利用を開始するには、 [HoloLens 開発者ドキュメント](https://developer.microsoft.com/windows/mixed-reality/development) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1efef-164">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="1efef-165">これらの命令は、HoloLens の Insider ビルドでも機能します。</span><span class="sxs-lookup"><span data-stu-id="1efef-165">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="1efef-166">既に HoloLens 開発に使用している Unity と Visual Studio の同じビルドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1efef-166">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>
## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="1efef-167">Insider ビルドの受信を停止します</span><span class="sxs-lookup"><span data-stu-id="1efef-167">Stop receiving Insider builds</span></span>
<span data-ttu-id="1efef-168">Windows Holographic の Insider ビルドを受信する必要がなくなった場合は、HoloLens が運用ビルドを実行しているときにオプトアウトできます。または、Advanced Recovery コンパニオンを使用してデバイスを [回復](hololens-recovery.md) し、デバイスを Insider バージョン以外の windows Holographic に回復することもできます。</span><span class="sxs-lookup"><span data-stu-id="1efef-168">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>
> [!CAUTION]
> <span data-ttu-id="1efef-169">新しいプレビュービルドを手動で再インストールした後に、Insider Preview ビルドから登録を解除したユーザーがブルースクリーンを使用するという既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="1efef-169">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="1efef-170">その後、デバイスを手動で回復する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1efef-170">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="1efef-171">影響を受けるかどうかに関する詳細については、この既知の [問題](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1efef-171">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>
<span data-ttu-id="1efef-172">HoloLens で運用ビルドが実行されていることを確認するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="1efef-172">To verify that your HoloLens is running a production build:</span></span>
1. <span data-ttu-id="1efef-173">[設定] にアクセスし、[ **バージョン情報] を > >**、ビルド番号を見つけます。</span><span class="sxs-lookup"><span data-stu-id="1efef-173">Go to **Settings > System > About**, and find the build number.</span></span>
1. <span data-ttu-id="1efef-174">[実稼働ビルド番号については、リリースノートを参照してください](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="1efef-174">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>
<span data-ttu-id="1efef-175">Insider ビルドをオプトアウトするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="1efef-175">To opt out of Insider builds:</span></span>
1. <span data-ttu-id="1efef-176">実稼働ビルドを実行する HoloLens で、[ **設定] [& セキュリティ > Windows Insider program に更新 >**、[ **Insider ビルドの停止**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1efef-176">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>
1. <span data-ttu-id="1efef-177">指示に従ってデバイスをオプトアウトします。</span><span class="sxs-lookup"><span data-stu-id="1efef-177">Follow the instructions to opt out your device.</span></span>
