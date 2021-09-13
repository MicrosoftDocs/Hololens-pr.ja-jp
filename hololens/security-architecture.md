---
title: HoloLens セキュリティ アーキテクチャ
description: セキュリティのアーキテクチャ
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: セキュリティ, hololens, hololens 2, hololens2, security, セキュリティの概要, セキュリティ アーキテクチャ, アーキテクチャ, hololens 2 のアーキテクチャ
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034446"
---
# <a name="security-overview-and-architecture"></a>セキュリティの概要とアーキテクチャ

HoloLens 2 のセキュリティ アーキテクチャは、攻撃を最小限に抑えるとともに、従来のセキュリティの問題から解放されるようにゼロから設計および構築されました。 この新しい革新的なアーキテクチャは、セキュリティで保護されたストレージの場所と、高度なセキュリティ要素を備え、オペレーティング システムを潜在的な脅威や脆弱性から保護できるメカニズムを備えています。

HoloLens 2 は、ハードウェア、ソフトウェア、ネットワーク、およびサービスを組み合わせて、エンドツーエンドのセキュリティを確保するとともに、ユーザーに最適なエクスペリエンスを提供します。 HoloLens 2 では、セキュリティ機能の大部分が自動的に有効になり、オペレーティング システムを正しくセットアップして構成するために必要な労力を最小限に抑えることができます。

Windows HoloLens 2 とオペレーティング システムのアーキテクチャには、次の革新的なセキュリティ機能があります。

  * **状態の分割と分離**: この新しいアーキテクチャによって、コア オペレーティング システムを信頼できる状態で起動するために必要な部分など、HoloLens 2 オペレーティング システムの重要部分が変わらないように保護されます。 分離技術を使用して、信頼されていないアプリをサンドボックス領域に限定し、システムのセキュリティに影響しないようにできます。 オペレーティング システム全体は安全なセクションに分かれており、セクションごとに異なるセキュリティ技術を組み合わせることによって保護されます。
  
  * **データ保護**: ユーザーのデバイスが紛失または盗難にあった場合、HoloLens 2 はデータの BitLocker 暗号化によって、認証されていないアプリケーションが機密情報を読み取ることを防ぎます。 
  
  * **パスワードのないオペレーティング システム**: 以前のパスワードベースのオペレーティング システムでは、ユーザーが不注意によるフィッシング詐欺にさらされる可能性があったため、アカウントが侵害される原因となることがしばしばでした。 Windows Holographic for Business により、MSA および Azure AD サインインのパスワードの使用が排除され、Windows Hello™ および FIDO2 サインインによるユーザー ID の保護が強化されます。 
  
    > [!NOTE]
    > FIDO2 のサポートを受けるには、デバイスがビルド 19041 以降である必要があります。 

  * **ネットワーク セキュリティ**: HoloLens 2 では、改善されたプロトコルと既定の設定により、強化されたネットワーク セキュリティが提供されます。
