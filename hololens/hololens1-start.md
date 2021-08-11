---
title: HoloLens (第 1 世代) を設定する
description: Microsoft (MSA) または Azure Active Directory (AAD) アカウントを使用して、Wi-Fi ネットワークを使用して HoloLens (第 1 世代) を初めて設定する方法について説明します。
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
ms.openlocfilehash: 9e09ba1a022428b098392464e5cd2abf84911bd6a86d8e699036b8fc4f91470a
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661867"
---
# <a name="set-up-your-hololens-1st-gen"></a>HoloLens (第 1 世代) のセットアップ

デバイスを初めて有効にHoloLens、デバイスの調整、デバイスの設定、サインインに関するガイドが表示されます。  この記事では、HoloLens (第 1 世代) の最初の開始とセットアップのエクスペリエンスについて説明します。

次のセクションでは、HoloLens とホログラムの操作方法を学びます。 この記事に進むには、「概要 (第 1 世代HoloLens[を参照してください](hololens1-basic-usage.md)。

## <a name="before-you-start"></a>開始する前に

始める前に、以下が利用可能であることを確認してください。

**接続Wi-Fiです**。 ネットワークを設定するには、HoloLensネットワークWi-Fi接続する必要があります。 初回接続時には、Web サイトへの移動や証明書を必要とせずに接続できる、オープン ネットワークまたはパスワードで保護されたネットワークが必要です。 [HoloLens を使用する Web サイトの詳細について説明します](hololens-offline.md)。

**ユーザー Microsoft アカウントまたは仕事用アカウント**。 また、デバイスにサインインするには、Microsoft アカウント (または組織がデバイスを所有している場合は仕事用アカウント) を使用するHoloLens。 Microsoft アカウントをお持ち出ない場合は、[account.microsoft.com](https://account.microsoft.com) に進んで作成してください。無料です。

**トリップの危険性がない、安全で明るく照らされた空間**。 [正常性と安全性に関する情報](https://go.microsoft.com/fwlink/p/?LinkId=746661)。

HoloLens に付属する **最適なフィット感のアクセサリ** で、快適なフィット感が得られます。 [フィット感と快適性の詳細について](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)。

> [!NOTE]
>  
> - HoloLens を初めて使用する場合[、Cortana](hololens-cortana.md)は既にオンであり、ガイドを受け取る準備ができています (しかし、デバイスを設定するまで質問に回答することはできません)。 設定でCortanaをいつでもオフCortanaできます。
> - 中国語または日本語バージョンの HoloLens に切り替えるには、PC で言語のビルドをダウンロードし、HoloLens にインストールする必要があります。 詳細については、「ローカライズされたバージョンの HoloLens (第 1 世代)[をインストールする」を参照してください](hololens1-install-localized.md)。

## <a name="start-your-hololens-and-set-up-windows"></a>Hololens を起動し、次の設定Windows

デバイスを初めて起動HoloLens最初のタスクは、デバイスで Holographic Windowsを設定します。

1. Connectに接続します (HoloLensネットワークを選択Wi-Fiガイドします)。

1. お使いのユーザー アカウントにサインインします。 [自分の **仕事または学校が所有している] と** [所有しています **] の中から選択します**。
    - [マイ ワークまたは **学校が所有している] を** 選択した場合は、自分のアカウントを使用してAzure ADします。 組織で Azure AD Premium を使用しており、MDM への自動登録が構成されている場合は、HoloLens が自動的に MDM に登録されます。 組織で Azure AD Premium を使用していない場合は、MDM の自動登録を使用できないので、デバイス管理 にHoloLens[登録する必要があります](hololens-enroll-mdm.md#different-ways-to-enroll)。 初めて仕事用または学校アカウントを使用してデバイスにサインインするには、次の手順に従います。
        1. 組織アカウントの情報を入力します。
        1. プライバシーに関する声明に同意します。
        1. Azure AD 資格情報を使用してサインインします。 組織のサインイン ページにリダイレクトされることがあります。
        1. デバイスのセットアップを続行します。
    - [所有している] **を選択した** 場合は、次のコマンドを使用してサインインMicrosoft アカウント。 セットアップが完了したら、[HoloLens をデバイス管理に手動で登録](hololens-enroll-mdm.md#different-ways-to-enroll)できます。
        1. Microsoft アカウントの情報を入力します。
        1. パスワードを入力します。 Microsoft アカウントで [2 段階認証 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/) が要求される場合、検証プロセスを実行します。

1. デバイスは、ネットワークから取得した情報に基づいてタイム ゾーンWi-Fiします。

## <a name="calibration"></a>調整

ユーザー Cortanaを導入した後、次のセットアップ手順は調整です。 最適なエクスペリエンスHoloLens、セットアップ中に調整プロセスを完了する必要があります。

HoloLens (第 1 世代) では、ホログラムを明確で簡単に操作するために、受け子間の距離 (IPD または相互の[距離)](https://en.wikipedia.org/wiki/Interpupillary_distance)を使用します。 IPD が正しくない場合、ホログラムが不安定または正しくない距離にある可能性があります。

調整中、HoloLens目あたり 6 つの一連のターゲットに指を合わせてください。 HoloLensプロセスを使用して、目に適切な IPD を設定します。 新しいユーザーの調整を更新または調整する必要がある場合は、新しいユーザーはセットアップの外部で調整アプリを実行できます。

![IPD の指合わせ画面 (2 番目の手順)](./images/ipd-finger-alignment-300px.jpg)

*IPD の指合わせ画面 (2 番目の手順)*

おめでとうございます。 セットアップが完了し、次のコマンドの使用HoloLens。

## <a name="next-steps"></a>次のステップ

> [!div class="nextstepaction"]
> [HoloLens の概要 (第 1 世代)](hololens1-basic-usage.md)
