---
title: Intune とポータル サイト
description: Intune, アプリ管理, アプリ, ポータル ポータル, ポータル
keywords: intune, アプリ管理, アプリ, ポータル, ポータル, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 7871d5113b6803a3f702bf8d64f16fabc1c5a9bb
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252658"
---
# Intune と会社のポータル

モバイル デバイス管理 (MDM) を使用すると [、Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) を通じて独自のカスタム アプリを使用して、HoloLens デバイスに直接展開できます。 Microsoft Intune は、モバイル デバイス管理 (MDM) とモバイル アプリケーション管理 (MAM) に重点を置いたクラウドベースのサービスです。 Intune は Microsoft の [Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)スイートに含まれており、組織のデータを保護しながら生産性を高めることができます。 Intune の詳細については、「Intune とは [」を参照してください](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)。

## セットアップ

1. アプリを Line of Business にアップロードするか、カスタム アプリを Intune テナントにアップロードします。 「エンタープライズ アプリ [管理」も参照してください](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)。

2. [アプリをグループに割り当てる](https://docs.microsoft.com/mem/intune/apps/apps-deploy)。 選択した割り当ての種類に基づいて、アプリを自動的に配信したり、選択したアプリがある場合は簡単に取得できます。

> [!NOTE]
> appx バンドルを構築する場合は、展開するデバイスのアーキテクチャを含む必要があります。 HoloLens 2 は ARM64、HoloLens (第 1 世代) は x86 です。 混在するデバイス環境を計画している場合は、両方を単一の appx バンドルに含めできます。

## 割り当ての種類

登録後にアプリをデバイスに自動的にインストールするには、そのグループに対して **[必須** ] を選択する必要があります。
ポータル サイトから登録されたデバイスにアプリをダウンロードするには、[登録済みデバイスで利用可能] **を選択します**。

## End-User エクスペリエンス

Intune で構成を設定すると、エンド ユーザーが選択したアプリを受け取る準備が整います。

アプリを自動的に取得するには、次の手順を実行します。

1. デバイスをテナントに登録します。
2. デバイスの登録が完了したら、デバイスでアプリを受け取る必要があります。
3. If you are not see you app immediately, go to **Settings**  >  **Accounts**  >  **Work or School**your  >  *account* Info, and scroll down to see information on installed app status.

ポータル サイトからアプリにアクセスする方法:

1. スタート メニュー **を開き、Microsoft** **Store を選択します**。
2. ポータル サイト **を検索し** 、アプリをダウンロードします。
3. アカウントにサインインします。
4. 受信するアプリを選択し、ダウンロードします。

> [!Tip]
> ポータル サイトの [自動インストールと](https://docs.microsoft.com/mem/intune/apps/company-portal-app) Intune でのアプリの展開と管理について [詳しく知る](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)。
