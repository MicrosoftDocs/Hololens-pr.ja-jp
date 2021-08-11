---
title: CSP の構成とデバイス管理の概要
description: Mobile デバイス管理 およびプロビジョニング パッケージを使用して、CSP、ポリシー、デバイス管理を構成する方法について説明します。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ed28033f10f7a6d0e826775e95d040d0cac7f9e9c6266acd6975d3532f6d8067
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664243"
---
# <a name="configure-csps-and-device-management-overview"></a>CSP の構成とデバイス管理の概要

IT 管理者は、ポリシー設定を定義して実装HoloLens 2。 使用する構成設定は展開シナリオによって異なり、企業のデバイスは幅広い制御機能を IT 部門に提供します。 このWindows 10構成サービス プロバイダー (CSP) は、デバイスの構成設定を読み取り、設定、変更、または削除するインターフェイスです。 これらの設定は、レジストリ キーまたはファイルにマップされます。 一部の構成サービス プロバイダーは WAP 形式をサポートし、一部は SyncML をサポートし、一部は両方をサポートします。

デバイス管理の WINDOWS 10 HOLOGRAPHICの詳細については、デバイスでサポートされている CSP の完全な一[覧をHoloLensしてください](/windows/client-management/mdm/configuration-service-provider-reference#hololens)。
IT 管理者は、デバイスでポリシー CSP を管理することもできます。詳細については、 でサポートされているポリシー CSP の完全な一覧[をHoloLens 2。](/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="configuration-methods"></a>構成方法

### <a name="configure-with-mdm"></a>MDM を使用して構成する

CSP とポリシーは、MDM システムに登録されている個人または企業のデバイスで簡単に管理できます。 MDM ソリューションにデバイスを登録すると、そのデバイスまたはデバイスのセットをデバイス構成を使用して管理できます。 MDM を使用してデバイスを[管理する方法HoloLensを確認してください](hololens-mdm-configure.md)。

### <a name="configure-with-provisioning-packages"></a>プロビジョニング パッケージを使用して構成する

HoloLens 2では、カスタム プロビジョニング パッケージを使用して、HoloLens 2デバイスの CSP 構成の制限付きセットを設定することもできます。 プロビジョニング パッケージは通常、MDM 以外のマネージド デバイスに利用され、各デバイスに手動で適用する必要があります。 のカスタム プロビジョニング パッケージの[構築に関する情報をHoloLens。](hololens-provisioning.md)

## <a name="configurations"></a>構成

### <a name="common-device-restrictions"></a>一般的なデバイスの制限

一部のデバイスの制限は、デバイスへの機能または接続を無効にした単純な制限です。 これらの詳細については、一般的なデバイスの [制限に関する記事を参照してください。](hololens-common-device-restrictions.md)

### <a name="kiosk-modes"></a>キオスク モード

キオスク モードを使用して、既定でどの ID にどのアプリにアクセス権を持つのか制御します。 キオスクは、1 つのアプリまたは複数のアプリ UI エクスペリエンスに使用できます。 キオスク構成は、デバイスを使用するユーザー向け 1 つのアプリから、異なるグループのアプリの異なる選択まで、さまざまな範囲です。 キオスク モードでは、"許可されたアプリ" が他のアプリの起動を停止するのではなく、これまでは意図して動作しません。 詳細については、キオスク [モードと、その使い方に関する記事を参照してください](hololens-kiosk.md)。

### <a name="settings-page-visibility"></a>設定ページの表示

既定設定アクセス権を持つ ID を制御するには、アプリ ポリシーを使用します。 このポリシーを使用設定選択したページのみを表示するか、選択したページをすべて非表示にするようにアプリを構成できます。 [使用可能なページを構成する方法を参照してください](settings-uri-list.md)。

この機能は現在、Insider ビルド[の Windowsでのみ使用できます](hololens-insider.md)。 この機能を使用するデバイスがビルド 19041.1349 以上に含まれる必要があります。

### <a name="wdac"></a>WDAC

WDAC 構成を使用して、システムがキオスク モードかどうかに関係なく、起動を許可/禁止するアプリ/プロセスを制御します。
[WDAC の概要を参照してください。](windows-defender-application-control-wdac.md)
