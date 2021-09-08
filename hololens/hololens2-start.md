---
title: HoloLens 2 のセットアップ
description: Microsoft (MSA) または Azure Active Directory (AAD) アカウントを使用して Wi-Fi ネットワーク上で初めて HoloLens 2 をセットアップする方法について説明します。
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 8f07ed42c873b62b3b4201c2756b55bbb29707d3
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189768"
---
# <a name="set-up-your-hololens-2"></a>HoloLens 2 のセットアップ

初めて HoloLens の電源を入れたときは、デバイスのセットアップ、ユーザー アカウントによるサインイン、ユーザーの目に合わせた HoloLens の調整の手順を案内するガイドが表示されます。  このセクションでは、HoloLens 2 の初期セットアップ エクスペリエンスについて説明します。

次のセクションでは、HoloLens とホログラムの操作方法を学びます。 この記事に進むには、[「HoloLens 2 について」](hololens2-basic-usage.md)を参照してください。

## <a name="before-you-start"></a>開始する前に

始める前に、以下が利用可能であることを確認してください。

**ネットワーク接続**。 HoloLens をセットアップするには、ネットワークに接続する必要があります。 HoloLens 2 では、Wi-Fi またはイーサネットを使用して接続できます (USB-C to Ethernet Adapter が必要です)。 初回接続時には、Web サイトへの移動や証明書を必要とせずに接続できる、オープン ネットワークまたはパスワードで保護されたネットワークが必要です。 [HoloLens を使用する Web サイトの詳細について説明します](hololens-offline.md)。

**Microsoft アカウント**。 HoloLens には、Microsoft アカウント (または、組織がデバイスを所有している場合は職場アカウント) を使ってサインインする必要があります。 Microsoft アカウントをお持ち出ない場合は、[account.microsoft.com](https://account.microsoft.com) に進んで作成してください。無料です。

**トリップの危険性がない、安全で明るく照らされた空間**。 [正常性と安全性に関する情報](https://go.microsoft.com/fwlink/p/?LinkId=746661)。

HoloLens に付属する **最適なフィット感のアクセサリ** で、快適なフィット感が得られます。 [フィット感と快適性の詳細について](hololens2-setup.md#adjust-fit)。

## <a name="set-up-windows"></a>Windows の設定

HoloLens 2 を初めて起動する場合、最初のタスクは Windows Holographic をセットアップすることです。  HoloLens を起動すると、音楽が再生され、Microsoft ロゴが表示されます。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGGGk]

<br/>
<img src="images/01-magic-moment.png" width="500px" alt="First screen during first boot">

ハチドリが飛び回っているのが見えます。

<img src="images/hummingbird-1.png" width="500px" alt="Hummingbird flying">

手のところにやって来ます。

<img src="images/hummingbird-2.png" width="500px" alt="Hummingbird flying close up">

Microsoft ロゴのボタンが表示されます。 ボタンを押すと、HoloLens 2 により、以下の手順が表示されます。

1. 言語を選択します。

    <img src="images/04-language.png" width="500px" alt="Select language">

1. 自分のリージョンを選択します。

    <img src="images/05-region.png" width="500px" alt="Select region">

1. HoloLens を自分の目に合わせて調整します。  調整のスキップを選択すると、次回のログイン時にメッセージが表示されます。 

    1. まず、バイザーを調整します。
    
    <img src="images/06-et-corners.png" width="500px" alt="Calibration selection screen">
    
    2. 調整するには、一連のターゲット (「宝石」 と呼ばれます) を目視します。 調整中にまばたきしたり目を閉じたりしても問題はありませんが、室内や物理空間内にある他の物体を見つめないように注意してください。 HoloLens はこのプロセスを使用して、高い精度でホログラフィックの世界をレンダリングできるように、ユーザーの眼球位置を学習します。 

        <img src="images/07-adjust-eyes.png" width="500px" alt="Adjust for your eyes">

        調整後は、頭部に装着したバイザーの位置がずれても、ホログラムが正しく表示されます。 調整情報は、デバイスにローカル保存され、アカウント情報には関連付けられません。 詳細については、[「調整データと セキュリティ」](hololens-calibration.md#calibration-data-and-security)を参照してください。

        <img src="images/calibration-complete.png" width="500px" alt="Calibration is complete">

1. インターネットに接続します (Wi-Fi またはイーサネット接続を選択します)。

     Wi-Fi ネットワークから取得した情報に基づいて、HoloLens のタイム ゾーンが自動的に設定されます。 タイムゾーンは、セットアップの完了後に設定アプリを使用して変更することもできます。

    ![Wi-Fi に接続する。](images/11-network.png)

    > [!NOTE] 
    > Wi-Fi の手順よりも先に進んでいて、後でセットアップ中に別のネットワークに切り替える必要がある場合は、 **[ボリューム ダウン]** ボタンと **[電源]** ボタンを同時に押して、この手順に戻ることができます (October 2019 以降の OS バージョンを実行している場合)。 以前のバージョンでは、自動的に接続できないようにするために、Wi-Fi ネットワークが使用できない場所で[デバイスをリセットする](hololens-recovery.md)か、または再起動する必要があります。
    > 
    > また、HoloLens のセットアップ時に、2 分間の資格情報のタイムアウトがあることに注意してください。 ユーザー名/パスワードは 2 分以内に入力する必要があります。そうしないと、ユーザー名フィールドは自動的にクリアされます。

1. HoloLens 2 Autopilot プロファイルが存在する場合は、そのプロファイルを検索して適用します。 この画面では、操作は必要はありません。
 
    ![Autopilot プロファイルの検索。](images/autopilot-profile-search.png) 

1. ライセンス 画面で **[同意する]** をクリックします。

    ![Windows ライセンス契約。](images/windows-license-agreement.png)

1. お使いのユーザー アカウントにサインインします。 **自分の職場または学校 が所有し**、 **自分が所有している** から 選択します。

    ![ユーザーの設定。](images/13-device-owner.png)
    - **[職場または学校が所有しています]** を選んだ場合、Azure AD アカウントを使ってサインインします。 組織で Azure AD Premium を使用しており、MDM への自動登録が構成されている場合は、HoloLens が自動的に MDM に登録されます。 組織で Azure AD Premium が使用されていない場合、MDM への自動登録は使用できません。 その場合は、[デバイス管理で手動で HoloLens を登録する必要があります](hololens-enroll-mdm.md#different-ways-to-enroll)。

        1. 組織アカウントの情報を入力します。
        1. プライバシー ステートメントとエンドユーザーのライセンス条項に同意します。
        1. Azure AD 資格情報を使用してサインインします。 組織のサインイン ページにリダイレクトされることがあります。
        1. デバイスのセットアップを続行します。

    - **[自分が所有しています]** を選んだ場合、Microsoft アカウントを使ってサインインします。 セットアップが完了したら、[HoloLens をデバイス管理に手動で登録](hololens-enroll-mdm.md#different-ways-to-enroll)できます。

        1. Microsoft アカウントの情報を入力します。
        2. パスワードを入力します。 Microsoft アカウントで [2 段階認証 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/) が要求される場合、検証プロセスを実行します。

        
1. **[次へ**] を選択して虹彩認証サインインを設定します。 目の調整と同様のエクスペリエンスを体験します。 スキャンが完了したら 、 **[完了]** を選択します。 **[スキップ]** を選択 して、この手順をバイパスできます。
    
    <img src="images/setup-iris.png" width="500px" alt="Iris setup">

    <img src="images/iris-setup-complete.png" width="500px" alt="Iris setup completion">

     
  
1. デバイスにログインする PIN を設定します。 この PIN はデバイス固有です。 

    ![Windows Hello の設定。](images/setup-windows-hello.png)

    ![Windows Hello PIN の設定。](images/windows-hello-pin.png)

    ![Windows Hello セットアップが成功しました。](images/windows-hello-successful.png) 

    
1. HoloLens 2 で音声を有効にするかどうかを選択します。

    <img src="images/22-do-more-with-voice.png" width="500px" alt="Enable Cortana">

1. HoloLens 2 で位置を有効にするかどうかを選択します。
    
    <img src="images/setup-location-services.png" width="500px" alt="Enable location services">

1. テレメトリ レベルを選択します。 可能な場合は、オプションのテレメトリを有効にしてください。 この情報は、HoloLens エンジニアリング チームの作業に大きく役立ちます。

    <img src="images/24-telemetry.png" width="500px" alt="Telemetry level">


1. HoloLens 2 でスタート ジェスチャを使用する方法について説明します。

    <img src="images/26-01-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 1">

    <img src="images/26-02-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 2">
    
    > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3Wxng]
    
    おめでとうございます。  セットアップは完了です。HoloLens の使用準備ができました。

## <a name="next-steps"></a>次のステップ

1. すぐに Mixed Reality の操作を開始し、HoloLens で Windows 10 をナビゲートします。手の操作に関する実践的なチュートリアルについては、**ヒント** アプリを確認してください。 スタート ジェスチャを使用して [スタート] に移動するか、「スタートに移動」と言って [ヒント] を選択します。

1. HoloLens 2 の操作方法について読み続けるには、以下をクリックしてください。

> [!div class="nextstepaction"]
> [HoloLens 2 の基本操作](hololens2-basic-usage.md)
