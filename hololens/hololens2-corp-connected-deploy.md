---
title: 展開ガイド – Dynamics 365 ガイドを使用した企業接続 HoloLens 2 - 展開
description: Dynamics 365 ガイドを使用して企業の接続ネットワークを使用して HoloLens 2 デバイスの展開をセットアップする方法について説明します。
keywords: HoloLens、管理、企業接続、Dynamics 365 ガイド、AAD、Azure AD、MDM、モバイル デバイス管理
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
ms.openlocfilehash: febf56f94a5cab623fd7ad08ae7abf7050224717
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448587"
---
# <a name="deploy---corporate-connected-guide"></a>展開 - 企業向けコネクテッド ガイド

各展開の重要な部分は、エンド ユーザーのスムーズなエクスペリエンスを確保するために、展開を自分でテストする前に、展開が適切にセットアップされていることを確認する点です。

MDM を介して Wi-Fi 証明書を展開する場合、最初に HoloLens をセットアップし、開いている Wi-Fi ネットワークまたは証明書を必要としないネットワークにデバイスを登録する必要があります。 HoloLens が OOBE と登録を完了すると、デバイスは以前に構成されたネットワーク証明書と LOB を受け取り、両方がデバイスによって受信されたのを検証できます。

その後、テスト ガイドを作成して操作できると確認できます。

## <a name="enrollment-validation"></a>登録の検証

Azure AD MDM 登録用にすべてが適切に構成されたので、残りはスナップになるはずです。 接続と HoloLens Wi-Fi、以前に構成された Azure ユーザー アカウントの 1 つADがあります。

デバイスが現在工場出荷時の設定状態に座ってない場合は、デバイスを再フラッシュ [する良い時期になります](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)。

1. デバイスが OOBE に入った後、プロンプトの操作と実行を開始する必要があります。

2. Wi-Fi に参加Wi-Fi証明書を必要としない開いているネットワークに接続します。 これにより、デバイスは、初期セットアップ後に組織のサーバーで使用するWi-Fiダウンロードできます。

3. 重要なプロンプトは、この HoloLens を所有しているユーザーを **確認するメッセージが表示されます。** [ **自分の仕事または学校が所有している] を選択し** 、Azure アカウントAD入力します。

4. 登録が成功すると、PIN の設定を求めるメッセージが表示されます。 この PIN は、このユーザーのこのデバイスに固有です。 また、Iris スキャン、音声データ、テレメトリ設定を求めるメッセージが表示され、最後にスタート メニューを開いて OOBE を完了する方法を学習できます。

5. Mixed Reality Home に着陸したら、学習したスタート ジェスチャを使用して **[スタート** ] メニューを開きます。

6. [設定] **アプリを選択** し、[システム] を **選択します**。 表示される情報の最初の部分はデバイス名です。HoloLens 2 デバイスの場合は HOLOLENS で、その後に 6 文字の文字列が &quot; &quot; 続きます。

7. この名前をメモします。

    ![HoloLens 2 [設定] 画面](./images/hololens2-settings-about.jpg)

8. デバイスが Azure サーバーに正常に参加AD。 2 つの方法があります。

    1.  設定アプリ。 [設定 **] から 、[** アカウント**アクセス**  ->  **の作業時間または学校] を選択します**。 この画面から、「接続済み nameofAAD」を参照して、正常に登録されたことを確認&#39;&quot; Azure AD。 によって接続** yourusername@nameofAAD.onmicrosoft.com。 これにより、デバイスが組織の Azure サーバーに参加&#39;確認AD。

    1. [Azure portal](https://portal.azure.com/#home). [Azure **Active Directory**  ->  **Devices] [**  ->  **すべてのデバイス] に移動**し、デバイス名を検索します。 [参加の種類] の下に、'Azure AD' と表示されます。
        ![Azure サーバーで参加の種類を確認AD](./images/hololens2-devices-all-devices.png)

9. デバイスが MDM に登録されているのを確認します。 2 つの方法があります。

    1. [設定 **] から**、[アカウント**アクセスの**  ->  **仕事または学校] を選択します**。 この画面から、「接続済み nameofAAD」を参照して、正常に登録されたことを確認&#39;&quot; Azure AD。 によって接続** yourusername@nameofAAD.onmicrosoft.com。 この Access の仕事または学校のアカウントで、[nameofAAD に接続] を選択&#39;&quot; Azure AD。 [情報] &quot; yourusername@nameofAAD.onmicrosoft.com[情報] ボタンを **選択** します。

    1. [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home). ログインし、[デバイス] 、[**すべてのデバイス****] の順に選択します**。 ここから、HoloLens デバイスの名前&#39;検索できます。 HoloLens が Intune に一覧表示されているのを確認できる必要があります。

        ![Azure の Intune によって管理されるAD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi証明書の検証

これで、デバイスは証明書を受け取Wi-Fiがあります。 最も簡単な検証は、証明書を受け取ったWi-Fi接続&#39;試みです。 [設定] アプリ**を開**き **、[ &amp; ネットワーク**インターネット  ->  **Wi-Fi] に移動し、Wi-Fi**接続を選択します。 接続が完了したら、Microsoft Edge アプリを開き、Web サイトに移動できます。

デバイスで証明書を受信したと確認するには、証明書マネージャーを [使用します](https://docs.microsoft.com/hololens/certificate-manager)。

## <a name="validate-lob-app-install"></a>LOB アプリのインストールを検証する

管理アプリのインストールの進行状況を確認するには、アプリがインストールされているのか、[設定] を確認します。 LOB アプリをグループの必須インストールとして構成することで、HoloLens を割り当てられたグループのユーザーと登録した後、アプリは HoloLens に自動的にダウンロードされます。

[スタート] メニューを開き、[すべてのアプリ **] を選択します**。 アプリの数によっては、ページの上ボタンまたはページダウン ボタンを使用******する必要**があります。

デバイス上のアプリのインストールを検証するには、Settings ****  ->  ****  ->  **Accounts Access****** の作業または学校から行い、アカウントの [情報] ボタンを選択し、下にスクロールして MDM からデバイスに適用されるさまざまな構成とアプリを確認します。

Intune からインストールを検証するには[、MEM](https://endpoint.microsoft.com/#home)ポータル アプリ  ->  ****-> [すべての**** アプリ]  -> *TheNameOfYourApp*デバイスのインストール状態ページ  ->  **に移動**します。

詳細: [HoloLens 用 Intune アプリの展開](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Dynamics 365 ガイドの検証

HoloLens のガイド アプリには、オーサリングと操作のモードがあります。 ガイドを操作する前に、ガイドの作成を完了する必要があります。

### <a name="authoring-the-guide"></a>ガイドの作成

この迅速な検証のために多くのことを行う必要はない。 PC で準備したガイドを選択します。 ガイドをアンカーする必要 [があります](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor)。簡単な検証のためには、ホログラフィック アンカーを使用できます。 その後、手順と [モデルを配置する必要があります](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation)。

>[!NOTE]
> HoloLens **で** PC と作成者にログインするには、オーサリング ロールが必要です。 Operator ロールは読み取り専用で、PC アプリにアクセスできません。

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>ガイドの操作

ホログラムを配置したら、ガイドの操作をテストできます。 
- [演算子 **モードの選択]**
- ガイドの手順をクリックします。

ガイドの操作方法に関する詳細なガイダンスについては、次のリソースを参照してください。

[Dynamics 365 ガイドでのガイドの操作の概要](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-overview)

[Dynamics 365 Guides で Step カードをオペレーターとして使用する](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>次の手順 
> [!div class="nextstepaction"]
> [企業の接続展開 - メンテナンス](hololens2-corp-connected-maintain.md)
