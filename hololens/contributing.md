---
title: 手順の貢献
description: 新しいフレーバーの Markdown を使用して、HoloLensプラットフォームの docs.microsoft.com ドキュメントにGitHubする方法について説明します。
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: 73b6e8bcd634cb4d45171bda0a85f2e991a977c9
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635672"
---
# <a name="contributing-to-the-hololens-documentation"></a>ドキュメントへのHoloLensする

ドキュメントへようこそHoloLens[してください](https://github.com/MicrosoftDocs/Hololens)。 このレポポで作成または編集した記事は **、一般に公開されます。** 

HoloLensドキュメントは、Markdig 機能と docs.microsoft.com された Markdown を使用GitHubプラットフォームに表示されます。 このレポジトで編集するコンテンツは、/hololens に表示されるスタイル化されたページに書式設定されます。

このページでは、Markdown の基本への貢献とリンクに関する基本的な手順とガイドラインについて説明します。 ご投稿いただきありがとうございます。

## <a name="available-repos"></a>使用可能なリポジトリ

| リポジトリ名です | [URL] |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Mixed Reality | [MicrosoftDocs/Mixed-Reality](/windows/mixed-reality) |
| VR ファンズ ガイド | [MicrosoftDocs/Mixed-Reality/ファンズガイド](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>開始する前に

アカウント をまだ作成していない場合は、アカウント を[作成GitHubがあります](https://github.com/join)。

>[!NOTE]
>Microsoft の従業員の場合は、Microsoft オープン ソース ポータルGitHubアカウントを Microsoft エイリアス[にリンクします](https://repos.opensource.microsoft.com/)。 **"Microsoft" および** **"MicrosoftDocs" 組織に参加** します。

お使GitHubアカウントを設定する場合は、次のセキュリティ上の注意事項も推奨されます。
- 自分の[アカウント の強力なパスワードをGitHubします](https://github.com/settings/admin)。
- 2 [要素認証 を有効にします](https://github.com/settings/two_factor_authentication/configure)。
- 回復コード [を安全な](https://github.com/settings/auth/recovery-codes) 場所に保存します。
- パブリック プロファイルの [設定を更新します](https://github.com/settings/profile)。
   - 自分の名前を設定し、[パブリック *メール]* を [自分のメール アドレスを表示しない *] に設定します*。
   - 投稿するドキュメント ページにサムネイルが表示されるので、プロファイル画像をアップロードすることをお勧めします。
- コマンド ラインを使用する予定の場合は、 に対して Git 資格情報マネージャー[を設定Windows。](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest) そうすることで、投稿を行うたびパスワードを入力する必要はありません。

発行システムは、公開システムGitHub関連付けられているので、これらの手順が重要です。 自分のエイリアスを使用して、各記事の作成者または共同作成者GitHubされます。

## <a name="editing-an-existing-article"></a>既存の記事の編集

次のワークフローを使用して、Webブラウザーで GitHubを更新します。

1. "mixed-reality-docs" フォルダーで編集する記事に移動します。

2. 右上にある編集ボタン (鉛筆アイコン) を選択すると、"master" ブランチから使い捨て可能なブランチが自動的にフォークされます。

   ![記事を編集します。](images/editpage.png)
   
3. "Markdown の基本" に従って、 [記事の内容を編集します](#markdown-basics)。

4. 各記事の上部にあるメタデータを更新します。

   * **title**: 記事を表示するときにブラウザー タブに表示されるページ タイトル。 ページ タイトルは SEO とインデックス作成に使用されます。そのため、必要な場合を限り、タイトルを変更する必要はありません (ドキュメントが公開される前はそれほど重要ではありません)。
   * **description**: 記事の内容の簡単な説明を記述します。この内容は SEO と検出を向上します。
   * **author:** ページのプライマリ所有者である場合は、ここに自分のエイリアスGitHub追加します。
   * **ms.author:** ページのプライマリ所有者である場合は、ここに Microsoft エイリアスを追加します (エイリアスは @microsoft.com 不要です)。
   * **ms.date:** ページに主要なコンテンツを追加する場合は日付を更新しますが、明確化、書式設定、文法、スペルの修正は行う必要はありません。
   * **keywords**: キーワードは、SEO (検索エンジンの最適化) を支援します。 記事に固有のコンマとスペースで区切られたキーワードを追加しますが、リスト内の最後のキーワードの後に句読点はありません。 すべての記事に適用されるグローバル キーワードは、他の場所で管理されているので、追加する必要があります。 
   
5. 記事の編集が完了したら、下にスクロールし、[ファイル変更の提案] **を選択します**。

6. 次のページで[作成] **を選択pull request** 自動的に作成されたブランチを 'master' にマージします。

7. 編集する次の記事について、上記の手順を繰り返します。

## <a name="renaming-or-deleting-an-existing-article"></a>既存の記事の名前変更または削除

変更によって既存の記事の名前が変更または削除される場合は、必ずリダイレクトを追加してください。 そうすることで、既存の記事へのリンクを持つユーザーは、依然として適切な場所に配置されます。 リダイレクトは、repo のルート.openpublishing.redirection.json ファイルで管理されます。

オンにリダイレクトを追加.openpublishing.redirection.js、配列にエントリを追加 `redirections` します。

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- は `source_path` 、削除する古い記事への相対リポジトリ パスです。 パスが で始まり、 `mixed-reality-docs` で終わる必要があります `.md` 。

- は `redirect_url` 、古い記事から新しい記事への相対パブリック URL です。 この URL は、リポジトリ **パスではなく** パブリック URL を参照しますので、 または `mixed-reality-docs` を含 `.md` めずにしてください。 を使用して、新しい記事内のセクション `#section` にリンクできます。 必要に応じて、ここで別のサイトへの絶対パスを使用できます。

- `redirect_document_id` は、前のファイルのドキュメント ID を保持するかどうかを示します。 既定では、 `false`です。 リダイレクト `true` された記事の属性値を `ms.documentid` 保持する場合は、 を使用します。 ドキュメント ID を保持すると、ページ ビューやランク付けなどのデータがターゲット記事に転送されます。 これは、リダイレクトが主に名前変更であり、同じコンテンツの一部のみを対象とする別の記事へのポインターではない場合に行います。

リダイレクトを追加する場合は、必ず古いファイルも削除してください。

## <a name="creating-a-new-article"></a>新しい記事の作成

次のワークフローを使用して *、Web* ブラウザーでレポートを使用してドキュメント GitHub新しい記事を作成します。

1. MicrosoftDocs/Mixed-Reality 'master' ブランチからフォークを作成します (上部の [ **フォーク** ] ボタンを使用)。

   ![マスター ブランチをフォークします。](images/forkbranch.png)
   
2. "mixed-reality-docs" フォルダーで、上部の **[新しいファイルの** 作成] を選択します。

3. 記事のページ名を作成し (スペースではなくハイフンを使用し、句読点やアポストロフィを使用しない)、".md" を追加します

   ![新しいページに名前を付け、](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >"mixed-reality-docs" フォルダー内から新しい記事を作成してください。 これを確認するには、新しいファイル名行で "/mixed-reality-docs/" を確認します。

4. 新しいページの上部に、次のメタデータ ブロックを追加します。

   ```md
   ---
   title:
   description:
   author:
   ms.author:
   ms.date:
   ms.topic: article
   keywords:
   ---
   ```

5. 上記のセクションの手順に従って、関連するメタデータ フィールド [を入力します](#editing-an-existing-article)。

6. Markdown の基本 を使用 [して記事のコンテンツを書き込む](#markdown-basics)。

7. 他の `## See also` 関連記事へのリンクを含むセクションを記事の下部に追加します。

8. 完了したら、[新しいファイルを **コミットする] を選択します**。

9. **[新しい** pull request] を選択し、フォークの 'master' ブランチを MicrosoftDocs/Mixed-Reality 'master' にマージします (矢印が正しい方法を指していることを確認してください)。

   ![フォークpull request MicrosoftDocs/Mixed-Reality にアプリを作成する](images/pr-to-master.png)

## <a name="markdown-basics"></a>Markdown の基本

次のリソースは、Markdown 言語を使用してドキュメントを編集する方法を学習するのに役立ちます。

- [Markdown の基礎](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Markdown for docs.microsoft.com の記述に関するその他の docs.microsoft.com](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>テーブルの追加

スタイル テーブルの docs.microsoft.com 方法のため、インライン CSS を試しても、罫線やカスタム スタイルは含め "されません"。 これは短時間動作する可能性がありますが、最終的にプラットフォームによってスタイル設定がテーブルから取り除かれます。 そのため、先に計画を立て、テーブルをシンプルに保つ必要があります。 [Markdown テーブルを簡単にするサイトを次に示します](https://www.tablesgenerator.com/markdown_tables)。

ドキュメント[の編集に](/teamblog/docs-extension)Visual Studio Code Docs Markdown 拡張機能を使用している場合は、Visual Studio Code Markdown 拡張機能を使用すると、テーブル[の](#using-visual-studio-code)生成も簡単になります。

### <a name="adding-images"></a>イメージの追加

イメージをレポポの "mixed-reality-docs/images" フォルダーにアップロードし、記事で適切に参照する必要があります。 画像はフルサイズで自動的に表示されます。これは、大きな画像が記事の幅全体を埋めるという意味です。 画像をアップロードする前に、事前にサイズを設定することをお勧めします。 推奨される幅は 600 から 700 ピクセルですが、高密度のスクリーンショットまたはスクリーンショットの一部である場合は、サイズを上下に設定する必要があります。

>[!IMPORTANT]
>マージする前に、フォークされたレポポに画像のみをアップロードできます。 そのため、記事に画像を追加する予定の場合は[、Visual Studio Code](#using-visual-studio-code)を使用して、最初にフォークの "images" フォルダーに画像を追加するか、Web ブラウザーで次の手順を実行する必要があります。
>
>1. MicrosoftDocs/Mixed-Reality レポポをフォークしました。
>2. フォーク内の記事を編集しました。
>3. 記事で参照している画像をフォークの "mixed-reality-docs/images" フォルダーにアップロードしました。
>4. フォークをmicrosoftDocs/mixed-reality 'master' ブランチにマージpull requestを作成しました。
>
>独自のフォークされたレポポを設定する方法については、新しい記事 を作成する [手順に従ってください](#creating-a-new-article)。

## <a name="previewing-your-work"></a>作業のプレビュー

Web ブラウザーをGitHubで編集する場合は、ページの上部付近にある[プレビュー] タブを選択して、コミット前に作業をプレビューできます。 

>[!NOTE]
>変更のプレビューはreview.docs.microsoft.com Microsoft の従業員だけが利用できます

Microsoft の従業員: 投稿が 'master' ブランチにマージされた後、</hololens?branch=master> で公開される前にコンテンツを確認できます。 左側の列の目次を使用して、記事を見つける。

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>ブラウザーでの編集とデスクトップ クライアントでの編集

ブラウザーでの編集は、簡単に変更を加える最も簡単な方法ですが、いくつかの欠点があります。

- スペル チェックは受け取らない。
- 他の記事へのスマート リンクは取得できません (記事のファイル名を手動で入力する必要があります)。
- 画像をアップロードして参照するのも面倒な場合があります。

これらの問題に対処しない場合は、Visual Studio Code のようなデスクトップ クライアントを使用して、[](https://code.visualstudio.com/)貢献するときに役立つ拡張機能を[](#useful-extensions)2 つ追加します。

## <a name="using-visual-studio-code"></a>Visual Studio Code の使用

上記の理由 [から、Web](#editing-in-the-browser-vs-editing-with-a-desktop-client)ブラウザーではなく、デスクトップ クライアントを使用してドキュメントを編集することができます。 [Visual Studio Code](https://code.visualstudio.com/) を使用することをお勧めします。

### <a name="setup"></a>セットアップ

次の手順に従って、このVisual Studio Codeを使用するための構成を構成します。

1. Web ブラウザーで:
    1. お使 [いの PC 用に Git をインストールします](https://git-scm.com/downloads)。
    2. [Visual Studio Code](https://code.visualstudio.com/) をインストールします。
    3. [まだ行っていない場合は、MicrosoftDocs/Mixed-Reality](#creating-a-new-article) をフォークします。
    4. フォークで、[複製] または **[ダウンロード] を選択し、URL** をコピーします。
2. 次の方法でフォークのローカル クローンを作成Visual Studio Code。
    1. [表示] **メニューの** [コマンド パレット] **を選択します**。
    2. 「Git: Clone」と入力します。
    3. コピーした URL を貼り付けます。
    4. 複製を PC に保存する場所を選択します。
    5. ポップアップ **で [Open repo]** を選択します。

### <a name="editing-documentation"></a>ドキュメントの編集

次のワークフローを使用して、 を使用してドキュメントを変更Visual Studio Code。

>[!NOTE]
>記事の編集と[作成に](#editing-an-existing-article)関するガイダンス、および[上記の Markdown](#markdown-basics)の編集の基本は、この記事を使用する場合Visual Studio Code適用されます。 [](#creating-a-new-article)

1. 複製したフォークが公式リポジトリで最新の情報に更新されていないことを確認します。

   1. Web ブラウザーで、MicrosoftDocs/Mixed-Reality 'master' の他の共同作成者からの最近の変更をフォークに同期する pull request を作成します (矢印が正しい方法を指している必要があります)。
      
      ![MicrosoftDocs/Mixed-Reality からフォークへの変更の同期](images/sync-repos.png)
      
   2. [Visual Studio Code同期] ボタンを選択して、新しく更新されたフォークをローカル クローンに同期します。
      
      ![同期ボタンの画像をクリックします](images/sync-clone.png)
      
2. 複製したリポジトリ内の記事を作成または編集するには、 Visual Studio Code。

   1. 1 つ以上の記事を編集します (必要に応じて、画像を "images" フォルダーに追加します)。
   
   2. **エクスプローラーに** 変更を **保存します**。
      
      ![エクスプローラーで [すべて保存] を選択する](images/explorer-save.png)
      
   3. **ソース管理のすべての** 変更を **コミットします** (メッセージが表示されたら、コミット メッセージを書き込む)。
   
      ![ソース管理で [すべてコミット] を選択する](images/source-control-commit.png)
      
   4. 同期ボタン **を選択** して、変更内容を元の元に戻します (GitHub。
      
      ![[同期] ボタンをクリックします](images/sync-back.png)
      
3. Web ブラウザーで、フォークの新しい変更を MicrosoftDocs/Mixed-Reality 'master' に同期する pull request を作成します (矢印が正しい方法を指していることを確認してください)。

   ![フォークpull request MicrosoftDocs/Mixed-Reality にアプリを作成する](images/pr-to-master.png)

### <a name="useful-extensions"></a>便利な拡張機能

次のVisual Studio Codeは、ドキュメントを編集するときに役立ちます。

- [Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - **Alt + M** を使用して、次のようなドキュメント作成オプションのメニューを表示します。
   - アップロードした画像を検索して参照します。
   - リスト、テーブル、ドキュメント固有の呼び出し (など) のような書式設定を追加します `>[!NOTE]` 。
   - 内部リンクとブックマーク (ページ内の特定のセクションへのリンク) を検索して参照します。
   - 書式設定エラーが強調表示されています (詳細については、エラーの上にマウス ポインターを合わせる)。
- [コード スペル チェック](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - スペルミスの単語には下線が引かされます。スペルミスの単語を右クリックして変更するか、ディクショナリに保存します。
