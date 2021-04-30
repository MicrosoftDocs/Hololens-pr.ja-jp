---
title: フィードバックの送信
description: フィードバックハブを使用して、HoloLens および Windows Mixed Reality 開発者向けのアクションに関するフィードバックを作成します。
ms.assetid: b9b24c72-ff86-44a9-b30d-dd76c49479a9
author: mattzmsft
ms.author: mazeller
ms.date: 12/17/2020
ms.custom:
- CI 116157
- CSSTroubleshooting
audience: ITPro
ms.prod: hololens
ms.topic: article
keywords: フィードバック、バグ、問題、エラー、トラブルシューティング、ヘルプ
manager: jarrettr
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f8704b7e1b75cd08bc282eb0c2df22b8266cb9fd
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2021
ms.locfileid: "108309631"
---
# <a name="feedback-for-hololens"></a><span data-ttu-id="5effd-104">HoloLens に関するフィードバック</span><span class="sxs-lookup"><span data-stu-id="5effd-104">Feedback for HoloLens</span></span>

<span data-ttu-id="5effd-105">フィードバックハブを使用して、気に入っている機能、どの機能を使用しないか、およびどのように改善できるかをご連絡ください。</span><span class="sxs-lookup"><span data-stu-id="5effd-105">Use the Feedback Hub to tell us which features you love, which features you could do without, and how something could be better.</span></span> <span data-ttu-id="5effd-106">エンジニアリングチームは、内部で同じメカニズムを使用してバグを追跡および修正します。そのため、フィードバックハブを使用して、表示されるすべてのバグを報告してください。</span><span class="sxs-lookup"><span data-stu-id="5effd-106">The engineering team uses the same mechanism internally to track and fix bugs, so please use Feedback Hub to report any bugs that you see.</span></span> <span data-ttu-id="5effd-107">お待ちしています。</span><span class="sxs-lookup"><span data-stu-id="5effd-107">We are listening!</span></span>

<span data-ttu-id="5effd-108">フィードバックハブは、エンジニアリングチームにバグを知らせる優れた方法であり、今後の更新プログラムが高くなりされ、一貫性のあるバグをより確実に解放できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5effd-108">Feedback Hub is an excellent way to alert the engineering team to bugs and to make sure that future updates are healthier and more consistently free of bugs.</span></span> <span data-ttu-id="5effd-109">ただし、フィードバックハブは応答を提供しません。</span><span class="sxs-lookup"><span data-stu-id="5effd-109">However, Feedback Hub does not provide a response.</span></span> <span data-ttu-id="5effd-110">早急に支援が必要な場合は、フィードバックをお送りください。フィードバックのために提供された概要を書き留め、 [HoloLens サポート](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f) にご協力ください。フィードバックハブの **共有** 機能を使用して、URL への直接リンクを共有してください。</span><span class="sxs-lookup"><span data-stu-id="5effd-110">If you need immediate help, please file feedback, take note of the summary that you provided for your feedback, and then follow up with [HoloLens support](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f) - use the **Share** feature in Feedback Hub to share a direct link to the URL.</span></span> <span data-ttu-id="5effd-111">フィードバックハブは、毎日大量のデータを取得します。この URL は、フィードバックを迅速に識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5effd-111">Feedback Hub gets lots of data daily - the URL helps us identify your feedback quickly.</span></span>

> [!NOTE]  
>  
> - <span data-ttu-id="5effd-112">フィードバックハブの最新バージョンがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5effd-112">Make sure you that you have the current version of Feedback Hub.</span></span> <span data-ttu-id="5effd-113">これを行うには、[**開始** Microsoft Store] を選択し、  >  省略記号 (**...**) を選択します。次に、[**ダウンロードと更新** プログラムの取得] を選択し  >  ます。</span><span class="sxs-lookup"><span data-stu-id="5effd-113">To do this, select **Start** > **Microsoft Store**, and then select the ellipses (**...**). Then, select **Downloads and updates** > **Get updates**.</span></span>  
>  
> - <span data-ttu-id="5effd-114">問題を修正するための最適なデータを提供するには、デバイスのテレメトリを **オプション** に設定することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5effd-114">To provide the best possible data for fixing issues, we highly recommended that you set your device telemetry to **Optional**.</span></span> <span data-ttu-id="5effd-115">この値は、既定のエクスペリエンス (OOBE) で、または設定アプリを使用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="5effd-115">You can set this value during the Out-of-Box-Experience (OOBE), or by using the Settings app.</span></span> <span data-ttu-id="5effd-116">設定を使用してこれを行うには、[**開始**  >  **設定**] [  >  **プライバシー**]  >  **[アプリ診断**  >  ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5effd-116">To do this by using Settings, select **Start** > **Settings** > **Privacy** > **App Diagnostics** > **On**.</span></span>

## <a name="use-the-feedback-hub"></a><span data-ttu-id="5effd-117">フィードバックハブを使用する</span><span class="sxs-lookup"><span data-stu-id="5effd-117">Use the Feedback Hub</span></span>

1. <span data-ttu-id="5effd-118">**開始** ジェスチャを使用して [**スタート**] メニューを開き、[**フィードバックハブ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5effd-118">Use the **Start** gesture to open the **Start** menu, and then select **Feedback Hub**.</span></span> <span data-ttu-id="5effd-119">環境でアプリが開きます。</span><span class="sxs-lookup"><span data-stu-id="5effd-119">The app opens in your environment.</span></span>

   ![HoloLens のフィードバックアプリの [スタート] メニュー](./images/hololens2-feedbackhub-tile.png)
   > [!NOTE]  
   > <span data-ttu-id="5effd-121">**フィードバックハブ** が表示されない場合は、[**すべてのアプリ**] を選択して、デバイス上のアプリの完全な一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="5effd-121">If you don't see **Feedback Hub**, select **All Apps** to see the complete list of apps on the device.</span></span>

1. <span data-ttu-id="5effd-122">他のユーザーが同様のフィードバックを受け取ったかどうかを確認するには、[ **フィードバック** ] 検索ボックスのトピックについていくつかのキーワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="5effd-122">To see whether someone else has given similar feedback, enter a few keywords about the topic in the **Feedback** search box.</span></span>
1. <span data-ttu-id="5effd-123">同様のフィードバックが見つかった場合は、それを選択し、[ **コメントの作成** ] ボックスに表示されている追加情報を追加して、[ **upvote**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5effd-123">If you find similar feedback, select it, add any additional information that you have in the **Write a comment** box, and then select **Upvote**.</span></span>
1. <span data-ttu-id="5effd-124">同様のフィードバックが見つからない場合は、[ **新しいフィードバックの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5effd-124">If you don't find any similar feedback, select **Add new feedback**.</span></span>

   ![[新しいフィードバックの追加]](./images/hololens-feedback-1.png)

1. <span data-ttu-id="5effd-126">[ **フィードバックの要約**] で、フィードバックの簡単な概要を入力します。</span><span class="sxs-lookup"><span data-stu-id="5effd-126">In **Summarize your feedback**, enter a short summary of your feedback.</span></span> <span data-ttu-id="5effd-127">詳細については、「 **説明」を参照** してください。</span><span class="sxs-lookup"><span data-stu-id="5effd-127">Then add details in the **Explain in more detail** box.</span></span> <span data-ttu-id="5effd-128">この問題を再現する方法やその効果など、提供する詳細情報が多いほど、フィードバックはより有益です。</span><span class="sxs-lookup"><span data-stu-id="5effd-128">The more details that you provide, such as how to reproduce this problem and the effect that it has, the more useful your feedback is.</span></span> <span data-ttu-id="5effd-129">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5effd-129">When you're finished, select **Next**.</span></span>

1. <span data-ttu-id="5effd-130">[ **カテゴリの選択**] からトピックを選択し、[サブカテゴリの **選択]** からサブカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="5effd-130">Select a topic from **Choose a category**, and then select a subcategory from **Select a subcategory**.</span></span> <span data-ttu-id="5effd-131">次の表では、Windows Holographic カテゴリで使用できるカテゴリについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5effd-131">The following table describes the categories that are available in the Windows Holographic category.</span></span>

   > [!NOTE]  
   > <span data-ttu-id="5effd-132">**商用のお客様**: MDM、プロビジョニング、またはその他のデバイス管理の側面に関連するバグを報告するには、[ **エンタープライズ管理** ] カテゴリと [ **デバイス** ] サブカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="5effd-132">**Commercial customers**: To report a bug that is related to MDM, provisioning, or any other device management aspect, select the **Enterprise Management** category, and the **Device** subcategory.</span></span>

   |<span data-ttu-id="5effd-133">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="5effd-133">Category</span></span> |<span data-ttu-id="5effd-134">説明</span><span class="sxs-lookup"><span data-stu-id="5effd-134">Description</span></span> |
   | --- | --- |
   |<span data-ttu-id="5effd-135">視線追跡</span><span class="sxs-lookup"><span data-stu-id="5effd-135">Eye tracking</span></span> |<span data-ttu-id="5effd-136">視線追跡、虹彩サインイン、または調整に関するフィードバック。</span><span class="sxs-lookup"><span data-stu-id="5effd-136">Feedback about eye tracking, iris sign-in, or calibration.</span></span> |
   |<span data-ttu-id="5effd-137">ホログラムの精度、安定性、信頼性</span><span class="sxs-lookup"><span data-stu-id="5effd-137">Hologram accuracy, stability, and reliability</span></span> |<span data-ttu-id="5effd-138">ホログラムがスペースにどのように表示されるかに関するフィードバック。</span><span class="sxs-lookup"><span data-stu-id="5effd-138">Feedback about how holograms appear in space.</span></span> |
   |<span data-ttu-id="5effd-139">アプリの起動、配置、調整、および終了</span><span class="sxs-lookup"><span data-stu-id="5effd-139">Launching, placing, adjusting, and exiting apps</span></span> |<span data-ttu-id="5effd-140">2D または3D アプリの開始または停止に関するフィードバック。</span><span class="sxs-lookup"><span data-stu-id="5effd-140">Feedback about starting or stopping 2D or 3D apps.</span></span> |
   |<span data-ttu-id="5effd-141">Miracast</span><span class="sxs-lookup"><span data-stu-id="5effd-141">Miracast</span></span> |<span data-ttu-id="5effd-142">Miracast に関するフィードバック。</span><span class="sxs-lookup"><span data-stu-id="5effd-142">Feedback about Miracast.</span></span> |
   |<span data-ttu-id="5effd-143">スペースと永続性</span><span class="sxs-lookup"><span data-stu-id="5effd-143">Spaces and persistence</span></span> |<span data-ttu-id="5effd-144">HoloLens がスペースを認識し、空間にホログラムを保持する方法に関するフィードバック。</span><span class="sxs-lookup"><span data-stu-id="5effd-144">Feedback about how HoloLens recognizes spaces and retains holograms in space.</span></span> |
   |<span data-ttu-id="5effd-145">[スタート] メニューと [すべてのアプリ] の一覧</span><span class="sxs-lookup"><span data-stu-id="5effd-145">Start menu and all apps list</span></span> |<span data-ttu-id="5effd-146">[ **スタート** ] メニューと [すべてのアプリ] の一覧に関するフィードバック。</span><span class="sxs-lookup"><span data-stu-id="5effd-146">Feedback about the **Start** menu and the all apps list.</span></span> |
   |<span data-ttu-id="5effd-147">Surface マッピング</span><span class="sxs-lookup"><span data-stu-id="5effd-147">Surface mapping</span></span> |<span data-ttu-id="5effd-148">Surface マッピングに関するフィードバック。</span><span class="sxs-lookup"><span data-stu-id="5effd-148">Feedback about surface mapping.</span></span> |
   |<span data-ttu-id="5effd-149">画像とビデオの撮影</span><span class="sxs-lookup"><span data-stu-id="5effd-149">Taking pictures and videos</span></span> |<span data-ttu-id="5effd-150">混合現実のキャプチャに関するフィードバック。</span><span class="sxs-lookup"><span data-stu-id="5effd-150">Feedback about mixed reality captures.</span></span> |
   |<span data-ttu-id="5effd-151">ビデオホログラム再生</span><span class="sxs-lookup"><span data-stu-id="5effd-151">Video hologram playback</span></span> |<span data-ttu-id="5effd-152">ビデオのホログラム再生に関するフィードバック。</span><span class="sxs-lookup"><span data-stu-id="5effd-152">Feedback about video hologram playback.</span></span> |
   |<span data-ttu-id="5effd-153">その他のすべての問題</span><span class="sxs-lookup"><span data-stu-id="5effd-153">All other issues</span></span> |<span data-ttu-id="5effd-154">その他のすべての問題。</span><span class="sxs-lookup"><span data-stu-id="5effd-154">All other issues.</span></span> |

1. <span data-ttu-id="5effd-155">同様のフィードバックを検索するように求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5effd-155">You may be prompted to search for similar feedback.</span></span> <span data-ttu-id="5effd-156">問題が他のユーザーからのフィードバックと類似している場合は、そのフィードバックを選択します。</span><span class="sxs-lookup"><span data-stu-id="5effd-156">If your problem resembles feedback from other users, select that feedback.</span></span> <span data-ttu-id="5effd-157">それ以外の場合は、[ **新しいフィードバック** ] を選択し、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5effd-157">Otherwise, select **New feedback** and then select **Next**.</span></span>

1. <span data-ttu-id="5effd-158">メッセージが表示されたら、問題の最適な説明を選択します。</span><span class="sxs-lookup"><span data-stu-id="5effd-158">If you are prompted, select the best description of the problem.</span></span>

1. <span data-ttu-id="5effd-159">関連するデータをフィードバックに添付するか、問題を再現します。</span><span class="sxs-lookup"><span data-stu-id="5effd-159">Attach any relevant data to your feedback, or reproduce the problem.</span></span> <span data-ttu-id="5effd-160">以下のオプションを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="5effd-160">You can select any of the following options:</span></span>

   - <span data-ttu-id="5effd-161">**スクリーンショットを添付** します。</span><span class="sxs-lookup"><span data-stu-id="5effd-161">**Attach a screenshot**.</span></span> <span data-ttu-id="5effd-162">このオプションを選択すると、説明している状況を示すスクリーンショットが添付されます。</span><span class="sxs-lookup"><span data-stu-id="5effd-162">Select this option to attach a screenshot that illustrates the situation that you're describing.</span></span>
   - <span data-ttu-id="5effd-163">**ファイルを添付** します。</span><span class="sxs-lookup"><span data-stu-id="5effd-163">**Attach a file**.</span></span> <span data-ttu-id="5effd-164">データファイルをアタッチするには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="5effd-164">Select this option to attach data files.</span></span> <span data-ttu-id="5effd-165">問題に関連するファイルがある場合、または問題の再現に役立つファイルがある場合は、それらを添付します。</span><span class="sxs-lookup"><span data-stu-id="5effd-165">If you have files that are relevant to your problem or that could help us to reproduce your problem, attach them.</span></span>
   - <span data-ttu-id="5effd-166">**問題を再作成** します。</span><span class="sxs-lookup"><span data-stu-id="5effd-166">**Recreate my problem**.</span></span> <span data-ttu-id="5effd-167">問題を自分で再現できる場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="5effd-167">Select this option if you can reproduce the problem yourself.</span></span> <span data-ttu-id="5effd-168">[問題の **再作成**] を選択した後、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5effd-168">After you select **Recreate my problem**, follow these steps:</span></span>  

     1. <span data-ttu-id="5effd-169">[ **データに関する情報を含める** ] を選択し、最も関連性の高いデータ型が一覧表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5effd-169">Select **Include data about** and make sure that the most relevant types of data are listed.</span></span> <span data-ttu-id="5effd-170">ほとんどの場合、既定の選択は、フィードバックに対して選択したカテゴリとサブカテゴリに基づいています。</span><span class="sxs-lookup"><span data-stu-id="5effd-170">In most cases, the default selections are based on the category and subcategory that you selected for your feedback.</span></span>  
     1. <span data-ttu-id="5effd-171">**[記録の開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5effd-171">Select **Start Recording**.</span></span>

     1. <span data-ttu-id="5effd-172">問題を再現します。</span><span class="sxs-lookup"><span data-stu-id="5effd-172">Reproduce your problem.</span></span> <span data-ttu-id="5effd-173">これは、イマーシブアプリを入力する必要があることを意味しています。</span><span class="sxs-lookup"><span data-stu-id="5effd-173">Don’t worry if this means that you have to enter an immersive app.</span></span> <span data-ttu-id="5effd-174">完了すると、[フィードバック] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="5effd-174">You will return to the feedback page when you're done.</span></span>
     1. <span data-ttu-id="5effd-175">[ **記録の停止**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5effd-175">Select **Stop recording**.</span></span> <span data-ttu-id="5effd-176">記録が停止すると、エンジニアリングチームのフィードバックに添付されているデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5effd-176">After recording stops, you can see the data that is attached to your feedback for the engineering team.</span></span>

1. <span data-ttu-id="5effd-177">フィードバックを受け取ることができるように、インターネット接続がアクティブになっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5effd-177">Make sure that you have an active internet connection so that we can receive your feedback.</span></span> <span data-ttu-id="5effd-178">[ **送信**] を選択すると、完了です。</span><span class="sxs-lookup"><span data-stu-id="5effd-178">Select **Submit**, and you’re done.</span></span>

1. <span data-ttu-id="5effd-179">[ **共有** ] ボタンを使用して、短い URL を Microsoft サポートまたは同僚と共有します。</span><span class="sxs-lookup"><span data-stu-id="5effd-179">Use the **Share** button to share the shortened-URL with Microsoft support, or your colleagues.</span></span>