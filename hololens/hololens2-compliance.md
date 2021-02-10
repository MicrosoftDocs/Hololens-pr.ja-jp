---
title: HoloLens 2 のコンプライアンスと GDPR
description: GDPR ドキュメント
keywords: HoloLens、GDPR、プライバシー、PII
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: skerewala, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b795513d83c9d23f70b8dd8365e703d1fc43a51
ms.sourcegitcommit: 76a99370ab841c06e533cc2f4a0c78c1fb7eac70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "11324876"
---
# HoloLens 2 のプライバシーに関する声明

GDPR の主要な要素の 1 つは、「設計によるデータ保護」です。 この概念は、移植性、無制限のインターネット接続、オープンな通信チャネルのために、HoloLens 2 のようなモバイル デバイスに特に適用されます。 その結果、HoloLens 2 の[](https://docs.microsoft.com/hololens/security-architecture)セキュリティは、Microsoft のプライバシーおよび[GDPR](https://privacy.microsoft.com/)規制に対する Microsoft のアプローチの両方を組み込み、高度で革新的なセキュリティとプライバシー保護をエンドツーエンドで提供するために再設計されました。

 >[!NOTE]
> このドキュメントは、HoloLens (第 1 世代) には適用されません。

## プライバシーの概要

HoloLens 2 は、イマーシブ Mixed Reality 環境でアプリとソリューションを実行する、Windows Holographic を実行する自己格納型の Windows コンピューターです。 セキュリティで保護されたオフライン デバイスとして使用するか、組織内の [管理対象デバイスとして](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business) 展開できます。 HoloLens 2 と Microsoft がデータを使用して保護する方法については、次のリンクを参照してください。
1. [Microsoft のプライバシーに関する声明 - HoloLens](https://privacy.microsoft.com/privacystatement) – 左側のナビゲーション メニューで [ **エンタープライズ** と開発者] セクションを展開し、[エンタープライズと開発者向けの **ソフトウェアとアプライアンス] を選択します**。 **HoloLens セクションに移動**します。
2.  [Windows 10 とオンライン サービス](https://privacy.microsoft.com/windows10privacy)
3.  [Windows 10 とプライバシー コンプライアンス ガイド](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
4.  [Intune のプライバシーと個人データ](https://docs.microsoft.com/mem/intune/protect/privacy-personal-data)

## ネットワーク セキュリティ
HoloLens 2 [の一](https://docs.microsoft.com/hololens/common-scenarios)般的な展開シナリオに従い、お客様のデータは [Azure](https://docs.microsoft.com/azure/compliance/) の世界クラスのコンプライアンスと共に法律/規制基準の統合によって保護されます。 Azure AD と Dynamics 365 リモート アシストを使い終える場合は、GDPR に関する Azure と [Dynamics 365](https://docs.microsoft.com/compliance/regulatory/gdpr-arc-azure-dynamics)のアアカウント責任準備チェックリストを参照してください。

さらに、Windows Defenderファイアウォールは重要な機能を提供し、デバイスの接続をセキュリティで保護します。 HoloLens 2 ではファイアウォールが常に有効になっています。ファイアウォールをプログラムによって無効にしたり、UI を介して無効にしたりする方法はありません。 Intune を使用して HoloLens 2 を管理対象デバイスとして展開すると [、Mobile](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)Threat Defense ソリューションとしての [Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection) とのエンドポイント統合により、より多くのコンプライアンス機能を利用できます。 

HoloLens 2 のセキュリティとアーキテクチャ [について詳しくは、以下をご覧ください](https://docs.microsoft.com/hololens/security-architecture)。

## OS セキュリティ
更新は (既定で) 自動的に行われるので、HoloLens 2 は常に最新の Windows Holographic とインストールされているアプリの最新のリリースです。 OS の安全な設計方法の詳細については、以下を参照してください。
1. [状態の分割と分離](https://docs.microsoft.com/hololens/security-state-separation-isolation)
1. [管理者不要のオペレーティング システム](https://docs.microsoft.com/hololens/security-adminless-os)
1. [パスワードの使用制限](https://docs.microsoft.com/hololens/security-limiting-password-use)

## 物理セキュリティ
HoloLens 2 には [、BitLocker](https://docs.microsoft.com/hololens/security-encryption-data-protection)暗号化で保護されたフラッシュ メモリがあります。 デバイスとそのローカル データは [、Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) を使用してオフラインでフラッシュするか、管理対象デバイスとして展開されている場合は MDM 経由でリモートワイプできます。

## データ保護
Windows 更新プログラムは (既定で) 自動的に実行され [、Azure](https://docs.microsoft.com/hololens/security-encryption-data-protection#Azure-integration) 統合はそれ自体とクラウドの間を移動するデータを保護します。 

HoloLens 2 を外部クライアントに展開する場合 [、Dynamics 365 リモート](https://docs.microsoft.com/hololens/hololens2-deployment-guide) アシストにより、機密性の高い会社のデータとリソースが分離され安全になります。 

Microsoft との診断データの共有は、MDM または OOBE 中にユーザーが手動で構成できます。 オプションの診断データと必須の診断データの 2 つの選択肢があります。 トラブルシューティングを目的として、元の診断設定を後で変更する必要がある場合は、[設定] -> [プライバシー] **-> [** 診断 & フィードバック] のユーザー、または管理対象デバイスの場合は IT 管理者 (MDM) で変更できます。 [Windows 10 の診断、フィードバック、プライバシーについて詳しくは、以下をご覧ください](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)。

> [!Important]
> デバイス診断ログには、ユーザーが一般的な操作中に開始するプロセスやアプリケーションなど、個人を特定できる情報 (PII) が含まれます。 複数のユーザーが HoloLens デバイスを共有する場合 (たとえば、ユーザーが異なる Microsoft Azure Active Directory (Azure AD) アカウントを使用して同じデバイスにサインインする場合)、診断ログには複数のユーザーに適用される PII 情報が含まれる場合があります。

 

HoloLens 2 から診断 [データ](https://docs.microsoft.com/hololens/hololens-diagnostic-logs) を収集するには、いくつかの収集方法とデータ保持ポリシーがあります。  Microsoft が診断データを収集して使用する方法の詳細については [、「Microsoft の](https://privacy.microsoft.com/privacystatement) プライバシーに関する声明 - 診断 - 左側のナビゲーション メニューで **Windows** を展開し、[診断] を選択する」を **参照してください**。 [診断] **セクションに移動** します。
