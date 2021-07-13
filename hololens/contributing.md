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
# <a name="contributing-to-the-hololens-documentation"></a><span data-ttu-id="e5e5f-103">ドキュメントへのHoloLensする</span><span class="sxs-lookup"><span data-stu-id="e5e5f-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="e5e5f-104">ドキュメントへようこそHoloLens[してください](https://github.com/MicrosoftDocs/Hololens)。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="e5e5f-105">このレポポで作成または編集した記事は **、一般に公開されます。**</span><span class="sxs-lookup"><span data-stu-id="e5e5f-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="e5e5f-106">HoloLensドキュメントは、Markdig 機能と docs.microsoft.com された Markdown を使用GitHubプラットフォームに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="e5e5f-107">このレポジトで編集するコンテンツは、/hololens に表示されるスタイル化されたページに書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-107">The content you edit in this repo gets formatted into stylized pages that show up at /hololens.</span></span>

<span data-ttu-id="e5e5f-108">このページでは、Markdown の基本への貢献とリンクに関する基本的な手順とガイドラインについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="e5e5f-109">ご投稿いただきありがとうございます。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-109">Thanks for your contribution!</span></span>

## <a name="available-repos"></a><span data-ttu-id="e5e5f-110">使用可能なリポジトリ</span><span class="sxs-lookup"><span data-stu-id="e5e5f-110">Available repos</span></span>

| <span data-ttu-id="e5e5f-111">リポジトリ名です</span><span class="sxs-lookup"><span data-stu-id="e5e5f-111">Repository name</span></span> | <span data-ttu-id="e5e5f-112">[URL]</span><span class="sxs-lookup"><span data-stu-id="e5e5f-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="e5e5f-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="e5e5f-113">HoloLens</span></span> | [<span data-ttu-id="e5e5f-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="e5e5f-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="e5e5f-115">Mixed Reality</span><span class="sxs-lookup"><span data-stu-id="e5e5f-115">Mixed Reality</span></span> | [<span data-ttu-id="e5e5f-116">MicrosoftDocs/Mixed-Reality</span><span class="sxs-lookup"><span data-stu-id="e5e5f-116">MicrosoftDocs/mixed-reality</span></span>](/windows/mixed-reality) |
| <span data-ttu-id="e5e5f-117">VR ファンズ ガイド</span><span class="sxs-lookup"><span data-stu-id="e5e5f-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="e5e5f-118">MicrosoftDocs/Mixed-Reality/ファンズガイド</span><span class="sxs-lookup"><span data-stu-id="e5e5f-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a><span data-ttu-id="e5e5f-119">開始する前に</span><span class="sxs-lookup"><span data-stu-id="e5e5f-119">Before you start</span></span>

<span data-ttu-id="e5e5f-120">アカウント をまだ作成していない場合は、アカウント を[作成GitHubがあります](https://github.com/join)。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="e5e5f-121">Microsoft の従業員の場合は、Microsoft オープン ソース ポータルGitHubアカウントを Microsoft エイリアス[にリンクします](https://repos.opensource.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="e5e5f-122">**"Microsoft" および** **"MicrosoftDocs" 組織に参加** します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="e5e5f-123">お使GitHubアカウントを設定する場合は、次のセキュリティ上の注意事項も推奨されます。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="e5e5f-124">自分の[アカウント の強力なパスワードをGitHubします](https://github.com/settings/admin)。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="e5e5f-125">2 [要素認証 を有効にします](https://github.com/settings/two_factor_authentication/configure)。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="e5e5f-126">回復コード [を安全な](https://github.com/settings/auth/recovery-codes) 場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="e5e5f-127">パブリック プロファイルの [設定を更新します](https://github.com/settings/profile)。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="e5e5f-128">自分の名前を設定し、[パブリック *メール]* を [自分のメール アドレスを表示しない *] に設定します*。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="e5e5f-129">投稿するドキュメント ページにサムネイルが表示されるので、プロファイル画像をアップロードすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="e5e5f-130">コマンド ラインを使用する予定の場合は、 に対して Git 資格情報マネージャー[を設定Windows。](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)</span><span class="sxs-lookup"><span data-stu-id="e5e5f-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="e5e5f-131">そうすることで、投稿を行うたびパスワードを入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="e5e5f-132">発行システムは、公開システムGitHub関連付けられているので、これらの手順が重要です。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="e5e5f-133">自分のエイリアスを使用して、各記事の作成者または共同作成者GitHubされます。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <a name="editing-an-existing-article"></a><span data-ttu-id="e5e5f-134">既存の記事の編集</span><span class="sxs-lookup"><span data-stu-id="e5e5f-134">Editing an existing article</span></span>

<span data-ttu-id="e5e5f-135">次のワークフローを使用して、Webブラウザーで GitHubを更新します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="e5e5f-136">"mixed-reality-docs" フォルダーで編集する記事に移動します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="e5e5f-137">右上にある編集ボタン (鉛筆アイコン) を選択すると、"master" ブランチから使い捨て可能なブランチが自動的にフォークされます。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![記事を編集します。](images/editpage.png)
   
3. <span data-ttu-id="e5e5f-139">"Markdown の基本" に従って、 [記事の内容を編集します](#markdown-basics)。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="e5e5f-140">各記事の上部にあるメタデータを更新します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="e5e5f-141">**title**: 記事を表示するときにブラウザー タブに表示されるページ タイトル。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="e5e5f-142">ページ タイトルは SEO とインデックス作成に使用されます。そのため、必要な場合を限り、タイトルを変更する必要はありません (ドキュメントが公開される前はそれほど重要ではありません)。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="e5e5f-143">**description**: 記事の内容の簡単な説明を記述します。この内容は SEO と検出を向上します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="e5e5f-144">**author:** ページのプライマリ所有者である場合は、ここに自分のエイリアスGitHub追加します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="e5e5f-145">**ms.author:** ページのプライマリ所有者である場合は、ここに Microsoft エイリアスを追加します (エイリアスは @microsoft.com 不要です)。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="e5e5f-146">**ms.date:** ページに主要なコンテンツを追加する場合は日付を更新しますが、明確化、書式設定、文法、スペルの修正は行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="e5e5f-147">**keywords**: キーワードは、SEO (検索エンジンの最適化) を支援します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="e5e5f-148">記事に固有のコンマとスペースで区切られたキーワードを追加しますが、リスト内の最後のキーワードの後に句読点はありません。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="e5e5f-149">すべての記事に適用されるグローバル キーワードは、他の場所で管理されているので、追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="e5e5f-150">記事の編集が完了したら、下にスクロールし、[ファイル変更の提案] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="e5e5f-151">次のページで[作成] **を選択pull request** 自動的に作成されたブランチを 'master' にマージします。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="e5e5f-152">編集する次の記事について、上記の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-152">Repeat the steps above for the next article you want to edit.</span></span>

## <a name="renaming-or-deleting-an-existing-article"></a><span data-ttu-id="e5e5f-153">既存の記事の名前変更または削除</span><span class="sxs-lookup"><span data-stu-id="e5e5f-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="e5e5f-154">変更によって既存の記事の名前が変更または削除される場合は、必ずリダイレクトを追加してください。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="e5e5f-155">そうすることで、既存の記事へのリンクを持つユーザーは、依然として適切な場所に配置されます。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="e5e5f-156">リダイレクトは、repo のルート.openpublishing.redirection.json ファイルで管理されます。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="e5e5f-157">オンにリダイレクトを追加.openpublishing.redirection.js、配列にエントリを追加 `redirections` します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="e5e5f-158">は `source_path` 、削除する古い記事への相対リポジトリ パスです。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="e5e5f-159">パスが で始まり、 `mixed-reality-docs` で終わる必要があります `.md` 。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="e5e5f-160">は `redirect_url` 、古い記事から新しい記事への相対パブリック URL です。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="e5e5f-161">この URL は、リポジトリ **パスではなく** パブリック URL を参照しますので、 または `mixed-reality-docs` を含 `.md` めずにしてください。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="e5e5f-162">を使用して、新しい記事内のセクション `#section` にリンクできます。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="e5e5f-163">必要に応じて、ここで別のサイトへの絶対パスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-163">You can also use an absolute path to another site here, if necessary.</span></span>

- <span data-ttu-id="e5e5f-164">`redirect_document_id` は、前のファイルのドキュメント ID を保持するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-164">`redirect_document_id` indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="e5e5f-165">既定では、 `false`です。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-165">The default is `false`.</span></span> <span data-ttu-id="e5e5f-166">リダイレクト `true` された記事の属性値を `ms.documentid` 保持する場合は、 を使用します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="e5e5f-167">ドキュメント ID を保持すると、ページ ビューやランク付けなどのデータがターゲット記事に転送されます。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="e5e5f-168">これは、リダイレクトが主に名前変更であり、同じコンテンツの一部のみを対象とする別の記事へのポインターではない場合に行います。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="e5e5f-169">リダイレクトを追加する場合は、必ず古いファイルも削除してください。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <a name="creating-a-new-article"></a><span data-ttu-id="e5e5f-170">新しい記事の作成</span><span class="sxs-lookup"><span data-stu-id="e5e5f-170">Creating a new article</span></span>

<span data-ttu-id="e5e5f-171">次のワークフローを使用して *、Web* ブラウザーでレポートを使用してドキュメント GitHub新しい記事を作成します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="e5e5f-172">MicrosoftDocs/Mixed-Reality 'master' ブランチからフォークを作成します (上部の [ **フォーク** ] ボタンを使用)。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![マスター ブランチをフォークします。](images/forkbranch.png)
   
2. <span data-ttu-id="e5e5f-174">"mixed-reality-docs" フォルダーで、上部の **[新しいファイルの** 作成] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="e5e5f-175">記事のページ名を作成し (スペースではなくハイフンを使用し、句読点やアポストロフィを使用しない)、".md" を追加します</span><span class="sxs-lookup"><span data-stu-id="e5e5f-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![新しいページに名前を付け、](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="e5e5f-177">"mixed-reality-docs" フォルダー内から新しい記事を作成してください。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="e5e5f-178">これを確認するには、新しいファイル名行で "/mixed-reality-docs/" を確認します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="e5e5f-179">新しいページの上部に、次のメタデータ ブロックを追加します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="e5e5f-180">上記のセクションの手順に従って、関連するメタデータ フィールド [を入力します](#editing-an-existing-article)。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="e5e5f-181">Markdown の基本 を使用 [して記事のコンテンツを書き込む](#markdown-basics)。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="e5e5f-182">他の `## See also` 関連記事へのリンクを含むセクションを記事の下部に追加します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="e5e5f-183">完了したら、[新しいファイルを **コミットする] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="e5e5f-184">**[新しい** pull request] を選択し、フォークの 'master' ブランチを MicrosoftDocs/Mixed-Reality 'master' にマージします (矢印が正しい方法を指していることを確認してください)。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![フォークpull request MicrosoftDocs/Mixed-Reality にアプリを作成する](images/pr-to-master.png)

## <a name="markdown-basics"></a><span data-ttu-id="e5e5f-186">Markdown の基本</span><span class="sxs-lookup"><span data-stu-id="e5e5f-186">Markdown basics</span></span>

<span data-ttu-id="e5e5f-187">次のリソースは、Markdown 言語を使用してドキュメントを編集する方法を学習するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="e5e5f-188">Markdown の基礎</span><span class="sxs-lookup"><span data-stu-id="e5e5f-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="e5e5f-189">Markdown for docs.microsoft.com の記述に関するその他の docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e5e5f-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a><span data-ttu-id="e5e5f-190">テーブルの追加</span><span class="sxs-lookup"><span data-stu-id="e5e5f-190">Adding tables</span></span>

<span data-ttu-id="e5e5f-191">スタイル テーブルの docs.microsoft.com 方法のため、インライン CSS を試しても、罫線やカスタム スタイルは含め "されません"。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="e5e5f-192">これは短時間動作する可能性がありますが、最終的にプラットフォームによってスタイル設定がテーブルから取り除かれます。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="e5e5f-193">そのため、先に計画を立て、テーブルをシンプルに保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="e5e5f-194">[Markdown テーブルを簡単にするサイトを次に示します](https://www.tablesgenerator.com/markdown_tables)。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="e5e5f-195">ドキュメント[の編集に](/teamblog/docs-extension)Visual Studio Code Docs Markdown 拡張機能を使用している場合は、Visual Studio Code Markdown 拡張機能を使用すると、テーブル[の](#using-visual-studio-code)生成も簡単になります。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-195">The [Docs Markdown Extension for Visual Studio Code](/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <a name="adding-images"></a><span data-ttu-id="e5e5f-196">イメージの追加</span><span class="sxs-lookup"><span data-stu-id="e5e5f-196">Adding images</span></span>

<span data-ttu-id="e5e5f-197">イメージをレポポの "mixed-reality-docs/images" フォルダーにアップロードし、記事で適切に参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="e5e5f-198">画像はフルサイズで自動的に表示されます。これは、大きな画像が記事の幅全体を埋めるという意味です。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="e5e5f-199">画像をアップロードする前に、事前にサイズを設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="e5e5f-200">推奨される幅は 600 から 700 ピクセルですが、高密度のスクリーンショットまたはスクリーンショットの一部である場合は、サイズを上下に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="e5e5f-201">マージする前に、フォークされたレポポに画像のみをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="e5e5f-202">そのため、記事に画像を追加する予定の場合は[、Visual Studio Code](#using-visual-studio-code)を使用して、最初にフォークの "images" フォルダーに画像を追加するか、Web ブラウザーで次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="e5e5f-203">MicrosoftDocs/Mixed-Reality レポポをフォークしました。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="e5e5f-204">フォーク内の記事を編集しました。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="e5e5f-205">記事で参照している画像をフォークの "mixed-reality-docs/images" フォルダーにアップロードしました。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="e5e5f-206">フォークをmicrosoftDocs/mixed-reality 'master' ブランチにマージpull requestを作成しました。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="e5e5f-207">独自のフォークされたレポポを設定する方法については、新しい記事 を作成する [手順に従ってください](#creating-a-new-article)。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <a name="previewing-your-work"></a><span data-ttu-id="e5e5f-208">作業のプレビュー</span><span class="sxs-lookup"><span data-stu-id="e5e5f-208">Previewing your work</span></span>

<span data-ttu-id="e5e5f-209">Web ブラウザーをGitHubで編集する場合は、ページの上部付近にある[プレビュー] タブを選択して、コミット前に作業をプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="e5e5f-210">変更のプレビューはreview.docs.microsoft.com Microsoft の従業員だけが利用できます</span><span class="sxs-lookup"><span data-stu-id="e5e5f-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="e5e5f-211">Microsoft の従業員: 投稿が 'master' ブランチにマージされた後、</hololens?branch=master> で公開される前にコンテンツを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at </hololens?branch=master>.</span></span> <span data-ttu-id="e5e5f-212">左側の列の目次を使用して、記事を見つける。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-212">Find your article using the table of contents in the left column.</span></span>

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a><span data-ttu-id="e5e5f-213">ブラウザーでの編集とデスクトップ クライアントでの編集</span><span class="sxs-lookup"><span data-stu-id="e5e5f-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="e5e5f-214">ブラウザーでの編集は、簡単に変更を加える最も簡単な方法ですが、いくつかの欠点があります。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="e5e5f-215">スペル チェックは受け取らない。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-215">You don't get spell-check.</span></span>
- <span data-ttu-id="e5e5f-216">他の記事へのスマート リンクは取得できません (記事のファイル名を手動で入力する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="e5e5f-217">画像をアップロードして参照するのも面倒な場合があります。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="e5e5f-218">これらの問題に対処しない場合は、Visual Studio Code のようなデスクトップ クライアントを使用して、[](https://code.visualstudio.com/)貢献するときに役立つ拡張機能を[](#useful-extensions)2 つ追加します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <a name="using-visual-studio-code"></a><span data-ttu-id="e5e5f-219">Visual Studio Code の使用</span><span class="sxs-lookup"><span data-stu-id="e5e5f-219">Using Visual Studio Code</span></span>

<span data-ttu-id="e5e5f-220">上記の理由 [から、Web](#editing-in-the-browser-vs-editing-with-a-desktop-client)ブラウザーではなく、デスクトップ クライアントを使用してドキュメントを編集することができます。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="e5e5f-221">[Visual Studio Code](https://code.visualstudio.com/) を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <a name="setup"></a><span data-ttu-id="e5e5f-222">セットアップ</span><span class="sxs-lookup"><span data-stu-id="e5e5f-222">Setup</span></span>

<span data-ttu-id="e5e5f-223">次の手順に従って、このVisual Studio Codeを使用するための構成を構成します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="e5e5f-224">Web ブラウザーで:</span><span class="sxs-lookup"><span data-stu-id="e5e5f-224">In a web browser:</span></span>
    1. <span data-ttu-id="e5e5f-225">お使 [いの PC 用に Git をインストールします](https://git-scm.com/downloads)。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="e5e5f-226">[Visual Studio Code](https://code.visualstudio.com/) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="e5e5f-227">[まだ行っていない場合は、MicrosoftDocs/Mixed-Reality](#creating-a-new-article) をフォークします。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="e5e5f-228">フォークで、[複製] または **[ダウンロード] を選択し、URL** をコピーします。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="e5e5f-229">次の方法でフォークのローカル クローンを作成Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="e5e5f-230">[表示] **メニューの** [コマンド パレット] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="e5e5f-231">「Git: Clone」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="e5e5f-232">コピーした URL を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="e5e5f-233">複製を PC に保存する場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="e5e5f-234">ポップアップ **で [Open repo]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-234">Select **Open repo** in the pop-up.</span></span>

### <a name="editing-documentation"></a><span data-ttu-id="e5e5f-235">ドキュメントの編集</span><span class="sxs-lookup"><span data-stu-id="e5e5f-235">Editing documentation</span></span>

<span data-ttu-id="e5e5f-236">次のワークフローを使用して、 を使用してドキュメントを変更Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="e5e5f-237">記事の編集と[作成に](#editing-an-existing-article)関するガイダンス、および[上記の Markdown](#markdown-basics)の編集の基本は、この記事を使用する場合Visual Studio Code適用されます。 [](#creating-a-new-article)</span><span class="sxs-lookup"><span data-stu-id="e5e5f-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="e5e5f-238">複製したフォークが公式リポジトリで最新の情報に更新されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="e5e5f-239">Web ブラウザーで、MicrosoftDocs/Mixed-Reality 'master' の他の共同作成者からの最近の変更をフォークに同期する pull request を作成します (矢印が正しい方法を指している必要があります)。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![MicrosoftDocs/Mixed-Reality からフォークへの変更の同期](images/sync-repos.png)
      
   2. <span data-ttu-id="e5e5f-241">[Visual Studio Code同期] ボタンを選択して、新しく更新されたフォークをローカル クローンに同期します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![同期ボタンの画像をクリックします](images/sync-clone.png)
      
2. <span data-ttu-id="e5e5f-243">複製したリポジトリ内の記事を作成または編集するには、 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="e5e5f-244">1 つ以上の記事を編集します (必要に応じて、画像を "images" フォルダーに追加します)。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="e5e5f-245">**エクスプローラーに** 変更を **保存します**。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-245">**Save** changes in **Explorer**.</span></span>
      
      ![エクスプローラーで [すべて保存] を選択する](images/explorer-save.png)
      
   3. <span data-ttu-id="e5e5f-247">**ソース管理のすべての** 変更を **コミットします** (メッセージが表示されたら、コミット メッセージを書き込む)。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![ソース管理で [すべてコミット] を選択する](images/source-control-commit.png)
      
   4. <span data-ttu-id="e5e5f-249">同期ボタン **を選択** して、変更内容を元の元に戻します (GitHub。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![[同期] ボタンをクリックします](images/sync-back.png)
      
3. <span data-ttu-id="e5e5f-251">Web ブラウザーで、フォークの新しい変更を MicrosoftDocs/Mixed-Reality 'master' に同期する pull request を作成します (矢印が正しい方法を指していることを確認してください)。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![フォークpull request MicrosoftDocs/Mixed-Reality にアプリを作成する](images/pr-to-master.png)

### <a name="useful-extensions"></a><span data-ttu-id="e5e5f-253">便利な拡張機能</span><span class="sxs-lookup"><span data-stu-id="e5e5f-253">Useful extensions</span></span>

<span data-ttu-id="e5e5f-254">次のVisual Studio Codeは、ドキュメントを編集するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="e5e5f-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - **Alt + M** を使用して、次のようなドキュメント作成オプションのメニューを表示します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="e5e5f-256">アップロードした画像を検索して参照します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="e5e5f-257">リスト、テーブル、ドキュメント固有の呼び出し (など) のような書式設定を追加します `>[!NOTE]` 。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="e5e5f-258">内部リンクとブックマーク (ページ内の特定のセクションへのリンク) を検索して参照します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="e5e5f-259">書式設定エラーが強調表示されています (詳細については、エラーの上にマウス ポインターを合わせる)。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="e5e5f-260">[コード スペル チェック](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - スペルミスの単語には下線が引かされます。スペルミスの単語を右クリックして変更するか、ディクショナリに保存します。</span><span class="sxs-lookup"><span data-stu-id="e5e5f-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
