---
title: HoloLens デバイスから診断情報を収集する
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
ms.sourcegitcommit: b5f1b7c197cb58b746efc3809c61cf7a2e8c08ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "11399809"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>HoloLens デバイスから診断情報を収集する

HoloLens ユーザーと管理者は、HoloLens から診断情報を収集する 4 つの異なる方法から選択できます。

- フィードバック ハブ アプリ
- DiagnosticLog CSP
- 設定アプリ
- オフライン診断

> [!IMPORTANT]  
> デバイス診断ログには、一般的な操作中にユーザーが開始するプロセスやアプリケーションなど、個人を特定できる情報 (PII) が含まれます。 複数のユーザーが HoloLens デバイスを共有する場合 (たとえば、ユーザーは異なる Microsoft Azure Active Directory (Azure AD) アカウントを使用して同じデバイスにサインインします)、診断ログには、複数のユーザーに適用される PII 情報が含まれる場合があります。 詳細については [、「Microsoft Privacy ステートメント」を参照してください](https://privacy.microsoft.com/privacystatement)。

次の表は、さまざまなコレクション メソッドを比較しています。 メソッド名は、表に続くセクションの詳細情報にリンクします。

|メソッド |前提条件 |データの場所 |データ アクセスと使用 |データ保持 |
| --- | --- | --- | --- | --- |
|[フィードバック Hub](#feedback-hub) |ネットワークとインターネット接続<br /><br />フィードバック ハブ アプリ<br /><br />Microsoft クラウドにファイルをアップロードするアクセス許可 |Microsoft クラウド<br /><br />HoloLens デバイス (オプション) |ユーザーが支援を要求し、使用条件に同意し、データをアップロードする<br /><br />Microsoft の従業員は、使用条件と一致するデータを表示します。 |クラウド内のデータは、次世代プライバシー (NGP) によって定義された期間保持されます。 その後、データは自動的に削除されます。<br /><br />デバイス上のデータは、デバイスの所有者または管理者のアクセス許可を持**** つユーザーが**いつでも削除できます**。 |
|[設定のトラブルシューティング](#settings-troubleshooter) |設定アプリ |HoloLens デバイス<br /><br />接続されたコンピューター (オプション) |ユーザーはデータを保存し、ユーザーだけがデータにアクセスします (ユーザーが別のユーザーとデータを具体的に共有しない限り)。 |データは、ユーザーが削除するまでデバイスに保持されます。* |
|[DiagnosticLog CSP](#diagnosticlog-csp) |ネットワーク接続<br /><br />DiagnosticLog CSP をサポートする MDM 環境 |管理者がストレージの場所を構成する |管理環境では、ユーザーはデータへの管理者アクセスに暗黙的に同意します。<br /><br />管理者は、アクセス ロールとアクセス許可を構成します。 | データはクラウド ストレージに保持され、管理者は保持ポリシーを構成します。 |
|[オフライン診断](#offline-diagnostics) |デバイス構成:<ul><li>電源をオンにし、コンピューターに接続する</li><li>電源ボタンと音量ボタンが機能している</li></ul> |HoloLens デバイス<br /><br />接続されたコンピューター |ユーザーはデータを保存し、ユーザーだけがデータにアクセスします (ユーザーが別のユーザーとデータを具体的に共有しない限り)。 |データは、ユーザーが削除するまでデバイスに保持されます。 |

- エンド ユーザーは、他のユーザーと責任を持ってログを共有する責任があります。 これらのファイルは、主に顧客サービスとサポートに問い合わせするときに役立ちます。  

## <a name="feedback-hub"></a>フィードバック Hub

HoloLens ユーザーは、Microsoft Feedback Hub デスクトップ アプリを使用して、診断情報を Microsoft サポートに送信できます。 詳細と完全な手順については、「フィードバックを [提供する」を参照してください](hololens-feedback.md)。  

> [!NOTE]  
> **商用ユーザーまたはエンタープライズ ユーザー:** フィードバック ハブ アプリを使用して、MDM、プロビジョニング、その他のデバイス管理の側面に関連する問題を報告する場合は、アプリ カテゴリを **[エンタープライズ**管理デバイス] カテゴリに  >  **変更します**。

### <a name="prerequisites"></a>前提条件

- デバイスはネットワークに接続されています。
- フィードバック ハブ アプリは、ユーザーのデスクトップ コンピューターで利用できます。ユーザーは Microsoft クラウドにファイルをアップロードできます。

### <a name="data-locations-access-and-retention"></a>データの場所、アクセス、および保持

フィードバック ハブの使用条件に同意すると、ユーザーはデータの保存と使用に明示的に同意します (この契約で定義されます)。

フィードバック ハブには、ユーザーが診断情報を格納する 2 つの場所があります。

- **Microsoft クラウド**. フィードバック ハブ アプリを使用してユーザーがアップロードしたデータは、次世代プライバシー (NGP) の要件と一致する日数で保存されます。 Microsoft の従業員は、NGP に準拠したビューアーを使用して、この期間中に情報にアクセスできます。
   > [!NOTE]  
   > これらの要件は、すべてのフィードバック ハブ カテゴリのデータに適用されます。

- **HoloLens デバイス**。 フィードバック ハブでレポートを提出する際に、フィードバックを送信するときに作成された診断と添付ファイルのローカル コピーを保存 **する を選択できます**。 ユーザーがこのオプションを選択すると、フィードバック ハブは HoloLens デバイスに診断情報のコピーを保存します。 この情報は、ユーザー (またはそのアカウントを使用して HoloLens にサインインするユーザー) からアクセス可能なままです。 この情報を削除するには、ユーザーがデバイスの **所有者** または **管理者** のアクセス許可を持っている必要があります。 適切なアクセス許可を持つユーザーは、フィードバック ハブにサインインし、[**** 設定] [診断ログの表示] を選択し、  >  **** 情報を削除できます。

## <a name="settings-troubleshooter"></a>設定のトラブルシューティング

HoloLens ユーザーは、デバイスの設定アプリを使用して問題のトラブルシューティングを行い、診断情報を収集できます。 これを行うためには、次の手順を実行します。

1. [設定] アプリを開き、[セキュリティのトラブルシューティング **] ページ&を**  >  **選択**します。
1. 適切な領域を選択し、[スタート] を **選択します**。
1. 問題を再現します。
1. 問題を再現したら、[設定] に戻り、[停止] を **選択します**。

### <a name="prerequisites"></a>前提条件

- 設定アプリはデバイスにインストールされ、ユーザーが利用できます。

### <a name="data-locations-access-and-retention"></a>データの場所、アクセス、および保持

ユーザーがデータ収集を開始すると、ユーザーは診断情報の格納に暗黙的に同意します。 データにアクセスできるのは、ユーザーまたはユーザーがデータを共有するユーザーのみです。

診断情報はデバイスに保存されます。 デバイスがユーザーのコンピューターに接続されている場合、情報は次のファイル内のコンピューターにも存在します。

> この PC\\ \<*HoloLens device name*> \\Internal Storage\\Documents\\Trace \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> このファイル パスと名前では、HoloLens デバイスの名前を表し、ファイルが作成された日時 \<*HoloLens device name*> \<*ddmmyyhhmmss*> を表します。

診断情報は、ユーザーが削除するまで、これらの場所に残ります。

## <a name="diagnosticlog-csp"></a>DiagnosticLog CSP

モバイル デバイス管理 (MDM) 環境では、IT 管理者は DiagnosticLog 構成サービス プロバイダー [(CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) を使用して、登録済み HoloLens デバイスの診断設定を構成できます。 IT 管理者は、登録されたデバイスからログを収集するためにこれらの設定を構成できます。

詳細については、次の情報を参照してください。
- [Windows デバイスから診断を収集する](https://docs.microsoft.com/mem/intune/remote-actions/collect-diagnostics)
- [Intune パブリック プレビュー - Windows 10 デバイス診断](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>前提条件

- デバイスはネットワークに接続されています。
- デバイスは、DiagnosticLog CSP をサポートする MDM 環境に登録されます。

### <a name="data-locations-access-and-retention"></a>データの場所、アクセス、および保持

デバイスは管理環境の一部なので、ユーザーは診断情報への管理アクセスに暗黙的に同意します。

IT 管理者は、DiagnosticLog CSP を使用して、次のポリシーを管理するポリシーを含む、データ ストレージ、保持、およびアクセス ポリシーを構成します。

- 診断情報を格納するクラウド インフラストラクチャ。
- 診断情報の保持期間。
- 診断情報へのアクセスを制御するアクセス許可。

## <a name="offline-diagnostics"></a>オフライン診断
デバイスがフィードバック ハブまたは設定トラブルシューティング ツールを介して診断を収集できない状況では、手動で診断を収集できます。 これが必要なシナリオの 1 つは、デバイスがデバイスに接続できない場合Wi-Fi上記の他の方法にアクセスできない場合です。 診断は、Microsoft サポート エンジニアが問題を特定するのに役立つクラッシュ ダンプとログをデバイスから収集します。

これは、USB ケーブルを介して PC に接続した後、デバイスがエクスプローラーに表示される場合に機能します。

> [!NOTE]
> オフライン診断の生成と管理は、OS のバージョンに応じて異なる方法で制御されます。 以前はテレメトリ設定によって制御されましたが、MDM ポリシーによって直接制御されました。 設定または MDM ポリシーを使用して無効にした場合、このメカニズムを使用して診断ログを収集できません。

[Windows Holographic バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2)より前の動作:
 - オフライン診断は、ユーザーが OOBE または [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) ポリシー値が Full に設定されている場合にのみ有効になります (HoloLens の既定値は Basic です)。 
- オフライン診断を無効にするには、[アプリの設定] ページ **>、[** 診断データ] で [ **基本** ] **を選択します**。 オフライン診断がテレメトリ設定に依存するビルドでは、ログが収集されるかどうかにのみ影響します。 収集されるファイルには影響はありません。
- デバイスがロックされている場合、ログは表示されません。

Windows [Holographic バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 以降をビルドする場合:
- フォールバック診断が有効になっている場合は、対応する[MixedReality/フォールバックDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)の設定を使用して特定の MDM ポリシーによって制御されます。
- デバイスがロックされている場合、ログは表示されません。

詳細については、このビデオをご覧ください。

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

診断を収集するには、次の手順に従います。
1.  デバイスを USB ケーブルで PC に接続します。
2.  PC のエクスプローラーで、[この ** \<hololens-device> PC\Internal Storage] に移動します**。
3.  [内部 **記憶域]** フォルダーが表示されない場合、デバイスはユーザーがサインインを待機しています。 POWER ボタンを 10 秒間押し続け、デバイスのサインインまたは電源のサイクルを行います。
4.  POWER + VOLUME DOWN ボタン **を一緒に押して** すぐに離します。
5.  デバイスが zip アーカイブを準備するまで 1 分待ちます。 (HololensDiagnostics.temp という名前の一時ファイルは、デバイスが zip アーカイブを生成している間に表示される場合があります。 そのファイルにアクセスしたり、保存したりしない。 プロセスが終了すると、zip アーカイブに置き換えられる)。
6.  エクスプローラーを更新し **、'\Documents' フォルダーに移動** します。
7.  診断 ZIP ファイルをコピーし、Microsoft サポート チームと共有します。

> [!NOTE]
> 一部の診断 ZIP ファイルには、個人を特定できる情報が含まれている場合があります。
