---
title: HoloLens を複数のユーザーと共有する
description: HoloLens を複数の Azure Active Directory アカウントで共有するように構成することも、1つのアカウントを使用する複数のユーザーが共有するように構成することもできます。
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
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309548"
---
# <a name="share-your-hololens-with-multiple-people"></a>HoloLens を複数のユーザーと共有する

1つの HoloLens を多くの人と共有したり、多くの人が HoloLens デバイスのセットを共有したりすることは一般的です。  この記事では、デバイスを共有するさまざまな方法について説明します。

## <a name="share-with-multiple-people-each-using-their-own-account"></a>複数のユーザーと共有し、それぞれが独自のアカウントを使用する

**前提条件**: HoloLens デバイスは、Windows 10 バージョン1803以降を実行している必要があります。  HoloLens (第1世代) も [Windows Holographic For Business にアップグレード](hololens-upgrade-enterprise.md)する必要があります。

独自の Azure Active Directory (Azure AD) アカウントを使用する場合、複数のユーザーが各自のユーザー設定とユーザーデータをデバイスに保持できます。

複数のユーザーが HoloLens で自分のアカウントを使用できるようにするには、次の手順に従って構成します。

1. デバイスで Windows 10 バージョン1803以降が実行されていることを確認します。
   > [!IMPORTANT]
   > HoloLens (第1世代) デバイスを使用している場合は、 [デバイスを Windows Holographic For Business にアップグレード](hololens1-upgrade-enterprise.md)します。
1. デバイスを設定するときに、[ **自分の職場または学校が所有** する] を選択し、Azure AD アカウントを使用してサインインします。
1. セットアップが完了したら、アカウント設定 (**設定**  >  **アカウント**) に **他のユーザー** が含まれていることを確認してください。

HoloLens を使用するには、各ユーザーが次の手順を実行します。

1. 別のユーザーがデバイスを使用している場合は、次のいずれかの操作を行います。
   - 電源ボタンを1回押して、スタンバイに切り替えてから、もう一度電源ボタンを押してロック画面に戻ります。
   - HoloLens 2 ユーザーは、[スタート] メニューから [ユーザー] タイルを選択して、現在のユーザーをサインアウトさせることができます。

1. Azure AD アカウントの資格情報を使用して、デバイスにサインインします。  
    初めてデバイスを使用する場合は、HoloLens を自分の目に合わせて [調整](hololens-calibration.md) する必要があります。

デバイスのユーザーの一覧を表示したり、デバイスからユーザーを削除したりするには、[**設定**] [アカウント] [  >    >  **その他のユーザー**] にアクセスします。

## <a name="share-with-multiple-people-all-using-the-same-account"></a>同じアカウントを使用して複数のメンバーと共有する

また、複数のユーザーが単一のユーザーアカウントを使用しているときに HoloLens デバイスを共有することもできます。

**HoloLens 2 で** は、新しいユーザーが初めてデバイスをヘッドに置いたとき (同じアカウントがサインインしている状態を維持している場合)、デバイスは、新しいユーザーに対して、表示エクスペリエンスを迅速に調整およびカスタマイズするように求めるメッセージを表示します。 デバイスは、将来、デバイスが各ユーザーの表示エクスペリエンスの品質と快適さを自動的に最適化できるように調整情報を保存できます。 ユーザーは、デバイスを再度調整する必要はありません。

**HoloLens (第1世代) で** は、アカウントを共有するユーザーは、設定アプリで再調整するように要求する必要があります。  詳細については、「 [調整](hololens-calibration.md)」を参照してください。
