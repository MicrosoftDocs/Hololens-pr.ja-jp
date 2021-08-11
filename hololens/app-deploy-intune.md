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
ms.openlocfilehash: f1c178c940224ed3cd07c58b886b176108614caf7a8463af089e2f2357f45553
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665252"
---
# <a name="intune--company-portal"></a>Intune & ポータル サイト

モバイルデバイス管理 (MDM) では、 [Microsoft エンドポイントマネージャー (Intune)](/intune/windows-holographic-for-business)を通じて独自のカスタムアプリを使用して、HoloLens デバイスに直接展開することができます。 Microsoft Intune は、モバイル デバイス管理 (MDM) とモバイル アプリケーション管理 (MAM) を中心にしたクラウドベースのサービスです。 Intune は、Microsoft の [Enterprise Mobility + Security (EMS) スイート](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)に含まれており、組織のデータを保護したまま、ユーザーの生産性を高めることができます。 Intune の詳細については、「 [intune とは](/mem/intune/fundamentals/what-is-intune)」を参照してください。

## <a name="setup"></a>セットアップ

1. アプリを基幹業務にアップロード、またはカスタムアプリを Intune テナントにアップロードします。 関連項目: [Enterprise app management](/windows/client-management/mdm/enterprise-app-management)」も参照してください。

2. [アプリをグループに割り当て](/mem/intune/apps/apps-deploy)ます。 選択した割り当ての種類に基づいて、アプリを自動的に配信することも、アプリを選択している場合はすぐに利用できるようにすることもできます。

> [!NOTE]
> Appx バンドルを構築するときは、デプロイ先のデバイスのアーキテクチャを含めるようにしてください。 HoloLens 2 は ARM64 で、HoloLens (第1世代) は x86 です。 混合デバイス環境を使用する場合は、両方を1つの appx バンドルに含めることができます。

## <a name="assignment-types"></a>割り当ての種類

登録後にアプリがデバイスに自動的にインストールされるようにするには、そのグループに対して [ **必須** ] を選択する必要があります。
ポータルサイトで登録されているデバイスにアプリをダウンロードできるようにするには、[ **登録済みデバイスで利用可能**] を選択します。

## <a name="end-user-experience"></a>エンドユーザー エクスペリエンス

Intune で構成を設定した後、エンドユーザーが選択したアプリを受信できるようになります。

アプリを自動的に取得するには、次の手順に従います。

1. テナントにデバイスを登録します。
2. デバイスの登録が完了したら、デバイスでアプリを受信する必要があります。
3. アプリがすぐに表示されない場合は、**設定**  >  **アカウント** の  >  **職場または学校** の  >  *アカウント* 情報に移動し、下にスクロールして、インストールされているアプリの状態に関する情報を確認してください。

ポータルサイトを通じてアプリにアクセスする方法:

1. [**スタート] メニュー** を開き、[ **Microsoft Store**] を選択します。
2. **ポータルサイト** を検索し、アプリをダウンロードします。
3. アカウントにサインインします。
4. 受信してダウンロードするアプリを選択します。

> [!Tip]
> [ポータルサイトの自動インストール](/mem/intune/apps/company-portal-app)と[Intune でのアプリの展開と管理の](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)詳細については、こちらを参照してください。
