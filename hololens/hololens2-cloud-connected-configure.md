---
title: 展開ガイド–リモートアシスタンスによる構成による、クラウド接続の HoloLens 2 展開
description: クラウドに接続されたネットワーク経由で HoloLens デバイスを登録するための構成を設定する方法
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
ms.openlocfilehash: 43b9db96a2c29d1e3a798d0c695ab6edaa8199ac
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196337"
---
# 構成-クラウド接続ガイド

このセクションでは、テナントの自動登録のセットアップ方法、および Intune とリモートアシストの両方のライセンスの適用方法について説明し&#39;します。

## Azure ユーザーとグループ

Azure、およびその拡張機能により、ユーザーとグループを使用して、構成とライセンスを割り当てることができます。 このような展開フローを検証して、あるユーザーから別のユーザーにリモートアシスタンス通話を発信できるようにするためには、2つのユーザーアカウントが必要です。&#39;ます。

ライセンスの割り当てを目的とした1つのユーザーグループを作成できます。 両方のユーザーを同じグループに参加させることができ、そのグループに Intune およびリモートアシスタンスのライセンスを適用することができます。

ユーザーグループ内の2つの AAD アカウントにまだアクセスできない場合は、次のような方法で&#39;ます。次のクイックスタートガイドを参照してください。

- [ユーザーを作成する方法](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [グループを作成する方法](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [グループにユーザーを追加](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) する–作成したユーザーを追加してグループを作成する
- [ユーザーグループがデバイスに参加することを許可するように AAD を構成](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) する–新しいユーザーグループに、デバイスを AAD に登録する権限があることを確認する

## HoloLens 2 での自動登録

円滑かつシームレスなエクスペリエンスを実現するために、Azure Active Directory の参加 (AADJ) と、Intune の自動登録機能を設定することができます。 これにより、ユーザーは OOBE 中に組織のログイン資格情報を入力し、AAD に自動的に登録し、デバイスを MDM に登録することができます。

[Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)を使用することで、[サービス] を選択し、[Premium 試用版の取得] が選択されるまで、いくつかのページに移動できます。 自動登録 P1 には、Azure Active Directory Premium 1 と2が用意されています。 [Intune] を選択し、自動登録のユーザー範囲を選択して、以前に作成されたグループを選択することができます。

詳細と手順については、「 [Intune の自動登録を有効](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)にする」のガイドを参照してください。

## アプリケーションライセンス

アプリケーションライセンスにより、ユーザーは会社で購入したアプリをインストールしたり、無料トライアルをアプリの完全バージョンにアップグレードしたりすることができます。 アプリケーションライセンスは、ユーザー、ユーザーグループ、またはデバイスグループのいずれかに適用できます。 リモートアシストを使用するには、組織内のユーザーに対してリモートアシスタンスライセンスが必要です&#39;ます。 このガイドでは、前述のように、 [Azure ユーザーとグループ](hololens2-cloud-connected-configure.md#azure-users-and-groups)で作成したユーザーグループにリモートアシスタンスライセンスを割り当てます。

ライセンスの要件は、ユーザーがデバイスからリモートアシスタンス通話を行う場合や、Microsoft Teams のリモートコラボレーターであるかによって異なる場合があります。 既定では、[リモートアシスタンス] と [チーム] チェックボックスは両方としてマークされています。 このガイドでは、既定のボックスをオンのままにしておくことをお勧めします。

1. さまざまな [ライセンスと製品の要件](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)の詳細については、こちらを参照してください。 リモートアシスタンスライセンスには、いくつかの種類があります。必要に応じて、正しいものを入手してください。
2. &#39;[、ライセンスを取得](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)する必要があります。
3. [ライセンス](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) をグループに適用します。

## 次のステップ

> [!div class="nextstepaction"]
> [クラウド接続展開-展開](hololens2-cloud-connected-deploy.md)