---
ms.date: 01/10/2020
keywords: powershell,コマンドレット
title: 移植可能なモジュールの作成
ms.openlocfilehash: a6b2f8b263e71b6c9dbd50900536cb5072597e71
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "86158124"
---
# <a name="portable-modules"></a><span data-ttu-id="d68e0-103">移植可能なモジュール</span><span class="sxs-lookup"><span data-stu-id="d68e0-103">Portable Modules</span></span>

<span data-ttu-id="d68e0-104">Windows PowerShell が [.NET Framework][] 用であるのに対し、PowerShell Core は [.NET Core][] 用に作成されています。</span><span class="sxs-lookup"><span data-stu-id="d68e0-104">Windows PowerShell is written for [.NET Framework][] while PowerShell Core is written for [.NET Core][].</span></span> <span data-ttu-id="d68e0-105">移植可能なモジュールとは、Windows PowerShell と PowerShell Core の両方で動作するモジュールです。</span><span class="sxs-lookup"><span data-stu-id="d68e0-105">Portable modules are modules that work in both Windows PowerShell and PowerShell Core.</span></span> <span data-ttu-id="d68e0-106">.NET Framework と .NET Core の間には高い互換性がありますが、使用可能な API には違いがあります。</span><span class="sxs-lookup"><span data-stu-id="d68e0-106">While .NET Framework and .NET Core are highly compatible, there are differences in the available APIs between the two.</span></span> <span data-ttu-id="d68e0-107">また、Windows PowerShell と PowerShell Core でも使用できる API が異なります。</span><span class="sxs-lookup"><span data-stu-id="d68e0-107">There are also differences in the APIs available in Windows PowerShell and PowerShell Core.</span></span> <span data-ttu-id="d68e0-108">両方の環境で使用するモジュールを作成するときは、これらの違いを意識する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d68e0-108">Modules intended to be used in both environments need to be aware of these differences.</span></span>

## <a name="porting-an-existing-module"></a><span data-ttu-id="d68e0-109">既存のモジュールの移植</span><span class="sxs-lookup"><span data-stu-id="d68e0-109">Porting an Existing Module</span></span>

### <a name="porting-a-pssnapin"></a><span data-ttu-id="d68e0-110">PSSnapIn の移植</span><span class="sxs-lookup"><span data-stu-id="d68e0-110">Porting a PSSnapIn</span></span>

<span data-ttu-id="d68e0-111">PowerShell [スナップイン](/powershell/scripting/developer/cmdlet/modules-and-snap-ins)は、PowerShell Core ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d68e0-111">PowerShell [SnapIns](/powershell/scripting/developer/cmdlet/modules-and-snap-ins) aren't supported in PowerShell Core.</span></span> <span data-ttu-id="d68e0-112">ただし、PSSnapIn を PowerShell モジュールに変換するのは簡単です。</span><span class="sxs-lookup"><span data-stu-id="d68e0-112">However, it's trivial to convert a PSSnapIn to a PowerShell module.</span></span> <span data-ttu-id="d68e0-113">通常、PSSnapIn の登録コードは、[PSSnapIn][] の派生クラスの単一のソース ファイルに含まれます。</span><span class="sxs-lookup"><span data-stu-id="d68e0-113">Typically, the PSSnapIn registration code is in a single source file of a class that derives from [PSSnapIn][].</span></span>
<span data-ttu-id="d68e0-114">このソース ファイルは、必要ありませんので、ビルドから削除します。</span><span class="sxs-lookup"><span data-stu-id="d68e0-114">Remove this source file from the build; it's no longer needed.</span></span>

<span data-ttu-id="d68e0-115">[New-ModuleManifest][] を使って、PSSnapIn 登録コードに必要なものを置き換える新しいモジュール マニフェストを作成します。</span><span class="sxs-lookup"><span data-stu-id="d68e0-115">Use [New-ModuleManifest][] to create a new module manifest that replaces the need for the PSSnapIn registration code.</span></span> <span data-ttu-id="d68e0-116">**PSSnapIn** の値の一部 (**Description** など) は、モジュール マニフェスト内で再利用できます。</span><span class="sxs-lookup"><span data-stu-id="d68e0-116">Some of the values from the **PSSnapIn** (such as **Description**) can be reused within the module manifest.</span></span>

<span data-ttu-id="d68e0-117">モジュール マニフェストの **RootModule** プロパティは、コマンドレットを実装するアセンブリ (dll) の名前に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d68e0-117">The **RootModule** property in the module manifest should be set to the name of the assembly (dll) implementing the cmdlets.</span></span>

### <a name="the-net-portability-analyzer-aka-apiport"></a><span data-ttu-id="d68e0-118">.NET Portability Analyzer (別名 APIPort)</span><span class="sxs-lookup"><span data-stu-id="d68e0-118">The .NET Portability Analyzer (aka APIPort)</span></span>

<span data-ttu-id="d68e0-119">Windows PowerShell 用に記述されたモジュールを PowerShell Core で動作するように移植するには、最初に [.NET Portability Analyzer][] を使用します。</span><span class="sxs-lookup"><span data-stu-id="d68e0-119">To port modules written for Windows PowerShell to work with PowerShell Core, start with the [.NET Portability Analyzer][].</span></span> <span data-ttu-id="d68e0-120">コンパイル済みアセンブリに対してこのツールを実行し、モジュールで使われている .NET API が .NET Framework、.NET Core、および他の .NET ランタイムと互換性があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="d68e0-120">Run this tool against your compiled assembly to determine if the .NET APIs used in the module are compatible with .NET Framework, .NET Core, and other .NET runtimes.</span></span> <span data-ttu-id="d68e0-121">このツールでは、代替 API がある場合は指摘されます。</span><span class="sxs-lookup"><span data-stu-id="d68e0-121">The tool suggests alternate APIs if they exist.</span></span> <span data-ttu-id="d68e0-122">それ以外の場合は、[ランタイム チェック][]を追加し、特定のランタイムで使用できない機能を制限することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d68e0-122">Otherwise, you may need to add [runtime checks][] and restrict capabilities not available in specific runtimes.</span></span>

## <a name="creating-a-new-module"></a><span data-ttu-id="d68e0-123">新しいモジュールの作成</span><span class="sxs-lookup"><span data-stu-id="d68e0-123">Creating a New Module</span></span>

<span data-ttu-id="d68e0-124">新しいモジュールを作成する場合に推奨されるのは、[.NET CLI][] の使用です。</span><span class="sxs-lookup"><span data-stu-id="d68e0-124">If creating a new module, the recommendation is to use the [.NET CLI][].</span></span>

### <a name="installing-the-powershell-standard-module-template"></a><span data-ttu-id="d68e0-125">PowerShell 標準モジュール テンプレートのインストール</span><span class="sxs-lookup"><span data-stu-id="d68e0-125">Installing the PowerShell Standard Module Template</span></span>

<span data-ttu-id="d68e0-126">.NET CLI をインストールした後、簡単な PowerShell モジュールを生成するためのテンプレート ライブラリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d68e0-126">Once the .NET CLI is installed, install a template library to generate a simple PowerShell module.</span></span>
<span data-ttu-id="d68e0-127">そのモジュールは、Windows PowerShell、PowerShell Core、Windows、Linux、および macOS と互換性を持つようになります。</span><span class="sxs-lookup"><span data-stu-id="d68e0-127">The module will be compatible with Windows PowerShell, PowerShell Core, Windows, Linux, and macOS.</span></span>

<span data-ttu-id="d68e0-128">次の例では、テンプレートのインストール方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d68e0-128">The following example shows how to install the template:</span></span>

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

### <a name="creating-a-new-module-project"></a><span data-ttu-id="d68e0-129">新しいモジュール プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="d68e0-129">Creating a New Module Project</span></span>

<span data-ttu-id="d68e0-130">テンプレートをインストールした後は、そのテンプレートを使用して新しい PowerShell モジュール プロジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d68e0-130">After the template is installed, you can create a new PowerShell module project using that template.</span></span> <span data-ttu-id="d68e0-131">この例のサンプル モジュールの名前は "myModule" です。</span><span class="sxs-lookup"><span data-stu-id="d68e0-131">In this example, the sample module is called 'myModule'.</span></span>

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

### <a name="building-the-module"></a><span data-ttu-id="d68e0-132">モジュールのビルド</span><span class="sxs-lookup"><span data-stu-id="d68e0-132">Building the Module</span></span>

<span data-ttu-id="d68e0-133">標準の .NET CLI コマンドを使用して、プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="d68e0-133">Use standard .NET CLI commands to build the project.</span></span>

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

### <a name="testing-the-module"></a><span data-ttu-id="d68e0-134">モジュールのテスト</span><span class="sxs-lookup"><span data-stu-id="d68e0-134">Testing the Module</span></span>

<span data-ttu-id="d68e0-135">モジュールをビルドした後は、それをインポートしてサンプルのコマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d68e0-135">After building the module, you can import it and execute the sample cmdlet.</span></span>

```powershell
Import-Module .\bin\Debug\netstandard2.0\myModule.dll
Test-SampleCmdlet -?
Test-SampleCmdlet -FavoriteNumber 7 -FavoritePet Cat
```

```output
NAME
    Test-SampleCmdlet

SYNTAX
    Test-SampleCmdlet [-FavoriteNumber] <int> [[-FavoritePet] {Cat | Dog | Horse}] [<CommonParameters>]


ALIASES
    None


REMARKS
    None


FavoriteNumber FavoritePet
-------------- -----------
             7 Cat
```

<span data-ttu-id="d68e0-136">次のセクションでは、このテンプレートで使用されているテクノロジの一部について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="d68e0-136">The following sections describe in detail some of the technologies used by this template.</span></span>

## <a name="net-standard-library"></a><span data-ttu-id="d68e0-137">.NET 標準ライブラリ</span><span class="sxs-lookup"><span data-stu-id="d68e0-137">.NET Standard Library</span></span>

<span data-ttu-id="d68e0-138">[.NET Standard][] は、すべての .NET 実装で使用できる .NET API の正式な仕様です。</span><span class="sxs-lookup"><span data-stu-id="d68e0-138">[.NET Standard][] is a formal specification of .NET APIs that are available in all .NET implementations.</span></span> <span data-ttu-id="d68e0-139">.NET Standard をターゲットとするマネージド コードは、.NET Standard のそのバージョンと互換性のある .NET Framework および .NET Core のバージョンで動作します。</span><span class="sxs-lookup"><span data-stu-id="d68e0-139">Managed code targeting .NET Standard works with the .NET Framework and .NET Core versions that are compatible with that version of the .NET Standard.</span></span>

> [!NOTE]
> <span data-ttu-id="d68e0-140">.NET Standard に API が存在していても、.NET Core での API の実装で実行時に `PlatformNotSupportedException` がスローされる可能性があるので、Windows PowerShell および PowerShell Core との互換性を確認するため、両方の環境内でモジュールのテストを実行するのがベスト プラクティスです。</span><span class="sxs-lookup"><span data-stu-id="d68e0-140">Although an API may exist in .NET Standard, the API implementation in .NET Core may throw a `PlatformNotSupportedException` at runtime, so to verify compatibility with Windows PowerShell and PowerShell Core, the best practice is to run tests for your module within both environments.</span></span>
> <span data-ttu-id="d68e0-141">クロスプラットフォームを意図したモジュールの場合は、Linux と macOS でもテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="d68e0-141">Also run tests on Linux and macOS if your module is intended to be cross-platform.</span></span>

<span data-ttu-id="d68e0-142">.NET Standard をターゲットにすると、モジュールが進化しても、互換性のない API が誤ってモジュールに導入されないことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="d68e0-142">Targeting .NET Standard helps ensure that, as the module evolves, incompatible APIs don't accidentally get introduced into the module.</span></span> <span data-ttu-id="d68e0-143">非互換性は、実行時ではなくコンパイル時に検出されます。</span><span class="sxs-lookup"><span data-stu-id="d68e0-143">Incompatibilities are discovered at compile time instead of runtime.</span></span>

<span data-ttu-id="d68e0-144">ただし、互換性のある API を使用してさえいれば、.NET Standard をターゲットにしなくても、モジュールは Windows PowerShell と PowerShell Core の両方で動作します。</span><span class="sxs-lookup"><span data-stu-id="d68e0-144">However, it isn't required to target .NET Standard for a module to work with both Windows PowerShell and PowerShell Core, as long as you use compatible APIs.</span></span> <span data-ttu-id="d68e0-145">中間言語 (IL) は、2 つのランタイムの間で互換性があります。</span><span class="sxs-lookup"><span data-stu-id="d68e0-145">The Intermediate Language (IL) is compatible between the two runtimes.</span></span> <span data-ttu-id="d68e0-146">.NET Framework 4.6.1 をターゲットにでき、これは .NET Standard 2.0 と互換性があります。</span><span class="sxs-lookup"><span data-stu-id="d68e0-146">You can target .NET Framework 4.6.1, which is compatible with .NET Standard 2.0.</span></span> <span data-ttu-id="d68e0-147">.NET Standard 2.0 の対象外の API を使用していなければ、モジュールは再コンパイルしなくても PowerShell Core 6 で動作します。</span><span class="sxs-lookup"><span data-stu-id="d68e0-147">If you don't use APIs outside of .NET Standard 2.0, then your module works with PowerShell Core 6 without recompilation.</span></span>

## <a name="powershell-standard-library"></a><span data-ttu-id="d68e0-148">PowerShell Standard ライブラリ</span><span class="sxs-lookup"><span data-stu-id="d68e0-148">PowerShell Standard Library</span></span>

<span data-ttu-id="d68e0-149">[PowerShell Standard][] ライブラリは、その標準のバージョン以降のすべての PowerShell のバージョンで利用可能な PowerShell API の正式な仕様です。</span><span class="sxs-lookup"><span data-stu-id="d68e0-149">The [PowerShell Standard][] library is a formal specification of PowerShell APIs available in all PowerShell versions greater than or equal to the version of that standard.</span></span>

<span data-ttu-id="d68e0-150">たとえば、[PowerShell Standard 5.1][] は、Windows PowerShell 5.1 および PowerShell Core 6.0 以降の両方と互換性があります。</span><span class="sxs-lookup"><span data-stu-id="d68e0-150">For example, [PowerShell Standard 5.1][] is compatible with both Windows PowerShell 5.1 and PowerShell Core 6.0 or newer.</span></span>

<span data-ttu-id="d68e0-151">PowerShell Standard ライブラリを使用してモジュールをコンパイルすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d68e0-151">We recommend you compile your module using PowerShell Standard Library.</span></span> <span data-ttu-id="d68e0-152">ライブラリにより、API が使用可能で、Windows PowerShell と PowerShell Core 6 の両方で実装されていることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="d68e0-152">The library ensures the APIs are available and implemented in both Windows PowerShell and PowerShell Core 6.</span></span>
<span data-ttu-id="d68e0-153">PowerShell Standard は、常に上位互換性があるように意図されています。</span><span class="sxs-lookup"><span data-stu-id="d68e0-153">PowerShell Standard is intended to always be forwards-compatible.</span></span> <span data-ttu-id="d68e0-154">PowerShell Standard ライブラリ 5.1 を使用してビルドされたモジュールは、PowerShell の将来のバージョンと常に互換性があります。</span><span class="sxs-lookup"><span data-stu-id="d68e0-154">A module built using PowerShell Standard Library 5.1 will always be compatible with future versions of PowerShell.</span></span>

## <a name="module-manifest"></a><span data-ttu-id="d68e0-155">モジュール マニフェスト</span><span class="sxs-lookup"><span data-stu-id="d68e0-155">Module Manifest</span></span>

### <a name="indicating-compatibility-with-windows-powershell-and-powershell-core"></a><span data-ttu-id="d68e0-156">Windows PowerShell および PowerShell Core との互換性を示す</span><span class="sxs-lookup"><span data-stu-id="d68e0-156">Indicating Compatibility With Windows PowerShell and PowerShell Core</span></span>

<span data-ttu-id="d68e0-157">モジュールが Windows PowerShell と PowerShell Core の両方で動作することを検証した後は、モジュール マニフェストで [CompatiblePSEditions][] プロパティを使用して、互換性を明示的に示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="d68e0-157">After validating that your module works with both Windows PowerShell and PowerShell Core, the module manifest should explicitly indicate compatibility by using the [CompatiblePSEditions][] property.</span></span> <span data-ttu-id="d68e0-158">値 `Desktop` はモジュールに Windows PowerShell との互換性があることを意味し、値 `Core` はモジュールに PowerShell Core との互換性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d68e0-158">A value of `Desktop` means that the module is compatible with Windows PowerShell, while a value of `Core` means that the module is compatible with PowerShell Core.</span></span> <span data-ttu-id="d68e0-159">`Desktop` と `Core` の両方を含めると、モジュールに Windows PowerShell および PowerShell Core の両方との互換性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d68e0-159">Including both `Desktop` and `Core` means that the module is compatible with both Windows PowerShell and PowerShell Core.</span></span>

> [!NOTE]
> <span data-ttu-id="d68e0-160">`Core` によってモジュールに Windows、Linux、macOS との互換性があることが自動的に示されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d68e0-160">`Core` does not automatically mean that the module is compatible with Windows, Linux, and macOS.</span></span>
> <span data-ttu-id="d68e0-161">PowerShell v5 では **CompatiblePSEditions** プロパティが導入されました。</span><span class="sxs-lookup"><span data-stu-id="d68e0-161">The **CompatiblePSEditions** property was introduced in PowerShell v5.</span></span> <span data-ttu-id="d68e0-162">**CompatiblePSEditions** プロパティを使用しているモジュール マニフェストは、PowerShell v5 より前のバージョンに読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="d68e0-162">Module manifests that use the **CompatiblePSEditions** property fail to load in versions prior to PowerShell v5.</span></span>

### <a name="indicating-os-compatibility"></a><span data-ttu-id="d68e0-163">OS の互換性を示す</span><span class="sxs-lookup"><span data-stu-id="d68e0-163">Indicating OS Compatibility</span></span>

<span data-ttu-id="d68e0-164">最初に、モジュールが Linux と macOS で動作することを検証します。</span><span class="sxs-lookup"><span data-stu-id="d68e0-164">First, validate that your module works on Linux and macOS.</span></span> <span data-ttu-id="d68e0-165">次に、モジュール マニフェストでこれらのオペレーティング システムとの互換性を示します。</span><span class="sxs-lookup"><span data-stu-id="d68e0-165">Next, indicate compatibility with those operating systems in the module manifest.</span></span> <span data-ttu-id="d68e0-166">これにより、[PowerShell ギャラリー][]に発行した後で、ユーザーがオペレーティング システム用のモジュールを見つけやすくなります。</span><span class="sxs-lookup"><span data-stu-id="d68e0-166">This makes it easier for users to find your module for their operating system when published to the [PowerShell Gallery][].</span></span>

<span data-ttu-id="d68e0-167">モジュール マニフェスト内で、`PrivateData` プロパティには `PSData` サブプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="d68e0-167">Within the module manifest, the `PrivateData` property has a `PSData` sub-property.</span></span> <span data-ttu-id="d68e0-168">`PSData` の省略可能な `Tags` プロパティは、PowerShell ギャラリーに表示される値の配列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d68e0-168">The optional `Tags` property of `PSData` takes an array of values that show up in PowerShell Gallery.</span></span> <span data-ttu-id="d68e0-169">PowerShell ギャラリーでは、次の互換性の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d68e0-169">The PowerShell Gallery supports the following compatibility values:</span></span>

| <span data-ttu-id="d68e0-170">タグ</span><span class="sxs-lookup"><span data-stu-id="d68e0-170">Tag</span></span>               | <span data-ttu-id="d68e0-171">説明</span><span class="sxs-lookup"><span data-stu-id="d68e0-171">Description</span></span>                                |
|-------------------|--------------------------------------------|
| <span data-ttu-id="d68e0-172">PSEdition_Core</span><span class="sxs-lookup"><span data-stu-id="d68e0-172">PSEdition_Core</span></span>    | <span data-ttu-id="d68e0-173">PowerShell Core 6 と互換性があります</span><span class="sxs-lookup"><span data-stu-id="d68e0-173">Compatible with PowerShell Core 6</span></span>          |
| <span data-ttu-id="d68e0-174">PSEdition_Desktop</span><span class="sxs-lookup"><span data-stu-id="d68e0-174">PSEdition_Desktop</span></span> | <span data-ttu-id="d68e0-175">Windows PowerShell と互換性があります</span><span class="sxs-lookup"><span data-stu-id="d68e0-175">Compatible with Windows PowerShell</span></span>         |
| <span data-ttu-id="d68e0-176">Windows</span><span class="sxs-lookup"><span data-stu-id="d68e0-176">Windows</span></span>           | <span data-ttu-id="d68e0-177">Windows と互換性があります</span><span class="sxs-lookup"><span data-stu-id="d68e0-177">Compatible with Windows</span></span>                    |
| <span data-ttu-id="d68e0-178">Linux</span><span class="sxs-lookup"><span data-stu-id="d68e0-178">Linux</span></span>             | <span data-ttu-id="d68e0-179">Linux と互換性があります (特定のディストリビューションはなし)</span><span class="sxs-lookup"><span data-stu-id="d68e0-179">Compatible with Linux (no specific distro)</span></span> |
| <span data-ttu-id="d68e0-180">macOS</span><span class="sxs-lookup"><span data-stu-id="d68e0-180">macOS</span></span>             | <span data-ttu-id="d68e0-181">macOS と互換性があります</span><span class="sxs-lookup"><span data-stu-id="d68e0-181">Compatible with macOS</span></span>                      |

<span data-ttu-id="d68e0-182">例:</span><span class="sxs-lookup"><span data-stu-id="d68e0-182">Example:</span></span>

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

## <a name="dependency-on-native-libraries"></a><span data-ttu-id="d68e0-183">ネイティブ ライブラリに対する依存関係</span><span class="sxs-lookup"><span data-stu-id="d68e0-183">Dependency on Native Libraries</span></span>

<span data-ttu-id="d68e0-184">さまざまなオペレーティング システムまたはプロセッサ アーキテクチャでの使用を目的としたモジュールは、それ自体が何らかのネイティブ ライブラリに依存するマネージド ライブラリに依存する場合があります。</span><span class="sxs-lookup"><span data-stu-id="d68e0-184">Modules intended for use across different operating systems or processor architectures may depend on a managed library that itself depends on some native libraries.</span></span>

<span data-ttu-id="d68e0-185">PowerShell 7 より前では、マネージド ライブラリが正しく検出できるように、適切なネイティブ dll を読み込むためのカスタム コードを用意する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="d68e0-185">Prior to PowerShell 7, one would have to have custom code to load the appropriate native dll so that the managed library can find it correctly.</span></span>

<span data-ttu-id="d68e0-186">PowerShell 7 では、読み込まれるネイティブ バイナリは、[.NET RID カタログ][] 表記のサブセットに従って、マネージド ライブラリの場所内のサブフォルダー内で検索されます。</span><span class="sxs-lookup"><span data-stu-id="d68e0-186">With PowerShell 7, native binaries to load are searched in sub-folders within the managed library's location following a subset of the [.NET RID Catalog][] notation.</span></span>

```
managed.dll folder
                |
                |--- 'win-x64' folder
                |       |--- native.dll
                |
                |--- 'win-x86' folder
                |       |--- native.dll
                |
                |--- 'win-arm' folder
                |       |--- native.dll
                |
                |--- 'win-arm64' folder
                |       |--- native.dll
                |
                |--- 'linux-x64' folder
                |       |--- native.so
                |
                |--- 'linux-x86' folder
                |       |--- native.so
                |
                |--- 'linux-arm' folder
                |       |--- native.so
                |
                |--- 'linux-arm64' folder
                |       |--- native.so
                |
                |--- 'osx-x64' folder
                |       |--- native.dylib
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
[PowerShell Standard]: https://github.com/PowerShell/PowerShellStandard
[PowerShell Standard 5.1]: https://www.nuget.org/packages/PowerShellStandard.Library/5.1.0
[PowerShell ギャラリー]: https://www.powershellgallery.com
[PowerShell Gallery]: https://www.powershellgallery.com
[.NET Portability Analyzer]: https://github.com/Microsoft/dotnet-apiport
[CompatiblePSEditions]: /powershell/scripting/gallery/concepts/module-psedition-support
[.NET RID カタログ]: /dotnet/core/rid-catalog
[.NET RID Catalog]: /dotnet/core/rid-catalog
