---
title: デプロイガイド–クラウドに接続された HoloLens 2 の大規模なデプロイとリモートサポート
description: クラウドに接続されたネットワーク経由での HoloLens デバイスの保守とサポートに関するヒントをご覧ください。
keywords: HoloLens、管理、クラウド接続、リモートアシスタンス、AAD、Azure AD、MDM、モバイルデバイス管理
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309784"
---
# <a name="maintain---cloud-connected-guide"></a>保守-クラウド接続ガイド

## <a name="updates"></a>更新プログラム

Windows Update for Business は、IT 管理者に対して Windows Update を中心とした追加の管理機能を提供するように設計されています。これには、更新プログラムをデバイスのグループに展開する機能や、更新プログラムをインストールするためのメンテナンス ウィンドウを定義する機能などが含まれています。

スケジュールされた日、スケジュールされた時刻、デバイスでのアクティブ時間の設定など、 [HoloLens の更新を管理](https://docs.microsoft.com/hololens/hololens-updates) して、勤務時間外に更新する方法について説明します。

リモートアシスタンスは In-Box アプリであり、Microsoft Store アプリを使用して更新できます。 Microsoft Store によってダウンロードされたすべてのアプリについて、Microsoft Store アプリ自体を [使用して](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) 手動で更新することができます。

## <a name="support-plan"></a>サポート計画

サポートプランは、適切な場所に配置することをお勧めします。 HoloLens デバイスでの登録プロセスのトラブルシューティングに関する他のユーザーやグループを持っている場合、または組織内での HoloLens デバイスの一般的な使用が役立ちます。 ユーザーがより迅速に問題を解決できるようにするために、エスカレーションプロセスは次の順序と同様の方法で処理することをお勧めします。

1. サポートデスク。
2. HoloLens エキスパートチーム
3. [HoloLens ドキュメント](https://docs.microsoft.com/hololens/)  / [HoloLens のトラブルシューティングに関するドキュメント](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [サポートにお問い合わせください](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>開発計画

デバイスが正常に登録されると、基幹業務アプリ (LOB アプリ) をデバイスに展開する準備が整いました。 これらは、組織&#39;のニーズに合わせて構築されたカスタムアプリです。

基幹業務アプリを既にお持ちの場合は、 [MDM を使用してアプリをデプロイ](https://docs.microsoft.com/hololens/app-deploy-intune)する準備が&#39;ます。 &#39;d で別の方法を選択する場合は、 [「HoloLens 2 のアプリケーション展開の概要」](https://docs.microsoft.com/hololens/app-deploy-overview) を参照して、LOB アプリをデバイスにデプロイする方法の詳細を確認してください。

独自の LOB アプリをまだ作成していない&#39;場合、またはまだ作成プロセスが完了している場合は、mixed reality の開発に関するドキュメントを参照して、[設計とプロトタイプ](https://docs.microsoft.com/windows/mixed-reality/design/design)作成を開始するか、 [mixed reality 開発](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)を開始するための主要な概念を学習してください。

## <a name="device-management"></a>デバイス管理 

このガイドではモバイルデバイス管理 (MDM) のセットアップについて説明しましたが、デバイスの制限を適用するために使用されていなかったか、デバイスにポリシーが適用されました。 デバイス管理を使用して、証明書をプッシュしてアクセスを許可するか、さまざまなデバイス制限を使用してアクセスを制限することができます。 

多くの場合、デバイスには、Bluetooth、VPN、USB などの接続制限や、カメラやマイクへのアクセスをオフにする機能があります。 これらのいずれかに興味がある場合は、 [一般的なデバイスの制限に関するページ](hololens-common-device-restrictions.md)をお読みになることをお勧めします。

使用できるデバイスには、他にも複雑な制限があります。 例:

- [Settingspagevisibility](settings-uri-list.md)を使用して設定アプリで表示できるページ数を制限することで、ユーザーは Wi-Fi 接続の変更など、調整が必要な設定にのみアクセスできるようになります。
- [キオスクモード](hololens-kiosk.md)を使用して、デバイス上のユーザーに表示される UI を制限します。 キオスクを設定して、1つのアプリ、またはカスタムスタートページを持つ複数のアプリを表示することができます。 キオスクでは、ユーザーごとに異なるエクスペリエンスを提示することもできます。  
- 特定のアプリまたはプロセスを完全に起動しないようにするための[Windows アプリケーション制御 (WDAC)](windows-defender-application-control-wdac.md) 。

デバイス管理またはデバイスの制限の別の方法について学習する場合は、次の手順を実行し、デバイス管理の概要に関するページを参照してください。

## <a name="next-step"></a>次のステップ

> [!div class="nextstepaction"]
> [Csp とデバイス管理の概要を読む](hololens-csp-policy-overview.md)