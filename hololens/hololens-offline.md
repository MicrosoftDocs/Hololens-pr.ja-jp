---
title: HoloLens の接続エンドポイントの管理
description: 接続エンドポイントの管理と構成を行いながら、Wi-Fi ネットワーク経由で HoloLens を設定する方法について説明します。
keywords: hololens、オフライン、OOBE
audience: ITPro
ms.date: 07/01/2019
ms.assetid: b86f603c-d25f-409b-b055-4bbc6edcd301
author: Teresa-Motiv
ms.author: v-tea
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: jarrettr
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f2d9faafac2f84b727b1e10be83d4d1b53a707b4
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640085"
---
# <a name="manage-connection-endpoints-for-hololens"></a>HoloLens の接続エンドポイントの管理

一部の HoloLens コンポーネント、アプリ、関連サービスにより、Microsoft ネットワーク エンドポイントにデータが転送されます。 この記事では、これらのコンポーネントを機能させるために、ネットワーク構成 (プロキシやファイアウォールなど) で許可する必要のあるさまざまなエンドポイントと URL を示します。    

## <a name="near-offline-setup"></a>ほぼオフラインのセットアップ

HoloLens は、ネットワーク環境に制限があるお客様向けに、限定された一連のオフライン エクスペリエンスをサポートしています。 ただし、HoloLens でデバイスの初期設定を行うにはネットワーク接続が必要であり、次の URL を有効にする必要があります。

| 目的 | URL |
|------|------|
| IDPS | https://sdx.microsoft.com/frx/idps |
| [NCSI](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services#bkmk-ncsi) |  http://www.msftconnecttest.com/connecttest.txt  |
| AADv9 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/9 |
| AADv10 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/10 |
| AAD PIN | https://account.live.com/aadngc?uiflavor=win10&showSuccess=1 |
| MSA | https://login.live.com/ppsecure/inlineconnect.srf?id=80600 |
| MSA PIN | https://account.live.com/msangc?fl=enroll |

## <a name="endpoint-configuration"></a>エンドポイントの構成

HoloLens 機能を最大限に活用するには、上記の一覧に加えて、ネットワーク構成で次のエンドポイントを有効にする必要があります。


| 目的 | URL |
|------|------|
| Azure                                               | wd-prod-fe.cloudapp.azure.com                                       |
|                                                     | ris-prod-atm.trafficmanager.net                                     |
|                                                     | validation-v2.sls.trafficmanager.net                                |
| Azure AD の Multi-Factor Authentication                | https://secure.aadcdn.microsoftonline-p.com                         |
| Intune と MDM の構成                       | activation-v2.sls.microsoft.com/*                                   |
|                                                     | cdn.onenote.net                                                     |
|                                                     | client.wns.windows.com                                              |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ctldl.windowsupdate.com                                             |
|                                                     | *displaycatalog.mp.microsoft.com                                    |
|                                                     | dm3p.wns.windows.com                                                |
|                                                     | *microsoft.com/pkiops/*                                             |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | r.manage.microsoft.com                                              |
|                                                     | tile-service.weather.microsoft.com                                  |
|                                                     | settings-win.data.microsoft.com                                     |
| 証明書                                        | activation-v2.sls.microsoft.com/*                                   |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | https://www.microsoft.com/pkiops/*                                          |
| Cortana と検索                                  | store-images.*microsoft.com                                         |
|                                                     | www.bing.com/client                                                 |
|                                                     | www.bing.com                                                        |
|                                                     | www.bing.com/proactive                                              |
|                                                     | www.bing.com/threshold/xls.aspx                                     |
|                                                     | exo-ring.msedge.net                                                 |
|                                                     | fp.msedge.net                                                       |
|                                                     | fp-vp.azureedge.net                                                 |
|                                                     | odinvzc.azureedge.net                                               |
|                                                     | spo-ring.msedge.net                                                 |
| デバイス認証                               | login.live.com*                                                     |
| デバイス メタデータ                                     | dmd.metaservices.microsoft.com                                      |
| インストール先                                            | inference.location.live.net                                         |
|                                                     | location-inference-westus.cloudapp.net                              |
| 診断データ                                     | v10.events.data.microsoft.com                                       |
|                                                     | v10.vortex-win.data.microsoft.com/collect/v1                        |
|                                                     | https://www.microsoft.com                                                   |
|                                                     | co4.telecommand.telemetry.microsoft.com                             |
|                                                     | cs11.wpc.v0cdn.net                                                  |
|                                                     | cs1137.wpc.gammacdn.net                                             |
|                                                     | modern.watson.data.microsoft.com*                                   |
|                                                     | watson.telemetry.microsoft.com                                      |
| ライセンス                                           | licensing.mp.microsoft.com                                          |
| Microsoft アカウント                                   | login.msa.akadns6.net                                               |
|                                                     | us.configsvc1.live.com.akadns.net                                   |
| Microsoft Edge                                      | iecvlist.microsoft.com                                              |
| Microsoft 前方リンク リダイレクト サービス (FWLink) | go.microsoft.com                                                    |
| Microsoft Store                                     | *.wns.windows.com                                                   |
|                                                     | storecatalogrevocation.storequality.microsoft.com                   |
|                                                     | img-prod-cms-rt-microsoft-com*                                      |
|                                                     | store-images.microsoft.com                                          |
|                                                     | .md.mp.microsoft.com                                                |
|                                                     | *displaycatalog.mp.microsoft.com                                    |
|                                                     | pti.store.microsoft.com                                             |
|                                                     | storeedgefd.dsx.mp.microsoft.com                                    |
|                                                     | markets.books.microsoft.com                                         |
|                                                     | share.microsoft.com                                                 |
| ネットワーク接続状態インジケーター (NCSI)          | www.msftconnecttest.com*                                            |
| Office                                              | *.c-msedge.net                                                      |
|                                                     | *.e-msedge.net                                                      |
|                                                     | *.s-msedge.net                                                      |
|                                                     | nexusrules.officeapps.live.com                                      |
|                                                     | ocos-office365-s2s.msedge.net                                       |
|                                                     | officeclient.microsoft.com                                          |
|                                                     | outlook.office365.com                                               |
|                                                     | client-office365-tas.msedge.net                                     |
|                                                     | https://www.office.com                                                      |
|                                                     | onecollector.cloudapp.aria                                          |
|                                                     | v10.events.data.microsoft.com/onecollector/1.0/                     |
|                                                     | self.events.data.microsoft.com                                      |
|                                                     | to-do.microsoft.com                                                 |
| OneDrive                                            | g.live.com/1rewlive5skydrive/*                                      |
|                                                     | msagfx.live.com                                                     |
|                                                     | oneclient.sfx.ms                                                    |
| フォト アプリ                                          | evoke-windowsservices-tas.msedge.net                                |
| 設定                                            | cy2.settings.data.microsoft.com.akadns.net                          |
|                                                     | settings.data.microsoft.com                                         |
|                                                     | settings-win.data.microsoft.com                                     |
| Windows Defender                                    | wdcp.microsoft.com                                                  |
|                                                     | definitionupdates.microsoft.com                                     |
|                                                     | go.microsoft.com                                                    |
|                                                     | *smartscreen.microsoft.com                                          |
|                                                     | smartscreen-sn3p.smartscreen.microsoft.com                          |
|                                                     | unitedstates.smartscreen-prod.microsoft.com                         |
| Windows スポットライト                                   | *.search.msn.com                                                    |
|                                                     | arc.msn.com                                                         |
|                                                     | g.msn.com*                                                          |
|                                                     | query.prod.cms.rt.microsoft.com                                     |
|                                                     | ris.api.iris.microsoft.com                                          |
| Windows Update                                      | *.prod.do.dsp.mp.microsoft.com                                      |
|                                                     | cs9.wac.phicdn.net                                                  |
|                                                     | emdl.ws.microsoft.com                                               |
|                                                     | *.dl.delivery.mp.microsoft.com                                      |
|                                                     | *.windowsupdate.com                                                 |
|                                                     | *.delivery.mp.microsoft.com                                         |
|                                                     | *.update.microsoft.com                                              |



## <a name="references"></a>References

> [!NOTE]
> D365 Remote Assist を展開している場合は、「[Office 365 URL および IP アドレス範囲](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)」に記載されている SharePoint Online と OneDrive for Business のエンドポイントを有効にする必要があります。

- [組織内の Windows 診断データの構成](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)
- [Windows 10 Enterprise Version 1903 の接続エンドポイントの管理](/windows/privacy/manage-windows-1903-endpoints)
- [Windows 10 オペレーティング システム コンポーネントから Microsoft サービスへの接続を管理する](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services)
- [Microsoft Intune MDM サーバーを使って、Windows 10 オペレーティング システム コンポーネントから Microsoft サービスへの接続を管理する](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services-using-mdm)
- [Intune のネットワーク構成の要件と帯域幅](/intune/fundamentals/network-bandwidth-use#network-communication-requirements)
- [Microsoft Intune のネットワーク エンドポイント](/intune/fundamentals/intune-endpoints)
- [Office 365 の URL と IP アドレスの範囲](/office365/enterprise/urls-and-ip-address-ranges)
- [Azure AD Connect の前提条件](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)


## <a name="hololens-limitations"></a>HoloLens の制限

HoloLens をセットアップした後は、Wi-Fi 接続なしで使用できるようになりますが、HoloLens をオフラインで使用すると、インターネット接続を使用するアプリの機能は制限されます。
