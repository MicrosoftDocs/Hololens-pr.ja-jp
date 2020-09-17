---
title: Intune と会社のポータル
description: intune、アプリ管理、アプリ、会社ポータル、ポータル
keywords: intune、アプリ管理、アプリ、会社ポータル、ポータル、hololens
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
ms.openlocfilehash: 55e2b15808e52bb80e8114e215bc0cef52358842
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016670"
---
# Intune と会社のポータル

モバイルデバイス管理 (MDM) を使用すると、 [Microsoft エンドポイントマネージャー (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) を介して独自のカスタムアプリを使って、直接 HoloLens デバイスに展開できます。 Microsoft Intune は、モバイルデバイス管理 (MDM) およびモバイルアプリケーション管理 (MAM) に重点を置いたクラウドベースのサービスです。 Intune は Microsoft[Enterprise Mobility + Security (EMS) スイート](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)に含まれており、組織のデータを保護したまま、ユーザーが生産性を高めることができます。 Intune の詳細については、「 [intune とは](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)」を参照してください。

## セットアップ

1. アプリを基幹業務にアップロードするか、カスタムアプリを Intune テナントにアップロードします。 「 [エンタープライズアプリの管理](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)」もご覧ください。

2. [アプリをグループに割り当て](https://docs.microsoft.com/mem/intune/apps/apps-deploy)ます。 選択した課題の種類に基づいて、アプリが自動的に配信されるようにするか、アプリが選択されている場合は、すぐに表示されるようにすることができます。 

> [!NOTE] 
> Appx バンドルを構築するときは、展開先のデバイスのアーキテクチャを含める必要があることを確認してください。 HoloLens 2 は ARM64、HoloLens (第1世代) は x86 です。 混合デバイス環境を計画している場合は、両方を1つの appx バンドルに含めることができます。

## 課題の種類

アプリを登録後、デバイスに自動的にインストールされるようにする場合は、そのグループに対して [ **必須** ] を選択する必要があります。
会社のポータルを通じて登録されたアプリにアプリをダウンロードできるようにするには、[登録されている **デバイスで利用可能**] を選択します。


## エンドユーザーエクスペリエンス

Intune で構成を設定した後、エンドユーザーは選んだアプリを受け取ることができます。

自動的にアプリを取得するには、次の手順を実行します。
1. テナントにデバイスを登録します。 
2. デバイスの登録が完了したら、デバイスでアプリを受け取る必要があります。 
3. アプリがすぐに表示されない場合は、[アカウント情報] の [アカウントの**設定**] に移動  >  **Accounts**  >  **Work or School**  >  **youraccount**し、下にスクロールして、インストールされているアプリの状態に関する情報を確認します。

会社のポータルからアプリにアクセスする方法を教えてください。
1. [ **スタート] メニュー** を開き、[ **Microsoft Store**] を選択します。 
2. 会社の **ポータル** を検索して、アプリをダウンロードします。
3. アカウントにサインインします。
4. 受け取りたいアプリを選択してダウンロードします。

> [!Tip]
> [会社のポータルの自動インストール](https://docs.microsoft.com/mem/intune/apps/company-portal-app)と、 [Intune でのアプリの展開と管理](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)の詳細については、こちらを参照してください。
