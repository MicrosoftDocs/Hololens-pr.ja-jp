---
title: HoloLens 2 アプリインストーラーを使用してアプリをサイドロードしてインストールする方法
description: アプリのインストーラーを使用してアプリをインストールおよびトラブルシューティングする方法と、UI を使用してアプリをサイドロードしてインストールする方法について説明します。
keywords: アプリ管理, アプリ, hololens, アプリインストーラー
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
ms.openlocfilehash: 9e413963dbf34dd071fc9603487590065b967ee7
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309273"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>アプリインストーラーを使用して HoloLens 2 にアプリをインストールする

> [!NOTE]
> この機能は [、Windows Holographic、バージョン20H2 –2020年12月の更新プログラム](hololens-release-notes.md)で利用可能になりました。 この機能を使用するようにデバイスが [更新](hololens-update-hololens.md) されていることを確認してください。

HoloLens 2 デバイスに **アプリケーションをシームレスにインストールできる新しい機能 (アプリインストーラー) が追加され** ました。 この機能は、管理されていない **デバイスに対しては既定でオンに** なります。 企業が中断されないように、現時点では、 **管理対象デバイス** でアプリインストーラーを使用できなくなります。  

次の **いずれか** に該当する場合、デバイスは "管理されている" と見なされます。

- MDM[登録](hololens-enroll-mdm.md)済み
- [プロビジョニングパッケージ](hololens-provisioning.md)で構成済み
- ユーザー [id](hololens-identity.md) が Azure AD

開発者モードを有効にしたり、デバイスポータルを使用したりすることなく、アプリをインストールできるようになりました。  Appx バンドルをデバイスに (USB 経由または Microsoft Edge 経由で) ダウンロードし、エクスプローラーで Appx バンドルに移動して、インストールを開始するように求められるようにします。  または、 [web ページからインストールを開始](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)します。  MDM の LOB アプリのデプロイ機能を使用して Microsoft Store またはサイドロードからインストールするアプリと同様に、アプリは [署名ツール](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) でデジタル署名する必要があり、 [署名に使用する証明書](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) は、アプリを展開する前に HoloLens デバイスによって信頼されている必要があります。

## <a name="requirements"></a>要件

### <a name="for-your-devices"></a>デバイスの場合:

この機能は現在、HoloLens 2 デバイス用の Windows Holographic 20H2 ビルドで使用できます。 この方法を使用しているデバイスがすべて [更新](hololens-update-hololens.md)されていることを確認します。

### <a name="for-your-apps"></a>アプリの場合:

アプリのインストーラーがストアからの依存関係を使用するため、アプリのソリューション構成は **マスター** または **リリース** のいずれかである必要があります。 詳細については、「 [アプリパッケージの作成](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)」を参照してください。

この方法でインストールされるアプリには、デジタル署名が必要です。 アプリに署名するには、証明書を使用する必要があります。 [MS 信頼さ](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)れた CA の一覧から証明書を取得することができます。この場合、特別な操作を行う必要はありません。 または、証明書をデバイスにプッシュする必要がありますが、独自の証明書に署名することもできます。

- [署名ツールを使用して](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)アプリに署名する方法。

**証明書のオプション:**

- [MS 信頼された CA の一覧](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**証明書の展開方法を選択します。**

- [プロビジョニングパッケージ](hololens-provisioning.md) は、ローカルデバイスに適用できます。
- MDM を使用し [て、デバイス構成を含む証明書を適用](https://docs.microsoft.com/mem/intune/protect/certificates-configure)できます。
- デバイス [証明書マネージャー](certificate-manager.md)でを使用します。

## <a name="installation-method"></a>インストール方法

1. デバイスが管理対象と見なされていないことを確認します。
1. HoloLens 2 デバイスの電源が入っていて、サインインしていることを確認します。
1. お使いの PC でカスタムアプリに移動し、yourapp を yourdevicename\Internal Storage\Downloads. にコピーします。
    ファイルのコピーが完了したら、デバイスを切断し、後でインストールを完了することができます。
1. HoloLens 2 デバイスから [ **スタート] メニュー** を開き、[ **すべてのアプリ** ] を選択して、 **エクスプローラー** アプリを起動します。
1. ダウンロードフォルダーに移動します。 アプリの左側のパネルで [ **このデバイス** を最初に選択する] をクリックし、[ダウンロード] に移動します。
1. Yourapp ファイルを選択します。
1. アプリのインストーラーが起動します。 [ **インストール** ] ボタンを選択して、アプリをインストールします。

インストールの完了時に、インストールされているアプリが自動的に起動します。

![アプリインストーラーを使用した MRTK の例のインストール](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>インストールのトラブルシューティング

アプリをインストールできなかった場合は、次のことを確認してトラブルシューティングを行います。

- アプリは、マスタービルドまたはリリースビルドのいずれかです。
- この機能が使用可能なビルドにデバイスが更新されます。
- [インターネットに接続](hololens-network.md)されています。
- [Microsoft Store のエンドポイント](hololens-offline.md)が正しく構成されています。  

## <a name="web-installer"></a>Web インストーラー

ユーザーは、web サーバーから直接アプリをインストールできます。 このフローでは、簡単なダウンロードとインストールの配布方法を組み合わせて、アプリインストーラーを使用します。

### <a name="how-to-set-up-web-install"></a>Web インストールのセットアップ方法:

1. アプリがインストールするように正しく構成されていることを確認します。
1. [Web ページからのインストールを有効にするには、次の手順に](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)従います。

### <a name="end-user-experience"></a>エンドユーザーエクスペリエンス:

1. ユーザーは、前に選択した方法を使用して、デバイスに証明書を受信してインストールします。
1. ユーザーは、前の手順で作成した URL にアクセスします。

これで、アプリがデバイスにインストールされます。 アプリを検索するには、[ **スタート] メニュー** を開き、[ **すべてのアプリ** ] ボタンをクリックしてアプリを検索します。

- アプリインストーラーのインストール方法のトラブルシューティングに関する詳細については、「 [アプリインストーラーの問題のトラブルシューティング](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)」を参照してください。

> [!NOTE]
> 更新プロセス中の UI はサポートされていません。 [このページ](https://docs.microsoft.com/windows/msix/app-installer/update-settings)の showprompt オプションと関連するオプションはサポートされていません。

## <a name="sample-apps"></a>サンプル アプリ

いくつかのサンプルアプリを使用してアプリインストーラーを試すには、使用可能なサンプルをいくつか確認してください。

- [MRTK Examples Hub](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [Surfaces](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [テストに使用できる UWP サンプルアプリ](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
