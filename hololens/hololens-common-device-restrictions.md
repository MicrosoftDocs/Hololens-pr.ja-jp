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
ms.openlocfilehash: e9c44466da375611f8864eae1b6e6ceea3ef9b09
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309085"
---
# <a name="common-device-restrictions"></a>一般的なデバイスの制限 

このガイドは、企業内の Windows 10 Holographic OS で使用できる一般的に使用される管理オプションを IT プロフェッショナルが理解するのに役立ちます。 これらのポリシーを MDM ベンダーで有効にする方法については、MDM システムのマニュアルをご覧ください。 このガイドで説明する設定がすべての MDM システムでサポートされるわけではありません。 一部の設定では、OMA-URI XML ファイルを通じてカスタム ポリシーがサポートされます。 「[Microsoft Intune によるカスタム ポリシーのサポート](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)」をご覧ください。 命名規則は、MDM ベンダーによって異なる場合があります。

## <a name="prevent-changing-of-settings"></a>設定変更の防止
通常、従業員は企業のデバイス上でロックダウンする必要のある個人のデバイスの特定の設定を変更することが許可されています。 従業員は、設定 UI を使用して、HoloLens の特定の設定を対話形式で調整できます。 MDM を使用すると、ユーザーが変更できる設定を制限できます。 次の一覧は、Windows 10 Holographic が設定の制限を構成するためにサポートする、一般的に使用される MDM 設定を示しています。
-   [VPN を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) ユーザーが VPN の設定を変更することを許可します
-   [WiFi の手動構成を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) ユーザーが MDM でプロビジョニングされたネットワークの外部で Wi-Fi 接続を確立できるようにします
-   [手動による MDM の登録解除を許可する](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) ユーザーが職場アカウントを削除することを許可されているかどうか (つまり、MDM システムからデバイスの登録を解除する)

[Windows Holographic、バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2) for HoloLens 2 デバイスに追加されました。
- [プロビジョニングパッケージの追加を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) ユーザーが新しいプロビジョニングパッケージを追加できる場合は、新しい値で上書きするかどうかを切り替えます。
- [プロビジョニングパッケージの削除を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) ユーザーがプロビジョニングパッケージを削除して、以前にロックされていた設定を切り替えることができる場合に切り替えます。

ポリシーオプションの詳細については、「HoloLens がサポートする[ポリシー csp](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2) 」を参照してください。

## <a name="hardware-restrictions"></a>ハードウェアの制限
Windows 10 Holographic デバイスは、カメラ、マイク、スピーカー、USB インターフェイス、Bluetooth インターフェイス、Wi-fi などの一般的なハードウェア機能を含む最先端のテクノロジを使用します。 ハードウェアの制限を使って、これらの機能の利用を制御できます。
次の一覧は、Windows 10 Holographic がハードウェアの制限を構成するためにサポートする、一般的に使用される MDM 設定を示しています。

> [!NOTE]
> これらのハードウェアの制限の一部は、接続性に影響し、データ保護に役立ちます。

-   [Wi-fi を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) ユーザーが自分のデバイスで WiFi ラジオを有効にして使用できるかどうか。
-   [USB 接続を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) USB 接続が有効になっているかどうかを示します (USB 充電には影響しません)。
-   [Bluetooth を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) ユーザーがデバイスで Bluetooth ラジオを有効にして使用できるかどうか。
-   [カメラを制限する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Windows アプリがカメラにアクセスできるかどうかを指定します。
-   [マイクを制限する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Windows アプリがマイクにアクセスできるかどうかを指定します。

[Windows Holographic、バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2) for HoloLens 2 デバイスに追加されました。 
- [Displayofftimeoutonbattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) ディスプレイがオフになるまでの時間を設定し、ディスプレイをオフにすることでデバイスをロックします。 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) ディスプレイがオフになるまでの時間を設定し、ディスプレイをオフにすることでデバイスをロックします。 
