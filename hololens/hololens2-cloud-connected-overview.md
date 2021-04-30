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
ms.openlocfilehash: 69b31657a7efaebd5b25b742023dc8767f9c5038
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309112"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>展開ガイド–リモートアシスタンスを使用したクラウド接続型 HoloLens 2 –概要

このガイドは、IT プロフェッショナルが Microsoft HoloLens 2 デバイスを組織に接続する際の全体的な目標を計画し、組織に展開するのに役立ちます。これらのデバイスは、Dynamics 365 リモートアシスタンスを使用する準備が整っている組織に接続されています。 これは、さまざまな HoloLens 2 ユースケースで組織に対する概念実証展開のモデルとして機能することに注意してください。

このガイドでは、デバイスをデバイス管理に登録する方法、必要に応じてライセンスを適用する方法、およびエンドユーザーがデバイスのセットアップ時にリモートアシスタンスをすぐに使用できることを検証する方法について説明します。 これを行うには、設定と実行に必要なインフラストラクチャの重要な部分について説明します。これは、HoloLens 2 を使用した大規模なデプロイを実現するために必要です。

![クラウドに接続されたバナー](./images/cloud-connected-hololens-large.png)

## <a name="in-this-guide"></a>このガイドの内容

このガイドには、お客様の HoloLens デバイスで組織内にリモートアシスタンスを設定するための特定の目標があります。 この目標を達成するために必要な virtual-machines-windows-classic-ps-sql-alwayson-availability-groups について説明します。 この目標に焦点を当てるために、この展開を最適化するため、または構成する必要がある項目を減らすために、特定の準備と構成があらかじめ選択されています。 これらの選択が通知され、ビジネスニーズに基づいてデプロイをカスタマイズできるようになります。

これは、 [シナリオ a: クラウド接続デバイスへのデプロイ](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)に似ています。これは、多くの概念実証展開に適しています。これには、次のようなものが含まれます。

- Wi-Fi ネットワークは、通常、インターネットおよびクラウドサービスに対して完全に開いています。
- MDM の自動登録による Azure AD 参加--MDM (Intune) で管理
- ユーザーが自分の会社のアカウントでサインインする (Azure AD)
  - デバイスごとに1つまたは複数のユーザーがサポートされています
- さまざまなレベルのデバイスロックダウン構成は、完全にオープンからシングルアプリキオスクまで、特定のユースケースに基づいて適用されます。

![クラウド接続シナリオ](./images/cloud-connected-guide-diagram.png)

このガイドでは、その他のデバイスの制限や構成は適用されませんが、完了後にこれらのオプションを調べることをお勧めします。

## <a name="learn-about-remote-assist"></a>リモートアシスタンスの詳細

リモートアシスタンスを使用すると、共同での保守と修復、リモート検査、知識の共有とトレーニングを行うことができます。 さまざまな役割と場所のメンバーを接続することで、リモートアシスタンスを使用する技術者は、Microsoft Teams のリモートコラボレーターに接続できます。 ビデオ、スクリーンショット、注釈を組み合わせることにより、同じ場所に t&#39;いなくても、リアルタイムで問題を解決できます。 リモートコラボレーターは参照イメージ、概略図、およびその他の役に立つ情報を挿入できます。技術者は、&#39;、HoloLens でのヘッドアップとハンドフリーの作業中に、概略図を参照できます。

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a>このガイドで行うこと:

準備:

> [!div class="checklist"]
> - [HoloLens 2 デバイスのインフラストラクチャの基本について説明します。](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Azure AD とセットアップの詳細について&#39;は、「」を参照してください。](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Id 管理と Azure AD アカウントを最適に設定する方法について説明します。](hololens2-cloud-connected-prepare.md#identity-management)
> - [MDM の詳細を確認し、まだ準備ができていない場合は、Intune を使用してセットアップします。&#39;。](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [リモートアシスタンスのネットワーク要件について説明します。](hololens2-cloud-connected-prepare.md#network)
> - [必要に応じて、組織のリソースに接続するための VPN](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

以下を構成します。

> [!div class="checklist"]
> - [ユーザーとグループを作成する方法。](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Azure AD 内で自動登録を設定する方法について説明します。](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [アプリケーションライセンスを割り当てる方法。](hololens2-cloud-connected-configure.md#application-licenses)

展開: 

> [!div class="checklist"]
> - [HoloLens 2 をセットアップし、登録を検証します。](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [検証リモートアシスタンス通話を行うことができます。](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

保守:

> [!div class="checklist"]
> - [Microsoft Store アプリを使用してリモートアシスタンスを更新する方法。](hololens2-cloud-connected-maintain.md#updates)
> - [サポートプランを作成しています。](hololens2-cloud-connected-maintain.md#support-plan)
> - [開発計画。](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>次のステップ

> [!div class="nextstepaction"]
> [クラウドに接続されたデプロイ-準備](hololens2-cloud-connected-prepare.md)

