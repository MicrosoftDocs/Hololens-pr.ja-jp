---
title: Windows Defender アプリケーション制御 (WDAC)
description: アプリケーション制御のWindows Defender概要と、それを使用して複合現実デバイスのHoloLens方法について説明します。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/21/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: efdc57b5e045c1669587ffc46dbe2132b6de6600
ms.sourcegitcommit: 52ed453cace3851fbec0cfcc228fa2a79f1a2fec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2021
ms.locfileid: "128075387"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender アプリケーション制御 - WDAC

## <a name="overview"></a>概要

WDAC を使用すると、アプリHoloLensをブロックするアプリを構成できます。 これはキオスク モードとは異なります。このモードでは、UI によってアプリが非表示になりますが、引き続き起動できます。 WDAC を使用すると、アプリを表示できますが、起動できない。

> [!NOTE]
> エンド ユーザーが HoloLens で WDAC によってブロックされているアプリを起動しようとすると、アプリを起動できないという通知は表示されません。

1 つのデバイスに複数の WDAC ポリシーを割り当てることができます。 システムに複数の WDAC ポリシーが設定されている場合、最も制限の厳しいポリシーが有効になります。

次に示すのは、WDAC と Windows PowerShell を使用して、 がインストールされているデバイスでアプリを許可またはブロックする方法HoloLens 2[ガイドMicrosoft Intune。](/mem/intune/configuration/custom-profile-hololens)

ユーザーが最初の例の手順を使用して Windows 10 PC にインストールされているアプリを検索する場合は、結果を絞り込む必要がある場合があります。

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
```

パッケージの完全な名前が分からない場合は、'Get-AppxPackage -name YourBestGuess' を数回実行して検索する必要 \* \* があります。 その後、名前を設定したら、'$package 1 = Get-AppxPackage -name Actual.PackageName' を実行します。

たとえば、Microsoft Edge に対して次のコードを実行すると、複数の結果が返されますが、その一覧から、必要な完全な名前が Microsoft.MicrosoftEdge である可能性があります。

```powershell
Get-AppxPackage -name *edge*
```

## <a name="package-family-names-for-apps-on-hololens"></a>アプリのパッケージ ファミリ名 HoloLens

上でリンクしたガイドでは、手動で newPolicy.xml を編集し、パッケージ ファミリ名を使用して HoloLens にのみインストールされるアプリケーションのルールを追加できます。 場合によっては、ポリシーに追加するデスクトップ PC 上にはないアプリを使用できます。

次に示すのは、一般的に使用されるアプリと、In-Boxデバイス用のHoloLens 2一覧です。

| アプリ名                   | パッケージ ファミリ名                                |
|----------------------------|----------------------------------------------------|
| 3D ビューアー                  | `Microsoft.Microsoft3DViewer_8wekyb3d8bbwe`          |
| アプリ インストーラー              | `Microsoft.DesktopAppInstaller_8wekyb3d8bbwe` <sup>1</sup>         |
| 予定表                   | `microsoft.windowscommunicationsapps_8wekyb3d8bbwe`  |
| カメラ                     | `HoloCamera_cw5n1h2txyewy`                          |
| Cortana                    | `Microsoft.549981C3F5F10_8wekyb3d8bbwe`              |
| Dynamics 365 Guides        | `Microsoft.Dynamics365.Guides_8wekyb3d8bbwe`         |
| Dynamics 365 Remote Assist | `Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe`      |
| フィードバック Hub               | `Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe`         |
| エクスプローラー              | `c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy` |
| メール                       | `microsoft.windowscommunicationsapps_8wekyb3d8bbwe`  |
| Microsoft Store            | `Microsoft.WindowsStore_8wekyb3d8bbwe`               |
| 映画 & テレビ                | `Microsoft.ZuneVideo_8wekyb3d8bbwe`                  |
| OneDrive                   | `microsoft.microsoftskydrive_8wekyb3d8bbwe`          |
| 写真                     | `Microsoft.Windows.Photos_8wekyb3d8bbwe`             |
| Settings                   | `HolographicSystemSettings_cw5n1h2txyewy`            |
| ヒント                       | `Microsoft.HoloLensTips_8wekyb3d8bbwe`               |

- 1 - アプリ インストーラーブロックすると、アプリ インストーラー アプリだけがブロックされ、Microsoft Store や MDM ソリューションなどの他のソースからインストールされたアプリはブロックされません。

### <a name="using-wdac-to-block-new-microsoft-edge"></a>WDAC を使用して新しい Microsoft Edge をブロック

新しい Microsoft Edge アプリをブロックするために[WDAC](windows-defender-application-control-wdac.md)ポリシーを更新[する](hololens-new-edge.md)IT 管理者の場合は、ポリシーに次を追加する必要があります。

```xml
<Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" />
```

### <a name="how-to-find-a-package-family-name"></a>パッケージ ファミリ名を検索する方法

アプリがこの一覧に含されていない場合、ユーザーはブロックするアプリをインストールした HoloLens 2 に接続されている デバイス ポータル を使用して PackageRelativeID を特定し、そこから PackageFamilyName を取得できます。

1. アプリをデバイスにHoloLens 2します。

1. [設定 -> Updates & Security -> 開発者向け] を開き、開発者モードを有効にしてから、**デバイス ポータル を有効にします**。

   詳細と手順については、デバイス ポータルの設定と使用に関する [ページを参照してください](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。

1. 接続デバイス ポータル、[ビュー] 、 [アプリ] の **順に****移動します**。

1. [インストール済みアプリ] パネルで、ドロップダウンを使用してインストールされているアプリを選択します。

1. PackageRelativeID を見つける。

1. の前にアプリ `!` 文字をコピーします。これらの文字は PackageFamilyName になります。
