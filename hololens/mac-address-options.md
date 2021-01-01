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
ms.openlocfilehash: 3e06540dd7dca8892cd69abaf9a318d46ca0f3f2
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253144"
---
# MAC アドレスが制限された Wi-Fi 環境での HoloLens デバイスのエンタープライズ登録

このドキュメントでは、Wi-Fi が MAC アドレスのために制限されている、またはワイヤレス ネットワークに参加するために証明書が必要な、お客様の環境内で特定された一般的なシナリオについて説明します。

## シナリオ例

セキュリティで保護された環境の多くのお客様は、ワイヤレス ネットワークまたはワイヤード (有線) ネットワークに制限があります。承認されたデバイス (MAC アドレスに基づく) のみが正常に接続できます (ワイヤレス アクセス ポイントまたは DHCP サーバーの MAC アドレス フィルターを使用)。 さらに、一部のワイヤレス ネットワークは PEAP で保護できます。PEAP では、ワイヤレス ネットワークを正常に認証する前に、デバイスに証明書を適用する必要があります。

HoloLens デバイスでは、2 つの重要な問題が発生する可能性があります。これにより、HoloLens デバイスをネットワークに参加させる際に遅延や手作業が発生する可能性があります。

- デバイスがワイヤレスネットワークに正常に参加する前に、ワイヤレス PEAP 証明書をデバイスに適用する必要があります。
- HoloLens Wi-fi アダプターの MAC アドレスが登録されている必要があります。

これに対する主な課題は次のとおりです。

1. 現在、MACアドレスは、デバイスの設定アプリから、またはIntuneの登録が成功した後に、Intuneから識別できます。
2. MACアドレスがないと、デバイスはWi-Fiネットワークに参加して登録を開始できません。
3. これらの課題を手動で解決するには、技術者がデバイスに関与する必要があります。

## 解決策

環境内で使用可能なインフラストラクチャに応じて、この状況を改善する方法は多数あります。

| 解決策 | メリット | 要件 |
| --- | --- | --- |
| イーサネット アダプターを使用したプロビジョニング パッケージ | OOBE エクスペリエンスを向上させ、より迅速な技術者エクスペリエンスを可能にします。 | HoloLens と互換性のある USB C HubTechnician は、MAC キャプチャと OOBE の最終処理のためにデバイスとやり取りする必要があります |
| イーサネット経由の Intune 登録による Autopilot | シングルステップ接続と顧客環境へのデバイスの登録 MACキ ャプチャは、デバイスとの通信なしで完了できます | 顧客 Azure AD TenantHoloLens 互換 USB-C ネットワーク アダプターに対して Intune が有効 |
| MAC アドレスの自動レポート | デバイスが Intune テナント内に登録されたら、技術者への MAC アドレスのレポートをスクリプト化します。 | Intune PowerShell Commandlets |

## イーサネット アダプターを使用したプロビジョニング パッケージ

> [!NOTE] 
> 有線ネットワークにも MAC 制限が適用される場合は、USB-C イーサネット アダプター/ハブの MAC アドレスを事前に承認する必要があります。 このハブには他のデバイスからネットワークにアクセスできるようになるため、注意が必要です。

### 要件

- カスタマー ネットワークにアクセスできる有線ネットワーク ポート
- イーサネット アダプターを含む HoloLens 互換の USB-C ハブ – 追加のドライバーやアプリケーションのインストールを必要としないハブが適しています。
- 以下を含むプロビジョニング パッケージ：
  - ワイヤレス ネットワーク情報と証明書が含まれている
  - オプションで、組織の &#39;s Azure AD の登録情報が含まれている
  - その他の必要なプロビジョニング設定が含まれている

### Process

このプロセスは、デバイスのソフトウェア レベルによって異なる場合があります。 デバイスに [2004 年 5 月](hololens-release-notes.md#windows-holographic-version-2004)の更新がある場合は、以下の手順に従います。

1. プロビジョニング パッケージを USB スティックのルートに配置し、ハブに接続します。
2. イーサネット ケーブルをハブに接続します。
3. USB-C ハブを HoloLens デバイスに接続します。
4. HoloLens デバイスの電源を入れ、デバイスを装着します。
5. **ボリューム ダウン ボタンと電源ボタン**を押して、プロビジョニング パッケージを適用します。
6. これで、技術者は OOBE をフォロー出来るようになったので、完了後、設定アプリを開いて、デバイスの MAC アドレスを取得できます。

デバイスに [2004 年 5 月の更新](hololens-release-notes.md#windows-holographic-version-2004)前の OS ビルドがある場合は、以下の手順に従ってください。

1. HoloLens デバイスの電源を入れ、デバイスを PC に接続します。
2. デバイスは、ファイル ストレージ デバイスとして PC に表示されます。
3. プロビジョニング パッケージをデバイスにコピーします
4. イーサネット ケーブルをハブに接続します。
5. USB-C ハブを HoloLens デバイスに接続します。
6. デバイスを装着します。
7. **ボリューム ダウン ボタンと電源**ボタンを押して、プロビジョニング パッケージを適用します。
8. これで、技術者は OOBE をフォロー出来るようになったので、完了後、設定アプリを開いて、デバイスの MAC アドレスを取得できます。

### メリット

これにより、デバイスの&quot;シングル タッチ&quot;で正しいプロビジョニング パッケージを適用し、デバイスの MAC アドレスを収集できます。 [プロビジョニングパッケージは、こちらのガイダンスに従って作成できます。](https://docs.microsoft.com/hololens/hololens-provisioning)

## Intune の登録を使用した Autopilot

### 要件

- カスタマー ネットワークにアクセスできる有線ネットワーク ポート
- Windows Holographic 2004 を実行している HoloLens デバイス
- HoloLens Compatible USB-C Hub
- Intuneがセットアップされ、顧客のテナントに対して有効です
- Autopilot に登録され、顧客のテナントにインポートされたデバイス
- デバイスに定義されている Intune ポリシー
   - ワイヤレス ネットワーク情報と証明書が含まれている
   - その他の必要なプロビジョニング設定が含まれている

これにより、高度なネットワーク要件を持つお客様は、ハンズオフでスケーラブルなアプローチでデバイスを登録できます。

必要な追加の前提条件は、次の通りです。
1. [Autopilot プレビューのテナントを有効にする](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. HoloLens ポリシーを作成して、Intune 内のプロビジョニング パッケージを置き換えます。
1. HoloLens Intune ポリシーを作成します。
1. デバイスを正しいグループに割り当てます。

### Process

1. USB-C ハブとイーサネット ケーブルを HoloLens 2 デバイスに接続します。
2. HoloLens 2 を有効にします。
3. デバイスは、イーサネットアダプターを介して OOBE でインターネットに自動的に接続し、自動操縦構成を検出し、AzureAD と Intune に自動的に登録する必要があります
4. デバイスは、必要に応じて Intune を介して必要な Wi-Fi 証明書とその他の構成を適用します
5. 完了すると、技術者は Intune (エンドポイント マネージャー) ポータルをロードし、**[ホーム]-> [デバイス] -> [デバイス名] -> [ハードウェア]** にある デバイス プロパティ ページを表示できるようになります。
6. Wi-Fi MAC アドレスが Intune Portal 内に表示されます

![Intune 経由の MAC アドレス](images/mac-address-intune.jpg)

7. 技術者は、この MAC アドレスを許可されたデバイスとして追加します。

### メリット

これにより、技術者がデバイスを装着したり、HoloLens 環境を手動で操作したりすることなく、デバイスをボックスから Azure AD および Intune に登録できる、技術者の&quot;ヘッドオフ&quot;展開エクスペリエンスが可能になります。

## 技術者への MAC アドレスの報告

### 要件

- 顧客テナントに対する &quot;Intune Graph PowerShell&quot; の承認
- 技術者のコンピューターへの Intune Graph PowerShell のインストール。
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Intune の &quot;管理対象デバイス&quot; 要素への読み取りアクセス。 (ヘルプデスクオペレーター以上、またはカスタムロール)

現時点では、Intune内の新しいデバイスの登録に基づいて自動化コマンドをトリガーする&quot;簡単な&quot;方法はありません。 したがって、このコマンドは、ポータルにログオンして手動で取得する必要なしに、技術者に MAC アドレスを取得する簡単な方法を提供します。

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

これにより、過去30日間に登録された HoloLens デバイスの名前と MAC アドレスが返されます。

![Powershell 経由の MAC アドレス](images/mac-address-powershell.jpg)

### Process

Intune の登録が完了すると、技術者は上記のスクリプトを実行して MAC アドレスを取得します。
