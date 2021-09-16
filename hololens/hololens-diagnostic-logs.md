---
title: HoloLens デバイスから診断情報を収集して使用する
description: デバイスから診断情報を収集、使用、および保持する方法HoloLensします。
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
ms.openlocfilehash: e977d0d42831760749bb5c6c469d2482e2ca72e7
ms.sourcegitcommit: 20ea1ed37772655504ccb11a7e185ed19d85f336
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2021
ms.locfileid: "127833524"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>HoloLens デバイスから診断情報を収集して使用する

HoloLensと管理者は、次の 4 つの方法から選択して、診断情報を収集HoloLens。

- フィードバック Hub アプリ
- DiagnosticLog CSP
- 設定アプリ
- オフライン診断

> [!IMPORTANT]  
> デバイス診断ログには、ユーザーが一般的な操作中に開始するプロセスやアプリケーションなど、個人を特定できる情報 (PII) が含まれます。 複数のユーザーが HoloLens デバイスを共有する場合 (たとえば、ユーザーは異なる Microsoft Azure Active Directory (Azure AD) アカウントを使用して同じデバイスにサインインします)、診断ログには、複数のユーザーに適用される PII 情報が含まれる場合があります。 詳細については、「Microsoft のプライバシーに関 [する声明」を参照してください](https://privacy.microsoft.com/privacystatement)。

次の表は、さまざまなコレクション メソッドを比較しています。 メソッド名は、表に続くセクションの詳細情報にリンクされています。

|Method |前提条件 |データの場所 |データへのアクセスと使用 |データの保持 |
| --- | --- | --- | --- | --- |
|[フィードバック Hub](#feedback-hub) |ネットワークとインターネット接続<br /><br />フィードバック Hub アプリ<br /><br />Microsoft クラウドにファイルをアップロードするアクセス許可 |Microsoft クラウド<br /><br />HoloLens デバイス (省略可能) |ユーザーがサポートを要求し、使用条件に同意し、データをアップロードする<br /><br />Microsoft の従業員は、使用条件に従ってデータを表示します |クラウド内のデータは、次世代プライバシー (NGP) によって定義されている期間保持されます。 その後、データは自動的に削除されます。<br /><br />デバイスの所有者または管理者のアクセス許可を持つユーザーは、デバイス上 **のデータ** を **いつでも削除** できます。 |
|[設定トラブルシューティング](#settings-troubleshooter) |設定アプリ |HoloLens デバイス<br /><br />接続されているコンピューター (省略可能) |ユーザーはデータを格納し、ユーザーだけがデータにアクセスします (ユーザーが別のユーザーとデータを具体的に共有しない限り)。 |データは、ユーザーが削除するまでデバイスに保持されます。* |
|[DiagnosticLog CSP](#diagnosticlog-csp) |ネットワーク接続<br /><br />DiagnosticLog CSP をサポートする MDM 環境 |管理者がストレージの場所を構成する |マネージド環境では、ユーザーはデータへの管理者アクセスに暗黙的に同意します。<br /><br />管理者は、アクセス ロールとアクセス許可を構成します。 | データはクラウド ストレージに保持され、管理者は保持ポリシーを構成します。 |
|[オフライン診断](#offline-diagnostics) |デバイス構成:<ul><li>電源をオンにし、コンピューターに接続する</li><li>機能する電源ボタンとボリューム ボタン</li></ul> |HoloLens デバイス<br /><br />接続されているコンピューター |ユーザーはデータを格納し、ユーザーだけがデータにアクセスします (ユーザーが別のユーザーとデータを具体的に共有しない限り)。 |データは、ユーザーが削除するまでデバイスに保持されます。 |

* エンド ユーザーは、他のユーザーと責任を持ってログを共有する責任があります。 これらのファイルは、主にカスタマー サービスとサポートに問い合わせするときに役立ちます。  

## <a name="feedback-hub"></a>フィードバック Hub

ユーザー HoloLens Microsoft フィードバック Hub デスクトップ アプリを使用して、診断情報をユーザーに送信Microsoft サポート。 詳細と詳細な手順については、「フィードバックをお寄せください [」を参照してください](hololens-feedback.md)。  

> [!NOTE]  
> **商用ユーザーまたはエンタープライズ ユーザー:** フィードバック Hub アプリを使用して、MDM、プロビジョニング、または他のデバイス管理の側面に関連する問題を報告する場合は、アプリ カテゴリを **Enterprise 管理** デバイス カテゴリ に変更  >  **します**。

>[!IMPORTANT]
> 問題を修正するために可能な限り最適なデータを提供するには、デバイステレメトリを省略可能 に設定することを強くお勧 **めします**。 この値は、Out-of-Box-Experience (OOBE) の間に設定するか、アプリで **設定できます。** これを行うには、 [アプリの診断] 設定を使用して [> 設定 >**プライバシー>を開始>選択します**。

### <a name="prerequisites"></a>前提条件

- デバイスはネットワークに接続されています。
- アプリフィードバック Hubユーザーのデスクトップ コンピューターで使用できます。ユーザーは Microsoft クラウドにファイルをアップロードできます。

### <a name="data-locations-access-and-retention"></a>データの場所、アクセス、リテンション期間

ユーザーは、フィードバック Hub の使用条件に同意することで、(その契約で定義されている) データの保存と使用に明示的に同意します。

このフィードバック Hub、ユーザーが診断情報を格納する 2 つの場所が提供されます。

- **Microsoft クラウド**。 フィードバック Hub アプリを使用してユーザーがアップロードしたデータは、次世代プライバシー (NGP) の要件と一致する日数の間格納されます。 Microsoft の従業員は、NGP に準拠したビューアーを使用して、この期間中の情報にアクセスできます。

   > [!NOTE]  
   > これらの要件は、すべてのカテゴリのデータフィードバック Hubされます。

- **デバイス HoloLens。** レポートをレポートに提出するときにフィードバック Hubユーザーは、フィードバックを提供するときに作成された診断と添付ファイルのローカル コピーを **保存するを選択できます**。 ユーザーがこのオプションを選択すると、フィードバック Hubデバイスに診断情報のコピーがHoloLensされます。 この情報には、ユーザー (または、そのアカウントを使用してサインインしてサインインしているユーザー) が引き続きHoloLens。 この情報を削除するには、ユーザーがデバイスに対する **デバイス所有者** または **管理者の** アクセス許可を持っている必要があります。 適切なアクセス許可を持つユーザーは、フィードバック Hub にサインインし、[診断ログ設定を表示] を選択して  >  、情報を削除できます。

## <a name="settings-troubleshooter"></a>設定トラブルシューティング

ユーザー HoloLensデバイス上の 設定アプリを使用して、問題のトラブルシューティングと診断情報の収集を行います。 これを行うには、次の手順に従います。

1. アプリを開設定、[セキュリティのトラブルシューティング] ページ **&更新]**  >  **を選択** します。
1. 適切な領域を選択し、 [開始] を **選択します**。
1. 問題を再現します。
1. 問題を再現した後、次の手順に戻設定停止] を **選択します**。

ユーザーは、アプリからフォールバック診断の動作 **設定** することもできます。 [プライバシー **] ->トラブルシューティング] ページに移動** して、この設定を構成します。
> [!NOTE]
> デバイスに対して MDM ポリシーが構成されている場合、ユーザーは、その動作をオーバーライドできます。

### <a name="os-update-troubleshooter"></a>OS 更新のトラブルシューティング ツール

[Holographic Windowsバージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1)以降のビルドの場合:
- 設定 アプリ内の以前のトラブルシューティング ツールに加えて、新しいトラブルシューティング ツールが追加され、OS 更新用の新しい 設定 アプリが追加されました。 **[設定 -> Update & Security -> Troubleshoot -> Windows Update]** に移動し、[開始] を **選択します**。 これにより、OS の更新に関する問題を再現しながらトレースを収集し、IT またはサポートのトラブルシューティングに役立ちます。

### <a name="prerequisites"></a>前提条件

- アプリ **設定** デバイスにインストールされ、ユーザーが使用できます。

### <a name="data-locations-access-and-retention"></a>データの場所、アクセス、リテンション期間

ユーザーがデータ収集を開始すると、ユーザーは診断情報のストレージに暗黙的に同意します。 データにアクセスできるのは、ユーザーまたはユーザーがデータを共有するユーザーのみです。

診断情報はデバイスに格納されます。 デバイスがユーザーのコンピューターに接続されている場合、情報は次のファイル内のコンピューターにも存在します。

> この PC \\ \<*HoloLens device name*> \\ Internal Storage \\ Documents Trace \\ \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> このファイル パスと名前では、 は HoloLens デバイスの名前を表し、ファイルが作成された日時 \<*HoloLens device name*> \<*ddmmyyhhmmss*> を表します。

診断情報は、ユーザーが削除するまで、これらの場所に残ります。

### <a name="view-diagnostic-report"></a>診断レポートを表示する

HoloLens 2 で MDM 診断を表示するには、WiFi アイコンを選択し、**設定** アカウントに移動して [  ->    >  **職場または学校にアクセス** する] を選択し、[**管理ログのエクスポート**] を選択します。 HoloLens は、ログファイルをアカウントに送信し、デスクトップ PC 上にその場所を表示します。

## <a name="diagnosticlog-csp"></a>DiagnosticLog CSP

モバイルデバイス管理 (MDM) 環境では、IT 管理者は[DiagnosticLog 構成サービスプロバイダー (CSP)](/windows/client-management/mdm/diagnosticlog-csp)を使用して、登録されている HoloLens デバイスの診断設定を構成できます。 IT 管理者は、登録されているデバイスからログを収集するようにこれらの設定を構成できます。

詳細を表示:
- [Windows デバイスから診断情報を収集する](/mem/intune/remote-actions/collect-diagnostics)
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

[Windows Holographic より前の動作、バージョン 20h2](hololens-release-notes.md#windows-holographic-version-20h2):
 - オフライン診断が有効になるのは、ユーザーが OOBE を使用している場合、または[System\AllowTelemetry](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry)ポリシー値が Full に設定されている場合のみです (基本は HoloLens の既定値です)。 
- オフライン診断を無効にするには、**設定 App > のプライバシー** ] ページにアクセスし、[**診断データ**] で [**基本**] を選択します。 オフライン診断がテレメトリ設定に依存するビルドでは、ログが収集されるかどうかにのみ影響します。 収集されるファイルには影響しません。
- デバイスがロックされている場合、ログは表示されません。

ビルドで[Windows Holographic、バージョン 20h2](hololens-release-notes.md#windows-holographic-version-20h2)以降:
- フォールバック診断が有効になっている場合は、対応する設定[MixedReality/FallbackDiagnostics](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)を使用して、特定の MDM ポリシーによって制御されます。
- デバイスがロックされている場合、ログは表示されません。

詳細については、次の動画をご覧ください。

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

診断を収集するには、次の手順を実行します。

1.  PC に USB ケーブルを使用してデバイスを Connect します。

2.  PC のファイルエクスプローラーで、 **' この pc \<hololens-device> \ 内部 Storage '** に移動します。

3.  **内部 Storage** フォルダーが表示されない場合、デバイスはユーザーのサインインを待機しています。 電源ボタンを10秒間押して、デバイスのサインインまたは電源を入れます。

4.  を押すと、すぐに [ **電源 + 音量** ] ボタンが一緒に解放されます。

5.  デバイスが zip アーカイブを準備するまで1分待ちます。 (HololensDiagnostics という名前の一時ファイルは、デバイスが zip アーカイブを生成している間に表示される場合があります。 このファイルにアクセスしたり保存したりしないでください。 プロセスが完了すると、zip アーカイブに置き換えられます)。

6.  エクスプローラーを最新の状態に更新し、 **' \Documents '** フォルダーに移動します。

7.  診断 ZIP ファイルをコピーし、Microsoft サポートチームと共有します。

    > [!NOTE]
    > 一部の診断 ZIP ファイルには PII が含まれている場合があります。
