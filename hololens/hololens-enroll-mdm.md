---
title: MDM での HoloLens の登録
description: 複数のデバイスを管理しやすいように、モバイル デバイス管理 (MDM) に HoloLens を登録します。
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
ms.openlocfilehash: 7c17cbf88fc2e7a6dcd9aa600ad6e6910edb29a8
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253234"
---
# MDM での HoloLens の登録

Microsoft Intune のようなソリューションを使用して、複数の Microsoft HoloLens デバイスを同時 [に管理できます](https://docs.microsoft.com/intune/windows-holographic-for-business)。 設定の管理、インストールするアプリの選択、組織のニーズに合わせたセキュリティ構成の設定を行うことができます。 「[Microsoft Intune を使用して Windows Holographic を実行するデバイスを管理する](https://docs.microsoft.com/intune/windows-holographic-for-business)」、[Windows Holographic でサポートされている構成サービス プロバイダー (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) と [Windows Holographic for Business でサポートされているポリシー](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)に関するトピックを参照してください。

> [!NOTE]
> VPN、Bitlocker、キオスク モードの機能を含むモバイル デバイス管理 (MDM) は、[Windows Holographic for Business にアップグレード](hololens1-upgrade-enterprise.md)した場合にのみ使用できます。

## 要件

 HoloLens デバイスを管理するには、組織でモバイル デバイス管理 (MDM) をセットアップする必要があります。 MDM プロバイダーには、Microsoft Intune や、Microsoft MDM API を使うサード パーティ プロバイダーを使うことができます。
 
## さまざまな登録方法

OOBE またはサインイン後に選択される ID の種類に応じて、登録方法が異なります。 HoloLens の ID の各種類の詳細については、このページを [参照してください](hololens-identity.md)。

- Identity が Azure ADの場合は、OOBE または**設定**アプリアクセスの [仕事用または学校用接続]  ->  **ボタンのいずれかの操作を**  ->  **行**います。
    - Azure ADの場合、MDM の自動登録は、Azure AD URL で構成されている場合にのみ発生します。
- Identity が Azure AD であり、特定の構成プロファイルが割り当てられた Intune MDM サーバーにデバイスが事前登録されている場合、Azure AD-Join と登録は OOBE 中に自動的に行われます。
    - [19041.1103+](hololens-release-notes.md#windows-holographic-version-2004)ビルドで利用可能な[Autopilot](hololens2-autopilot.md)フローとも呼ばれる。
- IDENTITY が MSA の場合は、[設定]**アプリ**アクセスの [仕事用] ボタンまたは [学校接続]  ->  **ボタン**  ->  **を使用**します。
    - 作業アカウントの追加 (AWA) フローとも呼ばれる。
- IDENTITY がローカル ユーザーの場合は、[設定]**アプリ**アクセスの [仕事または学校の登録] をデバイス  ->  ****  ->  **管理リンクでのみ使用**します。
    - 純粋な MDM 登録フローとも呼ばれる。

デバイスが MDM サーバーに登録された後、設定アプリには、デバイスがデバイス管理に登録されたと反映されます。

## MDM への自動登録

組織で Azure Active Directory (Azure AD) と認証用に Azure AD トークンを受け入れる MDM ソリューションを使用している場合 (現在、Microsoft Intune と AirWatch でのみサポートされています)、IT 管理者は、ユーザーが Azure AD アカウントでサインインした後に MDM 登録を自動的に許可するように Azure AD を構成できます。 [Azure AD の登録を構成する方法をご覧ください。](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

自動登録が有効な場合、追加の手動登録は必要ありません。 ユーザーが Azure AD アカウントでサインインすると、最初の実行エクスペリエンスを完了した後デバイスが MDM に登録されます。

デバイスが Azure デバイスに参加AD、デバイスの所有者と見なされたユーザーに [影響を与える可能性があります](security-adminless-os.md#device-owner)。

## Intune から HoloLens を登録解除する

デバイスの登録解除の詳細については、このページ [を参照してください](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment)。 
