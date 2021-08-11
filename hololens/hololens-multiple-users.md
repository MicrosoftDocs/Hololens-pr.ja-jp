---
title: 複数のユーザー HoloLens共有する
description: 複数のアカウントHoloLens、または 1 つのアカウントを使用する複数のユーザー Azure Active Directory共有するユーザーを構成できます。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 821ef2d17531226177e508b1428af82012c16406e9fbce3ed1a5617c767adfe8
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663074"
---
# <a name="share-your-hololens-with-multiple-people"></a>複数のユーザー HoloLens共有する

多くのユーザーと 1 つのHoloLens共有したり、多くのユーザーが一連のデバイスを共有したりHoloLensです。  この記事では、デバイスを共有するさまざまな方法について説明します。

## <a name="share-with-multiple-people-each-using-their-own-account"></a>それぞれ独自のアカウントを使用して複数のユーザーと共有する

**前提条件**: HoloLensバージョン 1803 以降Windows 10デバイスが実行されている必要があります。  HoloLens (第 1 世代) も、 に[アップグレードする必要Windows Holographic for Business。](hololens-upgrade-enterprise.md)

ユーザーが独自のユーザー (Azure Active Directory) Azure ADアカウントを使用する場合、複数のユーザーは、それぞれ独自のユーザー設定とユーザー データをデバイスに保持できます。

複数のユーザーが自分のアカウントを自分のアカウントで使用HoloLensするには、次の手順に従って構成します。

1. デバイスがバージョン 1803 以降Windows 10を実行している必要があります。
   > [!IMPORTANT]
   > デバイス (第 1 世代) HoloLens使用している場合は、デバイスを に[アップグレード](hololens1-upgrade-enterprise.md)Windows Holographic for Business。
1. デバイスを設定するときに、[マイ ワークまたは学校が所有している] を選択し、自分のアカウントを使用Azure ADします。
1. セットアップが完了したら、アカウント設定 ( [アカウント] ) に **[設定**  >  ユーザー] が含 **まれる必要があります**。

このコマンドをHoloLens、各ユーザーは次の手順に従います。

1. 別のユーザーがデバイスを使用している場合は、次のいずれかの操作を行います。
   - 電源ボタンを 1 回押してスタンバイ状態に戻り、電源ボタンを再度押してロック画面に戻ります
   - HoloLens 2ユーザーは、現在のユーザーをサインアウトするためにスタート メニューからユーザー タイルを選択できます。

1. 自分のAzure AD資格情報を使用して、デバイスにサインインします。  
    デバイスを初めて使用する場合は、自分の目に合HoloLens調整[](hololens-calibration.md)する必要があります。

デバイス ユーザーの一覧を表示したり、デバイスからユーザーを削除したりするには、[アカウント] [その他のユーザー] の **設定**  >  **に**  >  **移動します**。

## <a name="share-with-multiple-people-all-using-the-same-account"></a>同じアカウントを使用して複数のユーザーと共有する

複数のユーザーが 1 つのユーザー アカウントHoloLensデバイスを共有することもできます。

**HoloLens 2** では、新しいユーザーが (同じアカウントのサインインを維持しながら) デバイスを初めて頭に置いた場合、新しいユーザーにすばやく調整して表示エクスペリエンスをカスタマイズするように求めるメッセージが表示されます。 デバイスは調整情報を格納して、将来、デバイスが各ユーザーの表示エクスペリエンスの品質と快適性を自動的に最適化できるようすることができます。 ユーザーは、デバイスを再度調整する必要はありません。

**このHoloLens (第 1** 世代) に、アカウントを共有するユーザーは、アプリを再設定があります。  調整の詳細については、以下を [参照してください](hololens-calibration.md)。
