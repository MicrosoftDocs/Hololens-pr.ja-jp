---
title: グローバルに割り当てられた
description: グローバルに割り当てられた Access キオスク向けの OMA URI の使用ガイド
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens、hololens 2、割り当てられたアクセス、kiosk
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 9c411811376d34b4399db76c76364cd1254910c4
ms.sourcegitcommit: a59ce1cf68785c8e08c5ea94046ba04291ee1a55
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2020
ms.locfileid: "11094975"
---
# グローバルに割り当てられたアクセス-キオスク

この機能は、システムレベルで適用可能なマルチアプリキオスクモード用に Hololens 2 デバイスを構成します。システム上のID とのアフィニティはありません。また、デバイスにサインインするすべてのユーザーに適用されます。 

> [!NOTE]
> この機能は現在、Windows Insider ビルドでのみ利用可能です。  HoloLensリリースで一般に利用可能になる前にこの機能を試してみたい場合は、[Windows Insider](hololens-insider.md)ビルドの詳細をご覧ください。
 
## Intuneでこれを使用する方法 

> [!NOTE]
> [<!-] が付いている領域に注意してください。 これらの領域には、ユーザー設定に基づいて変更する必要があります。 

1.  次のようにカスタム OMA URI デバイス構成プロファイルを作成し、HoloLens デバイスグループに適用します。 

    URI 値: ./Device/Vendor/MSFT/AssignedAccess/Configuration
   
    > [!div class="mx-imgBorder"]
    > ![Intune のグローバル割り当てアクセス OMA - URI](images/global-assigned-access-omauri.png)

2.  値については、以下の内容を更新して貼り付けます: 

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## Windows 構成デザイナーでこれを使用する方法 
 
1.  上記のXML blob を XML ファイルとして更新して保存します。 

2.  [プロビジョニングパッケージを使用して、単一アプリまたはマルチアプリキオスクをセットアップする](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) の手順に従います。特にセクション "Prov について。 パッケージ、ステップ 2-キオスクの構成 XML ファイルをプロビジョニングパッケージに追加し、前の手順で保存された XML ファイルを参照します。 

## グローバルが全員に適用され、個別の構成が 1 つの AAD アカウントまたは AAD グループに適用される構成を作成できますか? 

はい。以下の XML blog の例を参照してください。 グローバルに割り当てられたアクセスプロファイルは、サインインしたユーザーの特定のプロファイルが見つからない場合に Hololens に適用されるため、サインインしたユーザーの既定キオスクモードの構成になっています。 使用する XML blob の例を表示します。 

> [!NOTE]
> `<!-`でマークされた、強調表示された領域に注意してください。 これらの領域には、ユーザー設定に基づいて変更する必要があります。 

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## デバイスの所有者をグローバルに割り当てられているアクセスプロファイルから除外する

この機能を使用すると、Hololens の 「[デバイス所有者](security-adminless-os.md)」 と見なされているユーザーは、グローバルに割り当てられたアクセスから除外されます。 この機能を利用するには、マルチアプリキオスク構成用の XML blob で、強調表示されている行を追加します。 

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::
 
