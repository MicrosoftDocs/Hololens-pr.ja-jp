---
title: HoloLens 2 のリリース ノート
description: 新しい HoloLens 2 リリースごとにすべての更新プログラムを最新の情報に更新します。
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
ms.openlocfilehash: 9ad1fd599605a82280fc3ce45a2b78fcd0be6f14
ms.sourcegitcommit: 1f3ad5b099e72491f436d851738d2b6f3d4dff31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400717"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 のリリース ノート

HoloLens デバイスで生産性の高いエクスペリエンスを提供するために、引き続き機能、バグ、およびセキュリティ更新プログラムをリリースします。 このページでは、毎月 HoloLens の新機能を確認できます。 最新の HoloLens 2 更新プログラムを取得[](hololens-update-hololens.md#check-for-updates-and-manually-update)するには、更新プログラムを確認し、手動で更新するか、Advanced Recovery [Companion](hololens-recovery.md#clean-reflash-the-device)経由でデバイスをフラッシュするフル フラッシュ更新プログラム (FFU) を取得します。 ダウンロード [は](https://aka.ms/hololens2download) 最新の状態に保たれ、一般に利用可能な最新のビルドが提供されます。

>[!NOTE]
> Windows Insiders への新機能のフライトを再び開始するのを楽しみにしています。 開発チャネルに最新の更新プログラムを提供します。 Windows Insider ビルドにさらに機能と更新プログラムを追加する場合は [**、HoloLens Insider**](hololens-insider.md) のメモに進む必要があります。 これらの更新プログラムを現実に組み合わせ、興奮して準備を整えます。

関連するリリース ノートを確認します。

- [HoloLens エミュレーター アーカイブにアクセスする](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic バージョン 20H2 - 2021 年 3 月更新プログラム
- ビルド 19041.1140

更新プログラムの改善と修正:

- AdvancedPhotoCapture または LowLagPhotoCapture を使用して HoloLens 2 で写真をキャプチャしているお客様は、写真がキャプチャされた後、最大 3 秒後にカメラ のポーズを取得できます。
- Device Portal Service のメモリ リークを修正すると、この問題により、他のアプリケーションがメモリの割り当てに失敗する原因となるサービスのメモリ使用量が増加しました。
- 段階的ロールアウトに登録されているユーザーがデバイスにサインインできない問題を修正しました。

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic バージョン 1903 - 2021 年 3 月更新プログラム
- ビルド 18362.1102

更新プログラムの改善と修正:

- Device Portal Service のメモリ リークを修正すると、この問題により、他のアプリケーションがメモリの割り当てに失敗する原因となるサービスのメモリ使用量が増加しました。

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic バージョン 20H2 - 2021 年 2 月更新プログラム
- ビルド 19041.1136

更新プログラムの改善と修正:

- デバイスの初期セットアップとストア アプリの更新に関する問題を修正します。
- 後の HoloLens リリースのアップグレードとフライトに関する問題に取り組む。
- HoloLens デバイスから eSIM ルート ストアから未使用のプレインストールされた証明書を削除しました。

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic バージョン 1903 - 2021 年 2 月更新
- ビルド 18362.1098

この毎月の品質更新プログラムには、重要な変更が含まれているのではなく、Windows Holographic バージョン 2004 の最新ビルドを試してみてください。

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic バージョン 20H2 - 2021 年 1 月更新プログラム
- ビルド 19041.1134

更新プログラムの改善と修正:

- デバイスに多数のユーザーがある場合の起動時、再開中、ユーザー切り替え時のパフォーマンスが向上しました。
- リサーチ モードの arm32 サポート [が追加されました](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)。

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic バージョン 1903 - 2021 年 1 月の更新プログラム
- ビルド 18362.1091

この毎月の品質更新プログラムには、重要な変更が含まれているのではなく、Windows Holographic バージョン 2004 の最新ビルドを試してみてください。

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic バージョン 20H2 – 2020 年 12 月更新プログラム
- ビルド 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>アプリ インストーラーを使用して HoloLens 2 にアプリをインストールする

新しい **機能 (アプリ インストーラー)** を追加して、HoloLens 2 デバイスにアプリケーションをシームレスにインストールできます。 この機能は、管理 **されていないデバイスに対して既定でオンになります**。 企業の中断を防ぐため、現時点では管理対象デバイスでアプリ インストーラー **を** 使用できません。  

次に当てはまる場合、デバイスは****"管理" と見なされます。
- MDM [登録](hololens-enroll-mdm.md)
- プロビジョニング パッケージ [で構成済み](hololens-provisioning.md)
- ユーザー [ID は](hololens-identity.md) Azure AD

開発者モードを有効にしたり、デバイス ポータルを使用したりすることなく、アプリをインストールできます。  Appx バンドルをデバイスにダウンロードし、エクスプローラーの Appx バンドルに移動して、インストールを開始するように求めるメッセージを表示します。  または、Web [ページからインストールを開始します](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。  MDM の LOB アプリ展開機能を使用して Microsoft Store からインストールするアプリやサイドロードするアプリと同様に、[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)アプリは署名ツール[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)でデジタル署名する必要があります。また、アプリを展開する前に、署名に使用する証明書を HoloLens デバイスで信頼する必要があります。

**アプリケーションのインストール手順。**

1.  デバイスが管理対象と見なされていないことを確認する
1.  HoloLens 2 デバイスの電源がオンで PC に接続されていることを確認する
1.  HoloLens 2 デバイスにサインインしている必要があります
1.  PC でカスタム アプリに移動し、yourapp.appxbundle をdevicename\Internal Storage\Downloads にコピーします。   ファイルのコピーが完了したら、デバイスを切断できます
1.  HoloLens 2 デバイスから [スタート] メニューを開き、[すべてのアプリ] を選択してエクスプローラー アプリを起動します。
1.  [ダウンロード] フォルダーに移動します。 アプリの左側のパネルで[このデバイス] を最初に選択してから、[ダウンロード] に移動する必要があります。
1.  yourapp.appxbundle ファイルを選択します。
1.  アプリ インストーラーが起動します。 [インストール] ボタンを選択してアプリをインストールします。
インストールが完了すると、インストールされたアプリが自動的に起動します。

このフローをテストするサンプル アプリは [、Windows ユニバーサル サンプル GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) にあります。

アプリ インストーラーを使用して [HoloLens 2](app-deploy-app-installer.md)にアプリをインストールする完全なプロセスについて説明します。  

![アプリ インストーラーによる MRTK の例のインストール](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>更新プログラムの改善と修正:

- 手の追跡は、以前は手が失われた可能性がある多くの新しいケースで追跡を維持します。  これらの新しいケースの中には、手のひらの位置だけがユーザーの実際の手に基づいて更新され続け、他のジョイントは前のポーズに基づいて推測されます。  この変更は、スラップ、スロー、スクープ、拍手などの動きの追跡の一貫性を向上させるのに役立ちます。  また、手がサーフェスに近い場合やオブジェクトを保持している場合にも役立ちます。  手の関節が推測されている場合 [、ジョイントごとの](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) 精度の値は"高" ではなく "近似" に設定されます。
- Azure ADアカウントの PIN リセットでエラーが表示される問題を修正しました。"何か問題が発生しました。
- ET、Iris を設定アプリ、新しいユーザー、または通知トーストから起動すると、ユーザーはブート後の OOBE クラッシュをはるかに少なくする必要があります。
- ユーザーは、OOBE から正しいタイム ゾーンが出てくる必要があります。

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic バージョン 1903 – 2020 年 12 月更新プログラム
- ビルド 18362.1088

この毎月の品質更新プログラムには特に重要な変更はありません。最新の Windows Holographic バージョン 20H2 ~ 2020 年 12 月の更新プログラムと、ビルドに追加された新しいアプリ インストーラー機能を試してみてください。


## <a name="windows-holographic-version-20h2"></a>Windows Holographic バージョン 20H2
- ビルド 19041.1128

Windows Holographic バージョン 20H2 が利用可能になってきて、HoloLens 2 のユーザーと IT 担当者に、一連の新機能が追加されました。 自動アイポジショニングから、設定の証明書マネージャー、キオスク モード機能の強化、および新しい Autopilot セットアップ機能まで。 この新しい更新プログラムにより、IT チームは HoloLens デバイスの構成と管理を細かく制御し、ユーザーにさらにシームレスなホログラフィック エクスペリエンスを提供します。 

この最新リリースは、バージョン 2004 の月次更新プログラムですが、今回は新機能を含む予定です。 メジャー ビルド番号は変わりません。Windows Update はバージョン 2004 (ビルド 19041) への月次リリースを示します。 [設定] 画面の [ビルド番号] >を確認して、利用可能な最新のビルド 19041.1128 以上を確認できます。 最新のリリースに更新するには、[設定] アプリを開き、[セキュリティの更新&] に移動し、[更新プログラムの確認] をタップします。 HoloLens 更新プログラムを管理する方法の詳細については、このページを [参照してください](https://docs.microsoft.com/hololens/hololens-updates)。

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Windows Holographic バージョン 20H2 の新機能  

| 機能                                              | 説明                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [視線の自動調整サポート](hololens-release-notes.md#auto-eye-position-support) | ユーザーがアイ トラッキングの調整を行わずに、目の位置をアクティブに計算します。   |
| [証明書マネージャー](hololens-release-notes.md#certificate-manager)   | 新しい簡単な方法で、設定アプリから証明書をインストールおよび削除できます。     |
| [USB からのプロビジョニングの自動起動](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | USB ドライブにパッケージをプロビジョニングすると、OOBE のプロビジョニング ページが自動的に表示されます。                                                         |
| [OOBE でのプロビジョニング パッケージの自動確認](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | プロビジョニング パッケージは、プロビジョニング ページから OOBE 中に自動的に適用されます。                                                         |
| [UI を使用しない自動プロビジョニング](hololens-release-notes.md#automatic-provisioning-without-using-ui) | プロビジョニングの自動起動と自動確認を組み合わせる方法。 |
| [自動パイロットを使用した接続Wi-Fiする](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | イーサネット アダプターを必要とせずにWi-Fiデバイスから自動パイロットを使用します。 |
| [Tenantlockdown CSP と Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | テナントの登録とポリシーの適用後、デバイスは、デバイスがリセットまたは再フラッシュされた場合にのみ、そのテナントに登録できます。 |
| [グローバルに割り当てられた](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | システム レベルでキオスクを適用し、すべてのユーザーに適用可能にする、複数のアプリ キオスク モードの新しい構成方法。                  |
| [マルチアプリ キオスクでアプリを自動起動する](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | 複数アプリキオスク モードにサインインするときに自動的に起動するアプリケーションを設定します。                                                        |
| [失敗の処理に関するキオスク モードの動作の変更](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | キオスク モードの失敗で制限的なフォールバックが発生しました。                                                                                                |
| [HoloLens ポリシー](hololens-release-notes.md#hololens-policies)                                    | HoloLens の新しいポリシー。     |
| [オフライン キオスクの Azure ADグループ メンバーシップをキャッシュする](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | 新しいポリシーを使用すると、ユーザーはグループ メンバーシップ キャッシュを使用して、設定された日数のキオスク モードをオフラインで使用できます。                                        |
| [HoloLens 2 の新しいデバイス制限ポリシー](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | HoloLens 2 で新しく有効にされたデバイス管理ポリシー。                                                                                |
| [HoloLens 2 の新しい電源ポリシー](hololens-release-notes.md#new-power-policies-for-hololens-2)       | 電源タイムアウト設定で新しくサポートされるポリシー。  |
| [ポリシーの更新](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | 更新プログラムの制御を許可する新しく有効なポリシー。           |
| [HoloLens 2 の [設定] ページの表示を有効にする](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | 設定アプリで表示されるページを選択するポリシー。             |
| [リサーチ モード](hololens-release-notes.md#research-mode) | HoloLens 2 でリサーチ モードを使用する。 |
| [録音の長さが長くなった](hololens-release-notes.md#recording-length-increased) | MRC の録音が 5 分に制限されなくなりました。 |
| [更新プログラムの改善と修正](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | 更新プログラムの追加の修正。   |

### <a name="auto-eye-position-support"></a>視線の自動調整サポート

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

この情報は、後で他の調整情報 [で確認できます](hololens-calibration.md#auto-eye-position-support)。 

### <a name="certificate-manager"></a>証明書マネージャー

- 新しい証明書マネージャーを通じて、デバイスのセキュリティとコンプライアンスのための監査、診断、検証ツールが改善されました。 この機能を使用すると、商用環境で大規模に証明書を展開、トラブルシューティング、検証できます。

Windows Holographic バージョン 20H2 では、HoloLens 2 Settings アプリに証明書マネージャーを追加しています。 [設定] **に移動>セキュリティ&証明書>します**。 この機能は、デバイスに証明書を表示、インストール、および削除するための簡単でユーザーフレンドリーな方法を提供します。 新しい証明書マネージャーにより、管理者とユーザーは監査、診断、検証ツールを改善し、デバイスが安全で準拠した状態を維持します。 

-   **監査:** 証明書が正しく展開されていることを検証する機能、または証明書が適切に削除されていることを確認する機能。 
-   **診断:** 問題が発生した場合は、デバイスに適切な証明書が存在する検証によって時間が節約され、トラブルシューティングに役立ちます。 
-   **検証:** 証明書が目的の目的に合って機能することを確認すると、特に商用環境で証明書を大規模に展開する前に、大幅な時間を節約できます。

リスト内の特定の証明書をすばやく検索するには、名前、ストア、または有効期限で並べ替えるオプションがあります。 ユーザーは証明書を直接検索することもできます。 個々の証明書のプロパティを表示するには、証明書を選択し、[情報] を **クリックします**。 

証明書のインストールでは、.cer ファイルと .crt ファイルが現在サポートされています。 デバイス所有者は、ローカル コンピューターと現在のユーザーに証明書をインストールできます。 他のすべてのユーザーは、現在のユーザーにのみインストールできます。 ユーザーは、設定 UI から直接インストールされた証明書のみを削除できます。 証明書が他の方法でインストールされている場合は、同じメカニズムによって削除する必要があります。

#### <a name="to-install-a-certificate"></a>証明書をインストールするには、次の手順を実行します。 

1.  HoloLens 2 を PC に接続します。
1.  HoloLens 2 の場所にインストールする証明書ファイルを配置します。
1.  [設定 **] アプリの [セキュリティ>更新&証明書>]** に移動し、[証明書のインストール] を選択します。
1.  [ファイル **のインポート]** をクリックし、証明書を保存した場所に移動します。
1.  [ストア **の場所] を選択します**。
1.  [証明書 **ストア] を選択します**。
1.  **[インストール]** をクリックします。

これで、証明書がデバイスにインストールされます。

#### <a name="to-remove-a-certificate"></a>証明書を削除するには、次の方法を使用します。 
1. [設定] **アプリの [更新>セキュリティ証明書] >移動します**。
1. 検索ボックスで名前で証明書を検索します。
1. 証明書を選択します。
1. [削除] **をクリックします。**
1. 確認 **を求めるメッセージが** 表示されたら、[はい] を選択します。

![設定アプリの証明書ビューアー](images/certificate-viewer-device.jpg)

![証明書 UI を使用して証明書をインストールする方法を示す図](images/certificate-device-install.jpg)

この情報は、後で新 [しい [証明書マネージャー] ページで確認できます](certificate-manager.md)。

### <a name="auto-launch-provisioning-from-usb"></a>USB からのプロビジョニングの自動起動

- OOBE の間にプロビジョニング パッケージ付き USB ドライブを使用する場合、ユーザーの操作を少なくできる自動化されたプロセス。

このリリースの前に、ユーザーはボタンの組み合わせを使用してプロビジョニングするために、OOBE の間にプロビジョニング画面を手動で起動する必要があります。 これで、ユーザーは USB ストレージ ドライブでプロビジョニング パッケージを使用して、ボタンの組み合わせをスキップできます。 

1. OOBE の最初の対話可能な瞬間にプロビジョニング パッケージを使用して USB ドライブを接続する
1. デバイスを準備する準備ができたら、プロビジョニング ページが表示されたプロンプトが自動的に開きます。 

注: デバイスの起動中に USB ドライブが接続された状態が残っている場合、OOBE は既存の USB ストレージ デバイスを列挙し、追加の USB ストレージ デバイスが接続されているのを監視します。

OOBE 中にプロビジョニング パッケージを適用する方法の詳細については [、HoloLens プロビジョニングのドキュメントを参照](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) してください。

USB からの [自動起動プロビジョニングの詳細](hololens-provisioning.md#auto-launch-provisioning-from-usb) については、HoloLens プロビジョニングのドキュメントを参照してください。

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>OOBE でのプロビジョニング パッケージの自動確認
- [プロビジョニング パッケージ] ページが表示されている場合、ユーザーの操作を減らして自動処理を実行すると、一覧に表示されているパッケージすべてが自動的に適用されます。

プロビジョニングのメイン画面が表示された場合、OOBE は 10 秒後に自動的にすべてのプロビジョニング パッケージの適用を開始します。 ユーザーは、 [予想したパッケージ](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) を確認した後も、この 10 秒以内に確認またはキャンセルできます。

### <a name="automatic-provisioning-without-using-ui"></a>UI を使用しない自動プロビジョニング
- プロビジョニングのデバイス操作を減らした自動プロセスを組み合わせた。 

USB デバイスからのプロビジョニングの自動起動とプロビジョニング パッケージの自動確認を組み合わせることで、ユーザーはデバイスの UI を使用したり、デバイスを装着したりすることなく、HoloLens 2 デバイスを自動的にプロビジョニングできます。 複数のデバイスに同じ USB ドライブとプロビジョニング パッケージを引き続き使用できます。 これは、同じ領域に複数のデバイスを一度に展開する場合に便利です。 

1. Windows[構成デザイナーを使用してプロビジョニング パッケージ](hololens-provisioning.md)[を作成します](https://www.microsoft.com/store/productId/9NBLGGH4TX22)。 
1. パッケージを USB ストレージ ドライブにコピーします。
1. [HoloLens 2 から](hololens-insider.md#ffu-download-and-flash-directions) [19041.1361 以降のビルドをフラッシュします](https://aka.ms/hololens2previewdownload)。 
1. Advanced [Recovery Companion が](https://www.microsoft.com/store/productId/9P74Z35SFRS8) デバイスのフラッシュを完了したら、USB-C ケーブルを取り外します。 
1. USB ドライブをデバイスに接続します。
1. HoloLens 2 デバイスが OOBE に起動すると、USB ドライブ上のプロビジョニング パッケージが自動的に検出され、プロビジョニング ページが起動します。
1. 10 秒後、デバイスはプロビジョニング パッケージを自動的に適用します。 

これでデバイスが構成され、[プロビジョニングの [成功] 画面が表示されます](hololens-provisioning.md#automatic-provisioning-without-using-ui)。

### <a name="using-autopilot-with-wi-fi-connection"></a>自動パイロットを使用した接続Wi-Fiする
- 接続されているデバイスで Autopilot が機能する機能を有効にすることで、ハードウェアニーズを低減するイーサネットへの USB-C アダプターWi-Fi削除されました。

OOBE の間、HoloLens 2 を Wi-Fi に接続すると、OOBE はデバイスの自動パイロット プロファイルを確認します。 1 つが見つかった場合は、AAD 参加フローと登録フローの残りの部分を完了するために使用されます。 つまり、USB-C または Wi-Fi から USB-C アダプターへのイーサネットの使用は、もう要件ではありません。ただし、OOBE の開始時に提供されている場合は、引き続き機能します。 [HoloLens 2 デバイスの自動パイロットについて詳しくは、次の情報をご覧ください](hololens2-autopilot.md)。

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP と Autopilot
- デバイスのリセットまたは再フラッシュを行っても、デバイスをテナントにロックすることにより、デバイスを組織のテナントに保持します。 プロビジョニングを介したアカウントの作成を禁止することにより、セキュリティを強化します。 

HoloLens 2 デバイスは [、Windows Holographic バージョン 20H2](hololens-release-notes.md#windows-holographic-version-20h2)のテナントロックダウン CSP をサポートしています。 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP は、HoloLens 2 が Autopilot のみを使用して MDM 登録に関連付けられるようにします。 TenantLockdown CSP の RequireNetworkInOOBE ノードが HoloLens 2 で true または false (最初に設定された) 値に設定されると、その値は、再フラッシュ、OS 更新プログラムなどにもかかわらずデバイスに残ります。 

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

1. 以下に示すように、カスタム OMA URI ベースのデバイス構成プロファイルを作成し、RequireNetworkInOOBE に false を指定します。 OMA-URI 値は ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE である必要があります

   > [!div class="mx-imgBorder"]
   > ![Intune の OMA URI を介して RequireNetworkInOOBE を false に設定するスクリーンショット](images/hololens-tenant-lockdown-false.png)

1. グループを作成し、デバイス構成プロファイルをそのデバイス グループに割り当てます。 

1. 前の手順で作成したグループの HoloLens 2 デバイス メンバーを作成し、同期をトリガーします。

Intune ポータルで、デバイス構成が正常に適用されていることを確認します。 このデバイスの構成が HoloLens 2 デバイスに正常に適用されると、TenantLockdown の効果が非アクティブになります。 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>TenantLockdown が true に設定された後、HoloLens で Autopilot プロファイルが割り当て解除された場合、OOBE 中にどうなりますか? 
OOBE は、Autopilot プロファイルがダウンロードされるのを無期限に待機し、次のダイアログが表示されます。 TenantLockdown の影響を取り除くには、最初に Autopilot のみを使用してデバイスを元のテナントに登録し、TenantLockdown CSP によって導入された制限を取り除く前に、前の手順で説明したように RequireNetworkInOOBE の設定を解除する必要があります。 

![ポリシーがデバイスに適用される時のデバイス内ビュー。](images/hololens-autopilot-lockdown.png)

この情報は、Tenantlockdown CSP と Autopilot の下の他の Autopilot と一緒 [に確認できます](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)。

### <a name="global-assigned-access--kiosk-mode"></a>グローバル割り当てアクセス – キオスク モード
- システム レベルでキオスク モードを適用する新しい Kiosk メソッドを有効にすることで、キオスクの ID 管理を減らしました。

この新しい機能により、IT 管理者は HoloLens 2 デバイスを複数のアプリ キオスク モード用に構成できます。これはシステム レベルで適用可能で、システム上の ID と親和性を持たず、デバイスにサインインするすべてのユーザーに適用されます。 この新機能の詳細については、「HoloLens グローバル割り当てアクセス [キオスク」を参照してください](hololens-global-assigned-access-kiosk.md)。

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>複数アプリキオスク モードでのアプリケーションの自動起動 
- アプリの自動起動に重点を置いてエクスペリエンスを向上し、キオスク モード エクスペリエンス用に選択された UI とアプリの選択をさらに増やします。

複数アプリキオスク モードにのみ適用され、割り当てられたアクセス構成で以下の強調表示された属性を使用して自動起動に指定できるアプリは 1 つのみです。 

ユーザーがサインインすると、アプリケーションが自動的に起動されます。 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>失敗の処理に関するキオスク モードの動作の変更
- キオスク モードのエラーで使用可能なアプリを排除することで、より安全なキオスク モードを提供します。 

以前、キオスク モードの適用でエラーが発生した場合、HoloLens はスタート メニューにすべてのアプリケーションを表示するために使用しました。 Windows Holographic Version 20H2 では、エラーが発生した場合、スタート メニューに以下のようにアプリが表示されません。 

![失敗した場合に表示されるキオスク モードのイメージ。](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens ポリシー
- デバイスを管理するために作成された HoloLens 専用のデバイス管理オプション。 

Windows Holographic バージョン 20H2 の HoloLens 2 デバイス用に新しい複合現実ポリシーが作成されました。 新しい制御可能な設定には、明るさの設定、音量の設定、複合現実キャプチャでのオーディオ録音の無効化、診断を収集できる場合の設定、および AAD グループ メンバーシップ キャッシュが含まれます。  

| 新しい HoloLens ポリシー                                | 説明                                                                               | 備考                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 明るさボタンを無効にすると、ボタンを押しても明るさは変わりません。       | 1 はい、0 いいえ (既定)                                                |
| MixedReality\VolumeButtonDisabled                  | ボリューム ボタンを無効にし、音量を変更しないので、ボタンを押します。               | 1 はい、0 いいえ (既定)                                                |
| MixedReality\MicrophoneDisabled                    | HoloLens 2 でオーディオ録音が行えなかないので、マイクを無効にします。                      | 1 はい、0 いいえ (既定)                                                |
| MixedReality\フォールバックDiagnostics                   | 診断ログを収集できる場合の動作を制御します。                               | 0 Disabled, 1 Enabled for Device Owners, 2 Enabled for all (Default) |
| MixedReality\HeadTrackingMode                      | 将来の使用のために予約されています。                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Azure とグループを対象ADキオスクで Azure メンバーシップ キャッシュを使用する日数ADします。 | 以下を参照してください。                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>オフライン キオスクの Azure ADグループ メンバーシップをキャッシュする
- 最大 60 日間、AAD グループでオフライン キオスクを使用できます。

このポリシーは、サインインしているユーザーの Azure AD グループを対象とする割り当てられたアクセス構成に、Azure AD グループ メンバーシップ キャッシュを使用できる日数を制御します。 このポリシー値を 0 より大きい値に設定すると、それ以外の場合はキャッシュが使用されません。  

名前: AADGroupMembershipCacheValidityInDays URI 値: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最小 - 0 日  
最大 - 60 日間 

このポリシーを正しく使用する手順は次のとおりです。 
1. Azure グループを対象とするキオスク用のデバイス構成プロファイルAD作成し、HoloLens デバイスに割り当てる。 
1. このポリシー値を希望の日数 (> > 0) に設定し、HoloLens デバイスに割り当てるカスタム OMA URI ベースのデバイス構成を作成します。 
    1. URI 値は 、./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays として OMA-URI テキスト ボックスに入力する必要があります。
    1. 値は最小/最大の間で指定できます。
1. HoloLens デバイスを登録し、両方の構成がデバイスに適用されるのを確認します。 
1. インターネットがAD、ユーザーがサインインし、Azure AD グループ メンバーシップが正常に確認されると、キャッシュが作成されます。 
1. これで、Azure ADユーザー 1 は HoloLens をオフラインにし、ポリシー値で日数を X に設定できる限り、キオスク モードで使用できます。 
1. 手順 4 と 5 は、他の Azure AD ユーザー N に対して繰り返し実行できます。ここで重要な点は、Azure AD ユーザーがインターネットを使用してデバイスにサインインする必要がある点です。少なくとも 1 回は、キオスク構成が対象となる Azure AD グループのメンバーと判断できます。 
 
> [!NOTE]
> Azure サーバーに対して手順 4 が実行されるまでAD「切断された」環境で説明されているエラー動作が発生します。 

### <a name="new-device-restriction-policies-for-hololens-2"></a>HoloLens 2 の新しいデバイス制限ポリシー
- ユーザーは、プロビジョニング パッケージの追加や削除をブロックするなどの特定のデバイス管理ポリシーを管理できます。

HoloLens 2 デバイスの管理オプションを追加できる新しく有効なポリシー。 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

AllowAddProvisioningPackage と AllowRemoveProvisioningPackage のこれら 2 つの新しいポリシーが、共通のデバイス制限に [追加されています](hololens-common-device-restrictions.md)。

> [!NOTE]
> [RemoteLock に関して](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)、HoloLens は ./Vendor/MSFT/RemoteLock/Lock 構成のみをサポートします。 リセットや回復などの PIN を扱う構成はサポートされていません。

### <a name="new-power-policies-for-hololens-2"></a>HoloLens 2 の新しい電源ポリシー
- HoloLens が電源ポリシーを使用してスリープまたはロックを行う場合のその他のオプション。 

これらの新しく追加されたポリシーにより、管理者はアイドル タイムアウトなどの電源状態を制御できます。 各ポリシーの詳細については、そのポリシーのリンクをクリックしてください。

|     ポリシードキュメントのリンク                |     備考                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Windows 構成デザイナーで使用する値の例、つまり、  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Windows 構成デザイナーで使用する値の例、つまり、  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Windows 構成デザイナーで使用する値の例(100)                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Windows 構成デザイナーで使用する値の例(100)                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows 構成デザイナーで使用する値の例、つまり、   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows 構成デザイナーで使用する値の例、つまり、  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

DisplayOffTimeoutOnBattery と DisplayOffTimeoutPluggedIn のこれら 2 つの新しいポリシーが、共通のデバイス制限に [追加されています](hololens-common-device-restrictions.md)。

> [!NOTE]
> HoloLens 2 で一貫したエクスペリエンスを得る場合は、DisplayOffTimeoutOnBattery と StandbyTimeoutOnBattery の両方の値が同じ値として設定されている必要があります。 DisplayOffTimeoutPluggedIn および StandbyTimeoutPluggedIn にも同じです。 モダン スタンバイ [の詳細については、「ディスプレイ、スリープ](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) 、休止状態のアイドル タイマー」を参照してください。

### <a name="newly-enabled-update-policies-for-hololens"></a>HoloLens の更新ポリシーを新しく有効にする
- [更新プログラムのインストール時] または [更新プログラムの一時停止] ボタンを無効にして更新プログラムを確認するその他のオプション。

これらの更新ポリシーは、HoloLens 2 デバイスで有効になっています。
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

これらの更新プログラム ポリシーと HoloLens デバイスに使用する方法の詳細については [、「HoloLens](hololens-updates.md)更新プログラムの管理」を参照してください。

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>HoloLens 2 の [設定] ページの表示を有効にする
- 設定アプリの UI コントロールが増え、ページの選択が制限されている場合は混乱する可能性があります。

これで、IT 管理者は、システム設定アプリ内の特定のページが表示またはアクセスできないか、指定されたページを除くすべてのページに対して表示またはアクセスを許可するポリシーを有効にしました。 この機能を完全にカスタマイズする方法については、以下のリンクをクリックしてください。

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

HoloLens 2 でカスタマイズできるページ設定については、「設定 [URI」ページをご覧ください](settings-uri-list.md)。 
 
![設定アプリで変更されたアクティブ時間のスクリーンショット](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>リサーチ モード
リサーチ モードでは、HoloLens 2 はコンピューター ビジョン研究の強力なツールになります。 以前のエディションと比較して、HoloLens 2 のリサーチ モードには次の利点があります。
-   HoloLens (第 1 世代) リサーチ モードで公開されているセンサーに加えて、加速度計、ジャイロスコープ、磁力計などの IMU センサー アクセスも提供しています。
-   HoloLens 2 は、リサーチ モードと共に使用できる新機能を提供します。 具体的には、より豊富な実験セットを提供できる、明確なハンドトラッキングおよびアイトラッキング API へのアクセスです。

研究者は、HoloLens デバイスでリサーチ モードを有効にし、これらすべての外部向け生画像センサー ストリームにアクセスできます。 HoloLens 2 のリサーチ モードでは、加速度計、ジャイロスコープ、磁力計の測定値にもアクセスできます。 ユーザーのプライバシーを保護するために、生の視線追跡カメラ画像はリサーチ モードでは使用できませんが、視線方向は既存の API を介して利用できます。

技術的な詳細 [については、リサーチ モードの](https://docs.microsoft.com/windows/mixed-reality/research-mode) ドキュメントを参照してください。

### <a name="recording-length-increased"></a>録音の長さが長くなった
お客様からのフィードバックにより、複合現実キャプチャの記録長 [が長くなっています](holographic-photos-and-videos.md)。 複合現実キャプチャは既定で 5 分に制限されなくなりましたが、代わりに使用可能なディスク領域に基づいて最大記録長が計算されます。 デバイスは、使用可能なディスク領域に基づいて最大ビデオ録画時間を推定し、ディスク容量全体の最大 80% を占める。

> [!NOTE]
> HoloLens は、次のいずれかの場合、既定のビデオ録画の長さ (5 分) を使用します。
> - 推定最大記録時間は、既定の 5 分よりも短い値です。
> - 使用可能なディスク領域は、ディスク領域全体の 20% 未満です。

完全な要件については、Holographic の写真と [ビデオのドキュメントをご覧](holographic-photos-and-videos.md#maximum-recording-length) ください。 

### <a name="improvements-and-fixes-in-the-update"></a>更新プログラムの改善と修正:
- OOBE のその他の画面が暗いモードになります。
- 詳しくは、最新のプライバシーに関する声明をオンラインで参照してください。
- ユーザーがプロビジョニング パッケージを通じて VPN プロファイルをプロビジョニングできない問題に対処しました。
- VPN 接続のプロキシ構成の問題を修正しました。
- AllowUsbConnection の NCM 用 MDM を介して USB 関数の列挙を無効にするポリシーを更新しました。
- デバイスが単一アプリ キオスクとして設定されている場合に、HoloLens デバイスがメディア転送プロトコル (MTP) を使用してエクスプローラーに表示されなかっている問題に [対処しました](hololens-kiosk.md)。 MTP (および一般的な USB 接続) は [、AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) ポリシーを使用して無効にできます。
- [スタート] メニューのアイコンがキオスク モードで正しく拡大/縮小される問題を修正しました。
- Azure グループを対象としたキオスク モードに干渉する HTTP キャッシュによる問題ADしました。
- 開発者モードを無効にし、再び有効にしない限り、プロビジョニング パッケージで開発者モードを有効にした後、ユーザーが [ペア] ボタンを使用できなかった問題を修正しました。

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic バージョン 1903 - 2020 年 11 月更新プログラム
- ビルド 18362.1085

この毎月の品質更新プログラムには、重要な変更点が含まれているのではなく、最新の機能リリース ビルド Windows Holographic バージョン 20H2 を試してみてください。

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic バージョン 2004 - 2020 年 10 月更新プログラム
- ビルド 19041.1124
 
更新プログラムの改善と修正:

- ランタイム システムの障害を引き起こした不要なチェックを削除しました。

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic バージョン 1903 - 2020 年 10 月更新プログラム
- ビルド 18362.1081

この毎月の品質更新プログラムには、重要な変更が含まれているのではなく、Windows Holographic バージョン 2004 の最新ビルドを試してみてください。

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic バージョン 2004 - 2020 年 9 月更新プログラム
- ビルド 19041.1117

更新プログラムの改善と修正:

- supportsMultipleInstances="true" が appxmanifest に存在する場合にVisual Studioアプリケーションのデバッグを妨げる問題を修正します。
- このリリースには、ネットワーク プロキシを使用したインターネット検出の失敗に対処するための NCSI プロキシ検出の修正が含まれています。 NCSI は、コンピューター プロキシとプロファイルごとのプロキシをインターネット接続の検出に使用できます。 ユーザーごとのプロキシは、今後のリリースで NCSI でサポートされます。
- ほとんどの Windows Mixed Reality デバイスでは、前方方向ベクトルは、ユーザーの頭が前方を見ている中立的な位置にある場合、グラウンドと平行です。 ただし、以前のバージョンの HoloLens 2 では、ベクトルを表示パネルに対して垂直に配置し、理想的な方向に対して数度下方向に傾きます。 HoloLens 2 の新しいバージョンでは、フォーム ファクター間でセマンティックな一貫性を確保するためにこれを修正しました。
- 特定のシナリオでの追跡損失が少ない手追跡の堅牢性が向上しました。
- このリリースには、ビデオ キャプチャの問題に貢献した可能性があるオーディオ タイムスタンプの品質を向上させる修正プログラムが含まれています。

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic バージョン 1903 - 2020 年 9 月更新プログラム
- ビルド 18362.1079

更新プログラムの改善と修正:

- ほとんどの Windows Mixed Reality デバイスでは、前方方向ベクトルは、ユーザーの頭が前方を見ている中立的な位置にある場合、グラウンドと平行です。 ただし、以前のバージョンの HoloLens 2 では、ベクトルを表示パネルに対して垂直に配置し、理想的な方向に対して数度下方向に傾きます。 HoloLens 2 の新しいバージョンでは、フォーム ファクター間でセマンティックな一貫性を確保するためにこれを修正しました。
- 特定のシナリオでの追跡損失が少ない手追跡の堅牢性が向上しました。

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic バージョン 2004 - 2020 年 8 月更新プログラム
- ビルド 19041.1113

更新プログラムの改善と修正:

- 設定アプリは、アイリス登録またはアイトラッキング調整エクスペリエンスにユーザーをフォローしなくなりました。
- OOBE の間にプロビジョニング パッケージを適用してデバイスの名前を変更し、他のアクション (ネットワークへの接続など) を実行すると、名前の変更によりデバイスの再起動後に他のアクションを実行できなかったバグを修正しました。
- 初期デバイスのセットアップ フローの変更された配色は、視覚的な品質を向上させるために流れます。

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic バージョン 1903 - 2020 年 8 月更新プログラム
- ビルド 18362.1074

この毎月の品質更新プログラムには、重要な変更が含まれているのではなく、Windows Holographic バージョン 2004 の最新ビルドを試してみてください。

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic バージョン 2004 - 2020 年 7 月更新プログラム
- ビルド 19041.1109

更新プログラムの改善と修正:

- 開発者は、デバイス ポータルを有効にするか無効にするか、安全な接続が必要になります。
- OS の更新後のアプリケーション起動の信頼性が向上しました。
- 既定の受信トレイの明るさを 100% に変更しました。
- HoloLens 2 の Windows デバイス ポータルの HTTPS 転送に関する問題に対処しました。

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic バージョン 1903 - 2020 年 7 月更新プログラム
- ビルド 18362.1071

更新プログラムの改善と修正:

- 追跡を失う、または回復すると、Unity アプリケーションでホログラムが消える可能性がある問題を修正しました。
- 特定のデバイスでハードウェア アクセラレータを使用して HoloLens エミュレーターを使用している間に、排他的な HoloLens アプリがシェルにクラッシュする問題を修正しました。
- HoloLens 2 の Windows デバイス ポータルの HTTPS 転送に関する問題に対処しました。

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic バージョン 2004 - 2020 年 6 月更新プログラム
- ビルド 19041.1106

更新プログラムの改善と修正:

- カスタム MRC レコーダーが指定されていない場合、特定のプロパティの新しい既定値が追加されました。
  - *MRC ビデオ効果の場合*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (イマーシブ ヘッドセット))
  - *MRC オーディオ効果の場合*:
    - ループバックGain (Windows デバイス ポータルの Mixed Reality Capture ページの現在の "App Audio Gain" 値)
    - MicrophoneGain (Windows デバイス ポータルの Mixed Reality Capture ページの現在の "マイク オーディオ ゲイン" の値)
- 複合現実キャプチャ シナリオのオーディオ品質を向上させるバグを修正しました。 具体的には、この修正プログラムは、[スタート] メニューが表示されているときに録音中のオーディオ **のグッチングを** 排除する必要があります。
- 記録されたビデオのホログラムの安定性が向上しました。
- デバイスがスタンバイ状態で数日間放置された後、複合現実キャプチャでビデオを記録できない問題を解決しました。
- HolographicSpace.UserPresence API は、Unity アプリケーションでは一般に無効になっています。 この動作により、バイザーが反転した際に一部のアプリが一時停止する問題が回避されます。"バックグラウンドで実行する" 設定が有効になっている場合でもです。 この API は、Unity バージョン 2018.4.18 以降および 2019.3.4 以降で有効になっています。
- デバイス ポータルにアクセスするときに、Wi-Fi接続を使用して、Web ブラウザーが無効な証明書によるアクセスを妨げる可能性があります。 デバイス証明書が以前に信頼されている場合でも、ブラウザーは "ERR_SSL_PROTOCOL_ERROR" などのエラーを報告する場合があります。 この場合、セキュリティ警告を無視するオプションは提供されませんので、デバイス ポータルに進む必要はありません。 この更新プログラムは問題を解決しました。 デバイス証明書が以前にダウンロードされ、ブラウザーのセキュリティ警告を削除するために PC で信頼され、SSL エラーが発生した場合は、ブラウザーのセキュリティ警告に対処するために新しい証明書をダウンロードして信頼する必要があります。
- MSIX パッケージを使用してアプリをインストールできるランタイム プロビジョニング パッケージを作成する機能を有効にしました。
- デバイスのシャットダウン時に **、ユーザー**が Mixed Reality ホームからすべてのホログラムを自動的に削除できる設定を [設定システム ホログラム]  >  ****  >  **** に追加しました。
- HoloLens エミュレーターでピクセル形式を変更した HoloLens アプリが黒く表示される問題を修正しました。
- Iris ログイン中にクラッシュするバグを修正しました。
- 既に現在のアプリの繰り返しストアのダウンロードに関する問題を修正しました。
- イマーシブ アプリが Microsoft Edge を繰り返し開かねないバグを修正しました。
- 1903 リリースから更新した後、初期起動中の写真アプリの起動に関する問題を修正しました。
- パフォーマンスと信頼性の向上。

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic バージョン 1903 - 2020 年 6 月更新プログラム
- ビルド 18362.1064

更新プログラムの改善と修正:

- カスタム MRC レコーダーは、指定されていない場合、特定のプロパティの新しい既定値を持っています。
  - *MRC ビデオ効果の場合*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (イマーシブ ヘッドセット))
  - *MRC オーディオ効果の場合*:
    - ループバックGain (Windows デバイス ポータルの Mixed Reality Capture ページの現在の "App Audio Gain" 値)
    - MicrophoneGain (Windows デバイス ポータルの Mixed Reality Capture ページの現在の "マイク オーディオ ゲイン" の値)
- HolographicSpace.UserPresence API は、Unity アプリケーションでは一般に無効になっています。 この動作により、バックグラウンドで実行する設定が有効になっている場合でも、バイザーが反転すると一部のアプリが一時停止する問題が回避されます。 この API は、Unity バージョン 2018.4.18 以降、および 2019.3.4 以降で有効になっています。
- HoloLens エミュレーターでピクセル形式を変更した HoloLens アプリが黒く表示される問題を修正しました。
- 1903 リリースから更新した後の初期ブートでの写真アプリの起動に関する問題を修正しました。

## <a name="windows-holographic-version-2004"></a>Windows Holographic バージョン 2004  
- ビルド - 19041.1103

HoloLens 2、Windows *Holographic、バージョン 2004* の 2020 年 5 月の主要なソフトウェア更新プログラムには、Windows Autopilot のサポート、アプリのダーク モード、5G/LTE ホットスポットの USB イーサネット サポートなど、多くの新機能が含まれています。 最新のリリースに更新するには、[設定]**** アプリを開き、[セキュリティの更新&] に移動し、[更新プログラムの確認]    **** **ボタンを選択**   します。 

|             機能                              |          説明                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Windows AutoPilot を使用して、生産用の新しいデバイスを事前構成してシームレスにセットアップする                 |
|       FIDO 2 のサポート                             |          共有デバイスの高速かつ安全な認証を有効にする FIDO2 セキュリティ キーのサポート            |
|       プロビジョニングの改善                      |          USB ドライブから HoloLens にプロビジョニング パッケージをシームレスに適用する                              |
|       アプリケーションのインストール状態                 |          アプリの設定アプリのインストール状態を MDM 経由で HoloLens 2 にプッシュした状態を確認する               |
|       構成サービス プロバイダー (AP)   |          管理制御機能を強化する新しい構成サービス プロバイダーを追加しました                 |
|       USB 5G/LTE のサポート                       |          拡張された USB イーサネット機能により、5G/LTE のサポートが可能                                    |
|       ダーク アプリ モード                              |          暗いモードと明るいモードの両方をサポートするアプリで使用できる暗いアプリ モードで、表示エクスペリエンスを向上させる        |
|       音声コマンド                             |          HoloLens ハンズフリーを制御する追加のシステム音声コマンドのサポート                           |
|       手の追跡の改善                 |          手の追跡の改善により、ボタンと 2D スレート操作の精度が向上                        |
|       品質の改善と修正                 |          プラットフォーム全体のさまざまなシステムパフォーマンスと信頼性の向上                            |

### <a name="support-for-windows-autopilot"></a>Windows Autopilot のサポート

Windows Autopilot for HoloLens 2 を使用すると、デバイス販売チャネルは HoloLens を Intune テナントに事前登録できます。 デバイスが到着すると、テナントの下に共有デバイスとして自己展開する準備が整います。 自己展開を利用するには、USB-C-to-Ethernet を使用してセットアップの最初の画面でネットワークに接続する必要があります。

ユーザーが自動パイロットの自己展開プロセスを開始すると、次の手順が完了します。

1. デバイスを Azure Active Directory (Azure AD) に参加させます。
1. Azure AD を使用して、Microsoft Intune (または別の MDM サービス) にデバイスを登録します。
1. デバイスを対象としたポリシー、証明書、およびネットワーク プロファイルをダウンロードします。
1. デバイスをプロビジョニングします。
1. ユーザーにサインイン画面を提示します。

[詳細については、「Windows Autopilot for HoloLens 2 評価ガイド」を参照してください](https://docs.microsoft.com/hololens/hololens2-autopilot)。

*今すぐ AutoPilot プレビューに参加するには、アカウント マネージャーに問い合わせください。 Autopilot 対応デバイスは近日出荷を開始します。*

### <a name="fido2-security-key-support"></a>FIDO2 セキュリティ キーのサポート

HoloLens デバイスを、仕事や学校の環境で他のユーザーと共有するユーザーもいます。 そのため、ユーザーは長いユーザー名とパスワードを入力せずに簡単に入力することが重要です。 Fast Identity Online (FIDO) を使用すると、組織内のすべてのユーザー (Azure AD テナント) は、ユーザー名やパスワードを入力せずに HoloLens にシームレスにサインインできます。

FIDO2 セキュリティ キーは、任意のフォーム ファクターに含め得る"未入力" の標準ベースのパスワードレス認証方法です。 FIDO は、パスワードレス認証のオープン標準です。 これにより、ユーザーと組織は、ユーザー名やパスワードを使用せずにリソースにサインインできます。 代わりに、デバイスに組み込んだ外部セキュリティ キーまたはプラットフォーム キーを使用します。

開始するには、「パスワードレス セキュリティ [キーサインインを有効にする」を参照してください](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)。

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>プロビジョニング パッケージによる MDM 登録の改善

プロビジョニング パッケージを使用すると、HoloLens のアウトボックス エクスペリエンスではなく、構成ファイルを使用して HoloLens 構成を設定できます。 以前は、プロビジョニング パッケージを HoloLens 内部メモリにコピーする必要があった。 USB ドライブに接続して、複数の HoloLens デバイスで再利用しやすく、デバイスを並列にプロビジョニングできるようになります。 プロビジョニング パッケージでは、デバイス管理に登録するフィールドもサポートされますので、プロビジョニング後に手動でセットアップする必要はありません。

以下の手順をお試しください。

1. Windows ストアから最新バージョンの Windows 構成デザイナーを PC にダウンロードします。
1. **[HoloLens デバイスのプロビジョニング]**  >  **HoloLens 2 デバイスのプロビジョニングを選択します**。
2. 構成プロファイルを作成します。 次に、作成されたファイルを USB-C ストレージ デバイスにコピーします。
3. USB-C デバイスを、新しくフラッシュされた HoloLens に接続します。 次に、**ボリューム ダウン電源**  +  **ボタンを押**して、プロビジョニング パッケージを適用します。

### <a name="line-of-business-application-install-status"></a>Line-of-business アプリケーションのインストール状態

ビジネス アプリの MDM アプリの展開と管理は、HoloLens にとって重要です。 管理者とユーザーは、監査と診断のためにアプリのインストール状態を表示する必要があります。 このリリースでは、「Settings Accounts Access **** work or  >  ****  >  **school**  >  **Click on your account Info」に詳細を追加**  >  **しました**。

### <a name="additional-csps-and-policies"></a>その他の CSP とポリシー

構成 [サービス プロバイダー (CSP) は](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) 、デバイスの構成設定を読み取り、設定、変更、または削除するインターフェイスです。 このリリースでは、展開された HoloLens デバイスよりも管理者が持つコントロールを増やすポリシーのサポートを追加しました。 HoloLens でサポートされる CSP の一覧については [、「NetworkQoSPolicy CSP」を参照してください](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。

このリリースの新機能:

**Policy CSP** 

ポリシー構成サービス プロバイダーを使用すると、企業は Windows デバイスでポリシーを構成できます。 このリリースでは、HoloLens の新しいポリシーが追加されました。ここに記載されています。 詳細については [、「HoloLens 2 でサポートされるポリシーの CSP」を参照してください](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)。  

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

NetworkQoSPolicy 構成サービス プロバイダーは、ネットワーク品質サービス (QoS) ポリシーを作成します。 QoS ポリシーは、一連の照合条件に基づいて、ネットワーク トラフィックに一連のアクションを実行します。 詳細については [、「NetworkQoSPolicy CSP」を参照してください](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>5G/LTE テザード デバイスの拡張 USB イーサネット サポート

USB 経由で HoloLens 2 に接続されている場合に、5G/LTE 電話や Wi-Fi ホットスポットなどの特定のモバイル ブロードバンド デバイスを有効にするためにサポートが追加されました。 これらのデバイスは、ネットワーク設定に **別の** イーサネット接続として表示されます。 (外部ドライバーを必要とするモバイル ブロードバンド デバイスはサポートされていません)。この機能を使用すると、Wi-FiテザリングWi-Fi十分なパフォーマンスが得られません。 サポートされている USB デバイスの詳細については [、「Connect to Bluetooth USB-C デバイス」を参照してください](https://docs.microsoft.com/hololens/hololens-connect-devices)。  

### <a name="hand-tracking-improvements"></a>手の追跡の改善

このリリースには、いくつかの手の追跡の機能強化が含まれています。

- **ポイントポーズの安定性:** 手のひらに押し込むときに人差し指を曲げるのに抵抗しました。 この変更により、ボタンの押し方、種類、コンテンツのスクロール時の精度が向上します。 
- **偶発的なエア タップの削減:** エア タップ ジェスチャの検出が改善されました。 複数の一般的なシナリオでは、手をサイドにドロップする場合など、偶発的なライセンス認証が少なくなっています。
- **ユーザー スイッチの信頼性:** デバイスを共有するときに手のサイズを更新する際に、システムの速度と信頼性が向上しました。
- **手盗みを減らしました。** センサーの視点で 2 つ以上の手がある場合の処理が改善されました。 複数のユーザーが近くで作業している場合、追跡された手がユーザーからシーン内の他のユーザーの手に「ジャンプ」する可能性がはるかに低くなります。
- **システムの信頼性:** デバイスの負荷が高いときに、手の追跡が機能しなくする問題を修正しました。

### <a name="dark-mode"></a>濃色モード

現在、多くの Windows アプリでは、暗いモードと明るいモードの両方がサポートされています。 HoloLens 2 ユーザーは、両方をサポートするアプリの既定のモードを選択できます。 更新後、既定のアプリ モードは "濃色" ですが、この設定を簡単に変更**** できます。[設定] [システムの色] に移動する 既定のアプリ  >  ****  >  ****  >  **モードを選択します**。 

次の "インボックス" アプリは、ダーク モードをサポートします。 

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

![暗いモードのウィンドウのタイル](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>システム音声コマンド

これで、デバイス上の任意のアプリで音声コマンドを使用できます。 詳細については、「音声を [使用して HoloLens を操作する」を参照してください](https://docs.microsoft.com/hololens/hololens-cortana)。 [「HoloLens 2 でサポートされている言語」も参照してください](https://docs.microsoft.com/hololens/hololens2-language-support)。  

### <a name="cortana-updates"></a>Cortana の更新

更新されたアプリは Microsoft 365 と統合され、デバイス全体でさらに多くの作業を行うのに役立ちます (現在、US-Englishのみです)。 HoloLens 2 では、Cortana はボリュームの調整や再起動など、特定のデバイス固有のコマンドをサポートしなくなりました。 これらのオプションは、新しいシステム音声コマンドでサポートされています。 新しい Cortana アプリの詳細については、ブログをご [覧ください](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)。

### <a name="quality-improvements-and-fixes"></a>品質の改善と修正

更新プログラムの改善と修正:  
- アクティブなディスプレイ調整システムを導入しました。 この機能により、ホログラムの安定性と配置が向上します。 頭を横に動かすと、その場に残ることになります。
- HoloLens へのWi-Fiが定期的に中断されるバグを修正しました。 アプリケーションが低遅延ストリーミングが必要と示す場合は [、SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)関数を呼び出して修正プログラムを実装します。
- リサーチ モードでのストリーミング中に発生したデバイスのハングを修正しました。
- セッションの再セッション時に、正しいユーザーがサインイン画面に表示されない場合があるバグを修正しました。
- ユーザーが設定を使用して MDM ログをエクスポートできない問題を **修正しました**。
- アウトオブボックスのセットアップ直後のアイトラッキングの精度が予想より低い可能性がある問題を修正しました。
- 特定の条件下でアイ トラッキング サブシステムが初期化または調整を実行できなかった問題を修正しました。
- 既に校正済みのユーザーに目の調整を求める問題を修正しました。
- 目の調整中にドライバーがクラッシュする問題を修正しました。
- 電源ボタンを繰り返し押すと、60 秒のシステム タイムアウトとシェル クラッシュが発生する可能性がある問題を修正しました。
- 深度バッファーの安定性が向上しました。
- ユーザーがフィードバック **を簡単** に共有できるよう、フィードバック ハブに [共有] ボタンを追加しました。
- RoboRaid が正しくインストールされないバグを修正しました。

### <a name="known-issues"></a>既知の問題

- zh-CN システム言語に関する問題により、音声コマンドで複合現実キャプチャを実行したり、デバイスの IP アドレスを表示したりできます。
- "Hey Cortana" 音声ライセンス認証を使用するには、デバイスを起動した後に Cortana アプリを起動する必要があります。 18362 ビルドから更新した場合、以前のバージョンの Cortana アプリの 2 番目のアプリ タイルが表示され、スタート ページで機能しなくなった場合 **もあります**。

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic バージョン 1903 - 2020 年 5 月更新プログラム 
- ビルド 18362.1061

この毎月の品質更新プログラムには、前述のように、チームが Windows Holographic バージョン 2004 May Update で作業していたため、重要な変更点は含められない。

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic バージョン 1903 - 2020 年 4 月更新プログラム
- ビルド 18362.1059

**サポートされているアプリのダーク モード** 

多くの Windows アプリは、暗いモードと明るいモードの両方をサポートしています。 HoloLens 2 のお客様は、両方の配色をサポートするアプリの既定のモードを選択できます。 お客様からのフィードバックに基づいて、既定のアプリ モードを "ダーク" に設定しますが、いつでもこの設定を簡単に変更できます。[設定] > System > **** **Colors**に移動して[既定のアプリ モードを選択する] を探します。

次の "インボックス" アプリは、ダーク モードをサポートします。
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

**更新プログラムの改善と修正:** 
- シェル オーバーレイが複合現実キャプチャに含まれるか確認します。
- Unreal 開発者は、デバイス ポータルの 3D ビュー ページを使用して、アプリケーションをテストおよびデバッグできます。
- *HolographicDepthReprojectionMethod DepthReprojection*アルゴリズムを使用すると、複合現実キャプチャのホログラムの安定性が向上しました。
- 32 ビット アプリで"WinRT IStreamSocketListener API Class が登録されていません" というエラーをARMしました。

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic バージョン 1903 - 2020 年 3 月更新プログラム 
- ビルド 18362.1056

更新プログラムの改善と修正:

- *HolographicDepthReprojectionMethod AutoPlanar*アルゴリズムを使用すると、複合現実キャプチャのホログラムの安定性が向上しました。
- 深度 MF サンプルに接続されている座標系がパブリック ドキュメントと一致している必要があります。
- ユーザーがデバイス ポータルを通じて大量のテキストを貼り付け可能にすることで、開発者の生産性が向上しました。

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic バージョン 1903 - 2020 年 2 月更新プログラム 
- ビルド 18362.1053

更新プログラムの改善と修正:

- Unity アプリケーションの HolographicSpace.UserPresence API を一時的に無効にします。 この変更により、"バックグラウンドで実行" 設定が有効になっている場合でも、バイザーが反転した場合に一部のアプリが一時停止する問題が回避されます。
- ユーザーが UI がフリーズし、数秒後にシェルに戻るという、手の追跡によるランダムな HUP クラッシュを修正しました。
- 人差し指で突っ込むときに、その指の上部が予期せずカールしそうにならず、手の追跡が改善されました。
- ヘッド 追跡、空間マッピング、その他のランタイムの信頼性が向上しました。

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic バージョン 1903 - 2020 年 1 月更新 
- ビルド 18362.1043
 
更新プログラムの改善と修正:

- HoloLens 2 エミュレーターを操作するときに、排他的なアプリの安定性が向上しました。

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic バージョン 1903 - 2019 年 12 月更新プログラム 
- ビルド 18362.1042

更新プログラムの改善と修正:

- 最終段階の再現 (LSR) 修正プログラムが導入されました。 ホログラムの深度をより正確に説明することで、より安定した鮮明なホログラムの表示を改善しました。 この現象は、アプリがホログラムの深度を正しく設定しない場合、この更新プログラムの後に顕著になります。
- 排他的なアプリと排他的なアプリ間のナビゲーションの安定性を修正しました。
- デバイスが数日間スタンバイ状態になっていた後、複合現実キャプチャでビデオを記録できない問題を解決しました。
- ホログラムの安定性が向上しました。

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic バージョン 1903 - 2019 年 11 月更新プログラム 
- ビルド 18362.1039

更新プログラムの改善と修正:

- en-CA**** および en-AU の初期セットアップ中に音声コマンドを選択する機能が修正されました。
- 最新の Unity および Mixed Reality バージョン (MRTK) で遠く離れた場所に配置Toolkit品質が向上しました。
- スタート メニューが開いて閉じるまで、ホログラフィック アプリケーションが起動時に一時停止状態で停止する問題を修正しました。
- HoloLens 2 とエミュレーターの OpenXR ランタイム準拠の修正と改善。
