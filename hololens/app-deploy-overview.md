---
title: 概要 - アプリ管理
description: モバイル デバイス管理、ビジネス向け Microsoft Store、プロビジョニング パッケージを使用した Mixed Reality アプリ管理の概要について説明します。
keywords: HoloLens、ユーザー、アカウント、アプリ、アプリケーション管理、
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283708"
---
# アプリ管理の概要

アプリは、モバイル デバイス管理 **(MDM)、****ビジネス向け Microsoft Store、Microsoft** **Store**の 4 つの異なるパスに展開するか、プロビジョニングを使用してアプリを**インストールすることで展開できます**。

## モバイル デバイス管理 (MDM)

MDM ソリューションを使用すると、IT の意思決定者と管理者は、企業内アプリ、業務アプリをプライベートに自動インストール (プッシュ) したり、ユーザー グループのストアを通じてアプリを購入することができます。 HoloLens デバイスは、Microsoft Endpoint Manager (Intune) を使用してアプリケーション管理を行う場合に最適 [です](app-deploy-intune.md)。 Intune では、ポータル サイトのダウンロード可能なエクスペリエンスを通じて、ユーザーが IT 管理アプリを細かく制御することもできます。

> [!NOTE]
> 次の手順は、Intune でアプリケーションを管理するユーザー向けです。 Microsoft では、アプリケーションとデバイスの管理に Intune を使用する方法をお勧めします。

モバイル デバイス管理 (MDM) は、次の場合に適用されます。

* MDM の展開 + ポータル サイト
* Line of Business (非パブリック) アプリ
* ポータル サイトを使用して利用可能なアプリケーションを手動でインストールする
* 管理者による MDM ポリシーのプッシュ
* MDM による自動更新

## ビジネス向け Microsoft Store

ビジネス [向け Microsoft Store](app-deploy-store-business.md) では、IT の意思決定者と管理者が無料アプリと有料アプリを検索、取得、管理、配布できます。 IT 管理者は、Microsoft Store アプリとプライベートな業務アプリを 1 つのインベントリで管理し、必要に応じてライセンスを割り当て、再利用できます。 詳細については、ビジネス向け [Microsoft Store を使用するための前提条件に関するページを参照してください](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)。

ビジネス向け Microsoft Store は、次の対象に適用されます。

* パブリック アプリまたは Line of Business アプリ
* MDM 関連付けを使用した必要なアプリケーションの自動インストール
* ユーザーがアプリを手動でダウンロードする
* 自動更新

## Microsoft Store アプリ

Microsoft Store では、企業の IT 意思決定者と管理者がパブリック アプリの検索、取得、管理、配布を行います。

この Microsoft Store は、次の対象に適用されます。

* パブリック アプリのみ
* ユーザーがアプリを手動でダウンロードする
* インターネットに接続されている場合の自動更新

詳しくは [、Holographic ストア アプリに関するページをご覧ください](https://docs.microsoft.com/hololens/holographic-store-apps)。

## プロビジョニング パッケージを使用してインストールする

[プロビジョニング パッケージを](app-deploy-provisioning-package.md) 使用すると、カスタム アプリまたは Line of Business アプリをインストールできます。IT 管理者は、USB 経由でローカル デバイスにアプリをすばやくインストールできます。 このインストールは、インターネットに接続せずに、任意の ID の種類に対して実行できます。

プロビジョニング パッケージを使用したインストールは、次の場合に適用されます。

* Line of Business / 自己開発 (非パブリック) アプリ
* パブリック アプリ (オフライン インストーラーが利用可能な場合)
* USB サイドローディングのみ
* 自動更新なし (プロビジョニング パッケージによる手動更新が必要)

## アプリ インストーラーを使用して HoloLens 2 にアプリをインストールする

アプリ[](app-deploy-app-installer.md)インストーラーを使用すると、ローカル デバイスにアプリをインストールしたり、HoloLens 上の他のアプリのインストール方法に慣れていない他のユーザーとアプリを共有したりする操作が簡単になります。 これは、開発者モードを有効にしたり、Device Portal を使用したりすることなく実行できます。 これは、完全に構築されたアプリを配布する簡単な方法です。 HoloLens を使って他のユーザーにアプリをデモする場合や、アプリを展開する場合に関係なく、このメソッドは簡単に機能します。

アプリ インストーラーを使用したインストールは、次の場合に適用されます。

* Line of Business / Self developed (non-public) apps
* サイドロードのみ
* 開発者モードや Device Portal は不要
* エンド ユーザーが簡単にインストールできる
