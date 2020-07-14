---
title: 無線と Wi-Fi
description: 無線と Wi-Fi
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: security、hololens、ワイヤレス、Wi-fi
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2771e6e5e428b2705fc2f495823480a9514fa71a
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865774"
---
# <span data-ttu-id="069ba-104">無線と Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="069ba-104">Wireless and Wi-Fi</span></span>

<span data-ttu-id="069ba-105">HoloLens 2 ワイヤレス LAN 接続は、次のような最新の Wi-fi セキュリティ標準をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="069ba-105">HoloLens 2 Wireless LAN connectivity supports an impressive range of the latest Wi-Fi security standards, such as:</span></span>
  * <span data-ttu-id="069ba-106">WPA2 (Wi-fi 保護アクセス 2)</span><span class="sxs-lookup"><span data-stu-id="069ba-106">WPA2 (Wi-Fi Protected Access 2)</span></span>  
  * <span data-ttu-id="069ba-107">TEAP (トンネル拡張認証プロトコル)</span><span class="sxs-lookup"><span data-stu-id="069ba-107">TEAP (Tunnel Extensible Authentication Protocol)</span></span>  
  * <span data-ttu-id="069ba-108">OWE (適時的ワイヤレス暗号化)</span><span class="sxs-lookup"><span data-stu-id="069ba-108">OWE (Opportunistic Wireless Encryption)</span></span>

<span data-ttu-id="069ba-109">TEAP (次世代のエンタープライズ ネットワーク認証) を使用すると、複数の資格情報を 1 つのトランザクションに安全に連結できます。</span><span class="sxs-lookup"><span data-stu-id="069ba-109">TEAP, the next generation of enterprise network authentication, provides the ability to securely chain multiple credentials into a single transaction.</span></span>  <span data-ttu-id="069ba-110">これにより管理者は、同じ認証トランザクション間で、コンピューターとユーザーの両方に有効なアイデンティティを要求することにより、セキュリティ態勢をより強化できます。</span><span class="sxs-lookup"><span data-stu-id="069ba-110">This allows administrators to enforce a stronger security stance – one that requires valid identities for both machine and user during the same authentication transaction.</span></span>

<span data-ttu-id="069ba-111">HoloLens 2 には最新のワイヤレスおよび Wi-fi プロトコルが搭載されており、お客様を最大限にサポートします。</span><span class="sxs-lookup"><span data-stu-id="069ba-111">HoloLens 2 has modern wireless and Wi-Fi protocols that enable customers with maximum support.</span></span> <span data-ttu-id="069ba-112">HoloLens 2 のラジオは、Qualcomm WCN3990 ソリューションでプレミアム無線機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="069ba-112">The HoloLens 2 radio is a Qualcomm WCN3990 solution delivering a premium radio experience.</span></span> <span data-ttu-id="069ba-113">サポートされている Wi-fi は 802.11 ac/n です。</span><span class="sxs-lookup"><span data-stu-id="069ba-113">The Wi-Fi supported is 802.11 ac/n.</span></span> <span data-ttu-id="069ba-114">Wi-Fi: ユーザーは周波数の範囲を設定できません。こちらは使用する国によって異なります。</span><span class="sxs-lookup"><span data-stu-id="069ba-114">The frequency range is not user configurable and depends on the country of use.</span></span> <span data-ttu-id="069ba-115">米国では、Wi-fi は 2.4 GHz (1-11) のチャネルと 5GHz (36-64, 100-165) チャネルの両方を使用します。</span><span class="sxs-lookup"><span data-stu-id="069ba-115">In the United States, Wi-Fi uses both 2.4GHz (1-11) channels and 5GHz (36-64, 100-165) channels.</span></span> <span data-ttu-id="069ba-116">ユーザーとデバイスはいずれも、特定の周波数の許可/拒否リストを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="069ba-116">Neither user nor device can make allow/deny lists for specific frequencies.</span></span> <span data-ttu-id="069ba-117">Bluetooth SIC Core 5.0 には、Wi-fi と共有されない Bluetooth 専用の 2.4 GHz アンテナが付いています。</span><span class="sxs-lookup"><span data-stu-id="069ba-117">Bluetooth SIC Core 5.0 has a dedicated 2.4GHz antenna for Bluetooth which is not shared with Wi-Fi.</span></span> <span data-ttu-id="069ba-118">HoloLens 2 のソフトウェア スタックは、HID、HOGP、A2DP、GATT などのいくつかのプロトコルとプロファイルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="069ba-118">HoloLens 2’s software stack supports several protocols and profiles including HID, HOGP, A2DP, and GATT.</span></span> 

<span data-ttu-id="069ba-119">IT 管理者ができることは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="069ba-119">IT admins can:</span></span> 
  * <span data-ttu-id="069ba-120">[Bluetooth アクセス](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)を有効または制限する</span><span class="sxs-lookup"><span data-stu-id="069ba-120">Enable or restrict  [Bluetooth access](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)</span></span>
  * <span data-ttu-id="069ba-121">[Bluetooth のローカル デバイス名](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename)を設定する</span><span class="sxs-lookup"><span data-stu-id="069ba-121">Set [local Bluetooth device names](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename)</span></span>
  * <span data-ttu-id="069ba-122">[デバイスを検出できるように](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode)許可する</span><span class="sxs-lookup"><span data-stu-id="069ba-122">Allow [devices to be discoverable](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode)</span></span>
  * <span data-ttu-id="069ba-123">[Wi-Fi 接続](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi)を許可/禁止する</span><span class="sxs-lookup"><span data-stu-id="069ba-123">Allow/disallow [Wi-Fi connections](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi)</span></span> 
  * <span data-ttu-id="069ba-124">[MDM サーバーがインストールされたネットワーク外部の Wi-Fi への接続](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)を許可または禁止する</span><span class="sxs-lookup"><span data-stu-id="069ba-124">Allow or disallow [connecting to Wi-Fi outside of MDM server-installed networks](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)</span></span>
