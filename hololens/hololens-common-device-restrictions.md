---
title: 一般的なデバイスの制限
description: Mixed Reality デバイスの一般的なデバイスの制限と設定をHoloLensに保つ。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2021
ms.reviewer: aboeger
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 12dd061565c88fed65d1152c224be9ebbc7185d4
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924301"
---
# <a name="common-device-restrictions"></a>一般的なデバイスの制限

このガイドは、IT プロフェッショナルが、企業内の WINDOWS 10 HOLOGRAPHIC OS で使用できる、より一般的に使用される管理オプションを理解するのに役立ちます。 これらのポリシーを MDM ベンダーで有効にする方法については、MDM システムのマニュアルをご覧ください。 このガイドで説明する設定がすべての MDM システムでサポートされるわけではありません。 一部の設定では、OMA-URI XML ファイルを通じてカスタム ポリシーがサポートされます。 「[Microsoft Intune によるカスタム ポリシーのサポート](/mem/intune/configuration/custom-settings-windows-10)」をご覧ください。 命名規則は、MDM ベンダーによって異なる場合があります。

## <a name="prevent-changing-of-settings"></a>設定変更の防止

通常、従業員は企業のデバイス上でロックダウンする必要のある個人のデバイスの特定の設定を変更することが許可されています。 従業員は、設定 UI を使用して、HoloLens設定を対話的に調整できます。 MDM を使用すると、ユーザーが変更できる設定を制限できます。
次に、設定の制限を構成するためにサポートWindows 10 Holographic MDM 設定の一覧を示します。

- [VPN を許可する:](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) ユーザーが VPN 設定を変更できます
- [手動 WiFi 構成を許可する:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) MDM でプロビジョニングされたネットワークWi-Fi外部でユーザーが接続を作成できるようにします
- [手動 MDM 登録解除を許可する](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) ユーザーが職場アカウントを削除できるかどうか (つまり、MDM システムからデバイスの登録を解除する)

[Holographic Windowsバージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2)で追加され、HoloLens 2されました。

- [プロビジョニング パッケージの追加を許可する:](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) ユーザーが新しいプロビジョニング パッケージを追加し、新しい値で上書きできる場合は切り替え。
- [プロビジョニング パッケージの削除を許可する:](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) ユーザーがプロビジョニング パッケージを削除して、以前にロックした設定を切り替える場合に切り替えます。

[Holographic バージョンWindows 21H2 で追加されました](hololens-release-notes.md#windows-holographic-version-21h2)。

- [RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)ポリシーを使用すると、組織用に構成されたプライベート ストアのみを表示するように Microsoft Store アプリを構成し、使用可能にしたアプリにのみアクセスを制限できます。

ポリシー オプションの詳細については、サポートされているポリシー HOLOLENSを[参照してください](/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="hardware-restrictions"></a>ハードウェアの制限

Windows 10 Holographicデバイスは、カメラ、マイク、スピーカー、USB インターフェイス、Bluetooth インターフェイス、Wi-Fi などの一般的なハードウェア機能を含む最先端のテクノロジを使用します。 ハードウェアの制限を使って、これらの機能の利用を制御できます。
ハードウェアの制限を構成するためにサポートされる一般的Windows 10 Holographic MDM 設定の一覧を次に示します。

> [!NOTE]
> これらのハードウェアの制限の一部は、接続に影響を与え、データ保護を支援します。

- [Wi-Fi を許可する:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) ユーザーが自分のデバイスで WiFi ラジオを有効にして使用できるかどうか。
- [USB 接続を許可する:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) USB 接続が有効になっているかどうか (USB 充電には影響しません)。
- [許可Bluetooth:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)ユーザーがデバイス上でオプションを有効Bluetooth使用できるかどうか。
- [カメラの制限:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera)アプリがWindowsにアクセスできるかどうかを指定します。
- [マイクを制限する:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone)アプリがマイクWindowsできるかどうかを指定します。

[Holographic Windowsバージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2)で追加され、HoloLens 2されました。

- [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) ディスプレイがオフになるまでの時間を設定し、ディスプレイをオフにすることで、デバイスをロックします。
- [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) ディスプレイがオフになるまでの時間を設定し、ディスプレイをオフにすることで、デバイスをロックします。
