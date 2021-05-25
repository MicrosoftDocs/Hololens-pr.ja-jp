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
ms.openlocfilehash: c1d5205d4faa4384600c489167c9581de8e4b62c
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397843"
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
|[フィードバック Hub](#feedback-hub) |ネットワークとインターネット接続<br /><br />フィードバックハブアプリ<br /><br />Microsoft クラウドにファイルをアップロードするためのアクセス許可 |Microsoft クラウド<br /><br />HoloLens デバイス (オプション) |ユーザーがアシスタンスを要求し、使用条件に同意して、データをアップロードする<br /><br />Microsoft の従業員が使用条件に従ってデータを表示する |クラウド内のデータは、次世代プライバシー (NGP) で定義されている期間にわたって保持されます。 その後、データは自動的に削除されます。<br /><br />デバイスの所有者または管理者のアクセス許可を持つユーザーは、デバイス上 **のデータ** を **いつでも削除** できます。 |
|[設定のトラブルシューティング ツール](#settings-troubleshooter) |設定アプリ |HoloLens デバイス<br /><br />接続されているコンピューター (省略可能) |ユーザーはデータを格納し、ユーザーだけがデータにアクセスします (ユーザーがデータを別のユーザーと具体的に共有しない限り)。 |データは、ユーザーが削除するまでデバイスに保持されます。* |
|[DiagnosticLog CSP](#diagnosticlog-csp) |ネットワーク接続<br /><br />DiagnosticLog CSP をサポートする MDM 環境 |管理者がストレージの場所を構成する |マネージド環境では、ユーザーはデータへの管理者アクセスに暗黙的に同意します。<br /><br />管理者は、アクセス ロールとアクセス許可を構成します。 | データはクラウド ストレージに保持され、管理者は保持ポリシーを構成します。 |
|[オフライン診断](#offline-diagnostics) |デバイス構成:<ul><li>電源をオンにし、コンピューターに接続する</li><li>機能する電源ボタンとボリューム ボタン</li></ul> |HoloLens デバイス<br /><br />接続されているコンピューター |ユーザーはデータを格納し、ユーザーだけがデータにアクセスします (ユーザーがデータを別のユーザーと具体的に共有しない限り)。 |データは、ユーザーが削除するまでデバイスに保持されます。 |

* エンド ユーザーは、他のユーザーと責任を持ってログを共有する責任があります。 これらのファイルは、主にカスタマー サービスとサポートに問い合わせするときに役立ちます。  

## <a name="feedback-hub"></a>フィードバック Hub

HoloLens ユーザーは、Microsoft フィードバック Hub デスクトップ アプリを使用して、診断情報をデバイスに送信Microsoft サポート。 詳細と詳しい手順については、「 [フィードバックの提供](hololens-feedback.md)」を参照してください。  

> [!NOTE]  
> **商用またはエンタープライズユーザー:** フィードバックハブアプリを使用して、MDM、プロビジョニング、またはその他のデバイス管理の側面に関連する問題を報告する場合は、アプリカテゴリを [**エンタープライズ管理**  >  **デバイス] カテゴリ** に変更します。

>[!IMPORTANT]
> 問題を修正するための最適なデータを提供するには、デバイスのテレメトリを **オプション** に設定することを強くお勧めします。 この値は、既定のエクスペリエンス (OOBE) で、または **設定** アプリを使用して設定できます。 設定を使用してこれを行うには、 **[> 設定の開始] > [プライバシー > アプリ診断 > オン**] を選択します。
### <a name="prerequisites"></a>前提条件

- デバイスはネットワークに接続されています。
- フィードバックハブアプリはユーザーのデスクトップコンピューターで使用でき、ユーザーは Microsoft クラウドにファイルをアップロードできます。

### <a name="data-locations-access-and-retention"></a>データの場所、アクセス、および保有期間

フィードバックハブの使用条件に同意することで、ユーザーは明示的にデータのストレージと使用状況に同意します (その契約に従って定義されています)。

フィードバックハブは、ユーザーが診断情報を格納するための2つの場所を提供します。

- **Microsoft cloud**。 フィードバックハブアプリを使用してユーザーがアップロードしたデータは、次世代プライバシー (NGP) の要件と一貫性のある日数だけ格納されます。 Microsoft の従業員は、NGP 準拠のビューアーを使用して、この期間中に情報にアクセスすることができます。

   > [!NOTE]  
   > これらの要件は、すべてのフィードバックハブのカテゴリのデータに適用されます。

- **HoloLens デバイス**。 フィードバックハブでレポートをファイリングするときに、ユーザーは [ **フィードバックの提供時に作成された診断と添付ファイルのローカルコピーを保存する**] を選択できます。 ユーザーがこのオプションを選択すると、フィードバックハブによって、HoloLens デバイスに診断情報のコピーが格納されます。 この情報は、ユーザー (またはそのアカウントを使用して HoloLens にサインインするユーザー) が引き続きアクセスできます。 この情報を削除するには、デバイスの **所有者** または **管理者** のアクセス許可が必要です。 適切なアクセス許可を持つユーザーは、フィードバック Hub にサインインし、[設定] [診断ログの表示] を選択して  >  、情報を削除できます。

## <a name="settings-troubleshooter"></a>設定のトラブルシューティング ツール

HoloLens ユーザーは、デバイス上の **設定** アプリを使用して、問題のトラブルシューティングと診断情報の収集を行います。 この操作を行うには、次の手順に従います。

1. [設定] アプリを開き、[セキュリティのトラブルシューティング **] &更新]**  >  **を選択** します。
1. 適切な領域を選択し、 [開始] を **選択します**。
1. 問題を再現します。
1. 問題を再現した後、[設定] に戻り、[停止] を **選択します**。

ユーザーは、設定アプリからフォールバック診断の動作を **構成** することもできます。 [プライバシー **] ->トラブルシューティング] ページに移動** して、この設定を構成します。
> [!NOTE]
> デバイスに対して MDM ポリシーが構成されている場合、ユーザーは、その動作をオーバーライドできます。

### <a name="os-update-troubleshooter"></a>OS 更新のトラブルシューティング ツール
では [、Windows Holographic バージョン 21H1 ](hololens-release-notes.md#windows-holographic-version-21h1) 以降がビルドされます。
- 設定アプリ内の以前のトラブルシューティング ツールに加えて、新しいトラブルシューティング ツールが追加され、OS 更新用の新しい設定アプリが追加されました。 [設定 **] -> [セキュリティ&更新] ->トラブルシューティング -> Windows Updateに** 移動し、[ 開始] を **選択します**。 これにより、OS の更新に関する問題を再現しながらトレースを収集し、IT またはサポートのトラブルシューティングに役立ちます。
### <a name="prerequisites"></a>前提条件

- 設定 **アプリ** はデバイスにインストールされ、ユーザーが使用できます。

### <a name="data-locations-access-and-retention"></a>データの場所、アクセス、リテンション期間

ユーザーがデータ収集を開始すると、ユーザーは診断情報のストレージに暗黙的に同意します。 データにアクセスできるのは、ユーザーまたはユーザーがデータを共有するユーザーのみです。

診断情報はデバイスに格納されます。 デバイスがユーザーのコンピューターに接続されている場合、情報は次のファイル内のコンピューターにも存在します。

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
デバイスがフィードバックハブまたは設定のトラブルシューティングツールを使用して診断情報を収集できない場合は、手動で診断を収集できます。 これが必要なシナリオの1つは、デバイスが Wi-Fi に接続できない場合、または上記の他の方法にアクセスできない場合です。 診断によって、Microsoft サポートエンジニアが問題を特定するのに役立つ、デバイスからのクラッシュダンプとログが収集されます。

これは、USB ケーブル経由で PC に接続した後に、デバイスがエクスプローラーに表示される場合に機能します。

> [!NOTE]
> オフライン診断の生成と管理は、OS のバージョンによって異なる方法で制御されます。 以前はテレメトリ設定によって制御されましたが、現在は MDM ポリシーを使用して直接制御されています。 設定または MDM ポリシーを使用して無効にした場合、このメカニズムを使用して診断ログを収集することはできません。

[Windows Holographic バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2)より前の動作:
 - オフライン診断は、ユーザーが OOBE を通過している場合、または [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) ポリシー値が Full に設定されている場合にのみ有効になります (HoloLens では Basic が既定値です)。 
- オフライン診断を無効にするには、[設定] [アプリとプライバシー] **>に移動** し、[診断データ] で [ **基本]** **を選択します**。 オフライン診断がテレメトリ設定に依存するビルドでは、ログが収集されるかどうかにのみ影響します。 収集されるファイルには影響はありません。
- デバイスがロックされている場合、ログは表示されません。

では [、Windows Holographic バージョン 20H2 以降が](hololens-release-notes.md#windows-holographic-version-20h2) ビルドされます。
- フォールバック診断が有効になっている場合は、対応する[MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)設定を使用して特定の MDM ポリシーによって制御されます
- デバイスがロックされている場合、ログは表示されません。

詳細については、次の動画をご覧ください。

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

診断を収集するには、次の手順に従います。
1.  デバイスを USB ケーブルで PC に接続します。
2.  PC エクスプローラーで、[This PC \Internal Storage]\(この **PC \<hololens-device> \内部ストレージ\) に移動します**。
3.  Internal **Storage フォルダーが** 表示されない場合、デバイスはユーザーのサインインを待機しています。 POWER ボタンを 10 秒間押して、サインインまたは電源サイクルを行います。
4.  Power + Volume Down ボタン **を押して** すぐに離します。
5.  デバイスが zip アーカイブを準備するまで少し待ちます。 (HololensDiagnostics.temp という名前の一時ファイルは、デバイスが zip アーカイブを生成している間に表示される場合があります。 このファイルにアクセスしたり保存したりしないでください。 プロセスが完了すると、zip アーカイブに置き換えられます)。
6.  エクスプローラーを最新の状態に更新し、 **' \Documents '** フォルダーに移動します。
7.  診断 ZIP ファイルをコピーし、Microsoft サポートチームと共有します。

> [!NOTE]
> 一部の診断 ZIP ファイルには PII が含まれている場合があります。
