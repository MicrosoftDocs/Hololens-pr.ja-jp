---
title: HoloLens (第 1 世代) のセットアップ
description: Microsoft (MSA) アカウントまたは Azure Active Directory (AAD) アカウントを使用して、Wi-Fi ネットワーク上で初めて HoloLens (第 1 世代) をセットアップする方法について説明します。
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
ms.sourcegitcommit: 01c0b0a789e156a9d29aaf6f61e36dfd09b8c01a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439063"
---
# <a name="set-up-your-hololens-1st-gen"></a>HoloLens (第 1 世代) のセットアップ

初めて HoloLens の電源を入れたときは、デバイスの調整、デバイスのセットアップ、サインインの手順を案内するガイドが表示されます。  この記事では、HoloLens (第 1 世代) の初回起動時とセットアップ時のエクスペリエンスについて説明します。

次のセクションでは、HoloLens とホログラムの操作方法を学びます。 直接この記事に進むには、「[HoloLens (第 1 世代) の概要](hololens1-basic-usage.md)」をご覧ください。

## <a name="before-you-start"></a>開始する前に

始める前に、以下が利用可能であることを確認してください。

**Wi-Fi 接続**。 HoloLens をセットアップするには、Wi-Fi ネットワークに接続する必要があります。 初回接続時には、Web サイトへの移動や証明書を必要とせずに接続できる、オープン ネットワークまたはパスワードで保護されたネットワークが必要です。 [HoloLens で使用する Web サイトについて詳しくは、こちらをご覧ください](hololens-offline.md)。

**Microsoft アカウントまたは職場アカウント**。 HoloLens にサインインするには、Microsoft アカウント (または、組織がデバイスを所有している場合は職場アカウント) を使用する必要があります。 Microsoft アカウントをお持ちでない場合は、[account.microsoft.com](https://account.microsoft.com) にアクセスして無料でセットアップできます。

**つまずく危険性のない安全で明るい場所**。 [健康と安全に関する情報をご覧ください](https://go.microsoft.com/fwlink/p/?LinkId=746661)。

**快適さを高めるオプションのアクセサリ**。HoloLens には、より快適なフィット感を得られるように、オプションのアクセサリが付属しています。 [快適に使うための詳しい情報をご覧ください](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)。

> [!NOTE]
>  
> - HoloLens を初めて使うときは、[Cortana](hololens-cortana.md) が既定でオンになり、ガイドが提供されます (ただし、デバイスのセットアップが完了するまでユーザーの質問に答えることはできません)。 Cortana の使用は、Cortana の設定を使用して、いつでもオフに変更できます。
> - HoloLens の中国語版または日本語版に切り替えるには、その言語のビルドを PC にダウンロードしてから HoloLens にインストールする必要があります。 詳細については、「[HoloLens (第 1 世代) のローカライズされたバージョンをインストールする](hololens1-install-localized.md)」を参照してください。

## <a name="start-your-hololens-and-set-up-windows"></a>Hololens の起動と Windows のセットアップ

初めて HoloLens を起動する場合は、最初の作業として、デバイスで Windows Holographic をセットアップする必要があります。

1. インターネットに接続します (HoloLens により、Wi-Fi ネットワークを選択できるようにガイドが表示されます)。

1. お使いのユーザー アカウントにサインインします。 **[職場または学校が所有しています]** または **[自分が所有しています]** を選択します。
    - **[職場または学校が所有しています]** を選択し場合は、Azure AD アカウントを使用してサインインします。 組織で Azure AD Premium を使用しており、MDM への自動登録が構成されている場合は、HoloLens が自動的に MDM に登録されます。 組織で Azure AD Premium が使用されていない場合は MDM への自動登録を利用できないため、[HoloLens をデバイス管理に手動で登録](hololens-enroll-mdm.md#different-ways-to-enroll)する必要があります。 職場または学校のアカウントを使用してデバイスへの初回サインインを行うには、次の手順を実行します。
        1. 組織アカウントの情報を入力します。
        1. プライバシー ステートメントに同意します。
        1. Azure AD 資格情報を使用してサインインします。 組織のサインイン ページにリダイレクトされることがあります。
        1. デバイスのセットアップを続行します。
    - **[自分が所有しています]** を選んだ場合は、Microsoft アカウントを使用してサインインします。 セットアップが完了したら、[手動で HoloLens をデバイス管理に登録](hololens-enroll-mdm.md#different-ways-to-enroll)できます。
        1. Microsoft アカウントの情報を入力します。
        1. パスワードを入力します。 Microsoft アカウントで [2 段階認証 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/) が要求される場合、検証プロセスを実行します。

1. Wi-Fi ネットワークから取得された情報に基づいて、デバイスでタイム ゾーンが設定されます。

## <a name="calibration"></a>調整

Cortana の紹介後、次のセットアップ手順は調整です。 HoloLens のエクスペリエンスを最適化するには、セットアップ中に調整プロセスを完了する必要があります。

HoloLens (第 1 世代) では、ホログラムをクリアに表示し、操作しやすくするために、瞳孔間距離 (IPD: [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance)) を使用します。 IPD が正しくない場合は、ホログラムが不安定になったり、正しくない距離感で表示されます。

HoloLens の調整では、片目ごとに 6 つのターゲットに指を合わせるように求められます。 HoloLens はこのプロセスを使用し、ユーザーの目に合わせた適切な IPD を設定します。 新しいユーザー用に調整を更新または調整する必要がある場合、セットアップ外で調整アプリを実行できます。

![IPD の指合わせ画面 (2 番目の手順)](./images/ipd-finger-alignment-300px.jpg)

*IPD の指合わせ画面 (2 番目の手順)*

お疲れさまでした。 セットアップは完了です。HoloLens の使用を開始できます。

## <a name="next-steps"></a>次のステップ

> [!div class="nextstepaction"]
> [HoloLens (第 1 世代) の概要](hololens1-basic-usage.md)
