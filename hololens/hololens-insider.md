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
ms.openlocfilehash: 8b8c3c26ff743a4df0010110d0fe6e2930646c86
ms.sourcegitcommit: add53aa73588986a3430cdc0310af7665a038cfc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2021
ms.locfileid: "112977238"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="43fbf-103">Microsoft HoloLens の Insider Preview</span><span class="sxs-lookup"><span data-stu-id="43fbf-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="43fbf-104">HoloLens の最新の Insider Preview ビルドへようこそ。</span><span class="sxs-lookup"><span data-stu-id="43fbf-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="43fbf-105">HoloLens [の次](hololens-insider.md#start-receiving-insider-builds) の主要なオペレーティング システム更新プログラムの開始と貴重なフィードバックの提供は簡単です。</span><span class="sxs-lookup"><span data-stu-id="43fbf-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="43fbf-106">Windows Insider リリース ノート</span><span class="sxs-lookup"><span data-stu-id="43fbf-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="43fbf-107">Windows Insider に新しい機能を再び提供し始め、楽しみに思います。</span><span class="sxs-lookup"><span data-stu-id="43fbf-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="43fbf-108">新しいビルドは、最新の更新プログラムのために Dev および Beta チャネルにフライトします。</span><span class="sxs-lookup"><span data-stu-id="43fbf-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="43fbf-109">このページは引き続き更新されます。このページでは、新しいビルドの機能と更新プログラムWindows Insiderします。</span><span class="sxs-lookup"><span data-stu-id="43fbf-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="43fbf-110">これらの更新プログラムを実際に組み合わせ、準備を整えます。</span><span class="sxs-lookup"><span data-stu-id="43fbf-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="43fbf-111">機能</span><span class="sxs-lookup"><span data-stu-id="43fbf-111">Feature</span></span>                 | <span data-ttu-id="43fbf-112">説明</span><span class="sxs-lookup"><span data-stu-id="43fbf-112">Description</span></span>                | <span data-ttu-id="43fbf-113">対象ユーザー</span><span class="sxs-lookup"><span data-stu-id="43fbf-113">Target Users</span></span> | <span data-ttu-id="43fbf-114">導入されたビルド</span><span class="sxs-lookup"><span data-stu-id="43fbf-114">Build introduced</span></span> |
|-------------------------|----------------------------|--------------|------------------|
| <span data-ttu-id="43fbf-115">HoloLens での CSP の変更</span><span class="sxs-lookup"><span data-stu-id="43fbf-115">CSP Changes on HoloLens</span></span> | <span data-ttu-id="43fbf-116">データに対してクエリを実行するの新しい CSP</span><span class="sxs-lookup"><span data-stu-id="43fbf-116">New CSPs for to query data</span></span> | <span data-ttu-id="43fbf-117">IT 管理者</span><span class="sxs-lookup"><span data-stu-id="43fbf-117">IT Admins</span></span>    | <span data-ttu-id="43fbf-118">20348.1403</span><span class="sxs-lookup"><span data-stu-id="43fbf-118">20348.1403</span></span>                 |

### <a name="csp-changes-on-hololens"></a><span data-ttu-id="43fbf-119">HoloLens での CSP の変更</span><span class="sxs-lookup"><span data-stu-id="43fbf-119">CSP changes on HoloLens</span></span>

- <span data-ttu-id="43fbf-120">このビルドでWindows Insider、20348.1403</span><span class="sxs-lookup"><span data-stu-id="43fbf-120">Introduced in Windows Insider build, 20348.1403</span></span>

#### <a name="devdetail-csp"></a><span data-ttu-id="43fbf-121">DevDetail CSP</span><span class="sxs-lookup"><span data-stu-id="43fbf-121">DevDetail CSP</span></span>

<span data-ttu-id="43fbf-122">DevDetail CSP では、HoloLens デバイス上の空き記憶域スペースも報告されます。</span><span class="sxs-lookup"><span data-stu-id="43fbf-122">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="43fbf-123">これは、設定アプリの [ストレージ] ページに表示される値とほぼ一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43fbf-123">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="43fbf-124">この情報を含む特定のノードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="43fbf-124">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="43fbf-125">./DevDetail/Ext/Microsoft/FreeStorage (GET 操作のみ)</span><span class="sxs-lookup"><span data-stu-id="43fbf-125">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp"></a><span data-ttu-id="43fbf-126">DeviceStatus CSP</span><span class="sxs-lookup"><span data-stu-id="43fbf-126">DeviceStatus CSP</span></span>

<span data-ttu-id="43fbf-127">DeviceStatus CSP では、HoloLens がアクティブに接続されている Wifi ネットワークの SSID と BSSID も報告されます。</span><span class="sxs-lookup"><span data-stu-id="43fbf-127">DeviceStatus CSP now also reports SSID and BSSID of Wifi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="43fbf-128">この情報を含む特定のノードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="43fbf-128">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="43fbf-129">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/ mac アドレス *(Wi-Fi*/SSID)</span><span class="sxs-lookup"><span data-stu-id="43fbf-129">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="43fbf-130">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac* Wi-Fi /BSSID</span><span class="sxs-lookup"><span data-stu-id="43fbf-130">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="43fbf-131">NetworkIdentifiers のクエリを実行する syncml BLOB の例 (MDM ベンダー向け)</span><span class="sxs-lookup"><span data-stu-id="43fbf-131">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

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

### <a name="fixes-and-improvements"></a><span data-ttu-id="43fbf-132">修正と機能強化:</span><span class="sxs-lookup"><span data-stu-id="43fbf-132">Fixes and improvements:</span></span>

- <span data-ttu-id="43fbf-133">ロックされた [ファイルをダウンロードするプロンプトデバイス ポータルが表示される場合の既知の問題を修正しました。](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="43fbf-133">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="43fbf-134">ファイルの [アップロードとダウンロードのデバイス ポータルに関する既知の問題を修正しました。](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="43fbf-134">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>

## <a name="start-receiving-insider-builds"></a><span data-ttu-id="43fbf-135">Insider ビルドの受信を開始する</span><span class="sxs-lookup"><span data-stu-id="43fbf-135">Start receiving Insider builds</span></span>
> [!NOTE]
> <span data-ttu-id="43fbf-136">最近更新していない場合は、デバイスを再起動して状態を更新し、最新のビルドを取得してください。</span><span class="sxs-lookup"><span data-stu-id="43fbf-136">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="43fbf-137">"デバイスの再起動" 音声コマンドは正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="43fbf-137">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="43fbf-138">[設定]/[再起動] で再起動ボタンを選択Windows Insider Program。</span><span class="sxs-lookup"><span data-stu-id="43fbf-138">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="43fbf-139">発生した可能性があるバック エンドにバグがありました。これにより、追跡が戻されます。</span><span class="sxs-lookup"><span data-stu-id="43fbf-139">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="43fbf-140">デバイス上HoloLens 2 [設定の **更新]** に移動し&セキュリティ  >  **Windows Insider Program]** を選択  >  **概要。**</span><span class="sxs-lookup"><span data-stu-id="43fbf-140">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="43fbf-141">アカウントとして登録するために使用したアカウントをリンクWindows Insider。</span><span class="sxs-lookup"><span data-stu-id="43fbf-141">Link the account you used to register as a Windows Insider.</span></span>
<span data-ttu-id="43fbf-142">Windows Insider は現在、チャネルに移行しています。</span><span class="sxs-lookup"><span data-stu-id="43fbf-142">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="43fbf-143">高速 **リング** は開発チャネルになり、低速リングはベータ チャネル になり、リリース プレビュー リングはリリースプレビュー チャネル **になります**。</span><span class="sxs-lookup"><span data-stu-id="43fbf-143">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="43fbf-144">マッピングは次のように表示されます。Windows Insider チャネルの説明 については、「Windows ブログでの Windows Insider チャネルの紹介」 ![ ](images/WindowsInsiderChannels.png) を参照してください。 [](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)</span><span class="sxs-lookup"><span data-stu-id="43fbf-144">Here is what that mapping looks like: ![Windows Insider Channels explanation](images/WindowsInsiderChannels.png) For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="43fbf-145">次に、 **[Windows のアクティブ** な開発] を選択し、開発チャネルを受け取るのとビルドをベータ チャネル、プログラムの用語を確認します。</span><span class="sxs-lookup"><span data-stu-id="43fbf-145">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="43fbf-146">[Confirm **> Restart Now]を選択して** 完了します。</span><span class="sxs-lookup"><span data-stu-id="43fbf-146">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="43fbf-147">デバイスが再起動したら、[設定] > [更新&セキュリティ] > **更新** プログラムを確認して最新のビルドを取得します。</span><span class="sxs-lookup"><span data-stu-id="43fbf-147">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>
### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="43fbf-148">更新エラー 0x80070490回避</span><span class="sxs-lookup"><span data-stu-id="43fbf-148">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="43fbf-149">Dev または Beta チャネルで更新0x80070490更新エラーが発生した場合は、次の短期的な回避を試してください。</span><span class="sxs-lookup"><span data-stu-id="43fbf-149">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="43fbf-150">インサイダー チャネルを移動し、更新プログラムを選択してから、Insider チャネルを戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="43fbf-150">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>
#### <a name="stage-one---release-preview"></a><span data-ttu-id="43fbf-151">ステージ 1 - リリース プレビュー</span><span class="sxs-lookup"><span data-stu-id="43fbf-151">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="43fbf-152">[設定] 、 [セキュリティ&更新] 、 [Windows Insider Program、 [リリース プレビュー チャネル **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="43fbf-152">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="43fbf-153">設定、更新プログラム&セキュリティ、Windows Update、 **更新プログラムの確認**。</span><span class="sxs-lookup"><span data-stu-id="43fbf-153">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="43fbf-154">更新後、ステージ 2 に進む。</span><span class="sxs-lookup"><span data-stu-id="43fbf-154">After the update, continue on to Stage two.</span></span>
#### <a name="stage-two---dev-channel"></a><span data-ttu-id="43fbf-155">ステージ 2 - 開発チャネル</span><span class="sxs-lookup"><span data-stu-id="43fbf-155">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="43fbf-156">[設定] 、 [セキュリティ&更新Windows Insider Program、 [開発チャネル] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="43fbf-156">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="43fbf-157">設定、更新プログラム&セキュリティ、Windows Update、 **更新プログラムの確認**。</span><span class="sxs-lookup"><span data-stu-id="43fbf-157">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>
## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="43fbf-158">FFU のダウンロードとフラッシュの方向</span><span class="sxs-lookup"><span data-stu-id="43fbf-158">FFU download and flash directions</span></span>
<span data-ttu-id="43fbf-159">フライト署名済み ffu でテストするには、フライト署名済み ffu をフラッシュする前に、まずデバイスのロックを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43fbf-159">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="43fbf-160">PC の場合:</span><span class="sxs-lookup"><span data-stu-id="43fbf-160">On PC:</span></span>
    1. <span data-ttu-id="43fbf-161">から ffu を PC にダウンロードします [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。</span><span class="sxs-lookup"><span data-stu-id="43fbf-161">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="43fbf-162">次のコマンドから ARC (Advanced Recovery Companion) をMicrosoft Storeします [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 。</span><span class="sxs-lookup"><span data-stu-id="43fbf-162">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="43fbf-163">HoloLens - Flight Unlock: Open **Settings**  >  **Update & Security Windows Insider Program** サインアップ  >  し、デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="43fbf-163">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>
1. <span data-ttu-id="43fbf-164">Flash FFU - ARC を使用してフライト署名済み FFU をフラッシュできます。</span><span class="sxs-lookup"><span data-stu-id="43fbf-164">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>
### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="43fbf-165">フィードバックを提供し、問題を報告する</span><span class="sxs-lookup"><span data-stu-id="43fbf-165">Provide feedback and report issues</span></span>
<span data-ttu-id="43fbf-166">HoloLens [フィードバック Hub](hololens-feedback.md) アプリを使用して、フィードバックを提供し、問題を報告してください。</span><span class="sxs-lookup"><span data-stu-id="43fbf-166">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="43fbf-167">このフィードバック Hubを使用すると、エンジニアが問題をすばやくデバッグして解決するのに役立つ、必要なすべての診断情報が確実に含まれます。</span><span class="sxs-lookup"><span data-stu-id="43fbf-167">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="43fbf-168">HoloLens の中国語と日本語のバージョンに関する問題は、同じ方法で報告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43fbf-168">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>
> [!NOTE]
> <span data-ttu-id="43fbf-169">[ドキュメント] フォルダーにアクセスするかどうかを確認するプロンプトフィードバック Hub受け入れる必要があります (メッセージが表示されたら、[は **い]** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="43fbf-169">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>
## <a name="note-for-developers"></a><span data-ttu-id="43fbf-170">開発者向けの注意</span><span class="sxs-lookup"><span data-stu-id="43fbf-170">Note for developers</span></span>
<span data-ttu-id="43fbf-171">HoloLens の Insider ビルドを使用してアプリケーションを開発してみてください。</span><span class="sxs-lookup"><span data-stu-id="43fbf-171">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="43fbf-172">使用を開始 [するには、HoloLens 開発者向けドキュメント](https://developer.microsoft.com/windows/mixed-reality/development) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43fbf-172">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="43fbf-173">これらの同じ手順は、HoloLens の Insider ビルドで動作します。</span><span class="sxs-lookup"><span data-stu-id="43fbf-173">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="43fbf-174">HoloLens 開発に既に使用Visual Studio Unity と同じビルドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="43fbf-174">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>
## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="43fbf-175">Insider ビルドの受信を停止する</span><span class="sxs-lookup"><span data-stu-id="43fbf-175">Stop receiving Insider builds</span></span>
<span data-ttu-id="43fbf-176">Windows Holographic の Insider ビルドを受け取りたくない場合は、HoloLens が実稼働ビルドを実行している場合はオプトアウト[](hololens-recovery.md)できます。または、Advanced Recovery Companion を使用してデバイスを回復して、Insider 以外のバージョンの Windows Holographic にデバイスを回復することもできます。</span><span class="sxs-lookup"><span data-stu-id="43fbf-176">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>
> [!CAUTION]
> <span data-ttu-id="43fbf-177">新しいプレビュー ビルドを手動で再インストールした後に Insider Preview から登録を解除したユーザーがブルー スクリーンを表示する既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="43fbf-177">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="43fbf-178">その後、デバイスを手動で回復する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43fbf-178">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="43fbf-179">影響を受け取る可能性がある場合の詳細については、この既知の問題に関するページを [参照してください](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)。</span><span class="sxs-lookup"><span data-stu-id="43fbf-179">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>
<span data-ttu-id="43fbf-180">HoloLens で実稼働ビルドが実行されていないことを確認するには:</span><span class="sxs-lookup"><span data-stu-id="43fbf-180">To verify that your HoloLens is running a production build:</span></span>
1. <span data-ttu-id="43fbf-181">[システムの **設定] > [>について**] に移動し、ビルド番号を見つける。</span><span class="sxs-lookup"><span data-stu-id="43fbf-181">Go to **Settings > System > About**, and find the build number.</span></span>
1. <span data-ttu-id="43fbf-182">[実稼働ビルド番号については、リリース ノートを参照してください](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="43fbf-182">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>
<span data-ttu-id="43fbf-183">Insider ビルドをオプトアウトするには:</span><span class="sxs-lookup"><span data-stu-id="43fbf-183">To opt out of Insider builds:</span></span>
1. <span data-ttu-id="43fbf-184">実稼働ビルドを実行している HoloLens で、[設定] > **[Update & Security**> Windows Insider Program] に移動し、[Stop Insider builds]/(Insider ビルドの停止)を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="43fbf-184">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>
1. <span data-ttu-id="43fbf-185">指示に従ってデバイスをオプトアウトします。</span><span class="sxs-lookup"><span data-stu-id="43fbf-185">Follow the instructions to opt out your device.</span></span>
