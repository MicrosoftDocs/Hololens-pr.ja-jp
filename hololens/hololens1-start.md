---
title: HoloLens のセットアップ (第1世代)
description: Microsoft (MSA) アカウントまたは Azure Active Directory (AAD) アカウントを使用して Wi-Fi ネットワーク経由で初めて HoloLens をセットアップする方法について説明します。
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
ms.openlocfilehash: f0ec62e55f15fda6d5a8304ea2bb77039d644b9e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309364"
---
# <a name="set-up-your-hololens-1st-gen"></a>HoloLens をセットアップする (第1世代)

HoloLens を初めてオンにしたときに、デバイスの調整、デバイスの設定、およびサインインについて説明します。  この記事では、HoloLens (第1世代) の最初の開始とセットアップのエクスペリエンスについて説明します。

次のセクションでは、HoloLens を操作し、ホログラムを操作する方法について説明します。 この記事に進むには、「 [HoloLens を使ってみる (第1世代)](hololens1-basic-usage.md)」を参照してください。

## <a name="before-you-start"></a>開始する前に

作業を開始する前に、次のものが用意されていることを確認してください。

**Wi-Fi 接続** です。 HoloLens を Wi-Fi ネットワークに接続して設定する必要があります。 初めて接続するときは、web サイトへの移動や接続に証明書を使用する必要がない、開いている、またはパスワードで保護されたネットワークが必要です。 [HoloLens が使用する web サイトの詳細については、こちらを参照して](hololens-offline.md)ください。

**Microsoft アカウントまたは職場アカウント**。 また、HoloLens にサインインするには、Microsoft アカウント (または、組織がデバイスを所有している場合は職場のアカウント) を使用する必要があります。 Microsoft アカウントがない場合は、 [account.microsoft.com](https://account.microsoft.com) にアクセスし、1つを無料で設定します。

**危険な状態にならない安全で十分に光がある領域**。 [正常性と安全性の情報](https://go.microsoft.com/fwlink/p/?LinkId=746661)。

お客様の HoloLens に付属している **オプションの快適なアクセサリは**、最適な適合性を得るのに役立ちます。 [より快適で安心](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)です。

> [!NOTE]
>  
> - HoloLens を初めて使用するときは、 [Cortana](hololens-cortana.md) は既にオンになっており、ガイドの準備ができています (ただし、デバイスをセットアップするまで質問に回答することはできません)。 Cortana の設定で、いつでも Cortana をオフにすることができます。
> - HoloLens の簡体字中国語または日本語版に切り替えるには、その言語のビルドを PC にダウンロードしてから HoloLens にインストールする必要があります。 詳細については、「 [HoloLens のローカライズ版をインストールする (第1世代)](hololens1-install-localized.md)」を参照してください。

## <a name="start-your-hololens-and-set-up-windows"></a>Hololens を起動して Windows をセットアップする

HoloLens を初めて起動するときは、まず、デバイスに Windows Holographic をセットアップします。

1. インターネットに接続します (HoloLens のガイドに従って Wi-Fi ネットワークを選択します)。

1. ユーザーアカウントにサインインします。 **職場または学校が所有するかどうか** を選択 **します。**
    - **職場または学校で所有** している場合は、Azure AD アカウントを使用してサインインします。 組織で Azure AD Premium を使用し、自動 MDM 登録を構成している場合、HoloLens は自動的に MDM に登録されます。 組織で Azure AD Premium を使用していない場合、MDM の自動登録は利用できないため、 [デバイス管理に HoloLens を手動で登録](hololens-enroll-mdm.md#different-ways-to-enroll)する必要があります。 職場または学校のアカウントを使用して初めてデバイスにサインインするには、次の手順を実行します。
        1. 組織のアカウント情報を入力します。
        1. プライバシーに関する声明に同意します。
        1. Azure AD の資格情報を使用してサインインします。 組織のサインイン ページにリダイレクトされることがあります。
        1. デバイスのセットアップを続行します。
    - **所有** している場合は、Microsoft アカウントを使用してサインインします。 セットアップが完了したら、 [デバイス管理に HoloLens を手動で登録](hololens-enroll-mdm.md#different-ways-to-enroll)できます。
        1. Microsoft アカウント情報を入力します。
        1. パスワードを入力します。 Microsoft アカウントで [2 段階認証 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/) が要求される場合、検証プロセスを実行します。

1. デバイスは、Wi-Fi ネットワークから取得した情報に基づいてタイムゾーンを設定します。

## <a name="calibration"></a>調整

Cortana が自分で導入された後、次のセットアップ手順は調整です。 最適な HoloLens エクスペリエンスを実現するには、セットアップ中に調整プロセスを完了する必要があります。

HoloLens (第1世代) では、pupils (IPD または [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance)) 間の距離を使用して、ホログラムをクリアし、簡単に操作できるようにします。 IPD が正しくない場合、ホログラムが不安定であるか、または正しくない距離にあるように見えることがあります。

調整中、HoloLens は、1つ目につき6つのターゲットに指を合わせるように求められます。 HoloLens は、このプロセスを使用して、目の IPD を適切なものに設定します。 新しいユーザーに対して調整を更新または調整する必要がある場合、新しいユーザーはセットアップの外部で調整アプリを実行できます。

![2番目の手順での IPD の指配置画面](./images/ipd-finger-alignment-300px.jpg)

*2番目の手順での IPD の指配置画面*

おめでとうございます。 セットアップが完了し、HoloLens の使用を開始できます。

## <a name="next-steps"></a>次のステップ

> [!div class="nextstepaction"]
> [HoloLens を使ってみる (第1世代)](hololens1-basic-usage.md)
