---
title: 展開ガイド–リモートアシスタンスでの展開による、クラウド接続型 HoloLens 2 展開
description: クラウドに接続されたネットワーク経由で HoloLens デバイスの登録およびリモートアシストを検証する方法
keywords: HoloLens、管理、クラウド接続、リモートアシスト、AAD、Azure AD、MDM、モバイルデバイス管理
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 4f4f787d6db16655d5fe3b54438a4524bc9df78f
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196343"
---
# 展開-クラウド接続ガイド

これですべての設定が完了したので、デバイスを配布する準備ができました。 ただし、まず設定を検証する必要があります。 まず、AAD の参加と MDM の登録プロセスを検証し、次にリモートアシスタンスの通話を配置できることを確認します。

## 登録の検証

AAD と MDM の登録に適切に構成されたすべての機能がスナップになります。 &#39;には、Wi-Fi 接続と HoloLens デバイスと、以前に構成された AAD ユーザーアカウントのいずれかが必要です。

現在出荷時の設定状態になっているデバイスが&#39;いない場合は、 [デバイスを reflash](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)することをお勧めします。

1. デバイスが OOBE に表示されたら、操作を開始して、画面の指示に従う必要が&#39;ます。 
1. **この HoloLens の所有者**をたずねるメッセージが表示されますか? **自分の職場または学校**を選択して、AAD アカウントの資格情報を入力します。
1. 登録に成功すると、PIN を設定するように求められ&#39;ます。 これは、このユーザのデバイスに固有のものです。 また、虹彩スキャン、音声データ、テレメトリ設定の入力を求められます。最後に、[スタート] メニューを開き、OOBE を完了する方法についても説明します&#39;。
1. Mixed Reality ホームに着陸したら、直前に学習した **開始ジェスチャ** を使って [スタート] メニューを開きます。 
1. [ **設定** ] アプリを選択し、[システム] を選択し **ます。** &#39;最初に表示される情報には、お使いのデバイス名が表示されます。 HoloLens 2 デバイスの場合は、 &quot; hololens- &quot; 6 文字の文字列が続きます。 
1. この名前はメモしておいてください。

![HoloLens 2 の設定-バージョン情報](./images/hololens2-settings-about.jpg)

7. デバイスが設定アプリ内で AAD に正常に登録されていることを確認できます。 [**設定**] で、[**アカウント**  ->  **アクセスの職場または学校**] を選択します。 この画面から、 &quot; _Nameofaad_&#39;s Azure AD に接続していることを確認できます。 _ユーザー名_名 onmicrosoft.com によって接続されている @ _nameofAAD_ &quot; 。

デバイスで AAD が結合されていることを確認するには、azure [Portal](https://portal.azure.com/#home)  ->  **azure active directory**デバイスのすべてのデバイスから azure active directory を確認  ->  **Devices**  ->  **All devices**し、デバイス名を検索します。 &#39;、デバイスが Azure Active Directory の一部であることを確認できます。

![Azure Active Directory-デバイス](./images/aad-enrollment.png)

次に、&#39;[Microsoft Endpoint Manager 管理センター](https://endpoint.microsoft.com/#home)にログインする必要があります。 ログインして、[ **デバイス** ]、[ **すべてのデバイス**] の順に選択します。 ここから、HoloLens デバイス&#39;s 名を検索できます。 Intune に、HoloLens が一覧表示されます。

![Intune デバイス](./images/endpoint-all-devices-enrolled.png)

## リモートアシスタンス通話の検証

お使いのデバイスが AAD と MDM の両方に登録されていることを確認した&#39;、テストリモートアシスタンス通話を発信する時間を&#39;します。 この検証を&#39;行うには、HoloLens デバイスと Windows 10 PC、および PC 用の2つ目の AAD ユーザーアカウントが必要です。

この検証手順では、前回の検証手順を行っていて、デバイスが登録されており、AAD ユーザーがデバイスにあることを前提としています。

1. PC に Microsoft Teams をまだインストールしていない&#39;は、 [ここからチームをダウンロード](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)できます。
2. 現在 HoloLens にサインインしているユーザーとは別の AAD ユーザーアカウントを使用して、チームにサインインします。 PC にサインインすると、通話を受信できるようになります。
3. HoloLens のロックを解除してサインインします。
4. リモートアシスタンスアプリを起動するには、[ **スタート] メニュー** を開き、[ **リモートアシスト**] を選びます。 リモートアシスタンスは、受信トレイアプリとしてバンドルされるだけでなく、HoloLens 2&#39;s の [スタート] メニューに固定されています。 イベントでは、[スタート] メニューにピン留めされていることを確認し&#39;、[ **すべてのアプリ** ] の一覧を開いて探します。
5. リモートアシスタンスが開始されると、 [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) 経由でデバイスのユーザーを特定して、アプリにログインする必要があります。
6. アプリ内で、[ **検索** ] を選び、PC 上の2番目のユーザーを検索します。 通話を開始するユーザーを選択します。
7. PC から通話に応答します。

お客さまの&#39;が正常に接続されました。リモートアシスタンス通話を利用しています。 次のようなリモートアシスト機能を使用してください。

- [手書き入力の注釈](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Mixed reality でファイルを共有して表示する](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [別の HoloLens アプリのヘルプを表示する](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## 次のステップ

> [!div class="nextstepaction"]
> [クラウド接続の展開-管理](hololens2-cloud-connected-maintain.md)