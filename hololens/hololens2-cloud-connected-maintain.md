---
title: 展開ガイド–クラウドに接続された HoloLens 2 展開でのリモートアシストの維持
description: クラウドに接続されたネットワーク経由で HoloLens デバイスを管理するためのヒント
keywords: HoloLens、管理、クラウド接続、リモートアシスト、AAD、Azure AD、MDM、モバイルデバイス管理
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
ms.openlocfilehash: beee64159415c0635812463f81c0b5565e44e4a8
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196336"
---
# 保守-クラウド接続ガイド

## 更新プログラム

Windows Update for Business は、IT 管理者に対して Windows Update を中心とした追加の管理機能を提供するように設計されています。これには、更新プログラムをデバイスのグループに展開する機能や、更新プログラムをインストールするためのメンテナンス ウィンドウを定義する機能などが含まれています。

スケジュールされた日数、スケジュールされた時間、およびデバイスのアクティブ時間の設定などの [HoloLens の更新を管理](https://docs.microsoft.com/hololens/hololens-updates) する方法について説明します。これにより、稼働時間外に更新されます。

リモートアシスタンスは In-Box アプリであり、Microsoft ストアアプリを通じて更新できます。 Microsoft Store からダウンロードされたすべてのアプリは、Microsoft ストアアプリ自体を [通じて](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) 手動で更新することができます。

## サポート プラン

サポート計画は、適切な場所に配置することをお勧めします。 HoloLens デバイスでの登録プロセスのトラブルシューティングや、組織内での HoloLens デバイスの一般的な使用については、他のユーザーやグループがトレーニングアップしていることもあります。 ユーザーが問題をより迅速に解決できるようにするために、エスカレーションプロセスは次のような方法で処理されることをお勧めします。

1. サポートデスク。
2. HoloLens の専門家チーム
3. [HoloLens ドキュメント](https://docs.microsoft.com/hololens/)  / [HoloLens トラブルシューティングドキュメント](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [サポートに問い合わせ](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## 開発計画

デバイスが正常に登録されたら、基幹業務アプリ (LOB アプリ) をデバイスに展開する準備が整いました。 これらは、組織&#39;s ニーズに合わせて構築されたカスタムアプリです。

基幹業務アプリを既にお持ちの場合は、 [MDM でアプリを展開](https://docs.microsoft.com/hololens/app-deploy-intune)する準備ができたら&#39;ます。 &#39;d で別の方法を使用したい場合は、 [HoloLens 2 のアプリケーション展開の概要](https://docs.microsoft.com/hololens/app-deploy-overview) を確認して、LOB アプリをデバイスに展開するためのその他の方法について確認してください。

独自の LOB アプリを作成しているか、まだ作成プロセスの途中で&#39;ある場合は、mixed reality 開発ドキュメントを参照して[設計とプロトタイプ](https://docs.microsoft.com/windows/mixed-reality/design/design)の作成を開始するか、または[mixed reality の開発](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)を開始するための基本的な概念について学習します。

## デバイス管理 

このガイドでは、モバイルデバイス管理 (MDM) を設定する方法について説明していますが、デバイスの制限やポリシーを適用するためには採用していませんでした。 デバイス管理は、証明書をプッシュするか、さまざまなデバイスの制限を使用してアクセスを制限することで、アクセスを許可するために使うことができます。 

多くの場合、デバイスは、Bluetooth、VPN、USB などの接続制限を行うことができます。また、カメラやマイクへのアクセスをオフにすることもできます。 上記のいずれかが該当する場合は、 [デバイスの一般的な制限のページ](hololens-common-device-restrictions.md)を参照することをお勧めします。

使用できるその他の複雑なデバイス制限があります。 次に例を示します。

- [Settingspagevisibility](settings-uri-list.md)を使用して、設定アプリで表示できるページを制限します。ユーザーは、Wi-Fi 接続の変更など、調整する必要がある設定にのみアクセスできます。
- [キオスクモード](hololens-kiosk.md)を使って、デバイスのユーザーに表示される UI を制限します。 キオスクを設定すると、1つのアプリを表示したり、カスタムスタートページを持つ複数のアプリを表示したりできます。 キオスクでは、ユーザーごとに異なるエクスペリエンスを提供することもできます。  
- 特定のアプリまたはプロセスをまったく起動しないようにするための[Windows アプリケーション制御 (WDAC)](windows-defender-application-control-wdac.md) 。

デバイス管理またはデバイス制限のその他の方法については、次の手順に進み、「デバイス管理の概要」をご覧ください。

## 次のステップ

> [!div class="nextstepaction"]
> [「Csp とデバイス管理の概要」を参照してください。](hololens-csp-policy-overview.md)