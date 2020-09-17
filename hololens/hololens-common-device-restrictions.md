---
title: 一般的なデバイスの制限
description: デバイス restrctions は、HoloLens で一般的に設定されています。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ace1e071b3d73855daacc8a11ac87770fb7f5f99
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016791"
---
# <span data-ttu-id="ad923-103">一般的なデバイスの制限</span><span class="sxs-lookup"><span data-stu-id="ad923-103">Common Device Restrictions</span></span> 

<span data-ttu-id="ad923-104">このガイドは、IT 担当者が企業の Windows 10 ホログラフィック OS で使用できる、より一般的に使用される管理オプションについて理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ad923-104">This guide helps IT professionals understand the more commonly used management options available for the Windows 10 Holographic OS in the enterprise.</span></span> <span data-ttu-id="ad923-105">これらのポリシーを MDM ベンダーで有効にする方法については、MDM システムのマニュアルをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ad923-105">Please consult your MDM system documentation to understand how these policies are enabled by your MDM vendor.</span></span> <span data-ttu-id="ad923-106">このガイドで説明する設定がすべての MDM システムでサポートされるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="ad923-106">Not all MDM systems support every setting described in this guide.</span></span> <span data-ttu-id="ad923-107">一部の設定では、OMA-URI XML ファイルを通じてカスタム ポリシーがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ad923-107">Some support custom policies through OMA-URI XML files.</span></span> <span data-ttu-id="ad923-108">「[Microsoft Intune によるカスタム ポリシーのサポート](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ad923-108">See [Microsoft Intune support for Custom Policies](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span></span> <span data-ttu-id="ad923-109">命名規則は、MDM ベンダーによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ad923-109">Naming conventions may also vary among MDM vendors.</span></span>

## <span data-ttu-id="ad923-110">設定変更の防止</span><span class="sxs-lookup"><span data-stu-id="ad923-110">Prevent changing of settings</span></span>
<span data-ttu-id="ad923-111">通常、従業員は企業のデバイス上でロックダウンする必要のある個人のデバイスの特定の設定を変更することが許可されています。</span><span class="sxs-lookup"><span data-stu-id="ad923-111">Employees are usually allowed to change certain personal device settings that you may want to lock down on corporate devices.</span></span> <span data-ttu-id="ad923-112">従業員は、設定 UI を通じて、HoloLens の特定の設定を対話的に調整できます。</span><span class="sxs-lookup"><span data-stu-id="ad923-112">Employees can interactively adjust certain settings of the HoloLens through the settings UI.</span></span> <span data-ttu-id="ad923-113">MDM を使用すると、ユーザーが変更できる設定を制限できます。</span><span class="sxs-lookup"><span data-stu-id="ad923-113">Using MDM, you can limit what users are allowed to change.</span></span> <span data-ttu-id="ad923-114">次の一覧は、Windows 10 ホログラフィックで設定の制限を構成するためにサポートされている MDM 設定の一般的な例を示しています。</span><span class="sxs-lookup"><span data-stu-id="ad923-114">The following lists commonly used MDM settings that Windows 10 Holographic supports to configure settings restrictions:</span></span>
-   <span data-ttu-id="ad923-115">[VPN を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) ユーザーが VPN 設定を変更できるようにします</span><span class="sxs-lookup"><span data-stu-id="ad923-115">[Allow VPN:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Allows the user to change VPN settings</span></span>
-   <span data-ttu-id="ad923-116">[WiFi の手動構成を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) ユーザーが MDM プロビジョニングされたネットワークの外部で Wi-fi 接続を確立することを許可します</span><span class="sxs-lookup"><span data-stu-id="ad923-116">[Allow Manual WiFi Configuration:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Allows users to make Wi-Fi connections outside of MDM provisioned networks</span></span>
-   <span data-ttu-id="ad923-117">[MDM Unenrollment を手動で許可する](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) ユーザーがワークプレースアカウントの削除を許可されているかどうか (例: MDM システムからデバイスを登録解除する)</span><span class="sxs-lookup"><span data-stu-id="ad923-117">[Allow Manual MDM Unenrollment](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Whether users are allowed to delete the workplace account (i.e., unenroll the device from the MDM system)</span></span>

<span data-ttu-id="ad923-118">HoloLens でサポートされている[ポリシーの csp](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)でポリシーオプションの詳細を確認する</span><span class="sxs-lookup"><span data-stu-id="ad923-118">Find more details on policy options in the HoloLens supported [Policy CSPs](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)</span></span>

## <span data-ttu-id="ad923-119">ハードウェアの制限</span><span class="sxs-lookup"><span data-stu-id="ad923-119">Hardware restrictions</span></span>
<span data-ttu-id="ad923-120">Windows 10 ホログラフィックデバイスでは、カメラ、マイク、スピーカー、USB インターフェイス、Bluetooth インターフェイス、Wi-fi などの一般的なハードウェア機能を含む、最先端の技術を使用しています。</span><span class="sxs-lookup"><span data-stu-id="ad923-120">Windows 10 Holographic devices use state-of-the-art technology that includes popular hardware features such as cameras, microphones, speakers, USB interfaces, Bluetooth interfaces, and Wi-Fi.</span></span> <span data-ttu-id="ad923-121">ハードウェアの制限を使って、これらの機能の利用を制御できます。</span><span class="sxs-lookup"><span data-stu-id="ad923-121">You can use hardware restrictions to control the availability of these features.</span></span>
<span data-ttu-id="ad923-122">次の表は、Windows 10 ホログラフィックでハードウェアの制限を構成するためにサポートされる MDM 設定の一般的な例を示しています。</span><span class="sxs-lookup"><span data-stu-id="ad923-122">The following lists commonly used MDM settings that Windows 10 Holographic supports to configure hardware restrictions:</span></span>

> [!NOTE]
> <span data-ttu-id="ad923-123">これらのハードウェア制限の一部は、接続性が影響を受け、データ保護を支援します。</span><span class="sxs-lookup"><span data-stu-id="ad923-123">Some of these hardware restrictions affect connectivity and assist in data protection.</span></span>

-   <span data-ttu-id="ad923-124">[Wi-fi を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) ユーザーがデバイスで WiFi 無線を有効にして使用できるかどうか。</span><span class="sxs-lookup"><span data-stu-id="ad923-124">[Allow Wi-Fi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Whether users can enable and use the WiFi radio on their devices.</span></span>
-   <span data-ttu-id="ad923-125">[USB 接続を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) USB 接続が有効になっているかどうか (USB 充電には影響ありません)</span><span class="sxs-lookup"><span data-stu-id="ad923-125">[Allow USB Connection:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Whether the USB connection is enabled (doesn’t affect USB charging.)</span></span>
-   <span data-ttu-id="ad923-126">[Bluetooth を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) ユーザーがデバイスで Bluetooth 無線を有効にして使用できるかどうか</span><span class="sxs-lookup"><span data-stu-id="ad923-126">[Allow Bluetooth:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Whether users can enable and use the Bluetooth radio on their devices.</span></span>
-   <span data-ttu-id="ad923-127">[カメラの制限:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Windows アプリがカメラにアクセスできるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="ad923-127">[Restrict Camera:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Specifies whether Windows apps can access the camera.</span></span>
-   <span data-ttu-id="ad923-128">[マイクの制限:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Windows アプリがマイクにアクセスできるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="ad923-128">[Restrict Microphones:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Specifies whether Windows apps can access the microphone.</span></span>
