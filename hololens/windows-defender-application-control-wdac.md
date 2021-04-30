---
title: Windows Defender アプリケーション制御-WDAC
description: Windows Defender アプリケーション制御の概要と、それを使用して HoloLens mixed reality デバイスを管理する方法について説明します。
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309404"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender アプリケーション制御-WDAC

WDAC を使用すると、IT 管理者は、デバイスでのアプリの起動をブロックするようにデバイスを構成できます。 これは、キオスクモードなどのデバイス制限の方法とは異なり、デバイス上のアプリを非表示にする UI がユーザーに表示されますが、それでも起動できます。 WDAC が実装されている場合でも、アプリはすべてのアプリの一覧に表示されますが、WDAC はデバイスユーザーがこれらのアプリとプロセスを起動できなくなります。

1つのデバイスに複数の WDAC ポリシーを割り当てることができます。 システムに複数の WDAC ポリシーが設定されている場合、最も制限の厳しいポリシーが有効になります。 

> [!NOTE]
> HoloLens でブロックされているアプリをエンドユーザーが起動しようとすると、そのアプリを起動できないことを知らせる通知を受信しません。

次に、 [WDAC および Windows PowerShell を使用して、Microsoft Intune で HoloLens 2 デバイス上のアプリを許可またはブロック](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)する方法について説明します。

最初の例の手順を使用して Windows 10 PC にインストールされているアプリをユーザーが検索する場合、結果を絞り込むためにいくつかの試行が必要になることがあります。

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

パッケージの完全な名前がわからない場合は、' Get-appxpackage-name \* YourBestGuess ' を何回か実行しなければならないことがあり \* ます。 名前を指定すると、' $package 1 = Get-AppxPackage-name PackageName ' という名前になります。

たとえば、Microsoft Edge に対して次のコードを実行すると複数の結果が返されますが、その一覧から、必要な完全な名前が MicrosoftEdge であることを確認できます。

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>HoloLens でのアプリのパッケージファミリ名

上記のガイドでは、手動で newPolicy.xml を編集し、HoloLens にのみインストールされているアプリケーションのパッケージファミリ名を使用してルールを追加することができます。 場合によっては、ポリシーに追加するデスクトップ PC 上にないアプリが使用されることがあります。

HoloLens 2 デバイス用の一般的に使用されるアプリと In-Box アプリの一覧を次に示します。

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
| エクスプローラー              | c5e2524a-ea46-4f67-84 1f-6a9465d9d515_cw5n1h2txyewy |
| Mail                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| 映画 & テレビ                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Photos                     | Microsoft.Windows.Photos_8wekyb3d8bbwe             |
| 設定                   | HolographicSystemSettings_cw5n1h2txyewy            |
| ヒント                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1-ブロックしているアプリのインストーラーは、アプリインストーラーアプリをブロックするだけで、Microsoft Store などの他のソースや MDM ソリューションからインストールされたアプリはブロックしません。

### <a name="how-to-find-a-package-family-name"></a>パッケージファミリ名を検索する方法

アプリがこの一覧にない場合、ユーザーは、ブロックされるアプリがインストールされている HoloLens 2 に接続されているデバイスポータルを使用して、PackageRelativeID を特定し、その中にパッケージ化 Efamilyname を取得することができます。

1. HoloLens 2 デバイスにアプリをインストールします。 
1. [設定] を開き、開発者向けのセキュリティ > & 更新を >、 **開発者モード** と **デバイスポータル** を有効にします。 
    1. 詳細について [は、こちらのデバイスポータルのセットアップと使用](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)に関するページを参照してください。
1. デバイスポータルが接続されたら、[ **ビュー** ]、[ **アプリ**] の順に移動します。 
1. [インストールされているアプリ] パネルで、ドロップダウンを使用して、インストールされているアプリを選択します。 
1. PackageRelativeID を見つけます。 
1. の前にアプリ文字をコピーします。これらの文字は、整理 Efamilyname になります。


