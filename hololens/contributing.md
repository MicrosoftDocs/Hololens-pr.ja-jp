---
title: 関与する指示
description: GitHub-flavored Markdown を使用して docs.microsoft.com プラットフォーム上の HoloLens docs に投稿する方法について説明します。
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: cbf0b2e4b61f006d0b5d7d74d3d81a4b33cfd6d8c2e124288b17959d54a5a1ad
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665068"
---
# <a name="contributing-to-the-hololens-documentation"></a>HoloLens のドキュメントに貢献する

[HoloLens のドキュメント](https://github.com/MicrosoftDocs/Hololens)へようこそ。 このリポジトリで作成または編集した記事 **は、パブリックに表示されます。** 

HoloLens docs は、docs.microsoft.com プラットフォームに表示されます。このプラットフォームでは、flavored Markdown を markdig 機能と共に GitHub 使用します。 このリポジトリで編集するコンテンツは、/hololens. に表示される定型ページに書式設定されます。

このページでは、Markdown の基本に寄与するための基本的な手順とガイドラインについて説明します。 投稿をお寄せいただき、ありがとうございます。

## <a name="available-repos"></a>利用可能なリポジトリ

| リポジトリ名です | URL |
| --- | --- |
| HoloLens | [Microsoft Docs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Mixed Reality | [Microsoft Docs/mixed-現実](/windows/mixed-reality) |
| VR 愛好家ガイド | [Microsoft Docs/mixed-現実ガイド](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>開始する前に

まだお持ちでない場合は、 [GitHub アカウントを作成](https://github.com/join)する必要があります。

>[!NOTE]
>microsoft の従業員の場合は、GitHub アカウントを microsoft[オープンソースポータル](https://repos.opensource.microsoft.com/)の microsoft エイリアスにリンクします。 **"Microsoft"** と "microsoft **docs"** の組織に参加してください。

GitHub アカウントを設定するときは、次のセキュリティに関する注意事項もお勧めします。
- [GitHub アカウントの強力なパスワード](https://github.com/settings/admin)を作成します。
- [2 要素認証](https://github.com/settings/two_factor_authentication/configure)を有効にします。
- [回復コード](https://github.com/settings/auth/recovery-codes)を安全な場所に保存します。
- [パブリックプロファイルの設定](https://github.com/settings/profile)を更新します。
   - 自分の名前を設定し、電子メールアドレスを *表示しない* ように *パブリック電子メール* を設定することを検討してください。
   - プロフィール画像をアップロードすることをお勧めします。これは、投稿するドキュメントページにサムネイルが表示されるためです。
- コマンドラインを使用する場合は、 [Windows 用に Git Credential Manager](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)を設定することを検討してください。 これにより、投稿を行うたびにパスワードを入力する必要がなくなります。

発行システムは GitHub に関連付けられているため、これらの手順は重要です。 GitHub エイリアスを使用して、各記事の作成者または共同作成者として一覧表示されます。

## <a name="editing-an-existing-article"></a>既存の記事の編集

次のワークフローを使用して、web ブラウザーで GitHub を介して *既存の記事* を更新します。

1. "Mixed-reality" フォルダーで、編集する記事に移動します。

2. 右上にある [編集] ボタン (鉛筆アイコン) を選択します。

   ![記事を編集します。](images/editpage.png)

   これにより、破棄可能な分岐が既定のブランチである _master_ に自動的にフォークされます。

   > [!NOTE]
   > この記事には、Microsoft が使用しなくなった、 _マスター_ への参照が含まれています。 ソフトウェアからこの用語が削除された時点で、この記事から削除します。
   
3. [Markdown の基本](#markdown-basics)に従って、記事の内容を編集します。

4. 各記事の上部にあるメタデータを更新します。

   * **title**: 記事が表示されているときに [ブラウザー] タブに表示されるページタイトル。 ページタイトルは、SEO とインデックス作成に使用されるため、必要な場合以外はタイトルを変更しないでください (ただし、ドキュメントが公開される前には重要度が低くなります)。
   * **description**: 記事のコンテンツに関する簡単な説明を記述します。これにより、SEO と検出が向上します。
   * **author**: ページのプライマリ所有者である場合は、ここに GitHub エイリアスを追加します。
   * **ms. author**: ページのプライマリ所有者である場合は、ここに Microsoft エイリアスを追加します (必要なのはエイリアスではありません @microsoft.com )。
   * **ms. date**: ページに主要なコンテンツを追加する場合は日付を更新します。ただし、明確、書式設定、文法、スペルなどの修正には使用しません。
   * **キーワード**: キーワードは、SEO (検索エンジンの最適化) に役立ちます。 コンマとスペースで区切られたキーワードを追加します。これは、記事に固有のものですが、リスト内の最後のキーワードの後には句読点がありません。 すべての記事に適用するグローバルキーワードを追加する必要はありません。他の場所で管理されているためです。 
   
5. 記事の編集が完了したら、下にスクロールして [ **ファイル変更の提案**] を選択します。

6. 次のページで、[ **プル要求の作成** ] を選択して、自動的に作成されたブランチを既定のブランチである _master_ にマージします。

7. 編集する次の記事に対して上記の手順を繰り返します。

## <a name="renaming-or-deleting-an-existing-article"></a>既存のアーティクルの名前の変更または削除

既存のアーティクルの名前を変更または削除する場合は、必ずリダイレクトを追加してください。 こうすることで、既存の記事へのリンクを持つユーザーは、引き続き適切な場所に配置されます。 リダイレクトは、リポジトリのルートにあるファイルの .openpublishing.redirection.jsによって管理されます。

.openpublishing.redirection.jsにリダイレクトを追加するには、次のように、配列にエントリを追加し `redirections` ます。

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- `source_path`は、削除しようとしている古いアーティクルへの相対リポジトリパスです。 パスがで始まり、で終わることを確認してください `mixed-reality-docs` `.md` 。

- は、 `redirect_url` 以前の記事から新しい記事までの相対パブリック URL です。 この URL は、  `mixed-reality-docs` `.md` リポジトリパスではなくパブリック url を参照しているため、またはを含んでいないことを確認してください。 を使用した新しいアーティクル内のセクションへのリンク `#section` は許可されます。 必要に応じて、ここで別のサイトへの絶対パスを使用することもできます。

- `redirect_document_id` 前のファイルのドキュメント ID を保持するかどうかを示します。 既定では、 `false`です。 リダイレクトされたアーティクルの属性値を保持する場合は、を使用し `true` `ms.documentid` ます。 ドキュメント ID を保持している場合は、ページビューやランキングなどのデータがターゲットアーティクルに転送されます。 リダイレクトの主な目的が名前変更であり、内容の一部だけが同じである別の記事へのポインターではない場合に、これを行ってください。

リダイレクトを追加する場合は、古いファイルも必ず削除してください。

## <a name="creating-a-new-article"></a>新しい記事を作成しています

次のワークフローを使用して、web ブラウザーで GitHub を使用してドキュメントリポジトリに *新しい記事を作成* します。

1. 右上の [**フォーク**] ボタンを使用して、microsoft docs/mixed reality の既定のブランチである _master_ からフォークを作成します。

   ![既定のブランチをフォークします。現在、"master" という名前が付けられています。](images/forkbranch.png)

   > [!NOTE]
   > この記事には、Microsoft が使用しなくなった、 _マスター_ への参照が含まれています。 ソフトウェアからこの用語が削除された時点で、この記事から削除します。
   
2. "Mixed-reality" フォルダーで、右上にある [ **新しいファイルの作成** ] を選択します。

3. アーティクルのページ名を作成します (スペースの代わりにハイフンを使用し、句読点やアポストロフィは使用しません)。 "md" を追加します。

   ![新しいページの名前を指定します。](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >必ず、"mixed-docs" フォルダー内から新しい記事を作成してください。 これを確認するには、新しいファイル名の行で "/mixed-reality-docs/" を確認します。

4. 新しいページの上部に、次のメタデータブロックを追加します。

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

5. 「 [既存の記事を編集する](#editing-an-existing-article)」の説明に従って、関連するメタデータフィールドに入力します。

6. [Markdown の基礎](#markdown-basics)を使用して、記事の内容を記述します。

7. `## See also`記事の下部に、関連するその他の記事へのリンクが記載されたセクションを追加します。

8. 完了したら、[ **新しいファイルをコミット** する] を選択します。

9. [ **新しいプル要求** ] を選択し、フォークの _マスター_ ブランチを microsoft docs/mixed reality _マスター_ にマージします (矢印が正しい宛先を指していることを確認します)。

   ![フォークからのプル要求を作成して、Microsoft Docs/mixed reality に](images/pr-to-master.png)

## <a name="markdown-basics"></a>Markdown の基本

Markdown 言語を使用してドキュメントを編集する方法については、次のリソースを参照してください。

- [Markdown の基礎](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Docs.microsoft.com の Markdown を作成するためのその他のリソース](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>テーブルの追加

Docs.microsoft.com スタイルの表では、インライン CSS を試す場合でも、罫線やカスタムスタイルはありません。 これは短時間は機能しているように見えますが、最終的には、プラットフォームによってテーブルからスタイルが除去されます。 そのため、事前に計画し、テーブルを単純にしておきます。 Markdown テーブルを簡単にするためのサイトを次に示します。 [Tables Generator] https://www.tablesgenerator.com/markdown_tables) ] ()

[Visual Studio Code の Docs Markdown 拡張機能](/teamblog/docs-extension)では、 [Visual Studio Code (下記参照)](#using-visual-studio-code)を使用してドキュメントを編集する場合にも、テーブルの生成を簡単に行うことができます。

### <a name="adding-images"></a>イメージの追加

イメージをレポポの "mixed-reality-docs/images" フォルダーにアップロードし、記事で適切に参照する必要があります。 画像はフルサイズで自動的に表示されます。これは、大きな画像が記事の幅全体を埋めるという意味です。 画像をアップロードする前に、事前にサイズを設定することをお勧めします。 推奨される幅は 600 から 700 ピクセルですが、高密度のスクリーンショットまたはスクリーンショットの一部である場合は、サイズを上下に設定する必要があります。

>[!IMPORTANT]
>マージする前に、フォークされたレポポに画像のみをアップロードできます。 そのため、記事に画像を追加する予定の場合は[、Visual Studio Code](#using-visual-studio-code)を使用して、最初にフォークの "images" フォルダーに画像を追加するか、Web ブラウザーで次の手順を実行する必要があります。
>
>1. MicrosoftDocs/Mixed-Reality レポポをフォークしました。
>2. フォーク内の記事を編集しました。
>3. 記事で参照している画像をフォークの "mixed-reality-docs/images" フォルダーにアップロードしました。
>4. フォークをmicrosoftDocs/mixed-reality マスター ブランチにマージpull requestを作成しました。
>
>独自のフォークされたレポポを設定する方法については、新しい記事 を作成する [手順に従ってください](#creating-a-new-article)。

## <a name="previewing-your-work"></a>作業のプレビュー

Web ブラウザーをGitHubで編集する場合は、ページの上部付近にある[プレビュー] タブを選択して、コミット前に作業をプレビューできます。 

>[!NOTE]
>変更のプレビューはreview.docs.microsoft.com Microsoft の従業員だけが利用できます

Microsoft の従業員: 投稿が既定のブランチ _master_ にマージされている場合は、</hololens?branch=master> で公開される前にコンテンツを確認できます。 左側の列の目次を使用して、記事を見つける。

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

   1. Web ブラウザーで pull request を作成し、MicrosoftDocs/Mixed-Reality の既定のブランチである _master_ の他の共同作成者からの最近の変更をフォークに同期します (矢印が正しい宛先を指していることを確認してください)。
      
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
      
3. Web ブラウザーで、フォークの新しい変更を MicrosoftDocs/Mixed-Reality マスターに同期する pull requestを作成します (矢印が正しい宛先を指していることを確認してください)。

   ![フォークpull request MicrosoftDocs/Mixed-Reality にアプリを作成する](images/pr-to-master.png)

### <a name="useful-extensions"></a>便利な拡張機能

次のVisual Studio Codeは、ドキュメントを編集するときに役立ちます。

- [Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - **Alt + M** を使用して、次のようなドキュメント作成オプションのメニューを表示します。
   - アップロードした画像を検索して参照します。
   - リスト、テーブル、ドキュメント固有の呼び出し (など) のような書式設定を追加します `>[!NOTE]` 。
   - 内部リンクとブックマーク (ページ内の特定のセクションへのリンク) を検索して参照します。
   - 書式設定エラーが強調表示されています (詳細については、エラーの上にマウス ポインターを合わせる)。
- [コード スペル チェック](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - スペルミスの単語には下線が引かされます。スペルミスの単語を右クリックして変更するか、ディクショナリに保存します。
