---
title: HoloLens (gen) リリース ノート
description: 各新しいリリースの更新プログラムHoloLensします。
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 1
ms.openlocfilehash: e332794baf20fbab8278a138ceeafb651c6fa2a06f3f41a66038e544f7a6e46b
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661834"
---
# <a name="hololens-1st-gen-release-notes"></a>HoloLens (gen) リリース ノート

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens (第 1 世代) 長期サービス
HoloLens (第 1 世代) が長期サービス (LTS) 状態に入っています。 今後の更新プログラムでは、Windows 10 Holographic(第 1 世代) の Windows 10 Holographic バージョン 180 HoloLens 9 リリースと機能のパリティを維持しながら、問題とセキュリティの修正に焦点を当てる予定です。

開発者にとって、これは、HoloLens (第 1 世代) アプリが OpenXR API をサポートしないという意味です。  これらのヘッドセットは、Unity 2019 LTS から 2022 年半ばまで、WinRT API バックエンドを使用して Unity 2019 LTS で引き続きサポートされています。

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographicバージョン 1809

> **適用対象: HoloLens** (第 1 世代)

| 機能 | 詳細 |
|---|---|
| **[クイック アクション] メニュー** | アプリを使用すると、アプリから離れることなく、一般的に使用されるシステム機能にすばやくアクセスできる [クイック アクション] メニューが[花のジェスチャ] で開きます。 <br> キオスク[モードの [クイック HoloLens] メニュー](hololens-kiosk.md)の詳細については、「キオスク モードでのアプリの設定」を参照してください。<br><br> |
| **[スタート] または [クイック アクション] メニューからビデオ キャプチャを停止する** | [クイック アクション] メニュースタート メニュービデオ キャプチャを開始すると、同じ場所から記録を停止できます。 (忘れずに、音声コマンドでもいつでもこれを実行できます)。 |
| **Project対応デバイスMiracastに接続する** | Project Microsoft HoloLens使用している場合は、近くの Surface デバイスまたは TV/Monitor にコンテンツを送信します。  [**スタート]** で **、[Connect]** を選択し、投影先のデバイスを選択します。 **注:** 開発者モードを有効にHoloLens、Miracastプロジェクションを使用するアプリケーションをデプロイできます。 |
| **新しい通知** | PC の場合と同様に、HoloLens通知トーストを表示して応答します。 応答または閉じ込める視線入力 (イマーシブ エクスペリエンスを使用している場合は、花のジェスチャを使用します)。 |
| **HoloLensオーバーレイ**<br>(ファイル ピッカー、キーボード、ダイアログなど) | イマーシブ アプリを使用すると、キーボード、ダイアログ、ファイル ピッカーなどのオーバーレイが表示されます。 |
| **ボリューム変更用のビジュアル フィードバック オーバーレイ UI** | ボリューム の上下のボタンを使用すると、HoloLensレベルが視覚的に表示されます。 |
| **デバイス ブート用の新しい UI** | システムが読み込み中の視覚的フィードバックを提供するために、ブート プロセス中に読み込みインジケーターが追加されました。 デバイスを再起動して、新しい読み込みインジケーター ("Hello" メッセージとブート ロゴの間Windows表示します。 |
| **近くの共有** | 近くのWindows共有エクスペリエンスが追加され、近くのデバイスとキャプチャをWindowsできます。 HoloLens で写真やビデオをキャプチャする (または Microsoft Edge などのアプリから共有ボタンを使用する) 場合は、共有する近くの Windows デバイスを選択します。 |
| **共有を Microsoft Edge** | [共有] ボタンが、Microsoft Edgeウィンドウで使用HoloLens。 [共有Microsoft Edge] を **選択します**。 [共有] HoloLensを使用して Web コンテンツを共有します。 |

#### <a name="for-international-customers"></a>国際的な顧客向け

| 機能 | 詳細 |
| --- | --- |
| ローカライズされた中国語と日本語のビルド | ローカライズHoloLensキーボード、ディクテーション、音声コマンドなど、簡体中国語または日本語用のローカライズされたユーザー インターフェイスと一緒に使用します。<br>[中国語と日本語のバージョンのコンピューターをインストールする方法HoloLens。](hololens1-install-localized.md) |
| 音声合成 (TTS) | 音声合成機能では、中国語、日本語、英語がサポートされます。 |

#### <a name="for-administrators"></a>管理者向け

| 機能 |  詳細  |
|---|----|
| [セットアップ後のプロビジョニングを有効にする](hololens-provisioning.md) | を使用して、ランタイム プロビジョニング パッケージをいつでも **適用設定。** |
| グループへの割り当Azure ADアクセス | 割り当てられたアクセスAzure AD構成にWindowsグループを使用して、単一または複数アプリのキオスク構成を設定できます。 |
| サインイン画面からのプロファイルスイッチでの PIN サインイン | PIN サインインは、他のユーザー で **使用できます**。 |
| パスワードを使用して Web 資格情報プロバイダーサインインする | これで、Globe サインイン オプションを選択して、パスワードを使用して Web サインインを起動できます。 サインイン画面で [サインイン オプション] を **選択** し、[地球] オプションを選択して Web サインインを起動します。 必要に応じてユーザー名を入力し、次にパスワードを入力します。 <br>**注:** Web サインイン中にプロンプトが表示されたら、PIN/スマートカードオプションをバイパスするように選択できます。 |
| デバイスをシリアル番号で追跡できるよう MDM 経由でデバイス ハードウェア情報を読み取る | IT 管理者は、MDM コンソールHoloLensデバイスのシリアル番号別にデータを表示および追跡できます。 機能の可用性と手順については、MDM のドキュメントを参照してください。 |
| MDM をHoloLensデバイス名を設定する (名前の変更) | IT 管理者は、MDM コンソールでHoloLensデバイスを表示および名前変更できます。 機能の可用性と手順については、MDM のドキュメントを参照してください。 |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10バージョン 1803 for Microsoft HoloLens

> **適用対象: HoloLens** (第 1 世代)

Windows 10バージョン 1803 は、Windows Holographic for Business バージョン 1607 のリリース以降、Windows 10 の最初の機能更新プログラムです。 この更新プログラムでは、次の変更点が導入されています。

- 以前は、デバイスで VPN が使用可能なオプションである場合に確認することで、Commercial Suite のアップグレード ライセンスが HoloLens デバイスに適用されたことを確認するだけでした。 これで **、設定**  >  **ライセンス** が適用 **されたWindows Holographic for Business** システムが表示されます。 [機能のロックを解除するWindows Holographic for Businessします](hololens1-upgrade-enterprise.md)。

- オペレーティング システムのビルド番号は、エクスプローラー アプリのデバイス プロパティと Windows Device [Recovery Tool (WDRT) で確認できます](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)。
- 構成デザイナー ツールHoloLens新しい [デバイスのプロビジョニング]  HoloLensウィザードを使用すると、Windowsデバイスのプロビジョニングが簡単になりました。 ウィザードでは、セットアップ エクスペリエンスとネットワーク接続を構成し、開発者モードを設定し、一括認証トークンAzure ADできます。 [に対して簡単なプロビジョニング ウィザードを使用する方法HoloLens。](hololens-provisioning.md#provisioning-package-hololens-wizard)

- プロビジョニング パッケージでローカル アカウントを作成すると、パスワードは 42 日ごとに期限切れになることはありません。

- 単一[アプリHoloLensマルチアプリ キオスクとして構成できます](hololens-kiosk.md)。 マルチアプリ キオスク モードを使用すると、指定HoloLensアプリのみを実行するアプリを設定し、ユーザーが変更を行うのを防ぐのに使用できます。

- メディア転送プロトコル (MTP) が有効になっているので、HoloLens デバイスを USB で PC に接続し、HoloLens と PC の間でファイルを転送できます。 また、アプリで エクスプローラーを使用して、アプリ内からファイルを移動HoloLens。

- 以前は、Azure Active Directory (Azure AD) アカウントを使用してデバイスにサインインした後、会社のリソースにアクセスするには **、設定** で作業アクセスを追加する必要があります。 これで、アカウントを使用してサインインするとAzure AD登録が自動的に行われます。

- サインインする前に、パスワード フィールドの下にあるネットワーク アイコンを選択して、接続する別のWi-Fiを選択できます。 ホテル、カンファレンス センター、ビジネスなど、ゲスト ネットワークに接続できます。

- 複数のアカウントを使用[してHoloLensユーザーと](hololens-multiple-users.md)簡単にAzure ADできます。

- セットアップまたはサインインが失敗した場合は、新しい **[情報** の収集] オプションを選択して、トラブルシューティング用の診断ログを取得します。

- 個々のユーザーは、モバイル デバイス管理 (MDM) にデバイスを登録せずに、会社の電子メールを同期できます。 Microsoft アカウントでデバイスを使用し、メール アプリをダウンロードしてインストールし、電子メール アカウントを直接追加することができます。

- デバイスの MDM 同期の状態は、 [アカウント] から [設定  >    >  **または学校情報にアクセスする] で確認**  >  **できます**。 [ **デバイス同期の状態** ] セクションでは、同期を開始し、MDM によって管理されている領域を確認し、高度な診断レポートを作成してエクスポートすることができます。
