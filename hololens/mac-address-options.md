---
title: MAC アドレスが制限された Wi-Fi 環境での HoloLens デバイスのエンタープライズ登録
description: HoloLens 2 デバイスでネットワークの MAC アドレスを設定する方法
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d21a63aae94f5ea5269f61fe319a9036626de1b4
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034431"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>MAC アドレスが制限された Wi-Fi 環境での HoloLens デバイスのエンタープライズ登録

このドキュメントでは、Wi-Fi が MAC アドレスのために制限されている、またはワイヤレス ネットワークに参加するために証明書が必要であるお客様の環境内で確認された一般的なシナリオについて説明します。

## <a name="example-scenario"></a>シナリオ例

セキュリティで保護された環境では、多くの場合、ワイヤレスまたは有線のネットワークに制限が設定されており、接続が許可されるのは (MAC アドレスに基づき) 承認されたデバイスのみとなっています。 このような制限は、ワイヤレス アクセス ポイント上の MAC アドレス フィルターまたは DHCP サーバーを介して適用されます。 また、一部のワイヤレス ネットワークは PEAP を用いて保護することもできます。この方式では、ワイヤレス ネットワークで認証する前にデバイスに証明書を適用する必要があります。

このシナリオでは、以下の 2 つの主要な要件が原因となり、HoloLens デバイスをネットワークに参加させる際に遅延が発生したり、手動による介入が必要になったりする場合があります。

- デバイスをワイヤレス ネットワークに正常に参加させるには、その前にワイヤレス PEAP 証明書をデバイスに適用する必要がある。
- HoloLens Wi-Fi アダプターの MAC アドレスは登録済みである必要がある。

上記の要件に関する主な課題は次のとおりです。

1. 現在、MAC アドレスは、デバイスの設定アプリから、または登録の完了後に Intune からのみ確認できます。

2. MAC アドレスがない場合、デバイスは Wi-Fi ネットワークに参加して登録手続きを開始できません。

3. これらの課題を手動で回避するには、技術者がデバイスを操作する必要があります。

## <a name="solutions"></a>ソリューション

環境内で使用可能なインフラストラクチャに応じて、この状況を改善する方法は多数あります。

| 解決策 | メリット | 必要条件 |
| --- | --- | --- |
| イーサネット アダプターを使用したプロビジョニング パッケージ | OOBE エクスペリエンスを向上させ、より迅速な技術者エクスペリエンスを可能にします。 | HoloLens 互換の USB-C ハブ + イーサネット アダプター。技術者は、MAC キャプチャと OOBE の終了処理のためにデバイスを操作する必要があります |
| イーサネット経由の Intune 登録による Autopilot | この解決策では、1 回の手順でデバイスを顧客環境に接続および登録できます。 MAC のキャプチャは、デバイスを操作することなく完了できます | 顧客の AAD テナントに対して有効になっている Intune および HoloLens 互換の USB-C イーサネット アダプター。 |
| MAC アドレスの自動レポート | デバイスが Intune テナントに登録されている場合、スクリプトを使用して MAC アドレスを技術者に報告することができます。 | Intune PowerShell コマンドレット |

## <a name="provisioning-package-with-ethernet-adaptor"></a>イーサネット アダプターを使用したプロビジョニング パッケージ

> [!NOTE] 
> 有線ネットワークに対しても MAC 制限が適用されている場合は、USB-C ハブ + イーサネット アダプターの MAC アドレスも事前承認を受ける必要があります。 このアダプターを介して他のデバイスがネットワークにアクセスできるようになるため、このアダプターを使用する場合は注意が必要です。

### <a name="requirements"></a>必要条件

- カスタマー ネットワークにアクセスできる有線ネットワーク ポート
- HoloLens 互換のイーサネット アダプター付き USB-C ハブ。追加のドライバーやアプリケーションのインストールを必要としないアダプターが適しています。
- 以下を含むプロビジョニング パッケージ:
  - ワイヤレス ネットワーク情報と証明書が含まれている
  - オプションで、組織の Azure AD の登録情報が含まれている
  - その他の必要なプロビジョニング設定が含まれている

### <a name="process"></a>Process

このプロセスは、デバイスのソフトウェア レベルによって異なる場合があります。 このデバイスに [2004 年 5 月の更新プログラム](hololens-release-notes.md#windows-holographic-version-2004)がインストールされている場合は、次の手順を実行します。

1. プロビジョニング パッケージを USB スティックのルートに配置し、ハブに接続します。
2. イーサネット ケーブルをハブ + イーサネット アダプターに接続します。
3. USB-C ハブを HoloLens デバイスに接続します。
4. HoloLens をオンにし、デバイスを装着します。
5. **[音量を下げる] と [電源] ボタン** を押して、プロビジョニング パッケージを適用します。
6. これで、技術者は OOBE の手順を実行できるようになりました。手順を完了したら、設定アプリを開いてデバイスの MAC アドレスを取得できます。

デバイスの OS ビルドが [2004 年 5 月の更新プログラム](hololens-release-notes.md#windows-holographic-version-2004)より前の場合は、次の手順を実行します。

1. HoloLens をオンにし、デバイスを PC に接続します。
2. デバイスは、ファイル ストレージ デバイスとして PC に表示されます。
3. プロビジョニング パッケージをデバイスにコピーします
4. イーサネット ケーブルをハブに接続します。
5. USB-C ハブを HoloLens デバイスに接続します。
6. HoloLens を装着します。
7. **[音量を下げる] と [電源] ボタン** を押して、プロビジョニング パッケージを適用します。
8. これで、技術者は OOBE の手順を実行できるようになりました。手順を完了したら、設定アプリを開いてデバイスの MAC アドレスを取得できます。

### <a name="benefits"></a>メリット

これで、デバイスを "1 回タッチ" して正しいプロビジョニング パッケージを適用し、デバイスの MAC アドレスを収集できるようになります。 [プロビジョニング パッケージは、こちらのガイダンスに従って作成できます。](hololens-provisioning.md)

## <a name="autopilot-with-intune-enrollment"></a>Intune の登録を使用した Autopilot

### <a name="requirements"></a>必要条件

- カスタマー ネットワークにアクセスできる有線ネットワーク ポート
- Windows Holographic 2004 を実行している HoloLens デバイス
- HoloLens 互換の USB-C イーサネット アダプター
- 顧客のテナントに対して構成および有効に設定されている Intune。
- Autopilot に登録され、顧客のテナントにインポートされたデバイス
- デバイスに定義されている Intune ポリシー
   - ワイヤレス ネットワーク情報と証明書が含まれている
   - その他の必要なプロビジョニング設定が含まれている

これで、高度なネットワーク要件を持つお客様でも、操作不要のスケーラブルなアプローチでデバイスを登録できるようになります。

必要な追加の前提条件は、次の通りです。
1. [Autopilot プレビューのテナントを有効にします](hololens2-autopilot.md)。
1. HoloLens ポリシーを作成して、Intune 内のプロビジョニング パッケージを置き換えます。
1. HoloLens Intune ポリシーを作成します。
1. デバイスを正しいグループに割り当てます。

### <a name="process"></a>Process

1. イーサネット ケーブルをアダプターに接続し、アダプターを HoloLens 2 デバイスの USB-C ポートに接続します。

2. HoloLens 2 の電源を入れます。

3. OOBE 中、デバイスがイーサネット アダプターを介してインターネットに自動的に接続されます。 Autopilot の構成が検出され、Azure AD および Intune に自動的に登録されます。

4. デバイスにより、必要な Wi-Fi 証明書が適用され、必要に応じて Intune 経由でその他の構成が行われます。

5. 完了すると、技術者は Intune (エンドポイント マネージャー) ポータルを読み込み、 **[ホーム] -> [デバイス] -> [<デバイス名>] -> [ハードウェア]** の順に移動し、デバイス プロパティ ページを表示することができます。

6. Wi-Fi MAC アドレスが Intune ポータル内に表示されます。

   ![Intune 経由の MAC アドレス。](images/mac-address-intune.jpg)

7. 技術者は、この MAC アドレスを許可されたデバイスとして追加します。

### <a name="benefits"></a>メリット

これで、技術者にとって "ヘッド オフ" 展開エクスペリエンスが可能になり、技術者は、デバイスを装着したり、HoloLens 環境を手動で操作したりすることなく、デバイスを箱から取り出して Azure AD や Intune に登録することができます。

## <a name="reporting-of-mac-addresses-to-the-technician"></a>技術者への MAC アドレスの報告

### <a name="requirements"></a>必要条件

- 顧客テナントに対する "Intune Graph PowerShell" の承認
- 技術者のコンピューターへの Intune Graph PowerShell のインストール。
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Intune の "マネージド デバイス" 要素への読み取りアクセス (ヘルプ デスク オペレーター以上、またはカスタム ロール)。

現時点では、Intune 内の新しいデバイスの登録に基づいて自動化コマンドをトリガーする "簡単な" 方法はありません。 そのため、技術者がこのコマンドを使用すると、ポータルにログオンして手動で取得することなく、MAC アドレスを簡単に取得できます。

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

これにより、過去 30 日間に登録された HoloLens デバイスの名前と MAC アドレスが返されます。

![PowerShell 経由の MAC アドレス。](images/mac-address-powershell.jpg)

### <a name="process"></a>Process

Intune の登録が完了すると、技術者は上記のスクリプトを実行して MAC アドレスを取得します。
