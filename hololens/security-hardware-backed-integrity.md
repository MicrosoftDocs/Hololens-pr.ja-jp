---
title: ハードウェアで支援された整合性と実行時認証
description: ハードウェアで支援された整合性と実行時認証
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: セキュリティ、hololens、ハードウェアによる整合性、実行時の認証、UEFI、UEFI セキュア ブート、セキュア ブート、TPM、脅威保護、Windows の永続的攻撃対策保証、コードの整合性、コードの保護、
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 037f9325555244314518c81d7814bf983c345af6
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034404"
---
# <a name="hardware-backed-integrity-and-runtime-attestation"></a>ハードウェアで支援された整合性とランタイム認証

デバイスからハードウェアを使用するときは、オペレーティング システムの起動前から実行中にかけて発生する脅威に対してハードウェアで支援された整合性と実行時認証によって保護されます。またリモート認証サービスにより、起動時と実行中の整合性が確実に維持されるように保護されます。

## <a name="uefi-secure-boot"></a>UEFI セキュア ブート

HoloLens 2 により、統合拡張ファームウェア インターフェイス (UEFI) セキュア ブートが常に実行され、UEFI により、Windows Holographic for Business のみがブートされます。
セキュア ブートを使用すると、ブート チェーン全体の整合性が検証され、常に正しいセキュリティ ポリシーを適用して Windows がブートされます。 詳細については、「[セキュア ブート](/windows-hardware/design/device-experiences/oem-secure-boot)」を参照してください。

## <a name="tpm"></a>TPM

トラステッド プラットフォーム モジュール (TPM) は、エンドポイント デバイスの特殊なチップです。 HoloLens 2 には、ハードウェアによるキーの分離を提供する TPM 2.0 が使用されています。 詳細については、「[TPM の基本事項](/windows/security/information-protection/tpm/tpm-fundamentals)」を参照してください。

## <a name="persistence-access-threat-protection"></a>永続的アクセスの脅威からの保護

ほとんどのサイバー攻撃の目標は、デバイスへのアクセスを永続的に維持することです。 サイバー犯罪の場合、この永続的なアクセスを維持することで、侵害された Windows デバイスをボットネットに参加させる、デバイスや他の悪意のあるユーザーにアクセスを販売する、または繰り返しデータを盗むことが可能になります。 標的型攻撃の世界でサイバー攻撃を成功させるには、デバイスであれ、(より一般的には) ネットワーク全体であれ、永続性が不可欠です。  

実際、標的型攻撃は、標的のデバイスやネットワークへのアクセスを維持するという戦略的な必要性から、"高度な持続的脅威" と考えられています。 このような理由から、Windows Holographic for Business では、永続性に対する防御が絶対に重要であると考え、永続的攻撃対策テクノロジを使用して、顧客のセキュリティを確固たるものにしています。

### <a name="secure-boot"></a>セキュア ブート

HoloLens 2 により、すべてのコア オペレーティング システムの状態に対して統合拡張ファームウェア インターフェイス (UEFI) セキュア ブートが適用されています。 UEFI によって、Microsoft の信頼されたプラットフォームのみが起動されます。これにより、ブート チェーン全体で整合性が検証され、Windows は常に正しいセキュリティ ポリシーを適用してブートします。 HoloLens 2 でセキュア ブートをオフにすることはできません。また、サードパーティ製ブート ローダーは許可されていません。

> [!Tip]
> 詳細については、「[セキュア ブート](/windows-hardware/design/device-experiences/oem-secure-boot)」を参照してください。

### <a name="windows-anti-persistence-assurance"></a>Windows の永続的攻撃対策保証

HoloLens 2 の永続的攻撃対策は、遠隔操作のような、システム実行中にセキュリティ侵害が起こるような稀な状況においても、デバイスの電源を切って悪意のあるコードをすべてシステムから削除することによって、そのイベントの害を緩和することを、ユーザーに対して保証しています。 永続的攻撃対策をさらに強化するために、HoloLens 2 には強力な整合性保護が追加され、読み取り専用の保護が設定されました。

データ形式でのオペレーティング システムデータの永続的攻撃は、変更可能なすべてのパーティションを消去するデバイスのプッシュボタン リセット (PBR) をユーザーが実行しない限り、引き続き可能です。 変更不可能なパーティションに対する永続性は非常に困難になりますが、ユーザーは HoloLens 2 の PBR を実行して、変更可能な部分から潜在的な脅威の永続性を取り除く必要があります。

## <a name="code-integrity-protection"></a>コードの整合性保護

コードの整合性 (CI) は、最新のオペレーティング システムの重要なセキュリティ プロパティです。 CI を適用すると、ユーザーとオペレーティング システムの両方に対してコードの由来が確実に明瞭になるので、適切なセキュリティ判断が可能になります。 コードの整合性を完全に維持するには、バイナリ イメージの過去の署名を延長する必要があります。また、制御フローの整合性や動的なコードの制限などのランタイム強制を含む必要があります。 CI は、ランサムウェア、リモート コード実行攻撃、各種の攻撃など、一般的に利用されているマルウェアを含む複数の攻撃を防ぐために欠かせません。
