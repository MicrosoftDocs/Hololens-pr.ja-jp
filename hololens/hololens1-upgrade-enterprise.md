---
title: Windows Holographic for Business 機能のロック解除
description: Windows ホログラフィック for Business にアップグレードする場合、HoloLens にはビジネス向けに設計された追加機能が用意されています。
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
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829336"
---
# Windows Holographic for Business 機能のロック解除

> [!IMPORTANT]
> このページは、HoloLens 第1世代にのみ適用されます。

Microsoft HoloLens は、Windows ホログラフィック (HoloLens 向けに設計された Windows 10 のエディション) と、ビジネス向けに設計された追加機能を提供する[商用スイート](hololens-commercial-features.md)で実行される*開発版*で利用できます。

Commercial Suite を購入すると、Windows Holographic を Windows Holographic for Business にアップグレードするライセンスを受け取ります。 このライセンスは、組織の[モバイルデバイス管理 (MDM) プロバイダー](#edition-upgrade-by-using-mdm)または[プロビジョニングパッケージ](#edition-upgrade-by-using-a-provisioning-package)を使って、デバイスに適用できます。

> [!TIP]
> Windows 10 バージョン1803では、[**設定**システム] を選択することにより、HoloLens が business エディションにアップグレードされていることを確認でき  >  **System**ます。

## MDM を使用してエディションをアップグレードする

エンタープライズ ライセンスは、[WindowsLicensing 構成サービス プロバイダー (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) をサポートする任意の MDM プロバイダーを使って適用できます。 最新バージョンの Microsoft MDM API では、WindowsLicensing CSP がサポートされる予定です。

Microsoft Intune を使って HoloLens をアップグレードするための詳しい手順については、「 [Windows ホログラフィックを実行しているデバイスを Windows ホログラフィック For Business にアップグレードする](https://docs.microsoft.com/intune/holographic-upgrade)」を参照してください。

 他の MDM プロバイダーでは、ポリシーをセットアップして展開する具体的な手順が異なる場合があります。

## プロビジョニングパッケージを使用したエディションのアップグレード

プロビジョニング パッケージは、Windows 構成デザイナー ツールにより作成された、指定された構成をデバイスに適用するファイルです。

### Windows Holographic エディションをアップグレードするプロビジョニング パッケージの作成

1. [HoloLens 用プロビジョニング パッケージを作成します。](hololens-provisioning.md)
1. **[実行時設定]** > **[EditionUpgrade]**、**[EditionUpgradeWithLicense]** の順に移動します。

    ![選んだライセンス設定でエディションをアップグレード](images/icd1.png)

1. 商用製品を購入したときに提供された XML ライセンスファイルを見つけます。

    > [!NOTE]
    > [プロビジョニング パッケージでは追加の設定](hololens-provisioning.md)を構成できます。

1. [**ファイル**] メニューで、[**保存**] を選択します。 

1. プロジェクトファイルに機密情報が含まれている可能性があるという警告を読み、[ **OK]** をクリックします。

    > [!IMPORTANT]
    > プロビジョニングパッケージを作成する場合は、プロジェクトファイルとプロビジョニングパッケージ (ppkg) ファイルに機密情報を含めることができます。 .ppkg ファイルは暗号化するかどうかを選べますが、プロジェクト ファイルは暗号化されません。 プロジェクトファイルは安全な場所に保存して、不要になった時点でプロジェクトファイルを削除する必要があります。

1. **[エクスポート]** メニューの **[プロビジョニング パッケージ]** を選びます。

1. [**所有者**] を**IT 管理**者に変更します。これにより、このプロビジョニングパッケージの優先順位が、別のソースからこのデバイスに適用されている他のアプリよりも高くなります。次に、[**次へ**] を選びます。

1. **[パッケージのバージョン]** の値を設定します。

    > [!TIP]
    > 既存のパッケージに変更を加えてバージョン番号を変更することで、以前に適用されたパッケージを更新できます。

1. **プロビジョニングパッケージの [セキュリティの詳細の選択**] で、[**次へ**] を選びます。

1. [**次へ**] を選択して、プロビジョニングパッケージをビルドするときの出力場所を指定します。 既定では、Windows ICD はプロジェクト フォルダーを出力先として使います。

    必要に応じて [**参照**] を選択して、既定の出力場所を変更できます。

1. **[次へ]** を選択します。

1. [**ビルド**] を選択して、パッケージの作成を開始します。 ビルドページにプロジェクト情報が表示され、進行状況バーにはビルドの状態が示されます。

1. ビルドが完了したら、[**完了**] を選びます。

### HoloLens へのプロビジョニング パッケージの適用

1. USB ケーブルを使って、デバイスを PC に接続します。 デバイスを起動しますが、最初のセットアップエクスペリエンスの [**自動調整**] ページ (青いボックスが付いた最初のページ) を超えて続行しないでください。 PC では、HoloLens がエクスプローラーでデバイスとして表示されます。

    > [!NOTE]
    > HoloLens デバイスで Windows 10 バージョン1607またはそれ以前のバージョンを実行している場合は、デバイス上で**ボリュームダウン**と**電源**ボタンを同時に押すことで、エクスプローラーを開きます。

1. エクスプローラーで、プロビジョニング パッケージ (.ppkg) をデバイス ストレージに ドラッグ アンド ドロップします。

1. HoloLens が [**自動調整**] ページに残っている状態で、**音量**を短くして、**電源**ボタンをもう一度同時に放します。

1. パッケージを信頼していて、それを適用する場合は、HoloLens から要求されます。 パッケージが信頼できることを確認します。

1. パッケージが正常に適用されたかどうかが表示されます。 正常に適用されなかった場合は、パッケージを修正して、もう一度試してください。 正常に終了したら、デバイスのセットアップを続行します。
