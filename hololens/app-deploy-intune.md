---
title: Intune と ポータル サイト
description: Intune、モバイル デバイス管理、およびポータル サイトを使用して、快適なユーザー エクスペリエンスを設定、割り当て、作成する方法について説明します。
keywords: Intune, アプリ管理, アプリ, ポータル サイト, ポータル, Hololens
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
ms.openlocfilehash: b192732f5e7edffaa1d0ab081454e4034c416191
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635502"
---
# <a name="intune--company-portal"></a>Intune & ポータル サイト

Mobile デバイス管理 (MDM) を使用すると[、Microsoft エンドポイント マネージャー (Intune)](/intune/windows-holographic-for-business)を使用して独自のカスタム アプリを使用して、HoloLens デバイスに直接展開できます。 Microsoft Intune は、モバイル デバイス管理 (MDM) とモバイル アプリケーション管理 (MAM) を中心にしたクラウドベースのサービスです。 Intune は、Microsoft の [Enterprise Mobility + Security (EMS) スイート](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)に含まれており、組織のデータを保護したまま、ユーザーの生産性を高めることができます。 Intune の詳細については、「Intune とは [」を参照してください](/mem/intune/fundamentals/what-is-intune)。

## <a name="setup"></a>セットアップ

1. アップロードを Line of Business にアップロードするか、カスタム アプリを Intune テナントにアップロードします。 「アプリ管理[のEnterprise」も参照してください](/windows/client-management/mdm/enterprise-app-management)。

2. [アプリをグループ に割り当てる](/mem/intune/apps/apps-deploy)。 選択した割り当ての種類に基づいて、アプリを自動的に配信したり、選択したアプリがある場合は簡単に引き下げられたりすることができます。

> [!NOTE]
> appx バンドルを構築する場合は、デプロイするデバイスのアーキテクチャを含め、必ず考慮してください。 HoloLens 2 ARM64 で、HoloLens (第 1 世代) は x86 です。 混在するデバイス環境を計画している場合は、両方を単一の appx バンドルに含める場合があります。

## <a name="assignment-types"></a>割り当ての種類

登録後にアプリをデバイスに自動的にインストールするには、そのグループに対して[必須] を選択する必要があります。
ポータル サイトを使用して登録されたデバイスにアプリをダウンロードするには、[登録済みデバイスで使用可能] **を選択します**。

## <a name="end-user-experience"></a>エンドユーザー エクスペリエンス

Intune で構成を設定すると、エンド ユーザーが選択したアプリを受け取る準備が整います。

アプリを自動的に取得するには、次の手順に従います。

1. デバイスをテナントに登録します。
2. デバイスの登録が完了すると、デバイスでアプリを受け取る必要があります。
3. アプリがすぐに表示されない場合は、[設定アカウントの作業または学校のアカウント情報] に移動し、下にスクロールしてインストールされているアプリの状態に関する  >    >    >  情報を表示します。

次の方法でアプリにアクセスポータル サイト。

1. [スタート]**メニューを開き**、[ ]**をMicrosoft Store。**
2. アプリを **検索ポータル サイト** アプリをダウンロードします。
3. アカウントにサインインします。
4. 受信するアプリを選択してダウンロードします。

> [!Tip]
> Intune での[アプリの自動インストール](/mem/intune/apps/company-portal-app)とポータル サイトおよび管理の詳細については、[以下を参照してください](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)。
