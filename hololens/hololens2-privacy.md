---
title: HoloLens 2プライバシーとデータ保護
description: プライバシーに関するドキュメント
keywords: HoloLens、GDPR、プライバシー、PII、データ保護
author: golish
ms.author: marcingo
ms.reviewer: sekerawa, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 74f74645a3fc1282f48cb7ce0f6f722979c91b04
ms.sourcegitcommit: 548550f309010fa95f674a7ff688166a31cf1963
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2021
ms.locfileid: "122336744"
---
# <a name="hololens-2-privacy-and-data-protection"></a>HoloLens 2プライバシーとデータ保護

GDPR の主要な要素の 1 つは、"設計によるデータ保護" です。 この概念は、移植性、無制限のインターネット接続、オープン通信チャネルにより、HoloLens 2 など、モバイル デバイスに特に適用されます。 その結果、HoloLens 2 のセキュリティが再設計[](/hololens/security-architecture)され、高度で革新的なセキュリティとプライバシー保護がエンドツーエンドで提供され、プライバシーと[GDPR](https://privacy.microsoft.com/)規制に対する Microsoft のアプローチの両方が組み込みされました。

 >[!NOTE]
> このドキュメントは、(第 1 世代) HoloLensには適用されません。

## <a name="privacy-overview"></a>プライバシーの概要

HoloLens 2は、イマーシブ Mixed Reality 環境でアプリとソリューションを実行する Windows Holographic を実行する自己Windowsコンピューターです。 セキュリティで保護されたオフライン デバイスとして使用するか、組織内のマネージド デバイス [として](/mem/intune/fundamentals/windows-holographic-for-business) 展開することができます。 次のリンクを参照して、HoloLens 2 Microsoft がデータを使用および保護する方法を理解してください。

1. [Microsoft のプライバシー](https://privacy.microsoft.com/privacystatement)に関する声明 - HoloLens – 左側のナビゲーション メニューの [Enterprise **と開発者**] セクションを展開し、[Enterprise と開発者向けソフトウェアとアプライアンス]**を選択します**。 次のセクション **にHoloLens** します。
2. [Windows 10 とオンラインサービス](https://privacy.microsoft.com/windows10privacy)
3. [Windows 10 & プライバシー コンプライアンス ガイド](/windows/privacy/windows-10-and-privacy-compliance)
4. [Intune におけるプライバシーと個人データ](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>ネットワークのセキュリティ
「一HoloLens 2[デプロイ](/hololens/common-scenarios)シナリオ」に従って、データは、法律/規制標準の統合と共に[、Azure](/azure/compliance/)の世界クラスのコンプライアンスによって保護されます。 データの作成と管理Azure ADするDynamics 365 Remote Assist、GDPR の Azure と[Dynamics 365](/compliance/regulatory/gdpr-arc-azure-dynamics)の説明責任対応性チェックリストを参照してください。

さらに、Windows Defenderファイアウォールは、デバイス接続をセキュリティで保護するための重要な機能を提供します。 HoloLens 2 を使用する場合、ファイアウォールは常に有効です。ファイアウォールをプログラムによって無効にしたり、UI を介して無効にしたりする方法はありません。 Intune をHoloLens 2マネージド デバイスとして展開する場合は[、Mobile](/mem/intune/protect/device-compliance-get-started)Threat Defense ソリューションとしてのエンドポイントと[Microsoft Intune](/mem/intune/protect/advanced-threat-protection)の統合により多くのコンプライアンス機能を利用できます。

セキュリティとアーキテクチャに関HoloLens 2[詳細を確認してください](/hololens/security-architecture)。

## <a name="os-security"></a>OS のセキュリティ
更新は自動的に (既定で) 行われるので、HoloLens 2 Holographic とインストールされているアプリの最新リリースで、Windows が常に最新の情報に更新されます。 OS の安全な設計方法の詳細については、次を参照してください。

1. [状態の分割と分離](/hololens/security-state-separation-isolation)
1. [管理者が使用するオペレーティング システム](/hololens/security-adminless-os)
1. [パスワードの使用制限](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>物理的なセキュリティ
HoloLens 2 [BitLocker](/hololens/security-encryption-data-protection)暗号化で保護されているフラッシュ メモリがあります。 デバイスとそのローカル データは [、Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) を使用してオフラインでフラッシュするか、マネージド デバイスとして展開されている場合は MDM 経由でリモートワイプできます。

## <a name="data-protection"></a>データ保護
Windows更新プログラムは (既定で) 自動的に実行され[、Azure 統合](/hololens/security-encryption-data-protection#Azure-integration)によって、それ自体とクラウドの間を移動するデータが保護されます。

外部クライアントHoloLens 2展開する場合、Dynamics 365 Remote Assist会社の機密[](/hololens/hololens2-deployment-guide)データとリソースの両方が分離され、安全になります。

Microsoft との診断データの共有は、MDM または OOBE 中にユーザーが手動で構成できます。 オプションの診断データと必要な診断データの 2 つの選択肢があります。 トラブルシューティングのために後で元の診断設定を変更する必要がある場合は **、設定 -> Privacy -> Diagnostics & Feedback** のユーザー、またはマネージド デバイスの場合は IT 管理者 (MDM) によって変更できます。 診断、フィードバック[、プライバシーの詳細については、以下を参照Windows 10。](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)

> [!Important]
> デバイス診断ログには、ユーザーが一般的な操作中に開始するプロセスやアプリケーションなど、個人を特定できる情報 (PII) が含まれます。 複数のユーザーが HoloLens デバイスを共有する場合 (たとえば、ユーザーは異なる Microsoft Azure Active Directory (Azure AD) アカウントを使用して同じデバイスにサインインします)、診断ログには、複数のユーザーに適用される PII 情報が含まれる場合があります。

診断データ[を収集するコレクション](/hololens/hololens-diagnostic-logs)方法とデータ保持ポリシーは、HoloLens 2。  Microsoft が診断データを収集して使用する方法の詳細については [、「Microsoft の](https://privacy.microsoft.com/privacystatement)プライバシーに関する声明 - 診断 - 左側のナビゲーション メニューで [Windows] を展開し、[診断] を選択 **します。** [診断] **セクションに移動** します。