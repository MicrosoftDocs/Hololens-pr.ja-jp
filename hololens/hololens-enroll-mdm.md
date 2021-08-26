---
title: MDM での HoloLens の登録
description: 複数のデバイスを簡単HoloLens管理するために、モバイル デバイス管理 (MDM) にデバイスを登録する方法について説明します。
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
ms.openlocfilehash: 5ded375d88740b9367eec87e4e902c423f131689
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2021
ms.locfileid: "122858985"
---
# <a name="enroll-hololens-in-mdm"></a>MDM での HoloLens の登録

のようなソリューションを使用してMicrosoft HoloLens複数のデバイスを同時[に管理Microsoft Intune。](/intune/windows-holographic-for-business) 設定の管理、インストールするアプリの選択、組織のニーズに合わせたセキュリティ構成の設定を行うことができます。 「[Microsoft Intune を使用して Windows Holographic を実行するデバイスを管理する](/intune/windows-holographic-for-business)」、[Windows Holographic でサポートされている構成サービス プロバイダー (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) と [Windows Holographic for Business でサポートされているポリシー](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)に関するトピックを参照してください。

> [!NOTE]
> VPN、Bitlocker、キオスク モードの機能を含むモバイル デバイス管理 (MDM) は、[Windows Holographic for Business にアップグレード](hololens1-upgrade-enterprise.md)した場合にのみ使用できます。

## <a name="requirements"></a>要件

 組織では、モバイル デバイスを管理デバイス管理 Mobile デバイス管理 (MDM) を設定HoloLensがあります。 MDM プロバイダーには、Microsoft Intune や、Microsoft MDM API を使うサード パーティ プロバイダーを使うことができます。

## <a name="different-ways-to-enroll"></a>登録するさまざまな方法

OOBE またはサインイン後に選択される [ID](hololens-identity.md) の種類に応じて、登録方法は異なります。

- [IDENTITY] がAzure AD場合は、OOBE 中またはApp Access Work または School 設定ボタンのいずれかを使用  ->    ->  Connectします。
    - たとえばAzure AD MDM の [自動](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 登録は、登録 URL Azure AD構成されている場合にのみ発生します。

- ID が Azure AD され、デバイスが特定の構成プロファイルが割り当てられた Intune MDM サーバーに事前登録されている場合、Azure AD-Join と [自動 MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 登録は OOBE 中に行われます。
    - [19041.1103+](hololens-release-notes.md#windows-holographic-version-2004)ビルドで利用可能な[Autopilot](hololens2-autopilot.md)フローとも呼ばれる。


- IDENTITY が MSA の場合は、[App Access Work **設定**  ->  **School]** ボタンを使用Connect  ->  します。
    - 作業アカウントの追加 (AWA) フローとも呼ばれる。
- [ID] が [ローカル ユーザー] の場合は、設定アプリ アクセスの [仕事] または **[** 学校の登録]  ->    ->  **のみをデバイス管理リンクで使用** します。
    - 純粋 MDM 登録フローとも呼ばれる。

デバイスが MDM サーバーに登録された後、設定アプリにデバイスがデバイス管理に登録されたと反映されます。

## <a name="auto-enrollment-in-mdm"></a>MDM への自動登録

組織に Azure[プレミアム](https://azure.microsoft.com/overview/)サブスクリプション がある場合は、Azure Active Directory (Azure AD) と認証に Azure AD トークンを受け入れる MDM ソリューション (現在は Microsoft Intune と AirWatch でのみサポートされています) を使用している場合、IT 管理者は、ユーザーが Azure AD アカウントでサインインした後に MDM 登録を自動的に許可するように Azure AD を構成できます。 [Azure AD の登録を構成する方法をご覧ください。](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

自動登録が有効になっている場合は、追加の手動登録は必要はありません。 ユーザーが Azure AD アカウントでサインインすると、最初の実行エクスペリエンスを完了した後デバイスが MDM に登録されます。

デバイスが [参加中Azure AD、デバイス所有者と見なされたユーザーに [影響する可能性があります](security-adminless-os.md#device-owner)。

## <a name="unenroll-hololens-from-intune"></a>Intune からHoloLens登録を解除する

登録方法によっては、デバイスの登録を解除できない場合があります。

デバイスがアカウントまたは Autopilot Azure AD登録されている場合、Intune から登録を解除することはできません。 Azure AD から HoloLens への登録を解除する場合、または Azure AD テナントとは別のテナントに再び追加する場合は、デバイスをリセット[または](hololens-recovery.md#reset-the-device)再フラッシュする必要があります。

仕事用アカウントを追加した MSA アカウントまたはデバイス管理にのみ登録されたローカル アカウントからデバイスが登録されている場合は、デバイスの登録を解除できます。 [アプリ] スタート メニューを開き、[App Access Work 設定 School  ->    ->  *YourAccount* Disconnect] ボタンを  ->  選択します。

## <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>デバイスの MDM 登録がブロックWindowsする

Autopilot を正常に実行するには、デバイスからデバイスを登録HoloLensする必要があります。 デバイスHoloLensと見なWindows展開をブロックする登録制限は必要ない必要があります。 [この制限の一覧を確認](/mem/intune/enrollment/enrollment-restrictions-set) し、デバイスを登録できる必要があります。