---
title: Windows Defender アプリケーション制御 - WDAC
description: アプリケーション コントロールWindows Defender概要と、それを使って HoloLens Mixed Reality デバイスを管理する方法について説明します。
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
ms.openlocfilehash: 23c9a274387424e8f084a4729ee621e130820716
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284138"
---
# Windows Defender アプリケーション制御 - WDAC

WDAC を使うと、IT 管理者はデバイス上のアプリの起動をブロックするデバイスを構成できます。 これは、キオスク モードなどのデバイス制限の方法とは異なります。キオスク モードでは、ユーザーにデバイス上のアプリを非表示にする UI が表示されますが、起動は可能です。 WDAC が実装されている間、アプリは [すべてのアプリ] の一覧に表示されますが、WDAC はそれらのアプリとプロセスをデバイス ユーザーが起動できないのを停止します。

1 つのデバイスに複数の WDAC ポリシーを割り当てることができます。 システムに複数の WDAC ポリシーが設定されている場合、最も制限の厳しいポリシーが有効になります。 

> [!NOTE]
> エンド ユーザーが WDAC によってブロックされているアプリを起動しようとすると、HoloLens では、そのアプリを起動できないという通知は表示されません。

Microsoft Intune で [HoloLens 2](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)デバイス上のアプリを許可またはブロックするために WDAC と Windows PowerShell を使用する方法について説明するガイドを次に示します。

ユーザーが最初の例の手順を使って Windows 10 PC にインストールされているアプリを検索する場合、結果を絞り込むには、いくつかの試行が必要な場合があります。

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

パッケージの完全な名前が分からない場合は、'Get-AppxPackage -name \*YourBestGuess\*' を数回実行して検索する必要があります。 名前を実行すると、'$package 1 = Get-AppxPackage -name Actual.PackageName' が実行されます。

たとえば、Microsoft Edge で次のコマンドを実行すると、複数の結果が返されますが、その一覧から、必要な完全な名前が Microsoft.MicrosoftEdge である必要があります。

```powershell
Get-AppxPackage -name *edge*
``` 

## HoloLens 上のアプリのパッケージ ファミリ名

上記のガイドでは、HoloLens にのみインストールされているアプリケーションのnewPolicy.xmlを手動で編集し、パッケージ ファミリ名で規則を追加できます。 場合によっては、ポリシーに追加するデスクトップ PC にはないアプリを使う場合があります。

HoloLens 2 デバイス用の一般的In-Boxアプリの一覧を次に示します。

| アプリ名                   | パッケージ ファミリ名                                |
|----------------------------|----------------------------------------------------|
| 3D ビューアー                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| アプリ インストーラー              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</sup>         |
| カレンダー                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
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
| フォト                     | Microsoft.Windows.Photos_8wekyb3d8bbwe             |
| 設定                   | HolographicSystemSettings_cw5n1h2txyewy            |
| ヒント                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1 - アプリ インストーラーをブロックすると、アプリ インストーラー アプリだけがブロックされ、Microsoft Store などの他のソースや MDM ソリューションからインストールされたアプリはブロックされません。

### パッケージ ファミリ名を見つける方法

アプリがこの一覧に表示されていない場合、ユーザーは Device Portal を使って、アプリをインストールした HoloLens 2 に接続し、ブロックする必要がある場合に PackageRelativeID を特定し、そこから PackageFamilyName を取得できます。

1. HoloLens 2 デバイスにアプリをインストールします。 
1. Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**. 
    1. 詳しくは、デバイス ポータルのセットアップと使用 [に関する詳細をご覧ください](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。
1. Device Portal に接続したら、[ビュー] の [ **アプリ]** に **移動します**。 
1. [インストールされたアプリ] パネルで、ドロップダウンを使用してインストール済みアプリを選択します。 
1. PackageRelativeID を探します。 
1. !の前にアプリの文字をコピーします。これらの文字は PackageFamilyName になります。


