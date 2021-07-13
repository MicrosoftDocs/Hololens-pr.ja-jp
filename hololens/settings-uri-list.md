---
title: ページ設定の可視性
description: PageVisibilityList および HoloLens Mixed Reality デバイスのガイドでサポートされている URI のリストを最新の状態に保ちます。
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, 割り当てられたアクセス, キオスク, 設定ページ
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d28994d911532a940d82756aa45609571ee80ac3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924334"
---
# <a name="page-settings-visibility"></a><span data-ttu-id="46bfd-104">ページ設定の可視性</span><span class="sxs-lookup"><span data-stu-id="46bfd-104">Page Settings Visibility</span></span>

<span data-ttu-id="46bfd-105">HoloLens デバイスの管理可能な機能の 1 つは、[設定/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) ポリシーを使用して、設定 アプリ内に表示されるページを制限することです。</span><span class="sxs-lookup"><span data-stu-id="46bfd-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="46bfd-106">PageVisibilityList は、IT 管理者がシステム設定アプリの特定のページを表示またはアクセスできないようにしたり、または指定されたページ以外のすべてのページで同様に行うことを許可するポリシーです。</span><span class="sxs-lookup"><span data-stu-id="46bfd-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="46bfd-107">この機能は、[Windows Holographic バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 以降の HoloLens 2 デバイスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="46bfd-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="46bfd-108">この機能を使用するデバイスが更新されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="46bfd-108">Please ensure devices you intend to use this for are updated.</span></span>

<span data-ttu-id="46bfd-109">次の例では、情報ページと Bluetooth ページにのみアクセスを許可するポリシーを示しています。これには、それぞれ URI "ms-settings:network-wifi" と "ms-settings:bluetooth" があります。</span><span class="sxs-lookup"><span data-stu-id="46bfd-109">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="46bfd-110">プロビジョニング パッケージを通して設定するには:</span><span class="sxs-lookup"><span data-stu-id="46bfd-110">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="46bfd-111">Windows 構成デザイナーでパッケージを作成しているときに、 **[ポリシー] > [設定] > [PageVisibilityList]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="46bfd-111">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="46bfd-112">次の文字列を入力します: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="46bfd-112">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="46bfd-113">プロビジョニング パッケージをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="46bfd-113">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="46bfd-114">デバイスにパッケージを適用します。</span><span class="sxs-lookup"><span data-stu-id="46bfd-114">Apply the package to your device.</span></span>
<span data-ttu-id="46bfd-115">プロビジョニング パッケージを作成して適用する方法の詳細については、[このページ](hololens-provisioning.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46bfd-115">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="46bfd-116">これは、OMA-URI を使用して Intune 経由で行います。</span><span class="sxs-lookup"><span data-stu-id="46bfd-116">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="46bfd-117">**カスタム ポリシー** を作成します。</span><span class="sxs-lookup"><span data-stu-id="46bfd-117">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="46bfd-118">OMA-URI を設定する場合は、次の文字列を使用します: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="46bfd-118">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="46bfd-119">選択したデータを選ぶときは、**文字列** を選択します</span><span class="sxs-lookup"><span data-stu-id="46bfd-119">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="46bfd-120">値を入力する場合は、次の値を使用します: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="46bfd-120">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="46bfd-121">カスタムデバイス構成は、デバイスが含まれる予定のグループに必ず割り当ててください。</span><span class="sxs-lookup"><span data-stu-id="46bfd-121">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="46bfd-122">Intune グループのデバイス構成の詳細については、[「HoloLens MDM 構成」](hololens-mdm-configure.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46bfd-122">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="46bfd-123">選択した方法に関係なく、デバイスは変更を受け取る必要があります。ユーザーには次の設定アプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="46bfd-123">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![設定アプリで変更されたアクティブ時間のスクリーンショット](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="46bfd-125">独自の選択したページを表示または非表示に設定アプリ ページを構成するには、HoloLens で使用可能な設定 URI を確認します。</span><span class="sxs-lookup"><span data-stu-id="46bfd-125">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="46bfd-126">設定に関する URI</span><span class="sxs-lookup"><span data-stu-id="46bfd-126">Settings URIs</span></span>

<span data-ttu-id="46bfd-127">HoloLens デバイスと Windows 10 デバイスでは、設定アプリ内に用意されているページが異なります。</span><span class="sxs-lookup"><span data-stu-id="46bfd-127">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="46bfd-128">このページには、HoloLens に存在する設定だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="46bfd-128">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="46bfd-129">アカウント</span><span class="sxs-lookup"><span data-stu-id="46bfd-129">Accounts</span></span>
| <span data-ttu-id="46bfd-130">[設定] ページ</span><span class="sxs-lookup"><span data-stu-id="46bfd-130">Settings page</span></span>           | <span data-ttu-id="46bfd-131">URI</span><span class="sxs-lookup"><span data-stu-id="46bfd-131">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="46bfd-132">職場または学校にアクセスする</span><span class="sxs-lookup"><span data-stu-id="46bfd-132">Access work or school</span></span> | `ms-settings:workplace`                         |
| <span data-ttu-id="46bfd-133">虹彩の登録</span><span class="sxs-lookup"><span data-stu-id="46bfd-133">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="46bfd-134">サインイン オプション</span><span class="sxs-lookup"><span data-stu-id="46bfd-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="46bfd-135">アプリ</span><span class="sxs-lookup"><span data-stu-id="46bfd-135">Apps</span></span>
| <span data-ttu-id="46bfd-136">[設定] ページ</span><span class="sxs-lookup"><span data-stu-id="46bfd-136">Settings page</span></span> | <span data-ttu-id="46bfd-137">URI</span><span class="sxs-lookup"><span data-stu-id="46bfd-137">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="46bfd-138">アプリと機能<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-138">Apps & features<sup>2</sup></span></span>     | `ms-settings:appsfeatures` <br> |
| <span data-ttu-id="46bfd-139">[アプリと機能] > [詳細なオプション] <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-139">Apps & features > Advanced Options <sup>2</sup></span></span>     | `ms-settings::appsfeatures-app` <br> |
| <span data-ttu-id="46bfd-140">[アプリと機能] > [オフライン マップ] <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-140">Apps & features > Offline Maps <sup>2</sup></span></span>     | `ms-settings:maps-maps` <br> |
| <span data-ttu-id="46bfd-141">[アプリと機能] > [オフライン マップ] > [マップをダウンロード] <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-141">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="46bfd-142">デバイス</span><span class="sxs-lookup"><span data-stu-id="46bfd-142">Devices</span></span>
| <span data-ttu-id="46bfd-143">[設定] ページ</span><span class="sxs-lookup"><span data-stu-id="46bfd-143">Settings page</span></span> | <span data-ttu-id="46bfd-144">URI</span><span class="sxs-lookup"><span data-stu-id="46bfd-144">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="46bfd-145">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="46bfd-145">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| <span data-ttu-id="46bfd-146">マウス <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-146">Mouse <sup>2</sup></span></span>      | `ms-settings:mouse` <br>  |
| <span data-ttu-id="46bfd-147">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-147">USB <sup>2</sup></span></span>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="46bfd-148">プライバシー</span><span class="sxs-lookup"><span data-stu-id="46bfd-148">Privacy</span></span>
| <span data-ttu-id="46bfd-149">[設定] ページ</span><span class="sxs-lookup"><span data-stu-id="46bfd-149">Settings page</span></span>            | <span data-ttu-id="46bfd-150">URI</span><span class="sxs-lookup"><span data-stu-id="46bfd-150">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="46bfd-151">アカウント情報</span><span class="sxs-lookup"><span data-stu-id="46bfd-151">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="46bfd-152">アプリの診断</span><span class="sxs-lookup"><span data-stu-id="46bfd-152">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="46bfd-153">バックグラウンド アプリ</span><span class="sxs-lookup"><span data-stu-id="46bfd-153">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="46bfd-154">予定表</span><span class="sxs-lookup"><span data-stu-id="46bfd-154">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="46bfd-155">通話履歴</span><span class="sxs-lookup"><span data-stu-id="46bfd-155">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="46bfd-156">カメラ</span><span class="sxs-lookup"><span data-stu-id="46bfd-156">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |
| <span data-ttu-id="46bfd-157">連絡先</span><span class="sxs-lookup"><span data-stu-id="46bfd-157">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="46bfd-158">診断とフィードバック</span><span class="sxs-lookup"><span data-stu-id="46bfd-158">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="46bfd-159">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="46bfd-159">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="46bfd-160">Email</span><span class="sxs-lookup"><span data-stu-id="46bfd-160">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="46bfd-161">ファイル システム</span><span class="sxs-lookup"><span data-stu-id="46bfd-161">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="46bfd-162">全般 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-162">General <sup>2</sup></span></span>             | `ms-settings:privacy-general`       |
| <span data-ttu-id="46bfd-163">インクと入力の個人用設定<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-163">Ink & typing personalization <sup>2</sup></span></span>             | `ms-settings:privacy-speechtyping`       |
| <span data-ttu-id="46bfd-164">場所</span><span class="sxs-lookup"><span data-stu-id="46bfd-164">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="46bfd-165">メッセージング</span><span class="sxs-lookup"><span data-stu-id="46bfd-165">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="46bfd-166">Microphone</span><span class="sxs-lookup"><span data-stu-id="46bfd-166">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="46bfd-167">モーション <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-167">Motion <sup>2</sup></span></span>               | `ms-settings:privacy-motion`                  |
| <span data-ttu-id="46bfd-168">通知</span><span class="sxs-lookup"><span data-stu-id="46bfd-168">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="46bfd-169">その他のデバイス</span><span class="sxs-lookup"><span data-stu-id="46bfd-169">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="46bfd-170">ピクチャ</span><span class="sxs-lookup"><span data-stu-id="46bfd-170">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="46bfd-171">無線</span><span class="sxs-lookup"><span data-stu-id="46bfd-171">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="46bfd-172">スクリーンショットの境界線 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-172">Screenshot borders <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="46bfd-173">スクリーンショットとアプリ <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-173">Screenshots and apps <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="46bfd-174">音声</span><span class="sxs-lookup"><span data-stu-id="46bfd-174">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="46bfd-175">タスク</span><span class="sxs-lookup"><span data-stu-id="46bfd-175">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="46bfd-176">ユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="46bfd-176">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="46bfd-177">ビデオ</span><span class="sxs-lookup"><span data-stu-id="46bfd-177">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="46bfd-178">音声のアクティブ化</span><span class="sxs-lookup"><span data-stu-id="46bfd-178">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="46bfd-179">ネットワークとインターネット</span><span class="sxs-lookup"><span data-stu-id="46bfd-179">Network & Internet</span></span>
| <span data-ttu-id="46bfd-180">[設定] ページ</span><span class="sxs-lookup"><span data-stu-id="46bfd-180">Settings page</span></span> | <span data-ttu-id="46bfd-181">URI</span><span class="sxs-lookup"><span data-stu-id="46bfd-181">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="46bfd-182">機内モード<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-182">Airplane Mode <sup>2</sup></span></span> | `ms-settings:network-airplanemode`        |
| <span data-ttu-id="46bfd-183">プロキシ</span><span class="sxs-lookup"><span data-stu-id="46bfd-183">Proxy</span></span> | `ms-settings:network-proxy`        |
| <span data-ttu-id="46bfd-184">VPN</span><span class="sxs-lookup"><span data-stu-id="46bfd-184">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="46bfd-185">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="46bfd-185">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="46bfd-186">システム</span><span class="sxs-lookup"><span data-stu-id="46bfd-186">System</span></span>
| <span data-ttu-id="46bfd-187">[設定] ページ</span><span class="sxs-lookup"><span data-stu-id="46bfd-187">Settings page</span></span>      | <span data-ttu-id="46bfd-188">URI</span><span class="sxs-lookup"><span data-stu-id="46bfd-188">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="46bfd-189">バッテリー<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-189">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver`<br>|
| <span data-ttu-id="46bfd-190">バッテリー<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-190">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver-settings`<br>|
| <span data-ttu-id="46bfd-191">色</span><span class="sxs-lookup"><span data-stu-id="46bfd-191">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="46bfd-192">ホログラム<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-192">Holograms <sup>2</sup></span></span>  |  `ms-settings:holograms`  |
| <span data-ttu-id="46bfd-193">調整<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-193">Calibration <sup>2</sup></span></span> |  `ms-settings:calibration` |
| <span data-ttu-id="46bfd-194">通知とアクション</span><span class="sxs-lookup"><span data-stu-id="46bfd-194">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="46bfd-195">共有エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="46bfd-195">Shared Experiences</span></span> | `ms-settings:crossdevice` 
| <span data-ttu-id="46bfd-196">サウンド<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-196">Sound <sup>2</sup></span></span>           | `ms-settings:sound`<br>|
| <span data-ttu-id="46bfd-197">[サウンド] > [アプリのボリュームとデバイスの優先順位] <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-197">Sound > App volume and device preference <sup>2</sup></span></span>           | `ms-settings:apps-volume`<br>|
| <span data-ttu-id="46bfd-198">[サウンド] > [サウンド デバイスを管理] <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-198">Sound > Manage sound devices <sup>2</sup></span></span>           | `ms-settings:sound-devices`<br>|
| <span data-ttu-id="46bfd-199">ストレージ</span><span class="sxs-lookup"><span data-stu-id="46bfd-199">Storage</span></span>            | `ms-settings:storagesense`           |
| <span data-ttu-id="46bfd-200">[サウンド] > [記憶域センスの構成] <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-200">Storage > Configure Storage Sense <sup>2</sup></span></span>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="46bfd-201">時刻と言語</span><span class="sxs-lookup"><span data-stu-id="46bfd-201">Time & Language</span></span>
| <span data-ttu-id="46bfd-202">[設定] ページ</span><span class="sxs-lookup"><span data-stu-id="46bfd-202">Settings page</span></span> | <span data-ttu-id="46bfd-203">URI</span><span class="sxs-lookup"><span data-stu-id="46bfd-203">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="46bfd-204">日付と時刻 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-204">Date & time <sup>2</sup></span></span> | `ms-settings:dateandtime`                  |
| <span data-ttu-id="46bfd-205">キーボード <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-205">Keyboard <sup>2</sup></span></span> | `ms-settings:keyboard`                  |
| <span data-ttu-id="46bfd-206">言語 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-206">Language <sup>2</sup></span></span> | `ms-settings:language`                  |
| <span data-ttu-id="46bfd-207">言語 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-207">Language <sup>2</sup></span></span> | `ms-settings:regionlanguage-languageoptions`                  |
| <span data-ttu-id="46bfd-208">Language</span><span class="sxs-lookup"><span data-stu-id="46bfd-208">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="46bfd-209">リージョン</span><span class="sxs-lookup"><span data-stu-id="46bfd-209">Region</span></span>        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="46bfd-210">アップデートとセキュリティ</span><span class="sxs-lookup"><span data-stu-id="46bfd-210">Update & Security</span></span>
| <span data-ttu-id="46bfd-211">[設定] ページ</span><span class="sxs-lookup"><span data-stu-id="46bfd-211">Settings page</span></span>                         | <span data-ttu-id="46bfd-212">URI</span><span class="sxs-lookup"><span data-stu-id="46bfd-212">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="46bfd-213">詳細オプション</span><span class="sxs-lookup"><span data-stu-id="46bfd-213">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |
| <span data-ttu-id="46bfd-214">リセットと回復 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="46bfd-214">Reset & Recovery <sup>2</sup></span></span>      | `ms-settings:reset`         |
| <span data-ttu-id="46bfd-215">Windows Insider Program</span><span class="sxs-lookup"><span data-stu-id="46bfd-215">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="46bfd-216">Windows Update</span><span class="sxs-lookup"><span data-stu-id="46bfd-216">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><span data-ttu-id="46bfd-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="46bfd-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span></span><br><span data-ttu-id="46bfd-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="46bfd-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="46bfd-219">Windows Update - 更新プログラムの確認</span><span class="sxs-lookup"><span data-stu-id="46bfd-219">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |


- <span data-ttu-id="46bfd-220"><sup>1</sup> - Windows Holographic バージョン 21H1 以前のバージョンの場合、次の 2 つの URI では、実際には **[詳細オプション]** ページまたは **[オプション]** ページに移動する必要があります。メインの Windows Update ページをブロックまたは表示するのみです。</span><span class="sxs-lookup"><span data-stu-id="46bfd-220"><sup>1</sup> - For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
  -  <span data-ttu-id="46bfd-221">ms-settings:windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="46bfd-221">ms-settings:windowsupdate-options</span></span>
  -  <span data-ttu-id="46bfd-222">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="46bfd-222">ms-settings:windowsupdate-restartoptions</span></span>

- <span data-ttu-id="46bfd-223"><sup>2</sup> - Holographic 21H1 Windows 21H1 以上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="46bfd-223"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="46bfd-224">Windows 10 設定 URI の完全なリストについては、[起動設定](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)のドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="46bfd-224">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
