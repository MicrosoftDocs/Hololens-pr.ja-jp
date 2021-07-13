---
title: 新しい設定アプリの概要
description: 新しい設定アプリの詳細
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens、設定、アプリ ピッカー、ボリューム
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: bf1a2080c15346843b9ea9b2d0dc93154e185107
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "110398909"
---
# <a name="new-settings-app"></a>新しい設定アプリ

[Windows Holographic バージョン 21H1](hololens-release-notes.md#windows-holographic-version-21h1)では、設定アプリの新しいバージョンを導入しています。 新しい設定アプリには、サウンド、電源とスリープ、ネットワークとインターネット、アプリ、アカウント、コンピューターの簡単操作などの領域における HoloLens 2 の新機能と拡張設定が含まれています。

> [!NOTE]
> 新しい設定アプリは従来の設定アプリとは別であるため、以前に環境に配置した設定の windows は、更新時に削除されます。

![新しい設定アプリのホームページ](images/new-settings-app.png)

**新機能と設定**
- 設定の検索: キーワードまたは設定の名前を使用して、設定ホームページから設定を検索します。
- [設定] > [[色の調整]](hololens2-display.md#how-to-use-display-color-calibration)
    - HoloLens 2 表示の代替カラー プロファイルを選択します。
- [システム] > [サウンド]:
  - 入出力オーディオ デバイス: 入力と出力のオーディオ デバイスを個別に選択します (たとえば、Bluetooth ヘッドホンを使用してオーディオをリッスンするか、オーディオ入力に USB C マイクを使用します)。
    > [!NOTE]
    > Bluetooth のマイクは、HoloLens 2 ではサポートされていません。
  - アプリのボリューム: 各アプリのボリュームを個別に調整します。 [「アプリごとのボリューム制御」](holographic-home.md#per-app-volume-control)を参照してください。
- [システム] > [電源とスリープ]: 操作のない状態が一定期間続いた後にスリープに移行するときに選択します。
- [システム] > [バッテリ]: バッテリ節約モードを手動で有効にするか、バッテリ省モードが自動的にオンになるようにバッテリのしきい値を設定します。
- [デバイス] > [USB]: USB 接続を既定で無効にすることができます。
- ネットワークとインターネット:
  - USB-C イーサネット アダプタが、[ネットワークとインターネット] に表示されます。
  - USB-C イーサネットアダプターの設定が、IP アドレスを含めて使用できるようになりました。
  - HoloLens 2 で機内モードを有効にできるようになりました。
- アプリ: ファイルとリンクの種類に使用される既定のアプリをリセットできます。 詳細については、[「既定のアプリ ピッカー」](holographic-home.md#default-app-picker)を参照してください。
- [アカウント] > [他のユーザー]: デバイス所有者は、ユーザーを追加し、標準ユーザーをデバイス所有者にアップグレードし、デバイス所有者を標準ユーザーにダウングレードして、ユーザーを削除することができます。
- 簡単操作: テキストのサイズと視覚効果を変更します。

**既知の問題**
- 以前に配置した設定ウィンドウは削除されます (上のメモを参照)。
- 設定アプリでは、デバイスの名前を変更できなくなります。 IT 管理者は、[Windows Autopilot for HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) のデバイス名テンプレートまたは MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName ノードを使用してデバイスの名前を変更できます。
- イーサネットのページには、常に仮想イーサネットデバイス ("UsbNcm") が表示されます。
- 新しい Microsoft Edge のバッテリ使用量は、UWP アダプター レイヤーによってサポートされている Win32 デスクトップ アプリケーションの性質上、正確ではない可能性があります (近日対応予定の修正プログラムはありません)。

