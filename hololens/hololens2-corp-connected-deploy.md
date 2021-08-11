---
title: 展開ガイド– Dynamics 365 Guides による企業接続 HoloLens 2
description: Dynamics 365 Guides を使用して、企業に接続されたネットワーク経由で HoloLens 2 デバイスの展開を設定する方法について説明します。
keywords: HoloLens、管理、企業接続、Dynamics 365 Guides、AAD、Azure AD、MDM、モバイルデバイス管理
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
ms.openlocfilehash: f9435ce94986a851bb7744eeea48fa6e411454f5090d7ae11c869ba6f27dc942
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660205"
---
# <a name="deploy---corporate-connected-guide"></a>デプロイ-企業接続ガイド

各デプロイの重要な部分は、エンドユーザーに対して円滑なエクスペリエンスを確保するために、自分でテストする前に、デプロイが適切に設定されていることを確認することです。

MDM 経由で Wi-Fi 証明書をデプロイしているため、最初に HoloLens を設定し、開いている Wi-Fi ネットワークまたは証明書を必要としないネットワークにデバイスを登録する必要があります。 HoloLens が OOBE を完了し、登録されると、デバイスは以前に構成したネットワーク証明書と LOB を受信します。デバイスが受信した両方の検証を行うことができます。

その後、テストガイドの作成と操作の両方ができることを確認できます。

## <a name="enrollment-validation"></a>登録の検証

これで、Azure AD と MDM 登録のすべてが正しく構成されたので、残りはスナップになります。 Wi-Fi 接続と HoloLens デバイス、および以前に構成した Azure AD ユーザーアカウントのいずれかが必要です。

現在デバイスが工場出荷時の設定状態になっていない場合は、ここで [デバイスを更新](/hololens/hololens-recovery#clean-reflash-the-device)することをお勧めします。

1. デバイスが OOBE になったら、操作を開始し、プロンプトに従って操作を開始する必要があります。

2. wi-fi に参加するために証明書を必要としない、開いている Wi-Fi ネットワークに Connect します。 これにより、初期セットアップ後に、デバイスが組織の Wi-Fi で使用する証明書をダウンロードできるようになります。

3. **この HoloLens を所有 Who** ことを確認するメッセージが表示されます。 [ **職場または学校が所有** する] を選択し、Azure AD アカウントの資格情報を入力します。

4. 登録が成功すると、PIN の設定を求められます。 この PIN は、このユーザーに対してこのデバイスに固有のものです。 また、虹彩スキャン、音声データ、テレメトリの設定を求められます。最後に、[スタート] メニューを開き、OOBE を完了する方法を学習できます。

5. Mixed Reality ホームに移動したら、学習した **開始ジェスチャ** を使用してスタートメニューを開きます。

6. **設定** アプリを選択し、[**システム**] を選択します。 最初に表示される情報は、デバイス名です。 HoloLens 2 デバイスの場合は、 &quot; HoloLens- &quot; 6 文字の文字列が続きます。

7. この名前をメモしておきます。

    ![HoloLens 2 設定画面](./images/hololens2-settings-about.jpg)

8. デバイスが Azure AD に正常に参加していることを確認します。 2つの方法があります。

    1.  設定アプリ。 **設定**[   ->  **職場または学校にアクセス** するアカウント] を選択します。 この画面では、 &quot; nameofAAD&#39;s Azure AD に接続されていることを確認して、正常に登録されたことを確認できます。 接続 *yourusername@nameofAAD.onmicrosoft.com* します。 これにより、デバイスが組織&#39;s Azure AD に参加していることが確認されます。

    1. [Azure ポータル](https://portal.azure.com/#home)。 [ **Azure Active Directory**  ->  **デバイス**  ->  ] [**すべてのデバイス**] にアクセスし、デバイス名を検索します。 [結合の種類] では、"Azure AD" 結合 "として表示されます。
        ![Azure AD での結合の種類の確認](./images/hololens2-devices-all-devices.png)

9. デバイスが MDM に登録されていることを確認します。 2つの方法があります。

    1. **設定** で、[**アカウント**] [  ->  **職場または学校にアクセス** する] を選択します。 この画面では、 &quot; nameofAAD&#39;s Azure AD に接続されていることを確認して、正常に登録されたことを確認できます。 接続 *yourusername@nameofAAD.onmicrosoft.com* します。 この職場または学校アカウントから、[ &quot; nameofAAD&#39;s に接続] を選択して Azure AD します。 によって接続され yourusername@nameofAAD.onmicrosoft.com &quot; 、[**情報**] ボタンを選択します。

    1. [Microsoft エンドポイントマネージャー管理センター](https://endpoint.microsoft.com/#home)。 ログインし、[  **デバイス**  ]、[  **すべてのデバイス**] の順に選択します。 ここから、HoloLens デバイス&#39;s 名を検索できます。 HoloLens が Intune に一覧表示されます。

        ![Azure AD で Intune によって管理されていることを確認する](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>証明書の検証の Wi-Fi

これで、デバイスは Wi-Fi 証明書を受信しました。 最も簡単な検証は、証明書を受信した Wi-Fi&#39;接続への接続を試みることです。 **設定** アプリを開き、[ネットワーク] **[ &amp; インターネット**] [wi-fi] の順に移動して  ->   、[wi-fi 接続] を選択します。 接続したら、Microsoft Edge アプリを開き、web サイトに移動できることを確認します。

デバイスで証明書を受信したことを確認するには、 [証明書マネージャー](/hololens/certificate-manager)を使用します。

## <a name="validate-lob-app-install"></a>LOB アプリのインストールの検証

マネージアプリのインストールの進行状況を表示するには、アプリがインストールされているかどうかを確認するか、設定を確認します。 LOB アプリをグループの必須のインストールとして構成することにより、割り当てられたグループのユーザーに HoloLens を登録した後、アプリが HoloLens に自動的にダウンロードされます。

スタートメニューを開き、[**すべてのアプリ**] を選択します。 使用しているアプリの数によっては、[pageup **]** ボタンまたは [ **pagedown] ボタン** の使用が必要になる場合があります。

デバイスでのアプリのインストールを検証するには、職場または学校にアクセスする **設定** アカウントを使用してアカウントを選択し、  ->    ->  [**情報**] ボタンをクリックして下にスクロールし、MDM からデバイスに適用されているさまざまな構成とアプリを表示します。

Intune からインストールを検証するには、[[メモリポータル](https://endpoint.microsoft.com/#home)  ->  **アプリ**-> すべての **アプリ**]  -> *TheNameOfYourApp*[  ->  **デバイスのインストール状態**] ページに移動します。

詳細については[、「HoloLens の Intune アプリの展開」を](/hololens/app-deploy-intune)参照してください。

## <a name="validate-dynamics-365-guides"></a>Dynamics 365 Guides の検証

HoloLens のガイドアプリには、作成と操作のためのモードが用意されています。 運用する前に、ガイドの作成を完了する必要があります。

### <a name="authoring-the-guide"></a>ガイドを作成する

このクイック検証については、あまり必要ありません。 PC で準備した番組ガイドを選択するだけです。 [ガイドを固定](/dynamics365/mixed-reality/guides/hololens-app-anchor)する必要があります。簡単な検証を行うには、holographic アンカーを使用します。 その後、 [ステップとモデルを配置](/dynamics365/mixed-reality/guides/hololens-app-orientation)する必要があります。

>[!NOTE]
> PC にログインして HoloLens に作成するには、**オーサリング** ロールが必要です。 オペレーターロールは読み取り専用で、PC アプリへのアクセス権はありません。

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>ガイドを操作する

ホログラムが配置されたら、ガイドの操作をテストできます。 
- **オペレーターモード** の選択
- ガイドの手順をクリックします。

ガイドを操作する方法の詳細なガイダンスについては、次のリソースを参照してください。

[Dynamics 365 Guides でのガイドの運用の概要](/dynamics365/mixed-reality/guides/operator-overview)

[ステップカードを Dynamics 365 Guides の演算子として取得します。](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>次のステップ 
> [!div class="nextstepaction"]
> [企業に接続された展開-管理](hololens2-corp-connected-maintain.md)
