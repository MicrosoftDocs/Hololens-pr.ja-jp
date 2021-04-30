---
title: HoloLens 2 のコンプライアンスと GDPR
description: GDPR のドキュメント
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309914"
---
# <a name="hololens-2-privacy-statement"></a>HoloLens 2 のプライバシーに関する声明

GDPR の中核となる要素の1つは、"design によるデータ保護" です。 この概念は、モバイルデバイス (HoloLens 2 など) に特に当てはまります。これは、移植性、無制限のインターネット接続、通信チャネルを開くことによるものです。 Resultingly は、Microsoft の[プライバシーと GDPR](https://privacy.microsoft.com/)の両方の方法を採用して、高度で革新的なセキュリティとプライバシー保護をエンドツーエンドで提供するように、HoloLens 2 の[セキュリティ](https://docs.microsoft.com/hololens/security-architecture)を再設計しました。

 >[!NOTE]
> このドキュメントは HoloLens (第1世代) には適用されません。

## <a name="privacy-overview"></a>プライバシーの概要

HoloLens 2 は、Windows Holographic を実行する自己完結型の Windows コンピューターであり、イマーシブ mixed reality 環境でアプリとソリューションを実行します。 セキュリティで保護されたオフラインデバイスとして使用することも、組織内の [管理対象デバイス](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business) として展開することもできます。 HoloLens 2 と Microsoft がデータを使用して保護する方法については、次のリンクを参照してください。
1. [Microsoft のプライバシーに関する声明-HoloLens](https://privacy.microsoft.com/privacystatement) –左側のナビゲーションメニューの [ **エンタープライズと開発者** ] セクションを展開し、[ **エンタープライズと開発者のソフトウェアおよびアプライアンス**] を選択します。 **HoloLens** セクションにアクセスします。
2.  [Windows 10 とオンラインサービス](https://privacy.microsoft.com/windows10privacy)
3.  [Windows 10 & プライバシー準拠ガイド](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
4.  [Intune におけるプライバシーと個人データ](https://docs.microsoft.com/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>ネットワークのセキュリティ
HoloLens 2 の [一般的なデプロイシナリオ](https://docs.microsoft.com/hololens/common-scenarios)に従うと、データは、法的/規制標準の統合と共に、 [Azure の世界クラスのコンプライアンス](https://docs.microsoft.com/azure/compliance/) によって保護されます。 Azure AD と Dynamics 365 リモートアシスタンスを初めて使用する場合は、 [GDPR の Azure と dynamics 365 のアカウンタビリティの準備チェックリスト](https://docs.microsoft.com/compliance/regulatory/gdpr-arc-azure-dynamics)を参照してください。

さらに、Windows Defender ファイアウォールは、デバイスの接続をセキュリティで保護するための重要な機能を提供します。 HoloLens 2 では、ファイアウォールは常に有効になっており、プログラムまたは UI を使用して無効にする方法はありません。 HoloLens 2 が [Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)を使用して管理対象デバイスとして展開されている場合、モバイル脅威防御ソリューションとして [Microsoft Intune を持つエンドポイント](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection) の統合により、より多くのコンプライアンス機能を利用できます。 

HoloLens 2 の [セキュリティとアーキテクチャ](https://docs.microsoft.com/hololens/security-architecture)の詳細については、こちらを参照してください。

## <a name="os-security"></a>OS のセキュリティ
更新プログラムは、既定で自動的に実行されるため、Windows Holographic とインストールされているすべてのアプリの最新リリースによって、HoloLens 2 が常に最新の状態になります。 OS が安全に設計されている方法の詳細については、以下を参照してください。
1. [状態の分離と分離](https://docs.microsoft.com/hololens/security-state-separation-isolation)
1. [管理者レスオペレーティングシステム](https://docs.microsoft.com/hololens/security-adminless-os)
1. [パスワードの使用を制限する](https://docs.microsoft.com/hololens/security-limiting-password-use)

## <a name="physical-security"></a>物理的なセキュリティ
HoloLens 2 には、 [BitLocker 暗号化](https://docs.microsoft.com/hololens/security-encryption-data-protection)によって保護されているフラッシュメモリがあります。 デバイスとそのローカルデータは、 [Advanced Recovery コンパニオン](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) を使用してオフラインで、または管理対象デバイスとしてデプロイされている場合は MDM 経由でリモートでワイプすることができます。

## <a name="data-protection"></a>データ保護
Windows の更新プログラムは自動的に (既定で) 実行され、 [Azure 統合](https://docs.microsoft.com/hololens/security-encryption-data-protection#Azure-integration) によって、自身とクラウドの間のデータ移動を保護します。 

HoloLens 2 を外部クライアントに展開すると、 [Dynamics 365 リモート](https://docs.microsoft.com/hololens/hololens2-deployment-guide) アシスタンスによって、会社の機密データとリソースの両方が分離され、安全になります。 

Microsoft との診断データの共有は、MDM または OOBE 中にユーザーが手動で構成できます。 オプションの診断データと必要な診断データの2つの選択肢があります。 トラブルシューティングのために元の診断設定を後で変更する必要がある場合は、ユーザーが [> 設定]、[ **プライバシー-> 診断 & のフィードバック** ]、または管理対象デバイスの場合は It 管理者 (MDM) で変更できます。 詳細については [、Windows 10 の診断、フィードバック、プライバシー](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)に関する情報を参照してください。

> [!Important]
> デバイス診断ログには、ユーザーが通常の操作で開始するプロセスやアプリケーションなど、個人を特定できる情報 (PII) が含まれています。 複数のユーザーが HoloLens デバイスを共有している場合 (たとえば、ユーザーが異なる Microsoft Azure Active Directory (Azure AD) アカウントを使用して同じデバイスにサインインした場合)、診断ログには、複数のユーザーに適用される PII 情報が含まれる場合があります。

 

HoloLens 2 から診断データを収集するための [収集方法とデータ保持ポリシーがいくつか](https://docs.microsoft.com/hololens/hololens-diagnostic-logs) あります。  Microsoft が診断データを収集して使用する方法の詳細については、左側のナビゲーションメニューで「 [microsoft のプライバシー](https://privacy.microsoft.com/privacystatement) に関する声明- **Windows** を展開する」および「 **診断**」を参照してください。 [ **診断** ] セクションにアクセスします。
