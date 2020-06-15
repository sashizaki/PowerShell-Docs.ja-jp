---
title: 関数
description: PowerShell 関数を使用すると、スクリプトで再利用できるツールを作成することができます。
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: ca48f3020fa306f8a24328bd18648d5954c48a94
ms.sourcegitcommit: 0d958eac5bde5ccf5ee2c1bac4f009a63bf71368
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2020
ms.locfileid: "84438203"
---
# <a name="chapter-9---functions"></a><span data-ttu-id="09a4a-103">第 9 章 - 関数</span><span class="sxs-lookup"><span data-stu-id="09a4a-103">Chapter 9 - Functions</span></span>

<span data-ttu-id="09a4a-104">PowerShell のワンライナーまたはスクリプトを記述していると、それを、さまざまなシナリオに合わせて変更しなければならないことがよく出てきます。このようなワンライナーやスクリプトが、再利用可能な関数への有力な変換候補である可能性は十分にあります。</span><span class="sxs-lookup"><span data-stu-id="09a4a-104">If you're writing PowerShell one-liners or scripts and find yourself often having to modify them for different scenarios, there's a good chance that it's a good candidate to be turned into a function that can be reused.</span></span>

<span data-ttu-id="09a4a-105">関数ではツールがより重視されているため、私はできる限り関数を記述したいと考えています。</span><span class="sxs-lookup"><span data-stu-id="09a4a-105">Whenever possible, I prefer to write functions because they are more tool oriented.</span></span> <span data-ttu-id="09a4a-106">関数をスクリプト モジュールに置き、そのモジュールを `$env:PSModulePath` に置いて、関数を呼び出すことができます。その際、その関数が保存されている場所を物理的に特定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="09a4a-106">I can put the functions in a script module, put that module in the `$env:PSModulePath`, and call the functions without needing to physically locate where they're saved.</span></span> <span data-ttu-id="09a4a-107">PowerShellGet モジュールを使用すると、NuGet リポジトリでこれらのモジュールを簡単に共有できます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-107">Using the PowerShellGet module, it's easy to share those modules in a NuGet repository.</span></span> <span data-ttu-id="09a4a-108">PowerShellGet は、PowerShell バージョン5.0 以降に付属しています。</span><span class="sxs-lookup"><span data-stu-id="09a4a-108">PowerShellGet ships with PowerShell version 5.0 and higher.</span></span> <span data-ttu-id="09a4a-109">PowerShell バージョン3.0 以降については、個別のダウンロードとして入手できます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-109">It is available as a separate download for PowerShell version 3.0 and higher.</span></span>

<span data-ttu-id="09a4a-110">物事を複雑にしすぎないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="09a4a-110">Don't over complicate things.</span></span> <span data-ttu-id="09a4a-111">シンプルを心がけ、最も簡単にタスクを実行できる方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="09a4a-111">Keep it simple and use the most straight forward way to accomplish a task.</span></span> <span data-ttu-id="09a4a-112">再利用するコードで、エイリアスと位置指定パラメーターを使用するのは避け、</span><span class="sxs-lookup"><span data-stu-id="09a4a-112">Avoid aliases and positional parameters in any code that you reuse.</span></span> <span data-ttu-id="09a4a-113">読みやすさを考えてコードを書式設定してください。</span><span class="sxs-lookup"><span data-stu-id="09a4a-113">Format your code for readability.</span></span> <span data-ttu-id="09a4a-114">値はハードコーディングせず、パラメーターと変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="09a4a-114">Don't hardcode values; use parameters and variables.</span></span> <span data-ttu-id="09a4a-115">悪い影響が何もなくても、不要なコードは記述しないでください。</span><span class="sxs-lookup"><span data-stu-id="09a4a-115">Don't write unnecessary code even if it doesn't hurt anything.</span></span> <span data-ttu-id="09a4a-116">不必要に複雑になってしまいます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-116">It adds unnecessary complexity.</span></span> <span data-ttu-id="09a4a-117">PowerShell コードを記述するときは、細部にまで注意を払うことが大いに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-117">Attention to detail goes a long way when writing any PowerShell code.</span></span>

## <a name="naming"></a><span data-ttu-id="09a4a-118">名前を付ける</span><span class="sxs-lookup"><span data-stu-id="09a4a-118">Naming</span></span>

<span data-ttu-id="09a4a-119">PowerShell で関数に名前を付けるときは、承認されている動詞と単数形の名詞で [Pascal case][] 名を使用します。</span><span class="sxs-lookup"><span data-stu-id="09a4a-119">When naming your functions in PowerShell, use a [Pascal case][] name with an approved verb and a singular noun.</span></span> <span data-ttu-id="09a4a-120">また、名詞の前にプレフィックスを付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="09a4a-120">I also recommend prefixing the noun.</span></span> <span data-ttu-id="09a4a-121">(例: `<ApprovedVerb>-<Prefix><SingularNoun>`)。</span><span class="sxs-lookup"><span data-stu-id="09a4a-121">For example: `<ApprovedVerb>-<Prefix><SingularNoun>`.</span></span>

<span data-ttu-id="09a4a-122">PowerShell には承認されている動詞の一覧があり、`Get-Verb` を実行して取得できます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-122">In PowerShell, there's a specific list of approved verbs that can be obtained by running `Get-Verb`.</span></span>

```powershell
Get-Verb | Sort-Object -Property Verb
```

```Output
Verb        Group
----        -----
Add         Common
Approve     Lifecycle
Assert      Lifecycle
Backup      Data
Block       Security
Checkpoint  Data
Clear       Common
Close       Common
Compare     Data
Complete    Lifecycle
Compress    Data
Confirm     Lifecycle
Connect     Communications
Convert     Data
ConvertFrom Data
ConvertTo   Data
Copy        Common
Debug       Diagnostic
Deny        Lifecycle
Disable     Lifecycle
Disconnect  Communications
Dismount    Data
Edit        Data
Enable      Lifecycle
Enter       Common
Exit        Common
Expand      Data
Export      Data
Find        Common
Format      Common
Get         Common
Grant       Security
Group       Data
Hide        Common
Import      Data
Initialize  Data
Install     Lifecycle
Invoke      Lifecycle
Join        Common
Limit       Data
Lock        Common
Measure     Diagnostic
Merge       Data
Mount       Data
Move        Common
New         Common
Open        Common
Optimize    Common
Out         Data
Ping        Diagnostic
Pop         Common
Protect     Security
Publish     Data
Push        Common
Read        Communications
Receive     Communications
Redo        Common
Register    Lifecycle
Remove      Common
Rename      Common
Repair      Diagnostic
Request     Lifecycle
Reset       Common
Resize      Common
Resolve     Diagnostic
Restart     Lifecycle
Restore     Data
Resume      Lifecycle
Revoke      Security
Save        Data
Search      Common
Select      Common
Send        Communications
Set         Common
Show        Common
Skip        Common
Split       Common
Start       Lifecycle
Step        Common
Stop        Lifecycle
Submit      Lifecycle
Suspend     Lifecycle
Switch      Common
Sync        Data
Test        Diagnostic
Trace       Diagnostic
Unblock     Security
Undo        Common
Uninstall   Lifecycle
Unlock      Common
Unprotect   Security
Unpublish   Data
Unregister  Lifecycle
Update      Data
Use         Other
Wait        Lifecycle
Watch       Common
Write       Communications
```

<span data-ttu-id="09a4a-123">この例では、**Verb** 列に基づいて結果を並べ替えました。</span><span class="sxs-lookup"><span data-stu-id="09a4a-123">In the previous example, I've sorted the results by the **Verb** column.</span></span> <span data-ttu-id="09a4a-124">**Group** 列には、これらの動詞がどのように使用されるかが示されています。</span><span class="sxs-lookup"><span data-stu-id="09a4a-124">The **Group** column gives you an idea of how these verbs are used.</span></span> <span data-ttu-id="09a4a-125">関数がモジュールに追加されている場合、PowerShell で承認されている動詞を選択することが重要です。</span><span class="sxs-lookup"><span data-stu-id="09a4a-125">It's important to choose an approved verb in PowerShell when functions are added to a module.</span></span> <span data-ttu-id="09a4a-126">未承認の動詞を選択すると、読み込み時にモジュールによって警告メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-126">The module generates a warning message at load time if you choose an unapproved verb.</span></span> <span data-ttu-id="09a4a-127">この警告メッセージにより、プロらしくない関数になってしまいます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-127">That warning message makes your functions look unprofessional.</span></span> <span data-ttu-id="09a4a-128">また、未承認の動詞があると、関数の検出可能性も制限されます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-128">Unapproved verbs also limit the discoverability of your functions.</span></span>

## <a name="a-simple-function"></a><span data-ttu-id="09a4a-129">単純な関数</span><span class="sxs-lookup"><span data-stu-id="09a4a-129">A simple function</span></span>

<span data-ttu-id="09a4a-130">PowerShell の関数を宣言するには、関数キーワード、関数名、左中かっこ、右中かっこの順に指定します。</span><span class="sxs-lookup"><span data-stu-id="09a4a-130">A function in PowerShell is declared with the function keyword followed by the function name and then an open and closing curly brace.</span></span> <span data-ttu-id="09a4a-131">関数によって実行されるコードは、中かっこに囲まれています。</span><span class="sxs-lookup"><span data-stu-id="09a4a-131">The code that the function will execute is contained within those curly braces.</span></span>

```powershell
function Get-Version {
    $PSVersionTable.PSVersion
}
```

<span data-ttu-id="09a4a-132">次に示す関数は、PowerShell のバージョンを返す簡単な例です。</span><span class="sxs-lookup"><span data-stu-id="09a4a-132">The function shown is a simple example that returns the version of PowerShell.</span></span>

```powershell
Get-Version
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  693
```

<span data-ttu-id="09a4a-133">`Get-Version` などの関数の名前と、PowerShell の既定のコマンドや他のユーザーが記述するかもしれないコマンドの名前が競合する可能性は大いにあります。</span><span class="sxs-lookup"><span data-stu-id="09a4a-133">There's a good chance of name conflict with functions named something like `Get-Version` and default commands in PowerShell or commands that others may write.</span></span> <span data-ttu-id="09a4a-134">関数の名詞部分にプレフィックスを付けることを勧めるのは、このためです。プレフィックスは名前の競合を防ぐうえで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-134">This is why I recommend prefixing the noun portion of your functions to help prevent naming conflicts.</span></span> <span data-ttu-id="09a4a-135">次の例では、プレフィックス "PS" を使用します。</span><span class="sxs-lookup"><span data-stu-id="09a4a-135">In the following example, I'll use the prefix "PS".</span></span>

```powershell
function Get-PSVersion {
    $PSVersionTable.PSVersion
}
```

<span data-ttu-id="09a4a-136">次の関数は、名前以外は、前の関数とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="09a4a-136">Other than the name, this function is identical to the previous one.</span></span>

```powershell
Get-PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  693
```

<span data-ttu-id="09a4a-137">名詞の前に PS のようなプレフィックスを付けても、名前が競合する可能性は少なくありません。</span><span class="sxs-lookup"><span data-stu-id="09a4a-137">Even when prefixing the noun with something like PS, there's still a good chance of having a name conflict.</span></span> <span data-ttu-id="09a4a-138">そこで私は、通常、関数の名詞の前に自分のイニシャルを付けます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-138">I typically prefix my function nouns with my initials.</span></span> <span data-ttu-id="09a4a-139">基準を決めて、それに従ってください。</span><span class="sxs-lookup"><span data-stu-id="09a4a-139">Develop a standard and stick to it.</span></span>

```powershell
function Get-MrPSVersion {
    $PSVersionTable.PSVersion
}
```

<span data-ttu-id="09a4a-140">この関数は基本的には前の 2 つと変わりませんが、他の PowerShell コマンドとの名前の競合を、さらに確実に避けられる名前が使われています。</span><span class="sxs-lookup"><span data-stu-id="09a4a-140">This function is no different than the previous two other than using a more sensible name to try to prevent naming conflicts with other PowerShell commands.</span></span>

```powershell
Get-MrPSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  693
```

<span data-ttu-id="09a4a-141">メモリに読み込まれると、**Function** PSDrive で関数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-141">Once loaded into memory, you can see functions on the **Function** PSDrive.</span></span>

```powershell
Get-ChildItem -Path Function:\Get-*Version
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Function        Get-Version
Function        Get-PSVersion
Function        Get-MrPSVersion
```

<span data-ttu-id="09a4a-142">これらの関数を現在のセッションから削除する場合は、**Function** PSDrive から削除するか、PowerShell を一度閉じてから再度開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="09a4a-142">If you want to remove these functions from your current session, you'll have to remove them from the **Function** PSDrive or close and reopen PowerShell.</span></span>

```powershell
Get-ChildItem -Path Function:\Get-*Version | Remove-Item
```

<span data-ttu-id="09a4a-143">関数が本当に削除されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="09a4a-143">Verify that the functions were indeed removed.</span></span>

```powershell
Get-ChildItem -Path Function:\Get-*Version
```

<span data-ttu-id="09a4a-144">関数がモジュールの一部として読み込まれている場合は、モジュールをアンロードすることで、関数を削除できます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-144">If the functions were loaded as part of a module, the module can be unloaded to remove them.</span></span>

```powershell
Remove-Module -Name <ModuleName>
```

<span data-ttu-id="09a4a-145">`Remove-Module` コマンドレットを実行すると、現在の PowerShell セッションのメモリからモジュールが削除されますが、システムまたはディスクからは削除されません。</span><span class="sxs-lookup"><span data-stu-id="09a4a-145">The `Remove-Module` cmdlet removes modules from memory in your current PowerShell session, it doesn't remove them from your system or from disk.</span></span>

## <a name="parameters"></a><span data-ttu-id="09a4a-146">パラメーター</span><span class="sxs-lookup"><span data-stu-id="09a4a-146">Parameters</span></span>

<span data-ttu-id="09a4a-147">値を静的に割り当てないでください。</span><span class="sxs-lookup"><span data-stu-id="09a4a-147">Don't statically assign values!</span></span> <span data-ttu-id="09a4a-148">パラメーターと変数を使用してください。</span><span class="sxs-lookup"><span data-stu-id="09a4a-148">Use parameters and variables.</span></span> <span data-ttu-id="09a4a-149">また、パラメーターに名前を付けるときは、できる限り既定のコマンドレットと同じ名前を、パラメーター名として使用してください。</span><span class="sxs-lookup"><span data-stu-id="09a4a-149">When it comes to naming your parameters, use the same name as the default cmdlets for your parameter names whenever possible.</span></span>

```powershell
function Test-MrParameter {

    param (
        $ComputerName
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="09a4a-150">ここでパラメーター名として **ComputerName** を使い、**Computer**、**ServerName**、または **Host** を使わなかったのは、</span><span class="sxs-lookup"><span data-stu-id="09a4a-150">Why did I use **ComputerName** and not **Computer**, **ServerName**, or **Host** for my parameter name?</span></span> <span data-ttu-id="09a4a-151">自分の関数を、既定のコマンドレットのように標準化したかったからです。</span><span class="sxs-lookup"><span data-stu-id="09a4a-151">It's because I wanted my function standardized like the default cmdlets.</span></span>

<span data-ttu-id="09a4a-152">システム上のすべてのコマンドに対してクエリを実行する関数を作成します。この関数により、特定のパラメーター名を持つコマンドの数を取得できます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-152">I'll create a function to query all of the commands on a system and return the number of them that have specific parameter names.</span></span>

```powershell
function Get-MrParameterCount {
    param (
        [string[]]$ParameterName
    )

    foreach ($Parameter in $ParameterName) {
        $Results = Get-Command -ParameterName $Parameter -ErrorAction SilentlyContinue

        [pscustomobject]@{
            ParameterName = $Parameter
            NumberOfCmdlets = $Results.Count
        }
    }
}
```

<span data-ttu-id="09a4a-153">次に示す結果でわかるように、**ComputerName** パラメーターを持つコマンドは 39 個あります。</span><span class="sxs-lookup"><span data-stu-id="09a4a-153">As you can see in the results shown below, 39 commands that have a **ComputerName** parameter.</span></span> <span data-ttu-id="09a4a-154">**Computer**、**ServerName**、**Host**、**Machine** などのパラメーターを持つコマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="09a4a-154">There aren't any cmdlets that have parameters such as **Computer**, **ServerName**, **Host**, or **Machine**.</span></span>

```powershell
Get-MrParameterCount -ParameterName ComputerName, Computer, ServerName, Host, Machine
```

```Output
ParameterName NumberOfCmdlets
------------- ---------------
ComputerName               39
Computer                    0
ServerName                  0
Host                        0
Machine                     0
```

<span data-ttu-id="09a4a-155">また、パラメーター名の大文字と小文字も、既定のコマンドレットに揃えることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="09a4a-155">I also recommend using the same case for your parameter names as the default cmdlets.</span></span> <span data-ttu-id="09a4a-156">`computername` ではなく、`ComputerName` を使用してください。</span><span class="sxs-lookup"><span data-stu-id="09a4a-156">Use `ComputerName`, not `computername`.</span></span> <span data-ttu-id="09a4a-157">これにより、関数の外観が既定のコマンドレットと同じようになります。</span><span class="sxs-lookup"><span data-stu-id="09a4a-157">This makes your functions look and feel like the default cmdlets.</span></span> <span data-ttu-id="09a4a-158">既に PowerShell に慣れている方にとっては、使いやすく感じるでしょう。</span><span class="sxs-lookup"><span data-stu-id="09a4a-158">People who are already familiar with PowerShell will feel right at home.</span></span>

## <a name="advanced-functions"></a><span data-ttu-id="09a4a-159">高度な関数</span><span class="sxs-lookup"><span data-stu-id="09a4a-159">Advanced Functions</span></span>

<span data-ttu-id="09a4a-160">PowerShell の関数は、非常に簡単に高度な関数に変換できます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-160">Turning a function in PowerShell into an advanced function is really simple.</span></span> <span data-ttu-id="09a4a-161">関数と高度な関数の違いの 1 つが、高度な関数には、多くの共通パラメーターが自動的に追加されることです。</span><span class="sxs-lookup"><span data-stu-id="09a4a-161">One of the differences between a function and an advanced function is that advanced functions have a number of common parameters that are added to the function automatically.</span></span> <span data-ttu-id="09a4a-162">たとえば、**Verbose**、**Debug** などのパラメーターが、共通パラメーターとして挙げられます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-162">These common parameters include parameters such as **Verbose** and **Debug**.</span></span>

<span data-ttu-id="09a4a-163">最初に、前のセクションで使用した `Test-MrParameter` 関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="09a4a-163">I'll start out with the `Test-MrParameter` function that was used in the previous section.</span></span>

```powershell
function Test-MrParameter {

    param (
        $ComputerName
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="09a4a-164">ここでは `Test-MrParameter` 関数に共通パラメーターがないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="09a4a-164">What I want you to notice is that the `Test-MrParameter` function doesn't have any common parameters.</span></span> <span data-ttu-id="09a4a-165">共通パラメーターを表示する方法はいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="09a4a-165">There are a couple of different ways to see the common parameters.</span></span> <span data-ttu-id="09a4a-166">1 つは `Get-Command` を使用して構文を表示する方法です。</span><span class="sxs-lookup"><span data-stu-id="09a4a-166">One is by viewing the syntax using `Get-Command`.</span></span>

```powershell
Get-Command -Name Test-MrParameter -Syntax
```

```Output
Test-MrParameter [[-ComputerName] <Object>]
```

<span data-ttu-id="09a4a-167">もう 1 つは、`Get-Command` でパラメーターをドリルダウンする方法です。</span><span class="sxs-lookup"><span data-stu-id="09a4a-167">Another is to drill down into the parameters with `Get-Command`.</span></span>

```powershell
(Get-Command -Name Test-MrParameter).Parameters.Keys
```

```Output
ComputerName
```

<span data-ttu-id="09a4a-168">`CmdletBinding` を追加して、関数を高度な関数に変換します。</span><span class="sxs-lookup"><span data-stu-id="09a4a-168">Add `CmdletBinding` to turn the function into an advanced function.</span></span>

```powershell
function Test-MrCmdletBinding {

    [CmdletBinding()] #<<-- This turns a regular function into an advanced function
    param (
        $ComputerName
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="09a4a-169">`CmdletBinding` を追加すると、共通パラメーターが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-169">Adding `CmdletBinding` adds the common parameters automatically.</span></span> <span data-ttu-id="09a4a-170">`CmdletBinding` には `param` ブロックが必要ですが、`param` ブロックは空にできます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-170">`CmdletBinding` requires a `param` block, but the `param` block can be empty.</span></span>

```powershell
Get-Command -Name Test-MrCmdletBinding -Syntax
```

```Output
Test-MrCmdletBinding [[-ComputerName] <Object>] [<CommonParameters>]
```

<span data-ttu-id="09a4a-171">`Get-Command` でパラメーターをドリルダウンすると、共通パラメーター名を含む実際のパラメーター名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-171">Drilling down into the parameters with `Get-Command` shows the actual parameter names including the common ones.</span></span>

```powershell
(Get-Command -Name Test-MrCmdletBinding).Parameters.Keys
```

```Output
ComputerName
Verbose
Debug
ErrorAction
WarningAction
InformationAction
ErrorVariable
WarningVariable
InformationVariable
OutVariable
OutBuffer
PipelineVariable
```

## <a name="supportsshouldprocess"></a><span data-ttu-id="09a4a-172">SupportsShouldProcess</span><span class="sxs-lookup"><span data-stu-id="09a4a-172">SupportsShouldProcess</span></span>

<span data-ttu-id="09a4a-173">`SupportsShouldProcess` により、**WhatIf** パラメーターと **Confirm** パラメーターが追加されます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-173">`SupportsShouldProcess` adds **WhatIf** and **Confirm** parameters.</span></span> <span data-ttu-id="09a4a-174">これらのパラメーターは、変更するコマンドにのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="09a4a-174">These are only needed for commands that make changes.</span></span>

```powershell
function Test-MrSupportsShouldProcess {

    [CmdletBinding(SupportsShouldProcess)]
    param (
        $ComputerName
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="09a4a-175">現在、**WhatIf** パラメーターと **Confirm** パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="09a4a-175">Notice that there are now **WhatIf** and **Confirm** parameters.</span></span>

```powershell
Get-Command -Name Test-MrSupportsShouldProcess -Syntax
```

```Output
Test-MrSupportsShouldProcess [[-ComputerName] <Object>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

<span data-ttu-id="09a4a-176">ここでも、`Get-Command` を使用して、共通パラメーター名と WhatIf および Confirm を含む実際のパラメーター名の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-176">Once again, you can also use `Get-Command` to return a list of the actual parameter names including the common ones along with WhatIf and Confirm.</span></span>

```powershell
(Get-Command -Name Test-MrSupportsShouldProcess).Parameters.Keys
```

```Output
ComputerName
Verbose
Debug
ErrorAction
WarningAction
InformationAction
ErrorVariable
WarningVariable
InformationVariable
OutVariable
OutBuffer
PipelineVariable
WhatIf
Confirm
```

## <a name="parameter-validation"></a><span data-ttu-id="09a4a-177">パラメーターの検証</span><span class="sxs-lookup"><span data-stu-id="09a4a-177">Parameter Validation</span></span>

<span data-ttu-id="09a4a-178">入力は早い段階で検証してください。</span><span class="sxs-lookup"><span data-stu-id="09a4a-178">Validate input early on.</span></span> <span data-ttu-id="09a4a-179">コードの処理を続行できるようにしても、有効な値が入力されていなくて実行できなければ意味がありません。</span><span class="sxs-lookup"><span data-stu-id="09a4a-179">Why allow your code to continue on a path when it's not possible to run without valid input?</span></span>

<span data-ttu-id="09a4a-180">入力する変数は必ず、パラメーターに対して使用されているものにします (データ型を指定します)。</span><span class="sxs-lookup"><span data-stu-id="09a4a-180">Always type the variables that are being used for your parameters (specify a datatype).</span></span>

```powershell
function Test-MrParameterValidation {

    [CmdletBinding()]
    param (
        [string]$ComputerName
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="09a4a-181">この例では、**ComputerName** パラメーターに対して、**String** をデータ型として指定しました。</span><span class="sxs-lookup"><span data-stu-id="09a4a-181">In the previous example, I've specified **String** as the datatype for the **ComputerName** parameter.</span></span> <span data-ttu-id="09a4a-182">これにより、コンピューター名を 1 つしか指定できなくなります。</span><span class="sxs-lookup"><span data-stu-id="09a4a-182">This causes it to allow only a single computer name to be specified.</span></span> <span data-ttu-id="09a4a-183">コンマ区切りのリストを使用して複数のコンピューター名が指定されていると、エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-183">If more than one computer name is specified via a comma-separated list, an error is generated.</span></span>

```powershell
Test-MrParameterValidation -ComputerName Server01, Server02
```

```Output
Test-MrParameterValidation : Cannot process argument transformation on parameter
'ComputerName'. Cannot convert value to type System.String.
At line:1 char:42
+ Test-MrParameterValidation -ComputerName Server01, Server02
+
    + CategoryInfo          : InvalidData: (:) [Test-MrParameterValidation], ParameterBindingArg
     umentTransformationException
    + FullyQualifiedErrorId : ParameterArgumentTransformationError,Test-MrParameterValidation
```

<span data-ttu-id="09a4a-184">現時点での定義の問題は、**ComputerName** パラメーターの値は省略できるのに、関数が正常に完了するには、その値が必要であることです。</span><span class="sxs-lookup"><span data-stu-id="09a4a-184">The problem with the current definition is that it's valid to omit the value of the **ComputerName** parameter, but a value is required for the function to complete successfully.</span></span> <span data-ttu-id="09a4a-185">ここで、`Mandatory` パラメーター属性が役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-185">This is where the `Mandatory` parameter attribute comes in handy.</span></span>

```powershell
function Test-MrParameterValidation {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory)]
        [string]$ComputerName
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="09a4a-186">この例で使用している構文は、PowerShell バージョン3.0 以降に対応しています。</span><span class="sxs-lookup"><span data-stu-id="09a4a-186">The syntax used in the previous example is PowerShell version 3.0 and higher compatible.</span></span>
<span data-ttu-id="09a4a-187">`[Parameter(Mandatory=$true)]` を指定すると、関数と PowerShell バージョン 2.0 以降の互換性が確保されます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-187">`[Parameter(Mandatory=$true)]` could be specified instead to make the function compatible with PowerShell version 2.0 and higher.</span></span> <span data-ttu-id="09a4a-188">これで **ComputerName** が必須になり、指定されていないと、入力を求めるメッセージが関数によって表示されます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-188">Now that the **ComputerName** is required, if one isn't specified, the function will prompt for one.</span></span>

```powershell
Test-MrParameterValidation
```

```Output
cmdlet Test-MrParameterValidation at command pipeline position 1
Supply values for the following parameters:
ComputerName:
```

<span data-ttu-id="09a4a-189">**ComputerName** パラメーターに複数の値を指定できるようにする場合は、**String** データ型を使用しますが、文字列の配列を指定できるように、データ型には左角かっこと右角かっこを追加します。</span><span class="sxs-lookup"><span data-stu-id="09a4a-189">If you want to allow for more than one value for the **ComputerName** parameter, use the **String** datatype but add open and closed square brackets to the datatype to allow for an array of strings.</span></span>

```powershell
function Test-MrParameterValidation {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory)]
        [string[]]$ComputerName
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="09a4a-190">**ComputerName** パラメーターに既定値を指定する必要が出てくることもあるでしょう (指定されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="09a4a-190">Maybe you want to specify a default value for the **ComputerName** parameter if one isn't specified.</span></span>
<span data-ttu-id="09a4a-191">問題は、必須パラメーターでは既定値を使用できないことです。</span><span class="sxs-lookup"><span data-stu-id="09a4a-191">The problem is that default values can't be used with mandatory parameters.</span></span> <span data-ttu-id="09a4a-192">この場合は、`ValidateNotNullOrEmpty` パラメーター検証属性を既定値と共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09a4a-192">Instead, you'll need to use the `ValidateNotNullOrEmpty` parameter validation attribute with a default value.</span></span>

```powershell
function Test-MrParameterValidation {

    [CmdletBinding()]
    param (
        [ValidateNotNullOrEmpty()]
        [string[]]$ComputerName = $env:COMPUTERNAME
    )

    Write-Output $ComputerName

}
```

<span data-ttu-id="09a4a-193">既定値を設定するときも、静的な値は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="09a4a-193">Even when setting a default value, try not to use static values.</span></span> <span data-ttu-id="09a4a-194">この例では、`$env:COMPUTERNAME` が既定値として使用されています。つまり、値が指定されていない場合、これはローカルコンピューター名に自動的に変換されます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-194">In the previous example, `$env:COMPUTERNAME` is used as the default value, which is automatically translated into the local computer name if a value is not provided.</span></span>

## <a name="verbose-output"></a><span data-ttu-id="09a4a-195">詳細出力</span><span class="sxs-lookup"><span data-stu-id="09a4a-195">Verbose Output</span></span>

<span data-ttu-id="09a4a-196">インライン コメントは、特に複雑なコードを記述している場合は便利ですが、コード自体を調べていないユーザーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="09a4a-196">While inline comments are useful, especially if you're writing some complex code, they never get seen by users unless they look into the code itself.</span></span>

<span data-ttu-id="09a4a-197">次の例の関数には、`foreach` ループにインライン コメントがあります。</span><span class="sxs-lookup"><span data-stu-id="09a4a-197">The function shown in the following example has an inline comment in the `foreach` loop.</span></span> <span data-ttu-id="09a4a-198">この特別なコメントについては、それほど苦労せずに見つけられるでしょう。しかし、関数に数百行のコードが含まれていたらどうかを想像してみてください。</span><span class="sxs-lookup"><span data-stu-id="09a4a-198">While this particular comment may not be that difficult to locate, imagine if the function included hundreds of lines of code.</span></span>

```powershell
function Test-MrVerboseOutput {

    [CmdletBinding()]
    param (
        [ValidateNotNullOrEmpty()]
        [string[]]$ComputerName = $env:COMPUTERNAME
    )

    foreach ($Computer in $ComputerName) {
        #Attempting to perform some action on $Computer <<-- Don't use
        #inline comments like this, use write verbose instead.
        Write-Output $Computer
    }

}
```

<span data-ttu-id="09a4a-199">もっと良い方法があります。インライン コメントではなく `Write-Verbose` を使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="09a4a-199">A better option is to use `Write-Verbose` instead of inline comments.</span></span>

```powershell
function Test-MrVerboseOutput {

    [CmdletBinding()]
    param (
        [ValidateNotNullOrEmpty()]
        [string[]]$ComputerName = $env:COMPUTERNAME
    )

    foreach ($Computer in $ComputerName) {
        Write-Verbose -Message "Attempting to perform some action on $Computer"
        Write-Output $Computer
    }

}
```

<span data-ttu-id="09a4a-200">**Verbose** パラメーターを指定せずに関数を呼び出すと、詳細出力は表示されません。</span><span class="sxs-lookup"><span data-stu-id="09a4a-200">When the function is called without the **Verbose** parameter, the verbose output won't be displayed.</span></span>

```powershell
Test-MrVerboseOutput -ComputerName Server01, Server02
```

<span data-ttu-id="09a4a-201">**Verbose** パラメーターを指定して呼び出すと、詳細出力は表示されます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-201">When it's called with the **Verbose** parameter, the verbose output will be displayed.</span></span>

```powershell
Test-MrVerboseOutput -ComputerName Server01, Server02 -Verbose
```

## <a name="pipeline-input"></a><span data-ttu-id="09a4a-202">パイプライン入力</span><span class="sxs-lookup"><span data-stu-id="09a4a-202">Pipeline Input</span></span>

<span data-ttu-id="09a4a-203">関数でパイプライン入力を受け入れるには、追加コーディングがいくつか必要です。</span><span class="sxs-lookup"><span data-stu-id="09a4a-203">When you want your function to accept pipeline input, some additional coding is necessary.</span></span> <span data-ttu-id="09a4a-204">本書で前述したように、コマンドが受け入れることができるのは、**値** (型) または**プロパティ名**によるパイプライン入力です。</span><span class="sxs-lookup"><span data-stu-id="09a4a-204">As mentioned earlier in this book, commands can accept pipeline input **by value** (by type) or **by property name**.</span></span> <span data-ttu-id="09a4a-205">関数はネイティブ コマンドと同じように記述できるため、これらの入力の種類のいずれか、または両方を受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-205">You can write your functions just like the native commands so that they accept either one or both of these types of input.</span></span>

<span data-ttu-id="09a4a-206">**値**によるパイプライン入力を受け入れるには、その特定のパラメーターに対して `ValueFromPipeline` パラメーター属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="09a4a-206">To accept pipeline input **by value**, specified the `ValueFromPipeline` parameter attribute for that particular parameter.</span></span> <span data-ttu-id="09a4a-207">受け入れることができるのは、いずれかのデータ型からの**値**によるパイプライン入力だけであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="09a4a-207">Keep in mind that you can only accept pipeline input **by value** from one of each datatype.</span></span> <span data-ttu-id="09a4a-208">たとえば、文字列入力を受け入れるパラメーターが 2 つある場合は、一方だけが**値**によるパイプライン入力を受け入れることができます。これは、両方の文字列パラメーターに対してそれを指定すると、パイプライン入力でバインド先を認識できなくなるためです。</span><span class="sxs-lookup"><span data-stu-id="09a4a-208">For example, if you have two parameters that accept string input, only one of those can accept pipeline input **by value** because if you specified it for both of the string parameters, the pipeline input wouldn't know which one to bind to.</span></span> <span data-ttu-id="09a4a-209">これも、私がこの種類のパイプライン入力を、**値**ではなく "_型_" によるパイプライン入力と呼ぶ理由です。</span><span class="sxs-lookup"><span data-stu-id="09a4a-209">This is another reason I call this type of pipeline input _by type_ instead of **by value**.</span></span>

<span data-ttu-id="09a4a-210">`foreach` ループでの項目の処理方法と同じように、パイプライン入力は 1 つずつ行われます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-210">Pipeline input comes in one item at a time similar to the way items are handled in a `foreach` loop.</span></span>
<span data-ttu-id="09a4a-211">少なくとも、配列を入力として受け入れる場合は、`process` ブロックがこれらの各項目を処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09a4a-211">At a minimum, a `process` block is required to process each of these items if you're accepting an array as input.</span></span> <span data-ttu-id="09a4a-212">入力として 1 つの値しか受け入れていない場合、`process` ブロックは不要ですが、それでも一貫性を確保するために指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="09a4a-212">If you're only accepting a single value as input, a `process` block isn't necessary, but I still recommend specifying it for consistency.</span></span>

```powershell
function Test-MrPipelineInput {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipeline)]
        [string[]]$ComputerName
    )

    PROCESS {
        Write-Output $ComputerName
    }

}
```

<span data-ttu-id="09a4a-213">**プロパティ名**によるパイプライン入力の受け入れも似ていますが、これは `ValueFromPipelineByPropertyName` パラメーター属性で指定され、データ型に関係なく、任意の数のパラメーターに対して指定できる点が異なります。</span><span class="sxs-lookup"><span data-stu-id="09a4a-213">Accepting pipeline input **by property name** is similar except it's specified with the `ValueFromPipelineByPropertyName` parameter attribute and it can be specified for any number of parameters regardless of datatype.</span></span> <span data-ttu-id="09a4a-214">重要なのは、パイプ入力中のコマンドの出力には、関数のパラメーターまたはパラメーター エイリアスの名前と一致するプロパティ名が必要であることです。</span><span class="sxs-lookup"><span data-stu-id="09a4a-214">The key is that the output of the command that's being piped in has to have a property name that matches the name of the parameter or a parameter alias of your function.</span></span>

```powershell
function Test-MrPipelineInput {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipelineByPropertyName)]
        [string[]]$ComputerName
    )

    PROCESS {
            Write-Output $ComputerName
    }

}
```

<span data-ttu-id="09a4a-215">`BEGIN` ブロックと`END` ブロックは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="09a4a-215">`BEGIN` and `END` blocks are optional.</span></span> <span data-ttu-id="09a4a-216">`BEGIN` は `PROCESS` ブロックの前で指定され、パイプラインから項目が受信される前の初期処理を実行するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-216">`BEGIN` would be specified before the `PROCESS` block and is used to perform any initial work prior to the items being received from the pipeline.</span></span> <span data-ttu-id="09a4a-217">これを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="09a4a-217">This is important to understand.</span></span> <span data-ttu-id="09a4a-218">パイプ処理された値には、`BEGIN` ブロックではアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="09a4a-218">Values that are piped in are not accessible in the `BEGIN` block.</span></span> <span data-ttu-id="09a4a-219">`END` ブロックは `PROCESS` ブロックの後ろで指定され、パイプ入力されたすべての項目が処理された後、その項目をクリーンアップするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-219">The `END` block would be specified after the `PROCESS` block and is used for cleanup once all of the items that are piped in have been processed.</span></span>

## <a name="error-handling"></a><span data-ttu-id="09a4a-220">エラー処理</span><span class="sxs-lookup"><span data-stu-id="09a4a-220">Error Handling</span></span>

<span data-ttu-id="09a4a-221">次の例に示す関数では、コンピューターに接続できない場合に、ハンドルされない例外が生成されます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-221">The function shown in the following example generates an unhandled exception when a computer can't be contacted.</span></span>

```powershell
function Test-MrErrorHandling {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipeline,
                   ValueFromPipelineByPropertyName)]
        [string[]]$ComputerName
    )

    PROCESS {
        foreach ($Computer in $ComputerName) {
            Test-WSMan -ComputerName $Computer
        }
    }

}
```

<span data-ttu-id="09a4a-222">PowerShell でエラーを処理する方法はいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="09a4a-222">There are a couple of different ways to handle errors in PowerShell.</span></span> <span data-ttu-id="09a4a-223">`Try/Catch` は、最新のエラー処理方法です。</span><span class="sxs-lookup"><span data-stu-id="09a4a-223">`Try/Catch` is the more modern way to handle errors.</span></span>

```powershell
function Test-MrErrorHandling {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipeline,
                   ValueFromPipelineByPropertyName)]
        [string[]]$ComputerName
    )

    PROCESS {
        foreach ($Computer in $ComputerName) {
            try {
                Test-WSMan -ComputerName $Computer
            }
            catch {
                Write-Warning -Message "Unable to connect to Computer: $Computer"
            }
        }
    }

}
```

<span data-ttu-id="09a4a-224">この例の関数では、エラー処理が使用されていますが、ハンドルされない例外も生成されます。終了するエラーがコマンドによって生成されないためです。</span><span class="sxs-lookup"><span data-stu-id="09a4a-224">Although the function shown in the previous example uses error handling, it also generates an unhandled exception because the command doesn't generate a terminating error.</span></span> <span data-ttu-id="09a4a-225">これを理解することも重要です。</span><span class="sxs-lookup"><span data-stu-id="09a4a-225">This is also important to understand.</span></span> <span data-ttu-id="09a4a-226">キャッチされるのは、終了するエラーだけです。</span><span class="sxs-lookup"><span data-stu-id="09a4a-226">Only terminating errors are caught.</span></span> <span data-ttu-id="09a4a-227">そこで **ErrorAction** パラメーターと **Stop** を値として指定して、終了しないエラーを終了するエラーに変換します。</span><span class="sxs-lookup"><span data-stu-id="09a4a-227">Specify the **ErrorAction** parameter with **Stop** as the value to turn a non-terminating error into a terminating one.</span></span>

```powershell
function Test-MrErrorHandling {

    [CmdletBinding()]
    param (
        [Parameter(Mandatory,
                   ValueFromPipeline,
                   ValueFromPipelineByPropertyName)]
        [string[]]$ComputerName
    )

    PROCESS {
        foreach ($Computer in $ComputerName) {
            try {
                Test-WSMan -ComputerName $Computer -ErrorAction Stop
            }
            catch {
                Write-Warning -Message "Unable to connect to Computer: $Computer"
            }
        }
    }

}
```

<span data-ttu-id="09a4a-228">グローバル `$ErrorActionPreference` 変数は、どうしても必要な場合を除き、変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="09a4a-228">Don't modify the global `$ErrorActionPreference` variable unless absolutely necessary.</span></span> <span data-ttu-id="09a4a-229">PowerShell 関数内から .NET のような何かを直接使用している場合は、コマンド自体で **ErrorAction** を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="09a4a-229">If you're using something like .NET directly from within your PowerShell function, you can't specify the **ErrorAction** on the command itself.</span></span> <span data-ttu-id="09a4a-230">このシナリオでは、グローバル `$ErrorActionPreference` 変数の変更が必要になる場合がありますが、変更する場合は、コマンドの実行後すぐに元に戻してください。</span><span class="sxs-lookup"><span data-stu-id="09a4a-230">In that scenario, you might need to change the global `$ErrorActionPreference` variable, but if you do change it, change it back immediately after trying the command.</span></span>

## <a name="comment-based-help"></a><span data-ttu-id="09a4a-231">コメント ベースのヘルプ</span><span class="sxs-lookup"><span data-stu-id="09a4a-231">Comment-Based Help</span></span>

<span data-ttu-id="09a4a-232">関数にはコメント ベースのヘルプを追加することをお勧めします。これにより、関数を共有しているユーザーが、その使用方法を理解できるようになります。</span><span class="sxs-lookup"><span data-stu-id="09a4a-232">It's considered to be a best practice to add comment based help to your functions so the people you're sharing them with will know how to use them.</span></span>

```powershell
function Get-MrAutoStoppedService {

<#
.SYNOPSIS
    Returns a list of services that are set to start automatically, are not
    currently running, excluding the services that are set to delayed start.

.DESCRIPTION
    Get-MrAutoStoppedService is a function that returns a list of services from
    the specified remote computer(s) that are set to start automatically, are not
    currently running, and it excludes the services that are set to start automatically
    with a delayed startup.

.PARAMETER ComputerName
    The remote computer(s) to check the status of the services on.

.PARAMETER Credential
    Specifies a user account that has permission to perform this action. The default
    is the current user.

.EXAMPLE
     Get-MrAutoStoppedService -ComputerName 'Server1', 'Server2'

.EXAMPLE
     'Server1', 'Server2' | Get-MrAutoStoppedService

.EXAMPLE
     Get-MrAutoStoppedService -ComputerName 'Server1' -Credential (Get-Credential)

.INPUTS
    String

.OUTPUTS
    PSCustomObject

.NOTES
    Author:  Mike F Robbins
    Website: http://mikefrobbins.com
    Twitter: @mikefrobbins
#>

    [CmdletBinding()]
    param (

    )

    #Function Body

}
```

<span data-ttu-id="09a4a-233">関数にコメント ベースのヘルプを追加すると、ユーザーが、既定の組み込みコマンドと同じようにヘルプを取得できます。</span><span class="sxs-lookup"><span data-stu-id="09a4a-233">When you add comment based help to your functions, help can be retrieved for them just like the default built-in commands.</span></span>

<span data-ttu-id="09a4a-234">PowerShell で関数を記述するためのすべての構文に、特に初心者は圧倒されるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="09a4a-234">All of the syntax for writing a function in PowerShell can seem overwhelming especially for someone who is just getting started.</span></span> <span data-ttu-id="09a4a-235">何かの構文を思い出せないときは、私はいつも別のモニターで ISE の 2 番目のコピーを開き、関数のコードを入力しながら、"Cmdlet (advanced function) - Complete" スニペットを表示します。</span><span class="sxs-lookup"><span data-stu-id="09a4a-235">Often times if I can't remember the syntax for something, I'll open a second copy of the ISE on a separate monitor and view the "Cmdlet (advanced function) - Complete" snippet while typing in the code for my function.</span></span> <span data-ttu-id="09a4a-236">スニペットにアクセスするには、PowerShell ISE で <kbd>Ctrl</kbd> + <kbd>J</kbd> キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="09a4a-236">Snippets can be accessed in the PowerShell ISE using the <kbd>Ctrl</kbd>+<kbd>J</kbd> key combination.</span></span>

## <a name="summary"></a><span data-ttu-id="09a4a-237">まとめ</span><span class="sxs-lookup"><span data-stu-id="09a4a-237">Summary</span></span>

<span data-ttu-id="09a4a-238">この章では、PowerShell での関数の記述に関する基本、たとえば、関数を高度な関数に変換する方法や、パラメーターの検証、詳細出力、パイプライン入力、エラー処理、コメントベースのヘルプなど、PowerShell 関数を記述するときに考慮する必要がある重要な要素について学習しました。</span><span class="sxs-lookup"><span data-stu-id="09a4a-238">In this chapter you've learned the basics of writing functions in PowerShell to include how to turn a function into an advanced function and some of the more important elements that you should consider when writing PowerShell functions such as parameter validation, verbose output, pipeline input, error handling, and comment based help.</span></span>

## <a name="review"></a><span data-ttu-id="09a4a-239">確認</span><span class="sxs-lookup"><span data-stu-id="09a4a-239">Review</span></span>

1. <span data-ttu-id="09a4a-240">PowerShell で承認されている動詞の一覧を取得するには、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="09a4a-240">How do you obtain a list of approved verbs in PowerShell?</span></span>
1. <span data-ttu-id="09a4a-241">PowerShell 関数を高度な関数に変換するには、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="09a4a-241">How do you turn a PowerShell function into an advanced function?</span></span>
1. <span data-ttu-id="09a4a-242">**WhatIf** パラメーターと **Confirm** パラメーターは、どのようなときに PowerShell 関数に追加する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="09a4a-242">When should **WhatIf** and **Confirm** parameters be added to your PowerShell functions?</span></span>
1. <span data-ttu-id="09a4a-243">終了しないエラーを終了するエラーに変換するには、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="09a4a-243">How do you turn a non-terminating error into a terminating one?</span></span>
1. <span data-ttu-id="09a4a-244">コメント ベースのヘルプを関数に追加する必要があるのは、なぜですか。</span><span class="sxs-lookup"><span data-stu-id="09a4a-244">Why should you add comment based help to your functions?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="09a4a-245">推奨トピック</span><span class="sxs-lookup"><span data-stu-id="09a4a-245">Recommended Reading</span></span>

- <span data-ttu-id="09a4a-246">[about_Functions][]</span><span class="sxs-lookup"><span data-stu-id="09a4a-246">[about_Functions][]</span></span>
- <span data-ttu-id="09a4a-247">[about_Functions_Advanced_Parameters][]</span><span class="sxs-lookup"><span data-stu-id="09a4a-247">[about_Functions_Advanced_Parameters][]</span></span>
- <span data-ttu-id="09a4a-248">[about_CommonParameters][]</span><span class="sxs-lookup"><span data-stu-id="09a4a-248">[about_CommonParameters][]</span></span>
- <span data-ttu-id="09a4a-249">[about_Functions_CmdletBindingAttribute][]</span><span class="sxs-lookup"><span data-stu-id="09a4a-249">[about_Functions_CmdletBindingAttribute][]</span></span>
- <span data-ttu-id="09a4a-250">[about_Functions_Advanced][]</span><span class="sxs-lookup"><span data-stu-id="09a4a-250">[about_Functions_Advanced][]</span></span>
- <span data-ttu-id="09a4a-251">[about_Try_Catch_Finally][]</span><span class="sxs-lookup"><span data-stu-id="09a4a-251">[about_Try_Catch_Finally][]</span></span>
- <span data-ttu-id="09a4a-252">[about_Comment_Based_Help][]</span><span class="sxs-lookup"><span data-stu-id="09a4a-252">[about_Comment_Based_Help][]</span></span>
- <span data-ttu-id="09a4a-253">[ビデオ:高度な関数とスクリプト モジュールを使用した PowerShell でのツール作成][]</span><span class="sxs-lookup"><span data-stu-id="09a4a-253">[Video: PowerShell Toolmaking with Advanced Functions and Script Modules][]</span></span>

<!-- link references -->
[about_Functions]: /powershell/module/microsoft.powershell.core/about/about_functions
[about_Functions_Advanced_Parameters]: /powershell/module/microsoft.powershell.core/about/about_functions_advanced_parameters
[about_CommonParameters]: /powershell/module/microsoft.powershell.core/about/about_commonparameters
[about_Functions_CmdletBindingAttribute]: /powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute
[about_Functions_Advanced]: /powershell/module/microsoft.powershell.core/about/about_functions_advanced
[about_Try_Catch_Finally]: /powershell/module/microsoft.powershell.core/about/about_try_catch_finally
[about_Comment_Based_Help]: /powershell/module/microsoft.powershell.core/about/about_comment_based_help
[ビデオ:高度な関数とスクリプト モジュールを使用した PowerShell でのツール作成]: https://mikefrobbins.com/2016/05/26/video-powershell-toolmaking-with-advanced-functions-and-script-modules/) [Pascal case]: /dotnet/standard/design-guidelines/capitalization-conventions
[Video: PowerShell Toolmaking with Advanced Functions and Script Modules]: https://mikefrobbins.com/2016/05/26/video-powershell-toolmaking-with-advanced-functions-and-script-modules/) [Pascal case]: /dotnet/standard/design-guidelines/capitalization-conventionss
