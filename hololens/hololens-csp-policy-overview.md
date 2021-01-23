---
title: CSP の構成とデバイス管理の概要
description: モバイル デバイス管理とプロビジョニング パッケージを使用して、CSP、ポリシー、デバイス管理を構成する方法について説明します。
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283248"
---
# CSP の構成とデバイス管理の概要

IT 管理者は、HoloLens 2 でポリシー設定を定義して実装できます。 使用する構成設定は展開シナリオによって異なり、企業のデバイスは幅広い制御機能を IT 部門に提供します。 Windows 10 では、構成サービス プロバイダー (CSP) は、デバイスの構成設定を読み取り、設定、変更、または削除するインターフェイスです。 これらの設定は、レジストリ キーまたはファイルにマップされます。 一部の構成サービス プロバイダーは WAP 形式をサポートし、一部は SyncML をサポートし、一部は両方をサポートします。

Windows 10 Holographic デバイス管理の CSP について詳しくは [、HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)デバイスでサポートされている CSP の一覧をご覧ください。
IT 管理者はデバイスでポリシー CSP を管理することもできます [。HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)でサポートされているポリシー CSP の完全な一覧をご覧ください。

## 構成方法

### MDM を使用して構成する

CSP とポリシーは、MDM システムに登録されている個人または企業のデバイスで簡単に管理できます。 MDM ソリューションにデバイスを登録すると、そのデバイスまたはデバイス構成を使用してデバイスのセットを管理できます。 MDM を使って [HoloLens デバイスを管理する方法について詳しくは、次をご覧ください](hololens-mdm-configure.md)。

### プロビジョニング パッケージを使用して構成する

HoloLens 2 では、カスタム プロビジョニング パッケージによる HoloLens 2 デバイスの CSP 構成の制限付きセットの設定もサポートされています。 プロビジョニング パッケージは、通常、MDM 以外の管理対象デバイスで利用され、各デバイスに手動で適用する必要があります。 [HoloLens 用のカスタム プロビジョニング パッケージの構築に関する情報を読み取る](https://docs.microsoft.com/hololens/hololens-provisioning)。

## 構成

### 一般的なデバイスの制限

一部のデバイスの制限は単純で、機能やデバイスへの接続を無効にします。 これらの詳細については、一般的なデバイスの [制限に関する記事を参照してください。](hololens-common-device-restrictions.md)

### キオスク モード

キオスク モードを使って、既定でどのアプリにアクセスできる ID を制御します。 キオスクは、1 つのアプリまたは複数のアプリの UI エクスペリエンスに使用できます。 キオスク構成は、デバイスを使うユーザー向け 1 つのアプリから、グループごとに異なる選択のアプリまでです。 キオスク モードでは、"許可されたアプリ" が他のアプリの起動を停止するのではなく、これまで意図された動作ではありません。 詳しくは、 [キオスク モードと使い方に関する記事をご覧ください](hololens-kiosk.md)。

### [設定] ページの可視性

設定アプリ ポリシーを使って、既定で設定にアクセスできる ID を制御します。 このポリシーを使って、選択したページのみを表示するか、選択したページを非表示にするように設定アプリを構成できます。 [使用可能なページを構成する方法についてお読みください](settings-uri-list.md)。

この機能は現在 [、Windows Insider ビルドでのみ使用できます](hololens-insider.md)。 この機能を使用するデバイスがビルド 19041.1349 以上のデバイスにインストールされている必要があります。

### WDAC

WDAC 構成を使って、システムがキオスク モードかどうかに関係なく、起動を許可/禁止するアプリ/プロセスを制御します。
[WDAC の概要をご覧ください。](windows-defender-application-control-wdac.md)
