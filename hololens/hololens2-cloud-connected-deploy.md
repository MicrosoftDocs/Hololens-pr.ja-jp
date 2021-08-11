---
title: デプロイガイド–リモートアシスタンスを使用した大規模なクラウド接続 HoloLens 2 デプロイ
description: クラウドに接続されたネットワーク経由で HoloLens デバイスの登録とリモートアシスタンスを検証する方法について説明します。
keywords: HoloLens、管理、クラウド接続、リモートアシスタンス、AAD、Azure AD、MDM、モバイルデバイス管理
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
ms.openlocfilehash: 593dc65ab97eaae65591a5239cd0a978750eac9fa538364ba6bbc7ef0a2a08a4
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660511"
---
# <a name="deploy---cloud-connected-guide"></a>デプロイ-クラウド接続ガイド

すべての構成が完了したので、デバイスを配布する準備ができました。 ただし、ここでは、最初にセットアップを検証する必要があります。 まず、Azure AD 参加と MDM 登録プロセスを検証した後、リモートアシスタンスの呼び出しを配置できることを確認する必要があります。

## <a name="enrollment-validation"></a>登録の検証

これで、Azure AD と MDM 登録のすべてが正しく構成されたので、残りはスナップになります。 Wi-Fi 接続と HoloLens デバイス、および以前に構成した AAD ユーザーアカウントのいずれかが必要&#39;ます。

現在、デバイスが工場出荷時の設定状態に&#39;ていない場合は、ここで [デバイスを更新](/hololens/hololens-recovery#clean-reflash-the-device)することをお勧めします。

1. デバイスが OOBE になったら、操作を開始し、プロンプトに従って操作を開始する必要が&#39;ます。 
1. **この HoloLens を所有 Who** ことを確認するメッセージが表示されます。 [ **職場または学校が所有** する] を選択し、Azure AD アカウントの資格情報を入力します。
1. 登録が成功すると、PIN の設定を求められ&#39;ます。 この PIN は、このユーザーに対してこのデバイスに固有のものです。 また、虹彩スキャン、音声データ、テレメトリの設定を求められます。最後に、[スタート] メニューを開き、OOBE を完了する方法を学習でき&#39;ます。
1. Mixed Reality ホームに移動したら、学習した **開始ジェスチャ** を使用してスタートメニューを開きます。
1. **設定** アプリを選択し、[システム] を選択し **ます。** &#39;最初に表示される情報は、デバイス名です。これは、HoloLens 2 デバイスの場合は &quot; HoloLens- &quot; その後に6文字の文字列が続きます。
1. この名前をメモしておきます。

![HoloLens 2 設定](./images/hololens2-settings-about.jpg)

7. デバイスが設定アプリ内の Azure AD に正常に登録されていることを確認できます。 **設定**[   ->  **職場または学校にアクセス** するアカウント] を選択します。 この画面では、 &quot; _Nameofaad_&#39;s Azure AD に接続されていることを確認して、正常に登録されたことを確認できます。 _ユーザー名_ @ _nameofaad_ によって接続され &quot; ます。


デバイスが参加して Azure AD かどうかを検証するには、[ [Azure portal](https://portal.azure.com/#home)  ->  **Azure Active Directory** デバイスのすべてのデバイス] から Azure Active Directory を確認  ->    ->  し、デバイス名を検索します。 デバイスが Azure Active Directory の一部であることを確認でき&#39;ます。


![Azure Active Directory-デバイス](./images/aad-enrollment.png)

次に&#39;[Microsoft エンドポイントマネージャー管理センター](https://endpoint.microsoft.com/#home)にログインする必要があります。 ログインし、[ **デバイス** ]、[ **すべてのデバイス**] の順に選択します。 ここから、HoloLens デバイス&#39;s 名を検索できます。 HoloLens が Intune に一覧表示されます。

![Intune-デバイス](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>リモートアシスタンス呼び出しの検証

デバイスが AAD と MDM の両方に登録されていることを確認したら、テストリモートアシスタンス呼び出しを行う時間を&#39;&#39;ます。 この検証では、HoloLens デバイスと Windows 10 pc、および pc の2つ目の Azure AD ユーザーアカウントが必要&#39;ます。

この検証手順では、前回の検証手順が既に完了していて、デバイスが登録されていて、Azure AD ユーザーがデバイス上にあることを前提としています。


1. PC にまだ Microsoft Teams がインストールされていない場合は、[こちら Teams をダウンロード](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)できます。
2. HoloLens に現在サインインしているユーザーアカウントとは別の Azure AD ユーザーアカウントを使用して Teams サインインします。 PC にサインインすると、電話を受ける準備が整います。
3. HoloLens のロックを解除してサインインします。
4. リモートアシスタンスアプリを起動するには、[ **スタート] メニュー** を開き、[ **リモート** アシスタンス] を選択します。 リモートアシスタンスは、受信トレイアプリとしてのみバンドルされていますが、HoloLens 2&#39;s スタートメニューにピン留めされています。 イベントでは、スタートメニューにピン留めされていない&#39;、[**すべてのアプリ**] の一覧を開いて検索します。
5. リモートアシスタンスが開始されると、 [SSO](/azure/active-directory/manage-apps/what-is-single-sign-on) 経由でデバイスのユーザーを識別し、アプリにログインする必要があります。
6. アプリ内で [ **検索** ] を選択し、PC で2番目のユーザーを検索します。 呼び出しを開始するユーザーを選択します。
7. PC から通話に応答します。

正常に接続されましたが、リモートアシスタンスの電話に&#39;ます。 次のような特定のリモートアシスタンス機能を試してみてください。

- [インク注釈](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [ファイルとビューを mixed reality で共有する](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [別の HoloLens アプリのヘルプを取得する](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>次のステップ

> [!div class="nextstepaction"]
> [クラウドに接続されたデプロイ-管理](hololens2-cloud-connected-maintain.md)