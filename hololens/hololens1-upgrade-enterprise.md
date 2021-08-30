---
title: Windows Holographic for Business 機能のロック解除
description: アプリケーションにアップグレードするとWindows Holographic for Business、HoloLensビジネス向けに設計された追加の機能が提供されます。
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: c6d1225dc6da1c039a34fc2782f23330ae40f280
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189190"
---
# <a name="unlock-windows-holographic-for-business-features"></a>Windows Holographic for Business 機能のロック解除

> [!IMPORTANT]
> このページは、第 1 世代HoloLensにのみ適用されます。

Microsoft HoloLensは、Windows Holographic (HoloLens 用に設計された Windows 10 のエディション) を実行する Development *Edition* と、ビジネス向けに設計された追加機能を提供する [Commercial Suite](hololens-commercial-features.md)で使用できます。

Commercial Suite を購入すると、Windows Holographic を Windows Holographic for Business にアップグレードするライセンスを受け取ります。 このライセンスは、組織のモバイル デバイス管理 [(MDM)](#edition-upgrade-by-using-mdm) プロバイダーまたはプロビジョニング パッケージ を使用して、デバイス [に適用できます](#edition-upgrade-by-using-a-provisioning-package)。

> [!TIP]
> バージョン Windows 10 1803 では、 [システム] を選択して、HoloLens がビジネス エディションにアップグレード設定  >  **できます**。

## <a name="edition-upgrade-by-using-mdm"></a>MDM を使用したエディションのアップグレード

エンタープライズ ライセンスは、[WindowsLicensing 構成サービス プロバイダー (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) をサポートする任意の MDM プロバイダーを使って適用できます。 最新バージョンの Microsoft MDM API では、WindowsLicensing CSP がサポートされる予定です。

Microsoft Intune を使用して HoloLens をアップグレードする手順については、「Windows [Holographic](/intune/holographic-upgrade)を実行しているデバイスを Windows Holographic for Business にアップグレードする」を参照してください。

 他の MDM プロバイダーでは、ポリシーをセットアップして展開する具体的な手順が異なる場合があります。

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>プロビジョニング パッケージを使用したエディションのアップグレード

プロビジョニング パッケージは、Windows 構成デザイナー ツールにより作成された、指定された構成をデバイスに適用するファイルです。

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>Windows Holographic エディションをアップグレードするプロビジョニング パッケージの作成

1. [HoloLens 用プロビジョニング パッケージを作成します。](hololens-provisioning.md)
1. [ランタイム設定 **] [**  >  **エディション] [アップグレード] に移動** し、 [エディション] [アップグレード] **[WithLicense] を選択します**。

    ![ライセンス設定が選択されたエディションをアップグレードします。](images/icd1.png)

1. Commercial Suite を購入した際に提供された XML ライセンス ファイルを見つける。

    > [!NOTE]
    > [プロビジョニング パッケージでは追加の設定](hololens-provisioning.md)を構成できます。

1. **[ファイル]** メニューで、 **[保存]** を選択します。 

1. プロジェクト ファイルに機密情報が含まれている可能性があるという警告を読み **、[OK] をクリックします**。

    > [!IMPORTANT]
    > プロビジョニング パッケージをビルドするときに、プロジェクト ファイルとプロビジョニング パッケージ (.ppkg) ファイルに機密情報を含めることもできます。 .ppkg ファイルは暗号化するかどうかを選べますが、プロジェクト ファイルは暗号化されません。 プロジェクト ファイルは安全な場所に格納し、不要になったらプロジェクト ファイルを削除する必要があります。

1. **[エクスポート]** メニューの **[プロビジョニング パッケージ]** をクリックします。

1. [ **所有者]** **を [IT 管理者**] に変更します。これにより、このプロビジョニング パッケージの優先順位が、異なるソースからこのデバイスに適用されている他のユーザーよりも高い値に設定され、[次へ] を **選択します**。

1. **[パッケージのバージョン]** の値を設定します。

    > [!TIP]
    > 既存のパッケージに変更を加えてバージョン番号を変更することで、以前に適用されたパッケージを更新することができます。

1. [ **プロビジョニング パッケージのセキュリティの詳細の選択] で、[次へ**] を **選択します**。

1. [ **次へ** ] を選択して、プロビジョニング パッケージがビルドされた後の出力場所を指定します。 既定では、Windows ICD はプロジェクト フォルダーを出力先として使います。

    必要に応じて、 [参照] **を選択** して、既定の出力場所を変更できます。

1. **[次へ]** を選択します。

1. [ビルド **] を** 選択して、パッケージのビルドを開始します。 ビルド ページにプロジェクト情報が表示され、進行状況バーにビルドの状態が示されます。

1. ビルドが完了したら、 [完了] を **選択します**。

### <a name="apply-the-provisioning-package-to-hololens"></a>HoloLens へのプロビジョニング パッケージの適用

1. USB ケーブルを使用して、デバイスを PC に接続します。 デバイスを起動しますが、初期セットアップ エクスペリエンスの適合ページ (青いボックスが付いた最初のページ) を過ぎて続行しない。 PC では、HoloLensデバイスとしてデバイスとして表示エクスプローラー。

    > [!NOTE]
    > HoloLens デバイスが Windows 10 バージョン 1607 以前を実行している場合は、デバイスで [ボリューム ダウン] ボタンと[電源]ボタンを同時に押して離すことで エクスプローラー を開きます。

1. エクスプローラーで、プロビジョニング パッケージ (.ppkg) をデバイス ストレージに ドラッグ アンド ドロップします。

1. このHoloLensページに **表示されている間** に、 [ボリューム ダウン] ボタンと [電源] ボタンを少し押して離します。

1. HoloLens信頼し、それを適用する必要がある場合は、この質問を受け取る必要があります。 パッケージが信頼できることを確認します。

1. パッケージが正常に適用されたかどうかが表示されます。 正常に適用されていない場合は、パッケージを修正して再試行できます。 成功した場合は、デバイスのセットアップに進みます。
