---
title: 状態の分割と分離
description: HoloLens 2 Mixed Reality デバイスでの状態の分割、分離、コード署名、およびディフェンダー アプリケーションについて説明します。
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: セキュリティ、HoloLens、状態の分割、状態の分割と分離、HoloLens 2、HoloLens 2 セキュリティ、セキュリティの概要、セキュリティ アーキテクチャ、アーキテクチャ、HoloLens 2 アーキテクチャ
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 60d6d7c0e281395957ce9158144a5f3d60927682
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11282808"
---
# 状態の分割と分離

状態の分割と分離は、オペレーティング システムを信頼できる状態で起動するために必要な部分など、HoloLens 2 オペレーティング システムの重要部分が変わらないように保護します。 分離技術を使用して、信頼できないアプリは、システム セキュリティに影響しないように、分離されたサンド ボックス環境に移動されます。

## 状態の分割

HoloLens 2 の状態の分割によって、セキュリティと保守性は大幅に改良され (更新中)、アプリケーションのデータを保護します。  状態の分割の機能は次のとおりです。
  * コア オペレーティング システムは、コア オペレーティング システム ボリュームに保存されています (信頼できるまたは確認済みの Microsoft OS がオペレーティング システムを更新しています)。
  * 実行時に変更できるオペレーティング システムの部分 (ダウンロード可能なドライバーや構成など) は、さらに状態の分割を使用してデータを分割し、安全な別の保存場所に格納します。
  * セキュリティで保護された各保存場所には、個別のセキュリティ ポリシーが関連付けられることで、さまざまなセキュリティ上の利点があります。次のセクションで詳細に説明します。

## 状態の分割の利点

  * セキュリティ: HoloLens 2 で使用される状態の分割は、プラットフォームの整合性、マルウェアへの耐性、ユーザー データ保護を大幅に改善させます。 状態の分割がオペレーティング システムの変更できない部分を分割して、読み取り専用にするか整合性の保護を行うことで、マルウェアが再起動後に状態を維持するのは非常に難しくなります。 
  * 更新: HoloLens 2 では、コア オペレーティング システムが変更できない状態になり、デバイス上の残りのデータから完全に分割されると、更新がシンプルかつ信頼性の高いものになります。  さらに、状態の分割は、更新プログラムを劇的に早くするための非常に重要な基礎作りをするため、1 回の操作 (atomic 単位) でオペレーティング システムを置き換えることができます。
  * デバイスのリセット: HoloLens 2 リセットは、ユーザーが生成したデータおよびデバイス上のユーザー アプリのデータ (内部および外部の保存場所を含む) をクリアします。 現在の OS アプリとセキュリティ上重要なアプリ、および現在の Microsoft と OEM のカスタマイズ済みアプリ (プレインストール済みアプリ) は保持されます。 プリインストールされたアプリはリセットの完了後にデバイス上で復元できます

### 状態の分割の状態

状態の分割では、Microsoft の信頼済みデバイス コンポーネントだけがオペレーティングシ ステムを変更できます。また、重要な状態だけが再起動後に状態を維持することを許可されます。その他のシステム状態は、ブート セッション中にのみ存在し、再起動後に破棄されます。 状態の分割を使用すれば、デバイスをすぐに Factory の状態に戻すことができます。 Windows Holographic for Business の状態は、次のような異なるカテゴリーに分割されます。
  * コア オペレーティング システム – 変更できない状態
  * オペレーティング システム データ – 変更できる状態 
  * ユーザー データ – 変更できる状態

HoloLens 2 のこれらのオペレーティングの状態については、次のセクションで説明します。

#### コア オペレーティング システム

変更できない状態は、実行可能ファイルと変更できないデータで構成され、更新プログラムのインストール中に Microsoft のみが変更できます。 このようなコア オペレーティング システムの更新中は、最新のオペレーティングの状態を含む新しい画像が有効になります。
変更できない状態は、読み取り専用に設定されているか、整合性が保護され、システム特権によるマルウェアの持続性を防いでいます。 変更できない状態では、次の実行可能ファイルとデータが保護されます。
  * Windows Holographic 受信トレイのドライバー
  * オペレーティング システム バイナリ
  * Windows 受信トレイのドライバー
  * Windows レジストリ ハイブ (HKLM) に保存されている Static Windows Holographic の設定
    * 例: HKLM には、コンピューターにインストールされているアプリの構成情報が保存されます。 また、ハードウェアと対応するドライバーを検出するための情報も保存されます。
これらを変更できない (読み取り専用で整合性が保護されている) 状態で保護することで、コア オペレーティング システムは常に信頼された状態で起動します。 また、デバイスがリセットされた場合、そのデバイスはこの変更できないセクションのコンポーネントでのみ起動します。 

#### オペレーティング システム データ 

実行時に変更できる実行可能ファイルとデータ (およびオペレーティング システム機能にとって重要ではないデータ) は、データが破損しているときやセキュリティ侵害を受けたときに破棄、再作成できることに注意する必要があります。 重要な変更できる状態は、オペレーティング システムによって機能的に保持されるか、オペレーティング システムのシャットダウン中に保持されるか、または、およびサポートされている Windows オペレーティング システムとデバイスのシナリオによって再起動中に保持される必要があります。 重要な変更可能な状態の例を次に示します。
  * すべてのユーザーを対象に場所を無効にするなどの IT 管理者構成のグローバル デバイス設定。
  * Wi-Fi ネットワーク接続アクセスの記憶されたデータ デバイスのネットワークと関連付けられた接続パスワード。
  * 設定、ログを含むクラッシュ ダンプ。
  * 新しく検出されたデバイスのために必要に応じてダウンロードされるドライバー。
HoloLens 2 の重要な変更できる状態は、オペレーティング システム データ セキュリティの保管場所の、ディスク内または保存済みのレジストリ ハイブ内にファイルとして保存されます。

#### ユーザー データ

状態の最後のカテゴリは、UWP アプリケーションまたはオペレーティング システムによって作成または保存されたユーザー データを表します。 また、ダウンロード、ドキュメント、ビデオ、ユーザー プロファイル、HKEY_CURRENT_USER ハイブなどのすべての既知のユーザー フォルダーもこの場所に保存されます。 このデータの抽出には、適切な資格情報が必要です。データ保護の詳細については、「[暗号化とデータ保護](security-encryption-data-protection.md)」 を参照してください。

##  分離

バランスを取るために、HoloLens 2 には、起動、ハードウェアの制御、ログインなどの主な機能に使用されるコア オペレーティング システムが用意されています。コア オペレーティング システムで実行するアプリケーションには、プリインストールされたアプリケーションと UWP アプリの 2 つがあります。

## コード署名

デジタル署名のコードは、実行可能ファイルとスクリプトが信頼できる発行元によって署名され、変更されていないため、信頼性と整合性を確保できることを実証します。 HoloLens 2 は、Microsoft および Microsoft ストアの 2 つの機関を信頼しています。 IT 管理者は [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) および [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) CSP から、新しい証明書をデバイスに追加できます。 また、[AllowAllTrustedApps ポリシー](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) を、信頼する追加のサイドロードや [基幹業務アプリ](https://docs.microsoft.com/intune/apps/lob-apps-windows) に使用できます。 証明書はローカル コンピューターの証明書ストアにあり、"Device" を使用している場合は HKLM/Root に格納されます。 "User" を使用している場合は HKCU に格納されます。

## Defender の保護
HoloLens 2 は、Microsoft サービスを使用して最新水準のセキュリティを提供します。

* [Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) は、OS によって Windows Holographic で自動的に有効になり、 Microsoft Edge でのフィッシング詐欺やマルウェア、悪意がある可能性があるファイルのダウンロードに対して保護を実行します。 ユーザーは無効にできませんが、ポリシーを使用して無効にすることができます。

* [Defender ファイアウォール](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) は、承認されていないネットワーク トラフィックがデバイスへ、またはデバイスから送信されるのを防ぎます。 この機能は既定で有効になっています。ローカルのアクションやポリシーを使って顧客が構成できません。 

* [Windows Defender アプリケーション制御](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview):  HoloLens 2 は WDAC をサポートし、IT 管理者はアプリケーション制御ポリシーをデバイスにプッシュできるようになります。 詳細については、[MSFT Intune を使用して HoloLens 2 デバイスで WDAC を使用する](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)参照ください。 

IT 管理者は、[AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) を使って SmartScreen の動作を管理でき、[これらのポリシー](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)を使ってブラウザーの動作を管理できます。 

