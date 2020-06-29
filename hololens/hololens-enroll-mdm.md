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
ms.date: 07/15/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 054c4ded7496957671c055e3161a1297de7abc1a
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828692"
---
# MDM での HoloLens の登録

[Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)などのソリューションを使用して、複数の microsoft HoloLens デバイスを同時に管理できます。 設定の管理、インストールするアプリの選択、組織のニーズに合わせたセキュリティ構成の設定を行うことができます。 「[Microsoft Intune を使用して Windows Holographic を実行するデバイスを管理する](https://docs.microsoft.com/intune/windows-holographic-for-business)」、[Windows Holographic でサポートされている構成サービス プロバイダー (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) と [Windows Holographic for Business でサポートされているポリシー](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)に関するトピックを参照してください。

> [!NOTE]
> VPN、Bitlocker、キオスク モードの機能を含むモバイル デバイス管理 (MDM) は、[Windows Holographic for Business にアップグレード](hololens1-upgrade-enterprise.md)した場合にのみ使用できます。

## 要件

 HoloLens デバイスを管理するには、組織でモバイルデバイス管理 (MDM) を設定する必要があります。 MDM プロバイダーには、Microsoft Intune や、Microsoft MDM API を使うサード パーティ プロバイダーを使うことができます。

## MDM への自動登録

Azure Active Directory (Azure AD) と、認証用の AAD トークンを受け入れる MDM ソリューション (現在のところ、Microsoft Intune と AirWatch でのみサポートされている場合) を組織で使っている場合、IT 管理者はユーザーが Azure AD アカウントにサインインした後 MDM 登録が自動的に行われるように Azure AD を構成できます。 [Azure AD の登録を構成する方法をご覧ください。](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

自動登録が有効な場合、追加の手動登録は必要ありません。 ユーザーが Azure AD アカウントでサインインすると、最初の実行エクスペリエンスを完了した後デバイスが MDM に登録されます。

## 設定アプリを使った登録

 最初の実行エクスペリエンス時にデバイスが MDM に登録されない場合、ユーザーは設定アプリを使って組織の MDM サーバーにデバイスを手動で登録できます。

1. **[設定]** > **[アカウント]** > **[職場のアクセス]** の順に移動します。
1. **[デバイス管理 (MDM) に登録する]** を選び、組織アカウントを入力します。 組織のサインイン ページにリダイレクトされます。
1. MDM サーバーでの認証に成功すると、成功を示すメッセージが表示されます。

これで、デバイスが MDM サーバーに登録されました。 設定アプリに、デバイスがデバイス管理に登録されたことが反映されます。

## Intune からの HoloLens の登録解除

Intune からリモートで HoloLens を[登録解除する](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows)ことはできません。 管理者が MDM を使用してデバイスを登録解除する場合、デバイスは Intune ダッシュボードから削除されます。
