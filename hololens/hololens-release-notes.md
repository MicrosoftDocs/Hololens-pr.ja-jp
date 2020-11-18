---
title: HoloLens 2 のリリース ノート
description: 新しい HoloLens 2 リリースごとの更新について説明します。
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/10/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 3cf2797d4c01f66b6433aaf327e31061a8dd2f3e
ms.sourcegitcommit: 307e313f05243b6d94f9bfc0cb4e316a00a8005c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2020
ms.locfileid: "11176909"
---
# HoloLens 2 のリリース ノート

HoloLens デバイスで生産性を向上させるには、引き続き機能、バグ、およびセキュリティの更新プログラムをリリースします。 このページでは、HoloLens の各月の新機能を確認できます。 最新の HoloLens 2 の更新プログラムを取得するには、 [更新プログラムを確認して](hololens-update-hololens.md#check-for-updates-and-manually-update) 、完全なフラッシュ更新プログラム (ffu) を手動で更新または取得して、 [アドバンスト回復コンパニオンでデバイスをフラッシュ](hololens-recovery.md#clean-reflash-the-device)するか、 [こちらからダウンロードして](https://aka.ms/hololens2download)ください。 ダウンロードは最新の状態に維持され、最新の一般的なビルドが提供されます。

>[!NOTE]
> HoloLens エミュレーターのリリースノートを読むには、 [アーカイブにアクセスして](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)ください。

## Windows ホログラフィック、バージョン20H2
- ビルド19041.1128

Windows ホログラフィック、バージョン20H2 が利用できるようになり、HoloLens 2 ユーザーと IT プロフェッショナルに優れた新機能が追加されました。 自動アイポジショニング、[設定] の [証明書マネージャー]、[キオスクモードの改善] 機能、および新しい自動操縦のセットアップ機能。 この新しい更新プログラムを使用すると、IT チームは HoloLens デバイスの構成と管理をより細かく制御できるようになり、よりシームレスなホログラフィックエクスペリエンスを提供できます。 

この最新のリリースは、バージョン2004に対する毎月の更新プログラムですが、今回の新機能は含まれています。 メジャービルド番号は変わりません。また、Windows Update では、バージョン 2004 (ビルド 19041) に対する毎月のリリースが示されます。 [> の設定] でビルド番号を確認して、最新のビルド 19041.1128 + が表示されていることを確認できます。 最新リリースに更新するには、[設定] アプリを開き、[& のセキュリティの更新] に移動して、[更新プログラムの確認] をタップします。 HoloLens の更新プログラムの管理方法の詳細については、 [このページ](https://docs.microsoft.com/hololens/hololens-updates)をご覧ください。

### Windows ホログラフィック、バージョン20H2 の新機能  

| 機能                                              | 説明                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [視線の自動調整サポート](hololens-release-notes.md#auto-eye-position-support) | ユーザーがアイトラッキングの調整を通過することなく、目の位置を積極的に計算します。   |
| [証明書マネージャー](hololens-release-notes.md#certificate-manager)   | 新しい簡単な方法で、設定アプリから証明書をインストールしたり、削除したりすることができます。     |
| [USB からの自動起動プロビジョニング](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | USB ドライブでパッケージをプロビジョニングすると、OOBE のプロビジョニングページが自動的に表示されます。                                                         |
| [OOBE でプロビジョニングパッケージを自動確認する](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | プロビジョニングパッケージは、プロビジョニングページから OOBE 中に自動的に適用されます。                                                         |
| [UI を使用しない自動プロビジョニング](hololens-release-notes.md#automatic-provisioning-without-using-ui) | プロビジョニング自動起動と自動確認を組み合わせる方法。 |
| [Wi-Fi 接続で自動操縦を使用する](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | イーサネットアダプターを必要とせずに、デバイス Wi-Fi から自動操縦を使用します。 |
| [Tenantlockdown CSP と Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | テナントの登録後、ポリシーが適用されると、デバイスがリセットまたは再アップデートされるたびに、そのテナントにのみデバイスを登録できます。 |
| [グローバルに割り当てられた](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | 複数のアプリキオスクモードの新しい構成方法により、システムレベルでキオスクが適用され、すべてに適用されます。                  |
| [マルチアプリキオスクでアプリを自動起動する](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | 複数アプリのキオスクモードにサインインしたときに自動的に起動するようにアプリケーションを設定します。                                                        |
| [障害処理のためのキオスクモードの動作の変更](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | キオスクモードのエラーにより、フォールバックが制限されるようになりました。                                                                                                |
| [HoloLens ポリシー](hololens-release-notes.md#hololens-policies)                                    | HoloLens の新しいポリシー。     |
| [オフラインキオスクの AAD グループメンバーシップをキャッシュする](hololens-release-notes.md#cache-aad-group-membership-for-offline-kiosk)         | 新しいポリシーを使用すると、ユーザーはグループメンバーシップキャッシュを使用して、設定した日数に対してオフラインでキオスクモードを使うことができます。                                        |
| [HoloLens 2 向けの新しいデバイス制限ポリシー](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | HoloLens 2 のデバイス管理ポリシーが有効になっています。                                                                                |
| [HoloLens 2 の新しい power policies](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Power timeout 設定に対して新しくサポートされているポリシー。  |
| [更新ポリシー](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | 新しく有効化されたポリシーにより、更新プログラムを制御できます。           |
| [HoloLens 2 で有効になっている設定ページの表示](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | 設定アプリに表示されるページを選ぶためのポリシーです。             |
| [リサーチモード](hololens-release-notes.md#research-mode) | HoloLens 2 でのリサーチモードの使用。 |
| [レコーディングの長さの増加](hololens-release-notes.md#recording-length-increased) | MRC レコーディングは、5分間では利用できなくなりました。 |
| [更新プログラムの機能強化と修正](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | 更新プログラムのその他の解決策。   |

### 視線の自動調整サポート

HoloLens 2 では、視線により、正確なホログラムの位置決め、快適な表示エクスペリエンス、および表示品質の向上が可能になります。 視線は、視線追跡計算の一部として内部的に計算されます。 ただし、これには、エクスペリエンスで視線の入力が必要ない場合でも、各ユーザーが視線追跡の調整を実行する必要があります。

**視線の自動調整 (AEP)** は、ユーザーの目の位置を計算するための操作のない方法でこれらのシナリオを可能にします。 視線の自動調整は、ユーザーがデバイスを装着した瞬間から自動的にバックグラウンドで動作を開始します。 ユーザーが事前に視線追跡の調整を行っていない場合、視線の自動調整は、20 ~ 30 秒の処理時間の後にユーザーの視線を表示システムに提供し始めます。 ユーザー データはデバイスに保持されないため、ユーザーがデバイスを外して装着した場合、またはデバイスが再起動したりスリープ状態から復帰したりすると、このプロセスが繰り返されます。

調整されていないユーザーがデバイスを装着した場合、視線の自動調整機能によるシステム動作の変更がいくつかあります。 このコンテキストでは、調整されていないユーザーとは、以前にデバイスで視線追跡の調整プロセスを実行したことがない人を指します。

| アクティブなアプリケーション | 以前の動作 | Windows Holographic、バージョン 20H2 アップデートからの動作 |
|:-------------------|:-----------------|:-----------------------------------|
| 非視線対応アプリまたはホログラフィック シェル |アイ トラッキングの調整プロンプト ダイアログが表示されます。 | プロンプトは表示されません。 |
| 視線対応アプリ | アイ トラッキングの調整プロンプト ダイアログが表示されます。 | アイ トラッキングの調整プロンプトは、アプリケーションが視線ストリームにアクセスした場合にのみ表示されます。 |

ユーザーが非視線対応アプリケーションから視線データにアクセスするアプリケーションに移行すると、調整プロンプトが表示されます。 

他のすべてのシステム動作は、現在のユーザーがアクティブな視線追跡の調整を持っていない場合と同様になります。 たとえば、片手で開始するジェスチャは有効になりません。 初期設定の Out-Of-Box-Experience に変更はありません。

視線データまたは非常に正確なホログラムの位置合わせが必要なエクスペリエンスの場合は、調整されていないユーザーに視線追跡の調整を実行することをお勧めします。 アイ トラッキング調整 プロンプトから、またはスタート メニューから設定アプリを起動し、**[システム] > [調整] > [視線調整] > [視線調整の実行]** の順に選択してアクセスできます。

この情報については、後で [他のキャリブレーション情報](hololens-calibration.md#auto-eye-position-support)を参照してください。 

### 証明書マネージャー

- 新しい証明書マネージャーを通じて、デバイスのセキュリティとコンプライアンスのための監査、診断、検証ツールが改善されました。 この機能を使用すると、商用環境で証明書の展開、トラブルシューティング、検証を行うことができます。

Windows ホログラフィックバージョン20Hh2 では、HoloLens 2 設定アプリで証明書マネージャーを追加しています。 [設定] に移動して **& セキュリティ > 証明書を更新 >** ます。 この機能を使うと、デバイスで証明書の表示、インストール、削除を簡単に行うことができます。 新しい証明書マネージャーを使用すると、管理者とユーザーは、より高度な監査、診断、検証ツールを使って、デバイスの安全性と準拠性を維持できるようになりました。 

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

この情報は、後で [新しい証明書マネージャーのページに](certificate-manager.md)記載されています。

### USB からの自動起動プロビジョニング

- プロビジョニングパッケージ付きの USB ドライブが OOBE 中に使用されるときに、ユーザーの操作が少なくなる自動プロセス。

このリリースを使用する前に、OOBE 中にボタンの組み合わせを使ってプロビジョニング画面を手動で起動する必要がありました。 これで、ユーザーは USB ストレージドライブ上のプロビジョニングパッケージを使用して、ボタンの組み合わせをスキップできます。 

1. OOBE の最初の押さモーメントの間にプロビジョニングパッケージを使って USB ドライブを接続する
1. デバイスをプロビジョニングする準備ができたら、自動的に [プロビジョニング] ページでプロンプトが開きます。 

注: デバイスの起動中に USB ドライブが電源に接続されている場合は、OOBE によって既存の USB ストレージデバイスが列挙されます。また、接続されている追加のデバイスを監視することもできます。

OOBE 中のプロビジョニングパッケージの適用の詳細について [は、こちら](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)を参照してください。

この情報は、[次のページ](hololens-provisioning.md#auto-launch-provisioning-from-usb)で参照できます。

### OOBE でプロビジョニングパッケージを自動確認する
- ユーザー操作が少なくなるように自動化されたプロセス。プロビジョニングパッケージページが表示されると、一覧表示されているすべてのパッケージが自動的に適用されます。

プロビジョニングのメイン画面が表示されると、すべてのプロビジョニングパッケージの適用が自動的に開始されるまで、OOBE は10秒後にカウントされます。 ユーザーは、予期したパッケージを確認した後、この10秒以内に確認または取り消しを行うことができます。

この情報は、[次のページ](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)で参照できます。

### UI を使用しない自動プロビジョニング
- プロビジョニングのためのデバイス操作を減らした自動プロセス。 

USB デバイスからのプロビジョニングの自動起動とプロビジョニングパッケージの自動確認を組み合わせることで、ユーザーはデバイスの UI を使わずに、またはデバイスを装着しなくても、HoloLens 2 デバイスを自動的にプロビジョニングできます。 複数のデバイスに同じ USB ドライブとプロビジョニングパッケージを引き続き使用することができます。 これは、同じ領域に複数のデバイスを一度に展開する場合に便利です。 

1. [Windows 構成デザイナー](https://www.microsoft.com/store/productId/9NBLGGH4TX22)を使用して[プロビジョニングパッケージを作成](hololens-provisioning.md)します。 
1. パッケージを USB ストレージドライブにコピーします。
1. [HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) を [19041.1361 以降のビルド](https://aka.ms/hololens2previewdownload)にフラッシュします。 
1. [アドバンスト回復コンパニオン](https://www.microsoft.com/store/productId/9P74Z35SFRS8)のフラッシュが完了すると、USB デバイスのプラグが切断されます。 
1. USB ドライブをデバイスに接続します。
1. HoloLens 2 デバイスが OOBE にブートすると、USB ドライブのプロビジョニングパッケージが自動的に検出され、プロビジョニングページが起動します。
1. 10秒後、デバイスはプロビジョニングパッケージを自動的に適用します。 

これでデバイスが構成され、プロビジョニングが成功したことを表示します。

この情報は、[次のページ](hololens-provisioning.md#automatic-provisioning-without-using-ui)で参照できます。

### Wi-Fi 接続で自動操縦を使用する
- デバイス Wi-Fi 接続されているデバイスで自動操縦を有効にすることによって、USB-C アダプターの必要なハードウェアの必要性を軽減します。

これで、OOBE 中に HoloLens 2 を Wifi で接続すると、OOBE はデバイスの自動操縦プロファイルを確認します。 検出された場合は、AAD の参加と登録フローの残りの部分を使用します。 つまり、イーサネットから USB への接続を使用する場合、または USB-C アダプターへの Wi-Fi を使うことは必須ではありませんが、OOBE の開始時に提供された場合は引き続き動作します。 [HoloLens 2 デバイスの自動操縦の](hololens2-autopilot.md)詳細については、こちらを参照してください。

### Tenantlockdown CSP と Autopilot
- デバイスのリセットまたは再フラッシュを行っても、デバイスをテナントにロックすることにより、デバイスを組織のテナントに保持します。 プロビジョニングを介したアカウントの作成を禁止することにより、セキュリティを強化します。 

HoloLens 2 デバイスでは、 [Windows ホログラフィックバージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2)での TENANTLOCKDOWN CSP がサポートされるようになりました。 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP は、HoloLens 2 が Autopilot のみを使用して MDM 登録に関連付けられるようにします。 TenantLockdown CSP の RequireNetworkInOOBE ノードが HoloLens 2 で true または false (最初に設定された) 値に設定されると、その値は、再フラッシュ、OS 更新プログラムなどにもかかわらずデバイスに残ります。 

HoloLens 2 で TenantLockdown CSP の RequireNetworkInOOBE ノードが true に設定されると、OOBE は、ネットワーク接続後、Autopilot プロファイルが正常にダウンロードおよび適用されるまで無期限に待機します。 

HoloLens 2 で TenantLockdown CSP の RequireNetworkInOOBE ノードが true に設定されると、OOBE では次の操作が許可されなくなります。 
- ランタイム プロビジョニングを使用したローカル ユーザーの作成 
- ランタイム プロビジョニングによる AAD 参加操作の実行 
- OOBE エクスペリエンスでデバイスの所有者を選択する 

#### Intune を使用してこれを設定する方法 
1. 以下に示すように、カスタム OMA URI デバイス構成プロファイルを作成し、RequireNetworkInOOBE ノードに true を指定します。
OMA-URI 値は ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE である必要があります

   > [!div class="mx-imgBorder"]
   > ![OMA-URI によるテナントのロックダウンの設定](images/hololens-tenant-lockdown.png)

1. グループを作成し、デバイス構成プロファイルをそのデバイス グループに割り当てます。 

1. 前の手順で作成したグループの HoloLens 2 デバイス メンバーを作成し、同期をトリガーします。  

Intune ポータルで、デバイス構成が正常に適用されていることを確認します。 このデバイスの構成が HoloLens 2 デバイスに正常に適用されると、TenantLockdown の効果がアクティブになります。

#### Intune を使用して HoloLens 2 で TenantLockdown の RequireNetworkInOOBE の設定を解除する方法 
1. 上で作成したデバイス構成が以前に割り当てられていたデバイス グループから HoloLens 2 を削除します。 

1. 以下に示すように、カスタム OMA URI ベースのデバイス構成プロファイルを作成し、RequireNetworkInOOBE に false を指定します。 OMA-URI 値は ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE である必要があります

   > [!div class="mx-imgBorder"]
   > ![Intune の OMA URI を介して RequireNetworkInOOBE を false に設定するスクリーンショット](images/hololens-tenant-lockdown-false.png)

1. グループを作成し、デバイス構成プロファイルをそのデバイス グループに割り当てます。 

1. 前の手順で作成したグループの HoloLens 2 デバイス メンバーを作成し、同期をトリガーします。

Intune ポータルで、デバイス構成が正常に適用されていることを確認します。 このデバイスの構成が HoloLens 2 デバイスに正常に適用されると、TenantLockdown の効果が非アクティブになります。 

#### TenantLockdown が true に設定された後、HoloLens で Autopilot プロファイルが割り当て解除された場合、OOBE 中にどうなりますか? 
OOBE は、Autopilot プロファイルがダウンロードされるのを無期限に待機し、次のダイアログが表示されます。 TenantLockdown の影響を取り除くには、最初に Autopilot のみを使用してデバイスを元のテナントに登録し、TenantLockdown CSP によって導入された制限を取り除く前に、前の手順で説明したように RequireNetworkInOOBE の設定を解除する必要があります。 

![ポリシーがデバイスに適用されるタイミングのデバイス内ビュー。](images/hololens-autopilot-lockdown.png)

この情報は、 [Tenantlockdown CSP と自動操縦](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)の残りの自動操縦の横にあります。

### グローバル割り当てアクセス–キオスクモード
- システムレベルでキオスクモードに適用される新しいキオスクメソッドを有効にすることで、キオスク用の Id 管理を削減しました。

この新機能により、IT 管理者は、システムレベルで適用可能な複数のアプリキオスクモード用に HoloLens 2 デバイスを構成できます。また、システム上の id とのアフィニティはありません。また、デバイスにサインインしたすべてのユーザーに適用されます。 この新機能の詳細について [は、こちらをご覧](hololens-global-assigned-access-kiosk.md)ください。

### 複数アプリのキオスクモードでのアプリケーションの自動起動 
- アプリの自動起動によるフォーカスエクスペリエンス。キオスクモードで選択された UI とアプリの選択範囲をさらに増やしています。

複数のアプリのキオスクモードにのみ適用され、[割り当て済みのアクセス構成] の下の強調表示された属性を使用して、1つのアプリのみを自動起動に指定できます。 

ユーザーがサインインすると、アプリケーションが自動的に起動します。 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### 障害処理のためのキオスクモードの動作の変更
- キオスクモードのエラーで利用可能なアプリを除去することで、より安全なキオスクモードを提供します。 

「キオスクモードの適用時にエラーが発生しました」では、[スタート] メニューのすべてのアプリケーションを表示するために使用されていました。 この時点では、エラーが発生した場合、Windows ホログラフィックバージョン20Hh2 では、[スタート] メニューに次のようなアプリは表示されません。 

![キオスクモードで失敗したときにどのように表示されるかを示した画像。](images/hololens-kiosk-failure-behavior.png )

### HoloLens ポリシー
- デバイスを管理するために作成された HoloLens 専用のデバイス管理オプション。 

新しい mixed reality ポリシーは、Windows ホログラフィックバージョン20H2 上の HoloLens 2 デバイス用に作成されています。 次のような新しい制御可能な設定があります。明るさの設定、音量の設定、混合の現実キャプチャでのオーディオ録音の無効化、診断を収集できるタイミングの設定、AAD グループメンバーシップキャッシュの設定があります。  

| 新しい HoloLens ポリシー                                | 説明                                                                               | 備考                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 明るさのボタンを無効にしても、明るさが変わらないようにすることができます。       | 1はい、0いいえ (既定)                                                |
| MixedReality\VolumeButtonDisabled                  | ボリュームボタンを無効にして音量を変更しないようにすることができます。               | 1はい、0いいえ (既定)                                                |
| MixedReality\MicrophoneDisabled                    | HoloLens 2 でオーディオ録音ができないように、マイクを無効にします。                      | 1はい、0いいえ (既定)                                                |
| MixedReality\FallbackDiagnostics                   | 診断ログを収集できる場合の動作を制御します。                               | 0無効、デバイス所有者の場合は1、すべてに対して有効 (既定) |
| MixedReality\HeadTrackingMode                      | 今後の使用のために予約されています。                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | キオスクグループメンバーシップキャッシュを使用してキオスクターゲット AAD グループに使用する日数を制御します。 | 以下を参照してください。                                                           |

### オフラインキオスクの AAD グループメンバーシップをキャッシュする
- 有効になっているオフラインキオスクは、最大60日間の AAD グループで使用できます。

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
> AAD ユーザーに対して手順4を実行するまで、"接続されていない" 環境で説明した失敗の動作が発生します。 

### HoloLens 2 向けの新しいデバイス制限ポリシー
- プロビジョニングパッケージの追加または削除をブロックするなど、特定のデバイス管理ポリシーをユーザーが管理できるようにします。

HoloLens 2 デバイスの管理オプションを強化するための、新しく有効化されたポリシー。 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

この2つの新しいポリシーは、Allowaddのパッケージと Allowremoveのパッケージについて、 [一般的なデバイスの制限](hololens-common-device-restrictions.md)に追加されています。

> [!NOTE]
> [Remotelock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)に関しては、HoloLens は/Vendor/MSFT/RemoteLock/Lock 構成のみをサポートしています。 Reset や recover など、PIN を扱う構成はサポートされません。

### HoloLens 2 の新しい power policies
- HoloLens を電源ポリシーでスリープまたはロックする場合のその他のオプション。 

新しく追加されたポリシーにより、管理者はアイドルタイムアウトなどの電源状態を制御することができます。 個々のポリシーの詳細を確認するには、ポリシーのリンクをクリックしてください。

|     ポリシードキュメントリンク                |     備考                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Windows 構成デザイナーで使用する値の例:  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Windows 構成デザイナーで使用する値の例:  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Windows 構成デザイナー (100) で使用する値の例                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Windows 構成デザイナー (100) で使用する値の例                                                                          |
|     [スタンドアロン](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows 構成デザイナーで使用する値の例:   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows 構成デザイナーで使用する値の例:  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

この2つの新しいポリシーは、DisplayOffTimeoutPluggedIn の [一般的なデバイス制限](hololens-common-device-restrictions.md)に追加されています。

> [!NOTE]
> HoloLens 2 で一貫したエクスペリエンスを実現するには、DisplayOffTimeoutOnBattery とスタンド Bytimeoutonバッテリーの両方の値が同じ値に設定されていることを確認してください。 同様に、DisplayOffTimeoutPluggedIn と StandbyTimeoutPluggedIn にも適用されます。 モダンスタンバイの詳細については [、「ディスプレイ、スリープ、および休止状態のアイドルタイマー」](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) を参照してください。

### HoloLens 用の新しく有効化済みの更新ポリシー
- 更新プログラムをインストールする場合や、更新プログラムの一時停止ボタンを無効にする場合のその他のオプション。

HoloLens 2 デバイスでは、これらの更新ポリシーが有効になりました。
-   [Update/Active/Send](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [更新/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/Active¥ Start](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [更新/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Thise 更新ポリシーの完全な詳細と、それらを HoloLens デバイスで使用する方法については、「 [hololens 更新プログラムの管理](hololens-updates.md)」をご覧ください。

### HoloLens 2 で有効になっている設定ページの表示
- 設定アプリでの UI コントロールの増加。一部のページのみを表示している場合は、混乱する可能性があります。

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

### レコーディングの長さの増加
お客様からのフィードバックのため、「 [mixed reality キャプチャ](holographic-photos-and-videos.md)」の録音時間が延長されました。 Mixed reality キャプチャは既定で5分に制限されることはありませんが、使用可能なディスク領域に基づいて、最大レコーディング長が計算されます。 デバイスは、ディスクの空き領域の最大80% に基づいて、利用可能なディスク領域に基づいて、最大ビデオ録画時間を推定します。

> [!NOTE]
> HoloLens では、次のいずれかが発生した場合に、既定のビデオ録画長 (5 分) が使用されます。
> - 予想される最大記録期間は、既定の5分よりも小さくなっています。
> - 使用可能なディスク領域は、合計ディスク領域の20% 未満です。

この情報は、 [ここで](holographic-photos-and-videos.md#maximum-recording-length)再び見つけることができます。 

### 更新プログラムの改善と修正:
- OOBE のその他の画面が、ダークモードになります。
- 詳細については、最新のプライバシーに関する声明をオンラインで参照するようにしてください。
- ユーザーがプロビジョニングパッケージを使用して VPN プロファイルをプロビジョニングできなかった問題に対処しました。
- VPN 接続のプロキシ構成の問題が修正されました。
- AllowUsbConnection の NCM での MDM 経由の USB 機能の列挙を無効にするポリシーが更新されました。
- デバイスが [単一アプリのキオスク](hololens-kiosk.md)として設定されているときに、HoloLens デバイスがメディア転送プロトコル (MTP) を介してファイルエクスプローラーに表示されない問題に対処しました。 [Allowusbconnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)ポリシーを使用しても、MTP (および通常の USB 接続) を無効にすることができます。
- [スタート] メニューのアイコンが自動プレゼンテーションモードで正しく調整された問題が修正されました。
- AAD グループを対象としたキオスクモードに対する HTTP キャッシュの干渉による問題が修正されました。
- 開発者モードを無効にして再び有効にしない限り、プロビジョニングパッケージで開発者モードを有効にした後でユーザーがペアリングボタンを使用できないという問題が修正されました。

## Windows ホログラフィック、バージョン 1903 (2020 年11月の更新プログラム)
- ビルド18362.1085

この毎月の品質更新プログラムには、注目すべき変更が含まれていません。最新の機能リリースビルド Windows ホログラフィック、バージョン20H2 を試用することをお勧めします。

## Windows ホログラフィック、バージョン 2004 (2020 年10月の更新プログラム)
- ビルド19041.1124
 
更新プログラムの改善と修正:

- ランタイムシステムフォールトを引き起こす不要なチェックが削除されました。

## Windows ホログラフィック、バージョン 1903 (2020 年10月の更新プログラム)
- ビルド18362.1081

この毎月の品質更新プログラムには、注目すべき変更内容が含まれていません。最新の Windows ホログラフィックバージョン2004のビルドをお試しいただくことをお勧めします。

## Windows ホログラフィック、バージョン 2004 (2020 年9月の更新プログラム)
- ビルド19041.1117

更新プログラムの改善と修正:

- Package.appxmanifest に Supports複数のインスタンス = "true" が含まれている場合に、Visual Studio がアプリケーションをデバッグできないという問題に対処します。
- このリリースには、ネットワークプロキシ経由のインターネット検出の失敗に対処するための NCSI プロキシ検出修正プログラムが含まれています。 NCSI では、コンピュータープロキシとプロファイルごとのプロキシを使って、インターネット接続が検出されます。 ユーザーごとのプロキシは、将来のリリースでは NCSI でサポートされます。
- ほとんどの Windows Mixed Reality デバイスでは、ユーザーのヘッドが中立の位置に表示されている場合、前方の方向ベクトルは地面に平行になります。 ただし、以前のバージョンの HoloLens 2 では、ベクターがディスプレイパネルに対して垂直になるように配置されています。この場合は、最適な向きに合わせて数度下方向に傾いています。 新しいバージョンの HoloLens 2 では、フォームファクターのセマンティックの一貫性を確保するために、これを修正しました。
- 明確な管理性が向上し、特定のシナリオでの追跡の損失が少なくなりました。
- このリリースには、ビデオキャプチャの問題が発生した可能性のあるオーディオタイムスタンプの品質を向上させる修正が含まれています。

## Windows ホログラフィック、バージョン 1903 (2020 年9月の更新プログラム)
- ビルド18362.1079

更新プログラムの改善と修正:

- ほとんどの Windows Mixed Reality デバイスでは、ユーザーのヘッドが中立の位置に表示されている場合、前方の方向ベクトルは地面に平行になります。 ただし、以前のバージョンの HoloLens 2 では、ベクターがディスプレイパネルに対して垂直になるように配置されています。この場合は、最適な向きに合わせて数度下方向に傾いています。 新しいバージョンの HoloLens 2 では、フォームファクターのセマンティックの一貫性を確保するために、これを修正しました。
- 明確な管理性が向上し、特定のシナリオでの追跡の損失が少なくなりました。

## Windows ホログラフィック、バージョン 2004 (2020 年8月の更新プログラム)
- ビルド19041.1113

更新プログラムの改善と修正:

- 設定アプリでは、ユーザーは虹彩登録またはアイトラッキングの調整エクスペリエンスに従わなくなります。
- デバイスの名前を変更して他の操作 (ネットワークへの接続など) を実行すると、名前の変更によるデバイスの再起動後に他の操作を実行できないというバグを修正しました。
- 視覚品質を向上させるために、デバイスセットアップの初期フローの配色が変更されました。

## Windows ホログラフィック、バージョン 1903 (2020 年8月の更新プログラム)
- ビルド18362.1074

この毎月の品質更新プログラムには、注目すべき変更内容が含まれていません。最新の Windows ホログラフィックバージョン2004のビルドをお試しいただくことをお勧めします。

## Windows ホログラフィック、バージョン 2004 (2020 年7月の更新プログラム)
- ビルド19041.1109

更新プログラムの改善と修正:

- 開発者は、Device Portal がセキュリティで保護された接続を必要とするかどうかを選択できるようになりました。
- OS の更新後にアプリケーションが起動するために、信頼性が向上しました。
- 既定の受信トレイの明るさが100% に変更されました。
- HoloLens 2 での Windows Device Portal の HTTPS 転送に関する問題に対処しました。

## Windows ホログラフィック、バージョン 1903 (2020 年7月の更新プログラム)
- ビルド18362.1071

更新プログラムの改善と修正:

- 変更履歴を紛失または regaining したときに、Unity アプリケーションでホログラムが表示されなくなる可能性がある問題が修正されました。
- 特定のデバイスでの HoloLens エミュレーターとハードウェアアクセラレーションを使っているときに、排他 HoloLens アプリがシェルにクラッシュする原因となっていた問題が修正されました。
- HoloLens 2 での Windows Device Portal の HTTPS 転送に関する問題に対処しました。

## Windows ホログラフィック、バージョン 2004-2020 年6月の更新プログラム
- ビルド19041.1106

更新プログラムの改善と修正:

- カスタム MRC レコーダーは、特定のプロパティに指定されていない場合は、新しい既定値を持つようになりました。
  - *MRC ビデオエフェクト*の場合:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (イマーシブヘッドセット))
  - *MRC オーディオエフェクト*の場合:
    - LoopbackGain (Windows Device Portal の Mixed Reality キャプチャページの現在の "アプリオーディオゲイン" 値)
    - マイクロフォンゲイン (Windows Device Portal の Mixed Reality キャプチャページの現在の "Mic オーディオゲイン" 値)
- 混合現実キャプチャシナリオでの音質を向上させるバグが修正されました。 具体的には、この修正プログラムでは、[ **スタート** ] メニューが表示されたときに、録音中のオーディオグリッチノイズを除去する必要があります。
- 記録されたビデオでのホログラムの安定性が向上しました。
- デバイスが複数日間スタンバイ状態になった後に、mixed reality キャプチャがビデオを録画できない問題を解決しました。
- HolographicSpace のプレゼンス API は、通常 Unity アプリケーションでは無効になっています。 この動作により、"バックグラウンドで実行する" 設定が有効になっている場合でも、一部のアプリが、バイザーが反転したときに一時停止される問題が回避されます。 これで、Unity バージョン2018.4.18 以降と2019.3.4 以降で、API が有効になります。
- Wi-Fi 接続経由で Device Portal にアクセスすると、web ブラウザーで無効な証明書が原因でアクセスできなくなることがあります。 デバイス証明書が以前信頼されていた場合でも、ブラウザーから "ERR_SSL_PROTOCOL_ERROR" などのエラーが報告されることがあります。 この場合、セキュリティの警告を無視するオプションはありませんので、Device Portal に進むことはできません。 この更新プログラムは、この問題を解決しました。 デバイス証明書が以前にダウンロードされ、PC に信頼されていて、ブラウザーのセキュリティ警告が表示されない場合は、新しい証明書をダウンロードして信頼し、ブラウザーのセキュリティの警告に対処する必要があります。
- MSIX パッケージを使ってアプリをインストールできるランタイムプロビジョニングパッケージを作成する機能が有効になりました。
- **Settings**  >  **System**  >  デバイスのシャットダウン時に、ユーザーが Mixed Reality ホームからすべてのホログラムを自動的に削除できるように設定システムの**ホログラム**の設定が追加されました。
- HoloLens エミュレーターでピクセル形式を変更する HoloLens アプリが、ブラックをレンダリングする問題を修正しました。
- 虹彩ログイン中のクラッシュの原因となるバグを修正しました。
- 既に現在のアプリのストアダウンロードの繰り返しに関する問題が修正されました。
- イマーシブアプリで Microsoft Edge が繰り返し開かれないようにするバグが修正されました。
- 1903リリースから更新された後の最初の起動でのフォトアプリの起動に関する問題が修正されました。
- パフォーマンスと信頼性が向上しました。

## Windows ホログラフィック、バージョン 1903-2020 年6月の更新プログラム
- ビルド18362.1064

更新プログラムの改善と修正:

- カスタム MRC レコーダーに指定されていない場合は、特定のプロパティに対して新しい既定値があります。
  - *MRC ビデオエフェクト*の場合:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (イマーシブヘッドセット))
  - *MRC オーディオエフェクト*の場合:
    - LoopbackGain (Windows Device Portal の Mixed Reality キャプチャページの現在の "アプリオーディオゲイン" 値)
    - マイクロフォンゲイン (Windows Device Portal の Mixed Reality キャプチャページの現在の "Mic オーディオゲイン" 値)
- HolographicSpace のプレゼンス API は、通常 Unity アプリケーションでは無効になっています。 この動作により、バックグラウンドで実行されている設定が有効になっている場合でも、バイザーが反転するときに一部のアプリが一時停止する問題が発生しなくなります。 この API は、Unity バージョン2018.4.18 以降、および2019.3.4 以降で有効になりました。
- HoloLens エミュレーターでピクセル形式を変更する HoloLens アプリが、ブラックをレンダリングする問題を修正しました。
- 1903リリースから更新された後の最初の起動での写真アプリの起動に関する問題が修正されました。

## Windows ホログラフィック、バージョン2004  
- ビルド-19041.1103

HoloLens 2、 *Windows ホログラフィック、バージョン 2004* 向けの2020年5月のメジャーソフトウェア更新プログラムには、Windows 自動操縦のサポート、アプリのダークモード、USB イーサネットでの 5G/LTE ホットスポットのサポートなど、魅力的な新機能のホストが含まれています。 最新リリースに更新するには、**設定**   アプリを開き、[ **更新 & セキュリティ**] に移動して、[ **更新プログラムのチェック**   ] ボタンを選択します。 

|             機能                              |          説明                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Windows 自動操縦を使用して、製造用の新しいデバイスを事前構成して、シームレスにセットアップする                 |
|       FIDO 2 のサポート                             |          共有デバイスの高速でセキュリティ保護された認証を可能にする FIDO2 セキュリティキーのサポート            |
|       プロビジョニングの改善                      |          USB ドライブから HoloLens へのプロビジョニングパッケージのシームレスな適用                              |
|       アプリケーションのインストールの状態                 |          アプリが MDM 経由で HoloLens 2 にプッシュされた設定アプリの [インストールの状態] を確認する               |
|       構成サービスプロバイダー (Csp)   |          管理者コントロール機能を強化するために新しい構成サービスプロバイダーを追加しました                 |
|       USB 5G/LTE のサポート                       |          拡張 USB Ethernet 機能により、5G/LTE のサポートが可能に                                    |
|       濃色アプリモード                              |          濃色とライトの両方のモードをサポートするアプリで使用できるダークアプリモード。表示エクスペリエンスを向上させる        |
|       音声コマンド                             |          HoloLens ハンズフリーを制御するための追加のシステム音声コマンドのサポート                           |
|       手動トラッキングの改善                 |          手作業でのトラッキングによるボタンと2D スレートの相互作用の精度を向上させる                        |
|       品質の改善と修正                 |          プラットフォーム全体でのさまざまなシステムのパフォーマンスと信頼性の向上                            |

### Windows 自動操縦のサポート

HoloLens 2 用の Windows 自動操縦機能を使うと、デバイス販売チャネルで HoloLens を Intune テナントに事前登録できます。 デバイスが到着すると、テナントの下で共有デバイスとして自己展開する準備が整います。 セルフ展開を活用するには、USB--イーサネットを使って、セットアップの最初の画面でネットワークに接続する必要があります。

ユーザーが自動操縦の自動展開プロセスを開始した後、プロセスは次の手順を完了します。

1. デバイスを Azure Active Directory (Azure AD) に参加させます。
1. Azure AD を使用して、Microsoft Intune (または別の MDM サービス) にデバイスを登録します。
1. デバイスを対象としたポリシー、証明書、およびネットワーク プロファイルをダウンロードします。
1. デバイスをプロビジョニングします。
1. ユーザーにサインイン画面を提示します。

詳細については、「 [Windows 自動操縦の HoloLens 2 の評価ガイド」](https://docs.microsoft.com/hololens/hololens2-autopilot)を参照してください。

*今すぐ自動操縦プレビューに参加するには、アカウントマネージャーに連絡してください。 自動操縦対応デバイスはまもなく出荷を開始します。*

### FIDO2 セキュリティキーのサポート

一部のユーザーは、職場または学校環境で HoloLens デバイスを他のユーザーと共有します。 このため、ユーザーは長いユーザー名とパスワードを入力しなくても簡単に行うことができるようにすることが重要です。 Fast Identity Online (FIDO) を使うと、組織内のすべてのユーザーが、ユーザー名またはパスワードを入力しなくても HoloLens にサインインすることができます。

FIDO2 セキュリティキーは、任意のフォームファクターで利用できる "unphishable" 標準ベースの passwordless メソッドです。 FIDO は、passwordless 認証のオープン標準です。 ユーザー名またはパスワードを使わずにリソースにサインインすることができます。 代わりに、デバイスに組み込まれている外部セキュリティキーまたはプラットフォームキーを使用します。

はじめに、「 [パスワードを使用したセキュリティキーのサインインを有効に](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)する」を参照してください。

### プロビジョニングパッケージによる MDM 登録の改善

プロビジョニングパッケージを使うと、HoloLens 以外のエクスペリエンスではなく、構成ファイルを使って HoloLens 構成を設定できます。 以前は、プロビジョニングパッケージを HoloLens 内部メモリにコピーする必要がありました。 これで、複数の HoloLens デバイスで簡単に再利用できるように USB ドライブに接続できるようになりました。また、デバイスを並列でプロビジョニングすることができます。 プロビジョニングパッケージは、デバイス管理に登録するフィールドもサポートするため、プロビジョニング後に手動で設定する必要はありません。

以下の手順をお試しください。

1. Windows ストアから PC に最新バージョンの Windows 構成デザイナーをダウンロードします。
1. [Hololens**デバイス**  >  のプロビジョニング**hololens 2 デバイス**のプロビジョニング] を選択します。
2. 構成プロファイルを作成します。 次に、作成されたすべてのファイルを USB-C ストレージデバイスにコピーします。
3. USB-C デバイスを、新しくフラッシュされた HoloLens に接続します。 次に、**音量を下げる**  +  **電源**ボタンを押してプロビジョニングパッケージを適用します。

### 基幹業務アプリケーションのインストール状態

基幹業務アプリの MDM アプリの展開と管理は、HoloLens にとって不可欠です。 管理者とユーザーは、監査と診断のためのアプリのインストール状態を表示する必要があります。 このリリースでは、「 **Settings**  >  **Accounts**  >  アカウント**アクセスの職場または学校**で  >  **アカウント情報をクリックする**  >  **Info**」の詳細を追加しました。

### その他の Csp とポリシー

[構成サービスプロバイダー (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN)は、デバイスの構成設定の読み取り、設定、変更、または削除を行うためのインターフェイスです。 このリリースでは、さらに多くのポリシーのサポートを追加して、管理者が HoloLens デバイスを使用した場合の制御を強化しています。 HoloLens でサポートされている Csp の一覧については、「 [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)」を参照してください。

今回のリリースの新バージョン:

**Policy CSP** 

ポリシー構成サービスプロバイダーによって、企業は Windows デバイスでポリシーを構成できます。 今回のリリースでは、以下に示す HoloLens の新しいポリシーが追加されています。 詳細については、「 [HoloLens 2 でサポートされているポリシーの csp](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)」を参照してください。  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessGazeInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- AllowWiFi 

**NetworkQoSPolicy CSP**

NetworkQoSPolicy 構成サービスプロバイダーは、ネットワークの QoS (quality of service) ポリシーを作成します。 QoS ポリシーは、一連の照合条件に基づいて、ネットワーク トラフィックに一連のアクションを実行します。 詳細については、「 [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)」を参照してください。

### 5G/LTE tethered デバイスの拡張 USB イーサネットサポート

USB 経由で HoloLens 2 に tethered されている場合、5G/LTE 電話や Wi-Fi ホットポットなどの特定のモバイルブロードバンドデバイスを有効にするためのサポートが追加されました。 これらのデバイスは、別のイーサネット接続として [ **ネットワーク設定** ] に表示されるようになりました。 (外付けドライバーが必要なモバイルブロードバンドデバイスはサポートされていません。)この機能により、Wi-Fi が利用できない場合には高帯域幅接続が有効になり、Wi-Fi テザリングでは十分なパフォーマンスが実現されません。 サポートされている USB デバイスの詳細については、「 [Bluetooth デバイスと usb デバイスに接続する](https://docs.microsoft.com/hololens/hololens-connect-devices)」を参照してください。  

### 手動トラッキングの改善

このリリースには、次のような手による追跡機能がいくつかあります。

- **ポイントの安定性:** これで、システムは palm によって見えなくなるされたときにインデックス指を resists ます。 この変更により、ボタンのプッシュ、テキストのスクロール、コンテンツのスクロールなどの精度が向上します。 
- **偶発的なエアタップの減少:** エアタップジェスチャの検出機能が改善されました。 いくつかの一般的なシナリオでは、偶発的なライセンス認証の回数が少なくなりました。たとえば、手を手にドロップしたときです。
- **ユーザーの切り替えの信頼性:** デバイスを共有するときに、システムの速度と信頼性が向上しました。
- **手を盗む:** センサーの表示に3つ以上の針がある場合の処理を改善しました。 複数のユーザーが接近して作業している場合は、追跡した針がユーザーからシーン内の他の人の手に "ジャンプ" する可能性がはるかに低くなります。
- **システムの信頼性:** デバイスが高負荷のときに、手動でトラッキングが機能しなくなる問題を修正しました。

### 濃色モード

多くの Windows アプリで、ダークモードとライトモードの両方がサポートされるようになりました。 HoloLens 2 ユーザーは、両方をサポートするアプリの既定のモードを選ぶことができます。 更新後、既定のアプリモードは "dark" ですが、この設定を簡単に変更できます。 [**設定**  >  **システム**の色] に移動し  >  **Colors**  >  **て、既定のアプリモードを選択**します。 

次の "in box" アプリは、ダークモードをサポートしています。 

- 設定 
- Microsoft Store 
- メール 
- カレンダー 
- エクスプローラー 
- フィードバック Hub 
- OneDrive 
- フォト 
- 3D ビューアー 
- 映画 & テレビ 

![ダークモードのウィンドウ (並べて表示)](images/DarkMode.jpg)

### システム音声コマンド

これで、デバイス上の任意のアプリで音声コマンドを使用できるようになりました。 詳細については、「 [お使いの音声を使って HoloLens を操作する](https://docs.microsoft.com/hololens/hololens-cortana)」を参照してください。 「 [HoloLens 2 でサポートされる言語](https://docs.microsoft.com/hololens/hololens2-language-support)」もご覧ください。  

### Cortana の更新

更新されたアプリは Microsoft 365 と統合され、デバイス全体でより多くの作業を行うことができます (現時点では US-English のみ)。 HoloLens 2 では、ボリュームの調整や再起動など、特定のデバイス固有のコマンドは Cortana でサポートされなくなりました。 これらのオプションは、新しいシステム音声コマンドでサポートされるようになりました。 [ブログ](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)の新しい Cortana アプリの詳細については、こちらを参照してください。

### 品質の改善と修正

以下の更新プログラムも含まれています。  
- アクティブなディスプレイ調整システムが導入されました。 この機能により、ホログラムの安定性と配置が向上します。 これで、ヘッドを左右に移動しても表示されます。
- HoloLens Wi-Fi のストリーミングが定期的に中断されているバグを修正しました。 待機時間の短いストリーミングが必要であることがアプリケーションで示されている場合は、 [SetSocketMediaStreamingMode 関数](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)を呼び出して修正プログラムを実装します。
- リサーチモードでのストリーミング中に発生したデバイスのハングが修正されました。
- セッションを再開するときに、サインイン画面に適切なユーザーが表示されない場合があるというバグを修正しました。
- ユーザーが **設定**を使用して MDM ログをエクスポートできない問題が修正されました。
- ボックスのすぐ後に目を通した正確さが期待よりも低くなる可能性がある問題が修正されました。
- 特定の条件下でアイトラッキングサブシステムの初期化または調整に失敗した問題が修正されました。
- 既に調整されたユーザーに目の調整が求められる問題が修正されました。
- 目の調整中にドライバーがクラッシュする問題が修正されました。
- 電源ボタンを繰り返し押すと、60秒のシステムタイムアウトとシェルのクラッシュが発生する問題が修正されました。
- 深度バッファーの安定性が向上しました。
- フィードバック Hub に [ **共有** ] ボタンが追加され、ユーザーがフィードバックを簡単に共有できるようになりました。
- RoboRaid wan't が正しくインストールされているバグを修正しました。

### 既知の問題

- Zh-cn&platform-CN システム言語で問題が発生したため、音声コマンドで mixed reality のキャプチャやデバイスの IP アドレスの表示が行われません。
- 問題が発生した場合は、デバイスを起動した後に Cortana アプリを起動して、"コルタナさん" という音声のアクティブ化を使用する必要があります。 18362ビルドから更新した場合は、 **最初**に動作しなくなった、以前のバージョンの Cortana アプリ用の2つ目のアプリタイルが表示されることもあります。

## Windows ホログラフィック、バージョン1903、2020年5月の更新プログラム 
- ビルド18362.1061

この毎月の品質更新プログラムには、前に説明したように、チームが Windows ホログラフィックバージョン2004で動作しているために、注目の変更が含まれていません。

## Windows ホログラフィック、バージョン 1903 (2020 年4月の更新プログラム)
- ビルド18362.1059

**ダークモード (サポートされているアプリ)** 

多くの Windows アプリでは、ダークモードと簡易モードの両方がサポートされています。 HoloLens 2 のユーザーは、両方の配色パターンをサポートするアプリの既定のモードを選択できるようになりました。 お客様からのフィードバックに基づき、既定のアプリモードは "dark" に設定していますが、いつでもこの設定を簡単に変更できます。 [**設定 > システム > 色**] に移動し**て、「既定のアプリモードを選択**する」を検索します。

次の "in box" アプリは、ダークモードをサポートしています。
- 設定
- Microsoft Store
- メール
- カレンダー
- エクスプローラー
- フィードバック Hub
- OneDrive
- フォト
- 3D ビューアー
- 映画 & テレビ

**以下の更新プログラムも含まれています。** 
- シェルのオーバーレイが mixed reality キャプチャに含まれていることを確認します。
- 実際に廃止された開発者は、Device Portal の3D ビューページを使用して、アプリケーションのテストとデバッグを行うことができます。
- *HolographicDepthReprojectionMethod Dep のプロジェクション*アルゴリズムが使用されると、mixed reality キャプチャでのホログラムの安定性が向上しました。
- 32ビット ARM アプリで "WinRT IStreamSocketListener API クラスが登録されていません" エラーが修正されました。

## Windows ホログラフィック、バージョン 1903 (2020 年3月の更新プログラム) 
- ビルド18362.1056

更新プログラムの改善と修正:

- *HolographicDepthReprojectionMethod AutoPlanar*アルゴリズムが使用されているときに、mixed reality キャプチャでのホログラムの安定性が向上しました。
- 深度 MF サンプルにアタッチされている座標系が、パブリックドキュメントと一貫性があることを確認します。
- 顧客が device portal で大量のテキストを貼り付けることにより、開発者の生産性が向上しました。

## Windows ホログラフィック、バージョン 1903 (2020 年2月の更新プログラム) 
- ビルド18362.1053

更新プログラムの改善と修正:

- Unity アプリケーションの HolographicSpace プレゼンス API を一時的に無効にしました。 この変更により、"バックグラウンドで実行する" 設定が有効になっている場合でも、バイザーが反転したときに一部のアプリが停止する問題が回避されます。
- 手動トラッキングによるランダムな HUP クラッシュを修正しました。ユーザーは、数秒後に UI がフリーズしてシェルに戻ります。
- 手書きのトラッキングが改善され、人差し指を poke たときに、指の上の部分が予期せずに curl になる可能性が低くなりました。
- ヘッドトラッキング、空間マッピング、その他のランタイムの信頼性が向上しました。

## Windows ホログラフィック、バージョン 1903 (2020 年1月更新プログラム) 
- ビルド18362.1043
 
更新プログラムの改善と修正:

- HoloLens 2 エミュレーターで作業する場合の排他的なアプリの安定性が向上しました。

## Windows ホログラフィック、バージョン 1903-2019 年12月の更新プログラム 
- ビルド18362.1042

更新プログラムの改善と修正:

- 最後のステージの再生 (LSR) の修正が導入されました。 より正確に表示されるように、ホログラムのビジュアルレンダリングが改善されました。 この問題は、アプリによってホログラムの深度が正しく設定されない場合に、この更新後に顕著になります。
- 排他的なアプリと、排他的なアプリ間のナビゲーションの安定性が固定されています。
- デバイスが数日間スタンバイ状態になった後に、mixed reality キャプチャがビデオを録画できない問題を解決しました。
- ホログラムの安定性が向上しました。

## Windows ホログラフィック、バージョン 1903 (2019 年11月の更新プログラム) 
- ビルド18362.1039

更新プログラムの改善と修正:

- En CA と en-us の最初のセットアップ中に音声コマンド **選択** の機能が固定されました。
- 最新の Unity と Mixed Reality ツールキット (MRTK) バージョンに遠く離れたオブジェクトの視覚品質が向上しました。
- ホログラフィックアプリケーションで、[スタート] メニューを開き、[閉じる] まで一時停止状態になったときに発生する、アドレス指定の問題を修正しました。
- OpenXR ランタイム準拠の修正と、HoloLens 2 とエミュレーターの改善
