---
title: Windows Autopilot for HoloLens 2 (プライベート プレビュー)
description: ''
author: Teresa-Motiv
ms.author: v-tea
ms.date: 4/10/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Autopilot
manager: jarrettr
ms.openlocfilehash: 33463685818c3e864c698160776c76ec7d8cbefd
ms.sourcegitcommit: 9197b9d507d8b9b195bdf512d1b832888b53162d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "10899109"
---
# Windows Autopilot for HoloLens 2

Windows Autopilot プログラムに HoloLens 2 デバイスをセットアップするときに、ユーザーはシンプルなプロセスに従ってクラウドからデバイスをプロビジョニングできます。

この Autopilot プログラムは、HoloLens 2 デバイスをテナント下に共有デバイスとしてプロビジョニングする Autopilot 自己展開モードをサポートしています。 自己展開モードでは、プロビジョニング プロセス中に、デバイスのプレインストールされた OEM イメージとドライバーが利用されます。 ユーザーは、デバイスを設置せず、かつ Out-of-the-box Experience (OOBE) を使用せずにデバイスをプロビジョニングできます。 Windows 10 の Windows Autopilot の詳細については、[ここを](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) クリックしてください。

ユーザーが Autopilot の自己展開プロセスを開始すると、プロセスは次の手順を完了します。

1. デバイスを Azure Active Directory (Azure AD) に参加させます。
   > [!NOTE]  
   > Autopilot for HoloLens は、Active Directory への参加または Hybrid Azure AD への参加をサポートしていません。
1. Azure AD を使用して、Microsoft Intune (または別の MDM サービス) にデバイスを登録します。
1. デバイスを対象にしたポリシー、ユーザーに対象を絞ったアプリケーション、証明書、ネットワーク プロファイルをダウンロードします。
1. デバイスをプロビジョニングします。
1. ユーザーにサインイン画面を提示します。

## Windows Autopilot for HoloLens 2 プライベート プレビュー

次の手順に従って、プライベート プレビューの環境を設定してください:

1. Windows Autopilot for HoloLens 2 の要件を満たしていることを確認する
1. Windows Autopilot for HoloLens 2 プライベート プレビュー プログラムに登録する
1. テナントがフライトされている (プログラムに参加するために登録されている) ことを確認する
1. Windows Autopilot にデバイスを登録する
1. デバイス グループを作成する
1. 展開プロファイルを作成する
1. ESP 構成を確認する
1. HoloLens デバイスのカスタム構成プロファイルを構成する (既知の問題)
1. HoloLens デバイスのプロファイルの状態を確認する


### 1. Windows Autopilot for HoloLens 2 の要件を満たしていることを確認する

**Windows Autopilot の要件に関する記事の次のセクションを確認してください。**

- [ネットワーク要件](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)  
- [ライセンスの要件](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#licensing-requirements)  
- [構成要件](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#configuration-requirements)

**Windows Autopilot 自己展開モードに関する記事の "[要件](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" のセクションを確認してください。** お客様の環境が、これらの要件に加えて、標準的な Windows Autopilot の要件を満たす必要があります。 記事の "ステップ バイ ステップ" と "検証" のセクションを確認する必要はありません。 この記事の後半の手順では、HoloLens に固有の対応する手順を示します。 デバイスを登録して、プロファイルを構成する方法については、この記事の「[4. Windows Autopilot にデバイスを登録する](#4-register-devices-in-windows-autopilot)」および「[6. 展開プロファイルを作成する](#6-create-a-deployment-profile)」をご覧ください。 これらのセクションでは、HoloLens に固有の手順について説明します。

> [!IMPORTANT]  
> 他の Windows Autopilot プログラムとは異なり、Windows Autopilot for HoloLens 2 には、特定のオペレーティング システムの要件があります。 Autopilot は、HoloLens デバイスにプレインストールされている Windows Holographic バージョン 2004 (ビルド 19041.1103 以降) に依存します。 2020 年 8 月下旬までに出荷されたデバイスには、Windows Holographic バージョン 1903 がプレインストールされています。 Autopilot 対応デバイスをいつ出荷できるかについては、販売代理店にお問い合わせください。 プライベート プレビューに参加する場合は、以下の手順と要件を確認してください。

**Autopilot プレビューを試す場合は、OOBE とプロビジョニング プロセスを開始する前に、HoloLens デバイスが次の要件を満たしていることを確認します:**

- [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) を使用して、最新の OS (Windows Holographic バージョン 2004 (ビルド 19041.1103 以降)) を手動でインストールする必要があります。 手順は [ここに](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device) あります。 
- Windows Autopilot にデバイスを登録する必要があります。 デバイスを登録する方法については、[「4. Windows Autopilot にデバイスを登録する」](#4-register-devices-in-windows-autopilot) を参照してください。 
- 現在のリリースでは、HoloLens をオンにし、Autopilot プロビジョニング プロセスを開始する前に、デバイスをインターネットに接続する必要があります。 有線インターネット接続用の「USB-C to Ethernet」アダプターを使用して、デバイスをイーサネットに接続します。 
- デバイスは、まだ Azure AD のメンバーではなく、Intune (または別の MDM システム) に登録されていません。 Autopilot の自己展開プロセスが、次の手順を実行します。 デバイス関連のすべての情報がクリーン アップされていることを確認するには、Azure AD および Intune Portal の両方の **[デバイス]** ページを確認します。
- Autopilot の自己展開モードプロファイルを構成および管理するには、[Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com)にアクセスできることをご確認ください。


### 2. Windows Autopilot for HoloLens 2 プログラムに登録する

**プログラムに参加するには、プライベート プレビュー プログラムにテナントを登録して、Autopilot の HoloLens 固有の Intune UI コントロールを取得する必要があります。** これを行うには、[Windows Autopilot for HoloLens のプライベート プレゼンテーションモード要求](https://aka.ms/APHoloLensTAP)にアクセスするか、次の QR コードを使用して要求を提出します。  

![Autopilot QR コード](./images/hololens-ap-qrcode.png)  

この要求では、次の情報を提供してください。

- テナント ドメイン
- テナント ID
- この評価に参加している HoloLens 2 デバイスの数
- Autopilot の自己展開モードを使用して展開する予定の HoloLens 2 デバイスの数

### 3. テナントがフライトされていることを確認する

要求を提出した後、Autopilot プログラムに対してテナントがフライトされていることを確認するには、次の手順を実行します。

1. [Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com)にサインインします。
1. **[デバイス]**  >  **[Windows]**  >  **[Windows の登録]**  >  **[Windows Autopilot 展開プロファイル]**  >  **[プロファイルの作成 **]の順に選択します。  
   
   ![[プロファイルの作成] ドロップダウンには、HoloLens 項目が含まれています。](./images/hololens-ap-enrollment-profiles.png)
  **HoloLens** を含む一覧が表示されます。 このオプションが表示されない場合は、[[フィードバック]](#feedback) オプションのいずれかを使用してお問い合わせください。

### 4. Windows Autopilot にデバイスを登録する

準備フェーズには、デバイスを Windows Autopilot に登録する主な方法が 2 つあります: 

1. **デバイスの登録を注文する場合は、販売代理店またはリセラーに連絡してください**、または
2. **ハードウェア ハッシュ (ハードウェア ID とも呼ばれる) を取得し、デバイスを手動で登録します。** 

デバイス登録の詳細については、[「Autopilot にデバイスを追加する」](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices) の文書を確認してください。  

**デバイス ハードウェア ハッシュを取得する**

デバイスは、OOBE プロセスの間に、またはデバイスの所有者が診断ログの収集プロセスを開始するときに、CSV ファイルにハードウェア ハッシュを 記録できます (次の手順を参照)。 通常、デバイスの所有者がデバイスにサインインする最初のユーザーです。

1. HoloLens 2 デバイスを起動します。
1. デバイスで、[電源] ボタンと [音量を下げる] ボタンを同時に押して離します。 デバイスは診断ログとハードウェア ハッシュを収集し、それらを一連の .zip ファイルに保存します。
1. USB-C ケーブルを使用して、コンピューターにデバイスを接続します。
1. コンピューターで、エクスプローラーを開きます。 **この PC\\\<*HoloLens device name*>\\Internal Storage\\Documents** を開き、AutopilotDiagnostics.zip ファイルを見つけます。  

   > [!NOTE]  
   > .zip ファイルはすぐに使用できない場合があります。 ファイルの準備ができていない場合は、[ドキュメント] フォルダーに HoloLensDiagnostics ファイルが表示されることがあります。 ファイルの一覧を更新するには、ウィンドウを更新します。

1. AutopilotDiagnostics.zip ファイルの内容を抽出します。
1. 抽出されたファイルで、ファイル名に "DeviceHash" プレフィックスが付いた CSV ファイルを見つけます。 そのファイルをコンピューターのドライブに保存し、後でアクセスできるようにします。  
   > [!IMPORTANT]  
   > CSV ファイル内のデータには、次のヘッダーと行の形式が使用されます。
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

**Windows Autopilot にデバイスを登録する**

1. Microsoft エンドポイント マネージャー管理センターで、**[デバイス]**  >  **[Windows]**  >  **[Windows の登録]** を選択し、**[Windows Autopilot 展開プログラム]** の下の **[デバイス]**  >  **[インポート]** を選択します。

1. **[Windows Autopilot デバイスの追加]** の下で、DeviceHash CSV ファイルを選択し、**[開く]** を選択して、**[インポート]** を選択します。  
   
   ![インポート コマンドを使用して、ハードウェア ハッシュをインポートします。](./images/hololens-ap-hash-import.png)
1. インポートが完了したら、**[デバイス]**  >  **[Windows]**  >  **[Windows の登録]**  >  **[デバイス]**  >  **[同期]**] の順に選択します。同期するデバイスの数によっては、プロセスが完了するまでに数分かかる場合があります。 登録済みのデバイスを表示するには、**[更新]** を選択し ます。  
   
   ![[同期] および [更新] コマンドを使用して、デバイスの一覧を表示します。](./images/hololens-ap-devices-sync.png)  

### 5. デバイス グループを作成する

1. Microsoft エンドポイント マネージャー管理センターで、**[グループ]**  >  **[新しいグループ]** を選択します。
1. **[グループの種類]** で、**[セキュリティ]** を選択し、グループの名前と説明を入力します。
1. **[メンバーシップの種類]** で、**[割り当て済み]** または **[動的デバイス]** のいずれかを選択します。
1. 次のいずれかの操作を行います。  
   
   - 前の手順で **[メンバーシップの種類]** に **[割り当て済み]** を選択した場合は、**[メンバー]** を選択し、グループに Autopilot デバイスを追加します。 まだ登録されていない Autopilot デバイスは、デバイスのシリアル番号をデバイス名として使用して一覧表示されます。
   - 前の手順で **[メンバーシップの種類]** に **[動的デバイス]** を選択した場合は、**[動的デバイス メンバー]** を選択し、**[詳細ルール]** に次のようなコードを入力します。
     - Autopilot デバイスをすべて含むグループを作成する場合は、次のように入力します。 `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Intune のグループ タグ フィールドは、Azure AD デバイスの **OrderID** 属性にマッピングされます。 特定のグループ タグ (Azure AD デバイス OrderID) のあるすべての Autopilot デバイスを含むグループを作成する場合は、次のように入力する必要があります。 `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - 特定の発注書 ID のあるすべての Autopilot デバイスを含むグループを作成する場合は、次のように入力します。 `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > これらのルールは、Autopilot デバイスに固有の属性を対象としています。
1. **[保存]** を選択し、**[作成]** を選択します。

### 6. 展開プロファイルを作成する

1. Microsoft エンドポイント マネージャー管理センターで、**[デバイス]**  >  **[Windows]**  >  **[Windows の登録]**  >  **[Windows Autopilot 展開プロファイル]**  >  **[プロファイルの作成]**  >  **[HoloLens]** の順に選択します。
1. [プロファイル名] と [説明] を入力し、**[次へ]** を選択します。  
   
   ![プロファイルの名前と説明を追加する](./images/hololens-ap-profile-name.png)
1. **[Out-of-box experience (OOBE)]** ページでは、ほとんどの設定が、この評価のために OOBE を合理化するように構成されています。 オプションで、次の設定を構成できます。  

   - **言語 (地域)**: OOBE の言語を選択します。 [[HoloLens 2 でサポートされている言語]](hololens2-language-support.md) の一覧から言語を選択することをお勧めします。
   - **キーボードを自動的に構成する**: キーボードが選択した言語と一致するかどうかを確認するには、**[はい]** を選択します。
   - **デバイス名テンプレートの適用**: OOBE 中にデバイス名を自動的に設定するには、**[はい]** を選択し、**[名前の入力]** にテンプレート フレーズとプレースホルダーを入力します。たとえば、4 桁の乱数のプレフィックスと`%RAND:4%`&mdash;プレースホルダーを入力します。
     > [!NOTE]  
     > デバイス名テンプレートを使用する場合、OOBE プロセスは、デバイス名を適用した後、Azure AD にデバイスを参加させる前に、デバイスをさらに 1 回再起動します。 この再起動により、新しい名前が有効になります。  

   ![OOBE の設定を構成する](./images/hololens-ap-profile-oobe.png)
1. 設定を構成したら、**[次へ]** を選択します。
1. **[スコープ タグ]** ページで、オプションで、このプロファイルに適用するスコープ タグを追加します。 スコープ タグの詳細については、「[分散型 IT に役割ベースのアクセス制御とスコープ タグを使用する](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md)」をご覧ください。 完了したら、**[次へ]** を選択します。
1. **[割り当て]** ページで、**[割り当て先]** に **[選択したグループ]** を選択します。
1. **[選択したグループ]** で、**[+ 含めるグループを選択]** を選択します。
1. **[含めるグループを選択]** の一覧で、Autopilot HoloLens デバイス用に作成したデバイス グループを選択し、**[次へ]** を選択します。  
  
   グループを除外する場合は、**[除外するグループを選択]** を選択し、除外するグループを選択します。

   ![プロファイルにデバイス グループを割り当てます。](./images/hololens-ap-profile-assign-devicegroup.png)
1. **[レビュー + 作成]** ページで、設定を確認し、**[作成]** を作成してプロファイルを作成します。  
   
   ![レビュー + 作成](./images/hololens-ap-profile-summ.png)

### 7. ESP 構成を確認する

[登録状態] ページ (ESP) には、MDM 管理対象ユーザーが初めてデバイスにサインインするときに実行される完全なデバイス構成プロセスの状態が表示されます。 ESP 構成が次のようになっていることを確認し、割り当てが正しいことを確認します。  

![ESP の構成](./images/hololens-ap-profile-settings.png)

### 8. HoloLens デバイスのプロファイルの状態を確認する

1. Microsoft エンドポイント マネージャー管理センターで、**[デバイス]**  >  **[Windows]**  >  **[Windows の登録]**  >  **[デバイス]** の順に選択します。
1. HoloLens デバイスが一覧に表示されていること、およびプロファイルの状態が**割り当て済み**であることを確認します。  
   > [!NOTE]  
   > デバイスにプロファイルが割り当てられるまで、数分かかる場合があります。  
   
   ![デバイスとプロファイルの割り当て。](./images/hololens-ap-devices-assignments.png)

## Windows Autopilot for HoloLens 2 のユーザー エクスペリエンス

上記の手順が完了すると、HoloLens 2 のユーザーは、次のようにして HoloLens デバイスをプロビジョニングします:  

1. 前述のように、現在のリリースでは、HoloLens をオンにし、Autopilot プロビジョニング プロセスを開始する前に、デバイスをインターネットに接続する必要があります。 有線インターネット接続には「USB-C to Ethernet」アダプターを、無線インターネット接続には「USB-C to Wifi」アダプターを使用して、デバイスを Ethernet に接続します。
   
   > [!IMPORTANT]  
   > Out-of-the-Box-Experience (OOBE) を開始する前に、ネットワークにデバイスを接続する必要があります。 デバイスは、最初の OOBE 画面で、Autopilot デバイスとしてプロビジョニングされているかどうかを判断します。 デバイスがネットワークに接続できない場合、またはデバイスを Autopilot デバイスとしてプロビジョニングしないことを選択した場合、後で Autopilot プロビジョニングに変更することはできません。 代わりに、デバイスを Autopilot デバイスとしてプロビジョニングするには、この手順を最初からやり直す必要があります。

1. デバイスは OOBE を自動的に起動します。 OOBE を使って操作しないでください。 何もせずにリラックスしてください。 HoloLens 2 にネットワーク接続を検出させ、OOBE が自動的に完了するようにします。 OOBE 中にデバイスが再起動される場合があります。 OOBE 画面は次のようになります。
   
   ![OOBE 手順 1](./images/hololens-ap-uex-1.png)
   ![OOBE 手順 2](./images/hololens-ap-uex-2.png)
   ![OOBE 手順 3](./images/hololens-ap-uex-3.png)
   ![OOBE 手順4](./images/hololens-ap-uex-4.png)

1. OOBE の最後に、ユーザー名とパスワードを使用してデバイスにサインインできます。

  ![OOBE 手順 5](./images/hololens-ap-uex-5.png)

## 既知の問題

- デバイス セキュリティ コンテキストを使うアプリケーションをインストールすることはできません。

## フィードバック

フィードバックを提供する、または問題を報告する場合は、次のいずれかの方法を使用します。

- フィードバック Hub アプリを使用します。 このアプリは、HoloLens に接続されたコンピューターにあります。 フィードバック Hub で、**[エンタープライズ管理]**  >  **[デバイス]** カテゴリを選択します。  

  フィードバックを提供する、または問題を報告する場合は、詳細な説明を提供してください。 該当する場合は、スクリーンショットとログを含めてください。
- [hlappreview@microsoft.com](mailto:hlappreview@microsoft.com) にメール メッセージを送信してください。 メールの件名については、**\<*Tenant*> Autopilot for HoloLens 2 評価フィードバック** (ここで、\<*Tenant*> は Intune テナントの名前です) と入力してください。

  メッセージに詳細な説明を入力してください。 ただし、サポート担当者が特に要求しない限り、スクリーンショットやログなどのデータを含めないでください。 このようなデータには、個人や個人を特定できる情報 (PII) が含まれる場合があります。
