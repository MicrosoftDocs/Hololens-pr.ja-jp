---
title: 複数のユーザー HoloLens共有する
description: 複数のアカウントHoloLens、または 1 つのアカウントを使用するAzure Active Directoryユーザーが共有する構成を構成できます。
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e3acd2665e93e44bce2c5dad467c825dc768bfed
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033915"
---
# <a name="share-your-hololens-with-multiple-people"></a>複数のユーザー HoloLens共有する

## <a name="overview"></a>概要
多くの場合、企業は多くの共有デバイスにHoloLensしています。 個々の要件HoloLensに応じて、アプリケーションを使用する方法は、ボード全体で柔軟に使用できます。 マルチユーザー エクスペリエンスの例を次に示します。 

- Dynamics 365 Guides が課金され、従業員が必要な Wi-Fi に調整するために 設定 アプリを開くことができるデバイスが、ページ 設定 表示ポリシーが有効になっていると、設定 アプリで使用可能なページの量が制限されます。
- デバイスは、Remote Assist、他の会社にレンタルされる業務アプリです。 これらのデバイスには、アプリとデバイスのみを含むキオスクRemote Assist。 WDAC は、アプリの起動と設定をMicrosoft Edgeするために使用されます。 レンタルに含まれる USB-C バッテリ パックは、デバイスを複数のシフトでフル 充電状態に保つ場合に使用します。
- すべてのデバイスが Autopilot 用に設定され、会社のすべてのアプリがダウンロードされます。 さまざまなキオスク プロファイルを設定し、異なるキオスク プロファイルとグループAzure ADしました。 各ユーザーは、FIDO2 キーをHoloLens、独自の Azure AD アカウントにサインインして、カスタマイズされたエクスペリエンスを提供します。



## <a name="share-with-multiple-people-each-using-their-own-account"></a>それぞれ独自のアカウントを使用して複数のユーザーと共有する

**前提条件**: HoloLensバージョン 1803 以降Windows 10デバイスが実行されている必要があります。  HoloLens (第 1 世代) も、 に[アップグレードする必要Windows Holographic for Business。](hololens-upgrade-enterprise.md)

ユーザーが独自のユーザー Azure Active Directory (Azure AD) アカウントを使用する場合、複数のユーザーは、それぞれ独自のユーザー設定とユーザー データをデバイスに保持できます。

複数のユーザーが自分のアカウントを自分のアカウントで使用HoloLens、次の手順に従って構成します。

1. デバイスがバージョン 1803 以降Windows 10を実行している必要があります。
   > [!IMPORTANT]
   > デバイス (第 1 世代) HoloLens使用している場合は、デバイスを にアップグレード[Windows Holographic for Business。](hololens1-upgrade-enterprise.md)
1. デバイスを設定するときに、[マイ ワークまたは学校が所有している] を選択し、自分のアカウントを使用Azure ADします。
1. セットアップが完了したら、アカウント設定 ( [アカウント] ) に [**その他** の設定  >  が含 **まれる必要があります**。

このコマンドをHoloLens、各ユーザーは次の手順に従います。

1. 別のユーザーがデバイスを使用している場合は、次のいずれかのオプションを選択します。
   - 電源ボタンを 1 回押してスタンバイ状態に戻り、電源ボタンを再度押してロック画面に戻ります
   - HoloLens 2ユーザーは、現在のユーザーをサインアウトスタート メニューユーザー タイルを選択できます。

1. デバイスにAzure ADアカウントの資格情報を使用します。  
    デバイスを初めて使用する場合は、自分の目に合HoloLens調整する[](hololens-calibration.md)必要があります。

デバイス ユーザーの一覧を表示したり、デバイスからユーザーを削除したりするには、[アカウント] [**その** 他のユーザー] の設定  >  **に**  >  **移動します**。

## <a name="share-with-multiple-people-all-using-the-same-account"></a>同じアカウントを使用して複数のユーザーと共有する

複数のユーザーが 1 つのユーザー アカウントHoloLensデバイスを共有することもできます。

**HoloLens 2** では、新しいユーザーが (同じアカウントのサインインを維持しながら) デバイスを初めて頭に置いた場合、新しいユーザーにすばやく調整し、表示エクスペリエンスをカスタマイズするように求めるメッセージが表示されます。 デバイスは調整情報を格納して、将来、デバイスが各ユーザーの表示エクスペリエンスの品質と快適性を自動的に最適化できるようすることができます。 ユーザーは、デバイスを再度調整する必要はありません。

**このHoloLens (第 1** 世代) では、アカウントを共有するユーザーは、アプリで再設定があります。  調整の詳細については、以下を [参照してください](hololens-calibration.md)。