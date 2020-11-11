---
title: Microsoft HoloLens の Insider Preview
description: 簡単に Insider ビルドを使い始めて、HoloLens の次の主要なオペレーティング システムの更新プログラムに対する貴重なフィードバックをご提供いただけます。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 11/10/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: cb8ac3b6b74fd6998cde4d32df12dcbd84556597
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162949"
---
# Microsoft HoloLens の Insider Preview

HoloLens 用の最新の Insider Preview ビルドへようこそ! HoloLens 向けの次の主要オペレーティングシステム更新プログラムについては、簡単に [作業を開始](hololens-insider.md#start-receiving-insider-builds) して、貴重なフィードバックを提供していただくことができます。

## Windows Insider リリース ノート

### アプリインストーラーを使用して HoloLens 2 にアプリをインストールする
Windows ホログラフィック、バージョン20H2 の更新プログラムをインストールした後、すぐにアプリのインストーラー機能が提供されます。 お客様が HoloLens 2 デバイスで **シームレスにアプリケーションをインストールできるように、新しい機能 (アプリのインストーラー) を追加** しています。 この機能は、 **非管理対象デバイスでは既定でオンに**なります。 この時点では、企業が中断されないように、アプリインストーラーを **管理対象デバイスで利用できなく** なります。  

以下の **いずれか** に該当する場合、デバイスは "管理されています" と見なされます。
- MDM[登録](hololens-enroll-mdm.md)済み
- [プロビジョニングパッケージ](hololens-provisioning.md)で構成されている
- ユーザー [id](hololens-identity.md) は AAD です

開発者モードを有効にしたり、Device Portal を使用したりしなくても、アプリをインストールできるようになりました。  Appx バンドルをデバイスにダウンロード (USB 経由またはエッジ経由) するだけで、インストールを開始するように促すメッセージが表示されるように、ファイルエクスプローラーで Appx バンドルに移動できます。  または、 [web ページからインストールを開始](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)します。  Microsoft Store またはサイドローディングで MDM の LOB アプリの展開機能を使用してインストールしたアプリと同様に、アプリを展開するには、アプリを展開する前に、アプリをインストールする前に、 [サインインツール](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) を使ってデジタル署名する必要があります。また、署名に使用する証明書は、HoloLens デバイスで [信頼される必要があり](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) ます

**アプリケーションのインストール手順。**

1.  デバイスが管理されていると見なされないようにします。
1.  HoloLens 2 デバイスの電源が入っていて、PC に接続されていることを確認する
1.  HoloLens 2 デバイスにサインインしていることを確認する
1.  PC でカスタムアプリに移動し、yourapp を yourdevicename\Internal Storage\Downloads. にコピーします。   ファイルのコピーが完了したら、デバイスを切断することができます。
1.  HoloLens 2 デバイスから [スタート] メニューを開き、[すべてのアプリ] を選択して、エクスプローラーアプリを起動します。
1.  [ダウンロード] フォルダーに移動します。 アプリの左側のパネルで、[このデバイス] を選択してから、[ダウンロード] に移動することが必要な場合があります。
1.  Yourapp ファイルを選びます。
1.  アプリのインストーラーが起動します。 アプリをインストールするには、[インストール] ボタンを選択します。
インストールされたアプリは、インストールの完了時に自動的に起動します。

このフローをテストするには、 [Windows Universal Sample GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) のサンプルアプリを参照してください。

[アプリインストーラーで HoloLens 2 にアプリをインストールする](app-deploy-app-installer.md)方法については、こちらを参照してください。  

![App Installer による MRTK の例のインストール](images/hololens-app-installer-picture.jpg)

## Insider ビルドの受信の開始

> [!NOTE]
> 最近更新していない場合は、デバイスを再起動して、状態を更新し、最新のビルドを取得してください。
> - "デバイスの再起動" 音声コマンドは適切に動作します。 
> - [設定] または [Windows Insider Program] で [再起動] を選択することもできます。
>
> バックエンドに、発生した可能性のあるバグがありました。これで、この問題が報告されます。

HoloLens 2 デバイスで、**[設定]** > **[更新とセキュリティ]** > **[Windows Insider Program]** の順に移動し、**[開始する]** を選択します。 Windows Insider として登録するために使用したアカウントをリンクします。

Windows insider がチャネルに移動するようになりました。 **ファスト**リングは**Dev チャネル**になります。**スロー**リングは**ベータチャネル**になり、 **release preview** ring は**リリースプレビューチャネル**になります。 マッピングの外観は次のようになります。

![Windows Insider チャネルの説明](images/WindowsInsiderChannels.png)

詳細については、「windows のブログに [Windows Insider チャネルを導入](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) する」を参照してください。

次に、[ **Windows のアクティブな開発**] を選択し、 **開発者チャネル** または **ベータチャネル** のビルドを受け取るかどうかを選択して、プログラムの利用規約を確認します。

[確認] を選択し、[ **今すぐ再起動 >** ます。] を選びます。 デバイスが再起動したら、[設定] に移動して **& セキュリティ > 更新** プログラムを確認し > 最新のビルドを入手します。

## FFU のダウンロードとフラッシュの手順
フライト署名のある FFU でテストするには、フライト署名のある FFU をフラッシュする前にデバイスのフライト ロックを解除する必要があります。
1. PC の場合:

    1. から PC に ffu をダウンロード [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) してください。
    
    1. Microsoft Store ([https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)) から ARC (Advanced Recovery Companion) をインストールします。
    
1. HoloLens でのロック解除:**設定**の  >  **更新 & セキュリティ**  >  **Windows Insider プログラム**を開くと、次にサインアップして、デバイスを再起動します。

1. Flash FFU-「ARC」を使って、フライト署名された FFU を点滅させることができます。

## フィードバックを提供し、問題を報告する

HoloLens で[フィードバック Hub アプリ](hololens-feedback.md)を使用してフィードバックを提供し、問題を報告することができます。 フィードバック Hub を使用すると、エンジニアが問題を迅速にデバッグして解決するのに役立つすべての必要な診断情報が含まれるようになります。  中国語および日本語版の HoloLens に関する問題は、同じ方法で報告する必要があります。

> [!NOTE]
> フィードバック Hub を使用してドキュメント フォルダーにアクセスするかどうかを確認するプロンプトに必ず同意してください (メッセージが表示されたら **[はい]** を選択します)。

## 開発者向けの注意事項

HoloLens の Insider ビルドを使用して自由にアプリケーションを開発してみることをお勧めします。  作業を始めるには、[HoloLens 開発者向けドキュメント](https://developer.microsoft.com/windows/mixed-reality/development)をご覧ください。 これらの同じ手順は HoloLens の Insider ビルドでも使用できます。  HoloLens 開発用に使用しているものと同じビルドの Unity と Visual Studio を使用できます。

## Insider ビルドの受信の停止

Windows Holographic の Insider ビルドを受け取りたくない場合は、HoloLens が製品版ビルドを実行しているときにオプトアウトすることができます。または、Advanced Recovery Companion を使用して[デバイスを回復](hololens-recovery.md)し、Windows Holographic の Insider バージョン以外にデバイスを回復することができます。

> [!CAUTION]
> 新しいプレビュー ビルドを手動で再インストールした後に Insider Preview ビルドの登録を解除すると、ブルー スクリーンが発生するという既知の問題があります。 その後、手動でデバイスを回復する必要があります。 影響を受けるかどうかの詳細については、この[既知の問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)の詳細をご覧ください。

HoloLens が製品版ビルドを実行していることを確認するには、次の操作を行います。

1. **[設定] > [システム] > [バージョン情報]** の順に移動し、ビルド番号を探します。

1. [製品のビルド番号については、リリースノートを参照してください](hololens-release-notes.md)。

Insider ビルドをオプトアウトするには、次の操作を行います。

1. 製品版ビルドを実行している HoloLens で、**[設定] > [更新とセキュリティ] > [Windows Insider Program]** に移動して、**[Insider Preview ビルドの停止]** を選択します。

1. 画面の指示に従って、デバイスでの受信を停止します。
