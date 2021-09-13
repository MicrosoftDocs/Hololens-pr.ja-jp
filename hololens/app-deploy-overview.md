---
title: 概要-アプリ管理
description: モバイルデバイス管理、ビジネス向け Microsoft ストア、およびプロビジョニングパッケージを使用した mixed reality アプリ管理の概要について説明します。
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033060"
---
# <a name="app-management-overview"></a>アプリ管理: 概要

アプリは、**モバイルデバイス管理 (MDM)**、**ビジネス向け Microsoft Store**、 **Microsoft Store** の4つのパスにデプロイすることも、**プロビジョニング** によってインストールすることもできます。

## <a name="mobile-device-management-mdm"></a>モバイル デバイス管理 (MDM)

MDM ソリューションを使用すると、IT の意思決定者および管理者は、社内の基幹業務アプリをプライベートに自動インストール (プッシュ) したり、ストアを介してユーザーのグループに対してアプリを購入したりすることができます。 HoloLens デバイスは、[アプリケーション管理](app-deploy-intune.md)のために Microsoft エンドポイントマネージャー (Intune) で最適に動作します。 また、Intune では、ポータルサイトダウンロード可能なエクスペリエンスを通じて、IT 管理対象アプリをよりきめ細かく制御できます。

> [!NOTE]
> 次の手順は、Intune を使用してアプリケーションを管理するユーザーを対象としています。 Microsoft では、アプリケーションとデバイスの管理に Intune を使用することをお勧めします。

モバイルデバイス管理 (MDM) は、次の場合に適用されます。

* MDM の展開 + ポータルサイト
* 基幹業務 (非パブリック) アプリ
* ポータルサイトによる使用可能なアプリケーションの手動インストール
* 管理者が MDM ポリシーを使用してプッシュする
* MDM を使用した自動更新

## <a name="microsoft-store-for-business"></a>ビジネス向け Microsoft Store

[ビジネス向け Microsoft Store](app-deploy-store-business.md)により、IT の意思決定者と企業の管理者は、無料および有料のアプリを検索、取得、管理、配布することができます。 IT 管理者は、1つのインベントリで Microsoft Store アプリとプライベート基幹業務アプリを管理し、必要に応じてライセンスを割り当てて再利用することができます。 詳細については、「[ビジネス向け Microsoft Store を使用するための前提条件](/microsoft-store/prerequisites-microsoft-store-for-business)」を参照してください。

ビジネス向け Microsoft Store は、次の場合に適用されます。

* パブリックまたは基幹業務アプリ
* MDM アソシエーションを使用した必要なアプリケーションの自動インストール
* ユーザーによるアプリの手動ダウンロード
* 自動更新

## <a name="microsoft-store-apps"></a>Microsoft Store アプリ

Microsoft Store は、企業の IT 意思決定者および管理者が、パブリックアプリの検索、取得、管理、配布を行います。

この Microsoft Store は、次の場合に適用されます。

* パブリックアプリのみ
* ユーザーによるアプリの手動ダウンロード
* インターネットに接続されている場合は自動更新

詳細については、 [Holographic ストアアプリ](/hololens/holographic-store-apps)に関するページを参照してください。

## <a name="install-via-provisioning-packages"></a>プロビジョニングパッケージを使用してインストールする

[プロビジョニングパッケージ](app-deploy-provisioning-package.md) を使用すると、カスタムまたは基幹業務アプリをインストールできます。これにより、IT 担当者および管理者は、USB を使用してローカルデバイスにアプリをすばやくインストールできます。 このインストールは、インターネットに接続せずに、任意の id の種類に対して行うことができます。

プロビジョニングパッケージを使用したのインストールは、次の場合に適用されます。

* 基幹業務/自己開発 (非パブリック) アプリ
* パブリックアプリ (オフラインインストーラーが使用可能な場合)
* USB サイドローディングのみ
* 自動更新なし (プロビジョニングパッケージを使用した手動更新が必要)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>アプリインストーラーを使用して HoloLens 2 にアプリをインストールする

アプリの[インストーラー](app-deploy-app-installer.md)を使用すると、ローカルデバイスにアプリをインストールしたり、HoloLens で他のアプリのインストール方法に慣れていない他のユーザーとアプリを共有したりすることができます。 これを行うには、開発者モードを有効にしたり、デバイスポータルを使用したりする必要はありません。 これは、完全にビルドされたアプリを配布するための簡単な方法です。 HoloLens を使用してアプリを別のユーザーにデモするだけの場合や、アプリを展開する場合は、この方法が簡単に機能します。

アプリインストーラーを使用したのインストールは、次の場合に適用されます。

* 基幹業務/自己開発 (非パブリック) アプリ
* サイドロードのみ
* 開発者モードまたはデバイスポータルは必要ありません
* エンドユーザーが簡単にインストール
