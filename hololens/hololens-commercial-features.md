---
title: HoloLens 2 の機能とソリューション
description: 企業による HoloLens デバイスの管理を容易にする Microsoft HoloLens Commercial の機能について説明します。
author: joyjaz
ms.author: v-jjaswinski
ms.date: 06/28/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: skerewa
appliesto:
- HoloLens 2
keywords: HoloLens 2, Commercial, 機能, MDM, モバイル デバイス管理, キオスク モード, アプリケーション, ID, Bitlocker, 虹彩, Windows Hello, Azure の利用, Autopilot, Mixed Reality, WDAC
ms.openlocfilehash: 88a75224909fd64e387cfb5677056e2ae5d62e4b3518aa758f22ec66a86a8355
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665346"
---
# <a name="hololens-2-capabilities-and-solutions"></a>HoloLens 2 の機能とソリューション

## <a name="what-can-hololens-2-do-for-you"></a>HoloLens 2 でできること

HoloLens 2 で Mixed Reality アプリケーションを使用すると、共同作業の境界がなくなり、正確に作業できるので、従業員の生産性が向上します。 エラーなしで安全にタスクを完了させることに常に集中するため、組み込みの音声コマンド、視線追跡、ワールドアンカーを使用して、より長く快適にヘッドアップとハンズフリーを維持してください。 リモートの同僚とリアルタイムで結び付き、物理環境にオーバーレイされた広範なホログラフィック キャンバスで連携して、作業場所で問題を迅速に解決します。 Microsoft のセキュリティ、信頼性、拡張性でサポートされる堅牢なアプリケーションのエコシステムを使用して、ROI をすぐに実現できます。  

[!INCLUDE [solutions](includes/hlsolutions.md)]

## <a name="hololens-2-capabilities"></a>HoloLens 2 の機能

HoloLens 2 を強力にしているものは何でしょうか。

| 機能 | 説明 |
|---------|-------------|
| ワールドアンカー | アンカーされたホログラムは、その場に正確にとどまります。 HoloLens 2 によってワークスペースが認識されます。 そのため、デジタル コンテンツは時間が経っても維持され、作業しているオブジェクトまたはサーフェイスに固定されます。 |
| ハンド トラッキング | 自然な形でホログラムに触り、つかみ、移動します。 HoloLens 2 は、対話式操作で新しい満足が得られるようにユーザーの手に対応します。 |
| 視線追跡 | 新しいレベルのコンテキストと人間の理解を活用できます。 HoloLens 2 はユーザーが見ているものを正確に把握するので、ユーザーの意図を理解し、リアルタイムでホログラムをユーザーの目に対応させることができます。 |
| 音声対応 | 組み込みの音声コマンドを使用すると、手が塞がっていても、HoloLens 2 内ですばやく移動したり操作したりすることができます。 |
| 人間工学 | HoloLens 2 は、広範な使用をサポートするダイヤルイン フィット システムを含めても軽量 (3.28 kg) です。 |
| 大きな視界 | 高解像度で大きな視野のディスプレイにより、ホログラフィック キャンバスを拡大します。 |
| 接続不要 | ワイヤーや外部パックを使用せず、自由に移動して作業できます。 |
| Azure の利用 | Azure Mixed Reality サービスを使用してユーザー間で保持される場所やオブジェクトに固定できる、高忠実度の 3D コンテンツをストリーム配信します。
| 複合現実キャプチャ | エクスペリエンスを写真またはビデオとしてドキュメント化し、リアルタイムで他のユーザーと共有します。 |
| Windows Hello for Business | 虹彩による生体認証を使用して、作業の流れを迅速かつ安全に入ることができます。 |
| Windows Autopilot | 分散した作業サイトですぐに使用できるように、HoloLens 2 のサービスをセットアップして事前構成します。 |
| OS の更新 | 毎月のサービス更新プログラムでセキュリティを確保し、半年ごとのリリースで新しい生産性と管理の機能を利用できます。 |
| デバイスを簡単に管理 | Microsoft Intune、VMware Workspace One、MobileIron などのソリューションを使用して、複数の HoloLens 2 デバイスを同時に管理します。 |
| 規制された環境での運用 | HoloLens 2 の広範なデバイス ポートフォリオにより、指定された ISO クラス 5.0 や UL クラス I ディビジョン 2 などの高度に規制された環境をサポートします。 |


## <a name="managing-hololens-2-in-your-organization"></a>組織内での HoloLens 2 の管理
HoloLens 2 には、組織で HoloLens デバイスを簡単に管理および使用するための機能が含まれています。 一部の機能はデバイスに含まれていますが、他は [HoloLens 用モバイル デバイス管理 (MDM)](hololens-mdm-configure.md) によって、または [Windows 構成デザイナー](app-deploy-provisioning-package.md#setup)を使用して[パッケージをプロビジョニングする](hololens-provisioning.md)ことによって有効にできます。

| ご希望のコースをお選びください。 | 解決策 | 説明 |  
|---------| ------------|------------|
エンド ユーザーがサインインする方法を管理する | [**ID**](hololens-identity.md) | HoloLens 2 では、複数の種類のユーザー ID がサポートされています - Azure Active Directory id (AAD)、Microsoft アカウント (MSA)、ローカル アカウント。  |
| ユーザー データを暗号化する | [**データのセキュリティ**](security-encryption-data-protection.md) | HoloLens 2 では、他の Windows デバイスと同じレベルのセキュリティ保護を提供するために、BitLocker データ暗号化が有効になっています。 | 
組織内の Hololens デバイスを管理する | [**モバイル デバイス管理**](hololens-mdm-configure.md) | 中央の場所から複数の HoloLens 2 デバイスの設定を管理し、インストールするアプリを選択し、組織のニーズに合わせて調整されたセキュリティ構成を設定します。 | 
|新しいユーザーとデバイスのセットアップ時間を最短にする | [**Autopilot**](hololens2-autopilot.md) | Microsoft エンドポイント マネージャーで Out-of-Box Experience (OOBE) を構成し、エンドユーザーがほとんど、またはまったく操作しないでビジネス用にデバイスを準備できるようにします。 |  
| デバイスの OS 更新プログラムを制御する | [**Windows Update for Business**](hololens-updates.md#managing-updates-by-using-windows-update-for-business) | Windows Update for Business は、デバイスに対するオペレーティング システムの更新プログラムの適用を制御し、長期間のサービスチャネルのサポートを提供します。 |  
| 特定のアプリや LOB アプリのダウンロードを許可する |[**アプリケーション管理**](app-deploy-overview.md) | 選択された HoloLens 2 ユーザー グループのアプリを配布および制御する方法を選択します。 | 
| [スタート] メニューで特定のアプリを表示または非表示にする |[**キオスク モード**](hololens-kiosk.md) | アプリのデモや専用のビジネス アプリで使用するために固定目的のデバイスとして機能するように HoloLens 2 を構成します。 
| アプリをロックダウンすることで環境をセキュリティ保護する | [**WDAC**](windows-defender-application-control-wdac.md) | Windows Defender Application Control (WDAC) を使用して、アプリやプロセスがデバイス ユーザーによって起動されるのをブロックします。
| アプリとプロセスのルールを使用してデバイスのセキュリティを管理する | [**ポリシー (CSP)**](hololens-csp-policy-overview.md) | IT 管理者は、HoloLens 2 のサポートされているポリシー CSP の既存の一覧を使用して、ポリシー設定を定義および実装できます。 |  
| デバイスがインターネットに接続する方法を管理する | [**ネットワークと接続性**](hololens-certificates-network.md) | 証明書ベースの認証を使用して Wi-Fi、VPN、または内部リソースにアクセスします。 | 
| デバイスを複数のユーザーと共有する | [**表示の自動カスタマイズ**](hololens-calibration.md#auto-eye-position-support) | HoloLens 2 の表示は視線の自動調整 (AEP) によって自動的に調整されるので、デバイスを[ユーザー間で共有する](hololens-multiple-users.md)ときに、手動調整プロセスを実行する必要がなくなります。 |

上記のソリューションの[ライセンス要件](hololens-licenses-requirements.md)を確認してください。

## <a name="next-steps"></a>次の手順
> [!div class="nextstepaction"]
> [HoloLens 2 のオプションを調べる](hololens2-options.md)

> [!div class="nextstepaction"]
>[HoloLens 2 の展開計画](hololens-requirements.md) 
