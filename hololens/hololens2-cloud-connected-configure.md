---
title: デプロイ ガイド – クラウドに接続HoloLens 2大規模なデプロイ - Remote Assist - 構成
description: クラウドに接続されたネットワークを使用して大規模HoloLensデバイスを登録する構成を設定する方法Remote Assist。
keywords: HoloLens、管理、クラウド接続、Remote Assist、AAD、Azure AD、MDM、Mobile デバイス管理
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
ms.openlocfilehash: eb96f1cdc799551297c0373268e8cc8f35c6bd06
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033544"
---
# <a name="configure---cloud-connected-guide"></a>構成 - クラウド接続ガイド

このガイドのセクションでは、テナント&#39;自動登録を設定する方法と、Intune と Remote Assist の両方にライセンスを適用する方法について説明します。

## <a name="azure-users-and-groups"></a>Azure ユーザーとグループ

その拡張機能による Azure と Intune では、ユーザーとグループを使用して構成とライセンスの割り当てに役立ちます。 このデプロイ フローを検証し、あるユーザーから別のユーザーへの Remote Assist 呼び出しを行&#39;、2 つのユーザー アカウントが必要になります。

ライセンスを割り当てる目的で、1 つのユーザー グループを作成できます。 両方のユーザーを同じグループに参加し、Intune のライセンスを適用し、そのグループにRemote Assistを適用できます。

ユーザー グループ内&#39;2 つのアカウントにまだAzure ADアクセスできない場合は、次のコマンドを使用できます。次に示すのは、以下のクイック スタート ガイドです。

- [ユーザーを作成する方法](/mem/intune/fundamentals/quickstart-create-user)
- [グループを作成する方法](/mem/intune/fundamentals/quickstart-create-group)
- [グループにユーザーを追加する](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – 作成したユーザーを追加してグループを作成する
- [ユーザー Azure ADデバイスへの参加を](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) 許可するユーザー グループを構成する – 新しいユーザー グループにデバイスを登録するアクセス許可が付与Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>[自動登録] (HoloLens 2

スムーズでシームレスなエクスペリエンスを実現するには、HoloLens 2 デバイス用に Azure Active Directory Join (AADJ) と Intune への自動登録を設定します。 これにより、ユーザーは OOBE 中に組織のログイン資格情報を入力し、Azure AD に自動的に登録し、デバイスを MDM に登録できます。

を使用[Microsoft エンドポイント マネージャー](https://endpoint.microsoft.com/#home)サービスを選択し、[無料試用版を取得する] を選択するまで、いくつかのページプレミアムできます。 自動登録 P1 でAzure Active Directory Premium 1 と 2 がある場合があります。 Intune を選択し、自動登録のユーザー スコープを選択し、以前に作成したグループを選択できます。

詳細と手順については、Intune の自動登録を有効 [にする方法に関するガイドを参照してください](/mem/intune/enrollment/quickstart-setup-auto-enrollment)。

## <a name="application-licenses"></a>アプリケーション ライセンス

アプリケーション ライセンスを使用すると、ユーザーは会社が購入したアプリをインストールするか、無料試用版から完全版のアプリにアップグレードできます。 アプリケーション ライセンスは、ユーザー、ユーザー グループ、またはデバイス グループに適用できます。 組織&#39;を使用Remote Assistユーザーのライセンスを取得する必要Remote Assist。 このガイドでは、上記の 「Azure ユーザーとグループRemote Assistグループ」で作成したユーザー グループにライセンスを割 [り当てる方法について説明します](hololens2-cloud-connected-configure.md#azure-users-and-groups)。

ライセンスの要件は、ユーザーがデバイスから Remote Assist を呼び出すのか、Microsoft Teams からのリモート コラボレーターになるかによって異なる場合があります。 既定では、Remote AssistとTeams両方のチェック ボックスがマークされます。 このガイドの目的上、既定のボックスはオンのままにしてください。

1. ロールごとに異なる [ライセンスと製品の要件の詳細を確認してください](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)。 ライセンスにはいくつかの異なる種類Remote Assist、ニーズに合った適切なライセンスを取得してください。
2. ライセンス&#39;取得する [必要があります](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)。
3. [グループにライセンス](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) を適用します。

## <a name="next-step"></a>次の手順

> [!div class="nextstepaction"]
> [クラウドに接続されたデプロイ - デプロイ](hololens2-cloud-connected-deploy.md)