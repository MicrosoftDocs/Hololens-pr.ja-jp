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
# <span data-ttu-id="95cf8-103">HoloLens ドキュメントへの貢献</span><span class="sxs-lookup"><span data-stu-id="95cf8-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="95cf8-104">[HoloLens ドキュメントへようこそ](https://github.com/MicrosoftDocs/Hololens)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="95cf8-105">このレポで作成または編集した記事は **、一般のユーザーに表示されます。**</span><span class="sxs-lookup"><span data-stu-id="95cf8-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="95cf8-106">HoloLens のドキュメントは、GitHub docs.microsoft.com Markdig 機能を備えた Markdown を使用する新しいプラットフォームに表示されます。</span><span class="sxs-lookup"><span data-stu-id="95cf8-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="95cf8-107">このレポで編集するコンテンツは、表示されるスタイル化されたページに書式設定されます https://docs.microsoft.com/hololens 。</span><span class="sxs-lookup"><span data-stu-id="95cf8-107">The content you edit in this repo gets formatted into stylized pages that show up at https://docs.microsoft.com/hololens.</span></span> 

<span data-ttu-id="95cf8-108">このページでは、Markdown に関する基本的な手順とガイドライン、および Markdown の基本へのリンクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="95cf8-109">ご投稿いただきありがとうございます。</span><span class="sxs-lookup"><span data-stu-id="95cf8-109">Thanks for your contribution!</span></span>

## <span data-ttu-id="95cf8-110">利用可能なリポジトリ</span><span class="sxs-lookup"><span data-stu-id="95cf8-110">Available repos</span></span>

| <span data-ttu-id="95cf8-111">リポジトリ名</span><span class="sxs-lookup"><span data-stu-id="95cf8-111">Repository name</span></span> | <span data-ttu-id="95cf8-112">URL</span><span class="sxs-lookup"><span data-stu-id="95cf8-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="95cf8-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="95cf8-113">HoloLens</span></span> | [<span data-ttu-id="95cf8-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="95cf8-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="95cf8-115">Mixed Reality</span><span class="sxs-lookup"><span data-stu-id="95cf8-115">Mixed Reality</span></span> | [<span data-ttu-id="95cf8-116">MicrosoftDocs/mixed-Reality</span><span class="sxs-lookup"><span data-stu-id="95cf8-116">MicrosoftDocs/mixed-reality</span></span>](https://docs.microsoft.com/windows/mixed-reality) |
| <span data-ttu-id="95cf8-117">VR ファンズ ガイド</span><span class="sxs-lookup"><span data-stu-id="95cf8-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="95cf8-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span><span class="sxs-lookup"><span data-stu-id="95cf8-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <span data-ttu-id="95cf8-119">開始する前に</span><span class="sxs-lookup"><span data-stu-id="95cf8-119">Before you start</span></span>

<span data-ttu-id="95cf8-120">まだ持ってない場合は [、GitHub アカウントを作成する必要があります](https://github.com/join)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="95cf8-121">Microsoft の従業員の場合は、Microsoft オープン ソース ポータルで GitHub アカウントを Microsoft エイリアス [にリンクします](https://repos.opensource.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="95cf8-122">**"Microsoft" 組織と** **"MicrosoftDocs" 組織に参加**します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="95cf8-123">GitHub アカウントをセットアップする場合は、次のセキュリティ上の予防措置も推奨されます。</span><span class="sxs-lookup"><span data-stu-id="95cf8-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="95cf8-124">[GitHub アカウントの強力なパスワードを作成します](https://github.com/settings/admin)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="95cf8-125">2 [要素認証を有効にします](https://github.com/settings/two_factor_authentication/configure)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="95cf8-126">回復コード [を安全な場所](https://github.com/settings/auth/recovery-codes) に保存します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="95cf8-127">パブリック プロファイルの [設定を更新します](https://github.com/settings/profile)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="95cf8-128">名前を設定し、パブリック メール *にメール* アドレスを表示 *しない設定を検討してください*。</span><span class="sxs-lookup"><span data-stu-id="95cf8-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="95cf8-129">投稿するドキュメント ページにサムネイルが表示される場合は、プロファイル画像をアップロードすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="95cf8-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="95cf8-130">コマンド ラインを使用する場合は、Windows 用 [の Git Credential Manager のセットアップを検討してください](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="95cf8-131">そうすることで、投稿の度にパスワードを入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="95cf8-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="95cf8-132">発行システムは GitHub に関連付けられているので、次の手順が重要です。</span><span class="sxs-lookup"><span data-stu-id="95cf8-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="95cf8-133">GitHub エイリアスを使用して、各記事の作成者または投稿者として一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="95cf8-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <span data-ttu-id="95cf8-134">既存の記事の編集</span><span class="sxs-lookup"><span data-stu-id="95cf8-134">Editing an existing article</span></span>

<span data-ttu-id="95cf8-135">次のワークフローを使用して、Web\*\* ブラウザーで GitHub 経由で既存の記事を更新します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="95cf8-136">編集する記事に移動し、"mixed-reality-docs" フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="95cf8-137">右上にある編集ボタン (鉛筆アイコン) を選択します。このボタンをクリックすると、"master" 分岐の分岐が自動的に分岐します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![記事を編集します。](images/editpage.png)
   
3. <span data-ttu-id="95cf8-139">「Markdown の基本」に従って記事 [の内容を編集します](#markdown-basics)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="95cf8-140">各記事の上部にあるメタデータを更新します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="95cf8-141">**title**: 記事が表示されているときにブラウザー タブに表示されるページ タイトル。</span><span class="sxs-lookup"><span data-stu-id="95cf8-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="95cf8-142">ページ タイトルは SEO とインデックス作成に使用されます。そのため、必要な場合を使用しない限り、タイトルを変更する必要はありません (ドキュメントが公開される前に、これはそれほど重要ではありません)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="95cf8-143">**description**: 記事のコンテンツの簡単な説明を記述します。SEO と検出が向上します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="95cf8-144">**author**: ページのプライマリ所有者である場合は、GitHub エイリアスをここに追加します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="95cf8-145">**ms.author**: ページのプライマリ所有者である場合は、ここに Microsoft エイリアスを追加します (@microsoft.com は不要で、エイリアスだけです)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="95cf8-146">**ms.date**: ページに主要なコンテンツを追加する場合は日付を更新しますが、説明、書式設定、文章校正、スペルチェックのような修正には更新しない。</span><span class="sxs-lookup"><span data-stu-id="95cf8-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="95cf8-147">**keywords**: Keywords aid in SEO (search engine optimization).</span><span class="sxs-lookup"><span data-stu-id="95cf8-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="95cf8-148">記事に固有のキーワードをコンマとスペースで区切って追加しますが、リスト内の最後のキーワードの後に句読点を追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="95cf8-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="95cf8-149">すべての記事に適用されるグローバル キーワードを追加する必要は、他の場所で管理されます。</span><span class="sxs-lookup"><span data-stu-id="95cf8-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="95cf8-150">記事の編集が完了したら、下にスクロールして [ファイル変更の提案] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="95cf8-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="95cf8-151">次のページで、[プル要求の作成] **を** 選択して、自動的に作成された分岐を 'master' にマージします。</span><span class="sxs-lookup"><span data-stu-id="95cf8-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="95cf8-152">次に編集する記事について、上記の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-152">Repeat the steps above for the next article you want to edit.</span></span>

## <span data-ttu-id="95cf8-153">既存の記事の名前の変更または削除</span><span class="sxs-lookup"><span data-stu-id="95cf8-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="95cf8-154">変更によって既存の記事の名前を変更または削除する場合は、必ずリダイレクトを追加してください。</span><span class="sxs-lookup"><span data-stu-id="95cf8-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="95cf8-155">この方法では、既存の記事へのリンクを持つユーザーは、正しい場所に引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="95cf8-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="95cf8-156">リダイレクトは、repo のルート.openpublishing.redirection.js上のユーザーによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="95cf8-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="95cf8-157">リダイレクトをオンに.openpublishing.redirection.js、配列にエントリを追加 `redirections` します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="95cf8-158">削除 `source_path` する古い記事への相対リポジトリ パスです。</span><span class="sxs-lookup"><span data-stu-id="95cf8-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="95cf8-159">パスの始まりと終 `mixed-reality-docs` わりが次のパスで始まるか確認してください `.md` 。</span><span class="sxs-lookup"><span data-stu-id="95cf8-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="95cf8-160">これは `redirect_url` 、古い記事から新しい記事への相対パブリック URL です。</span><span class="sxs-lookup"><span data-stu-id="95cf8-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="95cf8-161">この **URL** には、リポジトリ パスではなくパブリック URL を参照する URL が含まれているか、含 `mixed-reality-docs` `.md` まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="95cf8-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="95cf8-162">新しい記事内のセクションへのリンクは `#section` 使用できます。</span><span class="sxs-lookup"><span data-stu-id="95cf8-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="95cf8-163">必要に応じて、別のサイトへの絶対パスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="95cf8-163">You can also use an absolute path to another site here, if necessary.</span></span>

- `redirect_document_id` <span data-ttu-id="95cf8-164">は、前のファイルのドキュメント ID を保持するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-164">indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="95cf8-165">既定値は次の値です `false` 。</span><span class="sxs-lookup"><span data-stu-id="95cf8-165">The default is `false`.</span></span> <span data-ttu-id="95cf8-166">リダイレクト `true` された記事の属性値 `ms.documentid` を保持する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="95cf8-167">ドキュメント ID を保持すると、ページ ビューやランク付けなどのデータが対象の記事に転送されます。</span><span class="sxs-lookup"><span data-stu-id="95cf8-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="95cf8-168">リダイレクトが主に名前の変更であり、同じコンテンツの一部のみをカバーする別の記事へのポインターではない場合は、これを行います。</span><span class="sxs-lookup"><span data-stu-id="95cf8-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="95cf8-169">リダイレクトを追加する場合は、必ず古いファイルも削除してください。</span><span class="sxs-lookup"><span data-stu-id="95cf8-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <span data-ttu-id="95cf8-170">新しい記事の作成</span><span class="sxs-lookup"><span data-stu-id="95cf8-170">Creating a new article</span></span>

<span data-ttu-id="95cf8-171">以下のワークフローを使用して *、Web* ブラウザーの GitHub を介してドキュメント リポジトリに新しい記事を作成します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="95cf8-172">MicrosoftDocs/mixed-Reality 'master' 分岐からフォークを作成します (上部 **の [フォーク** ] ボタンを使用)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![マスター分岐をフォークします。](images/forkbranch.png)
   
2. <span data-ttu-id="95cf8-174">"mixed-reality-docs" フォルダーで、上部にある [新しい **ファイル** の作成] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="95cf8-175">記事のページ名を作成し (スペースではなくハイフンを使用し、句読点やアポストロフィを使用しない)、".md" を追加します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![新しいページに名前を付け、](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="95cf8-177">"mixed-reality-docs" フォルダー内から新しい記事を作成してください。</span><span class="sxs-lookup"><span data-stu-id="95cf8-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="95cf8-178">これを確認するには、新しいファイル名行で "/mixed-reality-docs/" を確認します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="95cf8-179">新しいページの上部に、次のメタデータ ブロックを追加します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="95cf8-180">上記のセクションの指示に従って、関連するメタデータ フィールド [を入力します](#editing-an-existing-article)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="95cf8-181">Markdown の基本を使用 [して記事のコンテンツを記述します](#markdown-basics)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="95cf8-182">記事の `## See also` 下部にセクションを追加し、関連する他の記事へのリンクを追加します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="95cf8-183">完了したら、[新しいファイルの **コミット] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="95cf8-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="95cf8-184">[ **新しいプル要求** ] を選択し、フォークの 'master' 分岐を MicrosoftDocs/Mixed-Reality 'master' にマージします (矢印が正しい方向を指していることを確認してください)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![フォークから MicrosoftDocs/mixed-Reality へのプル要求を作成する](images/pr-to-master.png)

## <span data-ttu-id="95cf8-186">Markdown の基本</span><span class="sxs-lookup"><span data-stu-id="95cf8-186">Markdown basics</span></span>

<span data-ttu-id="95cf8-187">次のリソースは、Markdown 言語を使用してドキュメントを編集する方法を学習するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="95cf8-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="95cf8-188">Markdown の基本</span><span class="sxs-lookup"><span data-stu-id="95cf8-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="95cf8-189">Markdown を作成する方法に関するその他のdocs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="95cf8-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <span data-ttu-id="95cf8-190">テーブルの追加</span><span class="sxs-lookup"><span data-stu-id="95cf8-190">Adding tables</span></span>

<span data-ttu-id="95cf8-191">スタイル テーブルをdocs.microsoft.com、インライン CSS を試しても、罫線やカスタム スタイルを持つ必要がなされません。</span><span class="sxs-lookup"><span data-stu-id="95cf8-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="95cf8-192">これは短時間動作する場合に表示されますが、最終的にプラットフォームは表からスタイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="95cf8-193">そのため、前もって計画を立て、テーブルをシンプルにしてください。</span><span class="sxs-lookup"><span data-stu-id="95cf8-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="95cf8-194">[Markdown テーブルを簡単に使用できるサイトを次に示します](https://www.tablesgenerator.com/markdown_tables)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="95cf8-195">ドキュメント [Markdown Extension for Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) では、ドキュメントの編集に Visual Studio コード (下記参照 [)](#using-visual-studio-code) を使用している場合でも、テーブルの生成が容易になります。</span><span class="sxs-lookup"><span data-stu-id="95cf8-195">The [Docs Markdown Extension for Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <span data-ttu-id="95cf8-196">画像の追加</span><span class="sxs-lookup"><span data-stu-id="95cf8-196">Adding images</span></span>

<span data-ttu-id="95cf8-197">画像をレポの "mixed-reality-docs/images" フォルダーにアップロードし、記事で適切に参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95cf8-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="95cf8-198">画像は自動的にフル サイズで表示されます。つまり、大きな画像は記事の幅全体を埋める必要があります。</span><span class="sxs-lookup"><span data-stu-id="95cf8-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="95cf8-199">画像をアップロードする前に、画像のサイズを事前に設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="95cf8-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="95cf8-200">推奨される幅は 600 ~ 700 ピクセルですが、スクリーンショットが濃い場合やスクリーンショットの一部である場合は、それぞれサイズを上げ下げする必要があります。</span><span class="sxs-lookup"><span data-stu-id="95cf8-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="95cf8-201">マージする前に、フォークされたレポにのみ画像をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="95cf8-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="95cf8-202">そのため、記事に画像を追加する場合は、まず [Visual Studio Code](#using-visual-studio-code) を使用して、画像をフォークの "images" フォルダーに追加するか、Web ブラウザーで次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95cf8-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="95cf8-203">MicrosoftDocs/mixed-Reality レポをフォークしました。</span><span class="sxs-lookup"><span data-stu-id="95cf8-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="95cf8-204">フォーク内の記事を編集しました。</span><span class="sxs-lookup"><span data-stu-id="95cf8-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="95cf8-205">記事で参照している画像をフォークの "mixed-reality-docs/images" フォルダーにアップロードしました。</span><span class="sxs-lookup"><span data-stu-id="95cf8-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="95cf8-206">フォークを\*\*\*\* MicrosoftDocs/mixed-Reality 'master' 分岐にマージするプル要求を作成しました。</span><span class="sxs-lookup"><span data-stu-id="95cf8-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="95cf8-207">フォークされた独自のレポを設定する方法については、新しい記事を作成する手順 [に従ってください](#creating-a-new-article)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <span data-ttu-id="95cf8-208">作業のプレビュー</span><span class="sxs-lookup"><span data-stu-id="95cf8-208">Previewing your work</span></span>

<span data-ttu-id="95cf8-209">GitHub で Web ブラウザーを使用して編集している間\*\*\*\* は、コミットする前にページの上部にある [プレビュー] タブを選択して作業をプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="95cf8-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="95cf8-210">ユーザーの変更をプレビューreview.docs.microsoft.com Microsoft の従業員だけが利用できます。</span><span class="sxs-lookup"><span data-stu-id="95cf8-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="95cf8-211">Microsoft の従業員: 投稿が 'master' ブランチにマージされた後、公開前にコンテンツを確認できます https://review.docs.microsoft.com/hololens?branch=master 。</span><span class="sxs-lookup"><span data-stu-id="95cf8-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at https://review.docs.microsoft.com/hololens?branch=master.</span></span> <span data-ttu-id="95cf8-212">左側の列の目次を使用して記事を見つける。</span><span class="sxs-lookup"><span data-stu-id="95cf8-212">Find your article using the table of contents in the left column.</span></span>

## <span data-ttu-id="95cf8-213">ブラウザーでの編集とデスクトップ クライアントでの編集</span><span class="sxs-lookup"><span data-stu-id="95cf8-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="95cf8-214">ブラウザーでの編集は、簡単に変更を加える最も簡単な方法ですが、いくつかの欠点があります。</span><span class="sxs-lookup"><span data-stu-id="95cf8-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="95cf8-215">スペル チェックを受け取らない。</span><span class="sxs-lookup"><span data-stu-id="95cf8-215">You don't get spell-check.</span></span>
- <span data-ttu-id="95cf8-216">他の記事へのスマート リンクは取得できません (記事のファイル名を手動で入力する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="95cf8-217">画像をアップロードして参照すると面倒な場合があります。</span><span class="sxs-lookup"><span data-stu-id="95cf8-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="95cf8-218">これらの問題に対処しない場合は、Visual Studio [Code](https://code.visualstudio.com/) のようなデスクトップ クライアントを使用して、貢献する際に役立つ拡張機能を [2](#useful-extensions) つ追加します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <span data-ttu-id="95cf8-219">コードVisual Studio使用する</span><span class="sxs-lookup"><span data-stu-id="95cf8-219">Using Visual Studio Code</span></span>

<span data-ttu-id="95cf8-220">上記の理由から、Web[](#editing-in-the-browser-vs-editing-with-a-desktop-client)ブラウザーではなく、デスクトップ クライアントを使用してドキュメントを編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="95cf8-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="95cf8-221">コードを使用することをお [Visual Studioします](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <span data-ttu-id="95cf8-222">セットアップ</span><span class="sxs-lookup"><span data-stu-id="95cf8-222">Setup</span></span>

<span data-ttu-id="95cf8-223">次の手順に従って、このVisual Studioを使用するためのコードを構成します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="95cf8-224">Web ブラウザーの場合:</span><span class="sxs-lookup"><span data-stu-id="95cf8-224">In a web browser:</span></span>
    1. <span data-ttu-id="95cf8-225">お [使いの PC 用に Git をインストールします](https://git-scm.com/downloads)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="95cf8-226">コード [Visual Studioインストールします](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="95cf8-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span><span class="sxs-lookup"><span data-stu-id="95cf8-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="95cf8-228">フォークで、URL を複製または **ダウンロードして** コピーします。</span><span class="sxs-lookup"><span data-stu-id="95cf8-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="95cf8-229">次のコードを使用して、フォークのローカル 複製Visual Studioします。</span><span class="sxs-lookup"><span data-stu-id="95cf8-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="95cf8-230">[表示] **メニューの** [コマンド パレット] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="95cf8-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="95cf8-231">「Git: Clone」と入力します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="95cf8-232">コピーした URL を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="95cf8-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="95cf8-233">PC で複製を保存する場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="95cf8-234">ポップアップ **で [開く** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-234">Select **Open repo** in the pop-up.</span></span>

### <span data-ttu-id="95cf8-235">ドキュメントの編集</span><span class="sxs-lookup"><span data-stu-id="95cf8-235">Editing documentation</span></span>

<span data-ttu-id="95cf8-236">以下のワークフローを使用して、コードを使用してドキュメントをVisual Studioします。</span><span class="sxs-lookup"><span data-stu-id="95cf8-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="95cf8-237">上記の記事の [編集](#editing-an-existing-article) と [作成](#creating-a-new-article) に関するガイダンス、 [および Markdown](#markdown-basics)の編集の基本はすべて、このコードを使用する場合にもVisual Studio適用されます。</span><span class="sxs-lookup"><span data-stu-id="95cf8-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="95cf8-238">複製されたフォークが公式リポジトリで最新の情報を得たか確認します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="95cf8-239">Web ブラウザーで、MicrosoftDocs/Mixed-Reality 'master' の他の投稿者からの最近の変更をフォークに同期するプル要求を作成します (矢印が正しい方向を指しているか確認してください)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![MicrosoftDocs/mixed-Reality からフォークへの変更を同期する](images/sync-repos.png)
      
   2. <span data-ttu-id="95cf8-241">[Visual Studioコード] で、同期ボタンを選択して、新しく更新したフォークをローカル複製に同期します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![同期ボタンの画像をクリックする](images/sync-clone.png)
      
2. <span data-ttu-id="95cf8-243">複製されたリポジトリの記事を作成または編集するには、次のコードVisual Studioします。</span><span class="sxs-lookup"><span data-stu-id="95cf8-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="95cf8-244">1 つ以上の記事を編集します (必要に応じて、イメージを "images" フォルダーに追加します)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="95cf8-245">**エクスプローラーで** 変更を **保存します**。</span><span class="sxs-lookup"><span data-stu-id="95cf8-245">**Save** changes in **Explorer**.</span></span>
      
      ![エクスプローラーで [すべて保存] を選択する](images/explorer-save.png)
      
   3. <span data-ttu-id="95cf8-247">**ソース管理のすべての** 変更を **コミット** します (メッセージが表示されたらコミット メッセージを書き込む)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
      
   4. <span data-ttu-id="95cf8-248">同期ボタン **を選択** して、変更内容を元の状態 (GitHub のフォーク) に同期します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-248">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![[同期] ボタンをクリックする](images/sync-back.png)
      
3. <span data-ttu-id="95cf8-250">Web ブラウザーで、フォークの新しい変更を MicrosoftDocs/mixed-Reality 'master' に同期するプル要求を作成します (矢印が正しい方向を指していることを確認してください)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-250">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![フォークから MicrosoftDocs/mixed-Reality へのプル要求を作成する](images/pr-to-master.png)

### <span data-ttu-id="95cf8-252">便利な拡張機能</span><span class="sxs-lookup"><span data-stu-id="95cf8-252">Useful extensions</span></span>

<span data-ttu-id="95cf8-253">ドキュメントを編集Visual Studioコード拡張機能は、次の方法で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="95cf8-253">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="95cf8-254">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Alt + **M** を使用して、次のようなドキュメント作成オプションのメニューを表示します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-254">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="95cf8-255">アップロードした画像を検索して参照します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-255">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="95cf8-256">リスト、表、ドキュメント固有のコールアウトなど、書式設定を追加します `>[!NOTE]` 。</span><span class="sxs-lookup"><span data-stu-id="95cf8-256">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="95cf8-257">内部リンクとブックマーク (ページ内の特定のセクションへのリンク) を検索して参照します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-257">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="95cf8-258">書式設定エラーが強調表示されます (詳細を確認するには、エラーの上にマウス ポインターを移動します)。</span><span class="sxs-lookup"><span data-stu-id="95cf8-258">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="95cf8-259">[コードスペル チェック](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - スペル ミスの単語に下線が引きされます。スペル ミスの単語を右クリックして変更するか、辞書に保存します。</span><span class="sxs-lookup"><span data-stu-id="95cf8-259">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
