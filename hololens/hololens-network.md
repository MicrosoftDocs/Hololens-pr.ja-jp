---
title: HoloLens をネットワークに接続する
description: HoloLens でインターネットに接続する方法と、デバイスの IP アドレスを識別する方法について説明します。
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, Wi-Fi, ワイヤレス, インターネット, IP, IP アドレス
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 0db64ffb4113ff948651c708c28b91da535cb09b
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009525"
---
# HoloLens をネットワークに接続する

HoloLens で何らかの操作を実行するには、ほとんどの場合、ネットワークに接続している必要があります。 このガイドは次の作業に役立ちます。

- Wi-Fi または (HoloLens 2 の場合のみ) Ethernet over USB-C を使用してネットワークに接続する
- Wi-Fi を有効または無効にする

[HoloLens のオフライン使用](hololens-offline.md)に関する詳細情報を参照してください。

## 初めての接続

HoloLens を初めて使うときは、Wi-Fi ネットワークに接続するためのガイドが表示されます。 セットアップ中に Wi-Fi に接続できない場合は、接続先がオープン ネットワーク、パスワードで保護されたネットワーク、またはキャプティブ ポータル ネットワークであることを確認してください。 また、そのネットワークへの接続時に証明書の使用が求められないことを確認してください。 セットアップの完了後は、他の種類の Wi-Fi ネットワークにも接続できます。

HoloLens 2 デバイスでは、[USB-C to Ethernet アダプターを使用](hololens-connect-devices.md#hololens-2-connect-usb-c-devices)して、直接 Wi-Fi に接続してデバイスのセットアップを支援する こともできます。 デバイスを設定した後は、アダプターを使い続けることもできますが、アダプターから切断して、[セットアップ後にデバイスを Wi-Fi に接続する](hololens-network.md#connecting-to-wi-fi-after-setup)こともできます。 

## セットアップ後の Wi-Fi 接続

1. **スタート ジェスチャ** を事前に準備し、**設定**を選択します。 設定アプリは、ユーザーの正面に自動配置されます。
1. **[ネットワークとインターネット]** > **[Wi-Fi]** の順に選択します。 Wi-Fi がオンになっていることを確認してください。 目的のネットワークが表示されない場合は、一覧を下方向へスクロールします。
1. ネットワークを選択し、**[接続]** を選択します。
1. ネットワーク パスワードを求めるメッセージが表示されたら、入力して **[次へ]** を選択します。

HoloLens には、802.11ac 対応の 2x2 Wi-Fi 無線が装備されています。 HoloLens から Wi-Fi ネットワークへの接続は、Windows 10 デスクトップまたはモバイル デバイスから Wi-Fi ネットワークへの接続と似ています。

![HoloLens の Wi-Fi 設定](./images/wifi-hololens-600px.jpg)

**スタート** メニューで Wi-Fi の状態を確認することにより、Wi-Fi ネットワークへの接続を確認することもできます。

1. **スタート** メニューを開きます。
1. **スタート** メニューの左上で Wi-Fi の状態を確認します。 Wi-Fi の状態と、接続されているネットワークの SSID が表示されます。

## Wi-Fi への接続のトラブルシューティング

Wi-Fi への接続で問題が発生した場合は、「[Wi-Fi に接続できない](./hololens-faq.md#i-cant-connect-to-wi-fi)」をご覧ください。

デバイスのエンタープライズ アカウントまたは組織アカウントにサインインするときに、ポリシーが IT 管理者によって構成されている場合、モバイル デバイス管理 (MDM) ポリシーも適用される場合があります。

## VPN
VPN 接続を使用すると、より安全な接続と会社のネットワークやインターネットへのアクセスを提供できます。 HoloLens 2 は、組み込み VPN クライアントおよびユニバーサル Windows プラットフォーム (UWP) VPN プラグインをサポートしています。 

サポートされている組み込み VPN プロトコル:
- IKEv2
- L2TP
- PPTP

組み込みのVPN クライアントの認証に証明書を使用している場合は、必要なクライアント証明書をユーザー証明書ストアに追加する必要があります。 サードパーティの VPN プラグインが HoloLens 2 をサポートしているかどうかを確認するには、[VPN アプリ] がある [ストア] に移動し、 ARM または ARM64 アーキテクチャ をサポートしているアプリの [システム要件ページ] に [HoloLens] が表示されているかどうかを確認します。 HoloLens は、サードパーティ VPN 用のユニバーサル Windows プラットフォームアプリケーションのみをサポートしています。

VPN は既定で有効になっていませんが、 **設定** アプリを開き、 **ネットワーク & インターネット -> VPN** に移動して、手動で有効にすることができます。 VPN は、[Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)経由で MDM によって管理され、  [Vpnv2-csp ポリシー](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)を使用して設定できます。
詳細については、[これらのガイド](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)を使用して[how to configure VPNを構成する方法](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn)を参照してください。  

## HoloLens (第 1 世代) での Wi-Fi の無効化

### HoloLens での設定アプリの使用

1. **スタート** メニューを開きます。
1. **[スタート]** か、**スタート** メニューの右側にある **[すべてのアプリ]** の一覧から、**設定**アプリを選択します。 **設定**アプリは、ユーザーの正面に自動配置されます。
1. **[ネットワークとインターネット]** を選択します。
1. [Wi-Fi] のスライダー スイッチを選択して、**[オフ]** の位置に移動します。 これにより、Wi-Fi 無線の RF コンポーネントがオフになり、HoloLens 上の Wi-Fi 機能がすべて無効になります。

    > [!WARNING]
    > Wi-Fi 無線が無効になっている場合、HoloLens は[空間](hololens-spaces.md)を自動的に読み込むことができません。

1. スライダー スイッチを **[オン]** の位置に移動して Wi-Fi 無線を有効にし、Microsoft HoloLens に Wi-Fi 機能を復元します。 選択した Wi-Fi 無線の状態 (**[オン]** または **[オフ]**) は、再起動しても維持されます。

## Wi-Fi ネットワーク上での HoloLens の IP アドレスの識別

### 設定アプリを使用する

1. **スタート** メニューを開きます。
1. **[スタート]** か、**スタート** メニューの右側にある **[すべてのアプリ]** の一覧から、**設定**アプリを選択します。 **設定**アプリは、ユーザーの正面に自動配置されます。
1. **[ネットワークとインターネット]** を選択します。
1. 使用可能な Wi-Fi ネットワークの下までスクロールし、**[ハードウェアのプロパティ]** を選択します。

    ![Wi-Fi 設定の [ハードウェア プロパティ]](./images/wifi-hololens-hwdetails.jpg)

   IP アドレスは **[IPv4 アドレス]** の横に表示されます。

### 音声コマンドを使用する

使用しているデバイスに応じて、組み込み音声コマンドや Cortana を使用して IP アドレスを表示することができます。 ビルドで[19041.1103](hololens-release-notes.md#windows-holographic-version-2004)の後に、"IP アドレスを教えて" と話します。 すると、それが表示されます。 以前のビルドまたは HoloLens (第１世代) では、「コルタナさん、IP アドレスを教えて」 と言います。 Cortana によって IP アドレスの表示と読み上げが行われます。

### Windows デバイス ポータルを使用する

1. PC の Web ブラウザーで[デバイス ポータル](/windows/mixed-reality/using-the-windows-device-portal.md#networking)を開きます。
1. **[ネットワーク]** セクションに移動します。  
   このセクションには、IP アドレスとその他のネットワーク情報が表示されます。 この方法を使用すると、開発用 PC の IP アドレスをコピーして貼り付けることができます。
