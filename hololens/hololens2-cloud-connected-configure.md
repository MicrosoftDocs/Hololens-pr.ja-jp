---
title: 展開ガイド - リモート アシストによるクラウド接続 HoloLens 2 の大規模な展開 - 構成
description: クラウド接続ネットワークを使用して HoloLens デバイスを登録する構成を設定する方法
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
ms.openlocfilehash: 042a29fe436b21ca37a2fcd7921fc53d6a9686d5
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253044"
---
# 構成 - クラウド接続ガイド

このガイドのセクションでは、&#39;の自動登録の設定方法と、Intune とリモート アシストの両方にライセンスを適用する方法について説明します。

## Azure ユーザーとグループ

Azure と Intune をその拡張機能で使用すると、ユーザーとグループを使用して構成とライセンスを割り当てるのに役立ちます。 この展開フローを検証し、あるユーザーから別のユーザーへのリモート アシスト呼び出しを行&#39;2 つのユーザー アカウントが必要になります。

ライセンスを割り当てる目的で、1 つのユーザー グループを作成できます。 両方のユーザーを同じグループに参加し、Intune とリモート アシストのライセンスをそのグループに適用できます。

1 つのユーザー&#39;内の 2 つの Azure ADアカウントにまだアクセスできない場合は、次の方法を使用できます。以下にクイック スタート ガイドを示します。

- [ユーザーを作成する方法](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [グループを作成する方法](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [グループにユーザーを追加する](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) - 作成したユーザーを追加してグループを作成する
- [Azure AD](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) を構成して、ユーザー グループがデバイスに参加するようにします。新しいユーザー グループに、Azure AD にデバイスを登録するアクセス許可を持つ必要があります。

## HoloLens 2 の自動登録

スムーズでシームレスなエクスペリエンスを実現するには、Azure Active Directory Join (AADJ) と Auto Enrollment to Intune for HoloLens 2 デバイスをセットアップする方法があります。 これにより、ユーザーは OOBE 中に組織のログイン資格情報を入力し、Azure AD に自動的に登録し、デバイスを MDM に登録できます。

Microsoft Endpoint [Manager を使用](https://endpoint.microsoft.com/#home)すると、サービスを選択し、[プレミアム評価版を取得] を選択できるまで、いくつかのページを移動できます。 自動登録 P1 では Azure Active Directory Premium 1 と Azure Active Directory Premium 2 で十分です。 Intune を選択し、自動登録のユーザー スコープを選択し、以前に作成したグループを選択できます。

詳細と手順については、Intune の自動登録を有効にする [方法に関するガイドを参照してください](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)。

## アプリケーション ライセンス

アプリケーション ライセンスを使用すると、ユーザーは会社が購入したアプリをインストールするか、無料試用版からアプリの完全版にアップグレードできます。 アプリケーション ライセンスは、ユーザー、ユーザー グループ、またはデバイス グループに適用できます。 リモート&#39;を使用するには、組織内のユーザーのリモート アシスト ライセンスが必要です。 このガイドの目的上、上記の Azure ユーザーとグループで作成したユーザー グループにリモート アシスト ライセンス [を割り当てる必要があります](hololens2-cloud-connected-configure.md#azure-users-and-groups)。

ライセンスの要件は、ユーザーがデバイスからリモート アシスト通話を行うのか、Microsoft Teams のリモートコラボレーターになるかによって異なります。 既定では、リモート アシストと Teams の両方のチェック ボックスがマークされます。 このガイドの目的上、既定のチェック ボックスはオンのままにしてください。

1. ロールごとのさまざまなライセンス要件と製品 [要件について説明します](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)。 リモート アシスト ライセンスにはいくつかの種類があります。そのため、必要に応じて適切なライセンスを取得してください。
2. ライセンス&#39;取得する [必要があります](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)。
3. [グループにライセンス](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) を適用します。

## 次のステップ

> [!div class="nextstepaction"]
> [クラウド接続展開 - 展開](hololens2-cloud-connected-deploy.md)