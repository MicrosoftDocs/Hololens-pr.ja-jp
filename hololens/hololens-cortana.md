---
title: 自分の声を使用して HoloLens を操作する
description: Cortana を使って、音声コマンド、ディクテーション、ホログラム操作など、HoloLens Mixed Reality デバイスであらゆる操作を行う方法について説明します。
ms.assetid: fd96fb0e-6759-4dbe-be1f-58bedad66fed
ms.date: 03/10/2020
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
audience: ITPro
ms.author: v-tea
ms.topic: article
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f6e3dd8f7dc90cea158d000251973ec75dc76a90
ms.sourcegitcommit: 07ffe1bf2f45dcb2ba9d7fbe54b4773a0fb9d525
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393871"
---
# <a name="use-your-voice-to-operate-hololens"></a><span data-ttu-id="73d8c-104">自分の声を使用して HoloLens を操作する</span><span class="sxs-lookup"><span data-stu-id="73d8c-104">Use your voice to operate HoloLens</span></span>

<span data-ttu-id="73d8c-105">HoloLens では、すばやく写真を撮影したり、アプリを開くなど、自分の声を使ってほとんどの操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="73d8c-105">You can use your voice to do almost anything on HoloLens, such as taking a quick photo or opening an app.</span></span> <span data-ttu-id="73d8c-106">HoloLens には多数の音声コマンドが組み込まれていますが、他のコマンドは Cortana 経由で使用できます。</span><span class="sxs-lookup"><span data-stu-id="73d8c-106">Many voice commands are built into HoloLens, while others are available through Cortana.</span></span>

<span data-ttu-id="73d8c-107">この記事では、自分の声と Cortana を使って HoloLens とホログラフィックの世界を制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="73d8c-107">This article teaches you how to control HoloLens and your holographic world with your voice and with Cortana.</span></span>

> [!NOTE]
> <span data-ttu-id="73d8c-108">音声認識は、[一部の言語](hololens2-language-support.md)のみでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="73d8c-108">Speech is only supported in [some languages](hololens2-language-support.md).</span></span> <span data-ttu-id="73d8c-109">音声言語は、キーボードの言語ではなく、Windows の表示言語に基づいています。</span><span class="sxs-lookup"><span data-stu-id="73d8c-109">The speech language is based on the Windows display language, not the keyboard language.</span></span>  
>  
> <span data-ttu-id="73d8c-110">Windows の表示言語は、**[設定]** > **[時刻と言語]** > **[言語]** を選択すると確認できます。</span><span class="sxs-lookup"><span data-stu-id="73d8c-110">You can verify the Windows display language by selecting **Settings** > **Time and Language** > **Language**.</span></span>

## <a name="built-in-voice-commands"></a><span data-ttu-id="73d8c-111">組み込みの音声コマンド</span><span class="sxs-lookup"><span data-stu-id="73d8c-111">Built-in voice commands</span></span>

<span data-ttu-id="73d8c-112">以下の基本コマンドを使用すると、HoloLens をすばやく操作できます。</span><span class="sxs-lookup"><span data-stu-id="73d8c-112">Get around HoloLens faster with these basic commands.</span></span> <span data-ttu-id="73d8c-113">基本コマンドを使用するには、デバイスの初回実行時か、**[設定]** > **[プライバシー]** > **[音声認識]** で音声認識を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="73d8c-113">In order to use these, you need to enable Speech during the first run of the device or in **Settings** > **Privacy** > **Speech**.</span></span> <span data-ttu-id="73d8c-114">音声認識が有効になっているかどうかは、スタート メニューの上部表示される "状態" でいつでも確認できます。</span><span class="sxs-lookup"><span data-stu-id="73d8c-114">You can always check whether speech is enabled by looking at the status at the top of the Start menu.</span></span> <span data-ttu-id="73d8c-115">最適な音声認識の結果を得るために、HoloLens 2 は、Microsoft クラウドベースのサービスを使用しています。</span><span class="sxs-lookup"><span data-stu-id="73d8c-115">For the best speech recognition results, HoloLens 2 uses the Microsoft cloud-based services.</span></span> <span data-ttu-id="73d8c-116">もちろん、[設定] を使用してこの機能を無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="73d8c-116">However, you can use Settings to disable this feature.</span></span> <span data-ttu-id="73d8c-117">この機能を無効にするには、[設定] で **オンライン音声認識**をオフにします。</span><span class="sxs-lookup"><span data-stu-id="73d8c-117">To do this, in Settings, turn off **Online speech recognition**.</span></span> <span data-ttu-id="73d8c-118">この設定を変更すると、HoloLens 2 は、コマンドとディクテーションを認識するためにローカルに音声データのみを処理し、Cortana は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="73d8c-118">After you change this setting, HoloLens 2 will only process voice data locally to recognize commands and dictation, and Cortana will not be available.</span></span>

### <a name="general-speech-commands"></a><span data-ttu-id="73d8c-119">一般的な音声コマンド</span><span class="sxs-lookup"><span data-stu-id="73d8c-119">General speech commands</span></span>

<span data-ttu-id="73d8c-120">次の音声コマンドは、すばやく操作するために Windows Mixed Reality 全体を通して使用できます。</span><span class="sxs-lookup"><span data-stu-id="73d8c-120">Use these commands throughout Windows Mixed Reality to get around faster.</span></span> <span data-ttu-id="73d8c-121">一部のコマンドでは視線カーソルが使用されます。これは「選択」と発声することで表示されます。</span><span class="sxs-lookup"><span data-stu-id="73d8c-121">Some commands use the gaze cursor, which you bring up by saying "select."</span></span>

> [!NOTE]
> <span data-ttu-id="73d8c-122">HoloLens (第 1 世代) では、ハンド レイがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="73d8c-122">Hand rays are not supported on HoloLens (1st Gen).</span></span>

| <span data-ttu-id="73d8c-123">音声コマンド</span><span class="sxs-lookup"><span data-stu-id="73d8c-123">Say this</span></span> | <span data-ttu-id="73d8c-124">目的</span><span class="sxs-lookup"><span data-stu-id="73d8c-124">To do this</span></span> |
| - | - |
| <span data-ttu-id="73d8c-125">「選択」</span><span class="sxs-lookup"><span data-stu-id="73d8c-125">"Select"</span></span> | <span data-ttu-id="73d8c-126">「選択」と言って視線カーソルを表示します。</span><span class="sxs-lookup"><span data-stu-id="73d8c-126">Say "select" to bring up the gaze cursor.</span></span> <span data-ttu-id="73d8c-127">次に、顔を向けて選択する対象の上にカーソルを置き、もう一度「選択」と言います。</span><span class="sxs-lookup"><span data-stu-id="73d8c-127">Then, turn your head to position the cursor on the thing you want to select, and say "select" again.</span></span> |
| <span data-ttu-id="73d8c-128">「スタートに移動」</span><span class="sxs-lookup"><span data-stu-id="73d8c-128">"Go to Start"</span></span> |  <span data-ttu-id="73d8c-129">スタート メニューを開く</span><span class="sxs-lookup"><span data-stu-id="73d8c-129">Open the Start menu</span></span> |
| <span data-ttu-id="73d8c-130">「閉じる」</span><span class="sxs-lookup"><span data-stu-id="73d8c-130">"Close"</span></span>  | <span data-ttu-id="73d8c-131">スタート メニューを閉じる</span><span class="sxs-lookup"><span data-stu-id="73d8c-131">Close the Start menu</span></span> |
| <span data-ttu-id="73d8c-132">「スタートに移動」と言ってクイック アクション メニューを表示し、「Mixed Reality ホーム」と言います。</span><span class="sxs-lookup"><span data-stu-id="73d8c-132">Say "Go to Start" to bring up the quick actions menu, then say "Mixed reality home."</span></span>  | <span data-ttu-id="73d8c-133">イマーシブ アプリを終了する</span><span class="sxs-lookup"><span data-stu-id="73d8c-133">Leave an immersive app</span></span> |
| <span data-ttu-id="73d8c-134">「ハンド レイを表示しない」 / 「ハンド レイを表示する」</span><span class="sxs-lookup"><span data-stu-id="73d8c-134">"Hide hand ray" / "Show hand ray"</span></span> | <span data-ttu-id="73d8c-135">ハンドレイの非表示と表示</span><span class="sxs-lookup"><span data-stu-id="73d8c-135">Hide and show hand ray</span></span> |
| <span data-ttu-id="73d8c-136">「音声操作の項目」</span><span class="sxs-lookup"><span data-stu-id="73d8c-136">"What can I say?"</span></span>  | <span data-ttu-id="73d8c-137">使用可能な音声コマンドを表示する</span><span class="sxs-lookup"><span data-stu-id="73d8c-137">See available speech commands</span></span> |

<span data-ttu-id="73d8c-138">HoloLens 2 のバージョン 19041.x 以降、次のコマンドを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="73d8c-138">Starting with version 19041.x of HoloLens 2, you can also use these commands:</span></span>

| <span data-ttu-id="73d8c-139">音声コマンド</span><span class="sxs-lookup"><span data-stu-id="73d8c-139">Say this</span></span> | <span data-ttu-id="73d8c-140">目的</span><span class="sxs-lookup"><span data-stu-id="73d8c-140">To do this</span></span> |
| - | - |
| <span data-ttu-id="73d8c-141">デバイスを再起動</span><span class="sxs-lookup"><span data-stu-id="73d8c-141">"Restart device"</span></span> | <span data-ttu-id="73d8c-142">デバイスを再起動するかどうかを確認するダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="73d8c-142">Bring up a dialogue to confirm you want to restart the device.</span></span> <span data-ttu-id="73d8c-143">「はい」と言って再起動します。</span><span class="sxs-lookup"><span data-stu-id="73d8c-143">You can say "yes" to restart.</span></span> |
| <span data-ttu-id="73d8c-144">デバイスをシャットダウン</span><span class="sxs-lookup"><span data-stu-id="73d8c-144">"Shutdown device"</span></span> | <span data-ttu-id="73d8c-145">デバイスの電源を切るかどうかを確認するダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="73d8c-145">Bring up a dialogue to confirm you want to turn off the device.</span></span> <span data-ttu-id="73d8c-146">「はい」と言って確認します。</span><span class="sxs-lookup"><span data-stu-id="73d8c-146">You can say "yes" to confirm.</span></span> |
| <span data-ttu-id="73d8c-147">「明るさを上げる」/「明るさを下げる」</span><span class="sxs-lookup"><span data-stu-id="73d8c-147">"Brightness up/down"</span></span> | <span data-ttu-id="73d8c-148">ディスプレイの明るさを 10% 上げるまたは下げます。</span><span class="sxs-lookup"><span data-stu-id="73d8c-148">Increase or decrease the display brightness by 10%.</span></span> |
| <span data-ttu-id="73d8c-149">「音量を上げる」/「音量を下げる」</span><span class="sxs-lookup"><span data-stu-id="73d8c-149">"Volume up/down"</span></span> | <span data-ttu-id="73d8c-150">音量を 10% 上げるまたは下げます。</span><span class="sxs-lookup"><span data-stu-id="73d8c-150">Increase or decrease the volume by 10%.</span></span> |
| <span data-ttu-id="73d8c-151">「自分の IP」</span><span class="sxs-lookup"><span data-stu-id="73d8c-151">"What's my IP address"</span></span> | <span data-ttu-id="73d8c-152">ローカル ネットワーク上のデバイスの現在の IP アドレスを表示するダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="73d8c-152">Bring up a dialogue displaying your device's current IP address on the local network.</span></span> |
| <span data-ttu-id="73d8c-153">「写真を撮る」</span><span class="sxs-lookup"><span data-stu-id="73d8c-153">"Take a picture"</span></span> | <span data-ttu-id="73d8c-154">実際に見ているものの Mixed Reality 写真を撮ります。</span><span class="sxs-lookup"><span data-stu-id="73d8c-154">Capture a mixed reality photo of what you are currently seeing.</span></span> |
| <span data-ttu-id="73d8c-155">「ビデオを撮る」</span><span class="sxs-lookup"><span data-stu-id="73d8c-155">"Take a video"</span></span> | <span data-ttu-id="73d8c-156">Mixed Reality ビデオの録画を開始します。</span><span class="sxs-lookup"><span data-stu-id="73d8c-156">Start recording a mixed reality video.</span></span> | 
| <span data-ttu-id="73d8c-157">「ビデオの停止」</span><span class="sxs-lookup"><span data-stu-id="73d8c-157">"Stop recording"</span></span> | <span data-ttu-id="73d8c-158">現在、Mixed Reality ビデオを録画している場合は停止します。</span><span class="sxs-lookup"><span data-stu-id="73d8c-158">Stops the current mixed reality video recording if one is in progress.</span></span> |

### <a name="hologram-commands"></a><span data-ttu-id="73d8c-159">ホログラム コマンド</span><span class="sxs-lookup"><span data-stu-id="73d8c-159">Hologram commands</span></span>

<span data-ttu-id="73d8c-160">ホログラム コマンドを使用するには、3D オブジェクト、ホログラム、またはアプリ ウィンドウを見つめます。</span><span class="sxs-lookup"><span data-stu-id="73d8c-160">To use these commands, gaze at a 3D object, hologram, or app window.</span></span>

| <span data-ttu-id="73d8c-161">音声コマンド</span><span class="sxs-lookup"><span data-stu-id="73d8c-161">Say this</span></span> | <span data-ttu-id="73d8c-162">目的</span><span class="sxs-lookup"><span data-stu-id="73d8c-162">To do this</span></span> |
| - | - |
| <span data-ttu-id="73d8c-163">「拡大」</span><span class="sxs-lookup"><span data-stu-id="73d8c-163">"Bigger"</span></span> | <span data-ttu-id="73d8c-164">もっと大きく</span><span class="sxs-lookup"><span data-stu-id="73d8c-164">Make it bigger</span></span> |
| <span data-ttu-id="73d8c-165">「もっと小さく」</span><span class="sxs-lookup"><span data-stu-id="73d8c-165">"Smaller"</span></span> | <span data-ttu-id="73d8c-166">小さくする</span><span class="sxs-lookup"><span data-stu-id="73d8c-166">Make it smaller</span></span> |
| <span data-ttu-id="73d8c-167">「正面から見る」</span><span class="sxs-lookup"><span data-stu-id="73d8c-167">"Face me"</span></span> | <span data-ttu-id="73d8c-168">正面が見えるように向きを変える</span><span class="sxs-lookup"><span data-stu-id="73d8c-168">Turn it to face you</span></span> |
| <span data-ttu-id="73d8c-169">「これを動かす」</span><span class="sxs-lookup"><span data-stu-id="73d8c-169">"Move this"</span></span> | <span data-ttu-id="73d8c-170">視線に合わせて移動する</span><span class="sxs-lookup"><span data-stu-id="73d8c-170">Move it (follow your gaze)</span></span> |
| <span data-ttu-id="73d8c-171">「閉じる」</span><span class="sxs-lookup"><span data-stu-id="73d8c-171">"Close"</span></span> | <span data-ttu-id="73d8c-172">閉じる</span><span class="sxs-lookup"><span data-stu-id="73d8c-172">Close it</span></span> |
| <span data-ttu-id="73d8c-173">「一緒に移動」/「移動停止」</span><span class="sxs-lookup"><span data-stu-id="73d8c-173">"Follow me" / "Stop following"</span></span> | <span data-ttu-id="73d8c-174">ユーザーの動きに合わせて移動する</span><span class="sxs-lookup"><span data-stu-id="73d8c-174">Make it follow you as you move around</span></span> |

### <a name="see-it-say-it"></a><span data-ttu-id="73d8c-175">音声に対応しているコントロール</span><span class="sxs-lookup"><span data-stu-id="73d8c-175">See it, say it</span></span>

<span data-ttu-id="73d8c-176">HoloLens の多くのボタンや他の要素も、ユーザーの声に応答します。たとえば、アプリ バーの **[一緒に移動]** や **[閉じる]**、Edge の **[戻る]** ボタンなどです。</span><span class="sxs-lookup"><span data-stu-id="73d8c-176">Many buttons and other elements on HoloLens also respond to your voice—for example, **Follow me** and **Close** on the app bar, or the **Back** button in Edge.</span></span> <span data-ttu-id="73d8c-177">ボタンが音声に対応しているかどうかを確認するには、**視線カーソル**、**タッチ カーソル**、または**ハンド レイ**をしばらく置いてください。</span><span class="sxs-lookup"><span data-stu-id="73d8c-177">To find out if a button is voice-enabled, rest your **gaze cursor**, **touch cursor** or one **hand ray** on it for a moment.</span></span> <span data-ttu-id="73d8c-178">ボタンが音声に対応している場合、音声に関するヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="73d8c-178">If the button is voice-enabled, you'll see a voice tip.</span></span>

### <a name="dictation-mode"></a><span data-ttu-id="73d8c-179">ディクテーション モード</span><span class="sxs-lookup"><span data-stu-id="73d8c-179">Dictation mode</span></span>

<span data-ttu-id="73d8c-180">文字入力に疲れた場合、</span><span class="sxs-lookup"><span data-stu-id="73d8c-180">Tired of typing?</span></span> <span data-ttu-id="73d8c-181">ホログラフィック キーボードが有効であれば、いつでもディクテーション モードに切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="73d8c-181">Switch to dictation mode anytime that the holographic keyboard is active.</span></span> <span data-ttu-id="73d8c-182">開始するには、マイク ボタンを選択するか、「ディクテーションを開始」と言います。</span><span class="sxs-lookup"><span data-stu-id="73d8c-182">To get started, select the microphone button or say "Start dictating."</span></span> <span data-ttu-id="73d8c-183">ディクテーションを停止するには、ボタンをもう一度選択するか、「ディクテーションを停止」と言います。</span><span class="sxs-lookup"><span data-stu-id="73d8c-183">To stop dictating, select the button again or say "Stop dictating."</span></span> <span data-ttu-id="73d8c-184">ディクテーションの内容を削除するには、「それを削除」と言います。</span><span class="sxs-lookup"><span data-stu-id="73d8c-184">To delete what you just dictated, say "Delete that."</span></span> 

> [!NOTE]
> <span data-ttu-id="73d8c-185">ディクテーション モードを使用するには、インターネット接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="73d8c-185">To use dictation mode, you have to have an internet connection.</span></span>

<span data-ttu-id="73d8c-186">HoloLens ディクテーションでは、明示的な句読点を使用します。つまり、使用する句読点の名前を言う必要があります。</span><span class="sxs-lookup"><span data-stu-id="73d8c-186">HoloLens dictation uses explicit punctuation, meaning that you say the name of the punctuation you want to use.</span></span> <span data-ttu-id="73d8c-187">たとえば、「Hey **comma** what are you up to **question mark**」のように言うことができます。</span><span class="sxs-lookup"><span data-stu-id="73d8c-187">For instance, you might say "Hey **comma** what are you up to **question mark**."</span></span>

<span data-ttu-id="73d8c-188">使用できる句読点のキーワードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="73d8c-188">Here are the punctuation keywords that you can use:</span></span>

- <span data-ttu-id="73d8c-189">Period、comma、question mark、exclamation point/exclamation mark (ピリオド、コンマ、疑問符、感嘆符)</span><span class="sxs-lookup"><span data-stu-id="73d8c-189">Period, comma, question mark, exclamation point/exclamation mark</span></span>
- <span data-ttu-id="73d8c-190">New line/new paragraph (改行/新しい段落)</span><span class="sxs-lookup"><span data-stu-id="73d8c-190">New line/new paragraph</span></span>
- <span data-ttu-id="73d8c-191">Semicolon、colon (セミコロン、コロン)</span><span class="sxs-lookup"><span data-stu-id="73d8c-191">Semicolon, colon</span></span>
- <span data-ttu-id="73d8c-192">Open quote(s)、close quote(s) (始め引用符、終わり引用符)</span><span class="sxs-lookup"><span data-stu-id="73d8c-192">Open quote(s), close quote(s)</span></span>
- <span data-ttu-id="73d8c-193">Hashtag、smiley/smiley face、frowny, winky (ハッシュタグ、スマイル/笑顔、泣き顔、ウインク)</span><span class="sxs-lookup"><span data-stu-id="73d8c-193">Hashtag, smiley/smiley face, frowny, winky</span></span>
- <span data-ttu-id="73d8c-194">Dollar、percent (ドル、パーセント)</span><span class="sxs-lookup"><span data-stu-id="73d8c-194">Dollar, percent</span></span>

<span data-ttu-id="73d8c-195">メール アドレスなどの情報はスペルを指定した方がよい場合があります。</span><span class="sxs-lookup"><span data-stu-id="73d8c-195">Sometimes it's helpful to spell out things like email addresses.</span></span> <span data-ttu-id="73d8c-196">たとえば、example@outlook.com をディクテーションするには、「E X A M P L E at outlook dot com」と言います。</span><span class="sxs-lookup"><span data-stu-id="73d8c-196">For instance, to dictate example@outlook.com, you'd say "E X A M P L E at outlook dot com."</span></span>

## <a name="do-more-with-cortana"></a><span data-ttu-id="73d8c-197">Cortana をさらに活用する</span><span class="sxs-lookup"><span data-stu-id="73d8c-197">Do more with Cortana</span></span>

<span data-ttu-id="73d8c-198">Cortana は、HoloLens でさまざまな操作を実行する場合に役立ちます。ただし、使用している Windows Holographic のバージョンによって機能が異なります。</span><span class="sxs-lookup"><span data-stu-id="73d8c-198">Cortana can help you do all kinds of things on your HoloLens, but depending on which version of Windows Holographic you're using, the capabilities may be different.</span></span> <span data-ttu-id="73d8c-199">最新バージョンの Cortana の更新された機能に関する詳細情報は、次の URL をご覧ください。[今後リリーズ予定の Windows 10 の Cortana: 強化されたセキュリティとプライバシーで生産性を重視](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)。</span><span class="sxs-lookup"><span data-stu-id="73d8c-199">You can learn more about the updated capabilities of the latest version of Cortana here: [Cortana in the upcoming Windows 10 release: focused on your productivity with enhanced security and privacy](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).</span></span> 

![コルタナさん](images/cortana-on-hololens.png)

<span data-ttu-id="73d8c-201">話しかける内容の例を次に示します (最初に必ず「コルタナさん」と言ってください)。</span><span class="sxs-lookup"><span data-stu-id="73d8c-201">Here are some things you can try saying (remember to say "Hey Cortana" first).</span></span>

<span data-ttu-id="73d8c-202">**コルタナさん**...</span><span class="sxs-lookup"><span data-stu-id="73d8c-202">**Hey, Cortana**...</span></span>

- <span data-ttu-id="73d8c-203">What can I say? (音声操作の項目)</span><span class="sxs-lookup"><span data-stu-id="73d8c-203">What can I say?</span></span>
- <span data-ttu-id="73d8c-204">Launch <*app name*> (<アプリ名> を起動して)。</span><span class="sxs-lookup"><span data-stu-id="73d8c-204">Launch <*app name*>.</span></span>
- <span data-ttu-id="73d8c-205">What time is it? (今何時?)</span><span class="sxs-lookup"><span data-stu-id="73d8c-205">What time is it?</span></span>
- <span data-ttu-id="73d8c-206">Show me the latest NBA scores (NBA の最新スコアを教えて)。</span><span class="sxs-lookup"><span data-stu-id="73d8c-206">Show me the latest NBA scores.</span></span>
- <span data-ttu-id="73d8c-207">Tell me a joke (冗談を言って)。</span><span class="sxs-lookup"><span data-stu-id="73d8c-207">Tell me a joke.</span></span>

<span data-ttu-id="73d8c-208">*18362.x より前のバージョン*を使用している場合、以下のコマンドも使用できます。</span><span class="sxs-lookup"><span data-stu-id="73d8c-208">If you're using *version 18362.x or earlier*, you can also use these commands:</span></span>

<span data-ttu-id="73d8c-209">**コルタナさん**...</span><span class="sxs-lookup"><span data-stu-id="73d8c-209">**Hey, Cortana**...</span></span>

- <span data-ttu-id="73d8c-210">Increase the volume (音量を上げて)。</span><span class="sxs-lookup"><span data-stu-id="73d8c-210">Increase the volume.</span></span>
- <span data-ttu-id="73d8c-211">Decrease the brightness (画面を暗くして)。</span><span class="sxs-lookup"><span data-stu-id="73d8c-211">Decrease the brightness.</span></span>
- <span data-ttu-id="73d8c-212">Shut down (シャットダウンして)。</span><span class="sxs-lookup"><span data-stu-id="73d8c-212">Shut down.</span></span>
- <span data-ttu-id="73d8c-213">Restart (再起動して)。</span><span class="sxs-lookup"><span data-stu-id="73d8c-213">Restart.</span></span>
- <span data-ttu-id="73d8c-214">Go to sleep (スリープにして)。</span><span class="sxs-lookup"><span data-stu-id="73d8c-214">Go to sleep.</span></span>
- <span data-ttu-id="73d8c-215">Mute (ミュート)。</span><span class="sxs-lookup"><span data-stu-id="73d8c-215">Mute.</span></span>
- <span data-ttu-id="73d8c-216">Move <*app name*> here (<アプリ名> をここに移動して) (アプリの移動先とする位置を見つめながら)。</span><span class="sxs-lookup"><span data-stu-id="73d8c-216">Move <*app name*> here (gaze at the spot that you want the app to move to).</span></span>
- <span data-ttu-id="73d8c-217">Go to Start (スタートに移動)。</span><span class="sxs-lookup"><span data-stu-id="73d8c-217">Go to Start.</span></span>
- <span data-ttu-id="73d8c-218">Take a picture (写真を撮影)。</span><span class="sxs-lookup"><span data-stu-id="73d8c-218">Take a picture.</span></span>
- <span data-ttu-id="73d8c-219">Start recording (録画開始) </span><span class="sxs-lookup"><span data-stu-id="73d8c-219">Start recording.</span></span> <span data-ttu-id="73d8c-220">(ビデオの録画をはじめ)。</span><span class="sxs-lookup"><span data-stu-id="73d8c-220">(Starts recording a video.)</span></span>
- <span data-ttu-id="73d8c-221">Stop recording (録画停止) </span><span class="sxs-lookup"><span data-stu-id="73d8c-221">Stop recording.</span></span> <span data-ttu-id="73d8c-222">(ビデオの録画を停止します)。</span><span class="sxs-lookup"><span data-stu-id="73d8c-222">(Stops recording a video.)</span></span>
- <span data-ttu-id="73d8c-223">How much battery do I have left? (バッテリー残量を教えて。)</span><span class="sxs-lookup"><span data-stu-id="73d8c-223">How much battery do I have left?</span></span>

<span data-ttu-id="73d8c-224">PC 上の Windows またはスマートフォンでよく使われる Cortana 機能の一部 (リマインダーや通知など) は、Microsoft HoloLens ではサポートされていません。また、Cortana のエクスペリエンスは地域によって異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="73d8c-224">Some Cortana features that you're used to from Windows on your PC or phone (for example, reminders and notifications) aren't supported in Microsoft HoloLens, and the Cortana experience may vary from one region to another.</span></span>

### <a name="turn-cortana-off"></a><span data-ttu-id="73d8c-225">Cortana をオフにする</span><span class="sxs-lookup"><span data-stu-id="73d8c-225">Turn Cortana off</span></span>

<span data-ttu-id="73d8c-226">音声認識を有効にすると、HoloLens を初めて使用するときに Cortana がオンになります。</span><span class="sxs-lookup"><span data-stu-id="73d8c-226">Cortana is on the first time you use HoloLens when you enable speech.</span></span> <span data-ttu-id="73d8c-227">Cortana の設定でオフにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="73d8c-227">You can turn her off in Cortana's settings.</span></span> <span data-ttu-id="73d8c-228">**[すべてのアプリ]** の一覧で、**[Cortana]** > **[設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="73d8c-228">In the **All apps** list, select **Cortana** > **Settings**.</span></span> <span data-ttu-id="73d8c-229">次に、[Cortana は、おすすめの最新情報の表示、リマインダーや通知を設定、その他さまざまなことができます] をオフにします。</span><span class="sxs-lookup"><span data-stu-id="73d8c-229">Then turn off Cortana can give you suggestions, ideas, reminders, alerts, and more.</span></span>

<span data-ttu-id="73d8c-230">「コルタナさん」と言っても Cortana が応答しない場合は、音声認識が有効になっていることをスタート画面で確認し、Cortana の設定に移動して、Cortana がオンになっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="73d8c-230">If Cortana isn't responding to "Hey Cortana," check that speech is enabled on Start and go to Cortana's settings and check to make sure she's on.</span></span>
