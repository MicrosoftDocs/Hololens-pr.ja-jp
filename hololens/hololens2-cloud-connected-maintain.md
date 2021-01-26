---
title: 展開ガイド - リモート アシストによるクラウド接続 HoloLens 2 の大規模な展開 - 保守
description: クラウド接続ネットワーク上で HoloLens デバイスを保守およびサポートするためのヒントを常に最新の状態に保つ。
keywords: HoloLens, 管理, クラウド接続, リモート アシスト, AAD, Azure AD, MDM, モバイル デバイス管理
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283898"
---
# 保守 - クラウド接続ガイド

## 更新プログラム

Windows Update for Business は、IT 管理者に対して Windows Update を中心とした追加の管理機能を提供するように設計されています。これには、更新プログラムをデバイスのグループに展開する機能や、更新プログラムをインストールするためのメンテナンス ウィンドウを定義する機能などが含まれています。

[HoloLens](https://docs.microsoft.com/hololens/hololens-updates)の更新プログラム (スケジュールされた日、スケジュールされた時刻、デバイスのアクティブ時間の設定など) を管理して、勤務時間外に更新する方法について学習します。

リモート アシストは、In-Boxアプリであり、Microsoft Store アプリを通じて更新できます。 Microsoft Store を通じてダウンロードされるアプリについては [、Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) アプリ自体を使って手動で更新できます。

## サポート プラン

サポート プランは、この計画に含め非常に優れたものです。 HoloLens デバイスでの登録プロセスのトラブルシューティングや組織内での HoloLens デバイスの一般的な使用に関するトレーニングを受けたユーザーやグループが役に立ちます。 ユーザーが問題をより迅速に解決するために、エスカレーション プロセスは次の順序と同様の方法で処理されます。

1. サポート デスク。
2. HoloLens エキスパート チーム
3. [HoloLens ドキュメント](https://docs.microsoft.com/hololens/)  / [HoloLens のトラブルシューティングに関するドキュメント](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [サポートに問い合わせ](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## 開発計画

デバイスが正常に登録されると、Line of Business アプリ (LOB アプリ) をデバイスに展開する準備が完了しました。 これらは、組織のニーズに合&#39;アプリです。

既に業務アプリがある場合は、MDM&#39;展開 [する準備が整っている必要があります](https://docs.microsoft.com/hololens/app-deploy-intune)。 別の&#39;方法が必要な場合は [、HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) のアプリケーション展開の概要を確認して、LOB アプリをデバイスに展開する方法の詳細を確認してください。

まだ独自&#39;LOB アプリを作成していない場合や、まだ作成中の場合は、Mixed Reality 開発ドキュメントを確認して、[](https://docs.microsoft.com/windows/mixed-reality/design/design)設計とプロトタイプの作成を開始したり[、Mixed Reality](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)開発を開始する中心概念を学ぶ必要があります。

## デバイス管理 

このガイドでは、モバイル デバイス管理 (MDM) のセットアップについて説明しましたが、デバイスの制限を適用したり、デバイスにポリシーを適用したりするために使用されません。 デバイス管理は、証明書をプッシュしてアクセスを許可したり、さまざまなデバイス制限でアクセスを制限したりするために使用できます。 

多くの場合、デバイスは Bluetooth、VPN、USB などの接続制限を持つ場合や、カメラやマイクへのアクセスをオフにすることもできます。 これらの関心がある場合は、一般的なデバイス制限の [ページをお読み](hololens-common-device-restrictions.md)ください。

使用できる他のより複雑なデバイス制限があります。 次に例を示します。

- [SettingsPageVisibility](settings-uri-list.md)を使用して設定アプリで表示できるページを制限し、ユーザーが調整する必要がある設定 (ユーザーの接続の変更など) にのみアクセスWi-Fiします。
- キオスク [モードを使](hololens-kiosk.md) って、デバイス上のユーザーに表示される UI を制限します。 キオスクは、1 つのアプリを表示するか、カスタムのスタート ページを持つ複数のアプリを表示するために設定できます。 キオスクでは、さまざまなユーザーに異なるエクスペリエンスを表示できます。  
- [Windows アプリケーション制御 (WDAC)](windows-defender-application-control-wdac.md) を使って、特定のアプリやプロセスが完全に起動しなきを維持します。

デバイス管理やデバイスの制限に関するさまざまな方法について詳しくは、次の手順に進み、「デバイス管理の概要」をご覧ください。

## 次のステップ

> [!div class="nextstepaction"]
> [CSP とデバイス管理の概要を読む](hololens-csp-policy-overview.md)