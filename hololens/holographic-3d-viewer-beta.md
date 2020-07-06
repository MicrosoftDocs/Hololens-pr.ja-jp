---
title: HoloLens で 3D ビューアーを使う (第 1 世代)
description: HoloLens (第 1 世代) の 3D ビューアーがサポートするファイルの種類と機能、およびアプリの使用方法とトラブルシューティング方法について説明します。
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 10/30/2019
ms.reviewer: scooley
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 47fe1fd5dc164c56ce22a09d7edf5bffdb60ea14
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10828889"
---
# <span data-ttu-id="d1557-103">HoloLens で 3D ビューアーを使う (第 1 世代)</span><span class="sxs-lookup"><span data-stu-id="d1557-103">Using 3D Viewer on HoloLens (1st gen)</span></span>

<span data-ttu-id="d1557-104">3D ビューアーを使用すると、HoloLens (第 1 世代) で 3D モデルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="d1557-104">3D Viewer lets you view 3D models on HoloLens (1st gen).</span></span> <span data-ttu-id="d1557-105">Microsoft Edge、OneDrive、およびその他のアプリから、*サポートされている* .fbx ファイルを開いて表示できます。</span><span class="sxs-lookup"><span data-stu-id="d1557-105">You can open and view *supported* .fbx files from Microsoft Edge, OneDrive, and other apps.</span></span>

>[!NOTE]
><span data-ttu-id="d1557-106">この記事は、.fbx ファイルをサポートし、HoloLens (第 1 世代) でのみ利用できるイマーシブ Unity **3D ビューアー** アプリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d1557-106">This article applies to the immersive Unity **3D Viewer** app, which supports .fbx files and is only available on HoloLens (1st gen).</span></span> <span data-ttu-id="d1557-107">HoloLens 2 にプリインストールされている **3D ビューアー** アプリは、Mixed Reality ホームでカスタム .glb 3D モデルを開くことができます (詳細については、「[資産要件の概要](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="d1557-107">The pre-installed **3D Viewer** app on HoloLens 2 supports opening custom .glb 3D models in the mixed reality home (see [Asset requirements overview](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) for more details.</span></span>

<span data-ttu-id="d1557-108">3D ビューアーで 3D モデルを開けない場合、または 3D モデルの特定の機能がサポートされていない場合は、「[サポートされるコンテンツの仕様](#supported-content-specifications)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1557-108">If you're having trouble opening a 3D model in 3D Viewer, or certain features of your 3D model are unsupported, see [Supported content specifications](#supported-content-specifications).</span></span>

<span data-ttu-id="d1557-109">3D ビューアーで使用する 3D モデルを作成または最適化するには、「[3D ビューアー用の 3D モデルの最適化](#optimizing-3d-models-for-3d-viewer)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1557-109">To build or optimize 3D models for use with 3D Viewer, see [Optimizing 3D models for 3D Viewer](#optimizing-3d-models-for-3d-viewer).</span></span>

<span data-ttu-id="d1557-110">HoloLens で 3D モデルを開く方法は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="d1557-110">There are two ways to open a 3D model on HoloLens.</span></span> <span data-ttu-id="d1557-111">詳細については、「[HoloLens での FBX ファイルの表示](#viewing-fbx-files-on-hololens)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1557-111">See [Viewing FBX files on HoloLens](#viewing-fbx-files-on-hololens) to learn more.</span></span>

<span data-ttu-id="d1557-112">これらのトピックを読んでも問題が発生した場合は、「[トラブルシューティング](#troubleshooting)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d1557-112">If you're having trouble after reading these topics, see [Troubleshooting](#troubleshooting).</span></span>

## <span data-ttu-id="d1557-113">サポートされるコンテンツの仕様</span><span class="sxs-lookup"><span data-stu-id="d1557-113">Supported content specifications</span></span>

### <span data-ttu-id="d1557-114">ファイル形式</span><span class="sxs-lookup"><span data-stu-id="d1557-114">File format</span></span>

- <span data-ttu-id="d1557-115">FBX 形式</span><span class="sxs-lookup"><span data-stu-id="d1557-115">FBX format</span></span>
- <span data-ttu-id="d1557-116">FBX の最大リリース 2015.1.0</span><span class="sxs-lookup"><span data-stu-id="d1557-116">Maximum FBX release 2015.1.0</span></span>

### <span data-ttu-id="d1557-117">ファイル サイズ</span><span class="sxs-lookup"><span data-stu-id="d1557-117">File size</span></span>

- <span data-ttu-id="d1557-118">最小 5 KB</span><span class="sxs-lookup"><span data-stu-id="d1557-118">Minimum 5 KB</span></span>
- <span data-ttu-id="d1557-119">最大 500 MB</span><span class="sxs-lookup"><span data-stu-id="d1557-119">Maximum 500 MB</span></span>

### <span data-ttu-id="d1557-120">ジオメトリ</span><span class="sxs-lookup"><span data-stu-id="d1557-120">Geometry</span></span>

- <span data-ttu-id="d1557-121">多角形モデルのみ。</span><span class="sxs-lookup"><span data-stu-id="d1557-121">Polygonal models only.</span></span> <span data-ttu-id="d1557-122">サブディビジョン サーフェスまたは NURBS なし</span><span class="sxs-lookup"><span data-stu-id="d1557-122">No subdivision surfaces or NURBs</span></span>
- <span data-ttu-id="d1557-123">右手座標系</span><span class="sxs-lookup"><span data-stu-id="d1557-123">Right-handed coordinate system</span></span>
- <span data-ttu-id="d1557-124">変換マトリックスのせん断はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="d1557-124">Shear in transformation matrices is not supported</span></span>

### <span data-ttu-id="d1557-125">テクスチャ</span><span class="sxs-lookup"><span data-stu-id="d1557-125">Textures</span></span>

- <span data-ttu-id="d1557-126">テクスチャ マップは FBX ファイルに埋め込む必要があります</span><span class="sxs-lookup"><span data-stu-id="d1557-126">Texture maps must be embedded in the FBX file</span></span>
- <span data-ttu-id="d1557-127">サポートされている画像形式</span><span class="sxs-lookup"><span data-stu-id="d1557-127">Supported image formats</span></span>
  - <span data-ttu-id="d1557-128">JPEG および PNG 画像</span><span class="sxs-lookup"><span data-stu-id="d1557-128">JPEG and PNG images</span></span>
  - <span data-ttu-id="d1557-129">BMP 画像 (24 ビット RGB トゥルー カラー)</span><span class="sxs-lookup"><span data-stu-id="d1557-129">BMP images (24-bit RGB true-color)</span></span>
  - <span data-ttu-id="d1557-130">TGA 画像 (24 ビット RGB および 32 ビット RGBQ トゥルー カラー)</span><span class="sxs-lookup"><span data-stu-id="d1557-130">TGA images (24-bit RGB and 32-bit RGBQ true-color)</span></span>
- <span data-ttu-id="d1557-131">2048x2048 の最大テクスチャ解像度</span><span class="sxs-lookup"><span data-stu-id="d1557-131">Maximum texture resolution of 2048x2048</span></span>
- <span data-ttu-id="d1557-132">メッシュごとに最大 1 つの拡散マップ、1 つの法線マップ、および 1 つの反射キューブ マップ</span><span class="sxs-lookup"><span data-stu-id="d1557-132">Maximum of one diffuse map, one normal map, and one reflection cube map per mesh</span></span>
- <span data-ttu-id="d1557-133">50% 未満の場合、拡散テクスチャのアルファ チャネルによりピクセルが破棄される</span><span class="sxs-lookup"><span data-stu-id="d1557-133">Alpha channel in diffuse textures causes pixels to be discarded if below 50%</span></span>

### <span data-ttu-id="d1557-134">アニメーション</span><span class="sxs-lookup"><span data-stu-id="d1557-134">Animation</span></span>

- <span data-ttu-id="d1557-135">個々のオブジェクトのスケーリング、回転、移動アニメーション</span><span class="sxs-lookup"><span data-stu-id="d1557-135">Scale/rotation/translation animation on individual objects</span></span>
- <span data-ttu-id="d1557-136">スキン適用のスケルタル (リギング) アニメーション</span><span class="sxs-lookup"><span data-stu-id="d1557-136">Skeletal (rigged) animation with skinning</span></span>
  - <span data-ttu-id="d1557-137">頂点ごとに最大 4 つの影響</span><span class="sxs-lookup"><span data-stu-id="d1557-137">Maximum of 4 influences per vertex</span></span>

### <span data-ttu-id="d1557-138">素材</span><span class="sxs-lookup"><span data-stu-id="d1557-138">Materials</span></span>

- <span data-ttu-id="d1557-139">ランバートおよびフォン素材がサポートされ、パラメータを調整できます</span><span class="sxs-lookup"><span data-stu-id="d1557-139">Lambert and Phong materials are supported, with adjustable parameters</span></span>
- <span data-ttu-id="d1557-140">ランバートでサポートされている素材の特性</span><span class="sxs-lookup"><span data-stu-id="d1557-140">Supported material properties for Lambert</span></span>
  - <span data-ttu-id="d1557-141">メイン テクスチャ (RGB + アルファ テスト)</span><span class="sxs-lookup"><span data-stu-id="d1557-141">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="d1557-142">拡散色 (RGB)</span><span class="sxs-lookup"><span data-stu-id="d1557-142">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="d1557-143">アンビエント色 (RGB)</span><span class="sxs-lookup"><span data-stu-id="d1557-143">Ambient Color (RGB)</span></span>
- <span data-ttu-id="d1557-144">フォンでサポートされている素材プロパティ</span><span class="sxs-lookup"><span data-stu-id="d1557-144">Supported material properties for Phong</span></span>
  - <span data-ttu-id="d1557-145">メイン テクスチャ (RGB + アルファ テスト)</span><span class="sxs-lookup"><span data-stu-id="d1557-145">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="d1557-146">拡散色 (RGB)</span><span class="sxs-lookup"><span data-stu-id="d1557-146">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="d1557-147">アンビエント色 (RGB)</span><span class="sxs-lookup"><span data-stu-id="d1557-147">Ambient Color (RGB)</span></span>
  - <span data-ttu-id="d1557-148">反射の色 (RGB)</span><span class="sxs-lookup"><span data-stu-id="d1557-148">Specular Color (RGB)</span></span>
  - <span data-ttu-id="d1557-149">光輝</span><span class="sxs-lookup"><span data-stu-id="d1557-149">Shininess</span></span>
  - <span data-ttu-id="d1557-150">反射率</span><span class="sxs-lookup"><span data-stu-id="d1557-150">Reflectivity</span></span>
- <span data-ttu-id="d1557-151">カスタム素材はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="d1557-151">Custom materials are not supported</span></span>
- <span data-ttu-id="d1557-152">メッシュごとに最大 1 つの素材</span><span class="sxs-lookup"><span data-stu-id="d1557-152">Maximum of one material per mesh</span></span>
- <span data-ttu-id="d1557-153">最大 1 つの素材レイヤー</span><span class="sxs-lookup"><span data-stu-id="d1557-153">Maximum of one material layer</span></span>
- <span data-ttu-id="d1557-154">ファイルごとに最大 8 つの素材</span><span class="sxs-lookup"><span data-stu-id="d1557-154">Maximum of 8 materials per file</span></span>

### <span data-ttu-id="d1557-155">ファイルとモデルの制限</span><span class="sxs-lookup"><span data-stu-id="d1557-155">File and model limitations</span></span>

<span data-ttu-id="d1557-156">3D ビューアーで同時に開くことができるモデル、頂点、メッシュの数だけでなく、ファイルのサイズにも厳しい制限があります。</span><span class="sxs-lookup"><span data-stu-id="d1557-156">There are hard limits on the size of files, as well as the number of models, vertices, and meshes that can be open simultaneously in 3D Viewer:</span></span>

- <span data-ttu-id="d1557-157">モデルごとに最大 500 MB のファイル サイズ</span><span class="sxs-lookup"><span data-stu-id="d1557-157">500 MB maximum file size per model</span></span>
- <span data-ttu-id="d1557-158">頂点: すべてのオープン モデルで合計 600,000</span><span class="sxs-lookup"><span data-stu-id="d1557-158">Vertices: 600,000 combined on all open models</span></span>
- <span data-ttu-id="d1557-159">メッシュ: すべてのオープン モデルで合計 1,600</span><span class="sxs-lookup"><span data-stu-id="d1557-159">Meshes: 1,600 combined on all open models</span></span>
- <span data-ttu-id="d1557-160">一度に最大 40 個のモデルを開く</span><span class="sxs-lookup"><span data-stu-id="d1557-160">Maximum of 40 models open at one time</span></span>

## <span data-ttu-id="d1557-161">3D ビューアー用に 3D モデルを最適化する</span><span class="sxs-lookup"><span data-stu-id="d1557-161">Optimizing 3D models for 3D Viewer</span></span>

### <span data-ttu-id="d1557-162">特別な考慮事項</span><span class="sxs-lookup"><span data-stu-id="d1557-162">Special considerations</span></span>

- <span data-ttu-id="d1557-163">テクスチャ マップの黒い素材や黒い領域は避けてください。</span><span class="sxs-lookup"><span data-stu-id="d1557-163">Avoid black materials or black areas in texture maps.</span></span> <span data-ttu-id="d1557-164">ホログラムは光でできているため、HoloLens は黒 (光がない場合) を透明としてレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="d1557-164">Holograms are made of light, thus HoloLens renders black (the absence of light) as transparent.</span></span>
- <span data-ttu-id="d1557-165">作成ツールから FBX にエクスポートする前に、すべてのジオメトリが表示され、ロックが解除されていること、およびジオメトリを含むレイヤーがオフになっていないか、テンプレート化されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d1557-165">Before exporting to FBX from your creation tool, ensure all geometry is visible and unlocked and no layers that contain geometry are turned off or templated.</span></span> <span data-ttu-id="d1557-166">可視性は考慮されません。</span><span class="sxs-lookup"><span data-stu-id="d1557-166">Visibility is not respected.</span></span>
- <span data-ttu-id="d1557-167">ノード間の非常に大きな変換オフセット (たとえば、100,000 単位) は避けてください。</span><span class="sxs-lookup"><span data-stu-id="d1557-167">Avoid very large translation offsets between nodes (for example, 100,000 units).</span></span> <span data-ttu-id="d1557-168">これにより、移動、スケーリング、回転中にモデルが揺れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d1557-168">This can cause the model to jitter while being moved/scaled/rotated.</span></span>

### <span data-ttu-id="d1557-169">パフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="d1557-169">Performance optimization</span></span>

<span data-ttu-id="d1557-170">コンテンツを作成するときはパフォーマンスを念頭に置き、作成プロセス中に HoloLens の 3D ビューアー アプリで検証して、最良の結果を得てください。</span><span class="sxs-lookup"><span data-stu-id="d1557-170">Keep performance in mind while authoring content and validate in the 3D Viewer app on HoloLens during the authoring process for best results.</span></span> <span data-ttu-id="d1557-171">3D ビューアーはコンテンツをリアルタイムでレンダリングし、パフォーマンスは HoloLens のハードウェア機能の影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="d1557-171">3D Viewer renders content real-time and performance is subject to HoloLens hardware capabilities.</span></span>  

<span data-ttu-id="d1557-172">3D モデルには、パフォーマンスに影響を与える可能性のある多くの変数があります。</span><span class="sxs-lookup"><span data-stu-id="d1557-172">There are many variables in a 3D model that can impact performance.</span></span> <span data-ttu-id="d1557-173">3D ビューアーは、150,000 個以上の頂点または 400 個以上のメッシュがある場合、読み込む際に警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="d1557-173">3D Viewer will show a warning on load if there are more than 150,000 vertices or more than 400 meshes.</span></span> <span data-ttu-id="d1557-174">アニメーションは、他のオープン モデルのパフォーマンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d1557-174">Animations can have an impact on the performance of other open models.</span></span> <span data-ttu-id="d1557-175">3D ビューアーで同時に開くことができるモデル、頂点、メッシュの総数にも厳しい制限があります (「[ファイルとモデルの制限](#file-and-model-limitations)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="d1557-175">There are also hard limits on the total number models, vertices, and meshes that can be open simultaneously in 3D Viewer (see [File and model limitations](#file-and-model-limitations)).</span></span>  

<span data-ttu-id="d1557-176">モデルの複雑さが原因で 3D モデルがうまく機能しない場合は、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="d1557-176">If the 3D model isn't running well due to model complexity, consider:</span></span>

- <span data-ttu-id="d1557-177">多角形の数を減らす</span><span class="sxs-lookup"><span data-stu-id="d1557-177">Reducing polygon count</span></span>
- <span data-ttu-id="d1557-178">スケルタル アニメーションのボーンの数を減らす</span><span class="sxs-lookup"><span data-stu-id="d1557-178">Reducing number of bones in rigged animation</span></span>
- <span data-ttu-id="d1557-179">自己遮蔽を回避する</span><span class="sxs-lookup"><span data-stu-id="d1557-179">Avoiding self-occlusion</span></span>

<span data-ttu-id="d1557-180">3D ビューアーでは両面レンダリングがサポートされていますが、パフォーマンス上の理由から既定ではオフになっています。</span><span class="sxs-lookup"><span data-stu-id="d1557-180">Double-sided rendering is supported in 3D Viewer, although it is turned off by default for performance reasons.</span></span> <span data-ttu-id="d1557-181">これは、**詳細**ページの [**両面**] ボタンでオンにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d1557-181">This can be turned on via the **Double Sided** button on the **Details** page.</span></span> <span data-ttu-id="d1557-182">最高のパフォーマンスのためには、コンテンツで両面レンダリングを行う必要がないようにします。</span><span class="sxs-lookup"><span data-stu-id="d1557-182">For best performance, avoid the need for double-sided rendering in your content.</span></span>

### <span data-ttu-id="d1557-183">3D モデルの検証</span><span class="sxs-lookup"><span data-stu-id="d1557-183">Validating your 3D model</span></span>

<span data-ttu-id="d1557-184">HoloLens の 3D ビューアーでモデルを開いて検証します。</span><span class="sxs-lookup"><span data-stu-id="d1557-184">Validate your model by opening it in 3D Viewer on HoloLens.</span></span> <span data-ttu-id="d1557-185">[**詳細**] ボタンを選択して、サポートされていないコンテンツ (存在する場合) のモデルの特性と警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="d1557-185">Select the **Details** button to view your model's characteristics and warnings of unsupported content (if present).</span></span>

### <span data-ttu-id="d1557-186">実物大の 3D モデルのレンダリング</span><span class="sxs-lookup"><span data-stu-id="d1557-186">Rendering 3D models with true-to-life dimensions</span></span>

<span data-ttu-id="d1557-187">既定では、3D ビューアーは 3D モデルをユーザーに対して適切なサイズと位置で表示します。</span><span class="sxs-lookup"><span data-stu-id="d1557-187">By default, 3D Viewer displays 3D models at a comfortable size and position relative to the user.</span></span> <span data-ttu-id="d1557-188">ただし、実際の測定で 3D モデルをレンダリングすることが重要な場合 (たとえば、部屋の家具モデルを評価する場合)、コンテンツ作成者はファイルのメタデータ内にフラグを設定して、アプリケーションとユーザーの両方によるそのモデルのサイズ変更を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="d1557-188">However, if rendering a 3D model with true-to-life measurements is important (for example, when evaluating furniture models in a room), the content creator can set a flag within the file's metadata to prevent resizing of that model by both the application and the user.</span></span>

<span data-ttu-id="d1557-189">モデルのスケーリングを防止するには、ブール値のカスタム属性をシーン内の Microsoft_DisableScale という名前のオブジェクトに追加し、それを true に設定します。</span><span class="sxs-lookup"><span data-stu-id="d1557-189">To prevent scaling of the model, add a Boolean custom attribute to any object in the scene named Microsoft_DisableScale and set it to true.</span></span> <span data-ttu-id="d1557-190">3D ビューアーは、FBX ファイルにベイクされた FbxSystemUnit 情報を尊重します。</span><span class="sxs-lookup"><span data-stu-id="d1557-190">3D Viewer will then respect the FbxSystemUnit information baked into the FBX file.</span></span> <span data-ttu-id="d1557-191">3D ビューアーのスケールは、FBX ユニットごとに 1 メートルです。</span><span class="sxs-lookup"><span data-stu-id="d1557-191">Scale in 3D Viewer is 1 meter per FBX unit.</span></span>

## <span data-ttu-id="d1557-192">HoloLens での FBX ファイルの表示</span><span class="sxs-lookup"><span data-stu-id="d1557-192">Viewing FBX files on HoloLens</span></span>

### <span data-ttu-id="d1557-193">Microsoft Edge から FBX ファイルを開く</span><span class="sxs-lookup"><span data-stu-id="d1557-193">Open an FBX file from Microsoft Edge</span></span>

<span data-ttu-id="d1557-194">FBX ファイルは、HoloLens の Microsoft Edge を使用して Web サイトから直接開くことができます。</span><span class="sxs-lookup"><span data-stu-id="d1557-194">FBX files can be opened directly from a website using Microsoft Edge on HoloLens.</span></span>

1. <span data-ttu-id="d1557-195">Microsoft Edge で、表示する FBX ファイルを含む Web ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="d1557-195">In Microsoft Edge, navigate to the webpage containing the FBX file you want to view.</span></span>
1. <span data-ttu-id="d1557-196">ダウンロードするファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d1557-196">Select the file to download it.</span></span>
1. <span data-ttu-id="d1557-197">ダウンロードが完了したら、Microsoft Edge の [**開く**] ボタンを選択して、ファイルを 3D ビューアーで開きます。</span><span class="sxs-lookup"><span data-stu-id="d1557-197">When the download is complete, select the **Open** button in Microsoft Edge to open the file in 3D Viewer.</span></span>

<span data-ttu-id="d1557-198">ダウンロードしたファイルは、Microsoft Edge の [ダウンロード] を使用して、後でアクセスして開くことができます。</span><span class="sxs-lookup"><span data-stu-id="d1557-198">The downloaded file can be accessed and opened again later by using Downloads in Microsoft Edge.</span></span> <span data-ttu-id="d1557-199">3D モデルを保存してアクセスを継続するには、ファイルを PC にダウンロードして、OneDrive アカウントに保存します。</span><span class="sxs-lookup"><span data-stu-id="d1557-199">To save a 3D model and ensure continued access, download the file on your PC and save it to your OneDrive account.</span></span> <span data-ttu-id="d1557-200">その後、HoloLens の OneDrive アプリからファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="d1557-200">The file can then be opened from the OneDrive app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="d1557-201">ダウンロード可能な FBX モデルを備えた一部の Web サイトでは、圧縮された ZIP 形式でそれらを提供しています。</span><span class="sxs-lookup"><span data-stu-id="d1557-201">Some websites with downloadable FBX models provide them in compressed ZIP format.</span></span> <span data-ttu-id="d1557-202">3D ビューアーは、ZIP ファイルを直接開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="d1557-202">3D Viewer cannot open ZIP files directly.</span></span> <span data-ttu-id="d1557-203">代わりに、PC を使用して FBX ファイルを抽出し、OneDrive アカウントに保存します。</span><span class="sxs-lookup"><span data-stu-id="d1557-203">Instead, use your PC to extract the FBX file and save it to your OneDrive account.</span></span> <span data-ttu-id="d1557-204">その後、HoloLens の OneDrive アプリからファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="d1557-204">The file can then be opened from the OneDrive app on HoloLens.</span></span>

### <span data-ttu-id="d1557-205">OneDrive から FBX ファイルを開く</span><span class="sxs-lookup"><span data-stu-id="d1557-205">Open an FBX file from OneDrive</span></span>

<span data-ttu-id="d1557-206">FBX ファイルは、HoloLens の OneDrive アプリを使用して OneDrive から開くことができます。</span><span class="sxs-lookup"><span data-stu-id="d1557-206">FBX files can be opened from OneDrive by using the OneDrive app on HoloLens.</span></span> <span data-ttu-id="d1557-207">HoloLens の Microsoft Store アプリを使用して OneDrive をインストールし、FBX ファイルを PC の OneDrive に既にアップロードしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d1557-207">Be sure you've installed OneDrive using Microsoft Store app on HoloLens and that you've already uploaded the FBX file to OneDrive on your PC.</span></span>

<span data-ttu-id="d1557-208">OneDrive に入ると、次の 2 つの方法のいずれかで、3D ビューアーを使用して HoloLens で FBX ファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="d1557-208">Once in OneDrive, FBX files can be opened on HoloLens using 3D Viewer in one of two ways:</span></span>

- <span data-ttu-id="d1557-209">HoloLens で OneDrive を起動し、FBX ファイルを選択して 3D ビューアーで開きます。</span><span class="sxs-lookup"><span data-stu-id="d1557-209">Launch OneDrive on HoloLens and select the FBX file to open it in 3D Viewer.</span></span>
- <span data-ttu-id="d1557-210">3D ビューアーを起動し、エアタップしてツールバーを表示し、[**ファイルを開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1557-210">Launch 3D Viewer, air tap to show the toolbar, and select **Open File**.</span></span> <span data-ttu-id="d1557-211">OneDrive が起動し、FBX ファイルを選択できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d1557-211">OneDrive will launch, allowing you to select an FBX file.</span></span>

## <span data-ttu-id="d1557-212">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d1557-212">Troubleshooting</span></span>

### <span data-ttu-id="d1557-213">3D モデルを開くと警告が表示されない</span><span class="sxs-lookup"><span data-stu-id="d1557-213">I see a warning when I open a 3D model</span></span>

<span data-ttu-id="d1557-214">3D ビューアーでサポートされていない機能を含む 3D モデルを開こうとする場合、またはモデルが複雑すぎてパフォーマンスに影響を与える可能性がある場合は、警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1557-214">You will see a warning if you attempt to open a 3D model that contains features that are not supported by 3D Viewer, or if the model is too complex and performance may be affected.</span></span> <span data-ttu-id="d1557-215">3D ビューアーは引き続き 3D モデルを読み込みますか、パフォーマンスまたは視覚的な忠実さが損なわれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d1557-215">3D Viewer will still load the 3D model, but performance or visual fidelity may be compromised.</span></span>

<span data-ttu-id="d1557-216">詳細については、「[サポートされるコンテンツの仕様](#supported-content-specifications)」および「[3D ビューアー用に 3D モデルを最適化する](#optimizing-3d-models-for-3d-viewer)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1557-216">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer](#optimizing-3d-models-for-3d-viewer).</span></span>

### <span data-ttu-id="d1557-217">警告が表示され、3D モデルが読み込まれない</span><span class="sxs-lookup"><span data-stu-id="d1557-217">I see a warning and the 3D model doesn't load</span></span>

<span data-ttu-id="d1557-218">複雑さやファイル サイズが原因で 3D ビューアーが 3D モデルを読み込めない場合、または FBX ファイルが破損しているか無効な場合は、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1557-218">You will see an error message when 3D Viewer cannot load a 3D model due to complexity or file size, or if the FBX file is corrupt or invalid.</span></span> <span data-ttu-id="d1557-219">同時に開くことができるモデル、頂点、またはメッシュの総数の制限に達した場合も、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1557-219">You will also see an error message if you have reached the limit on the total number of models, vertices, or meshes that can be open simultaneously.</span></span>  

<span data-ttu-id="d1557-220">詳しくは、「[サポートされるコンテンツの仕様](#supported-content-specifications)」と「[ファイルとモデルの制限](#file-and-model-limitations)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d1557-220">For more info, see [Supported content specifications](#supported-content-specifications) and [File and model limitations](#file-and-model-limitations).</span></span>

<span data-ttu-id="d1557-221">モデルがサポートされるコンテンツの仕様を満たし、ファイルまたはモデルの制限を超えていないと思われる場合は、FBX ファイルを 3D ビューアー チーム (holoapps@microsoft.com) に送信できます。</span><span class="sxs-lookup"><span data-stu-id="d1557-221">If you feel your model meets the supported content specifications and has not exceeded the file or model limitations, you may send your FBX file to the 3D Viewer team at holoapps@microsoft.com.</span></span> <span data-ttu-id="d1557-222">個人的には対応できませんが、適切に読み込まれないファイルの例があれば、今後のバージョンアップに役立つでしょう。</span><span class="sxs-lookup"><span data-stu-id="d1557-222">We are not able to respond personally, but having examples of files that do not load properly will help our team improve on future versions of the app.</span></span>

### <span data-ttu-id="d1557-223">3D モデルが読み込まれるが、期待どおりに表示されない</span><span class="sxs-lookup"><span data-stu-id="d1557-223">My 3D model loads, but does not appear as expected</span></span>

<span data-ttu-id="d1557-224">3D モデルが 3D ビューアーで期待どおりに表示されない場合は、エアタップしてツールバーを表示し、[**詳細**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1557-224">If your 3D model does not look as expected in 3D Viewer, air tap to show the toolbar, then select **Details**.</span></span> <span data-ttu-id="d1557-225">3D ビューアーでサポートされていないファイルの側面は、警告として強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1557-225">Aspects of the file which are not supported by 3D Viewer will be highlighted as warnings.</span></span>

<span data-ttu-id="d1557-226">表示される最も一般的な問題は、テクスチャが欠落していることです。これは、おそらく FBX ファイルに埋め込まれていないためです。</span><span class="sxs-lookup"><span data-stu-id="d1557-226">The most common issue you might see is missing textures, likely because they are not embedded in the FBX file.</span></span> <span data-ttu-id="d1557-227">この場合、モデルは白く表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1557-227">In this case, the model will appear white.</span></span> <span data-ttu-id="d1557-228">この問題は、埋め込みのテクスチャ オプションを選択して作成ツールから FBX にエクスポートすることにより、作成プロセスで対処できます。</span><span class="sxs-lookup"><span data-stu-id="d1557-228">This issue can be addressed in the creation process by exporting from your creation tool to FBX with the embed textures option selected.</span></span>

<span data-ttu-id="d1557-229">詳細については、「[サポートされるコンテンツの仕様](#supported-content-specifications)」および「[3D ビューアー用に 3D モデルを最適化する](#optimizing-3d-models-for-3d-viewer)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1557-229">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer](#optimizing-3d-models-for-3d-viewer).</span></span>

### <span data-ttu-id="d1557-230">3D モデルを表示しているときにパフォーマンスが低下する</span><span class="sxs-lookup"><span data-stu-id="d1557-230">I experience performance drops while viewing my 3D model</span></span>

<span data-ttu-id="d1557-231">3D モデルを読み込んで表示するときのパフォーマンスは、モデルの複雑さ、同時に開くモデルの数、または有効なアニメーションを持つモデルの数によって影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d1557-231">Performance when loading and viewing a 3D model can be affected by the complexity of the model, number of models open simultaneously, or number of models with active animations.</span></span>

<span data-ttu-id="d1557-232">詳細については、「[3D ビューアー用に 3D モデルを最適化する](#optimizing-3d-models-for-3d-viewer)」および「[ファイルとモデルの制限](#file-and-model-limitations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1557-232">For more info, see [Optimizing 3D models for 3D Viewer](#optimizing-3d-models-for-3d-viewer) and [File and model limitations](#file-and-model-limitations).</span></span>

### <span data-ttu-id="d1557-233">HoloLens で FBX ファイルを開くと、3D ビューアーで開かない</span><span class="sxs-lookup"><span data-stu-id="d1557-233">When I open an FBX file on HoloLens, it doesn't open in 3D Viewer</span></span>

<span data-ttu-id="d1557-234">3D ビューアーは、インストール時に自動的に .fbx ファイル拡張子に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="d1557-234">3D Viewer is automatically associated with the .fbx file extension when it is installed.</span></span>

<span data-ttu-id="d1557-235">FBX ファイルを開こうとして、Microsoft Store に移動するダイアログ ボックスが表示された場合、HoloLens の .fbx ファイル拡張子に関連付けられたアプリは現在ないということになります。</span><span class="sxs-lookup"><span data-stu-id="d1557-235">If you try to open an FBX file and see a dialog box that directs you to Microsoft Store, you do not currently have an app associated with the .fbx file extension on HoloLens.</span></span>

<span data-ttu-id="d1557-236">3D ビューアーがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d1557-236">Verify that 3D Viewer is installed.</span></span> <span data-ttu-id="d1557-237">インストールされていない場合は、HoloLens の Microsoft Storeからダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="d1557-237">If it is not installed, download it from Microsoft Store on HoloLens.</span></span>

<span data-ttu-id="d1557-238">3D ビューアーがすでにインストールされている場合は、3D ビューアーを起動し、ファイルをもう一度開いてみてください。</span><span class="sxs-lookup"><span data-stu-id="d1557-238">If 3D Viewer is already installed, launch 3D Viewer, then try opening the file again.</span></span> <span data-ttu-id="d1557-239">問題が解決しない場合は、3D ビューアーをアンインストールして再インストールします。</span><span class="sxs-lookup"><span data-stu-id="d1557-239">If the issue persists, uninstall and reinstall 3D Viewer.</span></span> <span data-ttu-id="d1557-240">これにより、.fbx ファイル拡張子が 3D ビューアーに再度関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="d1557-240">This will re-associate the .fbx file extension with 3D Viewer.</span></span>

<span data-ttu-id="d1557-241">FBX ファイルを開こうとすると、3D ビューアー以外のアプリが開かれる場合、そのアプリは 3D ビューアーの後にインストールされた可能性が高く、.fbx ファイル拡張子との関連付けを引き継いでいる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d1557-241">If attempting to open an FBX file opens an app other than 3D Viewer, that app was likely installed after 3D Viewer and has taken over association with the .fbx file extension.</span></span> <span data-ttu-id="d1557-242">3D ビューアーを .fbx ファイル拡張子に関連付けたい場合は、3D ビューアーをアンインストールして再インストールします。</span><span class="sxs-lookup"><span data-stu-id="d1557-242">If you prefer 3D Viewer to be associated with the .fbx file extension, uninstall and reinstall 3D Viewer.</span></span>

### <span data-ttu-id="d1557-243">3D ビューアーの [ファイルを開く] ボタンでアプリが起動しない</span><span class="sxs-lookup"><span data-stu-id="d1557-243">The Open File button in 3D Viewer doesn't launch an app</span></span>

<span data-ttu-id="d1557-244">[**ファイルを開く**] ボタンは、HoloLens のファイル ピッカー機能に関連付けられたアプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="d1557-244">The **Open File** button will open the app associated with the file picker function on HoloLens.</span></span> <span data-ttu-id="d1557-245">OneDrive がインストールされている場合、[**ファイルを開く**] ボタンで OneDrive が起動します。</span><span class="sxs-lookup"><span data-stu-id="d1557-245">If OneDrive is installed, the **Open File** button should launch OneDrive.</span></span> <span data-ttu-id="d1557-246">ただし、HoloLens にインストールされているファイル ピッカー機能に関連付けられたアプリが現在ない場合は、Microsoft Store に移動されます。</span><span class="sxs-lookup"><span data-stu-id="d1557-246">However, if there is currently no app associated with the file picker function installed on HoloLens, you will be directed to Microsoft Store.</span></span>

<span data-ttu-id="d1557-247">[**ファイルを開く**] ボタンが OneDrive 以外のアプリを起動した場合、そのアプリは OneDrive の後にインストールされた可能性が高く、ファイル ピッカー機能との関連付けを引き継いでいる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d1557-247">If the **Open File** button launches an app other than OneDrive, that app was likely installed after OneDrive and has taken over association with the file picker function.</span></span> <span data-ttu-id="d1557-248">3D ビューアーで [**ファイルを開く**] ボタンを選択したときに OneDrive を起動する場合は、OneDrive をアンインストールして再インストールします。</span><span class="sxs-lookup"><span data-stu-id="d1557-248">If you prefer OneDrive to launch when selecting the **Open File** button in 3D Viewer, uninstall and reinstall OneDrive.</span></span>

<span data-ttu-id="d1557-249">[**ファイルを開く**] ボタンが有効でない場合、一度に 3D ビューアーで開くことができるモデルの制限に達している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d1557-249">If the **Open File** button is not active, it's possible that you have reached the limit of models that can be open in 3D Viewer at one time.</span></span> <span data-ttu-id="d1557-250">3D ビューアーで 40 個のモデルを開いている場合は、追加のモデルを開く前にいくつかを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1557-250">If you have 40 models open in 3D Viewer, you will need to close some before you will be able to open additional models.</span></span>

## <span data-ttu-id="d1557-251">その他の資料</span><span class="sxs-lookup"><span data-stu-id="d1557-251">Additional resources</span></span>

- [<span data-ttu-id="d1557-252">サポート フォーラム</span><span class="sxs-lookup"><span data-stu-id="d1557-252">Support forums</span></span>](http://forums.hololens.com/categories/3d-viewer-beta)
- [<span data-ttu-id="d1557-253">サードパーティについての通知</span><span class="sxs-lookup"><span data-stu-id="d1557-253">Third-party notices</span></span>](https://www.microsoft.com/{lang-locale}/legal/products)
