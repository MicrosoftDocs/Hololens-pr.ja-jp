---
title: ビジネス向け Microsoft Store
description: 複合現実アプリケーションをビジネスに発行ビジネス向け Microsoft Storeを使用する方法について学習します。
keywords: ビジネス向け Microsoft Store, msfb, アプリのデプロイ, ストア
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
ms.openlocfilehash: 5bc719539aaa254b8aacb05e24554152231f7e5a
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924330"
---
# <a name="microsoft-store-for-business"></a>ビジネス向け Microsoft Store

[ビジネス向け Microsoft Store ビジネス向け Microsoft Store](/microsoft-store/microsoft-store-for-business-overview)は、主に、一部の市場で無料および有料のアプリを検索、取得、管理、配布する柔軟な方法を使用して、企業や組織の IT 意思決定者と管理者を対象に設計され、ボリューム内の Windows 10 デバイスに提供されます。 

1 つのインベントリMicrosoft Storeアプリとプライベートの業務アプリを管理し、必要に応じてライセンスを割り当て、再使用できます。 また、組織に最適な配布方法を選択することもできます。アプリを個人やチームに直接割り当てるか、Microsoft Store のプライベート ページにアプリを発行するか、管理ソリューションに接続してその他のオプションを選択することもできます。

エンド ビジネス向け Microsoft Store使用すると、エンド ユーザーはアプリを起動Microsoft Storeします。 起動すると、ユーザーは組織名のタブを選択できます。その後、ユーザーは自分またはデバイスで使用できるアプリと一緒に表示されます。

> [!Note]
> ビジネス向け Microsoft Storeアプリはデバイスに自動的にダウンロード (プッシュ) されません。 ただし、デバイス管理 (MDM) ビジネス向け Microsoft Storeに関連付け、アプリをターゲットにし、デバイスに同期することもできます。

次のページを参照して、次のページを参照して、次のページを参照ビジネス向け Microsoft Store。

* [アプリケーションのインストールに使用されるアクセス許可のレベル](/mem/intune/configuration/device-restrictions-windows-holographic#app-store)
* [ビジネス向けストアにアプリを追加する方法](/mem/intune/apps/store-apps-windows)
* [従業員のグループにアプリを割り当てる方法](/mem/intune/apps/windows-store-for-business)

アプリケーションを関連付ビジネス向け Microsoft Store、Intune[に関連付ビジネス向け Microsoft Storeに関するページを参照してください](/mem/intune/apps/windows-store-for-business#associate-your-microsoft-store-for-business-account-with-intune)。

> [!Tip]
> Advanced Recovery [](/microsoft-store/distribute-offline-apps) Companion (ARC) や Windows Configuration Designer (WCD) などのアプリを使用する場合のオフライン アプリの配布の詳細について説明します。

## <a name="use-only-private-store-apps-for-microsoft-store"></a>プライベート ストア アプリのみを使用してMicrosoft Store

- [Holographic バージョンWindows 21H2 で導入されました](hololens-release-notes.md#windows-holographic-version-21h2)。

RequirePrivateStoreOnly ポリシーが有効になっているHoloLens。 このポリシーにより、組織Microsoft Storeプライベート ストアのみを表示するようにアプリを構成できます。 使用可能にしたアプリにのみアクセスを制限する。

[ApplicationManagement/RequirePrivateStoreOnly の詳細を確認する](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

## <a name="smart-retry-for-app-updates"></a>アプリ更新プログラムのスマート再試行

- [Holographic バージョンWindows 21H2 で導入されました](hololens-release-notes.md#windows-holographic-version-21h2)。

HoloLens に対して有効にされたのは、IT 管理者が定期的または 1 回の日付を設定して、アプリの使用が原因で更新が失敗したアプリを再起動し、更新プログラムの適用を許可する新しいポリシーです。 これらは、スケジュールされた時刻やサインインなど、いくつかの異なるトリガーに基づいて設定できます。 このポリシーの使用方法の詳細については [、「ApplicationManagement/ScheduleForceRestartForUpdateFailures 」を参照してください](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)。