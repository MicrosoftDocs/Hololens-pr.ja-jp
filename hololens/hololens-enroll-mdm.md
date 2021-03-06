---
title: MDM での HoloLens の登録
description: 複数のデバイスを簡単に管理するために、HoloLens をモバイル デバイス管理 (MDM) に登録する方法について説明します。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5613c69bda8bbf70722a050ac5ce4ebeab95d332
ms.sourcegitcommit: 771e53feefbcc6bce18577515ad7d3f6a7f33840
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399385"
---
# <a name="enroll-hololens-in-mdm"></a>MDM での HoloLens の登録

Microsoft Intune のようなソリューションを使用して、複数の Microsoft HoloLens デバイスを同時 [に管理できます](https://docs.microsoft.com/intune/windows-holographic-for-business)。 設定の管理、インストールするアプリの選択、組織のニーズに合わせたセキュリティ構成の設定を行うことができます。 「[Microsoft Intune を使用して Windows Holographic を実行するデバイスを管理する](https://docs.microsoft.com/intune/windows-holographic-for-business)」、[Windows Holographic でサポートされている構成サービス プロバイダー (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) と [Windows Holographic for Business でサポートされているポリシー](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)に関するトピックを参照してください。

> [!NOTE]
> VPN、Bitlocker、キオスク モードの機能を含むモバイル デバイス管理 (MDM) は、[Windows Holographic for Business にアップグレード](hololens1-upgrade-enterprise.md)した場合にのみ使用できます。

## <a name="requirements"></a>要件

 HoloLens デバイスを管理するには、組織でモバイル デバイス管理 (MDM) を設定する必要があります。 MDM プロバイダーには、Microsoft Intune や、Microsoft MDM API を使うサード パーティ プロバイダーを使うことができます。
 
## <a name="different-ways-to-enroll"></a>さまざまな登録方法

OOBE またはサインイン後に選択される ID の種類に応じて、登録方法は異なります。 HoloLens の ID の各種類の詳細については、このページを [参照してください](hololens-identity.md)。

- Identity が Azure AD場合は、OOBE または **[** 設定] アプリ アクセス作業時間または学校接続  ->  ****  ->  ボタン**のどちらか**です。
    - Azure の場合AD MDM の自動登録は、Azure サーバーが登録 URL AD構成されている場合にのみ発生します。
- Identity が Azure AD で、デバイスが特定の構成プロファイルが割り当てられた Intune MDM サーバーに事前登録されている場合、Azure AD-Join と登録は OOBE 中に自動的に発生します。
    - また [、Autopilot flow Available in](hololens2-autopilot.md) [19041.1103+ ビルドとも呼ばれる](hololens-release-notes.md#windows-holographic-version-2004)。
- Identity が MSA の場合は、[設定]**アプリ**アクセス作業時間または学校  ->  **接続ボタン**  ->  **を使用**します。
    - 作業アカウントの追加 (AWA) フローとも呼ばれる。
- Id がローカル ユーザーの場合は、[設定]**アプリ**アクセス作業時間または学校登録のみをデバイス管理  ->  ****  ->  **リンクで使用**します。
    - 純粋な MDM 登録フローとも呼ばれる。

デバイスが MDM サーバーに登録された後、設定アプリはデバイスがデバイス管理に登録されたと反映されます。

## <a name="auto-enrollment-in-mdm"></a>MDM への自動登録

組織で Azure Active Directory (Azure AD) と認証用に Azure AD トークンを受け入れる MDM ソリューション (現在は Microsoft Intune と AirWatch でのみサポート) を使用している場合、IT 管理者は、ユーザーが Azure AD アカウントでサインインした後に MDM 登録を自動的に許可するように Azure AD を構成できます。 [Azure AD の登録を構成する方法をご覧ください。](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

自動登録が有効な場合、追加の手動登録は必要ありません。 ユーザーが Azure AD アカウントでサインインすると、最初の実行エクスペリエンスを完了した後デバイスが MDM に登録されます。

デバイスが Azure デバイスの場合AD参加している場合、デバイスの所有者と見なされるユーザーに [影響を与える可能性があります](security-adminless-os.md#device-owner)。

## <a name="unenroll-hololens-from-intune"></a>Intune から HoloLens の登録を解除する

HoloLens 2 は Windows 10 デバイスですが、Intune から単に登録解除することはできません。 Azure AD から HoloLens の接続を解除するか、Azure AD テナントとは別のテナントに再び追加する場合は、デバイスをリセット [または再](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) フラッシュする必要があります。