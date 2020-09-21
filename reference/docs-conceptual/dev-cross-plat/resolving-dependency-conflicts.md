---
title: PowerShell モジュール アセンブリの依存関係の競合の解決
description: C# でバイナリ PowerShell モジュールを記述する場合、機能を提供するために他のパッケージやライブラリに依存するのは自然なことです。
ms.date: 06/25/2020
ms.custom: rjmholt
ms.openlocfilehash: 536bcfd1ced536faccde0d6c5bc483cdaf31ce68
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87775182"
---
# <a name="resolving-powershell-module-assembly-dependency-conflicts"></a><span data-ttu-id="fa145-103">PowerShell モジュール アセンブリの依存関係の競合の解決</span><span class="sxs-lookup"><span data-stu-id="fa145-103">Resolving PowerShell module assembly dependency conflicts</span></span>

<span data-ttu-id="fa145-104">C# でバイナリ PowerShell モジュールを記述する場合、機能を提供するために他のパッケージやライブラリに依存するのは自然なことです。</span><span class="sxs-lookup"><span data-stu-id="fa145-104">When writing a binary PowerShell module in C#, it's natural to take dependencies on other packages or libraries to provide functionality.</span></span> <span data-ttu-id="fa145-105">コードの再利用のためには、他のライブラリに依存するのは望ましいことです。</span><span class="sxs-lookup"><span data-stu-id="fa145-105">Taking dependencies on other libraries is desirable for code reuse.</span></span> <span data-ttu-id="fa145-106">PowerShell では、アセンブリは常に同じコンテキストに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="fa145-106">PowerShell always loads assemblies into the same context.</span></span> <span data-ttu-id="fa145-107">そのため、モジュールの依存関係が既に読み込まれている DLL と競合し、そうでなければ同じ PowerShell セッション内で関係のないはずの 2 つのモジュールを、使用できなくなる場合があるという問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="fa145-107">This presents issues when a module's dependencies conflict with already-loaded DLLs and may prevent using two otherwise unrelated modules in the same PowerShell session.</span></span>

<span data-ttu-id="fa145-108">この問題が発生した場合は、次のようなエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fa145-108">If you've had this problem, you've seen an error message like this:</span></span>

![アセンブリ読み込み競合のエラー メッセージ](./media/resolving-dependency-conflicts/moduleconflict.png)

<span data-ttu-id="fa145-110">この記事では、どのような場合に PowerShell で依存関係の競合が発生するか、そして依存関係の競合の問題を軽減する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fa145-110">This article looks at some of the ways dependency conflicts occur in PowerShell and ways to mitigate dependency conflict issues.</span></span> <span data-ttu-id="fa145-111">モジュールの作成者でない場合でも、ここで説明するいくつかのテクニックは、モジュールの使用時に発生する依存関係の競合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fa145-111">Even if you're not a module author, there are some tricks in here that might help you with dependency conflicts occurring in modules that you use.</span></span>

## <a name="why-do-dependency-conflicts-occur"></a><span data-ttu-id="fa145-112">依存関係の競合が発生する理由</span><span class="sxs-lookup"><span data-stu-id="fa145-112">Why do dependency conflicts occur?</span></span>

<span data-ttu-id="fa145-113">.NET では、同じアセンブリの 2 つのバージョンが同じ "_アセンブリ読み込みコンテキスト_" に読み込まれると、依存関係の競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="fa145-113">In .NET, dependency conflicts occur when two versions of the same assembly are loaded into the same _Assembly Load Context_.</span></span> <span data-ttu-id="fa145-114">この用語の意味は、.NET プラットフォームによって若干異なります。これについては、[後で](#powershell-and-net)説明します。</span><span class="sxs-lookup"><span data-stu-id="fa145-114">This term means slightly different things on different .NET platforms, which is covered [later](#powershell-and-net).</span></span> <span data-ttu-id="fa145-115">この競合は一般的な問題であり、バージョン管理された依存関係を使用するすべてのソフトウェアで発生します。</span><span class="sxs-lookup"><span data-stu-id="fa145-115">This conflict is a common problem that occurs in any software where versioned dependencies are used.</span></span> <span data-ttu-id="fa145-116">簡単な解決策はなく、多くの依存関係解決フレームワークでは異なる方法で問題の解決が試みられるため、このような状況は "依存関係の地獄" と呼ばれることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="fa145-116">Because there are no simple solutions, and because many dependency-resolution frameworks try to solve the problem in different ways, this situation is often called "dependency hell".</span></span>

<span data-ttu-id="fa145-117">競合の問題は、プロジェクトで同じ依存関係の 2 つのバージョンに、意図的に、または直接依存することはほとんどないという事実によって、さらに複雑になります。</span><span class="sxs-lookup"><span data-stu-id="fa145-117">Conflict issues are compounded by the fact that a project almost never deliberately or directly depends on two versions of the same dependency.</span></span> <span data-ttu-id="fa145-118">そうではなく、プロジェクトの複数の依存関係のそれぞれで、同じ依存関係の異なるバージョンが必要になります。</span><span class="sxs-lookup"><span data-stu-id="fa145-118">Instead, the project has two or more dependencies that each require a different version of the same dependency.</span></span>

<span data-ttu-id="fa145-119">たとえば、次のような .NET アプリケーション `DuckBuilder` があり、その機能の一部を実行するために 2 つの依存関係が読み込まれているとします。</span><span class="sxs-lookup"><span data-stu-id="fa145-119">For example, say your .NET application, `DuckBuilder`, brings in two dependencies, to perform parts of its functionality and looks like this:</span></span>

![DuckBuilder の 2 つの依存関係は、Newtonsoft.Json の異なるバージョンに依存している](./media/resolving-dependency-conflicts/dep-conflict.jpg)

<span data-ttu-id="fa145-121">`Contoso.ZipTools` と `Fabrikam.FileHelpers` はどちらも異なるバージョンの `Newtonsoft.Json` に依存しているため、各依存関係の読み込み方法によっては、依存関係の競合が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-121">Because `Contoso.ZipTools` and `Fabrikam.FileHelpers` both depend on different versions of `Newtonsoft.Json`, there may be a dependency conflict depending on how each dependency is loaded.</span></span>

### <a name="conflicting-with-powershells-dependencies"></a><span data-ttu-id="fa145-122">PowerShell の依存関係での競合</span><span class="sxs-lookup"><span data-stu-id="fa145-122">Conflicting with PowerShell's dependencies</span></span>

<span data-ttu-id="fa145-123">Powershell では、PowerShell モジュールと PowerShell 独自の依存関係が同じ共有コンテキストに読み込まれるため、依存関係の競合の問題がいっそう大きくなります。</span><span class="sxs-lookup"><span data-stu-id="fa145-123">In PowerShell, the dependency conflict issue is magnified because PowerShell modules and PowerShell's own dependencies are loaded into the same shared context.</span></span> <span data-ttu-id="fa145-124">これは、PowerShell エンジンと、読み込まれるすべての PowerShell モジュールに、競合する依存関係があってはならないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="fa145-124">This means the PowerShell engine and all loaded PowerShell modules must not have conflicting dependencies.</span></span> <span data-ttu-id="fa145-125">これの典型的な例が `Newtonsoft.Json` です。</span><span class="sxs-lookup"><span data-stu-id="fa145-125">A classic example of this is `Newtonsoft.Json`:</span></span>

![FictionalTools モジュールは PowerShell より新しいバージョンの Newtonsoft.Json に依存している](./media/resolving-dependency-conflicts/engine-conflict.jpg)

<span data-ttu-id="fa145-127">この例では、モジュール `FictionalTools` は `Newtonsoft.Json` のバージョン `12.0.3` に依存していますが、これは例の PowerShell に付属する `11.0.2` より新しいバージョンの `Newtonsoft.Json` です。</span><span class="sxs-lookup"><span data-stu-id="fa145-127">In this example, the module `FictionalTools` depends on `Newtonsoft.Json` version `12.0.3`, which is a newer version of `Newtonsoft.Json` than `11.0.2` that ships in the example PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="fa145-128">これは例であり、現在の PowerShell 7 には `Newtonsoft.Json 12.0.3` が付属しています。</span><span class="sxs-lookup"><span data-stu-id="fa145-128">This is an example and PowerShell 7 currently ships with `Newtonsoft.Json 12.0.3`.</span></span>

<span data-ttu-id="fa145-129">モジュールは新しいバージョンのアセンブリに依存しているため、PowerShell によって既に読み込まれているバージョンを受け付けません。</span><span class="sxs-lookup"><span data-stu-id="fa145-129">Because the module depends on a newer version of the assembly, it won't accept the version that PowerShell already has loaded.</span></span> <span data-ttu-id="fa145-130">しかし、PowerShell によってアセンブリのあるバージョンが既に読み込まれているため、モジュールでは従来の読み込みメカニズムを使用して独自のバージョンを読み込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="fa145-130">But because PowerShell has already loaded a version of the assembly, the module can't load its own version using the conventional load mechanism.</span></span>

### <a name="conflicting-with-another-modules-dependencies"></a><span data-ttu-id="fa145-131">別のモジュールの依存関係との競合</span><span class="sxs-lookup"><span data-stu-id="fa145-131">Conflicting with another module's dependencies</span></span>

<span data-ttu-id="fa145-132">PowerShell でのもう 1 つの一般的なシナリオは、あるバージョンのアセンブリに依存するモジュールが読み込まれた後、そのアセンブリの異なるバージョンに依存する別のモジュールが読み込まれる場合です。</span><span class="sxs-lookup"><span data-stu-id="fa145-132">Another common scenario in PowerShell is that a module is loaded that depends on one version of an assembly, and then another module is loaded later that depends on a different version of that assembly.</span></span>

<span data-ttu-id="fa145-133">多くの場合、これは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fa145-133">This often looks like the following:</span></span>

![2 つの PowerShell モジュールでは、異なるバージョンの Microsoft.Extensions.Logging 依存関係が必要である](./media/resolving-dependency-conflicts/mod-conflict.jpg)

<span data-ttu-id="fa145-135">この場合、`FictionalTools` モジュールでは `FilesystemManager` モジュールより新しいバージョンの `Microsoft.Extensions.Logging` が必要です。</span><span class="sxs-lookup"><span data-stu-id="fa145-135">In this case, the `FictionalTools` module requires a newer version of `Microsoft.Extensions.Logging` than the `FilesystemManager` module.</span></span>

<span data-ttu-id="fa145-136">これらのモジュールで、ルート モジュール アセンブリと同じディレクトリに依存関係アセンブリを配置することにより、依存関係を読み込むものとします。</span><span class="sxs-lookup"><span data-stu-id="fa145-136">Imagine these modules load their dependencies by placing the dependency assemblies in the same directory as the root module assembly.</span></span> <span data-ttu-id="fa145-137">これにより、.NET では名前を使用して暗黙的にそれらを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="fa145-137">This allows .NET to implicitly load them by name.</span></span> <span data-ttu-id="fa145-138">(.NET Core 3.1 上の) PowerShell 7 を実行している場合は、`FictionalTools` を読み込んで実行した後、問題なく `FilesystemManager` を読み込んで実行できます。</span><span class="sxs-lookup"><span data-stu-id="fa145-138">If we're running PowerShell 7 (on top of .NET Core 3.1), we can load and run `FictionalTools`, then load and run `FilesystemManager` without issue.</span></span> <span data-ttu-id="fa145-139">しかし、新しいセッションで `FilesystemManager` を読み込んで実行した後、`FictionalTools` を読み込むと、読み込まれているものより新しいバージョンの `Microsoft.Extensions.Logging` が必要になるため、`FictionalTools` コマンドで `FileLoadException` が発生します。</span><span class="sxs-lookup"><span data-stu-id="fa145-139">However, in a new session, if we load and run `FilesystemManager`, then load `FictionalTools`, we get a `FileLoadException` from the `FictionalTools` command because it requires a newer version of `Microsoft.Extensions.Logging` than the one loaded.</span></span>
<span data-ttu-id="fa145-140">同じ名前のアセンブリが既に読み込まれているため、`FictionalTools` では必要なバージョンを読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="fa145-140">`FictionalTools` can't load the version needed because an assembly of the same name has already been loaded.</span></span>

## <a name="powershell-and-net"></a><span data-ttu-id="fa145-141">PowerShell と .NET</span><span class="sxs-lookup"><span data-stu-id="fa145-141">PowerShell and .NET</span></span>

<span data-ttu-id="fa145-142">PowerShell は .NET プラットフォーム上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="fa145-142">PowerShell runs on the .NET platform.</span></span> <span data-ttu-id="fa145-143">アセンブリの依存関係の解決と読み込みは最終的に .NET によって行われるため、依存関係の競合について理解するには、.NET の動作方法を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-143">NET is ultimately responsible for resolving and loading assembly dependencies, so we must understand how .NET operates here to understand dependency conflicts.</span></span>

<span data-ttu-id="fa145-144">また、異なるバージョンの PowerShell は異なる .NET の実装で実行されるという事実についても考える必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-144">We must also confront the fact that different versions of PowerShell run on different .NET implementations.</span></span> <span data-ttu-id="fa145-145">一般に、PowerShell 5.1 以前は .NET Framework で実行され、PowerShell 6 以降は .NET Core で実行されます。</span><span class="sxs-lookup"><span data-stu-id="fa145-145">In general, PowerShell 5.1 and below run on .NET Framework, while PowerShell 6 and above run on .NET Core.</span></span> <span data-ttu-id="fa145-146">.NET のこれら 2 つの実装では、アセンブリの読み込みと処理が異なります。</span><span class="sxs-lookup"><span data-stu-id="fa145-146">These two implementations of .NET load and handle assemblies differently.</span></span>
<span data-ttu-id="fa145-147">つまり、依存関係の競合の解決は、基になる .NET プラットフォームによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-147">This means that resolving dependency conflicts can vary depending on the underlying .NET platform.</span></span>

### <a name="assembly-load-contexts"></a><span data-ttu-id="fa145-148">アセンブリ読み込みコンテキスト</span><span class="sxs-lookup"><span data-stu-id="fa145-148">Assembly Load Contexts</span></span>

<span data-ttu-id="fa145-149">.NET では、アセンブリが読み込まれるランタイム名前空間である "_アセンブリ読み込みコンテキスト_" (ALC)。</span><span class="sxs-lookup"><span data-stu-id="fa145-149">In .NET, an _Assembly Load Context_ (ALC) that is a runtime namespace into which assemblies are loaded.</span></span> <span data-ttu-id="fa145-150">アセンブリの名前は一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-150">The assemblies' names must be unique.</span></span> <span data-ttu-id="fa145-151">この概念により、各 ALC 内の名前によってアセンブリを一意に解決できます。</span><span class="sxs-lookup"><span data-stu-id="fa145-151">This concept allows assemblies to be uniquely resolved by name in each ALC.</span></span>

### <a name="assembly-reference-loading-in-net"></a><span data-ttu-id="fa145-152">.NET でのアセンブリ参照読み込み</span><span class="sxs-lookup"><span data-stu-id="fa145-152">Assembly reference loading in .NET</span></span>

<span data-ttu-id="fa145-153">アセンブリ読み込みのセマンティクスは、.NET の実装 (.NET Core または .NET Framework) と、特定のアセンブリの読み込みに使用される .NET API の両方に依存します。</span><span class="sxs-lookup"><span data-stu-id="fa145-153">The semantics of assembly loading depend on both the .NET implementation (.NET Core vs .NET Framework) and the .NET API used to load a particular assembly.</span></span> <span data-ttu-id="fa145-154">ここでは詳細については説明しません。.NET の各実装で .NET アセンブリの読み込みがどのように機能するかについて詳しくは、「[関連項目](#further-reading)」セクションのリンクをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fa145-154">Rather than go into detail here, there are links in the [Further reading](#further-reading) section that go into great detail on how .NET assembly loading works in each .NET implementation.</span></span>

<span data-ttu-id="fa145-155">この記事では、次のメカニズムについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fa145-155">In this article we'll refer to the following mechanisms:</span></span>

- <span data-ttu-id="fa145-156">.NET により .NET コード内の静的アセンブリ参照からの名前でのアセンブリの読み込みが暗黙的に試みられるときの、暗黙でのアセンブリの読み込み (実質的には `Assembly.Load(AssemblyName)`)。</span><span class="sxs-lookup"><span data-stu-id="fa145-156">Implicit assembly loading (effectively `Assembly.Load(AssemblyName)`), when .NET implicitly tries to load an assembly by name from a static assembly reference in .NET code.</span></span>
- <span data-ttu-id="fa145-157">`Assembly.LoadFrom()`。読み込まれた DLL の依存関係を解決するためのハンドラーを追加する、プラグイン指向の読み込み API。</span><span class="sxs-lookup"><span data-stu-id="fa145-157">`Assembly.LoadFrom()`, a plugin-oriented loading API that adds handlers to resolve dependencies of the loaded DLL.</span></span> <span data-ttu-id="fa145-158">このメソッドでは、必要な方法で依存関係が解決されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-158">This method may not resolve dependencies the way we want.</span></span>
- <span data-ttu-id="fa145-159">`Assembly.LoadFile()`。要求されたアセンブリの読み込みだけが行われ、依存関係の処理は行われない、基本的な読み込み API。</span><span class="sxs-lookup"><span data-stu-id="fa145-159">`Assembly.LoadFile()`, a basic loading API intended to load only the assembly asked for and does not handle any dependencies.</span></span>

### <a name="differences-in-net-framework-vs-net-core"></a><span data-ttu-id="fa145-160">.NET Framework と .NET Core の相違点</span><span class="sxs-lookup"><span data-stu-id="fa145-160">Differences in .NET Framework vs .NET Core</span></span>

<span data-ttu-id="fa145-161">.NET Core と .NET Framework では、これらの API の動作が微妙に変更されているため、[リンク](#further-reading)の参照先をよく読んでください。</span><span class="sxs-lookup"><span data-stu-id="fa145-161">The way these APIs work has changed in subtle ways between .NET Core and .NET Framework, so it's worth reading through the included [links](#further-reading).</span></span> <span data-ttu-id="fa145-162">重要なのは、アセンブリ読み込みコンテキストと他のアセンブリ解決メカニズムが、.NET Framework と .NET Core の間で変更されていることです。</span><span class="sxs-lookup"><span data-stu-id="fa145-162">Importantly, Assembly Load Contexts and other assembly resolution mechanisms have changed between .NET Framework and .NET Core.</span></span>

<span data-ttu-id="fa145-163">具体的には、.NET Framework には次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-163">In particular, .NET Framework has the following features:</span></span>

- <span data-ttu-id="fa145-164">グローバル アセンブリ キャッシュは、コンピューター全体のアセンブリ解決用です</span><span class="sxs-lookup"><span data-stu-id="fa145-164">The Global Assembly Cache, for machine-wide assembly resolution</span></span>
- <span data-ttu-id="fa145-165">アプリケーション ドメインは、アセンブリの分離に関してはプロセス内サンドボックスと同様に機能しますが、競合するシリアル化レイヤーも提供されます</span><span class="sxs-lookup"><span data-stu-id="fa145-165">Application Domains, which work like in-process sandboxes for assembly isolation, but also present a serialization layer to contend with</span></span>
- <span data-ttu-id="fa145-166">制限付きアセンブリ読み込みコンテキスト モデル (詳細については[こちら](/dotnet/framework/deployment/best-practices-for-assembly-loading)を参照) には、それぞれが独自の動作を備えたアセンブリ読み込みコンテキストの固定セットがあります</span><span class="sxs-lookup"><span data-stu-id="fa145-166">A limited assembly load context model, explained in depth [here](/dotnet/framework/deployment/best-practices-for-assembly-loading), that has a fixed set of assembly load contexts, each with their own behavior:</span></span>
  - <span data-ttu-id="fa145-167">既定の読み込みコンテキストでは、アセンブリが既定で読み込まれます</span><span class="sxs-lookup"><span data-stu-id="fa145-167">The default load context, where assemblies are loaded by default</span></span>
  - <span data-ttu-id="fa145-168">読み込み元コンテキストは、実行時に手動でアセンブリを読み込むためのものです</span><span class="sxs-lookup"><span data-stu-id="fa145-168">The load-from context, for loading assemblies manually at runtime</span></span>
  - <span data-ttu-id="fa145-169">リフレクションのみのコンテキストは、アセンブリを実行せずにそのメタデータを読み取る、安全にアセンブリを読み込むためのものです</span><span class="sxs-lookup"><span data-stu-id="fa145-169">The reflection-only context, for safely loading assemblies to read their metadata without running them</span></span>
  - <span data-ttu-id="fa145-170">ミステリアス void には、`Assembly.LoadFile(string path)` と `Assembly.Load(byte[] asmBytes)` で読み込まれるアセンブリが存在します</span><span class="sxs-lookup"><span data-stu-id="fa145-170">The mysterious void that assemblies loaded with `Assembly.LoadFile(string path)` and `Assembly.Load(byte[] asmBytes)` live in</span></span>

<span data-ttu-id="fa145-171">.NET Core (および .NET 5 以降) では、この複雑さが単純なモデルに置き換えられています。</span><span class="sxs-lookup"><span data-stu-id="fa145-171">.NET Core (and .NET 5+) has replaced this complexity with a simpler model:</span></span>

- <span data-ttu-id="fa145-172">グローバル アセンブリ キャッシュはありません。</span><span class="sxs-lookup"><span data-stu-id="fa145-172">No Global Assembly Cache.</span></span> <span data-ttu-id="fa145-173">アプリケーション自体のすべての依存関係がアプリケーションに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="fa145-173">Applications bring all their own dependencies.</span></span> <span data-ttu-id="fa145-174">これにより、アプリケーションで依存関係を解決するための外部要因がなくなり、依存関係の解決がより再現しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="fa145-174">This removes an external factor for dependency resolution in applications, making dependency resolution more reproducible.</span></span>
  <span data-ttu-id="fa145-175">プラグイン ホストとしての PowerShell により、モジュールではこれが少し複雑になります。</span><span class="sxs-lookup"><span data-stu-id="fa145-175">PowerShell, as the plugin host, complicates this slightly for modules.</span></span> <span data-ttu-id="fa145-176">`$PSHOME` 内の依存関係は、すべてのモジュールで共有されます。</span><span class="sxs-lookup"><span data-stu-id="fa145-176">Its dependencies in `$PSHOME` are shared with all modules.</span></span>
- <span data-ttu-id="fa145-177">アプリケーション ドメインは 1 つだけで、新しいものを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="fa145-177">Only one Application Domain, and no ability to create new ones.</span></span> <span data-ttu-id="fa145-178">.NET Core では、アプリケーション ドメインの概念は .NET プロセスのグローバルな状態としてのみ維持されています。</span><span class="sxs-lookup"><span data-stu-id="fa145-178">The Application Domain concept is maintained in .NET Core purely to be the global state of the .NET process.</span></span>
- <span data-ttu-id="fa145-179">新しい拡張可能なアセンブリ読み込みコンテキスト モデル。</span><span class="sxs-lookup"><span data-stu-id="fa145-179">A new, extensible Assembly Load Context model.</span></span> <span data-ttu-id="fa145-180">アセンブリの解決は、新しい ALC に配置することによって、名前空間化できます。</span><span class="sxs-lookup"><span data-stu-id="fa145-180">Assembly resolution can be namespaced by putting it in a new ALC.</span></span> <span data-ttu-id="fa145-181">.NET Core のプロセスは、すべてのアセンブリが読み込まれる既定の 1 つの ALC で始まります。</span><span class="sxs-lookup"><span data-stu-id="fa145-181">.NET Core processes begin with a single default ALC into which all assemblies are loaded.</span></span> <span data-ttu-id="fa145-182">(`Assembly.LoadFile(string)` および `Assembly.Load(byte[])` で読み込まれるものは除きます)。ただし、プロセスでは、独自の読み込みロジックを使用して独自のカスタム ALC を作成および定義することができます。</span><span class="sxs-lookup"><span data-stu-id="fa145-182">(except for those loaded with `Assembly.LoadFile(string)` and `Assembly.Load(byte[])`) But the process can create and define its own custom ALCs with its own loading logic.</span></span> <span data-ttu-id="fa145-183">アセンブリが読み込まれるとき、最初の読み込み先 ALC によって依存関係の解決が行われます。</span><span class="sxs-lookup"><span data-stu-id="fa145-183">When an assembly is loaded, the first ALC it is loaded into is responsible for resolving its dependencies.</span></span> <span data-ttu-id="fa145-184">これにより、強力な .NET プラグイン読み込みメカニズムを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="fa145-184">This creates opportunities to implement powerful .NET plugin loading mechanisms.</span></span>

<span data-ttu-id="fa145-185">どちらの実装でも、アセンブリは遅延読み込みされます。</span><span class="sxs-lookup"><span data-stu-id="fa145-185">In both implementations, assemblies are loaded lazily.</span></span> <span data-ttu-id="fa145-186">これは、その型を必要とするメソッドが初めて実行されるときに読み込まれることを意味します。</span><span class="sxs-lookup"><span data-stu-id="fa145-186">This means that they are loaded when a method requiring their type is run for the first time.</span></span>

<span data-ttu-id="fa145-187">たとえば、同じコードの 2 つのバージョンがあり、依存関係を読み込むタイミングが異なるとします。</span><span class="sxs-lookup"><span data-stu-id="fa145-187">For example, here are two versions of the same code that load a dependency at different times.</span></span>

<span data-ttu-id="fa145-188">1 番目では、依存関係の参照がメソッド内に構文的に存在するため、依存関係は `Program.GetRange()` が呼び出されるときに常に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="fa145-188">The first always loads its dependency when `Program.GetRange()` is called, because the dependency reference is lexically present within the method:</span></span>

```csharp
using Dependency.Library;

public static class Program
{
    public static List<int> GetRange(int limit)
    {
        var list = new List<int>();
        for (int i = 0; i < limit; i++)
        {
            if (i >= 20)
            {
                // Dependency.Library will be loaded when GetRange is run
                // because the dependency call occurs directly within the method
                DependencyApi.Use();
            }

            list.Add(i);
        }
        return list;
    }
}
```

<span data-ttu-id="fa145-189">2 番目では、メソッドによる内部間接参照であるため、依存関係は `limit` パラメーターが 20 以上の場合にのみ読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="fa145-189">The second will load its dependency only if the `limit` parameter is 20 or more, because of the internal indirection through a method:</span></span>

```csharp
using Dependency.Library;

public static class Program
{
    public static List<int> GetNumbers(int limit)
    {
        var list = new List<int>();
        for (int i = 0; i < limit; i++)
        {
            if (i >= 20)
            {
                // Dependency.Library is only referenced within
                // the UseDependencyApi() method,
                // so will only be loaded when limit >= 20
                UseDependencyApi();
            }

            list.Add(i);
        }
        return list;
    }

    private static void UseDependencyApi()
    {
        // Once UseDependencyApi() is called, Dependency.Library is loaded
        DependencyApi.Use();
    }
}
```

<span data-ttu-id="fa145-190">メモリとファイル システムの I/O が最小限になり、リソースの使用効率が向上するため、これは良い方法です。</span><span class="sxs-lookup"><span data-stu-id="fa145-190">This is a good practice since it minimizes the memory and filesystem I/O and uses the resources more efficiently.</span></span> <span data-ttu-id="fa145-191">残念ながら、これには、アセンブリの読み込みを試みるコード パスに達するまで、アセンブリの読み込みが失敗することがわからないという副作用があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-191">The unfortunate a side effect of this is that we won't know that the assembly fails to load until we reach the code path that tries to load the assembly.</span></span>

<span data-ttu-id="fa145-192">また、アセンブリ読み込みの競合に対して、タイミング条件が作成される可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="fa145-192">It can also create a timing condition for assembly load conflicts.</span></span> <span data-ttu-id="fa145-193">同じプログラムの 2 つの部分で、同じアセンブリの異なるバージョンの読み込みが試みられた場合、読み込まれるバージョンは、最初に実行されるコード パスによって決まります。</span><span class="sxs-lookup"><span data-stu-id="fa145-193">If two parts of the same program try to load different versions of the same assembly, the version loaded depends on which code path is run first.</span></span>

<span data-ttu-id="fa145-194">PowerShell の場合、これは、次の要因がアセンブリ読み込みの競合に影響する可能性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="fa145-194">For PowerShell, this means that the following factors can affect an assembly load conflict:</span></span>

- <span data-ttu-id="fa145-195">どのモジュールが最初に読み込まれたか</span><span class="sxs-lookup"><span data-stu-id="fa145-195">Which module was loaded first?</span></span>
- <span data-ttu-id="fa145-196">依存関係ライブラリを使用するコード パスは実行されたか</span><span class="sxs-lookup"><span data-stu-id="fa145-196">Was the code path that uses the dependency library run?</span></span>
- <span data-ttu-id="fa145-197">PowerShell では、競合する依存関係が、起動時に読み込まれるか、それとも特定のコード パスでのみ読み込まれるか</span><span class="sxs-lookup"><span data-stu-id="fa145-197">Does PowerShell load a conflicting dependency at startup or only under certain code paths?</span></span>

## <a name="quick-fixes-and-their-limitations"></a><span data-ttu-id="fa145-198">簡単な修正とその制限事項</span><span class="sxs-lookup"><span data-stu-id="fa145-198">Quick fixes and their limitations</span></span>

<span data-ttu-id="fa145-199">場合によっては、モジュールを微調整し、最小限の労力で修正することができます。</span><span class="sxs-lookup"><span data-stu-id="fa145-199">In some cases, it's possible to make small adjustments to your module and fix things with minimal effort.</span></span> <span data-ttu-id="fa145-200">ただし、これらの解決策には注意が伴います。</span><span class="sxs-lookup"><span data-stu-id="fa145-200">But these solutions tend to come with caveats.</span></span> <span data-ttu-id="fa145-201">モジュールに適用できますが、モジュールによっては機能しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="fa145-201">While they may apply to your module, they won't work for every module.</span></span>

### <a name="change-your-dependency-version"></a><span data-ttu-id="fa145-202">依存関係のバージョンを変更する</span><span class="sxs-lookup"><span data-stu-id="fa145-202">Change your dependency version</span></span>

<span data-ttu-id="fa145-203">依存関係の競合を回避する最も簡単な方法は、依存関係に同意することです。</span><span class="sxs-lookup"><span data-stu-id="fa145-203">The simplest way to avoid dependency conflicts is to agree on a dependency.</span></span> <span data-ttu-id="fa145-204">これは、次の場合にできる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-204">This may be possible when:</span></span>

- <span data-ttu-id="fa145-205">競合がモジュールの直接的な依存関係に関するものであり、自分でバージョンを管理している。</span><span class="sxs-lookup"><span data-stu-id="fa145-205">Your conflict is with a direct dependency of your module and you control the version.</span></span>
- <span data-ttu-id="fa145-206">競合は間接的な依存関係に関するものだが、動作可能な間接的依存関係バージョンを使用するように、直接的な依存関係を構成できる。</span><span class="sxs-lookup"><span data-stu-id="fa145-206">Your conflict is with an indirect dependency, but you can configure your direct dependencies to use a workable indirect dependency version.</span></span>
- <span data-ttu-id="fa145-207">競合しているバージョンがわかっており、それが変更されていないことを信頼できる。</span><span class="sxs-lookup"><span data-stu-id="fa145-207">You know the conflicting version and can rely on it not changing.</span></span>

<span data-ttu-id="fa145-208">`Newtonsoft.Json` パッケージは、この最後のシナリオの好例です。</span><span class="sxs-lookup"><span data-stu-id="fa145-208">The `Newtonsoft.Json` package is a good example of this last scenario.</span></span> <span data-ttu-id="fa145-209">これは、PowerShell 6 以降の依存関係であり、Windows PowerShell では使用されません。</span><span class="sxs-lookup"><span data-stu-id="fa145-209">This is a dependency of PowerShell 6 and above, and isn't used in Windows PowerShell.</span></span> <span data-ttu-id="fa145-210">つまり、バージョン管理の競合を解決する簡単な方法は、対象とする PowerShell のすべてのバージョンで最も低いバージョンの `Newtonsoft.Json` をターゲットにすることです。</span><span class="sxs-lookup"><span data-stu-id="fa145-210">Meaning a simple way to resolve versioning conflicts is to target the lowest version of `Newtonsoft.Json` across the PowerShell versions you wish to target.</span></span>

<span data-ttu-id="fa145-211">たとえば、PowerShell 6.2.6 と PowerShell 7.0.2 のどちらでも、現在は `Newtonsoft.Json` バージョン 12.0.3 が使用されています。</span><span class="sxs-lookup"><span data-stu-id="fa145-211">For example, PowerShell 6.2.6 and PowerShell 7.0.2 both currently use `Newtonsoft.Json` version 12.0.3.</span></span> <span data-ttu-id="fa145-212">そのため、Windows PowerShell、PowerShell 6、PowerShell 7 をターゲットとするモジュールを作成するには、依存関係として `Newtonsoft.Json 12.0.3` をターゲットにし、ビルドされるモジュールにそれを組み込みます。</span><span class="sxs-lookup"><span data-stu-id="fa145-212">So, to create a module targeting Windows PowerShell, PowerShell 6, and PowerShell 7, you would target `Newtonsoft.Json 12.0.3` as a dependency and include it in your built module.</span></span> <span data-ttu-id="fa145-213">モジュールが PowerShell 6 または 7 に読み込まれるときには、PowerShell 独自の `Newtonsoft.Json` アセンブリが既に読み込まれています。</span><span class="sxs-lookup"><span data-stu-id="fa145-213">When the module is loaded in PowerShell 6 or 7, PowerShell's own `Newtonsoft.Json` assembly is already loaded.</span></span> <span data-ttu-id="fa145-214">また、それはモジュールに必要な最低のバージョンであるため、解決は成功します。</span><span class="sxs-lookup"><span data-stu-id="fa145-214">Also, it is at least the version required for your module, so resolution succeeds.</span></span> <span data-ttu-id="fa145-215">Windows PowerShell では、アセンブリは PowerShell 内にまだ存在しません。</span><span class="sxs-lookup"><span data-stu-id="fa145-215">In Windows PowerShell, the assembly isn't already present in PowerShell.</span></span> <span data-ttu-id="fa145-216">そのため、代わりにモジュール フォルダーから読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="fa145-216">So, it's loaded from your module folder instead.</span></span>

<span data-ttu-id="fa145-217">一般に、`Microsoft.PowerShell.Sdk` や `System.Management.Automation` などの具体的な PowerShell パッケージをターゲットとする場合、NuGet で必要とされる適切な依存関係のバージョンを解決できるはずです。</span><span class="sxs-lookup"><span data-stu-id="fa145-217">Generally, when targeting a concrete PowerShell package, like `Microsoft.PowerShell.Sdk` or `System.Management.Automation`, NuGet should be able to resolve the right dependency versions required.</span></span> <span data-ttu-id="fa145-218">Windows PowerShell と PowerShell 6 以降の両方をターゲットにすると、複数のフレームワークまたは `PowerShellStandard.Library` のどちらを対象にするかを選択する必要があるため、より困難になります。</span><span class="sxs-lookup"><span data-stu-id="fa145-218">Targeting both Windows PowerShell and PowerShell 6+ becomes more difficult because you must choose between targeting multiple frameworks or `PowerShellStandard.Library`.</span></span>

<span data-ttu-id="fa145-219">次のような状況では、共通の依存関係バージョンへの固定は動作しません。</span><span class="sxs-lookup"><span data-stu-id="fa145-219">Circumstances where pinning to a common dependency version won't work include:</span></span>

- <span data-ttu-id="fa145-220">競合が間接的な依存関係に関するものであり、どの依存関係も共通バージョンを使用するように構成できない。</span><span class="sxs-lookup"><span data-stu-id="fa145-220">The conflict is with an indirect dependency, and none of your dependencies can be configured to use a common version.</span></span>
- <span data-ttu-id="fa145-221">他の依存関係のバージョンが頻繁に変更される可能性があるため、共通バージョンへの固定は短期的な解決にすぎない。</span><span class="sxs-lookup"><span data-stu-id="fa145-221">The other dependency version is likely to change often, so settling on a common version is only a short-term fix.</span></span>

### <a name="add-an-assemblyresolve-event-handler-to-create-a-dynamic-binding-redirect"></a><span data-ttu-id="fa145-222">AssemblyResolve イベント ハンドラーを追加して動的バインド リダイレクトを作成する</span><span class="sxs-lookup"><span data-stu-id="fa145-222">Add an AssemblyResolve event handler to create a dynamic binding redirect</span></span>

<span data-ttu-id="fa145-223">独自の依存関係のバージョンを変更することが不可能な場合や、難しすぎる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-223">Sometimes changing your own dependency version isn't possible or is too difficult.</span></span> <span data-ttu-id="fa145-224">別の方法として、`AssemblyResolve` イベントに対してイベント ハンドラーを登録することで、動的バインド リダイレクトを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="fa145-224">Another option is to set up a dynamic binding redirect by registering an event handler for the `AssemblyResolve` event.</span></span>

<span data-ttu-id="fa145-225">静的バインド リダイレクトと同様に、重要なのは、依存関係のすべてのコンシューマーで、実際の同じアセンブリを使用させることです。</span><span class="sxs-lookup"><span data-stu-id="fa145-225">As with a static binding redirect, the point is to force all consumers of a dependency to use the same actual assembly.</span></span> <span data-ttu-id="fa145-226">依存関係を読み込む呼び出しをインターセプトし、それらを目的のバージョンに常にリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="fa145-226">You intercept calls to load the dependency and always redirect them to the version you want.</span></span>

<span data-ttu-id="fa145-227">これは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fa145-227">This looks something like this:</span></span>

```csharp
// Register the event handler as early as you can in your code.
// A good option is to use the IModuleAssemblyInitializer interface
// that PowerShell provides to run code early on when your module is loaded.

// This class will be instantiated on module import and the OnImport() method run.
// Make sure that:
//  - the class is public
//  - the class has a public, parameterless constructor
//  - the class implements IModuleAssemblyInitializer
public class MyModuleInitializer : IModuleAssemblyInitializer
{
    public void OnImport()
    {
        AppDomain.CurrentDomain.AssemblyResolve += DependencyResolution.ResolveNewtonsoftJson;
    }
}

// Clean up the event handler when the the module is removed
// to prevent memory leaks.
//
// Like IModuleAssemblyInitializer, IModuleAssemblyCleanup allows
// you to register code to run when a module is removed (with Remove-Module).
// Make sure it is also public with a public parameterless contructor
// and implements IModuleAssemblyCleanup.
public class MyModuleCleanup : IModuleAssemblyCleanup
{
    public void OnRemove()
    {
        AppDomain.CurrentDomain.AssemblyResolve -= DependencyResolution.ResolveNewtonsoftJson;
    }
}

internal static class DependencyResolution
{
    private static readonly string s_modulePath = Path.GetDirectoryName(
        Assembly.GetExecutingAssembly().Location);

    public static Assembly ResolveNewtonsoftJson(object sender, ResolveEventArgs args)
    {
        // Parse the assembly name
        var assemblyName = new AssemblyName(args.Name);

        // We only want to handle the dependency we care about.
        // In this example it's Newtonsoft.Json.
        if (!assemblyName.Name.Equals("Newtonsoft.Json"))
        {
            return null;
        }

        // Generally the version of the dependency you want to load is the higher one,
        // since it's the most likely to be compatible with all dependent assemblies.
        // The logic here assumes our module always has the version we want to load.
        // Also note the use of Assembly.LoadFrom() here rather than Assembly.LoadFile().
        return Assembly.LoadFrom(Path.Combine(s_modulePath, "Newtonsoft.Json.dll"));
    }
}
```

<span data-ttu-id="fa145-228">技術的には PowerShell 内の ScriptBlock を登録して `AssemblyResolve` イベントを処理できますが、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fa145-228">You can technically register a scriptblock within PowerShell to handle an `AssemblyResolve` event, but:</span></span>

- <span data-ttu-id="fa145-229">`AssemblyResolve` イベントは任意のスレッドでトリガーされる可能性があり、PowerShell で処理できないものである場合があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-229">An `AssemblyResolve` event may be triggered on any thread, something that PowerShell will be unable to handle.</span></span>
- <span data-ttu-id="fa145-230">イベントが適切なスレッドで処理されている場合でも、PowerShell のスコープ設定の概念では、外部で定義されている変数に依存しないように、イベント ハンドラーの ScriptBlock を慎重に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-230">Even when events are handled on the right thread, PowerShell's scoping concepts mean that the event handler scriptblock must be written carefully to not depend on variables defined outside it.</span></span>

<span data-ttu-id="fa145-231">共通バージョンへのリダイレクトが機能しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-231">There are situations where redirecting to a common version won't work:</span></span>

- <span data-ttu-id="fa145-232">依存関係のバージョン間で破壊的変更が行われた場合、またはそれ以外で、リダイレクト先のバージョンでは利用できない機能に依存コードが依存している場合。</span><span class="sxs-lookup"><span data-stu-id="fa145-232">When the dependency has made breaking changes between versions, or when dependent code relies on a functionality otherwise not available in the version you redirect to.</span></span>
- <span data-ttu-id="fa145-233">競合する依存関係より前に、モジュールが読み込まれない場合。</span><span class="sxs-lookup"><span data-stu-id="fa145-233">When your module isn't loaded before the conflicting dependency.</span></span> <span data-ttu-id="fa145-234">依存関係が読み込まれた後で `AssemblyResolve` イベント ハンドラーを登録すると、そのイベント ハンドラーは実行されません。</span><span class="sxs-lookup"><span data-stu-id="fa145-234">If you register an `AssemblyResolve` event handler after the dependency has been loaded, it will never be fired.</span></span> <span data-ttu-id="fa145-235">別のモジュールとの依存関係の競合を回避しようとしている場合、最初に他のモジュールが読み込まれる可能性があるため、これが問題になることがあります。</span><span class="sxs-lookup"><span data-stu-id="fa145-235">If you're trying to prevent dependency conflicts with another module, this may be an issue, since the other module may be loaded first.</span></span>

### <a name="use-the-dependency-out-of-process"></a><span data-ttu-id="fa145-236">プロセス外の依存関係を使用する</span><span class="sxs-lookup"><span data-stu-id="fa145-236">Use the dependency out of process</span></span>

<span data-ttu-id="fa145-237">この解決策は、モジュール作成者よりモジュール ユーザー向けです。</span><span class="sxs-lookup"><span data-stu-id="fa145-237">This solution is more for module users than module authors.</span></span> <span data-ttu-id="fa145-238">この解決策は、既存の依存関係の競合が原因でモジュールが動作しない場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="fa145-238">This is a solution to use when confronted with a module that won't work due to an existing dependency conflict.</span></span>

<span data-ttu-id="fa145-239">依存関係の競合は、同じアセンブリの 2 つのバージョンが同じ .NET プロセスに読み込まれることが原因で発生します。</span><span class="sxs-lookup"><span data-stu-id="fa145-239">Dependency conflicts occur because two versions of the same assembly are loaded into the same .NET process.</span></span> <span data-ttu-id="fa145-240">簡単な解決策は、異なる両方のプロセスからでも機能を使用できる場合は、それらを異なるプロセスに読み込むことです。</span><span class="sxs-lookup"><span data-stu-id="fa145-240">A simple solution is to load them into different processes, as long as you can still use the functionality from both together.</span></span>

<span data-ttu-id="fa145-241">PowerShell には、これを実現するための方法がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="fa145-241">In PowerShell, there are several ways to achieve this:</span></span>

- <span data-ttu-id="fa145-242">サブプロセスとして PowerShell を呼び出す</span><span class="sxs-lookup"><span data-stu-id="fa145-242">Invoke PowerShell as a subprocess</span></span>

  <span data-ttu-id="fa145-243">現在のプロセスの外部で PowerShell コマンドを実行する簡単な方法は、コマンドの呼び出しで新しい PowerShell プロセスを直接開始することです。</span><span class="sxs-lookup"><span data-stu-id="fa145-243">A simple way to run a PowerShell command out of the current process is to just start a new PowerShell process directly with the command call:</span></span>

  ```powershell
  pwsh -c 'Invoke-ConflictingCommand'
  ```

  <span data-ttu-id="fa145-244">この方法の主な制限事項は、他のオプションより、結果の再構築が困難であったり、エラーが発生しやすくなったりすることです。</span><span class="sxs-lookup"><span data-stu-id="fa145-244">The main limitation here is that restructuring the result can be trickier or more error prone than other options.</span></span>

- <span data-ttu-id="fa145-245">PowerShell ジョブ システム</span><span class="sxs-lookup"><span data-stu-id="fa145-245">The PowerShell job system</span></span>

  <span data-ttu-id="fa145-246">PowerShell ジョブ システムでも、コマンドを新しい PowerShell プロセスに送信し、結果を返すことにより、プロセスの外部でコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="fa145-246">The PowerShell job system also runs commands out of process, by sending commands to a new PowerShell process and returning the results:</span></span>

  ```powershell
  $result = Start-Job { Invoke-ConflictingCommand } | Receive-Job -Wait
  ```

  <span data-ttu-id="fa145-247">この場合は、変数と状態が正しく渡されることを確認するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="fa145-247">In this case, you just need to be sure that any variables and state are passed in correctly.</span></span>

  <span data-ttu-id="fa145-248">また、ジョブ システムは、小さいコマンドを実行するときは多少煩雑になることがあります。</span><span class="sxs-lookup"><span data-stu-id="fa145-248">The job system can also be slightly cumbersome when running small commands.</span></span>

- <span data-ttu-id="fa145-249">PowerShell リモート処理</span><span class="sxs-lookup"><span data-stu-id="fa145-249">PowerShell remoting</span></span>

  <span data-ttu-id="fa145-250">PowerShell リモート処理を使用できる場合は、プロセスの外部でコマンドを実行する便利な手段になります。</span><span class="sxs-lookup"><span data-stu-id="fa145-250">When it's available, PowerShell remoting can be a useful way to run commands out of process.</span></span> <span data-ttu-id="fa145-251">リモート処理では、新しいプロセス内に新しい **PSSession** を作成し、PowerShell リモート処理を使用してそのコマンドを呼び出した後、競合する依存関係が含まれる他のモジュールでローカルに結果を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fa145-251">With remoting, you can create a fresh **PSSession** in a new process, call its commands over PowerShell remoting, then use the results locally with the other modules containing the conflicting dependencies.</span></span>

  <span data-ttu-id="fa145-252">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fa145-252">An example might look like this:</span></span>

  ```powershell
  # Create a local PowerShell session
  # where the module with conflicting assemblies will be loaded
  $s = New-PSSession

  # Import the module with the conflicting dependency via remoting,
  # exposing the commands locally
  Import-Module -PSSession $s -Name ConflictingModule

  # Run a command from the module with the conflicting dependencies
  Invoke-ConflictingCommand
  ```

- <span data-ttu-id="fa145-253">Windows PowerShell に対する暗黙的なリモート処理</span><span class="sxs-lookup"><span data-stu-id="fa145-253">Implicit remoting to Windows PowerShell</span></span>

  <span data-ttu-id="fa145-254">PowerShell 7 でのもう 1 つのオプションは、`Import-Module` で `-UseWindowsPowerShell` フラグを使用することです。</span><span class="sxs-lookup"><span data-stu-id="fa145-254">Another option in PowerShell 7 is to use the `-UseWindowsPowerShell` flag on `Import-Module`.</span></span> <span data-ttu-id="fa145-255">これにより、ローカル リモート処理セッションを通じて Windows PowerShell にモジュールがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="fa145-255">This will import the module through a local remoting session into Windows PowerShell:</span></span>

  ```powershell
  Import-Module -Name ConflictingModule -UseWindowsPowerShell
  ```

  <span data-ttu-id="fa145-256">Windows PowerShell では、モジュールが動作しない場合、または動作が異なる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fa145-256">Be aware that modules may not work with, or work differently with Windows PowerShell.</span></span>

#### <a name="when-out-of-process-invocation-should-not-be-used"></a><span data-ttu-id="fa145-257">プロセス外の呼び出しを使用してはいけない場合</span><span class="sxs-lookup"><span data-stu-id="fa145-257">When out-of-process invocation should not be used</span></span>

<span data-ttu-id="fa145-258">モジュールの作成者に関しては、プロセス外のコマンド呼び出しをモジュールに組み込むのは難しく、問題の原因となるエッジ ケースが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-258">As a module author, out-of-process command invocation is difficult to bake into a module and may have edge cases that cause issues.</span></span> <span data-ttu-id="fa145-259">具体的には、モジュールが動作する必要がある環境によっては、リモート処理とジョブを利用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-259">In particular, remoting and jobs may not be available in all environments where your module needs to work.</span></span> <span data-ttu-id="fa145-260">ただし、実装をプロセス外に移動し、PowerShell モジュールをシン クライアントとして使用できるようにするための一般的な原則が、引き続き適用される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-260">However, the general principle of moving the implementation out of process and allowing the PowerShell module to be a thinner client, may still be applicable.</span></span>

<span data-ttu-id="fa145-261">モジュールのユーザーに関しては、プロセス外の呼び出しが機能しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-261">As a module user, there are cases where out-of-process invocation won't work:</span></span>

- <span data-ttu-id="fa145-262">機能を使用する権限がないか、機能が有効になっていないため、PowerShell リモート処理を使用できない場合。</span><span class="sxs-lookup"><span data-stu-id="fa145-262">When PowerShell remoting is unavailable because you don't have privileges to use it or it is not enabled.</span></span>
- <span data-ttu-id="fa145-263">メソッドまたは別のコマンドへの入力として、特定の .NET 型が出力で必要な場合。</span><span class="sxs-lookup"><span data-stu-id="fa145-263">When a particular .NET type is needed from output as input to a method or another command.</span></span>
  <span data-ttu-id="fa145-264">PowerShell リモート処理経由で実行されるコマンドからは、厳密に型指定された .NET オブジェクトではなく、逆シリアル化されたオブジェクトが出力されます。</span><span class="sxs-lookup"><span data-stu-id="fa145-264">Commands running over PowerShell remoting emit deserialized objects rather than strongly-typed .NET objects.</span></span> <span data-ttu-id="fa145-265">これは、リモート処理経由でインポートされたコマンドの出力では、メソッドの呼び出しや厳密に型指定された API が動作しないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="fa145-265">This means that method calls and strongly typed APIs do not work with the output of commands imported over remoting.</span></span>

## <a name="more-robust-solutions"></a><span data-ttu-id="fa145-266">より堅牢な解決策</span><span class="sxs-lookup"><span data-stu-id="fa145-266">More robust solutions</span></span>

<span data-ttu-id="fa145-267">これまでの解決策にはすべて、動作しないシナリオとモジュールがありました。</span><span class="sxs-lookup"><span data-stu-id="fa145-267">The previous solutions all had scenarios and modules that don't work.</span></span> <span data-ttu-id="fa145-268">ただし、これらには、正しく実装するのが比較的簡単であるという長所もあります。</span><span class="sxs-lookup"><span data-stu-id="fa145-268">However, they also have the virtue of being relatively simple to implement correctly.</span></span> <span data-ttu-id="fa145-269">以下のソリューションはより堅牢ですが、適切に実装するにはより多くの労力が必要になり、慎重に記述されていない場合は微妙なバグが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-269">The following solutions are more robust, but require more effort to implement correctly and can introduce subtle bugs if not written carefully.</span></span>

### <a name="loading-through-net-core-assembly-load-contexts"></a><span data-ttu-id="fa145-270">.NET Core アセンブリ読み込みコンテキスト経由での読み込み</span><span class="sxs-lookup"><span data-stu-id="fa145-270">Loading through .NET Core Assembly Load Contexts</span></span>

<span data-ttu-id="fa145-271">.NET Core 1.0 では、同じアセンブリの複数のバージョンを同じランタイムに読み込む必要がある場合に特に対処するため、実装可能な API としての[アセンブリ読み込みコンテキスト](/dotnet/api/system.runtime.loader.assemblyloadcontext) (ALC) が導入されました。</span><span class="sxs-lookup"><span data-stu-id="fa145-271">[Assembly Load Contexts](/dotnet/api/system.runtime.loader.assemblyloadcontext) (ALCs) as an implementable API were introduced in .NET Core 1.0 to specifically address the need to load multiple versions of the same assembly into the same runtime.</span></span>

<span data-ttu-id="fa145-272">.NET Core および .NET 5 では、それらによって、アセンブリの競合するバージョンの読み込みの問題に対する最も堅牢な解決策が提供されます。</span><span class="sxs-lookup"><span data-stu-id="fa145-272">Within .NET Core and .NET 5, they offer the most robust solution to the problem of loading conflicting versions of an assembly.</span></span> <span data-ttu-id="fa145-273">ただし、カスタム ALC は .NET Framework では使用できません。</span><span class="sxs-lookup"><span data-stu-id="fa145-273">However, custom ALCs are not available in .NET Framework.</span></span> <span data-ttu-id="fa145-274">これは、この解決策が PowerShell 6 以降でのみ機能することを意味します。</span><span class="sxs-lookup"><span data-stu-id="fa145-274">This means that this solution only works in PowerShell 6 and above.</span></span>

<span data-ttu-id="fa145-275">現在、PowerShell での依存関係の分離に対して ALC を使用する場合の最適な例は、Visual Studio Code 用の PowerShell 拡張機能に対する言語サーバーである PowerShell エディター サービスでのものです。</span><span class="sxs-lookup"><span data-stu-id="fa145-275">Currently, the best example of using an ALC for dependency isolation in PowerShell is in PowerShell Editor Services, the language server for the PowerShell extension for Visual Studio Code.</span></span> <span data-ttu-id="fa145-276">PowerShell モジュール内で PowerShell エディター サービスの独自の依存関係がクラッシュしないように、[ALC が使用されます](https://github.com/PowerShell/PowerShellEditorServices/blob/master/src/PowerShellEditorServices.Hosting/Internal/PsesLoadContext.cs)。</span><span class="sxs-lookup"><span data-stu-id="fa145-276">An [ALC is used](https://github.com/PowerShell/PowerShellEditorServices/blob/master/src/PowerShellEditorServices.Hosting/Internal/PsesLoadContext.cs) to prevent PowerShell Editor Services' own dependencies from clashing with those in PowerShell modules.</span></span>

<span data-ttu-id="fa145-277">ALC を使用してモジュールの依存関係の分離を実装することは、概念的には難しいことですが、ここでは最小限の例について説明します。</span><span class="sxs-lookup"><span data-stu-id="fa145-277">Implementing module dependency isolation with an ALC is conceptually difficult, but we will work through a minimal example.</span></span> <span data-ttu-id="fa145-278">PowerShell 7 だけで動作することが意図された簡単なモジュールについて考えます。</span><span class="sxs-lookup"><span data-stu-id="fa145-278">Imagine we have a simple module that is only intended to work in PowerShell 7.</span></span>
<span data-ttu-id="fa145-279">ソース コードは次のように構成されています。</span><span class="sxs-lookup"><span data-stu-id="fa145-279">The source code is organized as follows:</span></span>

```
+ AlcModule.psd1
+ src/
    + TestAlcModuleCommand.cs
    + AlcModule.csproj
```

<span data-ttu-id="fa145-280">コマンドレットの実装は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fa145-280">The cmdlet implementation looks like this:</span></span>

```csharp
using Shared.Dependency;

namespace AlcModule
{
    [Cmdlet(VerbsDiagnostic.Test, "AlcModule")]
    public class TestAlcModuleCommand : Cmdlet
    {
        protected override void EndProcessing()
        {
            // Here's where our dependency gets used
            Dependency.Use();
            // Something trivial to make our cmdlet do *something*
            WriteObject("done!");
        }
    }
}
```

<span data-ttu-id="fa145-281">(大幅に単純化された) マニフェストは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fa145-281">The (heavily simplified) manifest, looks like this:</span></span>

```powershell
@{
    Author = 'Me'
    ModuleVersion = '0.0.1'
    RootModule = 'AlcModule.dll'
    CmdletsToExport = @('Test-AlcModule')
    PowerShellVersion = '7.0'
}
```

<span data-ttu-id="fa145-282">そして、`csproj` は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fa145-282">And the `csproj` looks like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Shared.Dependency" Version="1.0.0" />
    <PackageReference Include="Microsoft.PowerShell.Sdk" Version="7.0.1" PrivateAssets="all" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="fa145-283">このモジュールをビルドすると、生成される出力のレイアウトは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fa145-283">When we build this module, the generated output has the following layout:</span></span>

```
AlcModule/
  + AlcModule.psd1
  + AlcModule.dll
  + Shared.Dependency.dll
```

<span data-ttu-id="fa145-284">この例の `Shared.Dependency.dll` アセンブリには、競合する依存関係の問題があるものと仮定します。</span><span class="sxs-lookup"><span data-stu-id="fa145-284">In this example, our problem is in the `Shared.Dependency.dll` assembly, which is our imaginary conflicting dependency.</span></span> <span data-ttu-id="fa145-285">これは、モジュール固有のバージョンを使用できるように、ALC の背後に配置する必要がある依存関係です。</span><span class="sxs-lookup"><span data-stu-id="fa145-285">This is the dependency that we need to put behind an ALC so that we can use the module-specific version.</span></span>

<span data-ttu-id="fa145-286">次のようにモジュールを再設計する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-286">We need to re-engineer the module so that:</span></span>

- <span data-ttu-id="fa145-287">競合が発生しないように、モジュールの依存関係は、PowerShell の ALC ではなく、カスタム ALC にのみ読み込みます。</span><span class="sxs-lookup"><span data-stu-id="fa145-287">Module dependencies are only loaded into our custom ALC, and not into PowerShell's ALC, so there can be no conflict.</span></span> <span data-ttu-id="fa145-288">さらに、プロジェクトに依存関係を追加するとき、読み込みが動作し続けるよう、コードを継続的に追加するようなことはしたくありません。</span><span class="sxs-lookup"><span data-stu-id="fa145-288">Moreover, as we add more dependencies to our project, we don't want to continuously add more code to keep loading working.</span></span> <span data-ttu-id="fa145-289">代わりに、再利用可能で汎用的な依存関係解決ロジックが必要です。</span><span class="sxs-lookup"><span data-stu-id="fa145-289">Instead, we want reusable, generic dependency resolution logic.</span></span>
- <span data-ttu-id="fa145-290">PowerShell でのモジュールの読み込みは通常どおりに動作します。</span><span class="sxs-lookup"><span data-stu-id="fa145-290">Loading the module still works as normal in PowerShell.</span></span> <span data-ttu-id="fa145-291">PowerShell モジュール システムで必要なコマンドレットと他の型は、PowerShell 独自の ALC 内で定義されています。</span><span class="sxs-lookup"><span data-stu-id="fa145-291">Cmdlets and other types that the PowerShell module system needs are defined within PowerShell's own ALC.</span></span>

<span data-ttu-id="fa145-292">これらの 2 つの要件を仲介するには、モジュールを 2 つのアセンブリに分割する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-292">To mediate these two requirements, we must break up our module into two assemblies:</span></span>

- <span data-ttu-id="fa145-293">PowerShell のモジュール システムでモジュールを正しく読み込むために必要なすべての型の定義が含まれるコマンドレット アセンブリ `AlcModule.Cmdlets.dll`。</span><span class="sxs-lookup"><span data-stu-id="fa145-293">A cmdlets assembly, `AlcModule.Cmdlets.dll`, that contains definitions of all the types that PowerShell's module system needs to load our module correctly.</span></span> <span data-ttu-id="fa145-294">つまり、`Cmdlet` 基底クラスと、`AssemblyLoadContext.Default.Resolving` でカスタム ALC を通して `AlcModule.Engine.dll` が適切に読み込まれるようにイベント ハンドラーを設定する `IModuleAssemblyInitializer` が実装されているクラスの、すべての実装。</span><span class="sxs-lookup"><span data-stu-id="fa145-294">Namely, any implementations of the `Cmdlet` base class and the class that implements `IModuleAssemblyInitializer`, which sets up the event handler for `AssemblyLoadContext.Default.Resolving` to properly load `AlcModule.Engine.dll` through our custom ALC.</span></span> <span data-ttu-id="fa145-295">PowerShell 7 では、他の ALC で読み込まれるアセンブリで定義されている型は意図的に非表示にされているため、PowerShell にパブリックに公開される型は、ここでも定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-295">Since PowerShell 7 deliberately hides types defined in assemblies loaded in other ALCs, any types that are meant to be publicly exposed to PowerShell must also be defined here.</span></span> <span data-ttu-id="fa145-296">最後に、カスタム ALC の定義がこのアセンブリで定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-296">Finally, our custom ALC definition needs to be defined in this assembly.</span></span> <span data-ttu-id="fa145-297">このアセンブリ内のそれ以外のコードは、できるだけ少なくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-297">Beyond that, as little code as possible should live in this assembly.</span></span>
- <span data-ttu-id="fa145-298">モジュールの実際の実装を処理するエンジン アセンブリ `AlcModule.Engine.dll`。</span><span class="sxs-lookup"><span data-stu-id="fa145-298">An engine assembly, `AlcModule.Engine.dll`, that handles the actual implementation of the module.</span></span>
  <span data-ttu-id="fa145-299">PowerShell ALC でこれに含まれる型を使用できますが、最初はカスタム ALC を通じて読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="fa145-299">Types from this are available in the PowerShell ALC, but it will initially be loaded through our custom ALC.</span></span> <span data-ttu-id="fa145-300">その依存関係は、カスタム ALC にのみ読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="fa145-300">Its dependencies are only loaded into the custom ALC.</span></span> <span data-ttu-id="fa145-301">実質的に、これは 2 つの ALC 間の "_ブリッジ_" になります。</span><span class="sxs-lookup"><span data-stu-id="fa145-301">Effectively, this becomes a _bridge_ between the two ALCs.</span></span>

<span data-ttu-id="fa145-302">このブリッジの概念を使用すると、新しいアセンブリの状況は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fa145-302">Using this bridge concept, our new assembly situation looks like this:</span></span>

![2 つの ALC をブリッジする AlcModule.Engine.dll を表す図](./media/resolving-dependency-conflicts/alc-diagram.jpg)

<span data-ttu-id="fa145-304">既定の ALC の依存関係プローブ ロジックによって、カスタム ALC に読み込まれる依存関係が解決されないようにするには、モジュールのこれら 2 つの部分を、異なるディレクトリに分ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-304">To make sure the default ALC's dependency probing logic does not resolve the dependencies to be loaded into the custom ALC, we need to separate these two parts of the module in different directories.</span></span> <span data-ttu-id="fa145-305">新しいモジュール レイアウトは次のような構造になります。</span><span class="sxs-lookup"><span data-stu-id="fa145-305">The new module layout has the following structure:</span></span>

```
AlcModule/
  AlcModule.Cmdlets.dll
  AlcModule.psd1
  Dependencies/
  | + AlcModule.Engine.dll
  | + Shared.Dependency.dll
```

<span data-ttu-id="fa145-306">実装がどのように変化するかを確認するため、最初に `AlcModule.Engine.dll` の実装について説明します。</span><span class="sxs-lookup"><span data-stu-id="fa145-306">To see how the implementation changes, we'll start with the implementation of `AlcModule.Engine.dll`:</span></span>

```csharp
using Shared.Dependency;

namespace AlcModule.Engine
{
    public class AlcEngine
    {
        public static void Use()
        {
            Dependency.Use();
        }
    }
}
```

<span data-ttu-id="fa145-307">これは依存関係 `Shared.Dependency.dll` 用の簡単なコンテナーですが、他のアセンブリ内のコマンドレットによって PowerShell 用にラップされる機能に対する .NET API と考える必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-307">This is a simple container for the dependency, `Shared.Dependency.dll`, but you should think of it as the .NET API for your functionality that the cmdlets in the other assembly wrap for PowerShell.</span></span>

<span data-ttu-id="fa145-308">`AlcModule.Cmdlets.dll` のコマンドレットは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fa145-308">The cmdlet in `AlcModule.Cmdlets.dll` looks like this:</span></span>

```csharp
// Reference our module's Engine implementation here
using AlcModule.Engine;

namespace AlcModule.Cmdlets
{
    [Cmdlet(VerbsDiagnostic.Test, "AlcModule")]
    public class TestAlcModuleCommand : Cmdlet
    {
        protected override void EndProcessing()
        {
            AlcEngine.Use();
            WriteObject("done!");
        }
    }
}
```

<span data-ttu-id="fa145-309">この時点で、**AlcModule** を読み込んで `Test-AlcModule` を実行すると、既定の ALC によって `Alc.Engine.dll` が読み込まれて `EndProcessing()` の実行が試みられるときに、`FileNotFoundException` が発生します。</span><span class="sxs-lookup"><span data-stu-id="fa145-309">At this point, if we were to load **AlcModule** and run `Test-AlcModule`, we get a `FileNotFoundException` when the default ALC tries to load `Alc.Engine.dll` to run `EndProcessing()`.</span></span> <span data-ttu-id="fa145-310">これは、非表示にする依存関係が既定の ALC によって検出されないことを意味するので、適切なことです。</span><span class="sxs-lookup"><span data-stu-id="fa145-310">This is good, since it means the default ALC can't find the dependencies we want to hide.</span></span>

<span data-ttu-id="fa145-311">次に、`AlcModule.Engine.dll` の解決方法を認識できるように、`AlcModule.Cmdlets.dll` にコードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-311">Now we need to add code to `AlcModule.Cmdlets.dll` so that it knows how to resolve `AlcModule.Engine.dll`.</span></span> <span data-ttu-id="fa145-312">最初に、モジュールの `Dependencies` ディレクトリからアセンブリを解決するカスタム ALC を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-312">First we must define our custom ALC that will resolve assemblies from our module's `Dependencies` directory:</span></span>

```csharp
namespace AlcModule.Cmdlets
{
    internal class AlcModuleAssemblyLoadContext : AssemblyLoadContext
    {
        private readonly string _dependencyDirPath;

        public AlcModuleAssemblyLoadContext(string dependencyDirPath)
        {
            _depdendencyDirPath = dependencyDirPath;
        }

        protected override Assembly Load(AssemblyName assemblyName)
        {
            // We do the simple logic here of
            // looking for an assembly of the given name
            // in the configured dependency directory
            string assemblyPath = Path.Combine(
                s_dependencyDirPath,
                $"{assemblyName.Name}.dll");

            // The ALC must use inherited methods to load assemblies
            // Assembly.Load*() won't work here
            return LoadFromAssemblyPath(assemblyPath);
        }
    }
}
```

<span data-ttu-id="fa145-313">次に、カスタム ALC を既定の ALC の `Resolving` イベントにフックする必要があります。これは、アプリケーション ドメインでの `AssemblyResolve` イベントの ALC バージョンです。</span><span class="sxs-lookup"><span data-stu-id="fa145-313">Then we need to hook up our custom ALC to the default ALC's `Resolving` event, which is the ALC version of the `AssemblyResolve` event on Application Domains.</span></span> <span data-ttu-id="fa145-314">`EndProcessing()` が呼び出されると、`AlcModule.Engine.dll` を見つけるためにこのイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="fa145-314">This event is fired to find `AlcModule.Engine.dll` when `EndProcessing()` is called.</span></span>

```csharp
namespace AlcModule.Cmdlets
{
    public class AlcModuleResolveEventHandler : IModuleAssemblyInitializer, IModuleAssemblyCleanup
    {
        // Get the path of the dependency directory.
        // In this case we find it relative to the AlcModule.Cmdlets.dll location
        private static readonly string s_dependencyDirPath = Path.GetFullPath(
            Path.Combine(
                Path.GetDirectoryName(Assembly.GetExecutingAssembly().Location),
                "Dependencies"));

        private static readonly AlcModuleAssemblyLoadContext s_dependencyAlc = new AlcModuleAssemblyLoadContext(s_dependencyDirPath);

        public void OnImport()
        {
            // Add the Resolving event handler here
            AssemblyLoadContext.Default.Resolving += ResolveAlcEngine;
        }

        public void OnRemove()
        {
          // Remove the Resolving event handler here
          AssemblyLoadContext.Default.Resolving -= ResolveAlcEngine;
        }

        private static Assembly ResolveAlcEngine(
            AssemblyLoadContext defaultAlc,
            AssemblyName assemblyToResolve)
        {
            // We only want to resolve the Alc.Engine.dll assembly here.
            // Because this will be loaded into the custom ALC,
            // all of *its* dependencies will be resolved
            // by the logic we defined for that ALC's implementation.
            //
            // Note that we are safe in our assumption that the name is enough
            // to distinguish our assembly here,
            // since it's unique to our module.
            // There should be no other AlcModule.Engine.dll on the system.
            if (!assemblyToResolve.Name.Equals("AlcModule.Engine"))
            {
                return null;
            }

            // Allow our ALC to handle the directory discovery concept
            //
            // This is where Alc.Engine.dll is loaded into our custom ALC
            // and then passed through into PowerShell's ALC,
            // becoming the bridge between both
            return s_dependencyAlc.LoadFromAssemblyName(assemblyToResolve);
        }
    }
}
```

<span data-ttu-id="fa145-315">新しい実装で、モジュールが読み込まれて `Test-AlcModule` が実行されるときに発生する呼び出しのシーケンスを確認します。</span><span class="sxs-lookup"><span data-stu-id="fa145-315">With the new implementation, take a look at the sequence of calls that occurs when the module is loaded and `Test-AlcModule` is run:</span></span>

![カスタム ALC を使用して依存関係を読み込む呼び出しのシーケンスの図](./media/resolving-dependency-conflicts/alc-sequence.png)

<span data-ttu-id="fa145-317">興味深い点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fa145-317">Some points of interest are:</span></span>

- <span data-ttu-id="fa145-318">モジュールで `Resolving` イベントが読み込まれて設定されると、`IModuleAssemblyInitializer` が最初に実行されます。</span><span class="sxs-lookup"><span data-stu-id="fa145-318">The `IModuleAssemblyInitializer` is run first when the module loads and sets the `Resolving` event.</span></span>
- <span data-ttu-id="fa145-319">`Test-AlcModule` が実行され、その `EndProcessing()` メソッドが呼び出されるまで、依存関係は読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="fa145-319">We don't load the dependencies until `Test-AlcModule` is run and its `EndProcessing()` method is called.</span></span>
- <span data-ttu-id="fa145-320">`EndProcessing()` が呼び出されると、既定の ALC では `AlcModule.Engine.dll` を検出できず、`Resolving` イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="fa145-320">When `EndProcessing()` is called, the default ALC fails to find `AlcModule.Engine.dll` and fires the `Resolving` event.</span></span>
- <span data-ttu-id="fa145-321">イベント ハンドラーによってカスタム ALC が既定の ALC にフックされ、`AlcModule.Engine.dll` のみが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="fa145-321">Our event handler hooks up the custom ALC to the default ALC and loads `AlcModule.Engine.dll` only.</span></span>
- <span data-ttu-id="fa145-322">`AlcModule.Engine.dll` 内で `AlcEngine.Use()` が呼び出されると、カスタム ALC が再び開始して `Shared.Dependency.dll` が解決されます。</span><span class="sxs-lookup"><span data-stu-id="fa145-322">When `AlcEngine.Use()` is called within `AlcModule.Engine.dll`, the custom ALC again kicks in to resolve `Shared.Dependency.dll`.</span></span> <span data-ttu-id="fa145-323">具体的には、既定の ALC 内の何とも競合せず、`Dependencies` ディレクトリだけが検索されるので、"_この_" `Shared.Dependency.dll` が常に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="fa145-323">Specifically, it always loads _our_ `Shared.Dependency.dll` since it never conflicts with anything in the default ALC and only looks in our `Dependencies` directory.</span></span>

<span data-ttu-id="fa145-324">実装をアセンブルすると、新しいソース コード レイアウトは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fa145-324">Assembling the implementation, our new source code layout looks like this:</span></span>

```
+ AlcModule.psd1
+ src/
  + AlcModule.Cmdlets/
  | + AlcModule.Cmdlets.csproj
  | + TestAlcModuleCommand.cs
  | + AlcModuleAssemblyLoadContext.cs
  | + AlcModuleInitializer.cs
  |
  + AlcModule.Engine/
  | + AlcModule.Engine.csproj
  | + AlcEngine.cs
```

<span data-ttu-id="fa145-325">AlcModule.Cmdlets.csproj は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fa145-325">AlcModule.Cmdlets.csproj looks like:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <ProjectReference Include="..\AlcModule.Engine\AlcModule.Engine.csproj" />
    <PackageReference Include="Microsoft.PowerShell.Sdk" Version="7.0.1" PrivateAssets="all" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="fa145-326">AlcModule.Engine.csproj は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fa145-326">AlcModule.Engine.csproj looks like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Shared.Dependency" Version="1.0.0" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="fa145-327">したがって、モジュールをビルドするときの戦略は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fa145-327">So, when we build the module, our strategy is:</span></span>

- <span data-ttu-id="fa145-328">`AlcModule.Engine` をビルドします</span><span class="sxs-lookup"><span data-stu-id="fa145-328">Build `AlcModule.Engine`</span></span>
- <span data-ttu-id="fa145-329">`AlcModule.Cmdlets` をビルドします</span><span class="sxs-lookup"><span data-stu-id="fa145-329">Build `AlcModule.Cmdlets`</span></span>
- <span data-ttu-id="fa145-330">`AlcModule.Engine` から `Dependencies` ディレクトリにすべてのものをコピーし、何をコピーしたかを憶えておきます</span><span class="sxs-lookup"><span data-stu-id="fa145-330">Copy everything from `AlcModule.Engine` into the `Dependencies` directory, and remember what we copied</span></span>
- <span data-ttu-id="fa145-331">`AlcModule.Engine` に存在しなかったすべてのものを、`AlcModule.Cmdlets` からベース モジュール ディレクトリにコピーします</span><span class="sxs-lookup"><span data-stu-id="fa145-331">Copy everything from `AlcModule.Cmdlets` that wasn't in `AlcModule.Engine` into the base module directory</span></span>

<span data-ttu-id="fa145-332">ここでのモジュール レイアウトは依存関係の分離にとって非常に重要であるため、ソース ルートから使用するビルド スクリプトは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fa145-332">Since the module layout here is so crucial to dependency separation, here's a build script to use from the source root:</span></span>

```powershell
param(
    # The .NET build configuration
    [ValidateSet('Debug', 'Release')]
    [string]
    $Configuration = 'Debug'
)

# Convenient reusable constants
$mod = "AlcModule"
$netcore = "netcoreapp3.1"
$copyExtensions = @('.dll', '.pdb')

# Source code locations
$src = "$PSScriptRoot/src"
$engineSrc = "$src/$mod.Engine"
$cmdletsSrc = "$src/$mod.Cmdlets"

# Generated output locations
$outDir = "$PSScriptRoot/out/$mod"
$outDeps = "$outDir/Dependencies"

# Build AlcModule.Engine
Push-Location $engineSrc
dotnet publish -c $Configuration
Pop-Location

# Build AlcModule.Cmdlets
Push-Location $cmdletsSrc
dotnet publish -c $Configuration
Pop-Location

# Ensure out directory exists and is clean
Remove-Item -Path $outDir -Recurse -ErrorAction Ignore
New-Item -Path $outDir -ItemType Directory
New-Item -Path $outDeps -ItemType Directory

# Copy manifest
Copy-Item -Path "$PSScriptRoot/$mod.psd1"

# Copy each Engine asset and remember it
$deps = [System.Collections.Generic.Hashtable[string]]::new()
Get-ChildItem -Path "$engineSrc/bin/$Configuration/$netcore/publish/" |
    Where-Object { $_.Extension -in $copyExtensions } |
    ForEach-Object { [void]$deps.Add($_.Name); Copy-Item -Path $_.FullName -Destination $outDeps }

# Now copy each Cmdlets asset, not taking any found in Engine
Get-ChildItem -Path "$cmdletsSrc/bin/$Configuration/$netcore/publish/" |
    Where-Object { -not $deps.Contains($_.Name) -and $_.Extension -in $copyExtensions } |
    ForEach-Object { Copy-Item -Path $_.FullName -Destination $outDir }
```

<span data-ttu-id="fa145-333">最後に、時間の経過と共に依存関係が追加されても堅牢な状態が維持されるアセンブリ読み込みコンテキストを使用して、モジュールの依存関係を分離する、一般的な方法があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-333">Finally, we have a general way to use an Assembly Load Context to isolate our module's dependencies that remains robust over time as more dependencies are added.</span></span>

<span data-ttu-id="fa145-334">詳細な例については、こちらの [GitHub リポジトリ](https://github.com/rjmholt/ModuleDependencyIsolationExample)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa145-334">For a more detailed example, go to this [GitHub repository](https://github.com/rjmholt/ModuleDependencyIsolationExample).</span></span> <span data-ttu-id="fa145-335">この例では、.NET Framework 内でモジュールを動作させたまま、ALC を使用するようにそのモジュールを移行する方法が示されています。</span><span class="sxs-lookup"><span data-stu-id="fa145-335">This example demonstrates how to migrate a module to use an ALC, while keeping that module working in .NET Framework.</span></span> <span data-ttu-id="fa145-336">また、.NET Standard と PowerShell Standard を使用して、中核となる実装を簡略化する方法についても説明されています。</span><span class="sxs-lookup"><span data-stu-id="fa145-336">It also show how to use .NET Standard and PowerShell Standard to simplify the core implementation.</span></span>

### <a name="assembly-resolve-handler-for-side-by-side-loading-with-assemblyloadfile"></a><span data-ttu-id="fa145-337">`Assembly.LoadFile()` での side-by-side 読み込みのためのアセンブリ解決ハンドラー</span><span class="sxs-lookup"><span data-stu-id="fa145-337">Assembly resolve handler for side-by-side loading with `Assembly.LoadFile()`</span></span>

<span data-ttu-id="fa145-338">side-by-side アセンブリ読み込みを実現するための、もう 1 つの、おそらくはさらに簡単な方法は、`AssemblyResolve` イベントを `Assembly.LoadFile()` にフックすることです。</span><span class="sxs-lookup"><span data-stu-id="fa145-338">Another, possibly simpler, way to achieve side-by-side assembly loading is to hook up an `AssemblyResolve` event to `Assembly.LoadFile()`.</span></span> <span data-ttu-id="fa145-339">`Assembly.LoadFile()` を使用すると、最も簡単に解決策を実装できるメリットがあり、.NET Core と .NET Framework の両方で動作します。</span><span class="sxs-lookup"><span data-stu-id="fa145-339">Using `Assembly.LoadFile()` has the advantage of being the simplest solution to implement and works with both .NET Core and .NET Framework.</span></span>

<span data-ttu-id="fa145-340">これを示すため、動的バインド リダイレクトの例と、上記のアセンブリ読み込みコンテキストの例のアイデアを組み合わせる実装の簡単な例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="fa145-340">To show this, let's take a look at a quick example of an implementation that combines ideas from our dynamic binding redirect example, and the Assembly Load Context example above.</span></span>

<span data-ttu-id="fa145-341">このモジュールは **LoadFileModule** という名前で、簡単なコマンド `Test-LoadFile [-Path] <path>` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fa145-341">We'll call this module **LoadFileModule**, which has a trivial command `Test-LoadFile [-Path] <path>`.</span></span> <span data-ttu-id="fa145-342">このモジュールでは、`CsvHelper` アセンブリ (バージョン 15.0.5) の依存関係を取得します。</span><span class="sxs-lookup"><span data-stu-id="fa145-342">This module takes a dependency on the `CsvHelper` assembly (version 15.0.5).</span></span>

<span data-ttu-id="fa145-343">ALC モジュールと同様に、最初にモジュールを 2 つの部分に分割する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-343">As with the ALC module, we must first split up the module into two pieces.</span></span>

<span data-ttu-id="fa145-344">1 つ目の部分 `LoadFileModule.Engine` では、実際の実装を行います。</span><span class="sxs-lookup"><span data-stu-id="fa145-344">The first part does the actual implementation, `LoadFileModule.Engine`:</span></span>

```csharp
using CsvHelper;

namespace LoadFileModule.Engine
{
    public class Runner
    {
        public void Use(string path)
        {
            // Here's where we use the CsvHelper dependency
            using (var reader = new StreamReader(path))
            using (var csvReader = new CsvReader(reader, CultureInfo.InvariantCulture))
            {
                // Imagine we do something useful here...
            }
        }
    }
}
```

<span data-ttu-id="fa145-345">2 つ目の部分 `LoadFileModule.Cmdlets` は、PowerShell によって直接読み込まれるものです。</span><span class="sxs-lookup"><span data-stu-id="fa145-345">The second part is what PowerShell loads directly, `LoadFileModule.Cmdlets`.</span></span> <span data-ttu-id="fa145-346">ALC モジュールと同様の戦略を使用して、依存関係を別のディレクトリに分離します。</span><span class="sxs-lookup"><span data-stu-id="fa145-346">We use a strategy similar to the ALC module, where we isolate dependencies in a separate directory.</span></span> <span data-ttu-id="fa145-347">ただし今回は、`LoadFileModule.Engine.dll` だけでなく、すべてのアセンブリを解決イベントと共に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="fa145-347">But this time, we load all assemblies in with a resolve event rather than just `LoadFileModule.Engine.dll`.</span></span>

```csharp
using LoadFileModule.Engine;

namespace LoadFileModule.Cmdlets
{
    // Actual cmdlet definition
    [Cmdlet(VerbsDiagnostic.Test, "LoadFile")]
    public class TestLoadFileCommand : Cmdlet
    {
        [Parameter(Mandatory = true)]
        public string Path { get; set; }

        protected override void EndProcessing()
        {
            // Here's where we use LoadFileModule.Engine
            new Runner().Use(Path);
        }
    }

    // This class controls our dependency resolution
    public class ModuleContextHandler : IModuleAssemblyInitializer, IModuleAssemblyCleanup
    {
        // We catalog our dependencies here to ensure we don't load anything else
        private static IReadOnlyDictionary<string, int> s_dependencies = new Dictionary<string, int>
        {
            { "CsvHelper", 15 },
        };

        // Set up the path to our dependency directory within the module
        private static string s_dependenciesDirPath = Path.GetFullPath(
            Path.Combine(
                Path.GetDirectoryName(Assembly.GetExecutingAssembly().Location),
                "Dependencies"));

        // This makes sure we only try to resolve dependencies when the module is loaded
        private static bool s_engineLoaded = false;

        public void OnImport()
          {
            // Set up our event when the module is loaded
            AppDomain.CurrentDomain.AssemblyResolve += HandleResolveEvent;
        }

        public void OnRemove(PSModuleInfo psModuleInfo)
        {
            // Unset the event when the module is unloaded
            AppDomain.CurrentDomain.AssemblyResolve -= HandleResolveEvent;
        }

        private static Assembly HandleResolveEvent(object sender, ResolveEventArgs args)
        {
            var asmName = new AssemblyName(args.Name);

            // First we want to know if this is the top-level assembly
            if (asmName.Name.Equals("LoadFileModule.Engine"))
            {
                s_engineLoaded = true;
                return Assembly.LoadFile(Path.Combine(s_dependenciesDirPath, "Unrelated.Engine.dll"));
            }

            // Otherwise, if that assembly has been loaded, we must try to resolve its dependencies too
            if (s_engineLoaded
                && s_dependencies.TryGetValue(asmName.Name, out int requiredMajorVersion)
                && asmName.Version.Major == requiredMajorVersion)
            {
                string asmPath = Path.Combine(s_dependenciesDirPath, $"{asmName.Name}.dll");
                return Assembly.LoadFile(asmPath);
            }

            return null;
        }
    }
}
```

<span data-ttu-id="fa145-348">最後に、モジュールのレイアウトも ALC モジュールと似ています。</span><span class="sxs-lookup"><span data-stu-id="fa145-348">Finally, the layout of the module is also similar to the ALC module:</span></span>

```
LoadFileModule/
  + LoadFileModule.Cmdlets.dll
  + LoadFileModule.psd1
  + Dependencies/
  |  + LoadFileModule.Engine.dll
  |  + CsvHelper.dll
```

<span data-ttu-id="fa145-349">この構造を使用すると、**LoadFileModule** を、**CsvHelper** に依存関係が含まれる他のモジュールと共に読み込むことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="fa145-349">With this structure in place, **LoadFileModule** now supports being loaded alongside other modules with a dependency on **CsvHelper**.</span></span>

<span data-ttu-id="fa145-350">このハンドラーは、アプリケーション ドメイン全体の**すべての** `AssemblyResolve` イベントに適用されるため、ここでは設計に関していくつか特定の選択を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-350">Because our handler applies to **all** `AssemblyResolve` events across the Application Domain, we need to make some specific design choices here:</span></span>

- <span data-ttu-id="fa145-351">このイベントによって他の読み込みが妨げられる可能性のある時間を短くするため、`LoadFileModule.Engine.dll` が読み込まれた後でのみ、一般的な依存関係の読み込みの処理を開始します。</span><span class="sxs-lookup"><span data-stu-id="fa145-351">To narrow the window in which our event may interfere with other loading, we only start handling general dependency loading after `LoadFileModule.Engine.dll` has been loaded.</span></span>
- <span data-ttu-id="fa145-352">PowerShell ではなく `LoadFile()` の呼び出しによって読み込まれるように、`LoadFileModule.Engine.dll` を Dependencies ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="fa145-352">We push `LoadFileModule.Engine.dll` out into the Dependencies directory, so that it's loaded by a `LoadFile()` call rather than by PowerShell.</span></span> <span data-ttu-id="fa145-353">これは、PowerShell で (たとえば) 別の `CsvHelper.dll` が読み込まれている場合でも、独自の依存関係の読み込みによって常に `AssemblyResolve` イベントが発生することを意味します。</span><span class="sxs-lookup"><span data-stu-id="fa145-353">This means its own dependency loads always raise an `AssemblyResolve` event, even if another `CsvHelper.dll` (for example) is loaded in PowerShell.</span></span>
  <span data-ttu-id="fa145-354">これにより、適切な依存関係を見つける機会ができます。</span><span class="sxs-lookup"><span data-stu-id="fa145-354">This gives us the opportunity to find the correct dependency.</span></span>
- <span data-ttu-id="fa145-355">モジュール用に特定の依存関係のみを解決する必要があるため、依存関係の名前とバージョンの辞書をハンドラーにコーディングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-355">Since we must only resolve the specific dependencies for our module, we're forced to code a dictionary of dependency names and versions into our handler.</span></span> <span data-ttu-id="fa145-356">このような場合は、`ResolveEventArgs.RequestingAssembly` プロパティを使用して、`CsvHelper` がモジュールによって要求されているかどうかを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="fa145-356">In our particular case, it would be possible to use the `ResolveEventArgs.RequestingAssembly` property to work out whether `CsvHelper` is being requested by our module.</span></span> <span data-ttu-id="fa145-357">ただし、たとえば `CsvHelper` 自体によって `AssemblyResolve` イベントが発生した場合など、依存関係の依存関係に対してはこれは機能しません。</span><span class="sxs-lookup"><span data-stu-id="fa145-357">But this doesn't work for dependencies of dependencies; for example, if `CsvHelper` itself raised an `AssemblyResolve` event.</span></span> <span data-ttu-id="fa145-358">これを行うには、要求されたアセンブリと `Dependencies` ディレクトリ内のアセンブリのメタデータの比較など、さらに困難な他の方法があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-358">There are other, harder ways to do this, such as comparing requested assemblies to the metadata of assemblies in the `Dependencies` directory.</span></span> <span data-ttu-id="fa145-359">ただし、この例では、問題を強調し、例を簡単にするため、このチェックをさらに明示的に行っています。</span><span class="sxs-lookup"><span data-stu-id="fa145-359">But, in this example, we've made this checking more explicit to both highlight the issue and simplify the example.</span></span>

<span data-ttu-id="fa145-360">これは、`LoadFile()` 戦略と ALC 戦略の重要な相違点です。`AssemblyResolve` イベントではアプリケーション ドメイン内のすべての読み込みを処理する必要があるため、この依存関係の解決が他のモジュールによって混乱しないようにすることが非常に困難になります。</span><span class="sxs-lookup"><span data-stu-id="fa145-360">This is the key difference between the `LoadFile()` strategy and the ALC strategy: the `AssemblyResolve` event must service all loads in the Application Domain, making it much harder to keep our dependency resolution from being tangled with other modules.</span></span> <span data-ttu-id="fa145-361">ただし、.NET Framework には ALC がないため、このオプションは理解しておく価値があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-361">However, the lack of ALCs in .NET Framework makes this option worth understanding.</span></span>

### <a name="custom-application-domains"></a><span data-ttu-id="fa145-362">カスタム アプリケーション ドメイン</span><span class="sxs-lookup"><span data-stu-id="fa145-362">Custom Application Domains</span></span>

<span data-ttu-id="fa145-363">アセンブリを分離するための最後の最も極端なオプションは、カスタム アプリケーション ドメインを使用することです。</span><span class="sxs-lookup"><span data-stu-id="fa145-363">The final and most extreme option for assembly isolation is to use custom Application Domains.</span></span>
<span data-ttu-id="fa145-364">アプリケーション ドメインは、.NET Framework でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="fa145-364">Application Domains (used in the plural) are only available in .NET Framework.</span></span> <span data-ttu-id="fa145-365">これらは、.NET アプリケーションのパーツをプロセス内で分離するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="fa145-365">They are used to provide in-process isolation between parts of a .NET application.</span></span> <span data-ttu-id="fa145-366">用途の 1 つは、同じプロセス内でアセンブリの読み込みを相互に分離することです。</span><span class="sxs-lookup"><span data-stu-id="fa145-366">One of the uses is to isolate assembly loads from each other within the same process.</span></span>

<span data-ttu-id="fa145-367">ただし、アプリケーション ドメインはシリアル化の境界です。</span><span class="sxs-lookup"><span data-stu-id="fa145-367">However, Application Domains are serialization boundaries.</span></span> <span data-ttu-id="fa145-368">あるアプリケーション ドメイン内のオブジェクトを、別のアプリケーション ドメイン内のオブジェクトから直接参照および使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fa145-368">Objects in one Application Domain can't be referenced and used directly by objects in another Application Domain.</span></span> <span data-ttu-id="fa145-369">この問題を回避するには、`MarshalByRefObject` を実装します。</span><span class="sxs-lookup"><span data-stu-id="fa145-369">You can work around this by implementing `MarshalByRefObject`.</span></span> <span data-ttu-id="fa145-370">ただし、依存関係でよくあるように、自分で型を制御できない場合は、ここで実装を強制することはできません。</span><span class="sxs-lookup"><span data-stu-id="fa145-370">But when you don't control the types, as is often the case with dependencies, it's not possible to force an implementation here.</span></span> <span data-ttu-id="fa145-371">唯一の解決策は、アーキテクチャを大幅に変更することです。</span><span class="sxs-lookup"><span data-stu-id="fa145-371">The only solution is to make large architectural changes.</span></span> <span data-ttu-id="fa145-372">シリアル化の境界を使用すると、パフォーマンスにも大きな影響があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-372">The serialization boundary also has serious performance implications.</span></span>

<span data-ttu-id="fa145-373">アプリケーション ドメインにはこのような重大な制限があり、実装が複雑であり、.NET Framework でしか機能しないため、ここでは使用方法の例を示しません。</span><span class="sxs-lookup"><span data-stu-id="fa145-373">Because Application Domains have this serious limitation, are complicated to implement, and only work in .NET Framework, we won't give an example of how you might use them here.</span></span> <span data-ttu-id="fa145-374">可能性として触れておく価値はありますが、推奨されません。</span><span class="sxs-lookup"><span data-stu-id="fa145-374">While they're worth mentioning as a possibility, they're not recommended.</span></span>

<span data-ttu-id="fa145-375">カスタム アプリケーション ドメインを使用することに関心がある場合は、次のリンクが役に立つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-375">If you're interested in trying to use a custom Application Domain, the following links might help:</span></span>

- [<span data-ttu-id="fa145-376">アプリケーション ドメインの概念に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="fa145-376">Conceptual documentation on Application Domains</span></span>](/dotnet/framework/app-domains/application-domains)
- [<span data-ttu-id="fa145-377">アプリケーション ドメインの使用例</span><span class="sxs-lookup"><span data-stu-id="fa145-377">Examples for using Application Domains</span></span>](/dotnet/framework/app-domains/use)

## <a name="solutions-for-dependency-conflicts-that-dont-work-for-powershell"></a><span data-ttu-id="fa145-378">PowerShell では機能しない依存関係の競合の解決策</span><span class="sxs-lookup"><span data-stu-id="fa145-378">Solutions for dependency conflicts that don't work for PowerShell</span></span>

<span data-ttu-id="fa145-379">最後に、.NET で .NET 依存関係の競合を調べるときに有望そうに見えるいくつかの可能性について説明します。ただし、通常は PowerShell では機能しません。</span><span class="sxs-lookup"><span data-stu-id="fa145-379">Finally, we'll address some possibilities that come up when researching .NET dependency conflicts in .NET that can look promising, but generally won't work for PowerShell.</span></span>

<span data-ttu-id="fa145-380">これらの解決策には、アプリケーションとおそらくはコンピューター全体を制御できる環境での配置構成の変更という共通のテーマがあります。</span><span class="sxs-lookup"><span data-stu-id="fa145-380">These solutions have the common theme that they are changes to deployment configurations for an environment where you control the application and possibly the entire machine.</span></span> <span data-ttu-id="fa145-381">これらの解決策は、サーバー環境に配置された Web サーバーや他のアプリケーションを対象とし、環境はアプリケーションをホストするためのもので、配置を行うユーザーが自由に構成できるというシナリオのためのものです。</span><span class="sxs-lookup"><span data-stu-id="fa145-381">These solutions are oriented toward scenarios like web servers and other applications deployed to server environments, where the environment is intended to host the application and is free to be configured by the deploying user.</span></span> <span data-ttu-id="fa145-382">また、これらはかなり .NET Framework 向けである傾向があり、PowerShell 6 以降では機能しません。</span><span class="sxs-lookup"><span data-stu-id="fa145-382">They also tend to be very much .NET Framework oriented, meaning they do not work with PowerShell 6 or above.</span></span>

<span data-ttu-id="fa145-383">完全に制御できる Windows PowerShell 5.1 環境だけでモジュールを使用することがわかっている場合は、これらの一部を使用できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-383">If you know that your module is only used in Windows PowerShell 5.1 environments that you have total control over, some of these may be options.</span></span> <span data-ttu-id="fa145-384">ただし、一般に、**モジュールではこのようなグローバルなコンピューターの状態を変更しないでください**。</span><span class="sxs-lookup"><span data-stu-id="fa145-384">In general however, **modules should not modify global machine state like this**.</span></span> <span data-ttu-id="fa145-385">構成が壊れ、`powershell.exe`、他のモジュール、または他の依存アプリケーションで問題が発生し、モジュールが予期しない方法で失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-385">It can break configurations that cause problems in `powershell.exe`, other modules, or other dependent applications that cause your module to fail in unexpected ways.</span></span>

### <a name="static-binding-redirect-with-appconfig-to-force-using-the-same-dependency-version"></a><span data-ttu-id="fa145-386">静的バインド リダイレクトと app.config を使用して、同じバージョンの依存関係の使用を強制する</span><span class="sxs-lookup"><span data-stu-id="fa145-386">Static binding redirect with app.config to force using the same dependency version</span></span>

<span data-ttu-id="fa145-387">.NET Framework アプリケーションでは、`app.config` ファイルを利用して、アプリケーションの動作の一部を宣言によって構成できます。</span><span class="sxs-lookup"><span data-stu-id="fa145-387">.NET Framework applications can take advantage of an `app.config` file to configure some of the application's behaviors declaratively.</span></span> <span data-ttu-id="fa145-388">アセンブリの読み込みを特定のバージョンにリダイレクトするようにアセンブリのバインドを構成する `app.config` エントリを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="fa145-388">It's possible to write an `app.config` entry that configures assembly binding to redirect assembly loading to a particular version.</span></span>

<span data-ttu-id="fa145-389">PowerShell では、次の 2 つの問題があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-389">Two issues with this for PowerShell are:</span></span>

- <span data-ttu-id="fa145-390">.NET Core では `app.config` がサポートされていないため、この解決策は `powershell.exe` にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="fa145-390">.NET Core does not support `app.config`, so this solution only applies to `powershell.exe`.</span></span>
- <span data-ttu-id="fa145-391">`powershell.exe` は、`System32` ディレクトリに存在する共有アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="fa145-391">`powershell.exe` is a shared application that lives in the `System32` directory.</span></span> <span data-ttu-id="fa145-392">多くのシステムでは、モジュールでその内容を変更できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-392">It's likely that your module won't be able to modify its contents on many systems.</span></span> <span data-ttu-id="fa145-393">可能な場合でも、`app.config` を変更すると、既存の構成が壊れたり、他のモジュールの読み込みに影響したりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-393">Even if it can, modifying the `app.config` could break an existing configuration or affect the loading of other modules.</span></span>

### <a name="setting-codebase-with-appconfig"></a><span data-ttu-id="fa145-394">app.config での `codebase` の設定</span><span class="sxs-lookup"><span data-stu-id="fa145-394">Setting `codebase` with app.config</span></span>

<span data-ttu-id="fa145-395">同じ理由から、`app.config` で `codebase` の設定を構成しようとしても、PowerShell モジュールでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="fa145-395">For the same reasons, trying to configure the `codebase` setting in `app.config` is not going to work in PowerShell modules.</span></span>

### <a name="installing-dependencies-to-the-global-assembly-cache-gac"></a><span data-ttu-id="fa145-396">グローバル アセンブリ キャッシュ (GAC) への依存関係のインストール</span><span class="sxs-lookup"><span data-stu-id="fa145-396">Installing dependencies to the Global Assembly Cache (GAC)</span></span>

<span data-ttu-id="fa145-397">.NET Framework での依存関係のバージョンの競合を解決するもう 1 つの方法は、GAC に依存関係をインストールし、GAC から異なるバージョンを side-by-side で読み込めるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="fa145-397">Another way to resolve dependency version conflicts in .NET Framework is to install dependencies to the GAC, so that different versions can be loaded side-by-side from the GAC.</span></span>

<span data-ttu-id="fa145-398">やはり、PowerShell モジュールの場合、ここでの主な問題は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fa145-398">Again, for PowerShell modules, the chief issues here are:</span></span>

- <span data-ttu-id="fa145-399">GAC は .NET Framework にのみ適用されるため、PowerShell 6 以降では役に立ちません。</span><span class="sxs-lookup"><span data-stu-id="fa145-399">The GAC only applies to .NET Framework, so this does not help in PowerShell 6 and above.</span></span>
- <span data-ttu-id="fa145-400">GAC へのアセンブリのインストールは、コンピューターのグローバルな状態の変更であり、他のアプリケーションや他のモジュールで副作用が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-400">Installing assemblies to the GAC is a modification of global machine state and may cause side-effects in other applications or to other modules.</span></span> <span data-ttu-id="fa145-401">また、モジュールに必要なアクセス特権がある場合でも、正しく行うことは難しい可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-401">It may also be difficult to do correctly, even when your module has the required access privileges.</span></span> <span data-ttu-id="fa145-402">誤って行うと、他の .NET アプリケーションでコンピューター全体の深刻な問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-402">Getting it wrong could cause serious, machine-wide issues in other .NET applications.</span></span>

## <a name="further-reading"></a><span data-ttu-id="fa145-403">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa145-403">Further reading</span></span>

<span data-ttu-id="fa145-404">.NET アセンブリのバージョンの依存関係の競合については、多くの資料があります。</span><span class="sxs-lookup"><span data-stu-id="fa145-404">There's plenty more to read on .NET assembly version dependency conflicts.</span></span> <span data-ttu-id="fa145-405">手始めに読むのに適したものをいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="fa145-405">Here are some nice jumping off points:</span></span>

- [<span data-ttu-id="fa145-406">.NET: .NET のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="fa145-406">.NET: Assemblies in .NET</span></span>](/dotnet/standard/assembly/)
- [<span data-ttu-id="fa145-407">.NET Core: マネージド アセンブリの読み込みアルゴリズム</span><span class="sxs-lookup"><span data-stu-id="fa145-407">.NET Core: The managed assembly loading algorithm</span></span>](/dotnet/core/dependency-loading/loading-managed)
- [<span data-ttu-id="fa145-408">.NET Core: System.Runtime.Loader.AssemblyLoadContext について</span><span class="sxs-lookup"><span data-stu-id="fa145-408">.NET Core: Understanding System.Runtime.Loader.AssemblyLoadContext</span></span>](/dotnet/core/dependency-loading/understanding-assemblyloadcontext)
- [<span data-ttu-id="fa145-409">.NET Core: side-by-side アセンブリ読み込みソリューションについての説明</span><span class="sxs-lookup"><span data-stu-id="fa145-409">.NET Core: Discussion about side-by-side assembly loading solutions</span></span>](https://github.com/dotnet/runtime/issues/13471)
- [<span data-ttu-id="fa145-410">.NET Framework: アセンブリ バージョンのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="fa145-410">.NET Framework: Redirecting assembly versions</span></span>](/dotnet/framework/configure-apps/redirect-assembly-versions)
- [<span data-ttu-id="fa145-411">.NET Framework: アセンブリの読み込みのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="fa145-411">.NET Framework: Best practices for assembly loading</span></span>](/dotnet/framework/deployment/best-practices-for-assembly-loading)
- [<span data-ttu-id="fa145-412">.NET Framework: ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="fa145-412">.NET Framework: How the runtime locates assemblies</span></span>](/dotnet/framework/deployment/how-the-runtime-locates-assemblies)
- [<span data-ttu-id="fa145-413">.NET Framework: アセンブリ読み込みを解決する</span><span class="sxs-lookup"><span data-stu-id="fa145-413">.NET Framework: Resolve assembly loads</span></span>](/dotnet/standard/assembly/resolve-loads)
- [<span data-ttu-id="fa145-414">StackOverflow:アセンブリ バインドのリダイレクト、方法、理由</span><span class="sxs-lookup"><span data-stu-id="fa145-414">StackOverflow: Assembly binding redirect, how and why?</span></span>](https://stackoverflow.com/questions/43365736/assembly-binding-redirect-how-and-why)
- [<span data-ttu-id="fa145-415">PowerShell: AssemblyLoadContexts の実装に関する説明</span><span class="sxs-lookup"><span data-stu-id="fa145-415">PowerShell: Discussion about implementing AssemblyLoadContexts</span></span>](https://github.com/PowerShell/PowerShell/issues/11571)
- [<span data-ttu-id="fa145-416">PowerShell: `Assembly.LoadFile()` で既定の AssemblyLoadContext に読み込まれない</span><span class="sxs-lookup"><span data-stu-id="fa145-416">PowerShell: `Assembly.LoadFile()` doesn't load into default AssemblyLoadContext</span></span>](https://github.com/PowerShell/PowerShell/issues/12052)
- [<span data-ttu-id="fa145-417">Rick Strahl: .NET アセンブリの依存関係はいつ読み込まれるか</span><span class="sxs-lookup"><span data-stu-id="fa145-417">Rick Strahl: When does a .NET assembly dependency get loaded?</span></span>](https://weblog.west-wind.com/posts/2012/Nov/03/Back-to-Basics-When-does-a-NET-Assembly-Dependency-get-loaded)
- [<span data-ttu-id="fa145-418">Jon Skeet: .NET でのバージョン管理の概要</span><span class="sxs-lookup"><span data-stu-id="fa145-418">Jon Skeet: Summary of versioning in .NET</span></span>](https://codeblog.jonskeet.uk/2019/06/30/versioning-limitations-in-net/)
- [<span data-ttu-id="fa145-419">Nate McMaster: .NET Core プリミティブの詳細</span><span class="sxs-lookup"><span data-stu-id="fa145-419">Nate McMaster: Deep dive into .NET Core primitives</span></span>](https://natemcmaster.com/blog/2017/12/21/netcore-primitives/)
