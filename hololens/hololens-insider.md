---
title: Microsoft HoloLens の Insider Preview
description: 簡単に Insider ビルドを使い始めて、HoloLens の次の主要なオペレーティング システムの更新プログラムに対する貴重なフィードバックをご提供いただけます。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 9/23/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 439ae9ddfbc6e7a83807e85c445f3d9f4cd2e182
ms.sourcegitcommit: fa2e551e3294ee49677035f5461b28861b20170f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "11088611"
---
# Microsoft HoloLens の Insider Preview

HoloLens 用の最新の Insider Preview ビルドへようこそ! HoloLens 向けの次の主要オペレーティングシステム更新プログラムについては、簡単に [作業を開始](hololens-insider.md#start-receiving-insider-builds) して、貴重なフィードバックを提供していただくことができます。

## Windows Insider リリース ノート

ここでは、Windows Insider ビルドで現在試すことができる今後の機能の一覧を示します。

| 機能                                                | 説明                                                                                    | Insider ビルドで利用可能 |
|--------------------------------------------------------|------------------------------------------------------------------------------------------------|-----------------------------|
| [オートアイポジションのサポート](hololens-insider.md#auto-eye-position-support)                              | 目の位置を実際に計算して、正確なホログラムの位置を指定します。                        | 19041.1339 +                 |
| [証明書マネージャー](hololens-insider.md#certificate-manager)                                     | ユーザーは、設定アプリで現在のユーザーとローカルコンピューターの証明書の表示、インストール、削除を行うことができます。                                         | 19041.1361 +                 |
| [USB からの自動起動プロビジョニング](hololens-insider.md#auto-launch-provisioning-from-usb)                      | OOBE は、USB ドライブ上のプロビジョニングパッケージを自動的に検出します。                                | 19041.1361 +                 |
| [OOBE でプロビジョニングパッケージを自動確認する](hololens-insider.md#auto-confirm-provisioning-packages-in-oobe)             | OOBE でプロビジョニングパッケージを自動的に適用します。                                             | 19041.1361 +                 |
| [Wi-fi 接続で自動操縦を使う](hololens-insider.md#using-autopilot-with-wi-fi-connection)                  | イーサネットアダプターを必要とせずに、デバイス Wi-fi から自動操縦を使用します。                             | 19041.1364 +                 |
|[Tenantlockdown CSP と自動操縦](hololens-insider.md#tenantlockdown-csp-and-autopilot) | テナントの登録後、ポリシーが適用されると、デバイスがリセットまたは再アップデートされるたびに、そのテナントにのみデバイスを登録できます。 | 19041.1366 +|
| [グローバルに割り当てられた](hololens-insider.md#global-assigned-access--kiosk-mode)                                 | システムレベルで適用可能な複数のアプリキオスクモード用に HoloLens 2 デバイスを構成します。 | 19041.1356 +                 |
| [マルチアプリキオスクでアプリを自動起動する](hololens-insider.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                  | 複数アプリのキオスクモードにサインインしたときに自動的に起動するようにアプリケーションを設定します。     | 19041.1346 +                 |
| [障害処理のためのキオスクモードの動作の変更](hololens-insider.md#kiosk-mode-behavior-changes-for-handling-of-failures) | キオスクモードのエラーが処理されるようになった変更。                                              | 19041.1356 +                 |
| [HoloLens ポリシー](hololens-insider.md#hololens-policies)                                      | Mixed reality デバイスの新しいポリシー。                                                        | 19041.1349 +                 |
| [オフラインキオスクの AAD グループメンバーシップをキャッシュする](hololens-insider.md#cache-aad-group-membership-for-offline-kiosk)           | AAD グループメンバーシップキャッシュをキオスクモードで使用できる日数のポリシーです。    | 19041.1356 +                 |
| [HoloLens 2 向けの新しいデバイス制限ポリシー](hololens-insider.md#new-device-restriction-policies-for-hololens-2)         | HoloLens 2 のデバイス管理ポリシーが有効になっています。                               | 19041.1349 +                 |
| [HoloLens 2 の新しい power policies](hololens-insider.md#new-power-policies-for-hololens-2)                      | Power timeout 設定に対して新しくサポートされているポリシー。                                           | 19041.1349 +                 |
| [更新ポリシー](hololens-insider.md#newly-enabled-update-policies-for-hololens)                                        | 新しく有効化されたポリシーにより、更新プログラムを制御できます。                                            | 19041.1352 +                 |
| [HoloLens 2 で有効になっている設定ページの表示](hololens-insider.md#enabled-settings-page-visibility-for-hololens-2)        | 設定アプリに表示されるページを選ぶためのポリシーです。                                           | 19041.1349 +                 |
|  [リサーチモード](hololens-insider.md#research-mode) | HoloLens 2 でのリサーチモードの使用 | 19041.1375 + |
| [更新プログラムの機能強化と修正](hololens-insider.md#improvements-and-fixes-in-the-update)                   | 更新プログラムのその他の解決策。                                                                | 19041.1361 +                 |


### オートアイポジションのサポート

HoloLens 2 では、目の位置によって正確なホログラムの配置が可能になり、表示品質が向上しました。 目の位置は、目の追跡結果の一部として計算されます。 ただし、そのためには、各ユーザーがアイ見つめ入力を必要としない場合でも、各ユーザーが目のトラッキングの調整を行う必要があります。

**オートアイポジション (AEP)** では、これらのシナリオを対話式の方法でユーザーの視点を計算できます。  自動目の位置は、ユーザーがデバイスを配置した瞬間から自動的にバックグラウンドで作業を開始します。 ユーザーが前に目を通したトラッキングの調整を行っていない場合は、処理時間が短いときにユーザーの視点がディスプレイシステムに提供されるようになります。 通常、この処理時間は 20-60 秒以内に行われます。 ユーザーデータはデバイス上で保持されないため、ユーザーが停止し、デバイスを再起動するか、デバイスをスリープ状態に戻した場合は、このプロセスを繰り返します。  

Uncalibrated ユーザーがデバイスに配置したときに、オートアイ位置機能によって、システムの動作がいくつか変更されます。 Uncalibrated ユーザーは、以前にデバイスの目のトラッキング調整プロセスを経ていないユーザーを参照しています。

|     アクティブなアプリケーション                           |     現在の動作                                   |     Windows Insider ビルド19041.1339 以降の動作                                                      |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     見つめ対応でないアプリまたはホログラフィックシェル    |     アイトラッキング調整のプロンプトが表示されます。    |     プロンプトは表示されません。                                                                                |
|     宝石対応アプリ                             |     アイトラッキング調整のプロンプトが表示されます。    |     アイトラッキング調整プロンプトは、アプリケーションがアイ見つめストリームにアクセスしたときにのみ表示されます。     |

 ユーザーが、見つめデータにアクセスするアプリケーションから、または見つめ対応のアプリケーションに切り替えた場合、調整のプロンプトが表示されます。 ボックスのエクスペリエンスフローの廃止には変更されません。 
 
視力のデータを必要とするエクスペリエンスや、非常に正確なホログラムの配置が必要な場合は、ユーザーがアイトラッキングの調整プロンプトからアイトラッキングの調整を実行するか、[スタート] メニューから設定アプリを起動して、[ **システム > 調整] >** 目の調整 > 実行することをお勧めします。

### 証明書マネージャー

Windows Insider ビルド 19041.1361 + microsoft は、HoloLens 2 設定アプリで証明書マネージャーを追加しています。 [設定] に移動して **& セキュリティ > 証明書を更新 >** ます。 この機能を使うと、デバイスで証明書の表示、インストール、削除を簡単に行うことができます。 新しい証明書マネージャーを使用すると、管理者とユーザーは、より高度な監査、診断、検証ツールを使って、デバイスの安全性と準拠性を維持できるようになりました。 

-   **監査:** 証明書が正しく展開されていることを確認したり、適切に削除されたことを確認したりすることができます。 
-   **診断:** 問題が発生した場合は、デバイス上に適切な証明書が存在することで、時間が節約され、トラブルシューティングに役立ちます。 
-   **検証:** 証明書が意図したものであり、機能していることを確認することにより、より大規模な証明書を展開する前に、特に商用環境では時間を節約できます。

リスト内の特定の証明書をすばやく検索するには、名前、ストア、有効期限のいずれかで並べ替えを行うオプションがあります。 ユーザーは、証明書を直接検索することもできます。 証明書のプロパティを個別に表示するには、証明書を選択し、[ **情報**] をクリックします。 

証明書のインストールでは、現在、.cer および .crt ファイルがサポートされています。 デバイスの所有者は、ローカルコンピューターおよび現在のユーザーに証明書をインストールできます。 他のすべてのユーザーは、現在のユーザーにのみインストールできます。 ユーザーは、[設定] UI から直接インストールされた証明書のみを削除することができます。 証明書が他の方法でインストールされている場合は、同じメカニズムでも削除する必要があります。

#### 証明書をインストールするには: 

1.  HoloLens 2 を PC に接続します。
1.  インストールする証明書ファイルを、HoloLens 2 の場所に配置します。
1.  [設定] アプリに移動して **& セキュリティ > 証明書を更新 >**、[証明書のインストール] を選択します。
1.  [ **ファイルのインポート** ] をクリックし、証明書を保存した場所に移動します。
1.  [ **保存場所**] を選びます。
1.  [ **証明書ストア**] を選びます。
1.  **[インストール]** をクリックします。

これで、証明書がデバイスにインストールされます。

#### 証明書を削除するには: 
1. [設定] アプリに移動し **て、[更新] および [セキュリティ > 証明書] >** します。
1. 検索ボックスに名前で証明書を検索します。
1. 証明書を選びます。
1. [**削除**] をクリック
1. 確認のメッセージが表示されたら、[ **はい]** を選択します。

![設定アプリの証明書ビューアー](images/certificate-viewer-device.jpg)

![証明書の UI を使用して証明書をインストールする方法を示す図](images/certificate-device-install.jpg)

### USB からの自動起動プロビジョニング
このビルドを実行する前に、OOBE 中にボタンの組み合わせを使用してプロビジョニング画面を手動で起動する必要がありました。 これで、ユーザーは USB ストレージドライブ上のプロビジョニングパッケージを使用して、ボタンの組み合わせをスキップできます。 

1. OOBE の最初の押さモーメントの間にプロビジョニングパッケージを使って USB ドライブを接続する
1. デバイスをプロビジョニングする準備ができたら、自動的に [プロビジョニング] ページでプロンプトが開きます。 

> [!NOTE]
> デバイスの起動中に USB ドライブが接続されている場合は、OOBE によって既存の USB ストレージデバイスが列挙されます。また、接続されている追加のデバイスを監視することもできます。

OOBE 中のプロビジョニングパッケージの適用の詳細について [は、こちら](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)を参照してください。

### OOBE でプロビジョニングパッケージを自動確認する
プロビジョニングのメイン画面が表示されると、すべてのプロビジョニングパッケージの適用が自動的に開始されるまで、OOBE は10秒後にカウントされます。 ユーザーは、予期したパッケージを確認した後、この10秒以内に確認または取り消しを行うことができます。

### UI を使用しない自動プロビジョニング
USB デバイスからのプロビジョニングの自動起動とプロビジョニングパッケージの自動確認を組み合わせることで、ユーザーはデバイスの UI を使わずに、またはデバイスを装着しなくても、HoloLens 2 デバイスを自動的にプロビジョニングできます。 複数のデバイスに同じ USB ドライブとプロビジョニングパッケージを引き続き使用することができます。 これは、同じ領域に複数のデバイスを一度に展開する場合に便利です。 

1. [Windows 構成デザイナー](https://www.microsoft.com/store/productId/9NBLGGH4TX22)を使用して[プロビジョニングパッケージを作成](hololens-provisioning.md)します。 
1. パッケージを USB ストレージドライブにコピーします。
1. [HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) を [19041.1361 以降のビルド](https://aka.ms/hololens2previewdownload)にフラッシュします。 
1. [アドバンスト回復コンパニオン](https://www.microsoft.com/store/productId/9P74Z35SFRS8)のフラッシュが完了すると、USB デバイスのプラグが切断されます。 
1. USB ドライブをデバイスに接続します。
1. HoloLens 2 デバイスが OOBE にブートすると、USB ドライブのプロビジョニングパッケージが自動的に検出され、プロビジョニングページが起動します。
1. 10秒後、デバイスはプロビジョニングパッケージを自動的に適用します。 

これでデバイスが構成され、プロビジョニングが成功したことを表示します。

### Wi-fi 接続で自動操縦を使う
これで、OOBE 中に HoloLens 2 を Wifi で接続すると、OOBE はデバイスの自動操縦プロファイルを確認します。 検出された場合は、AAD の参加と登録フローの残りの部分を使用します。 つまり、イーサネットから USB C または wifi から USB c への接続を使うことは必須ではありませんが、OOBE の開始時に提供された場合でも引き続き動作します。 [HoloLens 2 デバイスの自動操縦の](hololens2-autopilot.md)詳細については、こちらを参照してください。

### Tenantlockdown CSP と自動操縦
HoloLens 2 デバイスでは、Windows Insider ビルド 19041.1366 + の時点で TenantLockdown CSP がサポートされるようになりました。 

[Tenantlockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP は、HoloLens 2 が自動操縦のみを使用して MDM 登録に関連付けられるようにします。 RequireNetworkInOOBE ノードが HoloLens 2 の true または false (初期設定) の値に設定されると、その値は再フラッシュ、OS の更新などのデバイスに残ります。 

HoloLens で、RequireNetworkInOOBE ノードが HoloLens 2 で true に設定されると、OOBE は、ネットワーク接続後に自動操縦プロファイルが正常にダウンロードされ、適用されるまで無期限に待機します。 

HoloLens での RequireNetworkInOOBE ノードが HoloLens 2 で true に設定されると、次の操作は OOBE で許可されません。 
- ランタイムプロビジョニングを使用したローカルユーザーの作成 
- ランタイムプロビジョニングによる AAD 参加操作の実行 
- OOBE エクスペリエンスでデバイスの所有者を選択する 

#### Intune を使ってこれを設定するにはどうすればよいですか? 
1. カスタムの OMA URI デバイス構成プロファイルを作成し、次に示すように、RequireNetworkInOOBE ノードに true を指定します。
OMA-URI 値は/Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE である必要があります。

   > [!div class="mx-imgBorder"]
   > ![OMA-URI によるテナントのロックダウンの設定](images/hololens-tenant-lockdown.png)

1. グループを作成し、デバイス構成プロファイルをそのデバイスグループに割り当てます。 

1. 前の手順で作成したグループの HoloLens 2 デバイスメンバーを、同期をトリガーするように設定します。  

デバイス構成が正常に適用されたことを Intune ポータルで確認します。 このデバイスの構成が Hololens 2 デバイスに正常に適用されると、TenantLockdown の効果がアクティブになります。

#### Intune を使用して HoloLens 2 で TenantLockdown の RequireNetworkInOOBE を解除する方法 
1. 上で作成したデバイス構成が以前に割り当てられていたデバイスグループから HoloLens 2 を削除します。 

1. 次に示すように、カスタムの OMA URI ベースのデバイス構成プロファイルを作成し、RequireNetworkInOOBE に false を指定します。 OMA-URI 値は/Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE である必要があります。

   > [!div class="mx-imgBorder"]
   > ![Intune の OMA URI 経由で RequireNetworkInOOBE を false に設定する画面のスクリーンショット](images/hololens-tenant-lockdown-false.png)

1. グループを作成し、デバイス構成プロファイルをそのデバイスグループに割り当てます。 

1. 前の手順で作成したグループの HoloLens 2 デバイスメンバーを、同期をトリガーするように設定します。

デバイス構成が正常に適用されたことを Intune ポータルで確認します。 このデバイスの構成が Hololens 2 デバイスに正常に適用されると、TenantLockdown の効果は非アクティブになります。 

#### TenantLockdown が true に設定された後に、HoloLens で自動操縦プロファイルが割り当てられていない場合は、OOBE 中に何が起こりますか? 
OOBE は、自動操縦プロファイルがダウンロードされるまで無期限に待機し、次のダイアログが表示されます。 TenantLockdown の効果を削除するには、まず自動操縦のみを使用するようにデバイスを元のテナントに登録する必要があります。前の手順で説明したように、TenantLockdown CSP によって導入された制限は削除されます。 

![デバイスでポリシーが適用されている場合のデバイス内表示。](images/hololens-autopilot-lockdown.png)

### グローバル割り当てアクセス–キオスクモード
この新機能により、IT 管理者は、システムレベルで適用可能な複数のアプリキオスクモード用に HoloLens 2 デバイスを構成できます。また、システム上の id とのアフィニティはありません。また、デバイスにサインインしたすべてのユーザーに適用されます。 この新機能の詳細について [は、こちらをご覧](hololens-global-assigned-access-kiosk.md)ください。

### 複数アプリのキオスクモードでのアプリケーションの自動起動 
複数のアプリのキオスクモードにのみ適用され、[割り当て済みのアクセス構成] の下の強調表示された属性を使用して、1つのアプリのみを自動起動に指定できます。 

ユーザーがサインインすると、アプリケーションが自動的に起動します。 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### 障害処理のためのキオスクモードの動作の変更

「キオスクモードの適用時にエラーが発生しました」では、[スタート] メニューのすべてのアプリケーションを表示するために使用されていました。 この Windows Insider ビルド以降、障害が発生した場合、[スタート] メニューに次のようなアプリは表示されません。 

![キオスクモードで失敗したときにどのように表示されるかを示した画像。](images/hololens-kiosk-failure-behavior.png )

#### 更新プログラム
この方法でも更新プログラムを構成できます。そのため、ユーザーが Microsoft Store 経由でインストールしていない場合でも、更新プログラムを受け取ることができます。 アプリの起動チャンネルまたはスケジュールに基づいて更新を構成できます。 設定方法の詳細については、 [このページをご覧ください](https://docs.microsoft.com/windows/msix/app-installer/update-settings)。 

### HoloLens ポリシー
新しい mixed reality ポリシーは、ビルド 19041.1349 + の HoloLens 2 デバイス用に作成されています。 次のような新しい制御可能な設定があります。明るさの設定、音量の設定、混合の現実キャプチャでのオーディオ録音の無効化、診断を収集できるタイミングの設定、AAD グループメンバーシップキャッシュの設定があります。  

| 新しい HoloLens ポリシー                                | 説明                                                                               | 備考                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 明るさのボタンを無効にしても、明るさが変わらないようにすることができます。       | 1はい、0いいえ (既定)                                                |
| MixedReality\VolumeButtonDisabled                  | ボリュームボタンを無効にして音量を変更しないようにすることができます。               | 1はい、0いいえ (既定)                                                |
| MixedReality\MicrophoneDisabled                    | HoloLens 2 でオーディオ録音ができないように、マイクを無効にします。                      | 1はい、0いいえ (既定)                                                |
| MixedReality\FallbackDiagnostics                   | 診断ログを収集できる場合の動作を制御します。                               | 0無効、デバイス所有者の場合は1、すべてに対して有効 (既定) |
| MixedReality\HeadTrackingMode                      | 今後の使用のために予約されています。                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | キオスクグループメンバーシップキャッシュを使用してキオスクターゲット AAD グループに使用する日数を制御します。 | 以下を参照してください。                                                           |

### オフラインキオスクの AAD グループメンバーシップをキャッシュする

このポリシーは、サインインしたユーザーの AAD グループを対象とした割り当て済みのアクセス構成に対して、AAD グループメンバーシップキャッシュを使用できる日数を管理します。 このポリシー値が0より大きい値に設定された場合は、キャッシュが使用されます。  

名前: AADGroupMembershipCacheValidityInDays URI 値:./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最小-0 日  
最大60日 

このポリシーを正しく使用するための手順: 
1. キオスクターゲットの AAD グループ用のデバイス構成プロファイルを作成し、それを HoloLens デバイスに割り当てます。 
1. このポリシーの値を必要な日数 (> 0) に設定し、それを HoloLens デバイスに割り当てる、カスタム OMA URI ベースのデバイス構成を作成します。 
    1. URI 値は、/Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays のように、OMA-URI のテキストボックスに入力する必要があります。
    1. 指定できる値は、最小値と最大値の間で指定できます。
1. HoloLens デバイスを登録し、両方の構成がデバイスに適用されることを確認します。 
1. AAD ユーザー1のサインインを許可するインターネットが利用可能な場合、ユーザーがサインインして AAD グループメンバーシップが正常に確認されると、キャッシュが作成されます。 
1. この時点で、AAD user 1 は HoloLens をオフラインにして、ポリシー値が X 日で許可されている限り、キオスクモードで使用することができます。 
1. 手順4と5は、他の AAD ユーザー N に対して繰り返すことができます。重要なポイントは、どの AAD ユーザーもインターネット経由でデバイスにサインインする必要があります。そのため、少なくとも1回は、そのユーザーがキオスクの構成の対象となる AAD グループのメンバーであることを確認できます。 
 
> [!NOTE]
> AAD ユーザーに対して手順4を実行するまで、"接続されていない" 環境でのエラー動作が発生します。 

### HoloLens 2 向けの新しいデバイス制限ポリシー
HoloLens 2 デバイスの管理オプションを強化するための、新しく有効化されたポリシー。 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp) *

>[!NOTE]
> [Remotelock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)に関しては、HoloLens は/Vendor/MSFT/RemoteLock/Lock 構成のみをサポートしています。 Reset や recover など、PIN を扱う構成はサポートされません。

### Hololens 2 の新しい power policies
新しく追加されたポリシーにより、管理者はアイドルタイムアウトなどの電源状態を制御することができます。 個々のポリシーの詳細を確認するには、ポリシーのリンクをクリックしてください。

|     ポリシードキュメントリンク                |     備考                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Windows 構成デザイナーで使用する値の例:  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Windows 構成デザイナーで使用する値の例:  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Windows 構成デザイナー (100) で使用する値の例                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Windows 構成デザイナー (100) で使用する値の例                                                                          |
|     [スタンドアロン](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows 構成デザイナーで使用する値の例:   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows 構成デザイナーで使用する値の例:  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

> [!NOTE]
> HoloLens 2 で一貫したエクスペリエンスを実現するには、DisplayOffTimeoutOnBattery とスタンド Bytimeoutonバッテリーの両方の値が同じ値に設定されていることを確認してください。 同様に、DisplayOffTimeoutPluggedIn と StandbyTimeoutPluggedIn にも適用されます。 モダンスタンバイの詳細については [、「ディスプレイ、スリープ、および休止状態のアイドルタイマー」](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) を参照してください。

### HoloLens 用の新しく有効化済みの更新ポリシー
HoloLens 2 デバイスでは、これらの更新ポリシーが有効になりました。
-   [Update/Active/Send](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [更新/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/Active¥ Start](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [更新/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

### HoloLens 2 で有効になっている設定ページの表示
このポリシーを有効にすると、IT 管理者は、システム設定アプリで特定のページを表示またはアクセスできないようにするか、指定されたページ以外のすべてのページに対して行うことができます。 この機能を完全にカスタマイズする方法については、以下のリンクをクリックしてください。

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

HoloLens 2 でカスタマイズできるページ設定の詳細については、「 [Settings URIs (設定](settings-uri-list.md))」ページをご覧ください。 
 
![設定アプリで変更されたアクティブ時間のスクリーンショット](images/hololens-page-visibility-list.jpg)

### リサーチモード
[リサーチ] モードでは、HoloLens 2 はコンピューターのビジョン調査のための potent ツールになります。 以前のバージョンと比較すると、HoloLens 2 の Research モードには次の利点があります。
-   HoloLens (第1世代) リサーチモードで公開されるセンサーに加えて、加速度計、microsoft.devices.sensors.gyroscope、磁力計などの IMU センサーアクセスが提供されるようになりました。
-   HoloLens 2 には、リサーチモードと共に使用できる新機能が用意されています。 具体的には、より充実した一連の試験的機能を実現するための、表現力を追跡するための独自の Api へのアクセスを可能にします。

現在、研究者は、HoloLens デバイスでリサーチモードを有効にして、これらの外部向けの raw イメージセンサーストリームすべてにアクセスするオプションを利用できるようになりました。 HoloLens 2 の Research モードでは、加速度計、microsoft.devices.sensors.gyroscope、磁力計の読み取り結果にアクセスすることもできます。 ユーザーのプライバシーを保護するために、生の目を追跡するカメライメージは、リサーチモードでは使用できませんが、既存の Api を通じて目を見つめた方向にすることはできません。

詳しい技術情報については、 [リサーチモードのマニュアル](https://docs.microsoft.com/windows/mixed-reality/research-mode) をご覧ください。

### 更新プログラムの改善と修正:
- AllowUsbConnection の NCM での MDM 経由の USB 機能の列挙を無効にするポリシーが更新されました。
- OOBE のその他の画面が、ダークモードになります。
- 詳細については、最新のプライバシーに関する声明をオンラインで参照するようにしてください。
- ユーザーがプロビジョニングパッケージを使用して VPN プロファイルをプロビジョニングできなかった問題に対処しました。
- デバイスが [単一アプリのキオスク](hololens-kiosk.md)として設定されているときに、HoloLens デバイスがメディア転送プロトコル (MTP) を介してファイルエクスプローラーに表示されない問題に対処しました。 [Allowusbconnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)ポリシーを使用しても、MTP (および通常の USB 接続) を無効にすることができます。

## Insider ビルドの受信の開始

> [!NOTE]
> 最近更新していない場合は、デバイスを再起動して、状態を更新し、最新のビルドを取得してください。
> - "デバイスの再起動" 音声コマンドは適切に動作します。 
> - [設定] または [Windows Insider Program] で [再起動] を選択することもできます。
>
> バックエンドに、発生した可能性のあるバグがありました。これで、この問題が報告されます。

HoloLens 2 デバイスで、**[設定]** > **[更新とセキュリティ]** > **[Windows Insider Program]** の順に移動し、**[開始する]** を選択します。 Windows Insider として登録するために使用したアカウントをリンクします。

Windows insider がチャネルに移動するようになりました。 **ファスト**リングは**Dev チャネル**になります。**スロー**リングは**ベータチャネル**になり、 **release preview** ring は**リリースプレビューチャネル**になります。 マッピングの外観は次のようになります。

![Windows Insider チャネルの説明](images/WindowsInsiderChannels.png)

詳細については、「windows のブログに [Windows Insider チャネルを導入](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) する」を参照してください。

次に、[ **Windows のアクティブな開発**] を選択し、 **開発者チャネル** または **ベータチャネル** のビルドを受け取るかどうかを選択して、プログラムの利用規約を確認します。

[確認] を選択し、[ **今すぐ再起動 >** ます。] を選びます。 デバイスが再起動したら、[設定] に移動して **& セキュリティ > 更新** プログラムを確認し > 最新のビルドを入手します。

## FFU のダウンロードとフラッシュの手順
フライト署名のある FFU でテストするには、フライト署名のある FFU をフラッシュする前にデバイスのフライト ロックを解除する必要があります。
1. PC の場合:

    1. から PC に ffu をダウンロード [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) してください。
    
    1. Microsoft Store ([https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)) から ARC (Advanced Recovery Companion) をインストールします。
    
1. HoloLens でのロック解除:**設定**の  >  **更新 & セキュリティ**  >  **Windows Insider プログラム**を開くと、次にサインアップして、デバイスを再起動します。

1. Flash FFU-「ARC」を使って、フライト署名された FFU を点滅させることができます。

## フィードバックを提供し、問題を報告する

HoloLens で[フィードバック Hub アプリ](hololens-feedback.md)を使用してフィードバックを提供し、問題を報告することができます。 フィードバック Hub を使用すると、エンジニアが問題を迅速にデバッグして解決するのに役立つすべての必要な診断情報が含まれるようになります。  中国語および日本語版の HoloLens に関する問題は、同じ方法で報告する必要があります。

> [!NOTE]
> フィードバック Hub を使用してドキュメント フォルダーにアクセスするかどうかを確認するプロンプトに必ず同意してください (メッセージが表示されたら **[はい]** を選択します)。

## 開発者向けの注意事項

HoloLens の Insider ビルドを使用して自由にアプリケーションを開発してみることをお勧めします。  作業を始めるには、[HoloLens 開発者向けドキュメント](https://developer.microsoft.com/windows/mixed-reality/development)をご覧ください。 これらの同じ手順は HoloLens の Insider ビルドでも使用できます。  HoloLens 開発用に使用しているものと同じビルドの Unity と Visual Studio を使用できます。

## Insider ビルドの受信の停止

Windows Holographic の Insider ビルドを受け取りたくない場合は、HoloLens が製品版ビルドを実行しているときにオプトアウトすることができます。または、Advanced Recovery Companion を使用して[デバイスを回復](hololens-recovery.md)し、Windows Holographic の Insider バージョン以外にデバイスを回復することができます。

> [!CAUTION]
> 新しいプレビュー ビルドを手動で再インストールした後に Insider Preview ビルドの登録を解除すると、ブルー スクリーンが発生するという既知の問題があります。 その後、手動でデバイスを回復する必要があります。 影響を受けるかどうかの詳細については、この[既知の問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)の詳細をご覧ください。

HoloLens が製品版ビルドを実行していることを確認するには、次の操作を行います。

1. **[設定] > [システム] > [バージョン情報]** の順に移動し、ビルド番号を探します。

1. [製品のビルド番号については、リリースノートを参照してください](hololens-release-notes.md)。

Insider ビルドをオプトアウトするには、次の操作を行います。

1. 製品版ビルドを実行している HoloLens で、**[設定] > [更新とセキュリティ] > [Windows Insider Program]** に移動して、**[Insider Preview ビルドの停止]** を選択します。

1. 画面の指示に従って、デバイスでの受信を停止します。
