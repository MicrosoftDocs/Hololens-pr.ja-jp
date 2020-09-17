---
title: Csp とデバイス管理の概要を構成する
description: Csp、ポリシー、デバイスの管理を構成する方法。
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
ms.openlocfilehash: 4c31f7f92116031535a2dc2860e3f048a2311a39
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016794"
---
# Csp とデバイス管理の概要を構成する

IT 管理者は、HoloLens 2 でポリシー設定を定義して実装することができます。 使用する構成設定は展開シナリオによって異なり、企業のデバイスは幅広い制御機能を IT 部門に提供します。 Windows 10 では、構成サービスプロバイダー (CSP) は、デバイスの構成設定の読み取り、設定、変更、または削除を行うためのインターフェイスです。 これらの設定は、レジストリ キーまたはファイルにマップされます。 一部の構成サービスプロバイダーでは、WAP 形式をサポートしており、SyncML をサポートしていて、両方をサポートしています。 

Windows 10 ホログラフィック device management Csp の詳細については、「 [HoloLens デバイスでサポートされている](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)すべての csp の一覧」を参照してください。 IT 管理者は、デバイスでポリシー CSP を管理することもできます。 [HoloLens 2 でサポートされているポリシー](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)の完全な一覧を参照してください。

## 構成方法

### MDM で構成する
Csp とポリシーは、MDM システムに登録されている個人または企業のデバイスで簡単に管理できます。 デバイスが MDM ソリューションに登録されると、デバイスの構成を使用してデバイスまたはデバイスのセットを管理できるようになります。 [MDM で HoloLens デバイスを管理](hololens-mdm-configure.md)する方法の詳細については、こちらを参照してください。

### プロビジョニングパッケージを使った構成
HoloLens 2 では、カスタムプロビジョニングパッケージを介して、HoloLens 2 デバイスの一部の CSP 構成の設定もサポートされています。 通常、プロビジョニングパッケージは、MDM 以外で管理されるデバイスで利用できます。また、各デバイスに手動で適用する必要があります。 [HoloLens 用のカスタムプロビジョニングパッケージ](https://docs.microsoft.com/hololens/hololens-provisioning)の構築に関する情報を参照してください。 

## 構成 

### 一般的なデバイスの制限
デバイスの制限によっては、機能やデバイスへの接続を簡単に無効にすることができます。 詳細については、[一般的なデバイスの制限](hololens-common-device-restrictions.md)に関するページを参照してください。

### キオスクモード
キオスクモードを使用して、既定でどのアプリにアクセスできる id を制御します。 キオスクは、1つのアプリまたは複数のアプリの UI エクスペリエンスに使用できます。 [キオスクの構成] は、デバイスを使用するすべての人のための1つのアプリから、さまざまなグループ用のさまざまなアプリの選択までを対象としています。 これにより、「許可されたアプリ」が他のアプリを起動することはなくなり、これまでは意図していませんでした。 [キオスクモードの概要とその使い方](hololens-kiosk.md)については、こちらを参照してください。

### 設定ページの表示
設定アプリポリシーを使って、既定で設定にアクセスできる id を制御します。 このポリシーを設定すると、設定アプリは、選択したページのみを表示するか、選択したすべてのページを非表示にするように構成することができます。 [使用可能なページを構成する方法について](settings-uri-list.md)説明します。

この機能は、現時点では、 [Windows Insider ビルド](hololens-insider.md)でのみ avalible ます。 これを使用するデバイスがビルド 19041.1349 + であることを確認してください。

### WDAC
WDAC 構成を使って、システムがキオスクモードであるかどうかに関係なく、どのアプリ/プロセスを起動するかを制御します。
[「WDAC の概要」をご覧ください。](windows-defender-application-control-wdac.md)
