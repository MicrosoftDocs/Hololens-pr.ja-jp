---
title: HoloLens 2 の証明書とネットワーク プロファイルを準備する
description: HoloLens 2 Mixed Reality デバイスでネットワーク用証明書を構成、使用、展開、トラブルシューティングする方法について説明します。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: eedb451847757eba02465d7ded4494b9712497ff
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397443"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a><span data-ttu-id="83a7e-103">HoloLens 2 の証明書とネットワーク プロファイルを準備する</span><span class="sxs-lookup"><span data-stu-id="83a7e-103">Prepare certificates and network profiles for HoloLens 2</span></span>

<span data-ttu-id="83a7e-104">証明書ベースの認証は、HoloLens 2 を使用するお客様の共通の要件です。</span><span class="sxs-lookup"><span data-stu-id="83a7e-104">Certificate-based authentication is a common requirement for customers using HoloLens 2.</span></span> <span data-ttu-id="83a7e-105">Wi-Fi にアクセスしたり、VPN ソリューションに接続したり、組織内の内部リソースにアクセスしたりするために証明書が必要となる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="83a7e-105">You might require certificates to access Wi-Fi, to connect to VPN solutions, or for accessing internal resources in your organization.</span></span>

<span data-ttu-id="83a7e-106">HoloLens 2 デバイスは通常、Azure Active Directory (Azure AD) に参加し、Intune やその他の MDM プロバイダーによって管理されるため、ご利用の MDM ソリューションに統合されているネットワーク デバイス登録サービス (SCEP) や公開キー暗号化標準 (PKCS) 証明書インフラストラクチャを使用して、そのような証明書を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83a7e-106">Because HoloLens 2 devices are typically joined to Azure Active Directory (Azure AD) and managed by Intune or other MDM provider, you will need to deploy such certificates by using a Simple Certificate Enrollment Protocol (SCEP) or Public Key Cryptography Standard (PKCS) certificate infrastructure that is integrated with your MDM solution.</span></span> 

>[!NOTE]
> <span data-ttu-id="83a7e-107">MDM プロバイダーがない場合でも、 [Windows 構成デザイナー](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab)の [プロビジョニングパッケージ](https://docs.microsoft.com/hololens/hololens-provisioning#steps-for-creating-provisioning-packages)または [証明書マネージャー](https://docs.microsoft.com/hololens/certificate-manager)を使用して証明書を展開することができます。そのためには、 **[設定] > [アップデートとセキュリティ] > [証明書マネージャー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="83a7e-107">If you do not have an MDM provider, you can still deploy certificates via a [provisioning package](https://docs.microsoft.com/hololens/hololens-provisioning#steps-for-creating-provisioning-packages) in [Windows Configuration Designer](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) or through [Certificate Manager](https://docs.microsoft.com/hololens/certificate-manager) by going to **Settings > Update & Security > Certificate Manager**.</span></span>

## <a name="certificate-requirements"></a><span data-ttu-id="83a7e-108">証明書の要件</span><span class="sxs-lookup"><span data-stu-id="83a7e-108">Certificate requirements</span></span>
<span data-ttu-id="83a7e-109">SCEP や PKCS インフラストラクチャを介して証明書を展開するには、ルート証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="83a7e-109">Root certificates are required to deploy certificates through a SCEP or PKCS infrastructure.</span></span> <span data-ttu-id="83a7e-110">組織内のその他のアプリケーションやサービスでは、HoloLens 2 デバイスにもルート証明書を展開する必要がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="83a7e-110">Other applications and services in your organization might require root certificates to be deployed to your HoloLens 2 devices as well.</span></span> 

## <a name="wi-fi-connectivity-requirements"></a><span data-ttu-id="83a7e-111">Wi-Fi 接続要件</span><span class="sxs-lookup"><span data-stu-id="83a7e-111">Wi-Fi connectivity requirements</span></span>
<span data-ttu-id="83a7e-112">企業ネットワークに必要な Wi-Fi 構成をデバイスに自動的に提供できるようにするには、Wi-Fi 構成プロファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="83a7e-112">To allow a device to be automatically provided with the required Wi-Fi configuration for your enterprise network, you will need a Wi-Fi configuration profile.</span></span> <span data-ttu-id="83a7e-113">Intune やその他の MDM プロバイダーを構成して、これらのプロファイルをデバイスに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="83a7e-113">You can configure Intune or other MDM provider to deploy these profiles to your devices.</span></span> <span data-ttu-id="83a7e-114">ネットワーク セキュリティによりデバイスをローカル ドメインの一部にする必要がある場合は、ご利用の Wi-Fi ネットワーク インフラストラクチャを評価し、HoloLens 2 デバイスとの互換性があることを確認する必要がある可能性があります (HoloLens 2 デバイスは Azure AD 参加済みのもののみ)。</span><span class="sxs-lookup"><span data-stu-id="83a7e-114">If your network security requires devices to be part of the local domain, you might also need to evaluate your Wi-Fi network infrastructure to make sure it's compatible with HoloLens 2 devices (HoloLens 2 devices are Azure AD-joined only).</span></span>

## <a name="deploy-certificate-infrastructure"></a><span data-ttu-id="83a7e-115">証明書インフラストラクチャを展開する</span><span class="sxs-lookup"><span data-stu-id="83a7e-115">Deploy certificate infrastructure</span></span>
<span data-ttu-id="83a7e-116">既存の SCEP や PKCS インフラストラクチャが存在しない場合は、1 つ用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83a7e-116">If no SCEP or PKCS infrastructure already exists, you'll need to prepare one.</span></span> <span data-ttu-id="83a7e-117">認証に SCEP や PKCS 証明書の使用をサポートするために、Intune では[証明書コネクタ](https://docs.microsoft.com/mem/intune/protect/certificate-connectors)の使用が必要になります。</span><span class="sxs-lookup"><span data-stu-id="83a7e-117">To support the use of SCEP or PKCS certificates for authentication, Intune requires the use of a [certificate connector](https://docs.microsoft.com/mem/intune/protect/certificate-connectors).</span></span>

> [!NOTE]
> <span data-ttu-id="83a7e-118">Microsoft CA で SCEP を使用する場合は、[ネットワーク デバイス登録サービス (NDES) ](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes)も構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83a7e-118">When you use SCEP with a Microsoft CA, you must also configure the [Network Device Enrollment Service (NDES)](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes)</span></span>

<span data-ttu-id="83a7e-119">詳細については、「[Microsoft Intune でデバイスの証明書プロファイルを構成する](https://docs.microsoft.com/intune/certificates-configure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83a7e-119">For more information, see [Configure a certificate profile for your devices in Microsoft Intune.](https://docs.microsoft.com/intune/certificates-configure)</span></span>

## <a name="deploy-certificates-and-wi-fivpn-profile"></a><span data-ttu-id="83a7e-120">証明書と Wi-Fi/VPN プロファイルを展開する</span><span class="sxs-lookup"><span data-stu-id="83a7e-120">Deploy certificates and Wi-Fi/VPN profile</span></span>
<span data-ttu-id="83a7e-121">証明書とプロファイルを展開するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="83a7e-121">To deploy certificates and profiles, follow these steps:</span></span>
1.  <span data-ttu-id="83a7e-122">ルート証明書と中間証明書のそれぞれにプロファイルを作成します (「[信頼証明書プロファイルの作成](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles)」を参照してください)。各プロファイルには、DD/MM/YYYY 形式による有効期限を含む説明が必要です。</span><span class="sxs-lookup"><span data-stu-id="83a7e-122">Create a profile for each of the Root and Intermediate certificates (see [Create trusted certificate profiles](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles).) Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> <span data-ttu-id="83a7e-123">**有効期限のない証明書プロファイルは、展開されません。**</span><span class="sxs-lookup"><span data-stu-id="83a7e-123">**Certificate profiles without an expiration date will not be deployed.**</span></span>
1.  <span data-ttu-id="83a7e-124">SCEP 証明書または PKCS 証明書のそれぞれにプロファイルを作成します ([「SCEP 証明書プロファイルの作成」または「PKCS 証明書プロファイルの作成」](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)を参照してください)。各プロファイルには、DD/MM/YYYY 形式による有効期限を含む説明が必要です。</span><span class="sxs-lookup"><span data-stu-id="83a7e-124">Create a profile for each SCEP or PKCS certificates (see [Create a SCEP certificate profile or Create a PKCS certificate profile](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Each of these profiles must have a description that includes an expiration date in DD/MM/YYYY format.</span></span> <span data-ttu-id="83a7e-125">**有効期限のない証明書プロファイルは、展開されません。**</span><span class="sxs-lookup"><span data-stu-id="83a7e-125">**Certificate profiles without an expiration date will not be deployed.**</span></span>

    > [!NOTE]
    > <span data-ttu-id="83a7e-126">HoloLens 2 は共有デバイスであり、デバイスごとに複数のユーザーがいると多くの方が認識されているように、可能であれば Wi-Fi 認証にはユーザー証明書ではなくデバイス証明書を展開することをお勧めします</span><span class="sxs-lookup"><span data-stu-id="83a7e-126">As the HoloLens 2 is considered for many to be a shared device, multiple users per device, it is recommended to deploy Device certificates instead of User certificates for Wi-Fi authentication where possible</span></span>

3.  <span data-ttu-id="83a7e-127">企業の Wi-Fi ネットワークごとにプロファイルを作成します ([「Windows 10 以降のデバイスの Wi-Fi 設定」](https://docs.microsoft.com/intune/wi-fi-settings-windows)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="83a7e-127">Create a profile for each corporate Wi-Fi network (see [Wi-Fi settings for Windows 10 and later devices](https://docs.microsoft.com/intune/wi-fi-settings-windows)).</span></span> 
    > [!NOTE]
    > <span data-ttu-id="83a7e-128">Wi-Fi プロファイルは、可能であればユーザー グループではなくデバイス グループに[割り当て済み](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="83a7e-128">It is recommended that the Wi-Fi profile be [assigned](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) to Device groups rather than User groups where possible.</span></span> 

    > [!TIP]
    > <span data-ttu-id="83a7e-129">また、企業ネットワーク上の Windows 10 PC から実行中の Wi-Fi プロファイルをエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="83a7e-129">You also can export a working Wi-Fi profile from a Windows 10 PC on your corporate network.</span></span> <span data-ttu-id="83a7e-130">このエクスポートでは、現在のすべての設定を含む XML ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="83a7e-130">This export creates an XML file with all the current settings.</span></span> <span data-ttu-id="83a7e-131">次に、このファイルを Intune にインポートして、HoloLens 2 デバイスの Wi-Fi プロファイルとして使用します。</span><span class="sxs-lookup"><span data-stu-id="83a7e-131">Then, import this file into Intune, and use it as the Wi-Fi profile for your HoloLens 2 devices.</span></span> <span data-ttu-id="83a7e-132">[Windows デバイスの Wi-Fi 設定のエクスポートとインポート](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="83a7e-132">See [Export and import Wi-Fi settings for Windows devices.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)</span></span>

4.  <span data-ttu-id="83a7e-133">企業 VPN ごとにプロファイルを作成します ([「Windows 10 および Windows Holographic デバイス設定で Intune を使用する VPN 接続を追加」](https://docs.microsoft.com/intune/vpn-settings-windows-10)を参照)。</span><span class="sxs-lookup"><span data-stu-id="83a7e-133">Create a profile for each corporate VPN (see [Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/intune/vpn-settings-windows-10)).</span></span>

## <a name="troubleshooting-certificates"></a><span data-ttu-id="83a7e-134">証明書のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="83a7e-134">Troubleshooting certificates</span></span>

<span data-ttu-id="83a7e-135">証明書が正しく展開されていることを検証する必要がある場合は、デバイスの[証明書マネージャー](certificate-manager.md)を使用して、証明書が存在することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="83a7e-135">In the event that you need to validate that a certificate is deployed correctly please use the [Certificate Manager](certificate-manager.md) on the device to verify your certificate is present.</span></span>  

>[!WARNING]
> <span data-ttu-id="83a7e-136">MDM によって展開された証明書は証明書マネージャーで表示できますが、証明書マネージャーでアンインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="83a7e-136">Although you can view MDM-deployed certificates in Certificate Manager, you cannot uninstall them in Certificate Manager.</span></span> <span data-ttu-id="83a7e-137">MDM を使用してアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="83a7e-137">You must uninstall them through MDM.</span></span>


