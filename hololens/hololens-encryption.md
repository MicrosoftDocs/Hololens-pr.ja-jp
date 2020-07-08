---
title: HoloLens BitLocker 暗号化
description: Bitlocker デバイスの暗号化を有効にして、HoloLens に保存されたファイルを保護する
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: a18d9e890b34f28ffcd8be7546dcdbe08e9934a6
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857815"
---
# HoloLens BitLocker 暗号化

HoloLens (第1世代) と HoloLens 2 のどちらでも、BitLocker を使ったデバイスの暗号化がサポートされますが、HoloLens 2 では常に BitLocker を有効にします。

この記事では、HoloLens (第1世代) で BitLocker を有効にして管理する方法について説明します。

HoloLens (第1世代) では、BitLocker デバイス暗号化を手動で有効にするか、モバイルデバイス管理 (MDM) を使用することができます。 次の手順に従って、 [BitLocker デバイスの暗号化](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption)を有効にして、HoloLens に保存されているファイルと情報を保護します。 デバイスの暗号化は、AES-CBC 128 暗号化メソッドを使用してデータを保護するのに役立ちます。これは、BitLocker 構成サービスプロバイダー (CSP) の[Encryptionmethodbydrivetype メソッド 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype)と同じです。 適切な暗号化キー (パスワードなど) を持っているユーザーは、暗号化を解除したり、データの回復を実行したりできます。

## MDM を使ってデバイスの暗号化を有効にする

モバイルデバイス管理 (MDM) プロバイダーを使用して、デバイスの暗号化を必要とするポリシーを適用できます。 使用するポリシーは、ポリシー CSP の[Security/RequireDeviceEncryption 設定](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption)です。

[「Microsoft Intune を使ってデバイスの暗号化を有効にする」の手順を参照してください。](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

他の MDM ツールについては、MDM プロバイダーのドキュメントで手順をご覧ください。 MDM プロバイダーでデバイスの暗号化にカスタム URI が必要な場合は、次の構成を使用します。

- **名前**: 任意の名前
- **説明**: 省略可能
- **OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **データ型**: 整数型
- **値**: `1`

## プロビジョニング パッケージを使ってデバイスの暗号化を有効にする

プロビジョニング パッケージは、Windows 構成デザイナー ツールにより作成された、指定された構成をデバイスに適用するファイルです。 

### Windows ホログラフィック edition をアップグレードして暗号化を有効にするプロビジョニングパッケージを作成する

1. [HoloLens 用プロビジョニング パッケージを作成します。](hololens-provisioning.md)
1. **[実行時設定]** > **[ポリシー]** > **[セキュリティ]** に移動し、**[RequireDeviceEncryption]** を選びます。

    ![[はい] に構成されているデバイスの暗号化の設定が必要](images/device-encryption.png)

1. 商用製品を購入したときに提供された XML ライセンスファイルを見つけます。

1. Commercial Suite の購入時に提供された XML ライセンス ファイルを参照して選びます。
    > [!NOTE]
    > [プロビジョニング パッケージでは追加の設定](hololens-provisioning.md)を構成できます。

1. **[ファイル]** メニューの **[上書き保存]** をクリックします。 

1. プロジェクトファイルに機密情報が含まれている可能性があることを説明する警告を読み、[ **OK]** をクリックします。

    > [!IMPORTANT]
    > プロビジョニングパッケージを作成する場合は、プロジェクトファイルとプロビジョニングパッケージ (ppkg) ファイルに機密情報を含めることができます。 .ppkg ファイルは暗号化するかどうかを選べますが、プロジェクト ファイルは暗号化されません。 プロジェクトファイルは安全な場所に保存して、不要になった時点でプロジェクトファイルを削除する必要があります。

1. **[エクスポート]** メニューの **[プロビジョニング パッケージ]** をクリックします。
1. **[所有者]** を **[IT 管理者]** に変更して、このプロビジョニング パッケージの優先順位を他のソースからこのデバイスに適用されるプロビジョニング パッケージよりも高くします。次に、**[次へ]** を選択します。
1. **[パッケージのバージョン]** の値を設定します。

    > [!TIP]
    > 既存のパッケージに変更を加えてバージョン番号を変更することで、以前に適用されたパッケージを更新することができます。

1. **[プロビジョニング パッケージのセキュリティ情報の選択]** で、**[次へ]** をクリックします。
1. **[次へ]** をクリックし、ビルドしたプロビジョニング パッケージの出力先を指定します。 既定では、Windows ICD はプロジェクト フォルダーを出力先として使います。

    必要に応じて、 [参照] をクリックして既定の出力先を変更できます。

1. **[次へ]** をクリックします。
1. パッケージのビルドを開始するには、 **[ビルド]** をクリックします。 ビルド ページにプロジェクト情報が表示され、進行状況バーでビルドの状態が示されます。
1. ビルドが完了したら、**[完了]** をクリックします。

### HoloLens へのプロビジョニング パッケージの適用

1. USB 経由でデバイスを PC に接続してデバイスを起動しますが、初期セットアップ エクスペリエンスの**調整**ページ (青のボックスが表示された最初のページ) より先には進まないでください。
1. **[音量を下げる]** ボタンと**電源**ボタンを同時に短く押して離します。
1. HoloLens が PC のエクスプローラーにデバイスとして表示されます。
1. エクスプローラーで、プロビジョニング パッケージ (.ppkg) をデバイス ストレージに ドラッグ アンド ドロップします。
1. **調整**ページが表示されている間に、もう一度 **[音量を下げる]** ボタンと**電源**ボタンを同時に短く押して離します。
1. パッケージを信頼して適用するかどうかを確認するメッセージがデバイスに表示されます。 パッケージが信頼できることを確認します。
1. パッケージが正常に適用されたかどうかが表示されます。 失敗した場合、パッケージを修正してもう一度試します。 成功した場合はデバイスのセットアップを続けます。

> [!NOTE]
> 2016 年 8 月より前に購入したデバイスの場合、プロビジョニング パッケージを適用するには、Microsoft アカウントを使ってデバイスにサインインして最新の OS 更新プログラムを入手し、OS をリセットする必要があります。

## デバイスの暗号化を確認する

暗号化は、HoloLens で自動的に行われます。 デバイスの暗号化の状態を確認するには

- HoloLens で、**[設定]** > **[システム]** > **[バージョン情報]** に移動します。 デバイスが暗号化されている場合、 **BitLocker**は**有効に**なります。 

    ![BitLocker が有効になっていることを示す [バージョン情報] 画面](images/about-encryption.png)
