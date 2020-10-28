---
title: HoloLens 2 アプリインストーラーを使用してアプリをサイドロードおよびインストールする方法
description: UI を使用したスライドの読み込みとアプリのインストール
keywords: アプリ管理、アプリ、hololens、アプリインストーラー
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 10/26/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 4e2256f1086c92cdf0e788ba9dddf5b74a733116
ms.sourcegitcommit: 72ae5a270f869393872eac160e43076eaa35fe4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135528"
---
# アプリインストーラーを使用して HoloLens 2 にアプリをインストールする

Windows Insider のリリースでは、新しい機能 (アプリのインストーラー) を追加して、HoloLens 2 デバイスに **よりシームレスにアプリケーションをインストールできるように** しています。  開発者モードを有効にしたり、Device Portal を使用したりしなくても、アプリをインストールできるようになりました。  Appx バンドルをデバイスにダウンロード (USB 経由またはエッジ経由) するだけで、インストールを開始するように促すメッセージが表示されるように、ファイルエクスプローラーで Appx バンドルに移動できます。  または、 [web ページからインストールを開始](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)します。  Microsoft Store またはサイドローディングで MDM の LOB アプリの展開機能を使用してインストールしたアプリと同様に、アプリを展開するには、アプリを展開する前に、アプリをインストールする前に、 [サインインツール](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) を使ってデジタル署名する必要があります。また、署名に使用する証明書は、HoloLens デバイスで [信頼される必要があり](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) ます   

この更新プログラム[は、既定でサイドローディングが有効になっ](https://blogs.windows.com/windows-insider/2019/08/07/announcing-windows-10-insider-preview-build-18956/)ているデスクトップと連携します

> [!IMPORTANT]
> この機能は、現時点では、Windows Insider ビルド 19041.1377 + でのみ avalible になっています。 [詳細については、「Windows Insider ビルドに登録する」を参照して](hololens-insider.md)ください。

> [!NOTE]
> この機能を無効にする IT 管理者は、次のパッケージファミリ名を、 [WDAC ポリシー](windows-defender-application-control-wdac.md)の一部として使用してください。 これにより、アプリのインストーラーアプリがブロックされるだけで、Microsoft ストアや MDM ソリューションなどの他のソースからアプリをインストールすることはできません。
```
Microsoft.DesktopAppInstaller_8wekyb3d8bbwe
```
> [!NOTE]
> アプリの制御には、 [WDAC ポリシー](windows-defender-application-control-wdac.md) を使用することをお勧めします。ただし、microsoft store アプリを許可するのは、 [Applicationmanagement/allowalltrustedapps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) ポリシーを明示的に設定したデバイスのみが、microsoft store からアプリをインストールすることを許可します。 

## 要件

### デバイスの場合: 
> [!NOTE]
> この機能は、現時点では、Windows Insider ビルド 19041.1377 + でのみ avalible になっています。 [詳細については、「Windows Insider ビルドに登録する」を参照して](hololens-insider.md)ください。

### アプリの場合: 
アプリのインストーラーでストアからの依存関係が使用されるため、アプリのソリューション構成は **Master** または **Release** のいずれかである必要があります。 詳細については、「 [アプリパッケージの作成](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)」を参照してください。

このメソッドを使ってインストールされたアプリは、デジタル署名されている必要があります。 アプリに署名するには、証明書を使用する必要があります。 [ [MS TRUSTED CA] リスト](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)から証明書を取得することができます。その場合は、追加の操作を行う必要はありません。 または、独自の証明書に署名することもできます。ただし、証明書はデバイスにプッシュする必要があります。 
- [Sign Tool を使って](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)アプリに署名する方法を説明します。

**証明書オプション:** 
- [MS Trusted CA リスト](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**証明書の展開方法を選択します。** 
- [プロビジョニングパッケージ](hololens-provisioning.md) はローカルデバイスに適用できます。
- MDM を使って、 [デバイスの構成に証明書を適用](https://docs.microsoft.com/mem/intune/protect/certificates-configure)することができます。
- デバイス [証明書マネージャー](hololens-insider.md#certificate-manager)を使用します。 

## インストール方法

1.  HoloLens 2 デバイスの電源が入っていて、サインインしていることを確認します。
1.  PC でカスタムアプリに移動し、yourapp を yourdevicename\Internal Storage\Downloads. にコピーします。 
    ファイルのコピーが完了したら、デバイスを切断して、後でインストールを完了することができます。
1.  HoloLens 2 デバイスから [ **スタート] メニュー**を開き、[ **すべてのアプリ** ] を選択して、 **エクスプローラー** アプリを起動します。
1.  [ダウンロード] フォルダーに移動します。 アプリの左側のパネルで、[ **このデバイス** ] を選択してから、[ダウンロード] に移動することが必要な場合があります。
1.  Yourapp ファイルを選びます。 
1.  アプリのインストーラーが起動します。 アプリをインストールするには、[ **インストール** ] ボタンを選択します。 

インストールされたアプリは、インストールの完了時に自動的に起動します。 

![App Installer による MRTK の例のインストール](images/hololens-app-installer-picture.jpg)

### インストールのトラブルシューティング
アプリのインストールに失敗した場合は、次のことを確認してください。
-   アプリがマスターまたはリリースビルドのどちらかです。
- 使用しているデバイスが、この機能を利用できるビルドに更新されます。 
-   [インターネットに接続](hololens-network.md)されています。
-   [Microsoft Store のエンドポイント](hololens-offline.md)が適切に構成されている。  

## Web インストーラ

ユーザーは、web サーバーから直接アプリをインストールできます。 これにより、アプリのインストーラーが、簡単なダウンロードとインストールの配布方法と組み合わされて使用できるようになります。 

### Web インストールのセットアップ方法:
1.  アプリが正しくインストールされていることを確認します。
1.  [Web ページでこの機能を有効にするには、次の手順を](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)実行します。 

### エンドユーザーエクスペリエンス:
1. ユーザーは、前に選択した方法を使用して、デバイスに証明書を受け取り、インストールします。 
1. ユーザーは、上の手順で作成した URL にアクセスします。

これで、アプリがデバイスにインストールされます。 アプリを見つけるには、[ **スタート] メニュー** を開き、[ **すべてのアプリ** ] ボタンを選んでアプリを見つけます。 

-   このインストール方法のトラブルシューティングについては、「 [アプリインストーラーの問題のトラブルシューティング](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)」を参照してください。 

> [!NOTE]
> 更新プロセス中の UI はサポートされません。 そのため、 [このページ](https://docs.microsoft.com/windows/msix/app-installer/update-settings) と関連オプションの showprompt オプションはサポートされません。

## サンプルアプリ

サンプルアプリを試してみたい場合は、利用可能なサンプルの一部を確認してください。
- [MRTK の例の Hub](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [Hba](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [テストに使用できる UWP サンプルアプリ](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
