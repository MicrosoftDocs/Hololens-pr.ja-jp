---
title: HoloLens の更新プログラムの管理
description: 管理者は、モバイル デバイス管理を使用して HoloLens デバイスの更新プログラムを管理できます。
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 03/24/2020
ms.reviewer: jarrettr
manager: jarrettr
ms.custom:
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: f8d0c788756b0a24ac8a26b8258b267483f1a890
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857755"
---
# HoloLens の更新プログラムの管理

HoloLens は、他の Windows 10 デバイスと同じように、Windows Update を使用します。 更新プログラムが利用可能な場合は、次にデバイスに電源が入りインターネットに接続されたときに、自動的にダウンロードおよびインストールされます。 この記事では、エンタープライズ環境またはその他の管理環境で更新を管理する方法について説明します。 個別の HoloLens デバイスへの更新の管理については、「[HoloLens を更新する](hololens-update-hololens.md)」を参照してください。

## 更新を自動的に管理する

Windows Holographic for Business では、[Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) を使用して、更新を管理することができます。 すべての HoloLens 2 デバイスは、Windows Holographic for Business を使用できます。 Windows Holographic for Business ビルド 10.0.18362.1042 またはそれ以降のビルドを使用していることを確認してください。 HoloLens (第 1 世代) のデバイスを使用している場合は、更新を管理するために [Windows Holographic for Business に更新する](hololens1-upgrade-enterprise.md)必要があります。

Windows Update for Business により、HoloLens デバイスを Windows Update サービスに直接接続します。 Windows Update for Business を使用すると、更新プロセスの複数の側面として&mdash;いつ、どのデバイスで、どの更新プログラムを取得するか、などを管理することができます。 たとえば、テスト用にデバイスのサブセットに更新プログラムをロールアウトし、後日残りのデバイスに更新プログラムをロールアウトすることができます。 または、更新プログラムの種類によって、異なる更新スケジュールを定義することもできます。

> [!NOTE]  
> HoloLens デバイスでは、機能更新プログラム (年に 2 回リリース) と、品質更新プログラム (月ごとまたは必要に応じてリリースされ、重要なセキュリティ更新プログラムを含む) を、自動的に管理することができます。 更新プログラムの種類の詳細については、「[Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business) で管理される更新プログラムの種類」を参照してください。

HoloLens 用の Windows Update for Business の設定は、Microsoft Intune などのモバイル デバイス管理 (MDM) ソリューションのポリシーを使用して構成することができます。

Intune を使用して Windows Update for Business を構成する方法の詳細については、「[Windows 10 のソフトウェア更新プログラムを Intune で管理する](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure)」を参照してください。

> [!IMPORTANT]  
> Intune には、更新を管理するために、*Windows 10 更新リング* と *Windows 10 機能更新プログラム*の 2 種類のポリシーがあります。 Windows 10 機能更新プログラムのポリシーの種類は、現時点ではパブリック プレビュー段階であり、HoloLens でサポートされていません。
>  
> Windows 10 更新リング ポリシーを使用して HoloLens 2 の更新を管理できます。

### HoloLens 2 または HoloLens (第 1 世代) の更新ポリシーを構成する

このセクションでは、HoloLens 2 または HoloLens (第 1 世代) の更新を管理するのに使用できるポリシーについて説明します。 HoloLens 2 向けのその他の機能の詳細については、「[HoloLens 2 の更新プログラムのロールアウトについての計画と構成](#plan-and-configure-update-rollouts-for-hololens-2)」を参照してください。

[ポリシー構成サービス プロバイダー (CSP)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) は、Windows Update for Business を構成するポリシーを定義します。

> [!NOTE]  
> HoloLens の特定のエディションでサポートされている特定のポリシーの詳細については、「[HoloLens デバイスでサポートされているポリシー](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-hololens-devices)」を参照してください。

#### 更新プログラムの自動チェックを構成する

**Update/AllowAutoUpdate** ポリシーを使用して、更新プログラムのスキャン、ダウンロード、インストールなど、自動更新の動作を管理できます。

このポリシーでは、次の値をサポートします。

- **0** - デバイスに適用されるダウンロード可能な更新プログラムがある場合にユーザーに通知します。
- **1** - 更新プログラムを自動的にインストールし、デバイスの再起動をスケジュールするように、ユーザーに通知します。  
- **2** - 更新プログラムを自動的にインストールしてから、デバイスを再起動します。 これは推奨値であり、このポリシーの既定値です。  

- **3** - 更新プログラムを自動的にインストールしてから、指定の時間にデバイスを再起動します。 インストールの日付と時刻を指定します。 日付と時刻を指定しない場合、既定値は毎日午前 3 時になります。  

- **4** - 更新プログラムを自動的にインストールしてから、デバイスを再起動します。 このオプションでは、[設定] ページが読み取り専用に設定されます。

- **5** - 自動更新を無効にします。

このポリシーの使用可能な設定の詳細については、「[Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)」を参照してください。

> [!NOTE]  
> Microsoft Intune では、**自動更新動作**を使用して、このポリシーを変更できます  詳細については、「[Microsoft Intune でのソフトウェア更新プログラムの管理](https://docs.microsoft.com/intune/windows-update-for-business-configure)」を参照してください。

#### 更新スケジュールを構成する

更新プログラムを適用する方法とタイミングを構成するには、次のポリシーを使用します。

- [Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)。  
   - 値: **0**–**7** (0 = 毎日、1 = 日曜日、7 = 土曜日)
   - 既定値: **0** (毎日)
- [Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)。
   - Values: 0–23 (0 = 午前 0:00、23 = 午後 11:00)
   - 既定値: 午後 3:00

#### Windows 10 バージョン 1607 を実行するデバイスのみ

以下の更新ポリシーを使用して、Windows Update ではなく Windows Server Update Services (WSUS) から更新プログラムを取得するようにデバイスを構成することができます。

- [Update/AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### HoloLens 2 の更新プログラムのロールアウトについての計画と構成

HoloLens 2 は、HoloLens (第 1 世代) よりも多くの更新の自動化機能をサポートします。 Microsoft Intune を使用して Windows Update for Business のポリシーを管理する場合は、特にそうです。 これらの機能により、組織全体で行う更新プログラムのロールアウトを、より簡単に計画し、実装できるようになります。

#### 更新戦略を計画する

Windows Updates for Business は繰延ポリシーをサポートしています。 繰延ポリシーを使用して、更新プログラムがリリースされてから、どのぐらいの時間でデバイスにその更新プログラムをインストールするかを定義できます。 異なる繰延ポリシーを使用して、デバイスのサブセット (*更新リング*とも呼ばれる) を関連付けることにより、組織の更新プログラムのロールアウト戦略を調整できます。

たとえば、組織で 1000 台のデバイスを所有していて、それを 5 通りの方法で更新しなければならないとします。 組織では、次の表に示すような 5 つの更新リングを作成することができます。

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

####  例: Intune を使用して更新を管理する

**例 1: 更新リングを作成して割り当てる**

この例の詳細版については、「[更新リングの作成と割り当て](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)」を参照してください。

1. [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)にサインインし、Intune プロファイルに移動します。
1. **[ソフトウェアの更新]** > **[Windows 10 更新リング]** > **[作成]** の順に選択します。
1. **[基本事項]** で、名前と説明 (省略可能) を指定し、**[次へ]** を選択します。
1. **[更新リングの設定]** の **[サービス チャネル]** で、**[半期チャネル]** を選択し、**[機能更新プログラムの繰延期間]** を **120** に変更します。 **[次へ]** を選択します。
1. **[割り当て]** で、**[+ 含めるグループを選択する]** を選択し、1 つまたは複数のグループに更新リングを割り当てます。 **[+ 除外するグループを選択する]** を使って、割り当てを微調整します。 **[次へ]** を選択します。
1. **[確認 + 作成]** で設定を確認します。 更新リングの構成を保存する準備ができたら、**[作成]** を選択します。

更新リングの一覧に、新しい Windows 10 更新リングが表示されます。

**例 2: 更新リングを一時停止する**

機能更新プログラムまたは品質更新プログラムを展開するときに問題が発生した場合は、更新を (指定した日付から) 35 日間一時停止することができます。 この一時停止により、問題を解決するか、軽減するまで、他のデバイスで更新プログラムをインストールできなくなります。 機能更新プログラムを一時停止しても、品質更新プログラムは引き続きデバイスに提供され、セキュリティで保護された状態を保つことができます。 指定した時間が経過すると、一時停止が自動的に期限切れになります。 その時点で更新プロセスが再開します。

Intune で更新リングを一時停止するには、次の手順を実行します。

1. 更新リングの概要ページで、**[一時停止]** を選択します。
1. 一時停止する更新プログラムの種類 (**機能**または**品質**) を選択し、**[OK]** を選択します。

更新プログラムの種類が一時停止されると、そのリングの [概要] ウィンドウには、その種類の更新プログラムが再開するまでの日数が表示されます。

更新リングが一時停止している間、次のいずれかのオプションを選択できます。

- 35 日間の更新プログラムの種類の一時停止期間を延長するには、**[延長]** を選択します。
- そのリングの更新をアクティブな操作に復元するには、**[再開]** を選択します。 必要な場合は、更新リングを再び一時停止することができます。

> [!NOTE]  
> HoloLens 2 デバイスでは、更新リングに対する**アンインストール**操作はサポートされていません。

## 更新プログラムの手動での確認方法

HoloLens ではシステム更新プログラムを定期的に確認するので、手動で確認する必要はありませんが、場合によっては手動で確認したいことがあるかもしれません。

更新プログラムを手動で確認するには、**[設定]** > **[更新とセキュリティ]** > **[更新プログラムのチェック]** の順に移動します。 [設定] アプリに「お使いのデバイスは最新の状態です」と表示された場合は、現在利用できるすべての更新プログラムがインストールされています。

## 更新プログラムを手動で元に戻す

場合によっては、HoloLens ソフトウェアの以前のバージョンに戻すこともできます。 HoloLens 2 を使っているか HoloLens (第 1 世代) を使っているかによって、これを行う手順が異なります。

### 以前のバージョンに戻す (HoloLens 2)

高度な回復コンパニオンを使用して HoloLens を以前のバージョンにリセットすることにより、更新プログラムをロールバックし、HoloLens 2 を以前のバージョンに戻すことができます。

> [!NOTE]
> 以前のバージョンに戻すと、個人用のファイルと設定が削除されます。

以前のバージョンの HoloLens 2 に戻すには、次の手順を実行します。

1. コンピューターにスマートフォンや Windows デバイスが接続されていないことを確認します。
1. コンピューターで、Microsoft Store から[高度な回復コンパニオン](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)をダウンロードします。
1. [最新の HoloLens 2 リリース](https://aka.ms/hololens2download)をダウンロードします。
1. ダウンロードが完了したら、**エクスプローラー** > **[ダウンロード]** の順に開き、ダウンロードした圧縮 (zip 形式) フォルダーを右クリックし、**[すべて展開]** > **[展開]** を選択してファイルを展開します。
1. USB-A - USB-C ケーブルを使って HoloLens デバイスをコンピューターに接続します。 HoloLens の接続に他のケーブルを使用していた場合も、この種類のケーブルが最適です。
1. 高度な回復コンパニオンでは、HoloLens デバイスが自動的に検出されます。 **[Microsoft HoloLens]** タイルを選択します。
1. 次の画面で、**[手動によるパッケージの選択]** を選択してから、先に展開しておいたフォルダーを開きます。 
1. インストール ファイル (拡張子が .ffu のファイル) を選択します。
1. **[ソフトウェアのインストール]** を選択し、手順に従います。

### 以前のバージョンに戻す (HoloLens (第 1 世代))

Windows Device Recovery Tool を使用して HoloLens を以前のバージョンにリセットすることにより、更新プログラムをロールバックし、HoloLens (第 1 世代) を以前のバージョンに戻すことができます。

> [!NOTE]
> 以前のバージョンに戻すと、個人用のファイルと設定が削除されます。

以前のバージョンの HoloLens (第 1 世代) に戻すには、次の手順を実行します。

1. コンピューターにスマートフォンや Windows デバイスが接続されていないことを確認します。
1. コンピューターで、[Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) をダウンロードします。
1. [HoloLens Anniversary Update 回復パッケージ](https://aka.ms/hololensrecovery)をダウンロードします。
1. ダウンロードが完了したら、**エクスプローラー** > **[ダウンロード]** の順に開き、ダウンロードした圧縮 (zip 形式) フォルダーを右クリックし、**[すべて展開]** > **[展開]** を選択してファイルを展開します。
1. HoloLens デバイスに付属していた micro-USB ケーブルを使用して、HoloLens デバイスをコンピューターに接続します。 HoloLens デバイスの接続に他のケーブルを使用していた場合も、このケーブルが最適です。
1. WDRT により、HoloLens デバイスが自動的に検出されます。 **[Microsoft HoloLens]** タイルを選択します。
1. 次の画面で、**[手動によるパッケージの選択]** を選択してから、先に展開しておいたフォルダーを開きます。 
1. インストール ファイル (拡張子が .ffu のファイル) を選択します。
1. **[ソフトウェアのインストール]** を選択し、手順に従います。

> [!NOTE]
> WDRT で HoloLens デバイスが検出されない場合は、コンピューターを再起動してみてください。 それでも問題が解決しない場合は、**[デバイスが検出されませんでした]** を選択し、**[Microsoft HoloLens]** を選択して、表示される指示に従って操作します。

## 関連記事

- [Windows Update for Business を使った更新プログラムの展開](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [Windows 10 更新プログラムのサービス チャネルにデバイスを割り当てる](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Intune で Windows 10 のソフトウェア更新プログラムを管理する](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
