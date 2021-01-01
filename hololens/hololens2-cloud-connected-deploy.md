---
title: 展開ガイド - リモート アシストによるクラウド接続 HoloLens 2 の大規模な展開 - 展開
description: クラウド接続ネットワークを使用して HoloLens デバイスの登録とリモート アシストを検証する方法
keywords: HoloLens, 管理, クラウド接続, リモート アシスト, AAD, Azure AD, MDM, モバイル デバイス管理
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
ms.openlocfilehash: 2b38f4a76ee088d4f892c86de07d8f5a10d2a3bf
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253194"
---
# 展開 - クラウド接続ガイド

すべての構成が完了したので、デバイスを配布する準備が整いました。 ただし、最初にセットアップを検証する必要があります。 まず、Azure AD Join および MDM 登録プロセスを検証し、次にリモート アシストの呼び出しが可能なか確認する必要があります。

## 登録検証

Azure AD と MDM 登録用にすべてが適切に構成されたので、残りはスナップです。 以前&#39;AAD ユーザー アカウントWi-Fi接続と HoloLens デバイスの 1 つが必要です。

デバイスが現在&#39;設定の状態ではない場合は、デバイスを再フラッシュする良 [い時期です](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)。

1. デバイスが OOBE に入った後、&#39;操作を開始し、プロンプトに従う必要があります。 
1. 重要なプロンプトは、この **HoloLens の所有者を尋ねらた場合に表示されます。** [ **自分の仕事または学校が所有している** ] を選択し、Azure AD資格情報を入力します。
1. 登録が成功すると&#39;PIN の設定を求めるメッセージが表示されます。 この PIN は、このユーザーのこのデバイスに固有です。 虹彩スキャン、音声データ、テレメトリ設定の入力も求め、最後に&#39;でスタート メニューを開いて OOBE を完了する方法を確認できます。
1. Mixed Reality ホームに移動したら、学習したスタート ジェスチャを使ってスタート **メニューを** 開きます。
1. 設定アプリ **を選択し** 、[システム] を選択 **します。** 表示される最初の情報&#39;デバイス名です。HoloLens 2 デバイスの場合は HOLOLENS、その後に 6 つの文字文字列が続 &quot; &quot; きます。
1. この名前をメモします。

![HoloLens 2 の設定 - 概要](./images/hololens2-settings-about.jpg)

7. デバイスが設定アプリ内の Azure ADに正常に登録されたことを確認できます。 From **Settings** select **Accounts**Access work  ->  **or school**. この画面で &quot; 、[Connected to _nameofAAD] (nameofAAD_ に接続済み) を表示して、Azure&#39;に登録AD。 接続名__ @ _nameofAAD_.onmicrosoft.com &quot; .


デバイスに Azure AD 参加を確認するには[、Azure Portal](https://portal.azure.com/#home)の Azure Active Directory デバイスすべてのデバイスから Azure Active Directory を確認し、デバイス名  ->  ****  ->  ****  ->  **** を検索します。 デバイス&#39;Azure Active Directory の一部であるのを確認できます。


![Azure Active Directory - デバイス](./images/aad-enrollment.png)

次に&#39;Microsoft Endpoint Manager 管理センターに [ログインする必要があります](https://endpoint.microsoft.com/#home)。 ログインし、[デバイス] を選択 **し、[すべての** デバイス] **を選択します**。 ここから、HoloLens デバイスの名前&#39;検索できます。 Intune に表示されている HoloLens を確認できる必要があります。

![Intune - デバイス](./images/endpoint-all-devices-enrolled.png)

## リモート アシスト通話の検証

デバイス&#39;AAD と MDM の両方に登録されているのを確認したら、&#39;リモート アシスト呼び出しを行う必要があります。 この検証では&#39;HoloLens デバイスと Windows 10 PC、および PC 用の 2 番目の Azure AD ユーザー アカウントが必要です。

この検証手順では、前回の検証手順が完了し、デバイスが登録され、Azure AD ユーザーがデバイスに登録されている必要があります。


1. お使いの PC に Microsoft Teams がインストールされていない場合は、ここで [Teams をダウンロードできます](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)。
2. HoloLens に現在サインインしているアカウントAD 2 番目の Azure アカウントを使用して Teams にサインインします。 PC にサインインすると、通話を受信する準備が整います。
3. HoloLens のロックを解除し、サインインします。
4. リモート アシスト アプリを起動するには、[スタート] メニュー **を開き、[** リモート アシスト] **を選択します**。 リモート アシストは、受信トレイ アプリとしてバンドルされているだけでなく、HoloLens 2 のスタート メニュー&#39;ピン留めされています。 スタート メニューにピン&#39;表示されていない場合は、[すべてのアプリ] の一覧を開**** いて探します。
5. リモート アシストを起動すると [、SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) を介してデバイスのユーザーを識別し、アプリにログインする必要があります。
6. アプリ内から[検索] **を選択** し、PC で 2 番目のユーザーを検索します。 通話を開始するユーザーを選択します。
7. PC から通話に応答します。

これで完了です&#39;正常に接続され、リモート アシスト呼び出しに対応しています。 次の使用など、特定のリモート アシスト機能を試してください。

- [インク注釈](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Mixed Reality でファイルとビューを共有する](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [別の HoloLens アプリでヘルプを表示する](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## 次のステップ

> [!div class="nextstepaction"]
> [クラウド接続展開 - 保守](hololens2-cloud-connected-maintain.md)