---
title: スクリプト モジュール
description: スクリプト モジュールを使用すると、スクリプトや関数を、再利用可能なツールに容易にパッケージ化できます。
ms.date: 06/02/2020
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: c557c071bc202a4216a77e7e5ae0bd73b4bc014b
ms.sourcegitcommit: df5e6f032ee2d4b556d50406832732d2f7dc2502
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2021
ms.locfileid: "99601190"
---
# <a name="chapter-10---script-modules"></a><span data-ttu-id="4192e-103">第 10 章 - スクリプト モジュール</span><span class="sxs-lookup"><span data-stu-id="4192e-103">Chapter 10 - Script modules</span></span>

<span data-ttu-id="4192e-104">PowerShell のワンライナーやスクリプトを頻繁に使用する予定がある場合は、それを再利用可能なツールに変換するという作業が、より重要になってきます。</span><span class="sxs-lookup"><span data-stu-id="4192e-104">Turning your one-liners and scripts in PowerShell into reusable tools becomes even more important if it's something that you're going to use frequently.</span></span> <span data-ttu-id="4192e-105">関数をスクリプト モジュールにパッケージ化すると、プロらしい外観になり、共有しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="4192e-105">Packaging your functions in a script module makes them look and feel more professional and makes them easier to share.</span></span>

## <a name="dot-sourcing-functions"></a><span data-ttu-id="4192e-106">ドット ソース関数</span><span class="sxs-lookup"><span data-stu-id="4192e-106">Dot-Sourcing Functions</span></span>

<span data-ttu-id="4192e-107">前の章で言及しなかったのが、ドット ソース関数です。</span><span class="sxs-lookup"><span data-stu-id="4192e-107">Something that we didn't talk about in the previous chapter is dot-sourcing functions.</span></span> <span data-ttu-id="4192e-108">スクリプトの関数がモジュールの一部ではない場合、その関数をメモリに読み込むには、それが保存されている `.PS1` ファイルをドットソースするしかありません。</span><span class="sxs-lookup"><span data-stu-id="4192e-108">When a function in a script isn't part of a module, the only way to load it into memory is to dot-source the `.PS1` file that it's saved in.</span></span>

<span data-ttu-id="4192e-109">次の関数は、`Get-MrPSVersion.ps1` として保存されています。</span><span class="sxs-lookup"><span data-stu-id="4192e-109">The following function has been saved as `Get-MrPSVersion.ps1`.</span></span>

```powershell
function Get-MrPSVersion {
    $PSVersionTable
}
```

<span data-ttu-id="4192e-110">スクリプトを実行しても、何も起こりません。</span><span class="sxs-lookup"><span data-stu-id="4192e-110">When you run the script, nothing happens.</span></span>

```powershell
.\Get-MrPSVersion.ps1
```

<span data-ttu-id="4192e-111">関数を呼び出そうとすると、エラー メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="4192e-111">If you try to call the function, it generates an error message.</span></span>

```powershell
Get-MrPSVersion
```

```Output
Get-MrPSVersion : The term 'Get-MrPSVersion' is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or if a path
was included, verify that the path is correct and try again.
At line:1 char:1
+ Get-MrPSVersion
    + CategoryInfo          : ObjectNotFound: (Get-MrPSVersion:String) [], CommandNotFou
   ndException
    + FullyQualifiedErrorId : CommandNotFoundException

```

<span data-ttu-id="4192e-112">関数がメモリに読み込まれているかどうかを確認するには、その関数が **Function** PSDrive に存在するかどうかをチェックします。</span><span class="sxs-lookup"><span data-stu-id="4192e-112">You can determine if functions are loaded into memory by checking to see if they exist on the **Function** PSDrive.</span></span>

```powershell
Get-ChildItem -Path Function:\Get-MrPSVersion
```

```Output
Get-ChildItem : Cannot find path 'Get-MrPSVersion' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path Function:\Get-MrPSVersion
    + CategoryInfo          : ObjectNotFound: (Get-MrPSVersion:String) [Get-ChildItem],
   ItemNotFoundException
    + FullyQualifiedErrorId : PathNotFound,Microsoft.PowerShell.Commands.GetChildItemCommand
```

<span data-ttu-id="4192e-113">関数を含むスクリプトを呼び出すときに問題が発生するのは、その関数が _Script_ スコープに読み込まれているからです。</span><span class="sxs-lookup"><span data-stu-id="4192e-113">The problem with calling the script that contains the function is that the functions are loaded in the _Script_ scope.</span></span> <span data-ttu-id="4192e-114">スクリプトが完了すると、そのスコープは削除され、そのスコープと一緒に関数も削除されます。</span><span class="sxs-lookup"><span data-stu-id="4192e-114">When the script completes, that scope is removed and the function is removed with it.</span></span>

<span data-ttu-id="4192e-115">関数は _Global_ スコープに読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="4192e-115">The function needs to be loaded into the _Global_ scope.</span></span> <span data-ttu-id="4192e-116">これを行うには、関数を含むスクリプトをドットソースします。</span><span class="sxs-lookup"><span data-stu-id="4192e-116">That can be accomplished by dot-sourcing the script that contains the function.</span></span> <span data-ttu-id="4192e-117">相対パスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4192e-117">The relative path can be used.</span></span>

```powershell
. .\Get-MrPSVersion.ps1
```

<span data-ttu-id="4192e-118">絶対パスも使用できます。</span><span class="sxs-lookup"><span data-stu-id="4192e-118">The fully qualified path can also be used.</span></span>

```powershell
. C:\Demo\Get-MrPSVersion.ps1
```

<span data-ttu-id="4192e-119">パスの一部が変数に格納されている場合、その部分は、パスの残りの部分と結合できます。</span><span class="sxs-lookup"><span data-stu-id="4192e-119">If a portion of the path is stored in a variable, it can be combined with the remainder of the path.</span></span>
<span data-ttu-id="4192e-120">文字列連結を使用して、変数とパスの残りの部分を結合する理由はありません。</span><span class="sxs-lookup"><span data-stu-id="4192e-120">There's no reason to use string concatenation to combine the variable together with the remainder of the path.</span></span>

```powershell
$Path = 'C:\'
. $Path\Get-MrPSVersion.ps1
```

<span data-ttu-id="4192e-121">ここで **Function** PSDrive を確認すると、`Get-MrPSVersion` 関数が存在しています。</span><span class="sxs-lookup"><span data-stu-id="4192e-121">Now when I check the **Function** PSDrive, the `Get-MrPSVersion` function exists.</span></span>

```powershell
Get-ChildItem -Path Function:\Get-MrPSVersion
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Function        Get-MrPSVersion
```

## <a name="script-modules"></a><span data-ttu-id="4192e-122">スクリプト モジュール</span><span class="sxs-lookup"><span data-stu-id="4192e-122">Script Modules</span></span>

<span data-ttu-id="4192e-123">PowerShell のスクリプト モジュールは、1 つ以上の関数を含むファイルに過ぎず、`.PS1` ファイルではなく `.PSM1` ファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="4192e-123">A script module in PowerShell is simply a file containing one or more functions that's saved as a `.PSM1` file instead of a `.PS1` file.</span></span>

<span data-ttu-id="4192e-124">スクリプト モジュールを作成するには、どうすればよいのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="4192e-124">How do you create a script module?</span></span> <span data-ttu-id="4192e-125">`New-Module` のような名前のコマンドを使って作成すると思われるかもしれませんが、</span><span class="sxs-lookup"><span data-stu-id="4192e-125">You're probably guessing with a command named something like `New-Module`.</span></span> <span data-ttu-id="4192e-126">それは間違っています。</span><span class="sxs-lookup"><span data-stu-id="4192e-126">Your assumption would be wrong.</span></span> <span data-ttu-id="4192e-127">PowerShell には `New-Module` という名前のコマンドがありますが、このコマンドによって作成されるのは動的モジュールで、スクリプト モジュールではありません。</span><span class="sxs-lookup"><span data-stu-id="4192e-127">While there is a command in PowerShell named `New-Module`, that command creates a dynamic module, not a script module.</span></span> <span data-ttu-id="4192e-128">必要なコマンドが見つかった、と思っても、必ずコマンドのヘルプを読んでください。</span><span class="sxs-lookup"><span data-stu-id="4192e-128">Always be sure to read the help for a command even when you think you've found the command you need.</span></span>

```powershell
help New-Module
```

```Output
NAME
    New-Module

SYNOPSIS
    Creates a new dynamic module that exists only in memory.

SYNTAX
    New-Module [-Name] <String> [-ScriptBlock] <ScriptBlock> [-ArgumentList <Object[]>]
    [-AsCustomObject] [-Cmdlet <String[]>] [-Function <String[]>] [-ReturnResult]
    [<CommonParameters>]

DESCRIPTION
    The New-Module cmdlet creates a dynamic module from a script block. The members of
    the dynamic module, such as functions and variables, are immediately available in
    the session and remain available until you close the session.

    Like static modules, by default, the cmdlets and functions in a dynamic module are
    exported and the variables and aliases are not. However, you can use the
    Export-ModuleMember cmdlet and the parameters of New-Module to override the defaults.

    You can also use the AsCustomObject parameter of New-Module to return the dynamic
    module as a custom object. The members of the modules, such as functions, are
    implemented as script methods of the custom object instead of being imported into
    the session.

    Dynamic modules exist only in memory, not on disk. Like all modules, the members of
    dynamic modules run in a private module scope that is a child of the global scope.
    Get-Module cannot get a dynamic module, but Get-Command can get the exported members.

    To make a dynamic module available to Get-Module , pipe a New-Module command to
    Import-Module, or pipe the module object that New-Module returns to Import-Module .
    This action adds the dynamic module to the Get-Module list, but it does not save the
    module to disk or make it persistent.

RELATED LINKS
    Online Version: http://go.microsoft.com/fwlink/?LinkId=821495
    Export-ModuleMember
    Get-Module
    Import-Module
    Remove-Module

REMARKS
    To see the examples, type: "get-help New-Module -examples".
    For more information, type: "get-help New-Module -detailed".
    For technical information, type: "get-help New-Module -full".
    For online help, type: "get-help New-Module -online"
```

<span data-ttu-id="4192e-129">前の章で、関数では承認されている動詞を使用する必要があり、そうしないとモジュールのインポート時に警告メッセージが生成されると言いました。</span><span class="sxs-lookup"><span data-stu-id="4192e-129">In the previous chapter, I mentioned that functions should use approved verbs otherwise they'll generate a warning message when the module is imported.</span></span> <span data-ttu-id="4192e-130">次のコードは、`New-Module` コマンドレットを使って、メモリで動的モジュールを作成しています。</span><span class="sxs-lookup"><span data-stu-id="4192e-130">The following code uses the `New-Module` cmdlet to create a dynamic module in memory.</span></span> <span data-ttu-id="4192e-131">このモジュールは、未承認の動詞に関する警告を示しています。</span><span class="sxs-lookup"><span data-stu-id="4192e-131">This module demonstrates the unapproved verb warning.</span></span>

```powershell
New-Module -Name MyModule -ScriptBlock {

    function Return-MrOsVersion {
        Get-CimInstance -ClassName Win32_OperatingSystem |
        Select-Object -Property @{label='OperatingSystem';expression={$_.Caption}}
    }

    Export-ModuleMember -Function Return-MrOsVersion

} | Import-Module
```

```Output
WARNING: The names of some imported commands from the module 'MyModule' include
unapproved verbs that might make them less discoverable. To find the commands with
unapproved verbs, run the Import-Module command again with the Verbose parameter. For a
list of approved verbs, type Get-Verb.
```

<span data-ttu-id="4192e-132">繰り返しになりますが、この例では `New-Module` コマンドレットが使用されましたが、これは PowerShell でスクリプト モジュールを作成するコマンドではありません。</span><span class="sxs-lookup"><span data-stu-id="4192e-132">Just to reiterate, although the `New-Module` cmdlet was used in the previous example, that's not the command for creating script modules in PowerShell.</span></span>

<span data-ttu-id="4192e-133">次の 2 つの関数を `MyScriptModule.psm1` という名前のファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="4192e-133">Save the following two functions in a file named `MyScriptModule.psm1`.</span></span>

```powershell
function Get-MrPSVersion {
    $PSVersionTable
}

function Get-MrComputerName {
    $env:COMPUTERNAME
}
```

<span data-ttu-id="4192e-134">関数のいずれかを呼び出してみます。</span><span class="sxs-lookup"><span data-stu-id="4192e-134">Try to call one of the functions.</span></span>

```powershell
Get-MrComputerName
```

```Output
Get-MrComputerName : The term 'Get-MrComputerName' is not recognized as the name of a
cmdlet, function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
At line:1 char:1
+ Get-MrComputerName
    + CategoryInfo          : ObjectNotFound: (Get-MrComputerName:String) [], CommandNot
   FoundException
    + FullyQualifiedErrorId : CommandNotFoundException
```

<span data-ttu-id="4192e-135">関数が見つからないというエラー メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="4192e-135">An error message is generated saying the function can't be found.</span></span> <span data-ttu-id="4192e-136">ここでも、前と同じように **Function** PSDrive を確認でき、そこに関数が存在しないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="4192e-136">You could also check the **Function** PSDrive just like before and you'll find that it doesn't exist there either.</span></span>

<span data-ttu-id="4192e-137">`Import-Module` コマンドレットを使用して、ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="4192e-137">You could manually import the file with the `Import-Module` cmdlet.</span></span>

```powershell
Import-Module C:\MyScriptModule.psm1
```

<span data-ttu-id="4192e-138">モジュールの自動読み込み機能は、PowerShell バージョン 3 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4192e-138">The module autoloading feature was introduced in PowerShell version 3.</span></span> <span data-ttu-id="4192e-139">モジュールの自動読み込みを利用するには、スクリプト モジュールを、`$env:PSModulePath` で指定された場所にある、`.PSM1` ファイルと同じ基本名を持つフォルダーに保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4192e-139">To take advantage of module autoloading, a script module needs to be saved in a folder with the same base name as the `.PSM1` file and in a location specified in `$env:PSModulePath`.</span></span>

```powershell
$env:PSModulePath
```

```Output
C:\Users\mike-ladm\Documents\WindowsPowerShell\Modules;C:\Program Files\WindowsPowerShell\
Modules;C:\Windows\system32\WindowsPowerShell\v1.0\Modules;C:\Program Files (x86)\Microsof
t SQL Server\130\Tools\PowerShell\Modules\
```

<span data-ttu-id="4192e-140">読みにくい結果が出力されます。</span><span class="sxs-lookup"><span data-stu-id="4192e-140">The results are difficult to read.</span></span> <span data-ttu-id="4192e-141">それぞれのパスがセミコロンで区切られているので、結果を分割して、パスごとに改行します。</span><span class="sxs-lookup"><span data-stu-id="4192e-141">Since the paths are separated by a semicolon, you can split the results to return each path on a separate line.</span></span> <span data-ttu-id="4192e-142">これにより、読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="4192e-142">This makes them easier to read.</span></span>

```powershell
$env:PSModulePath -split ';'
```

```Output
C:\Users\mike-ladm\Documents\WindowsPowerShell\Modules
C:\Program Files\WindowsPowerShell\Modules
C:\Windows\system32\WindowsPowerShell\v1.0\Modules
C:\Program Files (x86)\Microsoft SQL Server\130\Tools\PowerShell\Modules\
```

<span data-ttu-id="4192e-143">一覧に示されている最初の 3 つは、既定のパスです。</span><span class="sxs-lookup"><span data-stu-id="4192e-143">The first three paths in the list are the default.</span></span> <span data-ttu-id="4192e-144">SQL Server Management Studio がインストールされている場合は、最後のパスが追加されます。</span><span class="sxs-lookup"><span data-stu-id="4192e-144">When SQL Server Management Studio was installed, it added the last path.</span></span> <span data-ttu-id="4192e-145">モジュールの自動読み込みを機能させるには、`MyScriptModule.psm1` ファイルを、これらのパスのいずれかにある `MyScriptModule` という名前のフォルダーに直接配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4192e-145">For module autoloading to work, the `MyScriptModule.psm1` file needs to be located in a folder named `MyScriptModule` directly inside one of those paths.</span></span>

<span data-ttu-id="4192e-146">慌てないでください。</span><span class="sxs-lookup"><span data-stu-id="4192e-146">Not so fast.</span></span> <span data-ttu-id="4192e-147">私の現在のユーザー パスは、この一覧の先頭のパスではありません。</span><span class="sxs-lookup"><span data-stu-id="4192e-147">For me, my current user path isn't the first one in the list.</span></span> <span data-ttu-id="4192e-148">私が Windows にログインするときのユーザーは、PowerShell を実行するときに使うユーザーとは異なるため、このパスはほとんど使用しません。</span><span class="sxs-lookup"><span data-stu-id="4192e-148">I almost never use that path since I log into Windows with a different user than the one I use to run PowerShell.</span></span> <span data-ttu-id="4192e-149">つまり、そのフォルダーは、通常のドキュメント フォルダーには存在しません。</span><span class="sxs-lookup"><span data-stu-id="4192e-149">That means it's not located in my normal Documents folder.</span></span>

<span data-ttu-id="4192e-150">2 番目のパスは、**AllUsers** パスです。</span><span class="sxs-lookup"><span data-stu-id="4192e-150">The second path is the **AllUsers** path.</span></span> <span data-ttu-id="4192e-151">この場所には、私のすべてのモジュールが格納されます。</span><span class="sxs-lookup"><span data-stu-id="4192e-151">This is the location where I store all of my modules.</span></span>

<span data-ttu-id="4192e-152">3 番目のパスは `C:\Windows\System32` の下にあります。</span><span class="sxs-lookup"><span data-stu-id="4192e-152">The third path is underneath `C:\Windows\System32`.</span></span> <span data-ttu-id="4192e-153">この場所は、オペレーティング システム フォルダー内にあるため、ここにモジュールを格納する必要があるのは Microsoft だけです。</span><span class="sxs-lookup"><span data-stu-id="4192e-153">Only Microsoft should be storing modules in that location since it resides within the operating systems folder.</span></span>

<span data-ttu-id="4192e-154">`.PSM1` ファイルが正しいパスに配置されると、そのコマンドの 1 つが呼び出されたときに、モジュールは自動的に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="4192e-154">Once the `.PSM1` file is located in the correct path, the module will load automatically when one of its commands is called.</span></span>

## <a name="module-manifests"></a><span data-ttu-id="4192e-155">モジュール マニフェスト</span><span class="sxs-lookup"><span data-stu-id="4192e-155">Module Manifests</span></span>

<span data-ttu-id="4192e-156">すべてのモジュールにモジュール マニフェストが必要です。</span><span class="sxs-lookup"><span data-stu-id="4192e-156">All modules should have a module manifest.</span></span> <span data-ttu-id="4192e-157">モジュール マニフェストには、モジュールに関するメタデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4192e-157">A module manifest contains metadata about your module.</span></span>
<span data-ttu-id="4192e-158">モジュール マニフェスト ファイルのファイル名拡張子は `.PSD1` です。</span><span class="sxs-lookup"><span data-stu-id="4192e-158">The file extension for a module manifest file is `.PSD1`.</span></span> <span data-ttu-id="4192e-159">`.PSD1` 拡張子のファイルすべてがモジュール マニフェストであるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="4192e-159">Not all files with a `.PSD1` extension are module manifests.</span></span> <span data-ttu-id="4192e-160">この拡張子は、DSC 構成の環境部分の格納などの用途にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="4192e-160">They can also be used for things such as storing the environmental portion of a DSC configuration.</span></span> <span data-ttu-id="4192e-161">`New-ModuleManifest` を使用すると、モジュール マニフェストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4192e-161">`New-ModuleManifest` is used to create a module manifest.</span></span> <span data-ttu-id="4192e-162">必須の値は **Path** のみですが、</span><span class="sxs-lookup"><span data-stu-id="4192e-162">**Path** is the only value that's required.</span></span> <span data-ttu-id="4192e-163">**RootModule** が指定されていないと、モジュールは機能しません。</span><span class="sxs-lookup"><span data-stu-id="4192e-163">However, the module won't work if **RootModule** isn't specified.</span></span> <span data-ttu-id="4192e-164">PowerShellGet を使用してモジュールを NuGet リポジトリにアップロードする場合に備えて、**Author** と **Description** を指定することをお勧めします。そのシナリオでは、この値が必要になります。</span><span class="sxs-lookup"><span data-stu-id="4192e-164">It's a good idea to specify **Author** and **Description** in case you decide to upload your module to a NuGet repository with PowerShellGet since those values are required in that scenario.</span></span>

<span data-ttu-id="4192e-165">マニフェストのないモジュールのバージョンは 0.0 です。</span><span class="sxs-lookup"><span data-stu-id="4192e-165">The version of a module without a manifest is 0.0.</span></span> <span data-ttu-id="4192e-166">これにより、モジュールにマニフェストがないことは一目瞭然です。</span><span class="sxs-lookup"><span data-stu-id="4192e-166">This is a dead giveaway that the module doesn't have a manifest.</span></span>

```powershell
Get-Module -Name MyScriptModule
```

```Output
ModuleType Version    Name                                ExportedCommands
---------- -------    ----                                ----------------
Script     0.0        myscriptmodule                      {Get-MrComputerName, Get-MrP...
```

<span data-ttu-id="4192e-167">モジュール マニフェストは、すべての推奨情報を使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="4192e-167">The module manifest can be created with all of the recommended information.</span></span>

```powershell
New-ModuleManifest -Path $env:ProgramFiles\WindowsPowerShell\Modules\MyScriptModule\MyScriptModule.psd1 -RootModule MyScriptModule -Author 'Mike F Robbins' -Description 'MyScriptModule' -CompanyName 'mikefrobbins.com'
```

<span data-ttu-id="4192e-168">最初に作成したモジュール マニフェストに、この情報のいずれかが欠落していた場合は、`Update-ModuleManifest` を使って後で追加または更新できます。</span><span class="sxs-lookup"><span data-stu-id="4192e-168">If any of this information is missed during the initial creation of the module manifest, it can be added or updated later using `Update-ModuleManifest`.</span></span> <span data-ttu-id="4192e-169">既に作成されているマニフェストについては、`New-ModuleManifest` を使って再作成しないでください。再作成すると、GUID が変更されてしまいます。</span><span class="sxs-lookup"><span data-stu-id="4192e-169">Don't recreate the manifest using `New-ModuleManifest` once it's already created because the GUID will change.</span></span>

## <a name="defining-public-and-private-functions"></a><span data-ttu-id="4192e-170">パブリック関数とプライベート関数の定義</span><span class="sxs-lookup"><span data-stu-id="4192e-170">Defining Public and Private Functions</span></span>

<span data-ttu-id="4192e-171">ご自身のヘルパー関数をプライベートにして、モジュール内の他の関数からのみアクセスできるようにしたいことがあります。</span><span class="sxs-lookup"><span data-stu-id="4192e-171">You may have helper functions that you may want to be private and only accessible by other functions within the module.</span></span> <span data-ttu-id="4192e-172">モジュールのユーザーがアクセスできるようにするつもりはありません。</span><span class="sxs-lookup"><span data-stu-id="4192e-172">They are not intended to be accessible to users of your module.</span></span> <span data-ttu-id="4192e-173">これを実現する方法はいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="4192e-173">There are a couple of different ways to accomplish this.</span></span>

<span data-ttu-id="4192e-174">ベスト プラクティスに従っておらず、`.PSM1` ファイルしかない場合、`Export-ModuleMember` コマンドレットを使用する以外の方法はありません。</span><span class="sxs-lookup"><span data-stu-id="4192e-174">If you're not following the best practices and only have a `.PSM1` file, then your only option is to use the `Export-ModuleMember` cmdlet.</span></span>

```powershell
function Get-MrPSVersion {
    $PSVersionTable
}

function Get-MrComputerName {
    $env:COMPUTERNAME
}

Export-ModuleMember -Function Get-MrPSVersion
```

<span data-ttu-id="4192e-175">この例では、モジュールのユーザーは、`Get-MrPSVersion` 関数にのみアクセスできます。`Get-MrComputerName` 関数は、モジュール自体にある他の関数が使用できます。</span><span class="sxs-lookup"><span data-stu-id="4192e-175">In the previous example, only the `Get-MrPSVersion` function is available to the users of your module, but the `Get-MrComputerName` function is available to other functions within the module itself.</span></span>

```powershell
Get-Command -Module MyScriptModule

CommandType     Name                        Version    Source
-----------     ----                        -------    ------
Function        Get-MrPSVersion             1.0        MyScript...
```

<span data-ttu-id="4192e-176">モジュール マニフェストをご自身のモジュールに追加した場合は (追加する必要がある場合は)、モジュール マニフェストの **FunctionsToExport**  セクションで、エクスポートする関数を個別に指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4192e-176">If you've added a module manifest to your module (and you should), then I recommend specifying the individual functions you want to export in the **FunctionsToExport** section of the module manifest.</span></span>

```powershell
FunctionsToExport = 'Get-MrPSVersion'
```

<span data-ttu-id="4192e-177">`.PSM1` ファイルの `Export-ModuleMember` と、モジュール マニフェストの **FunctionsToExport** セクションの両方を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4192e-177">It's not necessary to use both `Export-ModuleMember` in the `.PSM1` file and the **FunctionsToExport** section of the module manifest.</span></span> <span data-ttu-id="4192e-178">どちらか一方で十分です。</span><span class="sxs-lookup"><span data-stu-id="4192e-178">One or the other is sufficient.</span></span>

## <a name="summary"></a><span data-ttu-id="4192e-179">まとめ</span><span class="sxs-lookup"><span data-stu-id="4192e-179">Summary</span></span>

<span data-ttu-id="4192e-180">この章では、PowerShell で関数をスクリプト モジュールに変換する方法を学習しました。</span><span class="sxs-lookup"><span data-stu-id="4192e-180">In this chapter you've learned how to turn your functions into a script module in PowerShell.</span></span> <span data-ttu-id="4192e-181">また、スクリプト モジュールのモジュール マニフェストの作成など、スクリプト モジュール作成のベスト プラクティスについてもいくつか学びました。</span><span class="sxs-lookup"><span data-stu-id="4192e-181">You've also leaned some of the best practices for creating script modules such as creating a module manifest for your script module.</span></span>

## <a name="review"></a><span data-ttu-id="4192e-182">確認</span><span class="sxs-lookup"><span data-stu-id="4192e-182">Review</span></span>

1. <span data-ttu-id="4192e-183">PowerShell でスクリプト モジュールを作成するには、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="4192e-183">How do you create a script module in PowerShell?</span></span>
1. <span data-ttu-id="4192e-184">承認されている動詞を使用することが関数にとって重要なのは、なぜですか。</span><span class="sxs-lookup"><span data-stu-id="4192e-184">Why is it important for your functions to use an approved verb?</span></span>
1. <span data-ttu-id="4192e-185">PowerShell でモジュール マニフェストを作成するには、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="4192e-185">How do you create a module manifest in PowerShell?</span></span>
1. <span data-ttu-id="4192e-186">モジュールから特定の関数のみをエクスポートする 2 つのオプションは何ですか。</span><span class="sxs-lookup"><span data-stu-id="4192e-186">What are the two options for exporting only certain functions from your module?</span></span>
1. <span data-ttu-id="4192e-187">コマンドが呼び出されたときのモジュールの自動読み込みには何が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="4192e-187">What is required for your modules to load automatically when a command is called?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="4192e-188">推奨トピック</span><span class="sxs-lookup"><span data-stu-id="4192e-188">Recommended Reading</span></span>

- <span data-ttu-id="4192e-189">[PowerShell スクリプト モジュールとモジュール マニフェストを作成する方法][]</span><span class="sxs-lookup"><span data-stu-id="4192e-189">[How to Create PowerShell Script Modules and Module Manifests][]</span></span>
- <span data-ttu-id="4192e-190">[about_Modules][]</span><span class="sxs-lookup"><span data-stu-id="4192e-190">[about_Modules][]</span></span>
- <span data-ttu-id="4192e-191">[New-ModuleManifest][]</span><span class="sxs-lookup"><span data-stu-id="4192e-191">[New-ModuleManifest][]</span></span>
- <span data-ttu-id="4192e-192">[Export-ModuleMember][]</span><span class="sxs-lookup"><span data-stu-id="4192e-192">[Export-ModuleMember][]</span></span>

<!-- link references -->
[PowerShell スクリプト モジュールとモジュール マニフェストを作成する方法]: https://mikefrobbins.com/2013/07/04/how-to-create-powershell-script-modules-and-module-manifests/
[How to Create PowerShell Script Modules and Module Manifests]: https://mikefrobbins.com/2013/07/04/how-to-create-powershell-script-modules-and-module-manifests/
[about_Modules]: /powershell/module/microsoft.powershell.core/about/about_modules
[New-ModuleManifest]: /powershell/module/microsoft.powershell.core/new-modulemanifest
[Export-ModuleMember]: /powershell/module/microsoft.powershell.core/export-modulemember
