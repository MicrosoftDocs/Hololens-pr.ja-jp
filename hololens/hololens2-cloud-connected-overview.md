---
title: リモートアシスタンスを使用したクラウド接続型 HoloLens 2 の概要
description: Dynamics 365 Remote Assist を使用して、クラウドに接続されたネットワーク上に HoloLens 2 デバイスを登録する方法について説明します。
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
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397653"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>展開ガイド–リモートアシスタンスを使用したクラウド接続型 HoloLens 2 –概要

このガイドは、IT プロフェッショナルが Microsoft HoloLens 2 デバイスを組織に接続する際の全体的な目標を計画し、組織に展開するのに役立ちます。これらのデバイスは、Dynamics 365 リモートアシスタンスを使用する準備が整っている組織に接続されています。 これは、さまざまな HoloLens 2 ユースケースで組織に対する概念実証展開のモデルとして機能することに注意してください。

このガイドでは、デバイスをデバイス管理に登録する方法、必要に応じてライセンスを適用する方法、およびエンドユーザーがデバイスのセットアップ時にリモートアシスタンスをすぐに使用できることを検証する方法について説明します。 これを行うには、設定と実行に必要なインフラストラクチャの重要な部分について説明します。これは、HoloLens 2 を使用した大規模なデプロイを実現するために必要です。

[![クラウド接続シナリオ ](./images/deployment-guides-revised-scenario-a.png)](./images/deployment-guides-revised-scenario-a.png#lightbox)
## <a name="in-this-guide"></a>このガイドの内容

このガイドには、お客様の HoloLens デバイスで組織内にリモートアシスタンスを設定するための特定の目標があります。 この目標を達成するために必要な virtual-machines-windows-classic-ps-sql-alwayson-availability-groups について説明します。 この目標に焦点を当てるために、この展開を最適化するため、または構成する必要がある項目を減らすために、特定の準備と構成があらかじめ選択されています。 これらの選択が通知され、ビジネスニーズに基づいてデプロイをカスタマイズできるようになります。

これは、 [シナリオ a: クラウド接続デバイスへのデプロイ](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)に似ています。これは、多くの概念実証展開に適しています。これには、次のようなものが含まれます。

- Wi-Fi ネットワークは、通常、インターネットおよびクラウドサービスに対して完全に開いています。
- MDM の自動登録による Azure AD 参加--MDM (Intune) で管理
- ユーザーが自分の会社のアカウントでサインインする (Azure AD)
  - デバイスごとに1つまたは複数のユーザーがサポートされています
- デバイス ロックダウン構成のさまざまなレベルが、フル オープンからシングル アプリ キオスクまで、特定の使用事例に基づいて適用されます



このガイドでは、他のデバイスの制限や構成は適用されませんが、完了した後でこれらのオプションを確認してください。

## <a name="learn-about-remote-assist"></a>詳細については、Remote Assist

Remote Assist、共同作業によるメンテナンスと修復、リモート検査、ナレッジの共有とトレーニングが可能になります。 さまざまな役割と場所のユーザーを接続することで、Remote Assistを使用して、Microsoft Teams のリモート コラボレーターと接続できます。 ビデオ、スクリーンショット、注釈を組み合わせて、問題が同じ場所になくても&#39;をリアルタイムで解決できます。 リモート コラボレーターは、HoloLens でヘッドアップとハンズフリーの作業を行っている間に、技術者&#39;の物理空間に参照画像、概略図、その他の役に立つ情報を挿入できます。

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a>このガイドで行うこと:

準備:

> [!div class="checklist"]
> - [デバイスのインフラストラクチャの基本についてHoloLens 2します。](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [詳細については、Azure AD設定する必要がある場合は、&#39;してください。](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [ID 管理と、アカウントを最適に設定する方法Azure AD説明します。](hololens2-cloud-connected-prepare.md#identity-management)
> - [MDM の詳細を確認し、まだ準備ができていない場合&#39;Intune で設定します。](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [アプリケーションのネットワーク要件についてRemote Assist。](hololens2-cloud-connected-prepare.md#network)
> - [必要に応じて、組織のリソースに接続するための VPN](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

以下を構成します。

> [!div class="checklist"]
> - [ユーザーとグループを作成する方法。](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [データ 内で自動登録を設定するAzure AD。](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [アプリケーション ライセンスを割り当てる方法。](hololens2-cloud-connected-configure.md#application-licenses)

展開: 

> [!div class="checklist"]
> - [登録を設定しHoloLens 2を検証します。](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [呼び出しを行Remote Assist検証します。](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

保守:

> [!div class="checklist"]
> - [アプリを使用してRemote Assistを更新Microsoft Store方法。](hololens2-cloud-connected-maintain.md#updates)
> - [サポート プランを作成する。](hololens2-cloud-connected-maintain.md#support-plan)
> - [開発計画。](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>次のステップ

> [!div class="nextstepaction"]
> [クラウドに接続されたデプロイ-準備](hololens2-cloud-connected-prepare.md)

