---
title: ページ設定の可視性
description: PageVisibilityList および HoloLens Mixed Reality デバイスのガイドでサポートされている URI のリストを最新の状態に保ちます。
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens、hololens 2、割り当てられたアクセス、キオスク、設定ページ
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f004f39f4b69748e8c36ad93111f4423d14c40f3
ms.sourcegitcommit: 23ee06b659d7a51f3000d386c8f67cbf212d5aa4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327391"
---
# <span data-ttu-id="ed993-104">ページ設定の可視性</span><span class="sxs-lookup"><span data-stu-id="ed993-104">Page Settings Visibility</span></span>

<span data-ttu-id="ed993-105">HoloLens デバイスの管理可能な機能の 1 つに、[Settings/PageVisibilityList ポリシー](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)を使用した設定アプリ内で閲覧されるページの制限があります。</span><span class="sxs-lookup"><span data-stu-id="ed993-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="ed993-106">PageVisibilityList は、IT 管理者がシステム設定アプリの特定のページを表示またはアクセスできないようにしたり、または指定されたページ以外のすべてのページで同様に行うことを許可するポリシーです。</span><span class="sxs-lookup"><span data-stu-id="ed993-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="ed993-107">この機能は、HoloLens 2 デバイスの [Windows Holographic バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2) でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ed993-107">This feature is only avalible in [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) for HoloLens 2 devices.</span></span> <span data-ttu-id="ed993-108">この機能を使用するデバイスが更新されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ed993-108">Please ensure devices you intend to use this for are updated.</span></span>

> [!NOTE]
> <span data-ttu-id="ed993-109">20 以上の新しい SettingsURIs が間もなく追加されます。</span><span class="sxs-lookup"><span data-stu-id="ed993-109">20+ new SettingsURIs are being added soon.</span></span> <span data-ttu-id="ed993-110">[HoloLens Insider](hololens-insider.md) ビルドでこの設定をプレビューすることに興味がある場合は、「[Windows Inside ページ -ページ設定の可視性の新しい SettingsURI](hololens-insider.md#new-settingsuris-for-page-settings-visibility)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed993-110">Please view [the Windows Insider page - New SettingsURIs for Page Settings Visibility](hololens-insider.md#new-settingsuris-for-page-settings-visibility) if you are interesting in previewing this setting on a [HoloLens Insider](hololens-insider.md) build.</span></span>

<span data-ttu-id="ed993-111">次の例では、情報ページと Bluetooth ページにのみアクセスを許可するポリシーを示しています。これには、それぞれ URI "ms-settings:network-wifi" と "ms-settings:bluetooth" があります。</span><span class="sxs-lookup"><span data-stu-id="ed993-111">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="ed993-112">プロビジョニング パッケージを通して設定するには:</span><span class="sxs-lookup"><span data-stu-id="ed993-112">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="ed993-113">Windows 構成デザイナーでパッケージを作成しているときに、**[ポリシー] > [設定] > [PageVisibilityList]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="ed993-113">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="ed993-114">次の文字列を入力します: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="ed993-114">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="ed993-115">プロビジョニング パッケージをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ed993-115">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="ed993-116">デバイスにパッケージを適用します。</span><span class="sxs-lookup"><span data-stu-id="ed993-116">Apply the package to your device.</span></span>
<span data-ttu-id="ed993-117">プロビジョニング パッケージを作成して適用する方法の詳細については、[こちらのページ](hololens-provisioning.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed993-117">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="ed993-118">これは、OMA-URI を使用して Intune 経由で行います。</span><span class="sxs-lookup"><span data-stu-id="ed993-118">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="ed993-119">**カスタム ポリシー**を作成する。</span><span class="sxs-lookup"><span data-stu-id="ed993-119">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="ed993-120">OMA-URI を設定する場合は、次の文字列を使用します: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="ed993-120">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="ed993-121">選択したデータを選ぶときは、**文字列**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ed993-121">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="ed993-122">値を入力する場合は、次の値を使用します: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="ed993-122">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="ed993-123">カスタムデバイス構成は、デバイスが含まれる予定のグループに必ず割り当ててください。</span><span class="sxs-lookup"><span data-stu-id="ed993-123">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="ed993-124">Intune グループとデバイス構成の詳細については、「[HoloLens MDM 構成](hololens-mdm-configure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed993-124">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="ed993-125">選択した方法に関係なく、デバイスは変更を受け取る必要があります。ユーザーには次の設定アプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed993-125">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![設定アプリで変更されたアクティブ時間のスクリーンショット](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="ed993-127">独自の選択したページを表示または非表示に設定アプリ ページを構成するには、HoloLens で使用可能な設定 URI を確認します。</span><span class="sxs-lookup"><span data-stu-id="ed993-127">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <span data-ttu-id="ed993-128">設定に関する URI</span><span class="sxs-lookup"><span data-stu-id="ed993-128">Settings URIs</span></span>

<span data-ttu-id="ed993-129">HoloLens デバイスと Windows 10 デバイスでは、設定アプリ内に用意されているページが異なります。</span><span class="sxs-lookup"><span data-stu-id="ed993-129">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="ed993-130">このページには、HoloLens に存在する設定だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed993-130">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <span data-ttu-id="ed993-131">アカウント</span><span class="sxs-lookup"><span data-stu-id="ed993-131">Accounts</span></span>
| <span data-ttu-id="ed993-132">設定ページ</span><span class="sxs-lookup"><span data-stu-id="ed993-132">Settings page</span></span>           | <span data-ttu-id="ed993-133">URI</span><span class="sxs-lookup"><span data-stu-id="ed993-133">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="ed993-134">サインイン オプション</span><span class="sxs-lookup"><span data-stu-id="ed993-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |
| <span data-ttu-id="ed993-135">虹彩の登録</span><span class="sxs-lookup"><span data-stu-id="ed993-135">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="ed993-136">職場または学校にアクセスする</span><span class="sxs-lookup"><span data-stu-id="ed993-136">Access work or school</span></span> | `ms-settings:workplace`                         |

### <span data-ttu-id="ed993-137">デバイス</span><span class="sxs-lookup"><span data-stu-id="ed993-137">Devices</span></span>
| <span data-ttu-id="ed993-138">設定ページ</span><span class="sxs-lookup"><span data-stu-id="ed993-138">Settings page</span></span> | <span data-ttu-id="ed993-139">URI</span><span class="sxs-lookup"><span data-stu-id="ed993-139">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="ed993-140">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="ed993-140">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |

### <span data-ttu-id="ed993-141">プライバシー</span><span class="sxs-lookup"><span data-stu-id="ed993-141">Privacy</span></span>
| <span data-ttu-id="ed993-142">設定ページ</span><span class="sxs-lookup"><span data-stu-id="ed993-142">Settings page</span></span>            | <span data-ttu-id="ed993-143">URI</span><span class="sxs-lookup"><span data-stu-id="ed993-143">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="ed993-144">アカウント情報</span><span class="sxs-lookup"><span data-stu-id="ed993-144">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="ed993-145">アプリの診断</span><span class="sxs-lookup"><span data-stu-id="ed993-145">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="ed993-146">バックグラウンド アプリ</span><span class="sxs-lookup"><span data-stu-id="ed993-146">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="ed993-147">ユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="ed993-147">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="ed993-148">ファイル システム</span><span class="sxs-lookup"><span data-stu-id="ed993-148">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="ed993-149">カレンダー</span><span class="sxs-lookup"><span data-stu-id="ed993-149">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="ed993-150">通話履歴</span><span class="sxs-lookup"><span data-stu-id="ed993-150">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="ed993-151">連絡先</span><span class="sxs-lookup"><span data-stu-id="ed993-151">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="ed993-152">その他のデバイス</span><span class="sxs-lookup"><span data-stu-id="ed993-152">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="ed993-153">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="ed993-153">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="ed993-154">メール</span><span class="sxs-lookup"><span data-stu-id="ed993-154">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="ed993-155">診断とフィードバック</span><span class="sxs-lookup"><span data-stu-id="ed993-155">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="ed993-156">場所</span><span class="sxs-lookup"><span data-stu-id="ed993-156">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="ed993-157">メッセージング</span><span class="sxs-lookup"><span data-stu-id="ed993-157">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="ed993-158">マイク</span><span class="sxs-lookup"><span data-stu-id="ed993-158">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="ed993-159">通知</span><span class="sxs-lookup"><span data-stu-id="ed993-159">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="ed993-160">画像</span><span class="sxs-lookup"><span data-stu-id="ed993-160">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="ed993-161">無線</span><span class="sxs-lookup"><span data-stu-id="ed993-161">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="ed993-162">音声認識</span><span class="sxs-lookup"><span data-stu-id="ed993-162">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="ed993-163">タスク</span><span class="sxs-lookup"><span data-stu-id="ed993-163">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="ed993-164">ビデオ</span><span class="sxs-lookup"><span data-stu-id="ed993-164">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="ed993-165">音声によるアクティブ化</span><span class="sxs-lookup"><span data-stu-id="ed993-165">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |
| <span data-ttu-id="ed993-166">カメラ</span><span class="sxs-lookup"><span data-stu-id="ed993-166">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |

### <span data-ttu-id="ed993-167">ネットワークとインターネット</span><span class="sxs-lookup"><span data-stu-id="ed993-167">Network & Internet</span></span>
| <span data-ttu-id="ed993-168">設定ページ</span><span class="sxs-lookup"><span data-stu-id="ed993-168">Settings page</span></span> | <span data-ttu-id="ed993-169">URI</span><span class="sxs-lookup"><span data-stu-id="ed993-169">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="ed993-170">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="ed993-170">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |
| <span data-ttu-id="ed993-171">VPN</span><span class="sxs-lookup"><span data-stu-id="ed993-171">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="ed993-172">プロキシ</span><span class="sxs-lookup"><span data-stu-id="ed993-172">Proxy</span></span> | `ms-settings:network-proxy`        |

### <span data-ttu-id="ed993-173">System</span><span class="sxs-lookup"><span data-stu-id="ed993-173">System</span></span>
| <span data-ttu-id="ed993-174">設定ページ</span><span class="sxs-lookup"><span data-stu-id="ed993-174">Settings page</span></span>      | <span data-ttu-id="ed993-175">URI</span><span class="sxs-lookup"><span data-stu-id="ed993-175">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="ed993-176">共有エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="ed993-176">Shared Experiences</span></span> | `ms-settings:crossdevice`            |
| <span data-ttu-id="ed993-177">色</span><span class="sxs-lookup"><span data-stu-id="ed993-177">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="ed993-178">通知とアクション</span><span class="sxs-lookup"><span data-stu-id="ed993-178">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="ed993-179">ストレージ</span><span class="sxs-lookup"><span data-stu-id="ed993-179">Storage</span></span>            | `ms-settings:storagesense`           |

### <span data-ttu-id="ed993-180">時刻と言語</span><span class="sxs-lookup"><span data-stu-id="ed993-180">Time & Language</span></span>
| <span data-ttu-id="ed993-181">設定ページ</span><span class="sxs-lookup"><span data-stu-id="ed993-181">Settings page</span></span> | <span data-ttu-id="ed993-182">URI</span><span class="sxs-lookup"><span data-stu-id="ed993-182">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="ed993-183">地域</span><span class="sxs-lookup"><span data-stu-id="ed993-183">Region</span></span>        | `ms-settings:regionformatting`                  |
| <span data-ttu-id="ed993-184">言語</span><span class="sxs-lookup"><span data-stu-id="ed993-184">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |

### <span data-ttu-id="ed993-185">更新とセキュリティ</span><span class="sxs-lookup"><span data-stu-id="ed993-185">Update & Security</span></span>
| <span data-ttu-id="ed993-186">設定ページ</span><span class="sxs-lookup"><span data-stu-id="ed993-186">Settings page</span></span>                         | <span data-ttu-id="ed993-187">URI</span><span class="sxs-lookup"><span data-stu-id="ed993-187">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="ed993-188">Windows Insider Program</span><span class="sxs-lookup"><span data-stu-id="ed993-188">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="ed993-189">Windows Update</span><span class="sxs-lookup"><span data-stu-id="ed993-189">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup><span data-ttu-id="ed993-190">1</span><span class="sxs-lookup"><span data-stu-id="ed993-190">1</span></span></sup>`ms-settings:windowsupdate-options`<br><sup><span data-ttu-id="ed993-191">1</span><span class="sxs-lookup"><span data-stu-id="ed993-191">1</span></span></sup>`ms-settings:windowsupdate-restartoptions` |
| <span data-ttu-id="ed993-192">Windows Update - 更新プログラムの確認</span><span class="sxs-lookup"><span data-stu-id="ed993-192">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |
| <span data-ttu-id="ed993-193">詳細オプション</span><span class="sxs-lookup"><span data-stu-id="ed993-193">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |

>  <sup><span data-ttu-id="ed993-194">1</sup> 次の 2 つの URI は、実際には **[詳細オプション]** や **[オプション]** ページへの移動を行いません。Windows Update のメイン ページをブロックしたり、表示したりするだけです。</span><span class="sxs-lookup"><span data-stu-id="ed993-194">1</sup> The following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
> - <span data-ttu-id="ed993-195">ms-settings:windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="ed993-195">ms-settings:windowsupdate-options</span></span>
> - <span data-ttu-id="ed993-196">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="ed993-196">ms-settings:windowsupdate-restartoptions</span></span> 

<span data-ttu-id="ed993-197">Windows 10 設定 URI の完全なリストについては、[起動設定](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)のドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ed993-197">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
