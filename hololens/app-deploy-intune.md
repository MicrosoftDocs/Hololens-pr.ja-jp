---
title: Intune とポータルサイト
description: Intune、モバイルデバイス管理、およびポータルサイトで、快適なユーザーエクスペリエンスをセットアップ、割り当て、作成する方法について説明します。
keywords: intune、アプリ管理、アプリ、ポータルサイト、ポータル、hololens
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
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309731"
---
# <a name="intune--company-portal"></a>Intune & ポータルサイト

モバイルデバイス管理 (MDM) を使用すると、 [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) を通じて独自のカスタムアプリを使用して、直接 HoloLens デバイスに展開することができます。 Microsoft Intune は、モバイル デバイス管理 (MDM) とモバイル アプリケーション管理 (MAM) を中心にしたクラウドベースのサービスです。 Intune は、Microsoft の [Enterprise Mobility + Security (EMS) スイート](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)に含まれており、組織のデータを保護したまま、ユーザーの生産性を高めることができます。 Intune の詳細については、「 [intune とは](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)」を参照してください。

## <a name="setup"></a>セットアップ

1. アプリを基幹業務にアップロードするか、Intune テナントにカスタムアプリをアップロードします。 「 [エンタープライズアプリ管理](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)」も参照してください。

2. [アプリをグループに割り当て](https://docs.microsoft.com/mem/intune/apps/apps-deploy)ます。 選択した割り当ての種類に基づいて、アプリを自動的に配信することも、アプリを選択している場合はすぐに利用できるようにすることもできます。

> [!NOTE]
> Appx バンドルを構築するときは、デプロイ先のデバイスのアーキテクチャを含めるようにしてください。 HoloLens 2 は ARM64、HoloLens (第1世代) は x86 です。 混合デバイス環境を使用する場合は、両方を1つの appx バンドルに含めることができます。

## <a name="assignment-types"></a>割り当ての種類

登録後にアプリがデバイスに自動的にインストールされるようにするには、そのグループに対して [ **必須** ] を選択する必要があります。
ポータルサイトで登録されているデバイスにアプリをダウンロードできるようにするには、[ **登録済みデバイスで利用可能**] を選択します。

## <a name="end-user-experience"></a>エンドユーザー エクスペリエンス

Intune で構成を設定した後、エンドユーザーが選択したアプリを受信できるようになります。

アプリを自動的に取得するには、次の手順に従います。

1. テナントにデバイスを登録します。
2. デバイスの登録が完了したら、デバイスでアプリを受信する必要があります。
3. アプリがすぐに表示されない場合は、[**設定**] [  >  **アカウント**  >  ] [職場]**または [学校** の  >  *アカウント* 情報] に移動し、下にスクロールして、インストールされているアプリの状態に関する情報を表示します。

ポータルサイトを通じてアプリにアクセスする方法:

1. [ **スタート] メニュー** を開き、[ **Microsoft Store**] を選択します。
2. **ポータルサイト** を検索し、アプリをダウンロードします。
3. アカウントにサインインします。
4. 受信してダウンロードするアプリを選択します。

> [!Tip]
> [ポータルサイトの自動インストール](https://docs.microsoft.com/mem/intune/apps/company-portal-app)と[Intune でのアプリの展開と管理の](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)詳細については、こちらを参照してください。
