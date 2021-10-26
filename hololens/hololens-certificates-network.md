---
title: HoloLens 2 の証明書とネットワーク プロファイルを準備する
description: HoloLens 2 Mixed Reality デバイスでネットワーク用証明書を構成、使用、展開、トラブルシューティングする方法について説明します。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: c7c15cc0630f11d1687db19f2e6b28b8347dd4c3
ms.sourcegitcommit: f105a770814ccd61e88b650448902a03c95b7a3c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2021
ms.locfileid: "130151668"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>HoloLens 2 の証明書とネットワーク プロファイルを準備する

証明書ベースの認証は、HoloLens 2 を使用するお客様の共通の要件です。 Wi-Fi にアクセスしたり、VPN ソリューションに接続したり、組織内の内部リソースにアクセスしたりするために証明書が必要となる可能性があります。

HoloLens 2 デバイスは通常、Azure Active Directory (Azure AD) に参加し、Intune やその他の MDM プロバイダーによって管理されるため、ご利用の MDM ソリューションに統合されているネットワーク デバイス登録サービス (SCEP) や公開キー暗号化標準 (PKCS) 証明書インフラストラクチャを使用して、そのような証明書を展開する必要があります。 

>[!NOTE]
> MDM プロバイダーがない場合でも、 [Windows 構成デザイナー](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab)の [プロビジョニングパッケージ](hololens-provisioning.md#create-the-provisioning-package)または [証明書マネージャー](certificate-manager.md)を使用して証明書を展開することができます。そのためには、 **[設定] > [アップデートとセキュリティ] > [証明書マネージャー]** の順に移動します。

## <a name="certificate-requirements"></a>証明書の要件
SCEP や PKCS インフラストラクチャを介して証明書を展開するには、ルート証明書が必要です。 組織内のその他のアプリケーションやサービスでは、HoloLens 2 デバイスにもルート証明書を展開する必要がある可能性があります。 

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi 接続要件
企業ネットワークに必要な Wi-Fi 構成をデバイスに自動的に提供できるようにするには、Wi-Fi 構成プロファイルが必要です。 Intune やその他の MDM プロバイダーを構成して、これらのプロファイルをデバイスに展開することができます。 ネットワーク セキュリティによりデバイスをローカル ドメインの一部にする必要がある場合は、ご利用の Wi-Fi ネットワーク インフラストラクチャを評価し、HoloLens 2 デバイスとの互換性があることを確認する必要がある可能性があります (HoloLens 2 デバイスは Azure AD 参加済みのもののみ)。

## <a name="deploy-certificate-infrastructure"></a>証明書インフラストラクチャを展開する
既存の SCEP や PKCS インフラストラクチャが存在しない場合は、1 つ用意する必要があります。 認証に SCEP や PKCS 証明書の使用をサポートするために、Intune では[証明書コネクタ](/mem/intune/protect/certificate-connectors)の使用が必要になります。

> [!NOTE]
> Microsoft CA で SCEP を使用する場合は、[ネットワーク デバイス登録サービス (NDES) ](/mem/intune/protect/certificates-scep-configure#set-up-ndes)も構成する必要があります。

詳細については、「[Microsoft Intune でデバイスの証明書プロファイルを構成する](/intune/certificates-configure)」を参照してください。

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>証明書と Wi-Fi/VPN プロファイルを展開する
証明書とプロファイルを展開するには、次の手順に従います。
1.  ルート証明書と中間証明書のそれぞれにプロファイルを作成します (「[信頼証明書プロファイルの作成](/intune/protect/certificates-configure#create-trusted-certificate-profiles)」を参照してください)。各プロファイルには、DD/MM/YYYY 形式による有効期限を含む説明が必要です。 **有効期限のない証明書プロファイルは、展開されません。**
1.  SCEP 証明書または PKCS 証明書のそれぞれにプロファイルを作成します ([「SCEP 証明書プロファイルの作成」または「PKCS 証明書プロファイルの作成」](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)を参照してください)。各プロファイルには、DD/MM/YYYY 形式による有効期限を含む説明が必要です。 **有効期限のない証明書プロファイルは、展開されません。**

    > [!NOTE]
    > HoloLens 2 は共有デバイスであり、デバイスごとに複数のユーザーがいると多くの方が認識されているように、可能であれば Wi-Fi 認証にはユーザー証明書ではなくデバイス証明書を展開することをお勧めします

3.  企業の Wi-Fi ネットワークごとにプロファイルを作成します ([「Windows 10 以降のデバイスの Wi-Fi 設定」](/intune/wi-fi-settings-windows)を参照してください)。 
    > [!NOTE]
    > Wi-Fi プロファイルは、可能であればユーザー グループではなくデバイス グループに[割り当て済み](/mem/intune/configuration/device-profile-assign)にすることをお勧めします。 

    > [!TIP]
    > また、企業ネットワーク上の Windows 10 PC から実行中の Wi-Fi プロファイルをエクスポートすることもできます。 このエクスポートでは、現在のすべての設定を含む XML ファイルが作成されます。 次に、このファイルを Intune にインポートして、HoloLens 2 デバイスの Wi-Fi プロファイルとして使用します。 [Windows デバイスの Wi-Fi 設定のエクスポートとインポート](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)に関するページをご覧ください。

4.  企業 VPN ごとにプロファイルを作成します ([「Windows 10 および Windows Holographic デバイス設定で Intune を使用する VPN 接続を追加」](/intune/vpn-settings-windows-10)を参照)。

## <a name="troubleshooting-certificates"></a>証明書のトラブルシューティング

証明書が正しく展開されていることを検証する必要がある場合は、デバイスの[証明書マネージャー](certificate-manager.md)を使用して、証明書が存在することを確認してください。  

>[!WARNING]
> MDM によって展開された証明書は証明書マネージャーで表示できますが、証明書マネージャーでアンインストールすることはできません。 MDM を使用してアンインストールする必要があります。


