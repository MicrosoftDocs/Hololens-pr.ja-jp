---
title: HoloLens の更新プログラムの管理
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
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: fa31ab20b149ab62fa59e334f6710b98f2e826ff
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284058"
---
# HoloLens の更新プログラムの管理

HoloLens は、他の Windows 10 デバイスと同じように、Windows Update を使用します。 更新プログラムが利用可能な場合は、次にデバイスに電源が入りインターネットに接続されたときに、自動的にダウンロードおよびインストールされます。 この記事では、エンタープライズ環境またはその他の管理環境で更新を管理する方法について説明します。 個別の HoloLens デバイスへの更新プログラムを管理する方法については、「[HoloLens を更新する](hololens-update-hololens.md)」を参照してください。

## 更新を自動的に管理する

### Windows Update for Business を使った更新プログラムの管理

Windows Holographic for Business では、[Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) を使用して、更新を管理することができます。 すべての HoloLens 2 デバイスは、Windows Holographic for Business を使用できます。 Windows Holographic for Business ビルド 10.0.18362.1042 またはそれ以降のビルドを使用していることを確認してください。 HoloLens (第 1 世代) のデバイスを使用している場合は、更新を管理するために [Windows Holographic for Business に更新する](hololens1-upgrade-enterprise.md)必要があります。

Windows Update for Business により、HoloLens デバイスを Windows Update サービスに直接接続します。 Windows Update for Business を使用すると、更新プロセスの複数の側面として&mdash;いつ、どのデバイスで、どの更新プログラムを取得するか、などを管理することができます。 たとえば、テスト用にデバイスのサブセットに更新プログラムをロールアウトし、後ほど残りのデバイスに更新プログラムをロールアウトすることができます。 または、更新プログラムの種類によって、異なる更新スケジュールを定義することもできます。

> [!NOTE]  
> HoloLens デバイスでは、機能更新プログラム (年に 2 回リリース) と、品質更新プログラム (月ごとまたは必要に応じてリリースされ、重要なセキュリティ更新プログラムを含む) を、自動的に管理することができます。 更新プログラムの種類の詳細については、「[Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business) で管理される更新プログラムの種類」を参照してください。

HoloLens 用の Windows Update for Business の設定は、Microsoft Intune などのモバイル デバイス管理 (MDM) ソリューションのポリシーを使用して構成することができます。

### Microsoft Intune を使った、 Windows Update for Business の管理

Intune を使用して Windows Update for Business を構成する方法の詳細については、「[Windows 10 のソフトウェア更新プログラムを Intune で管理する](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure)」を参照してください。 HoloLens でサポートされている特定の Intune 機能の詳細については、「[HoloLens がをサポートする Intune の更新プログラム管理機能](#intune-update-management-functions-that-hololens-supports)」を参照してください。

> [!IMPORTANT]  
> Intune には、更新を管理するために、*Windows 10 更新リング* と *Windows 10 機能更新プログラム*の 2 種類のポリシーがあります。 Windows 10 機能更新プログラムのポリシーの種類は、現時点ではパブリック プレビュー段階であり、HoloLens でサポートされていません。
>  
> Windows 10 更新リング ポリシーを使用して HoloLens 2 の更新を管理できます。

### HoloLens 2 または HoloLens (第 1 世代) の更新ポリシーを構成する

このセクションでは、HoloLens 2 または HoloLens (第 1 世代) の更新を管理するのに使用できるポリシーについて説明します。 HoloLens 2 向けのその他の機能の詳細については、「[HoloLens 2 の更新プログラムのロールアウトについての計画と構成](#plan-and-configure-update-rollouts-for-hololens-2)」を参照してください。

[ポリシー CSP-更新プログラム](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) は、Windows Update for Business を構成するポリシーを定義します。

> [!NOTE]  
> HoloLens の特定のエディションでサポートされているポリシー構成サービス プロバイダー (CSP) の一覧については、「[HoloLens デバイスでサポートされているポリシーの CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)」を参照してください。

#### 更新プログラムの自動チェックを構成する

**Update/AllowAutoUpdate** ポリシーを使用して、更新プログラムのスキャン、ダウンロード、インストールなど、自動更新の動作を管理できます。 このポリシーの使用可能な設定の詳細については、「[Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)」を参照してください。

> [!NOTE]  
> Microsoft Intune では、**自動更新動作**を使用して、このポリシーを変更できます  詳細については、「[Intune での Windows 10 のソフトウェア更新プログラムの管理](https://docs.microsoft.com/intune/windows-update-for-business-configure)」を参照してください。

#### 更新スケジュールを構成する

更新プログラムを適用する方法とタイミングを構成するには、次のポリシーを使用します。

- [Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - 値: **0**–**7** (0 = 毎日、1 = 日曜日、7 = 土曜日)
  - 既定値: **0** (毎日)
- [Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Values: 0–23 (0 = 午前 0:00、23 = 午後 11:00)
  - 既定値: 午後 3:00

#### アクティブ時間の構成
[Windows Holographic、Verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2)以降では、IT 管理者は HoloLens 2 デバイスのアクティブ時間の範囲を指定できます。

アクティブ時間 には、デバイスを使用している可能性の高い時間帯を指定します。 更新後の自動再起動は、アクティブ時間を除く時間帯に行われます。 指定された範囲は、アクティブ時間の開始時刻からカウントされます。 MDM を使って設定できます。詳しくは、「[MDM を使ったアクティブ時間の構成](https://docs.microsoft.com/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm)」で説明します。 MDM は、ポリシー CSP で Update/Activehours Send および Update/ActiveHoursMaxRange の設定を使用して、アクティブ時間を構成します。

-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend) - この値は終了時刻を設定します。 開始時刻から最大 12 時間まで設定できます。
    -   サポートされている値は 0 - 23 です。0は夜中の 12 時、1 は午前 1 時のようになります。
    -   既定値は 17 (午後 5 時) です。
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) -この値は、開始時刻からのアクティブ時間の最大数を設定します。
    -   サポートされている値は 8 - 18 です。
    -   既定値は 18 (時間) です。
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart) -この値は開始時刻を設定します。 終了時刻から最大 12 時間まで設定できます。
    -   サポートされている値は 0 - 23 です。0は夜中の 12 時、1 は午前 1 時のようになります。
    -   既定値は 8 (午後 8 時) です。

#### Windows 10 バージョン 1607 を実行するデバイスのみ

以下の更新ポリシーを使用して、Windows Update からではなく Windows Server Update Services (WSUS) から更新プログラムを取得するようにデバイスを構成することができます。

- [Update/AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### HoloLens 2 の更新プログラムのロールアウトについての計画と構成

HoloLens 2 は、HoloLens (第 1 世代) よりも多くの更新の自動化機能をサポートします。 Microsoft Intune を使用して Windows Update for Business のポリシーを管理する場合は、特にそうです。 これらの機能により、組織全体で行う更新プログラムのロールアウトを、より簡単に計画し、実装できるようになります。

#### 更新戦略を計画する

Windows Updates for Business は繰延ポリシーをサポートしています。 繰延ポリシーを使用して、更新プログラムがリリースされてから、どのぐらいの時間でデバイスにその更新プログラムをインストールするかを定義できます。 異なる繰延ポリシーを使用して、デバイスのサブセット (*更新リング*とも呼ばれる) を関連付けることにより、組織の更新プログラムのロールアウト戦略を調整できます。

たとえば、組織で 1,000 台のデバイスを所有していて、それを 5 つのウェーブで更新しなければならないとします。 組織では、次の表に示すような 5 つの更新リングを作成することができます。

|Group |デバイスの数 |繰延 (日数) |
| ---| :---: | :---: |
|グループ 1 (IT スタッフ) |5 |0 |
|グループ 2 (早期導入者) |50 |60 |
|グループ 3 (メイン 1) |250 |120 |
|グループ 4 (メイン 2) |300 |150 |
|グループ 5 (メイン 3) |395 |180 |

時間の経過と共に組織全体にロールアウトする方法を示します。

![更新プログラムを展開するタイムライン](./images/hololens-updates-timeline.png)

#### 更新プログラムの繰延ポリシーを構成する

繰延ポリシーにより、更新プログラムが入手可能になった日から更新プログラムをデバイスに提供する日までの日数を指定します。

機能更新プログラムと品質更新プログラムに、異なる繰延を構成できます。 次の表で、それぞれの種類に使える特定のポリシーと、それぞれの繰延の最大日数を示します。

|カテゴリ |ポリシー |保留の最長期間 |
| --- | --- | --- |
|機能更新プログラム |DeferFeatureUpdatesPeriodInDays |365 日 |
|品質更新プログラム |DeferQualityUpdatesPeriodInDays |30 日 |

#### デバイス経由で更新プログラムを一時停止する

ユーザーが MDM にアクセスできない場合は、ビルド [Windows Holographic version 2004](hololens-release-notes.md#windows-holographic-version-2004) 以降の HoloLens 2 デバイスで最大 35 日間手動で更新を個別に一時停止できます。 ユーザーは、**[設定]、[更新とセキュリティ]、[詳細オプション]** の順に移動して **[更新を一時停止]** まで下にスクロールし、更新を一時停止する日付を選択すると、この設定にアクセスできます。 ユーザーが一時停止の制限に達すると、デバイスを再び一時停止できるようにするには、新しい更新を取得する必要があります。 

[Windows Holographic verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 以降、この一時停止更新機能は HoloLens 2 デバイスで管理できます。 
- [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)。
    - 0 (既定) – 有効
    - 1– 無効

#### HoloLens でサポートされている Intune 更新プログラム管理機能

HoloLens の更新プログラムを管理するには、次の Intune 更新プログラム管理機能を使用できます。

- **作成**と**割り当て**:　これらの関数は、Windows 10 更新プログラム リングを、更新リングの一覧に追加します。 詳しくは、「[更新リングを作成して割り当てる](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)」をご覧ください。

- **一時停止**:機能更新プログラムまたは品質更新プログラムを展開するときに問題が発生した場合は、更新を (指定した日付から) 35 日間一時停止することができます。 この一時停止により、問題を解決するか、軽減するまで、他のデバイスで更新プログラムをインストールできなくなります。 機能更新プログラムを一時停止しても、品質更新プログラムは引き続きデバイスに提供され、セキュリティで保護された状態を保つことができます。 更新プログラムの種類が一時停止されると、そのリングの [概要] ウィンドウには、その種類の更新プログラムが再開するまでの日数が表示されます。 指定した時間が経過すると、一時停止が自動的に期限切れになり、更新プロセスが再開します。

  更新リングが一時停止している間、次のいずれかのオプションを選択できます。

  - **[延長]**: 35 日間の更新プログラムの種類の一時停止期間を延長します。
  - **[再開]**: そのリングの更新をアクティブな操作に復元します。 必要な場合は、更新リングを再び一時停止することができます。

  > [!NOTE]  
  > HoloLens 2 デバイスでは、更新リングに対する**アンインストール**操作はサポートされていません。

## 更新プログラムの手動での確認方法

HoloLens ではシステム更新プログラムを定期的に確認しますが、場合によっては手動で確認したいことがあるかもしれません。

更新プログラムを手動で確認するには、**[設定]** > **[更新とセキュリティ]** > **[更新プログラムのチェック]** の順に移動します。 [設定] アプリに「お使いのデバイスは最新の状態です」と表示された場合は、現在利用できるすべての更新プログラムがインストールされています。

## 更新プログラムを手動でロールバックする

場合によっては、HoloLens ソフトウェアの以前のバージョンに戻すこともできます。 HoloLens 2 を使っているか HoloLens (第 1 世代) を使っているかによって、これを行う手順が異なります。

### 以前のバージョンに戻す (HoloLens 2)

[高度な回復コンパニオン](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)を使用して HoloLens を以前のバージョンにリセットすることにより、更新プログラムをロールバックし、HoloLens 2 を以前のバージョンに戻すことができます。

> [!NOTE]
> 以前のバージョンに戻すと、個人用のファイルと設定が削除されます。

以前のバージョンの HoloLens 2 に戻すには、次の手順を実行します。

1. コンピューターにスマートフォンや Windows デバイスが接続されていないことを確認します。
1. コンピューターで、Microsoft Store から[高度な回復コンパニオン](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)をダウンロードします。
1. [最新の HoloLens 2 リリース](https://aka.ms/hololens2download)をダウンロードします。
1. これらのダウンロードが完了したら、**エクスプローラー** > **[ダウンロード]** の順に開き、ダウンロードした圧縮 (zip 形式) フォルダーを右クリックし、**[すべて展開]** > **[展開]** を選択してファイルを展開します。
1. USB-A - USB-C ケーブルを使って HoloLens デバイスをコンピューターに接続します。 HoloLens の接続に他のケーブルを使用していた場合も、この種類のケーブルが最適です。
1. 高度な回復コンパニオンでは、HoloLens デバイスが自動的に検出されます。 **[Microsoft HoloLens]** タイルを選択します。
1. 次の画面で、**[手動によるパッケージの選択]** を選択してから、先に展開しておいたフォルダーを開きます。
1. インストールファイル (.ffu) を選択します。
1. **[ソフトウェアのインストール]** を選択し、手順に従います。

### 以前のバージョンに戻す (HoloLens (第 1 世代))

[Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) を使用して HoloLens を以前のバージョンにリセットすることにより、更新プログラムをロールバックし、HoloLens (第 1 世代) を以前のバージョンに戻すことができます。

> [!NOTE]
> 以前のバージョンの HoloLens に戻すと、個人用のファイルと設定が削除されます。

以前のバージョンの HoloLens (第 1 世代) に戻すには、次の手順を実行します。

1. コンピューターにスマートフォンや Windows デバイスが接続されていないことを確認します。
1. コンピューターで、[Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) をダウンロードします。
1. [HoloLens Anniversary Update 回復パッケージ](https://aka.ms/hololensrecovery)をダウンロードします。
1. ダウンロードが完了したら、**エクスプローラー** > **[ダウンロード]** の順に開き、ダウンロードした圧縮 (zip 形式) フォルダーを右クリックし、**[すべて展開]** > **[展開]** を選択してファイルを展開します。
1. HoloLens デバイスに付属していた micro-USB ケーブルを使用して、HoloLens デバイスをコンピューターに接続します。 HoloLens デバイスの接続に他のケーブルを使用していた場合も、このケーブルが最適です。
1. WDRT により、HoloLens デバイスが自動的に検出されます。 **[Microsoft HoloLens]** タイルを選択します。
1. 次の画面で、**[手動によるパッケージの選択]** を選択してから、先に展開しておいたフォルダーを開きます。
1. インストールファイル (.ffu) を選択します。
1. **[ソフトウェアのインストール]** を選択し、手順に従います。

**WDRT でデバイスが検出されない場合**

WDRT で HoloLens デバイスが検出されない場合は、コンピューターを再起動してみてください。 それでも問題が解決しない場合は、**[デバイスが検出されませんでした]** を選択し、**[Microsoft HoloLens]** を選択して、表示される指示に従って操作します。

## 関連記事

- [HoloLens 2 のリリース ノート](https://docs.microsoft.com/hololens/hololens-release-notes)
- [Windows Update for Business とは?](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [Windows 10 更新プログラムのサービス チャネルにデバイスを割り当てる](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Intune で Windows 10 のソフトウェア更新プログラムを管理する](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
