---
title: HoloLens 2 のプライバシーとデータ保護
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033299"
---
# <a name="hololens-2-privacy-and-data-protection"></a>HoloLens 2 のプライバシーとデータ保護

GDPR の中核となる要素の1つは、"design によるデータ保護" です。 この概念は、特に、HoloLens 2 のようなモバイルデバイスに適用されます。これは、移植性、無制限のインターネット接続、通信チャネルを開くことができるためです。 HoloLens 2 Resultingly の[セキュリティ](/hololens/security-architecture)は、高度で革新的なセキュリティとプライバシー保護をエンドツーエンドで提供するために再設計され、[プライバシーと GDPR](https://privacy.microsoft.com/)の両方の規制に Microsoft が採用しています。

 >[!NOTE]
> このドキュメントは HoloLens (第1世代) には適用されません。

## <a name="privacy-overview"></a>プライバシーの概要

HoloLens 2 は、イマーシブ mixed reality 環境でアプリとソリューションを実行する、Windows Holographic を実行する自己完結型の Windows コンピューターです。 セキュリティで保護されたオフラインデバイスとして使用することも、組織内の [管理対象デバイス](/mem/intune/fundamentals/windows-holographic-for-business) として展開することもできます。 HoloLens 2 とマイクロソフトがデータをどのように使用して保護するかを理解するには、次のリンクを参照してください。

1. [Microsoft のプライバシーに関する声明-HoloLens](https://privacy.microsoft.com/privacystatement) –左側のナビゲーションメニューで [ **Enterprise と開発者**] セクションを展開し、[ **Enterprise と開発者向けソフトウェアおよびアプライアンス**] を選択します。 **HoloLens** のセクションに進んでください。
2. [Windows 10 とオンラインサービス](https://privacy.microsoft.com/windows10privacy)
3. [Windows 10 & のプライバシー準拠ガイド](/windows/privacy/windows-10-and-privacy-compliance)
4. [Intune におけるプライバシーと個人データ](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>ネットワークのセキュリティ
HoloLens 2 の[一般的なデプロイシナリオ](/hololens/common-scenarios)に従うと、データは、法的/規制標準の統合と共に、 [Azure の世界クラスのコンプライアンス](/azure/compliance/)によって保護されます。 Azure AD と Dynamics 365 Remote Assist を初めて使用する場合は、 [GDPR の Azure および Dynamics 365 のアカウンタビリティの準備チェックリスト](/compliance/regulatory/gdpr-arc-azure-dynamics)を参照してください。

さらに、Windows Defender ファイアウォールは、デバイスの接続をセキュリティで保護するための重要な機能を提供します。 HoloLens 2 を使用する場合、ファイアウォールは常に有効です。ファイアウォールをプログラムによって無効にしたり、UI を介して無効にしたりする方法はありません。 [Intune](/mem/intune/protect/device-compliance-get-started)を使用して HoloLens 2 が管理対象デバイスとして展開されている場合、モバイル脅威防御ソリューションとして[Microsoft Intune を使用したエンドポイント](/mem/intune/protect/advanced-threat-protection)の統合により、より多くのコンプライアンス機能を利用できます。

HoloLens 2 の[セキュリティとアーキテクチャ](/hololens/security-architecture)の詳細については、こちらを参照してください。

## <a name="os-security"></a>OS のセキュリティ
更新プログラムは、既定では自動的に実行されるため、Windows Holographic およびインストールされているすべてのアプリの最新リリースにより、HoloLens 2 は常に最新の状態になります。 OS が安全に設計されている方法の詳細については、以下を参照してください。

1. [状態の分割と分離](/hololens/security-state-separation-isolation)
1. [管理者レスオペレーティングシステム](/hololens/security-adminless-os)
1. [パスワードの使用制限](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>物理的なセキュリティ
HoloLens 2 には、 [BitLocker 暗号化](/hololens/security-encryption-data-protection)によって保護されているフラッシュメモリがあります。 デバイスとそのローカルデータは、 [Advanced Recovery コンパニオン](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) を使用してオフラインで、または管理対象デバイスとしてデプロイされている場合は MDM 経由でリモートでワイプすることができます。

## <a name="data-protection"></a>データ保護
Windows の更新プログラムは (既定で) 自動的に実行され、 [Azure 統合](/hololens/security-encryption-data-protection#Azure-integration)によって、それ自体とクラウドの間のデータ移動を保護します。

HoloLens 2 を外部クライアントに展開すると、会社の機密データとリソースの両方が独立して安全であることが[Dynamics 365 Remote Assist](/hololens/hololens2-deployment-guide)になります。

Microsoft との診断データの共有は、MDM または OOBE 中にユーザーが手動で構成できます。 オプションの診断データと必要な診断データの2つの選択肢があります。 トラブルシューティングのために元の診断設定を後で変更する必要がある場合は、**設定 > のプライバシー-> 診断 & のフィードバック**、または管理対象デバイスの場合は it 管理者 (MDM) で変更できます。 [Windows 10 の診断、フィードバック、プライバシー](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)について詳しくは、こちらをご覧ください。

> [!Important]
> デバイス診断ログには、ユーザーが通常の操作で開始するプロセスやアプリケーションなど、個人を特定できる情報 (PII) が含まれています。 複数のユーザーが HoloLens デバイスを共有している場合 (たとえば、ユーザーが別の Microsoft Azure Active Directory (Azure AD) アカウントを使用して同じデバイスにサインインする場合)、診断ログには、複数のユーザーに適用される PII 情報が含まれる場合があります。

HoloLens 2 から診断データを収集するための[収集方法とデータ保持ポリシーがいくつか](/hololens/hololens-diagnostic-logs)あります。  microsoft が診断データを収集して使用する方法の詳細については、左側のナビゲーションメニューで [microsoft のプライバシーに関する [声明-診断](https://privacy.microsoft.com/privacystatement)]、[ **Windows** ] の順に展開し、[**診断**] を選択します。 [ **診断** ] セクションにアクセスします。
