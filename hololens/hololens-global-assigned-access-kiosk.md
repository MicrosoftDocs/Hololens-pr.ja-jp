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
ms.openlocfilehash: f91b77be846b585de8d89c17e516923f97304d57
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253204"
---
# グローバルに割り当てられたアクセス-キオスク

この機能は、システム レベルで適用可能な複数のアプリ キオスク モード用に HoloLens 2 デバイスを構成し、システム上の ID とのアフィニティを持たず、デバイスにサインインするユーザー全員に適用されます。

> [!NOTE]
> この機能は現在、Windows Insider ビルドでのみ利用できます。 HoloLens リリースで一般公開される前にこの機能を試す場合は [、Windows Insider](hololens-insider.md) ビルドの詳細をご覧ください。

## Intune でグローバルに割り当てられたアクセスを使用する方法

> [!NOTE]
> [<!-] が付いている領域に注意してください。 これらの領域には、ユーザー設定に基づいて変更する必要があります。

1. 次のようにカスタム OMA URI デバイス構成プロファイルを作成し、HoloLens デバイスグループに適用します。

    URI 値: ./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![Intune のグローバル割り当てアクセス OMA - URI](images/global-assigned-access-omauri.png)

2. 値については、以下の内容を更新して貼り付けます:

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## Windows 構成デザイナーでグローバルに割り当てられたアクセスを使用する方法

1. 上記のXML blob を XML ファイルとして更新して保存します。 

2. [プロビジョニングパッケージを使用して、単一アプリまたはマルチアプリキオスクをセットアップする](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) の手順に従います。特にセクション "Prov について。 パッケージ、ステップ 2-キオスクの構成 XML ファイルをプロビジョニングパッケージに追加し、前の手順で保存された XML ファイルを参照します。

## グローバルがすべてのユーザーに適用され、個別の構成が 1 つの Azure AD アカウントまたは Azure AD グループに適用される構成を作成できますか? 

はい、以下の XML BLOB の例を参照してください。 グローバルに割り当てられたアクセス プロファイルは、サインインしているユーザーの特定のプロファイルが見つからない場合に HoloLens に適用されます。そのため、サインインしているユーザーの既定のキオスク モード構成です。
使用する XML blob の例を表示します。

> [!NOTE]
> `<!-`でマークされた、強調表示された領域に注意してください。 これらの領域には、ユーザー設定に基づいて変更する必要があります。

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## デバイスの所有者をグローバルに割り当てられているアクセスプロファイルから除外する

この機能を使用すると、HoloLens で "[デバイスの所有者](security-adminless-os.md)" と見なされるユーザーをグローバルに割り当てられたアクセスから除外できます。 この機能を利用するには、マルチアプリキオスク構成用の XML blob で、強調表示されている行を追加します。

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## 他のグローバルに割り当てられたアクセスの例

これは、グローバルに割り当てられたアクセス キオスクの例で、ユーザーがサインインすると、設定アプリ、フィードバック Hub、Microsoft Edge で複数アプリのキオスクを使用できます。

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

この例は、デバイスの所有者を除外するグローバルに割り当てられたアクセス キオスクです。他の Azure AD ユーザーがサインインすると、設定アプリ、フィードバック Hub、および Microsoft Edge を使って複数アプリのキオスクが表示されます。 このキオスクには、ゲストのアカウントに対するセカンダリ キオスク構成も含まれます。これは、ロック画面で誰でもサインイン可能です。 ユーザーがゲストのアカウントにサインインすると、フィードバック Hub アプリのみを含むマルチアプリ キオスクが表示されます。

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
