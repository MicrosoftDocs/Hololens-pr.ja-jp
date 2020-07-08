---
title: 概要-アプリ管理
description: アプリ、管理、アプリの管理
keywords: HoloLens、ユーザー、アカウント、アプリ、アプリケーション管理、
author: v-jodben
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: eeed478970d08eff8789a9decd084f1863c6d7f9
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857955"
---
# アプリ管理: 概要

アプリを展開するには、**モバイルデバイス管理 (MDM)**、 **Microsoft ストア for Business**、 **Microsoft ストア**、または**プロビジョニング**によるインストールの4つの異なるパスを使用できます。 

## モバイル デバイス管理 (MDM)

MDM ソリューションを使用すると、IT の意思決定者や管理者は、社内、基幹業務のアプリをプライベートに自動インストール (プッシュ) することができます。また、ユーザーのグループに対してストアを通じてアプリを購入することもできます。 HoloLens デバイスは、[アプリケーション管理](app-deploy-intune.md)用の Microsoft Endpoint Manager (Intune) と最適に動作します。 また、ユーザーは、会社のポータルのダウンロード操作を通じて、IT によって管理されたアプリをきめ細かく制御できます。

> [!NOTE] 
> 次の手順は、Intune を使ってアプリケーションを管理するユーザーを対象としています。 アプリケーションとデバイスの管理には Intune を使用することをお勧めします。
    
モバイルデバイス管理 (MDM) は、次の場合に適用されます。 
* MDM の展開と会社のポータル 
* 1行の Buisness (非パブリック) アプリ
* 会社のポータル経由で利用可能なアプリケーションを手動でインストールする
* MDM ポリシーによる管理者プッシュ
* MDM による自動更新

## ビジネス向け Microsoft Store

一般[法人向け Microsoft ストア](app-deploy-store-business.md)では、ビジネスの意思決定者と管理者が、無料および有料のアプリを検索、入手、管理、配布することができます。 IT 管理者は、1 つのインベントリで Microsoft Store アプリとプライベートな基幹業務アプリを管理でき、必要に応じてライセンスの割り当てや再利用を行うことができます。 詳細については、「 [Microsoft Store For Business を使用するための前提条件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)」を参照してください。
    
ビジネス向けの Microsoft ストアは、次の場合に該当します。 
* 一般法人向けまたは基幹業務用のアプリ
* MDM の関連付けによる必須アプリケーションの自動インストール
* ユーザーが手動でアプリをダウンロードする
* 自動更新

## Microsoft Store アプリ

Microsoft Store では、企業の IT 意思決定者と管理者が公開アプリの検索、入手、管理、配布を行うことができます。
    
この Microsoft ストアは、次の目的で使用できます。 
* 公開アプリのみ
* ユーザーが手動でアプリをダウンロードする
* インターネットに接続されている場合に自動更新する

詳細については、「[ホログラフィック Store アプリ](https://docs.microsoft.com/hololens/holographic-store-apps)」を参照してください。

## プロビジョニングパッケージによるインストール

[プロビジョニングパッケージ](app-deploy-provisioning-package.md)では、カスタムまたは基幹業務アプリをインストールできるため、IT 担当者や管理者は、USB 経由でローカルデバイスにアプリをすばやくインストールすることができます。 これは、インターネットに接続しなくても、どのような種類の id でも実行できます。
    
プロビジョニングパッケージによるインストールは、次の場合に適用されます。 
* 1行の Buisness (非パブリック) アプリ
* 公開アプリ (オフラインインストーラーが利用可能な場合)
* USB サイドロードのみ
* 自動更新なし (プロビジョニングパッケージ経由で手動で更新する必要があります)
