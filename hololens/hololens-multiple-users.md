---
title: 複数のユーザーと HoloLens を共有する
description: 複数の Azure Active Directory アカウントで、または1つのアカウントを使用する複数のユーザーが共有するように HoloLens を構成することができます。
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
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829288"
---
# 複数のユーザーと HoloLens を共有する

1つの HoloLens を多くのユーザーと共有したり、多数のユーザーが一連の HoloLens デバイスを共有したりすることは一般的です。  この記事では、デバイスを共有するさまざまな方法について説明します。

## 自分のアカウントを使用して複数のユーザーと共有する

**前提条件**: HoloLens デバイスでは、Windows 10 バージョン1803以降を実行している必要があります。  HoloLens (第1世代) も、 [Windows ホログラフィック For Business にアップグレード](hololens-upgrade-enterprise.md)する必要があります。

独自の Azure Active Directory (Azure AD) アカウントを使用している場合、複数のユーザーが自分のユーザー設定とユーザーデータをデバイス上に保持することができます。

複数のユーザーが HoloLens で自分のアカウントを使用できるようにするには、次の手順に従って設定します。

1. デバイスで Windows 10 バージョン1803以降が実行されていることを確認します。
   > [!IMPORTANT]
   > HoloLens (第1世代) デバイスを使っている場合は、[デバイスを Windows ホログラフィック For Business にアップグレード](hololens1-upgrade-enterprise.md)します。
1. デバイスをセットアップするときに、[**自分の職場または学校**] を選択して、Azure AD アカウントを使用してサインインします。
1. セットアップが完了したら、アカウント設定 ([設定]**Settings**  >  **アカウント**) に**他のユーザー**が含まれていることを確認します。

HoloLens を使用するには、各ユーザーが次の手順を実行します。

1. 他のユーザーがデバイスを使っている場合は、次のいずれかの操作を行います。
   - 電源ボタンを1回押して [スタンバイ] に移動し、もう一度電源ボタンを押してロック画面に戻ります。
   - HoloLens 2 ユーザーは、[スタート] メニューからユーザータイルを選択して、現在のユーザーからサインアウトすることができます。

1. Azure AD アカウントの資格情報を使用して、デバイスにサインインします。  
    初めてデバイスを使った場合は、HoloLens を自分の目に合わせて[調整](hololens-calibration.md)する必要があります。

デバイスユーザーの一覧を表示したり、デバイスからユーザーを削除したりするには、[**設定**  >  **アカウント**  >  **の他のユーザー**] に移動します。

## 同じアカウントを使用して複数のユーザーと共有する

複数のユーザーが1つのユーザーアカウントを使用しているときに、HoloLens デバイスを共有することもできます。

**HoloLens 2 で**は、新しいユーザーが初めて (同じアカウントでサインインしたまま) デバイスをそのヘッド上に配置すると、デバイスは新しいユーザーに対して、表示エクスペリエンスの調整とカスタマイズをすばやく行うように求めます。 デバイスには調整情報が保存されているため、デバイスは、各ユーザーの表示エクスペリエンスの品質と快適さを自動的に最適化することができます。 ユーザーはデバイスを再調整する必要はありません。

**HoloLens (第1世代) で**は、アカウントを共有しているユーザーは、設定アプリで再調整を要求する必要があります。  詳細については、「[調整](hololens-calibration.md)」を参照してください。
