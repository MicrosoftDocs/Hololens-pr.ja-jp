---
title: 展開ガイド–リモートアシストによるクラウド接続の HoloLens 2-概要
description: クラウドに接続されたネットワーク経由で HoloLens デバイスを登録する
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
ms.openlocfilehash: ba3f826360f999a72e671166af7a19d19ce9c567
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196342"
---
# 展開ガイド–リモートアシスタンスによるクラウド接続の HoloLens 2 –概要

このガイドは、IT 担当者が組織に Microsoft HoloLens 2 デバイスを計画して展開する際の全体的な目標 (Dynamics 365 リモートアシスタンスを使用するために、それらのデバイスクラウドを組織に接続することを目的としています。 これは、さまざまな HoloLens 2 のユースケースを通じて、組織の概念実証の展開のモデルとして機能するという点に注意してください。

このガイドでは、デバイスをデバイス管理に登録する方法、必要に応じてライセンスを適用する方法、エンドユーザーがデバイスのセットアップ時にリモートアシスタンスを直ちに使用できることを検証する方法について説明します。 これを行うには、セットアップして実行するために必要なインフラストラクチャの重要な要素を把握します。これには、HoloLens 2 を使用して展開を実現します。

## このガイドの内容

このガイドには、HoloLens デバイスで組織内のリモートアシスタンスを設定するための具体的な目標があります。 その目標を達成するために必要な necessities について説明します。 この目標にフォーカスを維持するために、この展開の最適化または構成が必要な項目の削減のために、特定の準備と構成が事前に選択されます。 これらの選択肢の情報が表示され、ビジネスニーズに合わせて展開をカスタマイズできます。

これは、 [シナリオ a: クラウド接続デバイスへの展開](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)に似ています。これは、次のようなさまざまな概念展開の検証に最適なオプションです。

- 通常、インターネットとクラウドサービスへの Wi-Fi ネットワークは完全に開かれます。
- MDM の自動登録による Azure AD の参加--MDM (Intune) 管理
- ユーザーは独自の企業アカウント (AAD) でサインインする
  - デバイスごとに1つまたは複数のユーザーがサポートされる
- 特定の用途に応じてさまざまなレベルのデバイスロックダウン構成が適用されます。これは、完全に開いて単一のアプリキオスクにする場合です。

![クラウド接続のシナリオ](./images/cloud-connected-deployment-chart.png)

このガイドでは、追加のデバイス制限や構成は適用されませんが、これらのオプションをご確認いただくことをお勧めします。

## リモートアシストについて

リモートアシスタンスでは、共同作業と修理、リモート検査、知識共有、トレーニングを行うことができます。 さまざまな役割や場所のユーザーを接続することによって、リモートアシスタンスを使用する技術者は、Microsoft Teams のリモートコラボレーターとつながることができます。 ビデオ、スクリーンショット、注釈を組み合わせて、同じ場所に&#39;していないときでも、リアルタイムで問題を解決することができます。 リモートのコラボレーターは、技術者&#39;s の物理スペースを挿入して、お客様が登録を行っているときに、または HoloLens で作業しているときに、その他の役に立つ情報を挿入できます。

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## このガイドでは、次の操作を行います。

備える

> [!div class="checklist"]
> - [HoloLens 2 デバイスのインフラストラクチャの基礎について説明します。](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [AAD について詳しくは、「所有している&#39;」を参照してください。](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Id 管理と AAD アカウントを最適に設定する方法について説明します。](hololens2-cloud-connected-prepare.md#identity-management)
> - [MDM の詳細については、「準備が完了しているかどうかを&#39;する」を参照してください。](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [リモートアシストのネットワーク要件について説明します。](hololens2-cloud-connected-prepare.md#network)
> - [必要に応じて: 組織のリソースに接続する VPN](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

設定

> [!div class="checklist"]
> - [ユーザーとグループを作成する方法について説明します。](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [AAD で自動登録を設定する方法を説明します。](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [アプリケーションライセンスを割り当てる方法。](hololens2-cloud-connected-configure.md#application-licenses)

Deploy

> [!div class="checklist"]
> - [HoloLens 2 をセットアップし、登録を確認します。](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [リモートアシスタンス通話を発信できることを確認します。](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

維持

> [!div class="checklist"]
> - [Microsoft Store アプリを使ってリモートアシスタンスを更新する方法を説明します。](hololens2-cloud-connected-maintain.md#updates)
> - [サポート計画を作成します。](hololens2-cloud-connected-maintain.md#support-plan)
> - [開発計画。](hololens2-cloud-connected-maintain.md#development-plan)

## 次のステップ

> [!div class="nextstepaction"]
> [クラウド接続の展開-準備](hololens2-cloud-connected-prepare.md)

