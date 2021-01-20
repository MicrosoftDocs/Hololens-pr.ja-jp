---
title: HoloLens 2 アプリ インストーラーを使用してアプリをサイド ロードしてインストールする方法
description: UI を使ったアプリのスライドの読み込みとインストール
keywords: アプリ管理, アプリ, hololens, アプリ インストーラー
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
ms.openlocfilehash: ab0c58d5a97d5dbaf83adf321d1f9fbc01b3ad03
ms.sourcegitcommit: 37910c10f0f98aa9cbdc29124cd8f14ee0af3fbd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2021
ms.locfileid: "11280656"
---
# アプリ インストーラーを使用して HoloLens 2 にアプリをインストールする

> [!NOTE]
> この機能は [、Windows Holographic バージョン 20H2 ~ December 2020 Update で利用できます](hololens-release-notes.md)。 この機能を使用 [するためにデバイスが](hololens-update-hololens.md) 更新されていないことを確認します。

HoloLens 2 デバイスにアプリケーションをシームレスにインストールできる新しい機能 (アプリ インストーラー **)** が追加されました。 この機能は、非 **管理対象デバイスに対して既定で有効になります**。 企業の中断を防ぐため、現時点では管理対象デバイスでアプリ **インストーラーを** 利用できません。  

次の条件に当てはまる場合、デバイス**** は "管理対象" と見なされます。

- MDM [の登録](hololens-enroll-mdm.md)
- プロビジョニング パッケージ [で構成](hololens-provisioning.md)
- ユーザー [ID は](hololens-identity.md) Azure AD

開発者モードを有効にしたり、Device Portal を使用したりすることなく、アプリをインストールできます。  (USB 経由または Microsoft Edge 経由で) Appx バンドルをデバイスにダウンロードし、エクスプローラーで Appx バンドルに移動して、インストールを開始するように求めるメッセージが表示されます。  または、Web [ページからインストールを開始します](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。  Microsoft Store からインストールしたアプリや MDM の LOB アプリ展開機能を使ってサイドロードするアプリと同様に、[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)アプリは署名ツール[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)でデジタル署名する必要があります。また、アプリを展開する前に、署名に使用する証明書が HoloLens デバイスによって信頼されている必要があります。

## 要件

### デバイスの場合:

 この機能は現在、HoloLens 2 デバイス用の Windows Holographic 20H2 ビルドで利用できます。 この方法を使用しているすべてのデバイスが[更新されます。](hololens-update-hololens.md)

### アプリの場合: 
アプリ インストーラーはストアからの依存関係を使**** うの**** で、アプリのソリューション構成はマスターまたはリリースである必要があります。 アプリ パッケージの作成 [について詳しくは、以下をご覧ください](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)。

この方法でインストールされるアプリは、デジタル署名されている必要があります。 アプリに署名するには、証明書を使う必要があります。 MS Trusted [CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)から証明書を取得できます。その場合は、追加の操作を行う必要はありません。 または、独自の証明書に署名することもできますが、証明書をデバイスにプッシュする必要があります。

- 署名ツールを使って [アプリに署名する方法。](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**証明書オプション:**

- [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**証明書の展開方法を選択します。**

- [プロビジョニング パッケージは](hololens-provisioning.md) 、ローカル デバイスに適用できます。
- MDM を使って、デバイス [構成で証明書を適用できます](https://docs.microsoft.com/mem/intune/protect/certificates-configure)。
- デバイス証明書マネージャーを [使用します](certificate-manager.md)。

## インストール方法

1. デバイスが管理対象と見なされていないことを確認します。
1. HoloLens 2 デバイスの電源がオンで、サインイン中です。
1. PC でカスタム アプリに移動し、app.appxbundle をdevicename\Internal Storage\Downloads にコピーします。
    ファイルのコピーが完了したら、デバイスを切断して後でインストールを完了できます。
1. HoloLens 2 デバイスから [スタート]**** メニューを**開**き、[すべてのアプリ] を選択し、エクスプローラー アプリ**を起動**します。
1. [ダウンロード] フォルダーに移動します。 アプリの左側のパネルで、最初に [この**** デバイス] を選択し、[ダウンロード] に移動する必要があります。
1. yourapp.appxbundle ファイルを選択します。
1. アプリ インストーラーが起動します。 [インストール **] ボタン** を選択してアプリをインストールします。

インストールが完了すると、インストールされたアプリが自動的に起動します。

![アプリ インストーラーによる MRTK の例のインストール](images/hololens-app-installer-picture.jpg)

### インストールのトラブルシューティング

アプリのインストールに失敗した場合は、以下を確認してトラブルシューティングを行います。

- アプリは、マスター ビルドまたはリリース ビルドのいずれかです。
- デバイスは、この機能が利用可能なビルドに更新されます。
- インターネット [に接続されています](hololens-network.md)。
- [Microsoft Store のエンドポイントが正しく](hololens-offline.md)構成されている。  

## Web インストーラー

ユーザーは、Web サーバーから直接アプリをインストールできます。 このフローでは、アプリ インストーラーと簡単なダウンロードとインストールの配布方法を組み合わせて使用します。

### Web インストールをセットアップする方法:

1. アプリがインストールするように正しく構成されていることを確認します。
1. Web ページから [インストールを有効にするには、次の手順を実行します](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。

### エンド ユーザー エクスペリエンス:

1. ユーザーは、上記で選択した方法を使用して、デバイスに証明書を受信してインストールします。
1. ユーザーは、上記の手順で作成した URL にアクセスします。

アプリがデバイスにインストールされます。 アプリを見つけるには、スタート メニュー**を開**き****、[すべてのアプリ] ボタンを選択してアプリを探します。

- アプリ インストーラーのインストール方法のトラブルシューティングについて詳しくは、アプリ インストーラーの問題 [のトラブルシューティングに関するページをご覧ください](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)。

> [!NOTE]
> 更新プロセス中の UI はサポートされていません。 したがって、このページの ShowPrompt [オプションと](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 関連オプションはサポートされていません。

## サンプル アプリ

いくつかのサンプル アプリでアプリ インストーラーを試す場合は、利用可能なサンプルを確認してください。

- [MRTK の例ハブ](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [サーフェス](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [テストに使用できる UWP サンプル アプリ](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
