---
title: Windows Defender アプリケーション制御 - WDAC
description: WDAC の概要と、HoloLens デバイスを管理するための使い方について説明します。
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
ms.openlocfilehash: b12079142049cce28ec00803ad0a1f8dc92333e1
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163123"
---
# Windows Defender アプリケーション制御 - WDAC

WDAC は、IT 管理者がデバイス上のアプリの起動をブロックするようにデバイスを構成することを可能にします。 これは、キオスクモードなどのデバイス制限のメソッドとは異なり、デバイス上のアプリを非表示にする UI がユーザーに表示されますが、起動することはできます。 WDAC が実装されている間も、アプリは [すべてのアプリ] の一覧に表示されますが、WDAC では、デバイスユーザーがアプリとプロセスを起動することができなくなります。

デバイスに複数の WDAC ポリシーを割り当てることができます。 システムに複数の WDAC ポリシーが設定されている場合、最も制限の厳しいポリシーが有効になります。 

> [!NOTE]
> HoloLens でブロックされているアプリをエンドユーザーが起動しようとすると、そのアプリを起動できないという通知が表示されません。

次に示すのは、 [WDAC と Windows PowerShell を使用して、Microsoft Intune との HoloLens 2 デバイスでアプリを許可またはブロックする](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)方法についてのガイドです。

ユーザーが最初の例の手順を使用して、Windows 10 PC にインストールされたアプリを検索するときに、結果を絞り込むためにいくつかの操作を行う必要がある場合があります。

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

パッケージの完全な名前がわからない場合は、' Add-appxpackage-name \ * YourBestGuess \ * ' を数回実行して、検索する必要があります。 名前を指定したら、' $package 1 = Get-AppxPackage PackageName '

たとえば、Edge で次のように実行すると、複数の結果が返されますが、その一覧から必要な氏名が MicrosoftEdge であることを確認できます。 

```powershell
Get-AppxPackage -name *edge*
``` 

## HoloLens 上のアプリのパッケージファミリ名

上記のガイドでは、newPolicy.xml を手動で編集し、HoloLens にインストールされているパッケージファミリ名を持つアプリケーションのルールを追加できます。 場合によっては、ポリシーに追加する必要があるデスクトップ PC 以外のアプリを使うことがあります。 

以下は、HoloLens 2 デバイス用の一般的に使用されるアプリと In-Box アプリの一覧です。

| アプリ名                   | パッケージファミリ名                                |
|----------------------------|----------------------------------------------------|
| 3D ビューアー                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| アプリ インストーラー              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</sup>         |
| カレンダー                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| カメラ                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 Guides        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| フィードバック Hub               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| エクスプローラー              | c5e2524a-ea46-4f67-84 1f-6a9465d9d515_cw5n1h2txyewy |
| メール                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| 映画 & テレビ                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| フォト                     | Microsoft.Windows.Photos_8wekyb3d8bbwe             |
| 設定                   | HolographicSystemSettings_cw5n1h2txyewy            |
| ヒント                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1-アプリのインストーラーアプリがブロックされるのは、Microsoft Store や MDM ソリューションなどの他のソースからインストールされたアプリではなく、アプリのインストーラーアプリのみです。

### パッケージファミリ名を検索する方法

アプリがこの一覧に表示されていない場合は、デバイスポータルを使用して、ブロックする必要があるアプリをインストールしている HoloLens 2 に接続して、PackageRelativeID を判断し、その名前から「パッケージ Efamilyname」を取得することができます。

1. HoloLens 2 デバイスにアプリをインストールします。 
1. 開発者向け > & > 更新プログラムを開き、 **開発者モード** と **Device portal**を有効にします。 
    1. 詳細について [は、「device portal のセットアップと使用の](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)詳細」を参照してください。
1. Device Portal が接続されたら、[ **ビュー** ]、[ **アプリ**] の順に移動します。 
1. [インストールされているアプリ] パネルで、ドロップダウンを使ってインストールされているアプリを選びます。 
1. PackageRelativeID を見つけます。 
1. の前にアプリの文字をコピーします。これは、パッケージの名前になります。


