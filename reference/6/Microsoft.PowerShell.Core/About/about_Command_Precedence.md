---
description: PowerShell が実行するコマンドを決定する方法について説明します。
keywords: powershell,コマンドレット
ms.date: 02/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_command_precedence?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Command_Precedence
ms.openlocfilehash: f777d8b627288dff37a166f6819d36d10ed5db37
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221768"
---
# <a name="about-command-precedence"></a><span data-ttu-id="a934c-104">コマンドの優先順位について</span><span class="sxs-lookup"><span data-stu-id="a934c-104">About Command Precedence</span></span>

## <a name="short-description"></a><span data-ttu-id="a934c-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="a934c-105">Short description</span></span>
<span data-ttu-id="a934c-106">PowerShell が実行するコマンドを決定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a934c-106">Describes how PowerShell determines which command to run.</span></span>

## <a name="long-description"></a><span data-ttu-id="a934c-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="a934c-107">Long description</span></span>

<span data-ttu-id="a934c-108">コマンドの優先順位は、セッションに同じ名前の複数のコマンドが含まれている場合に、どのコマンドを実行するかを PowerShell が決定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a934c-108">Command precedence describes how PowerShell determines which command to run when a session contains more than one command with the same name.</span></span> <span data-ttu-id="a934c-109">セッション内のコマンドは、同じ名前のコマンドで非表示にしたり置き換えたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a934c-109">Commands within a session can be hidden or replaced by commands with the same name.</span></span> <span data-ttu-id="a934c-110">この記事では、非表示のコマンドを実行する方法と、コマンド名の競合を回避する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a934c-110">This article shows you how to run hidden commands and how to avoid command-name conflicts.</span></span>

## <a name="command-precedence"></a><span data-ttu-id="a934c-111">コマンドの優先順位</span><span class="sxs-lookup"><span data-stu-id="a934c-111">Command precedence</span></span>

<span data-ttu-id="a934c-112">PowerShell セッションに同じ名前の複数のコマンドが含まれている場合、PowerShell は次の規則を使用して実行するコマンドを決定します。</span><span class="sxs-lookup"><span data-stu-id="a934c-112">When a PowerShell session includes more than one command that has the same name, PowerShell determines which command to run by using the following rules.</span></span>

<span data-ttu-id="a934c-113">コマンドのパスを指定すると、PowerShell はパスで指定された場所でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a934c-113">If you specify the path to a command, PowerShell runs the command at the location specified by the path.</span></span>

<span data-ttu-id="a934c-114">たとえば、次のコマンドでは、"C: FindDocs.ps1" ディレクトリ内のスクリプトが実行され \\ ます。</span><span class="sxs-lookup"><span data-stu-id="a934c-114">For example, the following command runs the FindDocs.ps1 script in the "C:\\TechDocs" directory:</span></span>

```
C:\TechDocs\FindDocs.ps1
```

<span data-ttu-id="a934c-115">セキュリティ機能として、PowerShell では、コマンドが Path 環境変数に記載されているパスに配置されている `$env:path` か、スクリプトファイルへのパスを指定していない限り、powershell スクリプトなどの実行可能 (ネイティブ) コマンドは実行されません。</span><span class="sxs-lookup"><span data-stu-id="a934c-115">As a security feature, PowerShell does not run executable (native) commands, including PowerShell scripts, unless the command is located in a path that is listed in the Path environment variable `$env:path` or unless you specify the path to the script file.</span></span>

<span data-ttu-id="a934c-116">現在のディレクトリにあるスクリプトを実行するには、完全なパスを指定するか、 `.\` 現在のディレクトリを表すドットを入力します。</span><span class="sxs-lookup"><span data-stu-id="a934c-116">To run a script that is in the current directory, specify the full path, or type a dot `.\` to represent the current directory.</span></span>

<span data-ttu-id="a934c-117">たとえば、現在のディレクトリで FindDocs.ps1 ファイルを実行するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a934c-117">For example, to run the FindDocs.ps1 file in the current directory, type:</span></span>

```
.\FindDocs.ps1
```

### <a name="using-wildcards-in-execution"></a><span data-ttu-id="a934c-118">実行でのワイルドカードの使用</span><span class="sxs-lookup"><span data-stu-id="a934c-118">Using wildcards in execution</span></span>

<span data-ttu-id="a934c-119">コマンドの実行時には、ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a934c-119">You may use wildcards in command execution.</span></span> <span data-ttu-id="a934c-120">ワイルドカード文字の使用は *グロビング* とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a934c-120">Using wildcard characters is also known as *globbing*.</span></span>

<span data-ttu-id="a934c-121">PowerShell は、リテラルが一致する前に、ワイルドカードと一致するファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="a934c-121">PowerShell executes a file that has a wildcard match, before a literal match.</span></span>

<span data-ttu-id="a934c-122">たとえば、次のファイルを含むディレクトリを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="a934c-122">For example, consider a directory with the following files:</span></span>

```
Get-ChildItem C:\temp\test


    Directory: C:\temp\test


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        5/20/2019   2:29 PM             28 a.ps1
-a----        5/20/2019   2:29 PM             28 [a1].ps1
```

<span data-ttu-id="a934c-123">両方のスクリプトファイルの内容は同じ `$MyInvocation.MyCommand.Path` です。</span><span class="sxs-lookup"><span data-stu-id="a934c-123">Both script files have the same content: `$MyInvocation.MyCommand.Path`.</span></span>
<span data-ttu-id="a934c-124">このコマンドは、呼び出されるスクリプトの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="a934c-124">This command displays the name of the script that is invoked.</span></span>

<span data-ttu-id="a934c-125">を実行すると `[a1].ps1` 、 `a.ps1` ファイルがリテラル一致であってもファイルは実行され `[a1].ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="a934c-125">When you run `[a1].ps1`, the file `a.ps1` is executed even though the file `[a1].ps1` is a literal match.</span></span>

```powershell
C:\temp\test\[a1].ps1
```

```Output
C:\temp\test\a.ps1
```

<span data-ttu-id="a934c-126">次に、ファイルを削除 `a.ps1` し、もう一度実行してみましょう。</span><span class="sxs-lookup"><span data-stu-id="a934c-126">Now let's delete the `a.ps1` file and attempt to run it again.</span></span>

```powershell
Remove-Item C:\temp\test\a.ps1
C:\temp\test\[a1].ps1
```

```Output
C:\temp\test\[a1].ps1
```

<span data-ttu-id="a934c-127">`[a1].ps1`リテラル一致がそのワイルドカードパターンと一致する唯一のファイルであるため、この時点で実行される出力から確認できます。</span><span class="sxs-lookup"><span data-stu-id="a934c-127">You can see from the output that `[a1].ps1` runs this time because the literal match is the only file match for that wildcard pattern.</span></span>

<span data-ttu-id="a934c-128">PowerShell でのワイルドカードの使用方法の詳細については、「 [about_Wildcards](about_Wildcards.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a934c-128">For more information about how PowerShell uses wildcards, see [about_Wildcards](about_Wildcards.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a934c-129">検索を相対パスに制限するには、スクリプト名の前にパスを付ける必要があり `.\` ます。</span><span class="sxs-lookup"><span data-stu-id="a934c-129">To limit the search to a relative path, you must prefix the script name with the `.\` path.</span></span> <span data-ttu-id="a934c-130">これにより、その相対パス内のファイルに対するコマンドの検索が制限されます。</span><span class="sxs-lookup"><span data-stu-id="a934c-130">This limits the search for commands to files in that relative path.</span></span> <span data-ttu-id="a934c-131">このプレフィックスがないと、他の PowerShell 構文が競合する可能性があり、ファイルが確実に検出されることはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="a934c-131">Without this prefix, other PowerShell syntax may conflict and there are few guarantees that the file will be found.</span></span>

<span data-ttu-id="a934c-132">パスを指定しない場合、PowerShell は、現在のセッションに読み込まれたすべての項目に対してコマンドを実行するときに、次の優先順位を使用します。</span><span class="sxs-lookup"><span data-stu-id="a934c-132">If you do not specify a path, PowerShell uses the following precedence order when it runs commands for all items loaded in the current session:</span></span>

  1. <span data-ttu-id="a934c-133">エイリアス</span><span class="sxs-lookup"><span data-stu-id="a934c-133">Alias</span></span>
  2. <span data-ttu-id="a934c-134">機能</span><span class="sxs-lookup"><span data-stu-id="a934c-134">Function</span></span>
  3. <span data-ttu-id="a934c-135">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="a934c-135">Cmdlet</span></span>
  4. <span data-ttu-id="a934c-136">外部実行可能ファイル (プログラムと PowerShell 以外のスクリプト)</span><span class="sxs-lookup"><span data-stu-id="a934c-136">External executable files (programs and non-PowerShell scripts)</span></span>

<span data-ttu-id="a934c-137">したがって、「help」と入力すると、PowerShell はまずという名前のエイリアス、次にという名前の関数、最後にという名前のコマンドレットを検索し `help` `Help` `Help` ます。</span><span class="sxs-lookup"><span data-stu-id="a934c-137">Therefore, if you type "help", PowerShell first looks for an alias named `help`, then a function named `Help`, and finally a cmdlet named `Help`.</span></span> <span data-ttu-id="a934c-138">最初に検出された項目が実行され `help` ます。</span><span class="sxs-lookup"><span data-stu-id="a934c-138">It runs the first `help` item that it finds.</span></span>

<span data-ttu-id="a934c-139">たとえば、という名前のコマンドレットと関数がセッションに含まれている場合、 `Get-Map` `Get-Map` PowerShell によって関数が実行されます。</span><span class="sxs-lookup"><span data-stu-id="a934c-139">For example, if your session contains a cmdlet and a function, both named `Get-Map`, when you type `Get-Map`, PowerShell runs the function.</span></span>

> [!NOTE]
> <span data-ttu-id="a934c-140">これは、読み込まれたコマンドにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="a934c-140">This only applies to loaded commands.</span></span> <span data-ttu-id="a934c-141">`build` `build` `Invoke-Build` 現在のセッションに読み込まれていないモジュール内にという名前の関数の実行可能ファイルとエイリアスがある場合は、PowerShell によって実行可能ファイルが実行され `build` ます。</span><span class="sxs-lookup"><span data-stu-id="a934c-141">If there is a `build` executable and an Alias `build` for a function with the name of `Invoke-Build` inside a module that is not loaded into the current session, PowerShell runs the `build` executable instead.</span></span> <span data-ttu-id="a934c-142">この場合、モジュールが外部の実行可能ファイルを検出しても、モジュールは自動的に読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="a934c-142">It does not auto-load modules if it finds the external executable in this case.</span></span> <span data-ttu-id="a934c-143">これは、指定された名前のエイリアス、関数、またはコマンドレットが呼び出され、そのモジュールの自動読み込みをトリガーする外部実行可能ファイルが見つからなかった場合にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="a934c-143">It is only when no external executable is found that an alias, function, or cmdlet with the given name is invoked, thereby triggering auto-loading of its module.</span></span>

<span data-ttu-id="a934c-144">セッションに同じ種類の同じ名前の項目が含まれている場合、PowerShell は新しい項目を実行します。</span><span class="sxs-lookup"><span data-stu-id="a934c-144">When the session contains items of the same type that have the same name, PowerShell runs the newer item.</span></span>

<span data-ttu-id="a934c-145">たとえば、モジュールから別のコマンドレットをインポートする場合、 `Get-Date` 「」と入力すると、PowerShell によって、インポートされた `Get-Date` バージョンがネイティブのもので実行されます。</span><span class="sxs-lookup"><span data-stu-id="a934c-145">For example, if you import another `Get-Date` cmdlet from a module, when you type `Get-Date`, PowerShell runs the imported version over the native one.</span></span>

## <a name="hidden-and-replaced-items"></a><span data-ttu-id="a934c-146">非表示の項目と置換された項目</span><span class="sxs-lookup"><span data-stu-id="a934c-146">Hidden and replaced items</span></span>

<span data-ttu-id="a934c-147">これらのルールの結果として、同じ名前のアイテムでアイテムを置換または非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a934c-147">As a result of these rules, items can be replaced or hidden by items with the same name.</span></span>

<span data-ttu-id="a934c-148">項目の名前をモジュールまたはスナップインの名前に修飾することによって、元の項目にアクセスできる場合は、項目が "非表示" または "影付き" になります。</span><span class="sxs-lookup"><span data-stu-id="a934c-148">Items are "hidden" or "shadowed" if you can still access the original item, such as by qualifying the item name with a module or snap-in name.</span></span>

<span data-ttu-id="a934c-149">たとえば、セッションのコマンドレットと同じ名前の関数をインポートした場合、コマンドレットはスナップインまたはモジュールからインポートされたため、非表示になります (ただし、置き換えられません)。</span><span class="sxs-lookup"><span data-stu-id="a934c-149">For example, if you import a function that has the same name as a cmdlet in the session, the cmdlet is hidden (but not replaced) because it was imported from a snap-in or module.</span></span>

<span data-ttu-id="a934c-150">元の項目にアクセスできなくなった場合、項目は "置換" または "上書き" されます。</span><span class="sxs-lookup"><span data-stu-id="a934c-150">Items are "replaced" or "overwritten" if you can no longer access the original item.</span></span>

<span data-ttu-id="a934c-151">たとえば、セッションの変数と同じ名前の変数をインポートすると、元の変数は置き換えられ、アクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="a934c-151">For example, if you import a variable that has the same name as a variable in the session, the original variable is replaced and is no longer accessible.</span></span>
<span data-ttu-id="a934c-152">モジュール名を使用して変数を修飾することはできません。</span><span class="sxs-lookup"><span data-stu-id="a934c-152">You cannot qualify a variable with a module name.</span></span>

<span data-ttu-id="a934c-153">また、コマンドラインで関数を入力し、同じ名前の関数をインポートすると、元の関数が置き換えられ、アクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="a934c-153">Also, if you type a function at the command line and then import a function with the same name, the original function is replaced and is no longer accessible.</span></span>

### <a name="finding-hidden-commands"></a><span data-ttu-id="a934c-154">非表示のコマンドの検索</span><span class="sxs-lookup"><span data-stu-id="a934c-154">Finding hidden commands</span></span>

<span data-ttu-id="a934c-155">[Get コマンド](xref:Microsoft.PowerShell.Core.Get-Command)レットの **all** パラメーターは、指定された名前を持つすべてのコマンドを取得します (非表示にしたり置き換えたりする場合でも)。</span><span class="sxs-lookup"><span data-stu-id="a934c-155">The **All** parameter of the [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command) cmdlet gets all commands with the specified name, even if they are hidden or replaced.</span></span> <span data-ttu-id="a934c-156">PowerShell 3.0 以降では、既定では、 `Get-Command` コマンド名を入力したときに実行されるコマンドのみが取得されます。</span><span class="sxs-lookup"><span data-stu-id="a934c-156">Beginning in PowerShell 3.0, by default, `Get-Command` gets only the commands that run when you type the command name.</span></span>

<span data-ttu-id="a934c-157">次の例では、セッションに `Get-Date` 関数と [Get Date](xref:Microsoft.PowerShell.Utility.Get-Date) コマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a934c-157">In the following examples, the session includes a `Get-Date` function and a [Get-Date](xref:Microsoft.PowerShell.Utility.Get-Date) cmdlet.</span></span>

<span data-ttu-id="a934c-158">次のコマンドは、を入力したときに実行されるコマンドを取得し `Get-Date` `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="a934c-158">The following command gets the `Get-Date` command that runs when you type `Get-Date`.</span></span>

```powershell
Get-Command Get-Date
```

```output
CommandType     Name                      ModuleName
-----------     ----                      ----------
Function        Get-Date
```

<span data-ttu-id="a934c-159">次のコマンドでは、 **all** パラメーターを使用してすべてのコマンドを取得し `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="a934c-159">The following command uses the **All** parameter to get all `Get-Date` commands.</span></span>

```powershell
Get-Command Get-Date -All
```

```output
CommandType     Name                      ModuleName
-----------     ----                      ----------
Function        Get-Date
Cmdlet          Get-Date                  Microsoft.PowerShell.Utility
```

### <a name="running-hidden-commands"></a><span data-ttu-id="a934c-160">非表示のコマンドの実行</span><span class="sxs-lookup"><span data-stu-id="a934c-160">Running hidden commands</span></span>

<span data-ttu-id="a934c-161">コマンドを、同じ名前を持つ他のコマンドと区別する項目プロパティを指定することで、特定のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a934c-161">You can run particular commands by specifying item properties that distinguish the command from other commands that might have the same name.</span></span> <span data-ttu-id="a934c-162">このメソッドを使用して任意のコマンドを実行できますが、特に非表示のコマンドを実行する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="a934c-162">You can use this method to run any command, but it is especially useful for running hidden commands.</span></span>

#### <a name="qualified-names"></a><span data-ttu-id="a934c-163">修飾名</span><span class="sxs-lookup"><span data-stu-id="a934c-163">Qualified names</span></span>

<span data-ttu-id="a934c-164">コマンドレットのモジュール修飾名を使用すると、同じ名前の項目によって非表示になっているコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a934c-164">Using the module-qualified name of a cmdlet allows you to run commands hidden by an item with the same name.</span></span> <span data-ttu-id="a934c-165">たとえば、コマンドレットを実行するには、 `Get-Date` モジュール名に " **Microsoft. PowerShell. ユーティリティ** " を付けます。</span><span class="sxs-lookup"><span data-stu-id="a934c-165">For example, you can run the `Get-Date` cmdlet by qualifying it with its module name **Microsoft.PowerShell.Utility**.</span></span>

<span data-ttu-id="a934c-166">この推奨される方法は、配布するスクリプトを記述するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="a934c-166">Use this preferred method when writing scripts that you intend to distribute.</span></span> <span data-ttu-id="a934c-167">スクリプトが実行されるセッションに存在する可能性があるコマンドを予測することはできません。</span><span class="sxs-lookup"><span data-stu-id="a934c-167">You cannot predict which commands might be present in the session in which the script runs.</span></span>

```powershell
New-Alias -Name "Get-Date" -Value "Get-ChildItem"
Microsoft.PowerShell.Utility\Get-Date
```

```output
Tuesday, September 4, 2018 8:17:25 AM
```

<span data-ttu-id="a934c-168">`New-Map`モジュールによって追加されたコマンドを実行するには `MapFunctions` 、モジュール修飾名を使用します。</span><span class="sxs-lookup"><span data-stu-id="a934c-168">To run a `New-Map` command that was added by the `MapFunctions` module, use its module-qualified name:</span></span>

```powershell
MapFunctions\New-Map
```

<span data-ttu-id="a934c-169">コマンドがインポートされたモジュールを見つけるには、コマンドの **ModuleName** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="a934c-169">To find the module from which a command was imported, use the **ModuleName** property of commands.</span></span>

```
(Get-Command <command-name>).ModuleName
```

<span data-ttu-id="a934c-170">たとえば、コマンドレットのソースを検索するには、次のように `Get-Date` 入力します。</span><span class="sxs-lookup"><span data-stu-id="a934c-170">For example, to find the source of the `Get-Date` cmdlet, type:</span></span>

```powershell
(Get-Command Get-Date).ModuleName
```

```output
Microsoft.PowerShell.Utility
```

> [!NOTE]
> <span data-ttu-id="a934c-171">変数または別名を修飾することはできません。</span><span class="sxs-lookup"><span data-stu-id="a934c-171">You cannot qualify variables or aliases.</span></span>

#### <a name="call-operator"></a><span data-ttu-id="a934c-172">Call 演算子</span><span class="sxs-lookup"><span data-stu-id="a934c-172">Call operator</span></span>

<span data-ttu-id="a934c-173">また、演算子を使用して、 `Call` `&` [get-childitem](xref:Microsoft.PowerShell.Management.Get-ChildItem) (エイリアスは "dir") `Get-Command` または [get-Module](xref:Microsoft.PowerShell.Core.Get-Module)の呼び出しと組み合わせて、非表示のコマンドを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="a934c-173">You can also use the `Call` operator `&` to run hidden commands by combining it with a call to [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) (the alias is "dir"), `Get-Command` or [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module).</span></span>

<span data-ttu-id="a934c-174">呼び出し演算子は、子スコープ内で文字列とスクリプトブロックを実行します。</span><span class="sxs-lookup"><span data-stu-id="a934c-174">The call operator executes strings and script blocks in a child scope.</span></span> <span data-ttu-id="a934c-175">詳細については、「 [about_Operators](about_Operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a934c-175">For more information, see [about_Operators](about_Operators.md).</span></span>

<span data-ttu-id="a934c-176">たとえば、という名前のエイリアスによって非表示になっているという名前の関数がある場合は、 `Map` `Map` 次のコマンドを使用して関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="a934c-176">For example, if you have a function named `Map` that is hidden by an alias named `Map`, use the following command to run the function.</span></span>

```powershell
&(Get-Command -Name Map -CommandType Function)
```

<span data-ttu-id="a934c-177">or</span><span class="sxs-lookup"><span data-stu-id="a934c-177">or</span></span>

```powershell
&(dir Function:\map)
```

<span data-ttu-id="a934c-178">また、非表示のコマンドを変数に保存して、実行しやすくすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a934c-178">You can also save your hidden command in a variable to make it easier to run.</span></span>

<span data-ttu-id="a934c-179">たとえば、次のコマンドは、 `Map` 関数を変数に保存 `$myMap` し、演算子を使用し `Call` て実行します。</span><span class="sxs-lookup"><span data-stu-id="a934c-179">For example, the following command saves the `Map` function in the `$myMap` variable and then uses the `Call` operator to run it.</span></span>

```powershell
$myMap = (Get-Command -Name map -CommandType function)
&($myMap)
```

### <a name="replaced-items"></a><span data-ttu-id="a934c-180">置換された項目</span><span class="sxs-lookup"><span data-stu-id="a934c-180">Replaced items</span></span>

<span data-ttu-id="a934c-181">"置き換えられた" 項目とは、アクセスできなくなった項目のことです。</span><span class="sxs-lookup"><span data-stu-id="a934c-181">A "replaced" item is one that you can no longer access.</span></span> <span data-ttu-id="a934c-182">モジュールまたはスナップインから同じ名前の項目をインポートすることによって、項目を置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="a934c-182">You can replace items by importing items of the same name from a module or snap-in.</span></span>

<span data-ttu-id="a934c-183">たとえば、 `Get-Map` セッションに関数を入力し、という名前の関数をインポートすると、 `Get-Map` 元の関数が置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="a934c-183">For example, if you type a `Get-Map` function in your session, and you import a function called `Get-Map`, it replaces the original function.</span></span> <span data-ttu-id="a934c-184">現在のセッションでは取得できません。</span><span class="sxs-lookup"><span data-stu-id="a934c-184">You cannot retrieve it in the current session.</span></span>

<span data-ttu-id="a934c-185">変数とエイリアスは、呼び出し演算子または修飾名を使用して実行することはできないため、非表示にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a934c-185">Variables and aliases cannot be hidden because you cannot use a call operator or a qualified name to run them.</span></span> <span data-ttu-id="a934c-186">モジュールまたはスナップインから変数とエイリアスをインポートすると、セッションの変数は同じ名前で置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="a934c-186">When you import variables and aliases from a module or snap-in, they replace variables in the session with the same name.</span></span>

### <a name="avoiding-name-conflicts"></a><span data-ttu-id="a934c-187">名前の競合の回避</span><span class="sxs-lookup"><span data-stu-id="a934c-187">Avoiding name conflicts</span></span>

<span data-ttu-id="a934c-188">コマンド名の競合を管理する最良の方法は、それらを回避することです。</span><span class="sxs-lookup"><span data-stu-id="a934c-188">The best way to manage command name conflicts is to prevent them.</span></span> <span data-ttu-id="a934c-189">コマンドに名前を指定する場合は、一意の名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="a934c-189">When you name your commands, use a unique name.</span></span> <span data-ttu-id="a934c-190">たとえば、コマンドの名詞に頭文字または会社名の頭字語を追加します。</span><span class="sxs-lookup"><span data-stu-id="a934c-190">For example, add your initials or company name acronym to the nouns in your commands.</span></span>

<span data-ttu-id="a934c-191">また、PowerShell モジュールまたは別のセッションからセッションにコマンドをインポートする場合 `Prefix` は、 [インポートモジュール](xref:Microsoft.PowerShell.Core.Import-Module) のパラメーターを使用するか、</span><span class="sxs-lookup"><span data-stu-id="a934c-191">Also, when you import commands into your session from a PowerShell module or from another session, use the `Prefix` parameter of the [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) or</span></span>

<span data-ttu-id="a934c-192">コマンドの名前の名詞にプレフィックスを追加するには[、PSSession](xref:Microsoft.PowerShell.Utility.Import-PSSession)コマンドレットをインポートします。</span><span class="sxs-lookup"><span data-stu-id="a934c-192">[Import-PSSession](xref:Microsoft.PowerShell.Utility.Import-PSSession) cmdlet to add a prefix to the nouns in the names of commands.</span></span>

<span data-ttu-id="a934c-193">たとえば、次のコマンドは、モジュールをインポートする `Get-Date` `Set-Date` ときに PowerShell に付属するコマンドレットとコマンドレットとの競合を回避し `DateFunctions` ます。</span><span class="sxs-lookup"><span data-stu-id="a934c-193">For example, the following command avoids any conflict with the `Get-Date` and `Set-Date` cmdlets that come with PowerShell when you import the `DateFunctions` module.</span></span>

```powershell
Import-Module -Name DateFunctions -Prefix ZZ
```

<span data-ttu-id="a934c-194">詳細については、以下を参照してください `Import-Module` `Import-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="a934c-194">For more information, see `Import-Module` and `Import-PSSession` below.</span></span>

## <a name="see-also"></a><span data-ttu-id="a934c-195">関連項目</span><span class="sxs-lookup"><span data-stu-id="a934c-195">See also</span></span>

- [<span data-ttu-id="a934c-196">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="a934c-196">about_Path_Syntax</span></span>](about_Path_Syntax.md)
- [<span data-ttu-id="a934c-197">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="a934c-197">about_Aliases</span></span>](about_Aliases.md)
- [<span data-ttu-id="a934c-198">about_Functions</span><span class="sxs-lookup"><span data-stu-id="a934c-198">about_Functions</span></span>](about_Functions.md)
- [<span data-ttu-id="a934c-199">Alias-Provider</span><span class="sxs-lookup"><span data-stu-id="a934c-199">Alias-Provider</span></span>](../../Microsoft.PowerShell.Core/About/about_Alias_Provider.md)
- [<span data-ttu-id="a934c-200">Function-Provider</span><span class="sxs-lookup"><span data-stu-id="a934c-200">Function-Provider</span></span>](../../Microsoft.PowerShell.Core/About/about_Function_Provider.md)
- [<span data-ttu-id="a934c-201">Get-Command</span><span class="sxs-lookup"><span data-stu-id="a934c-201">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)
- [<span data-ttu-id="a934c-202">Import-Module</span><span class="sxs-lookup"><span data-stu-id="a934c-202">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)
- [<span data-ttu-id="a934c-203">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="a934c-203">Import-PSSession</span></span>](xref:Microsoft.PowerShell.Utility.Import-PSSession)
