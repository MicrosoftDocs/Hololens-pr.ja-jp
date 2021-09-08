---
title: HoloLens をネットワークに接続する
description: HoloLens を使用してインターネットを設定して接続する方法と、デバイスの IP アドレスを識別する方法について説明します。
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, Wi-Fi, ワイヤレス, インターネット, IP, IP アドレス
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: fe1c47de48e413a6f45921ba1e247016873ca996
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189105"
---
# <a name="connect-hololens-to-a-network"></a>HoloLens をネットワークに接続する

HoloLens で何らかの操作を実行するには、ほとんどの場合、ネットワークに接続している必要があります。 HoloLens には、802.11ac 対応の 2x2 Wi-Fi 無線が含まれているので、ネットワークに接続する方法は、Windows 10 デスクトップまたはモバイル デバイスを Wi-Fi ネットワークに接続するのと似ています。 このガイドは次の作業に役立ちます。

- Wi-Fi または HoloLens 2 のみの場合、Wi-Fi Direct または Ethernet over USB-C を使用してネットワークに接続する
- Wi-Fi を無効にし、再度有効にする

[HoloLens オフラインでの使用](hololens-offline.md)について詳しくは、こちらをご覧ください。

## <a name="connecting-for-the-first-time"></a>初めての接続

HoloLens を初めて使うときは、Wi-Fi ネットワークに接続するためのガイドが表示されます。 セットアップ中に Wi-Fi に接続できない場合は、接続先がオープン ネットワーク、パスワードで保護されたネットワーク、またはキャプティブ ポータル ネットワークであることを確認してください。 また、接続に証明書を使用する必要がネットワークに存在しない場合も確認します。 セットアップの完了後は、他の種類の Wi-Fi ネットワークにも接続できます。

HoloLens 2 デバイスでは、ユーザーは[USB-C からイーサネットアダプターを使用](hololens-connect-devices.md#hololens-2-connect-usb-c-devices)して Wi-Fi に直接接続し、デバイスのセットアップを支援することもできます。 デバイスがセットアップされた後、ユーザーはアダプターを引き続き使用するか、デバイスをアダプターから切断し、[セットアップ後にWi-Fiに接続することもできます](hololens-network.md#connecting-to-wi-fi-after-setup)。 

## <a name="connecting-to-wi-fi-after-setup"></a>セットアップ後の Wi-Fi 接続

1. **スタート ジェスチャ** を実行し、 **[設定]** を選択します。 設定アプリは、ユーザーの正面に自動配置されます。
1. **[ネットワークとインターネット]**  >  **[Wi-Fi]** を選択します。 Wi-Fi がオンになっていることを確認してください。 目的のネットワークが表示されない場合は、一覧を下方向へスクロールします。
1. ネットワークを選択し、 **[接続]** を選択します。
1. ネットワーク パスワードを求めるメッセージが表示されたら、入力して **[次へ]** を選択します。

![HoloLens の Wi-Fi 設定。](./images/hololens-2-wifi-settings.jpg)

Wi-Fi ネットワークに接続されていることを確認するには、 **[スタート]** メニューで Wi-Fiの状態を確認します。

1. **スタート** メニューを開きます。
1. **[スタート]** メニューの左上で Wi-Fi の状態を確認します。 Wi-Fi の状態と、接続されているネットワークの SSID が表示されます。

> [!TIP]
> Wi-Fi が使用できない場合は、 [携帯ネットワークや5G ネットワークに接続](hololens-cellular.md)することもできます。

> [!IMPORTANT]
> 設計上、ユーザーは HoloLens 2 の Wi-Fi ローミング動作を微調整することはできません。 **Wi-Fi リストを更新する唯一の方法は、Wi-Fi をオフまたはオンに切り替えることです**。 これにより、デバイスが範囲を外れ、AP に "スタック" 状態を維持できるなど、多くの問題が回避されます。

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>HoloLens をエンタープライズ Wi-Fi ネットワークに接続する

エンタープライズ Wi-Fi プロファイルは、拡張認証プロトコル (EAP) を使って Wi-Fi 接続を認証します。 HoloLens エンタープライズ Wi-Fi プロファイルは、[Windows 構成デザイナー](/windows/configuration/provisioning-packages/provisioning-packages) によって作成された MDM またはプロビジョニング パッケージを介して構成できます。

Microsoft Intune 管理対象デバイスの場合、構成手順については [Intune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) を参照してください。

WCD で Wi-Fi プロビジョニング パッケージを作成するには、事前に構成された Wi-Fi プロファイルの .xml ファイルが必要です。 以下は、EAP-TLS 認証を使用した WPA2-Enterprise の Wi-Fi プロファイルの例です。

``` xml
<?xml version="1.0"?> 
<WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1"> 
    <name>SampleEapTlsProfile</name> 
    <SSIDConfig> 
        <SSID> 
            <hex>53616d706c65</hex> 
            <name>Sample</name> 
        </SSID> 
        <nonBroadcast>true</nonBroadcast> 
    </SSIDConfig> 
    <connectionType>ESS</connectionType> 
    <connectionMode>auto</connectionMode> 
    <autoSwitch>false</autoSwitch> 
    <MSM> 
        <security> 
            <authEncryption> 
                <authentication>WPA2</authentication> 
                <encryption>AES</encryption> 
                <useOneX>true</useOneX> 
                <FIPSMode xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode> 
            </authEncryption> 
            <PMKCacheMode>disabled</PMKCacheMode> 
            <OneX xmlns="http://www.microsoft.com/networking/OneX/v1"> 
                <authMode>machine</authMode> 
                <EAPConfig> 
                    <EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                        <EapMethod> 
                            <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type> 
                            <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId> 
                            <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType> 
                            <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId> 
                        </EapMethod> 
                        <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                            <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"> 
                                <Type>13</Type> 
                                <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"> 
                                    <CredentialsSource><CertificateStore><SimpleCertSelection>true</SimpleCertSelection> 
                                        </CertificateStore> 
                                    </CredentialsSource> 
                                    <ServerValidation> 
                                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation> 
                                        <ServerNames></ServerNames> 
                                        <TrustedRootCA>00 01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f 10 11 12 13</TrustedRootCA> 
                                    </ServerValidation> 
                                    <DifferentUsername>false</DifferentUsername> 
                                    <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</PerformServerValidation> 
                                    <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName> 
                                </EapType> 
                            </Eap> 
                        </Config> 
                    </EapHostConfig> 
                </EAPConfig> 
            </OneX> 
        </security> 
    </MSM> 
</WLANProfile> 
```


サーバー ルート CA 証明書とクライアント証明書は、EAP の種類に応じて、デバイスにプロビジョニングされている必要があります。

その他のリソース:

- WLANv1 プロファイル スキーマ: [[MS-GPWL]: ワイヤレス LAN プロファイル v1 スキーマ | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- EAP-TLS スキーマ: [[MS-GPWL]: Microsoft EAP TLS スキーマ | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

Wi-fi への接続に問題がある場合は、 [トラブルシューティング](hololens2-enterprise-troubleshooting.md#) のページを確認してください。

## <a name="configure-network-proxy"></a>ネットワーク ポリシーの構成

このセクションでは Windows HTTP スタックを使用して HoloLens OS およびユニバーサル Windows プラットフォーム (UWP) アプリ用のネットワーク プロキシについて説明します。 Windows 以外の HTTP スタックを使用するアプリケーションでは、独自のプロキシ構成と処理を使用できます。 

### <a name="proxy-configurations"></a>プロキシの構成 

- プロキシの自動構成 (PAC) スクリプト: [PAC ファイル](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (Microsoft 以外のサイトを開く) には、JavaScript 関数 FindProxyForURL (url, host) が含まれています。 
- 静的プロキシ: サーバー: ポートの形式。  
- Web プロキシ自動検出プロトコル (WPAD): DHCP または DNS を介してプロキシ構成ファイルの URL を指定します。 

### <a name="proxy-provisioning-methods"></a>プロキシのプロビジョニング方法 
プロビジョニング プロキシを提供するには、3 つの方法があります。

 

1.  **設定UI:** 
    1. ユーザーごとのプロキシ (20H2 以前):
        1. スタート メニューを開き、[設定] を選択します。
        2. [ネットワークとインターネット] を選択して左のメニューでプロキシを選択します。
        3. [手動プロキシの設定] まで下にスクロールし、[プロキシサーバーの使用] を [オン] に切り替えます。
        4. プロキシ サーバーの IP アドレスを入力します。
        5. ポート番号を入力します。
        6. [保存] をクリックします。
      1. WiFi プロキシ (21H1 以降):
          1. スタートメニューを開き、Wi-Fi ネットワークのプロパティ ページにアクセスします。
          1. プロキシまで下方向へスクロールします。
          1. 手動セットアップに変更
          1. プロキシ サーバーの IP アドレスを入力します。
          1. ポート番号を入力します。
          1. [適用] をクリックします。
        
 2. **MDM** 
     1. Intune - Intune でプロキシを構成するには、次の[手順](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)に従います。 セクションの一番下までスクロールする必要があります。
     1. その他のサードパーティ製 MDM ソリューション- [WiFi CSP](/windows/client-management/mdm/wifi-csp)を使用します。

3. **PPKG** 
    1. Windows 構成デザイナーを開く
    1. [高度なプロビジョニング] をクリックし、新しいプロジェクトの名前を入力して、[次へ] をクリックします。
    1. [Windows Holographic (HoloLens 2)] を選択し、[次へ] をクリックします。
    1. PPKG をインポートし (オプション)、[完了] をクリックします。
    1. [ランタイムの設定] -> [接続プロファイル] -> [WLAN] -> [WLAN プロキシ] の順に展開します。
    1. Wi-Fi ネットワークの SSID を入力し、[追加] をクリックします。
    1. 左側のウィンドウで Wi-Fi ネットワークを選択し、必要なカスタマイズを入力します。 有効なカスタマイズは、左側のメニューに太字で表示されます。
    1. [保存して閉じる] をクリックします。
    1. HoloLens へプロビジョニング パッケージを[適用](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)氏ます。

[CSP](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) は、Microsoft Intune や Microsoft 以外の MDM サービス プロバイダーで、Windows 10 の多くの管理タスクとポリシーを陰で支えています。 [Windows 構成デザイナー](/windows/configuration/provisioning-packages/provisioning-install-icd)を使用して、[プロビジョニングパッケージ](/windows/configuration/provisioning-packages/provisioning-packages)を作成し、HoloLens 2 に適用することもできます。
HoloLens 2 に適用される可能性が最も高い CSP は次のとおりです。

- [WiFi CSP](/windows/client-management/mdm/wifi-csp): プロファイルごとの Wi-Fi プロキシ 

[HoloLens デバイスでサポートされているそのほかの CSP](/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a>VPN
VPN 接続を使用すると、より安全な接続と会社のネットワークやインターネットへのアクセスを提供できます。 HoloLens 2 は、組み込み VPN クライアントおよびユニバーサル Windows プラットフォーム (UWP) VPN プラグインをサポートしています。 

サポートされている組み込み VPN プロトコル:
- IKEv2
- L2TP
- PPTP

組み込みのVPN クライアントの認証に証明書を使用している場合は、必要なクライアント証明書をユーザー証明書ストアに追加する必要があります。 サードパーティの VPN プラグインが HoloLens 2 をサポートしているかどうかを確認するには、[VPN アプリ] がある [ストア] に移動し、 ARM または ARM64 アーキテクチャ をサポートしているアプリの [システム要件ページ] に [HoloLens] が表示されているかどうかを確認します。 HoloLens は、サード パーティ VPN 用のユニバーサル Windows プラットフォーム アプリケーションのみをサポートしています。

 VPN は[設定/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)を使用して MDM で管理し、 [Vpnv2-CSP ポリシー](/windows/client-management/mdm/vpnv2-csp)を使用して設定できます。

[VPN を構成する方法](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn)の詳細については、こちらの[ガイド](/windows/security/identity-protection/vpn/vpn-guide)を参照してください。  

### <a name="vpn-via-ui"></a>UI 経由の VPN

VPN は既定で有効になっていませんが、 **[設定]** アプリを開き、 **[ネットワークとインターネット] -> [VPN]** の順に移動して、手動で有効にすることができます。
1. VPN プロバイダーを選択します。
1. 接続名を作成します。 
1. サーバー名またはアドレスを入力します。
1. VPN の種類を選択します。
1. サインイン情報の種類を選択します。 
1. 必要に応じて、ユーザー名とパスワードを追加します。
1. VPN 設定を適用します。 

![HoloLens VPN の設定。](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>プロビジョニング パッケージによる VPN の設定

> [!TIP] 
> Windows Holographic バージョン 20H2 では、VPN 接続のプロキシ構成の問題が修正されました。 このフローを使う場合は、このビルドにデバイスをアップグレードすることを検討してください。

1. Windows 構成デザイナーを起動します。
1. **[HoloLens デバイスをプロビジョニング]** をクリックし、ターゲット デバイス と **[次へ]** を選択します。
1. パッケージ名とパスを入力します。
1. **[詳細エディターに切り替える]** をクリックします。
1. **[ランタイム設定]**  ->  **[ConnectivityProfiles]**  ->  **[VPN]**  ->  **[VPNSettings]** を開きます。
1. VPNProfileName を構成する
1. ProfileType (**Native** または **サードパーティー**) を選択します。
    1. ネイティブ プロファイルの場合、**NativeProtocolType** を選択し、サーバー、ルーティング ポリシー、認証の種類、その他の設定を構成します。
    1. 「サードパーティ」プロファイルの場合、サーバー URL、VPN プラグイン アプリ パッケージ ファミリ名 (事前に定義されている 3 つのみ) およびカスタム構成を構成します。
1. パッケージをエクスポートします。
1. HoloLens を接続して、.ppkg ファイルをデバイスにコピーします。 
1. HoloLens で、スタート メニュー を開き、 **[設定]**  ->  **[アカウント]**  ->  **[ワークまたはスクールにアクセス]**  ->  **[プロビジョニング パッケージを追加または削除]** -> [VPN パッケージを選択] を選択して、VPN .ppkg を適用します。


### <a name="setting-up-vpn-via-intune"></a>Intune を使用した VPN のセットアップ
Intune のドキュメントに従って、作業を開始します。 これらの手順を実行するときは、HoloLens デバイスがサポートする組み込みの VPN プロトコルに注意してください。 

[Intune で VPN サーバーに接続するための VPN プロファイルを作成します](/mem/intune/configuration/vpn-settings-configure)。

[Intune を使用して VPN 接続を追加するための Windows 10 デバイスと Windows Holographic デバイスの設定](/mem/intune/configuration/vpn-settings-windows-10)。

完了したら、忘れずに[プロファイル を割り当ててください](/mem/intune/configuration/device-profile-assign)。

### <a name="vpn-via-3rd-party-mdm-solutions"></a>サード パーティ MDM ソリューションを使用した VPN
サード パーティ VPN 接続の例:
```xml
<!-- Configure VPN Server Name or Address (PhoneNumber=) [Comma Separated]-->
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/ServerUrlList</LocURI>
          </Target>
          <Data>selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <!-- Configure VPN Plugin AppX Package ID (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/PluginPackageFamilyName</LocURI>
          </Target>
          <Data>TestVpnPluginApp-SL_8wekyb3d8bbwe</Data>
        </Item>
      </Add>

      <!-- Configure Microsoft's Custom XML (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/CustomConfiguration</LocURI>
          </Target>          <Data><pluginschema><ipAddress>auto</ipAddress><port>443</port><networksettings><routes><includev4><route><address>172.10.10.0</address><prefix>24</prefix></route></includev4></routes><namespaces><namespace><space>.vpnbackend.com</space><dnsservers><server>172.10.10.11</server></dnsservers></namespace></namespaces></networksettings></pluginschema></Data>
        </Item>
      </Add>
```

ネイティブ IKEv2 VPN の例:
```xml
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Servers</LocURI>
          </Target>
          <Data>Selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/RoutingPolicyType</LocURI>
          </Target>
          <Data>ForceTunnel</Data>
        </Item>
      </Add>

      <!-- Configure VPN Protocol Type (L2tp, Pptp, Ikev2) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/NativeProtocolType</LocURI>
          </Target>
          <Data>Ikev2</Data>
        </Item>
      </Add>

      <!-- Configure VPN User Method (Mschapv2, Eap) -->
      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/UserMethod</LocURI>
          </Target>
          <Data>Eap</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/Eap/Configuration</LocURI>
          </Target>
          <Data>EAP_configuration_xml_content</Data>
        </Item>
      </Add>
```
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a>HoloLens (第 1 世代) での Wi-Fi の無効化

### <a name="using-the-settings-app-on-hololens"></a>HoloLens での設定アプリの使用

1. **スタート** メニューを開きます。
1. **[スタート]** または **[スタート]** メニューの右側にある **[すべてのアプリ]** の一覧から **設定** アプリを選択します。 **設定** アプリは、ユーザーの正面に自動配置されます。
1. **[ネットワークとインターネット]** を選択します。
1. Wi-Fi のスライダー スイッチを選択して、**オフ** の位置に移動します。 これにより、Wi-Fi 無線の RF コンポーネントがオフになり、HoloLens 上の Wi-Fi 機能がすべて無効になります。

    > [!WARNING]
    > Wi-Fi 無線が無効になっている場合、HoloLens は[スペース](hololens-spaces.md)を自動的に読み込むことができません。

1. スライダー スイッチを **オン** の位置に移動して Wi-Fi 無線を有効にし、Microsoft HoloLens に Wi-Fi 機能を復元します。 選択した Wi-Fi 無線の状態 (**オン** または **オフ**) は、再起動しても維持されます。

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>Wi-Fi ネットワーク上での HoloLens の IP アドレスの識別

### <a name="by-using-the-settings-app"></a>設定アプリを使用する

1. **スタート** メニューを開きます。
1. **[スタート]** または **[スタート]** メニューの右側にある **[すべてのアプリ]** の一覧から **設定** アプリを選択します。 **設定** アプリは、ユーザーの正面に自動配置されます。
1. **[ネットワークとインターネット]** を選択します。
1. 使用可能な Wi-Fi ネットワークの下までスクロールし、 **[ハードウェアのプロパティ]** を選択します。

    ![Wi-Fi 設定のハードウェア プロパティ。](./images/wifi-hololens-hwdetails.jpg)

   IP アドレスは、**IPv4 アドレス** の横に表示されます。

### <a name="by-using-voice-commands"></a>音声コマンドを使用する

使用しているデバイスに応じて、組み込み音声コマンドや Cortana を使用して IP アドレスを表示することができます。 ビルドで [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) の後に、"IP アドレスを教えて" と話します。 すると、それが表示されます。 以前のビルドまたは HoloLens (第１世代) では、「コルタナさん、IP アドレスを教えて」 と言います。 Cortana によって IP アドレスの表示と読み上げが行われます。

### <a name="by-using-windows-device-portal"></a>Windows デバイス ポータルを使用する

1. PC の Web ブラウザーで、[デバイス ポータル](/windows/mixed-reality/using-the-windows-device-portal.md#networking)を開きます。
1. **[ネットワーク]** セクションに移動 します。  
   このセクションには、IP アドレスとその他のネットワーク情報が表示されます。 この方法を使用すると、開発用 PC の IP アドレスをコピーして貼り付けることができます。

## <a name="change-ip-address-to-static-address"></a>IP アドレスを静的アドレスに変更
### <a name="by-using-settings"></a>設定を使用する
 
1. **スタート** メニューを開きます。
1. **[スタート]** または **[スタート]** メニューの右側にある **[すべてのアプリ]** の一覧から **設定** アプリを選択します。 **設定** アプリは、ユーザーの正面に自動配置されます。
1. **[ネットワークとインターネット]** を選択します。
1. 使用可能な Wi-Fi ネットワークの下までスクロールし、 **[ハードウェアのプロパティ]** を選択します。
1. **[IP 設定の編集]** ウィンドウ で、最初のフィールドを **[手動]** に変更します。
1. 残りのフィールドに目的の IP 構成を入力し、 **[保存]** を クリックします。

### <a name="by-using-windows-device-portal"></a>Windows デバイス ポータルを使用する

1. PC の Web ブラウザーで、[デバイス ポータル](/windows/mixed-reality/using-the-windows-device-portal.md#networking)を開きます。
1. **[ネットワーク]** セクションに移動 します。
1. **[IPv4 構成]** ボタンを選択します。
1. **[次 の IP アドレスを使用する]** を選択し、必要な TCP/IP 構成を入力します。
1. **[次の DNS サーバー アドレスを使用する]** を選択し、必要に応じて優先 DNS サーバー アドレスと代替 DNS サーバー アドレスを入力します。
1. **[保存]** をクリックします。 
