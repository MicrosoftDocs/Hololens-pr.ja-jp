---
title: Csp およびデバイス管理の構成の概要
description: モバイルデバイス管理とプロビジョニングパッケージを使用して、Csp、ポリシー、およびデバイス管理を構成する方法について説明します。
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
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309721"
---
# <a name="configure-csps-and-device-management-overview"></a>Csp およびデバイス管理の構成の概要

IT 管理者は、HoloLens 2 でポリシー設定を定義および実装できます。 使用する構成設定は展開シナリオによって異なり、企業のデバイスは幅広い制御機能を IT 部門に提供します。 Windows 10 では、構成サービスプロバイダー (CSP) は、デバイスの構成設定を読み取り、設定、変更、または削除するためのインターフェイスです。 これらの設定は、レジストリ キーまたはファイルにマップされます。 一部の構成サービスプロバイダーは、WAP 形式をサポートしています。また、SyncML をサポートしており、その両方をサポートしています。

Windows 10 Holographic デバイス管理 Csp の詳細については、「 [HoloLens デバイスでサポートされる csp](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)の完全な一覧」を参照してください。
IT 管理者は、デバイスでポリシー CSP を管理することもできます。 [HoloLens 2 でサポートされているポリシー](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)csp の完全な一覧を参照してください。

## <a name="configuration-methods"></a>構成方法

### <a name="configure-with-mdm"></a>MDM を使用して構成する

Csp とポリシーは、MDM システムに登録されている個人または会社のデバイスで簡単に管理できます。 デバイスが MDM ソリューションに登録されると、そのデバイスを管理できるようになり、デバイスの構成を使用してデバイスのセットを管理できるようになります。 MDM を使用して [HoloLens デバイスを管理](hololens-mdm-configure.md)する方法の詳細については、こちらを参照してください。

### <a name="configure-with-provisioning-packages"></a>プロビジョニングパッケージを使用して構成する

HoloLens 2 では、カスタムプロビジョニングパッケージを使用して、HoloLens 2 デバイスに限定された CSP 構成を設定することもできます。 プロビジョニングパッケージは、通常、MDM 以外の管理対象デバイスに使用され、各デバイスに手動で適用する必要があります。 [HoloLens 用カスタムプロビジョニングパッケージ](https://docs.microsoft.com/hololens/hololens-provisioning)の構築については、こちらを参照してください。

## <a name="configurations"></a>構成

### <a name="common-device-restrictions"></a>一般的なデバイスの制限

デバイスの制限としては、単純に、デバイスへの機能や接続を無効にすることがあります。 これらの詳細については、[一般的なデバイスの制限](hololens-common-device-restrictions.md)に関するページを参照してください。

### <a name="kiosk-modes"></a>キオスクモード

キオスクモードを使用すると、どの id が既定でどのアプリにアクセスできるかを制御できます。 キオスクは、1つのアプリまたは複数のアプリの UI エクスペリエンスに使用できます。 キオスクの構成は、デバイスを使用するすべてのユーザーを対象とした1つのアプリから、さまざまなグループに対して異なるアプリを選択できます。 キオスクモードでは、"許可されたアプリ" が他のアプリの起動を停止することはなく、これまでは想定されていませんでした。 [キオスクモードとその使用方法については](hololens-kiosk.md)、こちらを参照してください。

### <a name="settings-page-visibility"></a>[設定] ページの表示

設定アプリポリシーを使用して、既定で設定にアクセスできる id を制御します。 このポリシーを使用して、設定アプリを構成して、選択したページのみを表示するか、選択したすべてのページを非表示にすることができます。 [ページを構成する方法については、「」を参照して](settings-uri-list.md)ください。

この機能は、現在、 [Windows Insider ビルド](hololens-insider.md)でのみ使用できます。 この機能を使用する予定のデバイスがビルド 19041.1349 + にあることを確認します。

### <a name="wdac"></a>WDAC

システムがキオスクモードであるかどうかに関係なく、どのアプリ/プロセスを起動できるかを制御するには、WDAC 構成を使用します。
[「WDAC の概要」を参照してください。](windows-defender-application-control-wdac.md)
