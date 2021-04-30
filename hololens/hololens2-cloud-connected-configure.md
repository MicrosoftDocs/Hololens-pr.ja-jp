---
title: デプロイガイド–リモートアシスタンスを使用した大規模なクラウド接続 HoloLens 2 デプロイ
description: リモートアシスタンスで、大規模なクラウド接続ネットワーク経由で HoloLens デバイスを登録する構成を設定する方法について説明します。
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
ms.openlocfilehash: 00cc3f9df1fefafc9c4c084ff642364ae3ccb85c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309361"
---
# <a name="configure---cloud-connected-guide"></a>構成-クラウド接続ガイド

ガイドのこのセクションでは、テナントの自動登録を設定する方法と、Intune とリモートアシスタンスの両方にライセンスを適用する方法について&#39;説明します。

## <a name="azure-users-and-groups"></a>Azure のユーザーとグループ

その拡張機能による Azure および Intune では、ユーザーとグループを使用して、構成とライセンスを割り当てることができます。 この展開フローを検証し、あるユーザーから別のユーザーにリモートアシスタンス呼び出しを行うことができるようにするには&#39;2 つのユーザーアカウントが必要です。

ライセンスを割り当てる目的で、1つのユーザーグループを作成できます。 両方のユーザーを同じグループに参加させ、Intune と Remote Assist のライセンスをそのグループに適用することができます。

ユーザーグループ内の2つの Azure AD アカウントに既にアクセス権がある&#39;は、次のように使用できます。次に、のクイックスタートガイドを示します。

- [ユーザーを作成する方法](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [グループを作成する方法](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [グループへのユーザーの追加](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) –作成されたユーザーをグループの作成に追加する
- [ユーザーグループがデバイスを参加できるように Azure AD を構成](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) する–新しいユーザーグループにデバイスを登録するアクセス許可があることを確認し Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>HoloLens 2 での自動登録

スムーズでシームレスなエクスペリエンスを実現するために、Intune への Azure Active Directory 参加 (AADJ) と Intune への自動登録を設定する方法があります。 これにより、OOBE 中に組織のログイン資格情報を入力し、Azure AD に自動的に登録して、デバイスを MDM に登録できるようになります。

[Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)を使用して、サービスを選択し、いくつかのページに移動して、[Premium 試用版を取得する] を選択できます。 自動登録 P1 の場合は Azure Active Directory Premium 1 と2があることに注意してください。 Intune を選択し、自動登録のユーザースコープを選択して、以前に作成したグループを選択できます。

詳細と手順については、 [Intune の自動登録を有効にする方法](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)に関するガイドを参照してください。

## <a name="application-licenses"></a>アプリケーションライセンス

アプリケーションライセンスを使用すると、ユーザーは、会社が購入したアプリをインストールすることも、無料試用版からアプリの完全なバージョンにアップグレードすることもできます。 アプリケーションライセンスは、ユーザー、ユーザーグループ、またはデバイスグループのいずれかに適用できます。 組織内のユーザーがリモートアシスタンスを使用するには、リモートアシスタンスのライセンスが必要&#39;ます。 このガイドでは、 [Azure ユーザーとグループ](hololens2-cloud-connected-configure.md#azure-users-and-groups)の上で作成したユーザーグループに Remote Assist ライセンスを割り当てます。

ライセンスの要件は、ユーザーがデバイスからのリモートアシスタンス呼び出しを行うかどうか、または Microsoft Teams からのリモートコラボレーターになるかどうかによって異なります。 既定では、[リモートアシスタンス] と [チーム] のチェックボックスは両方ともマークされています。 このガイドでは、既定のボックスをオンのままにしておくことをお勧めします。

1. ロールごとのさまざまな [ライセンスと製品の要件](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)について説明します。 リモートアシスタンスのライセンスにはいくつかの種類があります。そのため、ニーズに合わせて正しいものを入手してください。
2. [ライセンスを取得](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)する必要が&#39;ます。
3. グループに[ライセンスを適用](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist)します。

## <a name="next-step"></a>次のステップ

> [!div class="nextstepaction"]
> [クラウドに接続されたデプロイ-デプロイ](hololens2-cloud-connected-deploy.md)