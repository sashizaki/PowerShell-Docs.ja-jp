---
title: 標準ライブラリのバイナリ モジュールの作成方法
description: PowerShell 標準ライブラリを使用すると、PowerShell Core と Windows PowerShell 5.1 の両方で動作するクロスプラットフォーム モジュールを作成できます。
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: ff6a49f70a3fb77f5a30cc909d53bb77b3cd7d43
ms.sourcegitcommit: 8c01e56f0c10ff2637955dc892ea78432d563a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "88702747"
---
# <a name="how-to-create-a-standard-library-binary-module"></a><span data-ttu-id="75b16-103">標準ライブラリのバイナリ モジュールの作成方法</span><span class="sxs-lookup"><span data-stu-id="75b16-103">How to create a Standard Library binary module</span></span>

<span data-ttu-id="75b16-104">私は先日、バイナリ モジュールとして実装したいモジュールのアイデアを思いつきました。</span><span class="sxs-lookup"><span data-stu-id="75b16-104">I recently had an idea for module that I wanted to implement as a binary module.</span></span> <span data-ttu-id="75b16-105">[PowerShell 標準ライブラリ][]を使用して作成したことはまだないため、これは良い機会のように思われました。</span><span class="sxs-lookup"><span data-stu-id="75b16-105">I have yet to create one using the [PowerShell Standard Library][] so this felt like a good opportunity.</span></span> <span data-ttu-id="75b16-106">私は[クロスプラットフォーム バイナリ モジュールの作成][]に関するガイドを使用して、問題なくこのモジュールを作成しました。</span><span class="sxs-lookup"><span data-stu-id="75b16-106">I used the [Creating a cross-platform binary module][] guide to create this module without any roadblocks.</span></span>
<span data-ttu-id="75b16-107">ここではその同じプロセスについて説明し、その過程で多少のコメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="75b16-107">We're going to walk that same process and I'll add a little extra commentary along the way.</span></span>

> [!NOTE]
> <span data-ttu-id="75b16-108">この記事の[オリジナル バージョン][]は、[@KevinMarquette][] 氏のブログ記事です。</span><span class="sxs-lookup"><span data-stu-id="75b16-108">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="75b16-109">このコンテンツを共有してくださった Kevin 氏に、PowerShell チームより感謝を申し上げます。</span><span class="sxs-lookup"><span data-stu-id="75b16-109">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="75b16-110">[PowerShellExplained.com][] のブログをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="75b16-110">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="what-is-the-powershell-standard-library"></a><span data-ttu-id="75b16-111">PowerShell 標準ライブラリとは</span><span class="sxs-lookup"><span data-stu-id="75b16-111">What is the PowerShell Standard Library?</span></span>

<span data-ttu-id="75b16-112">PowerShell 標準ライブラリを使用すると、PowerShell Core と Windows PowerShell 5.1 (または 3.0) の両方で動作するクロスプラットフォーム モジュールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="75b16-112">The PowerShell Standard Library allows us to create cross platform modules that work in both PowerShell Core and with Windows PowerShell 5.1 (or 3.0).</span></span>

## <a name="planning-our-module"></a><span data-ttu-id="75b16-113">モジュールを計画する</span><span class="sxs-lookup"><span data-stu-id="75b16-113">Planning our module</span></span>

<span data-ttu-id="75b16-114">このモジュールの計画は、C# コード用の `src` フォルダーを作成し、スクリプト モジュールの場合と同様に残りの構造を作成することです。</span><span class="sxs-lookup"><span data-stu-id="75b16-114">The plan for this module is to create a `src` folder for the C# code and structure the rest like I would for a script module.</span></span> <span data-ttu-id="75b16-115">これには、ビルド スクリプトを使用してすべてを `output` フォルダーにコンパイルする作業も含まれます。</span><span class="sxs-lookup"><span data-stu-id="75b16-115">This includes using a build script to compile everything into an `output` folder.</span></span> <span data-ttu-id="75b16-116">フォルダー構造は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="75b16-116">The folder structure looks like this:</span></span>

```
MyModule
├───src
├───Output
│   └───MyModule
├───MyModule
│   ├───Data
│   ├───Private
│   └───Public
└───Tests
```

## <a name="getting-started"></a><span data-ttu-id="75b16-117">作業の開始</span><span class="sxs-lookup"><span data-stu-id="75b16-117">Getting Started</span></span>

<span data-ttu-id="75b16-118">私は通常 Plaster テンプレートを使用しますが、現在のテンプレートにはバイナリ モジュールのサポートがまだありません。</span><span class="sxs-lookup"><span data-stu-id="75b16-118">I normally use a Plaster template but my current template doesn't have any binary module support yet.</span></span> <span data-ttu-id="75b16-119">大した問題ではありません。</span><span class="sxs-lookup"><span data-stu-id="75b16-119">Not a big deal.</span></span> <span data-ttu-id="75b16-120">ここでは、これを手動で作成します。</span><span class="sxs-lookup"><span data-stu-id="75b16-120">I'll create this one by hand this time.</span></span>

<span data-ttu-id="75b16-121">まず、フォルダーを作成し、git リポジトリを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75b16-121">First I need to create the folder and create the git repo.</span></span> <span data-ttu-id="75b16-122">モジュール名のプレースホルダーとして `$module` を使用します。</span><span class="sxs-lookup"><span data-stu-id="75b16-122">I'm using `$module` as a placeholder for the module name.</span></span> <span data-ttu-id="75b16-123">これにより、必要に応じてこれらの例を再利用しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="75b16-123">This should make it easier for you to reuse these examples if needed.</span></span>

```powershell
$module = 'MyModule'
New-Item -Path $module -Type Directory
Set-Location $module
git init
```

<span data-ttu-id="75b16-124">次に、ルート レベル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="75b16-124">Then create the root level folders.</span></span>

```powershell
New-Item -Path 'src' -Type Directory
New-Item -Path 'Output' -Type Directory
New-Item -Path 'Tests' -Type Directory
New-Item -Path $module -Type Directory
```

### <a name="binary-module-setup"></a><span data-ttu-id="75b16-125">バイナリ モジュールのセットアップ</span><span class="sxs-lookup"><span data-stu-id="75b16-125">Binary module setup</span></span>

<span data-ttu-id="75b16-126">この記事ではバイナリ モジュールに重点を置くため、ここから開始します。</span><span class="sxs-lookup"><span data-stu-id="75b16-126">This article os focused on the binary module so that is where we'll start.</span></span> <span data-ttu-id="75b16-127">このセクションでは、[クロスプラットフォーム バイナリ モジュールの作成][]に関するガイドからの例を利用します。</span><span class="sxs-lookup"><span data-stu-id="75b16-127">This section pulls examples from the [Creating a cross-platform binary module][] guide.</span></span> <span data-ttu-id="75b16-128">詳細を知りたい場合や問題が発生した場合は、このガイドを確認してください。</span><span class="sxs-lookup"><span data-stu-id="75b16-128">Review that guide if you need more details or have any issues.</span></span>

<span data-ttu-id="75b16-129">最初に行う必要があるのは、インストールした [dotnet core SDK][] のバージョンを確認することです。</span><span class="sxs-lookup"><span data-stu-id="75b16-129">First thing we want to do is check the version of the [dotnet core SDK][] that we installed.</span></span> <span data-ttu-id="75b16-130">私は 2.1.4 を使用していますが、2.0.0 以降をインストールしてから続行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75b16-130">I'm using 2.1.4, but you should have 2.0.0 or newer before continuing.</span></span>

```powershell
PS> dotnet --version
2.1.4
```

<span data-ttu-id="75b16-131">このセクションでは、`src` フォルダーから作業します。</span><span class="sxs-lookup"><span data-stu-id="75b16-131">I'm working out of the `src` folder for this section.</span></span>

```powershell
Set-Location 'src'
```

<span data-ttu-id="75b16-132">dotnet コマンドを使用して、新しいクラス ライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="75b16-132">Using the dotnet command, create a new class library.</span></span>

```powershell
dotnet new classlib --name $module
```

<span data-ttu-id="75b16-133">これにより、サブフォルダーにライブラリ プロジェクトが作成されましたが、この追加された入れ子のレベルは不要です。</span><span class="sxs-lookup"><span data-stu-id="75b16-133">This created the library project in a subfolder but I don't want that extra level of nesting.</span></span> <span data-ttu-id="75b16-134">これらのファイルを 1 つ上のレベルに移動します。</span><span class="sxs-lookup"><span data-stu-id="75b16-134">I'm going to move those files up a level.</span></span>

```powershell
Move-Item -Path .\$module\* -Destination .\
Remove-Item $module -Recurse
```

<span data-ttu-id="75b16-135">プロジェクトに .NET Core SDK のバージョンを設定します。</span><span class="sxs-lookup"><span data-stu-id="75b16-135">Set the .NET core SDK version for the project.</span></span> <span data-ttu-id="75b16-136">2\.1 SDK があるので、私は 2.1.0 を指定します。</span><span class="sxs-lookup"><span data-stu-id="75b16-136">I have the 2.1 SDK so I'm going to specify 2.1.0.</span></span>
<span data-ttu-id="75b16-137">2\.0 SDK を使用している場合は、2.0.0 を使用してください。</span><span class="sxs-lookup"><span data-stu-id="75b16-137">Use 2.0.0 if you're using the 2.0 SDK.</span></span>

```powershell
dotnet new globaljson --sdk-version 2.1.0
```

<span data-ttu-id="75b16-138">PowerShell 標準ライブラリの [NuGet パッケージ][]をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="75b16-138">Add the PowerShell Standard Library [NuGet package][] to the project.</span></span> <span data-ttu-id="75b16-139">必要な互換性レベルにおいて使用できる最新のバージョンを使用するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="75b16-139">Make sure you use the most recent version available for the level of compatibility that you need.</span></span> <span data-ttu-id="75b16-140">私は最新バージョンを既定値に設定しますが、このモジュールで PowerShell 3.0 より新しい機能が活用されることはないはずです。</span><span class="sxs-lookup"><span data-stu-id="75b16-140">I would default to the latest version but I don't think this module leverages any features newer than PowerShell 3.0.</span></span>

```powershell
dotnet add package PowerShellStandard.Library --version 7.0.0-preview.1
```

<span data-ttu-id="75b16-141">src フォルダーは次のようになるはずです。</span><span class="sxs-lookup"><span data-stu-id="75b16-141">We should have a src folder that looks like this:</span></span>

```powershell
PS> Get-ChildItem
    Directory: \MyModule\src

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        7/14/2018   9:51 PM                obj
-a----        7/14/2018   9:51 PM             86 Class1.cs
-a----        7/14/2018  10:03 PM            259 MyModule.csproj
-a----        7/14/2018  10:05 PM             45 global.json
```

<span data-ttu-id="75b16-142">これで、独自のコードをプロジェクトに追加する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="75b16-142">Now we're ready to add our own code to the project.</span></span>

### <a name="building-a-binary-cmdlet"></a><span data-ttu-id="75b16-143">バイナリ コマンドレットのビルド</span><span class="sxs-lookup"><span data-stu-id="75b16-143">Building a binary cmdlet</span></span>

<span data-ttu-id="75b16-144">次のスターター コマンドレットを含むように `src\Class1.cs` を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75b16-144">We need to update the `src\Class1.cs` to contain this starter cmdlet:</span></span>

```csharp
using System;
using System.Management.Automation;

namespace MyModule
{
    [Cmdlet( VerbsDiagnostic.Resolve , "MyCmdlet")]
    public class ResolveMyCmdletCommand : PSCmdlet
    {
        [Parameter(Position=0)]
        public Object InputObject { get; set; }

        protected override void EndProcessing()
        {
            this.WriteObject(this.InputObject);
            base.EndProcessing();
        }
    }
}
```

<span data-ttu-id="75b16-145">クラス名と一致するようにファイル名を変更します。</span><span class="sxs-lookup"><span data-stu-id="75b16-145">Rename the file to match the class name.</span></span>

```powershell
Rename-Item .\Class1.cs .\ResolveMyCmdletCommand.cs
```

<span data-ttu-id="75b16-146">次に、モジュールをビルドできます。</span><span class="sxs-lookup"><span data-stu-id="75b16-146">Then we can build our module.</span></span>

```powershell
PS> dotnet build

Microsoft (R) Build Engine version 15.5.180.51428 for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

Restore completed in 18.19 ms for C:\workspace\MyModule\src\MyModule.csproj.
MyModule -> C:\workspace\MyModule\src\bin\Debug\netstandard2.0\MyModule.dll

Build succeeded.
    0 Warning(s)
    0 Error(s)

Time Elapsed 00:00:02.19
```

<span data-ttu-id="75b16-147">新しい dll に対して `Import-Module` を呼び出し、新しいコマンドレットを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="75b16-147">We can call `Import-Module` on the new dll to load our new CMDlet.</span></span>

```powershell
PS> Import-Module .\bin\Debug\netstandard2.0\$module.dll
PS> Get-Command -Module $module

CommandType Name                    Version Source
----------- ----                    ------- ------
Cmdlet      Resolve-MyCmdlet        1.0.0.0 MyModule
```

<span data-ttu-id="75b16-148">ご自分のシステムでインポートに失敗した場合は、.NET を 4.7.1 以降に更新してみてください。</span><span class="sxs-lookup"><span data-stu-id="75b16-148">If the import fails on your system, try updating .NET to 4.7.1 or newer.</span></span> <span data-ttu-id="75b16-149">[クロスプラットフォーム バイナリ モジュールの作成][]に関するガイドでは、.NET のサポートと旧バージョンの .NET の互換性について詳しく説明しています。</span><span class="sxs-lookup"><span data-stu-id="75b16-149">The [Creating a cross-platform binary module][] guide goes into more details on .NET support and compatibility for older versions of .NET.</span></span>

### <a name="module-manifest"></a><span data-ttu-id="75b16-150">モジュール マニフェスト</span><span class="sxs-lookup"><span data-stu-id="75b16-150">Module manifest</span></span>

<span data-ttu-id="75b16-151">dll をインポートして、作業モジュールを用意することができたら便利です。</span><span class="sxs-lookup"><span data-stu-id="75b16-151">It's cool that we can import the dll and have a working module.</span></span> <span data-ttu-id="75b16-152">これを継続し、モジュール マニフェストを作成してみたいと思います。</span><span class="sxs-lookup"><span data-stu-id="75b16-152">I like to keep going with it and create a module manifest.</span></span> <span data-ttu-id="75b16-153">後で PSGallery に発行する場合は、マニフェストが必要です。</span><span class="sxs-lookup"><span data-stu-id="75b16-153">We need the manifest if we want to publish to the PSGallery later.</span></span>

<span data-ttu-id="75b16-154">プロジェクトのルートから次のコマンドを実行して、必要なモジュール マニフェストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="75b16-154">From the root of our project, we can run this command to create the module manifest that we need.</span></span>

```powershell
$manifestSplat = @{
    Path              = ".\$module\$module.psd1"
    Author            = 'Kevin Marquette'
    NestedModules     = @('bin\MyModule.dll')
    RootModule        = "$module.psm1"
    FunctionsToExport = @('Resolve-MyCmdlet')
}
New-ModuleManifest @manifestSplat
```

<span data-ttu-id="75b16-155">また、今後の PowerShell 関数用に、空のルート モジュールも作成します。</span><span class="sxs-lookup"><span data-stu-id="75b16-155">I'm also going to create an empty root module for future PowerShell functions.</span></span>

```powershell
Set-Content -Value '' -Path ".\$module\$module.psm1"
```

<span data-ttu-id="75b16-156">これにより、通常の PowerShell 関数とバイナリ コマンドレットの両方を同じプロジェクトに混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="75b16-156">This allows me to mix both normal PowerShell functions and binary Cmdlets in the same project.</span></span>

### <a name="building-the-full-module"></a><span data-ttu-id="75b16-157">完全なモジュールのビルド</span><span class="sxs-lookup"><span data-stu-id="75b16-157">Building the full module</span></span>

<span data-ttu-id="75b16-158">すべてを 1 つの出力フォルダーにコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="75b16-158">I compile everything together into an output folder.</span></span> <span data-ttu-id="75b16-159">そのためには、ビルド スクリプトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75b16-159">We need to create a build script to do that.</span></span> <span data-ttu-id="75b16-160">通常は、これを `Invoke-Build` スクリプトに追加するのですが、この例ではこれをシンプルにしておくことができます。</span><span class="sxs-lookup"><span data-stu-id="75b16-160">I would normally add this to an `Invoke-Build` script, but we can keep it simple for this example.</span></span> <span data-ttu-id="75b16-161">これをプロジェクトのルートにある `build.ps1` に追加します。</span><span class="sxs-lookup"><span data-stu-id="75b16-161">Add this to a `build.ps1` at the root of the project.</span></span>

```powershell
$module = 'MyModule'
Push-Location $PSScriptRoot

dotnet build $PSScriptRoot\src -o $PSScriptRoot\output\$module\bin
Copy-Item "$PSScriptRoot\$module\*" "$PSScriptRoot\output\$module" -Recurse -Force

Import-Module "$PSScriptRoot\Output\$module\$module.psd1"
Invoke-Pester "$PSScriptRoot\Tests"
```

<span data-ttu-id="75b16-162">これらのコマンドにより、DLL がビルドされ、`output\$module\bin` フォルダーに配置されます。</span><span class="sxs-lookup"><span data-stu-id="75b16-162">These commands build our DLL and place it into our `output\$module\bin` folder.</span></span> <span data-ttu-id="75b16-163">その後、その他のモジュール ファイルが適切な場所にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="75b16-163">It then copies the other module files into place.</span></span>

```
Output
└───MyModule
    │   MyModule.psd1
    │   MyModule.psm1
    │
    └───bin
            MyModule.deps.json
            MyModule.dll
            MyModule.pdb
```

<span data-ttu-id="75b16-164">この時点で、psd1 ファイルを使用してモジュールをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="75b16-164">At this point, we can import our module with the psd1 file.</span></span>

```powershell
Import-Module ".\Output\$module\$module.psd1"
```

<span data-ttu-id="75b16-165">ここから、`.\Output\$module` フォルダーを `$env:PSModulePath` ディレクトリに追加することができ、これにより必要な時にいつでもコマンドが自動的に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="75b16-165">From here, we can drop the `.\Output\$module` folder into our `$env:PSModulePath` directory and it autoloads our command whenever we need it.</span></span>

### <a name="update-dotnet-new-psmodule"></a><span data-ttu-id="75b16-166">更新: dotnet new PSModule</span><span class="sxs-lookup"><span data-stu-id="75b16-166">Update: dotnet new PSModule</span></span>

<span data-ttu-id="75b16-167">`dotnet` ツールには `PSModule` テンプレートがあることがわかりました。</span><span class="sxs-lookup"><span data-stu-id="75b16-167">I learned that the `dotnet` tool has a `PSModule` template.</span></span>

<span data-ttu-id="75b16-168">上記で説明したすべての手順はまだ有効ですが、このテンプレートによってその多くが省略されます。これはまだかなり新しいテンプレートであり、依然として改良が加えられています。</span><span class="sxs-lookup"><span data-stu-id="75b16-168">All the steps that I outlined above are still valid, but this template cuts many of them out. It's still a fairly new template that is still getting some polish placed on it.</span></span> <span data-ttu-id="75b16-169">これからも改良が続けられていくでしょう。</span><span class="sxs-lookup"><span data-stu-id="75b16-169">Expect it to keep getting better from here.</span></span>

<span data-ttu-id="75b16-170">PSModule テンプレートをインストールして使用する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="75b16-170">This is how you use install and use the PSModule template.</span></span>

```powershell
dotnet new -i Microsoft.PowerShell.Standard.Module.Template
dotnet new psmodule
dotnet build
Import-Module "bin\Debug\netstandard2.0\$module.dll"
Get-Module $module
```

<span data-ttu-id="75b16-171">この実用最小限のテンプレートによって、.NET SDK と PowerShell 標準ライブラリの追加が処理され、プロジェクトにクラスの例が作成されます。</span><span class="sxs-lookup"><span data-stu-id="75b16-171">This minimally-viable template takes care of adding the .NET SDK, PowerShell Standard Library, and creates an example class in the project.</span></span> <span data-ttu-id="75b16-172">すぐにこれをビルドして実行することができます。</span><span class="sxs-lookup"><span data-stu-id="75b16-172">You can build it and run it right away.</span></span>

## <a name="important-details"></a><span data-ttu-id="75b16-173">重要な詳細</span><span class="sxs-lookup"><span data-stu-id="75b16-173">Important details</span></span>

<span data-ttu-id="75b16-174">この記事を終了する前に、言及する価値のあるその他の詳細についていくつか説明します。</span><span class="sxs-lookup"><span data-stu-id="75b16-174">Before we end this article, here are a few other details worth mentioning.</span></span>

### <a name="unloading-dlls"></a><span data-ttu-id="75b16-175">DLL のアンロード</span><span class="sxs-lookup"><span data-stu-id="75b16-175">Unloading DLLs</span></span>

<span data-ttu-id="75b16-176">バイナリ モジュールが読み込まれると、それを実際にアンロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="75b16-176">Once a binary module is loaded, you can't really unload it.</span></span> <span data-ttu-id="75b16-177">DLL ファイルは、これをアンロードするまでロックされます。</span><span class="sxs-lookup"><span data-stu-id="75b16-177">The DLL file is locked until you unload it.</span></span> <span data-ttu-id="75b16-178">これは開発時にはわずらわしい場合があります。変更を加えてビルドしようとするたびに、ファイルがしばしばロックされているためです。</span><span class="sxs-lookup"><span data-stu-id="75b16-178">This can be annoying when developing because every time you make a change and want to build it, the file is often locked.</span></span> <span data-ttu-id="75b16-179">これを解決する唯一の信頼性の高い方法は、DLL を読み込んだ PowerShell セッションを閉じることです。</span><span class="sxs-lookup"><span data-stu-id="75b16-179">The only reliable way to resolve this is to close the PowerShell session that loaded the DLL.</span></span>

### <a name="vs-code-reload-window-action"></a><span data-ttu-id="75b16-180">VS Code のウィンドウの再読み込み操作</span><span class="sxs-lookup"><span data-stu-id="75b16-180">VS Code reload window action</span></span>

<span data-ttu-id="75b16-181">私は、PowerShell の開発作業のほとんどを [VS Code][] で行っています。</span><span class="sxs-lookup"><span data-stu-id="75b16-181">I do most of my PowerShell dev work in [VS Code][].</span></span> <span data-ttu-id="75b16-182">バイナリ モジュール (またはクラスを含むモジュール) に取り組んでいるときは、ビルドするたびに VS Code を再読み込みする習慣を持っています。</span><span class="sxs-lookup"><span data-stu-id="75b16-182">When I'm working on a binary module (or a module with classes), I've gotten into the habit of reloading VS Code every time I build.</span></span>
<span data-ttu-id="75b16-183"><kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd> キーを押すとコマンド ウィンドウがポップアップ表示され、`Reload Window` は常に一覧の先頭にあります。</span><span class="sxs-lookup"><span data-stu-id="75b16-183"><kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> pops the command window and `Reload Window` is always at the top of my list.</span></span>

### <a name="nested-powershell-sessions"></a><span data-ttu-id="75b16-184">入れ子になった PowerShell セッション</span><span class="sxs-lookup"><span data-stu-id="75b16-184">Nested PowerShell sessions</span></span>

<span data-ttu-id="75b16-185">もう 1 つの選択肢は、適切な Pester テスト カバレッジを使用することです。</span><span class="sxs-lookup"><span data-stu-id="75b16-185">One other option is to have good Pester test coverage.</span></span> <span data-ttu-id="75b16-186">次に、新しい PowerShell セッションを開始するように build.ps1 スクリプトを調整して、ビルドを実行し、テストを実行して、セッションを閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="75b16-186">Then you can adjust the build.ps1 script to start a new PowerShell session, perform the build, run the tests, and close the session.</span></span>

### <a name="updating-installed-modules"></a><span data-ttu-id="75b16-187">インストールされているモジュールの更新</span><span class="sxs-lookup"><span data-stu-id="75b16-187">Updating installed modules</span></span>

<span data-ttu-id="75b16-188">ローカルにインストールされているモジュールを更新しようとする場合、このロックが面倒になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="75b16-188">This locking can be annoying when trying to update your locally installed module.</span></span> <span data-ttu-id="75b16-189">これがいずれかのセッションで読み込まれている場合は、それを見つけて閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="75b16-189">If any session has it loaded, you have to go hunt it down and close it.</span></span> <span data-ttu-id="75b16-190">PSGallery からインストールする場合、これはあまり問題にはなりません。モジュールのバージョン管理によって新しいものが異なるフォルダーに配置されるためです。</span><span class="sxs-lookup"><span data-stu-id="75b16-190">This is less of an issue when installing from a PSGallery because module versioning places the new one in a different folder.</span></span>

<span data-ttu-id="75b16-191">ローカルの PSGallery を設定し、ビルドの一部としてそれに発行することができます。</span><span class="sxs-lookup"><span data-stu-id="75b16-191">You can set up a local PSGallery and publish to that as part of your build.</span></span> <span data-ttu-id="75b16-192">その後、その PSGallery からローカル インストールを実行します。</span><span class="sxs-lookup"><span data-stu-id="75b16-192">Then do your local install from that PSGallery.</span></span> <span data-ttu-id="75b16-193">これは多くの作業のように聞こえますが、docker コンテナーを起動する場合と同じように簡単にできます。</span><span class="sxs-lookup"><span data-stu-id="75b16-193">This sounds like a lot of work, but this can be as simple as starting a docker container.</span></span> <span data-ttu-id="75b16-194">[PSRepository 用に NuGet サーバーを使用する][]に関する投稿で、これを行う方法が説明されています。</span><span class="sxs-lookup"><span data-stu-id="75b16-194">I cover a way to do that in my post on [Using a NuGet server for a PSRepository][].</span></span>

## <a name="why-binary-modules"></a><span data-ttu-id="75b16-195">バイナリ モジュールを使用する理由</span><span class="sxs-lookup"><span data-stu-id="75b16-195">Why binary modules?</span></span>

<span data-ttu-id="75b16-196">バイナリ モジュールを作成する方法について説明しましたが、それを作成する理由については触れませんでした。</span><span class="sxs-lookup"><span data-stu-id="75b16-196">I jumped right into how to make a binary module and didn't mention why you want to make one.</span></span> <span data-ttu-id="75b16-197">実際には、ユーザーは C# で記述し、PowerShell コマンドレットと関数への簡単なアクセスをあきらめます。</span><span class="sxs-lookup"><span data-stu-id="75b16-197">In reality, you are writing C# and give up easy access to PowerShell Cmdlets and functions.</span></span> <span data-ttu-id="75b16-198">これが、私がすぐにバイナリ モジュールに移行しなかった主な理由です。</span><span class="sxs-lookup"><span data-stu-id="75b16-198">That is the main reason why I have not shifted to binary modules sooner.</span></span>

<span data-ttu-id="75b16-199">ただし、他の多くの PowerShell コマンドに依存しないモジュールを作成する場合は、大きなパフォーマンス上の利点を得られる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="75b16-199">But if you are creating a module that doesn't depend on a lot of other PowerShell commands, the performance benefit can be significant.</span></span> <span data-ttu-id="75b16-200">C# を使用することで、PowerShell によって追加されるオーバーヘッドを軽減できます。</span><span class="sxs-lookup"><span data-stu-id="75b16-200">By dropping into C#, you get to shed the overhead added by PowerShell.</span></span> <span data-ttu-id="75b16-201">PowerShell は、コンピューターではなく管理者向けに最適化されたため、オーバーヘッドがわずかに増加しています。</span><span class="sxs-lookup"><span data-stu-id="75b16-201">PowerShell was optimized for the administrator, not the computer, and that adds a little overhead.</span></span>

<span data-ttu-id="75b16-202">私たちの職場には、JSON とハッシュテーブルを使用する多くの作業を行う重要なプロセスがあります。</span><span class="sxs-lookup"><span data-stu-id="75b16-202">At work, we have a critical process that does a lot of work with JSON and Hashtables.</span></span> <span data-ttu-id="75b16-203">私たちは PowerShell を可能な限り最適化しましたが、このプロセスは依然として 12 分間実行されました。</span><span class="sxs-lookup"><span data-stu-id="75b16-203">We optimized the PowerShell as much as we could but this process was still running for 12 minutes.</span></span> <span data-ttu-id="75b16-204">モジュールには、既に多数の C# スタイルの PowerShell が含まれていました。</span><span class="sxs-lookup"><span data-stu-id="75b16-204">The module already contained a lot of C# style PowerShell.</span></span> <span data-ttu-id="75b16-205">これにより、バイナリ モジュールへの変換がクリーンかつ実行しやすくなりました。</span><span class="sxs-lookup"><span data-stu-id="75b16-205">This made the conversion to a binary module clean and easy to do.</span></span> <span data-ttu-id="75b16-206">この変換によって、そのプロセスが 12 分以上から 4 分以内に短縮されました。</span><span class="sxs-lookup"><span data-stu-id="75b16-206">Our conversion cut that process down from over 12 minutes to under four minutes.</span></span>

### <a name="hybrid-modules"></a><span data-ttu-id="75b16-207">ハイブリッド モジュール</span><span class="sxs-lookup"><span data-stu-id="75b16-207">Hybrid modules</span></span>

<span data-ttu-id="75b16-208">バイナリ コマンドレットと PowerShell 拡張関数を混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="75b16-208">You can mix binary Cmdlets with PowerShell advanced functions.</span></span> <span data-ttu-id="75b16-209">これはまさにこのガイドで行われていることです。</span><span class="sxs-lookup"><span data-stu-id="75b16-209">That is exactly what I'm doing in this guide.</span></span> <span data-ttu-id="75b16-210">スクリプト モジュールについて知っているすべてのことを利用できます。これらはすべて同じ方法で適用されます。</span><span class="sxs-lookup"><span data-stu-id="75b16-210">You can take everything you know about script modules and it all applies the same way.</span></span>
<span data-ttu-id="75b16-211">今回作成した空の `psm1` ファイルは、単に後で他の PowerShell 関数を追加することが目的です。</span><span class="sxs-lookup"><span data-stu-id="75b16-211">The empty `psm1` file that I created today is there just so you can drop in other PowerShell functions later.</span></span>

<span data-ttu-id="75b16-212">作成したコンパイル済みのコマンドレットのほとんどが、最初は PowerShell 関数として開始されています。</span><span class="sxs-lookup"><span data-stu-id="75b16-212">Almost all of the compiled cmdlets that we created started out as a PowerShell function first.</span></span> <span data-ttu-id="75b16-213">すべてのバイナリ モジュールは、実際にはハイブリッド モジュールです。</span><span class="sxs-lookup"><span data-stu-id="75b16-213">All of our binary modules are really hybrid modules.</span></span>

### <a name="build-scripts"></a><span data-ttu-id="75b16-214">ビルド スクリプト</span><span class="sxs-lookup"><span data-stu-id="75b16-214">Build scripts</span></span>

<span data-ttu-id="75b16-215">ここでは、ビルド スクリプトをシンプルな状態にしておきました。</span><span class="sxs-lookup"><span data-stu-id="75b16-215">I kept the build script simple here.</span></span> <span data-ttu-id="75b16-216">私は通常、CI/CD パイプラインの一部として大きな `Invoke-Build` スクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="75b16-216">I generally use a large `Invoke-Build` script as part of my CI/CD pipeline.</span></span> <span data-ttu-id="75b16-217">これにより、さらに多くの機能を実行できます。たとえば、Pester テストの実行、PSScriptAnalyzer の実行、バージョン管理、PSGallery への発行などです。</span><span class="sxs-lookup"><span data-stu-id="75b16-217">It does more magic like running Pester tests, running PSScriptAnalyzer, managing versioning, and publishing to the PSGallery.</span></span> <span data-ttu-id="75b16-218">自分のモジュール用にビルド スクリプトを使い始めると、これに追加するものを多数発見できました。</span><span class="sxs-lookup"><span data-stu-id="75b16-218">Once I started using a build script for my modules, I was able to find lots of things to add to it.</span></span>

## <a name="final-thoughts"></a><span data-ttu-id="75b16-219">最後に</span><span class="sxs-lookup"><span data-stu-id="75b16-219">Final thoughts</span></span>

<span data-ttu-id="75b16-220">バイナリ モジュールは簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="75b16-220">Binary modules are easy to create.</span></span> <span data-ttu-id="75b16-221">コマンドレットを作成するための C# の構文には触れませんでしたが、[Windows PowerShell SDK][] にはこれに関する多くのドキュメントがあります。</span><span class="sxs-lookup"><span data-stu-id="75b16-221">I didn't touch on the C# syntax for creating a Cmdlet, but there is plenty of documentation on it in the [Windows PowerShell SDK][].</span></span> <span data-ttu-id="75b16-222">これは、より高度な C# への足掛かりとして、ぜひ試してみる価値があります。</span><span class="sxs-lookup"><span data-stu-id="75b16-222">It is definitely something worth experimenting with as a stepping stone into more serious C#.</span></span>

<!-- link references -->
[オリジナル バージョン]: https://powershellexplained.com/2018-08-04-Powershell-Standard-Library-Binary-Module/
[original version]: https://powershellexplained.com/2018-08-04-Powershell-Standard-Library-Binary-Module/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[PowerShell 標準ライブラリ]: https://github.com/PowerShell/PowerShellStandard
[PowerShell Standard Library]: https://github.com/PowerShell/PowerShellStandard
[クロスプラットフォーム バイナリ モジュールの作成]: https://github.com/PowerShell/PowerShell/blob/master/docs/cmdlet-example/command-line-simple-example.md
[Creating a cross-platform binary module]: https://github.com/PowerShell/PowerShell/blob/master/docs/cmdlet-example/command-line-simple-example.md
[dotnet core SDK]: https://www.microsoft.com/net/download/core
[PSRepository 用に NuGet サーバーを使用する]: https://powershellexplained.com/2018-03-03-Powershell-Using-a-NuGet-server-for-a-PSRepository/
[Using a NuGet server for a PSRepository]: https://powershellexplained.com/2018-03-03-Powershell-Using-a-NuGet-server-for-a-PSRepository/
[Windows PowerShell SDK]: /powershell/scripting/developer/windows-powershell-reference
[VS Code]: https://code.visualstudio.com
[nuget パッケージ]: https://www.nuget.org/packages/PowerShellStandard.Library/
[nuget package]: https://www.nuget.org/packages/PowerShellStandard.Library/
