---
title: セキュリティ adminless os
description: adminless os および hololens セキュリティ
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: セキュリティ、hololens、adminless、管理者不要、オペレーティング システム、管理者不要のオペレーティング システム、管理 os、管理者不要の os、hololens 2、hololens2 セキュリティ、
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e8a10a32d30206877eb79d53c90e59307b3990ab
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009565"
---
# 管理者不要のオペレーティング システム

HoloLens 2 は、管理者グループのサポートを無効にして、すべてのサードパーティ UWP アプリケーション コードを AppContainer サンドボックス内で標準ユーザーとしてのみ実行できるようにすることで、特権昇格の対象領域を最小化します。 このコードには、すべての AppContainers がアクセスできるリソースだけでなく、昇格されていないユーザーに対する、アプリケーションで明示的に指定された機能によって保護されたリソースへのアクセス権のみが許可されます。
これらのアプリケーション機能には、引き続き 3 階層の分類モデルがあります。
  * 全般的な情報
  * 制限されます
  * Windows

Windows コンポーネントは、システム UWP を介して AppContainer サンドボックスを利用することもできます。 ユニバーサル Windows プラットフォーム (UWP) の詳細については、「[UWP ドキュメント](https://docs.microsoft.com/windows/uwp/)」を参照してください。 また、特権を削減する必要がある Windows コンポーネント (ブラウザーのコンテンツ ページ、パーサーなど) は、すべての AppContainers がアクセスできるリソースのセットへのアクセスを遮断する、Less Privileged AppContainer (LPAC) サンドボックスを使用します。

最後に、デバイスのテナントへの参加やユーザーの管理など、特定のデバイス全体の操作の実行は、"デバイス オーナー" にのみ許可されます。 デバイス上のユーザーは、次のいずれかの手順でこのグループに入ることができます。
  * デバイスの最初のユーザーは、常にオーナーとして指定されます。 
    * このルールの例外は、デバイスが AAD 結合されている場合、結合を実行したユーザーがデバイス オーナーになることです。 たとえば、デバイスが自動操縦によって AAD 結合されている場合、デバイスに最初にサインインしているユーザーはデバイスに対して AAD 結合を行わないので、デバイス オーナーにはなりません。 AAD 結合しているデバイスのデバイス オーナーについての詳細については、["ローカル管理者に割り当てる" の](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin)ドキュメントをご覧ください。(ただし、HoloLens には管理者が存在しないため、「ローカル管理者」を「デバイス オーナー」とみなします)。
  * ユーザーがデバイス上の別のオーナーによって設定 UX からオーナーに昇格された場合。
  * デバイス オーナーが利用できなくなった場合 (会社を退職した場合など)、デバイスが AAD 結合されている場合、テナント管理者は、Azure ポータルでデバイス オーナーを新しいユーザーに変更できます。
Azure AD テナントのグローバル管理者は、前の手順を必要とせずに、デバイスの所有者として暗黙の内にサインインされます。 

IT 管理者は [プライバシー](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) ポリシーを使用して、アクセスできるアプリを管理できます。 
