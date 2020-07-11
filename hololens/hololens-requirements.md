---
title: 商用環境で HoloLens をセットアップする
description: エンタープライズ環境での HoloLens の展開と管理の詳細については、こちらを参照してください。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.openlocfilehash: e53e6575ef688e01ce2d1f6124f3214b18b05c95
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865566"
---
# 商用環境での HoloLens の展開

企業向けの設定では、HoloLens をスケールで展開して構成することができます。 この記事では、商用環境で HoloLens デバイスを展開するための手順について説明します。 このガイドでは、HoloLens の基本的な知識を前提としています。 「[はじめに」のガイド](hololens1-setup.md)に従って、初めて HoloLens をセットアップします。

また、このドキュメントでは、企業ネットワークでの使用に関しては、HoloLens がセキュリティチームによって評価されていることを前提としています。  
> [!Tip]
> [HoloLens のセキュリティ](security-overview.md)についての詳細はこちらをご覧ください。
> HoloLens (第1世代) セキュリティについては、[この FAQ](hololens1-faq-security.md)を確認してください。

## 展開手順の概要

1. [必要な機能を決定する](hololens-requirements.md#step-1-determine-what-you-need)
1. [必要なライセンスを決定する](hololens-licenses-requirements.md)
1. [HoloLens 用にネットワークを構成](hololens-commercial-infrastructure.md)します。
    1. このセクションでは、ファイアウォールで許可する必要がある帯域幅の要件、URL、ポートについて説明します。Azure AD ガイダンス;モバイルデバイス管理 (MDM) のガイダンスアプリの展開と管理のガイダンス証明書のガイダンス。
1. 省略[プロビジョニングパッケージを使用して HoloLens を構成](hololens-provisioning.md)する
1. [デバイスを登録する](hololens-enroll-mdm.md)
1. [HoloLens のリング ベースの更新プログラムをセットアップする](hololens-updates.md)
1. [HoloLens の Bitlocker デバイスの暗号化を有効にする](security-encryption-data-protection.md)

## 手順 1.  必要なものを決定する

お客様の環境に HoloLens を展開する前に、まず必要な機能、アプリ、および種類を特定することが重要です。 また、セキュリティチームが会社のネットワークで HoloLens の使用を承認していることを確認することも重要です。 追加のセキュリティ情報については、「 [HoloLens2 のセキュリティ](security-overview.md)」を参照してください。

### Id の種類

デバイスへのサインインに使用される id の種類を決定します。

1. **ローカルアカウント:** このアカウントは、デバイスに対してローカル (windows PC のローカル管理者アカウントなど) になります。 これにより、1ユーザーだけがデバイスにログインできるようになります。
2. **MSA:** これは個人アカウント (outlook、hotmail、gmail、yahoo など) です。これにより、1ユーザーだけがデバイスにログインできるようになります。
3. **Azure Active Directory (AZURE AD) アカウント:** これは、Azure AD で作成されたアカウントです。 これにより、企業は HoloLens デバイスを管理できるようになります。 これにより、複数のユーザーが HoloLens 第1世代の商用スイート/HoloLens 2 デバイスにログインできるようになります。

Id 型の詳細については、HoloLens の[id](hololens-identity.md)の記事を参照してください。

### 機能の種類

お客様の機能要件によって、必要な HoloLens が決定されます。 顧客の環境に展開されることが多い一般的な機能の1つに、キオスクモードがあります。 HoloLens の主要機能と、それらをサポートする HoloLens のエディションの一覧については、[こちら](hololens-commercial-features.md)を参照してください。

**キオスクモードとは**

キオスクモードは、ユーザーがアクセスできるアプリを制限するための手段です。 これは、ユーザーが特定のアプリにしかアクセスできないことを意味します。

**どのキオスクモードが必要ですか?**

キオスクモードには、単一アプリとマルチアプリの2種類があります。 1つのアプリのキオスクモードでは、ユーザーは1つのアプリにしかアクセスできません。マルチアプリのキオスクモードでは、複数の指定したアプリにアクセスできます。 お客様の会社に適したキオスクモードを決定するには、次の2つの質問に回答する必要があります。

1. **さまざまなユーザーがさまざまなエクスペリエンスと制限を必要とするかどうか** 次の例を参考にしてください。ユーザー A は、リモートアシストへのアクセスのみを必要とするフィールドサービスエンジニアです。 ユーザー B は、ガイドへのアクセスのみを必要とする研修者です。
    1. [はい] の場合は、次のものが必要になります。
        1. Azure AD アカウントを、デバイスへのサインイン方法として使うことができます。
        1. **マルチアプリ**キオスクモード。
    1. 「いいえ」の場合は、引き続き質問2
1. **複数のアプリでのエクスペリエンスが必要ですか?**
    1. [はい] の場合は、**マルチアプリ**のキオスクがモードである必要があります
    1. 質問1と2の答えが両方ともいいえの場合、**単一アプリ**のキオスクモードを使用できます。

**キオスクモードを構成する方法:**

HoloLens 用のキオスクモードを展開するには、主に2つの方法 ([プロビジョニングパッケージ](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)と[MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) があります。 これらのオプションについては、このドキュメントの後半で説明します。ただし、上記のリンクを使用して、このドキュメントの該当するセクションに移動することはできます。

### アプリとアプリ固有のシナリオ

このドキュメントに記載されている手順の大半は、次のアプリにも適用されます。

| アプリ | アプリ固有のシナリオ |
| --- | --- |
| リモートアシスト | [クロステナント通信](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview)|
| ガイド  | *もうすぐです* |
|カスタムアプリ | *もうすぐです* |

### 登録方法を決定する

1. プロビジョニングパッケージのセキュリティトークンを使った一括登録。  
  長所: これが最も自動化された方法です。
  短所: サーバー側の初期セットアップを行います。  
1. ユーザーのサインイン時に自動登録を行います。  
  長所: 最も簡単な方法  
  欠点: プロビジョニングパッケージが適用された後、ユーザーはセットアップを完了する必要があります。
1. _推奨しません_-セットアップ後に手動で登録してください。  
  長所: セットアップ後に登録できる  
  欠点: 手動のアプローチとデバイスは、手動で登録しない限り、一元管理することはできません。

  詳細については、こちらを参照して[ください](hololens-enroll-mdm.md)

### プロビジョニングパッケージを作成する必要があるかどうかを確認する

HoloLens デバイス (プロビジョニングパッケージと MDMs) を構成するには、2つの方法があります。 HoloLens デバイスの構成には MDM を使用することをお勧めします。 ただし、プロビジョニングパッケージの使用が適しているシナリオはいくつかあります。

1. 不在時のエクスペリエンス (OOBE) をスキップするように HoloLens を構成する必要がある場合
1. 複雑なネットワークでの証明書の展開で問題が発生しています。 多くの場合、MDM (複雑な環境でも) を使って証明書を展開できます。 ただし、一部のシナリオでは、プロビジョニングパッケージを使用して証明書を展開する必要があります。

プロビジョニング パッケージで適用できる HoloLens 構成の例は次のとおりです。

- 証明書をデバイスに適用する
- Wi-Fi 接続をセットアップする
- 言語やロケールなどのすぐに使える質問を事前構成する
- (HoloLens 2) モバイル デバイス管理への一括登録をする
- (HoloLens v1) キーを適用して Windows Holographic for Business を有効にする

プロビジョニングパッケージを使用する場合は、[このガイド](hololens-provisioning.md)に従ってください。

## サポートを受ける

Microsoft サポートサイトでサポートを利用します。

[サポートリクエストをファイルに保存する](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f)
