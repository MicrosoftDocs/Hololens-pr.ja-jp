---
title: デプロイ ガイド – 企業接続HoloLens 2 Dynamics 365 Guides - メンテナンス
description: デバイスを使用して企業の接続HoloLens 2ネットワークを使用してデバイスを管理する方法Dynamics 365 Guides。
keywords: HoloLens、管理、企業接続、Dynamics 365 Guides、AAD、Azure AD、MDM、Mobile デバイス管理
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
ms.openlocfilehash: 0176e816f167499574607bc16c8fbd6bde757daf
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033435"
---
# <a name="maintain---corporate-connected-guide"></a>メンテナンス - 企業接続ガイド

## <a name="update-hololens"></a>HoloLens を更新する

Windows Update for Business は、IT 管理者に対して Windows Update を中心とした追加の管理機能を提供するように設計されています。これには、更新プログラムをデバイスのグループに展開する機能や、更新プログラムをインストールするためのメンテナンス ウィンドウを定義する機能などが含まれています。

更新プログラムを管理する一般的な方法の 1 つは、機能の遅延を 30 日間実行する方法です。 これにより、管理者は新機能を更新してプレビューし、最初の知識を得て、新しい変更についてサポート デスクに通知することができます。

スケジュールされた日[、スケジュールHoloLens](/hololens/hololens-updates)時間、デバイスのアクティブな時間の設定など、更新プログラムを管理して、作業時間外に更新する方法について学習します。

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>アプリ (および他Dynamics 365 Guidesアプリ) を更新する方法

Dynamics 365 GuidesはIn-Boxであり、アプリを使用して更新Microsoft Storeできます。 アプリを使用してダウンロードMicrosoft Store、アプリ自体を手動でMicrosoft Store更新できます[](/hololens/holographic-store-apps#update-apps)。

## <a name="how-to-update-lob-apps"></a>LOB アプリを更新する方法

LOB アプリは、Intune に追加されたのと同じ方法で更新できます。 Intune でアプリを更新するには、バージョン番号が大きい新しいアプリを既存のアプリ構成にアップロードします。 デバイスが Intune と同期すると、新しいバージョンのアプリがインストールされ、新しいアプリがダウンロードされ、古いアプリが置き換えられます。

1. 新しいアプリをアップロードするには [、MEM ポータル](https://endpoint.microsoft.com/#home)の [アプリ]  ->   -> [すべての **アプリ**]  ->  *[TheNameOfYourApp の* プロパティ] に移動  ->  **します。**
2. [アプリ情報] の横にある [編集] を **選択します。**
3. [更新するファイル &quot; の選択] の値として &quot; 、ファイルを選択します。
4. ここから、コンテキスト メニューを使用してエクスプローラーを開き、新しいバージョンの LOB アプリをアップロードします。 必要に応じて依存関係を含める必要があります。

詳細については、以下をご覧ください[。Intune App Deployment for HoloLens](/hololens/app-deploy-intune)

## <a name="development-plan"></a>開発計画

デバイスが正常に登録されると、より多くの LOB アプリをデバイスに展開する準備が完了しました。 このガイドの期間中は、サンプル アプリを使用していますが、組織のニーズに合って構築されたカスタム アプリを使用する可能性が高い可能性があります。

既に LOB アプリがある場合は、MDM を使用してアプリ [をデプロイする準備が整います](/hololens/app-deploy-intune)。 別の方法を使用する場合は、HoloLens 2 のアプリケーション展開の概要に関するページを参照して[、LOB](/hololens/app-deploy-overview)アプリをデバイスに展開する方法の詳細を確認してください。

独自の LOB アプリをまだ作成していない場合、またはまだ作成中の場合は、Mixed Reality 開発に関する[](/windows/mixed-reality/design/design)ドキュメントを参照して、設計とプロトタイプ作成を開始するか、Mixed [Reality](/windows/mixed-reality/discover/get-started-with-mr)開発を開始する主要な概念を学習してください。

## <a name="support-plan"></a>サポート計画

サポート プランは、優れた機能です。 HoloLens デバイスでの登録プロセスのトラブルシューティングと、組織内の HoloLens デバイスの一般的な使用に関するトレーニングを受けたユーザー(グループ) が役に立ちます。 ユーザーが問題をより迅速に解決するには、エスカレーション プロセスを次の順序と同様の方法で処理してください。

1. サポート デスク。
2. HoloLensエキスパート チーム
3. [HoloLens Docs](/hololens/)  / [HoloLensトラブルシューティング ドキュメント](/hololens/hololens-troubleshooting)
4. [サポートに問い合わせ](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>デバイス管理

このガイドでは、Mobile デバイス管理 (MDM) の設定について説明し、それを使用していくつかのデバイス構成を設定し、Wi-Fi 証明書とプロキシの観点からアクセスを許可する設定を適用しました。 ただし、MDM を使用して、CSP とポリシーを介してデバイスの制限を適用することもできます。

多くの場合、デバイスには Bluetooth、VPN、USB などの接続制限がある場合や、カメラやマイクへのアクセスをオフにすることもできます。 これらの関心がある場合は、一般的なデバイス制限に関する [ページをお読みください](/hololens/hololens-common-device-restrictions)。

使用できるその他の複雑なデバイス制限があります。 例:

- [SettingsPageVisibility](/hololens/settings-uri-list)を使用して 設定 アプリで表示できるページを制限すると、ユーザーは、Wi-Fi 接続の変更など、調整する必要がある設定にのみアクセスできます。
- キオスク [モードを使用](/hololens/hololens-kiosk) して、デバイス上のユーザーに表示される UI を制限します。 キオスクを設定して、1 つのアプリを表示するか、カスタム スタート ページを使用して複数のアプリを表示できます。 キオスクでは、異なるユーザーに異なるエクスペリエンスを表示できます。
- [Windowsアプリケーション制御 (WDAC)](/hololens/windows-defender-application-control-wdac)を使用して、特定のアプリまたはプロセスが完全に起動しなきにし続ける必要があります。

デバイス管理またはデバイス制限の追加の方法について学習する場合は、次の手順に進み、「概要」を参照デバイス管理 [してください](/hololens/hololens-csp-policy-overview)。





