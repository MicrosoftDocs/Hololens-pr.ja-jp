---
title: MDM での HoloLens の登録
description: 複数のデバイスの管理を容易にするために、HoloLens をモバイルデバイス管理 (MDM) に登録する方法について説明します。
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
ms.openlocfilehash: 624ebd17335820b1d2858f9d39cabb7032a83bfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309714"
---
# <a name="enroll-hololens-in-mdm"></a>MDM での HoloLens の登録

[Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)などのソリューションを使用して、複数の Microsoft HoloLens デバイスを同時に管理できます。 設定の管理、インストールするアプリの選択、組織のニーズに合わせたセキュリティ構成の設定を行うことができます。 「[Microsoft Intune を使用して Windows Holographic を実行するデバイスを管理する](https://docs.microsoft.com/intune/windows-holographic-for-business)」、[Windows Holographic でサポートされている構成サービス プロバイダー (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) と [Windows Holographic for Business でサポートされているポリシー](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)に関するトピックを参照してください。

> [!NOTE]
> VPN、Bitlocker、キオスク モードの機能を含むモバイル デバイス管理 (MDM) は、[Windows Holographic for Business にアップグレード](hololens1-upgrade-enterprise.md)した場合にのみ使用できます。

## <a name="requirements"></a>要件

 HoloLens デバイスを管理するためには、組織でモバイルデバイス管理 (MDM) を設定する必要があります。 MDM プロバイダーには、Microsoft Intune や、Microsoft MDM API を使うサード パーティ プロバイダーを使うことができます。
 
## <a name="different-ways-to-enroll"></a>さまざまな登録方法

OOBE 中に選択された [id](hololens-identity.md) の種類によって、またはサインイン後に、さまざまな登録方法があります。

- Id が Azure AD 場合は、OOBE または **設定アプリ** で [  ->  **職場または学校へ** の  ->  **接続**] ボタンをクリックします。
    - Azure AD の場合、 [自動 MDM 登録](hololens-enroll-mdm.md#auto-enrollment-in-mdm) は、Azure AD が登録 url で構成されている場合にのみ実行されます。
     
- Id が Azure AD、デバイスが、割り当てられている特定の構成プロファイルを使用して Intune MDM サーバーに事前登録されている場合は、OOBE 中に Azure AD-Join と [自動 MDM 登録](hololens-enroll-mdm.md#auto-enrollment-in-mdm) が行われます。
    - [19041.1103 + ビルド](hololens-release-notes.md#windows-holographic-version-2004)で使用可能な[自動操縦フロー](hololens2-autopilot.md)とも呼ばれます。
    

- Id が MSA の場合は、[設定] [**アプリ**  ->  へのアクセス] [**職場または学校** への  ->  **接続**] ボタンを使用します。
    - "職場アカウントの追加 (AWA)" フローとも呼ばれます。
- Id がローカルユーザーの場合は、[設定] [**アプリ** へのアクセス] [  ->  **職場または学校**  ->  **に登録** する] リンクを使用します。
    - 純粋 MDM 登録フローとも呼ばれます。

デバイスが MDM サーバーに登録されると、デバイスがデバイス管理に登録されていることが設定アプリに反映されるようになります。

## <a name="auto-enrollment-in-mdm"></a>MDM への自動登録

組織が [Azure Premium サブスクリプション](https://azure.microsoft.com/overview/)を持っていて、Azure Active Directory (Azure AD) を使用していて、認証用の Azure AD トークンを受け入れる mdm ソリューション (現時点では Microsoft Intune と航空監視でのみサポートされている) を使用している場合、IT 管理者は Azure AD アカウントでユーザーがサインインした後に MDM 登録を自動的に許可するように Azure AD を構成 [Azure AD の登録を構成する方法をご覧ください。](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

自動登録が有効になっている場合、追加の手動登録は必要ありません。 ユーザーが Azure AD アカウントでサインインすると、最初の実行エクスペリエンスを完了した後デバイスが MDM に登録されます。

デバイスが参加 Azure AD と、 [デバイスの所有者](security-adminless-os.md#device-owner)と見なされたユーザーに影響を与える可能性があります。

## <a name="unenroll-hololens-from-intune"></a>Intune から HoloLens の登録を解除する

登録方法によっては、デバイスの登録解除が利用できない場合があります。

デバイスが Azure AD アカウントまたは自動操縦装置に登録されている場合、Intune から登録解除することはできません。 HoloLens を Azure AD から切断する場合、または Azure AD 別のテナントに再度参加させる場合は、デバイスを [リセット/更新](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) する必要があります。

仕事用アカウントを追加した MSA アカウント、またはデバイス管理のみに登録されているローカルアカウントからデバイスが登録されている場合は、デバイスの登録を解除することができます。 [スタート] メニューを開き、[設定] [**アプリ**  ->  **アクセス] [職場または学校**  ->  *アカウント* の  ->  **切断**] ボタンを選択します。