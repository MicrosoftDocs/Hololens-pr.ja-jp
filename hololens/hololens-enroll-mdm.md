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
ms.openlocfilehash: 5adc1b48c4603f3a9d3145bef4f1d8aa1867a9d1
ms.sourcegitcommit: 5877c3e51de49f949b35ab840a3312a009a4487a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "11102326"
---
# MDM での HoloLens の登録

[Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)などのソリューションを使用して、複数の microsoft HoloLens デバイスを同時に管理できます。 設定の管理、インストールするアプリの選択、組織のニーズに合わせたセキュリティ構成の設定を行うことができます。 「[Microsoft Intune を使用して Windows Holographic を実行するデバイスを管理する](https://docs.microsoft.com/intune/windows-holographic-for-business)」、[Windows Holographic でサポートされている構成サービス プロバイダー (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) と [Windows Holographic for Business でサポートされているポリシー](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)に関するトピックを参照してください。

> [!NOTE]
> VPN、Bitlocker、キオスク モードの機能を含むモバイル デバイス管理 (MDM) は、[Windows Holographic for Business にアップグレード](hololens1-upgrade-enterprise.md)した場合にのみ使用できます。

## 要件

 HoloLens デバイスを管理するには、組織でモバイルデバイス管理 (MDM) を設定する必要があります。 MDM プロバイダーには、Microsoft Intune や、Microsoft MDM API を使うサード パーティ プロバイダーを使うことができます。
 
## さまざまな登録方法

OOBE または投稿のサインインのいずれかで選択された id の種類に応じて、さまざまな登録方法があります。 HoloLens の各種類の Id の詳細については、 [このページ](hololens-identity.md)をご覧ください。

- Id が AAD の場合は、OOBE または**設定アプリ**への [  ->  **職場または学校**の  ->  **接続**] ボタンをクリックします。
    - AAD の場合、自動 MDM 登録は、AAD が登録 Url で構成されている場合にのみ発生します。
- Id が AAD であり、デバイスが、特定の構成プロファイルが割り当てられた Intune MDM サーバーに事前登録されている場合、AAD での参加と登録は自動的に行われます。
    - [19041.1103 + ビルド](hololens-release-notes.md#windows-holographic-version-2004)で利用可能な[自動操縦フロー](hololens2-autopilot.md)とも呼ばれます。
- Id が MSA の場合は、[**アプリ**  ->  **アクセスの職場または学校**の  ->  **接続**] ボタンを使用します。
    - [ワークアカウントの追加] (AWA) フローとも呼ばれます。
- Id が Local ユーザーの場合は、[**設定] アプリ**  ->  **へのアクセスは**、[  ->  **デバイス管理] リンクでのみ**機能します。
    - 純粋 MDM の登録フローとも呼ばれます。

デバイスが MDM サーバーに登録されると、設定アプリはデバイス管理にデバイスが登録されたことを反映するようになります。

## MDM への自動登録

Azure Active Directory (Azure AD) と、認証用の AAD トークンを受け入れる MDM ソリューション (現在のところ、Microsoft Intune と AirWatch でのみサポートされている場合) を組織で使っている場合、IT 管理者はユーザーが Azure AD アカウントにサインインした後 MDM 登録が自動的に行われるように Azure AD を構成できます。 [Azure AD の登録を構成する方法をご覧ください。](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

自動登録が有効な場合、追加の手動登録は必要ありません。 ユーザーが Azure AD アカウントでサインインすると、最初の実行エクスペリエンスを完了した後デバイスが MDM に登録されます。

デバイスが AAD に参加している場合、 [デバイス所有者](security-adminless-os.md#device-owner)と見なされるユーザーに影響を与える可能性があります。

## Intune からの HoloLens の登録解除

デバイスの未登録の詳細については、 [このページ](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment)をご覧ください。 
