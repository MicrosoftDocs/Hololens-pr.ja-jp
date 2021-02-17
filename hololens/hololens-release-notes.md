---
title: HoloLens 2 のリリース ノート
description: 新しい HoloLens 2 リリースごとに、すべての更新プログラムを最新の情報に更新します。
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 02/16/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 7ab8eede6e48ed1a6cb4584188a80adbd832c169
ms.sourcegitcommit: ab35169529776f0682eeb8fa448c9d9e8f598513
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/17/2021
ms.locfileid: "11340556"
---
# HoloLens 2 のリリース ノート

HoloLens デバイスで生産性の高いエクスペリエンスを提供するために、引き続き機能、バグ、セキュリティ更新プログラムがリリースされます。 このページでは、毎月 HoloLens の新機能を確認できます。 最新の HoloLens 2 更新プログラムを取得[](hololens-update-hololens.md#check-for-updates-and-manually-update)するには、更新プログラムを確認して手動で更新するか、フル フラッシュ更新プログラム (FFU) を取得して Advanced [Recovery Companion](hololens-recovery.md#clean-reflash-the-device)経由でデバイスをフラッシュします。 ダウンロード [は](https://aka.ms/hololens2download) 最新の状態に保たれ、一般に利用可能な最新のビルドが提供されます。

>[!NOTE]
> Windows Insider の新機能のフライトを再び開始します。 We will be flighting to the Dev Channel for the latest updates. Windows Insider ビルドに追加された機能や更新プログラムについては [**、HoloLens Insider**](hololens-insider.md) のメモを引き続きご覧ください。 これらの更新プログラムを実際に組み合わせ、準備を整えます。

関連するリリース ノートを確認してください。

- [HoloLens エミュレーター のアーカイブにアクセスする](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

## Windows Holographic バージョン 20H2 - 2021 年 2 月更新プログラム
- ビルド 19041.1136

更新プログラムの機能強化と修正:

- 初期デバイスのセットアップとアプリの更新プログラムの保存に関する問題を修正します。
- HoloLens の以降のリリースのアップグレードとフライトに関する問題に解決します。
- HoloLens デバイスから eSIM ルート ストアから未使用のプレインストールされた証明書を削除しました。

## Windows Holographic バージョン 1903 - 2021 年 2 月更新プログラム
- ビルド 18362.1098

この毎月の品質更新プログラムには重要な変更が含まれているのではなく、Windows Holographic バージョン 2004 の最新ビルドを試してみてください。

## Windows Holographic バージョン 20H2 - January 2021 Update
- ビルド 19041.1134

更新プログラムの機能強化と修正:

- デバイスに多数のユーザーがいて、起動時、再開時、ユーザー切り替え時のパフォーマンスが向上しました。
- リサーチ モードの arm32 サポートが [追加されました](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)。

## Windows Holographic バージョン 1903 - 2021 年 1 月更新プログラム
- ビルド 18362.1091

この毎月の品質更新プログラムには重要な変更が含まれているのではなく、Windows Holographic バージョン 2004 の最新ビルドを試してみてください。

## Windows Holographic Version 20H2 – December 2020 Update
- ビルド 19041.1131

### アプリ インストーラーを使用して HoloLens 2 にアプリをインストールする

HoloLens 2 デバイスにアプリケーションをシームレスにインストールできる新しい機能 (アプリ インストーラー **)** が追加されています。 この機能は、非 **管理対象デバイスに対して既定で有効になります**。 企業の中断を防ぐため、現時点では管理対象デバイスでアプリ **インストーラーを** 利用できません。  

次の条件に当てはまる場合、デバイス**** は "管理対象" と見なされます。
- MDM [の登録](hololens-enroll-mdm.md)
- プロビジョニング パッケージ [で構成](hololens-provisioning.md)
- ユーザー [ID は](hololens-identity.md) Azure AD

開発者モードを有効にしたり、Device Portal を使用したりすることなく、アプリをインストールできます。  (USB または Edge 経由で) Appx バンドルをデバイスにダウンロードし、エクスプローラーで Appx バンドルに移動するだけで、インストールを開始するように求めるメッセージが表示されます。  または、Web [ページからインストールを開始します](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。  Microsoft Store からインストールしたアプリや MDM の LOB アプリ展開機能を使ってサイドロードするアプリと同様に、[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)アプリは署名ツール[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)でデジタル署名する必要があります。また、アプリを展開する前に、署名に使用する証明書が HoloLens デバイスによって信頼されている必要があります。

**アプリケーションのインストール手順。**

1.  デバイスが管理対象と見なされていないことを確認する
1.  HoloLens 2 デバイスの電源が入り、PC に接続されていることを確認する
1.  HoloLens 2 デバイスにサインインしている
1.  PC でカスタム アプリに移動し、app.appxbundle をdevicename\Internal Storage\Downloads にコピーします。   ファイルのコピーが完了したら、デバイスを切断できます。
1.  HoloLens 2 デバイスから [スタート] メニューを開き、[すべてのアプリ] を選択し、エクスプローラー アプリを起動します。
1.  [ダウンロード] フォルダーに移動します。 アプリの左側のパネルで、最初に [このデバイス] を選択し、[ダウンロード] に移動する必要があります。
1.  yourapp.appxbundle ファイルを選択します。
1.  アプリ インストーラーが起動します。 [インストール] ボタンを選択してアプリをインストールします。
インストールが完了すると、インストールされたアプリが自動的に起動します。

このフローをテストする [サンプル アプリは、Windows ユニバーサル サンプル GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) にあります。

アプリ インストーラーを使用して [HoloLens 2](app-deploy-app-installer.md)にアプリをインストールする完全なプロセスについて説明します。  

![アプリ インストーラーによる MRTK の例のインストール](images/hololens-app-installer-picture.jpg)

### 更新プログラムの機能強化と修正:

- 手の追跡では、以前は手が失われた可能性がある多くの新しいケースで追跡が維持されます。  これらの新しいケースの一部では、手のひらの位置だけがユーザーの実手に基づいて引き続き更新され、他のジョイントは前のポージに基づいて推定されます。  この変更により、スラップ、スロー、手の込み、手引きなどの動きの追跡の一貫性が向上します。  また、手が表面に近い場合やオブジェクトを持っている場合にも役立ちます。  手のジョイントが推測される場合、ジョイント[](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true)ごとの精度の値は "High" ではなく "Approximate" に設定されます。
- Azure アカウントの PIN のリセットAD「問題が発生しました。」というエラーが表示される問題を修正しました。
- ET、設定アプリ、新しいユーザー、または通知トーストからの虹彩を起動すると、ユーザーに表示されるポストブート OOBE クラッシュがはるかに少ない必要があります。
- ユーザーは、OOBE から正しいタイム ゾーンが提供されている必要があります。

## Windows Holographic バージョン 1903 – 2020 年 12 月更新プログラム
- ビルド 18362.1088

この毎月の品質更新プログラムには重要な変更はありません。最新の Windows Holographic バージョン 20H2 ~ 2020 年 12 月の更新プログラムと、ビルドに追加された新しいアプリ インストーラー機能を試してみてください。


## Windows Holographic バージョン 20H2
- ビルド 19041.1128

Windows Holographic バージョン 20H2 が使用可能にされ、HoloLens 2 のユーザーと IT 担当者に多くの新機能が提供されます。 自動目の位置指定から、[設定] の証明書マネージャー、キオスク モード機能の強化、および新しい Autopilot セットアップ機能まで。 この新しい更新プログラムにより、IT チームは HoloLens デバイスの構成と管理を細かく制御し、さらにシームレスなホログラフィック エクスペリエンスをユーザーに提供できます。 

この最新リリースは、バージョン 2004 の月次更新プログラムですが、今回は新機能を含む予定です。 メジャー ビルド番号は変わりません。Windows Update は、バージョン 2004 (ビルド 19041) の月次リリースを示します。 [設定] の [バージョン情報] 画面でビルド番号>、最新の利用可能なビルド 19041.1128 以上を使用している必要があります。 最新のリリースに更新するには、[設定] アプリを開き、[更新とセキュリティ] &し、[更新プログラムの確認] をタップします。 HoloLens の更新プログラムを管理する方法について詳しくは、このページをご [覧ください](https://docs.microsoft.com/hololens/hololens-updates)。

### Windows Holographic Version 20H2 の新機能  

| 機能                                              | 説明                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [視線の自動調整サポート](hololens-release-notes.md#auto-eye-position-support) | ユーザーが目追跡の調整を行わずに、目の位置をアクティブに計算します。   |
| [証明書マネージャー](hololens-release-notes.md#certificate-manager)   | 設定アプリから証明書をインストールおよび削除する新しい簡単な方法を許可します。     |
| [USB からの自動起動プロビジョニング](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | USB ドライブ上のプロビジョニング パッケージは、OOBE のプロビジョニング ページを自動的に確認します。                                                         |
| [OOBE でのプロビジョニング パッケージの自動確認](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | プロビジョニング パッケージは、プロビジョニング ページから OOBE 中に自動的に適用されます。                                                         |
| [UI を使用しない自動プロビジョニング](hololens-release-notes.md#automatic-provisioning-without-using-ui) | プロビジョニングの自動起動と自動確認を組み合わせる方法。 |
| [Autopilot と接続をWi-Fiする](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | イーサネット アダプターを必要とせずに、Wi-Fiから autopilot を使用します。 |
| [Tenantlockdown CSP と Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | テナントの登録とポリシーの適用後、デバイスがリセットまたは再フラッシュされると、そのテナントにのみデバイスを登録できます。 |
| [グローバルに割り当てられた](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | システム レベルでキオスクを適用し、すべてのユーザーに適用可能な複数のアプリ キオスク モードの新しい構成方法。                  |
| [複数アプリキオスクでアプリを自動起動する](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | 複数アプリのキオスク モードにサインインするときに自動的に起動するアプリケーションを設定します。                                                        |
| [エラーの処理に関するキオスク モードの動作の変更](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | キオスク モードの失敗により、フォールバックが制限されます。                                                                                                |
| [HoloLens ポリシー](hololens-release-notes.md#hololens-policies)                                    | HoloLens の新しいポリシー。     |
| [オフライン キオスクAD Azure グループ メンバーシップをキャッシュする](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | 新しいポリシーにより、ユーザーはグループ メンバーシップ キャッシュを使用して、設定された日数のキオスク モードをオフラインで使用できます。                                        |
| [HoloLens 2 の新しいデバイス制限ポリシー](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | HoloLens 2 で新しく有効にされたデバイス管理ポリシー。                                                                                |
| [HoloLens 2 の新しい電源ポリシー](hololens-release-notes.md#new-power-policies-for-hololens-2)       | 電源タイムアウト設定で新しくサポートされたポリシー。  |
| [ポリシーの更新](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | 更新の制御を許可する新しく有効にされたポリシー。           |
| [HoloLens 2 の [設定] ページの表示を有効にする](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | 設定アプリに表示されるページを選択するポリシー。             |
| [リサーチ モード](hololens-release-notes.md#research-mode) | HoloLens 2 でのリサーチ モードの使用。 |
| [レコーディングの長さが長くなった](hololens-release-notes.md#recording-length-increased) | MRC のレコーディングは 5 分に制限されなくなりました。 |
| [更新プログラムの機能強化と修正](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | 更新プログラムの追加の修正。   |

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

この情報は、後で他の調整情報 [と一緒に確認できます](hololens-calibration.md#auto-eye-position-support)。 

### 証明書マネージャー

- 新しい証明書マネージャーを通じて、デバイスのセキュリティとコンプライアンスのための監査、診断、検証ツールが改善されました。 この機能を使用すると、商用環境で大規模に証明書を展開、トラブルシューティング、検証できます。

Windows Holographic バージョン 20H2 では、HoloLens 2 設定アプリに証明書マネージャーを追加します。 [セキュリティと **証明書>更新&設定>移動します**。 この機能を使用すると、デバイス上の証明書を表示、インストール、および削除するための簡単で使い方が容易です。 新しい証明書マネージャーにより、管理者とユーザーは監査、診断、検証ツールが強化され、デバイスのセキュリティと準拠が維持されます。 

-   **監査:** 証明書が正しく展開されていることを検証する機能、または証明書が適切に削除されていることを確認する機能。 
-   **診断:** 問題が発生した場合、デバイスに適切な証明書が存在する場合は、時間を節約し、トラブルシューティングに役立ちます。 
-   **検証:** 証明書が目的の目的を持ち、機能することを確認すると、特に商用環境で証明書を大規模に展開する前に、大幅な時間を節約できます。

一覧で特定の証明書をすばやく見つけるには、名前、ストア、または有効期限で並べ替えるオプションがあります。 ユーザーは証明書を直接検索することもできます。 個々の証明書のプロパティを表示するには、証明書を選択し、[情報] をクリック **します**。 

証明書のインストールでは、.cer ファイルと .crt ファイルが現在サポートされています。 デバイス所有者は、ローカル コンピューターと現在のユーザーに証明書をインストールできます。 他のすべてのユーザーは現在のユーザーにのみインストールできます。 ユーザーは、設定 UI から直接インストールされた証明書のみを削除できます。 証明書が他の方法でインストールされている場合は、同じメカニズムでも削除する必要があります。

#### 証明書をインストールするには: 

1.  HoloLens 2 を PC に接続します。
1.  HoloLens 2 上の場所にインストールする証明書ファイルを配置します。
1.  [設定アプリ **とセキュリティ>更新&証明書>に**移動し、[証明書のインストール] を選択します。
1.  [ **ファイルのインポート]** をクリックし、証明書を保存した場所に移動します。
1.  [ストア **の場所] を選択します**。
1.  証明書ストア **を選択します**。
1.  **[インストール]** をクリックします。

これで、証明書がデバイスにインストールされます。

#### 証明書を削除するには: 
1. [設定] **アプリの [更新>セキュリティと証明書] >移動します**。
1. 検索ボックスで名前で証明書を検索します。
1. 証明書を選択します。
1. [削除 **] をクリックします。**
1. 確認 **を求める** メッセージが表示されたら、[はい] を選択します。

![設定アプリの証明書ビューアー](images/certificate-viewer-device.jpg)

![証明書 UI を使用して証明書をインストールする方法を示す図](images/certificate-device-install.jpg)

この情報は、後で新 [しい [証明書マネージャー] ページで確認できます](certificate-manager.md)。

### USB からの自動起動プロビジョニング

- OOBE 中にプロビジョニング パッケージ付き USB ドライブを使用する場合に、ユーザー操作を減らす自動プロセス。

このリリースの前に、ユーザーは OOBE 中にプロビジョニング画面を手動で起動して、ボタンの組み合わせを使用してプロビジョニングする必要があります。 これで、ユーザーは USB ストレージ ドライブ上のプロビジョニング パッケージを使って、ボタンの組み合わせをスキップできます。 

1. OOBE の最初の対話可能な瞬間にプロビジョニング パッケージを使って USB ドライブを接続する
1. デバイスをプロビジョニングする準備ができたら、プロビジョニング ページでプロンプトが自動的に開きます。 

注: デバイスの起動中に USB ドライブが電源に接続された状態の場合、OOBE は既存の USB ストレージ デバイスを列挙し、追加の USB ストレージ デバイスが接続されているのを監視します。

OOBE 中にプロビジョニング パッケージを適用する方法について詳しくは [、HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) のプロビジョニングに関するドキュメントをご覧ください。

USB からの [自動起動プロビジョニングの](hololens-provisioning.md#auto-launch-provisioning-from-usb) 詳細については、HoloLens のプロビジョニングに関するドキュメントを参照してください。

### OOBE でのプロビジョニング パッケージの自動確認
- [プロビジョニング パッケージ] ページが表示されているときに、ユーザーの操作を減らして自動的にプロセスを自動化すると、一覧に表示されているパッケージすべてが自動的に適用されます。

プロビジョニングのメイン画面が表示された場合、OOBE は、すべてのプロビジョニング パッケージの適用を自動的に開始する前に 10 秒カウント ダウンします。 ユーザーは、 [期待したパッケージ](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) を確認した後、この 10 分以内に確認またはキャンセルできます。

### UI を使用しない自動プロビジョニング
- プロビジョニングのためのデバイス操作を減らした場合の自動プロセスの組み合わせ。 

USB デバイスからのプロビジョニングの自動起動とプロビジョニング パッケージの自動確認を組み合わせることで、ユーザーはデバイスの UI を使用したり、デバイスを装着したりすることなく、HoloLens 2 デバイスを自動的にプロビジョニングできます。 複数のデバイスに対して同じ USB ドライブとプロビジョニング パッケージを引き続き使用できます。 これは、同じ領域に複数のデバイスを一度に展開する場合に便利です。 

1. Windows[構成デザイナーを使用して](hololens-provisioning.md)プロビジョニング[パッケージを作成します](https://www.microsoft.com/store/productId/9NBLGGH4TX22)。 
1. パッケージを USB ストレージ ドライブにコピーします。
1. [HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) から [19041.1361 以降のビルドをフラッシュします](https://aka.ms/hololens2previewdownload)。 
1. Advanced [Recovery Companion が](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 完了したら、デバイスのフラッシュを完了し、USB-C ケーブルを取り外します。 
1. USB ドライブをデバイスに接続します。
1. HoloLens 2 デバイスが OOBE で起動すると、USB ドライブ上のプロビジョニング パッケージが自動的に検出され、プロビジョニング ページが起動します。
1. 10 秒後、デバイスはプロビジョニング パッケージを自動的に適用します。 

これで、デバイスが構成され、[プロビジョニング成功] [画面が表示されます](hololens-provisioning.md#automatic-provisioning-without-using-ui)。

### Autopilot と接続をWi-Fiする
- 接続されているデバイスで Autopilot が機能する機能を有効にすることで、イーサネットを使用してハードウェアのニーズを軽減する USB-C アダプターWi-Fiしました。

OOBE 中に、HoloLens 2 を Wi-Fi に接続すると、OOBE はデバイスの Autopilot プロファイルを確認します。 見つかった場合は、残りの AAD 参加フローと登録フローを完了するために使用されます。 つまり、USB-C または Wi-Fi から USB-C アダプターへのイーサネットの使用は要件ではなくなりましたが、OOBE の初めに指定すると、引き続き機能します。 [HoloLens 2 デバイス用の Autopilot について詳しくは、次をご覧ください](hololens2-autopilot.md)。

### Tenantlockdown CSP と Autopilot
- デバイスのリセットまたは再フラッシュを行っても、デバイスをテナントにロックすることにより、デバイスを組織のテナントに保持します。 プロビジョニングを介したアカウントの作成を禁止することにより、セキュリティを強化します。 

HoloLens 2 デバイスでは [、Windows Holographic バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2)の TenantLockdown CSP がサポートされています。 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP は、HoloLens 2 が Autopilot のみを使用して MDM 登録に関連付けられるようにします。 TenantLockdown CSP の RequireNetworkInOOBE ノードが HoloLens 2 で true または false (最初に設定された) 値に設定されると、その値は、再フラッシュ、OS 更新プログラムなどにもかかわらずデバイスに残ります。 

HoloLens 2 で TenantLockdown CSP の RequireNetworkInOOBE ノードが true に設定されると、OOBE は、ネットワーク接続後、Autopilot プロファイルが正常にダウンロードおよび適用されるまで無期限に待機します。 

HoloLens 2 で TenantLockdown CSP の RequireNetworkInOOBE ノードが true に設定されると、OOBE では次の操作が許可されなくなります。 
- ランタイム プロビジョニングを使用したローカル ユーザーの作成 
- ランタイム プロビジョニングによる Azure AD への参加操作の実行 
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

![ポリシーがデバイスに適用される時のデバイス内ビュー。](images/hololens-autopilot-lockdown.png)

この情報は、Tenantlockdown CSP と Autopilot の下で Autopilot の他の部分と一緒 [に見つめ直す事が可能です](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)。

### グローバル割り当てアクセス – キオスク モード
- システム レベルでキオスク モードを適用する新しいキオスク方式を有効にすることで、キオスクの ID 管理が削減されます。

この新機能により、IT 管理者は HoloLens 2 デバイスを複数のアプリ キオスク モード用に構成できます。これはシステム レベルで適用可能で、システム上の ID とのアフィニティは持たず、デバイスにサインインするユーザー全員に適用されます。 この新機能の詳細については [、HoloLens](hololens-global-assigned-access-kiosk.md)のグローバル割り当てアクセス キオスクをご確認ください。

### 複数アプリキオスク モードでのアプリケーションの自動起動 
- アプリの自動起動に重点を置いてエクスペリエンスを提供し、キオスク モードエクスペリエンス用に選択された UI とアプリの選択をさらに増やします。

複数アプリのキオスク モードにのみ適用され、割り当てられたアクセスの構成で以下の強調表示された属性を使って自動起動を指定できるアプリは 1 つのみです。 

ユーザーがサインインすると、アプリケーションが自動的に起動します。 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### エラーの処理に関するキオスク モードの動作の変更
- キオスク モードのエラーで利用可能なアプリを排除することで、より安全なキオスク モード。 

以前は、キオスク モードの適用でエラーが発生した場合、HoloLens はスタート メニューにすべてのアプリケーションを表示するために使用しました。 Windows Holographic Version 20H2 では、エラーが発生した場合、スタート メニューに以下のようにアプリは表示されません。 

![失敗したときのキオスク モードの画像。](images/hololens-kiosk-failure-behavior.png )

### HoloLens ポリシー
- デバイス管理用に作成された HoloLens 専用のデバイス管理オプション。 

Windows Holographic バージョン 20H2 の HoloLens 2 デバイス用に、新しい Mixed Reality ポリシーが作成されました。 新しい制御可能な設定には、明るさの設定、音量の設定、Mixed Reality キャプチャでのオーディオ録音の無効化、診断を収集できる時間の設定、AAD グループ メンバーシップ キャッシュが含まれます。  

| 新しい HoloLens ポリシー                                | 説明                                                                               | 備考                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 明るさボタンを無効にし、ボタンを押しても明るさが変わりません。       | 1 はい、0 はい (既定)                                                |
| MixedReality\VolumeButtonDisabled                  | ボリューム ボタンを無効にし、押してもボリュームが変更されません。               | 1 はい、0 いいえ (既定)                                                |
| MixedReality\MicrophoneDisabled                    | HoloLens 2 でオーディオ録音が行えなくマイクを無効にします。                      | 1 はい、0 はい (既定)                                                |
| MixedReality\FallbackDiagnostics                   | 診断ログを収集できる場合の動作を制御します。                               | 0 無効、1 デバイス所有者に対して有効、2 すべて有効 (既定) |
| MixedReality\HeadTrackingMode                      | 将来の使用のために予約されています。                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Azure AD グループをターゲットとするキオスクで Azure メンバーシップ キャッシュが使用される日数ADします。 | 以下を参照してください。                                                           |

### オフライン キオスクAD Azure グループ メンバーシップをキャッシュする
- 最大 60 日間、AAD グループでオフライン キオスクを使用できます。

このポリシーは、Azure AD グループ メンバーシップ キャッシュを、サインインしているユーザーの Azure AD グループをターゲットとする割り当てられたアクセス構成に使用できる日数を制御します。 このポリシー値を 0 より大きい値に設定すると、それ以外の場合はキャッシュが使用されません。  

名前: AADGroupMembershipCacheValidityInDays URI 値: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最小 - 0 日  
最大 - 60 日 

このポリシーを正しく使用する手順は次のとおりです。 
1. Azure AD グループをターゲットとするキオスクのデバイス構成プロファイルを作成し、HoloLens デバイスに割り当てる。 
1. このポリシー値を希望する日数 (> 0) に設定し、HoloLens デバイスに割り当てるカスタム OMA URI ベースのデバイス構成を作成します。 
    1. URI 値は、OMA-URI テキスト ボックスに ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays として入力する必要があります。
    1. 値は、最小/最大許容値の間で指定できます。
1. HoloLens デバイスを登録し、両方の構成がデバイスに適用されるのを確認します。 
1. インターネットが利用可能AD Azure ユーザー 1 のサインインを許可し、ユーザーのサインインと Azure AD グループ メンバーシップが正常に確認されると、キャッシュが作成されます。 
1. Azure ADユーザー 1 は HoloLens をオフラインにし、ポリシー値で X 日数が許可されている限りキオスク モードで使用できます。 
1. 他の Azure AD ユーザー N に対して手順 4 と 5 を繰り返し実行できます。ここでの重要なポイントは、すべての Azure AD ユーザーがインターネットを使用してデバイスにサインインする必要がある点です。少なくとも 1 回は、キオスク構成の対象となる Azure AD グループのメンバーと判断できます。 
 
> [!NOTE]
> Azure アプリケーションに対して手順 4 が実行されるまでAD"切断された" 環境で説明されているエラー動作が発生します。 

### HoloLens 2 の新しいデバイス制限ポリシー
- プロビジョニング パッケージの追加や削除のブロックなど、特定のデバイス管理ポリシーをユーザーが管理できます。

HoloLens 2 デバイスの管理オプションを追加できる新しく有効にされたポリシー。 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

AllowAddProvisioningPackage と AllowRemoveProvisioningPackage のこれら 2 つの新しいポリシーは、共通デバイスの制限に [追加されています](hololens-common-device-restrictions.md)。

> [!NOTE]
> [RemoteLock に関して](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)、HoloLens は ./Vendor/MSFT/RemoteLock/Lock 構成のみをサポートします。 リセットや復元などの PIN を扱う構成はサポートされていません。

### HoloLens 2 の新しい電源ポリシー
- HoloLens が電源ポリシーを使用してスリープまたはロックする場合のその他のオプション。 

これらの新しく追加されたポリシーにより、管理者はアイドル タイムアウトなどの電源状態を制御できます。 各ポリシーの詳細については、そのポリシーのリンクをクリックしてください。

|     ポリシー ドキュメントへのリンク                |     備考                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Windows 構成デザイナーで使用する値の例 (例:  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Windows 構成デザイナーで使用する値の例 (例:  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Windows 構成デザイナーで使用する値の例 (100 など)                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Windows 構成デザイナーで使用する値の例 (100 など)                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows 構成デザイナーで使用する値の例 (例:   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows 構成デザイナーで使用する値の例 (例:  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

DisplayOffTimeoutOnBattery と DisplayOffTimeoutPluggedIn のこれら 2 つの新しいポリシーは、一般的なデバイスの制限 [に追加されています](hololens-common-device-restrictions.md)。

> [!NOTE]
> HoloLens 2 で一貫したエクスペリエンスを提供するには、DisplayOffTimeoutOnBattery と StandbyTimeoutOnBattery の両方の値が同じ値として設定されている必要があります。 DisplayOffTimeoutPluggedIn と StandbyTimeoutPluggedIn にも同じです。 モダン スタンバイ [の詳細については、「表示、スリープ、休止](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) 状態のアイドル タイマー」を参照してください。

### HoloLens の新しく有効にされた更新ポリシー
- 更新プログラムをインストールする場合や、[更新の一時停止] ボタンを無効にして更新を確認するその他のオプション。

これらの更新ポリシーは、HoloLens 2 デバイスで有効になっています。
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

これらの更新ポリシーと HoloLens デバイスで使用する方法の詳細については [、「HoloLens](hololens-updates.md)更新プログラムの管理」を参照してください。

### HoloLens 2 の [設定] ページの表示を有効にする
- 設定アプリの UI コントロールが増え、限られたページの選択を表示すると混乱する可能性があります。

IT 管理者がシステム設定アプリの特定のページの表示やアクセスを防止したり、指定したページを除くすべてのページに対して表示またはアクセスを行えるようにするポリシーを有効にしました。 この機能を完全にカスタマイズする方法については、以下のリンクをクリックしてください。

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

HoloLens 2 でカスタマイズできるページ設定については、「設定 [URI」ページをご覧ください](settings-uri-list.md)。 
 
![設定アプリで変更されたアクティブ時間のスクリーンショット](images/hololens-page-visibility-list.jpg)

### リサーチ モード
リサーチ モードでは、HoloLens 2 はコンピューター ビジョンリサーチの強力なツールになります。 以前のエディションと比較すると、HoloLens 2 のリサーチ モードには次の利点があります。
-   HoloLens (第 1 世代) リサーチ モードで公開されているセンサーに加えて、加速度計、ジャイロスコープ、磁力計などの IMU センサー アクセスが提供されます。
-   HoloLens 2 は、リサーチ モードと共に使用できる新機能を提供します。 具体的には、より豊富な実験セットを提供できる、明確な手追跡および追跡 API へのアクセスです。

リサーチ ャーは、HoloLens デバイスでリサーチ モードを有効にし、これらすべての外部向け未加工イメージ センサー ストリームにアクセスするオプションを利用できます。 HoloLens 2 のリサーチ モードでは、加速度計、ジャイロスコープ、磁力計の読み取り値にもアクセスできます。 ユーザーのプライバシーを保護するために、未加工の視線追跡カメラ画像はリサーチ モードでは使用できませんが、視線方向は既存の API から利用できます。

技術的な詳細 [については、リサーチ モードの](https://docs.microsoft.com/windows/mixed-reality/research-mode) ドキュメントを参照してください。

### レコーディングの長さが長くなった
お客様からのフィードバックにより、Mixed Reality キャプチャの記録 [の長さが長くなっています](holographic-photos-and-videos.md)。 Mixed Reality キャプチャは既定で 5 分に制限されず、使用可能なディスク領域に基づいて最大記録長が計算されます。 デバイスは、利用可能なディスク領域に基づいてビデオ録画の最大再生時間を、合計ディスク領域の 80% まで推定します。

> [!NOTE]
> 次のいずれかの場合、HoloLens は既定のビデオ録画の長さ (5 分) を使用します。
> - 推定最大記録時間は、既定の 5 分よりも小さくてす。
> - 使用可能なディスク領域は、ディスク領域全体の 20% 未満です。

完全な要件については、ホログラフィックの写真と [ビデオのドキュメントをご覧](holographic-photos-and-videos.md#maximum-recording-length) ください。 

### 更新プログラムの機能強化と修正:
- OOBE のその他の画面が濃色モードになります。
- 最新のプライバシーに関する声明をオンラインで示す必要があるコンテンツについて説明します。
- ユーザーがプロビジョニング パッケージを使用して VPN プロファイルをプロビジョニングできない問題に対処しました。
- VPN 接続のプロキシ構成の問題を修正しました。
- AllowUsbConnection の NCM で MDM による USB 関数の列挙を無効にするポリシーを更新しました。
- デバイスが単一アプリキオスクとして設定されているときに、HoloLens デバイスがメディア転送プロトコル (MTP) を使ってエクスプローラーに表示されなく問題に [対処しました](hololens-kiosk.md)。 [なお、ALLOWUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)ポリシーを使って MTP (および USB 接続全般) を無効にできます。
- [スタート] メニューのアイコンがキオスク モードで正しくスケーリングされる問題を修正しました。
- Azure グループを対象としたキオスク モードと HTTP キャッシュが干渉するAD修正しました。
- 開発者モードを無効にし、開発者モードを再び有効にしない限り、プロビジョニング パッケージで開発者モードを有効にした後、ユーザーが [ペアリング] ボタンを使用できない問題を修正しました。

## Windows Holographic バージョン 1903 - November 2020 Update
- ビルド 18362.1085

この毎月の品質更新プログラムには、重要な変更点が含まれているのではなく、Windows Holographic バージョン 20H2 の最新機能リリース ビルドを試してみてください。

## Windows Holographic バージョン 2004 - October 2020 Update
- ビルド 19041.1124
 
更新プログラムの機能強化と修正:

- ランタイム システムの障害の原因となる不要なチェックを削除しました。

## Windows Holographic バージョン 1903 - October 2020 Update
- ビルド 18362.1081

この毎月の品質更新プログラムには重要な変更が含まれているのではなく、Windows Holographic バージョン 2004 の最新ビルドを試してみてください。

## Windows Holographic バージョン 2004 - 2020 年 9 月更新プログラム
- ビルド 19041.1117

更新プログラムの機能強化と修正:

- SupportsMultipleInstances="true" が appxmanifest に存在する場合に、Visual Studioがアプリケーションをデバッグしない問題に対応します。
- このリリースには、ネットワーク プロキシを使用したインターネット検出の失敗に対処するための NCSI プロキシ検出の修正が含まれています。 NCSI では、コンピューター プロキシとプロファイルごとのプロキシを使用してインターネット接続を検出できます。 ユーザーごとのプロキシは、今後のリリースで NCSI でサポートされる予定です。
- ほとんどの Windows Mixed Reality デバイスでは、ユーザーの頭が中間位置で前方を見ている場合、前方方向ベクトルは地に平行です。 ただし、以前のバージョンの HoloLens 2 では、ベクトルがディスプレイ パネルに対して垂直になるように配置され、理想的な向きに対して数度下に傾きます。 新しいバージョンの HoloLens 2 では、フォーム ファクター間のセマンティック整合性を確保するためにこれを修正しました。
- ハンド トラッキングの堅牢性が向上し、特定のシナリオで損失を追跡する数を減らします。
- このリリースには、ビデオ キャプチャの問題の原因である可能性がある、オーディオ タイムスタンプの品質を向上させる修正プログラムが含まれています。

## Windows Holographic バージョン 1903 - 2020 年 9 月更新プログラム
- ビルド 18362.1079

更新プログラムの機能強化と修正:

- ほとんどの Windows Mixed Reality デバイスでは、ユーザーの頭が中間位置で前方を見ている場合、前方方向ベクトルは地に平行です。 ただし、以前のバージョンの HoloLens 2 では、ベクトルがディスプレイ パネルに対して垂直になるように配置され、理想的な向きに対して数度下に傾きます。 新しいバージョンの HoloLens 2 では、フォーム ファクター間のセマンティック整合性を確保するためにこれを修正しました。
- ハンド トラッキングの堅牢性が向上し、特定のシナリオで損失を追跡する数を減らします。

## Windows Holographic バージョン 2004 - August 2020 Update
- ビルド 19041.1113

更新プログラムの機能強化と修正:

- 設定アプリは、虹彩登録または目追跡調整エクスペリエンスにユーザーをフォローしなくなりました。
- OOBE 中にプロビジョニング パッケージを適用してデバイスの名前を変更し、他の操作 (ネットワークへの接続など) を実行するバグを修正しました。名前の変更により、デバイスの再起動後に他の操作を実行できなかった場合があります。
- 初期デバイスのセットアップ フローの配色が変更され、視覚的な品質が向上しました。

## Windows Holographic バージョン 1903 - August 2020 Update
- ビルド 18362.1074

この毎月の品質更新プログラムには重要な変更が含まれているのではなく、Windows Holographic バージョン 2004 の最新ビルドを試してみてください。

## Windows Holographic バージョン 2004 - July 2020 Update
- ビルド 19041.1109

更新プログラムの機能強化と修正:

- 開発者は、Device Portal にセキュリティで保護された接続が必要な場合に、有効にするか無効にするか選択できます。
- OS の更新後にアプリケーションを起動する場合の信頼性が向上しました。
- 既定の受信トレイの明るさを 100% に変更しました。
- HoloLens 2 の Windows Device Portal の HTTPS 転送に関する問題に対処しました。

## Windows Holographic バージョン 1903 - July 2020 Update
- ビルド 18362.1071

更新プログラムの機能強化と修正:

- 追跡を失った、または追跡を取り戻す際に Unity アプリケーションでホログラムが消える原因となる可能性がある問題を修正しました。
- 特定のデバイスでハードウェア アクセラレータを使って HoloLens エミュレーターを使用している間に排他的な HoloLens アプリがシェルにクラッシュする原因となる問題を修正しました。
- HoloLens 2 の Windows Device Portal の HTTPS 転送に関する問題に対処しました。

## Windows Holographic バージョン 2004 - June 2020 Update
- ビルド 19041.1106

更新プログラムの機能強化と修正:

- カスタム MRC レコーダーが指定されていない場合、特定のプロパティに対して新しい既定値が設定されます。
  - *MRC ビデオ効果について*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (イマーシブ ヘッドセット)
  - *MRC オーディオ効果の場合*:
    - LoopbackGain (Windows Device Portal の Mixed Reality キャプチャ ページの現在の "アプリ オーディオ ゲイン" 値)
    - MicrophoneGain (Windows Device Portal の Mixed Reality キャプチャ ページの現在の "Mic Audio Gain" 値)
- Mixed Reality キャプチャ シナリオで音質を向上させるバグを修正しました。 具体的には、この修正プログラムを実行すると、[スタート] メニューが表示されているときに、録音中のオーディオ **の画面表示が** 削除される必要があります。
- 記録されたビデオのホログラムの安定性が向上しました。
- デバイスがスタンバイ状態を数日間残した後、Mixed Reality キャプチャでビデオを記録できない問題を解決しました。
- HolographicSpace.UserPresence API は、通常、Unity アプリケーションでは無効です。 この動作により、"バックグラウンドでの実行" 設定が有効になっている場合でも、バイザーが反転した場合に一部のアプリが一時停止する問題が回避されます。 この API は、Unity バージョン 2018.4.18 以降および 2019.3.4 以降で有効になっています。
- Wi-Fi 接続を使用して Device Portal にアクセスすると、Web ブラウザーで無効な証明書が原因でアクセスが妨げる可能性があります。 デバイス証明書が以前に信頼されている場合でも、ブラウザーから "ERR_SSL_PROTOCOL_ERROR" などのエラーが報告される場合があります。 この場合、セキュリティの警告を無視するオプションは提供されませんので、Device Portal に進む必要はありません。 この更新プログラムは問題を解決しました。 デバイス証明書が以前にダウンロードされ、ブラウザーのセキュリティ警告を削除するために PC で信頼されている場合、SSL エラーが発生した場合、ブラウザーのセキュリティ警告に対処するには、新しい証明書をダウンロードして信頼する必要があります。
- MSIX パッケージを使用してアプリをインストールできるランタイム プロビジョニング パッケージを作成する機能を有効にしました。
- ユーザーがデバイスのシャットダウン**時に**Mixed Reality ホームからすべてのホログラムを自動的に削除できる設定システム ホログラムに設定  >  ****  >  **** を追加しました。
- HoloLens エミュレーターでピクセル形式を変更して黒にレンダリングする HoloLens アプリの問題を修正しました。
- 虹彩ログイン中にクラッシュを引き起こすバグを修正しました。
- 既に現在のアプリでストアのダウンロードが繰り返される問題を修正しました。
- イマーシブ アプリが Microsoft Edge を繰り返し開くのを防ぐためのバグを修正しました。
- 1903 リリースから更新した後、初期起動中にフォト アプリが起動する問題を修正しました。
- パフォーマンスと信頼性の向上。

## Windows Holographic バージョン 1903 - June 2020 Update
- ビルド 18362.1064

更新プログラムの機能強化と修正:

- カスタム MRC レコーダーは、指定されていない場合、特定のプロパティの新しい既定値を持っています。
  - *MRC ビデオ効果について*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (イマーシブ ヘッドセット)
  - *MRC オーディオ効果の場合*:
    - LoopbackGain (Windows Device Portal の Mixed Reality キャプチャ ページの現在の "アプリ オーディオ ゲイン" 値)
    - MicrophoneGain (Windows Device Portal の Mixed Reality キャプチャ ページの現在の "Mic Audio Gain" 値)
- HolographicSpace.UserPresence API は、通常、Unity アプリケーションでは無効です。 この動作により、バックグラウンドで実行する設定が有効になっている場合でも、バイザーが反転した場合に一部のアプリが一時停止する問題を回避できます。 この API は、Unity バージョン 2018.4.18 以降、および 2019.3.4 以降で有効になっています。
- HoloLens エミュレーターでピクセル形式を変更して黒にレンダリングする HoloLens アプリの問題を修正しました。
- 1903 リリースから更新した後、初期起動中のフォト アプリの起動に関する問題を修正しました。

## Windows Holographic バージョン 2004  
- ビルド - 19041.1103

HoloLens 2、Windows *Holographic バージョン 2004 の 2020* 年 5 月のメジャー ソフトウェア更新プログラムには、Windows Autopilot のサポート、アプリのダーク モード、5G/LTE ホットスポットの USB イーサネット サポートなど、多くの新しい機能が含まれています。 最新のリリースに更新するには、設定アプリ**** を開き、[更新とセキュリティ] &し、[更新プログラムの確認] ボタン    **** **を選択**   します。 

|             機能                              |          説明                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Windows AutoPilot を使用して、新しいデバイスを事前構成し、シームレスに実稼働用にセットアップする                 |
|       FIDO 2 のサポート                             |          共有デバイスで高速かつ安全な認証を可能にする FIDO2 セキュリティ キーのサポート            |
|       プロビジョニングの強化                      |          USB ドライブから HoloLens にプロビジョニング パッケージをシームレスに適用する                              |
|       アプリケーションのインストール状態                 |          MDM 経由で HoloLens 2 にプッシュされたアプリの設定アプリのインストール状態を確認する               |
|       構成サービス プロバイダー (CSP)   |          管理制御機能を強化する新しい構成サービス プロバイダーを追加しました                 |
|       USB 5G/LTE のサポート                       |          拡張された USB イーサネット機能により、5G/LTE のサポートが可能                                    |
|       濃色アプリ モード                              |          濃色モードと淡色モードの両方をサポートし、表示エクスペリエンスを向上させるアプリで利用できる濃色アプリ モード        |
|       音声コマンド                             |          HoloLens をハンズフリーで制御する追加のシステム音声コマンドのサポート                           |
|       手の追跡の機能強化                 |          手の追跡が改善され、ボタンと 2D スレート操作の精度が向上                        |
|       品質の向上と修正                 |          プラットフォーム全体のさまざまなシステム パフォーマンスと信頼性の向上                            |

### Windows Autopilot のサポート

Windows Autopilot for HoloLens 2 を使うと、デバイス販売チャネルは HoloLens を Intune テナントに事前登録できます。 デバイスが到着すると、テナントの下に共有デバイスとして自己展開する準備が整います。 自己展開を利用するには、セットアップの最初の画面で USB-C からイーサネットを使用してネットワークに接続する必要があります。

ユーザーが Autopilot の自己展開プロセスを開始すると、次の手順が完了します。

1. デバイスを Azure Active Directory (Azure AD) に参加させます。
1. Azure AD を使用して、Microsoft Intune (または別の MDM サービス) にデバイスを登録します。
1. デバイスを対象としたポリシー、証明書、およびネットワーク プロファイルをダウンロードします。
1. デバイスをプロビジョニングします。
1. ユーザーにサインイン画面を提示します。

詳しくは [、Windows Autopilot for HoloLens 2 評価ガイドをご覧ください](https://docs.microsoft.com/hololens/hololens2-autopilot)。

*今すぐ AutoPilot プレビューに参加するには、アカウント マネージャーにお問い合わせください。 Autopilot 対応デバイスは間もなく出荷を開始します。*

### FIDO2 セキュリティ キーのサポート

HoloLens デバイスを、仕事や学校の環境で共有するユーザーもいます。 そのため、ユーザーは長いユーザー名とパスワードを入力せずに簡単に入力できる必要があります。 Fast Identity Online (FIDO) を使用すると、組織内のすべてのユーザー (Azure AD テナント) は、ユーザー名やパスワードを入力せずに HoloLens にシームレスにサインインできます。

FIDO2 セキュリティ キーは、任意のフォーム ファクターで使用できる"不必要な" 標準ベースのパスワードレス認証方法です。 FIDO は、パスワードレス認証のオープンな標準です。 これにより、ユーザーと組織は、ユーザー名やパスワードを使用せずにリソースにサインインできます。 代わりに、外部セキュリティ キーまたはデバイスに組み込みのプラットフォーム キーを使用します。

To get started, [see Enable passwordless security key sign-in](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key).

### プロビジョニング パッケージによる MDM 登録の強化

プロビジョニング パッケージを使って HoloLens 構成を設定するには、HoloLens の Out-Of-Box Experience を使うのではなく、構成ファイルを使います。 以前は、プロビジョニング パッケージを HoloLens の内部メモリにコピーする必要があります。 複数の HoloLens デバイスで再利用しやすく、デバイスを並行してプロビジョニングできるよう、USB ドライブ上に追加できます。 プロビジョニング パッケージでは、デバイス管理に登録するフィールドもサポートされるので、プロビジョニング後に手動でセットアップする必要はありません。

以下の手順をお試しください。

1. Windows ストアから PC に最新バージョンの Windows 構成デザイナーをダウンロードします。
1. **[HoloLens デバイスプロビジョニング**  >  **HoloLens 2 デバイスのプロビジョニング] を選択します**。
2. 構成プロファイルを作成します。 次に、作成されたファイルを USB-C ストレージ デバイスにコピーします。
3. USB-C デバイスを新しくフラッシュした HoloLens に接続します。 次に、**ボリューム ダウン電源**  +  **ボタン**を押して、プロビジョニング パッケージを適用します。

### Line-of-Business アプリケーションのインストール状態

HoloLens では、業務アプリの MDM アプリの展開と管理が重要です。 管理者とユーザーは、監査と診断のためにアプリのインストール状態を表示する必要があります。 このリリースでは、「Settings **** Accounts Access work or  >  ****  >  **school**Click on your account  >  Info」に詳細**を追加**  >  **しました**。

### その他の CSP とポリシー

構成 [サービス プロバイダー (CSP) は](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) 、デバイスの構成設定を読み取り、設定、変更、または削除するインターフェイスです。 このリリースでは、展開された HoloLens デバイスよりも管理者が持っているコントロールを増やすポリシーのサポートが追加されました。 HoloLens でサポートされている CSP の一覧については [、「NetworkQoSPolicy CSP」を参照してください](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。

このリリースの新機能:

**Policy CSP** 

ポリシー構成サービス プロバイダーを使用すると、企業は Windows デバイスでポリシーを構成できます。 このリリースでは、HoloLens の新しいポリシーを追加しました。このポリシーは、ここに記載されています。 詳しくは [、HoloLens 2 でサポートされているポリシー CSP に関するページをご覧ください](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)。  

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

NetworkQoSPolicy 構成サービス プロバイダーは、ネットワークサービス品質 (QoS) ポリシーを作成します。 QoS ポリシーは、一連の照合条件に基づいて、ネットワーク トラフィックに一連のアクションを実行します。 詳細については [、「NetworkQoSPolicy CSP」を参照してください](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。

### 5G/LTE テザリング デバイス向け USB イーサネット サポートの拡張

USB 経由で HoloLens 2 に接続するときに、5G/LTE 電話や Wi-Fi ホットスポットなどの特定のモバイル ブロードバンド デバイスを有効にするためにサポートが追加されました。 これらのデバイスは、別のイーサネット **接続としてネットワーク** 設定に表示されます。 (外部ドライバーを必要とするモバイル ブロードバンド デバイスはサポートされていません。この機能により、テザリングWi-Fi十分なパフォーマンスが得Wi-Fi高帯域幅接続が可能になります。 サポートされている USB デバイスの詳細については、「Bluetooth デバイスと [USB-C デバイスへの接続」を参照してください](https://docs.microsoft.com/hololens/hololens-connect-devices)。  

### 手の追跡の機能強化

このリリースでは、手による追跡に関する次の点が改善されています。

- **ポイントの位置を示す安定性:** 手のひらに人差し指が入り込むのをシステムが抵抗する。 この変更により、ボタンを押す、コンテンツを入力する、コンテンツをスクロールする、など、精度が向上します。 
- **偶発的なエア タップの削減:** エアタップ ジェスチャの検出が改善されました。 いくつかの一般的なシナリオでは、手を手前に置くなど、偶発的なアクティブ化が少なされました。
- **ユーザー 切り替えの信頼性:** デバイスを共有すると、システムは手のサイズを更新する速度と信頼性が向上しました。
- **ハンド盗みを減らします。** センサーを 2 つ以上の手で見る場合の処理が改善されました。 複数のユーザーが近くで作業している場合、追跡された手がユーザーからシーン内の他のユーザーの手に「ジャンプ」する可能性がはるかに低くなります。
- **システムの信頼性:** デバイスの負荷が高いときに手の追跡が機能しなしない問題を修正しました。

### 濃色モード

多くの Windows アプリでは、濃色モードと淡色モードの両方がサポートされています。 HoloLens 2 ユーザーは、両方をサポートするアプリの既定のモードを選択できます。 更新後、既定のアプリ モードは "濃色" になりますが、この設定は簡単に**** 変更できます。[設定システムの色] に移動します。既定のアプリ  >  ****  >  ****  >  **モードを選択します**。 

これらの "インボックス" アプリは、濃色モードをサポートしています。 

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

![濃色モードのウィンドウのタイル表示](images/DarkMode.jpg)

### システム音声コマンド

デバイス上の任意のアプリで音声コマンドを使用できます。 詳しくは、「音声を [使って HoloLens を操作する」をご覧ください](https://docs.microsoft.com/hololens/hololens-cortana)。 [HoloLens 2 でサポートされている言語も参照してください](https://docs.microsoft.com/hololens/hololens2-language-support)。  

### Cortana の更新

更新されたアプリは Microsoft 365 と統合され、デバイス全体で作業をUS-Englishしています。 HoloLens 2 では、Cortana は、ボリュームの調整や再起動など、特定のデバイス固有のコマンドをサポートしなくなりました。 これらのオプションは、新しいシステム音声コマンドでサポートされています。 新しい Cortana アプリの詳細については、ブログを参照 [してください](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)。

### 品質の向上と修正

更新プログラムの機能強化と修正プログラム:  
- アクティブなディスプレイ調整システムを導入しました。 この機能により、ホログラムの安定性と配置が向上します。 頭を横から横に動かすと、このボタンは配置された場所に残ることになります。
- HoloLens へのWi-Fiが定期的に中断されるバグを修正しました。 アプリケーションが待機時間の短いストリーミングが必要な場合は [、SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)関数を呼び出して修正プログラムを実装します。
- リサーチ モードでストリーミング中に発生したデバイスハングを修正しました。
- セッションを再開始するときに、サインイン画面に適切なユーザーが表示されない場合があるというバグを修正しました。
- ユーザーが設定を使用して MDM ログをエクスポートできない問題を **修正しました**。
- Out-Of-Box Setup の直後の目追跡の精度が予想より低い可能性がある問題を修正しました。
- 特定の条件下で、目追跡サブシステムが初期化または調整の実行に失敗する問題を修正しました。
- 既に調整済みのユーザーに対して目の調整を求める問題を修正しました。
- 目の調整中にドライバーがクラッシュする問題を修正しました。
- 電源ボタンを繰り返し押すと、60 秒のシステム タイムアウトとシェル クラッシュが発生する可能性がある問題を修正しました。
- 深度バッファーの安定性が向上しました。
- ユーザーがフィードバック **を** 簡単に共有できるよう、フィードバック Hub に [共有] ボタンを追加しました。
- RoboRaid wan が正しくインストールされないバグを修正しました。

### 既知の問題

- zh-CN システム言語の問題により、音声コマンドが Mixed Reality キャプチャを取得したり、デバイスの IP アドレスを表示したり妨げる。
- 問題では、デバイスを起動して "コルタナさん" の音声アクティブ化を使った後、Cortana アプリを起動する必要があります。 If you updated from a 18362 build, you may also see a second app tile for the previous version of the Cortana app that longer works in **Start**.

## Windows Holographic バージョン 1903 - 2020 年 5 月更新プログラム 
- ビルド 18362.1061

この毎月の品質更新プログラムには、前述のように、チームが Windows Holographic バージョン 2004 May Update で作業していたため、重要な変更は含められない。

## Windows Holographic バージョン 1903 - April 2020 Update
- ビルド 18362.1059

**サポートされているアプリの濃色モード** 

多くの Windows アプリは、濃色モードと淡色モードの両方をサポートしています。 HoloLens 2 のお客様は、両方の配色をサポートするアプリの既定のモードを選択できます。 お客様からのフィードバックに基づいて、既定のアプリ モードを "濃色" に設定していますが、この設定はいつでも簡単に変更できます。[設定] **> システム > 色**に移動して **、"** 既定のアプリ モードを選択してください" を見つける。

これらの "インボックス" アプリは、濃色モードをサポートしています。
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

**更新プログラムの機能強化と修正プログラム:** 
- シェル オーバーレイが Mixed Reality キャプチャに含まれるか確認します。
- Unreal 開発者は、Device Portal の 3D ビュー ページを使って、アプリケーションをテストおよびデバッグできます。
- *HolographicDepthReprojectionMethod DepthReprojection*アルゴリズムを使用した場合の Mixed Reality キャプチャでのホログラムの安定性の向上。
- 32 ビットアプリの "WinRT IStreamSocketListener API クラスが登録されていません" というエラーをARMしました。

## Windows Holographic バージョン 1903 - 2020 年 3 月更新プログラム 
- ビルド 18362.1056

更新プログラムの機能強化と修正:

- *HolographicDepthReprojectionMethod AutoPlanar*アルゴリズムを使用した場合の Mixed Reality キャプチャでのホログラムの安定性の向上。
- 深度 MF サンプルにアタッチされている座標系がパブリック ドキュメントと一致する必要があります。
- ユーザーがデバイス ポータルで大量のテキストを貼り付け可能にすることで、開発者の生産性が向上しました。

## Windows Holographic バージョン 1903 - 2020 年 2 月更新プログラム 
- ビルド 18362.1053

更新プログラムの機能強化と修正:

- Unity アプリケーションの HolographicSpace.UserPresence API を一時的に無効にします。 この変更により、"バックグラウンドでの実行" 設定が有効になっている場合でも、バイザーが反転した場合に一部のアプリが一時停止する問題が回避されます。
- ユーザーが数秒後に UI がフリーズし、シェルに戻るのをユーザーが気付いた、手の追跡によって発生するランダムな HUP クラッシュを修正しました。
- 手の追跡が改善され、人差し指で動かされた場合、その指の上部が予期せず動き出す可能性が低くなっています。
- ヘッド トラッキング、空間マッピング、その他のランタイムの信頼性が向上しました。

## Windows Holographic バージョン 1903 - 2020 年 1 月更新プログラム 
- ビルド 18362.1043
 
更新プログラムの機能強化と修正:

- HoloLens 2 エミュレーターを使用する場合の排他アプリの安定性が向上しました。

## Windows Holographic バージョン 1903 - 2019 年 12 月更新プログラム 
- ビルド 18362.1042

更新プログラムの機能強化と修正:

- 最終段階の再現 (LSR) 修正プログラムを導入しました。 ホログラムの視覚的なレンダリングが改善され、奥行きをより正確に計算することで、より安定して鮮明に表示されます。 この現象は、アプリがホログラムの深さを正しく設定しない場合、この更新後に顕著になります。
- 排他的アプリと排他的アプリ間のナビゲーションの安定性を修正しました。
- デバイスが数日間スタンバイ状態だった後、Mixed Reality キャプチャでビデオを記録できない問題を解決しました。
- ホログラムの安定性が向上しました。

## Windows Holographic バージョン 1903 - November 2019 Update 
- ビルド 18362.1039

更新プログラムの機能強化と修正:

- en-CA**** および en-AU の初期セットアップ中に音声コマンドを選択する機能が修正されました。
- 最新の Unity および Mixed Reality バージョン (MRTK) に配置されたオブジェクトToolkit品質が向上しました。
- スタート メニューを開いて閉じるまで、起動時にホログラフィック アプリケーションが一時停止状態で停止する問題に対処する問題を修正しました。
- HoloLens 2 とエミュレーターの OpenXR ランタイム適合性の修正と機能強化。
