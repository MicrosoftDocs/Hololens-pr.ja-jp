---
title: 操作手順
description: GitHub で提供される Markdown を使用して、docs.microsoft.com HoloLens ドキュメントに投稿する方法について説明します。
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: 311da6bc52098d5ba16e4684f68fec9a01e7c23b
ms.sourcegitcommit: 8cea4c04c6d2e22225f4de43e10c05dab840736a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "11253847"
---
# HoloLens ドキュメントへの貢献

[HoloLens ドキュメントへようこそ](https://github.com/MicrosoftDocs/Hololens)。 このレポで作成または編集した記事は **、一般のユーザーに表示されます。** 

HoloLens のドキュメントは、GitHub docs.microsoft.com Markdig 機能を備えた Markdown を使用する新しいプラットフォームに表示されます。 このレポで編集するコンテンツは、表示されるスタイル化されたページに書式設定されます https://docs.microsoft.com/hololens 。 

このページでは、Markdown に関する基本的な手順とガイドライン、および Markdown の基本へのリンクについて説明します。 ご投稿いただきありがとうございます。

## 利用可能なリポジトリ

| リポジトリ名 | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Mixed Reality | [MicrosoftDocs/mixed-Reality](https://docs.microsoft.com/windows/mixed-reality) |
| VR ファンズ ガイド | [MicrosoftDocs/mixed-reality/enthusiast-guide](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## 開始する前に

まだ持ってない場合は [、GitHub アカウントを作成する必要があります](https://github.com/join)。

>[!NOTE]
>Microsoft の従業員の場合は、Microsoft オープン ソース ポータルで GitHub アカウントを Microsoft エイリアス [にリンクします](https://repos.opensource.microsoft.com/)。 **"Microsoft" 組織と** **"MicrosoftDocs" 組織に参加**します。

GitHub アカウントをセットアップする場合は、次のセキュリティ上の予防措置も推奨されます。
- [GitHub アカウントの強力なパスワードを作成します](https://github.com/settings/admin)。
- 2 [要素認証を有効にします](https://github.com/settings/two_factor_authentication/configure)。
- 回復コード [を安全な場所](https://github.com/settings/auth/recovery-codes) に保存します。
- パブリック プロファイルの [設定を更新します](https://github.com/settings/profile)。
   - 名前を設定し、パブリック メール *にメール* アドレスを表示 *しない設定を検討してください*。
   - 投稿するドキュメント ページにサムネイルが表示される場合は、プロファイル画像をアップロードすることをお勧めします。
- コマンド ラインを使用する場合は、Windows 用 [の Git Credential Manager のセットアップを検討してください](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)。 そうすることで、投稿の度にパスワードを入力する必要はありません。

発行システムは GitHub に関連付けられているので、次の手順が重要です。 GitHub エイリアスを使用して、各記事の作成者または投稿者として一覧表示されます。

## 既存の記事の編集

次のワークフローを使用して、Web** ブラウザーで GitHub 経由で既存の記事を更新します。

1. 編集する記事に移動し、"mixed-reality-docs" フォルダーに移動します。

2. 右上にある編集ボタン (鉛筆アイコン) を選択します。このボタンをクリックすると、"master" 分岐の分岐が自動的に分岐します。

   ![記事を編集します。](images/editpage.png)
   
3. 「Markdown の基本」に従って記事 [の内容を編集します](#markdown-basics)。

4. 各記事の上部にあるメタデータを更新します。

   * **title**: 記事が表示されているときにブラウザー タブに表示されるページ タイトル。 ページ タイトルは SEO とインデックス作成に使用されます。そのため、必要な場合を使用しない限り、タイトルを変更する必要はありません (ドキュメントが公開される前に、これはそれほど重要ではありません)。
   * **description**: 記事のコンテンツの簡単な説明を記述します。SEO と検出が向上します。
   * **author**: ページのプライマリ所有者である場合は、GitHub エイリアスをここに追加します。
   * **ms.author**: ページのプライマリ所有者である場合は、ここに Microsoft エイリアスを追加します (@microsoft.com は不要で、エイリアスだけです)。
   * **ms.date**: ページに主要なコンテンツを追加する場合は日付を更新しますが、説明、書式設定、文章校正、スペルチェックのような修正には更新しない。
   * **keywords**: Keywords aid in SEO (search engine optimization). 記事に固有のキーワードをコンマとスペースで区切って追加しますが、リスト内の最後のキーワードの後に句読点を追加する必要はありません。 すべての記事に適用されるグローバル キーワードを追加する必要は、他の場所で管理されます。 
   
5. 記事の編集が完了したら、下にスクロールして [ファイル変更の提案] **を選択します**。

6. 次のページで、[プル要求の作成] **を** 選択して、自動的に作成された分岐を 'master' にマージします。

7. 次に編集する記事について、上記の手順を繰り返します。

## 既存の記事の名前の変更または削除

変更によって既存の記事の名前を変更または削除する場合は、必ずリダイレクトを追加してください。 この方法では、既存の記事へのリンクを持つユーザーは、正しい場所に引き続き表示されます。 リダイレクトは、repo のルート.openpublishing.redirection.js上のユーザーによって管理されます。

リダイレクトをオンに.openpublishing.redirection.js、配列にエントリを追加 `redirections` します。

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- 削除 `source_path` する古い記事への相対リポジトリ パスです。 パスの始まりと終 `mixed-reality-docs` わりが次のパスで始まるか確認してください `.md` 。

- これは `redirect_url` 、古い記事から新しい記事への相対パブリック URL です。 この **URL** には、リポジトリ パスではなくパブリック URL を参照する URL が含まれているか、含 `mixed-reality-docs` `.md` まれている必要があります。 新しい記事内のセクションへのリンクは `#section` 使用できます。 必要に応じて、別のサイトへの絶対パスを使用できます。

- `redirect_document_id` は、前のファイルのドキュメント ID を保持するかどうかを示します。 既定値は次の値です `false` 。 リダイレクト `true` された記事の属性値 `ms.documentid` を保持する場合に使用します。 ドキュメント ID を保持すると、ページ ビューやランク付けなどのデータが対象の記事に転送されます。 リダイレクトが主に名前の変更であり、同じコンテンツの一部のみをカバーする別の記事へのポインターではない場合は、これを行います。

リダイレクトを追加する場合は、必ず古いファイルも削除してください。

## 新しい記事の作成

以下のワークフローを使用して *、Web* ブラウザーの GitHub を介してドキュメント リポジトリに新しい記事を作成します。

1. MicrosoftDocs/mixed-Reality 'master' 分岐からフォークを作成します (上部 **の [フォーク** ] ボタンを使用)。

   ![マスター分岐をフォークします。](images/forkbranch.png)
   
2. "mixed-reality-docs" フォルダーで、上部にある [新しい **ファイル** の作成] を選択します。

3. 記事のページ名を作成し (スペースではなくハイフンを使用し、句読点やアポストロフィを使用しない)、".md" を追加します。

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

5. 上記のセクションの指示に従って、関連するメタデータ フィールド [を入力します](#editing-an-existing-article)。

6. Markdown の基本を使用 [して記事のコンテンツを記述します](#markdown-basics)。

7. 記事の `## See also` 下部にセクションを追加し、関連する他の記事へのリンクを追加します。

8. 完了したら、[新しいファイルの **コミット] を選択します**。

9. [ **新しいプル要求** ] を選択し、フォークの 'master' 分岐を MicrosoftDocs/Mixed-Reality 'master' にマージします (矢印が正しい方向を指していることを確認してください)。

   ![フォークから MicrosoftDocs/mixed-Reality へのプル要求を作成する](images/pr-to-master.png)

## Markdown の基本

次のリソースは、Markdown 言語を使用してドキュメントを編集する方法を学習するのに役立ちます。

- [Markdown の基本](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Markdown を作成する方法に関するその他のdocs.microsoft.com](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### テーブルの追加

スタイル テーブルをdocs.microsoft.com、インライン CSS を試しても、罫線やカスタム スタイルを持つ必要がなされません。 これは短時間動作する場合に表示されますが、最終的にプラットフォームは表からスタイルを削除します。 そのため、前もって計画を立て、テーブルをシンプルにしてください。 [Markdown テーブルを簡単に使用できるサイトを次に示します](https://www.tablesgenerator.com/markdown_tables)。

ドキュメント [Markdown Extension for Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) では、ドキュメントの編集に Visual Studio コード (下記参照 [)](#using-visual-studio-code) を使用している場合でも、テーブルの生成が容易になります。

### 画像の追加

画像をレポの "mixed-reality-docs/images" フォルダーにアップロードし、記事で適切に参照する必要があります。 画像は自動的にフル サイズで表示されます。つまり、大きな画像は記事の幅全体を埋める必要があります。 画像をアップロードする前に、画像のサイズを事前に設定することをお勧めします。 推奨される幅は 600 ~ 700 ピクセルですが、スクリーンショットが濃い場合やスクリーンショットの一部である場合は、それぞれサイズを上げ下げする必要があります。

>[!IMPORTANT]
>マージする前に、フォークされたレポにのみ画像をアップロードできます。 そのため、記事に画像を追加する場合は、まず [Visual Studio Code](#using-visual-studio-code) を使用して、画像をフォークの "images" フォルダーに追加するか、Web ブラウザーで次の手順を実行する必要があります。
>
>1. MicrosoftDocs/mixed-Reality レポをフォークしました。
>2. フォーク内の記事を編集しました。
>3. 記事で参照している画像をフォークの "mixed-reality-docs/images" フォルダーにアップロードしました。
>4. フォークを**** MicrosoftDocs/mixed-Reality 'master' 分岐にマージするプル要求を作成しました。
>
>フォークされた独自のレポを設定する方法については、新しい記事を作成する手順 [に従ってください](#creating-a-new-article)。

## 作業のプレビュー

GitHub で Web ブラウザーを使用して編集している間**** は、コミットする前にページの上部にある [プレビュー] タブを選択して作業をプレビューできます。 

>[!NOTE]
>ユーザーの変更をプレビューreview.docs.microsoft.com Microsoft の従業員だけが利用できます。

Microsoft の従業員: 投稿が 'master' ブランチにマージされた後、公開前にコンテンツを確認できます https://review.docs.microsoft.com/hololens?branch=master 。 左側の列の目次を使用して記事を見つける。

## ブラウザーでの編集とデスクトップ クライアントでの編集

ブラウザーでの編集は、簡単に変更を加える最も簡単な方法ですが、いくつかの欠点があります。

- スペル チェックを受け取らない。
- 他の記事へのスマート リンクは取得できません (記事のファイル名を手動で入力する必要があります)。
- 画像をアップロードして参照すると面倒な場合があります。

これらの問題に対処しない場合は、Visual Studio [Code](https://code.visualstudio.com/) のようなデスクトップ クライアントを使用して、貢献する際に役立つ拡張機能を [2](#useful-extensions) つ追加します。

## コードVisual Studio使用する

上記の理由から、Web[](#editing-in-the-browser-vs-editing-with-a-desktop-client)ブラウザーではなく、デスクトップ クライアントを使用してドキュメントを編集することもできます。 コードを使用することをお [Visual Studioします](https://code.visualstudio.com/)。

### セットアップ

次の手順に従って、このVisual Studioを使用するためのコードを構成します。

1. Web ブラウザーの場合:
    1. お [使いの PC 用に Git をインストールします](https://git-scm.com/downloads)。
    2. コード [Visual Studioインストールします](https://code.visualstudio.com/)。
    3. [Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.
    4. フォークで、URL を複製または **ダウンロードして** コピーします。
2. 次のコードを使用して、フォークのローカル 複製Visual Studioします。
    1. [表示] **メニューの** [コマンド パレット] **を選択します**。
    2. 「Git: Clone」と入力します。
    3. コピーした URL を貼り付けます。
    4. PC で複製を保存する場所を選択します。
    5. ポップアップ **で [開く** ] を選択します。

### ドキュメントの編集

以下のワークフローを使用して、コードを使用してドキュメントをVisual Studioします。

>[!NOTE]
>上記の記事の [編集](#editing-an-existing-article) と [作成](#creating-a-new-article) に関するガイダンス、 [および Markdown](#markdown-basics)の編集の基本はすべて、このコードを使用する場合にもVisual Studio適用されます。

1. 複製されたフォークが公式リポジトリで最新の情報を得たか確認します。

   1. Web ブラウザーで、MicrosoftDocs/Mixed-Reality 'master' の他の投稿者からの最近の変更をフォークに同期するプル要求を作成します (矢印が正しい方向を指しているか確認してください)。
      
      ![MicrosoftDocs/mixed-Reality からフォークへの変更を同期する](images/sync-repos.png)
      
   2. [Visual Studioコード] で、同期ボタンを選択して、新しく更新したフォークをローカル複製に同期します。
      
      ![同期ボタンの画像をクリックする](images/sync-clone.png)
      
2. 複製されたリポジトリの記事を作成または編集するには、次のコードVisual Studioします。

   1. 1 つ以上の記事を編集します (必要に応じて、イメージを "images" フォルダーに追加します)。
   
   2. **エクスプローラーで** 変更を **保存します**。
      
      ![エクスプローラーで [すべて保存] を選択する](images/explorer-save.png)
      
   3. **ソース管理のすべての** 変更を **コミット** します (メッセージが表示されたらコミット メッセージを書き込む)。
      
   4. 同期ボタン **を選択** して、変更内容を元の状態 (GitHub のフォーク) に同期します。
      
      ![[同期] ボタンをクリックする](images/sync-back.png)
      
3. Web ブラウザーで、フォークの新しい変更を MicrosoftDocs/mixed-Reality 'master' に同期するプル要求を作成します (矢印が正しい方向を指していることを確認してください)。

   ![フォークから MicrosoftDocs/mixed-Reality へのプル要求を作成する](images/pr-to-master.png)

### 便利な拡張機能

ドキュメントを編集Visual Studioコード拡張機能は、次の方法で役立ちます。

- [Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Alt + **M** を使用して、次のようなドキュメント作成オプションのメニューを表示します。
   - アップロードした画像を検索して参照します。
   - リスト、表、ドキュメント固有のコールアウトなど、書式設定を追加します `>[!NOTE]` 。
   - 内部リンクとブックマーク (ページ内の特定のセクションへのリンク) を検索して参照します。
   - 書式設定エラーが強調表示されます (詳細を確認するには、エラーの上にマウス ポインターを移動します)。
- [コードスペル チェック](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - スペル ミスの単語に下線が引きされます。スペル ミスの単語を右クリックして変更するか、辞書に保存します。
