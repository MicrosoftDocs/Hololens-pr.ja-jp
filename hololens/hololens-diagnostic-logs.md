---
title: HoloLens デバイスから診断情報を収集して使用する
description: HoloLens デバイスから診断情報を収集、使用、および保持する方法について説明します。
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/15/2020
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.custom:
- CI 115131
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4a360e99a45b855957e36dd6ba31ede3da9631ba
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309724"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>HoloLens デバイスから診断情報を収集して使用する

HoloLens のユーザーと管理者は、HoloLens から診断情報を収集するために、4つの異なる方法から選択できます。

- フィードバックハブアプリ
- DiagnosticLog CSP
- 設定アプリ
- オフライン診断

> [!IMPORTANT]  
> デバイス診断ログには、ユーザーが通常の操作で開始するプロセスやアプリケーションなど、個人を特定できる情報 (PII) が含まれています。 複数のユーザーが HoloLens デバイスを共有している場合 (たとえば、ユーザーが異なる Microsoft Azure Active Directory (Azure AD) アカウントを使用して同じデバイスにサインインした場合)、診断ログには、複数のユーザーに適用される PII 情報が含まれる場合があります。 詳細については、「 [Microsoft のプライバシー](https://privacy.microsoft.com/privacystatement)に関する声明」を参照してください。

次の表は、さまざまな収集方法を比較したものです。 メソッド名は、テーブルに続くセクションの詳細情報にリンクされています。

|メソッド |前提条件 |データの場所 |データアクセスと使用 |データの保持 |
| --- | --- | --- | --- | --- |
|[フィードバック Hub](#feedback-hub) |ネットワークとインターネット接続<br /><br />フィードバックハブアプリ<br /><br />Microsoft クラウドにファイルをアップロードするためのアクセス許可 |Microsoft クラウド<br /><br />HoloLens デバイス (オプション) |ユーザーがアシスタンスを要求し、使用条件に同意して、データをアップロードする<br /><br />Microsoft の従業員が使用条件に従ってデータを表示する |クラウド内のデータは、次世代プライバシー (NGP) で定義されている期間にわたって保持されます。 その後、データは自動的に削除されます。<br /><br />デバイス上のデータは、 **デバイスの所有者** または **管理者** のアクセス許可を持つユーザーがいつでも削除できます。 |
|[設定のトラブルシューティング](#settings-troubleshooter) |設定アプリ |HoloLens デバイス<br /><br />接続されたコンピューター (オプション) |ユーザーはデータを保存し、ユーザーのみがデータにアクセスします (ユーザーが明示的に別のユーザーとデータを共有している場合を除く)。 |データは、ユーザーが削除するまでデバイスに保持されます。 * |
|[DiagnosticLog CSP](#diagnosticlog-csp) |ネットワーク接続<br /><br />DiagnosticLog CSP をサポートする MDM 環境 |管理者がストレージの場所を構成する |管理された環境では、ユーザーはデータへの管理者アクセスを暗黙的に同意ます。<br /><br />管理者は、アクセスの役割とアクセス許可を構成します。 | データはクラウドストレージに保持され、管理者はリテンション期間ポリシーを構成します。 |
|[オフライン診断](#offline-diagnostics) |デバイスの構成:<ul><li>電源が入っていて、コンピューターに接続されている</li><li>電源ボタンと音量ボタンが機能している</li></ul> |HoloLens デバイス<br /><br />接続されたコンピューター |ユーザーはデータを保存し、ユーザーのみがデータにアクセスします (ユーザーが明示的に別のユーザーとデータを共有している場合を除く)。 |データは、ユーザーが削除するまでデバイスに保持されます。 |

- エンドユーザーは、ログを他のユーザーと確実に共有する責任があります。 これらのファイルは、主にカスタマーサービスおよびサポートに連絡するときに役立ちます。  

## <a name="feedback-hub"></a>フィードバック Hub

HoloLens ユーザーは、Microsoft フィードバックハブデスクトップアプリを使用して、Microsoft サポートに診断情報を送信できます。 詳細と詳しい手順については、「 [フィードバックの提供](hololens-feedback.md)」を参照してください。  

> [!NOTE]  
> **商用またはエンタープライズユーザー:** フィードバックハブアプリを使用して、MDM、プロビジョニング、またはその他のデバイス管理の側面に関連する問題を報告する場合は、アプリカテゴリを [**エンタープライズ管理**  >  **デバイス] カテゴリ** に変更します。

### <a name="prerequisites"></a>前提条件

- デバイスはネットワークに接続されています。
- フィードバックハブアプリはユーザーのデスクトップコンピューターで使用でき、ユーザーは Microsoft クラウドにファイルをアップロードできます。

### <a name="data-locations-access-and-retention"></a>データの場所、アクセス、および保有期間

フィードバックハブの使用条件に同意することで、ユーザーは明示的にデータのストレージと使用状況に同意します (その契約に従って定義されています)。

フィードバックハブは、ユーザーが診断情報を格納するための2つの場所を提供します。

- **Microsoft cloud**。 フィードバックハブアプリを使用してユーザーがアップロードしたデータは、次世代プライバシー (NGP) の要件と一貫性のある日数だけ格納されます。 Microsoft の従業員は、NGP 準拠のビューアーを使用して、この期間中に情報にアクセスすることができます。
   > [!NOTE]  
   > これらの要件は、すべてのフィードバックハブのカテゴリのデータに適用されます。

- **HoloLens デバイス**。 フィードバックハブでレポートをファイリングするときに、ユーザーは [ **フィードバックの提供時に作成された診断と添付ファイルのローカルコピーを保存する**] を選択できます。 ユーザーがこのオプションを選択すると、フィードバックハブによって、HoloLens デバイスに診断情報のコピーが格納されます。 この情報は、ユーザー (またはそのアカウントを使用して HoloLens にサインインするユーザー) が引き続きアクセスできます。 この情報を削除するには、デバイスの **所有者** または **管理者** のアクセス許可が必要です。 適切なアクセス許可を持つユーザーは、フィードバックハブにサインインし、[**設定**] [  >  **診断ログの表示**] を選択して、情報を削除できます。

## <a name="settings-troubleshooter"></a>設定のトラブルシューティング

HoloLens ユーザーは、デバイスの設定アプリを使用して、問題のトラブルシューティングを行ったり、診断情報を収集したりすることができます。 この操作を行うには、次の手順に従います。

1. 設定アプリを開き、[**更新 & のセキュリティ**  >  **トラブルシューティング**] ページを選択します。
1. 適切な領域を選択し、[ **開始**] を選択します。
1. 問題を再現します。
1. 問題を再現した後、[設定] に戻り、[ **停止**] を選択します。

### <a name="prerequisites"></a>前提条件

- 設定アプリがデバイスにインストールされ、ユーザーが使用できるようになります。

### <a name="data-locations-access-and-retention"></a>データの場所、アクセス、および保有期間

ユーザーはデータコレクションを開始するため、ユーザーは診断情報の格納に暗黙的に同意ます。 データにアクセスできるのは、ユーザー、またはユーザーがデータを共有しているユーザーだけです。

診断情報はデバイスに格納されます。 デバイスがユーザーのコンピューターに接続されている場合、情報はコンピューターの次のファイルにも存在します。

> この PC \\ \<*HoloLens device name*> \\ 内部ストレージ \\ ドキュメント \\ トレース \<*ddmmyyhhmmss*>

> [!NOTE]  
> このファイルのパスと名前は、 \<*HoloLens device name*> HoloLens デバイスの名前を表し、 \<*ddmmyyhhmmss*> ファイルが作成された日付と時刻を表します。

診断情報は、ユーザーが削除するまで、これらの場所に残ります。

## <a name="diagnosticlog-csp"></a>DiagnosticLog CSP

モバイルデバイス管理 (MDM) 環境では、IT 管理者は [DiagnosticLog 構成サービスプロバイダー (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) を使用して、登録された HoloLens デバイスの診断設定を構成できます。 IT 管理者は、登録されているデバイスからログを収集するようにこれらの設定を構成できます。

詳細を表示:
- [Windows デバイスから診断情報を収集する](https://docs.microsoft.com/mem/intune/remote-actions/collect-diagnostics)
- [Intune パブリックプレビュー-Windows 10 デバイス診断](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>前提条件

- デバイスはネットワークに接続されています。
- デバイスは、DiagnosticLog CSP をサポートする MDM 環境に登録されています。

### <a name="data-locations-access-and-retention"></a>データの場所、アクセス、および保有期間

デバイスは管理された環境の一部であるため、ユーザーは、診断情報への管理アクセスを暗黙的に同意ます。

IT 管理者は、DiagnosticLog CSP を使用して、データストレージ、リテンション期間、およびアクセスポリシーを構成します。これには、次のポリシーが含まれます。

- 診断情報を格納するクラウドインフラストラクチャ。
- 診断情報の保有期間。
- 診断情報へのアクセスを制御するアクセス許可。

## <a name="offline-diagnostics"></a>オフライン診断
デバイスがフィードバックハブまたは設定トラブルシューティングツールを使用して診断情報を収集できない場合は、手動で診断を収集できます。 これが必要なシナリオの1つは、デバイスが Wi-Fi に接続できない場合、または上記の他の方法にアクセスできない場合です。 診断によって、Microsoft サポートエンジニアが問題を特定するのに役立つ、デバイスからのクラッシュダンプとログが収集されます。

これは、USB ケーブル経由で PC に接続した後に、デバイスがエクスプローラーに表示される場合に機能します。

> [!NOTE]
> オフライン診断の生成と管理は、使用している OS のバージョンによって異なる方法で制御されます。 以前はテレメトリの設定によって制御されていましたが、MDM ポリシーを使用して直接制御されています。 いずれかの設定または MDM ポリシーを使用して無効にした場合、このメカニズムを使用して診断ログを収集することはできません。

[Windows Holographic の前の動作、バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2):
 - オフライン診断が有効になるのは、ユーザーが OOBE を使用しているか、 [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) ポリシーの値が Full (HoloLens では既定値) に設定されている場合のみです。 
- オフライン診断を無効にするには、[設定] [**アプリ > のプライバシー** ] ページにアクセスし、[**診断データ**] で [**基本**] を選択します。 オフライン診断がテレメトリ設定に依存するビルドでは、ログが収集されるかどうかにのみ影響します。 収集されるファイルには影響しません。
- デバイスがロックされている場合、ログは表示されません。

ビルド時に [は、Windows Holographic、バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 以降:
- フォールバック診断が有効になっている場合は、対応する設定[MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)を使用して、特定の MDM ポリシーによって制御されます。
- デバイスがロックされている場合、ログは表示されません。

詳細については、次の動画をご覧ください。

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

診断を収集するには、次の手順を実行します。
1.  USB ケーブルを使用してデバイスを PC に接続します。
2.  PC のエクスプローラーで、[ **この pc \<hololens-device> \ 内部ストレージ]** に移動します。
3.  **内部ストレージ** フォルダーが表示されない場合、デバイスはユーザーのサインインを待機しています。 電源ボタンを10秒間押して、デバイスのサインインまたは電源を入れます。
4.  を押すと、すぐに [ **電源 + 音量** ] ボタンが一緒に解放されます。
5.  デバイスが zip アーカイブを準備するまで1分待ちます。 (HololensDiagnostics という名前の一時ファイルは、デバイスが zip アーカイブを生成している間に表示される場合があります。 このファイルにアクセスしたり保存したりしないでください。 プロセスが完了すると、zip アーカイブに置き換えられます)。
6.  エクスプローラーを最新の状態に更新し、 **' \Documents '** フォルダーに移動します。
7.  診断 ZIP ファイルをコピーし、Microsoft サポートチームと共有します。

> [!NOTE]
> 一部の診断 ZIP ファイルには、個人を特定できる情報が含まれている場合があります。
