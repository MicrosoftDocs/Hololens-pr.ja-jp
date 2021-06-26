---
title: HoloLens デバイスとホログラムに関してよく寄せられる質問
description: HoloLens やホログラムの操作に関する簡単な質問はありますか?  この記事では、簡単な回答と他のリソースを提供します。
keywords: hololens, FAQ, 既知の問題, ヘルプ
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ae44ae1d9a2e088a1ef746f4e929e8fae73880bf
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924028"
---
# <a name="holograms-and-interactions-troubleshooting"></a><span data-ttu-id="ff9ec-105">ホログラムと相互作用のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ff9ec-105">Holograms and interactions troubleshooting</span></span>

<span data-ttu-id="ff9ec-106">この記事では、ホログラムの配置、スペースの操作、ホログラムに関する問題の報告に関する問題のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-106">This article troubleshoots issues with placing holograms, working with spaces, and reporting issues with holograms.</span></span>

<span data-ttu-id="ff9ec-107">問題が発生した場合は、次の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-107">Anytime that you have problems, make sure:</span></span>
- <span data-ttu-id="ff9ec-108">再起動 [して、](hololens-restart-recover.md) それが問題を解決するかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-108">Try [restarting it](hololens-restart-recover.md) to see whether that fixes things.</span></span>
- <span data-ttu-id="ff9ec-109">トラブルシューティングを行う前に、HoloLens に [課金されます](hololens2-charging.md) (少なくとも 1 時間は課金されます)。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-109">Before troubleshooting, ensure the HoloLens is [charged up](hololens2-charging.md) (charged for at least an hour).</span></span> 


<span data-ttu-id="ff9ec-110">フィードバック アプリを使用して、問題に関する情報を送信してください。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-110">Please use the Feedback app to send us information about the issue.</span></span> <span data-ttu-id="ff9ec-111">[スタート] メニューにフィードバック アプリ[があります。](holographic-home.md)</span><span class="sxs-lookup"><span data-stu-id="ff9ec-111">You'll find the Feedback app on the [**Start** menu](holographic-home.md).</span></span> 

<span data-ttu-id="ff9ec-112">HoloLens の装着方法に関するヒントについては、「Fit の調整」 [を参照してください](hololens2-setup.md#adjust-fit)。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-112">For tips about how to wear your HoloLens, see [Adjust Fit](hololens2-setup.md#adjust-fit).</span></span>

<a id="list"></a>
- [<span data-ttu-id="ff9ec-113">新しいスペースを作成できない</span><span class="sxs-lookup"><span data-stu-id="ff9ec-113">New spaces can't be created</span></span>](#new-spaces-cant-be-created)
- [<span data-ttu-id="ff9ec-114">スペースを識別または読み込めない</span><span class="sxs-lookup"><span data-stu-id="ff9ec-114">Spaces can't be identified or loaded</span></span>](#spaces-cant-be-identified-or-loaded)
- [<span data-ttu-id="ff9ec-115">操作方法削除しますか?</span><span class="sxs-lookup"><span data-stu-id="ff9ec-115">How do I delete all spaces?</span></span>](#how-do-i-delete-all-spaces)
- [<span data-ttu-id="ff9ec-116">ホログラムが正しく見えなかったり、動き回っている</span><span class="sxs-lookup"><span data-stu-id="ff9ec-116">Holograms don't look right or are moving around</span></span>](#holograms-dont-look-right-or-are-moving-around)
- [<span data-ttu-id="ff9ec-117">"領域の検索" メッセージ</span><span class="sxs-lookup"><span data-stu-id="ff9ec-117">"Finding your space" message</span></span>](#finding-your-space-message)
- [<span data-ttu-id="ff9ec-118">予想されるホログラムが空間に表示されない</span><span class="sxs-lookup"><span data-stu-id="ff9ec-118">Expected holograms aren't showing in my space</span></span>](#expected-holograms-arent-showing-in-my-space)
- [<span data-ttu-id="ff9ec-119">ホログラムを配置できない、または以前に配置されたホログラムを表示できない</span><span class="sxs-lookup"><span data-stu-id="ff9ec-119">Can't place holograms or see previously placed holograms</span></span>](#cant-place-holograms-or-see-previously-placed-holograms)
- [<span data-ttu-id="ff9ec-120">ホログラムが消える、または他のホログラムまたはオブジェクトに含まれています</span><span class="sxs-lookup"><span data-stu-id="ff9ec-120">Holograms disappear or are encased in other holograms or objects</span></span>](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [<span data-ttu-id="ff9ec-121">ホログラムが壁の反対側に表示されている</span><span class="sxs-lookup"><span data-stu-id="ff9ec-121">Holograms are appearing on the other side of a wall</span></span>](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [<span data-ttu-id="ff9ec-122">ホログラムを壁に配置すると、浮いているようです</span><span class="sxs-lookup"><span data-stu-id="ff9ec-122">After placing a hologram on a wall, it seems to float</span></span>](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [<span data-ttu-id="ff9ec-123">アプリを移動した後に近すぎると表示される</span><span class="sxs-lookup"><span data-stu-id="ff9ec-123">Apps appear too close after moving them</span></span>](#apps-appear-too-close-after-moving-them)
- [<span data-ttu-id="ff9ec-124">不安定または未加工のホログラムに関する問題を報告する</span><span class="sxs-lookup"><span data-stu-id="ff9ec-124">Reporting issues with unstable or inexact holograms</span></span>](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a><span data-ttu-id="ff9ec-125">新しいスペースを作成できない</span><span class="sxs-lookup"><span data-stu-id="ff9ec-125">New spaces can't be created</span></span>

<span data-ttu-id="ff9ec-126">最も可能性の高い問題は、記憶域スペースが少なかっているという問題です。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-126">The most likely problem is that you're running low on storage space.</span></span> <span data-ttu-id="ff9ec-127">[一部のディスク領域を解放してから](hololens-troubleshooting.md#low-disk-space-error) 、再試行してください。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-127">[Free up some disk space](hololens-troubleshooting.md#low-disk-space-error) and then retry.</span></span>

[<span data-ttu-id="ff9ec-128">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="ff9ec-128">Back to list</span></span>](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a><span data-ttu-id="ff9ec-129">スペースを識別または読み込めない</span><span class="sxs-lookup"><span data-stu-id="ff9ec-129">Spaces can't be identified or loaded</span></span>

<span data-ttu-id="ff9ec-130">HoloLens で、自分が入っている領域を自動的に識別して読み込めなかった場合は、次の要因を確認します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-130">If your HoloLens can't identify and load the space you're in automatically, check the following factors:</span></span>

- <span data-ttu-id="ff9ec-131">接続されていることを確認Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="ff9ec-131">Make sure that you're connected to Wi-Fi</span></span>
- <span data-ttu-id="ff9ec-132">部屋に十分な光が入っているのを確認する</span><span class="sxs-lookup"><span data-stu-id="ff9ec-132">Make sure that there's plenty of light in the room</span></span>
- <span data-ttu-id="ff9ec-133">周囲に大きな変更が加えっていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-133">Make sure that there haven't been any major changes to the surroundings.</span></span>

<span data-ttu-id="ff9ec-134">[設定] [システムスペース] に移動して、スペースを手動で読み込むか、スペース  >  **を管理**  >  **することもできます**。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-134">You can also load a space manually or manage your spaces by going to **Settings** > **System** > **Spaces**.</span></span>

[<span data-ttu-id="ff9ec-135">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="ff9ec-135">Back to list</span></span>](#list)

## <a name="how-do-i-delete-all-spaces"></a><span data-ttu-id="ff9ec-136">操作方法削除しますか?</span><span class="sxs-lookup"><span data-stu-id="ff9ec-136">How do I delete all spaces?</span></span>

<span data-ttu-id="ff9ec-137">*近日公開予定*</span><span class="sxs-lookup"><span data-stu-id="ff9ec-137">*Coming soon*</span></span>

[<span data-ttu-id="ff9ec-138">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="ff9ec-138">Back to list</span></span>](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a><span data-ttu-id="ff9ec-139">ホログラムが正しく見えなかったり、動き回っている</span><span class="sxs-lookup"><span data-stu-id="ff9ec-139">Holograms don't look right or are moving around</span></span>

<span data-ttu-id="ff9ec-140">ホログラムが正しそうに表示されていない場合 (ジッターや不安定な場合や、黒いパッチが上に表示されるなど) 場合は、次のいずれかの修正プログラムを試してください。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-140">If your holograms don't look right (for example, they're jittery or shaky, or you see black patches on top of them), try one of these fixes:</span></span>

- <span data-ttu-id="ff9ec-141">[デバイスバイザーをクリーンアップし](hololens1-hardware.md#care-and-cleaning) 、何もセンサーをブロックされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-141">[Clean your device visor](hololens1-hardware.md#care-and-cleaning) and make sure nothing is blocking the sensors.</span></span>
- <span data-ttu-id="ff9ec-142">直接の光が多くはない明るい部屋に入っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-142">Make sure that you're in a well-lit room that does not have a lot of direct sunlight.</span></span>
- <span data-ttu-id="ff9ec-143">HoloLens がそれらをより完全にスキャンできるよう、周囲を歩き回って歩き回ってみろ。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-143">Try walking around and gazing at your surroundings so that HoloLens can scan them more completely.</span></span>
- <span data-ttu-id="ff9ec-144">ホログラムを多く配置している場合は、一部を削除してみてください。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-144">If you've placed a lot of holograms, try removing some.</span></span>

<span data-ttu-id="ff9ec-145">まだ問題が解決しない場合は、調整アプリを実行してください。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-145">If you're still having problems, trying running the Calibration app.</span></span> <span data-ttu-id="ff9ec-146">このアプリでは、ホログラムを最適な外観に保つために、HoloLens を調整します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-146">This app calibrates your HoloLens just for you to help keep your holograms looking their best.</span></span> <span data-ttu-id="ff9ec-147">これを行うには、 [設定] [システム **ユーティリティ**  >  **] に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-147">To do this, go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="ff9ec-148">[調整 **] で**、[ 調整を **開く] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-148">Under **Calibration**, select **Open Calibration**.</span></span>

[<span data-ttu-id="ff9ec-149">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="ff9ec-149">Back to list</span></span>](#list)

## <a name="finding-your-space-message"></a><span data-ttu-id="ff9ec-150">"領域の検索" メッセージ</span><span class="sxs-lookup"><span data-stu-id="ff9ec-150">"Finding your space" message</span></span>

<span data-ttu-id="ff9ec-151">HoloLens がスペースを学習または読み込むときに、"領域の検索" という短いメッセージが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-151">When HoloLens is learning or loading a space, you may see a brief message that says "Finding your space."</span></span> <span data-ttu-id="ff9ec-152">このメッセージが数秒以上表示される場合は、スタート メニュー の下に "まだ領域を探しています" という別のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-152">If this message displays for more than a few seconds, you'll see another message under the Start menu that says "Still looking for your space."</span></span>

<span data-ttu-id="ff9ec-153">これらのメッセージは、HoloLens で領域のマッピングに問題が発生しているという意味です。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-153">These messages mean that HoloLens is having trouble mapping your space.</span></span> <span data-ttu-id="ff9ec-154">このような場合は、アプリを開くできますが、環境内にホログラムを配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-154">When this happens, you can open apps, but you can't place holograms in your environment.</span></span>

<span data-ttu-id="ff9ec-155">これらのメッセージが頻繁に表示される場合は、次の修正プログラムを 1 つ以上試してください。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-155">If you see these messages often, try one or more of the following fixes:</span></span>

- <span data-ttu-id="ff9ec-156">直接の光が多くはない明るい部屋に入っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-156">Make sure that you're in a well-lit room that does not have a lot of direct sunlight.</span></span>
- <span data-ttu-id="ff9ec-157">デバイス バイザーがクリーンなデバイスを確認します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-157">Make sure that your device visor is clean.</span></span> <span data-ttu-id="ff9ec-158">[バイザー をクリーンアップする方法について学習します](hololens1-hardware.md#care-and-cleaning)。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-158">[Learn how to clean your visor](hololens1-hardware.md#care-and-cleaning).</span></span>
- <span data-ttu-id="ff9ec-159">強力なシグナルが発生Wi-Fiしてください。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-159">Make sure that you have a strong Wi-Fi signal.</span></span> <span data-ttu-id="ff9ec-160">新しい環境に入り、Wi-Fi または弱い Wi-Fi シグナルを入力した場合、HoloLens は領域を見つけ出すことはありません。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-160">If you enter a new environment that has no Wi-Fi or a weak Wi-Fi signal, HoloLens won't be able find your space.</span></span> <span data-ttu-id="ff9ec-161">[設定] Wi-Fiインターネット Wi-Fiに移動して、接続  >  **&amp;**  >  **を確認します**。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-161">Check your Wi-Fi connection by going to **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span>
- <span data-ttu-id="ff9ec-162">もっとゆっくり移動してみてください。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-162">Try moving more slowly.</span></span>

[<span data-ttu-id="ff9ec-163">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="ff9ec-163">Back to list</span></span>](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a><span data-ttu-id="ff9ec-164">予想されるホログラムが空間に表示されない</span><span class="sxs-lookup"><span data-stu-id="ff9ec-164">Expected holograms aren't showing in my space</span></span>

<span data-ttu-id="ff9ec-165">配置したホログラムが表示しない場合、または期待しないホログラムが表示される場合は、次の修正プログラムを 1 つ以上試してください。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-165">If you don't see the holograms that you placed, or if you're seeing some that you don't expect, try one or more of the following fixes:</span></span>

- <span data-ttu-id="ff9ec-166">一部のライトをオンにする。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-166">Turn on some lights.</span></span> <span data-ttu-id="ff9ec-167">HoloLens は、明るい空間で最適に動作します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-167">HoloLens works best in a well-lit space.</span></span>
- <span data-ttu-id="ff9ec-168">[設定] [システム ホログラム] [近くのホログラムの削除] に移動して、不要  >    >    >  **なホログラムを削除します**。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-168">Remove holograms that you don't need by going to **Settings** > **System** > **Holograms** > **Remove nearby holograms**.</span></span> <span data-ttu-id="ff9ec-169">または、必要に応じて、[すべてのホログラム **を削除する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-169">Or, if needed, select **Remove all holograms**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ff9ec-170">空間内のレイアウトまたは照明が大幅に変更された場合、デバイスでスペースの識別とホログラムの表示に問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-170">If the layout or lighting in your space changes significantly, your device might have trouble identifying your space and showing your holograms.</span></span>

[<span data-ttu-id="ff9ec-171">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="ff9ec-171">Back to list</span></span>](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a><span data-ttu-id="ff9ec-172">ホログラムを配置できない、または以前に配置されたホログラムを表示できない</span><span class="sxs-lookup"><span data-stu-id="ff9ec-172">Can't place holograms or see previously placed holograms</span></span>

<span data-ttu-id="ff9ec-173">HoloLens がスペースをマップまたは読み込めなかった場合は、制限モードに入り、ホログラムを配置したり、配置したホログラムを表示したりできません。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-173">If HoloLens can't map or load your space, it enters Limited mode and you won't be able to place holograms or see holograms that you've placed.</span></span> <span data-ttu-id="ff9ec-174">以下のことを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-174">Here are some things to try:</span></span>

- <span data-ttu-id="ff9ec-175">HoloLens が空間を表示してマップできるよう、環境内に十分な光が入っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-175">Make sure that there's enough light in your environment so HoloLens can see and map the space.</span></span>
- <span data-ttu-id="ff9ec-176">ホログラムを配置しようとしている場所から 1 ~ 3 メートルの間に立つ。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-176">Stand between one and three meters from where you're trying to place the hologram.</span></span>
- <span data-ttu-id="ff9ec-177">ホログラムを黒または反射面に配置しない。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-177">Don't place holograms on black or reflective surfaces.</span></span>
- <span data-ttu-id="ff9ec-178">ネットワークに接続されていることを確認Wi-Fiします。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-178">Make sure that you're connected to a Wi-Fi network.</span></span> <span data-ttu-id="ff9ec-179">Wi-Fi に接続していない場合、HoloLens は既知の領域を識別して読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-179">If you're not connected to Wi-Fi, HoloLens can't identify and load a known space.</span></span>
- <span data-ttu-id="ff9ec-180">HoloLens が周囲を再スキャンできるよう、部屋を歩き回る。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-180">Walk around the rooms so HoloLens can rescan your surroundings.</span></span> <span data-ttu-id="ff9ec-181">既にスキャンされている情報を確認するには、エア タップしてマッピング メッシュのグラフィックを表示します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-181">To see what's already been scanned, air tap to reveal the mapping mesh graphic.</span></span>
- <span data-ttu-id="ff9ec-182">新しい領域を作成する必要がある場合は、Wi-Fi に接続し、HoloLens を再起動します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-182">If you need to create a new space, connect to Wi-Fi, then restart your HoloLens.</span></span>
- <span data-ttu-id="ff9ec-183">正しい領域がアクティブな場合、またはスペースを手動で読み込む場合は、 [**設定]**[システムスペース] に  >  **移動**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-183">To see if the correct space is active, or to manually load a space, go to **Settings** > **System** > **Spaces**.</span></span>
- <span data-ttu-id="ff9ec-184">正しい領域が読み込まれ、問題が解決しない場合は、領域が破損している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-184">If the correct space is loaded and you're still having problems, the space may be corrupt.</span></span> <span data-ttu-id="ff9ec-185">この問題を解決するには、スペースを選択し、 [削除] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-185">To fix this issue, select the space, then select **Remove**.</span></span> <span data-ttu-id="ff9ec-186">スペースを削除すると、HoloLens によって周囲のマップが開始され、新しいスペースが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-186">After you remove the space, HoloLens starts to map your surroundings and create a new space.</span></span>

[<span data-ttu-id="ff9ec-187">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="ff9ec-187">Back to list</span></span>](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a><span data-ttu-id="ff9ec-188">ホログラムが消える、または他のホログラムまたはオブジェクトに含まれています</span><span class="sxs-lookup"><span data-stu-id="ff9ec-188">Holograms disappear or are encased in other holograms or objects</span></span>

<span data-ttu-id="ff9ec-189">ホログラムに近すぎると、ホログラムを復元するために一時的に消え、ホログラムから離 &mdash; れるだけになります。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-189">If you get too close to a hologram, it will temporarily disappear&mdash;to restore the hologram, just move away from it.</span></span> <span data-ttu-id="ff9ec-190">また、複数のホログラムを近くに配置した場合は、一部が消える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-190">Also, if you've placed several holograms close together, some may disappear.</span></span> <span data-ttu-id="ff9ec-191">いくつか削除してみてください。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-191">Try removing a few.</span></span>

<span data-ttu-id="ff9ec-192">ホログラムは、他のホログラムや壁などのオブジェクトによってブロックまたは囲む場合もあります。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-192">Holograms can also be blocked or encased by other holograms or by objects such as walls.</span></span> <span data-ttu-id="ff9ec-193">このような場合は、次のいずれかの修正プログラムを試してください。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-193">If this happens, try one of the following fixes:</span></span>

- <span data-ttu-id="ff9ec-194">ホログラムが別のホログラムに入る場合は、そのホログラムを別の場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-194">If the hologram is encased in another hologram, move the encased hologram to another location.</span></span> <span data-ttu-id="ff9ec-195">これを行うには、[調整] **を選択し**、長押しして配置します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-195">To do this, select **Adjust**, then tap and hold to position it.</span></span>
- <span data-ttu-id="ff9ec-196">ホログラムが壁に入る場合は、[調整]を選択し、ホログラムが表示されるまで壁に向かって歩いてください。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-196">If the hologram is encased in a wall, select **Adjust**, then walk toward the wall until the hologram appears.</span></span> <span data-ttu-id="ff9ec-197">長押しし、ホログラムを壁の前と外に引き出します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-197">Tap and hold, then pull the hologram forward and out of the wall.</span></span>
- <span data-ttu-id="ff9ec-198">ジェスチャを使用してホログラムを移動できない場合は、音声を使用してホログラムを削除します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-198">If you can't move the hologram by using gestures, use your voice to remove it.</span></span> <span data-ttu-id="ff9ec-199">ホログラムを視線入力し、"Remove" と入力します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-199">Gaze at the hologram, then say "Remove."</span></span> <span data-ttu-id="ff9ec-200">次に、ホログラムを再度開き、新しい場所に配置します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-200">Then reopen the hologram and place it in a new location.</span></span>

[<span data-ttu-id="ff9ec-201">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="ff9ec-201">Back to list</span></span>](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a><span data-ttu-id="ff9ec-202">ホログラムが壁の反対側に表示される</span><span class="sxs-lookup"><span data-stu-id="ff9ec-202">Holograms are appearing on the other side of a wall</span></span>

<span data-ttu-id="ff9ec-203">壁に近づいている場合、または HoloLens でウォールがまだスキャンされていない場合は、次の部屋にあるホログラムを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-203">If you're very close to a wall, or if HoloLens hasn't scanned the wall yet, you can see holograms that are in the next room.</span></span> <span data-ttu-id="ff9ec-204">壁をスキャンするには、1 ~ 3 つのメーターを壁から離れた場所に設置します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-204">To scan the wall, stand between one and three meters from the wall and gaze at it.</span></span>

<span data-ttu-id="ff9ec-205">HoloLens が壁をスキャンしようとしたときに、黒色または反射のオブジェクト (たとえば、黒色のソファまたは小さいスチール冷蔵庫) が壁の近くにあると、問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-205">A black or reflective object (for example, a black couch or a stainless steel refrigerator) near the wall may cause problems when HoloLens tries to scan the wall.</span></span> <span data-ttu-id="ff9ec-206">そのようなオブジェクトがある場合は、壁の反対側をスキャンします。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-206">If there is such an object, scan the other side of the wall.</span></span>

[<span data-ttu-id="ff9ec-207">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="ff9ec-207">Back to list</span></span>](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a><span data-ttu-id="ff9ec-208">壁にホログラムを配置すると、フロートに見えるように見えます。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-208">After placing a hologram on a wall, it seems to float</span></span>

<span data-ttu-id="ff9ec-209">壁に置いたホログラムは、通常、壁からインチまたはそれほど離れた場所にあるように見えます。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-209">A hologram that you place on a wall typically appears to be an inch or so away from the wall.</span></span> <span data-ttu-id="ff9ec-210">他にも表示されている場合は、次の1つまたは複数の修正プログラムを試してください。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-210">If it appears to be farther away, try one or more of the following fixes:</span></span>

- <span data-ttu-id="ff9ec-211">壁にホログラムを配置する場合は、壁から 1 ~ 3 個のメーターを設置し、壁をまっすぐにします。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-211">When you place a hologram on a wall, stand between one and three meters from the wall and face the wall straight on.</span></span>
- <span data-ttu-id="ff9ec-212">壁をエアタップして、マッピングメッシュのグラフィックを表示します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-212">Air tap the wall to reveal the mapping mesh graphic.</span></span> <span data-ttu-id="ff9ec-213">メッシュが壁に沿って配置されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-213">Make sure that the mesh aligns with the wall.</span></span> <span data-ttu-id="ff9ec-214">そうでない場合は、ホログラムを削除し、壁を再スキャンしてから、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-214">If it doesn't, remove the hologram, rescan the wall, and then try again.</span></span>
- <span data-ttu-id="ff9ec-215">問題が引き続き発生する場合は、調整アプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-215">If the issue persists, run the Calibration app.</span></span> <span data-ttu-id="ff9ec-216">詳細については、[**設定**] [システムユーティリティ] を参照して  >    >  ください。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-216">You'll find it in **Settings** > **System** > **Utilities**.</span></span>

[<span data-ttu-id="ff9ec-217">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="ff9ec-217">Back to list</span></span>](#list)

## <a name="apps-appear-too-close-after-moving-them"></a><span data-ttu-id="ff9ec-218">移動後にアプリが近すぎて表示される</span><span class="sxs-lookup"><span data-stu-id="ff9ec-218">Apps appear too close after moving them</span></span>

<span data-ttu-id="ff9ec-219">HoloLens がさまざまな角度から領域をスキャンできるように、アプリを配置している領域を調べてみてください。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-219">Try walking around and looking at the area where you're placing the app so that HoloLens scans the area from different angles.</span></span> <span data-ttu-id="ff9ec-220">[デバイスバイザーをクリーニングする](hololens1-hardware.md#care-and-cleaning) こともできます。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-220">[Cleaning your device visor](hololens1-hardware.md#care-and-cleaning) may also help.</span></span>

[<span data-ttu-id="ff9ec-221">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="ff9ec-221">Back to list</span></span>](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a><span data-ttu-id="ff9ec-222">不安定または不正確なホログラムに関する問題を報告する</span><span class="sxs-lookup"><span data-stu-id="ff9ec-222">Reporting issues with unstable or inexact holograms</span></span>
 
1. <span data-ttu-id="ff9ec-223">問題のビデオを記録し、 [Mixed Reality をキャプチャ](holographic-photos-and-videos.md#capture-a-mixed-reality-video) してください。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-223">Please record and a [Mixed Reality Capture video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) of the issue.</span></span> <span data-ttu-id="ff9ec-224">このビデオは、後でフィードバックハブを使用して添付ファイルとしてアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-224">This video can be later uploaded through Feedback Hub as an attached file.</span></span>  
1. <span data-ttu-id="ff9ec-225">**設定** アプリを使用して完全なテレメトリを有効にする->**プライバシー**  ->  **診断 & のフィードバック** と、**オプションの診断データ** で、トグルが **On** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-225">Enable full telemetry via the **Settings** app -> **Privacy** -> **Diagnostics & feedback** and under **Optional diagnostics data** ensure the toggle is set to **On**</span></span>
1. <span data-ttu-id="ff9ec-226">最新の [Windows HOLOGRAPHIC OS (20H2 以降)](hololens-release-notes.md#windows-holographic-version-20h2)に更新して、最新のホログラムスケールと安定性の修正を取得します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-226">Get the latest hologram scale and stability fixes by updating to the latest [Windows Holographic OS, (20H2 or higher)](hololens-release-notes.md#windows-holographic-version-20h2).</span></span> <span data-ttu-id="ff9ec-227">更新後、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-227">After updating perform the following:</span></span>
    1. <span data-ttu-id="ff9ec-228">**設定** アプリを使用してすべてのホログラムを削除する->**システム**  ->  **ホログラム**-> [**すべてのホログラムを削除** し、新しいマップで開始する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-228">Remove all Holograms via **Settings** app -> **System** -> **Holograms** -> then select **Remove all holograms** and start with a fresh map.</span></span>
    1. <span data-ttu-id="ff9ec-229">HoloLens を装着して部屋に移動し、空間内のすべての領域とサーフェイスを確認することで、スペースの新しいマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-229">Create a new map of your space by wearing the HoloLens and walking around your room and looking at all areas and surfaces in the space.</span></span> <span data-ttu-id="ff9ec-230">これは、2-3 分間実行します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-230">Do this for 2-3 minutes.</span></span>
    1. <span data-ttu-id="ff9ec-231">IPD の調整を実行します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-231">Perform IPD calibration.</span></span> <span data-ttu-id="ff9ec-232">[**設定**] [システムユーティリティ] にアクセス  >    >  します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-232">Go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="ff9ec-233">[ **調整**] で [ **調整を開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-233">Under **Calibration**, select **Open Calibration**.</span></span>
    1. <span data-ttu-id="ff9ec-234">シナリオを再テストし、まだ永続化されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-234">Re-test the scenario and see if it still persists.</span></span>
1. <span data-ttu-id="ff9ec-235">更新によって問題が解決されない場合は、 [フィードバックハブの問題](hololens-feedback.md)を報告してください。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-235">If updating does not fix the issue, please file a [Feedback Hub issue](hololens-feedback.md).</span></span> <span data-ttu-id="ff9ec-236">フィードバックを入力したら、[ **共有** ] ボタンを使用して、サポートに連絡するときに送信できる、共有の簡単なリンクを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-236">After you've filled feedback you can use the **Share** button, to create an easy to share link that can be sent when contacting support.</span></span>

[<span data-ttu-id="ff9ec-237">リストに戻る</span><span class="sxs-lookup"><span data-stu-id="ff9ec-237">Back to list</span></span>](#list)