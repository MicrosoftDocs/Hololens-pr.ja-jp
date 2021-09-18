---
title: MDM での HoloLens の登録
description: 複数のデバイスを簡単に管理できるように、モバイルデバイス管理 (MDM) に HoloLens を登録する方法について説明します。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/15/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b6206f7121d1ba78908d96f71c5c809ec97b06d5
ms.sourcegitcommit: 6c8406bbcc79c1f624736cc68e1aaeab70436902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2021
ms.locfileid: "127904346"
---
# <a name="enroll-hololens-in-mdm"></a>MDM での HoloLens の登録

[Microsoft Intune](/intune/windows-holographic-for-business)などのソリューションを使用して、複数の Microsoft HoloLens デバイスを同時に管理できます。 設定の管理、インストールするアプリの選択、組織のニーズに合わせたセキュリティ構成の設定を行うことができます。 「[Microsoft Intune を使用して Windows Holographic を実行するデバイスを管理する](/intune/windows-holographic-for-business)」、[Windows Holographic でサポートされている構成サービス プロバイダー (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) と [Windows Holographic for Business でサポートされているポリシー](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)に関するトピックを参照してください。

> [!NOTE]
> VPN、Bitlocker、キオスク モードの機能を含むモバイル デバイス管理 (MDM) は、[Windows Holographic for Business にアップグレード](hololens1-upgrade-enterprise.md)した場合にのみ使用できます。

## <a name="requirements"></a>要件

 HoloLens デバイスを管理するために、組織でモバイルデバイス管理 (MDM) を設定する必要があります。 MDM プロバイダーには、Microsoft Intune や、Microsoft MDM API を使うサード パーティ プロバイダーを使うことができます。

## <a name="different-ways-to-enroll"></a>さまざまな登録方法

OOBE 中に選択された [id](hololens-identity.md) の種類によって、またはサインイン後に、さまざまな登録方法があります。

- id が Azure AD 場合は、OOBE の間、または **設定 App** Access の [  ->  **職場または学校**  ->  **Connect** ] ボタンをクリックします。
    - Azure AD の場合、 [自動 MDM 登録](hololens-enroll-mdm.md#auto-enrollment-in-mdm) は、Azure AD が登録 url で構成されている場合にのみ実行されます。

- Id が Azure AD、デバイスが、割り当てられている特定の構成プロファイルを使用して Intune MDM サーバーに事前登録されている場合は、OOBE 中に Azure AD-Join と [自動 MDM 登録](hololens-enroll-mdm.md#auto-enrollment-in-mdm) が行われます。
    - [19041.1103 + ビルド](hololens-release-notes.md#windows-holographic-version-2004)で使用可能な[自動操縦フロー](hololens2-autopilot.md)とも呼ばれます。


- id が MSA の場合は **設定アプリ**  ->  **アクセス職場または学校**  ->  **Connect** ボタンを使用します。
    - "職場アカウントの追加 (AWA)" フローとも呼ばれます。
- id がローカルユーザーの場合、[デバイスの管理] リンクで **設定アプリ**  ->  **アクセス職場または学校**  ->  **の登録のみ** を使用します。
    - 純粋 MDM 登録フローとも呼ばれます。

デバイスが MDM サーバーに登録されると、デバイスがデバイス管理に登録されていることが設定アプリに反映されるようになります。

## <a name="auto-enrollment-in-mdm"></a>MDM への自動登録

組織に[Azure プレミアムサブスクリプション](https://azure.microsoft.com/overview/)があり、Azure Active Directory (Azure AD) を使用していて、認証のために Azure AD トークンを受け入れる mdm ソリューション (現時点では、Microsoft Intune と航空監視でのみサポートされています) を使用している場合、IT 管理者は、ユーザーが Azure AD アカウントでサインインした後に MDM 登録を自動的に許可するように Azure AD を [Azure AD の登録を構成する方法をご覧ください。](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

自動登録が有効になっている場合、追加の手動登録は必要ありません。 ユーザーが Azure AD アカウントでサインインすると、最初の実行エクスペリエンスを完了した後デバイスが MDM に登録されます。

デバイスが参加 Azure AD と、 [デバイスの所有者](security-adminless-os.md#device-owner)と見なされたユーザーに影響を与える可能性があります。

## <a name="unenroll-hololens-from-intune"></a>Intune から HoloLens の登録を解除する

登録方法によっては、デバイスの登録解除が利用できない場合があります。

デバイスが Azure AD アカウントまたは自動操縦装置に登録されている場合、Intune から登録解除することはできません。 Azure AD から HoloLens を解除する場合、または Azure AD 別のテナントに再参加する場合は、デバイスを[リセット/更新](hololens-recovery.md#reset-the-device)する必要があります。

仕事用アカウントを追加した MSA アカウント、またはデバイス管理のみに登録されているローカルアカウントからデバイスが登録されている場合は、デバイスの登録を解除することができます。 スタートメニューを開き、[**設定アプリ**  ->  **アクセスの職場または学校**  ->  *アカウント* の  ->  **切断**] ボタンを選択します。

## <a name="enrollment-troubleshooting"></a>登録のトラブルシューティング

### <a name="ensure-valid-license-is-assigned-to-the-user"></a>有効なライセンスがユーザーに割り当てられていることを確認する

詳細については、 [Microsoft Intune 以下のセクションの「デバイスの登録に関する問題のトラブル Windows シューティング](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors)」を参照してください。たとえば、デバイスの種類の制限を[確認](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#check-device-type-restrictions)し、[ユーザーに有効なライセンスを割り当て](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#assign-a-valid-license-to-the-user)ます。

### <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>Windows デバイスの MDM 登録がブロックされていないことを確認する

登録を成功させるには、HoloLens デバイスが登録できることを確認する必要があります。 HoloLens は Windows デバイスと見なされるため、デプロイをブロックする登録の制限がない必要があります。 [この制限の一覧を確認](/mem/intune/enrollment/enrollment-restrictions-set)し、デバイスを登録できることを確認してください。