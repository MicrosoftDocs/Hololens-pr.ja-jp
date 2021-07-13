---
title: アプリの読み込みとインストールのサイド HoloLens 2 アプリ インストーラー
description: アプリ インストーラーを使用してアプリをインストールし、トラブルシューティングを行い、UI を使用してアプリをサイド ロードしてインストールする方法について説明します。
keywords: アプリ管理, アプリ, Hololens, アプリ インストーラー
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8f236ee27903069b65d3ded8eb7a1f37c65f535e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635587"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>HoloLens 2 経由でアプリを アプリ インストーラー

> [!NOTE]
> この機能は[、Holographic バージョン 20H2 Windows 2020 年 12](hololens-release-notes.md)月の更新プログラム で使用できます。 この機能を使用するには [、デバイス](hololens-update-hololens.md) が更新されている必要があります。

新しい **機能 (アプリ インストーラー)** が追加され、お使いのデバイスにアプリケーションをシームレスにHoloLens 2しました。 この機能は、アン **マネージド デバイスでは既定でオンになります**。 企業の中断を防ぐために、現時点では、マネージド デバイスでアプリ インストーラー **を** 使用できません。  

次の条件に当てはまる場合、デバイスは "マネージド" と見なされます。

- MDM [登録済み](hololens-enroll-mdm.md)
- プロビジョニング パッケージ [を使用して構成する](hololens-provisioning.md)
- ユーザー [ID が](hololens-identity.md) Azure AD

開発者モードを有効にしたり、アプリを使用したりせずにアプリをインストールデバイス ポータル。  (USB 経由または Microsoft Edge 経由で) Appx バンドルをデバイスにダウンロードし、エクスプローラー の Appx バンドルに移動して、インストールを開始するように求めるメッセージが表示されます。  または、Web [ページ からインストールを開始します](/windows/msix/app-installer/installing-windows10-apps-web)。 mdm の LOB アプリ展開機能を使用して Microsoft Store またはサイドロードからインストールするアプリと同様に、アプリは署名ツールでデジタル[](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)署名する必要があります[](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)。また、アプリを展開する前に、署名に使用される証明書が HoloLens デバイスによって信頼されている必要があります。

## <a name="requirements"></a>必要条件

### <a name="for-your-devices"></a>デバイスの場合:

この機能は、現在、デバイスWindows Holographic 20H2 ビルドでHoloLens 2されています。 この方法を使用しているデバイスが[更新されます。](hololens-update-hololens.md)

### <a name="for-your-apps"></a>アプリの場合:

アプリのソリューション構成は、ストアからの依存関係を使用アプリ インストーラーマスターまたはリリースのいずれかである必要があります。 アプリ パッケージの作成に [関する詳細を参照してください](/windows/msix/app-installer/create-appinstallerfile-vs)。

この方法でインストールされるアプリは、デジタル署名する必要があります。 証明書を使用してアプリに署名する必要があります。 MS の信頼された [CA](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)リストから証明書を取得できます。その場合は、追加のアクションを実行する必要はありません。 または、独自の証明書に署名することもできますが、その証明書をデバイスにプッシュする必要があります。

- 署名ツールを使用 [してアプリに署名する方法。](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**証明書のオプション:**

- [MS 信頼された CA リスト](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**証明書の展開方法を選択します。**

- [プロビジョニング パッケージは](hololens-provisioning.md) 、ローカル デバイスに適用できます。
- MDM を使用して、 [デバイス構成 を使用して証明書を適用できます](/mem/intune/protect/certificates-configure)。
- デバイスの証明書マネージャー で [を使用します](certificate-manager.md)。

## <a name="installation-method"></a>インストール方法

1. デバイスが管理対象と見なされていないことを確認します。
1. デバイスの電源HoloLens 2、サインイン済みである必要があります。
1. PC でカスタム アプリに移動し、yourapp.appxbundle を yourdevicename\Internal Storage\Downloads にコピーします。
    ファイルのコピーが完了したら、デバイスを切断し、後でインストールを完了できます。
1. デバイスからHoloLens 2スタート メニューを **開** き **、[すべてのアプリ**] を選択し、アプリを起動 **エクスプローラーします。**
1. [ダウンロード] フォルダーに移動します。 アプリの左側のパネルで、[このデバイス] を最初に選択し、[ダウンロード] に移動する必要があります。
1. yourapp.appxbundle ファイルを選択します。
1. このアプリ インストーラーが起動します。 [インストール **] ボタンを** 選択して、アプリをインストールします。

インストールが完了すると、インストールされたアプリが自動的に起動します。

![以下を使用した MRTK のアプリ インストーラー](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>インストールのトラブルシューティング

アプリのインストールに失敗した場合は、次を確認してトラブルシューティングを行います。

- アプリはマスター ビルドまたはリリース ビルドのいずれかです。
- デバイスは、この機能を使用できるビルドに更新されます。
- インターネット [に接続されています](hololens-network.md)。
- アプリケーション[のエンドポイントMicrosoft Store](hololens-offline.md)正しく構成されています。  

## <a name="web-installer"></a>Web インストーラー

ユーザーは Web サーバーから直接アプリをインストールできます。 このフローでは、簡単なダウンロードとインストールアプリ インストーラー方法と組み合わせて使用する必要があります。

### <a name="how-to-set-up-web-install"></a>Web インストールを設定する方法:

1. アプリがインストールするように正しく構成されていることを確認します。
1. Web ページ から [インストールを有効にするには、次の手順に従います](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。

### <a name="end-user-experience"></a>エンド ユーザー エクスペリエンス:

1. ユーザーは、前に選択した方法を使用して、デバイスに証明書を受信してインストールします。
1. ユーザーは、上記の手順で作成した URL にアクセスします。

これで、アプリがデバイスにインストールされます。 アプリを見つけるには、アプリ **を開** スタート メニュー[すべてのアプリ]ボタンを選択してアプリを見つける必要があります。

- アプリ インストーラーのインストール方法のトラブルシューティングの詳細については、アプリ インストーラーの [問題のトラブルシューティングに関するページを参照してください](/windows/msix/app-installer/troubleshoot-appinstaller-issues)。

> [!NOTE]
> 更新プロセス中の UI はサポートされていません。 そのため、このページの ShowPrompt [オプションと](/windows/msix/app-installer/update-settings) 関連オプションはサポートされていません。

## <a name="sample-apps"></a>サンプル アプリ

使用可能なサンプル アプリ インストーラーを試してみてください。 
> [!div class="nextstepaction"]
> [サンプル アプリ](/windows/mixed-reality/develop/features-and-samples)
