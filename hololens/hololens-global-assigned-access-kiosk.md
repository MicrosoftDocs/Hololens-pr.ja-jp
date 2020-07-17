---
title: グローバルに割り当てられた
description: グローバルに割り当てられた Access キオスク向けの OMA URI の使用ガイド
author: evmill
ms.author: v-evmill
ms.date: 7/13/2020
ms.topic: article
keywords: hololens、hololens 2、割り当てられたアクセス、kiosk
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: ad7f75ccfcae9fb42974abb43d87f2f1ce1571f8
ms.sourcegitcommit: 3db43bc4a007b10901d8edb045f66e1e299c57a9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882455"
---
# <span data-ttu-id="d1f4d-104">グローバルに割り当てられたアクセス-キオスク</span><span class="sxs-lookup"><span data-stu-id="d1f4d-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="d1f4d-105">この機能は、システムレベルで適用可能なマルチアプリキオスクモード用に Hololens 2 デバイスを構成します。システム上のID とのアフィニティはありません。また、デバイスにサインインするすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d1f4d-105">This feature configures Hololens 2 device for multiple app kiosk mode which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span> 

> [!NOTE]
> <span data-ttu-id="d1f4d-106">この機能は現在、Windows Insider ビルドでのみ利用可能です。 </span><span class="sxs-lookup"><span data-stu-id="d1f4d-106">This feature is currently only avalible in Windows Insider builds.</span></span> <span data-ttu-id="d1f4d-107">HoloLensリリースで一般に利用可能になる前にこの機能を試してみたい場合は、[Windows Insider](hololens-insider.md)ビルドの詳細をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d1f4d-107">If you would like to try this feature before it is generally avalible in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>
 
## <span data-ttu-id="d1f4d-108">Intuneでこれを使用する方法</span><span class="sxs-lookup"><span data-stu-id="d1f4d-108">How to use this in Intune?</span></span> 

> [!NOTE]
> <span data-ttu-id="d1f4d-109">[<!-] が付いている領域に注意してください。</span><span class="sxs-lookup"><span data-stu-id="d1f4d-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="d1f4d-110">これらの領域には、ユーザー設定に基づいて変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1f4d-110">These areas will require you to make modifications based on your preferences.</span></span> 

1.  <span data-ttu-id="d1f4d-111">次のように、カスタムの OMA URI デバイス構成プロファイルを作成して、 HoloLens デバイスグループに適用します：![ Intune でグローバル割り当てられたアクセス OMA-URI</span><span class="sxs-lookup"><span data-stu-id="d1f4d-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group: ![Global Assigned Access OMA-URI in Intune</span></span>](images/global-assigned-access-omauri.png)

2.  <span data-ttu-id="d1f4d-112">値については、以下の内容を更新して貼り付けます:</span><span class="sxs-lookup"><span data-stu-id="d1f4d-112">For value, update and paste following content:</span></span> 

    ```xml
    <?xml version="1.0" encoding="utf-8" ?> 
    <AssignedAccessConfiguration 
        xmlns="http://schemas.microsoft.com/AssignedAccess/2017/config" 
        xmlns:v2="http://schemas.microsoft.com/AssignedAccess/201810/config" 
        xmlns:v3="http://schemas.microsoft.com/AssignedAccess/2020/config" 
        xmlns:rs5="http://schemas.microsoft.com/AssignedAccess/201810/config" 
    > 
        <Profiles> 
            <Profile Id="{8739C257-184F-45DD-8657-C235819172A3}"> 
                <AllAppsList> 
                    <AllowedApps>                     
                        <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch=”true” /> --> 
                         <!—TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.settingn_8wekyb3d8bbwe!MicrosoftEdge" /> --> 
                     </AllowedApps> 
                </AllAppsList> 
                <StartLayout> 
                    <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"> 
                          <LayoutOptions StartTileGroupCellWidth="6" /> 
                          <DefaultLayoutOverride> 
                            <StartLayoutCollection> 
                              <defaultlayout:StartLayout GroupCellWidth="6"> 
                                <start:Group Name="Life at a glance"> 
                                  <!—This AUMID can be of any app and is not used on Hololens but is required for parity, so you can leave it as is. --> 
                                  <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" />                               
                                </start:Group> 
                              </defaultlayout:StartLayout> 
                            </StartLayoutCollection> 
                          </DefaultLayoutOverride> 
                        </LayoutModificationTemplate> 
                    ]]> 
                </StartLayout> 
                <Taskbar ShowTaskbar="true"/> 
            </Profile> 
        </Profiles> 
        <Configs> 
            <v3:GlobalProfile Id="{8739C257-184F-45DD-8657-C235819172A3}"/> 
        </Configs> 
    </AssignedAccessConfiguration> 
    ```

## <span data-ttu-id="d1f4d-113">Windows 構成デザイナーでこれを使用する方法</span><span class="sxs-lookup"><span data-stu-id="d1f4d-113">How to use this in Windows Configuration Designer?</span></span> 
 
1.  <span data-ttu-id="d1f4d-114">上記のXML blob を XML ファイルとして更新して保存します。</span><span class="sxs-lookup"><span data-stu-id="d1f4d-114">Update and save XML blob mentioned above as XML file.</span></span> 

2.  <span data-ttu-id="d1f4d-115">[プロビジョニングパッケージを使用して、単一アプリまたはマルチアプリキオスクをセットアップする](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) の手順に従います。特にセクション "Prov について。</span><span class="sxs-lookup"><span data-stu-id="d1f4d-115">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="d1f4d-116">パッケージ、ステップ 2-キオスクの構成 XML ファイルをプロビジョニングパッケージに追加し、前の手順で保存された XML ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="d1f4d-116">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span> 

## <span data-ttu-id="d1f4d-117">1つの AAD アカウントや AAD グループを除くすべてのユーザーにグローバルが適用される構成を作成できますか?</span><span class="sxs-lookup"><span data-stu-id="d1f4d-117">Can I create a configuration where global applies to everyone except 1 AAD account or AAD group?</span></span> 

<span data-ttu-id="d1f4d-118">はい。以下の XML blog の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1f4d-118">Yes, please refer to the example XML blob below.</span></span> <span data-ttu-id="d1f4d-119">グローバルに割り当てられたアクセスプロファイルは、サインインしたユーザーの特定のプロファイルが見つからない場合に Hololens に適用されるため、サインインしたユーザーの既定キオスクモードの構成になっています。</span><span class="sxs-lookup"><span data-stu-id="d1f4d-119">Global Assigned Access profile is applied on Hololens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span> <span data-ttu-id="d1f4d-120">使用する XML blob の例を表示します。</span><span class="sxs-lookup"><span data-stu-id="d1f4d-120">Here is an example of XML blob to be used:</span></span> 

> [!NOTE]
> <span data-ttu-id="d1f4d-121"><!- でマークされている領域に注意してください。これらの領域には、ユーザー設定に基づいて変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1f4d-121">Please be aware of the areas marked with <!-  these areas will require you to make modifications based on your preferences.</span></span> 

```xml
<?xml version="1.0" encoding="utf-8" ?> 
<AssignedAccessConfiguration xmlns="http://schemas.microsoft.com/AssignedAccess/2017/config" 
    xmlns:v2="http://schemas.microsoft.com/AssignedAccess/201810/config" 
    xmlns:v3="http://schemas.microsoft.com/AssignedAccess/2020/config" 
    xmlns:rs5="http://schemas.microsoft.com/AssignedAccess/201810/config"> 
    <Profiles> 
        <Profile Id="{9A2A490F-10F6-4764-974A-43B19E722C23}"> 
            <!—specify AUMIDs and other nodes as used in example above --> 
        </Profile> 
        <Profile Id="{8739C257-184F-45DD-8657-C235819172A3}"> 
            <!—specify AUMIDs and other nodes as used in example above --> 
        </Profile> 
    </Profiles> 
    <Configs> 
        <v3:GlobalProfile Id="{8739C257-184F-45DD-8657-C235819172A3}"/> 
        <Config> 
           <Account>AzureAD\<!-fully qualified AAD account name></Account> 
           <DefaultProfile Id="{9A2A490F-10F6-4764-974A-43B19E722C23}"/> 
        </Config> 
    </Configs> 
</AssignedAccessConfiguration> 
```
