---
ms.date: 12/14/2018
keywords: PowerShell, コマンドレット
title: 移植可能なモジュールの作成
ms.openlocfilehash: 38a93b5b030d58784b91292e2cd060b3a2c19a00
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "55682551"
---
# <a name="portable-modules"></a><span data-ttu-id="546f9-103">移植可能なモジュール</span><span class="sxs-lookup"><span data-stu-id="546f9-103">Portable Modules</span></span>

<span data-ttu-id="546f9-104">Windows PowerShell が用に記述された[.NET Framework][]用の PowerShell Core の書き込み中に[.NET Core][]します。</span><span class="sxs-lookup"><span data-stu-id="546f9-104">Windows PowerShell is written for [.NET Framework][] while PowerShell Core is written for [.NET Core][].</span></span> <span data-ttu-id="546f9-105">移植可能なモジュールとは、Windows PowerShell と PowerShell Core の両方で動作するモジュールです。</span><span class="sxs-lookup"><span data-stu-id="546f9-105">Portable modules are modules that work in both Windows PowerShell and PowerShell Core.</span></span> <span data-ttu-id="546f9-106">.NET Framework と .NET Core は互換性が高いが、2 つの利用可能な Api の違いがあります。</span><span class="sxs-lookup"><span data-stu-id="546f9-106">While .NET Framework and .NET Core are highly compatible, there are differences in the available APIs between the two.</span></span> <span data-ttu-id="546f9-107">違いが、Api で Windows PowerShell と PowerShell Core で使用できます。</span><span class="sxs-lookup"><span data-stu-id="546f9-107">There are also differences in the APIs available in Windows PowerShell and PowerShell Core.</span></span> <span data-ttu-id="546f9-108">モジュールの両方の環境で使用するものでは、これらの違いを意識する必要があります。</span><span class="sxs-lookup"><span data-stu-id="546f9-108">Modules intended to be used in both environments need to be aware of these differences.</span></span>

## <a name="porting-an-existing-module"></a><span data-ttu-id="546f9-109">既存のモジュールの移植</span><span class="sxs-lookup"><span data-stu-id="546f9-109">Porting an Existing Module</span></span>

### <a name="porting-a-pssnapin"></a><span data-ttu-id="546f9-110">PSSnapIn の移植</span><span class="sxs-lookup"><span data-stu-id="546f9-110">Porting a PSSnapIn</span></span>

<span data-ttu-id="546f9-111">PowerShell スナップイン (PSSnapIn) は、PowerShell Core でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="546f9-111">PowerShell SnapIns (PSSnapIn) aren't supported in PowerShell Core.</span></span> <span data-ttu-id="546f9-112">ただし、PSSnapIn を PowerShell モジュールに変換する単純なは。</span><span class="sxs-lookup"><span data-stu-id="546f9-112">However, it's trivial to convert a PSSnapIn to a PowerShell module.</span></span> <span data-ttu-id="546f9-113">派生したクラスの 1 つのソース ファイルで PSSnapIn 登録コードは、通常、 [PSSnapIn][]します。</span><span class="sxs-lookup"><span data-stu-id="546f9-113">Typically, the PSSnapIn registration code is in a single source file of a class that derives from [PSSnapIn][].</span></span> <span data-ttu-id="546f9-114">このソース ファイル、ビルドから削除します。これが不要になった。</span><span class="sxs-lookup"><span data-stu-id="546f9-114">Remove this source file from the build; it's no longer needed.</span></span>

<span data-ttu-id="546f9-115">使用[New-modulemanifest][] PSSnapIn 登録コードの必要性を置換する新しいモジュール マニフェストを作成します。</span><span class="sxs-lookup"><span data-stu-id="546f9-115">Use [New-ModuleManifest][] to create a new module manifest that replaces the need for the PSSnapIn registration code.</span></span> <span data-ttu-id="546f9-116">(説明) などの PSSnapIn から値の一部は、モジュール マニフェスト内で再利用できます。</span><span class="sxs-lookup"><span data-stu-id="546f9-116">Some of the values from the PSSnapIn (such as Description) can be reused within the module manifest.</span></span>

<span data-ttu-id="546f9-117">`RootModule`コマンドレットを実装するアセンブリ (dll) の名前に、モジュール マニフェスト内のプロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="546f9-117">The `RootModule` property in the module manifest should be set to the name of the assembly (dll) implementing the cmdlets.</span></span>

### <a name="the-net-portability-analyzer-aka-apiport"></a><span data-ttu-id="546f9-118">.NET Portability Analyzer (APIPort とも呼ばれます)</span><span class="sxs-lookup"><span data-stu-id="546f9-118">The .NET Portability Analyzer (aka APIPort)</span></span>

<span data-ttu-id="546f9-119">PowerShell Core で動作、開始して Windows PowerShell 用に記述されたモジュールをポートに、 [.NET Portability Analyzer][]します。</span><span class="sxs-lookup"><span data-stu-id="546f9-119">To port modules written for Windows PowerShell to work with PowerShell Core, start with the [.NET Portability Analyzer][].</span></span> <span data-ttu-id="546f9-120">モジュールで使用される .NET Api が .NET Framework、.NET Core、およびその他の .NET ランタイムと互換性があるかを判断するコンパイル済みのアセンブリに対してこのツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="546f9-120">Run this tool against your compiled assembly to determine if the .NET APIs used in the module are compatible with .NET Framework, .NET Core, and other .NET runtimes.</span></span> <span data-ttu-id="546f9-121">このツールは、存在する場合の代替 Api をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="546f9-121">The tool suggests alternate APIs if they exist.</span></span> <span data-ttu-id="546f9-122">追加する必要がありますそれ以外の場合、[ランタイム チェック][]し、特定のランタイムで使用できない機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="546f9-122">Otherwise, you may need to add [runtime checks][] and restrict capabilities not available in specific runtimes.</span></span>

## <a name="creating-a-new-module"></a><span data-ttu-id="546f9-123">新しいモジュールの作成</span><span class="sxs-lookup"><span data-stu-id="546f9-123">Creating a New Module</span></span>

<span data-ttu-id="546f9-124">使用する推奨事項は、新しいモジュールを作成する場合、 [.NET CLI][]します。</span><span class="sxs-lookup"><span data-stu-id="546f9-124">If creating a new module, the recommendation is to use the [.NET CLI][].</span></span>

### <a name="installing-the-powershell-standard-module-template"></a><span data-ttu-id="546f9-125">標準の PowerShell モジュールのテンプレートをインストールします。</span><span class="sxs-lookup"><span data-stu-id="546f9-125">Installing the PowerShell Standard Module Template</span></span>

<span data-ttu-id="546f9-126">.NET CLI がインストールされると、単純な PowerShell モジュールを生成するテンプレート ライブラリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="546f9-126">Once the .NET CLI is installed, install a template library to generate a simple PowerShell module.</span></span>
<span data-ttu-id="546f9-127">モジュールは、Windows PowerShell、PowerShell Core、Windows、Linux、および macOS の操作に互換性があります。</span><span class="sxs-lookup"><span data-stu-id="546f9-127">The module will be compatible with Windows PowerShell, PowerShell Core, Windows, Linux, and macOS.</span></span>

<span data-ttu-id="546f9-128">次の例では、テンプレートをインストールする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="546f9-128">The following example shows how to install the template:</span></span>

```powershell
dotnet new -i Microsoft.PowerShell.Standard.Module.Template
```

```output
  Restoring packages for C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\restore.csproj...
  Installing Microsoft.PowerShell.Standard.Module.Template 0.1.3.
  Generating MSBuild file C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\obj\restore.csproj.nuget.g.props.
  Generating MSBuild file C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\obj\restore.csproj.nuget.g.targets.
  Restore completed in 1.66 sec for C:\Users\Steve\.templateengine\dotnetcli\v2.1.302\scratch\restore.csproj.

Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.
  -n, --name          The name for the output being created. If no name is specified, the name of the current directory is used.
  -o, --output        Location to place the generated output.
  -i, --install       Installs a source or a template pack.
  -u, --uninstall     Uninstalls a source or a template pack.
  --nuget-source      Specifies a NuGet source to use during install.
  --type              Filters templates based on available types. Predefined values are "project", "item" or "other".
  --force             Forces content to be generated even if it would change existing files.
  -lang, --language   Filters templates based on language and specifies the language of the template to create.


Templates                                         Short Name         Language          Tags
----------------------------------------------------------------------------------------------------------------------------
Console Application                               console            [C#], F#, VB      Common/Console
Class library                                     classlib           [C#], F#, VB      Common/Library
PowerShell Standard Module                        psmodule           [C#]              Library/PowerShell/Module
...
```

### <a name="creating-a-new-module-project"></a><span data-ttu-id="546f9-129">新しいモジュール プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="546f9-129">Creating a New Module Project</span></span>

<span data-ttu-id="546f9-130">テンプレートをインストールした後は、そのテンプレートを使用して、新しい PowerShell モジュール プロジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="546f9-130">After the template is installed, you can create a new PowerShell module project using that template.</span></span> <span data-ttu-id="546f9-131">この例では、サンプル モジュールが 'myModule' と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="546f9-131">In this example, the sample module is called 'myModule'.</span></span>

```
PS> mkdir myModule

    Directory: C:\Users\Steve

Mode LastWriteTime Length Name
---- ------------- ------ ----
d----- 8/3/2018 2:41 PM myModule

PS> cd myModule
PS C:\Users\Steve\myModule> dotnet new psmodule

The template "PowerShell Standard Module" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on C:\Users\Steve\myModule\myModule.csproj...
  Restoring packages for C:\Users\Steve\myModule\myModule.csproj...
  Installing PowerShellStandard.Library 5.1.0.
  Generating MSBuild file C:\Users\Steve\myModule\obj\myModule.csproj.nuget.g.props.
  Generating MSBuild file C:\Users\Steve\myModule\obj\myModule.csproj.nuget.g.targets.
  Restore completed in 1.76 sec for C:\Users\Steve\myModule\myModule.csproj.

Restore succeeded.
```

### <a name="building-the-module"></a><span data-ttu-id="546f9-132">モジュールの構築</span><span class="sxs-lookup"><span data-stu-id="546f9-132">Building the Module</span></span>

<span data-ttu-id="546f9-133">プロジェクトをビルドするのにには、標準の .NET CLI コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="546f9-133">Use standard .NET CLI commands to build the project.</span></span>

```powershell
dotnet build
```

```output
PS C:\Users\Steve\myModule> dotnet build
Microsoft (R) Build Engine version 15.7.179.6572 for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 76.85 ms for C:\Users\Steve\myModule\myModule.csproj.
  myModule -> C:\Users\Steve\myModule\bin\Debug\netstandard2.0\myModule.dll

Build succeeded.
    0 Warning(s)
    0 Error(s)

Time Elapsed 00:00:05.40
```

### <a name="testing-the-module"></a><span data-ttu-id="546f9-134">モジュールのテスト</span><span class="sxs-lookup"><span data-stu-id="546f9-134">Testing the Module</span></span>

<span data-ttu-id="546f9-135">モジュールをビルドした後は、インポートし、サンプルのコマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="546f9-135">After building the module, you can import it and execute the sample cmdlet.</span></span>

```powershell
ipmo .\bin\Debug\netstandard2.0\myModule.dll
Test-SampleCmdlet -?
Test-SampleCmdlet -FavoriteNumber 7 -FavoritePet Cat
```

```output
PS C:\Users\Steve\myModule> ipmo .\bin\Debug\netstandard2.0\myModule.dll
PS C:\Users\Steve\myModule> Test-SampleCmdlet -?

NAME
    Test-SampleCmdlet

SYNTAX
    Test-SampleCmdlet [-FavoriteNumber] <int> [[-FavoritePet] {Cat | Dog | Horse}] [<CommonParameters>]


ALIASES
    None


REMARKS
    None


PS C:\Users\Steve\myModule> Test-SampleCmdlet -FavoriteNumber 7 -FavoritePet Cat

FavoriteNumber FavoritePet
-------------- -----------
             7 Cat
```

<span data-ttu-id="546f9-136">次のセクションについて詳しく説明このテンプレートで使用されるテクノロジの一部です。</span><span class="sxs-lookup"><span data-stu-id="546f9-136">The following sections describe in detail some of the technologies used by this template.</span></span>

## <a name="net-standard-library"></a><span data-ttu-id="546f9-137">.NET 標準ライブラリ</span><span class="sxs-lookup"><span data-stu-id="546f9-137">.NET Standard Library</span></span>

<span data-ttu-id="546f9-138">[.NET standard][]はすべての .NET 実装で使用できる .NET Api の正式な仕様です。</span><span class="sxs-lookup"><span data-stu-id="546f9-138">[.NET Standard][] is a formal specification of .NET APIs that are available in all .NET implementations.</span></span> <span data-ttu-id="546f9-139">.NET Standard のバージョンと互換性のある .NET Framework と .NET Core のバージョンで動作を .NET Standard をターゲットとするコードを管理します。</span><span class="sxs-lookup"><span data-stu-id="546f9-139">Managed code targeting .NET Standard works with the .NET Framework and .NET Core versions that are compatible with that version of the .NET Standard.</span></span>

> [!NOTE]
> <span data-ttu-id="546f9-140">.NET Core での API の実装が .NET standard API が存在する可能性があります、スローする可能性が、 `PlatformNotSupportedException` 、実行時にように Windows PowerShell および PowerShell Core との互換性を確認するベスト プラクティスは、モジュール内での両方の環境のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="546f9-140">Although an API may exist in .NET Standard, the API implementation in .NET Core may throw a `PlatformNotSupportedException` at runtime, so to verify compatibility with Windows PowerShell and PowerShell Core, the best practice is to run tests for your module within both environments.</span></span>
> <span data-ttu-id="546f9-141">クロスプラット フォーム対応にするものでは、モジュールの場合は、Linux と macOS でテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="546f9-141">Also run tests on Linux and macOS if your module is intended to be cross-platform.</span></span>

<span data-ttu-id="546f9-142">.NET Standard をターゲットとにより、モジュールの進化に伴って、互換性のない Api しない誤って取得に導入されたモジュール。</span><span class="sxs-lookup"><span data-stu-id="546f9-142">Targeting .NET Standard helps ensure that, as the module evolves, incompatible APIs don't accidentally get introduced into the module.</span></span> <span data-ttu-id="546f9-143">非互換性は、ランタイムではなくコンパイル時に検出されます。</span><span class="sxs-lookup"><span data-stu-id="546f9-143">Incompatibilities are discovered at compile time instead of runtime.</span></span>

<span data-ttu-id="546f9-144">ただし、必須ではなく .NET 標準モジュールの Windows PowerShell と PowerShell Core の両方を使用するターゲットに互換性のある Api を使用する限り。</span><span class="sxs-lookup"><span data-stu-id="546f9-144">However, it isn't required to target .NET Standard for a module to work with both Windows PowerShell and PowerShell Core, as long as you use compatible APIs.</span></span> <span data-ttu-id="546f9-145">中間言語 (IL) は、2 つのランタイムとの間に互換性があります。</span><span class="sxs-lookup"><span data-stu-id="546f9-145">The Intermediate Language (IL) is compatible between the two runtimes.</span></span> <span data-ttu-id="546f9-146">.NET Framework 4.6.1 を対象 .NET Standard 2.0 と互換性があることができます。</span><span class="sxs-lookup"><span data-stu-id="546f9-146">You can target .NET Framework 4.6.1, which is compatible with .NET Standard 2.0.</span></span> <span data-ttu-id="546f9-147">.NET Standard 2.0 以外の Api を使用しないし、モジュールは、再コンパイルせずに PowerShell Core 6 では機能します。</span><span class="sxs-lookup"><span data-stu-id="546f9-147">If you don't use APIs outside of .NET Standard 2.0, then your module works with PowerShell Core 6 without recompilation.</span></span>

## <a name="powershell-standard-library"></a><span data-ttu-id="546f9-148">PowerShell の標準ライブラリ</span><span class="sxs-lookup"><span data-stu-id="546f9-148">PowerShell Standard Library</span></span>

<span data-ttu-id="546f9-149">[PowerShell の標準][]ライブラリは、その標準のバージョン以上のすべての PowerShell バージョンで利用可能な PowerShell Api の正式な仕様。</span><span class="sxs-lookup"><span data-stu-id="546f9-149">The [PowerShell Standard][] library is a formal specification of PowerShell APIs available in all PowerShell versions greater than or equal to the version of that standard.</span></span>

<span data-ttu-id="546f9-150">たとえば、[PowerShell の標準 5.1][]は、Windows PowerShell 5.1 と PowerShell Core 6.0 の両方と互換性のある以降です。</span><span class="sxs-lookup"><span data-stu-id="546f9-150">For example, [PowerShell Standard 5.1][] is compatible with both Windows PowerShell 5.1 and PowerShell Core 6.0 or newer.</span></span>

<span data-ttu-id="546f9-151">PowerShell の標準ライブラリを使用して、モジュールをコンパイルすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="546f9-151">We recommend you compile your module using PowerShell Standard Library.</span></span> <span data-ttu-id="546f9-152">ライブラリにより、Api が使用可能で Windows PowerShell と PowerShell Core 6 の両方に実装されているようになります。</span><span class="sxs-lookup"><span data-stu-id="546f9-152">The library ensures the APIs are available and implemented in both Windows PowerShell and PowerShell Core 6.</span></span>
<span data-ttu-id="546f9-153">PowerShell の標準は、常に上位互換になります。</span><span class="sxs-lookup"><span data-stu-id="546f9-153">PowerShell Standard is intended to always be forwards-compatible.</span></span> <span data-ttu-id="546f9-154">標準ライブラリ 5.1 の PowerShell を使用して構築されたモジュールは、PowerShell の将来のバージョンと互換性のある常になります。</span><span class="sxs-lookup"><span data-stu-id="546f9-154">A module built using PowerShell Standard Library 5.1 will always be compatible with future versions of PowerShell.</span></span>

## <a name="module-manifest"></a><span data-ttu-id="546f9-155">モジュール マニフェスト</span><span class="sxs-lookup"><span data-stu-id="546f9-155">Module Manifest</span></span>

### <a name="indicating-compatibility-with-windows-powershell-and-powershell-core"></a><span data-ttu-id="546f9-156">Windows PowerShell および PowerShell Core との互換性を示す</span><span class="sxs-lookup"><span data-stu-id="546f9-156">Indicating Compatibility With Windows PowerShell and PowerShell Core</span></span>

<span data-ttu-id="546f9-157">モジュールが Windows PowerShell と PowerShell Core の両方で動作するかを検証した後、モジュール マニフェストが明示的に示す互換性を使用して、 [CompatiblePSEditions][]プロパティ。</span><span class="sxs-lookup"><span data-stu-id="546f9-157">After validating that your module works with both Windows PowerShell and PowerShell Core, the module manifest should explicitly indicate compatibility by using the [CompatiblePSEditions][] property.</span></span> <span data-ttu-id="546f9-158">値`Desktop`モジュールが Windows PowerShell では、値の中に互換性があることを意味`Core`モジュールが PowerShell Core と互換性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="546f9-158">A value of `Desktop` means that the module is compatible with Windows PowerShell, while a value of `Core` means that the module is compatible with PowerShell Core.</span></span> <span data-ttu-id="546f9-159">両方を含む`Desktop`と`Core`モジュールが Windows PowerShell と PowerShell Core の両方と互換性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="546f9-159">Including both `Desktop` and `Core` means that the module is compatible with both Windows PowerShell and PowerShell Core.</span></span>

> [!NOTE]
> <span data-ttu-id="546f9-160">`Core` わけではありません、モジュールが、Windows、Linux、および macOS と互換性があります。</span><span class="sxs-lookup"><span data-stu-id="546f9-160">`Core` does not automatically mean that the module is compatible with Windows, Linux, and macOS.</span></span>
> <span data-ttu-id="546f9-161">**CompatiblePSEditions**プロパティは PowerShell v5 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="546f9-161">The **CompatiblePSEditions** property was introduced in PowerShell v5.</span></span> <span data-ttu-id="546f9-162">モジュール マニフェストを使用して、 **CompatiblePSEditions**プロパティは、PowerShell v5 以前のバージョンでの読み込みに失敗します。</span><span class="sxs-lookup"><span data-stu-id="546f9-162">Module manifests that use the **CompatiblePSEditions** property fail to load in versions prior to PowerShell v5.</span></span>

### <a name="indicating-os-compatibility"></a><span data-ttu-id="546f9-163">OS の互換性を示す</span><span class="sxs-lookup"><span data-stu-id="546f9-163">Indicating OS Compatibility</span></span>

<span data-ttu-id="546f9-164">最初に、Linux と macOS で、モジュールが動作する検証します。</span><span class="sxs-lookup"><span data-stu-id="546f9-164">First, validate that your module works on Linux and macOS.</span></span> <span data-ttu-id="546f9-165">次に、モジュール マニフェストでこれらのオペレーティング システムとの互換性を示します。</span><span class="sxs-lookup"><span data-stu-id="546f9-165">Next, indicate compatibility with those operating systems in the module manifest.</span></span> <span data-ttu-id="546f9-166">これにより、ユーザーに発行されると、オペレーティング システムのモジュールを見つけやすく、 [PowerShell ギャラリー][]します。</span><span class="sxs-lookup"><span data-stu-id="546f9-166">This makes it easier for users to find your module for their operating system when published to the [PowerShell Gallery][].</span></span>

<span data-ttu-id="546f9-167">モジュール マニフェスト内で、`PrivateData`プロパティは、`PSData`サブプロパティ。</span><span class="sxs-lookup"><span data-stu-id="546f9-167">Within the module manifest, the `PrivateData` property has a `PSData` sub-property.</span></span> <span data-ttu-id="546f9-168">省略可能な`Tags`プロパティの`PSData`は PowerShell ギャラリーに表示される値の配列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="546f9-168">The optional `Tags` property of `PSData` takes an array of values that show up in PowerShell Gallery.</span></span> <span data-ttu-id="546f9-169">PowerShell ギャラリーには、次の互換性の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="546f9-169">The PowerShell Gallery supports the following compatibility values:</span></span>

| <span data-ttu-id="546f9-170">タグ</span><span class="sxs-lookup"><span data-stu-id="546f9-170">Tag</span></span>               | <span data-ttu-id="546f9-171">説明</span><span class="sxs-lookup"><span data-stu-id="546f9-171">Description</span></span>                                |
|-------------------|--------------------------------------------|
| <span data-ttu-id="546f9-172">PSEdition_Core</span><span class="sxs-lookup"><span data-stu-id="546f9-172">PSEdition_Core</span></span>    | <span data-ttu-id="546f9-173">PowerShell Core 6 と互換性があります。</span><span class="sxs-lookup"><span data-stu-id="546f9-173">Compatible with PowerShell Core 6</span></span>          |
| <span data-ttu-id="546f9-174">PSEdition_Desktop</span><span class="sxs-lookup"><span data-stu-id="546f9-174">PSEdition_Desktop</span></span> | <span data-ttu-id="546f9-175">Windows PowerShell との互換性</span><span class="sxs-lookup"><span data-stu-id="546f9-175">Compatible with Windows PowerShell</span></span>         |
| <span data-ttu-id="546f9-176">Windows</span><span class="sxs-lookup"><span data-stu-id="546f9-176">Windows</span></span>           | <span data-ttu-id="546f9-177">Windows と互換性があります。</span><span class="sxs-lookup"><span data-stu-id="546f9-177">Compatible with Windows</span></span>                    |
| <span data-ttu-id="546f9-178">Linux</span><span class="sxs-lookup"><span data-stu-id="546f9-178">Linux</span></span>             | <span data-ttu-id="546f9-179">Linux (特定のディストリビューションがありません) との互換性</span><span class="sxs-lookup"><span data-stu-id="546f9-179">Compatible with Linux (no specific distro)</span></span> |
| <span data-ttu-id="546f9-180">macOS</span><span class="sxs-lookup"><span data-stu-id="546f9-180">macOS</span></span>             | <span data-ttu-id="546f9-181">MacOS と互換性があります。</span><span class="sxs-lookup"><span data-stu-id="546f9-181">Compatible with macOS</span></span>                      |

<span data-ttu-id="546f9-182">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="546f9-182">Example:</span></span>

```powershell
@{
    GUID = "4ae9fd46-338a-459c-8186-07f910774cb8"
    Author = "Microsoft Corporation"
    CompanyName = "Microsoft Corporation"
    Copyright = "(C) Microsoft Corporation. All rights reserved."
    HelpInfoUri = "https://go.microsoft.com/fwlink/?linkid=855962"
    ModuleVersion = "1.2.4"
    PowerShellVersion = "3.0"
    ClrVersion = "4.0"
    RootModule = "PackageManagement.psm1"
    Description = 'PackageManagement (a.k.a. OneGet) is a new way to discover and install software packages from around the web.
 It is a manager or multiplexer of existing package managers (also called package providers) that unifies Windows package management with a single Windows PowerShell interface. With PackageManagement, you can do the following.
  - Manage a list of software repositories in which packages can be searched, acquired and installed
  - Discover software packages
  - Seamlessly install, uninstall, and inventory packages from one or more software repositories'

    CmdletsToExport = @(
        'Find-Package',
        'Get-Package',
        'Get-PackageProvider',
        'Get-PackageSource',
        'Install-Package',
        'Import-PackageProvider'
        'Find-PackageProvider'
        'Install-PackageProvider'
        'Register-PackageSource',
        'Set-PackageSource',
        'Unregister-PackageSource',
        'Uninstall-Package'
        'Save-Package'
    )

    FormatsToProcess  = @('PackageManagement.format.ps1xml')

    PrivateData = @{
        PSData = @{
            Tags = @('PackageManagement', 'PSEdition_Core', 'PSEdition_Desktop', 'Windows', 'Linux', 'macOS')
            ProjectUri = 'https://oneget.org'
        }
    }
}
```

<!-- reference links -->
[.NET Framework]: /dotnet/framework/
[.NET Core]: /dotnet/core/
[PSSnapIn]: /dotnet/api/system.management.automation.pssnapin
[New-ModuleManifest]: /powershell/module/microsoft.powershell.core/new-modulemanifest
[ランタイム チェック]: /dotnet/api/system.runtime.interopservices.runtimeinformation.frameworkdescription#System_Runtime_InteropServices_RuntimeInformation_FrameworkDescription
[runtime checks]: /dotnet/api/system.runtime.interopservices.runtimeinformation.frameworkdescription#System_Runtime_InteropServices_RuntimeInformation_FrameworkDescription
[.NET CLI]: /dotnet/core/tools/?tabs=netcore2x
[.NET Standard]: /dotnet/standard/net-standard
[PowerShell の標準]: https://github.com/PowerShell/PowerShellStandard
[PowerShell Standard]: https://github.com/PowerShell/PowerShellStandard
[PowerShell の標準 5.1]: https://www.nuget.org/packages/PowerShellStandard.Library/5.1.0
[PowerShell Standard 5.1]: https://www.nuget.org/packages/PowerShellStandard.Library/5.1.0
[PowerShell ギャラリー]: https://www.powershellgallery.com
[PowerShell Gallery]: https://www.powershellgallery.com
[.NET portability Analyzer]: https://github.com/Microsoft/dotnet-apiport
[.NET Portability Analyzer]: https://github.com/Microsoft/dotnet-apiport
[CompatiblePSEditions]: /powershell/gallery/concepts/module-psedition-support
