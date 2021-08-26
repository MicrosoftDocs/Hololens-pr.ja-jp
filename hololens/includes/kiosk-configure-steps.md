---
ms.openlocfilehash: 7a7122790d3e0257c07cdd8bc8c7f658b3a0e279
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859426"
---
# <a name="microsoft-intune-single-app-kiosk-template"></a>[シングルアプリキオスクテンプレートを Microsoft Intune](#tab/uisak)

## <a name="microsoft-intune-single-app-kiosk-template"></a>シングルアプリキオスクテンプレートを Microsoft Intune

1. 構成プロファイルを作成する <br> 
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. キオスクテンプレートの選択 <br> 
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. シングルアプリと複数のアプリキオスクのどちらを選択するか、また、キオスクモードのユーザーターゲットを選択するかを選択します <br> 
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-sa-3.png"/>
</kbd>

<br>

4. キオスクモードで実行するアプリを選択します <br> 
<kbd>
    <img alt="Choose the app" src="../images/kiosk-steps/kiosk-template-sa-4.png"/>
</kbd>

<br>

5. 残りのオプションはそのままにしておきます。 <br> 
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. この構成プロファイルが割り当てられるグループ/デバイスまたはユーザーを選択します <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

7. 確認して作成し、構成プロファイルを保存します
8. デバイスまたは Intune から MDM 同期を実行して、デバイスに構成を適用します。 設定 > アカウントを使用して Intune またはデバイス上のデバイスを [同期](/mem/intune/remote-actions/device-sync#sync-a-device)する- **> 職場または学校->** 接続されたアカウントを選択する- **> 情報-> 同期**
9. キオスクを体験するために、ターゲットユーザーとしてサインインします。

# <a name="microsoft-intune-multi-app-kiosk-template"></a>[マルチアプリキオスクテンプレートの Microsoft Intune](#tab/uimak)

## <a name="microsoft-intune-multi-app-kiosk-template"></a>マルチアプリキオスクテンプレートの Microsoft Intune

1. 構成プロファイルを作成する <br> 
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. キオスクテンプレートの選択 <br> 
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. シングルアプリと複数のアプリキオスクのどちらを選択するか、また、キオスクモードのユーザーターゲットを選択するかを選択します <br> 
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-mak-3.png"/>
</kbd>

<br>

4. キオスクモードで実行するアプリを選択します <br> 
<kbd>
    <img alt="Choose the app(s)" src="../images/kiosk-steps/kiosk-template-mak-4.png"/>
</kbd>

<br>

5. 残りのオプションはそのままにしておきます。 <br> 
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. この構成プロファイルが割り当てられるグループ/デバイスまたはユーザーを選択します <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

<br>

7. 確認して作成し、構成プロファイルを保存します
8. デバイスまたは Intune から MDM 同期を実行して、デバイスに構成を適用します。 設定 > アカウントを使用して Intune またはデバイス上のデバイスを [同期](/mem/intune/remote-actions/device-sync#sync-a-device)する- **> 職場または学校->** 接続されたアカウントを選択する- **> 情報-> 同期**
9. キオスクを体験するために、ターゲットユーザーとしてサインインします。

# <a name="microsoft-intune-custom-template"></a>[カスタムテンプレートの Microsoft Intune](#tab/intunecustom)

## <a name="microsoft-intune-custom-template"></a>カスタムテンプレートの Microsoft Intune

1. 必要なキオスクエクスペリエンスの xml 構成を作成します。 最初に、 [例](../hololens-kiosk-reference.md#kiosk-xml-code-samples) を参照してください。

1. カスタム構成プロファイルを作成する <br>
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

    1. [OMA-URI] ボックスに、「/Device/Vendor/MSFT/AssignedAccess/Configuration」と入力し **ます。**
    1. [データ型] を [ **文字列**] として選択します。
    1. [値] ボックスに、割り当てられたアクセス構成 xml をコピーして貼り付けます (シナリオに基づいた例については、「参照リンク」を参照してください。コピーと貼り付けの前に必要に応じて更新してください)。
    1. [保存] ボタンを選択して、設定と構成を保存します。

    <kbd>
        <img alt="Specify OMA-URI settings" src="../images/kiosk-steps/kiosk-custom-3.png"/>
    </kbd>

<br>

5. この構成プロファイルが割り当てられるグループ/デバイスまたはユーザーを選択します。 <br>
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-custom-4.png"/>
</kbd>

<br>

6. 確認して作成し、構成プロファイルを保存します。
1. デバイスまたは Intune から MDM 同期を実行して、デバイスに構成を適用します。 設定 > アカウントを使用して Intune またはデバイス上のデバイスを [同期](/mem/intune/remote-actions/device-sync#sync-a-device)する- **> 職場または学校->** 接続されたアカウントを選択する- **> 情報-> 同期**
1. キオスクを体験するために、ターゲットユーザーとしてサインインします。

# <a name="runtime-provisioning---multi-app"></a>[ランタイムのプロビジョニング-マルチアプリ](#tab/ppkgmak)

## <a name="runtime-provisioning---multi-app"></a>ランタイムのプロビジョニング-マルチアプリ

1. 必要なキオスクエクスペリエンスの xml 構成を作成します。 最初に、 [例](../hololens-kiosk-reference.md#kiosk-xml-code-samples) を参照してください。

1. [Windows 構成デザイナー](https://www.microsoft.com/store/apps/9nblggh4tx22)を開きます。

1. スタートページで、[ **HoloLens デバイスのプロビジョニング**] を選択します。 <br>
<kbd>
    <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
</kbd>

<br>

4. [**プロビジョニング HoloLens 2 デバイス**] を選択し、[次へ] を選択します。 <br>
<kbd>
    <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
</kbd>

<br>

5. プロジェクトに名前を付けます。 必要に応じて説明を記述します。 [ **完了** ] を選択して続行します。

6. 画面の左下にある [**詳細エディターに切り替え**] を選択します。 [はい] を選択して、詳細エディターへの切り替えを確認し **ます。** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

7. 左側で、[ランタイム設定]、[AssignedAccess] の順に展開し、[ **MultiAppAssignedAccess**] を選択します。 <br>

    <kbd>
        <img alt="select MultiAppAssignedAccess" src="../images/kiosk-steps/kiosk-provision-3.png"/>
    </kbd>

<br>

8. **[参照...]** ボタン をクリックしてエクスプローラーを開きます。 構成されているキオスク xml ファイルを選択します。

9. [ **エクスポート** ]、[ **パッケージのプロビジョニング**] の順に選択します。

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

10. 所有者の種類を **IT 管理** 者に変更します。 <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

11. **[次へ]** を 3 回選択します。 [ **ビルド**] を選択します。

12. プロビジョニングパッケージがビルドされたら、[出力場所] フォルダーを開きます。 Ppkg ファイルは、プロビジョニングパッケージです。 省略可能な手順: プロジェクトを保存します。

13. これで、プロビジョニングパッケージを適用できるようになりました。 セットアップ中に[プロビジョニングパッケージを HoloLens に適用](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)するか、[セットアップ後に HoloLens にプロビジョニングパッケージを適用](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)することができます。

14. キオスクを体験するために、ターゲットユーザーとしてサインインします。

# <a name="runtime-provisioning---single-app"></a>[ランタイムプロビジョニング-単一アプリ](#tab/ppkgsak)

## <a name="runtime-provisioning---single-app"></a>ランタイムプロビジョニング-単一アプリ

1. [Windows 構成デザイナー](https://www.microsoft.com/store/apps/9nblggh4tx22)を開きます。

1. スタートページで、[ **HoloLens デバイスのプロビジョニング**] を選択します。 <br>

    <kbd>
        <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
    </kbd>

<br>

3. [**プロビジョニング HoloLens 2 デバイス**] を選択し、[次へ] を選択します。 <br>

    <kbd>
        <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

4. プロジェクトに名前を付けます。 必要に応じて説明を記述します。 [ **完了** ] を選択して続行します。

5. 画面の左下にある [**詳細エディターに切り替え**] を選択します。 [はい] を選択して、詳細エディターへの切り替えを確認し **ます。** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

6. 左側で、[ランタイム設定]、[AssignedAccess] の順に展開し、[ **AssignedAccessSettings**] を選択します。 <br>

    <kbd>
        <img alt="Navigate to assigned access settings" src="../images/kiosk-steps/kiosk-provision-sak-1.png"/>
    </kbd>

<br>

7. テキストボックスでキオスクを定義します。 たとえば、次の例では、LocalAccount という名前のローカルアカウント (設定アプリ) に対して1つのアプリキオスクを作成します。
```{"Account":"LocalAccount","AUMID":"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App"}```

8. [ **エクスポート** ]、[ **パッケージのプロビジョニング**] の順に選択します。 <br>

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

9. 所有者の種類を **IT 管理** 者に変更します。 <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

10. **[次へ]** を 3 回選択します。 [ **ビルド**] を選択します。

11. プロビジョニングパッケージがビルドされたら、[出力場所] フォルダーを開きます。 Ppkg ファイルは、プロビジョニングパッケージです。 省略可能な手順: プロジェクトを保存します。

12. これで、プロビジョニングパッケージを適用できるようになりました。 セットアップ中に[プロビジョニングパッケージを HoloLens に適用](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)するか、[セットアップ後に HoloLens にプロビジョニングパッケージを適用](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)することができます。