---
title: HoloLensキオスクの参照情報
description: デバイス上のキオスクの情報とHoloLensします。
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
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2021
ms.locfileid: "122863945"
---
# <a name="hololens-kiosk-reference-information"></a>HoloLensキオスクの参照情報

このページには、デバイスのキオスク モードを設定HoloLens役立つ情報が含まれている。 このリファレンスには、受信トレイ アプリと検索用の AUMID、キオスク モード用の XML サンプルが含まれます。キオスク モードの XML サンプルは、いくつかの異なるシナリオで使用する準備が整うのをほんの少しだけ離れた場所で行います。 キオスクの設定については、キオスクの設定に関 [するページを参照してください。](hololens-kiosk.md)

## <a name="hololens-application-user-model-ids-aumids"></a>HoloLensアプリケーション ユーザー モデル ID (AUMID)  

キオスク アプリの選択方法に関する一般的な情報については、「割り当て済みアクセスのアプリを選択するためのガイドライン (キオスク モード [)」を参照してください](/windows/configuration/guidelines-for-assigned-access-app)。

Mobile デバイス管理 (MDM) システムまたはプロビジョニング パッケージを使用してキオスク モードを構成する場合は [、AssignedAccess 構成](/windows/client-management/mdm/assignedaccess-csp) サービス プロバイダー (CSP) を使用してアプリケーションを指定します。 CSP は、 [アプリケーション を識別するためにアプリケーション ユーザー モデル ID (AUMID)](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) を使用します。 次の表に、マルチアプリ キオスクで使用できる一部のインボックス アプリケーションの AUMID を示します。

<a id="aumids"></a>

|アプリ名 |AUMID |
| --- | --- |
|3D ビューアー |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Calendar |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|カメラ<sup>1、2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! アプリ |
|HoloLens デバイス ピッカー (第 1 世代) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|デバイス ピッカー (HoloLens 2 |マイクロソフト。Windows。DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows。DevicesFlowHost |
|Dynamics 365 Guides |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft.RemoteAssist |
|フィードバック &nbsp; ハブ |Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe \! アプリ |
|エクスプローラー |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|古いMicrosoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge |
|新しい Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast<sup>4</sup> | &nbsp; |
|映画 & テレビ |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! アプリ |
|写真 |マイクロソフト。Windows。写真 \_ 8wekyb3d8bbwe \! アプリ |
|古い設定 |HolographicSystemSettings_cw5n1h2txyewy!アプリ |
|新しい設定 |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!アプリ |
|ヒント |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> 写真またはビデオのキャプチャを有効にするには、キオスク アプリとしてカメラ アプリを有効にする必要があります。  
> <sup>2</sup> カメラ アプリを有効にする場合は、次の条件に注意してください。
> - [クイック アクション] メニューには、[写真] ボタンと [ビデオ] ボタンが表示されます。
> - また、画像を操作または取得できるアプリ (写真、メール、OneDrive など) を有効にする必要があります。  
>  
> <sup>3</sup>キオスク アプリとしてCortana有効にしていない場合でも、組み込みの音声コマンドが有効になります。 ただし、無効な機能に関連するコマンドは効果がありません。  
> <sup>4</sup>直接有効にMiracastすることはできません。 キオスク アプリMiracast有効にするには、カメラ アプリとデバイス ピッカー アプリを有効にします。

さらに、Mixed Reality Home をキオスク アプリとして設定できない。

ID の種類 [に基づくキオスク モードでサポートされるシナリオに戻る](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

## <a name="kiosk-xml-code-samples"></a>キオスク XML コード サンプル

1. [複数のアプリのグローバル割り当てアクセス プロファイル](#multiple-app-global-assigned-access-profile)
1. [デバイス所有者を除く複数のアプリのグローバル割り当てアクセス プロファイル](#multiple-app-global-assigned-access-profile-excluding-device-owners)
1. [ローカル アカウントまたは AAD ユーザー アカウントの複数のアプリ割り当てアクセス プロファイル](#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account)
1. [2 人の AAD ユーザー以上の複数のアプリ割り当てアクセス プロファイル](#multiple-app-assigned-access-profiles-for-two-aad-users-or-more)
1. [1 つの AAD グループに対して複数のアプリ割り当てアクセス プロファイル](#multiple-app-assigned-access-profile-for-one-aad-group)
1. [2 つの AAD グループ以上の複数のアプリ割り当てアクセス プロファイル](#multiple-app-assigned-access-profile-for-two-aad-groups-or-more)
1. [1 つの AAD アカウントと 1 つの AAD グループに対して複数のアプリ割り当てアクセス プロファイル](#multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group)
1. [訪問者に対する複数のアプリ割り当てアクセス プロファイル](#multiple-app-assigned-access-profile-for-visitors)

> [!NOTE]
> 要件に従って TODO アクションを置き換える。

### <a name="multiple-app-global-assigned-access-profile"></a>複数のアプリのグローバル割り当てアクセス プロファイル

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone.xml" highlight="18-20":::

[一覧に戻る](#kiosk-xml-code-samples) <br>
ID の種類 [に基づくキオスク モードでサポートされるシナリオに戻る](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-global-assigned-access-profile-excluding-device-owners"></a>デバイス所有者を除く複数のアプリのグローバル割り当てアクセス プロファイル

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone-excluding-device-owners.xml" highlight="18-20":::

[一覧に戻る](#kiosk-xml-code-samples) <br>
ID の種類 [に基づくキオスク モードでサポートされるシナリオに戻る](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account"></a>ローカル アカウントまたは AAD ユーザー アカウントの複数のアプリ割り当てアクセス プロファイル

:::code language="xml" source="samples/kiosk-sample-multi-app-local-or-aad-user.xml" highlight="18-20,51,55":::

[一覧に戻る](#kiosk-xml-code-samples) <br>
ID の種類 [に基づくキオスク モードでサポートされるシナリオに戻る](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profiles-for-two-aad-users-or-more"></a>2 人の AAD ユーザー以上の複数のアプリ割り当てアクセス プロファイル

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-users-or-more.xml" highlight="22-24,52,53,80,88":::

[一覧に戻る](#kiosk-xml-code-samples) <br>
ID の種類 [に基づくキオスク モードでサポートされるシナリオに戻る](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-group"></a>1 つの AAD グループに対して複数のアプリ割り当てアクセス プロファイル

:::code language="xml" source="samples/kiosk-sample-multi-app-one-aad-group.xml" highlight="28":::

[一覧に戻る](#kiosk-xml-code-samples) <br>
ID の種類 [に基づくキオスク モードでサポートされるシナリオに戻る](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-two-aad-groups-or-more"></a>2 つの AAD グループ以上の複数のアプリ割り当てアクセス プロファイル

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-groups-or-more.xml" highlight="22-24,52,53,83,94":::

[一覧に戻る](#kiosk-xml-code-samples) <br>
ID の種類 [に基づくキオスク モードでサポートされるシナリオに戻る](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group"></a>1 つの AAD アカウントと 1 つの AAD グループに対して複数のアプリ割り当てアクセス プロファイル

:::code language="xml" source="samples/kiosk-sample-multi-app-for-aad-user-and-aad-group.xml" highlight="22-24,52,53,80,91":::

[一覧に戻る](#kiosk-xml-code-samples) <br>
ID の種類 [に基づくキオスク モードでサポートされるシナリオに戻る](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-visitors"></a>訪問者に対する複数のアプリ割り当てアクセス プロファイル

:::code language="xml" source="samples/kiosk-sample-multi-app-visitor-user.xml" highlight="18-20":::

[一覧に戻る](#kiosk-xml-code-samples) <br>
ID の種類 [に基づくキオスク モードでサポートされるシナリオに戻る](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)
