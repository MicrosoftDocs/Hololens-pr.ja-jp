---
title: 展開ガイド – Dynamics 365 ガイドを使用した企業接続 HoloLens 2 - Maintain
description: Dynamics 365 Guides を使用して企業の接続ネットワークを使用して HoloLens 2 デバイスを維持する方法について学習します。
keywords: HoloLens、管理、企業接続、Dynamics 365 ガイド、AAD、Azure AD、MDM、モバイル デバイス管理
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f231e65e17ab053e34e7174e1ed7ff6e7a0a56b8
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448584"
---
# <a name="maintain---corporate-connected-guide"></a>メンテナンス - 企業向けコネクテッド ガイド

## <a name="update-hololens"></a>HoloLens を更新する

Windows Update for Business は、IT 管理者に対して Windows Update を中心とした追加の管理機能を提供するように設計されています。これには、更新プログラムをデバイスのグループに展開する機能や、更新プログラムをインストールするためのメンテナンス ウィンドウを定義する機能などが含まれています。

更新プログラムを管理する一般的な方法の 1 つは、30 日間の機能の延期を行う方法です。 これにより、管理者は新機能を更新してプレビューし、最初の手で知識を得て、新しい変更をサポート デスクに通知できます。

[HoloLens](https://docs.microsoft.com/hololens/hololens-updates)更新プログラム (スケジュールされた日、スケジュールされた時刻、デバイスのアクティブな時間の設定など) を管理して、勤務時間外に更新する方法について学習します。

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Dynamics 365 ガイド (および他のストア アプリ) を更新する方法

Dynamics 365 Guides は、In-Boxアプリであり、Microsoft Store アプリを通じて更新できます。 Microsoft Store を通じてダウンロードされたアプリはすべて [、Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) アプリ自体を介して手動で更新できます。

## <a name="how-to-update-lob-apps"></a>LOB アプリを更新する方法

LOB アプリは、Intune に追加されたのと同じ方法で更新できます。 Intune でアプリを更新するには、バージョン番号が大きい新しいアプリを既存のアプリ構成にアップロードします。 デバイスが Intune に同期すると、新しいアプリ バージョンが作成され、新しいアプリがダウンロードされ、古いアプリが置き換えられます。

1. 新しいアプリをアップロードするには[、MEM ポータル](https://endpoint.microsoft.com/#home)アプリ  ->  ****->すべてのアプリ****  ->  *TheNameOfYourApp プロパティに移動*  ->  **します。**
2. [アプリ情報] の横にある [編集] を **選択します。**
3. 更新するファイルの &quot; 選択の値については &quot; 、ファイルを選択します。
4. ここから、コンテキスト メニューを使用してファイル エクスプローラーを開き、新しいバージョンの LOB アプリをアップロードします。 必要に応じて依存関係を含める必要があります。

詳細: [HoloLens 用 Intune アプリの展開](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="development-plan"></a>開発計画

デバイスが正常に登録されると、デバイスに追加の LOB アプリを展開する準備が完了しました。 このガイドの期間中は、サンプル アプリを使用していますが、組織のニーズに合って構築されたカスタム アプリを使用する可能性が高い可能性があります。

LOB アプリが既に存在する場合は、MDM を使用して [アプリを展開する準備が整いました](https://docs.microsoft.com/hololens/app-deploy-intune)。 別の方法を使用する場合は [、HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) のアプリケーション展開の概要を確認して、LOB アプリをデバイスに展開する方法の詳細について説明します。

独自の LOB アプリをまだ作成していない場合や、まだ作成中の場合は、複合現実開発ドキュメントを確認して、[](https://docs.microsoft.com/windows/mixed-reality/design/design)設計とプロトタイプ作成を開始するか、複合現実開発を開始[](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)するコア概念を学ぶ必要があります。

## <a name="support-plan"></a>サポート プラン

サポート プランは、優れた機能です。 HoloLens デバイスでの登録プロセスのトラブルシューティングと、組織内での HoloLens デバイスの一般的な使用に関するトレーニングを受けたユーザー(またはグループ)が役に立ちます。 ユーザーが問題をより迅速に解決するために、エスカレーション プロセスは次の順序と同様の方法で処理されます。

1. サポート デスク。
2. HoloLens エキスパート チーム
3. [HoloLens Docs](https://docs.microsoft.com/hololens/)  / [HoloLens トラブルシューティング ドキュメント](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [サポートに問い合わせ](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>デバイス管理

このガイドでは、モバイル デバイス管理 (MDM) のセットアップについて説明し、それを使用して、一部のデバイス構成をセットアップし、Wi-Fi 証明書とプロキシの観点からアクセスを許可する設定を適用しました。 ただし、MDM を使用して、CSP とポリシーを使用してデバイスの制限を適用することもできます。

多くの場合、デバイスには、Bluetooth、VPN、USB などの接続制限が設定されている場合や、カメラやマイクへのアクセスをオフにすることもできます。 これらの興味がある場合は、一般的なデバイス制限ページ [をお読みください](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)。

他にも、使用できるより複雑なデバイス制限があります。 次のようにします。

- [SettingsPageVisibility](https://docs.microsoft.com/hololens/settings-uri-list)を使用して設定アプリで表示できるページを制限し、ユーザーが調整する必要がある設定 (Wi-Fi 接続の変更など) にのみアクセスできます。
- キオスク [モードを使用](https://docs.microsoft.com/hololens/hololens-kiosk) して、デバイス上のユーザーに表示される UI を制限します。 キオスクを設定して、1 つのアプリを表示するか、カスタムスタート ページを使用して複数のアプリを表示できます。 キオスクでは、さまざまなユーザーに異なるエクスペリエンスを表示できます。
- [Windows アプリケーションコントロール (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) を使用して、特定のアプリやプロセスを完全に起動し続ける。

デバイス管理またはデバイス制限の追加の方法について説明する場合は、次の手順に進み、「デバイス管理の概要」 [を参照してください](https://docs.microsoft.com/hololens/hololens-csp-policy-overview)。





