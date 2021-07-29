---
title: 状態の分割と分離
description: HoloLens 2 Mixed Reality デバイスでの状態の分割、分離、コード署名、Defender アプリケーションについて説明します。
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
ms.openlocfilehash: 0487ea49c706c753f4dfca7da7daa499d1715e9f
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639796"
---
# <a name="state-separation-and-isolation"></a>状態の分割と分離

状態の分割と分離によって、オペレーティング システムを信頼できる状態で起動するために必要な部分など、HoloLens 2 オペレーティング システムの重要部分が変わらないように保護します。 分離テクノロジを使用すると、信頼できないアプリを隔離されたサンドボックス環境に移動し、システムのセキュリティに影響しないようにすることができます。

## <a name="state-separation"></a>状態の分割

HoloLens 2 の状態の分割によって、セキュリティと保守性は大幅に改良され (更新中)、アプリケーションのデータが保護されます。  状態の分割の機能は次のとおりです。
  * コア オペレーティング システムは、コア オペレーティング システム ボリュームに格納されています (信頼済みまたは検証済みの Microsoft OS によってオペレーティング システムが更新されています)。
  * 実行時に変更できるオペレーティング システムの部分 (ダウンロード可能なドライバーや構成など) は、さらに状態の分割を使用してデータを分割し、セキュリティで保護された別の格納場所に格納します。
  * セキュリティで保護された各保存場所には、個別のセキュリティ ポリシーが関連付けられているおり、次のセクションで説明するように、さまざまなセキュリティ上の利点があります。

## <a name="state-separation-benefits"></a>状態の分割の利点

  * セキュリティ: HoloLens 2 の特長である状態の分割により、プラットフォームの整合性、マルウェアへの耐性、ユーザー データの保護が大幅に向上します。 状態の分割によってオペレーティング システムの変更できない部分が分割され、読み取り専用にされるか、整合性が保護されるので、コールド リブート後にマルウェアが存続することは非常に困難になります。 
  * 更新: HoloLens 2 では、コア オペレーティング システムが変更不可能になり、デバイス上の他のデータと完全に分割されたので、更新がシンプルかつ信頼性の高いものになります。  さらに、状態の分割により、更新プログラムを劇的に早くするための非常に重要な基礎作りが行われるため、1 回の操作 (アトミック単位) でオペレーティング システムを置き換えることができます。
  * デバイスのリセット: HoloLens 2 のリセットにより、ユーザーが生成したデータおよびデバイス上のユーザー アプリのデータ (内部と外部の保存場所を含む) がクリアされます。 現在の OS アプリとセキュリティ上重要なアプリ、および現在の Microsoft と OEM のカスタマイズ済みアプリ (プリインストールされたアプリ) は保持されます。 プリインストールされたアプリはリセットの完了後にデバイス上で復元できます

### <a name="state-separation-states"></a>状態の分割の状態

状態の分離により、Microsoft の信頼できるデバイス コンポーネントによってのみ オペレーティング システムを変更できます。また、重要な状態のみが再起動後も存続できます。他のシステム状態はブート セッションの間のみ存在し、再起動後は破棄されます。 状態の分離を使用すると、デバイスをすぐに工場出荷時の状態に戻すことができます。 Windows Holographic for Business の状態は、次のような異なるカテゴリに分割されます。
  * コア オペレーティング システム - 変更不可能な状態
  * オペレーティング システム データ - 変更可能な状態 
  * ユーザー データ - 変更可能な状態

HoloLens 2 のこれらの動作状態については、次のセクションで説明します。

#### <a name="core-operating-system"></a>コア オペレーティング システム

変更不可能な状態は、実行可能ファイルと変更できないデータで構成され、更新プログラムのインストール中に Microsoft のみが変更できます。 このようなコア オペレーティング システムの更新中は、最新のオペレーティングの状態を含む新しいイメージが有効になります。
変更不可能な状態は、読み取り専用とマークされ (または整合性が保護され)、管理者特権を使用するマルウェアの存続を防ぎます。 変更不可能な状態では、次の実行可能ファイルとデータが保護されます。
  * Windows Holographic インボックス ドライバー
  * オペレーティング システムのバイナリ
  * Windows インボックス ドライバー
  * Windows レジストリ ハイブ (HKLM) に格納されている静的な Windows Holographic の設定
    * 例: HKLM には、コンピューターにインストールされているアプリの構成情報が格納されています。 また、ハードウェアと対応するドライバーを検出するための情報も格納されています。
これらを変更不可能な (読み取り専用で整合性が保護されている) 状態で保護することで、コア オペレーティング システムは常に信頼された状態で起動します。 また、デバイスがリセットされた場合、そのデバイスはこの変更不可能なセクション上にあるコンポーネントでのみ起動します。 

#### <a name="operating-system-data"></a>オペレーティング システム データ 

実行時に変更可能な実行可能ファイルとデータ (およびオペレーティング システム機能にとって重要ではないもの) は、データが破損した場合や侵害された場合に、破棄して再作成できることに注意する必要があります。 重要な変更可能な状態とは、オペレーティング システムによって存続することが機能的に要求されているか、オペレーティング システムのシャットダウンやサポートされている Windows オペレーティング システムとデバイスのシナリオによる再起動を経ても存続することが期待される状態です。 重要な変更可能な状態の例を次に示します。
  * すべてのユーザーを対象に場所を無効にするなどの IT 管理者構成のグローバル デバイス設定。
  * Wi-Fi ネットワーク接続のアクセス データデバイスに記憶されたネットワークとそれに関連する接続パスワード。
  * 設定、ログを含むクラッシュ ダンプ。
  * 新しく検出されたデバイスのために必要に応じてダウンロードされるドライバー。
HoloLens 2 の重要な変更可能な状態は、オペレーティング システム データ セキュリティの保管場所の、ディスク内または保存済みのレジストリ ハイブ内にファイルとして保存されます。

#### <a name="user-data"></a>ユーザー データ

状態の最後のカテゴリは、UWP アプリケーションまたはオペレーティング システムによって作成または保存されたユーザー データを表します。 また、ダウンロード、ドキュメント、ビデオ、ユーザー プロファイル、HKEY_CURRENT_USER ハイブなどのすべての既知のユーザー フォルダーもこの場所に格納されます。 このデータを抽出するには、適切な資格情報が必要です。データの保護方法の詳細については、「[データ保護と暗号化](security-encryption-data-protection.md)」を参照してください。

##  <a name="isolation"></a>分離:

このバランスを実現するために、HoloLens 2 には、起動、ハードウェア制御、ログインなどの主要機能に使用されるコア オペレーティング システムが搭載されています。コア オペレーティング システム上で動作するアプリケーションは、プリインストールされたアプリケーションと UWP アプリの 2 種類のみです。

## <a name="code-signing"></a>コード署名

デジタル署名コードを使用すると、実行可能ファイルとスクリプトが信頼できるソースによって署名された後に変更されていないことを実証できるので、真正性と完全性が確保されます。 HoloLens 2 は、Microsoft および Microsoft ストアの 2 つの機関を信頼しています。 IT 管理者は [ClientCertificateInstall](/windows/client-management/mdm/clientcertificateinstall-csp) および [RootCATrustedCertificates](/windows/client-management/mdm/rootcacertificates-csp) CSP から新しい証明書をデバイスに追加できます。 また、[AllowAllTrustedApps ポリシー](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)を、信頼する追加のサイドロードや[基幹業務アプリ](/intune/apps/lob-apps-windows)に使用できます。 証明書はローカル コンピューターの証明書ストアにあり、"Device" を使用している場合は HKLM/Root に格納されます。"User" を使用している場合は HKCU に格納されます。

## <a name="defender-protections"></a>Defender の保護
HoloLens 2 では、Microsoft サービスを使用して最新水準のセキュリティを提供しています。

* [Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) は、OS によって Windows Holographic で自動的に有効になり、Microsoft Edge でのフィッシング詐欺やマルウェア、悪意がある可能性があるファイルのダウンロードに対して保護を実行します。 ユーザーがこれを無効にすることはできませんが、ポリシーを使用して無効にすることができます。

* [Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) を使用すると、承認されていないネットワーク トラフィックがデバイスへ、またはデバイスから送信されるのを防ぐことができます。 この機能は既定で有効になっています。ローカルのアクションやポリシーを使って顧客が構成することはできません。 

* [Windows Defender アプリケーション制御](/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview): HoloLens 2 は WDAC をサポートしているため、IT 管理者はアプリケーション制御ポリシーをデバイスにプッシュすることができます。 詳細については、[MSFT Intune を使用して HoloLens 2 デバイス上で WDAC を使用する](/mem/intune/configuration/custom-profile-hololens)方法に関するページを参照してください。 

IT 管理者は、[AllowSmartScreen](/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) を使用して SmartScreen の動作を管理し、[これらのポリシー](/windows/client-management/mdm/policy-csps-supported-by-hololens2)を使用してブラウザーの動作を管理することができます。 

