---
title: HoloLens 2 の実装とマネージド デバイスのトラブルシューティング
description: エンタープライズ環境における HoloLens 2 デバイスのトラブルシューティング
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: トラブルシューティング
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: f038cbf58b6dfaef0395a1ea5b406cce23e4e3fe0464c6bfc1162518f9caf3ff
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115659770"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a>実装とマネージド デバイスのトラブルシューティング 

この記事では、HoloLens 2 の実装と管理について問題を解決する方法、または質問に回答する方法について説明します。

>[!IMPORTANT]
> トラブルシューティングの手順を開始する前に、可能であれば、デバイスのバッテリ容量が **20 - 40%** 残っていることを確認してください。 電源 ボタンの下 にある[バッテリ インジケーター ライト](hololens2-setup.md#lights-that-indicate-the-battery-level)により、デバイスにログインせずにバッテリ容量を簡単に確認できます。


<a id="list"></a>
- [EAP のトラブルシューティング](#eap-troubleshooting)
- [Wi-Fi のトラブルシューティング](#wi-fi-troubleshooting)
- [ネットワークのトラブルシューティング](#network-troubleshooting)
- [以前にセットアップした HoloLens デバイスにサインインできない](#cant-sign-in-to-a-previously-setup-hololens-device)
- [Windows Holographic 21H1 への更新後ログインできない](#cant-login-after-updating-to-windows-holographic-21h1)
- [Autopilot のトラブルシューティング](#autopilot-troubleshooting)
- [マネージド HoloLens デバイスに関する FAQ](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>EAP のトラブルシューティング
1. Wi-Fi プロファイルが正しく設定されているかどうかを再確認します。
    - EAP の種類が正しく構成されているか。一般的な EAP の種類は、EAP-TLS (13)、EAP-TTLS (21)、および PEAP (25) です。
    - Wi-Fi SSID 名は正しく、HEX 文字列と一致しているか。
    - EAP-TLS の場合、TrustedRootCA に、サーバーの信頼されたルート CA 証明書の SHA-1 ハッシュが含まれるかどうか。 Windows PC 上では、"certutil.exe -dump cert_file_name" コマンドを実行すると、証明書の SHA-1 ハッシュ文字列が表示されます。
2. アクセス ポイントまたはコントローラーまたは AAA サーバー ログでネットワーク パケット キャプチャを収集して、EAP セッションが失敗した場所を確認します。
    - HoloLens によって提供される EAP ID が想定されていない場合は、Wi-Fi プロファイルまたはクライアント証明書を通じて、ID が正しくプロビジョニングされているかどうかを確認します。
    - サーバーが HoloLens クライアント証明書を拒否した場合は、必要なクライアント証明書がデバイスでプロビジョニングされているかどうかを確認します。
    - HoloLens がサーバー証明書を拒否した場合は、サーバー ルート CA 証明書が HoloLens でプロビジョニングされているかどうかを確認します。
3. エンタープライズ プロファイルが Wi-Fi プロビジョニング パッケージによってプロビジョニングされている場合は、Windows 10 PC にプロビジョニング パッケージを適用することを検討してください。 Windows 10 PC でも失敗する場合は、Windows クライアントの 802.1X 認証ガイドに従ってください。
4. フィードバック Hub からフィードバックを送信してください。

[一覧に戻る](#list)

## <a name="wi-fi-troubleshooting"></a>Wi-Fi のトラブルシューティング

HoloLens を Wi-Fi ネットワークに接続できない場合は、以下を試してください。

1. Wi-Fi がオンになっていることを確認してください。 確認するには、スタート ジェスチャを使用して、[設定] > [ネットワークとインターネット] > [Wi-Fi] を選択します。 Wi-Fi がオンである場合は、オフにしてから、もう一度オンにしてみてください。
2. ルーターまたはアクセス ポイントに PC を近づけます。
3. Wi-Fi ルーターを再起動し、その後で、HoloLens を再起動します。 接続を再試行してください。
4. これらのいずれも機能しない場合は、ルーターのファームウェアが最新であるか確認します。 この情報は、製造元の Web サイトで見つけることができます。

デバイスのエンタープライズ アカウントまたは組織アカウントにサインインするときに、ポリシーが IT 管理者によって構成されている場合、モバイル デバイス管理 (MDM) ポリシーも適用される場合があります。

[一覧に戻る](#list)

## <a name="network-troubleshooting"></a>ネットワークのトラブルシューティング
HoloLens 2 を正常に展開および使用する上で、ネットワークの問題が障害となっている場合、Fiddler、Wireshark、またはその両方を構成して HTTP と HTTPS のトラフィックをキャプチャし、分析します。 

### <a name="configure-fiddler-to-capture-http-traffic"></a>HTTP トラフィックをキャプチャするように Fiddler を構成する
Fiddler は Web デバッグ プロキシであり、HTTP(S) の問題のトラブルシューティングに使用されます。 コンピューターによるすべての HTTP 要求がキャプチャされ、それに関連付けられているすべてが記録されます。 HTTPS アプリのエンドユーザー認証の問題が明らかになると、対象となる HoloLens 2 のユース ケースの生産性と効率性が向上します。 

#### <a name="prerequisites"></a>[前提条件]
 
- HoloLens 2 デバイスとお使いの PC が同じネットワーク上にある必要があります
- PC の IP アドレスをメモしておきます

#### <a name="install-and-configure-fiddler"></a>Fiddler をインストールして構成する

1. PC 上: Fiddler を[インストール](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure)して起動します。  
1. PC 上: リモート コンピューターの接続を許可するように Fiddler を構成します。
    1. Fiddler の [Settings]\(設定\) -> [Connections]\(接続\) に移動します
    1. Fiddler のリッスン ポートをメモします (既定値は 8866 です)
    1. [Allow remote computers to connect]\(リモート コンピューターの接続を許可する\) をオンにします
    1. [保存] をクリックします。
3. HoloLens 2 上 - Fiddler をプロキシ サーバー<sup>1</sup> として構成します。
    1. スタート メニューを開き、[設定] を選択します
    1. [ネットワークとインターネット] を選択して左のメニューでプロキシを選択します
    1. [手動プロキシの設定] まで下にスクロールし、[プロキシ サーバーの使用] を [オン] に切り替えます
    1. Fiddler がインストールされている PC の IP アドレスを入力します
    1. 前述のポート番号を入力します (既定値は 8866 です)
    1. [保存] をクリックします。

<sup>1</sup> ビルド 20279.1006 以降 (Insider と今後のリリース) の場合は、次の手順でプロキシを構成します。
1. スタート メニューを開き、お使いの Wi-Fi ネットワークの [プロパティ] ページにアクセスします。 
1. プロキシまで下方向へスクロールします。
1. 手動セットアップに変更
1. Fiddler がインストールされている PC の IP アドレスを入力します
1. 前述のポート番号を入力します (既定値は 8866 です)。
1. [適用] をクリックします
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a>HoloLens 2 からの HTTPS トラフィックの暗号化を解除する

1. PC 上 - Fiddler の証明書をエクスポートします。
    1. Fiddler の [Settings]\(設定\) -> [HTTPS] に移動し、[Advanced Settings]\(詳細設定\) を展開します
    2. [Export Fiddler certificate]\(Fiddler の証明書のエクスポート\) をクリックします。 デスクトップに保存されます
    3. その証明書を HoloLens 2 の Downloads フォルダーに移動します。

2.  HoloLens 2 上 - Fiddler の証明書をインポートします。
    1. [設定] -> [更新とセキュリティ] -> [証明書] に移動します
    2. [証明書のインストール] をクリックし、Downloads フォルダーを参照して Fiddler の証明書を選択します
    3. [保存場所] を [ローカル コンピューター] に変更します
    4. [証明書ストア] を [ルート] に変更します
    5. [インストール] を選択します
    6. 証明書の一覧に証明書が表示されることを確認します。 ない場合は、上記の手順を繰り返します

#### <a name="inspect-https-sessions"></a>HTTP(S) セッションを検査する

PC 上で Fiddler を使用すると、HoloLens 2 のライブ HTTP(S) セッションが表示されます。 Fiddler の [Inspectors]\(インスペクター\) パネルには、HTTP(S) の要求と応答をさまざまなビューで表示できます。たとえば、[Raw]\(未加工\) ビューには、未加工の要求または応答がプレーン テキストで表示されます。 

### <a name="configure-wireshark-to-capture-network-traffic"></a>ネットワーク トラフィックをキャプチャするように Wireshark を構成する
Wireshark はネットワーク プロトコル アナライザーであり、HoloLens 2 デバイスとの間の TCP および UDP トラフィックを検査するために使用されます。 これを使用すると、どのようなトラフィックがネットワークを経由して HoloLens 2 に到達しているか、その量、頻度、特定のホップ間の待機時間の長さなどを簡単に特定できるようになります。

#### <a name="prerequisites"></a>前提条件:
- PC はインターネットにアクセスでき、Wi-Fi 経由のインターネット共有をサポートしている必要があります

#### <a name="install-and-configure-wireshark"></a>Wireshark のインストールと構成
1. PC 上 - [Wireshark](https://www.wireshark.org/#download) をインストールします 
1. PC 上 - [モバイル ホットスポット] で Wi-Fi からのインターネット接続を共有できるようにします。
1. PC 上 - Wireshark を起動し、モバイル ホットスポット インターフェイスからのトラフィックをキャプチャします。 
1. HoloLens 2 上 - その Wi-Fi ネットワークを PC のモバイル ホットスポットに変更します。 HoloLens 2 の IP トラフィックが Wireshark に表示されます。

#### <a name="analyze-wireshark-logs"></a>Wireshark ログを分析する
Wireshark のフィルターは、対象のパケットを絞り込むのに役立ちます。 

元の[ブログ](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458)を参照してください。

[一覧に戻る](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>以前にセットアップした HoloLens デバイスにサインインできない

クライアントや元従業員用など、デバイスが誰か他の人に設定されていており、デバイスのロックを解除するためのパスワードを持ってない場合は、Intune を使用してデバイスをリモートで[ワイプ](/intune/remote-actions/devices-wipe)できます。 その後、デバイス自体が再フラッシュされます。  
> [!IMPORTANT]
> デバイスをワイプする場合は、**登録状態を保持 し、ユーザー アカウント** をオフのままにします。

[一覧に戻る](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>Windows Holographic 21H1 への更新後ログインできない

### <a name="symptoms"></a>現象
- 正しい PIN を入力した後、ログオンに PIN を使用すると失敗します。
- Web ページで正常にサインインした後、Web ログオン方法を使用すると失敗します。
- デバイスは[[Azure portal]](https://portal.azure.com/) -> [Azure Active Directory] -> で [Azure AD joined] として一覧表示されていません。

### <a name="cause"></a>原因
影響を受けたデバイスが、Azure AD テナントから削除された可能性があります。 たとえば、これは次の理由で発生する可能性があります。

- 管理者またはユーザーが Azure portal で、または PowerShell を使用してデバイスを削除した。
- 非アクティブであるため、デバイスが Azure AD テナントから削除された。 効率的に管理される環境の場合、通常、IT 管理者は、[古い非アクティブなデバイスを Azure AD テナントから削除することをお勧めします](/azure/active-directory/devices/manage-stale-devices)。

影響を受けたデバイスが、削除された後に Azure AD テナントに再度接続しようとすると、Azure AD を使用した認証に失敗します。 PIN によるキャッシュされたログオンでは引き続きユーザーのログオンが許可されるので、この効果は多くの場合、デバイスのユーザーには表示されません。

### <a name="mitigation"></a>対応策
現在、削除された HoloLens デバイスを Azure AD に戻す方法はありません。 影響を受けるデバイスは、[デバイス の再フラッシュ](hololens-recovery.md#clean-reflash-the-device)に関する手順に従って 、クリーンな再フラッシュを行う必要があります。

[一覧に戻る](#list)

## <a name="autopilot-troubleshooting"></a>Autopilot のトラブルシューティング

以下の記事は、Autopilot に関する問題の詳細情報を参照してトラブルシューティングを行う場合に役立つリソースです。ただし、これらの記事は、Windows 10 のデスクトップ版を使用しており、HoloLens には適用されない情報もあることにご注意ください。

- [Windows Autopilot - 既知の問題](/mem/autopilot/known-issues)
- [Microsoft Intune での Windows デバイスの登録に関する問題のトラブルシューティング](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - ポリシーの競合](/mem/autopilot/policy-conflicts)

[一覧に戻る](#list)

## <a name="managed-hololens-devices-faqs"></a>マネージド HoloLens デバイスに関する FAQ

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>System Center Configuration Manager (SCCM) を使用して HoloLens デバイスを管理できますか?

いいえ。 MDM システムを使用して、HoloLens デバイスを管理しなければなりません。

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>HoloLens ユーザー アカウントの管理に Active Directory Domain Services (AD DS) を使用できますか?

いいえ。 HoloLens デバイスのユーザー アカウントを管理するために Azure Active Directory (Azure AD) を使用する必要があります。

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>HoloLens は、Automated Data Capture Systems (ADCS) の自動登録は可能ですか?

いいえ。

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>HoloLens は統合 Windows 認証に参加できますか?

いいえ。

### <a name="does-hololens-support-branding"></a>HoloLens はブランディングをサポートしていますか?

いいえ。 ただし、この件は、次のいずれかの方法を使用して回避できます。

- カスタム アプリを作成し、キオスク [Kiosk モード を有効にします](hololens-kiosk.md)。 カスタム アプリにはブランドを設定し、他のアプリ (Remote Assist など) を起動できます。  
- Azure AD 内のユーザー プロファイルのすべての画像を会社のロゴに変更します。 ただし、これはすべてのシナリオで望ましいとは言えません。

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>HoloLens 2 にはどのようなログ機能がありますか?

ログ記録は、開発またはトラブルシューティングのシナリオでキャプチャできるトレース、またはデバイスが Microsoft サーバーに送信するテレメトリに限定されます。

## <a name="questions-about-securing-hololens-devices"></a>HoloLens デバイスのセキュリティ保護に関する質問

[当社のHoloLens 2 セキュリティに関する情報](security-overview.md)を確認してください。
HoloLens の第 1 世代については、[この FAQ ](hololens1-faq-security.yml)を参照してください。

[一覧に戻る](#list)
