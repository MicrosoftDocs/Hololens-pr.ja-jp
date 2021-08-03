---
title: Windows Autopilot for HoloLens 2
description: HoloLens 2 デバイスで Autopilot をセットアップ、構成、およびトラブルシューティングする方法を説明します。
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/13/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Autopilot
manager: jarrettr
ms.openlocfilehash: 273dcd2180225cf953686ed1c2e5b6524996dba3
ms.sourcegitcommit: 78e5f26014e55c13fee9c2b75a80810fd2e77877
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2021
ms.locfileid: "115009359"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot for HoloLens 2

> [!NOTE]
> Microsoft エンドポイント マネージャーでの HoloLens 用 Autopilot の構成は、**パブリック プレビュー** から **一般提供** に移行中です。 すべてのテナントは、MEM 管理センターで Autopilot を設定することができるようになります。

Windows Holographic バージョン 2004 より、HoloLens 2 では Microsoft Intune を使用して Windows Autopilot [自己展開モード](/mem/autopilot/self-deploying)がサポートされています (サードパーティの MDM はサポートされていません)。 管理者は、Microsoft エンドポイント マネージャーでOut-of-box experience (OOBE) を構成できます。また、エンドユーザーは、ほとんどの操作なしで、ビジネス用のデバイスを準備することができます。 これにより、セットアップ エクスペリエンスの際に、在庫管理のオーバーヘッド、実地で使用するデバイス準備のコスト、および従業員からの通話のサポートが削減されます。 詳細については、[Windows Autopilot](/mem/autopilot/windows-autopilot) のドキュメントを参照してください。

Surface デバイスの場合と同様に、お客様が Microsoft [クラウド ソリューション プロバイダー](https://partner.microsoft.com/cloud-solution-provider)(販売店または卸売業者) と協力して、パートナー センターを通じてAutopilot サービスにデバイスに登録することをお勧めします。 デバイス登録のその他の方法については、[デバイスの追加](/mem/autopilot/add-devices)ドキュメントに説明されていますが、Microsoft のチャネル パートナーを活用すると、最も有効なエンドツーエンドのパスを確実に実現できます。



ユーザーが Autopilot の自動展開プロセスを開始すると、Autopilot が次の手順を完了します:

1. デバイスを Azure Active Directory (Azure AD) に参加させます。 Autopilot for HoloLens は、Active Directory への参加またはハイブリッド Azure AD への参加をサポートしていないことに注意してください。

1. Azure AD を使用して、デバイスを Microsoft エンドポイント マネージャー (または別の MDM サービス) に登録します。

1. デバイスを対象としたポリシー、証明書、ネットワーク プロファイル、アプリケーションをダウンロードして適用します。

1. デバイスをプロビジョニングします。

1. ユーザーにサインイン画面を提示します。

## <a name="configuring-autopilot-for-hololens-2"></a>Autopilot for HoloLens 2 を構成する

環境をセット アップするには、次の手順に従ってください:

1. [Windows Autopilot for HoloLens 2 の要件を確認します。](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [MDM の自動登録を有効にする](#2-enable-automatic-mdm-enrollment)

1. [Windows Autopilot にデバイスを登録します。](#3-register-devices-in-windows-autopilot)

1. [デバイス グループを作成します。](#4-create-a-device-group)

1. [展開プロファイルを作成します。](#5-create-a-deployment-profile)

1. [登録状態ページ (ESP) の構成を確認します。](#6-verify-the-esp-configuration)

1. [HoloLens デバイスのプロファイルの状態を確認します。](#7-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. Windows Autopilot for HoloLens 2 の要件を確認します。

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Windows Autopilot の要件に関する記事の次のセクションを確認してください。

- [ネットワークの要件](/mem/autopilot/networking-requirements)  
- [ライセンスの要件](/mem/autopilot/licensing-requirements)  
- [構成要件](/mem/autopilot/configuration-requirements)

**Windows Autopilot 自己展開モードに関する記事の「[要件](/windows/deployment/windows-autopilot/self-deploying#requirements)」のセクションを確認してください。** お客様の環境が、これらの要件に加えて、標準的な Windows Autopilot の要件を満たす必要があります。 記事の「ステップ バイ ステップ」と「検証」のセクションを確認する必要はありません。 この記事の後半の手順では、HoloLens に固有の対応する手順を示します。

デバイスを登録してプロファイルを構成する方法については、この記事の[「2.Windows Autopilot にデバイスを登録する」](#3-register-devices-in-windows-autopilot)と[「4. 展開プロファイルを作成する」](#5-create-a-deployment-profile)を参照してください。 Autopilot 自己展開モード プロファイルを構成して管理するには、[Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com)にアクセスできることを確認してください。

#### <a name="review-hololens-os-requirements"></a>HoloLens OS の要件を確認します:

- デバイスは、[Windows Holographic、バージョン 2004](hololens-release-notes.md#windows-holographic-version-2004) (build 19041.1103) 以降にインストールされている必要があります。 デバイスのビルド バージョンを確認するか、最新の OS に再フラッシュするには、[Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) と[デバイスの再フラッシュ手順](/hololens/hololens-recovery#clean-reflash-the-device)を使用します。 2020 年 9 月の後半までに配信されたデバイスには、Windows Holographic バージョン 1903 がプリインストールされていることに注意してください。 販売業者に連絡して、Autopilot 対応のデバイスが発送されていることを確認してください。

- Windows Holographic、バージョン 2004 では、イーサネット接続経由の Autopilot のみがサポートされています。 **電源を入れる前に**、「USB-C to Ethernet」アダプターを使って、HoloLens が イーサネットに接続されていることを確認します。 デバイスの起動時に、ユーザーの操作は必要ありません。 多くの HoloLens デバイスに Autopilot ロールアウトを計画している場合は、アダプター インフラストラクチャの計画を立てることをお勧めします。 USB ハブは、HoloLens でサポートされていないサードパーティ製のドライバーを追加でインストールすることを要求することが多いため、お勧めしません。

- [Windows Holographic、バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (ビルド 19041.1128) 以降では、Wi-Fi 経由の Autopilot がサポートされています。ただし、イーサネット アダプターを引き続き使用することもできます。 Wi-fi 経由で接続されているデバイスの場合、ユーザーは次のことのみを行う必要があります:

     - ハチドリのシーンに移動する
     - 言語とロケールを選ぶ
     - 視線の調整を実行
     - ネットワーク接続を確立する

- Windows Holographic、バージョン 20H2 では、 [Tenantlockdown CSP と Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot) をサポートしています。これにより、デバイスがテナントにロックされ、偶発的または故意にリセットまたはワイプが行われた場合でも、デバイスがそのテナントにバインドされたままになります。  

- デバイスがまだ Azure AD のメンバーではなく、Intune (または別の MDM システム) に登録されていないことを確認します。 Autopilot の自己展開プロセスが、次の手順を実行します。 デバイス関連のすべての情報がクリーン アップされていることを確認するには、Azure AD および Intune ポータル の両方の **デバイス** ページを確認します。 現時点では、HoloLens で [すべての対象デバイスを Autopilot に変換する] 機能はサポートされていないことに注意してください。  

### <a name="2-enable-automatic-mdm-enrollment"></a>2. MDM の自動登録を有効にする

Autopilot を正常に実行するには、Azure Portal で MDM の自動登録を有効にする必要があります。 これにより、デバイスはユーザーなしで登録できるようになります。

[Azure portal](https://portal.azure.com/#home) で、 **[Azure Active Directory]**  ->  **[モビリティ (MDM および MAM)]**  ->  **[Microsoft Intune]** を選択します。 次に、**MDM ユーザー スコープ** を構成します。 **[すべて]** を選択する必要があります。

設定の詳細については、[MDM自動登録の有効化に関する次の短いガイド](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal)または[自動登録クイック スタート ガイド](/mem/intune/enrollment/quickstart-setup-auto-enrollment)を参照してください。

### <a name="3-register-devices-in-windows-autopilot"></a>3. Windows Autopilot にデバイスを登録する

最初のセットアップの前に、お使いのデバイスが Windows Autopilot に登録されている必要があります。 デバイス登録に関する MEM ドキュメントについては、[「Autopilot へのデバイスの追加」](/mem/autopilot/add-devices)を参照してください。  

HoloLens デバイスを登録する主な方法は 3 つあります。

 - **販売業者は、注文時にパートナー センターにデバイスを登録できます。**

   > [!NOTE]  
   > これは、デバイスを Autopilot サービスに追加する際に推奨されるパスです。 [詳細については、こちらを参照してください](/mem/autopilot/partner-registration)。  

 - **サポートリクエスト [は、Microsoft に直接](hololens2-autopilot-registration-support.md) 送信できます。**
 - **ハードウェア ハッシュ (ハードウェア ID とも呼ばれる) を取得し、MEM 管理センター にデバイスを手動で登録します**。

#### <a name="obtain-hardware-hash"></a>ハードウェア ハッシュを取得する
ハードウェア ハッシュを取得するには、2 つの方法があります。
1. [サポートリクエストは、Microsoft に直接](hololens2-autopilot-registration-support.md) 送信できます。
2. これはデバイスから取得できます。 デバイスは、OOBE プロセスの間、または後ほどデバイスの所有者が診断ログの収集プロセス ( 次の手順で説明します ) を開始したときに、そのハードウェア ハッシュを CSV ファイルに記録します。 通常、デバイスの所有者がデバイスにサインインする最初のユーザーです。
     > [!WARNING]
     > 20H2 より前のビルドでは、OOBE を実行し、テレメトリが [必須] に設定されている場合、このメソッドを使用して Autopilot のハードウェア ハッシュを収集することはできません。 この方法を使用してハードウェア ハッシュを収集するには、設定 アプリを使用してテレメトリ オプションを [完全] に設定し、[プライバシー] -[診断] を選択します。

    1. HoloLens 2 デバイスを起動します。

    1. デバイスで、 **[電源]** ボタンと **[ボリューム ダウン]** ボタンを同時に押し、それらを離します。 デバイスは診断ログとハードウェア ハッシュを収集し、それらを一連の .zip ファイルに保存します。

   1. 詳細とこれを実行する方法の説明ビデオについては、[オフライン診断](hololens-diagnostic-logs.md#offline-diagnostics)を参照してください。

    1. USB-C ケーブルを使用して、コンピューターにデバイスを接続します。

    1. コンピューターで、エクスプローラーを開きます。 **[この PC]\\\<*HoloLens device name*>\\[内部ストレージ]\\[ドキュメント]** を開き、AutopilotDiagnostics.zip ファイルを見つけます。  

       > [!NOTE]  
       > .zip ファイルはすぐに使用できない場合があります。 ファイルの準備ができていない場合は、[ドキュメント] フォルダーに HoloLensDiagnostics ファイルが表示されることがあります。 ファイルの一覧を更新するには、ウィンドウを更新します。
    
    1. AutopilotDiagnostics.zip ファイルの内容を抽出します。

    1. 抽出されたファイルで、ファイル名に "DeviceHash" プレフィックスが付いた CSV ファイルを見つけます。 そのファイルをコンピューターのドライブに保存し、後でアクセスできるようにします。  

       > [!IMPORTANT]  
       > CSV ファイル内のデータには、次のヘッダーと行の形式が使用されます:
       > ```
       > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
       >```

#### <a name="register-device-through-mem"></a>MEM でデバイスを登録する

1. [Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com)で、 **[デバイス]**  >  **[Windows]**  >  **[Windows 加入契約]** を選択し、次に **Windows Autopilot 展開プログラム** 下で **[デバイス]**  >  **[インポート]** を選択します。

1. **[Windows Autopilot デバイスの追加]** で、DeviceHash CSV ファイルを選択し、 **[開く]** を選択して、 **[インポート]** を選択します。  

   > [!div class="mx-imgBorder"]
   > ![インポート コマンドを使用して、ハードウェア ハッシュをインポートします。](./images/hololens-ap-hash-import.png)

1. インポートが完了したら、 **[デバイス]**  >  **[Windows]**  >  **[Windows 加入契約]**  >  **[デバイス]**  >  **[同期]** を選択します。同期されているデバイスの数によっては、プロセスが完了するには数分かかる場合があります。 登録済みのデバイスを表示するには、 **[更新]** を選択し ます。  

   > [!div class="mx-imgBorder"]
   > ![[同期] および [更新] のコマンドを使用して、デバイスの一覧を表示します。](./images/hololens-ap-devices-sync.png)  

### <a name="4-create-a-device-group"></a>4. デバイス グループを作成する

1. [Microsoft エンドポイント　管理者センター](https://endpoint.microsoft.com)で、 **[グループ]**  >  **[新しいグループ]** を選択します。

1. **[グループの種類]** に **[セキュリティ]** を選択し、グループ名と説明を入力します。

1. **[メンバーシップの種類]** に、 **[割り当て済み]** または **[動的デバイス]** のどちらかを選択します。

1. 次のいずれかの操作を行います。  

   - 前の手順で **[メンバーシップの種類]** で **[割り当て済み]** を選択した場合は、 **[メンバー]** を選択し、Autopilot デバイスをグループに追加します。 まだ登録されていない Autopilot デバイスは、デバイスのシリアル番号をデバイス名として使用して一覧表示されます。
   - 前の手順で **[メンバーシップの種類]** で **[動的デバイス]** を選択した場合は、 **[動的デバイス メンバー]** を選択し、次のような **詳細ルール** にコードを入力します。
     - Autopilot デバイスをすべて含むグループを作成する場合は、「`(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`」と入力します
     - Intune のグループ タグ フィールドは、Azure AD デバイス上の **OrderID** 属性にマップされます。 特定のグループ タグ (Azure AD デバイス OrderID) のあるすべての Autopilot デバイスを含むグループを作成する場合は、次のように入力する必要があります。`(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - 特定の発注書 ID のあるすべての Autopilot デバイスを含むグループを作成する場合は、次のように入力します。`(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > これらのルールは、Autopilot デバイスに固有の属性を対象としています。
1. **[保存]** を選択し、 **[作成]** を選択します。

### <a name="5-create-a-deployment-profile"></a>5.展開プロファイルを作成する

1. [Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com)で、 **[デバイス]**  >  **[Windows]**  >  **[Windows 加入契約]**  >  **[Windows Autopilot 展開プロファイル]**  >  **[プロファイルの作成]**  >  **[HoloLens]** を選択します。
   ![[プロファイルの作成] ドロップダウンには、HoloLens 項目が含まれています。](./images/hololens-ap-enrollment-profiles.png)

1. プロファイル名 と説明を入力し、 **[次へ]** を選択します。  
   **HoloLens** を含む一覧が表示されます。 このオプションが表示されない場合は、[フィードバック](hololens2-autopilot.md#feedback-and-support-for-autopilot) オプションのいずれかを使用してお問い合わせください。

   > [!div class="mx-imgBorder"]
   > ![プロファイルの名前と説明を追加する](./images/hololens-ap-profile-name.png)

1. **Out-of-box experience (OOBE)** ページでは、この評価のために OOBE を効率化するようにほとんどの設定が事前に構成されています。 オプションで、次の設定を構成できます。  

   - **言語 (リージョン)** : OOBE の言語を選択します。 [HoloLens 2 用にサポートされている言語](hololens2-language-support.md)の一覧から言語を選択することをお勧めします。
   - **キーボードを自動的に構成する**: キーボードが選択した言語と一致することを確かめるには、 **[はい]** を選択します。
   - **デバイス名テンプレートを適用**: OOBE 中にデバイス名を自動的に設定するには、 **[はい]** を選択し、 **[名前を入力]** にテンプレート フレーズとプレースホルダーを入力します。たとえば、4 桁の乱数のプレフィックスと `%RAND:4%`&mdash; プレースホルダーを入力します。
     > [!NOTE]  
     > デバイス名テンプレートを使用する場合、OOBE プロセスは、デバイス名を適用した後、Azure AD にデバイスを参加させる前に、デバイスをさらに 1 回再起動します。 この再起動により、新しい名前が有効になります。  

   > [!div class="mx-imgBorder"]
   > ![OOBE の設定を構成する](./images/hololens-ap-profile-oobe.png)

1. 設定を構成したら、 **[次へ]** を選択します。
1. **[スコープ タグ]** ページ上で、このプロファイルに適用するスコープ タグをオプションで追加します。 スコープのタグの詳細については、[分散 IT のためのロールベースのアクセス制御とスコープのタグの使用](/mem/intune/fundamentals/scope-tags.md)に関するページをご覧ください。 完了したら **[次へ]** を選択します。
1. **[割り当て]** ページで、 **[割り当て先]** として **[選択したグループ]** を選択します。
1. **[選択したグループ]** で、 **[+ 含めるグループの選択]** を選択します。
1. **含めるグループの選択** の一覧で、Autopilot HoloLens デバイス用に作成したデバイス グループを選択し、 **[次へ]** を選択します。  
  
   いずれかのグループを除外する場合は、 **[含めないグループを選択]** を選択して、除外するグループを選びます。

   > [!div class="mx-imgBorder"]
   > ![プロファイルにデバイス グループを割り当てます。](./images/hololens-ap-profile-assign-devicegroup.png)

1. **[確認と作成]** ページで 設定を確認し、 **[作成]** を選択 してプロファイルを作成します。  

   > [!div class="mx-imgBorder"]
   > ![確認および作成](./images/hololens-ap-profile-summ.png)

### <a name="6-verify-the-esp-configuration"></a>6. ESP 構成を確認する

[登録状態] ページ (ESP) には、MDM 管理対象ユーザーが初めてデバイスにサインインするときに実行される完全なデバイス構成プロセスの状態が表示されます。 ESP 構成が次のようになっていることを確認し、割り当てが正しいことを確認します。  

> [!div class="mx-imgBorder"]
> ![ESP の構成](./images/hololens-ap-profile-settings.png)

### <a name="7-verify-the-profile-status-of-the-hololens-devices"></a>7. HoloLens デバイスのプロファイルの状態を確認する

1. Microsoft エンドポイント マネージャー管理センターで、 **[デバイス]**  >  **[Windows]**  >  **[Windows 加入契約]**  >  **[デバイス]** を選択します。

1. HoloLens デバイスが一覧に表示されていること、およびプロファイルの状態が **割り当て済み** であることを確認します。  

   > [!NOTE]  
   > デバイスにプロファイルが割り当てられるまで、数分かかる場合があります。  

   > [!div class="mx-imgBorder"]
   > ![デバイスとプロファイルの割り当て](./images/hololens-ap-devices-assignments.png)。

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows Autopilot for HoloLens 2 のユーザー エクスペリエンス

上記の手順が完了すると、HoloLens 2 ユーザーは次のエクスペリエンスを実行して HoloLens デバイスをプロビジョニングします。  

1. Autopilot のエクスペリエンスには、インターネット アクセスが必要です。 インターネットにアクセスするには、次のいずれかのオプションを使用してください。

    - デバイスを OOBE の Wi-Fi ネットワークに接続し、Autopilot エクスペリエンスを自動的に検出できるようにします。 これは、Autopilot エクスペリエンスが自動的に完了するまで、OOBE を操作する必要がある唯一の場合です。 既定では、HoloLens 2 は、インターネットを検出した後、Autopilot を検出するために 10 秒間待機することに注意してください。 Autopilot プロファイルが 10 秒以内に検出されない場合は、OOBE に EULA が表示されます。 このシナリオが発生した場合は、デバイスを再起動して、Autopilot の検出をもう一度試行できるようにしてください。 また、デバイスに TenantLockdown ポリシーが設定されている場合にのみ、OOBE が Autopilot を無期限に待機する場合があることにも注意してください。

    - 有線インターネット接続用の「USB-C to Ethernet」アダプターを使用してデバイスをイーサネットに接続し、HoloLens 2 に Autopilot エクスペリエンスを自動的に完了させます。

    - 無線インターネット接続用の「USB-C to Wifi」アダプターを使用してデバイスを接続し、HoloLens 2 に Autopilot エクスペリエンスを自動的に完了させます。

        > [!IMPORTANT]  
       > Autopilot 用の OOBE で Wi-Fi ネットワークを使用しようとするデバイスは、[Windows Holographic、バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2)上にある必要があります。
       >
       > イーサネット アダプターを使用するデバイスの場合、Out-of-the-Box-Experience (OOBE) を開始する前に、デバイスをネットワークに接続する必要があります。 デバイスは、最初の OOBE 画面で、Autopilot デバイスとしてプロビジョニングされているかどうかを判断します。 デバイスがネットワークに接続できない場合、またはデバイスを Autopilot デバイスとしてプロビジョニングしないことを選択した場合、後で Autopilot プロビジョニングに変更することはできません。 代わりに、デバイスを Autopilot デバイスとしてプロビジョニングするには、この手順を最初からやり直す必要があります。

1. デバイスは OOBE を自動的に起動します。 OOBE を使って操作しないでください。 何もせずにリラックスしてください。 HoloLens 2 にネットワーク接続を検出させ、OOBE が自動的に完了するようにします。 OOBE 中にデバイスが再起動される場合があります。 OOBE 画面は次のようになります。

   ![OOBE ステップ 1 ](./images/autopilot-welcome.jpg)
    ![ OOBE ステップ 2 ](./images/autopilot-step-complete.jpg)
    ![ OOBE ステップ 3](./images/autopilot-device-setup.jpg)

1. OOBE の最後に、ユーザー名とパスワードを使用してデバイスにサインインできます。

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP と Autopilot

HoloLens 2 デバイスでは、Windows Holographic のバージョン 20H2 での TenantLockdown CSP がサポートされています。 この CSP は、デバイスのリセットまたは再フラッシュ によっても、デバイスをそのテナントにロックすることによって、デバイスを組織のテナント上に保持します。

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP は、HoloLens 2 が Autopilot のみを使用して MDM 登録に関連付けられるようにします。 TenantLockdown CSP の RequireNetworkInOOBE ノードが HoloLens 2 で true または false (最初に設定された) 値に設定されると、その値は、再フラッシュ、OS 更新プログラムなどにもかかわらずデバイスに残ります。

HoloLens 2 で TenantLockdown CSP の RequireNetworkInOOBE ノードが true に設定されると、OOBE は、ネットワーク接続後、Autopilot プロファイルが正常にダウンロードおよび適用されるまで無期限に待機します。

HoloLens 2 で TenantLockdown CSP の RequireNetworkInOOBE ノードが true に設定されると、OOBE では次の操作が許可されなくなります。

- ランタイム プロビジョニングを使用したローカル ユーザーの作成 
- ランタイム プロビジョニングによる Azure AD への参加操作の実行 
- OOBE エクスペリエンスでデバイスの所有者を選択する 

#### <a name="how-to-set-this-using-intune"></a>Intune を使用してこれを設定する方法 
1. 以下に示すように、カスタム OMA URI デバイス構成プロファイルを作成し、RequireNetworkInOOBE ノードに true を指定します。
OMA-URI 値は ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE である必要があります

   > [!div class="mx-imgBorder"]
   > ![OMA-URI によるテナントのロックダウンの設定](images/hololens-tenant-lockdown.png)

1. グループを作成し、デバイス構成プロファイルをそのデバイス グループに割り当てます。

1. 前の手順で作成したグループの HoloLens 2 デバイス メンバーを作成し、同期をトリガーします。  

Intune ポータルで、デバイス構成が正常に適用されていることを確認します。 このデバイスの構成が HoloLens 2 デバイスに正常に適用されると、TenantLockdown の効果がアクティブになります。

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Intune を使用して HoloLens 2 で TenantLockdown の RequireNetworkInOOBE の設定を解除する方法

1. 上で作成したデバイス構成が以前に割り当てられていたデバイス グループから HoloLens 2 を削除します。

1. 以下に示すように、カスタム OMA URI ベースのデバイス構成プロファイルを作成し、RequireNetworkInOOBE に false を指定します。
OMA-URI 値は ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE である必要があります

   > [!div class="mx-imgBorder"]
   > ![Intune の OMA URI を介して RequireNetworkInOOBE を false に設定するスクリーンショット](images/hololens-tenant-lockdown-false.png)

1. グループを作成し、デバイス構成プロファイルをそのデバイス グループに割り当てます。 

1. 前の手順で作成したグループの HoloLens 2 デバイス メンバーを作成し、同期をトリガーします。

Intune ポータルで、デバイス構成が正常に適用されていることを確認します。 このデバイスの構成が HoloLens 2 デバイスに正常に適用されると、TenantLockdown の効果が非アクティブになります。

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>TenantLockdown が true に設定された後、HoloLens で Autopilot プロファイルが割り当て解除された場合、OOBE 中にどうなりますか? 
OOBE は、Autopilot プロファイルがダウンロードされるのを無期限に待機し、次のダイアログが表示されます。 TenantLockdown の影響を取り除くには、最初に Autopilot のみを使用してデバイスを元のテナントに登録し、TenantLockdown CSP によって導入された制限を取り除く前に、前の手順で説明したように RequireNetworkInOOBE の設定を解除する必要があります。

![ポリシーがデバイスに適用される時のデバイス内ビュー。](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a>既知の問題と制限事項

- MEM に構成されているデバイスコンテキスト ベースのアプリケーション インストールが HoloLens に適用されない問題を調査しています。 [「デバイス コンテキストとユーザー コンテキストのインストールの詳細」をご覧ください。](/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Wi-Fi 経由で Autopilot を設定しているときに、インターネット接続が最初に確立されたときに Autopilot プロファイルがダウンロードされない場合があります。 この場合、使用許諾契約書 (EULA) が提示され、ユーザーは Autopilot 以外のセットアップを続行することができます。 Autopilot による設定を再試行するには、デバイスをスリープ状態にしてから電源を入れます。または、デバイスを再起動して、もう一度お試しください。
- 現時点では、HoloLens で [すべての対象デバイスをAutopilot に変換する] 機能はサポートされていません。  

### <a name="troubleshooting"></a>トラブルシューティング

以下の記事は、Autopilot に関する問題の詳細情報を参照してトラブルシューティングを行う場合に役立つリソースです。ただし、これらの記事は、Windows 10 のデスクトップ版を使用しており、HoloLens には適用されない情報もあることにご注意ください。

- [Windows Autopilot - 既知の問題](/mem/autopilot/known-issues)
- [Microsoft Intune での Windows デバイスの登録に関する問題のトラブルシューティング](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - ポリシーの競合](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Autopilot のフィードバックとサポート

フィードバックを提供する、または問題を報告する場合は、次のいずれかの方法を使用します:

- デバイス登録のサポートについては、販売店または販売代理店にお問い合わせください。
- Windows Autopilot に関する一般的なサポートに関する問い合わせ、またはプロファイルの割り当て、グループの作成、MEM ポータルコントロールのような問題については、[Microsoft エンドポイント マネージャーのサポートにお問い合わせください](/mem/get-support)  
- デバイスが Autopilot サービスに登録されていて、プロファイルが MEM ポータルに割り当てられている場合は、HoloLens の[サポート](/hololens/)にお問い合わせください (「サポートカード」を参照してください)。 サポート チケットを開いて、(該当する場合は)Out-of-box-experience (OOBE) 中に [オフライン診断ログ](hololens-diagnostic-logs.md#offline-diagnostics) をキャプチャして、 スクリーンショットとログを追加します。
- デバイスから問題を報告するには、HoloLens でフィードバック Hub アプリを使用します。 フィードバック Hub で **[エンタープライズ管理]**  >  **[デバイス]** カテゴリを選択します。
- Autopilot for HoloLens に関する一般的なフィードバックを提供するには、この[アンケート](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)を提出してください

## <a name="delete-autopilot-devices"></a>Autopilot デバイスを削除する

Autopilot にデバイスを使用したり、デバイスを別のテナントに登録したりする必要がなくなります。 この場合は、[Autopilot デバイスの削除](/mem/autopilot/add-devices#delete-autopilot-devices)に関する記事を参照してください。