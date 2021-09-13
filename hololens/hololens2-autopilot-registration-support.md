---
title: HoloLens 2 の Windows Autopilot 登録サポート
description: HoloLens 2 デバイスで Autopilot の登録サポートを受ける方法について説明します。
author: joyjaz
ms.author: v-jjaswinski
ms.date: 5/20/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Autopilot
manager: ylempidakis
ms.openlocfilehash: cdd2ab68905d5cc82b1c5ccc50640112e857f2f4
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034359"
---
# <a name="hololens-2-registration-support-for-autopilot"></a>Autopilot の HoloLens 2 登録のサポート

お客様と Microsoft クラウド ソリューションプロバイダ－ (CSP) は、Microsoft サポートに直接要求を送信することで、HoloLens 2 デバイスを登録できるようになりました。 このページでは、次のサポートされているAutopilot 登録シナリオの要件について説明します。

- **HoloLens 2 デバイスの Autopilot 登録**。 HoloLens 2 デバイスを Windows Autopilot に登録する要求を送信します。
- **HoloLens 2 デバイスのハードウェアハッシュ要求** です。 Microsoft サポートに要求を送信し、顧客または CSP が Microsoft Intune または Microsoft パートナーセンターを使用してデバイスを自己登録するために使用できるハードウェア ハッシュを提供します。
- **HoloLens 2 デバイスの Autopilot 登録解除**。 Windows Autopilot からデバイスを削除する要求を送信します。これは通常、デバイスのライフサイクルのシナリオで使用されます。

次の表は、登録要求を Microsoft サポートに送信する *前* に収集する必要がある情報について説明します。

| 必須情報 | 説明 | Autopilot の登録  | ハードウェア ハッシュ要求 | Autopilot の登録解除 |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  Azure Active Directory テナント ID    |    Azure Active Directory テナント ID は、組織名またはドメインとは異なるグローバル一意識別子 (GUID) です。    テナント ID を検索するには、[Azure Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) にサインインします。    |     ✔️                         |                              |                         ✔️                        |
|  Azure Active Directory ドメイン名    |   トップレベルドメイン名。たとえば、contoso.com など。    |     ✔️                         |                              |                         ✔️                        |
|  所有権の証明    |   元の販売明細書または請求書を PDF 形式でアップロードして、所有権の証明を確認します。 スクリーンショットは受け入れられません。 請求書には、次のデバイスのシリアル番号が含まれている必要があります。 会社名     |     ✔️                         |              ✔️                |                         ✔️                        |
|  デバイスのシリアル番号    |   各デバイスのシリアル番号を新しい行に使用して、CSV 形式で Excel ファイルをアップロードします。     |     ✔️                         |              ✔️                |                         ✔️                        |

## <a name="submit-support-requests"></a>サポート リクエストの送信

> [!div class="nextstepaction"]
> [HoloLens 2 の Autopilot 登録サポート](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
