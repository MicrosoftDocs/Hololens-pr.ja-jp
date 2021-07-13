---
title: デプロイ ガイド – 企業接続HoloLens 2 Dynamics 365 Guides - デプロイ
description: デバイスを使用して企業の接続済みネットワークHoloLens 2デバイスの展開を設定する方法についてDynamics 365 Guides。
keywords: HoloLens、管理、企業接続、Dynamics 365 Guides、AAD、Azure AD、MDM、Mobile デバイス管理
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 6407517bca9efd02fdaf45a78cba7a215ec05670
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637066"
---
# <a name="deploy---corporate-connected-guide"></a>デプロイ - 企業接続ガイド

各デプロイの重要な部分は、エンド ユーザーのスムーズなエクスペリエンスを確保するために、自分でテストする前にデプロイが適切に設定されていることを確認する点です。

MDM を使用して Wi-Fi 証明書を展開するために、最初に HoloLens を設定し、開いている Wi-Fi ネットワークまたは証明書を必要としないネットワークにデバイスを登録する必要があります。 HoloLens OOBE と登録が完了すると、デバイスは前に構成したネットワーク証明書と LOB を受け取り、両方がデバイスによって受信されたと検証できます。

その後、テスト ガイドを作成して操作できると確認できます。

## <a name="enrollment-validation"></a>登録の検証

アプリケーションと MDM 登録用にすべてがAzure AD構成されたので、残りはスナップする必要があります。 ユーザー アカウントに接続Wi-FiデバイスHoloLens、以前に構成したデバイスの 1 つAzure AD必要があります。

デバイスが現在出荷時の設定状態ではない場合は、デバイス を再フラッシュする [良い時期になります](/hololens/hololens-recovery#clean-reflash-the-device)。

1. デバイスが OOBE に入った後は、対話を開始し、プロンプトに従う必要があります。

2. Connectに参加する証明書Wi-Fiを必要としない、開いているネットワークに接続します。 これにより、デバイスは、初期セットアップ後に組織のアカウントで使用される証明書Wi-Fiダウンロードできます。

3. 重要なプロンプトは、このサービスを **Who求めるメッセージが表示HoloLens?** [ **マイ ワークまたは学校が所有している] を選択し** 、アカウントの資格情報Azure AD入力します。

4. 登録が成功すると、PIN の設定を求めるメッセージが表示されます。 この PIN は、このユーザーに対してこのデバイスに固有です。 あやめスキャン、音声データ、テレメトリ設定の入力も求め、最後にスタート メニューを開いて OOBE を完了する方法を学習できます。

5. [ホーム] に移動Mixed Reality、学習スタート メニュー開始ジェスチャを使用して **アプリを開** きます。

6. アプリを選択 **設定、[** システム] を **選択します**。 最初に表示される情報は、デバイス名です。HoloLens 2 デバイスの場合は HOLOLENS で、その後に 6 文字の文字列が &quot; &quot; 続きます。

7. この名前をメモします。

    ![HoloLens 2 設定画面](./images/hololens2-settings-about.jpg)

8. デバイスがデバイスに正常に参加Azure AD。 次の 2 つの方法があります。

    1.  アプリ設定します。 [アカウント **設定****アクセスの**  ->  **仕事または学校] を選択します**。 この画面から、[Connected &quot; to nameofAAD]/(nameofAAD に接続済み)[connected to s&#39;s Azure AD。 によって接続されます *yourusername@nameofAAD.onmicrosoft.com* 。 これにより、デバイスが組織の組織に参加&#39;確認Azure AD。

    1. [Azure ポータル](https://portal.azure.com/#home)。 [デバイス **Azure Active Directory**  ->  **すべてのデバイス**] に  ->  **移動** し、デバイス名を検索します。 [結合の種類] の下に 、"結合されたAzure AD表示されます。
        ![[結合の種類] を [確認] Azure AD](./images/hololens2-devices-all-devices.png)

9. デバイスが MDM に登録されていないことを確認します。 次の 2 つの方法があります。

    1. [アカウント **設定、**[アカウント] [**アクセス] の**  ->  **[仕事または学校] を選択します**。 この画面から、[Connected &quot; to nameofAAD]/(nameofAAD に接続済み)[connected to s&#39;s Azure AD。 によって接続されます *yourusername@nameofAAD.onmicrosoft.com* 。 この [Access work or school account]/(この [仕事または学校アカウントにアクセスする]) で、[接続済み] &quot; [nameofAAD]&#39;選択Azure AD。 [接続者 yourusername@nameofAAD.onmicrosoft.com &quot; ] を選択し、[**情報] ボタンを** 選択します。

    1. [Microsoft エンドポイント マネージャー 管理センター に移動します](https://endpoint.microsoft.com/#home)。 ログインし、 [デバイス] 、  **[すべてのデバイス**  ]  **の順に選択します**。 ここから、デバイスの名前HoloLens検索&#39;できます。 Intune に一覧表示されているHoloLens表示される必要があります。

        ![Intune によって管理されているのを確認Azure AD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi証明書の検証

これで、デバイスは証明書を受け取Wi-Fiがあります。 実行できる最も簡単な検証は、証明書をWi-Fiした接続&#39;接続を試みる方法です。 アプリを開 **設定** Network **&amp; Internet** Wi-Fi に移動し  ->  **、Wi-Fi** 接続を選択します。 接続したら、アプリで Microsoft Edge開き、Web サイトに移動できると確認します。

デバイスで証明書を受信したと確認するには、証明書マネージャー を [使用できます](/hololens/certificate-manager)。

## <a name="validate-lob-app-install"></a>LOB アプリのインストールを検証する

マネージド アプリのインストールの進行状況を確認するには、アプリがインストールされているのか、またはアプリのインストール設定。 LOB アプリをグループに必要なインストールとして構成することで、割り当てられたグループ内のユーザーと HoloLens を登録した後、アプリは自動的に HoloLens にダウンロードされます。

[アプリ] をスタート メニュー[すべてのアプリ]**を選択します**。 アプリの数によっては、ページアップボタンまたはページダウン ボタンの使用が必要 **な場合** があります。

デバイスへのアプリのインストールを検証するには **、設定**  ->  **Accounts**  ->  **Access** の仕事または学校を使用して行います。アカウントを選択し、[情報] ボタンを選択し、下にスクロールして MDM からデバイスに適用されているさまざまな構成とアプリを表示します。

Intune からインストールを検証するには [、MEM ポータル](https://endpoint.microsoft.com/#home)の [アプリ]  ->   -> [すべてのアプリ]   -> *[TheNameOfYourApp Device* install status] ページ  ->  **に移動** します。

詳細については、以下をご覧ください[。Intune App Deployment for HoloLens](/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>検証Dynamics 365 Guides

ガイド アプリには、アプリの作成、作成HoloLens操作に関するモードがあります。 ガイドを操作する前に、ガイドの作成を完了する必要があります。

### <a name="authoring-the-guide"></a>ガイドの作成

このクイック検証のために多くのことを行う必要はない。 PC で準備したガイドを選択します。 ホログラフィック アンカーを [使用して簡単](/dynamics365/mixed-reality/guides/hololens-app-anchor)に検証するには、ガイド を固定する必要があります。 その後、手順と [モデル を配置する必要があります](/dynamics365/mixed-reality/guides/hololens-app-orientation)。

>[!NOTE]
> PC にログイン **し**、管理者アカウントで作成するには、オーサリング ロールがHoloLens。 オペレーター ロールは読み取り専用であり、PC アプリにアクセスできません。

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>ガイドの操作

ホログラムが配置された後は、ガイドの操作をテストできます。 
- 演算子モード **の選択**
- ガイドの手順をクリックします。

ガイドの操作方法に関する詳細なガイダンスについては、次のリソースを参照してください。

[Dynamics 365 Guides でのガイドの操作の概要](/dynamics365/mixed-reality/guides/operator-overview)

[[ステップ] カードを操作者として使用Dynamics 365 Guides](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>次のステップ 
> [!div class="nextstepaction"]
> [企業に接続されたデプロイ - 保守](hololens2-corp-connected-maintain.md)
