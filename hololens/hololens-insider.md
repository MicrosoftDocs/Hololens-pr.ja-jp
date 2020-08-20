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
ms.date: 7/17/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 1e6b8fcfad1dab49823f38c722de33654b361f58
ms.sourcegitcommit: 16d61083a1da8007278aed7e11eb6d44f7a90952
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941694"
---
# Microsoft HoloLens の Insider Preview

HoloLens 用の最新の Insider Preview ビルドへようこそ! HoloLens の[get started](hololens-insider.md#start-receiving-insider-builds)次の主要オペレーティング システムの更新プログラムを利用して、優れたフィードバックを提供できます。

## Windows Insider リリース ノート

Windows Insider ビルドで今日試すことのできる今後の機能の一覧を次に示します。

| 機能                                                | 説明                                                                                    | Insider ビルドで利用可能 |
|--------------------------------------------------------|------------------------------------------------------------------------------------------------|-----------------------------|
| [自動的に目回復位置のサポート](hololens-insider.md#auto-eye-position-support)                              | イイーロック位置が見つかり、正確なホログラームの位置を正確に示します。                        | 19041.1339+                 |
| [Certificate Viewer](hololens-insider.md#certificate-viewer)                                     | [設定] アプリでユーザーとデバイスの認明書を表示します。                                         | 19041.1346+                 |
| [Certificat をインストールおよび削除する](hololens-insider.md#install-and-remove-certificates)                        | ユーザーは、Certificate Viewer を使用して、サーティフェイスをインストールおよび削除できます。                        | 19041.1361+                 |
| [USB から自動起動プロビジョニングを行う](hololens-insider.md#auto-launch-provisioning-from-usb)                      | OOBE は、USB ドライブ上のプロビジョニング パッケージを自動的に検出します。                                | 19041.1361+                 |
| [OOBE でのプロビジョニング パッケージの自動確認](hololens-insider.md#auto-confirm-provisioning-packages-in-oobe)             | OOBE で自動プロビジョニング パッケージを自動的に適用します。                                             | 19041.1361+                 |
| [Wi-Fi 接続で自動パイロットを使用する](hololens-insider.md#using-autopilot-with-wi-fi-connection)                  | イーサネット アダプターが必要なく、デバイス Wi-Fi から自動パイロットを使用します。                             | 19041.1364+                 |
|[Tenantlockdown CSP and Autopilot](hololens-insider.md#tenantlockdown-csp-and-autopilot) | テナントの参加とポリシーの適用後、デバイスをリセットまたはフラッシュしたときはいつでも、デバイスをそのテナントに追加できます。 | 19041.1366+|
| [グローバルに割り当てられた](hololens-insider.md#global-assigned-access--kiosk-mode)                                 | システム レベルで適用される複数のアプリ キオスク モードの HoloLens 2 デバイスを構成します。 | 19041.1356+                 |
| [マルチ アプリ キオスクでアプリを自動起動する](hololens-insider.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                  | 複数アプリキオスク モードへのサインイン時に自動的に起動するアプリケーションを設定します。     | 19041.1346+                 |
| [Kiosks の表示者の自動ログオン](hololens-insider.md#visitor-auto-logon-for-kiosks)                          | キオスク モードで、ベストター アカウントに自動ログオンを有効にします。                         | 19041.1361+                 |
| [エラーの対数の対するキオク モードの動作変更](hololens-insider.md#kiosk-mode-behavior-changes-for-handling-of-failures) | キオスク モードの障敗が現在どのように対ハンドルに対する対に行います。                                              | 19041.1356+                 |
| [HoloLens ポリシー](hololens-insider.md#hololens-policies)                                      | Mixed Reality デバイス向けの新しいポリシー。                                                        | 19041.1349+                 |
| [オフライン キオスクのキャッシュ AAD グループ メンバーシップ](hololens-insider.md#cache-aad-group-membership-for-offline-kiosk)           | Kiosk モードで使用できる AAD グループ メンバーシップ キャッシュの数を示すポリシー。    | 19041.1356+                 |
| [HoloLens 2 の新しいデバイス制限ポリシー](hololens-insider.md#new-device-restriction-policies-for-hololens-2)         | HoloLens 2 で新しく有効化されたデバイス管理ポリシー。                               | 19041.1349+                 |
| [HoloLens 2 の新しい電源ポリシー](hololens-insider.md#new-power-policies-for-hololens-2)                      | Power タイムアウト設定の新しくサポートされているポリシー。                                           | 19041.1349+                 |
| [更新ポリシー](hololens-insider.md#newly-enabled-update-policies-for-hololens)                                        | 新しく有効にされたポリシーにより、更新プログラムを制御できます。                                            | 19041.1352+                 |
| [HoloLens 2 で設定ページの表示が有効にされました](hololens-insider.md#enabled-settings-page-visibility-for-hololens-2)        | 設定アプリで表示するページを選択するためのポリシー。                                           | 19041.1349+                 |
| [更新プログラムの改善点と修正プログラム](hololens-insider.md#improvements-and-fixes-in-the-update)                   | 更新プログラムの追加の修正プログラム。                                                                | 19041.1361+                 |

### 自動的に目回復位置のサポート

HoloLens 2 では、目の位置によりホログラームの配置、操作性がわかりやすく表示され、表示品質が向上します。 目の進捗管理結果の一部として目の位置が計算されます。 ただし、エクスペリエンスに目を必要としない場合でも、目の追跡機能を経営する必要があります。

**自動的に目を回る位置 (AEP)** を使用すると、これらのシナリオが対話型の方法でユーザーの目の位置を算出できます。  自動的にイーリーの場所で自動的に作業が始まるので、ユーザーがデバイスを配置します。 ユーザーに優先的な追跡機能がない場合、自動的にイイー語の位置は小さい処理時間の後でディスプレイ システムにユーザーの目の位置を指定します。 この処理時間は通常 20 ~ 60 秒です。 ユーザー データはデバイス上で永続的になり、ユーザーがデバイスをオフにしてデバイスを戻してデバイスを再開するか、デバイスが再び再開されたりスリープ状態から復復したりする場合は、このプロセスが繰り返されます。  

統合されていないユーザーがデバイスに配置されると、システムの動作がいくつか変更されます。 統合されていないユーザーは、以前にデバイス上で視示管理の評価プロセスを通じて移行していない人を示します。

|     アクティブなアプリケーション                           |     現在の動作                                   |     Windows Insider ビルド 19041.1339 以降の動作                                                      |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     ガジェットなしのアプリまたは Holographic Shell    |     追跡機能のプロンプトが表示されます。    |     メッセージは表示されません。                                                                                |
|     有効なアプリをゲーマートする                             |     追跡機能のプロンプトが表示されます。    |     視線の追跡のプロンプトは、アプリケーションがイージング ストリームにアクセスした場合にのみ表示されます。     |

 ユーザーが見つからないアプリケーションからデータをアクセスするアプリケーションにユーザーを移行すると、そのように求めるプロンプトが表示されます。 [既定の操作環境] フローには変更されません。 
 
データを見ているエクスペリエンス、または非常に正確なホログラマ位置を必要とするエクスペリエンスの場合は、 ユーザーの調整調整の調整を、見たい確認のプロンプトから、または [スタート] メニューから [設定] アプリを起動してから [ **システム環境の >調整>** イエイリブ>を実行する方法をお勧めします。

**既知の問題**
 - 負のメモリ ロードで実行しているときに、イーストラック ドライバー ホスト プロセスがクラッシュする可能性がある問題を調査しています。 イースト レージのホスト プロセスは自動的に回復する必要があります。

### Certificate Viewer

Windows Insider ビルド 19041.1346 以降では、HoloLens 2 Settings アプリに Certificate Viewer を追加しています。 現在、証明書インストールは .cer と .crt ファイルをサポートしています。 デバイスの所有者は、ローカル コンピューターと現在のユーザーに、サーティフェイスをインストールできます。 他のすべてのユーザーは、現在のユーザーのみにインストールできます。 ユーザーは、設定 UI から直接インストールされた Certificaticats のみを削除できます。 他の方法で、そのチャートがインストールされている場合は、同じメカニズマによるものが削除される必要があります。

-   **監査:** 証明書が正しく配置されていることを検証したり、適切に削除されたことを確認したりする機能。 
-   **診切れ:** 問題が発生した場合は、適切な証明書がデバイスに存在することを確認すると、時間を大きくなり、トラブルシューティングに役立ちます。 
-   **検証:** 証明書が目的を処理し、その証明書が機能することを確認することで、証明書をより大規模なスケールで展開する前に、業者環境で大きな時間を保存できます。

証明書を表示するには、[設定] メニューの **[>の更新&>に移動します**。

![設定アプリの認明者](images/certificate-viewer-device.jpg)

### Certificat をインストールおよび削除する
Windows Insider リリース 19041.1361 以降では、設定アプリから直接、HoloLens 2 に、Certificaticat をインストールして削除することができます。 現在、証明書インストールは .cer と .crt ファイルをサポートしています。 デバイスの所有者は、ローカル コンピューターと現在のユーザーに、サーティフェイスをインストールできます。 他のすべてのユーザーは、現在のユーザーのみにインストールできます。 ユーザーは、設定 UI から直接インストールされた Certificaticats のみを削除できます。 他の方法で、そのチャートがインストールされている場合は、同じメカニズマによるものが削除される必要があります。

#### 診明書ビューアーを使って、Certificate をインストールするには: 
1. [**設定] アプリの更新**プログラムとセキュリティ証明書に移動し、[証明書のインストール]  ->  **Update and Security**  ->  **Certificates****を選択します**。 
1. ファイル ピッカー エクスペリエンスから .cer ファイルを選択します。
1. ローカル コンピューター (または、ユーザーの認証をしている場所) を選択します。
1. Certificate Store (または、ユーザーの定め書を配置するストア) としてルートを選択します。 **Root** 
1. **[インストール]** をクリックします。

これで、Certificate がデバイスにインストールされるはずです。

#### 診明書ビューアーを使って、Certificate を削除するには: 
1. [設定 **] アプリの**  ->  **更新とセキュリティ**証明  ->  **書に移動します**。
1. 検索ボックスで、名前で検索します。
1. Certificate を選びます。
1. [削除] を **クリックする**
1. メッセージが表示されたら [はい] を選び、確認を求められたら [はい] を選びます。

![Certificate UI を使用して、Certificate をインストールする方法を示す画像](images/certificate-device-install.jpg)

#### 既知の問題 
インストール フロー中に、[ファイル ピッカー] から証明書を選択した後、インストール ダイアログ UI には選択した証明書ファイルは表示されません。 ファイルを選ぶと、ダイアログ ボックスに表示されているファイルが表示されない場合でも、インストールを進めます。 

### USB から自動起動プロビジョニングを行う
このビルド ユーザーは、OOBE の前に手動でプロビジョニング画面を起動し、ボタンの組み合わせを使用してプロビジョニング画面を起動する必要があります。 ユーザーは、USB ストレージ ドライブでプロビジョニング パッケージを使用してボタンの組み合わせをスキップできるようになりました。 

1. OOBE の最初のインターフェイス率の間に、USB ドライブをプロビジョニング パッケージを接続します
1. デバイスをプロビジョニングする準備ができたら、プロビジョニング ページを含むプロンプトが自動的に開きます。 

注: デバイスのボット中に USB ドライブが接続されたままの場合、OOBE は既存の USB ストレージ デバイスと接続されている追加のデバイスを視点で確認します。

OOBE のプロビジョニング パッケージの適用の詳細については、ここを参照 [してください](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。

### OOBE でのプロビジョニング パッケージの自動確認
プロビジョニング メイン画面が上に表示されると、すべてのプロビジョニング パッケージの適用を開始する前に OOBE は 10 秒間カウントされます。 期待されたパッケージを確認した後、この 10 秒後にユーザーはこの情報を確認または取り消すことができます。

### UI を使用せずに自動プロビジョニングを行う
USB デバイスからのプロビジョニングの自動起動とプロビジョニング パッケージの自動確認を組み合わせることで、ユーザーはデバイスの UI を使用することなく、またはデバイスをウェアリングしなくても、HoloLens 2 デバイスを自動的にプロビジョニングできます。 複数のデバイスに同じ USB ドライブとプロビジョニング パッケージを引き続き使用できます。 これは、複数のデバイスを同じ領域にまとめて配置する場合に便利です。 

1. Windows[構成デザイナーを使用してプロ](hololens-provisioning.md)[ビジョニング パッケージを作成します](https://www.microsoft.com/store/productId/9NBLGGH4TX22)。 
1. USB ストレージ ドライブにパッケージをコピーします。
1. [HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) から [19041.1361 以降のビルドにフラッシュします](https://aka.ms/hololens2previewdownload)。 
1. 高 [度な回復コンパニオン](https://www.microsoft.com/store/productId/9P74Z35SFRS8) が完了した後、デバイスが USB-C ケーブルを取り外すようになりました。 
1. USB ドライブをデバイスに接続します。
1. HoloLens 2 デバイスを OOBE にブートすると、USB ドライブ上のプロビジョニング パッケージが自動的に検出され、プロビジョニング ページが起動されます。
1. 10 秒があったら、デバイスは自動的にプロビジョニング パッケージを適用します。 

デバイスが構成され、正常な画面が表示されます。

### Wi-Fi 接続で自動パイロットを使用する
OOBE の実行中に、HoloLens 2 を Wifi に接続すると、OOBE はデバイスの自動パイロット プロファイルを確認します。 いずれかが見つかった場合は、AAD 結合と加加フローの残りの完了に使用されます。 つまり、USB C または USB C アダプターへのイーサプターの使用は要件でないため、OOBE の開始時に提供された場合は、それらの機能は継続します。 [HoloLens 2 デバイスの Autopilot の詳細を参照してください](hololens2-autopilot.md)。

### Tenantlockdown CSP and Autopilot
HoloLens 2 デバイスでは、Windows Insider ビルド 19041.1366 以降の時に TenantLockdown CSP がサポートされるようになりました。 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP では、OloLens 2 を自動パイロットのみを使用して MDM の加用に強くすることができます。 HoloLens 2 で TenantLockDown CSP の RequireNetworkInOOBE ノードが true または false (初回セット) の値に設定すると、その値は再フラッシュ、OS 更新プログラムなどがデバイス上に残ります。 

HoloLens 2 で TenantLockDown CSPs' RequireNetworkInOOBE ノードが true に設定されると、ネットワーク接続が正常にダウンロードされ適用されると、OOBE は Autopilot プロファイルを無期限にダウンロードし、適用されます。 

HoloLens 2 で TenantLockDown CSPs' RequireNetworkInOOBE ノードが true に設定されると、OOBE で次の操作が許可されます。 
- ランタイムのプロビジョニングを使用してローカル ユーザーを作成する 
- ランタイムのプロビジョニングを使用した AAD 結合操作の実行 
- OOBE エクスペリエンスでデバイスを所有しているユーザーを選択する 

#### Intune を使用して設定する方法 
1. カスタム OMA URI デバイス構成プロファイルを作成し、次に示すように RequireNetworkInOOBE ノードに true を指定します。
OMA-URI 値は、OMA-URI を使用して 、./ベンダー/MSFT/TenantLockdown/RequireNetworkInOOBE 設定のテンニアント ロック ![ ダウンを行う必要があります](images/hololens-tenant-lockdown.png)
1. グループを作成し、デバイス構成プロファイルをそのデバイス グループに割り当てます。 
1. 前の手順で作成したグループの HoloLens 2 デバイス メンバーを作成し、同期をトリガーします。  

デバイスの構成が正常に適用されたことを Intune ポータルで確認します。 このデバイス構成が Hololens 2 デバイスに正常に適用されると、TenantLockdown の効果がアクティブになります。

#### HoloLens 2 で TenantLockdown's RequireNetworkInOBE を解除する方法 
1. 前の手順で作成したデバイス構成が割り当てられていたデバイス グループから HoloLens 2 を削除します。 
1. カスタム OMA URI ベースのデバイス構成プロファイルを作成し、次に示すように要求ネットワークInOOBE の false を指定します。 OMA-URI 値は ![ 、OMA URI intune で OMA URI を使用して False への設定を要求する](images/hololens-tenant-lockdown-false.png)
1. グループを作成し、デバイス構成プロファイルをそのデバイス グループに割り当てます。 
1. 前の手順で作成したグループの HoloLens 2 デバイス メンバーを作成し、同期をトリガーします。

デバイスの構成が正常に適用されたことを Intune ポータルで確認します。 このデバイス構成が Hololens 2 デバイスに正常に適用されると、TenantLockdown の効果は非アクティブになります。 

#### TenantLockdown が True に設定された後に OOBE で AutoPilot プロファイルが割り当てられていない場合、どうなりますか? 
OOBE は、AutoPilot プロファイルをダウンロードし、次のダイアログが表示されるのを間もなくお待たします。 TenantLockdown の効果を削除するには、TenantLockdown CSP によって制限を解除する前に、まず AutoPilot のみを使用してデバイスを元のテナントに追加し、RequireNetworkInOOBE を最初に使用してデバイスを元のテナントに追加する必要があります。 

![デバイスでポリシーが適用されている場合のデバイス内ビュー。](images/hololens-autopilot-lockdown.png)

### グローバル割り当てアクセス – Kiosk モード
この新機能により、IT 管理者はシステム レベルで適用される複数のアプリ キオスク モード用の HoloLens 2 デバイスを構成できます。システムの ID に関するいかなることに優先があり、デバイスにサインインするすべてのユーザーに適用されます。 この新機能については、こちらを [参照してください](hololens-global-assigned-access-kiosk.md)。

### 複数アプリ キオスク モードでアプリケーションを自動起動する 
適用されるのは、複数アプリキオク モードにのみ適用され、[割り当て済みのアクセス] 構成で以下で強調表示されている属性を使用して自動起動に適用されるアプリは 1 つのアプリのみです。 

ユーザーがサインインすると、アプリケーションが自動的に起動します。 

```xml
<AllowedApps>                     
    <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### Kiosks の表示者の自動ログオン
この新機能により、ベストリ アカウントでの自動ログオンがキオスク モードで使用されるようになります。 

AAD 以外の構成の場合、次の手順にアクセスするデバイスを構成して、サイトの自動ログオンを実行します。
1.  次の操作を行うプロビジョニング パッケージを作成します。
    1.  **Visitor アカウントを許可する Runtime 設定/AssignedAccess**を構成します。
    1.  必要に応じて、デバイスを後で管理できるように MDM **(Runtime 設定/Workplace/加入)、デバイスを MDM (Runtime settings/Workplace/Enrollments)** に追加します。
    1.  ローカル アカウントを作成しない
1.  [プロビジョニング パッケージを適用します](hololens-provisioning.md)。

AAD 構成の場合、この変更を行わずにこのように同様のものを実用できます。 キオスク モード用に構成された AAD に参加しているデバイスでは、サインイン画面から 1 つのボタンをタップするだけで、"ベジター アカウント" にサインインできます。 アクセス者のアカウントにサインインすると、スタート メニューからその他のユーザーが自分でサインアウトするか、デバイスが再起動されるまで、デバイスにもう一度サインインするプロンプトが表示されません。

### エラーの対数の対するキオク モードの動作変更

キオスク モードの適用に関して問題が発生した場合、HoloLens はスタート メニューにすべてのアプリケーションを表示するために使用した HoloLens が使用されています。 この Windows Insider ビルドから起動すると、エラーが表示されなかった場合、次のようにスタート メニューにアプリは表示されません。 

![失敗したときに表示されるキオスク モードの画像。](images/hololens-kiosk-failure-behavior.png )

### HoloLens ポリシー
HoloLens 2 デバイス向けに新しい Mixed Reality ポリシーがビルドされ、ビルド 19041.1349 以降が作成されました。 新しい制御可能な設定には、明るさの設定、音量の設定、Mixed Reality キャプチャでのオーディオ録音の無効化、診切の診定を収集できる場合の設定、AAD グループ メンバーシップ キャッシュなどがあります。  

| 新しい HoloLens ポリシー                                | 説明                                                                               | 備考                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 明るさボタンを無効にして、押して明るさは変更されません。       | あり、0 No (既定)                                                |
| MixedReality\VolumeButtonDisabled                  | 音量ボタンを無効にして音量が変更されないようにします。               | あり、0 No (既定)                                                |
| MixedReality\MicrophoneDisabled                    | HoloLens 2 でオーディオ録音を実行できないように、マイクを無効にします。                      | あり、0 No (既定)                                                |
| MixedReality\FallbackDiagnostics                   | 診定ログを収集できるときのコントロール動作。                               | デバイスの所有者が 1 を有効にします。2 をすべてのデバイスで有効にします (既定) |
| MixedReality\HeadTrackingMode                      | 後で使用するためにために予定されています。                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | AAD グループを対象とする Kiosk に使用される AAD グループ メンバーシップのキャッシュの数を制御します。 | 以下を参照してください。                                                           |

### オフライン キオスクのキャッシュ AAD グループ メンバーシップ

このポリシーは、サインインしているユーザーの AAD グループを対象とする [割り当てられたアクセス] 構成に使用できる、AAD グループ メンバーシップ キャッシュを使用できる日数を制御します。 このポリシー値が 0 より大きい値に設定されたら、それ以外の場合はキャッシュが使用されます。  

名前: AADGroupMembershipCacheValidityInDays URI 値: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最小 - 0 日  
最大 - 60 日間 

このポリシーを正しく使用する手順: 
1. AAD グループを対象とするキオスクのデバイス構成プロファイルを作成し、HoloLens デバイスに割り当てます。 
1. このポリシー値を目的の日数 (> 0) に設定し、HoloLens デバイスに割り当てる OMA URI ベースのデバイス構成を作成します。 
    1. URI 値は、OMA-URI テキスト ボックスに ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays として入力する必要があります。
    1. 指定できる値の最小/最大値を指定できます。
1. HoloLens デバイスを入手し、両方の構成がデバイスに適用されていることを確認します。 
1. インターネットが利用可能になっていれば AAD ユーザー 1 のサインインを許可し、ユーザーがサインインし、AAD グループ メンバーシップが正常に確認されたら、キャッシュが作成されます。 
1. これで、AAD ユーザー 1 は HoloLens をオフラインにし、ポリシー値が X 日間可能な場合にキオスク モードに使用できるようになりました。 
1. その他の AAD ユーザー N に対して手順 4 と 5 を繰り返すことができます。ここで、AAD ユーザーはインターネットを使用してデバイスにサインインする必要があるため、Kiosk 構成がターゲットとなる AAD グループのメンバーであることを確認できるようになると、少なくとも AAD ユーザーがインターネットを使用してデバイスにサインインする必要があることです。 
 
> [!NOTE]
> AAD ユーザーの手順 4 が "切断" 環境で下記のエラー行敗を実行するまでは、経験します。 

### HoloLens 2 の新しいデバイス制限ポリシー
HoloLens 2 デバイスのより多くの管理オプションを管理できるポリシーが新しく有効になっています。 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

### Hololens 2 の新しい電源ポリシー
これらの新しく追加されたポリシーにより、管理者はアイドル タイムアウトなどの電源状態を制御できます。 個々のポリシーについて詳しく見るには、そのポリシーのリンクをクリックしてください。

|     ポリシー ドキュメント リンク                |     備考                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Windows 構成デザイナーで使用する値の例 (例:  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Windows 構成デザイナーで使用する値の例 (例:  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Windows 構成デザイナー (例: 100) で使用する値の例                                                                             |
|     [EnergySaverBatteryThresholdPlugedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Windows 構成デザイナー (例: 100) で使用する値の例                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows 構成デザイナーで使用する値の例 (例:   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows 構成デザイナーで使用する値の例 (例:  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

### HoloLens の新しく有効な更新ポリシー
HoloLens 2 デバイスで、次の更新ポリシーが有効になりました。
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

### HoloLens 2 で設定ページの表示が有効にされました
IT 管理者がシステム設定アプリの特定のページを表示またはアクセスできないようにするポリシーを有効にできるようになりました。また、指定されているページを除くすべてのページに対しても、このようにすることができるようになりました。 この機能を完全にカスタマイズする方法については、以下のリンクをクリックしてください。
 
- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)
 
![[設定] アプリで変更されているアクティブ時間のスクリーンショット](images/hololens-page-visibility-list.jpg)

### 更新プログラムの改善点と修正プログラム:
- AllowUsbConnection の NCM を通じて USB 関数の列挙を無効にする更新ポリシー。
- OOBE の画面がダーク モードになりました。
- 詳細については、最新のプライバシーに関する声明をオンラインで参照する必要があります。
- プロビジョニング パッケージを通じてユーザーが VPN プロファイルをプロビジョニングできない問題。

## Insider ビルドの受信の開始

> [!NOTE]
> 最近更新されない場合は、デバイスを再起動して最新のビルドを入手してください。
> - 「再ボット デバイス」の音声コマンドが有効なので、問題なく利用できます。 
> - [設定/Windows Insider Program] の [再起動] ボタンを選択することもできます。
>
> バックエンドでバックグラウンドでバグが発生したため、バックエンドに戻るとバグが発生しました。

HoloLens 2 デバイスで、**[設定]** > **[更新とセキュリティ]** > **[Windows Insider Program]** の順に移動し、**[開始する]** を選択します。 Windows Insider として登録するために使用したアカウントをリンクします。

Windows Insider は Channels に移動できるようになりました。 フ **ァスト リ** ングは **Dev Channel**になり、 **スロ** ー リングが **ベータ チャネル**になり、リリース **プレビュー** リングが **リリース プレビュー チャネルになります**。 マッピングは次のようになります。

![Windows Insider Channels の説明](images/WindowsInsiderChannels.png)

詳細については、Windows ブログにお使いの [Windows Insider Channels のご](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 説明をご覧ください。

次に **、Windows のアクティブ開発を選択し**、デベロッ **パ** ー チャネルビルドまたは **ベ** ータ版チャネル ビルドのいずれを受け取るかを選択し、プログラムの用語を確認します。

[ **今すぐ再起動] >を選択** します。 デバイスが再起動されたら、[設定 **] >[更新プログラム] >[セキュリティ & >確認] に移動して最新の** ビルドを入手します。

## FFU のダウンロードとフラッシュの手順
フライト署名のある FFU でテストするには、フライト署名のある FFU をフラッシュする前にデバイスのフライト ロックを解除する必要があります。
1. PC の場合:

    1. PC にファーストしてから PC にフィルタをダウンロードします [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. Microsoft Store ([https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)) から ARC (Advanced Recovery Companion) をインストールします。
    
1. HoloLens の場合 - Flight **Settings**Unlock のロック解除: Windows Insider Program  >  **&設定**の更新を  >  **開**いてから、再びサインアップします。

1. FFU - ARC を使用して署名した FFU をフラッシュできるようになりました。

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

1. [製品ビルド番号のリリース ノートを参照してください](hololens-release-notes.md)。

Insider ビルドをオプトアウトするには、次の操作を行います。

1. 製品版ビルドを実行している HoloLens で、**[設定] > [更新とセキュリティ] > [Windows Insider Program]** に移動して、**[Insider Preview ビルドの停止]** を選択します。

1. 画面の指示に従って、デバイスでの受信を停止します。
