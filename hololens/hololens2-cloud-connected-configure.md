---
title: デプロイガイド–リモートアシスタンスを使用した大規模なクラウド接続 HoloLens 2 デプロイ
description: リモートアシスタンスを使用して大規模にクラウドに接続されたネットワーク経由でデバイス HoloLens 登録するように構成する方法について説明します。
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
ms.openlocfilehash: eb96f1cdc799551297c0373268e8cc8f35c6bd06
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635145"
---
# <a name="configure---cloud-connected-guide"></a>構成-クラウド接続ガイド

ガイドのこのセクションでは、テナントの自動登録を設定する方法と、Intune とリモートアシスタンスの両方にライセンスを適用する方法について&#39;説明します。

## <a name="azure-users-and-groups"></a>Azure のユーザーとグループ

その拡張機能による Azure および Intune では、ユーザーとグループを使用して、構成とライセンスを割り当てることができます。 この展開フローを検証し、あるユーザーから別のユーザーにリモートアシスタンス呼び出しを行うことができるようにするには&#39;2 つのユーザーアカウントが必要です。

ライセンスを割り当てる目的で、1つのユーザーグループを作成できます。 両方のユーザーを同じグループに参加させ、Intune と Remote Assist のライセンスをそのグループに適用することができます。

ユーザーグループ内の2つの Azure AD アカウントに既にアクセス権がある&#39;は、次のように使用できます。次に、のクイックスタートガイドを示します。

- [ユーザーを作成する方法](/mem/intune/fundamentals/quickstart-create-user)
- [グループを作成する方法](/mem/intune/fundamentals/quickstart-create-group)
- [グループへのユーザーの追加](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) –作成されたユーザーをグループの作成に追加する
- [ユーザーグループがデバイスを参加できるように Azure AD を構成](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) する–新しいユーザーグループにデバイスを登録するアクセス許可があることを確認し Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>HoloLens 2 での自動登録

スムーズでシームレスなエクスペリエンスを実現するために、HoloLens 2 デバイスに対して Azure Active Directory Join (aadj) と Intune への自動登録を設定する方法があります。 これにより、OOBE 中に組織のログイン資格情報を入力し、Azure AD に自動的に登録して、デバイスを MDM に登録できるようになります。

[Microsoft エンドポイントマネージャー](https://endpoint.microsoft.com/#home)を使用すると、サービスを選択し、[Get a プレミアム試用版] を選択するまでいくつかのページに移動できます。 自動登録 P1 の場合は Azure Active Directory Premium 1 と2があることに注意してください。 Intune を選択し、自動登録のユーザースコープを選択して、以前に作成したグループを選択できます。

詳細と手順については、 [Intune の自動登録を有効にする方法](/mem/intune/enrollment/quickstart-setup-auto-enrollment)に関するガイドを参照してください。

## <a name="application-licenses"></a>アプリケーションライセンス

アプリケーションライセンスを使用すると、ユーザーは、会社が購入したアプリをインストールすることも、無料試用版からアプリの完全なバージョンにアップグレードすることもできます。 アプリケーションライセンスは、ユーザー、ユーザーグループ、またはデバイスグループのいずれかに適用できます。 組織内のユーザーがリモートアシスタンスを使用するには、リモートアシスタンスのライセンスが必要&#39;ます。 このガイドでは、 [Azure ユーザーとグループ](hololens2-cloud-connected-configure.md#azure-users-and-groups)の上で作成したユーザーグループに Remote Assist ライセンスを割り当てます。

ライセンスの要件は、ユーザーがデバイスからリモートアシスタンス通話を行うか、Microsoft Teams からリモートコラボレーターになるかによって異なります。 既定では、[リモートアシスタンス] チェックボックスと [Teams] チェックボックスは両方ともマークされています。 このガイドでは、既定のボックスをオンのままにしておくことをお勧めします。

1. ロールごとのさまざまな [ライセンスと製品の要件](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)について説明します。 リモートアシスタンスのライセンスにはいくつかの種類があります。そのため、ニーズに合わせて正しいものを入手してください。
2. [ライセンスを取得](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)する必要が&#39;ます。
3. グループに[ライセンスを適用](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist)します。

## <a name="next-step"></a>次のステップ

> [!div class="nextstepaction"]
> [クラウドに接続されたデプロイ-デプロイ](hololens2-cloud-connected-deploy.md)