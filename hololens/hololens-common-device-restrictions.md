---
title: 一般的なデバイスの制限
description: HoloLens mixed reality デバイスの一般的なデバイスの制限と設定を使用して、最新の状態に保ちます。
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
ms.openlocfilehash: 769cacc1803af9d9e9bf1079f8cd5671f194c3bc
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639218"
---
# <a name="common-device-restrictions"></a>一般的なデバイスの制限 

このガイドは、企業内の Windows 10 Holographic OS で使用できる、より一般的に使用される管理オプションを IT プロフェッショナルが理解するのに役立ちます。 これらのポリシーを MDM ベンダーで有効にする方法については、MDM システムのマニュアルをご覧ください。 このガイドで説明する設定がすべての MDM システムでサポートされるわけではありません。 一部の設定では、OMA-URI XML ファイルを通じてカスタム ポリシーがサポートされます。 「[Microsoft Intune によるカスタム ポリシーのサポート](/mem/intune/configuration/custom-settings-windows-10)」をご覧ください。 命名規則は、MDM ベンダーによって異なる場合があります。

## <a name="prevent-changing-of-settings"></a>設定変更の防止
通常、従業員は企業のデバイス上でロックダウンする必要のある個人のデバイスの特定の設定を変更することが許可されています。 従業員は、設定 UI を使用して、HoloLens の特定の設定を対話形式で調整できます。 MDM を使用すると、ユーザーが変更できる設定を制限できます。 次の一覧では、設定の制限を構成するために Windows 10 Holographic でサポートされている一般的に使用される MDM 設定を示します。
-   [VPN を許可する:](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) ユーザーが VPN の設定を変更することを許可します
-   [WiFi の手動構成を許可する:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) ユーザーが MDM でプロビジョニングされたネットワークの外部で Wi-Fi 接続を確立できるようにします
-   [手動による MDM の登録解除を許可する](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) ユーザーが職場アカウントを削除することを許可されているかどうか (つまり、MDM システムからデバイスの登録を解除する)

[Windows Holographic、バージョン 20h2](hololens-release-notes.md#windows-holographic-version-20h2)で HoloLens 2 デバイス用に追加されました。
- [プロビジョニングパッケージの追加を許可する:](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) ユーザーが新しいプロビジョニングパッケージを追加できる場合は、新しい値で上書きするかどうかを切り替えます。
- [プロビジョニングパッケージの削除を許可する:](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) ユーザーがプロビジョニングパッケージを削除して、以前にロックされていた設定を切り替えることができる場合に切り替えます。

ポリシーオプションの詳細については HoloLens 「サポートされている[ポリシー csp](/windows/client-management/mdm/policy-csps-supported-by-hololens2) 」を参照してください。

## <a name="hardware-restrictions"></a>ハードウェアの制限
Windows 10 Holographic デバイスは、カメラ、マイク、スピーカー、USB インターフェイス、Bluetooth インターフェイス、wi-fi などの一般的なハードウェア機能を含む最先端のテクノロジを使用します。 ハードウェアの制限を使って、これらの機能の利用を制御できます。
次の一覧は、ハードウェアの制限を構成するために Windows 10 Holographic がサポートしている一般的に使用される MDM 設定を示しています。

> [!NOTE]
> これらのハードウェアの制限の一部は、接続性に影響し、データ保護に役立ちます。

-   [Wi-fi を許可する:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) ユーザーが自分のデバイスで WiFi ラジオを有効にして使用できるかどうか。
-   [USB 接続を許可する:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) USB 接続が有効になっているかどうかを示します (USB 充電には影響しません)。
-   [Bluetooth を許可する:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)ユーザーがデバイスで Bluetooth ラジオを有効にして使用できるかどうか。
-   [カメラを制限する:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera)Windows アプリがカメラにアクセスできるかどうかを指定します。
-   [マイクを制限する:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone)Windows アプリがマイクにアクセスできるかどうかを指定します。

HoloLens 2 デバイスの[Windows Holographic、バージョン 20h2](hololens-release-notes.md#windows-holographic-version-20h2)で追加されました。 
- [Displayofftimeoutonbattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) ディスプレイがオフになるまでの時間を設定し、ディスプレイをオフにすることでデバイスをロックします。 
- [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) ディスプレイがオフになるまでの時間を設定し、ディスプレイをオフにすることでデバイスをロックします。 
