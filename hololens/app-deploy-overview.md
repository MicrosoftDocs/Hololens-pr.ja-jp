---
title: 概要 - アプリ管理
description: 概要デバイス管理、ビジネス向け Microsoft ストア、およびプロビジョニング パッケージを使用した Mixed Reality アプリ管理の概要について説明します。
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
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635553"
---
# <a name="app-management-overview"></a>アプリ管理: 概要

アプリは **、Mobile デバイス管理 (MDM)** **、ビジネス向け Microsoft Store** **、Microsoft Store** の 4 つの異なるパスにデプロイできます。または、プロビジョニング を使用してアプリを **インストールします**。

## <a name="mobile-device-management-mdm"></a>モバイル デバイス管理 (MDM)

MDM ソリューションを使用すると、IT の意思決定者と管理者は、企業内の業務アプリを非公開で自動インストール (プッシュ) したり、ユーザー グループのストアを通じてアプリを購入したりすることができます。 HoloLensデバイスは、アプリケーション管理のために Microsoft エンドポイント マネージャー (Intune) で最適[に動作します](app-deploy-intune.md)。 Intune では、ダウンロード可能なエクスペリエンスを通じて、IT で管理されたアプリをユーザーポータル サイト制御することもできます。

> [!NOTE]
> 次の手順は、Intune でアプリケーションを管理するユーザー向けです。 Microsoft では、アプリケーションとデバイスの管理に Intune を使用する方法をお勧めします。

モバイル デバイス管理 (MDM) は次の場合に適用されます。

* MDM のデプロイ + ポータル サイト
* Line of Business (非パブリック) アプリ
* アプリケーションを使用して使用可能なアプリケーションを手動ポータル サイト
* MDM ポリシーによる管理者プッシュ
* MDM による自動更新

## <a name="microsoft-store-for-business"></a>ビジネス向け Microsoft Store

この[ビジネス向け Microsoft Store、IT](app-deploy-store-business.md)の意思決定者と企業の管理者が、無料アプリと有料アプリを検索、取得、管理、配布できます。 IT 管理者は、1 Microsoft Storeアプリとプライベートの業務アプリを 1 つのインベントリで管理し、必要に応じてライセンスを割り当て、再利用することができます。 詳細については、「 を使用するための[前提条件」を参照ビジネス向け Microsoft Store。](/microsoft-store/prerequisites-microsoft-store-for-business)

このビジネス向け Microsoft Storeは次の場合に適用されます。

* パブリック アプリまたは Line of Business アプリ
* MDM 関連付けを使用した必要なアプリケーションの自動インストール
* ユーザーがアプリを手動でダウンロードする
* 自動更新

## <a name="microsoft-store-apps"></a>Microsoft Store アプリ

このMicrosoft Store、IT の意思決定者と企業の管理者が、パブリック アプリの検索、取得、管理、配布を行います。

このMicrosoft Storeは次の場合に適用されます。

* パブリック アプリのみ
* ユーザーがアプリを手動でダウンロードする
* インターネットに接続されている場合の自動更新

詳細については [、「Holographic Store Apps 」を参照してください](/hololens/holographic-store-apps)。

## <a name="install-via-provisioning-packages"></a>プロビジョニング パッケージを使用してインストールする

[プロビジョニング パッケージを](app-deploy-provisioning-package.md) 使用すると、カスタムアプリまたは Line of Business アプリをインストールできます。IT のプロや管理者は、USB 経由でローカル デバイスにアプリをすばやくインストールできます。 このインストールは、インターネットに接続せずに、任意の ID の種類に対して実行できます。

プロビジョニング パッケージを使用したインストールは、次の場合に適用されます。

* Line of Business / 自己開発 (非パブリック) アプリ
* パブリック アプリ (オフライン インストーラーが使用可能な場合)
* USB サイドローディングのみ
* 自動更新なし (プロビジョニング パッケージを使用した手動更新が必要)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>HoloLens 2 経由でアプリを アプリ インストーラー

[アプリ インストーラー](app-deploy-app-installer.md)ユーザーは、ローカル デバイスにアプリをインストールしたり、HoloLens で他のアプリのインストール方法に慣れていない他のユーザーとアプリを共有したりする簡単なエクスペリエンスを利用できます。 これは、開発者モードを有効にしたり、開発者モードを使用したりすることなくデバイス ポータル。 これは、完全に構築されたアプリを配布する簡単な方法です。 HoloLens を使用してアプリを別のユーザーにデモする場合や、アプリをデプロイする場合は、この方法が簡単に機能します。

次のアプリ インストーラーを使用してインストールできます。

* Line of Business / Self developed (非パブリック) アプリ
* サイドロードのみ
* 開発者モードまたはデバイス ポータルは必要ない
* エンド ユーザーが簡単にインストールできる
