---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-pssession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PSSession
ms.openlocfilehash: 1a87783f9d12d852d3a6809e9457a55ad6e7be50
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602177"
---
# <span data-ttu-id="df6a1-102">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="df6a1-102">Import-PSSession</span></span>

## <span data-ttu-id="df6a1-103">概要</span><span class="sxs-lookup"><span data-stu-id="df6a1-103">SYNOPSIS</span></span>
<span data-ttu-id="df6a1-104">別のセッションから現在のセッションにコマンドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="df6a1-104">Imports commands from another session into the current session.</span></span>

## <span data-ttu-id="df6a1-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="df6a1-105">SYNTAX</span></span>

```
Import-PSSession [-Prefix <String>] [-DisableNameChecking] [[-CommandName] <String[]>] [-AllowClobber]
 [-ArgumentList <Object[]>] [-CommandType <CommandTypes>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-FormatTypeName] <String[]>]
 [-Certificate <X509Certificate2>] [-Session] <PSSession> [<CommonParameters>]
```

## <span data-ttu-id="df6a1-106">Description</span><span class="sxs-lookup"><span data-stu-id="df6a1-106">DESCRIPTION</span></span>

<span data-ttu-id="df6a1-107">コマンドレットは、コマンド `Import-PSSession` レット、関数、エイリアスなどのコマンドを、ローカルコンピューターまたはリモートコンピューター上の PSSession から現在のセッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="df6a1-107">The `Import-PSSession` cmdlet imports commands , such as cmdlets, functions, and aliases, from a PSSession on a local or remote computer into the current session.</span></span> <span data-ttu-id="df6a1-108">コマンド `Get-Command` レットが PSSession で検索できる任意のコマンドをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-108">You can import any command that the `Get-Command` cmdlet can find in the PSSession.</span></span>

<span data-ttu-id="df6a1-109">コマンドを使用し `Import-PSSession` て、Microsoft Exchange Server シェルなどのカスタマイズされたシェルから、または、現在のセッションに含まれていない Windows PowerShell モジュールやスナップインなどの要素を含むセッションからコマンドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="df6a1-109">Use an `Import-PSSession` command to import commands from a customized shell, such as a Microsoft Exchange Server shell, or from a session that includes Windows PowerShell modules and snap-ins or other elements that are not in the current session.</span></span>

<span data-ttu-id="df6a1-110">コマンドをインポートするには、まず、コマンドレットを使用して `New-PSSession` PSSession を作成します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-110">To import commands, first use the `New-PSSession` cmdlet to create a PSSession.</span></span> <span data-ttu-id="df6a1-111">次に、コマンドレットを使用し `Import-PSSession` てコマンドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="df6a1-111">Then, use the `Import-PSSession` cmdlet to import the commands.</span></span> <span data-ttu-id="df6a1-112">既定では、は、 `Import-PSSession` 現在のセッションのコマンドと同じ名前のコマンドを除くすべてのコマンドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="df6a1-112">By default, `Import-PSSession` imports all commands except for commands that have the same names as commands in the current session.</span></span> <span data-ttu-id="df6a1-113">すべてのコマンドをインポートするには、**AllowClobber** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-113">To import all the commands, use the **AllowClobber** parameter.</span></span>

<span data-ttu-id="df6a1-114">インポートしたコマンドは、セッションのコマンドを使用する場合と同じように使用できます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-114">You can use imported commands just as you would use any command in the session.</span></span> <span data-ttu-id="df6a1-115">インポートしたコマンドを使用すると、インポートした部分のコマンドがインポート元のセッションで暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-115">When you use an imported command, the imported part of the command runs implicitly in the session from which it was imported.</span></span> <span data-ttu-id="df6a1-116">ただし、リモート操作はすべて Windows PowerShell によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-116">However, the remote operations are handled entirely by Windows PowerShell.</span></span> <span data-ttu-id="df6a1-117">リモート操作に注意を払う必要はありませんが、もう一方のセッション (PSSession) への接続を開いたままにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df6a1-117">You need not even be aware of them, except that you must keep the connection to the other session (PSSession) open.</span></span> <span data-ttu-id="df6a1-118">接続を閉じると、インポートしたコマンドを利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="df6a1-118">If you close it, the imported commands are no longer available.</span></span>

<span data-ttu-id="df6a1-119">インポートされたコマンドはローカルコマンドよりも実行に時間がかかる場合があるため、 `Import-PSSession` インポートされたすべてのコマンドに **AsJob** パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-119">Because imported commands might take longer to run than local commands, `Import-PSSession` adds an **AsJob** parameter to every imported command.</span></span> <span data-ttu-id="df6a1-120">このパラメーターを使用すると、コマンドを Windows PowerShell のバックグラウンド ジョブとして実行することができます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-120">This parameter allows you to run the command as a Windows PowerShell background job.</span></span> <span data-ttu-id="df6a1-121">詳細については、「[about_Jobs](../Microsoft.PowerShell.Core/about/about_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df6a1-121">For more information, see [about_Jobs](../Microsoft.PowerShell.Core/about/about_Jobs.md).</span></span>

<span data-ttu-id="df6a1-122">を使用すると `Import-PSSession` 、Windows PowerShell は、インポートされたコマンドをセッションにのみ存在する一時モジュールに追加し、モジュールを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-122">When you use `Import-PSSession`, Windows PowerShell adds the imported commands to a temporary module that exists only in your session and returns an object that represents the module.</span></span> <span data-ttu-id="df6a1-123">今後のセッションで使用できる永続的なモジュールを作成するには、 `Export-PSSession` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-123">To create a persistent module that you can use in future sessions, use the `Export-PSSession` cmdlet.</span></span>

<span data-ttu-id="df6a1-124">この `Import-PSSession` コマンドレットは、Windows PowerShell の暗黙的なリモート処理機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-124">The `Import-PSSession` cmdlet uses the implicit remoting feature of Windows PowerShell.</span></span> <span data-ttu-id="df6a1-125">現在のセッションにコマンドをインポートすると、元のセッションまたは元のコンピューターの同様のセッションで、コマンドが暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-125">When you import commands into the current session, they run implicitly in the original session or in a similar session on the originating computer.</span></span>

<span data-ttu-id="df6a1-126">Windows PowerShell 3.0 以降では、コマンドレットを使用して、 `Import-Module` リモートセッションから現在のセッションにモジュールをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-126">Beginning in Windows PowerShell 3.0, you can use the `Import-Module` cmdlet to import modules from a remote session into the current session.</span></span> <span data-ttu-id="df6a1-127">この機能では、暗黙的なリモート処理が使用されます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-127">This feature uses implicit remoting.</span></span> <span data-ttu-id="df6a1-128">これは、を使用して、 `Import-PSSession` リモートセッションから選択したモジュールを現在のセッションにインポートすることと同じです。</span><span class="sxs-lookup"><span data-stu-id="df6a1-128">It is equivalent to using `Import-PSSession` to import selected modules from a remote session into the current session.</span></span>

## <span data-ttu-id="df6a1-129">例</span><span class="sxs-lookup"><span data-stu-id="df6a1-129">EXAMPLES</span></span>

### <span data-ttu-id="df6a1-130">例 1: PSSession からすべてのコマンドをインポートする</span><span class="sxs-lookup"><span data-stu-id="df6a1-130">Example 1: Import all commands from a PSSession</span></span>

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Import-PSSession -Session $S
```

<span data-ttu-id="df6a1-131">このコマンドは、Server01 コンピューターの PSSession から現在のセッションに、現在のセッションのコマンドと同じ名前のコマンドを除くすべてのコマンドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="df6a1-131">This command imports all commands from a PSSession on the Server01 computer into the current session, except for commands that have the same names as commands in the current session.</span></span>

<span data-ttu-id="df6a1-132">このコマンドでは **CommandName** パラメーターを使用しないため、インポートされたコマンドに必要な書式データもすべてインポートされます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-132">Because this command does not use the **CommandName** parameter, it also imports all of the formatting data required for the imported commands.</span></span>

### <span data-ttu-id="df6a1-133">例 2: 特定の文字列で終わるコマンドをインポートする</span><span class="sxs-lookup"><span data-stu-id="df6a1-133">Example 2: Import commands that end with a specific string</span></span>

```
PS C:\> $S = New-PSSession https://ps.testlabs.com/powershell
PS C:\> Import-PSSession -Session $S -CommandName *-test -FormatTypeName *
PS C:\> New-Test -Name Test1
PS C:\> Get-Test test1 | Run-Test
```

<span data-ttu-id="df6a1-134">これらのコマンドは、PSSession からローカル セッションに名前が "-test" で終わるコマンドをインポートします。その後、インポートしたコマンドレットを使用する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-134">These commands import the commands with names that end in "-test" from a PSSession into the local session, and then they show how to use an imported cmdlet.</span></span>

<span data-ttu-id="df6a1-135">最初のコマンドは、コマンドレットを使用して `New-PSSession` PSSession を作成します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-135">The first command uses the `New-PSSession` cmdlet to create a PSSession.</span></span> <span data-ttu-id="df6a1-136">このメソッドは、PSSession を変数に保存し `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-136">It saves the PSSession in the `$S` variable.</span></span>

<span data-ttu-id="df6a1-137">2番目のコマンドは、コマンドレットを使用して、 `Import-PSSession` の PSSession から現在のセッションにコマンドをインポートし `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-137">The second command uses the `Import-PSSession` cmdlet to import commands from the PSSession in `$S` into the current session.</span></span> <span data-ttu-id="df6a1-138">**CommandName** パラメーターを使用して "Test" という名詞を含むコマンドを指定し、**FormatTypeName** パラメーターを使用して Test コマンドの書式データをインポートします。</span><span class="sxs-lookup"><span data-stu-id="df6a1-138">It uses the **CommandName** parameter to specify commands with the Test noun and the **FormatTypeName** parameter to import the formatting data for the Test commands.</span></span>

<span data-ttu-id="df6a1-139">3 番目と 4 番目のコマンドは、現在のセッションでインポートされたコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-139">The third and fourth commands use the imported commands in the current session.</span></span> <span data-ttu-id="df6a1-140">インポートされたコマンドは、現在のセッションに実際に追加されるため、ローカル構文を使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-140">Because imported commands are actually added to the current session, you use the local syntax to run them.</span></span> <span data-ttu-id="df6a1-141">インポートされた `Invoke-Command` コマンドを実行するためにコマンドレットを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="df6a1-141">You do not need to use the `Invoke-Command` cmdlet to run an imported command.</span></span>

### <span data-ttu-id="df6a1-142">例 3: PSSession からコマンドレットをインポートする</span><span class="sxs-lookup"><span data-stu-id="df6a1-142">Example 3: Import cmdlets from a PSSession</span></span>

```
PS C:\> $S1 = New-PSSession -ComputerName s1
PS C:\> $S2 = New-PSSession -ComputerName s2
PS C:\> Import-PSSession -Session s1 -Type cmdlet -Name New-Test, Get-Test -FormatTypeName *
PS C:\> Import-PSSession -Session s2 -Type Cmdlet -Name Set-Test -FormatTypeName *
PS C:\> New-Test Test1 | Set-Test -RunType Full
```

<span data-ttu-id="df6a1-143">この例では、ローカルのコマンドレットを使用するのと同じように、インポートされたコマンドレットを使用できることを示します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-143">This example shows that you can use imported cmdlets just as you would use local cmdlets.</span></span>

<span data-ttu-id="df6a1-144">これらのコマンドは、Server01 コンピューターの PSSession からコマンドレットとコマンドレットをインポートし、 `New-Test` `Get-Test` `Set-Test` Server02 コンピューターの pssession からコマンドレットをインポートします。</span><span class="sxs-lookup"><span data-stu-id="df6a1-144">These commands import the `New-Test` and `Get-Test` cmdlets from a PSSession on the Server01 computer and the `Set-Test` cmdlet from a PSSession on the Server02 computer.</span></span>

<span data-ttu-id="df6a1-145">別々の PSSession からコマンドレットをインポートした場合でも、パイプを使用して 1 つのコマンドレットから別のコマンドレットにオブジェクトを渡すことができます。エラーにはなりません。</span><span class="sxs-lookup"><span data-stu-id="df6a1-145">Even though the cmdlets were imported from different PSSessions, you can pipe an object from one cmdlet to another without error.</span></span>

### <span data-ttu-id="df6a1-146">例 4: インポートされたコマンドをバックグラウンドジョブとして実行する</span><span class="sxs-lookup"><span data-stu-id="df6a1-146">Example 4: Run an imported command as a background job</span></span>

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Import-PSSession -Session $S -CommandName *-test* -FormatTypeName *
PS C:\> $batch = New-Test -Name Batch -AsJob
PS C:\> Receive-Job $batch
```

<span data-ttu-id="df6a1-147">この例では、インポートしたコマンドをバックグラウンド ジョブとして実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-147">This example shows how to run an imported command as a background job.</span></span>

<span data-ttu-id="df6a1-148">インポートされたコマンドはローカルコマンドよりも実行に時間がかかる場合があるため、 `Import-PSSession` インポートされたすべてのコマンドに **AsJob** パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-148">Because imported commands might take longer to run than local commands, `Import-PSSession` adds an **AsJob** parameter to every imported command.</span></span> <span data-ttu-id="df6a1-149">**AsJob** パラメーターを使用すると、コマンドをバックグラウンド ジョブとして実行できます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-149">The **AsJob** parameter lets you run the command as a background job.</span></span>

<span data-ttu-id="df6a1-150">最初のコマンドは、Server01 コンピューター上に PSSession を作成し、その変数に PSSession オブジェクトを保存し `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-150">The first command creates a PSSession on the Server01 computer and saves the PSSession object in the `$S` variable.</span></span>

<span data-ttu-id="df6a1-151">2番目のコマンドは、を使用して、 `Import-PSSession` の PSSession から現在のセッションにテストコマンドレットをインポートし `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-151">The second command uses `Import-PSSession` to import the Test cmdlets from the PSSession in `$S` into the current session.</span></span>

<span data-ttu-id="df6a1-152">3番目のコマンドは、インポートされたコマンドレットの **AsJob** パラメーターを使用し `New-Test` て、 `New-Test` バックグラウンドジョブとしてコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-152">The third command uses the **AsJob** parameter of the imported `New-Test` cmdlet to run a `New-Test` command as a background job.</span></span> <span data-ttu-id="df6a1-153">このコマンドは、を返すジョブオブジェクトを `New-Test` 変数に保存し `$batch` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-153">The command saves the job object that `New-Test` returns in the `$batch` variable.</span></span>

<span data-ttu-id="df6a1-154">4番目のコマンドは、コマンドレットを使用して、 `Receive-Job` 変数内のジョブの結果を取得し `$batch` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-154">The fourth command uses the `Receive-Job` cmdlet to get the results of the job in the `$batch` variable.</span></span>

### <span data-ttu-id="df6a1-155">例 5: Windows PowerShell モジュールからコマンドレットと関数をインポートする</span><span class="sxs-lookup"><span data-stu-id="df6a1-155">Example 5: Import cmdlets and functions from a Windows PowerShell module</span></span>

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Invoke-Command -Session $S {Import-Module TestManagement}
PS C:\> Import-PSSession -Session $S -Module TestManagement
```

<span data-ttu-id="df6a1-156">この例では、リモート コンピューターの Windows PowerShell モジュールから現在のセッションにコマンドレットと関数をインポートする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-156">This example shows how to import the cmdlets and functions from a Windows PowerShell module on a remote computer into the current session.</span></span>

<span data-ttu-id="df6a1-157">最初のコマンドは、Server01 コンピューター上に PSSession を作成し、変数に保存し `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-157">The first command creates a PSSession on the Server01 computer and saves it in the `$S` variable.</span></span>

<span data-ttu-id="df6a1-158">2番目のコマンドは、コマンドレットを使用して、 `Invoke-Command` `Import-Module` の PSSession でコマンドを実行し `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-158">The second command uses the `Invoke-Command` cmdlet to run an `Import-Module` command in the PSSession in `$S`.</span></span>

<span data-ttu-id="df6a1-159">通常、モジュールは Windows PowerShell プロファイルのコマンドによってすべてのセッションに追加され `Import-Module` ますが、プロファイルは PSSessions では実行されません。</span><span class="sxs-lookup"><span data-stu-id="df6a1-159">Typically, the module would be added to all sessions by an `Import-Module` command in a Windows PowerShell profile, but profiles are not run in PSSessions.</span></span>

<span data-ttu-id="df6a1-160">3番目のコマンドは、の **module** パラメーターを使用して、 `Import-PSSession` モジュール内のコマンドレットと関数を現在のセッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="df6a1-160">The third command uses the **Module** parameter of `Import-PSSession` to import the cmdlets and functions in the module into the current session.</span></span>

### <span data-ttu-id="df6a1-161">例 6: 一時ファイルにモジュールを作成する</span><span class="sxs-lookup"><span data-stu-id="df6a1-161">Example 6: Create a module in a temporary file</span></span>

```
PS C:\> Import-PSSession $S -CommandName Get-Date, SearchHelp -FormatTypeName * -AllowClobber

Name              : tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf
Path              : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1
zunz.ttf\tmp_79468106-4e1d-4d90-af97-1154f9317239_
tcw1zunz.ttf.psm1
Description       : Implicit remoting for http://server01.corp.fabrikam.com/wsman
Guid              : 79468106-4e1d-4d90-af97-1154f9317239
Version           : 1.0
ModuleBase        : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1
zunz.ttf
ModuleType        : Script
PrivateData       : {ImplicitRemoting}
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Get-Date, Get-Date], [SearchHelp, SearchHelp]}
ExportedVariables : {}
NestedModules     : {}
```

<span data-ttu-id="df6a1-162">この例では、が `Import-PSSession` ディスク上の一時ファイルにモジュールを作成することを示しています。</span><span class="sxs-lookup"><span data-stu-id="df6a1-162">This example shows that `Import-PSSession` creates a module in a temporary file on disk.</span></span> <span data-ttu-id="df6a1-163">また、現在のセッションにインポートする前に、すべてのコマンドを関数に変換します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-163">It also shows that all commands are converted into functions before they are imported into the current session.</span></span>

<span data-ttu-id="df6a1-164">このコマンドは、コマンドレットを使用して、 `Import-PSSession` `Get-Date` 現在のセッションにコマンドレットと searchhelp 関数をインポートします。</span><span class="sxs-lookup"><span data-stu-id="df6a1-164">The command uses the `Import-PSSession` cmdlet to import a `Get-Date` cmdlet and a SearchHelp function into the current session.</span></span>

<span data-ttu-id="df6a1-165">この `Import-PSSession` コマンドレットは、一時モジュールを表す **PSModuleInfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-165">The `Import-PSSession` cmdlet returns a **PSModuleInfo** object that represents the temporary module.</span></span> <span data-ttu-id="df6a1-166">**Path** プロパティの値は、によって `Import-PSSession` スクリプトモジュール (hbase-runner.psm1) ファイルが一時的な場所に作成されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-166">The value of the **Path** property shows that `Import-PSSession` created a script module (.psm1) file in a temporary location.</span></span> <span data-ttu-id="df6a1-167">**ExportedFunctions** プロパティは、 `Get-Date` コマンドレットと searchhelp 関数が両方とも関数としてインポートされたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="df6a1-167">The **ExportedFunctions** property shows that the `Get-Date` cmdlet and the SearchHelp function were both imported as functions.</span></span>

### <span data-ttu-id="df6a1-168">例 7: インポートされたコマンドによって非表示になっているコマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="df6a1-168">Example 7: Run a command that is hidden by an imported command</span></span>

```
PS C:\> Import-PSSession $S -CommandName Get-Date -FormatTypeName * -AllowClobber

PS C:\> Get-Command Get-Date -All

CommandType   Name       Definition
-----------   ----       ----------
Function      Get-Date   ...
Cmdlet        Get-Date   Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>]

PS C:\> Get-Date
09074

PS C:\> (Get-Command -Type Cmdlet -Name Get-Date).PSSnapin.Name
Microsoft.PowerShell.Utility

PS C:\> Microsoft.PowerShell.Utility\Get-Date
Sunday, March 15, 2009 2:08:26 PM
```

<span data-ttu-id="df6a1-169">この例では、インポートされたコマンドによって非表示になったコマンドを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-169">This example shows how to run a command that is hidden by an imported command.</span></span>

<span data-ttu-id="df6a1-170">最初のコマンドは、 `Get-Date` 変数の PSSession からコマンドレットをインポートし `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-170">The first command imports a `Get-Date` cmdlet from the PSSession in the `$S` variable.</span></span> <span data-ttu-id="df6a1-171">現在のセッションにはコマンドレットが含まれているため、 `Get-Date` コマンドでは **AllowClobber** パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="df6a1-171">Because the current session includes a `Get-Date` cmdlet, the **AllowClobber** parameter is required in the command.</span></span>

<span data-ttu-id="df6a1-172">2番目のコマンドは、コマンドレットの **all** パラメーターを使用して、 `Get-Command` 現在のセッションのすべてのコマンドを取得し `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-172">The second command uses the **All** parameter of the `Get-Command` cmdlet to get all `Get-Date` commands in the current session.</span></span> <span data-ttu-id="df6a1-173">出力には、セッションに元のコマンドレットと関数が含まれていることが示されて `Get-Date` `Get-Date` います。</span><span class="sxs-lookup"><span data-stu-id="df6a1-173">The output shows that the session includes the original `Get-Date` cmdlet and a `Get-Date` function.</span></span> <span data-ttu-id="df6a1-174">関数は、 `Get-Date` の PSSession でインポートされたコマンドレットを実行し `Get-Date` `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-174">The `Get-Date` function runs the imported `Get-Date` cmdlet in the PSSession in `$S`.</span></span>

<span data-ttu-id="df6a1-175">3番目のコマンドは、コマンドを実行し `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-175">The third command runs a `Get-Date` command.</span></span> <span data-ttu-id="df6a1-176">関数はコマンドレットよりも優先されるため、Windows PowerShell はインポートされた関数を実行します `Get-Date` 。これにより、ユリウス暦の日付が返されます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-176">Because functions take precedence over cmdlets, Windows PowerShell runs the imported `Get-Date` function, which returns a Julian date.</span></span>

<span data-ttu-id="df6a1-177">4 番目と 5 番目のコマンドは、修飾名を使用して、インポートされたコマンドによって非表示になったコマンドを実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="df6a1-177">The fourth and fifth commands show how to use a qualified name to run a command that is hidden by an imported command.</span></span>

<span data-ttu-id="df6a1-178">4番目のコマンドは、元のコマンドレットを現在のセッションに追加した Windows PowerShell スナップインの名前を取得し `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-178">The fourth command gets the name of the Windows PowerShell snap-in that added the original `Get-Date` cmdlet to the current session.</span></span>

<span data-ttu-id="df6a1-179">5番目のコマンドは、コマンドレットのスナップインによって修飾された名前を使用して、 `Get-Date` コマンドを実行し `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-179">The fifth command uses the snap-in-qualified name of the `Get-Date` cmdlet to run a `Get-Date` command.</span></span>

<span data-ttu-id="df6a1-180">コマンドの優先順位と非表示のコマンドの詳細については、「[about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df6a1-180">For more information about command precedence and hidden commands, see [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).</span></span>

### <span data-ttu-id="df6a1-181">例 8: 名前に特定の文字列が含まれているコマンドをインポートする</span><span class="sxs-lookup"><span data-stu-id="df6a1-181">Example 8: Import commands that have a specific string in their names</span></span>

```
PS C:\> Import-PSSession -Session $S -CommandName **Item** -AllowClobber
```

<span data-ttu-id="df6a1-182">このコマンドは、の PSSession からの項目を含む名前を持つコマンドをインポート `$S` します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-182">This command imports commands whose names include Item from the PSSession in `$S`.</span></span> <span data-ttu-id="df6a1-183">このコマンドには、 **CommandName** パラメーターは含まれていますが、 **formattypedata** パラメーターは含まれていないため、コマンドのみがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-183">Because the command includes the **CommandName** parameter but not the **FormatTypeData** parameter, only the command is imported.</span></span>

<span data-ttu-id="df6a1-184">このコマンドは、を使用して `Import-PSSession` リモートコンピューターでコマンドを実行し、現在のセッションでコマンドの書式データを既に持っている場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-184">Use this command when you are using `Import-PSSession` to run a command on a remote computer and you already have the formatting data for the command in the current session.</span></span>

### <span data-ttu-id="df6a1-185">例 9: モジュールパラメーターを使用して、セッションにインポートされたコマンドを検出する</span><span class="sxs-lookup"><span data-stu-id="df6a1-185">Example 9: Use the Module parameter to discover which commands were imported into the session</span></span>

```
PS C:\> $M = Import-PSSession -Session $S -CommandName *bits* -FormatTypeName *bits*
PS C:\> Get-Command -Module $M
CommandType     Name
-----------     ----
Function        Add-BitsFile
Function        Complete-BitsTransfer
Function        Get-BitsTransfer
Function        Remove-BitsTransfer
Function        Resume-BitsTransfer
Function        Set-BitsTransfer
Function        Start-BitsTransfer
Function        Suspend-BitsTransfer
```

<span data-ttu-id="df6a1-186">このコマンドは、の **Module** パラメーターを使用し `Get-Command` て、コマンドによってセッションにインポートされたコマンドを確認する方法を示して `Import-PSSession` います。</span><span class="sxs-lookup"><span data-stu-id="df6a1-186">This command shows how to use the **Module** parameter of `Get-Command` to find out which commands were imported into the session by an `Import-PSSession` command.</span></span>

<span data-ttu-id="df6a1-187">最初のコマンドは、コマンドレットを使用して、 `Import-PSSession` 変数の PSSession から "bits" を含む名前のコマンドをインポートし `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-187">The first command uses the `Import-PSSession` cmdlet to import commands whose names include "bits" from the PSSession in the `$S` variable.</span></span> <span data-ttu-id="df6a1-188">`Import-PSSession`コマンドは一時モジュールを返し、モジュールは変数に保存され `$m` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-188">The `Import-PSSession` command returns a temporary module, and the command saves the module in the `$m` variable.</span></span>

<span data-ttu-id="df6a1-189">2番目のコマンドは、コマンドレットを使用し `Get-Command` て、変数内のモジュールによってエクスポートされたコマンドを取得し `$M` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-189">The second command uses the `Get-Command` cmdlet to get the commands that are exported by the module in the `$M` variable.</span></span>

<span data-ttu-id="df6a1-190">**Module** パラメーターは、モジュール名用に設計されており、文字列値を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="df6a1-190">The **Module** parameter takes a string value, which is designed for the module name.</span></span> <span data-ttu-id="df6a1-191">ただし、モジュール オブジェクトを渡すと、Windows PowerShell は、モジュール オブジェクトの **ToString** メソッドを使用して、モジュール名を返します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-191">However, when you submit a module object, Windows PowerShell uses the **ToString** method on the module object, which returns the module name.</span></span>

<span data-ttu-id="df6a1-192">コマンドは、 `Get-Command` "" に相当し `Get-Command $M.Name` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-192">The `Get-Command` command is the equivalent of `Get-Command $M.Name`".</span></span>

## <span data-ttu-id="df6a1-193">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="df6a1-193">PARAMETERS</span></span>

### <span data-ttu-id="df6a1-194">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="df6a1-194">-AllowClobber</span></span>

<span data-ttu-id="df6a1-195">このコマンドレットが、現在のセッションのコマンドと同じ名前を持つ場合でも、指定したコマンドをインポートすることを示します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-195">Indicates that this cmdlet imports the specified commands, even if they have the same names as commands in the current session.</span></span>

<span data-ttu-id="df6a1-196">現在のセッションにあるコマンドと同じ名前のコマンドをインポートする場合、インポートされたコマンドを非表示にするか、元のコマンドを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-196">If you import a command with the same name as a command in the current session, the imported command hides or replaces the original commands.</span></span> <span data-ttu-id="df6a1-197">詳細については、「[about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md)」(コマンドの優先順位について) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df6a1-197">For more information, see [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).</span></span>

<span data-ttu-id="df6a1-198">既定で `Import-PSSession` は、は、現在のセッションのコマンドと同じ名前のコマンドをインポートしません。</span><span class="sxs-lookup"><span data-stu-id="df6a1-198">By default, `Import-PSSession` does not import commands that have the same name as commands in the current session.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df6a1-199">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="df6a1-199">-ArgumentList</span></span>

<span data-ttu-id="df6a1-200">指定された引数 (パラメーター値) を使用した結果として得られるコマンドの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-200">Specifies an array of commands that results from using the specified arguments (parameter values).</span></span>

<span data-ttu-id="df6a1-201">たとえば、 `Get-Item` 証明書 (Cert:) のコマンドのバリアントをインポートするには、の PSSession のドライブに `$S` 、「」と入力 `Import-PSSession -Session $S -Command Get-Item -ArgumentList cert:` します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-201">For instance, to import the variant of the `Get-Item` command in the certificate (Cert:) drive in the PSSession in `$S`, type `Import-PSSession -Session $S -Command Get-Item -ArgumentList cert:`.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df6a1-202">-証明書</span><span class="sxs-lookup"><span data-stu-id="df6a1-202">-Certificate</span></span>

<span data-ttu-id="df6a1-203">が作成する一時モジュール内のフォーマットファイル (\* .Format.ps1xml) またはスクリプトモジュールファイル (hbase-runner.psm1) の署名に使用されるクライアント証明書を指定し `Import-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-203">Specifies the client certificate that is used to sign the format files (\*.Format.ps1xml) or script module files (.psm1) in the temporary module that `Import-PSSession` creates.</span></span>

<span data-ttu-id="df6a1-204">証明書が格納されている変数を入力するか、証明書を取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-204">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="df6a1-205">証明書を検索するには、コマンドレットを使用する `Get-PfxCertificate` か、 `Get-ChildItem` 証明書 (Cert:) のコマンドレットを使用します。駆動.</span><span class="sxs-lookup"><span data-stu-id="df6a1-205">To find a certificate, use the `Get-PfxCertificate` cmdlet or use the `Get-ChildItem` cmdlet in the Certificate (Cert:) drive.</span></span> <span data-ttu-id="df6a1-206">証明書が無効な場合、または証明書に十分な権限がない場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-206">If the certificate is not valid or does not have sufficient authority, the command fails.</span></span>

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate2
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df6a1-207">-CommandName</span><span class="sxs-lookup"><span data-stu-id="df6a1-207">-CommandName</span></span>

<span data-ttu-id="df6a1-208">指定された名前または名前パターンのコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-208">Specifies commands with the specified names or name patterns.</span></span> <span data-ttu-id="df6a1-209">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-209">Wildcards are permitted.</span></span> <span data-ttu-id="df6a1-210">**CommandName** またはそのエイリアスである **Name** を使用します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-210">Use **CommandName** or its alias, **Name**.</span></span>

<span data-ttu-id="df6a1-211">既定では、は `Import-PSSession` セッションからすべてのコマンドをインポートします。ただし、現在のセッションのコマンドと同じ名前を持つコマンドは除きます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-211">By default, `Import-PSSession` imports all commands from the session, except for commands that have the same names as commands in the current session.</span></span> <span data-ttu-id="df6a1-212">そのため、インポート先のセッションでインポートしたコマンドが非表示になることや、置き換えられることがありません。</span><span class="sxs-lookup"><span data-stu-id="df6a1-212">This prevents imported commands from hiding or replacing commands in the session.</span></span> <span data-ttu-id="df6a1-213">非表示になったり、他のコマンドを置き換えたりするコマンドを含め、すべてのコマンドをインポートするには、**AllowClobber** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-213">To import all commands, even those that hide or replace other commands, use the **AllowClobber** parameter.</span></span>

<span data-ttu-id="df6a1-214">**CommandName** パラメーターを使用する場合は、**FormatTypeName** パラメーターを使用しない限り、コマンドの書式ファイルはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="df6a1-214">If you use the **CommandName** parameter, the formatting files for the commands are not imported unless you use the **FormatTypeName** parameter.</span></span> <span data-ttu-id="df6a1-215">同様に、**FormatTypeName** パラメーターを使用する場合は、**CommandName** パラメーターを使用しない限り、コマンドはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="df6a1-215">Similarly, if you use the **FormatTypeName** parameter, no commands are imported unless you use the **CommandName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df6a1-216">-CommandType</span><span class="sxs-lookup"><span data-stu-id="df6a1-216">-CommandType</span></span>

<span data-ttu-id="df6a1-217">コマンドオブジェクトの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-217">Specifies the type of command objects.</span></span> <span data-ttu-id="df6a1-218">既定値は Cmdlet です。</span><span class="sxs-lookup"><span data-stu-id="df6a1-218">The default value is Cmdlet.</span></span> <span data-ttu-id="df6a1-219">**CommandType** またはそのエイリアスの **Type** を使用します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-219">Use **CommandType** or its alias, **Type**.</span></span> <span data-ttu-id="df6a1-220">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df6a1-220">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="df6a1-221">エイリアス.</span><span class="sxs-lookup"><span data-stu-id="df6a1-221">Alias.</span></span> <span data-ttu-id="df6a1-222">リモート セッションの Windows PowerShell エイリアス。</span><span class="sxs-lookup"><span data-stu-id="df6a1-222">The Windows PowerShell aliases in the remote session.</span></span>
- <span data-ttu-id="df6a1-223">すべて。</span><span class="sxs-lookup"><span data-stu-id="df6a1-223">All.</span></span> <span data-ttu-id="df6a1-224">リモート セッションのコマンドレットと関数。</span><span class="sxs-lookup"><span data-stu-id="df6a1-224">The cmdlets and functions in the remote session.</span></span>
- <span data-ttu-id="df6a1-225">アプリケーション をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df6a1-225">Application.</span></span> <span data-ttu-id="df6a1-226">リモートセッションの Path 環境変数 () に一覧表示されているパス内のファイル Windows-PowerShell 以外のすべてのファイル ( `$env:path` .txt、.exe、.dll ファイルなど)。</span><span class="sxs-lookup"><span data-stu-id="df6a1-226">All the files other than Windows-PowerShell files in the paths that are listed in the Path environment variable (`$env:path`) in the remote session, including .txt, .exe, and .dll files.</span></span>
- <span data-ttu-id="df6a1-227">コマンドレット.</span><span class="sxs-lookup"><span data-stu-id="df6a1-227">Cmdlet.</span></span> <span data-ttu-id="df6a1-228">リモート セッションのコマンドレット。</span><span class="sxs-lookup"><span data-stu-id="df6a1-228">The cmdlets in the remote session.</span></span> <span data-ttu-id="df6a1-229">"Cmdlet" が既定値です。</span><span class="sxs-lookup"><span data-stu-id="df6a1-229">"Cmdlet" is the default.</span></span>
- <span data-ttu-id="df6a1-230">ExternalScript。</span><span class="sxs-lookup"><span data-stu-id="df6a1-230">ExternalScript.</span></span> <span data-ttu-id="df6a1-231">リモートセッションの Path 環境変数 () に一覧表示されているパス内の ps1 ファイル。 `$env:path`</span><span class="sxs-lookup"><span data-stu-id="df6a1-231">The .ps1 files in the paths listed in the Path environment variable (`$env:path`) in the remote session.</span></span>
- <span data-ttu-id="df6a1-232">フィルターと関数。</span><span class="sxs-lookup"><span data-stu-id="df6a1-232">Filter and Function.</span></span> <span data-ttu-id="df6a1-233">リモート セッションの Windows PowerShell 関数。</span><span class="sxs-lookup"><span data-stu-id="df6a1-233">The Windows PowerShell functions in the remote session.</span></span>
- <span data-ttu-id="df6a1-234">スクリプティング。</span><span class="sxs-lookup"><span data-stu-id="df6a1-234">Script.</span></span> <span data-ttu-id="df6a1-235">リモート セッションのスクリプト ブロック。</span><span class="sxs-lookup"><span data-stu-id="df6a1-235">The script blocks in the remote session.</span></span>

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: (All)
Aliases: Type
Accepted values: Alias, Function, Filter, Cmdlet, ExternalScript, Application, Script, Workflow, Configuration, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df6a1-236">-DisableNameChecking</span><span class="sxs-lookup"><span data-stu-id="df6a1-236">-DisableNameChecking</span></span>

<span data-ttu-id="df6a1-237">このコマンドレットが、許可されていない動詞または禁止された文字を含んでいる名前を持つコマンドレットまたは関数をインポートしたときに警告するメッセージを抑制することを示します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-237">Indicates that this cmdlet suppresses the message that warns you when you import a cmdlet or function whose name includes an unapproved verb or a prohibited character.</span></span>

<span data-ttu-id="df6a1-238">既定では、インポートしたモジュールが、名前に許可されていない動詞を持つコマンドレットまたは関数をエクスポートすると、Windows PowerShell によって次の警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-238">By default, when a module that you import exports cmdlets or functions that have unapproved verbs in their names, the Windows PowerShell displays the following warning message:</span></span>

<span data-ttu-id="df6a1-239">"警告: インポートされたコマンド名には、許可されていない動詞が含まれているため、検出できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="df6a1-239">"WARNING: Some imported command names include unapproved verbs which might make them less discoverable.</span></span> <span data-ttu-id="df6a1-240">詳細については Verbose パラメーターを使用し、承認された `Get-Verb` 動詞の一覧を表示するには「」と入力してください。</span><span class="sxs-lookup"><span data-stu-id="df6a1-240">Use the Verbose parameter for more detail or type `Get-Verb` to see the list of approved verbs."</span></span>

<span data-ttu-id="df6a1-241">このメッセージは、単なる警告です。</span><span class="sxs-lookup"><span data-stu-id="df6a1-241">This message is only a warning.</span></span> <span data-ttu-id="df6a1-242">実際には、非準拠のコマンドを含む、すべてのモジュールがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-242">The complete module is still imported, including the non-conforming commands.</span></span> <span data-ttu-id="df6a1-243">モジュール ユーザーにメッセージが表示されますが、名前付けの問題はモジュール作成者が解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df6a1-243">Although the message is displayed to module users, the naming problem should be fixed by the module author.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df6a1-244">-FormatTypeName</span><span class="sxs-lookup"><span data-stu-id="df6a1-244">-FormatTypeName</span></span>

<span data-ttu-id="df6a1-245">指定された Microsoft .NET Framework 型の書式設定命令を指定します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-245">Specifies formatting instructions for the specified Microsoft .NET Framework types.</span></span>
<span data-ttu-id="df6a1-246">型名を入力します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-246">Enter the type names.</span></span>
<span data-ttu-id="df6a1-247">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-247">Wildcards are permitted.</span></span>

<span data-ttu-id="df6a1-248">このパラメーターの値は、コマンドがインポートされるセッション内のコマンドによって返される型の名前である必要があり `Get-FormatData` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-248">The value of this parameter must be the name of a type that is returned by a `Get-FormatData` command in the session from which the commands are being imported.</span></span> <span data-ttu-id="df6a1-249">リモートセッションのすべての書式設定データを取得するには、「」と入力 `*` します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-249">To get all of the formatting data in the remote session, type `*`.</span></span>

<span data-ttu-id="df6a1-250">コマンドに **CommandName** パラメーターまたは **formattypename** パラメーターが含まれていない場合は、 `Import-PSSession` `Get-FormatData` リモートセッションでコマンドによって返されるすべての .NET Framework 型の書式設定命令をインポートします。</span><span class="sxs-lookup"><span data-stu-id="df6a1-250">If the command does not include either the **CommandName** or **FormatTypeName** parameter, `Import-PSSession` imports formatting instructions for all .NET Framework types returned by a `Get-FormatData` command in the remote session.</span></span>

<span data-ttu-id="df6a1-251">**FormatTypeName** パラメーターを使用する場合は、**CommandName** パラメーターを使用しない限り、コマンドはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="df6a1-251">If you use the **FormatTypeName** parameter, no commands are imported unless you use the **CommandName** parameter.</span></span>

<span data-ttu-id="df6a1-252">同様に、**CommandName** パラメーターを使用する場合は、**FormatTypeName** パラメーターを使用しない限り、コマンドの書式ファイルはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="df6a1-252">Similarly, if you use the **CommandName** parameter, the formatting files for the commands are not imported unless you use the **FormatTypeName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df6a1-253">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="df6a1-253">-FullyQualifiedModule</span></span>

<span data-ttu-id="df6a1-254">PowerShell SDK の Modulの **特定の**[コンストラクター (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_)の「解説」で説明されている名前を持つモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-254">Specifies modules with names that are specified in the form of **ModuleSpecification** objects (described in the Remarks section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_) in the PowerShell SDK.</span></span> <span data-ttu-id="df6a1-255">たとえば、 **FullyQualifiedModule** パラメーターは、次の形式で指定されたモジュール名を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-255">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in the format:</span></span>

- <span data-ttu-id="df6a1-256">`@{ModuleName = "modulename"; ModuleVersion = "version_number"}` または</span><span class="sxs-lookup"><span data-stu-id="df6a1-256">`@{ModuleName = "modulename"; ModuleVersion = "version_number"}` or</span></span>
- <span data-ttu-id="df6a1-257">`@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`.</span><span class="sxs-lookup"><span data-stu-id="df6a1-257">`@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`.</span></span>

<span data-ttu-id="df6a1-258">**ModuleName** と **ModuleVersion** は必須ですが、**Guid** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="df6a1-258">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="df6a1-259">**モジュール** パラメーターと同じコマンドで **FullyQualifiedModule** パラメーターを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="df6a1-259">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span> <span data-ttu-id="df6a1-260">2つのパラメーターは相互に排他的です。</span><span class="sxs-lookup"><span data-stu-id="df6a1-260">The two parameters are mutually exclusive.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df6a1-261">-モジュール</span><span class="sxs-lookup"><span data-stu-id="df6a1-261">-Module</span></span>

<span data-ttu-id="df6a1-262">Windows PowerShell スナップインおよびモジュールのコマンドの配列とを指定します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-262">Specifies and array of commands in the Windows PowerShell snap-ins and modules.</span></span> <span data-ttu-id="df6a1-263">スナップインとモジュールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-263">Enter the snap-in and module names.</span></span> <span data-ttu-id="df6a1-264">ワイルドカードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="df6a1-264">Wildcards are not permitted.</span></span>

<span data-ttu-id="df6a1-265">`Import-PSSession` スナップインからプロバイダーをインポートできません。</span><span class="sxs-lookup"><span data-stu-id="df6a1-265">`Import-PSSession` cannot import providers from a snap-in.</span></span>

<span data-ttu-id="df6a1-266">詳細については、「[about_PSSnapins](/powershell/module/Microsoft.PowerShell.Core/About/about_PSSnapins)」と「[about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df6a1-266">For more information, see [about_PSSnapins](/powershell/module/Microsoft.PowerShell.Core/About/about_PSSnapins) and [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df6a1-267">-Prefix</span><span class="sxs-lookup"><span data-stu-id="df6a1-267">-Prefix</span></span>

<span data-ttu-id="df6a1-268">インポートされたコマンドの名前の名詞のプレフィックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-268">Specifies a prefix to the nouns in the names of imported commands.</span></span>

<span data-ttu-id="df6a1-269">セッションに同じ名前の別のコマンドが存在する場合に発生する名前の競合を回避するには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-269">Use this parameter to avoid name conflicts that might occur when different commands in the session have the same name.</span></span>

<span data-ttu-id="df6a1-270">たとえば、プレフィックス Remote を指定してからコマンドレットをインポートした場合、 `Get-Date` このコマンドレットはセッションではとして認識され、 `Get-RemoteDate` 元のコマンドレットと混同されることはありません `Get-Date` 。</span><span class="sxs-lookup"><span data-stu-id="df6a1-270">For instance, if you specify the prefix Remote and then import a `Get-Date` cmdlet, the cmdlet is known in the session as `Get-RemoteDate`, and it is not confused with the original `Get-Date` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df6a1-271">-セッション</span><span class="sxs-lookup"><span data-stu-id="df6a1-271">-Session</span></span>

<span data-ttu-id="df6a1-272">コマンドレットのインポート元の **PSSession** を指定します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-272">Specifies the **PSSession** from which the cmdlets are imported.</span></span> <span data-ttu-id="df6a1-273">セッションオブジェクトを含む変数、 `New-PSSession` またはコマンドやコマンドなどのセッションオブジェクトを取得するコマンドを入力し `Get-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-273">Enter a variable that contains a session object or a command that gets a session object, such as a `New-PSSession` or `Get-PSSession` command.</span></span> <span data-ttu-id="df6a1-274">指定できるセッションは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="df6a1-274">You can specify only one session.</span></span> <span data-ttu-id="df6a1-275">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="df6a1-275">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df6a1-276">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="df6a1-276">CommonParameters</span></span>

<span data-ttu-id="df6a1-277">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="df6a1-277">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="df6a1-278">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df6a1-278">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="df6a1-279">入力</span><span class="sxs-lookup"><span data-stu-id="df6a1-279">INPUTS</span></span>

### <span data-ttu-id="df6a1-280">なし</span><span class="sxs-lookup"><span data-stu-id="df6a1-280">None</span></span>

<span data-ttu-id="df6a1-281">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="df6a1-281">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="df6a1-282">出力</span><span class="sxs-lookup"><span data-stu-id="df6a1-282">OUTPUTS</span></span>

### <span data-ttu-id="df6a1-283">PSModuleInfo (システム管理)</span><span class="sxs-lookup"><span data-stu-id="df6a1-283">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="df6a1-284">`Import-PSSession` およびコマンドレットが返すのと同じモジュールオブジェクトを返し `New-Module` `Get-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-284">`Import-PSSession` returns the same module object that `New-Module` and `Get-Module` cmdlets return.</span></span>
<span data-ttu-id="df6a1-285">ただし、インポートされたモジュールは一時的なもので、現在のセッションにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-285">However, the imported module is temporary and exists only in the current session.</span></span> <span data-ttu-id="df6a1-286">ディスクにパーマネントモジュールを作成するには、 `Export-PSSession` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-286">To create a permanent module on disk, use the `Export-PSSession` cmdlet.</span></span>

## <span data-ttu-id="df6a1-287">注</span><span class="sxs-lookup"><span data-stu-id="df6a1-287">NOTES</span></span>

- <span data-ttu-id="df6a1-288">`Import-PSSession` は、PowerShell リモート処理インフラストラクチャに依存しています。</span><span class="sxs-lookup"><span data-stu-id="df6a1-288">`Import-PSSession` relies on the  PowerShell remoting infrastructure.</span></span> <span data-ttu-id="df6a1-289">このコマンドレットを使用するには、WS-Management リモート処理用にコンピューターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df6a1-289">To use this cmdlet, the computer must be configured for WS-Management remoting.</span></span> <span data-ttu-id="df6a1-290">詳細については、「 [about_Remote](../Microsoft.PowerShell.Core/about/about_Remote.md) 」および「 [about_Remote_Requirements](../Microsoft.PowerShell.Core/about/about_Remote_Requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df6a1-290">For more information, see [about_Remote](../Microsoft.PowerShell.Core/about/about_Remote.md) and [about_Remote_Requirements](../Microsoft.PowerShell.Core/about/about_Remote_Requirements.md).</span></span>
- <span data-ttu-id="df6a1-291">`Import-PSSession` では、変数または PowerShell プロバイダーはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="df6a1-291">`Import-PSSession` does not import variables or  PowerShell providers.</span></span>
- <span data-ttu-id="df6a1-292">現在のセッションのコマンドと同じ名前のコマンドをインポートすると、インポートされたコマンドによって、現在のセッションのエイリアス、関数、およびコマンドレットが非表示になったり、現在のセッションの関数や変数が置き換えられたりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="df6a1-292">When you import commands that have the same names as commands in the current session, the imported commands can hide aliases, functions, and cmdlets in the session and they can replace functions and variables in the session.</span></span> <span data-ttu-id="df6a1-293">名前の競合を回避するには、**Prefix** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-293">To prevent name conflicts, use the **Prefix** parameter.</span></span> <span data-ttu-id="df6a1-294">詳細については、「[about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md)」(コマンドの優先順位について) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df6a1-294">For more information, see [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).</span></span>
- <span data-ttu-id="df6a1-295">`Import-PSSession` すべてのコマンドをインポート前に関数に変換します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-295">`Import-PSSession` converts all commands into functions before it imports them.</span></span> <span data-ttu-id="df6a1-296">そのため、インポートされたコマンドの動作は、元のコマンドの種類が維持されている場合と少し異なります。</span><span class="sxs-lookup"><span data-stu-id="df6a1-296">As a result, imported commands behave a bit differently than they would if they retained their original command type.</span></span> <span data-ttu-id="df6a1-297">たとえば、PSSession からコマンドレットをインポートした後、モジュールまたはスナップインから同じ名前のコマンドレットをインポートした場合は、関数はコマンドレットよりも優先されるため、既定では PSSession からインポートしたコマンドレットが常に実行されます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-297">For example, if you import a cmdlet from a PSSession and then import a cmdlet with the same name from a module or snap-in, the cmdlet that is imported from the PSSession always runs by default because functions take precedence over cmdlets.</span></span> <span data-ttu-id="df6a1-298">また、同じ名前のエイリアスが存在するセッションにエイリアスをインポートした場合は、エイリアスは関数よりも優先されるため、元のエイリアスが常に使用されます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-298">Conversely, if you import an alias into a session that has an alias with the same name, the original alias is always used, because aliases take precedence over functions.</span></span> <span data-ttu-id="df6a1-299">詳細については、「[about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md)」(コマンドの優先順位について) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df6a1-299">For more information, see [about_Command_Precedence](../Microsoft.PowerShell.Core/about/about_Command_Precedence.md).</span></span>
- <span data-ttu-id="df6a1-300">`Import-PSSession` コマンドレットを使用して、 `Write-Progress` コマンドの進行状況を表示します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-300">`Import-PSSession` uses the `Write-Progress` cmdlet to display the progress of the command.</span></span> <span data-ttu-id="df6a1-301">コマンドが実行中の場合、進行状況バーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-301">You might see the progress bar while the command is running.</span></span>
- <span data-ttu-id="df6a1-302">インポートするコマンドを見つけるには、コマンドレットを使用して `Import-PSSession` `Invoke-Command` `Get-Command` PSSession でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-302">To find the commands to import, `Import-PSSession` uses the `Invoke-Command` cmdlet to run a `Get-Command` command in the PSSession.</span></span> <span data-ttu-id="df6a1-303">コマンドの書式設定データを取得するには、コマンドレットを使用し `Get-FormatData` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-303">To get formatting data for the commands, it uses the `Get-FormatData` cmdlet.</span></span> <span data-ttu-id="df6a1-304">コマンドを実行すると、これらのコマンドレットからのエラーメッセージが表示することがあり `Import-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="df6a1-304">You might see error messages from these cmdlets when you run an `Import-PSSession` command.</span></span> <span data-ttu-id="df6a1-305">また、、、 `Import-PSSession` `Get-Command` `Get-FormatData` `Select-Object` 、およびコマンドレットを含まない PSSession からコマンドをインポートすることはできません `Get-Help` 。</span><span class="sxs-lookup"><span data-stu-id="df6a1-305">Also, `Import-PSSession` cannot import commands from a PSSession that does not include the `Get-Command`, `Get-FormatData`, `Select-Object`, and `Get-Help` cmdlets.</span></span>
- <span data-ttu-id="df6a1-306">インポートされたコマンドには、ユーザー インターフェイスを備えたプログラム (たとえば、メモ帳) を起動できないなど、他のリモート コマンドと同じ制限があります。</span><span class="sxs-lookup"><span data-stu-id="df6a1-306">Imported commands have the same limitations as other remote commands, including the inability to start a program with a user interface, such as Notepad.</span></span>
- <span data-ttu-id="df6a1-307">Windows PowerShell プロファイルは PSSessions では実行されないため、プロファイルによってセッションに追加されたコマンドはでは使用できません `Import-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="df6a1-307">Because Windows PowerShell profiles are not run in PSSessions, the commands that a profile adds to a session are not available to `Import-PSSession`.</span></span> <span data-ttu-id="df6a1-308">プロファイルからコマンドをインポートするには、コマンドを使用して、コマンドをインポートする前に、コマンドを使用し `Invoke-Command` て PSSession でプロファイルを手動で実行します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-308">To import commands from a profile, use an `Invoke-Command` command to run the profile in the PSSession manually before importing commands.</span></span>
- <span data-ttu-id="df6a1-309">`Import-PSSession`コマンドで書式データがインポートされない場合でも、によって作成される一時モジュールには書式設定ファイルが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="df6a1-309">The temporary module that `Import-PSSession` creates might include a formatting file, even if the command does not import formatting data.</span></span> <span data-ttu-id="df6a1-310">コマンドで書式データがインポートされない場合、作成される書式ファイルに書式データは含まれません。</span><span class="sxs-lookup"><span data-stu-id="df6a1-310">If the command does not import formatting data, any formatting files that are created will not contain formatting data.</span></span>
- <span data-ttu-id="df6a1-311">を使用するには `Import-PSSession` 、現在のセッションの実行ポリシーを Restricted または AllSigned にすることはできません。作成される一時モジュールには、 `Import-PSSession` これらのポリシーで禁止されている未署名のスクリプトファイルが含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="df6a1-311">To use `Import-PSSession`, the execution policy in the current session cannot be Restricted or AllSigned, because the temporary module that `Import-PSSession` creates contains unsigned script files that are prohibited by these policies.</span></span> <span data-ttu-id="df6a1-312">`Import-PSSession`ローカルコンピューターの実行ポリシーを変更せずにを使用するには、の **Scope** パラメーターを使用して、 `Set-ExecutionPolicy` 1 つのプロセスに対してより制限の緩い実行ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-312">To use `Import-PSSession` without changing the execution policy for the local computer, use the **Scope** parameter of `Set-ExecutionPolicy` to set a less restrictive execution policy for a single process.</span></span>
- <span data-ttu-id="df6a1-313">Windows PowerShell 2.0 では、別のセッションからインポートしたコマンドのヘルプ トピックに、**Prefix** パラメーターを使用して割り当てたプレフィックスが含まれません。</span><span class="sxs-lookup"><span data-stu-id="df6a1-313">In Windows PowerShell 2.0, help topics for commands that are imported from another session do not include the prefix that you assign by using the **Prefix** parameter.</span></span> <span data-ttu-id="df6a1-314">Windows PowerShell 2.0 でインポートしたコマンドのヘルプを取得するには、元の (プレフィックスなしの) コマンド名を使用します。</span><span class="sxs-lookup"><span data-stu-id="df6a1-314">To get help for an imported command in Windows PowerShell 2.0, use the original (non-prefixed) command name.</span></span>

## <span data-ttu-id="df6a1-315">関連リンク</span><span class="sxs-lookup"><span data-stu-id="df6a1-315">RELATED LINKS</span></span>

[<span data-ttu-id="df6a1-316">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="df6a1-316">Export-PSSession</span></span>](Export-PSSession.md)
