---
title: HoloLens 2 の証明書とネットワーク プロファイルを準備する
description: HoloLens 2 デバイスでネットワーク用の証明書を構成して使用する方法
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 460b6f42de7413e77eaec041a5ab6141ed959cf4
ms.sourcegitcommit: 9944fd2040fc1267ace1da1bd62ef36b68c7f318
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015525"
---
# HoloLens 2 の証明書とネットワーク プロファイルを準備する

証明書ベースの認証は、HoloLens 2 を使用するお客様の共通の要件です。 Wi-Fi にアクセスしたり、VPN ソリューションに接続したり、組織内の内部リソースにアクセスしたりするために証明書が必要となる可能性があります。

HoloLens 2 デバイスは通常、Azure Active Directory (Azure AD) に参加し、Intune やその他の MDM プロバイダーによって管理されるため、ご利用の MDM ソリューションに統合されているネットワーク デバイス登録サービス (SCEP) や公開キー暗号化標準 (PKCS) 証明書インフラストラクチャを使用して、そのような証明書を展開する必要があります。

## 証明書の要件
SCEP や PKCS インフラストラクチャを介して証明書を展開するには、ルート証明書が必要です。 組織内のその他のアプリケーションやサービスでは、HoloLens 2 デバイスにもルート証明書を展開する必要がある可能性があります。 

## Wi-Fi 接続要件
企業ネットワークに必要な Wi-Fi 構成をデバイスに自動的に提供できるようにするには、Wi-Fi 構成プロファイルが必要です。 Intune やその他の MDM プロバイダーを構成して、これらのプロファイルをデバイスに展開することができます。 ネットワーク セキュリティによりデバイスをローカル ドメインの一部にする必要がある場合は、ご利用の Wi-Fi ネットワーク インフラストラクチャを評価し、HoloLens 2 デバイスとの互換性があることを確認する必要がある可能性があります (HoloLens 2 デバイスは Azure AD 参加済みのもののみ)。

## 証明書インフラストラクチャを展開する
既存の SCEP や PKCS インフラストラクチャが存在しない場合は、1 つ用意する必要があります。 認証に SCEP や PKCS 証明書の使用をサポートするために、Intune では[証明書コネクタ](https://docs.microsoft.com/mem/intune/protect/certificate-connectors)の使用が必要になります。

> [!NOTE]
> Microsoft CA で SCEP を使用する場合、[ネットワーク デバイス登録サービス (NDES)](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes) も構成する必要があります

詳細については、「[Configure a certificate profile for your devices in Microsoft Intune (Microsoft Intune でデバイスの証明書プロファイルを構成する)](https://docs.microsoft.com/intune/certificates-configure)」を参照してください。

## 証明書と Wi-Fi/VPN プロファイルを展開する
証明書とプロファイルを展開するには、次の手順に従います。
1.  ルート証明書と中間証明書のそれぞれにプロファイルを作成します (「[Create trusted certificate profiles (信頼された証明書プロファイルを作成する)](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles)」を参照してください)。これらのプロファイルのそれぞれには、DD/MM/YYYY 形式による有効期限を含む説明が必要となります。 **有効期限のない証明書プロファイルは、展開されません。**
1.  SCEP 証明書または PKCS 証明書のそれぞれにプロファイルを作成します (「[Create a SCEP certificate profile or Create a PKCS certificate profile (SCEP 証明書プロファイルの作成または PKCS 証明書プロファイルの作成)](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)」を参照してください)。これらのプロファイルのそれぞれには、DD/MM/YYYY 形式による有効期限を含む説明が必要となります。 **有効期限のない証明書プロファイルは、展開されません。**

> [!NOTE]
> HoloLens 2 は共有デバイスであり、デバイスごとに複数のユーザーがいると多くの方々に考えられているため、可能であれば Wi-Fi 認証にはユーザー証明書ではなくデバイス証明書の実装をお勧めします

3.  企業の Wi-Fi ネットワークのそれぞれにプロファイルを作成します (「[Wi-Fi settings for Windows 10 and later devices (Windows 10 以降のデバイス向けの Wi-Fi 設定)](https://docs.microsoft.com/intune/wi-fi-settings-windows)」を参照してください)。 
> [!NOTE]
> Wi-Fi プロファイルは、可能であればユーザー グループではなくデバイス グループに[割り当てる](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)ことをお勧めします。 

> [!TIP]
> また、企業ネットワーク上の Windows 10 PC から実行中の Wi-Fi プロファイルをエクスポートすることもできます。 このエクスポートでは、現在のすべての設定を含む XML ファイルが作成されます。 次に、このファイルを Intune にインポートして、HoloLens 2 デバイスの Wi-Fi プロファイルとして使用します。 「[Export and import Wi-Fi settings for Windows devices (Windows デバイスの Wi-Fi 設定のエクスポートとインポート)](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)」を参照してください。

4.  企業 VPN のそれぞれにプロファイルを作成します (「[Windows 10 and Windows Holographic device settings to add VPN connections using Intune (Windows 10 と Windows Holographic デバイスの設定で Intune を使用して VPN 接続を追加する)](https://docs.microsoft.com/intune/vpn-settings-windows-10)」)。




