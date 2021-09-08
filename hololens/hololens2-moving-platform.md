---
title: HoloLens 2 の移動プラットフォーム モード
description: 移動プラットフォームで HoloLens を使用する方法
keywords: 動くプラットフォーム, ダイナミック モーション, hololens, 移動プラットフォーム モード
author: evmill
ms.author: v-evmill
ms.reviewer: yabahman
ms.date: 8/10/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: high
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: a0717524cd1f762c92a5b821ae90acb8474dafd2
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190397"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>低ダイナミック モーション移動プラットフォームでの移動プラットフォーム モード

**Insider ビルド 20348.1411** において、HoloLens 2 上の低ダイナミック モーション移動プラットフォームでの追跡用にベータ サポートを追加しました。 ビルドをインストールし、移動プラットフォーム モードを有効にすると、大型の船や海洋船舶など、以前にアクセスできなかった環境で HoloLens 2 を使用できるようになります。 現在、この機能は、これらの特定の移動プラットフォームを有効にすることのみを目的としています。 この機能を他の環境で使用してはいけないことはありませんが、この機能はそもそもこういった環境にサポートを追加することに重点を置いています。

> [!NOTE]
> 現在、この機能は [Windows Insider](hololens-insider.md) でのみ利用できます。

![移動プラットフォームの例。](./images/mpm-compare.gif)

この記事には、次の内容が含まれます。

1. [移動プラットフォームが必要な理由](#why-moving-platform-mode-is-necessary)
1. [移動プラットフォーム モードを有効にする](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>移動プラットフォーム モードが必要な理由

HoloLens は、安定したホログラムを表示するために、[自由度 6](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) (X、Y、Z 方向の平行移動、ロール、ピッチ、ヨーの回転) で頭の位置を追跡できる必要があります。 これを行うために、HoloLens により、次の 2 つの別々のソースから 2 つの類似した情報が追跡されます。

1. 可視光カメラ: 環境を追跡します。たとえば、HoloLens を使用している物理的な部屋など
1. 慣性測定装置 (IMU) – 地球を基準として頭の動きと向きを追跡する、加速度計、ジャイロスコープ、および磁力計で構成されます。

これら 2 つのソースからの情報が複雑に組み合わされて、スムーズなホログラムをレンダリングするために、低待機時間かつ十分に高い頻度でヘッド位置が追跡されます。

ただし、この方法は、重要な仮定に依存します。つまり、(カメラによって追跡される) 環境は、(IMU による測定の基準となる) 地球 (地面) を基準に固定されているということです。 そうでない場合 (水に浮かぶボート上など)、両方のソースからの情報が競合し、トラッカーが追跡できなくなる可能性があります。 この競合によって、不正確な位置情報が生成され、目まいがするようなホログラムになったり、さらには追跡が失われたりします。

この問題は、移動プラットフォーム モードにより解決します。 移動プラットフォーム モードを有効にした場合、これは、互いに完全に合致するために自身のセンサー入力に依存できない、というヒントをトラッカーに与えることになります。 IMU 入力を使用する前に、視覚追跡にもっと依存し、つじつまの合わない慣性モーション データを迅速に特定して、必要に応じてそれを除外する必要があります。

## <a name="supported-environments-and-known-limitations"></a>サポートされている環境と既知の制限事項

移動プラットフォーム モードは、慣性と視覚的なデータの競合をインテリジェントに処理するために開発されましたが、その範囲は現在、低ダイナミック モーションが発生する大型の海洋船舶にまで及んでいます。 つまり、制限事項があり、サポートされていないシナリオもあります。

### <a name="known-limitations"></a>既知の制限事項

- 移動プラットフォーム モード (MPM) の唯一サポートされている環境は、低ダイナミック モーションを経験する大型の船舶です。 つまり、多くの一般的な環境や状況は、頻度の高いモーションや高レベルのアクセラレーションと [ジャーク](https://en.wikipedia.org/wiki/Jerk_(physics))が原因で、まだ **サポートされていません**。 たとえば、飛行機、電車、自動車、バイク、バス、小型船、エレベーターなどです。
- MPM を有効にした場合、特に波立った水面では、ホログラムは若干ぐらつく可能性があります。
- MPM をサポートされていない環境で使用してはいけないことはありませんが、サポートされていない空間でデバイスにより追跡を維持できる場合、望ましくない副作用が発生する可能性があります。 たとえば、MPM は、以前は不可能だった、フロア間を行き来するエレベーターで使用できるかもしれません。 ただし、MPM ではデバイスにより追跡を維持できるものの、現時点ではマップ管理は処理されません。 エレベーターでの階の変更により、デバイスが上の階と下の階がわからなくなり、マップの質に悪影響が及びます。

## <a name="prerequisites"></a>前提条件

移動プラットフォーム モードのベータ サポートの前提条件は、数えるほどしかありません。

1. [ARC 経由で最新の Insider ビルドをフラッシュ](hololens-insider.md#ffu-download-and-flash-directions)するか、[デバイスの登録と更新](hololens-insider.md#start-receiving-insider-builds)を行って、ビルド 20348.1411 以降をインストールします。

   > [!NOTE]
   > 現在、このビルドは [Insider Dev チャネル](hololens-insider.md#start-receiving-insider-builds)でのみ入手できます。

2. [開発者モードとデバイス ポータル](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)を有効にします。

## <a name="enabling-moving-platform-mode"></a>移動プラットフォーム モードを有効にする

移動プラットフォーム モードを有効にするには、まず[デバイス ポータルを有効にします](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。

1. 左側のメニューで、 **[システム]** アコーディオンを選択します。

   ![最初の画像。](.\images\moving-platform-1w.png)

2. **[Moving Platform Mode]\(移動プラットフォーム モード\)** ページを選択し、 **[Moving Platform Mode]\(移動プラットフォーム モード\)** チェックボックスをオンにします。

    ![2 番目の画像。](.\images\moving-platform-2z.png)

3. 警告が表示されたら、 **[OK]** を選択します。

   ![3 番目の画像。](.\images\moving-platform-3w.png)

4. デバイスを再起動します。この操作は、右上のデバイスポータルの **[電源]** メニューから、または音声コマンド「&quot;デバイスを再起動&quot;」を使用し、&quot;[はい]&quot; を選択して行えます。

   ![4 番目の画像。](.\images\moving-platform-4z.png)

デバイス ポータルで [Moving Platform Mode]\(移動プラットフォーム モード\) オプションが表示されない場合は、まだ適切なビルドを使用していない可能性があります。 「[前提条件](#prerequisites)」をご覧ください。

## <a name="reporting-issues"></a>問題の報告

前述のように、この機能は、開発者モードでのみ使用できるベータ機能です。そのため、問題が発生する可能性があります。 そのような場合は、Microsoft が製品を調査して改善できます。以下を行ってください。

1. **Hologram の精度、安定性、信頼性** のカテゴリで [フィードバック Hub](hololens-feedback.md) を使用して問題を報告し、その際、以下を含めます。
    1. 期待される動作と経験した動作を含む、問題の説明
    1. 問題の Mixed Reality の[ビデオ録画](holographic-photos-and-videos.md#capture-a-mixed-reality-video)
2.  Microsoft がフォローアップの質問がある場合にアクセスできるように、[https://aka.ms/hlsupport](https://aka.ms/hlsupport) でサポート ケースを開き、フィードバック Hub の URL を共有します。