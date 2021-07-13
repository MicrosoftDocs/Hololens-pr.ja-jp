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
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961501"
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

## <a name="network-troubleshooting"></a>ネットワークのトラブルシューティング
ネットワークの問題が組織内で HoloLens 2 を正常にデプロイして使用するための障害である場合は、Fiddler と Wireshark という 2 つのよく知られたネットワーク診断ツールが、問題のスキャン、診断、および特定にどのように役立つのか確認してください。 詳細については、 [このブログ](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) を参照してください。

[一覧に戻る](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>以前にセットアップした HoloLens デバイスにサインインできない

クライアントや元従業員用など、デバイスが誰か他の人に設定されていており、デバイスのロックを解除するためのパスワードを持ってない場合は、Intune を使用してデバイスをリモートで[ワイプ](https://docs.microsoft.com/intune/remote-actions/devices-wipe)できます。 その後、デバイス自体が再フラッシュされます。  
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
- 非アクティブであるため、デバイスが Azure AD テナントから削除された。 効率的に管理される環境の場合、通常、IT 管理者は、[古い非アクティブなデバイスを Azure AD テナントから削除することをお勧めします](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices)。

影響を受けたデバイスが、削除された後に Azure AD テナントに再度接続しようとすると、Azure AD を使用した認証に失敗します。 PIN によるキャッシュされたログオンでは引き続きユーザーのログオンが許可されるので、この効果は多くの場合、デバイスのユーザーには表示されません。

### <a name="mitigation"></a>対応策
現在、削除された HoloLens デバイスを Azure AD に戻す方法はありません。 影響を受けるデバイスは、[デバイス の再フラッシュ](hololens-recovery.md#clean-reflash-the-device)に関する手順に従って 、クリーンな再フラッシュを行う必要があります。

## <a name="autopilot-troubleshooting"></a>Autopilot のトラブルシューティング

以下の記事は、Autopilot に関する問題の詳細情報を参照してトラブルシューティングを行う場合に役立つリソースです。ただし、これらの記事は、Windows 10 のデスクトップ版を使用しており、HoloLens には適用されない情報もあることにご注意ください。

- [Windows Autopilot - 既知の問題](https://docs.microsoft.com/mem/autopilot/known-issues)
- [Microsoft Intune での Windows デバイスの登録に関する問題のトラブルシューティング](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - ポリシーの競合](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

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
HoloLens の第 1 世代については、[この FAQ ](hololens1-faq-security.md)を参照してください。

[一覧に戻る](#list)
