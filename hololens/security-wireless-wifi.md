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
# 無線と Wi-Fi

HoloLens 2 ワイヤレス LAN 接続は、次のような最新の Wi-fi セキュリティ標準をサポートしています。
  * WPA2 (Wi-fi 保護アクセス 2)  
  * TEAP (トンネル拡張認証プロトコル)  
  * OWE (適時的ワイヤレス暗号化)

TEAP (次世代のエンタープライズ ネットワーク認証) を使用すると、複数の資格情報を 1 つのトランザクションに安全に連結できます。  これにより管理者は、同じ認証トランザクション間で、コンピューターとユーザーの両方に有効なアイデンティティを要求することにより、セキュリティ態勢をより強化できます。

HoloLens 2 には最新のワイヤレスおよび Wi-fi プロトコルが搭載されており、お客様を最大限にサポートします。 HoloLens 2 のラジオは、Qualcomm WCN3990 ソリューションでプレミアム無線機能を提供します。 サポートされている Wi-fi は 802.11 ac/n です。 Wi-Fi: ユーザーは周波数の範囲を設定できません。こちらは使用する国によって異なります。 米国では、Wi-fi は 2.4 GHz (1-11) のチャネルと 5GHz (36-64, 100-165) チャネルの両方を使用します。 ユーザーとデバイスはいずれも、特定の周波数の許可/拒否リストを作成することはできません。 Bluetooth SIC Core 5.0 には、Wi-fi と共有されない Bluetooth 専用の 2.4 GHz アンテナが付いています。 HoloLens 2 のソフトウェア スタックは、HID、HOGP、A2DP、GATT などのいくつかのプロトコルとプロファイルをサポートしています。 

IT 管理者ができることは、次のとおりです。 
  * [Bluetooth アクセス](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)を有効または制限する
  * [Bluetooth のローカル デバイス名](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename)を設定する
  * [デバイスを検出できるように](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode)許可する
  * [Wi-Fi 接続](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi)を許可/禁止する 
  * [MDM サーバーがインストールされたネットワーク外部の Wi-Fi への接続](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)を許可または禁止する
