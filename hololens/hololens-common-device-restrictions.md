---
title: 一般的なデバイスの制限
description: HoloLens Mixed Reality デバイスの一般的なデバイスの制限と設定を常に最新の状態に保つ。
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283358"
---
# 一般的なデバイスの制限 

このガイドは、企業で Windows 10 Holographic OS で使用できる、より一般的に使用される管理オプションを IT 担当者が理解するのに役立ちます。 これらのポリシーを MDM ベンダーで有効にする方法については、MDM システムのマニュアルをご覧ください。 このガイドで説明する設定がすべての MDM システムでサポートされるわけではありません。 一部の設定では、OMA-URI XML ファイルを通じてカスタム ポリシーがサポートされます。 「[Microsoft Intune によるカスタム ポリシーのサポート](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)」をご覧ください。 命名規則は、MDM ベンダーによって異なる場合があります。

## 設定変更の防止
通常、従業員は企業のデバイス上でロックダウンする必要のある個人のデバイスの特定の設定を変更することが許可されています。 従業員は、設定 UI を使って HoloLens の特定の設定を対話的に調整できます。 MDM を使用すると、ユーザーが変更できる設定を制限できます。 Windows 10 Holographic が設定の制限を構成するためにサポートする一般的に使用される MDM 設定の一覧を次に示します。
-   [VPN を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) ユーザーが VPN 設定を変更できます。
-   [手動 WiFi 構成を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) MDM でプロビジョニングされたネットワークWi-Fi外部でユーザーが接続を許可する
-   [手動 MDM 登録解除を許可する](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) ユーザーが職場アカウントを削除できるかどうか (MDM システムからデバイスを登録解除するかどうか)

[Windows Holographic Version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) for HoloLens 2 デバイスで追加されました。
- [プロビジョニング パッケージの追加を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) ユーザーが新しいプロビジョニング パッケージを追加して、新しい値を上書きできる場合に切り替える。
- [プロビジョニング パッケージの削除を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) ユーザーがプロビジョニング パッケージを削除できる場合に切り替え、以前にロックした設定を切り替え可能にします。

HoloLens でサポートされているポリシー CSP のポリシー オプションについて[詳しくは、以下をご覧ください](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)。

## ハードウェアの制限
Windows 10 Holographic デバイスは、カメラ、マイク、スピーカー、USB インターフェイス、Bluetooth インターフェイス、Wi-Fi などの一般的なハードウェア機能を含む最新のテクノロジを使用します。 ハードウェアの制限を使って、これらの機能の利用を制御できます。
ハードウェアの制限を構成するために Windows 10 Holographic がサポートする一般的に使用される MDM 設定の一覧を次に示します。

> [!NOTE]
> これらのハードウェアの制限の一部は、接続に影響を与え、データ保護を支援します。

-   [Wi-Fi を許可する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) ユーザーがデバイスで WiFi 無線を有効にして使用できるかどうか。
-   [USB 接続を許可します。](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) USB 接続を有効にするかどうかを指定します (USB 充電には影響しません)。
-   [許可Bluetooth:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) ユーザーがデバイスでデバイスのBluetoothを有効にして使用できるかどうか。
-   [カメラを制限する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Windows アプリがカメラにアクセスできるかどうかを指定します。
-   [マイクを制限する:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Windows アプリがマイクにアクセスできるかどうかを指定します。

[Windows Holographic、Verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) for HoloLens 2 デバイスに追加されました。 
- [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) ディスプレイがオフになるまでの時間を設定し、ディスプレイをオフにすることでデバイスをロックします。 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) ディスプレイがオフになるまでの時間を設定し、ディスプレイをオフにすることでデバイスをロックします。 
