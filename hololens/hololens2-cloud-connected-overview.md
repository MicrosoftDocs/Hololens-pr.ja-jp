---
title: 展開ガイド - リモート アシスト付きのクラウド接続 HoloLens 2 - 概要
description: クラウド接続ネットワークを使用して HoloLens デバイスを登録する
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
ms.openlocfilehash: 7d954347c7c274b844d436c0d6fc96e8bbc59f10
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253184"
---
# 展開ガイド - リモート アシスト付きのクラウド接続 HoloLens 2 – 概要

このガイドは、Dynamics 365 リモート アシストを使用してこれらのデバイスを組織に接続する全体的な目標を達成し、IT 担当者が Microsoft HoloLens 2 デバイスを計画して組織に展開する場合に役立ちます。 これは、さまざまな HoloLens 2 の使用事例にわたって組織に概念実証を展開するモデルとして機能します。

このガイドでは、デバイスをデバイス管理に登録し、必要に応じてライセンスを適用し、エンド ユーザーがデバイスのセットアップ時にリモート アシストをすぐに使用できるのを検証する方法について説明します。 これを行うには、HoloLens 2 を使用して大規模な展開を実現するために、セットアップと実行に必要な重要なインフラストラクチャについて説明します。

## このガイドの情報

このガイドには、組織内で HoloLens デバイスにリモート アシストをセットアップする具体的な目標があります。 その目標を達成するために必要な情報を扱います。 この目標に集中するために、この展開を最適化したり、構成に必要な項目を減らしたりするために、特定の準備と構成を事前に選択します。 これらの選択肢が通知され、ビジネス ニーズに基づいて展開をカスタマイズできます。

これは、シナリオ [A:](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)クラウド接続デバイスへの展開に似た設定です。これは、概念実証の多くの展開に最適なオプションです。これには、次のものが含まれます。

- Wi-Fiネットワークは、通常、インターネットサービスとクラウド サービスに完全に開いている
- Azure AD MDM 自動登録を使用した参加 - MDM (Intune) 管理
- ユーザーが自分の会社のアカウントでサインインする (Azure AD)
  - サポートされているデバイスごとに 1 人または複数のユーザー
- さまざまなレベルのデバイス ロックダウン構成が、完全に開いているアプリからシングル アプリ キオスクまで、特定の使用例に基づいて適用されます。

![クラウド接続シナリオ](./images/cloud-connected-deployment-chart.png)

このガイドでは、他のデバイスの制限や構成は適用されませんが、終了後にこれらのオプションを確認してください。

## リモート アシストについて

リモート アシストを使用すると、共同作業による保守と修復、リモート検査、知識の共有とトレーニングが可能になります。 リモート アシストを使用して技術者と異なる役割や場所のユーザーを接続すると、Microsoft Teams のリモート共同作業者と接続できます。 ビデオ、スクリーンショット、注釈を組み合わせて、問題が同じ場所になくても&#39;をリアルタイムで解決できます。 リモート共同作業者は、HoloLens でヘッドアップとハンズフリーの作業を行っている間に、技術者&#39;の物理空間に参照イメージ、概略図、その他の有用な情報を挿入できます。

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## このガイドでは、次の方法を行います。

準備:

> [!div class="checklist"]
> - [HoloLens 2 デバイスのインフラストラクチャの基本について学習します。](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Azure ADについてAD、必要ない場合はセットアップ&#39;確認してください。](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [ID 管理と、Azure アカウントを最適にセットアップする方法ADします。](hololens2-cloud-connected-prepare.md#identity-management)
> - [MDM について詳しく知り、まだ準備ができていない場合は Intune&#39;セットアップしてください。](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [リモート アシストのネットワーク要件について説明します。](hololens2-cloud-connected-prepare.md#network)
> - [オプション: 組織のリソースに接続するための VPN](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

次の構成を行います。

> [!div class="checklist"]
> - [ユーザーとグループを作成する方法。](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Azure AD 内で自動登録をセットアップする方法。](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [アプリケーション ライセンスを割り当てる方法。](hololens2-cloud-connected-configure.md#application-licenses)

展開:

> [!div class="checklist"]
> - [HoloLens 2 をセットアップし、登録を検証します。](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [リモート アシスト呼び出しを行う可能性を検証します。](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

次の保守を行います。

> [!div class="checklist"]
> - [Microsoft Store アプリを使ってリモート アシストを更新する方法。](hololens2-cloud-connected-maintain.md#updates)
> - [サポート計画の作成。](hololens2-cloud-connected-maintain.md#support-plan)
> - [開発計画。](hololens2-cloud-connected-maintain.md#development-plan)

## 次のステップ

> [!div class="nextstepaction"]
> [クラウド接続展開 - 準備](hololens2-cloud-connected-prepare.md)

