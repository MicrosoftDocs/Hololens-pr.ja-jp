---
title: Windows Defender アプリケーション制御 - WDAC
description: アプリケーション制御のWindows Defender概要と、それを使用して複合現実デバイスのHoloLensする方法について説明します。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: ab05f1bbe1570d4966932d6f8ac857e5bd2d8a7d3a8f5b93aaba0335eda05b01
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665558"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender アプリケーション制御 - WDAC

WDAC を使用すると、IT 管理者はデバイスでのアプリの起動をブロックするデバイスを構成できます。 これは、キオスク モードなどのデバイス制限の方法とは異なります。この場合、ユーザーにはデバイス上のアプリを非表示にする UI が表示されますが、引き続き起動できます。 WDAC が実装されている間、アプリは [すべてのアプリ] の一覧に引き続き表示されますが、WDAC では、これらのアプリとプロセスがデバイス ユーザーによって起動されるのを停止します。

1 つのデバイスに複数の WDAC ポリシーを割り当てることができます。 システムに複数の WDAC ポリシーが設定されている場合、最も制限の厳しいポリシーが有効になります。 

> [!NOTE]
> エンド ユーザーが WDAC によってブロックされているアプリを起動しようとすると、HoloLens で、そのアプリを起動できないという通知は受信されません。

次に示すのは[、WDAC](/mem/intune/configuration/custom-profile-hololens)と Windows PowerShell を使用して、 がインストールされている HoloLens 2 デバイスでアプリを許可またはブロックする方法を学習Microsoft Intune。

ユーザーが最初の例の手順を使用して Windows 10 PC にインストールされているアプリを検索する場合は、結果を絞り込む必要がある場合があります。

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

パッケージの完全な名前が分からない場合は、'Get-AppxPackage -name YourBestGuess' を数回実行して検索する必要 \* \* があります。 その後、名前を設定したら、'$package 1 = Get-AppxPackage -name Actual.PackageName' を実行します。

たとえば、Microsoft Edge に対して次を実行すると、複数の結果が返されますが、その一覧から、必要な完全な名前が Microsoft.MicrosoftEdge である可能性があります。

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>アプリのパッケージ ファミリ名は、HoloLens

上記のリンク先のガイドでは、手動で newPolicy.xml を編集し、パッケージ ファミリ名を使用して HoloLens にのみインストールされるアプリケーションのルールを追加できます。 場合によっては、ポリシーに追加するデスクトップ PC 上にはないアプリを使用できます。

次に示すのは、デバイスで一般的に使用In-Boxアプリの一覧HoloLens 2です。

| アプリ名                   | パッケージ ファミリ名                                |
|----------------------------|----------------------------------------------------|
| 3D ビューアー                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| アプリ インストーラー              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup>         |
| Calendar                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| カメラ                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 Guides        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| フィードバック Hub               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| エクスプローラー              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| メール                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| 映画 & テレビ                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| 写真                     | マイクロソフト。Windows。Photos_8wekyb3d8bbwe             |
| 設定                   | HolographicSystemSettings_cw5n1h2txyewy            |
| ヒント                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1 - アプリ インストーラーブロックすると、アプリ インストーラー アプリだけがブロックされ、Microsoft Store や MDM ソリューションなどの他のソースからインストールされたアプリはブロックされません。

### <a name="how-to-find-a-package-family-name"></a>パッケージ ファミリ名を検索する方法

アプリがこの一覧に含されていない場合、ユーザーはブロックするアプリをインストールした HoloLens 2 に接続されている デバイス ポータル を使用して PackageRelativeID を特定し、そこから PackageFamilyName を取得できます。

1. アプリをデバイスにHoloLens 2します。 
1. [設定 -> Updates & Security -> 開発者向け] を開き、[開発者モード] を有効にしてから、[デバイス ポータル]**を有効にします**。 
    1. 詳細については、デバイス ポータルのセットアップと使用に [関するページを参照してください](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。
1. 接続デバイス ポータル、[ビュー] 、 [アプリ] の **順に****移動します**。 
1. [インストール済みアプリ] パネルで、ドロップダウンを使用してインストールされているアプリを選択します。 
1. PackageRelativeID を見つける。 
1. !の前にアプリの文字をコピーします。これらの文字は PackageFamilyName になります。


