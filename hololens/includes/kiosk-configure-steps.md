---
ms.openlocfilehash: 3d6b36124cd50dcc9f420227cb7787f0d787c013
ms.sourcegitcommit: c73cdefbdb4411f6a187cc38bb2570dadeb156bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2021
ms.locfileid: "129220623"
---
# <a name="microsoft-intune-single-app-kiosk-template"></a>[Microsoft Intune シングル アプリ キオスク テンプレート](#tab/uisak)

### <a name="microsoft-intune-single-app-kiosk-template"></a>Microsoft Intune シングル アプリ キオスク テンプレート

1. 構成プロファイルを作成します。 <br>
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. キオスク テンプレートを選択します。 <br>
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. 単一のアプリまたは複数のアプリ キオスクのいずれかを選択し、キオスク モードのユーザー ターゲット設定の種類も選択します。 <br>
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-sa-3.png"/>
</kbd>

<br>

4. キオスク モードで実行するアプリを選択します。 <br>
<kbd>
    <img alt="Choose the app" src="../images/kiosk-steps/kiosk-template-sa-4.png"/>
</kbd>

<br>

5. 残りのオプションはそのままにします。 <br>
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. この構成プロファイルの割り当て先のグループ/デバイスまたはユーザーを選択します。 <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

7. 構成プロファイルを確認、作成して保存します。
8. デバイスまたは Intune から開始する MDM 同期を実行し、デバイスに構成を適用します。 [Intune からデバイスを同期](/mem/intune/remote-actions/device-sync#sync-a-device)するか、デバイス上で **[設定] > [アカウント] > [職場または学校]** を選択し、接続されたアカウント > **[情報] > [同期]** を選択します。
9. キオスクを体験するターゲット ユーザーとしてサインインします。

# <a name="microsoft-intune-multi-app-kiosk-template"></a>[Microsoft Intune マルチ アプリ キオスク テンプレート](#tab/uimak)

### <a name="microsoft-intune-multi-app-kiosk-template"></a>Microsoft Intune マルチ アプリ キオスク テンプレート

1. 構成プロファイルを作成します。 <br>
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. キオスク テンプレートを選択します。 <br>
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. 単一のアプリまたは複数のアプリ キオスクのいずれかを選択し、キオスク モードのユーザー ターゲット設定の種類も選択します。 <br>
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-mak-3.png"/>
</kbd>

<br>

4. キオスク モードで実行するアプリを選択します。 <br>
<kbd>
    <img alt="Choose the app(s)" src="../images/kiosk-steps/kiosk-template-mak-4.png"/>
</kbd>

<br>

5. 残りのオプションはそのままにします。 <br>
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. この構成プロファイルの割り当て先のグループ/デバイスまたはユーザーを選択します。 <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

<br>

7. 構成プロファイルを確認、作成して保存します。
8. デバイスまたは Intune から開始する MDM 同期を実行し、デバイスに構成を適用します。 [Intune からデバイスを同期](/mem/intune/remote-actions/device-sync#sync-a-device)するか、デバイス上で **[設定] > [アカウント] > [職場または学校]** を選択し、接続されたアカウント > **[情報] > [同期]** を選択します。
9. キオスクを体験するターゲット ユーザーとしてサインインします。

# <a name="microsoft-intune-custom-template"></a>[Microsoft Intune カスタム テンプレート](#tab/intunecustom)

### <a name="microsoft-intune-custom-template"></a>Microsoft Intune カスタム テンプレート

1. 目的のキオスク エクスペリエンスの xml 構成を作成します。 こちらの[例](../hololens-kiosk-reference.md#kiosk-xml-code-samples)を参照して開始します。

1. カスタム構成プロファイルを作成します。 <br>
<kbd>
    <img alt="Create a custom configuration profile" src="../images/kiosk-steps/kiosk-custom-1.png"/>
</kbd>

<br>

3. カスタム構成プロファイルの名前を指定し、[構成設定] セクションの [追加] をクリックして、OMA-URI 設定を追加します。 <br>
<kbd>
    <img alt="Name and add" src="../images/kiosk-steps/kiosk-custom-2.png"/>
</kbd>

<br>

4. OMA-URI 設定の名前を指定します。

    1. OMA-URI テキストボックスで、 **./Device/Vendor/MSFT/AssignedAccess/Configuration** を入力します。
    1. データ型に **[文字列]** を選択します。
    1. [値] テキストボックスに、割り当てられたアクセス構成 xml をコピーして貼り付けます (シナリオに基づいた例については、参照先のリンクを参照し、コピー/貼り付けの前に必要に応じて更新します)。
    1. [保存] ボタンを選択して、設定と構成を保存します。

    <kbd>
        <img alt="Specify OMA-URI settings" src="../images/kiosk-steps/kiosk-custom-3.png"/>
    </kbd>

<br>

5. この構成プロファイルの割り当て先のグループ/デバイスまたはユーザーを選択します。 <br>
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-custom-4.png"/>
</kbd>

<br>

6. 構成プロファイルを確認、作成して保存します。
1. デバイスまたは Intune から開始する MDM 同期を実行し、デバイスに構成を適用します。 [Intune からデバイスを同期](/mem/intune/remote-actions/device-sync#sync-a-device)するか、デバイス上で **[設定] > [アカウント] > [職場または学校]** を選択し、接続されたアカウント > **[情報] > [同期]** を選択します。
1. キオスクを体験するターゲット ユーザーとしてサインインします。

# <a name="runtime-provisioning---multi-app"></a>[ランタイム プロビジョニング - 複数アプリ](#tab/ppkgmak)

### <a name="runtime-provisioning---multi-app"></a>ランタイム プロビジョニング - 複数アプリ

1. 目的のキオスク エクスペリエンスの xml 構成を作成します。 こちらの[例](../hololens-kiosk-reference.md#kiosk-xml-code-samples)を参照して開始します。

1. [Windows 構成デザイナー](https://www.microsoft.com/store/apps/9nblggh4tx22)を開きます。

1. スタート ページで、 **[HoloLens デバイスのプロビジョニング]** を選択します。 <br>
<kbd>
    <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
</kbd>

<br>

4. **[HoloLens 2 デバイスのプロビジョニング]** を選択し、[次へ] を選択します。 <br>
<kbd>
    <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
</kbd>

<br>

5. プロジェクトに名前を付けます。 必要に応じて、説明を追加します。 **[完了]** をクリックして続行します。

6. 画面の左下で、 **[詳細エディターに切り替える]** を選びます。 **[はい]** を選択して、詳細エディターへの切り替えを確認します。 <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

7. 左側で、[ランタイム設定]、[AssignedAccess] の順に展開し、 **[MultiAppAssignedAccess]** を選択します。 <br>

    <kbd>
        <img alt="select MultiAppAssignedAccess" src="../images/kiosk-steps/kiosk-provision-3.png"/>
    </kbd>

<br>

8. **[参照...]** ボタン をクリックしてエクスプローラーを開きます。 構成されたキオスク xml ファイルを選択します。

9. **[エクスポート]** 、 **[プロビジョニング パッケージ]** の順に選択します

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

10. 所有者の種類を **[IT 管理者]** に変更します。 <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

11. **[次へ]** を 3 回選択します。 **[Build]\(ビルド\)** を選択します。

12. プロビジョニング パッケージがビルドされたら、出力場所のフォルダーを開きます。 .ppkg ファイルは、プロビジョニング パッケージです。 省略可能な手順: プロジェクトを保存します。

13. これで、プロビジョニング パッケージを適用できるようになりました。 [セットアップ時にプロビジョニング パッケージを HoloLens に適用[するか、](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)セットアップ後にプロビジョニング パッケージを HoloLens に適用](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)できます。

14. キオスクを体験するターゲット ユーザーとしてサインインします。

# <a name="runtime-provisioning---single-app"></a>[ランタイムプロビジョニング - 単一アプリ](#tab/ppkgsak)

### <a name="runtime-provisioning---single-app"></a>ランタイムプロビジョニング - 単一アプリ

1. [Windows 構成デザイナー](https://www.microsoft.com/store/apps/9nblggh4tx22)を開きます。

1. スタート ページで、 **[HoloLens デバイスのプロビジョニング]** を選択します。 <br>

    <kbd>
        <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
    </kbd>

<br>

3. **[HoloLens 2 デバイスのプロビジョニング]** を選択し、[次へ] を選択します。 <br>

    <kbd>
        <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

4. プロジェクトに名前を付けます。 必要に応じて、説明を追加します。 **[完了]** をクリックして続行します。

5. 画面の左下で、 **[詳細エディターに切り替える]** を選びます。 **[はい]** を選択して、詳細エディターへの切り替えを確認します。 <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

6. 左側で、[ランタイム設定]、[AssignedAccess] の順に展開し、 **[AssignedAccessSettings]** を選択します。 <br>

    <kbd>
        <img alt="Navigate to assigned access settings" src="../images/kiosk-steps/kiosk-provision-sak-1.png"/>
    </kbd>

<br>

7. テキスト ボックスでキオスクを定義します。 たとえば、以下では、設定アプリである LocalAccount という名前のローカル アカウント用のシングル アプリ キオスクが作成されます。
```{"Account":"LocalAccount","AUMID":"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App"}```

8. **[エクスポート]** 、 **[プロビジョニング パッケージ]** の順に選択します <br>

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

9. 所有者の種類を **[IT 管理者]** に変更します。 <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

10. **[次へ]** を 3 回選択します。 **[Build]\(ビルド\)** を選択します。

11. プロビジョニング パッケージがビルドされたら、出力場所フォルダーを開きます。 .ppkg ファイルは、プロビジョニング パッケージです。 省略可能な手順: プロジェクトを保存します。

12. これで、プロビジョニング パッケージを適用できるようになりました。 [セットアップ時にプロビジョニング パッケージを HoloLens に適用[するか、](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)セットアップ後にプロビジョニング パッケージを HoloLens に適用](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)できます。