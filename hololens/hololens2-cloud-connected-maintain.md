---
title: デプロイ ガイド – クラウドに接続されたHoloLens 2大規模なデプロイ - Remote Assist - メンテナンス
description: クラウドに接続されたネットワークを使用してデバイスを管理およびサポートHoloLens関するヒントを常に確認してください。
keywords: HoloLens、管理、クラウド接続、Remote Assist、AAD、Azure AD、MDM、Mobile デバイス管理
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
ms.openlocfilehash: 941de296d59713c098718b16431fa793bd1b60e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635162"
---
# <a name="maintain---cloud-connected-guide"></a>メンテナンス - クラウド接続ガイド

## <a name="updates"></a>更新プログラム

Windows Update for Business は、IT 管理者に対して Windows Update を中心とした追加の管理機能を提供するように設計されています。これには、更新プログラムをデバイスのグループに展開する機能や、更新プログラムをインストールするためのメンテナンス ウィンドウを定義する機能などが含まれています。

スケジュールされた日、[スケジュールHoloLens、](/hololens/hololens-updates)デバイスのアクティブな時間の設定など、スケジュールされた更新プログラムを管理して、作業時間外に更新する方法について学習します。

Remote AssistはIn-Boxであり、アプリを使用して更新Microsoft Storeできます。 アプリを介してダウンロードMicrosoft Storeアプリ自体を使用して更新Microsoft Store更新できます[](/hololens/holographic-store-apps#update-apps)。

## <a name="support-plan"></a>サポート計画

サポート プランは、優れた機能です。 HoloLens デバイスでの登録プロセスのトラブルシューティングと、組織内の HoloLens デバイスの一般的な使用に関するトレーニングを受けたユーザーやグループが役に立ちます。 ユーザーが問題をより迅速に解決するには、エスカレーション プロセスを次の順序と同様の方法で処理してください。

1. サポート デスク。
2. HoloLensエキスパート チーム
3. [HoloLens Docs](/hololens/)  / [HoloLensトラブルシューティング ドキュメント](/hololens/hololens-troubleshooting)
4. [サポートに問い合わせ](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>開発計画

デバイスが正常に登録されると、Line of Business アプリ (LOB アプリ) をデバイスに展開する準備が完了しました。 これらは、組織のニーズに合&#39;アプリです。

既に一行のビジネス アプリがある場合は&#39;MDM を使用してアプリを [デプロイする準備が整います](/hololens/app-deploy-intune)。 別の方法&#39;場合は[、HoloLens 2](/hololens/app-deploy-overview)のアプリケーション展開の概要に関するページを参照して、ご利用のデバイスに LOB アプリを展開する方法の詳細を確認してください。

独自&#39;LOB アプリをまだ作成していない場合、または作成中の場合は、Mixed Reality 開発ドキュメントを参照して、設計[](/windows/mixed-reality/design/design)とプロトタイプ作成を開始するか、Mixed [Reality](/windows/mixed-reality/discover/get-started-with-mr)開発を開始する主要な概念を学習してください。

## <a name="device-management"></a>デバイス管理 

このガイドでは Mobile デバイス管理 (MDM) の設定について説明しましたが、デバイスの制限を適用したり、デバイスにポリシーを適用したりするために使用されません。 デバイス管理は、証明書をプッシュしてアクセスを許可したり、さまざまなデバイス制限でアクセスを制限したりするために使用できます。 

多くの場合、デバイスには、Bluetooth、VPN、USB などの接続制限がある場合や、カメラまたはマイクへのアクセスをオフにすることもできます。 これらの関心がある場合は、一般的なデバイスの制限に関する [ページをお読みください](hololens-common-device-restrictions.md)。

使用できるその他の複雑なデバイス制限があります。 例:

- [SettingsPageVisibility](settings-uri-list.md)を使用して 設定 アプリで表示できるページを制限すると、ユーザーは、Wi-Fi 接続の変更など、調整する必要がある設定にのみアクセスできます。
- キオスク [モードを使用](hololens-kiosk.md) して、デバイス上のユーザーに表示される UI を制限します。 キオスクを設定して、1 つのアプリを表示するか、カスタム スタート ページを使用して複数のアプリを表示できます。 キオスクでは、異なるユーザーに異なるエクスペリエンスを表示できます。  
- [Windowsアプリケーション制御 (WDAC)](windows-defender-application-control-wdac.md)を使用して、特定のアプリやプロセスが完全に起動しなきを維持します。

デバイス管理またはデバイスの制限のより異なる方法について学習する場合は、次の手順に進み、「概要」をデバイス管理してください。

## <a name="next-step"></a>次のステップ

> [!div class="nextstepaction"]
> [CSP とアプリケーションの概要をデバイス管理する](hololens-csp-policy-overview.md)