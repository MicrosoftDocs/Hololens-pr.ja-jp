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
ms.openlocfilehash: 6d11ae0907aa82df71d7c86bb37996dcce71d845
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283978"
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

## HoloLens をエンタープライズ Wi-Fi ネットワークに接続する

エンタープライズ Wi-Fi プロファイルは、拡張認証プロトコル (EAP) を使って Wi-Fi 接続を認証します。 HoloLens エンタープライズ Wi-Fi プロファイルは、[Windows 構成デザイナー](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)によって作成された MDM またはプロビジョニング パッケージを介して構成できます。

Microsoft Intune 管理対象デバイスの場合、構成手順については [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) を参照してください。

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

- WLANv1プロファイル スキーマ: [[MS-GPWL]: ワイヤレス LAN プロファイル V1 スキーマ | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- EAP-TLS スキーマ: [[MS-GPWL]: Microsoft EAP TLS スキーマ | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

### EAP のトラブルシューティング

1. Wi-Fi プロファイルが正しく設定されているかどうかを再確認します。
   1. EAP の種類が正しく構成されているか。一般的な EAP の種類は、EAP-TLS (13)、EAP-TTLS (21)、および PEAP (25) です。
   1. Wi-Fi SSID 名は正しく、HEX 文字列と一致しているか。
   1. EAP-TLS の場合、TrustedRootCA に、サーバーの信頼されたルート CA 証明書の SHA-1 ハッシュが含まれるかどうか。 Windows PC で &quot;certutil.exe -dump cert\_file\_name&quot; コマンドを実行すると、証明書の SHA-1 ハッシュ文字列が表示されます。
1. アクセス ポイントまたはコントローラーまたは AAA サーバー ログでネットワーク パケット キャプチャを収集して、EAP セッションが失敗した場所を確認します。
   1. HoloLens によって提供される EAP ID が想定されていない場合は、Wi-Fi プロファイルまたはクライアント証明書を通じて、ID が正しくプロビジョニングされているかどうかを確認します。
   1. サーバーが HoloLens クライアント証明書を拒否した場合は、必要なクライアント証明書がデバイスでプロビジョニングされているかどうかを確認します。
   1. HoloLens がサーバー証明書を拒否した場合は、サーバー ルート CA 証明書が HoloLens でプロビジョニングされているかどうかを確認します。
1. エンタープライズ プロファイルが Wi-Fi プロビジョニング パッケージによってプロビジョニングされている場合は、Windows 10 PC にプロビジョニング パッケージを適用することを検討してください。 Windows 10 PC でもエラーが発生する場合は、「[Windows クライアント 802.1X 認証に関するトラブルシューティング ガイド](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication)」に従ってください。
1. [フィードバック Hub](https://docs.microsoft.com/hololens/hololens-feedback)からフィードバックを送信してください。

### その他のリソース:
- [Windows デバイスから Wi-Fi 設定をエクスポートする](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## VPN
VPN 接続を使用すると、より安全な接続と会社のネットワークやインターネットへのアクセスを提供できます。 HoloLens 2 は、組み込み VPN クライアントおよびユニバーサル Windows プラットフォーム (UWP) VPN プラグインをサポートしています。 

サポートされている組み込み VPN プロトコル:
- IKEv2
- L2TP
- PPTP

組み込みのVPN クライアントの認証に証明書を使用している場合は、必要なクライアント証明書をユーザー証明書ストアに追加する必要があります。 サードパーティの VPN プラグインが HoloLens 2 をサポートしているかどうかを確認するには、[VPN アプリ] がある [ストア] に移動し、 ARM または ARM64 アーキテクチャ をサポートしているアプリの [システム要件ページ] に [HoloLens] が表示されているかどうかを確認します。 HoloLens は、サード パーティ VPN 用のユニバーサル Windows プラットフォーム アプリケーションのみをサポートしています。

 VPN は、[Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) 経由で MDM によって管理され、[Vpnv2-csp ポリシー](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)を使用して設定できます。

[これらのガイド](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)を使用して [VPN を構成する方法](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn)の詳細をご覧ください。  

### UI 経由の VPN

VPN は既定で有効になっていませんが、**設定** アプリを開き、**[ネットワークとインターネット]、[VPN]** の順に移動して、手動で有効にすることができます。
1. VPN プロバイダーを選択します。
1. 接続名を作成します。 
1. サーバー名またはアドレスを入力します。
1. VPN の種類を選択します。
1. サインイン情報の種類を選択します。 
1. 必要に応じて、ユーザー名とパスワードを追加します。
1. VPN 設定を適用します。 

![HoloLens VPN の設定](./images/vpn-settings-ui.jpg)

### プロビジョニング パッケージによる VPN の設定

> [!TIP] 
> Windows Holographic バージョン 20H2 では、VPN 接続のプロキシ構成の問題が修正されました。 このフローを使う場合は、このビルドにデバイスをアップグレードすることを検討してください。

1. Windows 構成デザイナーを起動します。
1. **[HoloLens デバイスのプロビジョニング]** をクリックして対象のデバイスを選択してから **[次へ]** を選択します。
1. パッケージ名とパスを入力します。
1. **[詳細エディターに切り替える]** をクリックします。
1. **[ランタイム設定]** -> **[ConnectivityProfiles]** -> **[VPN]** -> **[VPNSettings]** の順に開きます。
1. VPNProfileName を構成する
1. ProfileType を **[ネイティブ]** または **[サードパーティ]** から選択します。
    1. ネイティブ プロファイルの場合、**[NativeProtocolType]** を選択し、サーバー、ルーティング ポリシー、認証の種類、その他の設定を構成します。
    1. 「サードパーティ」プロファイルの場合、サーバー URL、VPN プラグイン アプリ パッケージ ファミリ名 (事前に定義されている 3 つのみ) およびカスタム構成を構成します。
1. パッケージをエクスポートします。
1. HoloLens を接続して、.ppkg ファイルをデバイスにコピーします。 
1. HoloLens では、[スタート] メニューを開き、**[設定]** -> **[アカウント]** -> **[職場または学校にアクセスする]** -> **[プロビジョニング パッケージを追加または削除する]** の順に選択して、VPN パッケージを選択します。


### Intune を使用した VPN のセットアップ
Intune のドキュメントに従って、作業を開始します。 これらの手順を実行するときは、HoloLens デバイスがサポートする組み込みの VPN プロトコルに注意してください。 

[Intune で VPN サーバーに接続するための VPN プロファイルを作成します](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure)。

[Intune を使用して VPN 接続を追加するための Windows 10 および Windows Holographic デバイスを設定します](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)。

完了したら、[プロファイルを割り当てる](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)ことを忘れないでください。

### サード パーティ MDM ソリューションを使用した VPN
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
