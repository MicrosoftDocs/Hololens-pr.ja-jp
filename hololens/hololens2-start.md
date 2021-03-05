---
title: HoloLens 2 のセットアップ
description: Microsoft (MSA) または Azure Active Directory (AAD) アカウントを使用して Wi-Fi ネットワーク上で初めて HoLens 2 をセットアップする方法について説明します。
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 9/17/2019
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 31c2c9ed7b2a35c759a0e1d86b89a2f0ab75d965
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385609"
---
# <a name="set-up-your-hololens-2"></a>HoloLens 2 のセットアップ

初めて HoloLens の電源を入れたときは、デバイスのセットアップ、ユーザー アカウントによるサインイン、ユーザーの目に合わせた HoloLens の調整の手順を案内するガイドが表示されます。  このセクションでは、HoloLens 2 の初期セットアップ エクスペリエンスについて説明します。

次のセクションでは、HoloLens とホログラムの操作方法を学びます。 直接この記事に進むには、「[HoloLens 2 の概要](hololens2-basic-usage.md)」をご覧ください。

## <a name="before-you-start"></a>開始する前に

始める前に、以下が利用可能であることを確認してください。

**ネットワーク接続**。 HoloLens をセットアップするには、ネットワークに接続する必要があります。 HoloLens 2 では、Wi-Fi またはイーサネットを使用して接続できます (USB-C to Ethernet Adapter が必要です)。 初回接続時には、Web サイトへの移動や証明書を必要とせずに接続できる、オープン ネットワークまたはパスワードで保護されたネットワークが必要です。 [HoloLens で使用する Web サイトについて詳しくは、こちらをご覧ください](hololens-offline.md)。

**Microsoft アカウント**。 HoloLens には、Microsoft アカウント (または、組織がデバイスを所有している場合は職場アカウント) を使ってサインインする必要があります。 Microsoft アカウントをお持ちでない場合は、[account.microsoft.com](https://account.microsoft.com) にアクセスして無料でセットアップできます。

**つまずく危険性のない安全で明るい場所**。 [健康と安全に関する情報をご覧ください](https://go.microsoft.com/fwlink/p/?LinkId=746661)。

**快適さを高めるオプションのアクセサリ**。HoloLens には、より快適なフィット感を得られるように、オプションのアクセサリが付属しています。 [快適に使うための詳しい情報をご覧ください](hololens2-setup.md#adjust-fit)。

## <a name="set-up-windows"></a>Windows のセットアップ

HoloLens 2 を初めて起動する場合、最初のタスクは Windows Holographic をセットアップすることです。  HoloLens を起動すると、音楽が再生され、Windows ロゴが表示されます。

![初回起動時の最初の画面](images/01-magic-moment.png)

HoloLens 2 に、以下の手順が表示されます。

1. 言語を選択します。
    ![言語の選択](images/04-language.png)

1. 地域を選択します。
    ![地域の選択](images/05-region.png)

1. HoloLens を自分の目に合わせて調整します。  調整のスキップを選択すると、次回のログイン時にメッセージが表示されます。

    調整するには、一連のターゲット ("ジェム" と呼ばれます) を目視します。 調整中にまばたきしたり目を閉じたりしても問題はありませんが、室内や物理空間内にある他の物体を見つめないように注意してください。 HoloLens はこのプロセスを使用して、高い精度でホログラフィックの世界をレンダリングできるように、ユーザーの眼球位置を学習します。 調整後は、頭部に装着したバイザーの位置がずれても、ホログラムが正しく表示されます。

    調整情報は、デバイスにローカル保存され、アカウント情報には関連付けられません。 詳しくは、「[調整データとセキュリティ](hololens-calibration.md#calibration-data-and-security)」をご覧ください。

    ![調整の選択画面](images/06-et-corners.png)

1. インターネットに接続します (Wi-Fi またはイーサネット接続を選択します)。
     Wi-Fi ネットワークから取得した情報に基づいて、HoloLens のタイム ゾーンが自動的に設定されます。 タイムゾーンは、セットアップの完了後に設定アプリを使用して変更することもできます。

    ![Wi-Fi に接続する](images/11-network.png)
> [!NOTE] 
> Wi-Fi の手順よりも先に進んでいて、後でセットアップ中に別のネットワークに切り替える必要がある場合は、**[音量を下げる]** ボタンと **[電源]** ボタンを同時に押して、この手順に戻ることができます (October 2019 以降の OS バージョンを実行している場合)。 以前のバージョンでは、自動的に接続できないようにするために、Wi-Fi ネットワークが使用できない場所で[デバイスをリセットする](hololens-recovery.md)か、または再起動する必要があります。
> 
> また、HoloLens のセットアップ時に、2 分間の資格情報のタイムアウトがあることに注意してください。 ユーザー名/パスワードは 2 分以内に入力する必要があります。そうしないと、ユーザー名フィールドは自動的にクリアされます。

1. お使いのユーザー アカウントにサインインします。 **[職場または学校が所有しています]** または **[自分が所有しています]** を選択します。
    - **[職場または学校が所有しています]** を選んだ場合、Azure AD アカウントを使ってサインインします。 組織で Azure AD Premium を使用しており、MDM への自動登録が構成されている場合は、HoloLens が自動的に MDM に登録されます。 組織で Azure AD Premium が使用されていない場合、MDM への自動登録は使用できません。 その場合は、[HoloLens をデバイス管理に手動で登録](hololens-enroll-mdm.md#different-ways-to-enroll)する必要があります。
        1. 組織アカウントの情報を入力します。
        1. プライバシー ステートメントとソフトウェア ライセンス条項に同意します。
        1. Azure AD 資格情報を使用してサインインします。 組織のサインイン ページにリダイレクトされることがあります。
        1. デバイスのセットアップを続行します。
    - **[自分が所有しています]** を選んだ場合、Microsoft アカウントを使ってサインインします。 セットアップが完了したら、[手動で HoloLens をデバイス管理に登録](hololens-enroll-mdm.md#different-ways-to-enroll)できます。
        1. Microsoft アカウントの情報を入力します。
        2. パスワードを入力します。 Microsoft アカウントで [2 段階認証 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/) が要求される場合、検証プロセスを実行します。

    ![ユーザーの設定](images/13-device-owner.png)

1. HoloLens 2 で音声認識を有効にするかどうかと、診断に関する製品利用統計情報を送信するかどうかを選択します。
    ![Cortana を有効にする](images/22-do-more-with-voice.png)

1. 製品利用統計情報レベルを選択します。 可能であれば、"完全" 利用統計情報レベルを有効にしてください。 この情報は、HoloLens エンジニアリング チームの作業に大きく役立ちます。
     ![製品利用統計情報のレベル](images/24-telemetry.png)

1. HoloLens 2 でスタート ジェスチャを使用する方法について説明します。
     ![スタート ジェスチャの使用方法、イメージ 1](images/26-01-startmenu-learning.png) ![スタート ジェスチャの使用方法、イメージ 2](images/26-02-startmenu-learning.png)

お疲れさまでした。  セットアップは完了です。HoloLens の使用準備ができました。

## <a name="next-steps"></a>次の手順

1. すぐに Mixed Reality の操作を開始し、HoloLens で Windows 10 をナビゲートします。手の操作に関する実践的なチュートリアルについては、**ヒント** アプリを確認してください。 スタート ジェスチャを使用して [スタート] に移動するか、「スタートに移動」と言って [ヒント] を選択します。 
1. HoloLens 2 の操作方法について読み続けるには、以下をクリックしてください。

> [!div class="nextstepaction"]
> [HoloLens 2 の概要](hololens2-basic-usage.md)
