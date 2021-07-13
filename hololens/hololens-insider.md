---
title: Microsoft HoloLens の Insider Preview
description: Insider ビルドの使用を開始する方法について説明します。また、次の主要なオペレーティングシステムの更新プログラムに関して、HoloLens の貴重なフィードバックを提供します。
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
ms.openlocfilehash: 87b606e634d4035da02802ddd1a8e1a980f1f1d6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636095"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="d8725-103">Microsoft HoloLens の Insider Preview</span><span class="sxs-lookup"><span data-stu-id="d8725-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="d8725-104">HoloLens のための最新の Insider Preview ビルドへようこそ。</span><span class="sxs-lookup"><span data-stu-id="d8725-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="d8725-105">この機能は簡単に[開始](hololens-insider.md#start-receiving-insider-builds)でき、次の主要なオペレーティングシステムの更新プログラムについての重要なフィードバックを提供します HoloLens。</span><span class="sxs-lookup"><span data-stu-id="d8725-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="d8725-106">WindowsInsider のリリースノート</span><span class="sxs-lookup"><span data-stu-id="d8725-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="d8725-107">ここでは、新しい機能を開始して、insider を Windows します。</span><span class="sxs-lookup"><span data-stu-id="d8725-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="d8725-108">新しいビルドは、最新の更新プログラムの開発およびベータチャネルに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="d8725-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="d8725-109">Windows Insider ビルドに機能と更新プログラムを追加すると、このページは引き続き更新されます。</span><span class="sxs-lookup"><span data-stu-id="d8725-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="d8725-110">これらの更新プログラムを実際のものに混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="d8725-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="d8725-111">機能</span><span class="sxs-lookup"><span data-stu-id="d8725-111">Feature</span></span>                 | <span data-ttu-id="d8725-112">説明</span><span class="sxs-lookup"><span data-stu-id="d8725-112">Description</span></span>                | <span data-ttu-id="d8725-113">ユーザーまたはシナリオ</span><span class="sxs-lookup"><span data-stu-id="d8725-113">User or Scenario</span></span> | <span data-ttu-id="d8725-114">導入されたビルド</span><span class="sxs-lookup"><span data-stu-id="d8725-114">Build introduced</span></span> |
|-------------------------|----------------------------|--------------|------------------|
| [<span data-ttu-id="d8725-115">レポート HoloLens の詳細の CSP の変更</span><span class="sxs-lookup"><span data-stu-id="d8725-115">CSP changes for reporting HoloLens details</span></span>](#csp-changes-for-reporting-hololens-details) | <span data-ttu-id="d8725-116">データを照会するための新しい Csp</span><span class="sxs-lookup"><span data-stu-id="d8725-116">New CSPs for to query data</span></span> | <span data-ttu-id="d8725-117">IT 管理者</span><span class="sxs-lookup"><span data-stu-id="d8725-117">IT Admins</span></span>    | <span data-ttu-id="d8725-118">20348.1403</span><span class="sxs-lookup"><span data-stu-id="d8725-118">20348.1403</span></span>                 |
| [<span data-ttu-id="d8725-119">CSP によって制御される自動ログインポリシー</span><span class="sxs-lookup"><span data-stu-id="d8725-119">Auto login policy controlled by CSP</span></span>](#auto-login-policy-controlled-by-csp) | <span data-ttu-id="d8725-120">アカウントを自動的にログインするために使用されます</span><span class="sxs-lookup"><span data-stu-id="d8725-120">Used to log in an account automatically</span></span> | <span data-ttu-id="d8725-121">IT 管理者</span><span class="sxs-lookup"><span data-stu-id="d8725-121">IT Admins</span></span> | <span data-ttu-id="d8725-122">20348.1405</span><span class="sxs-lookup"><span data-stu-id="d8725-122">20348.1405</span></span> |
| [<span data-ttu-id="d8725-123">証明書マネージャーの PFX ファイルのサポート</span><span class="sxs-lookup"><span data-stu-id="d8725-123">PFX file support for Certificate Manager</span></span>](#pfx-file-support-for-certificate-manager) | <span data-ttu-id="d8725-124">設定 UI を使用した PFX 証明書の追加</span><span class="sxs-lookup"><span data-stu-id="d8725-124">Add PFX certs via Settings UI</span></span> | <span data-ttu-id="d8725-125">エンド ユーザー</span><span class="sxs-lookup"><span data-stu-id="d8725-125">End User</span></span> | <span data-ttu-id="d8725-126">20348.1405</span><span class="sxs-lookup"><span data-stu-id="d8725-126">20348.1405</span></span> |
| [<span data-ttu-id="d8725-127">HoloLens の設定で詳細な診断レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="d8725-127">View advanced diagnostic report in Settings on HoloLens</span></span>](#view-advanced-diagnostic-report-in-settings-on-hololens) | <span data-ttu-id="d8725-128">デバイスで MDM 診断ログを表示する</span><span class="sxs-lookup"><span data-stu-id="d8725-128">View MDM diagnostic logs on device</span></span> | <span data-ttu-id="d8725-129">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d8725-129">Troubleshooting</span></span> | <span data-ttu-id="d8725-130">20348.1405</span><span class="sxs-lookup"><span data-stu-id="d8725-130">20348.1405</span></span> |
| [<span data-ttu-id="d8725-131">オフライン診断の通知</span><span class="sxs-lookup"><span data-stu-id="d8725-131">Offline Diagnostics notifications</span></span>](#offline-diagnostics-notifications) | <span data-ttu-id="d8725-132">ログ収集に関する audiovisual フィードバック</span><span class="sxs-lookup"><span data-stu-id="d8725-132">Audiovisual feedback for log collection</span></span> | <span data-ttu-id="d8725-133">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d8725-133">Troubleshooting</span></span> | <span data-ttu-id="d8725-134">20348.1405</span><span class="sxs-lookup"><span data-stu-id="d8725-134">20348.1405</span></span> |


### <a name="csp-changes-for-reporting-hololens-details"></a><span data-ttu-id="d8725-135">レポート HoloLens の詳細の CSP の変更</span><span class="sxs-lookup"><span data-stu-id="d8725-135">CSP changes for reporting HoloLens details</span></span>

- <span data-ttu-id="d8725-136">Windows Insider build、20348.1403 で導入されました</span><span class="sxs-lookup"><span data-stu-id="d8725-136">Introduced in Windows Insider build, 20348.1403</span></span>

<span data-ttu-id="d8725-137">次の csp は、HoloLens デバイスから情報をレポートする新しい方法で更新されました。</span><span class="sxs-lookup"><span data-stu-id="d8725-137">The following CSPs have been updated with new ways to report information from your HoloLens devices.</span></span>

#### <a name="devdetail-csp---free-storage"></a><span data-ttu-id="d8725-138">DevDetail CSP-Free Storage</span><span class="sxs-lookup"><span data-stu-id="d8725-138">DevDetail CSP - Free Storage</span></span>

<span data-ttu-id="d8725-139">devdetail CSP は HoloLens デバイスの空き記憶域も報告するようになりました。</span><span class="sxs-lookup"><span data-stu-id="d8725-139">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="d8725-140">これは、設定アプリの Storage ページに表示される値とほぼ一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8725-140">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="d8725-141">この情報を含む特定のノードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d8725-141">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="d8725-142">./DevDetail/Ext/Microsoft/FreeStorage (GET 操作のみ)</span><span class="sxs-lookup"><span data-stu-id="d8725-142">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp---ssid-and-bssid"></a><span data-ttu-id="d8725-143">DeviceStatus CSP-SSID および BSSID</span><span class="sxs-lookup"><span data-stu-id="d8725-143">DeviceStatus CSP - SSID and BSSID</span></span>

<span data-ttu-id="d8725-144">devicestatus CSP は、HoloLens がアクティブに接続されている Wi-Fi ネットワークの SSID と BSSID も報告するようになりました。</span><span class="sxs-lookup"><span data-stu-id="d8725-144">DeviceStatus CSP now also reports SSID and BSSID of Wi-Fi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="d8725-145">この情報を含む特定のノードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d8725-145">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="d8725-146">*Wi-Fi アダプタ/SSID の/Vendor/MSFT/DeviceStatus/NetworkIdentifiers/mac アドレス*</span><span class="sxs-lookup"><span data-stu-id="d8725-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="d8725-147">*Wi-Fi アダプタ/BSSID の/Vendor/MSFT/DeviceStatus/NetworkIdentifiers/mac アドレス*</span><span class="sxs-lookup"><span data-stu-id="d8725-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="d8725-148">ネットワーク識別子を照会するための syncml blob の例 (MDM ベンダー向け)</span><span class="sxs-lookup"><span data-stu-id="d8725-148">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

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

### <a name="auto-login-policy-controlled-by-csp"></a><span data-ttu-id="d8725-149">CSP によって制御される自動ログインポリシー</span><span class="sxs-lookup"><span data-stu-id="d8725-149">Auto login policy controlled by CSP</span></span>

<span data-ttu-id="d8725-150">この新しい AutoLogonUser ポリシーは、ユーザーが自動的にログオンするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d8725-150">This new AutoLogonUser policy controls whether a user will be automatically logged on.</span></span> <span data-ttu-id="d8725-151">一部のお客様は、id に関連付けられているものの、サインインエクスペリエンスが不要なデバイスを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8725-151">Some customers want to set up devices that are tied to an identity but don't want any sign-in experience.</span></span> <span data-ttu-id="d8725-152">デバイスを選択し、リモートアシスタンスをすぐに使用する Imagine ます。</span><span class="sxs-lookup"><span data-stu-id="d8725-152">Imagine picking up a device and using remote assist immediately.</span></span> <span data-ttu-id="d8725-153">または、HoloLens デバイスを迅速に配布し、エンドユーザーがログインを迅速に行えるようにするという利点があります。</span><span class="sxs-lookup"><span data-stu-id="d8725-153">Or have a benefit of being able to rapidly  distribute HoloLens devices and enable their end users to expedite login.</span></span>

<span data-ttu-id="d8725-154">ポリシーが空でない値に設定されている場合は、自動ログオンユーザーの電子メールアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8725-154">When the policy is set to a non-empty value, it specifies the email address of the auto-logon user.</span></span> <span data-ttu-id="d8725-155">自動ログオンを有効にするには、指定されたユーザーがデバイスに少なくとも1回ログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8725-155">The specified user must logon to the device at least once to enable auto-logon.</span></span>

<span data-ttu-id="d8725-156">新しいポリシー `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` 文字列値の oma-uri</span><span class="sxs-lookup"><span data-stu-id="d8725-156">The OMA-URI of new policy `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` String value</span></span>

- <span data-ttu-id="d8725-157">同じ電子メールアドレスを持つユーザーは、自動ログオンが有効になります。</span><span class="sxs-lookup"><span data-stu-id="d8725-157">User with the same email address will have auto logon enabled.</span></span>

<span data-ttu-id="d8725-158">このポリシーが構成されているデバイスでは、ポリシーで指定されたユーザーが少なくとも1回ログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8725-158">On a device where this policy is configured, the user specified in the policy will need to logon at least once.</span></span> <span data-ttu-id="d8725-159">最初のログオン後にデバイスを再起動すると、指定したユーザーが自動的にログオンします。</span><span class="sxs-lookup"><span data-stu-id="d8725-159">Subsequent reboots of the device after the first logon will have the specified user automatically logged on.</span></span> <span data-ttu-id="d8725-160">1つの自動ログオンユーザーのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d8725-160">Only a single auto-logon user is supported.</span></span> <span data-ttu-id="d8725-161">有効にすると、自動的にログオンしたユーザーは手動でログアウトできなくなります。</span><span class="sxs-lookup"><span data-stu-id="d8725-161">Once enabled, the automatically logged on user will not be able to log out manually.</span></span> <span data-ttu-id="d8725-162">別のユーザーとしてログオンするには、まずポリシーを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8725-162">To logon as a different user, the policy must first be disabled.</span></span>

> [!NOTE]
> - <span data-ttu-id="d8725-163">主要な OS の更新などの一部のイベントでは、指定されたユーザーがデバイスにもう一度ログオンして、自動ログオンの動作を再開することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d8725-163">Some events such as major OS updates may require the specified user to logon to the device again to resume auto-logon behavior.</span></span> 
> - <span data-ttu-id="d8725-164">自動ログオンは、MSA および AAD ユーザーに対してのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d8725-164">Auto-logon is only supported for MSA and AAD users.</span></span>

### <a name="pfx-file-support-for-certificate-manager"></a><span data-ttu-id="d8725-165">証明書マネージャーの PFX ファイルのサポート</span><span class="sxs-lookup"><span data-stu-id="d8725-165">PFX file support for Certificate Manager</span></span>

<span data-ttu-id="d8725-166">Windows Insider build 20348.1405 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="d8725-166">Introduced in Windows Insider build 20348.1405.</span></span> <span data-ttu-id="d8725-167">.Pfx 証明書を使用するように、 [証明書マネージャー](certificate-manager.md) にサポートを追加しました。</span><span class="sxs-lookup"><span data-stu-id="d8725-167">We’ve added support to the [Certificate Manager](certificate-manager.md) to now use .pfx certificates.</span></span> <span data-ttu-id="d8725-168">ユーザーが  >  **& セキュリティ**  >  **証明書** を更新設定に移動し、[**証明書のインストール**] を選択すると、UI で .pfx 証明書ファイルがサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d8725-168">When users navigate to **Settings** > **Update & Security** > **Certificates**, and select **Install a certificate** the UI now supports .pfx certificate file.</span></span>
<span data-ttu-id="d8725-169">ユーザーは、秘密キーを持つ .pfx 証明書をユーザーストアまたはコンピューターストアにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="d8725-169">Users can import .pfx certificate, with private key, to user store or machine store.</span></span>

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a><span data-ttu-id="d8725-170">HoloLens の設定で詳細な診断レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="d8725-170">View advanced diagnostic report in Settings on HoloLens</span></span>

<span data-ttu-id="d8725-171">管理対象デバイスでの動作のトラブルシューティングでは、必要なポリシー構成が適用されていることを確認することが重要な手順です。</span><span class="sxs-lookup"><span data-stu-id="d8725-171">For managed devices when troubleshooting behavior, confirming that an expected policy configuration is applied is an important step.</span></span> <span data-ttu-id="d8725-172">これまでの新機能では、**設定** アカウントによって収集された mdm 診断ログをエクスポートした後、mdm またはデバイスの近くでデバイスを使用する必要がありました。これには、  ->    >  **職場または学校へのアクセス権** があります。また、**管理ログをエクスポート** し、近くの PC に表示します。</span><span class="sxs-lookup"><span data-stu-id="d8725-172">Previously to this new feature, this had to be done off device via MDM or near the device after exporting MDM diagnostic logs gathered via **Settings** -> **Accounts** > **Access work or school**, and select **Export your management logs** and viewed on a nearby PC.</span></span>

<span data-ttu-id="d8725-173">これで、Edge ブラウザーを使用してデバイスで MDM 診断を表示できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d8725-173">Now the MDM Diagnostics can be viewed on device using the Edge browser.</span></span> <span data-ttu-id="d8725-174">MDM 診断レポートをより簡単に表示するには、[職場または学校へのアクセス] ページに移動し、[ **詳細な診断レポートの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8725-174">To more easily view the MDM Diagnostic report navigate to the Access work or school page, and select **View advanced diagnostic report**.</span></span> <span data-ttu-id="d8725-175">これにより、レポートが生成され、新しいエッジウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="d8725-175">This will generate and open the report in a new Edge window.</span></span>

![設定アプリで詳細な診断レポートを表示します。](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a><span data-ttu-id="d8725-177">オフライン診断の通知</span><span class="sxs-lookup"><span data-stu-id="d8725-177">Offline Diagnostics notifications</span></span>

<span data-ttu-id="d8725-178">これは、 [オフライン診断](hololens-diagnostic-logs.md#offline-diagnostics)と呼ばれる既存の機能の更新プログラムです。</span><span class="sxs-lookup"><span data-stu-id="d8725-178">This an update for an existing feature called [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span> <span data-ttu-id="d8725-179">以前は、診断コレクションがトリガーされたか、または完了したことをユーザーに明確に示すインジケーターがありませんでした。</span><span class="sxs-lookup"><span data-stu-id="d8725-179">Previously, there was no clear indicator to users that they had triggered diagnostic collection or it had completed.</span></span>
<span data-ttu-id="d8725-180">Windows Insider ビルドに追加された、オフライン診断に対するオーディオビジュアルフィードバックには、2つの形式があります。</span><span class="sxs-lookup"><span data-stu-id="d8725-180">Now added in Windows Insider builds, there are two forms of audiovisual feedback for Offline Diagnostics.</span></span> <span data-ttu-id="d8725-181">コレクションの開始時と完了時の両方について、最初に表示されるトースト通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8725-181">The first being toasts notifications displayed for both when collection starts and completes.</span></span> <span data-ttu-id="d8725-182">これらは、ユーザーがログインし、視覚エフェクトを持っているときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8725-182">These will be displayed when the user is logged in and has visuals.</span></span>

![ログを収集するためのトースト。](./images/logcollection1.jpg)

![ログの収集が完了したときのトースト。](./images/logcollection2.jpg)
 
<span data-ttu-id="d8725-185">多くの場合、ユーザーがディスプレイにアクセスできない場合にはフォールバックログ収集メカニズムとしてオフライン診断を使用しますが、ログインができない場合や、まだ OOBE にある場合は、ログが収集されるときにオーディオキューも再生されます。</span><span class="sxs-lookup"><span data-stu-id="d8725-185">Because users often use Offline Diagnostics as a fallback log gathering mechanism for when they don’t have access to a display, can’t log-in or are still in OOBE there will also be an audio cue played when logs are gathered.</span></span> <span data-ttu-id="d8725-186">このサウンドは、トースト通知に加えて再生されます。</span><span class="sxs-lookup"><span data-stu-id="d8725-186">This sound will be played in addition to the toast notification.</span></span>

<span data-ttu-id="d8725-187">この新機能は、デバイスの更新時に有効になり、有効にしたり管理したりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d8725-187">This new feature will be enabled when your device updates, and doesn’t need to be enabled or managed.</span></span> <span data-ttu-id="d8725-188">この新しいフィードバックを表示したり聞いたりできない場合でも、オフライン診断は引き続き生成されます。</span><span class="sxs-lookup"><span data-stu-id="d8725-188">In any event that this new feedback cannot be displayed or heard, Offline Diagnostics will still be generated.</span></span>

<span data-ttu-id="d8725-189">この新しいオーディオビジュアルフィードバックの追加により、診断データを簡単に収集し、問題のトラブルシューティングをより簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d8725-189">We hope with this newer addition of audiovisual feedback it is easier to gather diagnostic data, and more quickly be able to troubleshoot your problems.</span></span>



### <a name="fixes-and-improvements"></a><span data-ttu-id="d8725-190">修正と改善:</span><span class="sxs-lookup"><span data-stu-id="d8725-190">Fixes and improvements:</span></span>

- <span data-ttu-id="d8725-191">[ロックされたファイルをダウンロードするプロンプトがないデバイスポータルの既知の問題を修正しました。](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="d8725-191">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="d8725-192">[ファイルのアップロードとダウンロードのタイムアウトを含むデバイスポータルの既知の問題](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)を修正した。</span><span class="sxs-lookup"><span data-stu-id="d8725-192">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>


## <a name="start-receiving-insider-builds"></a><span data-ttu-id="d8725-193">Insider ビルドの受信を開始します</span><span class="sxs-lookup"><span data-stu-id="d8725-193">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="d8725-194">最近更新したことがない場合は、デバイスを再起動して状態を更新し、最新のビルドを取得してください。</span><span class="sxs-lookup"><span data-stu-id="d8725-194">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="d8725-195">"デバイスの再起動" 音声コマンドは正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="d8725-195">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="d8725-196">設定/Windows Insider プログラムで [再起動] ボタンを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="d8725-196">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="d8725-197">バックエンドには、発生した可能性があるバグがあり、これによって追跡が再開されます。</span><span class="sxs-lookup"><span data-stu-id="d8725-197">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="d8725-198">HoloLens 2 デバイスで、[   >  **セキュリティ**  >  **Windows Insider program** & 設定更新] をクリックし、[**開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8725-198">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="d8725-199">Windows Insider として登録するために使用したアカウントをリンクします。</span><span class="sxs-lookup"><span data-stu-id="d8725-199">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="d8725-200">Windows insider がチャネルに移行しています。</span><span class="sxs-lookup"><span data-stu-id="d8725-200">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="d8725-201">高速 **リング** は開発チャネルになり、低速リングはベータ チャネル になり、リリース プレビュー リングはリリースプレビュー チャネル **になります**。</span><span class="sxs-lookup"><span data-stu-id="d8725-201">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="d8725-202">マッピングは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8725-202">Here is what that mapping looks like:</span></span>

![WindowsInsider Channels の説明](images/WindowsInsiderChannels.png)

<span data-ttu-id="d8725-204">詳細については、「 [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8725-204">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="d8725-205">次 **に、[** Windows のアクティブな開発 ] を選択し、開発チャネルを受け取ベータ チャネルビルドを受け取 **る** かどうかを選択し、プログラムの用語を確認します。</span><span class="sxs-lookup"><span data-stu-id="d8725-205">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="d8725-206">[Confirm **> Restart Now]を選択して** 完了します。</span><span class="sxs-lookup"><span data-stu-id="d8725-206">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="d8725-207">デバイスが再起動したら、[Update 設定 > **Security]** &に移動>更新プログラムを確認して最新のビルドを取得します。</span><span class="sxs-lookup"><span data-stu-id="d8725-207">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="d8725-208">更新エラー 0x80070490回避</span><span class="sxs-lookup"><span data-stu-id="d8725-208">Update error 0x80070490 work-around</span></span>

<span data-ttu-id="d8725-209">Dev または Beta チャネルで更新0x80070490更新エラーが発生した場合は、次の短期的な回避を試してください。</span><span class="sxs-lookup"><span data-stu-id="d8725-209">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="d8725-210">インサイダー チャネルを移動し、更新プログラムを選択してから、Insider チャネルを戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8725-210">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>

#### <a name="stage-one---release-preview"></a><span data-ttu-id="d8725-211">ステージ 1 - リリース プレビュー</span><span class="sxs-lookup"><span data-stu-id="d8725-211">Stage one - Release Preview</span></span>

1.  <span data-ttu-id="d8725-212">設定セキュリティの更新&、Windows Insider Programリリース プレビュー チャネル **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d8725-212">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>

2.  <span data-ttu-id="d8725-213">設定セキュリティの更新&更新プログラムWindows更新プログラムの **確認」を参照してください**。</span><span class="sxs-lookup"><span data-stu-id="d8725-213">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="d8725-214">更新後、ステージ 2 に進む。</span><span class="sxs-lookup"><span data-stu-id="d8725-214">After the update, continue on to Stage two.</span></span>

#### <a name="stage-two---dev-channel"></a><span data-ttu-id="d8725-215">ステージ 2 - 開発チャネル</span><span class="sxs-lookup"><span data-stu-id="d8725-215">Stage two - Dev Channel</span></span>

1. <span data-ttu-id="d8725-216">設定セキュリティの更新&、Windows Insider Program Dev Channel ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d8725-216">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>

2. <span data-ttu-id="d8725-217">設定セキュリティの更新&更新プログラムWindows更新プログラムの **確認」を参照してください**。</span><span class="sxs-lookup"><span data-stu-id="d8725-217">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>

## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="d8725-218">FFU のダウンロードとフラッシュの方向</span><span class="sxs-lookup"><span data-stu-id="d8725-218">FFU download and flash directions</span></span>

<span data-ttu-id="d8725-219">フライト署名済み ffu でテストするには、フライト署名済み ffu をフラッシュする前に、まずデバイスのロックを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8725-219">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>

1. <span data-ttu-id="d8725-220">PC の場合:</span><span class="sxs-lookup"><span data-stu-id="d8725-220">On PC:</span></span>
    1. <span data-ttu-id="d8725-221">から ffu を PC にダウンロードします [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。</span><span class="sxs-lookup"><span data-stu-id="d8725-221">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="d8725-222">ARC (Advanced Recovery Companion) を次のコマンドからMicrosoft Storeします [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 。</span><span class="sxs-lookup"><span data-stu-id="d8725-222">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="d8725-223">[HoloLens - Flight Unlock: Update 設定 Security &を開Windows Insider Program  >    >  サインアップし、デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d8725-223">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="d8725-224">Flash FFU - ARC を使用してフライト署名済み FFU をフラッシュできます。</span><span class="sxs-lookup"><span data-stu-id="d8725-224">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="d8725-225">フィードバックを提供し、問題を報告する</span><span class="sxs-lookup"><span data-stu-id="d8725-225">Provide feedback and report issues</span></span>

<span data-ttu-id="d8725-226">フィードバックを[提供フィードバック Hub問題を報告](hololens-feedback.md)するには、HoloLensアプリを使用してください。</span><span class="sxs-lookup"><span data-stu-id="d8725-226">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="d8725-227">このフィードバック Hubを使用すると、エンジニアが問題をすばやくデバッグして解決するのに役立つ、必要なすべての診断情報が確実に含まれます。</span><span class="sxs-lookup"><span data-stu-id="d8725-227">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="d8725-228">中国語と日本語のバージョンに関する問題HoloLens同じように報告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8725-228">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="d8725-229">[ドキュメント] フォルダーにアクセスするかどうかを確認するプロンプトフィードバック Hub受け入れる必要があります (メッセージが表示されたら、[は **い]** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="d8725-229">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <a name="note-for-developers"></a><span data-ttu-id="d8725-230">開発者向けの注意</span><span class="sxs-lookup"><span data-stu-id="d8725-230">Note for developers</span></span>

<span data-ttu-id="d8725-231">アプリケーションの Insider ビルドを使用してアプリケーションの開発を試みHoloLens。</span><span class="sxs-lookup"><span data-stu-id="d8725-231">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="d8725-232">使用を開始[するにはHoloLens開発者向けドキュメント](https://developer.microsoft.com/windows/mixed-reality/development)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8725-232">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="d8725-233">これらの同じ手順は、アプリケーションの Insider ビルドHoloLens。</span><span class="sxs-lookup"><span data-stu-id="d8725-233">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="d8725-234">Unity のビルドと同じビルドを使用してVisual Studio開発に既に使用している同じHoloLensできます。</span><span class="sxs-lookup"><span data-stu-id="d8725-234">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="d8725-235">Insider ビルドの受信を停止する</span><span class="sxs-lookup"><span data-stu-id="d8725-235">Stop receiving Insider builds</span></span>

<span data-ttu-id="d8725-236">Windows Holographic の Insider ビルドを受け取らなくなった場合は、HoloLens が実稼働ビルドを実行している場合はオプトアウトできます。または、Advanced [](hololens-recovery.md) Recovery Companion を使用してデバイスを回復して、Insider 以外のバージョンの Windows Holographic にデバイスを回復することもできます。</span><span class="sxs-lookup"><span data-stu-id="d8725-236">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="d8725-237">新しいプレビュー ビルドを手動で再インストールした後に Insider Preview から登録を解除したユーザーがブルー スクリーンを表示する既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="d8725-237">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="d8725-238">その後、デバイスを手動で回復する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8725-238">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="d8725-239">影響を受け取る可能性がある場合の詳細については、この既知の問題に関するページを [参照してください](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)。</span><span class="sxs-lookup"><span data-stu-id="d8725-239">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>

<span data-ttu-id="d8725-240">お使HoloLensが実稼働ビルドを実行している場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d8725-240">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="d8725-241">[System **設定 > About] >に移動** し、ビルド番号を見つける。</span><span class="sxs-lookup"><span data-stu-id="d8725-241">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="d8725-242">[実稼働ビルド番号については、リリース ノートを参照してください](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="d8725-242">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="d8725-243">Insider ビルドをオプトアウトするには:</span><span class="sxs-lookup"><span data-stu-id="d8725-243">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="d8725-244">実稼働ビルドHoloLens実行中のアプリで、設定 > **Update & Security**> Windows Insider Program に移動し、[Stop Insider builds]/(Insider ビルドの停止)を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d8725-244">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="d8725-245">指示に従ってデバイスをオプトアウトします。</span><span class="sxs-lookup"><span data-stu-id="d8725-245">Follow the instructions to opt out your device.</span></span>
