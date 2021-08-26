---
ms.openlocfilehash: d96a769b40daba0948f8f3c71a88513576c531b5
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859406"
---
# <a name="non-aad-configuration"></a>[AAD 以外の構成](#tab/nonaadlogon)

#### <a name="non-aad-configuration"></a>AAD 以外の構成

1. 次のようなプロビジョニングパッケージを作成します。
    1. ユーザーアカウントを許可するようにランタイム設定/AssignedAccess を構成します。
    1. 必要に応じて、後で管理できるように MDM (ランタイム設定/ワークプレース/登録) にデバイスを登録します。
    1. ローカルアカウントを作成しない
2. [プロビジョニングパッケージを適用](../hololens-provisioning.md)します。

# <a name="aad-configuration"></a>[AAD の構成](#tab/aadlogon)

#### <a name="aad-configuration"></a>AAD の構成

キオスクモード用に構成された AAD 参加済みデバイスは、サインイン画面からボタンを1回タップするだけで、ビジターアカウントにサインインできます。 ビジターアカウントにサインインすると、ユーザーが [スタート] メニューから明示的にサインアウトするか、デバイスが再起動されるまで、もう一度サインインを求めるメッセージが表示されません。

ビジター自動ログオンは、 [カスタム oma-uri ポリシー](/mem/intune/configuration/custom-settings-windows-10)を使用して管理できます。

- URI 値:./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| ポリシー | 説明 | 構成 |
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | 訪問者がキオスクに自動ログオンすることを許可します。 | 1 (はい)、0 (いいえ、既定値) |