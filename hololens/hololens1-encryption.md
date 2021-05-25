---
title: HoloLens BitLocker 暗号化
description: BitLocker デバイス暗号化を有効にして、HoloLens mixed reality デバイスに格納されているファイルを保護する方法について説明します。
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
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 2929cbea826e0cc92a72550c7874995506b94257
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397283"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a>HoloLens (第1世代) BitLocker 暗号化

HoloLens (第1世代) と HoloLens 2 の両方で、BitLocker を使用したデバイスの暗号化がサポートされていますが、HoloLens 2 では常に BitLocker が有効になっています。

この記事では、HoloLens (第1世代) で BitLocker を有効にして管理する方法について説明します。

HoloLens (第1世代) では、BitLocker デバイス暗号化を手動で、またはモバイルデバイス管理 (MDM) を使用して有効にすることができます。 [BitLocker デバイスの暗号化](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption)を有効にして、HoloLens に格納されているファイルと情報を保護するには、次の手順に従います。 デバイスの暗号化は、AES-CBC 128 暗号化方式を使用してデータを保護するのに役立ちます。これは、BitLocker 構成サービスプロバイダー (CSP) の [Encryptionmethodbydrivetype メソッド 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) に相当します。 正しい暗号化キー (パスワードなど) を持つ担当者は、暗号化を解除したり、データの回復を実行したりすることができます。

## <a name="enable-device-encryption-using-mdm"></a>MDM を使ってデバイスの暗号化を有効にする

モバイルデバイス管理 (MDM) プロバイダーを使用して、デバイスの暗号化を必要とするポリシーを適用することができます。 使用するポリシーは、ポリシー CSP の [Security/RequireDeviceEncryption 設定](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) です。

[Microsoft Intune を使用してデバイスの暗号化を有効にする手順を参照してください。](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

他の MDM ツールについては、MDM プロバイダーのドキュメントで手順をご覧ください。 MDM プロバイダーでデバイスの暗号化にカスタム URI が必要な場合は、次の構成を使用します。

- **名前**: 任意の名前
- **説明**: 省略可能
- **OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **データ型**: 整数
- **値**: `1`

## <a name="enable-device-encryption-using-a-provisioning-package"></a>プロビジョニング パッケージを使ってデバイスの暗号化を有効にする

プロビジョニング パッケージは、Windows 構成デザイナー ツールにより作成された、指定された構成をデバイスに適用するファイルです。 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a>Windows Holographic edition をアップグレードして暗号化を有効にするプロビジョニングパッケージを作成する

1. [HoloLens 用プロビジョニング パッケージを作成します。](hololens-provisioning.md)
1. [**ランタイム設定**  >  ] [**ポリシー**  >  ] [**セキュリティ**] にアクセスし、[ **requiredeviceencryption**] を選択します。

    ![[はい] に構成されているデバイスの暗号化の設定が必要](images/device-encryption.png)

1. 商用スイートを購入したときに提供された XML ライセンスファイルを見つけます。

1. Commercial Suite の購入時に提供された XML ライセンス ファイルを参照して選びます。
    > [!NOTE]
    > [プロビジョニング パッケージでは追加の設定](hololens-provisioning.md)を構成できます。

1. **[ファイル]** メニューの **[保存]** をクリックします。 

1. プロジェクトファイルに機密情報が含まれている可能性があることを示す警告を確認し、[ **OK]** をクリックします。

    > [!IMPORTANT]
    > プロビジョニング パッケージをビルドするときに、プロジェクト ファイルとプロビジョニング パッケージ (.ppkg) ファイルに機密情報を含めることもできます。 .ppkg ファイルは暗号化するかどうかを選べますが、プロジェクト ファイルは暗号化されません。 プロジェクト ファイルは安全な場所に格納し、不要になったらプロジェクト ファイルを削除する必要があります。

1. **[エクスポート]** メニューの **[プロビジョニング パッケージ]** をクリックします。
1. [ **所有者]** **を [IT 管理者**] に変更します。これにより、このプロビジョニング パッケージの優先順位が、他のソースからこのデバイスに適用されるプロビジョニング パッケージよりも高く設定され、[次へ] を選択 **します**。
1. **[パッケージのバージョン]** の値を設定します。

    > [!TIP]
    > 既存のパッケージに変更を加えてバージョン番号を変更することで、以前に適用されたパッケージを更新することができます。

1. **[プロビジョニング パッケージのセキュリティ情報の選択]** で、**[次へ]** をクリックします。
1. **[次へ]** をクリックし、ビルドしたプロビジョニング パッケージの出力先を指定します。 既定では、Windows ICD はプロジェクト フォルダーを出力先として使います。

    必要に応じて、 [参照] をクリックして既定の出力先を変更できます。

1. **[次へ]** をクリックします。
1. パッケージのビルドを開始するには、**[ビルド]** をクリックします。 ビルド ページにプロジェクト情報が表示され、進行状況バーでビルドの状態が示されます。
1. ビルドが完了したら、**[完了]** をクリックします。

### <a name="apply-the-provisioning-package-to-hololens"></a>HoloLens へのプロビジョニング パッケージの適用

1. USB 経由でデバイスを PC に接続してデバイスを起動しますが、初期セットアップ エクスペリエンスの **調整** ページ (青のボックスが表示された最初のページ) より先には進まないでください。
1. **[音量を下げる]** ボタンと **電源** ボタンを同時に短く押して離します。
1. HoloLens が PC のエクスプローラーにデバイスとして表示されます。
1. エクスプローラーで、プロビジョニング パッケージ (.ppkg) をデバイス ストレージに ドラッグ アンド ドロップします。
1. **調整** ページが表示されている間に、もう一度 **[音量を下げる]** ボタンと **電源** ボタンを同時に短く押して離します。
1. パッケージを信頼して適用するかどうかを確認するメッセージがデバイスに表示されます。 パッケージが信頼できることを確認します。
1. パッケージが正常に適用されたかどうかが表示されます。 失敗した場合、パッケージを修正してもう一度試します。 成功した場合はデバイスのセットアップを続けます。

> [!NOTE]
> 2016 年 8 月より前に購入したデバイスの場合、プロビジョニング パッケージを適用するには、Microsoft アカウントを使ってデバイスにサインインして最新の OS 更新プログラムを入手し、OS をリセットする必要があります。

## <a name="verify-device-encryption"></a>デバイスの暗号化を確認する

暗号化は、HoloLens で自動的に行われます。 デバイスの暗号化の状態を確認するには

- HoloLens で、 [設定] [**システムの概要]**  >  **に移動**  >  **します**。 デバイスが暗号化 **されている場合** は **、BitLocker** が有効になります。 

    ![BitLocker が有効になっている画面について](images/about-encryption.png)
