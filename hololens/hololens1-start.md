---
title: HoloLens の設定 (第1世代)
description: Microsoft (MSA) アカウントまたは Azure Active Directory (AAD) アカウントを使用して Wi-Fi ネットワーク上で初めて HoloLens を設定する方法について説明します。
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 06b7142be471d0db3f45812654288a33425abd60
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189870"
---
# <a name="set-up-your-hololens-1st-gen"></a>HoloLens (第 1 世代) のセットアップ

初めて HoloLens をオンにすると、デバイスの調整、デバイスの設定、およびサインインについてのガイドが表示されます。  この記事では、HoloLens (第1世代) 最初の開始とセットアップのエクスペリエンスについて説明します。

次のセクションでは、HoloLens とホログラムの操作方法を学びます。 この記事に進むには、「 [HoloLens の概要 (第1世代)](hololens1-basic-usage.md)」を参照してください。

## <a name="before-you-start"></a>開始する前に

始める前に、以下が利用可能であることを確認してください。

**Wi-Fi 接続** です。 HoloLens を Wi-Fi ネットワークに接続して設定する必要があります。 初回接続時には、Web サイトへの移動や証明書を必要とせずに接続できる、オープン ネットワークまたはパスワードで保護されたネットワークが必要です。 [HoloLens を使用する Web サイトの詳細について説明します](hololens-offline.md)。

**Microsoft アカウントまたは職場アカウント**。 また、HoloLens にサインインするには、Microsoft アカウント (または、組織がデバイスを所有している場合は職場のアカウント) を使用する必要があります。 Microsoft アカウントをお持ち出ない場合は、[account.microsoft.com](https://account.microsoft.com) に進んで作成してください。無料です。

**トリップの危険性がない、安全で明るく照らされた空間**。 [正常性と安全性に関する情報](https://go.microsoft.com/fwlink/p/?LinkId=746661)。

HoloLens に付属する **最適なフィット感のアクセサリ** で、快適なフィット感が得られます。 [フィット感と快適性の詳細について](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)。

> [!NOTE]
>  
> - 初めて HoloLens を使用する場合、 [Cortana](hololens-cortana.md)は既にオンになっており、ガイドの準備ができています (ただし、デバイスをセットアップするまで質問に回答することはできません)。 Cortana の設定でいつでも Cortana をオフにすることができます。
> - HoloLens の簡体字中国語または日本語版に切り替えるには、その言語のビルドを PC にダウンロードし、HoloLens にインストールする必要があります。 詳細については、「 [HoloLens のローカライズ版のインストール (第1世代)](hololens1-install-localized.md)」を参照してください。

## <a name="start-your-hololens-and-set-up-windows"></a>Hololens を起動して Windows を設定する

初めて HoloLens を開始するときに、最初にデバイスで Windows Holographic を設定します。

1. インターネットに Connect します (HoloLens ガイドネットワーク Wi-Fi 選択します)。

1. お使いのユーザー アカウントにサインインします。 **職場または学校が所有するかどうか** を選択 **します。**
    - **職場または学校で所有** している場合は、Azure AD アカウントを使用してサインインします。 組織で Azure AD Premium を使用しており、MDM への自動登録が構成されている場合は、HoloLens が自動的に MDM に登録されます。 組織で Azure AD Premium を使用していない場合は、MDM の自動登録を利用できないため、 [HoloLens をデバイス管理に手動で登録](hololens-enroll-mdm.md#different-ways-to-enroll)する必要があります。 職場または学校のアカウントを使用して初めてデバイスにサインインするには、次の手順を実行します。
        1. 組織アカウントの情報を入力します。
        1. プライバシーに関する声明に同意します。
        1. Azure AD 資格情報を使用してサインインします。 組織のサインイン ページにリダイレクトされることがあります。
        1. デバイスのセットアップを続行します。
    - **所有** している場合は、Microsoft アカウントを使用してサインインします。 セットアップが完了したら、[HoloLens をデバイス管理に手動で登録](hololens-enroll-mdm.md#different-ways-to-enroll)できます。
        1. Microsoft アカウントの情報を入力します。
        1. パスワードを入力します。 Microsoft アカウントで [2 段階認証 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/) が要求される場合、検証プロセスを実行します。

1. デバイスは、Wi-Fi ネットワークから取得した情報に基づいてタイムゾーンを設定します。

## <a name="calibration"></a>調整

Cortana が新しく導入された後、次のセットアップ手順は調整です。 最適な HoloLens エクスペリエンスを得るには、セットアップ中に調整プロセスを完了する必要があります。

HoloLens (第1世代) では、pupils (IPD または[interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance)) 間の距離を使用して、ホログラムをクリアし、簡単に操作できるようにします。 IPD が正しくない場合、ホログラムが不安定であるか、または正しくない距離にあるように見えることがあります。

調整中、HoloLens は、指を1つの視点に沿って6つのターゲットに揃えるように求めます。 HoloLens は、このプロセスを使用して、目の IPD を適切に設定します。 新しいユーザーに対して調整を更新または調整する必要がある場合、新しいユーザーはセットアップの外部で調整アプリを実行できます。

![2番目の手順での IPD の指配置画面。](./images/ipd-finger-alignment-300px.jpg)

*IPD の指合わせ画面 (2 番目の手順)*

おめでとうございます。 セットアップが完了し、HoloLens の使用を開始できます。

## <a name="next-steps"></a>次のステップ

> [!div class="nextstepaction"]
> [HoloLens の概要 (第 1 世代)](hololens1-basic-usage.md)
