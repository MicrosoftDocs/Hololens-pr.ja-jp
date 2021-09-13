---
title: キオスク参照情報の HoloLens
description: HoloLens デバイスでキオスクを使用するための情報とサンプルです。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9f8cfd0013ac5b8cf85a334cbb89c458440820d9
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033204"
---
# <a name="hololens-kiosk-reference-information"></a>HoloLens キオスクの参照情報

このページには、HoloLens デバイスのキオスクモードの設定に役立つ情報が含まれています。 このリファレンスには、受信トレイアプリの AUMIDs、お客様の検索対象や、キオスクモード用のいくつかの XML サンプルが含まれています。これらのサンプルは、いくつかの異なるシナリオで使用する準備ができていません。 キオスクの設定の詳細については、「キオスクのセットアップ」ページを参照して [ください。](hololens-kiosk.md)

## <a name="hololens-application-user-model-ids-aumids"></a>HoloLensアプリケーションユーザーモデル Id (AUMIDs)  

キオスクアプリを選択する方法に関する一般的な情報については、「 [割り当てられたアクセス用のアプリを選択するためのガイドライン (キオスクモード)](/windows/configuration/guidelines-for-assigned-access-app)」を参照してください。

モバイルデバイス管理 (MDM) システムまたはプロビジョニングパッケージを使用してキオスクモードを構成する場合は、 [AssignedAccess 構成サービスプロバイダー (CSP)](/windows/client-management/mdm/assignedaccess-csp) を使用してアプリケーションを指定します。 CSP は、 [アプリケーションユーザーモデル id (AUMIDs)](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) を使用してアプリケーションを識別します。 次の表に、マルチアプリキオスクで使用できるいくつかのインボックスアプリケーションの AUMIDs を示します。

<a id="aumids"></a>

|アプリ名 |AUMID |
| --- | --- |
|3D ビューアー |Microsoft3DViewer \_ 8Wekyb3d8bbwe \! Microsoft3DViewer |
|予定表 |windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft. live |
|カメラ<sup>1、2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft 549981C3F5F10 \_ 8wekyb3d8bbwe \! アプリ |
|HoloLens のデバイスピッカー (第1世代) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|HoloLens 2 でのデバイスの選択 |エクスプローラー.Windows。DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft. Windows。DevicesFlowHost |
|Dynamics 365 Guides |Dynamics365 \_ 8wekyb3d8bbwe の \! ガイド |
|Dynamics 365 Remote Assist |Microsoft office Remoteassist \_ 8wekyb3d8bbwe \! Microsoft. remoteassist |
|フィードバック &nbsp; ハブ |Microsoft Windowsフィード Backhub \_ 8wekyb3d8bbwe \! アプリ |
|エクスプローラー |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe! live |
|古い Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge |
|新しい Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast<sup>4</sup> | &nbsp; |
|映画 & テレビ |Microsoft ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft ZuneVideo |
|OneDrive |microsoft office skydrive \_ 8wekyb3d8bbwe \! アプリ |
|写真 |エクスプローラー.Windows。Photos \_ 8wekyb3d8bbwe \! アプリ |
|古い設定 |HolographicSystemSettings_cw5n1h2txyewy!アプリケーション |
|新しい設定 |BAEAEF15-9BAB-47 FC-800B-ACECAD2AE94B_cw5n1h2txyewy!アプリケーション |
|ヒント |HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> 写真またはビデオのキャプチャを有効にするには、キオスクアプリとしてカメラアプリを有効にする必要があります。  
> <sup>2</sup> カメラアプリを有効にするときは、次の条件に注意してください。
> - [クイックアクション] メニューには、[写真] ボタンと [ビデオ] ボタンがあります。
> - また、画像を操作したり、画像を取得したりできるアプリ (写真、メール、OneDrive など) を有効にする必要もあります。  
>  
> <sup>3</sup>キオスクアプリとして Cortana を有効にしない場合でも、組み込みの音声コマンドが有効になります。 ただし、無効になっている機能に関連するコマンドには影響しません。  
> <sup>4</sup> Miracast を直接有効にすることはできません。 キオスクアプリとして Miracast を有効にするには、カメラアプリとデバイスピッカーアプリを有効にします。

また、Mixed Reality ホームをキオスクアプリとして設定することはできません。

[Id の種類に基づくキオスクモードのサポートされているシナリオ](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)に戻る

## <a name="kiosk-xml-code-samples"></a>キオスク XML コードサンプル

1. [複数のアプリのグローバルに割り当てられたアクセスプロファイル](#multiple-app-global-assigned-access-profile)
1. [複数のアプリのグローバルに割り当てられたアクセスプロファイル (デバイス所有者を除く)](#multiple-app-global-assigned-access-profile-excluding-device-owners)
1. [ローカルアカウントまたは AAD ユーザーアカウントの複数のアプリが割り当てられたアクセスプロファイル](#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account)
1. [2つの AAD ユーザーに対して複数のアプリが割り当てられたアクセスプロファイル](#multiple-app-assigned-access-profiles-for-two-aad-users-or-more)
1. [1つの AAD グループに対して複数のアプリが割り当てられたアクセスプロファイル](#multiple-app-assigned-access-profile-for-one-aad-group)
1. [2つの AAD グループ以上に対して複数のアプリが割り当てられたアクセスプロファイル](#multiple-app-assigned-access-profile-for-two-aad-groups-or-more)
1. [1つの AAD アカウントと1つの AAD グループに対して、複数のアプリが割り当てられたアクセスプロファイル](#multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group)
1. [複数のアプリによって訪問者に割り当てられたアクセスプロファイル](#multiple-app-assigned-access-profile-for-visitors)

> [!NOTE]
> TODO アクションを要件に従って置き換えます。

### <a name="multiple-app-global-assigned-access-profile"></a>複数のアプリのグローバルに割り当てられたアクセスプロファイル

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone.xml" highlight="18-20":::

[一覧に戻る](#kiosk-xml-code-samples) <br>
[Id の種類に基づくキオスクモードのサポートされているシナリオ](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)に戻る

### <a name="multiple-app-global-assigned-access-profile-excluding-device-owners"></a>複数のアプリのグローバルに割り当てられたアクセスプロファイル (デバイス所有者を除く)

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone-excluding-device-owners.xml" highlight="18-20":::

[一覧に戻る](#kiosk-xml-code-samples) <br>
[Id の種類に基づくキオスクモードのサポートされているシナリオ](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)に戻る

### <a name="multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account"></a>ローカルアカウントまたは AAD ユーザーアカウントの複数のアプリが割り当てられたアクセスプロファイル

:::code language="xml" source="samples/kiosk-sample-multi-app-local-or-aad-user.xml" highlight="18-20,51,55":::

[一覧に戻る](#kiosk-xml-code-samples) <br>
[Id の種類に基づくキオスクモードのサポートされているシナリオ](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)に戻る

### <a name="multiple-app-assigned-access-profiles-for-two-aad-users-or-more"></a>2つの AAD ユーザーに対して複数のアプリが割り当てられたアクセスプロファイル

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-users-or-more.xml" highlight="22-24,52,53,80,88":::

[一覧に戻る](#kiosk-xml-code-samples) <br>
[Id の種類に基づくキオスクモードのサポートされているシナリオ](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)に戻る

### <a name="multiple-app-assigned-access-profile-for-one-aad-group"></a>1つの AAD グループに対して複数のアプリが割り当てられたアクセスプロファイル

:::code language="xml" source="samples/kiosk-sample-multi-app-one-aad-group.xml" highlight="28":::

[一覧に戻る](#kiosk-xml-code-samples) <br>
[Id の種類に基づくキオスクモードのサポートされているシナリオ](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)に戻る

### <a name="multiple-app-assigned-access-profile-for-two-aad-groups-or-more"></a>2つの AAD グループ以上に対して複数のアプリが割り当てられたアクセスプロファイル

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-groups-or-more.xml" highlight="22-24,52,53,83,94":::

[一覧に戻る](#kiosk-xml-code-samples) <br>
[Id の種類に基づくキオスクモードのサポートされているシナリオ](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)に戻る

### <a name="multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group"></a>1つの AAD アカウントと1つの AAD グループに対して、複数のアプリが割り当てられたアクセスプロファイル

:::code language="xml" source="samples/kiosk-sample-multi-app-for-aad-user-and-aad-group.xml" highlight="22-24,52,53,80,91":::

[一覧に戻る](#kiosk-xml-code-samples) <br>
[Id の種類に基づくキオスクモードのサポートされているシナリオ](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)に戻る

### <a name="multiple-app-assigned-access-profile-for-visitors"></a>複数のアプリによって訪問者に割り当てられたアクセスプロファイル

:::code language="xml" source="samples/kiosk-sample-multi-app-visitor-user.xml" highlight="18-20":::

[一覧に戻る](#kiosk-xml-code-samples) <br>
[Id の種類に基づくキオスクモードのサポートされているシナリオ](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)に戻る
