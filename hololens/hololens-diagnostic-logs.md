---
title: HoloLens デバイスから診断情報を収集して使用する
description: HoloLens デバイスから診断情報を収集、使用、および保持する方法について説明します。
author: Teresa-Motiv
ms.author: v-tea
ms.date: 9/12/2021
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
ms.openlocfilehash: 4f62a70430d78087157b3adcdf76af53183db708
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924414"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>HoloLens デバイスから診断情報を収集して使用する

HoloLens のユーザーと管理者は、HoloLens から診断情報を収集するために、次の4種類の方法から選択できます。

- フィードバックハブアプリ
- DiagnosticLog CSP
- 設定アプリ
- オフライン診断

> [!IMPORTANT]  
> デバイス診断ログには、ユーザーが通常の操作で開始するプロセスやアプリケーションなど、個人を特定できる情報 (PII) が含まれています。 複数のユーザーが HoloLens デバイスを共有している場合 (たとえば、ユーザーが別の Microsoft Azure Active Directory (Azure AD) アカウントを使用して同じデバイスにサインインする場合)、診断ログには、複数のユーザーに適用される PII 情報が含まれる場合があります。 詳細については、「 [Microsoft のプライバシー](https://privacy.microsoft.com/privacystatement)に関する声明」を参照してください。

次の表は、さまざまな収集方法を比較したものです。 メソッド名は、テーブルに続くセクションの詳細情報にリンクされています。

|メソッド |前提条件 |データの場所 |データアクセスと使用 |データ保持期間 |
| --- | --- | --- | --- | --- |
|[フィードバック Hub](#feedback-hub) |ネットワークとインターネット接続<br /><br />フィードバックハブアプリ<br /><br />Microsoft クラウドにファイルをアップロードするためのアクセス許可 |Microsoft クラウド<br /><br />HoloLens デバイス (オプション) |ユーザーがアシスタンスを要求し、使用条件に同意して、データをアップロードする<br /><br />Microsoft の従業員が使用条件に従ってデータを表示する |クラウド内のデータは、次世代プライバシー (NGP) で定義されている期間にわたって保持されます。 その後、データは自動的に削除されます。<br /><br />デバイス上のデータは、 **デバイスの所有者** または **管理者** のアクセス許可を持つユーザーがいつでも削除できます。 |
|[設定診断](#settings-troubleshooter) |設定アプリ |HoloLens デバイス<br /><br />接続されたコンピューター (オプション) |ユーザーはデータを保存し、ユーザーのみがデータにアクセスします (ユーザーが明示的に別のユーザーとデータを共有している場合を除く)。 |データは、ユーザーが削除するまでデバイスに保持されます。 * |
|[DiagnosticLog CSP](#diagnosticlog-csp) |ネットワーク接続<br /><br />DiagnosticLog CSP をサポートする MDM 環境 |管理者がストレージの場所を構成する |管理された環境では、ユーザーはデータへの管理者アクセスを暗黙的に同意ます。<br /><br />管理者は、アクセスの役割とアクセス許可を構成します。 | データはクラウドストレージに保持され、管理者はリテンション期間ポリシーを構成します。 |
|[オフライン診断](#offline-diagnostics) |デバイスの構成:<ul><li>電源が入っていて、コンピューターに接続されている</li><li>電源ボタンと音量ボタンが機能している</li></ul> |HoloLens デバイス<br /><br />接続されたコンピューター |ユーザーはデータを保存し、ユーザーのみがデータにアクセスします (ユーザーが明示的に別のユーザーとデータを共有している場合を除く)。 |データは、ユーザーが削除するまでデバイスに保持されます。 |

* エンドユーザーは、他のユーザーとログを確実に共有する必要があります。 これらのファイルは、主にカスタマーサービスおよびサポートに連絡するときに役立ちます。  

## <a name="feedback-hub"></a>フィードバック Hub

HoloLens ユーザーは、Microsoft フィードバックハブデスクトップアプリを使用して Microsoft サポートに診断情報を送信できます。 詳細と詳しい手順については、「 [フィードバックの提供](hololens-feedback.md)」を参照してください。  

> [!NOTE]  
> **商用またはエンタープライズユーザー:** フィードバックハブアプリを使用して、MDM、プロビジョニング、またはその他のデバイス管理の側面に関連する問題を報告する場合は、アプリのカテゴリを [ **Enterprise 管理**  >  **デバイス] カテゴリ** に変更します。

>[!IMPORTANT]
> 問題を修正するための最適なデータを提供するには、デバイスのテレメトリを **オプション** に設定することを強くお勧めします。 この値は、インボックスエクスペリエンス (OOBE) で、または **設定** アプリを使用して設定できます。 設定を使用してこれを行うには、[**スタート > 設定 > プライバシー > App Diagnostics > On**] を選択します。

### <a name="prerequisites"></a>前提条件

- デバイスはネットワークに接続されています。
- フィードバックハブアプリはユーザーのデスクトップコンピューターで使用でき、ユーザーは Microsoft クラウドにファイルをアップロードできます。

### <a name="data-locations-access-and-retention"></a>データの場所、アクセス、および保有期間

フィードバックハブの使用条件に同意することで、ユーザーは明示的にデータのストレージと使用状況に同意します (その契約に従って定義されています)。

フィードバックハブは、ユーザーが診断情報を格納するための2つの場所を提供します。

- **Microsoft cloud**。 フィードバックハブアプリを使用してユーザーがアップロードしたデータは、次世代プライバシー (NGP) の要件と一貫性のある日数だけ格納されます。 Microsoft の従業員は、NGP 準拠のビューアーを使用して、この期間中に情報にアクセスすることができます。

   > [!NOTE]  
   > これらの要件は、すべてのフィードバックハブのカテゴリのデータに適用されます。

- **HoloLens デバイス**。 フィードバックハブでレポートをファイリングするときに、ユーザーは [ **フィードバックの提供時に作成された診断と添付ファイルのローカルコピーを保存する**] を選択できます。 ユーザーがこのオプションを選択すると、フィードバックハブは HoloLens デバイスに診断情報のコピーを保存します。 この情報は、ユーザー (またはそのアカウントを使用して HoloLens にサインインするユーザー) が引き続きアクセスできます。 この情報を削除するには、デバイスの **所有者** または **管理者** のアクセス許可が必要です。 適切なアクセス許可を持つユーザーは、フィードバックハブにサインインして、   >  **診断ログ** を設定表示し、情報を削除できます。

## <a name="settings-troubleshooter"></a>設定診断

HoloLens ユーザーは、デバイスの **設定** アプリを使用して、問題のトラブルシューティングを行い、診断情報を収集できます。 これを行うには、次の手順に従います。

1. 設定アプリを開き、[**更新 & セキュリティ**  >  **トラブルシューティング**] ページを選択します。
1. 適切な領域を選択し、[ **開始**] を選択します。
1. 問題を再現します。
1. 問題を再現した後、設定に戻り、[**停止**] を選択します。

ユーザーは、**設定** アプリからフォールバック診断の動作を構成することもできます。 この設定を構成するには **、[プライバシー]-> のトラブルシューティング** ページに移動します。
> [!NOTE]
> デバイスに MDM ポリシーが構成されている場合、ユーザーはその動作をオーバーライドすることはできません。

### <a name="os-update-troubleshooter"></a>OS の更新に関するトラブルシューティング

ビルド時[Windows Holographic、バージョン 21h1](hololens-release-notes.md#windows-holographic-version-21h1)以降:
- 設定アプリ内の前のトラブルシューティングツールに加えて、新しいトラブルシューティングツールが追加されました。 OS 更新プログラム用の新しい設定アプリが追加されました。 設定に移動し、 **> Update & Security-> トラブルシューティング-> Windows Update** をクリックして、[**開始**] を選択します。 これにより、OS の更新に関する問題を再現しながら、IT またはサポートによるトラブルシューティングを容易にするために、トレースを収集することができます。

### <a name="prerequisites"></a>前提条件

- **設定** アプリがデバイスにインストールされ、ユーザーが使用できるようになります。

### <a name="data-locations-access-and-retention"></a>データの場所、アクセス、および保有期間

ユーザーはデータコレクションを開始するため、ユーザーは診断情報の格納に暗黙的に同意ます。 データにアクセスできるのは、ユーザー、またはユーザーがデータを共有しているユーザーだけです。

診断情報はデバイスに格納されます。 デバイスがユーザーのコンピューターに接続されている場合、情報はコンピューターの次のファイルにも存在します。

> この PC \\ \<*HoloLens device name*> \\ 内部 Storage \\ ドキュメント \\ トレース \<*ddmmyyhhmmss*>

> [!NOTE]  
> このファイルのパスと名前は、 \<*HoloLens device name*> HoloLens デバイスの名前を表し、 \<*ddmmyyhhmmss*> ファイルが作成された日付と時刻を表します。

診断情報は、ユーザーが削除するまで、これらの場所に残ります。

### <a name="view-diagnostic-report"></a>診断レポートを表示する

HoloLens 2 で MDM 診断を表示するには、WiFi アイコンを選択し、[設定Accounts Access work or school] に移動し、[管理ログのエクスポート]  ->    >  **を選択します**。 HoloLensアカウントにログ ファイルを送信し、その場所をデスクトップ PC に表示します。

## <a name="diagnosticlog-csp"></a>DiagnosticLog CSP

MOBILE デバイス管理 (MDM) 環境では、IT 管理者は DiagnosticLog 構成サービス プロバイダー [(CSP)](/windows/client-management/mdm/diagnosticlog-csp)を使用して、登録済みデバイスの診断設定を構成HoloLensできます。 IT 管理者は、登録されたデバイスからログを収集するためにこれらの設定を構成できます。

詳細については、以下を参照してください。
- [Windows デバイスから診断情報を収集する](/mem/intune/remote-actions/collect-diagnostics)
- [Intune パブリック プレビュー - Windows 10 デバイス診断](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>前提条件

- デバイスはネットワークに接続されています。
- デバイスは、DiagnosticLog CSP をサポートする MDM 環境に登録されます。

### <a name="data-locations-access-and-retention"></a>データの場所、アクセス、リテンション期間

デバイスはマネージド環境の一部なので、ユーザーは診断情報への管理アクセスに暗黙的に同意します。

IT 管理者は、DiagnosticLog CSP を使用して、次のポリシーを管理するポリシーを含む、データ ストレージ、リテンション期間、およびアクセス ポリシーを構成します。

- 診断情報を格納するクラウド インフラストラクチャ。
- 診断情報の保持期間。
- 診断情報へのアクセスを制御するアクセス許可。

## <a name="offline-diagnostics"></a>オフライン診断

デバイスが診断を収集できない場合は、フィードバック Hub または 設定 トラブルシューティング ツールを使用して診断を手動で収集できます。 これが必要なシナリオの 1 つは、デバイスがデバイスに接続できない場合Wi-Fi上記の他の方法にアクセスできない場合です。 診断では、Microsoft サポート エンジニアが問題を特定するのに役立つクラッシュ ダンプとログがデバイスから収集されます。

これは、USB ケーブルを介して PC に接続エクスプローラーデバイスがデバイスに表示される場合に機能します。

> [!NOTE]
> オフライン診断の生成と管理は、OS のバージョンによって異なる方法で制御されます。 以前はテレメトリ設定によって制御されましたが、現在は MDM ポリシーを介して直接制御されています。 設定または MDM ポリシーを使用して無効にした場合、このメカニズムを使用して診断ログを収集することはできません。

[Holographic バージョン 20H2 Windows以前の動作](hololens-release-notes.md#windows-holographic-version-20h2):
 - オフライン診断は、ユーザーが OOBE を通過している場合、または[System\AllowTelemetry](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry)ポリシー値が [完全] に設定されている場合にのみ有効になります (基本は HoloLens の既定値です)。 
- オフライン診断を無効にするには、[アプリのプライバシー] ページ **設定[>]** ページに移動し、[診断データ] で [**基本]** **を選択します**。 オフライン診断がテレメトリ設定に依存するビルドでは、ログが収集されるかどうかにのみ影響します。 収集されるファイルには影響はありません。
- デバイスがロックされている場合、ログは表示されません。

[Holographic Windowsバージョン 20H2 以降のビルド](hololens-release-notes.md#windows-holographic-version-20h2)の場合:
- フォールバック診断が有効になっている場合は、対応する[MixedReality/FallbackDiagnostics](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)設定を使用して特定の MDM ポリシーによって制御されます
- デバイスがロックされている場合、ログは表示されません。

詳細については、次の動画をご覧ください。

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

診断を収集するには、次の手順に従います。

1.  Connect USB ケーブルでデバイスを PC に接続します。

2.  PC エクスプローラーで **、'This PC \<hololens-device> \Internal Storage' に移動します**。

3.  Internal **Storage** フォルダーが表示されない場合、デバイスはユーザーのサインインを待機しています。 POWER ボタンを 10 秒間押して、サインインまたは電源サイクルを行います。

4.  Power + Volume Down ボタンを **押してすぐに** 離します。

5.  デバイスが zip アーカイブを準備するまで少し待ちます。 (HololensDiagnostics.temp という名前の一時ファイルは、デバイスが zip アーカイブを生成している間に表示される場合があります。 そのファイルにアクセスしたり保存したりしない。 プロセスが完了すると、zip アーカイブに置き換えられる)。

6.  エクスプローラーを更新し **、'\Documents' フォルダーに移動** します。

7.  診断 ZIP ファイルをコピーし、Microsoft サポート チームと共有します。

> [!NOTE]
> 一部の診断 ZIP ファイルには PII が含まれている場合があります。

### <a name="offline-diagnostics-notifications"></a>オフライン診断通知

- [Holographic バージョンWindows 21H2 で導入されました](hololens-release-notes.md#windows-holographic-version-21h2)。

これは、オフライン診断 と呼ばれる既存の機能 [の更新プログラムです](hololens-diagnostic-logs.md#offline-diagnostics)。 以前は、診断収集をトリガーした、または完了したユーザーに対する明確なインジケーターは見ていました。
Insider ビルドWindowsに追加されました。オフライン診断には、2 つの形式の視聴覚フィードバックがあります。 1 つ目は、コレクションの開始と完了の両方に対して表示されるトースト通知です。 これらは、ユーザーがログインし、ビジュアルを持つ場合に表示されます。

![ログを収集するトースト。](./images/logcollection1.jpg)

![ログ収集が完了したらトーストします。](./images/logcollection2.jpg)

ユーザーは、ディスプレイにアクセスできない場合、ログインできない、または OOBE にまだ存在する場合のフォールバック ログ収集メカニズムとしてオフライン診断を使用する場合が多いので、ログを収集するときにオーディオ キューも再生されます。 このサウンドは、トースト通知に加えて再生されます。

この新機能は、デバイスが更新された場合に有効になります。有効または管理する必要はない。 この新しいフィードバックを表示または確認できない場合でも、オフライン診断は生成されます。

この新しいオーディオビジュアル フィードバックの追加により、診断データの収集が容易になり、問題をより迅速にトラブルシューティングできると期待しています。

### <a name="low-storage-log-collection-improvements"></a>低ストレージ ログ収集の機能強化

- [Holographic バージョンWindows 21H2 で導入されました](hololens-release-notes.md#windows-holographic-version-21h2)。

診断ログの収集時にデバイスのディスク領域が少なそうなシナリオでは、StorageDiagnostics.zipという名前 **の追加レポート** が作成されます。 記憶域が少ない場合のしきい値は、ストレージ のWindows[によって決まります](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)。

## <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>詳細な診断レポートは、設定で表示HoloLens

- [Holographic バージョンWindows 21H2 で導入されました](hololens-release-notes.md#windows-holographic-version-21h2)。

動作のトラブルシューティング時にマネージド デバイスに対して、想定されるポリシー構成が適用されるのを確認することが重要な手順です。 以前は、この新機能では **、設定** アカウント アクセスの仕事または学校を介して収集された MDM 診断ログをエクスポートした後、MDM またはデバイスの近くでデバイスからこれを行い、管理ログをエクスポートし、近くの  ->    >  PCで表示するを選択する必要がありました。

これで、Edge ブラウザーを使用してデバイスで MDM 診断を表示できます。 MDM 診断レポートを簡単に表示するには、[Access work or school]/(学校または学校へのアクセス)ページに移動し、[高度な診断レポートの表示 **] を選択します**。 これにより、新しい Edge ウィンドウでレポートが生成され、開きます。

![アプリで高度な診断レポート設定表示します。](./images/view-advanced-diagnostic-report.jpg)
