---
title: 展開ガイド– Dynamics 365 を使用した企業接続 HoloLens 2 ガイド-メンテナンス
description: Dynamics 365 ガイドを使用して、企業に接続されたネットワーク経由で HoloLens 2 デバイスを保守する方法について説明します。
keywords: HoloLens, 管理, 企業接続, Dynamics 365 ガイド, AAD, Azure AD, MDM, モバイルデバイス管理
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309500"
---
# <a name="maintain---corporate-connected-guide"></a>保守-企業の接続ガイド

## <a name="update-hololens"></a>HoloLens を更新する

Windows Update for Business は、IT 管理者に対して Windows Update を中心とした追加の管理機能を提供するように設計されています。これには、更新プログラムをデバイスのグループに展開する機能や、更新プログラムをインストールするためのメンテナンス ウィンドウを定義する機能などが含まれています。

更新プログラムを管理する一般的な方法の1つは、機能の遅延を30日間にすることです。 これにより、管理者は新しい機能を更新してプレビューし、最初の知識を取得し、新しい変更をサポートデスクに通知することができます。

スケジュールされた日、スケジュールされた時刻、デバイスのアクティブ時間の設定など、 [HoloLens の更新を管理](https://docs.microsoft.com/hololens/hololens-updates)する方法について説明します。これにより、勤務時間外に更新されるようになります。

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Dynamics 365 ガイド (およびその他のストアアプリ) を更新する方法

Dynamics 365 ガイドは In-Box アプリであり、Microsoft Store アプリを使用して更新できます。 Microsoft Store によってダウンロードされたすべてのアプリについて、Microsoft Store アプリ自体を [使用して](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) 手動で更新することができます。

## <a name="how-to-update-lob-apps"></a>LOB アプリを更新する方法

LOB アプリは、Intune に追加したときと同じ方法で更新できます。 Intune でアプリを更新するには、新しいバージョン番号を持つ新しいアプリを既存のアプリ構成にアップロードします。 デバイスが Intune に同期すると、新しいバージョンのアプリがあることが確認され、新しいアプリがダウンロードされて、古いアプリが置き換えられます。

1. 新しいアプリをアップロードするには、[[メモリポータル](https://endpoint.microsoft.com/#home)  ->  **アプリ**>-すべての **アプリ** の TheNameOfYourApp] プロパティに移動し  ->    ->  **ます。**
2. [アプリ情報] の横にある [編集] を選択し **ます。**
3. &quot;[更新するファイルを選択してください] の値とし &quot; て、ファイルを選択します。
4. ここから、コンテキストメニューを使用してファイルエクスプローラーを開き、新しいバージョンの LOB アプリをアップロードします。 必要に応じて依存関係を含めてください。

詳細については[、「HoloLens の Intune アプリの展開」を](https://docs.microsoft.com/hololens/app-deploy-intune)参照してください。

## <a name="development-plan"></a>開発計画

デバイスが正常に登録されたら、より多くの LOB アプリをデバイスにデプロイする準備が整いました。 このガイドの期間中はサンプルアプリを使用していますが、組織のニーズに合わせて構築されたカスタムアプリを使用することが必要になる可能性が高くなります。

LOB アプリを既にお持ちの場合は、MDM を [使用](https://docs.microsoft.com/hololens/app-deploy-intune)してアプリをデプロイする準備ができています。 別の方法を使用する場合は、 [「HoloLens 2 のアプリケーション展開の概要」](https://docs.microsoft.com/hololens/app-deploy-overview) を参照して、LOB アプリをデバイスにデプロイする方法の詳細を確認してください。

独自の LOB アプリをまだ作成していない場合、またはまだ作成プロセスが完了している場合は、mixed reality の開発に関するドキュメントを参照して、[設計とプロトタイプ](https://docs.microsoft.com/windows/mixed-reality/design/design)作成を開始するか、または[mixed reality 開発を開始](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)するための主要な概念を学習してください。

## <a name="support-plan"></a>サポート計画

サポートプランは、適切な場所に配置することをお勧めします。 HoloLens デバイスでの登録プロセスのトラブルシューティングに関するトレーニングを受けているユーザーやグループがあれば、組織内での HoloLens デバイスの一般的な使用が役立ちます。 ユーザーがより迅速に問題を解決できるようにするために、エスカレーションプロセスは次の順序と同様の方法で処理することをお勧めします。

1. サポートデスク。
2. HoloLens エキスパートチーム
3. [HoloLens ドキュメント](https://docs.microsoft.com/hololens/)  / [HoloLens のトラブルシューティングに関するドキュメント](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [サポートにお問い合わせください](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>デバイス管理

このガイドでは、モバイルデバイス管理 (MDM) を設定し、それを使用して一部のデバイス構成を設定し、Wi-Fi 証明書とプロキシの観点からアクセスを許可する設定を適用する方法について説明します。 ただし、MDM を使用して、Csp とポリシーを使用してデバイスの制限を適用することもできます。

多くの場合、デバイスには、Bluetooth、VPN、USB などの接続制限や、カメラやマイクへのアクセスをオフにすることもできます。 これらのいずれかが興味をお持ちの場合は、 [一般的なデバイスの制限に関するページ](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)をお読みになることをお勧めします。

使用できるデバイスには、他にも複雑な制限があります。 例:

- [Settingspagevisibility](https://docs.microsoft.com/hololens/settings-uri-list)を使用して設定アプリで表示できるページ数を制限することで、ユーザーは Wi-Fi 接続の変更など、調整が必要な設定にのみアクセスできるようになります。
- [キオスクモード](https://docs.microsoft.com/hololens/hololens-kiosk)を使用して、デバイス上のユーザーに表示される UI を制限します。 キオスクを設定して、1つのアプリ、またはカスタムスタートページを持つ複数のアプリを表示することができます。 キオスクでは、ユーザーごとに異なるエクスペリエンスを提示することもできます。
- 特定のアプリまたはプロセスを完全に起動しないようにするための[Windows アプリケーション制御 (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 。

デバイス管理またはデバイスの制限のその他の方法について学習する場合は、次の手順を実行し、 [デバイス管理の概要](https://docs.microsoft.com/hololens/hololens-csp-policy-overview)に関するページを参照してください。





