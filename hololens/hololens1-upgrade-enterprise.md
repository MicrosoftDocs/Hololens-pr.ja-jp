---
title: Windows Holographic for Business 機能のロック解除
description: Windows Holographic for Business にアップグレードすると、HoloLens はビジネス向けに設計された追加機能を提供します。
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
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309473"
---
# <a name="unlock-windows-holographic-for-business-features"></a>Windows Holographic for Business 機能のロック解除

> [!IMPORTANT]
> このページは、HoloLens ファースト世代にのみ適用されます。

Microsoft HoloLens は、Windows Holographic (HoloLens 向けに設計された Windows 10 のエディション) を実行する *Development Edition* と、ビジネス向けに設計された追加機能を提供する [商用スイート](hololens-commercial-features.md)で利用できます。

Commercial Suite を購入すると、Windows Holographic を Windows Holographic for Business にアップグレードするライセンスを受け取ります。 このライセンスは、組織の [モバイルデバイス管理 (MDM) プロバイダー](#edition-upgrade-by-using-mdm) または [プロビジョニングパッケージ](#edition-upgrade-by-using-a-provisioning-package)を使用して、デバイスに適用できます。

> [!TIP]
> Windows 10 バージョン1803では、[**設定** システム] を選択して、HoloLens が business edition にアップグレードされていることを確認でき  >  ます。

## <a name="edition-upgrade-by-using-mdm"></a>MDM を使用したエディションのアップグレード

エンタープライズ ライセンスは、[WindowsLicensing 構成サービス プロバイダー (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) をサポートする任意の MDM プロバイダーを使って適用できます。 最新バージョンの Microsoft MDM API では、WindowsLicensing CSP がサポートされる予定です。

Microsoft Intune を使用して HoloLens をアップグレードする詳細な手順については、「 [Windows Holographic を実行するデバイスを Windows Holographic For Business にアップグレードする](https://docs.microsoft.com/intune/holographic-upgrade)」を参照してください。

 他の MDM プロバイダーでは、ポリシーをセットアップして展開する具体的な手順が異なる場合があります。

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>プロビジョニングパッケージを使用したエディションのアップグレード

プロビジョニング パッケージは、Windows 構成デザイナー ツールにより作成された、指定された構成をデバイスに適用するファイルです。

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>Windows Holographic エディションをアップグレードするプロビジョニング パッケージの作成

1. [HoloLens 用プロビジョニング パッケージを作成します。](hololens-provisioning.md)
1. **ランタイム設定**  >  **EditionUpgrade** にアクセスし、[ **EditionUpgradeWithLicense**] を選択します。

    ![選んだライセンス設定でエディションをアップグレード](images/icd1.png)

1. 商用スイートを購入したときに提供された XML ライセンスファイルを見つけます。

    > [!NOTE]
    > [プロビジョニング パッケージでは追加の設定](hololens-provisioning.md)を構成できます。

1. **[ファイル]** メニューの **[保存]** をクリックします。 

1. プロジェクトファイルに機密情報が含まれている可能性があることを示す警告を確認し、[ **OK]** をクリックします。

    > [!IMPORTANT]
    > プロビジョニングパッケージを作成するときに、プロジェクトファイルとプロビジョニングパッケージ (ppkg) ファイルに機密情報を含めることができます。 .ppkg ファイルは暗号化するかどうかを選べますが、プロジェクト ファイルは暗号化されません。 プロジェクトファイルは安全な場所に保存し、不要になったときにプロジェクトファイルを削除する必要があります。

1. **[エクスポート]** メニューの **[プロビジョニング パッケージ]** をクリックします。

1. [ **所有者** ] を **IT 管理** 者に変更します。これにより、このプロビジョニングパッケージの優先順位が、別のソースからこのデバイスに適用されている他のものよりも高くなるように設定し、[ **次へ**] を選択します。

1. **[パッケージのバージョン]** の値を設定します。

    > [!TIP]
    > 既存のパッケージに変更を加えてバージョン番号を変更することで、以前に適用されたパッケージを更新することができます。

1. [ **プロビジョニングパッケージのセキュリティの詳細の選択**] で、[ **次へ**] を選択します。

1. [ **次** へ] を選択して、プロビジョニングパッケージを構築した後の出力場所を指定します。 既定では、Windows ICD はプロジェクト フォルダーを出力先として使います。

    必要に応じて、[ **参照** ] を選択して既定の出力場所を変更することもできます。

1. **[次へ]** を選択します。

1. [ **ビルド** ] を選択して、パッケージのビルドを開始します。 [ビルド] ページにプロジェクト情報が表示され、進行状況バーにビルドの状態が示されます。

1. ビルドが完了したら、[ **完了**] を選択します。

### <a name="apply-the-provisioning-package-to-hololens"></a>HoloLens へのプロビジョニング パッケージの適用

1. USB ケーブルを使用して、デバイスを PC に接続します。 デバイスを起動しますが、初期セットアップエクスペリエンス (青いボックスの最初のページ) の [ **フィット** ] ページを超えないで続行しないでください。 PC では、HoloLens はエクスプローラーでデバイスとして表示されます。

    > [!NOTE]
    > HoloLens デバイスで Windows 10 バージョン1607以前が実行されている場合は、デバイス上で **ボリュームダウン** と **電源** ボタンを同時に押すことによって、ファイルエクスプローラーを開きます。

1. エクスプローラーで、プロビジョニング パッケージ (.ppkg) をデバイス ストレージに ドラッグ アンド ドロップします。

1. HoloLens が引き続き [ **適合** ] ページにあるのに対して、 **音量** を簡単に押したまま、[ **電源** ] ボタンをもう一度押します。

1. HoloLens を使用すると、パッケージを信頼するかどうかを確認するメッセージが表示され、適用されます。 パッケージが信頼できることを確認します。

1. パッケージが正常に適用されたかどうかが表示されます。 正常に適用されなかった場合は、パッケージを修正して、もう一度やり直してください。 成功した場合は、デバイスのセットアップを続行します。
