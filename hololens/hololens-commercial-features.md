---
title: 商用機能
description: Microsoft HoloLens Commercial Suite には、企業で HoloLens デバイスを簡単に管理するための機能が含まれています。 HoloLens 2 デバイスには、既定で商用機能が装備されています。
keywords: HoloLens, 商用, 機能, MDM, モバイル デバイス管理, キオスク モード
author: scooley
ms.author: scooley
ms.date: 08/26/2019
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 28898c5c0cbc2a4f66cea13665e5ef63447db382
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828759"
---
# 商用機能

HoloLens には、企業で HoloLens デバイスを簡単に管理するための機能が含まれています。

すべての HoloLens 2 デバイスには、商用機能が装備されています。

HoloLens (第 1 世代) には、ライセンス オプションとして開発者ライセンスと商用ライセンスの 2 つがありました。 HoloLens の商用機能を有効にするには、開発者ライセンスから商用ライセンスにアップグレードします。 Microsoft HoloLens Commercial Suite のご購入については、お住まいの地域の Microsoft アカウントマネージャーにお問い合わせください。

>[!VIDEO https://www.youtube.com/embed/tNd0e2CiAkE]

## 主要な商用機能

- **キオスク モード。** キオスク モードで実行可能なアプリを制限することにより、HoloLens をデモやショーケース エクスペリエンスに使用できます。

  ![キオスク モードでは、HoloLens が起動すると、指定のアプリが直接開きます。](images/201608-kioskmode-400px.png)

- **HoloLens 向けモバイル デバイス管理 (MDM)。** IT 部門では Microsoft Intune などのソリューションを使い、複数の HoloLens デバイスを同時に管理できます。 設定の管理、インストールするアプリの選択、組織のニーズに合わせたセキュリティ構成の設定を行うことができます。

  ![HoloLens のモバイル デバイス管理では、複数のデバイスに対してエンタープライズ レベルのデバイス管理を行うことができます。](images/201608-enterprisemanagement-400px.png)

- **Windows Update for Business。** Windows Update for Business は、デバイスに対するオペレーティング システムの更新プログラムの適用を制御し、長期間のサービスチャネルのサポートを提供します。
- **データ セキュリティ。** HoloLens では、他の Windows デバイスと同じレベルのセキュリティ保護を提供するために、BitLocker データ暗号化が有効になっています。
- **職場のアクセス。** 組織内のユーザーはすべて、HoloLens の仮想プライベート ネットワーク (VPN) 経由で企業ネットワークにリモート接続できます。 HoloLens では、資格情報を必要とする Wi-Fi ネットワークにもアクセスできます。
- **ビジネス向け Microsoft Store。** IT 部門では、HoloLens の特定使用に応じて、会社のアプリのみを登録したエンタープライズ プライベート ストアをセットアップすることもできます。 選択したエンタープライズ ユーザー グループに、エンタープライズ ソフトウェアを安全に配布できます。

## エディション間の機能の比較

|機能 |HoloLens Development Edition |HoloLens Commercial Suite |HoloLens 2 |
|---|:---:|:---:|:---:|
|デバイスの暗号化 (BitLocker) | |✔️ |✔️ |
|仮想プライベート ネットワーク (VPN) | |✔️ |✔️ |
|[キオスク モード](hololens-kiosk.md) | |✔️ |✔️ |
|**管理と展開** | | | |
|モバイル デバイス管理 (MDM) | |✔️ |✔️ |
|登録解除をブロックする機能 | |✔️ |✔️ |
|企業のWi-Fi アクセス (証明書ベース) | |✔️ |✔️ |
|Microsoft Store (コンシューマー) |コンシューマー |MDM を使用してフィルター処理 |MDM を使用してフィルター処理 |
|[ビジネス向け Microsoft Store ポータル](https://docs.microsoft.com/microsoft-store/working-with-line-of-business-apps) | |✔️ |✔️ |
|**セキュリティと ID** | | | |
|Azure Active Directory (AAD) アカウントを使用したサインイン |✔️ |✔️ |✔️ |
|Microsoft アカウント (MSA) を使用したサインイン |✔️ |✔️ |✔️ |
|Next Generation Credentials と PIN ロック解除 |✔️ |✔️ |✔️ |
|[セキュア ブート](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot) |✔️ |✔️ |✔️ |
|**サービスとサポート** | | | |
|システムの自動更新 (受信時) |✔️ |✔️ |✔️ |
|[Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) | |✔️ |✔️ |
|長期サービス チャネル (LTSC) | |✔️ |✔️ |

## 商用機能を有効にする

組織の IT 管理者は、ビジネス向け Microsoft Store、キオスク モード、エンタープライズ Wi-Fi アクセスなどの商用機能をセットアップできます。 デバイスを登録し、ビジネス向け Microsoft Store からアプリをインストールする手順については、[Microsoft HoloLens](index.md) ドキュメントをご覧ください。

## 関連項目

- [Microsoft HoloLens](index.md)
- [キオスク モード](hololens-kiosk.md)
- [HoloLens デバイスでサポートされている CSP](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)
- [ビジネス向け Microsoft Store と基幹業務アプリケーション](https://blogs.technet.microsoft.com/sbucci/2016/04/13/windows-store-for-business-and-line-of-business-applications/)
- [基幹業務アプリの操作](/microsoft-store/working-with-line-of-business-apps)