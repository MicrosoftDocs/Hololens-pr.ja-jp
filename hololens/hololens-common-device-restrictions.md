---
title: 一般的なデバイスの制限
description: デバイス restrctions は、HoloLens で一般的に設定されています。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 744d54a344867c5c38681781580f5357e0a0da70
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162963"
---
# 一般的なデバイスの制限 

このガイドは、IT 担当者が企業の Windows 10 ホログラフィック OS で使用できる、より一般的に使用される管理オプションについて理解するのに役立ちます。 これらのポリシーを MDM ベンダーで有効にする方法については、MDM システムのマニュアルをご覧ください。 このガイドで説明する設定がすべての MDM システムでサポートされるわけではありません。 一部の設定では、OMA-URI XML ファイルを通じてカスタム ポリシーがサポートされます。 「[Microsoft Intune によるカスタム ポリシーのサポート](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)」をご覧ください。 命名規則は、MDM ベンダーによって異なる場合があります。

## 設定変更の防止
通常、従業員は企業のデバイス上でロックダウンする必要のある個人のデバイスの特定の設定を変更することが許可されています。 従業員は、設定 UI を通じて、HoloLens の特定の設定を対話的に調整できます。 MDM を使用すると、ユーザーが変更できる設定を制限できます。 次の一覧は、Windows 10 ホログラフィックで設定の制限を構成するためにサポートされている MDM 設定の一般的な例を示しています。
-   [VPN を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) ユーザーが VPN 設定を変更できるようにします
-   [WiFi の手動構成を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) ユーザーが MDM プロビジョニングされたネットワークの外部で接続 Wi-Fi できるようにします
-   [MDM Unenrollment を手動で許可する](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) ユーザーがワークプレースアカウントの削除を許可されているかどうか (例: MDM システムからデバイスを登録解除する)

[Windows ホログラフィック、バージョン 20H2 (](hololens-release-notes.md#windows-holographic-version-20h2) HoloLens 2 デバイス用) に追加されました。
- [プロビジョニングパッケージの追加を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) ユーザーが新しいプロビジョニングパッケージを追加できるかどうかを切り替えます。新しい値で上書きします。
- [プロビジョニングパッケージの削除を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) ユーザーがプロビジョニングパッケージを削除できるかどうかを切り替えます。これにより、ロックされた設定を切り替えることができます。

HoloLens でサポートされている[ポリシーの csp](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)でポリシーオプションの詳細を確認する

## ハードウェアの制限
Windows 10 ホログラフィックデバイスでは、カメラ、マイク、スピーカー、USB インターフェイス、Bluetooth インターフェイス、Wi-fi などの一般的なハードウェア機能を含む、最先端の技術を使用しています。 ハードウェアの制限を使って、これらの機能の利用を制御できます。
次の表は、Windows 10 ホログラフィックでハードウェアの制限を構成するためにサポートされる MDM 設定の一般的な例を示しています。

> [!NOTE]
> これらのハードウェア制限の一部は、接続性が影響を受け、データ保護を支援します。

-   [Wi-fi を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) ユーザーがデバイスで WiFi 無線を有効にして使用できるかどうか。
-   [USB 接続を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) USB 接続が有効になっているかどうか (USB 充電には影響ありません)
-   [Bluetooth を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) ユーザーがデバイスで Bluetooth 無線を有効にして使用できるかどうか
-   [カメラの制限:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Windows アプリがカメラにアクセスできるかどうかを指定します。
-   [マイクの制限:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Windows アプリがマイクにアクセスできるかどうかを指定します。

[Windows ホログラフィック、Verison 20H2 (](hololens-release-notes.md#windows-holographic-version-20h2) HoloLens 2 デバイス用) に追加されました。 
- [Displayofftimeoutonbattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) ディスプレイがオフになるまでの時間を設定します。表示をオフにすると、デバイスがロックされます。 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) ディスプレイがオフになるまでの時間を設定します。表示をオフにすると、デバイスがロックされます。 
