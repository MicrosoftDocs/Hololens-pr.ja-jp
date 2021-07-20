---
title: HoloLens 更新プログラムの管理
description: 管理者は、モバイル デバイス管理を使用して HoloLens デバイスの更新プログラムを管理する方法について説明します。
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 10/13/2020
ms.reviewer: jarrettr
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 5ec26c64a971b8bfc9f8d1f9044e2e651a218816
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640000"
---
# <a name="manage-hololens-updates"></a>HoloLens 更新プログラムの管理

HoloLens は、他の Windows 10 デバイスと同じように、Windows Update を使用します。 更新プログラムが利用可能な場合は、次にデバイスに電源が入りインターネットに接続されたときに、自動的にダウンロードおよびインストールされます。 この記事では、エンタープライズ環境またはその他の管理環境で更新を管理する方法について説明します。 個別の HoloLens デバイスへの更新プログラムを管理する方法については、[「HoloLens の更新」](hololens-update-hololens.md)を参照してください。

## <a name="manage-updates-automatically"></a>更新を自動的に管理する

### <a name="managing-updates-by-using-windows-update-for-business"></a>Windows Update for Business を使って更新プログラムを管理する

Windows Holographic for Business では、[Windows Update for Business](/windows/deployment/update/waas-manage-updates-wufb) を使用して更新プログラムを管理できます。 すべての HoloLens 2 デバイスは、Windows Holographic for Business を使用できます。 Windows Holographic for Business ビルド 10.0.18362.1042 以降のビルドを使用していることを確認してください。 (第 1 世代) HoloLens のデバイスがある場合は、更新プログラムを管理するために、[Windows Holographic for Business にアップグレードする](hololens1-upgrade-enterprise.md)必要があります。

Windows Update for Business により、HoloLens デバイスを Windows Update サービスに直接接続します。 Windows Update for Business を使用すると、更新プロセス &mdash; の複数の側面として、いつ、どのデバイスで、どの更新プログラムを取得するか、などを管理することができます。 たとえば、テスト用にデバイスのサブセットに更新プログラムをロールアウトし、後ほど残りのデバイスに更新プログラムをロールアウトすることができます。 または、更新プログラムの種類によって、異なる更新スケジュールを定義することもできます。

> [!NOTE]  
> HoloLens デバイスでは、機能更新プログラム (年に 2 回リリース) と、品質更新プログラム (月ごとまたは必要に応じてリリースされ、重要なセキュリティ更新プログラムを含む) を、自動的に管理することができます。 更新プログラムの種類の詳細については、[「Windows Update for Business で管理される更新プログラムの種類」](/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)を参照してください。

HoloLens 用の Windows Update for Business の設定は、Microsoft Intune などのモバイル デバイス管理 (MDM) ソリューションのポリシーを使用して構成することができます。

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>Microsoft Intune を使って、 Windows Update for Business を管理する

Intune を使用して Windows Update for Business を構成する方法の詳細については、[「 Intune で Windows 10 ソフトウェア更新プログラムを管理」](/intune/protect/windows-update-for-business-configure)を参照してください。 HoloLens がサポートする特定の Intune 機能の詳細については、[「HoloLens がサポートする Intune 更新プログラム管理関数」](#intune-update-management-functions-that-hololens-supports)を参照してください。

> [!IMPORTANT]  
> Intune には、*Windows 10 更新リング* と *Windows 10 機能の更新プログラム* という更新プログラムを管理するための 2 種類のポリシーがあります。 Windows 10 機能更新プログラムのポリシーの種類は、現時点ではパブリック プレビュー段階であり、HoloLens でサポートされていません。
>  
> Windows 10 更新リング ポリシーを使用して HoloLens 2 の更新を管理できます。

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>HoloLens 2 または HoloLens (第 1 世代) の更新ポリシーを構成する

このセクションでは、HoloLens 2 または HoloLens (第 1 世代) の更新を管理するのに使用できるポリシーについて説明します。 HoloLens 2 で使用できる機能の詳細については、[「HoloLens 2 の更新プログラムのロールアウトの計画と構成」](#plan-and-configure-update-rollouts-for-hololens-2)を参照してください。

[ポリシー CSP - 更新プログラム](/windows/client-management/mdm/policy-csp-update) は、Windows Update for Business を構成するポリシーを定義します。

> [!NOTE]  
> HoloLens の特定のエディションでサポートされている特定のポリシー構成サービス プロバイダー (HOLOLENS) の一覧については、[「HoloLens デバイスでサポートされているポリシー CSP」](/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)を参照してください。

#### <a name="configure-automatic-checks-for-updates"></a>更新プログラムの自動チェックを構成する

**Update/AllowAutoUpdate** ポリシーを使用して、更新プログラムのスキャン、ダウンロード、インストールなど、自動更新の動作を管理できます。 このポリシーで使用できる設定の詳細については、[「Update/AllowAutoUpdate 」](/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)を参照してください。

> [!NOTE]  
> Microsoft Intune では、**自動更新動作を使用して**、このポリシーを変更できます。 詳細については、「[Intune で Windows 10 ソフトウェア更新プログラムを管理する](/intune/windows-update-for-business-configure)」を参照してください。

#### <a name="configure-an-update-schedule"></a>更新スケジュールを構成する

更新プログラムを適用する方法とタイミングを構成するには、次のポリシーを使用します。

- [Update/ScheduledInstallDay](/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - 値: **0**–**7** (0 = 毎日、1 = 日曜日、7 = 土曜日)
  - 既定値: **0** (毎日)
- [Update/ScheduledInstallTime](/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - 値: 0–23 (0 = 午前 0:00、23 = 午後 11:00)
  - 規定値: 午前 3 時

#### <a name="configure-active-hours"></a>アクティブ時間の構成
[Windows Holographic, バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2) より、IT 管理者は、HoloLens 2 デバイスのアクティブな時間の範囲を指定できます。

[アクティブ時間] によって、デバイスが使用中であると予測される期間が特定されます。 更新後の自動再起動は、アクティブ時間を除く時間帯に行われます。 指定された範囲は、アクティブ時間の開始時刻からカウントされます。 MDM を使って設定できます。詳しくは、「[MDM を使ったアクティブ時間の構成](/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm)」で説明します。 MDM では、ポリシー CSP の Update/ActiveHoursStart and Update/ActiveHoursEnd および Update/ActiveHoursMaxRange の設定を使ってアクティブ時間を構成します。

-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend) - この値は終了時刻を設定します。 開始時刻から最大 12 時間まで設定できます。
    -   サポートされている値は 0 - 23 です。0 は夜中の 12 時、1 は午前 1 時のようになります。
    -   既定値は 17 (午後 5 時) です。
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) - この値は、開始時刻からのアクティブ時間の最大時間を設定します。
    -   サポートされる値: 8-18。
    -   既定値は 18 (時間) です。
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart) - この値は開始時刻を設定します。 終了時刻から最大 12 時間まで設定できます。
    -   サポートされている値は 0 - 23 です。0 は夜中の 12 時、1 は午前 1 時のようになります。
    -   既定値は 8 (午前 8 時) です。

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Windows 10 バージョン 1607 を実行するデバイスのみ

以下の更新ポリシーを使用して、Windows Update からではなく Windows Server Update Services (WSUS) から更新プログラムを取得するようにデバイスを構成することができます。

- [Update/AllowUpdateService](/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>HoloLens 2 の更新プログラムのロールアウトについての計画と構成

HoloLens 2 は、HoloLens (第 1 世代) よりも多くの更新プログラムの自動化機能をサポートします。 Microsoft Intune を使用して Windows Update for Business のポリシーを管理する場合は、特にそうです。 これらの機能により、組織全体で行う更新プログラムのロールアウトを、より簡単に計画し、実装できるようになります。

#### <a name="plan-the-update-strategy"></a>更新戦略を計画する

Windows Updates for Business は繰延ポリシーをサポートしています。 更新プログラムがリリースされてから、繰延ポリシーを使用して、どのぐらいの時間でデバイスにその更新プログラムをインストールするかを定義できます。 異なる繰延ポリシーを使用して、デバイスのサブセット (*更新リング* とも呼ばれる) を関連付けることにより、組織の更新プログラムのロールアウト戦略を調整できます。

たとえば、組織で 1,000 台のデバイスを所有していて、それを 5 つのウェーブで更新しなければならないとします。 組織では、次の表に示すような 5 つの更新リングを作成することができます。

|Group |Number of devices (デバイス数) |繰延 (日数) |
| ---| :---: | :---: |
|グループ 1 (IT スタッフ) |5 |0 |
|グループ 2 (早期導入者) |50 |60 |
|グループ 3 (メイン 1) |250 |120 |
|グループ 4 (メイン 2) |300 |150 |
|グループ 5 (メイン 3) |395 |180 |

時間の経過と共に組織全体にロールアウトする方法を示します。

![更新プログラムを展開するタイムライン](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>更新プログラムの繰延ポリシーを構成する

繰延ポリシーにより、更新プログラムが入手可能になった日から更新プログラムをデバイスに提供する日までの日数を指定します。

機能更新プログラムと品質更新プログラムに、異なる繰延を構成できます。 次の表で、それぞれの種類に使える特定のポリシーと、それぞれの繰延の最大日数を示します。

|カテゴリ |ポリシー |延期の最長期間 |
| --- | --- | --- |
|機能更新プログラム |DeferFeatureUpdatesPeriodInDays |365 日 |
|品質に関する更新 |DeferQualityUpdatesPeriodInDays |30 日 |

#### <a name="pause-updates-via-device"></a>デバイス経由で更新プログラムを一時停止する

ユーザーが MDM にアクセスできない場合は、ビルド [Windows Holographic、バージョン 2004](hololens-release-notes.md#windows-holographic-version-2004) 以降の HoloLens 2 デバイスで最大 35 日間手動で更新を個別に一時停止できます。 この設定にたどり着くには、 **[設定] > [アップデートとセキュリティ] > [詳細] オプションから** **[アップデートを中断]** までスクロールダウンし、いつまでアップデートを中断したいのか日付を選択します。 ユーザーが一時停止の制限に達すると、デバイスを再び一時停止できるようにするには、新しい更新を取得する必要があります。 

[Windows Holographic バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2) から、この一時停止更新機能は、HoloLens 2 デバイスで管理できます。 
- [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)。
    - 0 (規定) – 有効
    - 1 - 無効

#### <a name="intune-update-management-functions-that-hololens-supports"></a>HoloLens でサポートされている Intune 更新プログラム管理機能

HoloLens の更新プログラムを管理するには、次の Intune 更新プログラム管理機能を使用できます。

- **Create** と **Assign**:　これらの関数は、Windows 10 更新プログラム リングを、更新リングの一覧に追加します。 詳細については、[「更新プログラム リングの作成 と割り当て」](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)を参照してください。

- **Pause**:機能更新プログラムまたは品質更新プログラムを展開するときに問題が発生した場合は、更新を (指定した日付から) 35 日間一時停止することができます。 この一時停止により、問題を解決するか、軽減するまで、他のデバイスで更新プログラムをインストールできなくなります。 機能更新プログラムを一時停止しても、品質更新プログラムは引き続きデバイスに提供され、セキュリティで保護された状態を保つことができます。 更新プログラムのリングが一時停止されると、そのリングの [概要] ウィンドウに、その更新プログラムの種類が再開されるまでの日数が表示されます。 指定した時間が経過すると、一時停止が自動的に期限切れになり、更新プロセスが再開します。

  更新リングが一時停止している間、次のいずれかのオプションを選択できます。

  - **Extend**: 35 日間の更新プログラムの種類の一時停止期間を延長します。
  - **Resume**: そのリングの更新をアクティブな操作に復元します。 必要な場合は、更新リングを再び一時停止することができます。

  > [!NOTE]  
  > HoloLens 2 デバイスでは、更新リングに対する **アンインストール** 操作はサポートされていません。

### <a name="delivery-optimization-preview"></a>配信の最適化のプレビュー

[Windows Holographic バージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1) では、配信の最適化設定の早期プレビューを有効にし、複数の HoloLens デバイスからのダウンロードの帯域幅消費を減らしています。 推奨されるネットワーク構成と共に、この機能の詳細な説明については、[「Windows 10 更新プログラムの配信の最適化」](/windows/deployment/update/waas-delivery-optimization)を参照してください。

次の設定は管理画面の一部として有効にされ、[Intune から構成できます](/mem/intune/configuration/delivery-optimization-settings)。

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

このプレビューの内容に関する注意点を次に示します。

- HoloLens のサポートは、このプレビューでは OS の更新プログラムにのみ制限されます。
- Windows Holographic for Business は、HTTP ダウンロード モードと [Microsoft 接続キャッシュ エンドポイント](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)からのダウンロードのみをサポートします。ピア ツー ピア のダウンロード モードとグループの割り当ては、現時点では HoloLens デバイスではサポートされていません。
- HoloLens では、Windows Server Update Services エンドポイントのデプロイまたは配信の最適化はサポートされていません。
- トラブルシューティングを行う場合は、接続キャッシュ サーバーでの診断、または **[設定]**  >  **[アップデートとセキュリティ]**  >   **[トラブルシューティング]**  >   **[Windows Update]** を介して HoloLens 上で HoloLens のトレースを収集する必要があります。

## <a name="manually-check-for-updates"></a>更新プログラムの手動での確認方法

HoloLens ではシステム更新プログラムを定期的に確認しますが、場合によっては手動で確認したいことがあるかもしれません。

更新プログラムを手動で確認するには、 **[設定]**  >  **[アップデートとセキュリティ]**  >  **[アップデートの確認]** に進みます。 [設定] アプリに「お使いのデバイスは最新の状態です」と表示された場合は、現在利用できるすべての更新プログラムがインストールされています。

## <a name="manually-roll-back-an-update"></a>更新プログラムを手動でロールバックする

場合によっては、HoloLens ソフトウェアの以前のバージョンに戻すこともできます。 HoloLens 2 を使っているか HoloLens (第 1 世代) を使っているかによって、これを行う手順が異なります。

### <a name="revert-to-a-previous-version-hololens-2"></a>以前のバージョンに戻す (HoloLens 2)

[Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) を使用して HoloLens を以前のバージョンにリセットすることにより、更新プログラムをロールバックし、HoloLens 2 を以前のバージョンに戻すことができます。

> [!NOTE]
> 以前のバージョンに戻すと、個人用のファイルと設定が削除されます。

以前のバージョンの HoloLens 2 に戻すには、次の手順を実行します。

1. コンピューターにスマートフォンや Windows デバイスが接続されていないことを確認します。
1. お使いのコンピューターで、Microsoft Storeから [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) をダウンロードします。
1. [最新の HoloLens 2 リリース](https://aka.ms/hololens2download)をダウンロードします。
1. これらのダウンロードが完了したら、**エクスプローラー** >  **[ダウンロード]** を開き、ダウンロードした圧縮 (.zip) フォルダーを右クリックし、 **[すべての抽出]**  >  **[抽出]** を選択してファイルを展開します。
1. USB-A - USB-C ケーブルを使って HoloLens デバイスをコンピューターに接続します。 HoloLens の接続に他のケーブルを使用していた場合も、この種類のケーブルが最適です。
1. Advanced Recovery Companion では、HoloLens デバイスが自動的に検出されます。 **[Microsoft HoloLens]** タイルを選択します。
1. 次の画面で、 **[手動パッケージの選択 ]** を選択し、前に展開したフォルダーを開きます。
1. インストールファイル (.ffu) を選択します。
1. **[ソフトウェアのインストール]** を選択し、指示に従います。

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>以前のバージョン (HoloLens (第 1 世代)) に戻す

[Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) を使用して HoloLens を以前のバージョンにリセットすることにより、更新プログラムをロールバックし、HoloLens (第 1 世代) を以前のバージョンに戻すことができます。

> [!NOTE]
> 以前のバージョンの HoloLens に戻すと、個人用のファイルと設定が削除されます。

以前のバージョンの HoloLens (第 1 世代) に戻すには、次の手順を実行します。

1. コンピューターにスマートフォンや Windows デバイスが接続されていないことを確認します。
1. お使いのコンピューターで、[Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) をダウンロードします。
1. [HoloLens Anniversary Update 回復パッケージ](https://aka.ms/hololensrecovery)をダウンロードします。
1. これらのダウンロードが完了したら、**エクスプローラー** >  **[ダウンロード]** を開き、ダウンロードした圧縮 (.zip) フォルダーを右クリックし、 **[すべての抽出]**  >  **[抽出]** を選択してファイルを展開します。
1. HoloLens デバイスに付属していた micro-USB ケーブルを使用して、HoloLens デバイスをコンピューターに接続します。 HoloLens デバイスの接続に他のケーブルを使用していた場合も、このケーブルが最適です。
1. WDRT により、HoloLens デバイスが自動的に検出されます。 **[Microsoft HoloLens]** タイルを選択します。
1. 次の画面で、 **[手動パッケージの選択 ]** を選択し、前に展開したフォルダーを開きます。
1. インストールファイル (.ffu) を選択します。
1. **[ソフトウェアのインストール]** を選択し、指示に従います。

**WDRT でデバイスが検出されない場合**

WDRT で HoloLens デバイスが検出されない場合は、コンピューターを再起動してみてください。 それでも機能しなかった場合は **[デバイスが検出されていない]** を選択し、 **[Microsoft HoloLens]** を選択して、指示に従います。

## <a name="related-articles"></a>関連記事

- [HoloLens 2 のリリース ノート](hololens-release-notes.md)
- [Windows Update for Business とは?](/windows/deployment/update/waas-manage-updates-wufb)
- [Windows 10 更新プログラムのサービス チャネルへデバイスを割り当てる](/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Intune で Windows 10 ソフトウェア更新プログラムを管理する](/mem/intune/protect/windows-update-for-business-configure)
