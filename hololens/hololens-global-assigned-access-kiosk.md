---
title: グローバル割り当てアクセス
description: Intune および Windows 構成デザイナーでグローバル割り当てアクセス キオスク用の OMA-URI を使用する方法について説明します。
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens、hololens 2、割り当てアクセス、キオスク
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d36192e7f65f7fe2ccc7ff8699484a19b3d5d3a7ccab0167d2dbdcaf64bb5880
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664019"
---
# <a name="global-assigned-access--kiosk"></a>グローバル割り当てアクセス - キオスク

この機能を使用して、複数のアプリ キオスク モード用に HoloLens 2 デバイスを構成することができます。これはシステム レベルで適用可能であり、システム上の ID とのアフィニティを持たず、デバイスにサインインするユーザー全員に適用されます。

> [!NOTE]
> 現在、この機能は Windows Insider ビルドでのみ利用できます。 HoloLens リリースで一般提供される前にこの機能を試す場合は [Windows Insider](hololens-insider.md) ビルドの詳細を参照してください。

## <a name="how-to-use-global-assigned-access-in-intune"></a>Intune でグローバル割り当てアクセスを使用する方法

> [!NOTE]
> "<!-" が付いている領域に注意してください。 これらの領域は、好みに基づいて変更する必要があります。

1. 次のようにカスタム OMA URI デバイス構成プロファイルを作成し、HoloLens デバイス グループに適用します。

    URI 値: ./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![Intune のグローバル割り当てアクセス OMA-URI](images/global-assigned-access-omauri.png)

2. 値については、以下の内容を更新して貼り付けます。

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a>Windows 構成デザイナーでグローバル割り当てアクセスを使用する方法

1. 上記の XML BLOB を更新して XML ファイルとして保存します。 

2. 「[プロビジョニング パッケージを使用してシングル アプリまたはマルチアプリ キオスクを設定する](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)」(具体的には、セクション「Prov. パッケージ、手順 2. - キオスク構成 XML ファイルをプロビジョニング パッケージに追加する」) の手順に従い、前の手順で保存された XML ファイルを参照します。

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a>グローバルをすべてのユーザーに適用し、個別の構成を 1 つの Azure AD アカウントまたは Azure AD グループに適用する構成を作成できますか? 

はい、以下の XML BLOB の例を参照してください。 グローバル割り当てアクセス プロファイルは、サインインしているユーザーの特定のプロファイルが見つからない場合に HoloLens に適用されます。そのため、サインインしているユーザーの既定のキオスク モード構成です。
使用する XML BLOB の例を次に示します。

> [!NOTE]
> `<!-` のマークで強調表示された領域に注意してください。 これらの領域は、好みに基づいて変更する必要があります。

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a>グローバル割り当てアクセス プロファイルから DeviceOwners を除外する

この機能を使用すると、HoloLens で "[デバイス所有者](security-adminless-os.md)" と見なされるユーザーをグローバル割り当てアクセスから除外できます。 この機能を利用するには、マルチアプリ キオスク構成用の XML BLOB に、強調表示された行を追加します。

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a>他のグローバル割り当てアクセスの例

これは、グローバル割り当てアクセス キオスクの一例であり、ユーザーがサインインすると、設定アプリ、フィードバック Hub、Microsoft Edge を備えたマルチアプリ キオスクを利用できます。

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

この例は、デバイスの所有者を除外するグローバル割り当てアクセス キオスクです。他の Azure AD ユーザーがサインインすると、設定アプリ、フィードバック Hub、Microsoft Edge を備えたマルチアプリ キオスクを利用できます。 このキオスクには、訪問者アカウントに対するセカンダリ キオスク構成も含まれています。これは、ロック画面で誰でもサインイン可能です。 ユーザーが訪問者アカウントにサインインすると、フィードバック Hub アプリのみを備えるマルチアプリ キオスクを利用できます。

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
